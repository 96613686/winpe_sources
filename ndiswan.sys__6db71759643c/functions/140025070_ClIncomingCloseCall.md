# ClIncomingCloseCall

- ea: `0x140025070`
- end: `0x1400253a2`
- name: `ClIncomingCloseCall`
- size: `818`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002cc0`
- `0x140005494`
- `0x14000550c`
- `0x140005750`
- `0x140007364`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a648`
- `0x14000a68c`
- `0x140016230`
- `0x140024fe0`
- `0x140025070`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140025149`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002518a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025246`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400252d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025317`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002534c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025149`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002518a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025246`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400252d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025317`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002534c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025123`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002519d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025261`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400252e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025326`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025123`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002519d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025261`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400252e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025326`
- `NDIS!NdisClCloseCall` at `0x140025161`
- `NDIS!NdisClCloseCall` at `0x140025161`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ClIncomingCloseCall(unsigned int a1, __int64 a2)
{
  int v2; // ebp
  __int64 v4; // r8
  PDEVICE_OBJECT v5; // rcx
  int v6; // eax
  _QWORD *v7; // rbx
  KSPIN_LOCK *v8; // r15
  KIRQL v9; // al
  unsigned int v10; // eax
  KIRQL v11; // al
  __int64 *v12; // rdi
  __int64 *v13; // rsi
  __int64 **v14; // rax
  char *v15; // rdi
  KSPIN_LOCK *v16; // r12
  __int64 v17; // rdx
  __int64 v18; // r8
  char *v19; // r14
  __int64 *v20; // rcx
  __int64 v21; // rsi
  __int64 **v22; // rax
  KIRQL v23; // al
  bool v24; // zf
  KIRQL v25; // al
  PDEVICE_OBJECT *result; // rax
  PVOID v27; // [rsp+30h] [rbp-48h] BYREF
  PVOID Entry[8]; // [rsp+38h] [rbp-40h] BYREF

  v2 = 0;
  v27 = 0;
  v4 = a1;
  Entry[0] = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a2, v4);
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline(v5, a2, v4);
  if ( v6 )
  {
    if ( (int)ValidateLinkAndBundle(a2, 1, &v27, Entry) < 0 )
      goto LABEL_41;
  }
  else if ( !(unsigned __int8)AreLinkAndBundleValid(a2, 1, &v27, Entry) )
  {
    goto LABEL_41;
  }
  v7 = v27;
  v8 = (KSPIN_LOCK *)((char *)v27 + 736);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v27 + 92);
  *((_BYTE *)v7 + 744) = v9;
  *((_DWORD *)v7 + 5) = 1;
  if ( *((_DWORD *)v7 + 8) )
  {
    *((_DWORD *)v7 + 6) = 1;
    KeReleaseSpinLock(v8, v9);
  }
  else
  {
    *((_DWORD *)v7 + 6) = 0;
    KeReleaseSpinLock(v8, v9);
    v10 = NdisClCloseCall((NDIS_HANDLE)v7[7], 0, 0, 0);
    if ( v10 != 259 )
      ClCloseCallComplete(v10, v7, 0);
  }
  v11 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v12 = (__int64 *)qword_14001E338;
  byte_14001E3D8 = v11;
  if ( (__int64 *)qword_14001E338 != &qword_14001E338 )
  {
    do
    {
      v13 = (__int64 *)*v12;
      if ( (_QWORD *)v12[3] == v7 )
      {
        if ( (__int64 *)v13[1] != v12 || (v14 = (__int64 **)v12[1], *v14 != v12) )
LABEL_36:
          __fastfail(3u);
        *v14 = v13;
        v13[1] = (__int64)v14;
        --*((_DWORD *)v7 + 24);
        --dword_14001E32C;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, v12);
        }
        NdisWanFreeRecvDesc((__int64)v12);
      }
      v12 = v13;
    }
    while ( v13 != &qword_14001E338 );
  }
  KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
  v15 = (char *)Entry[0];
  v16 = (KSPIN_LOCK *)((char *)Entry[0] + 1768);
  v15[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry[0] + 221);
  do
  {
    v19 = &v15[32 * v2 + 112 + 8 * v2];
    v20 = *(__int64 **)v19;
    if ( *(char **)v19 != v19 )
    {
      do
      {
        v21 = *v20;
        if ( (_QWORD *)v20[5] == v7 )
        {
          if ( *(__int64 **)(v21 + 8) != v20 )
            goto LABEL_36;
          v22 = (__int64 **)v20[1];
          if ( *v22 != v20 )
            goto LABEL_36;
          *v22 = (__int64 *)v21;
          *(_QWORD *)(v21 + 8) = v22;
          --*((_DWORD *)v19 + 4);
          ((void (*)(void))v7[14])();
        }
        v20 = (__int64 *)v21;
      }
      while ( (char *)v21 != v19 );
    }
    ++v2;
  }
  while ( !v2 );
  UpdateBundleInfo(v15, v17, v18);
  KeReleaseSpinLock(v16, v15[1776]);
  v23 = KeAcquireSpinLockRaiseToDpc(v8);
  *((_BYTE *)v7 + 744) = v23;
  v24 = (*((_DWORD *)v7 + 7))-- == 1;
  if ( v24 )
    DoDerefLinkCBWork(v7);
  else
    KeReleaseSpinLock(v8, v23);
  v25 = KeAcquireSpinLockRaiseToDpc(v16);
  v15[1776] = v25;
  v24 = (*((_DWORD *)v15 + 6))-- == 1;
  if ( v24 )
    DoDerefBundleCBWork(v15);
  else
    KeReleaseSpinLock(v16, v25);
LABEL_41:
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    return (PDEVICE_OBJECT *)WPP_SF_(
                               WPP_GLOBAL_Control->AttachedDevice,
                               49,
                               WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140025070  push    rbx
0x140025072  push    rbp
0x140025073  push    rsi
0x140025074  push    rdi
0x140025075  push    r12
0x140025077  push    r14
0x140025079  push    r15
0x14002507b  sub     rsp, 40h
0x14002507f  xor     ebp, ebp
0x140025081  mov     rbx, rdx
0x140025084  mov     [rsp+78h+var_48], rbp
0x140025089  mov     r8d, ecx
0x14002508c  mov     [rsp+78h+Entry], rbp
0x140025091  mov     rcx, cs:WPP_GLOBAL_Control
0x140025098  lea     rax, WPP_GLOBAL_Control
0x14002509f  mov     r12d, 8000h
0x1400250a5  cmp     rcx, rax
0x1400250a8  jz      short loc_1400250D1
0x1400250aa  test    [rcx+2Ch], r12d
0x1400250ae  jz      short loc_1400250D1
0x1400250b0  cmp     byte ptr [rcx+29h], 5
0x1400250b4  jb      short loc_1400250D1
0x1400250b6  mov     rcx, [rcx+18h]
0x1400250ba  lea     edx, [rbp+2Fh]
0x1400250bd  mov     [rsp+78h+var_58], r8d
0x1400250c2  mov     r9, rbx
0x1400250c5  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400250cc  call    WPP_SF_qD
0x1400250d1  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x1400250d7  test    al, 10h
0x1400250d9  jz      short loc_1400250E0
0x1400250db  and     eax, 1
0x1400250de  jmp     short loc_1400250E5
0x1400250e0  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x1400250e5  lea     r9, [rsp+78h+Entry]
0x1400250ea  mov     dl, 1
0x1400250ec  lea     r8, [rsp+78h+var_48]
0x1400250f1  mov     rcx, rbx
0x1400250f4  test    eax, eax
0x1400250f6  jnz     short loc_140025107
0x1400250f8  call    AreLinkAndBundleValid
0x1400250fd  test    al, al
0x1400250ff  jz      loc_14002535E
0x140025105  jmp     short loc_140025114
0x140025107  call    ValidateLinkAndBundle
0x14002510c  test    eax, eax
0x14002510e  js      loc_14002535E
0x140025114  mov     rbx, [rsp+78h+var_48]
0x140025119  lea     r15, [rbx+2E0h]
0x140025120  mov     rcx, r15; SpinLock
0x140025123  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002512a  nop     dword ptr [rax+rax+00h]
0x14002512f  mov     [rbx+2E8h], al
0x140025135  mov     dl, al; NewIrql
0x140025137  mov     dword ptr [rbx+14h], 1
0x14002513e  mov     rcx, r15; SpinLock
0x140025141  cmp     [rbx+20h], ebp
0x140025144  jnz     short loc_140025183
0x140025146  mov     [rbx+18h], ebp
0x140025149  call    cs:__imp_KeReleaseSpinLock
0x140025150  nop     dword ptr [rax+rax+00h]
0x140025155  mov     rcx, [rbx+38h]; NdisVcHandle
0x140025159  xor     r9d, r9d; Size
0x14002515c  xor     r8d, r8d; Buffer
0x14002515f  xor     edx, edx; NdisPartyHandle
0x140025161  call    cs:__imp_NdisClCloseCall
0x140025168  nop     dword ptr [rax+rax+00h]
0x14002516d  cmp     eax, 103h
0x140025172  jz      short loc_140025196
0x140025174  xor     r8d, r8d
0x140025177  mov     rdx, rbx
0x14002517a  mov     ecx, eax
0x14002517c  call    ClCloseCallComplete
0x140025181  jmp     short loc_140025196
0x140025183  mov     dword ptr [rbx+18h], 1
0x14002518a  call    cs:__imp_KeReleaseSpinLock
0x140025191  nop     dword ptr [rax+rax+00h]
0x140025196  lea     rcx, SpinLock; SpinLock
0x14002519d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400251a4  nop     dword ptr [rax+rax+00h]
0x1400251a9  mov     rdi, cs:qword_14001E338
0x1400251b0  lea     r14, qword_14001E338
0x1400251b7  mov     cs:byte_14001E3D8, al
0x1400251bd  cmp     rdi, r14
0x1400251c0  jz      short loc_140025239
0x1400251c2  mov     rsi, [rdi]
0x1400251c5  cmp     [rdi+18h], rbx
0x1400251c9  jnz     short loc_140025231
0x1400251cb  cmp     [rsi+8], rdi
0x1400251cf  jnz     loc_14002530B
0x1400251d5  mov     rax, [rdi+8]
0x1400251d9  cmp     [rax], rdi
0x1400251dc  jnz     loc_14002530B
0x1400251e2  mov     [rax], rsi
0x1400251e5  mov     [rsi+8], rax
0x1400251e9  dec     dword ptr [rbx+60h]
0x1400251ec  dec     cs:dword_14001E32C
0x1400251f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400251f9  lea     rax, WPP_GLOBAL_Control
0x140025200  cmp     rcx, rax
0x140025203  jz      short loc_140025229
0x140025205  test    [rcx+2Ch], r12d
0x140025209  jz      short loc_140025229
0x14002520b  cmp     byte ptr [rcx+29h], 5
0x14002520f  jb      short loc_140025229
0x140025211  mov     rcx, [rcx+18h]
0x140025215  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14002521c  mov     edx, 30h ; '0'
0x140025221  mov     r9, rdi
0x140025224  call    WPP_SF_q
0x140025229  mov     rcx, rdi
0x14002522c  call    NdisWanFreeRecvDesc
0x140025231  mov     rdi, rsi
0x140025234  cmp     rsi, r14
0x140025237  jnz     short loc_1400251C2
0x140025239  mov     dl, cs:byte_14001E3D8; NewIrql
0x14002523f  lea     rcx, SpinLock; SpinLock
0x140025246  call    cs:__imp_KeReleaseSpinLock
0x14002524d  nop     dword ptr [rax+rax+00h]
0x140025252  mov     rdi, [rsp+78h+Entry]
0x140025257  lea     r12, [rdi+6E8h]
0x14002525e  mov     rcx, r12; SpinLock
0x140025261  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025268  nop     dword ptr [rax+rax+00h]
0x14002526d  mov     [rdi+6F0h], al
0x140025273  mov     eax, ebp
0x140025275  lea     rcx, ds:0Eh[rax*4]
0x14002527d  add     rcx, rax
0x140025280  lea     r14, [rdi+rcx*8]
0x140025284  mov     rcx, [r14]
0x140025287  cmp     rcx, r14
0x14002528a  jz      short loc_1400252C0
0x14002528c  mov     rsi, [rcx]
0x14002528f  cmp     [rcx+28h], rbx
0x140025293  jnz     short loc_1400252B8
0x140025295  cmp     [rsi+8], rcx
0x140025299  jnz     short loc_14002530B
0x14002529b  mov     rax, [rcx+8]
0x14002529f  cmp     [rax], rcx
0x1400252a2  jnz     short loc_14002530B
0x1400252a4  mov     [rax], rsi
0x1400252a7  mov     [rsi+8], rax
0x1400252ab  dec     dword ptr [r14+10h]
0x1400252af  mov     rax, [rbx+70h]
0x1400252b3  call    _guard_dispatch_icall
0x1400252b8  mov     rcx, rsi
0x1400252bb  cmp     rsi, r14
0x1400252be  jnz     short loc_14002528C
0x1400252c0  inc     ebp
0x1400252c2  cmp     ebp, 1
0x1400252c5  jb      short loc_140025273
0x1400252c7  mov     rcx, rdi
0x1400252ca  call    UpdateBundleInfo
0x1400252cf  mov     dl, [rdi+6F0h]; NewIrql
0x1400252d5  mov     rcx, r12; SpinLock
0x1400252d8  call    cs:__imp_KeReleaseSpinLock
0x1400252df  nop     dword ptr [rax+rax+00h]
0x1400252e4  mov     rcx, r15; SpinLock
0x1400252e7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400252ee  nop     dword ptr [rax+rax+00h]
0x1400252f3  or      esi, 0FFFFFFFFh
0x1400252f6  mov     [rbx+2E8h], al
0x1400252fc  add     [rbx+1Ch], esi
0x1400252ff  jnz     short loc_140025312
0x140025301  mov     rcx, rbx; Entry
0x140025304  call    DoDerefLinkCBWork
0x140025309  jmp     short loc_140025323
0x14002530b  mov     ecx, 3
0x140025310  int     29h; Win8: RtlFailFast(ecx)
0x140025312  mov     dl, al; NewIrql
0x140025314  mov     rcx, r15; SpinLock
0x140025317  call    cs:__imp_KeReleaseSpinLock
0x14002531e  nop     dword ptr [rax+rax+00h]
0x140025323  mov     rcx, r12; SpinLock
0x140025326  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002532d  nop     dword ptr [rax+rax+00h]
0x140025332  mov     [rdi+6F0h], al
0x140025338  add     [rdi+18h], esi
0x14002533b  jnz     short loc_140025347
0x14002533d  mov     rcx, rdi; Entry
0x140025340  call    DoDerefBundleCBWork
0x140025345  jmp     short loc_140025358
0x140025347  mov     dl, al; NewIrql
0x140025349  mov     rcx, r12; SpinLock
0x14002534c  call    cs:__imp_KeReleaseSpinLock
0x140025353  nop     dword ptr [rax+rax+00h]
0x140025358  mov     r12d, 8000h
0x14002535e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025365  lea     rax, WPP_GLOBAL_Control
0x14002536c  cmp     rcx, rax
0x14002536f  jz      short loc_140025392
0x140025371  test    [rcx+2Ch], r12d
0x140025375  jz      short loc_140025392
0x140025377  cmp     byte ptr [rcx+29h], 5
0x14002537b  jb      short loc_140025392
0x14002537d  mov     rcx, [rcx+18h]
0x140025381  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140025388  mov     edx, 31h ; '1'
0x14002538d  call    WPP_SF_
0x140025392  add     rsp, 40h
0x140025396  pop     r15
0x140025398  pop     r14
0x14002539a  pop     r12
0x14002539c  pop     rdi
0x14002539d  pop     rsi
0x14002539e  pop     rbp
0x14002539f  pop     rbx
0x1400253a0  retn
```
