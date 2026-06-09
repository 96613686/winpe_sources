# CDsregTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180001ec0`
- end: `0x180001efe`
- name: `??_ECDsregTaskHandler@@UEAAPEAXI@Z`
- size: `62`
- prototype: `CDsregTaskHandler *__fastcall(CDsregTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001830`
- `0x180001e10`
- `0x180001ec0`

## pseudocode

```c
CDsregTaskHandler *__fastcall CDsregTaskHandler::`vector deleting destructor'(CDsregTaskHandler *this, char a2)
{
  *(_QWORD *)this = &CDsregTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001ec0  mov     [rsp+arg_0], rbx
0x180001ec5  push    rdi
0x180001ec6  sub     rsp, 20h
0x180001eca  lea     rax, ??_7CDsregTaskHandler@@6B@; const CDsregTaskHandler::`vftable'
0x180001ed1  mov     ebx, edx
0x180001ed3  mov     [rcx], rax
0x180001ed6  mov     rdi, rcx
0x180001ed9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180001ede  test    bl, 1
0x180001ee1  jz      short loc_180001EF0
0x180001ee3  mov     edx, 38h ; '8'; unsigned __int64
0x180001ee8  mov     rcx, rdi; void *
0x180001eeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001ef0  mov     rbx, [rsp+28h+arg_0]
0x180001ef5  mov     rax, rdi
0x180001ef8  add     rsp, 20h
0x180001efc  pop     rdi
0x180001efd  retn
```
