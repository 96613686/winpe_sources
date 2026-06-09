# ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(void)

- ea: `0x18000a520`
- end: `0x18000a53c`
- name: `??1?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a940`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a535`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIChapteredRowset>::~CComCachedTearOffObject<CImpIChapteredRowset>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a520  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable'
0x18000a527  mov     dword ptr [rcx+8], 1
0x18000a52e  mov     [rcx], rax
0x18000a531  add     rcx, 28h ; '('
0x18000a535  jmp     cs:__imp_MPDeleteCriticalSection
```
