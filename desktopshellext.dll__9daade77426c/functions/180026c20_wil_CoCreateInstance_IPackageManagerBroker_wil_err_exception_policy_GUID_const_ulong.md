# wil::CoCreateInstance<IPackageManagerBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180026c20`
- end: `0x180026c8a`
- name: `??$CoCreateInstance@UIPackageManagerBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052128`

## callees

- `0x18002661c`
- `0x180026c20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026c5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026c5c`

## string_xrefs

- `0x180026c6e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<IPackageManagerBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_38578775_65cf_4827_b800_9e68236c5af2,
               0,
               4u,
               &GUID_b8c9f2a1_4e3d_4f5b_9c7a_1d2e3f4a5b6c,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x180026c20  mov     rax, rsp
0x180026c23  mov     [rax+8], rcx
0x180026c27  push    rbx
0x180026c28  sub     rsp, 40h
0x180026c2c  mov     rbx, rcx
0x180026c2f  mov     dword ptr [rax-18h], 0
0x180026c36  mov     dword ptr [rax-18h], 1
0x180026c3d  mov     qword ptr [rcx], 0
0x180026c44  mov     [rax-28h], rcx
0x180026c48  lea     r9, _GUID_b8c9f2a1_4e3d_4f5b_9c7a_1d2e3f4a5b6c; riid
0x180026c4f  xor     edx, edx; pUnkOuter
0x180026c51  lea     r8d, [rdx+4]; dwClsContext
0x180026c55  lea     rcx, _GUID_38578775_65cf_4827_b800_9e68236c5af2; rclsid
0x180026c5c  call    cs:__imp_CoCreateInstance
0x180026c62  test    eax, eax
0x180026c64  jns     short loc_180026C80
0x180026c66  mov     rcx, [rsp+48h]; this
0x180026c6b  mov     r9d, eax; char *
0x180026c6e  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026c75  mov     edx, 1CBEh; void *
0x180026c7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026c80  mov     rax, rbx
0x180026c83  add     rsp, 40h
0x180026c87  pop     rbx
0x180026c88  retn
```
