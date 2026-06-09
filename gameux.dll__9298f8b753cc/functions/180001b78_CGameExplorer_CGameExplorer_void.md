# CGameExplorer::CGameExplorer(void)

- ea: `0x180001b78`
- end: `0x180001bac`
- name: `??0CGameExplorer@@QEAA@XZ`
- size: `52`
- prototype: `CGameExplorer *__fastcall(CGameExplorer *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f44`
- `0x18000203c`

## pseudocode

```c
CGameExplorer *__fastcall CGameExplorer::CGameExplorer(CGameExplorer *this)
{
  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *(_QWORD *)this = &CGameExplorer::`vftable'{for `IGameExplorer2'};
  *((_QWORD *)this + 1) = &CGameExplorer::`vftable'{for `IGameExplorer'};
  return this;
}

```

## disassembly

```asm
0x180001b78  mov     dword ptr [rcx+10h], 0
0x180001b7f  xor     eax, eax
0x180001b81  xorps   xmm0, xmm0
0x180001b84  movups  xmmword ptr [rcx+18h], xmm0
0x180001b88  movups  xmmword ptr [rcx+28h], xmm0
0x180001b8c  mov     [rcx+38h], rax
0x180001b90  mov     [rcx+40h], al
0x180001b93  lea     rax, ??_7CGameExplorer@@6BIGameExplorer2@@@; const CGameExplorer::`vftable'{for `IGameExplorer2'}
0x180001b9a  mov     [rcx], rax
0x180001b9d  lea     rax, ??_7CGameExplorer@@6BIGameExplorer@@@; const CGameExplorer::`vftable'{for `IGameExplorer'}
0x180001ba4  mov     [rcx+8], rax
0x180001ba8  mov     rax, rcx
0x180001bab  retn
```
