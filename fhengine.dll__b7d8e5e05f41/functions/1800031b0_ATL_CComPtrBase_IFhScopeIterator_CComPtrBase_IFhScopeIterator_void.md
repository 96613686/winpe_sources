# ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)

- ea: `0x1800031b0`
- end: `0x1800031ce`
- name: `??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003478`
- `0x1800034ec`
- `0x180006b44`
- `0x1800079c0`
- `0x180007a90`
- `0x180007ab8`
- `0x180007ae4`
- `0x180007b3c`
- `0x18000a4ac`
- `0x18000a818`
- `0x18000ac60`
- `0x18000d4f4`
- `0x180010b18`
- `0x180010de8`
- `0x180013e14`
- `0x180016da0`
- `0x180017290`
- `0x18001789c`
- `0x180017c68`
- `0x180019dd0`
- `0x18001afe4`
- `0x18001f92c`
- `0x1800228b0`
- `0x180022d20`
- `0x1800244e0`

## callees

- `0x1800031b0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800031b0  sub     rsp, 28h
0x1800031b4  mov     rcx, [rcx]
0x1800031b7  test    rcx, rcx
0x1800031ba  jz      short loc_1800031C9
0x1800031bc  mov     rax, [rcx]
0x1800031bf  mov     rax, [rax+10h]
0x1800031c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c8  nop
0x1800031c9  add     rsp, 28h
0x1800031cd  retn
```
