# MdmLogCollector::CollectTpmHighLevelInfo(void)

- ea: `0x18010d45c`
- end: `0x18010d970`
- name: `?CollectTpmHighLevelInfo@MdmLogCollector@@AEAAJXZ`
- size: `1300`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1801089c0`
- `0x18010d45c`
- `0x18010f704`
- `0x180110974`
- `0x1801109fc`
- `0x180111118`
- `0x18013ca0c`
- `0x18013cb98`
- `0x18013cf74`
- `0x18013d9c0`
- `0x18013e304`
- `0x18013e784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d527`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d527`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d93b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d93b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d4eb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d4eb`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetFirmwareType` at `0x18010d6e0`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetFirmwareType` at `0x18010d6e0`

## string_xrefs

- `0x18010d49f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d74e`: `TpmHLI IsReady for Storage result: 0x%08x\n`
- `0x18010d781`: `Ready: %s\n`
- `0x18010d876`: `Ready: %s\n`
- `0x18010d851`: `TpmHLI IsReady for Attestation result: 0x%08x\n`

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
      (void *)0x7E9,
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
0x18010d45c  push    rbp
0x18010d45e  push    rbx
0x18010d45f  push    rdi
0x18010d460  push    r13
0x18010d462  lea     rbp, [rsp-3Fh]
0x18010d467  sub     rsp, 0E8h
0x18010d46e  mov     rax, cs:__security_cookie
0x18010d475  xor     rax, rsp
0x18010d478  mov     [rbp+57h+var_28], rax
0x18010d47c  mov     rdi, rcx
0x18010d47f  lea     rcx, [rbp+57h+var_88]
0x18010d483  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010d488  nop
0x18010d489  lea     rdx, [rbp+57h+var_88]
0x18010d48d  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010d492  mov     ebx, eax
0x18010d494  test    eax, eax
0x18010d496  jns     short loc_18010D4C1
0x18010d498  mov     rcx, [rbp+5Fh]; this
0x18010d49c  mov     r9d, eax; char *
0x18010d49f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010d4a6  mov     edx, 7E9h; void *
0x18010d4ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d4b0  nop
0x18010d4b1  lea     rcx, [rbp+57h+var_88]
0x18010d4b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d4ba  mov     eax, ebx
0x18010d4bc  jmp     loc_18010D957
0x18010d4c1  lea     rdx, [rbp+57h+var_88]
0x18010d4c5  lea     rcx, [rbp+57h+var_A8]
0x18010d4c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010d4ce  nop
0x18010d4cf  lea     rdx, aTpmhliinfoOutp; "\\TpmHliInfo_Output.txt"
0x18010d4d6  lea     rcx, [rbp+57h+var_A8]
0x18010d4da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010d4df  lea     rcx, [rbp+57h+var_A8]
0x18010d4e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d4e8  mov     rcx, rax; lpFileName
0x18010d4eb  call    cs:__imp_DeleteFileW
0x18010d4f1  lea     rcx, [rbp+57h+var_A8]
0x18010d4f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d4fa  mov     rcx, rax
0x18010d4fd  lea     rdx, [rdi+20h]
0x18010d501  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010d506  mov     [rsp+100h+Stream], 0
0x18010d50f  lea     rcx, [rbp+57h+var_A8]
0x18010d513  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d518  mov     rdx, rax; FileName
0x18010d51b  lea     r8, aA; "a+"
0x18010d522  lea     rcx, [rsp+100h+Stream]; Stream
0x18010d527  call    cs:__imp__wfopen_s
0x18010d52d  mov     [rbp+57h+var_C4], eax
0x18010d530  lea     rax, [rbp+57h+var_C4]
0x18010d534  mov     [rbp+57h+var_C0], rax
0x18010d538  lea     rax, [rsp+100h+Stream]
0x18010d53d  mov     [rbp+57h+var_B8], rax
0x18010d541  mov     [rbp+57h+var_B0], 1
0x18010d545  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d54a  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010d54f  lea     rdx, asc_1801B9CF8; "\n"
0x18010d556  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d55b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d560  mov     [rbp+57h+var_C8], 0
0x18010d567  lea     rax, ?WinPlatformGetMemory@@YAPEAX_K@Z; WinPlatformGetMemory(unsigned __int64)
0x18010d56e  mov     cs:?g_fpGetMemory@@3P6APEAX_K@ZEA, rax; void * (*g_fpGetMemory)(unsigned __int64)
0x18010d575  lea     rax, ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18010d57c  mov     cs:?g_fpFreeMemory@@3P6AXPEAX@ZEA, rax; void (*g_fpFreeMemory)(void *)
0x18010d583  lea     rax, ?WinPlatformIdle@@YAXK@Z; WinPlatformIdle(ulong)
0x18010d58a  mov     cs:?g_fpIdle@@3P6AXK@ZEA, rax; void (*g_fpIdle)(ulong)
0x18010d591  lea     rax, ?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z; WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)
0x18010d598  mov     cs:?g_fpTpmSubmit@@3P6AIQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpTpmSubmit)(uchar * const,uint,uchar *,uint *)
0x18010d59f  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x18010d5a6  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x18010d5ad  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x18010d5b4  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x18010d5bb  lea     rax, ?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z; WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)
0x18010d5c2  mov     cs:?g_fpSha1Hash@@3P6AJPEAEI0I0I@ZEA, rax; long (*g_fpSha1Hash)(uchar *,uint,uchar *,uint,uchar *,uint)
0x18010d5c9  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18010d5d0  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x18010d5d7  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010d5de  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010d5e5  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010d5ec  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x18010d5f3  mov     dword ptr [rbp+57h+var_D0], 0
0x18010d5fa  lea     rcx, [rbp+57h+var_48]
0x18010d5fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010d603  nop
0x18010d604  lea     r8, [rbp+57h+var_48]
0x18010d608  lea     rdx, [rbp+57h+var_D0]
0x18010d60c  lea     rcx, [rbp+57h+var_C8]
0x18010d610  call    ?GetVersion@TrustedPlatformModule@@QEAAJPEAW4TpmVersion@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrustedPlatformModule::GetVersion(TpmVersion *,std::wstring *)
0x18010d615  mov     ebx, eax
0x18010d617  mov     r8d, eax
0x18010d61a  lea     rdx, aTpmhliGetversi; "TpmHLI GetVersion result: 0x%08x\n"
0x18010d621  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d626  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d62b  test    ebx, ebx
0x18010d62d  js      loc_18010D72A
0x18010d633  cmp     dword ptr [rbp+57h+var_D0], 0
0x18010d637  jbe     short loc_18010D658
0x18010d639  lea     rcx, [rbp+57h+var_48]
0x18010d63d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d642  mov     r8, rax
0x18010d645  lea     rdx, aTpmhliVersionS; "TpmHLI Version: %s\n"
0x18010d64c  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d651  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d656  jmp     short loc_18010D669
0x18010d658  lea     rdx, aWarningUnknown; "Warning! Unknown TPM Version detected!"...
0x18010d65f  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d664  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d669  lea     rcx, [rbp+57h+var_C8]; this
0x18010d66d  call    ?GetManufacturerID@TrustedPlatformModule@@QEAAIXZ; TrustedPlatformModule::GetManufacturerID(void)
0x18010d672  mov     edx, eax
0x18010d674  lea     rcx, [rbp+57h+var_68]
0x18010d678  call    ?GetManufacturerName@HWSecurityBooster@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityBooster::GetManufacturerName(uint)
0x18010d67d  lea     rcx, [rbp+57h+var_68]
0x18010d681  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d686  mov     r8, rax
0x18010d689  lea     rdx, aManufacturerS; "Manufacturer: %s\n"
0x18010d690  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d695  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d69a  lea     rcx, [rbp+57h+var_68]
0x18010d69e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d6a3  lea     rdx, [rbp+57h+var_68]
0x18010d6a7  lea     rcx, [rbp+57h+var_C8]; this
0x18010d6ab  call    ?GetVendorIDString@TrustedPlatformModule@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; TrustedPlatformModule::GetVendorIDString(void)
0x18010d6b0  mov     rcx, rax
0x18010d6b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d6b8  mov     r8, rax
0x18010d6bb  lea     rdx, aVendoridS; "VendorId: %s\n"
0x18010d6c2  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d6c7  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d6cc  lea     rcx, [rbp+57h+var_68]
0x18010d6d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d6d5  mov     dword ptr [rbp+57h+var_D0], 0
0x18010d6dc  lea     rcx, [rbp+57h+var_D0]
0x18010d6e0  call    cs:__imp_GetFirmwareType
0x18010d6e6  mov     rcx, [rbp+5Fh]; this
0x18010d6ea  test    eax, eax
0x18010d6ec  jnz     short loc_18010D6FE
0x18010d6ee  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\trus"...
0x18010d6f5  lea     edx, [rax+11h]; void *
0x18010d6f8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18010d6fe  cmp     dword ptr [rbp+57h+var_D0], 2
0x18010d702  setz    al
0x18010d705  lea     rcx, aNo; "No"
0x18010d70c  lea     r8, aYes; "Yes"
0x18010d713  test    al, al
0x18010d715  cmovz   r8, rcx
0x18010d719  lea     rdx, aUefiIsPresentS; "Uefi Is Present: %s\n"
0x18010d720  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d725  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d72a  mov     byte ptr [rsp+100h+var_E0], 0
0x18010d72f  xor     eax, eax
0x18010d731  mov     [rbp+57h+var_D0], rax
0x18010d735  lea     r9, [rbp+57h+var_D0]
0x18010d739  lea     r8, [rsp+100h+var_E0]
0x18010d73e  xor     edx, edx
0x18010d740  lea     rcx, [rbp+57h+var_C8]
0x18010d744  call    ?IsReady@TrustedPlatformModule@@QEAAJW4IsReadySpecifier@@AEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReady(IsReadySpecifier,bool &,std::bitset<64> *)
0x18010d749  mov     ebx, eax
0x18010d74b  mov     r8d, eax
0x18010d74e  lea     rdx, aTpmhliIsreadyF; "TpmHLI IsReady for Storage result: 0x%0"...
0x18010d755  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d75a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d75f  lea     rdi, aTrue_1; "True"
0x18010d766  lea     r13, aFalse_2; "False"
0x18010d76d  test    ebx, ebx
0x18010d76f  js      loc_18010D830
0x18010d775  mov     r8, rdi
0x18010d778  cmp     byte ptr [rsp+100h+var_E0], 0
0x18010d77d  cmovz   r8, r13
0x18010d781  lea     rdx, aReadyS; "Ready: %s\n"
0x18010d788  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d78d  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d792  mov     r8, [rbp+57h+var_D0]
0x18010d796  lea     rdx, aBits0x016x; "Bits:  0x%016X\n"
0x18010d79d  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d7a2  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d7a7  xor     edx, edx
0x18010d7a9  lea     rcx, [rbp+57h+var_D0]
0x18010d7ad  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d7b2  test    al, al
0x18010d7b4  jz      short loc_18010D7C7
0x18010d7b6  lea     rdx, aNotcgeventlogN; "  -NoTcgEventLog: No TCG event log foun"...
0x18010d7bd  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d7c2  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d7c7  mov     edx, 1
0x18010d7cc  lea     rcx, [rbp+57h+var_D0]
0x18010d7d0  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d7d5  test    al, al
0x18010d7d7  jz      short loc_18010D7EA
0x18010d7d9  lea     rdx, aNovalidekcertN; "  -NoValidEkCert: No valid EK cert foun"...
0x18010d7e0  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d7e5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d7ea  mov     edx, 2
0x18010d7ef  lea     rcx, [rbp+57h+var_D0]
0x18010d7f3  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d7f8  test    al, al
0x18010d7fa  jz      short loc_18010D80D
0x18010d7fc  lea     rdx, aLostauthsTheOw; "  -LostAuths: The OwnerAuth and Endorse"...
0x18010d803  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d808  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d80d  mov     edx, 3
0x18010d812  lea     rcx, [rbp+57h+var_D0]
0x18010d816  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d81b  test    al, al
0x18010d81d  jz      short loc_18010D830
0x18010d81f  lea     rdx, aSrknotpresentT; "  -SrkNotPresent: The Storage Root Key "...
0x18010d826  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d82b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d830  mov     byte ptr [rsp+100h+var_E0], 0
0x18010d835  lea     r9, [rbp+57h+var_D0]
0x18010d839  lea     r8, [rsp+100h+var_E0]
0x18010d83e  mov     edx, 1
0x18010d843  lea     rcx, [rbp+57h+var_C8]
0x18010d847  call    ?IsReady@TrustedPlatformModule@@QEAAJW4IsReadySpecifier@@AEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReady(IsReadySpecifier,bool &,std::bitset<64> *)
0x18010d84c  mov     ebx, eax
0x18010d84e  mov     r8d, eax
0x18010d851  lea     rdx, aTpmhliIsreadyF_0; "TpmHLI IsReady for Attestation result: "...
0x18010d858  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d85d  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d862  test    ebx, ebx
0x18010d864  js      loc_18010D926
0x18010d86a  cmp     byte ptr [rsp+100h+var_E0], 0
0x18010d86f  cmovz   rdi, r13
0x18010d873  mov     r8, rdi
0x18010d876  lea     rdx, aReadyS; "Ready: %s\n"
0x18010d87d  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d882  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d887  mov     r8, [rbp+57h+var_D0]
0x18010d88b  lea     rdx, aBits0x016x; "Bits:  0x%016X\n"
0x18010d892  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d897  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d89c  xor     edx, edx
0x18010d89e  lea     rcx, [rbp+57h+var_D0]
0x18010d8a2  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d8a7  test    al, al
0x18010d8a9  jz      short loc_18010D8BC
0x18010d8ab  lea     rdx, aNotcgeventlogN; "  -NoTcgEventLog: No TCG event log foun"...
0x18010d8b2  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d8b7  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d8bc  mov     edx, 1
0x18010d8c1  lea     rcx, [rbp+57h+var_D0]
0x18010d8c5  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d8ca  test    al, al
0x18010d8cc  jz      short loc_18010D8DF
0x18010d8ce  lea     rdx, aNovalidekcertN; "  -NoValidEkCert: No valid EK cert foun"...
0x18010d8d5  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d8da  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d8df  mov     edx, 2
0x18010d8e4  lea     rcx, [rbp+57h+var_D0]
0x18010d8e8  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d8ed  test    al, al
0x18010d8ef  jz      short loc_18010D902
0x18010d8f1  lea     rdx, aLostauthsTheOw; "  -LostAuths: The OwnerAuth and Endorse"...
0x18010d8f8  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d8fd  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d902  mov     edx, 3
0x18010d907  lea     rcx, [rbp+57h+var_D0]
0x18010d90b  call    ?_Subscript@?$bitset@$0EA@@std@@AEBA_N_K@Z; std::bitset<64>::_Subscript(unsigned __int64)
0x18010d910  test    al, al
0x18010d912  jz      short loc_18010D926
0x18010d914  lea     rdx, aSrknotpresentT; "  -SrkNotPresent: The Storage Root Key "...
0x18010d91b  mov     rcx, [rsp+100h+Stream]; struct _iobuf *
0x18010d920  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d925  nop
0x18010d926  lea     rcx, [rbp+57h+var_48]
0x18010d92a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d92f  nop
0x18010d930  cmp     [rbp+57h+var_C4], 0
0x18010d934  jnz     short loc_18010D942
0x18010d936  mov     rcx, [rsp+100h+Stream]; Stream
0x18010d93b  call    cs:__imp_fclose
0x18010d941  nop
0x18010d942  lea     rcx, [rbp+57h+var_A8]
0x18010d946  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d94b  nop
0x18010d94c  lea     rcx, [rbp+57h+var_88]
0x18010d950  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d955  xor     eax, eax
0x18010d957  mov     rcx, [rbp+57h+var_28]
0x18010d95b  xor     rcx, rsp; StackCookie
0x18010d95e  call    __security_check_cookie
0x18010d963  add     rsp, 0E8h
0x18010d96a  pop     r13
0x18010d96c  pop     rdi
0x18010d96d  pop     rbx
0x18010d96e  pop     rbp
0x18010d96f  retn
```
