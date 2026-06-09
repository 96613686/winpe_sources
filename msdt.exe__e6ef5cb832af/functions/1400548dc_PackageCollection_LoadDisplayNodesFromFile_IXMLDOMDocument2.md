# PackageCollection::LoadDisplayNodesFromFile(IXMLDOMDocument2 *)

- ea: `0x1400548dc`
- end: `0x140054dd8`
- name: `?LoadDisplayNodesFromFile@PackageCollection@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `1276`
- prototype: `int(PackageCollection *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005421c`

## callees

- `0x140020420`
- `0x1400548dc`
- `0x140056dcc`
- `0x14005a6e0`
- `0x14005a798`
- `0x14005a850`
- `0x14005a908`
- `0x14005a9a4`
- `0x14005aa5c`
- `0x14005ba68`
- `0x14005befc`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140054956`
- `KERNEL32!HeapAlloc` at `0x140054956`
- `KERNEL32!HeapFree` at `0x140054a0d`
- `KERNEL32!HeapFree` at `0x140054a0d`
- `KERNEL32!GetProcessHeap` at `0x14005493f`
- `KERNEL32!GetProcessHeap` at `0x1400549f9`
- `KERNEL32!GetProcessHeap` at `0x14005493f`
- `KERNEL32!GetProcessHeap` at `0x1400549f9`
- `msvcrt!_wcsnicmp` at `0x140054bca`
- `msvcrt!_wcsnicmp` at `0x140054bea`
- `msvcrt!_wcsnicmp` at `0x140054bca`
- `msvcrt!_wcsnicmp` at `0x140054bea`
- `msvcrt!_wcsicmp` at `0x140054cd8`
- `msvcrt!_wcsicmp` at `0x140054cd8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400549e8`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ad0`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b33`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c35`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c94`
- `OLEAUT32!__imp_SysFreeString` at `0x140054cf7`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140054dc5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400549e8`
- `OLEAUT32!__imp_SysFreeString` at `0x140054a5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140054ad0`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b33`
- `OLEAUT32!__imp_SysFreeString` at `0x140054b8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c35`
- `OLEAUT32!__imp_SysFreeString` at `0x140054c94`
- `OLEAUT32!__imp_SysFreeString` at `0x140054cf7`
- `OLEAUT32!__imp_SysFreeString` at `0x140054d5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140054dc5`

## string_xrefs

- `0x140054982`: `cfg:PackageConfiguration/cfg:Execution/cfg:Name`
- `0x140054aeb`: `cfg:PackageConfiguration/cfg:Execution/cfg:Description`
- `0x140054ba8`: `cfg:PackageConfiguration/cfg:Index/cfg:PrivacyUrl`
- `0x140054c50`: `cfg:PackageConfiguration/cfg:Index/cfg:PublisherName`
- `0x140054caf`: `cfg:PackageConfiguration/cfg:Index/cfg:RequiresAdminPrivileges`
- `0x140054d12`: `cfg:PackageConfiguration/cfg:Index/cfg:Version`
- `0x140054d75`: `cfg:PackageConfiguration/cfg:Index/cfg:Id`

## pseudocode

```c
__int64 __fastcall PackageCollection::LoadDisplayNodesFromFile(PackageCollection *this, struct IXMLDOMDocument2 *a2)
{
  __int64 v2; // rax
  OLECHAR *v4; // rbx
  int v6; // eax
  unsigned int v7; // edi
  unsigned __int16 *v8; // r14
  int v9; // r9d
  HANDLE ProcessHeap; // rax
  int v11; // r9d
  HANDLE v12; // rax
  int v14; // eax
  int v15; // r9d
  int v16; // eax
  OLECHAR *v17; // rbx
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF
  PackageInfo *v19; // [rsp+70h] [rbp+40h] BYREF

  v2 = *(_QWORD *)this;
  v4 = 0;
  bstrString = 0;
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(PackageCollection *, PackageInfo **))(v2 + 80))(this, &v19);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 0;
    v9 = 1724;
LABEL_3:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadDisplayNodesFromFile", v9, v6);
    goto LABEL_11;
  }
  ProcessHeap = GetProcessHeap();
  v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v8 )
  {
    v7 = -2147024882;
    SdpDebugPrint(
      1u,
      "Met ERROR: %s:%d - hr = 0x%08X\n",
      "PackageCollection::LoadDisplayNodesFromFile",
      1726,
      -2147024882);
    goto LABEL_11;
  }
  if ( (unsigned int)MetXmlTextFromSingleNode(L"cfg:PackageConfiguration/cfg:Execution/cfg:Name", a2, &bstrString) )
  {
    v11 = 1735;
LABEL_9:
    SdpDebugPrint(
      1u,
      "Met ERROR: %s:%d - hr = 0x%08X\n",
      "PackageCollection::LoadDisplayNodesFromFile",
      v11,
      -2147024809);
    v7 = -2147024809;
LABEL_10:
    v4 = bstrString;
    goto LABEL_11;
  }
  v4 = bstrString;
  v6 = MetExpandVariables(v8, 0x104u, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1741;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  v14 = MetTryLoadResourceString(v8, &bstrString);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 1746;
LABEL_24:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadDisplayNodesFromFile", v15, v14);
    goto LABEL_10;
  }
  v4 = bstrString;
  v6 = PackageInfo::set_Name(v19, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1749;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  if ( (unsigned int)MetXmlTextFromSingleNode(
                       L"cfg:PackageConfiguration/cfg:Execution/cfg:Description",
                       a2,
                       &bstrString) )
  {
    v11 = 1760;
    goto LABEL_9;
  }
  v4 = bstrString;
  v6 = MetExpandVariables(v8, 0x104u, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1766;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  v14 = MetTryLoadResourceString(v8, &bstrString);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 1771;
    goto LABEL_24;
  }
  v4 = bstrString;
  v6 = PackageInfo::set_Description(v19, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1774;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  v16 = MetXmlTextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:PrivacyUrl", a2, &bstrString);
  v4 = bstrString;
  if ( v16 || _wcsnicmp(bstrString, L"http://", 7u) && _wcsnicmp(v4, L"https://", 8u) )
  {
    v7 = -2147024809;
    SdpDebugPrint(
      1u,
      "Met ERROR: %s:%d - hr = 0x%08X\n",
      "PackageCollection::LoadDisplayNodesFromFile",
      1788,
      -2147024809);
    goto LABEL_11;
  }
  v6 = PackageInfo::set_PrivacyLink(v19, v4);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1791;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  if ( (unsigned int)MetXmlTextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:PublisherName", a2, &bstrString) )
  {
    v11 = 1802;
    goto LABEL_9;
  }
  v4 = bstrString;
  v6 = PackageInfo::set_Publisher(v19, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1805;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    bstrString = 0;
  }
  if ( (unsigned int)MetXmlTextFromSingleNode(
                       L"cfg:PackageConfiguration/cfg:Index/cfg:RequiresAdminPrivileges",
                       a2,
                       &bstrString) )
  {
    v11 = 1816;
    goto LABEL_9;
  }
  v17 = bstrString;
  *((_DWORD *)this + 18) = _wcsicmp(bstrString, L"true") == 0;
  if ( v17 )
  {
    SysFreeString(v17);
    bstrString = 0;
  }
  v14 = MetXmlTextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:Version", a2, &bstrString);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 1826;
    goto LABEL_24;
  }
  if ( !v14 )
  {
    v4 = bstrString;
    v6 = PackageInfo::set_Version(v19, bstrString);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = 1829;
      goto LABEL_3;
    }
    if ( v4 )
    {
      SysFreeString(v4);
      bstrString = 0;
    }
  }
  v14 = MetXmlTextFromSingleNode(L"cfg:PackageConfiguration/cfg:Index/cfg:Id", a2, &bstrString);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 1838;
    goto LABEL_24;
  }
  if ( v14 )
    goto LABEL_10;
  v4 = bstrString;
  v6 = PackageInfo::set_ID(v19, bstrString);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = 1841;
    goto LABEL_3;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    v4 = 0;
  }
LABEL_11:
  if ( v19 )
  {
    (*(void (__fastcall **)(PackageInfo *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v8 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v8);
  }
  return v7;
}

```

## disassembly

```asm
0x1400548dc  mov     [rsp-28h+arg_8], rbx
0x1400548e1  push    rbp
0x1400548e2  push    rsi
0x1400548e3  push    rdi
0x1400548e4  push    r14
0x1400548e6  push    r15
0x1400548e8  mov     rbp, rsp
0x1400548eb  sub     rsp, 30h
0x1400548ef  mov     rax, [rcx]
0x1400548f2  mov     rsi, rdx
0x1400548f5  xor     ebx, ebx
0x1400548f7  lea     rdx, [rbp+arg_10]
0x1400548fb  mov     r15, rcx
0x1400548fe  mov     [rbp+bstrString], rbx
0x140054902  mov     [rbp+arg_10], rbx
0x140054906  mov     rax, [rax+50h]
0x14005490a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005490f  mov     edi, eax
0x140054911  test    eax, eax
0x140054913  jns     short loc_14005493F
0x140054915  xor     r14d, r14d
0x140054918  mov     r9d, 6BCh
0x14005491e  mov     [rsp+30h+var_10], eax
0x140054922  lea     r8, aPackagecollect_14; "PackageCollection::LoadDisplayNodesFrom"...
0x140054929  mov     ecx, 1; Level
0x14005492e  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140054935  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005493a  jmp     loc_1400549C3
0x14005493f  call    cs:__imp_GetProcessHeap
0x140054946  nop     dword ptr [rax+rax+00h]
0x14005494b  xor     edx, edx; dwFlags
0x14005494d  mov     r8d, 208h; dwBytes
0x140054953  mov     rcx, rax; hHeap
0x140054956  call    cs:__imp_HeapAlloc
0x14005495d  nop     dword ptr [rax+rax+00h]
0x140054962  mov     r14, rax
0x140054965  test    rax, rax
0x140054968  jnz     short loc_14005497B
0x14005496a  mov     edi, 8007000Eh
0x14005496f  mov     r9d, 6BEh
0x140054975  mov     [rsp+30h+var_10], edi
0x140054979  jmp     short loc_140054922
0x14005497b  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14005497f  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054982  lea     rcx, aCfgPackageconf_10; "cfg:PackageConfiguration/cfg:Execution/"...
0x140054989  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x14005498e  test    eax, eax
0x140054990  jz      loc_140054A2D
0x140054996  mov     r9d, 6C7h
0x14005499c  mov     esi, 80070057h
0x1400549a1  lea     r8, aPackagecollect_14; "PackageCollection::LoadDisplayNodesFrom"...
0x1400549a8  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400549af  mov     [rsp+30h+var_10], esi
0x1400549b3  mov     ecx, 1; Level
0x1400549b8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400549bd  mov     edi, esi
0x1400549bf  mov     rbx, [rbp+bstrString]
0x1400549c3  mov     rcx, [rbp+arg_10]
0x1400549c7  test    rcx, rcx
0x1400549ca  jz      short loc_1400549E0
0x1400549cc  mov     rax, [rcx]
0x1400549cf  mov     rax, [rax+10h]
0x1400549d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400549d8  mov     [rbp+arg_10], 0
0x1400549e0  test    rbx, rbx
0x1400549e3  jz      short loc_1400549F4
0x1400549e5  mov     rcx, rbx; bstrString
0x1400549e8  call    cs:__imp_SysFreeString
0x1400549ef  nop     dword ptr [rax+rax+00h]
0x1400549f4  test    r14, r14
0x1400549f7  jz      short loc_140054A19
0x1400549f9  call    cs:__imp_GetProcessHeap
0x140054a00  nop     dword ptr [rax+rax+00h]
0x140054a05  mov     r8, r14; lpMem
0x140054a08  xor     edx, edx; dwFlags
0x140054a0a  mov     rcx, rax; hHeap
0x140054a0d  call    cs:__imp_HeapFree
0x140054a14  nop     dword ptr [rax+rax+00h]
0x140054a19  mov     rbx, [rsp+30h+arg_8]
0x140054a1e  mov     eax, edi
0x140054a20  add     rsp, 30h
0x140054a24  pop     r15
0x140054a26  pop     r14
0x140054a28  pop     rdi
0x140054a29  pop     rsi
0x140054a2a  pop     rbp
0x140054a2b  retn
0x140054a2d  mov     rbx, [rbp+bstrString]
0x140054a31  mov     edx, 104h; unsigned __int64
0x140054a36  mov     r8, rbx; lpSrc
0x140054a39  mov     rcx, r14; unsigned __int16 *
0x140054a3c  call    ?MetExpandVariables@@YAJPEAG_KPEBG@Z; MetExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140054a41  mov     edi, eax
0x140054a43  test    eax, eax
0x140054a45  jns     short loc_140054A52
0x140054a47  mov     r9d, 6CDh
0x140054a4d  jmp     loc_14005491E
0x140054a52  test    rbx, rbx
0x140054a55  jz      short loc_140054A6E
0x140054a57  mov     rcx, rbx; bstrString
0x140054a5a  call    cs:__imp_SysFreeString
0x140054a61  nop     dword ptr [rax+rax+00h]
0x140054a66  mov     [rbp+bstrString], 0
0x140054a6e  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140054a72  mov     rcx, r14; psz
0x140054a75  call    ?MetTryLoadResourceString@@YAJPEBGPEAPEAG@Z; MetTryLoadResourceString(ushort const *,ushort * *)
0x140054a7a  mov     edi, eax
0x140054a7c  test    eax, eax
0x140054a7e  jns     short loc_140054AA7
0x140054a80  mov     r9d, 6D2h
0x140054a86  lea     r8, aPackagecollect_14; "PackageCollection::LoadDisplayNodesFrom"...
0x140054a8d  mov     [rsp+30h+var_10], eax
0x140054a91  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140054a98  mov     ecx, 1; Level
0x140054a9d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140054aa2  jmp     loc_1400549BF
0x140054aa7  mov     rbx, [rbp+bstrString]
0x140054aab  mov     rcx, [rbp+arg_10]; this
0x140054aaf  mov     rdx, rbx; unsigned __int16 *
0x140054ab2  call    ?set_Name@PackageInfo@@QEAAJPEBG@Z; PackageInfo::set_Name(ushort const *)
0x140054ab7  mov     edi, eax
0x140054ab9  test    eax, eax
0x140054abb  jns     short loc_140054AC8
0x140054abd  mov     r9d, 6D5h
0x140054ac3  jmp     loc_14005491E
0x140054ac8  test    rbx, rbx
0x140054acb  jz      short loc_140054AE4
0x140054acd  mov     rcx, rbx; bstrString
0x140054ad0  call    cs:__imp_SysFreeString
0x140054ad7  nop     dword ptr [rax+rax+00h]
0x140054adc  mov     [rbp+bstrString], 0
0x140054ae4  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054ae8  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054aeb  lea     rcx, aCfgPackageconf_0; "cfg:PackageConfiguration/cfg:Execution/"...
0x140054af2  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054af7  test    eax, eax
0x140054af9  jz      short loc_140054B06
0x140054afb  mov     r9d, 6E0h
0x140054b01  jmp     loc_14005499C
0x140054b06  mov     rbx, [rbp+bstrString]
0x140054b0a  mov     edx, 104h; unsigned __int64
0x140054b0f  mov     r8, rbx; lpSrc
0x140054b12  mov     rcx, r14; unsigned __int16 *
0x140054b15  call    ?MetExpandVariables@@YAJPEAG_KPEBG@Z; MetExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140054b1a  mov     edi, eax
0x140054b1c  test    eax, eax
0x140054b1e  jns     short loc_140054B2B
0x140054b20  mov     r9d, 6E6h
0x140054b26  jmp     loc_14005491E
0x140054b2b  test    rbx, rbx
0x140054b2e  jz      short loc_140054B47
0x140054b30  mov     rcx, rbx; bstrString
0x140054b33  call    cs:__imp_SysFreeString
0x140054b3a  nop     dword ptr [rax+rax+00h]
0x140054b3f  mov     [rbp+bstrString], 0
0x140054b47  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140054b4b  mov     rcx, r14; psz
0x140054b4e  call    ?MetTryLoadResourceString@@YAJPEBGPEAPEAG@Z; MetTryLoadResourceString(ushort const *,ushort * *)
0x140054b53  mov     edi, eax
0x140054b55  test    eax, eax
0x140054b57  jns     short loc_140054B64
0x140054b59  mov     r9d, 6EBh
0x140054b5f  jmp     loc_140054A86
0x140054b64  mov     rbx, [rbp+bstrString]
0x140054b68  mov     rcx, [rbp+arg_10]; this
0x140054b6c  mov     rdx, rbx; unsigned __int16 *
0x140054b6f  call    ?set_Description@PackageInfo@@QEAAJPEBG@Z; PackageInfo::set_Description(ushort const *)
0x140054b74  mov     edi, eax
0x140054b76  test    eax, eax
0x140054b78  jns     short loc_140054B85
0x140054b7a  mov     r9d, 6EEh
0x140054b80  jmp     loc_14005491E
0x140054b85  test    rbx, rbx
0x140054b88  jz      short loc_140054BA1
0x140054b8a  mov     rcx, rbx; bstrString
0x140054b8d  call    cs:__imp_SysFreeString
0x140054b94  nop     dword ptr [rax+rax+00h]
0x140054b99  mov     [rbp+bstrString], 0
0x140054ba1  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054ba5  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054ba8  lea     rcx, aCfgPackageconf_5; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140054baf  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054bb4  mov     rbx, [rbp+bstrString]
0x140054bb8  test    eax, eax
0x140054bba  jnz     short loc_140054BFA
0x140054bbc  lea     r8d, [rax+7]; MaxCount
0x140054bc0  mov     rcx, rbx; String1
0x140054bc3  lea     rdx, aHttp; "http://"
0x140054bca  call    cs:__imp__wcsnicmp
0x140054bd1  nop     dword ptr [rax+rax+00h]
0x140054bd6  test    eax, eax
0x140054bd8  jz      short loc_140054C10
0x140054bda  mov     r8d, 8; MaxCount
0x140054be0  lea     rdx, aHttps; "https://"
0x140054be7  mov     rcx, rbx; String1
0x140054bea  call    cs:__imp__wcsnicmp
0x140054bf1  nop     dword ptr [rax+rax+00h]
0x140054bf6  test    eax, eax
0x140054bf8  jz      short loc_140054C10
0x140054bfa  mov     esi, 80070057h
0x140054bff  mov     r9d, 6FCh
0x140054c05  mov     edi, esi
0x140054c07  mov     [rsp+30h+var_10], esi
0x140054c0b  jmp     loc_140054922
0x140054c10  mov     rcx, [rbp+arg_10]; this
0x140054c14  mov     rdx, rbx; unsigned __int16 *
0x140054c17  call    ?set_PrivacyLink@PackageInfo@@QEAAJPEBG@Z; PackageInfo::set_PrivacyLink(ushort const *)
0x140054c1c  mov     edi, eax
0x140054c1e  test    eax, eax
0x140054c20  jns     short loc_140054C2D
0x140054c22  mov     r9d, 6FFh
0x140054c28  jmp     loc_14005491E
0x140054c2d  test    rbx, rbx
0x140054c30  jz      short loc_140054C49
0x140054c32  mov     rcx, rbx; bstrString
0x140054c35  call    cs:__imp_SysFreeString
0x140054c3c  nop     dword ptr [rax+rax+00h]
0x140054c41  mov     [rbp+bstrString], 0
0x140054c49  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054c4d  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054c50  lea     rcx, aCfgPackageconf_7; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140054c57  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054c5c  test    eax, eax
0x140054c5e  jz      short loc_140054C6B
0x140054c60  mov     r9d, 70Ah
0x140054c66  jmp     loc_14005499C
0x140054c6b  mov     rbx, [rbp+bstrString]
0x140054c6f  mov     rcx, [rbp+arg_10]; this
0x140054c73  mov     rdx, rbx; unsigned __int16 *
0x140054c76  call    ?set_Publisher@PackageInfo@@QEAAJPEBG@Z; PackageInfo::set_Publisher(ushort const *)
0x140054c7b  mov     edi, eax
0x140054c7d  test    eax, eax
0x140054c7f  jns     short loc_140054C8C
0x140054c81  mov     r9d, 70Dh
0x140054c87  jmp     loc_14005491E
0x140054c8c  test    rbx, rbx
0x140054c8f  jz      short loc_140054CA8
0x140054c91  mov     rcx, rbx; bstrString
0x140054c94  call    cs:__imp_SysFreeString
0x140054c9b  nop     dword ptr [rax+rax+00h]
0x140054ca0  mov     [rbp+bstrString], 0
0x140054ca8  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054cac  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054caf  lea     rcx, aCfgPackageconf_6; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140054cb6  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054cbb  test    eax, eax
0x140054cbd  jz      short loc_140054CCA
0x140054cbf  mov     r9d, 718h
0x140054cc5  jmp     loc_14005499C
0x140054cca  mov     rbx, [rbp+bstrString]
0x140054cce  lea     rdx, aTrue; "true"
0x140054cd5  mov     rcx, rbx; String1
0x140054cd8  call    cs:__imp__wcsicmp
0x140054cdf  nop     dword ptr [rax+rax+00h]
0x140054ce4  xor     edx, edx
0x140054ce6  test    eax, eax
0x140054ce8  setz    dl
0x140054ceb  mov     [r15+48h], edx
0x140054cef  test    rbx, rbx
0x140054cf2  jz      short loc_140054D0B
0x140054cf4  mov     rcx, rbx; bstrString
0x140054cf7  call    cs:__imp_SysFreeString
0x140054cfe  nop     dword ptr [rax+rax+00h]
0x140054d03  mov     [rbp+bstrString], 0
0x140054d0b  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054d0f  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054d12  lea     rcx, aCfgPackageconf_3; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140054d19  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054d1e  mov     edi, eax
0x140054d20  test    eax, eax
0x140054d22  jns     short loc_140054D2F
0x140054d24  mov     r9d, 722h
0x140054d2a  jmp     loc_140054A86
0x140054d2f  jnz     short loc_140054D6E
0x140054d31  mov     rbx, [rbp+bstrString]
0x140054d35  mov     rcx, [rbp+arg_10]; this
0x140054d39  mov     rdx, rbx; unsigned __int16 *
0x140054d3c  call    ?set_Version@PackageInfo@@QEAAJPEBG@Z; PackageInfo::set_Version(ushort const *)
0x140054d41  mov     edi, eax
0x140054d43  test    eax, eax
0x140054d45  jns     short loc_140054D52
0x140054d47  mov     r9d, 725h
0x140054d4d  jmp     loc_14005491E
0x140054d52  test    rbx, rbx
0x140054d55  jz      short loc_140054D6E
0x140054d57  mov     rcx, rbx; bstrString
0x140054d5a  call    cs:__imp_SysFreeString
0x140054d61  nop     dword ptr [rax+rax+00h]
0x140054d66  mov     [rbp+bstrString], 0
0x140054d6e  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x140054d72  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x140054d75  lea     rcx, aCfgPackageconf_2; "cfg:PackageConfiguration/cfg:Index/cfg:"...
0x140054d7c  call    ?MetXmlTextFromSingleNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAPEAG@Z; MetXmlTextFromSingleNode(ushort const *,IXMLDOMDocument2 *,ushort * *)
0x140054d81  mov     edi, eax
0x140054d83  test    eax, eax
0x140054d85  jns     short loc_140054D92
0x140054d87  mov     r9d, 72Eh
0x140054d8d  jmp     loc_140054A86
0x140054d92  jnz     loc_1400549BF
0x140054d98  mov     rbx, [rbp+bstrString]
  ... truncated ...
```
