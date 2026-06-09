# Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS::WinsockDCTUdpChannelContextQoS(void)

- ea: `0x18012e914`
- end: `0x18012eacc`
- name: `??0WinsockDCTUdpChannelContextQoS@Dct@Basix@Microsoft@@QEAA@XZ`
- size: `440`
- prototype: `__int64 __fastcall(Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18012f620`
- `0x18013bba0`

## callees

- `0x180015bb8`
- `0x18009f188`
- `0x18009f228`
- `0x18012aa4c`
- `0x18012e914`
- `0x1802e78ec`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18012e9f2`
- `KERNEL32!LoadLibraryW` at `0x18012e9f2`
- `KERNEL32!GetProcAddress` at `0x18012ea0f`
- `KERNEL32!GetProcAddress` at `0x18012ea24`
- `KERNEL32!GetProcAddress` at `0x18012ea39`
- `KERNEL32!GetProcAddress` at `0x18012ea0f`
- `KERNEL32!GetProcAddress` at `0x18012ea24`
- `KERNEL32!GetProcAddress` at `0x18012ea39`

## string_xrefs

- `0x18012e9eb`: `qwave.dll`
- `0x18012ea05`: `QOSCreateHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *__fastcall Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS::WinsockDCTUdpChannelContextQoS(
        HMODULE *this)
{
  const struct Microsoft::Basix::Instrumentation::UdpQOSCreated *Description; // rax
  const struct Microsoft::Basix::Instrumentation::UdpQOSAdded *v3; // rax
  int v4; // esi
  HMODULE LibraryW; // rax
  char v6; // bl
  FARPROC ProcAddress; // rcx
  __int64 (__fastcall *v8)(int *, HMODULE *); // rax
  char v10[8]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v11; // [rsp+28h] [rbp-38h] BYREF
  __m128i si128; // [rsp+38h] [rbp-28h]
  Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *v13; // [rsp+48h] [rbp-18h]
  int v14; // [rsp+50h] [rbp-10h] BYREF

  v13 = (Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *)this;
  *this = 0;
  *((_DWORD *)this + 2) = 0;
  this[2] = 0;
  this[3] = 0;
  this[4] = 0;
  this[5] = 0;
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v11) = 0;
  Description = Microsoft::Basix::Instrumentation::UdpQOSCreated::GetDescription();
  Microsoft::Basix::Instrumentation::EventBase::EventBase(this + 8, Description, &v11);
  this[8] = (HMODULE)&Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::UdpQOSCreated>::`vftable';
  std::string::_Tidy_deallocate(&v11);
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v11) = 0;
  v3 = Microsoft::Basix::Instrumentation::UdpQOSAdded::GetDescription();
  Microsoft::Basix::Instrumentation::EventBase::EventBase(this + 48, v3, &v11);
  this[48] = (HMODULE)&Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::UdpQOSAdded>::`vftable';
  std::string::_Tidy_deallocate(&v11);
  v4 = 0;
  LibraryW = LoadLibraryW(L"qwave.dll");
  this[2] = LibraryW;
  v6 = 1;
  if ( LibraryW )
  {
    this[3] = (HMODULE)GetProcAddress(LibraryW, "QOSCreateHandle");
    this[4] = (HMODULE)GetProcAddress(this[2], "QOSCloseHandle");
    ProcAddress = GetProcAddress(this[2], "QOSAddSocketToFlow");
    this[5] = (HMODULE)ProcAddress;
    if ( this[2] )
    {
      if ( this[4] )
      {
        v8 = (__int64 (__fastcall *)(int *, HMODULE *))this[3];
        if ( v8 )
        {
          if ( ProcAddress )
          {
            v14 = 1;
            v4 = v8(&v14, this);
          }
        }
      }
    }
  }
  if ( *((_BYTE *)this + 192) )
  {
    if ( !*this || !this[2] || !v4 )
      v6 = 0;
    v10[0] = v6;
    Microsoft::Basix::Instrumentation::UdpQOSCreated::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
      this + 40,
      this + 25,
      v10);
  }
  return (Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *)this;
}

```

## disassembly

```asm
0x18012e914  mov     [rsp-18h+arg_8], rbx
0x18012e919  mov     [rsp-18h+arg_10], rsi
0x18012e91e  push    rbp
0x18012e91f  push    rdi
0x18012e920  push    r14
0x18012e922  mov     rbp, rsp
0x18012e925  mov     eax, 60h
0x18012e92a  call    _alloca_probe
0x18012e92f  sub     rsp, rax
0x18012e932  mov     rax, cs:__security_cookie
0x18012e939  xor     rax, rsp
0x18012e93c  mov     [rbp+var_8], rax
0x18012e940  mov     rdi, rcx
0x18012e943  mov     [rbp+var_18], rcx
0x18012e947  xor     r14d, r14d
0x18012e94a  mov     [rcx], r14
0x18012e94d  mov     [rcx+8], r14d
0x18012e951  mov     [rcx+10h], r14
0x18012e955  mov     [rcx+18h], r14
0x18012e959  mov     [rcx+20h], r14
0x18012e95d  mov     [rcx+28h], r14
0x18012e961  xorps   xmm0, xmm0
0x18012e964  movups  [rbp+var_38], xmm0
0x18012e968  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18012e970  movdqu  [rbp+var_28], xmm1
0x18012e975  mov     byte ptr [rbp+var_38], r14b
0x18012e979  call    ?GetDescription@UdpQOSCreated@Instrumentation@Basix@Microsoft@@SAAEBV1234@XZ; Microsoft::Basix::Instrumentation::UdpQOSCreated::GetDescription(void)
0x18012e97e  mov     rdx, rax
0x18012e981  lea     r8, [rbp+var_38]
0x18012e985  lea     rcx, [rdi+40h]
0x18012e989  call    ??0EventBase@Instrumentation@Basix@Microsoft@@IEAA@AEBVRecordDescriptor@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Instrumentation::EventBase::EventBase(Microsoft::Basix::Instrumentation::RecordDescriptor const &,std::string const &)
0x18012e98e  lea     rax, ??_7?$Event@VUdpQOSCreated@Instrumentation@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::UdpQOSCreated>::`vftable'
0x18012e995  mov     [rdi+40h], rax
0x18012e999  lea     rcx, [rbp+var_38]
0x18012e99d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012e9a2  lea     rbx, [rdi+180h]
0x18012e9a9  xorps   xmm0, xmm0
0x18012e9ac  movups  [rbp+var_38], xmm0
0x18012e9b0  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18012e9b8  movdqu  [rbp+var_28], xmm1
0x18012e9bd  mov     byte ptr [rbp+var_38], r14b
0x18012e9c1  call    ?GetDescription@UdpQOSAdded@Instrumentation@Basix@Microsoft@@SAAEBV1234@XZ; Microsoft::Basix::Instrumentation::UdpQOSAdded::GetDescription(void)
0x18012e9c6  mov     rdx, rax
0x18012e9c9  lea     r8, [rbp+var_38]
0x18012e9cd  mov     rcx, rbx
0x18012e9d0  call    ??0EventBase@Instrumentation@Basix@Microsoft@@IEAA@AEBVRecordDescriptor@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Instrumentation::EventBase::EventBase(Microsoft::Basix::Instrumentation::RecordDescriptor const &,std::string const &)
0x18012e9d5  lea     rax, ??_7?$Event@VUdpQOSAdded@Instrumentation@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::Instrumentation::UdpQOSAdded>::`vftable'
0x18012e9dc  mov     [rbx], rax
0x18012e9df  lea     rcx, [rbp+var_38]
0x18012e9e3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012e9e8  mov     esi, r14d
0x18012e9eb  lea     rcx, LibFileName; "qwave.dll"
0x18012e9f2  call    cs:__imp_LoadLibraryW
0x18012e9f8  mov     [rdi+10h], rax
0x18012e9fc  lea     ebx, [r14+1]
0x18012ea00  test    rax, rax
0x18012ea03  jz      short loc_18012EA72
0x18012ea05  lea     rdx, aQoscreatehandl; "QOSCreateHandle"
0x18012ea0c  mov     rcx, rax; hModule
0x18012ea0f  call    cs:__imp_GetProcAddress
0x18012ea15  mov     [rdi+18h], rax
0x18012ea19  lea     rdx, aQosclosehandle; "QOSCloseHandle"
0x18012ea20  mov     rcx, [rdi+10h]; hModule
0x18012ea24  call    cs:__imp_GetProcAddress
0x18012ea2a  mov     [rdi+20h], rax
0x18012ea2e  lea     rdx, aQosaddsocketto; "QOSAddSocketToFlow"
0x18012ea35  mov     rcx, [rdi+10h]; hModule
0x18012ea39  call    cs:__imp_GetProcAddress
0x18012ea3f  mov     rcx, rax
0x18012ea42  mov     [rdi+28h], rax
0x18012ea46  cmp     [rdi+10h], r14
0x18012ea4a  jz      short loc_18012EA72
0x18012ea4c  cmp     [rdi+20h], r14
0x18012ea50  jz      short loc_18012EA72
0x18012ea52  mov     rax, [rdi+18h]
0x18012ea56  test    rax, rax
0x18012ea59  jz      short loc_18012EA72
0x18012ea5b  test    rcx, rcx
0x18012ea5e  jz      short loc_18012EA72
0x18012ea60  mov     [rbp+var_10], ebx
0x18012ea63  mov     rdx, rdi
0x18012ea66  lea     rcx, [rbp+var_10]
0x18012ea6a  call    cs:__guard_dispatch_icall_fptr
0x18012ea70  mov     esi, eax
0x18012ea72  cmp     [rdi+0C0h], r14b
0x18012ea79  jz      short loc_18012EAA8
0x18012ea7b  cmp     [rdi], r14
0x18012ea7e  jz      short loc_18012EA8A
0x18012ea80  cmp     [rdi+10h], r14
0x18012ea84  jz      short loc_18012EA8A
0x18012ea86  test    esi, esi
0x18012ea88  jnz     short loc_18012EA8D
0x18012ea8a  mov     bl, r14b
0x18012ea8d  mov     [rbp+var_40], bl
0x18012ea90  lea     rdx, [rdi+0C8h]
0x18012ea97  lea     rcx, [rdi+140h]
0x18012ea9e  lea     r8, [rbp+var_40]
0x18012eaa2  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@UdpQOSCreated@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_N@Z; Microsoft::Basix::Instrumentation::UdpQOSCreated::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,bool const &)
0x18012eaa7  nop
0x18012eaa8  mov     rax, rdi
0x18012eaab  mov     rcx, [rbp+var_8]
0x18012eaaf  xor     rcx, rsp; StackCookie
0x18012eab2  call    __security_check_cookie
0x18012eab7  lea     r11, [rsp+60h+var_s0]
0x18012eabc  mov     rbx, [r11+28h]
0x18012eac0  mov     rsi, [r11+30h]
0x18012eac4  mov     rsp, r11
0x18012eac7  pop     r14
0x18012eac9  pop     rdi
0x18012eaca  pop     rbp
0x18012eacb  retn
```
