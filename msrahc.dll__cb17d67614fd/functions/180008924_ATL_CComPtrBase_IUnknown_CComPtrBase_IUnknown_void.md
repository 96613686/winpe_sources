# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180008924`
- end: `0x180008942`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800099a8`
- `0x180009cec`
- `0x180009ea0`
- `0x18000f520`
- `0x180010184`
- `0x180011b8c`
- `0x18001317c`
- `0x18001369c`
- `0x180015510`
- `0x180015f1c`

## callees

- `0x180008924`
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
0x180008924  sub     rsp, 28h
0x180008928  mov     rcx, [rcx]
0x18000892b  test    rcx, rcx
0x18000892e  jz      short loc_18000893D
0x180008930  mov     rax, [rcx]
0x180008933  mov     rax, [rax+10h]
0x180008937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893c  nop
0x18000893d  add     rsp, 28h
0x180008941  retn
```
