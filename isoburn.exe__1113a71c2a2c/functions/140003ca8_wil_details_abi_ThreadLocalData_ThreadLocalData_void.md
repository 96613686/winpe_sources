# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003ca8`
- end: `0x140003d24`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003888`

## callees

- `0x140003ca8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140003ccd`
- `KERNEL32!GetProcessHeap` at `0x140003cfe`
- `KERNEL32!GetProcessHeap` at `0x140003ccd`
- `KERNEL32!GetProcessHeap` at `0x140003cfe`
- `KERNEL32!HeapFree` at `0x140003cdb`
- `KERNEL32!HeapFree` at `0x140003d0c`
- `KERNEL32!HeapFree` at `0x140003cdb`
- `KERNEL32!HeapFree` at `0x140003d0c`

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
0x140003ca8  push    rbx
0x140003caa  push    rbp
0x140003cab  push    rsi
0x140003cac  push    rdi
0x140003cad  sub     rsp, 28h
0x140003cb1  movzx   eax, word ptr [rcx+20h]
0x140003cb5  mov     rsi, rcx
0x140003cb8  mov     rdi, [rcx+18h]
0x140003cbc  lea     rbp, [rax+rax*4]
0x140003cc0  shl     rbp, 4
0x140003cc4  add     rbp, rdi
0x140003cc7  jmp     short loc_140003CF5
0x140003cc9  mov     rbx, [rdi+40h]
0x140003ccd  call    cs:__imp_GetProcessHeap
0x140003cd3  mov     r8, rbx; lpMem
0x140003cd6  xor     edx, edx; dwFlags
0x140003cd8  mov     rcx, rax; hHeap
0x140003cdb  call    cs:__imp_HeapFree
0x140003ce1  mov     qword ptr [rdi+40h], 0
0x140003ce9  mov     qword ptr [rdi+48h], 0
0x140003cf1  add     rdi, 50h ; 'P'
0x140003cf5  cmp     rdi, rbp
0x140003cf8  jnz     short loc_140003CC9
0x140003cfa  mov     rbx, [rsi+18h]
0x140003cfe  call    cs:__imp_GetProcessHeap
0x140003d04  mov     r8, rbx; lpMem
0x140003d07  xor     edx, edx; dwFlags
0x140003d09  mov     rcx, rax; hHeap
0x140003d0c  call    cs:__imp_HeapFree
0x140003d12  xor     eax, eax
0x140003d14  mov     [rsi+20h], eax
0x140003d17  mov     [rsi+18h], rax
0x140003d1b  add     rsp, 28h
0x140003d1f  pop     rdi
0x140003d20  pop     rsi
0x140003d21  pop     rbp
0x140003d22  pop     rbx
0x140003d23  retn
```
