# ATL::CComPtr<IUnknown>::Release(void)

- ea: `0x1800123a4`
- end: `0x1800123cb`
- name: `?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ`
- size: `39`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aa30`
- `0x18000aa70`
- `0x18000aab0`
- `0x18000ab18`
- `0x18000ab58`
- `0x18000ab98`
- `0x18000abd8`
- `0x18000ac18`
- `0x18000ac58`
- `0x18000ac98`
- `0x18000acd8`
- `0x18000ad90`
- `0x18000add8`
- `0x18000ae20`
- `0x18000aed0`
- `0x18000af30`
- `0x18000af78`
- `0x18000afc0`
- `0x18000b008`
- `0x18000b050`
- `0x18000b098`
- `0x18000b0e0`
- `0x180025620`

## callees

- `0x1800123a4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtr<IUnknown>::Release(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800123a4  sub     rsp, 28h
0x1800123a8  mov     rax, rcx
0x1800123ab  mov     rcx, [rcx]
0x1800123ae  test    rcx, rcx
0x1800123b1  jz      short loc_1800123C6
0x1800123b3  mov     qword ptr [rax], 0
0x1800123ba  mov     rax, [rcx]
0x1800123bd  mov     rax, [rax+10h]
0x1800123c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123c6  add     rsp, 28h
0x1800123ca  retn
```
