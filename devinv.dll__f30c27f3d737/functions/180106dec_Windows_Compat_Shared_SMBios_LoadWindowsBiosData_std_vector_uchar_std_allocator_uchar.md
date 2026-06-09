# Windows::Compat::Shared::SMBios::LoadWindowsBiosData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180106dec`
- end: `0x180107046`
- name: `?LoadWindowsBiosData@SMBios@Shared@Compat@Windows@@YAHAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b560`

## callees

- `0x180006eb8`
- `0x180006ec4`
- `0x180066c10`
- `0x180106be0`
- `0x180106dec`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180106e14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180106e14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180107027`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180107027`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106e5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106e5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180107018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180107018`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180106ef2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180106ef2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180106ee4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010700a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180106ee4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010700a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106f42`

## string_xrefs

- `0x180106e0d`: `kernel32.dll`
- `0x180106e3c`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180106e80`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180106eca`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180106f13`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180106f59`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180106ff5`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Shared::SMBios::LoadWindowsBiosData(void **a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD LastError; // eax
  unsigned int v5; // esi
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD); // rdi
  DWORD v8; // eax
  unsigned int v9; // eax
  SIZE_T v10; // rsi
  DWORD v11; // eax
  size_t v12; // rbp
  HANDLE ProcessHeap; // rax
  char *v14; // rax
  char *v15; // r15
  DWORD v16; // eax
  char *v17; // rdx
  char *v18; // r12
  size_t v19; // rcx
  char *v20; // rax
  size_t v21; // rdi
  HANDLE v22; // rax

  Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
  v3 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
      23,
      "Failed to load kernel32 [%d]",
      LastError);
    v5 = 22;
    goto LABEL_23;
  }
  ProcAddress = GetProcAddress(Library, "GetSystemFirmwareTable");
  v7 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
  {
    v8 = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
      37,
      "Failed to find GetSystemFirmwareTable [%d]",
      v8);
    v5 = 40;
    goto LABEL_23;
  }
  v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1381190978, 0, 0, 0);
  v10 = v9;
  if ( !v9 )
  {
    v11 = GetLastError();
    v5 = 1;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
      45,
      "Failed to call GetSystemFirmwareTable [%d]",
      v11);
    goto LABEL_23;
  }
  v12 = v9;
  ProcessHeap = GetProcessHeap();
  v14 = (char *)HeapAlloc(ProcessHeap, 0, v10);
  v15 = v14;
  if ( !v14 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
      53,
      "Failed to allocate memory [%#x]",
      -2147024882);
    v5 = 12;
    goto LABEL_23;
  }
  if ( (_DWORD)v10 == v7(1381190978, 0, v14, (unsigned int)v10) )
  {
    if ( v15[v10 - 2] || v15[v10 - 1] )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
        78,
        "SMBIOS table is corrupt and does not end in double null [%#x]",
        -2147024809);
      v5 = 42;
      goto LABEL_22;
    }
    v5 = 0;
    v17 = (char *)*a1;
    v18 = (char *)a1[1];
    v19 = v18 - (_BYTE *)*a1;
    if ( v12 < v19 )
    {
      v20 = &v17[v12];
LABEL_19:
      a1[1] = v20;
      goto LABEL_20;
    }
    if ( v12 > v19 )
    {
      if ( v12 <= (_BYTE *)a1[2] - v17 )
      {
        v21 = v12 - v19;
        memset_0(a1[1], 0, v12 - v19);
        v20 = &v18[v21];
        goto LABEL_19;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1, v12);
    }
LABEL_20:
    memmove_0(*a1, v15, v12);
    goto LABEL_22;
  }
  v16 = GetLastError();
  v5 = 1;
  AslLogCallPrintf(
    1,
    "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
    60,
    "Failed to call GetSystemFirmwareTable [%d]",
    v16);
LABEL_22:
  v22 = GetProcessHeap();
  HeapFree(v22, 0, v15);
LABEL_23:
  if ( v3 )
    FreeLibrary(v3);
  return v5;
}

```

## disassembly

```asm
0x180106dec  mov     [rsp+arg_0], rbx
0x180106df1  mov     [rsp+arg_10], rbp
0x180106df6  push    rsi
0x180106df7  push    rdi
0x180106df8  push    r12
0x180106dfa  push    r14
0x180106dfc  push    r15
0x180106dfe  sub     rsp, 30h
0x180106e02  mov     r14, rcx
0x180106e05  xor     edx, edx; hFile
0x180106e07  mov     r8d, 800h; dwFlags
0x180106e0d  lea     rcx, SourceString; "kernel32.dll"
0x180106e14  call    cs:__imp_LoadLibraryExW
0x180106e1a  mov     rbx, rax
0x180106e1d  mov     [rsp+58h+arg_8], rax
0x180106e22  test    rax, rax
0x180106e25  jnz     short loc_180106E53
0x180106e27  call    cs:__imp_GetLastError
0x180106e2d  mov     [rsp+58h+var_38], eax
0x180106e31  lea     r9, aFailedToLoadKe; "Failed to load kernel32 [%d]"
0x180106e38  lea     r8d, [rbx+17h]
0x180106e3c  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106e43  lea     ecx, [rbx+1]
0x180106e46  call    AslLogCallPrintf
0x180106e4b  lea     esi, [rbx+16h]
0x180106e4e  jmp     loc_18010701F
0x180106e53  lea     rdx, aGetsystemfirmw; "GetSystemFirmwareTable"
0x180106e5a  mov     rcx, rbx; hModule
0x180106e5d  call    cs:__imp_GetProcAddress
0x180106e63  mov     rdi, rax
0x180106e66  test    rax, rax
0x180106e69  jnz     short loc_180106E97
0x180106e6b  call    cs:__imp_GetLastError
0x180106e71  mov     [rsp+58h+var_38], eax
0x180106e75  lea     r9, aFailedToFindGe; "Failed to find GetSystemFirmwareTable ["...
0x180106e7c  lea     r8d, [rdi+25h]
0x180106e80  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106e87  lea     ecx, [rdi+1]
0x180106e8a  call    AslLogCallPrintf
0x180106e8f  lea     esi, [rdi+28h]
0x180106e92  jmp     loc_18010701F
0x180106e97  xor     r9d, r9d
0x180106e9a  xor     r8d, r8d
0x180106e9d  xor     edx, edx
0x180106e9f  mov     r12d, 52534D42h
0x180106ea5  mov     ecx, r12d
0x180106ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106ead  mov     esi, eax
0x180106eaf  test    eax, eax
0x180106eb1  jnz     short loc_180106EE1
0x180106eb3  call    cs:__imp_GetLastError
0x180106eb9  mov     [rsp+58h+var_38], eax
0x180106ebd  lea     r9, aFailedToCallGe; "Failed to call GetSystemFirmwareTable ["...
0x180106ec4  mov     r8d, 2Dh ; '-'
0x180106eca  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106ed1  lea     esi, [r8-2Ch]
0x180106ed5  mov     ecx, esi
0x180106ed7  call    AslLogCallPrintf
0x180106edc  jmp     loc_18010701F
0x180106ee1  mov     rbp, rsi
0x180106ee4  call    cs:__imp_GetProcessHeap
0x180106eea  mov     rcx, rax; hHeap
0x180106eed  mov     r8, rsi; dwBytes
0x180106ef0  xor     edx, edx; dwFlags
0x180106ef2  call    cs:__imp_HeapAlloc
0x180106ef8  mov     r15, rax
0x180106efb  test    rax, rax
0x180106efe  jnz     short loc_180106F2B
0x180106f00  mov     [rsp+58h+var_38], 8007000Eh
0x180106f08  lea     r9, aFailedToAlloca_0; "Failed to allocate memory [%#x]"
0x180106f0f  lea     r8d, [rax+35h]
0x180106f13  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106f1a  lea     ecx, [rax+1]
0x180106f1d  call    AslLogCallPrintf
0x180106f22  lea     esi, [r15+0Ch]
0x180106f26  jmp     loc_18010701F
0x180106f2b  mov     r9d, esi
0x180106f2e  mov     r8, r15
0x180106f31  xor     edx, edx
0x180106f33  mov     ecx, r12d
0x180106f36  mov     rax, rdi
0x180106f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f3e  cmp     esi, eax
0x180106f40  jz      short loc_180106F70
0x180106f42  call    cs:__imp_GetLastError
0x180106f48  mov     [rsp+58h+var_38], eax
0x180106f4c  lea     r9, aFailedToCallGe; "Failed to call GetSystemFirmwareTable ["...
0x180106f53  mov     r8d, 3Ch ; '<'
0x180106f59  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106f60  lea     esi, [r8-3Bh]
0x180106f64  mov     ecx, esi
0x180106f66  call    AslLogCallPrintf
0x180106f6b  jmp     loc_18010700A
0x180106f70  cmp     byte ptr [r15+rsi-2], 0
0x180106f76  jnz     short loc_180106FE0
0x180106f78  cmp     byte ptr [r15+rsi-1], 0
0x180106f7e  jnz     short loc_180106FE0
0x180106f80  xor     esi, esi
0x180106f82  mov     rdx, [r14]
0x180106f85  mov     r12, [r14+8]
0x180106f89  mov     rcx, r12
0x180106f8c  sub     rcx, rdx
0x180106f8f  cmp     rbp, rcx
0x180106f92  jnb     short loc_180106F9A
0x180106f94  lea     rax, [rdx+rbp]
0x180106f98  jmp     short loc_180106FCC
0x180106f9a  jbe     short loc_180106FD0
0x180106f9c  mov     rax, [r14+10h]
0x180106fa0  sub     rax, rdx
0x180106fa3  cmp     rbp, rax
0x180106fa6  jbe     short loc_180106FB5
0x180106fa8  mov     rdx, rbp
0x180106fab  mov     rcx, r14
0x180106fae  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180106fb3  jmp     short loc_180106FD0
0x180106fb5  mov     rdi, rbp
0x180106fb8  sub     rdi, rcx
0x180106fbb  mov     r8, rdi; Size
0x180106fbe  xor     edx, edx; Val
0x180106fc0  mov     rcx, r12; void *
0x180106fc3  call    memset_0
0x180106fc8  lea     rax, [rdi+r12]
0x180106fcc  mov     [r14+8], rax
0x180106fd0  mov     r8, rbp; Size
0x180106fd3  mov     rdx, r15; Src
0x180106fd6  mov     rcx, [r14]; void *
0x180106fd9  call    memmove_0
0x180106fde  jmp     short loc_18010700A
0x180106fe0  mov     [rsp+58h+var_38], 80070057h
0x180106fe8  lea     r9, aSmbiosTableIsC; "SMBIOS table is corrupt and does not en"...
0x180106fef  mov     r8d, 4Eh ; 'N'
0x180106ff5  lea     rdx, aWindowsCompatS_2; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180106ffc  lea     ecx, [r8-4Dh]
0x180107000  call    AslLogCallPrintf
0x180107005  mov     esi, 2Ah ; '*'
0x18010700a  call    cs:__imp_GetProcessHeap
0x180107010  mov     rcx, rax; hHeap
0x180107013  mov     r8, r15; lpMem
0x180107016  xor     edx, edx; dwFlags
0x180107018  call    cs:__imp_HeapFree
0x18010701e  nop
0x18010701f  test    rbx, rbx
0x180107022  jz      short loc_18010702D
0x180107024  mov     rcx, rbx; hLibModule
0x180107027  call    cs:__imp_FreeLibrary
0x18010702d  mov     eax, esi
0x18010702f  mov     rbx, [rsp+58h+arg_0]
0x180107034  mov     rbp, [rsp+58h+arg_10]
0x180107039  add     rsp, 30h
0x18010703d  pop     r15
0x18010703f  pop     r14
0x180107041  pop     r12
0x180107043  pop     rdi
0x180107044  pop     rsi
0x180107045  retn
```
