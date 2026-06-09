# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180022560`
- end: `0x180022676`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800273b0`

## callees

- `0x180022560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022610`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022630`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022610`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022630`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022622`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022622`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r13
  _QWORD *v2; // r15
  _QWORD *v3; // rbp
  _QWORD *v4; // r14
  void *v5; // r12
  __int64 v6; // rbx
  __int64 i; // rsi
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v5 = v3;
        v3 = (_QWORD *)v3[1];
        v6 = v4[5];
        for ( i = v6 + 80LL * *((unsigned __int16 *)v4 + 24); v6 != i; v6 += 80 )
        {
          v8 = *(void **)(v6 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v8);
          *(_QWORD *)(v6 + 64) = 0;
          *(_QWORD *)(v6 + 72) = 0;
        }
        v10 = (void *)v4[5];
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v10);
        *((_DWORD *)v4 + 12) = 0;
        v4[5] = 0;
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v5);
      }
      while ( v3 );
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180022560  push    r13
0x180022562  push    r15
0x180022564  sub     rsp, 38h
0x180022568  lea     r13, [rcx+50h]
0x18002256c  mov     r15, rcx
0x18002256f  cmp     rcx, r13
0x180022572  jz      loc_18002266D
0x180022578  mov     [rsp+48h+arg_8], rbx
0x18002257d  mov     [rsp+48h+arg_10], rbp
0x180022582  mov     [rsp+48h+arg_18], rsi
0x180022587  mov     [rsp+48h+var_18], rdi
0x18002258c  xor     edi, edi
0x18002258e  mov     [rsp+48h+var_20], r12
0x180022593  mov     [rsp+48h+var_28], r14
0x180022598  nop     dword ptr [rax+rax+00000000h]
0x1800225a0  mov     rbp, [r15]
0x1800225a3  test    rbp, rbp
0x1800225a6  jz      loc_18002263F
0x1800225ac  nop     dword ptr [rax+00h]
0x1800225b0  mov     r14, rbp
0x1800225b3  mov     r12, rbp
0x1800225b6  mov     rbp, [rbp+8]
0x1800225ba  mov     rbx, [r14+28h]
0x1800225be  movzx   eax, word ptr [r14+30h]
0x1800225c3  lea     rsi, [rax+rax*4]
0x1800225c7  shl     rsi, 4
0x1800225cb  add     rsi, rbx
0x1800225ce  cmp     rbx, rsi
0x1800225d1  jz      short loc_1800225FE
0x1800225d3  mov     rdi, [rbx+40h]
0x1800225d7  call    cs:__imp_GetProcessHeap
0x1800225dd  mov     r8, rdi; lpMem
0x1800225e0  xor     edx, edx; dwFlags
0x1800225e2  mov     rcx, rax; hHeap
0x1800225e5  call    cs:__imp_HeapFree
0x1800225eb  xor     edi, edi
0x1800225ed  mov     [rbx+40h], rdi
0x1800225f1  mov     [rbx+48h], rdi
0x1800225f5  add     rbx, 50h ; 'P'
0x1800225f9  cmp     rbx, rsi
0x1800225fc  jnz     short loc_1800225D3
0x1800225fe  mov     rbx, [r14+28h]
0x180022602  call    cs:__imp_GetProcessHeap
0x180022608  mov     r8, rbx; lpMem
0x18002260b  xor     edx, edx; dwFlags
0x18002260d  mov     rcx, rax; hHeap
0x180022610  call    cs:__imp_HeapFree
0x180022616  mov     dword ptr [r14+30h], 0
0x18002261e  mov     [r14+28h], rdi
0x180022622  call    cs:__imp_GetProcessHeap
0x180022628  mov     r8, r12; lpMem
0x18002262b  xor     edx, edx; dwFlags
0x18002262d  mov     rcx, rax; hHeap
0x180022630  call    cs:__imp_HeapFree
0x180022636  test    rbp, rbp
0x180022639  jnz     loc_1800225B0
0x18002263f  mov     [r15], rdi
0x180022642  add     r15, 8
0x180022646  cmp     r15, r13
0x180022649  jnz     loc_1800225A0
0x18002264f  mov     r14, [rsp+48h+var_28]
0x180022654  mov     r12, [rsp+48h+var_20]
0x180022659  mov     rdi, [rsp+48h+var_18]
0x18002265e  mov     rsi, [rsp+48h+arg_18]
0x180022663  mov     rbp, [rsp+48h+arg_10]
0x180022668  mov     rbx, [rsp+48h+arg_8]
0x18002266d  add     rsp, 38h
0x180022671  pop     r15
0x180022673  pop     r13
0x180022675  retn
```
