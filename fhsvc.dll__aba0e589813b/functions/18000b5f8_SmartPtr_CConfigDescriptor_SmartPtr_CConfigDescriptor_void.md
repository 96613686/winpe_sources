# SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)

- ea: `0x18000b5f8`
- end: `0x18000b60e`
- name: `??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`
- `0x18000ac48`
- `0x18000ee74`
- `0x18000efb4`
- `0x18000f14c`
- `0x18000f2c0`
- `0x18000feb4`
- `0x180011c10`

## callees

- `0x180004e50`
- `0x18000b5f8`

## pseudocode

```c
__int64 __fastcall SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v1);
  return result;
}

```

## disassembly

```asm
0x18000b5f8  sub     rsp, 28h
0x18000b5fc  mov     rcx, [rcx]
0x18000b5ff  test    rcx, rcx
0x18000b602  jz      short loc_18000B609
0x18000b604  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000b609  add     rsp, 28h
0x18000b60d  retn
```
