# AVrfpVerifierStopInitialize

- ea: `0x18011e5b0`
- end: `0x18011e66a`
- name: `AVrfpVerifierStopInitialize`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180112488`

## callees

- `0x180007060`
- `0x180050f70`
- `0x1800cca40`
- `0x18011e5b0`
- `0x180127d10`

## string_xrefs

- `0x18011e5de`: `verifier.dll`
- `0x18011e652`: `AVRF: Failed to find verifier.dll among loaded providers! \n`
- `0x18011e634`: `AVRF: Failed to find `VerifierStopMessage()' export in verifier.dll! \n`

## pseudocode

```c
__int64 AVrfpVerifierStopInitialize()
{
  __int64 v0; // rbx
  __int64 v1; // rbx
  int ProcedureAddress; // ebx
  STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF

  v0 = AVrfpVerifierProvidersList;
  DestinationString = 0;
  v5 = 0;
  while ( 1 )
  {
    if ( (__int64 *)v0 == &AVrfpVerifierProvidersList )
      goto LABEL_10;
    if ( !wcsicmp(*(const wchar_t **)(v0 + 24), L"verifier.dll") )
      break;
    v0 = *(_QWORD *)v0;
  }
  v1 = *(_QWORD *)(*(_QWORD *)(v0 + 32) + 48LL);
  if ( !v1 )
  {
LABEL_10:
    DbgPrint("AVRF: Failed to find verifier.dll among loaded providers! \n");
    return 3221225473LL;
  }
  RtlInitAnsiString(&DestinationString, "VerifierStopMessage");
  ProcedureAddress = LdrGetProcedureAddressEx(v1, (unsigned int)&DestinationString, 0, (unsigned int)&v5, 0);
  if ( ProcedureAddress >= 0 )
    AVrfpVerifierStopMessageFunction = v5;
  else
    DbgPrint("AVRF: Failed to find `VerifierStopMessage()' export in verifier.dll! \n");
  return (unsigned int)ProcedureAddress;
}

```

## disassembly

```asm
0x18011e5b0  push    rbx
0x18011e5b2  sub     rsp, 40h
0x18011e5b6  mov     rbx, cs:AVrfpVerifierProvidersList
0x18011e5bd  xorps   xmm0, xmm0
0x18011e5c0  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18011e5c5  mov     [rsp+48h+arg_0], 0
0x18011e5ce  lea     rax, AVrfpVerifierProvidersList
0x18011e5d5  cmp     rbx, rax
0x18011e5d8  jz      short loc_18011E652
0x18011e5da  mov     rcx, [rbx+18h]; String1
0x18011e5de  lea     rdx, aVerifierDll; "verifier.dll"
0x18011e5e5  call    _wcsicmp
0x18011e5ea  test    eax, eax
0x18011e5ec  jz      short loc_18011E5F3
0x18011e5ee  mov     rbx, [rbx]
0x18011e5f1  jmp     short loc_18011E5CE
0x18011e5f3  mov     rax, [rbx+20h]
0x18011e5f7  mov     rbx, [rax+30h]
0x18011e5fb  test    rbx, rbx
0x18011e5fe  jz      short loc_18011E652
0x18011e600  lea     rdx, aVerifierstopme; "VerifierStopMessage"
0x18011e607  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18011e60c  call    RtlInitAnsiString
0x18011e611  lea     r9, [rsp+48h+arg_0]
0x18011e616  mov     [rsp+48h+var_28], 0
0x18011e61e  xor     r8d, r8d
0x18011e621  lea     rdx, [rsp+48h+DestinationString]
0x18011e626  mov     rcx, rbx
0x18011e629  call    LdrGetProcedureAddressEx
0x18011e62e  mov     ebx, eax
0x18011e630  test    eax, eax
0x18011e632  jns     short loc_18011E644
0x18011e634  lea     rcx, aAvrfFailedToFi; "AVRF: Failed to find `VerifierStopMessa"...
0x18011e63b  call    DbgPrint
0x18011e640  mov     eax, ebx
0x18011e642  jmp     short loc_18011E663
0x18011e644  mov     rax, [rsp+48h+arg_0]
0x18011e649  mov     cs:AVrfpVerifierStopMessageFunction, rax
0x18011e650  jmp     short loc_18011E640
0x18011e652  lea     rcx, aAvrfFailedToFi_0; "AVRF: Failed to find verifier.dll among"...
0x18011e659  call    DbgPrint
0x18011e65e  mov     eax, 0C0000001h
0x18011e663  add     rsp, 40h
0x18011e667  pop     rbx
0x18011e668  retn
```
