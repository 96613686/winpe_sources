# AslPathIsTemporaryDirectory

- ea: `0x18001e568`
- end: `0x18001e7e8`
- name: `AslPathIsTemporaryDirectory`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001d910`

## callees

- `0x18001e568`
- `0x18001e7f0`
- `0x18001f138`
- `0x180061df4`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!wcscpy_s` at `0x18001e607`
- `ntdll!wcscpy_s` at `0x18001e66d`
- `ntdll!wcscpy_s` at `0x18001e68a`
- `ntdll!wcscpy_s` at `0x18001e607`
- `ntdll!wcscpy_s` at `0x18001e66d`
- `ntdll!wcscpy_s` at `0x18001e68a`
- `ntdll!wcscat_s` at `0x18001e622`
- `ntdll!wcscat_s` at `0x18001e622`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001e5b0`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001e5b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e6f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e6f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e741`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e741`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e6d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e6d4`

## string_xrefs

- `0x18001e613`: `\TEMP\`
- `0x18001e679`: `\TEMP\`
- `0x18001e6e8`: `GetTempPath2W`
- `0x18001e792`: `Failed to retrieve temporary directory [%x]`
- `0x18001e7be`: `Failed to retrieve temporary directory [%x]`
- `0x18001e7a3`: `AslPathIsTemporaryDirectory`
- `0x18001e7cf`: `AslPathIsTemporaryDirectory`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryDirectory(int *a1, const wchar_t *a2)
{
  int v4; // ebx
  size_t v5; // rdi
  size_t v6; // r8
  unsigned int v7; // r14d
  const wchar_t *NtSystemRoot; // rax
  size_t v9; // r8
  const wchar_t *v10; // rax
  size_t v11; // r8
  HMODULE Library; // rax
  HMODULE v13; // rsi
  FARPROC ProcAddress; // rax
  wchar_t Buffer[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Destination[258]; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v18; // [rsp+238h] [rbp+138h]

  v4 = 0;
  if ( GetTempPathW(0x105u, Buffer) - 1 > 0x103 )
  {
    v7 = -1073741789;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathIsTemporaryDirectory",
      607,
      (unsigned int)"Failed to retrieve temporary directory [%x]",
      35);
  }
  else
  {
    v5 = -1;
    v6 = -1;
    v7 = 0;
    do
      ++v6;
    while ( Buffer[v6] );
    if ( !wcsnicmp_0(a2, Buffer, v6) )
      goto LABEL_19;
    NtSystemRoot = (const wchar_t *)RtlDownlevelGetNtSystemRoot();
    wcscpy_s(Buffer, 0x105u, NtSystemRoot);
    wcscat_s(Buffer, 0x105u, L"\\TEMP\\");
    v18 = 0;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    if ( !wcsnicmp_0(a2, Buffer, v9) )
      goto LABEL_19;
    v10 = (const wchar_t *)RtlDownlevelGetNtSystemRoot();
    wcscpy_s(Buffer, 0x105u, v10);
    wcscpy_s(Destination, 0x103u, L"\\TEMP\\");
    v18 = 0;
    v11 = -1;
    do
      ++v11;
    while ( Buffer[v11] );
    if ( wcsnicmp_0(a2, Buffer, v11) )
    {
      Library = LoadLibraryExW(L"KernelBase", 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "GetTempPath2W");
        if ( ProcAddress )
        {
          if ( ((unsigned int (__fastcall *)(__int64, wchar_t *))ProcAddress)(261, Buffer) - 1 > 0x103 )
          {
            v7 = -1073741789;
            AslLogCallPrintf(
              1,
              (unsigned int)"AslPathIsTemporaryDirectory",
              653,
              (unsigned int)"Failed to retrieve temporary directory [%x]",
              35);
          }
          else
          {
            do
              ++v5;
            while ( Buffer[v5] );
            if ( !wcsnicmp_0(a2, Buffer, v5) )
              v4 = 1;
          }
        }
        FreeLibrary(v13);
      }
    }
    else
    {
LABEL_19:
      v4 = 1;
    }
  }
  *a1 = v4;
  return v7;
}

```

## disassembly

```asm
0x18001e568  mov     [rsp-8+arg_10], rbx
0x18001e56d  push    rbp
0x18001e56e  push    rsi
0x18001e56f  push    rdi
0x18001e570  push    r12
0x18001e572  push    r13
0x18001e574  push    r14
0x18001e576  push    r15
0x18001e578  lea     rbp, [rsp-150h]
0x18001e580  sub     rsp, 250h
0x18001e587  mov     rax, cs:__security_cookie
0x18001e58e  xor     rax, rsp
0x18001e591  mov     [rbp+180h+var_40], rax
0x18001e598  mov     r15, rdx
0x18001e59b  mov     r12, rcx
0x18001e59e  mov     esi, 105h
0x18001e5a3  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x18001e5a8  xor     r13d, r13d
0x18001e5ab  mov     ecx, esi; nBufferLength
0x18001e5ad  mov     ebx, r13d
0x18001e5b0  call    cs:__imp_GetTempPathW
0x18001e5b7  nop     dword ptr [rax+rax+00h]
0x18001e5bc  dec     eax
0x18001e5be  cmp     eax, 103h
0x18001e5c3  ja      loc_18001E7B9
0x18001e5c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e5cd  lea     rax, [rsp+280h+Buffer]
0x18001e5d2  mov     r8, rdi
0x18001e5d5  mov     r14d, r13d
0x18001e5d8  inc     r8; MaxCount
0x18001e5db  cmp     [rax+r8*2], r13w
0x18001e5e0  jnz     short loc_18001E5D8
0x18001e5e2  lea     rdx, [rsp+280h+Buffer]; String2
0x18001e5e7  mov     rcx, r15; String1
0x18001e5ea  call    _wcsnicmp_0
0x18001e5ef  test    eax, eax
0x18001e5f1  jz      loc_18001E77F
0x18001e5f7  call    RtlDownlevelGetNtSystemRoot
0x18001e5fc  mov     r8, rax; Source
0x18001e5ff  lea     rcx, [rsp+280h+Buffer]; Destination
0x18001e604  mov     rdx, rsi; SizeInWords
0x18001e607  call    cs:__imp_wcscpy_s
0x18001e60e  nop     dword ptr [rax+rax+00h]
0x18001e613  lea     r8, aTemp_1; "\\TEMP\\"
0x18001e61a  mov     rdx, rsi; SizeInWords
0x18001e61d  lea     rcx, [rsp+280h+Buffer]; Destination
0x18001e622  call    cs:__imp_wcscat_s
0x18001e629  nop     dword ptr [rax+rax+00h]
0x18001e62e  lea     rax, [rsp+280h+Buffer]
0x18001e633  mov     [rbp+180h+var_48], r13w
0x18001e63b  mov     r8, rdi
0x18001e63e  inc     r8; MaxCount
0x18001e641  cmp     [rax+r8*2], r13w
0x18001e646  jnz     short loc_18001E63E
0x18001e648  lea     rdx, [rsp+280h+Buffer]; String2
0x18001e64d  mov     rcx, r15; String1
0x18001e650  call    _wcsnicmp_0
0x18001e655  test    eax, eax
0x18001e657  jz      loc_18001E77F
0x18001e65d  call    RtlDownlevelGetNtSystemRoot
0x18001e662  mov     r8, rax; Source
0x18001e665  lea     rcx, [rsp+280h+Buffer]; Destination
0x18001e66a  mov     rdx, rsi; SizeInWords
0x18001e66d  call    cs:__imp_wcscpy_s
0x18001e674  nop     dword ptr [rax+rax+00h]
0x18001e679  lea     r8, aTemp_1; "\\TEMP\\"
0x18001e680  mov     edx, 103h; SizeInWords
0x18001e685  lea     rcx, [rsp+280h+Destination]; Destination
0x18001e68a  call    cs:__imp_wcscpy_s
0x18001e691  nop     dword ptr [rax+rax+00h]
0x18001e696  lea     rax, [rsp+280h+Buffer]
0x18001e69b  mov     [rbp+180h+var_48], r13w
0x18001e6a3  mov     r8, rdi
0x18001e6a6  inc     r8; MaxCount
0x18001e6a9  cmp     [rax+r8*2], r13w
0x18001e6ae  jnz     short loc_18001E6A6
0x18001e6b0  lea     rdx, [rsp+280h+Buffer]; String2
0x18001e6b5  mov     rcx, r15; String1
0x18001e6b8  call    _wcsnicmp_0
0x18001e6bd  test    eax, eax
0x18001e6bf  jz      loc_18001E77F
0x18001e6c5  xor     edx, edx; hFile
0x18001e6c7  lea     rcx, LibFileName; "KernelBase"
0x18001e6ce  mov     r8d, 800h; dwFlags
0x18001e6d4  call    cs:__imp_LoadLibraryExW
0x18001e6db  nop     dword ptr [rax+rax+00h]
0x18001e6e0  mov     rsi, rax
0x18001e6e3  test    rax, rax
0x18001e6e6  jz      short loc_18001E74D
0x18001e6e8  lea     rdx, ProcName; "GetTempPath2W"
0x18001e6ef  mov     rcx, rax; hModule
0x18001e6f2  call    cs:__imp_GetProcAddress
0x18001e6f9  nop     dword ptr [rax+rax+00h]
0x18001e6fe  test    rax, rax
0x18001e701  jz      short loc_18001E73E
0x18001e703  lea     rdx, [rsp+280h+Buffer]
0x18001e708  mov     ecx, 105h
0x18001e70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e712  dec     eax
0x18001e714  cmp     eax, 103h
0x18001e719  ja      short loc_18001E78D
0x18001e71b  lea     rax, [rsp+280h+Buffer]
0x18001e720  inc     rdi
0x18001e723  cmp     [rax+rdi*2], r13w
0x18001e728  jnz     short loc_18001E720
0x18001e72a  mov     r8, rdi; MaxCount
0x18001e72d  lea     rdx, [rsp+280h+Buffer]; String2
0x18001e732  mov     rcx, r15; String1
0x18001e735  call    _wcsnicmp_0
0x18001e73a  test    eax, eax
0x18001e73c  jz      short loc_18001E786
0x18001e73e  mov     rcx, rsi; hLibModule
0x18001e741  call    cs:__imp_FreeLibrary
0x18001e748  nop     dword ptr [rax+rax+00h]
0x18001e74d  mov     [r12], ebx
0x18001e751  mov     eax, r14d
0x18001e754  mov     rcx, [rbp+180h+var_40]
0x18001e75b  xor     rcx, rsp; StackCookie
0x18001e75e  call    __security_check_cookie
0x18001e763  mov     rbx, [rsp+280h+arg_10]
0x18001e76b  add     rsp, 250h
0x18001e772  pop     r15
0x18001e774  pop     r14
0x18001e776  pop     r13
0x18001e778  pop     r12
0x18001e77a  pop     rdi
0x18001e77b  pop     rsi
0x18001e77c  pop     rbp
0x18001e77d  retn
0x18001e77f  mov     ebx, 1
0x18001e784  jmp     short loc_18001E74D
0x18001e786  mov     ebx, 1
0x18001e78b  jmp     short loc_18001E73E
0x18001e78d  mov     eax, 0C0000023h
0x18001e792  lea     r9, aFailedToRetrie; "Failed to retrieve temporary directory "...
0x18001e799  mov     r8d, 28Dh
0x18001e79f  mov     [rsp+280h+var_260], eax
0x18001e7a3  lea     rdx, aAslpathistempo_1; "AslPathIsTemporaryDirectory"
0x18001e7aa  mov     ecx, 1
0x18001e7af  mov     r14d, eax
0x18001e7b2  call    AslLogCallPrintf
0x18001e7b7  jmp     short loc_18001E73E
0x18001e7b9  mov     eax, 0C0000023h
0x18001e7be  lea     r9, aFailedToRetrie; "Failed to retrieve temporary directory "...
0x18001e7c5  mov     r8d, 25Fh
0x18001e7cb  mov     [rsp+280h+var_260], eax
0x18001e7cf  lea     rdx, aAslpathistempo_1; "AslPathIsTemporaryDirectory"
0x18001e7d6  mov     ecx, 1
0x18001e7db  mov     r14d, eax
0x18001e7de  call    AslLogCallPrintf
0x18001e7e3  jmp     loc_18001E74D
```
