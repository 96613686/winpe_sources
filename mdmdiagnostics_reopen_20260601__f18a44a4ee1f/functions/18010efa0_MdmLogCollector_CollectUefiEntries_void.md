# MdmLogCollector::CollectUefiEntries(void)

- ea: `0x18010efa0`
- end: `0x18010f3bc`
- name: `?CollectUefiEntries@MdmLogCollector@@AEAAJXZ`
- size: `1052`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f9a08`
- `0x180105294`
- `0x1801091e0`
- `0x180109204`
- `0x180109d50`
- `0x18010efa0`
- `0x180110d34`
- `0x1801115e8`
- `0x180111e34`
- `0x180111ec4`
- `0x18011268c`
- `0x18011298c`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010f11f`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010f11f`
- `ntdll!RtlAcquirePrivilege` at `0x18010f1ab`
- `ntdll!RtlAcquirePrivilege` at `0x18010f1ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010f0dc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010f0dc`

## string_xrefs

- `0x18010f02d`: `DeviceLinkCreationTimeUtc`
- `0x18010f019`: `DeviceLinkId`
- `0x18010f053`: `DeviceLinkJwtCompressed`
- `0x18010f066`: `DeviceLinkJwtLastWrite`
- `0x18010f0a5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f136`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f1bf`: `Failed to acquire UEFI privilege. Error: 0x%08X`
- `0x18010f357`: `UEFI query complete.\n`

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
  v23[11] = MdmLogCollector::GetUefiMbcsAsString;
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
             (void *)0x566,
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
      (void *)0x55B,
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
0x18010efa0  mov     rax, rsp
0x18010efa3  mov     [rax+10h], rbx
0x18010efa7  mov     [rax+18h], rdi
0x18010efab  push    rbp
0x18010efac  lea     rbp, [rax-78h]
0x18010efb0  sub     rsp, 170h
0x18010efb7  movaps  xmmword ptr [rax-18h], xmm6
0x18010efbb  mov     rax, cs:__security_cookie
0x18010efc2  xor     rax, rsp
0x18010efc5  mov     [rbp+70h+var_20], rax
0x18010efc9  mov     rdi, rcx
0x18010efcc  lea     rcx, a616e2ea6Af897e; "{616E2EA6-AF89-7EB3-F2EF-4E47368A657B}"
0x18010efd3  mov     [rsp+170h+var_130], rcx
0x18010efd8  lea     rax, aForcedNetworkF; "FORCED_NETWORK_FLAG"
0x18010efdf  mov     [rsp+170h+var_128], rax
0x18010efe4  lea     rax, ?GetUefiDwordAsString@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetUefiDwordAsString(ushort const *,ushort const *,std::wstring &)
0x18010efeb  mov     [rsp+170h+var_120], rax
0x18010eff0  mov     [rsp+170h+var_118], rcx
0x18010eff5  lea     rax, aAutopilotMarke; "AUTOPILOT_MARKER"
0x18010effc  mov     [rsp+170h+var_110], rax
0x18010f001  lea     rdx, ?GetUefiMbcsAsString@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetUefiMbcsAsString(ushort const *,ushort const *,std::wstring &)
0x18010f008  mov     [rsp+170h+var_108], rdx
0x18010f00d  lea     rcx, aB3de75da819c4f; "{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}"
0x18010f014  mov     [rsp+170h+var_100], rcx
0x18010f019  lea     rax, aDevicelinkid; "DeviceLinkId"
0x18010f020  mov     [rsp+170h+var_F8], rax
0x18010f025  mov     [rbp+70h+var_F0], rdx
0x18010f029  mov     [rbp+70h+var_E8], rcx
0x18010f02d  lea     rax, aDevicelinkcrea; "DeviceLinkCreationTimeUtc"
0x18010f034  mov     [rbp+70h+var_E0], rax
0x18010f038  mov     [rbp+70h+var_D8], rdx
0x18010f03c  mov     [rbp+70h+var_D0], rcx
0x18010f040  lea     rax, aIdkkeyid; "IdkKeyId"
0x18010f047  mov     [rbp+70h+var_C8], rax
0x18010f04b  mov     [rbp+70h+var_C0], rdx
0x18010f04f  mov     [rbp+70h+var_B8], rcx
0x18010f053  lea     rax, aDevicelinkjwtc; "DeviceLinkJwtCompressed"
0x18010f05a  mov     [rbp+70h+var_B0], rax
0x18010f05e  mov     [rbp+70h+var_A8], rdx
0x18010f062  mov     [rbp+70h+var_A0], rcx
0x18010f066  lea     rax, aDevicelinkjwtl; "DeviceLinkJwtLastWrite"
0x18010f06d  mov     [rbp+70h+var_98], rax
0x18010f071  mov     [rbp+70h+var_90], rdx
0x18010f075  xorps   xmm0, xmm0
0x18010f078  movups  [rbp+70h+var_40], xmm0
0x18010f07c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18010f084  movdqu  [rbp+70h+var_30], xmm6
0x18010f089  xor     eax, eax
0x18010f08b  mov     word ptr [rbp+70h+var_40], ax
0x18010f08f  lea     rdx, [rbp+70h+var_40]
0x18010f093  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010f098  mov     ebx, eax
0x18010f09a  test    eax, eax
0x18010f09c  jns     short loc_18010F0BB
0x18010f09e  mov     rcx, [rbp+78h]; this
0x18010f0a2  mov     r9d, eax; char *
0x18010f0a5  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f0ac  mov     edx, 55Bh; void *
0x18010f0b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f0b6  jmp     loc_18010F38A
0x18010f0bb  lea     r8, aUefiDataOutput; "\\UEFI_Data_Output.txt"
0x18010f0c2  lea     rdx, [rbp+70h+var_40]
0x18010f0c6  lea     rcx, [rbp+70h+var_60]
0x18010f0ca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18010f0cf  nop
0x18010f0d0  lea     rcx, [rbp+70h+var_60]
0x18010f0d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f0d9  mov     rcx, rax; lpFileName
0x18010f0dc  call    cs:__imp_DeleteFileW
0x18010f0e3  nop     dword ptr [rax+rax+00h]
0x18010f0e8  lea     rcx, [rbp+70h+var_60]
0x18010f0ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f0f1  mov     rcx, rax
0x18010f0f4  lea     rdx, [rdi+20h]
0x18010f0f8  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010f0fd  nop
0x18010f0fe  mov     [rsp+170h+Stream], 0
0x18010f107  lea     rcx, [rbp+70h+var_60]
0x18010f10b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f110  mov     rdx, rax; FileName
0x18010f113  lea     r8, aA; "a+"
0x18010f11a  lea     rcx, [rsp+170h+Stream]; Stream
0x18010f11f  call    cs:__imp__wfopen_s
0x18010f126  nop     dword ptr [rax+rax+00h]
0x18010f12b  test    eax, eax
0x18010f12d  jz      short loc_18010F162
0x18010f12f  mov     rcx, [rbp+78h]; this
0x18010f133  mov     r9d, eax; char *
0x18010f136  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f13d  mov     edx, 566h; void *
0x18010f142  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010f147  mov     ebx, eax
0x18010f149  lea     rcx, [rsp+170h+Stream]
0x18010f14e  call    ??1?$unique_storage@U?$resource_policy@PEAU_iobuf@@P6AHPEAU1@@Z$1?fclose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(void)
0x18010f153  nop
0x18010f154  lea     rcx, [rbp+70h+var_60]
0x18010f158  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f15d  jmp     loc_18010F38A
0x18010f162  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f167  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010f16c  lea     rdx, asc_1801BBCF8; "\n"
0x18010f173  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f178  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f17d  mov     [rsp+170h+ReturnedState], 0
0x18010f186  mov     [rsp+170h+Privilege], 16h
0x18010f18e  xor     edx, edx
0x18010f190  lea     rcx, [rsp+170h+ReturnedState]
0x18010f195  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18010f19a  lea     r9, [rsp+170h+ReturnedState]; ReturnedState
0x18010f19f  xor     r8d, r8d; Flags
0x18010f1a2  lea     edx, [r8+1]; NumPriv
0x18010f1a6  lea     rcx, [rsp+170h+Privilege]; Privilege
0x18010f1ab  call    cs:__imp_RtlAcquirePrivilege
0x18010f1b2  nop     dword ptr [rax+rax+00h]
0x18010f1b7  test    eax, eax
0x18010f1b9  jns     short loc_18010F1D8
0x18010f1bb  bts     eax, 1Ch
0x18010f1bf  lea     rdx, aFailedToAcquir; "Failed to acquire UEFI privilege. Error"...
0x18010f1c6  mov     r8d, eax
0x18010f1c9  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f1ce  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f1d3  jmp     loc_18010F369
0x18010f1d8  mov     byte ptr [rsp+170h+var_150], 0
0x18010f1dd  lea     rcx, [rsp+170h+var_150]
0x18010f1e2  call    ?IsUefiSupported@?$UefiGeneralUtilsT@VEmptyTemplateClassType@Core@Autopilot@ModernDeployment@@@Core@Autopilot@ModernDeployment@@SAJAEA_N@Z; ModernDeployment::Autopilot::Core::UefiGeneralUtilsT<ModernDeployment::Autopilot::Core::EmptyTemplateClassType>::IsUefiSupported(bool &)
0x18010f1e7  test    eax, eax
0x18010f1e9  jns     short loc_18010F1F4
0x18010f1eb  lea     rdx, aUefiSupportQue; "UEFI support query failed. Error: 0x%08"...
0x18010f1f2  jmp     short loc_18010F1C6
0x18010f1f4  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f1f9  cmp     byte ptr [rsp+170h+var_150], 0
0x18010f1fe  jnz     short loc_18010F20C
0x18010f200  lea     rdx, aUefiIsNotSuppo; "UEFI is not supported.\n"
0x18010f207  jmp     loc_18010F363
0x18010f20c  lea     rdx, aUefiIsSupporte; "UEFI is supported.\n"
0x18010f213  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f218  lea     rbx, [rsp+170h+var_130]
0x18010f21d  mov     r9, [rbx+8]
0x18010f221  mov     r8, [rbx]
0x18010f224  lea     rdx, aNamespaceSVari; "Namespace: %s, variable name: %s\n"
0x18010f22b  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f230  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f235  xorps   xmm0, xmm0
0x18010f238  movups  [rbp+70h+var_80], xmm0
0x18010f23c  movdqu  [rbp+70h+var_70], xmm6
0x18010f241  xor     eax, eax
0x18010f243  mov     word ptr [rbp+70h+var_80], ax
0x18010f247  lea     r8, [rbp+70h+var_80]
0x18010f24b  mov     rdx, [rbx+8]
0x18010f24f  mov     rcx, [rbx]
0x18010f252  mov     rax, [rbx+10h]
0x18010f256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f25b  test    eax, eax
0x18010f25d  jns     short loc_18010F275
0x18010f25f  mov     r8d, eax
0x18010f262  lea     rdx, aError0x08x; "Error: 0x%08X\n"
0x18010f269  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f26e  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f273  jmp     short loc_18010F293
0x18010f275  lea     rcx, [rbp+70h+var_80]
0x18010f279  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f27e  mov     r8, rax
0x18010f281  lea     rdx, aValueS; "Value: %s\n"
0x18010f288  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f28d  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f292  nop
0x18010f293  lea     rcx, [rbp+70h+var_80]
0x18010f297  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f29c  add     rbx, 18h
0x18010f2a0  lea     rax, [rsp+170h+var_100]
0x18010f2a5  cmp     rbx, rax
0x18010f2a8  jnz     loc_18010F21D
0x18010f2ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010f2b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010f2ba  test    al, al
0x18010f2bc  jz      loc_18010F357
0x18010f2c2  lea     rbx, [rsp+170h+var_100]
0x18010f2c7  mov     r9, [rbx+8]
0x18010f2cb  mov     r8, [rbx]
0x18010f2ce  lea     rdx, aNamespaceSVari; "Namespace: %s, variable name: %s\n"
0x18010f2d5  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f2da  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f2df  xorps   xmm0, xmm0
0x18010f2e2  movups  [rbp+70h+var_80], xmm0
0x18010f2e6  movdqu  [rbp+70h+var_70], xmm6
0x18010f2eb  xor     eax, eax
0x18010f2ed  mov     word ptr [rbp+70h+var_80], ax
0x18010f2f1  lea     r8, [rbp+70h+var_80]
0x18010f2f5  mov     rdx, [rbx+8]
0x18010f2f9  mov     rcx, [rbx]
0x18010f2fc  mov     rax, [rbx+10h]
0x18010f300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f305  test    eax, eax
0x18010f307  jns     short loc_18010F31F
0x18010f309  mov     r8d, eax
0x18010f30c  lea     rdx, aError0x08x; "Error: 0x%08X\n"
0x18010f313  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f318  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f31d  jmp     short loc_18010F33D
0x18010f31f  lea     rcx, [rbp+70h+var_80]
0x18010f323  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f328  mov     r8, rax
0x18010f32b  lea     rdx, aValueS; "Value: %s\n"
0x18010f332  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f337  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f33c  nop
0x18010f33d  lea     rcx, [rbp+70h+var_80]
0x18010f341  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f346  add     rbx, 18h
0x18010f34a  lea     rax, [rbp+70h+var_88]
0x18010f34e  cmp     rbx, rax
0x18010f351  jnz     loc_18010F2C7
0x18010f357  lea     rdx, aUefiQueryCompl; "UEFI query complete.\n"
0x18010f35e  mov     rcx, [rsp+170h+Stream]; struct _iobuf *
0x18010f363  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010f368  nop
0x18010f369  lea     rcx, [rsp+170h+ReturnedState]
0x18010f36e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RtlReleasePrivilege@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&RtlReleasePrivilege(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18010f373  nop
0x18010f374  lea     rcx, [rsp+170h+Stream]
0x18010f379  call    ??1?$unique_storage@U?$resource_policy@PEAU_iobuf@@P6AHPEAU1@@Z$1?fclose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_iobuf *,int (*)(_iobuf *),&fclose(_iobuf *),wistd::integral_constant<unsigned __int64,0>,_iobuf *,_iobuf *,0,std::nullptr_t>>(void)
0x18010f37e  nop
0x18010f37f  lea     rcx, [rbp+70h+var_60]
0x18010f383  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f388  xor     ebx, ebx
0x18010f38a  lea     rcx, [rbp+70h+var_40]
0x18010f38e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f393  mov     eax, ebx
0x18010f395  mov     rcx, [rbp+70h+var_20]
0x18010f399  xor     rcx, rsp; StackCookie
0x18010f39c  call    __security_check_cookie
0x18010f3a1  lea     r11, [rsp+170h+var_s0]
0x18010f3a9  mov     rbx, [r11+18h]
0x18010f3ad  mov     rdi, [r11+20h]
0x18010f3b1  movaps  xmm6, xmmword ptr [r11-10h]
0x18010f3b6  mov     rsp, r11
0x18010f3b9  pop     rbp
0x18010f3ba  retn
```
