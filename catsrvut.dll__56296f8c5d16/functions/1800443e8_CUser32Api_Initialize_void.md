# CUser32Api::Initialize(void)

- ea: `0x1800443e8`
- end: `0x1800445e1`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800442a0`

## callees

- `0x1800443e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044405`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044405`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004443e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004445b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044509`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044526`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044579`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044592`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800445ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800445c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004443e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004445b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800444ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044509`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044526`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044579`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044592`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800445ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800445c4`

## string_xrefs

- `0x1800443fc`: `user32.dll`
- `0x18004453c`: `OpenWindowStationW`
- `0x180044572`: `GetThreadDesktop`
- `0x18004458b`: `SetThreadDesktop`
- `0x1800445a4`: `OpenDesktopW`

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
0x1800443e8  push    rbx
0x1800443ea  sub     rsp, 20h
0x1800443ee  mov     rax, [rcx]
0x1800443f1  mov     rbx, rcx
0x1800443f4  test    rax, rax
0x1800443f7  jnz     short loc_180044417
0x1800443f9  xor     r8d, r8d; dwFlags
0x1800443fc  lea     rcx, aUser32Dll; "user32.dll"
0x180044403  xor     edx, edx; hFile
0x180044405  call    cs:__imp_LoadLibraryExW
0x18004440b  mov     [rbx], rax
0x18004440e  test    rax, rax
0x180044411  jz      loc_1800445D9
0x180044417  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x18004441e  mov     rcx, rax; hModule
0x180044421  call    cs:__imp_GetProcAddress
0x180044427  mov     [rbx+8], rax
0x18004442b  test    rax, rax
0x18004442e  jz      loc_1800445D9
0x180044434  mov     rcx, [rbx]; hModule
0x180044437  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x18004443e  call    cs:__imp_GetProcAddress
0x180044444  mov     [rbx+10h], rax
0x180044448  test    rax, rax
0x18004444b  jz      loc_1800445D9
0x180044451  mov     rcx, [rbx]; hModule
0x180044454  lea     rdx, aEnddialog; "EndDialog"
0x18004445b  call    cs:__imp_GetProcAddress
0x180044461  mov     [rbx+18h], rax
0x180044465  test    rax, rax
0x180044468  jz      loc_1800445D9
0x18004446e  mov     rcx, [rbx]; hModule
0x180044471  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x180044478  call    cs:__imp_GetProcAddress
0x18004447e  mov     [rbx+20h], rax
0x180044482  test    rax, rax
0x180044485  jz      loc_1800445D9
0x18004448b  mov     rcx, [rbx]; hModule
0x18004448e  lea     rdx, aGetwindowrect; "GetWindowRect"
0x180044495  call    cs:__imp_GetProcAddress
0x18004449b  mov     [rbx+28h], rax
0x18004449f  test    rax, rax
0x1800444a2  jz      loc_1800445D9
0x1800444a8  mov     rcx, [rbx]; hModule
0x1800444ab  lea     rdx, aGetclientrect; "GetClientRect"
0x1800444b2  call    cs:__imp_GetProcAddress
0x1800444b8  mov     [rbx+30h], rax
0x1800444bc  test    rax, rax
0x1800444bf  jz      loc_1800445D9
0x1800444c5  mov     rcx, [rbx]; hModule
0x1800444c8  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x1800444cf  call    cs:__imp_GetProcAddress
0x1800444d5  mov     [rbx+38h], rax
0x1800444d9  test    rax, rax
0x1800444dc  jz      loc_1800445D9
0x1800444e2  mov     rcx, [rbx]; hModule
0x1800444e5  lea     rdx, aSetwindowpos; "SetWindowPos"
0x1800444ec  call    cs:__imp_GetProcAddress
0x1800444f2  mov     [rbx+40h], rax
0x1800444f6  test    rax, rax
0x1800444f9  jz      loc_1800445D9
0x1800444ff  mov     rcx, [rbx]; hModule
0x180044502  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180044509  call    cs:__imp_GetProcAddress
0x18004450f  mov     [rbx+48h], rax
0x180044513  test    rax, rax
0x180044516  jz      loc_1800445D9
0x18004451c  mov     rcx, [rbx]; hModule
0x18004451f  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x180044526  call    cs:__imp_GetProcAddress
0x18004452c  mov     [rbx+50h], rax
0x180044530  test    rax, rax
0x180044533  jz      loc_1800445D9
0x180044539  mov     rcx, [rbx]; hModule
0x18004453c  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x180044543  call    cs:__imp_GetProcAddress
0x180044549  mov     [rbx+58h], rax
0x18004454d  test    rax, rax
0x180044550  jz      loc_1800445D9
0x180044556  mov     rcx, [rbx]; hModule
0x180044559  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x180044560  call    cs:__imp_GetProcAddress
0x180044566  mov     [rbx+60h], rax
0x18004456a  test    rax, rax
0x18004456d  jz      short loc_1800445D9
0x18004456f  mov     rcx, [rbx]; hModule
0x180044572  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x180044579  call    cs:__imp_GetProcAddress
0x18004457f  mov     [rbx+68h], rax
0x180044583  test    rax, rax
0x180044586  jz      short loc_1800445D9
0x180044588  mov     rcx, [rbx]; hModule
0x18004458b  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x180044592  call    cs:__imp_GetProcAddress
0x180044598  mov     [rbx+70h], rax
0x18004459c  test    rax, rax
0x18004459f  jz      short loc_1800445D9
0x1800445a1  mov     rcx, [rbx]; hModule
0x1800445a4  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x1800445ab  call    cs:__imp_GetProcAddress
0x1800445b1  mov     [rbx+78h], rax
0x1800445b5  test    rax, rax
0x1800445b8  jz      short loc_1800445D9
0x1800445ba  mov     rcx, [rbx]; hModule
0x1800445bd  lea     rdx, aClosedesktop; "CloseDesktop"
0x1800445c4  call    cs:__imp_GetProcAddress
0x1800445ca  test    rax, rax
0x1800445cd  mov     [rbx+80h], rax
0x1800445d4  setnz   al
0x1800445d7  jmp     short loc_1800445DB
0x1800445d9  xor     al, al
0x1800445db  add     rsp, 20h
0x1800445df  pop     rbx
0x1800445e0  retn
```
