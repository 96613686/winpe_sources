# CMediaWrapperFilter::~CMediaWrapperFilter(void)

- ea: `0x180015448`
- end: `0x1800155bc`
- name: `??1CMediaWrapperFilter@@UEAA@XZ`
- size: `372`
- prototype: `void __fastcall(CMediaWrapperFilter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015650`

## callees

- `0x180003678`
- `0x180015448`
- `0x180016924`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001557d`
- `KERNEL32!DeleteCriticalSection` at `0x18001558a`
- `KERNEL32!DeleteCriticalSection` at `0x180015597`
- `KERNEL32!DeleteCriticalSection` at `0x1800155a4`
- `KERNEL32!DeleteCriticalSection` at `0x18001557d`
- `KERNEL32!DeleteCriticalSection` at `0x18001558a`
- `KERNEL32!DeleteCriticalSection` at `0x180015597`
- `KERNEL32!DeleteCriticalSection` at `0x1800155a4`

## pseudocode

```c
void __fastcall CMediaWrapperFilter::~CMediaWrapperFilter(CMediaWrapperFilter *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CMediaWrapperFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CMediaWrapperFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CMediaWrapperFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CMediaWrapperFilter::`vftable'{for `IDMOWrapperFilter'};
  *((_QWORD *)this + 16) = &CMediaWrapperFilter::`vftable'{for `IPersistStream'};
  CMediaWrapperFilter::FreePerStreamStuff(this);
  v2 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 23) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 16LL))(*((_QWORD *)this + 23));
  }
  if ( *((_QWORD *)this + 22) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 22) + 16LL))(*((_QWORD *)this + 22));
  }
  if ( *((_QWORD *)this + 20) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 16LL))(*((_QWORD *)this + 20));
  }
  v3 = *((_QWORD *)this + 21);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 25);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 26);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 16LL))(*((_QWORD *)this + 26));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x180015448  mov     [rsp+arg_0], rbx
0x18001544d  push    rdi
0x18001544e  sub     rsp, 20h
0x180015452  lea     rax, ??_7CMediaWrapperFilter@@6BCUnknown@@@; const CMediaWrapperFilter::`vftable'{for `CUnknown'}
0x180015459  mov     rbx, rcx
0x18001545c  mov     [rcx], rax
0x18001545f  lea     rax, ??_7CMediaWrapperFilter@@6BIBaseFilter@@@; const CMediaWrapperFilter::`vftable'{for `IBaseFilter'}
0x180015466  mov     [rcx+18h], rax
0x18001546a  lea     rax, ??_7CMediaWrapperFilter@@6BIAMovieSetup@@@; const CMediaWrapperFilter::`vftable'{for `IAMovieSetup'}
0x180015471  mov     [rcx+20h], rax
0x180015475  lea     rax, ??_7CMediaWrapperFilter@@6BIDMOWrapperFilter@@@; const CMediaWrapperFilter::`vftable'{for `IDMOWrapperFilter'}
0x18001547c  mov     [rcx+78h], rax
0x180015480  lea     rax, ??_7CMediaWrapperFilter@@6BIPersistStream@@@; const CMediaWrapperFilter::`vftable'{for `IPersistStream'}
0x180015487  mov     [rcx+80h], rax
0x18001548e  call    ?FreePerStreamStuff@CMediaWrapperFilter@@IEAAXXZ; CMediaWrapperFilter::FreePerStreamStuff(void)
0x180015493  cmp     qword ptr [rbx+0B8h], 0
0x18001549b  lea     rdi, [rbx+8]
0x18001549f  jz      short loc_1800154C3
0x1800154a1  mov     rcx, [rdi]
0x1800154a4  mov     rax, [rcx]
0x1800154a7  mov     rax, [rax+8]
0x1800154ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b0  mov     rcx, [rbx+0B8h]
0x1800154b7  mov     rax, [rcx]
0x1800154ba  mov     rax, [rax+10h]
0x1800154be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c3  cmp     qword ptr [rbx+0B0h], 0
0x1800154cb  jz      short loc_1800154EF
0x1800154cd  mov     rcx, [rdi]
0x1800154d0  mov     rax, [rcx]
0x1800154d3  mov     rax, [rax+8]
0x1800154d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154dc  mov     rcx, [rbx+0B0h]
0x1800154e3  mov     rax, [rcx]
0x1800154e6  mov     rax, [rax+10h]
0x1800154ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ef  cmp     qword ptr [rbx+0A0h], 0
0x1800154f7  jz      short loc_18001551B
0x1800154f9  mov     rcx, [rdi]
0x1800154fc  mov     rax, [rcx]
0x1800154ff  mov     rax, [rax+8]
0x180015503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015508  mov     rcx, [rbx+0A0h]
0x18001550f  mov     rax, [rcx]
0x180015512  mov     rax, [rax+10h]
0x180015516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001551b  mov     rcx, [rbx+0A8h]
0x180015522  test    rcx, rcx
0x180015525  jz      short loc_180015533
0x180015527  mov     rax, [rcx]
0x18001552a  mov     rax, [rax+10h]
0x18001552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015533  mov     rcx, [rbx+0C8h]
0x18001553a  test    rcx, rcx
0x18001553d  jz      short loc_18001554B
0x18001553f  mov     rax, [rcx]
0x180015542  mov     rax, [rax+10h]
0x180015546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554b  mov     rcx, [rbx+0D0h]
0x180015552  test    rcx, rcx
0x180015555  jz      short loc_180015576
0x180015557  mov     rax, [rcx]
0x18001555a  mov     rax, [rax+50h]
0x18001555e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015563  mov     rcx, [rbx+0D0h]
0x18001556a  mov     rax, [rcx]
0x18001556d  mov     rax, [rax+10h]
0x180015571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015576  lea     rcx, [rbx+170h]; lpCriticalSection
0x18001557d  call    cs:__imp_DeleteCriticalSection
0x180015583  lea     rcx, [rbx+148h]; lpCriticalSection
0x18001558a  call    cs:__imp_DeleteCriticalSection
0x180015590  lea     rcx, [rbx+108h]; lpCriticalSection
0x180015597  call    cs:__imp_DeleteCriticalSection
0x18001559d  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x1800155a4  call    cs:__imp_DeleteCriticalSection
0x1800155aa  mov     rcx, rbx; this
0x1800155ad  mov     rbx, [rsp+28h+arg_0]
0x1800155b2  add     rsp, 20h
0x1800155b6  pop     rdi
0x1800155b7  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
```
