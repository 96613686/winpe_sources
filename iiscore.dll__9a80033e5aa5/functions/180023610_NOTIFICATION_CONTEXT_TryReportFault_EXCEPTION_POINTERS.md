# NOTIFICATION_CONTEXT::TryReportFault(_EXCEPTION_POINTERS *)

- ea: `0x180023610`
- end: `0x1800236d8`
- name: `?TryReportFault@NOTIFICATION_CONTEXT@@QEAAXPEAU_EXCEPTION_POINTERS@@@Z`
- size: `200`
- prototype: `void __fastcall(NOTIFICATION_CONTEXT *__hidden this, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005ba0`

## callees

- `0x180023610`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002366d`
- `msvcrt!wcscat_s` at `0x18002366d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800236b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800236b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023699`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023699`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023681`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023681`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180023650`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180023650`

## string_xrefs

- `0x18002365f`: `\faultrep.dll`

## pseudocode

```c
void __fastcall NOTIFICATION_CONTEXT::TryReportFault(NOTIFICATION_CONTEXT *this, struct _EXCEPTION_POINTERS *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemDirectoryW(Buffer, 0x105u) - 1 <= 0x104 && !wcscat_s(Buffer, 0x105u, L"\\faultrep.dll") )
  {
    Library = LoadLibraryExW(Buffer, 0, 0);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "ReportFault");
      if ( ProcAddress )
        ((void (__fastcall *)(struct _EXCEPTION_POINTERS *, _QWORD))ProcAddress)(a2, 0);
      FreeLibrary(v4);
    }
  }
}

```

## disassembly

```asm
0x180023610  mov     [rsp+arg_0], rbx
0x180023615  push    rdi
0x180023616  sub     rsp, 240h
0x18002361d  mov     rax, cs:__security_cookie
0x180023624  xor     rax, rsp
0x180023627  mov     [rsp+248h+var_18], rax
0x18002362f  mov     rdi, rdx
0x180023632  lea     rcx, [rsp+248h+Buffer]; void *
0x180023637  xor     edx, edx; Val
0x180023639  mov     r8d, 20Ah; Size
0x18002363f  call    memset_0
0x180023644  mov     ebx, 105h
0x180023649  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18002364e  mov     edx, ebx; uSize
0x180023650  call    cs:__imp_GetSystemDirectoryW
0x180023656  dec     eax
0x180023658  cmp     eax, 104h
0x18002365d  ja      short loc_1800236B7
0x18002365f  lea     r8, aFaultrepDll; "\\faultrep.dll"
0x180023666  mov     edx, ebx; SizeInWords
0x180023668  lea     rcx, [rsp+248h+Buffer]; Destination
0x18002366d  call    cs:__imp_wcscat_s
0x180023673  test    eax, eax
0x180023675  jnz     short loc_1800236B7
0x180023677  xor     r8d, r8d; dwFlags
0x18002367a  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x18002367f  xor     edx, edx; hFile
0x180023681  call    cs:__imp_LoadLibraryExW
0x180023687  mov     rbx, rax
0x18002368a  test    rax, rax
0x18002368d  jz      short loc_1800236B7
0x18002368f  lea     rdx, ProcName; "ReportFault"
0x180023696  mov     rcx, rax; hModule
0x180023699  call    cs:__imp_GetProcAddress
0x18002369f  test    rax, rax
0x1800236a2  jz      short loc_1800236AE
0x1800236a4  xor     edx, edx
0x1800236a6  mov     rcx, rdi
0x1800236a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236ae  mov     rcx, rbx; hLibModule
0x1800236b1  call    cs:__imp_FreeLibrary
0x1800236b7  mov     rcx, [rsp+248h+var_18]
0x1800236bf  xor     rcx, rsp; StackCookie
0x1800236c2  call    __security_check_cookie
0x1800236c7  mov     rbx, [rsp+248h+arg_0]
0x1800236cf  add     rsp, 240h
0x1800236d6  pop     rdi
0x1800236d7  retn
```
