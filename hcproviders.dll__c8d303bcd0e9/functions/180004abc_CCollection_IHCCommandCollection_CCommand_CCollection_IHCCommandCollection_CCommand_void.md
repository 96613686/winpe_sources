# CCollection<IHCCommandCollection,CCommand>::CCollection<IHCCommandCollection,CCommand>(void)

- ea: `0x180004abc`
- end: `0x180004ae0`
- name: `??0?$CCollection@UIHCCommandCollection@@VCCommand@@@@IEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800020a0`

## pseudocode

```c
__int64 __fastcall CCollection<IHCCommandCollection,CCommand>::CCollection<IHCCommandCollection,CCommand>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &CCollection<IHCCommandCollection,CCommand>::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  _InterlockedIncrement(&g_cLocks);
  return a1;
}

```

## disassembly

```asm
0x180004abc  lea     rax, ??_7?$CCollection@UIHCCommandCollection@@VCCommand@@@@6B@; const CCollection<IHCCommandCollection,CCommand>::`vftable'
0x180004ac3  mov     dword ptr [rcx+8], 1
0x180004aca  mov     [rcx], rax
0x180004acd  mov     qword ptr [rcx+10h], 0
0x180004ad5  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180004adc  mov     rax, rcx
0x180004adf  retn
```
