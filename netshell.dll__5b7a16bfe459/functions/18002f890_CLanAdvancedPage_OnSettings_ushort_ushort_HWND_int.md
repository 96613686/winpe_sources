# CLanAdvancedPage::OnSettings(ushort,ushort,HWND__ *,int &)

- ea: `0x18002f890`
- end: `0x18002f988`
- name: `?OnSettings@CLanAdvancedPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `248`
- prototype: `__int64 __fastcall(CLanAdvancedPage *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002fc20`

## callees

- `0x18002f890`
- `0x18003ff7c`
- `0x180065010`

## import_xrefs

- `USER32!MessageBoxW` at `0x18002f961`
- `USER32!MessageBoxW` at `0x18002f961`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f8d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f8d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f906`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8e3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f944`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f96c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f96c`

## string_xrefs

- `0x18002f8a9`: `hnetcfg.dll`

## pseudocode

```c
__int64 __fastcall CLanAdvancedPage::OnSettings(CLanAdvancedPage *this, __int64 a2, __int64 a3, const WCHAR *a4)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  WCHAR *Buffer; // [rsp+68h] [rbp+20h] BYREF

  Buffer = (WCHAR *)a4;
  Library = LoadLibraryExW(L"hnetcfg.dll", 0, 0x800u);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "HNetSharingAndFirewallSettingsDlg");
    if ( ProcAddress )
    {
      LastError = 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
        *((_QWORD *)this + 1),
        *((_QWORD *)this + 10),
        0,
        *((_QWORD *)this + 12));
    }
    else
    {
      LastError = GetLastError();
    }
    FreeLibrary(v6);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
  {
    Buffer = 0;
    if ( FormatMessageW(0x1300u, 0, LastError, 0x400u, (LPWSTR)&Buffer, 0, 0) )
    {
      MessageBoxW(*((HWND *)this + 1), Buffer, &Caption, 0);
      LocalFree(Buffer);
    }
  }
  return LresFromHr(0);
}

```

## disassembly

```asm
0x18002f890  mov     [rsp+arg_0], rbx
0x18002f895  mov     [rsp+arg_8], rsi
0x18002f89a  mov     [rsp+Buffer], r9
0x18002f89f  push    rdi
0x18002f8a0  sub     rsp, 40h
0x18002f8a4  mov     rsi, rcx
0x18002f8a7  xor     edx, edx; hFile
0x18002f8a9  lea     rcx, aHnetcfgDll; "hnetcfg.dll"
0x18002f8b0  mov     r8d, 800h; dwFlags
0x18002f8b6  call    cs:__imp_LoadLibraryExW
0x18002f8bc  mov     rdi, rax
0x18002f8bf  test    rax, rax
0x18002f8c2  jnz     short loc_18002F8CE
0x18002f8c4  call    cs:__imp_GetLastError
0x18002f8ca  mov     ebx, eax
0x18002f8cc  jmp     short loc_18002F90C
0x18002f8ce  lea     rdx, aHnetsharingand; "HNetSharingAndFirewallSettingsDlg"
0x18002f8d5  mov     rcx, rdi; hModule
0x18002f8d8  call    cs:__imp_GetProcAddress
0x18002f8de  test    rax, rax
0x18002f8e1  jnz     short loc_18002F8ED
0x18002f8e3  call    cs:__imp_GetLastError
0x18002f8e9  mov     ebx, eax
0x18002f8eb  jmp     short loc_18002F903
0x18002f8ed  mov     r9, [rsi+60h]
0x18002f8f1  xor     ebx, ebx
0x18002f8f3  mov     rdx, [rsi+50h]
0x18002f8f7  xor     r8d, r8d
0x18002f8fa  mov     rcx, [rsi+8]
0x18002f8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f903  mov     rcx, rdi; hLibModule
0x18002f906  call    cs:__imp_FreeLibrary
0x18002f90c  test    ebx, ebx
0x18002f90e  jz      short loc_18002F972
0x18002f910  mov     [rsp+48h+Arguments], 0; Arguments
0x18002f919  lea     rax, [rsp+48h+Buffer]
0x18002f91e  mov     [rsp+48h+nSize], 0; nSize
0x18002f926  mov     r9d, 400h; dwLanguageId
0x18002f92c  mov     r8d, ebx; dwMessageId
0x18002f92f  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x18002f934  xor     edx, edx; lpSource
0x18002f936  mov     [rsp+48h+Buffer], 0
0x18002f93f  mov     ecx, 1300h; dwFlags
0x18002f944  call    cs:__imp_FormatMessageW
0x18002f94a  test    eax, eax
0x18002f94c  jz      short loc_18002F972
0x18002f94e  mov     rdx, [rsp+48h+Buffer]; lpText
0x18002f953  lea     r8, Caption; lpCaption
0x18002f95a  mov     rcx, [rsi+8]; hWnd
0x18002f95e  xor     r9d, r9d; uType
0x18002f961  call    cs:__imp_MessageBoxW
0x18002f967  mov     rcx, [rsp+48h+Buffer]; hMem
0x18002f96c  call    cs:__imp_LocalFree
0x18002f972  xor     ecx, ecx; int
0x18002f974  mov     rbx, [rsp+48h+arg_0]
0x18002f979  mov     rsi, [rsp+48h+arg_8]
0x18002f97e  add     rsp, 40h
0x18002f982  pop     rdi
0x18002f983  jmp     ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
```
