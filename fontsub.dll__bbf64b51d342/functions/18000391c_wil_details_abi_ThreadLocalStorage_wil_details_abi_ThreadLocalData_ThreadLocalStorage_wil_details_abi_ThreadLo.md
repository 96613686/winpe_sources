# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000391c`
- end: `0x1800039f6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003894`

## callees

- `0x18000391c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003969`
- `KERNEL32!GetProcessHeap` at `0x18000399a`
- `KERNEL32!GetProcessHeap` at `0x1800039b8`
- `KERNEL32!GetProcessHeap` at `0x180003969`
- `KERNEL32!GetProcessHeap` at `0x18000399a`
- `KERNEL32!GetProcessHeap` at `0x1800039b8`
- `KERNEL32!HeapFree` at `0x180003977`
- `KERNEL32!HeapFree` at `0x1800039a8`
- `KERNEL32!HeapFree` at `0x1800039c6`
- `KERNEL32!HeapFree` at `0x180003977`
- `KERNEL32!HeapFree` at `0x1800039a8`
- `KERNEL32!HeapFree` at `0x1800039c6`

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
0x18000391c  push    rbx
0x18000391e  push    rbp
0x18000391f  push    rsi
0x180003920  push    rdi
0x180003921  push    r12
0x180003923  push    r13
0x180003925  push    r14
0x180003927  push    r15
0x180003929  sub     rsp, 28h
0x18000392d  lea     r15, [rcx+50h]
0x180003931  mov     rdi, rcx
0x180003934  cmp     rcx, r15
0x180003937  jz      loc_1800039E5
0x18000393d  mov     rsi, [rdi]
0x180003940  jmp     loc_1800039CC
0x180003945  mov     r13, rsi
0x180003948  mov     r12, rsi
0x18000394b  mov     rsi, [rsi+8]
0x18000394f  movzx   eax, word ptr [r13+30h]
0x180003954  mov     rbp, [r13+28h]
0x180003958  lea     r14, [rax+rax*4]
0x18000395c  shl     r14, 4
0x180003960  add     r14, rbp
0x180003963  jmp     short loc_180003991
0x180003965  mov     rbx, [rbp+40h]
0x180003969  call    cs:__imp_GetProcessHeap
0x18000396f  mov     r8, rbx; lpMem
0x180003972  xor     edx, edx; dwFlags
0x180003974  mov     rcx, rax; hHeap
0x180003977  call    cs:__imp_HeapFree
0x18000397d  mov     qword ptr [rbp+40h], 0
0x180003985  mov     qword ptr [rbp+48h], 0
0x18000398d  add     rbp, 50h ; 'P'
0x180003991  cmp     rbp, r14
0x180003994  jnz     short loc_180003965
0x180003996  mov     rbx, [r13+28h]
0x18000399a  call    cs:__imp_GetProcessHeap
0x1800039a0  mov     r8, rbx; lpMem
0x1800039a3  xor     edx, edx; dwFlags
0x1800039a5  mov     rcx, rax; hHeap
0x1800039a8  call    cs:__imp_HeapFree
0x1800039ae  xor     eax, eax
0x1800039b0  mov     [r13+30h], eax
0x1800039b4  mov     [r13+28h], rax
0x1800039b8  call    cs:__imp_GetProcessHeap
0x1800039be  mov     r8, r12; lpMem
0x1800039c1  xor     edx, edx; dwFlags
0x1800039c3  mov     rcx, rax; hHeap
0x1800039c6  call    cs:__imp_HeapFree
0x1800039cc  test    rsi, rsi
0x1800039cf  jnz     loc_180003945
0x1800039d5  mov     [rdi], rsi
0x1800039d8  add     rdi, 8
0x1800039dc  cmp     rdi, r15
0x1800039df  jnz     loc_18000393D
0x1800039e5  add     rsp, 28h
0x1800039e9  pop     r15
0x1800039eb  pop     r14
0x1800039ed  pop     r13
0x1800039ef  pop     r12
0x1800039f1  pop     rdi
0x1800039f2  pop     rsi
0x1800039f3  pop     rbp
0x1800039f4  pop     rbx
0x1800039f5  retn
```
