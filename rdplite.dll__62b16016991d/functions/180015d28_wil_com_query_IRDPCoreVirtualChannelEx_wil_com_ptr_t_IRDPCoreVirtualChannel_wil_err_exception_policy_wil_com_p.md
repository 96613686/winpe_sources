# wil::com_query<IRDPCoreVirtualChannelEx,wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &>(wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &)

- ea: `0x180015d28`
- end: `0x180015d77`
- name: `??$com_query@UIRDPCoreVirtualChannelEx@@AEAV?$com_ptr_t@UIRDPCoreVirtualChannel@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIRDPCoreVirtualChannelEx@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UIRDPCoreVirtualChannel@@Uerr_exception_policy@wil@@@0@@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016738`

## callees

- `0x18000d590`
- `0x180015d28`
- `0x18002a010`

## string_xrefs

- `0x180015d59`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<IRDPCoreVirtualChannelEx,wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_5c45d603_ff63_46ec_885f_7f9c366ae117, a1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a1;
}

```

## disassembly

```asm
0x180015d28  push    rbx
0x180015d2a  sub     rsp, 30h
0x180015d2e  mov     rbx, rcx
0x180015d31  mov     rcx, [rdx]
0x180015d34  mov     r8, rbx
0x180015d37  lea     rdx, _GUID_5c45d603_ff63_46ec_885f_7f9c366ae117
0x180015d3e  mov     qword ptr [rbx], 0
0x180015d45  mov     rax, [rcx]
0x180015d48  mov     rax, [rax]
0x180015d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d50  test    eax, eax
0x180015d52  jns     short loc_180015D6E
0x180015d54  mov     rcx, [rsp+38h]; this
0x180015d59  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015d60  mov     r9d, eax; char *
0x180015d63  mov     edx, 1CBEh; void *
0x180015d68  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015d6e  mov     rax, rbx
0x180015d71  add     rsp, 30h
0x180015d75  pop     rbx
0x180015d76  retn
```
