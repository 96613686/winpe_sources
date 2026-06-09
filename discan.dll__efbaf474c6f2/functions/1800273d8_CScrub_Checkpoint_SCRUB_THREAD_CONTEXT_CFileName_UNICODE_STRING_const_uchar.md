# CScrub::_Checkpoint(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,uchar)

- ea: `0x1800273d8`
- end: `0x180027792`
- name: `?_Checkpoint@CScrub@@AEAAXPEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU_UNICODE_STRING@@E@Z`
- size: `954`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct _SCRUB_THREAD_CONTEXT *, struct CFileName *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022450`
- `0x180024b24`
- `0x180029210`
- `0x18002a2e0`

## callees

- `0x1800032f8`
- `0x180006470`
- `0x180006688`
- `0x180012048`
- `0x1800137d4`
- `0x180017588`
- `0x180017a80`
- `0x180021db4`
- `0x180027184`
- `0x1800273d8`
- `0x180027858`
- `0x1800375ee`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18002749e`
- `KERNEL32!GetTickCount64` at `0x18002749e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800274fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027678`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800274fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027678`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800274e3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027551`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800274e3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027551`

## pseudocode

```c
void __fastcall CScrub::_Checkpoint(
        RTL_SRWLOCK *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        struct CFileName *a3,
        const struct _UNICODE_STRING *a4,
        unsigned __int8 a5)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v10; // rdx
  USHORT v11; // dx
  USHORT v12; // ax
  ULONGLONG TickCount64; // rax
  unsigned __int64 v14; // r14
  _QWORD *Ptr; // rdi
  unsigned __int64 v16; // r8
  _DWORD *v17; // r11
  unsigned __int64 v18; // r9
  _QWORD *v19; // r10
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r8
  unsigned int v24; // eax
  unsigned __int64 v25; // rdx
  const struct _UNICODE_STRING *FullPathName; // rbx
  struct _UNICODE_STRING *v27; // [rsp+20h] [rbp-48h]
  RTL_SRWLOCK *v28[2]; // [rsp+40h] [rbp-28h] BYREF
  const struct _UNICODE_STRING *v29; // [rsp+50h] [rbp-18h] BYREF
  int v30; // [rsp+58h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v29 = &stru_18003EFB0;
  Length = GlobalIndentString.Length;
  v30 = 0;
  v10 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v10 + 16) = &stru_18003EFB0;
  v11 = ++*(_WORD *)(v10 + 8);
  v12 = Length;
  if ( v11 < Length )
  {
    v12 = v11;
    Length = v11;
  }
  LOWORD(v28[0]) = v12;
  HIDWORD(v28[0]) = 0;
  v28[1] = (RTL_SRWLOCK *)off_180047060;
  WORD1(v28[0]) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&stru_18003EFB0);
  }
  TickCount64 = GetTickCount64();
  v14 = TickCount64;
  if ( a5 || TickCount64 >= *((_QWORD *)a2 + 207) + 30000LL )
  {
    *((_QWORD *)a2 + 185) = TickCount64 - (unsigned __int64)this[166].Ptr;
    AcquireSRWLockExclusive(this + 162);
    CScrubCheckpoint::AccumulateStats(
      (struct _SCRUB_THREAD_CONTEXT *)((char *)a2 + 1480),
      (struct _SCRUB_CHECKPOINT_STATS *)((char *)this[163].Ptr + 16));
    ReleaseSRWLockExclusive(this + 162);
    v28[0] = 0;
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(v28);
    memset_0((char *)a2 + 1480, 0, 0xB0u);
    *((_QWORD *)a2 + 207) = v14;
    if ( !BYTE1(this[187].Ptr) || (HIDWORD(this[157].Ptr) & 0x20000000) == 0 )
    {
LABEL_31:
      if ( a5 || a3 )
      {
        FullPathName = 0;
        if ( !a3 || (FullPathName = CScrub::_GetFullPathName((CScrub *)this, a2, a3, a4, v27)) != 0 )
        {
          if ( (BYTE4(this[157].Ptr) & 0x10) == 0 )
          {
            v30 = CScrubCheckpoint::WriteCheckpoint((CScrubCheckpoint *)&this[158], FullPathName);
            if ( v30 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DDZZd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
                *((_QWORD *)this->Ptr + 8),
                (__int64)FullPathName,
                v30);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_efaeeb0993ed33c3273434515202503b_Traceguids);
        }
      }
      goto LABEL_45;
    }
    Ptr = this[163].Ptr;
    AcquireSRWLockExclusive(this + 162);
    v16 = Ptr[12];
    if ( !v16 )
    {
LABEL_30:
      ReleaseSRWLockExclusive(this + 162);
      v28[0] = 0;
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(v28);
      goto LABEL_31;
    }
    v17 = this[1].Ptr;
    if ( v17[2] || *v17 != 1 )
    {
      v21 = 100LL * Ptr[10] / v16;
    }
    else
    {
      v18 = Ptr[13];
      v19 = Ptr + 10;
      if ( v18 > ~v16 || (v20 = Ptr[11], v20 > 0x28F5C28F5C28F5CLL - *v19) )
      {
        v22 = 0;
        v23 = v18 / 0x64 + v16 / 0x64;
        if ( !v23 )
        {
LABEL_25:
          v25 = *((unsigned __int16 *)Ptr + 92);
          if ( v25 + 10 <= v22 || Ptr[14] + (unsigned __int64)(unsigned int)v17[12] <= v14 )
          {
            if ( v25 > v22 )
              LOWORD(v22) = *((_WORD *)Ptr + 92);
            CScrubCheckpoint::UpdatePercentComplete((CScrubCheckpoint *)&this[158], v22);
            CScrub::LogLastVolumeScrubResult((CScrub *)this, 0, 1u);
          }
          goto LABEL_30;
        }
        v22 = *v19 / v23 + Ptr[11] / v23;
LABEL_21:
        if ( v22 >= 0x64 )
        {
          v24 = 99;
          if ( (unsigned int)*((unsigned __int16 *)Ptr + 92) + 10 < 0x63 )
            v24 = *((unsigned __int16 *)Ptr + 92) + 10;
          v22 = v24;
        }
        goto LABEL_25;
      }
      v21 = 100 * (v20 + *v19) / (v18 + v16);
    }
    v22 = v21;
    goto LABEL_21;
  }
LABEL_45:
  CHResultImp::~CHResultImp((CHResultImp *)&v29);
}

```

## disassembly

```asm
0x1800273d8  mov     [rsp-40h+arg_18], r9
0x1800273dd  push    rbp
0x1800273de  push    rbx
0x1800273df  push    rsi
0x1800273e0  push    rdi
0x1800273e1  push    r12
0x1800273e3  push    r13
0x1800273e5  push    r14
0x1800273e7  push    r15
0x1800273e9  mov     rbp, rsp
0x1800273ec  sub     rsp, 68h
0x1800273f0  mov     rax, gs:58h
0x1800273f9  lea     r9, stru_18003EFB0
0x180027400  mov     r10d, cs:_tls_index
0x180027407  mov     r13, rdx
0x18002740a  mov     rsi, rcx
0x18002740d  mov     [rbp+var_18], r9
0x180027411  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180027418  mov     r12, r8
0x18002741b  mov     r8d, 1
0x180027421  mov     [rbp+var_10], 0
0x180027428  mov     rdx, [rax+r10*8]
0x18002742c  mov     eax, 10h
0x180027431  mov     [rax+rdx], r9
0x180027435  mov     eax, 8
0x18002743a  add     [rax+rdx], r8w
0x18002743f  movzx   edx, word ptr [rax+rdx]
0x180027443  movzx   eax, cx
0x180027446  cmp     dx, cx
0x180027449  cmovb   ax, dx
0x18002744d  cmovb   cx, dx
0x180027451  mov     word ptr [rbp+var_28], ax
0x180027455  xor     eax, eax
0x180027457  mov     dword ptr [rbp+var_28+4], eax
0x18002745a  mov     rax, cs:off_180047060; "                                       "...
0x180027461  mov     [rbp+var_20], rax
0x180027465  mov     word ptr [rbp+var_28+2], cx
0x180027469  mov     rcx, cs:WPP_GLOBAL_Control
0x180027470  lea     rax, WPP_GLOBAL_Control
0x180027477  cmp     rcx, rax
0x18002747a  jz      short loc_18002749E
0x18002747c  test    [rcx+1Ch], r8b
0x180027480  jz      short loc_18002749E
0x180027482  cmp     byte ptr [rcx+19h], 5
0x180027486  jb      short loc_18002749E
0x180027488  mov     rcx, [rcx+10h]; LoggerHandle
0x18002748c  lea     edx, [r8+0Ch]
0x180027490  mov     [rsp+68h+var_48], r9; struct _UNICODE_STRING *
0x180027495  lea     r9, [rbp+var_28]
0x180027499  call    WPP_SF_aZs
0x18002749e  call    cs:__imp_GetTickCount64
0x1800274a4  cmp     [rbp+arg_20], 0
0x1800274a8  mov     r14, rax
0x1800274ab  jnz     short loc_1800274C4
0x1800274ad  mov     rcx, [r13+678h]
0x1800274b4  add     rcx, 7530h
0x1800274bb  cmp     rax, rcx
0x1800274be  jb      loc_180027778
0x1800274c4  sub     rax, [rsi+530h]
0x1800274cb  lea     r15, [rsi+4F0h]
0x1800274d2  lea     rbx, [r15+20h]
0x1800274d6  lea     rdi, [r13+5C8h]
0x1800274dd  mov     rcx, rbx; SRWLock
0x1800274e0  mov     [rdi], rax
0x1800274e3  call    cs:__imp_AcquireSRWLockExclusive
0x1800274e9  mov     rdx, [r15+28h]
0x1800274ed  mov     rcx, rdi; struct _SCRUB_CHECKPOINT_STATS *
0x1800274f0  add     rdx, 10h; struct _SCRUB_CHECKPOINT_STATS *
0x1800274f4  call    ?AccumulateStats@CScrubCheckpoint@@SAXPEBU_SCRUB_CHECKPOINT_STATS@@PEAU2@@Z; CScrubCheckpoint::AccumulateStats(_SCRUB_CHECKPOINT_STATS const *,_SCRUB_CHECKPOINT_STATS *)
0x1800274f9  mov     rcx, rbx; SRWLock
0x1800274fc  call    cs:__imp_ReleaseSRWLockExclusive
0x180027502  lea     rcx, [rbp+var_28]; this
0x180027506  mov     [rbp+var_28], 0
0x18002750e  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180027513  xor     edx, edx; Val
0x180027515  mov     r8d, 0B0h; Size
0x18002751b  mov     rcx, rdi; void *
0x18002751e  call    memset_0
0x180027523  mov     [r13+678h], r14
0x18002752a  cmp     byte ptr [rsi+5D9h], 0
0x180027531  jz      loc_18002768F
0x180027537  test    dword ptr [rsi+4ECh], 20000000h
0x180027541  jz      loc_18002768F
0x180027547  mov     rdi, [rsi+518h]
0x18002754e  mov     rcx, rbx; SRWLock
0x180027551  call    cs:__imp_AcquireSRWLockExclusive
0x180027557  mov     r8, [rdi+60h]
0x18002755b  test    r8, r8
0x18002755e  jz      loc_180027675
0x180027564  mov     r11, [rsi+8]
0x180027568  cmp     dword ptr [r11+8], 0
0x18002756d  jnz     loc_180027610
0x180027573  cmp     dword ptr [r11], 1
0x180027577  jnz     loc_180027610
0x18002757d  mov     r9, [rdi+68h]
0x180027581  lea     r10, [rdi+50h]
0x180027585  mov     rax, r8
0x180027588  not     rax
0x18002758b  cmp     r9, rax
0x18002758e  ja      short loc_1800275BC
0x180027590  mov     rcx, [r10]
0x180027593  mov     rax, 28F5C28F5C28F5Ch
0x18002759d  mov     rdx, [rdi+58h]
0x1800275a1  sub     rax, rcx
0x1800275a4  cmp     rdx, rax
0x1800275a7  ja      short loc_1800275BC
0x1800275a9  lea     rax, [rdx+rcx]
0x1800275ad  xor     edx, edx
0x1800275af  imul    rax, 64h ; 'd'
0x1800275b3  lea     rcx, [r9+r8]
0x1800275b7  div     rcx
0x1800275ba  jmp     short loc_18002761A
0x1800275bc  mov     rax, 47AE147AE147AE15h
0x1800275c6  xor     ecx, ecx
0x1800275c8  mul     r9
0x1800275cb  mov     rax, 47AE147AE147AE15h
0x1800275d5  sub     r9, rdx
0x1800275d8  shr     r9, 1
0x1800275db  add     r9, rdx
0x1800275de  mul     r8
0x1800275e1  shr     r9, 6
0x1800275e5  sub     r8, rdx
0x1800275e8  shr     r8, 1
0x1800275eb  add     r8, rdx
0x1800275ee  shr     r8, 6
0x1800275f2  add     r8, r9
0x1800275f5  jz      short loc_180027639
0x1800275f7  mov     rax, [rdi+58h]
0x1800275fb  xor     edx, edx
0x1800275fd  div     r8
0x180027600  xor     edx, edx
0x180027602  mov     rcx, rax
0x180027605  mov     rax, [r10]
0x180027608  div     r8
0x18002760b  add     rcx, rax
0x18002760e  jmp     short loc_18002761D
0x180027610  imul    rax, [rdi+50h], 64h ; 'd'
0x180027615  xor     edx, edx
0x180027617  div     r8
0x18002761a  mov     rcx, rax
0x18002761d  cmp     rcx, 64h ; 'd'
0x180027621  jb      short loc_180027639
0x180027623  movzx   ecx, word ptr [rdi+0B8h]
0x18002762a  mov     eax, 63h ; 'c'
0x18002762f  add     ecx, 0Ah
0x180027632  cmp     ecx, eax
0x180027634  cmovb   eax, ecx
0x180027637  mov     ecx, eax
0x180027639  movzx   edx, word ptr [rdi+0B8h]
0x180027640  lea     rax, [rdx+0Ah]
0x180027644  cmp     rax, rcx
0x180027647  jbe     short loc_180027656
0x180027649  mov     eax, [r11+30h]
0x18002764d  add     rax, [rdi+70h]
0x180027651  cmp     rax, r14
0x180027654  ja      short loc_180027675
0x180027656  cmp     rdx, rcx
0x180027659  cmova   rcx, rdx
0x18002765d  movzx   edx, cx; unsigned __int16
0x180027660  mov     rcx, r15; this
0x180027663  call    ?UpdatePercentComplete@CScrubCheckpoint@@QEAAXG@Z; CScrubCheckpoint::UpdatePercentComplete(ushort)
0x180027668  mov     r8b, 1; unsigned __int8
0x18002766b  xor     edx, edx; int
0x18002766d  mov     rcx, rsi; this
0x180027670  call    ?LogLastVolumeScrubResult@CScrub@@QEAAXJE@Z; CScrub::LogLastVolumeScrubResult(long,uchar)
0x180027675  mov     rcx, rbx; SRWLock
0x180027678  call    cs:__imp_ReleaseSRWLockExclusive
0x18002767e  lea     rcx, [rbp+var_28]; this
0x180027682  mov     [rbp+var_28], 0
0x18002768a  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x18002768f  cmp     [rbp+arg_20], 0
0x180027693  jnz     short loc_18002769E
0x180027695  test    r12, r12
0x180027698  jz      loc_180027778
0x18002769e  xor     ebx, ebx
0x1800276a0  test    r12, r12
0x1800276a3  jz      short loc_180027701
0x1800276a5  mov     r9, [rbp+arg_18]; struct _UNICODE_STRING *
0x1800276a9  mov     r8, r12; struct CFileName *
0x1800276ac  mov     rdx, r13; struct _SCRUB_THREAD_CONTEXT *
0x1800276af  mov     rcx, rsi; this
0x1800276b2  call    ?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z; CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800276b7  mov     rbx, rax
0x1800276ba  test    rax, rax
0x1800276bd  jnz     short loc_180027701
0x1800276bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276c6  lea     rax, WPP_GLOBAL_Control
0x1800276cd  cmp     rcx, rax
0x1800276d0  jz      loc_180027778
0x1800276d6  test    byte ptr [rcx+1Ch], 1
0x1800276da  jz      loc_180027778
0x1800276e0  cmp     byte ptr [rcx+19h], 2
0x1800276e4  jb      loc_180027778
0x1800276ea  mov     rcx, [rcx+10h]
0x1800276ee  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x1800276f5  mov     edx, 0BAh
0x1800276fa  call    WPP_SF_
0x1800276ff  jmp     short loc_180027778
0x180027701  test    byte ptr [rsi+4ECh], 10h
0x180027708  jnz     short loc_180027778
0x18002770a  mov     rdx, rbx; struct _UNICODE_STRING *
0x18002770d  mov     rcx, r15; this
0x180027710  call    ?WriteCheckpoint@CScrubCheckpoint@@QEAAJPEBU_UNICODE_STRING@@@Z; CScrubCheckpoint::WriteCheckpoint(_UNICODE_STRING const *)
0x180027715  mov     [rbp+var_10], eax
0x180027718  mov     r8d, eax
0x18002771b  test    eax, eax
0x18002771d  jns     short loc_180027778
0x18002771f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027726  lea     rax, WPP_GLOBAL_Control
0x18002772d  cmp     rcx, rax
0x180027730  jz      short loc_180027778
0x180027732  test    byte ptr [rcx+1Ch], 1
0x180027736  jz      short loc_180027778
0x180027738  cmp     byte ptr [rcx+19h], 2
0x18002773c  jb      short loc_180027778
0x18002773e  mov     rax, [rsi]
0x180027741  mov     edx, 0BBh
0x180027746  mov     rcx, [rcx+10h]; LoggerHandle
0x18002774a  mov     dword ptr [rsp+68h+var_30], r8d; char
0x18002774f  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180027756  mov     [rsp+68h+var_38], rbx; __int64
0x18002775b  mov     r9, [rax]
0x18002775e  mov     rax, [rax+40h]
0x180027762  mov     [rsp+68h+var_40], rax; __int64
0x180027767  mov     eax, [r9+24h]
0x18002776b  mov     r9d, [r9+10h]
0x18002776f  mov     dword ptr [rsp+68h+var_48], eax; char
0x180027773  call    WPP_SF_DDZZd
0x180027778  lea     rcx, [rbp+var_18]; this
0x18002777c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180027781  add     rsp, 68h
0x180027785  pop     r15
0x180027787  pop     r14
0x180027789  pop     r13
0x18002778b  pop     r12
0x18002778d  pop     rdi
0x18002778e  pop     rsi
0x18002778f  pop     rbx
0x180027790  pop     rbp
0x180027791  retn
```
