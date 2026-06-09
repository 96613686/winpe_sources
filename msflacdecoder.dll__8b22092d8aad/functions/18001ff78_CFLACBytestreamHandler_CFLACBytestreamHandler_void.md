# CFLACBytestreamHandler::~CFLACBytestreamHandler(void)

- ea: `0x18001ff78`
- end: `0x18001ffdf`
- name: `??1CFLACBytestreamHandler@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CFLACBytestreamHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016c24`
- `0x180016d18`

## callees

- `0x180016e48`
- `0x18001ff78`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ffc2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ffc2`

## pseudocode

```c
void __fastcall CFLACBytestreamHandler::~CFLACBytestreamHandler(CFLACBytestreamHandler *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CFLACBytestreamHandler::`vftable'{for `IMFAsyncCallback'};
  *((_QWORD *)this + 1) = &CFLACBytestreamHandler::`vftable'{for `IMFByteStreamHandler'};
  *((_QWORD *)this + 2) = &CFLACBytestreamHandler::`vftable'{for `IMFTelemetryComponent'};
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 6) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 64);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 56);
}

```

## disassembly

```asm
0x18001ff78  push    rbx
0x18001ff7a  sub     rsp, 20h
0x18001ff7e  lea     rax, ??_7CFLACBytestreamHandler@@6BIMFAsyncCallback@@@
0x18001ff85  mov     rbx, rcx
0x18001ff88  mov     [rcx], rax
0x18001ff8b  lea     rax, ??_7CFLACBytestreamHandler@@6BIMFByteStreamHandler@@@
0x18001ff92  mov     [rcx+8], rax
0x18001ff96  lea     rax, ??_7CFLACBytestreamHandler@@6BIMFTelemetryComponent@@@
0x18001ff9d  mov     [rcx+10h], rax
0x18001ffa1  mov     rcx, [rcx+30h]
0x18001ffa5  test    rcx, rcx
0x18001ffa8  jz      short loc_18001FFBE
0x18001ffaa  mov     rax, [rcx]
0x18001ffad  mov     rax, [rax+10h]
0x18001ffb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffb6  mov     qword ptr [rbx+30h], 0
0x18001ffbe  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001ffc2  call    cs:__imp_DeleteCriticalSection
0x18001ffc8  lea     rcx, [rbx+40h]
0x18001ffcc  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ
0x18001ffd1  lea     rcx, [rbx+38h]
0x18001ffd5  add     rsp, 20h
0x18001ffd9  pop     rbx
0x18001ffda  jmp     ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ
```
