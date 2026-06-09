# CNodeMonitorNode::SetValueWrap(tagVARIANT)

- ea: `0x1800594a0`
- end: `0x1800599ff`
- name: `?SetValueWrap@CNodeMonitorNode@@IEAAJUtagVARIANT@@@Z`
- size: `1375`
- prototype: `__int64 __fastcall(CNodeMonitorNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800593d0`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a9c`
- `0x18002dc94`
- `0x180055bc0`
- `0x18005745c`
- `0x180057650`
- `0x1800594a0`
- `0x18005ade0`
- `0x180060d64`
- `0x180060f20`
- `0x1800610e4`
- `0x1800611c8`
- `0x18006125c`
- `0x180061474`
- `0x18006167c`
- `0x180061728`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800596e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800596e6`
- `OLEAUT32!__imp_VariantInit` at `0x1800596ca`
- `OLEAUT32!__imp_VariantInit` at `0x1800596ca`
- `OLEAUT32!__imp_VariantClear` at `0x180059724`
- `OLEAUT32!__imp_VariantClear` at `0x18005974d`
- `OLEAUT32!__imp_VariantClear` at `0x180059724`
- `OLEAUT32!__imp_VariantClear` at `0x18005974d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800599e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800598f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800599e4`

## string_xrefs

- `0x18005951d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180059564`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x1800595a2`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x1800595e0`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180059642`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x18005970f`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x1800599a2`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x18005982a`: `NodeUri`
- `0x18005995e`: `CacheVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNodeMonitorNode::SetValueWrap(const unsigned __int16 **this, struct tagVARIANT *a2)
{
  CNodeCacheManager *v4; // rsi
  const unsigned __int16 *v5; // rdx
  int NodesRegValueBstr; // eax
  int ProviderIdKey; // ebx
  CNodeMonitorCsp *v8; // rbx
  int ConfigManager; // eax
  struct IConfigNode *v10; // rdx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rbx
  int v13; // eax
  int v14; // r14d
  bool v15; // r14
  int v16; // eax
  int v17; // esi
  int v18; // eax
  CNodeCacheManager *v19; // rdi
  __int64 v20; // rdx
  int ExpectedValueSemanticType; // eax
  int v22; // r8d
  unsigned __int16 *v23; // rsi
  CNodeCacheManager *v24; // rcx
  HKEY v25; // rdi
  unsigned __int16 *bstrVal; // rsi
  CNodeCacheManager *v27; // rcx
  HKEY v28; // rdi
  int v29; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v34; // [rsp+90h] [rbp+40h] BYREF
  struct IConfigManager2 *v35; // [rsp+98h] [rbp+48h] BYREF

  LODWORD(hKey) = 0;
  switch ( *((_DWORD *)this[7] + 1) )
  {
    case 1:
      if ( !a2->vt )
      {
        hKey = 0;
        ProviderIdKey = CNodeCacheManager::GetProviderIdKey((CNodeCacheManager *)this, this[1], this[2], &hKey, 1);
        if ( hKey )
          RegCloseKey(hKey);
        if ( ProviderIdKey >= 0 )
          return 0;
        v20 = 1050;
        goto LABEL_82;
      }
      v20 = 1049;
      goto LABEL_81;
    case 2:
      if ( a2->vt == 8 )
      {
        bstrVal = a2->bstrVal;
        hKey = 0;
        if ( bstrVal )
        {
          ProviderIdKey = CNodeCacheManager::GetProviderIdKey((CNodeCacheManager *)this, this[1], this[2], &hKey, 0);
          v28 = hKey;
          if ( ProviderIdKey >= 0 )
            ProviderIdKey = CNodeCacheManager::SetRegValueBstr(v27, hKey, L"CacheVersion", bstrVal);
          if ( v28 )
            RegCloseKey(v28);
          if ( ProviderIdKey >= 0 )
            return 0;
        }
        else
        {
          ProviderIdKey = -2147024809;
        }
        v20 = 1074;
        goto LABEL_82;
      }
      v20 = 1073;
      goto LABEL_81;
    case 3:
      return 2248146961LL;
    case 4:
      if ( !a2->vt )
      {
        hKey = 0;
        ProviderIdKey = CNodeCacheManager::GetNodesKey((CNodeCacheManager *)this, this[1], this[2], &hKey, 1);
        if ( hKey )
          RegCloseKey(hKey);
        if ( ProviderIdKey >= 0 )
          return 0;
        v20 = 1058;
        goto LABEL_82;
      }
      v20 = 1057;
      goto LABEL_81;
    case 5:
      if ( !a2->vt )
      {
        hKey = 0;
        ProviderIdKey = CNodeCacheManager::GetNodeIdKey((CNodeCacheManager *)this, this[1], this[2], this[3], &hKey, 1);
        if ( hKey )
          RegCloseKey(hKey);
        if ( ProviderIdKey >= 0 )
          return 0;
        v20 = 1066;
        goto LABEL_82;
      }
      v20 = 1065;
      goto LABEL_81;
    case 6:
      if ( a2->vt == 8 )
      {
        hKey = 0;
        v23 = a2->bstrVal;
        if ( v23 )
        {
          ProviderIdKey = CNodeCacheManager::GetNodeIdKey(
                            (CNodeCacheManager *)this,
                            this[1],
                            this[2],
                            this[3],
                            &hKey,
                            0);
          v25 = hKey;
          if ( ProviderIdKey >= 0 )
            ProviderIdKey = CNodeCacheManager::SetRegValueBstr(v24, hKey, L"NodeUri", v23);
          if ( v25 )
            RegCloseKey(v25);
          if ( ProviderIdKey >= 0 )
            return 0;
        }
        else
        {
          ProviderIdKey = -2147024809;
        }
        v20 = 1090;
        goto LABEL_82;
      }
      v20 = 1089;
LABEL_81:
      ProviderIdKey = -2046820351;
      goto LABEL_82;
    case 7:
      v19 = (CNodeCacheManager *)(this + 1);
      ProviderIdKey = CNodeCacheManager::SetExpectedValue((CNodeCacheManager *)(this + 1), a2);
      if ( ProviderIdKey >= 0 )
      {
        ExpectedValueSemanticType = CNodeCacheManager::GetExpectedValueSemanticType(v19, (unsigned int *)&hKey);
        v22 = (int)hKey;
        if ( ExpectedValueSemanticType < 0 )
          v22 = 0;
        if ( v22 != 2 )
          return 0;
        ProviderIdKey = CNodeCacheManager::SetExpectedValueSemanticType(v19, 0);
        if ( ProviderIdKey >= 0 )
          return 0;
        v20 = 1108;
      }
      else
      {
        v20 = 1097;
      }
LABEL_82:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)ProviderIdKey,
        v29);
      return (unsigned int)ProviderIdKey;
  }
  if ( *((_DWORD *)this[7] + 1) != 8 )
  {
    if ( *((_DWORD *)this[7] + 1) != 9 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)0x86000011LL,
        v29);
    return 2248146961LL;
  }
  v30 = 0;
  v4 = (CNodeCacheManager *)(this + 1);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v30,
    0);
  NodesRegValueBstr = CNodeCacheManager::GetNodesRegValueBstr(v4, v5, &v30);
  ProviderIdKey = NodesRegValueBstr;
  if ( NodesRegValueBstr >= 0 )
  {
    v35 = 0;
    v8 = (CNodeMonitorCsp *)this[10];
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
    ConfigManager = CNodeMonitorCsp::GetConfigManager(v8, &v35);
    ProviderIdKey = ConfigManager;
    if ( ConfigManager < 0 )
    {
      v11 = 1120;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)ConfigManager,
        v29);
LABEL_35:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
      goto LABEL_36;
    }
    LODWORD(hKey) = 0;
    v12 = v30;
    v13 = IsCspNodeForUriExists(v35, v10, v30, (int *)&hKey);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x463,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
        (const char *)(unsigned int)v13,
        v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
      ProviderIdKey = v14;
      goto LABEL_36;
    }
    if ( (_DWORD)hKey )
    {
      v15 = 0;
      v34 = 0;
      v16 = CNodeCacheManager::GetExpectedValueSemanticType(v4, &v34);
      if ( v16 >= 0 )
        v15 = v34 == 1;
      v17 = 0;
      if ( v16 != -2147024894 )
        v17 = v16;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
          (const char *)(unsigned int)v17,
          v29);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
        ProviderIdKey = v17;
        goto LABEL_36;
      }
      if ( v15 )
      {
        ConfigManager = CNodeMonitorNode::AutoSetNodeHashValue((CNodeMonitorNode *)this, v12, v35);
        ProviderIdKey = ConfigManager;
        if ( ConfigManager < 0 )
        {
          v11 = 1141;
          goto LABEL_16;
        }
      }
      else
      {
        ConfigManager = CNodeMonitorNode::AutoSetNodeValue((CNodeMonitorNode *)this, v35, v12);
        ProviderIdKey = ConfigManager;
        if ( ConfigManager < 0 )
        {
          v11 = 1145;
          goto LABEL_16;
        }
      }
    }
    else
    {
      ConfigManager = CNodeCacheManager::SetExpectedValueSemanticType(v4, 2u);
      ProviderIdKey = ConfigManager;
      if ( ConfigManager < 0 )
      {
        v11 = 1151;
        goto LABEL_16;
      }
      VariantInit(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(&Class);
      v18 = CNodeCacheManager::SetExpectedValue(v4, &pvarg);
      ProviderIdKey = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x484,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
          (const char *)(unsigned int)v18,
          v29);
        VariantClear(&pvarg);
        goto LABEL_35;
      }
      VariantClear(&pvarg);
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
    (const char *)(unsigned int)NodesRegValueBstr,
    v29);
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  return (unsigned int)ProviderIdKey;
}

```

## disassembly

```asm
0x1800594a0  mov     [rsp-28h+arg_8], rbx
0x1800594a5  push    rbp
0x1800594a6  push    rsi
0x1800594a7  push    rdi
0x1800594a8  push    r14
0x1800594aa  push    r15
0x1800594ac  mov     rbp, rsp
0x1800594af  sub     rsp, 50h
0x1800594b3  mov     rdi, rcx
0x1800594b6  xor     r15d, r15d
0x1800594b9  mov     dword ptr [rbp+hKey], r15d
0x1800594bd  mov     r8, [rcx+38h]
0x1800594c1  mov     r9d, [r8+4]
0x1800594c5  sub     r9d, 1
0x1800594c9  jz      loc_180059992
0x1800594cf  sub     r9d, 1
0x1800594d3  jz      loc_180059916
0x1800594d9  sub     r9d, 1
0x1800594dd  jz      short loc_18005952E
0x1800594df  sub     r9d, 1
0x1800594e3  jz      loc_1800598C0
0x1800594e9  sub     r9d, 1
0x1800594ed  jz      loc_180059861
0x1800594f3  sub     r9d, 1
0x1800594f7  jz      loc_1800597D6
0x1800594fd  sub     r9d, 1
0x180059501  jz      loc_180059784
0x180059507  sub     r9d, 1
0x18005950b  jz      short loc_180059538
0x18005950d  cmp     r9d, 1
0x180059511  jz      short loc_18005952E
0x180059513  mov     rcx, [rbp+28h]; this
0x180059517  mov     r9d, 86000011h; char *
0x18005951d  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180059524  mov     edx, 48Bh; void *
0x180059529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005952e  mov     eax, 86000011h
0x180059533  jmp     loc_18005976F
0x180059538  mov     [rbp+var_20], r15
0x18005953c  lea     rsi, [rcx+8]
0x180059540  xor     edx, edx
0x180059542  lea     rcx, [rbp+var_20]
0x180059546  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005954b  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18005954f  mov     rcx, rsi; this
0x180059552  call    ?GetNodesRegValueBstr@CNodeCacheManager@@AEAAJPEBGPEAPEAG@Z; CNodeCacheManager::GetNodesRegValueBstr(ushort const *,ushort * *)
0x180059557  mov     ebx, eax
0x180059559  test    eax, eax
0x18005955b  jns     short loc_18005957A
0x18005955d  mov     rcx, [rbp+28h]; this
0x180059561  mov     r9d, eax; char *
0x180059564  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005956b  mov     edx, 45Dh; void *
0x180059570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059575  jmp     loc_18005973B
0x18005957a  mov     [rbp+arg_18], r15
0x18005957e  mov     rbx, [rdi+50h]
0x180059582  lea     rcx, [rbp+arg_18]
0x180059586  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005958b  lea     rdx, [rbp+arg_18]; struct IConfigManager2 **
0x18005958f  mov     rcx, rbx; this
0x180059592  call    ?GetConfigManager@CNodeMonitorCsp@@QEAAJPEAPEAUIConfigManager2@@@Z; CNodeMonitorCsp::GetConfigManager(IConfigManager2 * *)
0x180059597  mov     ebx, eax
0x180059599  test    eax, eax
0x18005959b  jns     short loc_1800595BA
0x18005959d  mov     edx, 460h; void *
0x1800595a2  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800595a9  mov     r9d, eax; char *
0x1800595ac  mov     rcx, [rbp+28h]; this
0x1800595b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800595b5  jmp     loc_180059731
0x1800595ba  mov     dword ptr [rbp+hKey], r15d
0x1800595be  lea     r9, [rbp+hKey]; int *
0x1800595c2  mov     rbx, [rbp+var_20]
0x1800595c6  mov     r8, rbx; unsigned __int16 *
0x1800595c9  mov     rcx, [rbp+arg_18]; struct IConfigManager2 *
0x1800595cd  call    ?IsCspNodeForUriExists@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAH@Z; IsCspNodeForUriExists(IConfigManager2 *,IConfigNode *,ushort const *,int *)
0x1800595d2  mov     r14d, eax
0x1800595d5  test    eax, eax
0x1800595d7  jns     short loc_180059603
0x1800595d9  mov     rcx, [rbp+28h]; this
0x1800595dd  mov     r9d, eax; char *
0x1800595e0  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800595e7  mov     edx, 463h; void *
0x1800595ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800595f1  nop
0x1800595f2  lea     rcx, [rbp+arg_18]
0x1800595f6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800595fb  mov     ebx, r14d
0x1800595fe  jmp     loc_18005973B
0x180059603  mov     rcx, rsi; this
0x180059606  cmp     dword ptr [rbp+hKey], r15d
0x18005960a  jz      loc_1800596AC
0x180059610  mov     r14b, r15b
0x180059613  mov     [rbp+arg_10], r15d
0x180059617  lea     rdx, [rbp+arg_10]; unsigned int *
0x18005961b  call    ?GetExpectedValueSemanticType@CNodeCacheManager@@QEAAJPEAK@Z; CNodeCacheManager::GetExpectedValueSemanticType(ulong *)
0x180059620  test    eax, eax
0x180059622  js      short loc_18005962C
0x180059624  cmp     [rbp+arg_10], 1
0x180059628  setz    r14b
0x18005962c  mov     esi, r15d
0x18005962f  cmp     eax, 80070002h
0x180059634  cmovnz  esi, eax
0x180059637  test    esi, esi
0x180059639  jns     short loc_180059664
0x18005963b  mov     rcx, [rbp+28h]; this
0x18005963f  mov     r9d, esi; char *
0x180059642  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180059649  mov     edx, 471h; void *
0x18005964e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059653  nop
0x180059654  lea     rcx, [rbp+arg_18]
0x180059658  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005965d  mov     ebx, esi
0x18005965f  jmp     loc_18005973B
0x180059664  mov     rcx, rdi; this
0x180059667  test    r14b, r14b
0x18005966a  jz      short loc_18005968C
0x18005966c  mov     r8, [rbp+arg_18]; struct IConfigManager2 *
0x180059670  mov     rdx, rbx; unsigned __int16 *
0x180059673  call    ?AutoSetNodeHashValue@CNodeMonitorNode@@IEAAJPEAGPEAUIConfigManager2@@@Z; CNodeMonitorNode::AutoSetNodeHashValue(ushort *,IConfigManager2 *)
0x180059678  mov     ebx, eax
0x18005967a  test    eax, eax
0x18005967c  jns     loc_18005975A
0x180059682  mov     edx, 475h
0x180059687  jmp     loc_1800595A2
0x18005968c  mov     r8, rbx; unsigned __int16 *
0x18005968f  mov     rdx, [rbp+arg_18]; struct IConfigManager2 *
0x180059693  call    ?AutoSetNodeValue@CNodeMonitorNode@@IEAAJPEAUIConfigManager2@@PEAG@Z; CNodeMonitorNode::AutoSetNodeValue(IConfigManager2 *,ushort *)
0x180059698  mov     ebx, eax
0x18005969a  test    eax, eax
0x18005969c  jns     loc_18005975A
0x1800596a2  mov     edx, 479h
0x1800596a7  jmp     loc_1800595A2
0x1800596ac  mov     edx, 2; unsigned int
0x1800596b1  call    ?SetExpectedValueSemanticType@CNodeCacheManager@@QEAAJK@Z; CNodeCacheManager::SetExpectedValueSemanticType(ulong)
0x1800596b6  mov     ebx, eax
0x1800596b8  test    eax, eax
0x1800596ba  jns     short loc_1800596C6
0x1800596bc  mov     edx, 47Fh
0x1800596c1  jmp     loc_1800595A2
0x1800596c6  lea     rcx, [rbp+pvarg]; pvarg
0x1800596ca  call    cs:__imp_VariantInit
0x1800596d1  nop     dword ptr [rax+rax+00h]
0x1800596d6  mov     eax, 8
0x1800596db  mov     word ptr [rbp+pvarg], ax
0x1800596df  lea     rcx, Class; psz
0x1800596e6  call    cs:__imp_SysAllocString
0x1800596ed  nop     dword ptr [rax+rax+00h]
0x1800596f2  mov     qword ptr [rbp+pvarg+8], rax
0x1800596f6  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x1800596fa  mov     rcx, rsi; this
0x1800596fd  call    ?SetExpectedValue@CNodeCacheManager@@QEAAJPEAUtagVARIANT@@@Z; CNodeCacheManager::SetExpectedValue(tagVARIANT *)
0x180059702  mov     ebx, eax
0x180059704  test    eax, eax
0x180059706  jns     short loc_180059749
0x180059708  mov     rcx, [rbp+28h]; this
0x18005970c  mov     r9d, eax; char *
0x18005970f  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180059716  mov     edx, 484h; void *
0x18005971b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059720  lea     rcx, [rbp+pvarg]; pvarg
0x180059724  call    cs:__imp_VariantClear
0x18005972b  nop     dword ptr [rax+rax+00h]
0x180059730  nop
0x180059731  lea     rcx, [rbp+arg_18]
0x180059735  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005973a  nop
0x18005973b  lea     rcx, [rbp+var_20]
0x18005973f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180059744  jmp     loc_1800599B5
0x180059749  lea     rcx, [rbp+pvarg]; pvarg
0x18005974d  call    cs:__imp_VariantClear
0x180059754  nop     dword ptr [rax+rax+00h]
0x180059759  nop
0x18005975a  lea     rcx, [rbp+arg_18]
0x18005975e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180059763  nop
0x180059764  lea     rcx, [rbp+var_20]
0x180059768  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005976d  xor     eax, eax
0x18005976f  mov     rbx, [rsp+50h+arg_8]
0x180059777  add     rsp, 50h
0x18005977b  pop     r15
0x18005977d  pop     r14
0x18005977f  pop     rdi
0x180059780  pop     rsi
0x180059781  pop     rbp
0x180059782  retn
0x180059784  add     rdi, 8
0x180059788  mov     rcx, rdi; this
0x18005978b  call    ?SetExpectedValue@CNodeCacheManager@@QEAAJPEAUtagVARIANT@@@Z; CNodeCacheManager::SetExpectedValue(tagVARIANT *)
0x180059790  mov     ebx, eax
0x180059792  test    eax, eax
0x180059794  jns     short loc_1800597A0
0x180059796  mov     edx, 449h
0x18005979b  jmp     loc_1800599A2
0x1800597a0  lea     rdx, [rbp+hKey]; unsigned int *
0x1800597a4  mov     rcx, rdi; this
0x1800597a7  call    ?GetExpectedValueSemanticType@CNodeCacheManager@@QEAAJPEAK@Z; CNodeCacheManager::GetExpectedValueSemanticType(ulong *)
0x1800597ac  mov     r8d, dword ptr [rbp+hKey]
0x1800597b0  test    eax, eax
0x1800597b2  cmovs   r8d, r15d
0x1800597b6  cmp     r8d, 2
0x1800597ba  jnz     short loc_18005976D
0x1800597bc  xor     edx, edx; unsigned int
0x1800597be  mov     rcx, rdi; this
0x1800597c1  call    ?SetExpectedValueSemanticType@CNodeCacheManager@@QEAAJK@Z; CNodeCacheManager::SetExpectedValueSemanticType(ulong)
0x1800597c6  mov     ebx, eax
0x1800597c8  test    eax, eax
0x1800597ca  jns     short loc_18005976D
0x1800597cc  mov     edx, 454h
0x1800597d1  jmp     loc_1800599A2
0x1800597d6  mov     eax, 8
0x1800597db  cmp     ax, [rdx]
0x1800597de  jz      short loc_1800597EA
0x1800597e0  mov     edx, 441h
0x1800597e5  jmp     loc_18005999D
0x1800597ea  mov     [rbp+hKey], r15
0x1800597ee  mov     rsi, [rdx+8]
0x1800597f2  test    rsi, rsi
0x1800597f5  jnz     short loc_1800597FE
0x1800597f7  mov     ebx, 80070057h
0x1800597fc  jmp     short loc_180059857
0x1800597fe  mov     [rsp+50h+var_28], r15d; int
0x180059803  lea     rax, [rbp+hKey]
0x180059807  mov     [rsp+50h+var_30], rax; HKEY *
0x18005980c  mov     r9, [rcx+18h]; unsigned __int16 *
0x180059810  mov     r8, [rcx+10h]; unsigned __int16 *
0x180059814  mov     rdx, [rcx+8]; unsigned __int16 *
0x180059818  call    ?GetNodeIdKey@CNodeCacheManager@@AEAAJPEBG00PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetNodeIdKey(ushort const *,ushort const *,ushort const *,HKEY__ * *,int)
0x18005981d  mov     ebx, eax
0x18005981f  mov     rdi, [rbp+hKey]
0x180059823  test    eax, eax
0x180059825  js      short loc_18005983B
0x180059827  mov     r9, rsi; unsigned __int16 *
0x18005982a  lea     r8, aNodeuri_4; "NodeUri"
0x180059831  mov     rdx, rdi; HKEY
0x180059834  call    ?SetRegValueBstr@CNodeCacheManager@@AEAAJPEAUHKEY__@@PEBGPEAG@Z; CNodeCacheManager::SetRegValueBstr(HKEY__ *,ushort const *,ushort *)
0x180059839  mov     ebx, eax
0x18005983b  test    rdi, rdi
0x18005983e  jz      short loc_18005984F
0x180059840  mov     rcx, rdi; hKey
0x180059843  call    cs:__imp_RegCloseKey
0x18005984a  nop     dword ptr [rax+rax+00h]
0x18005984f  test    ebx, ebx
0x180059851  jns     loc_18005976D
0x180059857  mov     edx, 442h
0x18005985c  jmp     loc_1800599A2
0x180059861  cmp     r15w, [rdx]
0x180059865  jz      short loc_180059871
0x180059867  mov     edx, 429h
0x18005986c  jmp     loc_18005999D
0x180059871  mov     [rbp+hKey], r15
0x180059875  mov     [rsp+50h+var_28], 1; int
0x18005987d  lea     rax, [rbp+hKey]
0x180059881  mov     [rsp+50h+var_30], rax; HKEY *
0x180059886  mov     r9, [rcx+18h]; unsigned __int16 *
0x18005988a  mov     r8, [rcx+10h]; unsigned __int16 *
0x18005988e  mov     rdx, [rcx+8]; unsigned __int16 *
0x180059892  call    ?GetNodeIdKey@CNodeCacheManager@@AEAAJPEBG00PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetNodeIdKey(ushort const *,ushort const *,ushort const *,HKEY__ * *,int)
0x180059897  mov     ebx, eax
0x180059899  mov     rcx, [rbp+hKey]; hKey
0x18005989d  test    rcx, rcx
0x1800598a0  jz      short loc_1800598AE
0x1800598a2  call    cs:__imp_RegCloseKey
0x1800598a9  nop     dword ptr [rax+rax+00h]
0x1800598ae  test    ebx, ebx
0x1800598b0  jns     loc_18005976D
0x1800598b6  mov     edx, 42Ah
0x1800598bb  jmp     loc_1800599A2
0x1800598c0  cmp     r15w, [rdx]
0x1800598c4  jz      short loc_1800598D0
0x1800598c6  mov     edx, 421h
0x1800598cb  jmp     loc_18005999D
0x1800598d0  mov     [rbp+hKey], r15
0x1800598d4  mov     dword ptr [rsp+50h+var_30], 1; int
0x1800598dc  lea     r9, [rbp+hKey]; HKEY *
0x1800598e0  mov     r8, [rcx+10h]; unsigned __int16 *
0x1800598e4  mov     rdx, [rcx+8]; unsigned __int16 *
0x1800598e8  call    ?GetNodesKey@CNodeCacheManager@@AEAAJPEBG0PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetNodesKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800598ed  mov     ebx, eax
0x1800598ef  mov     rcx, [rbp+hKey]; hKey
0x1800598f3  test    rcx, rcx
0x1800598f6  jz      short loc_180059904
0x1800598f8  call    cs:__imp_RegCloseKey
0x1800598ff  nop     dword ptr [rax+rax+00h]
0x180059904  test    ebx, ebx
0x180059906  jns     loc_18005976D
0x18005990c  mov     edx, 422h
0x180059911  jmp     loc_1800599A2
0x180059916  mov     eax, 8
0x18005991b  cmp     ax, [rdx]
0x18005991e  jz      short loc_180059927
0x180059920  mov     edx, 431h
0x180059925  jmp     short loc_18005999D
0x180059927  mov     rsi, [rdx+8]
0x18005992b  mov     [rbp+hKey], r15
0x18005992f  test    rsi, rsi
  ... truncated ...
```
