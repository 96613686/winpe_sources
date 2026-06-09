# ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)

- ea: `0x180001f70`
- end: `0x180001f8d`
- name: `??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f94`
- `0x180002bf0`
- `0x180002ca0`
- `0x180002d6c`
- `0x1800031d0`
- `0x180003370`
- `0x180003918`
- `0x180003e04`
- `0x180003ed0`
- `0x180004658`
- `0x18000593c`
- `0x1800114c0`
- `0x180012734`
- `0x180012988`
- `0x180013fa0`
- `0x180014200`
- `0x1800147c0`
- `0x18001565c`
- `0x18002ed18`
- `0x18002ed31`
- `0x18002ed4a`
- `0x18002ed63`

## callees

- `0x180001f70`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(__int64 *a1)
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
0x180001f70  sub     rsp, 28h
0x180001f74  mov     rcx, [rcx]
0x180001f77  test    rcx, rcx
0x180001f7a  jz      short loc_180001F88
0x180001f7c  mov     rax, [rcx]
0x180001f7f  mov     rax, [rax+10h]
0x180001f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f88  add     rsp, 28h
0x180001f8c  retn
```
