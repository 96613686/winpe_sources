# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003b18`
- end: `0x180003b94`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003900`

## callees

- `0x180003b18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b7c`

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
0x180003b18  push    rbx
0x180003b1a  push    rbp
0x180003b1b  push    rsi
0x180003b1c  push    rdi
0x180003b1d  sub     rsp, 28h
0x180003b21  movzx   eax, word ptr [rcx+20h]
0x180003b25  mov     rsi, rcx
0x180003b28  mov     rdi, [rcx+18h]
0x180003b2c  lea     rbp, [rax+rax*4]
0x180003b30  shl     rbp, 4
0x180003b34  add     rbp, rdi
0x180003b37  jmp     short loc_180003B65
0x180003b39  mov     rbx, [rdi+40h]
0x180003b3d  call    cs:__imp_GetProcessHeap
0x180003b43  mov     r8, rbx; lpMem
0x180003b46  xor     edx, edx; dwFlags
0x180003b48  mov     rcx, rax; hHeap
0x180003b4b  call    cs:__imp_HeapFree
0x180003b51  mov     qword ptr [rdi+40h], 0
0x180003b59  mov     qword ptr [rdi+48h], 0
0x180003b61  add     rdi, 50h ; 'P'
0x180003b65  cmp     rdi, rbp
0x180003b68  jnz     short loc_180003B39
0x180003b6a  mov     rbx, [rsi+18h]
0x180003b6e  call    cs:__imp_GetProcessHeap
0x180003b74  mov     r8, rbx; lpMem
0x180003b77  xor     edx, edx; dwFlags
0x180003b79  mov     rcx, rax; hHeap
0x180003b7c  call    cs:__imp_HeapFree
0x180003b82  xor     eax, eax
0x180003b84  mov     [rsi+20h], eax
0x180003b87  mov     [rsi+18h], rax
0x180003b8b  add     rsp, 28h
0x180003b8f  pop     rdi
0x180003b90  pop     rsi
0x180003b91  pop     rbp
0x180003b92  pop     rbx
0x180003b93  retn
```
