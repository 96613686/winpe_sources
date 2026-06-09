# wil::com_query<ID3D11Fence,IUnknown * &>(IUnknown * &)

- ea: `0x18001fbb8`
- end: `0x18001fc07`
- name: `??$com_query@UID3D11Fence@@AEAPEAUIUnknown@@@wil@@YA?AV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@0@AEAPEAUIUnknown@@@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ff30`

## callees

- `0x18000d590`
- `0x18001fbb8`
- `0x18002a010`

## string_xrefs

- `0x18001fbe9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<ID3D11Fence,IUnknown * &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80, a1);
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
0x18001fbb8  push    rbx
0x18001fbba  sub     rsp, 30h
0x18001fbbe  mov     rbx, rcx
0x18001fbc1  mov     rcx, [rdx]
0x18001fbc4  mov     r8, rbx
0x18001fbc7  lea     rdx, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x18001fbce  mov     qword ptr [rbx], 0
0x18001fbd5  mov     rax, [rcx]
0x18001fbd8  mov     rax, [rax]
0x18001fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbe0  test    eax, eax
0x18001fbe2  jns     short loc_18001FBFE
0x18001fbe4  mov     rcx, [rsp+38h]; this
0x18001fbe9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fbf0  mov     r9d, eax; char *
0x18001fbf3  mov     edx, 1CBEh; void *
0x18001fbf8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fbfe  mov     rax, rbx
0x18001fc01  add     rsp, 30h
0x18001fc05  pop     rbx
0x18001fc06  retn
```
