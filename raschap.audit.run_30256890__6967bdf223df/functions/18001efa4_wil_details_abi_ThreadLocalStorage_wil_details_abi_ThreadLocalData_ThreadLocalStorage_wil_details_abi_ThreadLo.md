# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18001efa4`
- end: `0x18001f07e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ef44`

## callees

- `0x18001efa4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f022`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f022`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001efff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f04e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001efff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f04e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001efa4  push    rbx
0x18001efa6  push    rbp
0x18001efa7  push    rsi
0x18001efa8  push    rdi
0x18001efa9  push    r12
0x18001efab  push    r13
0x18001efad  push    r14
0x18001efaf  push    r15
0x18001efb1  sub     rsp, 28h
0x18001efb5  mov     rdi, rcx
0x18001efb8  lea     r15, [rcx+50h]
0x18001efbc  cmp     rcx, r15
0x18001efbf  jz      loc_18001F06D
0x18001efc5  mov     rsi, [rdi]
0x18001efc8  jmp     loc_18001F054
0x18001efcd  mov     r12, rsi
0x18001efd0  mov     r13, rsi
0x18001efd3  mov     rsi, [rsi+8]
0x18001efd7  mov     rbp, [r13+28h]
0x18001efdb  movzx   eax, word ptr [r13+30h]
0x18001efe0  lea     r14, [rax+rax*4]
0x18001efe4  shl     r14, 4
0x18001efe8  add     r14, rbp
0x18001efeb  jmp     short loc_18001F019
0x18001efed  mov     rbx, [rbp+40h]
0x18001eff1  call    cs:__imp_GetProcessHeap
0x18001eff7  mov     r8, rbx; lpMem
0x18001effa  xor     edx, edx; dwFlags
0x18001effc  mov     rcx, rax; hHeap
0x18001efff  call    cs:__imp_HeapFree
0x18001f005  mov     qword ptr [rbp+40h], 0
0x18001f00d  mov     qword ptr [rbp+48h], 0
0x18001f015  add     rbp, 50h ; 'P'
0x18001f019  cmp     rbp, r14
0x18001f01c  jnz     short loc_18001EFED
0x18001f01e  mov     rbx, [r13+28h]
0x18001f022  call    cs:__imp_GetProcessHeap
0x18001f028  mov     r8, rbx; lpMem
0x18001f02b  xor     edx, edx; dwFlags
0x18001f02d  mov     rcx, rax; hHeap
0x18001f030  call    cs:__imp_HeapFree
0x18001f036  xor     eax, eax
0x18001f038  mov     [r13+30h], eax
0x18001f03c  mov     [r13+28h], rax
0x18001f040  call    cs:__imp_GetProcessHeap
0x18001f046  mov     rcx, rax; hHeap
0x18001f049  mov     r8, r12; lpMem
0x18001f04c  xor     edx, edx; dwFlags
0x18001f04e  call    cs:__imp_HeapFree
0x18001f054  test    rsi, rsi
0x18001f057  jnz     loc_18001EFCD
0x18001f05d  mov     [rdi], rsi
0x18001f060  add     rdi, 8
0x18001f064  cmp     rdi, r15
0x18001f067  jnz     loc_18001EFC5
0x18001f06d  add     rsp, 28h
0x18001f071  pop     r15
0x18001f073  pop     r14
0x18001f075  pop     r13
0x18001f077  pop     r12
0x18001f079  pop     rdi
0x18001f07a  pop     rsi
0x18001f07b  pop     rbp
0x18001f07c  pop     rbx
0x18001f07d  retn
```
