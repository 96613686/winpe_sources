# Marshal::Details::WriteArrayXml(Marshal::XmlWriter &,ushort const *,bool,void const *,unsigned __int64,Marshal::MarshalContext const &,Marshal::Details::BaseTypeData const *,Marshal::Details::XmlTypeData const *,unsigned __int64)

- ea: `0x1800210f4`
- end: `0x180021187`
- name: `?WriteArrayXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBG_NPEBX_KAEBVMarshalContext@2@PEBUBaseTypeData@12@PEBUXmlTypeData@12@4@Z`
- size: `147`
- prototype: `void __fastcall(Marshal::Details *__hidden this, struct Marshal::XmlWriter *, const unsigned __int16 *, bool, const void *, unsigned __int64, const struct Marshal::MarshalContext *, const struct Marshal::Details::BaseTypeData *, const struct Marshal::Details::XmlTypeData *, unsigned __int64)`
- caller_count: `17`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a0e0`
- `0x18001a140`
- `0x18001a1a0`
- `0x18001a200`
- `0x18001a260`
- `0x18001a2c0`
- `0x18001a310`
- `0x18001a360`
- `0x18001a3c0`
- `0x18001a420`
- `0x18001a470`
- `0x18001a4d0`
- `0x18001a530`
- `0x18001a590`
- `0x18001a5f0`
- `0x18001a650`
- `0x18001a6a0`

## callees

- `0x18000bdc8`
- `0x1800210f4`
- `0x180034010`

## string_xrefs

- `0x180021175`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
void __fastcall Marshal::Details::WriteArrayXml(
        Marshal::Details *this,
        struct Marshal::XmlWriter *a2,
        const unsigned __int16 *a3,
        const char *a4,
        const void *a5,
        unsigned __int64 a6,
        const struct Marshal::MarshalContext *a7,
        const struct Marshal::Details::BaseTypeData *a8,
        const struct Marshal::Details::XmlTypeData *a9)
{
  unsigned __int64 i; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (_BYTE)a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x701,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      a4);
  for ( i = 0; i < (_QWORD)a9 * (_QWORD)a5; i += (unsigned __int64)a9 )
    (*(void (__fastcall **)(Marshal::Details *, struct Marshal::XmlWriter *, _QWORD, const char *, unsigned __int64))a8)(
      this,
      a2,
      0,
      &a4[i],
      a6);
}

```

## disassembly

```asm
0x1800210f4  push    rbx
0x1800210f6  push    rbp
0x1800210f7  push    rsi
0x1800210f8  push    rdi
0x1800210f9  push    r12
0x1800210fb  push    r14
0x1800210fd  push    r15
0x1800210ff  sub     rsp, 30h
0x180021103  mov     r14, r9
0x180021106  mov     r15, rdx
0x180021109  mov     r12, rcx
0x18002110c  test    r8b, r8b
0x18002110f  jnz     short loc_180021170
0x180021111  mov     rbx, [rsp+68h+arg_20]
0x180021119  xor     edi, edi
0x18002111b  imul    rbx, [rsp+68h+arg_40]
0x180021124  test    rbx, rbx
0x180021127  jz      short loc_180021160
0x180021129  mov     rsi, [rsp+68h+arg_38]
0x180021131  mov     rbp, [rsp+68h+arg_28]
0x180021139  mov     rax, [rsi]
0x18002113c  lea     r9, [rdi+r14]
0x180021140  xor     r8d, r8d
0x180021143  mov     [rsp+68h+var_48], rbp
0x180021148  mov     rdx, r15
0x18002114b  mov     rcx, r12
0x18002114e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021153  add     rdi, [rsp+68h+arg_40]
0x18002115b  cmp     rdi, rbx
0x18002115e  jb      short loc_180021139
0x180021160  add     rsp, 30h
0x180021164  pop     r15
0x180021166  pop     r14
0x180021168  pop     r12
0x18002116a  pop     rdi
0x18002116b  pop     rsi
0x18002116c  pop     rbp
0x18002116d  pop     rbx
0x18002116e  retn
0x180021170  mov     rcx, [rsp+68h]; this
0x180021175  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18002117c  mov     edx, 701h; void *
0x180021181  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
