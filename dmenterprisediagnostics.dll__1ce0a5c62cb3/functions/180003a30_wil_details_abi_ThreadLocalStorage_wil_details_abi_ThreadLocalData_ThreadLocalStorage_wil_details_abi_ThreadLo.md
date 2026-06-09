# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003a30`
- end: `0x180003b0a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003960`

## callees

- `0x180003a30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ada`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003aae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003acc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003aae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003acc`

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
0x180003a30  push    rbx
0x180003a32  push    rbp
0x180003a33  push    rsi
0x180003a34  push    rdi
0x180003a35  push    r12
0x180003a37  push    r13
0x180003a39  push    r14
0x180003a3b  push    r15
0x180003a3d  sub     rsp, 28h
0x180003a41  lea     r15, [rcx+50h]
0x180003a45  mov     rdi, rcx
0x180003a48  cmp     rcx, r15
0x180003a4b  jz      loc_180003AF9
0x180003a51  mov     rsi, [rdi]
0x180003a54  jmp     loc_180003AE0
0x180003a59  mov     r13, rsi
0x180003a5c  mov     r12, rsi
0x180003a5f  mov     rsi, [rsi+8]
0x180003a63  movzx   eax, word ptr [r13+30h]
0x180003a68  mov     rbp, [r13+28h]
0x180003a6c  lea     r14, [rax+rax*4]
0x180003a70  shl     r14, 4
0x180003a74  add     r14, rbp
0x180003a77  jmp     short loc_180003AA5
0x180003a79  mov     rbx, [rbp+40h]
0x180003a7d  call    cs:__imp_GetProcessHeap
0x180003a83  mov     r8, rbx; lpMem
0x180003a86  xor     edx, edx; dwFlags
0x180003a88  mov     rcx, rax; hHeap
0x180003a8b  call    cs:__imp_HeapFree
0x180003a91  mov     qword ptr [rbp+40h], 0
0x180003a99  mov     qword ptr [rbp+48h], 0
0x180003aa1  add     rbp, 50h ; 'P'
0x180003aa5  cmp     rbp, r14
0x180003aa8  jnz     short loc_180003A79
0x180003aaa  mov     rbx, [r13+28h]
0x180003aae  call    cs:__imp_GetProcessHeap
0x180003ab4  mov     r8, rbx; lpMem
0x180003ab7  xor     edx, edx; dwFlags
0x180003ab9  mov     rcx, rax; hHeap
0x180003abc  call    cs:__imp_HeapFree
0x180003ac2  xor     eax, eax
0x180003ac4  mov     [r13+30h], eax
0x180003ac8  mov     [r13+28h], rax
0x180003acc  call    cs:__imp_GetProcessHeap
0x180003ad2  mov     r8, r12; lpMem
0x180003ad5  xor     edx, edx; dwFlags
0x180003ad7  mov     rcx, rax; hHeap
0x180003ada  call    cs:__imp_HeapFree
0x180003ae0  test    rsi, rsi
0x180003ae3  jnz     loc_180003A59
0x180003ae9  mov     [rdi], rsi
0x180003aec  add     rdi, 8
0x180003af0  cmp     rdi, r15
0x180003af3  jnz     loc_180003A51
0x180003af9  add     rsp, 28h
0x180003afd  pop     r15
0x180003aff  pop     r14
0x180003b01  pop     r13
0x180003b03  pop     r12
0x180003b05  pop     rdi
0x180003b06  pop     rsi
0x180003b07  pop     rbp
0x180003b08  pop     rbx
0x180003b09  retn
```
