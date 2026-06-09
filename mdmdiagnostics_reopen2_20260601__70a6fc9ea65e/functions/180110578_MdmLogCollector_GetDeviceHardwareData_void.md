# MdmLogCollector::GetDeviceHardwareData(void)

- ea: `0x180110578`
- end: `0x180110a9f`
- name: `?GetDeviceHardwareData@MdmLogCollector@@AEAAJXZ`
- size: `1319`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x18001989c`
- `0x18001a130`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e7c78`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1800fa50c`
- `0x1800fa538`
- `0x18010562c`
- `0x180109140`
- `0x180109d50`
- `0x180110578`
- `0x180110d34`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180110681`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180110681`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110815`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110815`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801109e8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801109e8`
- `OLEAUT32!__imp_VariantInit` at `0x1801106b1`
- `OLEAUT32!__imp_VariantInit` at `0x1801106b1`
- `OLEAUT32!__imp_VariantClear` at `0x180110728`
- `OLEAUT32!__imp_VariantClear` at `0x180110a36`
- `OLEAUT32!__imp_VariantClear` at `0x180110728`
- `OLEAUT32!__imp_VariantClear` at `0x180110a36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801106f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801106f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180110914`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180110993`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180110914`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180110993`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18011087c`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18011087c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1801105cc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1801105cc`

## string_xrefs

- `0x1801105e0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180110644`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180110712`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180110833`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180110932`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801109af`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801109fc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MdmLogCollector::GetDeviceHardwareData(MdmLogCollector *this)
{
  const char *v2; // r9
  __int64 v4; // rcx
  int TemporaryOutputPath; // eax
  unsigned int LastError; // ebx
  const WCHAR *v7; // rax
  __int64 v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  LPVOID v12; // rbx
  __int64 (__fastcall *v13)(LPVOID, const wchar_t *, __int64 *); // rdi
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  HANDLE FileW; // rbx
  const char *v17; // r9
  const WCHAR *v18; // rdx
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int v21; // esi
  unsigned __int16 *v22; // rdi
  const WCHAR *v23; // rax
  int v24; // eax
  const char *v25; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  LPVOID v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v34; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  DWORD nSize; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v38[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v39[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v40[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v41[32]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR Buffer[8]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v43; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  wprintf(L"Collecting hardware hash information.\n");
  *(_OWORD *)Buffer = 0;
  v43 = 0;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x69E,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
             v2);
  std::wstring::wstring(v39, L"\\DeviceHash_");
  std::wstring::append(v39, Buffer);
  std::wstring::append(v39, L".csv");
  std::wstring::wstring(v41);
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v4, v41);
  LastError = TemporaryOutputPath;
  if ( TemporaryOutputPath >= 0 )
  {
    std::wstring::wstring(v37, v41);
    std::wstring::append(v37, v39);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    DeleteFileW(v7);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    MdmLogCollector::AddEntry(v8, (char *)this + 32);
    v31 = 0;
    VariantInit(&pvarg);
    v30 = 0;
    v9 = CoCreateInstance(
           &GUID_66d0db14_5638_475f_a386_629522d8c461,
           0,
           1u,
           &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
           &v30);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v12 = v30;
      v13 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v30 + 80LL);
      v14 = v31;
      v31 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v9 = v13(v12, L"./DevDetail/Ext/DeviceHardwareData", &v31);
      LastError = v9;
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v31 + 104LL))(v31, &pvarg);
        LastError = v9;
        if ( v9 >= 0 )
        {
          if ( pvarg.vt == 8 )
          {
            v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
            FileW = CreateFileW(v15, 0x10000000u, 0, 0, 2u, 0, 0);
            v34 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x6C8,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                            v17);
            }
            else
            {
              std::wstring::wstring(v38, L"Device Serial Number,Windows Product ID,Hardware Hash\r\n");
              v32 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v32,
                0);
              if ( (int)DmGetSmbiosSerialNumber(&v32) < 0 )
              {
                v18 = &Name;
              }
              else
              {
                v18 = v32;
                v32 = 0;
              }
              std::wstring::wstring(v40, v18);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
              std::wstring::append(v38, v40);
              std::wstring::_Tidy_deallocate(v40);
              std::wstring::append(v38, L",,");
              std::wstring::append(v38, pvarg.llVal);
              v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
              v20 = WideCharToMultiByte(0xFDE9u, 0, v19, -1, 0, 0, 0, 0);
              v21 = v20;
              if ( v20 )
              {
                v22 = (unsigned __int16 *)operator new[](v20, (const struct std::nothrow_t *)std::nothrow);
                v32 = v22;
                v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
                v24 = WideCharToMultiByte(0xFDE9u, 0, v23, -1, (LPSTR)v22, v21, 0, 0);
                if ( v24 )
                {
                  NumberOfBytesWritten = 0;
                  if ( WriteFile(FileW, v22, v24 - 1, &NumberOfBytesWritten, 0) )
                  {
                    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v32);
                    std::wstring::_Tidy_deallocate(v38);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
                    VariantClear(&pvarg);
                    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v30);
                    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v31);
                    std::wstring::_Tidy_deallocate(v37);
                    LastError = 0;
                    goto LABEL_33;
                  }
                  LastError = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0x6DE,
                                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                                v25);
                }
                else
                {
                  LastError = -2147418113;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6D7,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                    (const char *)0x8000FFFFLL,
                    ppvc);
                }
                std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v32);
              }
              else
              {
                LastError = -2147418113;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6D2,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  (const char *)0x8000FFFFLL,
                  ppvb);
              }
              std::wstring::_Tidy_deallocate(v38);
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
            goto LABEL_9;
          }
          LastError = -2147418113;
          v11 = 2147549183LL;
          v10 = 1725;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)v11,
            ppva);
LABEL_9:
          VariantClear(&pvarg);
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v30);
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v31);
          std::wstring::_Tidy_deallocate(v37);
          goto LABEL_33;
        }
        v10 = 1724;
      }
      else
      {
        v10 = 1723;
      }
    }
    else
    {
      v10 = 1722;
    }
    v11 = (unsigned int)v9;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6A5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
    (const char *)(unsigned int)TemporaryOutputPath,
    ppv);
LABEL_33:
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v39);
  return LastError;
}

```

## disassembly

```asm
0x180110578  mov     [rsp-8+arg_8], rbx
0x18011057d  mov     [rsp-8+arg_10], rsi
0x180110582  push    rbp
0x180110583  push    rdi
0x180110584  push    r14
0x180110586  lea     rbp, [rsp-50h]
0x18011058b  sub     rsp, 150h
0x180110592  mov     rax, cs:__security_cookie
0x180110599  xor     rax, rsp
0x18011059c  mov     [rbp+60h+var_18], rax
0x1801105a0  mov     rdi, rcx
0x1801105a3  xor     r14d, r14d
0x1801105a6  lea     rcx, aCollectingHard; "Collecting hardware hash information.\n"
0x1801105ad  call    wprintf
0x1801105b2  xorps   xmm0, xmm0
0x1801105b5  movups  xmmword ptr [rbp+60h+Buffer], xmm0
0x1801105b9  movups  [rbp+60h+var_28], xmm0
0x1801105bd  mov     [rbp+60h+nSize], 10h
0x1801105c4  lea     rdx, [rbp+60h+nSize]; nSize
0x1801105c8  lea     rcx, [rbp+60h+Buffer]; lpBuffer
0x1801105cc  call    cs:__imp_GetComputerNameW
0x1801105d3  nop     dword ptr [rax+rax+00h]
0x1801105d8  test    eax, eax
0x1801105da  jnz     short loc_1801105F6
0x1801105dc  mov     rcx, [rbp+68h]; this
0x1801105e0  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801105e7  mov     edx, 69Eh; void *
0x1801105ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801105f1  jmp     loc_180110A7A
0x1801105f6  lea     rdx, aDevicehash; "\\DeviceHash_"
0x1801105fd  lea     rcx, [rbp+60h+var_98]
0x180110601  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180110606  nop
0x180110607  lea     rdx, [rbp+60h+Buffer]
0x18011060b  lea     rcx, [rbp+60h+var_98]
0x18011060f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180110614  lea     rdx, aCsv; ".csv"
0x18011061b  lea     rcx, [rbp+60h+var_98]
0x18011061f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180110624  lea     rcx, [rbp+60h+var_58]
0x180110628  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18011062d  nop
0x18011062e  lea     rdx, [rbp+60h+var_58]
0x180110632  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x180110637  mov     ebx, eax
0x180110639  test    eax, eax
0x18011063b  jns     short loc_18011065A
0x18011063d  mov     rcx, [rbp+68h]; this
0x180110641  mov     r9d, eax; char *
0x180110644  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011064b  mov     edx, 6A5h; void *
0x180110650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110655  jmp     loc_180110A65
0x18011065a  lea     rdx, [rbp+60h+var_58]
0x18011065e  lea     rcx, [rbp+60h+var_D8]
0x180110662  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180110667  nop
0x180110668  lea     rdx, [rbp+60h+var_98]
0x18011066c  lea     rcx, [rbp+60h+var_D8]
0x180110670  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180110675  lea     rcx, [rbp+60h+var_D8]
0x180110679  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011067e  mov     rcx, rax; lpFileName
0x180110681  call    cs:__imp_DeleteFileW
0x180110688  nop     dword ptr [rax+rax+00h]
0x18011068d  lea     rcx, [rbp+60h+var_D8]
0x180110691  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110696  mov     rcx, rax
0x180110699  lea     rdx, [rdi+20h]
0x18011069d  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x1801106a2  mov     [rsp+160h+var_118], r14
0x1801106a7  mov     [rsp+160h+var_120], r14
0x1801106ac  lea     rcx, [rsp+160h+pvarg]; pvarg
0x1801106b1  call    cs:__imp_VariantInit
0x1801106b8  nop     dword ptr [rax+rax+00h]
0x1801106bd  nop
0x1801106be  mov     rcx, [rsp+160h+var_120]
0x1801106c3  mov     [rsp+160h+var_120], r14
0x1801106c8  test    rcx, rcx
0x1801106cb  jz      short loc_1801106DA
0x1801106cd  mov     rax, [rcx]
0x1801106d0  mov     rax, [rax+10h]
0x1801106d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801106d9  nop
0x1801106da  lea     rax, [rsp+160h+var_120]
0x1801106df  mov     [rsp+160h+ppv], rax; int
0x1801106e4  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1801106eb  xor     edx, edx; pUnkOuter
0x1801106ed  lea     r8d, [rdx+1]; dwClsContext
0x1801106f1  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1801106f8  call    cs:__imp_CoCreateInstance
0x1801106ff  nop     dword ptr [rax+rax+00h]
0x180110704  mov     ebx, eax
0x180110706  test    eax, eax
0x180110708  jns     short loc_180110759
0x18011070a  mov     edx, 6BAh; void *
0x18011070f  mov     r9d, eax; char *
0x180110712  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180110719  mov     rcx, [rbp+68h]; this
0x18011071d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110722  nop
0x180110723  lea     rcx, [rsp+160h+pvarg]; pvarg
0x180110728  call    cs:__imp_VariantClear
0x18011072f  nop     dword ptr [rax+rax+00h]
0x180110734  nop
0x180110735  lea     rcx, [rsp+160h+var_120]
0x18011073a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18011073f  nop
0x180110740  lea     rcx, [rsp+160h+var_118]
0x180110745  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18011074a  nop
0x18011074b  lea     rcx, [rbp+60h+var_D8]
0x18011074f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110754  jmp     loc_180110A65
0x180110759  mov     rbx, [rsp+160h+var_120]
0x18011075e  mov     rax, [rbx]
0x180110761  mov     rdi, [rax+50h]
0x180110765  mov     rcx, [rsp+160h+var_118]
0x18011076a  mov     [rsp+160h+var_118], r14
0x18011076f  test    rcx, rcx
0x180110772  jz      short loc_180110781
0x180110774  mov     rdx, [rcx]
0x180110777  mov     rax, [rdx+10h]
0x18011077b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110780  nop
0x180110781  lea     r8, [rsp+160h+var_118]
0x180110786  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18011078d  mov     rcx, rbx
0x180110790  mov     rax, rdi
0x180110793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110798  mov     ebx, eax
0x18011079a  test    eax, eax
0x18011079c  jns     short loc_1801107A8
0x18011079e  mov     edx, 6BBh
0x1801107a3  jmp     loc_18011070F
0x1801107a8  mov     rcx, [rsp+160h+var_118]
0x1801107ad  mov     rax, [rcx]
0x1801107b0  lea     rdx, [rsp+160h+pvarg]
0x1801107b5  mov     rax, [rax+68h]
0x1801107b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801107be  mov     ebx, eax
0x1801107c0  test    eax, eax
0x1801107c2  jns     short loc_1801107CE
0x1801107c4  mov     edx, 6BCh
0x1801107c9  jmp     loc_18011070F
0x1801107ce  mov     eax, 8
0x1801107d3  cmp     ax, word ptr [rsp+160h+pvarg]
0x1801107d8  jz      short loc_1801107EC
0x1801107da  mov     ebx, 8000FFFFh
0x1801107df  mov     r9d, ebx
0x1801107e2  mov     edx, 6BDh
0x1801107e7  jmp     loc_180110712
0x1801107ec  lea     rcx, [rbp+60h+var_D8]
0x1801107f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801107f5  mov     rcx, rax; lpFileName
0x1801107f8  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x1801107fd  mov     [rsp+160h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180110802  mov     dword ptr [rsp+160h+ppv], 2; dwCreationDisposition
0x18011080a  xor     r9d, r9d; lpSecurityAttributes
0x18011080d  xor     r8d, r8d; dwShareMode
0x180110810  mov     edx, 10000000h; dwDesiredAccess
0x180110815  call    cs:__imp_CreateFileW
0x18011081c  nop     dword ptr [rax+rax+00h]
0x180110821  mov     rbx, rax
0x180110824  mov     [rsp+160h+var_100], rax
0x180110829  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011082d  jnz     short loc_180110855
0x18011082f  mov     rcx, [rbp+68h]; this
0x180110833  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011083a  mov     edx, 6C8h; void *
0x18011083f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180110844  mov     ebx, eax
0x180110846  lea     rcx, [rsp+160h+var_100]
0x18011084b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180110850  jmp     loc_180110723
0x180110855  lea     rdx, aDeviceSerialNu; "Device Serial Number,Windows Product ID"...
0x18011085c  lea     rcx, [rbp+60h+var_B8]
0x180110860  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180110865  nop
0x180110866  mov     [rsp+160h+var_110], r14
0x18011086b  xor     edx, edx
0x18011086d  lea     rcx, [rsp+160h+var_110]
0x180110872  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180110877  lea     rcx, [rsp+160h+var_110]
0x18011087c  call    cs:__imp_?DmGetSmbiosSerialNumber@@YAJPEAPEAG@Z; DmGetSmbiosSerialNumber(ushort * *)
0x180110883  nop     dword ptr [rax+rax+00h]
0x180110888  lea     rcx, [rbp+60h+var_78]
0x18011088c  test    eax, eax
0x18011088e  js      short loc_18011089C
0x180110890  mov     rdx, [rsp+160h+var_110]
0x180110895  mov     [rsp+160h+var_110], r14
0x18011089a  jmp     short loc_1801108A3
0x18011089c  lea     rdx, Name
0x1801108a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801108a8  nop
0x1801108a9  lea     rcx, [rsp+160h+var_110]
0x1801108ae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801108b3  nop
0x1801108b4  lea     rdx, [rbp+60h+var_78]
0x1801108b8  lea     rcx, [rbp+60h+var_B8]
0x1801108bc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1801108c1  nop
0x1801108c2  lea     rcx, [rbp+60h+var_78]
0x1801108c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801108cb  lea     rdx, asc_1801D49D4; ",,"
0x1801108d2  lea     rcx, [rbp+60h+var_B8]
0x1801108d6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801108db  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x1801108e0  lea     rcx, [rbp+60h+var_B8]
0x1801108e4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801108e9  lea     rcx, [rbp+60h+var_B8]
0x1801108ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801108f2  mov     r8, rax; lpWideCharStr
0x1801108f5  mov     [rsp+160h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1801108fa  mov     [rsp+160h+hTemplateFile], r14; lpDefaultChar
0x1801108ff  mov     [rsp+160h+dwFlagsAndAttributes], r14d; cbMultiByte
0x180110904  mov     [rsp+160h+ppv], r14; int
0x180110909  or      r9d, 0FFFFFFFFh; cchWideChar
0x18011090d  xor     edx, edx; dwFlags
0x18011090f  mov     ecx, 0FDE9h; CodePage
0x180110914  call    cs:__imp_WideCharToMultiByte
0x18011091b  nop     dword ptr [rax+rax+00h]
0x180110920  mov     esi, eax
0x180110922  test    eax, eax
0x180110924  jnz     short loc_180110952
0x180110926  mov     rcx, [rbp+68h]; this
0x18011092a  mov     ebx, 8000FFFFh
0x18011092f  mov     r9d, ebx; char *
0x180110932  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180110939  mov     edx, 6D2h; void *
0x18011093e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110943  nop
0x180110944  lea     rcx, [rbp+60h+var_B8]
0x180110948  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011094d  jmp     loc_180110846
0x180110952  mov     rcx, rsi; unsigned __int64
0x180110955  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011095c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180110961  mov     rdi, rax
0x180110964  mov     [rsp+160h+var_110], rax
0x180110969  lea     rcx, [rbp+60h+var_B8]
0x18011096d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110972  mov     r8, rax; lpWideCharStr
0x180110975  mov     [rsp+160h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18011097a  mov     [rsp+160h+hTemplateFile], r14; lpDefaultChar
0x18011097f  mov     [rsp+160h+dwFlagsAndAttributes], esi; cbMultiByte
0x180110983  mov     [rsp+160h+ppv], rdi; int
0x180110988  or      r9d, 0FFFFFFFFh; cchWideChar
0x18011098c  xor     edx, edx; dwFlags
0x18011098e  mov     ecx, 0FDE9h; CodePage
0x180110993  call    cs:__imp_WideCharToMultiByte
0x18011099a  nop     dword ptr [rax+rax+00h]
0x18011099f  test    eax, eax
0x1801109a1  jnz     short loc_1801109CF
0x1801109a3  mov     rcx, [rbp+68h]; this
0x1801109a7  mov     ebx, 8000FFFFh
0x1801109ac  mov     r9d, ebx; char *
0x1801109af  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801109b6  mov     edx, 6D7h; void *
0x1801109bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801109c0  lea     rcx, [rsp+160h+var_110]
0x1801109c5  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801109ca  jmp     loc_180110944
0x1801109cf  mov     [rsp+160h+NumberOfBytesWritten], r14d
0x1801109d4  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x1801109d8  mov     [rsp+160h+ppv], r14; lpOverlapped
0x1801109dd  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801109e2  mov     rdx, rdi; lpBuffer
0x1801109e5  mov     rcx, rbx; hFile
0x1801109e8  call    cs:__imp_WriteFile
0x1801109ef  nop     dword ptr [rax+rax+00h]
0x1801109f4  test    eax, eax
0x1801109f6  jnz     short loc_180110A11
0x1801109f8  mov     rcx, [rbp+68h]; this
0x1801109fc  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180110a03  mov     edx, 6DEh; void *
0x180110a08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180110a0d  mov     ebx, eax
0x180110a0f  jmp     short loc_1801109C0
0x180110a11  lea     rcx, [rsp+160h+var_110]
0x180110a16  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180110a1b  nop
0x180110a1c  lea     rcx, [rbp+60h+var_B8]
0x180110a20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110a25  nop
0x180110a26  lea     rcx, [rsp+160h+var_100]
0x180110a2b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180110a30  nop
0x180110a31  lea     rcx, [rsp+160h+pvarg]; pvarg
0x180110a36  call    cs:__imp_VariantClear
0x180110a3d  nop     dword ptr [rax+rax+00h]
0x180110a42  nop
0x180110a43  lea     rcx, [rsp+160h+var_120]
0x180110a48  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180110a4d  nop
0x180110a4e  lea     rcx, [rsp+160h+var_118]
0x180110a53  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180110a58  nop
0x180110a59  lea     rcx, [rbp+60h+var_D8]
0x180110a5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
