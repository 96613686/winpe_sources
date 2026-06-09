# MapsBackgroundTransferJob::~MapsBackgroundTransferJob(void)

- ea: `0x18000b544`
- end: `0x18000b676`
- name: `??1MapsBackgroundTransferJob@@UEAA@XZ`
- size: `306`
- prototype: `void __fastcall(MapsBackgroundTransferJob *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b980`

## callees

- `0x1800033d4`
- `0x180005b9c`
- `0x18000aff4`
- `0x18000b0cc`
- `0x18000b128`
- `0x18000b544`
- `0x18000c440`
- `0x18000cf70`
- `0x18000f9cc`
- `0x180010954`
- `0x18001368c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b616`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b616`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b5ef`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b5ef`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000b5b0`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000b5b0`

## pseudocode

```c
void __fastcall MapsBackgroundTransferJob::~MapsBackgroundTransferJob(MapsBackgroundTransferJob *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  unsigned int JobState; // eax
  int v5; // eax
  int v6; // ecx
  DWORD FileAttributesW; // eax
  int v8; // edx
  void *v9; // r9
  std::_Ref_count_base *v10; // rcx

  *(_QWORD *)this = &MapsBackgroundTransferJob::`vftable';
  v2 = (_QWORD *)((char *)this + 24);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 200LL))(v3, 0);
  JobState = MapsBackgroundTransferJob::GetJobState(this);
  if ( JobState == 3 )
  {
    if ( !*v2 )
      __int2c();
    v5 = MapsBackgroundTransferJob::SwitchToIdleModeNotifications(this);
    if ( v5 < 0 )
      ZTraceReportIgnore(v5, "MapsBackgroundTransferJob::~MapsBackgroundTransferJob", 116, this);
  }
  else if ( JobState <= 5 )
  {
    v6 = 37;
    if ( _bittest(&v6, JobState) )
      MapsBackgroundTransferJob::CancelJob(this);
  }
  if ( (unsigned int)MapsBackgroundTransferJob::GetJobState(this) == 4 && this != (MapsBackgroundTransferJob *)-84LL )
  {
    if ( *((_WORD *)this + 42) )
    {
      FileAttributesW = GetFileAttributesW((LPCWSTR)this + 42);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x400) == 0 )
        RecursiveScanDirectory(
          (const unsigned __int16 *)this + 42,
          v8,
          (int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))ForceDelete,
          v9);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 784));
  __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2__std___2__0A__std___std__QEAA_XZ((char *)this + 672);
  std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>((char *)this + 608);
  std::wstring::_Tidy_deallocate((char *)this + 48);
  ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>((char *)this + 32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v2);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
  *(_QWORD *)this = &IMapsBackgroundTransferJob::`vftable';
}

```

## disassembly

```asm
0x18000b544  mov     [rsp+arg_0], rbx
0x18000b549  mov     [rsp+arg_8], rsi
0x18000b54e  push    rdi
0x18000b54f  sub     rsp, 20h
0x18000b553  mov     rbx, rcx
0x18000b556  lea     rax, ??_7MapsBackgroundTransferJob@@6B@; const MapsBackgroundTransferJob::`vftable'
0x18000b55d  mov     [rcx], rax
0x18000b560  lea     rsi, [rcx+18h]
0x18000b564  mov     rcx, [rsi]
0x18000b567  test    rcx, rcx
0x18000b56a  jz      short loc_18000B57D
0x18000b56c  mov     rax, [rcx]
0x18000b56f  xor     edx, edx
0x18000b571  mov     rax, [rax+0C8h]
0x18000b578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b57d  mov     rcx, rbx
0x18000b580  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x18000b585  cmp     eax, 3
0x18000b588  jnz     short loc_18000B5B8
0x18000b58a  cmp     qword ptr [rsi], 0
0x18000b58e  jnz     short loc_18000B592
0x18000b590  int     2Ch; Windows NT - assertion failure
0x18000b592  mov     rcx, rbx; this
0x18000b595  call    ?SwitchToIdleModeNotifications@MapsBackgroundTransferJob@@AEAAJXZ; MapsBackgroundTransferJob::SwitchToIdleModeNotifications(void)
0x18000b59a  test    eax, eax
0x18000b59c  jns     short loc_18000B5CF
0x18000b59e  mov     r9, rbx
0x18000b5a1  mov     r8d, 74h ; 't'
0x18000b5a7  lea     rdx, aMapsbackground_40; "MapsBackgroundTransferJob::~MapsBackgro"...
0x18000b5ae  mov     ecx, eax
0x18000b5b0  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000b5b6  jmp     short loc_18000B5CF
0x18000b5b8  cmp     eax, 5
0x18000b5bb  ja      short loc_18000B5CF
0x18000b5bd  mov     ecx, 25h ; '%'
0x18000b5c2  bt      ecx, eax
0x18000b5c5  jnb     short loc_18000B5CF
0x18000b5c7  mov     rcx, rbx; this
0x18000b5ca  call    ?CancelJob@MapsBackgroundTransferJob@@UEAAJXZ; MapsBackgroundTransferJob::CancelJob(void)
0x18000b5cf  mov     rcx, rbx
0x18000b5d2  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x18000b5d7  cmp     eax, 4
0x18000b5da  jnz     short loc_18000B60F
0x18000b5dc  lea     rdi, [rbx+54h]
0x18000b5e0  test    rdi, rdi
0x18000b5e3  jz      short loc_18000B60F
0x18000b5e5  xor     eax, eax
0x18000b5e7  cmp     ax, [rdi]
0x18000b5ea  jz      short loc_18000B60F
0x18000b5ec  mov     rcx, rdi; lpFileName
0x18000b5ef  call    cs:__imp_GetFileAttributesW
0x18000b5f5  cmp     eax, 0FFFFFFFFh
0x18000b5f8  jz      short loc_18000B60F
0x18000b5fa  bt      eax, 0Ah
0x18000b5fe  jb      short loc_18000B60F
0x18000b600  lea     r8, ForceDelete; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x18000b607  mov     rcx, rdi; unsigned __int16 *
0x18000b60a  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x18000b60f  lea     rcx, [rbx+310h]; lpCriticalSection
0x18000b616  call    cs:__imp_DeleteCriticalSection
0x18000b61c  lea     rcx, [rbx+2A0h]
0x18000b623  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>(void)
0x18000b628  lea     rcx, [rbx+260h]
0x18000b62f  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>(void)
0x18000b634  lea     rcx, [rbx+30h]
0x18000b638  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b63d  lea     rcx, [rbx+20h]
0x18000b641  call    ??1?$CComPtrBase@VBackgroundCopyJobNotify@@@ATL@@QEAA@XZ; ATL::CComPtrBase<BackgroundCopyJobNotify>::~CComPtrBase<BackgroundCopyJobNotify>(void)
0x18000b646  mov     rcx, rsi
0x18000b649  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b64e  mov     rcx, [rbx+10h]; this
0x18000b652  test    rcx, rcx
0x18000b655  jz      short loc_18000B65C
0x18000b657  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000b65c  lea     rax, ??_7IMapsBackgroundTransferJob@@6B@; const IMapsBackgroundTransferJob::`vftable'
0x18000b663  mov     [rbx], rax
0x18000b666  mov     rbx, [rsp+28h+arg_0]
0x18000b66b  mov     rsi, [rsp+28h+arg_8]
0x18000b670  add     rsp, 20h
0x18000b674  pop     rdi
0x18000b675  retn
```
