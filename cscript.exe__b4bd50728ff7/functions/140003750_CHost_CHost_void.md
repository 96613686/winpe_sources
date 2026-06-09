# CHost::CHost(void)

- ea: `0x140003750`
- end: `0x140003806`
- name: `??0CHost@@QEAA@XZ`
- size: `182`
- prototype: `CHost *__fastcall(CHost *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034b4`

## callees

- `0x1400093c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400037e8`
- `KERNEL32!GetCurrentThreadId` at `0x1400037e8`

## pseudocode

```c
CHost *__fastcall CHost::CHost(CHost *this)
{
  CHost *result; // rax

  *(_QWORD *)this = &CHost::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *(_QWORD *)((char *)this + 60) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  CCriticalSection::CCriticalSection((CHost *)((char *)this + 696));
  *((_WORD *)this + 40) = 0;
  *((_DWORD *)this + 14) = GetCurrentThreadId();
  result = this;
  g_pHost = this;
  return result;
}

```

## disassembly

```asm
0x140003750  mov     [rsp+arg_0], rbx
0x140003755  push    rdi
0x140003756  sub     rsp, 20h
0x14000375a  xor     edi, edi
0x14000375c  lea     rax, ??_7CHost@@6B@; const CHost::`vftable'
0x140003763  mov     [rcx], rax
0x140003766  mov     rbx, rcx
0x140003769  mov     [rcx+8], edi
0x14000376c  mov     [rcx+10h], rdi
0x140003770  mov     [rcx+18h], rdi
0x140003774  mov     [rcx+20h], rdi
0x140003778  mov     [rcx+28h], rdi
0x14000377c  mov     [rcx+30h], rdi
0x140003780  mov     [rcx+3Ch], rdi
0x140003784  mov     [rcx+44h], edi
0x140003787  mov     [rcx+48h], rdi
0x14000378b  mov     [rcx+260h], rdi
0x140003792  mov     [rcx+268h], rdi
0x140003799  mov     [rcx+270h], rdi
0x1400037a0  mov     [rcx+278h], rdi
0x1400037a7  mov     [rcx+280h], rdi
0x1400037ae  mov     [rcx+288h], rdi
0x1400037b5  mov     [rcx+290h], rdi
0x1400037bc  mov     [rcx+298h], rdi
0x1400037c3  mov     [rcx+2A0h], rdi
0x1400037ca  mov     [rcx+2A8h], rdi
0x1400037d1  mov     [rcx+2B0h], rdi
0x1400037d8  add     rcx, 2B8h; this
0x1400037df  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x1400037e4  mov     [rbx+50h], di
0x1400037e8  call    cs:__imp_GetCurrentThreadId
0x1400037ee  mov     [rbx+38h], eax
0x1400037f1  mov     rax, rbx
0x1400037f4  mov     cs:?g_pHost@@3PEAVCHost@@EA, rbx; CHost * g_pHost
0x1400037fb  mov     rbx, [rsp+28h+arg_0]
0x140003800  add     rsp, 20h
0x140003804  pop     rdi
0x140003805  retn
```
