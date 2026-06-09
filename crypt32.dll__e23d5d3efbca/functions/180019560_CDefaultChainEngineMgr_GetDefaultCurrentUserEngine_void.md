# CDefaultChainEngineMgr::GetDefaultCurrentUserEngine(void * *)

- ea: `0x180019560`
- end: `0x180019715`
- name: `?GetDefaultCurrentUserEngine@CDefaultChainEngineMgr@@QEAAHPEAPEAX@Z`
- size: `437`
- prototype: `__int64 __fastcall(CDefaultChainEngineMgr *__hidden this, void **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018f10`
- `0x180019174`
- `0x180019310`
- `0x18001abcc`

## callees

- `0x180019560`
- `0x18001971c`
- `0x180054a4c`
- `0x1800578f8`
- `0x180058040`
- `0x180068cf0`
- `0x1800a11c8`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019600`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019600`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800195c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800195c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800195f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019637`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800195f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019637`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800195cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001969a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800195cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001969a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001959d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001959d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196ee`

## pseudocode

```c
__int64 __fastcall CDefaultChainEngineMgr::GetDefaultCurrentUserEngine(CDefaultChainEngineMgr *this, void **a2)
{
  HANDLE CurrentThread; // rax
  unsigned int DefaultCurrentImpersonatedUserEngine; // edi
  struct _CERT_AUTO_FLUSH_ENGINE_INFO *AutoFlushEngineInfo; // rsi
  __int64 v7; // rax
  unsigned int v9; // eax
  CCertChainEngine *v10; // rbp
  struct _CERT_CHAIN_ENGINE_CONFIG Src; // [rsp+20h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+C0h] [rbp+18h] BYREF
  CCertChainEngine *v13; // [rsp+C8h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    DefaultCurrentImpersonatedUserEngine = CDefaultChainEngineMgr::GetDefaultCurrentImpersonatedUserEngine(
                                             this,
                                             TokenHandle,
                                             a2);
    CloseHandle(TokenHandle);
    return DefaultCurrentImpersonatedUserEngine;
  }
  if ( GetLastError() == 1008 )
  {
    DefaultCurrentImpersonatedUserEngine = 1;
    AutoFlushEngineInfo = 0;
    AcquireSRWLockExclusive((PSRWLOCK)this + 9);
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    if ( *((_QWORD *)this + 8) )
      goto LABEL_4;
    v13 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    memset_0(&Src, 0, 0x58u);
    Src.cbSize = 88;
    Src.dwFlags = 48;
    v9 = InternalCertCreateCertificateChainEngine(&Src, (void **)&v13);
    v10 = v13;
    DefaultCurrentImpersonatedUserEngine = v9;
    if ( v9 && v13 )
      AutoFlushEngineInfo = CDefaultChainEngineMgr::CreateAutoFlushEngineInfo(this, v13, 1u, 0);
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    if ( DefaultCurrentImpersonatedUserEngine && !*((_QWORD *)this + 8) )
    {
      *((_QWORD *)this + 8) = v10;
      v10 = 0;
      *((_QWORD *)this + 10) = AutoFlushEngineInfo;
      I_StartAutoFlush(AutoFlushEngineInfo);
      AutoFlushEngineInfo = 0;
    }
    if ( v10 )
      CCertChainEngine::Release(v10);
    if ( DefaultCurrentImpersonatedUserEngine )
    {
LABEL_4:
      _InterlockedIncrement(*((volatile signed __int32 **)this + 8));
      *a2 = (void *)*((_QWORD *)this + 8);
      v7 = *((_QWORD *)this + 10);
      if ( v7 )
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 48));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 9);
    if ( AutoFlushEngineInfo )
      I_FreeAutoFlushEngineInfo(AutoFlushEngineInfo, 1);
    return DefaultCurrentImpersonatedUserEngine;
  }
  return 0;
}

```

## disassembly

```asm
0x180019560  mov     rax, rsp
0x180019563  mov     [rax+8], rbx
0x180019567  push    rbp
0x180019568  push    rsi
0x180019569  push    rdi
0x18001956a  push    r14
0x18001956c  push    r15
0x18001956e  sub     rsp, 80h
0x180019575  mov     r15, rdx
0x180019578  mov     qword ptr [rax+18h], 0
0x180019580  mov     rbx, rcx
0x180019583  call    cs:__imp_GetCurrentThread
0x180019589  mov     edx, 8; DesiredAccess
0x18001958e  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x180019596  mov     rcx, rax; ThreadHandle
0x180019599  lea     r8d, [rdx-7]; OpenAsSelf
0x18001959d  call    cs:__imp_OpenThreadToken
0x1800195a3  test    eax, eax
0x1800195a5  jnz     loc_1800196D1
0x1800195ab  call    cs:__imp_GetLastError
0x1800195b1  cmp     eax, 3F0h
0x1800195b6  jnz     short loc_180019628
0x1800195b8  lea     rcx, [rbx+48h]; SRWLock
0x1800195bc  mov     edi, 1
0x1800195c1  xor     esi, esi
0x1800195c3  call    cs:__imp_AcquireSRWLockExclusive
0x1800195c9  mov     rcx, rbx; lpCriticalSection
0x1800195cc  call    cs:__imp_EnterCriticalSection
0x1800195d2  cmp     [rbx+40h], rsi
0x1800195d6  jz      short loc_18001962C
0x1800195d8  mov     rax, [rbx+40h]
0x1800195dc  lock inc dword ptr [rax]
0x1800195df  mov     rax, [rbx+40h]
0x1800195e3  mov     [r15], rax
0x1800195e6  mov     rax, [rbx+50h]
0x1800195ea  test    rax, rax
0x1800195ed  jz      short loc_1800195F3
0x1800195ef  lock inc dword ptr [rax+30h]
0x1800195f3  mov     rcx, rbx; lpCriticalSection
0x1800195f6  call    cs:__imp_LeaveCriticalSection
0x1800195fc  lea     rcx, [rbx+48h]; SRWLock
0x180019600  call    cs:__imp_ReleaseSRWLockExclusive
0x180019606  test    rsi, rsi
0x180019609  jnz     loc_180019703
0x18001960f  mov     eax, edi
0x180019611  mov     rbx, [rsp+0A8h+arg_0]
0x180019619  add     rsp, 80h
0x180019620  pop     r15
0x180019622  pop     r14
0x180019624  pop     rdi
0x180019625  pop     rsi
0x180019626  pop     rbp
0x180019627  retn
0x180019628  xor     eax, eax
0x18001962a  jmp     short loc_180019611
0x18001962c  mov     rcx, rbx; lpCriticalSection
0x18001962f  mov     [rsp+0A8h+arg_18], rsi
0x180019637  call    cs:__imp_LeaveCriticalSection
0x18001963d  mov     edi, 58h ; 'X'
0x180019642  lea     rcx, [rsp+0A8h+Src]; void *
0x180019647  mov     r8d, edi; Size
0x18001964a  xor     edx, edx; Val
0x18001964c  call    memset_0
0x180019651  lea     rdx, [rsp+0A8h+arg_18]; void **
0x180019659  mov     [rsp+0A8h+Src.cbSize], edi
0x18001965d  lea     rcx, [rsp+0A8h+Src]; Src
0x180019662  mov     [rsp+0A8h+Src.dwFlags], 30h ; '0'
0x18001966a  call    ?InternalCertCreateCertificateChainEngine@@YAHPEAU_CERT_CHAIN_ENGINE_CONFIG@@PEAPEAX@Z; InternalCertCreateCertificateChainEngine(_CERT_CHAIN_ENGINE_CONFIG *,void * *)
0x18001966f  mov     rbp, [rsp+0A8h+arg_18]
0x180019677  mov     edi, eax
0x180019679  test    eax, eax
0x18001967b  jz      short loc_180019697
0x18001967d  test    rbp, rbp
0x180019680  jz      short loc_180019697
0x180019682  xor     r9d, r9d; void *
0x180019685  mov     rdx, rbp; void *
0x180019688  mov     rcx, rbx; this
0x18001968b  lea     r8d, [r9+1]; unsigned int
0x18001968f  call    ?CreateAutoFlushEngineInfo@CDefaultChainEngineMgr@@QEAAPEAU_CERT_AUTO_FLUSH_ENGINE_INFO@@PEAXK0@Z; CDefaultChainEngineMgr::CreateAutoFlushEngineInfo(void *,ulong,void *)
0x180019694  mov     rsi, rax
0x180019697  mov     rcx, rbx; lpCriticalSection
0x18001969a  call    cs:__imp_EnterCriticalSection
0x1800196a0  test    edi, edi
0x1800196a2  jz      short loc_1800196BF
0x1800196a4  cmp     qword ptr [rbx+40h], 0
0x1800196a9  jnz     short loc_1800196BF
0x1800196ab  mov     [rbx+40h], rbp
0x1800196af  mov     rcx, rsi; struct _CERT_AUTO_FLUSH_ENGINE_INFO *
0x1800196b2  xor     ebp, ebp
0x1800196b4  mov     [rbx+50h], rsi
0x1800196b8  call    ?I_StartAutoFlush@@YAXPEAU_CERT_AUTO_FLUSH_ENGINE_INFO@@@Z; I_StartAutoFlush(_CERT_AUTO_FLUSH_ENGINE_INFO *)
0x1800196bd  xor     esi, esi
0x1800196bf  test    rbp, rbp
0x1800196c2  jnz     short loc_1800196F9
0x1800196c4  test    edi, edi
0x1800196c6  jnz     loc_1800195D8
0x1800196cc  jmp     loc_1800195F3
0x1800196d1  mov     rdx, [rsp+0A8h+TokenHandle]; void *
0x1800196d9  mov     r8, r15; void **
0x1800196dc  mov     rcx, rbx; this
0x1800196df  call    ?GetDefaultCurrentImpersonatedUserEngine@CDefaultChainEngineMgr@@AEAAHPEAXPEAPEAX@Z; CDefaultChainEngineMgr::GetDefaultCurrentImpersonatedUserEngine(void *,void * *)
0x1800196e4  mov     rcx, [rsp+0A8h+TokenHandle]; hObject
0x1800196ec  mov     edi, eax
0x1800196ee  call    cs:__imp_CloseHandle
0x1800196f4  jmp     loc_18001960F
0x1800196f9  mov     rcx, rbp; this
0x1800196fc  call    ?Release@CCertChainEngine@@QEAAXXZ; CCertChainEngine::Release(void)
0x180019701  jmp     short loc_1800196C4
0x180019703  mov     edx, 1; int
0x180019708  mov     rcx, rsi; hMem
0x18001970b  call    ?I_FreeAutoFlushEngineInfo@@YAXPEAU_CERT_AUTO_FLUSH_ENGINE_INFO@@H@Z; I_FreeAutoFlushEngineInfo(_CERT_AUTO_FLUSH_ENGINE_INFO *,int)
0x180019710  jmp     loc_18001960F
```
