# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180006ca4`
- end: `0x180006d7e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c1c`

## callees

- `0x180006ca4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d40`

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
0x180006ca4  push    rbx
0x180006ca6  push    rbp
0x180006ca7  push    rsi
0x180006ca8  push    rdi
0x180006ca9  push    r12
0x180006cab  push    r13
0x180006cad  push    r14
0x180006caf  push    r15
0x180006cb1  sub     rsp, 28h
0x180006cb5  lea     r15, [rcx+50h]
0x180006cb9  mov     rdi, rcx
0x180006cbc  cmp     rcx, r15
0x180006cbf  jz      loc_180006D6D
0x180006cc5  mov     rsi, [rdi]
0x180006cc8  jmp     loc_180006D54
0x180006ccd  mov     r13, rsi
0x180006cd0  mov     r12, rsi
0x180006cd3  mov     rsi, [rsi+8]
0x180006cd7  movzx   eax, word ptr [r13+30h]
0x180006cdc  mov     rbp, [r13+28h]
0x180006ce0  lea     r14, [rax+rax*4]
0x180006ce4  shl     r14, 4
0x180006ce8  add     r14, rbp
0x180006ceb  jmp     short loc_180006D19
0x180006ced  mov     rbx, [rbp+40h]
0x180006cf1  call    cs:__imp_GetProcessHeap
0x180006cf7  mov     r8, rbx; lpMem
0x180006cfa  xor     edx, edx; dwFlags
0x180006cfc  mov     rcx, rax; hHeap
0x180006cff  call    cs:__imp_HeapFree
0x180006d05  mov     qword ptr [rbp+40h], 0
0x180006d0d  mov     qword ptr [rbp+48h], 0
0x180006d15  add     rbp, 50h ; 'P'
0x180006d19  cmp     rbp, r14
0x180006d1c  jnz     short loc_180006CED
0x180006d1e  mov     rbx, [r13+28h]
0x180006d22  call    cs:__imp_GetProcessHeap
0x180006d28  mov     r8, rbx; lpMem
0x180006d2b  xor     edx, edx; dwFlags
0x180006d2d  mov     rcx, rax; hHeap
0x180006d30  call    cs:__imp_HeapFree
0x180006d36  xor     eax, eax
0x180006d38  mov     [r13+30h], eax
0x180006d3c  mov     [r13+28h], rax
0x180006d40  call    cs:__imp_GetProcessHeap
0x180006d46  mov     r8, r12; lpMem
0x180006d49  xor     edx, edx; dwFlags
0x180006d4b  mov     rcx, rax; hHeap
0x180006d4e  call    cs:__imp_HeapFree
0x180006d54  test    rsi, rsi
0x180006d57  jnz     loc_180006CCD
0x180006d5d  mov     [rdi], rsi
0x180006d60  add     rdi, 8
0x180006d64  cmp     rdi, r15
0x180006d67  jnz     loc_180006CC5
0x180006d6d  add     rsp, 28h
0x180006d71  pop     r15
0x180006d73  pop     r14
0x180006d75  pop     r13
0x180006d77  pop     r12
0x180006d79  pop     rdi
0x180006d7a  pop     rsi
0x180006d7b  pop     rbp
0x180006d7c  pop     rbx
0x180006d7d  retn
```
