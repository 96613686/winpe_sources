# CEdpNotificationTaskHandler::`vector deleting destructor'(uint)

- ea: `0x1800024b0`
- end: `0x1800024ea`
- name: `??_ECEdpNotificationTaskHandler@@UEAAPEAXI@Z`
- size: `58`
- prototype: `CEdpNotificationTaskHandler *__fastcall(CEdpNotificationTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002408`
- `0x1800024b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800024d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800024d6`

## pseudocode

```c
CEdpNotificationTaskHandler *__fastcall CEdpNotificationTaskHandler::`vector deleting destructor'(
        CEdpNotificationTaskHandler *this,
        char a2)
{
  *(_QWORD *)this = &CEdpNotificationTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800024b0  mov     [rsp+arg_0], rbx
0x1800024b5  push    rdi
0x1800024b6  sub     rsp, 20h
0x1800024ba  lea     rax, ??_7CEdpNotificationTaskHandler@@6B@; const CEdpNotificationTaskHandler::`vftable'
0x1800024c1  mov     ebx, edx
0x1800024c3  mov     [rcx], rax
0x1800024c6  mov     rdi, rcx
0x1800024c9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800024ce  test    bl, 1
0x1800024d1  jz      short loc_1800024DC
0x1800024d3  mov     rcx, rdi
0x1800024d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800024dc  mov     rbx, [rsp+28h+arg_0]
0x1800024e1  mov     rax, rdi
0x1800024e4  add     rsp, 20h
0x1800024e8  pop     rdi
0x1800024e9  retn
```
