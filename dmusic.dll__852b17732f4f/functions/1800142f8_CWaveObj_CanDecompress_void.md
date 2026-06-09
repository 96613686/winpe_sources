# CWaveObj::CanDecompress(void)

- ea: `0x1800142f8`
- end: `0x18001442f`
- name: `?CanDecompress@CWaveObj@@AEAAJXZ`
- size: `311`
- prototype: `__int64 __fastcall(CWaveObj *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014834`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800140a4`
- `0x1800142f8`
- `0x1800217bc`

## import_xrefs

- `MSACM32!acmFormatSuggest` at `0x1800143d3`
- `MSACM32!acmFormatSuggest` at `0x1800143f6`
- `MSACM32!acmFormatSuggest` at `0x1800143d3`
- `MSACM32!acmFormatSuggest` at `0x1800143f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWaveObj::CanDecompress(CWaveObj *this)
{
  struct tWAVEFORMATEX *v1; // r15
  struct tWAVEFORMATEX *v2; // rsi
  const void *v4; // rdx
  int v5; // r14d
  struct tWAVEFORMATEX *v6; // rax
  struct tWAVEFORMATEX *v7; // rbx
  char *v9; // rbp
  WORD v10; // ax
  struct tWAVEFORMATEX *v11; // [rsp+60h] [rbp+8h] BYREF

  v1 = (struct tWAVEFORMATEX *)((char *)this + 74);
  v11 = 0;
  *(_OWORD *)((char *)this + 74) = 0;
  *((_WORD *)this + 45) = 0;
  v2 = (struct tWAVEFORMATEX *)((char *)this + 56);
  *((_WORD *)this + 44) = 16;
  *((_WORD *)this + 37) = 1;
  *((_WORD *)this + 38) = 1;
  v5 = CWaveObj::AllocWMAudioFormat(this, (const struct tWAVEFORMATEX *)((char *)this + 56), &v11);
  if ( v5 < 0 )
  {
    v7 = v2;
    v9 = (char *)v2;
  }
  else
  {
    v6 = (struct tWAVEFORMATEX *)operator new[](v2->cbSize + 18LL);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    *(_OWORD *)&v6->wFormatTag = *(_OWORD *)&v2->wFormatTag;
    v6->cbSize = v2->cbSize;
    v4 = (const void *)*((_QWORD *)this + 14);
    if ( v4 )
      memcpy_0(&v6[1], v4, *((unsigned __int16 *)this + 36));
    v9 = (char *)v7;
  }
  if ( *((_DWORD *)this + 13) == 1 )
  {
    v10 = *((_WORD *)this + 54);
    *(_OWORD *)&v1->wFormatTag = *(_OWORD *)((char *)this + 92);
    v1->cbSize = v10;
  }
  else if ( acmFormatSuggest(0, v7, v1, 0x12u, 0xB0000u) )
  {
    *((_WORD *)this + 44) = 8;
    if ( acmFormatSuggest(0, v7, v1, 0x12u, 0xB0000u) )
      goto LABEL_13;
  }
  v5 = 0;
LABEL_13:
  if ( v9 )
  {
    if ( v9 != (char *)v2 )
      operator delete(v7, (unsigned __int64)v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800142f8  mov     r11, rsp
0x1800142fb  mov     [r11+10h], rbx
0x1800142ff  mov     [r11+18h], rbp
0x180014303  push    rsi
0x180014304  push    rdi
0x180014305  push    r12
0x180014307  push    r14
0x180014309  push    r15
0x18001430b  sub     rsp, 30h
0x18001430f  xor     eax, eax
0x180014311  lea     r15, [rcx+4Ah]
0x180014315  xorps   xmm0, xmm0
0x180014318  mov     [r11+8], rax
0x18001431c  movups  xmmword ptr [r15], xmm0
0x180014320  mov     [r15+10h], ax
0x180014325  lea     rsi, [rcx+38h]
0x180014329  lea     r12d, [rax+1]
0x18001432d  mov     word ptr [rcx+58h], 10h
0x180014333  lea     r8, [r11+8]; struct tWAVEFORMATEX **
0x180014337  mov     [r15], r12w
0x18001433b  mov     rdx, rsi; struct tWAVEFORMATEX *
0x18001433e  mov     [rcx+4Ch], r12w
0x180014343  mov     rdi, rcx
0x180014346  call    ?AllocWMAudioFormat@CWaveObj@@AEAAJPEBUtWAVEFORMATEX@@PEAPEAU2@@Z; CWaveObj::AllocWMAudioFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001434b  mov     r14d, eax
0x18001434e  test    eax, eax
0x180014350  js      short loc_18001439B
0x180014352  movzx   ecx, word ptr [rsi+10h]
0x180014356  add     rcx, 12h; unsigned __int64
0x18001435a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001435f  mov     rbx, rax
0x180014362  test    rax, rax
0x180014365  jnz     short loc_180014371
0x180014367  mov     eax, 8007000Eh
0x18001436c  jmp     loc_180014418
0x180014371  movups  xmm0, xmmword ptr [rsi]
0x180014374  movups  xmmword ptr [rax], xmm0
0x180014377  movzx   eax, word ptr [rsi+10h]
0x18001437b  mov     [rbx+10h], ax
0x18001437f  mov     rdx, [rdi+70h]; Src
0x180014383  test    rdx, rdx
0x180014386  jz      short loc_180014396
0x180014388  movzx   r8d, word ptr [rdi+48h]; Size
0x18001438d  lea     rcx, [rbx+12h]; void *
0x180014391  call    memcpy_0
0x180014396  mov     rbp, rbx
0x180014399  jmp     short loc_1800143A1
0x18001439b  mov     rbx, rsi
0x18001439e  mov     rbp, rsi
0x1800143a1  cmp     [rdi+34h], r12d
0x1800143a5  jnz     short loc_1800143BA
0x1800143a7  movups  xmm0, xmmword ptr [rdi+5Ch]
0x1800143ab  movzx   eax, word ptr [rdi+6Ch]
0x1800143af  movups  xmmword ptr [r15], xmm0
0x1800143b3  mov     [r15+10h], ax
0x1800143b8  jmp     short loc_180014400
0x1800143ba  mov     r12d, 0B0000h
0x1800143c0  mov     r9d, 12h; cbwfxDst
0x1800143c6  mov     r8, r15; pwfxDst
0x1800143c9  mov     [rsp+58h+fdwSuggest], r12d; fdwSuggest
0x1800143ce  mov     rdx, rbx; pwfxSrc
0x1800143d1  xor     ecx, ecx; had
0x1800143d3  call    cs:__imp_acmFormatSuggest
0x1800143d9  test    eax, eax
0x1800143db  jz      short loc_180014400
0x1800143dd  mov     r9d, 12h; cbwfxDst
0x1800143e3  mov     word ptr [rdi+58h], 8
0x1800143e9  mov     r8, r15; pwfxDst
0x1800143ec  mov     [rsp+58h+fdwSuggest], r12d; fdwSuggest
0x1800143f1  mov     rdx, rbx; pwfxSrc
0x1800143f4  xor     ecx, ecx; had
0x1800143f6  call    cs:__imp_acmFormatSuggest
0x1800143fc  test    eax, eax
0x1800143fe  jnz     short loc_180014403
0x180014400  xor     r14d, r14d
0x180014403  test    rbp, rbp
0x180014406  jz      short loc_180014415
0x180014408  cmp     rbp, rsi
0x18001440b  jz      short loc_180014415
0x18001440d  mov     rcx, rbx; void *
0x180014410  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014415  mov     eax, r14d
0x180014418  mov     rbx, [rsp+58h+arg_8]
0x18001441d  mov     rbp, [rsp+58h+arg_10]
0x180014422  add     rsp, 30h
0x180014426  pop     r15
0x180014428  pop     r14
0x18001442a  pop     r12
0x18001442c  pop     rdi
0x18001442d  pop     rsi
0x18001442e  retn
```
