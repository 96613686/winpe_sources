# ATL::CComPtr<IEapHostPeerSessionApis>::~CComPtr<IEapHostPeerSessionApis>(void)

- ea: `0x180002e24`
- end: `0x180002e43`
- name: `??1?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e068`
- `0x18000e0d6`
- `0x18000e137`
- `0x18000e1b9`
- `0x18000e22e`
- `0x18000e2e9`

## callees

- `0x180002e24`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IEapHostPeerSessionApis>::~CComPtr<IEapHostPeerSessionApis>(__int64 *a1)
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
0x180002e24  sub     rsp, 28h
0x180002e28  mov     rcx, [rcx]
0x180002e2b  test    rcx, rcx
0x180002e2e  jz      short loc_180002E3D
0x180002e30  mov     rax, [rcx]
0x180002e33  mov     rax, [rax+10h]
0x180002e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3c  nop
0x180002e3d  add     rsp, 28h
0x180002e41  retn
```
