# CThisDllClassFactory::CThisDllClassFactory(_GUID const &)

- ea: `0x180011dd4`
- end: `0x180011df8`
- name: `??0CThisDllClassFactory@@QEAA@AEBU_GUID@@@Z`
- size: `36`
- prototype: `CThisDllClassFactory *__fastcall(CThisDllClassFactory *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180012150`

## pseudocode

```c
CThisDllClassFactory *__fastcall CThisDllClassFactory::CThisDllClassFactory(
        CThisDllClassFactory *this,
        const struct _GUID *a2)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CThisDllClassFactory::`vftable';
  *(struct _GUID *)((char *)this + 12) = *a2;
  _InterlockedIncrement(&g_cRefThisDll);
  return this;
}

```

## disassembly

```asm
0x180011dd4  lea     rax, ??_7CThisDllClassFactory@@6B@; const CThisDllClassFactory::`vftable'
0x180011ddb  mov     dword ptr [rcx+8], 1
0x180011de2  mov     [rcx], rax
0x180011de5  movups  xmm0, xmmword ptr [rdx]
0x180011de8  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x180011ded  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180011df4  mov     rax, rcx
0x180011df7  retn
```
