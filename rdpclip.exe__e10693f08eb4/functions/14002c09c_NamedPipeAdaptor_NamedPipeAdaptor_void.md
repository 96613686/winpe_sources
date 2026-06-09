# NamedPipeAdaptor::~NamedPipeAdaptor(void)

- ea: `0x14002c09c`
- end: `0x14002c23f`
- name: `??1NamedPipeAdaptor@@UEAA@XZ`
- size: `419`
- prototype: `void __fastcall(NamedPipeAdaptor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002c38c`

## callees

- `0x140006210`
- `0x140014d64`
- `0x14002bfc8`
- `0x14002c014`
- `0x14002c030`
- `0x14002c054`
- `0x14002c09c`
- `0x14002c248`
- `0x14002dd04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c132`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c0ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002c0ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c0d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002c0d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c13f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c13f`

## pseudocode

```c
void __fastcall NamedPipeAdaptor::~NamedPipeAdaptor(NamedPipeAdaptor *this)
{
  int v2; // esi
  void *v3; // rdx
  int v4; // esi

  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &NamedPipeAdaptor::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 6) = &NamedPipeAdaptor::`vftable';
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  v2 = *((_DWORD *)this + 48);
  *((_DWORD *)this + 48) = 4;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
  v4 = v2 - 1;
  if ( !v4 || (unsigned int)(v4 - 1) <= 1 )
    wil::details::SetEvent(*((wil::details **)this + 53), v3);
  if ( *((_QWORD *)this + 22) )
  {
    if ( *((_DWORD *)this + 46) == GetCurrentThreadId() )
      __int2c();
    WaitForSingleObject(*((HANDLE *)this + 22), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 22));
    *((_QWORD *)this + 22) = 0;
    *((_DWORD *)this + 46) = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 424);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 408);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 400);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 384);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 376);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 360);
  utl::unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>::~unique_ptr<utl::vector<unsigned char,utl::allocator<unsigned char>>,utl::default_delete<utl::vector<unsigned char,utl::allocator<unsigned char>>>>((char *)this + 352);
  OverlappedState::~OverlappedState((NamedPipeAdaptor *)((char *)this + 272));
  OverlappedState::~OverlappedState((NamedPipeAdaptor *)((char *)this + 208));
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 200);
  if ( *((_QWORD *)this + 22) )
    __int2c();
  wil::com_ptr_t<ITSPlatform,wil::err_returncode_policy>::~com_ptr_t<ITSPlatform,wil::err_returncode_policy>((char *)this + 168);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 160);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 152);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 104);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 72);
  *((_QWORD *)this + 6) = &INamedPipeAdaptor::`vftable';
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTSObject::`vftable';
  *((_DWORD *)this + 7) |= 8u;
}

```

## disassembly

```asm
0x14002c09c  mov     [rsp+arg_0], rbx
0x14002c0a1  mov     [rsp+arg_8], rsi
0x14002c0a6  push    rdi
0x14002c0a7  sub     rsp, 20h
0x14002c0ab  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x14002c0b2  mov     rdi, rcx
0x14002c0b5  mov     [rcx], rax
0x14002c0b8  lea     rax, ??_7NamedPipeAdaptor@@6BCTSObject@@@; const NamedPipeAdaptor::`vftable'{for `CTSObject'}
0x14002c0bf  mov     [rcx+8], rax
0x14002c0c3  lea     rax, ??_7NamedPipeAdaptor@@6B@; const NamedPipeAdaptor::`vftable'
0x14002c0ca  mov     [rcx+30h], rax
0x14002c0ce  add     rcx, 38h ; '8'; SRWLock
0x14002c0d2  call    cs:__imp_AcquireSRWLockExclusive
0x14002c0d8  mov     esi, [rdi+0C0h]
0x14002c0de  lea     rcx, [rdi+38h]; SRWLock
0x14002c0e2  mov     dword ptr [rdi+0C0h], 4
0x14002c0ec  call    cs:__imp_ReleaseSRWLockExclusive
0x14002c0f2  sub     esi, 1
0x14002c0f5  jz      short loc_14002C101
0x14002c0f7  sub     esi, 1
0x14002c0fa  jz      short loc_14002C101
0x14002c0fc  cmp     esi, 1
0x14002c0ff  jnz     short loc_14002C10D
0x14002c101  mov     rcx, [rdi+1A8h]; this
0x14002c108  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14002c10d  xor     ebx, ebx
0x14002c10f  cmp     [rdi+0B0h], rbx
0x14002c116  jz      short loc_14002C152
0x14002c118  call    cs:__imp_GetCurrentThreadId
0x14002c11e  cmp     [rdi+0B8h], eax
0x14002c124  jnz     short loc_14002C128
0x14002c126  int     2Ch; Windows NT - assertion failure
0x14002c128  mov     rcx, [rdi+0B0h]; hHandle
0x14002c12f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002c132  call    cs:__imp_WaitForSingleObject
0x14002c138  mov     rcx, [rdi+0B0h]; hObject
0x14002c13f  call    cs:__imp_CloseHandle
0x14002c145  mov     [rdi+0B0h], rbx
0x14002c14c  mov     [rdi+0B8h], ebx
0x14002c152  lea     rcx, [rdi+1A8h]
0x14002c159  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c15e  lea     rcx, [rdi+198h]
0x14002c165  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c16a  lea     rcx, [rdi+190h]
0x14002c171  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c176  lea     rcx, [rdi+180h]
0x14002c17d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c182  lea     rcx, [rdi+178h]
0x14002c189  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c18e  lea     rcx, [rdi+168h]
0x14002c195  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002c19a  lea     rcx, [rdi+160h]
0x14002c1a1  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@utl@@@utl@@U?$default_delete@V?$vector@EV?$allocator@E@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>::~unique_ptr<utl::vector<uchar,utl::allocator<uchar>>,utl::default_delete<utl::vector<uchar,utl::allocator<uchar>>>>(void)
0x14002c1a6  lea     rcx, [rdi+110h]; this
0x14002c1ad  call    ??1OverlappedState@@QEAA@XZ; OverlappedState::~OverlappedState(void)
0x14002c1b2  lea     rcx, [rdi+0D0h]; this
0x14002c1b9  call    ??1OverlappedState@@QEAA@XZ; OverlappedState::~OverlappedState(void)
0x14002c1be  lea     rcx, [rdi+0C8h]
0x14002c1c5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002c1ca  cmp     [rdi+0B0h], rbx
0x14002c1d1  jz      short loc_14002C1D5
0x14002c1d3  int     2Ch; Windows NT - assertion failure
0x14002c1d5  lea     rcx, [rdi+0A8h]
0x14002c1dc  call    ??1?$com_ptr_t@VITSPlatform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITSPlatform,wil::err_returncode_policy>::~com_ptr_t<ITSPlatform,wil::err_returncode_policy>(void)
0x14002c1e1  lea     rcx, [rdi+0A0h]
0x14002c1e8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002c1ed  lea     rcx, [rdi+98h]
0x14002c1f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002c1f9  lea     rcx, [rdi+68h]
0x14002c1fd  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x14002c202  lea     rcx, [rdi+48h]
0x14002c206  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x14002c20b  mov     rbx, [rsp+28h+arg_0]
0x14002c210  lea     rax, ??_7INamedPipeAdaptor@@6B@; const INamedPipeAdaptor::`vftable'
0x14002c217  mov     rsi, [rsp+28h+arg_8]
0x14002c21c  mov     [rdi+30h], rax
0x14002c220  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x14002c227  mov     [rdi], rax
0x14002c22a  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x14002c231  mov     [rdi+8], rax
0x14002c235  or      dword ptr [rdi+1Ch], 8
0x14002c239  add     rsp, 20h
0x14002c23d  pop     rdi
0x14002c23e  retn
```
