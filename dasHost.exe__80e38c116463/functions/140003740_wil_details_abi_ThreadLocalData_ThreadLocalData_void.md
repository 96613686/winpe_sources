# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003740`
- end: `0x1400037bc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000312c`

## callees

- `0x140003740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400037a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400037a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003796`

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
0x140003740  push    rbx
0x140003742  push    rbp
0x140003743  push    rsi
0x140003744  push    rdi
0x140003745  sub     rsp, 28h
0x140003749  movzx   eax, word ptr [rcx+20h]
0x14000374d  mov     rsi, rcx
0x140003750  mov     rdi, [rcx+18h]
0x140003754  lea     rbp, [rax+rax*4]
0x140003758  shl     rbp, 4
0x14000375c  add     rbp, rdi
0x14000375f  jmp     short loc_14000378D
0x140003761  mov     rbx, [rdi+40h]
0x140003765  call    cs:__imp_GetProcessHeap
0x14000376b  mov     r8, rbx; lpMem
0x14000376e  xor     edx, edx; dwFlags
0x140003770  mov     rcx, rax; hHeap
0x140003773  call    cs:__imp_HeapFree
0x140003779  mov     qword ptr [rdi+40h], 0
0x140003781  mov     qword ptr [rdi+48h], 0
0x140003789  add     rdi, 50h ; 'P'
0x14000378d  cmp     rdi, rbp
0x140003790  jnz     short loc_140003761
0x140003792  mov     rbx, [rsi+18h]
0x140003796  call    cs:__imp_GetProcessHeap
0x14000379c  mov     r8, rbx; lpMem
0x14000379f  xor     edx, edx; dwFlags
0x1400037a1  mov     rcx, rax; hHeap
0x1400037a4  call    cs:__imp_HeapFree
0x1400037aa  xor     eax, eax
0x1400037ac  mov     [rsi+20h], eax
0x1400037af  mov     [rsi+18h], rax
0x1400037b3  add     rsp, 28h
0x1400037b7  pop     rdi
0x1400037b8  pop     rsi
0x1400037b9  pop     rbp
0x1400037ba  pop     rbx
0x1400037bb  retn
```
