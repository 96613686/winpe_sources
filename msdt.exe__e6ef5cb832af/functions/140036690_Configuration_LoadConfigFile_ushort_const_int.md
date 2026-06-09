# Configuration::LoadConfigFile(ushort const *,int *)

- ea: `0x140036690`
- end: `0x140036bc3`
- name: `?LoadConfigFile@Configuration@@QEAAJPEBGPEAH@Z`
- size: `1331`
- prototype: `__int64 __fastcall(Configuration *__hidden this, LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x140037e2c`

## callees

- `0x140020420`
- `0x140021a54`
- `0x140021cf8`
- `0x140022070`
- `0x14003504c`
- `0x140036690`
- `0x140036bcc`
- `0x14003744c`
- `0x140037b90`
- `0x14003896c`
- `0x140041020`
- `0x14004270c`
- `0x14004ae44`
- `0x14004b10c`
- `0x14004b2d8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400366fa`
- `KERNEL32!HeapAlloc` at `0x1400366fa`
- `KERNEL32!HeapFree` at `0x1400368d4`
- `KERNEL32!HeapFree` at `0x140036b52`
- `KERNEL32!HeapFree` at `0x140036b77`
- `KERNEL32!HeapFree` at `0x140036b9c`
- `KERNEL32!HeapFree` at `0x1400368d4`
- `KERNEL32!HeapFree` at `0x140036b52`
- `KERNEL32!HeapFree` at `0x140036b77`
- `KERNEL32!HeapFree` at `0x140036b9c`
- `KERNEL32!GetProcessHeap` at `0x1400366e3`
- `KERNEL32!GetProcessHeap` at `0x1400368c0`
- `KERNEL32!GetProcessHeap` at `0x140036b3e`
- `KERNEL32!GetProcessHeap` at `0x140036b63`
- `KERNEL32!GetProcessHeap` at `0x140036b88`
- `KERNEL32!GetProcessHeap` at `0x1400366e3`
- `KERNEL32!GetProcessHeap` at `0x1400368c0`
- `KERNEL32!GetProcessHeap` at `0x140036b3e`
- `KERNEL32!GetProcessHeap` at `0x140036b63`
- `KERNEL32!GetProcessHeap` at `0x140036b88`
- `msvcrt!_wcsnicmp` at `0x14003688c`
- `msvcrt!_wcsnicmp` at `0x14003688c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400369e2`
- `OLEAUT32!__imp_SysFreeString` at `0x140036a04`
- `OLEAUT32!__imp_SysFreeString` at `0x140036a66`
- `OLEAUT32!__imp_SysFreeString` at `0x140036aab`
- `OLEAUT32!__imp_SysFreeString` at `0x140036b2d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400369e2`
- `OLEAUT32!__imp_SysFreeString` at `0x140036a04`
- `OLEAUT32!__imp_SysFreeString` at `0x140036a66`
- `OLEAUT32!__imp_SysFreeString` at `0x140036aab`
- `OLEAUT32!__imp_SysFreeString` at `0x140036b2d`

## string_xrefs

- `0x140036713`: `Configuration::LoadConfigFile`
- `0x140036754`: `Configuration::LoadConfigFile`
- `0x140036990`: `Configuration::LoadConfigFile`
- `0x140036ad8`: `Configuration::LoadConfigFile`
- `0x1400367a9`: `SupportPackageConfiguration`
- `0x140036927`: `cfg:PackageConfiguration/cfg:Execution/cfg:Disconnected`
- `0x140036978`: `cfg:PackageConfiguration/cfg:Execution/cfg:Icon`
- `0x140036a1f`: `cfg:PackageConfiguration/cfg:Index/cfg:Category`
- `0x140036ab9`: `cfg:PackageConfiguration/cfg:Index/cfg:Keyword`

## pseudocode

```c
__int64 __fastcall Configuration::LoadConfigFile(Configuration *this, LPCWSTR lpFileName, int *a3)
{
  OLECHAR *v6; // r12
  unsigned __int16 *v7; // rsi
  OLECHAR *v8; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // r15
  unsigned int v11; // ebx
  int v12; // eax
  int DisplayNodesFromFile; // eax
  struct IXMLDOMDocument2 *v14; // rsi
  int v15; // r9d
  const wchar_t *v16; // r11
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  HANDLE v19; // rax
  Configuration *v20; // rcx
  int v21; // eax
  int v22; // r9d
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  unsigned __int16 *v27; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v29; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v30; // [rsp+48h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+58h] BYREF

  v33 = 0;
  g_ErrorContext = 401;
  v6 = 0;
  lpMem = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  bstrString = 0;
  v29 = 0;
  v30 = 0;
  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v10 )
  {
    v11 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadConfigFile", 855, -2147024882);
    goto LABEL_64;
  }
  v12 = Configuration::CanonicalizeFilePath(lpFileName, (unsigned __int16 **)&lpMem);
  v11 = v12;
  if ( v12 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadConfigFile", 858, v12);
    v6 = (OLECHAR *)lpMem;
    goto LABEL_64;
  }
  v6 = (OLECHAR *)lpMem;
  Packages_SetPath((OLECHAR *)lpMem);
  DisplayNodesFromFile = DwzXmlLoad(v6, &v29);
  v14 = v29;
  v11 = DisplayNodesFromFile;
  if ( DisplayNodesFromFile < 0 )
  {
    v15 = 863;
LABEL_60:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadConfigFile", v15, DisplayNodesFromFile);
    goto LABEL_61;
  }
  DisplayNodesFromFile = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v29->lpVtbl->selectSingleNode)(
                           v29,
                           L"SupportPackageConfiguration",
                           &v33);
  v11 = DisplayNodesFromFile;
  if ( DisplayNodesFromFile < 0 )
  {
    v15 = 866;
    goto LABEL_60;
  }
  if ( DisplayNodesFromFile )
  {
    if ( v33 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v33 = 0;
    }
    DisplayNodesFromFile = ExpandVariables(v10, 0x104u, L"%windir%\\diagnostics\\index\\");
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 880;
      goto LABEL_60;
    }
    DisplayNodesFromFile = Configuration::CanonicalizeFilePath(v10, &v27);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 883;
      goto LABEL_60;
    }
    DisplayNodesFromFile = StringCchLengthW(v27, 0x104u, &v30);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 889;
      goto LABEL_60;
    }
    v17 = _wcsnicmp(lpFileName, v16, v30 - 1);
    *((_DWORD *)this + 1) = v17 == 0;
    if ( v17 )
    {
      v11 = -2147024891;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadConfigFile", 895, -2147024891);
      goto LABEL_61;
    }
    if ( v6 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v6);
      v6 = 0;
    }
    *((_DWORD *)this + 66) = 7;
    DisplayNodesFromFile = DwzXmlSetSelectionNamespace(v14, v18);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 903;
      goto LABEL_60;
    }
    DisplayNodesFromFile = Configuration::LoadDisplayNodesFromFile(v20, v14);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 906;
      goto LABEL_60;
    }
    DisplayNodesFromFile = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v14->lpVtbl->selectSingleNode)(
                             v14,
                             L"cfg:PackageConfiguration/cfg:Execution/cfg:Disconnected",
                             &v33);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v15 = 912;
      goto LABEL_60;
    }
    if ( !DisplayNodesFromFile )
      *((_DWORD *)this + 8) = 1;
    if ( v33 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v33 = 0;
    }
    v21 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Execution/cfg:Icon", v14, &bstrString);
    v11 = v21;
    if ( v21 >= 0 )
    {
      v8 = bstrString;
      if ( !v21 )
      {
        DisplayNodesFromFile = ExpandVariables(v10, 0x104u, bstrString);
        v11 = DisplayNodesFromFile;
        if ( DisplayNodesFromFile < 0 )
        {
          v15 = 929;
          goto LABEL_60;
        }
        if ( v8 )
        {
          SysFreeString(v8);
          v8 = 0;
          bstrString = 0;
        }
        Packages_SetIcon(v10);
      }
      if ( v8 )
      {
        SysFreeString(v8);
        bstrString = 0;
      }
      v21 = Configuration::TextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:Category", v14, &bstrString);
      v11 = v21;
      if ( v21 >= 0 )
      {
        v8 = bstrString;
        if ( !v21 )
        {
          DisplayNodesFromFile = ExpandVariables(v10, 0x104u, bstrString);
          v11 = DisplayNodesFromFile;
          if ( DisplayNodesFromFile < 0 )
          {
            v15 = 949;
            goto LABEL_60;
          }
          if ( v8 )
          {
            SysFreeString(v8);
            bstrString = 0;
          }
          v21 = DwzTryLoadResourceString(v10, &bstrString);
          v11 = v21;
          if ( v21 < 0 )
          {
            v22 = 954;
            goto LABEL_37;
          }
          v8 = bstrString;
          Packages_SetCategory(bstrString);
        }
        if ( v8 )
        {
          SysFreeString(v8);
          v8 = 0;
        }
        DisplayNodesFromFile = Configuration::LoadKeywordsFromFile(
                                 v14,
                                 L"cfg:PackageConfiguration/cfg:Index/cfg:Keyword");
        v11 = DisplayNodesFromFile;
        if ( DisplayNodesFromFile >= 0 )
          goto LABEL_61;
        v15 = 962;
        goto LABEL_60;
      }
      v22 = 942;
    }
    else
    {
      v22 = 923;
    }
LABEL_37:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::LoadConfigFile", v22, v21);
    v8 = bstrString;
    goto LABEL_61;
  }
  DisplayNodesFromFile = Configuration::LoadSupport(this, v14);
  v11 = DisplayNodesFromFile;
  if ( DisplayNodesFromFile < 0 )
  {
    v15 = 869;
    goto LABEL_60;
  }
  *a3 = 1;
LABEL_61:
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->Release)(v14);
  v7 = v27;
LABEL_64:
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v8 )
    SysFreeString(v8);
  if ( v6 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v6);
  }
  if ( v10 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v10);
  }
  if ( v7 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v7);
  }
  return v11;
}

```

## disassembly

```asm
0x140036690  mov     [rsp-38h+arg_0], rbx
0x140036695  mov     [rsp-38h+String1], rdx
0x14003669a  push    rbp
0x14003669b  push    rsi
0x14003669c  push    rdi
0x14003669d  push    r12
0x14003669f  push    r13
0x1400366a1  push    r14
0x1400366a3  push    r15
0x1400366a5  mov     rbp, rsp
0x1400366a8  sub     rsp, 50h
0x1400366ac  xor     eax, eax
0x1400366ae  mov     r13, r8
0x1400366b1  mov     [rbp+arg_18], rax
0x1400366b5  mov     rbx, rdx
0x1400366b8  mov     cs:?g_ErrorContext@@3IC, 191h; uint volatile g_ErrorContext
0x1400366c2  mov     r14, rcx
0x1400366c5  mov     r12d, eax
0x1400366c8  mov     [rbp+lpMem], rax
0x1400366cc  mov     esi, eax
0x1400366ce  mov     [rbp+var_20], rax
0x1400366d2  mov     edi, eax
0x1400366d4  mov     [rbp+bstrString], rax
0x1400366d8  mov     [rbp+var_10], rax
0x1400366dc  mov     [rbp+var_8], rax
0x1400366e0  mov     [r8], eax
0x1400366e3  call    cs:__imp_GetProcessHeap
0x1400366ea  nop     dword ptr [rax+rax+00h]
0x1400366ef  xor     edx, edx; dwFlags
0x1400366f1  mov     r8d, 208h; dwBytes
0x1400366f7  mov     rcx, rax; hHeap
0x1400366fa  call    cs:__imp_HeapAlloc
0x140036701  nop     dword ptr [rax+rax+00h]
0x140036706  mov     r15, rax
0x140036709  test    rax, rax
0x14003670c  jnz     short loc_140036738
0x14003670e  mov     ebx, 8007000Eh
0x140036713  lea     r8, aConfigurationL_4; "Configuration::LoadConfigFile"
0x14003671a  mov     r9d, 357h
0x140036720  mov     [rsp+50h+var_30], ebx
0x140036724  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003672b  lea     ecx, [rdi+1]; Level
0x14003672e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036733  jmp     loc_140036B08
0x140036738  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x14003673c  mov     rcx, rbx; lpFileName
0x14003673f  call    ?CanonicalizeFilePath@Configuration@@SAJPEBGPEAPEAG@Z; Configuration::CanonicalizeFilePath(ushort const *,ushort * *)
0x140036744  mov     ebx, eax
0x140036746  test    eax, eax
0x140036748  jns     short loc_140036775
0x14003674a  mov     r9d, 35Ah
0x140036750  mov     [rsp+50h+var_30], eax
0x140036754  lea     r8, aConfigurationL_4; "Configuration::LoadConfigFile"
0x14003675b  mov     ecx, 1; Level
0x140036760  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036767  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003676c  mov     r12, [rbp+lpMem]
0x140036770  jmp     loc_140036B08
0x140036775  mov     r12, [rbp+lpMem]
0x140036779  mov     rcx, r12; psz
0x14003677c  call    ?Packages_SetPath@@YAJPEBG@Z; Packages_SetPath(ushort const *)
0x140036781  lea     rdx, [rbp+var_10]; struct IXMLDOMDocument2 **
0x140036785  mov     rcx, r12; psz
0x140036788  call    ?DwzXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlLoad(ushort const *,IXMLDOMDocument2 * *)
0x14003678d  mov     rsi, [rbp+var_10]
0x140036791  mov     ebx, eax
0x140036793  test    eax, eax
0x140036795  jns     short loc_1400367A2
0x140036797  mov     r9d, 35Fh
0x14003679d  jmp     loc_140036AD4
0x1400367a2  mov     rax, [rsi]
0x1400367a5  lea     r8, [rbp+arg_18]
0x1400367a9  lea     rdx, aSupportpackage; "SupportPackageConfiguration"
0x1400367b0  mov     rcx, rsi
0x1400367b3  mov     rax, [rax+128h]
0x1400367ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400367bf  mov     ebx, eax
0x1400367c1  test    eax, eax
0x1400367c3  jns     short loc_1400367D0
0x1400367c5  mov     r9d, 362h
0x1400367cb  jmp     loc_140036AD4
0x1400367d0  jnz     short loc_1400367FB
0x1400367d2  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x1400367d5  mov     rcx, r14; this
0x1400367d8  call    ?LoadSupport@Configuration@@AEAAJPEAUIXMLDOMDocument2@@@Z; Configuration::LoadSupport(IXMLDOMDocument2 *)
0x1400367dd  mov     ebx, eax
0x1400367df  test    eax, eax
0x1400367e1  jns     short loc_1400367EE
0x1400367e3  mov     r9d, 365h
0x1400367e9  jmp     loc_140036AD4
0x1400367ee  mov     dword ptr [r13+0], 1
0x1400367f6  jmp     loc_140036AF0
0x1400367fb  mov     rcx, [rbp+arg_18]
0x1400367ff  test    rcx, rcx
0x140036802  jz      short loc_140036814
0x140036804  mov     rax, [rcx]
0x140036807  mov     rax, [rax+10h]
0x14003680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036810  mov     [rbp+arg_18], rdi
0x140036814  mov     r13d, 104h
0x14003681a  lea     r8, aWindirDiagnost; "%windir%\\diagnostics\\index\\"
0x140036821  mov     edx, r13d; unsigned __int64
0x140036824  mov     rcx, r15; unsigned __int16 *
0x140036827  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x14003682c  mov     ebx, eax
0x14003682e  test    eax, eax
0x140036830  jns     short loc_14003683D
0x140036832  mov     r9d, 370h
0x140036838  jmp     loc_140036AD4
0x14003683d  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x140036841  mov     rcx, r15; lpFileName
0x140036844  call    ?CanonicalizeFilePath@Configuration@@SAJPEBGPEAPEAG@Z; Configuration::CanonicalizeFilePath(ushort const *,ushort * *)
0x140036849  mov     ebx, eax
0x14003684b  test    eax, eax
0x14003684d  jns     short loc_14003685A
0x14003684f  mov     r9d, 373h
0x140036855  jmp     loc_140036AD4
0x14003685a  mov     r11, [rbp+var_20]
0x14003685e  lea     r8, [rbp+var_8]; unsigned __int64 *
0x140036862  mov     rcx, r11; unsigned __int16 *
0x140036865  mov     rdx, r13; unsigned __int64
0x140036868  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14003686d  mov     ebx, eax
0x14003686f  test    eax, eax
0x140036871  jns     short loc_14003687E
0x140036873  mov     r9d, 379h
0x140036879  jmp     loc_140036AD4
0x14003687e  mov     r8, [rbp+var_8]
0x140036882  mov     rdx, r11; String2
0x140036885  mov     rcx, [rbp+String1]; String1
0x140036889  dec     r8; MaxCount
0x14003688c  call    cs:__imp__wcsnicmp
0x140036893  nop     dword ptr [rax+rax+00h]
0x140036898  xor     ecx, ecx
0x14003689a  test    eax, eax
0x14003689c  setz    cl
0x14003689f  mov     [r14+4], ecx
0x1400368a3  test    eax, eax
0x1400368a5  jz      short loc_1400368BB
0x1400368a7  mov     ebx, 80070005h
0x1400368ac  mov     r9d, 37Fh
0x1400368b2  mov     [rsp+50h+var_30], ebx
0x1400368b6  jmp     loc_140036AD8
0x1400368bb  test    r12, r12
0x1400368be  jz      short loc_1400368E3
0x1400368c0  call    cs:__imp_GetProcessHeap
0x1400368c7  nop     dword ptr [rax+rax+00h]
0x1400368cc  mov     r8, r12; lpMem
0x1400368cf  xor     edx, edx; dwFlags
0x1400368d1  mov     rcx, rax; hHeap
0x1400368d4  call    cs:__imp_HeapFree
0x1400368db  nop     dword ptr [rax+rax+00h]
0x1400368e0  xor     r12d, r12d
0x1400368e3  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1400368e6  mov     dword ptr [r14+108h], 7
0x1400368f1  call    ?DwzXmlSetSelectionNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG@Z; DwzXmlSetSelectionNamespace(IXMLDOMDocument2 *,ushort const *)
0x1400368f6  mov     ebx, eax
0x1400368f8  test    eax, eax
0x1400368fa  jns     short loc_140036907
0x1400368fc  mov     r9d, 387h
0x140036902  jmp     loc_140036AD4
0x140036907  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x14003690a  call    ?LoadDisplayNodesFromFile@Configuration@@AEAAJPEAUIXMLDOMDocument2@@@Z; Configuration::LoadDisplayNodesFromFile(IXMLDOMDocument2 *)
0x14003690f  mov     ebx, eax
0x140036911  test    eax, eax
0x140036913  jns     short loc_140036920
0x140036915  mov     r9d, 38Ah
0x14003691b  jmp     loc_140036AD4
0x140036920  mov     rax, [rsi]
0x140036923  lea     r8, [rbp+arg_18]
0x140036927  lea     rdx, aCfgPackageconf_4; "cfg:PackageConfiguration/cfg:Execution/"...
0x14003692e  mov     rcx, rsi
0x140036931  mov     rax, [rax+128h]
0x140036938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003693d  mov     ebx, eax
0x14003693f  test    eax, eax
0x140036941  jns     short loc_14003694E
0x140036943  mov     r9d, 390h
0x140036949  jmp     loc_140036AD4
0x14003694e  jnz     short loc_140036958
0x140036950  mov     dword ptr [r14+20h], 1
0x140036958  mov     rcx, [rbp+arg_18]
0x14003695c  test    rcx, rcx
0x14003695f  jz      short loc_140036971
0x140036961  mov     rax, [rcx]
0x140036964  mov     rax, [rax+10h]
0x140036968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003696d  mov     [rbp+arg_18], rdi
0x140036971  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036975  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036978  lea     rcx, aCfgPackageconf_9; "cfg:PackageConfiguration/cfg:Execution/"...
0x14003697f  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036984  mov     ebx, eax
0x140036986  test    eax, eax
0x140036988  jns     short loc_1400369B5
0x14003698a  mov     r9d, 39Bh
0x140036990  lea     r8, aConfigurationL_4; "Configuration::LoadConfigFile"
0x140036997  mov     [rsp+50h+var_30], eax
0x14003699b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400369a2  mov     ecx, 1; Level
0x1400369a7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400369ac  mov     rdi, [rbp+bstrString]
0x1400369b0  jmp     loc_140036AF0
0x1400369b5  mov     rdi, [rbp+bstrString]
0x1400369b9  jnz     short loc_1400369FC
0x1400369bb  mov     r8, rdi; lpSrc
0x1400369be  mov     rdx, r13; unsigned __int64
0x1400369c1  mov     rcx, r15; unsigned __int16 *
0x1400369c4  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x1400369c9  mov     ebx, eax
0x1400369cb  test    eax, eax
0x1400369cd  jns     short loc_1400369DA
0x1400369cf  mov     r9d, 3A1h
0x1400369d5  jmp     loc_140036AD4
0x1400369da  test    rdi, rdi
0x1400369dd  jz      short loc_1400369F4
0x1400369df  mov     rcx, rdi; bstrString
0x1400369e2  call    cs:__imp_SysFreeString
0x1400369e9  nop     dword ptr [rax+rax+00h]
0x1400369ee  xor     edi, edi
0x1400369f0  mov     [rbp+bstrString], rdi
0x1400369f4  mov     rcx, r15; psz
0x1400369f7  call    ?Packages_SetIcon@@YAXPEBG@Z; Packages_SetIcon(ushort const *)
0x1400369fc  test    rdi, rdi
0x1400369ff  jz      short loc_140036A18
0x140036a01  mov     rcx, rdi; bstrString
0x140036a04  call    cs:__imp_SysFreeString
0x140036a0b  nop     dword ptr [rax+rax+00h]
0x140036a10  mov     [rbp+bstrString], 0
0x140036a18  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140036a1c  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140036a1f  lea     rcx, aCfgPackageconf; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036a26  call    ?TextFromSingleNode@Configuration@@SAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; Configuration::TextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140036a2b  mov     ebx, eax
0x140036a2d  test    eax, eax
0x140036a2f  jns     short loc_140036A3C
0x140036a31  mov     r9d, 3AEh
0x140036a37  jmp     loc_140036990
0x140036a3c  mov     rdi, [rbp+bstrString]
0x140036a40  jnz     short loc_140036AA3
0x140036a42  mov     r8, rdi; lpSrc
0x140036a45  mov     rdx, r13; unsigned __int64
0x140036a48  mov     rcx, r15; unsigned __int16 *
0x140036a4b  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140036a50  mov     ebx, eax
0x140036a52  test    eax, eax
0x140036a54  jns     short loc_140036A5E
0x140036a56  mov     r9d, 3B5h
0x140036a5c  jmp     short loc_140036AD4
0x140036a5e  test    rdi, rdi
0x140036a61  jz      short loc_140036A7A
0x140036a63  mov     rcx, rdi; bstrString
0x140036a66  call    cs:__imp_SysFreeString
0x140036a6d  nop     dword ptr [rax+rax+00h]
0x140036a72  mov     [rbp+bstrString], 0
0x140036a7a  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140036a7e  mov     rcx, r15; psz
0x140036a81  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x140036a86  mov     ebx, eax
0x140036a88  test    eax, eax
0x140036a8a  jns     short loc_140036A97
0x140036a8c  mov     r9d, 3BAh
0x140036a92  jmp     loc_140036990
0x140036a97  mov     rdi, [rbp+bstrString]
0x140036a9b  mov     rcx, rdi; psz
0x140036a9e  call    ?Packages_SetCategory@@YAXPEBG@Z; Packages_SetCategory(ushort const *)
0x140036aa3  test    rdi, rdi
0x140036aa6  jz      short loc_140036AB9
0x140036aa8  mov     rcx, rdi; bstrString
0x140036aab  call    cs:__imp_SysFreeString
0x140036ab2  nop     dword ptr [rax+rax+00h]
0x140036ab7  xor     edi, edi
0x140036ab9  lea     rdx, aCfgPackageconf_8; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140036ac0  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x140036ac3  call    ?LoadKeywordsFromFile@Configuration@@SAJPEAUIXMLDOMDocument2@@PEBG@Z; Configuration::LoadKeywordsFromFile(IXMLDOMDocument2 *,ushort const *)
0x140036ac8  mov     ebx, eax
0x140036aca  test    eax, eax
0x140036acc  jns     short loc_140036AF0
0x140036ace  mov     r9d, 3C2h
0x140036ad4  mov     [rsp+50h+var_30], eax
0x140036ad8  lea     r8, aConfigurationL_4; "Configuration::LoadConfigFile"
0x140036adf  mov     ecx, 1; Level
0x140036ae4  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140036aeb  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140036af0  test    rsi, rsi
0x140036af3  jz      short loc_140036B04
0x140036af5  mov     rax, [rsi]
0x140036af8  mov     rcx, rsi
0x140036afb  mov     rax, [rax+10h]
0x140036aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b04  mov     rsi, [rbp+var_20]
0x140036b08  mov     rcx, [rbp+arg_18]
0x140036b0c  test    rcx, rcx
0x140036b0f  jz      short loc_140036B25
0x140036b11  mov     rax, [rcx]
0x140036b14  mov     rax, [rax+10h]
0x140036b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036b1d  mov     [rbp+arg_18], 0
0x140036b25  test    rdi, rdi
0x140036b28  jz      short loc_140036B39
  ... truncated ...
```
