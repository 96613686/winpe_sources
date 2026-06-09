# EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)

- ea: `0x18001a2f0`
- end: `0x18001a750`
- name: `?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z`
- size: `1120`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *this, const struct RegistryKey *, __int64, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b200`
- `0x18001b698`

## callees

- `0x180002a90`
- `0x180003fa4`
- `0x180004988`
- `0x1800054c4`
- `0x180009b98`
- `0x180009dc4`
- `0x180009dec`
- `0x18000a050`
- `0x180010aa8`
- `0x1800118e8`
- `0x180011908`
- `0x180019548`
- `0x180019588`
- `0x1800195c8`
- `0x180019b7c`
- `0x180019e54`
- `0x180019f30`
- `0x18001a2f0`
- `0x18002f93c`
- `0x180030294`
- `0x18003044c`
- `0x180030564`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::BaseEapLibraryManager::AddLegacyEapMethod(
        EapLm::BaseEapLibraryManager *this,
        const struct RegistryKey *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int MuiString; // eax
  int v11; // r8d
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  unsigned int v20; // esi
  unsigned int v21; // edi
  __int64 v22; // rax
  char v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int128 v27; // [rsp+60h] [rbp-A0h]
  _BYTE v28[16]; // [rsp+70h] [rbp-90h] BYREF
  char *v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  _BYTE v31[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h]
  _BYTE v33[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  ReferenceCounted *v35; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v36; // [rsp+D8h] [rbp-28h]
  _BYTE v37[64]; // [rsp+F0h] [rbp-10h] BYREF

  v25 = 0;
  v26 = 0;
  v27 = 0;
  HIDWORD(v25) = 0;
  LOBYTE(v25) = a3;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v33,
    a2,
    a3,
    a4);
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, &qword_18003C520, v33) )
    RegistryKey::QueryValue(a2, &qword_18003C520, v33);
  v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  *(_QWORD *)&v26 = BasicSimpleString<wchar_t>::Copy(v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v31,
    v7,
    v8,
    v9);
  MuiString = RegistryKey::ReadMuiString(a2, L"FriendlyName", v31);
  v12 = MuiString;
  if ( MuiString )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      v23 = MuiString;
      v29 = &v23;
      v30 = 1;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)MUIReadFailed,
        v11,
        2,
        (__int64)v28);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v12);
    }
    RegistryKey::QueryValue(a2, L"FriendlyName", v31);
  }
  if ( v32 )
  {
    if ( v34 )
    {
      v14 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v35, v33);
      std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v28, v14, v31);
      v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      *((_QWORD *)&v26 + 1) = BasicSimpleString<wchar_t>::Copy(v15);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v28);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v35);
    }
    else
    {
      v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      *((_QWORD *)&v26 + 1) = BasicSimpleString<wchar_t>::Copy(v13);
    }
  }
  LODWORD(v24) = 0;
  if ( (unsigned int)RegistryKey::QueryValue(a2, L"Properties", &v24) )
  {
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
      v28,
      v16,
      v17,
      v18);
    v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    RegistryKey::QueryValue(a2, v19, v28);
    if ( v29 )
      LODWORD(v27) = v27 | 0x200000;
    LODWORD(v24) = 0;
    RegistryKey::QueryValue(a2, L"StandaloneSupported", &v24);
    if ( (_DWORD)v24 )
      LODWORD(v27) = v27 | 0x40000;
    LODWORD(v24) = 0;
    RegistryKey::QueryValue(a2, L"MPPEEncryptionSupported", &v24);
    if ( (_DWORD)v24 )
      LODWORD(v27) = v27 | 0x80000;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v28);
  }
  else
  {
    LODWORD(v27) = v24;
  }
  v20 = 3;
  LODWORD(v24) = 0;
  RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v24);
  v21 = v24;
  if ( (_DWORD)v24 )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned int)v24);
    }
    v20 = v21;
  }
  if ( (*(unsigned __int8 (__fastcall **)(EapLm::BaseEapLibraryManager *, __int128 *, _QWORD, const struct RegistryKey *))(*(_QWORD *)this + 56LL))(
         this,
         &v25,
         v20,
         a2) )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v25,
        HIDWORD(v25));
    }
    v35 = 0;
    v24 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v35, &v24);
    v36 = v20;
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v24, (__int64)this + 80);
    v22 = std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(
            v37,
            &v25,
            &v35);
    std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(
      (char *)this + 136,
      v28,
      v22);
    std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(v37);
    if ( v28[8] )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v25);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 16));
    if ( v35 )
      ReferenceCounted::Release(v35);
  }
  else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v25);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v31);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v33);
  Free<HeapAllocator>((__int64)&v25);
}

```

## disassembly

```asm
0x18001a2f0  mov     [rsp-8+arg_18], rbx
0x18001a2f5  push    rbp
0x18001a2f6  push    rsi
0x18001a2f7  push    rdi
0x18001a2f8  push    r12
0x18001a2fa  push    r13
0x18001a2fc  push    r14
0x18001a2fe  push    r15
0x18001a300  lea     rbp, [rsp-40h]
0x18001a305  sub     rsp, 140h
0x18001a30c  mov     rax, cs:__security_cookie
0x18001a313  xor     rax, rsp
0x18001a316  mov     [rbp+70h+var_40], rax
0x18001a31a  mov     rbx, rdx
0x18001a31d  mov     r14, rcx
0x18001a320  xorps   xmm0, xmm0
0x18001a323  movups  [rsp+170h+var_130], xmm0
0x18001a328  movups  [rsp+170h+var_120], xmm0
0x18001a32d  movups  [rsp+170h+var_110], xmm0
0x18001a332  xor     r15d, r15d
0x18001a335  mov     dword ptr [rsp+170h+var_130+0Ch], r15d
0x18001a33a  mov     byte ptr [rsp+170h+var_130], r8b
0x18001a33f  lea     rcx, [rbp+70h+var_C0]
0x18001a343  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001a348  nop
0x18001a349  lea     r8, [rbp+70h+var_C0]
0x18001a34d  lea     rdx, qword_18003C520
0x18001a354  mov     rcx, rbx
0x18001a357  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a35c  test    eax, eax
0x18001a35e  jz      short loc_18001A373
0x18001a360  lea     r8, [rbp+70h+var_C0]
0x18001a364  lea     rdx, qword_18003C520
0x18001a36b  mov     rcx, rbx
0x18001a36e  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a373  lea     rcx, [rbp+70h+var_C0]
0x18001a377  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a37c  mov     rcx, rax
0x18001a37f  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001a384  mov     qword ptr [rsp+170h+var_120], rax
0x18001a389  lea     rcx, [rbp+70h+var_E0]
0x18001a38d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001a392  nop
0x18001a393  lea     r8, [rbp+70h+var_E0]
0x18001a397  lea     rdx, aFriendlyname; "FriendlyName"
0x18001a39e  mov     rcx, rbx
0x18001a3a1  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a3a6  mov     edi, eax
0x18001a3a8  lea     r12, WPP_GLOBAL_Control
0x18001a3af  lea     r13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001a3b6  test    eax, eax
0x18001a3b8  jz      short loc_18001A435
0x18001a3ba  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001a3c1  jz      short loc_18001A3FC
0x18001a3c3  mov     [rsp+170h+var_140], dil
0x18001a3c8  lea     rax, [rsp+170h+var_140]
0x18001a3cd  mov     [rbp+70h+var_F0], rax
0x18001a3d1  mov     [rbp+70h+var_E8], 1
0x18001a3d9  lea     rax, [rsp+170h+var_100]
0x18001a3de  mov     [rsp+170h+var_150], rax
0x18001a3e3  mov     r9d, 2
0x18001a3e9  lea     rdx, MUIReadFailed
0x18001a3f0  lea     rcx, eaphost_Context
0x18001a3f7  call    McGenEventWrite_EtwEventWriteTransfer
0x18001a3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a403  cmp     rcx, r12
0x18001a406  jz      short loc_18001A422
0x18001a408  test    byte ptr [rcx+1Ch], 4
0x18001a40c  jz      short loc_18001A422
0x18001a40e  mov     edx, 13h
0x18001a413  mov     r9d, edi
0x18001a416  mov     r8, r13
0x18001a419  mov     rcx, [rcx+10h]
0x18001a41d  call    WPP_SF_d
0x18001a422  lea     r8, [rbp+70h+var_E0]
0x18001a426  lea     rdx, aFriendlyname; "FriendlyName"
0x18001a42d  mov     rcx, rbx
0x18001a430  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a435  cmp     [rbp+70h+var_D0], r15
0x18001a439  jz      short loc_18001A4A2
0x18001a43b  cmp     [rbp+70h+var_B0], r15
0x18001a43f  jnz     short loc_18001A459
0x18001a441  lea     rcx, [rbp+70h+var_E0]
0x18001a445  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a44a  mov     rcx, rax
0x18001a44d  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001a452  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001a457  jmp     short loc_18001A4A2
0x18001a459  lea     rdx, [rbp+70h+var_C0]
0x18001a45d  lea     rcx, [rbp+70h+var_A0]
0x18001a461  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001a466  nop
0x18001a467  lea     r8, [rbp+70h+var_E0]
0x18001a46b  mov     rdx, rax
0x18001a46e  lea     rcx, [rsp+170h+var_100]
0x18001a473  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001a478  nop
0x18001a479  mov     rcx, rax
0x18001a47c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a481  mov     rcx, rax
0x18001a484  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001a489  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001a48e  lea     rcx, [rsp+170h+var_100]
0x18001a493  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a498  nop
0x18001a499  lea     rcx, [rbp+70h+var_A0]
0x18001a49d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a4a2  mov     dword ptr [rsp+170h+var_138], r15d
0x18001a4a7  lea     r8, [rsp+170h+var_138]
0x18001a4ac  lea     rdx, aProperties; "Properties"
0x18001a4b3  mov     rcx, rbx
0x18001a4b6  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a4bb  test    eax, eax
0x18001a4bd  jnz     short loc_18001A4CC
0x18001a4bf  mov     eax, dword ptr [rsp+170h+var_138]
0x18001a4c3  mov     dword ptr [rsp+170h+var_110], eax
0x18001a4c7  jmp     loc_18001A552
0x18001a4cc  lea     rcx, [rsp+170h+var_100]
0x18001a4d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001a4d6  nop
0x18001a4d7  lea     rcx, [r14+28h]
0x18001a4db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a4e0  lea     r8, [rsp+170h+var_100]
0x18001a4e5  mov     rdx, rax
0x18001a4e8  mov     rcx, rbx
0x18001a4eb  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a4f0  cmp     [rbp+70h+var_F0], r15
0x18001a4f4  jz      short loc_18001A4FC
0x18001a4f6  bts     dword ptr [rsp+170h+var_110], 15h
0x18001a4fc  mov     dword ptr [rsp+170h+var_138], r15d
0x18001a501  lea     r8, [rsp+170h+var_138]
0x18001a506  lea     rdx, aStandalonesupp; "StandaloneSupported"
0x18001a50d  mov     rcx, rbx
0x18001a510  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a515  cmp     dword ptr [rsp+170h+var_138], r15d
0x18001a51a  jz      short loc_18001A522
0x18001a51c  bts     dword ptr [rsp+170h+var_110], 12h
0x18001a522  mov     dword ptr [rsp+170h+var_138], r15d
0x18001a527  lea     r8, [rsp+170h+var_138]
0x18001a52c  lea     rdx, aMppeencryption; "MPPEEncryptionSupported"
0x18001a533  mov     rcx, rbx
0x18001a536  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a53b  cmp     dword ptr [rsp+170h+var_138], r15d
0x18001a540  jz      short loc_18001A548
0x18001a542  bts     dword ptr [rsp+170h+var_110], 13h
0x18001a548  lea     rcx, [rsp+170h+var_100]
0x18001a54d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a552  mov     esi, 3
0x18001a557  mov     dword ptr [rsp+170h+var_138], r15d
0x18001a55c  lea     r8, [rsp+170h+var_138]
0x18001a561  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18001a568  mov     rcx, rbx
0x18001a56b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a570  mov     edi, dword ptr [rsp+170h+var_138]
0x18001a574  test    edi, edi
0x18001a576  jz      short loc_18001A59E
0x18001a578  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a57f  cmp     rcx, r12
0x18001a582  jz      short loc_18001A59C
0x18001a584  test    byte ptr [rcx+1Ch], 4
0x18001a588  jz      short loc_18001A59C
0x18001a58a  lea     edx, [rsi+11h]
0x18001a58d  mov     r9d, edi
0x18001a590  mov     r8, r13
0x18001a593  mov     rcx, [rcx+10h]
0x18001a597  call    WPP_SF_d
0x18001a59c  mov     esi, edi
0x18001a59e  mov     rax, [r14]
0x18001a5a1  mov     r9, rbx
0x18001a5a4  mov     r8d, esi
0x18001a5a7  lea     rdx, [rsp+170h+var_130]
0x18001a5ac  mov     rcx, r14
0x18001a5af  mov     rax, [rax+38h]
0x18001a5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5b8  test    al, al
0x18001a5ba  jnz     short loc_18001A60A
0x18001a5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5c3  cmp     rcx, r12
0x18001a5c6  jz      short loc_18001A5E6
0x18001a5c8  test    byte ptr [rcx+1Ch], 4
0x18001a5cc  jz      short loc_18001A5E6
0x18001a5ce  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001a5d4  mov     edx, 15h
0x18001a5d9  mov     r8, r13
0x18001a5dc  mov     rcx, [rcx+10h]
0x18001a5e0  call    WPP_SF_d
0x18001a5e5  nop
0x18001a5e6  lea     rcx, [rbp+70h+var_E0]
0x18001a5ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a5ef  nop
0x18001a5f0  lea     rcx, [rbp+70h+var_C0]
0x18001a5f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a5f9  nop
0x18001a5fa  lea     rcx, [rsp+170h+var_130]
0x18001a5ff  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001a604  nop
0x18001a605  jmp     loc_18001A729
0x18001a60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a611  cmp     rcx, r12
0x18001a614  jz      short loc_18001A63B
0x18001a616  test    byte ptr [rcx+1Ch], 4
0x18001a61a  jz      short loc_18001A63B
0x18001a61c  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001a622  mov     edx, 16h
0x18001a627  mov     eax, dword ptr [rsp+170h+var_130+0Ch]
0x18001a62b  mov     dword ptr [rsp+170h+var_150], eax
0x18001a62f  mov     r8, r13
0x18001a632  mov     rcx, [rcx+10h]
0x18001a636  call    WPP_SF_dd
0x18001a63b  mov     [rbp+70h+var_A0], r15
0x18001a63f  mov     [rsp+170h+var_138], r15
0x18001a644  lea     rdx, [rsp+170h+var_138]
0x18001a649  lea     rcx, [rbp+70h+var_A0]
0x18001a64d  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18001a652  mov     [rbp+70h+var_98], esi
0x18001a655  lea     rdx, [r14+50h]
0x18001a659  lea     rcx, [rsp+170h+var_138]
0x18001a65e  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001a663  nop
0x18001a664  lea     r8, [rbp+70h+var_A0]
0x18001a668  lea     rdx, [rsp+170h+var_130]
0x18001a66d  lea     rcx, [rbp+70h+var_80]
0x18001a671  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18001a676  nop
0x18001a677  lea     rcx, [r14+88h]
0x18001a67e  mov     r8, rax
0x18001a681  lea     rdx, [rsp+170h+var_100]
0x18001a686  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18001a68b  nop
0x18001a68c  lea     rcx, [rbp+70h+var_80]
0x18001a690  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18001a695  cmp     [rsp+170h+var_F8], r15b
0x18001a69a  jz      short loc_18001A6C1
0x18001a69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6a3  cmp     rcx, r12
0x18001a6a6  jz      short loc_18001A6EB
0x18001a6a8  test    byte ptr [rcx+1Ch], 4
0x18001a6ac  jz      short loc_18001A6EB
0x18001a6ae  mov     edx, 17h
0x18001a6b3  mov     r8, r13
0x18001a6b6  mov     rcx, [rcx+10h]
0x18001a6ba  call    WPP_SF_
0x18001a6bf  jmp     short loc_18001A6EB
0x18001a6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6c8  cmp     rcx, r12
0x18001a6cb  jz      short loc_18001A6EB
0x18001a6cd  test    byte ptr [rcx+1Ch], 1
0x18001a6d1  jz      short loc_18001A6EB
0x18001a6d3  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001a6d9  mov     edx, 18h
0x18001a6de  mov     r8, r13
0x18001a6e1  mov     rcx, [rcx+10h]
0x18001a6e5  call    WPP_SF_d
0x18001a6ea  nop
0x18001a6eb  mov     rcx, [rsp+170h+var_138]
0x18001a6f0  add     rcx, 10h; lpCriticalSection
0x18001a6f4  call    cs:__imp_LeaveCriticalSection
0x18001a6fa  nop
0x18001a6fb  mov     rcx, [rbp+70h+var_A0]; this
0x18001a6ff  test    rcx, rcx
0x18001a702  jz      short loc_18001A70A
0x18001a704  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18001a709  nop
0x18001a70a  lea     rcx, [rbp+70h+var_E0]
0x18001a70e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a713  nop
0x18001a714  lea     rcx, [rbp+70h+var_C0]
0x18001a718  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a71d  nop
0x18001a71e  lea     rcx, [rsp+170h+var_130]
0x18001a723  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001a728  nop
0x18001a729  mov     rcx, [rbp+70h+var_40]
0x18001a72d  xor     rcx, rsp; StackCookie
0x18001a730  call    __security_check_cookie
0x18001a735  mov     rbx, [rsp+170h+arg_18]
0x18001a73d  add     rsp, 140h
0x18001a744  pop     r15
0x18001a746  pop     r14
0x18001a748  pop     r13
0x18001a74a  pop     r12
0x18001a74c  pop     rdi
0x18001a74d  pop     rsi
0x18001a74e  pop     rbp
0x18001a74f  retn
```
