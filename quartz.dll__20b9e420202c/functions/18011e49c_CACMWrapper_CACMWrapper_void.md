# CACMWrapper::~CACMWrapper(void)

- ea: `0x18011e49c`
- end: `0x18011e5c4`
- name: `??1CACMWrapper@@UEAA@XZ`
- size: `296`
- prototype: `void __fastcall(CACMWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18011e610`

## callees

- `0x18007b8f8`
- `0x18011e49c`
- `0x1801443cc`
- `0x18015e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18011e58b`
- `KERNEL32!DeleteCriticalSection` at `0x18011e58b`
- `KERNEL32!LeaveCriticalSection` at `0x18011e578`
- `KERNEL32!LeaveCriticalSection` at `0x18011e578`
- `KERNEL32!EnterCriticalSection` at `0x18011e4f4`
- `KERNEL32!EnterCriticalSection` at `0x18011e4f4`
- `ole32!CoTaskMemFree` at `0x18011e53a`
- `ole32!CoTaskMemFree` at `0x18011e569`
- `ole32!CoTaskMemFree` at `0x18011e53a`
- `ole32!CoTaskMemFree` at `0x18011e569`

## pseudocode

```c
void __fastcall CACMWrapper::~CACMWrapper(CACMWrapper *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CACMWrapper::`vftable'{for `CUnknown'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  *((_QWORD *)this + 3) = &CMjpegDec::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CMpegAudioCodec::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 29) = &CACMWrapper::`vftable'{for `IPersistPropertyBag'};
  *((_QWORD *)this + 30) = &CACMWrapper::`vftable'{for `CPersistStream'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v3 = *((_QWORD *)this + 32);
  if ( v3 )
  {
    ((void (__fastcall *)(__int64, _QWORD))qword_18019E8F8)(v3, 0);
    *((_QWORD *)this + 32) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 36);
  if ( !v4 )
    goto LABEL_7;
  while ( 1 )
  {
    CoTaskMemFree(v4);
LABEL_7:
    v5 = *((unsigned int *)this + 500);
    *((_DWORD *)this + 500) = v5 - 1;
    if ( (int)v5 <= 0 )
      break;
    v4 = (void *)*((_QWORD *)this + v5 + 49);
  }
  if ( *((_DWORD *)this + 78) )
    CoTaskMemFree(*((LPVOID *)this + 38));
  LeaveCriticalSection(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  *((_QWORD *)this + 30) = &CPersistStream::`vftable';
  CACMDynLink::~CACMDynLink((CACMWrapper *)((char *)this + 256));
  CTransformFilter::~CTransformFilter(this);
}

```

## disassembly

```asm
0x18011e49c  mov     [rsp+arg_0], rbx
0x18011e4a1  mov     [rsp+arg_8], rsi
0x18011e4a6  push    rdi
0x18011e4a7  sub     rsp, 20h
0x18011e4ab  lea     rax, ??_7CACMWrapper@@6BCUnknown@@@; const CACMWrapper::`vftable'{for `CUnknown'}
0x18011e4b2  mov     rdi, rcx
0x18011e4b5  mov     [rcx], rax
0x18011e4b8  lea     rbx, [rcx+88h]
0x18011e4bf  lea     rax, ??_7CMjpegDec@@6BIBaseFilter@@@; const CMjpegDec::`vftable'{for `IBaseFilter'}
0x18011e4c6  mov     [rcx+18h], rax
0x18011e4ca  lea     rax, ??_7CMpegAudioCodec@@6BIAMovieSetup@@@; const CMpegAudioCodec::`vftable'{for `IAMovieSetup'}
0x18011e4d1  mov     [rcx+20h], rax
0x18011e4d5  lea     rax, ??_7CACMWrapper@@6BIPersistPropertyBag@@@; const CACMWrapper::`vftable'{for `IPersistPropertyBag'}
0x18011e4dc  mov     [rcx+0E8h], rax
0x18011e4e3  lea     rax, ??_7CACMWrapper@@6BCPersistStream@@@; const CACMWrapper::`vftable'{for `CPersistStream'}
0x18011e4ea  mov     [rcx+0F0h], rax
0x18011e4f1  mov     rcx, rbx; lpCriticalSection
0x18011e4f4  call    cs:__imp_EnterCriticalSection
0x18011e4fb  nop     dword ptr [rax+rax+00h]
0x18011e500  lea     rsi, [rdi+100h]
0x18011e507  mov     rcx, [rsi]
0x18011e50a  test    rcx, rcx
0x18011e50d  jz      short loc_18011E524
0x18011e50f  mov     rax, cs:qword_18019E8F8
0x18011e516  xor     edx, edx
0x18011e518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e51d  mov     qword ptr [rsi], 0
0x18011e524  mov     rcx, [rdi+120h]
0x18011e52b  test    rcx, rcx
0x18011e52e  jz      short loc_18011E546
0x18011e530  jmp     short loc_18011E53A
0x18011e532  mov     rcx, [rdi+rcx*8+188h]; pv
0x18011e53a  call    cs:__imp_CoTaskMemFree
0x18011e541  nop     dword ptr [rax+rax+00h]
0x18011e546  mov     ecx, [rdi+7D0h]
0x18011e54c  lea     eax, [rcx-1]
0x18011e54f  mov     [rdi+7D0h], eax
0x18011e555  test    ecx, ecx
0x18011e557  jg      short loc_18011E532
0x18011e559  cmp     dword ptr [rdi+138h], 0
0x18011e560  jz      short loc_18011E575
0x18011e562  mov     rcx, [rdi+130h]; pv
0x18011e569  call    cs:__imp_CoTaskMemFree
0x18011e570  nop     dword ptr [rax+rax+00h]
0x18011e575  mov     rcx, rbx; lpCriticalSection
0x18011e578  call    cs:__imp_LeaveCriticalSection
0x18011e57f  nop     dword ptr [rax+rax+00h]
0x18011e584  lea     rcx, [rdi+148h]; lpCriticalSection
0x18011e58b  call    cs:__imp_DeleteCriticalSection
0x18011e592  nop     dword ptr [rax+rax+00h]
0x18011e597  lea     rax, ??_7CPersistStream@@6B@; const CPersistStream::`vftable'
0x18011e59e  mov     rcx, rsi; this
0x18011e5a1  mov     [rdi+0F0h], rax
0x18011e5a8  call    ??1CACMDynLink@@QEAA@XZ; CACMDynLink::~CACMDynLink(void)
0x18011e5ad  mov     rcx, rdi; this
0x18011e5b0  mov     rbx, [rsp+28h+arg_0]
0x18011e5b5  mov     rsi, [rsp+28h+arg_8]
0x18011e5ba  add     rsp, 20h
0x18011e5be  pop     rdi
0x18011e5bf  jmp     ??1CTransformFilter@@UEAA@XZ; CTransformFilter::~CTransformFilter(void)
```
