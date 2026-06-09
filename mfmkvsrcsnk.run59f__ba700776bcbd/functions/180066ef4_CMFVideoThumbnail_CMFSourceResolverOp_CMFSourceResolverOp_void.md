# CMFVideoThumbnail::CMFSourceResolverOp::~CMFSourceResolverOp(void)

- ea: `0x180066ef4`
- end: `0x180066f7f`
- name: `??1CMFSourceResolverOp@CMFVideoThumbnail@@UEAA@XZ`
- size: `139`
- prototype: `void __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067050`

## callees

- `0x1800516a4`
- `0x180054a9c`
- `0x180066ef4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066f55`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f14`

## pseudocode

```c
void __fastcall CMFVideoThumbnail::CMFSourceResolverOp::~CMFSourceResolverOp(
        CMFVideoThumbnail::CMFSourceResolverOp *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CMFVideoThumbnail::CMFSourceResolverOp::`vftable';
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CloseHandle(v2);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 96LL))(v3);
    if ( *((_QWORD *)this + 3) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 3, 0);
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 24);
  *(_QWORD *)this = &CBaseUnknown::`vftable';
}

```

## disassembly

```asm
0x180066ef4  mov     [rsp+arg_0], rbx
0x180066ef9  push    rdi
0x180066efa  sub     rsp, 20h
0x180066efe  lea     rax, ??_7CMFSourceResolverOp@CMFVideoThumbnail@@6B@; const CMFVideoThumbnail::CMFSourceResolverOp::`vftable'
0x180066f05  mov     rbx, rcx
0x180066f08  mov     [rcx], rax
0x180066f0b  mov     rcx, [rcx+20h]; hObject
0x180066f0f  test    rcx, rcx
0x180066f12  jz      short loc_180066F20
0x180066f14  call    cs:__imp_CloseHandle
0x180066f1b  nop     dword ptr [rax+rax+00h]
0x180066f20  lea     rdi, [rbx+18h]
0x180066f24  mov     rcx, [rdi]
0x180066f27  test    rcx, rcx
0x180066f2a  jz      short loc_180066F48
0x180066f2c  mov     rax, [rcx]
0x180066f2f  mov     rax, [rax+60h]
0x180066f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f38  cmp     qword ptr [rdi], 0
0x180066f3c  jz      short loc_180066F48
0x180066f3e  xor     edx, edx; struct IUnknown *
0x180066f40  mov     rcx, rdi; struct IUnknown **
0x180066f43  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180066f48  lea     rcx, [rbx+58h]
0x180066f4c  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180066f51  lea     rcx, [rbx+30h]; lpCriticalSection
0x180066f55  call    cs:__imp_DeleteCriticalSection
0x180066f5c  nop     dword ptr [rax+rax+00h]
0x180066f61  mov     rcx, rdi
0x180066f64  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180066f69  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180066f70  mov     [rbx], rax
0x180066f73  mov     rbx, [rsp+28h+arg_0]
0x180066f78  add     rsp, 20h
0x180066f7c  pop     rdi
0x180066f7d  retn
```
