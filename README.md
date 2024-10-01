#!/usr/bin/env python
# coding: utf-8

# In[1]:


from datetime import date

class Guest:
    def __init__(self, guest_id: int, name: str, email: str, phone: str, credit_card_info: str):
        self._guest_id = guest_id
        self._name = name
        self._email = email
        self._phone = phone
        self._credit_card_info = credit_card_info
    
    # Getters
    def get_guest_id(self) -> int:
        return self._guest_id
    
    def get_name(self) -> str:
        return self._name
    
    def get_email(self) -> str:
        return self._email
    
    def get_phone(self) -> str:
        return self._phone
    
    def get_credit_card_info(self) -> str:
        return self._credit_card_info
    
    # Setters
    def set_name(self, name: str):
        self._name = name
    
    def set_email(self, email: str):
        self._email = email
    
    def set_phone(self, phone: str):
        self._phone = phone
    
    def set_credit_card_info(self, credit_card_info: str):
        self._credit_card_info = credit_card_info
    
    # Methods
    def view_reservation(self, reservation_id: int):
        """ Method to view the guest's reservation details """
        pass  # Logic for viewing reservation details
    
    def modify_reservation(self, reservation_id: int, new_checkin_date: date, new_checkout_date: date):
        """ Method to modify the guest's reservation """
        pass  # Logic for modifying reservation

    def cancel_reservation(self, reservation_id: int):
        """ Method to cancel the guest's reservation """
        pass  # Logic for canceling reservation


class Room:
    def __init__(self, room_id: int, room_type: str, is_available: bool, room_rate: float):
        self._room_id = room_id
        self._room_type = room_type
        self._is_available = is_available
        self._room_rate = room_rate
    
    # Getters
    def get_room_id(self) -> int:
        return self._room_id
    
    def get_room_type(self) -> str:
        return self._room_type
    
    def get_is_available(self) -> bool:
        return self._is_available
    
    def get_room_rate(self) -> float:
        return self._room_rate
    
    # Setters
    def set_room_type(self, room_type: str):
        self._room_type = room_type
    
    def set_is_available(self, is_available: bool):
        self._is_available = is_available
    
    def set_room_rate(self, room_rate: float):
        self._room_rate = room_rate
    
    # Methods
    def check_availability(self, checkin_date: date, checkout_date: date) -> bool:
        """ Method to check room availability for a specific period """
        pass  # Logic to check availability
    
    def assign_room(self, guest: Guest) -> bool:
        """ Method to assign room to a guest """
        pass  # Logic to assign room to guest


class Payment:
    def __init__(self, payment_id: int, payment_date: date, amount: float, payment_method: str, payment_status: str):
        self._payment_id = payment_id
        self._payment_date = payment_date
        self._amount = amount
        self._payment_method = payment_method
        self._payment_status = payment_status
    
    # Getters
    def get_payment_id(self) -> int:
        return self._payment_id
    
    def get_payment_date(self) -> date:
        return self._payment_date
    
    def get_amount(self) -> float:
        return self._amount
    
    def get_payment_method(self) -> str:
        return self._payment_method
    
    def get_payment_status(self) -> str:
        return self._payment_status
    
    # Setters
    def set_payment_method(self, payment_method: str):
        self._payment_method = payment_method
    
    def set_payment_status(self, payment_status: str):
        self._payment_status = payment_status
    
    # Methods
    def process_payment(self, amount: float, payment_method: str) -> bool:
        """ Method to process payment for the reservation """
        pass  # Logic for payment processing
    
    def refund_payment(self, payment_id: int) -> bool:
        """ Method to refund payment """
        pass  # Logic for refund processing


class Reservation:
    def __init__(self, reservation_id: int, checkin_date: date, checkout_date: date, guest: Guest, room: Room, total_amount: float, payment_status: str):
        self._reservation_id = reservation_id
        self._checkin_date = checkin_date
        self._checkout_date = checkout_date
        self._guest = guest
        self._room = room
        self._total_amount = total_amount
        self._payment_status = payment_status
    
    # Getters
    def get_reservation_id(self) -> int:
        return self._reservation_id
    
    def get_checkin_date(self) -> date:
        return self._checkin_date
    
    def get_checkout_date(self) -> date:
        return self._checkout_date
    
    def get_guest(self) -> Guest:
        return self._guest
    
    def get_room(self) -> Room:
        return self._room
    
    def get_total_amount(self) -> float:
        return self._total_amount
    
    def get_payment_status(self) -> str:
        return self._payment_status
    
    # Setters
    def set_checkin_date(self, checkin_date: date):
        self._checkin_date = checkin_date
    
    def set_checkout_date(self, checkout_date: date):
        self._checkout_date = checkout_date
    
    def set_room(self, room: Room):
        self._room = room
    
    def set_total_amount(self, total_amount: float):
        self._total_amount = total_amount
    
    def set_payment_status(self, payment_status: str):
        self._payment_status = payment_status
    
    # Methods
    def create_reservation(self, guest: Guest, room: Room, checkin_date: date, checkout_date: date):
        """ Method to create a new reservation """
        pass  # Logic for creating reservation
    
    def cancel_reservation(self) -> bool:
        """ Method to cancel the reservation """
        pass  # Logic for canceling reservation
    
    def modify_reservation(self, new_checkin_date: date, new_checkout_date: date) -> bool:
        """ Method to modify the reservation """
        pass  # Logic for modifying reservation
    
    def get_reservation_details(self):
        """ Method to retrieve reservation details """
        pass  # Logic for fetching reservation details



# In[2]:


from datetime import date

# Create the Guest object
guest = Guest(
    guest_id=1,
    name="Ted H Vera",
    email="tedvera@mac.com",
    phone="505-661-1110",
    credit_card_info="Mastercard (ending in 9904)"
)

# Create the Room object
room = Room(
    room_id=101,
    room_type="2 Queen Beds / No Smoking / Desk / Safe / Coffee Maker / In Room / Hair Dryer",
    is_available=True,
    room_rate=89.95
)

# Create the Payment object
payment = Payment(
    payment_id=1001,
    payment_date=date(2010, 8, 22),
    amount=201.48,
    payment_method="Mastercard (ending in 9904)",
    payment_status="Paid"
)

# Create the Reservation object
reservation = Reservation(
    reservation_id=1355,
    checkin_date=date(2010, 8, 22),
    checkout_date=date(2010, 8, 24),
    guest=guest,
    room=room,
    total_amount=201.48,
    payment_status="Paid"
)

# Display reservation information
def display_reservation_details(reservation: Reservation, payment: Payment):
    print("Your Reservation is Confirmed")
    print(f"Thank you for your reservation. Please print your hotel receipt and show it at check-in.")
    print(f"Your Name: {reservation.get_guest().get_name()}")
    print(f"Your Email: {reservation.get_guest().get_email()}")
    print(f"Priceline Trip Number: {reservation.get_reservation_id()}")
    print(f"Hotel Confirmation Number: 5225387")
    print("\nComfort Inn & Suites Los Alamos")
    print("2455 Trinity Drive, Los Alamos, NM 87544")
    print(f"Check-In: Sun, {reservation.get_checkin_date().strftime('%b %d, %Y')}, 02:00 PM")
    print(f"Check-Out: Tue, {reservation.get_checkout_date().strftime('%b %d, %Y')}, 12:00 PM")
    print(f"Number of Nights: 2")
    print(f"Phone: 505-661-1110")
    print(f"Number of Rooms: 1")
    print(f"Room 1: {reservation.get_guest().get_name()}")
    print(f"Room Type: {reservation.get_room().get_room_type()}")
    
    print("\nSummary of Charges")
    print(f"Billing Name: {reservation.get_guest().get_name()}")
    print(f"Credit Card: {payment.get_payment_method()}")
    print(f"Room Cost (per room per night): ${reservation.get_room().get_room_rate():.2f}")
    print(f"Rooms: 1")
    print(f"Nights: 2")
    print(f"Room Subtotal: ${reservation.get_room().get_room_rate() * 2:.2f}")
    print(f"Taxes and Fees: $21.58")
    print(f"Total Charges: ${reservation.get_total_amount():.2f}")

# Call the function to display the reservation details
display_reservation_details(reservation, payment)


# In[ ]:




