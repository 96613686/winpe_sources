# ForceSyncPrinterDriver(ushort const *)

- ea: `0x18002f4e4`
- end: `0x18002f599`
- name: `?ForceSyncPrinterDriver@@YAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002f364`
- `0x18002fc34`

## callees

- `0x18000d57c`
- `0x180018d18`
- `0x18002f4e4`

## import_xrefs

- `WINSPOOL!SetPrinterDataW` at `0x18002f548`
- `WINSPOOL!SetPrinterDataW` at `0x18002f548`
- `WINSPOOL!ClosePrinter` at `0x18002f563`
- `WINSPOOL!ClosePrinter` at `0x18002f563`
- `WINSPOOL!OpenPrinter2W` at `0x18002f528`
- `WINSPOOL!OpenPrinter2W` at `0x18002f528`

## pseudocode

```c
__int64 __fastcall ForceSyncPrinterDriver(const unsigned __int16 *a1)
{
  signed int v2; // eax
  unsigned int LastErrorAsHResult; // ebx
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-20h] BYREF
  int pData; // [rsp+78h] [rbp+28h] BYREF
  HANDLE phPrinter; // [rsp+80h] [rbp+30h] BYREF
  _PRINTER_OPTIONSW pOptions; // [rsp+88h] [rbp+38h] BYREF

  pOptions.cbSize = 8;
  phPrinter = (HANDLE)-1LL;
  *(_QWORD *)&pDefault.DesiredAccess = 4;
  pOptions.dwFlags = 4;
  pData = 1;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( OpenPrinter2W(a1, &phPrinter, &pDefault, &pOptions) )
  {
    v2 = SetPrinterDataW(phPrinter, (LPWSTR)L"bad38fb9-39eb-404b-9589-5a396316a93c", 4u, (LPBYTE)&pData, 4u);
    LastErrorAsHResult = v2;
    if ( v2 > 0 )
      LastErrorAsHResult = (unsigned __int16)v2 | 0x80070000;
    ClosePrinter(phPrinter);
  }
  else
  {
    LastErrorAsHResult = GetLastErrorAsHResult();
  }
  if ( (LastErrorAsHResult & 0x80000000) != 0 )
    ClassInstallerTelemetry::WriteDbgTraceError(
      "ForceSyncPrinterDriver",
      L"ForceSyncPrinterDriver(%ws) failed hr: 0x%x",
      a1,
      LastErrorAsHResult);
  return LastErrorAsHResult;
}

```

## disassembly

```asm
0x18002f4e4  push    rbp
0x18002f4e6  push    rbx
0x18002f4e7  push    rdi
0x18002f4e8  mov     rbp, rsp
0x18002f4eb  sub     rsp, 50h
0x18002f4ef  xorps   xmm0, xmm0
0x18002f4f2  mov     [rbp+pOptions.cbSize], 8
0x18002f4f9  mov     ebx, 4
0x18002f4fe  mov     [rbp+phPrinter], 0FFFFFFFFFFFFFFFFh
0x18002f506  lea     r9, [rbp+pOptions]; pOptions
0x18002f50a  mov     qword ptr [rbp+pDefault.DesiredAccess], rbx
0x18002f50e  lea     r8, [rbp+pDefault]; pDefault
0x18002f512  mov     [rbp+pOptions.dwFlags], ebx
0x18002f515  lea     rdx, [rbp+phPrinter]; phPrinter
0x18002f519  mov     [rbp+pData], 1
0x18002f520  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18002f525  mov     rdi, rcx
0x18002f528  call    cs:__imp_OpenPrinter2W
0x18002f52e  test    eax, eax
0x18002f530  jz      short loc_18002F56B
0x18002f532  mov     rcx, [rbp+phPrinter]; hPrinter
0x18002f536  lea     r9, [rbp+pData]; pData
0x18002f53a  mov     r8d, ebx; Type
0x18002f53d  mov     [rsp+50h+cbData], ebx; cbData
0x18002f541  lea     rdx, aBad38fb939eb40; "bad38fb9-39eb-404b-9589-5a396316a93c"
0x18002f548  call    cs:__imp_SetPrinterDataW
0x18002f54e  mov     ebx, eax
0x18002f550  test    eax, eax
0x18002f552  jz      short loc_18002F55F
0x18002f554  jle     short loc_18002F55F
0x18002f556  movzx   ebx, ax
0x18002f559  or      ebx, 80070000h
0x18002f55f  mov     rcx, [rbp+phPrinter]; hPrinter
0x18002f563  call    cs:__imp_ClosePrinter
0x18002f569  jmp     short loc_18002F572
0x18002f56b  call    GetLastErrorAsHResult
0x18002f570  mov     ebx, eax
0x18002f572  test    ebx, ebx
0x18002f574  jns     short loc_18002F58F
0x18002f576  mov     r9d, ebx
0x18002f579  lea     rdx, aForcesyncprint; "ForceSyncPrinterDriver(%ws) failed hr: "...
0x18002f580  mov     r8, rdi
0x18002f583  lea     rcx, aForcesyncprint_0; "ForceSyncPrinterDriver"
0x18002f58a  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002f58f  mov     eax, ebx
0x18002f591  add     rsp, 50h
0x18002f595  pop     rdi
0x18002f596  pop     rbx
0x18002f597  pop     rbp
0x18002f598  retn
```
