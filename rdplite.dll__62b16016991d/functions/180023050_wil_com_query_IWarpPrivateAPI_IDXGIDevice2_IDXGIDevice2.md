# wil::com_query<IWarpPrivateAPI,IDXGIDevice2 * &>(IDXGIDevice2 * &)

- ea: `0x180023050`
- end: `0x18002309f`
- name: `??$com_query@VIWarpPrivateAPI@@AEAPEAUIDXGIDevice2@@@wil@@YA?AV?$com_ptr_t@VIWarpPrivateAPI@@Uerr_exception_policy@wil@@@0@AEAPEAUIDXGIDevice2@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800232c8`

## callees

- `0x18000d590`
- `0x180023050`
- `0x18002a010`

## string_xrefs

- `0x180023081`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<IWarpPrivateAPI,IDXGIDevice2 * &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_f13ebcd1_672c_4f8b_a631_9539ca748d71, a1);
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
0x180023050  push    rbx
0x180023052  sub     rsp, 30h
0x180023056  mov     rbx, rcx
0x180023059  mov     rcx, [rdx]
0x18002305c  mov     r8, rbx
0x18002305f  lea     rdx, _GUID_f13ebcd1_672c_4f8b_a631_9539ca748d71
0x180023066  mov     qword ptr [rbx], 0
0x18002306d  mov     rax, [rcx]
0x180023070  mov     rax, [rax]
0x180023073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023078  test    eax, eax
0x18002307a  jns     short loc_180023096
0x18002307c  mov     rcx, [rsp+38h]; this
0x180023081  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023088  mov     r9d, eax; char *
0x18002308b  mov     edx, 1CBEh; void *
0x180023090  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023096  mov     rax, rbx
0x180023099  add     rsp, 30h
0x18002309d  pop     rbx
0x18002309e  retn
```
