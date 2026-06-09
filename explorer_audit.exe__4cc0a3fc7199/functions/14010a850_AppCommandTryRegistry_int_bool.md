# AppCommandTryRegistry(int,bool)

- ea: `0x14010a850`
- end: `0x14010ab84`
- name: `?AppCommandTryRegistry@@YAHH_N@Z`
- size: `820`
- prototype: `__int64 __fastcall(int, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14010a850`
- `0x14011e410`

## callees

- `0x14000edcc`
- `0x1400158a4`
- `0x1400a49e0`
- `0x1400b3e24`
- `0x1401040e0`
- `0x140104ce0`
- `0x14010a1c8`
- `0x14010a850`
- `0x14010aeb4`
- `0x14010b9e4`
- `0x14010bb8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010aa7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010aa8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010ab3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010ab4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010aa7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010aa8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010ab3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14010ab4a`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a8e3`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a921`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a985`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a8e3`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a921`
- `api-ms-win-shcore-registry-l1-1-1!SHRegGetValueFromHKCUHKLM` at `0x14010a985`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x14010aa60`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x14010aa60`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14010aaa4`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x14010aaa4`
- `SHELL32!ShellExecuteExW` at `0x14010ab1b`
- `SHELL32!ShellExecuteExW` at `0x14010ab1b`
- `SHLWAPI!__imp_SHRunIndirectRegClientCommand` at `0x14010a998`
- `SHLWAPI!__imp_SHRunIndirectRegClientCommand` at `0x14010a998`

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
0x14010a850  mov     [rsp-8+arg_8], rbx
0x14010a855  mov     [rsp-8+arg_10], rsi
0x14010a85a  push    rbp
0x14010a85b  push    rdi
0x14010a85c  push    r14
0x14010a85e  lea     rbp, [rsp-520h]
0x14010a866  sub     rsp, 620h
0x14010a86d  mov     rax, cs:__security_cookie
0x14010a874  xor     rax, rsp
0x14010a877  mov     [rbp+530h+var_20], rax
0x14010a87e  mov     sil, dl
0x14010a881  mov     ebx, ecx
0x14010a883  xor     r14d, r14d
0x14010a886  mov     [rsp+630h+var_5F0], r14b
0x14010a88b  mov     r9d, ecx
0x14010a88e  lea     r8, aSoftwareMicros_29; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14010a895  mov     edx, 80h; unsigned __int64
0x14010a89a  lea     rcx, [rbp+530h+pwszKey]; unsigned __int16 *
0x14010a89e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010a8a3  mov     [rsp+630h+punk], r14
0x14010a8a8  mov     [rsp+630h+var_5EC], 208h
0x14010a8b0  mov     edi, r14d
0x14010a8b3  mov     [rbp+530h+pszCmdTemplate], r14w
0x14010a8bb  lea     rax, [rsp+630h+var_5EC]
0x14010a8c0  mov     [rsp+630h+pcbData], rax; pcbData
0x14010a8c5  lea     rax, [rbp+530h+pszCmdTemplate]
0x14010a8cc  mov     [rsp+630h+pvData], rax; pvData
0x14010a8d1  xor     r9d, r9d; pdwType
0x14010a8d4  lea     r8d, [r14+2]; srrfFlags
0x14010a8d8  lea     rdx, pwszValue; "ShellExecute"
0x14010a8df  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x14010a8e3  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x14010a8e9  test    eax, eax
0x14010a8eb  jz      loc_14010AA06
0x14010a8f1  mov     [rsp+630h+var_5EC], 104h
0x14010a8f9  lea     rax, [rsp+630h+var_5EC]
0x14010a8fe  mov     [rsp+630h+pcbData], rax; pcbData
0x14010a903  lea     rax, [rbp+530h+var_230]
0x14010a90a  mov     [rsp+630h+pvData], rax; unsigned int
0x14010a90f  xor     r9d, r9d; pdwType
0x14010a912  lea     r8d, [r14+2]; srrfFlags
0x14010a916  lea     rdx, aAssociation; "Association"
0x14010a91d  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x14010a921  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x14010a927  test    eax, eax
0x14010a929  jnz     short loc_14010A955
0x14010a92b  lea     rax, [rsp+630h+punk]
0x14010a930  mov     [rsp+630h+pcbData], rax; struct IShellItem2 **
0x14010a935  lea     r9, [rbp+530h+pszCmdTemplate]; unsigned __int16 *
0x14010a93c  lea     r8, [rsp+630h+var_5F0]; bool *
0x14010a941  mov     dl, sil; bool
0x14010a944  lea     rcx, [rbp+530h+var_230]; unsigned __int16 *
0x14010a94b  call    ?HandleAssociationAppCommand@@YAXPEBG_NPEA_NPEAGKPEAPEAUIShellItem2@@@Z; HandleAssociationAppCommand(ushort const *,bool,bool *,ushort *,ulong,IShellItem2 * *)
0x14010a950  jmp     loc_14010A9DB
0x14010a955  mov     [rsp+630h+var_5EC], 104h
0x14010a95d  lea     rax, [rsp+630h+var_5EC]
0x14010a962  mov     [rsp+630h+pcbData], rax; pcbData
0x14010a967  lea     rax, [rbp+530h+var_230]
0x14010a96e  mov     [rsp+630h+pvData], rax; unsigned __int64
0x14010a973  xor     r9d, r9d; pdwType
0x14010a976  lea     r8d, [r9+2]; srrfFlags
0x14010a97a  lea     rdx, aRegisteredapp; "RegisteredApp"
0x14010a981  lea     rcx, [rbp+530h+pwszKey]; pwszKey
0x14010a985  call    cs:__imp_SHRegGetValueFromHKCUHKLM
0x14010a98b  test    eax, eax
0x14010a98d  jnz     short loc_14010A9AF
0x14010a98f  lea     rdx, [rbp+530h+var_230]
0x14010a996  xor     ecx, ecx
0x14010a998  call    cs:__imp_SHRunIndirectRegClientCommand
0x14010a99e  mov     eax, r14d
0x14010a9a1  mov     [rbp+530h+pszCmdTemplate], ax
0x14010a9a8  mov     edi, 1
0x14010a9ad  jmp     short loc_14010AA0D
0x14010a9af  lea     rax, [rsp+630h+punk]
0x14010a9b4  mov     [rsp+630h+var_5F8], rax; struct IShellItem2 **
0x14010a9b9  lea     rax, [rbp+530h+pszCmdTemplate]
0x14010a9c0  mov     [rsp+630h+pcbData], rax; unsigned __int16 *
0x14010a9c5  lea     r9, [rbp+530h+var_230]; unsigned __int16 *
0x14010a9cc  lea     r8, [rsp+630h+var_5F0]; bool *
0x14010a9d1  mov     dl, sil; bool
0x14010a9d4  mov     ecx, ebx; int
0x14010a9d6  call    ?TryFallbackAppKeyCommands@@YAXH_NPEA_NPEAG_K2KPEAPEAUIShellItem2@@@Z; TryFallbackAppKeyCommands(int,bool,bool *,ushort *,unsigned __int64,ushort *,ulong,IShellItem2 * *)
0x14010a9db  cmp     [rsp+630h+var_5F0], r14b
0x14010a9e0  jz      short loc_14010AA06
0x14010a9e2  lea     rcx, [rbp+530h+var_230]; unsigned __int16 *
0x14010a9e9  call    ?ShowOpenWithDialog@@YAJPEBG@Z; ShowOpenWithDialog(ushort const *)
0x14010a9ee  test    eax, eax
0x14010a9f0  js      loc_14010AB51
0x14010a9f6  mov     dl, 1; bool
0x14010a9f8  mov     ecx, ebx; int
0x14010a9fa  call    ?AppCommandTryRegistry@@YAHH_N@Z; AppCommandTryRegistry(int,bool)
0x14010a9ff  mov     edi, eax
0x14010aa01  jmp     loc_14010AB51
0x14010aa06  movzx   eax, [rbp+530h+pszCmdTemplate]
0x14010aa0d  mov     rbx, [rsp+630h+punk]
0x14010aa12  test    rbx, rbx
0x14010aa15  jnz     short loc_14010AA20
0x14010aa17  test    ax, ax
0x14010aa1a  jz      loc_14010AB51
0x14010aa20  mov     [rsp+630h+pv], r14
0x14010aa25  mov     [rsp+630h+ppszParameters], r14
0x14010aa2a  mov     [rsp+630h+ppidl], r14
0x14010aa2f  mov     [rbp+530h+pExecInfo.cbSize], 70h ; 'p'
0x14010aa36  xor     edx, edx; Val
0x14010aa38  lea     r8d, [rdx+6Ch]; Size
0x14010aa3c  lea     rcx, [rbp+530h+pExecInfo.fMask]; void *
0x14010aa40  call    memset_0
0x14010aa45  mov     [rbp+530h+pExecInfo.nShow], 1
0x14010aa4c  mov     [rbp+530h+pExecInfo.fMask], 400h
0x14010aa53  test    rbx, rbx
0x14010aa56  jz      short loc_14010AA7D
0x14010aa58  lea     rdx, [rsp+630h+ppidl]; ppidl
0x14010aa5d  mov     rcx, rbx; punk
0x14010aa60  call    cs:__imp_SHGetIDListFromObject
0x14010aa66  test    eax, eax
0x14010aa68  js      loc_14010AB30
0x14010aa6e  or      [rbp+530h+pExecInfo.fMask], 0Ch
0x14010aa72  mov     rax, [rsp+630h+ppidl]
0x14010aa77  mov     [rbp+530h+pExecInfo.lpIDList], rax
0x14010aa7b  jmp     short loc_14010AAD1
0x14010aa7d  xor     ecx, ecx; pv
0x14010aa7f  call    cs:__imp_CoTaskMemFree
0x14010aa85  mov     rcx, [rsp+630h+pv]; pv
0x14010aa8a  call    cs:__imp_CoTaskMemFree
0x14010aa90  lea     r9, [rsp+630h+ppszParameters]; ppszParameters
0x14010aa95  xor     r8d, r8d; ppszCommandLine
0x14010aa98  lea     rdx, [rsp+630h+pv]; ppszApplication
0x14010aa9d  lea     rcx, [rbp+530h+pszCmdTemplate]; pszCmdTemplate
0x14010aaa4  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x14010aaaa  test    eax, eax
0x14010aaac  jns     short loc_14010AABF
0x14010aaae  lea     rax, [rbp+530h+pszCmdTemplate]
0x14010aab5  mov     [rbp+530h+pExecInfo.lpFile], rax
0x14010aab9  mov     [rbp+530h+pExecInfo.lpParameters], r14
0x14010aabd  jmp     short loc_14010AAD1
0x14010aabf  mov     rax, [rsp+630h+pv]
0x14010aac4  mov     [rbp+530h+pExecInfo.lpFile], rax
0x14010aac8  mov     rax, [rsp+630h+ppszParameters]
0x14010aacd  mov     [rbp+530h+pExecInfo.lpParameters], rax
0x14010aad1  mov     [rsp+630h+var_5E8], r14
0x14010aad6  mov     [rsp+630h+var_5D0], 2
0x14010aade  lea     rcx, [rsp+630h+var_5E8]
0x14010aae3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14010aae8  lea     rdx, [rsp+630h+var_5D0]
0x14010aaed  lea     rcx, [rsp+630h+var_5E8]
0x14010aaf2  call    ??$MakeAndInitialize@VCLauncherUIMode@@V1@W4EC_HOST_UI_MODE@@@Details@WRL@Microsoft@@YAJPEAPEAVCLauncherUIMode@@$$QEAW4EC_HOST_UI_MODE@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,EC_HOST_UI_MODE>(CLauncherUIMode * *,EC_HOST_UI_MODE &&)
0x14010aaf7  test    eax, eax
0x14010aaf9  js      short loc_14010AB21
0x14010aafb  bts     [rbp+530h+pExecInfo.fMask], 1Bh
0x14010ab00  mov     rax, [rsp+630h+var_5E8]
0x14010ab05  test    rax, rax
0x14010ab08  jz      short loc_14010AB10
0x14010ab0a  add     rax, 28h ; '('
0x14010ab0e  jmp     short loc_14010AB13
0x14010ab10  mov     rax, r14
0x14010ab13  mov     [rbp+530h+pExecInfo.hInstApp], rax
0x14010ab17  lea     rcx, [rbp+530h+pExecInfo]; pExecInfo
0x14010ab1b  call    cs:__imp_ShellExecuteExW
0x14010ab21  mov     edi, 1
0x14010ab26  lea     rcx, [rsp+630h+var_5E8]
0x14010ab2b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14010ab30  lea     rcx, [rsp+630h+ppidl]
0x14010ab35  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x14010ab3a  mov     rcx, [rsp+630h+ppszParameters]; pv
0x14010ab3f  call    cs:__imp_CoTaskMemFree
0x14010ab45  mov     rcx, [rsp+630h+pv]; pv
0x14010ab4a  call    cs:__imp_CoTaskMemFree
0x14010ab50  nop
0x14010ab51  lea     rcx, [rsp+630h+punk]
0x14010ab56  call    ??1?$com_ptr_t@UIGlobalOptions@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IGlobalOptions,wil::err_exception_policy>::~com_ptr_t<IGlobalOptions,wil::err_exception_policy>(void)
0x14010ab5b  mov     eax, edi
0x14010ab5d  mov     rcx, [rbp+530h+var_20]
0x14010ab64  xor     rcx, rsp; StackCookie
0x14010ab67  call    __security_check_cookie
0x14010ab6c  lea     r11, [rsp+630h+var_10]
0x14010ab74  mov     rbx, [r11+28h]
0x14010ab78  mov     rsi, [r11+30h]
0x14010ab7c  mov     rsp, r11
0x14010ab7f  pop     r14
0x14010ab81  pop     rdi
0x14010ab82  pop     rbp
0x14010ab83  retn
```
