# TComObject<NOutermost::CDevice>::CFinalReleaseSentinel::~CFinalReleaseSentinel(void)

- ea: `0x18000aa98`
- end: `0x18000aaca`
- name: `??1CFinalReleaseSentinel@?$TComObject@VCDevice@NOutermost@@@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013ced`

## callees

- `0x180002950`
- `0x1800029b0`
- `0x18000aa98`

## pseudocode

```c
void __fastcall TComObject<NOutermost::CDevice>::CFinalReleaseSentinel::~CFinalReleaseSentinel(
        NOutermost::CDevice **a1)
{
  NOutermost::CDevice *v1; // rbx
  NOutermost::CDevice *v2; // rcx
  struct IUnknown *v3; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = *a1;
    *((_DWORD *)v1 + 2) = -1073741823;
    NOutermost::CDevice::LLOBeginLayerDestruction(v2);
    if ( *((_QWORD *)v1 + 12) )
      ATL::AtlComPtrAssign((struct IUnknown **)v1 + 12, v3);
  }
}

```

## disassembly

```asm
0x18000aa98  push    rbx
0x18000aa9a  sub     rsp, 20h
0x18000aa9e  mov     rbx, [rcx]
0x18000aaa1  test    rbx, rbx
0x18000aaa4  jz      short loc_18000AAC4
0x18000aaa6  mov     rcx, rbx; this
0x18000aaa9  mov     dword ptr [rbx+8], 0C0000001h
0x18000aab0  call    ?LLOBeginLayerDestruction@CDevice@NOutermost@@UEAAXXZ; NOutermost::CDevice::LLOBeginLayerDestruction(void)
0x18000aab5  lea     rcx, [rbx+60h]; struct IUnknown **
0x18000aab9  cmp     qword ptr [rcx], 0
0x18000aabd  jz      short loc_18000AAC4
0x18000aabf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000aac4  add     rsp, 20h
0x18000aac8  pop     rbx
0x18000aac9  retn
```
