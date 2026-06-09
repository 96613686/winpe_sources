# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x180006860`
- end: `0x1800068f5`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064d4`

## callees

- `0x180006860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006899`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d6`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180006860  push    rbx
0x180006862  push    rbp
0x180006863  push    rsi
0x180006864  push    rdi
0x180006865  sub     rsp, 28h
0x180006869  movzx   eax, word ptr [rcx+20h]
0x18000686d  mov     rsi, rcx
0x180006870  mov     rdi, [rcx+18h]
0x180006874  lea     rbp, [rax+rax*4]
0x180006878  shl     rbp, 4
0x18000687c  add     rbp, rdi
0x18000687f  jmp     short loc_1800068B9
0x180006881  mov     rbx, [rdi+40h]
0x180006885  call    cs:__imp_GetProcessHeap
0x18000688c  nop     dword ptr [rax+rax+00h]
0x180006891  mov     r8, rbx; lpMem
0x180006894  xor     edx, edx; dwFlags
0x180006896  mov     rcx, rax; hHeap
0x180006899  call    cs:__imp_HeapFree
0x1800068a0  nop     dword ptr [rax+rax+00h]
0x1800068a5  mov     qword ptr [rdi+40h], 0
0x1800068ad  mov     qword ptr [rdi+48h], 0
0x1800068b5  add     rdi, 50h ; 'P'
0x1800068b9  cmp     rdi, rbp
0x1800068bc  jnz     short loc_180006881
0x1800068be  mov     rbx, [rsi+18h]
0x1800068c2  call    cs:__imp_GetProcessHeap
0x1800068c9  nop     dword ptr [rax+rax+00h]
0x1800068ce  mov     r8, rbx; lpMem
0x1800068d1  xor     edx, edx; dwFlags
0x1800068d3  mov     rcx, rax; hHeap
0x1800068d6  call    cs:__imp_HeapFree
0x1800068dd  nop     dword ptr [rax+rax+00h]
0x1800068e2  xor     eax, eax
0x1800068e4  mov     [rsi+20h], eax
0x1800068e7  mov     [rsi+18h], rax
0x1800068eb  add     rsp, 28h
0x1800068ef  pop     rdi
0x1800068f0  pop     rsi
0x1800068f1  pop     rbp
0x1800068f2  pop     rbx
0x1800068f3  retn
```
