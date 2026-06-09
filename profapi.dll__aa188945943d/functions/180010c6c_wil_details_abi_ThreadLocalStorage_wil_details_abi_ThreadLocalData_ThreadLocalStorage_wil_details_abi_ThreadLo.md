# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180010c6c`
- end: `0x180010d46`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010c3c`

## callees

- `0x180010c6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010cf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010cea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d08`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180010c6c  push    rbx
0x180010c6e  push    rbp
0x180010c6f  push    rsi
0x180010c70  push    rdi
0x180010c71  push    r12
0x180010c73  push    r13
0x180010c75  push    r14
0x180010c77  push    r15
0x180010c79  sub     rsp, 28h
0x180010c7d  lea     r15, [rcx+50h]
0x180010c81  mov     rdi, rcx
0x180010c84  cmp     rcx, r15
0x180010c87  jz      loc_180010D35
0x180010c8d  mov     rsi, [rdi]
0x180010c90  jmp     loc_180010D1C
0x180010c95  mov     r13, rsi
0x180010c98  mov     r12, rsi
0x180010c9b  mov     rsi, [rsi+8]
0x180010c9f  movzx   eax, word ptr [r13+30h]
0x180010ca4  mov     rbp, [r13+28h]
0x180010ca8  lea     r14, [rax+rax*4]
0x180010cac  shl     r14, 4
0x180010cb0  add     r14, rbp
0x180010cb3  jmp     short loc_180010CE1
0x180010cb5  mov     rbx, [rbp+40h]
0x180010cb9  call    cs:__imp_GetProcessHeap
0x180010cbf  mov     r8, rbx; lpMem
0x180010cc2  xor     edx, edx; dwFlags
0x180010cc4  mov     rcx, rax; hHeap
0x180010cc7  call    cs:__imp_HeapFree
0x180010ccd  mov     qword ptr [rbp+40h], 0
0x180010cd5  mov     qword ptr [rbp+48h], 0
0x180010cdd  add     rbp, 50h ; 'P'
0x180010ce1  cmp     rbp, r14
0x180010ce4  jnz     short loc_180010CB5
0x180010ce6  mov     rbx, [r13+28h]
0x180010cea  call    cs:__imp_GetProcessHeap
0x180010cf0  mov     r8, rbx; lpMem
0x180010cf3  xor     edx, edx; dwFlags
0x180010cf5  mov     rcx, rax; hHeap
0x180010cf8  call    cs:__imp_HeapFree
0x180010cfe  xor     eax, eax
0x180010d00  mov     [r13+30h], eax
0x180010d04  mov     [r13+28h], rax
0x180010d08  call    cs:__imp_GetProcessHeap
0x180010d0e  mov     r8, r12; lpMem
0x180010d11  xor     edx, edx; dwFlags
0x180010d13  mov     rcx, rax; hHeap
0x180010d16  call    cs:__imp_HeapFree
0x180010d1c  test    rsi, rsi
0x180010d1f  jnz     loc_180010C95
0x180010d25  mov     [rdi], rsi
0x180010d28  add     rdi, 8
0x180010d2c  cmp     rdi, r15
0x180010d2f  jnz     loc_180010C8D
0x180010d35  add     rsp, 28h
0x180010d39  pop     r15
0x180010d3b  pop     r14
0x180010d3d  pop     r13
0x180010d3f  pop     r12
0x180010d41  pop     rdi
0x180010d42  pop     rsi
0x180010d43  pop     rbp
0x180010d44  pop     rbx
0x180010d45  retn
```
