# CWMWriterInputPin::CWMWriterInputPin(CWMWriter *,long *,ushort const *,int,ulong,IWMStreamConfig *)

- ea: `0x180013354`
- end: `0x180013508`
- name: `??0CWMWriterInputPin@@QEAA@PEAVCWMWriter@@PEAJPEBGHKPEAUIWMStreamConfig@@@Z`
- size: `436`
- prototype: `CWMWriterInputPin *__usercall@<rax>(CWMWriterInputPin *__hidden this@<rcx>, struct CWMWriter *@<rdx>, int *@<r8>, const unsigned __int16 *@<r9>, int, unsigned int, struct IWMStreamConfig *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e444`

## callees

- `0x180001cfc`
- `0x1800033c0`
- `0x180013354`
- `0x1800138bc`
- `0x18001f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180013417`
- `KERNEL32!InitializeCriticalSection` at `0x180013417`
- `KERNEL32!CreateEventW` at `0x1800134c0`
- `KERNEL32!CreateEventW` at `0x1800134c0`

## pseudocode

```c
CWMWriterInputPin *__fastcall CWMWriterInputPin::CWMWriterInputPin(
        CWMWriterInputPin *this,
        struct CWMWriter *a2,
        int *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int a6,
        struct IWMStreamConfig *a7)
{
  HANDLE EventW; // rax
  __int64 v11; // rcx
  int *v13; // [rsp+20h] [rbp-48h]

  CBasePin::CBasePin(
    this,
    (const unsigned __int16 *)a2,
    a2,
    (struct CWMWriter *)((char *)a2 + 240),
    v13,
    a4,
    PINDIR_INPUT);
  *((_QWORD *)this + 28) = 0;
  *((_WORD *)this + 116) = 0;
  memset_0((char *)this + 240, 0, 0x40u);
  *((_QWORD *)this + 43) = a2;
  *(_QWORD *)this = &CWMWriterInputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWMWriterInputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CWMWriterInputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 27) = &CWMWriterInputPin::`vftable'{for `CBaseInputPin'};
  *((_QWORD *)this + 38) = &CWMWriterInputPin::`vftable'{for `IAMStreamConfig'};
  *((_QWORD *)this + 39) = &CWMWriterInputPin::`vftable'{for `IAMWMBufferPass'};
  *((_QWORD *)this + 40) = &CWMWriterInputPin::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 41) = &CWMWriterInputPin::`vftable'{for `IPinConnection'};
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  *((_DWORD *)this + 99) = a5;
  *((_DWORD *)this + 98) = 0;
  *((_DWORD *)this + 100) = a5 + 1;
  *((_DWORD *)this + 106) = a6;
  *((_QWORD *)this + 56) = a7;
  *((_DWORD *)this + 128) = 1;
  *((_DWORD *)this + 129) = 1;
  *(_QWORD *)((char *)this + 404) = 0;
  *((_QWORD *)this + 52) = 0;
  *(_QWORD *)((char *)this + 428) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 117) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 65) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 42) = EventW;
  if ( EventW )
  {
    *a3 = CWMWriterInputPin::BuildInputTypeList(this);
    v11 = *((_QWORD *)this + 56);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  else
  {
    *a3 = -2147024882;
  }
  return this;
}

```

## disassembly

```asm
0x180013354  push    rbx
0x180013356  push    rbp
0x180013357  push    rsi
0x180013358  push    rdi
0x180013359  sub     rsp, 48h
0x18001335d  mov     rax, r9
0x180013360  mov     rsi, r8
0x180013363  xor     ebp, ebp
0x180013365  lea     r9, [rdx+0F0h]; struct CCritSec *
0x18001336c  mov     [rsp+68h+var_38], ebp; enum _PinDirection
0x180013370  mov     r8, rdx; struct CBaseFilter *
0x180013373  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180013378  mov     rbx, rdx
0x18001337b  mov     rdi, rcx
0x18001337e  call    ??0CBasePin@@QEAA@PEBGPEAVCBaseFilter@@PEAVCCritSec@@PEAJ0W4_PinDirection@@@Z; CBasePin::CBasePin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *,_PinDirection)
0x180013383  lea     rcx, [rdi+0F0h]; void *
0x18001338a  mov     [rdi+0E0h], rbp
0x180013391  xor     edx, edx; Val
0x180013393  mov     [rdi+0E8h], bp
0x18001339a  lea     r8d, [rbp+40h]; Size
0x18001339e  call    memset_0
0x1800133a3  lea     rax, ??_7CWMWriterInputPin@@6BCUnknown@@@; const CWMWriterInputPin::`vftable'{for `CUnknown'}
0x1800133aa  mov     [rdi+158h], rbx
0x1800133b1  mov     [rdi], rax
0x1800133b4  lea     rcx, [rdi+160h]; lpCriticalSection
0x1800133bb  lea     rax, ??_7CWMWriterInputPin@@6BIPin@@@; const CWMWriterInputPin::`vftable'{for `IPin'}
0x1800133c2  mov     [rdi+18h], rax
0x1800133c6  lea     rax, ??_7CWMWriterInputPin@@6BIQualityControl@@@; const CWMWriterInputPin::`vftable'{for `IQualityControl'}
0x1800133cd  mov     [rdi+20h], rax
0x1800133d1  lea     rax, ??_7CWMWriterInputPin@@6BCBaseInputPin@@@; const CWMWriterInputPin::`vftable'{for `CBaseInputPin'}
0x1800133d8  mov     [rdi+0D8h], rax
0x1800133df  lea     rax, ??_7CWMWriterInputPin@@6BIAMStreamConfig@@@; const CWMWriterInputPin::`vftable'{for `IAMStreamConfig'}
0x1800133e6  mov     [rdi+130h], rax
0x1800133ed  lea     rax, ??_7CWMWriterInputPin@@6BIAMWMBufferPass@@@; const CWMWriterInputPin::`vftable'{for `IAMWMBufferPass'}
0x1800133f4  mov     [rdi+138h], rax
0x1800133fb  lea     rax, ??_7CWMWriterInputPin@@6BIReferenceClock@@@; const CWMWriterInputPin::`vftable'{for `IReferenceClock'}
0x180013402  mov     [rdi+140h], rax
0x180013409  lea     rax, ??_7CWMWriterInputPin@@6BIPinConnection@@@; const CWMWriterInputPin::`vftable'{for `IPinConnection'}
0x180013410  mov     [rdi+148h], rax
0x180013417  call    cs:__imp_InitializeCriticalSection
0x18001341d  mov     eax, [rsp+68h+arg_20]
0x180013424  xor     r9d, r9d; lpName
0x180013427  mov     [rdi+18Ch], eax
0x18001342d  xor     r8d, r8d; bInitialState
0x180013430  inc     eax
0x180013432  mov     [rdi+188h], ebp
0x180013438  mov     [rdi+190h], eax
0x18001343e  xor     edx, edx; bManualReset
0x180013440  mov     eax, [rsp+68h+arg_28]
0x180013447  xor     ecx, ecx; lpEventAttributes
0x180013449  mov     [rdi+1A8h], eax
0x18001344f  mov     rax, [rsp+68h+arg_30]
0x180013457  mov     [rdi+1C0h], rax
0x18001345e  lea     eax, [rbp+1]
0x180013461  mov     [rdi+200h], eax
0x180013467  mov     [rdi+204h], eax
0x18001346d  mov     [rdi+194h], rbp
0x180013474  mov     [rdi+1A0h], rbp
0x18001347b  mov     [rdi+1ACh], rbp
0x180013482  mov     [rdi+1B8h], rbp
0x180013489  mov     [rdi+1C8h], rbp
0x180013490  mov     [rdi+1D4h], ebp
0x180013496  mov     [rdi+1D8h], rbp
0x18001349d  mov     [rdi+1E0h], rbp
0x1800134a4  mov     [rdi+1E8h], rbp
0x1800134ab  mov     [rdi+1F0h], rbp
0x1800134b2  mov     [rdi+1F8h], rbp
0x1800134b9  mov     [rdi+208h], rbp
0x1800134c0  call    cs:__imp_CreateEventW
0x1800134c6  mov     [rdi+150h], rax
0x1800134cd  test    rax, rax
0x1800134d0  jnz     short loc_1800134DA
0x1800134d2  mov     dword ptr [rsi], 8007000Eh
0x1800134d8  jmp     short loc_1800134FC
0x1800134da  mov     rcx, rdi; this
0x1800134dd  call    ?BuildInputTypeList@CWMWriterInputPin@@QEAAJXZ; CWMWriterInputPin::BuildInputTypeList(void)
0x1800134e2  mov     [rsi], eax
0x1800134e4  mov     rcx, [rdi+1C0h]
0x1800134eb  test    rcx, rcx
0x1800134ee  jz      short loc_1800134FC
0x1800134f0  mov     rax, [rcx]
0x1800134f3  mov     rax, [rax+8]
0x1800134f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134fc  mov     rax, rdi
0x1800134ff  add     rsp, 48h
0x180013503  pop     rdi
0x180013504  pop     rsi
0x180013505  pop     rbp
0x180013506  pop     rbx
0x180013507  retn
```
