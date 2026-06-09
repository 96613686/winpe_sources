# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180005938`
- end: `0x180005a12`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058d8`

## callees

- `0x180005938`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059e2`

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
0x180005938  push    rbx
0x18000593a  push    rbp
0x18000593b  push    rsi
0x18000593c  push    rdi
0x18000593d  push    r12
0x18000593f  push    r13
0x180005941  push    r14
0x180005943  push    r15
0x180005945  sub     rsp, 28h
0x180005949  lea     r15, [rcx+50h]
0x18000594d  mov     rdi, rcx
0x180005950  cmp     rcx, r15
0x180005953  jz      loc_180005A01
0x180005959  mov     rsi, [rdi]
0x18000595c  jmp     loc_1800059E8
0x180005961  mov     r13, rsi
0x180005964  mov     r12, rsi
0x180005967  mov     rsi, [rsi+8]
0x18000596b  movzx   eax, word ptr [r13+30h]
0x180005970  mov     rbp, [r13+28h]
0x180005974  lea     r14, [rax+rax*4]
0x180005978  shl     r14, 4
0x18000597c  add     r14, rbp
0x18000597f  jmp     short loc_1800059AD
0x180005981  mov     rbx, [rbp+40h]
0x180005985  call    cs:__imp_GetProcessHeap
0x18000598b  mov     r8, rbx; lpMem
0x18000598e  xor     edx, edx; dwFlags
0x180005990  mov     rcx, rax; hHeap
0x180005993  call    cs:__imp_HeapFree
0x180005999  mov     qword ptr [rbp+40h], 0
0x1800059a1  mov     qword ptr [rbp+48h], 0
0x1800059a9  add     rbp, 50h ; 'P'
0x1800059ad  cmp     rbp, r14
0x1800059b0  jnz     short loc_180005981
0x1800059b2  mov     rbx, [r13+28h]
0x1800059b6  call    cs:__imp_GetProcessHeap
0x1800059bc  mov     r8, rbx; lpMem
0x1800059bf  xor     edx, edx; dwFlags
0x1800059c1  mov     rcx, rax; hHeap
0x1800059c4  call    cs:__imp_HeapFree
0x1800059ca  xor     eax, eax
0x1800059cc  mov     [r13+30h], eax
0x1800059d0  mov     [r13+28h], rax
0x1800059d4  call    cs:__imp_GetProcessHeap
0x1800059da  mov     r8, r12; lpMem
0x1800059dd  xor     edx, edx; dwFlags
0x1800059df  mov     rcx, rax; hHeap
0x1800059e2  call    cs:__imp_HeapFree
0x1800059e8  test    rsi, rsi
0x1800059eb  jnz     loc_180005961
0x1800059f1  mov     [rdi], rsi
0x1800059f4  add     rdi, 8
0x1800059f8  cmp     rdi, r15
0x1800059fb  jnz     loc_180005959
0x180005a01  add     rsp, 28h
0x180005a05  pop     r15
0x180005a07  pop     r14
0x180005a09  pop     r13
0x180005a0b  pop     r12
0x180005a0d  pop     rdi
0x180005a0e  pop     rsi
0x180005a0f  pop     rbp
0x180005a10  pop     rbx
0x180005a11  retn
```
