# CGPApplicationService::~CGPApplicationService(void)

- ea: `0x18000a684`
- end: `0x18000a882`
- name: `??1CGPApplicationService@@QEAA@XZ`
- size: `510`
- prototype: `void __fastcall(CGPApplicationService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000924c`

## callees

- `0x180007c7c`
- `0x18000a404`
- `0x18000a5c4`
- `0x18000a684`
- `0x18000a888`
- `0x18000c398`
- `0x180065208`
- `0x18007cde4`
- `0x18007d304`
- `0x18007d6f0`
- `0x18008a17c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a725`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a797`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a7eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a814`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a797`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a7eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a814`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a6c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a761`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a877`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a77e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a77e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000a861`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000a861`

## pseudocode

```c
void __fastcall CGPApplicationService::~CGPApplicationService(CGPApplicationService *this)
{
  void *v2; // rcx
  CStatusMessage *v3; // rdi
  void *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  void *v6; // rcx
  char *v7; // rcx
  unsigned int v8; // edx
  AccountPolicyCriticalSection *v9; // rcx
  char *v10; // rcx
  void *v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  void *v13; // rcx
  void **v14; // rdi
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  void *v16; // rcx
  struct _RTL_CRITICAL_SECTION *v17; // rcx

  *(_QWORD *)this = &CGPApplicationService::`vftable';
  v2 = (void *)*((_QWORD *)this + 34);
  if ( v2 )
    STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v2);
  v3 = CStatusMessage::m_instance;
  if ( CStatusMessage::m_instance )
  {
    CStatusMessage::~CStatusMessage(CStatusMessage::m_instance);
    operator delete(v3);
    CStatusMessage::m_instance = 0;
  }
  v4 = (void *)*((_QWORD *)this + 44);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 44) = 0;
  }
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 33);
  if ( v5 )
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 33));
  v6 = (void *)*((_QWORD *)this + 40);
  if ( v6 )
  {
    UnregisterWaitEx(v6, 0);
    *((_QWORD *)this + 40) = 0;
  }
  v7 = (char *)*((_QWORD *)this + 39);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  *((_QWORD *)this + 39) = 0;
  if ( v5 )
    LeaveCriticalSection(v5);
  CGPUserCollection::Uninitialize((CGPApplicationService *)((char *)this + 8));
  CPolicyCriticalSectionCollection::Uninitialize((CGPApplicationService *)((char *)this + 152));
  v9 = (AccountPolicyCriticalSection *)*((_QWORD *)this + 35);
  if ( v9 )
    AccountPolicyCriticalSection::`scalar deleting destructor'(v9, v8);
  v10 = (char *)*((_QWORD *)this + 39);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 39) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 36);
  if ( v11 )
    *((_QWORD *)this + 36) = LocalFree(v11);
  v12 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 33);
  if ( v12 )
    DeleteCriticalSection(v12);
  v13 = (void *)*((_QWORD *)this + 27);
  if ( v13 )
    *((_QWORD *)this + 27) = LocalFree(v13);
  v14 = (void **)*((_QWORD *)this + 25);
  if ( v14 )
  {
    std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(
      v13,
      *v14);
    operator delete(*v14);
    operator delete(v14);
  }
  v15 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 24);
  if ( v15 )
    DeleteCriticalSection(v15);
  v16 = (void *)*((_QWORD *)this + 18);
  if ( v16 )
    std::list<_USER_COLLECTION_CONTEXT *,STLWrap_allocator<_USER_COLLECTION_CONTEXT *>>::`scalar deleting destructor'(v16);
  CRWLock::~CRWLock((CGPApplicationService *)((char *)this + 64));
  v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 6);
  if ( v17 )
    DeleteCriticalSection(v17);
}

```

## disassembly

```asm
0x18000a684  mov     [rsp+arg_0], rbx
0x18000a689  push    rdi
0x18000a68a  sub     rsp, 20h
0x18000a68e  mov     rbx, rcx
0x18000a691  lea     rax, ??_7CGPApplicationService@@6B@; const CGPApplicationService::`vftable'
0x18000a698  mov     [rcx], rax
0x18000a69b  mov     rcx, [rcx+110h]; Block
0x18000a6a2  test    rcx, rcx
0x18000a6a5  jnz     loc_18000A830
0x18000a6ab  mov     rdi, cs:?m_instance@CStatusMessage@@0PEAV1@EA; CStatusMessage * CStatusMessage::m_instance
0x18000a6b2  test    rdi, rdi
0x18000a6b5  jnz     loc_18000A83A
0x18000a6bb  mov     rcx, [rbx+160h]; hObject
0x18000a6c2  test    rcx, rcx
0x18000a6c5  jz      short loc_18000A6D8
0x18000a6c7  call    cs:__imp_CloseHandle
0x18000a6cd  mov     qword ptr [rbx+160h], 0
0x18000a6d8  mov     rdi, [rbx+108h]
0x18000a6df  test    rdi, rdi
0x18000a6e2  jz      short loc_18000A6ED
0x18000a6e4  mov     rcx, rdi; lpCriticalSection
0x18000a6e7  call    cs:__imp_EnterCriticalSection
0x18000a6ed  mov     rcx, [rbx+140h]; WaitHandle
0x18000a6f4  test    rcx, rcx
0x18000a6f7  jnz     loc_18000A85F
0x18000a6fd  mov     rcx, [rbx+138h]; hObject
0x18000a704  lea     rax, [rcx-1]
0x18000a708  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a70c  jbe     loc_18000A877
0x18000a712  mov     qword ptr [rbx+138h], 0
0x18000a71d  test    rdi, rdi
0x18000a720  jz      short loc_18000A72B
0x18000a722  mov     rcx, rdi; lpCriticalSection
0x18000a725  call    cs:__imp_LeaveCriticalSection
0x18000a72b  lea     rcx, [rbx+8]; this
0x18000a72f  call    ?Uninitialize@CGPUserCollection@@QEAAKXZ; CGPUserCollection::Uninitialize(void)
0x18000a734  lea     rcx, [rbx+98h]; this
0x18000a73b  call    ?Uninitialize@CPolicyCriticalSectionCollection@@QEAAKXZ; CPolicyCriticalSectionCollection::Uninitialize(void)
0x18000a740  mov     rcx, [rbx+118h]; this
0x18000a747  test    rcx, rcx
0x18000a74a  jnz     loc_18000A826
0x18000a750  mov     rcx, [rbx+138h]; hObject
0x18000a757  lea     rax, [rcx-1]
0x18000a75b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a75f  ja      short loc_18000A772
0x18000a761  call    cs:__imp_CloseHandle
0x18000a767  mov     qword ptr [rbx+138h], 0
0x18000a772  mov     rcx, [rbx+120h]; hMem
0x18000a779  test    rcx, rcx
0x18000a77c  jz      short loc_18000A78B
0x18000a77e  call    cs:__imp_LocalFree
0x18000a784  mov     [rbx+120h], rax
0x18000a78b  mov     rcx, [rbx+108h]; lpCriticalSection
0x18000a792  test    rcx, rcx
0x18000a795  jz      short loc_18000A79D
0x18000a797  call    cs:__imp_DeleteCriticalSection
0x18000a79d  mov     rcx, [rbx+0D8h]; hMem
0x18000a7a4  test    rcx, rcx
0x18000a7a7  jz      short loc_18000A7B6
0x18000a7a9  call    cs:__imp_LocalFree
0x18000a7af  mov     [rbx+0D8h], rax
0x18000a7b6  mov     rdi, [rbx+0C8h]
0x18000a7bd  test    rdi, rdi
0x18000a7c0  jz      short loc_18000A7DF
0x18000a7c2  mov     rdx, [rdi]
0x18000a7c5  call    ??$_Free_non_head@V?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@@?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@SAXAEAV?$STLWrap_allocator@U?$_List_node@PEAU_POLICY_SECTION_CONTEXT@@PEAX@std@@@@PEAU01@@Z; std::_List_node<_POLICY_SECTION_CONTEXT *,void *>::_Free_non_head<STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>>>(STLWrap_allocator<std::_List_node<_POLICY_SECTION_CONTEXT *,void *>> &,std::_List_node<_POLICY_SECTION_CONTEXT *,void *> *)
0x18000a7ca  mov     rcx, [rdi]; Block
0x18000a7cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7d2  mov     edx, 10h
0x18000a7d7  mov     rcx, rdi; Block
0x18000a7da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a7df  mov     rcx, [rbx+0C0h]; lpCriticalSection
0x18000a7e6  test    rcx, rcx
0x18000a7e9  jz      short loc_18000A7F1
0x18000a7eb  call    cs:__imp_DeleteCriticalSection
0x18000a7f1  mov     rcx, [rbx+90h]; Block
0x18000a7f8  test    rcx, rcx
0x18000a7fb  jz      short loc_18000A802
0x18000a7fd  call    ??_G?$list@PEAU_USER_COLLECTION_CONTEXT@@V?$STLWrap_allocator@PEAU_USER_COLLECTION_CONTEXT@@@@@std@@QEAAPEAXI@Z; std::list<_USER_COLLECTION_CONTEXT *,STLWrap_allocator<_USER_COLLECTION_CONTEXT *>>::`scalar deleting destructor'(uint)
0x18000a802  lea     rcx, [rbx+40h]; this
0x18000a806  call    ??1CRWLock@@QEAA@XZ; CRWLock::~CRWLock(void)
0x18000a80b  mov     rcx, [rbx+30h]; lpCriticalSection
0x18000a80f  test    rcx, rcx
0x18000a812  jz      short loc_18000A81B
0x18000a814  call    cs:__imp_DeleteCriticalSection
0x18000a81a  nop
0x18000a81b  mov     rbx, [rsp+28h+arg_0]
0x18000a820  add     rsp, 20h
0x18000a824  pop     rdi
0x18000a825  retn
0x18000a826  call    ??_GAccountPolicyCriticalSection@@QEAAPEAXI@Z; AccountPolicyCriticalSection::`scalar deleting destructor'(uint)
0x18000a82b  jmp     loc_18000A750
0x18000a830  call    ??_G?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAPEAXI@Z; STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(uint)
0x18000a835  jmp     loc_18000A6AB
0x18000a83a  mov     rcx, rdi; this
0x18000a83d  call    ??1CStatusMessage@@IEAA@XZ; CStatusMessage::~CStatusMessage(void)
0x18000a842  mov     edx, 138h
0x18000a847  mov     rcx, rdi; Block
0x18000a84a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a84f  mov     cs:?m_instance@CStatusMessage@@0PEAV1@EA, 0; CStatusMessage * CStatusMessage::m_instance
0x18000a85a  jmp     loc_18000A6BB
0x18000a85f  xor     edx, edx; CompletionEvent
0x18000a861  call    cs:__imp_UnregisterWaitEx
0x18000a867  mov     qword ptr [rbx+140h], 0
0x18000a872  jmp     loc_18000A6FD
0x18000a877  call    cs:__imp_CloseHandle
0x18000a87d  jmp     loc_18000A712
```
