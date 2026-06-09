# CreateAssociationEntry(_GUID const *,ulong,ushort const *,_GUID const *,ushort const *,void *,void *,_ASSOCIATION_ENTRY * *)

- ea: `0x14000afa4`
- end: `0x14000b331`
- name: `?CreateAssociationEntry@@YAJPEBU_GUID@@KPEBG01PEAX2PEAPEAU_ASSOCIATION_ENTRY@@@Z`
- size: `909`
- prototype: `__int64 __fastcall(const struct _GUID *, int, const unsigned __int16 *, const struct _GUID *, unsigned __int16 *, void *, HANDLE ExistingTokenHandle, struct _ASSOCIATION_ENTRY **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bf80`
- `0x14000c350`

## callees

- `0x1400020d0`
- `0x140008eec`
- `0x140008f88`
- `0x14000afa4`
- `0x14000be64`
- `0x14000ccf0`
- `0x140011ea4`
- `0x1400124d0`
- `0x140014d74`
- `0x140017880`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b247`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000b247`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000b200`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000b200`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b20d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000b20d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b032`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b196`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000b125`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000b125`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000b0e8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000b0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b270`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000b18c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000b18c`

## pseudocode

```c
__int64 __fastcall CreateAssociationEntry(
        const struct _GUID *a1,
        int a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        void *a6,
        HANDLE ExistingTokenHandle,
        struct _ASSOCIATION_ENTRY **a8)
{
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  HANDLE ProcessHeap; // rax
  int v16; // edx
  struct _GUID *v17; // rdi
  int v18; // r8d
  int ClassFactory; // ebx
  int ProviderByName; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int v23; // eax
  __int64 v24; // rcx
  const unsigned __int16 *v25; // rdx
  _QWORD *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  void *v29; // rsi
  HANDLE v30; // rax
  HANDLE v31; // rax
  int MessageGuid; // [rsp+20h] [rbp-68h]
  int v34; // [rsp+28h] [rbp-60h]
  void *DuplicateTokenHandle; // [rsp+40h] [rbp-48h] BYREF
  struct IClassFactory *v36; // [rsp+48h] [rbp-40h] BYREF

  v36 = 0;
  DuplicateTokenHandle = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      16,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s_guid_(*((_QWORD *)WPP_GLOBAL_Control + 5), v12, v13, v14, MessageGuid);
  }
  ProcessHeap = GetProcessHeap();
  v17 = (struct _GUID *)HeapAlloc(ProcessHeap, 0, 0xC0u);
  if ( !v17 )
  {
    ClassFactory = -2147024882;
    goto LABEL_31;
  }
  ClassFactory = 0;
  memset_0(v17, 0, 0xC0u);
  *v17 = *a1;
  *(_DWORD *)v17[5].Data4 = a2;
  *(_QWORD *)&v17[11].Data1 = a6;
  if ( a5 )
  {
    ClassFactory = DafStringCopy(a5);
    if ( ClassFactory < 0 )
    {
LABEL_31:
      if ( !ExistingTokenHandle )
        goto LABEL_33;
      goto LABEL_32;
    }
  }
  if ( a3 )
  {
    ProviderByName = DAS::ProviderManagement::ProviderManager::GetProviderByName(g_providerManager, a3, &v17[2]);
  }
  else
  {
    if ( !a4 )
      goto LABEL_13;
    ProviderByName = DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(g_providerManager, a4, &v17[2]);
  }
  ClassFactory = ProviderByName;
LABEL_13:
  if ( ClassFactory )
    goto LABEL_31;
  ThreadpoolWait = CreateThreadpoolWait(CancelWaitCallback, v17, 0);
  *(_QWORD *)v17[11].Data4 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = GetLastError();
    ClassFactory = LastError;
    if ( LastError > 0 )
      ClassFactory = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_31;
  }
  SetThreadpoolWait(ThreadpoolWait, *(HANDLE *)&v17[11].Data1, 0);
  ClassFactory = ProviderContext::GetClassFactory(*(ProviderContext **)&v17[2].Data1, &v36);
  if ( ClassFactory )
    goto LABEL_31;
  ClassFactory = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, struct _GUID *))v36->lpVtbl->CreateInstance)(
                   v36,
                   0,
                   &IID_IAepAssociation,
                   &v17[3]);
  if ( ClassFactory )
    goto LABEL_31;
  ((void (__fastcall *)(struct IClassFactory *))v36->lpVtbl->Release)(v36);
  if ( !ExistingTokenHandle
    || DuplicateToken(ExistingTokenHandle, (SECURITY_IMPERSONATION_LEVEL)(ClassFactory + 2), &DuplicateTokenHandle) )
  {
    goto LABEL_24;
  }
  v23 = GetLastError();
  ClassFactory = v23;
  if ( v23 > 0 )
    ClassFactory = (unsigned __int16)v23 | 0x80070000;
  if ( ClassFactory >= 0 )
  {
LABEL_24:
    v24 = *(_QWORD *)&v17[2].Data1;
    if ( (*(_DWORD *)(v24 + 56) & 0x800) != 0 )
      v25 = *(const unsigned __int16 **)&v17[5].Data1;
    else
      v25 = 0;
    ClassFactory = CAssociationCallback::Create(
                     *(const unsigned __int16 **)v24,
                     v25,
                     *(_DWORD *)(v24 + 76),
                     v17,
                     DuplicateTokenHandle,
                     (struct CAssociationCallback **)v17[3].Data4);
    if ( !ClassFactory )
    {
      DuplicateTokenHandle = 0;
      InitializeSRWLock((PSRWLOCK)v17[10].Data4);
      EnterCriticalSection(&ActiveAssociationsList);
      v26 = (_QWORD *)qword_1400296B8;
      if ( *(__int64 **)qword_1400296B8 != &qword_1400296B0 )
        __fastfail(ClassFactory + 3);
      *(_QWORD *)&v17[1].Data1 = &qword_1400296B0;
      *(_QWORD *)v17[1].Data4 = v26;
      *v26 = v17 + 1;
      qword_1400296B8 = (__int64)&v17[1];
      LeaveCriticalSection(&ActiveAssociationsList);
      *a8 = (struct _ASSOCIATION_ENTRY *)v17;
    }
    goto LABEL_31;
  }
LABEL_32:
  CloseHandle(ExistingTokenHandle);
LABEL_33:
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( ClassFactory && v17 )
  {
    v27 = *(_QWORD *)v17[3].Data4;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v28 = *(_QWORD *)&v17[3].Data1;
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v17[3].Data1 + 16LL))(*(_QWORD *)&v17[3].Data1);
    }
    v29 = *(void **)&v17[5].Data1;
    if ( v29 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
    }
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v17);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v18,
      18,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v34,
      ClassFactory);
  return (unsigned int)ClassFactory;
}

```

## disassembly

```asm
0x14000afa4  push    rbx
0x14000afa6  push    rbp
0x14000afa7  push    rsi
0x14000afa8  push    rdi
0x14000afa9  push    r12
0x14000afab  push    r14
0x14000afad  push    r15
0x14000afaf  sub     rsp, 50h
0x14000afb3  mov     r15, r9
0x14000afb6  mov     rbp, r8
0x14000afb9  mov     r12d, edx
0x14000afbc  mov     r14, rcx
0x14000afbf  mov     [rsp+88h+var_40], 0
0x14000afc8  mov     [rsp+88h+DuplicateTokenHandle], 0
0x14000afd1  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000afd8  lea     rax, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000afdf  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000afe6  jz      short loc_14000B021
0x14000afe8  mov     r9d, 10h; int
0x14000afee  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x14000aff3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000affa  mov     rcx, [rcx+28h]; int
0x14000affe  call    WPP_RECORDER_SF_s
0x14000b003  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000b00a  jz      short loc_14000B021
0x14000b00c  mov     qword ptr [rsp+88h+var_58], r14
0x14000b011  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b018  mov     rcx, [rcx+28h]
0x14000b01c  call    WPP_RECORDER_SF_s_guid_
0x14000b021  call    cs:__imp_GetProcessHeap
0x14000b027  mov     rcx, rax; hHeap
0x14000b02a  xor     edx, edx; dwFlags
0x14000b02c  mov     r8d, 0C0h; dwBytes
0x14000b032  call    cs:__imp_HeapAlloc
0x14000b038  mov     rdi, rax
0x14000b03b  mov     rsi, [rsp+88h+ExistingTokenHandle]
0x14000b043  test    rax, rax
0x14000b046  jnz     short loc_14000B052
0x14000b048  mov     ebx, 8007000Eh
0x14000b04d  jmp     loc_14000B258
0x14000b052  xor     ebx, ebx
0x14000b054  xor     edx, edx; Val
0x14000b056  mov     r8d, 0C0h; Size
0x14000b05c  mov     rcx, rdi; void *
0x14000b05f  call    memset_0
0x14000b064  movups  xmm0, xmmword ptr [r14]
0x14000b068  movdqu  xmmword ptr [rdi], xmm0
0x14000b06c  mov     [rdi+58h], r12d
0x14000b070  mov     rax, [rsp+88h+arg_28]
0x14000b078  mov     [rdi+0B0h], rax
0x14000b07f  mov     rcx, [rsp+88h+arg_20]; unsigned __int16 *
0x14000b087  test    rcx, rcx
0x14000b08a  jz      short loc_14000B09F
0x14000b08c  lea     rdx, [rdi+50h]
0x14000b090  call    DafStringCopy
0x14000b095  mov     ebx, eax
0x14000b097  test    eax, eax
0x14000b099  js      loc_14000B258
0x14000b09f  test    rbp, rbp
0x14000b0a2  jz      short loc_14000B0B9
0x14000b0a4  lea     r8, [rdi+20h]
0x14000b0a8  mov     rdx, rbp
0x14000b0ab  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x14000b0b2  call    ?GetProviderByName@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderByName(ushort const *,std::shared_ptr<ProviderContext> &)
0x14000b0b7  jmp     short loc_14000B0D1
0x14000b0b9  test    r15, r15
0x14000b0bc  jz      short loc_14000B0D3
0x14000b0be  lea     r8, [rdi+20h]
0x14000b0c2  mov     rdx, r15
0x14000b0c5  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x14000b0cc  call    ?GetProviderFromProtocolId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBU_GUID@@AEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromProtocolId(_GUID const *,std::shared_ptr<ProviderContext> &)
0x14000b0d1  mov     ebx, eax
0x14000b0d3  test    ebx, ebx
0x14000b0d5  jnz     loc_14000B258
0x14000b0db  xor     r8d, r8d; pcbe
0x14000b0de  mov     rdx, rdi; pv
0x14000b0e1  lea     rcx, ?CancelWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14000b0e8  call    cs:__imp_CreateThreadpoolWait
0x14000b0ee  mov     [rdi+0B8h], rax
0x14000b0f5  test    rax, rax
0x14000b0f8  jnz     short loc_14000B118
0x14000b0fa  call    cs:__imp_GetLastError
0x14000b100  mov     ebx, eax
0x14000b102  test    eax, eax
0x14000b104  jle     loc_14000B258
0x14000b10a  movzx   ebx, ax
0x14000b10d  or      ebx, 80070000h
0x14000b113  jmp     loc_14000B258
0x14000b118  xor     r8d, r8d; pftTimeout
0x14000b11b  mov     rdx, [rdi+0B0h]; h
0x14000b122  mov     rcx, rax; pwa
0x14000b125  call    cs:__imp_SetThreadpoolWait
0x14000b12b  lea     rdx, [rsp+88h+var_40]; struct IClassFactory **
0x14000b130  mov     rcx, [rdi+20h]; this
0x14000b134  call    ?GetClassFactory@ProviderContext@@QEAAJPEAPEAUIClassFactory@@@Z; ProviderContext::GetClassFactory(IClassFactory * *)
0x14000b139  mov     ebx, eax
0x14000b13b  test    eax, eax
0x14000b13d  jnz     loc_14000B258
0x14000b143  mov     rcx, [rsp+88h+var_40]
0x14000b148  mov     rax, [rcx]
0x14000b14b  lea     r9, [rdi+30h]
0x14000b14f  lea     r8, IID_IAepAssociation
0x14000b156  xor     edx, edx
0x14000b158  mov     rax, [rax+18h]
0x14000b15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b161  mov     ebx, eax
0x14000b163  test    eax, eax
0x14000b165  jnz     loc_14000B258
0x14000b16b  mov     rcx, [rsp+88h+var_40]
0x14000b170  mov     rax, [rcx]
0x14000b173  mov     rax, [rax+10h]
0x14000b177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b17c  test    rsi, rsi
0x14000b17f  jz      short loc_14000B1B3
0x14000b181  lea     r8, [rsp+88h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14000b186  lea     edx, [rbx+2]; ImpersonationLevel
0x14000b189  mov     rcx, rsi; ExistingTokenHandle
0x14000b18c  call    cs:__imp_DuplicateToken
0x14000b192  test    eax, eax
0x14000b194  jnz     short loc_14000B1B3
0x14000b196  call    cs:__imp_GetLastError
0x14000b19c  mov     ebx, eax
0x14000b19e  test    eax, eax
0x14000b1a0  jle     short loc_14000B1AB
0x14000b1a2  movzx   ebx, ax
0x14000b1a5  or      ebx, 80070000h
0x14000b1ab  test    ebx, ebx
0x14000b1ad  js      loc_14000B25D
0x14000b1b3  mov     r8, [rsp+88h+DuplicateTokenHandle]
0x14000b1b8  mov     rcx, [rdi+20h]
0x14000b1bc  test    dword ptr [rcx+38h], 800h
0x14000b1c3  jz      short loc_14000B1CB
0x14000b1c5  mov     rdx, [rdi+50h]
0x14000b1c9  jmp     short loc_14000B1CD
0x14000b1cb  xor     edx, edx; unsigned __int16 *
0x14000b1cd  lea     rax, [rdi+38h]
0x14000b1d1  mov     [rsp+88h+var_60], rax; int
0x14000b1d6  mov     [rsp+88h+MessageGuid], r8; void *
0x14000b1db  mov     r9, rdi; void *
0x14000b1de  mov     r8d, [rcx+4Ch]; int
0x14000b1e2  mov     rcx, [rcx]; unsigned __int16 *
0x14000b1e5  call    ?Create@CAssociationCallback@@SAJPEBG0HPEAX1PEAPEAV1@@Z; CAssociationCallback::Create(ushort const *,ushort const *,int,void *,void *,CAssociationCallback * *)
0x14000b1ea  mov     ebx, eax
0x14000b1ec  test    eax, eax
0x14000b1ee  jnz     short loc_14000B258
0x14000b1f0  mov     [rsp+88h+DuplicateTokenHandle], 0
0x14000b1f9  lea     rcx, [rdi+0A8h]; SRWLock
0x14000b200  call    cs:__imp_InitializeSRWLock
0x14000b206  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000b20d  call    cs:__imp_EnterCriticalSection
0x14000b213  mov     rcx, cs:qword_1400296B8
0x14000b21a  lea     rdx, qword_1400296B0
0x14000b221  cmp     [rcx], rdx
0x14000b224  jz      short loc_14000B22B
0x14000b226  lea     ecx, [rbx+3]
0x14000b229  int     29h; Win8: RtlFailFast(ecx)
0x14000b22b  lea     rax, [rdi+10h]
0x14000b22f  mov     [rax], rdx
0x14000b232  mov     [rax+8], rcx
0x14000b236  mov     [rcx], rax
0x14000b239  mov     cs:qword_1400296B8, rax
0x14000b240  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000b247  call    cs:__imp_LeaveCriticalSection
0x14000b24d  mov     rax, [rsp+88h+arg_38]
0x14000b255  mov     [rax], rdi
0x14000b258  test    rsi, rsi
0x14000b25b  jz      short loc_14000B266
0x14000b25d  mov     rcx, rsi; hObject
0x14000b260  call    cs:__imp_CloseHandle
0x14000b266  mov     rcx, [rsp+88h+DuplicateTokenHandle]; hObject
0x14000b26b  test    rcx, rcx
0x14000b26e  jz      short loc_14000B276
0x14000b270  call    cs:__imp_CloseHandle
0x14000b276  test    ebx, ebx
0x14000b278  jz      short loc_14000B2EA
0x14000b27a  test    rdi, rdi
0x14000b27d  jz      short loc_14000B2EA
0x14000b27f  mov     rcx, [rdi+38h]
0x14000b283  test    rcx, rcx
0x14000b286  jz      short loc_14000B294
0x14000b288  mov     rax, [rcx]
0x14000b28b  mov     rax, [rax+10h]
0x14000b28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b294  mov     rcx, [rdi+30h]
0x14000b298  test    rcx, rcx
0x14000b29b  jz      short loc_14000B2B9
0x14000b29d  mov     rax, [rcx]
0x14000b2a0  mov     rax, [rax+60h]
0x14000b2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2a9  mov     rcx, [rdi+30h]
0x14000b2ad  mov     rax, [rcx]
0x14000b2b0  mov     rax, [rax+10h]
0x14000b2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2b9  mov     rsi, [rdi+50h]
0x14000b2bd  test    rsi, rsi
0x14000b2c0  jz      short loc_14000B2D6
0x14000b2c2  call    cs:__imp_GetProcessHeap
0x14000b2c8  mov     r8, rsi; lpMem
0x14000b2cb  xor     edx, edx; dwFlags
0x14000b2cd  mov     rcx, rax; hHeap
0x14000b2d0  call    cs:__imp_HeapFree
0x14000b2d6  call    cs:__imp_GetProcessHeap
0x14000b2dc  mov     rcx, rax; hHeap
0x14000b2df  mov     r8, rdi; lpMem
0x14000b2e2  xor     edx, edx; dwFlags
0x14000b2e4  call    cs:__imp_HeapFree
0x14000b2ea  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b2f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b2f8  jz      short loc_14000B320
0x14000b2fa  mov     r9d, 12h; int
0x14000b300  mov     dword ptr [rsp+88h+var_58], ebx; char
0x14000b304  lea     rax, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b30b  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x14000b310  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b317  mov     rcx, [rcx+28h]; int
0x14000b31b  call    WPP_RECORDER_SF_sd
0x14000b320  mov     eax, ebx
0x14000b322  add     rsp, 50h
0x14000b326  pop     r15
0x14000b328  pop     r14
0x14000b32a  pop     r12
0x14000b32c  pop     rdi
0x14000b32d  pop     rsi
0x14000b32e  pop     rbp
0x14000b32f  pop     rbx
0x14000b330  retn
```
