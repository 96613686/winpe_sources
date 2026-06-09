# CSpJobMgr::CleanupJob(_GUID,SpSubsystemType,int)

- ea: `0x18005ebd8`
- end: `0x18005edd8`
- name: `?CleanupJob@CSpJobMgr@@QEAAHU_GUID@@W4SpSubsystemType@@H@Z`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180014f20`
- `0x180025570`

## callees

- `0x1800011c4`
- `0x18005ebd8`
- `0x1800607b8`
- `0x18006102c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ed11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ed11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ed2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ed2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005edaf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005edaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ec4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ed70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ec4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ed70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005edbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005edbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ec7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ec7a`

## pseudocode

```c
__int64 __fastcall CSpJobMgr::CleanupJob(__int64 a1, __int128 *a2, unsigned int a3, int a4)
{
  LPCRITICAL_SECTION v7; // rbx
  _DWORD *v8; // rsi
  unsigned int v9; // edi
  int DebugInfo_high; // r12d
  __int128 *v11; // r13
  int v12; // r8d
  int v13; // r9d
  HANDLE CurrentThread; // rax
  int v16; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v20 = 603;
    *(_QWORD *)&v18 = "CSpJobMgr::CleanupJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpJobMgr::CleanupJob",
      (unsigned int)&dword_18031132C,
      a3,
      a4,
      (__int64)&v18,
      (__int64)&v20);
  }
  v7 = MISpaceHandle::g_MISpaceHandle;
  v8 = 0;
  TokenHandle = 0;
  v9 = 1;
  EnterCriticalSection(MISpaceHandle::g_MISpaceHandle);
  DebugInfo_high = HIDWORD(v7[1].DebugInfo);
  LeaveCriticalSection(v7);
  if ( a4 || DebugInfo_high )
    goto LABEL_7;
  v8 = LocalAlloc(0, 0x20u);
  if ( !v8
    || a3 != -1
    && (CurrentThread = GetCurrentThread(), !OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle))
    && GetLastError() != 1008 )
  {
    v9 = 0;
LABEL_7:
    v11 = a2;
LABEL_8:
    v18 = *v11;
    CSpJobMgr::_RemoveJob(a1, &v18, a3);
    goto LABEL_9;
  }
  v11 = a2;
  v8[6] = a3;
  *(_OWORD *)v8 = *a2;
  *((_QWORD *)v8 + 2) = TokenHandle;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)(a1 + 368) + 8LL))(a1 + 368, v8) )
  {
    if ( a3 != -1 )
      _InterlockedAdd((volatile signed __int32 *)(a1 + 48), 1u);
    v8 = 0;
    v16 = 0;
    SetEvent(*(HANDLE *)(a1 + 64));
  }
  else
  {
    v16 = 1;
    v9 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( v16 )
    goto LABEL_8;
LABEL_9:
  SuFreeTpContext(v8);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v20 = 683;
    *(_QWORD *)&v18 = "CSpJobMgr::CleanupJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18039EB68,
      (unsigned int)&dword_1803114E4,
      v12,
      v13,
      (__int64)&v18,
      (__int64)&v20);
  }
  return v9;
}

```

## disassembly

```asm
0x18005ebd8  mov     r11, rsp
0x18005ebdb  mov     [r11+8], rbx
0x18005ebdf  mov     [r11+10h], rdx
0x18005ebe3  push    rbp
0x18005ebe4  push    rsi
0x18005ebe5  push    rdi
0x18005ebe6  push    r12
0x18005ebe8  push    r13
0x18005ebea  push    r14
0x18005ebec  push    r15
0x18005ebee  mov     rbp, rsp
0x18005ebf1  sub     rsp, 50h
0x18005ebf5  mov     eax, cs:dword_18039EB68
0x18005ebfb  mov     r14, rcx
0x18005ebfe  lea     rcx, aCspjobmgrClean; "CSpJobMgr::CleanupJob"
0x18005ec05  mov     r13d, r9d
0x18005ec08  mov     r15d, r8d
0x18005ec0b  cmp     eax, 5
0x18005ec0e  jbe     short loc_18005EC37
0x18005ec10  lea     rax, [rbp+arg_18]
0x18005ec14  mov     [rbp+arg_18], 25Bh
0x18005ec1b  mov     [r11-60h], rax
0x18005ec1f  lea     rdx, dword_18031132C
0x18005ec26  lea     rax, [rbp+var_10]
0x18005ec2a  mov     qword ptr [rbp+var_10], rcx
0x18005ec2e  mov     [r11-68h], rax
0x18005ec32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005ec37  mov     rbx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; MISpaceHandle * MISpaceHandle::g_MISpaceHandle
0x18005ec3e  xor     esi, esi
0x18005ec40  mov     rcx, rbx; lpCriticalSection
0x18005ec43  mov     [rbp+TokenHandle], rsi
0x18005ec47  mov     edi, 1
0x18005ec4c  call    cs:__imp_EnterCriticalSection
0x18005ec53  nop     dword ptr [rax+rax+00h]
0x18005ec58  mov     r12d, [rbx+2Ch]
0x18005ec5c  mov     rcx, rbx; lpCriticalSection
0x18005ec5f  call    cs:__imp_LeaveCriticalSection
0x18005ec66  nop     dword ptr [rax+rax+00h]
0x18005ec6b  test    r13d, r13d
0x18005ec6e  jnz     short loc_18005EC90
0x18005ec70  test    r12d, r12d
0x18005ec73  jnz     short loc_18005EC90
0x18005ec75  lea     edx, [rdi+1Fh]; uBytes
0x18005ec78  xor     ecx, ecx; uFlags
0x18005ec7a  call    cs:__imp_LocalAlloc
0x18005ec81  nop     dword ptr [rax+rax+00h]
0x18005ec86  mov     rsi, rax
0x18005ec89  test    rax, rax
0x18005ec8c  jnz     short loc_18005ED0B
0x18005ec8e  xor     edi, edi
0x18005ec90  mov     r13, [rbp+arg_8]
0x18005ec94  movups  xmm0, xmmword ptr [r13+0]
0x18005ec99  mov     r8d, r15d
0x18005ec9c  lea     rdx, [rbp+var_10]
0x18005eca0  mov     rcx, r14
0x18005eca3  movdqu  [rbp+var_10], xmm0
0x18005eca8  call    ?_RemoveJob@CSpJobMgr@@AEAAHU_GUID@@W4SpSubsystemType@@@Z; CSpJobMgr::_RemoveJob(_GUID,SpSubsystemType)
0x18005ecad  mov     rcx, rsi; hMem
0x18005ecb0  call    ?SuFreeTpContext@@YAXPEAU_SU_TP_CONTEXT@@@Z; SuFreeTpContext(_SU_TP_CONTEXT *)
0x18005ecb5  mov     ecx, cs:dword_18039EB68
0x18005ecbb  cmp     ecx, 5
0x18005ecbe  jbe     short loc_18005ECF0
0x18005ecc0  lea     rax, aCspjobmgrClean; "CSpJobMgr::CleanupJob"
0x18005ecc7  mov     [rbp+arg_18], 2ABh
0x18005ecce  mov     qword ptr [rbp+var_10], rax
0x18005ecd2  lea     rdx, dword_1803114E4
0x18005ecd9  lea     rax, [rbp+arg_18]
0x18005ecdd  mov     [rsp+50h+var_28], rax
0x18005ece2  lea     rax, [rbp+var_10]
0x18005ece6  mov     [rsp+50h+var_30], rax
0x18005eceb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005ecf0  mov     rbx, [rsp+50h+arg_0]
0x18005ecf8  mov     eax, edi
0x18005ecfa  add     rsp, 50h
0x18005ecfe  pop     r15
0x18005ed00  pop     r14
0x18005ed02  pop     r13
0x18005ed04  pop     r12
0x18005ed06  pop     rdi
0x18005ed07  pop     rsi
0x18005ed08  pop     rbp
0x18005ed09  retn
0x18005ed0b  cmp     r15d, 0FFFFFFFFh
0x18005ed0f  jz      short loc_18005ED53
0x18005ed11  call    cs:__imp_GetCurrentThread
0x18005ed18  nop     dword ptr [rax+rax+00h]
0x18005ed1d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005ed21  xor     r8d, r8d; OpenAsSelf
0x18005ed24  mov     rcx, rax; ThreadHandle
0x18005ed27  mov     edx, 2000Ch; DesiredAccess
0x18005ed2c  call    cs:__imp_OpenThreadToken
0x18005ed33  nop     dword ptr [rax+rax+00h]
0x18005ed38  test    eax, eax
0x18005ed3a  jnz     short loc_18005ED53
0x18005ed3c  call    cs:__imp_GetLastError
0x18005ed43  nop     dword ptr [rax+rax+00h]
0x18005ed48  cmp     eax, 3F0h
0x18005ed4d  jnz     loc_18005EC8E
0x18005ed53  mov     r13, [rbp+arg_8]
0x18005ed57  lea     rcx, [r14+8]; lpCriticalSection
0x18005ed5b  mov     [rsi+18h], r15d
0x18005ed5f  movups  xmm0, xmmword ptr [r13+0]
0x18005ed64  movdqu  xmmword ptr [rsi], xmm0
0x18005ed68  mov     rax, [rbp+TokenHandle]
0x18005ed6c  mov     [rsi+10h], rax
0x18005ed70  call    cs:__imp_EnterCriticalSection
0x18005ed77  nop     dword ptr [rax+rax+00h]
0x18005ed7c  lea     rcx, [r14+170h]
0x18005ed83  mov     rdx, rsi
0x18005ed86  mov     rax, [rcx]
0x18005ed89  mov     rax, [rax+8]
0x18005ed8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed92  test    al, al
0x18005ed94  jnz     short loc_18005ED9C
0x18005ed96  mov     ebx, edi
0x18005ed98  xor     edi, edi
0x18005ed9a  jmp     short loc_18005EDBB
0x18005ed9c  cmp     r15d, 0FFFFFFFFh
0x18005eda0  jz      short loc_18005EDA7
0x18005eda2  lock add [r14+30h], edi
0x18005eda7  mov     rcx, [r14+40h]; hEvent
0x18005edab  xor     esi, esi
0x18005edad  xor     ebx, ebx
0x18005edaf  call    cs:__imp_SetEvent
0x18005edb6  nop     dword ptr [rax+rax+00h]
0x18005edbb  lea     rcx, [r14+8]; lpCriticalSection
0x18005edbf  call    cs:__imp_LeaveCriticalSection
0x18005edc6  nop     dword ptr [rax+rax+00h]
0x18005edcb  test    ebx, ebx
0x18005edcd  jz      loc_18005ECAD
0x18005edd3  jmp     loc_18005EC94
```
