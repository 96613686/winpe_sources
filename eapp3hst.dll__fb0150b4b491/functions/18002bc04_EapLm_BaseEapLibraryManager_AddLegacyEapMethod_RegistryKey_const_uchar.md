# EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)

- ea: `0x18002bc04`
- end: `0x18002c064`
- name: `?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z`
- size: `1120`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *this, const struct RegistryKey *, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002ca50`
- `0x18002cee8`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180006ccc`
- `0x18000bf94`
- `0x18000eb74`
- `0x18000eb94`
- `0x18000ec84`
- `0x180012c10`
- `0x180012d18`
- `0x180014ecc`
- `0x180016c54`
- `0x18002a974`
- `0x18002ab2c`
- `0x18002ac44`
- `0x18002b088`
- `0x18002b0c8`
- `0x18002b108`
- `0x18002b298`
- `0x18002b544`
- `0x18002b7d0`
- `0x18002b85c`
- `0x18002bc04`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c008`

## pseudocode

```c
void __fastcall EapLm::BaseEapLibraryManager::AddLegacyEapMethod(
        EapLm::BaseEapLibraryManager *this,
        const struct RegistryKey *a2,
        char a3)
{
  __int64 v5; // rax
  unsigned int MuiString; // eax
  int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // esi
  unsigned int v15; // edi
  __int64 v16; // rax
  char v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  _BYTE v22[16]; // [rsp+70h] [rbp-90h] BYREF
  char *v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  _BYTE v27[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-40h]
  ReferenceCounted *v29; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+D8h] [rbp-28h]
  _BYTE v31[64]; // [rsp+F0h] [rbp-10h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  HIDWORD(v19) = 0;
  LOBYTE(v19) = a3;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v27);
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, &qword_18003A720, v27) )
    RegistryKey::QueryValue(a2, &qword_18003A720, v27);
  v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
  *(_QWORD *)&v20 = BasicSimpleString<wchar_t>::Copy(v5);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v25);
  MuiString = RegistryKey::ReadMuiString(a2, L"FriendlyName", v25);
  v8 = MuiString;
  if ( MuiString )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      v17 = MuiString;
      v23 = &v17;
      v24 = 1;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)MUIReadFailed,
        v7,
        2,
        (__int64)v22);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v8);
    RegistryKey::QueryValue(a2, L"FriendlyName", v25);
  }
  if ( v26 )
  {
    if ( v28 )
    {
      v10 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v29, v27);
      v11 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v22, v10, v25);
      v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v11);
      *((_QWORD *)&v20 + 1) = BasicSimpleString<wchar_t>::Copy(v12);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v22);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v29);
    }
    else
    {
      v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
      *((_QWORD *)&v20 + 1) = BasicSimpleString<wchar_t>::Copy(v9);
    }
  }
  LODWORD(v18) = 0;
  if ( (unsigned int)RegistryKey::QueryValue(a2, L"Properties", &v18) )
  {
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v22);
    v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 40);
    RegistryKey::QueryValue(a2, v13, v22);
    if ( v23 )
      LODWORD(v21) = v21 | 0x200000;
    LODWORD(v18) = 0;
    RegistryKey::QueryValue(a2, L"StandaloneSupported", &v18);
    if ( (_DWORD)v18 )
      LODWORD(v21) = v21 | 0x40000;
    LODWORD(v18) = 0;
    RegistryKey::QueryValue(a2, L"MPPEEncryptionSupported", &v18);
    if ( (_DWORD)v18 )
      LODWORD(v21) = v21 | 0x80000;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v22);
  }
  else
  {
    LODWORD(v21) = v18;
  }
  v14 = 3;
  LODWORD(v18) = 0;
  RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v18);
  v15 = v18;
  if ( (_DWORD)v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned int)v18);
    v14 = v15;
  }
  if ( (*(unsigned __int8 (__fastcall **)(EapLm::BaseEapLibraryManager *, __int128 *, _QWORD, const struct RegistryKey *))(*(_QWORD *)this + 56LL))(
         this,
         &v19,
         v14,
         a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v19,
        HIDWORD(v19));
    v29 = 0;
    v18 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v29, &v18);
    v30 = v14;
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v18, (char *)this + 80);
    v16 = std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(
            v31,
            &v19,
            &v29);
    std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(
      (char *)this + 136,
      v22,
      v16);
    std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(v31);
    if ( v22[8] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v19);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    if ( v29 )
      ReferenceCounted::Release(v29);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v19);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v25);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v27);
  Free<HeapAllocator>(&v19);
}

```

## disassembly

```asm
0x18002bc04  mov     [rsp-8+arg_18], rbx
0x18002bc09  push    rbp
0x18002bc0a  push    rsi
0x18002bc0b  push    rdi
0x18002bc0c  push    r12
0x18002bc0e  push    r13
0x18002bc10  push    r14
0x18002bc12  push    r15
0x18002bc14  lea     rbp, [rsp-40h]
0x18002bc19  sub     rsp, 140h
0x18002bc20  mov     rax, cs:__security_cookie
0x18002bc27  xor     rax, rsp
0x18002bc2a  mov     [rbp+70h+var_40], rax
0x18002bc2e  mov     rbx, rdx
0x18002bc31  mov     r14, rcx
0x18002bc34  xorps   xmm0, xmm0
0x18002bc37  movups  [rsp+170h+var_130], xmm0
0x18002bc3c  movups  [rsp+170h+var_120], xmm0
0x18002bc41  movups  [rsp+170h+var_110], xmm0
0x18002bc46  xor     r15d, r15d
0x18002bc49  mov     dword ptr [rsp+170h+var_130+0Ch], r15d
0x18002bc4e  mov     byte ptr [rsp+170h+var_130], r8b
0x18002bc53  lea     rcx, [rbp+70h+var_C0]
0x18002bc57  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002bc5c  nop
0x18002bc5d  lea     r8, [rbp+70h+var_C0]
0x18002bc61  lea     rdx, qword_18003A720
0x18002bc68  mov     rcx, rbx
0x18002bc6b  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002bc70  test    eax, eax
0x18002bc72  jz      short loc_18002BC87
0x18002bc74  lea     r8, [rbp+70h+var_C0]
0x18002bc78  lea     rdx, qword_18003A720
0x18002bc7f  mov     rcx, rbx
0x18002bc82  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002bc87  lea     rcx, [rbp+70h+var_C0]
0x18002bc8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bc90  mov     rcx, rax
0x18002bc93  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18002bc98  mov     qword ptr [rsp+170h+var_120], rax
0x18002bc9d  lea     rcx, [rbp+70h+var_E0]
0x18002bca1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002bca6  nop
0x18002bca7  lea     r8, [rbp+70h+var_E0]
0x18002bcab  lea     rdx, aFriendlyname; "FriendlyName"
0x18002bcb2  mov     rcx, rbx
0x18002bcb5  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002bcba  mov     edi, eax
0x18002bcbc  lea     r12, WPP_GLOBAL_Control
0x18002bcc3  lea     r13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002bcca  test    eax, eax
0x18002bccc  jz      short loc_18002BD49
0x18002bcce  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18002bcd5  jz      short loc_18002BD10
0x18002bcd7  mov     [rsp+170h+var_140], dil
0x18002bcdc  lea     rax, [rsp+170h+var_140]
0x18002bce1  mov     [rbp+70h+var_F0], rax
0x18002bce5  mov     [rbp+70h+var_E8], 1
0x18002bced  lea     rax, [rsp+170h+var_100]
0x18002bcf2  mov     [rsp+170h+var_150], rax
0x18002bcf7  mov     r9d, 2
0x18002bcfd  lea     rdx, MUIReadFailed
0x18002bd04  lea     rcx, eaphost_Context
0x18002bd0b  call    McGenEventWrite_EtwEventWriteTransfer
0x18002bd10  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd17  cmp     rcx, r12
0x18002bd1a  jz      short loc_18002BD36
0x18002bd1c  test    byte ptr [rcx+1Ch], 4
0x18002bd20  jz      short loc_18002BD36
0x18002bd22  mov     edx, 13h
0x18002bd27  mov     r9d, edi
0x18002bd2a  mov     r8, r13
0x18002bd2d  mov     rcx, [rcx+10h]
0x18002bd31  call    WPP_SF_d
0x18002bd36  lea     r8, [rbp+70h+var_E0]
0x18002bd3a  lea     rdx, aFriendlyname; "FriendlyName"
0x18002bd41  mov     rcx, rbx
0x18002bd44  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002bd49  cmp     [rbp+70h+var_D0], r15
0x18002bd4d  jz      short loc_18002BDB6
0x18002bd4f  cmp     [rbp+70h+var_B0], r15
0x18002bd53  jnz     short loc_18002BD6D
0x18002bd55  lea     rcx, [rbp+70h+var_E0]
0x18002bd59  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bd5e  mov     rcx, rax
0x18002bd61  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18002bd66  mov     qword ptr [rsp+170h+var_120+8], rax
0x18002bd6b  jmp     short loc_18002BDB6
0x18002bd6d  lea     rdx, [rbp+70h+var_C0]
0x18002bd71  lea     rcx, [rbp+70h+var_A0]
0x18002bd75  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18002bd7a  nop
0x18002bd7b  lea     r8, [rbp+70h+var_E0]
0x18002bd7f  mov     rdx, rax
0x18002bd82  lea     rcx, [rsp+170h+var_100]
0x18002bd87  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002bd8c  nop
0x18002bd8d  mov     rcx, rax
0x18002bd90  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bd95  mov     rcx, rax
0x18002bd98  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18002bd9d  mov     qword ptr [rsp+170h+var_120+8], rax
0x18002bda2  lea     rcx, [rsp+170h+var_100]
0x18002bda7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002bdac  nop
0x18002bdad  lea     rcx, [rbp+70h+var_A0]
0x18002bdb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002bdb6  mov     dword ptr [rsp+170h+var_138], r15d
0x18002bdbb  lea     r8, [rsp+170h+var_138]
0x18002bdc0  lea     rdx, aProperties; "Properties"
0x18002bdc7  mov     rcx, rbx
0x18002bdca  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002bdcf  test    eax, eax
0x18002bdd1  jnz     short loc_18002BDE0
0x18002bdd3  mov     eax, dword ptr [rsp+170h+var_138]
0x18002bdd7  mov     dword ptr [rsp+170h+var_110], eax
0x18002bddb  jmp     loc_18002BE66
0x18002bde0  lea     rcx, [rsp+170h+var_100]
0x18002bde5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002bdea  nop
0x18002bdeb  lea     rcx, [r14+28h]
0x18002bdef  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bdf4  lea     r8, [rsp+170h+var_100]
0x18002bdf9  mov     rdx, rax
0x18002bdfc  mov     rcx, rbx
0x18002bdff  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002be04  cmp     [rbp+70h+var_F0], r15
0x18002be08  jz      short loc_18002BE10
0x18002be0a  bts     dword ptr [rsp+170h+var_110], 15h
0x18002be10  mov     dword ptr [rsp+170h+var_138], r15d
0x18002be15  lea     r8, [rsp+170h+var_138]
0x18002be1a  lea     rdx, aStandalonesupp; "StandaloneSupported"
0x18002be21  mov     rcx, rbx
0x18002be24  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002be29  cmp     dword ptr [rsp+170h+var_138], r15d
0x18002be2e  jz      short loc_18002BE36
0x18002be30  bts     dword ptr [rsp+170h+var_110], 12h
0x18002be36  mov     dword ptr [rsp+170h+var_138], r15d
0x18002be3b  lea     r8, [rsp+170h+var_138]
0x18002be40  lea     rdx, aMppeencryption; "MPPEEncryptionSupported"
0x18002be47  mov     rcx, rbx
0x18002be4a  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002be4f  cmp     dword ptr [rsp+170h+var_138], r15d
0x18002be54  jz      short loc_18002BE5C
0x18002be56  bts     dword ptr [rsp+170h+var_110], 13h
0x18002be5c  lea     rcx, [rsp+170h+var_100]
0x18002be61  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002be66  mov     esi, 3
0x18002be6b  mov     dword ptr [rsp+170h+var_138], r15d
0x18002be70  lea     r8, [rsp+170h+var_138]
0x18002be75  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18002be7c  mov     rcx, rbx
0x18002be7f  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002be84  mov     edi, dword ptr [rsp+170h+var_138]
0x18002be88  test    edi, edi
0x18002be8a  jz      short loc_18002BEB2
0x18002be8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be93  cmp     rcx, r12
0x18002be96  jz      short loc_18002BEB0
0x18002be98  test    byte ptr [rcx+1Ch], 4
0x18002be9c  jz      short loc_18002BEB0
0x18002be9e  lea     edx, [rsi+11h]
0x18002bea1  mov     r9d, edi
0x18002bea4  mov     r8, r13
0x18002bea7  mov     rcx, [rcx+10h]
0x18002beab  call    WPP_SF_d
0x18002beb0  mov     esi, edi
0x18002beb2  mov     rax, [r14]
0x18002beb5  mov     r9, rbx
0x18002beb8  mov     r8d, esi
0x18002bebb  lea     rdx, [rsp+170h+var_130]
0x18002bec0  mov     rcx, r14
0x18002bec3  mov     rax, [rax+38h]
0x18002bec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002becc  test    al, al
0x18002bece  jnz     short loc_18002BF1E
0x18002bed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bed7  cmp     rcx, r12
0x18002beda  jz      short loc_18002BEFA
0x18002bedc  test    byte ptr [rcx+1Ch], 4
0x18002bee0  jz      short loc_18002BEFA
0x18002bee2  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18002bee8  mov     edx, 15h
0x18002beed  mov     r8, r13
0x18002bef0  mov     rcx, [rcx+10h]
0x18002bef4  call    WPP_SF_d
0x18002bef9  nop
0x18002befa  lea     rcx, [rbp+70h+var_E0]
0x18002befe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002bf03  nop
0x18002bf04  lea     rcx, [rbp+70h+var_C0]
0x18002bf08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002bf0d  nop
0x18002bf0e  lea     rcx, [rsp+170h+var_130]
0x18002bf13  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002bf18  nop
0x18002bf19  jmp     loc_18002C03D
0x18002bf1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf25  cmp     rcx, r12
0x18002bf28  jz      short loc_18002BF4F
0x18002bf2a  test    byte ptr [rcx+1Ch], 4
0x18002bf2e  jz      short loc_18002BF4F
0x18002bf30  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18002bf36  mov     edx, 16h
0x18002bf3b  mov     eax, dword ptr [rsp+170h+var_130+0Ch]
0x18002bf3f  mov     dword ptr [rsp+170h+var_150], eax
0x18002bf43  mov     r8, r13
0x18002bf46  mov     rcx, [rcx+10h]
0x18002bf4a  call    WPP_SF_dd
0x18002bf4f  mov     [rbp+70h+var_A0], r15
0x18002bf53  mov     [rsp+170h+var_138], r15
0x18002bf58  lea     rdx, [rsp+170h+var_138]
0x18002bf5d  lea     rcx, [rbp+70h+var_A0]
0x18002bf61  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18002bf66  mov     [rbp+70h+var_98], esi
0x18002bf69  lea     rdx, [r14+50h]
0x18002bf6d  lea     rcx, [rsp+170h+var_138]
0x18002bf72  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18002bf77  nop
0x18002bf78  lea     r8, [rbp+70h+var_A0]
0x18002bf7c  lea     rdx, [rsp+170h+var_130]
0x18002bf81  lea     rcx, [rbp+70h+var_80]
0x18002bf85  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18002bf8a  nop
0x18002bf8b  lea     rcx, [r14+88h]
0x18002bf92  mov     r8, rax
0x18002bf95  lea     rdx, [rsp+170h+var_100]
0x18002bf9a  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18002bf9f  nop
0x18002bfa0  lea     rcx, [rbp+70h+var_80]
0x18002bfa4  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18002bfa9  cmp     [rsp+170h+var_F8], r15b
0x18002bfae  jz      short loc_18002BFD5
0x18002bfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfb7  cmp     rcx, r12
0x18002bfba  jz      short loc_18002BFFF
0x18002bfbc  test    byte ptr [rcx+1Ch], 4
0x18002bfc0  jz      short loc_18002BFFF
0x18002bfc2  mov     edx, 17h
0x18002bfc7  mov     r8, r13
0x18002bfca  mov     rcx, [rcx+10h]
0x18002bfce  call    WPP_SF_
0x18002bfd3  jmp     short loc_18002BFFF
0x18002bfd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfdc  cmp     rcx, r12
0x18002bfdf  jz      short loc_18002BFFF
0x18002bfe1  test    byte ptr [rcx+1Ch], 1
0x18002bfe5  jz      short loc_18002BFFF
0x18002bfe7  movzx   r9d, byte ptr [rsp+170h+var_130]
0x18002bfed  mov     edx, 18h
0x18002bff2  mov     r8, r13
0x18002bff5  mov     rcx, [rcx+10h]
0x18002bff9  call    WPP_SF_d
0x18002bffe  nop
0x18002bfff  mov     rcx, [rsp+170h+var_138]
0x18002c004  add     rcx, 10h; lpCriticalSection
0x18002c008  call    cs:__imp_LeaveCriticalSection
0x18002c00e  nop
0x18002c00f  mov     rcx, [rbp+70h+var_A0]; this
0x18002c013  test    rcx, rcx
0x18002c016  jz      short loc_18002C01E
0x18002c018  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002c01d  nop
0x18002c01e  lea     rcx, [rbp+70h+var_E0]
0x18002c022  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c027  nop
0x18002c028  lea     rcx, [rbp+70h+var_C0]
0x18002c02c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c031  nop
0x18002c032  lea     rcx, [rsp+170h+var_130]
0x18002c037  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002c03c  nop
0x18002c03d  mov     rcx, [rbp+70h+var_40]
0x18002c041  xor     rcx, rsp; StackCookie
0x18002c044  call    __security_check_cookie
0x18002c049  mov     rbx, [rsp+170h+arg_18]
0x18002c051  add     rsp, 140h
0x18002c058  pop     r15
0x18002c05a  pop     r14
0x18002c05c  pop     r13
0x18002c05e  pop     r12
0x18002c060  pop     rdi
0x18002c061  pop     rsi
0x18002c062  pop     rbp
0x18002c063  retn
```
