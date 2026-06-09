# PTQuerySchemaVersionSupport

- ea: `0x1800196c0`
- end: `0x180019798`
- name: `PTQuerySchemaVersionSupport`
- size: `216`
- prototype: `HRESULT __stdcall(PCWSTR pszPrinterName, DWORD *pMaxVersion)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f970`
- `0x180018d08`
- `0x1800196c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019743`
- `KERNEL32!GetLastError` at `0x180019743`
- `WINSPOOL!OpenPrinterW` at `0x180019724`
- `WINSPOOL!OpenPrinterW` at `0x180019724`
- `WINSPOOL!ClosePrinter` at `0x18001973b`
- `WINSPOOL!ClosePrinter` at `0x18001973b`

## pseudocode

```c
HRESULT __stdcall PTQuerySchemaVersionSupport(PCWSTR pszPrinterName, DWORD *pMaxVersion)
{
  __int64 v2; // r8
  __int64 v3; // r9
  HANDLE v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  signed int LastError; // eax
  HANDLE phPrinter; // [rsp+30h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+38h] [rbp-20h] BYREF

  if ( !pszPrinterName || !pMaxVersion )
    return -2147024809;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)pszPrinterName,
      (const EVENT_DESCRIPTOR *)&DocPerf_PrintTicket_QuerySchemaVersionSupport_Start,
      v2,
      v3,
      &v14);
  phPrinter = 0;
  if ( OpenPrinterW((LPWSTR)pszPrinterName, &phPrinter, 0) )
  {
    v6 = phPrinter;
    v7 = 0;
    *pMaxVersion = 1;
    ClosePrinter(v6);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v8,
      (const EVENT_DESCRIPTOR *)&DocPerf_PrintTicket_QuerySchemaVersionSupport_Stop,
      v9,
      v10,
      &v14);
  return v7;
}

```

## disassembly

```asm
0x1800196c0  mov     [rsp+arg_10], rbx
0x1800196c5  push    rdi
0x1800196c6  sub     rsp, 50h
0x1800196ca  mov     rax, cs:__security_cookie
0x1800196d1  xor     rax, rsp
0x1800196d4  mov     [rsp+58h+var_10], rax
0x1800196d9  mov     rdi, rdx
0x1800196dc  mov     rbx, rcx
0x1800196df  test    rcx, rcx
0x1800196e2  jz      loc_18001977B
0x1800196e8  test    rdx, rdx
0x1800196eb  jz      loc_18001977B
0x1800196f1  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x1800196f8  jz      short loc_180019710
0x1800196fa  lea     rax, [rsp+58h+var_20]
0x1800196ff  lea     rdx, DocPerf_PrintTicket_QuerySchemaVersionSupport_Start; int
0x180019706  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x18001970b  call    McGenEventWrite_EventWriteTransfer
0x180019710  xor     r8d, r8d; pDefault
0x180019713  mov     [rsp+58h+phPrinter], 0
0x18001971c  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x180019721  mov     rcx, rbx; pPrinterName
0x180019724  call    cs:__imp_OpenPrinterW
0x18001972a  test    eax, eax
0x18001972c  jz      short loc_180019743
0x18001972e  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x180019733  xor     ebx, ebx
0x180019735  mov     dword ptr [rdi], 1
0x18001973b  call    cs:__imp_ClosePrinter
0x180019741  jmp     short loc_180019758
0x180019743  call    cs:__imp_GetLastError
0x180019749  mov     ebx, eax
0x18001974b  test    eax, eax
0x18001974d  jle     short loc_180019758
0x18001974f  movzx   ebx, ax
0x180019752  or      ebx, 80070000h
0x180019758  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18001975f  jz      short loc_180019777
0x180019761  lea     rax, [rsp+58h+var_20]
0x180019766  lea     rdx, DocPerf_PrintTicket_QuerySchemaVersionSupport_Stop; int
0x18001976d  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x180019772  call    McGenEventWrite_EventWriteTransfer
0x180019777  mov     eax, ebx
0x180019779  jmp     short loc_180019780
0x18001977b  mov     eax, 80070057h
0x180019780  mov     rcx, [rsp+58h+var_10]
0x180019785  xor     rcx, rsp; StackCookie
0x180019788  call    __security_check_cookie
0x18001978d  mov     rbx, [rsp+58h+arg_10]
0x180019792  add     rsp, 50h
0x180019796  pop     rdi
0x180019797  retn
```
