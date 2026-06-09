# NOTIFICATION_CONTEXT::TryReportFault(_EXCEPTION_POINTERS *)

- ea: `0x180025464`
- end: `0x18002554b`
- name: `?TryReportFault@NOTIFICATION_CONTEXT@@QEAAXPEAU_EXCEPTION_POINTERS@@@Z`
- size: `231`
- prototype: `void __fastcall(NOTIFICATION_CONTEXT *__hidden this, struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006010`

## callees

- `0x180025464`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800254c7`
- `msvcrt!wcscat_s` at `0x1800254c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002551d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002551d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800254e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800254e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800254a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800254a4`

## string_xrefs

- `0x1800254b9`: `\faultrep.dll`

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
0x180025464  mov     [rsp+arg_0], rbx
0x180025469  push    rdi
0x18002546a  sub     rsp, 240h
0x180025471  mov     rax, cs:__security_cookie
0x180025478  xor     rax, rsp
0x18002547b  mov     [rsp+248h+var_18], rax
0x180025483  mov     rdi, rdx
0x180025486  lea     rcx, [rsp+248h+Buffer]; void *
0x18002548b  xor     edx, edx; Val
0x18002548d  mov     r8d, 20Ah; Size
0x180025493  call    memset_0
0x180025498  mov     ebx, 105h
0x18002549d  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800254a2  mov     edx, ebx; uSize
0x1800254a4  call    cs:__imp_GetSystemDirectoryW
0x1800254ab  nop     dword ptr [rax+rax+00h]
0x1800254b0  dec     eax
0x1800254b2  cmp     eax, 104h
0x1800254b7  ja      short loc_180025529
0x1800254b9  lea     r8, aFaultrepDll; "\\faultrep.dll"
0x1800254c0  mov     edx, ebx; SizeInWords
0x1800254c2  lea     rcx, [rsp+248h+Buffer]; Destination
0x1800254c7  call    cs:__imp_wcscat_s
0x1800254ce  nop     dword ptr [rax+rax+00h]
0x1800254d3  test    eax, eax
0x1800254d5  jnz     short loc_180025529
0x1800254d7  xor     r8d, r8d; dwFlags
0x1800254da  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x1800254df  xor     edx, edx; hFile
0x1800254e1  call    cs:__imp_LoadLibraryExW
0x1800254e8  nop     dword ptr [rax+rax+00h]
0x1800254ed  mov     rbx, rax
0x1800254f0  test    rax, rax
0x1800254f3  jz      short loc_180025529
0x1800254f5  lea     rdx, ProcName; "ReportFault"
0x1800254fc  mov     rcx, rax; hModule
0x1800254ff  call    cs:__imp_GetProcAddress
0x180025506  nop     dword ptr [rax+rax+00h]
0x18002550b  test    rax, rax
0x18002550e  jz      short loc_18002551A
0x180025510  xor     edx, edx
0x180025512  mov     rcx, rdi
0x180025515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002551a  mov     rcx, rbx; hLibModule
0x18002551d  call    cs:__imp_FreeLibrary
0x180025524  nop     dword ptr [rax+rax+00h]
0x180025529  mov     rcx, [rsp+248h+var_18]
0x180025531  xor     rcx, rsp; StackCookie
0x180025534  call    __security_check_cookie
0x180025539  mov     rbx, [rsp+248h+arg_0]
0x180025541  add     rsp, 240h
0x180025548  pop     rdi
0x180025549  retn
```
