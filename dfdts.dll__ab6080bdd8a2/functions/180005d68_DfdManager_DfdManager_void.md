# DfdManager::~DfdManager(void)

- ea: `0x180005d68`
- end: `0x180005da5`
- name: `??1DfdManager@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(DfdManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002450`
- `0x180002790`
- `0x180002ed8`

## callees

- `0x180005d68`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005d7e`
- `KERNEL32!GetProcessHeap` at `0x180005d7e`
- `KERNEL32!HeapFree` at `0x180005d8c`
- `KERNEL32!HeapFree` at `0x180005d8c`

## pseudocode

```c
void __fastcall DfdManager::~DfdManager(DfdManager *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 3);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180005d68  mov     [rsp+arg_0], rbx
0x180005d6d  push    rdi
0x180005d6e  sub     rsp, 20h
0x180005d72  mov     rdi, [rcx+18h]
0x180005d76  mov     rbx, rcx
0x180005d79  test    rdi, rdi
0x180005d7c  jz      short loc_180005D9A
0x180005d7e  call    cs:__imp_GetProcessHeap
0x180005d84  mov     r8, rdi; lpMem
0x180005d87  xor     edx, edx; dwFlags
0x180005d89  mov     rcx, rax; hHeap
0x180005d8c  call    cs:__imp_HeapFree
0x180005d92  mov     qword ptr [rbx+18h], 0
0x180005d9a  mov     rbx, [rsp+28h+arg_0]
0x180005d9f  add     rsp, 20h
0x180005da3  pop     rdi
0x180005da4  retn
```
