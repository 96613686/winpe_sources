# CRasUiBase::LaunchVANThreadProc(void)

- ea: `0x18005d6b0`
- end: `0x18005d771`
- name: `?LaunchVANThreadProc@CRasUiBase@@KAP6AKPEAX@ZXZ`
- size: `193`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001eb7c`
- `0x18005d2bc`
- `0x18005d680`
- `0x18005d6b0`

## import_xrefs

- `SHELL32!SHCreateItemInKnownFolder` at `0x18005d6ef`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18005d6ef`
- `SHELL32!SHGetIDListFromObject` at `0x18005d709`
- `SHELL32!SHGetIDListFromObject` at `0x18005d709`
- `SHELL32!ShellExecuteExW` at `0x18005d74e`
- `SHELL32!ShellExecuteExW` at `0x18005d74e`

## pseudocode

```c
__int64 __fastcall CRasUiBase::LaunchVANThreadProc(PVOID Parameter)
{
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-19h] BYREF
  IUnknown *punk; // [rsp+B0h] [rbp+67h] BYREF
  LPITEMIDLIST ppidl; // [rsp+B8h] [rbp+6Fh] BYREF

  punk = 0;
  Microsoft::WRL::ComPtr<IShellItem>::InternalRelease(&punk);
  if ( SHCreateItemInKnownFolder(
         &FOLDERID_AppsFolder,
         0,
         L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         (void **)&punk) >= 0 )
  {
    ppidl = 0;
    if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
    {
      pExecInfo.cbSize = 112;
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.fMask = 67108876;
      pExecInfo.lpParameters = L"page=SettingsPageNetworkVPN";
      pExecInfo.lpIDList = ppidl;
      pExecInfo.nShow = 1;
      ShellExecuteExW(&pExecInfo);
    }
    CCoTaskMemPtr<_ITEMIDLIST>::~CCoTaskMemPtr<_ITEMIDLIST>((void **)&ppidl);
  }
  Microsoft::WRL::ComPtr<IShellItem>::InternalRelease(&punk);
  return 0;
}

```

## disassembly

```asm
0x18005d6b0  push    rbp
0x18005d6b2  lea     rbp, [rsp-57h]
0x18005d6b7  sub     rsp, 0A0h
0x18005d6be  lea     rcx, [rbp+57h+punk]
0x18005d6c2  mov     [rbp+57h+punk], 0
0x18005d6ca  call    ?InternalRelease@?$ComPtr@UIShellItem@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IShellItem>::InternalRelease(void)
0x18005d6cf  lea     rax, [rbp+57h+punk]
0x18005d6d3  xor     edx, edx; dwKFFlags
0x18005d6d5  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18005d6dc  mov     [rsp+0A0h+ppv], rax; ppv
0x18005d6e1  lea     r8, ?c_szPCSettingsAppID@@3QBGB; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18005d6e8  lea     rcx, FOLDERID_AppsFolder; kfid
0x18005d6ef  call    cs:__imp_SHCreateItemInKnownFolder
0x18005d6f5  test    eax, eax
0x18005d6f7  js      short loc_18005D75D
0x18005d6f9  mov     rcx, [rbp+57h+punk]; punk
0x18005d6fd  lea     rdx, [rbp+57h+ppidl]; ppidl
0x18005d701  mov     [rbp+57h+ppidl], 0
0x18005d709  call    cs:__imp_SHGetIDListFromObject
0x18005d70f  test    eax, eax
0x18005d711  js      short loc_18005D754
0x18005d713  xor     edx, edx; Val
0x18005d715  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18005d71c  lea     rcx, [rbp+57h+pExecInfo.fMask]; void *
0x18005d720  lea     r8d, [rdx+6Ch]; Size
0x18005d724  call    memset_0
0x18005d729  lea     rax, aPageSettingspa; "page=SettingsPageNetworkVPN"
0x18005d730  mov     [rbp+57h+pExecInfo.fMask], 400000Ch
0x18005d737  mov     [rbp+57h+pExecInfo.lpParameters], rax
0x18005d73b  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18005d73f  mov     rax, [rbp+57h+ppidl]
0x18005d743  mov     [rbp+57h+pExecInfo.lpIDList], rax
0x18005d747  mov     [rbp+57h+pExecInfo.nShow], 1
0x18005d74e  call    cs:__imp_ShellExecuteExW
0x18005d754  lea     rcx, [rbp+57h+ppidl]
0x18005d758  call    ??1?$CCoTaskMemPtr@U_ITEMIDLIST@@@@QEAA@XZ; CCoTaskMemPtr<_ITEMIDLIST>::~CCoTaskMemPtr<_ITEMIDLIST>(void)
0x18005d75d  lea     rcx, [rbp+57h+punk]
0x18005d761  call    ?InternalRelease@?$ComPtr@UIShellItem@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IShellItem>::InternalRelease(void)
0x18005d766  xor     eax, eax
0x18005d768  add     rsp, 0A0h
0x18005d76f  pop     rbp
0x18005d770  retn
```
