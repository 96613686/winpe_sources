# ATL::CComAggregateCreator<SplPipeline::SplFilterPipelineCallObject,&_GUID const CLSID_ManualResetEvent>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140010b00`
- end: `0x140010b49`
- name: `?CreateInstance@?$CComAggregateCreator@VSplFilterPipelineCallObject@SplPipeline@@$1?CLSID_ManualResetEvent@@3U_GUID@@B@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140010b00`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010b3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010b3d`

## pseudocode

```c
HRESULT __fastcall ATL::CComAggregateCreator<SplPipeline::SplFilterPipelineCallObject,&_GUID const CLSID_ManualResetEvent>::CreateInstance(
        __int64 a1,
        __int64 a2,
        LPVOID *a3)
{
  IUnknown *v5; // rax

  if ( !a1 )
    return -2147024809;
  v5 = (IUnknown *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  return CoCreateInstance(&CLSID_ManualResetEvent, v5, 3u, &GUID_00000000_0000_0000_c000_000000000046, a3);
}

```

## disassembly

```asm
0x140010b00  push    rbx
0x140010b02  sub     rsp, 30h
0x140010b06  mov     rbx, r8
0x140010b09  test    rcx, rcx
0x140010b0c  jnz     short loc_140010B15
0x140010b0e  mov     eax, 80070057h
0x140010b13  jmp     short loc_140010B43
0x140010b15  mov     rax, [rcx]
0x140010b18  mov     rax, [rax+28h]
0x140010b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b21  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140010b28  mov     [rsp+38h+ppv], rbx; ppv
0x140010b2d  mov     r8d, 3; dwClsContext
0x140010b33  lea     rcx, CLSID_ManualResetEvent; rclsid
0x140010b3a  mov     rdx, rax; pUnkOuter
0x140010b3d  call    cs:__imp_CoCreateInstance
0x140010b43  add     rsp, 30h
0x140010b47  pop     rbx
0x140010b48  retn
```
