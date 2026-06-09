# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize(void)

- ea: `0x18000b804`
- end: `0x18000b994`
- name: `?Initialize@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJXZ`
- size: `400`
- prototype: `__int64 __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b9cc`

## callees

- `0x180002b10`
- `0x180002f1c`
- `0x180003998`
- `0x18000430c`
- `0x180004580`
- `0x180008378`
- `0x180009f6c`
- `0x18000a3ac`
- `0x18000aa90`
- `0x18000ab9c`
- `0x18000b804`
- `0x18000c300`
- `0x18000c6ec`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000b838`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000b838`

## string_xrefs

- `0x18000b957`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Initialize(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  _DWORD *v4; // rdi
  std::_Ref_count_base *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v8; // rax
  struct wil::details::wnf_subscription_state_base *v9; // rdx
  Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *v10; // r14
  wil::details **v11; // rdi
  wil::details *v12; // r15
  wil::details *v13; // rsi
  struct wil::details::wnf_subscription_state_base *v14; // rdx
  char *v15; // [rsp+20h] [rbp-D8h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-D0h] BYREF
  _DWORD *v17; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-B8h] BYREF
  _QWORD v19[18]; // [rsp+48h] [rbp-B0h] BYREF

  result = RoInitialize(1);
  v3 = result;
  if ( (int)result >= 0 )
  {
    LODWORD(v15) = 4;
    v16 = 1;
    v4 = operator new(0x128u);
    v17 = v4;
    v4[2] = 1;
    v4[3] = 1;
    *(_QWORD *)v4 = &std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAThreadPool>::`vftable';
    std::_Construct_in_place<Microsoft::IoT::Utility::MTAThreadPool,int,int>(
      (Microsoft::IoT::Utility::MTAThreadPool *)(v4 + 4),
      &v16,
      (unsigned int *)&v15);
    *((_QWORD *)this + 9) = v4 + 4;
    v5 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v4;
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
    v6 = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            &v17,
            (__int64)this);
    v19[0] = off_18001C368;
    v19[1] = v6;
    v19[13] = v19;
    v8 = (Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *)wil::make_wnf_subscription<wil::details::empty_wnf_state>(
                                                                 &v15,
                                                                 v7,
                                                                 (__int64)v18);
    v10 = v8;
    v11 = (wil::details **)((char *)this + 96);
    if ( (Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *)((char *)this + 96) != v8 )
    {
      v12 = *(wil::details **)v8;
      v13 = *v11;
      if ( *v11 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
        wil::details::delete_wnf_subscription_state(v13, v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
      }
      *v11 = v12;
      *(_QWORD *)v10 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
      (wil::details **)&v15,
      v9);
    wistd::function<void (void)>::~function<void (void)>(v18);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000b804  mov     [rsp+arg_8], rbx
0x18000b809  mov     [rsp+arg_10], rsi
0x18000b80e  push    rdi
0x18000b80f  push    r14
0x18000b811  push    r15
0x18000b813  sub     rsp, 0E0h
0x18000b81a  mov     rax, cs:__security_cookie
0x18000b821  xor     rax, rsp
0x18000b824  mov     [rsp+0F8h+var_20], rax
0x18000b82c  mov     rsi, rcx
0x18000b82f  mov     r14d, 1
0x18000b835  mov     ecx, r14d
0x18000b838  call    cs:__imp_RoInitialize
0x18000b83e  mov     ebx, eax
0x18000b840  test    eax, eax
0x18000b842  js      loc_18000B96A
0x18000b848  mov     dword ptr [rsp+0F8h+var_D8], 4
0x18000b850  mov     [rsp+0F8h+var_D0], r14d
0x18000b855  mov     ecx, 128h; Size
0x18000b85a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b85f  mov     rdi, rax
0x18000b862  mov     [rsp+0F8h+var_C8], rax
0x18000b867  mov     [rax+8], r14d
0x18000b86b  mov     [rax+0Ch], r14d
0x18000b86f  lea     rax, ??_7?$_Ref_count_obj2@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::IoT::Utility::MTAThreadPool>::`vftable'
0x18000b876  mov     [rdi], rax
0x18000b879  lea     r14, [rdi+10h]
0x18000b87d  lea     r8, [rsp+0F8h+var_D8]
0x18000b882  lea     rdx, [rsp+0F8h+var_D0]
0x18000b887  mov     rcx, r14
0x18000b88a  call    ??$_Construct_in_place@VMTAThreadPool@Utility@IoT@Microsoft@@HH@std@@YAXAEAVMTAThreadPool@Utility@IoT@Microsoft@@$$QEAH1@Z; std::_Construct_in_place<Microsoft::IoT::Utility::MTAThreadPool,int,int>(Microsoft::IoT::Utility::MTAThreadPool &,int &&,int &&)
0x18000b88f  nop
0x18000b890  mov     [rsi+48h], r14
0x18000b894  mov     rcx, [rsi+50h]; this
0x18000b898  mov     [rsi+50h], rdi
0x18000b89c  test    rcx, rcx
0x18000b89f  jz      short loc_18000B8A6
0x18000b8a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b8a6  mov     rdx, rsi
0x18000b8a9  lea     rcx, [rsp+0F8h+var_C8]
0x18000b8ae  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000b8b3  mov     rcx, [rax]
0x18000b8b6  lea     rax, off_18001C368
0x18000b8bd  mov     [rsp+0F8h+var_B0], rax
0x18000b8c2  mov     [rsp+0F8h+var_A8], rcx
0x18000b8c7  lea     rax, [rsp+0F8h+var_B0]
0x18000b8cc  mov     [rsp+0F8h+var_48], rax
0x18000b8d4  lea     r8, [rsp+0F8h+var_B8]
0x18000b8d9  lea     rcx, [rsp+0F8h+var_D8]
0x18000b8de  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18000b8e3  mov     r14, rax
0x18000b8e6  lea     rdi, [rsi+60h]
0x18000b8ea  cmp     rdi, rax
0x18000b8ed  jz      short loc_18000B920
0x18000b8ef  mov     r15, [rax]
0x18000b8f2  mov     rsi, [rdi]
0x18000b8f5  test    rsi, rsi
0x18000b8f8  jz      short loc_18000B916
0x18000b8fa  lea     rcx, [rsp+0F8h+var_D0]; this
0x18000b8ff  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000b904  mov     rcx, rsi; this
0x18000b907  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18000b90c  lea     rcx, [rsp+0F8h+var_D0]; this
0x18000b911  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b916  mov     [rdi], r15
0x18000b919  mov     qword ptr [r14], 0
0x18000b920  lea     rcx, [rsp+0F8h+var_D8]
0x18000b925  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18000b92a  nop
0x18000b92b  lea     rcx, [rsp+0F8h+var_B8]
0x18000b930  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18000b935  nop
0x18000b936  jmp     short loc_18000B968
0x18000b938  mov     ebx, dword ptr [rsp+0F8h+var_D8]
0x18000b93c  test    ebx, ebx
0x18000b93e  jns     short loc_18000B968
0x18000b940  jmp     short loc_18000B94C
0x18000b942  jmp     short loc_18000B948
0x18000b944  jmp     short loc_18000B948
0x18000b946  jmp     short $+2
0x18000b948  mov     ebx, dword ptr [rsp+0F8h+var_D8]
0x18000b94c  mov     rcx, [rsp+0F8h]; this
0x18000b954  mov     r9d, ebx; char *
0x18000b957  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b95e  mov     edx, 64h ; 'd'; void *
0x18000b963  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b968  mov     eax, ebx
0x18000b96a  mov     rcx, [rsp+0F8h+var_20]
0x18000b972  xor     rcx, rsp; StackCookie
0x18000b975  call    __security_check_cookie
0x18000b97a  lea     r11, [rsp+0F8h+var_18]
0x18000b982  mov     rbx, [r11+28h]
0x18000b986  mov     rsi, [r11+30h]
0x18000b98a  mov     rsp, r11
0x18000b98d  pop     r15
0x18000b98f  pop     r14
0x18000b991  pop     rdi
0x18000b992  retn
```
