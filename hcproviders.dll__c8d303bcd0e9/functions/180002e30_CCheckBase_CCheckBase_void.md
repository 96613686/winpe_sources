# CCheckBase::CCheckBase(void)

- ea: `0x180002e30`
- end: `0x180002e9c`
- name: `??0CCheckBase@@IEAA@XZ`
- size: `108`
- prototype: `CCheckBase *__fastcall(CCheckBase *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002650`
- `0x180008768`

## pseudocode

```c
CCheckBase *__fastcall CCheckBase::CCheckBase(CCheckBase *this)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CCheckBase::`vftable';
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = 0;
  _InterlockedIncrement(&g_cLocks);
  return this;
}

```

## disassembly

```asm
0x180002e30  lea     rax, ??_7CCheckBase@@6B@; const CCheckBase::`vftable'
0x180002e37  mov     dword ptr [rcx+8], 1
0x180002e3e  mov     [rcx], rax
0x180002e41  xor     eax, eax
0x180002e43  mov     [rcx+90h], rax
0x180002e4a  mov     [rcx+98h], rax
0x180002e51  mov     [rcx+0A0h], rax
0x180002e58  mov     [rcx+0A8h], rax
0x180002e5f  mov     [rcx+0B0h], rax
0x180002e66  mov     [rcx+0B8h], rax
0x180002e6d  mov     [rcx+0C0h], rax
0x180002e74  mov     [rcx+0C8h], rax
0x180002e7b  mov     [rcx+0D0h], rax
0x180002e82  mov     [rcx+0D8h], rax
0x180002e89  mov     [rcx+10h], rax
0x180002e8d  mov     [rcx+18h], ax
0x180002e91  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180002e98  mov     rax, rcx
0x180002e9b  retn
```
