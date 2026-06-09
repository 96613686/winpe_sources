# ATL::CComPtr<IWICImagingFactory>::~CComPtr<IWICImagingFactory>(void)

- ea: `0x180003864`
- end: `0x180003882`
- name: `??1?$CComPtr@UIWICImagingFactory@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a499`
- `0x18000a4ab`
- `0x18000a4bd`
- `0x18000a4cf`
- `0x18000a4e1`
- `0x18000a54d`
- `0x18000a55f`
- `0x18000a571`

## callees

- `0x180003864`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IWICImagingFactory>::~CComPtr<IWICImagingFactory>(__int64 *a1)
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
0x180003864  sub     rsp, 28h
0x180003868  mov     rcx, [rcx]
0x18000386b  test    rcx, rcx
0x18000386e  jz      short loc_18000387D
0x180003870  mov     rax, [rcx]
0x180003873  mov     rax, [rax+10h]
0x180003877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000387c  nop
0x18000387d  add     rsp, 28h
0x180003881  retn
```
