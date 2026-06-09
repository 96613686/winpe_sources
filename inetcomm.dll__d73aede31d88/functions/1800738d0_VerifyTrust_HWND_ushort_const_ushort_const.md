# VerifyTrust(HWND__ *,ushort const *,ushort const *)

- ea: `0x1800738d0`
- end: `0x180073a1c`
- name: `?VerifyTrust@@YAJPEAUHWND__@@PEBG1@Z`
- size: `332`
- prototype: `__int64 __fastcall(HWND hwnd, LPCWSTR pszPath, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18007f2c0`

## callees

- `0x1800738d0`
- `0x1800cca00`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18007392b`
- `SHLWAPI!PathFindExtensionW` at `0x18007392b`
- `SHLWAPI!StrCmpIW` at `0x18007393b`
- `SHLWAPI!StrCmpIW` at `0x18007393b`
- `KERNEL32!CloseHandle` at `0x1800739ed`
- `KERNEL32!CloseHandle` at `0x1800739ed`
- `KERNEL32!CreateFileW` at `0x18007396d`
- `KERNEL32!CreateFileW` at `0x18007396d`
- `WINTRUST!WinVerifyTrust` at `0x1800739e2`
- `WINTRUST!WinVerifyTrust` at `0x1800739e2`

## pseudocode

```c
__int64 __fastcall VerifyTrust(HWND hwnd, LPCWSTR pszPath, LPCWSTR lpFileName)
{
  const WCHAR *ExtensionW; // rax
  HANDLE FileW; // rsi
  unsigned int v9; // ebx
  _QWORD v10[2]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD pWVTData[3]; // [rsp+50h] [rbp-9h] BYREF
  _DWORD v12[4]; // [rsp+68h] [rbp+Fh] BYREF
  GUID pgActionID; // [rsp+78h] [rbp+1Fh] BYREF

  if ( !pszPath )
    return 0;
  if ( !*pszPath )
    return 0;
  if ( !lpFileName )
    return 0;
  if ( !*lpFileName )
    return 0;
  ExtensionW = PathFindExtensionW(pszPath);
  if ( StrCmpIW(ExtensionW, L".exe") )
    return 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 2147942406LL;
  pgActionID.Data1 = 1689899392;
  pWVTData[1] = v12;
  *(_DWORD *)&pgActionID.Data2 = 298814882;
  pWVTData[2] = v10;
  *(_DWORD *)pgActionID.Data4 = -1442826617;
  *(_DWORD *)&pgActionID.Data4[4] = -343563264;
  v12[0] = 1137287648;
  v12[1] = 298814880;
  v12[2] = -1442826617;
  v12[3] = -343563264;
  v10[0] = FileW;
  v10[1] = pszPath;
  pWVTData[0] = 0;
  v9 = WinVerifyTrust(hwnd, &pgActionID, pWVTData);
  CloseHandle(FileW);
  return v9;
}

```

## disassembly

```asm
0x1800738d0  mov     [rsp-8+arg_18], rbx
0x1800738d5  push    rbp
0x1800738d6  push    rsi
0x1800738d7  push    rdi
0x1800738d8  push    r14
0x1800738da  push    r15
0x1800738dc  lea     rbp, [rsp-37h]
0x1800738e1  sub     rsp, 90h
0x1800738e8  mov     rax, cs:__security_cookie
0x1800738ef  xor     rax, rsp
0x1800738f2  mov     [rbp+57h+var_28], rax
0x1800738f6  xor     r15d, r15d
0x1800738f9  mov     rbx, r8
0x1800738fc  mov     rdi, rdx
0x1800738ff  mov     r14, rcx
0x180073902  test    rdx, rdx
0x180073905  jz      loc_1800739F7
0x18007390b  cmp     [rdx], r15w
0x18007390f  jz      loc_1800739F7
0x180073915  test    rbx, rbx
0x180073918  jz      loc_1800739F7
0x18007391e  cmp     [r8], r15w
0x180073922  jz      loc_1800739F7
0x180073928  mov     rcx, rdx; pszPath
0x18007392b  call    cs:__imp_PathFindExtensionW
0x180073931  mov     rcx, rax; psz1
0x180073934  lea     rdx, c_szExeExt; ".exe"
0x18007393b  call    cs:__imp_StrCmpIW
0x180073941  test    eax, eax
0x180073943  jnz     loc_1800739F7
0x180073949  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x18007394e  lea     r8d, [r15+1]; dwShareMode
0x180073952  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007395a  xor     r9d, r9d; lpSecurityAttributes
0x18007395d  mov     edx, 80000000h; dwDesiredAccess
0x180073962  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007396a  mov     rcx, rbx; lpFileName
0x18007396d  call    cs:__imp_CreateFileW
0x180073973  mov     rsi, rax
0x180073976  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007397a  jnz     short loc_180073983
0x18007397c  mov     eax, 80070006h
0x180073981  jmp     short loc_1800739F9
0x180073983  lea     rax, [rbp+57h+var_48]
0x180073987  mov     [rbp+57h+pgActionID.Data1], 64B9D180h
0x18007398e  mov     [rbp+57h+var_58], rax
0x180073992  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x180073996  lea     rax, [rbp+57h+var_70]
0x18007399a  mov     dword ptr [rbp+57h+pgActionID.Data2], 11CF8DA2h
0x1800739a1  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x1800739a5  mov     [rbp+57h+var_50], rax
0x1800739a9  mov     rcx, r14; hwnd
0x1800739ac  mov     dword ptr [rbp+57h+pgActionID.Data4], 0AA003687h
0x1800739b3  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EB85A400h
0x1800739ba  mov     [rbp+57h+var_48], 43C9A1E0h
0x1800739c1  mov     [rbp+57h+var_44], 11CF8DA0h
0x1800739c8  mov     [rbp+57h+var_40], 0AA003687h
0x1800739cf  mov     [rbp+57h+var_3C], 0EB85A400h
0x1800739d6  mov     [rbp+57h+var_70], rsi
0x1800739da  mov     [rbp+57h+var_68], rdi
0x1800739de  mov     [rbp+57h+pWVTData], r15
0x1800739e2  call    cs:__imp_WinVerifyTrust
0x1800739e8  mov     rcx, rsi; hObject
0x1800739eb  mov     ebx, eax
0x1800739ed  call    cs:__imp_CloseHandle
0x1800739f3  mov     eax, ebx
0x1800739f5  jmp     short loc_1800739F9
0x1800739f7  xor     eax, eax
0x1800739f9  mov     rcx, [rbp+57h+var_28]
0x1800739fd  xor     rcx, rsp; StackCookie
0x180073a00  call    __security_check_cookie
0x180073a05  mov     rbx, [rsp+0B0h+arg_18]
0x180073a0d  add     rsp, 90h
0x180073a14  pop     r15
0x180073a16  pop     r14
0x180073a18  pop     rdi
0x180073a19  pop     rsi
0x180073a1a  pop     rbp
0x180073a1b  retn
```
