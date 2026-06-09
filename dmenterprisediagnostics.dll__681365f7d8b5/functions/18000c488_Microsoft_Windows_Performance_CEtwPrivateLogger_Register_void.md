# Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)

- ea: `0x18000c488`
- end: `0x18000c52b`
- name: `?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ca5c`

## callees

- `0x180009e98`
- `0x18000c488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c49e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c4b5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c49e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c4b5`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000c507`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000c507`

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
             Microsoft::Windows::Performance::CEtwPrivateLogger::ControlCallback,
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
0x18000c488  mov     [rsp+arg_0], rbx
0x18000c48d  mov     [rsp+arg_8], rsi
0x18000c492  push    rdi
0x18000c493  sub     rsp, 40h
0x18000c497  mov     rbx, rcx
0x18000c49a  add     rcx, 20h ; ' '; pguid
0x18000c49e  call    cs:__imp_CoCreateGuid
0x18000c4a5  nop     dword ptr [rax+rax+00h]
0x18000c4aa  test    eax, eax
0x18000c4ac  js      short loc_18000C51A
0x18000c4ae  lea     rdi, [rbx+30h]
0x18000c4b2  mov     rcx, rdi; pguid
0x18000c4b5  call    cs:__imp_CoCreateGuid
0x18000c4bc  nop     dword ptr [rax+rax+00h]
0x18000c4c1  test    eax, eax
0x18000c4c3  js      short loc_18000C51A
0x18000c4c5  lea     rcx, [rbx+10h]
0x18000c4c9  mov     qword ptr [rbx+18h], 0
0x18000c4d1  lea     rax, [rbx+40h]
0x18000c4d5  mov     [rcx], rdi
0x18000c4d8  mov     [rsp+48h+RegistrationHandle], rax; RegistrationHandle
0x18000c4dd  lea     r8, [rbx+20h]; ControlGuid
0x18000c4e1  mov     [rsp+48h+MofResourceName], 0; MofResourceName
0x18000c4ea  mov     r9d, 1; GuidCount
0x18000c4f0  mov     [rsp+48h+MofImagePath], 0; MofImagePath
0x18000c4f9  xor     edx, edx; RequestContext
0x18000c4fb  mov     [rsp+48h+TraceGuidReg], rcx; TraceGuidReg
0x18000c500  lea     rcx, ?ControlCallback@CEtwPrivateLogger@Performance@Windows@Microsoft@@CAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; RequestAddress
0x18000c507  call    cs:__imp_RegisterTraceGuidsW
0x18000c50e  nop     dword ptr [rax+rax+00h]
0x18000c513  mov     ecx, eax; unsigned int
0x18000c515  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000c51a  mov     rbx, [rsp+48h+arg_0]
0x18000c51f  mov     rsi, [rsp+48h+arg_8]
0x18000c524  add     rsp, 40h
0x18000c528  pop     rdi
0x18000c529  retn
```
