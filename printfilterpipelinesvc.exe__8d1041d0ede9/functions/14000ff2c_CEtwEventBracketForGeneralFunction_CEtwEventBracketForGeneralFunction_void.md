# CEtwEventBracketForGeneralFunction::~CEtwEventBracketForGeneralFunction(void)

- ea: `0x14000ff2c`
- end: `0x14000ff72`
- name: `??1CEtwEventBracketForGeneralFunction@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(CEtwEventBracketForGeneralFunction *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ff90`
- `0x14005d960`

## callees

- `0x14000ff2c`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14000ff46`
- `ADVAPI32!EventEnabled` at `0x14000ff46`
- `ADVAPI32!EventWrite` at `0x14000ff61`
- `ADVAPI32!EventWrite` at `0x14000ff61`

## pseudocode

```c
void __fastcall CEtwEventBracketForGeneralFunction::~CEtwEventBracketForGeneralFunction(
        CEtwEventBracketForGeneralFunction *this)
{
  if ( *((_BYTE *)this + 60) )
  {
    if ( EventEnabled(*(_QWORD *)this, (PCEVENT_DESCRIPTOR)((char *)this + 24)) )
      EventWrite(
        *(_QWORD *)this,
        (PCEVENT_DESCRIPTOR)((char *)this + 24),
        1u,
        (PEVENT_DATA_DESCRIPTOR)((char *)this + 40));
  }
}

```

## disassembly

```asm
0x14000ff2c  mov     [rsp+arg_0], rbx
0x14000ff31  push    rdi
0x14000ff32  sub     rsp, 20h
0x14000ff36  cmp     byte ptr [rcx+3Ch], 0
0x14000ff3a  mov     rbx, rcx
0x14000ff3d  jz      short loc_14000FF67
0x14000ff3f  lea     rdx, [rcx+18h]; EventDescriptor
0x14000ff43  mov     rcx, [rcx]; RegHandle
0x14000ff46  call    cs:__imp_EventEnabled
0x14000ff4c  test    al, al
0x14000ff4e  jz      short loc_14000FF67
0x14000ff50  mov     rcx, [rbx]; RegHandle
0x14000ff53  lea     r9, [rbx+28h]; UserData
0x14000ff57  mov     r8d, 1; UserDataCount
0x14000ff5d  lea     rdx, [rbx+18h]; EventDescriptor
0x14000ff61  call    cs:__imp_EventWrite
0x14000ff67  mov     rbx, [rsp+28h+arg_0]
0x14000ff6c  add     rsp, 20h
0x14000ff70  pop     rdi
0x14000ff71  retn
```
