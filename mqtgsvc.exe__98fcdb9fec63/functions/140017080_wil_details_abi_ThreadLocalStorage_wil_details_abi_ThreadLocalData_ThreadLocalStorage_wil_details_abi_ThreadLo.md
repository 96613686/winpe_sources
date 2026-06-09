# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140017080`
- end: `0x14001715a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016fc8`

## callees

- `0x140017080`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400170db`
- `KERNEL32!HeapFree` at `0x14001710c`
- `KERNEL32!HeapFree` at `0x14001712a`
- `KERNEL32!HeapFree` at `0x1400170db`
- `KERNEL32!HeapFree` at `0x14001710c`
- `KERNEL32!HeapFree` at `0x14001712a`
- `KERNEL32!GetProcessHeap` at `0x1400170cd`
- `KERNEL32!GetProcessHeap` at `0x1400170fe`
- `KERNEL32!GetProcessHeap` at `0x14001711c`
- `KERNEL32!GetProcessHeap` at `0x1400170cd`
- `KERNEL32!GetProcessHeap` at `0x1400170fe`
- `KERNEL32!GetProcessHeap` at `0x14001711c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // r15
  _QWORD *v3; // rsi
  void *v4; // r12
  _QWORD *v5; // r13
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = (_QWORD *)*v1;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v5[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v5 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v5[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v5 + 12) = 0;
      v5[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v4);
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x140017080  push    rbx
0x140017082  push    rbp
0x140017083  push    rsi
0x140017084  push    rdi
0x140017085  push    r12
0x140017087  push    r13
0x140017089  push    r14
0x14001708b  push    r15
0x14001708d  sub     rsp, 28h
0x140017091  mov     rdi, rcx
0x140017094  lea     r15, [rcx+50h]
0x140017098  cmp     rcx, r15
0x14001709b  jz      loc_140017149
0x1400170a1  mov     rsi, [rdi]
0x1400170a4  jmp     loc_140017130
0x1400170a9  mov     r12, rsi
0x1400170ac  mov     r13, rsi
0x1400170af  mov     rsi, [rsi+8]
0x1400170b3  mov     rbp, [r13+28h]
0x1400170b7  movzx   eax, word ptr [r13+30h]
0x1400170bc  lea     r14, [rax+rax*4]
0x1400170c0  shl     r14, 4
0x1400170c4  add     r14, rbp
0x1400170c7  jmp     short loc_1400170F5
0x1400170c9  mov     rbx, [rbp+40h]
0x1400170cd  call    cs:__imp_GetProcessHeap
0x1400170d3  mov     r8, rbx; lpMem
0x1400170d6  xor     edx, edx; dwFlags
0x1400170d8  mov     rcx, rax; hHeap
0x1400170db  call    cs:__imp_HeapFree
0x1400170e1  mov     qword ptr [rbp+40h], 0
0x1400170e9  mov     qword ptr [rbp+48h], 0
0x1400170f1  add     rbp, 50h ; 'P'
0x1400170f5  cmp     rbp, r14
0x1400170f8  jnz     short loc_1400170C9
0x1400170fa  mov     rbx, [r13+28h]
0x1400170fe  call    cs:__imp_GetProcessHeap
0x140017104  mov     r8, rbx; lpMem
0x140017107  xor     edx, edx; dwFlags
0x140017109  mov     rcx, rax; hHeap
0x14001710c  call    cs:__imp_HeapFree
0x140017112  xor     eax, eax
0x140017114  mov     [r13+30h], eax
0x140017118  mov     [r13+28h], rax
0x14001711c  call    cs:__imp_GetProcessHeap
0x140017122  mov     rcx, rax; hHeap
0x140017125  mov     r8, r12; lpMem
0x140017128  xor     edx, edx; dwFlags
0x14001712a  call    cs:__imp_HeapFree
0x140017130  test    rsi, rsi
0x140017133  jnz     loc_1400170A9
0x140017139  mov     [rdi], rsi
0x14001713c  add     rdi, 8
0x140017140  cmp     rdi, r15
0x140017143  jnz     loc_1400170A1
0x140017149  add     rsp, 28h
0x14001714d  pop     r15
0x14001714f  pop     r14
0x140017151  pop     r13
0x140017153  pop     r12
0x140017155  pop     rdi
0x140017156  pop     rsi
0x140017157  pop     rbp
0x140017158  pop     rbx
0x140017159  retn
```
