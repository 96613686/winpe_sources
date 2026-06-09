# MdmLogCollector::CollectUefiEntries(void)

- ea: `0x18010da60`
- end: `0x18010de70`
- name: `?CollectUefiEntries@MdmLogCollector@@AEAAJXZ`
- size: `1040`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f8a0c`
- `0x180104108`
- `0x180107f0c`
- `0x180107f2c`
- `0x1801089c0`
- `0x18010da60`
- `0x18010f704`
- `0x180110190`
- `0x180110974`
- `0x1801109fc`
- `0x1801111ec`
- `0x1801114b8`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010dbe0`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010dbe0`
- `ntdll!RtlAcquirePrivilege` at `0x18010dc66`
- `ntdll!RtlAcquirePrivilege` at `0x18010dc66`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010dba3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010dba3`

## string_xrefs

- `0x18010daed`: `DeviceLinkCreationTimeUtc`
- `0x18010dad9`: `DeviceLinkId`
- `0x18010db13`: `DeviceLinkJwtCompressed`
- `0x18010db2d`: `DeviceLinkJwtLastWrite`
- `0x18010db6c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010dbf1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010dc74`: `Failed to acquire UEFI privilege. Error: 0x%08X`
- `0x18010de0c`: `UEFI query complete.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MdmLogCollector::CollectUefiEntries(MdmLogCollector *this)
{
  __m128i si128; // xmm6
  int TemporaryOutputPath; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // rax
  __int64 v6; // rax
  const wchar_t *v7; // rax
  unsigned int v8; // eax
  NTSTATUS v9; // eax
  int IsUefiSupported; // eax
  _QWORD *v11; // rbx
  int v12; // eax
  __int64 v13; // rax
  char *v14; // rbx
  int v15; // eax
  __int64 v16; // rax
  __int64 v18; // [rsp+28h] [rbp-E0h] BYREF
  FILE *Stream; // [rsp+30h] [rbp-D8h] BYREF
  PVOID ReturnedState; // [rsp+38h] [rbp-D0h] BYREF
  ULONG Privilege[2]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v22[6]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v23[15]; // [rsp+78h] [rbp-90h] BYREF
  char v24; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v25; // [rsp+F8h] [rbp-10h] BYREF
  __m128i v26; // [rsp+108h] [rbp+0h]
  _BYTE v27[32]; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v28[2]; // [rsp+138h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v22[0] = L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}";
  v22[1] = L"FORCED_NETWORK_FLAG";
  v22[2] = MdmLogCollector::GetUefiDwordAsString;
  v22[3] = L"{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}";
  v22[4] = L"AUTOPILOT_MARKER";
  v22[5] = MdmLogCollector::GetUefiMbcsAsString;
  v23[0] = L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}";
  v23[1] = L"DeviceLinkId";
  v23[2] = MdmLogCollector::GetUefiMbcsAsString;
  v23[3] = L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}";
  v23[4] = L"DeviceLinkCreationTimeUtc";
  v23[5] = MdmLogCollector::GetUefiMbcsAsString;
  v23[6] = L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}";
  v23[7] = L"IdkKeyId";
  v23[8] = MdmLogCollector::GetUefiMbcsAsString;
  v23[9] = L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}";
  v23[10] = L"DeviceLinkJwtCompressed";
  v23[11] = MdmLogCollector::GetUefiCompressedAsBase64String;
  v23[12] = L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}";
  v23[13] = L"DeviceLinkJwtLastWrite";
  v23[14] = MdmLogCollector::GetUefiMbcsAsString;
  v28[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v28[1] = si128;
  LOWORD(v28[0]) = 0;
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}", v28);
  v4 = TemporaryOutputPath;
  if ( TemporaryOutputPath >= 0 )
  {
    std::operator+<unsigned short>(v27, v28, L"\\UEFI_Data_Output.txt");
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    DeleteFileW(v5);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    MdmLogCollector::AddEntry(v6, (char *)this + 32);
    Stream = 0;
    v7 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    v8 = _wfopen_s(&Stream, v7, L"a+");
    if ( v8 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x58F,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
             (const char *)v8,
             v18);
      wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&int fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&int fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(&Stream);
      std::wstring::_Tidy_deallocate(v27);
    }
    else
    {
      MdmLogCollector::WriteSystemTime(Stream);
      MdmLogCollector::WriteToFile(Stream, L"\n");
      ReturnedState = 0;
      Privilege[0] = 22;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &ReturnedState,
        0);
      v9 = RtlAcquirePrivilege(Privilege, 1u, 0, &ReturnedState);
      if ( v9 >= 0 )
      {
        LOBYTE(v18) = 0;
        IsUefiSupported = ModernDeployment::Autopilot::Core::UefiGeneralUtilsT<ModernDeployment::Autopilot::Core::EmptyTemplateClassType>::IsUefiSupported(&v18);
        if ( IsUefiSupported >= 0 )
        {
          if ( (_BYTE)v18 )
          {
            MdmLogCollector::WriteToFile(Stream, L"UEFI is supported.\n");
            v11 = v22;
            do
            {
              MdmLogCollector::WriteToFile(Stream, L"Namespace: %s, variable name: %s\n", *v11, v11[1]);
              v25 = 0;
              v26 = si128;
              LOWORD(v25) = 0;
              v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *))v11[2])(*v11, v11[1], &v25);
              if ( v12 >= 0 )
              {
                v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
                MdmLogCollector::WriteToFile(Stream, L"Value: %s\n", v13);
              }
              else
              {
                MdmLogCollector::WriteToFile(Stream, L"Error: 0x%08X\n", (unsigned int)v12);
              }
              std::wstring::_Tidy_deallocate(&v25);
              v11 += 3;
            }
            while ( v11 != v23 );
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
            {
              v14 = (char *)v23;
              do
              {
                MdmLogCollector::WriteToFile(
                  Stream,
                  L"Namespace: %s, variable name: %s\n",
                  *(_QWORD *)v14,
                  *((_QWORD *)v14 + 1));
                v25 = 0;
                v26 = si128;
                LOWORD(v25) = 0;
                v15 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))v14 + 2))(
                        *(_QWORD *)v14,
                        *((_QWORD *)v14 + 1),
                        &v25);
                if ( v15 >= 0 )
                {
                  v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
                  MdmLogCollector::WriteToFile(Stream, L"Value: %s\n", v16);
                }
                else
                {
                  MdmLogCollector::WriteToFile(Stream, L"Error: 0x%08X\n", (unsigned int)v15);
                }
                std::wstring::_Tidy_deallocate(&v25);
                v14 += 24;
              }
              while ( v14 != &v24 );
            }
            MdmLogCollector::WriteToFile(Stream, L"UEFI query complete.\n");
          }
          else
          {
            MdmLogCollector::WriteToFile(Stream, L"UEFI is not supported.\n");
          }
        }
        else
        {
          MdmLogCollector::WriteToFile(
            Stream,
            L"UEFI support query failed. Error: 0x%08X",
            (unsigned int)IsUefiSupported);
        }
      }
      else
      {
        MdmLogCollector::WriteToFile(Stream, L"Failed to acquire UEFI privilege. Error: 0x%08X", v9 | 0x10000000u);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ReturnedState);
      wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&int fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&int fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(&Stream);
      std::wstring::_Tidy_deallocate(v27);
      v4 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x584,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)TemporaryOutputPath,
      v18);
  }
  std::wstring::_Tidy_deallocate(v28);
  return v4;
}

```

## disassembly

```asm
0x18010da60  mov     rax, rsp
0x18010da63  mov     [rax+10h], rbx
0x18010da67  mov     [rax+18h], rdi
0x18010da6b  push    rbp
0x18010da6c  lea     rbp, [rax-78h]
0x18010da70  sub     rsp, 170h
0x18010da77  movaps  xmmword ptr [rax-18h], xmm6
0x18010da7b  mov     rax, cs:__security_cookie
0x18010da82  xor     rax, rsp
0x18010da85  mov     [rbp+70h+var_20], rax
0x18010da89  mov     rdi, rcx
0x18010da8c  lea     rcx, a616e2ea6Af897e; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18010da93  mov     [rsp+170h+var_130], rcx
0x18010da98  lea     rax, aForcedNetworkF; "FORCED_NETWORK_FLAG"
0x18010da9f  mov     [rsp+170h+var_128], rax
0x18010daa4  lea     rax, ?GetUefiDwordAsString@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetUefiDwordAsString(ushort const *,ushort const *,std::wstring &)
0x18010daab  mov     [rsp+170h+var_120], rax
0x18010dab0  mov     [rsp+170h+var_118], rcx
0x18010dab5  lea     rax, aAutopilotMarke; "AUTOPILOT_MARKER"
0x18010dabc  mov     [rsp+170h+var_110], rax
0x18010dac1  lea     rdx, ?GetUefiMbcsAsString@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetUefiMbcsAsString(ushort const *,ushort const *,std::wstring &)
0x18010dac8  mov     [rsp+170h+var_108], rdx
0x18010dacd  lea     rcx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18010dad4  mov     [rsp+170h+var_100], rcx
0x18010dad9  lea     rax, aDevicelinkid; "DeviceLinkId"
0x18010dae0  mov     [rsp+170h+var_F8], rax
0x18010dae5  mov     [rbp+70h+var_F0], rdx
0x18010dae9  mov     [rbp+70h+var_E8], rcx
0x18010daed  lea     rax, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18010daf4  mov     [rbp+70h+var_E0], rax
0x18010daf8  mov     [rbp+70h+var_D8], rdx
0x18010dafc  mov     [rbp+70h+var_D0], rcx
0x18010db00  lea     rax, aIdkkeyid; "IdkKeyId"
0x18010db07  mov     [rbp+70h+var_C8], rax
0x18010db0b  mov     [rbp+70h+var_C0], rdx
0x18010db0f  mov     [rbp+70h+var_B8], rcx
0x18010db13  lea     rax, aDevicelinkjwtc; "DeviceLinkJwtCompressed"
0x18010db1a  mov     [rbp+70h+var_B0], rax
0x18010db1e  lea     rax, ?GetUefiCompressedAsBase64String@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetUefiCompressedAsBase64String(ushort const *,ushort const *,std::wstring &)
0x18010db25  mov     [rbp+70h+var_A8], rax
0x18010db29  mov     [rbp+70h+var_A0], rcx
0x18010db2d  lea     rax, aDevicelinkjwtl; "DeviceLinkJwtLastWrite"
0x18010db34  mov     [rbp+70h+var_98], rax
0x18010db38  mov     [rbp+70h+var_90], rdx
0x18010db3c  xorps   xmm0, xmm0
0x18010db3f  movups  [rbp+70h+var_40], xmm0
0x18010db43  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18010db4b  movdqu  [rbp+70h+var_30], xmm6
0x18010db50  xor     eax, eax
0x18010db52  mov     word ptr [rbp+70h+var_40], ax
0x18010db56  lea     rdx, [rbp+70h+var_40]
0x18010db5a  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010db5f  mov     ebx, eax
0x18010db61  test    eax, eax
0x18010db63  jns     short loc_18010DB82
0x18010db65  mov     rcx, [rbp+78h]; this
0x18010db69  mov     r9d, eax; char *
0x18010db6c  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010db73  mov     edx, 584h; void *
0x18010db78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010db7d  jmp     loc_18010DE3F
0x18010db82  lea     r8, aUefiDataOutput; "\\UEFI_Data_Output.txt"
0x18010db89  lea     rdx, [rbp+70h+var_40]
0x18010db8d  lea     rcx, [rbp+70h+var_60]
0x18010db91  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18010db96  nop
0x18010db97  lea     rcx, [rbp+70h+var_60]
0x18010db9b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010dba0  mov     rcx, rax; lpFileName
0x18010dba3  call    cs:__imp_DeleteFileW
0x18010dba9  lea     rcx, [rbp+70h+var_60]
0x18010dbad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010dbb2  mov     rcx, rax
0x18010dbb5  lea     rdx, [rdi+20h]
0x18010dbb9  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010dbbe  nop
0x18010dbbf  mov     [rsp+170h+Stream], 0
0x18010dbc8  lea     rcx, [rbp+70h+var_60]
0x18010dbcc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010dbd1  mov     rdx, rax; FileName
0x18010dbd4  lea     r8, aA; "a+"
0x18010dbdb  lea     rcx, [rsp+170h+Stream]; Stream
0x18010dbe0  call    cs:__imp__wfopen_s
0x18010dbe6  test    eax, eax
0x18010dbe8  jz      short loc_18010DC1D
0x18010dbea  mov     rcx, [rbp+78h]; this
0x18010dbee  mov     r9d, eax; char *
0x18010dbf1  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010dbf8  mov     edx, 58Fh; void *
0x18010dbfd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010dc02  mov     ebx, eax
0x18010dc04  lea     rcx, [rsp+170h+Stream]
0x18010dc09  call    ??1?$unique_storage@U?$resource_policy@PEAU_iobuf@@P6AHPEAU1@@Z$1?fclose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(void)
0x18010dc0e  nop
0x18010dc0f  lea     rcx, [rbp+70h+var_60]
0x18010dc13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010dc18  jmp     loc_18010DE3F
0x18010dc1d  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dc22  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010dc27  lea     rdx, asc_1801B9CF8; "\n"
0x18010dc2e  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dc33  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dc38  mov     [rsp+170h+ReturnedState], 0
0x18010dc41  mov     [rsp+170h+Privilege], 16h
0x18010dc49  xor     edx, edx
0x18010dc4b  lea     rcx, [rsp+170h+ReturnedState]
0x18010dc50  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18010dc55  lea     r9, [rsp+170h+ReturnedState]; ReturnedState
0x18010dc5a  xor     r8d, r8d; Flags
0x18010dc5d  lea     edx, [r8+1]; NumPriv
0x18010dc61  lea     rcx, [rsp+170h+Privilege]; Privilege
0x18010dc66  call    cs:__imp_RtlAcquirePrivilege
0x18010dc6c  test    eax, eax
0x18010dc6e  jns     short loc_18010DC8D
0x18010dc70  bts     eax, 1Ch
0x18010dc74  lea     rdx, aFailedToAcquir; "Failed to acquire UEFI privilege. Error"...
0x18010dc7b  mov     r8d, eax
0x18010dc7e  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dc83  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dc88  jmp     loc_18010DE1E
0x18010dc8d  mov     byte ptr [rsp+170h+var_150], 0
0x18010dc92  lea     rcx, [rsp+170h+var_150]
0x18010dc97  call    ?IsUefiSupported@?$UefiGeneralUtilsT@VEmptyTemplateClassType@Core@Autopilot@ModernDeployment@@@Core@Autopilot@ModernDeployment@@SAJAEA_N@Z; ModernDeployment::Autopilot::Core::UefiGeneralUtilsT<ModernDeployment::Autopilot::Core::EmptyTemplateClassType>::IsUefiSupported(bool &)
0x18010dc9c  test    eax, eax
0x18010dc9e  jns     short loc_18010DCA9
0x18010dca0  lea     rdx, aUefiSupportQue; "UEFI support query failed. Error: 0x%08"...
0x18010dca7  jmp     short loc_18010DC7B
0x18010dca9  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dcae  cmp     byte ptr [rsp+170h+var_150], 0
0x18010dcb3  jnz     short loc_18010DCC1
0x18010dcb5  lea     rdx, aUefiIsNotSuppo; "UEFI is not supported.\n"
0x18010dcbc  jmp     loc_18010DE18
0x18010dcc1  lea     rdx, aUefiIsSupporte; "UEFI is supported.\n"
0x18010dcc8  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dccd  lea     rbx, [rsp+170h+var_130]
0x18010dcd2  mov     r9, [rbx+8]
0x18010dcd6  mov     r8, [rbx]
0x18010dcd9  lea     rdx, aNamespaceSVari; "Namespace: %s, variable name: %s\n"
0x18010dce0  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dce5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dcea  xorps   xmm0, xmm0
0x18010dced  movups  [rbp+70h+var_80], xmm0
0x18010dcf1  movdqu  [rbp+70h+var_70], xmm6
0x18010dcf6  xor     eax, eax
0x18010dcf8  mov     word ptr [rbp+70h+var_80], ax
0x18010dcfc  lea     r8, [rbp+70h+var_80]
0x18010dd00  mov     rdx, [rbx+8]
0x18010dd04  mov     rcx, [rbx]
0x18010dd07  mov     rax, [rbx+10h]
0x18010dd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd10  test    eax, eax
0x18010dd12  jns     short loc_18010DD2A
0x18010dd14  mov     r8d, eax
0x18010dd17  lea     rdx, aError0x08x; "Error: 0x%08X\n"
0x18010dd1e  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dd23  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dd28  jmp     short loc_18010DD48
0x18010dd2a  lea     rcx, [rbp+70h+var_80]
0x18010dd2e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010dd33  mov     r8, rax
0x18010dd36  lea     rdx, aValueS; "Value: %s\n"
0x18010dd3d  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dd42  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dd47  nop
0x18010dd48  lea     rcx, [rbp+70h+var_80]
0x18010dd4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010dd51  add     rbx, 18h
0x18010dd55  lea     rax, [rsp+170h+var_100]
0x18010dd5a  cmp     rbx, rax
0x18010dd5d  jnz     loc_18010DCD2
0x18010dd63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010dd6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010dd6f  test    al, al
0x18010dd71  jz      loc_18010DE0C
0x18010dd77  lea     rbx, [rsp+170h+var_100]
0x18010dd7c  mov     r9, [rbx+8]
0x18010dd80  mov     r8, [rbx]
0x18010dd83  lea     rdx, aNamespaceSVari; "Namespace: %s, variable name: %s\n"
0x18010dd8a  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010dd8f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010dd94  xorps   xmm0, xmm0
0x18010dd97  movups  [rbp+70h+var_80], xmm0
0x18010dd9b  movdqu  [rbp+70h+var_70], xmm6
0x18010dda0  xor     eax, eax
0x18010dda2  mov     word ptr [rbp+70h+var_80], ax
0x18010dda6  lea     r8, [rbp+70h+var_80]
0x18010ddaa  mov     rdx, [rbx+8]
0x18010ddae  mov     rcx, [rbx]
0x18010ddb1  mov     rax, [rbx+10h]
0x18010ddb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ddba  test    eax, eax
0x18010ddbc  jns     short loc_18010DDD4
0x18010ddbe  mov     r8d, eax
0x18010ddc1  lea     rdx, aError0x08x; "Error: 0x%08X\n"
0x18010ddc8  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010ddcd  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ddd2  jmp     short loc_18010DDF2
0x18010ddd4  lea     rcx, [rbp+70h+var_80]
0x18010ddd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010dddd  mov     r8, rax
0x18010dde0  lea     rdx, aValueS; "Value: %s\n"
0x18010dde7  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010ddec  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ddf1  nop
0x18010ddf2  lea     rcx, [rbp+70h+var_80]
0x18010ddf6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ddfb  add     rbx, 18h
0x18010ddff  lea     rax, [rbp+70h+var_88]
0x18010de03  cmp     rbx, rax
0x18010de06  jnz     loc_18010DD7C
0x18010de0c  lea     rdx, aUefiQueryCompl; "UEFI query complete.\n"
0x18010de13  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010de18  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010de1d  nop
0x18010de1e  lea     rcx, [rsp+170h+ReturnedState]
0x18010de23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010de28  nop
0x18010de29  lea     rcx, [rsp+170h+Stream]
0x18010de2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_iobuf@@P6AHPEAU1@@Z$1?fclose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(void)
0x18010de33  nop
0x18010de34  lea     rcx, [rbp+70h+var_60]
0x18010de38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010de3d  xor     ebx, ebx
0x18010de3f  lea     rcx, [rbp+70h+var_40]
0x18010de43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010de48  mov     eax, ebx
0x18010de4a  mov     rcx, [rbp+70h+var_20]
0x18010de4e  xor     rcx, rsp; StackCookie
0x18010de51  call    __security_check_cookie
0x18010de56  lea     r11, [rsp+170h+var_s0]
0x18010de5e  mov     rbx, [r11+18h]
0x18010de62  mov     rdi, [r11+20h]
0x18010de66  movaps  xmm6, xmmword ptr [r11-10h]
0x18010de6b  mov     rsp, r11
0x18010de6e  pop     rbp
0x18010de6f  retn
```
