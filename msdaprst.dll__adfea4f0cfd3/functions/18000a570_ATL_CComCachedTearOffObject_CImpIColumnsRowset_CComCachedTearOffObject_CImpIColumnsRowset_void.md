# ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>(void)

- ea: `0x18000a570`
- end: `0x18000a58c`
- name: `??1?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a990`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a585`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a570  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable'
0x18000a577  mov     dword ptr [rcx+8], 1
0x18000a57e  mov     [rcx], rax
0x18000a581  add     rcx, 28h ; '('
0x18000a585  jmp     cs:__imp_MPDeleteCriticalSection
```
