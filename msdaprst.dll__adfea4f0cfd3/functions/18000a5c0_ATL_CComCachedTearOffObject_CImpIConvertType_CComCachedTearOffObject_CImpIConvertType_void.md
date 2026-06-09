# ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(void)

- ea: `0x18000a5c0`
- end: `0x18000a5dc`
- name: `??1?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a9e0`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a5d5`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIConvertType>::~CComCachedTearOffObject<CImpIConvertType>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a5c0  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable'
0x18000a5c7  mov     dword ptr [rcx+8], 1
0x18000a5ce  mov     [rcx], rax
0x18000a5d1  add     rcx, 28h ; '('
0x18000a5d5  jmp     cs:__imp_MPDeleteCriticalSection
```
