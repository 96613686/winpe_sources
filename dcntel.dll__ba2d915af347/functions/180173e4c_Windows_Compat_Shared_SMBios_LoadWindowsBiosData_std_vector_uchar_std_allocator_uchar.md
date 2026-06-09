# Windows::Compat::Shared::SMBios::LoadWindowsBiosData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180173e4c`
- end: `0x18017404b`
- name: `?LoadWindowsBiosData@SMBios@Shared@Compat@Windows@@YAHAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180173cb8`

## callees

- `0x180009f08`
- `0x180019640`
- `0x18016796c`
- `0x180173e4c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180173e6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180173e6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180174036`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180174036`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180173eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180173eb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180173f45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180173f45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180173f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180174019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180173f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180174019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180174027`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180174027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180173f97`

## string_xrefs

- `0x180173e64`: `kernel32.dll`
- `0x180173e93`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180173ed7`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180173f20`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180173f66`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180173fae`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`
- `0x180174004`: `Windows::Compat::Shared::SMBios::LoadWindowsBiosData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Shared::SMBios::LoadWindowsBiosData(void **a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD v4; // eax
  unsigned int v5; // edi
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD); // rdi
  DWORD v8; // eax
  unsigned int v9; // eax
  SIZE_T v10; // r14
  DWORD v11; // eax
  HANDLE ProcessHeap; // rax
  char *v13; // rax
  char *v14; // rsi
  DWORD LastError; // eax
  HANDLE v16; // rax

  Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetSystemFirmwareTable");
    v7 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1381190978, 0, 0, 0);
      v10 = v9;
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        v13 = (char *)HeapAlloc(ProcessHeap, 0, v10);
        v14 = v13;
        if ( v13 )
        {
          if ( (_DWORD)v10 == v7(1381190978, 0, v13, (unsigned int)v10) )
          {
            if ( v14[v10 - 2] || v14[v10 - 1] )
            {
              AslLogCallPrintf(
                1,
                "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
                78,
                "SMBIOS table is corrupt and does not end in double null [%#x]",
                -2147024809);
              v5 = 42;
            }
            else
            {
              v5 = 0;
              std::vector<unsigned char>::resize(a1, v10);
              memmove_0(*a1, v14, v10);
            }
          }
          else
          {
            LastError = GetLastError();
            v5 = 1;
            AslLogCallPrintf(
              1,
              "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
              60,
              "Failed to call GetSystemFirmwareTable [%d]",
              LastError);
          }
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v14);
        }
        else
        {
          AslLogCallPrintf(
            1,
            "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
            53,
            "Failed to allocate memory [%#x]",
            -2147024882);
          v5 = 12;
        }
      }
      else
      {
        v11 = GetLastError();
        v5 = 1;
        AslLogCallPrintf(
          1,
          "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
          45,
          "Failed to call GetSystemFirmwareTable [%d]",
          v11);
      }
    }
    else
    {
      v8 = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Shared::SMBios::LoadWindowsBiosData",
        37,
        "Failed to find GetSystemFirmwareTable [%d]",
        v8);
      v5 = 40;
    }
  }
  else
  {
    v4 = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Shared::SMBios::LoadWindowsBiosData", 23, "Failed to load kernel32 [%d]", v4);
    v5 = 22;
  }
  if ( v3 )
    FreeLibrary(v3);
  return v5;
}

```

## disassembly

```asm
0x180173e4c  push    rbx
0x180173e4e  push    rbp
0x180173e4f  push    rsi
0x180173e50  push    rdi
0x180173e51  push    r14
0x180173e53  push    r15
0x180173e55  sub     rsp, 38h
0x180173e59  mov     r15, rcx
0x180173e5c  xor     edx, edx; hFile
0x180173e5e  mov     r8d, 800h; dwFlags
0x180173e64  lea     rcx, SourceString; "kernel32.dll"
0x180173e6b  call    cs:__imp_LoadLibraryExW
0x180173e71  mov     rbx, rax
0x180173e74  mov     [rsp+68h+arg_8], rax
0x180173e79  test    rax, rax
0x180173e7c  jnz     short loc_180173EAA
0x180173e7e  call    cs:__imp_GetLastError
0x180173e84  mov     [rsp+68h+var_48], eax
0x180173e88  lea     r9, aFailedToLoadKe; "Failed to load kernel32 [%d]"
0x180173e8f  lea     r8d, [rbx+17h]
0x180173e93  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180173e9a  lea     ecx, [rbx+1]
0x180173e9d  call    AslLogCallPrintf
0x180173ea2  lea     edi, [rbx+16h]
0x180173ea5  jmp     loc_18017402E
0x180173eaa  lea     rdx, aGetsystemfirmw; "GetSystemFirmwareTable"
0x180173eb1  mov     rcx, rbx; hModule
0x180173eb4  call    cs:__imp_GetProcAddress
0x180173eba  mov     rdi, rax
0x180173ebd  test    rax, rax
0x180173ec0  jnz     short loc_180173EF0
0x180173ec2  call    cs:__imp_GetLastError
0x180173ec8  mov     [rsp+68h+var_48], eax
0x180173ecc  lea     r9, aFailedToFindGe; "Failed to find GetSystemFirmwareTable ["...
0x180173ed3  lea     r8d, [rdi+25h]
0x180173ed7  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180173ede  lea     ecx, [rdi+1]
0x180173ee1  call    AslLogCallPrintf
0x180173ee6  mov     edi, 28h ; '('
0x180173eeb  jmp     loc_18017402E
0x180173ef0  xor     r9d, r9d
0x180173ef3  xor     r8d, r8d
0x180173ef6  xor     edx, edx
0x180173ef8  mov     ecx, 52534D42h
0x180173efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173f02  mov     r14d, eax
0x180173f05  test    eax, eax
0x180173f07  jnz     short loc_180173F37
0x180173f09  call    cs:__imp_GetLastError
0x180173f0f  mov     [rsp+68h+var_48], eax
0x180173f13  lea     r9, aFailedToCallGe; "Failed to call GetSystemFirmwareTable ["...
0x180173f1a  mov     r8d, 2Dh ; '-'
0x180173f20  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180173f27  lea     edi, [r8-2Ch]
0x180173f2b  mov     ecx, edi
0x180173f2d  call    AslLogCallPrintf
0x180173f32  jmp     loc_18017402E
0x180173f37  call    cs:__imp_GetProcessHeap
0x180173f3d  mov     rcx, rax; hHeap
0x180173f40  mov     r8, r14; dwBytes
0x180173f43  xor     edx, edx; dwFlags
0x180173f45  call    cs:__imp_HeapAlloc
0x180173f4b  mov     rsi, rax
0x180173f4e  test    rax, rax
0x180173f51  jnz     short loc_180173F7D
0x180173f53  mov     [rsp+68h+var_48], 8007000Eh
0x180173f5b  lea     r9, aFailedToAlloca; "Failed to allocate memory [%#x]"
0x180173f62  lea     r8d, [rax+35h]
0x180173f66  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180173f6d  lea     ecx, [rax+1]
0x180173f70  call    AslLogCallPrintf
0x180173f75  lea     edi, [rsi+0Ch]
0x180173f78  jmp     loc_18017402E
0x180173f7d  mov     r9d, r14d
0x180173f80  mov     r8, rsi
0x180173f83  xor     edx, edx
0x180173f85  mov     ecx, 52534D42h
0x180173f8a  mov     rax, rdi
0x180173f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173f92  cmp     r14d, eax
0x180173f95  jz      short loc_180173FC2
0x180173f97  call    cs:__imp_GetLastError
0x180173f9d  mov     [rsp+68h+var_48], eax
0x180173fa1  lea     r9, aFailedToCallGe; "Failed to call GetSystemFirmwareTable ["...
0x180173fa8  mov     r8d, 3Ch ; '<'
0x180173fae  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x180173fb5  lea     edi, [r8-3Bh]
0x180173fb9  mov     ecx, edi
0x180173fbb  call    AslLogCallPrintf
0x180173fc0  jmp     short loc_180174019
0x180173fc2  cmp     byte ptr [rsi+r14-2], 0
0x180173fc8  jnz     short loc_180173FEF
0x180173fca  cmp     byte ptr [rsi+r14-1], 0
0x180173fd0  jnz     short loc_180173FEF
0x180173fd2  xor     edi, edi
0x180173fd4  mov     rdx, r14
0x180173fd7  mov     rcx, r15
0x180173fda  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180173fdf  mov     r8, r14; Size
0x180173fe2  mov     rdx, rsi; Src
0x180173fe5  mov     rcx, [r15]; void *
0x180173fe8  call    memmove_0
0x180173fed  jmp     short loc_180174019
0x180173fef  mov     [rsp+68h+var_48], 80070057h
0x180173ff7  lea     r9, aSmbiosTableIsC; "SMBIOS table is corrupt and does not en"...
0x180173ffe  mov     r8d, 4Eh ; 'N'
0x180174004  lea     rdx, aWindowsCompatS_4; "Windows::Compat::Shared::SMBios::LoadWi"...
0x18017400b  lea     ecx, [r8-4Dh]
0x18017400f  call    AslLogCallPrintf
0x180174014  mov     edi, 2Ah ; '*'
0x180174019  call    cs:__imp_GetProcessHeap
0x18017401f  mov     rcx, rax; hHeap
0x180174022  mov     r8, rsi; lpMem
0x180174025  xor     edx, edx; dwFlags
0x180174027  call    cs:__imp_HeapFree
0x18017402d  nop
0x18017402e  test    rbx, rbx
0x180174031  jz      short loc_18017403C
0x180174033  mov     rcx, rbx; hLibModule
0x180174036  call    cs:__imp_FreeLibrary
0x18017403c  mov     eax, edi
0x18017403e  add     rsp, 38h
0x180174042  pop     r15
0x180174044  pop     r14
0x180174046  pop     rdi
0x180174047  pop     rsi
0x180174048  pop     rbp
0x180174049  pop     rbx
0x18017404a  retn
```
