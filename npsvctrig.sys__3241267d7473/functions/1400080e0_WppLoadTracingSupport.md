# WppLoadTracingSupport

- ea: `0x1400080e0`
- end: `0x140008228`
- name: `WppLoadTracingSupport`
- size: `328`
- prototype: `PVOID()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b080`

## callees

- `0x140001b80`
- `0x1400080e0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008111`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008141`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008171`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081d0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008205`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008111`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008141`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008171`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400081d0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140008205`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008100`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008130`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008160`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008100`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008130`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008160`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400081f4`

## pseudocode

```c
PVOID WppLoadTracingSupport()
{
  PVOID result; // rax
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v2; // [rsp+50h] [rbp+8h] BYREF

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
0x1400080e0  sub     rsp, 48h
0x1400080e4  xorps   xmm0, xmm0
0x1400080e7  mov     [rsp+48h+arg_0], 0
0x1400080ef  lea     rdx, SourceString; "PsGetVersion"
0x1400080f6  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400080fb  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x140008100  call    cs:__imp_RtlInitUnicodeString
0x140008107  nop     dword ptr [rax+rax+00h]
0x14000810c  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x140008111  call    cs:__imp_MmGetSystemRoutineAddress
0x140008118  nop     dword ptr [rax+rax+00h]
0x14000811d  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x140008124  mov     cs:pfnWppGetVersion, rax
0x14000812b  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140008130  call    cs:__imp_RtlInitUnicodeString
0x140008137  nop     dword ptr [rax+rax+00h]
0x14000813c  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x140008141  call    cs:__imp_MmGetSystemRoutineAddress
0x140008148  nop     dword ptr [rax+rax+00h]
0x14000814d  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x140008154  mov     cs:pfnWppTraceMessage, rax
0x14000815b  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140008160  call    cs:__imp_RtlInitUnicodeString
0x140008167  nop     dword ptr [rax+rax+00h]
0x14000816c  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x140008171  call    cs:__imp_MmGetSystemRoutineAddress
0x140008178  nop     dword ptr [rax+rax+00h]
0x14000817d  mov     cs:pfnWppQueryTraceInformation, rax
0x140008184  mov     rax, cs:pfnWppGetVersion
0x14000818b  mov     cs:WPPTraceSuite, 2
0x140008195  test    rax, rax
0x140008198  jz      short loc_1400081AC
0x14000819a  xor     r9d, r9d
0x14000819d  lea     rcx, [rsp+48h+arg_0]
0x1400081a2  xor     r8d, r8d
0x1400081a5  xor     edx, edx
0x1400081a7  call    _guard_dispatch_icall
0x1400081ac  cmp     [rsp+48h+arg_0], 6
0x1400081b1  jb      short loc_140008222
0x1400081b3  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x1400081ba  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400081bf  call    cs:__imp_RtlInitUnicodeString
0x1400081c6  nop     dword ptr [rax+rax+00h]
0x1400081cb  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x1400081d0  call    cs:__imp_MmGetSystemRoutineAddress
0x1400081d7  nop     dword ptr [rax+rax+00h]
0x1400081dc  mov     cs:pfnEtwRegisterClassicProvider, rax
0x1400081e3  test    rax, rax
0x1400081e6  jz      short loc_140008222
0x1400081e8  lea     rdx, aEtwunregister; "EtwUnregister"
0x1400081ef  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400081f4  call    cs:__imp_RtlInitUnicodeString
0x1400081fb  nop     dword ptr [rax+rax+00h]
0x140008200  lea     rcx, [rsp+48h+DestinationString]; SystemRoutineName
0x140008205  call    cs:__imp_MmGetSystemRoutineAddress
0x14000820c  nop     dword ptr [rax+rax+00h]
0x140008211  mov     cs:pfnEtwUnregister, rax
0x140008218  mov     cs:WPPTraceSuite, 4
0x140008222  add     rsp, 48h
0x140008226  retn
```
