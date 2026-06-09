# CASFOutput::~CASFOutput(void)

- ea: `0x180007e84`
- end: `0x180007f02`
- name: `??1CASFOutput@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CASFOutput *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800080b0`

## callees

- `0x1800036fc`
- `0x180007e84`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007eef`
- `KERNEL32!DeleteCriticalSection` at `0x180007eef`

## pseudocode

```c
void __fastcall CASFOutput::~CASFOutput(CASFOutput *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CASFOutput::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CASFOutput::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CASFOutput::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 29) = &CASFOutput::`vftable'{for `IAMVideoAcceleratorNotify'};
  *((_QWORD *)this + 30) = &CASFOutput::`vftable'{for `IAMWMBufferPass'};
  v2 = *((_QWORD *)this + 50);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x180007e84  push    rbx
0x180007e86  sub     rsp, 20h
0x180007e8a  lea     rax, ??_7CASFOutput@@6BCUnknown@@@; const CASFOutput::`vftable'{for `CUnknown'}
0x180007e91  mov     rbx, rcx
0x180007e94  mov     [rcx], rax
0x180007e97  lea     rax, ??_7CASFOutput@@6BIPin@@@; const CASFOutput::`vftable'{for `IPin'}
0x180007e9e  mov     [rcx+18h], rax
0x180007ea2  lea     rax, ??_7CASFOutput@@6BIQualityControl@@@; const CASFOutput::`vftable'{for `IQualityControl'}
0x180007ea9  mov     [rcx+20h], rax
0x180007ead  lea     rax, ??_7CASFOutput@@6BIAMVideoAcceleratorNotify@@@; const CASFOutput::`vftable'{for `IAMVideoAcceleratorNotify'}
0x180007eb4  mov     [rcx+0E8h], rax
0x180007ebb  lea     rax, ??_7CASFOutput@@6BIAMWMBufferPass@@@; const CASFOutput::`vftable'{for `IAMWMBufferPass'}
0x180007ec2  mov     [rcx+0F0h], rax
0x180007ec9  mov     rcx, [rcx+190h]
0x180007ed0  test    rcx, rcx
0x180007ed3  jz      short loc_180007EE1
0x180007ed5  mov     rax, [rcx]
0x180007ed8  mov     rax, [rax+10h]
0x180007edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee1  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180007ee8  lea     rcx, [rbx+0F8h]; lpCriticalSection
0x180007eef  call    cs:__imp_DeleteCriticalSection
0x180007ef5  mov     rcx, rbx; this
0x180007ef8  add     rsp, 20h
0x180007efc  pop     rbx
0x180007efd  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
```
