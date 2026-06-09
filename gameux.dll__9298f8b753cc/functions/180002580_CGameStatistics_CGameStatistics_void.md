# CGameStatistics::CGameStatistics(void)

- ea: `0x180002580`
- end: `0x180002595`
- name: `??0CGameStatistics@@QEAA@XZ`
- size: `21`
- prototype: `CGameStatistics *__fastcall(CGameStatistics *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002788`

## pseudocode

```c
CGameStatistics *__fastcall CGameStatistics::CGameStatistics(CGameStatistics *this)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CGameStatistics::`vftable';
  return this;
}

```

## disassembly

```asm
0x180002580  lea     rax, ??_7CGameStatistics@@6B@; const CGameStatistics::`vftable'
0x180002587  mov     dword ptr [rcx+8], 0
0x18000258e  mov     [rcx], rax
0x180002591  mov     rax, rcx
0x180002594  retn
```
