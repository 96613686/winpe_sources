# utils::CSqmStream::~CSqmStream(void)

- ea: `0x18000f580`
- end: `0x18000f5ce`
- name: `??1CSqmStream@utils@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(utils::CSqmStream *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6bc`
- `0x18000f620`
- `0x180010803`

## callees

- `0x18000f580`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000f5a0`
- `KERNEL32!GetProcessHeap` at `0x18000f5a0`
- `KERNEL32!HeapFree` at `0x18000f5ae`
- `KERNEL32!HeapFree` at `0x18000f5ae`

## pseudocode

```c
void __fastcall utils::CSqmStream::~CSqmStream(utils::CSqmStream *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 2);
  *(_QWORD *)this = &utils::CSqmStream::`vftable';
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x18000f580  mov     [rsp+arg_0], rbx
0x18000f585  push    rdi
0x18000f586  sub     rsp, 20h
0x18000f58a  mov     rdi, [rcx+10h]
0x18000f58e  lea     rax, ??_7CSqmStream@utils@@6B@; const utils::CSqmStream::`vftable'
0x18000f595  mov     [rcx], rax
0x18000f598  mov     rbx, rcx
0x18000f59b  test    rdi, rdi
0x18000f59e  jz      short loc_18000F5C3
0x18000f5a0  call    cs:__imp_GetProcessHeap
0x18000f5a6  mov     r8, rdi; lpMem
0x18000f5a9  xor     edx, edx; dwFlags
0x18000f5ab  mov     rcx, rax; hHeap
0x18000f5ae  call    cs:__imp_HeapFree
0x18000f5b4  mov     qword ptr [rbx+10h], 0
0x18000f5bc  mov     dword ptr [rbx+0Ch], 0
0x18000f5c3  mov     rbx, [rsp+28h+arg_0]
0x18000f5c8  add     rsp, 20h
0x18000f5cc  pop     rdi
0x18000f5cd  retn
```
