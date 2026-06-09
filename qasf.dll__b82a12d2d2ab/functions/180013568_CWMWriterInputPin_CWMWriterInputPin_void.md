# CWMWriterInputPin::~CWMWriterInputPin(void)

- ea: `0x180013568`
- end: `0x1800136ad`
- name: `??1CWMWriterInputPin@@UEAA@XZ`
- size: `325`
- prototype: `void __fastcall(CWMWriterInputPin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800136c0`

## callees

- `0x1800036bc`
- `0x180013568`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180013697`
- `KERNEL32!DeleteCriticalSection` at `0x180013697`
- `KERNEL32!CloseHandle` at `0x18001367f`
- `KERNEL32!CloseHandle` at `0x18001367f`
- `ole32!CoTaskMemFree` at `0x18001362c`
- `ole32!CoTaskMemFree` at `0x18001362c`

## pseudocode

```c
void __fastcall CWMWriterInputPin::~CWMWriterInputPin(CWMWriterInputPin *this)
{
  bool v1; // zf
  _DWORD *v2; // rdi
  int i; // esi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx

  v1 = *((_QWORD *)this + 55) == 0;
  *(_QWORD *)this = &CWMWriterInputPin::`vftable'{for `CUnknown'};
  v2 = (_DWORD *)((char *)this + 432);
  *((_QWORD *)this + 3) = &CWMWriterInputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CWMWriterInputPin::`vftable'{for `IQualityControl'};
  *((_QWORD *)this + 27) = &CWMWriterInputPin::`vftable'{for `CBaseInputPin'};
  *((_QWORD *)this + 38) = &CWMWriterInputPin::`vftable'{for `IAMStreamConfig'};
  *((_QWORD *)this + 39) = &CWMWriterInputPin::`vftable'{for `IAMWMBufferPass'};
  *((_QWORD *)this + 40) = &CWMWriterInputPin::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 41) = &CWMWriterInputPin::`vftable'{for `IPinConnection'};
  if ( !v1 )
  {
    for ( i = 0; i < *v2; ++i )
    {
      v5 = *(_QWORD *)(*((_QWORD *)this + 55) + 8LL * i);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *(_QWORD *)(*((_QWORD *)this + 55) + 8LL * i) = 0;
      }
    }
    CoTaskMemFree(*((LPVOID *)this + 55));
  }
  v6 = *((_QWORD *)this + 65);
  *v2 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 56);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 56) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 42);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 42) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  CBaseInputPin::~CBaseInputPin(this);
}

```

## disassembly

```asm
0x180013568  push    rbx
0x18001356a  push    rbp
0x18001356b  push    rsi
0x18001356c  push    rdi
0x18001356d  sub     rsp, 28h
0x180013571  cmp     qword ptr [rcx+1B8h], 0
0x180013579  lea     rax, ??_7CWMWriterInputPin@@6BCUnknown@@@; const CWMWriterInputPin::`vftable'{for `CUnknown'}
0x180013580  mov     [rcx], rax
0x180013583  lea     rdi, [rcx+1B0h]
0x18001358a  lea     rax, ??_7CWMWriterInputPin@@6BIPin@@@; const CWMWriterInputPin::`vftable'{for `IPin'}
0x180013591  mov     rbx, rcx
0x180013594  mov     [rcx+18h], rax
0x180013598  lea     rax, ??_7CWMWriterInputPin@@6BIQualityControl@@@; const CWMWriterInputPin::`vftable'{for `IQualityControl'}
0x18001359f  mov     [rcx+20h], rax
0x1800135a3  lea     rax, ??_7CWMWriterInputPin@@6BCBaseInputPin@@@; const CWMWriterInputPin::`vftable'{for `CBaseInputPin'}
0x1800135aa  mov     [rcx+0D8h], rax
0x1800135b1  lea     rax, ??_7CWMWriterInputPin@@6BIAMStreamConfig@@@; const CWMWriterInputPin::`vftable'{for `IAMStreamConfig'}
0x1800135b8  mov     [rcx+130h], rax
0x1800135bf  lea     rax, ??_7CWMWriterInputPin@@6BIAMWMBufferPass@@@; const CWMWriterInputPin::`vftable'{for `IAMWMBufferPass'}
0x1800135c6  mov     [rcx+138h], rax
0x1800135cd  lea     rax, ??_7CWMWriterInputPin@@6BIReferenceClock@@@; const CWMWriterInputPin::`vftable'{for `IReferenceClock'}
0x1800135d4  mov     [rcx+140h], rax
0x1800135db  lea     rax, ??_7CWMWriterInputPin@@6BIPinConnection@@@; const CWMWriterInputPin::`vftable'{for `IPinConnection'}
0x1800135e2  mov     [rcx+148h], rax
0x1800135e9  jz      short loc_180013632
0x1800135eb  xor     esi, esi
0x1800135ed  cmp     [rdi], esi
0x1800135ef  jle     short loc_180013625
0x1800135f1  mov     rax, [rbx+1B8h]
0x1800135f8  movsxd  rbp, esi
0x1800135fb  mov     rcx, [rax+rbp*8]
0x1800135ff  test    rcx, rcx
0x180013602  jz      short loc_18001361F
0x180013604  mov     rax, [rcx]
0x180013607  mov     rax, [rax+10h]
0x18001360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013610  mov     rax, [rbx+1B8h]
0x180013617  mov     qword ptr [rax+rbp*8], 0
0x18001361f  inc     esi
0x180013621  cmp     esi, [rdi]
0x180013623  jl      short loc_1800135F1
0x180013625  mov     rcx, [rbx+1B8h]; pv
0x18001362c  call    cs:__imp_CoTaskMemFree
0x180013632  mov     rcx, [rbx+208h]
0x180013639  mov     dword ptr [rdi], 0
0x18001363f  test    rcx, rcx
0x180013642  jz      short loc_180013650
0x180013644  mov     rax, [rcx]
0x180013647  mov     rax, [rax+10h]
0x18001364b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013650  mov     rcx, [rbx+1C0h]
0x180013657  test    rcx, rcx
0x18001365a  jz      short loc_180013673
0x18001365c  mov     rax, [rcx]
0x18001365f  mov     rax, [rax+10h]
0x180013663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013668  mov     qword ptr [rbx+1C0h], 0
0x180013673  mov     rcx, [rbx+150h]; hObject
0x18001367a  test    rcx, rcx
0x18001367d  jz      short loc_180013690
0x18001367f  call    cs:__imp_CloseHandle
0x180013685  mov     qword ptr [rbx+150h], 0
0x180013690  lea     rcx, [rbx+160h]; lpCriticalSection
0x180013697  call    cs:__imp_DeleteCriticalSection
0x18001369d  mov     rcx, rbx; this
0x1800136a0  add     rsp, 28h
0x1800136a4  pop     rdi
0x1800136a5  pop     rsi
0x1800136a6  pop     rbp
0x1800136a7  pop     rbx
0x1800136a8  jmp     ??1CBaseInputPin@@UEAA@XZ; CBaseInputPin::~CBaseInputPin(void)
```
