# CCollection<IHCCommandCollection,CCommand>::~CCollection<IHCCommandCollection,CCommand>(void)

- ea: `0x180004894`
- end: `0x1800048ae`
- name: `??1?$CCollection@UIHCCommandCollection@@VCCommand@@@@MEAA@XZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800047e0`

## callees

- `0x1800048b4`

## pseudocode

```c
void __fastcall CCollection<IHCCommandCollection,CCommand>::~CCollection<IHCCommandCollection,CCommand>(__int64 a1)
{
  *(_QWORD *)a1 = &CCollection<IHCCommandCollection,CCommand>::`vftable';
  _InterlockedDecrement(&g_cLocks);
  CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::~CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>((HDPA *)(a1 + 16));
}

```

## disassembly

```asm
0x180004894  lea     rax, ??_7?$CCollection@UIHCCommandCollection@@VCCommand@@@@6B@; const CCollection<IHCCommandCollection,CCommand>::`vftable'
0x18000489b  mov     [rcx], rax
0x18000489e  add     rcx, 10h
0x1800048a2  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x1800048a9  jmp     ??1?$CDPA_Base@VCCommand@@V?$CTContainer_PolicyRelease@VCCommand@@@@@@QEAA@XZ; CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::~CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>(void)
```
