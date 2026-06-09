# WppLoadTracingSupport

- ea: `0x14000f1cc`
- end: `0x14000f30c`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011168`

## callees

- `0x140007170`
- `0x14000f1cc`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f1fe`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f22c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f25a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f2b5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f2e8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f1fe`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f22c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f25a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f2b5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f2e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f21c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f24a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f21c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f24a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f2d8`

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
0x14000f1cc  push    rbp
0x14000f1ce  mov     rbp, rsp
0x14000f1d1  sub     rsp, 40h
0x14000f1d5  xorps   xmm0, xmm0
0x14000f1d8  mov     [rbp+arg_0], 0
0x14000f1df  lea     rdx, aPsgetversion; "PsGetVersion"
0x14000f1e6  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f1ea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000f1ee  call    cs:__imp_RtlInitUnicodeString
0x14000f1f5  nop     dword ptr [rax+rax+00h]
0x14000f1fa  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f1fe  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f205  nop     dword ptr [rax+rax+00h]
0x14000f20a  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x14000f211  mov     cs:pfnWppGetVersion, rax
0x14000f218  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f21c  call    cs:__imp_RtlInitUnicodeString
0x14000f223  nop     dword ptr [rax+rax+00h]
0x14000f228  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f22c  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f233  nop     dword ptr [rax+rax+00h]
0x14000f238  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x14000f23f  mov     cs:pfnWppTraceMessage, rax
0x14000f246  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f24a  call    cs:__imp_RtlInitUnicodeString
0x14000f251  nop     dword ptr [rax+rax+00h]
0x14000f256  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f25a  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f261  nop     dword ptr [rax+rax+00h]
0x14000f266  mov     cs:pfnWppQueryTraceInformation, rax
0x14000f26d  mov     rax, cs:pfnWppGetVersion
0x14000f274  mov     cs:WPPTraceSuite, 2
0x14000f27e  test    rax, rax
0x14000f281  jz      short loc_14000F294
0x14000f283  xor     r9d, r9d
0x14000f286  lea     rcx, [rbp+arg_0]
0x14000f28a  xor     r8d, r8d
0x14000f28d  xor     edx, edx
0x14000f28f  call    _guard_dispatch_icall
0x14000f294  cmp     [rbp+arg_0], 6
0x14000f298  jb      short loc_14000F305
0x14000f29a  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x14000f2a1  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f2a5  call    cs:__imp_RtlInitUnicodeString
0x14000f2ac  nop     dword ptr [rax+rax+00h]
0x14000f2b1  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f2b5  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f2bc  nop     dword ptr [rax+rax+00h]
0x14000f2c1  mov     cs:pfnEtwRegisterClassicProvider, rax
0x14000f2c8  test    rax, rax
0x14000f2cb  jz      short loc_14000F305
0x14000f2cd  lea     rdx, aEtwunregister; "EtwUnregister"
0x14000f2d4  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f2d8  call    cs:__imp_RtlInitUnicodeString
0x14000f2df  nop     dword ptr [rax+rax+00h]
0x14000f2e4  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000f2e8  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f2ef  nop     dword ptr [rax+rax+00h]
0x14000f2f4  mov     cs:pfnEtwUnregister, rax
0x14000f2fb  mov     cs:WPPTraceSuite, 4
0x14000f305  add     rsp, 40h
0x14000f309  pop     rbp
0x14000f30a  retn
```
