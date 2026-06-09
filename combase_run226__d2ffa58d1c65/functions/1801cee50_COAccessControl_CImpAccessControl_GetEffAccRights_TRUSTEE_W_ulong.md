# COAccessControl::CImpAccessControl::GetEffAccRights(_TRUSTEE_W *,ulong *)

- ea: `0x1801cee50`
- end: `0x1801cf151`
- name: `?GetEffAccRights@CImpAccessControl@COAccessControl@@AEAAJPEAU_TRUSTEE_W@@PEAK@Z`
- size: `769`
- prototype: `HRESULT __fastcall(COAccessControl::CImpAccessControl *this, _TRUSTEE_W *pdwRights, unsigned int *pTrustee)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801cf990`

## callees

- `0x180068780`
- `0x1801999b0`
- `0x1801ceaa8`
- `0x1801cee50`
- `0x1801d0ca4`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf10c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cefa4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cefcd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cf0ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cefa4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cefcd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801cf0ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801cef04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801cef7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801cef04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801cef7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801cef17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801cef8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801cef17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801cef8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ceedb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf02e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf0a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ceedb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf02e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cf0a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf0c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf0c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cefed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cefed`

## pseudocode

```c
__int64 __fastcall COAccessControl::CImpAccessControl::GetEffAccRights(
        COAccessControl::CImpAccessControl *this,
        _TRUSTEE_W *pdwRights,
        unsigned int *pTrustee)
{
  int v6; // ebx
  int v7; // r12d
  HANDLE v8; // rax
  signed int v9; // eax
  signed int v10; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  bool v13; // zf
  int v14; // ecx
  CEffPermsCacheLUID *v15; // rcx
  unsigned int LowPart; // ebx
  unsigned int v17; // eax
  int v18; // edi
  __int64 v19; // r13
  CEffPermsCacheLUID *v20; // rcx
  _LUID v21; // rbx
  unsigned int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rdi
  int v25; // [rsp+34h] [rbp-55h]
  unsigned int dwInfoLength; // [rsp+38h] [rbp-51h] BYREF
  IServerSecurity *pSSec; // [rsp+40h] [rbp-49h] BYREF
  void *hImpersonate; // [rsp+48h] [rbp-41h] BYREF
  void *hEnter; // [rsp+50h] [rbp-39h] BYREF
  _LUID ModifiedId; // [rsp+58h] [rbp-31h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-29h]
  _TOKEN_STATISTICS sTokenStatistics; // [rsp+68h] [rbp-21h] BYREF

  pSSec = 0;
  hEnter = (void *)-1LL;
  hImpersonate = (void *)-1LL;
  dwInfoLength = 56;
  memset(&sTokenStatistics, 0, sizeof(sTokenStatistics));
  if ( CoGetCallContext(&IID_IServerSecurity, (void **)&pSSec) < 0 )
    return 2147549476LL;
  v6 = 0;
  lpCriticalSection = &this->m_ACLLock;
  EnterCriticalSection(&this->m_ACLLock);
  v25 = pSSec->IsImpersonating(pSSec);
  v7 = v25;
  if ( !v25 || (v8 = GetCurrentThread(), OpenThreadToken(v8, 0x20008u, 1, &hEnter)) )
  {
    v10 = pSSec->ImpersonateClient(pSSec);
    if ( v10 >= 0 )
    {
      v6 = 1;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &hImpersonate) )
      {
        SetThreadToken(0, 0);
        if ( GetTokenInformation(hImpersonate, TokenStatistics, &sTokenStatistics, dwInfoLength, &dwInfoLength) )
        {
          LowPart = sTokenStatistics.ModifiedId.LowPart;
          ModifiedId = sTokenStatistics.ModifiedId;
          v17 = CEffPermsCacheLUID::Hash(v15, sTokenStatistics.ModifiedId);
          if ( !this->m_Cache.m_bLockValid )
            goto LABEL_21;
          v18 = 0;
          v19 = v17;
          EnterCriticalSection(&this->m_Cache.m_CacheLock);
          if ( *(_QWORD *)&this->m_Cache.m_cache[v19].lClient == __PAIR64__(ModifiedId.HighPart, LowPart) )
          {
            v18 = 1;
            *pTrustee = this->m_Cache.m_cache[v19].dwEffectivePermissions;
          }
          LeaveCriticalSection(&this->m_Cache.m_CacheLock);
          if ( !v18 )
          {
LABEL_21:
            v10 = ComputeEffectiveAccess(&this->m_ACLDesc, &this->m_pcb.StreamACL, hImpersonate, pTrustee);
            if ( v10 >= 0 )
            {
              v21 = sTokenStatistics.ModifiedId;
              v22 = CEffPermsCacheLUID::Hash(v20, sTokenStatistics.ModifiedId);
              if ( this->m_Cache.m_bLockValid )
              {
                v23 = *pTrustee;
                v24 = v22;
                EnterCriticalSection(&this->m_Cache.m_CacheLock);
                this->m_Cache.m_cache[v24].lClient = v21;
                this->m_Cache.m_cache[v24].dwEffectivePermissions = v23;
                LeaveCriticalSection(&this->m_Cache.m_CacheLock);
              }
            }
          }
          v7 = v25;
          v6 = 1;
        }
        else
        {
          v10 = -2147417818;
        }
      }
      else
      {
        LastError = GetLastError();
        SetThreadToken(0, 0);
        v13 = LastError == 1008;
        v14 = -2147023888;
        v6 = 1;
        if ( !v13 )
          v14 = -2147417819;
        v10 = v14;
      }
    }
    else
    {
      v10 = -2147417821;
    }
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 == 1008 )
    {
      v10 = -2147417819;
    }
    else if ( v9 > 0 )
    {
      v10 = (unsigned __int16)v9 | 0x80070000;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( hImpersonate != (void *)-1LL )
    CloseHandle(hImpersonate);
  if ( v6 )
  {
    if ( v7 )
      SetThreadToken(0, hEnter);
    else
      pSSec->RevertToSelf(pSSec);
  }
  if ( hEnter != (void *)-1LL )
    CloseHandle(hEnter);
  if ( pSSec )
    pSSec->Release(pSSec);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801cee50  mov     [rsp-8+arg_8], rbx
0x1801cee55  push    rbp
0x1801cee56  push    rsi
0x1801cee57  push    rdi
0x1801cee58  push    r12
0x1801cee5a  push    r13
0x1801cee5c  push    r14
0x1801cee5e  push    r15
0x1801cee60  lea     rbp, [rsp-27h]
0x1801cee65  sub     rsp, 0B0h
0x1801cee6c  mov     rax, cs:__security_cookie
0x1801cee73  xor     rax, rsp
0x1801cee76  mov     [rbp+57h+var_40], rax
0x1801cee7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801cee7e  mov     [rbp+57h+pSSec], 0
0x1801cee86  xorps   xmm0, xmm0
0x1801cee89  mov     [rbp+57h+hEnter], rax
0x1801cee8d  mov     [rbp+57h+hImpersonate], rax
0x1801cee91  lea     rdx, [rbp+57h+pSSec]; ppInterface
0x1801cee95  xor     eax, eax
0x1801cee97  mov     [rbp+57h+dwInfoLength], 38h ; '8'
0x1801cee9e  mov     r15, this
0x1801ceea1  mov     qword ptr [rbp+57h+sTokenStatistics.ModifiedId.LowPart], rax
0x1801ceea5  lea     this, IID_IServerSecurity; riid
0x1801ceeac  mov     rsi, pdwRights
0x1801ceeaf  movups  xmmword ptr [rbp+57h+sTokenStatistics.TokenId.LowPart], xmm0
0x1801ceeb3  movups  xmmword ptr [rbp+57h+sTokenStatistics.ExpirationTime], xmm0
0x1801ceeb7  movups  xmmword ptr [rbp+57h+sTokenStatistics.DynamicCharged], xmm0
0x1801ceebb  call    CoGetCallContext
0x1801ceec0  test    eax, eax
0x1801ceec2  jns     short loc_1801CEECE
0x1801ceec4  mov     eax, 80010124h
0x1801ceec9  jmp     loc_1801CF12A
0x1801ceece  lea     rax, [r15+28h]
0x1801ceed2  xor     ebx, ebx
0x1801ceed4  mov     this, rax; lpCriticalSection
0x1801ceed7  mov     [rbp+57h+lpCriticalSection], rax
0x1801ceedb  call    cs:__imp_EnterCriticalSection
0x1801ceee1  mov     this, [rbp+57h+pSSec]
0x1801ceee5  mov     rax, [this]
0x1801ceee8  mov     rax, [rax+30h]
0x1801ceeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ceef1  mov     [rbp+57h+var_AC], eax
0x1801ceef4  mov     r12d, eax
0x1801ceef7  lea     edi, [rbx+1]
0x1801ceefa  mov     r13d, 20008h
0x1801cef00  test    eax, eax
0x1801cef02  jz      short loc_1801CEF54
0x1801cef04  call    cs:__imp_GetCurrentThread
0x1801cef0a  lea     r9, [rbp+57h+hEnter]; TokenHandle
0x1801cef0e  mov     r8d, edi; OpenAsSelf
0x1801cef11  mov     this, rax; ThreadHandle
0x1801cef14  mov     edx, r13d; DesiredAccess
0x1801cef17  call    cs:__imp_OpenThreadToken
0x1801cef1d  test    eax, eax
0x1801cef1f  jnz     short loc_1801CEF54
0x1801cef21  call    cs:__imp_GetLastError
0x1801cef27  mov     r14d, eax
0x1801cef2a  cmp     eax, 3F0h
0x1801cef2f  jnz     short loc_1801CEF3C
0x1801cef31  mov     r14d, 80010125h
0x1801cef37  jmp     $Error_10
0x1801cef3c  test    eax, eax
0x1801cef3e  jle     $Error_10
0x1801cef44  movzx   r14d, ax
0x1801cef48  or      r14d, 80070000h
0x1801cef4f  jmp     $Error_10
0x1801cef54  mov     this, [rbp+57h+pSSec]
0x1801cef58  mov     rax, [this]
0x1801cef5b  mov     rax, [rax+20h]
0x1801cef5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cef64  mov     r14d, eax
0x1801cef67  test    eax, eax
0x1801cef69  jns     short loc_1801CEF76
0x1801cef6b  mov     r14d, 80010123h
0x1801cef71  jmp     $Error_10
0x1801cef76  mov     ebx, edi
0x1801cef78  mov     [rbp+57h+var_B0], ebx
0x1801cef7b  call    cs:__imp_GetCurrentThread
0x1801cef81  lea     r9, [rbp+57h+hImpersonate]; TokenHandle
0x1801cef85  mov     r8d, edi; OpenAsSelf
0x1801cef88  mov     this, rax; ThreadHandle
0x1801cef8b  mov     edx, r13d; DesiredAccess
0x1801cef8e  call    cs:__imp_OpenThreadToken
0x1801cef94  test    eax, eax
0x1801cef96  jnz     short loc_1801CEFC9
0x1801cef98  call    cs:__imp_GetLastError
0x1801cef9e  xor     edx, edx; Token
0x1801cefa0  xor     ecx, ecx; Thread
0x1801cefa2  mov     ebx, eax
0x1801cefa4  call    cs:__imp_SetThreadToken
0x1801cefaa  cmp     ebx, 3F0h
0x1801cefb0  mov     r14d, 80010125h
0x1801cefb6  mov     ecx, 800703F0h
0x1801cefbb  mov     ebx, edi
0x1801cefbd  cmovnz  ecx, r14d
0x1801cefc1  mov     r14d, ecx
0x1801cefc4  jmp     $Error_10
0x1801cefc9  xor     edx, edx; Token
0x1801cefcb  xor     ecx, ecx; Thread
0x1801cefcd  call    cs:__imp_SetThreadToken
0x1801cefd3  mov     r9d, [rbp+57h+dwInfoLength]; TokenInformationLength
0x1801cefd7  lea     rax, [rbp+57h+dwInfoLength]
0x1801cefdb  mov     this, [rbp+57h+hImpersonate]; TokenHandle
0x1801cefdf  lea     pdwRights, [rbp+57h+sTokenStatistics]; TokenInformation
0x1801cefe3  mov     edx, 0Ah; TokenInformationClass
0x1801cefe8  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1801cefed  call    cs:__imp_GetTokenInformation
0x1801ceff3  test    eax, eax
0x1801ceff5  jnz     short loc_1801CF002
0x1801ceff7  mov     r14d, 80010126h
0x1801ceffd  jmp     $Error_10
0x1801cf002  mov     rbx, qword ptr [rbp+57h+sTokenStatistics.ModifiedId.LowPart]
0x1801cf006  mov     rdx, rbx; lClient
0x1801cf009  mov     [rbp+57h+var_88], rbx
0x1801cf00d  call    ?Hash@CEffPermsCacheLUID@@AEAAKU_LUID@@@Z; CEffPermsCacheLUID::Hash(_LUID)
0x1801cf012  cmp     dword ptr [r15+190h], 0
0x1801cf01a  lea     r12, [r15+168h]
0x1801cf021  jz      short loc_1801CF05F
0x1801cf023  mov     eax, eax
0x1801cf025  mov     this, r12; lpCriticalSection
0x1801cf028  xor     edi, edi
0x1801cf02a  lea     r13, [rax+rax*2]
0x1801cf02e  call    cs:__imp_EnterCriticalSection
0x1801cf034  mov     rax, [r15+r13*4+50h]
0x1801cf039  cmp     eax, ebx
0x1801cf03b  jnz     short loc_1801CF052
0x1801cf03d  shr     rax, 20h
0x1801cf041  cmp     eax, dword ptr [rbp+57h+var_88+4]
0x1801cf044  jnz     short loc_1801CF052
0x1801cf046  mov     eax, [r15+r13*4+58h]
0x1801cf04b  mov     edi, 1
0x1801cf050  mov     [rsi], eax
0x1801cf052  mov     this, r12; lpCriticalSection
0x1801cf055  call    cs:__imp_LeaveCriticalSection
0x1801cf05b  test    edi, edi
0x1801cf05d  jnz     short loc_1801CF0BA
0x1801cf05f  mov     pdwRights, [rbp+57h+hImpersonate]; TokenHandle
0x1801cf063  lea     rdx, [r15+1F0h]; pStreamACL
0x1801cf06a  lea     this, [r15+198h]; pACLDesc
0x1801cf071  mov     r9, rsi; pdwRights
0x1801cf074  call    ?ComputeEffectiveAccess@@YAJPEAUtagACL_DESCRIPTOR@@PEAUtagSTREAM_ACL@@PEAXPEAK@Z; ComputeEffectiveAccess(tagACL_DESCRIPTOR *,tagSTREAM_ACL *,void *,ulong *)
0x1801cf079  mov     r14d, eax
0x1801cf07c  test    eax, eax
0x1801cf07e  js      short loc_1801CF0BA
0x1801cf080  mov     rbx, qword ptr [rbp+57h+sTokenStatistics.ModifiedId.LowPart]
0x1801cf084  mov     rdx, rbx; lClient
0x1801cf087  call    ?Hash@CEffPermsCacheLUID@@AEAAKU_LUID@@@Z; CEffPermsCacheLUID::Hash(_LUID)
0x1801cf08c  cmp     dword ptr [r15+190h], 0
0x1801cf094  jz      short loc_1801CF0BA
0x1801cf096  mov     esi, [rsi]
0x1801cf098  mov     this, r12; lpCriticalSection
0x1801cf09b  mov     eax, eax
0x1801cf09d  lea     rdi, [rax+rax*2]
0x1801cf0a1  call    cs:__imp_EnterCriticalSection
0x1801cf0a7  mov     this, r12; lpCriticalSection
0x1801cf0aa  mov     [r15+rdi*4+50h], rbx
0x1801cf0af  mov     [r15+rdi*4+58h], esi
0x1801cf0b4  call    cs:__imp_LeaveCriticalSection
0x1801cf0ba  mov     r12d, [rbp+57h+var_AC]
0x1801cf0be  mov     ebx, [rbp+57h+var_B0]
0x1801cf0c1  mov     this, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1801cf0c5  call    cs:__imp_LeaveCriticalSection
0x1801cf0cb  mov     this, [rbp+57h+hImpersonate]; hObject
0x1801cf0cf  cmp     this, 0FFFFFFFFFFFFFFFFh
0x1801cf0d3  jz      short loc_1801CF0DB
0x1801cf0d5  call    cs:__imp_CloseHandle
0x1801cf0db  test    ebx, ebx
0x1801cf0dd  jz      short loc_1801CF102
0x1801cf0df  test    r12d, r12d
0x1801cf0e2  jz      short loc_1801CF0F2
0x1801cf0e4  mov     rdx, [rbp+57h+hEnter]; Token
0x1801cf0e8  xor     ecx, ecx; Thread
0x1801cf0ea  call    cs:__imp_SetThreadToken
0x1801cf0f0  jmp     short loc_1801CF102
0x1801cf0f2  mov     this, [rbp+57h+pSSec]
0x1801cf0f6  mov     rax, [this]
0x1801cf0f9  mov     rax, [rax+28h]
0x1801cf0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf102  mov     this, [rbp+57h+hEnter]; hObject
0x1801cf106  cmp     this, 0FFFFFFFFFFFFFFFFh
0x1801cf10a  jz      short loc_1801CF112
0x1801cf10c  call    cs:__imp_CloseHandle
0x1801cf112  mov     this, [rbp+57h+pSSec]
0x1801cf116  test    this, this
0x1801cf119  jz      short loc_1801CF127
0x1801cf11b  mov     rax, [this]
0x1801cf11e  mov     rax, [rax+10h]
0x1801cf122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf127  mov     eax, r14d
0x1801cf12a  mov     this, [rbp+57h+var_40]
0x1801cf12e  xor     this, rsp; StackCookie
0x1801cf131  call    __security_check_cookie
0x1801cf136  mov     rbx, [rsp+0E0h+arg_8]
0x1801cf13e  add     rsp, 0B0h
0x1801cf145  pop     r15
0x1801cf147  pop     r14
0x1801cf149  pop     r13
0x1801cf14b  pop     r12
0x1801cf14d  pop     rdi
0x1801cf14e  pop     rsi
0x1801cf14f  pop     rbp
0x1801cf150  retn
```
