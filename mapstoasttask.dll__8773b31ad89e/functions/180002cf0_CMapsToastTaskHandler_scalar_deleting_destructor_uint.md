# CMapsToastTaskHandler::`scalar deleting destructor'(uint)

- ea: `0x180002cf0`
- end: `0x180002d1f`
- name: `??_GCMapsToastTaskHandler@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CMapsToastTaskHandler *__fastcall(CMapsToastTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001618`
- `0x180002984`
- `0x180002cf0`

## pseudocode

```c
CMapsToastTaskHandler *__fastcall CMapsToastTaskHandler::`scalar deleting destructor'(
        CMapsToastTaskHandler *this,
        char a2)
{
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002cf0  mov     [rsp+arg_0], rbx
0x180002cf5  push    rdi
0x180002cf6  sub     rsp, 20h
0x180002cfa  mov     ebx, edx
0x180002cfc  mov     rdi, rcx
0x180002cff  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180002d04  test    bl, 1
0x180002d07  jz      short loc_180002D11
0x180002d09  mov     rcx, rdi; Block
0x180002d0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d11  mov     rbx, [rsp+28h+arg_0]
0x180002d16  mov     rax, rdi
0x180002d19  add     rsp, 20h
0x180002d1d  pop     rdi
0x180002d1e  retn
```
