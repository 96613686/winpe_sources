# COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)

- ea: `0x180007f68`
- end: `0x180007fc2`
- name: `??1COMPRESSION_SCHEME@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(COMPRESSION_SCHEME *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e00`
- `0x180008904`

## callees

- `0x180007f68`
- `0x180009010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fad`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007fa3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007fa3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007fbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007f8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007f8e`

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
0x180007f68  push    rbx
0x180007f6a  sub     rsp, 20h
0x180007f6e  mov     rax, [rcx+0B8h]
0x180007f75  mov     rbx, rcx
0x180007f78  test    rax, rax
0x180007f7b  jz      short loc_180007F82
0x180007f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f82  mov     rcx, [rbx+0A8h]; hLibModule
0x180007f89  test    rcx, rcx
0x180007f8c  jz      short loc_180007F9F
0x180007f8e  call    cs:__imp_FreeLibrary
0x180007f94  mov     qword ptr [rbx+0A8h], 0
0x180007f9f  lea     rcx, [rbx+70h]
0x180007fa3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007fa9  lea     rcx, [rbx+38h]
0x180007fad  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007fb3  mov     rcx, rbx
0x180007fb6  add     rsp, 20h
0x180007fba  pop     rbx
0x180007fbb  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
