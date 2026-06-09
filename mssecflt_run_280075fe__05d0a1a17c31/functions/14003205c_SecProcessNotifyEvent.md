# SecProcessNotifyEvent

- ea: `0x14003205c`
- end: `0x1400327d7`
- name: `SecProcessNotifyEvent`
- size: `1915`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002f6d0`
- `0x14002fa68`

## callees

- `0x140006d3c`
- `0x14000885c`
- `0x140011650`
- `0x1400119c0`
- `0x140028640`
- `0x14003044c`
- `0x140030ca8`
- `0x140031300`
- `0x140031598`
- `0x14003205c`
- `0x140041eac`
- `0x14004268c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140032222`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140032509`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003266b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140032222`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140032509`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003266b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400327a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400327a7`

## pseudocode

```c
void __fastcall SecProcessNotifyEvent(
        __int64 a1,
        int *a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        __int64 a7,
        bool *a8)
{
  wchar_t *v10; // r15
  __int64 v11; // rbx
  wchar_t *v12; // rsi
  __int64 v13; // r14
  wchar_t *v14; // r12
  __int64 v15; // rax
  wchar_t *v16; // rax
  int v17; // ebx
  unsigned int CurrentThreadId; // eax
  int v19; // r14d
  int v20; // r15d
  int v21; // r12d
  int v22; // r13d
  int v23; // edx
  const WCHAR *v24; // rax
  const WCHAR *v25; // rax
  bool v26; // zf
  int v27; // ebx
  __int64 v28; // r9
  int v29; // r11d
  __int64 v30; // r8
  const WCHAR *v31; // rax
  const WCHAR *v32; // rax
  void *Sid; // r10
  int v34; // ecx
  int v35; // r12d
  int v36; // eax
  int v37; // r15d
  __int64 v38; // r14
  int v39; // r13d
  __int64 v40; // rdi
  int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // r8
  wchar_t *v44; // r11
  wchar_t *v45; // rsi
  void *v46; // r9
  int v47; // ecx
  unsigned int v48; // eax
  unsigned int v49; // eax
  int v50; // r13d
  int v51; // r15d
  __int64 v52; // rdi
  __int64 v53; // rsi
  __int64 v54; // r14
  volatile signed __int64 *v55; // rbx
  void *v56; // r12
  char CachedCodeIntegrityOptions; // al
  int v58; // ecx
  unsigned int v59; // eax
  char v60; // [rsp+78h] [rbp-168h]
  char HasMotwAds; // [rsp+160h] [rbp-80h]
  char v62; // [rsp+161h] [rbp-7Fh]
  int v64; // [rsp+168h] [rbp-78h]
  int v65; // [rsp+168h] [rbp-78h]
  int v66; // [rsp+170h] [rbp-70h]
  int v67; // [rsp+170h] [rbp-70h]
  int v68; // [rsp+178h] [rbp-68h]
  wchar_t *v69; // [rsp+178h] [rbp-68h]
  int v71; // [rsp+180h] [rbp-60h]
  char v72; // [rsp+188h] [rbp-58h]
  wchar_t *v73; // [rsp+190h] [rbp-50h]
  wchar_t *v74; // [rsp+190h] [rbp-50h]
  wchar_t *v75; // [rsp+198h] [rbp-48h]
  wchar_t *Str; // [rsp+198h] [rbp-48h]
  __int64 v77; // [rsp+1A0h] [rbp-40h]
  __int64 v78; // [rsp+1A0h] [rbp-40h]
  __int64 v79; // [rsp+1A8h] [rbp-38h]
  char v80[4]; // [rsp+1B0h] [rbp-30h]
  char v81[4]; // [rsp+1B4h] [rbp-2Ch]
  char v82[4]; // [rsp+1B8h] [rbp-28h]
  char v84[8]; // [rsp+1C8h] [rbp-18h]
  char v85[8]; // [rsp+1C8h] [rbp-18h]
  char v86[8]; // [rsp+1D0h] [rbp-10h]
  int v87; // [rsp+1D0h] [rbp-10h]
  char v88[8]; // [rsp+1E0h] [rbp+0h]
  char v89[8]; // [rsp+1E8h] [rbp+8h]
  wchar_t *v90; // [rsp+1F0h] [rbp+10h]
  char v91[8]; // [rsp+1F8h] [rbp+18h]
  char v92[8]; // [rsp+208h] [rbp+28h]
  char v93[8]; // [rsp+210h] [rbp+30h]
  char v94[8]; // [rsp+218h] [rbp+38h]
  PVOID P; // [rsp+220h] [rbp+40h] BYREF
  char v96[8]; // [rsp+228h] [rbp+48h] BYREF
  char v97[160]; // [rsp+230h] [rbp+50h] BYREF

  v10 = 0;
  *(_DWORD *)&v96[4] = 0;
  memset(v97, 0, 0x94u);
  P = 0;
  HasMotwAds = 0;
  v96[1] = 0;
  v96[0] = 0;
  v11 = 0;
  v79 = 0;
  v12 = 0;
  v77 = 0;
  v13 = 0;
  v75 = 0;
  v14 = 0;
  v73 = 0;
  if ( (int)SecGetEffectiveTokenUser(KeGetCurrentThread(), a1, &P, &v96[1], v96) >= 0 )
  {
    if ( a3 )
    {
      *a8 = 0;
      if ( (BYTE6(xmmword_14001B740) & 1) != 0 )
        *a8 = (int)SecCacheQueryFileHashEa(a3, v97) < 0;
      HasMotwAds = SecFileHasMotwAds(a3);
    }
    _mm_lfence();
    if ( a5 )
    {
      if ( *(_WORD *)(a1 + 80) )
      {
        _mm_lfence();
        if ( *(_QWORD *)(a1 + 88) )
          v11 = *(_QWORD *)(a1 + 88);
        v79 = v11;
      }
      if ( *(_WORD *)(a1 + 128) )
      {
        _mm_lfence();
        if ( *(_QWORD *)(a1 + 136) )
          v12 = *(wchar_t **)(a1 + 136);
      }
      if ( *(_WORD *)(a1 + 152) )
      {
        _mm_lfence();
        if ( *(_QWORD *)(a1 + 160) )
          v13 = *(_QWORD *)(a1 + 160);
        v77 = v13;
      }
      v15 = *(_QWORD *)(a1 + 224);
      if ( v15 && *(_WORD *)v15 )
      {
        v16 = *(wchar_t **)(v15 + 8);
        if ( v16 )
          v14 = v16;
        v75 = v14;
      }
      if ( *(_WORD *)(a1 + 688) )
      {
        _mm_lfence();
        if ( *(_QWORD *)(a1 + 696) )
          v10 = *(wchar_t **)(a1 + 696);
        v73 = v10;
      }
      v17 = *(_DWORD *)(a1 + 280);
      *(_DWORD *)v81 = *(_DWORD *)(a1 + 624);
      *(_DWORD *)v82 = *(_DWORD *)(a1 + 104);
      v64 = *(_DWORD *)(a1 + 56);
      CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
      v19 = *(_DWORD *)(a1 + 680);
      v20 = *(_DWORD *)(a1 + 676);
      v21 = *(_DWORD *)(a1 + 672);
      v22 = *(_DWORD *)(a1 + 644);
      v68 = CurrentThreadId;
      v66 = *(_DWORD *)(a1 + 32);
      *(_DWORD *)v80 = *(_DWORD *)(a1 + 640);
      *(_QWORD *)v88 = *(_QWORD *)(a1 + 632);
      *(_QWORD *)v89 = *(_QWORD *)(a1 + 568);
      v90 = *(wchar_t **)(a7 + 8);
      *(_QWORD *)v91 = *(_QWORD *)(a1 + 120);
      *(_QWORD *)v92 = *(_QWORD *)(a1 + 112);
      v71 = *(_DWORD *)(a1 + 592);
      v62 = *(_BYTE *)(a1 + 596);
      v23 = *(_DWORD *)(a1 + 276);
      *(_QWORD *)v93 = *(_QWORD *)(a1 + 584);
      *(_QWORD *)v94 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)v84 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)v86 = *(_QWORD *)(a1 + 288);
      v72 = v96[0];
      v24 = v73;
      if ( !v73 )
        v24 = &SourceString;
      v74 = (wchar_t *)v24;
      v25 = v75;
      if ( !v12 )
        v12 = (wchar_t *)&SourceString;
      v26 = v17 == 0;
      v27 = *(_DWORD *)(a1 + 264);
      if ( !v75 )
        v25 = &SourceString;
      v28 = *(_QWORD *)(a1 + 64);
      v29 = *(_DWORD *)(a1 + 616);
      v30 = *(_QWORD *)(a1 + 40);
      Str = (wchar_t *)v25;
      v31 = (const WCHAR *)v77;
      if ( !v77 )
        v31 = &SourceString;
      v78 = (__int64)v31;
      v32 = (const WCHAR *)v79;
      if ( !v79 )
        v32 = &SourceString;
      Sid = *(void **)P;
      v34 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u) + 1;
      EventWriteCreateProcess(
        v34,
        v66,
        v30,
        v68,
        Sid,
        v29,
        v64,
        v28,
        (__int64)v32,
        v78,
        Str,
        (__int64)&v97[1],
        (__int64)&v97[33],
        (__int64)&v97[53],
        v97[136],
        v97[140],
        v97[144],
        HasMotwAds,
        v27,
        v23,
        !v26,
        v72,
        v86[0],
        v84[0],
        v94[0],
        (__int64)&v97[69],
        v93[0],
        v62,
        v71,
        v82[0],
        v92[0],
        v12,
        v91[0],
        a6,
        v90,
        v89[0],
        v81[0],
        v88[0],
        v80[0],
        v22,
        v21,
        v20,
        v19,
        v74);
    }
    else
    {
      v35 = *a2;
      v36 = (unsigned int)PsGetCurrentThreadId();
      v37 = *a2;
      v38 = *(_QWORD *)(*((_QWORD *)a2 + 5) + 8LL);
      v39 = *(_DWORD *)(a1 + 32);
      v40 = *((_QWORD *)a2 + 3);
      v41 = *(_DWORD *)(a1 + 616);
      v42 = *(_QWORD *)(a1 + 48);
      v43 = *(_QWORD *)(a1 + 40);
      v44 = *(wchar_t **)(a7 + 8);
      v45 = *(wchar_t **)(a4 + 8);
      v46 = *(void **)P;
      v60 = *((_QWORD *)a2 + 1);
      v47 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u) + 1;
      v48 = EventWriteLoadImage(
              v47,
              v39,
              v43,
              v36,
              v46,
              v41,
              v45,
              HasMotwAds,
              (__int64)&v97[1],
              (__int64)&v97[33],
              (__int64)&v97[53],
              v97[136],
              v97[140],
              v97[144],
              BYTE1(v35) & 1,
              v60,
              v42,
              v40,
              (__int64)&v97[69],
              a6,
              v44,
              (unsigned __int16)v37 >> 12,
              v38);
      SecIncrementEtwCounters(v48);
      if ( (*a2 & 0x100) != 0 && (xmmword_14001B740 & 0x4000000) != 0 && (int)SecQueryCodeIntegrityOptions(&v96[4]) >= 0 )
      {
        _mm_lfence();
        v49 = (unsigned int)PsGetCurrentThreadId();
        v50 = *a2;
        v51 = *a2;
        v52 = *((_QWORD *)a2 + 3);
        v53 = *((_QWORD *)a2 + 1);
        v54 = *(_QWORD *)(a1 + 48);
        v55 = (volatile signed __int64 *)SecData;
        v87 = v49;
        v65 = *(_DWORD *)(a1 + 32);
        v69 = *(wchar_t **)(a4 + 8);
        v67 = *(_DWORD *)(a1 + 616);
        v56 = *(void **)P;
        *(_QWORD *)v85 = *(_QWORD *)(a1 + 40);
        CachedCodeIntegrityOptions = SecGetCachedCodeIntegrityOptions();
        v58 = _InterlockedExchangeAdd64(v55 + 42, 1u) + 1;
        v59 = EventWriteLoadDriver(
                v58,
                v65,
                *(int *)v85,
                v87,
                v56,
                v67,
                v69,
                HasMotwAds,
                (__int64)&v97[1],
                (__int64)&v97[33],
                (__int64)&v97[53],
                v97[136],
                v97[140],
                v97[144],
                (unsigned __int16)v50 >> 12,
                BYTE2(v51) & 7,
                v96[4],
                CachedCodeIntegrityOptions,
                v54,
                v53,
                v52,
                (char)&v97[69]);
        SecIncrementEtwCounters(v59);
      }
    }
  }
  if ( v96[1] )
    ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14003205c  push    rbp
0x14003205e  push    rbx
0x14003205f  push    rsi
0x140032060  push    rdi
0x140032061  push    r12
0x140032063  push    r13
0x140032065  push    r14
0x140032067  push    r15
0x140032069  lea     rbp, [rsp-108h]
0x140032071  sub     rsp, 2E8h
0x140032078  mov     rax, cs:__security_cookie
0x14003207f  xor     rax, rsp
0x140032082  mov     [rbp+140h+var_50], rax
0x140032089  mov     rax, [rbp+140h+arg_28]
0x140032090  mov     r13, r8
0x140032093  mov     [rbp+140h+var_148], rax
0x140032097  mov     rdi, rcx
0x14003209a  mov     rax, [rbp+140h+arg_30]
0x1400320a1  xor     r15d, r15d
0x1400320a4  mov     qword ptr [rbp+140h+var_198], rax
0x1400320a8  mov     r8d, 94h; Size
0x1400320ae  mov     rax, [rbp+140h+arg_38]
0x1400320b5  mov     qword ptr [rbp+140h+var_1B8], rdx
0x1400320b9  xor     edx, edx; Val
0x1400320bb  mov     [rbp+140h+var_160], rcx
0x1400320bf  lea     rcx, [rbp+140h+var_F0]; void *
0x1400320c3  mov     qword ptr [rbp+140h+var_1B0], rax
0x1400320c7  mov     qword ptr [rbp+140h+var_1A0], r9
0x1400320cb  mov     dword ptr [rbp+140h+var_F8+4], r15d
0x1400320cf  call    memset
0x1400320d4  xor     ecx, ecx
0x1400320d6  mov     [rbp+140h+P], r15
0x1400320da  mov     [rbp+140h+var_1C0], cl
0x1400320dd  lea     rax, [rbp+140h+var_F8]
0x1400320e1  mov     [rbp+140h+var_F8+1], r15b
0x1400320e5  lea     r9, [rbp+140h+var_F8+1]
0x1400320e9  mov     [rbp+140h+var_F8], r15b
0x1400320ed  lea     r8, [rbp+140h+P]
0x1400320f1  mov     rcx, gs:188h; Thread
0x1400320fa  mov     ebx, r15d
0x1400320fd  mov     rdx, rdi
0x140032100  mov     [rbp+140h+var_178], rbx
0x140032104  mov     esi, r15d
0x140032107  mov     [rbp+140h+var_180], r15
0x14003210b  mov     r14d, r15d
0x14003210e  mov     [rbp+140h+var_188], r15
0x140032112  mov     r12d, r15d
0x140032115  mov     [rbp+140h+var_190], r15
0x140032119  mov     [rsp+320h+Sid], rax; __int64
0x14003211e  call    SecGetEffectiveTokenUser
0x140032123  xor     ecx, ecx
0x140032125  test    eax, eax
0x140032127  js      loc_14003279A
0x14003212d  test    r13, r13
0x140032130  jz      short loc_140032161
0x140032132  mov     rax, qword ptr [rbp+140h+var_1B0]
0x140032136  mov     [rax], cl
0x140032138  test    byte ptr cs:xmmword_14001B740+6, 1
0x14003213f  jz      short loc_140032156
0x140032141  lea     rdx, [rbp+140h+var_F0]
0x140032145  mov     rcx, r13
0x140032148  call    SecCacheQueryFileHashEa
0x14003214d  mov     rcx, qword ptr [rbp+140h+var_1B0]
0x140032151  shr     eax, 1Fh
0x140032154  mov     [rcx], al
0x140032156  mov     rcx, r13; FileObject
0x140032159  call    SecFileHasMotwAds
0x14003215e  mov     [rbp+140h+var_1C0], al
0x140032161  xor     r13d, r13d
0x140032164  lfence
0x140032167  cmp     [rbp+140h+arg_20], r13b
0x14003216e  jz      loc_140032502
0x140032174  cmp     r13w, [rdi+50h]
0x140032179  jz      short loc_14003218D
0x14003217b  lfence
0x14003217e  mov     rcx, [rdi+58h]
0x140032182  test    rcx, rcx
0x140032185  cmovnz  rbx, rcx
0x140032189  mov     [rbp+140h+var_178], rbx
0x14003218d  cmp     r13w, [rdi+80h]
0x140032195  jz      short loc_1400321A8
0x140032197  lfence
0x14003219a  mov     rax, [rdi+88h]
0x1400321a1  test    rax, rax
0x1400321a4  cmovnz  rsi, rax
0x1400321a8  cmp     r13w, [rdi+98h]
0x1400321b0  jz      short loc_1400321C7
0x1400321b2  lfence
0x1400321b5  mov     rax, [rdi+0A0h]
0x1400321bc  test    rax, rax
0x1400321bf  cmovnz  r14, rax
0x1400321c3  mov     [rbp+140h+var_180], r14
0x1400321c7  mov     rax, [rdi+0E0h]
0x1400321ce  test    rax, rax
0x1400321d1  jz      short loc_1400321E8
0x1400321d3  cmp     r13w, [rax]
0x1400321d7  jz      short loc_1400321E8
0x1400321d9  mov     rax, [rax+8]
0x1400321dd  test    rax, rax
0x1400321e0  cmovnz  r12, rax
0x1400321e4  mov     [rbp+140h+var_188], r12
0x1400321e8  cmp     r13w, [rdi+2B0h]
0x1400321f0  jz      short loc_140032207
0x1400321f2  lfence
0x1400321f5  mov     rax, [rdi+2B8h]
0x1400321fc  test    rax, rax
0x1400321ff  cmovnz  r15, rax
0x140032203  mov     [rbp+140h+var_190], r15
0x140032207  mov     eax, [rdi+270h]
0x14003220d  mov     ebx, [rdi+118h]
0x140032213  mov     dword ptr [rbp+140h+var_16C], eax
0x140032216  mov     eax, [rdi+68h]
0x140032219  mov     dword ptr [rbp+140h+var_168], eax
0x14003221c  mov     eax, [rdi+38h]
0x14003221f  mov     dword ptr [rbp+140h+var_1B8], eax
0x140032222  call    cs:__imp_PsGetCurrentThreadId
0x140032229  nop     dword ptr [rax+rax+00h]
0x14003222e  mov     r11, qword ptr [rbp+140h+var_198]
0x140032232  lea     rcx, SourceString
0x140032239  mov     r14d, [rdi+2A8h]
0x140032240  xor     r8d, r8d
0x140032243  mov     r15d, [rdi+2A4h]
0x14003224a  mov     r12d, [rdi+2A0h]
0x140032251  mov     r13d, [rdi+284h]
0x140032258  mov     [rbp+140h+var_1A8], rax
0x14003225c  mov     eax, [rdi+20h]
0x14003225f  mov     dword ptr [rbp+140h+var_1B0], eax
0x140032262  mov     eax, [rdi+280h]
0x140032268  mov     dword ptr [rbp+140h+var_170], eax
0x14003226b  mov     rax, [rdi+278h]
0x140032272  mov     qword ptr [rbp+140h+var_140], rax
0x140032276  mov     rax, [rdi+238h]
0x14003227d  mov     qword ptr [rbp+140h+var_138], rax
0x140032281  mov     rax, [r11+8]
0x140032285  mov     [rbp+140h+var_130], rax
0x140032289  mov     rax, [rdi+78h]
0x14003228d  mov     qword ptr [rbp+140h+var_128], rax
0x140032291  mov     rax, [rdi+70h]
0x140032295  mov     qword ptr [rbp+140h+var_118], rax
0x140032299  mov     eax, [rdi+250h]
0x14003229f  mov     dword ptr [rbp+140h+var_1A0], eax
0x1400322a2  mov     al, [rdi+254h]
0x1400322a8  mov     [rbp+140h+var_1BF], al
0x1400322ab  mov     rax, [rdi+248h]
0x1400322b2  mov     edx, [rdi+114h]
0x1400322b8  mov     qword ptr [rbp+140h+var_110], rax
0x1400322bc  mov     rax, [rdi+48h]
0x1400322c0  mov     qword ptr [rbp+140h+var_108], rax
0x1400322c4  mov     rax, [rdi+30h]
0x1400322c8  mov     qword ptr [rbp+140h+var_158], rax
0x1400322cc  mov     rax, [rdi+120h]
0x1400322d3  mov     qword ptr [rbp+140h+var_150], rax
0x1400322d7  movzx   eax, [rbp+140h+var_F8]
0x1400322db  mov     dword ptr [rbp+140h+var_198], eax
0x1400322de  mov     rax, [rbp+140h+var_190]
0x1400322e2  test    rax, rax
0x1400322e5  cmovz   rax, rcx
0x1400322e9  test    rsi, rsi
0x1400322ec  mov     [rbp+140h+var_190], rax
0x1400322f0  mov     rax, [rbp+140h+var_188]
0x1400322f4  cmovz   rsi, rcx
0x1400322f8  test    ebx, ebx
0x1400322fa  mov     [rbp+140h+var_120], rsi
0x1400322fe  mov     ebx, [rdi+108h]
0x140032304  mov     esi, r8d
0x140032307  mov     r8, [rbp+140h+var_160]
0x14003230b  setnz   sil
0x14003230f  movzx   edi, [rbp+140h+var_1C0]
0x140032313  test    rax, rax
0x140032316  cmovz   rax, rcx
0x14003231a  mov     r9, [r8+40h]
0x14003231e  mov     r11d, [r8+268h]
0x140032325  mov     r8, [r8+28h]; int
0x140032329  mov     [rbp+140h+var_188], rax
0x14003232d  mov     rax, [rbp+140h+var_180]
0x140032331  test    rax, rax
0x140032334  cmovz   rax, rcx
0x140032338  mov     [rbp+140h+var_180], rax
0x14003233c  mov     rax, [rbp+140h+var_178]
0x140032340  test    rax, rax
0x140032343  cmovz   rax, rcx
0x140032347  mov     ecx, 1
0x14003234c  mov     [rbp+140h+var_178], rax
0x140032350  mov     rax, [rbp+140h+P]
0x140032354  mov     r10, [rax]
0x140032357  mov     rax, cs:SecData
0x14003235e  lock xadd [rax+150h], rcx
0x140032367  mov     rax, [rbp+140h+var_190]
0x14003236b  inc     rcx; int
0x14003236e  mov     [rsp+320h+var_1C8], rax; wchar_t *
0x140032376  mov     dword ptr [rsp+320h+var_1D0], r14d; char
0x14003237e  mov     dword ptr [rsp+320h+var_1D8], r15d; char
0x140032386  mov     dword ptr [rsp+320h+var_1E0], r12d; char
0x14003238e  mov     dword ptr [rsp+320h+var_1E8], r13d; char
0x140032396  mov     eax, dword ptr [rbp+140h+var_170]
0x140032399  mov     dword ptr [rsp+320h+var_1F0], eax; char
0x1400323a0  mov     rax, qword ptr [rbp+140h+var_140]
0x1400323a4  mov     qword ptr [rsp+320h+var_1F8], rax; char
0x1400323ac  mov     eax, dword ptr [rbp+140h+var_16C]
0x1400323af  mov     dword ptr [rsp+320h+var_200], eax; char
0x1400323b6  mov     rax, qword ptr [rbp+140h+var_138]
0x1400323ba  mov     qword ptr [rsp+320h+var_208], rax; char
0x1400323c2  mov     rax, [rbp+140h+var_130]
0x1400323c6  mov     [rsp+320h+var_210], rax; wchar_t *
0x1400323ce  mov     rax, [rbp+140h+var_148]
0x1400323d2  mov     [rsp+320h+var_218], rax; __int64
0x1400323da  mov     rax, qword ptr [rbp+140h+var_128]
0x1400323de  mov     qword ptr [rsp+320h+var_220], rax; char
0x1400323e6  mov     rax, [rbp+140h+var_120]
0x1400323ea  mov     [rsp+320h+var_228], rax; wchar_t *
0x1400323f2  mov     rax, qword ptr [rbp+140h+var_118]
0x1400323f6  mov     qword ptr [rsp+320h+var_230], rax; char
0x1400323fe  mov     eax, dword ptr [rbp+140h+var_168]
0x140032401  mov     dword ptr [rsp+320h+var_238], eax; char
0x140032408  mov     eax, dword ptr [rbp+140h+var_1A0]
0x14003240b  mov     dword ptr [rsp+320h+var_240], eax; char
0x140032412  mov     al, [rbp+140h+var_1BF]
0x140032415  mov     [rsp+320h+var_248], al; char
0x14003241c  mov     rax, qword ptr [rbp+140h+var_110]
0x140032420  mov     qword ptr [rsp+320h+var_250], rax; char
0x140032428  lea     rax, [rbp+140h+var_AB]
0x14003242f  mov     [rsp+320h+var_258], rax; __int64
0x140032437  mov     rax, qword ptr [rbp+140h+var_108]
0x14003243b  mov     qword ptr [rsp+320h+var_260], rax; char
0x140032443  mov     rax, qword ptr [rbp+140h+var_158]
0x140032447  mov     qword ptr [rsp+320h+var_268], rax; char
0x14003244f  mov     rax, qword ptr [rbp+140h+var_150]
0x140032453  mov     qword ptr [rsp+320h+var_270], rax; char
0x14003245b  mov     eax, dword ptr [rbp+140h+var_198]
0x14003245e  mov     dword ptr [rsp+320h+var_278], eax; char
0x140032465  mov     eax, dword ptr [rbp+140h+var_60]
0x14003246b  mov     dword ptr [rsp+320h+var_280], esi; char
0x140032472  mov     dword ptr [rsp+320h+var_288], edx; char
0x140032479  mov     edx, dword ptr [rbp+140h+var_1B0]; int
0x14003247c  mov     dword ptr [rsp+320h+var_290], ebx; char
0x140032483  mov     dword ptr [rsp+320h+var_298], edi; char
0x14003248a  mov     dword ptr [rsp+320h+var_2A0], eax; char
0x140032491  mov     eax, dword ptr [rbp+140h+var_64]
0x140032497  mov     dword ptr [rsp+320h+var_2A8], eax; char
0x14003249b  mov     eax, dword ptr [rbp+140h+var_68]
0x1400324a1  mov     dword ptr [rsp+320h+var_2B0], eax; char
0x1400324a5  lea     rax, [rbp+140h+var_BB]
0x1400324ac  mov     qword ptr [rsp+320h+var_2B8], rax; __int64
0x1400324b1  lea     rax, [rbp+140h+var_CF]
0x1400324b5  mov     qword ptr [rsp+320h+var_2C0], rax; __int64
0x1400324ba  lea     rax, [rbp+140h+var_EF]
0x1400324be  mov     qword ptr [rsp+320h+var_2C8], rax; __int64
0x1400324c3  mov     rax, [rbp+140h+var_188]
0x1400324c7  mov     [rsp+320h+Str], rax; Str
0x1400324cc  mov     rax, [rbp+140h+var_180]
0x1400324d0  mov     [rsp+320h+var_2D8], rax; __int64
0x1400324d5  mov     rax, [rbp+140h+var_178]
0x1400324d9  mov     [rsp+320h+var_2E0], rax; __int64
0x1400324de  mov     eax, dword ptr [rbp+140h+var_1B8]
0x1400324e1  mov     qword ptr [rsp+320h+var_2E8], r9; char
0x1400324e6  mov     r9d, dword ptr [rbp+140h+var_1A8]; int
0x1400324ea  mov     dword ptr [rsp+320h+var_2F0], eax; char
0x1400324ee  mov     dword ptr [rsp+320h+var_2F8], r11d; char
0x1400324f3  mov     [rsp+320h+Sid], r10; Sid
0x1400324f8  call    EventWriteCreateProcess
0x1400324fd  jmp     loc_14003279A
0x140032502  mov     rbx, qword ptr [rbp+140h+var_1B8]
0x140032506  mov     r12d, [rbx]
0x140032509  call    cs:__imp_PsGetCurrentThreadId
0x140032510  nop     dword ptr [rax+rax+00h]
0x140032515  mov     rcx, [rbx+28h]
0x140032519  mov     r10d, 1
0x14003251f  mov     r8, [rbp+140h+var_160]
0x140032523  mov     r15d, [rbx]
0x140032526  mov     r11, qword ptr [rbp+140h+var_198]
0x14003252a  mov     rsi, qword ptr [rbp+140h+var_1A0]
0x14003252e  mov     r14, [rcx+8]
0x140032532  mov     r13d, [rdi+20h]
0x140032536  mov     rcx, [rbx+8]
0x14003253a  mov     rdi, [rbx+18h]
0x14003253e  mov     ebx, [r8+268h]
0x140032545  mov     rdx, [r8+30h]
0x140032549  mov     r8, [r8+28h]; int
0x14003254d  mov     r11, [r11+8]
0x140032551  mov     rsi, [rsi+8]
0x140032555  mov     [rbp+140h+var_1A8], rax
0x140032559  mov     rax, [rbp+140h+P]
0x14003255d  shr     r15d, 0Ch
0x140032561  and     r15d, 0Fh
0x140032565  shr     r12d, 8
0x140032569  and     r12d, 1
0x14003256d  mov     r9, [rax]
0x140032570  mov     rax, cs:SecData
0x140032577  lock xadd [rax+150h], r10
0x140032580  mov     rax, [rbp+140h+var_148]
0x140032584  mov     qword ptr [rsp+320h+var_270], r14; __int64
0x14003258c  mov     dword ptr [rsp+320h+var_278], r15d; char
0x140032594  mov     [rsp+320h+var_280], r11; wchar_t *
0x14003259c  mov     qword ptr [rsp+320h+var_288], rax; __int64
0x1400325a4  lea     rax, [rbp+140h+var_AB]
0x1400325ab  mov     qword ptr [rsp+320h+var_290], rax; __int64
0x1400325b3  mov     eax, dword ptr [rbp+140h+var_60]
0x1400325b9  mov     qword ptr [rsp+320h+var_298], rdi; char
0x1400325c1  mov     qword ptr [rsp+320h+var_2A0], rdx; char
0x1400325c9  mov     edx, r13d; int
  ... truncated ...
```
