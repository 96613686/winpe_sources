# Microsoft::RdpNano::RdpSideTransport::OnSignalingChannelDataReceived(ushort,std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x1800e6990`
- end: `0x1800e6ea8`
- name: `?OnSignalingChannelDataReceived@RdpSideTransport@RdpNano@Microsoft@@UEAAJGV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z`
- size: `1304`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001bbdc`
- `0x180028820`
- `0x18004569c`
- `0x18004d03c`
- `0x1800c3a18`
- `0x1800c4238`
- `0x1800e6990`
- `0x1800fdb80`
- `0x1802f13d4`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800e6a91`: `C:\__w\1\s\rdnanolib\rdnano\RdpSideTransport.cpp`
- `0x1800e6a7d`: `Microsoft::RdpNano::RdpSideTransport::OnSignalingChannelDataReceived`
- `0x1800e6a6b`: `RdpSideTransport::OnSignalingChannelDataReceived: Invalid dataTree.\n    %s(%d): %s()`
- `0x1800e6b4a`: `RdpSideTransport::OnSignalingChannelDataReceived: type=%d`
- `0x1800e6cc3`: `OnSignalingChannelDataReceived: iceSourcePtr == nullptr. cache it for now`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::RdpNano::RdpSideTransport::OnSignalingChannelDataReceived(
        __int64 a1,
        unsigned __int16 a2,
        const char **a3)
{
  int v6; // r9d
  volatile signed __int32 *v7; // rdi
  __int64 result; // rax
  volatile signed __int32 *v9; // rdi
  void (__fastcall ***v10)(_QWORD, _QWORD, __int128 *); // rcx
  __int64 v11; // rax
  __int64 v12; // rsi
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rdi
  const char *v15; // [rsp+20h] [rbp-C8h]
  __int128 v16; // [rsp+30h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+40h] [rbp-A8h]
  __int128 v18; // [rsp+50h] [rbp-98h] BYREF
  __int128 v19; // [rsp+60h] [rbp-88h]
  __int128 v20; // [rsp+70h] [rbp-78h] BYREF
  _OWORD v21[2]; // [rsp+80h] [rbp-68h] BYREF
  __int128 v22; // [rsp+A0h] [rbp-48h] BYREF

  v22 = 0;
  v16 = 0;
  v17 = 0;
  try
  {
    std::string::_Construct<1,char const *>(&v16, *a3);
    Microsoft::Basix::Containers::AnyPTreeFromJson(&v22, &v16);
    std::string::_Tidy_deallocate(&v16);
    v20 = 0;
    if ( *(_QWORD *)((*((_QWORD *)&v22 + 1) & -(__int64)(*((_QWORD *)&v22 + 1) != -17)) + 0x18) )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v20);
      if ( (_QWORD)v20 && *(_BYTE *)(v20 + 128) )
      {
        memset(v21, 0, sizeof(v21));
        std::string::_Construct<1,char const *>(v21, "RdpSideTransport::OnSignalingChannelDataReceived: type=%d", 57);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned short>(
          &v20,
          "RDPNANO",
          v21,
          a2);
        std::string::_Tidy_deallocate(v21);
      }
      v9 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
      if ( *((_QWORD *)&v20 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      if ( (unsigned __int8)a2 >> 4 == 15 )
      {
        v10 = *(void (__fastcall ****)(_QWORD, _QWORD, __int128 *))(a1 + 160);
        if ( v10 )
          (**v10)(v10, a2, &v22);
      }
      else
      {
        if ( (unsigned __int8)a2 >> 4 )
        {
          v21[0] = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v21);
          if ( *(_QWORD *)&v21[0] && *(_BYTE *)(*(_QWORD *)&v21[0] + 128LL) )
          {
            v18 = 0;
            v19 = 0;
            std::string::_Construct<1,char const *>(
              &v18,
              "OnSignalingChannelDataReceived from unknown source: type=%d",
              59);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short>(
              v21,
              "RDPNANO",
              &v18,
              a2);
            std::string::_Tidy_deallocate(&v18);
          }
          v13 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
        }
        else
        {
          v20 = 0;
          v16 = (unsigned __int64)(a1 + 256);
          if ( Mtx_lock((_Mtx_t)(a1 + 256)) )
            std::_Throw_Cpp_error(5);
          if ( *(_DWORD *)(a1 + 332) == 0x7FFFFFFF )
          {
            *(_DWORD *)(a1 + 332) = 2147483646;
            std::_Throw_Cpp_error(6);
          }
          BYTE8(v16) = 1;
          if ( *(_QWORD *)(a1 + 112) )
          {
            v11 = *(_QWORD *)(a1 + 120);
            if ( v11 )
              _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
            v12 = *(_QWORD *)(a1 + 112);
            *(_QWORD *)&v20 = v12;
            v13 = *(volatile signed __int32 **)(a1 + 120);
            *((_QWORD *)&v20 + 1) = v13;
          }
          else
          {
            v21[0] = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v21);
            if ( *(_QWORD *)&v21[0] && *(_BYTE *)(*(_QWORD *)&v21[0] + 128LL) )
            {
              v18 = 0;
              v19 = 0;
              std::string::_Construct<1,char const *>(
                &v18,
                "OnSignalingChannelDataReceived: iceSourcePtr == nullptr. cache it for now",
                73);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
                v21,
                "RDPNANO",
                &v18);
              std::string::_Tidy_deallocate(&v18);
            }
            v14 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
            if ( *((_QWORD *)&v21[0] + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
                if ( !_InterlockedDecrement(v14 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
              }
            }
            std::string::assign<std::string_view,0>(a1 + 224, a3);
            *(_WORD *)(a1 + 216) = a2;
            v13 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
            v12 = v20;
          }
          Mtx_unlock((_Mtx_t)(a1 + 256));
          if ( v12 )
            Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(v12, a2, (__int64)&v22);
        }
        if ( v13 )
        {
          if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
      }
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v22);
      result = 0;
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v20);
      if ( (_QWORD)v20 && *(_BYTE *)(v20 + 128) )
      {
        v16 = 0;
        v17 = 0;
        std::string::_Construct<1,char const *>(
          &v16,
          "RdpSideTransport::OnSignalingChannelDataReceived: Invalid dataTree.\n    %s(%d): %s()",
          (const char *)0x54,
          v6,
          v15);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v20,
          (unsigned int)"RDPNANO",
          (unsigned int)&v16,
          (unsigned int)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSideTransport.cpp",
          167,
          (__int64)"Microsoft::RdpNano::RdpSideTransport::OnSignalingChannelDataReceived");
        std::string::_Tidy_deallocate(&v16);
      }
      v7 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
      if ( *((_QWORD *)&v20 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v22);
      result = 2147942487LL;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return 2147942974LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800e6990  mov     [rsp+arg_18], rbx
0x1800e6995  push    rsi
0x1800e6996  push    rdi
0x1800e6997  push    r13
0x1800e6999  push    r14
0x1800e699b  push    r15
0x1800e699d  mov     eax, 0C0h
0x1800e69a2  call    _alloca_probe
0x1800e69a7  sub     rsp, rax
0x1800e69aa  mov     rax, cs:__security_cookie
0x1800e69b1  xor     rax, rsp
0x1800e69b4  mov     [rsp+0E8h+var_38], rax
0x1800e69bc  mov     rsi, r8
0x1800e69bf  movzx   r15d, dx
0x1800e69c3  mov     r14, rcx
0x1800e69c6  xorps   xmm0, xmm0
0x1800e69c9  movups  [rsp+0E8h+var_48], xmm0
0x1800e69d1  xorps   xmm1, xmm1
0x1800e69d4  movups  [rsp+0E8h+var_B8], xmm1
0x1800e69d9  movdqu  [rsp+0E8h+var_A8], xmm0
0x1800e69df  mov     r8, [r8+8]
0x1800e69e3  mov     rdx, [rsi]
0x1800e69e6  lea     rcx, [rsp+0E8h+var_B8]
0x1800e69eb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e69f0  nop
0x1800e69f1  lea     rdx, [rsp+0E8h+var_B8]
0x1800e69f6  lea     rcx, [rsp+0E8h+var_48]
0x1800e69fe  call    ?AnyPTreeFromJson@Containers@Basix@Microsoft@@YA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Containers::AnyPTreeFromJson(std::string const &)
0x1800e6a03  nop
0x1800e6a04  lea     rcx, [rsp+0E8h+var_B8]
0x1800e6a09  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6a0e  mov     rdx, qword ptr [rsp+0E8h+var_48+8]
0x1800e6a16  lea     rax, [rdx+11h]
0x1800e6a1a  neg     rax
0x1800e6a1d  sbb     rcx, rcx
0x1800e6a20  and     rcx, rdx
0x1800e6a23  xorps   xmm0, xmm0
0x1800e6a26  movups  [rsp+0E8h+var_78], xmm0
0x1800e6a2b  cmp     qword ptr [rcx+18h], 0
0x1800e6a30  lea     rcx, [rsp+0E8h+var_78]
0x1800e6a35  jnz     loc_1800E6B14
0x1800e6a3b  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800e6a40  nop
0x1800e6a41  mov     rax, qword ptr [rsp+0E8h+var_78]
0x1800e6a46  test    rax, rax
0x1800e6a49  jz      short loc_1800E6ABA
0x1800e6a4b  cmp     byte ptr [rax+80h], 0
0x1800e6a52  jz      short loc_1800E6ABA
0x1800e6a54  xorps   xmm0, xmm0
0x1800e6a57  movups  [rsp+0E8h+var_B8], xmm0
0x1800e6a5c  xorps   xmm1, xmm1
0x1800e6a5f  movdqu  [rsp+0E8h+var_A8], xmm1
0x1800e6a65  mov     r8d, 54h ; 'T'
0x1800e6a6b  lea     rdx, aRdpsidetranspo_21; "RdpSideTransport::OnSignalingChannelDat"...
0x1800e6a72  lea     rcx, [rsp+0E8h+var_B8]
0x1800e6a77  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e6a7c  nop
0x1800e6a7d  lea     rax, aMicrosoftRdpna_20; "Microsoft::RdpNano::RdpSideTransport::O"...
0x1800e6a84  mov     [rsp+0E8h+var_C0], rax
0x1800e6a89  mov     dword ptr [rsp+0E8h+var_C8], 4A7h
0x1800e6a91  lea     r9, aCW1SRdnanolibR; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSi"...
0x1800e6a98  lea     r8, [rsp+0E8h+var_B8]
0x1800e6a9d  lea     rdx, aRdpnano; "RDPNANO"
0x1800e6aa4  lea     rcx, [rsp+0E8h+var_78]
0x1800e6aa9  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1800e6aae  nop
0x1800e6aaf  lea     rcx, [rsp+0E8h+var_B8]
0x1800e6ab4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6ab9  nop
0x1800e6aba  mov     rdi, qword ptr [rsp+0E8h+var_78+8]
0x1800e6abf  test    rdi, rdi
0x1800e6ac2  jz      short loc_1800E6AFD
0x1800e6ac4  or      ebx, 0FFFFFFFFh
0x1800e6ac7  mov     eax, ebx
0x1800e6ac9  lock xadd [rdi+8], eax
0x1800e6ace  add     eax, ebx
0x1800e6ad0  jnz     short loc_1800E6AFD
0x1800e6ad2  mov     rax, [rdi]
0x1800e6ad5  mov     rcx, rdi
0x1800e6ad8  mov     rax, [rax]
0x1800e6adb  call    cs:__guard_dispatch_icall_fptr
0x1800e6ae1  mov     eax, ebx
0x1800e6ae3  lock xadd [rdi+0Ch], eax
0x1800e6ae8  add     eax, ebx
0x1800e6aea  jnz     short loc_1800E6AFD
0x1800e6aec  mov     rax, [rdi]
0x1800e6aef  mov     rcx, rdi
0x1800e6af2  mov     rax, [rax+8]
0x1800e6af6  call    cs:__guard_dispatch_icall_fptr
0x1800e6afc  nop
0x1800e6afd  lea     rcx, [rsp+0E8h+var_48]
0x1800e6b05  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800e6b0a  mov     eax, 80070057h
0x1800e6b0f  jmp     loc_1800E6E62
0x1800e6b14  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e6b19  nop
0x1800e6b1a  mov     rax, qword ptr [rsp+0E8h+var_78]
0x1800e6b1f  test    rax, rax
0x1800e6b22  jz      short loc_1800E6B8B
0x1800e6b24  cmp     byte ptr [rax+80h], 0
0x1800e6b2b  jz      short loc_1800E6B8B
0x1800e6b2d  xorps   xmm0, xmm0
0x1800e6b30  movups  [rsp+0E8h+var_68], xmm0
0x1800e6b38  xorps   xmm1, xmm1
0x1800e6b3b  movdqu  [rsp+0E8h+var_58], xmm1
0x1800e6b44  mov     r8d, 39h ; '9'
0x1800e6b4a  lea     rdx, aRdpsidetranspo_18; "RdpSideTransport::OnSignalingChannelDat"...
0x1800e6b51  lea     rcx, [rsp+0E8h+var_68]
0x1800e6b59  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e6b5e  nop
0x1800e6b5f  movzx   r9d, r15w
0x1800e6b63  lea     r8, [rsp+0E8h+var_68]
0x1800e6b6b  lea     rdx, aRdpnano; "RDPNANO"
0x1800e6b72  lea     rcx, [rsp+0E8h+var_78]
0x1800e6b77  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@G@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,ushort>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,ushort)
0x1800e6b7c  nop
0x1800e6b7d  lea     rcx, [rsp+0E8h+var_68]
0x1800e6b85  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6b8a  nop
0x1800e6b8b  mov     rdi, qword ptr [rsp+0E8h+var_78+8]
0x1800e6b90  or      ebx, 0FFFFFFFFh
0x1800e6b93  test    rdi, rdi
0x1800e6b96  jz      short loc_1800E6BCD
0x1800e6b98  mov     eax, ebx
0x1800e6b9a  lock xadd [rdi+8], eax
0x1800e6b9f  add     eax, ebx
0x1800e6ba1  jnz     short loc_1800E6BCD
0x1800e6ba3  mov     rax, [rdi]
0x1800e6ba6  mov     rcx, rdi
0x1800e6ba9  mov     rax, [rax]
0x1800e6bac  call    cs:__guard_dispatch_icall_fptr
0x1800e6bb2  mov     eax, ebx
0x1800e6bb4  lock xadd [rdi+0Ch], eax
0x1800e6bb9  add     eax, ebx
0x1800e6bbb  jnz     short loc_1800E6BCD
0x1800e6bbd  mov     rax, [rdi]
0x1800e6bc0  mov     rcx, rdi
0x1800e6bc3  mov     rax, [rax+8]
0x1800e6bc7  call    cs:__guard_dispatch_icall_fptr
0x1800e6bcd  mov     al, r15b
0x1800e6bd0  shr     al, 4
0x1800e6bd3  and     al, 0Fh
0x1800e6bd5  cmp     al, 0Fh
0x1800e6bd7  jnz     short loc_1800E6C06
0x1800e6bd9  mov     rcx, [r14+0A0h]
0x1800e6be0  test    rcx, rcx
0x1800e6be3  jz      loc_1800E6E45
0x1800e6be9  mov     rax, [rcx]
0x1800e6bec  lea     r8, [rsp+0E8h+var_48]
0x1800e6bf4  movzx   edx, r15w
0x1800e6bf8  mov     rax, [rax]
0x1800e6bfb  call    cs:__guard_dispatch_icall_fptr
0x1800e6c01  jmp     loc_1800E6E45
0x1800e6c06  xorps   xmm0, xmm0
0x1800e6c09  test    al, al
0x1800e6c0b  jnz     loc_1800E6D84
0x1800e6c11  xorps   xmm1, xmm1
0x1800e6c14  movdqu  [rsp+0E8h+var_78], xmm1
0x1800e6c1a  movups  [rsp+0E8h+var_B8], xmm0
0x1800e6c1f  lea     r13, [r14+100h]
0x1800e6c26  mov     qword ptr [rsp+0E8h+var_B8], r13
0x1800e6c2b  mov     byte ptr [rsp+0E8h+var_B8+8], al
0x1800e6c2f  mov     rcx, r13; _Mtx_t
0x1800e6c32  call    _Mtx_lock
0x1800e6c37  test    eax, eax
0x1800e6c39  jnz     loc_1800E6E8A
0x1800e6c3f  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x1800e6c47  jz      loc_1800E6E94
0x1800e6c4d  mov     byte ptr [rsp+0E8h+var_B8+8], 1
0x1800e6c52  cmp     qword ptr [r14+70h], 0
0x1800e6c57  jz      short loc_1800E6C7D
0x1800e6c59  mov     rax, [r14+78h]
0x1800e6c5d  test    rax, rax
0x1800e6c60  jz      short loc_1800E6C66
0x1800e6c62  lock inc dword ptr [rax+8]
0x1800e6c66  mov     rsi, [r14+70h]
0x1800e6c6a  mov     qword ptr [rsp+0E8h+var_78], rsi
0x1800e6c6f  mov     rdi, [r14+78h]
0x1800e6c73  mov     qword ptr [rsp+0E8h+var_78+8], rdi
0x1800e6c78  jmp     loc_1800E6D5D
0x1800e6c7d  xorps   xmm0, xmm0
0x1800e6c80  movups  [rsp+0E8h+var_68], xmm0
0x1800e6c88  lea     rcx, [rsp+0E8h+var_68]
0x1800e6c90  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800e6c95  nop
0x1800e6c96  mov     rax, qword ptr [rsp+0E8h+var_68]
0x1800e6c9e  test    rax, rax
0x1800e6ca1  jz      short loc_1800E6CFA
0x1800e6ca3  cmp     byte ptr [rax+80h], 0
0x1800e6caa  jz      short loc_1800E6CFA
0x1800e6cac  xorps   xmm0, xmm0
0x1800e6caf  movups  [rsp+0E8h+var_98], xmm0
0x1800e6cb4  xorps   xmm1, xmm1
0x1800e6cb7  movdqu  [rsp+0E8h+var_88], xmm1
0x1800e6cbd  mov     r8d, 49h ; 'I'
0x1800e6cc3  lea     rdx, aOnsignalingcha; "OnSignalingChannelDataReceived: iceSour"...
0x1800e6cca  lea     rcx, [rsp+0E8h+var_98]
0x1800e6ccf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e6cd4  nop
0x1800e6cd5  lea     r8, [rsp+0E8h+var_98]
0x1800e6cda  lea     rdx, aRdpnano; "RDPNANO"
0x1800e6ce1  lea     rcx, [rsp+0E8h+var_68]
0x1800e6ce9  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x1800e6cee  nop
0x1800e6cef  lea     rcx, [rsp+0E8h+var_98]
0x1800e6cf4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6cf9  nop
0x1800e6cfa  mov     rdi, qword ptr [rsp+0E8h+var_68+8]
0x1800e6d02  test    rdi, rdi
0x1800e6d05  jz      short loc_1800E6D3C
0x1800e6d07  mov     eax, ebx
0x1800e6d09  lock xadd [rdi+8], eax
0x1800e6d0e  add     eax, ebx
0x1800e6d10  jnz     short loc_1800E6D3C
0x1800e6d12  mov     rax, [rdi]
0x1800e6d15  mov     rcx, rdi
0x1800e6d18  mov     rax, [rax]
0x1800e6d1b  call    cs:__guard_dispatch_icall_fptr
0x1800e6d21  mov     eax, ebx
0x1800e6d23  lock xadd [rdi+0Ch], eax
0x1800e6d28  add     eax, ebx
0x1800e6d2a  jnz     short loc_1800E6D3C
0x1800e6d2c  mov     rax, [rdi]
0x1800e6d2f  mov     rcx, rdi
0x1800e6d32  mov     rax, [rax+8]
0x1800e6d36  call    cs:__guard_dispatch_icall_fptr
0x1800e6d3c  lea     rcx, [r14+0E0h]
0x1800e6d43  mov     rdx, rsi
0x1800e6d46  call    ??$assign@V?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::assign<std::string_view,0>(std::string_view const &)
0x1800e6d4b  mov     [r14+0D8h], r15w
0x1800e6d53  mov     rdi, qword ptr [rsp+0E8h+var_78+8]
0x1800e6d58  mov     rsi, qword ptr [rsp+0E8h+var_78]
0x1800e6d5d  mov     rcx, r13; _Mtx_t
0x1800e6d60  call    _Mtx_unlock
0x1800e6d65  test    rsi, rsi
0x1800e6d68  jz      short loc_1800E6D7F
0x1800e6d6a  lea     r8, [rsp+0E8h+var_48]
0x1800e6d72  movzx   edx, r15w
0x1800e6d76  mov     rcx, rsi
0x1800e6d79  call    ?OnReceiveSideBandData@ICESourceAdapter@RdpNano@Microsoft@@QEAAXGAEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z; Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(ushort,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &)
0x1800e6d7e  nop
0x1800e6d7f  jmp     loc_1800E6E0A
0x1800e6d84  movups  [rsp+0E8h+var_68], xmm0
0x1800e6d8c  lea     rcx, [rsp+0E8h+var_68]
0x1800e6d94  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800e6d99  nop
0x1800e6d9a  mov     rax, qword ptr [rsp+0E8h+var_68]
0x1800e6da2  test    rax, rax
0x1800e6da5  jz      short loc_1800E6E02
0x1800e6da7  cmp     byte ptr [rax+80h], 0
0x1800e6dae  jz      short loc_1800E6E02
0x1800e6db0  xorps   xmm0, xmm0
0x1800e6db3  movups  [rsp+0E8h+var_98], xmm0
0x1800e6db8  xorps   xmm1, xmm1
0x1800e6dbb  movdqu  [rsp+0E8h+var_88], xmm1
0x1800e6dc1  mov     r8d, 3Bh ; ';'
0x1800e6dc7  lea     rdx, aOnsignalingcha_0; "OnSignalingChannelDataReceived from unk"...
0x1800e6dce  lea     rcx, [rsp+0E8h+var_98]
0x1800e6dd3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e6dd8  nop
0x1800e6dd9  movzx   r9d, r15w
0x1800e6ddd  lea     r8, [rsp+0E8h+var_98]
0x1800e6de2  lea     rdx, aRdpnano; "RDPNANO"
0x1800e6de9  lea     rcx, [rsp+0E8h+var_68]
0x1800e6df1  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@G@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,ushort>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,ushort)
0x1800e6df6  nop
0x1800e6df7  lea     rcx, [rsp+0E8h+var_98]
0x1800e6dfc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6e01  nop
0x1800e6e02  mov     rdi, qword ptr [rsp+0E8h+var_68+8]
0x1800e6e0a  test    rdi, rdi
0x1800e6e0d  jz      short loc_1800E6E45
0x1800e6e0f  mov     eax, ebx
0x1800e6e11  lock xadd [rdi+8], eax
0x1800e6e16  add     eax, ebx
0x1800e6e18  jnz     short loc_1800E6E45
0x1800e6e1a  mov     rax, [rdi]
0x1800e6e1d  mov     rcx, rdi
0x1800e6e20  mov     rax, [rax]
0x1800e6e23  call    cs:__guard_dispatch_icall_fptr
0x1800e6e29  mov     eax, ebx
0x1800e6e2b  lock xadd [rdi+0Ch], eax
0x1800e6e30  add     eax, ebx
0x1800e6e32  jnz     short loc_1800E6E45
0x1800e6e34  mov     rax, [rdi]
0x1800e6e37  mov     rcx, rdi
0x1800e6e3a  mov     rax, [rax+8]
0x1800e6e3e  call    cs:__guard_dispatch_icall_fptr
0x1800e6e44  nop
0x1800e6e45  lea     rcx, [rsp+0E8h+var_48]
0x1800e6e4d  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800e6e52  xor     eax, eax
0x1800e6e54  jmp     short loc_1800E6E62
0x1800e6e56  mov     eax, 8007000Eh
0x1800e6e5b  jmp     short loc_1800E6E62
0x1800e6e5d  mov     eax, 8007023Eh
0x1800e6e62  mov     rcx, [rsp+0E8h+var_38]
0x1800e6e6a  xor     rcx, rsp; StackCookie
0x1800e6e6d  call    __security_check_cookie
0x1800e6e72  mov     rbx, [rsp+0E8h+arg_18]
  ... truncated ...
```
