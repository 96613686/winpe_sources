# EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)

- ea: `0x18001acdc`
- end: `0x18001b143`
- name: `?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z`
- size: `1127`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this, const struct RegistryKey *, unsigned __int8)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001bc10`
- `0x18001c0a8`

## callees

- `0x180002af0`
- `0x1800040a8`
- `0x180004af8`
- `0x1800056cc`
- `0x180009fe4`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000a4d4`
- `0x180011218`
- `0x18001204c`
- `0x18001206c`
- `0x180019f30`
- `0x180019f70`
- `0x180019fb0`
- `0x18001a560`
- `0x18001a838`
- `0x18001a918`
- `0x18001acdc`
- `0x180030b08`
- `0x1800314c4`
- `0x18003165c`
- `0x180031778`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b0e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b0e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  __int64 v11; // r8
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  unsigned int v21; // esi
  unsigned int v22; // edi
  __int64 v23; // rax
  char v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+60h] [rbp-A0h]
  _BYTE v29[16]; // [rsp+70h] [rbp-90h] BYREF
  char *v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  _BYTE v32[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  _BYTE v34[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-40h]
  ReferenceCounted *v36; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp-28h]
  _BYTE v38[64]; // [rsp+F0h] [rbp-10h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  HIDWORD(v26) = 0;
  LOBYTE(v26) = a3;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v34,
    a2,
    a3,
    a4);
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, &qword_18003D520, v34) )
    RegistryKey::QueryValue(a2, &qword_18003D520, v34);
  v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
  *(_QWORD *)&v27 = BasicSimpleString<wchar_t>::Copy(v6);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v32,
    v7,
    v8,
    v9);
  MuiString = RegistryKey::ReadMuiString(a2, L"FriendlyName", v32);
  v12 = MuiString;
  if ( MuiString )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      v24 = MuiString;
      v30 = &v24;
      v31 = 1;
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)MUIReadFailed, v11, 2, (__int64)v29);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v12);
    }
    RegistryKey::QueryValue(a2, L"FriendlyName", v32);
  }
  if ( v33 )
  {
    if ( v35 )
    {
      v14 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v36, v34);
      v15 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v29, v14, v32);
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v15);
      *((_QWORD *)&v27 + 1) = BasicSimpleString<wchar_t>::Copy(v16);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v29);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v36);
    }
    else
    {
      v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v32);
      *((_QWORD *)&v27 + 1) = BasicSimpleString<wchar_t>::Copy(v13);
    }
  }
  LODWORD(v25) = 0;
  if ( (unsigned int)RegistryKey::QueryValue(a2, L"Properties", &v25) )
  {
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
      v29,
      v17,
      v18,
      v19);
    v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 40);
    RegistryKey::QueryValue(a2, v20, v29);
    if ( v30 )
      LODWORD(v28) = v28 | 0x200000;
    LODWORD(v25) = 0;
    RegistryKey::QueryValue(a2, L"StandaloneSupported", &v25);
    if ( (_DWORD)v25 )
      LODWORD(v28) = v28 | 0x40000;
    LODWORD(v25) = 0;
    RegistryKey::QueryValue(a2, L"MPPEEncryptionSupported", &v25);
    if ( (_DWORD)v25 )
      LODWORD(v28) = v28 | 0x80000;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v29);
  }
  else
  {
    LODWORD(v28) = v25;
  }
  v21 = 3;
  LODWORD(v25) = 0;
  RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v25);
  v22 = v25;
  if ( (_DWORD)v25 )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned int)v25);
    }
    v21 = v22;
  }
  if ( (*(unsigned __int8 (__fastcall **)(EapLm::BaseEapLibraryManager *, __int128 *, _QWORD, const struct RegistryKey *))(*(_QWORD *)this + 56LL))(
         this,
         &v26,
         v21,
         a2) )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v26,
        HIDWORD(v26));
    }
    v36 = 0;
    v25 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v36, &v25);
    v37 = v21;
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v25, (char *)this + 80);
    v23 = std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(
            v38,
            &v26,
            &v36);
    std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(
      (char *)this + 136,
      v29,
      v23);
    std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(v38);
    if ( v29[8] )
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
        (unsigned __int8)v26);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 16));
    if ( v36 )
      ReferenceCounted::Release(v36);
  }
  else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v26);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v32);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v34);
  Free<HeapAllocator>(&v26);
}

```

## disassembly

```asm
0x18001acdc  mov     [rsp-8+arg_18], rbx
0x18001ace1  push    rbp
0x18001ace2  push    rsi
0x18001ace3  push    rdi
0x18001ace4  push    r12
0x18001ace6  push    r13
0x18001ace8  push    r14
0x18001acea  push    r15
0x18001acec  lea     rbp, [rsp-40h]
0x18001acf1  sub     rsp, 140h
0x18001acf8  mov     rax, cs:__security_cookie
0x18001acff  xor     rax, rsp
0x18001ad02  mov     [rbp+70h+var_40], rax
0x18001ad06  mov     rbx, rdx
0x18001ad09  mov     r14, rcx
0x18001ad0c  xorps   xmm0, xmm0
0x18001ad0f  movups  [rsp+170h+var_130], xmm0
0x18001ad14  movups  [rsp+170h+var_120], xmm0
0x18001ad19  movups  [rsp+170h+var_110], xmm0
0x18001ad1e  xor     r15d, r15d
0x18001ad21  mov     dword ptr [rsp+170h+var_130+0Ch], r15d
0x18001ad26  mov     byte ptr [rsp+170h+var_130], r8b
0x18001ad2b  lea     rcx, [rbp+70h+var_C0]
0x18001ad2f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001ad34  nop
0x18001ad35  lea     r8, [rbp+70h+var_C0]
0x18001ad39  lea     rdx, qword_18003D520
0x18001ad40  mov     rcx, rbx
0x18001ad43  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ad48  test    eax, eax
0x18001ad4a  jz      short loc_18001AD5F
0x18001ad4c  lea     r8, [rbp+70h+var_C0]
0x18001ad50  lea     rdx, qword_18003D520
0x18001ad57  mov     rcx, rbx
0x18001ad5a  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ad5f  lea     rcx, [rbp+70h+var_C0]
0x18001ad63  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ad68  mov     rcx, rax
0x18001ad6b  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001ad70  mov     qword ptr [rsp+170h+var_120], rax
0x18001ad75  lea     rcx, [rbp+70h+var_E0]
0x18001ad79  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001ad7e  nop
0x18001ad7f  lea     r8, [rbp+70h+var_E0]
0x18001ad83  lea     rdx, aFriendlyname; "FriendlyName"
0x18001ad8a  mov     rcx, rbx
0x18001ad8d  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ad92  mov     edi, eax
0x18001ad94  lea     r12, WPP_GLOBAL_Control
0x18001ad9b  lea     r13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001ada2  test    eax, eax
0x18001ada4  jz      short loc_18001AE21
0x18001ada6  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001adad  jz      short loc_18001ADE8
0x18001adaf  mov     [rsp+170h+var_140], dil
0x18001adb4  lea     rax, [rsp+170h+var_140]
0x18001adb9  mov     [rbp+70h+var_F0], rax
0x18001adbd  mov     [rbp+70h+var_E8], 1
0x18001adc5  lea     rax, [rsp+170h+var_100]
0x18001adca  mov     [rsp+170h+var_150], rax
0x18001adcf  mov     r9d, 2
0x18001add5  lea     rdx, MUIReadFailed
0x18001addc  lea     rcx, eaphost_Context
0x18001ade3  call    McGenEventWrite_EtwEventWriteTransfer
0x18001ade8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adef  cmp     rcx, r12
0x18001adf2  jz      short loc_18001AE0E
0x18001adf4  test    byte ptr [rcx+1Ch], 4
0x18001adf8  jz      short loc_18001AE0E
0x18001adfa  mov     edx, 13h
0x18001adff  mov     r9d, edi
0x18001ae02  mov     r8, r13
0x18001ae05  mov     rcx, [rcx+10h]
0x18001ae09  call    WPP_SF_d
0x18001ae0e  lea     r8, [rbp+70h+var_E0]
0x18001ae12  lea     rdx, aFriendlyname; "FriendlyName"
0x18001ae19  mov     rcx, rbx
0x18001ae1c  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ae21  cmp     [rbp+70h+var_D0], r15
0x18001ae25  jz      short loc_18001AE8E
0x18001ae27  cmp     [rbp+70h+var_B0], r15
0x18001ae2b  jnz     short loc_18001AE45
0x18001ae2d  lea     rcx, [rbp+70h+var_E0]
0x18001ae31  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ae36  mov     rcx, rax
0x18001ae39  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001ae3e  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001ae43  jmp     short loc_18001AE8E
0x18001ae45  lea     rdx, [rbp+70h+var_C0]
0x18001ae49  lea     rcx, [rbp+70h+var_A0]
0x18001ae4d  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001ae52  nop
0x18001ae53  lea     r8, [rbp+70h+var_E0]
0x18001ae57  mov     rdx, rax
0x18001ae5a  lea     rcx, [rsp+170h+var_100]
0x18001ae5f  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001ae64  nop
0x18001ae65  mov     rcx, rax
0x18001ae68  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ae6d  mov     rcx, rax
0x18001ae70  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001ae75  mov     qword ptr [rsp+170h+var_120+8], rax
0x18001ae7a  lea     rcx, [rsp+170h+var_100]
0x18001ae7f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ae84  nop
0x18001ae85  lea     rcx, [rbp+70h+var_A0]
0x18001ae89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ae8e  mov     dword ptr [rsp+170h+var_138], r15d
0x18001ae93  lea     r8, [rsp+170h+var_138]
0x18001ae98  lea     rdx, aProperties; "Properties"
0x18001ae9f  mov     rcx, rbx
0x18001aea2  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001aea7  test    eax, eax
0x18001aea9  jnz     short loc_18001AEB8
0x18001aeab  mov     eax, dword ptr [rsp+170h+var_138]
0x18001aeaf  mov     dword ptr [rsp+170h+var_110], eax
0x18001aeb3  jmp     loc_18001AF3E
0x18001aeb8  lea     rcx, [rsp+170h+var_100]
0x18001aebd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001aec2  nop
0x18001aec3  lea     rcx, [r14+28h]
0x18001aec7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001aecc  lea     r8, [rsp+170h+var_100]
0x18001aed1  mov     rdx, rax
0x18001aed4  mov     rcx, rbx
0x18001aed7  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001aedc  cmp     [rbp+70h+var_F0], r15
0x18001aee0  jz      short loc_18001AEE8
0x18001aee2  bts     dword ptr [rsp+170h+var_110], 15h
0x18001aee8  mov     dword ptr [rsp+170h+var_138], r15d
0x18001aeed  lea     r8, [rsp+170h+var_138]
0x18001aef2  lea     rdx, aStandalonesupp; "StandaloneSupported"
0x18001aef9  mov     rcx, rbx
0x18001aefc  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001af01  cmp     dword ptr [rsp+170h+var_138], r15d
0x18001af06  jz      short loc_18001AF0E
0x18001af08  bts     dword ptr [rsp+170h+var_110], 12h
0x18001af0e  mov     dword ptr [rsp+170h+var_138], r15d
0x18001af13  lea     r8, [rsp+170h+var_138]
0x18001af18  lea     rdx, aMppeencryption; "MPPEEncryptionSupported"
0x18001af1f  mov     rcx, rbx
0x18001af22  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001af27  cmp     dword ptr [rsp+170h+var_138], r15d
0x18001af2c  jz      short loc_18001AF34
0x18001af2e  bts     dword ptr [rsp+170h+var_110], 13h
0x18001af34  lea     rcx, [rsp+170h+var_100]
0x18001af39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001af3e  mov     esi, 3
0x18001af43  mov     dword ptr [rsp+170h+var_138], r15d
0x18001af48  lea     r8, [rsp+170h+var_138]
0x18001af4d  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18001af54  mov     rcx, rbx
0x18001af57  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001af5c  mov     edi, dword ptr [rsp+170h+var_138]
0x18001af60  test    edi, edi
0x18001af62  jz      short loc_18001AF8A
0x18001af64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af6b  cmp     rcx, r12
0x18001af6e  jz      short loc_18001AF88
0x18001af70  test    byte ptr [rcx+1Ch], 4
0x18001af74  jz      short loc_18001AF88
0x18001af76  lea     edx, [rsi+11h]
0x18001af79  mov     r9d, edi
0x18001af7c  mov     r8, r13
0x18001af7f  mov     rcx, [rcx+10h]
0x18001af83  call    WPP_SF_d
0x18001af88  mov     esi, edi
0x18001af8a  mov     rax, [r14]
0x18001af8d  mov     r9, rbx
0x18001af90  mov     r8d, esi
0x18001af93  lea     rdx, [rsp+170h+var_130]
0x18001af98  mov     rcx, r14
0x18001af9b  mov     rax, [rax+38h]
0x18001af9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afa4  test    al, al
0x18001afa6  jnz     short loc_18001AFF6
0x18001afa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afaf  cmp     rcx, r12
0x18001afb2  jz      short loc_18001AFD2
0x18001afb4  test    byte ptr [rcx+1Ch], 4
0x18001afb8  jz      short loc_18001AFD2
0x18001afba  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001afc0  mov     edx, 15h
0x18001afc5  mov     r8, r13
0x18001afc8  mov     rcx, [rcx+10h]
0x18001afcc  call    WPP_SF_d
0x18001afd1  nop
0x18001afd2  lea     rcx, [rbp+70h+var_E0]
0x18001afd6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001afdb  nop
0x18001afdc  lea     rcx, [rbp+70h+var_C0]
0x18001afe0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001afe5  nop
0x18001afe6  lea     rcx, [rsp+170h+var_130]
0x18001afeb  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001aff0  nop
0x18001aff1  jmp     loc_18001B11B
0x18001aff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001affd  cmp     rcx, r12
0x18001b000  jz      short loc_18001B027
0x18001b002  test    byte ptr [rcx+1Ch], 4
0x18001b006  jz      short loc_18001B027
0x18001b008  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001b00e  mov     edx, 16h
0x18001b013  mov     eax, dword ptr [rsp+170h+var_130+0Ch]
0x18001b017  mov     dword ptr [rsp+170h+var_150], eax
0x18001b01b  mov     r8, r13
0x18001b01e  mov     rcx, [rcx+10h]
0x18001b022  call    WPP_SF_dd
0x18001b027  mov     [rbp+70h+var_A0], r15
0x18001b02b  mov     [rsp+170h+var_138], r15
0x18001b030  lea     rdx, [rsp+170h+var_138]
0x18001b035  lea     rcx, [rbp+70h+var_A0]
0x18001b039  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18001b03e  mov     [rbp+70h+var_98], esi
0x18001b041  lea     rdx, [r14+50h]
0x18001b045  lea     rcx, [rsp+170h+var_138]
0x18001b04a  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001b04f  nop
0x18001b050  lea     r8, [rbp+70h+var_A0]
0x18001b054  lea     rdx, [rsp+170h+var_130]
0x18001b059  lea     rcx, [rbp+70h+var_80]
0x18001b05d  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18001b062  nop
0x18001b063  lea     rcx, [r14+88h]
0x18001b06a  mov     r8, rax
0x18001b06d  lea     rdx, [rsp+170h+var_100]
0x18001b072  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18001b077  nop
0x18001b078  lea     rcx, [rbp+70h+var_80]
0x18001b07c  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18001b081  cmp     [rsp+170h+var_F8], r15b
0x18001b086  jz      short loc_18001B0AD
0x18001b088  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b08f  cmp     rcx, r12
0x18001b092  jz      short loc_18001B0D7
0x18001b094  test    byte ptr [rcx+1Ch], 4
0x18001b098  jz      short loc_18001B0D7
0x18001b09a  mov     edx, 17h
0x18001b09f  mov     r8, r13
0x18001b0a2  mov     rcx, [rcx+10h]
0x18001b0a6  call    WPP_SF_
0x18001b0ab  jmp     short loc_18001B0D7
0x18001b0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0b4  cmp     rcx, r12
0x18001b0b7  jz      short loc_18001B0D7
0x18001b0b9  test    byte ptr [rcx+1Ch], 1
0x18001b0bd  jz      short loc_18001B0D7
0x18001b0bf  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18001b0c5  mov     edx, 18h
0x18001b0ca  mov     r8, r13
0x18001b0cd  mov     rcx, [rcx+10h]
0x18001b0d1  call    WPP_SF_d
0x18001b0d6  nop
0x18001b0d7  mov     rcx, [rsp+170h+var_138]
0x18001b0dc  add     rcx, 10h; lpCriticalSection
0x18001b0e0  call    cs:__imp_LeaveCriticalSection
0x18001b0e7  nop     dword ptr [rax+rax+00h]
0x18001b0ec  nop
0x18001b0ed  mov     rcx, [rbp+70h+var_A0]; this
0x18001b0f1  test    rcx, rcx
0x18001b0f4  jz      short loc_18001B0FC
0x18001b0f6  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18001b0fb  nop
0x18001b0fc  lea     rcx, [rbp+70h+var_E0]
0x18001b100  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b105  nop
0x18001b106  lea     rcx, [rbp+70h+var_C0]
0x18001b10a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b10f  nop
0x18001b110  lea     rcx, [rsp+170h+var_130]
0x18001b115  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001b11a  nop
0x18001b11b  mov     rcx, [rbp+70h+var_40]
0x18001b11f  xor     rcx, rsp; StackCookie
0x18001b122  call    __security_check_cookie
0x18001b127  mov     rbx, [rsp+170h+arg_18]
0x18001b12f  add     rsp, 140h
0x18001b136  pop     r15
0x18001b138  pop     r14
0x18001b13a  pop     r13
0x18001b13c  pop     r12
0x18001b13e  pop     rdi
0x18001b13f  pop     rsi
0x18001b140  pop     rbp
0x18001b141  retn
```
