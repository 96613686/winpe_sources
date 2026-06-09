# Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *)

- ea: `0x18000da64`
- end: `0x18000dc7d`
- name: `?QueueWorkItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJPEAUIMTAThreadPoolWorkCallback@234@@Z`
- size: `537`
- prototype: `__int64 __fastcall(Microsoft::IoT::Utility::MTAThreadPool *__hidden this, struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b0a0`
- `0x18000de50`
- `0x180010db8`

## callees

- `0x180002f1c`
- `0x18000c300`
- `0x18000ca78`
- `0x18000cb74`
- `0x18000cc14`
- `0x18000cee0`
- `0x18000d1cc`
- `0x18000d410`
- `0x18000d7c8`
- `0x18000da64`
- `0x18000dc84`
- `0x18000dcb4`
- `0x18000dce4`
- `0x18000de38`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000daec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000daec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(
        Microsoft::IoT::Utility::MTAThreadPool *this,
        struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  _QWORD **v6; // r14
  __int64 v7; // rax
  unsigned int v8; // r15d
  _QWORD *v9; // rdi
  _QWORD *i; // rbx
  void *v11; // rdx
  void *v12; // rdx
  wil::details *v13; // rcx
  _DWORD *v14; // rdi
  __int64 v15; // rdx
  __int64 *v16; // rcx
  Microsoft::IoT::Utility::MTAThread *v17; // [rsp+20h] [rbp-10h] BYREF
  std::_Ref_count_base *v18; // [rsp+28h] [rbp-8h]
  struct Microsoft::IoT::Utility::MTAThreadPool *v19; // [rsp+60h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+70h] [rbp+40h] BYREF
  _DWORD *v21; // [rsp+78h] [rbp+48h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v20 = v4;
  if ( *((_BYTE *)this + 273) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
    return 0;
  }
  else
  {
    v19 = a2;
    Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(&v19);
    std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(
      (__int64)this + 144,
      (__int64)&v19);
    if ( v19 )
      (*(void (__fastcall **)(struct Microsoft::IoT::Utility::MTAThreadPool *))(*(_QWORD *)v19 + 16LL))(v19);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    v6 = (_QWORD **)((char *)this + 80);
    v7 = (__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 4;
    if ( (unsigned int)v7 < *((_DWORD *)this + 66)
      || *((_QWORD *)this + 22) > 4u && (unsigned int)v7 < *((_DWORD *)this + 67) )
    {
      v19 = this;
      v14 = operator new(0x40u);
      v21 = v14;
      *(_OWORD *)v14 = 0;
      v14[2] = 1;
      v14[3] = 1;
      *(_QWORD *)v14 = &std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAEventThread>::`vftable';
      std::_Construct_in_place<Microsoft::IoT::Utility::MTAThread,Microsoft::IoT::Utility::MTAThreadPool *>(
        (Microsoft::IoT::Utility::MTAThread *)(v14 + 4),
        &v19);
      v17 = (Microsoft::IoT::Utility::MTAThread *)(v14 + 4);
      v18 = (std::_Ref_count_base *)v14;
      v15 = *((_QWORD *)this + 11);
      v16 = (__int64 *)((char *)this + 80);
      if ( v15 == *((_QWORD *)this + 12) )
        std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(
          v16,
          v15,
          &v17);
      else
        std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(
          (__int64)v16,
          &v17);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v17,
        (_QWORD *)(*((_QWORD *)this + 11) - 16LL));
      v8 = Microsoft::IoT::Utility::MTAThread::Start(v17);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
    }
    else
    {
      v8 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v19 = (Microsoft::IoT::Utility::MTAThreadPool *)((char *)this + 16);
      v9 = (_QWORD *)*((_QWORD *)this + 11);
      for ( i = *v6; i != v9 && !(unsigned __int8)Microsoft::IoT::Utility::MTAThreadPool::WorkerIdle(i); i += 2 )
        ;
      if ( i == *((_QWORD **)this + 11) )
        i = *v6;
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v17,
        i);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>((struct _RTL_CRITICAL_SECTION **)&v19);
      wil::details::SetEvent(*((wil::details **)v17 + 2), v11);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      if ( *((_BYTE *)this + 273) || *((_QWORD *)this + 22) > 4u )
      {
        v13 = *(wil::details **)this;
        if ( *(_QWORD *)this )
          v13 = *(wil::details **)v13;
        wil::details::ResetEvent(v13, v12);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
    return v8;
  }
}

```

## disassembly

```asm
0x18000da64  mov     [rsp-28h+arg_8], rbx
0x18000da69  push    rbp
0x18000da6a  push    rsi
0x18000da6b  push    rdi
0x18000da6c  push    r14
0x18000da6e  push    r15
0x18000da70  mov     rbp, rsp
0x18000da73  sub     rsp, 30h
0x18000da77  mov     rdi, rdx
0x18000da7a  mov     rsi, rcx
0x18000da7d  lea     rbx, [rcx+68h]
0x18000da81  mov     rcx, rbx; lpCriticalSection
0x18000da84  call    cs:__imp_EnterCriticalSection
0x18000da8a  mov     [rbp+arg_10], rbx
0x18000da8e  cmp     byte ptr [rsi+111h], 0
0x18000da95  jz      short loc_18000DAA7
0x18000da97  lea     rcx, [rbp+arg_10]
0x18000da9b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000daa0  xor     eax, eax
0x18000daa2  jmp     loc_18000DC6C
0x18000daa7  mov     [rbp+arg_0], rdi
0x18000daab  lea     rcx, [rbp+arg_0]
0x18000daaf  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000dab4  nop
0x18000dab5  lea     rdx, [rbp+arg_0]
0x18000dab9  lea     rcx, [rsi+90h]
0x18000dac0  call    ??$_Emplace_back_internal@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAX$$QEAV?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@Z; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Emplace_back_internal<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback> &&)
0x18000dac5  nop
0x18000dac6  mov     rcx, [rbp+arg_0]
0x18000daca  test    rcx, rcx
0x18000dacd  jz      short loc_18000DADC
0x18000dacf  mov     rax, [rcx]
0x18000dad2  mov     rax, [rax+10h]
0x18000dad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dadb  nop
0x18000dadc  lea     rcx, [rbp+arg_10]
0x18000dae0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000dae5  lea     rbx, [rsi+10h]
0x18000dae9  mov     rcx, rbx; lpCriticalSection
0x18000daec  call    cs:__imp_EnterCriticalSection
0x18000daf2  mov     [rbp+arg_10], rbx
0x18000daf6  lea     r14, [rsi+50h]
0x18000dafa  mov     rax, [r14+8]
0x18000dafe  sub     rax, [r14]
0x18000db01  sar     rax, 4
0x18000db05  cmp     eax, [rsi+108h]
0x18000db0b  jb      loc_18000DBBB
0x18000db11  cmp     qword ptr [rsi+0B0h], 4
0x18000db19  jbe     short loc_18000DB27
0x18000db1b  cmp     eax, [rsi+10Ch]
0x18000db21  jb      loc_18000DBBB
0x18000db27  xor     r15d, r15d
0x18000db2a  mov     rcx, rbx; lpCriticalSection
0x18000db2d  call    cs:__imp_EnterCriticalSection
0x18000db33  mov     [rbp+arg_0], rbx
0x18000db37  mov     rdi, [r14+8]
0x18000db3b  mov     rbx, [r14]
0x18000db3e  jmp     short loc_18000DB50
0x18000db40  mov     rcx, rbx
0x18000db43  call    ?WorkerIdle@MTAThreadPool@Utility@IoT@Microsoft@@CA_NAEBV?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@@Z; Microsoft::IoT::Utility::MTAThreadPool::WorkerIdle(std::shared_ptr<Microsoft::IoT::Utility::MTAThread> const &)
0x18000db48  test    al, al
0x18000db4a  jnz     short loc_18000DB55
0x18000db4c  add     rbx, 10h
0x18000db50  cmp     rbx, rdi
0x18000db53  jnz     short loc_18000DB40
0x18000db55  cmp     rbx, [r14+8]
0x18000db59  jnz     short loc_18000DB5E
0x18000db5b  mov     rbx, [r14]
0x18000db5e  mov     rdx, rbx
0x18000db61  lea     rcx, [rbp+var_10]
0x18000db65  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18000db6a  nop
0x18000db6b  lea     rcx, [rbp+arg_0]
0x18000db6f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000db74  mov     rcx, [rbp+var_10]
0x18000db78  mov     rcx, [rcx+10h]; this
0x18000db7c  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000db81  mov     rcx, [rbp+var_8]; this
0x18000db85  test    rcx, rcx
0x18000db88  jz      short loc_18000DB8F
0x18000db8a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000db8f  cmp     byte ptr [rsi+111h], 0
0x18000db96  jnz     short loc_18000DBA6
0x18000db98  cmp     qword ptr [rsi+0B0h], 4
0x18000dba0  jbe     loc_18000DC60
0x18000dba6  mov     rcx, [rsi]
0x18000dba9  test    rcx, rcx
0x18000dbac  jz      short loc_18000DBB1
0x18000dbae  mov     rcx, [rcx]; this
0x18000dbb1  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18000dbb6  jmp     loc_18000DC60
0x18000dbbb  mov     [rbp+arg_0], rsi
0x18000dbbf  mov     ecx, 40h ; '@'; Size
0x18000dbc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dbc9  mov     rdi, rax
0x18000dbcc  mov     [rbp+arg_18], rax
0x18000dbd0  xorps   xmm0, xmm0
0x18000dbd3  movups  xmmword ptr [rax], xmm0
0x18000dbd6  mov     eax, 1
0x18000dbdb  mov     [rdi+8], eax
0x18000dbde  mov     [rdi+0Ch], eax
0x18000dbe1  lea     rax, ??_7?$_Ref_count_obj2@VMTAEventThread@Utility@IoT@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAEventThread>::`vftable'
0x18000dbe8  mov     [rdi], rax
0x18000dbeb  lea     rbx, [rdi+10h]
0x18000dbef  lea     rdx, [rbp+arg_0]
0x18000dbf3  mov     rcx, rbx
0x18000dbf6  call    ??$_Construct_in_place@VMTAThread@Utility@IoT@Microsoft@@PEAVMTAThreadPool@234@@std@@YAXAEAVMTAThread@Utility@IoT@Microsoft@@$$QEAPEAVMTAThreadPool@234@@Z; std::_Construct_in_place<Microsoft::IoT::Utility::MTAThread,Microsoft::IoT::Utility::MTAThreadPool *>(Microsoft::IoT::Utility::MTAThread &,Microsoft::IoT::Utility::MTAThreadPool * &&)
0x18000dbfb  nop
0x18000dbfc  mov     [rbp+var_10], rbx
0x18000dc00  mov     [rbp+var_8], rdi
0x18000dc04  mov     rdx, [r14+8]
0x18000dc08  mov     rcx, r14
0x18000dc0b  cmp     rdx, [r14+10h]
0x18000dc0f  jz      short loc_18000DC1C
0x18000dc11  lea     rdx, [rbp+var_10]
0x18000dc15  call    ??$_Emplace_back_with_unused_capacity@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@AEAAAEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_back_with_unused_capacity<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> &&)
0x18000dc1a  jmp     short loc_18000DC26
0x18000dc1c  lea     r8, [rbp+var_10]
0x18000dc20  call    ??$_Emplace_reallocate@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@?$vector@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VMTAEventThread@Utility@IoT@Microsoft@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>::_Emplace_reallocate<std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread>>(std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> * const,std::shared_ptr<Microsoft::IoT::Utility::MTAEventThread> &&)
0x18000dc25  nop
0x18000dc26  mov     rcx, [rbp+var_8]; this
0x18000dc2a  test    rcx, rcx
0x18000dc2d  jz      short loc_18000DC34
0x18000dc2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000dc34  mov     rdx, [r14+8]
0x18000dc38  sub     rdx, 10h
0x18000dc3c  lea     rcx, [rbp+var_10]
0x18000dc40  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18000dc45  mov     rcx, [rbp+var_10]; this
0x18000dc49  call    ?Start@MTAThread@Utility@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::Utility::MTAThread::Start(void)
0x18000dc4e  mov     r15d, eax
0x18000dc51  mov     rcx, [rbp+var_8]; this
0x18000dc55  test    rcx, rcx
0x18000dc58  jz      short loc_18000DC60
0x18000dc5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000dc5f  nop
0x18000dc60  lea     rcx, [rbp+arg_10]
0x18000dc64  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000dc69  mov     eax, r15d
0x18000dc6c  mov     rbx, [rsp+30h+arg_8]
0x18000dc71  add     rsp, 30h
0x18000dc75  pop     r15
0x18000dc77  pop     r14
0x18000dc79  pop     rdi
0x18000dc7a  pop     rsi
0x18000dc7b  pop     rbp
0x18000dc7c  retn
```
