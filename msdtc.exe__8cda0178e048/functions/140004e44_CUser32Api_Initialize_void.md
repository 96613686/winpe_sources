# CUser32Api::Initialize(void)

- ea: `0x140004e44`
- end: `0x14000503d`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(HMODULE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004cfc`

## callees

- `0x140004e44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004e61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140004e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004e7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004e9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004eb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005007`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004e7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004e9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004eb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004fee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005007`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005020`

## string_xrefs

- `0x140004e58`: `user32.dll`
- `0x140004f98`: `OpenWindowStationW`
- `0x140004fce`: `GetThreadDesktop`
- `0x140004fe7`: `SetThreadDesktop`
- `0x140005000`: `OpenDesktopW`

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
0x140004e44  push    rbx
0x140004e46  sub     rsp, 20h
0x140004e4a  mov     rax, [rcx]
0x140004e4d  mov     rbx, rcx
0x140004e50  test    rax, rax
0x140004e53  jnz     short loc_140004E73
0x140004e55  xor     r8d, r8d; dwFlags
0x140004e58  lea     rcx, aUser32Dll; "user32.dll"
0x140004e5f  xor     edx, edx; hFile
0x140004e61  call    cs:__imp_LoadLibraryExW
0x140004e67  mov     [rbx], rax
0x140004e6a  test    rax, rax
0x140004e6d  jz      loc_140005035
0x140004e73  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x140004e7a  mov     rcx, rax; hModule
0x140004e7d  call    cs:__imp_GetProcAddress
0x140004e83  mov     [rbx+8], rax
0x140004e87  test    rax, rax
0x140004e8a  jz      loc_140005035
0x140004e90  mov     rcx, [rbx]; hModule
0x140004e93  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x140004e9a  call    cs:__imp_GetProcAddress
0x140004ea0  mov     [rbx+10h], rax
0x140004ea4  test    rax, rax
0x140004ea7  jz      loc_140005035
0x140004ead  mov     rcx, [rbx]; hModule
0x140004eb0  lea     rdx, aEnddialog; "EndDialog"
0x140004eb7  call    cs:__imp_GetProcAddress
0x140004ebd  mov     [rbx+18h], rax
0x140004ec1  test    rax, rax
0x140004ec4  jz      loc_140005035
0x140004eca  mov     rcx, [rbx]; hModule
0x140004ecd  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x140004ed4  call    cs:__imp_GetProcAddress
0x140004eda  mov     [rbx+20h], rax
0x140004ede  test    rax, rax
0x140004ee1  jz      loc_140005035
0x140004ee7  mov     rcx, [rbx]; hModule
0x140004eea  lea     rdx, aGetwindowrect; "GetWindowRect"
0x140004ef1  call    cs:__imp_GetProcAddress
0x140004ef7  mov     [rbx+28h], rax
0x140004efb  test    rax, rax
0x140004efe  jz      loc_140005035
0x140004f04  mov     rcx, [rbx]; hModule
0x140004f07  lea     rdx, aGetclientrect; "GetClientRect"
0x140004f0e  call    cs:__imp_GetProcAddress
0x140004f14  mov     [rbx+30h], rax
0x140004f18  test    rax, rax
0x140004f1b  jz      loc_140005035
0x140004f21  mov     rcx, [rbx]; hModule
0x140004f24  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x140004f2b  call    cs:__imp_GetProcAddress
0x140004f31  mov     [rbx+38h], rax
0x140004f35  test    rax, rax
0x140004f38  jz      loc_140005035
0x140004f3e  mov     rcx, [rbx]; hModule
0x140004f41  lea     rdx, aSetwindowpos; "SetWindowPos"
0x140004f48  call    cs:__imp_GetProcAddress
0x140004f4e  mov     [rbx+40h], rax
0x140004f52  test    rax, rax
0x140004f55  jz      loc_140005035
0x140004f5b  mov     rcx, [rbx]; hModule
0x140004f5e  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x140004f65  call    cs:__imp_GetProcAddress
0x140004f6b  mov     [rbx+48h], rax
0x140004f6f  test    rax, rax
0x140004f72  jz      loc_140005035
0x140004f78  mov     rcx, [rbx]; hModule
0x140004f7b  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x140004f82  call    cs:__imp_GetProcAddress
0x140004f88  mov     [rbx+50h], rax
0x140004f8c  test    rax, rax
0x140004f8f  jz      loc_140005035
0x140004f95  mov     rcx, [rbx]; hModule
0x140004f98  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x140004f9f  call    cs:__imp_GetProcAddress
0x140004fa5  mov     [rbx+58h], rax
0x140004fa9  test    rax, rax
0x140004fac  jz      loc_140005035
0x140004fb2  mov     rcx, [rbx]; hModule
0x140004fb5  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x140004fbc  call    cs:__imp_GetProcAddress
0x140004fc2  mov     [rbx+60h], rax
0x140004fc6  test    rax, rax
0x140004fc9  jz      short loc_140005035
0x140004fcb  mov     rcx, [rbx]; hModule
0x140004fce  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x140004fd5  call    cs:__imp_GetProcAddress
0x140004fdb  mov     [rbx+68h], rax
0x140004fdf  test    rax, rax
0x140004fe2  jz      short loc_140005035
0x140004fe4  mov     rcx, [rbx]; hModule
0x140004fe7  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x140004fee  call    cs:__imp_GetProcAddress
0x140004ff4  mov     [rbx+70h], rax
0x140004ff8  test    rax, rax
0x140004ffb  jz      short loc_140005035
0x140004ffd  mov     rcx, [rbx]; hModule
0x140005000  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x140005007  call    cs:__imp_GetProcAddress
0x14000500d  mov     [rbx+78h], rax
0x140005011  test    rax, rax
0x140005014  jz      short loc_140005035
0x140005016  mov     rcx, [rbx]; hModule
0x140005019  lea     rdx, aClosedesktop; "CloseDesktop"
0x140005020  call    cs:__imp_GetProcAddress
0x140005026  test    rax, rax
0x140005029  mov     [rbx+80h], rax
0x140005030  setnz   al
0x140005033  jmp     short loc_140005037
0x140005035  xor     al, al
0x140005037  add     rsp, 20h
0x14000503b  pop     rbx
0x14000503c  retn
```
