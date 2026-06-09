# AVrfpVerifierStopInitialize

- ea: `0x18011f0a0`
- end: `0x18011f15a`
- name: `AVrfpVerifierStopInitialize`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180113878`

## callees

- `0x180007060`
- `0x18006d950`
- `0x1800ce5d0`
- `0x18011f0a0`
- `0x180128800`

## string_xrefs

- `0x18011f0ce`: `verifier.dll`
- `0x18011f142`: `AVRF: Failed to find verifier.dll among loaded providers! \n`
- `0x18011f124`: `AVRF: Failed to find `VerifierStopMessage()' export in verifier.dll! \n`

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
0x18011f0a0  push    rbx
0x18011f0a2  sub     rsp, 40h
0x18011f0a6  mov     rbx, cs:AVrfpVerifierProvidersList
0x18011f0ad  xorps   xmm0, xmm0
0x18011f0b0  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18011f0b5  mov     [rsp+48h+arg_0], 0
0x18011f0be  lea     rax, AVrfpVerifierProvidersList
0x18011f0c5  cmp     rbx, rax
0x18011f0c8  jz      short loc_18011F142
0x18011f0ca  mov     rcx, [rbx+18h]; String1
0x18011f0ce  lea     rdx, aVerifierDll; "verifier.dll"
0x18011f0d5  call    _wcsicmp
0x18011f0da  test    eax, eax
0x18011f0dc  jz      short loc_18011F0E3
0x18011f0de  mov     rbx, [rbx]
0x18011f0e1  jmp     short loc_18011F0BE
0x18011f0e3  mov     rax, [rbx+20h]
0x18011f0e7  mov     rbx, [rax+30h]
0x18011f0eb  test    rbx, rbx
0x18011f0ee  jz      short loc_18011F142
0x18011f0f0  lea     rdx, aVerifierstopme; "VerifierStopMessage"
0x18011f0f7  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18011f0fc  call    RtlInitAnsiString
0x18011f101  lea     r9, [rsp+48h+arg_0]
0x18011f106  mov     [rsp+48h+var_28], 0
0x18011f10e  xor     r8d, r8d
0x18011f111  lea     rdx, [rsp+48h+DestinationString]
0x18011f116  mov     rcx, rbx
0x18011f119  call    LdrGetProcedureAddressEx
0x18011f11e  mov     ebx, eax
0x18011f120  test    eax, eax
0x18011f122  jns     short loc_18011F134
0x18011f124  lea     rcx, aAvrfFailedToFi; "AVRF: Failed to find `VerifierStopMessa"...
0x18011f12b  call    DbgPrint
0x18011f130  mov     eax, ebx
0x18011f132  jmp     short loc_18011F153
0x18011f134  mov     rax, [rsp+48h+arg_0]
0x18011f139  mov     cs:AVrfpVerifierStopMessageFunction, rax
0x18011f140  jmp     short loc_18011F130
0x18011f142  lea     rcx, aAvrfFailedToFi_0; "AVRF: Failed to find verifier.dll among"...
0x18011f149  call    DbgPrint
0x18011f14e  mov     eax, 0C0000001h
0x18011f153  add     rsp, 40h
0x18011f157  pop     rbx
0x18011f158  retn
```
