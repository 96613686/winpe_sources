# ClIncomingCallQoSChange

- ea: `0x140007bf0`
- end: `0x140007dc2`
- name: `ClIncomingCallQoSChange`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002cc0`
- `0x140005494`
- `0x14000550c`
- `0x140007364`
- `0x140007bf0`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007d36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ca5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ca5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d4c`

## pseudocode

```c
void __fastcall ClIncomingCallQoSChange(__int64 a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT v5; // rcx
  int v6; // eax
  _BYTE *v7; // rdi
  KSPIN_LOCK *v8; // rsi
  KIRQL v9; // al
  _QWORD *v10; // rbx
  _OWORD *v11; // rax
  __int64 v12; // rax
  int v13; // eax
  bool v14; // zf
  KIRQL v15; // al
  PVOID Entry; // [rsp+50h] [rbp+18h] BYREF
  PVOID v17; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  Entry = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a1);
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline(v5, a2, a3);
  if ( v6 )
  {
    if ( (int)ValidateLinkAndBundle(a1, 1, &v17, &Entry) < 0 )
      goto LABEL_22;
  }
  else if ( !(unsigned __int8)AreLinkAndBundleValid(a1, 1, &v17, &Entry) )
  {
    goto LABEL_22;
  }
  v7 = Entry;
  v8 = (KSPIN_LOCK *)((char *)Entry + 1768);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
  v10 = v17;
  v7[1776] = v9;
  v11 = *(_OWORD **)(a2 + 8);
  *((_OWORD *)v10 + 8) = *v11;
  *((_OWORD *)v10 + 9) = v11[1];
  v12 = *(_QWORD *)(a2 + 8);
  *((_OWORD *)v10 + 10) = *(_OWORD *)(v12 + 32);
  *((_OWORD *)v10 + 11) = *(_OWORD *)(v12 + 48);
  v13 = *((_DWORD *)v10 + 34);
  if ( !v13 )
  {
    v13 = 3600;
    *((_DWORD *)v10 + 34) = 3600;
  }
  if ( !*((_DWORD *)v10 + 42) )
    *((_DWORD *)v10 + 42) = v13;
  UpdateBundleInfo((__int64)v7);
  v14 = (*((_DWORD *)v7 + 6))-- == 1;
  if ( v14 )
    DoDerefBundleCBWork(v7);
  else
    KeReleaseSpinLock(v8, v7[1776]);
  v15 = KeAcquireSpinLockRaiseToDpc(v10 + 92);
  *((_BYTE *)v10 + 744) = v15;
  v14 = (*((_DWORD *)v10 + 7))-- == 1;
  if ( v14 )
    DoDerefLinkCBWork(v10);
  else
    KeReleaseSpinLock(v10 + 92, v15);
LABEL_22:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x140007bf0  mov     rax, rsp
0x140007bf3  mov     [rax+8], rbx
0x140007bf7  mov     [rax+10h], rbp
0x140007bfb  push    rsi
0x140007bfc  push    rdi
0x140007bfd  push    r12
0x140007bff  sub     rsp, 20h
0x140007c03  mov     rbp, rdx
0x140007c06  mov     qword ptr [rax+20h], 0
0x140007c0e  mov     rbx, rcx
0x140007c11  mov     qword ptr [rax+18h], 0
0x140007c19  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c20  lea     r12, WPP_GLOBAL_Control
0x140007c27  cmp     rcx, r12
0x140007c2a  jz      short loc_140007C53
0x140007c2c  test    dword ptr [rcx+2Ch], 8000h
0x140007c33  jz      short loc_140007C53
0x140007c35  cmp     byte ptr [rcx+29h], 5
0x140007c39  jb      short loc_140007C53
0x140007c3b  mov     rcx, [rcx+18h]
0x140007c3f  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007c46  mov     edx, 2Bh ; '+'
0x140007c4b  mov     r9, rbx
0x140007c4e  call    WPP_SF_q
0x140007c53  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140007c59  test    al, 10h
0x140007c5b  jz      short loc_140007C62
0x140007c5d  and     eax, 1
0x140007c60  jmp     short loc_140007C67
0x140007c62  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140007c67  lea     r9, [rsp+38h+Entry]
0x140007c6c  mov     dl, 1
0x140007c6e  lea     r8, [rsp+38h+arg_18]
0x140007c73  mov     rcx, rbx
0x140007c76  test    eax, eax
0x140007c78  jz      short loc_140007C89
0x140007c7a  call    ValidateLinkAndBundle
0x140007c7f  test    eax, eax
0x140007c81  js      loc_140007D7E
0x140007c87  jmp     short loc_140007C96
0x140007c89  call    AreLinkAndBundleValid
0x140007c8e  test    al, al
0x140007c90  jz      loc_140007D7E
0x140007c96  mov     rdi, [rsp+38h+Entry]
0x140007c9b  lea     rsi, [rdi+6E8h]
0x140007ca2  mov     rcx, rsi; SpinLock
0x140007ca5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007cac  nop     dword ptr [rax+rax+00h]
0x140007cb1  mov     rbx, [rsp+38h+arg_18]
0x140007cb6  mov     [rdi+6F0h], al
0x140007cbc  mov     rax, [rbp+8]
0x140007cc0  movups  xmm0, xmmword ptr [rax]
0x140007cc3  movups  xmmword ptr [rbx+80h], xmm0
0x140007cca  movups  xmm1, xmmword ptr [rax+10h]
0x140007cce  movups  xmmword ptr [rbx+90h], xmm1
0x140007cd5  mov     rax, [rbp+8]
0x140007cd9  movups  xmm0, xmmword ptr [rax+20h]
0x140007cdd  movups  xmmword ptr [rbx+0A0h], xmm0
0x140007ce4  movups  xmm1, xmmword ptr [rax+30h]
0x140007ce8  movups  xmmword ptr [rbx+0B0h], xmm1
0x140007cef  mov     eax, [rbx+88h]
0x140007cf5  test    eax, eax
0x140007cf7  jnz     short loc_140007D04
0x140007cf9  mov     eax, 0E10h
0x140007cfe  mov     [rbx+88h], eax
0x140007d04  cmp     dword ptr [rbx+0A8h], 0
0x140007d0b  jnz     short loc_140007D13
0x140007d0d  mov     [rbx+0A8h], eax
0x140007d13  mov     rcx, rdi
0x140007d16  call    UpdateBundleInfo
0x140007d1b  or      ebp, 0FFFFFFFFh
0x140007d1e  add     [rdi+18h], ebp
0x140007d21  jnz     short loc_140007D2D
0x140007d23  mov     rcx, rdi; Entry
0x140007d26  call    DoDerefBundleCBWork
0x140007d2b  jmp     short loc_140007D42
0x140007d2d  mov     dl, [rdi+6F0h]; NewIrql
0x140007d33  mov     rcx, rsi; SpinLock
0x140007d36  call    cs:__imp_KeReleaseSpinLock
0x140007d3d  nop     dword ptr [rax+rax+00h]
0x140007d42  lea     rdi, [rbx+2E0h]
0x140007d49  mov     rcx, rdi; SpinLock
0x140007d4c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007d53  nop     dword ptr [rax+rax+00h]
0x140007d58  mov     [rbx+2E8h], al
0x140007d5e  add     [rbx+1Ch], ebp
0x140007d61  jnz     short loc_140007D6D
0x140007d63  mov     rcx, rbx; Entry
0x140007d66  call    DoDerefLinkCBWork
0x140007d6b  jmp     short loc_140007D7E
0x140007d6d  mov     dl, al; NewIrql
0x140007d6f  mov     rcx, rdi; SpinLock
0x140007d72  call    cs:__imp_KeReleaseSpinLock
0x140007d79  nop     dword ptr [rax+rax+00h]
0x140007d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d85  cmp     rcx, r12
0x140007d88  jz      short loc_140007DAE
0x140007d8a  test    dword ptr [rcx+2Ch], 8000h
0x140007d91  jz      short loc_140007DAE
0x140007d93  cmp     byte ptr [rcx+29h], 5
0x140007d97  jb      short loc_140007DAE
0x140007d99  mov     rcx, [rcx+18h]
0x140007d9d  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007da4  mov     edx, 2Ch ; ','
0x140007da9  call    WPP_SF_
0x140007dae  mov     rbx, [rsp+38h+arg_0]
0x140007db3  mov     rbp, [rsp+38h+arg_8]
0x140007db8  add     rsp, 20h
0x140007dbc  pop     r12
0x140007dbe  pop     rdi
0x140007dbf  pop     rsi
0x140007dc0  retn
```
