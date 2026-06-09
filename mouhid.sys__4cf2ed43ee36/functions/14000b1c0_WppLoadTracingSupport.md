# WppLoadTracingSupport

- ea: `0x14000b1c0`
- end: `0x14000b300`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d078`

## callees

- `0x140004e10`
- `0x14000b1c0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b1f2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b220`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b24e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b2a9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b2dc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b1f2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b220`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b24e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b2a9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000b2dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b1e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b210`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b23e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b299`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b2cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b1e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b210`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b23e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b299`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b2cc`

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
  pfnWppTraceMessage = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
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
      pfnEtwUnregister = (__int64)result;
      WPPTraceSuite = 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b1c0  push    rbp
0x14000b1c2  mov     rbp, rsp
0x14000b1c5  sub     rsp, 40h
0x14000b1c9  xorps   xmm0, xmm0
0x14000b1cc  mov     [rbp+arg_0], 0
0x14000b1d3  lea     rdx, aPsgetversion; "PsGetVersion"
0x14000b1da  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b1de  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b1e2  call    cs:__imp_RtlInitUnicodeString
0x14000b1e9  nop     dword ptr [rax+rax+00h]
0x14000b1ee  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000b1f2  call    cs:__imp_MmGetSystemRoutineAddress
0x14000b1f9  nop     dword ptr [rax+rax+00h]
0x14000b1fe  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x14000b205  mov     cs:pfnWppGetVersion, rax
0x14000b20c  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b210  call    cs:__imp_RtlInitUnicodeString
0x14000b217  nop     dword ptr [rax+rax+00h]
0x14000b21c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000b220  call    cs:__imp_MmGetSystemRoutineAddress
0x14000b227  nop     dword ptr [rax+rax+00h]
0x14000b22c  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x14000b233  mov     cs:pfnWppTraceMessage, rax
0x14000b23a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b23e  call    cs:__imp_RtlInitUnicodeString
0x14000b245  nop     dword ptr [rax+rax+00h]
0x14000b24a  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000b24e  call    cs:__imp_MmGetSystemRoutineAddress
0x14000b255  nop     dword ptr [rax+rax+00h]
0x14000b25a  mov     cs:pfnWppQueryTraceInformation, rax
0x14000b261  mov     rax, cs:pfnWppGetVersion
0x14000b268  mov     cs:WPPTraceSuite, 2
0x14000b272  test    rax, rax
0x14000b275  jz      short loc_14000B288
0x14000b277  xor     r9d, r9d
0x14000b27a  lea     rcx, [rbp+arg_0]
0x14000b27e  xor     r8d, r8d
0x14000b281  xor     edx, edx
0x14000b283  call    _guard_dispatch_icall
0x14000b288  cmp     [rbp+arg_0], 6
0x14000b28c  jb      short loc_14000B2F9
0x14000b28e  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x14000b295  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b299  call    cs:__imp_RtlInitUnicodeString
0x14000b2a0  nop     dword ptr [rax+rax+00h]
0x14000b2a5  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000b2a9  call    cs:__imp_MmGetSystemRoutineAddress
0x14000b2b0  nop     dword ptr [rax+rax+00h]
0x14000b2b5  mov     cs:pfnEtwRegisterClassicProvider, rax
0x14000b2bc  test    rax, rax
0x14000b2bf  jz      short loc_14000B2F9
0x14000b2c1  lea     rdx, aEtwunregister; "EtwUnregister"
0x14000b2c8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b2cc  call    cs:__imp_RtlInitUnicodeString
0x14000b2d3  nop     dword ptr [rax+rax+00h]
0x14000b2d8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000b2dc  call    cs:__imp_MmGetSystemRoutineAddress
0x14000b2e3  nop     dword ptr [rax+rax+00h]
0x14000b2e8  mov     cs:pfnEtwUnregister, rax
0x14000b2ef  mov     cs:WPPTraceSuite, 4
0x14000b2f9  add     rsp, 40h
0x14000b2fd  pop     rbp
0x14000b2fe  retn
```
