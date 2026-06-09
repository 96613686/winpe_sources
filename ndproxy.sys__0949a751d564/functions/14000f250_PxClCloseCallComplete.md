# PxClCloseCallComplete

- ea: `0x14000f250`
- end: `0x14000f47c`
- name: `PxClCloseCallComplete`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140016450`

## callees

- `0x140001bc8`
- `0x140001c0c`
- `0x140001c60`
- `0x140006e08`
- `0x140007040`
- `0x140007fc0`
- `0x14000f250`
- `0x140011d30`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f305`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f418`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f305`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f418`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f455`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f455`

## pseudocode

```c
void __fastcall PxClCloseCallComplete(int a1, unsigned __int64 a2)
{
  char *v4; // rbx
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  PVOID Entry; // [rsp+40h] [rbp-68h] BYREF
  _QWORD Src[6]; // [rsp+48h] [rbp-60h] BYREF

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a2, a1);
  GetVcFromCtx(a2, &Entry);
  v4 = (char *)Entry;
  if ( Entry )
  {
    v4[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    if ( a1 )
    {
      *((_DWORD *)v4 + 8) |= 8u;
      *((_DWORD *)v4 + 9) |= 0x400u;
      goto LABEL_22;
    }
    *((_DWORD *)v4 + 9) |= 0x200u;
    v5 = *((_DWORD *)v4 + 8);
    if ( (v5 & 0x100) != 0 )
    {
LABEL_22:
      if ( (*((_DWORD *)v4 + 7))-- == 1 )
        DoDerefVcWork(v4);
      else
        KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, v4[520]);
      return;
    }
    if ( (v5 & 0x80u) == 0 )
    {
      if ( (v5 & 0x20) == 0 )
        goto LABEL_16;
      v6 = v5 & 0xFFFFFF9F | 0x40;
    }
    else
    {
      v6 = v5 & 0xFFFFFE7F | 0x100;
    }
    *((_DWORD *)v4 + 8) = v6;
LABEL_16:
    *((_DWORD *)v4 + 5) = *((_DWORD *)v4 + 4);
    *((_DWORD *)v4 + 4) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        v4,
        0x4000,
        0,
        *(_DWORD *)(*((_QWORD *)v4 + 38) + 32LL));
    v7 = *((_QWORD *)v4 + 32);
    Src[2] = 2;
    Src[3] = 0x4000;
    Src[4] = 0;
    v8 = *(_QWORD *)(v7 + 40);
    v9 = *((_QWORD *)v4 + 34);
    Src[0] = v8;
    Src[1] = v9;
    Src[5] = *(unsigned int *)(*((_QWORD *)v4 + 38) + 32LL);
    *(_QWORD *)(v4 + 292) = 0x4000;
    KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, v4[520]);
    PxIndicateStatus(Src);
    v4[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v4 + 64);
    if ( (*((_DWORD *)v4 + 8) & 0x10) != 0 )
      PxTapiCompleteDropIrps((__int64)v4);
    --*((_DWORD *)v4 + 7);
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)((_DWORD)Entry + 29),
      WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
      a2);
}

```

## disassembly

```asm
0x14000f250  push    rbx
0x14000f252  push    rsi
0x14000f253  push    rdi
0x14000f254  push    r14
0x14000f256  sub     rsp, 88h
0x14000f25d  mov     rax, cs:__security_cookie
0x14000f264  xor     rax, rsp
0x14000f267  mov     [rsp+0A8h+var_30], rax
0x14000f26c  mov     rdi, rdx
0x14000f26f  mov     [rsp+0A8h+Entry], 0
0x14000f278  mov     esi, ecx
0x14000f27a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f281  lea     r14, WPP_GLOBAL_Control
0x14000f288  cmp     rcx, r14
0x14000f28b  jz      short loc_14000F2AF
0x14000f28d  cmp     byte ptr [rcx+29h], 5
0x14000f291  jb      short loc_14000F2AF
0x14000f293  mov     rcx, [rcx+18h]
0x14000f297  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f29e  mov     edx, 1Ch
0x14000f2a3  mov     [rsp+0A8h+var_88], esi
0x14000f2a7  mov     r9, rdi
0x14000f2aa  call    WPP_SF_qD
0x14000f2af  lea     rdx, [rsp+0A8h+Entry]
0x14000f2b4  mov     rcx, rdi
0x14000f2b7  call    GetVcFromCtx
0x14000f2bc  mov     rbx, [rsp+0A8h+Entry]
0x14000f2c1  test    rbx, rbx
0x14000f2c4  jnz     short loc_14000F2FB
0x14000f2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2cd  cmp     rcx, r14
0x14000f2d0  jz      loc_14000F461
0x14000f2d6  cmp     byte ptr [rcx+29h], 3
0x14000f2da  jb      loc_14000F461
0x14000f2e0  mov     rcx, [rcx+18h]
0x14000f2e4  lea     edx, [rbx+1Dh]
0x14000f2e7  mov     r9, rdi
0x14000f2ea  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f2f1  call    WPP_SF_q
0x14000f2f6  jmp     loc_14000F461
0x14000f2fb  lea     rdi, [rbx+200h]
0x14000f302  mov     rcx, rdi; SpinLock
0x14000f305  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f30c  nop     dword ptr [rax+rax+00h]
0x14000f311  mov     [rbx+208h], al
0x14000f317  test    esi, esi
0x14000f319  jz      short loc_14000F329
0x14000f31b  or      dword ptr [rbx+20h], 8
0x14000f31f  bts     dword ptr [rbx+24h], 0Ah
0x14000f324  jmp     loc_14000F43C
0x14000f329  bts     dword ptr [rbx+24h], 9
0x14000f32e  mov     ecx, 100h
0x14000f333  mov     eax, [rbx+20h]
0x14000f336  test    ecx, eax
0x14000f338  jnz     loc_14000F43C
0x14000f33e  test    al, al
0x14000f340  jns     short loc_14000F34A
0x14000f342  btr     eax, 7
0x14000f346  or      eax, ecx
0x14000f348  jmp     short loc_14000F354
0x14000f34a  test    al, 20h
0x14000f34c  jz      short loc_14000F357
0x14000f34e  and     eax, 0FFFFFFDFh
0x14000f351  or      eax, 40h
0x14000f354  mov     [rbx+20h], eax
0x14000f357  mov     eax, [rbx+10h]
0x14000f35a  mov     [rbx+14h], eax
0x14000f35d  mov     dword ptr [rbx+10h], 0
0x14000f364  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f36b  mov     esi, 4000h
0x14000f370  cmp     rcx, r14
0x14000f373  jz      short loc_14000F3AD
0x14000f375  cmp     byte ptr [rcx+29h], 5
0x14000f379  jb      short loc_14000F3AD
0x14000f37b  mov     rax, [rbx+130h]
0x14000f382  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f389  mov     rcx, [rcx+18h]
0x14000f38d  mov     edx, 1Eh
0x14000f392  mov     r9, rbx
0x14000f395  mov     eax, [rax+20h]
0x14000f398  mov     [rsp+0A8h+var_78], eax
0x14000f39c  mov     [rsp+0A8h+var_80], 0
0x14000f3a4  mov     [rsp+0A8h+var_88], esi
0x14000f3a8  call    WPP_SF_qDDD
0x14000f3ad  mov     rax, [rbx+100h]
0x14000f3b4  mov     [rsp+0A8h+var_50], 2
0x14000f3bd  mov     [rsp+0A8h+var_48], rsi
0x14000f3c2  mov     [rsp+0A8h+var_40], 0
0x14000f3cb  mov     rcx, [rax+28h]
0x14000f3cf  mov     rax, [rbx+110h]
0x14000f3d6  mov     [rsp+0A8h+Src], rcx
0x14000f3db  mov     [rsp+0A8h+var_58], rax
0x14000f3e0  mov     rax, [rbx+130h]
0x14000f3e7  mov     ecx, [rax+20h]
0x14000f3ea  mov     [rsp+0A8h+var_38], rcx
0x14000f3ef  mov     rcx, rdi; SpinLock
0x14000f3f2  mov     [rbx+124h], rsi
0x14000f3f9  mov     dl, [rbx+208h]; NewIrql
0x14000f3ff  call    cs:__imp_KeReleaseSpinLock
0x14000f406  nop     dword ptr [rax+rax+00h]
0x14000f40b  lea     rcx, [rsp+0A8h+Src]; Src
0x14000f410  call    PxIndicateStatus
0x14000f415  mov     rcx, rdi; SpinLock
0x14000f418  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f41f  nop     dword ptr [rax+rax+00h]
0x14000f424  mov     [rbx+208h], al
0x14000f42a  mov     eax, [rbx+20h]
0x14000f42d  test    al, 10h
0x14000f42f  jz      short loc_14000F439
0x14000f431  mov     rcx, rbx
0x14000f434  call    PxTapiCompleteDropIrps
0x14000f439  dec     dword ptr [rbx+1Ch]
0x14000f43c  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14000f440  jnz     short loc_14000F44C
0x14000f442  mov     rcx, rbx; Entry
0x14000f445  call    DoDerefVcWork
0x14000f44a  jmp     short loc_14000F461
0x14000f44c  mov     dl, [rbx+208h]; NewIrql
0x14000f452  mov     rcx, rdi; SpinLock
0x14000f455  call    cs:__imp_KeReleaseSpinLock
0x14000f45c  nop     dword ptr [rax+rax+00h]
0x14000f461  mov     rcx, [rsp+0A8h+var_30]
0x14000f466  xor     rcx, rsp; StackCookie
0x14000f469  call    __security_check_cookie
0x14000f46e  add     rsp, 88h
0x14000f475  pop     r14
0x14000f477  pop     rdi
0x14000f478  pop     rsi
0x14000f479  pop     rbx
0x14000f47a  retn
```
