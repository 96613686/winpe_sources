# BDGetFontPaths

- ea: `0x14008066c`
- end: `0x140080730`
- name: `BDGetFontPaths`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x14007da08`

## callees

- `0x14007ee98`
- `0x14008066c`
- `0x140080fcc`

## pseudocode

```c
__int64 __fastcall BDGetFontPaths(_WORD *a1, int a2)
{
  unsigned int v2; // edi
  __int64 v3; // rsi
  _WORD *v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rdx
  __int64 v7; // rbx
  char v8; // cl
  void *v9; // rcx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v2 = -223;
  v11 = 0;
  v3 = (__int64)(a1 + 12);
  a1[12] = 0;
  v4 = a1 + 273;
  a1[273] = 0;
  v5 = (__int64)(a1 + 534);
  a1[534] = 0;
  if ( (unsigned int)FindFont((int)a1 + 1590, a2, (unsigned __int16)a1[859], (unsigned int)&v11, 0) == 1 )
  {
    v2 = -2001;
    v6 = (__int64)v4;
    v7 = v11;
    if ( GetFontFilePath(*(void **)(v11 + 136), v6) )
    {
      v8 = *(_BYTE *)(v7 + 1109) & 8;
      if ( (*(_BYTE *)(v7 + 1109) & 0x10) != 0 )
      {
        if ( !v8 )
          GetFontFilePath(*(void **)(v7 + 112), v5);
        v9 = *(void **)(v7 + 160);
        if ( !v9 )
          return 0;
      }
      else
      {
        if ( v8 )
          return 0;
        v9 = *(void **)(v7 + 112);
      }
      GetFontFilePath(v9, v3);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14008066c  push    rbx
0x14008066e  push    rsi
0x14008066f  push    rdi
0x140080670  push    r14
0x140080672  sub     rsp, 38h
0x140080676  mov     r8, rcx
0x140080679  mov     edi, 0FFFFFF21h
0x14008067e  mov     [rsp+58h+arg_8], 0
0x140080687  lea     rsi, [rcx+18h]
0x14008068b  xor     eax, eax
0x14008068d  mov     [rsi], ax
0x140080690  lea     rbx, [rcx+222h]
0x140080697  mov     [rbx], ax
0x14008069a  lea     r14, [rcx+42Ch]
0x1400806a1  mov     [r14], ax
0x1400806a5  add     rcx, 636h
0x1400806ac  mov     [rsp+58h+var_38], al
0x1400806b0  lea     r9, [rsp+58h+arg_8]
0x1400806b5  movzx   r8d, word ptr [r8+6B6h]
0x1400806bd  call    FindFont
0x1400806c2  cmp     eax, 1
0x1400806c5  jnz     short loc_140080724
0x1400806c7  mov     edi, 0FFFFF82Fh
0x1400806cc  mov     rdx, rbx
0x1400806cf  mov     rbx, [rsp+58h+arg_8]
0x1400806d4  mov     rcx, [rbx+88h]
0x1400806db  call    GetFontFilePath
0x1400806e0  cmp     eax, 1
0x1400806e3  jnz     short loc_140080724
0x1400806e5  mov     al, [rbx+455h]
0x1400806eb  mov     cl, al
0x1400806ed  and     cl, 8
0x1400806f0  test    al, 10h
0x1400806f2  jz      short loc_140080712
0x1400806f4  test    cl, cl
0x1400806f6  jnz     short loc_140080704
0x1400806f8  mov     rdx, r14
0x1400806fb  mov     rcx, [rbx+70h]
0x1400806ff  call    GetFontFilePath
0x140080704  mov     rcx, [rbx+0A0h]
0x14008070b  test    rcx, rcx
0x14008070e  jz      short loc_140080722
0x140080710  jmp     short loc_14008071A
0x140080712  test    cl, cl
0x140080714  jnz     short loc_140080722
0x140080716  mov     rcx, [rbx+70h]
0x14008071a  mov     rdx, rsi
0x14008071d  call    GetFontFilePath
0x140080722  xor     edi, edi
0x140080724  mov     eax, edi
0x140080726  add     rsp, 38h
0x14008072a  pop     r14
0x14008072c  pop     rdi
0x14008072d  pop     rsi
0x14008072e  pop     rbx
0x14008072f  retn
0x14009780f  push    rbp
0x140097811  sub     rsp, 30h
0x140097815  mov     rbp, rdx
0x140097818  add     rsp, 30h
0x14009781c  pop     rbp
0x14009781d  retn
```
