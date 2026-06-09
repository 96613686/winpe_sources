# ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>(void)

- ea: `0x180002374`
- end: `0x180002392`
- name: `??1?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ec2`
- `0x180009f02`
- `0x180009f98`

## callees

- `0x180002374`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>(__int64 *a1)
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
0x180002374  sub     rsp, 28h
0x180002378  mov     rcx, [rcx]
0x18000237b  test    rcx, rcx
0x18000237e  jz      short loc_18000238D
0x180002380  mov     rax, [rcx]
0x180002383  mov     rax, [rax+10h]
0x180002387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000238c  nop
0x18000238d  add     rsp, 28h
0x180002391  retn
```
