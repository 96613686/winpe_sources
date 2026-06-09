# CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)

- ea: `0x180016100`
- end: `0x180016177`
- name: `??0CONTEXT_CONTAINER@@QEAA@_N0@Z`
- size: `119`
- prototype: `CONTEXT_CONTAINER *__fastcall(CONTEXT_CONTAINER *__hidden this, bool, bool)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180015f5c`
- `0x1800160d0`
- `0x18001a234`
- `0x18001a368`
- `0x18001f29c`
- `0x18001f410`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001613b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001613b`

## pseudocode

```c
CONTEXT_CONTAINER *__fastcall CONTEXT_CONTAINER::CONTEXT_CONTAINER(CONTEXT_CONTAINER *this, char a2, char a3)
{
  *(_QWORD *)this = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
  *((_QWORD *)this + 1) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
  *((_QWORD *)this + 2) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
  CReaderWriterLock3::CReaderWriterLock3((CONTEXT_CONTAINER *)((char *)this + 24));
  *((_BYTE *)this + 52) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_BYTE *)this + 53) = a3;
  *((_BYTE *)this + 54) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  return this;
}

```

## disassembly

```asm
0x180016100  mov     [rsp+arg_0], rbx
0x180016105  mov     [rsp+arg_8], rsi
0x18001610a  push    rdi
0x18001610b  sub     rsp, 20h
0x18001610f  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x180016116  mov     rsi, rcx
0x180016119  mov     [rcx], rax
0x18001611c  mov     dil, r8b
0x18001611f  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x180016126  mov     bl, dl
0x180016128  mov     [rcx+8], rax
0x18001612c  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x180016133  mov     [rcx+10h], rax
0x180016137  add     rcx, 18h
0x18001613b  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180016141  xor     eax, eax
0x180016143  mov     [rsi+34h], bl
0x180016146  mov     rbx, [rsp+28h+arg_0]
0x18001614b  mov     [rsi+20h], rax
0x18001614f  mov     [rsi+28h], rax
0x180016153  mov     [rsi+30h], eax
0x180016156  mov     [rsi+35h], dil
0x18001615a  mov     [rsi+36h], al
0x18001615d  mov     [rsi+38h], rax
0x180016161  mov     [rsi+40h], rax
0x180016165  mov     [rsi+48h], rax
0x180016169  mov     rax, rsi
0x18001616c  mov     rsi, [rsp+28h+arg_8]
0x180016171  add     rsp, 20h
0x180016175  pop     rdi
0x180016176  retn
```
