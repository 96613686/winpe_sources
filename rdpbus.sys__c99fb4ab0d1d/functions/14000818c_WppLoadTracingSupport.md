# WppLoadTracingSupport

- ea: `0x14000818c`
- end: `0x1400082cc`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b078`

## callees

- `0x140002560`
- `0x14000818c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400081ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000820a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008265`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008298`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000820a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008265`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008298`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081be`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081ec`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000821a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008275`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400082a8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081be`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081ec`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000821a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008275`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400082a8`

## pseudocode

```c
PVOID WppLoadTracingSupport()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v2; // [rsp+50h] [rbp+10h] BYREF

  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"PsGetVersion");
  pfnWppGetVersion = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiTraceMessage");
  pfnWppTraceMessage = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiQueryTraceInformation");
  pfnWppQueryTraceInformation = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  result = pfnWppGetVersion;
  WPPTraceSuite = 2;
  if ( pfnWppGetVersion )
    result = (PVOID)pfnWppGetVersion(&v2, 0, 0, 0);
  if ( v2 >= 6 )
  {
    RtlInitUnicodeString(&DestinationString, L"EtwRegisterClassicProvider");
    result = MmGetSystemRoutineAddress(&DestinationString);
    pfnEtwRegisterClassicProvider = (__int64)result;
    if ( result )
    {
      RtlInitUnicodeString(&DestinationString, L"EtwUnregister");
      result = MmGetSystemRoutineAddress(&DestinationString);
      WPP_MAIN_CB.DeviceExtension = result;
      WPPTraceSuite = 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000818c  push    rbp
0x14000818e  mov     rbp, rsp
0x140008191  sub     rsp, 40h
0x140008195  xorps   xmm0, xmm0
0x140008198  mov     [rbp+arg_0], 0
0x14000819f  lea     rdx, aPsgetversion; "PsGetVersion"
0x1400081a6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400081aa  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400081ae  call    cs:__imp_RtlInitUnicodeString
0x1400081b5  nop     dword ptr [rax+rax+00h]
0x1400081ba  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400081be  call    cs:__imp_MmGetSystemRoutineAddress
0x1400081c5  nop     dword ptr [rax+rax+00h]
0x1400081ca  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x1400081d1  mov     cs:pfnWppGetVersion, rax
0x1400081d8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400081dc  call    cs:__imp_RtlInitUnicodeString
0x1400081e3  nop     dword ptr [rax+rax+00h]
0x1400081e8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400081ec  call    cs:__imp_MmGetSystemRoutineAddress
0x1400081f3  nop     dword ptr [rax+rax+00h]
0x1400081f8  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x1400081ff  mov     cs:pfnWppTraceMessage, rax
0x140008206  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000820a  call    cs:__imp_RtlInitUnicodeString
0x140008211  nop     dword ptr [rax+rax+00h]
0x140008216  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000821a  call    cs:__imp_MmGetSystemRoutineAddress
0x140008221  nop     dword ptr [rax+rax+00h]
0x140008226  mov     cs:pfnWppQueryTraceInformation, rax
0x14000822d  mov     rax, cs:pfnWppGetVersion
0x140008234  mov     cs:WPPTraceSuite, 2
0x14000823e  test    rax, rax
0x140008241  jz      short loc_140008254
0x140008243  xor     r9d, r9d
0x140008246  lea     rcx, [rbp+arg_0]
0x14000824a  xor     r8d, r8d
0x14000824d  xor     edx, edx
0x14000824f  call    _guard_dispatch_icall
0x140008254  cmp     [rbp+arg_0], 6
0x140008258  jb      short loc_1400082C5
0x14000825a  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x140008261  lea     rcx, [rbp+DestinationString]; DestinationString
0x140008265  call    cs:__imp_RtlInitUnicodeString
0x14000826c  nop     dword ptr [rax+rax+00h]
0x140008271  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140008275  call    cs:__imp_MmGetSystemRoutineAddress
0x14000827c  nop     dword ptr [rax+rax+00h]
0x140008281  mov     cs:pfnEtwRegisterClassicProvider, rax
0x140008288  test    rax, rax
0x14000828b  jz      short loc_1400082C5
0x14000828d  lea     rdx, aEtwunregister; "EtwUnregister"
0x140008294  lea     rcx, [rbp+DestinationString]; DestinationString
0x140008298  call    cs:__imp_RtlInitUnicodeString
0x14000829f  nop     dword ptr [rax+rax+00h]
0x1400082a4  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400082a8  call    cs:__imp_MmGetSystemRoutineAddress
0x1400082af  nop     dword ptr [rax+rax+00h]
0x1400082b4  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x1400082bb  mov     cs:WPPTraceSuite, 4
0x1400082c5  add     rsp, 40h
0x1400082c9  pop     rbp
0x1400082ca  retn
```
