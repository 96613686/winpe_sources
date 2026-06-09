# CWrapperOutputPin::~CWrapperOutputPin(void)

- ea: `0x180018f10`
- end: `0x180018fca`
- name: `??1CWrapperOutputPin@@UEAA@XZ`
- size: `186`
- prototype: `void __fastcall(CWrapperOutputPin *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018fd0`

## callees

- `0x1800036fc`
- `0x1800071e8`
- `0x180018f10`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180018faa`
- `KERNEL32!DeleteCriticalSection` at `0x180018fb7`
- `KERNEL32!DeleteCriticalSection` at `0x180018faa`
- `KERNEL32!DeleteCriticalSection` at `0x180018fb7`

## pseudocode

```c
void __fastcall CWrapperOutputPin::~CWrapperOutputPin(CWrapperOutputPin *this)
{
  __int64 v2; // rcx
  struct _AMMediaType *v3; // rcx

  *(_QWORD *)this = &CWrapperOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWrapperOutputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CWrapperOutputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 29) = &CWrapperOutputPin::`vftable'{for `IAMStreamConfig'};
  *((_QWORD *)this + 30) = &CWrapperOutputPin::`vftable'{for `IAMVideoAcceleratorNotify'};
  *((_QWORD *)this + 31) = &CWrapperOutputPin::`vftable'{for `IAMVideoCompression'};
  v2 = *((_QWORD *)this + 39);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v2 + 16) + 24LL))(v2 + 16, 1);
  v3 = (struct _AMMediaType *)*((_QWORD *)this + 55);
  if ( v3 )
    DeleteMediaType(v3);
  *((_QWORD *)this + 46) = &CBaseMediaBuffer::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x180018f10  push    rbx
0x180018f12  sub     rsp, 20h
0x180018f16  lea     rax, ??_7CWrapperOutputPin@@6BCUnknown@@@; const CWrapperOutputPin::`vftable'{for `CUnknown'}
0x180018f1d  mov     rbx, rcx
0x180018f20  mov     [rcx], rax
0x180018f23  lea     rax, ??_7CWrapperOutputPin@@6BIPin@@@; const CWrapperOutputPin::`vftable'{for `IPin'}
0x180018f2a  mov     [rcx+18h], rax
0x180018f2e  lea     rax, ??_7CWrapperOutputPin@@6BIQualityControl@@@; const CWrapperOutputPin::`vftable'{for `IQualityControl'}
0x180018f35  mov     [rcx+20h], rax
0x180018f39  lea     rax, ??_7CWrapperOutputPin@@6BIAMStreamConfig@@@; const CWrapperOutputPin::`vftable'{for `IAMStreamConfig'}
0x180018f40  mov     [rcx+0E8h], rax
0x180018f47  lea     rax, ??_7CWrapperOutputPin@@6BIAMVideoAcceleratorNotify@@@; const CWrapperOutputPin::`vftable'{for `IAMVideoAcceleratorNotify'}
0x180018f4e  mov     [rcx+0F0h], rax
0x180018f55  lea     rax, ??_7CWrapperOutputPin@@6BIAMVideoCompression@@@; const CWrapperOutputPin::`vftable'{for `IAMVideoCompression'}
0x180018f5c  mov     [rcx+0F8h], rax
0x180018f63  mov     rcx, [rcx+138h]
0x180018f6a  test    rcx, rcx
0x180018f6d  jz      short loc_180018F84
0x180018f6f  add     rcx, 10h
0x180018f73  mov     edx, 1
0x180018f78  mov     rax, [rcx]
0x180018f7b  mov     rax, [rax+18h]
0x180018f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f84  mov     rcx, [rbx+1B8h]; pv
0x180018f8b  test    rcx, rcx
0x180018f8e  jz      short loc_180018F95
0x180018f90  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180018f95  lea     rax, ??_7CBaseMediaBuffer@@6B@; const CBaseMediaBuffer::`vftable'
0x180018f9c  lea     rcx, [rbx+140h]; lpCriticalSection
0x180018fa3  mov     [rbx+170h], rax
0x180018faa  call    cs:__imp_DeleteCriticalSection
0x180018fb0  lea     rcx, [rbx+108h]; lpCriticalSection
0x180018fb7  call    cs:__imp_DeleteCriticalSection
0x180018fbd  mov     rcx, rbx; this
0x180018fc0  add     rsp, 20h
0x180018fc4  pop     rbx
0x180018fc5  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
```
