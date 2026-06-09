# CServerSecurity::ImpersonateClient(void)

- ea: `0x1800e67f0`
- end: `0x1800e6b3a`
- name: `?ImpersonateClient@CServerSecurity@@UEAAJXZ`
- size: `842`
- prototype: `HRESULT __fastcall(CServerSecurity *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006250`
- `0x180006390`
- `0x1800188a0`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x18003cf8c`
- `0x18005cde8`
- `0x18005ce60`
- `0x18005ce9c`
- `0x1800e67f0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800e686e`
- `RPCRT4!RpcImpersonateClient` at `0x1800e686e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e69d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024b90a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e69d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6b04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024b90a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e6909`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e6909`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e695a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e69e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e695a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e69e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e691b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e691b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e6839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e6839`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e684e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e684e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800e6946`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800e6946`

## string_xrefs

- `0x1800e68ad`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e68ca`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e696e`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e69f8`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e6a43`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e6a79`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e6ad1`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800e6b18`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18024b8ba`: `onecore\com\combase\dcomrem\security.cxx`

## pseudocode

```c
HRESULT __fastcall CServerSecurity::ImpersonateClient(CServerSecurity *this)
{
  tagSOleTlsData *ReservedForOle; // rax
  void **p_hRevert; // rbx
  HANDLE CurrentThread; // rax
  RPC_STATUS v5; // eax
  HRESULT v7; // ebx
  HRESULT LastError; // eax
  void *hToken; // rdx
  HRESULT v10; // eax
  HANDLE CurrentProcess; // rax
  CChannelHandle *pHandle; // rax
  const char *v13; // r9
  CChannelHandle *v14; // rdx
  void *v15; // rax
  void *hRevert; // rcx
  void *m_ptr; // rcx
  bool v18; // cc
  void *v19; // rcx
  unsigned int v20; // edx
  void *v21; // rcx
  void *v22; // rcx
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > processToken; // [rsp+20h] [rbp-10h] BYREF
  void *retaddr; // [rsp+58h] [rbp+28h]
  COleTls tls; // [rsp+68h] [rbp+38h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > oldThreadToken; // [rsp+70h] [rbp+40h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > newThreadToken; // [rsp+78h] [rbp+48h] BYREF

  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  tls._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    v7 = COleTls::TLSAllocData(&tls);
    if ( v7 < 0 )
    {
      v20 = 4206;
      goto LABEL_40;
    }
    ReservedForOle = tls._pData;
  }
  if ( (this->_iFlags & 1) == 0 )
  {
    if ( (ReservedForOle->dwFlags & 0x200) == 0 )
    {
      p_hRevert = &ReservedForOle->hRevert;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, p_hRevert) && GetLastError() != 1008 )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 0x1078u,
                 "onecore\\com\\combase\\dcomrem\\security.cxx");
    }
    if ( this->_callLocality )
    {
      v5 = RpcImpersonateClient(this->_hRpc);
      if ( !v5 )
      {
LABEL_8:
        tls._pData->dwFlags |= 0x200u;
        return 0;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    0x10ABu,
                    "onecore\\com\\combase\\dcomrem\\security.cxx",
                    v5);
      goto LABEL_28;
    }
    hToken = this->_pHandle->_hToken;
    if ( hToken )
    {
      if ( SetThreadToken(0, hToken) )
        goto LABEL_8;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x10A5u,
                    "onecore\\com\\combase\\dcomrem\\security.cxx");
LABEL_28:
      v7 = LastError;
      if ( (tls._pData->dwFlags & 0x200) == 0 )
      {
        hRevert = tls._pData->hRevert;
        if ( hRevert )
        {
          CloseHandle(hRevert);
          tls._pData->hRevert = 0;
        }
      }
      return v7;
    }
    oldThreadToken.m_ptr = 0;
    v10 = SuspendImpersonate(&oldThreadToken.m_ptr);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x108Eu, "onecore\\com\\combase\\dcomrem\\security.cxx", v10);
      m_ptr = oldThreadToken.m_ptr;
      v18 = (unsigned __int64)oldThreadToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    }
    else
    {
      processToken.m_ptr = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 2u, &processToken.m_ptr) )
      {
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               0x1092u,
               "onecore\\com\\combase\\dcomrem\\security.cxx");
LABEL_45:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&processToken);
        v21 = oldThreadToken.m_ptr;
        oldThreadToken.m_ptr = 0;
        ResumeImpersonate(v21);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&oldThreadToken);
LABEL_46:
        if ( (tls._pData->dwFlags & 0x200) == 0 )
        {
          v22 = tls._pData->hRevert;
          if ( v22 )
          {
            CloseHandle(v22);
            tls._pData->hRevert = 0;
          }
        }
        return v7;
      }
      pHandle = this->_pHandle;
      newThreadToken.m_ptr = 0;
      if ( DuplicateToken(processToken.m_ptr, ImpLevelToSecLevel[pHandle->_lImp], &newThreadToken.m_ptr) )
      {
        if ( SetThreadToken(0, newThreadToken.m_ptr) )
        {
          COleStaticMutexSem::Request(&gComLock, "onecore\\com\\combase\\dcomrem\\security.cxx", 0x109Cu, v13);
          v14 = this->_pHandle;
          if ( !v14->_hToken )
          {
            v15 = newThreadToken.m_ptr;
            newThreadToken.m_ptr = 0;
            v14->_hToken = v15;
          }
          COleStaticMutexSem::Release(&gComLock);
          if ( (unsigned __int64)newThreadToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(newThreadToken.m_ptr);
          if ( (unsigned __int64)processToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(processToken.m_ptr);
          if ( (unsigned __int64)oldThreadToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(oldThreadToken.m_ptr);
          goto LABEL_8;
        }
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               0x1096u,
               "onecore\\com\\combase\\dcomrem\\security.cxx");
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&newThreadToken);
        goto LABEL_45;
      }
      v7 = wil::details::in1diag3::Return_GetLastError(retaddr, 0x1095u, "onecore\\com\\combase\\dcomrem\\security.cxx");
      if ( (unsigned __int64)newThreadToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(newThreadToken.m_ptr);
      if ( (unsigned __int64)processToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(processToken.m_ptr);
      v19 = oldThreadToken.m_ptr;
      oldThreadToken.m_ptr = 0;
      ResumeImpersonate(v19);
      m_ptr = oldThreadToken.m_ptr;
      v18 = (unsigned __int64)oldThreadToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL;
    }
    if ( v18 )
      CloseHandle(m_ptr);
    goto LABEL_46;
  }
  v7 = -2147417833;
  v20 = 4209;
LABEL_40:
  wil::details::in1diag3::Return_Hr(retaddr, v20, "onecore\\com\\combase\\dcomrem\\security.cxx", v7);
  return v7;
}

```

## disassembly

```asm
0x1800e67f0  push    rbp
0x1800e67f2  push    rbx
0x1800e67f3  push    rsi
0x1800e67f4  push    rdi
0x1800e67f5  push    r14
0x1800e67f7  mov     rbp, rsp
0x1800e67fa  sub     rsp, 30h
0x1800e67fe  mov     rax, gs:30h
0x1800e6807  xor     esi, esi
0x1800e6809  mov     rdi, this
0x1800e680c  mov     rax, [rax+1758h]
0x1800e6813  mov     [rbp+tls._pData], rax
0x1800e6817  test    rax, rax
0x1800e681a  jz      short loc_1800E688D
0x1800e681c  test    byte ptr [rdi+34h], 1
0x1800e6820  jnz     loc_1800E6AC3
0x1800e6826  mov     r14d, 200h
0x1800e682c  test    [rax+14h], r14d
0x1800e6830  jnz     short loc_1800E6865
0x1800e6832  lea     rbx, [rax+0E8h]
0x1800e6839  call    cs:__imp_GetCurrentThread
0x1800e683f  mov     edx, 4; DesiredAccess
0x1800e6844  mov     r9, rbx; TokenHandle
0x1800e6847  mov     this, rax; ThreadHandle
0x1800e684a  lea     r8d, [rdx-3]; OpenAsSelf
0x1800e684e  call    cs:__imp_OpenThreadToken
0x1800e6854  test    eax, eax
0x1800e6856  jnz     short loc_1800E6865
0x1800e6858  call    cs:__imp_GetLastError
0x1800e685e  cmp     eax, 3F0h
0x1800e6863  jnz     short loc_1800E68C6
0x1800e6865  cmp     [rdi+68h], esi
0x1800e6868  jz      short loc_1800E68DD
0x1800e686a  mov     this, [rdi+40h]; BindingHandle
0x1800e686e  call    cs:__imp_RpcImpersonateClient
0x1800e6874  test    eax, eax
0x1800e6876  jnz     short loc_1800E68A9
0x1800e6878  mov     rax, [rbp+tls._pData]
0x1800e687c  or      [rax+14h], r14d
0x1800e6880  xor     eax, eax
0x1800e6882  add     rsp, 30h
0x1800e6886  pop     r14
0x1800e6888  pop     rdi
0x1800e6889  pop     rsi
0x1800e688a  pop     rbx
0x1800e688b  pop     rbp
0x1800e688c  retn
0x1800e688d  lea     this, [rbp+tls]; this
0x1800e6891  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x1800e6896  mov     ebx, eax
0x1800e6898  test    eax, eax
0x1800e689a  js      loc_1800E6AE7
0x1800e68a0  mov     rax, [rbp+tls._pData]
0x1800e68a4  jmp     loc_1800E681C
0x1800e68a9  mov     this, [rbp+28h]; callerReturnAddress
0x1800e68ad  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e68b4  mov     r9d, eax; err
0x1800e68b7  mov     edx, 10ABh; lineNumber
0x1800e68bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e68c1  jmp     loc_1800E6A09
0x1800e68c6  mov     this, [rbp+28h]; callerReturnAddress
0x1800e68ca  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e68d1  mov     edx, 1078h; lineNumber
0x1800e68d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e68db  jmp     short loc_1800E6882
0x1800e68dd  mov     rax, [rdi+38h]
0x1800e68e1  mov     rdx, [rax+20h]; Token
0x1800e68e5  test    rdx, rdx
0x1800e68e8  jnz     loc_1800E69E4
0x1800e68ee  lea     this, [rbp+oldThreadToken]; pHandle
0x1800e68f2  mov     [rbp+oldThreadToken.m_ptr], rsi
0x1800e68f6  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800e68fb  mov     ebx, eax
0x1800e68fd  test    eax, eax
0x1800e68ff  js      loc_1800E6A3F
0x1800e6905  mov     [rbp+processToken.m_ptr], rsi
0x1800e6909  call    cs:__imp_GetCurrentProcess
0x1800e690f  lea     r8, [rbp+processToken]; TokenHandle
0x1800e6913  mov     edx, 2; DesiredAccess
0x1800e6918  mov     this, rax; ProcessHandle
0x1800e691b  call    cs:__imp_OpenProcessToken
0x1800e6921  test    eax, eax
0x1800e6923  jz      loc_18024B8B6
0x1800e6929  mov     rax, [rdi+38h]
0x1800e692d  lea     r8, [rbp+newThreadToken]; DuplicateTokenHandle
0x1800e6931  mov     this, [rbp+processToken.m_ptr]; ExistingTokenHandle
0x1800e6935  mov     [rbp+newThreadToken.m_ptr], rsi
0x1800e6939  mov     edx, [rax+1Ch]
0x1800e693c  lea     rax, ImpLevelToSecLevel
0x1800e6943  mov     edx, [rax+rdx*4]; ImpersonationLevel
0x1800e6946  call    cs:__imp_DuplicateToken
0x1800e694c  test    eax, eax
0x1800e694e  jz      loc_1800E6A75
0x1800e6954  mov     rdx, [rbp+newThreadToken.m_ptr]; Token
0x1800e6958  xor     ecx, ecx; Thread
0x1800e695a  call    cs:__imp_SetThreadToken
0x1800e6960  test    eax, eax
0x1800e6962  jz      loc_1800E6B14
0x1800e6968  mov     r8d, 109Ch; dwLine
0x1800e696e  lea     rdx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e6975  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x1800e697c  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1800e6981  mov     rdx, [rdi+38h]
0x1800e6985  cmp     [rdx+20h], rsi
0x1800e6989  jnz     short loc_1800E6997
0x1800e698b  mov     rax, [rbp+newThreadToken.m_ptr]
0x1800e698f  mov     [rbp+newThreadToken.m_ptr], rsi
0x1800e6993  mov     [rdx+20h], rax
0x1800e6997  lea     this, ?gComLock@@3VCOleStaticMutexSem@@A; this
0x1800e699e  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x1800e69a3  mov     this, [rbp+newThreadToken.m_ptr]; hObject
0x1800e69a7  lea     rax, [this-1]
0x1800e69ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e69af  jbe     loc_1800E6AEE
0x1800e69b5  mov     this, [rbp+processToken.m_ptr]; hObject
0x1800e69b9  lea     rax, [this-1]
0x1800e69bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e69c1  jbe     loc_1800E6AF9
0x1800e69c7  mov     this, [rbp+oldThreadToken.m_ptr]; hObject
0x1800e69cb  lea     rax, [this-1]
0x1800e69cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e69d3  ja      loc_1800E6878
0x1800e69d9  call    cs:__imp_CloseHandle
0x1800e69df  jmp     loc_1800E6878
0x1800e69e4  xor     ecx, ecx; Thread
0x1800e69e6  call    cs:__imp_SetThreadToken
0x1800e69ec  test    eax, eax
0x1800e69ee  jnz     loc_1800E6878
0x1800e69f4  mov     this, [rbp+28h]; callerReturnAddress
0x1800e69f8  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e69ff  mov     edx, 10A5h; lineNumber
0x1800e6a04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e6a09  mov     this, [rbp+tls._pData]
0x1800e6a0d  mov     ebx, eax
0x1800e6a0f  test    [this+14h], r14d
0x1800e6a13  jnz     loc_1800E6AE0
0x1800e6a19  mov     this, [this+0E8h]; hObject
0x1800e6a20  test    this, this
0x1800e6a23  jz      loc_1800E6AE0
0x1800e6a29  call    cs:__imp_CloseHandle
0x1800e6a2f  mov     this, [rbp+tls._pData]
0x1800e6a33  mov     [this+0E8h], rsi
0x1800e6a3a  jmp     loc_1800E6AE0
0x1800e6a3f  mov     this, [rbp+28h]; callerReturnAddress
0x1800e6a43  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e6a4a  mov     r9d, ebx; hr
0x1800e6a4d  mov     edx, 108Eh; lineNumber
0x1800e6a52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6a57  mov     this, [rbp+oldThreadToken.m_ptr]; hObject
0x1800e6a5b  lea     rdx, [this-1]
0x1800e6a5f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800e6a63  ja      loc_18024B8EC
0x1800e6a69  call    cs:__imp_CloseHandle
0x1800e6a6f  nop
0x1800e6a70  jmp     loc_18024B8EC
0x1800e6a75  mov     this, [rbp+28h]; callerReturnAddress
0x1800e6a79  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e6a80  mov     edx, 1095h; lineNumber
0x1800e6a85  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e6a8a  mov     this, [rbp+newThreadToken.m_ptr]; hObject
0x1800e6a8e  mov     ebx, eax
0x1800e6a90  lea     rdx, [this-1]
0x1800e6a94  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800e6a98  jbe     short loc_1800E6B04
0x1800e6a9a  mov     this, [rbp+processToken.m_ptr]; hObject
0x1800e6a9e  lea     rdx, [this-1]
0x1800e6aa2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800e6aa6  jbe     short loc_1800E6B0C
0x1800e6aa8  mov     this, [rbp+oldThreadToken.m_ptr]; hToken
0x1800e6aac  mov     [rbp+oldThreadToken.m_ptr], rsi
0x1800e6ab0  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800e6ab5  mov     this, [rbp+oldThreadToken.m_ptr]
0x1800e6ab9  lea     rax, [this-1]
0x1800e6abd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e6ac1  jmp     short loc_1800E6A63
0x1800e6ac3  mov     ebx, 80010117h
0x1800e6ac8  mov     edx, 1071h; lineNumber
0x1800e6acd  mov     this, [rbp+28h]; callerReturnAddress
0x1800e6ad1  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e6ad8  mov     r9d, ebx; hr
0x1800e6adb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6ae0  mov     eax, ebx
0x1800e6ae2  jmp     loc_1800E6882
0x1800e6ae7  mov     edx, 106Eh
0x1800e6aec  jmp     short loc_1800E6ACD
0x1800e6aee  call    cs:__imp_CloseHandle
0x1800e6af4  jmp     loc_1800E69B5
0x1800e6af9  call    cs:__imp_CloseHandle
0x1800e6aff  jmp     loc_1800E69C7
0x1800e6b04  call    cs:__imp_CloseHandle
0x1800e6b0a  jmp     short loc_1800E6A9A
0x1800e6b0c  call    cs:__imp_CloseHandle
0x1800e6b12  jmp     short loc_1800E6AA8
0x1800e6b14  mov     this, [rbp+28h]; callerReturnAddress
0x1800e6b18  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800e6b1f  mov     edx, 1096h; lineNumber
0x1800e6b24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e6b29  lea     this, [rbp+newThreadToken]; this
0x1800e6b2d  mov     ebx, eax
0x1800e6b2f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6b34  nop
0x1800e6b35  jmp     loc_18024B8CD
0x18024b8b6  mov     rcx, [rbp+28h]; callerReturnAddress
0x18024b8ba  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18024b8c1  mov     edx, 1092h; lineNumber
0x18024b8c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18024b8cb  mov     ebx, eax
0x18024b8cd  lea     rcx, [rbp+processToken]; this
0x18024b8d1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18024b8d6  mov     rcx, [rbp+oldThreadToken.m_ptr]; hToken
0x18024b8da  mov     [rbp+oldThreadToken.m_ptr], rsi
0x18024b8de  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18024b8e3  lea     rcx, [rbp+oldThreadToken]; this
0x18024b8e7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18024b8ec  mov     rcx, [rbp+tls._pData]
0x18024b8f0  test    [rcx+14h], r14d
0x18024b8f4  jnz     loc_1800E6AE0
0x18024b8fa  mov     rcx, [rcx+0E8h]; hObject
0x18024b901  test    rcx, rcx
0x18024b904  jz      loc_1800E6AE0
0x18024b90a  call    cs:__imp_CloseHandle
0x18024b910  mov     rax, [rbp+tls._pData]
0x18024b914  mov     [rax+0E8h], rsi
0x18024b91b  jmp     loc_1800E6AE0
```
