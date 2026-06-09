# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180008634`
- end: `0x1800086b0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008068`

## callees

- `0x180008634`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008667`
- `KERNEL32!HeapFree` at `0x180008698`
- `KERNEL32!HeapFree` at `0x180008667`
- `KERNEL32!HeapFree` at `0x180008698`
- `KERNEL32!GetProcessHeap` at `0x180008659`
- `KERNEL32!GetProcessHeap` at `0x18000868a`
- `KERNEL32!GetProcessHeap` at `0x180008659`
- `KERNEL32!GetProcessHeap` at `0x18000868a`

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
0x180008634  push    rbx
0x180008636  push    rbp
0x180008637  push    rsi
0x180008638  push    rdi
0x180008639  sub     rsp, 28h
0x18000863d  movzx   eax, word ptr [rcx+20h]
0x180008641  mov     rsi, rcx
0x180008644  mov     rdi, [rcx+18h]
0x180008648  lea     rbp, [rax+rax*4]
0x18000864c  shl     rbp, 4
0x180008650  add     rbp, rdi
0x180008653  jmp     short loc_180008681
0x180008655  mov     rbx, [rdi+40h]
0x180008659  call    cs:__imp_GetProcessHeap
0x18000865f  mov     r8, rbx; lpMem
0x180008662  xor     edx, edx; dwFlags
0x180008664  mov     rcx, rax; hHeap
0x180008667  call    cs:__imp_HeapFree
0x18000866d  mov     qword ptr [rdi+40h], 0
0x180008675  mov     qword ptr [rdi+48h], 0
0x18000867d  add     rdi, 50h ; 'P'
0x180008681  cmp     rdi, rbp
0x180008684  jnz     short loc_180008655
0x180008686  mov     rbx, [rsi+18h]
0x18000868a  call    cs:__imp_GetProcessHeap
0x180008690  mov     r8, rbx; lpMem
0x180008693  xor     edx, edx; dwFlags
0x180008695  mov     rcx, rax; hHeap
0x180008698  call    cs:__imp_HeapFree
0x18000869e  xor     eax, eax
0x1800086a0  mov     [rsi+20h], eax
0x1800086a3  mov     [rsi+18h], rax
0x1800086a7  add     rsp, 28h
0x1800086ab  pop     rdi
0x1800086ac  pop     rsi
0x1800086ad  pop     rbp
0x1800086ae  pop     rbx
0x1800086af  retn
```
