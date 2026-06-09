# wil::com_query<ID3D11Texture2D,IUnknown * &>(IUnknown * &)

- ea: `0x18001fc10`
- end: `0x18001fc5f`
- name: `??$com_query@UID3D11Texture2D@@AEAPEAUIUnknown@@@wil@@YA?AV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@0@AEAPEAUIUnknown@@@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020004`

## callees

- `0x18000d590`
- `0x18001fc10`
- `0x18002a010`

## string_xrefs

- `0x18001fc41`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<ID3D11Texture2D,IUnknown * &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, a1);
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
0x18001fc10  push    rbx
0x18001fc12  sub     rsp, 30h
0x18001fc16  mov     rbx, rcx
0x18001fc19  mov     rcx, [rdx]
0x18001fc1c  mov     r8, rbx
0x18001fc1f  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18001fc26  mov     qword ptr [rbx], 0
0x18001fc2d  mov     rax, [rcx]
0x18001fc30  mov     rax, [rax]
0x18001fc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc38  test    eax, eax
0x18001fc3a  jns     short loc_18001FC56
0x18001fc3c  mov     rcx, [rsp+38h]; this
0x18001fc41  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fc48  mov     r9d, eax; char *
0x18001fc4b  mov     edx, 1CBEh; void *
0x18001fc50  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fc56  mov     rax, rbx
0x18001fc59  add     rsp, 30h
0x18001fc5d  pop     rbx
0x18001fc5e  retn
```
