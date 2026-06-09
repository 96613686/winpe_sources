# SmbQuicCleanupAsyncSendContext

- ea: `0x14008b348`
- end: `0x14008b42f`
- name: `SmbQuicCleanupAsyncSendContext`
- size: `231`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14008c2e8`
- `0x14008c568`

## callees

- `0x1400359f8`
- `0x14008b348`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b41c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b3e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b41c`
- `rdbss!RxCeFreeIrp` at `0x14008b400`
- `rdbss!RxCeFreeIrp` at `0x14008b400`
- `rdbss!RxRemoveHeaderFromMdl` at `0x14008b36e`
- `rdbss!RxRemoveHeaderFromMdl` at `0x14008b36e`
- `rdbss!RxFreeMdl` at `0x14008b393`
- `rdbss!RxFreeMdl` at `0x14008b393`

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
0x14008b348  push    rbx
0x14008b34a  sub     rsp, 20h
0x14008b34e  mov     rax, [rcx+20h]
0x14008b352  mov     rbx, rcx
0x14008b355  test    rax, rax
0x14008b358  jnz     short loc_14008B35E
0x14008b35a  mov     rax, [rcx+10h]
0x14008b35e  mov     rcx, [rcx+18h]
0x14008b362  cmp     rcx, 1
0x14008b366  jnz     short loc_14008B37C
0x14008b368  lea     edx, [rcx+3]
0x14008b36b  mov     rcx, rax
0x14008b36e  call    cs:__imp_RxRemoveHeaderFromMdl
0x14008b375  nop     dword ptr [rax+rax+00h]
0x14008b37a  jmp     short loc_14008B39F
0x14008b37c  test    rcx, rcx
0x14008b37f  jz      short loc_14008B39F
0x14008b381  cmp     [rcx], rax
0x14008b384  jz      short loc_14008B388
0x14008b386  int     2Ch; Windows NT - assertion failure
0x14008b388  mov     qword ptr [rcx], 0
0x14008b38f  mov     rcx, [rbx+18h]
0x14008b393  call    cs:__imp_RxFreeMdl
0x14008b39a  nop     dword ptr [rax+rax+00h]
0x14008b39f  mov     rcx, [rbx+20h]
0x14008b3a3  mov     qword ptr [rbx+18h], 0
0x14008b3ab  test    rcx, rcx
0x14008b3ae  jz      short loc_14008B3CD
0x14008b3b0  mov     eax, [rbx+2Ch]
0x14008b3b3  and     eax, 40000000h
0x14008b3b8  neg     eax
0x14008b3ba  sbb     edx, edx
0x14008b3bc  and     edx, 0FFFFFE02h
0x14008b3c2  add     edx, 6D537043h
0x14008b3c8  call    RxCeFreeTransformBufferAndMdl
0x14008b3cd  mov     rcx, [rbx+40h]; P
0x14008b3d1  mov     qword ptr [rbx+20h], 0
0x14008b3d9  test    rcx, rcx
0x14008b3dc  jz      short loc_14008B3F7
0x14008b3de  mov     edx, 6D537551h; Tag
0x14008b3e3  call    cs:__imp_ExFreePoolWithTag
0x14008b3ea  nop     dword ptr [rax+rax+00h]
0x14008b3ef  mov     qword ptr [rbx+40h], 0
0x14008b3f7  mov     rcx, [rbx+38h]; pIrp
0x14008b3fb  test    rcx, rcx
0x14008b3fe  jz      short loc_14008B414
0x14008b400  call    cs:__imp_RxCeFreeIrp
0x14008b407  nop     dword ptr [rax+rax+00h]
0x14008b40c  mov     qword ptr [rbx+38h], 0
0x14008b414  mov     edx, 6D537551h; Tag
0x14008b419  mov     rcx, rbx; P
0x14008b41c  call    cs:__imp_ExFreePoolWithTag
0x14008b423  nop     dword ptr [rax+rax+00h]
0x14008b428  add     rsp, 20h
0x14008b42c  pop     rbx
0x14008b42d  retn
```
