# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180027900`
- end: `0x1800279da`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027848`

## callees

- `0x180027900`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002795b`
- `KERNEL32!HeapFree` at `0x18002798c`
- `KERNEL32!HeapFree` at `0x1800279aa`
- `KERNEL32!HeapFree` at `0x18002795b`
- `KERNEL32!HeapFree` at `0x18002798c`
- `KERNEL32!HeapFree` at `0x1800279aa`
- `KERNEL32!GetProcessHeap` at `0x18002794d`
- `KERNEL32!GetProcessHeap` at `0x18002797e`
- `KERNEL32!GetProcessHeap` at `0x18002799c`
- `KERNEL32!GetProcessHeap` at `0x18002794d`
- `KERNEL32!GetProcessHeap` at `0x18002797e`
- `KERNEL32!GetProcessHeap` at `0x18002799c`

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
0x180027900  push    rbx
0x180027902  push    rbp
0x180027903  push    rsi
0x180027904  push    rdi
0x180027905  push    r12
0x180027907  push    r13
0x180027909  push    r14
0x18002790b  push    r15
0x18002790d  sub     rsp, 28h
0x180027911  mov     rdi, rcx
0x180027914  lea     r15, [rcx+50h]
0x180027918  cmp     rcx, r15
0x18002791b  jz      loc_1800279C9
0x180027921  mov     rsi, [rdi]
0x180027924  jmp     loc_1800279B0
0x180027929  mov     r12, rsi
0x18002792c  mov     r13, rsi
0x18002792f  mov     rsi, [rsi+8]
0x180027933  mov     rbp, [r13+28h]
0x180027937  movzx   eax, word ptr [r13+30h]
0x18002793c  lea     r14, [rax+rax*4]
0x180027940  shl     r14, 4
0x180027944  add     r14, rbp
0x180027947  jmp     short loc_180027975
0x180027949  mov     rbx, [rbp+40h]
0x18002794d  call    cs:__imp_GetProcessHeap
0x180027953  mov     r8, rbx; lpMem
0x180027956  xor     edx, edx; dwFlags
0x180027958  mov     rcx, rax; hHeap
0x18002795b  call    cs:__imp_HeapFree
0x180027961  mov     qword ptr [rbp+40h], 0
0x180027969  mov     qword ptr [rbp+48h], 0
0x180027971  add     rbp, 50h ; 'P'
0x180027975  cmp     rbp, r14
0x180027978  jnz     short loc_180027949
0x18002797a  mov     rbx, [r13+28h]
0x18002797e  call    cs:__imp_GetProcessHeap
0x180027984  mov     r8, rbx; lpMem
0x180027987  xor     edx, edx; dwFlags
0x180027989  mov     rcx, rax; hHeap
0x18002798c  call    cs:__imp_HeapFree
0x180027992  xor     eax, eax
0x180027994  mov     [r13+30h], eax
0x180027998  mov     [r13+28h], rax
0x18002799c  call    cs:__imp_GetProcessHeap
0x1800279a2  mov     rcx, rax; hHeap
0x1800279a5  mov     r8, r12; lpMem
0x1800279a8  xor     edx, edx; dwFlags
0x1800279aa  call    cs:__imp_HeapFree
0x1800279b0  test    rsi, rsi
0x1800279b3  jnz     loc_180027929
0x1800279b9  mov     [rdi], rsi
0x1800279bc  add     rdi, 8
0x1800279c0  cmp     rdi, r15
0x1800279c3  jnz     loc_180027921
0x1800279c9  add     rsp, 28h
0x1800279cd  pop     r15
0x1800279cf  pop     r14
0x1800279d1  pop     r13
0x1800279d3  pop     r12
0x1800279d5  pop     rdi
0x1800279d6  pop     rsi
0x1800279d7  pop     rbp
0x1800279d8  pop     rbx
0x1800279d9  retn
```
