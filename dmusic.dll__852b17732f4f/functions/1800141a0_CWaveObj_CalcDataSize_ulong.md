# CWaveObj::CalcDataSize(ulong *)

- ea: `0x1800141a0`
- end: `0x1800142f2`
- name: `?CalcDataSize@CWaveObj@@AEAAJPEAK@Z`
- size: `338`
- prototype: `__int64 __fastcall(CWaveObj *__hidden this, LPDWORD pdwOutputBytes)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180014d48`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800140a4`
- `0x1800141a0`
- `0x1800217bc`

## import_xrefs

- `MSACM32!acmStreamOpen` at `0x18001426e`
- `MSACM32!acmStreamOpen` at `0x18001426e`
- `MSACM32!acmStreamSize` at `0x180014291`
- `MSACM32!acmStreamSize` at `0x180014291`
- `MSACM32!acmStreamClose` at `0x1800142a6`
- `MSACM32!acmStreamClose` at `0x1800142d1`
- `MSACM32!acmStreamClose` at `0x1800142a6`
- `MSACM32!acmStreamClose` at `0x1800142d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWaveObj::CalcDataSize(CWaveObj *this, LPDWORD pdwOutputBytes)
{
  const struct tWAVEFORMATEX *v2; // r14
  struct tWAVEFORMATEX *v5; // rax
  struct tWAVEFORMATEX *v6; // rbx
  const void *v7; // rdx
  unsigned __int64 v8; // rdx
  MMRESULT v9; // eax
  struct tWAVEFORMATEX *v10; // rcx
  HACMSTREAM v12; // rcx
  HACMSTREAM phas; // [rsp+60h] [rbp+8h] BYREF
  struct tWAVEFORMATEX *v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = (const struct tWAVEFORMATEX *)((char *)this + 56);
  v14 = 0;
  if ( (unsigned __int16)(*((_WORD *)this + 28) - 352) <= 1u )
  {
    if ( (int)CWaveObj::AllocWMAudioFormat(this, v2, &v14) < 0 )
      return 2147500037LL;
    v6 = v14;
LABEL_8:
    phas = 0;
    if ( acmStreamOpen(&phas, 0, v6, (LPWAVEFORMATEX)((char *)this + 74), 0, 0, 0, 0) )
    {
      *pdwOutputBytes = 0;
    }
    else
    {
      if ( !acmStreamSize(phas, *((_DWORD *)this + 37), pdwOutputBytes, 0) && *pdwOutputBytes )
      {
        v9 = acmStreamClose(phas, 0);
        v10 = v6;
        if ( !v9 )
        {
          operator delete(v6, v8);
          return 0;
        }
        *pdwOutputBytes = 0;
        goto LABEL_17;
      }
      v12 = phas;
      *pdwOutputBytes = 0;
      acmStreamClose(v12, 0);
    }
    v10 = v6;
LABEL_17:
    operator delete(v10, v8);
    return 2147500037LL;
  }
  v5 = (struct tWAVEFORMATEX *)operator new[](*((unsigned __int16 *)this + 36) + 18LL);
  v6 = v5;
  if ( v5 )
  {
    *(_OWORD *)&v5->wFormatTag = *(_OWORD *)&v2->wFormatTag;
    v5->cbSize = v2->cbSize;
    v7 = (const void *)*((_QWORD *)this + 14);
    if ( v7 )
      memcpy_0(&v5[1], v7, *((unsigned __int16 *)this + 36));
    goto LABEL_8;
  }
  *pdwOutputBytes = 0;
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800141a0  mov     [rsp+arg_8], rbx
0x1800141a5  push    rsi
0x1800141a6  push    rdi
0x1800141a7  push    r14
0x1800141a9  sub     rsp, 40h
0x1800141ad  lea     r14, [rcx+38h]
0x1800141b1  mov     [rsp+58h+arg_10], 0
0x1800141ba  movzx   eax, word ptr [r14]
0x1800141be  mov     rsi, rcx
0x1800141c1  mov     ecx, 160h
0x1800141c6  mov     rdi, rdx
0x1800141c9  sub     ax, cx
0x1800141cc  cmp     ax, 1
0x1800141d0  jbe     short loc_180014217
0x1800141d2  movzx   ecx, word ptr [rsi+48h]
0x1800141d6  add     rcx, 12h; unsigned __int64
0x1800141da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800141df  mov     rbx, rax
0x1800141e2  test    rax, rax
0x1800141e5  jnz     short loc_1800141EE
0x1800141e7  mov     [rdi], eax
0x1800141e9  jmp     loc_1800142DF
0x1800141ee  movups  xmm0, xmmword ptr [r14]
0x1800141f2  movups  xmmword ptr [rax], xmm0
0x1800141f5  movzx   eax, word ptr [r14+10h]
0x1800141fa  mov     [rbx+10h], ax
0x1800141fe  mov     rdx, [rsi+70h]; Src
0x180014202  test    rdx, rdx
0x180014205  jz      short loc_180014234
0x180014207  movzx   r8d, word ptr [rsi+48h]; Size
0x18001420c  lea     rcx, [rbx+12h]; void *
0x180014210  call    memcpy_0
0x180014215  jmp     short loc_180014234
0x180014217  lea     r8, [rsp+58h+arg_10]; struct tWAVEFORMATEX **
0x18001421c  mov     rdx, r14; struct tWAVEFORMATEX *
0x18001421f  mov     rcx, rsi; this
0x180014222  call    ?AllocWMAudioFormat@CWaveObj@@AEAAJPEBUtWAVEFORMATEX@@PEAPEAU2@@Z; CWaveObj::AllocWMAudioFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180014227  test    eax, eax
0x180014229  js      loc_1800142DF
0x18001422f  mov     rbx, [rsp+58h+arg_10]
0x180014234  mov     [rsp+58h+fdwOpen], 0; fdwOpen
0x18001423c  lea     r9, [rsi+4Ah]; pwfxDst
0x180014240  mov     [rsp+58h+dwInstance], 0; dwInstance
0x180014249  lea     rcx, [rsp+58h+phas]; phas
0x18001424e  mov     [rsp+58h+dwCallback], 0; dwCallback
0x180014257  mov     r8, rbx; pwfxSrc
0x18001425a  xor     edx, edx; had
0x18001425c  mov     [rsp+58h+pwfltr], 0; pwfltr
0x180014265  mov     [rsp+58h+phas], 0
0x18001426e  call    cs:__imp_acmStreamOpen
0x180014274  test    eax, eax
0x180014276  jz      short loc_180014280
0x180014278  mov     dword ptr [rdi], 0
0x18001427e  jmp     short loc_1800142D7
0x180014280  mov     edx, [rsi+94h]; cbInput
0x180014286  xor     r9d, r9d; fdwSize
0x180014289  mov     rcx, [rsp+58h+phas]; has
0x18001428e  mov     r8, rdi; pdwOutputBytes
0x180014291  call    cs:__imp_acmStreamSize
0x180014297  test    eax, eax
0x180014299  jnz     short loc_1800142C4
0x18001429b  cmp     [rdi], eax
0x18001429d  jz      short loc_1800142C4
0x18001429f  mov     rcx, [rsp+58h+phas]; has
0x1800142a4  xor     edx, edx; fdwClose
0x1800142a6  call    cs:__imp_acmStreamClose
0x1800142ac  mov     rcx, rbx; void *
0x1800142af  test    eax, eax
0x1800142b1  jz      short loc_1800142BB
0x1800142b3  mov     dword ptr [rdi], 0
0x1800142b9  jmp     short loc_1800142DA
0x1800142bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800142c0  xor     eax, eax
0x1800142c2  jmp     short loc_1800142E4
0x1800142c4  mov     rcx, [rsp+58h+phas]; has
0x1800142c9  xor     edx, edx; fdwClose
0x1800142cb  mov     dword ptr [rdi], 0
0x1800142d1  call    cs:__imp_acmStreamClose
0x1800142d7  mov     rcx, rbx; void *
0x1800142da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800142df  mov     eax, 80004005h
0x1800142e4  mov     rbx, [rsp+58h+arg_8]
0x1800142e9  add     rsp, 40h
0x1800142ed  pop     r14
0x1800142ef  pop     rdi
0x1800142f0  pop     rsi
0x1800142f1  retn
```
