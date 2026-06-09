# CanShareSMB(IShellItem *)

- ea: `0x18001d370`
- end: `0x18001d486`
- name: `?CanShareSMB@@YAJPEAUIShellItem@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(struct IShellItem *)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b180`
- `0x180034560`
- `0x180054620`
- `0x18005e960`

## callees

- `0x180012340`
- `0x18001d370`
- `0x1800254e0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d450`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001d431`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001d431`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001d3a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001d3a5`
- `SHCORE!__imp_PathBuildRootW` at `0x18001d426`
- `SHCORE!__imp_PathBuildRootW` at `0x18001d426`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001d415`
- `SHLWAPI!PathGetDriveNumberW` at `0x18001d415`

## pseudocode

```c
__int64 __fastcall CanShareSMB(struct IShellItem *a1)
{
  int LocalPathForItemIfPossible; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  int v4; // edi
  int DriveNumberW; // eax
  UINT v6; // eax
  UINT v7; // eax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR pszPath; // [rsp+28h] [rbp-20h] BYREF
  WCHAR pszRoot; // [rsp+30h] [rbp-18h] BYREF

  InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
  if ( !a1 || !g_fSharingEnabled )
    return 1;
  pszPath = 0;
  LocalPathForItemIfPossible = GetLocalPathForItemIfPossible(a1, (LPWSTR *)&pszPath);
  if ( LocalPathForItemIfPossible >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v4 = 0;
    v9 = 0;
    LocalPathForItemIfPossible = ((__int64 (__fastcall *)(struct IShellItem *, __int64, int *))lpVtbl->GetAttributes)(
                                   a1,
                                   1614807040,
                                   &v9);
    if ( LocalPathForItemIfPossible >= 0 && v9 == 1610612736 )
    {
      DriveNumberW = PathGetDriveNumberW(pszPath);
      if ( DriveNumberW >= 0 )
      {
        PathBuildRootW(&pszRoot, DriveNumberW);
        v6 = GetDriveTypeW(&pszRoot) - 2;
        if ( !v6 || (v7 = v6 - 1) == 0 || v7 == 2 )
          v4 = 1;
      }
    }
    CoTaskMemFree((LPVOID)pszPath);
    if ( LocalPathForItemIfPossible >= 0 )
      return !v4;
  }
  return (unsigned int)LocalPathForItemIfPossible;
}

```

## disassembly

```asm
0x18001d370  mov     [rsp+arg_8], rbx
0x18001d375  mov     [rsp+arg_10], rsi
0x18001d37a  push    rdi
0x18001d37b  sub     rsp, 40h
0x18001d37f  mov     rax, cs:__security_cookie
0x18001d386  xor     rax, rsp
0x18001d389  mov     [rsp+48h+var_10], rax
0x18001d38e  mov     rsi, rcx
0x18001d391  lea     rdx, _OneTimeInit; InitFn
0x18001d398  lea     rcx, InitOnce; InitOnce
0x18001d39f  xor     r9d, r9d; Context
0x18001d3a2  xor     r8d, r8d; Parameter
0x18001d3a5  call    cs:__imp_InitOnceExecuteOnce
0x18001d3ab  test    rsi, rsi
0x18001d3ae  jz      loc_18001D462
0x18001d3b4  cmp     cs:?g_fSharingEnabled@@3HA, 0; int g_fSharingEnabled
0x18001d3bb  jz      loc_18001D462
0x18001d3c1  lea     rdx, [rsp+48h+pszPath]
0x18001d3c6  mov     [rsp+48h+pszPath], 0
0x18001d3cf  mov     rcx, rsi
0x18001d3d2  call    GetLocalPathForItemIfPossible
0x18001d3d7  mov     ebx, eax
0x18001d3d9  test    eax, eax
0x18001d3db  js      loc_18001D467
0x18001d3e1  mov     rax, [rsi]
0x18001d3e4  lea     r8, [rsp+48h+var_28]
0x18001d3e9  xor     edi, edi
0x18001d3eb  mov     edx, 60400000h
0x18001d3f0  mov     rcx, rsi
0x18001d3f3  mov     [rsp+48h+var_28], edi
0x18001d3f7  mov     rax, [rax+30h]
0x18001d3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d400  mov     ebx, eax
0x18001d402  test    eax, eax
0x18001d404  js      short loc_18001D44B
0x18001d406  cmp     [rsp+48h+var_28], 60000000h
0x18001d40e  jnz     short loc_18001D44B
0x18001d410  mov     rcx, [rsp+48h+pszPath]; pszPath
0x18001d415  call    cs:__imp_PathGetDriveNumberW
0x18001d41b  test    eax, eax
0x18001d41d  js      short loc_18001D44B
0x18001d41f  mov     edx, eax; iDrive
0x18001d421  lea     rcx, [rsp+48h+pszRoot]; pszRoot
0x18001d426  call    cs:__imp_PathBuildRootW
0x18001d42c  lea     rcx, [rsp+48h+pszRoot]; lpRootPathName
0x18001d431  call    cs:__imp_GetDriveTypeW
0x18001d437  sub     eax, 2
0x18001d43a  jz      short loc_18001D446
0x18001d43c  sub     eax, 1
0x18001d43f  jz      short loc_18001D446
0x18001d441  cmp     eax, 2
0x18001d444  jnz     short loc_18001D44B
0x18001d446  mov     edi, 1
0x18001d44b  mov     rcx, [rsp+48h+pszPath]; pv
0x18001d450  call    cs:__imp_CoTaskMemFree
0x18001d456  test    ebx, ebx
0x18001d458  js      short loc_18001D467
0x18001d45a  test    edi, edi
0x18001d45c  jz      short loc_18001D462
0x18001d45e  xor     ebx, ebx
0x18001d460  jmp     short loc_18001D467
0x18001d462  mov     ebx, 1
0x18001d467  mov     eax, ebx
0x18001d469  mov     rcx, [rsp+48h+var_10]
0x18001d46e  xor     rcx, rsp; StackCookie
0x18001d471  call    __security_check_cookie
0x18001d476  mov     rbx, [rsp+48h+arg_8]
0x18001d47b  mov     rsi, [rsp+48h+arg_10]
0x18001d480  add     rsp, 40h
0x18001d484  pop     rdi
0x18001d485  retn
```
