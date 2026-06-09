# CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction(void)

- ea: `0x1400254fc`
- end: `0x14002553c`
- name: `??1CEtwEventBracketForLocalFunction@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CEtwEventBracketForLocalFunction *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140025b48`
- `0x140025d5c`
- `0x140025ee4`
- `0x14005f40e`
- `0x14005f48c`
- `0x14005f4d4`

## callees

- `0x1400254fc`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x140025510`
- `ADVAPI32!EventEnabled` at `0x140025510`
- `ADVAPI32!EventWrite` at `0x14002552b`
- `ADVAPI32!EventWrite` at `0x14002552b`

## pseudocode

```c
void __fastcall CEtwEventBracketForLocalFunction::~CEtwEventBracketForLocalFunction(
        CEtwEventBracketForLocalFunction *this)
{
  if ( EventEnabled(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8)) )
    EventWrite(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 8), 1u, (PEVENT_DATA_DESCRIPTOR)this + 2);
}

```

## disassembly

```asm
0x1400254fc  mov     [rsp+arg_0], rbx
0x140025501  push    rdi
0x140025502  sub     rsp, 20h
0x140025506  mov     rbx, rcx
0x140025509  lea     rdx, [rcx+8]; EventDescriptor
0x14002550d  mov     rcx, [rcx]; RegHandle
0x140025510  call    cs:__imp_EventEnabled
0x140025516  test    al, al
0x140025518  jz      short loc_140025531
0x14002551a  mov     rcx, [rbx]; RegHandle
0x14002551d  lea     r9, [rbx+20h]; UserData
0x140025521  mov     r8d, 1; UserDataCount
0x140025527  lea     rdx, [rbx+8]; EventDescriptor
0x14002552b  call    cs:__imp_EventWrite
0x140025531  mov     rbx, [rsp+28h+arg_0]
0x140025536  add     rsp, 20h
0x14002553a  pop     rdi
0x14002553b  retn
```
