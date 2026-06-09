# wil::CoCreateInstance<IUPnPDeviceFinder,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x1800d2f8c`
- end: `0x1800d301c`
- name: `??$CoCreateInstance@UIUPnPDeviceFinder@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUPnPDeviceFinder@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db608`

## callees

- `0x180015738`
- `0x1800d2f8c`
- `0x18032f050`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800d2fe2`
- `ole32!CoCreateInstance` at `0x1800d2fe2`

## string_xrefs

- `0x1800d300a`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::CoCreateInstance<IUPnPDeviceFinder,wil::err_exception_policy>(
        _QWORD *a1,
        const IID *a2,
        DWORD a3)
{
  LPVOID *v6; // rax
  HRESULT Instance; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  v6 = (LPVOID *)(*(__int64 (**)(void))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)();
  Instance = CoCreateInstance(a2, 0, a3, &GUID_adda3d55_6f72_4319_bff9_18600a539b10, v6);
  _mm_lfence();
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C89,
      (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      ppv);
  return a1;
}

```

## disassembly

```asm
0x1800d2f8c  mov     [rsp+arg_8], rbx
0x1800d2f91  mov     [rsp+arg_10], rsi
0x1800d2f96  mov     [rsp+arg_0], rcx
0x1800d2f9b  push    rdi
0x1800d2f9c  mov     eax, 40h
0x1800d2fa1  call    _alloca_probe
0x1800d2fa6  sub     rsp, rax
0x1800d2fa9  mov     ebx, r8d
0x1800d2fac  mov     rdi, rdx
0x1800d2faf  mov     rsi, rcx
0x1800d2fb2  mov     [rsp+48h+var_18], 0
0x1800d2fba  mov     [rsp+48h+var_18], 1
0x1800d2fc2  mov     qword ptr [rcx], 0
0x1800d2fc9  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1800d2fce  mov     qword ptr [rsp+48h+ppv], rax; int
0x1800d2fd3  lea     r9, _GUID_adda3d55_6f72_4319_bff9_18600a539b10; riid
0x1800d2fda  mov     r8d, ebx; dwClsContext
0x1800d2fdd  xor     edx, edx; pUnkOuter
0x1800d2fdf  mov     rcx, rdi; rclsid
0x1800d2fe2  call    cs:__imp_CoCreateInstance
0x1800d2fe8  lfence
0x1800d2feb  test    eax, eax
0x1800d2fed  js      short loc_1800D3002
0x1800d2fef  mov     rax, rsi
0x1800d2ff2  mov     rbx, [rsp+48h+arg_8]
0x1800d2ff7  mov     rsi, [rsp+48h+arg_10]
0x1800d2ffc  add     rsp, 40h
0x1800d3000  pop     rdi
0x1800d3001  retn
0x1800d3002  mov     rcx, [rsp+48h]; this
0x1800d3007  mov     r9d, eax; char *
0x1800d300a  lea     r8, aCW1SExternalsV_12; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x1800d3011  mov     edx, 1C89h; void *
0x1800d3016  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
