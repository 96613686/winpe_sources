# CReAgentTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180001850`
- end: `0x18000188a`
- name: `??_ECReAgentTaskHandler@@UEAAPEAXI@Z`
- size: `58`
- prototype: `void *__fastcall(CReAgentTaskHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180001798`
- `0x180001850`

## pseudocode

```c
CReAgentTaskHandler *__fastcall CReAgentTaskHandler::`vector deleting destructor'(CReAgentTaskHandler *this, char a2)
{
  *(_QWORD *)this = &CReAgentTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001850  mov     [rsp+arg_0], rbx
0x180001855  push    rdi
0x180001856  sub     rsp, 20h
0x18000185a  lea     rax, ??_7CReAgentTaskHandler@@6B@; const CReAgentTaskHandler::`vftable'
0x180001861  mov     ebx, edx
0x180001863  mov     [rcx], rax
0x180001866  mov     rdi, rcx
0x180001869  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x18000186e  test    bl, 1
0x180001871  jz      short loc_18000187B
0x180001873  mov     rcx, rdi; Block
0x180001876  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000187b  mov     rbx, [rsp+28h+arg_0]
0x180001880  mov     rax, rdi
0x180001883  add     rsp, 20h
0x180001887  pop     rdi
0x180001888  retn
```
