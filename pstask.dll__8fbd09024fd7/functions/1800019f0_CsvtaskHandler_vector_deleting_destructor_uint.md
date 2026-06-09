# CsvtaskHandler::`vector deleting destructor'(uint)

- ea: `0x1800019f0`
- end: `0x180001a29`
- name: `??_ECsvtaskHandler@@UEAAPEAXI@Z`
- size: `57`
- prototype: `CsvtaskHandler *__fastcall(CsvtaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180001948`
- `0x1800019f0`

## pseudocode

```c
CsvtaskHandler *__fastcall CsvtaskHandler::`vector deleting destructor'(CsvtaskHandler *this, char a2)
{
  *(_QWORD *)this = &CsvtaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800019f0  mov     [rsp+arg_0], rbx
0x1800019f5  push    rdi
0x1800019f6  sub     rsp, 20h
0x1800019fa  lea     rax, ??_7CsvtaskHandler@@6B@; const CsvtaskHandler::`vftable'
0x180001a01  mov     ebx, edx
0x180001a03  mov     [rcx], rax
0x180001a06  mov     rdi, rcx
0x180001a09  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180001a0e  test    bl, 1
0x180001a11  jz      short loc_180001A1B
0x180001a13  mov     rcx, rdi; Block
0x180001a16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001a1b  mov     rbx, [rsp+28h+arg_0]
0x180001a20  mov     rax, rdi
0x180001a23  add     rsp, 20h
0x180001a27  pop     rdi
0x180001a28  retn
```
