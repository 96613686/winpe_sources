# AutoThreadpool::`vector deleting destructor'(uint)

- ea: `0x140015100`
- end: `0x140015137`
- name: `??_EAutoThreadpool@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(AutoThreadpool *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400150b8`
- `0x140015100`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14001511c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001511c`

## pseudocode

```c
AutoThreadpool *__fastcall AutoThreadpool::`vector deleting destructor'(AutoThreadpool *this, char a2)
{
  AutoThreadpool::~AutoThreadpool(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140015100  mov     [rsp+arg_0], rbx
0x140015105  push    rdi
0x140015106  sub     rsp, 20h
0x14001510a  mov     ebx, edx
0x14001510c  mov     rdi, rcx
0x14001510f  call    ??1AutoThreadpool@@UEAA@XZ; AutoThreadpool::~AutoThreadpool(void)
0x140015114  test    bl, 1
0x140015117  jz      short loc_140015128
0x140015119  mov     rcx, rdi
0x14001511c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140015123  nop     dword ptr [rax+rax+00h]
0x140015128  mov     rbx, [rsp+28h+arg_0]
0x14001512d  mov     rax, rdi
0x140015130  add     rsp, 20h
0x140015134  pop     rdi
0x140015135  retn
```
