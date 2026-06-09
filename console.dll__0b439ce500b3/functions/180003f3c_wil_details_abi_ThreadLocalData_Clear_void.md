# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x180003f3c`
- end: `0x180003fd1`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bb8`

## callees

- `0x180003f3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f9e`

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
0x180003f3c  push    rbx
0x180003f3e  push    rbp
0x180003f3f  push    rsi
0x180003f40  push    rdi
0x180003f41  sub     rsp, 28h
0x180003f45  movzx   eax, word ptr [rcx+20h]
0x180003f49  mov     rsi, rcx
0x180003f4c  mov     rdi, [rcx+18h]
0x180003f50  lea     rbp, [rax+rax*4]
0x180003f54  shl     rbp, 4
0x180003f58  add     rbp, rdi
0x180003f5b  jmp     short loc_180003F95
0x180003f5d  mov     rbx, [rdi+40h]
0x180003f61  call    cs:__imp_GetProcessHeap
0x180003f68  nop     dword ptr [rax+rax+00h]
0x180003f6d  mov     r8, rbx; lpMem
0x180003f70  xor     edx, edx; dwFlags
0x180003f72  mov     rcx, rax; hHeap
0x180003f75  call    cs:__imp_HeapFree
0x180003f7c  nop     dword ptr [rax+rax+00h]
0x180003f81  mov     qword ptr [rdi+40h], 0
0x180003f89  mov     qword ptr [rdi+48h], 0
0x180003f91  add     rdi, 50h ; 'P'
0x180003f95  cmp     rdi, rbp
0x180003f98  jnz     short loc_180003F5D
0x180003f9a  mov     rbx, [rsi+18h]
0x180003f9e  call    cs:__imp_GetProcessHeap
0x180003fa5  nop     dword ptr [rax+rax+00h]
0x180003faa  mov     r8, rbx; lpMem
0x180003fad  xor     edx, edx; dwFlags
0x180003faf  mov     rcx, rax; hHeap
0x180003fb2  call    cs:__imp_HeapFree
0x180003fb9  nop     dword ptr [rax+rax+00h]
0x180003fbe  xor     eax, eax
0x180003fc0  mov     [rsi+20h], eax
0x180003fc3  mov     [rsi+18h], rax
0x180003fc7  add     rsp, 28h
0x180003fcb  pop     rdi
0x180003fcc  pop     rsi
0x180003fcd  pop     rbp
0x180003fce  pop     rbx
0x180003fcf  retn
```
