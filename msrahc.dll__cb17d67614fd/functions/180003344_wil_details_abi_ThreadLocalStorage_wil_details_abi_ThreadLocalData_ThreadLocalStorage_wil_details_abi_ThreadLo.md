# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003344`
- end: `0x18000341e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000328c`

## callees

- `0x180003344`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003391`
- `KERNEL32!GetProcessHeap` at `0x1800033c2`
- `KERNEL32!GetProcessHeap` at `0x1800033e0`
- `KERNEL32!GetProcessHeap` at `0x180003391`
- `KERNEL32!GetProcessHeap` at `0x1800033c2`
- `KERNEL32!GetProcessHeap` at `0x1800033e0`
- `KERNEL32!HeapFree` at `0x18000339f`
- `KERNEL32!HeapFree` at `0x1800033d0`
- `KERNEL32!HeapFree` at `0x1800033ee`
- `KERNEL32!HeapFree` at `0x18000339f`
- `KERNEL32!HeapFree` at `0x1800033d0`
- `KERNEL32!HeapFree` at `0x1800033ee`

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
0x180003344  push    rbx
0x180003346  push    rbp
0x180003347  push    rsi
0x180003348  push    rdi
0x180003349  push    r12
0x18000334b  push    r13
0x18000334d  push    r14
0x18000334f  push    r15
0x180003351  sub     rsp, 28h
0x180003355  lea     r15, [rcx+50h]
0x180003359  mov     rdi, rcx
0x18000335c  cmp     rcx, r15
0x18000335f  jz      loc_18000340D
0x180003365  mov     rsi, [rdi]
0x180003368  jmp     loc_1800033F4
0x18000336d  mov     r13, rsi
0x180003370  mov     r12, rsi
0x180003373  mov     rsi, [rsi+8]
0x180003377  movzx   eax, word ptr [r13+30h]
0x18000337c  mov     rbp, [r13+28h]
0x180003380  lea     r14, [rax+rax*4]
0x180003384  shl     r14, 4
0x180003388  add     r14, rbp
0x18000338b  jmp     short loc_1800033B9
0x18000338d  mov     rbx, [rbp+40h]
0x180003391  call    cs:__imp_GetProcessHeap
0x180003397  mov     r8, rbx; lpMem
0x18000339a  xor     edx, edx; dwFlags
0x18000339c  mov     rcx, rax; hHeap
0x18000339f  call    cs:__imp_HeapFree
0x1800033a5  mov     qword ptr [rbp+40h], 0
0x1800033ad  mov     qword ptr [rbp+48h], 0
0x1800033b5  add     rbp, 50h ; 'P'
0x1800033b9  cmp     rbp, r14
0x1800033bc  jnz     short loc_18000338D
0x1800033be  mov     rbx, [r13+28h]
0x1800033c2  call    cs:__imp_GetProcessHeap
0x1800033c8  mov     r8, rbx; lpMem
0x1800033cb  xor     edx, edx; dwFlags
0x1800033cd  mov     rcx, rax; hHeap
0x1800033d0  call    cs:__imp_HeapFree
0x1800033d6  xor     eax, eax
0x1800033d8  mov     [r13+30h], eax
0x1800033dc  mov     [r13+28h], rax
0x1800033e0  call    cs:__imp_GetProcessHeap
0x1800033e6  mov     r8, r12; lpMem
0x1800033e9  xor     edx, edx; dwFlags
0x1800033eb  mov     rcx, rax; hHeap
0x1800033ee  call    cs:__imp_HeapFree
0x1800033f4  test    rsi, rsi
0x1800033f7  jnz     loc_18000336D
0x1800033fd  mov     [rdi], rsi
0x180003400  add     rdi, 8
0x180003404  cmp     rdi, r15
0x180003407  jnz     loc_180003365
0x18000340d  add     rsp, 28h
0x180003411  pop     r15
0x180003413  pop     r14
0x180003415  pop     r13
0x180003417  pop     r12
0x180003419  pop     rdi
0x18000341a  pop     rsi
0x18000341b  pop     rbp
0x18000341c  pop     rbx
0x18000341d  retn
```
