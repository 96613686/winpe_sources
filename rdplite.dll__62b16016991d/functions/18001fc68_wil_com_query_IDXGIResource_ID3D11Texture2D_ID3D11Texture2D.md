# wil::com_query<IDXGIResource,ID3D11Texture2D * &>(ID3D11Texture2D * &)

- ea: `0x18001fc68`
- end: `0x18001fcb7`
- name: `??$com_query@UIDXGIResource@@AEAPEAUID3D11Texture2D@@@wil@@YA?AV?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@0@AEAPEAUID3D11Texture2D@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fd70`
- `0x1800230a8`

## callees

- `0x18000d590`
- `0x18001fc68`
- `0x18002a010`

## string_xrefs

- `0x18001fc99`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_query<IDXGIResource,ID3D11Texture2D * &>(
        _QWORD *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *))
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  v4 = (**v3)(v3, &GUID_035f3ab4_482e_4e50_b41f_8a7f8bd8960b, a1);
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
0x18001fc68  push    rbx
0x18001fc6a  sub     rsp, 30h
0x18001fc6e  mov     rbx, rcx
0x18001fc71  mov     rcx, [rdx]
0x18001fc74  mov     r8, rbx
0x18001fc77  lea     rdx, _GUID_035f3ab4_482e_4e50_b41f_8a7f8bd8960b
0x18001fc7e  mov     qword ptr [rbx], 0
0x18001fc85  mov     rax, [rcx]
0x18001fc88  mov     rax, [rax]
0x18001fc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc90  test    eax, eax
0x18001fc92  jns     short loc_18001FCAE
0x18001fc94  mov     rcx, [rsp+38h]; this
0x18001fc99  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fca0  mov     r9d, eax; char *
0x18001fca3  mov     edx, 1CBEh; void *
0x18001fca8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fcae  mov     rax, rbx
0x18001fcb1  add     rsp, 30h
0x18001fcb5  pop     rbx
0x18001fcb6  retn
```
