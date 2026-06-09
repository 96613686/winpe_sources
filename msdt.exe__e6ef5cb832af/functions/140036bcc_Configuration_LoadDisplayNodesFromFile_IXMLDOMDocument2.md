# Configuration::LoadDisplayNodesFromFile(IXMLDOMDocument2 *)

- ea: `0x140036bcc`
- end: `0x140037127`
- name: `?LoadDisplayNodesFromFile@Configuration@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `1371`
- prototype: `int(Configuration *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140036690`

## callees

- `0x140020420`
- `0x140036bcc`
- `0x14003896c`
- `0x140041020`
- `0x14004270c`
- `0x14004ae44`
- `0x14004aed8`
- `0x14004af7c`
- `0x14004b068`
- `0x14004b10c`
- `0x14004b234`
- `0x14004b388`
- `0x14004b42c`
- `0x14004b838`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140036c0b`
- `KERNEL32!HeapAlloc` at `0x140036c0b`
- `KERNEL32!HeapFree` at `0x140037101`
- `KERNEL32!HeapFree` at `0x140037101`
- `KERNEL32!GetProcessHeap` at `0x140036bf4`
- `KERNEL32!GetProcessHeap` at `0x1400370ed`
- `KERNEL32!GetProcessHeap` at `0x140036bf4`
- `KERNEL32!GetProcessHeap` at `0x1400370ed`
- `msvcrt!_wcsnicmp` at `0x140036e13`
- `msvcrt!_wcsnicmp` at `0x140036e33`
- `msvcrt!_wcsnicmp` at `0x140036e13`
- `msvcrt!_wcsnicmp` at `0x140036e33`
- `msvcrt!_wcsicmp` at `0x140036eef`
- `msvcrt!_wcsicmp` at `0x140036eef`
- `OLEAUT32!__imp_SysFreeString` at `0x140036cdf`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d3c`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d99`
- `OLEAUT32!__imp_SysFreeString` at `0x140036dda`
- `OLEAUT32!__imp_SysFreeString` at `0x140036e69`
- `OLEAUT32!__imp_SysFreeString` at `0x140036eaf`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f10`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036fa4`
- `OLEAUT32!__imp_SysFreeString` at `0x140037005`
- `OLEAUT32!__imp_SysFreeString` at `0x140037028`
- `OLEAUT32!__imp_SysFreeString` at `0x140037089`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370e1`
- `OLEAUT32!__imp_SysFreeString` at `0x140036cdf`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d3c`
- `OLEAUT32!__imp_SysFreeString` at `0x140036d99`
- `OLEAUT32!__imp_SysFreeString` at `0x140036dda`
- `OLEAUT32!__imp_SysFreeString` at `0x140036e69`
- `OLEAUT32!__imp_SysFreeString` at `0x140036eaf`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f10`
- `OLEAUT32!__imp_SysFreeString` at `0x140036f5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036fa4`
- `OLEAUT32!__imp_SysFreeString` at `0x140037005`
- `OLEAUT32!__imp_SysFreeString` at `0x140037028`
- `OLEAUT32!__imp_SysFreeString` at `0x140037089`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1400370e1`

## string_xrefs

- `0x140036fbb`: `cfg:PackageConfiguration/cfg:Execution/cfg:Icon`
- `0x14003703f`: `cfg:PackageConfiguration/cfg:Index/cfg:Category`
- `0x140036c24`: `Configuration::LoadDisplayNodesFromFile`
- `0x140036c6b`: `Configuration::LoadDisplayNodesFromFile`
- `0x140036cba`: `Configuration::LoadDisplayNodesFromFile`
- `0x140036d07`: `Configuration::LoadDisplayNodesFromFile`
- `0x140036c50`: `cfg:PackageConfiguration/cfg:Execution/cfg:Name`
- `0x140036d53`: `cfg:PackageConfiguration/cfg:Execution/cfg:Description`
- `0x140036df1`: `cfg:PackageConfiguration/cfg:Index/cfg:PrivacyUrl`
- `0x140036e80`: `cfg:PackageConfiguration/cfg:Index/cfg:PublisherName`
- `0x140036ec6`: `cfg:PackageConfiguration/cfg:Index/cfg:RequiresAdminPrivileges`
- `0x140036f27`: `cfg:PackageConfiguration/cfg:Index/cfg:Version`
- `0x140036f71`: `cfg:PackageConfiguration/cfg:Index/cfg:Id`

## pseudocode

```c
__int64 __fastcall Configuration::LoadDisplayNodesFromFile(Configuration *this, struct IXMLDOMDocument2 *a2)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // r14
  unsigned int v5; // ebx
  int v6; // r9d
  OLECHAR *v7; // rdi
  int v8; // eax
  int v9; // r9d
  int v10; // eax
  int v11; // r9d
  OLECHAR *v12; // rbx
  OLECHAR *v13; // rbx
  int v14; // eax
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rbx
  int v17; // eax
  OLECHAR *v18; // rbx
  OLECHAR *v19; // rbx
  HANDLE v20; // rax
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF

  bstrString = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v4 )
  {
    if ( (unsigned int)Configuration::TextFromSingleNode(
                         L"cfg:PackageConfiguration/cfg:Execution/cfg:Name",
                         a2,
                         &bstrString) )
    {
      v6 = 1015;
LABEL_5:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadDisplayNodesFromFile", v6, -2147024809);
      v5 = -2147024809;
LABEL_6:
      v7 = bstrString;
      goto LABEL_74;
    }
    v7 = bstrString;
    v8 = ExpandVariables(v4, 0x104u, bstrString);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 1021;
LABEL_9:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadDisplayNodesFromFile", v9, v8);
      goto LABEL_74;
    }
    if ( v7 )
    {
      SysFreeString(v7);
      bstrString = 0;
    }
    v10 = DwzTryLoadResourceString(v4, &bstrString);
    v5 = v10;
    if ( v10 >= 0 )
    {
      v12 = bstrString;
      Packages_SetName(bstrString);
      if ( v12 )
      {
        SysFreeString(v12);
        bstrString = 0;
      }
      if ( (unsigned int)Configuration::TextFromSingleNode(
                           L"cfg:PackageConfiguration/cfg:Execution/cfg:Description",
                           a2,
                           &bstrString) )
      {
        v6 = 1038;
        goto LABEL_5;
      }
      v7 = bstrString;
      v8 = ExpandVariables(v4, 0x104u, bstrString);
      v5 = v8;
      if ( v8 < 0 )
      {
        v9 = 1044;
        goto LABEL_9;
      }
      if ( v7 )
      {
        SysFreeString(v7);
        bstrString = 0;
      }
      v10 = DwzTryLoadResourceString(v4, &bstrString);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v13 = bstrString;
        Packages_SetDescription(bstrString);
        if ( v13 )
        {
          SysFreeString(v13);
          bstrString = 0;
        }
        v14 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:PrivacyUrl", a2, &bstrString);
        v7 = bstrString;
        if ( v14 || _wcsnicmp(bstrString, L"http://", 7u) && _wcsnicmp(v7, L"https://", 8u) )
        {
          v5 = -2147024809;
          SdpDebugPrint(
            1u,
            "Dwz ERROR: %s:%d - hr = 0x%08X\n",
            "Configuration::LoadDisplayNodesFromFile",
            1064,
            -2147024809);
          goto LABEL_74;
        }
        Packages_SetPrivacyLink(v7);
        if ( v7 )
        {
          SysFreeString(v7);
          bstrString = 0;
        }
        if ( (unsigned int)Configuration::TextFromSingleNode(
                             L"cfg:PackageConfiguration/cfg:Index/cfg:PublisherName",
                             a2,
                             &bstrString) )
        {
          v6 = 1076;
          goto LABEL_5;
        }
        v15 = bstrString;
        Packages_SetPublisher(bstrString);
        if ( v15 )
        {
          SysFreeString(v15);
          bstrString = 0;
        }
        if ( (unsigned int)Configuration::TextFromSingleNode(
                             L"cfg:PackageConfiguration/cfg:Index/cfg:RequiresAdminPrivileges",
                             a2,
                             &bstrString) )
        {
          v6 = 1088;
          goto LABEL_5;
        }
        v16 = bstrString;
        v17 = _wcsicmp(bstrString, L"true");
        Packages_SetElevation(v17 == 0);
        if ( v16 )
        {
          SysFreeString(v16);
          bstrString = 0;
        }
        v10 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:Version", a2, &bstrString);
        v5 = v10;
        if ( v10 >= 0 )
        {
          if ( !v10 )
          {
            v18 = bstrString;
            Packages_SetVersion(bstrString);
            if ( v18 )
            {
              SysFreeString(v18);
              bstrString = 0;
            }
          }
          v10 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:Id", a2, &bstrString);
          v5 = v10;
          if ( v10 >= 0 )
          {
            if ( !v10 )
            {
              v19 = bstrString;
              Packages_SetID(bstrString);
              if ( v19 )
              {
                SysFreeString(v19);
                bstrString = 0;
              }
            }
            v10 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Execution/cfg:Icon", a2, &bstrString);
            v5 = v10;
            if ( v10 >= 0 )
            {
              v7 = bstrString;
              if ( !v10 )
              {
                v8 = ExpandVariables(v4, 0x104u, bstrString);
                v5 = v8;
                if ( v8 < 0 )
                {
                  v9 = 1123;
                  goto LABEL_9;
                }
                if ( v7 )
                {
                  SysFreeString(v7);
                  v7 = 0;
                  bstrString = 0;
                }
                Packages_SetIcon(v4);
              }
              if ( v7 )
              {
                SysFreeString(v7);
                bstrString = 0;
              }
              v10 = Configuration::TextFromSingleNode(
                      L"cfg:PackageConfiguration/cfg:Index/cfg:Category",
                      a2,
                      &bstrString);
              v5 = v10;
              if ( v10 >= 0 )
              {
                v7 = bstrString;
                if ( !v10 )
                {
                  v8 = ExpandVariables(v4, 0x104u, bstrString);
                  v5 = v8;
                  if ( v8 < 0 )
                  {
                    v9 = 1143;
                    goto LABEL_9;
                  }
                  if ( v7 )
                  {
                    SysFreeString(v7);
                    bstrString = 0;
                  }
                  v10 = DwzTryLoadResourceString(v4, &bstrString);
                  v5 = v10;
                  if ( v10 < 0 )
                  {
                    v11 = 1148;
                    goto LABEL_15;
                  }
                  v7 = bstrString;
                  Packages_SetCategory(bstrString);
                }
                if ( !v7 )
                {
LABEL_76:
                  v20 = GetProcessHeap();
                  HeapFree(v20, 0, v4);
                  return v5;
                }
                SysFreeString(v7);
                v7 = 0;
LABEL_74:
                if ( v7 )
                  SysFreeString(v7);
                goto LABEL_76;
              }
              v11 = 1136;
            }
            else
            {
              v11 = 1117;
            }
          }
          else
          {
            v11 = 1107;
          }
        }
        else
        {
          v11 = 1097;
        }
      }
      else
      {
        v11 = 1049;
      }
    }
    else
    {
      v11 = 1026;
    }
LABEL_15:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadDisplayNodesFromFile", v11, v10);
    goto LABEL_6;
  }
  v5 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadDisplayNodesFromFile", 1006, -2147024882);
  return v5;
}

```

## disassembly

```asm
0x140036bcc  mov     [rsp-28h+arg_8], rbx
0x140036bd1  mov     [rsp-28h+arg_10], rsi
0x140036bd6  mov     [rsp-28h+bstrString], rcx
0x140036bdb  push    rbp
0x140036bdc  push    rdi
0x140036bdd  push    r12
0x140036bdf  push    r14
0x140036be1  push    r15
0x140036be3  mov     rbp, rsp
0x140036be6  sub     rsp, 30h
0x140036bea  xor     r15d, r15d
0x140036bed  mov     rsi, rdx
0x140036bf0  mov     [rbp+bstrString], r15
0x140036bf4  call    cs:__imp_GetProcessHeap
0x140036bfb  nop     dword ptr [rax+rax+00h]
0x140036c00  xor     edx, edx; dwFlags
0x140036c02  mov     r8d, 208h; dwBytes
0x140036c08  mov     rcx, rax; hHeap
0x140036c0b  call    cs:__imp_HeapAlloc
0x140036c12  nop     dword ptr [rax+rax+00h]
0x140036c17  mov     r14, rax
0x140036c1a  test    rax, rax
0x140036c1d  jnz     short loc_140036C49
0x140036c1f  mov     ebx, 8007000Eh
0x140036c24  lea     r8, aConfigurationL_2; "Configuration::LoadDisplayNodesFromFile"
0x140036c2b  mov     r9d, 3EEh
0x140036c31  mov     [rsp+30h+var_10], ebx
0x140036c35  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036c3c  lea     ecx, [rax+1]; Level
0x140036c3f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036c44  jmp     loc_14003710D
0x140036c49  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036c4d  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036c50  lea     rcx, aCfgPackageconf_10; "cfg:PackageConfiguration/cfg:Execution/"...
0x140036c57  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036c5c  test    eax, eax
0x140036c5e  jz      short loc_140036C92
0x140036c60  mov     r9d, 3F7h
0x140036c66  mov     esi, 80070057h
0x140036c6b  lea     r8, aConfigurationL_2; "Configuration::LoadDisplayNodesFromFile"
0x140036c72  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036c79  mov     [rsp+30h+var_10], esi
0x140036c7d  mov     ecx, 1; Level
0x140036c82  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036c87  mov     ebx, esi
0x140036c89  mov     rdi, [rbp+bstrString]
0x140036c8d  jmp     loc_1400370D9
0x140036c92  mov     rdi, [rbp+bstrString]
0x140036c96  mov     r12d, 104h
0x140036c9c  mov     r8, rdi; lpSrc
0x140036c9f  mov     edx, r12d; unsigned __int64
0x140036ca2  mov     rcx, r14; unsigned __int16 *
0x140036ca5  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140036caa  mov     ebx, eax
0x140036cac  test    eax, eax
0x140036cae  jns     short loc_140036CD7
0x140036cb0  mov     r9d, 3FDh
0x140036cb6  mov     [rsp+30h+var_10], eax
0x140036cba  lea     r8, aConfigurationL_2; "Configuration::LoadDisplayNodesFromFile"
0x140036cc1  mov     ecx, 1; Level
0x140036cc6  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036ccd  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036cd2  jmp     loc_1400370D9
0x140036cd7  test    rdi, rdi
0x140036cda  jz      short loc_140036CEF
0x140036cdc  mov     rcx, rdi; bstrString
0x140036cdf  call    cs:__imp_SysFreeString
0x140036ce6  nop     dword ptr [rax+rax+00h]
0x140036ceb  mov     [rbp+bstrString], r15
0x140036cef  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140036cf3  mov     rcx, r14; psz
0x140036cf6  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x140036cfb  mov     ebx, eax
0x140036cfd  test    eax, eax
0x140036cff  jns     short loc_140036D28
0x140036d01  mov     r9d, 402h
0x140036d07  lea     r8, aConfigurationL_2; "Configuration::LoadDisplayNodesFromFile"
0x140036d0e  mov     [rsp+30h+var_10], eax
0x140036d12  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036d19  mov     ecx, 1; Level
0x140036d1e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036d23  jmp     loc_140036C89
0x140036d28  mov     rbx, [rbp+bstrString]
0x140036d2c  mov     rcx, rbx; psz
0x140036d2f  call    ?Packages_SetName@@YAXPEBG@Z; Packages_SetName(ushort const *)
0x140036d34  test    rbx, rbx
0x140036d37  jz      short loc_140036D4C
0x140036d39  mov     rcx, rbx; bstrString
0x140036d3c  call    cs:__imp_SysFreeString
0x140036d43  nop     dword ptr [rax+rax+00h]
0x140036d48  mov     [rbp+bstrString], r15
0x140036d4c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036d50  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036d53  lea     rcx, aCfgPackageconf_0; "cfg:PackageConfiguration/cfg:Execution/"...
0x140036d5a  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036d5f  test    eax, eax
0x140036d61  jz      short loc_140036D6E
0x140036d63  mov     r9d, 40Eh
0x140036d69  jmp     loc_140036C66
0x140036d6e  mov     rdi, [rbp+bstrString]
0x140036d72  mov     rdx, r12; unsigned __int64
0x140036d75  mov     r8, rdi; lpSrc
0x140036d78  mov     rcx, r14; unsigned __int16 *
0x140036d7b  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140036d80  mov     ebx, eax
0x140036d82  test    eax, eax
0x140036d84  jns     short loc_140036D91
0x140036d86  mov     r9d, 414h
0x140036d8c  jmp     loc_140036CB6
0x140036d91  test    rdi, rdi
0x140036d94  jz      short loc_140036DA9
0x140036d96  mov     rcx, rdi; bstrString
0x140036d99  call    cs:__imp_SysFreeString
0x140036da0  nop     dword ptr [rax+rax+00h]
0x140036da5  mov     [rbp+bstrString], r15
0x140036da9  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140036dad  mov     rcx, r14; psz
0x140036db0  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x140036db5  mov     ebx, eax
0x140036db7  test    eax, eax
0x140036db9  jns     short loc_140036DC6
0x140036dbb  mov     r9d, 419h
0x140036dc1  jmp     loc_140036D07
0x140036dc6  mov     rbx, [rbp+bstrString]
0x140036dca  mov     rcx, rbx; psz
0x140036dcd  call    ?Packages_SetDescription@@YAXPEBG@Z; Packages_SetDescription(ushort const *)
0x140036dd2  test    rbx, rbx
0x140036dd5  jz      short loc_140036DEA
0x140036dd7  mov     rcx, rbx; bstrString
0x140036dda  call    cs:__imp_SysFreeString
0x140036de1  nop     dword ptr [rax+rax+00h]
0x140036de6  mov     [rbp+bstrString], r15
0x140036dea  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036dee  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036df1  lea     rcx, aCfgPackageconf_5; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036df8  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036dfd  mov     rdi, [rbp+bstrString]
0x140036e01  test    eax, eax
0x140036e03  jnz     short loc_140036E43
0x140036e05  lea     r8d, [rax+7]; MaxCount
0x140036e09  mov     rcx, rdi; String1
0x140036e0c  lea     rdx, aHttp; "http://"
0x140036e13  call    cs:__imp__wcsnicmp
0x140036e1a  nop     dword ptr [rax+rax+00h]
0x140036e1f  test    eax, eax
0x140036e21  jz      short loc_140036E59
0x140036e23  mov     r8d, 8; MaxCount
0x140036e29  lea     rdx, aHttps; "https://"
0x140036e30  mov     rcx, rdi; String1
0x140036e33  call    cs:__imp__wcsnicmp
0x140036e3a  nop     dword ptr [rax+rax+00h]
0x140036e3f  test    eax, eax
0x140036e41  jz      short loc_140036E59
0x140036e43  mov     esi, 80070057h
0x140036e48  mov     r9d, 428h
0x140036e4e  mov     ebx, esi
0x140036e50  mov     [rsp+30h+var_10], esi
0x140036e54  jmp     loc_140036CBA
0x140036e59  mov     rcx, rdi; psz
0x140036e5c  call    ?Packages_SetPrivacyLink@@YAXPEBG@Z; Packages_SetPrivacyLink(ushort const *)
0x140036e61  test    rdi, rdi
0x140036e64  jz      short loc_140036E79
0x140036e66  mov     rcx, rdi; bstrString
0x140036e69  call    cs:__imp_SysFreeString
0x140036e70  nop     dword ptr [rax+rax+00h]
0x140036e75  mov     [rbp+bstrString], r15
0x140036e79  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036e7d  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036e80  lea     rcx, aCfgPackageconf_7; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036e87  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036e8c  test    eax, eax
0x140036e8e  jz      short loc_140036E9B
0x140036e90  mov     r9d, 434h
0x140036e96  jmp     loc_140036C66
0x140036e9b  mov     rbx, [rbp+bstrString]
0x140036e9f  mov     rcx, rbx; psz
0x140036ea2  call    ?Packages_SetPublisher@@YAXPEBG@Z; Packages_SetPublisher(ushort const *)
0x140036ea7  test    rbx, rbx
0x140036eaa  jz      short loc_140036EBF
0x140036eac  mov     rcx, rbx; bstrString
0x140036eaf  call    cs:__imp_SysFreeString
0x140036eb6  nop     dword ptr [rax+rax+00h]
0x140036ebb  mov     [rbp+bstrString], r15
0x140036ebf  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036ec3  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036ec6  lea     rcx, aCfgPackageconf_6; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036ecd  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036ed2  test    eax, eax
0x140036ed4  jz      short loc_140036EE1
0x140036ed6  mov     r9d, 440h
0x140036edc  jmp     loc_140036C66
0x140036ee1  mov     rbx, [rbp+bstrString]
0x140036ee5  lea     rdx, aTrue; "true"
0x140036eec  mov     rcx, rbx; String1
0x140036eef  call    cs:__imp__wcsicmp
0x140036ef6  nop     dword ptr [rax+rax+00h]
0x140036efb  test    eax, eax
0x140036efd  mov     ecx, r15d
0x140036f00  setz    cl; int
0x140036f03  call    ?Packages_SetElevation@@YAXH@Z; Packages_SetElevation(int)
0x140036f08  test    rbx, rbx
0x140036f0b  jz      short loc_140036F20
0x140036f0d  mov     rcx, rbx; bstrString
0x140036f10  call    cs:__imp_SysFreeString
0x140036f17  nop     dword ptr [rax+rax+00h]
0x140036f1c  mov     [rbp+bstrString], r15
0x140036f20  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036f24  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036f27  lea     rcx, aCfgPackageconf_3; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036f2e  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036f33  mov     ebx, eax
0x140036f35  test    eax, eax
0x140036f37  jns     short loc_140036F44
0x140036f39  mov     r9d, 449h
0x140036f3f  jmp     loc_140036D07
0x140036f44  jnz     short loc_140036F6A
0x140036f46  mov     rbx, [rbp+bstrString]
0x140036f4a  mov     rcx, rbx; psz
0x140036f4d  call    ?Packages_SetVersion@@YAXPEBG@Z; Packages_SetVersion(ushort const *)
0x140036f52  test    rbx, rbx
0x140036f55  jz      short loc_140036F6A
0x140036f57  mov     rcx, rbx; bstrString
0x140036f5a  call    cs:__imp_SysFreeString
0x140036f61  nop     dword ptr [rax+rax+00h]
0x140036f66  mov     [rbp+bstrString], r15
0x140036f6a  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036f6e  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036f71  lea     rcx, aCfgPackageconf_2; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036f78  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036f7d  mov     ebx, eax
0x140036f7f  test    eax, eax
0x140036f81  jns     short loc_140036F8E
0x140036f83  mov     r9d, 453h
0x140036f89  jmp     loc_140036D07
0x140036f8e  jnz     short loc_140036FB4
0x140036f90  mov     rbx, [rbp+bstrString]
0x140036f94  mov     rcx, rbx; psz
0x140036f97  call    ?Packages_SetID@@YAXPEBG@Z; Packages_SetID(ushort const *)
0x140036f9c  test    rbx, rbx
0x140036f9f  jz      short loc_140036FB4
0x140036fa1  mov     rcx, rbx; bstrString
0x140036fa4  call    cs:__imp_SysFreeString
0x140036fab  nop     dword ptr [rax+rax+00h]
0x140036fb0  mov     [rbp+bstrString], r15
0x140036fb4  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036fb8  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036fbb  lea     rcx, aCfgPackageconf_9; "cfg:PackageConfiguration/cfg:Execution/"...
0x140036fc2  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036fc7  mov     ebx, eax
0x140036fc9  test    eax, eax
0x140036fcb  jns     short loc_140036FD8
0x140036fcd  mov     r9d, 45Dh
0x140036fd3  jmp     loc_140036D07
0x140036fd8  mov     rdi, [rbp+bstrString]
0x140036fdc  jnz     short loc_140037020
0x140036fde  mov     r8, rdi; lpSrc
0x140036fe1  mov     rdx, r12; unsigned __int64
0x140036fe4  mov     rcx, r14; unsigned __int16 *
0x140036fe7  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140036fec  mov     ebx, eax
0x140036fee  test    eax, eax
0x140036ff0  jns     short loc_140036FFD
0x140036ff2  mov     r9d, 463h
0x140036ff8  jmp     loc_140036CB6
0x140036ffd  test    rdi, rdi
0x140037000  jz      short loc_140037018
0x140037002  mov     rcx, rdi; bstrString
0x140037005  call    cs:__imp_SysFreeString
0x14003700c  nop     dword ptr [rax+rax+00h]
0x140037011  mov     rdi, r15
0x140037014  mov     [rbp+bstrString], r15
0x140037018  mov     rcx, r14; psz
0x14003701b  call    ?Packages_SetIcon@@YAXPEBG@Z; Packages_SetIcon(ushort const *)
0x140037020  test    rdi, rdi
0x140037023  jz      short loc_140037038
0x140037025  mov     rcx, rdi; bstrString
0x140037028  call    cs:__imp_SysFreeString
0x14003702f  nop     dword ptr [rax+rax+00h]
0x140037034  mov     [rbp+bstrString], r15
0x140037038  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14003703c  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x14003703f  lea     rcx, aCfgPackageconf; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140037046  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x14003704b  mov     ebx, eax
0x14003704d  test    eax, eax
0x14003704f  jns     short loc_14003705C
0x140037051  mov     r9d, 470h
0x140037057  jmp     loc_140036D07
0x14003705c  mov     rdi, [rbp+bstrString]
0x140037060  jnz     short loc_1400370C2
0x140037062  mov     r8, rdi; lpSrc
0x140037065  mov     rdx, r12; unsigned __int64
0x140037068  mov     rcx, r14; unsigned __int16 *
0x14003706b  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140037070  mov     ebx, eax
0x140037072  test    eax, eax
0x140037074  jns     short loc_140037081
0x140037076  mov     r9d, 477h
0x14003707c  jmp     loc_140036CB6
0x140037081  test    rdi, rdi
  ... truncated ...
```
