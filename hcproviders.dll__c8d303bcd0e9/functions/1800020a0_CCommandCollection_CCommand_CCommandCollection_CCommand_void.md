# CCommandCollection<CCommand>::CCommandCollection<CCommand>(void)

- ea: `0x1800020a0`
- end: `0x1800020bc`
- name: `??0?$CCommandCollection@VCCommand@@@@IEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019f0`

## callees

- `0x180004abc`

## pseudocode

```c
_QWORD *CCommandCollection<CCommand>::CCommandCollection<CCommand>()
{
  _QWORD *v0; // rcx
  _QWORD *result; // rax

  CCollection<IHCCommandCollection,CCommand>::CCollection<IHCCommandCollection,CCommand>();
  result = v0;
  *v0 = &CCommandCollection<CCommand>::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800020a0  sub     rsp, 28h
0x1800020a4  call    ??0?$CCollection@UIHCCommandCollection@@VCCommand@@@@IEAA@XZ; CCollection<IHCCommandCollection,CCommand>::CCollection<IHCCommandCollection,CCommand>(void)
0x1800020a9  lea     rdx, ??_7?$CCommandCollection@VCCommand@@@@6B@; const CCommandCollection<CCommand>::`vftable'
0x1800020b0  mov     rax, rcx
0x1800020b3  mov     [rcx], rdx
0x1800020b6  add     rsp, 28h
0x1800020ba  retn
```
