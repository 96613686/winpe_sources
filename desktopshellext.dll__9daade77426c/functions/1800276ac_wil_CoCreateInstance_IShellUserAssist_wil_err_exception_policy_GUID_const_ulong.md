# wil::CoCreateInstance<IShellUserAssist,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x1800276ac`
- end: `0x180027715`
- name: `??$CoCreateInstance@UIShellUserAssist@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIShellUserAssist@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052614`

## callees

- `0x18002661c`
- `0x1800276ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800276e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800276e7`

## string_xrefs

- `0x1800276f9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<IShellUserAssist,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_dd313e04_feff_11d1_8ecd_0000f87a470c,
               0,
               1u,
               &GUID_49b36d57_5fd2_45a7_981b_06028d577a47,
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
0x1800276ac  mov     rax, rsp
0x1800276af  mov     [rax+8], rcx
0x1800276b3  push    rbx
0x1800276b4  sub     rsp, 40h
0x1800276b8  mov     rbx, rcx
0x1800276bb  mov     dword ptr [rax-18h], 0
0x1800276c2  mov     r8d, 1; dwClsContext
0x1800276c8  mov     [rax-18h], r8d
0x1800276cc  mov     qword ptr [rcx], 0
0x1800276d3  mov     [rax-28h], rcx
0x1800276d7  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x1800276de  xor     edx, edx; pUnkOuter
0x1800276e0  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c; rclsid
0x1800276e7  call    cs:__imp_CoCreateInstance
0x1800276ed  test    eax, eax
0x1800276ef  jns     short loc_18002770B
0x1800276f1  mov     rcx, [rsp+48h]; this
0x1800276f6  mov     r9d, eax; char *
0x1800276f9  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027700  mov     edx, 1CBEh; void *
0x180027705  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002770b  mov     rax, rbx
0x18002770e  add     rsp, 40h
0x180027712  pop     rbx
0x180027713  retn
```
