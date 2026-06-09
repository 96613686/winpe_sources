# Microsoft::RdpNano::UPnPManager::ActivePortMapping::~ActivePortMapping(void)

- ea: `0x1800d669c`
- end: `0x1800d6964`
- name: `??1ActivePortMapping@UPnPManager@RdpNano@Microsoft@@UEAA@XZ`
- size: `712`
- prototype: `void __fastcall(Microsoft::RdpNano::UPnPManager::ActivePortMapping *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800d7090`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180045eb4`
- `0x1800d6154`
- `0x1800d6410`
- `0x1800d669c`
- `0x1800d9eb0`
- `0x1800dbd30`
- `0x1800dbe90`
- `0x180249a80`
- `0x1802f487c`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800d67d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800d67e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800d67ef`
- `OLEAUT32!__imp_VariantInit` at `0x1800d67d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800d67e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800d67ef`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d6801`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d6801`

## string_xrefs

- `0x1800d678c`: `DeletePortMapping`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Microsoft::RdpNano::UPnPManager::ActivePortMapping::~ActivePortMapping(
        Microsoft::RdpNano::UPnPManager::ActivePortMapping *this)
{
  Microsoft::RdpNano::UPnPManager::ActivePortMapping *v1; // rbx
  __int64 v2; // rdx
  Microsoft::Basix::Timer *v3; // rdi
  Microsoft::Basix::Timer *v4; // rsi
  char v5; // r12
  unsigned __int16 PortInHostByteOrder; // r15
  __int64 *v7; // r14
  const char *v8; // rdx
  __int64 v9; // rcx
  __int64 *Description; // rax
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // r15
  __int128 *v14; // rsi
  char v15; // bl
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  char v20; // bl
  const char *v21; // r9
  volatile signed __int32 *v22; // rbx
  const char *v23; // [rsp+20h] [rbp-268h]
  int v24; // [rsp+28h] [rbp-260h]
  const char *v25; // [rsp+30h] [rbp-258h]
  __int128 v27; // [rsp+50h] [rbp-238h] BYREF
  __int128 v28; // [rsp+60h] [rbp-228h]
  Microsoft::Basix::Timer *v29; // [rsp+70h] [rbp-218h]
  __int128 v30; // [rsp+80h] [rbp-208h] BYREF
  __int64 v31; // [rsp+90h] [rbp-1F8h]
  __int64 v32; // [rsp+98h] [rbp-1F0h]
  __int128 v33; // [rsp+A0h] [rbp-1E8h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-1D8h]
  __int64 v35; // [rsp+B8h] [rbp-1D0h]
  __int128 v36; // [rsp+C0h] [rbp-1C8h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-1B8h]
  __int64 v38; // [rsp+D8h] [rbp-1B0h]
  char v39[8]; // [rsp+E0h] [rbp-1A8h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-1A0h] BYREF
  VARIANTARG v41; // [rsp+100h] [rbp-188h] BYREF
  VARIANTARG v42; // [rsp+118h] [rbp-170h] BYREF
  const std::exception *v43[2]; // [rsp+130h] [rbp-158h] BYREF
  _BYTE v44[32]; // [rsp+140h] [rbp-148h] BYREF
  _BYTE v45[32]; // [rsp+160h] [rbp-128h] BYREF
  _BYTE v46[32]; // [rsp+180h] [rbp-108h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE v48[32]; // [rsp+1B8h] [rbp-D0h] BYREF
  _BYTE v49[32]; // [rsp+1D8h] [rbp-B0h] BYREF
  _BYTE v50[32]; // [rsp+1F8h] [rbp-90h] BYREF
  _BYTE v51[32]; // [rsp+218h] [rbp-70h] BYREF
  char v52; // [rsp+238h] [rbp-50h]
  char *v53[2]; // [rsp+240h] [rbp-48h] BYREF
  __int128 v54; // [rsp+250h] [rbp-38h]

  try
  {
    v1 = this;
    *(_QWORD *)this = &Microsoft::RdpNano::UPnPManager::ActivePortMapping::`vftable'{for `Microsoft::Basix::ITimerCallback'};
    v2 = *(int *)(*((_QWORD *)this + 1) + 4LL);
    *(_QWORD *)((char *)this + v2 + 8) = &Microsoft::RdpNano::UPnPManager::ActivePortMapping::`vftable'{for `Microsoft::Basix::SharedFromThis'};
    v3 = (Microsoft::RdpNano::UPnPManager::ActivePortMapping *)((char *)this + 16);
    v4 = (Microsoft::RdpNano::UPnPManager::ActivePortMapping *)((char *)this + 16);
    v29 = (Microsoft::RdpNano::UPnPManager::ActivePortMapping *)((char *)this + 16);
    LOBYTE(v2) = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3), v2);
    v5 = *((_BYTE *)v1 + 360);
    PortInHostByteOrder = Microsoft::Basix::Dct::SocketAddress::GetPortInHostByteOrder((Microsoft::RdpNano::UPnPManager::ActivePortMapping *)((char *)v1 + 184));
    v27 = 0;
    v28 = 0;
    std::string::_Construct<1,char const *>(&v27, (const char *)&Str1, 0);
    v7 = qword_18053D360;
    if ( v5 )
      v7 = qword_18053D2E0;
    *(_OWORD *)v53 = 0;
    v54 = 0;
    std::string::_Construct<1,char const *>(v53, "DeletePortMapping", 17);
    v8 = (const char *)v53;
    if ( *((_QWORD *)&v54 + 1) > 0xFu )
      v8 = v53[0];
    _bstr_t::_bstr_t((_bstr_t *)v39, v8);
    VariantInit(&pvarg);
    VariantInit(&v41);
    VariantInit(&v42);
    pvarg.llVal = (LONGLONG)SafeArrayCreateVector(0xCu, 0, 3u);
    if ( !pvarg.llVal )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    pvarg.vt = 8204;
    Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::VariantArrayPutElement(v39, &pvarg, 0, &v27);
    Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::VariantArrayPutElement_0(
      v39,
      &pvarg,
      1,
      PortInHostByteOrder);
    Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::VariantArrayPutElement(v39, &pvarg, 2, v7);
    std::string::_Tidy_deallocate(v53);
    Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::InvokeSync(v39, (char *)v1 + 40);
    Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::_UPnPAction_void_(v39);
    std::string::_Tidy_deallocate(&v27);
  }
  catch ( const std::exception *v43 )
  {
    *(_OWORD *)v53 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v53);
    if ( v53[0] && v53[0][128] )
    {
      Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v51, v43[0]);
      v11 = (__int64)Description;
      if ( (unsigned __int64)Description[3] > 0xF )
        v11 = *Description;
      v43[1] = (const std::exception *)v44;
      v12 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::SocketAddress>(v50, (char *)this + 48, 0, 6);
      v13 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::SocketAddress>(v49, (char *)this + 184, 0, 6);
      if ( *((_BYTE *)this + 360) )
      {
        v27 = 0;
        v28 = 0u;
        std::string::_Construct<1,char const *>(&v27, "UDP:", 4);
        v14 = &v27;
        v15 = 5;
      }
      else
      {
        v36 = 0;
        v37 = 0;
        v38 = 0;
        std::string::_Construct<1,char const *>(&v36, "TCP", 3);
        v14 = &v36;
        v15 = 10;
      }
      v33 = 0;
      v34 = 0;
      v35 = 0;
      std::string::_Construct<1,char const *>(&v33, "Failed to delete port mapping ", 30);
      LOBYTE(v16) = v52;
      std::string::string(v46, v16, &v33, v14);
      LOBYTE(v17) = v52;
      std::string::string(v45, v17, v46, v13);
      v18 = std::operator+<char>(v48, v45, "->");
      LOBYTE(v19) = v52;
      std::string::string(v44, v19, v18, v12);
      v20 = v15 | 0xF0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      std::string::_Construct<1,char const *>(
        &v30,
        "%s: %s\n Caught at:\n    %s(%d): %s()",
        (const char *)0x23,
        v21,
        v23,
        v24,
        v25);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,std::string,char const *,char const *,int,char const *>(
        (unsigned int)v53,
        (unsigned int)"RDPNANO",
        (unsigned int)&v30,
        (unsigned int)v44,
        v11,
        (__int64)"C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp",
        189,
        (__int64)"Microsoft::RdpNano::UPnPManager::ActivePortMapping::~ActivePortMapping");
      std::string::_Tidy_deallocate(&v30);
      std::string::_Tidy_deallocate(v48);
      std::string::_Tidy_deallocate(v45);
      std::string::_Tidy_deallocate(v46);
      std::string::_Tidy_deallocate(&v33);
      if ( (v20 & 2) != 0 )
      {
        v20 &= ~2u;
        std::string::_Tidy_deallocate(&v36);
      }
      if ( (v20 & 1) != 0 )
        std::string::_Tidy_deallocate(&v27);
      std::string::_Tidy_deallocate(v49);
      std::string::_Tidy_deallocate(v50);
      std::string::_Tidy_deallocate(v51);
    }
    v22 = (volatile signed __int32 *)v53[1];
    if ( v53[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v53[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
    v4 = v29;
    v1 = this;
    v3 = v29;
  }
  std::string::_Tidy_deallocate((char *)v1 + 320);
  v9 = *((_QWORD *)v1 + 5);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  Microsoft::Basix::Timer::~Timer(v4);
  *(_QWORD *)v1 = &Microsoft::Basix::ITimerCallback::`vftable';
  *(_QWORD *)((char *)v3 + *(int *)(*((_QWORD *)v3 - 1) + 4LL) - 8) = &Microsoft::Basix::SharedFromThis::`vftable';
}

```

## disassembly

```asm
0x1800d669c  mov     [rsp+arg_8], rbx
0x1800d66a1  mov     [rsp+arg_10], rsi
0x1800d66a6  mov     [rsp+arg_18], rdi
0x1800d66ab  push    r12
0x1800d66ad  push    r14
0x1800d66af  push    r15
0x1800d66b1  mov     eax, 270h
0x1800d66b6  call    _alloca_probe
0x1800d66bb  sub     rsp, rax
0x1800d66be  mov     rax, cs:__security_cookie
0x1800d66c5  xor     rax, rsp
0x1800d66c8  mov     [rsp+288h+var_28], rax
0x1800d66d0  mov     rbx, rcx
0x1800d66d3  mov     [rsp+288h+var_240], rcx
0x1800d66d8  mov     [rsp+288h+var_248], 0
0x1800d66e0  lea     rax, ??_7ActivePortMapping@UPnPManager@RdpNano@Microsoft@@6BITimerCallback@Basix@3@@; const Microsoft::RdpNano::UPnPManager::ActivePortMapping::`vftable'{for `Microsoft::Basix::ITimerCallback'}
0x1800d66e7  mov     [rcx], rax
0x1800d66ea  mov     rax, [rcx+8]
0x1800d66ee  movsxd  rdx, dword ptr [rax+4]
0x1800d66f2  lea     rax, ??_7ActivePortMapping@UPnPManager@RdpNano@Microsoft@@6BSharedFromThis@Basix@3@@; const Microsoft::RdpNano::UPnPManager::ActivePortMapping::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x1800d66f9  mov     [rdx+rcx+8], rax
0x1800d66fe  lea     rdi, [rcx+10h]
0x1800d6702  mov     rsi, rdi
0x1800d6705  mov     [rsp+288h+var_218], rdi
0x1800d670a  mov     rcx, [rdi+8]
0x1800d670e  mov     rax, [rcx]
0x1800d6711  mov     dl, 1
0x1800d6713  mov     rax, [rax+8]
0x1800d6717  call    cs:__guard_dispatch_icall_fptr
0x1800d671d  mov     r12b, [rbx+168h]
0x1800d6724  lea     rcx, [rbx+0B8h]; this
0x1800d672b  call    ?GetPortInHostByteOrder@SocketAddress@Dct@Basix@Microsoft@@QEBAGXZ; Microsoft::Basix::Dct::SocketAddress::GetPortInHostByteOrder(void)
0x1800d6730  movzx   r15d, ax
0x1800d6734  xorps   xmm0, xmm0
0x1800d6737  movups  [rsp+288h+var_238], xmm0
0x1800d673c  xorps   xmm1, xmm1
0x1800d673f  movdqu  [rsp+288h+var_228], xmm1
0x1800d6745  xor     r8d, r8d
0x1800d6748  lea     rdx, Str1
0x1800d674f  lea     rcx, [rsp+288h+var_238]
0x1800d6754  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d6759  nop
0x1800d675a  lea     rax, qword_18053D2E0
0x1800d6761  lea     r14, qword_18053D360
0x1800d6768  test    r12b, r12b
0x1800d676b  cmovnz  r14, rax
0x1800d676f  xorps   xmm0, xmm0
0x1800d6772  movups  xmmword ptr [rsp+288h+var_48], xmm0
0x1800d677a  xorps   xmm1, xmm1
0x1800d677d  movdqu  [rsp+288h+var_38], xmm1
0x1800d6786  mov     r8d, 11h
0x1800d678c  lea     rdx, aDeleteportmapp; "DeletePortMapping"
0x1800d6793  lea     rcx, [rsp+288h+var_48]
0x1800d679b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d67a0  nop
0x1800d67a1  lea     rdx, [rsp+288h+var_48]
0x1800d67a9  cmp     qword ptr [rsp+288h+var_38+8], 0Fh
0x1800d67b2  cmova   rdx, [rsp+288h+var_48]; char *
0x1800d67bb  lea     rcx, [rsp+288h+var_1A8]; this
0x1800d67c3  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800d67c8  nop
0x1800d67c9  lea     rcx, [rsp+288h+pvarg]; pvarg
0x1800d67d1  call    cs:__imp_VariantInit
0x1800d67d7  nop
0x1800d67d8  lea     rcx, [rsp+288h+var_188]; pvarg
0x1800d67e0  call    cs:__imp_VariantInit
0x1800d67e6  nop
0x1800d67e7  lea     rcx, [rsp+288h+var_170]; pvarg
0x1800d67ef  call    cs:__imp_VariantInit
0x1800d67f5  nop
0x1800d67f6  mov     ecx, 0Ch; vt
0x1800d67fb  xor     edx, edx; lLbound
0x1800d67fd  lea     r8d, [rcx-9]; cElements
0x1800d6801  call    cs:__imp_SafeArrayCreateVector
0x1800d6807  mov     qword ptr [rsp+288h+pvarg+8], rax
0x1800d680f  test    rax, rax
0x1800d6812  jz      loc_1800D6941
0x1800d6818  mov     eax, 200Ch
0x1800d681d  mov     word ptr [rsp+288h+pvarg], ax
0x1800d6825  lea     r9, [rsp+288h+var_238]
0x1800d682a  xor     r8d, r8d
0x1800d682d  lea     rdx, [rsp+288h+pvarg]
0x1800d6835  lea     rcx, [rsp+288h+var_1A8]
0x1800d683d  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void___VariantArrayPutElement
0x1800d6842  movzx   r9d, r15w
0x1800d6846  mov     r8d, 1
0x1800d684c  lea     rdx, [rsp+288h+pvarg]
0x1800d6854  lea     rcx, [rsp+288h+var_1A8]
0x1800d685c  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void___VariantArrayPutElement_0
0x1800d6861  mov     r9, r14
0x1800d6864  mov     r8d, 2
0x1800d686a  lea     rdx, [rsp+288h+pvarg]
0x1800d6872  lea     rcx, [rsp+288h+var_1A8]
0x1800d687a  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void___VariantArrayPutElement
0x1800d687f  nop
0x1800d6880  lea     rcx, [rsp+288h+var_48]
0x1800d6888  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d688d  nop
0x1800d688e  lea     rdx, [rbx+28h]
0x1800d6892  lea     rcx, [rsp+288h+var_1A8]
0x1800d689a  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void___InvokeSync
0x1800d689f  nop
0x1800d68a0  lea     rcx, [rsp+288h+var_1A8]
0x1800d68a8  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void____UPnPAction_void_
0x1800d68ad  nop
0x1800d68ae  lea     rcx, [rsp+288h+var_238]
0x1800d68b3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d68b8  nop
0x1800d68b9  jmp     short loc_1800D68C8
0x1800d68bb  mov     rsi, [rsp+288h+var_218]
0x1800d68c0  mov     rbx, [rsp+288h+var_240]
0x1800d68c5  mov     rdi, rsi
0x1800d68c8  lea     rcx, [rbx+140h]
0x1800d68cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d68d4  nop
0x1800d68d5  mov     rcx, [rbx+28h]
0x1800d68d9  test    rcx, rcx
0x1800d68dc  jz      short loc_1800D68EC
0x1800d68de  mov     rax, [rcx]
0x1800d68e1  mov     rax, [rax+10h]
0x1800d68e5  call    cs:__guard_dispatch_icall_fptr
0x1800d68eb  nop
0x1800d68ec  mov     rcx, rsi; this
0x1800d68ef  call    ??1Timer@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Timer::~Timer(void)
0x1800d68f4  nop
0x1800d68f5  lea     rax, ??_7ITimerCallback@Basix@Microsoft@@6B@; const Microsoft::Basix::ITimerCallback::`vftable'
0x1800d68fc  mov     [rbx], rax
0x1800d68ff  mov     rax, [rdi-8]
0x1800d6903  movsxd  rcx, dword ptr [rax+4]
0x1800d6907  lea     rax, ??_7SharedFromThis@Basix@Microsoft@@6B@; const Microsoft::Basix::SharedFromThis::`vftable'
0x1800d690e  mov     [rcx+rdi-8], rax
0x1800d6913  mov     rcx, [rsp+288h+var_28]
0x1800d691b  xor     rcx, rsp; StackCookie
0x1800d691e  call    __security_check_cookie
0x1800d6923  lea     r11, [rsp+288h+var_18]
0x1800d692b  mov     rbx, [r11+28h]
0x1800d692f  mov     rsi, [r11+30h]
0x1800d6933  mov     rdi, [r11+38h]
0x1800d6937  mov     rsp, r11
0x1800d693a  pop     r15
0x1800d693c  pop     r14
0x1800d693e  pop     r12
0x1800d6940  retn
0x1800d6941  lea     rcx, [rsp+288h+pExceptionObject]; this
0x1800d6949  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800d694e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800d6955  lea     rcx, [rsp+288h+pExceptionObject]; pExceptionObject
0x1800d695d  call    _CxxThrowException
```
