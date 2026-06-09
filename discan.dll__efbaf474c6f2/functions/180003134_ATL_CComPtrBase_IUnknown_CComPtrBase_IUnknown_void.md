# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180003134`
- end: `0x180003152`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003128`
- `0x180003aa0`
- `0x18000502c`
- `0x180005d20`
- `0x180006d40`
- `0x180007078`
- `0x1800213b8`
- `0x180021450`
- `0x180021730`
- `0x180021aac`
- `0x180022450`
- `0x180024280`
- `0x1800277e0`
- `0x180027b88`
- `0x180028360`
- `0x18002a2e0`

## callees

- `0x180003134`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x180003134  sub     rsp, 28h
0x180003138  mov     rcx, [rcx]
0x18000313b  test    rcx, rcx
0x18000313e  jz      short loc_18000314D
0x180003140  mov     rax, [rcx]
0x180003143  mov     rax, [rax+10h]
0x180003147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314c  nop
0x18000314d  add     rsp, 28h
0x180003151  retn
```
