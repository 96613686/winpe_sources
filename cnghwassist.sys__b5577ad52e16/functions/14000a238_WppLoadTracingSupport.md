# WppLoadTracingSupport

- ea: `0x14000a238`
- end: `0x14000a378`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c078`

## callees

- `0x140003e00`
- `0x14000a238`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a26a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a298`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a2c6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a321`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a354`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a26a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a298`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a2c6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a321`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a354`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a25a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a288`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a2b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a311`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a344`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a25a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a288`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a2b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a311`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a344`

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
      pfnEtwUnregister = (__int64)result;
      WPPTraceSuite = 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a238  push    rbp
0x14000a23a  mov     rbp, rsp
0x14000a23d  sub     rsp, 40h
0x14000a241  xorps   xmm0, xmm0
0x14000a244  mov     [rbp+arg_0], 0
0x14000a24b  lea     rdx, SourceString; "PsGetVersion"
0x14000a252  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a256  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a25a  call    cs:__imp_RtlInitUnicodeString
0x14000a261  nop     dword ptr [rax+rax+00h]
0x14000a266  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a26a  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a271  nop     dword ptr [rax+rax+00h]
0x14000a276  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x14000a27d  mov     cs:pfnWppGetVersion, rax
0x14000a284  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a288  call    cs:__imp_RtlInitUnicodeString
0x14000a28f  nop     dword ptr [rax+rax+00h]
0x14000a294  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a298  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a29f  nop     dword ptr [rax+rax+00h]
0x14000a2a4  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x14000a2ab  mov     cs:pfnWppTraceMessage, rax
0x14000a2b2  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a2b6  call    cs:__imp_RtlInitUnicodeString
0x14000a2bd  nop     dword ptr [rax+rax+00h]
0x14000a2c2  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a2c6  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a2cd  nop     dword ptr [rax+rax+00h]
0x14000a2d2  mov     cs:pfnWppQueryTraceInformation, rax
0x14000a2d9  mov     rax, cs:pfnWppGetVersion
0x14000a2e0  mov     cs:WPPTraceSuite, 2
0x14000a2ea  test    rax, rax
0x14000a2ed  jz      short loc_14000A300
0x14000a2ef  xor     r9d, r9d
0x14000a2f2  lea     rcx, [rbp+arg_0]
0x14000a2f6  xor     r8d, r8d
0x14000a2f9  xor     edx, edx
0x14000a2fb  call    _guard_dispatch_icall
0x14000a300  cmp     [rbp+arg_0], 6
0x14000a304  jb      short loc_14000A371
0x14000a306  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x14000a30d  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a311  call    cs:__imp_RtlInitUnicodeString
0x14000a318  nop     dword ptr [rax+rax+00h]
0x14000a31d  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a321  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a328  nop     dword ptr [rax+rax+00h]
0x14000a32d  mov     cs:pfnEtwRegisterClassicProvider, rax
0x14000a334  test    rax, rax
0x14000a337  jz      short loc_14000A371
0x14000a339  lea     rdx, aEtwunregister; "EtwUnregister"
0x14000a340  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a344  call    cs:__imp_RtlInitUnicodeString
0x14000a34b  nop     dword ptr [rax+rax+00h]
0x14000a350  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a354  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a35b  nop     dword ptr [rax+rax+00h]
0x14000a360  mov     cs:pfnEtwUnregister, rax
0x14000a367  mov     cs:WPPTraceSuite, 4
0x14000a371  add     rsp, 40h
0x14000a375  pop     rbp
0x14000a376  retn
```
