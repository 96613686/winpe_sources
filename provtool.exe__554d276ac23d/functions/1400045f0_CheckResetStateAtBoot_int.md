# CheckResetStateAtBoot(int *)

- ea: `0x1400045f0`
- end: `0x140004ccb`
- name: `?CheckResetStateAtBoot@@YAJPEAH@Z`
- size: `1755`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x1400022c8`
- `0x1400045f0`
- `0x140007734`
- `0x140007758`
- `0x140008820`
- `0x140008ba8`
- `0x140009340`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004a91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004a91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004ba5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004c25`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004ba5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004c25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004b75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ab1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000464e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000464e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400048a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400048a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400048b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400049b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004a21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004b25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004bb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400048b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400049b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004a21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004b25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004bb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004c36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400049a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400049a1`
- `OLEAUT32!__imp_SysAllocString` at `0x14000476f`
- `OLEAUT32!__imp_SysAllocString` at `0x140004824`
- `OLEAUT32!__imp_SysAllocString` at `0x14000476f`
- `OLEAUT32!__imp_SysAllocString` at `0x140004824`
- `OLEAUT32!__imp_SysFreeString` at `0x1400047af`
- `OLEAUT32!__imp_SysFreeString` at `0x140004861`
- `OLEAUT32!__imp_SysFreeString` at `0x1400047af`
- `OLEAUT32!__imp_SysFreeString` at `0x140004861`

## string_xrefs

- `0x140004ca6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140004cb8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140004993`: `InstallType`
- `0x140004a8a`: `provmigrate.dll`
- `0x140004ac7`: `Error loading provmigrate.dll.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CheckResetStateAtBoot(int *a1)
{
  LPVOID *v2; // rax
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  _QWORD *v6; // rcx
  __int64 result; // rax
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  _QWORD *v11; // rdi
  __int64 v12; // r14
  BSTR v13; // rax
  const char *v14; // r9
  OLECHAR *v15; // rbx
  int v16; // edi
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rdi
  __int64 v20; // r14
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // r8d
  _QWORD *v26; // rcx
  _QWORD *v27; // rcx
  unsigned int v28; // ebx
  _QWORD *v29; // rcx
  _QWORD *v30; // rcx
  unsigned int ValueW; // eax
  unsigned int v32; // r8d
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  unsigned int v35; // ebx
  _QWORD *v36; // rcx
  _QWORD *v37; // rcx
  int v38; // ecx
  HMODULE Library; // rax
  HMODULE v40; // rbx
  signed int LastError; // eax
  __int64 v42; // rcx
  __int64 v43; // r8
  _QWORD *v44; // rcx
  _QWORD *v45; // rcx
  __int64 (*ProcAddress)(void); // rax
  _QWORD *v47; // rcx
  _QWORD *v48; // rcx
  int v49; // eax
  _QWORD *v50; // rcx
  _QWORD *v51; // rcx
  int ppv; // [rsp+20h] [rbp-118h]
  unsigned int ppva; // [rsp+20h] [rbp-118h]
  unsigned int ppvb; // [rsp+20h] [rbp-118h]
  _QWORD *v55; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v56; // [rsp+58h] [rbp-E0h] BYREF
  int v57; // [rsp+60h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-C8h] BYREF
  int pvData; // [rsp+74h] [rbp-C4h] BYREF
  void *v61; // [rsp+78h] [rbp-C0h]
  int v62[4]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+90h] [rbp-A8h]
  __int128 v64; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-88h]
  __int128 v66; // [rsp+C0h] [rbp-78h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-68h]
  __int128 v68; // [rsp+E0h] [rbp-58h] BYREF
  const wchar_t *v69; // [rsp+F0h] [rbp-48h]
  __int64 v70; // [rsp+F8h] [rbp-40h]
  int *v71; // [rsp+100h] [rbp-38h]
  __int64 v72; // [rsp+108h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v57 = 0;
  *a1 = 0;
  v55 = 0;
  v2 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v55);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, v2);
  try
  {
    v4 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v6 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      }
      return v4;
    }
    *(_OWORD *)v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int128 *, __int128 *))(*v55 + 80LL))(v55, &v68, &v66, &v64);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
        (const char *)(unsigned int)v8,
        (int)v62);
      v10 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
      }
      return v9;
    }
    v56 = 0;
    v11 = v55;
    v12 = *v55;
    v13 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
    v15 = v13;
    v61 = v13;
    v57 = 1;
    if ( !v13 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    v16 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, _QWORD **))(v12 + 56))(v11, v13, &v56);
    SysFreeString(v15);
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
        (const char *)(unsigned int)v16,
        (int)v62);
      v17 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
      }
      v18 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      return (unsigned int)v16;
    }
    v19 = v56;
    v20 = *v56;
    v21 = SysAllocString(L"PostResetBoot");
    v23 = v21;
    v61 = v21;
    v57 = 2;
    if ( !v21 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    (*(void (__fastcall **)(_QWORD *, BSTR, _QWORD))(v20 + 120))(v19, v21, 0);
    SysFreeString(v23);
    hKey = 0;
    v24 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
            0,
            0,
            0,
            0x20019u,
            0,
            &hKey,
            0);
    if ( v24 == 2 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      v26 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      }
      v27 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
      }
      return 0;
    }
    if ( v24 )
    {
      v28 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xD8, v25, (const char *)v24, ppva);
      if ( hKey )
        RegCloseKey(hKey);
      v29 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      }
      v30 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
      }
      return v28;
    }
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"InstallType", 0x10u, 0, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      v33 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
      }
      v34 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
      }
      return 0;
    }
    if ( ValueW )
    {
      v35 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xE9, v32, (const char *)ValueW, ppvb);
      if ( hKey )
        RegCloseKey(hKey);
      v36 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
      }
      v37 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
      }
      return v35;
    }
    v38 = pvData;
    if ( (unsigned int)(pvData - 15) <= 1 )
      *a1 = 1;
    if ( v38 == 17 )
    {
      Library = LoadLibraryExW(L"provmigrate.dll", 0, 0x800u);
      v40 = Library;
      v61 = Library;
      if ( !Library )
      {
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v57 = LastError;
          v69 = L"Error loading provmigrate.dll.";
          v70 = 62;
          v71 = &v57;
          v72 = 4;
          McGenEventWrite_EventWriteTransfer(v42, PackageFailure, v43, 3, &v68);
        }
        if ( hKey )
          RegCloseKey(hKey);
        v44 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
        }
        v45 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
        }
        return 0;
      }
      ProcAddress = GetProcAddress(Library, "RunPostPowerwashOperationsStatusPagePhase");
      if ( !ProcAddress )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
          (const char *)0x80070032LL,
          ppvb);
        FreeLibrary(v40);
        if ( hKey )
          RegCloseKey(hKey);
        v47 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
        }
        v48 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v48 + 16LL))(v48, *v48);
        }
        return 2147942450LL;
      }
      v49 = ProcAddress();
      if ( v49 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
          (const char *)(unsigned int)v49,
          ppvb);
      FreeLibrary(v40);
    }
    if ( hKey )
      RegCloseKey(hKey);
    v50 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
    }
    v51 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x105,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x1400045f0  mov     [rsp+arg_8], rbx
0x1400045f5  mov     [rsp+arg_10], rsi
0x1400045fa  push    rdi
0x1400045fb  push    r14
0x1400045fd  push    r15
0x1400045ff  sub     rsp, 120h
0x140004606  mov     rax, cs:__security_cookie
0x14000460d  xor     rax, rsp
0x140004610  mov     [rsp+138h+var_28], rax
0x140004618  mov     rsi, rcx
0x14000461b  xor     r15d, r15d
0x14000461e  mov     [rsp+138h+var_D8], r15d
0x140004623  mov     [rcx], r15d
0x140004626  mov     [rsp+138h+var_E8], r15
0x14000462b  lea     rcx, [rsp+138h+var_E8]
0x140004630  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140004635  mov     [rsp+138h+ppv], rax; int
0x14000463a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140004641  xor     edx, edx; pUnkOuter
0x140004643  lea     r8d, [r15+1]; dwClsContext
0x140004647  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000464e  call    cs:__imp_CoCreateInstance
0x140004654  mov     ebx, eax
0x140004656  test    eax, eax
0x140004658  jns     short loc_14000469A
0x14000465a  mov     rcx, [rsp+138h]; this
0x140004662  mov     r9d, eax; char *
0x140004665  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000466c  mov     edx, 0BAh; void *
0x140004671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004676  nop
0x140004677  mov     rcx, [rsp+138h+var_E8]
0x14000467c  test    rcx, rcx
0x14000467f  jz      short loc_140004693
0x140004681  mov     [rsp+138h+var_E8], r15
0x140004686  mov     rax, [rcx]
0x140004689  mov     rax, [rax+10h]
0x14000468d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004692  nop
0x140004693  mov     eax, ebx
0x140004695  jmp     loc_140004C7D
0x14000469a  xorps   xmm1, xmm1
0x14000469d  xor     eax, eax
0x14000469f  mov     rcx, [rsp+138h+var_E8]
0x1400046a4  movaps  xmmword ptr [rsp+138h+var_B8], xmm1
0x1400046ac  mov     [rsp+138h+var_A8], rax
0x1400046b4  movaps  [rsp+138h+var_98], xmm1
0x1400046bc  mov     [rsp+138h+var_88], rax
0x1400046c4  movaps  [rsp+138h+var_78], xmm1
0x1400046cc  mov     [rsp+138h+var_68], rax
0x1400046d4  movaps  [rsp+138h+var_58], xmm1
0x1400046dc  mov     [rsp+138h+var_48], rax
0x1400046e4  mov     rax, [rcx]
0x1400046e7  lea     rdx, [rsp+138h+var_B8]
0x1400046ef  mov     [rsp+138h+ppv], rdx; int
0x1400046f4  lea     r9, [rsp+138h+var_98]
0x1400046fc  lea     r8, [rsp+138h+var_78]
0x140004704  lea     rdx, [rsp+138h+var_58]
0x14000470c  mov     rax, [rax+50h]
0x140004710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004715  mov     ebx, eax
0x140004717  test    eax, eax
0x140004719  jns     short loc_14000475B
0x14000471b  mov     rcx, [rsp+138h]; this
0x140004723  mov     r9d, eax; char *
0x140004726  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000472d  mov     edx, 0C0h; void *
0x140004732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004737  nop
0x140004738  mov     rcx, [rsp+138h+var_E8]
0x14000473d  test    rcx, rcx
0x140004740  jz      short loc_140004754
0x140004742  mov     [rsp+138h+var_E8], r15
0x140004747  mov     rax, [rcx]
0x14000474a  mov     rax, [rax+10h]
0x14000474e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004753  nop
0x140004754  mov     eax, ebx
0x140004756  jmp     loc_140004C7D
0x14000475b  mov     [rsp+138h+var_E0], r15
0x140004760  mov     rdi, [rsp+138h+var_E8]
0x140004765  mov     r14, [rdi]
0x140004768  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x14000476f  call    cs:__imp_SysAllocString
0x140004775  mov     rbx, rax
0x140004778  mov     [rsp+138h+var_C0], rax
0x14000477d  mov     [rsp+138h+var_D8], 1
0x140004785  mov     rcx, [rsp+138h]; this
0x14000478d  test    rax, rax
0x140004790  jz      loc_140004CA6
0x140004796  lea     r8, [rsp+138h+var_E0]
0x14000479b  mov     rdx, rbx
0x14000479e  mov     rcx, rdi
0x1400047a1  mov     rax, [r14+38h]
0x1400047a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047aa  mov     edi, eax
0x1400047ac  mov     rcx, rbx; bstrString
0x1400047af  call    cs:__imp_SysFreeString
0x1400047b5  test    edi, edi
0x1400047b7  jns     short loc_140004815
0x1400047b9  mov     rcx, [rsp+138h]; this
0x1400047c1  mov     r9d, edi; char *
0x1400047c4  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x1400047cb  mov     edx, 0C4h; void *
0x1400047d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400047d5  nop
0x1400047d6  mov     rcx, [rsp+138h+var_E0]
0x1400047db  test    rcx, rcx
0x1400047de  jz      short loc_1400047F2
0x1400047e0  mov     [rsp+138h+var_E0], r15
0x1400047e5  mov     rax, [rcx]
0x1400047e8  mov     rax, [rax+10h]
0x1400047ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047f1  nop
0x1400047f2  mov     rcx, [rsp+138h+var_E8]
0x1400047f7  test    rcx, rcx
0x1400047fa  jz      short loc_14000480E
0x1400047fc  mov     [rsp+138h+var_E8], r15
0x140004801  mov     rax, [rcx]
0x140004804  mov     rax, [rax+10h]
0x140004808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000480d  nop
0x14000480e  mov     eax, edi
0x140004810  jmp     loc_140004C7D
0x140004815  mov     rdi, [rsp+138h+var_E0]
0x14000481a  mov     r14, [rdi]
0x14000481d  lea     rcx, aPostresetboot; "PostResetBoot"
0x140004824  call    cs:__imp_SysAllocString
0x14000482a  mov     rbx, rax
0x14000482d  mov     [rsp+138h+var_C0], rax
0x140004832  mov     [rsp+138h+var_D8], 2
0x14000483a  mov     rcx, [rsp+138h]; this
0x140004842  test    rax, rax
0x140004845  jz      loc_140004CB8
0x14000484b  xor     r8d, r8d
0x14000484e  mov     rdx, rbx
0x140004851  mov     rcx, rdi
0x140004854  mov     rax, [r14+78h]
0x140004858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000485d  nop
0x14000485e  mov     rcx, rbx; bstrString
0x140004861  call    cs:__imp_SysFreeString
0x140004867  nop
0x140004868  mov     [rsp+138h+hKey], r15
0x14000486d  mov     [rsp+138h+lpdwDisposition], r15; lpdwDisposition
0x140004872  lea     rax, [rsp+138h+hKey]
0x140004877  mov     [rsp+138h+phkResult], rax; phkResult
0x14000487c  mov     [rsp+138h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140004881  mov     [rsp+138h+samDesired], 20019h; samDesired
0x140004889  mov     dword ptr [rsp+138h+ppv], r15d; unsigned int
0x14000488e  xor     r9d, r9d; lpClass
0x140004891  xor     r8d, r8d; Reserved
0x140004894  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000489b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400048a2  call    cs:__imp_RegCreateKeyExW
0x1400048a8  cmp     eax, 2
0x1400048ab  jnz     short loc_1400048FD
0x1400048ad  mov     rcx, [rsp+138h+hKey]; hKey
0x1400048b2  test    rcx, rcx
0x1400048b5  jz      short loc_1400048BE
0x1400048b7  call    cs:__imp_RegCloseKey
0x1400048bd  nop
0x1400048be  mov     rcx, [rsp+138h+var_E0]
0x1400048c3  test    rcx, rcx
0x1400048c6  jz      short loc_1400048DA
0x1400048c8  mov     [rsp+138h+var_E0], r15
0x1400048cd  mov     rax, [rcx]
0x1400048d0  mov     rax, [rax+10h]
0x1400048d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048d9  nop
0x1400048da  mov     rcx, [rsp+138h+var_E8]
0x1400048df  test    rcx, rcx
0x1400048e2  jz      short loc_1400048F6
0x1400048e4  mov     [rsp+138h+var_E8], r15
0x1400048e9  mov     rax, [rcx]
0x1400048ec  mov     rax, [rax+10h]
0x1400048f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048f5  nop
0x1400048f6  xor     eax, eax
0x1400048f8  jmp     loc_140004C7D
0x1400048fd  test    eax, eax
0x1400048ff  jz      short loc_140004968
0x140004901  mov     rcx, [rsp+138h]; this
0x140004909  mov     r9d, eax; char *
0x14000490c  mov     edx, 0D8h; void *
0x140004911  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140004916  mov     ebx, eax
0x140004918  mov     rcx, [rsp+138h+hKey]; hKey
0x14000491d  test    rcx, rcx
0x140004920  jz      short loc_140004929
0x140004922  call    cs:__imp_RegCloseKey
0x140004928  nop
0x140004929  mov     rcx, [rsp+138h+var_E0]
0x14000492e  test    rcx, rcx
0x140004931  jz      short loc_140004945
0x140004933  mov     [rsp+138h+var_E0], r15
0x140004938  mov     rax, [rcx]
0x14000493b  mov     rax, [rax+10h]
0x14000493f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004944  nop
0x140004945  mov     rcx, [rsp+138h+var_E8]
0x14000494a  test    rcx, rcx
0x14000494d  jz      short loc_140004961
0x14000494f  mov     [rsp+138h+var_E8], r15
0x140004954  mov     rax, [rcx]
0x140004957  mov     rax, [rax+10h]
0x14000495b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004960  nop
0x140004961  mov     eax, ebx
0x140004963  jmp     loc_140004C7D
0x140004968  mov     [rsp+138h+pvData], r15d
0x14000496d  mov     edi, 4
0x140004972  mov     [rsp+138h+pcbData], edi
0x140004976  lea     rax, [rsp+138h+pcbData]
0x14000497b  mov     [rsp+138h+lpSecurityAttributes], rax; pcbData
0x140004980  lea     rax, [rsp+138h+pvData]
0x140004985  mov     qword ptr [rsp+138h+samDesired], rax; pvData
0x14000498a  mov     [rsp+138h+ppv], r15; int
0x14000498f  lea     r9d, [rdi+0Ch]; dwFlags
0x140004993  lea     r8, Value; "InstallType"
0x14000499a  xor     edx, edx; lpSubKey
0x14000499c  mov     rcx, [rsp+138h+hKey]; hkey
0x1400049a1  call    cs:__imp_RegGetValueW
0x1400049a7  cmp     eax, 2
0x1400049aa  jnz     short loc_1400049FC
0x1400049ac  mov     rcx, [rsp+138h+hKey]; hKey
0x1400049b1  test    rcx, rcx
0x1400049b4  jz      short loc_1400049BD
0x1400049b6  call    cs:__imp_RegCloseKey
0x1400049bc  nop
0x1400049bd  mov     rcx, [rsp+138h+var_E0]
0x1400049c2  test    rcx, rcx
0x1400049c5  jz      short loc_1400049D9
0x1400049c7  mov     [rsp+138h+var_E0], r15
0x1400049cc  mov     rax, [rcx]
0x1400049cf  mov     rax, [rax+10h]
0x1400049d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049d8  nop
0x1400049d9  mov     rcx, [rsp+138h+var_E8]
0x1400049de  test    rcx, rcx
0x1400049e1  jz      short loc_1400049F5
0x1400049e3  mov     [rsp+138h+var_E8], r15
0x1400049e8  mov     rax, [rcx]
0x1400049eb  mov     rax, [rax+10h]
0x1400049ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049f4  nop
0x1400049f5  xor     eax, eax
0x1400049f7  jmp     loc_140004C7D
0x1400049fc  test    eax, eax
0x1400049fe  jz      short loc_140004A67
0x140004a00  mov     rcx, [rsp+138h]; this
0x140004a08  mov     r9d, eax; char *
0x140004a0b  mov     edx, 0E9h; void *
0x140004a10  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140004a15  mov     ebx, eax
0x140004a17  mov     rcx, [rsp+138h+hKey]; hKey
0x140004a1c  test    rcx, rcx
0x140004a1f  jz      short loc_140004A28
0x140004a21  call    cs:__imp_RegCloseKey
0x140004a27  nop
0x140004a28  mov     rcx, [rsp+138h+var_E0]
0x140004a2d  test    rcx, rcx
0x140004a30  jz      short loc_140004A44
0x140004a32  mov     [rsp+138h+var_E0], r15
0x140004a37  mov     rax, [rcx]
0x140004a3a  mov     rax, [rax+10h]
0x140004a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a43  nop
0x140004a44  mov     rcx, [rsp+138h+var_E8]
0x140004a49  test    rcx, rcx
0x140004a4c  jz      short loc_140004A60
0x140004a4e  mov     [rsp+138h+var_E8], r15
0x140004a53  mov     rax, [rcx]
0x140004a56  mov     rax, [rax+10h]
0x140004a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a5f  nop
0x140004a60  mov     eax, ebx
0x140004a62  jmp     loc_140004C7D
0x140004a67  mov     ecx, [rsp+138h+pvData]
0x140004a6b  lea     eax, [rcx-0Fh]
0x140004a6e  cmp     eax, 1
0x140004a71  ja      short loc_140004A79
0x140004a73  mov     dword ptr [rsi], 1
0x140004a79  cmp     ecx, 11h
0x140004a7c  jnz     loc_140004C2C
0x140004a82  xor     edx, edx; hFile
0x140004a84  mov     r8d, 800h; dwFlags
0x140004a8a  lea     rcx, LibFileName; "provmigrate.dll"
0x140004a91  call    cs:__imp_LoadLibraryExW
0x140004a97  mov     rbx, rax
0x140004a9a  mov     [rsp+138h+var_C0], rax
0x140004a9f  test    rax, rax
0x140004aa2  jnz     loc_140004B6B
0x140004aa8  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 2
0x140004aaf  jz      short loc_140004B1B
0x140004ab1  call    cs:__imp_GetLastError
0x140004ab7  test    eax, eax
0x140004ab9  jle     short loc_140004AC3
0x140004abb  movzx   eax, ax
0x140004abe  or      eax, 80070000h
  ... truncated ...
```
