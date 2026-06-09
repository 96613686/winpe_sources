# CDescriptor::~CDescriptor(void)

- ea: `0x18000a10c`
- end: `0x18000a170`
- name: `??1CDescriptor@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CDescriptor *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800080f0`
- `0x18000828c`
- `0x180008450`
- `0x1800085b0`
- `0x180008710`
- `0x180008bc0`
- `0x180008e90`
- `0x1800099e0`
- `0x180009b20`
- `0x180009d30`
- `0x18000a0e4`
- `0x18000a178`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000bbc4`

## callees

- `0x1800019a0`
- `0x18000a10c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a164`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a164`

## pseudocode

```c
void __fastcall CDescriptor::~CDescriptor(CDescriptor *this, unsigned __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx

  if ( *((_DWORD *)this + 42) )
  {
    v3 = (void *)*((_QWORD *)this + 10);
    if ( v3 )
      operator delete(v3, a2);
    v4 = (void *)*((_QWORD *)this + 9);
    if ( v4 )
      operator delete(v4, a2);
    v5 = (void *)*((_QWORD *)this + 8);
    if ( v5 )
      operator delete(v5, a2);
    v6 = *((_QWORD *)this + 13);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  }
}

```

## disassembly

```asm
0x18000a10c  push    rbx
0x18000a10e  sub     rsp, 20h
0x18000a112  cmp     dword ptr [rcx+0A8h], 0
0x18000a119  mov     rbx, rcx
0x18000a11c  jz      short loc_18000A16A
0x18000a11e  mov     rcx, [rcx+50h]; void *
0x18000a122  test    rcx, rcx
0x18000a125  jz      short loc_18000A12C
0x18000a127  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a12c  mov     rcx, [rbx+48h]; void *
0x18000a130  test    rcx, rcx
0x18000a133  jz      short loc_18000A13A
0x18000a135  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a13a  mov     rcx, [rbx+40h]; void *
0x18000a13e  test    rcx, rcx
0x18000a141  jz      short loc_18000A148
0x18000a143  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a148  mov     rcx, [rbx+68h]
0x18000a14c  test    rcx, rcx
0x18000a14f  jz      short loc_18000A15D
0x18000a151  mov     rax, [rcx]
0x18000a154  mov     rax, [rax+10h]
0x18000a158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a15d  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000a164  call    cs:__imp_DeleteCriticalSection
0x18000a16a  add     rsp, 20h
0x18000a16e  pop     rbx
0x18000a16f  retn
```
