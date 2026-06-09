# CEmfPlusEnumState::~CEmfPlusEnumState(void)

- ea: `0x1800d1a6c`
- end: `0x1800d1bb3`
- name: `??1CEmfPlusEnumState@@UEAA@XZ`
- size: `327`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800d1a30`

## callees

- `0x18001f950`
- `0x18004bb6c`
- `0x180060564`
- `0x1800c3638`
- `0x1800d1a6c`
- `0x1800d1bc0`
- `0x1800d1bd0`
- `0x1800e5100`
- `0x1800e9774`
- `0x180118268`
- `0x180175010`

## import_xrefs

- `GDI32!RestoreDC` at `0x1800d1aa8`
- `GDI32!RestoreDC` at `0x1800d1aa8`
- `GDI32!DeleteObject` at `0x1800d1b23`
- `GDI32!DeleteObject` at `0x1800d1b23`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::~CEmfPlusEnumState(CEmfPlusEnumState *this)
{
  int v2; // edx
  unsigned int v3; // edx
  CSmartGpObject *v4; // rsi
  char *v5; // rcx
  char *v6; // rbx
  GraphicsStateInfo *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  __int64 v10; // rbx

  *(_QWORD *)this = &CEmfPlusEnumState::`vftable';
  GpFree(*((_QWORD *)this + 30));
  if ( (*((_BYTE *)this + 8) & 4) != 0 )
    v2 = *((_DWORD *)this + 7) - 1;
  else
    v2 = *((_DWORD *)this + 6);
  RestoreDC(*((HDC *)this + 2), v2);
  v4 = (CEmfPlusEnumState *)((char *)this + 2696);
  v5 = (char *)*((_QWORD *)this + 337);
  if ( v5 )
  {
    v6 = v5 - 8;
    `vector destructor iterator'(v5, 8u, *((_QWORD *)v5 - 1), (void (*)(void *))CSmartGpObject::~CSmartGpObject);
    operator delete(v6, 8LL * *(_QWORD *)v6 + 8);
  }
  v7 = (GraphicsStateInfo *)*((_QWORD *)this + 397);
  if ( v7 )
    GraphicsStateInfo::`vector deleting destructor'(v7, v3);
  v8 = *((_QWORD *)this + 527);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 56LL))(v8);
  v9 = (void *)*((_QWORD *)this + 536);
  if ( v9 )
    DeleteObject(v9);
  CSmartGpObject::Release((CEmfPlusEnumState *)((char *)this + 4280));
  CSmartGpObject::Release((CEmfPlusEnumState *)((char *)this + 4272));
  GpPath::~GpPath((CEmfPlusEnumState *)((char *)this + 2808));
  *((_QWORD *)this + 344) = &GpMatrix::`vftable';
  v10 = 20;
  *((_DWORD *)this + 690) = 1279869254;
  *((_QWORD *)this + 338) = &GpMatrix::`vftable';
  *((_DWORD *)this + 678) = 1279869254;
  do
  {
    v4 = (CSmartGpObject *)((char *)v4 - 8);
    CSmartGpObject::~CSmartGpObject(v4);
    --v10;
  }
  while ( v10 );
  GraphicsStateInfo::~GraphicsStateInfo((CEmfPlusEnumState *)((char *)this + 2400));
  MfEnumState::~MfEnumState((HDC *)this);
}

```

## disassembly

```asm
0x1800d1a6c  mov     [rsp+arg_0], rbx
0x1800d1a71  mov     [rsp+arg_8], rsi
0x1800d1a76  push    rdi
0x1800d1a77  sub     rsp, 20h
0x1800d1a7b  lea     rax, ??_7CEmfPlusEnumState@@6B@; const CEmfPlusEnumState::`vftable'
0x1800d1a82  mov     rdi, rcx
0x1800d1a85  mov     [rcx], rax
0x1800d1a88  mov     rcx, [rcx+0F0h]
0x1800d1a8f  call    GpFree
0x1800d1a94  test    byte ptr [rdi+8], 4
0x1800d1a98  mov     rcx, [rdi+10h]; hdc
0x1800d1a9c  jz      short loc_1800D1AA5
0x1800d1a9e  mov     edx, [rdi+1Ch]
0x1800d1aa1  dec     edx
0x1800d1aa3  jmp     short loc_1800D1AA8
0x1800d1aa5  mov     edx, [rdi+18h]; nSavedDC
0x1800d1aa8  call    cs:__imp_RestoreDC
0x1800d1aaf  nop     dword ptr [rax+rax+00h]
0x1800d1ab4  lea     rsi, [rdi+0A88h]
0x1800d1abb  mov     rcx, [rsi]; void *
0x1800d1abe  test    rcx, rcx
0x1800d1ac1  jz      short loc_1800D1AEE
0x1800d1ac3  lea     rbx, [rcx-8]
0x1800d1ac7  mov     edx, 8; unsigned __int64
0x1800d1acc  mov     r8, [rbx]; unsigned __int64
0x1800d1acf  lea     r9, ??1CSmartGpObject@@QEAA@XZ; void (*)(void *)
0x1800d1ad6  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800d1adb  mov     rdx, [rbx]
0x1800d1ade  mov     rcx, rbx; void *
0x1800d1ae1  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x1800d1ae9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d1aee  mov     rcx, [rdi+0C68h]; this
0x1800d1af5  test    rcx, rcx
0x1800d1af8  jz      short loc_1800D1AFF
0x1800d1afa  call    ??_EGraphicsStateInfo@@QEAAPEAXI@Z; GraphicsStateInfo::`vector deleting destructor'(uint)
0x1800d1aff  mov     rcx, [rdi+1078h]
0x1800d1b06  test    rcx, rcx
0x1800d1b09  jz      short loc_1800D1B17
0x1800d1b0b  mov     rax, [rcx]
0x1800d1b0e  mov     rax, [rax+38h]
0x1800d1b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1b17  mov     rcx, [rdi+10C0h]; ho
0x1800d1b1e  test    rcx, rcx
0x1800d1b21  jz      short loc_1800D1B2F
0x1800d1b23  call    cs:__imp_DeleteObject
0x1800d1b2a  nop     dword ptr [rax+rax+00h]
0x1800d1b2f  lea     rcx, [rdi+10B8h]; this
0x1800d1b36  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x1800d1b3b  lea     rcx, [rdi+10B0h]; this
0x1800d1b42  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x1800d1b47  lea     rcx, [rdi+0AF8h]; this
0x1800d1b4e  call    ??1GpPath@@UEAA@XZ; GpPath::~GpPath(void)
0x1800d1b53  lea     rcx, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x1800d1b5a  mov     eax, 4C494146h
0x1800d1b5f  mov     [rdi+0AC0h], rcx
0x1800d1b66  mov     ebx, 14h
0x1800d1b6b  mov     [rdi+0AC8h], eax
0x1800d1b71  mov     [rdi+0A90h], rcx
0x1800d1b78  mov     [rdi+0A98h], eax
0x1800d1b7e  sub     rsi, 8
0x1800d1b82  mov     rcx, rsi; this
0x1800d1b85  call    ??1CSmartGpObject@@QEAA@XZ; CSmartGpObject::~CSmartGpObject(void)
0x1800d1b8a  sub     rbx, 1
0x1800d1b8e  jnz     short loc_1800D1B7E
0x1800d1b90  lea     rcx, [rdi+960h]; this
0x1800d1b97  call    ??1GraphicsStateInfo@@QEAA@XZ; GraphicsStateInfo::~GraphicsStateInfo(void)
0x1800d1b9c  mov     rcx, rdi; this
0x1800d1b9f  mov     rbx, [rsp+28h+arg_0]
0x1800d1ba4  mov     rsi, [rsp+28h+arg_8]
0x1800d1ba9  add     rsp, 20h
0x1800d1bad  pop     rdi
0x1800d1bae  jmp     ??1MfEnumState@@UEAA@XZ; MfEnumState::~MfEnumState(void)
```
