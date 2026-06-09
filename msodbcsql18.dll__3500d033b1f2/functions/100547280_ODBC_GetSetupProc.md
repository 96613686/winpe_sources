# ODBC___GetSetupProc

- ea: `0x100547280`
- end: `0x1005473b0`
- name: `ODBC___GetSetupProc`
- size: `304`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x100546f80`
- `0x100546ff0`
- `0x100547060`
- `0x1005470b0`
- `0x1005470f0`
- `0x100547130`
- `0x100547180`

## callees

- `0x1005471e0`
- `0x100547280`
- `0x100547460`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x100547326`
- `KERNEL32!GetModuleFileNameW` at `0x100547339`
- `KERNEL32!GetModuleFileNameW` at `0x100547326`
- `KERNEL32!GetModuleFileNameW` at `0x100547339`
- `KERNEL32!GetProcAddress` at `0x1005472ea`
- `KERNEL32!GetProcAddress` at `0x1005472ea`
- `USER32!MessageBoxW` at `0x1005472cf`
- `USER32!MessageBoxW` at `0x100547386`
- `USER32!MessageBoxW` at `0x1005472cf`
- `USER32!MessageBoxW` at `0x100547386`

## string_xrefs

- `0x100547351`: `The program %s, or one of its DLLs attempted to call the function %S which is not supported in the loaded ODBC installer DLL (%s). Press OK to proceed.`
- `0x1005472bf`: `ODBC Installer Error`
- `0x10054736f`: `ODBC Installer Error`
- `0x1005472c6`: `The ODBC installer DLL (ODBCCP32.DLL) is not installed on this system.`

## pseudocode

```c
FARPROC __fastcall ODBC___GetSetupProc(LPCSTR lpProcName)
{
  HMODULE ProperSetupDLL; // rax
  FARPROC ProcAddress; // rbx
  WCHAR v5[264]; // [rsp+30h] [rbp-A58h] BYREF
  WCHAR Filename[264]; // [rsp+240h] [rbp-848h] BYREF
  wchar_t pszDest[784]; // [rsp+450h] [rbp-638h] BYREF

  ProperSetupDLL = hModule;
  if ( hModule || (ProperSetupDLL = LoadProperSetupDLL(), (hModule = ProperSetupDLL) != 0) )
  {
    ProcAddress = GetProcAddress(ProperSetupDLL, lpProcName);
    if ( !ProcAddress )
    {
      pszDest[0] = 0;
      Filename[0] = 0;
      v5[0] = 0;
      GetModuleFileNameW(hModule, Filename, 0x105u);
      GetModuleFileNameW(0, v5, 0x105u);
      StringCchPrintfW(
        pszDest,
        0x30Fu,
        L"The program %s, or one of its DLLs attempted to call the function %S which is not supported in the loaded ODBC i"
         "nstaller DLL (%s). Press OK to proceed.",
        v5,
        lpProcName,
        Filename);
      MessageBoxW(0, pszDest, L"ODBC Installer Error", 0x40u);
    }
    return ProcAddress;
  }
  else
  {
    MessageBoxW(
      0,
      L"The ODBC installer DLL (ODBCCP32.DLL) is not installed on this system.",
      L"ODBC Installer Error",
      0x40u);
    return 0;
  }
}

```

## disassembly

```asm
0x100547280  push    rdi
0x100547282  sub     rsp, 0A80h
0x100547289  mov     rax, cs:__security_cookie
0x100547290  xor     rax, rsp
0x100547293  mov     [rsp+0A88h+var_18], rax
0x10054729b  mov     rax, cs:hModule
0x1005472a2  mov     rdi, rcx
0x1005472a5  test    rax, rax
0x1005472a8  jnz     short loc_1005472DC
0x1005472aa  call    LoadProperSetupDLL
0x1005472af  mov     cs:hModule, rax
0x1005472b6  test    rax, rax
0x1005472b9  jnz     short loc_1005472DC
0x1005472bb  lea     r9d, [rax+40h]; uType
0x1005472bf  lea     r8, INSTALLER_ERROR_TITLE; "ODBC Installer Error"
0x1005472c6  lea     rdx, INSTALLER_ERROR_NOT_INSTALLED; "The ODBC installer DLL (ODBCCP32.DLL) i"...
0x1005472cd  xor     ecx, ecx; hWnd
0x1005472cf  call    cs:__imp_MessageBoxW
0x1005472d5  xor     eax, eax
0x1005472d7  jmp     loc_100547397
0x1005472dc  mov     rdx, rdi; lpProcName
0x1005472df  mov     rcx, rax; hModule
0x1005472e2  mov     [rsp+0A88h+arg_8], rbx
0x1005472ea  call    cs:__imp_GetProcAddress
0x1005472f0  mov     rbx, rax
0x1005472f3  test    rax, rax
0x1005472f6  jnz     loc_10054738C
0x1005472fc  mov     rcx, cs:hModule; hModule
0x100547303  lea     rdx, [rsp+0A88h+Filename]; lpFilename
0x10054730b  mov     r8d, 105h; nSize
0x100547311  mov     [rsp+0A88h+pszDest], ax
0x100547319  mov     [rsp+0A88h+Filename], ax
0x100547321  mov     [rsp+0A88h+var_A58], ax
0x100547326  call    cs:__imp_GetModuleFileNameW
0x10054732c  lea     rdx, [rsp+0A88h+var_A58]; lpFilename
0x100547331  mov     r8d, 105h; nSize
0x100547337  xor     ecx, ecx; hModule
0x100547339  call    cs:__imp_GetModuleFileNameW
0x10054733f  lea     rax, [rsp+0A88h+Filename]
0x100547347  lea     r9, [rsp+0A88h+var_A58]
0x10054734c  mov     [rsp+0A88h+var_A60], rax
0x100547351  lea     r8, INSTALLER_ERROR_API_NOTEXIST_FORMAT; "The program %s, or one of its DLLs atte"...
0x100547358  lea     rcx, [rsp+0A88h+pszDest]; pszDest
0x100547360  mov     edx, 30Fh; cchDest
0x100547365  mov     [rsp+0A88h+var_A68], rdi
0x10054736a  call    StringCchPrintfW
0x10054736f  lea     r8, INSTALLER_ERROR_TITLE; "ODBC Installer Error"
0x100547376  lea     rdx, [rsp+0A88h+pszDest]; lpText
0x10054737e  mov     r9d, 40h ; '@'; uType
0x100547384  xor     ecx, ecx; hWnd
0x100547386  call    cs:__imp_MessageBoxW
0x10054738c  mov     rax, rbx
0x10054738f  mov     rbx, [rsp+0A88h+arg_8]
0x100547397  mov     rcx, [rsp+0A88h+var_18]
0x10054739f  xor     rcx, rsp; StackCookie
0x1005473a2  call    __security_check_cookie
0x1005473a7  add     rsp, 0A80h
0x1005473ae  pop     rdi
0x1005473af  retn
```
