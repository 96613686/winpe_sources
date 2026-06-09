# ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)

- ea: `0x18000a404`
- end: `0x18000a424`
- name: `??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aee0`
- `0x18000afc0`
- `0x18000b0a0`
- `0x18000b180`
- `0x18000b260`
- `0x18000b350`
- `0x18000b430`
- `0x18000b540`
- `0x18000b630`
- `0x18000b710`
- `0x18000b7f0`

## callees

- `0x18000a3d4`

## pseudocode

```c
__int64 __fastcall ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 result; // rax

  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>();
  result = a1;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18000a404  push    rbx
0x18000a406  sub     rsp, 20h
0x18000a40a  mov     rbx, rcx
0x18000a40d  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18000a412  mov     rax, rbx
0x18000a415  mov     qword ptr [rbx+10h], 0
0x18000a41d  add     rsp, 20h
0x18000a421  pop     rbx
0x18000a422  retn
```
