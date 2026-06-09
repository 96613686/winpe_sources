# HamConnector::AddExemptionForProcess(ulong,void *,bool)

- ea: `0x18002539c`
- end: `0x18002578f`
- name: `?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z`
- size: `1011`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, DWORD dwProcessId, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180014c34`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x1800028ec`
- `0x180003474`
- `0x180009f00`
- `0x180009f40`
- `0x18002539c`
- `0x180025b5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025464`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002550a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025580`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002550a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025580`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800255e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800255e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002575c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002575c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025452`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025452`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x1800253fe`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x1800253fe`
- `RMCLIENT!HamCreateActivityForProcess` at `0x18002559e`
- `RMCLIENT!HamCreateActivityForProcess` at `0x18002559e`
- `RMCLIENT!HamStartActivityAsync` at `0x180025689`
- `RMCLIENT!HamStartActivityAsync` at `0x180025689`

## pseudocode

```c
__int64 __fastcall HamConnector::AddExemptionForProcess(
        PSRWLOCK SRWLock,
        DWORD dwProcessId,
        void *a3,
        unsigned __int8 a4)
{
  RTL_SRWLOCK *v8; // r12
  int v9; // edi
  char *v10; // rbx
  unsigned int v11; // edi
  signed int LastError; // eax
  RTL_SRWLOCK *v13; // r14
  PVOID Ptr; // rax
  PSRWLOCK v15; // rsi
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rax
  int ActivityForProcess; // edi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  char *v23; // rax
  char *v24; // rcx
  PVOID v25; // r13
  _BYTE *v26; // rdi
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  char *v29; // r9
  void **v30; // rdx
  void *v31; // rax
  RTL_SRWLOCK *v34; // [rsp+38h] [rbp-1E0h] BYREF
  _BYTE v35[400]; // [rsp+40h] [rbp-1D8h] BYREF

  v8 = 0;
  memset_0(v35, 0, 0x188u);
  v9 = HamPopulateActivityPropertiesByClass(L"Windows Error Reporting", 0, 6, v35);
  if ( v9 < 0 )
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
        dwProcessId,
        v9);
    v11 = v9 | 0x10000000;
    goto LABEL_49;
  }
  v10 = (char *)OpenProcess(0x1001u, 0, dwProcessId);
  if ( v10 == (char *)-1LL || v10 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
        dwProcessId,
        v11);
    goto LABEL_49;
  }
  v13 = (RTL_SRWLOCK *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v13 )
  {
    Ptr = SRWLock[1].Ptr;
    v13->Ptr = 0;
    v8 = v13;
    v13[5].Ptr = Ptr;
    LODWORD(v13[1].Ptr) = dwProcessId;
    v13[2].Ptr = (PVOID)-1LL;
    v13[3].Ptr = a3;
    LOBYTE(v13[4].Ptr) = a4;
    HIDWORD(v13[4].Ptr) = 4;
    v34 = v13;
    AcquireSRWLockExclusive(SRWLock);
    v15 = SRWLock + 2;
    v16 = (((char *)SRWLock[3].Ptr - (char *)SRWLock[2].Ptr) >> 3) + 1;
    v17 = ((char *)SRWLock[4].Ptr - (char *)SRWLock[2].Ptr) >> 3;
    if ( v16 > v17 )
    {
      v18 = (((char *)SRWLock[3].Ptr - (char *)SRWLock[2].Ptr) >> 3) + 1;
      v19 = 7 * (v17 >> 2) + 8;
      if ( v19 >= v16 )
        v18 = v19;
      if ( v18 > 0xFFFFFFFFFFFFFFFLL )
        v18 = 0xFFFFFFFFFFFFFFFLL;
      if ( v16 > v18
        || !utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(
              (__int64)&SRWLock[2],
              v18) )
      {
        v11 = -2147024882;
LABEL_21:
        ReleaseSRWLockExclusive(SRWLock);
        goto LABEL_49;
      }
    }
    AcquireSRWLockExclusive(v13);
    ActivityForProcess = HamCreateActivityForProcess(SRWLock[1].Ptr, v13, v10, v35, &v13[2]);
    if ( ActivityForProcess < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v22 = 20;
      goto LABEL_26;
    }
    v23 = (char *)SRWLock[3].Ptr;
    v24 = (char *)SRWLock[4].Ptr;
    v25 = v13[2].Ptr;
    if ( v23 == v24 )
    {
      v26 = v15->Ptr;
      v27 = (v24 - (char *)v15->Ptr) >> 3;
      v28 = 7 * (v27 >> 2) + 8;
      if ( v28 > 0xFFFFFFFFFFFFFFFLL )
        v28 = 0xFFFFFFFFFFFFFFFLL;
      if ( v27 >= v28
        || !utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(
              (__int64)&SRWLock[2],
              v28) )
      {
        goto LABEL_39;
      }
      v29 = (char *)SRWLock[3].Ptr;
      v30 = (void **)&v34;
      if ( (char *)&v34 - v26 < (unsigned __int64)(v29 - (char *)SRWLock[2].Ptr) )
        v30 = (void **)((char *)v15->Ptr + (char *)&v34 - v26);
      v31 = *v30;
      *v30 = 0;
      v8 = v34;
      *(_QWORD *)v29 = v31;
    }
    else
    {
      v8 = 0;
      *(_QWORD *)v23 = v13;
    }
    SRWLock[3].Ptr = (char *)SRWLock[3].Ptr + 8;
LABEL_39:
    ActivityForProcess = HamStartActivityAsync(SRWLock[1].Ptr, v25, 0, 0);
    if ( ActivityForProcess >= 0 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_b6936b066fab37677c58fa622b799e39_Traceguids,
          dwProcessId,
          a4);
      goto LABEL_28;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_27:
      v11 = ActivityForProcess | 0x10000000;
LABEL_28:
      ReleaseSRWLockExclusive(v13);
      goto LABEL_21;
    }
    v22 = 21;
LABEL_26:
    WPP_SF_Dd(v21[2], v22, WPP_b6936b066fab37677c58fa622b799e39_Traceguids, dwProcessId, ActivityForProcess);
    goto LABEL_27;
  }
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b6936b066fab37677c58fa622b799e39_Traceguids, 2147942414LL);
LABEL_49:
  if ( v8 )
    operator delete(v8, (const struct std::nothrow_t *)0x30);
  if ( (unsigned __int64)(v10 + 1) > 1 )
    CloseHandle(v10);
  return v11;
}

```

## disassembly

```asm
0x18002539c  mov     [rsp+arg_10], rbx
0x1800253a1  push    rbp
0x1800253a2  push    rsi
0x1800253a3  push    rdi
0x1800253a4  push    r12
0x1800253a6  push    r13
0x1800253a8  push    r14
0x1800253aa  push    r15
0x1800253ac  sub     rsp, 1E0h
0x1800253b3  mov     rax, cs:__security_cookie
0x1800253ba  xor     rax, rsp
0x1800253bd  mov     [rsp+218h+var_48], rax
0x1800253c5  mov     rsi, r8
0x1800253c8  mov     [rsp+218h+var_1E8], r9b
0x1800253cd  mov     r15d, edx
0x1800253d0  mov     rbp, rcx
0x1800253d3  xor     edx, edx; Val
0x1800253d5  lea     rcx, [rsp+218h+var_1D8]; void *
0x1800253da  mov     r8d, 188h; Size
0x1800253e0  mov     r13b, r9b
0x1800253e3  xor     r12d, r12d
0x1800253e6  call    memset_0
0x1800253eb  lea     r9, [rsp+218h+var_1D8]
0x1800253f0  xor     edx, edx
0x1800253f2  lea     r8d, [r12+6]
0x1800253f7  lea     rcx, aWindowsErrorRe; "Windows Error Reporting"
0x1800253fe  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x180025404  mov     edi, eax
0x180025406  test    eax, eax
0x180025408  jns     short loc_180025448
0x18002540a  xor     ebx, ebx
0x18002540c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025413  lea     rax, WPP_GLOBAL_Control
0x18002541a  cmp     rcx, rax
0x18002541d  jz      short loc_18002543F
0x18002541f  test    byte ptr [rcx+1Ch], 1
0x180025423  jz      short loc_18002543F
0x180025425  mov     rcx, [rcx+10h]
0x180025429  lea     edx, [rbx+11h]
0x18002542c  mov     r9d, r15d
0x18002542f  mov     dword ptr [rsp+218h+var_1F8], edi
0x180025433  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x18002543a  call    WPP_SF_Dd
0x18002543f  bts     edi, 1Ch
0x180025443  jmp     loc_18002573D
0x180025448  mov     r8d, r15d; dwProcessId
0x18002544b  xor     edx, edx; bInheritHandle
0x18002544d  mov     ecx, 1001h; dwDesiredAccess
0x180025452  call    cs:__imp_OpenProcess
0x180025458  mov     rbx, rax
0x18002545b  inc     rax
0x18002545e  cmp     rax, 1
0x180025462  ja      short loc_1800254BB
0x180025464  call    cs:__imp_GetLastError
0x18002546a  mov     edi, eax
0x18002546c  test    eax, eax
0x18002546e  jle     short loc_180025479
0x180025470  movzx   edi, ax
0x180025473  or      edi, 80070000h
0x180025479  mov     rcx, cs:WPP_GLOBAL_Control
0x180025480  lea     rax, WPP_GLOBAL_Control
0x180025487  cmp     rcx, rax
0x18002548a  jz      loc_18002573D
0x180025490  test    byte ptr [rcx+1Ch], 1
0x180025494  jz      loc_18002573D
0x18002549a  mov     rcx, [rcx+10h]
0x18002549e  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x1800254a5  mov     edx, 12h
0x1800254aa  mov     dword ptr [rsp+218h+var_1F8], edi
0x1800254ae  mov     r9d, r15d
0x1800254b1  call    WPP_SF_Dd
0x1800254b6  jmp     loc_18002573D
0x1800254bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800254c2  mov     ecx, 30h ; '0'; unsigned __int64
0x1800254c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800254cc  mov     r14, rax
0x1800254cf  test    rax, rax
0x1800254d2  jz      loc_180025707
0x1800254d8  mov     rax, [rbp+8]
0x1800254dc  mov     rcx, rbp; SRWLock
0x1800254df  mov     [r14], r12
0x1800254e2  mov     r12, r14
0x1800254e5  mov     [r14+28h], rax
0x1800254e9  mov     [r14+8], r15d
0x1800254ed  mov     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x1800254f5  mov     [r14+18h], rsi
0x1800254f9  mov     [r14+20h], r13b
0x1800254fd  mov     dword ptr [r14+24h], 4
0x180025505  mov     [rsp+218h+var_1E0], r14
0x18002550a  call    cs:__imp_AcquireSRWLockExclusive
0x180025510  lea     rsi, [rbp+10h]
0x180025514  mov     r8, 0FFFFFFFFFFFFFFFh
0x18002551e  mov     rcx, [rsi+8]
0x180025522  sub     rcx, [rsi]
0x180025525  mov     rax, [rsi+10h]
0x180025529  sub     rax, [rsi]
0x18002552c  sar     rcx, 3
0x180025530  inc     rcx
0x180025533  sar     rax, 3
0x180025537  cmp     rcx, rax
0x18002553a  jbe     short loc_18002557D
0x18002553c  shr     rax, 2
0x180025540  mov     rdx, rcx
0x180025543  imul    rax, 7
0x180025547  add     rax, 8
0x18002554b  cmp     rax, rcx
0x18002554e  cmovnb  rdx, rax
0x180025552  cmp     rdx, r8
0x180025555  cmova   rdx, r8
0x180025559  cmp     rcx, rdx
0x18002555c  ja      short loc_18002556A
0x18002555e  mov     rcx, rsi
0x180025561  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x180025566  test    al, al
0x180025568  jnz     short loc_18002557D
0x18002556a  mov     edi, 8007000Eh
0x18002556f  mov     rcx, rbp; SRWLock
0x180025572  call    cs:__imp_ReleaseSRWLockExclusive
0x180025578  jmp     loc_18002573D
0x18002557d  mov     rcx, r14; SRWLock
0x180025580  call    cs:__imp_AcquireSRWLockExclusive
0x180025586  mov     rcx, [rbp+8]
0x18002558a  lea     r13, [r14+10h]
0x18002558e  lea     r9, [rsp+218h+var_1D8]
0x180025593  mov     [rsp+218h+var_1F8], r13
0x180025598  mov     r8, rbx
0x18002559b  mov     rdx, r14
0x18002559e  call    cs:__imp_HamCreateActivityForProcess
0x1800255a4  mov     edi, eax
0x1800255a6  test    eax, eax
0x1800255a8  jns     short loc_1800255EE
0x1800255aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255b1  lea     rax, WPP_GLOBAL_Control
0x1800255b8  cmp     rcx, rax
0x1800255bb  jz      short loc_1800255DF
0x1800255bd  test    byte ptr [rcx+1Ch], 1
0x1800255c1  jz      short loc_1800255DF
0x1800255c3  mov     edx, 14h
0x1800255c8  mov     rcx, [rcx+10h]
0x1800255cc  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x1800255d3  mov     r9d, r15d
0x1800255d6  mov     dword ptr [rsp+218h+var_1F8], edi
0x1800255da  call    WPP_SF_Dd
0x1800255df  bts     edi, 1Ch
0x1800255e3  mov     rcx, r14; SRWLock
0x1800255e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800255ec  jmp     short loc_18002556F
0x1800255ee  mov     rax, [rsi+8]
0x1800255f2  mov     rcx, [rsi+10h]
0x1800255f6  mov     r13, [r13+0]
0x1800255fa  cmp     rax, rcx
0x1800255fd  jz      short loc_180025607
0x1800255ff  xor     r12d, r12d
0x180025602  mov     [rax], r14
0x180025605  jmp     short loc_180025677
0x180025607  mov     rdi, [rsi]
0x18002560a  sub     rcx, rdi
0x18002560d  sar     rcx, 3
0x180025611  mov     rax, rcx
0x180025614  shr     rax, 2
0x180025618  imul    rdx, rax, 7
0x18002561c  mov     rax, 0FFFFFFFFFFFFFFFh
0x180025626  add     rdx, 8
0x18002562a  cmp     rdx, rax
0x18002562d  cmova   rdx, rax
0x180025631  cmp     rcx, rdx
0x180025634  jnb     short loc_18002567C
0x180025636  mov     rcx, rsi
0x180025639  call    ?_SetCapacity@?$vector@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UHamActivity@HamConnector@@U?$default_delete@UHamActivity@HamConnector@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>,utl::allocator<utl::unique_ptr<HamConnector::HamActivity,utl::default_delete<HamConnector::HamActivity>>>>::_SetCapacity(unsigned __int64)
0x18002563e  test    al, al
0x180025640  jz      short loc_18002567C
0x180025642  mov     r9, [rsi+8]
0x180025646  lea     rcx, [rsp+218h+var_1E0]
0x18002564b  mov     r8, [rsi]
0x18002564e  lea     rdx, [rsp+218h+var_1E0]
0x180025653  mov     rax, r9
0x180025656  sub     rcx, rdi
0x180025659  sub     rax, r8
0x18002565c  cmp     rcx, rax
0x18002565f  jnb     short loc_180025665
0x180025661  lea     rdx, [rcx+r8]
0x180025665  mov     rax, [rdx]
0x180025668  mov     qword ptr [rdx], 0
0x18002566f  mov     r12, [rsp+218h+var_1E0]
0x180025674  mov     [r9], rax
0x180025677  add     qword ptr [rsi+8], 8
0x18002567c  mov     rcx, [rbp+8]
0x180025680  xor     r9d, r9d
0x180025683  xor     r8d, r8d
0x180025686  mov     rdx, r13
0x180025689  call    cs:__imp_HamStartActivityAsync
0x18002568f  mov     edi, eax
0x180025691  test    eax, eax
0x180025693  js      short loc_1800256DC
0x180025695  xor     edi, edi
0x180025697  mov     rcx, cs:WPP_GLOBAL_Control
0x18002569e  lea     rax, WPP_GLOBAL_Control
0x1800256a5  cmp     rcx, rax
0x1800256a8  jz      loc_1800255E3
0x1800256ae  test    byte ptr [rcx+1Ch], 4
0x1800256b2  jz      loc_1800255E3
0x1800256b8  movzx   eax, [rsp+218h+var_1E8]
0x1800256bd  lea     edx, [rdi+16h]
0x1800256c0  mov     rcx, [rcx+10h]
0x1800256c4  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x1800256cb  mov     r9d, r15d
0x1800256ce  mov     dword ptr [rsp+218h+var_1F8], eax
0x1800256d2  call    WPP_SF_Dd
0x1800256d7  jmp     loc_1800255E3
0x1800256dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256e3  lea     rax, WPP_GLOBAL_Control
0x1800256ea  cmp     rcx, rax
0x1800256ed  jz      loc_1800255DF
0x1800256f3  test    byte ptr [rcx+1Ch], 1
0x1800256f7  jz      loc_1800255DF
0x1800256fd  mov     edx, 15h
0x180025702  jmp     loc_1800255C8
0x180025707  mov     edi, 8007000Eh
0x18002570c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025713  lea     rax, WPP_GLOBAL_Control
0x18002571a  cmp     rcx, rax
0x18002571d  jz      short loc_18002573D
0x18002571f  test    byte ptr [rcx+1Ch], 1
0x180025723  jz      short loc_18002573D
0x180025725  mov     rcx, [rcx+10h]
0x180025729  lea     r8, WPP_b6936b066fab37677c58fa622b799e39_Traceguids
0x180025730  mov     edx, 13h
0x180025735  mov     r9d, edi
0x180025738  call    WPP_SF_d
0x18002573d  test    r12, r12
0x180025740  jz      short loc_18002574F
0x180025742  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180025747  mov     rcx, r12; void *
0x18002574a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002574f  lea     rcx, [rbx+1]
0x180025753  cmp     rcx, 1
0x180025757  jbe     short loc_180025762
0x180025759  mov     rcx, rbx; hObject
0x18002575c  call    cs:__imp_CloseHandle
0x180025762  mov     eax, edi
0x180025764  mov     rcx, [rsp+218h+var_48]
0x18002576c  xor     rcx, rsp; StackCookie
0x18002576f  call    __security_check_cookie
0x180025774  mov     rbx, [rsp+218h+arg_10]
0x18002577c  add     rsp, 1E0h
0x180025783  pop     r15
0x180025785  pop     r14
0x180025787  pop     r13
0x180025789  pop     r12
0x18002578b  pop     rdi
0x18002578c  pop     rsi
0x18002578d  pop     rbp
0x18002578e  retn
```
