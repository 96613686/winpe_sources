# Microsoft::IoT::Utility::MTAThreadPool::Stop(void)

- ea: `0x18000dd80`
- end: `0x18000de31`
- name: `?Stop@MTAThreadPool@Utility@IoT@Microsoft@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(Microsoft::IoT::Utility::MTAThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800081c4`
- `0x18000adbc`

## callees

- `0x18000a020`
- `0x18000d410`
- `0x18000dd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dddd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dddd`

## pseudocode

```c
void __fastcall Microsoft::IoT::Utility::MTAThreadPool::Stop(Microsoft::IoT::Utility::MTAThreadPool *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v7 = v1;
  *((_BYTE *)this + 272) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  *((_BYTE *)this + 273) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = *((_QWORD *)this + 11);
  v4 = *((_QWORD *)this + 10);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( v4 != v3 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(v4, v3);
    *((_QWORD *)this + 11) = *((_QWORD *)this + 10);
  }
  v5 = *((_QWORD *)this + 8);
  v6 = *((_QWORD *)this + 7);
  if ( v6 != v5 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(v6, v5);
    *((_QWORD *)this + 8) = *((_QWORD *)this + 7);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
}

```

## disassembly

```asm
0x18000dd80  mov     [rsp+arg_8], rbx
0x18000dd85  push    rdi
0x18000dd86  sub     rsp, 20h
0x18000dd8a  lea     rbx, [rcx+0B8h]
0x18000dd91  mov     rdi, rcx
0x18000dd94  mov     rcx, rbx; lpCriticalSection
0x18000dd97  call    cs:__imp_EnterCriticalSection
0x18000dd9d  lea     rcx, [rsp+28h+arg_0]
0x18000dda2  mov     [rsp+28h+arg_0], rbx
0x18000dda7  mov     byte ptr [rdi+110h], 1
0x18000ddae  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000ddb3  lea     rbx, [rdi+68h]
0x18000ddb7  mov     rcx, rbx; lpCriticalSection
0x18000ddba  call    cs:__imp_EnterCriticalSection
0x18000ddc0  lea     rcx, [rsp+28h+arg_0]
0x18000ddc5  mov     [rsp+28h+arg_0], rbx
0x18000ddca  mov     byte ptr [rdi+111h], 1
0x18000ddd1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000ddd6  lea     rbx, [rdi+10h]
0x18000ddda  mov     rcx, rbx; lpCriticalSection
0x18000dddd  call    cs:__imp_EnterCriticalSection
0x18000dde3  mov     rdx, [rdi+58h]
0x18000dde7  mov     rcx, [rdi+50h]
0x18000ddeb  mov     [rsp+28h+arg_0], rbx
0x18000ddf0  cmp     rcx, rdx
0x18000ddf3  jz      short loc_18000DE02
0x18000ddf5  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)
0x18000ddfa  mov     rax, [rdi+50h]
0x18000ddfe  mov     [rdi+58h], rax
0x18000de02  mov     rdx, [rdi+40h]
0x18000de06  mov     rcx, [rdi+38h]
0x18000de0a  cmp     rcx, rdx
0x18000de0d  jz      short loc_18000DE1C
0x18000de0f  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> *,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::allocator<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>> &)
0x18000de14  mov     rax, [rdi+38h]
0x18000de18  mov     [rdi+40h], rax
0x18000de1c  lea     rcx, [rsp+28h+arg_0]
0x18000de21  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000de26  mov     rbx, [rsp+28h+arg_8]
0x18000de2b  add     rsp, 20h
0x18000de2f  pop     rdi
0x18000de30  retn
```
