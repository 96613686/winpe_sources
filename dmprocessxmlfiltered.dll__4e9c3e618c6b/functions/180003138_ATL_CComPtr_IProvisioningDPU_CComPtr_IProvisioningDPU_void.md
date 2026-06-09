# ATL::CComPtr<IProvisioningDPU>::~CComPtr<IProvisioningDPU>(void)

- ea: `0x180003138`
- end: `0x180003156`
- name: `??1?$CComPtr@UIProvisioningDPU@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007052`

## callees

- `0x180003138`
- `0x180008010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IProvisioningDPU>::~CComPtr<IProvisioningDPU>(__int64 *a1)
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
0x180003138  sub     rsp, 28h
0x18000313c  mov     rcx, [rcx]
0x18000313f  test    rcx, rcx
0x180003142  jz      short loc_180003151
0x180003144  mov     rax, [rcx]
0x180003147  mov     rax, [rax+10h]
0x18000314b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003150  nop
0x180003151  add     rsp, 28h
0x180003155  retn
```
