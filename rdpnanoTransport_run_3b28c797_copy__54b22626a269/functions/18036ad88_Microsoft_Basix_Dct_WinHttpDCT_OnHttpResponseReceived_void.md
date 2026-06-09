# Microsoft::Basix::Dct::WinHttpDCT::OnHttpResponseReceived(void)

- ea: `0x18036ad88`
- end: `0x18036b23f`
- name: `?OnHttpResponseReceived@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `1207`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinHttpDCT *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18036d148`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x18011963c`
- `0x180123200`
- `0x180125c94`
- `0x1801b3e10`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180366c14`
- `0x180367784`
- `0x180369978`
- `0x18036ad88`
- `0x18036c55c`
- `0x18036ca18`
- `0x18036cdc8`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18036ae8e`
- `KERNEL32!GetLastError` at `0x18036ae8e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18036ae07`
- `WINHTTP!WinHttpQueryHeaders` at `0x18036ae07`
- `WINHTTP!WinHttpWebSocketCompleteUpgrade` at `0x18036af50`
- `WINHTTP!WinHttpWebSocketCompleteUpgrade` at `0x18036af50`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Microsoft::Basix::Dct::WinHttpDCT::OnHttpResponseReceived(HINTERNET **this)
{
  HINTERNET **v2; // rsi
  void (__fastcall *v3)(HINTERNET **, __int64); // rsi
  __int64 v4; // rdi
  Microsoft::Basix *v5; // rcx
  const struct std::error_category *v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE *v11; // rcx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rcx
  HINTERNET *v17; // rbx
  __int64 v18; // rax
  HINTERNET *v19; // rdx
  void (__fastcall *v20)(HINTERNET **, __int64); // rdi
  __int64 v21; // rbx
  Microsoft::Basix *v22; // rcx
  const struct std::error_category *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  Microsoft::Basix::Dct::WinHttpDCT *v26; // rdi
  void (__fastcall *v27)(Microsoft::Basix::Dct::WinHttpDCT *, __int128 *); // rbx
  __int128 v28; // [rsp+30h] [rbp-158h] BYREF
  _OWORD v29[2]; // [rsp+40h] [rbp-148h] BYREF
  __int128 v30; // [rsp+60h] [rbp-128h] BYREF
  __int128 v31; // [rsp+70h] [rbp-118h]
  _OWORD v32[2]; // [rsp+80h] [rbp-108h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp-E8h] BYREF
  _BYTE v34[144]; // [rsp+C0h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+150h] [rbp-38h] BYREF
  int Buffer; // [rsp+160h] [rbp-28h] BYREF
  DWORD dwBufferLength; // [rsp+164h] [rbp-24h] BYREF

  *(_QWORD *)&v28 = this;
  Buffer = 0;
  dwBufferLength = 4;
  v2 = this + 144;
  if ( !WinHttpQueryHeaders(*this[144], 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    v3 = (void (__fastcall *)(HINTERNET **, __int64))(*this)[15];
    v4 = ((__int64 (__fastcall *)(HINTERNET **, _OWORD *))(*this)[13])(this, v32);
    v30 = 0;
    v31 = 0;
    std::string::_Construct<1,char const *>(&v30, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
    memset(v29, 0, sizeof(v29));
    std::string::_Construct<1,char const *>(v29, "WinHttpQueryHeaders failed", 26);
    v6 = Microsoft::Basix::WindowsCategory(v5);
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    LODWORD(v28) = v8;
    *((_QWORD *)&v28 + 1) = v6;
    v9 = Microsoft::Basix::SystemException::SystemException(
           (unsigned int)v34,
           (unsigned int)&v28,
           (unsigned int)v29,
           (unsigned int)&v30,
           460,
           v4);
    v10 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v35, v9);
    v3(this, v10);
    __ExceptionPtrDestroy(&v35);
    std::string::_Tidy_deallocate(v29);
    std::string::_Tidy_deallocate(&v30);
    v11 = v32;
    goto LABEL_23;
  }
  if ( Buffer != 101 )
  {
    v20 = (void (__fastcall *)(HINTERNET **, __int64))(*this)[15];
    v21 = ((__int64 (__fastcall *)(HINTERNET **, _BYTE *))(*this)[13])(this, v33);
    memset(v32, 0, sizeof(v32));
    std::string::_Construct<1,char const *>(v32, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
    v30 = 0;
    v31 = 0;
    std::string::_Construct<1,char const *>(&v30, "Unexpected http status returned", 31);
    v23 = Microsoft::Basix::WindowsCategory(v22);
    LODWORD(v28) = Buffer | 0x80190000;
    *((_QWORD *)&v28 + 1) = v23;
    v29[0] = v28;
    v24 = Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v34,
            (unsigned int)v29,
            (unsigned int)&v30,
            (unsigned int)v32,
            487,
            v21);
    v25 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v35, v24);
    v20(this, v25);
    __ExceptionPtrDestroy(&v35);
    std::string::_Tidy_deallocate(&v30);
    std::string::_Tidy_deallocate(v32);
    v11 = v33;
LABEL_23:
    std::string::_Tidy_deallocate(v11);
    Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal((Microsoft::Basix::Dct::WinHttpDCT *)this, 0);
    return;
  }
  Microsoft::Basix::Dct::WinHttpDCT::RemoveHttpCallback(v2);
  *(_QWORD *)&v35 = WinHttpWebSocketCompleteUpgrade(**v2, 0);
  v12 = std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(v29, &v35);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(this + 146, v12);
  v13 = (volatile signed __int32 *)*((_QWORD *)&v29[0] + 1);
  if ( *((_QWORD *)&v29[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v35 = 0;
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(v2, &v35);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  try
  {
    v15 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WinHttpDCT>(
            (char *)this + *((int *)this[1] + 1) + 8,
            v29);
    Microsoft::Basix::Dct::WinHttpDCT::SetHttpCallback(this + 146, v15);
    v16 = *((_QWORD *)&v29[0] + 1);
    if ( *((_QWORD *)&v29[0] + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29[0] + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  catch ( ... )
  {
    v26 = (Microsoft::Basix::Dct::WinHttpDCT *)v28;
    v27 = *(void (__fastcall **)(Microsoft::Basix::Dct::WinHttpDCT *, __int128 *))(*(_QWORD *)v28 + 120LL);
    v28 = 0;
    __ExceptionPtrCreate(&v28);
    __ExceptionPtrCurrentException(&v28);
    v27(v26, &v28);
    __ExceptionPtrDestroy(&v28);
    Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(v26, 0);
    return;
  }
  v17 = this[168];
  if ( v17 )
  {
    v18 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback>(
            (char *)this + *((int *)this[1] + 1) + 8,
            v29);
    v28 = 0;
    v19 = this[34];
    if ( v19 )
    {
      *(_QWORD *)&v28 = this[33];
      *((_QWORD *)&v28 + 1) = v19;
      _InterlockedIncrement((volatile signed __int32 *)v19 + 3);
    }
    Microsoft::Basix::Dct::ChannelThreadQueue::StartQueue(v17, &v28, v18);
  }
  Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnOpened(
    (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)this,
    0,
    1);
  Microsoft::Basix::Dct::WinHttpDCT::QueueRead((Microsoft::Basix::Dct::WinHttpDCT *)this);
}

```

## disassembly

```asm
0x18036ad88  mov     [rsp+arg_8], rbx
0x18036ad8d  mov     [rsp+arg_10], rsi
0x18036ad92  push    rdi
0x18036ad93  push    r14
0x18036ad95  push    r15
0x18036ad97  mov     eax, 170h
0x18036ad9c  call    _alloca_probe
0x18036ada1  sub     rsp, rax
0x18036ada4  mov     rax, cs:__security_cookie
0x18036adab  xor     rax, rsp
0x18036adae  mov     [rsp+188h+var_20], rax
0x18036adb6  mov     r14, rcx
0x18036adb9  mov     qword ptr [rsp+188h+var_158], rcx
0x18036adbe  mov     [rsp+188h+Buffer], 0
0x18036adc9  mov     [rsp+188h+dwBufferLength], 4
0x18036add4  lea     rsi, [rcx+480h]
0x18036addb  mov     rcx, [rsi]
0x18036adde  mov     [rsp+188h+lpdwIndex], 0; lpdwIndex
0x18036ade7  lea     rax, [rsp+188h+dwBufferLength]
0x18036adef  mov     [rsp+188h+lpdwBufferLength], rax; lpdwBufferLength
0x18036adf4  lea     r9, [rsp+188h+Buffer]; lpBuffer
0x18036adfc  xor     r8d, r8d; pwszName
0x18036adff  mov     edx, 20000013h; dwInfoLevel
0x18036ae04  mov     rcx, [rcx]; hRequest
0x18036ae07  call    cs:__imp_WinHttpQueryHeaders
0x18036ae0d  test    eax, eax
0x18036ae0f  jnz     loc_18036AF32
0x18036ae15  mov     rax, [r14]
0x18036ae18  mov     rsi, [rax+78h]
0x18036ae1c  lea     rdx, [rsp+188h+var_108]
0x18036ae24  mov     rcx, r14
0x18036ae27  mov     rax, [rax+68h]
0x18036ae2b  call    cs:__guard_dispatch_icall_fptr
0x18036ae31  mov     rdi, rax
0x18036ae34  xorps   xmm0, xmm0
0x18036ae37  movups  [rsp+188h+var_128], xmm0
0x18036ae3c  xorps   xmm1, xmm1
0x18036ae3f  movdqu  [rsp+188h+var_118], xmm1
0x18036ae45  mov     r8d, 32h ; '2'
0x18036ae4b  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036ae52  lea     rcx, [rsp+188h+var_128]
0x18036ae57  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036ae5c  nop
0x18036ae5d  xorps   xmm0, xmm0
0x18036ae60  movups  [rsp+188h+var_148], xmm0
0x18036ae65  xorps   xmm1, xmm1
0x18036ae68  movdqu  [rsp+188h+var_138], xmm1
0x18036ae6e  mov     r8d, 1Ah
0x18036ae74  lea     rdx, aWinhttpqueryhe_0; "WinHttpQueryHeaders failed"
0x18036ae7b  lea     rcx, [rsp+188h+var_148]
0x18036ae80  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036ae85  nop
0x18036ae86  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036ae8b  mov     rbx, rax
0x18036ae8e  call    cs:__imp_GetLastError
0x18036ae94  movzx   ecx, ax
0x18036ae97  or      ecx, 80070000h
0x18036ae9d  test    eax, eax
0x18036ae9f  cmovle  ecx, eax
0x18036aea2  mov     dword ptr [rsp+188h+var_158], ecx
0x18036aea6  mov     qword ptr [rsp+188h+var_158+8], rbx
0x18036aeab  movaps  xmm0, [rsp+188h+var_158]
0x18036aeb0  movdqa  [rsp+188h+var_158], xmm0
0x18036aeb6  mov     [rsp+188h+lpdwIndex], rdi
0x18036aebb  mov     [rsp+188h+lpdwBufferLength], 1CCh
0x18036aec4  lea     r9, [rsp+188h+var_128]
0x18036aec9  lea     r8, [rsp+188h+var_148]
0x18036aece  lea     rdx, [rsp+188h+var_158]
0x18036aed3  lea     rcx, [rsp+188h+var_C8]
0x18036aedb  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036aee0  mov     rdx, rax
0x18036aee3  lea     rcx, [rsp+188h+var_38]
0x18036aeeb  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18036aef0  nop
0x18036aef1  mov     rdx, rax
0x18036aef4  mov     rcx, r14
0x18036aef7  mov     rax, rsi
0x18036aefa  call    cs:__guard_dispatch_icall_fptr
0x18036af00  nop
0x18036af01  lea     rcx, [rsp+188h+var_38]; void *
0x18036af09  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18036af0e  nop
0x18036af0f  lea     rcx, [rsp+188h+var_148]
0x18036af14  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036af19  nop
0x18036af1a  lea     rcx, [rsp+188h+var_128]
0x18036af1f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036af24  nop
0x18036af25  lea     rcx, [rsp+188h+var_108]
0x18036af2d  jmp     loc_18036B207
0x18036af32  cmp     [rsp+188h+Buffer], 65h ; 'e'
0x18036af3a  jnz     loc_18036B0EA
0x18036af40  mov     rcx, rsi
0x18036af43  call    ?RemoveHttpCallback@WinHttpDCT@Dct@Basix@Microsoft@@KAXAEBV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::WinHttpDCT::RemoveHttpCallback(std::shared_ptr<Microsoft::Basix::Dct::WinHttpObj> const &)
0x18036af48  mov     rcx, [rsi]
0x18036af4b  xor     edx, edx; pContext
0x18036af4d  mov     rcx, [rcx]; hRequest
0x18036af50  call    cs:__imp_WinHttpWebSocketCompleteUpgrade
0x18036af56  mov     qword ptr [rsp+188h+var_38], rax
0x18036af5e  lea     rdx, [rsp+188h+var_38]
0x18036af66  lea     rcx, [rsp+188h+var_148]
0x18036af6b  call    ??$make_shared@VWinHttpObj@Dct@Basix@Microsoft@@AEAPEAX@std@@YA?AV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@0@AEAPEAX@Z; std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(void * &)
0x18036af70  lea     r15, [r14+490h]
0x18036af77  mov     rdx, rax
0x18036af7a  mov     rcx, r15
0x18036af7d  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036af82  mov     rdi, qword ptr [rsp+188h+var_148+8]
0x18036af87  or      ebx, 0FFFFFFFFh
0x18036af8a  test    rdi, rdi
0x18036af8d  jz      short loc_18036AFC4
0x18036af8f  mov     eax, ebx
0x18036af91  lock xadd [rdi+8], eax
0x18036af96  add     eax, ebx
0x18036af98  jnz     short loc_18036AFC4
0x18036af9a  mov     rax, [rdi]
0x18036af9d  mov     rcx, rdi
0x18036afa0  mov     rax, [rax]
0x18036afa3  call    cs:__guard_dispatch_icall_fptr
0x18036afa9  mov     eax, ebx
0x18036afab  lock xadd [rdi+0Ch], eax
0x18036afb0  add     eax, ebx
0x18036afb2  jnz     short loc_18036AFC4
0x18036afb4  mov     rax, [rdi]
0x18036afb7  mov     rcx, rdi
0x18036afba  mov     rax, [rax+8]
0x18036afbe  call    cs:__guard_dispatch_icall_fptr
0x18036afc4  xorps   xmm0, xmm0
0x18036afc7  movdqu  [rsp+188h+var_38], xmm0
0x18036afd0  lea     rdx, [rsp+188h+var_38]
0x18036afd8  mov     rcx, rsi
0x18036afdb  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036afe0  mov     rdi, qword ptr [rsp+188h+var_38+8]
0x18036afe8  test    rdi, rdi
0x18036afeb  jz      short loc_18036B023
0x18036afed  mov     eax, ebx
0x18036afef  lock xadd [rdi+8], eax
0x18036aff4  add     eax, ebx
0x18036aff6  jnz     short loc_18036B023
0x18036aff8  mov     rax, [rdi]
0x18036affb  mov     rcx, rdi
0x18036affe  mov     rax, [rax]
0x18036b001  call    cs:__guard_dispatch_icall_fptr
0x18036b007  mov     eax, ebx
0x18036b009  lock xadd [rdi+0Ch], eax
0x18036b00e  add     eax, ebx
0x18036b010  jnz     short loc_18036B023
0x18036b012  mov     rax, [rdi]
0x18036b015  mov     rcx, rdi
0x18036b018  mov     rax, [rax+8]
0x18036b01c  call    cs:__guard_dispatch_icall_fptr
0x18036b022  nop
0x18036b023  mov     rax, [r14+8]
0x18036b027  movsxd  rcx, dword ptr [rax+4]
0x18036b02b  add     rcx, 8
0x18036b02f  add     rcx, r14
0x18036b032  lea     rdx, [rsp+188h+var_148]
0x18036b037  call    ??$GetWeakPtr@VWinHttpDCT@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VWinHttpDCT@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WinHttpDCT>(void)
0x18036b03c  nop
0x18036b03d  mov     rdx, rax
0x18036b040  mov     rcx, r15
0x18036b043  call    ?SetHttpCallback@WinHttpDCT@Dct@Basix@Microsoft@@KAXAEBV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@std@@AEBV?$weak_ptr@VWinHttpDCT@Dct@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Dct::WinHttpDCT::SetHttpCallback(std::shared_ptr<Microsoft::Basix::Dct::WinHttpObj> const &,std::weak_ptr<Microsoft::Basix::Dct::WinHttpDCT> const &)
0x18036b048  nop
0x18036b049  mov     rcx, qword ptr [rsp+188h+var_148+8]
0x18036b04e  test    rcx, rcx
0x18036b051  jz      short loc_18036B06C
0x18036b053  mov     eax, ebx
0x18036b055  lock xadd [rcx+0Ch], eax
0x18036b05a  add     eax, ebx
0x18036b05c  jnz     short loc_18036B06C
0x18036b05e  mov     rax, [rcx]
0x18036b061  mov     rax, [rax+8]
0x18036b065  call    cs:__guard_dispatch_icall_fptr
0x18036b06b  nop
0x18036b06c  mov     rbx, [r14+540h]
0x18036b073  test    rbx, rbx
0x18036b076  jz      short loc_18036B0CB
0x18036b078  mov     rax, [r14+8]
0x18036b07c  movsxd  rcx, dword ptr [rax+4]
0x18036b080  add     rcx, 8
0x18036b084  add     rcx, r14
0x18036b087  lea     rdx, [rsp+188h+var_148]
0x18036b08c  call    ??$GetWeakPtr@VThreadTerminateCallback@IThreadedObject@Pattern@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VThreadTerminateCallback@IThreadedObject@Pattern@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback>(void)
0x18036b091  xorps   xmm0, xmm0
0x18036b094  movdqu  [rsp+188h+var_158], xmm0
0x18036b09a  mov     rdx, [r14+110h]
0x18036b0a1  test    rdx, rdx
0x18036b0a4  jz      short loc_18036B0BB
0x18036b0a6  mov     rcx, [r14+108h]
0x18036b0ad  mov     qword ptr [rsp+188h+var_158], rcx
0x18036b0b2  mov     qword ptr [rsp+188h+var_158+8], rdx
0x18036b0b7  lock inc dword ptr [rdx+0Ch]
0x18036b0bb  mov     r8, rax
0x18036b0be  lea     rdx, [rsp+188h+var_158]
0x18036b0c3  mov     rcx, rbx
0x18036b0c6  call    ?StartQueue@ChannelThreadQueue@Dct@Basix@Microsoft@@QEAAXV?$weak_ptr@VDataReceiveCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$weak_ptr@VThreadTerminateCallback@IThreadedObject@Pattern@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Dct::ChannelThreadQueue::StartQueue(std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback>,std::weak_ptr<Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback>)
0x18036b0cb  mov     r8b, 1; bool
0x18036b0ce  xor     edx, edx; bool
0x18036b0d0  mov     rcx, r14; this
0x18036b0d3  call    ?FireOnOpened@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@MEAAX_N0@Z; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnOpened(bool,bool)
0x18036b0d8  mov     rcx, r14; this
0x18036b0db  call    ?QueueRead@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXXZ; Microsoft::Basix::Dct::WinHttpDCT::QueueRead(void)
0x18036b0e0  jmp     loc_18036B216
0x18036b0e5  jmp     loc_18036B216
0x18036b0ea  mov     rax, [r14]
0x18036b0ed  mov     rdi, [rax+78h]
0x18036b0f1  lea     rdx, [rsp+188h+var_E8]
0x18036b0f9  mov     rcx, r14
0x18036b0fc  mov     rax, [rax+68h]
0x18036b100  call    cs:__guard_dispatch_icall_fptr
0x18036b106  mov     rbx, rax
0x18036b109  xorps   xmm0, xmm0
0x18036b10c  movups  [rsp+188h+var_108], xmm0
0x18036b114  xorps   xmm1, xmm1
0x18036b117  movdqu  [rsp+188h+var_F8], xmm1
0x18036b120  mov     r8d, 32h ; '2'
0x18036b126  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036b12d  lea     rcx, [rsp+188h+var_108]
0x18036b135  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036b13a  nop
0x18036b13b  xorps   xmm0, xmm0
0x18036b13e  movups  [rsp+188h+var_128], xmm0
0x18036b143  xorps   xmm1, xmm1
0x18036b146  movdqu  [rsp+188h+var_118], xmm1
0x18036b14c  mov     r8d, 1Fh
0x18036b152  lea     rdx, aUnexpectedHttp; "Unexpected http status returned"
0x18036b159  lea     rcx, [rsp+188h+var_128]
0x18036b15e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036b163  nop
0x18036b164  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036b169  mov     ecx, [rsp+188h+Buffer]
0x18036b170  or      ecx, 80190000h
0x18036b176  mov     dword ptr [rsp+188h+var_158], ecx
0x18036b17a  mov     qword ptr [rsp+188h+var_158+8], rax
0x18036b17f  movaps  xmm0, [rsp+188h+var_158]
0x18036b184  movdqa  [rsp+188h+var_148], xmm0
0x18036b18a  mov     [rsp+188h+lpdwIndex], rbx
0x18036b18f  mov     [rsp+188h+lpdwBufferLength], 1E7h
0x18036b198  lea     r9, [rsp+188h+var_108]
0x18036b1a0  lea     r8, [rsp+188h+var_128]
0x18036b1a5  lea     rdx, [rsp+188h+var_148]
0x18036b1aa  lea     rcx, [rsp+188h+var_C8]
0x18036b1b2  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036b1b7  mov     rdx, rax
0x18036b1ba  lea     rcx, [rsp+188h+var_38]
0x18036b1c2  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18036b1c7  nop
0x18036b1c8  mov     rdx, rax
0x18036b1cb  mov     rcx, r14
0x18036b1ce  mov     rax, rdi
0x18036b1d1  call    cs:__guard_dispatch_icall_fptr
0x18036b1d7  nop
0x18036b1d8  lea     rcx, [rsp+188h+var_38]; void *
0x18036b1e0  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18036b1e5  nop
0x18036b1e6  lea     rcx, [rsp+188h+var_128]
0x18036b1eb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036b1f0  nop
0x18036b1f1  lea     rcx, [rsp+188h+var_108]
0x18036b1f9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036b1fe  nop
0x18036b1ff  lea     rcx, [rsp+188h+var_E8]
0x18036b207  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036b20c  xor     edx, edx; bool
0x18036b20e  mov     rcx, r14; this
0x18036b211  call    ?FireOnClosedInternal@WinHttpDCT@Dct@Basix@Microsoft@@IEAAX_N@Z; Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(bool)
0x18036b216  mov     rcx, [rsp+188h+var_20]
0x18036b21e  xor     rcx, rsp; StackCookie
0x18036b221  call    __security_check_cookie
0x18036b226  lea     r11, [rsp+188h+var_18]
0x18036b22e  mov     rbx, [r11+28h]
0x18036b232  mov     rsi, [r11+30h]
0x18036b236  mov     rsp, r11
0x18036b239  pop     r15
0x18036b23b  pop     r14
0x18036b23d  pop     rdi
0x18036b23e  retn
```
