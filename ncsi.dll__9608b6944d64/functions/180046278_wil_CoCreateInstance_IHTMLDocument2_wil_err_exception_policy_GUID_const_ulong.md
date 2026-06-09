# wil::CoCreateInstance<IHTMLDocument2,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180046278`
- end: `0x1800462e1`
- name: `??$CoCreateInstance@UIHTMLDocument2@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIHTMLDocument2@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800453bc`

## callees

- `0x180046278`
- `0x18004f5f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800462b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800462b3`

## string_xrefs

- `0x1800462c5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IHTMLDocument2,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_25336920_03f9_11cf_8fd0_00aa00686f13,
               0,
               1u,
               &GUID_332c4425_26cb_11d0_b483_00c04fd90119,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
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
0x180046278  mov     rax, rsp
0x18004627b  mov     [rax+8], rcx
0x18004627f  push    rbx
0x180046280  sub     rsp, 40h
0x180046284  mov     rbx, rcx
0x180046287  mov     dword ptr [rax-18h], 0
0x18004628e  mov     r8d, 1; dwClsContext
0x180046294  mov     [rax-18h], r8d
0x180046298  mov     qword ptr [rcx], 0
0x18004629f  mov     [rax-28h], rcx
0x1800462a3  lea     r9, _GUID_332c4425_26cb_11d0_b483_00c04fd90119; riid
0x1800462aa  xor     edx, edx; pUnkOuter
0x1800462ac  lea     rcx, _GUID_25336920_03f9_11cf_8fd0_00aa00686f13; rclsid
0x1800462b3  call    cs:__imp_CoCreateInstance
0x1800462b9  test    eax, eax
0x1800462bb  jns     short loc_1800462D7
0x1800462bd  mov     rcx, [rsp+48h]; this
0x1800462c2  mov     r9d, eax; char *
0x1800462c5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800462cc  mov     edx, 1CBEh; void *
0x1800462d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800462d7  mov     rax, rbx
0x1800462da  add     rsp, 40h
0x1800462de  pop     rbx
0x1800462df  retn
```
