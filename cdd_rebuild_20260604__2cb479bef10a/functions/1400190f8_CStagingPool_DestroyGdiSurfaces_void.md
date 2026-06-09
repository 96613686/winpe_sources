# CStagingPool::DestroyGdiSurfaces(void)

- ea: `0x1400190f8`
- end: `0x1400191ca`
- name: `?DestroyGdiSurfaces@CStagingPool@@QEAAXXZ`
- size: `210`
- prototype: `void __fastcall(CStagingPool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140028a40`

## callees

- `0x1400190f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019181`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400191b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019181`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400191b4`
- `WIN32K!EngDeleteSurface` at `0x140019140`
- `WIN32K!EngDeleteSurface` at `0x140019140`
- `WIN32K!EngUnlockSurface` at `0x14001911b`
- `WIN32K!EngUnlockSurface` at `0x14001911b`

## pseudocode

```c
void __fastcall CStagingPool::DestroyGdiSurfaces(CStagingPool *this)
{
  __int64 v1; // rsi
  __int64 v3; // rdi
  SURFOBJ *v4; // rcx
  HSURF v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v1 = 0;
  v3 = 0;
  do
  {
    v4 = *(SURFOBJ **)((char *)this + v3 + 168);
    if ( v4 )
    {
      EngUnlockSurface(v4);
      *(_QWORD *)((char *)this + v3 + 168) = 0;
    }
    v5 = *(HSURF *)((char *)this + v3 + 176);
    if ( v5 )
    {
      EngDeleteSurface(v5);
      *(_QWORD *)((char *)this + v3 + 176) = 0;
    }
    ++v1;
    v3 += 40;
  }
  while ( v1 != 16 );
  *((_QWORD *)this + 100) = (char *)this + 792;
  *((_QWORD *)this + 99) = (char *)this + 792;
  v6 = (void *)*((_QWORD *)this + 101);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)this + 101) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    *((_QWORD *)this + 7) = 0;
  }
}

```

## disassembly

```asm
0x1400190f8  mov     [rsp+arg_0], rbx
0x1400190fd  mov     [rsp+arg_8], rsi
0x140019102  push    rdi
0x140019103  sub     rsp, 20h
0x140019107  xor     esi, esi
0x140019109  mov     rbx, rcx
0x14001910c  xor     edi, edi
0x14001910e  mov     rcx, [rbx+rdi+0A8h]; pso
0x140019116  test    rcx, rcx
0x140019119  jz      short loc_140019133
0x14001911b  call    cs:__imp_EngUnlockSurface
0x140019122  nop     dword ptr [rax+rax+00h]
0x140019127  mov     qword ptr [rbx+rdi+0A8h], 0
0x140019133  mov     rcx, [rbx+rdi+0B0h]; hsurf
0x14001913b  test    rcx, rcx
0x14001913e  jz      short loc_140019158
0x140019140  call    cs:__imp_EngDeleteSurface
0x140019147  nop     dword ptr [rax+rax+00h]
0x14001914c  mov     qword ptr [rbx+rdi+0B0h], 0
0x140019158  inc     rsi
0x14001915b  add     rdi, 28h ; '('
0x14001915f  cmp     rsi, 10h
0x140019163  jnz     short loc_14001910E
0x140019165  lea     rax, [rbx+318h]
0x14001916c  mov     [rax+8], rax
0x140019170  mov     [rax], rax
0x140019173  mov     rcx, [rbx+328h]; P
0x14001917a  test    rcx, rcx
0x14001917d  jz      short loc_140019198
0x14001917f  xor     edx, edx; Tag
0x140019181  call    cs:__imp_ExFreePoolWithTag
0x140019188  nop     dword ptr [rax+rax+00h]
0x14001918d  mov     qword ptr [rbx+328h], 0
0x140019198  mov     rcx, [rbx+38h]; P
0x14001919c  test    rcx, rcx
0x14001919f  jnz     short loc_1400191B2
0x1400191a1  mov     rbx, [rsp+28h+arg_0]
0x1400191a6  mov     rsi, [rsp+28h+arg_8]
0x1400191ab  add     rsp, 20h
0x1400191af  pop     rdi
0x1400191b0  retn
0x1400191b2  xor     edx, edx; Tag
0x1400191b4  call    cs:__imp_ExFreePoolWithTag
0x1400191bb  nop     dword ptr [rax+rax+00h]
0x1400191c0  mov     qword ptr [rbx+38h], 0
0x1400191c8  jmp     short loc_1400191A1
```
