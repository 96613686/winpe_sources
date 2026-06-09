# AslPathIsTemporaryDirectory

- ea: `0x180020764`
- end: `0x180020a8b`
- name: `AslPathIsTemporaryDirectory`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001fabc`

## callees

- `0x180020764`
- `0x1800212e4`
- `0x18005c414`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!wcscpy_s` at `0x18002080a`
- `ntdll!wcscpy_s` at `0x180020870`
- `ntdll!wcscpy_s` at `0x180020887`
- `ntdll!wcscpy_s` at `0x18002080a`
- `ntdll!wcscpy_s` at `0x180020870`
- `ntdll!wcscpy_s` at `0x180020887`
- `ntdll!wcscat_s` at `0x18002081e`
- `ntdll!wcscat_s` at `0x18002081e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800207aa`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800207aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800208e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020997`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800209ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800208e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020997`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800209ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020934`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800209ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020a04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020934`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800209ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020a04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800208cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002097f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800209d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800208cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002097f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800209d6`

## string_xrefs

- `0x180020810`: `\TEMP\`
- `0x180020876`: `\TEMP\`
- `0x1800208d9`: `GetTempPath2W`
- `0x18002096d`: `ntdll.dll`
- `0x1800209c4`: `ntdll.dll`
- `0x180020a32`: `Failed to retrieve temporary directory [%x]`
- `0x180020a61`: `Failed to retrieve temporary directory [%x]`
- `0x180020a43`: `AslPathIsTemporaryDirectory`
- `0x180020a72`: `AslPathIsTemporaryDirectory`

## pseudocode

```c
__int64 __fastcall AslPathIsTemporaryDirectory(int *a1, const wchar_t *a2)
{
  int v4; // edi
  size_t v5; // rsi
  size_t v6; // r8
  unsigned int v7; // r15d
  __int64 v8; // rbx
  size_t v9; // r8
  __int64 v10; // rbx
  size_t v11; // r8
  HMODULE v12; // rax
  HMODULE v13; // rbx
  FARPROC v14; // rax
  HMODULE Library; // rax
  HMODULE v17; // r14
  __int64 (*ProcAddress)(void); // rax
  HMODULE v19; // rax
  HMODULE v20; // r14
  __int64 (*v21)(void); // rax
  wchar_t Buffer[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Destination[258]; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v24; // [rsp+238h] [rbp+138h]

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
      goto LABEL_31;
    v8 = (__int64)Src;
    if ( !Src )
    {
      v8 = 2147352624;
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v17 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v8 = ProcAddress();
        FreeLibrary(v17);
      }
      Src = (wchar_t *)v8;
    }
    wcscpy_s(Buffer, 0x105u, (const wchar_t *)v8);
    wcscat_s(Buffer, 0x105u, L"\\TEMP\\");
    v24 = 0;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    if ( !wcsnicmp_0(a2, Buffer, v9) )
      goto LABEL_31;
    v10 = (__int64)Src;
    if ( !Src )
    {
      v10 = 2147352624;
      v19 = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v20 = v19;
      if ( v19 )
      {
        v21 = GetProcAddress(v19, "RtlGetNtSystemRoot");
        if ( v21 )
          v10 = v21();
        FreeLibrary(v20);
      }
      Src = (wchar_t *)v10;
    }
    wcscpy_s(Buffer, 0x105u, (const wchar_t *)v10);
    wcscpy_s(Destination, 0x103u, L"\\TEMP\\");
    v24 = 0;
    v11 = -1;
    do
      ++v11;
    while ( Buffer[v11] );
    if ( wcsnicmp_0(a2, Buffer, v11) )
    {
      v12 = LoadLibraryExW(L"KernelBase", 0, 0x800u);
      v13 = v12;
      if ( v12 )
      {
        v14 = GetProcAddress(v12, "GetTempPath2W");
        if ( v14 )
        {
          if ( ((unsigned int (__fastcall *)(__int64, wchar_t *))v14)(261, Buffer) - 1 > 0x103 )
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
LABEL_31:
      v4 = 1;
    }
  }
  *a1 = v4;
  return v7;
}

```

## disassembly

```asm
0x180020764  mov     [rsp-8+arg_10], rbx
0x180020769  push    rbp
0x18002076a  push    rsi
0x18002076b  push    rdi
0x18002076c  push    r12
0x18002076e  push    r13
0x180020770  push    r14
0x180020772  push    r15
0x180020774  lea     rbp, [rsp-150h]
0x18002077c  sub     rsp, 250h
0x180020783  mov     rax, cs:__security_cookie
0x18002078a  xor     rax, rsp
0x18002078d  mov     [rbp+180h+var_40], rax
0x180020794  mov     r12, rdx
0x180020797  mov     r13, rcx
0x18002079a  xor     r14d, r14d
0x18002079d  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x1800207a2  mov     ecx, 105h; nBufferLength
0x1800207a7  mov     edi, r14d
0x1800207aa  call    cs:__imp_GetTempPathW
0x1800207b0  dec     eax
0x1800207b2  cmp     eax, 103h
0x1800207b7  ja      loc_180020A5C
0x1800207bd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800207c1  lea     rax, [rsp+280h+Buffer]
0x1800207c6  mov     r8, rsi
0x1800207c9  mov     r15d, r14d
0x1800207cc  inc     r8; MaxCount
0x1800207cf  cmp     [rax+r8*2], r14w
0x1800207d4  jnz     short loc_1800207CC
0x1800207d6  lea     rdx, [rsp+280h+Buffer]; String2
0x1800207db  mov     rcx, r12; String1
0x1800207de  call    _wcsnicmp_0
0x1800207e3  test    eax, eax
0x1800207e5  jz      loc_180020A19
0x1800207eb  mov     rbx, cs:Src
0x1800207f2  test    rbx, rbx
0x1800207f5  jz      loc_18002096B
0x1800207fb  mov     r8, rbx; Source
0x1800207fe  lea     rcx, [rsp+280h+Buffer]; Destination
0x180020803  mov     ebx, 105h
0x180020808  mov     edx, ebx; SizeInWords
0x18002080a  call    cs:__imp_wcscpy_s
0x180020810  lea     r8, aTemp_1; "\\TEMP\\"
0x180020817  mov     edx, ebx; SizeInWords
0x180020819  lea     rcx, [rsp+280h+Buffer]; Destination
0x18002081e  call    cs:__imp_wcscat_s
0x180020824  lea     rax, [rsp+280h+Buffer]
0x180020829  mov     [rbp+180h+var_48], r14w
0x180020831  mov     r8, rsi
0x180020834  inc     r8; MaxCount
0x180020837  cmp     [rax+r8*2], r14w
0x18002083c  jnz     short loc_180020834
0x18002083e  lea     rdx, [rsp+280h+Buffer]; String2
0x180020843  mov     rcx, r12; String1
0x180020846  call    _wcsnicmp_0
0x18002084b  test    eax, eax
0x18002084d  jz      loc_180020A19
0x180020853  mov     rbx, cs:Src
0x18002085a  test    rbx, rbx
0x18002085d  jz      loc_1800209C2
0x180020863  mov     r8, rbx; Source
0x180020866  lea     rcx, [rsp+280h+Buffer]; Destination
0x18002086b  mov     edx, 105h; SizeInWords
0x180020870  call    cs:__imp_wcscpy_s
0x180020876  lea     r8, aTemp_1; "\\TEMP\\"
0x18002087d  mov     edx, 103h; SizeInWords
0x180020882  lea     rcx, [rsp+280h+Destination]; Destination
0x180020887  call    cs:__imp_wcscpy_s
0x18002088d  lea     rax, [rsp+280h+Buffer]
0x180020892  mov     [rbp+180h+var_48], r14w
0x18002089a  mov     r8, rsi
0x18002089d  inc     r8; MaxCount
0x1800208a0  cmp     [rax+r8*2], r14w
0x1800208a5  jnz     short loc_18002089D
0x1800208a7  lea     rdx, [rsp+280h+Buffer]; String2
0x1800208ac  mov     rcx, r12; String1
0x1800208af  call    _wcsnicmp_0
0x1800208b4  test    eax, eax
0x1800208b6  jz      loc_180020A19
0x1800208bc  xor     edx, edx; hFile
0x1800208be  lea     rcx, aKernelbase; "KernelBase"
0x1800208c5  mov     r8d, 800h; dwFlags
0x1800208cb  call    cs:__imp_LoadLibraryExW
0x1800208d1  mov     rbx, rax
0x1800208d4  test    rax, rax
0x1800208d7  jz      short loc_18002093A
0x1800208d9  lea     rdx, aGettemppath2w_0; "GetTempPath2W"
0x1800208e0  mov     rcx, rax; hModule
0x1800208e3  call    cs:__imp_GetProcAddress
0x1800208e9  test    rax, rax
0x1800208ec  jz      short loc_180020931
0x1800208ee  lea     rdx, [rsp+280h+Buffer]
0x1800208f3  mov     ecx, 105h
0x1800208f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208fd  dec     eax
0x1800208ff  cmp     eax, 103h
0x180020904  ja      loc_180020A2D
0x18002090a  lea     rax, [rsp+280h+Buffer]
0x18002090f  inc     rsi
0x180020912  cmp     [rax+rsi*2], r14w
0x180020917  jnz     short loc_18002090F
0x180020919  mov     r8, rsi; MaxCount
0x18002091c  lea     rdx, [rsp+280h+Buffer]; String2
0x180020921  mov     rcx, r12; String1
0x180020924  call    _wcsnicmp_0
0x180020929  test    eax, eax
0x18002092b  jz      loc_180020A23
0x180020931  mov     rcx, rbx; hLibModule
0x180020934  call    cs:__imp_FreeLibrary
0x18002093a  mov     [r13+0], edi
0x18002093e  mov     eax, r15d
0x180020941  mov     rcx, [rbp+180h+var_40]
0x180020948  xor     rcx, rsp; StackCookie
0x18002094b  call    __security_check_cookie
0x180020950  mov     rbx, [rsp+280h+arg_10]
0x180020958  add     rsp, 250h
0x18002095f  pop     r15
0x180020961  pop     r14
0x180020963  pop     r13
0x180020965  pop     r12
0x180020967  pop     rdi
0x180020968  pop     rsi
0x180020969  pop     rbp
0x18002096a  retn
0x18002096b  xor     edx, edx; hFile
0x18002096d  lea     rcx, ModuleName; "ntdll.dll"
0x180020974  mov     r8d, 800h; dwFlags
0x18002097a  mov     ebx, 7FFE0030h
0x18002097f  call    cs:__imp_LoadLibraryExW
0x180020985  mov     r14, rax
0x180020988  test    rax, rax
0x18002098b  jz      short loc_1800209B3
0x18002098d  lea     rdx, ProcName; "RtlGetNtSystemRoot"
0x180020994  mov     rcx, rax; hModule
0x180020997  call    cs:__imp_GetProcAddress
0x18002099d  test    rax, rax
0x1800209a0  jz      short loc_1800209AA
0x1800209a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209a7  mov     rbx, rax
0x1800209aa  mov     rcx, r14; hLibModule
0x1800209ad  call    cs:__imp_FreeLibrary
0x1800209b3  mov     cs:Src, rbx
0x1800209ba  xor     r14d, r14d
0x1800209bd  jmp     loc_1800207FB
0x1800209c2  xor     edx, edx; hFile
0x1800209c4  lea     rcx, ModuleName; "ntdll.dll"
0x1800209cb  mov     r8d, 800h; dwFlags
0x1800209d1  mov     ebx, 7FFE0030h
0x1800209d6  call    cs:__imp_LoadLibraryExW
0x1800209dc  mov     r14, rax
0x1800209df  test    rax, rax
0x1800209e2  jz      short loc_180020A0A
0x1800209e4  lea     rdx, ProcName; "RtlGetNtSystemRoot"
0x1800209eb  mov     rcx, rax; hModule
0x1800209ee  call    cs:__imp_GetProcAddress
0x1800209f4  test    rax, rax
0x1800209f7  jz      short loc_180020A01
0x1800209f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209fe  mov     rbx, rax
0x180020a01  mov     rcx, r14; hLibModule
0x180020a04  call    cs:__imp_FreeLibrary
0x180020a0a  mov     cs:Src, rbx
0x180020a11  xor     r14d, r14d
0x180020a14  jmp     loc_180020863
0x180020a19  mov     edi, 1
0x180020a1e  jmp     loc_18002093A
0x180020a23  mov     edi, 1
0x180020a28  jmp     loc_180020931
0x180020a2d  mov     eax, 0C0000023h
0x180020a32  lea     r9, aFailedToRetrie; "Failed to retrieve temporary directory "...
0x180020a39  mov     r8d, 28Dh
0x180020a3f  mov     [rsp+280h+var_260], eax
0x180020a43  lea     rdx, aAslpathistempo_1; "AslPathIsTemporaryDirectory"
0x180020a4a  mov     ecx, 1
0x180020a4f  mov     r15d, eax
0x180020a52  call    AslLogCallPrintf
0x180020a57  jmp     loc_180020931
0x180020a5c  mov     eax, 0C0000023h
0x180020a61  lea     r9, aFailedToRetrie; "Failed to retrieve temporary directory "...
0x180020a68  mov     r8d, 25Fh
0x180020a6e  mov     [rsp+280h+var_260], eax
0x180020a72  lea     rdx, aAslpathistempo_1; "AslPathIsTemporaryDirectory"
0x180020a79  mov     ecx, 1
0x180020a7e  mov     r15d, eax
0x180020a81  call    AslLogCallPrintf
0x180020a86  jmp     loc_18002093A
```
