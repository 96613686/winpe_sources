# Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)

- ea: `0x18000bf04`
- end: `0x18000bf94`
- name: `?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c484`

## callees

- `0x1800099b8`
- `0x18000bf04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bf1a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bf2b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bf1a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000bf2b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000bf77`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000bf77`

## pseudocode

```c
HRESULT __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::Register(
        Microsoft::Windows::Performance::CEtwPrivateLogger *this)
{
  HRESULT result; // eax
  ULONG v3; // eax

  result = CoCreateGuid((GUID *)this + 2);
  if ( result >= 0 )
  {
    result = CoCreateGuid((GUID *)this + 3);
    if ( result >= 0 )
    {
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 2) = (char *)this + 48;
      v3 = RegisterTraceGuidsW(
             _scrt_stub_for_is_c_termination_complete,
             0,
             (LPCGUID)this + 2,
             1u,
             (PTRACE_GUID_REGISTRATION)this + 1,
             0,
             0,
             (PTRACEHANDLE)this + 8);
      return ATL::AtlHresultFromWin32(v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bf04  mov     [rsp+arg_0], rbx
0x18000bf09  mov     [rsp+arg_8], rsi
0x18000bf0e  push    rdi
0x18000bf0f  sub     rsp, 40h
0x18000bf13  mov     rbx, rcx
0x18000bf16  add     rcx, 20h ; ' '; pguid
0x18000bf1a  call    cs:__imp_CoCreateGuid
0x18000bf20  test    eax, eax
0x18000bf22  js      short loc_18000BF84
0x18000bf24  lea     rdi, [rbx+30h]
0x18000bf28  mov     rcx, rdi; pguid
0x18000bf2b  call    cs:__imp_CoCreateGuid
0x18000bf31  test    eax, eax
0x18000bf33  js      short loc_18000BF84
0x18000bf35  lea     rcx, [rbx+10h]
0x18000bf39  mov     qword ptr [rbx+18h], 0
0x18000bf41  lea     rax, [rbx+40h]
0x18000bf45  mov     [rcx], rdi
0x18000bf48  mov     [rsp+48h+RegistrationHandle], rax; RegistrationHandle
0x18000bf4d  lea     r8, [rbx+20h]; ControlGuid
0x18000bf51  mov     [rsp+48h+MofResourceName], 0; MofResourceName
0x18000bf5a  mov     r9d, 1; GuidCount
0x18000bf60  mov     [rsp+48h+MofImagePath], 0; MofImagePath
0x18000bf69  xor     edx, edx; RequestContext
0x18000bf6b  mov     [rsp+48h+TraceGuidReg], rcx; TraceGuidReg
0x18000bf70  lea     rcx, __scrt_stub_for_is_c_termination_complete; RequestAddress
0x18000bf77  call    cs:__imp_RegisterTraceGuidsW
0x18000bf7d  mov     ecx, eax; unsigned int
0x18000bf7f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bf84  mov     rbx, [rsp+48h+arg_0]
0x18000bf89  mov     rsi, [rsp+48h+arg_8]
0x18000bf8e  add     rsp, 40h
0x18000bf92  pop     rdi
0x18000bf93  retn
```
