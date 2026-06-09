# ExtSTAOffloadGTKReKey(EXTSTA_VELAN *)

- ea: `0x14006a410`
- end: `0x14006a73b`
- name: `?ExtSTAOffloadGTKReKey@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `811`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400630ac`
- `0x14006319c`
- `0x14006aff4`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140046504`
- `0x14006a324`
- `0x14006a410`
- `0x14006a744`
- `0x14006ae0c`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14006a61a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006a61a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a45b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a6b2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a45b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a6b2`
- `NDIS!NdisReleaseRWLock` at `0x14006a5cb`
- `NDIS!NdisReleaseRWLock` at `0x14006a6dd`
- `NDIS!NdisReleaseRWLock` at `0x14006a5cb`
- `NDIS!NdisReleaseRWLock` at `0x14006a6dd`

## pseudocode

```c
void __fastcall ExtSTAOffloadGTKReKey(struct EXTSTA_VELAN *a1)
{
  _VELAN *pGenVElan; // rcx
  unsigned __int8 v3; // di
  _VELAN *v4; // rcx
  _DOT11_AUTH_ALGORITHM AuthAlgo; // r8d
  _ADAPT *pAdapt; // rax
  int v7; // ecx
  unsigned int v8; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[96]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[256]; // [rsp+A0h] [rbp-60h] BYREF

  LockState.OldIrql = 0;
  pGenVElan = a1->pGenVElan;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockWrite(pGenVElan->pRWLock, &LockState, 0);
  v3 = 0;
  if ( (*(_DWORD *)&a1->RoD & 1) != 0 )
  {
    if ( a1->AssocMgr.uNumAssoc )
    {
      if ( a1->RoD.CurrentBSSType == dot11_BSS_type_infrastructure )
      {
        v4 = a1->pGenVElan;
        if ( v4->pSecurityEndpoint == v4->pMSSecurityEndpoint )
        {
          AuthAlgo = v4->KeyContext.AuthAlgo;
          if ( (unsigned int)(AuthAlgo - 6) <= 5 )
          {
            pAdapt = v4->pAdapt;
            v7 = 0;
            v3 = (pAdapt->PmCapabilities.SupportedProtocolOffloads & 0x80) != 0;
            if ( (pAdapt->PmCapabilities.SupportedWoLPacketPatterns & 0x10000) != 0
              && (((AuthAlgo - 6) & 0xFFFFFFFD) == 0 || AuthAlgo == DOT11_AUTH_ALGO_WPA3_ENT) )
            {
              v7 = 1;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                139,
                WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
                v3,
                v7);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              138,
              WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
              (unsigned int)AuthAlgo);
          }
        }
      }
    }
  }
  if ( (*(_DWORD *)&a1->Rw & 2) == 0 && !a1->pGenVElan->pAdapt->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids);
    v3 = 0;
  }
  memset(v10, 0, 0x58u);
  if ( v3 )
    v3 &= -(Dot11RsnaGetRsnRekeyOffloadState(a1->pGenVElan, (struct DOT11_RSN_REKEY_PARAMETERS *)v10) != 0);
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
        a1->pGenVElan->pAdapt->AdapterEnhancedCapabilities.uWindowsWifiCxVersion != 0);
    if ( KeGetCurrentIrql() )
    {
      ExtSTARequestAsyncRsnRekeyOffload(a1, (struct DOT11_RSN_REKEY_PARAMETERS *)v10);
    }
    else
    {
      memset(v11, 0, sizeof(v11));
      CreateRsnRekeyOffload(a1, (struct DOT11_RSN_REKEY_PARAMETERS *)v10, (struct _NDIS_PM_PROTOCOL_OFFLOAD *)v11);
      v8 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xFD01010D, v11, 0x100u);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, v8);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids,
            *(unsigned int *)&v11[148]);
        NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
        ExtSTAProcessOffloadedGTKProtocol(a1, (struct _NDIS_PM_PROTOCOL_OFFLOAD *)v11);
        NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
      }
    }
  }
}

```

## disassembly

```asm
0x14006a410  push    rbp
0x14006a412  push    rbx
0x14006a413  push    rdi
0x14006a414  push    r14
0x14006a416  lea     rbp, [rsp-0B8h]
0x14006a41e  sub     rsp, 1B8h
0x14006a425  mov     rax, cs:__security_cookie
0x14006a42c  xor     rax, rsp
0x14006a42f  mov     [rbp+0D0h+var_30], rax
0x14006a436  mov     rbx, rcx
0x14006a439  mov     [rsp+1D0h+LockState.OldIrql], 0
0x14006a43e  mov     rcx, [rcx+0A38h]
0x14006a445  lea     rdx, [rsp+1D0h+LockState]; LockState
0x14006a44a  xor     eax, eax
0x14006a44c  xor     r8d, r8d; Flags
0x14006a44f  mov     word ptr [rsp+1D0h+LockState.LockState], ax
0x14006a454  mov     rcx, [rcx+90h]; Lock
0x14006a45b  call    cs:__imp_NdisAcquireRWLockWrite
0x14006a462  nop     dword ptr [rax+rax+00h]
0x14006a467  mov     eax, [rbx+610h]
0x14006a46d  lea     r14, WPP_GLOBAL_Control
0x14006a474  xor     dil, dil
0x14006a477  test    al, 1
0x14006a479  jz      loc_14006A548
0x14006a47f  cmp     dword ptr [rbx+14Ch], 0
0x14006a486  jz      loc_14006A548
0x14006a48c  cmp     dword ptr [rbx+64Ch], 1
0x14006a493  jnz     loc_14006A548
0x14006a499  mov     rcx, [rbx+0A38h]
0x14006a4a0  mov     rax, [rcx+16F0h]
0x14006a4a7  cmp     [rcx+1700h], rax
0x14006a4ae  jnz     loc_14006A548
0x14006a4b4  mov     r8d, [rcx+171Ch]
0x14006a4bb  lea     eax, [r8-6]
0x14006a4bf  cmp     eax, 5
0x14006a4c2  jbe     short loc_14006A4EA
0x14006a4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4cb  cmp     rcx, r14
0x14006a4ce  jz      short loc_14006A548
0x14006a4d0  mov     rcx, [rcx+18h]
0x14006a4d4  mov     r9d, r8d
0x14006a4d7  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14006a4de  mov     edx, 8Ah
0x14006a4e3  call    WPP_SF_d
0x14006a4e8  jmp     short loc_14006A548
0x14006a4ea  mov     rax, [rcx+10h]
0x14006a4ee  xor     ecx, ecx
0x14006a4f0  mov     edi, [rax+3F4h]
0x14006a4f6  shr     edi, 7
0x14006a4f9  and     dil, 1
0x14006a4fd  test    dword ptr [rax+3E0h], 10000h
0x14006a507  jz      short loc_14006A51F
0x14006a509  lea     eax, [r8-6]
0x14006a50d  test    eax, 0FFFFFFFDh
0x14006a512  jz      short loc_14006A51A
0x14006a514  cmp     r8d, 0Bh
0x14006a518  jnz     short loc_14006A51F
0x14006a51a  mov     ecx, 1
0x14006a51f  mov     rax, cs:WPP_GLOBAL_Control
0x14006a526  cmp     rax, r14
0x14006a529  jz      short loc_14006A548
0x14006a52b  mov     [rsp+1D0h+var_1B0], ecx
0x14006a52f  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14006a536  mov     rcx, [rax+18h]
0x14006a53a  mov     edx, 8Bh
0x14006a53f  movzx   r9d, dil
0x14006a543  call    WPP_SF_Dd
0x14006a548  mov     eax, [rbx+6B8h]
0x14006a54e  test    al, 2
0x14006a550  jnz     short loc_14006A58B
0x14006a552  mov     rax, [rbx+0A38h]
0x14006a559  mov     rcx, [rax+10h]
0x14006a55d  cmp     qword ptr [rcx+610h], 0
0x14006a565  jnz     short loc_14006A58B
0x14006a567  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a56e  cmp     rcx, r14
0x14006a571  jz      short loc_14006A588
0x14006a573  mov     rcx, [rcx+18h]
0x14006a577  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a57e  mov     edx, 24h ; '$'
0x14006a583  call    WPP_SF_
0x14006a588  xor     dil, dil
0x14006a58b  xor     edx, edx; Val
0x14006a58d  lea     rcx, [rsp+1D0h+var_190]; void *
0x14006a592  lea     r8d, [rdx+58h]; Size
0x14006a596  call    memset
0x14006a59b  test    dil, dil
0x14006a59e  jz      short loc_14006A5B8
0x14006a5a0  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x14006a5a7  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x14006a5ac  call    ?Dot11RsnaGetRsnRekeyOffloadState@@YAHPEAU_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z; Dot11RsnaGetRsnRekeyOffloadState(_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)
0x14006a5b1  neg     eax
0x14006a5b3  sbb     cl, cl
0x14006a5b5  and     dil, cl
0x14006a5b8  mov     rcx, [rbx+0A38h]
0x14006a5bf  lea     rdx, [rsp+1D0h+LockState]; LockState
0x14006a5c4  mov     rcx, [rcx+90h]; Lock
0x14006a5cb  call    cs:__imp_NdisReleaseRWLock
0x14006a5d2  nop     dword ptr [rax+rax+00h]
0x14006a5d7  test    dil, dil
0x14006a5da  jz      loc_14006A71E
0x14006a5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a5e7  cmp     rcx, r14
0x14006a5ea  jz      short loc_14006A61A
0x14006a5ec  mov     rax, [rbx+0A38h]
0x14006a5f3  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a5fa  mov     rcx, [rcx+18h]
0x14006a5fe  xor     r9d, r9d
0x14006a601  mov     rdx, [rax+10h]
0x14006a605  cmp     [rdx+610h], r9
0x14006a60c  mov     edx, 25h ; '%'
0x14006a611  setnz   r9b
0x14006a615  call    WPP_SF_d
0x14006a61a  call    cs:__imp_KeGetCurrentIrql
0x14006a621  nop     dword ptr [rax+rax+00h]
0x14006a626  test    al, al
0x14006a628  jnz     loc_14006A711
0x14006a62e  mov     edi, 100h
0x14006a633  lea     rcx, [rbp+0D0h+var_130]; void *
0x14006a637  mov     r8d, edi; Size
0x14006a63a  xor     edx, edx; Val
0x14006a63c  call    memset
0x14006a641  lea     r8, [rbp+0D0h+var_130]; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x14006a645  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006a648  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x14006a64d  call    ?CreateRsnRekeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; CreateRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x14006a652  mov     rcx, [rbx+0A38h]
0x14006a659  lea     r9, [rbp+0D0h+var_130]; void *
0x14006a65d  mov     edx, 1; unsigned int
0x14006a662  mov     [rsp+1D0h+var_1B0], edi; unsigned int
0x14006a666  mov     r8d, 0FD01010Dh; unsigned int
0x14006a66c  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006a670  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006a675  test    eax, eax
0x14006a677  jnz     short loc_14006A6EB
0x14006a679  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a680  cmp     rcx, r14
0x14006a683  jz      short loc_14006A69C
0x14006a685  mov     r9d, dword ptr [rbp+0D0h+var_130+94h]
0x14006a689  lea     edx, [rax+26h]
0x14006a68c  mov     rcx, [rcx+18h]
0x14006a690  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a697  call    WPP_SF_d
0x14006a69c  mov     rcx, [rbx+0A38h]
0x14006a6a3  lea     rdx, [rsp+1D0h+LockState]; LockState
0x14006a6a8  xor     r8d, r8d; Flags
0x14006a6ab  mov     rcx, [rcx+90h]; Lock
0x14006a6b2  call    cs:__imp_NdisAcquireRWLockWrite
0x14006a6b9  nop     dword ptr [rax+rax+00h]
0x14006a6be  lea     rdx, [rbp+0D0h+var_130]; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x14006a6c2  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006a6c5  call    ?ExtSTAProcessOffloadedGTKProtocol@@YAXPEAUEXTSTA_VELAN@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; ExtSTAProcessOffloadedGTKProtocol(EXTSTA_VELAN *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x14006a6ca  mov     rcx, [rbx+0A38h]
0x14006a6d1  lea     rdx, [rsp+1D0h+LockState]; LockState
0x14006a6d6  mov     rcx, [rcx+90h]; Lock
0x14006a6dd  call    cs:__imp_NdisReleaseRWLock
0x14006a6e4  nop     dword ptr [rax+rax+00h]
0x14006a6e9  jmp     short loc_14006A71E
0x14006a6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a6f2  cmp     rcx, r14
0x14006a6f5  jz      short loc_14006A71E
0x14006a6f7  mov     rcx, [rcx+18h]
0x14006a6fb  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a702  mov     edx, 27h ; '''
0x14006a707  mov     r9d, eax
0x14006a70a  call    WPP_SF_d
0x14006a70f  jmp     short loc_14006A71E
0x14006a711  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x14006a716  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006a719  call    ?ExtSTARequestAsyncRsnRekeyOffload@@YAHPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z; ExtSTARequestAsyncRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)
0x14006a71e  mov     rcx, [rbp+0D0h+var_30]
0x14006a725  xor     rcx, rsp; StackCookie
0x14006a728  call    __security_check_cookie
0x14006a72d  add     rsp, 1B8h
0x14006a734  pop     r14
0x14006a736  pop     rdi
0x14006a737  pop     rbx
0x14006a738  pop     rbp
0x14006a739  retn
```
