# CMFVideoThumbnail::~CMFVideoThumbnail(void)

- ea: `0x180064444`
- end: `0x18006449e`
- name: `??1CMFVideoThumbnail@@UEAA@XZ`
- size: `90`
- prototype: `void __fastcall(CMFVideoThumbnail *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064540`

## callees

- `0x18004f47c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006447f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006447f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064469`

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
0x180064444  push    rbx
0x180064446  sub     rsp, 20h
0x18006444a  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x180064451  mov     rbx, rcx
0x180064454  mov     [rcx], rax
0x180064457  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x18006445e  mov     [rcx+10h], rax
0x180064462  mov     rcx, [rcx+170h]; hObject
0x180064469  call    cs:__imp_CloseHandle
0x18006446f  lea     rcx, [rbx+190h]
0x180064476  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18006447b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18006447f  call    cs:__imp_DeleteCriticalSection
0x180064485  lea     rcx, [rbx+20h]
0x180064489  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18006448e  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180064495  mov     [rbx], rax
0x180064498  add     rsp, 20h
0x18006449c  pop     rbx
0x18006449d  retn
```
