# W32DrAutoPrn::GetPrinterInfoAndSessionID(ProcObj *,ushort *,ulong,uchar * *,ulong *,ulong *,W32DrAutoPrn::_PrinterInfo *)

- ea: `0x180077590`
- end: `0x1800779e9`
- name: `?GetPrinterInfoAndSessionID@W32DrAutoPrn@@KAKPEAVProcObj@@PEAGKPEAPEAEPEAK3PEAU_PrinterInfo@1@@Z`
- size: `1113`
- prototype: `static unsigned int(struct ProcObj *, unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *, struct W32DrAutoPrn::_PrinterInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007b2d4`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180077590`
- `0x18012962c`
- `0x18012966c`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800775df`
- `KERNEL32!GetLastError` at `0x1800776e6`
- `KERNEL32!GetLastError` at `0x180077784`
- `KERNEL32!GetLastError` at `0x18007780c`
- `KERNEL32!GetLastError` at `0x180077899`
- `KERNEL32!GetLastError` at `0x1800778db`
- `KERNEL32!GetLastError` at `0x1800775df`
- `KERNEL32!GetLastError` at `0x1800776e6`
- `KERNEL32!GetLastError` at `0x180077784`
- `KERNEL32!GetLastError` at `0x18007780c`
- `KERNEL32!GetLastError` at `0x180077899`
- `KERNEL32!GetLastError` at `0x1800778db`
- `WINSPOOL!OpenPrinterW` at `0x1800775d5`
- `WINSPOOL!OpenPrinterW` at `0x1800775d5`
- `WINSPOOL!GetPrinterDriverW` at `0x1800776d8`
- `WINSPOOL!GetPrinterDriverW` at `0x18007777a`
- `WINSPOOL!GetPrinterDriverW` at `0x1800776d8`
- `WINSPOOL!GetPrinterDriverW` at `0x18007777a`
- `WINSPOOL!ClosePrinter` at `0x1800779d2`
- `WINSPOOL!ClosePrinter` at `0x1800779d2`
- `WINSPOOL!GetPrinterDataW` at `0x1800779b3`
- `WINSPOOL!GetPrinterDataW` at `0x1800779b3`
- `WINSPOOL!GetPrinterW` at `0x1800777fe`
- `WINSPOOL!GetPrinterW` at `0x18007788b`
- `WINSPOOL!GetPrinterW` at `0x1800777fe`
- `WINSPOOL!GetPrinterW` at `0x18007788b`

## pseudocode

```c

```
