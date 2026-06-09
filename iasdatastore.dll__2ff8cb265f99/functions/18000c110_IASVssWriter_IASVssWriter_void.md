# IASVssWriter::~IASVssWriter(void)

- ea: `0x18000c110`
- end: `0x18000c193`
- name: `??1IASVssWriter@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(IASVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c220`

## callees

- `0x18000c110`
- `0x18000c2b0`
- `0x180010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c141`
- `KERNEL32!DeleteCriticalSection` at `0x18000c141`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IASVssWriter::~IASVssWriter(IASVssWriter *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // rcx

  *(_QWORD *)this = &IASVssWriter::`vftable'{for `CVssWriter'};
  v2 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 2) = &IASVssWriter::`vftable'{for `IIASVssWriter'};
  IASVssWriter::DisableVssWriter((IASVssWriter *)((char *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *v2 = &IIASVssWriter::`vftable';
  *(_QWORD *)this = &CVssWriter::`vftable';
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000c110  mov     [rsp+arg_0], rbx
0x18000c115  push    rdi
0x18000c116  sub     rsp, 20h
0x18000c11a  mov     rdi, rcx
0x18000c11d  lea     rax, ??_7IASVssWriter@@6BCVssWriter@@@; const IASVssWriter::`vftable'{for `CVssWriter'}
0x18000c124  mov     [rcx], rax
0x18000c127  lea     rbx, [rcx+10h]
0x18000c12b  lea     rax, ??_7IASVssWriter@@6BIIASVssWriter@@@; const IASVssWriter::`vftable'{for `IIASVssWriter'}
0x18000c132  mov     [rbx], rax
0x18000c135  mov     rcx, rbx; this
0x18000c138  call    ?DisableVssWriter@IASVssWriter@@UEAAJXZ; IASVssWriter::DisableVssWriter(void)
0x18000c13d  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000c141  call    cs:__imp_DeleteCriticalSection
0x18000c147  lea     rax, ??_7IIASVssWriter@@6B@; const IIASVssWriter::`vftable'
0x18000c14e  mov     [rbx], rax
0x18000c151  lea     rax, ??_7CVssWriter@@6B@; const CVssWriter::`vftable'
0x18000c158  mov     [rdi], rax
0x18000c15b  mov     rcx, [rdi+8]
0x18000c15f  test    rcx, rcx
0x18000c162  jz      short loc_18000C188
0x18000c164  mov     rax, [rcx]
0x18000c167  mov     rax, [rax+30h]
0x18000c16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c170  mov     rcx, [rdi+8]
0x18000c174  mov     rax, [rcx]
0x18000c177  mov     rax, [rax+10h]
0x18000c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c180  mov     qword ptr [rdi+8], 0
0x18000c188  mov     rbx, [rsp+28h+arg_0]
0x18000c18d  add     rsp, 20h
0x18000c191  pop     rdi
0x18000c192  retn
```
