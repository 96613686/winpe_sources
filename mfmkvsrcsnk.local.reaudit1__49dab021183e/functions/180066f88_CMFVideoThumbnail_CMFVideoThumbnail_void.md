# CMFVideoThumbnail::~CMFVideoThumbnail(void)

- ea: `0x180066f88`
- end: `0x180066fef`
- name: `??1CMFVideoThumbnail@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CMFVideoThumbnail *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067090`

## callees

- `0x1800516a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066fc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066fad`

## pseudocode

```c
void __fastcall CMFVideoThumbnail::~CMFVideoThumbnail(CMFVideoThumbnail *this)
{
  *(_QWORD *)this = &CMFVideoThumbnail::`vftable'{for `CBaseUnknown'};
  *((_QWORD *)this + 2) = &CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'};
  CloseHandle(*((HANDLE *)this + 46));
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 32);
  *(_QWORD *)this = &CBaseUnknown::`vftable';
}

```

## disassembly

```asm
0x180066f88  push    rbx
0x180066f8a  sub     rsp, 20h
0x180066f8e  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x180066f95  mov     rbx, rcx
0x180066f98  mov     [rcx], rax
0x180066f9b  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x180066fa2  mov     [rcx+10h], rax
0x180066fa6  mov     rcx, [rcx+170h]; hObject
0x180066fad  call    cs:__imp_CloseHandle
0x180066fb4  nop     dword ptr [rax+rax+00h]
0x180066fb9  lea     rcx, [rbx+190h]
0x180066fc0  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180066fc5  lea     rcx, [rbx+28h]; lpCriticalSection
0x180066fc9  call    cs:__imp_DeleteCriticalSection
0x180066fd0  nop     dword ptr [rax+rax+00h]
0x180066fd5  lea     rcx, [rbx+20h]
0x180066fd9  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180066fde  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180066fe5  mov     [rbx], rax
0x180066fe8  add     rsp, 20h
0x180066fec  pop     rbx
0x180066fed  retn
```
