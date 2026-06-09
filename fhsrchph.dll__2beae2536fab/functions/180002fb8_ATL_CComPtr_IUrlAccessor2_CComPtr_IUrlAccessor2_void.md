# ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>(void)

- ea: `0x180002fb8`
- end: `0x180002fd6`
- name: `??1?$CComPtr@UIUrlAccessor2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b042`
- `0x18000b32a`
- `0x18000b33c`
- `0x18000b352`
- `0x18000b368`
- `0x18000b394`
- `0x18000b3a6`
- `0x18000b453`
- `0x18000b49b`

## callees

- `0x180002fb8`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>(__int64 *a1)
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
0x180002fb8  sub     rsp, 28h
0x180002fbc  mov     rcx, [rcx]
0x180002fbf  test    rcx, rcx
0x180002fc2  jz      short loc_180002FD1
0x180002fc4  mov     rax, [rcx]
0x180002fc7  mov     rax, [rax+10h]
0x180002fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd0  nop
0x180002fd1  add     rsp, 28h
0x180002fd5  retn
```
