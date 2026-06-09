# W32ProcObj::PrinterChangesMonitoringThreadFunc(void)

- ea: `0x180037a74`
- end: `0x180037f55`
- name: `?PrinterChangesMonitoringThreadFunc@W32ProcObj@@AEAAKXZ`
- size: `1249`
- prototype: `unsigned int __fastcall(W32ProcObj *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180561950`

## callees

- `0x18002a334`
- `0x180037a74`
- `0x180037f5c`
- `0x180039ab0`
- `0x180039c98`
- `0x180039ce4`
- `0x180561998`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180037f14`
- `KERNEL32!CloseHandle` at `0x180037f14`
- `KERNEL32!GetLastError` at `0x180037ad7`
- `KERNEL32!GetLastError` at `0x180037b59`
- `KERNEL32!GetLastError` at `0x180037c7a`
- `KERNEL32!GetLastError` at `0x180037cf4`
- `KERNEL32!GetLastError` at `0x180037e47`
- `KERNEL32!GetLastError` at `0x180037edb`
- `KERNEL32!GetLastError` at `0x180037ad7`
- `KERNEL32!GetLastError` at `0x180037b59`
- `KERNEL32!GetLastError` at `0x180037c7a`
- `KERNEL32!GetLastError` at `0x180037cf4`
- `KERNEL32!GetLastError` at `0x180037e47`
- `KERNEL32!GetLastError` at `0x180037edb`
- `KERNEL32!CreateWaitableTimerW` at `0x180037c6c`
- `KERNEL32!CreateWaitableTimerW` at `0x180037c6c`
- `KERNEL32!SetWaitableTimer` at `0x180037cea`
- `KERNEL32!SetWaitableTimer` at `0x180037cea`
- `KERNEL32!CancelWaitableTimer` at `0x180037f0b`
- `KERNEL32!CancelWaitableTimer` at `0x180037f0b`
- `KERNEL32!WaitForMultipleObjects` at `0x180037d6d`
- `KERNEL32!WaitForMultipleObjects` at `0x180037d6d`
- `WINSPOOL!OpenPrinterW` at `0x180037acd`
- `WINSPOOL!OpenPrinterW` at `0x180037acd`
- `WINSPOOL!ClosePrinter` at `0x180037f2d`
- `WINSPOOL!ClosePrinter` at `0x180037f2d`
- `ext-ms-win-printer-winspool-l1-1-4!FindNextPrinterChangeNotification` at `0x180037d8f`
- `ext-ms-win-printer-winspool-l1-1-4!FindNextPrinterChangeNotification` at `0x180037d8f`
- `ext-ms-win-printer-winspool-l1-1-4!FindFirstPrinterChangeNotification` at `0x180037b46`
- `ext-ms-win-printer-winspool-l1-1-4!FindFirstPrinterChangeNotification` at `0x180037b46`
- `ext-ms-win-printer-winspool-l1-1-4!FindClosePrinterChangeNotification` at `0x180037f1d`
- `ext-ms-win-printer-winspool-l1-1-4!FindClosePrinterChangeNotification` at `0x180037f1d`

## pseudocode

```c

```
