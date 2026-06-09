# TpProviderCleanup

- ea: `0x140003c44`
- end: `0x140003d10`
- name: `TpProviderCleanup`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002794`
- `0x14000e3d8`

## callees

- `0x14000110c`
- `0x140003c44`
- `0x140005374`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003cc5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cc5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c94`

## pseudocode

```c
void __fastcall TpProviderCleanup(__int64 a1)
{
  KIRQL v2; // al
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x30u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  if ( a1 )
  {
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    v3 = *(void **)(a1 + 96);
    *(_BYTE *)(a1 + 16) = v2;
    if ( v3 )
      FreeHandleTable(v3);
    *(_OWORD *)(a1 + 80) = 0;
    *(_QWORD *)(a1 + 96) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x31u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
}

```

## disassembly

```asm
0x140003c44  mov     [rsp+arg_0], rbx
0x140003c49  mov     [rsp+arg_8], rsi
0x140003c4e  push    rdi
0x140003c4f  sub     rsp, 20h
0x140003c53  mov     rbx, rcx
0x140003c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c5d  lea     rsi, WPP_GLOBAL_Control
0x140003c64  cmp     rcx, rsi
0x140003c67  jz      short loc_140003C8B
0x140003c69  mov     eax, [rcx+2Ch]
0x140003c6c  test    al, 2
0x140003c6e  jz      short loc_140003C8B
0x140003c70  cmp     byte ptr [rcx+29h], 3
0x140003c74  jb      short loc_140003C8B
0x140003c76  mov     rcx, [rcx+18h]
0x140003c7a  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140003c81  mov     edx, 30h ; '0'
0x140003c86  call    WPP_SF_
0x140003c8b  test    rbx, rbx
0x140003c8e  jz      short loc_140003CD1
0x140003c90  lea     rcx, [rbx+8]; SpinLock
0x140003c94  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003c9b  nop     dword ptr [rax+rax+00h]
0x140003ca0  mov     rcx, [rbx+60h]; VirtualAddress
0x140003ca4  mov     [rbx+10h], al
0x140003ca7  test    rcx, rcx
0x140003caa  jz      short loc_140003CB1
0x140003cac  call    FreeHandleTable
0x140003cb1  xorps   xmm0, xmm0
0x140003cb4  lea     rcx, [rbx+8]; SpinLock
0x140003cb8  movups  xmmword ptr [rbx+50h], xmm0
0x140003cbc  xor     eax, eax
0x140003cbe  mov     [rbx+60h], rax
0x140003cc2  mov     dl, [rbx+10h]; NewIrql
0x140003cc5  call    cs:__imp_KeReleaseSpinLock
0x140003ccc  nop     dword ptr [rax+rax+00h]
0x140003cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cd8  cmp     rcx, rsi
0x140003cdb  jz      short loc_140003CFF
0x140003cdd  mov     eax, [rcx+2Ch]
0x140003ce0  test    al, 2
0x140003ce2  jz      short loc_140003CFF
0x140003ce4  cmp     byte ptr [rcx+29h], 3
0x140003ce8  jb      short loc_140003CFF
0x140003cea  mov     rcx, [rcx+18h]
0x140003cee  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140003cf5  mov     edx, 31h ; '1'
0x140003cfa  call    WPP_SF_
0x140003cff  mov     rbx, [rsp+28h+arg_0]
0x140003d04  mov     rsi, [rsp+28h+arg_8]
0x140003d09  add     rsp, 20h
0x140003d0d  pop     rdi
0x140003d0e  retn
```
