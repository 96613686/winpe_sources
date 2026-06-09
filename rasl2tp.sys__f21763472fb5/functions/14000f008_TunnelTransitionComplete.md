# TunnelTransitionComplete

- ea: `0x14000f008`
- end: `0x14000f2e4`
- name: `TunnelTransitionComplete`
- size: `732`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140010998`
- `0x1400130b8`
- `0x1400133ac`
- `0x1400135f0`
- `0x140013820`

## callees

- `0x1400013f0`
- `0x140001850`
- `0x14000328c`
- `0x1400035f0`
- `0x14000f008`
- `0x14000f698`
- `0x14000f898`
- `0x140012138`
- `0x14001ac30`
- `0x14001c050`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f261`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f261`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f194`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f194`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f12d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f14f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f12d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f14f`
- `NDIS!NdisFreeNetBufferList` at `0x14000f241`
- `NDIS!NdisFreeNetBufferList` at `0x14000f241`

## pseudocode

```c
void __fastcall TunnelTransitionComplete(__int64 a1, int a2)
{
  int *v2; // r15
  unsigned __int8 v4; // dl
  __int64 v5; // rcx
  int v6; // r11d
  int v7; // ebp
  const char *v8; // r9
  __int64 *i; // rdi
  KIRQL v10; // al
  bool v11; // zf
  _QWORD **v12; // r14
  _QWORD *v13; // rdi
  _QWORD *v14; // rax
  __int64 v15; // rdx
  _QWORD **v16; // r14
  _QWORD *v17; // rdi
  _QWORD *v18; // rax
  struct _NET_BUFFER_LIST *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx

  *(_DWORD *)(a1 + 124) = a2;
  v2 = (int *)(a1 + 120);
  ClearFlags(a1 + 120, 2);
  if ( v6 == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= v4 )
    {
      WPP_SF_qdd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids,
        a1,
        *(unsigned __int16 *)(a1 + 114),
        *(unsigned __int16 *)(a1 + 116));
    }
    ScheduleTunnelWork(a1, 0, (__int64)L2TPAddHostRoute, 0, 0, 0, 0, 0);
  }
  else
  {
    v7 = *v2;
    SetFlags(v5, 256);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v8 = "IN";
      if ( (v7 & 4) == 0 )
        v8 = "OUT";
      WPP_SF_sqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int16 *)(a1 + 114),
        (unsigned int)"OUT",
        (_DWORD)v8,
        a1,
        *(_WORD *)(a1 + 114),
        *(_WORD *)(a1 + 116));
    }
    *(_BYTE *)(a1 + 368) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
    for ( i = *(__int64 **)(a1 + 344); i != (__int64 *)(a1 + 344); i = (__int64 *)*i )
    {
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)i + 5);
      v11 = *((_DWORD *)i + 32) == 0;
      *((_BYTE *)i + 48) = v10;
      if ( v11 )
        *((_DWORD *)i + 32) = (v7 & 0x20) != 0 ? -1073668058 : -1073668063;
      CallTransitionComplete(a1, i, 0);
      KeReleaseSpinLock((PKSPIN_LOCK)i + 5, *((_BYTE *)i + 48));
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), *(_BYTE *)(a1 + 368));
    v12 = (_QWORD **)(a1 + 208);
    while ( 1 )
    {
      v13 = *v12;
      if ( *v12 == v12 )
        break;
      if ( (_QWORD **)v13[1] != v12 || (v14 = (_QWORD *)*v13, *(_QWORD **)(*v13 + 8LL) != v13) )
LABEL_30:
        __fastfail(3u);
      *v12 = v14;
      v14[1] = v12;
      v15 = v13[3];
      v13[1] = v13;
      *v13 = v13;
      RemoveTqi(*(_QWORD *)(a1 + 304), v15, 2);
      DereferenceControlSent(v13);
    }
    v16 = (_QWORD **)(a1 + 288);
    while ( 1 )
    {
      v17 = *v16;
      if ( *v16 == v16 )
        break;
      if ( (_QWORD **)v17[1] != v16 )
        goto LABEL_30;
      v18 = (_QWORD *)*v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 )
        goto LABEL_30;
      *v16 = v18;
      v18[1] = v16;
      v19 = (struct _NET_BUFFER_LIST *)v17[4];
      v17[1] = v17;
      *v17 = v17;
      NdisFreeNetBufferList(v19);
      v20 = v17[3];
      if ( v20 )
        DereferenceVc(v20);
      ExFreePoolWithTag(v17 - 2, 0);
    }
    v21 = *(_QWORD *)(a1 + 264);
    if ( v21 )
    {
      RemoveTqi(*(_QWORD *)(a1 + 304), v21, 1);
      *(_QWORD *)(a1 + 264) = 0;
    }
    if ( (v7 & 8) != 0 )
    {
      ClearFlags(v2, 8);
      DereferenceTunnel(a1);
    }
    if ( (v7 & 0x200) != 0 )
    {
      ClearFlags(v2, 512);
      DereferenceTunnel(a1);
    }
  }
}

```

## disassembly

```asm
0x14000f008  push    rbx
0x14000f00a  push    rbp
0x14000f00b  push    rdi
0x14000f00c  push    r12
0x14000f00e  push    r13
0x14000f010  push    r14
0x14000f012  push    r15
0x14000f014  sub     rsp, 50h
0x14000f018  mov     [rcx+7Ch], edx
0x14000f01b  lea     r15, [rcx+78h]
0x14000f01f  mov     r11d, edx
0x14000f022  mov     rbx, rcx
0x14000f025  mov     rcx, r15
0x14000f028  mov     edx, 2
0x14000f02d  call    ClearFlags
0x14000f032  cmp     r11d, 3
0x14000f036  jnz     loc_14000F0C2
0x14000f03c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f043  lea     rax, WPP_GLOBAL_Control
0x14000f04a  cmp     rcx, rax
0x14000f04d  jz      short loc_14000F084
0x14000f04f  mov     eax, [rcx+2Ch]
0x14000f052  test    al, 8
0x14000f054  jz      short loc_14000F084
0x14000f056  cmp     [rcx+29h], dl
0x14000f059  jb      short loc_14000F084
0x14000f05b  movzx   r8d, word ptr [rbx+72h]
0x14000f060  lea     edx, [r11+0Ch]
0x14000f064  movzx   eax, word ptr [rbx+74h]
0x14000f068  mov     r9, rbx
0x14000f06b  mov     rcx, [rcx+18h]
0x14000f06f  mov     dword ptr [rsp+88h+var_60], eax
0x14000f073  mov     dword ptr [rsp+88h+var_68], r8d
0x14000f078  lea     r8, WPP_6ae8e3282b593c5549b818ef668891aa_Traceguids
0x14000f07f  call    WPP_SF_qdd
0x14000f084  mov     [rsp+88h+var_48], 0
0x14000f089  lea     r8, L2TPAddHostRoute
0x14000f090  mov     [rsp+88h+var_50], 0
0x14000f095  xor     r9d, r9d
0x14000f098  mov     [rsp+88h+var_58], 0
0x14000f0a1  xor     edx, edx
0x14000f0a3  mov     [rsp+88h+var_60], 0
0x14000f0ac  mov     rcx, rbx
0x14000f0af  mov     [rsp+88h+var_68], 0
0x14000f0b8  call    ScheduleTunnelWork
0x14000f0bd  jmp     loc_14000F2D3
0x14000f0c2  mov     ebp, [r15]
0x14000f0c5  mov     edx, 100h
0x14000f0ca  call    SetFlags
0x14000f0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0d6  lea     rax, WPP_GLOBAL_Control
0x14000f0dd  cmp     rcx, rax
0x14000f0e0  jz      short loc_14000F123
0x14000f0e2  mov     eax, [rcx+2Ch]
0x14000f0e5  test    al, 8
0x14000f0e7  jz      short loc_14000F123
0x14000f0e9  cmp     byte ptr [rcx+29h], 2
0x14000f0ed  jb      short loc_14000F123
0x14000f0ef  movzx   eax, word ptr [rbx+74h]
0x14000f0f3  lea     r8, aOut; "OUT"
0x14000f0fa  movzx   edx, word ptr [rbx+72h]
0x14000f0fe  lea     r9, aIn; "IN"
0x14000f105  mov     rcx, [rcx+18h]
0x14000f109  test    bpl, 4
0x14000f10d  mov     dword ptr [rsp+88h+var_58], eax
0x14000f111  mov     dword ptr [rsp+88h+var_60], edx
0x14000f115  cmovz   r9, r8
0x14000f119  mov     [rsp+88h+var_68], rbx
0x14000f11e  call    WPP_SF_sqdd
0x14000f123  lea     r13, [rbx+168h]
0x14000f12a  mov     rcx, r13; SpinLock
0x14000f12d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f134  nop     dword ptr [rax+rax+00h]
0x14000f139  lea     r14, [rbx+158h]
0x14000f140  mov     [rbx+170h], al
0x14000f146  mov     rdi, [r14]
0x14000f149  jmp     short loc_14000F1A3
0x14000f14b  lea     rcx, [rdi+28h]; SpinLock
0x14000f14f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f156  nop     dword ptr [rax+rax+00h]
0x14000f15b  cmp     dword ptr [rdi+80h], 0
0x14000f162  mov     [rdi+30h], al
0x14000f165  jnz     short loc_14000F17F
0x14000f167  mov     al, bpl
0x14000f16a  and     al, 20h
0x14000f16c  neg     al
0x14000f16e  sbb     edx, edx
0x14000f170  and     edx, 5
0x14000f173  add     edx, 0C0012021h
0x14000f179  mov     [rdi+80h], edx
0x14000f17f  xor     r8d, r8d
0x14000f182  mov     rdx, rdi
0x14000f185  mov     rcx, rbx
0x14000f188  call    CallTransitionComplete
0x14000f18d  mov     dl, [rdi+30h]; NewIrql
0x14000f190  lea     rcx, [rdi+28h]; SpinLock
0x14000f194  call    cs:__imp_KeReleaseSpinLock
0x14000f19b  nop     dword ptr [rax+rax+00h]
0x14000f1a0  mov     rdi, [rdi]
0x14000f1a3  cmp     rdi, r14
0x14000f1a6  jnz     short loc_14000F14B
0x14000f1a8  mov     dl, [rbx+170h]; NewIrql
0x14000f1ae  mov     rcx, r13; SpinLock
0x14000f1b1  call    cs:__imp_KeReleaseSpinLock
0x14000f1b8  nop     dword ptr [rax+rax+00h]
0x14000f1bd  lea     r14, [rbx+0D0h]
0x14000f1c4  mov     rdi, [r14]
0x14000f1c7  cmp     rdi, r14
0x14000f1ca  jz      short loc_14000F211
0x14000f1cc  cmp     [rdi+8], r14
0x14000f1d0  jnz     loc_14000F26F
0x14000f1d6  mov     rax, [rdi]
0x14000f1d9  cmp     [rax+8], rdi
0x14000f1dd  jnz     loc_14000F26F
0x14000f1e3  mov     [r14], rax
0x14000f1e6  mov     r8d, 2
0x14000f1ec  mov     [rax+8], r14
0x14000f1f0  mov     rdx, [rdi+18h]
0x14000f1f4  mov     [rdi+8], rdi
0x14000f1f8  mov     [rdi], rdi
0x14000f1fb  mov     rcx, [rbx+130h]
0x14000f202  call    RemoveTqi
0x14000f207  mov     rcx, rdi; Entry
0x14000f20a  call    DereferenceControlSent
0x14000f20f  jmp     short loc_14000F1C4
0x14000f211  lea     r14, [rbx+120h]
0x14000f218  mov     rdi, [r14]
0x14000f21b  cmp     rdi, r14
0x14000f21e  jz      short loc_14000F276
0x14000f220  cmp     [rdi+8], r14
0x14000f224  jnz     short loc_14000F26F
0x14000f226  mov     rax, [rdi]
0x14000f229  cmp     [rax+8], rdi
0x14000f22d  jnz     short loc_14000F26F
0x14000f22f  mov     [r14], rax
0x14000f232  mov     [rax+8], r14
0x14000f236  mov     rcx, [rdi+20h]; NetBufferList
0x14000f23a  mov     [rdi+8], rdi
0x14000f23e  mov     [rdi], rdi
0x14000f241  call    cs:__imp_NdisFreeNetBufferList
0x14000f248  nop     dword ptr [rax+rax+00h]
0x14000f24d  mov     rcx, [rdi+18h]
0x14000f251  test    rcx, rcx
0x14000f254  jz      short loc_14000F25B
0x14000f256  call    DereferenceVc
0x14000f25b  lea     rcx, [rdi-10h]; P
0x14000f25f  xor     edx, edx; Tag
0x14000f261  call    cs:__imp_ExFreePoolWithTag
0x14000f268  nop     dword ptr [rax+rax+00h]
0x14000f26d  jmp     short loc_14000F218
0x14000f26f  mov     ecx, 3
0x14000f274  int     29h; Win8: RtlFailFast(ecx)
0x14000f276  mov     rdx, [rbx+108h]
0x14000f27d  test    rdx, rdx
0x14000f280  jz      short loc_14000F29F
0x14000f282  mov     rcx, [rbx+130h]
0x14000f289  mov     r8d, 1
0x14000f28f  call    RemoveTqi
0x14000f294  mov     qword ptr [rbx+108h], 0
0x14000f29f  test    bpl, 8
0x14000f2a3  jz      short loc_14000F2BA
0x14000f2a5  mov     edx, 8
0x14000f2aa  mov     rcx, r15
0x14000f2ad  call    ClearFlags
0x14000f2b2  mov     rcx, rbx
0x14000f2b5  call    DereferenceTunnel
0x14000f2ba  mov     edx, 200h
0x14000f2bf  test    edx, ebp
0x14000f2c1  jz      short loc_14000F2D3
0x14000f2c3  mov     rcx, r15
0x14000f2c6  call    ClearFlags
0x14000f2cb  mov     rcx, rbx
0x14000f2ce  call    DereferenceTunnel
0x14000f2d3  add     rsp, 50h
0x14000f2d7  pop     r15
0x14000f2d9  pop     r14
0x14000f2db  pop     r13
0x14000f2dd  pop     r12
0x14000f2df  pop     rdi
0x14000f2e0  pop     rbp
0x14000f2e1  pop     rbx
0x14000f2e2  retn
```
