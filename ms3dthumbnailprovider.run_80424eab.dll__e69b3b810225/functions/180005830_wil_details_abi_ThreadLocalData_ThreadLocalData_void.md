# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005830`
- end: `0x1800058ac`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005338`

## callees

- `0x180005830`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180005863`
- `KERNEL32!HeapFree` at `0x180005894`
- `KERNEL32!HeapFree` at `0x180005863`
- `KERNEL32!HeapFree` at `0x180005894`
- `KERNEL32!GetProcessHeap` at `0x180005855`
- `KERNEL32!GetProcessHeap` at `0x180005886`
- `KERNEL32!GetProcessHeap` at `0x180005855`
- `KERNEL32!GetProcessHeap` at `0x180005886`

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
0x180005830  push    rbx
0x180005832  push    rbp
0x180005833  push    rsi
0x180005834  push    rdi
0x180005835  sub     rsp, 28h
0x180005839  movzx   eax, word ptr [rcx+20h]
0x18000583d  mov     rsi, rcx
0x180005840  mov     rdi, [rcx+18h]
0x180005844  lea     rbp, [rax+rax*4]
0x180005848  shl     rbp, 4
0x18000584c  add     rbp, rdi
0x18000584f  jmp     short loc_18000587D
0x180005851  mov     rbx, [rdi+40h]
0x180005855  call    cs:__imp_GetProcessHeap
0x18000585b  mov     r8, rbx; lpMem
0x18000585e  xor     edx, edx; dwFlags
0x180005860  mov     rcx, rax; hHeap
0x180005863  call    cs:__imp_HeapFree
0x180005869  mov     qword ptr [rdi+40h], 0
0x180005871  mov     qword ptr [rdi+48h], 0
0x180005879  add     rdi, 50h ; 'P'
0x18000587d  cmp     rdi, rbp
0x180005880  jnz     short loc_180005851
0x180005882  mov     rbx, [rsi+18h]
0x180005886  call    cs:__imp_GetProcessHeap
0x18000588c  mov     r8, rbx; lpMem
0x18000588f  xor     edx, edx; dwFlags
0x180005891  mov     rcx, rax; hHeap
0x180005894  call    cs:__imp_HeapFree
0x18000589a  xor     eax, eax
0x18000589c  mov     [rsi+20h], eax
0x18000589f  mov     [rsi+18h], rax
0x1800058a3  add     rsp, 28h
0x1800058a7  pop     rdi
0x1800058a8  pop     rsi
0x1800058a9  pop     rbp
0x1800058aa  pop     rbx
0x1800058ab  retn
```
