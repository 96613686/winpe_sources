# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000b518`
- end: `0x18000b594`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b44c`

## callees

- `0x18000b518`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b53d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b56e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b53d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b56e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b57c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b54b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b57c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
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
0x18000b518  push    rbx
0x18000b51a  push    rbp
0x18000b51b  push    rsi
0x18000b51c  push    rdi
0x18000b51d  sub     rsp, 28h
0x18000b521  movzx   eax, word ptr [rcx+20h]
0x18000b525  mov     rsi, rcx
0x18000b528  mov     rdi, [rcx+18h]
0x18000b52c  lea     rbp, [rax+rax*4]
0x18000b530  shl     rbp, 4
0x18000b534  add     rbp, rdi
0x18000b537  jmp     short loc_18000B565
0x18000b539  mov     rbx, [rdi+40h]
0x18000b53d  call    cs:__imp_GetProcessHeap
0x18000b543  mov     r8, rbx; lpMem
0x18000b546  xor     edx, edx; dwFlags
0x18000b548  mov     rcx, rax; hHeap
0x18000b54b  call    cs:__imp_HeapFree
0x18000b551  mov     qword ptr [rdi+40h], 0
0x18000b559  mov     qword ptr [rdi+48h], 0
0x18000b561  add     rdi, 50h ; 'P'
0x18000b565  cmp     rdi, rbp
0x18000b568  jnz     short loc_18000B539
0x18000b56a  mov     rbx, [rsi+18h]
0x18000b56e  call    cs:__imp_GetProcessHeap
0x18000b574  mov     r8, rbx; lpMem
0x18000b577  xor     edx, edx; dwFlags
0x18000b579  mov     rcx, rax; hHeap
0x18000b57c  call    cs:__imp_HeapFree
0x18000b582  xor     eax, eax
0x18000b584  mov     [rsi+20h], eax
0x18000b587  mov     [rsi+18h], rax
0x18000b58b  add     rsp, 28h
0x18000b58f  pop     rdi
0x18000b590  pop     rsi
0x18000b591  pop     rbp
0x18000b592  pop     rbx
0x18000b593  retn
```
