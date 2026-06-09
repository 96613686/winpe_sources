# CleanupOpenFileStreams

- ea: `0x18000829c`
- end: `0x180008362`
- name: `CleanupOpenFileStreams`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090f4`

## callees

- `0x18000829c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000830f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000832c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000830f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000832c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000831d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000833a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008353`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000831d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000833a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008353`
- `ntdll!NtClose` at `0x1800082cf`
- `ntdll!NtClose` at `0x180008300`
- `ntdll!NtClose` at `0x1800082cf`
- `ntdll!NtClose` at `0x180008300`

## pseudocode

```c
void __fastcall CleanupOpenFileStreams(__int64 a1, void *a2, void *a3)
{
  __int64 i; // rsi
  void *v7; // rcx
  void *v8; // rax
  void *v9; // rsi
  HANDLE ProcessHeap; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax

  if ( *(_QWORD *)(a1 + 24) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
    {
      v7 = *(void **)(*(_QWORD *)(a1 + 24) + 8 * i);
      v8 = 0;
      if ( a3 != v7 )
        v8 = a3;
      a3 = v8;
      NtClose(v7);
    }
    v9 = *(void **)(a1 + 24);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( a3 )
    NtClose(a3);
  v11 = *(void **)(a1 + 8);
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  v13 = *(void **)(a1 + 16);
  if ( v13 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
  }
  if ( a2 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, a2);
  }
}

```

## disassembly

```asm
0x18000829c  push    rbx
0x18000829e  push    rbp
0x18000829f  push    rsi
0x1800082a0  push    rdi
0x1800082a1  sub     rsp, 28h
0x1800082a5  cmp     qword ptr [rcx+18h], 0
0x1800082aa  mov     rbx, r8
0x1800082ad  mov     rbp, rdx
0x1800082b0  mov     rdi, rcx
0x1800082b3  jz      short loc_1800082F8
0x1800082b5  xor     esi, esi
0x1800082b7  cmp     [rcx], esi
0x1800082b9  jbe     short loc_1800082DB
0x1800082bb  mov     rax, [rdi+18h]
0x1800082bf  mov     rcx, [rax+rsi*8]; Handle
0x1800082c3  xor     eax, eax
0x1800082c5  cmp     rbx, rcx
0x1800082c8  cmovnz  rax, rbx
0x1800082cc  mov     rbx, rax
0x1800082cf  call    cs:__imp_NtClose
0x1800082d5  inc     esi
0x1800082d7  cmp     esi, [rdi]
0x1800082d9  jb      short loc_1800082BB
0x1800082db  mov     rsi, [rdi+18h]
0x1800082df  test    rsi, rsi
0x1800082e2  jz      short loc_1800082F8
0x1800082e4  call    cs:__imp_GetProcessHeap
0x1800082ea  mov     r8, rsi; lpMem
0x1800082ed  xor     edx, edx; dwFlags
0x1800082ef  mov     rcx, rax; hHeap
0x1800082f2  call    cs:__imp_HeapFree
0x1800082f8  test    rbx, rbx
0x1800082fb  jz      short loc_180008306
0x1800082fd  mov     rcx, rbx; Handle
0x180008300  call    cs:__imp_NtClose
0x180008306  mov     rbx, [rdi+8]
0x18000830a  test    rbx, rbx
0x18000830d  jz      short loc_180008323
0x18000830f  call    cs:__imp_GetProcessHeap
0x180008315  mov     r8, rbx; lpMem
0x180008318  xor     edx, edx; dwFlags
0x18000831a  mov     rcx, rax; hHeap
0x18000831d  call    cs:__imp_HeapFree
0x180008323  mov     rbx, [rdi+10h]
0x180008327  test    rbx, rbx
0x18000832a  jz      short loc_180008340
0x18000832c  call    cs:__imp_GetProcessHeap
0x180008332  mov     r8, rbx; lpMem
0x180008335  xor     edx, edx; dwFlags
0x180008337  mov     rcx, rax; hHeap
0x18000833a  call    cs:__imp_HeapFree
0x180008340  test    rbp, rbp
0x180008343  jz      short loc_180008359
0x180008345  call    cs:__imp_GetProcessHeap
0x18000834b  mov     r8, rbp; lpMem
0x18000834e  xor     edx, edx; dwFlags
0x180008350  mov     rcx, rax; hHeap
0x180008353  call    cs:__imp_HeapFree
0x180008359  add     rsp, 28h
0x18000835d  pop     rdi
0x18000835e  pop     rsi
0x18000835f  pop     rbp
0x180008360  pop     rbx
0x180008361  retn
```
