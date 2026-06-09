# CFLACSource::~CFLACSource(void)

- ea: `0x180020ab8`
- end: `0x180020ba0`
- name: `??1CFLACSource@@UEAA@XZ`
- size: `232`
- prototype: `void __fastcall(CFLACSource *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020908`
- `0x180020e70`

## callees

- `0x180002b00`
- `0x180016e48`
- `0x18002089c`
- `0x180020990`
- `0x180020a8c`
- `0x180020ab8`
- `0x180026d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020b74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020b74`

## pseudocode

```c
void __fastcall CFLACSource::~CFLACSource(CFLACSource *this)
{
  CFLACSource *v2; // rcx

  *(_QWORD *)this = &CFLACSource::`vftable'{for `OpQueue<CSourceOp>'};
  v2 = (CFLACSource *)((char *)this + 80);
  *(_QWORD *)v2 = &CFLACSource::`vftable'{for `IMFMediaSource'};
  *((_QWORD *)this + 11) = &CFLACSource::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 12) = &CFLACSource::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 13) = &CFLACSource::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 14) = &CFLACSource::`vftable'{for `FLAC::Decoder::Stream'};
  *((_QWORD *)this + 16) = &CFLACSource::`vftable'{for `IMFTelemetryComponent'};
  if ( *((_DWORD *)this + 56) != 5 )
    CFLACSource::Shutdown(v2);
  CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>((char *)this + 456);
  CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,enum FLACDecoderEvtType,FLACDecoderEvtData *,0,0>((char *)this + 424);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 416);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 408);
  CBuffReader::~CBuffReader((CFLACSource *)((char *)this + 328));
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>((char *)this + 272);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  FLAC::Decoder::Stream::~Stream((CFLACSource *)((char *)this + 112));
  *(_QWORD *)this = &OpQueue<CSourceOp>::`vftable';
  ComPtrList<CSourceOp,0>::~ComPtrList<CSourceOp,0>((char *)this + 8);
}

```

## disassembly

```asm
0x180020ab8  mov     [rsp+arg_0], rbx
0x180020abd  push    rdi
0x180020abe  sub     rsp, 20h
0x180020ac2  mov     rbx, rcx
0x180020ac5  lea     rax, ??_7CFLACSource@@6B?$OpQueue@VCSourceOp@@@@@; const CFLACSource::`vftable'{for `OpQueue<CSourceOp>'}
0x180020acc  mov     [rcx], rax
0x180020acf  add     rcx, 50h ; 'P'; this
0x180020ad3  lea     rax, ??_7CFLACSource@@6BIMFMediaSource@@@; const CFLACSource::`vftable'{for `IMFMediaSource'}
0x180020ada  mov     [rcx], rax
0x180020add  lea     rax, ??_7CFLACSource@@6BIMFGetService@@@; const CFLACSource::`vftable'{for `IMFGetService'}
0x180020ae4  mov     [rbx+58h], rax
0x180020ae8  lea     rax, ??_7CFLACSource@@6BIMFRateSupport@@@; const CFLACSource::`vftable'{for `IMFRateSupport'}
0x180020aef  mov     [rbx+60h], rax
0x180020af3  lea     rax, ??_7CFLACSource@@6BIMFRateControl@@@; const CFLACSource::`vftable'{for `IMFRateControl'}
0x180020afa  mov     [rbx+68h], rax
0x180020afe  lea     rax, ??_7CFLACSource@@6BStream@Decoder@FLAC@@@; const CFLACSource::`vftable'{for `FLAC::Decoder::Stream'}
0x180020b05  mov     [rbx+70h], rax
0x180020b09  lea     rax, ??_7CFLACSource@@6BIMFTelemetryComponent@@@; const CFLACSource::`vftable'{for `IMFTelemetryComponent'}
0x180020b10  mov     [rbx+80h], rax
0x180020b17  cmp     dword ptr [rbx+0E0h], 5
0x180020b1e  jz      short loc_180020B25
0x180020b20  call    ?Shutdown@CFLACSource@@UEAAJXZ; CFLACSource::Shutdown(void)
0x180020b25  lea     rcx, [rbx+1C8h]
0x180020b2c  call    ??1?$CAggregateTelemetry@VCAggregateFlacPropHandlerEvts@@W4FLACDecoderEvtType@@PEATFLACDecoderEvtData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>(void)
0x180020b31  lea     rcx, [rbx+1A8h]
0x180020b38  call    ??1?$CAggregateTelemetry@VCAggregateFlacPropHandlerEvts@@W4FLACDecoderEvtType@@PEATFLACDecoderEvtData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>::~CAggregateTelemetry<CAggregateFlacPropHandlerEvts,FLACDecoderEvtType,FLACDecoderEvtData *,0,0>(void)
0x180020b3d  lea     rcx, [rbx+1A0h]
0x180020b44  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180020b49  lea     rcx, [rbx+198h]
0x180020b50  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180020b55  lea     rcx, [rbx+148h]; this
0x180020b5c  call    ??1CBuffReader@@QEAA@XZ; CBuffReader::~CBuffReader(void)
0x180020b61  lea     rcx, [rbx+110h]
0x180020b68  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180020b6d  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x180020b74  call    cs:__imp_DeleteCriticalSection
0x180020b7a  lea     rcx, [rbx+70h]; this
0x180020b7e  call    ??1Stream@Decoder@FLAC@@UEAA@XZ; FLAC::Decoder::Stream::~Stream(void)
0x180020b83  lea     rax, ??_7?$OpQueue@VCSourceOp@@@@6B@; const OpQueue<CSourceOp>::`vftable'
0x180020b8a  mov     [rbx], rax
0x180020b8d  lea     rcx, [rbx+8]
0x180020b91  mov     rbx, [rsp+28h+arg_0]
0x180020b96  add     rsp, 20h
0x180020b9a  pop     rdi
0x180020b9b  jmp     ??1?$ComPtrList@VCSourceOp@@$0A@@@UEAA@XZ; ComPtrList<CSourceOp,0>::~ComPtrList<CSourceOp,0>(void)
```
