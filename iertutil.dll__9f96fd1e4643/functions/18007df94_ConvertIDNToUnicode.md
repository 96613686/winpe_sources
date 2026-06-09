# ConvertIDNToUnicode

- ea: `0x18007df94`
- end: `0x18007e0cf`
- name: `ConvertIDNToUnicode`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007e7d0`

## callees

- `0x180025c18`
- `0x18007df94`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dfd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e094`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e037`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e026`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e026`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007e077`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007e085`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007dfbe`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007dfbe`

## string_xrefs

- `0x18007dfb7`: `normaliz.dll`

## pseudocode

```c
__int64 __fastcall ConvertIDNToUnicode(__int64 a1, unsigned int a2, void **a3, _DWORD *a4)
{
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // rbp
  int v11; // eax
  SIZE_T v12; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  unsigned int v15; // edi
  unsigned int ErrorError; // eax
  void *v17; // rbx
  HANDLE v18; // rax
  signed int LastError; // eax

  if ( a2 )
  {
    LibraryA = LoadLibraryA("normaliz.dll");
    if ( LibraryA
      && (ProcAddress = GetProcAddress(LibraryA, "IdnToUnicode"),
          (v10 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress) != 0)
      && (v11 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))ProcAddress)(2, a1, a2), (*a4 = v11) != 0) )
    {
      v12 = 2LL * v11;
      if ( !is_mul_ok(v11, 2u) )
        v12 = -1;
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 8u, v12);
      *a3 = v14;
      if ( v14 )
      {
        v15 = 0;
        if ( !v10(2, a1, a2, v14, *a4) )
        {
          ErrorError = HRESULTFromLastErrorError();
          v17 = *a3;
          v15 = ErrorError;
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v17);
          *a3 = 0;
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    *a4 = 0;
    v15 = -2147024809;
    *a3 = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x18007df94  push    rbx
0x18007df96  push    rbp
0x18007df97  push    rsi
0x18007df98  push    rdi
0x18007df99  push    r12
0x18007df9b  push    r14
0x18007df9d  push    r15
0x18007df9f  sub     rsp, 30h
0x18007dfa3  mov     r14, r9
0x18007dfa6  mov     rsi, r8
0x18007dfa9  mov     r15d, edx
0x18007dfac  mov     r12, rcx
0x18007dfaf  test    edx, edx
0x18007dfb1  jz      loc_18007E0AB
0x18007dfb7  lea     rcx, aNormalizDll; "normaliz.dll"
0x18007dfbe  call    cs:__imp_LoadLibraryA
0x18007dfc4  test    rax, rax
0x18007dfc7  jz      loc_18007E094
0x18007dfcd  lea     rdx, aIdntounicode; "IdnToUnicode"
0x18007dfd4  mov     rcx, rax; hModule
0x18007dfd7  call    cs:__imp_GetProcAddress
0x18007dfdd  mov     rbp, rax
0x18007dfe0  test    rax, rax
0x18007dfe3  jz      loc_18007E094
0x18007dfe9  xor     r9d, r9d
0x18007dfec  mov     [rsp+68h+var_48], 0
0x18007dff4  mov     r8d, r15d
0x18007dff7  mov     rdx, r12
0x18007dffa  lea     ebx, [r9+2]
0x18007dffe  mov     ecx, ebx
0x18007e000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e005  mov     [r14], eax
0x18007e008  test    eax, eax
0x18007e00a  jz      loc_18007E094
0x18007e010  movsxd  rcx, eax
0x18007e013  mov     eax, ebx
0x18007e015  mul     rcx
0x18007e018  mov     rbx, rax
0x18007e01b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007e022  cmovb   rbx, rax
0x18007e026  call    cs:__imp_GetProcessHeap
0x18007e02c  mov     r8, rbx; dwBytes
0x18007e02f  mov     edx, 8; dwFlags
0x18007e034  mov     rcx, rax; hHeap
0x18007e037  call    cs:__imp_HeapAlloc
0x18007e03d  mov     [rsi], rax
0x18007e040  mov     r9, rax
0x18007e043  test    rax, rax
0x18007e046  jnz     short loc_18007E04F
0x18007e048  mov     edi, 8007000Eh
0x18007e04d  jmp     short loc_18007E0BE
0x18007e04f  mov     eax, [r14]
0x18007e052  xor     edi, edi
0x18007e054  mov     [rsp+68h+var_48], eax
0x18007e058  mov     r8d, r15d
0x18007e05b  mov     rdx, r12
0x18007e05e  mov     rax, rbp
0x18007e061  lea     ecx, [rdi+2]
0x18007e064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e069  test    eax, eax
0x18007e06b  jnz     short loc_18007E0BE
0x18007e06d  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18007e072  mov     rbx, [rsi]
0x18007e075  mov     edi, eax
0x18007e077  call    cs:__imp_GetProcessHeap
0x18007e07d  mov     r8, rbx; lpMem
0x18007e080  xor     edx, edx; dwFlags
0x18007e082  mov     rcx, rax; hHeap
0x18007e085  call    cs:__imp_HeapFree
0x18007e08b  mov     qword ptr [rsi], 0
0x18007e092  jmp     short loc_18007E0BE
0x18007e094  call    cs:__imp_GetLastError
0x18007e09a  mov     edi, eax
0x18007e09c  test    eax, eax
0x18007e09e  jle     short loc_18007E0BE
0x18007e0a0  movzx   edi, ax
0x18007e0a3  or      edi, 80070000h
0x18007e0a9  jmp     short loc_18007E0BE
0x18007e0ab  mov     dword ptr [r9], 0
0x18007e0b2  mov     edi, 80070057h
0x18007e0b7  mov     qword ptr [r8], 0
0x18007e0be  mov     eax, edi
0x18007e0c0  add     rsp, 30h
0x18007e0c4  pop     r15
0x18007e0c6  pop     r14
0x18007e0c8  pop     r12
0x18007e0ca  pop     rdi
0x18007e0cb  pop     rsi
0x18007e0cc  pop     rbp
0x18007e0cd  pop     rbx
0x18007e0ce  retn
```
