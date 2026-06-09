# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000fa18`
- end: `0x18000faf2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f990`

## callees

- `0x18000fa18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faa4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fab4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fab4`

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
0x18000fa18  push    rbx
0x18000fa1a  push    rbp
0x18000fa1b  push    rsi
0x18000fa1c  push    rdi
0x18000fa1d  push    r12
0x18000fa1f  push    r13
0x18000fa21  push    r14
0x18000fa23  push    r15
0x18000fa25  sub     rsp, 28h
0x18000fa29  lea     r15, [rcx+50h]
0x18000fa2d  mov     rdi, rcx
0x18000fa30  cmp     rcx, r15
0x18000fa33  jz      loc_18000FAE1
0x18000fa39  mov     rsi, [rdi]
0x18000fa3c  jmp     loc_18000FAC8
0x18000fa41  mov     r13, rsi
0x18000fa44  mov     r12, rsi
0x18000fa47  mov     rsi, [rsi+8]
0x18000fa4b  movzx   eax, word ptr [r13+30h]
0x18000fa50  mov     rbp, [r13+28h]
0x18000fa54  lea     r14, [rax+rax*4]
0x18000fa58  shl     r14, 4
0x18000fa5c  add     r14, rbp
0x18000fa5f  jmp     short loc_18000FA8D
0x18000fa61  mov     rbx, [rbp+40h]
0x18000fa65  call    cs:__imp_GetProcessHeap
0x18000fa6b  mov     r8, rbx; lpMem
0x18000fa6e  xor     edx, edx; dwFlags
0x18000fa70  mov     rcx, rax; hHeap
0x18000fa73  call    cs:__imp_HeapFree
0x18000fa79  mov     qword ptr [rbp+40h], 0
0x18000fa81  mov     qword ptr [rbp+48h], 0
0x18000fa89  add     rbp, 50h ; 'P'
0x18000fa8d  cmp     rbp, r14
0x18000fa90  jnz     short loc_18000FA61
0x18000fa92  mov     rbx, [r13+28h]
0x18000fa96  call    cs:__imp_GetProcessHeap
0x18000fa9c  mov     r8, rbx; lpMem
0x18000fa9f  xor     edx, edx; dwFlags
0x18000faa1  mov     rcx, rax; hHeap
0x18000faa4  call    cs:__imp_HeapFree
0x18000faaa  xor     eax, eax
0x18000faac  mov     [r13+30h], eax
0x18000fab0  mov     [r13+28h], rax
0x18000fab4  call    cs:__imp_GetProcessHeap
0x18000faba  mov     r8, r12; lpMem
0x18000fabd  xor     edx, edx; dwFlags
0x18000fabf  mov     rcx, rax; hHeap
0x18000fac2  call    cs:__imp_HeapFree
0x18000fac8  test    rsi, rsi
0x18000facb  jnz     loc_18000FA41
0x18000fad1  mov     [rdi], rsi
0x18000fad4  add     rdi, 8
0x18000fad8  cmp     rdi, r15
0x18000fadb  jnz     loc_18000FA39
0x18000fae1  add     rsp, 28h
0x18000fae5  pop     r15
0x18000fae7  pop     r14
0x18000fae9  pop     r13
0x18000faeb  pop     r12
0x18000faed  pop     rdi
0x18000faee  pop     rsi
0x18000faef  pop     rbp
0x18000faf0  pop     rbx
0x18000faf1  retn
```
