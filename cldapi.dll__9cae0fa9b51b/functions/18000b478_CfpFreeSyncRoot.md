# CfpFreeSyncRoot

- ea: `0x18000b478`
- end: `0x18000b599`
- name: `CfpFreeSyncRoot`
- size: `289`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004dd0`
- `0x18000c024`

## callees

- `0x18000b478`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b4fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b4fc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b55c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b55c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b568`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b548`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b548`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b586`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b494`

## pseudocode

```c
BOOL __fastcall CfpFreeSyncRoot(_QWORD *a1)
{
  char *v2; // rcx
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v2 = (char *)a1[1];
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (void *)a1[2];
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  v5 = (void *)a1[4];
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  RtlAcquireSRWLockExclusive(a1 + 21);
  v7 = (_QWORD *)a1[19];
  while ( v7 != a1 + 19 )
  {
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
      __fastfail(3u);
    *v9 = v8;
    v10 = v7 - 1;
    *(_QWORD *)(v8 + 8) = v9;
    v7 = (_QWORD *)*v7;
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  RtlReleaseSRWLockExclusive(a1 + 21);
  v12 = GetProcessHeap();
  return HeapFree(v12, 0, a1);
}

```

## disassembly

```asm
0x18000b478  push    rbx
0x18000b47a  push    rbp
0x18000b47b  push    rsi
0x18000b47c  push    rdi
0x18000b47d  push    r14
0x18000b47f  sub     rsp, 20h
0x18000b483  mov     rsi, rcx
0x18000b486  mov     rcx, [rcx+8]; hObject
0x18000b48a  lea     rax, [rcx-1]
0x18000b48e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b492  ja      short loc_18000B4A0
0x18000b494  call    cs:__imp_CloseHandle
0x18000b49b  nop     dword ptr [rax+rax+00h]
0x18000b4a0  mov     rbx, [rsi+10h]
0x18000b4a4  test    rbx, rbx
0x18000b4a7  jz      short loc_18000B4C9
0x18000b4a9  call    cs:__imp_GetProcessHeap
0x18000b4b0  nop     dword ptr [rax+rax+00h]
0x18000b4b5  mov     r8, rbx; lpMem
0x18000b4b8  xor     edx, edx; dwFlags
0x18000b4ba  mov     rcx, rax; hHeap
0x18000b4bd  call    cs:__imp_HeapFree
0x18000b4c4  nop     dword ptr [rax+rax+00h]
0x18000b4c9  mov     rbx, [rsi+20h]
0x18000b4cd  test    rbx, rbx
0x18000b4d0  jz      short loc_18000B4F2
0x18000b4d2  call    cs:__imp_GetProcessHeap
0x18000b4d9  nop     dword ptr [rax+rax+00h]
0x18000b4de  mov     r8, rbx; lpMem
0x18000b4e1  xor     edx, edx; dwFlags
0x18000b4e3  mov     rcx, rax; hHeap
0x18000b4e6  call    cs:__imp_HeapFree
0x18000b4ed  nop     dword ptr [rax+rax+00h]
0x18000b4f2  lea     rbp, [rsi+0A8h]
0x18000b4f9  mov     rcx, rbp
0x18000b4fc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b503  nop     dword ptr [rax+rax+00h]
0x18000b508  lea     r14, [rsi+98h]
0x18000b50f  mov     rdi, [r14]
0x18000b512  jmp     short loc_18000B554
0x18000b514  mov     rax, [rdi]
0x18000b517  cmp     [rax+8], rdi
0x18000b51b  jnz     short loc_18000B592
0x18000b51d  mov     rcx, [rdi+8]
0x18000b521  cmp     [rcx], rdi
0x18000b524  jnz     short loc_18000B592
0x18000b526  mov     [rcx], rax
0x18000b529  lea     rbx, [rdi-8]
0x18000b52d  mov     [rax+8], rcx
0x18000b531  mov     rdi, [rdi]
0x18000b534  call    cs:__imp_GetProcessHeap
0x18000b53b  nop     dword ptr [rax+rax+00h]
0x18000b540  mov     r8, rbx; lpMem
0x18000b543  xor     edx, edx; dwFlags
0x18000b545  mov     rcx, rax; hHeap
0x18000b548  call    cs:__imp_HeapFree
0x18000b54f  nop     dword ptr [rax+rax+00h]
0x18000b554  cmp     rdi, r14
0x18000b557  jnz     short loc_18000B514
0x18000b559  mov     rcx, rbp
0x18000b55c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b563  nop     dword ptr [rax+rax+00h]
0x18000b568  call    cs:__imp_GetProcessHeap
0x18000b56f  nop     dword ptr [rax+rax+00h]
0x18000b574  mov     r8, rsi
0x18000b577  xor     edx, edx
0x18000b579  mov     rcx, rax
0x18000b57c  add     rsp, 20h
0x18000b580  pop     r14
0x18000b582  pop     rdi
0x18000b583  pop     rsi
0x18000b584  pop     rbp
0x18000b585  pop     rbx
0x18000b586  jmp     cs:__imp_HeapFree
0x18000b592  mov     ecx, 3
0x18000b597  int     29h; Win8: RtlFailFast(ecx)
```
