# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x1800030d8`
- end: `0x1800030f6`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003198`
- `0x18000561c`
- `0x1800084d0`
- `0x18000a22c`
- `0x18000db7c`
- `0x18000ea78`
- `0x1800104f8`
- `0x1800168e0`
- `0x18001e84a`
- `0x18001eb32`
- `0x18001f100`
- `0x18001f775`
- `0x1800203a6`
- `0x1800203bc`
- `0x1800203ce`
- `0x1800203e0`
- `0x180020db4`
- `0x180020e66`

## callees

- `0x1800030d8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(__int64 *a1)
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
0x1800030d8  sub     rsp, 28h
0x1800030dc  mov     rcx, [rcx]
0x1800030df  test    rcx, rcx
0x1800030e2  jz      short loc_1800030F1
0x1800030e4  mov     rax, [rcx]
0x1800030e7  mov     rax, [rax+10h]
0x1800030eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f0  nop
0x1800030f1  add     rsp, 28h
0x1800030f5  retn
```
