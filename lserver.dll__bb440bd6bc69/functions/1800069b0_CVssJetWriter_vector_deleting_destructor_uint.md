# CVssJetWriter::`vector deleting destructor'(uint)

- ea: `0x1800069b0`
- end: `0x180006a2f`
- name: `??_ECVssJetWriter@@UEAAPEAXI@Z`
- size: `127`
- prototype: `void *__fastcall(CVssJetWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000280c`
- `0x1800069b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006a0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006a0f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069eb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069eb`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x1800069fc`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x1800069d0`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x1800069fc`

## pseudocode

```c
CVssJetWriter *__fastcall CVssJetWriter::`vector deleting destructor'(CVssJetWriter *this, char a2)
{
  int v3; // esi
  char *v4; // rdi

  v3 = a2 & 1;
  if ( (a2 & 2) != 0 )
  {
    v4 = (char *)this - 8;
    `eh vector destructor iterator'(this, 0x18u, *((_QWORD *)this - 1), CVssJetWriter::~CVssJetWriter);
    if ( v3 )
      operator delete[](v4);
    return (CVssJetWriter *)v4;
  }
  else
  {
    CVssJetWriter::~CVssJetWriter(this);
    if ( v3 )
      operator delete(this);
    return this;
  }
}

```

## disassembly

```asm
0x1800069b0  mov     [rsp+arg_0], rbx
0x1800069b5  mov     [rsp+arg_8], rsi
0x1800069ba  push    rdi
0x1800069bb  sub     rsp, 20h
0x1800069bf  mov     rbx, rcx
0x1800069c2  mov     esi, edx
0x1800069c4  and     esi, 1
0x1800069c7  test    dl, 2
0x1800069ca  jz      short loc_1800069FC
0x1800069cc  lea     rdi, [rcx-8]
0x1800069d0  mov     r9, cs:__imp_??1CVssJetWriter@@UEAA@XZ; void (*)(void *)
0x1800069d7  mov     r8, [rdi]; unsigned __int64
0x1800069da  mov     edx, 18h; unsigned __int64
0x1800069df  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800069e4  test    esi, esi
0x1800069e6  jz      short loc_1800069F7
0x1800069e8  mov     rcx, rdi
0x1800069eb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800069f2  nop     dword ptr [rax+rax+00h]
0x1800069f7  mov     rax, rdi
0x1800069fa  jmp     short loc_180006A1E
0x1800069fc  call    cs:__imp_??1CVssJetWriter@@UEAA@XZ; CVssJetWriter::~CVssJetWriter(void)
0x180006a03  nop     dword ptr [rax+rax+00h]
0x180006a08  test    esi, esi
0x180006a0a  jz      short loc_180006A1B
0x180006a0c  mov     rcx, rbx
0x180006a0f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006a16  nop     dword ptr [rax+rax+00h]
0x180006a1b  mov     rax, rbx
0x180006a1e  mov     rbx, [rsp+28h+arg_0]
0x180006a23  mov     rsi, [rsp+28h+arg_8]
0x180006a28  add     rsp, 20h
0x180006a2c  pop     rdi
0x180006a2d  retn
```
