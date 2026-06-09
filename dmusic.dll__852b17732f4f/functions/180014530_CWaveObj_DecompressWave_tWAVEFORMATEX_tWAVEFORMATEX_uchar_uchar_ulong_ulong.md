# CWaveObj::DecompressWave(tWAVEFORMATEX *,tWAVEFORMATEX *,uchar *,uchar *,ulong,ulong)

- ea: `0x180014530`
- end: `0x18001471c`
- name: `?DecompressWave@CWaveObj@@AEAAJPEAUtWAVEFORMATEX@@0PEAE1KK@Z`
- size: `492`
- prototype: `__int64 __fastcall(CWaveObj *this, struct tWAVEFORMATEX *, struct tWAVEFORMATEX *, unsigned __int8 *, unsigned __int8 *, DWORD, unsigned int Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014bb8`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x1800016d0`
- `0x1800021a8`
- `0x180014530`
- `0x1800217bc`

## import_xrefs

- `MSACM32!acmStreamOpen` at `0x1800145b5`
- `MSACM32!acmStreamOpen` at `0x1800145b5`
- `MSACM32!acmStreamPrepareHeader` at `0x18001462e`
- `MSACM32!acmStreamPrepareHeader` at `0x18001462e`
- `MSACM32!acmStreamUnprepareHeader` at `0x18001467a`
- `MSACM32!acmStreamUnprepareHeader` at `0x1800146b0`
- `MSACM32!acmStreamUnprepareHeader` at `0x18001467a`
- `MSACM32!acmStreamUnprepareHeader` at `0x1800146b0`
- `MSACM32!acmStreamConvert` at `0x18001464f`
- `MSACM32!acmStreamConvert` at `0x18001464f`
- `MSACM32!acmStreamClose` at `0x180014687`
- `MSACM32!acmStreamClose` at `0x1800146c8`
- `MSACM32!acmStreamClose` at `0x180014687`
- `MSACM32!acmStreamClose` at `0x1800146c8`

## pseudocode

```c
__int64 __fastcall CWaveObj::DecompressWave(
        CWaveObj *this,
        struct tWAVEFORMATEX *a2,
        struct tWAVEFORMATEX *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        DWORD a6,
        unsigned int Size)
{
  DWORD nSamplesPerSec; // ecx
  DWORD v10; // eax
  BYTE *v11; // rax
  BYTE *v12; // rdi
  MMRESULT v14; // eax
  DWORD cbDstLength; // r14d
  HACMSTREAM v16; // rcx
  MMRESULT v17; // eax
  MMRESULT v18; // r14d
  int v19; // eax
  __int64 v20; // rdx
  int v21; // r15d
  unsigned __int64 v22; // rdx
  HACMSTREAM phas; // [rsp+40h] [rbp-91h] BYREF
  tACMSTREAMHEADER pash; // [rsp+50h] [rbp-81h] BYREF

  nSamplesPerSec = a2->nSamplesPerSec;
  if ( nSamplesPerSec != a3->nSamplesPerSec )
  {
    v10 = nSamplesPerSec * a3->nBlockAlign;
    a3->nSamplesPerSec = nSamplesPerSec;
    a3->nAvgBytesPerSec = v10;
  }
  phas = 0;
  if ( acmStreamOpen(&phas, 0, a2, a3, 0, 0, 0, 0) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 46) )
  {
    v11 = (BYTE *)operator new[](Size);
    v12 = v11;
    if ( !v11 )
      return 2147942414LL;
    memset_0(v11, 0, Size);
  }
  else
  {
    v12 = a5;
  }
  memset_0(&pash, 0, sizeof(pash));
  pash.cbStruct = 124;
  pash.cbSrcLength = a6;
  pash.pbSrc = a4;
  pash.cbDstLength = Size;
  pash.pbDst = v12;
  if ( acmStreamPrepareHeader(phas, &pash, 0) || (pash.fdwStatus & 0x20000) == 0 )
    goto LABEL_13;
  v14 = acmStreamConvert(phas, &pash, 0x24u);
  cbDstLength = pash.cbDstLength;
  *((_DWORD *)this + 36) = pash.cbDstLengthUsed;
  pash.cbSrcLength = a6;
  pash.cbDstLength = Size;
  if ( v14 )
  {
    acmStreamUnprepareHeader(phas, &pash, 0);
LABEL_13:
    v16 = phas;
LABEL_14:
    acmStreamClose(v16, 0);
    return 2147500037LL;
  }
  v17 = acmStreamUnprepareHeader(phas, &pash, 0);
  v16 = phas;
  if ( v17 )
    goto LABEL_14;
  *((_DWORD *)this + 35) = cbDstLength;
  v18 = acmStreamClose(v16, 0);
  v19 = *((_DWORD *)this + 46);
  if ( v19 )
  {
    v20 = v19 * (*((unsigned __int16 *)this + 53) >> 3);
    v21 = Size - v20;
    memcpy_0(a5, &v12[v20], Size - (unsigned int)v20);
    *((_DWORD *)this + 35) = v21;
    *((_DWORD *)this + 36) = v21;
    operator delete(v12, v22);
  }
  return v18 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180014530  push    rbp
0x180014532  push    rbx
0x180014533  push    rsi
0x180014534  push    rdi
0x180014535  push    r12
0x180014537  push    r14
0x180014539  push    r15
0x18001453b  lea     rbp, [rsp-0Fh]
0x180014540  sub     rsp, 0E0h
0x180014547  mov     rax, cs:__security_cookie
0x18001454e  xor     rax, rsp
0x180014551  mov     [rbp+3Fh+var_40], rax
0x180014555  mov     r12, [rbp+3Fh+arg_20]
0x180014559  mov     rsi, rcx
0x18001455c  mov     ecx, [rdx+4]
0x18001455f  mov     r14, r9
0x180014562  mov     r15d, dword ptr [rbp+3Fh+Size]
0x180014566  cmp     ecx, [r8+4]
0x18001456a  jz      short loc_18001457C
0x18001456c  movzx   eax, word ptr [r8+0Ch]
0x180014571  imul    eax, ecx
0x180014574  mov     [r8+4], ecx
0x180014578  mov     [r8+8], eax
0x18001457c  mov     [rsp+110h+fdwOpen], 0; fdwOpen
0x180014584  lea     rcx, [rsp+110h+phas]; phas
0x180014589  mov     r9, r8; pwfxDst
0x18001458c  mov     [rsp+110h+dwInstance], 0; dwInstance
0x180014595  mov     r8, rdx; pwfxSrc
0x180014598  mov     [rsp+110h+dwCallback], 0; dwCallback
0x1800145a1  xor     edx, edx; had
0x1800145a3  mov     [rsp+110h+pwfltr], 0; pwfltr
0x1800145ac  mov     [rsp+110h+phas], 0
0x1800145b5  call    cs:__imp_acmStreamOpen
0x1800145bb  test    eax, eax
0x1800145bd  jnz     loc_18001468D
0x1800145c3  cmp     [rsi+0B8h], eax
0x1800145c9  jbe     short loc_1800145F4
0x1800145cb  mov     rcx, r15; unsigned __int64
0x1800145ce  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800145d3  mov     rdi, rax
0x1800145d6  test    rax, rax
0x1800145d9  jnz     short loc_1800145E5
0x1800145db  mov     eax, 8007000Eh
0x1800145e0  jmp     loc_180014692
0x1800145e5  mov     r8, r15; Size
0x1800145e8  xor     edx, edx; Val
0x1800145ea  mov     rcx, rax; void *
0x1800145ed  call    memset_0
0x1800145f2  jmp     short loc_1800145F7
0x1800145f4  mov     rdi, r12
0x1800145f7  mov     ebx, 7Ch ; '|'
0x1800145fc  lea     rcx, [rsp+110h+pash]; void *
0x180014601  mov     r8d, ebx; Size
0x180014604  xor     edx, edx; Val
0x180014606  call    memset_0
0x18001460b  mov     rcx, [rsp+110h+phas]; has
0x180014610  lea     rdx, [rsp+110h+pash]; pash
0x180014615  mov     [rsp+110h+pash.cbStruct], ebx
0x180014619  xor     r8d, r8d; fdwPrepare
0x18001461c  mov     ebx, [rbp+3Fh+arg_28]
0x18001461f  mov     [rbp+3Fh+pash.cbSrcLength], ebx
0x180014622  mov     [rbp+3Fh+pash.pbSrc], r14
0x180014626  mov     [rbp+3Fh+pash.cbDstLength], r15d
0x18001462a  mov     [rbp+3Fh+pash.pbDst], rdi
0x18001462e  call    cs:__imp_acmStreamPrepareHeader
0x180014634  test    eax, eax
0x180014636  jnz     short loc_180014680
0x180014638  test    [rbp+3Fh+pash.fdwStatus], 20000h
0x18001463f  jz      short loc_180014680
0x180014641  mov     rcx, [rsp+110h+phas]; has
0x180014646  lea     r8d, [rax+24h]; fdwConvert
0x18001464a  lea     rdx, [rsp+110h+pash]; pash
0x18001464f  call    cs:__imp_acmStreamConvert
0x180014655  mov     ecx, [rbp+3Fh+pash.cbDstLengthUsed]
0x180014658  lea     rdx, [rsp+110h+pash]; pash
0x18001465d  mov     r14d, [rbp+3Fh+pash.cbDstLength]
0x180014661  xor     r8d, r8d; fdwUnprepare
0x180014664  mov     [rsi+90h], ecx
0x18001466a  mov     rcx, [rsp+110h+phas]; has
0x18001466f  mov     [rbp+3Fh+pash.cbSrcLength], ebx
0x180014672  mov     [rbp+3Fh+pash.cbDstLength], r15d
0x180014676  test    eax, eax
0x180014678  jz      short loc_1800146B0
0x18001467a  call    cs:__imp_acmStreamUnprepareHeader
0x180014680  mov     rcx, [rsp+110h+phas]; has
0x180014685  xor     edx, edx; fdwClose
0x180014687  call    cs:__imp_acmStreamClose
0x18001468d  mov     eax, 80004005h
0x180014692  mov     rcx, [rbp+3Fh+var_40]
0x180014696  xor     rcx, rsp; StackCookie
0x180014699  call    __security_check_cookie
0x18001469e  add     rsp, 0E0h
0x1800146a5  pop     r15
0x1800146a7  pop     r14
0x1800146a9  pop     r12
0x1800146ab  pop     rdi
0x1800146ac  pop     rsi
0x1800146ad  pop     rbx
0x1800146ae  pop     rbp
0x1800146af  retn
0x1800146b0  call    cs:__imp_acmStreamUnprepareHeader
0x1800146b6  mov     rcx, [rsp+110h+phas]; has
0x1800146bb  xor     edx, edx; fdwClose
0x1800146bd  test    eax, eax
0x1800146bf  jnz     short loc_180014687
0x1800146c1  mov     [rsi+8Ch], r14d
0x1800146c8  call    cs:__imp_acmStreamClose
0x1800146ce  mov     r14d, eax
0x1800146d1  mov     eax, [rsi+0B8h]
0x1800146d7  test    eax, eax
0x1800146d9  jz      short loc_18001470D
0x1800146db  movzx   edx, word ptr [rsi+6Ah]
0x1800146df  mov     rcx, r12; void *
0x1800146e2  shr     edx, 3
0x1800146e5  imul    edx, eax
0x1800146e8  sub     r15d, edx
0x1800146eb  add     rdx, rdi; Src
0x1800146ee  mov     r8d, r15d; Size
0x1800146f1  mov     ebx, r15d
0x1800146f4  call    memcpy_0
0x1800146f9  mov     rcx, rdi; void *
0x1800146fc  mov     [rsi+8Ch], ebx
0x180014702  mov     [rsi+90h], ebx
0x180014708  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001470d  neg     r14d
0x180014710  sbb     eax, eax
0x180014712  and     eax, 80004005h
0x180014717  jmp     loc_180014692
```
