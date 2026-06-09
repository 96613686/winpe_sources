# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180005ae0`
- end: `0x180005bba`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a28`

## callees

- `0x180005ae0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180005b3b`
- `KERNEL32!HeapFree` at `0x180005b6c`
- `KERNEL32!HeapFree` at `0x180005b8a`
- `KERNEL32!HeapFree` at `0x180005b3b`
- `KERNEL32!HeapFree` at `0x180005b6c`
- `KERNEL32!HeapFree` at `0x180005b8a`
- `KERNEL32!GetProcessHeap` at `0x180005b2d`
- `KERNEL32!GetProcessHeap` at `0x180005b5e`
- `KERNEL32!GetProcessHeap` at `0x180005b7c`
- `KERNEL32!GetProcessHeap` at `0x180005b2d`
- `KERNEL32!GetProcessHeap` at `0x180005b5e`
- `KERNEL32!GetProcessHeap` at `0x180005b7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180005ae0  push    rbx
0x180005ae2  push    rbp
0x180005ae3  push    rsi
0x180005ae4  push    rdi
0x180005ae5  push    r12
0x180005ae7  push    r13
0x180005ae9  push    r14
0x180005aeb  push    r15
0x180005aed  sub     rsp, 28h
0x180005af1  mov     rdi, rcx
0x180005af4  lea     r15, [rcx+50h]
0x180005af8  cmp     rcx, r15
0x180005afb  jz      loc_180005BA9
0x180005b01  mov     rsi, [rdi]
0x180005b04  jmp     loc_180005B90
0x180005b09  mov     r12, rsi
0x180005b0c  mov     r13, rsi
0x180005b0f  mov     rsi, [rsi+8]
0x180005b13  mov     rbp, [r13+28h]
0x180005b17  movzx   eax, word ptr [r13+30h]
0x180005b1c  lea     r14, [rax+rax*4]
0x180005b20  shl     r14, 4
0x180005b24  add     r14, rbp
0x180005b27  jmp     short loc_180005B55
0x180005b29  mov     rbx, [rbp+40h]
0x180005b2d  call    cs:__imp_GetProcessHeap
0x180005b33  mov     r8, rbx; lpMem
0x180005b36  xor     edx, edx; dwFlags
0x180005b38  mov     rcx, rax; hHeap
0x180005b3b  call    cs:__imp_HeapFree
0x180005b41  mov     qword ptr [rbp+40h], 0
0x180005b49  mov     qword ptr [rbp+48h], 0
0x180005b51  add     rbp, 50h ; 'P'
0x180005b55  cmp     rbp, r14
0x180005b58  jnz     short loc_180005B29
0x180005b5a  mov     rbx, [r13+28h]
0x180005b5e  call    cs:__imp_GetProcessHeap
0x180005b64  mov     r8, rbx; lpMem
0x180005b67  xor     edx, edx; dwFlags
0x180005b69  mov     rcx, rax; hHeap
0x180005b6c  call    cs:__imp_HeapFree
0x180005b72  xor     eax, eax
0x180005b74  mov     [r13+30h], eax
0x180005b78  mov     [r13+28h], rax
0x180005b7c  call    cs:__imp_GetProcessHeap
0x180005b82  mov     rcx, rax; hHeap
0x180005b85  mov     r8, r12; lpMem
0x180005b88  xor     edx, edx; dwFlags
0x180005b8a  call    cs:__imp_HeapFree
0x180005b90  test    rsi, rsi
0x180005b93  jnz     loc_180005B09
0x180005b99  mov     [rdi], rsi
0x180005b9c  add     rdi, 8
0x180005ba0  cmp     rdi, r15
0x180005ba3  jnz     loc_180005B01
0x180005ba9  add     rsp, 28h
0x180005bad  pop     r15
0x180005baf  pop     r14
0x180005bb1  pop     r13
0x180005bb3  pop     r12
0x180005bb5  pop     rdi
0x180005bb6  pop     rsi
0x180005bb7  pop     rbp
0x180005bb8  pop     rbx
0x180005bb9  retn
```
