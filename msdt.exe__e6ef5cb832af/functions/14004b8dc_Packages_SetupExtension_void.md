# Packages_SetupExtension(void)

- ea: `0x14004b8dc`
- end: `0x14004bd7d`
- name: `?Packages_SetupExtension@@YAJXZ`
- size: `1185`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400489dc`
- `0x14004a33c`

## callees

- `0x140001d54`
- `0x140020420`
- `0x1400210f0`
- `0x140037130`
- `0x14003744c`
- `0x1400481a8`
- `0x140049770`
- `0x140049b1c`
- `0x14004b8dc`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004bb4a`
- `KERNEL32!GetLastError` at `0x14004bb81`
- `KERNEL32!GetLastError` at `0x14004bb4a`
- `KERNEL32!GetLastError` at `0x14004bb81`
- `KERNEL32!SetDllDirectoryW` at `0x14004bb3a`
- `KERNEL32!SetDllDirectoryW` at `0x14004bb71`
- `KERNEL32!SetDllDirectoryW` at `0x14004bb3a`
- `KERNEL32!SetDllDirectoryW` at `0x14004bb71`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b984`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b99d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b9b6`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bcd5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bcee`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bd07`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b984`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b99d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004b9b6`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bcd5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bcee`
- `OLEAUT32!__imp_SysFreeString` at `0x14004bd07`

## string_xrefs

- `0x14004ba70`: `./ExtensionPoint/Icon`
- `0x14004b8f1`: `Packages_SetupExtension`
- `0x14004bae5`: `./ExtensionPoint/Maintenance`
- `0x14004bba4`: `./ExtensionPoint/HelpKeywords`

## pseudocode

```c
__int64 Packages_SetupExtension(void)
{
  signed int v0; // ebx
  struct IXMLDOMDocument2 *v1; // rdi
  unsigned int v2; // esi
  unsigned int v3; // edx
  int Package; // eax
  PackageExtension *v5; // rax
  int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax
  int KeywordsFromFile; // eax
  int FeedbackContextIdFromFile; // eax
  int v11; // r9d
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  BSTR v14; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v15; // [rsp+40h] [rbp-10h] BYREF
  PackageExtension *v16; // [rsp+90h] [rbp+40h] BYREF
  struct IPackage *v17; // [rsp+98h] [rbp+48h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+50h] BYREF
  BSTR v19; // [rsp+A8h] [rbp+58h] BYREF

  v0 = 0;
  v17 = 0;
  v1 = 0;
  v15 = 0;
  v18 = 0;
  v2 = 0;
  bstrString = 0;
  v19 = 0;
  v14 = 0;
  while ( 1 )
  {
    v16 = 0;
    if ( v2 >= Packages_GetNumber() )
      break;
    if ( v17 )
    {
      (*(void (__fastcall **)(struct IPackage *))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    if ( v1 )
    {
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v1->lpVtbl->Release)(v1);
      v1 = 0;
      v15 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v19 )
    {
      SysFreeString(v19);
      v19 = 0;
    }
    if ( v14 )
    {
      SysFreeString(v14);
      v14 = 0;
    }
    if ( v16 )
    {
      PackageExtension::`scalar deleting destructor'(v16, v3);
      v16 = 0;
    }
    Package = Packages_GetPackage(v2, &v17);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3784;
      goto LABEL_61;
    }
    Package = (*(__int64 (__fastcall **)(struct IPackage *, PackageExtension **))(*(_QWORD *)v17 + 32LL))(v17, &v16);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3787;
      goto LABEL_61;
    }
    if ( v16 )
    {
      v16 = 0;
      break;
    }
    v5 = (PackageExtension *)operator new(8u);
    v16 = v5;
    if ( !v5 )
    {
      v0 = -2147024882;
      v16 = 0;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", 3795, -2147024882);
      break;
    }
    *(_QWORD *)v5 = 0;
    v16 = v5;
    Package = (*(__int64 (__fastcall **)(struct IPackage *, BSTR *))(*(_QWORD *)v17 + 40LL))(v17, &bstrString);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3801;
      goto LABEL_61;
    }
    v6 = DwzXmlCreate(bstrString, &v15);
    v0 = v6;
    if ( v6 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", 3804, v6);
      v1 = v15;
      break;
    }
    v1 = v15;
    Package = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v15->lpVtbl->selectSingleNode)(
                v15,
                L"./ExtensionPoint/Icon",
                &v18);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3807;
      goto LABEL_61;
    }
    if ( !Package )
    {
      Package = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 208LL))(v18, &v19);
      v0 = Package;
      if ( Package < 0 )
      {
        v11 = 3811;
LABEL_61:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", v11, Package);
        break;
      }
      *(_QWORD *)v16 = v19;
      v19 = 0;
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    Package = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v1->lpVtbl->selectSingleNode)(
                v1,
                L"./ExtensionPoint/Maintenance",
                &v18);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3823;
      goto LABEL_61;
    }
    if ( !Package )
      *((_DWORD *)Config + 20) = 1;
    if ( !v2 )
    {
      Package = (*(__int64 (__fastcall **)(struct IPackage *, BSTR *))(*(_QWORD *)v17 + 80LL))(v17, &v14);
      v0 = Package;
      if ( Package < 0 )
      {
        v11 = 3834;
        goto LABEL_61;
      }
      if ( !SetDllDirectoryW(0) )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v0 = (unsigned __int16)LastError | 0x80070000;
        if ( v0 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", 3837, v0);
          break;
        }
      }
      if ( !SetDllDirectoryW(v14) )
      {
        v8 = GetLastError();
        v0 = v8;
        if ( v8 > 0 )
          v0 = (unsigned __int16)v8 | 0x80070000;
        if ( v0 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", 3840, v0);
          break;
        }
      }
      KeywordsFromFile = Configuration::LoadKeywordsFromFile(v1, L"./ExtensionPoint/HelpKeywords");
      if ( KeywordsFromFile < 0 )
        SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "Packages_SetupExtension", 3843, KeywordsFromFile);
      FeedbackContextIdFromFile = Configuration::LoadFeedbackContextIdFromFile(v1);
      if ( FeedbackContextIdFromFile < 0 )
        SdpDebugPrint(
          1u,
          "Dwz IGNORED: %s:%d - hr = 0x%08X\n",
          "Packages_SetupExtension",
          3849,
          FeedbackContextIdFromFile);
    }
    Package = (*(__int64 (__fastcall **)(struct IPackage *, PackageExtension *))(*(_QWORD *)v17 + 24LL))(v17, v16);
    v0 = Package;
    if ( Package < 0 )
    {
      v11 = 3853;
      goto LABEL_61;
    }
    ++v2;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v14 )
  {
    SysFreeString(v14);
    v14 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(struct IPackage *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v1 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v1->lpVtbl->Release)(v1);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v16 )
    PackageExtension::`scalar deleting destructor'(v16, v3);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14004b8dc  push    rbp
0x14004b8de  push    rbx
0x14004b8df  push    rsi
0x14004b8e0  push    rdi
0x14004b8e1  push    r12
0x14004b8e3  push    r14
0x14004b8e5  push    r15
0x14004b8e7  mov     rbp, rsp
0x14004b8ea  sub     rsp, 50h
0x14004b8ee  xor     r14d, r14d
0x14004b8f1  lea     r12, aPackagesSetupe; "Packages_SetupExtension"
0x14004b8f8  mov     ebx, r14d
0x14004b8fb  mov     [rbp+arg_8], r14
0x14004b8ff  mov     edi, r14d
0x14004b902  mov     [rbp+var_10], r14
0x14004b906  mov     [rbp+arg_10], r14
0x14004b90a  mov     esi, r14d
0x14004b90d  lea     r15d, [r14+1]
0x14004b911  mov     [rbp+bstrString], r14
0x14004b915  mov     [rbp+arg_18], r14
0x14004b919  mov     [rbp+var_18], r14
0x14004b91d  mov     [rbp+arg_0], r14
0x14004b921  call    ?Packages_GetNumber@@YAIXZ; Packages_GetNumber(void)
0x14004b926  cmp     esi, eax
0x14004b928  jnb     loc_14004BCCC
0x14004b92e  mov     rcx, [rbp+arg_8]
0x14004b932  test    rcx, rcx
0x14004b935  jz      short loc_14004B947
0x14004b937  mov     rax, [rcx]
0x14004b93a  mov     rax, [rax+10h]
0x14004b93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b943  mov     [rbp+arg_8], r14
0x14004b947  mov     rcx, [rbp+arg_10]
0x14004b94b  test    rcx, rcx
0x14004b94e  jz      short loc_14004B960
0x14004b950  mov     rax, [rcx]
0x14004b953  mov     rax, [rax+10h]
0x14004b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b95c  mov     [rbp+arg_10], r14
0x14004b960  test    rdi, rdi
0x14004b963  jz      short loc_14004B97B
0x14004b965  mov     rax, [rdi]
0x14004b968  mov     rcx, rdi
0x14004b96b  mov     rax, [rax+10h]
0x14004b96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b974  mov     rdi, r14
0x14004b977  mov     [rbp+var_10], r14
0x14004b97b  mov     rcx, [rbp+bstrString]; bstrString
0x14004b97f  test    rcx, rcx
0x14004b982  jz      short loc_14004B994
0x14004b984  call    cs:__imp_SysFreeString
0x14004b98b  nop     dword ptr [rax+rax+00h]
0x14004b990  mov     [rbp+bstrString], r14
0x14004b994  mov     rcx, [rbp+arg_18]; bstrString
0x14004b998  test    rcx, rcx
0x14004b99b  jz      short loc_14004B9AD
0x14004b99d  call    cs:__imp_SysFreeString
0x14004b9a4  nop     dword ptr [rax+rax+00h]
0x14004b9a9  mov     [rbp+arg_18], r14
0x14004b9ad  mov     rcx, [rbp+var_18]; bstrString
0x14004b9b1  test    rcx, rcx
0x14004b9b4  jz      short loc_14004B9C6
0x14004b9b6  call    cs:__imp_SysFreeString
0x14004b9bd  nop     dword ptr [rax+rax+00h]
0x14004b9c2  mov     [rbp+var_18], r14
0x14004b9c6  mov     rcx, [rbp+arg_0]; this
0x14004b9ca  test    rcx, rcx
0x14004b9cd  jz      short loc_14004B9D8
0x14004b9cf  call    ??_GPackageExtension@@QEAAPEAXI@Z; PackageExtension::`scalar deleting destructor'(uint)
0x14004b9d4  mov     [rbp+arg_0], r14
0x14004b9d8  lea     rdx, [rbp+arg_8]; struct IPackage **
0x14004b9dc  mov     ecx, esi; unsigned int
0x14004b9de  call    ?Packages_GetPackage@@YAJIPEAPEAVIPackage@@@Z; Packages_GetPackage(uint,IPackage * *)
0x14004b9e3  mov     ebx, eax
0x14004b9e5  test    eax, eax
0x14004b9e7  js      loc_14004BCB0
0x14004b9ed  mov     rcx, [rbp+arg_8]
0x14004b9f1  lea     rdx, [rbp+arg_0]
0x14004b9f5  mov     rax, [rcx]
0x14004b9f8  mov     rax, [rax+20h]
0x14004b9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ba01  mov     ebx, eax
0x14004ba03  test    eax, eax
0x14004ba05  js      loc_14004BCA8
0x14004ba0b  cmp     [rbp+arg_0], r14
0x14004ba0f  jnz     loc_14004BCA2
0x14004ba15  mov     ecx, 8; Size
0x14004ba1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004ba1f  mov     [rbp+arg_0], rax
0x14004ba23  test    rax, rax
0x14004ba26  jz      loc_14004BC8D
0x14004ba2c  mov     [rax], r14
0x14004ba2f  lea     rdx, [rbp+bstrString]
0x14004ba33  mov     rcx, [rbp+arg_8]
0x14004ba37  mov     [rbp+arg_0], rax
0x14004ba3b  mov     rax, [rcx]
0x14004ba3e  mov     rax, [rax+28h]
0x14004ba42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ba47  mov     ebx, eax
0x14004ba49  test    eax, eax
0x14004ba4b  js      loc_14004BC85
0x14004ba51  mov     rcx, [rbp+bstrString]; psz
0x14004ba55  lea     rdx, [rbp+var_10]; struct IXMLDOMDocument2 **
0x14004ba59  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14004ba5e  mov     ebx, eax
0x14004ba60  test    eax, eax
0x14004ba62  js      loc_14004BC63
0x14004ba68  mov     rdi, [rbp+var_10]
0x14004ba6c  lea     r8, [rbp+arg_10]
0x14004ba70  lea     rdx, aExtensionpoint_8; "./ExtensionPoint/Icon"
0x14004ba77  mov     rcx, rdi
0x14004ba7a  mov     rax, [rdi]
0x14004ba7d  mov     rax, [rax+128h]
0x14004ba84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ba89  mov     ebx, eax
0x14004ba8b  test    eax, eax
0x14004ba8d  js      loc_14004BC5B
0x14004ba93  jnz     short loc_14004BAC5
0x14004ba95  mov     rcx, [rbp+arg_10]
0x14004ba99  lea     rdx, [rbp+arg_18]
0x14004ba9d  mov     rax, [rcx]
0x14004baa0  mov     rax, [rax+0D0h]
0x14004baa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004baac  mov     ebx, eax
0x14004baae  test    eax, eax
0x14004bab0  js      loc_14004BC1D
0x14004bab6  mov     rax, [rbp+arg_18]
0x14004baba  mov     rcx, [rbp+arg_0]
0x14004babe  mov     [rcx], rax
0x14004bac1  mov     [rbp+arg_18], r14
0x14004bac5  mov     rcx, [rbp+arg_10]
0x14004bac9  test    rcx, rcx
0x14004bacc  jz      short loc_14004BADE
0x14004bace  mov     rax, [rcx]
0x14004bad1  mov     rax, [rax+10h]
0x14004bad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bada  mov     [rbp+arg_10], r14
0x14004bade  mov     rax, [rdi]
0x14004bae1  lea     r8, [rbp+arg_10]
0x14004bae5  lea     rdx, aExtensionpoint_15; "./ExtensionPoint/Maintenance"
0x14004baec  mov     rcx, rdi
0x14004baef  mov     rax, [rax+128h]
0x14004baf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bafb  mov     ebx, eax
0x14004bafd  test    eax, eax
0x14004baff  js      loc_14004BC53
0x14004bb05  jnz     short loc_14004BB12
0x14004bb07  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14004bb0e  mov     [rax+50h], r15d
0x14004bb12  test    esi, esi
0x14004bb14  jnz     loc_14004BBFB
0x14004bb1a  mov     rcx, [rbp+arg_8]
0x14004bb1e  lea     rdx, [rbp+var_18]
0x14004bb22  mov     rax, [rcx]
0x14004bb25  mov     rax, [rax+50h]
0x14004bb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bb2e  mov     ebx, eax
0x14004bb30  test    eax, eax
0x14004bb32  js      loc_14004BC43
0x14004bb38  xor     ecx, ecx; lpPathName
0x14004bb3a  call    cs:__imp_SetDllDirectoryW
0x14004bb41  nop     dword ptr [rax+rax+00h]
0x14004bb46  test    eax, eax
0x14004bb48  jnz     short loc_14004BB6D
0x14004bb4a  call    cs:__imp_GetLastError
0x14004bb51  nop     dword ptr [rax+rax+00h]
0x14004bb56  mov     ebx, eax
0x14004bb58  test    eax, eax
0x14004bb5a  jle     short loc_14004BB65
0x14004bb5c  movzx   ebx, ax
0x14004bb5f  or      ebx, 80070000h
0x14004bb65  test    ebx, ebx
0x14004bb67  js      loc_14004BC28
0x14004bb6d  mov     rcx, [rbp+var_18]; lpPathName
0x14004bb71  call    cs:__imp_SetDllDirectoryW
0x14004bb78  nop     dword ptr [rax+rax+00h]
0x14004bb7d  test    eax, eax
0x14004bb7f  jnz     short loc_14004BBA4
0x14004bb81  call    cs:__imp_GetLastError
0x14004bb88  nop     dword ptr [rax+rax+00h]
0x14004bb8d  mov     ebx, eax
0x14004bb8f  test    eax, eax
0x14004bb91  jle     short loc_14004BB9C
0x14004bb93  movzx   ebx, ax
0x14004bb96  or      ebx, 80070000h
0x14004bb9c  test    ebx, ebx
0x14004bb9e  js      loc_14004BC37
0x14004bba4  lea     rdx, aExtensionpoint_21; "./ExtensionPoint/HelpKeywords"
0x14004bbab  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14004bbae  call    ?LoadKeywordsFromFile@Configuration@@SAJPEAUIXMLDOMDocument2@@PEBG@Z; Configuration::LoadKeywordsFromFile(IXMLDOMDocument2 *,ushort const *)
0x14004bbb3  test    eax, eax
0x14004bbb5  jns     short loc_14004BBD3
0x14004bbb7  mov     r9d, 0F03h
0x14004bbbd  mov     [rsp+50h+var_30], eax
0x14004bbc1  mov     r8, r12
0x14004bbc4  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14004bbcb  mov     ecx, r15d; Level
0x14004bbce  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004bbd3  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14004bbd6  call    ?LoadFeedbackContextIdFromFile@Configuration@@SAJPEAUIXMLDOMDocument2@@@Z; Configuration::LoadFeedbackContextIdFromFile(IXMLDOMDocument2 *)
0x14004bbdb  test    eax, eax
0x14004bbdd  jns     short loc_14004BBFB
0x14004bbdf  mov     r9d, 0F09h
0x14004bbe5  mov     [rsp+50h+var_30], eax
0x14004bbe9  mov     r8, r12
0x14004bbec  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14004bbf3  mov     ecx, r15d; Level
0x14004bbf6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004bbfb  mov     rcx, [rbp+arg_8]
0x14004bbff  mov     rdx, [rbp+arg_0]
0x14004bc03  mov     rax, [rcx]
0x14004bc06  mov     rax, [rax+18h]
0x14004bc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bc0f  mov     ebx, eax
0x14004bc11  test    eax, eax
0x14004bc13  js      short loc_14004BC4B
0x14004bc15  add     esi, r15d
0x14004bc18  jmp     loc_14004B91D
0x14004bc1d  mov     r9d, 0EE3h
0x14004bc23  jmp     loc_14004BCB6
0x14004bc28  mov     [rsp+50h+var_30], ebx
0x14004bc2c  mov     r9d, 0EFDh
0x14004bc32  jmp     loc_14004BCBA
0x14004bc37  mov     [rsp+50h+var_30], ebx
0x14004bc3b  mov     r9d, 0F00h
0x14004bc41  jmp     short loc_14004BCBA
0x14004bc43  mov     r9d, 0EFAh
0x14004bc49  jmp     short loc_14004BCB6
0x14004bc4b  mov     r9d, 0F0Dh
0x14004bc51  jmp     short loc_14004BCB6
0x14004bc53  mov     r9d, 0EEFh
0x14004bc59  jmp     short loc_14004BCB6
0x14004bc5b  mov     r9d, 0EDFh
0x14004bc61  jmp     short loc_14004BCB6
0x14004bc63  mov     r9d, 0EDCh
0x14004bc69  mov     [rsp+50h+var_30], eax
0x14004bc6d  mov     r8, r12
0x14004bc70  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004bc77  mov     ecx, r15d; Level
0x14004bc7a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004bc7f  mov     rdi, [rbp+var_10]
0x14004bc83  jmp     short loc_14004BCCC
0x14004bc85  mov     r9d, 0ED9h
0x14004bc8b  jmp     short loc_14004BCB6
0x14004bc8d  mov     ebx, 8007000Eh
0x14004bc92  mov     [rbp+arg_0], r14
0x14004bc96  mov     [rsp+50h+var_30], ebx
0x14004bc9a  mov     r9d, 0ED3h
0x14004bca0  jmp     short loc_14004BCBA
0x14004bca2  mov     [rbp+arg_0], r14
0x14004bca6  jmp     short loc_14004BCCC
0x14004bca8  mov     r9d, 0ECBh
0x14004bcae  jmp     short loc_14004BCB6
0x14004bcb0  mov     r9d, 0EC8h
0x14004bcb6  mov     [rsp+50h+var_30], eax
0x14004bcba  mov     r8, r12
0x14004bcbd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004bcc4  mov     ecx, r15d; Level
0x14004bcc7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004bccc  mov     rcx, [rbp+bstrString]; bstrString
0x14004bcd0  test    rcx, rcx
0x14004bcd3  jz      short loc_14004BCE5
0x14004bcd5  call    cs:__imp_SysFreeString
0x14004bcdc  nop     dword ptr [rax+rax+00h]
0x14004bce1  mov     [rbp+bstrString], r14
0x14004bce5  mov     rcx, [rbp+arg_18]; bstrString
0x14004bce9  test    rcx, rcx
0x14004bcec  jz      short loc_14004BCFE
0x14004bcee  call    cs:__imp_SysFreeString
0x14004bcf5  nop     dword ptr [rax+rax+00h]
0x14004bcfa  mov     [rbp+arg_18], r14
0x14004bcfe  mov     rcx, [rbp+var_18]; bstrString
0x14004bd02  test    rcx, rcx
0x14004bd05  jz      short loc_14004BD17
0x14004bd07  call    cs:__imp_SysFreeString
0x14004bd0e  nop     dword ptr [rax+rax+00h]
0x14004bd13  mov     [rbp+var_18], r14
0x14004bd17  mov     rcx, [rbp+arg_8]
0x14004bd1b  test    rcx, rcx
0x14004bd1e  jz      short loc_14004BD30
0x14004bd20  mov     rax, [rcx]
0x14004bd23  mov     rax, [rax+10h]
0x14004bd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bd2c  mov     [rbp+arg_8], r14
0x14004bd30  test    rdi, rdi
0x14004bd33  jz      short loc_14004BD44
0x14004bd35  mov     rax, [rdi]
0x14004bd38  mov     rcx, rdi
0x14004bd3b  mov     rax, [rax+10h]
0x14004bd3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bd44  mov     rcx, [rbp+arg_10]
0x14004bd48  test    rcx, rcx
0x14004bd4b  jz      short loc_14004BD5D
0x14004bd4d  mov     rax, [rcx]
0x14004bd50  mov     rax, [rax+10h]
0x14004bd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bd59  mov     [rbp+arg_10], r14
0x14004bd5d  mov     rcx, [rbp+arg_0]; this
0x14004bd61  test    rcx, rcx
0x14004bd64  jz      short loc_14004BD6B
  ... truncated ...
```
