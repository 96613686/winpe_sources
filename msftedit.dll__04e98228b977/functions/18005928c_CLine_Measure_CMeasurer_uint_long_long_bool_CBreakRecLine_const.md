# CLine::Measure(CMeasurer &,uint,long *,long,bool,CBreakRecLine const *)

- ea: `0x18005928c`
- end: `0x1800597a5`
- name: `?Measure@CLine@@QEAAHAEAVCMeasurer@@IPEAJJ_NPEBUCBreakRecLine@@@Z`
- size: `1305`
- prototype: `__int64 __usercall@<rax>(CLine *__hidden this@<rcx>, struct CMeasurer *@<rdx>, unsigned int@<r8d>, int *@<r9>, int, bool, const struct CBreakRecLine *)`
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180049d20`
- `0x18004c5d0`
- `0x18004df98`
- `0x1800bc3d8`

## callees

- `0x18000f260`
- `0x180012270`
- `0x18001668c`
- `0x18003ed40`
- `0x18004f130`
- `0x180057560`
- `0x18005912c`
- `0x180059150`
- `0x18005928c`
- `0x18005a5f8`
- `0x18005abb0`
- `0x1800bd038`
- `0x1800de824`
- `0x18013dcce`
- `0x18013dce6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800595eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800595eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005943d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800595f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005943d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800595f7`

## pseudocode

```c
__int64 __fastcall CLine::Measure(
        CLine *this,
        struct CMeasurer *a2,
        unsigned int a3,
        int *a4,
        int a5,
        bool a6,
        const struct CBreakRecLine *a7)
{
  __int64 v7; // rax
  int v8; // edi
  char *v11; // r13
  __int64 v12; // rcx
  int v13; // edx
  char v14; // si
  _BYTE *v15; // rax
  int v16; // edx
  char v17; // cl
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rsi
  int v28; // edi
  _DWORD *LockTelemetry; // rax
  struct Ptls6::ols *Pols; // rax
  Ptls6::ols *v31; // rdi
  __int16 v32; // ax
  int *v33; // r15
  unsigned int v34; // esi
  int v35; // edi
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rcx
  const struct CParaFormat *PF; // rax
  __int64 v40; // rax
  RTL_SRWLOCK *Lock; // rax
  __int64 v43; // rax
  const struct CParaFormat *v44; // rax
  const struct CParaFormat *v45; // rax
  const struct CParaFormat *v46; // rax
  int v47; // eax
  int Height; // eax
  _QWORD v49[2]; // [rsp+58h] [rbp-41h] BYREF
  bool v50; // [rsp+68h] [rbp-31h]
  char v51; // [rsp+69h] [rbp-30h]
  int v52; // [rsp+70h] [rbp-29h]
  char v53; // [rsp+74h] [rbp-25h]
  BOOL v54; // [rsp+78h] [rbp-21h]
  __int64 v55; // [rsp+80h] [rbp-19h]
  __int128 v56; // [rsp+88h] [rbp-11h]
  __int16 v57; // [rsp+98h] [rbp-1h]
  int v60; // [rsp+110h] [rbp+77h]

  v7 = *((_QWORD *)a2 + 19);
  v8 = a3 & 1;
  if ( (*(_DWORD *)(v7 + 116) & 0x10000) != 0
    && (*(_DWORD *)(*(_QWORD *)(v7 + 16) + 288LL) & 0x200000) == 0
    && (a3 & 1) != 0
    && *((_DWORD *)a2 + 8)
    && CRchTxtPtr::GetPrevUnhiddenChar(a2) == 11 )
  {
    v8 = 0;
  }
  v11 = (char *)a2 + 16;
  v12 = *((_QWORD *)a2 + 2);
  if ( v12 )
    v12 = *(_QWORD *)(v12 + 40);
  v13 = *(_DWORD *)(v12 + 184);
  if ( (v13 & 0x40000000) != 0 )
  {
    v14 = 0x80;
  }
  else if ( (v13 & 0x400000) != 0 || (*(_BYTE *)(v12 + 276) & 0xC0) == 0xC0 )
  {
    v14 = 64;
  }
  else
  {
    v14 = 0;
  }
  *((_BYTE *)a2 + 111) &= 0x1Fu;
  *((_BYTE *)a2 + 111) |= v14;
  memset_0(
    (char *)a2 + 96,
    0,
    4LL * *((unsigned __int8 *)&qword_1802A7F68 + ((unsigned __int64)*((unsigned __int8 *)a2 + 111) >> 5)) + 32);
  *((_BYTE *)a2 + 111) &= 0x1Fu;
  v15 = (char *)a2 + 110;
  *((_BYTE *)a2 + 111) |= v14;
  if ( v8 )
    *v15 |= 2u;
  v16 = *((_DWORD *)a2 + 8);
  v17 = *((_BYTE *)a2 + 277) & 0xBF;
  *(_QWORD *)((char *)a2 + 204) = 0;
  *((_DWORD *)a2 + 58) = -1;
  *((_DWORD *)a2 + 42) = v16;
  if ( v8 )
    *v15 |= 2u;
  *((_BYTE *)a2 + 277) = v17 | 0x20;
  v60 = 0;
  if ( a7 )
  {
    v47 = *((_DWORD *)a7 + 2);
    if ( v47 > 0 )
      v60 = v16 + v47;
  }
  v18 = *(_QWORD *)v11;
  if ( *(_QWORD *)v11 )
    v19 = *(_QWORD *)(v18 + 40);
  else
    v19 = 0;
  if ( (*(_BYTE *)(v19 + 358) & 1) != 0 )
  {
    v49[0] = a2;
    if ( v18 )
      v20 = *(_QWORD *)(v18 + 40);
    else
      v20 = 0;
    v21 = *(_QWORD *)(v20 + 256);
    v50 = 0;
    if ( v21 && (v22 = *(__int64 **)(v21 + 80)) != 0 )
    {
      v50 = (v22[2] & 4) != 0;
      v23 = *v22;
    }
    else
    {
      v23 = 0;
    }
    v49[1] = v23;
    v51 = 0;
    if ( v18 )
      v24 = *(_QWORD *)(v18 + 40);
    else
      v24 = 0;
    v25 = *(_QWORD *)(v24 + 256);
    if ( v25 && (v26 = *(__int64 **)(v25 + 80)) != 0 )
      v27 = *v26;
    else
      v27 = 0;
    v28 = (int)CLockSharedData::LockOwner;
    v52 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v28 == GetCurrentThreadId() )
    {
      LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
      ++*LockTelemetry;
    }
    else
    {
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
      v43 = CLock::GetLockTelemetry(0);
      ++*(_DWORD *)(v43 + 4);
    }
    ++CLSLock::_cOLSBusy;
    v53 = 1;
    v56 = 0;
    g_cFCLock += v27 == 0;
    v55 = 0;
    v57 = 0;
    v54 = v27 == 0;
    Pols = CMeasurerLS::GetPols((CMeasurerLS *)v49);
    v31 = Pols;
    if ( Pols )
    {
      v32 = *((_WORD *)Pols + 526);
      if ( (v32 & 0x20) != 0 && !a7 )
      {
        *((_WORD *)v31 + 526) = v32 & 0xFFDF;
        Ptls6::ols::ClearRunCache(v31);
      }
      v33 = a4;
      v34 = a3;
      v35 = Ptls6::ols::MeasureLine(v31, a3, a4, v60, 1, 0, 0, 0, 0, a7);
      if ( v35 >= 0 )
      {
        CMeasurerLS::~CMeasurerLS((CMeasurerLS *)v49);
        v36 = v35 != 1;
        goto LABEL_34;
      }
    }
    else
    {
      v34 = a3;
      v33 = a4;
    }
    CMeasurerLS::~CMeasurerLS((CMeasurerLS *)v49);
  }
  else
  {
    v34 = a3;
    v33 = a4;
  }
  v36 = CMeasurer::MeasureLine(a2, v34, v33);
LABEL_34:
  if ( !v36 )
    return 0;
  memcpy_0(
    this,
    (char *)a2 + 96,
    4LL * *((unsigned __int8 *)&qword_1802A7F68 + ((unsigned __int64)*((unsigned __int8 *)a2 + 111) >> 5)) + 32);
  if ( (*((_BYTE *)a2 + 277) & 0x10) != 0 )
  {
    Height = CLine::GetHeight(this, 0, 0);
    CLineBasic::SetHeight(this, (Height + 4) & 0xFFFFFFF8);
  }
  v37 = *((_QWORD *)a2 + 19);
  if ( (*(_DWORD *)(v37 + 116) & 0x10000) != 0 && (*(_DWORD *)(*(_QWORD *)(v37 + 16) + 288LL) & 0x200000) == 0 )
  {
    v38 = *(_QWORD *)v11 ? *(_QWORD *)(*(_QWORD *)v11 + 40LL) : 0LL;
    if ( (*(_BYTE *)(v38 + 176) & 1) != 0 )
    {
      PF = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
      if ( !PF )
        PF = CRchTxtPtr::GetPF(a2);
      if ( *((__int16 *)PF + 16) <= -2 )
      {
        v44 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
        if ( !v44 )
          v44 = CRchTxtPtr::GetPF(a2);
        if ( *((__int16 *)v44 + 16) >= -10 )
        {
          v45 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
          if ( !v45 )
            v45 = CRchTxtPtr::GetPF(a2);
          *((_BYTE *)this + 13) ^= (*((_BYTE *)this + 13) ^ ~*((_BYTE *)v45 + 32)) & 0xF;
        }
      }
      v40 = *(_QWORD *)v11;
      if ( *(_QWORD *)v11 )
        v40 = *(_QWORD *)(v40 + 40);
      if ( *(__int16 *)(v40 + 276) < 0 )
      {
        v46 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
        if ( !v46 )
          v46 = CRchTxtPtr::GetPF(a2);
        if ( (*(_DWORD *)v46 & 0x100) != 0 )
          *((_BYTE *)this + 13) |= 0x10u;
      }
      if ( CTxtPtr::GetPrevChar((struct CMeasurer *)((char *)a2 + 16)) == 12 )
        *((_BYTE *)this + 13) |= 0x40u;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18005928c  mov     rax, rsp
0x18005928f  mov     [rax+8], rbx
0x180059293  mov     [rax+20h], r9
0x180059297  mov     [rax+18h], r8d
0x18005929b  push    rbp
0x18005929c  push    rsi
0x18005929d  push    rdi
0x18005929e  push    r12
0x1800592a0  push    r13
0x1800592a2  push    r14
0x1800592a4  push    r15
0x1800592a6  lea     rbp, [rax-47h]
0x1800592aa  sub     rsp, 0A0h
0x1800592b1  mov     rax, [rdx+98h]
0x1800592b8  mov     edi, r8d
0x1800592bb  and     edi, 1
0x1800592be  mov     rbx, rdx
0x1800592c1  mov     r14, rcx
0x1800592c4  test    dword ptr [rax+74h], 10000h
0x1800592cb  jz      short loc_1800592E1
0x1800592cd  mov     rax, [rax+10h]
0x1800592d1  test    dword ptr [rax+120h], 200000h
0x1800592db  jz      loc_180059618
0x1800592e1  lea     r13, [rbx+10h]
0x1800592e5  mov     rcx, [r13+0]
0x1800592e9  test    rcx, rcx
0x1800592ec  jz      short loc_1800592F2
0x1800592ee  mov     rcx, [rcx+28h]
0x1800592f2  mov     edx, [rcx+0B8h]
0x1800592f8  mov     eax, edx
0x1800592fa  shr     eax, 1Eh
0x1800592fd  test    al, 1
0x1800592ff  jnz     loc_180059700
0x180059305  bt      edx, 16h
0x180059309  jb      loc_180059708
0x18005930f  mov     al, [rcx+114h]
0x180059315  and     al, 0C0h
0x180059317  cmp     al, 0C0h
0x180059319  jz      loc_180059708
0x18005931f  xor     sil, sil
0x180059322  and     byte ptr [rbx+6Fh], 1Fh
0x180059326  lea     rcx, qword_1802A7F68
0x18005932d  or      [rbx+6Fh], sil
0x180059331  xor     edx, edx; Val
0x180059333  movzx   eax, byte ptr [rbx+6Fh]
0x180059337  shr     rax, 5
0x18005933b  movzx   r8d, byte ptr [rax+rcx]
0x180059340  lea     rcx, [rbx+60h]; void *
0x180059344  lea     r8, ds:20h[r8*4]; Size
0x18005934c  call    memset_0
0x180059351  and     byte ptr [rbx+6Fh], 1Fh
0x180059355  lea     rax, [rbx+6Eh]
0x180059359  or      [rbx+6Fh], sil
0x18005935d  xor     r9d, r9d
0x180059360  test    edi, edi
0x180059362  jz      short loc_180059367
0x180059364  or      byte ptr [rax], 2
0x180059367  mov     cl, [rbx+115h]
0x18005936d  mov     edx, [rbx+20h]
0x180059370  and     cl, 0BFh
0x180059373  mov     [rbx+0CCh], r9
0x18005937a  mov     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x180059384  mov     [rbx+0A8h], edx
0x18005938a  test    edi, edi
0x18005938c  jz      short loc_180059391
0x18005938e  or      byte ptr [rax], 2
0x180059391  mov     r15, [rbp+3Fh+arg_30]
0x180059395  or      cl, 20h
0x180059398  mov     [rbx+115h], cl
0x18005939e  mov     dword ptr [rbp+3Fh+arg_28], r9d
0x1800593a2  test    r15, r15
0x1800593a5  jnz     loc_180059710
0x1800593ab  mov     r8, [r13+0]
0x1800593af  test    r8, r8
0x1800593b2  jz      loc_180059669
0x1800593b8  mov     rax, [r8+28h]
0x1800593bc  test    byte ptr [rax+166h], 1
0x1800593c3  jz      loc_180059643
0x1800593c9  mov     [rbp+3Fh+var_80], rbx
0x1800593cd  test    r8, r8
0x1800593d0  jz      loc_180059671
0x1800593d6  mov     rax, [r8+28h]
0x1800593da  mov     rdx, [rax+100h]
0x1800593e1  mov     [rbp+3Fh+var_70], r9b
0x1800593e5  test    rdx, rdx
0x1800593e8  jz      short loc_1800593F7
0x1800593ea  mov     rdx, [rdx+50h]
0x1800593ee  test    rdx, rdx
0x1800593f1  jnz     loc_180059726
0x1800593f7  mov     rax, r9
0x1800593fa  mov     [rbp+3Fh+var_78], rax
0x1800593fe  mov     [rbp+3Fh+var_6F], r9b
0x180059402  test    r8, r8
0x180059405  jz      loc_180059679
0x18005940b  mov     rax, [r8+28h]
0x18005940f  mov     rcx, [rax+100h]
0x180059416  test    rcx, rcx
0x180059419  jz      short loc_180059428
0x18005941b  mov     rax, [rcx+50h]
0x18005941f  test    rax, rax
0x180059422  jnz     loc_180059739
0x180059428  mov     rsi, r9
0x18005942b  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180059431  mov     [rbp+3Fh+var_68], r9d
0x180059435  test    edi, edi
0x180059437  jz      loc_1800595E1
0x18005943d  call    cs:__imp_GetCurrentThreadId
0x180059444  nop     dword ptr [rax+rax+00h]
0x180059449  cmp     edi, eax
0x18005944b  jnz     loc_1800595E1
0x180059451  xor     ecx, ecx
0x180059453  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180059458  inc     dword ptr [rax]
0x18005945a  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x180059460  lea     rcx, [rbp+3Fh+var_80]; this
0x180059464  xor     eax, eax
0x180059466  mov     [rbp+3Fh+var_64], 1
0x18005946a  test    rsi, rsi
0x18005946d  xorps   xmm0, xmm0
0x180059470  movdqa  [rbp+3Fh+var_50], xmm0
0x180059475  setz    al
0x180059478  xor     esi, esi
0x18005947a  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x180059480  mov     [rbp+3Fh+var_58], rsi
0x180059484  mov     [rbp+3Fh+var_40], si
0x180059488  mov     [rbp+3Fh+var_60], eax
0x18005948b  call    ?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ; CMeasurerLS::GetPols(void)
0x180059490  mov     rdi, rax
0x180059493  test    rax, rax
0x180059496  jz      loc_180059766
0x18005949c  movzx   eax, word ptr [rax+41Ch]
0x1800594a3  test    al, 20h
0x1800594a5  jnz     loc_180059741
0x1800594ab  mov     r9d, dword ptr [rbp+3Fh+arg_28]; int
0x1800594af  mov     rcx, rdi; this
0x1800594b2  mov     [rsp+48h], r15; struct CBreakRecLine *
0x1800594b7  mov     r15, [rbp+3Fh+arg_18]
0x1800594bb  mov     [rsp+0D0h+var_90], rsi; int *
0x1800594c0  mov     r8, r15; int *
0x1800594c3  mov     [rsp+0D0h+var_98], rsi; int *
0x1800594c8  mov     [rsp+0D0h+var_A0], sil; bool
0x1800594cd  mov     [rsp+0D0h+var_A8], sil; bool
0x1800594d2  mov     esi, [rbp+3Fh+arg_10]
0x1800594d5  mov     edx, esi; unsigned int
0x1800594d7  mov     [rsp+0D0h+var_B0], 1; bool
0x1800594dc  call    ?MeasureLine@ols@Ptls6@@QEAAJIPEAJJ_N1100PEBUCBreakRecLine@@@Z; Ptls6::ols::MeasureLine(uint,long *,long,bool,bool,bool,long *,long *,CBreakRecLine const *)
0x1800594e1  mov     edi, eax
0x1800594e3  test    eax, eax
0x1800594e5  js      loc_18005976D
0x1800594eb  lea     rcx, [rbp+3Fh+var_80]; this
0x1800594ef  call    ??1CMeasurerLS@@QEAA@XZ; CMeasurerLS::~CMeasurerLS(void)
0x1800594f4  xor     eax, eax
0x1800594f6  cmp     edi, 1
0x1800594f9  setnz   al
0x1800594fc  test    eax, eax
0x1800594fe  jz      loc_180059688
0x180059504  movzx   eax, byte ptr [rbx+6Fh]
0x180059508  lea     rcx, qword_1802A7F68
0x18005950f  shr     rax, 5
0x180059513  lea     rdx, [rbx+60h]; Src
0x180059517  movzx   r8d, byte ptr [rax+rcx]
0x18005951c  mov     rcx, r14; void *
0x18005951f  lea     r8, ds:20h[r8*4]; Size
0x180059527  call    memcpy_0
0x18005952c  test    byte ptr [rbx+115h], 10h
0x180059533  jnz     loc_18005977B
0x180059539  mov     rax, [rbx+98h]
0x180059540  test    dword ptr [rax+74h], 10000h
0x180059547  jz      short loc_1800595C0
0x180059549  mov     rax, [rax+10h]
0x18005954d  test    dword ptr [rax+120h], 200000h
0x180059557  jnz     short loc_1800595C0
0x180059559  mov     rax, [r13+0]
0x18005955d  test    rax, rax
0x180059560  jz      loc_180059681
0x180059566  mov     rcx, [rax+28h]
0x18005956a  test    byte ptr [rcx+0B0h], 1
0x180059571  jz      short loc_1800595C0
0x180059573  mov     rax, [rbx+128h]
0x18005957a  test    rax, rax
0x18005957d  jz      loc_18005965C
0x180059583  cmp     word ptr [rax+20h], 0FFFEh
0x180059588  jle     loc_18005968F
0x18005958e  mov     rax, [r13+0]
0x180059592  test    rax, rax
0x180059595  jz      short loc_18005959B
0x180059597  mov     rax, [rax+28h]
0x18005959b  movzx   eax, word ptr [rax+114h]
0x1800595a2  shr     ax, 0Fh
0x1800595a6  test    al, al
0x1800595a8  jnz     loc_1800596D6
0x1800595ae  mov     rcx, r13; this
0x1800595b1  call    ?GetPrevChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetPrevChar(void)
0x1800595b6  cmp     ax, 0Ch
0x1800595ba  jz      loc_18005979B
0x1800595c0  mov     eax, 1
0x1800595c5  mov     rbx, [rsp+0D0h+arg_0]
0x1800595cd  add     rsp, 0A0h
0x1800595d4  pop     r15
0x1800595d6  pop     r14
0x1800595d8  pop     r13
0x1800595da  pop     r12
0x1800595dc  pop     rdi
0x1800595dd  pop     rsi
0x1800595de  pop     rbp
0x1800595df  retn
0x1800595e1  xor     ecx, ecx
0x1800595e3  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800595e8  mov     rcx, rax; SRWLock
0x1800595eb  call    cs:__imp_AcquireSRWLockExclusive
0x1800595f2  nop     dword ptr [rax+rax+00h]
0x1800595f7  call    cs:__imp_GetCurrentThreadId
0x1800595fe  nop     dword ptr [rax+rax+00h]
0x180059603  xor     ecx, ecx
0x180059605  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18005960b  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180059610  inc     dword ptr [rax+4]
0x180059613  jmp     loc_18005945A
0x180059618  test    edi, edi
0x18005961a  jz      loc_1800592E1
0x180059620  cmp     dword ptr [rdx+20h], 0
0x180059624  jz      loc_1800592E1
0x18005962a  mov     rcx, rbx; this
0x18005962d  call    ?GetPrevUnhiddenChar@CRchTxtPtr@@QEAAGXZ; CRchTxtPtr::GetPrevUnhiddenChar(void)
0x180059632  movzx   ecx, ax
0x180059635  xor     eax, eax
0x180059637  cmp     cx, 0Bh
0x18005963b  cmovz   edi, eax
0x18005963e  jmp     loc_1800592E1
0x180059643  mov     esi, [rbp+3Fh+arg_10]
0x180059646  mov     r15, [rbp+3Fh+arg_18]
0x18005964a  mov     r8, r15; int *
0x18005964d  mov     edx, esi; unsigned int
0x18005964f  mov     rcx, rbx; this
0x180059652  call    ?MeasureLine@CMeasurer@@QEAAHIPEAJ@Z; CMeasurer::MeasureLine(uint,long *)
0x180059657  jmp     loc_1800594FC
0x18005965c  mov     rcx, rbx; this
0x18005965f  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180059664  jmp     loc_180059583
0x180059669  mov     rax, r9
0x18005966c  jmp     loc_1800593BC
0x180059671  mov     rax, r9
0x180059674  jmp     loc_1800593DA
0x180059679  mov     rax, r9
0x18005967c  jmp     loc_18005940F
0x180059681  xor     ecx, ecx
0x180059683  jmp     loc_18005956A
0x180059688  xor     eax, eax
0x18005968a  jmp     loc_1800595C5
0x18005968f  mov     rax, [rbx+128h]
0x180059696  test    rax, rax
0x180059699  jnz     short loc_1800596A3
0x18005969b  mov     rcx, rbx; this
0x18005969e  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1800596a3  cmp     word ptr [rax+20h], 0FFF6h
0x1800596a8  jl      loc_18005958E
0x1800596ae  mov     rax, [rbx+128h]
0x1800596b5  test    rax, rax
0x1800596b8  jnz     short loc_1800596C2
0x1800596ba  mov     rcx, rbx; this
0x1800596bd  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1800596c2  mov     al, [rax+20h]
0x1800596c5  not     al
0x1800596c7  xor     al, [r14+0Dh]
0x1800596cb  and     al, 0Fh
0x1800596cd  xor     [r14+0Dh], al
0x1800596d1  jmp     loc_18005958E
0x1800596d6  mov     rax, [rbx+128h]
0x1800596dd  test    rax, rax
0x1800596e0  jnz     short loc_1800596EA
0x1800596e2  mov     rcx, rbx; this
0x1800596e5  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1800596ea  test    dword ptr [rax], 100h
0x1800596f0  jz      loc_1800595AE
0x1800596f6  or      byte ptr [r14+0Dh], 10h
0x1800596fb  jmp     loc_1800595AE
0x180059700  mov     sil, 80h
0x180059703  jmp     loc_180059322
0x180059708  mov     sil, 40h ; '@'
0x18005970b  jmp     loc_180059322
0x180059710  mov     eax, [r15+8]
0x180059714  test    eax, eax
0x180059716  jle     loc_1800593AB
0x18005971c  add     eax, edx
0x18005971e  mov     dword ptr [rbp+3Fh+arg_28], eax
0x180059721  jmp     loc_1800593AB
0x180059726  mov     eax, [rdx+10h]
0x180059729  shr     eax, 2
0x18005972c  and     al, 1
0x18005972e  mov     [rbp+3Fh+var_70], al
0x180059731  mov     rax, [rdx]
0x180059734  jmp     loc_1800593FA
0x180059739  mov     rsi, [rax]
0x18005973c  jmp     loc_18005942B
0x180059741  test    r15, r15
0x180059744  jnz     loc_1800594AB
0x18005974a  mov     ecx, 0FFDFh
0x18005974f  and     ax, cx
0x180059752  mov     rcx, rdi; this
0x180059755  mov     [rdi+41Ch], ax
  ... truncated ...
```
