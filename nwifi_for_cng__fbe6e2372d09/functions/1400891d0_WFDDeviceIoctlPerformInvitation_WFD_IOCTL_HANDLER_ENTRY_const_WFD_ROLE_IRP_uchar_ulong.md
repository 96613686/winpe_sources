# WFDDeviceIoctlPerformInvitation(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x1400891d0`
- end: `0x14008980e`
- name: `?WFDDeviceIoctlPerformInvitation@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `1598`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140015b0c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140031488`
- `0x14003da34`
- `0x14007a8fc`
- `0x140080bb4`
- `0x140080dd0`
- `0x140080dfc`
- `0x1400891d0`
- `0x14008c000`
- `0x14008c694`
- `0x14008c788`
- `0x14008ee88`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089619`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089735`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089619`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140089735`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008962d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089746`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008962d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089746`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089479`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400894fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089712`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089479`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400894fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140089712`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400893d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140089648`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400893d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140089648`

## pseudocode

```c
__int64 __fastcall WFDDeviceIoctlPerformInvitation(
        const struct _WFD_IOCTL_HANDLER_ENTRY *a1,
        struct _WFD_ROLE *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  struct _WFD_ROLE *v5; // r10
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *v7; // rsi
  int v8; // r15d
  unsigned int v9; // ecx
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned __int8 *v13; // r9
  void *pRoleExt; // r13
  const char *v15; // rdx
  bool v16; // zf
  const char *v17; // r9
  unsigned int v18; // eax
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *v19; // r15
  __int64 v20; // rdx
  struct _WFD_PEER_DEVICE *v21; // r12
  unsigned int v22; // eax
  unsigned int v23; // edi
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *v24; // r9
  unsigned int v25; // edx
  unsigned int v26; // eax
  struct _WFD_PEER_DEVICE *v27; // rbx
  unsigned __int8 v29; // [rsp+60h] [rbp-20h]
  unsigned int v30; // [rsp+64h] [rbp-1Ch]
  unsigned int v31; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v32; // [rsp+6Ch] [rbp-14h]
  struct _WFD_PEER_DEVICE *v33; // [rsp+70h] [rbp-10h] BYREF
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *v34; // [rsp+78h] [rbp-8h] BYREF
  char v37; // [rsp+D8h] [rbp+58h] BYREF

  v5 = a2;
  v33 = 0;
  v37 = 0;
  v34 = 0;
  v31 = 0;
  if ( !a4 || a5 < 0x60 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, 199, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    }
    return v10;
  }
  v7 = (struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *)(a4 + 8);
  v8 = *((_DWORD *)a4 + 23);
  if ( v8 && (v9 = *((_DWORD *)a4 + 22), v9 < 0x58) || (v9 = *((_DWORD *)a4 + 22), v9 + v8 < v9) || v9 + v8 > a5 )
  {
    v10 = -1073676267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        200,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        v9,
        v8,
        v8 + v9,
        a5);
    }
    return v10;
  }
  v29 = a4[84];
  if ( v29 )
  {
    if ( !a4[33] )
    {
      v10 = -1073676267;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = 201;
LABEL_11:
      WPP_SF_(v11->AttachedDevice, v12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      return v10;
    }
    v13 = a4 + 26;
  }
  else
  {
    v13 = a4 + 26;
    if ( (*((_BYTE *)v7 + 18) & 1) == 0 && !*((_BYTE *)v7 + 25) )
    {
      v10 = -1073676267;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v10;
      v12 = 202;
      goto LABEL_11;
    }
  }
  pRoleExt = a2->pRoleExt;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
  {
    v15 = "CLIENT";
    if ( !v29 )
      v15 = "GO";
    v16 = (*v13 & 1) == 0;
    v17 = "REINVOKE";
    if ( v16 )
      v17 = "JOIN";
    WPP_SF_ss_MAC__MAC__SSID_DDq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v15,
      (_DWORD)v7 + 40,
      (_DWORD)v17,
      (__int64)v15,
      (__int64)v7 + 5,
      (__int64)v7 + 32,
      (__int64)v7 + 40,
      v9,
      v8,
      *(_QWORD *)a4);
    v5 = a2;
  }
  v18 = PtQueryAdapterSyncEx(v5->pGenVElan->pAdapt, 0xE050111u, &v37, 1u, 0, 0);
  v10 = v18;
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 204, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v18);
    return v10;
  }
  v19 = 0;
  *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
  if ( !(unsigned int)WFDDeviceFindPeerByMAC(
                        (struct _WFD_DEVICE_ROLE *)pRoleExt,
                        (unsigned __int8 (*)[6])((char *)v7 + 5),
                        &v33) )
  {
    v21 = 0;
    v10 = 1073807377;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 205, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_35:
    v23 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
LABEL_48:
    if ( v21 )
      WFDDeviceCleanupPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, v23);
    if ( v19 )
    {
      if ( *((_QWORD *)v19 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v19 - 2), (char *)v19 - 16);
      else
        ExFreePoolWithTag((char *)v19 - 16, *((_DWORD *)v19 - 2));
    }
    return v10;
  }
  v22 = WFDPeerDeviceCreate(pRoleExt, v20, *(_QWORD *)a4, 0, &v33);
  v10 = v22;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 206, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v22);
    v21 = v33;
    goto LABEL_35;
  }
  v21 = v33;
  *((_OWORD *)v33 + 28) = *(_OWORD *)v7;
  *((_OWORD *)v21 + 29) = *((_OWORD *)v7 + 1);
  *((_OWORD *)v21 + 30) = *((_OWORD *)v7 + 2);
  *((_OWORD *)v21 + 31) = *((_OWORD *)v7 + 3);
  *((_OWORD *)v21 + 32) = *((_OWORD *)v7 + 4);
  *((_QWORD *)v21 + 66) = *((_QWORD *)v7 + 10);
  v30 = *((_DWORD *)v21 + 14);
  *((_BYTE *)v21 + 40) = v37;
  KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
  v32 = a5 - 8;
  v10 = WFDRoleAddCachedIEsToInviteParamsOidStructure(a2, v7, a5 - 8, &v34, &v31);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_47:
    v23 = v30;
    goto LABEL_48;
  }
  v24 = v34;
  v19 = v34;
  if ( v34 )
  {
    v25 = v31;
    v7 = v34;
  }
  else
  {
    v25 = v32;
    v24 = v7;
  }
  *(_BYTE *)v24 = *((_BYTE *)a1 + 12);
  *((_WORD *)v7 + 1) = *((_WORD *)a1 + 7);
  *((_BYTE *)v7 + 1) = *((_BYTE *)a1 + 13);
  *((_DWORD *)v7 + 3) = 10000;
  *((_BYTE *)v7 + 4) = v37;
  v26 = PtRequestAdapterSync(a2->pGenVElan->pAdapt, 1u, 0xE05010Du, v24, v25);
  v10 = 0;
  if ( v26 != 1076035585 )
    v10 = v26;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 208, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v10);
    goto LABEL_47;
  }
  *((_BYTE *)pRoleExt + 1200) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pRoleExt + 149);
  if ( (unsigned int)WFDDeviceFindPeerByID((struct _WFD_DEVICE_ROLE *)pRoleExt, v30, &v33) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 209, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
    }
  }
  else
  {
    v27 = v33;
    if ( (unsigned __int8)WFDPeerDeviceSetState(v33, 1) )
    {
      *((_BYTE *)v27 + 40) = v37;
      WFDPeerDeviceQueueTimer(v27, 0x2710u, 0x3E8u);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
           && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        210,
        WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
        *((unsigned int *)v27 + 9));
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)pRoleExt + 149, *((_BYTE *)pRoleExt + 1200));
  if ( v19 )
  {
    if ( *((_QWORD *)v19 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v19 - 2), (char *)v19 - 16);
    else
      ExFreePoolWithTag((char *)v19 - 16, *((_DWORD *)v19 - 2));
  }
  return 0;
}

```

## disassembly

```asm
0x1400891d0  mov     [rsp-38h+arg_10], rbx
0x1400891d5  mov     [rsp-38h+arg_8], rdx
0x1400891da  mov     [rsp-38h+arg_0], rcx
0x1400891df  push    rbp
0x1400891e0  push    rsi
0x1400891e1  push    rdi
0x1400891e2  push    r12
0x1400891e4  push    r13
0x1400891e6  push    r14
0x1400891e8  push    r15
0x1400891ea  mov     rbp, rsp
0x1400891ed  sub     rsp, 80h
0x1400891f4  mov     r8d, [rbp+arg_20]
0x1400891f8  mov     r10, rdx
0x1400891fb  xor     edx, edx
0x1400891fd  mov     r12, r9
0x140089200  mov     [rbp+var_10], rdx
0x140089204  mov     [rbp+arg_18], dl
0x140089207  mov     [rbp+var_8], rdx
0x14008920b  mov     [rbp+var_18], edx
0x14008920e  test    r9, r9
0x140089211  jz      loc_1400897AC
0x140089217  cmp     r8d, 60h ; '`'
0x14008921b  jb      loc_1400897AC
0x140089221  lea     rsi, [r9+8]
0x140089225  mov     r15d, [rsi+54h]
0x140089229  test    r15d, r15d
0x14008922c  jz      short loc_14008923A
0x14008922e  mov     ecx, [rsi+50h]
0x140089231  cmp     ecx, 58h ; 'X'
0x140089234  jb      loc_140089759
0x14008923a  mov     ecx, [rsi+50h]
0x14008923d  lea     eax, [rcx+r15]
0x140089241  cmp     eax, ecx
0x140089243  jb      loc_140089759
0x140089249  cmp     eax, r8d
0x14008924c  ja      loc_140089759
0x140089252  mov     al, [rsi+4Ch]
0x140089255  mov     [rbp+var_20], al
0x140089258  test    al, al
0x14008925a  jz      loc_14008938B
0x140089260  cmp     [rsi+19h], dl
0x140089263  jnz     short loc_14008929B
0x140089265  mov     ebx, 0C0010015h
0x14008926a  mov     rcx, cs:WPP_GLOBAL_Control
0x140089271  lea     rdi, WPP_GLOBAL_Control
0x140089278  cmp     rcx, rdi
0x14008927b  jz      loc_1400897F0
0x140089281  mov     edx, 0C9h
0x140089286  mov     rcx, [rcx+18h]
0x14008928a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089291  call    WPP_SF_
0x140089296  jmp     loc_1400897F0
0x14008929b  lea     r9, [rsi+12h]
0x14008929f  mov     rbx, cs:WPP_GLOBAL_Control
0x1400892a6  lea     rdi, WPP_GLOBAL_Control
0x1400892ad  mov     r13, [r10+0B8h]
0x1400892b4  cmp     rbx, rdi
0x1400892b7  jz      short loc_140089333
0x1400892b9  cmp     byte ptr [rbx+29h], 3
0x1400892bd  jb      short loc_140089333
0x1400892bf  bt      dword ptr [rbx+2Ch], 15h
0x1400892c4  jnb     short loc_140089333
0x1400892c6  cmp     [rbp+var_20], 0
0x1400892ca  lea     r11, [rsi+20h]
0x1400892ce  lea     rax, aGo; "GO"
0x1400892d5  lea     r8, [r11+8]
0x1400892d9  lea     r10, [rsi+5]
0x1400892dd  lea     rdx, aClient; "CLIENT"
0x1400892e4  cmovz   rdx, rax
0x1400892e8  test    byte ptr [r9], 1
0x1400892ec  lea     rax, aJoin; "JOIN"
0x1400892f3  lea     r9, aReinvoke; "REINVOKE"
0x1400892fa  cmovz   r9, rax
0x1400892fe  mov     rax, [r12]
0x140089302  mov     [rsp+80h+var_30], rax
0x140089307  mov     [rsp+80h+var_38], r15d
0x14008930c  mov     [rsp+80h+var_40], ecx
0x140089310  mov     rcx, [rbx+18h]
0x140089314  mov     [rsp+80h+var_48], r8
0x140089319  mov     [rsp+80h+var_50], r11
0x14008931e  mov     [rsp+80h+var_58], r10
0x140089323  mov     [rsp+80h+var_60], rdx
0x140089328  call    WPP_SF_ss_MAC__MAC__SSID_DDq
0x14008932d  mov     r10, [rbp+arg_8]
0x140089331  xor     edx, edx
0x140089333  mov     rcx, [r10]
0x140089336  lea     r8, [rbp+arg_18]; void *
0x14008933a  mov     [rsp+80h+var_58], rdx; unsigned int *
0x14008933f  mov     r9d, 1; unsigned int
0x140089345  mov     [rsp+80h+var_60], rdx; unsigned int *
0x14008934a  mov     edx, 0E050111h; unsigned int
0x14008934f  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140089353  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140089358  mov     ebx, eax
0x14008935a  test    eax, eax
0x14008935c  jz      short loc_1400893C8
0x14008935e  mov     rcx, cs:WPP_GLOBAL_Control
0x140089365  cmp     rcx, rdi
0x140089368  jz      loc_1400897F0
0x14008936e  mov     rcx, [rcx+18h]
0x140089372  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089379  mov     edx, 0CCh
0x14008937e  mov     r9d, eax
0x140089381  call    WPP_SF_d
0x140089386  jmp     loc_1400897F0
0x14008938b  lea     r9, [rsi+12h]
0x14008938f  test    byte ptr [r9], 1
0x140089393  jnz     loc_14008929F
0x140089399  cmp     [rsi+19h], dl
0x14008939c  jnz     loc_14008929F
0x1400893a2  mov     ebx, 0C0010015h
0x1400893a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400893ae  lea     rdi, WPP_GLOBAL_Control
0x1400893b5  cmp     rcx, rdi
0x1400893b8  jz      loc_1400897F0
0x1400893be  mov     edx, 0CAh
0x1400893c3  jmp     loc_140089286
0x1400893c8  lea     rcx, [r13+4A8h]; SpinLock
0x1400893cf  xor     r15d, r15d
0x1400893d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400893d9  nop     dword ptr [rax+rax+00h]
0x1400893de  lea     rdx, [rsi+5]; unsigned __int8 (*)[6]
0x1400893e2  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x1400893e5  lea     r8, [rbp+var_10]; struct _WFD_PEER_DEVICE **
0x1400893e9  mov     [r13+4B0h], al
0x1400893f0  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x1400893f5  test    eax, eax
0x1400893f7  jnz     short loc_140089424
0x1400893f9  xor     r12d, r12d
0x1400893fc  mov     ebx, 40010011h
0x140089401  mov     rcx, cs:WPP_GLOBAL_Control
0x140089408  cmp     rcx, rdi
0x14008940b  jz      short loc_14008946A
0x14008940d  mov     rcx, [rcx+18h]
0x140089411  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089418  mov     edx, 0CDh
0x14008941d  call    WPP_SF_
0x140089422  jmp     short loc_14008946A
0x140089424  mov     r8, [r12]
0x140089428  lea     rax, [rbp+var_10]
0x14008942c  xor     r9d, r9d
0x14008942f  mov     [rsp+80h+var_60], rax
0x140089434  mov     rcx, r13
0x140089437  call    ?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)
0x14008943c  mov     ebx, eax
0x14008943e  test    eax, eax
0x140089440  jz      short loc_14008948A
0x140089442  mov     rcx, cs:WPP_GLOBAL_Control
0x140089449  cmp     rcx, rdi
0x14008944c  jz      short loc_140089466
0x14008944e  mov     rcx, [rcx+18h]
0x140089452  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089459  mov     edx, 0CEh
0x14008945e  mov     r9d, eax
0x140089461  call    WPP_SF_d
0x140089466  mov     r12, [rbp+var_10]
0x14008946a  lea     rax, [r13+4A8h]
0x140089471  xor     edi, edi
0x140089473  mov     dl, [rax+8]; NewIrql
0x140089476  mov     rcx, rax; SpinLock
0x140089479  call    cs:__imp_KeReleaseSpinLock
0x140089480  nop     dword ptr [rax+rax+00h]
0x140089485  jmp     loc_1400895EF
0x14008948a  movups  xmm0, xmmword ptr [rsi]
0x14008948d  mov     r12, [rbp+var_10]
0x140089491  lea     rcx, [r13+4A8h]; SpinLock
0x140089498  movups  xmmword ptr [r12+1C0h], xmm0
0x1400894a1  movups  xmm1, xmmword ptr [rsi+10h]
0x1400894a5  movups  xmmword ptr [r12+1D0h], xmm1
0x1400894ae  movups  xmm0, xmmword ptr [rsi+20h]
0x1400894b2  movups  xmmword ptr [r12+1E0h], xmm0
0x1400894bb  movups  xmm1, xmmword ptr [rsi+30h]
0x1400894bf  movups  xmmword ptr [r12+1F0h], xmm1
0x1400894c8  movups  xmm0, xmmword ptr [rsi+40h]
0x1400894cc  movups  xmmword ptr [r12+200h], xmm0
0x1400894d5  movsd   xmm1, qword ptr [rsi+50h]
0x1400894da  movsd   qword ptr [r12+210h], xmm1
0x1400894e4  mov     eax, [r12+38h]
0x1400894e9  mov     [rbp+var_1C], eax
0x1400894ec  mov     al, [rbp+arg_18]
0x1400894ef  mov     [r12+28h], al
0x1400894f4  mov     dl, [r13+4B0h]; NewIrql
0x1400894fb  call    cs:__imp_KeReleaseSpinLock
0x140089502  nop     dword ptr [rax+rax+00h]
0x140089507  mov     eax, [rbp+arg_20]
0x14008950a  lea     rcx, [rbp+var_18]
0x14008950e  add     eax, 0FFFFFFF8h
0x140089511  mov     [rsp+80h+var_60], rcx; unsigned int *
0x140089516  mov     rcx, [rbp+arg_8]; struct _WFD_ROLE *
0x14008951a  lea     r9, [rbp+var_8]; struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **
0x14008951e  mov     r8d, eax; unsigned int
0x140089521  mov     [rbp+var_14], eax
0x140089524  mov     rdx, rsi; struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *
0x140089527  call    ?WFDRoleAddCachedIEsToInviteParamsOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_SEND_INVITATION_REQUEST_PARAMETERS@@KPEAPEAU2@PEAK@Z; WFDRoleAddCachedIEsToInviteParamsOidStructure(_WFD_ROLE *,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS *,ulong,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS * *,ulong *)
0x14008952c  mov     ebx, eax
0x14008952e  test    eax, eax
0x140089530  jz      short loc_14008955C
0x140089532  mov     rcx, cs:WPP_GLOBAL_Control
0x140089539  cmp     rcx, rdi
0x14008953c  jz      loc_1400895EC
0x140089542  mov     rcx, [rcx+18h]
0x140089546  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008954d  mov     edx, 0CFh
0x140089552  call    WPP_SF_
0x140089557  jmp     loc_1400895EC
0x14008955c  mov     r9, [rbp+var_8]; void *
0x140089560  mov     r15, r9
0x140089563  test    r9, r9
0x140089566  jnz     short loc_140089570
0x140089568  mov     edx, [rbp+var_14]
0x14008956b  mov     r9, rsi
0x14008956e  jmp     short loc_140089576
0x140089570  mov     edx, [rbp+var_18]
0x140089573  mov     rsi, r15
0x140089576  mov     rcx, [rbp+arg_0]
0x14008957a  mov     r8d, 0E05010Dh; unsigned int
0x140089580  mov     dword ptr [rsp+80h+var_60], edx; unsigned int
0x140089584  mov     edx, 1; unsigned int
0x140089589  mov     al, [rcx+0Ch]
0x14008958c  mov     [r9], al
0x14008958f  movzx   eax, word ptr [rcx+0Eh]
0x140089593  mov     [rsi+2], ax
0x140089597  mov     al, [rcx+0Dh]
0x14008959a  mov     [rsi+1], al
0x14008959d  mov     dword ptr [rsi+0Ch], 2710h
0x1400895a4  mov     al, [rbp+arg_18]
0x1400895a7  mov     [rsi+4], al
0x1400895aa  mov     rax, [rbp+arg_8]
0x1400895ae  mov     rcx, [rax]
0x1400895b1  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400895b5  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400895ba  xor     ebx, ebx
0x1400895bc  cmp     eax, 40230001h
0x1400895c1  cmovnz  ebx, eax
0x1400895c4  test    ebx, ebx
0x1400895c6  jz      short loc_14008963E
0x1400895c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400895cf  cmp     rcx, rdi
0x1400895d2  jz      short loc_1400895EC
0x1400895d4  mov     rcx, [rcx+18h]
0x1400895d8  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400895df  mov     edx, 0D0h
0x1400895e4  mov     r9d, ebx
0x1400895e7  call    WPP_SF_d
0x1400895ec  mov     edi, [rbp+var_1C]
0x1400895ef  test    r12, r12
0x1400895f2  jz      short loc_1400895FE
0x1400895f4  mov     edx, edi; unsigned int
0x1400895f6  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x1400895f9  call    ?WFDDeviceCleanupPeerByID@@YAXPEAU_WFD_DEVICE_ROLE@@K@Z; WFDDeviceCleanupPeerByID(_WFD_DEVICE_ROLE *,ulong)
0x1400895fe  test    r15, r15
0x140089601  jz      loc_1400897F0
0x140089607  lea     rcx, [r15-10h]; P
0x14008960b  mov     rax, [rcx]
0x14008960e  test    rax, rax
0x140089611  jz      short loc_14008962A
0x140089613  mov     rdx, rcx; Entry
0x140089616  mov     rcx, rax; Lookaside
0x140089619  call    cs:__imp_ExFreeToNPagedLookasideList
0x140089620  nop     dword ptr [rax+rax+00h]
0x140089625  jmp     loc_1400897F0
0x14008962a  mov     edx, [rcx+8]; Tag
0x14008962d  call    cs:__imp_ExFreePoolWithTag
0x140089634  nop     dword ptr [rax+rax+00h]
0x140089639  jmp     loc_1400897F0
0x14008963e  lea     rsi, [r13+4A8h]
0x140089645  mov     rcx, rsi; SpinLock
0x140089648  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14008964f  nop     dword ptr [rax+rax+00h]
0x140089654  mov     edx, [rbp+var_1C]; unsigned int
0x140089657  lea     r8, [rbp+var_10]; struct _WFD_PEER_DEVICE **
0x14008965b  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x14008965e  mov     [r13+4B0h], al
0x140089665  call    ?WFDDeviceFindPeerByID@@YAHPEAU_WFD_DEVICE_ROLE@@KPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByID(_WFD_DEVICE_ROLE *,ulong,_WFD_PEER_DEVICE * *)
0x14008966a  test    eax, eax
0x14008966c  jz      short loc_1400896A6
0x14008966e  mov     rcx, cs:WPP_GLOBAL_Control
0x140089675  cmp     rcx, rdi
0x140089678  jz      loc_140089708
0x14008967e  cmp     byte ptr [rcx+29h], 3
0x140089682  jb      loc_140089708
0x140089688  bt      dword ptr [rcx+2Ch], 15h
0x14008968d  jnb     short loc_140089708
0x14008968f  mov     rcx, [rcx+18h]
0x140089693  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008969a  mov     edx, 0D1h
0x14008969f  call    WPP_SF_
0x1400896a4  jmp     short loc_140089708
0x1400896a6  mov     rbx, [rbp+var_10]
0x1400896aa  mov     edx, 1
0x1400896af  mov     rcx, rbx
0x1400896b2  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x1400896b7  test    al, al
0x1400896b9  jnz     short loc_1400896EF
0x1400896bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400896c2  cmp     rcx, rdi
0x1400896c5  jz      short loc_140089708
0x1400896c7  cmp     byte ptr [rcx+29h], 3
0x1400896cb  jb      short loc_140089708
  ... truncated ...
```
