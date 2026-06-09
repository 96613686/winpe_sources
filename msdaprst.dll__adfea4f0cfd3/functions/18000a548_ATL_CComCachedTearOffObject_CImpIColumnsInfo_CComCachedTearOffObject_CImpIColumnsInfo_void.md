# ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(void)

- ea: `0x18000a548`
- end: `0x18000a564`
- name: `??1?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a968`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a55d`

## pseudocode

```c
__int64 __fastcall ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable';
  return MPDeleteCriticalSection(a1 + 40);
}

```

## disassembly

```asm
0x18000a548  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable'
0x18000a54f  mov     dword ptr [rcx+8], 1
0x18000a556  mov     [rcx], rax
0x18000a559  add     rcx, 28h ; '('
0x18000a55d  jmp     cs:__imp_MPDeleteCriticalSection
```
