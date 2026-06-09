# CUser32Api::Initialize(void)

- ea: `0x180089ca4`
- end: `0x180089e9d`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180089b60`

## callees

- `0x180089ca4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089cc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089cc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089cdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089cfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089da8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089dc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089de2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089cdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089cfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089da8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089dc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089de2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089dff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089e80`

## string_xrefs

- `0x180089cb8`: `user32.dll`
- `0x180089df8`: `OpenWindowStationW`
- `0x180089e47`: `SetThreadDesktop`
- `0x180089e2e`: `GetThreadDesktop`
- `0x180089e60`: `OpenDesktopW`

## pseudocode

```c
bool __fastcall CUser32Api::Initialize(HMODULE *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax

  Library = *this;
  if ( !*this )
  {
    Library = LoadLibraryExW(L"user32.dll", 0, 0);
    *this = Library;
    if ( !Library )
      return 0;
  }
  ProcAddress = GetProcAddress(Library, "DialogBoxParamW");
  this[1] = (HMODULE)ProcAddress;
  if ( !ProcAddress )
    return 0;
  v4 = GetProcAddress(*this, "SetDlgItemTextW");
  this[2] = (HMODULE)v4;
  if ( !v4 )
    return 0;
  v5 = GetProcAddress(*this, "EndDialog");
  this[3] = (HMODULE)v5;
  if ( !v5 )
    return 0;
  v6 = GetProcAddress(*this, "GetDesktopWindow");
  this[4] = (HMODULE)v6;
  if ( !v6 )
    return 0;
  v7 = GetProcAddress(*this, "GetWindowRect");
  this[5] = (HMODULE)v7;
  if ( !v7 )
    return 0;
  v8 = GetProcAddress(*this, "GetClientRect");
  this[6] = (HMODULE)v8;
  if ( !v8 )
    return 0;
  v9 = GetProcAddress(*this, "MapWindowPoints");
  this[7] = (HMODULE)v9;
  if ( !v9 )
    return 0;
  v10 = GetProcAddress(*this, "SetWindowPos");
  this[8] = (HMODULE)v10;
  if ( !v10 )
    return 0;
  v11 = GetProcAddress(*this, "GetProcessWindowStation");
  this[9] = (HMODULE)v11;
  if ( !v11 )
    return 0;
  v12 = GetProcAddress(*this, "SetProcessWindowStation");
  this[10] = (HMODULE)v12;
  if ( !v12 )
    return 0;
  v13 = GetProcAddress(*this, "OpenWindowStationW");
  this[11] = (HMODULE)v13;
  if ( !v13 )
    return 0;
  v14 = GetProcAddress(*this, "CloseWindowStation");
  this[12] = (HMODULE)v14;
  if ( !v14 )
    return 0;
  v15 = GetProcAddress(*this, "GetThreadDesktop");
  this[13] = (HMODULE)v15;
  if ( !v15 )
    return 0;
  v16 = GetProcAddress(*this, "SetThreadDesktop");
  this[14] = (HMODULE)v16;
  if ( !v16 )
    return 0;
  v17 = GetProcAddress(*this, "OpenDesktopW");
  this[15] = (HMODULE)v17;
  if ( !v17 )
    return 0;
  v18 = GetProcAddress(*this, "CloseDesktop");
  this[16] = (HMODULE)v18;
  return v18 != 0;
}

```

## disassembly

```asm
0x180089ca4  push    rbx
0x180089ca6  sub     rsp, 20h
0x180089caa  mov     rax, [rcx]
0x180089cad  mov     rbx, rcx
0x180089cb0  test    rax, rax
0x180089cb3  jnz     short loc_180089CD3
0x180089cb5  xor     r8d, r8d; dwFlags
0x180089cb8  lea     rcx, aUser32Dll_0; "user32.dll"
0x180089cbf  xor     edx, edx; hFile
0x180089cc1  call    cs:__imp_LoadLibraryExW
0x180089cc7  mov     [rbx], rax
0x180089cca  test    rax, rax
0x180089ccd  jz      loc_180089E95
0x180089cd3  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x180089cda  mov     rcx, rax; hModule
0x180089cdd  call    cs:__imp_GetProcAddress
0x180089ce3  mov     [rbx+8], rax
0x180089ce7  test    rax, rax
0x180089cea  jz      loc_180089E95
0x180089cf0  mov     rcx, [rbx]; hModule
0x180089cf3  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x180089cfa  call    cs:__imp_GetProcAddress
0x180089d00  mov     [rbx+10h], rax
0x180089d04  test    rax, rax
0x180089d07  jz      loc_180089E95
0x180089d0d  mov     rcx, [rbx]; hModule
0x180089d10  lea     rdx, aEnddialog; "EndDialog"
0x180089d17  call    cs:__imp_GetProcAddress
0x180089d1d  mov     [rbx+18h], rax
0x180089d21  test    rax, rax
0x180089d24  jz      loc_180089E95
0x180089d2a  mov     rcx, [rbx]; hModule
0x180089d2d  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x180089d34  call    cs:__imp_GetProcAddress
0x180089d3a  mov     [rbx+20h], rax
0x180089d3e  test    rax, rax
0x180089d41  jz      loc_180089E95
0x180089d47  mov     rcx, [rbx]; hModule
0x180089d4a  lea     rdx, aGetwindowrect; "GetWindowRect"
0x180089d51  call    cs:__imp_GetProcAddress
0x180089d57  mov     [rbx+28h], rax
0x180089d5b  test    rax, rax
0x180089d5e  jz      loc_180089E95
0x180089d64  mov     rcx, [rbx]; hModule
0x180089d67  lea     rdx, aGetclientrect; "GetClientRect"
0x180089d6e  call    cs:__imp_GetProcAddress
0x180089d74  mov     [rbx+30h], rax
0x180089d78  test    rax, rax
0x180089d7b  jz      loc_180089E95
0x180089d81  mov     rcx, [rbx]; hModule
0x180089d84  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x180089d8b  call    cs:__imp_GetProcAddress
0x180089d91  mov     [rbx+38h], rax
0x180089d95  test    rax, rax
0x180089d98  jz      loc_180089E95
0x180089d9e  mov     rcx, [rbx]; hModule
0x180089da1  lea     rdx, aSetwindowpos; "SetWindowPos"
0x180089da8  call    cs:__imp_GetProcAddress
0x180089dae  mov     [rbx+40h], rax
0x180089db2  test    rax, rax
0x180089db5  jz      loc_180089E95
0x180089dbb  mov     rcx, [rbx]; hModule
0x180089dbe  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180089dc5  call    cs:__imp_GetProcAddress
0x180089dcb  mov     [rbx+48h], rax
0x180089dcf  test    rax, rax
0x180089dd2  jz      loc_180089E95
0x180089dd8  mov     rcx, [rbx]; hModule
0x180089ddb  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x180089de2  call    cs:__imp_GetProcAddress
0x180089de8  mov     [rbx+50h], rax
0x180089dec  test    rax, rax
0x180089def  jz      loc_180089E95
0x180089df5  mov     rcx, [rbx]; hModule
0x180089df8  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x180089dff  call    cs:__imp_GetProcAddress
0x180089e05  mov     [rbx+58h], rax
0x180089e09  test    rax, rax
0x180089e0c  jz      loc_180089E95
0x180089e12  mov     rcx, [rbx]; hModule
0x180089e15  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x180089e1c  call    cs:__imp_GetProcAddress
0x180089e22  mov     [rbx+60h], rax
0x180089e26  test    rax, rax
0x180089e29  jz      short loc_180089E95
0x180089e2b  mov     rcx, [rbx]; hModule
0x180089e2e  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x180089e35  call    cs:__imp_GetProcAddress
0x180089e3b  mov     [rbx+68h], rax
0x180089e3f  test    rax, rax
0x180089e42  jz      short loc_180089E95
0x180089e44  mov     rcx, [rbx]; hModule
0x180089e47  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x180089e4e  call    cs:__imp_GetProcAddress
0x180089e54  mov     [rbx+70h], rax
0x180089e58  test    rax, rax
0x180089e5b  jz      short loc_180089E95
0x180089e5d  mov     rcx, [rbx]; hModule
0x180089e60  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x180089e67  call    cs:__imp_GetProcAddress
0x180089e6d  mov     [rbx+78h], rax
0x180089e71  test    rax, rax
0x180089e74  jz      short loc_180089E95
0x180089e76  mov     rcx, [rbx]; hModule
0x180089e79  lea     rdx, aClosedesktop; "CloseDesktop"
0x180089e80  call    cs:__imp_GetProcAddress
0x180089e86  test    rax, rax
0x180089e89  mov     [rbx+80h], rax
0x180089e90  setnz   al
0x180089e93  jmp     short loc_180089E97
0x180089e95  xor     al, al
0x180089e97  add     rsp, 20h
0x180089e9b  pop     rbx
0x180089e9c  retn
```
