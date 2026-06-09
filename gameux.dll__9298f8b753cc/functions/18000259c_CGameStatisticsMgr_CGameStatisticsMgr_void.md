# CGameStatisticsMgr::CGameStatisticsMgr(void)

- ea: `0x18000259c`
- end: `0x1800025b1`
- name: `??0CGameStatisticsMgr@@QEAA@XZ`
- size: `21`
- prototype: `CGameStatisticsMgr *__fastcall(CGameStatisticsMgr *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002558`
- `0x180002914`

## pseudocode

```c
CGameStatisticsMgr *__fastcall CGameStatisticsMgr::CGameStatisticsMgr(CGameStatisticsMgr *this)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CGameStatisticsMgr::`vftable';
  return this;
}

```

## disassembly

```asm
0x18000259c  lea     rax, ??_7CGameStatisticsMgr@@6B@; const CGameStatisticsMgr::`vftable'
0x1800025a3  mov     dword ptr [rcx+8], 0
0x1800025aa  mov     [rcx], rax
0x1800025ad  mov     rax, rcx
0x1800025b0  retn
```
