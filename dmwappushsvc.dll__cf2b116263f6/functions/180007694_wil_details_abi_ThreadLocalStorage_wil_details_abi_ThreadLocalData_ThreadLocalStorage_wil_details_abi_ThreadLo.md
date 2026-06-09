# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180007694`
- end: `0x18000776e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075dc`

## callees

- `0x180007694`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000773e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000773e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007730`

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
0x180007694  push    rbx
0x180007696  push    rbp
0x180007697  push    rsi
0x180007698  push    rdi
0x180007699  push    r12
0x18000769b  push    r13
0x18000769d  push    r14
0x18000769f  push    r15
0x1800076a1  sub     rsp, 28h
0x1800076a5  lea     r15, [rcx+50h]
0x1800076a9  mov     rdi, rcx
0x1800076ac  cmp     rcx, r15
0x1800076af  jz      loc_18000775D
0x1800076b5  mov     rsi, [rdi]
0x1800076b8  jmp     loc_180007744
0x1800076bd  mov     r13, rsi
0x1800076c0  mov     r12, rsi
0x1800076c3  mov     rsi, [rsi+8]
0x1800076c7  movzx   eax, word ptr [r13+30h]
0x1800076cc  mov     rbp, [r13+28h]
0x1800076d0  lea     r14, [rax+rax*4]
0x1800076d4  shl     r14, 4
0x1800076d8  add     r14, rbp
0x1800076db  jmp     short loc_180007709
0x1800076dd  mov     rbx, [rbp+40h]
0x1800076e1  call    cs:__imp_GetProcessHeap
0x1800076e7  mov     r8, rbx; lpMem
0x1800076ea  xor     edx, edx; dwFlags
0x1800076ec  mov     rcx, rax; hHeap
0x1800076ef  call    cs:__imp_HeapFree
0x1800076f5  mov     qword ptr [rbp+40h], 0
0x1800076fd  mov     qword ptr [rbp+48h], 0
0x180007705  add     rbp, 50h ; 'P'
0x180007709  cmp     rbp, r14
0x18000770c  jnz     short loc_1800076DD
0x18000770e  mov     rbx, [r13+28h]
0x180007712  call    cs:__imp_GetProcessHeap
0x180007718  mov     r8, rbx; lpMem
0x18000771b  xor     edx, edx; dwFlags
0x18000771d  mov     rcx, rax; hHeap
0x180007720  call    cs:__imp_HeapFree
0x180007726  xor     eax, eax
0x180007728  mov     [r13+30h], eax
0x18000772c  mov     [r13+28h], rax
0x180007730  call    cs:__imp_GetProcessHeap
0x180007736  mov     r8, r12; lpMem
0x180007739  xor     edx, edx; dwFlags
0x18000773b  mov     rcx, rax; hHeap
0x18000773e  call    cs:__imp_HeapFree
0x180007744  test    rsi, rsi
0x180007747  jnz     loc_1800076BD
0x18000774d  mov     [rdi], rsi
0x180007750  add     rdi, 8
0x180007754  cmp     rdi, r15
0x180007757  jnz     loc_1800076B5
0x18000775d  add     rsp, 28h
0x180007761  pop     r15
0x180007763  pop     r14
0x180007765  pop     r13
0x180007767  pop     r12
0x180007769  pop     rdi
0x18000776a  pop     rsi
0x18000776b  pop     rbp
0x18000776c  pop     rbx
0x18000776d  retn
```
