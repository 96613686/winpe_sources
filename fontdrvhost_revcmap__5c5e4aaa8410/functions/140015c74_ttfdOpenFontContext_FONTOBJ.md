# ttfdOpenFontContext(_FONTOBJ *)

- ea: `0x140015c74`
- end: `0x140015cd5`
- name: `?ttfdOpenFontContext@@YAPEAU_TT_FONTCONTEXT@@PEAU_FONTOBJ@@@Z`
- size: `97`
- prototype: `struct _TT_FONTCONTEXT *__fastcall(struct _FONTOBJ *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140014c60`
- `0x140015890`
- `0x1400280c4`
- `0x140091290`

## callees

- `0x14000bd04`
- `0x140015c74`
- `0x140015cdc`
- `0x140091178`

## pseudocode

```c
struct _TT_FONTCONTEXT *__fastcall ttfdOpenFontContext(struct _FONTOBJ *a1)
{
  return ttfdOpenFontContextInternal(a1);
}

```

## disassembly

```asm
0x140015c74  mov     [rsp+arg_8], rbx
0x140015c79  push    rdi
0x140015c7a  sub     rsp, 30h
0x140015c7e  mov     rax, [rcx+18h]
0x140015c82  mov     [rsp+38h+arg_0], rax
0x140015c87  call    ?ttfdOpenFontContextInternal@@YAPEAU_TT_FONTCONTEXT@@PEAU_FONTOBJ@@@Z; ttfdOpenFontContextInternal(_FONTOBJ *)
0x140015c8c  mov     [rsp+38h+var_18], rax
0x140015c91  jmp     short loc_140015CCA
0x140015c93  mov     edi, eax
0x140015c95  mov     edx, eax; unsigned int
0x140015c97  mov     rbx, [rsp+38h+arg_0]
0x140015c9c  mov     rcx, rbx; struct _TTC_FONTFILE *
0x140015c9f  call    ?vMarkFontGone@@YAXPEAU_TTC_FONTFILE@@K@Z; vMarkFontGone(_TTC_FONTFILE *,ulong)
0x140015ca4  test    rbx, rbx
0x140015ca7  jz      short loc_140015CC3
0x140015ca9  cmp     dword ptr [rbx], 0
0x140015cac  jnz     short loc_140015CC3
0x140015cae  cmp     edi, 0C0000006h
0x140015cb4  jnz     short loc_140015CC3
0x140015cb6  mov     rcx, [rbx+30h]
0x140015cba  mov     rcx, [rcx+38h]; iFile
0x140015cbe  call    EngUnmapFontFileFD
0x140015cc3  xor     eax, eax
0x140015cc5  mov     [rsp+38h+var_18], rax
0x140015cca  mov     rbx, [rsp+38h+arg_8]
0x140015ccf  add     rsp, 30h
0x140015cd3  pop     rdi
0x140015cd4  retn
```
