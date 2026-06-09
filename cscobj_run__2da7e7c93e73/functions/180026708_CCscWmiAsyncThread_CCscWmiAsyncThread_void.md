# CCscWmiAsyncThread::~CCscWmiAsyncThread(void)

- ea: `0x180026708`
- end: `0x1800267b2`
- name: `??1CCscWmiAsyncThread@@UEAA@XZ`
- size: `170`
- prototype: `void __fastcall(CCscWmiAsyncThread *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180016a40`
- `0x180016b34`
- `0x1800185dc`
- `0x1800267c0`

## callees

- `0x180016280`
- `0x180016974`
- `0x180026708`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002674d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002675c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002676b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002677a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002674d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002675c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002676b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002677a`

## pseudocode

```c
void __fastcall CCscWmiAsyncThread::~CCscWmiAsyncThread(CCscWmiAsyncThread *this)
{
  CRefCounted *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CCscWmiAsyncThread::`vftable';
  v2 = (CRefCounted *)*((_QWORD *)this + 18);
  if ( v2 )
    CRefCounted::ReleaseReference(v2);
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 6);
  if ( v7 )
    CloseHandle(v7);
  _InterlockedDecrement(&g_cRefDll);
  CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>((char *)this + 112);
  CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>((char *)this + 88);
  CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>((char *)this + 64);
  *(_QWORD *)this = &CRefCounted::`vftable';
}

```

## disassembly

```asm
0x180026708  push    rbx
0x18002670a  sub     rsp, 20h
0x18002670e  lea     rax, ??_7CCscWmiAsyncThread@@6B@; const CCscWmiAsyncThread::`vftable'
0x180026715  mov     rbx, rcx
0x180026718  mov     [rcx], rax
0x18002671b  mov     rcx, [rcx+90h]; this
0x180026722  test    rcx, rcx
0x180026725  jz      short loc_18002672C
0x180026727  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18002672c  mov     rcx, [rbx+88h]
0x180026733  test    rcx, rcx
0x180026736  jz      short loc_180026744
0x180026738  mov     rax, [rcx]
0x18002673b  mov     rax, [rax+10h]
0x18002673f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026744  mov     rcx, [rbx+28h]; hObject
0x180026748  test    rcx, rcx
0x18002674b  jz      short loc_180026753
0x18002674d  call    cs:__imp_CloseHandle
0x180026753  mov     rcx, [rbx+20h]; hObject
0x180026757  test    rcx, rcx
0x18002675a  jz      short loc_180026762
0x18002675c  call    cs:__imp_CloseHandle
0x180026762  mov     rcx, [rbx+18h]; hObject
0x180026766  test    rcx, rcx
0x180026769  jz      short loc_180026771
0x18002676b  call    cs:__imp_CloseHandle
0x180026771  mov     rcx, [rbx+30h]; hObject
0x180026775  test    rcx, rcx
0x180026778  jz      short loc_180026780
0x18002677a  call    cs:__imp_CloseHandle
0x180026780  lock dec cs:?g_cRefDll@@3JA; long g_cRefDll
0x180026787  lea     rcx, [rbx+70h]
0x18002678b  call    ??1?$CInterThreadIFacePtr@UIOfflineFilesCache@@@@QEAA@XZ; CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>(void)
0x180026790  lea     rcx, [rbx+58h]
0x180026794  call    ??1?$CInterThreadIFacePtr@UIOfflineFilesCache@@@@QEAA@XZ; CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>(void)
0x180026799  lea     rcx, [rbx+40h]
0x18002679d  call    ??1?$CInterThreadIFacePtr@UIOfflineFilesCache@@@@QEAA@XZ; CInterThreadIFacePtr<IOfflineFilesCache>::~CInterThreadIFacePtr<IOfflineFilesCache>(void)
0x1800267a2  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x1800267a9  mov     [rbx], rax
0x1800267ac  add     rsp, 20h
0x1800267b0  pop     rbx
0x1800267b1  retn
```
