# OROpenHiveInternal

- ea: `0x1800a2494`
- end: `0x1800a2686`
- name: `OROpenHiveInternal`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005b580`

## callees

- `0x180006036`
- `0x180006042`
- `0x1800a2404`
- `0x1800a2494`
- `0x1800a402c`
- `0x1800a5284`
- `0x1800a6580`
- `0x1800a65c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2610`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2610`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a25e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a25e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a252c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a259d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a25f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a252c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a259d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a25f2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a258d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a258d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a251c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a251c`

## string_xrefs

- `0x1800a25d4`: `ntdll.dll`
- `0x1800a2606`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE v4; // r14
  HANDLE v5; // rsi
  char v6; // r15
  DWORD LastError; // edi
  DWORD v10; // eax
  void *v11; // rax
  HMODULE ModuleHandleW; // rax
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+50h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  FileSize.QuadPart = 0;
  *(_QWORD *)a4 = 0;
  hFile = 0;
  if ( !a2 )
  {
    LastError = 87;
    goto LABEL_23;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    v10 = ORCreateFile(a2, 1, 3, 1, &hFile);
    v4 = hFile;
    LastError = v10;
    if ( !v10 )
    {
      v6 = 1;
      if ( !GetFileSizeEx(hFile, &FileSize) )
        LastError = GetLastError();
      if ( !LastError )
      {
        if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
        {
          LastError = 1009;
          goto LABEL_23;
        }
        v11 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
        hFile = v11;
        v5 = v11;
        if ( !v11 )
        {
          LastError = 8;
          goto LABEL_23;
        }
        LastError = 0;
        if ( !ReadFile(v4, v11, FileSize.LowPart, &NumberOfBytesRead, 0) )
          LastError = GetLastError();
        if ( !LastError )
        {
          LastError = ValidateHiveAndRecoverFromLog(&hFile, &FileSize, a2, v4);
          if ( !LastError )
          {
            ORCloseFile(v4);
            v4 = 0;
            v6 = 0;
            ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
            if ( ModuleHandleW )
            {
              ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                             ModuleHandleW,
                                                             "RtlValidRelativeSecurityDescriptor");
              if ( ORValidRelativeSecurityDescriptor )
              {
                v5 = 0;
                LastError = OROpenHiveFromMemoryInternal(hFile);
                if ( !LastError )
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = 0;
                goto LABEL_23;
              }
            }
            LastError = GetLastError();
          }
          v5 = hFile;
        }
      }
    }
  }
LABEL_23:
  if ( v5 )
    aligned_free(v5);
  if ( v6 )
    ORCloseFile(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800a2494  mov     [rsp-38h+NumberOfBytesRead], r8d
0x1800a2499  mov     qword ptr [rsp-38h+FileSize], rcx
0x1800a249e  push    rbp
0x1800a249f  push    rsi
0x1800a24a0  push    rdi
0x1800a24a1  push    r12
0x1800a24a3  push    r13
0x1800a24a5  push    r14
0x1800a24a7  push    r15
0x1800a24a9  mov     rbp, rsp
0x1800a24ac  sub     rsp, 30h
0x1800a24b0  xor     r14d, r14d
0x1800a24b3  xor     esi, esi
0x1800a24b5  and     [rbp+NumberOfBytesRead], r14d
0x1800a24b9  xor     r15b, r15b
0x1800a24bc  and     qword ptr [rbp+FileSize], r14
0x1800a24c0  mov     r13, r9
0x1800a24c3  and     [r9], rsi
0x1800a24c6  mov     r12, rdx
0x1800a24c9  mov     [rbp+hFile], r14
0x1800a24cd  test    rdx, rdx
0x1800a24d0  jnz     short loc_1800A24DA
0x1800a24d2  lea     edi, [rdx+57h]
0x1800a24d5  jmp     loc_1800A2659
0x1800a24da  call    ORStart
0x1800a24df  mov     edi, eax
0x1800a24e1  test    eax, eax
0x1800a24e3  jnz     loc_1800A2659
0x1800a24e9  lea     edx, [rdi+1]
0x1800a24ec  mov     rcx, r12
0x1800a24ef  lea     rax, [rbp+hFile]
0x1800a24f3  mov     r9d, edx
0x1800a24f6  lea     r8d, [rdi+3]
0x1800a24fa  mov     [rsp+30h+lpOverlapped], rax; lpOverlapped
0x1800a24ff  call    ORCreateFile
0x1800a2504  mov     r14, [rbp+hFile]
0x1800a2508  mov     edi, eax
0x1800a250a  test    eax, eax
0x1800a250c  jnz     loc_1800A2659
0x1800a2512  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800a2516  mov     rcx, r14; hFile
0x1800a2519  mov     r15b, 1
0x1800a251c  call    cs:__imp_GetFileSizeEx
0x1800a2523  nop     dword ptr [rax+rax+00h]
0x1800a2528  test    eax, eax
0x1800a252a  jnz     short loc_1800A253A
0x1800a252c  call    cs:__imp_GetLastError
0x1800a2533  nop     dword ptr [rax+rax+00h]
0x1800a2538  mov     edi, eax
0x1800a253a  test    edi, edi
0x1800a253c  jnz     loc_1800A2659
0x1800a2542  cmp     dword ptr [rbp+FileSize], 1000h
0x1800a2549  jbe     loc_1800A2654
0x1800a254f  cmp     dword ptr [rbp+FileSize+4], esi
0x1800a2552  jnz     loc_1800A2654
0x1800a2558  mov     rcx, qword ptr [rbp+FileSize]; Size
0x1800a255c  lea     edx, [rdi+10h]; Alignment
0x1800a255f  call    _o__aligned_malloc_0
0x1800a2564  mov     [rbp+hFile], rax
0x1800a2568  mov     rsi, rax
0x1800a256b  test    rax, rax
0x1800a256e  jnz     short loc_1800A2578
0x1800a2570  lea     edi, [rax+8]
0x1800a2573  jmp     loc_1800A2659
0x1800a2578  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x1800a257c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a2580  xor     edi, edi
0x1800a2582  mov     rdx, rax; lpBuffer
0x1800a2585  and     [rsp+30h+lpOverlapped], rdi
0x1800a258a  mov     rcx, r14; hFile
0x1800a258d  call    cs:__imp_ReadFile
0x1800a2594  nop     dword ptr [rax+rax+00h]
0x1800a2599  test    eax, eax
0x1800a259b  jnz     short loc_1800A25AB
0x1800a259d  call    cs:__imp_GetLastError
0x1800a25a4  nop     dword ptr [rax+rax+00h]
0x1800a25a9  mov     edi, eax
0x1800a25ab  test    edi, edi
0x1800a25ad  jnz     loc_1800A2659
0x1800a25b3  mov     r9, r14
0x1800a25b6  lea     rdx, [rbp+FileSize]
0x1800a25ba  mov     r8, r12
0x1800a25bd  lea     rcx, [rbp+hFile]
0x1800a25c1  call    ValidateHiveAndRecoverFromLog
0x1800a25c6  mov     edi, eax
0x1800a25c8  test    eax, eax
0x1800a25ca  jnz     short loc_1800A2600
0x1800a25cc  mov     rcx, r14
0x1800a25cf  call    ORCloseFile
0x1800a25d4  lea     rcx, ModuleName; "ntdll.dll"
0x1800a25db  xor     r14d, r14d
0x1800a25de  xor     r15b, r15b
0x1800a25e1  call    cs:__imp_GetModuleHandleW
0x1800a25e8  nop     dword ptr [rax+rax+00h]
0x1800a25ed  test    rax, rax
0x1800a25f0  jnz     short loc_1800A2606
0x1800a25f2  call    cs:__imp_GetLastError
0x1800a25f9  nop     dword ptr [rax+rax+00h]
0x1800a25fe  mov     edi, eax
0x1800a2600  mov     rsi, [rbp+hFile]
0x1800a2604  jmp     short loc_1800A2659
0x1800a2606  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x1800a260d  mov     rcx, rax; hModule
0x1800a2610  call    cs:__imp_GetProcAddress
0x1800a2617  nop     dword ptr [rax+rax+00h]
0x1800a261c  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x1800a2623  test    rax, rax
0x1800a2626  jz      short loc_1800A25F2
0x1800a2628  mov     rdx, qword ptr [rbp+FileSize]
0x1800a262c  mov     r9, r13
0x1800a262f  mov     rcx, [rbp+hFile]; Block
0x1800a2633  mov     r8, r12
0x1800a2636  call    OROpenHiveFromMemoryInternal
0x1800a263b  xor     esi, esi
0x1800a263d  mov     edi, eax
0x1800a263f  test    eax, eax
0x1800a2641  jnz     short loc_1800A2659
0x1800a2643  mov     rax, [r13+0]
0x1800a2647  mov     rcx, [rax+10h]
0x1800a264b  and     [rcx+80h], rsi
0x1800a2652  jmp     short loc_1800A2659
0x1800a2654  mov     edi, 3F1h
0x1800a2659  test    rsi, rsi
0x1800a265c  jz      short loc_1800A2666
0x1800a265e  mov     rcx, rsi; Block
0x1800a2661  call    _aligned_free
0x1800a2666  test    r15b, r15b
0x1800a2669  jz      short loc_1800A2673
0x1800a266b  mov     rcx, r14
0x1800a266e  call    ORCloseFile
0x1800a2673  mov     eax, edi
0x1800a2675  add     rsp, 30h
0x1800a2679  pop     r15
0x1800a267b  pop     r14
0x1800a267d  pop     r13
0x1800a267f  pop     r12
0x1800a2681  pop     rdi
0x1800a2682  pop     rsi
0x1800a2683  pop     rbp
0x1800a2684  retn
```
