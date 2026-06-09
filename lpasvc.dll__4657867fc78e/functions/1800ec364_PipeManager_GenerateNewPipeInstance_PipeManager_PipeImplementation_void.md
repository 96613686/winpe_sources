# PipeManager::GenerateNewPipeInstance(PipeManager::PipeImplementation * &,void * &)

- ea: `0x1800ec364`
- end: `0x1800ec90a`
- name: `?GenerateNewPipeInstance@PipeManager@@AEAAJAEAPEAVPipeImplementation@1@AEAPEAX@Z`
- size: `1446`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION *this, struct PipeManager::PipeImplementation **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800ebe58`

## callees

- `0x1800017c8`
- `0x1800018b4`
- `0x18000df90`
- `0x18000e4e0`
- `0x18000ebf4`
- `0x18006ba8c`
- `0x1800cf300`
- `0x1800eb5b8`
- `0x1800ec364`
- `0x1800ee5e4`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec425`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec878`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec878`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec85d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec85d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ec687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ec687`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800ec6b1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800ec6b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec5c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec6ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec7cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec5c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec6ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec7cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec7fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec7fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ec4df`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ec4df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ec603`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ec603`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec6e2`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec759`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec6e2`
- `RPCRT4!RpcRevertToSelf` at `0x1800ec759`
- `RPCRT4!RpcBindingFree` at `0x1800ec5ac`
- `RPCRT4!RpcBindingFree` at `0x1800ec5ac`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800ec626`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800ec626`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800ec4fe`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800ec4fe`
- `RPCRT4!RpcImpersonateClient` at `0x1800ec648`
- `RPCRT4!RpcImpersonateClient` at `0x1800ec648`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800ec56c`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800ec56c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ec66e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ec66e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PipeManager::GenerateNewPipeInstance(
        LPCRITICAL_SECTION *this,
        struct PipeManager::PipeImplementation **a2,
        void **a3)
{
  PipeManager::PipeImplementation *v6; // rax
  struct PipeManager::PipeImplementation *v7; // rcx
  struct PipeManager::PipeImplementation *v8; // rbx
  __int64 v9; // rcx
  signed int LastErrorToHResultAndForceFailure; // ebx
  CommonUtil *v11; // rcx
  RPC_STATUS v12; // eax
  CommonUtil *v13; // rcx
  HANDLE v14; // r15
  __int64 v15; // r14
  CommonUtil *v16; // rcx
  RPC_STATUS v17; // eax
  RPC_STATUS v18; // eax
  CommonUtil *v19; // rcx
  HANDLE v20; // rsi
  HANDLE CurrentProcess; // rax
  CommonUtil *v22; // rcx
  RPC_STATUS v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  RPC_STATUS v27; // eax
  int v28; // r8d
  int v29; // r9d
  signed int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  signed int v33; // ecx
  RPC_BINDING_HANDLE *p_Binding; // rax
  __int16 *v35; // rdx
  RPC_BINDING_HANDLE *lpSecurityAttributes; // [rsp+38h] [rbp-C8h]
  signed int v38; // [rsp+40h] [rbp-C0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-B8h] BYREF
  const char *v40; // [rsp+50h] [rbp-B0h] BYREF
  const char *v41; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+78h] [rbp-88h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+90h] [rbp-70h] BYREF
  char v45[56]; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwProcessId; // [rsp+D0h] [rbp-30h]
  WCHAR StringSecurityDescriptor[80]; // [rsp+110h] [rbp+10h] BYREF

  memset_0(v45, 0, 0x70u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v6 = (PipeManager::PipeImplementation *)operator new(0xB0u, (const struct std::nothrow_t *)std::nothrow);
  v40 = (const char *)v6;
  if ( v6 )
    v7 = (struct PipeManager::PipeImplementation *)PipeManager::PipeImplementation::PipeImplementation(
                                                     v6,
                                                     (struct PipeManager *)this);
  else
    v7 = 0;
  *a2 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(struct PipeManager::PipeImplementation *))(*(_QWORD *)v7 + 8LL))(v7);
    v8 = *a2;
    *(_QWORD *)(*((_QWORD *)v8 + 12) + 24LL) = CreateEventW(0, 1, 0, 0);
    v9 = *((_QWORD *)v8 + 12);
    LastErrorToHResultAndForceFailure = -2147467259;
    if ( *(_QWORD *)(v9 + 24) )
      LastErrorToHResultAndForceFailure = 0;
  }
  else
  {
    LastErrorToHResultAndForceFailure = -2147024882;
  }
  if ( LastErrorToHResultAndForceFailure >= 0 )
  {
    wcscpy(StringSecurityDescriptor, L"D:(A;;GA;;;S-1-5-80-3916113136-2435487254-2535488001-4050622930-2364918814)");
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           1u,
           &SecurityAttributes.lpSecurityDescriptor,
           0)
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v11),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      v12 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
      LastErrorToHResultAndForceFailure = v12;
      if ( v12 > 0 )
        LastErrorToHResultAndForceFailure = (unsigned __int16)v12 | 0x80070000;
      if ( LastErrorToHResultAndForceFailure >= 0 )
      {
        Binding = 0;
        v43 = &PipeManager::_lockPipeManager;
        EnterCriticalSection(&PipeManager::_lockPipeManager);
        v14 = CreateNamedPipeW(
                L"\\\\.\\pipe\\ec4491ca-3d03-4eea-9b35-f103cfef314f",
                0x40000002u,
                0xEu,
                0xFFu,
                0x7D8u,
                0,
                0xFFFFFFFF,
                &SecurityAttributes);
        if ( v14 == (HANDLE)-1LL
          && (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v13),
              LastErrorToHResultAndForceFailure < 0) )
        {
          v15 = -1;
        }
        else
        {
          v15 = (__int64)CreateFileW(
                           L"\\\\.\\pipe\\ec4491ca-3d03-4eea-9b35-f103cfef314f",
                           0x80000000,
                           0,
                           &SecurityAttributes,
                           3u,
                           0x40000000u,
                           0);
          if ( v15 != -1
            || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v16),
                LastErrorToHResultAndForceFailure >= 0) )
          {
            v17 = RpcServerInqBindingHandle(&Binding);
            LastErrorToHResultAndForceFailure = v17;
            if ( v17 > 0 )
              LastErrorToHResultAndForceFailure = (unsigned __int16)v17 | 0x80070000;
            if ( LastErrorToHResultAndForceFailure >= 0 )
            {
              v18 = RpcImpersonateClient(Binding);
              LastErrorToHResultAndForceFailure = v18;
              if ( v18 > 0 )
                LastErrorToHResultAndForceFailure = (unsigned __int16)v18 | 0x80070000;
              if ( LastErrorToHResultAndForceFailure >= 0 )
              {
                v20 = OpenProcess(0x40u, 0, dwProcessId);
                if ( v20
                  || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v19),
                      LastErrorToHResultAndForceFailure >= 0) )
                {
                  CurrentProcess = GetCurrentProcess();
                  if ( !DuplicateHandle(CurrentProcess, (HANDLE)v15, v20, a3, 0, 0, 2u) )
                    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v22);
                  if ( v20 )
                    CloseHandle(v20);
                }
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
                {
                  v23 = RpcRevertToSelf();
                  LastErrorToHResultAndForceFailure = v23;
                  if ( v23 > 0 )
                    LastErrorToHResultAndForceFailure = (unsigned __int16)v23 | 0x80070000;
                  if ( LastErrorToHResultAndForceFailure < 0 && (unsigned int)CallbackContext > 2 )
                  {
                    v38 = LastErrorToHResultAndForceFailure;
                    v41 = "PipeManager::GenerateNewPipeInstance";
                    v40 = "LuiPipeManager";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      v24,
                      (unsigned int)&unk_180134E70,
                      v25,
                      v26,
                      (__int64)&v40,
                      (__int64)&v41,
                      (__int64)&v38);
                  }
                }
                else
                {
                  v27 = RpcRevertToSelf();
                  v30 = v27;
                  if ( v27 > 0 )
                    v30 = (unsigned __int16)v27 | 0x80070000;
                  if ( v30 < 0 && (unsigned int)CallbackContext > 3 )
                  {
                    v38 = v30;
                    v40 = "PipeManager::GenerateNewPipeInstance";
                    v41 = "LuiPipeManager";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      v30,
                      (unsigned int)byte_180134E33,
                      v28,
                      v29,
                      (__int64)&v41,
                      (__int64)&v40,
                      (__int64)&v38);
                  }
                }
              }
            }
          }
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl)
          && Binding )
        {
          RpcBindingFree(&Binding);
          Binding = 0;
        }
        if ( v15 != -1 )
          CloseHandle((HANDLE)v15);
        if ( LastErrorToHResultAndForceFailure < 0 )
        {
          if ( v14 != (HANDLE)-1LL )
            CloseHandle(v14);
        }
        else
        {
          *((_QWORD *)*a2 + 4) = v14;
        }
        LeaveCriticalSection(&PipeManager::_lockPipeManager);
      }
    }
  }
  if ( SecurityAttributes.lpSecurityDescriptor )
  {
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
    SecurityAttributes.lpSecurityDescriptor = 0;
  }
  if ( LastErrorToHResultAndForceFailure >= 0 )
  {
    EnterCriticalSection(this[7]);
    std::_Hash<std::_Uset_traits<PipeManager::PipeImplementation *,std::_Uhash_compare<PipeManager::PipeImplementation *,std::hash<PipeManager::PipeImplementation *>,std::equal_to<PipeManager::PipeImplementation *>>,std::allocator<PipeManager::PipeImplementation *>,0>>::emplace<PipeManager::PipeImplementation * const &>(
      this + 11,
      &v43,
      a2);
    LeaveCriticalSection(this[7]);
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(Binding) = LastErrorToHResultAndForceFailure;
      if ( *a2 )
        v33 = *((_DWORD *)*a2 + 4);
      else
        v33 = 0;
      v38 = v33;
      lpSecurityAttributes = &Binding;
      p_Binding = (RPC_BINDING_HANDLE *)&v38;
      v35 = (__int16 *)byte_180134DA9;
      goto LABEL_66;
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v38 = LastErrorToHResultAndForceFailure;
      if ( *a2 )
        v33 = *((_DWORD *)*a2 + 4);
      else
        v33 = 0;
      LODWORD(Binding) = v33;
      lpSecurityAttributes = (RPC_BINDING_HANDLE *)&v38;
      p_Binding = &Binding;
      v35 = &word_180134DEE;
LABEL_66:
      v40 = "PipeManager::GenerateNewPipeInstance";
      v41 = "LuiPipeManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v33,
        (_DWORD)v35,
        v31,
        v32,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)p_Binding,
        (__int64)lpSecurityAttributes);
    }
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800ec364  mov     [rsp-8+arg_18], rbx
0x1800ec369  push    rbp
0x1800ec36a  push    rsi
0x1800ec36b  push    rdi
0x1800ec36c  push    r12
0x1800ec36e  push    r13
0x1800ec370  push    r14
0x1800ec372  push    r15
0x1800ec374  lea     rbp, [rsp-0C0h]
0x1800ec37c  sub     rsp, 1C0h
0x1800ec383  mov     rax, cs:__security_cookie
0x1800ec38a  xor     rax, rsp
0x1800ec38d  mov     [rbp+0F0h+var_40], rax
0x1800ec394  mov     r12, r8
0x1800ec397  mov     rdi, rdx
0x1800ec39a  mov     r13, rcx
0x1800ec39d  xor     edx, edx; Val
0x1800ec39f  lea     r8d, [rdx+70h]; Size
0x1800ec3a3  lea     rcx, [rbp+0F0h+var_158]; void *
0x1800ec3a7  call    memset_0
0x1800ec3ac  mov     [rbp+0F0h+RpcCallAttributes], 3
0x1800ec3b3  mov     [rbp+0F0h+var_15C], 10h
0x1800ec3ba  xor     esi, esi
0x1800ec3bc  mov     qword ptr [rsp+1F0h+SecurityAttributes.nLength], 18h
0x1800ec3c5  mov     qword ptr [rsp+1F0h+SecurityAttributes.bInheritHandle], rsi
0x1800ec3ca  mov     [rsp+1F0h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1800ec3cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ec3d6  mov     ecx, 0B0h; unsigned __int64
0x1800ec3db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ec3e0  mov     [rsp+1F0h+var_1A0], rax
0x1800ec3e5  test    rax, rax
0x1800ec3e8  jz      short loc_1800EC3FA
0x1800ec3ea  mov     rdx, r13; struct PipeManager *
0x1800ec3ed  mov     rcx, rax; this
0x1800ec3f0  call    ??0PipeImplementation@PipeManager@@QEAA@PEAV1@@Z; PipeManager::PipeImplementation::PipeImplementation(PipeManager *)
0x1800ec3f5  mov     rcx, rax
0x1800ec3f8  jmp     short loc_1800EC3FD
0x1800ec3fa  mov     rcx, rsi
0x1800ec3fd  mov     [rdi], rcx
0x1800ec400  mov     r14d, 1
0x1800ec406  test    rcx, rcx
0x1800ec409  jz      short loc_1800EC445
0x1800ec40b  mov     rax, [rcx]
0x1800ec40e  mov     rax, [rax+8]
0x1800ec412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec417  mov     rbx, [rdi]
0x1800ec41a  xor     r9d, r9d; lpName
0x1800ec41d  xor     r8d, r8d; bInitialState
0x1800ec420  mov     edx, r14d; bManualReset
0x1800ec423  xor     ecx, ecx; lpEventAttributes
0x1800ec425  call    cs:__imp_CreateEventW
0x1800ec42b  mov     rcx, [rbx+60h]
0x1800ec42f  mov     [rcx+18h], rax
0x1800ec433  mov     rcx, [rbx+60h]
0x1800ec437  mov     ebx, 80004005h
0x1800ec43c  cmp     [rcx+18h], rsi
0x1800ec440  cmovnz  ebx, esi
0x1800ec443  jmp     short loc_1800EC44A
0x1800ec445  mov     ebx, 8007000Eh
0x1800ec44a  lea     r15, aPipemanagerGen; "PipeManager::GenerateNewPipeInstance"
0x1800ec451  test    ebx, ebx
0x1800ec453  js      loc_1800EC7E9
0x1800ec459  movaps  xmm0, xmmword ptr cs:aDAGaS158039161; "D:(A;;GA;;;S-1-5-80-3916113136-24354872"...
0x1800ec460  movups  xmmword ptr [rbp+0F0h+StringSecurityDescriptor], xmm0
0x1800ec464  movaps  xmm1, xmmword ptr cs:aDAGaS158039161+10h; ";;;S-1-5-80-3916113136-2435487254-25354"...
0x1800ec46b  movups  [rbp+0F0h+var_D0], xmm1
0x1800ec46f  movaps  xmm0, xmmword ptr cs:aDAGaS158039161+20h; "-80-3916113136-2435487254-2535488001-40"...
0x1800ec476  movups  [rbp+0F0h+var_C0], xmm0
0x1800ec47a  movaps  xmm1, xmmword ptr cs:aDAGaS158039161+30h; "113136-2435487254-2535488001-4050622930"...
0x1800ec481  movups  [rbp+0F0h+var_B0], xmm1
0x1800ec485  movaps  xmm0, xmmword ptr cs:aDAGaS158039161+40h; "435487254-2535488001-4050622930-2364918"...
0x1800ec48c  movups  [rbp+0F0h+var_A0], xmm0
0x1800ec490  movaps  xmm1, xmmword ptr cs:aDAGaS158039161+50h; "4-2535488001-4050622930-2364918814)"
0x1800ec497  movups  [rbp+0F0h+var_90], xmm1
0x1800ec49b  movaps  xmm0, xmmword ptr cs:aDAGaS158039161+60h; "8001-4050622930-2364918814)"
0x1800ec4a2  movups  [rbp+0F0h+var_80], xmm0
0x1800ec4a6  movaps  xmm1, xmmword ptr cs:aDAGaS158039161+70h; "0622930-2364918814)"
0x1800ec4ad  movups  [rbp+0F0h+var_70], xmm1
0x1800ec4b4  movaps  xmm0, xmmword ptr cs:aDAGaS158039161+80h; "2364918814)"
0x1800ec4bb  movups  [rbp+0F0h+var_60], xmm0
0x1800ec4c2  mov     rax, qword ptr cs:aDAGaS158039161+90h; "14)"
0x1800ec4c9  mov     [rbp+0F0h+var_50], rax
0x1800ec4d0  xor     r9d, r9d; SecurityDescriptorSize
0x1800ec4d3  lea     r8, [rsp+1F0h+SecurityAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x1800ec4d8  mov     edx, r14d; StringSDRevision
0x1800ec4db  lea     rcx, [rbp+0F0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800ec4df  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ec4e5  test    eax, eax
0x1800ec4e7  jnz     short loc_1800EC4F8
0x1800ec4e9  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ec4ee  mov     ebx, eax
0x1800ec4f0  test    eax, eax
0x1800ec4f2  js      loc_1800EC7E9
0x1800ec4f8  lea     rdx, [rbp+0F0h+RpcCallAttributes]; RpcCallAttributes
0x1800ec4fc  xor     ecx, ecx; ClientBinding
0x1800ec4fe  call    cs:__imp_RpcServerInqCallAttributesW
0x1800ec504  mov     ebx, eax
0x1800ec506  test    eax, eax
0x1800ec508  jle     short loc_1800EC513
0x1800ec50a  movzx   ebx, ax
0x1800ec50d  or      ebx, 80070000h
0x1800ec513  test    ebx, ebx
0x1800ec515  js      loc_1800EC7E9
0x1800ec51b  mov     [rsp+1F0h+Binding], rsi
0x1800ec520  lea     rax, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; LockHelpers::BasicLock PipeManager::_lockPipeManager
0x1800ec527  mov     [rsp+1F0h+var_178], rax
0x1800ec52c  mov     rcx, rax; lpCriticalSection
0x1800ec52f  call    cs:__imp_EnterCriticalSection
0x1800ec535  nop
0x1800ec536  lea     rax, [rsp+1F0h+SecurityAttributes]
0x1800ec53b  mov     [rsp+1F0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800ec540  mov     [rsp+1F0h+nDefaultTimeOut], 0FFFFFFFFh; nDefaultTimeOut
0x1800ec548  mov     [rsp+1F0h+nInBufferSize], esi; nInBufferSize
0x1800ec54c  mov     [rsp+1F0h+nOutBufferSize], 7D8h; nOutBufferSize
0x1800ec554  mov     edx, 40000002h; dwOpenMode
0x1800ec559  mov     r9d, 0FFh; nMaxInstances
0x1800ec55f  mov     r8d, 0Eh; dwPipeMode
0x1800ec565  lea     rcx, FileName; "\\\\.\\pipe\\ec4491ca-3d03-4eea-9b35-f1"...
0x1800ec56c  call    cs:__imp_CreateNamedPipeW
0x1800ec572  mov     r15, rax
0x1800ec575  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ec579  jnz     short loc_1800EC5DA
0x1800ec57b  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ec580  mov     ebx, eax
0x1800ec582  test    eax, eax
0x1800ec584  jns     short loc_1800EC5DA
0x1800ec586  or      r14, r15
0x1800ec589  lea     r12, aLuipipemanager; "LuiPipeManager"
0x1800ec590  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800ec597  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800ec59c  test    al, al
0x1800ec59e  jz      short loc_1800EC5B7
0x1800ec5a0  cmp     [rsp+1F0h+Binding], rsi
0x1800ec5a5  jz      short loc_1800EC5B7
0x1800ec5a7  lea     rcx, [rsp+1F0h+Binding]; Binding
0x1800ec5ac  call    cs:__imp_RpcBindingFree
0x1800ec5b2  mov     [rsp+1F0h+Binding], rsi
0x1800ec5b7  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800ec5bb  jz      short loc_1800EC5C6
0x1800ec5bd  mov     rcx, r14; hObject
0x1800ec5c0  call    cs:__imp_CloseHandle
0x1800ec5c6  test    ebx, ebx
0x1800ec5c8  js      loc_1800EC7C3
0x1800ec5ce  mov     rax, [rdi]
0x1800ec5d1  mov     [rax+20h], r15
0x1800ec5d5  jmp     loc_1800EC7D3
0x1800ec5da  mov     qword ptr [rsp+1F0h+nDefaultTimeOut], rsi; hTemplateFile
0x1800ec5df  mov     [rsp+1F0h+nInBufferSize], 40000000h; dwFlagsAndAttributes
0x1800ec5e7  mov     [rsp+1F0h+nOutBufferSize], 3; dwCreationDisposition
0x1800ec5ef  lea     r9, [rsp+1F0h+SecurityAttributes]; lpSecurityAttributes
0x1800ec5f4  xor     r8d, r8d; dwShareMode
0x1800ec5f7  mov     edx, 80000000h; dwDesiredAccess
0x1800ec5fc  lea     rcx, FileName; "\\\\.\\pipe\\ec4491ca-3d03-4eea-9b35-f1"...
0x1800ec603  call    cs:__imp_CreateFileW
0x1800ec609  mov     r14, rax
0x1800ec60c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ec610  jnz     short loc_1800EC621
0x1800ec612  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ec617  mov     ebx, eax
0x1800ec619  test    eax, eax
0x1800ec61b  js      loc_1800EC589
0x1800ec621  lea     rcx, [rsp+1F0h+Binding]; Binding
0x1800ec626  call    cs:__imp_RpcServerInqBindingHandle
0x1800ec62c  mov     ebx, eax
0x1800ec62e  test    eax, eax
0x1800ec630  jle     short loc_1800EC63B
0x1800ec632  movzx   ebx, ax
0x1800ec635  or      ebx, 80070000h
0x1800ec63b  test    ebx, ebx
0x1800ec63d  js      loc_1800EC589
0x1800ec643  mov     rcx, [rsp+1F0h+Binding]; BindingHandle
0x1800ec648  call    cs:__imp_RpcImpersonateClient
0x1800ec64e  mov     ebx, eax
0x1800ec650  test    eax, eax
0x1800ec652  jle     short loc_1800EC65D
0x1800ec654  movzx   ebx, ax
0x1800ec657  or      ebx, 80070000h
0x1800ec65d  test    ebx, ebx
0x1800ec65f  js      loc_1800EC589
0x1800ec665  mov     r8d, [rbp+0F0h+dwProcessId]; dwProcessId
0x1800ec669  xor     edx, edx; bInheritHandle
0x1800ec66b  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800ec66e  call    cs:__imp_OpenProcess
0x1800ec674  mov     rsi, rax
0x1800ec677  test    rax, rax
0x1800ec67a  jnz     short loc_1800EC687
0x1800ec67c  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ec681  mov     ebx, eax
0x1800ec683  test    eax, eax
0x1800ec685  js      short loc_1800EC6D0
0x1800ec687  call    cs:__imp_GetCurrentProcess
0x1800ec68d  mov     rcx, rax; hSourceProcessHandle
0x1800ec690  mov     [rsp+1F0h+nDefaultTimeOut], 2; dwOptions
0x1800ec698  mov     [rsp+1F0h+nInBufferSize], 0; bInheritHandle
0x1800ec6a0  mov     [rsp+1F0h+nOutBufferSize], 0; dwDesiredAccess
0x1800ec6a8  mov     r9, r12; lpTargetHandle
0x1800ec6ab  mov     r8, rsi; hTargetProcessHandle
0x1800ec6ae  mov     rdx, r14; hSourceHandle
0x1800ec6b1  call    cs:__imp_DuplicateHandle
0x1800ec6b7  test    eax, eax
0x1800ec6b9  jnz     short loc_1800EC6C2
0x1800ec6bb  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ec6c0  mov     ebx, eax
0x1800ec6c2  test    rsi, rsi
0x1800ec6c5  jz      short loc_1800EC6D0
0x1800ec6c7  mov     rcx, rsi; hObject
0x1800ec6ca  call    cs:__imp_CloseHandle
0x1800ec6d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800ec6d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800ec6dc  xor     esi, esi
0x1800ec6de  test    al, al
0x1800ec6e0  jz      short loc_1800EC759
0x1800ec6e2  call    cs:__imp_RpcRevertToSelf
0x1800ec6e8  mov     ebx, eax
0x1800ec6ea  test    eax, eax
0x1800ec6ec  jle     short loc_1800EC6F7
0x1800ec6ee  movzx   ebx, ax
0x1800ec6f1  or      ebx, 80070000h
0x1800ec6f7  test    ebx, ebx
0x1800ec6f9  jns     loc_1800EC589
0x1800ec6ff  mov     eax, cs:CallbackContext
0x1800ec705  cmp     eax, 2
0x1800ec708  jbe     loc_1800EC589
0x1800ec70e  mov     [rsp+1F0h+var_1B0], ebx
0x1800ec712  lea     rax, aPipemanagerGen; "PipeManager::GenerateNewPipeInstance"
0x1800ec719  mov     [rsp+1F0h+var_198], rax
0x1800ec71e  lea     r12, aLuipipemanager; "LuiPipeManager"
0x1800ec725  mov     [rsp+1F0h+var_1A0], r12
0x1800ec72a  lea     rax, [rsp+1F0h+var_1B0]
0x1800ec72f  mov     qword ptr [rsp+1F0h+nDefaultTimeOut], rax
0x1800ec734  lea     rax, [rsp+1F0h+var_198]
0x1800ec739  mov     qword ptr [rsp+1F0h+nInBufferSize], rax
0x1800ec73e  lea     rax, [rsp+1F0h+var_1A0]
0x1800ec743  lea     rdx, unk_180134E70
0x1800ec74a  mov     qword ptr [rsp+1F0h+nOutBufferSize], rax
0x1800ec74f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ec754  jmp     loc_1800EC590
0x1800ec759  call    cs:__imp_RpcRevertToSelf
0x1800ec75f  mov     ecx, eax
0x1800ec761  test    eax, eax
0x1800ec763  jle     short loc_1800EC76E
0x1800ec765  movzx   ecx, ax
0x1800ec768  or      ecx, 80070000h
0x1800ec76e  test    ecx, ecx
0x1800ec770  jns     loc_1800EC589
0x1800ec776  mov     eax, cs:CallbackContext
0x1800ec77c  cmp     eax, 3
0x1800ec77f  jbe     loc_1800EC589
0x1800ec785  mov     [rsp+1F0h+var_1B0], ecx
0x1800ec789  lea     rax, aPipemanagerGen; "PipeManager::GenerateNewPipeInstance"
0x1800ec790  mov     [rsp+1F0h+var_1A0], rax
0x1800ec795  lea     r12, aLuipipemanager; "LuiPipeManager"
0x1800ec79c  mov     [rsp+1F0h+var_198], r12
0x1800ec7a1  lea     rax, [rsp+1F0h+var_1B0]
0x1800ec7a6  mov     qword ptr [rsp+1F0h+nDefaultTimeOut], rax
0x1800ec7ab  lea     rax, [rsp+1F0h+var_1A0]
0x1800ec7b0  mov     qword ptr [rsp+1F0h+nInBufferSize], rax
0x1800ec7b5  lea     rax, [rsp+1F0h+var_198]
0x1800ec7ba  lea     rdx, byte_180134E33
0x1800ec7c1  jmp     short loc_1800EC74A
0x1800ec7c3  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800ec7c7  jz      short loc_1800EC7D3
0x1800ec7c9  mov     rcx, r15; hObject
0x1800ec7cc  call    cs:__imp_CloseHandle
0x1800ec7d2  nop
0x1800ec7d3  lea     rcx, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; lpCriticalSection
0x1800ec7da  call    cs:__imp_LeaveCriticalSection
0x1800ec7e0  lea     r15, aPipemanagerGen; "PipeManager::GenerateNewPipeInstance"
0x1800ec7e7  jmp     short loc_1800EC7F0
0x1800ec7e9  lea     r12, aLuipipemanager; "LuiPipeManager"
0x1800ec7f0  mov     rcx, [rsp+1F0h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x1800ec7f5  test    rcx, rcx
0x1800ec7f8  jz      short loc_1800EC805
0x1800ec7fa  call    cs:__imp_LocalFree
0x1800ec800  mov     [rsp+1F0h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1800ec805  test    ebx, ebx
0x1800ec807  jns     short loc_1800EC859
0x1800ec809  mov     rcx, [rdi]
0x1800ec80c  mov     rax, [rcx]
0x1800ec80f  mov     rax, [rax+10h]
0x1800ec813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec818  mov     [rdi], rsi
0x1800ec81b  mov     eax, cs:CallbackContext
0x1800ec821  cmp     eax, 2
0x1800ec824  jbe     loc_1800EC8DE
0x1800ec82a  mov     [rsp+1F0h+var_1B0], ebx
0x1800ec82e  mov     rax, [rdi]
0x1800ec831  test    rax, rax
0x1800ec834  jz      short loc_1800EC83B
0x1800ec836  mov     ecx, [rax+10h]
0x1800ec839  jmp     short loc_1800EC83D
0x1800ec83b  mov     ecx, esi
0x1800ec83d  mov     dword ptr [rsp+1F0h+Binding], ecx
0x1800ec841  lea     rax, [rsp+1F0h+var_1B0]
0x1800ec846  mov     [rsp+1F0h+lpSecurityAttributes], rax
0x1800ec84b  lea     rax, [rsp+1F0h+Binding]
0x1800ec850  lea     rdx, word_180134DEE
0x1800ec857  jmp     short loc_1800EC8B6
0x1800ec859  mov     rcx, [r13+38h]; lpCriticalSection
0x1800ec85d  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
