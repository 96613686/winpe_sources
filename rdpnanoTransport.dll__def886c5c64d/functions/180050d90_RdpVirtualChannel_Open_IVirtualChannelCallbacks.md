# RdpVirtualChannel::Open(IVirtualChannelCallbacks *)

- ea: `0x180050d90`
- end: `0x18005104f`
- name: `?Open@RdpVirtualChannel@@UEAAXPEAUIVirtualChannelCallbacks@@@Z`
- size: `703`
- prototype: `void __fastcall(RdpVirtualChannel *__hidden this, struct IVirtualChannelCallbacks *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001b6b8`
- `0x180045a60`
- `0x18004c814`
- `0x18004f4a4`
- `0x180050d90`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x180050e90`: `RdpVirtualChannel::Open - Created -> CallbacksSet, waiting for DCT, channel='%s'`
- `0x180050f0c`: `RdpVirtualChannel::Open - DctOpened -> Opened, delivering callback, channel='%s'`
- `0x180050f6a`: `RdpVirtualChannel::Open`
- `0x180050f7e`: `C:\__w\1\s\rdpnanodll\RdpTransportStackAbi.h`
- `0x180050f5a`: `RdpVirtualChannel::Open - unexpected state %d, channel='%s'\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RdpVirtualChannel::Open(RdpVirtualChannel *this, struct IVirtualChannelCallbacks *a2)
{
  char v4; // r12
  char *v5; // r14
  __int64 *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  char v9; // al
  _QWORD *v10; // rbx
  const char *v11; // rdx
  const char *v12; // r9
  _QWORD *v13; // rdi
  int v14; // ebx
  volatile signed __int32 *v15; // rdi
  const char *v16; // [rsp+20h] [rbp-60h]
  int v17; // [rsp+28h] [rbp-58h]
  const char *v18; // [rsp+30h] [rbp-50h]
  __int128 v19; // [rsp+40h] [rbp-40h] BYREF
  __int128 v20; // [rsp+50h] [rbp-30h]
  struct IVirtualChannelCallbacks *v21; // [rsp+60h] [rbp-20h] BYREF
  __int128 v22; // [rsp+68h] [rbp-18h] BYREF

  if ( !a2 )
    return;
  v21 = a2;
  v4 = 0;
  v5 = (char *)this + 128;
  if ( Mtx_lock((RdpVirtualChannel *)((char *)this + 128)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v5 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v5 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v6 = (__int64 *)wil::com_weak_query<IVirtualChannelCallbacks * &>(&v22, &v21);
  v7 = *v6;
  *v6 = 0;
  v8 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v7;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( (_QWORD)v22 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 16LL))(v22);
  v9 = *((_BYTE *)this + 208);
  v22 = 0;
  if ( v9 == 1 )
  {
    *((_BYTE *)this + 208) = 3;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v22);
    if ( !(_QWORD)v22 || !*(_BYTE *)(v22 + 128) )
      goto LABEL_27;
    v10 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 0xFu )
      v10 = (_QWORD *)*v10;
    v11 = "RdpVirtualChannel::Open - Created -> CallbacksSet, waiting for DCT, channel='%s'";
  }
  else
  {
    if ( v9 != 2 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v22);
      if ( !(_QWORD)v22 || !*(_BYTE *)(v22 + 128) )
        goto LABEL_27;
      v13 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) > 0xFu )
        v13 = (_QWORD *)*v13;
      v14 = *((unsigned __int8 *)this + 208);
      v19 = 0;
      v20 = 0;
      std::string::_Construct<1,char const *>(
        &v19,
        "RdpVirtualChannel::Open - unexpected state %d, channel='%s'\n    %s(%d): %s()",
        76,
        v12,
        v16,
        v17,
        v18);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,char const *,int,char const *>(
        (unsigned int)&v22,
        (unsigned int)"TRANSSTACK",
        (unsigned int)&v19,
        v14,
        (__int64)v13,
        (__int64)"C:\\__w\\1\\s\\rdpnanodll\\RdpTransportStackAbi.h",
        108,
        (__int64)"RdpVirtualChannel::Open");
      goto LABEL_26;
    }
    *((_BYTE *)this + 208) = 4;
    v4 = 1;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v22);
    if ( !(_QWORD)v22 || !*(_BYTE *)(v22 + 128) )
      goto LABEL_27;
    v10 = (_QWORD *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 0xFu )
      v10 = (_QWORD *)*v10;
    v11 = "RdpVirtualChannel::Open - DctOpened -> Opened, delivering callback, channel='%s'";
  }
  v20 = 0;
  v19 = 0;
  std::string::_Construct<1,char const *>(&v19, v11, 80);
  Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(
    &v22,
    "TRANSSTACK",
    &v19,
    v10);
LABEL_26:
  std::string::_Tidy_deallocate(&v19);
LABEL_27:
  v15 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  if ( *((_QWORD *)&v22 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  Mtx_unlock((_Mtx_t)v5);
  if ( v4 )
    RdpVirtualChannel::FireOnOpenedCbAsync(this, a2);
}

```

## disassembly

```asm
0x180050d90  test    rdx, rdx
0x180050d93  jz      locret_180051030
0x180050d99  mov     [rsp-28h+arg_10], rbx
0x180050d9e  mov     [rsp-28h+arg_18], rsi
0x180050da3  push    rbp
0x180050da4  push    rdi
0x180050da5  push    r12
0x180050da7  push    r14
0x180050da9  push    r15
0x180050dab  mov     rbp, rsp
0x180050dae  mov     eax, 80h
0x180050db3  call    _alloca_probe
0x180050db8  sub     rsp, rax
0x180050dbb  mov     rax, cs:__security_cookie
0x180050dc2  xor     rax, rsp
0x180050dc5  mov     [rbp+var_8], rax
0x180050dc9  mov     r15, rdx
0x180050dcc  mov     rsi, rcx
0x180050dcf  mov     [rbp+var_20], rdx
0x180050dd3  xor     r12b, r12b
0x180050dd6  lea     r14, [rcx+80h]
0x180050ddd  mov     rcx, r14; _Mtx_t
0x180050de0  call    _Mtx_lock
0x180050de5  test    eax, eax
0x180050de7  jnz     loc_180051044
0x180050ded  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x180050df5  jz      loc_180051031
0x180050dfb  lea     rdx, [rbp+var_20]
0x180050dff  lea     rcx, [rbp+var_18]
0x180050e03  call    ??$com_weak_query@AEAPEAUIVirtualChannelCallbacks@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIVirtualChannelCallbacks@@@Z; wil::com_weak_query<IVirtualChannelCallbacks * &>(IVirtualChannelCallbacks * &)
0x180050e08  mov     rcx, [rax]
0x180050e0b  mov     qword ptr [rax], 0
0x180050e12  mov     rdx, [rsi+40h]
0x180050e16  mov     [rsi+40h], rcx
0x180050e1a  test    rdx, rdx
0x180050e1d  jz      short loc_180050E30
0x180050e1f  mov     rax, [rdx]
0x180050e22  mov     rcx, rdx
0x180050e25  mov     rax, [rax+10h]
0x180050e29  call    cs:__guard_dispatch_icall_fptr
0x180050e2f  nop
0x180050e30  mov     rcx, qword ptr [rbp+var_18]
0x180050e34  test    rcx, rcx
0x180050e37  jz      short loc_180050E47
0x180050e39  mov     rax, [rcx]
0x180050e3c  mov     rax, [rax+10h]
0x180050e40  call    cs:__guard_dispatch_icall_fptr
0x180050e46  nop
0x180050e47  mov     al, [rsi+0D0h]
0x180050e4d  xorps   xmm0, xmm0
0x180050e50  lea     rcx, [rbp+var_18]
0x180050e54  movups  [rbp+var_18], xmm0
0x180050e58  cmp     al, 1
0x180050e5a  jnz     short loc_180050ED1
0x180050e5c  mov     byte ptr [rsi+0D0h], 3
0x180050e63  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180050e68  mov     rax, qword ptr [rbp+var_18]
0x180050e6c  test    rax, rax
0x180050e6f  jz      loc_180050FAF
0x180050e75  cmp     byte ptr [rax+80h], 0
0x180050e7c  jz      loc_180050FAF
0x180050e82  lea     rbx, [rsi+48h]
0x180050e86  cmp     qword ptr [rbx+18h], 0Fh
0x180050e8b  jbe     short loc_180050E90
0x180050e8d  mov     rbx, [rbx]
0x180050e90  lea     rdx, aRdpvirtualchan_2; "RdpVirtualChannel::Open - Created -> Ca"...
0x180050e97  xorps   xmm1, xmm1
0x180050e9a  xorps   xmm0, xmm0
0x180050e9d  mov     r8d, 50h ; 'P'
0x180050ea3  movdqu  [rbp+var_30], xmm1
0x180050ea8  movups  [rbp+var_40], xmm0
0x180050eac  lea     rcx, [rbp+var_40]
0x180050eb0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180050eb5  mov     r9, rbx
0x180050eb8  lea     r8, [rbp+var_40]
0x180050ebc  lea     rdx, aTransstack; "TRANSSTACK"
0x180050ec3  lea     rcx, [rbp+var_18]
0x180050ec7  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *)
0x180050ecc  jmp     loc_180050FA6
0x180050ed1  cmp     al, 2
0x180050ed3  jnz     short loc_180050F15
0x180050ed5  mov     byte ptr [rsi+0D0h], 4
0x180050edc  mov     r12b, 1
0x180050edf  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180050ee4  mov     rax, qword ptr [rbp+var_18]
0x180050ee8  test    rax, rax
0x180050eeb  jz      loc_180050FAF
0x180050ef1  cmp     byte ptr [rax+80h], 0
0x180050ef8  jz      loc_180050FAF
0x180050efe  lea     rbx, [rsi+48h]
0x180050f02  cmp     qword ptr [rbx+18h], 0Fh
0x180050f07  jbe     short loc_180050F0C
0x180050f09  mov     rbx, [rbx]
0x180050f0c  lea     rdx, aRdpvirtualchan_4; "RdpVirtualChannel::Open - DctOpened -> "...
0x180050f13  jmp     short loc_180050E97
0x180050f15  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180050f1a  mov     rax, qword ptr [rbp+var_18]
0x180050f1e  test    rax, rax
0x180050f21  jz      loc_180050FAF
0x180050f27  cmp     byte ptr [rax+80h], 0
0x180050f2e  jz      short loc_180050FAF
0x180050f30  lea     rdi, [rsi+48h]
0x180050f34  cmp     qword ptr [rdi+18h], 0Fh
0x180050f39  jbe     short loc_180050F3E
0x180050f3b  mov     rdi, [rdi]
0x180050f3e  movzx   ebx, byte ptr [rsi+0D0h]
0x180050f45  xorps   xmm0, xmm0
0x180050f48  movups  [rbp+var_40], xmm0
0x180050f4c  xorps   xmm1, xmm1
0x180050f4f  movdqu  [rbp+var_30], xmm1
0x180050f54  mov     r8d, 4Ch ; 'L'
0x180050f5a  lea     rdx, aRdpvirtualchan; "RdpVirtualChannel::Open - unexpected st"...
0x180050f61  lea     rcx, [rbp+var_40]
0x180050f65  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180050f6a  lea     rax, aRdpvirtualchan_5; "RdpVirtualChannel::Open"
0x180050f71  mov     [rsp+80h+var_48], rax
0x180050f76  mov     dword ptr [rsp+80h+var_50], 6Ch ; 'l'
0x180050f7e  lea     rax, aCW1SRdpnanodll_9; "C:\\__w\\1\\s\\rdpnanodll\\RdpTransport"...
0x180050f85  mov     [rsp+80h+var_58], rax
0x180050f8a  mov     [rsp+80h+var_60], rdi
0x180050f8f  mov     r9d, ebx
0x180050f92  lea     r8, [rbp+var_40]
0x180050f96  lea     rdx, aTransstack; "TRANSSTACK"
0x180050f9d  lea     rcx, [rbp+var_18]
0x180050fa1  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@HPEBDPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H11H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,int,char const *,char const *,int,char const *)
0x180050fa6  lea     rcx, [rbp+var_40]
0x180050faa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180050faf  mov     rdi, qword ptr [rbp+var_18+8]
0x180050fb3  test    rdi, rdi
0x180050fb6  jz      short loc_180050FF0
0x180050fb8  or      ebx, 0FFFFFFFFh
0x180050fbb  mov     eax, ebx
0x180050fbd  lock xadd [rdi+8], eax
0x180050fc2  add     eax, ebx
0x180050fc4  jnz     short loc_180050FF0
0x180050fc6  mov     rax, [rdi]
0x180050fc9  mov     rcx, rdi
0x180050fcc  mov     rax, [rax]
0x180050fcf  call    cs:__guard_dispatch_icall_fptr
0x180050fd5  mov     eax, ebx
0x180050fd7  lock xadd [rdi+0Ch], eax
0x180050fdc  add     eax, ebx
0x180050fde  jnz     short loc_180050FF0
0x180050fe0  mov     rax, [rdi]
0x180050fe3  mov     rcx, rdi
0x180050fe6  mov     rax, [rax+8]
0x180050fea  call    cs:__guard_dispatch_icall_fptr
0x180050ff0  mov     rcx, r14; _Mtx_t
0x180050ff3  call    _Mtx_unlock
0x180050ff8  test    r12b, r12b
0x180050ffb  jz      short loc_180051009
0x180050ffd  mov     rdx, r15; struct IVirtualChannelCallbacks *
0x180051000  mov     rcx, rsi; this
0x180051003  call    ?FireOnOpenedCbAsync@RdpVirtualChannel@@IEAAXPEAUIVirtualChannelCallbacks@@@Z; RdpVirtualChannel::FireOnOpenedCbAsync(IVirtualChannelCallbacks *)
0x180051008  nop
0x180051009  mov     rcx, [rbp+var_8]
0x18005100d  xor     rcx, rsp; StackCookie
0x180051010  call    __security_check_cookie
0x180051015  lea     r11, [rsp+80h+var_s0]
0x18005101d  mov     rbx, [r11+40h]
0x180051021  mov     rsi, [r11+48h]
0x180051025  mov     rsp, r11
0x180051028  pop     r15
0x18005102a  pop     r14
0x18005102c  pop     r12
0x18005102e  pop     rdi
0x18005102f  pop     rbp
0x180051030  retn
0x180051031  mov     dword ptr [r14+4Ch], 7FFFFFFEh
0x180051039  mov     ecx, 6; int
0x18005103e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180051044  mov     ecx, 5; int
0x180051049  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
