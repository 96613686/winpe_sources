# SmbQuicCleanupAsyncSendContext

- ea: `0x14008b2f8`
- end: `0x14008b3df`
- name: `SmbQuicCleanupAsyncSendContext`
- size: `231`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14008c298`
- `0x14008c518`

## callees

- `0x1400359f8`
- `0x14008b2f8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008b393`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b393`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3cc`
- `rdbss!RxCeFreeIrp` at `0x14008b3b0`
- `rdbss!RxCeFreeIrp` at `0x14008b3b0`
- `rdbss!RxRemoveHeaderFromMdl` at `0x14008b31e`
- `rdbss!RxRemoveHeaderFromMdl` at `0x14008b31e`
- `rdbss!RxFreeMdl` at `0x14008b343`
- `rdbss!RxFreeMdl` at `0x14008b343`

## pseudocode

```c
void __fastcall SmbQuicCleanupAsyncSendContext(_QWORD *P)
{
  __int64 v1; // rax
  _QWORD *v3; // rcx
  struct _MDL *v4; // rcx
  void *v5; // rcx
  IRP *v6; // rcx

  v1 = P[4];
  if ( !v1 )
    v1 = P[2];
  v3 = (_QWORD *)P[3];
  if ( v3 == (_QWORD *)1 )
  {
    RxRemoveHeaderFromMdl(v1, 4);
  }
  else if ( v3 )
  {
    if ( *v3 != v1 )
      __int2c();
    *v3 = 0;
    RxFreeMdl(P[3]);
  }
  v4 = (struct _MDL *)P[4];
  P[3] = 0;
  if ( v4 )
    RxCeFreeTransformBufferAndMdl(v4, (*((_DWORD *)P + 11) & 0x40000000) != 0 ? 1834184261 : 1834184771);
  v5 = (void *)P[8];
  P[4] = 0;
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x6D537551u);
    P[8] = 0;
  }
  v6 = (IRP *)P[7];
  if ( v6 )
  {
    RxCeFreeIrp(v6);
    P[7] = 0;
  }
  ExFreePoolWithTag(P, 0x6D537551u);
}

```

## disassembly

```asm
0x14008b2f8  push    rbx
0x14008b2fa  sub     rsp, 20h
0x14008b2fe  mov     rax, [rcx+20h]
0x14008b302  mov     rbx, rcx
0x14008b305  test    rax, rax
0x14008b308  jnz     short loc_14008B30E
0x14008b30a  mov     rax, [rcx+10h]
0x14008b30e  mov     rcx, [rcx+18h]
0x14008b312  cmp     rcx, 1
0x14008b316  jnz     short loc_14008B32C
0x14008b318  lea     edx, [rcx+3]
0x14008b31b  mov     rcx, rax
0x14008b31e  call    cs:__imp_RxRemoveHeaderFromMdl
0x14008b325  nop     dword ptr [rax+rax+00h]
0x14008b32a  jmp     short loc_14008B34F
0x14008b32c  test    rcx, rcx
0x14008b32f  jz      short loc_14008B34F
0x14008b331  cmp     [rcx], rax
0x14008b334  jz      short loc_14008B338
0x14008b336  int     2Ch; Windows NT - assertion failure
0x14008b338  mov     qword ptr [rcx], 0
0x14008b33f  mov     rcx, [rbx+18h]
0x14008b343  call    cs:__imp_RxFreeMdl
0x14008b34a  nop     dword ptr [rax+rax+00h]
0x14008b34f  mov     rcx, [rbx+20h]
0x14008b353  mov     qword ptr [rbx+18h], 0
0x14008b35b  test    rcx, rcx
0x14008b35e  jz      short loc_14008B37D
0x14008b360  mov     eax, [rbx+2Ch]
0x14008b363  and     eax, 40000000h
0x14008b368  neg     eax
0x14008b36a  sbb     edx, edx
0x14008b36c  and     edx, 0FFFFFE02h
0x14008b372  add     edx, 6D537043h
0x14008b378  call    RxCeFreeTransformBufferAndMdl
0x14008b37d  mov     rcx, [rbx+40h]; P
0x14008b381  mov     qword ptr [rbx+20h], 0
0x14008b389  test    rcx, rcx
0x14008b38c  jz      short loc_14008B3A7
0x14008b38e  mov     edx, 6D537551h; Tag
0x14008b393  call    cs:__imp_ExFreePoolWithTag
0x14008b39a  nop     dword ptr [rax+rax+00h]
0x14008b39f  mov     qword ptr [rbx+40h], 0
0x14008b3a7  mov     rcx, [rbx+38h]; pIrp
0x14008b3ab  test    rcx, rcx
0x14008b3ae  jz      short loc_14008B3C4
0x14008b3b0  call    cs:__imp_RxCeFreeIrp
0x14008b3b7  nop     dword ptr [rax+rax+00h]
0x14008b3bc  mov     qword ptr [rbx+38h], 0
0x14008b3c4  mov     edx, 6D537551h; Tag
0x14008b3c9  mov     rcx, rbx; P
0x14008b3cc  call    cs:__imp_ExFreePoolWithTag
0x14008b3d3  nop     dword ptr [rax+rax+00h]
0x14008b3d8  add     rsp, 20h
0x14008b3dc  pop     rbx
0x14008b3dd  retn
```
