# CCommand::CCommand(void)

- ea: `0x180002170`
- end: `0x1800021a5`
- name: `??0CCommand@@AEAA@XZ`
- size: `53`
- prototype: `CCommand *__fastcall(CCommand *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800019f0`
- `0x1800020d0`

## pseudocode

```c
CCommand *__fastcall CCommand::CCommand(CCommand *this)
{
  *((_DWORD *)this + 10) = 1;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &CCommand::`vftable'{for `CCommandImpl'};
  *((_QWORD *)this + 4) = &CCommand::`vftable'{for `IHCCommand'};
  _InterlockedIncrement(&g_cLocks);
  return this;
}

```

## disassembly

```asm
0x180002170  xor     eax, eax
0x180002172  mov     dword ptr [rcx+28h], 1
0x180002179  mov     [rcx+8], rax
0x18000217d  mov     [rcx+10h], rax
0x180002181  mov     [rcx+18h], rax
0x180002185  lea     rax, ??_7CCommand@@6BCCommandImpl@@@; const CCommand::`vftable'{for `CCommandImpl'}
0x18000218c  mov     [rcx], rax
0x18000218f  lea     rax, ??_7CCommand@@6BIHCCommand@@@; const CCommand::`vftable'{for `IHCCommand'}
0x180002196  mov     [rcx+20h], rax
0x18000219a  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x1800021a1  mov     rax, rcx
0x1800021a4  retn
```
