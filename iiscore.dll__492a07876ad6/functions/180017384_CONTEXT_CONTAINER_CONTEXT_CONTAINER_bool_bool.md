# CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)

- ea: `0x180017384`
- end: `0x180017402`
- name: `??0CONTEXT_CONTAINER@@QEAA@_N0@Z`
- size: `126`
- prototype: `CONTEXT_CONTAINER *__fastcall(CONTEXT_CONTAINER *__hidden this, bool, bool)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800171ac`
- `0x180017350`
- `0x18001b830`
- `0x18001b978`
- `0x180020e1c`
- `0x180020fac`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800173bf`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800173bf`

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
0x180017384  mov     [rsp+arg_0], rbx
0x180017389  mov     [rsp+arg_8], rsi
0x18001738e  push    rdi
0x18001738f  sub     rsp, 20h
0x180017393  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18001739a  mov     rsi, rcx
0x18001739d  mov     [rcx], rax
0x1800173a0  mov     dil, r8b
0x1800173a3  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x1800173aa  mov     bl, dl
0x1800173ac  mov     [rcx+8], rax
0x1800173b0  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x1800173b7  mov     [rcx+10h], rax
0x1800173bb  add     rcx, 18h
0x1800173bf  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800173c6  nop     dword ptr [rax+rax+00h]
0x1800173cb  xor     eax, eax
0x1800173cd  mov     [rsi+34h], bl
0x1800173d0  mov     rbx, [rsp+28h+arg_0]
0x1800173d5  mov     [rsi+20h], rax
0x1800173d9  mov     [rsi+28h], rax
0x1800173dd  mov     [rsi+30h], eax
0x1800173e0  mov     [rsi+35h], dil
0x1800173e4  mov     [rsi+36h], al
0x1800173e7  mov     [rsi+38h], rax
0x1800173eb  mov     [rsi+40h], rax
0x1800173ef  mov     [rsi+48h], rax
0x1800173f3  mov     rax, rsi
0x1800173f6  mov     rsi, [rsp+28h+arg_8]
0x1800173fb  add     rsp, 20h
0x1800173ff  pop     rdi
0x180017400  retn
```
