# ResourceBookingPagedEntitySQLQuery::InitQuery

- ea: `0x143a0`
- end: `0x143de`
- name: `ResourceBookingPagedEntitySQLQuery::InitQuery`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14360`
- `0x147b0`
- `0x14860`
- `0x14cd0`

## string_xrefs

- `0x143d1`: `JOIN BookingStatus ON BookingStatus.BookingStatusId = BookableResourceBooking.BookingStatus`

## pseudocode

```c

```

## disassembly

```asm
0x143a0  ldarg.2
0x143a1  ldstr    aSelectBookable// "SELECT BookableResourceBooking.Bookable"...
0x143a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143ab  pop
0x143ac  ldarg.2
0x143ad  ldstr    aBookableresour_3// "BookableResourceBooking.EndTime, Bookab"...
0x143b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143b7  pop
0x143b8  ldarg.2
0x143b9  ldstr    aBookingstatusS_0// "BookingStatus.Status AS Booking_Status"
0x143be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143c3  pop
0x143c4  ldarg.2
0x143c5  ldstr    aFromBookablere// "FROM BookableResourceBooking"
0x143ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143cf  pop
0x143d0  ldarg.2
0x143d1  ldstr    aJoinBookingsta// "JOIN BookingStatus ON BookingStatus.Boo"...
0x143d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143db  pop
0x143dc  ldarg.2
0x143dd  ret
```
