# DpContext::~DpContext(void)

- ea: `0x18001eb48`
- end: `0x18001ed1c`
- name: `??1DpContext@@QEAA@XZ`
- size: `468`
- prototype: `void __fastcall(DpContext *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e6fc`
- `0x18001eb1c`
- `0x180105b70`

## callees

- `0x18001eb1c`
- `0x18001eb48`
- `0x18001ed24`
- `0x18001f950`
- `0x180101df8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ebca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ebca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ec56`
- `GDI32!DeleteObject` at `0x18001ecf4`
- `GDI32!DeleteObject` at `0x18001ecf4`

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
  *((_QWORD *)this + 1) = 0;
  v4 = (void *)*((_QWORD *)this + 85);
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
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 103) &= ~4u;
  *((_DWORD *)this + 102) = 1279869254;
  if ( (*((_BYTE *)this + 356) & 4) == 0 )
  {
    v6 = (void *)*((_QWORD *)this + 47);
    if ( v6 )
      HeapFree(GpRuntime::GpMemHeap, 0, v6);
  }
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 89) &= ~4u;
  *((_DWORD *)this + 88) = 1279869254;
  *((_QWORD *)this + 37) = &DpOutputSpan::`vftable';
  if ( (*((_BYTE *)this + 308) & 4) == 0 )
  {
    v7 = (void *)*((_QWORD *)this + 41);
    if ( v7 )
      HeapFree(GpRuntime::GpMemHeap, 0, v7);
  }
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 77) &= ~4u;
  *((_DWORD *)this + 76) = 1279869254;
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
0x18001eb48  mov     [rsp+arg_0], rbx
0x18001eb4d  mov     [rsp+arg_8], rsi
0x18001eb52  push    r14
0x18001eb54  sub     rsp, 20h
0x18001eb58  mov     rbx, rcx
0x18001eb5b  mov     rcx, [rcx+8]; this
0x18001eb5f  test    rcx, rcx
0x18001eb62  jnz     loc_18001ECE5
0x18001eb68  and     qword ptr [rbx+8], 0
0x18001eb6d  mov     rcx, [rbx+2A8h]; ho
0x18001eb74  test    rcx, rcx
0x18001eb77  jnz     loc_18001ECF4
0x18001eb7d  cmp     qword ptr [rbx], 0
0x18001eb81  jz      loc_18001ECB7
0x18001eb87  lea     r14, ??_7GpMatrix@@6B@; const GpMatrix::`vftable'
0x18001eb8e  mov     esi, 4C494146h
0x18001eb93  lea     rcx, [rbx+1C0h]; this
0x18001eb9a  mov     [rbx+2C0h], r14
0x18001eba1  mov     [rbx+2C8h], esi
0x18001eba7  call    ??1GpRegion@@UEAA@XZ; GpRegion::~GpRegion(void)
0x18001ebac  test    byte ptr [rbx+19Ch], 4
0x18001ebb3  jnz     short loc_18001EBD6
0x18001ebb5  mov     r8, [rbx+1B0h]; lpMem
0x18001ebbc  test    r8, r8
0x18001ebbf  jz      short loc_18001EBD6
0x18001ebc1  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18001ebc8  xor     edx, edx; dwFlags
0x18001ebca  call    cs:__imp_HeapFree
0x18001ebd1  nop     dword ptr [rax+rax+00h]
0x18001ebd6  and     qword ptr [rbx+1B0h], 0
0x18001ebde  and     dword ptr [rbx+19Ch], 0FFFFFFFBh
0x18001ebe5  mov     [rbx+198h], esi
0x18001ebeb  test    byte ptr [rbx+164h], 4
0x18001ebf2  jnz     short loc_18001EC15
0x18001ebf4  mov     r8, [rbx+178h]; lpMem
0x18001ebfb  test    r8, r8
0x18001ebfe  jz      short loc_18001EC15
0x18001ec00  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18001ec07  xor     edx, edx; dwFlags
0x18001ec09  call    cs:__imp_HeapFree
0x18001ec10  nop     dword ptr [rax+rax+00h]
0x18001ec15  and     qword ptr [rbx+178h], 0
0x18001ec1d  lea     rax, ??_7DpOutputSpan@@6B@; const DpOutputSpan::`vftable'
0x18001ec24  and     dword ptr [rbx+164h], 0FFFFFFFBh
0x18001ec2b  mov     [rbx+160h], esi
0x18001ec31  mov     [rbx+128h], rax
0x18001ec38  test    byte ptr [rbx+134h], 4
0x18001ec3f  jnz     short loc_18001EC62
0x18001ec41  mov     r8, [rbx+148h]; lpMem
0x18001ec48  test    r8, r8
0x18001ec4b  jz      short loc_18001EC62
0x18001ec4d  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18001ec54  xor     edx, edx; dwFlags
0x18001ec56  call    cs:__imp_HeapFree
0x18001ec5d  nop     dword ptr [rax+rax+00h]
0x18001ec62  and     qword ptr [rbx+148h], 0
0x18001ec6a  and     dword ptr [rbx+134h], 0FFFFFFFBh
0x18001ec71  mov     [rbx+130h], esi
0x18001ec77  mov     [rbx+0F8h], esi
0x18001ec7d  mov     [rbx+0F0h], r14
0x18001ec84  mov     [rbx+0C8h], esi
0x18001ec8a  mov     [rbx+0C0h], r14
0x18001ec91  mov     [rbx+98h], esi
0x18001ec97  mov     [rbx+90h], r14
0x18001ec9e  mov     [rbx+68h], esi
0x18001eca1  mov     rsi, [rsp+28h+arg_8]
0x18001eca6  mov     [rbx+60h], r14
0x18001ecaa  mov     rbx, [rsp+28h+arg_0]
0x18001ecaf  add     rsp, 20h
0x18001ecb3  pop     r14
0x18001ecb5  retn
0x18001ecb7  mov     rcx, [rbx+2A0h]; this
0x18001ecbe  test    rcx, rcx
0x18001ecc1  jnz     short loc_18001ED0D
0x18001ecc3  mov     rcx, [rbx+298h]
0x18001ecca  test    rcx, rcx
0x18001eccd  jz      loc_18001EB87
0x18001ecd3  call    GpFree
0x18001ecd8  and     qword ptr [rbx+298h], 0
0x18001ece0  jmp     loc_18001EB87
0x18001ece5  mov     edx, 1; unsigned int
0x18001ecea  call    ??_GDpContext@@QEAAPEAXI@Z; DpContext::`scalar deleting destructor'(uint)
0x18001ecef  jmp     loc_18001EB68
0x18001ecf4  call    cs:__imp_DeleteObject
0x18001ecfb  nop     dword ptr [rax+rax+00h]
0x18001ed00  and     qword ptr [rbx+2A8h], 0
0x18001ed08  jmp     loc_18001EB7D
0x18001ed0d  call    ??_GEpPaletteMap@@QEAAPEAXI@Z; EpPaletteMap::`scalar deleting destructor'(uint)
0x18001ed12  and     qword ptr [rbx+2A0h], 0
0x18001ed1a  jmp     short loc_18001ECC3
```
