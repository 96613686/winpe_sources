# CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CreateInstance(NOutermost::CDeviceChild::TConstructorArgs const &,NOutermost::CDevice *,void *,void *,_GUID const &,void * *)

- ea: `0x18000195c`
- end: `0x180001a4f`
- name: `?CreateInstance@?$CDelegatingUseCountedObject@VCDeviceChild@NOutermost@@@@SAXAEBUTConstructorArgs@CDeviceChild@NOutermost@@PEAVCDevice@4@PEAX2AEBU_GUID@@PEAPEAX@Z`
- size: `243`
- prototype: `__int64 __usercall@<rax>(struct NOutermost::CDeviceChild::TConstructorArgs *@<rcx>, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800014c0`

## callees

- `0x18000195c`
- `0x180001da0`
- `0x180001f30`
- `0x1800020b0`
- `0x180008b98`
- `0x18000aa60`
- `0x18000b81c`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CreateInstance(
        struct NOutermost::CDeviceChild::TConstructorArgs *a1,
        __int64 a2,
        NOutermost::CDeviceChild *a3,
        __int64 a4,
        struct _GUID *a5,
        void **a6)
{
  NOutermost::CDeviceChild *v7; // rbx
  int Interface; // eax
  __int64 result; // rax
  void *v12; // [rsp+58h] [rbp+10h] BYREF
  NOutermost::CDeviceChild *v13; // [rsp+60h] [rbp+18h] BYREF
  NOutermost::CDeviceChild *v14; // [rsp+68h] [rbp+20h]

  v7 = a3;
  v13 = 0;
  if ( !a3 )
  {
    v12 = operator new[](0x20u);
    std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&v13, &v12);
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v12);
    v7 = v13;
  }
  v14 = v7;
  *((_QWORD *)v7 + 2) = a2;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *(_QWORD *)v7 = &CDelegatingUseCountedObject<NOutermost::CDeviceChild>::`vftable';
  *((_QWORD *)v7 + 1) = a4;
  NOutermost::CDeviceChild::FinalConstruct(v7, a1);
  Interface = ATL::AtlInternalQueryInterface(
                v7,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`NOutermost::CDeviceChild::_GetEntries'::`2'::_entries,
                a5,
                a6);
  ThrowFailure(Interface);
  v12 = 0;
  result = (***((__int64 (__fastcall ****)(_QWORD, GUID *, void **))v7 + 1))(
             *((_QWORD *)v7 + 1),
             &GUID_e667af9f_cd56_4f46_83ce_032e595d70a8,
             &v12);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(void *, NOutermost::CDeviceChild *))(*(_QWORD *)v12 + 64LL))(v12, v7);
  return result;
}

```

## disassembly

```asm
0x18000195c  mov     [rsp+arg_0], rbx
0x180001961  push    rbp
0x180001962  push    rsi
0x180001963  push    rdi
0x180001964  sub     rsp, 30h
0x180001968  mov     rdi, r9
0x18000196b  mov     rbx, r8
0x18000196e  mov     rsi, rdx
0x180001971  mov     rbp, rcx
0x180001974  mov     [rsp+48h+arg_10], 0
0x18000197d  test    r8, r8
0x180001980  jnz     short loc_1800019AE
0x180001982  lea     ecx, [r8+20h]; unsigned __int64
0x180001986  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000198b  mov     [rsp+48h+arg_8], rax
0x180001990  lea     rdx, [rsp+48h+arg_8]
0x180001995  lea     rcx, [rsp+48h+arg_10]
0x18000199a  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x18000199f  lea     rcx, [rsp+48h+arg_8]
0x1800019a4  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800019a9  mov     rbx, [rsp+48h+arg_10]
0x1800019ae  mov     [rsp+48h+arg_18], rbx
0x1800019b3  mov     [rbx+10h], rsi
0x1800019b7  mov     qword ptr [rbx+8], 0
0x1800019bf  mov     qword ptr [rbx+18h], 0
0x1800019c7  lea     rax, ??_7?$CDelegatingUseCountedObject@VCDeviceChild@NOutermost@@@@6B@; const CDelegatingUseCountedObject<NOutermost::CDeviceChild>::`vftable'
0x1800019ce  mov     [rbx], rax
0x1800019d1  mov     [rbx+8], rdi
0x1800019d5  mov     [rsp+48h+var_28], rbx
0x1800019da  mov     rdx, rbp; struct NOutermost::CDeviceChild::TConstructorArgs *
0x1800019dd  mov     rcx, rbx; this
0x1800019e0  call    ?FinalConstruct@CDeviceChild@NOutermost@@QEAAXAEBUTConstructorArgs@12@@Z; NOutermost::CDeviceChild::FinalConstruct(NOutermost::CDeviceChild::TConstructorArgs const &)
0x1800019e5  mov     r9, [rsp+48h+arg_28]; void **
0x1800019ea  mov     r8, [rsp+48h+arg_20]; struct _GUID *
0x1800019ef  lea     rdx, ?_entries@?1??_GetEntries@CDeviceChild@NOutermost@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU45@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800019f6  mov     rcx, rbx; void *
0x1800019f9  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800019fe  mov     ecx, eax; int
0x180001a00  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180001a05  mov     [rsp+48h+arg_8], 0
0x180001a0e  mov     rcx, [rbx+8]
0x180001a12  mov     rax, [rcx]
0x180001a15  lea     r8, [rsp+48h+arg_8]
0x180001a1a  lea     rdx, _GUID_e667af9f_cd56_4f46_83ce_032e595d70a8
0x180001a21  mov     rax, [rax]
0x180001a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a29  test    eax, eax
0x180001a2b  js      short loc_180001A42
0x180001a2d  mov     rcx, [rsp+48h+arg_8]
0x180001a32  mov     rax, [rcx]
0x180001a35  mov     rdx, rbx
0x180001a38  mov     rax, [rax+40h]
0x180001a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a41  nop
0x180001a42  mov     rbx, [rsp+48h+arg_0]
0x180001a47  add     rsp, 30h
0x180001a4b  pop     rdi
0x180001a4c  pop     rsi
0x180001a4d  pop     rbp
0x180001a4e  retn
```
