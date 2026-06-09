# CUser32Api::Initialize(void)

- ea: `0x180033378`
- end: `0x180033571`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180033234`

## callees

- `0x180033378`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033408`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033442`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003345f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003347c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033499`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033509`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033522`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003353b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033554`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800333eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033408`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033442`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003345f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003347c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033499`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033509`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033522`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003353b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033554`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033395`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033395`

## string_xrefs

- `0x18003338c`: `user32.dll`
- `0x1800334cc`: `OpenWindowStationW`
- `0x180033502`: `GetThreadDesktop`
- `0x18003351b`: `SetThreadDesktop`
- `0x180033534`: `OpenDesktopW`

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
0x180033378  push    rbx
0x18003337a  sub     rsp, 20h
0x18003337e  mov     rax, [rcx]
0x180033381  mov     rbx, rcx
0x180033384  test    rax, rax
0x180033387  jnz     short loc_1800333A7
0x180033389  xor     r8d, r8d; dwFlags
0x18003338c  lea     rcx, aUser32Dll; "user32.dll"
0x180033393  xor     edx, edx; hFile
0x180033395  call    cs:__imp_LoadLibraryExW
0x18003339b  mov     [rbx], rax
0x18003339e  test    rax, rax
0x1800333a1  jz      loc_180033569
0x1800333a7  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x1800333ae  mov     rcx, rax; hModule
0x1800333b1  call    cs:__imp_GetProcAddress
0x1800333b7  mov     [rbx+8], rax
0x1800333bb  test    rax, rax
0x1800333be  jz      loc_180033569
0x1800333c4  mov     rcx, [rbx]; hModule
0x1800333c7  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x1800333ce  call    cs:__imp_GetProcAddress
0x1800333d4  mov     [rbx+10h], rax
0x1800333d8  test    rax, rax
0x1800333db  jz      loc_180033569
0x1800333e1  mov     rcx, [rbx]; hModule
0x1800333e4  lea     rdx, aEnddialog; "EndDialog"
0x1800333eb  call    cs:__imp_GetProcAddress
0x1800333f1  mov     [rbx+18h], rax
0x1800333f5  test    rax, rax
0x1800333f8  jz      loc_180033569
0x1800333fe  mov     rcx, [rbx]; hModule
0x180033401  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x180033408  call    cs:__imp_GetProcAddress
0x18003340e  mov     [rbx+20h], rax
0x180033412  test    rax, rax
0x180033415  jz      loc_180033569
0x18003341b  mov     rcx, [rbx]; hModule
0x18003341e  lea     rdx, aGetwindowrect; "GetWindowRect"
0x180033425  call    cs:__imp_GetProcAddress
0x18003342b  mov     [rbx+28h], rax
0x18003342f  test    rax, rax
0x180033432  jz      loc_180033569
0x180033438  mov     rcx, [rbx]; hModule
0x18003343b  lea     rdx, aGetclientrect; "GetClientRect"
0x180033442  call    cs:__imp_GetProcAddress
0x180033448  mov     [rbx+30h], rax
0x18003344c  test    rax, rax
0x18003344f  jz      loc_180033569
0x180033455  mov     rcx, [rbx]; hModule
0x180033458  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x18003345f  call    cs:__imp_GetProcAddress
0x180033465  mov     [rbx+38h], rax
0x180033469  test    rax, rax
0x18003346c  jz      loc_180033569
0x180033472  mov     rcx, [rbx]; hModule
0x180033475  lea     rdx, aSetwindowpos; "SetWindowPos"
0x18003347c  call    cs:__imp_GetProcAddress
0x180033482  mov     [rbx+40h], rax
0x180033486  test    rax, rax
0x180033489  jz      loc_180033569
0x18003348f  mov     rcx, [rbx]; hModule
0x180033492  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180033499  call    cs:__imp_GetProcAddress
0x18003349f  mov     [rbx+48h], rax
0x1800334a3  test    rax, rax
0x1800334a6  jz      loc_180033569
0x1800334ac  mov     rcx, [rbx]; hModule
0x1800334af  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x1800334b6  call    cs:__imp_GetProcAddress
0x1800334bc  mov     [rbx+50h], rax
0x1800334c0  test    rax, rax
0x1800334c3  jz      loc_180033569
0x1800334c9  mov     rcx, [rbx]; hModule
0x1800334cc  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x1800334d3  call    cs:__imp_GetProcAddress
0x1800334d9  mov     [rbx+58h], rax
0x1800334dd  test    rax, rax
0x1800334e0  jz      loc_180033569
0x1800334e6  mov     rcx, [rbx]; hModule
0x1800334e9  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x1800334f0  call    cs:__imp_GetProcAddress
0x1800334f6  mov     [rbx+60h], rax
0x1800334fa  test    rax, rax
0x1800334fd  jz      short loc_180033569
0x1800334ff  mov     rcx, [rbx]; hModule
0x180033502  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x180033509  call    cs:__imp_GetProcAddress
0x18003350f  mov     [rbx+68h], rax
0x180033513  test    rax, rax
0x180033516  jz      short loc_180033569
0x180033518  mov     rcx, [rbx]; hModule
0x18003351b  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x180033522  call    cs:__imp_GetProcAddress
0x180033528  mov     [rbx+70h], rax
0x18003352c  test    rax, rax
0x18003352f  jz      short loc_180033569
0x180033531  mov     rcx, [rbx]; hModule
0x180033534  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x18003353b  call    cs:__imp_GetProcAddress
0x180033541  mov     [rbx+78h], rax
0x180033545  test    rax, rax
0x180033548  jz      short loc_180033569
0x18003354a  mov     rcx, [rbx]; hModule
0x18003354d  lea     rdx, aClosedesktop; "CloseDesktop"
0x180033554  call    cs:__imp_GetProcAddress
0x18003355a  test    rax, rax
0x18003355d  mov     [rbx+80h], rax
0x180033564  setnz   al
0x180033567  jmp     short loc_18003356B
0x180033569  xor     al, al
0x18003356b  add     rsp, 20h
0x18003356f  pop     rbx
0x180033570  retn
```
