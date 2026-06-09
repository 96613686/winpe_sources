# MupiFreeProvider

- ea: `0x14000f644`
- end: `0x14000f6ca`
- name: `MupiFreeProvider`
- size: `134`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f2a0`
- `0x140012194`
- `0x1400129cc`

## callees

- `0x140002754`
- `0x14000f644`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f68c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f68c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6b7`

## pseudocode

```c
void __fastcall MupiFreeProvider(_QWORD *P)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x14u,
      (__int64)WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
      P);
  }
  v2 = (void *)P[6];
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = (void *)P[17];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000f644  push    rbx
0x14000f646  sub     rsp, 20h
0x14000f64a  mov     rbx, rcx
0x14000f64d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f654  lea     rax, WPP_GLOBAL_Control
0x14000f65b  cmp     rcx, rax
0x14000f65e  jz      short loc_14000F681
0x14000f660  test    dword ptr [rcx+2Ch], 4000000h
0x14000f667  jz      short loc_14000F681
0x14000f669  mov     rcx, [rcx+18h]
0x14000f66d  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14000f674  mov     edx, 14h
0x14000f679  mov     r9, rbx
0x14000f67c  call    WPP_SF_q
0x14000f681  mov     rcx, [rbx+30h]; P
0x14000f685  test    rcx, rcx
0x14000f688  jz      short loc_14000F698
0x14000f68a  xor     edx, edx; Tag
0x14000f68c  call    cs:__imp_ExFreePoolWithTag
0x14000f693  nop     dword ptr [rax+rax+00h]
0x14000f698  mov     rcx, [rbx+88h]; P
0x14000f69f  test    rcx, rcx
0x14000f6a2  jz      short loc_14000F6B2
0x14000f6a4  xor     edx, edx; Tag
0x14000f6a6  call    cs:__imp_ExFreePoolWithTag
0x14000f6ad  nop     dword ptr [rax+rax+00h]
0x14000f6b2  xor     edx, edx; Tag
0x14000f6b4  mov     rcx, rbx; P
0x14000f6b7  call    cs:__imp_ExFreePoolWithTag
0x14000f6be  nop     dword ptr [rax+rax+00h]
0x14000f6c3  add     rsp, 20h
0x14000f6c7  pop     rbx
0x14000f6c8  retn
```
