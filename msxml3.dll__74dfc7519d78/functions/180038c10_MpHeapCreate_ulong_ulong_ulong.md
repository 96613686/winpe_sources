# MpHeapCreate(ulong,ulong,ulong)

- ea: `0x180038c10`
- end: `0x180038daa`
- name: `?MpHeapCreate@@YAPEAXKKK@Z`
- size: `410`
- prototype: `void *__fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180062aa4`

## callees

- `0x180038c10`
- `0x180038db0`
- `0x180060d74`
- `0x180062a08`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038cb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038cb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038c9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038cd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038cd5`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180038d12`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180038d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c3e`

## string_xrefs

- `0x180038c96`: `kernel32.dll`

## pseudocode

```c
_DWORD *__fastcall MpHeapCreate(__int64 a1, __int64 a2, int a3)
{
  DWORD v3; // ecx
  DWORD v5; // ebx
  unsigned int v6; // esi
  DWORD v7; // ebp
  FARPROC ProcAddress; // r15
  HMODULE ModuleHandleW; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  DWORD v12; // esi
  HANDLE v13; // rax
  void *v14; // r14
  __int64 v15; // r12
  _MP_HEAP_ENTRY *v16; // rcx
  DWORD LastError; // ebx
  int v18; // [rsp+70h] [rbp+18h] BYREF

  v18 = a3;
  if ( (g_dwMpHeapOptions & 0xBFFFFFFF) != 0 )
  {
    v3 = 87;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = g_dwMpHeapCount;
  v6 = g_dwMpHeapOptions | 1;
  v7 = g_dwMpHeapOptions & 0xEFFFFFF6 | 1;
  if ( g_dwMpHeapCount )
  {
    if ( g_dwMpHeapCount > 0x40 )
      v5 = 64;
  }
  else
  {
    if ( g_si.dwNumberOfProcessors >= 4 )
      v5 = g_si.dwNumberOfProcessors + 3;
    else
      v5 = 2 * g_si.dwNumberOfProcessors + 1;
    if ( v5 > 0x10 )
      v5 = 16;
  }
  ProcAddress = 0;
  if ( (g_dwMpHeapOptions & 0x40000000) != 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
      ProcAddress = GetProcAddress(ModuleHandleW, "HeapSetInformation");
  }
  v10 = HeapAlloc(g_hProcessHeap, 0, 9416LL * (v5 - 1) + 9432);
  v11 = v10;
  if ( !v10 )
  {
    v3 = 8;
    goto LABEL_3;
  }
  *v10 = 0;
  v10[1] = v6 & 0x10000008;
  v12 = 0;
  v10[2] = 0;
  while ( v12 < v5 )
  {
    v13 = HeapCreate(v7, 0, 0);
    v14 = v13;
    if ( !v13 )
      goto LABEL_26;
    if ( ProcAddress )
    {
      v18 = 2;
      ((void (__fastcall *)(HANDLE, _QWORD, int *, __int64))ProcAddress)(v13, 0, &v18, 4);
    }
    v15 = 2354LL * v12;
    v16 = (_MP_HEAP_ENTRY *)&v11[v15 + 4];
    if ( v16 )
      _MP_HEAP_ENTRY::_MP_HEAP_ENTRY(v16, v14);
    if ( (int)X_CRITICAL_SECTION::Initialize((X_CRITICAL_SECTION *)&v11[v15 + 2080]) < 0 )
    {
LABEL_26:
      LastError = GetLastError();
      MpHeapDestroy(v11);
      v3 = LastError;
      goto LABEL_3;
    }
    ++*v11;
    ++v12;
  }
  return v11;
}

```

## disassembly

```asm
0x180038c10  mov     [rsp+arg_0], rbx
0x180038c15  mov     [rsp+arg_8], rbp
0x180038c1a  mov     [rsp+arg_10], r8d
0x180038c1f  push    rsi
0x180038c20  push    rdi
0x180038c21  push    r12
0x180038c23  push    r14
0x180038c25  push    r15
0x180038c27  sub     rsp, 30h
0x180038c2b  mov     esi, cs:?g_dwMpHeapOptions@@3KA; ulong g_dwMpHeapOptions
0x180038c31  test    esi, 0BFFFFFFFh
0x180038c37  jz      short loc_180038C4B
0x180038c39  mov     ecx, 57h ; 'W'; dwErrCode
0x180038c3e  call    cs:__imp_SetLastError
0x180038c44  xor     eax, eax
0x180038c46  jmp     loc_180038D93
0x180038c4b  mov     ebx, cs:?g_dwMpHeapCount@@3KA; ulong g_dwMpHeapCount
0x180038c51  or      esi, 1
0x180038c54  mov     ebp, esi
0x180038c56  and     ebp, 0EFFFFFF7h
0x180038c5c  test    ebx, ebx
0x180038c5e  jnz     short loc_180038C83
0x180038c60  mov     ebx, cs:?g_si@@3U_SYSTEM_INFO@@A.dwNumberOfProcessors; _SYSTEM_INFO g_si ...
0x180038c66  cmp     ebx, 4
0x180038c69  jnb     short loc_180038C74
0x180038c6b  lea     ebx, ds:1[rbx*2]
0x180038c72  jmp     short loc_180038C77
0x180038c74  add     ebx, 3
0x180038c77  cmp     ebx, 10h
0x180038c7a  jbe     short loc_180038C8D
0x180038c7c  mov     ebx, 10h
0x180038c81  jmp     short loc_180038C8D
0x180038c83  mov     eax, 40h ; '@'
0x180038c88  cmp     ebx, eax
0x180038c8a  cmova   ebx, eax
0x180038c8d  xor     r15d, r15d
0x180038c90  bt      ebp, 1Eh
0x180038c94  jnb     short loc_180038CBB
0x180038c96  lea     rcx, ModuleName; "kernel32.dll"
0x180038c9d  call    cs:__imp_GetModuleHandleW
0x180038ca3  test    rax, rax
0x180038ca6  jz      short loc_180038CBB
0x180038ca8  lea     rdx, ProcName; "HeapSetInformation"
0x180038caf  mov     rcx, rax; hModule
0x180038cb2  call    cs:__imp_GetProcAddress
0x180038cb8  mov     r15, rax
0x180038cbb  mov     rcx, cs:g_hProcessHeap; hHeap
0x180038cc2  lea     edx, [rbx-1]
0x180038cc5  imul    r8, rdx, 24C8h
0x180038ccc  xor     edx, edx; dwFlags
0x180038cce  add     r8, 24D8h; dwBytes
0x180038cd5  call    cs:__imp_HeapAlloc
0x180038cdb  mov     rdi, rax
0x180038cde  test    rax, rax
0x180038ce1  jnz     short loc_180038CEB
0x180038ce3  lea     ecx, [rax+8]
0x180038ce6  jmp     loc_180038C3E
0x180038ceb  and     esi, 10000008h
0x180038cf1  mov     dword ptr [rax], 0
0x180038cf7  mov     [rax+4], esi
0x180038cfa  xor     esi, esi
0x180038cfc  mov     dword ptr [rax+8], 0
0x180038d03  cmp     esi, ebx
0x180038d05  jnb     loc_180038D90
0x180038d0b  xor     r8d, r8d; dwMaximumSize
0x180038d0e  xor     edx, edx; dwInitialSize
0x180038d10  mov     ecx, ebp; flOptions
0x180038d12  call    cs:__imp_HeapCreate
0x180038d18  mov     r14, rax
0x180038d1b  test    rax, rax
0x180038d1e  jz      short loc_180038D79
0x180038d20  test    r15, r15
0x180038d23  jz      short loc_180038D45
0x180038d25  mov     rcx, rax
0x180038d28  mov     [rsp+58h+arg_10], 2
0x180038d30  mov     rax, r15
0x180038d33  lea     r8, [rsp+58h+arg_10]
0x180038d38  mov     r9d, 4
0x180038d3e  xor     edx, edx
0x180038d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d45  mov     eax, esi
0x180038d47  imul    r12, rax, 24C8h
0x180038d4e  lea     rcx, [r12+10h]
0x180038d53  add     rcx, rdi; this
0x180038d56  jz      short loc_180038D60
0x180038d58  mov     rdx, r14; void *
0x180038d5b  call    ??0_MP_HEAP_ENTRY@@QEAA@PEAX@Z; _MP_HEAP_ENTRY::_MP_HEAP_ENTRY(void *)
0x180038d60  lea     rcx, [rdi+2080h]
0x180038d67  add     rcx, r12; this
0x180038d6a  call    ?Initialize@X_CRITICAL_SECTION@@QEAAJXZ; X_CRITICAL_SECTION::Initialize(void)
0x180038d6f  test    eax, eax
0x180038d71  js      short loc_180038D79
0x180038d73  inc     dword ptr [rdi]
0x180038d75  inc     esi
0x180038d77  jmp     short loc_180038D03
0x180038d79  call    cs:__imp_GetLastError
0x180038d7f  mov     rcx, rdi; lpMem
0x180038d82  mov     ebx, eax
0x180038d84  call    ?MpHeapDestroy@@YAHPEAX@Z; MpHeapDestroy(void *)
0x180038d89  mov     ecx, ebx
0x180038d8b  jmp     loc_180038C3E
0x180038d90  mov     rax, rdi
0x180038d93  mov     rbx, [rsp+58h+arg_0]
0x180038d98  mov     rbp, [rsp+58h+arg_8]
0x180038d9d  add     rsp, 30h
0x180038da1  pop     r15
0x180038da3  pop     r14
0x180038da5  pop     r12
0x180038da7  pop     rdi
0x180038da8  pop     rsi
0x180038da9  retn
```
