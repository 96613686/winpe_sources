# OpenCapture(ushort const *,void * *,ushort *,int)

- ea: `0x180041c20`
- end: `0x180041d40`
- name: `?OpenCapture@@YAHPEBGPEAPEAXPEAGH@Z`
- size: `288`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180041d50`

## callees

- `0x1800098b0`
- `0x18000b828`
- `0x180018eb0`
- `0x18003f390`
- `0x180041c20`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041ccc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041ccc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041d0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cdb`

## string_xrefs

- `0x180041cf2`: `StiCreateInstance`
- `0x180041cbf`: `sti.dll`

## pseudocode

```c
__int64 __fastcall OpenCapture(const unsigned __int16 *a1, unsigned __int16 ***a2, unsigned __int16 *a3)
{
  unsigned __int16 **v5; // rdi
  unsigned int v6; // edi
  signed int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rsi
  HMODULE ModuleHandleW; // rax

  v5 = (unsigned __int16 **)MemAlloc(24);
  if ( !v5 )
  {
    v6 = 0;
    v7 = -2147024882;
LABEL_8:
    SetLastErrorFromHRESULT((unsigned int)v7, 4319);
    return v6;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = (unsigned __int16 *)MemAlloc(2 * v9 + 2);
  *v5 = v10;
  if ( v10 )
  {
    do
      ++v8;
    while ( a1[v8] );
    v7 = StringCchCopyW(v10, v8 + 1, a1);
    if ( v7 >= 0 )
    {
      Library = LoadLibraryExW(gszStiDll, 0, 0x800u);
      v5[1] = (unsigned __int16 *)Library;
      if ( Library && (ProcAddress = GetProcAddress(Library, gszStiCreateInstance)) != 0 )
      {
        ModuleHandleW = GetModuleHandleW(0);
        v7 = ((__int64 (__fastcall *)(HMODULE, __int64, unsigned __int16 **, _QWORD))ProcAddress)(
               ModuleHandleW,
               16777218,
               v5 + 2,
               0);
        if ( v7 >= 0 )
        {
          *a2 = v5;
          return 1;
        }
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  CloseCapture(v5);
  v6 = 0;
  if ( v7 < 0 )
    goto LABEL_8;
  return v6;
}

```

## disassembly

```asm
0x180041c20  push    rbx
0x180041c22  push    rbp
0x180041c23  push    rsi
0x180041c24  push    rdi
0x180041c25  push    r14
0x180041c27  sub     rsp, 30h
0x180041c2b  mov     rsi, rcx
0x180041c2e  mov     r14, rdx
0x180041c31  mov     ecx, 18h
0x180041c36  call    MemAlloc
0x180041c3b  xor     ebp, ebp
0x180041c3d  mov     rdi, rax
0x180041c40  test    rax, rax
0x180041c43  jnz     short loc_180041C4E
0x180041c45  mov     edi, ebp
0x180041c47  mov     ebx, 8007000Eh
0x180041c4c  jmp     short loc_180041C86
0x180041c4e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180041c52  mov     rcx, rbx
0x180041c55  inc     rcx
0x180041c58  cmp     [rsi+rcx*2], bp
0x180041c5c  jnz     short loc_180041C55
0x180041c5e  lea     rcx, ds:2[rcx*2]
0x180041c66  call    MemAlloc
0x180041c6b  mov     [rdi], rax
0x180041c6e  test    rax, rax
0x180041c71  jnz     short loc_180041C9F
0x180041c73  mov     ebx, 8007000Eh
0x180041c78  mov     rcx, rdi; lpMem
0x180041c7b  call    ?CloseCapture@@YAHPEAX@Z; CloseCapture(void *)
0x180041c80  mov     edi, ebp
0x180041c82  test    ebx, ebx
0x180041c84  jns     short loc_180041C92
0x180041c86  mov     edx, 10DFh
0x180041c8b  mov     ecx, ebx
0x180041c8d  call    SetLastErrorFromHRESULT
0x180041c92  mov     eax, edi
0x180041c94  add     rsp, 30h
0x180041c98  pop     r14
0x180041c9a  pop     rdi
0x180041c9b  pop     rsi
0x180041c9c  pop     rbp
0x180041c9d  pop     rbx
0x180041c9e  retn
0x180041c9f  inc     rbx
0x180041ca2  cmp     [rsi+rbx*2], bp
0x180041ca6  jnz     short loc_180041C9F
0x180041ca8  lea     rdx, [rbx+1]; unsigned __int64
0x180041cac  mov     r8, rsi; unsigned __int16 *
0x180041caf  mov     rcx, rax; unsigned __int16 *
0x180041cb2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041cb7  mov     ebx, eax
0x180041cb9  test    eax, eax
0x180041cbb  js      short loc_180041C78
0x180041cbd  xor     edx, edx; hFile
0x180041cbf  lea     rcx, gszStiDll; "sti.dll"
0x180041cc6  mov     r8d, 800h; dwFlags
0x180041ccc  call    cs:__imp_LoadLibraryExW
0x180041cd2  mov     [rdi+8], rax
0x180041cd6  test    rax, rax
0x180041cd9  jnz     short loc_180041CF2
0x180041cdb  call    cs:__imp_GetLastError
0x180041ce1  mov     ebx, eax
0x180041ce3  test    eax, eax
0x180041ce5  jle     short loc_180041C78
0x180041ce7  movzx   ebx, ax
0x180041cea  or      ebx, 80070000h
0x180041cf0  jmp     short loc_180041C78
0x180041cf2  lea     rdx, gszStiCreateInstance; "StiCreateInstance"
0x180041cf9  mov     rcx, rax; hModule
0x180041cfc  call    cs:__imp_GetProcAddress
0x180041d02  mov     rsi, rax
0x180041d05  test    rax, rax
0x180041d08  jz      short loc_180041CDB
0x180041d0a  xor     ecx, ecx; lpModuleName
0x180041d0c  call    cs:__imp_GetModuleHandleW
0x180041d12  xor     r9d, r9d
0x180041d15  lea     r8, [rdi+10h]
0x180041d19  mov     rcx, rax
0x180041d1c  mov     edx, 1000002h
0x180041d21  mov     rax, rsi
0x180041d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d29  mov     ebx, eax
0x180041d2b  test    eax, eax
0x180041d2d  js      loc_180041C78
0x180041d33  mov     [r14], rdi
0x180041d36  mov     edi, 1
0x180041d3b  jmp     loc_180041C92
```
