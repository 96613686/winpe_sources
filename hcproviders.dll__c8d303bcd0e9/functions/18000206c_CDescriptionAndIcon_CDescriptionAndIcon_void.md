# CDescriptionAndIcon::CDescriptionAndIcon(void)

- ea: `0x18000206c`
- end: `0x180002098`
- name: `??0CDescriptionAndIcon@@AEAA@XZ`
- size: `44`
- prototype: `CDescriptionAndIcon *__fastcall(CDescriptionAndIcon *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001490`
- `0x1800019f0`

## pseudocode

```c
CDescriptionAndIcon *__fastcall CDescriptionAndIcon::CDescriptionAndIcon(CDescriptionAndIcon *this)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CDescriptionAndIcon::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  _InterlockedIncrement(&g_cLocks);
  return this;
}

```

## disassembly

```asm
0x18000206c  lea     rax, ??_7CDescriptionAndIcon@@6B@; const CDescriptionAndIcon::`vftable'
0x180002073  mov     dword ptr [rcx+8], 1
0x18000207a  mov     [rcx], rax
0x18000207d  mov     qword ptr [rcx+10h], 0
0x180002085  mov     qword ptr [rcx+18h], 0
0x18000208d  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180002094  mov     rax, rcx
0x180002097  retn
```
