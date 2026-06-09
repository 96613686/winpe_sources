# CCheckProviderBase::CCheckProviderBase(void)

- ea: `0x1800094e0`
- end: `0x18000950c`
- name: `??0CCheckProviderBase@@IEAA@XZ`
- size: `44`
- prototype: `CCheckProviderBase *__fastcall(CCheckProviderBase *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800063f0`
- `0x18000896c`

## pseudocode

```c
CCheckProviderBase *__fastcall CCheckProviderBase::CCheckProviderBase(CCheckProviderBase *this)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CCheckProviderBase::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  _InterlockedIncrement(&g_cLocks);
  return this;
}

```

## disassembly

```asm
0x1800094e0  lea     rax, ??_7CCheckProviderBase@@6B@; const CCheckProviderBase::`vftable'
0x1800094e7  mov     dword ptr [rcx+8], 1
0x1800094ee  mov     [rcx], rax
0x1800094f1  mov     qword ptr [rcx+10h], 0
0x1800094f9  mov     qword ptr [rcx+18h], 0
0x180009501  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180009508  mov     rax, rcx
0x18000950b  retn
```
