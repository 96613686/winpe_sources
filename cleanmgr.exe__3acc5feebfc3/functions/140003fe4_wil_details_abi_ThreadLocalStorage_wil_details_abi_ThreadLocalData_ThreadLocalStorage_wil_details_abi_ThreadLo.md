# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003fe4`
- end: `0x1400040be`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f5c`

## callees

- `0x140003fe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004062`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004062`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000403f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004070`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000408e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000403f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004070`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000408e`

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
0x140003fe4  push    rbx
0x140003fe6  push    rbp
0x140003fe7  push    rsi
0x140003fe8  push    rdi
0x140003fe9  push    r12
0x140003feb  push    r13
0x140003fed  push    r14
0x140003fef  push    r15
0x140003ff1  sub     rsp, 28h
0x140003ff5  lea     r15, [rcx+50h]
0x140003ff9  mov     rdi, rcx
0x140003ffc  cmp     rcx, r15
0x140003fff  jz      loc_1400040AD
0x140004005  mov     rsi, [rdi]
0x140004008  jmp     loc_140004094
0x14000400d  mov     r13, rsi
0x140004010  mov     r12, rsi
0x140004013  mov     rsi, [rsi+8]
0x140004017  movzx   eax, word ptr [r13+30h]
0x14000401c  mov     rbp, [r13+28h]
0x140004020  lea     r14, [rax+rax*4]
0x140004024  shl     r14, 4
0x140004028  add     r14, rbp
0x14000402b  jmp     short loc_140004059
0x14000402d  mov     rbx, [rbp+40h]
0x140004031  call    cs:__imp_GetProcessHeap
0x140004037  mov     r8, rbx; lpMem
0x14000403a  xor     edx, edx; dwFlags
0x14000403c  mov     rcx, rax; hHeap
0x14000403f  call    cs:__imp_HeapFree
0x140004045  mov     qword ptr [rbp+40h], 0
0x14000404d  mov     qword ptr [rbp+48h], 0
0x140004055  add     rbp, 50h ; 'P'
0x140004059  cmp     rbp, r14
0x14000405c  jnz     short loc_14000402D
0x14000405e  mov     rbx, [r13+28h]
0x140004062  call    cs:__imp_GetProcessHeap
0x140004068  mov     r8, rbx; lpMem
0x14000406b  xor     edx, edx; dwFlags
0x14000406d  mov     rcx, rax; hHeap
0x140004070  call    cs:__imp_HeapFree
0x140004076  xor     eax, eax
0x140004078  mov     [r13+30h], eax
0x14000407c  mov     [r13+28h], rax
0x140004080  call    cs:__imp_GetProcessHeap
0x140004086  mov     r8, r12; lpMem
0x140004089  xor     edx, edx; dwFlags
0x14000408b  mov     rcx, rax; hHeap
0x14000408e  call    cs:__imp_HeapFree
0x140004094  test    rsi, rsi
0x140004097  jnz     loc_14000400D
0x14000409d  mov     [rdi], rsi
0x1400040a0  add     rdi, 8
0x1400040a4  cmp     rdi, r15
0x1400040a7  jnz     loc_140004005
0x1400040ad  add     rsp, 28h
0x1400040b1  pop     r15
0x1400040b3  pop     r14
0x1400040b5  pop     r13
0x1400040b7  pop     r12
0x1400040b9  pop     rdi
0x1400040ba  pop     rsi
0x1400040bb  pop     rbp
0x1400040bc  pop     rbx
0x1400040bd  retn
```
