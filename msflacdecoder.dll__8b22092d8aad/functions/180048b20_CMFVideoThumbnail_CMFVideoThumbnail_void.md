# CMFVideoThumbnail::~CMFVideoThumbnail(void)

- ea: `0x180048b20`
- end: `0x180048b7c`
- name: `??1CMFVideoThumbnail@@UEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CMFVideoThumbnail *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048c70`

## callees

- `0x180016e48`
- `0x18002a100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048b5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFVideoThumbnail::~CMFVideoThumbnail(CMFVideoThumbnail *this)
{
  *(_QWORD *)this = &CMFVideoThumbnail::`vftable'{for `CBaseUnknown'};
  *((_QWORD *)this + 2) = &CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'};
  CloseHandle(*((HANDLE *)this + 46));
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 32);
  *(_QWORD *)this = &CBaseUnknown::`vftable';
}

```

## disassembly

```asm
0x180048b20  push    rbx
0x180048b22  sub     rsp, 20h
0x180048b26  mov     rbx, rcx
0x180048b29  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x180048b30  mov     [rcx], rax
0x180048b33  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x180048b3a  mov     [rcx+10h], rax
0x180048b3e  mov     rcx, [rcx+170h]; hObject
0x180048b45  call    cs:__imp_CloseHandle
0x180048b4b  lea     rcx, [rbx+190h]
0x180048b52  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180048b57  lea     rcx, [rbx+28h]; lpCriticalSection
0x180048b5b  call    cs:__imp_DeleteCriticalSection
0x180048b61  nop
0x180048b62  lea     rcx, [rbx+20h]
0x180048b66  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180048b6b  nop
0x180048b6c  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180048b73  mov     [rbx], rax
0x180048b76  add     rsp, 20h
0x180048b7a  pop     rbx
0x180048b7b  retn
```
