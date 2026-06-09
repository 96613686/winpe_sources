# CMFVideoThumbnail::CMFSourceResolverOp::~CMFSourceResolverOp(void)

- ea: `0x180048a9c`
- end: `0x180048b1a`
- name: `??1CMFSourceResolverOp@CMFVideoThumbnail@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048c30`

## callees

- `0x180017e64`
- `0x18002a100`
- `0x180048a9c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048af7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048af7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048abc`

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
0x180048a9c  mov     [rsp+arg_0], rbx
0x180048aa1  push    rdi
0x180048aa2  sub     rsp, 20h
0x180048aa6  lea     rax, ??_7CMFSourceResolverOp@CMFVideoThumbnail@@6B@; const CMFVideoThumbnail::CMFSourceResolverOp::`vftable'
0x180048aad  mov     rbx, rcx
0x180048ab0  mov     [rcx], rax
0x180048ab3  mov     rcx, [rcx+20h]; hObject
0x180048ab7  test    rcx, rcx
0x180048aba  jz      short loc_180048AC2
0x180048abc  call    cs:__imp_CloseHandle
0x180048ac2  lea     rdi, [rbx+18h]
0x180048ac6  mov     rcx, [rdi]
0x180048ac9  test    rcx, rcx
0x180048acc  jz      short loc_180048AEA
0x180048ace  mov     rax, [rcx]
0x180048ad1  mov     rax, [rax+60h]
0x180048ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ada  cmp     qword ptr [rdi], 0
0x180048ade  jz      short loc_180048AEA
0x180048ae0  xor     edx, edx; struct IUnknown *
0x180048ae2  mov     rcx, rdi; struct IUnknown **
0x180048ae5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180048aea  lea     rcx, [rbx+58h]
0x180048aee  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180048af3  lea     rcx, [rbx+30h]; lpCriticalSection
0x180048af7  call    cs:__imp_DeleteCriticalSection
0x180048afd  mov     rcx, rdi
0x180048b00  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180048b05  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180048b0c  mov     [rbx], rax
0x180048b0f  mov     rbx, [rsp+28h+arg_0]
0x180048b14  add     rsp, 20h
0x180048b18  pop     rdi
0x180048b19  retn
```
