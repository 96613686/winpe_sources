# CMFSourceMPEG2TSPin::CMFSourceMPEG2TSPin(long *,CMFSourceFilter *)

- ea: `0x18004f758`
- end: `0x18004f91e`
- name: `??0CMFSourceMPEG2TSPin@@QEAA@PEAJPEAVCMFSourceFilter@@@Z`
- size: `454`
- prototype: `CMFSourceMPEG2TSPin *(CMFSourceMPEG2TSPin *__hidden this, int *, struct CMFSourceFilter *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18008b044`

## callees

- `0x18000e8b8`
- `0x18000f6c8`
- `0x18004f924`
- `0x18004f93c`
- `0x18004f954`
- `0x180074a06`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004f863`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004f863`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f879`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f879`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f8e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004f8e8`

## pseudocode

```c
CMFSourceMPEG2TSPin *__fastcall CMFSourceMPEG2TSPin::CMFSourceMPEG2TSPin(
        CMFSourceMPEG2TSPin *this,
        unsigned __int16 *a2,
        struct CMFSourceFilter *a3)
{
  void *v6; // rcx
  const unsigned __int16 *v8; // [rsp+20h] [rbp-38h]

  CSourceStream::CSourceStream(this, a2, (int *)a2, a3, v8);
  *((_QWORD *)this + 48) = -1;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *(_QWORD *)this = &CMFSourceMPEG2TSPin::`vftable'{for `CSourceStream'};
  *((_QWORD *)this + 15) = &CMFSourceMPEG2TSPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 18) = &CMFSourceMPEG2TSPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 19) = &CMFSourceMPEG2TSPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 45) = &CMFSourceMPEG2TSPin::`vftable'{for `CMFSourceBufferingSupport'};
  *((_QWORD *)this + 49) = &CMFSourceMPEG2TSPin::`vftable'{for `IAsyncReader'};
  *((_QWORD *)this + 50) = &CMFSourceMPEG2TSPin::`vftable'{for `ICodecAPI'};
  *((_QWORD *)this + 51) = &CMFSourceMPEG2TSPin::`vftable'{for `IReaderSetPosition'};
  CAMEvent::CAMEvent((CMFSourceMPEG2TSPin *)((char *)this + 416), 1, (int *)a2);
  *((_QWORD *)this + 53) = 0;
  CMFSourceMPEG2TSPin::OnSyncReadAsyncCallback::OnSyncReadAsyncCallback((CMFSourceMPEG2TSPin *)((char *)this + 432));
  CMFSourceMPEG2TSPin::OnEventAsyncCallback::OnEventAsyncCallback((CMFSourceMPEG2TSPin *)((char *)this + 440));
  *((_QWORD *)this + 56) = a3;
  *((_DWORD *)this + 114) = 0;
  *((_WORD *)this + 230) = 1;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  *((_QWORD *)this + 66) = CreateEventW(0, 0, 0, 0);
  *((_DWORD *)this + 134) = 0;
  *(_QWORD *)((char *)this + 548) = 0;
  *((_DWORD *)this + 139) = 0;
  CMFSourceMPEG2TSPin::OnBufferedReadAsyncCallback::OnBufferedReadAsyncCallback((CMFSourceMPEG2TSPin *)((char *)this + 560));
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 72) = 0;
  v6 = (void *)*((_QWORD *)this + 52);
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  SetEvent(v6);
  *((_DWORD *)this + 106) = 1;
  memset_0((char *)this + 632, 0, 0x200u);
  return this;
}

```

## disassembly

```asm
0x18004f758  push    rbx
0x18004f75a  push    rbp
0x18004f75b  push    rsi
0x18004f75c  push    rdi
0x18004f75d  push    r14
0x18004f75f  sub     rsp, 30h
0x18004f763  mov     rdi, r8
0x18004f766  mov     r9, r8; struct CSource *
0x18004f769  mov     r8, rdx; int *
0x18004f76c  mov     rbx, rdx
0x18004f76f  mov     r14, rcx
0x18004f772  call    ??0CSourceStream@@QEAA@PEBGPEAJPEAVCSource@@0@Z; CSourceStream::CSourceStream(ushort const *,long *,CSource *,ushort const *)
0x18004f777  mov     qword ptr [r14+180h], 0FFFFFFFFFFFFFFFFh
0x18004f782  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BCSourceStream@@@; const CMFSourceMPEG2TSPin::`vftable'{for `CSourceStream'}
0x18004f789  xor     ebp, ebp
0x18004f78b  lea     rsi, [r14+1A0h]
0x18004f792  mov     [r14+170h], rbp
0x18004f799  mov     r8, rbx; int *
0x18004f79c  mov     [r14+178h], rbp
0x18004f7a3  mov     rcx, rsi; this
0x18004f7a6  mov     [r14], rax
0x18004f7a9  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BCUnknown@@@; const CMFSourceMPEG2TSPin::`vftable'{for `CUnknown'}
0x18004f7b0  mov     [r14+78h], rax
0x18004f7b4  lea     ebx, [rbp+1]
0x18004f7b7  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BIPin@@@; const CMFSourceMPEG2TSPin::`vftable'{for `IPin'}
0x18004f7be  mov     edx, ebx; int
0x18004f7c0  mov     [r14+90h], rax
0x18004f7c7  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BIQualityControl@@@; const CMFSourceMPEG2TSPin::`vftable'{for `IQualityControl'}
0x18004f7ce  mov     [r14+98h], rax
0x18004f7d5  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BCMFSourceBufferingSupport@@@; const CMFSourceMPEG2TSPin::`vftable'{for `CMFSourceBufferingSupport'}
0x18004f7dc  mov     [r14+168h], rax
0x18004f7e3  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BIAsyncReader@@@; const CMFSourceMPEG2TSPin::`vftable'{for `IAsyncReader'}
0x18004f7ea  mov     [r14+188h], rax
0x18004f7f1  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BICodecAPI@@@; const CMFSourceMPEG2TSPin::`vftable'{for `ICodecAPI'}
0x18004f7f8  mov     [r14+190h], rax
0x18004f7ff  lea     rax, ??_7CMFSourceMPEG2TSPin@@6BIReaderSetPosition@@@; const CMFSourceMPEG2TSPin::`vftable'{for `IReaderSetPosition'}
0x18004f806  mov     [r14+198h], rax
0x18004f80d  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x18004f812  lea     rcx, [r14+1B0h]; this
0x18004f819  mov     [r14+1A8h], rbp
0x18004f820  call    ??0OnSyncReadAsyncCallback@CMFSourceMPEG2TSPin@@QEAA@XZ; CMFSourceMPEG2TSPin::OnSyncReadAsyncCallback::OnSyncReadAsyncCallback(void)
0x18004f825  lea     rcx, [r14+1B8h]; this
0x18004f82c  call    ??0OnEventAsyncCallback@CMFSourceMPEG2TSPin@@QEAA@XZ; CMFSourceMPEG2TSPin::OnEventAsyncCallback::OnEventAsyncCallback(void)
0x18004f831  lea     rcx, [r14+1E8h]; lpCriticalSection
0x18004f838  mov     [r14+1C0h], rdi
0x18004f83f  mov     [r14+1C8h], ebp
0x18004f846  mov     [r14+1CCh], bx
0x18004f84e  mov     [r14+1D0h], rbp
0x18004f855  mov     [r14+1D8h], rbp
0x18004f85c  mov     [r14+1E0h], rbp
0x18004f863  call    cs:__imp_InitializeCriticalSection
0x18004f86a  nop     dword ptr [rax+rax+00h]
0x18004f86f  xor     r9d, r9d; lpName
0x18004f872  xor     r8d, r8d; bInitialState
0x18004f875  xor     edx, edx; bManualReset
0x18004f877  xor     ecx, ecx; lpEventAttributes
0x18004f879  call    cs:__imp_CreateEventW
0x18004f880  nop     dword ptr [rax+rax+00h]
0x18004f885  mov     [r14+210h], rax
0x18004f88c  lea     rcx, [r14+230h]; this
0x18004f893  mov     [r14+218h], ebp
0x18004f89a  mov     [r14+224h], rbp
0x18004f8a1  mov     [r14+22Ch], ebp
0x18004f8a8  call    ??0OnBufferedReadAsyncCallback@CMFSourceMPEG2TSPin@@QEAA@XZ; CMFSourceMPEG2TSPin::OnBufferedReadAsyncCallback::OnBufferedReadAsyncCallback(void)
0x18004f8ad  mov     [r14+238h], ebp
0x18004f8b4  mov     [r14+240h], rbp
0x18004f8bb  mov     rcx, [rsi]; hEvent
0x18004f8be  mov     [r14+248h], rbp
0x18004f8c5  mov     [r14+250h], rbp
0x18004f8cc  mov     [r14+258h], rbp
0x18004f8d3  mov     [r14+260h], rbp
0x18004f8da  mov     [r14+268h], rbp
0x18004f8e1  mov     [r14+270h], rbp
0x18004f8e8  call    cs:__imp_SetEvent
0x18004f8ef  nop     dword ptr [rax+rax+00h]
0x18004f8f4  lea     rcx, [r14+278h]; void *
0x18004f8fb  mov     [r14+1A8h], ebx
0x18004f902  xor     edx, edx; Val
0x18004f904  mov     r8d, 200h; Size
0x18004f90a  call    memset_0
0x18004f90f  mov     rax, r14
0x18004f912  add     rsp, 30h
0x18004f916  pop     r14
0x18004f918  pop     rdi
0x18004f919  pop     rsi
0x18004f91a  pop     rbp
0x18004f91b  pop     rbx
0x18004f91c  retn
```
