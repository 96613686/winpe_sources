# Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)

- ea: `0x180020e30`
- end: `0x180020e9a`
- name: `?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ`
- size: `106`
- prototype: `struct IDXGIDevice2 *(Rdp::Utils::Graphics::CRenderDevice *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021640`
- `0x180021b78`

## callees

- `0x180007b28`
- `0x18000d590`
- `0x180020e30`
- `0x18002a010`

## string_xrefs

- `0x180020e69`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDXGIDevice2 *__fastcall Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(
        Rdp::Utils::Graphics::CRenderDevice *this)
{
  __int64 v1; // rbx
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v7 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = (**v2)(v2, &GUID_05008617_fbfd_4051_a790_144884b4f6a9, &v7);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v3,
        v5);
    v1 = v7;
  }
  else
  {
    v7 = 0;
  }
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v7);
  return (struct IDXGIDevice2 *)v1;
}

```

## disassembly

```asm
0x180020e30  push    rbx; int
0x180020e32  sub     rsp, 20h
0x180020e36  xor     ebx, ebx
0x180020e38  mov     [rsp+28h+arg_0], rbx
0x180020e3d  mov     rcx, [rcx+10h]
0x180020e41  test    rcx, rcx
0x180020e44  jz      short loc_180020E82
0x180020e46  mov     rax, [rcx]
0x180020e49  lea     r8, [rsp+28h+arg_0]
0x180020e4e  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x180020e55  mov     rax, [rax]
0x180020e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e5d  mov     rcx, [rsp+28h]; this
0x180020e62  test    eax, eax
0x180020e64  jns     short loc_180020E7B
0x180020e66  mov     r9d, eax; char *
0x180020e69  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020e70  mov     edx, 1CBEh; void *
0x180020e75  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020e7b  mov     rbx, [rsp+28h+arg_0]
0x180020e80  jmp     short loc_180020E87
0x180020e82  mov     [rsp+28h+arg_0], rbx
0x180020e87  lea     rcx, [rsp+28h+arg_0]
0x180020e8c  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180020e91  mov     rax, rbx
0x180020e94  add     rsp, 20h
0x180020e98  pop     rbx
0x180020e99  retn
```
