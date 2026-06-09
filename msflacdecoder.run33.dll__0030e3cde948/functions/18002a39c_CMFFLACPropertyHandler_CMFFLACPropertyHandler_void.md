# CMFFLACPropertyHandler::~CMFFLACPropertyHandler(void)

- ea: `0x18002a39c`
- end: `0x18002a40c`
- name: `??1CMFFLACPropertyHandler@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(CMFFLACPropertyHandler *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016cac`
- `0x180016dc4`
- `0x180017060`

## callees

- `0x180016e48`
- `0x18002089c`
- `0x18002a100`
- `0x18002a39c`
- `0x18002fe68`
- `0x18003f550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a3f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a3f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a3b1`

## pseudocode

```c
void __fastcall CMFFLACPropertyHandler::~CMFFLACPropertyHandler(CMFFLACPropertyHandler *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 245);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 245) = 0;
  }
  CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>((char *)this + 2128);
  CFLACMetadataWriter::~CFLACMetadataWriter((CMFFLACPropertyHandler *)((char *)this + 1976));
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 1944);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>((char *)this + 1936);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
  CWMPropHandlerBase::~CWMPropHandlerBase(this);
}

```

## disassembly

```asm
0x18002a39c  push    rbx
0x18002a39e  sub     rsp, 20h
0x18002a3a2  mov     rbx, rcx
0x18002a3a5  mov     rcx, [rcx+7A8h]; hObject
0x18002a3ac  test    rcx, rcx
0x18002a3af  jz      short loc_18002A3C2
0x18002a3b1  call    cs:__imp_CloseHandle
0x18002a3b7  mov     qword ptr [rbx+7A8h], 0
0x18002a3c2  lea     rcx, [rbx+850h]
0x18002a3c9  call    ??1?$CAggregateTelemetry@VCAggregateFlacPropHandlerEvts@@W4FLACDecoderEvtType@@PEATFLACDecoderEvtData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>(void)
0x18002a3ce  lea     rcx, [rbx+7B8h]; this
0x18002a3d5  call    ??1CFLACMetadataWriter@@QEAA@XZ; CFLACMetadataWriter::~CFLACMetadataWriter(void)
0x18002a3da  lea     rcx, [rbx+798h]
0x18002a3e1  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18002a3e6  lea     rcx, [rbx+790h]
0x18002a3ed  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18002a3f2  lea     rcx, [rbx+760h]; lpCriticalSection
0x18002a3f9  call    cs:__imp_DeleteCriticalSection
0x18002a3ff  mov     rcx, rbx; this
0x18002a402  add     rsp, 20h
0x18002a406  pop     rbx
0x18002a407  jmp     ??1CWMPropHandlerBase@@MEAA@XZ; CWMPropHandlerBase::~CWMPropHandlerBase(void)
```
