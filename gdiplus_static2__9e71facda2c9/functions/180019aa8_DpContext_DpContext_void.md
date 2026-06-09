# DpContext::~DpContext(void)

- ea: `0x180019aa8`
- end: `0x180019c91`
- name: `??1DpContext@@QEAA@XZ`
- size: `489`
- prototype: `void __fastcall(DpContext *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180019864`
- `0x180019890`
- `0x180046000`

## callees

- `0x180010bd0`
- `0x180019864`
- `0x180019aa8`
- `0x180019c98`
- `0x18011b7d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019bbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019bbf`
- `GDI32!DeleteObject` at `0x180019c63`
- `GDI32!DeleteObject` at `0x180019c63`

## pseudocode

```c
void __fastcall DpContext::~DpContext(DpContext *this, unsigned int a2)
{
  DpContext *v3; // rcx
  void *v4; // rcx
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8
  EpPaletteMap *v8; // rcx
  __int64 v9; // rcx

  v3 = (DpContext *)*((_QWORD *)this + 1);
  if ( v3 )
    DpContext::`scalar deleting destructor'(v3, 1u);
  v4 = (void *)*((_QWORD *)this + 85);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 85) = 0;
  }
  if ( !*(_QWORD *)this )
  {
    v8 = (EpPaletteMap *)*((_QWORD *)this + 84);
    if ( v8 )
    {
      EpPaletteMap::`scalar deleting destructor'(v8, a2);
      *((_QWORD *)this + 84) = 0;
    }
    v9 = *((_QWORD *)this + 83);
    if ( v9 )
    {
      GpFree(v9);
      *((_QWORD *)this + 83) = 0;
    }
  }
  *((_QWORD *)this + 88) = &GpMatrix::`vftable';
  *((_DWORD *)this + 178) = 1279869254;
  GpRegion::~GpRegion((DpContext *)((char *)this + 448));
  if ( (*((_BYTE *)this + 412) & 4) == 0 )
  {
    v5 = (void *)*((_QWORD *)this + 54);
    if ( v5 )
      HeapFree(GpRuntime::GpMemHeap, 0, v5);
  }
  *((_DWORD *)this + 103) &= ~4u;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 102) = 1279869254;
  if ( (*((_BYTE *)this + 356) & 4) == 0 )
  {
    v6 = (void *)*((_QWORD *)this + 47);
    if ( v6 )
      HeapFree(GpRuntime::GpMemHeap, 0, v6);
  }
  *((_DWORD *)this + 89) &= ~4u;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 88) = 1279869254;
  *((_QWORD *)this + 37) = &DpOutputSpan::`vftable';
  if ( (*((_BYTE *)this + 308) & 4) == 0 )
  {
    v7 = (void *)*((_QWORD *)this + 41);
    if ( v7 )
      HeapFree(GpRuntime::GpMemHeap, 0, v7);
  }
  *((_DWORD *)this + 77) &= ~4u;
  *((_DWORD *)this + 76) = 1279869254;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 62) = 1279869254;
  *((_QWORD *)this + 30) = &GpMatrix::`vftable';
  *((_DWORD *)this + 50) = 1279869254;
  *((_QWORD *)this + 24) = &GpMatrix::`vftable';
  *((_DWORD *)this + 38) = 1279869254;
  *((_QWORD *)this + 18) = &GpMatrix::`vftable';
  *((_DWORD *)this + 26) = 1279869254;
  *((_QWORD *)this + 12) = &GpMatrix::`vftable';
}

```

## disassembly

```asm
0x180019aa8  mov     [rsp+arg_0], rbx
0x180019aad  mov     [rsp+arg_8], rsi
0x180019ab2  push    r14
0x180019ab4  sub     rsp, 20h
0x180019ab8  mov     rbx, rcx
0x180019abb  mov     rcx, [rcx+8]; this
0x180019abf  test    rcx, rcx
0x180019ac2  jnz     loc_180019C54
0x180019ac8  mov     rcx, [rbx+2A8h]; ho
0x180019acf  mov     qword ptr [rbx+8], 0
0x180019ad7  test    rcx, rcx
0x180019ada  jnz     loc_180019C63
0x180019ae0  cmp     qword ptr [rbx], 0
0x180019ae4  jz      loc_180019C23
0x180019aea  lea     r14, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x180019af1  mov     esi, 4C494146h
0x180019af6  lea     rcx, [rbx+1C0h]; this
0x180019afd  mov     [rbx+2C0h], r14
0x180019b04  mov     [rbx+2C8h], esi
0x180019b0a  call    ??1GpRegion@@UEAA@XZ; GpRegion::~GpRegion(void)
0x180019b0f  test    byte ptr [rbx+19Ch], 4
0x180019b16  jnz     short loc_180019B39
0x180019b18  mov     r8, [rbx+1B0h]; lpMem
0x180019b1f  test    r8, r8
0x180019b22  jz      short loc_180019B39
0x180019b24  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180019b2b  xor     edx, edx; dwFlags
0x180019b2d  call    cs:__imp_HeapFree
0x180019b34  nop     dword ptr [rax+rax+00h]
0x180019b39  and     dword ptr [rbx+19Ch], 0FFFFFFFBh
0x180019b40  mov     qword ptr [rbx+1B0h], 0
0x180019b4b  mov     [rbx+198h], esi
0x180019b51  test    byte ptr [rbx+164h], 4
0x180019b58  jnz     short loc_180019B7B
0x180019b5a  mov     r8, [rbx+178h]; lpMem
0x180019b61  test    r8, r8
0x180019b64  jz      short loc_180019B7B
0x180019b66  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180019b6d  xor     edx, edx; dwFlags
0x180019b6f  call    cs:__imp_HeapFree
0x180019b76  nop     dword ptr [rax+rax+00h]
0x180019b7b  and     dword ptr [rbx+164h], 0FFFFFFFBh
0x180019b82  lea     rax, ??_7DpOutputSpan@@6B@; const DpOutputSpan::`vftable'
0x180019b89  mov     qword ptr [rbx+178h], 0
0x180019b94  mov     [rbx+160h], esi
0x180019b9a  mov     [rbx+128h], rax
0x180019ba1  test    byte ptr [rbx+134h], 4
0x180019ba8  jnz     short loc_180019BCB
0x180019baa  mov     r8, [rbx+148h]; lpMem
0x180019bb1  test    r8, r8
0x180019bb4  jz      short loc_180019BCB
0x180019bb6  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180019bbd  xor     edx, edx; dwFlags
0x180019bbf  call    cs:__imp_HeapFree
0x180019bc6  nop     dword ptr [rax+rax+00h]
0x180019bcb  and     dword ptr [rbx+134h], 0FFFFFFFBh
0x180019bd2  mov     [rbx+130h], esi
0x180019bd8  mov     qword ptr [rbx+148h], 0
0x180019be3  mov     [rbx+0F8h], esi
0x180019be9  mov     [rbx+0F0h], r14
0x180019bf0  mov     [rbx+0C8h], esi
0x180019bf6  mov     [rbx+0C0h], r14
0x180019bfd  mov     [rbx+98h], esi
0x180019c03  mov     [rbx+90h], r14
0x180019c0a  mov     [rbx+68h], esi
0x180019c0d  mov     rsi, [rsp+28h+arg_8]
0x180019c12  mov     [rbx+60h], r14
0x180019c16  mov     rbx, [rsp+28h+arg_0]
0x180019c1b  add     rsp, 20h
0x180019c1f  pop     r14
0x180019c21  retn
0x180019c23  mov     rcx, [rbx+2A0h]; this
0x180019c2a  test    rcx, rcx
0x180019c2d  jnz     short loc_180019C7F
0x180019c2f  mov     rcx, [rbx+298h]
0x180019c36  test    rcx, rcx
0x180019c39  jz      loc_180019AEA
0x180019c3f  call    GpFree
0x180019c44  mov     qword ptr [rbx+298h], 0
0x180019c4f  jmp     loc_180019AEA
0x180019c54  mov     edx, 1; unsigned int
0x180019c59  call    ??_GDpContext@@QEAAPEAXI@Z; DpContext::`scalar deleting destructor'(uint)
0x180019c5e  jmp     loc_180019AC8
0x180019c63  call    cs:__imp_DeleteObject
0x180019c6a  nop     dword ptr [rax+rax+00h]
0x180019c6f  mov     qword ptr [rbx+2A8h], 0
0x180019c7a  jmp     loc_180019AE0
0x180019c7f  call    ??_GEpPaletteMap@@QEAAPEAXI@Z; EpPaletteMap::`scalar deleting destructor'(uint)
0x180019c84  mov     qword ptr [rbx+2A0h], 0
0x180019c8f  jmp     short loc_180019C2F
```
