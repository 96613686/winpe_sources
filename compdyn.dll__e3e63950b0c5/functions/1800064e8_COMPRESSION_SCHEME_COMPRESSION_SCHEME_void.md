# COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)

- ea: `0x1800064e8`
- end: `0x180006542`
- name: `??1COMPRESSION_SCHEME@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(COMPRESSION_SCHEME *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x180006e14`

## callees

- `0x1800064e8`
- `0x180008010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000652d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000652d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006523`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006523`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000653b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000650e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000650e`

## pseudocode

```c
void __fastcall COMPRESSION_SCHEME::~COMPRESSION_SCHEME(COMPRESSION_SCHEME *this)
{
  void (*v1)(void); // rax
  HMODULE v3; // rcx

  v1 = (void (*)(void))*((_QWORD *)this + 23);
  if ( v1 )
    v1();
  v3 = (HMODULE)*((_QWORD *)this + 21);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 21) = 0;
  }
  STRU::~STRU((COMPRESSION_SCHEME *)((char *)this + 112));
  STRA::~STRA((COMPRESSION_SCHEME *)((char *)this + 56));
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x1800064e8  push    rbx
0x1800064ea  sub     rsp, 20h
0x1800064ee  mov     rax, [rcx+0B8h]
0x1800064f5  mov     rbx, rcx
0x1800064f8  test    rax, rax
0x1800064fb  jz      short loc_180006502
0x1800064fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006502  mov     rcx, [rbx+0A8h]; hLibModule
0x180006509  test    rcx, rcx
0x18000650c  jz      short loc_18000651F
0x18000650e  call    cs:__imp_FreeLibrary
0x180006514  mov     qword ptr [rbx+0A8h], 0
0x18000651f  lea     rcx, [rbx+70h]
0x180006523  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006529  lea     rcx, [rbx+38h]
0x18000652d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006533  mov     rcx, rbx
0x180006536  add     rsp, 20h
0x18000653a  pop     rbx
0x18000653b  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
