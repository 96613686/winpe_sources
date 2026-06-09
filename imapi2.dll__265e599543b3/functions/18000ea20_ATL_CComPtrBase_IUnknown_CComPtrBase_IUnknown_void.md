# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000ea20`
- end: `0x18000ea3d`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e9e4`
- `0x18000fc4c`
- `0x180016a30`
- `0x180016a84`
- `0x180016c5c`
- `0x1800170ec`
- `0x18001724c`
- `0x1800174d0`
- `0x1800175ec`
- `0x1800185a0`
- `0x18001b910`
- `0x18001c030`
- `0x18001c340`
- `0x18001c42c`
- `0x180024770`
- `0x180024930`
- `0x1800251a0`
- `0x180028310`
- `0x18002e020`
- `0x180032900`
- `0x180037b30`
- `0x18003c23c`
- `0x18003c280`
- `0x18003c3d0`
- `0x18003c7f0`
- `0x18003cf30`
- `0x18003d884`
- `0x180040890`
- `0x180041a34`
- `0x180041d78`
- `0x180041f0c`

## callees

- `0x18000ea20`
- `0x18004a010`

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
0x18000ea20  sub     rsp, 28h
0x18000ea24  mov     rcx, [rcx]
0x18000ea27  test    rcx, rcx
0x18000ea2a  jz      short loc_18000EA38
0x18000ea2c  mov     rax, [rcx]
0x18000ea2f  mov     rax, [rax+10h]
0x18000ea33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea38  add     rsp, 28h
0x18000ea3c  retn
```
