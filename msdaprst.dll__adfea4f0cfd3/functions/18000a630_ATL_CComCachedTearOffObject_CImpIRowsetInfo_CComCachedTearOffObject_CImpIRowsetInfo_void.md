# ATL::CComCachedTearOffObject<CImpIRowsetInfo>::~CComCachedTearOffObject<CImpIRowsetInfo>(void)

- ea: `0x18000a630`
- end: `0x18000a64c`
- name: `??1?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000aa58`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a645`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIRowsetInfo>::~CComCachedTearOffObject<CImpIRowsetInfo>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a630  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable'
0x18000a637  mov     dword ptr [rcx+8], 1
0x18000a63e  mov     [rcx], rax
0x18000a641  add     rcx, 28h ; '('
0x18000a645  jmp     cs:__imp_MPDeleteCriticalSection
```
