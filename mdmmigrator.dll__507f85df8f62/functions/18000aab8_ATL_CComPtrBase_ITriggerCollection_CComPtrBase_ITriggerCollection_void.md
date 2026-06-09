# ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)

- ea: `0x18000aab8`
- end: `0x18000aad6`
- name: `??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012664`
- `0x180012ed4`
- `0x180016b88`
- `0x180016ca8`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001b094`

## callees

- `0x18000aab8`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(__int64 *a1)
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
0x18000aab8  sub     rsp, 28h
0x18000aabc  mov     rcx, [rcx]
0x18000aabf  test    rcx, rcx
0x18000aac2  jz      short loc_18000AAD1
0x18000aac4  mov     rax, [rcx]
0x18000aac7  mov     rax, [rax+10h]
0x18000aacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aad0  nop
0x18000aad1  add     rsp, 28h
0x18000aad5  retn
```
