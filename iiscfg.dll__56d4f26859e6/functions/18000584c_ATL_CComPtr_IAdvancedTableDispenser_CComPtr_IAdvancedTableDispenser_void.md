# ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)

- ea: `0x18000584c`
- end: `0x18000586a`
- name: `??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000593c`
- `0x18000ce00`
- `0x18000d110`
- `0x18001565c`
- `0x18002e873`
- `0x18002e8cd`
- `0x18002ecff`

## callees

- `0x18000584c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(__int64 *a1)
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
0x18000584c  sub     rsp, 28h
0x180005850  mov     rcx, [rcx]
0x180005853  test    rcx, rcx
0x180005856  jz      short loc_180005865
0x180005858  mov     rax, [rcx]
0x18000585b  mov     rax, [rax+10h]
0x18000585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005864  nop
0x180005865  add     rsp, 28h
0x180005869  retn
```
