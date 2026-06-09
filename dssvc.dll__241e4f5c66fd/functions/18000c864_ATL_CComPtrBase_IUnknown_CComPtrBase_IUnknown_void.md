# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000c864`
- end: `0x18000c881`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d860`
- `0x18000e2b0`
- `0x180013394`
- `0x180013400`
- `0x18001b980`

## callees

- `0x18000c864`
- `0x18001c010`

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
0x18000c864  sub     rsp, 28h
0x18000c868  mov     rcx, [rcx]
0x18000c86b  test    rcx, rcx
0x18000c86e  jz      short loc_18000C87C
0x18000c870  mov     rax, [rcx]
0x18000c873  mov     rax, [rax+10h]
0x18000c877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c87c  add     rsp, 28h
0x18000c880  retn
```
