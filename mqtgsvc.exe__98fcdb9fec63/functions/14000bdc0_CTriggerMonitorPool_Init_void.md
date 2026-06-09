# CTriggerMonitorPool::Init(void)

- ea: `0x14000bdc0`
- end: `0x14000c0da`
- name: `?Init@CTriggerMonitorPool@@EEAA_NXZ`
- size: `794`
- prototype: `char __fastcall(CTriggerMonitorPool *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001cc6`
- `0x14000393c`
- `0x140003dc8`
- `0x1400046bc`
- `0x14000474c`
- `0x140004eb4`
- `0x140005cb0`
- `0x140006eb4`
- `0x14000752c`
- `0x140007554`
- `0x140008f08`
- `0x14000afa0`
- `0x14000b180`
- `0x14000b43c`
- `0x14000b93c`
- `0x14000b984`
- `0x14000bdc0`
- `0x14000ed18`
- `0x14001c774`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x14000bef2`
- `KERNEL32!ResetEvent` at `0x14000bef2`
- `KERNEL32!SetThreadPriority` at `0x14000be15`
- `KERNEL32!SetThreadPriority` at `0x14000be15`
- `KERNEL32!GetLastError` at `0x14000bf0e`
- `KERNEL32!GetLastError` at `0x14000c067`
- `KERNEL32!GetLastError` at `0x14000bf0e`
- `KERNEL32!GetLastError` at `0x14000c067`
- `KERNEL32!SetEvent` at `0x14000c04b`
- `KERNEL32!SetEvent` at `0x14000c04b`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000bf3e`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000c022`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000c097`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000bf3e`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000c022`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000c097`

## pseudocode

```c
char __fastcall CTriggerMonitorPool::Init(CTriggerMonitorPool *this)
{
  char *v2; // rsi
  __int64 v3; // rax
  struct IUnknown *v4; // rax
  unsigned int InitialThreads; // esi
  struct IUnknown *v6; // rax
  int v7; // ebx
  struct IUnknown *v8; // rax
  struct IUnknown *v9; // rax
  unsigned int i; // ebx
  PVOID *v11; // rcx
  _BYTE v13[24]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+48h] BYREF
  char *v16; // [rsp+A8h] [rbp+50h]
  __int64 *v17; // [rsp+B0h] [rbp+58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
  SetThreadPriority(*((HANDLE *)this + 4), 1);
  v2 = (char *)MmAllocate(0x50u);
  v16 = v2;
  if ( v2 )
  {
    v15 = *((_QWORD *)this + 2);
    _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(&v15);
    v17 = &v15;
    *((_DWORD *)v2 + 2) = 1;
    *(_QWORD *)v2 = &CQueueManager::`vftable';
    CReadWriteLock::CReadWriteLock((CReadWriteLock *)(v2 + 16));
    v3 = std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::_Buynode();
    *((_QWORD *)v2 + 6) = v3;
    *(_BYTE *)(v3 + 73) = 1;
    *(_QWORD *)(*((_QWORD *)v2 + 6) + 8LL) = *((_QWORD *)v2 + 6);
    **((_QWORD **)v2 + 6) = *((_QWORD *)v2 + 6);
    *(_QWORD *)(*((_QWORD *)v2 + 6) + 16LL) = *((_QWORD *)v2 + 6);
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 9) = v15;
    _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef((__int64 *)v2 + 9);
    R<IObjectContext>::~R<IObjectContext>(&v15);
  }
  else
  {
    v2 = 0;
  }
  SafeRelease<CQueue>(*((CReference **)this + 33));
  *((_QWORD *)this + 33) = v2;
  CTriggerMonitorPool::CreateIOCompletionPort(this);
  std::list<CAdminMessage *>::list<CAdminMessage *>(v13);
  CTriggerMonitorPool::GetTriggerData(this, v13);
  CTriggerMonitorPool::AttachTriggersToQueues(this, v13);
  if ( !ResetEvent(g_hServicePaused) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v4 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)this + 2);
  InitialThreads = IMSMQTriggersConfig::GetInitialThreads(v4);
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)this + 2);
  v7 = IMSMQTriggersConfig::GetInitialThreads(v6);
  v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)this + 2);
  if ( v7 > (int)IMSMQTriggersConfig::GetMaxThreads(v8) )
  {
    v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)this + 2);
    InitialThreads = IMSMQTriggersConfig::GetMaxThreads(v9);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= InitialThreads )
      goto LABEL_21;
    if ( (int)CTriggerMonitorPool::CreateTriggerMonitor(this) < 0 )
      break;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
LABEL_21:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 24) )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_(v11[2], 18, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( !SetEvent(g_hServicePaused) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_BYTE *)this + 88) = 1;
  std::list<R<CRuntimeTriggerInfo>>::_Tidy(v13);
  return 1;
}

```

## disassembly

```asm
0x14000bdc0  push    rbp
0x14000bdc2  push    rbx
0x14000bdc3  push    rsi
0x14000bdc4  push    rdi
0x14000bdc5  push    r12
0x14000bdc7  push    r13
0x14000bdc9  push    r14
0x14000bdcb  push    r15
0x14000bdcd  mov     rbp, rsp
0x14000bdd0  sub     rsp, 58h
0x14000bdd4  mov     rdi, rcx
0x14000bdd7  lea     r12, WPP_GLOBAL_Control
0x14000bdde  lea     r13, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000bde5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdec  cmp     rcx, r12
0x14000bdef  jz      short loc_14000BE08
0x14000bdf1  test    byte ptr [rcx+1Ch], 4
0x14000bdf5  jz      short loc_14000BE08
0x14000bdf7  mov     edx, 0Fh
0x14000bdfc  mov     r8, r13
0x14000bdff  mov     rcx, [rcx+10h]
0x14000be03  call    WPP_SF_
0x14000be08  mov     r15d, 1
0x14000be0e  mov     edx, r15d; nPriority
0x14000be11  mov     rcx, [rdi+20h]; hThread
0x14000be15  call    cs:__imp_SetThreadPriority
0x14000be1b  lea     ecx, [r15+4Fh]; unsigned __int64
0x14000be1f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000be24  mov     rsi, rax
0x14000be27  mov     [rbp+arg_8], rax
0x14000be2b  lea     r14, [rdi+10h]
0x14000be2f  test    rax, rax
0x14000be32  jz      short loc_14000BEAC
0x14000be34  mov     rax, [r14]
0x14000be37  mov     [rbp+arg_0], rax
0x14000be3b  lea     rcx, [rbp+arg_0]
0x14000be3f  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x14000be44  lea     rax, [rbp+arg_0]
0x14000be48  mov     [rbp+arg_10], rax
0x14000be4c  mov     [rsi+8], r15d
0x14000be50  lea     rax, ??_7CQueueManager@@6B@; const CQueueManager::`vftable'
0x14000be57  mov     [rsi], rax
0x14000be5a  lea     rcx, [rsi+10h]; this
0x14000be5e  call    ??0CReadWriteLock@@QEAA@K@Z; CReadWriteLock::CReadWriteLock(ulong)
0x14000be63  nop
0x14000be64  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCQueue@@@@@std@@@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CQueue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CQueue>>>,0>>::_Buynode(void)
0x14000be69  mov     [rsi+30h], rax
0x14000be6d  mov     [rax+49h], r15b
0x14000be71  mov     rax, [rsi+30h]
0x14000be75  mov     [rax+8], rax
0x14000be79  mov     rax, [rsi+30h]
0x14000be7d  mov     [rax], rax
0x14000be80  mov     rax, [rsi+30h]
0x14000be84  mov     [rax+10h], rax
0x14000be88  mov     qword ptr [rsi+38h], 0
0x14000be90  lea     rcx, [rsi+48h]
0x14000be94  mov     rax, [rbp+arg_0]
0x14000be98  mov     [rcx], rax
0x14000be9b  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x14000bea0  nop
0x14000bea1  lea     rcx, [rbp+arg_0]
0x14000bea5  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000beaa  jmp     short loc_14000BEAE
0x14000beac  xor     esi, esi
0x14000beae  mov     rcx, [rdi+108h]
0x14000beb5  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x14000beba  mov     [rdi+108h], rsi
0x14000bec1  mov     rcx, rdi; this
0x14000bec4  call    ?CreateIOCompletionPort@CTriggerMonitorPool@@AEAAXXZ; CTriggerMonitorPool::CreateIOCompletionPort(void)
0x14000bec9  lea     rcx, [rbp+var_38]
0x14000becd  call    ??0?$list@PEAVCAdminMessage@@V?$allocator@PEAVCAdminMessage@@@std@@@std@@QEAA@XZ; std::list<CAdminMessage *>::list<CAdminMessage *>(void)
0x14000bed2  nop
0x14000bed3  lea     rdx, [rbp+var_38]
0x14000bed7  mov     rcx, rdi
0x14000beda  call    ?GetTriggerData@CTriggerMonitorPool@@AEAAXAEAV?$list@V?$R@VCRuntimeTriggerInfo@@@@V?$allocator@V?$R@VCRuntimeTriggerInfo@@@@@std@@@std@@@Z; CTriggerMonitorPool::GetTriggerData(std::list<R<CRuntimeTriggerInfo>> &)
0x14000bedf  lea     rdx, [rbp+var_38]
0x14000bee3  mov     rcx, rdi
0x14000bee6  call    ?AttachTriggersToQueues@CTriggerMonitorPool@@AEAAXAEAV?$list@V?$R@VCRuntimeTriggerInfo@@@@V?$allocator@V?$R@VCRuntimeTriggerInfo@@@@@std@@@std@@@Z; CTriggerMonitorPool::AttachTriggersToQueues(std::list<R<CRuntimeTriggerInfo>> &)
0x14000beeb  mov     rcx, cs:?g_hServicePaused@@3VCHandle@@A; hEvent
0x14000bef2  call    cs:__imp_ResetEvent
0x14000bef8  test    eax, eax
0x14000befa  jnz     short loc_14000BF60
0x14000befc  mov     rax, cs:WPP_GLOBAL_Control
0x14000bf03  cmp     rax, r12
0x14000bf06  jz      short loc_14000BF30
0x14000bf08  test    [rax+1Ch], r15b
0x14000bf0c  jz      short loc_14000BF30
0x14000bf0e  call    cs:__imp_GetLastError
0x14000bf14  mov     edx, 10h
0x14000bf19  mov     r9d, eax
0x14000bf1c  mov     r8, r13
0x14000bf1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf26  mov     rcx, [rcx+10h]
0x14000bf2a  call    WPP_SF_d
0x14000bf2f  nop
0x14000bf30  mov     r8d, r15d
0x14000bf33  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000bf3a  lea     rcx, [rbp+pExceptionObject]
0x14000bf3e  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000bf44  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000bf4b  mov     [rbp+pExceptionObject], rax
0x14000bf4f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000bf56  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000bf5a  call    _CxxThrowException_0
0x14000bf60  mov     rcx, r14
0x14000bf63  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000bf68  mov     rcx, rax; this
0x14000bf6b  call    ?GetInitialThreads@IMSMQTriggersConfig@@QEAAJXZ; IMSMQTriggersConfig::GetInitialThreads(void)
0x14000bf70  mov     esi, eax
0x14000bf72  mov     rcx, r14
0x14000bf75  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000bf7a  mov     rcx, rax; this
0x14000bf7d  call    ?GetInitialThreads@IMSMQTriggersConfig@@QEAAJXZ; IMSMQTriggersConfig::GetInitialThreads(void)
0x14000bf82  mov     ebx, eax
0x14000bf84  mov     rcx, r14
0x14000bf87  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000bf8c  mov     rcx, rax; this
0x14000bf8f  call    ?GetMaxThreads@IMSMQTriggersConfig@@QEAAJXZ; IMSMQTriggersConfig::GetMaxThreads(void)
0x14000bf94  cmp     ebx, eax
0x14000bf96  jle     short loc_14000BFAA
0x14000bf98  mov     rcx, r14
0x14000bf9b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000bfa0  mov     rcx, rax; this
0x14000bfa3  call    ?GetMaxThreads@IMSMQTriggersConfig@@QEAAJXZ; IMSMQTriggersConfig::GetMaxThreads(void)
0x14000bfa8  mov     esi, eax
0x14000bfaa  xor     ebx, ebx
0x14000bfac  cmp     ebx, esi
0x14000bfae  jnb     short loc_14000BFE7
0x14000bfb0  mov     rcx, rdi; this
0x14000bfb3  call    ?CreateTriggerMonitor@CTriggerMonitorPool@@AEAAJXZ; CTriggerMonitorPool::CreateTriggerMonitor(void)
0x14000bfb8  test    eax, eax
0x14000bfba  js      short loc_14000BFC1
0x14000bfbc  add     ebx, r15d
0x14000bfbf  jmp     short loc_14000BFAC
0x14000bfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfc8  cmp     rcx, r12
0x14000bfcb  jz      short loc_14000BFEE
0x14000bfcd  test    [rcx+1Ch], r15b
0x14000bfd1  jz      short loc_14000BFEE
0x14000bfd3  mov     edx, 11h
0x14000bfd8  mov     r9d, eax
0x14000bfdb  mov     r8, r13
0x14000bfde  mov     rcx, [rcx+10h]
0x14000bfe2  call    WPP_SF_d
0x14000bfe7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfee  cmp     [rdi+0C0h], r15
0x14000bff5  jnb     short loc_14000C044
0x14000bff7  cmp     rcx, r12
0x14000bffa  jz      short loc_14000C014
0x14000bffc  test    [rcx+1Ch], r15b
0x14000c000  jz      short loc_14000C014
0x14000c002  mov     edx, 12h
0x14000c007  mov     r8, r13
0x14000c00a  mov     rcx, [rcx+10h]
0x14000c00e  call    WPP_SF_
0x14000c013  nop
0x14000c014  mov     r8d, r15d
0x14000c017  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000c01e  lea     rcx, [rbp+pExceptionObject]
0x14000c022  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000c028  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000c02f  mov     [rbp+pExceptionObject], rax
0x14000c033  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000c03a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000c03e  call    _CxxThrowException_0
0x14000c044  mov     rcx, cs:?g_hServicePaused@@3VCHandle@@A; hEvent
0x14000c04b  call    cs:__imp_SetEvent
0x14000c051  test    eax, eax
0x14000c053  jnz     short loc_14000C0B9
0x14000c055  mov     rax, cs:WPP_GLOBAL_Control
0x14000c05c  cmp     rax, r12
0x14000c05f  jz      short loc_14000C089
0x14000c061  test    [rax+1Ch], r15b
0x14000c065  jz      short loc_14000C089
0x14000c067  call    cs:__imp_GetLastError
0x14000c06d  mov     edx, 13h
0x14000c072  mov     r9d, eax
0x14000c075  mov     r8, r13
0x14000c078  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c07f  mov     rcx, [rcx+10h]
0x14000c083  call    WPP_SF_d
0x14000c088  nop
0x14000c089  mov     r8d, r15d
0x14000c08c  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000c093  lea     rcx, [rbp+pExceptionObject]
0x14000c097  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000c09d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000c0a4  mov     [rbp+pExceptionObject], rax
0x14000c0a8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000c0af  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000c0b3  call    _CxxThrowException_0
0x14000c0b9  mov     [rdi+58h], r15b
0x14000c0bd  lea     rcx, [rbp+var_38]
0x14000c0c1  call    ?_Tidy@?$list@V?$R@VCRuntimeTriggerInfo@@@@V?$allocator@V?$R@VCRuntimeTriggerInfo@@@@@std@@@std@@IEAAXXZ; std::list<R<CRuntimeTriggerInfo>>::_Tidy(void)
0x14000c0c6  mov     al, r15b
0x14000c0c9  add     rsp, 58h
0x14000c0cd  pop     r15
0x14000c0cf  pop     r14
0x14000c0d1  pop     r13
0x14000c0d3  pop     r12
0x14000c0d5  pop     rdi
0x14000c0d6  pop     rsi
0x14000c0d7  pop     rbx
0x14000c0d8  pop     rbp
0x14000c0d9  retn
```
