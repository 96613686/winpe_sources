# CFileStream::~CFileStream(void)

- ea: `0x1800216fc`
- end: `0x180021729`
- name: `??1CFileStream@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(CFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800216d8`

## callees

- `0x1800218c8`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002171d`

## pseudocode

```c
void __fastcall CFileStream::~CFileStream(CFileStream *this)
{
  *(_QWORD *)this = &CFileStream::`vftable';
  CFileStream::Close(this);
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x1800216fc  push    rbx
0x1800216fe  sub     rsp, 20h
0x180021702  lea     rax, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x180021709  mov     rbx, rcx
0x18002170c  mov     [rcx], rax
0x18002170f  call    ?Close@CFileStream@@QEAAXXZ; CFileStream::Close(void)
0x180021714  lea     rcx, [rbx+10h]
0x180021718  add     rsp, 20h
0x18002171c  pop     rbx
0x18002171d  jmp     cs:__imp_MPDeleteCriticalSection
```
