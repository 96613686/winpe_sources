# AppCommandTryRegistry(int,bool)

- ea: `0x140114aa0`
- end: `0x140114e17`
- name: `?AppCommandTryRegistry@@YAHH_N@Z`
- size: `887`
- prototype: `__int64 __fastcall(int, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140114aa0`
- `0x140129670`

## callees

- `0x140012594`
- `0x140020580`
- `0x1400aad30`
- `0x1400b9d70`
- `0x14010e160`
- `0x14010ed90`
- `0x14011437c`
- `0x140114aa0`
- `0x140115164`
- `0x140115d24`
- `0x140115ed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140114dd6`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114b33`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114b77`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114be1`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114b33`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114b77`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x140114be1`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x140114cc8`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x140114cc8`
- `SHELL32!ShellExecuteExW` at `0x140114d9b`
- `SHELL32!ShellExecuteExW` at `0x140114d9b`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x140114d1e`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x140114d1e`
- `SHLWAPI!__imp_SHRunIndirectRegClientCommand` at `0x140114bfa`
- `SHLWAPI!__imp_SHRunIndirectRegClientCommand` at `0x140114bfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppCommandTryRegistry(unsigned int a1, bool a2)
{
  unsigned int v4; // edi
  WCHAR v5; // ax
  IUnknown *v6; // rbx
  HINSTANCE v7; // rax
  unsigned int pvData; // [rsp+20h] [rbp-E0h]
  void *pvDataa; // [rsp+20h] [rbp-E0h]
  unsigned int v11; // [rsp+30h] [rbp-D0h]
  bool v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *punk; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+68h] [rbp-98h] BYREF
  PWSTR ppszParameters; // [rsp+70h] [rbp-90h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pwszKey[128]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR pszCmdTemplate[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v23[264]; // [rsp+400h] [rbp+300h] BYREF

  v12[0] = 0;
  StringCchPrintfW(pwszKey, 0x80u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppKey\\%d", a1);
  punk = 0;
  pcbData = 520;
  v4 = 0;
  pszCmdTemplate[0] = 0;
  if ( !SHRegGetValueFromHKCUHKLM(pwszKey, L"ShellExecute", 2, 0, pszCmdTemplate, &pcbData) )
    goto LABEL_10;
  pcbData = 260;
  if ( SHRegGetValueFromHKCUHKLM(pwszKey, L"Association", 2, 0, v23, &pcbData) )
  {
    pcbData = 260;
    if ( !SHRegGetValueFromHKCUHKLM(pwszKey, L"RegisteredApp", 2, 0, v23, &pcbData) )
    {
      SHRunIndirectRegClientCommand(0, v23);
      v5 = 0;
      pszCmdTemplate[0] = 0;
      v4 = 1;
LABEL_11:
      v6 = punk;
      if ( !punk && !v5 )
        goto LABEL_26;
      pv = 0;
      ppszParameters = 0;
      ppidl = 0;
      pExecInfo.cbSize = 112;
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.nShow = 1;
      pExecInfo.fMask = 1024;
      if ( v6 )
      {
        if ( SHGetIDListFromObject(v6, &ppidl) < 0 )
        {
LABEL_25:
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppidl);
          CoTaskMemFree(ppszParameters);
          CoTaskMemFree(pv);
          goto LABEL_26;
        }
        pExecInfo.fMask |= 0xCu;
        pExecInfo.lpIDList = ppidl;
      }
      else
      {
        CoTaskMemFree(0);
        CoTaskMemFree(pv);
        if ( SHEvaluateSystemCommandTemplate(pszCmdTemplate, (PWSTR *)&pv, 0, &ppszParameters) >= 0 )
        {
          pExecInfo.lpFile = (LPCWSTR)pv;
          pExecInfo.lpParameters = ppszParameters;
        }
        else
        {
          pExecInfo.lpFile = pszCmdTemplate;
          pExecInfo.lpParameters = 0;
        }
      }
      v14 = 0;
      v17 = 2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,enum EC_HOST_UI_MODE>(
                  &v14,
                  &v17) >= 0 )
      {
        pExecInfo.fMask |= 0x8000000u;
        if ( v14 )
          v7 = (HINSTANCE)(v14 + 40);
        else
          v7 = 0;
        pExecInfo.hInstApp = v7;
        ShellExecuteExW(&pExecInfo);
      }
      v4 = 1;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      goto LABEL_25;
    }
    TryFallbackAppKeyCommands(
      a1,
      a2,
      v12,
      v23,
      (unsigned __int64)pvDataa,
      pszCmdTemplate,
      v11,
      (struct IShellItem2 **)&punk);
  }
  else
  {
    HandleAssociationAppCommand(v23, a2, v12, pszCmdTemplate, pvData, (struct IShellItem2 **)&punk);
  }
  if ( !v12[0] )
  {
LABEL_10:
    v5 = pszCmdTemplate[0];
    goto LABEL_11;
  }
  if ( (int)ShowOpenWithDialog(v23) >= 0 )
    v4 = AppCommandTryRegistry(a1, 1);
LABEL_26:
  wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(&punk);
  return v4;
}

```

## disassembly

```asm
0x140114aa0  mov     [rsp-8+arg_8], rbx
0x140114aa5  mov     [rsp-8+arg_10], rsi
0x140114aaa  push    rbp
0x140114aab  push    rdi
0x140114aac  push    r14
0x140114aae  lea     rbp, [rsp-520h]
0x140114ab6  sub     rsp, 620h
0x140114abd  mov     rax, cs:__security_cookie
0x140114ac4  xor     rax, rsp
0x140114ac7  mov     [rbp+530h+var_20], rax
0x140114ace  mov     sil, dl
0x140114ad1  mov     ebx, ecx
0x140114ad3  xor     r14d, r14d
0x140114ad6  mov     [rsp+630h+var_5F0], r14b
0x140114adb  mov     r9d, ecx
0x140114ade  lea     r8, aSoftwareMicros_29; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140114ae5  mov     edx, 80h; unsigned __int64
0x140114aea  lea     rcx, [rbp+530h+pwszKey]; unsigned __int16 *
0x140114aee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140114af3  mov     [rsp+630h+punk], r14
0x140114af8  mov     [rsp+630h+var_5EC], 208h
0x140114b00  mov     edi, r14d
0x140114b03  mov     [rbp+530h+pszCmdTemplate], r14w
0x140114b0b  lea     rax, [rsp+630h+var_5EC]
0x140114b10  mov     [rsp+630h+pcbData], rax; pcbData
0x140114b15  lea     rax, [rbp+530h+pszCmdTemplate]
0x140114b1c  mov     [rsp+630h+pvData], rax; pvData
0x140114b21  xor     r9d, r9d; pdwType
0x140114b24  lea     r8d, [r14+2]; srrfFlags
0x140114b28  lea     rdx, pwszValue; "ShellExecute"
0x140114b2f  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x140114b33  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x140114b3a  nop     dword ptr [rax+rax+00h]
0x140114b3f  test    eax, eax
0x140114b41  jz      loc_140114C6E
0x140114b47  mov     [rsp+630h+var_5EC], 104h
0x140114b4f  lea     rax, [rsp+630h+var_5EC]
0x140114b54  mov     [rsp+630h+pcbData], rax; pcbData
0x140114b59  lea     rax, [rbp+530h+var_230]
0x140114b60  mov     [rsp+630h+pvData], rax; unsigned int
0x140114b65  xor     r9d, r9d; pdwType
0x140114b68  lea     r8d, [r14+2]; srrfFlags
0x140114b6c  lea     rdx, aAssociation; "Association"
0x140114b73  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x140114b77  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x140114b7e  nop     dword ptr [rax+rax+00h]
0x140114b83  test    eax, eax
0x140114b85  jnz     short loc_140114BB1
0x140114b87  lea     rax, [rsp+630h+punk]
0x140114b8c  mov     [rsp+630h+pcbData], rax; struct IShellItem2 **
0x140114b91  lea     r9, [rbp+530h+pszCmdTemplate]; unsigned __int16 *
0x140114b98  lea     r8, [rsp+630h+var_5F0]; bool *
0x140114b9d  mov     dl, sil; bool
0x140114ba0  lea     rcx, [rbp+530h+var_230]; unsigned __int16 *
0x140114ba7  call    ?HandleAssociationAppCommand@@YAXPEBG_NPEA_NPEAGKPEAPEAUIShellItem2@@@Z; HandleAssociationAppCommand(ushort const *,bool,bool *,ushort *,ulong,IShellItem2 * *)
0x140114bac  jmp     loc_140114C43
0x140114bb1  mov     [rsp+630h+var_5EC], 104h
0x140114bb9  lea     rax, [rsp+630h+var_5EC]
0x140114bbe  mov     [rsp+630h+pcbData], rax; pcbData
0x140114bc3  lea     rax, [rbp+530h+var_230]
0x140114bca  mov     [rsp+630h+pvData], rax; unsigned __int64
0x140114bcf  xor     r9d, r9d; pdwType
0x140114bd2  lea     r8d, [r9+2]; srrfFlags
0x140114bd6  lea     rdx, aRegisteredapp; "RegisteredApp"
0x140114bdd  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x140114be1  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x140114be8  nop     dword ptr [rax+rax+00h]
0x140114bed  test    eax, eax
0x140114bef  jnz     short loc_140114C17
0x140114bf1  lea     rdx, [rbp+530h+var_230]
0x140114bf8  xor     ecx, ecx
0x140114bfa  call    cs:__imp_SHRunIndirectRegClientCommand
0x140114c01  nop     dword ptr [rax+rax+00h]
0x140114c06  mov     eax, r14d
0x140114c09  mov     [rbp+530h+pszCmdTemplate], ax
0x140114c10  mov     edi, 1
0x140114c15  jmp     short loc_140114C75
0x140114c17  lea     rax, [rsp+630h+punk]
0x140114c1c  mov     [rsp+630h+var_5F8], rax; struct IShellItem2 **
0x140114c21  lea     rax, [rbp+530h+pszCmdTemplate]
0x140114c28  mov     [rsp+630h+pcbData], rax; unsigned __int16 *
0x140114c2d  lea     r9, [rbp+530h+var_230]; unsigned __int16 *
0x140114c34  lea     r8, [rsp+630h+var_5F0]; bool *
0x140114c39  mov     dl, sil; bool
0x140114c3c  mov     ecx, ebx; int
0x140114c3e  call    ?TryFallbackAppKeyCommands@@YAXH_NPEA_NPEAG_K2KPEAPEAUIShellItem2@@@Z; TryFallbackAppKeyCommands(int,bool,bool *,ushort *,unsigned __int64,ushort *,ulong,IShellItem2 * *)
0x140114c43  cmp     [rsp+630h+var_5F0], r14b
0x140114c48  jz      short loc_140114C6E
0x140114c4a  lea     rcx, [rbp+530h+var_230]; unsigned __int16 *
0x140114c51  call    ?ShowOpenWithDialog@@YAJPEBG@Z; ShowOpenWithDialog(ushort const *)
0x140114c56  test    eax, eax
0x140114c58  js      loc_140114DE3
0x140114c5e  mov     dl, 1; bool
0x140114c60  mov     ecx, ebx; int
0x140114c62  call    ?AppCommandTryRegistry@@YAHH_N@Z; AppCommandTryRegistry(int,bool)
0x140114c67  mov     edi, eax
0x140114c69  jmp     loc_140114DE3
0x140114c6e  movzx   eax, [rbp+530h+pszCmdTemplate]
0x140114c75  mov     rbx, [rsp+630h+punk]
0x140114c7a  test    rbx, rbx
0x140114c7d  jnz     short loc_140114C88
0x140114c7f  test    ax, ax
0x140114c82  jz      loc_140114DE3
0x140114c88  mov     [rsp+630h+pv], r14
0x140114c8d  mov     [rsp+630h+ppszParameters], r14
0x140114c92  mov     [rsp+630h+ppidl], r14
0x140114c97  mov     [rbp+530h+pExecInfo.cbSize], 70h ; 'p'
0x140114c9e  xor     edx, edx; Val
0x140114ca0  lea     r8d, [rdx+6Ch]; Size
0x140114ca4  lea     rcx, [rbp+530h+pExecInfo.fMask]; void *
0x140114ca8  call    memset_0
0x140114cad  mov     [rbp+530h+pExecInfo.nShow], 1
0x140114cb4  mov     [rbp+530h+pExecInfo.fMask], 400h
0x140114cbb  test    rbx, rbx
0x140114cbe  jz      short loc_140114CEB
0x140114cc0  lea     rdx, [rsp+630h+ppidl]; ppidl
0x140114cc5  mov     rcx, rbx; punk
0x140114cc8  call    cs:__imp_SHGetIDListFromObject
0x140114ccf  nop     dword ptr [rax+rax+00h]
0x140114cd4  test    eax, eax
0x140114cd6  js      loc_140114DB6
0x140114cdc  or      [rbp+530h+pExecInfo.fMask], 0Ch
0x140114ce0  mov     rax, [rsp+630h+ppidl]
0x140114ce5  mov     [rbp+530h+pExecInfo.lpIDList], rax
0x140114ce9  jmp     short loc_140114D51
0x140114ceb  xor     ecx, ecx; pv
0x140114ced  call    cs:__imp_CoTaskMemFree
0x140114cf4  nop     dword ptr [rax+rax+00h]
0x140114cf9  mov     rcx, [rsp+630h+pv]; pv
0x140114cfe  call    cs:__imp_CoTaskMemFree
0x140114d05  nop     dword ptr [rax+rax+00h]
0x140114d0a  lea     r9, [rsp+630h+ppszParameters]; ppszParameters
0x140114d0f  xor     r8d, r8d; ppszCommandLine
0x140114d12  lea     rdx, [rsp+630h+pv]; ppszApplication
0x140114d17  lea     rcx, [rbp+530h+pszCmdTemplate]; pszCmdTemplate
0x140114d1e  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x140114d25  nop     dword ptr [rax+rax+00h]
0x140114d2a  test    eax, eax
0x140114d2c  jns     short loc_140114D3F
0x140114d2e  lea     rax, [rbp+530h+pszCmdTemplate]
0x140114d35  mov     [rbp+530h+pExecInfo.lpFile], rax
0x140114d39  mov     [rbp+530h+pExecInfo.lpParameters], r14
0x140114d3d  jmp     short loc_140114D51
0x140114d3f  mov     rax, [rsp+630h+pv]
0x140114d44  mov     [rbp+530h+pExecInfo.lpFile], rax
0x140114d48  mov     rax, [rsp+630h+ppszParameters]
0x140114d4d  mov     [rbp+530h+pExecInfo.lpParameters], rax
0x140114d51  mov     [rsp+630h+var_5E8], r14
0x140114d56  mov     [rsp+630h+var_5D0], 2
0x140114d5e  lea     rcx, [rsp+630h+var_5E8]
0x140114d63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x140114d68  lea     rdx, [rsp+630h+var_5D0]
0x140114d6d  lea     rcx, [rsp+630h+var_5E8]
0x140114d72  call    ??$MakeAndInitialize@VCLauncherUIMode@@V1@W4EC_HOST_UI_MODE@@@Details@WRL@Microsoft@@YAJPEAPEAVCLauncherUIMode@@$$QEAW4EC_HOST_UI_MODE@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,EC_HOST_UI_MODE>(CLauncherUIMode * *,EC_HOST_UI_MODE &&)
0x140114d77  test    eax, eax
0x140114d79  js      short loc_140114DA7
0x140114d7b  bts     [rbp+530h+pExecInfo.fMask], 1Bh
0x140114d80  mov     rax, [rsp+630h+var_5E8]
0x140114d85  test    rax, rax
0x140114d88  jz      short loc_140114D90
0x140114d8a  add     rax, 28h ; '('
0x140114d8e  jmp     short loc_140114D93
0x140114d90  mov     rax, r14
0x140114d93  mov     [rbp+530h+pExecInfo.hInstApp], rax
0x140114d97  lea     rcx, [rbp+530h+pExecInfo]; pExecInfo
0x140114d9b  call    cs:__imp_ShellExecuteExW
0x140114da2  nop     dword ptr [rax+rax+00h]
0x140114da7  mov     edi, 1
0x140114dac  lea     rcx, [rsp+630h+var_5E8]
0x140114db1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x140114db6  lea     rcx, [rsp+630h+ppidl]
0x140114dbb  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x140114dc0  mov     rcx, [rsp+630h+ppszParameters]; pv
0x140114dc5  call    cs:__imp_CoTaskMemFree
0x140114dcc  nop     dword ptr [rax+rax+00h]
0x140114dd1  mov     rcx, [rsp+630h+pv]; pv
0x140114dd6  call    cs:__imp_CoTaskMemFree
0x140114ddd  nop     dword ptr [rax+rax+00h]
0x140114de2  nop
0x140114de3  lea     rcx, [rsp+630h+punk]
0x140114de8  call    ??1?$com_ptr_t@UIGlobalOptions@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(void)
0x140114ded  mov     eax, edi
0x140114def  mov     rcx, [rbp+530h+var_20]
0x140114df6  xor     rcx, rsp; StackCookie
0x140114df9  call    __security_check_cookie
0x140114dfe  lea     r11, [rsp+630h+var_10]
0x140114e06  mov     rbx, [r11+28h]
0x140114e0a  mov     rsi, [r11+30h]
0x140114e0e  mov     rsp, r11
0x140114e11  pop     r14
0x140114e13  pop     rdi
0x140114e14  pop     rbp
0x140114e15  retn
```
