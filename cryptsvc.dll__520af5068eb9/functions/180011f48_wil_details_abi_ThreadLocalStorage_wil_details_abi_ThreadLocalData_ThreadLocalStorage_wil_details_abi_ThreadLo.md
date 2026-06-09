# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180011f48`
- end: `0x180012022`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e90`

## callees

- `0x180011f48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fe4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fe4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ff2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ff2`

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
0x180011f48  push    rbx
0x180011f4a  push    rbp
0x180011f4b  push    rsi
0x180011f4c  push    rdi
0x180011f4d  push    r12
0x180011f4f  push    r13
0x180011f51  push    r14
0x180011f53  push    r15
0x180011f55  sub     rsp, 28h
0x180011f59  lea     r15, [rcx+50h]
0x180011f5d  mov     rdi, rcx
0x180011f60  cmp     rcx, r15
0x180011f63  jz      loc_180012011
0x180011f69  mov     rsi, [rdi]
0x180011f6c  jmp     loc_180011FF8
0x180011f71  mov     r13, rsi
0x180011f74  mov     r12, rsi
0x180011f77  mov     rsi, [rsi+8]
0x180011f7b  movzx   eax, word ptr [r13+30h]
0x180011f80  mov     rbp, [r13+28h]
0x180011f84  lea     r14, [rax+rax*4]
0x180011f88  shl     r14, 4
0x180011f8c  add     r14, rbp
0x180011f8f  jmp     short loc_180011FBD
0x180011f91  mov     rbx, [rbp+40h]
0x180011f95  call    cs:__imp_GetProcessHeap
0x180011f9b  mov     r8, rbx; lpMem
0x180011f9e  xor     edx, edx; dwFlags
0x180011fa0  mov     rcx, rax; hHeap
0x180011fa3  call    cs:__imp_HeapFree
0x180011fa9  mov     qword ptr [rbp+40h], 0
0x180011fb1  mov     qword ptr [rbp+48h], 0
0x180011fb9  add     rbp, 50h ; 'P'
0x180011fbd  cmp     rbp, r14
0x180011fc0  jnz     short loc_180011F91
0x180011fc2  mov     rbx, [r13+28h]
0x180011fc6  call    cs:__imp_GetProcessHeap
0x180011fcc  mov     r8, rbx; lpMem
0x180011fcf  xor     edx, edx; dwFlags
0x180011fd1  mov     rcx, rax; hHeap
0x180011fd4  call    cs:__imp_HeapFree
0x180011fda  xor     eax, eax
0x180011fdc  mov     [r13+30h], eax
0x180011fe0  mov     [r13+28h], rax
0x180011fe4  call    cs:__imp_GetProcessHeap
0x180011fea  mov     r8, r12; lpMem
0x180011fed  xor     edx, edx; dwFlags
0x180011fef  mov     rcx, rax; hHeap
0x180011ff2  call    cs:__imp_HeapFree
0x180011ff8  test    rsi, rsi
0x180011ffb  jnz     loc_180011F71
0x180012001  mov     [rdi], rsi
0x180012004  add     rdi, 8
0x180012008  cmp     rdi, r15
0x18001200b  jnz     loc_180011F69
0x180012011  add     rsp, 28h
0x180012015  pop     r15
0x180012017  pop     r14
0x180012019  pop     r13
0x18001201b  pop     r12
0x18001201d  pop     rdi
0x18001201e  pop     rsi
0x18001201f  pop     rbp
0x180012020  pop     rbx
0x180012021  retn
```
