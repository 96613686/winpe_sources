# ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(void)

- ea: `0x18000a4f8`
- end: `0x18000a514`
- name: `??1?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a918`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a50d`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIAccessor>::~CComCachedTearOffObject<CImpIAccessor>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a4f8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable'
0x18000a4ff  mov     dword ptr [rcx+8], 1
0x18000a506  mov     [rcx], rax
0x18000a509  add     rcx, 28h ; '('
0x18000a50d  jmp     cs:__imp_MPDeleteCriticalSection
```
