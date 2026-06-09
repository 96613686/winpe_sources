# TComObject<NOutermost::CDevice>::~TComObject<NOutermost::CDevice>(void)

- ea: `0x18000290c`
- end: `0x180002949`
- name: `??1?$TComObject@VCDevice@NOutermost@@@@UEAA@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800028d0`

## callees

- `0x18000290c`
- `0x180002950`
- `0x180002988`
- `0x1800029b0`

## pseudocode

```c
__int64 __fastcall TComObject<NOutermost::CDevice>::~TComObject<NOutermost::CDevice>(__int64 a1)
{
  struct IUnknown *v2; // rdx

  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &TComObject<NOutermost::CDevice>::`vftable';
  NOutermost::CDevice::LLOBeginLayerDestruction((NOutermost::CDevice *)a1);
  if ( *(_QWORD *)(a1 + 96) )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 96), v2);
  return ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>((__int64 *)(a1 + 96));
}

```

## disassembly

```asm
0x18000290c  push    rbx
0x18000290e  sub     rsp, 20h
0x180002912  lea     rax, ??_7?$TComObject@VCDevice@NOutermost@@@@6B@; const TComObject<NOutermost::CDevice>::`vftable'
0x180002919  mov     dword ptr [rcx+8], 0C0000001h
0x180002920  mov     [rcx], rax
0x180002923  mov     rbx, rcx
0x180002926  call    ?LLOBeginLayerDestruction@CDevice@NOutermost@@UEAAXXZ; NOutermost::CDevice::LLOBeginLayerDestruction(void)
0x18000292b  cmp     qword ptr [rbx+60h], 0
0x180002930  jz      short loc_18000293B
0x180002932  lea     rcx, [rbx+60h]; struct IUnknown **
0x180002936  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000293b  lea     rcx, [rbx+60h]
0x18000293f  add     rsp, 20h
0x180002943  pop     rbx
0x180002944  jmp     ??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)
```
