# NCoreLibrary::TCriticalSection::~TCriticalSection(void)

- ea: `0x140016d1c`
- end: `0x140016d3e`
- name: `??1TCriticalSection@NCoreLibrary@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(NCoreLibrary::TCriticalSection *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14005e199`
- `0x14005e1c1`
- `0x14005e34a`
- `0x14005ea13`
- `0x14005ef0b`
- `0x14005fcb4`
- `0x14005fda8`
- `0x14005fdda`
- `0x14005ff9e`
- `0x14006002b`
- `0x1400600f3`
- `0x140061847`
- `0x1400618c7`
- `0x140061d3d`

## callees

- `0x140016d1c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140016d2b`
- `KERNEL32!DeleteCriticalSection` at `0x140016d2b`

## pseudocode

```c
void __fastcall NCoreLibrary::TCriticalSection::~TCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( this[1].LockCount >= 0 )
  {
    DeleteCriticalSection(this);
    this[1].LockCount = -2147467259;
  }
}

```

## disassembly

```asm
0x140016d1c  push    rbx
0x140016d1e  sub     rsp, 20h
0x140016d22  cmp     dword ptr [rcx+30h], 0
0x140016d26  mov     rbx, rcx
0x140016d29  jl      short loc_140016D38
0x140016d2b  call    cs:__imp_DeleteCriticalSection
0x140016d31  mov     dword ptr [rbx+30h], 80004005h
0x140016d38  add     rsp, 20h
0x140016d3c  pop     rbx
0x140016d3d  retn
```
