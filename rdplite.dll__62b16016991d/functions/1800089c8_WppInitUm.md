# WppInitUm

- ea: `0x1800089c8`
- end: `0x180008a8d`
- name: `WppInitUm`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800083d0`

## callees

- `0x1800089c8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008a38`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008a38`
- `ntdll!RtlInitUnicodeString` at `0x180008a5a`
- `ntdll!RtlInitUnicodeString` at `0x180008a5a`
- `WppRecorderUM!WppAutoLogStart` at `0x180008a6e`
- `WppRecorderUM!WppAutoLogStart` at `0x180008a6e`

## string_xrefs

- `0x180008a49`: `RdpLite.dll`

## pseudocode

```c
__int64 *WppInitUm()
{
  ULONG64 *v0; // rbx
  const GUID **v1; // rdi
  const GUID *v2; // r8
  __int64 *result; // rax
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-28h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v0 = (ULONG64 *)WPP_GLOBAL_Control;
  v1 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  TraceGuidReg = 0;
  while ( v0 )
  {
    v2 = *v1;
    TraceGuidReg.Guid = v2;
    ++v1;
    TraceGuidReg.RegHandle = 0;
    v0[4] = (ULONG64)v2;
    RegisterTraceGuidsW(WppControlCallback, v0, v2, 1u, &TraceGuidReg, 0, 0, v0 + 1);
    v0 = (ULONG64 *)*v0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RdpLite.dll");
  WppAutoLogStart(WPP_GLOBAL_Control, 0, &DestinationString);
  result = &WPP_MAIN_CB;
  WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  return result;
}

```

## disassembly

```asm
0x1800089c8  mov     [rsp+arg_0], rbx
0x1800089cd  push    rdi
0x1800089ce  sub     rsp, 60h
0x1800089d2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800089d9  lea     rdi, WPP_REGISTRATION_GUIDS
0x1800089e0  xorps   xmm0, xmm0
0x1800089e3  movups  xmmword ptr [rsp+68h+var_28.Guid], xmm0
0x1800089e8  jmp     short loc_180008A41
0x1800089ea  mov     r8, [rdi]; ControlGuid
0x1800089ed  lea     rax, [rbx+8]
0x1800089f1  mov     [rsp+68h+RegistrationHandle], rax; RegistrationHandle
0x1800089f6  lea     rcx, WppControlCallback; RequestAddress
0x1800089fd  mov     [rsp+68h+MofResourceName], 0; MofResourceName
0x180008a06  lea     rax, [rsp+68h+var_28]
0x180008a0b  mov     [rsp+68h+var_28.Guid], r8
0x180008a10  lea     rdi, [rdi+8]
0x180008a14  mov     [rsp+68h+var_28.RegHandle], 0
0x180008a1d  mov     r9d, 1; GuidCount
0x180008a23  mov     [rsp+68h+MofImagePath], 0; MofImagePath
0x180008a2c  mov     rdx, rbx; RequestContext
0x180008a2f  mov     [rsp+68h+TraceGuidReg], rax; TraceGuidReg
0x180008a34  mov     [rbx+20h], r8
0x180008a38  call    cs:__imp_RegisterTraceGuidsW
0x180008a3e  mov     rbx, [rbx]
0x180008a41  test    rbx, rbx
0x180008a44  jnz     short loc_1800089EA
0x180008a46  xorps   xmm0, xmm0
0x180008a49  lea     rdx, SourceString; "RdpLite.dll"
0x180008a50  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180008a55  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180008a5a  call    cs:__imp_RtlInitUnicodeString
0x180008a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a67  lea     r8, [rsp+68h+DestinationString]
0x180008a6c  xor     edx, edx
0x180008a6e  call    cs:__imp_WppAutoLogStart
0x180008a74  mov     rbx, [rsp+68h+arg_0]
0x180008a79  lea     rax, WPP_MAIN_CB
0x180008a80  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x180008a87  add     rsp, 60h
0x180008a8b  pop     rdi
0x180008a8c  retn
```
