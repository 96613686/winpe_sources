# GetProcessVersionString(ushort *,int)

- ea: `0x18003c2bc`
- end: `0x18003c4c0`
- name: `?GetProcessVersionString@@YAHPEAGH@Z`
- size: `516`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003c678`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dcec`
- `0x18003c2bc`
- `0x180116010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003c3f0`
- `ntdll!RtlAllocateHeap` at `0x18003c3f0`
- `ntdll!RtlFreeHeap` at `0x18003c495`
- `ntdll!RtlFreeHeap` at `0x18003c495`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c324`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c324`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c47c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c47c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c35f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c37b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c35f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c37b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c3e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c487`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c3e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c38d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c38d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003c3a2`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18003c3a2`

## string_xrefs

- `0x18003c319`: `version.dll`

## pseudocode

```c
HMODULE __fastcall GetProcessVersionString(unsigned __int16 *a1)
{
  unsigned int v2; // esi
  HMODULE result; // rax
  HMODULE v4; // rdi
  void *v5; // rbx
  FARPROC ProcAddress; // r15
  FARPROC v7; // r14
  FARPROC v8; // r12
  HANDLE CurrentProcess; // rax
  unsigned int v10; // eax
  SIZE_T v11; // r14
  int v12; // eax
  HANDLE ProcessHeap; // rax
  PVOID Heap; // rax
  HANDLE v15; // rax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h]
  DWORD dwSize; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ExeName[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(ExeName, 0, 0x20Au);
  v2 = 0;
  dwSize = 260;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  result = LoadLibraryExW(L"version.dll", 0, 0x800u);
  v4 = result;
  if ( !result )
    return result;
  v5 = 0;
  ProcAddress = GetProcAddress(result, "GetFileVersionInfoW");
  if ( ProcAddress )
  {
    v7 = GetProcAddress(v4, "GetFileVersionInfoSizeW");
    if ( v7 )
    {
      v8 = GetProcAddress(v4, "VerQueryValueW");
      if ( v8 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
        {
          v10 = ((__int64 (__fastcall *)(WCHAR *, int *))v7)(ExeName, &v20);
          v11 = v10;
          if ( !v10 )
          {
            v12 = StringCchPrintfW(a1, 0xC8u, L"0.0.0.0");
            goto LABEL_12;
          }
          ProcessHeap = GetProcessHeap();
          Heap = RtlAllocateHeap(ProcessHeap, 0, v11);
          v5 = Heap;
          if ( Heap
            && ((unsigned int (__fastcall *)(WCHAR *, _QWORD, _QWORD, PVOID))ProcAddress)(
                 ExeName,
                 0,
                 (unsigned int)v11,
                 Heap)
            && ((unsigned int (__fastcall *)(void *, const WCHAR *, unsigned __int16 **, int *))v8)(
                 v5,
                 L"\\",
                 &v22,
                 &v21) )
          {
            v18 = v22[6];
            v17 = v22[7];
            v16 = v22[4];
            v12 = StringCchPrintfW(a1, 0xC8u, L"%u.%u.%u.%u", v22[5], v16, v17, v18);
LABEL_12:
            if ( v12 >= 0 )
              v2 = 1;
          }
        }
      }
    }
  }
  FreeLibrary(v4);
  if ( v5 )
  {
    v15 = GetProcessHeap();
    RtlFreeHeap(v15, 0, v5);
  }
  return (HMODULE)v2;
}

```

## disassembly

```asm
0x18003c2bc  push    rbp
0x18003c2be  push    rbx
0x18003c2bf  push    rsi
0x18003c2c0  push    rdi
0x18003c2c1  push    r12
0x18003c2c3  push    r13
0x18003c2c5  push    r14
0x18003c2c7  push    r15
0x18003c2c9  lea     rbp, [rsp-188h]
0x18003c2d1  sub     rsp, 288h
0x18003c2d8  mov     rax, cs:__security_cookie
0x18003c2df  xor     rax, rsp
0x18003c2e2  mov     [rbp+1C0h+var_50], rax
0x18003c2e9  mov     r13, rcx
0x18003c2ec  xor     edx, edx; Val
0x18003c2ee  lea     rcx, [rsp+2C0h+ExeName]; void *
0x18003c2f3  mov     r8d, 20Ah; Size
0x18003c2f9  call    memset_0
0x18003c2fe  xor     esi, esi
0x18003c300  mov     [rsp+2C0h+dwSize], 104h
0x18003c308  xor     edx, edx; hFile
0x18003c30a  mov     [rsp+2C0h+var_270], rsi
0x18003c30f  mov     r8d, 800h; dwFlags
0x18003c315  mov     [rsp+2C0h+var_27C], esi
0x18003c319  lea     rcx, aVersionDll; "version.dll"
0x18003c320  mov     [rsp+2C0h+var_278], esi
0x18003c324  call    cs:__imp_LoadLibraryExW
0x18003c32a  mov     rdi, rax
0x18003c32d  test    rax, rax
0x18003c330  jz      loc_18003C49D
0x18003c336  lea     rdx, aGetfileversion_1; "GetFileVersionInfoW"
0x18003c33d  mov     rcx, rdi; hModule
0x18003c340  mov     rbx, rsi
0x18003c343  call    cs:__imp_GetProcAddress
0x18003c349  mov     r15, rax
0x18003c34c  test    rax, rax
0x18003c34f  jz      loc_18003C479
0x18003c355  lea     rdx, aGetfileversion; "GetFileVersionInfoSizeW"
0x18003c35c  mov     rcx, rdi; hModule
0x18003c35f  call    cs:__imp_GetProcAddress
0x18003c365  mov     r14, rax
0x18003c368  test    rax, rax
0x18003c36b  jz      loc_18003C479
0x18003c371  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x18003c378  mov     rcx, rdi; hModule
0x18003c37b  call    cs:__imp_GetProcAddress
0x18003c381  mov     r12, rax
0x18003c384  test    rax, rax
0x18003c387  jz      loc_18003C479
0x18003c38d  call    cs:__imp_GetCurrentProcess
0x18003c393  lea     r9, [rsp+2C0h+dwSize]; lpdwSize
0x18003c398  xor     edx, edx; dwFlags
0x18003c39a  mov     rcx, rax; hProcess
0x18003c39d  lea     r8, [rsp+2C0h+ExeName]; lpExeName
0x18003c3a2  call    cs:__imp_QueryFullProcessImageNameW
0x18003c3a8  test    eax, eax
0x18003c3aa  jz      loc_18003C479
0x18003c3b0  lea     rdx, [rsp+2C0h+var_27C]
0x18003c3b5  mov     rax, r14
0x18003c3b8  lea     rcx, [rsp+2C0h+ExeName]
0x18003c3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3c2  mov     r14d, eax
0x18003c3c5  test    eax, eax
0x18003c3c7  jnz     short loc_18003C3E2
0x18003c3c9  lea     r8, a0000; "0.0.0.0"
0x18003c3d0  mov     edx, 0C8h; unsigned __int64
0x18003c3d5  mov     rcx, r13; unsigned __int16 *
0x18003c3d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c3dd  jmp     loc_18003C470
0x18003c3e2  call    cs:__imp_GetProcessHeap
0x18003c3e8  mov     r8, r14; Size
0x18003c3eb  xor     edx, edx; Flags
0x18003c3ed  mov     rcx, rax; HeapHandle
0x18003c3f0  call    cs:__imp_RtlAllocateHeap
0x18003c3f6  mov     rbx, rax
0x18003c3f9  test    rax, rax
0x18003c3fc  jz      short loc_18003C479
0x18003c3fe  mov     r9, rax
0x18003c401  lea     rcx, [rsp+2C0h+ExeName]
0x18003c406  mov     rax, r15
0x18003c409  mov     r8d, r14d
0x18003c40c  xor     edx, edx
0x18003c40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c413  test    eax, eax
0x18003c415  jz      short loc_18003C479
0x18003c417  lea     r9, [rsp+2C0h+var_278]
0x18003c41c  mov     rcx, rbx
0x18003c41f  lea     r8, [rsp+2C0h+var_270]
0x18003c424  mov     rax, r12
0x18003c427  lea     rdx, SubBlock; "\\"
0x18003c42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c433  test    eax, eax
0x18003c435  jz      short loc_18003C479
0x18003c437  mov     r8, [rsp+2C0h+var_270]
0x18003c43c  movzx   ecx, word ptr [r8+0Eh]
0x18003c441  movzx   edx, word ptr [r8+8]
0x18003c446  movzx   eax, word ptr [r8+0Ch]
0x18003c44b  movzx   r9d, word ptr [r8+0Ah]
0x18003c450  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18003c457  mov     [rsp+2C0h+var_290], eax
0x18003c45b  mov     [rsp+2C0h+var_298], ecx
0x18003c45f  mov     rcx, r13; unsigned __int16 *
0x18003c462  mov     [rsp+2C0h+var_2A0], edx
0x18003c466  mov     edx, 0C8h; unsigned __int64
0x18003c46b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c470  test    eax, eax
0x18003c472  js      short loc_18003C479
0x18003c474  mov     esi, 1
0x18003c479  mov     rcx, rdi; hLibModule
0x18003c47c  call    cs:__imp_FreeLibrary
0x18003c482  test    rbx, rbx
0x18003c485  jz      short loc_18003C49B
0x18003c487  call    cs:__imp_GetProcessHeap
0x18003c48d  mov     r8, rbx; P
0x18003c490  xor     edx, edx; Flags
0x18003c492  mov     rcx, rax; HeapHandle
0x18003c495  call    cs:__imp_RtlFreeHeap
0x18003c49b  mov     eax, esi
0x18003c49d  mov     rcx, [rbp+1C0h+var_50]
0x18003c4a4  xor     rcx, rsp; StackCookie
0x18003c4a7  call    __security_check_cookie
0x18003c4ac  add     rsp, 288h
0x18003c4b3  pop     r15
0x18003c4b5  pop     r14
0x18003c4b7  pop     r13
0x18003c4b9  pop     r12
0x18003c4bb  pop     rdi
0x18003c4bc  pop     rsi
0x18003c4bd  pop     rbx
0x18003c4be  pop     rbp
0x18003c4bf  retn
```
