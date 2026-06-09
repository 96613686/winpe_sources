# RdpVirtualChannel::OnOpened(void)

- ea: `0x1800504e4`
- end: `0x180050af3`
- name: `?OnOpened@RdpVirtualChannel@@IEAAXXZ`
- size: `1551`
- prototype: `void __fastcall(RdpVirtualChannel *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800504a0`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001b6b8`
- `0x18004589c`
- `0x18004c7a4`
- `0x18004c814`
- `0x18004f4a4`
- `0x1800504e4`
- `0x180051adc`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800505e5`: `RdpVirtualChannel::OnOpened - Created -> DctOpened, channel='%s'`
- `0x180050693`: `RdpVirtualChannel::OnOpened - CallbacksSet -> Opened, channel='%s'`
- `0x180050733`: `RdpVirtualChannel::OnOpened`
- `0x1800508ac`: `RdpVirtualChannel::OnOpened`
- `0x1800509e2`: `RdpVirtualChannel::OnOpened`
- `0x180050747`: `C:\__w\1\s\rdpnanodll\RdpTransportStackAbi.cpp`
- `0x1800508c0`: `C:\__w\1\s\rdpnanodll\RdpTransportStackAbi.cpp`
- `0x1800509f6`: `C:\__w\1\s\rdpnanodll\RdpTransportStackAbi.cpp`
- `0x180050722`: `RdpVirtualChannel::OnOpened - unexpected state %d, channel='%s'\n    %s(%d): %s()`
- `0x18005089b`: `RdpVirtualChannel::OnOpened - VCControllerCallbacks ref expired, channel='%s'\n    %s(%d): %s()`
- `0x1800509d1`: `RdpVirtualChannel::OnOpened - callbacks ref expired, channel='%s'\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall RdpVirtualChannel::OnOpened(RdpVirtualChannel *this)
{
  char v2; // r13
  char v3; // r12
  struct IWeakReference *v4; // r14
  struct IWeakReference *v5; // r15
  char *v6; // rbx
  char v7; // al
  _QWORD *v8; // rdi
  _QWORD *v9; // rdi
  const char *v10; // r9
  _QWORD *v11; // r12
  int v12; // edi
  volatile signed __int32 *v13; // rdi
  void **v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rdx
  const char *v18; // r9
  _QWORD *v19; // rbx
  volatile signed __int32 *v20; // rbx
  void **v21; // rax
  const char *v22; // r9
  _QWORD *v23; // rsi
  volatile signed __int32 *v24; // rbx
  const char *v25; // [rsp+20h] [rbp-49h]
  const char *v26; // [rsp+28h] [rbp-41h]
  const char *v27; // [rsp+30h] [rbp-39h]
  __int128 v28; // [rsp+48h] [rbp-21h] BYREF
  __int128 v29; // [rsp+58h] [rbp-11h]
  struct IWeakReference *v30; // [rsp+68h] [rbp-1h]
  struct IWeakReference *v31; // [rsp+70h] [rbp+7h]
  __int128 v32; // [rsp+78h] [rbp+Fh] BYREF
  struct IVirtualChannelCallbacks *v33[2]; // [rsp+88h] [rbp+1Fh] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v30 = 0;
  v5 = 0;
  v31 = 0;
  v6 = (char *)this + 128;
  v33[0] = (RdpVirtualChannel *)((char *)this + 128);
  if ( Mtx_lock((RdpVirtualChannel *)((char *)this + 128)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v6 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v7 = *((_BYTE *)this + 208);
  if ( v7 == 1 )
  {
    *((_BYTE *)this + 208) = 2;
    if ( !*((_BYTE *)this + 209) )
    {
      v2 = 1;
      v4 = (struct IWeakReference *)*((_QWORD *)this + 7);
      v30 = v4;
      if ( v4 )
        ((void (__fastcall *)(struct IWeakReference *))v4->lpVtbl->AddRef)(v4);
    }
    v32 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v32);
    if ( (_QWORD)v32 && *(_BYTE *)(v32 + 128) )
    {
      v8 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) > 0xFu )
        v8 = (_QWORD *)*v8;
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(
        &v28,
        "RdpVirtualChannel::OnOpened - Created -> DctOpened, channel='%s'",
        (const char *)0x40);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(
        &v32,
        "RDPNANO",
        &v28,
        v8);
      std::string::_Tidy_deallocate(&v28);
    }
  }
  else if ( v7 == 3 )
  {
    *((_BYTE *)this + 208) = 4;
    v3 = 1;
    v5 = (struct IWeakReference *)*((_QWORD *)this + 8);
    v31 = v5;
    if ( v5 )
      ((void (__fastcall *)(struct IWeakReference *))v5->lpVtbl->AddRef)(v5);
    v32 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v32);
    if ( (_QWORD)v32 && *(_BYTE *)(v32 + 128) )
    {
      v9 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) > 0xFu )
        v9 = (_QWORD *)*v9;
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(
        &v28,
        "RdpVirtualChannel::OnOpened - CallbacksSet -> Opened, channel='%s'",
        (const char *)0x42);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(
        &v32,
        "RDPNANO",
        &v28,
        v9);
      std::string::_Tidy_deallocate(&v28);
    }
  }
  else
  {
    v32 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v32);
    if ( (_QWORD)v32 && *(_BYTE *)(v32 + 128) )
    {
      v11 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) > 0xFu )
        v11 = (_QWORD *)*v11;
      v12 = *((unsigned __int8 *)this + 208);
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(
        &v28,
        "RdpVirtualChannel::OnOpened - unexpected state %d, channel='%s'\n    %s(%d): %s()",
        80,
        v10,
        v25,
        (_DWORD)v26,
        v27);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,char const *,int,char const *>(
        (unsigned int)&v32,
        (unsigned int)"RDPNANO",
        (unsigned int)&v28,
        v12,
        (__int64)v11,
        (__int64)"C:\\__w\\1\\s\\rdpnanodll\\RdpTransportStackAbi.cpp",
        61,
        (__int64)"RdpVirtualChannel::OnOpened");
      std::string::_Tidy_deallocate(&v28);
      v3 = 0;
    }
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  Mtx_unlock((_Mtx_t)v6);
  if ( v2 )
  {
    *(_QWORD *)&v32 = 0;
    v14 = (void **)(*(__int64 (__fastcall **)(__int128 *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(&v32);
    wil::details::weak_query_policy::query(v4, &GUID_2243b2a4_3eff_4029_a0ac_45024ff03fe2, v14);
    if ( (_QWORD)v32 )
    {
      v33[0] = 0;
      v15 = (*(__int64 (__fastcall **)(RdpVirtualChannel *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(this);
      LOBYTE(v16) = 0;
      wil::com_ptr_t<IVirtualChannel,wil::err_exception_policy>::com_ptr_t<IVirtualChannel,wil::err_exception_policy>(
        v33,
        v15,
        v16);
      v17 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) > 0xFu )
        v17 = (_QWORD *)*v17;
      (*(void (__fastcall **)(_QWORD, _QWORD *, struct IVirtualChannelCallbacks *))(*(_QWORD *)v32 + 24LL))(
        v32,
        v17,
        v33[0]);
      if ( v33[0] )
        (*(void (__fastcall **)(struct IVirtualChannelCallbacks *))(*(_QWORD *)v33[0] + 16LL))(v33[0]);
    }
    else
    {
      *(_OWORD *)v33 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v33);
      if ( v33[0] && *((_BYTE *)v33[0] + 128) )
      {
        v19 = (_QWORD *)((char *)this + 72);
        if ( *((_QWORD *)this + 12) > 0xFu )
          v19 = (_QWORD *)*v19;
        v28 = 0;
        v29 = 0;
        std::string::_Construct<1,char const *>(
          &v28,
          "RdpVirtualChannel::OnOpened - VCControllerCallbacks ref expired, channel='%s'\n    %s(%d): %s()",
          (const char *)0x5E,
          v18,
          (_DWORD)v25,
          v26);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,int,char const *>(
          (unsigned int)v33,
          (unsigned int)"RDPNANO",
          (unsigned int)&v28,
          (_DWORD)v19,
          (__int64)"C:\\__w\\1\\s\\rdpnanodll\\RdpTransportStackAbi.cpp",
          74,
          (__int64)"RdpVirtualChannel::OnOpened");
        std::string::_Tidy_deallocate(&v28);
      }
      v20 = (volatile signed __int32 *)v33[1];
      if ( v33[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v33[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( !_InterlockedDecrement(v20 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
    }
    if ( (_QWORD)v32 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 16LL))(v32);
  }
  if ( v3 )
  {
    v33[0] = 0;
    v21 = (void **)(*(__int64 (__fastcall **)(struct IVirtualChannelCallbacks **))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v33);
    wil::details::weak_query_policy::query(v5, &GUID_6a04ebe4_82bd_4f11_aab5_3f60e5822e36, v21);
    if ( v33[0] )
    {
      RdpVirtualChannel::FireOnOpenedCbAsync(this, v33[0]);
    }
    else
    {
      v32 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v32);
      if ( (_QWORD)v32 && *(_BYTE *)(v32 + 128) )
      {
        v23 = (_QWORD *)((char *)this + 72);
        if ( v23[3] > 0xFu )
          v23 = (_QWORD *)*v23;
        v28 = 0;
        v29 = 0;
        std::string::_Construct<1,char const *>(
          &v28,
          "RdpVirtualChannel::OnOpened - callbacks ref expired, channel='%s'\n    %s(%d): %s()",
          (const char *)0x52,
          v22,
          (_DWORD)v25,
          v26);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,int,char const *>(
          (unsigned int)&v32,
          (unsigned int)"RDPNANO",
          (unsigned int)&v28,
          (_DWORD)v23,
          (__int64)"C:\\__w\\1\\s\\rdpnanodll\\RdpTransportStackAbi.cpp",
          86,
          (__int64)"RdpVirtualChannel::OnOpened");
        std::string::_Tidy_deallocate(&v28);
      }
      v24 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
      if ( *((_QWORD *)&v32 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( !_InterlockedDecrement(v24 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
    }
    if ( v33[0] )
      (*(void (__fastcall **)(struct IVirtualChannelCallbacks *))(*(_QWORD *)v33[0] + 16LL))(v33[0]);
  }
  if ( v5 )
    ((void (__fastcall *)(struct IWeakReference *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    ((void (__fastcall *)(struct IWeakReference *))v4->lpVtbl->Release)(v4);
}

```

## disassembly

```asm
0x1800504e4  mov     rax, rsp
0x1800504e7  mov     [rax+10h], rbx
0x1800504eb  mov     [rax+18h], rsi
0x1800504ef  mov     [rax+20h], rdi
0x1800504f3  push    rbp
0x1800504f4  push    r12
0x1800504f6  push    r13
0x1800504f8  push    r14
0x1800504fa  push    r15
0x1800504fc  lea     rbp, [rax-5Fh]
0x180050500  mov     eax, 0A0h
0x180050505  call    _alloca_probe
0x18005050a  sub     rsp, rax
0x18005050d  mov     rax, cs:__security_cookie
0x180050514  xor     rax, rsp
0x180050517  mov     [rbp+57h+var_28], rax
0x18005051b  mov     rsi, rcx
0x18005051e  xor     edi, edi
0x180050520  mov     r13b, dil
0x180050523  mov     r12b, dil
0x180050526  mov     [rbp+57h+var_80], dil
0x18005052a  mov     r14d, edi
0x18005052d  mov     [rbp+57h+var_58], rdi
0x180050531  mov     r15d, edi
0x180050534  mov     [rbp+57h+var_50], rdi
0x180050538  lea     rbx, [rcx+80h]
0x18005053f  mov     [rbp+57h+var_38], rbx
0x180050543  mov     rcx, rbx; _Mtx_t
0x180050546  call    _Mtx_lock
0x18005054b  test    eax, eax
0x18005054d  jnz     loc_180050AE8
0x180050553  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18005055a  jz      loc_180050AD6
0x180050560  mov     al, [rsi+0D0h]
0x180050566  cmp     al, 1
0x180050568  jnz     loc_18005061D
0x18005056e  mov     byte ptr [rsi+0D0h], 2
0x180050575  cmp     [rsi+0D1h], dil
0x18005057c  jnz     short loc_18005059F
0x18005057e  mov     r13b, al
0x180050581  mov     r14, [rsi+38h]
0x180050585  mov     [rbp+57h+var_58], r14
0x180050589  test    r14, r14
0x18005058c  jz      short loc_18005059F
0x18005058e  mov     rax, [r14]
0x180050591  mov     rcx, r14
0x180050594  mov     rax, [rax+8]
0x180050598  call    cs:__guard_dispatch_icall_fptr
0x18005059e  nop
0x18005059f  xorps   xmm0, xmm0
0x1800505a2  movups  [rbp+57h+var_48], xmm0
0x1800505a6  lea     rcx, [rbp+57h+var_48]
0x1800505aa  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800505af  nop
0x1800505b0  mov     rax, qword ptr [rbp+57h+var_48]
0x1800505b4  test    rax, rax
0x1800505b7  jz      short loc_180050618
0x1800505b9  cmp     [rax+80h], dil
0x1800505c0  jz      short loc_180050618
0x1800505c2  lea     rdi, [rsi+48h]
0x1800505c6  cmp     qword ptr [rdi+18h], 0Fh
0x1800505cb  jbe     short loc_1800505D0
0x1800505cd  mov     rdi, [rdi]
0x1800505d0  xorps   xmm0, xmm0
0x1800505d3  movups  [rbp+57h+var_78], xmm0
0x1800505d7  xorps   xmm1, xmm1
0x1800505da  movdqu  [rbp+57h+var_68], xmm1
0x1800505df  mov     r8d, 40h ; '@'
0x1800505e5  lea     rdx, aRdpvirtualchan_9; "RdpVirtualChannel::OnOpened - Created -"...
0x1800505ec  lea     rcx, [rbp+57h+var_78]
0x1800505f0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800505f5  nop
0x1800505f6  mov     r9, rdi
0x1800505f9  lea     r8, [rbp+57h+var_78]
0x1800505fd  lea     rdx, aRdpnano; "RDPNANO"
0x180050604  lea     rcx, [rbp+57h+var_48]
0x180050608  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *)
0x18005060d  nop
0x18005060e  lea     rcx, [rbp+57h+var_78]
0x180050612  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180050617  nop
0x180050618  jmp     loc_18005077D
0x18005061d  cmp     al, 3
0x18005061f  jnz     loc_1800506CB
0x180050625  mov     byte ptr [rsi+0D0h], 4
0x18005062c  mov     r12b, 1
0x18005062f  mov     r15, [rsi+40h]
0x180050633  mov     [rbp+57h+var_50], r15
0x180050637  test    r15, r15
0x18005063a  jz      short loc_18005064D
0x18005063c  mov     rax, [r15]
0x18005063f  mov     rcx, r15
0x180050642  mov     rax, [rax+8]
0x180050646  call    cs:__guard_dispatch_icall_fptr
0x18005064c  nop
0x18005064d  xorps   xmm0, xmm0
0x180050650  movups  [rbp+57h+var_48], xmm0
0x180050654  lea     rcx, [rbp+57h+var_48]
0x180050658  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18005065d  nop
0x18005065e  mov     rax, qword ptr [rbp+57h+var_48]
0x180050662  test    rax, rax
0x180050665  jz      short loc_1800506C6
0x180050667  cmp     [rax+80h], dil
0x18005066e  jz      short loc_1800506C6
0x180050670  lea     rdi, [rsi+48h]
0x180050674  cmp     qword ptr [rdi+18h], 0Fh
0x180050679  jbe     short loc_18005067E
0x18005067b  mov     rdi, [rdi]
0x18005067e  xorps   xmm0, xmm0
0x180050681  movups  [rbp+57h+var_78], xmm0
0x180050685  xorps   xmm1, xmm1
0x180050688  movdqu  [rbp+57h+var_68], xmm1
0x18005068d  mov     r8d, 42h ; 'B'
0x180050693  lea     rdx, aRdpvirtualchan_6; "RdpVirtualChannel::OnOpened - Callbacks"...
0x18005069a  lea     rcx, [rbp+57h+var_78]
0x18005069e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800506a3  nop
0x1800506a4  mov     r9, rdi
0x1800506a7  lea     r8, [rbp+57h+var_78]
0x1800506ab  lea     rdx, aRdpnano; "RDPNANO"
0x1800506b2  lea     rcx, [rbp+57h+var_48]
0x1800506b6  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *)
0x1800506bb  nop
0x1800506bc  lea     rcx, [rbp+57h+var_78]
0x1800506c0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800506c5  nop
0x1800506c6  jmp     loc_18005077D
0x1800506cb  xorps   xmm0, xmm0
0x1800506ce  movups  [rbp+57h+var_48], xmm0
0x1800506d2  lea     rcx, [rbp+57h+var_48]
0x1800506d6  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800506db  nop
0x1800506dc  mov     rax, qword ptr [rbp+57h+var_48]
0x1800506e0  test    rax, rax
0x1800506e3  jz      loc_18005077D
0x1800506e9  cmp     [rax+80h], dil
0x1800506f0  jz      loc_18005077D
0x1800506f6  lea     r12, [rsi+48h]
0x1800506fa  cmp     qword ptr [r12+18h], 0Fh
0x180050700  jbe     short loc_180050706
0x180050702  mov     r12, [r12]
0x180050706  movzx   edi, byte ptr [rsi+0D0h]
0x18005070d  xorps   xmm0, xmm0
0x180050710  movups  [rbp+57h+var_78], xmm0
0x180050714  xorps   xmm1, xmm1
0x180050717  movdqu  [rbp+57h+var_68], xmm1
0x18005071c  mov     r8d, 50h ; 'P'
0x180050722  lea     rdx, aRdpvirtualchan_3; "RdpVirtualChannel::OnOpened - unexpecte"...
0x180050729  lea     rcx, [rbp+57h+var_78]
0x18005072d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180050732  nop
0x180050733  lea     rax, aRdpvirtualchan_7; "RdpVirtualChannel::OnOpened"
0x18005073a  mov     [rsp+0C0h+var_88], rax
0x18005073f  mov     dword ptr [rsp+0C0h+var_90], 3Dh ; '='
0x180050747  lea     rax, aCW1SRdpnanodll_5; "C:\\__w\\1\\s\\rdpnanodll\\RdpTransport"...
0x18005074e  mov     [rsp+0C0h+var_98], rax
0x180050753  mov     [rsp+0C0h+var_A0], r12
0x180050758  mov     r9d, edi
0x18005075b  lea     r8, [rbp+57h+var_78]
0x18005075f  lea     rdx, aRdpnano; "RDPNANO"
0x180050766  lea     rcx, [rbp+57h+var_48]
0x18005076a  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@HPEBDPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H11H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,int,char const *,char const *,int,char const *)
0x18005076f  nop
0x180050770  lea     rcx, [rbp+57h+var_78]
0x180050774  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180050779  mov     r12b, [rbp+57h+var_80]
0x18005077d  mov     rdi, qword ptr [rbp+57h+var_48+8]
0x180050781  test    rdi, rdi
0x180050784  jz      short loc_1800507C0
0x180050786  or      eax, 0FFFFFFFFh
0x180050789  lock xadd [rdi+8], eax
0x18005078e  cmp     eax, 1
0x180050791  jnz     short loc_1800507C0
0x180050793  mov     rax, [rdi]
0x180050796  mov     rcx, rdi
0x180050799  mov     rax, [rax]
0x18005079c  call    cs:__guard_dispatch_icall_fptr
0x1800507a2  or      eax, 0FFFFFFFFh
0x1800507a5  lock xadd [rdi+0Ch], eax
0x1800507aa  cmp     eax, 1
0x1800507ad  jnz     short loc_1800507C0
0x1800507af  mov     rax, [rdi]
0x1800507b2  mov     rcx, rdi
0x1800507b5  mov     rax, [rax+8]
0x1800507b9  call    cs:__guard_dispatch_icall_fptr
0x1800507bf  nop
0x1800507c0  mov     rcx, rbx; _Mtx_t
0x1800507c3  call    _Mtx_unlock
0x1800507c8  xor     edi, edi
0x1800507ca  test    r13b, r13b
0x1800507cd  jz      loc_18005094C
0x1800507d3  mov     qword ptr [rbp+57h+var_48], rdi
0x1800507d7  lea     rcx, [rbp+57h+var_48]
0x1800507db  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x1800507e0  mov     r8, rax; void **
0x1800507e3  lea     rdx, _GUID_2243b2a4_3eff_4029_a0ac_45024ff03fe2; struct _GUID *
0x1800507ea  mov     rcx, r14; struct IWeakReference *
0x1800507ed  call    ?query@weak_query_policy@details@wil@@SAJPEAUIWeakReference@@AEBU_GUID@@PEAPEAX@Z; wil::details::weak_query_policy::query(IWeakReference *,_GUID const &,void * *)
0x1800507f2  nop
0x1800507f3  cmp     qword ptr [rbp+57h+var_48], rdi
0x1800507f7  jz      short loc_180050855
0x1800507f9  mov     [rbp+57h+var_38], rdi
0x1800507fd  mov     rcx, rsi
0x180050800  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180050805  mov     rdx, rax
0x180050808  mov     r8b, [rbp+57h+var_80]
0x18005080c  lea     rcx, [rbp+57h+var_38]
0x180050810  call    ??$?0VRdpVirtualChannel@@@?$com_ptr_t@UIVirtualChannel@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVRdpVirtualChannel@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IVirtualChannel,wil::err_exception_policy>::com_ptr_t<IVirtualChannel,wil::err_exception_policy>(RdpVirtualChannel *,wistd::integral_constant<char,0>)
0x180050815  mov     rcx, qword ptr [rbp+57h+var_48]
0x180050819  mov     rax, [rcx]
0x18005081c  lea     rdx, [rsi+48h]
0x180050820  cmp     qword ptr [rdx+18h], 0Fh
0x180050825  jbe     short loc_18005082A
0x180050827  mov     rdx, [rdx]
0x18005082a  mov     r8, [rbp+57h+var_38]
0x18005082e  mov     rax, [rax+18h]
0x180050832  call    cs:__guard_dispatch_icall_fptr
0x180050838  nop
0x180050839  mov     rcx, [rbp+57h+var_38]
0x18005083d  test    rcx, rcx
0x180050840  jz      short loc_180050850
0x180050842  mov     rax, [rcx]
0x180050845  mov     rax, [rax+10h]
0x180050849  call    cs:__guard_dispatch_icall_fptr
0x18005084f  nop
0x180050850  jmp     loc_180050935
0x180050855  xorps   xmm0, xmm0
0x180050858  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18005085c  lea     rcx, [rbp+57h+var_38]
0x180050860  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180050865  nop
0x180050866  mov     rax, [rbp+57h+var_38]
0x18005086a  test    rax, rax
0x18005086d  jz      short loc_1800508EE
0x18005086f  cmp     [rax+80h], dil
0x180050876  jz      short loc_1800508EE
0x180050878  lea     rbx, [rsi+48h]
0x18005087c  cmp     qword ptr [rbx+18h], 0Fh
0x180050881  jbe     short loc_180050886
0x180050883  mov     rbx, [rbx]
0x180050886  xorps   xmm0, xmm0
0x180050889  movups  [rbp+57h+var_78], xmm0
0x18005088d  xorps   xmm1, xmm1
0x180050890  movdqu  [rbp+57h+var_68], xmm1
0x180050895  mov     r8d, 5Eh ; '^'
0x18005089b  lea     rdx, aRdpvirtualchan_1; "RdpVirtualChannel::OnOpened - VCControl"...
0x1800508a2  lea     rcx, [rbp+57h+var_78]
0x1800508a6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800508ab  nop
0x1800508ac  lea     rax, aRdpvirtualchan_7; "RdpVirtualChannel::OnOpened"
0x1800508b3  mov     [rsp+0C0h+var_90], rax
0x1800508b8  mov     dword ptr [rsp+0C0h+var_98], 4Ah ; 'J'
0x1800508c0  lea     rax, aCW1SRdpnanodll_5; "C:\\__w\\1\\s\\rdpnanodll\\RdpTransport"...
0x1800508c7  mov     [rsp+0C0h+var_A0], rax
0x1800508cc  mov     r9, rbx
0x1800508cf  lea     r8, [rbp+57h+var_78]
0x1800508d3  lea     rdx, aRdpnano; "RDPNANO"
0x1800508da  lea     rcx, [rbp+57h+var_38]
0x1800508de  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@11H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,char const *,int,char const *)
0x1800508e3  nop
0x1800508e4  lea     rcx, [rbp+57h+var_78]
0x1800508e8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800508ed  nop
0x1800508ee  mov     rbx, [rbp+57h+var_38+8]
0x1800508f2  test    rbx, rbx
0x1800508f5  jz      short loc_180050935
0x1800508f7  or      r13d, 0FFFFFFFFh
0x1800508fb  mov     eax, r13d
0x1800508fe  lock xadd [rbx+8], eax
0x180050903  add     eax, r13d
0x180050906  jnz     short loc_180050935
0x180050908  mov     rax, [rbx]
0x18005090b  mov     rcx, rbx
0x18005090e  mov     rax, [rax]
0x180050911  call    cs:__guard_dispatch_icall_fptr
0x180050917  mov     eax, r13d
0x18005091a  lock xadd [rbx+0Ch], eax
0x18005091f  add     eax, r13d
0x180050922  jnz     short loc_180050935
0x180050924  mov     rax, [rbx]
0x180050927  mov     rcx, rbx
0x18005092a  mov     rax, [rax+8]
0x18005092e  call    cs:__guard_dispatch_icall_fptr
0x180050934  nop
0x180050935  mov     rcx, qword ptr [rbp+57h+var_48]
0x180050939  test    rcx, rcx
0x18005093c  jz      short loc_18005094C
0x18005093e  mov     rax, [rcx]
0x180050941  mov     rax, [rax+10h]
0x180050945  call    cs:__guard_dispatch_icall_fptr
0x18005094b  nop
0x18005094c  test    r12b, r12b
0x18005094f  jz      loc_180050A7D
0x180050955  mov     [rbp+57h+var_38], rdi
0x180050959  lea     rcx, [rbp+57h+var_38]
0x18005095d  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180050962  mov     r8, rax; void **
0x180050965  lea     rdx, _GUID_6a04ebe4_82bd_4f11_aab5_3f60e5822e36; struct _GUID *
0x18005096c  mov     rcx, r15; struct IWeakReference *
  ... truncated ...
```
