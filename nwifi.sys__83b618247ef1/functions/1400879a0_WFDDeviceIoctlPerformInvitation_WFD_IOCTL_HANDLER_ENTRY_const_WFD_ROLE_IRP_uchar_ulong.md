# WFDDeviceIoctlPerformInvitation(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x1400879a0`
- end: `0x140087fde`
- name: `?WFDDeviceIoctlPerformInvitation@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `1598`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140015b1c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400311f8`
- `0x14003d814`
- `0x1400790cc`
- `0x14007f384`
- `0x14007f5a0`
- `0x14007f5cc`
- `0x1400879a0`
- `0x14008a7d0`
- `0x14008ae64`
- `0x14008af58`
- `0x14008d658`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087de9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087f05`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087de9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087f05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087dfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087dfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140087f16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087c49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087ccb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087ee2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087c49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087ccb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087ee2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087ba2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087e18`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087ba2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140087e18`

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
0x1400879a0  mov     [rsp-38h+arg_10], rbx
0x1400879a5  mov     [rsp-38h+arg_8], rdx
0x1400879aa  mov     [rsp-38h+arg_0], rcx
0x1400879af  push    rbp
0x1400879b0  push    rsi
0x1400879b1  push    rdi
0x1400879b2  push    r12
0x1400879b4  push    r13
0x1400879b6  push    r14
0x1400879b8  push    r15
0x1400879ba  mov     rbp, rsp
0x1400879bd  sub     rsp, 80h
0x1400879c4  mov     r8d, [rbp+arg_20]
0x1400879c8  mov     r10, rdx
0x1400879cb  xor     edx, edx
0x1400879cd  mov     r12, r9
0x1400879d0  mov     [rbp+var_10], rdx
0x1400879d4  mov     [rbp+arg_18], dl
0x1400879d7  mov     [rbp+var_8], rdx
0x1400879db  mov     [rbp+var_18], edx
0x1400879de  test    r9, r9
0x1400879e1  jz      loc_140087F7C
0x1400879e7  cmp     r8d, 60h ; '`'
0x1400879eb  jb      loc_140087F7C
0x1400879f1  lea     rsi, [r9+8]
0x1400879f5  mov     r15d, [rsi+54h]
0x1400879f9  test    r15d, r15d
0x1400879fc  jz      short loc_140087A0A
0x1400879fe  mov     ecx, [rsi+50h]
0x140087a01  cmp     ecx, 58h ; 'X'
0x140087a04  jb      loc_140087F29
0x140087a0a  mov     ecx, [rsi+50h]
0x140087a0d  lea     eax, [rcx+r15]
0x140087a11  cmp     eax, ecx
0x140087a13  jb      loc_140087F29
0x140087a19  cmp     eax, r8d
0x140087a1c  ja      loc_140087F29
0x140087a22  mov     al, [rsi+4Ch]
0x140087a25  mov     [rbp+var_20], al
0x140087a28  test    al, al
0x140087a2a  jz      loc_140087B5B
0x140087a30  cmp     [rsi+19h], dl
0x140087a33  jnz     short loc_140087A6B
0x140087a35  mov     ebx, 0C0010015h
0x140087a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140087a41  lea     rdi, WPP_GLOBAL_Control
0x140087a48  cmp     rcx, rdi
0x140087a4b  jz      loc_140087FC0
0x140087a51  mov     edx, 0C9h
0x140087a56  mov     rcx, [rcx+18h]
0x140087a5a  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087a61  call    WPP_SF_
0x140087a66  jmp     loc_140087FC0
0x140087a6b  lea     r9, [rsi+12h]
0x140087a6f  mov     rbx, cs:WPP_GLOBAL_Control
0x140087a76  lea     rdi, WPP_GLOBAL_Control
0x140087a7d  mov     r13, [r10+0B8h]
0x140087a84  cmp     rbx, rdi
0x140087a87  jz      short loc_140087B03
0x140087a89  cmp     byte ptr [rbx+29h], 3
0x140087a8d  jb      short loc_140087B03
0x140087a8f  bt      dword ptr [rbx+2Ch], 15h
0x140087a94  jnb     short loc_140087B03
0x140087a96  cmp     [rbp+var_20], 0
0x140087a9a  lea     r11, [rsi+20h]
0x140087a9e  lea     rax, aGo; "GO"
0x140087aa5  lea     r8, [r11+8]
0x140087aa9  lea     r10, [rsi+5]
0x140087aad  lea     rdx, aClient; "CLIENT"
0x140087ab4  cmovz   rdx, rax
0x140087ab8  test    byte ptr [r9], 1
0x140087abc  lea     rax, aJoin; "JOIN"
0x140087ac3  lea     r9, aReinvoke; "REINVOKE"
0x140087aca  cmovz   r9, rax
0x140087ace  mov     rax, [r12]
0x140087ad2  mov     [rsp+80h+var_30], rax
0x140087ad7  mov     [rsp+80h+var_38], r15d
0x140087adc  mov     [rsp+80h+var_40], ecx
0x140087ae0  mov     rcx, [rbx+18h]
0x140087ae4  mov     [rsp+80h+var_48], r8
0x140087ae9  mov     [rsp+80h+var_50], r11
0x140087aee  mov     [rsp+80h+var_58], r10
0x140087af3  mov     [rsp+80h+var_60], rdx
0x140087af8  call    WPP_SF_ss_MAC__MAC__SSID_DDq
0x140087afd  mov     r10, [rbp+arg_8]
0x140087b01  xor     edx, edx
0x140087b03  mov     rcx, [r10]
0x140087b06  lea     r8, [rbp+arg_18]; void *
0x140087b0a  mov     [rsp+80h+var_58], rdx; unsigned int *
0x140087b0f  mov     r9d, 1; unsigned int
0x140087b15  mov     [rsp+80h+var_60], rdx; unsigned int *
0x140087b1a  mov     edx, 0E050111h; unsigned int
0x140087b1f  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140087b23  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140087b28  mov     ebx, eax
0x140087b2a  test    eax, eax
0x140087b2c  jz      short loc_140087B98
0x140087b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140087b35  cmp     rcx, rdi
0x140087b38  jz      loc_140087FC0
0x140087b3e  mov     rcx, [rcx+18h]
0x140087b42  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087b49  mov     edx, 0CCh
0x140087b4e  mov     r9d, eax
0x140087b51  call    WPP_SF_d
0x140087b56  jmp     loc_140087FC0
0x140087b5b  lea     r9, [rsi+12h]
0x140087b5f  test    byte ptr [r9], 1
0x140087b63  jnz     loc_140087A6F
0x140087b69  cmp     [rsi+19h], dl
0x140087b6c  jnz     loc_140087A6F
0x140087b72  mov     ebx, 0C0010015h
0x140087b77  mov     rcx, cs:WPP_GLOBAL_Control
0x140087b7e  lea     rdi, WPP_GLOBAL_Control
0x140087b85  cmp     rcx, rdi
0x140087b88  jz      loc_140087FC0
0x140087b8e  mov     edx, 0CAh
0x140087b93  jmp     loc_140087A56
0x140087b98  lea     rcx, [r13+4A8h]; SpinLock
0x140087b9f  xor     r15d, r15d
0x140087ba2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140087ba9  nop     dword ptr [rax+rax+00h]
0x140087bae  lea     rdx, [rsi+5]; unsigned __int8 (*)[6]
0x140087bb2  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140087bb5  lea     r8, [rbp+var_10]; struct _WFD_PEER_DEVICE **
0x140087bb9  mov     [r13+4B0h], al
0x140087bc0  call    ?WFDDeviceFindPeerByMAC@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByMAC(_WFD_DEVICE_ROLE *,uchar (*)[6],_WFD_PEER_DEVICE * *)
0x140087bc5  test    eax, eax
0x140087bc7  jnz     short loc_140087BF4
0x140087bc9  xor     r12d, r12d
0x140087bcc  mov     ebx, 40010011h
0x140087bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140087bd8  cmp     rcx, rdi
0x140087bdb  jz      short loc_140087C3A
0x140087bdd  mov     rcx, [rcx+18h]
0x140087be1  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087be8  mov     edx, 0CDh
0x140087bed  call    WPP_SF_
0x140087bf2  jmp     short loc_140087C3A
0x140087bf4  mov     r8, [r12]
0x140087bf8  lea     rax, [rbp+var_10]
0x140087bfc  xor     r9d, r9d
0x140087bff  mov     [rsp+80h+var_60], rax
0x140087c04  mov     rcx, r13
0x140087c07  call    ?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z; WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)
0x140087c0c  mov     ebx, eax
0x140087c0e  test    eax, eax
0x140087c10  jz      short loc_140087C5A
0x140087c12  mov     rcx, cs:WPP_GLOBAL_Control
0x140087c19  cmp     rcx, rdi
0x140087c1c  jz      short loc_140087C36
0x140087c1e  mov     rcx, [rcx+18h]
0x140087c22  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087c29  mov     edx, 0CEh
0x140087c2e  mov     r9d, eax
0x140087c31  call    WPP_SF_d
0x140087c36  mov     r12, [rbp+var_10]
0x140087c3a  lea     rax, [r13+4A8h]
0x140087c41  xor     edi, edi
0x140087c43  mov     dl, [rax+8]; NewIrql
0x140087c46  mov     rcx, rax; SpinLock
0x140087c49  call    cs:__imp_KeReleaseSpinLock
0x140087c50  nop     dword ptr [rax+rax+00h]
0x140087c55  jmp     loc_140087DBF
0x140087c5a  movups  xmm0, xmmword ptr [rsi]
0x140087c5d  mov     r12, [rbp+var_10]
0x140087c61  lea     rcx, [r13+4A8h]; SpinLock
0x140087c68  movups  xmmword ptr [r12+1C0h], xmm0
0x140087c71  movups  xmm1, xmmword ptr [rsi+10h]
0x140087c75  movups  xmmword ptr [r12+1D0h], xmm1
0x140087c7e  movups  xmm0, xmmword ptr [rsi+20h]
0x140087c82  movups  xmmword ptr [r12+1E0h], xmm0
0x140087c8b  movups  xmm1, xmmword ptr [rsi+30h]
0x140087c8f  movups  xmmword ptr [r12+1F0h], xmm1
0x140087c98  movups  xmm0, xmmword ptr [rsi+40h]
0x140087c9c  movups  xmmword ptr [r12+200h], xmm0
0x140087ca5  movsd   xmm1, qword ptr [rsi+50h]
0x140087caa  movsd   qword ptr [r12+210h], xmm1
0x140087cb4  mov     eax, [r12+38h]
0x140087cb9  mov     [rbp+var_1C], eax
0x140087cbc  mov     al, [rbp+arg_18]
0x140087cbf  mov     [r12+28h], al
0x140087cc4  mov     dl, [r13+4B0h]; NewIrql
0x140087ccb  call    cs:__imp_KeReleaseSpinLock
0x140087cd2  nop     dword ptr [rax+rax+00h]
0x140087cd7  mov     eax, [rbp+arg_20]
0x140087cda  lea     rcx, [rbp+var_18]
0x140087cde  add     eax, 0FFFFFFF8h
0x140087ce1  mov     [rsp+80h+var_60], rcx; unsigned int *
0x140087ce6  mov     rcx, [rbp+arg_8]; struct _WFD_ROLE *
0x140087cea  lea     r9, [rbp+var_8]; struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **
0x140087cee  mov     r8d, eax; unsigned int
0x140087cf1  mov     [rbp+var_14], eax
0x140087cf4  mov     rdx, rsi; struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *
0x140087cf7  call    ?WFDRoleAddCachedIEsToInviteParamsOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_SEND_INVITATION_REQUEST_PARAMETERS@@KPEAPEAU2@PEAK@Z; WFDRoleAddCachedIEsToInviteParamsOidStructure(_WFD_ROLE *,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS *,ulong,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS * *,ulong *)
0x140087cfc  mov     ebx, eax
0x140087cfe  test    eax, eax
0x140087d00  jz      short loc_140087D2C
0x140087d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140087d09  cmp     rcx, rdi
0x140087d0c  jz      loc_140087DBC
0x140087d12  mov     rcx, [rcx+18h]
0x140087d16  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087d1d  mov     edx, 0CFh
0x140087d22  call    WPP_SF_
0x140087d27  jmp     loc_140087DBC
0x140087d2c  mov     r9, [rbp+var_8]; void *
0x140087d30  mov     r15, r9
0x140087d33  test    r9, r9
0x140087d36  jnz     short loc_140087D40
0x140087d38  mov     edx, [rbp+var_14]
0x140087d3b  mov     r9, rsi
0x140087d3e  jmp     short loc_140087D46
0x140087d40  mov     edx, [rbp+var_18]
0x140087d43  mov     rsi, r15
0x140087d46  mov     rcx, [rbp+arg_0]
0x140087d4a  mov     r8d, 0E05010Dh; unsigned int
0x140087d50  mov     dword ptr [rsp+80h+var_60], edx; unsigned int
0x140087d54  mov     edx, 1; unsigned int
0x140087d59  mov     al, [rcx+0Ch]
0x140087d5c  mov     [r9], al
0x140087d5f  movzx   eax, word ptr [rcx+0Eh]
0x140087d63  mov     [rsi+2], ax
0x140087d67  mov     al, [rcx+0Dh]
0x140087d6a  mov     [rsi+1], al
0x140087d6d  mov     dword ptr [rsi+0Ch], 2710h
0x140087d74  mov     al, [rbp+arg_18]
0x140087d77  mov     [rsi+4], al
0x140087d7a  mov     rax, [rbp+arg_8]
0x140087d7e  mov     rcx, [rax]
0x140087d81  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140087d85  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140087d8a  xor     ebx, ebx
0x140087d8c  cmp     eax, 40230001h
0x140087d91  cmovnz  ebx, eax
0x140087d94  test    ebx, ebx
0x140087d96  jz      short loc_140087E0E
0x140087d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140087d9f  cmp     rcx, rdi
0x140087da2  jz      short loc_140087DBC
0x140087da4  mov     rcx, [rcx+18h]
0x140087da8  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087daf  mov     edx, 0D0h
0x140087db4  mov     r9d, ebx
0x140087db7  call    WPP_SF_d
0x140087dbc  mov     edi, [rbp+var_1C]
0x140087dbf  test    r12, r12
0x140087dc2  jz      short loc_140087DCE
0x140087dc4  mov     edx, edi; unsigned int
0x140087dc6  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140087dc9  call    ?WFDDeviceCleanupPeerByID@@YAXPEAU_WFD_DEVICE_ROLE@@K@Z; WFDDeviceCleanupPeerByID(_WFD_DEVICE_ROLE *,ulong)
0x140087dce  test    r15, r15
0x140087dd1  jz      loc_140087FC0
0x140087dd7  lea     rcx, [r15-10h]; P
0x140087ddb  mov     rax, [rcx]
0x140087dde  test    rax, rax
0x140087de1  jz      short loc_140087DFA
0x140087de3  mov     rdx, rcx; Entry
0x140087de6  mov     rcx, rax; Lookaside
0x140087de9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140087df0  nop     dword ptr [rax+rax+00h]
0x140087df5  jmp     loc_140087FC0
0x140087dfa  mov     edx, [rcx+8]; Tag
0x140087dfd  call    cs:__imp_ExFreePoolWithTag
0x140087e04  nop     dword ptr [rax+rax+00h]
0x140087e09  jmp     loc_140087FC0
0x140087e0e  lea     rsi, [r13+4A8h]
0x140087e15  mov     rcx, rsi; SpinLock
0x140087e18  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140087e1f  nop     dword ptr [rax+rax+00h]
0x140087e24  mov     edx, [rbp+var_1C]; unsigned int
0x140087e27  lea     r8, [rbp+var_10]; struct _WFD_PEER_DEVICE **
0x140087e2b  mov     rcx, r13; struct _WFD_DEVICE_ROLE *
0x140087e2e  mov     [r13+4B0h], al
0x140087e35  call    ?WFDDeviceFindPeerByID@@YAHPEAU_WFD_DEVICE_ROLE@@KPEAPEAU_WFD_PEER_DEVICE@@@Z; WFDDeviceFindPeerByID(_WFD_DEVICE_ROLE *,ulong,_WFD_PEER_DEVICE * *)
0x140087e3a  test    eax, eax
0x140087e3c  jz      short loc_140087E76
0x140087e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140087e45  cmp     rcx, rdi
0x140087e48  jz      loc_140087ED8
0x140087e4e  cmp     byte ptr [rcx+29h], 3
0x140087e52  jb      loc_140087ED8
0x140087e58  bt      dword ptr [rcx+2Ch], 15h
0x140087e5d  jnb     short loc_140087ED8
0x140087e5f  mov     rcx, [rcx+18h]
0x140087e63  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140087e6a  mov     edx, 0D1h
0x140087e6f  call    WPP_SF_
0x140087e74  jmp     short loc_140087ED8
0x140087e76  mov     rbx, [rbp+var_10]
0x140087e7a  mov     edx, 1
0x140087e7f  mov     rcx, rbx
0x140087e82  call    ?WFDPeerDeviceSetState@@YAEPEAU_WFD_PEER_DEVICE@@W4WFD_PEER_PAIRING_STATE@@@Z; WFDPeerDeviceSetState(_WFD_PEER_DEVICE *,WFD_PEER_PAIRING_STATE)
0x140087e87  test    al, al
0x140087e89  jnz     short loc_140087EBF
0x140087e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140087e92  cmp     rcx, rdi
0x140087e95  jz      short loc_140087ED8
0x140087e97  cmp     byte ptr [rcx+29h], 3
0x140087e9b  jb      short loc_140087ED8
  ... truncated ...
```
