# CUser32Api::Initialize(void)

- ea: `0x18007e730`
- end: `0x18007e929`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007e5ec`

## callees

- `0x18007e730`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007e74d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007e74d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e769`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e786`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e817`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e834`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e86e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e88b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e90c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e769`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e786`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e817`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e834`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e86e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e88b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e8f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007e90c`

## string_xrefs

- `0x18007e744`: `user32.dll`
- `0x18007e884`: `OpenWindowStationW`
- `0x18007e8d3`: `SetThreadDesktop`
- `0x18007e8ba`: `GetThreadDesktop`
- `0x18007e8ec`: `OpenDesktopW`

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
0x18007e730  push    rbx
0x18007e732  sub     rsp, 20h
0x18007e736  mov     rax, [rcx]
0x18007e739  mov     rbx, rcx
0x18007e73c  test    rax, rax
0x18007e73f  jnz     short loc_18007E75F
0x18007e741  xor     r8d, r8d; dwFlags
0x18007e744  lea     rcx, aUser32Dll; "user32.dll"
0x18007e74b  xor     edx, edx; hFile
0x18007e74d  call    cs:__imp_LoadLibraryExW
0x18007e753  mov     [rbx], rax
0x18007e756  test    rax, rax
0x18007e759  jz      loc_18007E921
0x18007e75f  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x18007e766  mov     rcx, rax; hModule
0x18007e769  call    cs:__imp_GetProcAddress
0x18007e76f  mov     [rbx+8], rax
0x18007e773  test    rax, rax
0x18007e776  jz      loc_18007E921
0x18007e77c  mov     rcx, [rbx]; hModule
0x18007e77f  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x18007e786  call    cs:__imp_GetProcAddress
0x18007e78c  mov     [rbx+10h], rax
0x18007e790  test    rax, rax
0x18007e793  jz      loc_18007E921
0x18007e799  mov     rcx, [rbx]; hModule
0x18007e79c  lea     rdx, aEnddialog; "EndDialog"
0x18007e7a3  call    cs:__imp_GetProcAddress
0x18007e7a9  mov     [rbx+18h], rax
0x18007e7ad  test    rax, rax
0x18007e7b0  jz      loc_18007E921
0x18007e7b6  mov     rcx, [rbx]; hModule
0x18007e7b9  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x18007e7c0  call    cs:__imp_GetProcAddress
0x18007e7c6  mov     [rbx+20h], rax
0x18007e7ca  test    rax, rax
0x18007e7cd  jz      loc_18007E921
0x18007e7d3  mov     rcx, [rbx]; hModule
0x18007e7d6  lea     rdx, aGetwindowrect; "GetWindowRect"
0x18007e7dd  call    cs:__imp_GetProcAddress
0x18007e7e3  mov     [rbx+28h], rax
0x18007e7e7  test    rax, rax
0x18007e7ea  jz      loc_18007E921
0x18007e7f0  mov     rcx, [rbx]; hModule
0x18007e7f3  lea     rdx, aGetclientrect; "GetClientRect"
0x18007e7fa  call    cs:__imp_GetProcAddress
0x18007e800  mov     [rbx+30h], rax
0x18007e804  test    rax, rax
0x18007e807  jz      loc_18007E921
0x18007e80d  mov     rcx, [rbx]; hModule
0x18007e810  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x18007e817  call    cs:__imp_GetProcAddress
0x18007e81d  mov     [rbx+38h], rax
0x18007e821  test    rax, rax
0x18007e824  jz      loc_18007E921
0x18007e82a  mov     rcx, [rbx]; hModule
0x18007e82d  lea     rdx, aSetwindowpos; "SetWindowPos"
0x18007e834  call    cs:__imp_GetProcAddress
0x18007e83a  mov     [rbx+40h], rax
0x18007e83e  test    rax, rax
0x18007e841  jz      loc_18007E921
0x18007e847  mov     rcx, [rbx]; hModule
0x18007e84a  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x18007e851  call    cs:__imp_GetProcAddress
0x18007e857  mov     [rbx+48h], rax
0x18007e85b  test    rax, rax
0x18007e85e  jz      loc_18007E921
0x18007e864  mov     rcx, [rbx]; hModule
0x18007e867  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x18007e86e  call    cs:__imp_GetProcAddress
0x18007e874  mov     [rbx+50h], rax
0x18007e878  test    rax, rax
0x18007e87b  jz      loc_18007E921
0x18007e881  mov     rcx, [rbx]; hModule
0x18007e884  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x18007e88b  call    cs:__imp_GetProcAddress
0x18007e891  mov     [rbx+58h], rax
0x18007e895  test    rax, rax
0x18007e898  jz      loc_18007E921
0x18007e89e  mov     rcx, [rbx]; hModule
0x18007e8a1  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x18007e8a8  call    cs:__imp_GetProcAddress
0x18007e8ae  mov     [rbx+60h], rax
0x18007e8b2  test    rax, rax
0x18007e8b5  jz      short loc_18007E921
0x18007e8b7  mov     rcx, [rbx]; hModule
0x18007e8ba  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x18007e8c1  call    cs:__imp_GetProcAddress
0x18007e8c7  mov     [rbx+68h], rax
0x18007e8cb  test    rax, rax
0x18007e8ce  jz      short loc_18007E921
0x18007e8d0  mov     rcx, [rbx]; hModule
0x18007e8d3  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x18007e8da  call    cs:__imp_GetProcAddress
0x18007e8e0  mov     [rbx+70h], rax
0x18007e8e4  test    rax, rax
0x18007e8e7  jz      short loc_18007E921
0x18007e8e9  mov     rcx, [rbx]; hModule
0x18007e8ec  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x18007e8f3  call    cs:__imp_GetProcAddress
0x18007e8f9  mov     [rbx+78h], rax
0x18007e8fd  test    rax, rax
0x18007e900  jz      short loc_18007E921
0x18007e902  mov     rcx, [rbx]; hModule
0x18007e905  lea     rdx, aClosedesktop; "CloseDesktop"
0x18007e90c  call    cs:__imp_GetProcAddress
0x18007e912  test    rax, rax
0x18007e915  mov     [rbx+80h], rax
0x18007e91c  setnz   al
0x18007e91f  jmp     short loc_18007E923
0x18007e921  xor     al, al
0x18007e923  add     rsp, 20h
0x18007e927  pop     rbx
0x18007e928  retn
```
