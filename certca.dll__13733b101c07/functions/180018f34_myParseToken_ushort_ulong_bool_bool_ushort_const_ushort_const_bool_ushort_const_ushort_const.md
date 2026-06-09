# myParseToken(ushort *,ulong,bool,bool,ushort const *,ushort const * *,bool *,ushort const * *,ushort const * *)

- ea: `0x180018f34`
- end: `0x180019052`
- name: `?myParseToken@@YAJPEAGK_N1PEBGPEAPEBGPEA_N33@Z`
- size: `286`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64, const unsigned __int16 *, const unsigned __int16 **, bool *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018ddc`

## callees

- `0x180008400`
- `0x180008610`
- `0x180013a86`
- `0x180018f34`

## import_xrefs

- `msvcrt!wcscspn` at `0x180018f77`
- `msvcrt!wcscspn` at `0x180018f77`
- `msvcrt!wcschr` at `0x180018fb7`
- `msvcrt!wcschr` at `0x180018fb7`

## pseudocode

```c
__int64 __fastcall myParseToken(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 *a5,
        const unsigned __int16 **a6,
        bool *a7,
        const unsigned __int16 **a8,
        const unsigned __int16 **a9)
{
  unsigned int v9; // esi
  const wchar_t *v11; // rdi
  size_t v12; // rax
  size_t v13; // r14
  size_t v14; // rbx
  const unsigned __int16 *v15; // rdi
  wchar_t i; // dx

  v9 = 1;
  while ( 1 )
  {
    v11 = *a9;
    *a1 = 0;
    while ( *v11 == 32 )
      ++v11;
    v12 = wcscspn(v11, L",");
    v13 = v12;
    if ( v12 >= 0x104 )
    {
      v9 = -2147024785;
      CSPrintErrorLineFile(0x1C5019Au, -2147024785);
      goto LABEL_16;
    }
    v14 = v12;
    memcpy_0(a1, v11, 2 * v12);
    v15 = &v11[v14];
    a1[v14] = 0;
    for ( i = *v15; *v15; i = *v15 )
    {
      if ( !wcschr(L",", i) )
        break;
      ++v15;
    }
    *a9 = v15;
    if ( v13 )
      break;
LABEL_12:
    if ( !*v15 )
    {
      *a8 = 0;
      CSPrintErrorLineFileData2(0, 0x1DC019Au, 1, 1);
LABEL_16:
      *a1 = 0;
      return v9;
    }
  }
  while ( a1[v13 - 1] == 32 )
  {
    a1[--v13] = 0;
    if ( !v13 )
      goto LABEL_12;
  }
  v9 = 0;
  *a8 = a1;
  return v9;
}

```

## disassembly

```asm
0x180018f34  push    rbx
0x180018f36  push    rbp
0x180018f37  push    rsi
0x180018f38  push    rdi
0x180018f39  push    r12
0x180018f3b  push    r14
0x180018f3d  push    r15
0x180018f3f  sub     rsp, 20h
0x180018f43  mov     rbp, [rsp+58h+arg_40]
0x180018f4b  mov     esi, 1
0x180018f50  mov     r15, rcx
0x180018f53  lea     r12d, [rsi+1Fh]
0x180018f57  mov     rdi, [rbp+0]
0x180018f5b  xor     eax, eax
0x180018f5d  mov     [r15], ax
0x180018f61  jmp     short loc_180018F67
0x180018f63  add     rdi, 2
0x180018f67  cmp     r12w, [rdi]
0x180018f6b  jz      short loc_180018F63
0x180018f6d  lea     rdx, asc_180063424; ","
0x180018f74  mov     rcx, rdi; String
0x180018f77  call    cs:__imp_wcscspn
0x180018f7d  mov     r14, rax
0x180018f80  cmp     rax, 104h
0x180018f86  jnb     loc_18001902A
0x180018f8c  lea     rbx, [rax+rax]
0x180018f90  mov     rdx, rdi; Src
0x180018f93  mov     r8, rbx; Size
0x180018f96  mov     rcx, r15; void *
0x180018f99  call    memcpy_0
0x180018f9e  add     rdi, rbx
0x180018fa1  xor     ecx, ecx
0x180018fa3  mov     [rbx+r15], cx
0x180018fa8  movzx   edx, word ptr [rdi]; Ch
0x180018fab  cmp     cx, dx
0x180018fae  jz      short loc_180018FD0
0x180018fb0  lea     rcx, asc_180063424; ","
0x180018fb7  call    cs:__imp_wcschr
0x180018fbd  test    rax, rax
0x180018fc0  jz      short loc_180018FD0
0x180018fc2  add     rdi, 2
0x180018fc6  xor     eax, eax
0x180018fc8  movzx   edx, word ptr [rdi]
0x180018fcb  cmp     ax, dx
0x180018fce  jnz     short loc_180018FB0
0x180018fd0  mov     [rbp+0], rdi
0x180018fd4  test    r14, r14
0x180018fd7  jz      short loc_180018FED
0x180018fd9  cmp     r12w, [r15+r14*2-2]
0x180018fdf  jnz     short loc_18001901B
0x180018fe1  sub     r14, rsi
0x180018fe4  mov     word ptr [r15+r14*2], 0
0x180018feb  jnz     short loc_180018FD9
0x180018fed  xor     eax, eax
0x180018fef  cmp     ax, [rdi]
0x180018ff2  jnz     loc_180018F57
0x180018ff8  mov     rax, [rsp+58h+arg_38]
0x180019000  mov     r9d, esi; int
0x180019003  mov     r8d, esi; int
0x180019006  mov     edx, 1DC019Ah; unsigned int
0x18001900b  xor     ecx, ecx; unsigned __int16 *
0x18001900d  mov     qword ptr [rax], 0
0x180019014  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180019019  jmp     short loc_18001903B
0x18001901b  mov     rax, [rsp+58h+arg_38]
0x180019023  xor     esi, esi
0x180019025  mov     [rax], r15
0x180019028  jmp     short loc_180019041
0x18001902a  mov     edx, 8007006Fh; int
0x18001902f  mov     ecx, 1C5019Ah; unsigned int
0x180019034  mov     esi, edx
0x180019036  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001903b  xor     eax, eax
0x18001903d  mov     [r15], ax
0x180019041  mov     eax, esi
0x180019043  add     rsp, 20h
0x180019047  pop     r15
0x180019049  pop     r14
0x18001904b  pop     r12
0x18001904d  pop     rdi
0x18001904e  pop     rsi
0x18001904f  pop     rbp
0x180019050  pop     rbx
0x180019051  retn
```
