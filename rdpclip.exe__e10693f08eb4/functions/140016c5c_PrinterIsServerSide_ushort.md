# PrinterIsServerSide(ushort *)

- ea: `0x140016c5c`
- end: `0x140016cf0`
- name: `?PrinterIsServerSide@@YAHPEAG@Z`
- size: `148`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016cf8`

## callees

- `0x140016c5c`

## import_xrefs

- `ext-ms-win-printer-winspool-l1-1-2!GetPrinterDataW` at `0x140016cce`
- `ext-ms-win-printer-winspool-l1-1-2!GetPrinterDataW` at `0x140016cce`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x140016cdd`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x140016cdd`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x140016ca0`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x140016ca0`

## pseudocode

```c
__int64 __fastcall PrinterIsServerSide(unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  HANDLE phPrinter; // [rsp+30h] [rbp-20h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+38h] [rbp-18h] BYREF
  DWORD pcbNeeded; // [rsp+68h] [rbp+18h] BYREF
  int pData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pType; // [rsp+78h] [rbp+28h] BYREF

  pType = 0;
  pData = 0;
  pcbNeeded = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  phPrinter = 0;
  v1 = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 8;
  if ( OpenPrinterW(a1, &phPrinter, &pDefault) )
  {
    LOBYTE(v1) = GetPrinterDataW(phPrinter, (LPWSTR)L"TSSessionID", &pType, (LPBYTE)&pData, 4u, &pcbNeeded) != 0;
    ClosePrinter(phPrinter);
  }
  return v1;
}

```

## disassembly

```asm
0x140016c5c  mov     [rsp-8+arg_0], rbx
0x140016c61  push    rbp
0x140016c62  mov     rbp, rsp
0x140016c65  sub     rsp, 50h
0x140016c69  xorps   xmm0, xmm0
0x140016c6c  mov     [rbp+pType], 0
0x140016c73  lea     r8, [rbp+pDefault]; pDefault
0x140016c77  mov     [rbp+pData], 0
0x140016c7e  lea     rdx, [rbp+phPrinter]; phPrinter
0x140016c82  mov     [rbp+arg_8], 0
0x140016c89  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x140016c8e  mov     [rbp+phPrinter], 0
0x140016c96  xor     ebx, ebx
0x140016c98  mov     qword ptr [rbp+pDefault.DesiredAccess], 8
0x140016ca0  call    cs:__imp_OpenPrinterW
0x140016ca6  test    eax, eax
0x140016ca8  jz      short loc_140016CE3
0x140016caa  mov     rcx, [rbp+phPrinter]; hPrinter
0x140016cae  lea     rax, [rbp+arg_8]
0x140016cb2  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x140016cb7  lea     r9, [rbp+pData]; pData
0x140016cbb  lea     r8, [rbp+pType]; pType
0x140016cbf  mov     [rsp+50h+nSize], 4; nSize
0x140016cc7  lea     rdx, pValueName; "TSSessionID"
0x140016cce  call    cs:__imp_GetPrinterDataW
0x140016cd4  mov     rcx, [rbp+phPrinter]; hPrinter
0x140016cd8  test    eax, eax
0x140016cda  setnz   bl
0x140016cdd  call    cs:__imp_ClosePrinter
0x140016ce3  mov     eax, ebx
0x140016ce5  mov     rbx, [rsp+50h+arg_0]
0x140016cea  add     rsp, 50h
0x140016cee  pop     rbp
0x140016cef  retn
```
