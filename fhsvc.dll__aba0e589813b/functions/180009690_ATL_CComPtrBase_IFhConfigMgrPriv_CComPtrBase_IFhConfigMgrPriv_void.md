# ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(void)

- ea: `0x180009690`
- end: `0x1800096ae`
- name: `??1?$CComPtrBase@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c5d4`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`
- `0x180010848`

## callees

- `0x180009690`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(__int64 *a1)
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
0x180009690  sub     rsp, 28h
0x180009694  mov     rcx, [rcx]
0x180009697  test    rcx, rcx
0x18000969a  jz      short loc_1800096A9
0x18000969c  mov     rax, [rcx]
0x18000969f  mov     rax, [rax+10h]
0x1800096a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a8  nop
0x1800096a9  add     rsp, 28h
0x1800096ad  retn
```
