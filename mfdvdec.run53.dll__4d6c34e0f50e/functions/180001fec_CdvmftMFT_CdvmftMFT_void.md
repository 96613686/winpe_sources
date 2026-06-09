# CdvmftMFT::~CdvmftMFT(void)

- ea: `0x180001fec`
- end: `0x18000208a`
- name: `??1CdvmftMFT@@UEAA@XZ`
- size: `158`
- prototype: `void __fastcall(CdvmftMFT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800020a0`

## callees

- `0x180001fec`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002077`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002077`

## pseudocode

```c
void __fastcall CdvmftMFT::~CdvmftMFT(CdvmftMFT *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &CdvmftMFT::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CdvmftMFT::`vftable'{for `CMFTBase'};
  *((_QWORD *)this + 11) = &CdvmftMFT::`vftable'{for `IMFQualityAdvise2'};
  *((_QWORD *)this + 12) = &CdvmftMFT::`vftable'{for `IMFQualityAdviseLimits'};
  *((_QWORD *)this + 13) = &CdvmftMFT::`vftable'{for `IMFRateControl'};
  *((_QWORD *)this + 14) = &CdvmftMFT::`vftable'{for `IMFRateSupport'};
  *((_QWORD *)this + 15) = &CdvmftMFT::`vftable'{for `IMFGetService'};
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  if ( v3 )
    (**v3)(v3, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x180001fec  push    rbx
0x180001fee  sub     rsp, 20h
0x180001ff2  lea     rax, ??_7CdvmftMFT@@6BCUnknown@@@; const CdvmftMFT::`vftable'{for `CUnknown'}
0x180001ff9  mov     rbx, rcx
0x180001ffc  mov     [rcx], rax
0x180001fff  lea     rax, ??_7CdvmftMFT@@6BCMFTBase@@@; const CdvmftMFT::`vftable'{for `CMFTBase'}
0x180002006  mov     [rcx+18h], rax
0x18000200a  lea     rax, ??_7CdvmftMFT@@6BIMFQualityAdvise2@@@; const CdvmftMFT::`vftable'{for `IMFQualityAdvise2'}
0x180002011  mov     [rcx+58h], rax
0x180002015  lea     rax, ??_7CdvmftMFT@@6BIMFQualityAdviseLimits@@@; const CdvmftMFT::`vftable'{for `IMFQualityAdviseLimits'}
0x18000201c  mov     [rcx+60h], rax
0x180002020  lea     rax, ??_7CdvmftMFT@@6BIMFRateControl@@@; const CdvmftMFT::`vftable'{for `IMFRateControl'}
0x180002027  mov     [rcx+68h], rax
0x18000202b  lea     rax, ??_7CdvmftMFT@@6BIMFRateSupport@@@; const CdvmftMFT::`vftable'{for `IMFRateSupport'}
0x180002032  mov     [rcx+70h], rax
0x180002036  lea     rax, ??_7CdvmftMFT@@6BIMFGetService@@@; const CdvmftMFT::`vftable'{for `IMFGetService'}
0x18000203d  mov     [rcx+78h], rax
0x180002041  mov     rcx, [rcx+20h]
0x180002045  test    rcx, rcx
0x180002048  jz      short loc_18000205A
0x18000204a  mov     rax, [rcx]
0x18000204d  mov     edx, 1
0x180002052  mov     rax, [rax]
0x180002055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000205a  mov     rcx, [rbx+28h]
0x18000205e  test    rcx, rcx
0x180002061  jz      short loc_180002073
0x180002063  mov     rax, [rcx]
0x180002066  mov     edx, 1
0x18000206b  mov     rax, [rax]
0x18000206e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002073  lea     rcx, [rbx+30h]; lpCriticalSection
0x180002077  call    cs:__imp_DeleteCriticalSection
0x18000207d  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180002084  add     rsp, 20h
0x180002088  pop     rbx
0x180002089  retn
```
