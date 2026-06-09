# Container::Manager::Core::Details::ServicingOrchestrator::~ServicingOrchestrator(void)

- ea: `0x180069c44`
- end: `0x180069e66`
- name: `??1ServicingOrchestrator@Details@Core@Manager@Container@@QEAA@XZ`
- size: `546`
- prototype: `void __fastcall(Container::Manager::Core::Details::ServicingOrchestrator *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180076520`

## callees

- `0x18000a10c`
- `0x180016658`
- `0x1800471dc`
- `0x1800493c8`
- `0x180053ea0`
- `0x180069b00`
- `0x180069c44`
- `0x180069e6c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069c8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069d04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069c8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069d04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069cb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069d2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069d86`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069dbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069cb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069d2d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069d86`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069dbf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180069cdf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180069cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069cc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069d3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069cc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ServicingOrchestrator::~ServicingOrchestrator(
        Container::Manager::Core::Details::ServicingOrchestrator **this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  PTP_WORK *v5; // rsi
  HANDLE *v6; // r14
  struct _TP_WORK *v7; // rbp
  DWORD LastError; // ebx
  unsigned int v9; // r8d
  const char *v10; // r9
  struct _TP_WORK *v11; // rbp
  DWORD v12; // ebx
  Container::Manager::Core::Details::ServicingOrchestrator *v13; // rcx
  unsigned int v14; // r8d
  const char *v15; // r9
  struct _TP_WORK *v16; // rcx
  utl::_RefCountBase *v17; // rcx
  utl::_RefCountBase *v18; // rcx
  utl::_RefCountBase *v19; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( this[16] )
  {
    if ( this[32] != (Container::Manager::Core::Details::ServicingOrchestrator *)(this + 30) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x85E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
        a4);
    v5 = this + 38;
    WaitForThreadpoolWorkCallbacks(this[38], 1);
    v7 = *v5;
    if ( *v5 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v7);
      SetLastError(LastError);
    }
    *v5 = 0;
    v6 = (HANDLE *)(this + 37);
    if ( !SetEvent(this[37]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
    WaitForThreadpoolWorkCallbacks(this[36], 1);
    v11 = this[36];
    if ( v11 )
    {
      v12 = GetLastError();
      CloseThreadpoolWork(v11);
      SetLastError(v12);
    }
    this[36] = 0;
    v13 = this[34];
    if ( v13 && (!*((_DWORD *)v13 + 1) || *(_DWORD *)v13 == -2147023436) )
      Csl::CompletionEvent<void>::CompleteInternal(this[34], 2147943623LL);
  }
  else
  {
    v5 = this + 38;
    v6 = (HANDLE *)(this + 37);
  }
  if ( *v5 )
    CloseThreadpoolWork(*v5);
  if ( *v6 && !CloseHandle(*v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
  v16 = this[36];
  if ( v16 )
    CloseThreadpoolWork(v16);
  v17 = this[35];
  if ( v17 )
    utl::_RefCountBase::_DecStrong(v17);
  utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>>,0>::~_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>>,0>(this + 30);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(this + 26);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(this + 22);
  v18 = this[19];
  if ( v18 )
    utl::_RefCountBase::_DecStrong(v18);
  v19 = this[17];
  if ( v19 )
    utl::_RefCountBase::_DecStrong(v19);
  Container::Manager::Core::Details::ServicingStore::~ServicingStore((Container::Manager::Core::Details::ServicingStore *)this);
}

```

## disassembly

```asm
0x180069c44  push    rbx
0x180069c46  push    rbp
0x180069c47  push    rsi
0x180069c48  push    rdi
0x180069c49  push    r14
0x180069c4b  sub     rsp, 20h
0x180069c4f  mov     rdi, rcx
0x180069c52  cmp     qword ptr [rcx+80h], 0
0x180069c5a  jnz     short loc_180069C6F
0x180069c5c  lea     rsi, [rcx+130h]
0x180069c63  lea     r14, [rcx+128h]
0x180069c6a  jmp     loc_180069D7E
0x180069c6f  lea     rax, [rcx+0F0h]
0x180069c76  cmp     [rax+10h], rax
0x180069c7a  jnz     loc_180069E44
0x180069c80  lea     rsi, [rcx+130h]
0x180069c87  mov     edx, 1; fCancelPendingCallbacks
0x180069c8c  mov     rcx, [rsi]; pwk
0x180069c8f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180069c96  nop     dword ptr [rax+rax+00h]
0x180069c9b  mov     rbp, [rsi]
0x180069c9e  test    rbp, rbp
0x180069ca1  jz      short loc_180069CCE
0x180069ca3  call    cs:__imp_GetLastError
0x180069caa  nop     dword ptr [rax+rax+00h]
0x180069caf  mov     ebx, eax
0x180069cb1  mov     rcx, rbp; pwk
0x180069cb4  call    cs:__imp_CloseThreadpoolWork
0x180069cbb  nop     dword ptr [rax+rax+00h]
0x180069cc0  mov     ecx, ebx; dwErrCode
0x180069cc2  call    cs:__imp_SetLastError
0x180069cc9  nop     dword ptr [rax+rax+00h]
0x180069cce  mov     qword ptr [rsi], 0
0x180069cd5  lea     r14, [rdi+128h]
0x180069cdc  mov     rcx, [r14]; hEvent
0x180069cdf  call    cs:__imp_SetEvent
0x180069ce6  nop     dword ptr [rax+rax+00h]
0x180069ceb  mov     rcx, [rsp+48h]; this
0x180069cf0  test    eax, eax
0x180069cf2  jz      loc_180069E5B
0x180069cf8  mov     edx, 1; fCancelPendingCallbacks
0x180069cfd  mov     rcx, [rdi+120h]; pwk
0x180069d04  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180069d0b  nop     dword ptr [rax+rax+00h]
0x180069d10  mov     rbp, [rdi+120h]
0x180069d17  test    rbp, rbp
0x180069d1a  jz      short loc_180069D47
0x180069d1c  call    cs:__imp_GetLastError
0x180069d23  nop     dword ptr [rax+rax+00h]
0x180069d28  mov     ebx, eax
0x180069d2a  mov     rcx, rbp; pwk
0x180069d2d  call    cs:__imp_CloseThreadpoolWork
0x180069d34  nop     dword ptr [rax+rax+00h]
0x180069d39  mov     ecx, ebx; dwErrCode
0x180069d3b  call    cs:__imp_SetLastError
0x180069d42  nop     dword ptr [rax+rax+00h]
0x180069d47  mov     qword ptr [rdi+120h], 0
0x180069d52  mov     rcx, [rdi+110h]
0x180069d59  test    rcx, rcx
0x180069d5c  jz      short loc_180069D7E
0x180069d5e  mov     eax, [rcx+4]
0x180069d61  test    eax, eax
0x180069d63  jz      short loc_180069D6D
0x180069d65  cmp     dword ptr [rcx], 800705B4h
0x180069d6b  jnz     short loc_180069D7E
0x180069d6d  mov     edx, 800704C7h
0x180069d72  mov     rcx, [rdi+110h]
0x180069d79  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x180069d7e  mov     rcx, [rsi]; pwk
0x180069d81  test    rcx, rcx
0x180069d84  jz      short loc_180069D92
0x180069d86  call    cs:__imp_CloseThreadpoolWork
0x180069d8d  nop     dword ptr [rax+rax+00h]
0x180069d92  mov     rcx, [r14]; hObject
0x180069d95  test    rcx, rcx
0x180069d98  jz      short loc_180069DB3
0x180069d9a  call    cs:__imp_CloseHandle
0x180069da1  nop     dword ptr [rax+rax+00h]
0x180069da6  mov     rcx, [rsp+48h]; this
0x180069dab  test    eax, eax
0x180069dad  jz      loc_180069E39
0x180069db3  mov     rcx, [rdi+120h]; pwk
0x180069dba  test    rcx, rcx
0x180069dbd  jz      short loc_180069DCC
0x180069dbf  call    cs:__imp_CloseThreadpoolWork
0x180069dc6  nop     dword ptr [rax+rax+00h]
0x180069dcb  nop
0x180069dcc  mov     rcx, [rdi+118h]; this
0x180069dd3  test    rcx, rcx
0x180069dd6  jz      short loc_180069DDE
0x180069dd8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180069ddd  nop
0x180069dde  lea     rcx, [rdi+0F0h]
0x180069de5  call    ??1?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$weak_ptr@VContainerObject@Details@Core@Manager@Container@@@utl@@@utl@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VContainerObject@Details@Core@Manager@Container@@@utl@@@utl@@@3@$0A@@utl@@IEAA@XZ; utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>>,0>::~_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>,utl::less<_GUID>,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<Container::Manager::Core::Details::ContainerObject>>>,0>(void)
0x180069dea  lea     rcx, [rdi+0D0h]
0x180069df1  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x180069df6  lea     rcx, [rdi+0B0h]
0x180069dfd  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x180069e02  nop
0x180069e03  mov     rcx, [rdi+98h]; this
0x180069e0a  test    rcx, rcx
0x180069e0d  jz      short loc_180069E15
0x180069e0f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180069e14  nop
0x180069e15  mov     rcx, [rdi+88h]; this
0x180069e1c  test    rcx, rcx
0x180069e1f  jz      short loc_180069E27
0x180069e21  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180069e26  nop
0x180069e27  mov     rcx, rdi; this
0x180069e2a  add     rsp, 20h
0x180069e2e  pop     r14
0x180069e30  pop     rdi
0x180069e31  pop     rsi
0x180069e32  pop     rbp
0x180069e33  pop     rbx
0x180069e34  jmp     ??1ServicingStore@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ServicingStore::~ServicingStore(void)
0x180069e39  mov     edx, 0A0Bh; void *
0x180069e3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180069e44  mov     rcx, [rsp+48h]; this
0x180069e49  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180069e50  mov     edx, 85Eh; void *
0x180069e55  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180069e5b  mov     edx, 0A01h; void *
0x180069e60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
