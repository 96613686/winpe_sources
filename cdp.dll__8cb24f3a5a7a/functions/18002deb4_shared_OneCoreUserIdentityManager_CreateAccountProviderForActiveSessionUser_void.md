# shared::OneCoreUserIdentityManager::CreateAccountProviderForActiveSessionUser(void)

- ea: `0x18002deb4`
- end: `0x18002e53d`
- name: `?CreateAccountProviderForActiveSessionUser@OneCoreUserIdentityManager@shared@@AEAA?AV?$shared_ptr@VICDPAccountProvider@@@std@@XZ`
- size: `1673`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b8290`

## callees

- `0x180009b94`
- `0x18000acdc`
- `0x18000b7b0`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x18001ce80`
- `0x18002a254`
- `0x18002a350`
- `0x18002c838`
- `0x18002c9c4`
- `0x18002deb4`
- `0x180030190`
- `0x1800624cc`
- `0x18010b3ac`
- `0x180114c58`
- `0x180199618`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fc5e8`
- `0x1801fcb4e`
- `0x1801fcb5a`
- `0x180354010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e433`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002e433`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002defd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002defd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2cc`

## string_xrefs

- `0x18002e0a6`: `clsid:`
- `0x18002e405`: `Could not get CLSID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall shared::OneCoreUserIdentityManager::CreateAccountProviderForActiveSessionUser(
        __int64 a1,
        __int64 a2)
{
  HRESULT v3; // eax
  LPOLESTR v4; // r15
  unsigned __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 size_of; // rax
  char *v8; // rdi
  size_t v9; // rbx
  __int128 *v10; // rbx
  __int128 *i; // r9
  __int64 v12; // r8
  size_t v13; // rdi
  void **v14; // r9
  struct ICDPComAccountProvider *v15; // rsi
  unsigned __int64 v16; // r13
  void **v17; // rbx
  __int64 v18; // r8
  size_t v19; // r12
  void **v20; // r9
  struct ICDPComAccountProvider *v21; // rdi
  unsigned __int64 v22; // r15
  void **v23; // rbx
  struct ICDPComAccountProvider *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // r12
  struct ICDPComAccountProvider *v27; // rax
  const struct std::nothrow_t *v28; // rdx
  __int64 v29; // rcx
  const struct std::nothrow_t *v30; // rdx
  struct ICDPComAccountProvider *v31; // rcx
  const struct std::nothrow_t *v32; // rdx
  struct ICDPComAccountProvider *v34; // rdx
  void *v35; // rcx
  struct ICDPComAccountProvider *v36; // rdx
  __int64 v37; // rax
  size_t v38; // rbx
  char v39; // [rsp+20h] [rbp-E0h] BYREF
  void *v40; // [rsp+28h] [rbp-D8h] BYREF
  struct ICDPComAccountProvider *v41; // [rsp+30h] [rbp-D0h] BYREF
  int v42; // [rsp+38h] [rbp-C8h]
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v46; // [rsp+68h] [rbp-98h]
  void *v47[2]; // [rsp+70h] [rbp-90h] BYREF
  size_t v48; // [rsp+80h] [rbp-80h]
  unsigned __int64 v49; // [rsp+88h] [rbp-78h]
  __int128 v50; // [rsp+90h] [rbp-70h] BYREF
  void *v51[2]; // [rsp+A0h] [rbp-60h] BYREF
  size_t v52; // [rsp+B0h] [rbp-50h]
  size_t v53; // [rsp+B8h] [rbp-48h]
  void *v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  size_t v55; // [rsp+D0h] [rbp-30h]
  size_t v56; // [rsp+D8h] [rbp-28h]
  int v57; // [rsp+E0h] [rbp-20h]
  char v58; // [rsp+E4h] [rbp-1Ch]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  int v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h]
  __int64 v62; // [rsp+100h] [rbp+0h]
  __int128 v63; // [rsp+108h] [rbp+8h]
  __int128 v64; // [rsp+118h] [rbp+18h]
  __int128 v65; // [rsp+128h] [rbp+28h]
  int v66; // [rsp+138h] [rbp+38h]
  int v67; // [rsp+13Ch] [rbp+3Ch]
  void *Src[2]; // [rsp+140h] [rbp+40h] BYREF
  size_t Size; // [rsp+150h] [rbp+50h]
  unsigned __int64 v70; // [rsp+158h] [rbp+58h]
  void *v71[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v72; // [rsp+178h] [rbp+78h]
  _BYTE v73[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  v41 = (struct ICDPComAccountProvider *)a2;
  lpsz = 0;
  v3 = StringFromCLSID(&GUID_049d54b5_e524_41b2_bd4d_34f7a0efc31d, &lpsz);
  if ( v3 < 0 )
  {
    v41 = (struct ICDPComAccountProvider *)".\\onecoreuseridentitymanager.cpp";
    v42 = 551;
    v37 = cdp::MakeException<cdp::hresult_exception,>(v71, &v41, (unsigned int)v3, "Could not get CLSID.");
    cdp::CdpThrow<cdp::hresult_exception>(&v41, v37);
  }
  v4 = lpsz;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v5 = -1;
  do
    ++v5;
  while ( lpsz[v5] );
  v6 = 0x7FFFFFFFFFFFFFFELL;
  if ( v5 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v5 <= 7 )
  {
    v45 = v5;
    v46 = 7;
    v38 = 2 * v5;
    memcpy_0(&v44, lpsz, v38);
    *(_WORD *)((char *)&v44 + v38) = 0;
  }
  else
  {
    if ( (v5 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v6 = v5 | 7;
      if ( (v5 | 7) < 0xA )
        v6 = 10;
    }
    size_of = std::_Get_size_of_n<2>(v6 + 1);
    v8 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *(_QWORD *)&v44 = v8;
    v45 = v5;
    v46 = v6;
    v9 = 2 * v5;
    memcpy_0(v8, v4, v9);
    *(_WORD *)&v8[v9] = 0;
  }
  v10 = &v44;
  if ( v46 > 7 )
    v10 = (__int128 *)v44;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v73);
  for ( i = v10; *(_WORD *)i; i = (__int128 *)((char *)i + 2) )
    ;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v73,
    v47,
    v10,
    i);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v73);
  if ( v46 > 7 )
    std::_Deallocate<16>(v44, 2 * v46 + 2);
  v45 = 0;
  v46 = 7;
  LOWORD(v44) = 0;
  std::string::substr(v47, v71, 1, v48 - 2);
  v50 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  v53 = 15;
  LOBYTE(v51[0]) = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  v56 = 15;
  LOBYTE(v54[0]) = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v61 = 0;
  v62 = 0;
  v66 = -1;
  v60 = 2;
  v67 = 0;
  std::operator+<char>(Src, "clsid:", v71);
  v13 = Size;
  v14 = Src;
  v15 = (struct ICDPComAccountProvider *)Src[0];
  v16 = v70;
  if ( v70 > 0xF )
    v14 = (void **)Src[0];
  if ( Size > v53 )
  {
    LOBYTE(v12) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v51, Size, v12, v14);
    v16 = v70;
    v15 = (struct ICDPComAccountProvider *)Src[0];
  }
  else
  {
    v17 = v51;
    if ( v53 > 0xF )
      v17 = (void **)v51[0];
    v52 = Size;
    memmove_0(v17, v14, Size);
    *((_BYTE *)v17 + v13) = 0;
  }
  v19 = v48;
  v20 = v47;
  v21 = (struct ICDPComAccountProvider *)v47[0];
  v22 = v49;
  if ( v49 > 0xF )
    v20 = (void **)v47[0];
  if ( v48 > v56 )
  {
    LOBYTE(v18) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v54, v48, v18, v20);
    v22 = v49;
    v21 = (struct ICDPComAccountProvider *)v47[0];
  }
  else
  {
    v23 = v54;
    if ( v56 > 0xF )
      v23 = (void **)v54[0];
    v55 = v48;
    memmove_0(v23, v20, v48);
    *((_BYTE *)v23 + v19) = 0;
  }
  v57 = 2;
  v58 = 1;
  if ( *((_QWORD *)&v50 + 1) )
  {
    v41 = (struct ICDPComAccountProvider *)*((_QWORD *)&v50 + 1);
    *((_QWORD *)&v50 + 1) = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    if ( v57 == 3 )
    {
      shared::ComObjectLifetimeMgr<ICDPComAccountProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComAccountProvider,IUnknown>>::Get(
        &v50,
        &v41);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    }
  }
  shared::ComObjectLifetimeMgr<ICDPComAccountProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComAccountProvider,IUnknown>>::Get(
    &v50,
    &v41);
  v24 = v41;
  if ( v41 )
  {
    v40 = operator new(0x88u);
    v25 = shared::AccountProviderlet::AccountProviderlet((shared::AccountProviderlet *)v40, 0, v24);
    v26 = v25;
    if ( v25 )
    {
      *(_QWORD *)&v44 = v25;
      *((_QWORD *)&v44 + 1) = &v39;
      LOBYTE(v45) = 1;
      v27 = (struct ICDPComAccountProvider *)operator new(0x18u);
      v41 = v27;
      *(_OWORD *)v27 = 0;
      *((_DWORD *)v27 + 2) = 1;
      *((_DWORD *)v27 + 3) = 1;
      *(_QWORD *)v27 = &std::_Ref_count_resource<shared::AccountProviderlet *,cdp::detail::iunknown_deleter<shared::AccountProviderlet>>::`vftable';
      *((_QWORD *)v27 + 2) = v26;
    }
    else
    {
      v26 = 0;
      v27 = 0;
    }
    *(_QWORD *)a2 = v26;
    *(_QWORD *)(a2 + 8) = v27;
    if ( v24 )
      (*(void (__fastcall **)(struct ICDPComAccountProvider *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v16 > 0xF )
    {
      v28 = (const struct std::nothrow_t *)(v16 + 1);
      v40 = (void *)(v16 + 1);
      v41 = v15;
      if ( v16 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&v41, (unsigned __int64 *)&v40);
        v28 = (const struct std::nothrow_t *)v40;
        v15 = v41;
      }
      operator delete(v15, v28);
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v54);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v51);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)&v50 + 8);
    v29 = v50;
    if ( (_QWORD)v50 )
    {
      *(_QWORD *)&v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v72 > 0xF )
    {
      v30 = (const struct std::nothrow_t *)(v72 + 1);
      v40 = (void *)(v72 + 1);
      v31 = (struct ICDPComAccountProvider *)v71[0];
      v41 = (struct ICDPComAccountProvider *)v71[0];
      if ( v72 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&v41, (unsigned __int64 *)&v40);
        v31 = v41;
        v30 = (const struct std::nothrow_t *)v40;
      }
      operator delete(v31, v30);
    }
    if ( v22 > 0xF )
    {
      v32 = (const struct std::nothrow_t *)(v22 + 1);
      v40 = (void *)(v22 + 1);
      v41 = v21;
      if ( v22 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&v41, (unsigned __int64 *)&v40);
        v21 = v41;
        v32 = (const struct std::nothrow_t *)v40;
      }
LABEL_47:
      operator delete(v21, v32);
    }
  }
  else
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    if ( v16 > 0xF )
    {
      v34 = (struct ICDPComAccountProvider *)(v16 + 1);
      v41 = (struct ICDPComAccountProvider *)(v16 + 1);
      v40 = v15;
      if ( v16 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v40, (unsigned __int64 *)&v41);
        v34 = v41;
        v15 = (struct ICDPComAccountProvider *)v40;
      }
      operator delete(v15, v34);
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v54);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v51);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)&v50 + 8);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
    if ( v72 > 0xF )
    {
      v35 = v71[0];
      v36 = (struct ICDPComAccountProvider *)(v72 + 1);
      v41 = (struct ICDPComAccountProvider *)(v72 + 1);
      v40 = v71[0];
      if ( v72 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v40, (unsigned __int64 *)&v41);
        v36 = v41;
        v35 = v40;
      }
      operator delete(v35, v36);
    }
    if ( v22 > 0xF )
    {
      v32 = (const struct std::nothrow_t *)(v22 + 1);
      v41 = (struct ICDPComAccountProvider *)(v22 + 1);
      v40 = v21;
      if ( v22 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v40, (unsigned __int64 *)&v41);
        v32 = v41;
        v21 = (struct ICDPComAccountProvider *)v40;
      }
      goto LABEL_47;
    }
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return a2;
}

```

## disassembly

```asm
0x18002deb4  push    rbp
0x18002deb6  push    rbx
0x18002deb7  push    rsi
0x18002deb8  push    rdi
0x18002deb9  push    r12
0x18002debb  push    r13
0x18002debd  push    r14
0x18002debf  push    r15
0x18002dec1  lea     rbp, [rsp-138h]
0x18002dec9  sub     rsp, 238h
0x18002ded0  mov     rax, cs:__security_cookie
0x18002ded7  xor     rax, rsp
0x18002deda  mov     [rbp+170h+var_50], rax
0x18002dee1  mov     r14, rdx
0x18002dee4  mov     [rsp+270h+var_240], rdx
0x18002dee9  xor     r12d, r12d
0x18002deec  mov     [rsp+270h+lpsz], r12
0x18002def1  lea     rdx, [rsp+270h+lpsz]; lplpsz
0x18002def6  lea     rcx, _GUID_049d54b5_e524_41b2_bd4d_34f7a0efc31d; rclsid
0x18002defd  call    cs:__imp_StringFromCLSID
0x18002df03  test    eax, eax
0x18002df05  js      loc_18002E3F1
0x18002df0b  mov     r15, [rsp+270h+lpsz]
0x18002df10  xorps   xmm0, xmm0
0x18002df13  movups  [rsp+270h+var_220], xmm0
0x18002df18  mov     [rsp+270h+var_210], r12
0x18002df1d  mov     [rsp+270h+var_208], r12
0x18002df22  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002df26  inc     rbx
0x18002df29  cmp     [r15+rbx*2], r12w
0x18002df2e  jnz     short loc_18002DF26
0x18002df30  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18002df3a  cmp     rbx, rsi
0x18002df3d  ja      loc_18002E42C
0x18002df43  mov     r13d, 7
0x18002df49  cmp     rbx, r13
0x18002df4c  jbe     loc_18002E43A
0x18002df52  mov     rax, rbx
0x18002df55  or      rax, r13
0x18002df58  cmp     rax, rsi
0x18002df5b  ja      short loc_18002DF6B
0x18002df5d  mov     rsi, rax
0x18002df60  lea     ecx, [r13+3]
0x18002df64  cmp     rax, rcx
0x18002df67  cmovb   rsi, rcx
0x18002df6b  lea     rcx, [rsi+1]
0x18002df6f  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x18002df74  mov     rcx, rax
0x18002df77  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002df7c  mov     rdi, rax
0x18002df7f  mov     qword ptr [rsp+270h+var_220], rax
0x18002df84  mov     [rsp+270h+var_210], rbx
0x18002df89  mov     [rsp+270h+var_208], rsi
0x18002df8e  add     rbx, rbx
0x18002df91  mov     r8, rbx; Size
0x18002df94  mov     rdx, r15; Src
0x18002df97  mov     rcx, rax; void *
0x18002df9a  call    memcpy_0
0x18002df9f  mov     [rbx+rdi], r12w
0x18002dfa4  lea     rbx, [rsp+270h+var_220]
0x18002dfa9  cmp     [rsp+270h+var_208], r13
0x18002dfae  cmova   rbx, qword ptr [rsp+270h+var_220]
0x18002dfb4  lea     rcx, [rbp+170h+var_D0]
0x18002dfbb  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18002dfc0  nop
0x18002dfc1  mov     r9, rbx
0x18002dfc4  cmp     [rbx], r12w
0x18002dfc8  jz      short loc_18002DFD4
0x18002dfca  add     r9, 2
0x18002dfce  cmp     [r9], r12w
0x18002dfd2  jnz     short loc_18002DFCA
0x18002dfd4  mov     r8, rbx
0x18002dfd7  lea     rdx, [rsp+270h+var_200]
0x18002dfdc  lea     rcx, [rbp+170h+var_D0]
0x18002dfe3  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18002dfe8  nop
0x18002dfe9  lea     rcx, [rbp+170h+var_D0]
0x18002dff0  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18002dff5  nop
0x18002dff6  mov     rdx, [rsp+270h+var_208]
0x18002dffb  cmp     rdx, r13
0x18002dffe  jbe     short loc_18002E012
0x18002e000  lea     rdx, ds:2[rdx*2]
0x18002e008  mov     rcx, qword ptr [rsp+270h+var_220]
0x18002e00d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e012  mov     [rsp+270h+var_210], r12
0x18002e017  mov     [rsp+270h+var_208], r13
0x18002e01c  mov     word ptr [rsp+270h+var_220], r12w
0x18002e022  mov     r9, [rbp+170h+var_1F0]
0x18002e026  add     r9, 0FFFFFFFFFFFFFFFEh
0x18002e02a  mov     r8d, 1
0x18002e030  lea     rdx, [rbp+170h+var_110]
0x18002e034  lea     rcx, [rsp+270h+var_200]
0x18002e039  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x18002e03e  nop
0x18002e03f  xorps   xmm0, xmm0
0x18002e042  movdqa  [rbp+170h+var_1E0], xmm0
0x18002e047  xorps   xmm1, xmm1
0x18002e04a  movups  xmmword ptr [rbp+170h+var_1D0], xmm1
0x18002e04e  mov     [rbp+170h+var_1C0], r12
0x18002e052  mov     r15d, 0Fh
0x18002e058  mov     [rbp+170h+var_1B8], r15
0x18002e05c  mov     byte ptr [rbp+170h+var_1D0], r12b
0x18002e060  movups  xmmword ptr [rbp+170h+var_1B0], xmm0
0x18002e064  mov     [rbp+170h+var_1A0], r12
0x18002e068  mov     [rbp+170h+var_198], r15
0x18002e06c  mov     byte ptr [rbp+170h+var_1B0], r12b
0x18002e070  mov     [rbp+170h+var_190], r12d
0x18002e074  mov     [rbp+170h+var_18C], r12b
0x18002e078  mov     [rbp+170h+var_188], r12
0x18002e07c  movups  [rbp+170h+var_168], xmm0
0x18002e080  movups  [rbp+170h+var_158], xmm0
0x18002e084  movups  [rbp+170h+var_148], xmm0
0x18002e088  mov     [rbp+170h+var_178], r12
0x18002e08c  mov     [rbp+170h+var_170], r12
0x18002e090  mov     [rbp+170h+var_138], 0FFFFFFFFh
0x18002e097  mov     [rbp+170h+var_180], 2
0x18002e09e  mov     [rbp+170h+var_134], r12d
0x18002e0a2  lea     r8, [rbp+170h+var_110]
0x18002e0a6  lea     rdx, aClsid; "clsid:"
0x18002e0ad  lea     rcx, [rbp+170h+Src]
0x18002e0b1  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18002e0b6  nop
0x18002e0b7  mov     rdi, [rbp+170h+Size]
0x18002e0bb  lea     r9, [rbp+170h+Src]
0x18002e0bf  mov     rsi, [rbp+170h+Src]
0x18002e0c3  mov     r13, [rbp+170h+var_118]
0x18002e0c7  cmp     r13, r15
0x18002e0ca  cmova   r9, rsi
0x18002e0ce  cmp     rdi, [rbp+170h+var_1B8]
0x18002e0d2  ja      loc_18002E3B8
0x18002e0d8  lea     rbx, [rbp+170h+var_1D0]
0x18002e0dc  cmp     [rbp+170h+var_1B8], r15
0x18002e0e0  cmova   rbx, [rbp+170h+var_1D0]
0x18002e0e5  mov     [rbp+170h+var_1C0], rdi
0x18002e0e9  mov     r8, rdi; Size
0x18002e0ec  mov     rdx, r9; Src
0x18002e0ef  mov     rcx, rbx; void *
0x18002e0f2  call    memmove_0
0x18002e0f7  mov     [rbx+rdi], r12b
0x18002e0fb  mov     r12, [rbp+170h+var_1F0]
0x18002e0ff  lea     r9, [rsp+270h+var_200]
0x18002e104  mov     rdi, [rsp+270h+var_200]
0x18002e109  mov     r15, [rbp+170h+var_1E8]
0x18002e10d  cmp     r15, 0Fh
0x18002e111  cmova   r9, rdi
0x18002e115  cmp     r12, [rbp+170h+var_198]
0x18002e119  ja      loc_18002E3D4
0x18002e11f  lea     rbx, [rbp+170h+var_1B0]
0x18002e123  cmp     [rbp+170h+var_198], 0Fh
0x18002e128  cmova   rbx, [rbp+170h+var_1B0]
0x18002e12d  mov     [rbp+170h+var_1A0], r12
0x18002e131  mov     r8, r12; Size
0x18002e134  mov     rdx, r9; Src
0x18002e137  mov     rcx, rbx; void *
0x18002e13a  call    memmove_0
0x18002e13f  mov     byte ptr [rbx+r12], 0
0x18002e144  mov     [rbp+170h+var_190], 2
0x18002e14b  mov     [rbp+170h+var_18C], 1
0x18002e14f  mov     rax, qword ptr [rbp+170h+var_1E0+8]
0x18002e153  xor     r12d, r12d
0x18002e156  test    rax, rax
0x18002e159  jnz     loc_18002E462
0x18002e15f  lea     rdx, [rsp+270h+var_240]
0x18002e164  lea     rcx, [rbp+170h+var_1E0]
0x18002e168  call    ?Get@?$ComObjectLifetimeMgr@UICDPComAccountProvider@@UIUnknown@@U?$DefaultCallbackPolicy@UICDPComAccountProvider@@UIUnknown@@@shared@@@shared@@QEAA?AV?$ComPtr@UICDPComAccountProvider@@@WRL@Microsoft@@_K@Z; shared::ComObjectLifetimeMgr<ICDPComAccountProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComAccountProvider,IUnknown>>::Get(unsigned __int64)
0x18002e16d  nop
0x18002e16e  mov     rbx, [rsp+270h+var_240]
0x18002e173  test    rbx, rbx
0x18002e176  jz      loc_18002E2F8
0x18002e17c  mov     ecx, 88h; Size
0x18002e181  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e186  mov     [rsp+270h+var_248], rax
0x18002e18b  mov     r8, rbx; struct ICDPComAccountProvider *
0x18002e18e  xor     edx, edx; unsigned __int64
0x18002e190  mov     rcx, rax; this
0x18002e193  call    ??0AccountProviderlet@shared@@QEAA@_KPEAUICDPComAccountProvider@@@Z; shared::AccountProviderlet::AccountProviderlet(unsigned __int64,ICDPComAccountProvider *)
0x18002e198  mov     r12, rax
0x18002e19b  test    rax, rax
0x18002e19e  jz      loc_18002E49C
0x18002e1a4  mov     al, [rsp+270h+var_250]
0x18002e1a8  mov     [rsp+270h+var_250], al
0x18002e1ac  mov     qword ptr [rsp+270h+var_220], r12
0x18002e1b1  lea     rax, [rsp+270h+var_250]
0x18002e1b6  mov     qword ptr [rsp+270h+var_220+8], rax
0x18002e1bb  mov     byte ptr [rsp+270h+var_210], 1
0x18002e1c0  mov     ecx, 18h; Size
0x18002e1c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e1ca  mov     [rsp+270h+var_240], rax
0x18002e1cf  xorps   xmm0, xmm0
0x18002e1d2  movups  xmmword ptr [rax], xmm0
0x18002e1d5  mov     dword ptr [rax+8], 1
0x18002e1dc  mov     dword ptr [rax+0Ch], 1
0x18002e1e3  lea     rcx, ??_7?$_Ref_count_resource@PEAVAccountProviderlet@shared@@U?$iunknown_deleter@VAccountProviderlet@shared@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<shared::AccountProviderlet *,cdp::detail::iunknown_deleter<shared::AccountProviderlet>>::`vftable'
0x18002e1ea  mov     [rax], rcx
0x18002e1ed  mov     [rax+10h], r12
0x18002e1f1  mov     [r14], r12
0x18002e1f4  mov     [r14+8], rax
0x18002e1f8  test    rbx, rbx
0x18002e1fb  jz      short loc_18002E20D
0x18002e1fd  mov     rax, [rbx]
0x18002e200  mov     rcx, rbx
0x18002e203  mov     rax, [rax+10h]
0x18002e207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e20c  nop
0x18002e20d  mov     ebx, 1000h
0x18002e212  cmp     r13, 0Fh
0x18002e216  jbe     short loc_18002E238
0x18002e218  lea     rdx, [r13+1]; struct std::nothrow_t *
0x18002e21c  mov     [rsp+270h+var_248], rdx
0x18002e221  mov     [rsp+270h+var_240], rsi
0x18002e226  cmp     rdx, rbx
0x18002e229  jnb     loc_18002E4A6
0x18002e22f  mov     rcx, rsi; void *
0x18002e232  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e237  nop
0x18002e238  lea     rcx, [rbp+170h+var_1B0]; void *
0x18002e23c  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18002e241  lea     rcx, [rbp+170h+var_1D0]; void *
0x18002e245  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18002e24a  lea     rcx, [rbp+170h+var_1E0+8]
0x18002e24e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e253  nop
0x18002e254  mov     rcx, qword ptr [rbp+170h+var_1E0]
0x18002e258  test    rcx, rcx
0x18002e25b  jz      short loc_18002E272
0x18002e25d  mov     qword ptr [rbp+170h+var_1E0], 0
0x18002e265  mov     rax, [rcx]
0x18002e268  mov     rax, [rax+10h]
0x18002e26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e271  nop
0x18002e272  mov     rdx, [rbp+170h+var_F8]
0x18002e276  cmp     rdx, 0Fh
0x18002e27a  jbe     short loc_18002E29C
0x18002e27c  inc     rdx; struct std::nothrow_t *
0x18002e27f  mov     [rsp+270h+var_248], rdx
0x18002e284  mov     rcx, [rbp+170h+var_110]; void *
0x18002e288  mov     [rsp+270h+var_240], rcx
0x18002e28d  cmp     rdx, rbx
0x18002e290  jnb     loc_18002E4C4
0x18002e296  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e29b  nop
0x18002e29c  cmp     r15, 0Fh
0x18002e2a0  jbe     short loc_18002E2C2
0x18002e2a2  lea     rdx, [r15+1]; struct std::nothrow_t *
0x18002e2a6  mov     [rsp+270h+var_248], rdx
0x18002e2ab  mov     [rsp+270h+var_240], rdi
0x18002e2b0  cmp     rdx, rbx
0x18002e2b3  jnb     loc_18002E4E2
0x18002e2b9  mov     rcx, rdi; void *
0x18002e2bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e2c1  nop
0x18002e2c2  mov     rcx, [rsp+270h+lpsz]; pv
0x18002e2c7  test    rcx, rcx
0x18002e2ca  jz      short loc_18002E2D2
0x18002e2cc  call    cs:__imp_CoTaskMemFree
0x18002e2d2  mov     rax, r14
0x18002e2d5  mov     rcx, [rbp+170h+var_50]
0x18002e2dc  xor     rcx, rsp; StackCookie
0x18002e2df  call    __security_check_cookie
0x18002e2e4  add     rsp, 238h
0x18002e2eb  pop     r15
0x18002e2ed  pop     r14
0x18002e2ef  pop     r13
0x18002e2f1  pop     r12
0x18002e2f3  pop     rdi
0x18002e2f4  pop     rsi
0x18002e2f5  pop     rbx
0x18002e2f6  pop     rbp
0x18002e2f7  retn
0x18002e2f8  mov     [r14], r12
0x18002e2fb  mov     [r14+8], r12
0x18002e2ff  mov     ebx, 1000h
0x18002e304  cmp     r13, 0Fh
0x18002e308  jbe     short loc_18002E32A
0x18002e30a  lea     rdx, [r13+1]; struct std::nothrow_t *
0x18002e30e  mov     [rsp+270h+var_240], rdx
0x18002e313  mov     [rsp+270h+var_248], rsi
0x18002e318  cmp     rdx, rbx
0x18002e31b  jnb     loc_18002E500
0x18002e321  mov     rcx, rsi; void *
0x18002e324  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e329  nop
0x18002e32a  lea     rcx, [rbp+170h+var_1B0]; void *
0x18002e32e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18002e333  lea     rcx, [rbp+170h+var_1D0]; void *
0x18002e337  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18002e33c  lea     rcx, [rbp+170h+var_1E0+8]
0x18002e340  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e345  lea     rcx, [rbp+170h+var_1E0]
0x18002e349  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e34e  nop
0x18002e34f  mov     rdx, [rbp+170h+var_F8]
0x18002e353  cmp     rdx, 0Fh
0x18002e357  jbe     short loc_18002E379
0x18002e359  mov     rcx, [rbp+170h+var_110]; void *
0x18002e35d  inc     rdx; struct std::nothrow_t *
0x18002e360  mov     [rsp+270h+var_240], rdx
0x18002e365  mov     [rsp+270h+var_248], rcx
0x18002e36a  cmp     rdx, rbx
  ... truncated ...
```
