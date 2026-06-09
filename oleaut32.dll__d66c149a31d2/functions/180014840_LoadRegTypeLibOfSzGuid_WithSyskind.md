# LoadRegTypeLibOfSzGuid_WithSyskind

- ea: `0x180014840`
- end: `0x180014ed9`
- name: `LoadRegTypeLibOfSzGuid_WithSyskind`
- size: `1689`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013900`
- `0x1800155b0`
- `0x180042130`
- `0x180059124`
- `0x180059b90`

## callees

- `0x18000a830`
- `0x180011f84`
- `0x180011fb4`
- `0x180012b70`
- `0x180014840`
- `0x180014ee0`
- `0x180014f04`
- `0x180014f30`
- `0x1800161b8`
- `0x18001a954`
- `0x180037d28`
- `0x18004a504`
- `0x18004d900`
- `0x18004e530`
- `0x18004ebb0`
- `0x180056778`
- `0x1800590c0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180014c1e`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180014c1e`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180014e13`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180014e13`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800148bd`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800148bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800149de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800149de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e71`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32RedirectTypeLibrary` at `0x180014927`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32RedirectTypeLibrary` at `0x180014927`

## string_xrefs

- `0x180014c33`: `mincore\com\oleaut32\typelib\tlibapi.cpp`
- `0x180014c98`: `mincore\com\oleaut32\typelib\tlibapi.cpp`
- `0x180014cfc`: `mincore\com\oleaut32\typelib\tlibapi.cpp`
- `0x180014d37`: `mincore\com\oleaut32\typelib\tlibapi.cpp`
- `0x180014ddd`: `mincore\com\oleaut32\typelib\tlibapi.cpp`
- `0x180014d6a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall LoadRegTypeLibOfSzGuid_WithSyskind(
        ITypeLib *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned int a4,
        int a5,
        BSTR *a6,
        int a7,
        ITypeLib **a8,
        char a9)
{
  HRESULT v13; // eax
  unsigned int v14; // ebx
  wil::details *v15; // rbx
  int v16; // eax
  const char *v17; // r9
  int RegTypeLibIsolated; // esi
  const OLECHAR *StringRawBuffer; // rdi
  OLECHAR *v20; // r14
  HRESULT v21; // esi
  LPVOID v22; // rsi
  __int64 (__fastcall *v23)(LPVOID, GUID *, _QWORD, _QWORD); // rdi
  int TypeLibPathFromRegistry; // edi
  LPVOID v25; // rcx
  ITypeLib *v26; // rsi
  REGKIND v27; // r12d
  HRESULT v28; // r15d
  BSTR *v29; // r14
  ITypeLib *v30; // rax
  void *v31; // rdx
  LPVOID v33; // rcx
  void *v34; // rdx
  LCID UserDefaultLCID; // eax
  void *v36; // rdx
  BSTR v37; // rax
  const OLECHAR *v38; // rax
  void *v39; // rdx
  __int64 v40; // rsi
  wil::details *v41; // rax
  int v42; // ecx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 *v45; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v48; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v49; // [rsp+68h] [rbp-98h] BYREF
  ITypeLib *pptlib; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v51; // [rsp+78h] [rbp-88h]
  unsigned int v52; // [rsp+7Ch] [rbp-84h]
  LPVOID v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Token; // [rsp+90h] [rbp-70h] BYREF
  BSTR *v56; // [rsp+98h] [rbp-68h]
  GUID iid; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR szFile[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  pptlib = a1;
  v56 = a6;
  if ( a8 )
    *a8 = 0;
  if ( a6 )
    *a6 = 0;
  iid = 0;
  v13 = IIDFromString((LPCOLESTR)a1, &iid);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B8,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    return v14;
  }
  memset_0(szFile, 0, 0x208u);
  v15 = 0;
  v54 = 260;
  if ( (unsigned __int8)IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent() )
  {
    v45 = &v54;
    ppva = a5;
    v16 = SxsOleAut32RedirectTypeLibrary(a1, a2, a3, a4);
    RegTypeLibIsolated = v16;
    if ( !v16 )
    {
      StringRawBuffer = szFile;
LABEL_39:
      v20 = (OLECHAR *)StringRawBuffer;
      goto LABEL_23;
    }
    StringRawBuffer = 0;
    if ( v16 == -2147024774 )
    {
      v40 = v54;
      if ( v54 == -1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v17);
      v41 = (wil::details *)wil::details::heap_allocator::allocate(2 * v54 + 2);
      v15 = v41;
      if ( !v41 )
      {
        TypeLibPathFromRegistry = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9CC,
          (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
          (const char *)0x8007000ELL,
          a5);
        WindowsDeleteString(0);
        return (unsigned int)TypeLibPathFromRegistry;
      }
      v42 = (int)pptlib;
      *(_WORD *)v41 = 0;
      *((_WORD *)v41 + v40) = 0;
      RegTypeLibIsolated = LoadRegTypeLibIsolated(v42, a2, a3, a4, a5, (__int64)&v54, (__int64)v41);
      if ( !RegTypeLibIsolated )
      {
        StringRawBuffer = (const OLECHAR *)v15;
        goto LABEL_39;
      }
    }
    if ( RegTypeLibIsolated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D6,
        (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
        (const char *)(unsigned int)RegTypeLibIsolated,
        ppva);
      WindowsDeleteString(0);
      if ( v15 )
        wil::details::FreeProcessHeap(v15, v39);
      return (unsigned int)RegTypeLibIsolated;
    }
    if ( RegTypeLibIsolated != 1 )
      goto LABEL_39;
  }
  v20 = 0;
  if ( a4 == 1024 )
  {
    UserDefaultLCID = GetUserDefaultLCID();
  }
  else
  {
    if ( a4 != 2048 )
      goto LABEL_13;
    UserDefaultLCID = GetSystemDefaultLCID();
  }
  a4 = UserDefaultLCID;
LABEL_13:
  v21 = -2147467231;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  if ( a9 )
    goto LABEL_77;
  Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(&v53);
  v21 = CoCreateInstance(
          &GUID_00000346_0000_0000_c000_000000000046,
          0,
          1u,
          &GUID_e085ad58_b839_4625_b40b_4cc546e82d75,
          &v53);
  if ( v21 < 0
    || (v22 = v53,
        v23 = *(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD, _QWORD))(*(_QWORD *)v53 + 24LL),
        WindowsDeleteString(0),
        LODWORD(v45) = a4,
        LOBYTE(ppva) = a5 != 0,
        v21 = v23(v22, &iid, a2, a3),
        v21 < 0)
    || a5
    || a2 != v51
    || a3 != v52 )
  {
LABEL_77:
    v48 = 0;
    v49 = 0;
    TypeLibPathFromRegistry = GetTypeLibPathFromRegistry(
                                (const unsigned __int16 *)pptlib,
                                a2,
                                a3,
                                a4,
                                a5,
                                (unsigned int)v45,
                                szFile,
                                &v48,
                                &v49);
    if ( TypeLibPathFromRegistry >= 0 && !a5 && a2 == v48 && a3 == v49 )
      goto LABEL_20;
    if ( v21 < 0 )
    {
      if ( TypeLibPathFromRegistry < 0 )
      {
        v33 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
        }
        goto LABEL_44;
      }
      goto LABEL_20;
    }
    if ( TypeLibPathFromRegistry >= 0 && v51 <= v48 && (v51 != v48 || v52 < v49) )
    {
LABEL_20:
      StringRawBuffer = szFile;
      v20 = szFile;
      goto LABEL_21;
    }
  }
  StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
LABEL_21:
  v25 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_23:
  v26 = 0;
  pptlib = 0;
  if ( !a8 )
    goto LABEL_30;
  if ( a7 == 1 )
  {
    v27 = 32;
  }
  else
  {
    v27 = REGKIND_DEFAULT;
    if ( a7 == 3 )
      v27 = 64;
  }
  Token = 0;
  v28 = SuspendImpersonate(&Token);
  if ( v28 < 0 )
    goto LABEL_49;
  Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(&pptlib);
  v28 = LoadTypeLibEx(StringRawBuffer, v27, &pptlib);
  if ( v28 < 0 && v20 )
  {
    Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(&pptlib);
    v38 = (const OLECHAR *)IsolateFilename(v20, 0);
    v28 = LoadTypeLibEx(v38, v27, &pptlib);
  }
  ResumeImpersonate(Token);
  v26 = pptlib;
  if ( v28 < 0 )
  {
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA58,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
      (const char *)(unsigned int)v28,
      ppva);
    if ( v26 )
      ((void (__fastcall *)(ITypeLib *))v26->lpVtbl->Release)(v26);
    WindowsDeleteString(0);
    if ( v15 )
      wil::details::FreeProcessHeap(v15, v36);
    return (unsigned int)v28;
  }
  else
  {
LABEL_30:
    v29 = v56;
    if ( v56 )
    {
      v37 = SysAllocString(StringRawBuffer);
      *v29 = v37;
      if ( !v37 )
      {
        TypeLibPathFromRegistry = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5F,
          (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
          (const char *)0x8007000ELL,
          ppva);
        Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(&pptlib);
LABEL_44:
        WindowsDeleteString(0);
        if ( v15 )
          wil::details::FreeProcessHeap(v15, v34);
        return (unsigned int)TypeLibPathFromRegistry;
      }
    }
    if ( a8 )
    {
      v30 = v26;
      v26 = 0;
      *a8 = v30;
    }
    if ( v26 )
      ((void (__fastcall *)(ITypeLib *))v26->lpVtbl->Release)(v26);
    WindowsDeleteString(0);
    if ( v15 )
      wil::details::FreeProcessHeap(v15, v31);
    return 0;
  }
}

```

## disassembly

```asm
0x180014840  push    rbp
0x180014842  push    rbx
0x180014843  push    rsi
0x180014844  push    rdi
0x180014845  push    r12
0x180014847  push    r13
0x180014849  push    r14
0x18001484b  push    r15
0x18001484d  lea     rbp, [rsp-1D8h]
0x180014855  sub     rsp, 2D8h
0x18001485c  mov     rax, cs:__security_cookie
0x180014863  xor     rax, rsp
0x180014866  mov     [rbp+210h+var_50], rax
0x18001486d  mov     r13, [rbp+210h+arg_38]
0x180014874  xor     r12d, r12d
0x180014877  mov     rax, [rbp+210h+arg_28]
0x18001487e  mov     r15d, r9d
0x180014881  mov     [rsp+310h+var_2C0], r8w
0x180014887  movzx   edi, r8w
0x18001488b  mov     [rsp+310h+var_2B0], dx
0x180014890  movzx   r14d, dx
0x180014894  mov     [rsp+310h+pptlib], rcx
0x180014899  mov     rsi, rcx
0x18001489c  mov     [rbp+210h+var_278], rax
0x1800148a0  test    r13, r13
0x1800148a3  jz      short loc_1800148A9
0x1800148a5  mov     [r13+0], r12
0x1800148a9  test    rax, rax
0x1800148ac  jnz     loc_180014C75
0x1800148b2  xorps   xmm0, xmm0
0x1800148b5  lea     rdx, [rbp+210h+iid]; lpiid
0x1800148b9  movups  xmmword ptr [rbp+210h+iid.Data1], xmm0
0x1800148bd  call    cs:__imp_IIDFromString
0x1800148c3  mov     ebx, eax
0x1800148c5  test    eax, eax
0x1800148c7  js      loc_180014D30
0x1800148cd  xor     edx, edx; Val
0x1800148cf  lea     rcx, [rbp+210h+szFile]; void *
0x1800148d3  mov     r8d, 208h; Size
0x1800148d9  call    memset_0
0x1800148de  mov     rbx, r12
0x1800148e1  mov     [rsp+310h+string], r12
0x1800148e6  mov     [rbp+210h+var_288], 104h
0x1800148ee  call    IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent
0x1800148f3  mov     r12d, [rbp+210h+arg_20]
0x1800148fa  test    al, al
0x1800148fc  jz      loc_180014D52
0x180014902  lea     rax, [rbp+210h+szFile]
0x180014906  mov     r9d, r15d
0x180014909  mov     [rsp+310h+var_2E0], rax
0x18001490e  movzx   r8d, di
0x180014912  lea     rax, [rbp+210h+var_288]
0x180014916  movzx   edx, r14w
0x18001491a  mov     qword ptr [rsp+310h+var_2E8], rax
0x18001491f  mov     rcx, rsi
0x180014922  mov     dword ptr [rsp+310h+ppv], r12d; int
0x180014927  call    cs:__imp_SxsOleAut32RedirectTypeLibrary
0x18001492d  mov     esi, eax
0x18001492f  test    eax, eax
0x180014931  jz      loc_180014BC4
0x180014937  xor     edi, edi
0x180014939  cmp     eax, 8007007Ah
0x18001493e  jz      loc_180014D59
0x180014944  test    esi, esi
0x180014946  js      loc_180014CF5
0x18001494c  cmp     esi, 1
0x18001494f  jnz     loc_180014BC8
0x180014955  mov     r14, rdi
0x180014958  cmp     r15d, 400h
0x18001495f  jz      loc_180014C1E
0x180014965  cmp     r15d, 800h
0x18001496c  jz      loc_180014E13
0x180014972  cmp     [rbp+210h+arg_40], 0
0x180014979  mov     esi, 80004021h
0x18001497e  mov     [rsp+310h+var_298], 0
0x180014986  mov     [rsp+310h+var_294], 0
0x18001498e  mov     [rbp+210h+var_290], 0
0x180014996  jnz     loc_180014A41
0x18001499c  lea     rcx, [rbp+210h+var_290]
0x1800149a0  call    ?InternalRelease@?$ComPtr@UITypeInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(void)
0x1800149a5  xor     edx, edx; pUnkOuter
0x1800149a7  lea     rax, [rbp+210h+var_290]
0x1800149ab  lea     r9, _GUID_e085ad58_b839_4625_b40b_4cc546e82d75; riid
0x1800149b2  mov     [rsp+310h+ppv], rax; ppv
0x1800149b7  lea     rcx, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x1800149be  lea     r8d, [rdx+1]; dwClsContext
0x1800149c2  call    cs:__imp_CoCreateInstance
0x1800149c8  mov     esi, eax
0x1800149ca  test    eax, eax
0x1800149cc  js      short loc_180014A41
0x1800149ce  mov     rsi, [rbp+210h+var_290]
0x1800149d2  mov     rcx, [rsp+310h+string]; string
0x1800149d7  mov     rax, [rsi]
0x1800149da  mov     rdi, [rax+18h]
0x1800149de  call    cs:__imp_WindowsDeleteString
0x1800149e4  movzx   eax, [rsp+310h+var_2B0]
0x1800149e9  lea     r8, [rsp+310h+var_294]
0x1800149ee  movzx   r9d, [rsp+310h+var_2C0]
0x1800149f4  test    r12d, r12d
0x1800149f7  mov     [rsp+310h+var_2D0], r8
0x1800149fc  mov     rcx, rsi
0x1800149ff  setnz   dl
0x180014a02  mov     [rsp+310h+string], 0
0x180014a0b  lea     r8, [rsp+310h+var_298]
0x180014a10  mov     [rsp+310h+var_2D8], r8
0x180014a15  lea     r8, [rsp+310h+string]
0x180014a1a  mov     [rsp+310h+var_2E0], r8
0x180014a1f  mov     r8d, eax
0x180014a22  mov     [rsp+310h+var_2E8], r15d; unsigned int
0x180014a27  mov     rax, rdi
0x180014a2a  mov     byte ptr [rsp+310h+ppv], dl
0x180014a2e  lea     rdx, [rbp+210h+iid]
0x180014a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a37  mov     esi, eax
0x180014a39  test    eax, eax
0x180014a3b  jns     loc_180014E1E
0x180014a41  movzx   r8d, [rsp+310h+var_2C0]; unsigned __int16
0x180014a47  xor     eax, eax
0x180014a49  mov     rcx, [rsp+310h+pptlib]; unsigned __int16 *
0x180014a4e  mov     r9d, r15d; unsigned int
0x180014a51  movzx   r15d, [rsp+310h+var_2B0]
0x180014a57  mov     [rsp+310h+var_2AC], ax
0x180014a5c  movzx   edx, r15w; unsigned __int16
0x180014a60  mov     [rsp+310h+var_2A8], ax
0x180014a65  lea     rax, [rsp+310h+var_2A8]
0x180014a6a  mov     [rsp+310h+var_2D0], rax; unsigned __int16 *
0x180014a6f  lea     rax, [rsp+310h+var_2AC]
0x180014a74  mov     [rsp+310h+var_2D8], rax; unsigned __int16 *
0x180014a79  lea     rax, [rbp+210h+szFile]
0x180014a7d  mov     [rsp+310h+var_2E0], rax; unsigned __int16 *
0x180014a82  mov     dword ptr [rsp+310h+ppv], r12d; int
0x180014a87  call    ?GetTypeLibPathFromRegistry@@YAJPEBGGGKHKPEAG11@Z; GetTypeLibPathFromRegistry(ushort const *,ushort,ushort,ulong,int,ulong,ushort *,ushort *,ushort *)
0x180014a8c  mov     edi, eax
0x180014a8e  test    eax, eax
0x180014a90  js      loc_180014BD0
0x180014a96  test    r12d, r12d
0x180014a99  jnz     loc_180014BD0
0x180014a9f  cmp     r15w, [rsp+310h+var_2AC]
0x180014aa5  jnz     loc_180014BD0
0x180014aab  movzx   eax, [rsp+310h+var_2C0]
0x180014ab0  cmp     ax, [rsp+310h+var_2A8]
0x180014ab5  jnz     loc_180014BD0
0x180014abb  lea     rdi, [rbp+210h+szFile]
0x180014abf  lea     r14, [rbp+210h+szFile]
0x180014ac3  mov     rcx, [rbp+210h+var_290]
0x180014ac7  test    rcx, rcx
0x180014aca  jz      short loc_180014AE0
0x180014acc  mov     [rbp+210h+var_290], 0
0x180014ad4  mov     rax, [rcx]
0x180014ad7  mov     rax, [rax+10h]
0x180014adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae0  xor     esi, esi
0x180014ae2  mov     [rsp+310h+pptlib], rsi
0x180014ae7  test    r13, r13
0x180014aea  jz      short loc_180014B5E
0x180014aec  cmp     [rbp+210h+arg_30], 1
0x180014af3  jz      loc_180014E8C
0x180014af9  xor     r12d, r12d
0x180014afc  lea     eax, [rsi+40h]
0x180014aff  cmp     [rbp+210h+arg_30], 3
0x180014b06  cmovz   r12d, eax
0x180014b0a  lea     rcx, [rbp+210h+Token]; TokenHandle
0x180014b0e  mov     [rbp+210h+Token], rsi
0x180014b12  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180014b17  mov     r15d, eax
0x180014b1a  test    eax, eax
0x180014b1c  js      loc_180014C2C
0x180014b22  lea     rcx, [rsp+310h+pptlib]
0x180014b27  call    ?InternalRelease@?$ComPtr@UITypeLib@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(void)
0x180014b2c  lea     r8, [rsp+310h+pptlib]; pptlib
0x180014b31  mov     edx, r12d; regkind
0x180014b34  mov     rcx, rdi; szFile
0x180014b37  call    LoadTypeLibEx
0x180014b3c  mov     r15d, eax
0x180014b3f  test    eax, eax
0x180014b41  js      loc_180014CC0
0x180014b47  mov     rcx, [rbp+210h+Token]; Token
0x180014b4b  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180014b50  mov     rsi, [rsp+310h+pptlib]
0x180014b55  test    r15d, r15d
0x180014b58  js      loc_180014C2C
0x180014b5e  mov     r14, [rbp+210h+var_278]
0x180014b62  test    r14, r14
0x180014b65  jnz     loc_180014C7D
0x180014b6b  test    r13, r13
0x180014b6e  jz      short loc_180014B79
0x180014b70  mov     rax, rsi
0x180014b73  xor     esi, esi
0x180014b75  mov     [r13+0], rax
0x180014b79  test    rsi, rsi
0x180014b7c  jnz     loc_180014EB8
0x180014b82  mov     rcx, [rsp+310h+string]; string
0x180014b87  call    cs:__imp_WindowsDeleteString
0x180014b8d  mov     [rsp+310h+string], 0
0x180014b96  test    rbx, rbx
0x180014b99  jnz     loc_180014ECC
0x180014b9f  xor     eax, eax
0x180014ba1  mov     rcx, [rbp+210h+var_50]
0x180014ba8  xor     rcx, rsp; StackCookie
0x180014bab  call    __security_check_cookie
0x180014bb0  add     rsp, 2D8h
0x180014bb7  pop     r15
0x180014bb9  pop     r14
0x180014bbb  pop     r13
0x180014bbd  pop     r12
0x180014bbf  pop     rdi
0x180014bc0  pop     rsi
0x180014bc1  pop     rbx
0x180014bc2  pop     rbp
0x180014bc3  retn
0x180014bc4  lea     rdi, [rbp+210h+szFile]
0x180014bc8  mov     r14, rdi
0x180014bcb  jmp     loc_180014AE0
0x180014bd0  test    esi, esi
0x180014bd2  jns     loc_180014E46
0x180014bd8  test    edi, edi
0x180014bda  jns     loc_180014ABB
0x180014be0  mov     rcx, [rbp+210h+var_290]
0x180014be4  test    rcx, rcx
0x180014be7  jz      short loc_180014BFD
0x180014be9  mov     [rbp+210h+var_290], 0
0x180014bf1  mov     rax, [rcx]
0x180014bf4  mov     rax, [rax+10h]
0x180014bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bfd  mov     rcx, [rsp+310h+string]; string
0x180014c02  call    cs:__imp_WindowsDeleteString
0x180014c08  mov     [rsp+310h+string], 0
0x180014c11  test    rbx, rbx
0x180014c14  jnz     loc_180014E7F
0x180014c1a  mov     eax, edi
0x180014c1c  jmp     short loc_180014BA1
0x180014c1e  call    cs:__imp_GetUserDefaultLCID
0x180014c24  mov     r15d, eax
0x180014c27  jmp     loc_180014972
0x180014c2c  mov     rcx, [rbp+218h]; this
0x180014c33  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180014c3a  mov     r9d, r15d; char *
0x180014c3d  mov     edx, 0A58h; void *
0x180014c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c47  test    rsi, rsi
0x180014c4a  jnz     loc_180014E97
0x180014c50  mov     rcx, [rsp+310h+string]; string
0x180014c55  call    cs:__imp_WindowsDeleteString
0x180014c5b  mov     [rsp+310h+string], 0
0x180014c64  test    rbx, rbx
0x180014c67  jnz     loc_180014EAB
0x180014c6d  mov     eax, r15d
0x180014c70  jmp     loc_180014BA1
0x180014c75  mov     [rax], r12
0x180014c78  jmp     loc_1800148B2
0x180014c7d  mov     rcx, rdi; psz
0x180014c80  call    SysAllocString
0x180014c85  mov     [r14], rax
0x180014c88  test    rax, rax
0x180014c8b  jnz     loc_180014B6B
0x180014c91  mov     rcx, [rbp+218h]; this
0x180014c98  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180014c9f  mov     edi, 8007000Eh
0x180014ca4  mov     edx, 0A5Fh; void *
0x180014ca9  mov     r9d, edi; char *
0x180014cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cb1  lea     rcx, [rsp+310h+pptlib]
0x180014cb6  call    ?InternalRelease@?$ComPtr@UITypeLib@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(void)
0x180014cbb  jmp     loc_180014BFD
0x180014cc0  test    r14, r14
0x180014cc3  jz      loc_180014B47
0x180014cc9  lea     rcx, [rsp+310h+pptlib]
0x180014cce  call    ?InternalRelease@?$ComPtr@UITypeLib@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ITypeLib>::InternalRelease(void)
0x180014cd3  xor     edx, edx
0x180014cd5  mov     rcx, r14
0x180014cd8  call    IsolateFilename
0x180014cdd  lea     r8, [rsp+310h+pptlib]; pptlib
0x180014ce2  mov     edx, r12d; regkind
0x180014ce5  mov     rcx, rax; szFile
0x180014ce8  call    LoadTypeLibEx
0x180014ced  mov     r15d, eax
0x180014cf0  jmp     loc_180014B47
0x180014cf5  mov     rcx, [rbp+218h]; this
0x180014cfc  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180014d03  mov     r9d, esi; char *
0x180014d06  mov     edx, 9D6h; void *
0x180014d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d10  mov     rcx, [rsp+310h+string]; string
0x180014d15  call    cs:__imp_WindowsDeleteString
0x180014d1b  mov     [rsp+310h+string], rdi
0x180014d20  test    rbx, rbx
0x180014d23  jnz     loc_180014E06
0x180014d29  mov     eax, esi
0x180014d2b  jmp     loc_180014BA1
0x180014d30  mov     rcx, [rbp+218h]; this
0x180014d37  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180014d3e  mov     r9d, ebx; char *
0x180014d41  mov     edx, 9B8h; void *
0x180014d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d4b  mov     eax, ebx
0x180014d4d  jmp     loc_180014BA1
0x180014d52  xor     edi, edi
0x180014d54  jmp     loc_180014955
0x180014d59  mov     rsi, [rbp+210h+var_288]
0x180014d5d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
