# MdmLogCollector::CollectTpmHighLevelInfo(void)

- ea: `0x18010e984`
- end: `0x18010eeb1`
- name: `?CollectTpmHighLevelInfo@MdmLogCollector@@AEAAJXZ`
- size: `1325`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180109d50`
- `0x18010e984`
- `0x180110d34`
- `0x180111e34`
- `0x180111ec4`
- `0x1801125a4`
- `0x18013ed74`
- `0x18013ef00`
- `0x18013f2e4`
- `0x18013fdcc`
- `0x180140720`
- `0x180140ba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010ea55`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010ea55`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010ee75`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010ee75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010ea13`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010ea13`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetFirmwareType` at `0x18010ec14`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetFirmwareType` at `0x18010ec14`

## string_xrefs

- `0x18010e9c7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ec88`: `TpmHLI IsReady for Storage result: 0x%08x\n`
- `0x18010ecbb`: `Ready: %s\n`
- `0x18010edb0`: `Ready: %s\n`
- `0x18010ed8b`: `TpmHLI IsReady for Attestation result: 0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmLogCollector::CollectTpmHighLevelInfo(MdmLogCollector *this)
{
  __int64 v2; // rcx
  int TemporaryOutputPath; // eax
  unsigned int v4; // ebx
  const WCHAR *v6; // rax
  __int64 v7; // rax
  const wchar_t *v8; // rax
  __int64 Version; // rbx
  __int64 v10; // rax
  unsigned int ManufacturerID; // eax
  __int64 v12; // rax
  __int64 VendorIDString; // rax
  __int64 v14; // rax
  const char *v15; // r9
  const wchar_t *v16; // r8
  __int64 IsReady; // rbx
  const wchar_t *v18; // rdi
  const wchar_t *v19; // r8
  __int64 v20; // rbx
  int v21; // [rsp+20h] [rbp-89h] BYREF
  FILE *Stream; // [rsp+28h] [rbp-81h] BYREF
  __int64 v23; // [rsp+30h] [rbp-79h] BYREF
  int v24; // [rsp+38h] [rbp-71h] BYREF
  errno_t v25; // [rsp+3Ch] [rbp-6Dh] BYREF
  errno_t *v26; // [rsp+40h] [rbp-69h]
  FILE **p_Stream; // [rsp+48h] [rbp-61h]
  char v28; // [rsp+50h] [rbp-59h]
  _BYTE v29[32]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v31[32]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v32[32]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  std::wstring::wstring(v30);
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v2, v30);
  v4 = TemporaryOutputPath;
  if ( TemporaryOutputPath >= 0 )
  {
    std::wstring::wstring(v29, v30);
    std::wstring::append(v29, L"\\TpmHliInfo_Output.txt");
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    DeleteFileW(v6);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    MdmLogCollector::AddEntry(v7, (char *)this + 32);
    Stream = 0;
    v8 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v25 = _wfopen_s(&Stream, v8, L"a+");
    v26 = &v25;
    p_Stream = &Stream;
    v28 = 1;
    MdmLogCollector::WriteSystemTime(Stream);
    MdmLogCollector::WriteToFile(Stream, L"\n");
    v24 = 0;
    g_fpGetMemory = (void *(*)(unsigned __int64))WinPlatformGetMemory;
    g_fpFreeMemory = (void (*)(void *))wil::details::FreeProcessHeap;
    g_fpIdle = WinPlatformIdle;
    g_fpTpmSubmit = (unsigned int (*)(unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *))WinPlatformTbsSubmit;
    g_fpW8TpmSubmit = WinPlatformW8TbsSubmit;
    g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))WinPlatformGetRandom;
    g_fpSha1Hash = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))WinPlatformSha1Hash;
    g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))WinPlatformHash;
    g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
    g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
    LODWORD(v23) = 0;
    std::wstring::wstring(v32);
    Version = (unsigned int)TrustedPlatformModule::GetVersion(&v24, &v23, v32);
    MdmLogCollector::WriteToFile(Stream, L"TpmHLI GetVersion result: 0x%08x\n", Version);
    if ( (int)Version >= 0 )
    {
      if ( (_DWORD)v23 )
      {
        v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
        MdmLogCollector::WriteToFile(Stream, L"TpmHLI Version: %s\n", v10);
      }
      else
      {
        MdmLogCollector::WriteToFile(Stream, L"Warning! Unknown TPM Version detected!\n");
      }
      ManufacturerID = TrustedPlatformModule::GetManufacturerID((TrustedPlatformModule *)&v24);
      HWSecurityBooster::GetManufacturerName(v31, ManufacturerID);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
      MdmLogCollector::WriteToFile(Stream, L"Manufacturer: %s\n", v12);
      std::wstring::_Tidy_deallocate(v31);
      VendorIDString = TrustedPlatformModule::GetVendorIDString((TrustedPlatformModule *)&v24);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(VendorIDString);
      MdmLogCollector::WriteToFile(Stream, L"VendorId: %s\n", v14);
      std::wstring::_Tidy_deallocate(v31);
      LODWORD(v23) = 0;
      if ( !(unsigned int)GetFirmwareType(&v23) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x11,
          (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\trustedplatformproperties.cpp",
          v15);
      v16 = L"Yes";
      if ( (_DWORD)v23 != 2 )
        v16 = L"No";
      MdmLogCollector::WriteToFile(Stream, L"Uefi Is Present: %s\n", v16);
    }
    LOBYTE(v21) = 0;
    v23 = 0;
    IsReady = (unsigned int)TrustedPlatformModule::IsReady(&v24, 0, &v21, &v23);
    MdmLogCollector::WriteToFile(Stream, L"TpmHLI IsReady for Storage result: 0x%08x\n", IsReady);
    v18 = L"True";
    if ( (int)IsReady >= 0 )
    {
      v19 = L"True";
      if ( !(_BYTE)v21 )
        v19 = L"False";
      MdmLogCollector::WriteToFile(Stream, L"Ready: %s\n", v19);
      MdmLogCollector::WriteToFile(Stream, L"Bits:  0x%016X\n", v23);
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 0) )
        MdmLogCollector::WriteToFile(Stream, L"  -NoTcgEventLog: No TCG event log found\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 1) )
        MdmLogCollector::WriteToFile(Stream, L"  -NoValidEkCert: No valid EK cert found\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 2) )
        MdmLogCollector::WriteToFile(
          Stream,
          L"  -LostAuths: The OwnerAuth and EndorsementAuth have been set and are not available\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 3) )
        MdmLogCollector::WriteToFile(Stream, L"  -SrkNotPresent: The Storage Root Key (SRK) is not found\n");
    }
    LOBYTE(v21) = 0;
    v20 = (unsigned int)TrustedPlatformModule::IsReady(&v24, 1, &v21, &v23);
    MdmLogCollector::WriteToFile(Stream, L"TpmHLI IsReady for Attestation result: 0x%08x\n", v20);
    if ( (int)v20 >= 0 )
    {
      if ( !(_BYTE)v21 )
        v18 = L"False";
      MdmLogCollector::WriteToFile(Stream, L"Ready: %s\n", v18);
      MdmLogCollector::WriteToFile(Stream, L"Bits:  0x%016X\n", v23);
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 0) )
        MdmLogCollector::WriteToFile(Stream, L"  -NoTcgEventLog: No TCG event log found\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 1) )
        MdmLogCollector::WriteToFile(Stream, L"  -NoValidEkCert: No valid EK cert found\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 2) )
        MdmLogCollector::WriteToFile(
          Stream,
          L"  -LostAuths: The OwnerAuth and EndorsementAuth have been set and are not available\n");
      if ( (unsigned __int8)std::bitset<64>::_Subscript(&v23, 3) )
        MdmLogCollector::WriteToFile(Stream, L"  -SrkNotPresent: The Storage Root Key (SRK) is not found\n");
    }
    std::wstring::_Tidy_deallocate(v32);
    if ( !v25 )
      fclose(Stream);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)TemporaryOutputPath,
      v21);
    std::wstring::_Tidy_deallocate(v30);
    return v4;
  }
}

```

## disassembly

```asm
0x18010e984  push    rbp
0x18010e986  push    rbx
0x18010e987  push    rdi
0x18010e988  push    r13
0x18010e98a  lea     rbp, [rsp-3Fh]
0x18010e98f  sub     rsp, 0E8h
0x18010e996  mov     rax, cs:__security_cookie
0x18010e99d  xor     rax, rsp
0x18010e9a0  mov     [rbp+57h+var_28], rax
0x18010e9a4  mov     rdi, rcx
0x18010e9a7  lea     rcx, [rbp+57h+var_88]
0x18010e9ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010e9b0  nop
0x18010e9b1  lea     rdx, [rbp+57h+var_88]
0x18010e9b5  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010e9ba  mov     ebx, eax
0x18010e9bc  test    eax, eax
0x18010e9be  jns     short loc_18010E9E9
0x18010e9c0  mov     rcx, [rbp+5Fh]; this
0x18010e9c4  mov     r9d, eax; char *
0x18010e9c7  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e9ce  mov     edx, 7C0h; void *
0x18010e9d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e9d8  nop
0x18010e9d9  lea     rcx, [rbp+57h+var_88]
0x18010e9dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e9e2  mov     eax, ebx
0x18010e9e4  jmp     loc_18010EE97
0x18010e9e9  lea     rdx, [rbp+57h+var_88]
0x18010e9ed  lea     rcx, [rbp+57h+var_A8]
0x18010e9f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010e9f6  nop
0x18010e9f7  lea     rdx, aTpmhliinfoOutp; "\\TpmHliInfo_Output.txt"
0x18010e9fe  lea     rcx, [rbp+57h+var_A8]
0x18010ea02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010ea07  lea     rcx, [rbp+57h+var_A8]
0x18010ea0b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ea10  mov     rcx, rax; lpFileName
0x18010ea13  call    cs:__imp_DeleteFileW
0x18010ea1a  nop     dword ptr [rax+rax+00h]
0x18010ea1f  lea     rcx, [rbp+57h+var_A8]
0x18010ea23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ea28  mov     rcx, rax
0x18010ea2b  lea     rdx, [rdi+20h]
0x18010ea2f  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010ea34  mov     [rsp+100h+Stream], 0
0x18010ea3d  lea     rcx, [rbp+57h+var_A8]
0x18010ea41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ea46  mov     rdx, rax; FileName
0x18010ea49  lea     r8, aA; "a+"
0x18010ea50  lea     rcx, [rsp+100h+Stream]; Stream
0x18010ea55  call    cs:__imp__wfopen_s
0x18010ea5c  nop     dword ptr [rax+rax+00h]
0x18010ea61  mov     [rbp+57h+var_C4], eax
0x18010ea64  lea     rax, [rbp+57h+var_C4]
0x18010ea68  mov     [rbp+57h+var_C0], rax
0x18010ea6c  lea     rax, [rsp+100h+Stream]
0x18010ea71  mov     [rbp+57h+var_B8], rax
0x18010ea75  mov     [rbp+57h+var_B0], 1
0x18010ea79  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ea7e  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010ea83  lea     rdx, asc_1801BBCF8; "\n"
0x18010ea8a  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ea8f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ea94  mov     [rbp+57h+var_C8], 0
0x18010ea9b  lea     rax, ?WinPlatformGetMemory@@YAPEAX_K@Z; WinPlatformGetMemory(unsigned __int64)
0x18010eaa2  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x18010eaa9  lea     rax, ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18010eab0  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x18010eab7  lea     rax, ?WinPlatformIdle@@YAXK@Z; WinPlatformIdle(ulong)
0x18010eabe  mov     cs:?g_fpIdle@@3P6AXK@ZEA, rax; void (*g_fpIdle)(ulong)
0x18010eac5  lea     rax, ?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z; WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)
0x18010eacc  mov     cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x18010ead3  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x18010eada  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x18010eae1  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x18010eae8  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x18010eaef  lea     rax, ?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z; WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)
0x18010eaf6  mov     cs:?g_fpSha1Hash@@3P6AJPEAEI0I0I@ZEA, rax; long (*g_fpSha1Hash)(uchar *,uint,uchar *,uint,uchar *,uint)
0x18010eafd  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18010eb04  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18010eb0b  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010eb12  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010eb19  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010eb20  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010eb27  mov     dword ptr [rbp+57h+var_D0], 0
0x18010eb2e  lea     rcx, [rbp+57h+var_48]
0x18010eb32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010eb37  nop
0x18010eb38  lea     r8, [rbp+57h+var_48]
0x18010eb3c  lea     rdx, [rbp+57h+var_D0]
0x18010eb40  lea     rcx, [rbp+57h+var_C8]
0x18010eb44  call    ?GetVersion@TrustedPlatformModule@@QEAAJPEAW4TpmVersion@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrustedPlatformModule::GetVersion(TpmVersion *,std::wstring *)
0x18010eb49  mov     ebx, eax
0x18010eb4b  mov     r8d, eax
0x18010eb4e  lea     rdx, aTpmhliGetversi; "TpmHLI GetVersion result: 0x%08x\n"
0x18010eb55  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010eb5a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010eb5f  test    ebx, ebx
0x18010eb61  js      loc_18010EC64
0x18010eb67  cmp     dword ptr [rbp+57h+var_D0], 0
0x18010eb6b  jbe     short loc_18010EB8C
0x18010eb6d  lea     rcx, [rbp+57h+var_48]
0x18010eb71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010eb76  mov     r8, rax
0x18010eb79  lea     rdx, aTpmhliVersionS; "TpmHLI Version: %s\n"
0x18010eb80  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010eb85  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010eb8a  jmp     short loc_18010EB9D
0x18010eb8c  lea     rdx, aWarningUnknown; "Warning! Unknown TPM Version detected!"...
0x18010eb93  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010eb98  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010eb9d  lea     rcx, [rbp+57h+var_C8]; this
0x18010eba1  call    ?GetManufacturerID@TrustedPlatformModule@@QEAAIXZ; TrustedPlatformModule::GetManufacturerID(void)
0x18010eba6  mov     edx, eax
0x18010eba8  lea     rcx, [rbp+57h+var_68]
0x18010ebac  call    ?GetManufacturerName@HWSecurityBooster@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityBooster::GetManufacturerName(uint)
0x18010ebb1  lea     rcx, [rbp+57h+var_68]
0x18010ebb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ebba  mov     r8, rax
0x18010ebbd  lea     rdx, aManufacturerS; "Manufacturer: %s\n"
0x18010ebc4  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ebc9  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ebce  lea     rcx, [rbp+57h+var_68]
0x18010ebd2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ebd7  lea     rdx, [rbp+57h+var_68]
0x18010ebdb  lea     rcx, [rbp+57h+var_C8]; this
0x18010ebdf  call    ?GetVendorIDString@TrustedPlatformModule@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; TrustedPlatformModule::GetVendorIDString(void)
0x18010ebe4  mov     rcx, rax
0x18010ebe7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ebec  mov     r8, rax
0x18010ebef  lea     rdx, aVendoridS; "VendorId: %s\n"
0x18010ebf6  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ebfb  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ec00  lea     rcx, [rbp+57h+var_68]
0x18010ec04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ec09  mov     dword ptr [rbp+57h+var_D0], 0
0x18010ec10  lea     rcx, [rbp+57h+var_D0]
0x18010ec14  call    cs:__imp_GetFirmwareType
0x18010ec1b  nop     dword ptr [rax+rax+00h]
0x18010ec20  mov     rcx, [rbp+5Fh]; this
0x18010ec24  test    eax, eax
0x18010ec26  jnz     short loc_18010EC38
0x18010ec28  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\trus"...
0x18010ec2f  lea     edx, [rax+11h]; void *
0x18010ec32  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18010ec38  cmp     dword ptr [rbp+57h+var_D0], 2
0x18010ec3c  setz    al
0x18010ec3f  lea     rcx, aNo; "No"
0x18010ec46  lea     r8, aYes; "Yes"
0x18010ec4d  test    al, al
0x18010ec4f  cmovz   r8, rcx
0x18010ec53  lea     rdx, aUefiIsPresentS; "Uefi Is Present: %s\n"
0x18010ec5a  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ec5f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ec64  mov     byte ptr [rsp+100h+var_E0], 0
0x18010ec69  xor     eax, eax
0x18010ec6b  mov     [rbp+57h+var_D0], rax
0x18010ec6f  lea     r9, [rbp+57h+var_D0]
0x18010ec73  lea     r8, [rsp+100h+var_E0]
0x18010ec78  xor     edx, edx
0x18010ec7a  lea     rcx, [rbp+57h+var_C8]
0x18010ec7e  call    ?IsReady@TrustedPlatformModule@@QEAAJW4IsReadySpecifier@@AEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReady(IsReadySpecifier,bool &,std::bitset<64> *)
0x18010ec83  mov     ebx, eax
0x18010ec85  mov     r8d, eax
0x18010ec88  lea     rdx, aTpmhliIsreadyF; "TpmHLI IsReady for Storage result: 0x%0"...
0x18010ec8f  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ec94  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ec99  lea     rdi, aTrue_1; "True"
0x18010eca0  lea     r13, aFalse_2; "False"
0x18010eca7  test    ebx, ebx
0x18010eca9  js      loc_18010ED6A
0x18010ecaf  mov     r8, rdi
0x18010ecb2  cmp     byte ptr [rsp+100h+var_E0], 0
0x18010ecb7  cmovz   r8, r13
0x18010ecbb  lea     rdx, aReadyS; "Ready: %s\n"
0x18010ecc2  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ecc7  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010eccc  mov     r8, [rbp+57h+var_D0]
0x18010ecd0  lea     rdx, aBits0x016x; "Bits:  0x%016X\n"
0x18010ecd7  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ecdc  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ece1  xor     edx, edx
0x18010ece3  lea     rcx, [rbp+57h+var_D0]
0x18010ece7  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ecec  test    al, al
0x18010ecee  jz      short loc_18010ED01
0x18010ecf0  lea     rdx, aNotcgeventlogN; "  -NoTcgEventLog: No TCG event log foun"...
0x18010ecf7  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ecfc  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed01  mov     edx, 1
0x18010ed06  lea     rcx, [rbp+57h+var_D0]
0x18010ed0a  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ed0f  test    al, al
0x18010ed11  jz      short loc_18010ED24
0x18010ed13  lea     rdx, aNovalidekcertN; "  -NoValidEkCert: No valid EK cert foun"...
0x18010ed1a  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ed1f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed24  mov     edx, 2
0x18010ed29  lea     rcx, [rbp+57h+var_D0]
0x18010ed2d  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ed32  test    al, al
0x18010ed34  jz      short loc_18010ED47
0x18010ed36  lea     rdx, aLostauthsTheOw; "  -LostAuths: The OwnerAuth and Endorse"...
0x18010ed3d  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ed42  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed47  mov     edx, 3
0x18010ed4c  lea     rcx, [rbp+57h+var_D0]
0x18010ed50  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ed55  test    al, al
0x18010ed57  jz      short loc_18010ED6A
0x18010ed59  lea     rdx, aSrknotpresentT; "  -SrkNotPresent: The Storage Root Key "...
0x18010ed60  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ed65  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed6a  mov     byte ptr [rsp+100h+var_E0], 0
0x18010ed6f  lea     r9, [rbp+57h+var_D0]
0x18010ed73  lea     r8, [rsp+100h+var_E0]
0x18010ed78  mov     edx, 1
0x18010ed7d  lea     rcx, [rbp+57h+var_C8]
0x18010ed81  call    ?IsReady@TrustedPlatformModule@@QEAAJW4IsReadySpecifier@@AEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReady(IsReadySpecifier,bool &,std::bitset<64> *)
0x18010ed86  mov     ebx, eax
0x18010ed88  mov     r8d, eax
0x18010ed8b  lea     rdx, aTpmhliIsreadyF_0; "TpmHLI IsReady for Attestation result: "...
0x18010ed92  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ed97  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed9c  test    ebx, ebx
0x18010ed9e  js      loc_18010EE60
0x18010eda4  cmp     byte ptr [rsp+100h+var_E0], 0
0x18010eda9  cmovz   rdi, r13
0x18010edad  mov     r8, rdi
0x18010edb0  lea     rdx, aReadyS; "Ready: %s\n"
0x18010edb7  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010edbc  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010edc1  mov     r8, [rbp+57h+var_D0]
0x18010edc5  lea     rdx, aBits0x016x; "Bits:  0x%016X\n"
0x18010edcc  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010edd1  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010edd6  xor     edx, edx
0x18010edd8  lea     rcx, [rbp+57h+var_D0]
0x18010eddc  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ede1  test    al, al
0x18010ede3  jz      short loc_18010EDF6
0x18010ede5  lea     rdx, aNotcgeventlogN; "  -NoTcgEventLog: No TCG event log foun"...
0x18010edec  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010edf1  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010edf6  mov     edx, 1
0x18010edfb  lea     rcx, [rbp+57h+var_D0]
0x18010edff  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ee04  test    al, al
0x18010ee06  jz      short loc_18010EE19
0x18010ee08  lea     rdx, aNovalidekcertN; "  -NoValidEkCert: No valid EK cert foun"...
0x18010ee0f  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ee14  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ee19  mov     edx, 2
0x18010ee1e  lea     rcx, [rbp+57h+var_D0]
0x18010ee22  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ee27  test    al, al
0x18010ee29  jz      short loc_18010EE3C
0x18010ee2b  lea     rdx, aLostauthsTheOw; "  -LostAuths: The OwnerAuth and Endorse"...
0x18010ee32  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ee37  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ee3c  mov     edx, 3
0x18010ee41  lea     rcx, [rbp+57h+var_D0]
0x18010ee45  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010ee4a  test    al, al
0x18010ee4c  jz      short loc_18010EE60
0x18010ee4e  lea     rdx, aSrknotpresentT; "  -SrkNotPresent: The Storage Root Key "...
0x18010ee55  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010ee5a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ee5f  nop
0x18010ee60  lea     rcx, [rbp+57h+var_48]
0x18010ee64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ee69  nop
0x18010ee6a  cmp     [rbp+57h+var_C4], 0
0x18010ee6e  jnz     short loc_18010EE82
0x18010ee70  mov     rcx, [rsp+100h+Stream]; Stream
0x18010ee75  call    cs:__imp_fclose
0x18010ee7c  nop     dword ptr [rax+rax+00h]
0x18010ee81  nop
0x18010ee82  lea     rcx, [rbp+57h+var_A8]
0x18010ee86  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ee8b  nop
0x18010ee8c  lea     rcx, [rbp+57h+var_88]
0x18010ee90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ee95  xor     eax, eax
0x18010ee97  mov     rcx, [rbp+57h+var_28]
0x18010ee9b  xor     rcx, rsp; StackCookie
0x18010ee9e  call    __security_check_cookie
0x18010eea3  add     rsp, 0E8h
0x18010eeaa  pop     r13
0x18010eeac  pop     rdi
0x18010eead  pop     rbx
0x18010eeae  pop     rbp
0x18010eeaf  retn
```
