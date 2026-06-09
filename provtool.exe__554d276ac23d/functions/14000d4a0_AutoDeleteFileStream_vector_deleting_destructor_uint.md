# AutoDeleteFileStream::`vector deleting destructor'(uint)

- ea: `0x14000d4a0`
- end: `0x14000d4d0`
- name: `??_EAutoDeleteFileStream@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(AutoDeleteFileStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14000d394`
- `0x14000d4a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000d4bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000d4bc`

## pseudocode

```c
AutoDeleteFileStream *__fastcall AutoDeleteFileStream::`vector deleting destructor'(
        AutoDeleteFileStream *this,
        char a2)
{
  AutoDeleteFileStream::~AutoDeleteFileStream(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000d4a0  mov     [rsp+arg_0], rbx
0x14000d4a5  push    rdi
0x14000d4a6  sub     rsp, 20h
0x14000d4aa  mov     ebx, edx
0x14000d4ac  mov     rdi, rcx
0x14000d4af  call    ??1AutoDeleteFileStream@@UEAA@XZ; AutoDeleteFileStream::~AutoDeleteFileStream(void)
0x14000d4b4  test    bl, 1
0x14000d4b7  jz      short loc_14000D4C2
0x14000d4b9  mov     rcx, rdi
0x14000d4bc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000d4c2  mov     rbx, [rsp+28h+arg_0]
0x14000d4c7  mov     rax, rdi
0x14000d4ca  add     rsp, 20h
0x14000d4ce  pop     rdi
0x14000d4cf  retn
```
