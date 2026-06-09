# CMFVideoThumbnail::CMFSourceResolverOp::~CMFSourceResolverOp(void)

- ea: `0x1800643c0`
- end: `0x18006443e`
- name: `??1CMFSourceResolverOp@CMFVideoThumbnail@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064500`

## callees

- `0x18004f47c`
- `0x180052754`
- `0x1800643c0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006441b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006441b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800643e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800643e0`

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
0x1800643c0  mov     [rsp+arg_0], rbx
0x1800643c5  push    rdi
0x1800643c6  sub     rsp, 20h
0x1800643ca  lea     rax, ??_7CMFSourceResolverOp@CMFVideoThumbnail@@6B@; const CMFVideoThumbnail::CMFSourceResolverOp::`vftable'
0x1800643d1  mov     rbx, rcx
0x1800643d4  mov     [rcx], rax
0x1800643d7  mov     rcx, [rcx+20h]; hObject
0x1800643db  test    rcx, rcx
0x1800643de  jz      short loc_1800643E6
0x1800643e0  call    cs:__imp_CloseHandle
0x1800643e6  lea     rdi, [rbx+18h]
0x1800643ea  mov     rcx, [rdi]
0x1800643ed  test    rcx, rcx
0x1800643f0  jz      short loc_18006440E
0x1800643f2  mov     rax, [rcx]
0x1800643f5  mov     rax, [rax+60h]
0x1800643f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643fe  cmp     qword ptr [rdi], 0
0x180064402  jz      short loc_18006440E
0x180064404  xor     edx, edx; struct IUnknown *
0x180064406  mov     rcx, rdi; struct IUnknown **
0x180064409  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18006440e  lea     rcx, [rbx+58h]
0x180064412  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180064417  lea     rcx, [rbx+30h]; lpCriticalSection
0x18006441b  call    cs:__imp_DeleteCriticalSection
0x180064421  mov     rcx, rdi
0x180064424  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180064429  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180064430  mov     [rbx], rax
0x180064433  mov     rbx, [rsp+28h+arg_0]
0x180064438  add     rsp, 20h
0x18006443c  pop     rdi
0x18006443d  retn
```
