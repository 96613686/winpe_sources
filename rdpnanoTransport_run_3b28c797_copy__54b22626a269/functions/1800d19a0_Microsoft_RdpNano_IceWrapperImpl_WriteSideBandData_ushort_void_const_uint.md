# Microsoft::RdpNano::IceWrapperImpl::WriteSideBandData(ushort,void const *,uint)

- ea: `0x1800d19a0`
- end: `0x1800d1e0b`
- name: `?WriteSideBandData@IceWrapperImpl@RdpNano@Microsoft@@UEAAJGPEBXI@Z`
- size: `1131`
- prototype: `__int64 __fastcall(Microsoft::RdpNano::IceWrapperImpl *__hidden this, unsigned __int16, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000be70`
- `0x18000d9c0`
- `0x180015bb8`
- `0x18001902c`
- `0x1800191b4`
- `0x18001bbdc`
- `0x180028820`
- `0x180029d20`
- `0x1800c3a18`
- `0x1800c4238`
- `0x1800d19a0`
- `0x1800fdb80`
- `0x1802f13d4`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800d1a42`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800d1ab0`: `IceWrapperImpl::WriteSideBandData: type=%d`
- `0x1800d1c02`: `WriteSideBandData: iceSourcePtr == nullptr. cache it for now`
- `0x1800d1d35`: `WriteSideBandData from unknown source: type=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::RdpNano::IceWrapperImpl::WriteSideBandData(
        Microsoft::RdpNano::IceWrapperImpl *this,
        unsigned __int16 a2,
        const char *a3)
{
  const char *v5; // r9
  __int64 result; // rax
  volatile signed __int32 *v7; // rbx
  void (__fastcall ***v8)(_QWORD, _QWORD, __int128 *); // rcx
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rsi
  volatile signed __int32 *v12; // rsi
  void (__fastcall **v13)(__int64); // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  int v16; // [rsp+20h] [rbp-C8h]
  __int128 v17; // [rsp+28h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+38h] [rbp-B0h]
  __int128 v19; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-90h] BYREF
  _OWORD v21[2]; // [rsp+68h] [rbp-80h] BYREF
  _OWORD v22[2]; // [rsp+88h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  memset(v22, 0, sizeof(v22));
  try
  {
    std::string::_Construct<1,char const *>(v22, a3);
    v20 = 0;
    Microsoft::Basix::Containers::AnyPTreeFromJson(&v20, v22);
    if ( !*(_QWORD *)((*((_QWORD *)&v20 + 1) & -(__int64)(*((_QWORD *)&v20 + 1) != -17)) + 0x18) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)0x80070057LL,
        v16);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v20);
      std::string::_Tidy_deallocate(v22);
      return 2147942487LL;
    }
    v19 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v19);
    if ( (_QWORD)v19 && *(_BYTE *)(v19 + 128) )
    {
      memset(v21, 0, sizeof(v21));
      std::string::_Construct<1,char const *>(v21, "IceWrapperImpl::WriteSideBandData: type=%d", 42);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned short>(
        &v19,
        "RDPNANO",
        v21,
        a2);
      std::string::_Tidy_deallocate(v21);
    }
    v7 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    if ( (unsigned __int8)a2 >> 4 == 15 )
    {
      v8 = (void (__fastcall ***)(_QWORD, _QWORD, __int128 *))*((_QWORD *)this + 18);
      if ( v8 )
        (**v8)(v8, a2, &v20);
    }
    else
    {
      if ( (unsigned __int8)a2 >> 4 )
      {
        v21[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v21);
        if ( *(_QWORD *)&v21[0] && *(_BYTE *)(*(_QWORD *)&v21[0] + 128LL) )
        {
          v17 = 0;
          v18 = 0;
          std::string::_Construct<1,char const *>(&v17, "WriteSideBandData from unknown source: type=%d", 46);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short>(
            v21,
            "RDPNANO",
            &v17,
            a2);
          std::string::_Tidy_deallocate(&v17);
        }
        v15 = *((_QWORD *)&v21[0] + 1);
        if ( !*((_QWORD *)&v21[0] + 1) )
          goto LABEL_43;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) != 1 )
          goto LABEL_43;
        (**(void (__fastcall ***)(__int64))v15)(v15);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 12), 0xFFFFFFFF) != 1 )
          goto LABEL_43;
        v13 = *(void (__fastcall ***)(__int64))v15;
        v14 = v15;
      }
      else
      {
        v19 = 0;
        if ( Mtx_lock((Microsoft::RdpNano::IceWrapperImpl *)((char *)this + 168)) )
          std::_Throw_Cpp_error(5);
        if ( *((_DWORD *)this + 61) == 0x7FFFFFFF )
        {
          *((_DWORD *)this + 61) = 2147483646;
          std::_Throw_Cpp_error(6);
        }
        if ( *((_QWORD *)this + 8) )
        {
          v9 = *((_QWORD *)this + 9);
          if ( v9 )
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
          v10 = *((_QWORD *)this + 8);
          *(_QWORD *)&v19 = v10;
          v11 = *((_QWORD *)this + 9);
          *((_QWORD *)&v19 + 1) = v11;
        }
        else
        {
          v21[0] = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v21);
          if ( *(_QWORD *)&v21[0] && *(_BYTE *)(*(_QWORD *)&v21[0] + 128LL) )
          {
            v17 = 0;
            v18 = 0;
            std::string::_Construct<1,char const *>(
              &v17,
              "WriteSideBandData: iceSourcePtr == nullptr. cache it for now",
              60);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
              v21,
              "RDPNANO",
              &v17);
            std::string::_Tidy_deallocate(&v17);
          }
          v12 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
          if ( *((_QWORD *)&v21[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
              if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            }
          }
          *((_WORD *)this + 152) = a2;
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=((char *)this + 312);
          v11 = *((_QWORD *)&v19 + 1);
          v10 = v19;
        }
        Mtx_unlock((Microsoft::RdpNano::IceWrapperImpl *)((char *)this + 168));
        if ( v10 )
          Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(v10, a2, (__int64)&v20);
        if ( !v11 )
          goto LABEL_43;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 0xFFFFFFFF) != 1 )
          goto LABEL_43;
        (**(void (__fastcall ***)(__int64))v11)(v11);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 12), 0xFFFFFFFF) != 1 )
          goto LABEL_43;
        v13 = *(void (__fastcall ***)(__int64))v11;
        v14 = v11;
      }
      v13[1](v14);
    }
LABEL_43:
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v20);
    std::string::_Tidy_deallocate(v22);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2A5,
                           (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800d19a0  push    rbx
0x1800d19a2  push    rsi
0x1800d19a3  push    rdi
0x1800d19a4  push    r12
0x1800d19a6  push    r14
0x1800d19a8  push    r15
0x1800d19aa  mov     eax, 0B8h
0x1800d19af  call    _alloca_probe
0x1800d19b4  sub     rsp, rax
0x1800d19b7  mov     rax, cs:__security_cookie
0x1800d19be  xor     rax, rsp
0x1800d19c1  mov     [rsp+0E8h+var_40], rax
0x1800d19c9  mov     rax, r8
0x1800d19cc  movzx   r12d, dx
0x1800d19d0  mov     r15, rcx
0x1800d19d3  xorps   xmm0, xmm0
0x1800d19d6  movups  [rsp+0E8h+var_60], xmm0
0x1800d19de  xorps   xmm1, xmm1
0x1800d19e1  movdqu  [rsp+0E8h+var_50], xmm1
0x1800d19ea  mov     r8d, r9d
0x1800d19ed  mov     rdx, rax
0x1800d19f0  lea     rcx, [rsp+0E8h+var_60]
0x1800d19f8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d19fd  nop
0x1800d19fe  xorps   xmm0, xmm0
0x1800d1a01  movups  [rsp+0E8h+var_90], xmm0
0x1800d1a06  lea     rdx, [rsp+0E8h+var_60]
0x1800d1a0e  lea     rcx, [rsp+0E8h+var_90]
0x1800d1a13  call    ?AnyPTreeFromJson@Containers@Basix@Microsoft@@YA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Containers::AnyPTreeFromJson(std::string const &)
0x1800d1a18  nop
0x1800d1a19  mov     rdx, qword ptr [rsp+0E8h+var_90+8]
0x1800d1a1e  lea     rax, [rdx+11h]
0x1800d1a22  neg     rax
0x1800d1a25  sbb     rcx, rcx
0x1800d1a28  and     rcx, rdx
0x1800d1a2b  cmp     qword ptr [rcx+18h], 0
0x1800d1a30  jnz     short loc_1800D1A73
0x1800d1a32  mov     rcx, [rsp+0E8h]; this
0x1800d1a3a  mov     ebx, 80070057h
0x1800d1a3f  mov     r9d, ebx; char *
0x1800d1a42  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800d1a49  mov     edx, 278h; void *
0x1800d1a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1a53  nop
0x1800d1a54  lea     rcx, [rsp+0E8h+var_90]
0x1800d1a59  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800d1a5e  nop
0x1800d1a5f  lea     rcx, [rsp+0E8h+var_60]
0x1800d1a67  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d1a6c  mov     eax, ebx
0x1800d1a6e  jmp     loc_1800D1DCD
0x1800d1a73  xorps   xmm0, xmm0
0x1800d1a76  movups  [rsp+0E8h+var_A0], xmm0
0x1800d1a7b  lea     rcx, [rsp+0E8h+var_A0]
0x1800d1a80  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d1a85  nop
0x1800d1a86  mov     rax, qword ptr [rsp+0E8h+var_A0]
0x1800d1a8b  test    rax, rax
0x1800d1a8e  jz      short loc_1800D1AE8
0x1800d1a90  cmp     byte ptr [rax+80h], 0
0x1800d1a97  jz      short loc_1800D1AE8
0x1800d1a99  xorps   xmm0, xmm0
0x1800d1a9c  movups  [rsp+0E8h+var_80], xmm0
0x1800d1aa1  xorps   xmm1, xmm1
0x1800d1aa4  movdqu  [rsp+0E8h+var_70], xmm1
0x1800d1aaa  mov     r8d, 2Ah ; '*'
0x1800d1ab0  lea     rdx, aIcewrapperimpl_4; "IceWrapperImpl::WriteSideBandData: type"...
0x1800d1ab7  lea     rcx, [rsp+0E8h+var_80]
0x1800d1abc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d1ac1  nop
0x1800d1ac2  movzx   r9d, r12w
0x1800d1ac6  lea     r8, [rsp+0E8h+var_80]
0x1800d1acb  lea     rdx, aRdpnano; "RDPNANO"
0x1800d1ad2  lea     rcx, [rsp+0E8h+var_A0]
0x1800d1ad7  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@G@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,ushort>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,ushort)
0x1800d1adc  nop
0x1800d1add  lea     rcx, [rsp+0E8h+var_80]
0x1800d1ae2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d1ae7  nop
0x1800d1ae8  mov     rbx, qword ptr [rsp+0E8h+var_A0+8]
0x1800d1aed  or      edi, 0FFFFFFFFh
0x1800d1af0  test    rbx, rbx
0x1800d1af3  jz      short loc_1800D1B2A
0x1800d1af5  mov     eax, edi
0x1800d1af7  lock xadd [rbx+8], eax
0x1800d1afc  add     eax, edi
0x1800d1afe  jnz     short loc_1800D1B2A
0x1800d1b00  mov     rax, [rbx]
0x1800d1b03  mov     rcx, rbx
0x1800d1b06  mov     rax, [rax]
0x1800d1b09  call    cs:__guard_dispatch_icall_fptr
0x1800d1b0f  mov     eax, edi
0x1800d1b11  lock xadd [rbx+0Ch], eax
0x1800d1b16  add     eax, edi
0x1800d1b18  jnz     short loc_1800D1B2A
0x1800d1b1a  mov     rax, [rbx]
0x1800d1b1d  mov     rcx, rbx
0x1800d1b20  mov     rax, [rax+8]
0x1800d1b24  call    cs:__guard_dispatch_icall_fptr
0x1800d1b2a  mov     al, r12b
0x1800d1b2d  shr     al, 4
0x1800d1b30  and     al, 0Fh
0x1800d1b32  cmp     al, 0Fh
0x1800d1b34  jnz     short loc_1800D1B60
0x1800d1b36  mov     rcx, [r15+90h]
0x1800d1b3d  test    rcx, rcx
0x1800d1b40  jz      loc_1800D1DAD
0x1800d1b46  mov     rax, [rcx]
0x1800d1b49  lea     r8, [rsp+0E8h+var_90]
0x1800d1b4e  movzx   edx, r12w
0x1800d1b52  mov     rax, [rax]
0x1800d1b55  call    cs:__guard_dispatch_icall_fptr
0x1800d1b5b  jmp     loc_1800D1DAD
0x1800d1b60  test    al, al
0x1800d1b62  jnz     loc_1800D1CF8
0x1800d1b68  xorps   xmm1, xmm1
0x1800d1b6b  movdqu  [rsp+0E8h+var_A0], xmm1
0x1800d1b71  lea     rbx, [r15+0A8h]
0x1800d1b78  mov     [rsp+0E8h+var_C8], rbx
0x1800d1b7d  mov     rcx, rbx; _Mtx_t
0x1800d1b80  call    _Mtx_lock
0x1800d1b85  test    eax, eax
0x1800d1b87  jnz     loc_1800D1DEE
0x1800d1b8d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800d1b94  jz      loc_1800D1DF8
0x1800d1b9a  cmp     qword ptr [r15+40h], 0
0x1800d1b9f  jz      short loc_1800D1BC5
0x1800d1ba1  mov     rax, [r15+48h]
0x1800d1ba5  test    rax, rax
0x1800d1ba8  jz      short loc_1800D1BAE
0x1800d1baa  lock inc dword ptr [rax+8]
0x1800d1bae  mov     r14, [r15+40h]
0x1800d1bb2  mov     qword ptr [rsp+0E8h+var_A0], r14
0x1800d1bb7  mov     rsi, [r15+48h]
0x1800d1bbb  mov     qword ptr [rsp+0E8h+var_A0+8], rsi
0x1800d1bc0  jmp     loc_1800D1C98
0x1800d1bc5  xorps   xmm0, xmm0
0x1800d1bc8  movups  [rsp+0E8h+var_80], xmm0
0x1800d1bcd  lea     rcx, [rsp+0E8h+var_80]
0x1800d1bd2  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800d1bd7  nop
0x1800d1bd8  mov     rax, qword ptr [rsp+0E8h+var_80]
0x1800d1bdd  test    rax, rax
0x1800d1be0  jz      short loc_1800D1C36
0x1800d1be2  cmp     byte ptr [rax+80h], 0
0x1800d1be9  jz      short loc_1800D1C36
0x1800d1beb  xorps   xmm0, xmm0
0x1800d1bee  movups  [rsp+0E8h+var_C0], xmm0
0x1800d1bf3  xorps   xmm1, xmm1
0x1800d1bf6  movdqu  [rsp+0E8h+var_B0], xmm1
0x1800d1bfc  mov     r8d, 3Ch ; '<'
0x1800d1c02  lea     rdx, aWritesidebandd_0; "WriteSideBandData: iceSourcePtr == null"...
0x1800d1c09  lea     rcx, [rsp+0E8h+var_C0]
0x1800d1c0e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d1c13  nop
0x1800d1c14  lea     r8, [rsp+0E8h+var_C0]
0x1800d1c19  lea     rdx, aRdpnano; "RDPNANO"
0x1800d1c20  lea     rcx, [rsp+0E8h+var_80]
0x1800d1c25  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x1800d1c2a  nop
0x1800d1c2b  lea     rcx, [rsp+0E8h+var_C0]
0x1800d1c30  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d1c35  nop
0x1800d1c36  mov     rsi, qword ptr [rsp+0E8h+var_80+8]
0x1800d1c3b  test    rsi, rsi
0x1800d1c3e  jz      short loc_1800D1C75
0x1800d1c40  mov     eax, edi
0x1800d1c42  lock xadd [rsi+8], eax
0x1800d1c47  add     eax, edi
0x1800d1c49  jnz     short loc_1800D1C75
0x1800d1c4b  mov     rax, [rsi]
0x1800d1c4e  mov     rcx, rsi
0x1800d1c51  mov     rax, [rax]
0x1800d1c54  call    cs:__guard_dispatch_icall_fptr
0x1800d1c5a  mov     eax, edi
0x1800d1c5c  lock xadd [rsi+0Ch], eax
0x1800d1c61  add     eax, edi
0x1800d1c63  jnz     short loc_1800D1C75
0x1800d1c65  mov     rax, [rsi]
0x1800d1c68  mov     rcx, rsi
0x1800d1c6b  mov     rax, [rax+8]
0x1800d1c6f  call    cs:__guard_dispatch_icall_fptr
0x1800d1c75  mov     [r15+130h], r12w
0x1800d1c7d  lea     rcx, [r15+138h]
0x1800d1c84  lea     rdx, [rsp+0E8h+var_90]
0x1800d1c89  call    ??4?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV012@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=(boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &)
0x1800d1c8e  mov     rsi, qword ptr [rsp+0E8h+var_A0+8]
0x1800d1c93  mov     r14, qword ptr [rsp+0E8h+var_A0]
0x1800d1c98  mov     rcx, rbx; _Mtx_t
0x1800d1c9b  call    _Mtx_unlock
0x1800d1ca0  test    r14, r14
0x1800d1ca3  jz      short loc_1800D1CB7
0x1800d1ca5  lea     r8, [rsp+0E8h+var_90]
0x1800d1caa  movzx   edx, r12w
0x1800d1cae  mov     rcx, r14
0x1800d1cb1  call    ?OnReceiveSideBandData@ICESourceAdapter@RdpNano@Microsoft@@QEAAXGAEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z; Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(ushort,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &)
0x1800d1cb6  nop
0x1800d1cb7  test    rsi, rsi
0x1800d1cba  jz      loc_1800D1DAD
0x1800d1cc0  mov     eax, edi
0x1800d1cc2  lock xadd [rsi+8], eax
0x1800d1cc7  add     eax, edi
0x1800d1cc9  jnz     loc_1800D1DAD
0x1800d1ccf  mov     rax, [rsi]
0x1800d1cd2  mov     rcx, rsi
0x1800d1cd5  mov     rax, [rax]
0x1800d1cd8  call    cs:__guard_dispatch_icall_fptr
0x1800d1cde  mov     eax, edi
0x1800d1ce0  lock xadd [rsi+0Ch], eax
0x1800d1ce5  add     eax, edi
0x1800d1ce7  jnz     loc_1800D1DAD
0x1800d1ced  mov     rax, [rsi]
0x1800d1cf0  mov     rcx, rsi
0x1800d1cf3  jmp     loc_1800D1DA2
0x1800d1cf8  xorps   xmm0, xmm0
0x1800d1cfb  movups  [rsp+0E8h+var_80], xmm0
0x1800d1d00  lea     rcx, [rsp+0E8h+var_80]
0x1800d1d05  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800d1d0a  nop
0x1800d1d0b  mov     rax, qword ptr [rsp+0E8h+var_80]
0x1800d1d10  test    rax, rax
0x1800d1d13  jz      short loc_1800D1D6D
0x1800d1d15  cmp     byte ptr [rax+80h], 0
0x1800d1d1c  jz      short loc_1800D1D6D
0x1800d1d1e  xorps   xmm0, xmm0
0x1800d1d21  movups  [rsp+0E8h+var_C0], xmm0
0x1800d1d26  xorps   xmm1, xmm1
0x1800d1d29  movdqu  [rsp+0E8h+var_B0], xmm1
0x1800d1d2f  mov     r8d, 2Eh ; '.'
0x1800d1d35  lea     rdx, aWritesidebandd; "WriteSideBandData from unknown source: "...
0x1800d1d3c  lea     rcx, [rsp+0E8h+var_C0]
0x1800d1d41  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d1d46  nop
0x1800d1d47  movzx   r9d, r12w
0x1800d1d4b  lea     r8, [rsp+0E8h+var_C0]
0x1800d1d50  lea     rdx, aRdpnano; "RDPNANO"
0x1800d1d57  lea     rcx, [rsp+0E8h+var_80]
0x1800d1d5c  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@G@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,ushort>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,ushort)
0x1800d1d61  nop
0x1800d1d62  lea     rcx, [rsp+0E8h+var_C0]
0x1800d1d67  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d1d6c  nop
0x1800d1d6d  mov     rbx, qword ptr [rsp+0E8h+var_80+8]
0x1800d1d72  test    rbx, rbx
0x1800d1d75  jz      short loc_1800D1DAD
0x1800d1d77  mov     eax, edi
0x1800d1d79  lock xadd [rbx+8], eax
0x1800d1d7e  add     eax, edi
0x1800d1d80  jnz     short loc_1800D1DAD
0x1800d1d82  mov     rax, [rbx]
0x1800d1d85  mov     rcx, rbx
0x1800d1d88  mov     rax, [rax]
0x1800d1d8b  call    cs:__guard_dispatch_icall_fptr
0x1800d1d91  mov     eax, edi
0x1800d1d93  lock xadd [rbx+0Ch], eax
0x1800d1d98  add     eax, edi
0x1800d1d9a  jnz     short loc_1800D1DAD
0x1800d1d9c  mov     rax, [rbx]
0x1800d1d9f  mov     rcx, rbx
0x1800d1da2  mov     rax, [rax+8]
0x1800d1da6  call    cs:__guard_dispatch_icall_fptr
0x1800d1dac  nop
0x1800d1dad  lea     rcx, [rsp+0E8h+var_90]
0x1800d1db2  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800d1db7  nop
0x1800d1db8  lea     rcx, [rsp+0E8h+var_60]
0x1800d1dc0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d1dc5  xor     eax, eax
0x1800d1dc7  jmp     short loc_1800D1DCD
0x1800d1dc9  mov     eax, dword ptr [rsp+0E8h+var_C8]
0x1800d1dcd  mov     rcx, [rsp+0E8h+var_40]
0x1800d1dd5  xor     rcx, rsp; StackCookie
0x1800d1dd8  call    __security_check_cookie
0x1800d1ddd  add     rsp, 0B8h
0x1800d1de4  pop     r15
0x1800d1de6  pop     r14
0x1800d1de8  pop     r12
0x1800d1dea  pop     rdi
0x1800d1deb  pop     rsi
0x1800d1dec  pop     rbx
0x1800d1ded  retn
0x1800d1dee  mov     ecx, 5; int
0x1800d1df3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800d1df8  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800d1dff  mov     ecx, 6; int
0x1800d1e04  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
