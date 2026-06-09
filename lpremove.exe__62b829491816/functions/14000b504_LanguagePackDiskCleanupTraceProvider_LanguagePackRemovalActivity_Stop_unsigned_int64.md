# LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::Stop(unsigned __int64)

- ea: `0x14000b504`
- end: `0x14000b8c6`
- name: `?Stop@LanguagePackRemovalActivity@LanguagePackDiskCleanupTraceProvider@@QEAAX_K@Z`
- size: `962`
- prototype: `void __fastcall(LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000d8b8`

## callees

- `0x1400012bc`
- `0x140001b9c`
- `0x140002190`
- `0x140007eac`
- `0x1400084b8`
- `0x14000b504`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000b7b1`
- `KERNEL32!GetCurrentThreadId` at `0x14000b848`
- `KERNEL32!GetCurrentThreadId` at `0x14000b7b1`
- `KERNEL32!GetCurrentThreadId` at `0x14000b848`
- `KERNEL32!GetTickCount64` at `0x14000b5bd`
- `KERNEL32!GetTickCount64` at `0x14000b787`
- `KERNEL32!GetTickCount64` at `0x14000b5bd`
- `KERNEL32!GetTickCount64` at `0x14000b787`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b579`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b743`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b579`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b743`

## string_xrefs

- `0x14000b866`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::Stop(
        LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this,
        __int64 a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rsi
  ULONGLONG TickCount64; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 v12; // r8
  char *v13; // rbx
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+C0h] [rbp-70h] BYREF
  int v19; // [rsp+C8h] [rbp-68h] BYREF
  int v20; // [rsp+CCh] [rbp-64h] BYREF
  int v21; // [rsp+D0h] [rbp-60h] BYREF
  int v22; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  ULONGLONG v24; // [rsp+E0h] [rbp-50h] BYREF
  int *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  int *v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  int *v30; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v31; // [rsp+118h] [rbp-18h] BYREF
  const unsigned __int16 *v32; // [rsp+120h] [rbp-10h] BYREF
  _BYTE v33[32]; // [rsp+130h] [rbp+0h] BYREF
  __int64 *v34; // [rsp+150h] [rbp+20h]
  __int64 v35; // [rsp+158h] [rbp+28h]
  int *v36; // [rsp+160h] [rbp+30h]
  __int64 v37; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v39; // [rsp+178h] [rbp+48h]
  PSRWLOCK *v40; // [rsp+180h] [rbp+50h]
  __int64 v41; // [rsp+188h] [rbp+58h]
  void *retaddr; // [rsp+1B8h] [rbp+88h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x200000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      TickCount64 = GetTickCount64();
      v9 = ((TickCount64 - a2) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      v24 = (v9 + ((TickCount64 - a2 - v9) >> 1)) >> 9;
      v25 = (int *)*((_QWORD *)v6 + 15);
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v19 = v6[26];
      v27 = (int *)*((_QWORD *)v6 + 12);
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v20 = v6[20];
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v21 = v6[8];
      v30 = (int *)*((_QWORD *)v6 + 3);
      v22 = *v6;
      v31 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v16 = v6[16];
      v32 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v23 = 0x1000000;
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v7,
        (__int64)byte_140014439,
        *((_QWORD *)this + 34) + 8LL,
        v10,
        (__int64)&v18,
        (__int64)&v23,
        (__int64)&SRWLock,
        &v32,
        (__int64)&v16,
        &v31,
        (__int64)&v22,
        &v30,
        (__int64)&v21,
        &v29,
        (__int64)&v20,
        &v28,
        &v27,
        (__int64)&v19,
        &v26,
        &v25,
        (__int64)&v24);
    }
  }
  else
  {
    wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    **((_DWORD **)this + 34) = 2;
    if ( v18 )
      ReleaseSRWLockExclusive(v18);
    v11 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v11 > 5u
      && (*(_QWORD *)(v11 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v11 + 24) & 0x200000000000LL) == *(_QWORD *)(v11 + 24) )
    {
      v18 = (PSRWLOCK)((GetTickCount64() - a2) / 0x3E8);
      LODWORD(SRWLock) = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v16 = *(_DWORD *)(v12 + 72);
      v23 = 0;
      v40 = &v18;
      v41 = 8;
      p_SRWLock = &SRWLock;
      v39 = 4;
      v36 = &v16;
      v37 = 4;
      v34 = &v23;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v11, byte_1400143D3, v12 + 8, 0, 6, v33);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( *((_DWORD *)v13 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v13 + 6) = 0;
    v14 = *(__int64 **)v13;
    while ( 1 )
    {
      v15 = *v14;
      if ( !*v14 )
        break;
      if ( (char *)v15 == v13 )
      {
        *v14 = *((_QWORD *)v13 + 2);
        break;
      }
      v14 = (__int64 *)(v15 + 16);
      *(_QWORD *)v13 = v15 + 16;
    }
    *(_QWORD *)v13 = 0;
  }
}

```

## disassembly

```asm
0x14000b504  mov     [rsp-8+arg_8], rbx
0x14000b509  mov     [rsp-8+arg_10], rsi
0x14000b50e  push    rbp
0x14000b50f  push    rdi
0x14000b510  push    r14
0x14000b512  lea     rbp, [rsp-70h]
0x14000b517  sub     rsp, 1A0h
0x14000b51e  mov     rax, cs:__security_cookie
0x14000b525  xor     rax, rsp
0x14000b528  mov     [rbp+80h+var_20], rax
0x14000b52c  mov     r14, rdx
0x14000b52f  mov     rbx, rcx
0x14000b532  mov     rdi, [rcx+110h]
0x14000b539  mov     eax, [rdi+48h]
0x14000b53c  test    eax, eax
0x14000b53e  jns     loc_14000B724
0x14000b544  add     rdi, 50h ; 'P'
0x14000b548  cmp     eax, [rdi+8]
0x14000b54b  jnz     loc_14000B724
0x14000b551  test    rdi, rdi
0x14000b554  jz      loc_14000B724
0x14000b55a  lea     rdx, [rbp+80h+SRWLock]
0x14000b55e  call    ?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b563  mov     rax, [rbx+110h]
0x14000b56a  mov     dword ptr [rax], 2
0x14000b570  mov     rcx, [rbp+80h+SRWLock]; SRWLock
0x14000b574  test    rcx, rcx
0x14000b577  jz      short loc_14000B57F
0x14000b579  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b57f  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000b584  mov     rsi, [rax+8]
0x14000b588  mov     eax, [rsi]
0x14000b58a  cmp     eax, 5
0x14000b58d  jbe     loc_14000B838
0x14000b593  mov     rdx, [rsi+18h]
0x14000b597  mov     rax, [rsi+10h]
0x14000b59b  mov     rcx, 200000000000h
0x14000b5a5  test    rcx, rax
0x14000b5a8  jz      loc_14000B838
0x14000b5ae  mov     rax, rdx
0x14000b5b1  and     rax, rcx
0x14000b5b4  cmp     rax, rdx
0x14000b5b7  jnz     loc_14000B838
0x14000b5bd  call    cs:__imp_GetTickCount64
0x14000b5c3  mov     rcx, rax
0x14000b5c6  sub     rcx, r14
0x14000b5c9  mov     rax, 624DD2F1A9FBE77h
0x14000b5d3  mul     rcx
0x14000b5d6  sub     rcx, rdx
0x14000b5d9  shr     rcx, 1
0x14000b5dc  add     rcx, rdx
0x14000b5df  shr     rcx, 9
0x14000b5e3  mov     [rbp+80h+var_D0], rcx
0x14000b5e7  mov     rax, [rdi+78h]
0x14000b5eb  mov     [rbp+80h+var_C8], rax
0x14000b5ef  mov     rax, [rdi+70h]
0x14000b5f3  mov     [rbp+80h+var_C0], rax
0x14000b5f7  mov     eax, [rdi+68h]
0x14000b5fa  mov     [rbp+80h+var_E8], eax
0x14000b5fd  mov     rax, [rdi+60h]
0x14000b601  mov     [rbp+80h+var_B8], rax
0x14000b605  mov     rax, [rdi+58h]
0x14000b609  mov     [rbp+80h+var_B0], rax
0x14000b60d  mov     eax, [rdi+50h]
0x14000b610  mov     [rbp+80h+var_E4], eax
0x14000b613  mov     rax, [rdi+48h]
0x14000b617  mov     [rbp+80h+var_A8], rax
0x14000b61b  mov     eax, [rdi+20h]
0x14000b61e  mov     [rbp+80h+var_E0], eax
0x14000b621  mov     rax, [rdi+18h]
0x14000b625  mov     [rbp+80h+var_A0], rax
0x14000b629  mov     eax, [rdi]
0x14000b62b  mov     [rbp+80h+var_DC], eax
0x14000b62e  mov     rax, [rdi+80h]
0x14000b635  mov     [rbp+80h+var_98], rax
0x14000b639  mov     eax, [rdi+40h]
0x14000b63c  mov     [rbp+80h+var_100], eax
0x14000b63f  mov     rax, [rdi+38h]
0x14000b643  mov     [rbp+80h+var_90], rax
0x14000b647  mov     eax, [rdi+8]
0x14000b64a  mov     dword ptr [rbp+80h+SRWLock], eax
0x14000b64d  mov     [rbp+80h+var_D8], 1000000h
0x14000b655  mov     [rbp+80h+var_F0], 0
0x14000b65d  mov     r8, [rbx+110h]
0x14000b664  add     r8, 8
0x14000b668  lea     rax, [rbp+80h+var_D0]
0x14000b66c  mov     [rsp+1B0h+var_110], rax
0x14000b674  lea     rax, [rbp+80h+var_C8]
0x14000b678  mov     [rsp+1B0h+var_118], rax
0x14000b680  lea     rax, [rbp+80h+var_C0]
0x14000b684  mov     [rsp+1B0h+var_120], rax
0x14000b68c  lea     rax, [rbp+80h+var_E8]
0x14000b690  mov     [rsp+1B0h+var_128], rax
0x14000b698  lea     rax, [rbp+80h+var_B8]
0x14000b69c  mov     [rsp+1B0h+var_130], rax
0x14000b6a4  lea     rax, [rbp+80h+var_B0]
0x14000b6a8  mov     [rsp+1B0h+var_138], rax
0x14000b6ad  lea     rax, [rbp+80h+var_E4]
0x14000b6b1  mov     [rsp+1B0h+var_140], rax
0x14000b6b6  lea     rax, [rbp+80h+var_A8]
0x14000b6ba  mov     [rsp+1B0h+var_148], rax
0x14000b6bf  lea     rax, [rbp+80h+var_E0]
0x14000b6c3  mov     [rsp+1B0h+var_150], rax
0x14000b6c8  lea     rax, [rbp+80h+var_A0]
0x14000b6cc  mov     [rsp+1B0h+var_158], rax
0x14000b6d1  lea     rax, [rbp+80h+var_DC]
0x14000b6d5  mov     [rsp+1B0h+var_160], rax
0x14000b6da  lea     rax, [rbp+80h+var_98]
0x14000b6de  mov     [rsp+1B0h+var_168], rax
0x14000b6e3  lea     rax, [rbp+80h+var_100]
0x14000b6e7  mov     [rsp+1B0h+var_170], rax
0x14000b6ec  lea     rax, [rbp+80h+var_90]
0x14000b6f0  mov     [rsp+1B0h+var_178], rax
0x14000b6f5  lea     rax, [rbp+80h+SRWLock]
0x14000b6f9  mov     [rsp+1B0h+var_180], rax
0x14000b6fe  lea     rax, [rbp+80h+var_D8]
0x14000b702  mov     [rsp+1B0h+var_188], rax
0x14000b707  lea     rax, [rbp+80h+var_F0]
0x14000b70b  mov     [rsp+1B0h+var_190], rax
0x14000b710  lea     rdx, byte_140014439
0x14000b717  mov     rcx, rsi
0x14000b71a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14000b71f  jmp     loc_14000B838
0x14000b724  lea     rdx, [rbp+80h+var_F0]
0x14000b728  call    ?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b72d  mov     rax, [rbx+110h]
0x14000b734  mov     dword ptr [rax], 2
0x14000b73a  mov     rcx, [rbp+80h+var_F0]; SRWLock
0x14000b73e  test    rcx, rcx
0x14000b741  jz      short loc_14000B749
0x14000b743  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b749  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000b74e  mov     rdi, [rax+8]
0x14000b752  mov     eax, [rdi]
0x14000b754  cmp     eax, 5
0x14000b757  jbe     loc_14000B838
0x14000b75d  mov     rdx, [rdi+18h]
0x14000b761  mov     rax, [rdi+10h]
0x14000b765  mov     rcx, 200000000000h
0x14000b76f  test    rcx, rax
0x14000b772  jz      loc_14000B838
0x14000b778  mov     rax, rdx
0x14000b77b  and     rax, rcx
0x14000b77e  cmp     rax, rdx
0x14000b781  jnz     loc_14000B838
0x14000b787  call    cs:__imp_GetTickCount64
0x14000b78d  mov     rcx, rax
0x14000b790  sub     rcx, r14
0x14000b793  mov     rax, 624DD2F1A9FBE77h
0x14000b79d  mul     rcx
0x14000b7a0  sub     rcx, rdx
0x14000b7a3  shr     rcx, 1
0x14000b7a6  add     rcx, rdx
0x14000b7a9  shr     rcx, 9
0x14000b7ad  mov     [rbp+80h+var_F0], rcx
0x14000b7b1  call    cs:__imp_GetCurrentThreadId
0x14000b7b7  mov     dword ptr [rbp+80h+SRWLock], eax
0x14000b7ba  mov     r8, [rbx+110h]
0x14000b7c1  mov     eax, [r8+48h]
0x14000b7c5  mov     [rbp+80h+var_100], eax
0x14000b7c8  mov     [rbp+80h+var_D8], 0
0x14000b7d0  lea     rax, [rbp+80h+var_F0]
0x14000b7d4  mov     [rbp+80h+var_30], rax
0x14000b7d8  mov     [rbp+80h+var_28], 8
0x14000b7e0  lea     rax, [rbp+80h+SRWLock]
0x14000b7e4  mov     [rbp+80h+var_40], rax
0x14000b7e8  mov     [rbp+80h+var_38], 4
0x14000b7f0  lea     rax, [rbp+80h+var_100]
0x14000b7f4  mov     [rbp+80h+var_50], rax
0x14000b7f8  mov     [rbp+80h+var_48], 4
0x14000b800  lea     rax, [rbp+80h+var_D8]
0x14000b804  mov     [rbp+80h+var_60], rax
0x14000b808  mov     [rbp+80h+var_58], 8
0x14000b810  add     r8, 8
0x14000b814  lea     rax, [rbp+80h+var_80]
0x14000b818  mov     [rsp+1B0h+var_188], rax
0x14000b81d  mov     dword ptr [rsp+1B0h+var_190], 6
0x14000b825  xor     r9d, r9d
0x14000b828  lea     rdx, byte_1400143D3
0x14000b82f  mov     rcx, rdi
0x14000b832  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b837  nop
0x14000b838  cmp     dword ptr [rbx+138h], 0
0x14000b83f  jz      short loc_14000B8A2
0x14000b841  add     rbx, 120h
0x14000b848  call    cs:__imp_GetCurrentThreadId
0x14000b84e  cmp     [rbx+18h], eax
0x14000b851  jz      short loc_14000B872
0x14000b853  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000b85a  test    rax, rax
0x14000b85d  jz      short loc_14000B872
0x14000b85f  mov     rdx, [rbp+88h]
0x14000b866  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000b86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b872  mov     dword ptr [rbx+18h], 0
0x14000b879  mov     rcx, [rbx]
0x14000b87c  jmp     short loc_14000B88A
0x14000b87e  cmp     rax, rbx
0x14000b881  jz      short loc_14000B894
0x14000b883  lea     rcx, [rax+10h]
0x14000b887  mov     [rbx], rcx
0x14000b88a  mov     rax, [rcx]
0x14000b88d  test    rax, rax
0x14000b890  jnz     short loc_14000B87E
0x14000b892  jmp     short loc_14000B89B
0x14000b894  mov     rax, [rbx+10h]
0x14000b898  mov     [rcx], rax
0x14000b89b  mov     qword ptr [rbx], 0
0x14000b8a2  mov     rcx, [rbp+80h+var_20]
0x14000b8a6  xor     rcx, rsp; StackCookie
0x14000b8a9  call    __security_check_cookie
0x14000b8ae  lea     r11, [rsp+1B0h+var_10]
0x14000b8b6  mov     rbx, [r11+28h]
0x14000b8ba  mov     rsi, [r11+30h]
0x14000b8be  mov     rsp, r11
0x14000b8c1  pop     r14
0x14000b8c3  pop     rdi
0x14000b8c4  pop     rbp
0x14000b8c5  retn
```
