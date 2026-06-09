# ExtSTAOffloadGTKReKey(EXTSTA_VELAN *)

- ea: `0x140068be0`
- end: `0x140068f0b`
- name: `?ExtSTAOffloadGTKReKey@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `811`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14006187c`
- `0x14006196c`
- `0x1400697c4`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140020f20`
- `0x140045984`
- `0x140068af4`
- `0x140068be0`
- `0x140068f14`
- `0x1400695dc`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140068dea`
- `ntoskrnl!KeGetCurrentIrql` at `0x140068dea`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068c2b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068e82`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068c2b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068e82`
- `NDIS!NdisReleaseRWLock` at `0x140068d9b`
- `NDIS!NdisReleaseRWLock` at `0x140068ead`
- `NDIS!NdisReleaseRWLock` at `0x140068d9b`
- `NDIS!NdisReleaseRWLock` at `0x140068ead`

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
                140,
                WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
                v3,
                v7);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              139,
              WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
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
0x140068be0  push    rbp
0x140068be2  push    rbx
0x140068be3  push    rdi
0x140068be4  push    r14
0x140068be6  lea     rbp, [rsp-0B8h]
0x140068bee  sub     rsp, 1B8h
0x140068bf5  mov     rax, cs:__security_cookie
0x140068bfc  xor     rax, rsp
0x140068bff  mov     [rbp+0D0h+var_30], rax
0x140068c06  mov     rbx, rcx
0x140068c09  mov     [rsp+1D0h+LockState.OldIrql], 0
0x140068c0e  mov     rcx, [rcx+0A38h]
0x140068c15  lea     rdx, [rsp+1D0h+LockState]; LockState
0x140068c1a  xor     eax, eax
0x140068c1c  xor     r8d, r8d; Flags
0x140068c1f  mov     word ptr [rsp+1D0h+LockState.LockState], ax
0x140068c24  mov     rcx, [rcx+90h]; Lock
0x140068c2b  call    cs:__imp_NdisAcquireRWLockWrite
0x140068c32  nop     dword ptr [rax+rax+00h]
0x140068c37  mov     eax, [rbx+610h]
0x140068c3d  lea     r14, WPP_GLOBAL_Control
0x140068c44  xor     dil, dil
0x140068c47  test    al, 1
0x140068c49  jz      loc_140068D18
0x140068c4f  cmp     dword ptr [rbx+14Ch], 0
0x140068c56  jz      loc_140068D18
0x140068c5c  cmp     dword ptr [rbx+64Ch], 1
0x140068c63  jnz     loc_140068D18
0x140068c69  mov     rcx, [rbx+0A38h]
0x140068c70  mov     rax, [rcx+16F0h]
0x140068c77  cmp     [rcx+1700h], rax
0x140068c7e  jnz     loc_140068D18
0x140068c84  mov     r8d, [rcx+171Ch]
0x140068c8b  lea     eax, [r8-6]
0x140068c8f  cmp     eax, 5
0x140068c92  jbe     short loc_140068CBA
0x140068c94  mov     rcx, cs:WPP_GLOBAL_Control
0x140068c9b  cmp     rcx, r14
0x140068c9e  jz      short loc_140068D18
0x140068ca0  mov     rcx, [rcx+18h]
0x140068ca4  mov     r9d, r8d
0x140068ca7  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140068cae  mov     edx, 8Bh
0x140068cb3  call    WPP_SF_d
0x140068cb8  jmp     short loc_140068D18
0x140068cba  mov     rax, [rcx+10h]
0x140068cbe  xor     ecx, ecx
0x140068cc0  mov     edi, [rax+3F4h]
0x140068cc6  shr     edi, 7
0x140068cc9  and     dil, 1
0x140068ccd  test    dword ptr [rax+3E0h], 10000h
0x140068cd7  jz      short loc_140068CEF
0x140068cd9  lea     eax, [r8-6]
0x140068cdd  test    eax, 0FFFFFFFDh
0x140068ce2  jz      short loc_140068CEA
0x140068ce4  cmp     r8d, 0Bh
0x140068ce8  jnz     short loc_140068CEF
0x140068cea  mov     ecx, 1
0x140068cef  mov     rax, cs:WPP_GLOBAL_Control
0x140068cf6  cmp     rax, r14
0x140068cf9  jz      short loc_140068D18
0x140068cfb  mov     [rsp+1D0h+var_1B0], ecx
0x140068cff  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140068d06  mov     rcx, [rax+18h]
0x140068d0a  mov     edx, 8Ch
0x140068d0f  movzx   r9d, dil
0x140068d13  call    WPP_SF_Dd
0x140068d18  mov     eax, [rbx+6B8h]
0x140068d1e  test    al, 2
0x140068d20  jnz     short loc_140068D5B
0x140068d22  mov     rax, [rbx+0A38h]
0x140068d29  mov     rcx, [rax+10h]
0x140068d2d  cmp     qword ptr [rcx+610h], 0
0x140068d35  jnz     short loc_140068D5B
0x140068d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140068d3e  cmp     rcx, r14
0x140068d41  jz      short loc_140068D58
0x140068d43  mov     rcx, [rcx+18h]
0x140068d47  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140068d4e  mov     edx, 24h ; '$'
0x140068d53  call    WPP_SF_
0x140068d58  xor     dil, dil
0x140068d5b  xor     edx, edx; Val
0x140068d5d  lea     rcx, [rsp+1D0h+var_190]; void *
0x140068d62  lea     r8d, [rdx+58h]; Size
0x140068d66  call    memset
0x140068d6b  test    dil, dil
0x140068d6e  jz      short loc_140068D88
0x140068d70  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x140068d77  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x140068d7c  call    ?Dot11RsnaGetRsnRekeyOffloadState@@YAHPEAU_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z; Dot11RsnaGetRsnRekeyOffloadState(_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)
0x140068d81  neg     eax
0x140068d83  sbb     cl, cl
0x140068d85  and     dil, cl
0x140068d88  mov     rcx, [rbx+0A38h]
0x140068d8f  lea     rdx, [rsp+1D0h+LockState]; LockState
0x140068d94  mov     rcx, [rcx+90h]; Lock
0x140068d9b  call    cs:__imp_NdisReleaseRWLock
0x140068da2  nop     dword ptr [rax+rax+00h]
0x140068da7  test    dil, dil
0x140068daa  jz      loc_140068EEE
0x140068db0  mov     rcx, cs:WPP_GLOBAL_Control
0x140068db7  cmp     rcx, r14
0x140068dba  jz      short loc_140068DEA
0x140068dbc  mov     rax, [rbx+0A38h]
0x140068dc3  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140068dca  mov     rcx, [rcx+18h]
0x140068dce  xor     r9d, r9d
0x140068dd1  mov     rdx, [rax+10h]
0x140068dd5  cmp     [rdx+610h], r9
0x140068ddc  mov     edx, 25h ; '%'
0x140068de1  setnz   r9b
0x140068de5  call    WPP_SF_d
0x140068dea  call    cs:__imp_KeGetCurrentIrql
0x140068df1  nop     dword ptr [rax+rax+00h]
0x140068df6  test    al, al
0x140068df8  jnz     loc_140068EE1
0x140068dfe  mov     edi, 100h
0x140068e03  lea     rcx, [rbp+0D0h+var_130]; void *
0x140068e07  mov     r8d, edi; Size
0x140068e0a  xor     edx, edx; Val
0x140068e0c  call    memset
0x140068e11  lea     r8, [rbp+0D0h+var_130]; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x140068e15  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140068e18  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x140068e1d  call    ?CreateRsnRekeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; CreateRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x140068e22  mov     rcx, [rbx+0A38h]
0x140068e29  lea     r9, [rbp+0D0h+var_130]; void *
0x140068e2d  mov     edx, 1; unsigned int
0x140068e32  mov     [rsp+1D0h+var_1B0], edi; unsigned int
0x140068e36  mov     r8d, 0FD01010Dh; unsigned int
0x140068e3c  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140068e40  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140068e45  test    eax, eax
0x140068e47  jnz     short loc_140068EBB
0x140068e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e50  cmp     rcx, r14
0x140068e53  jz      short loc_140068E6C
0x140068e55  mov     r9d, dword ptr [rbp+0D0h+var_130+94h]
0x140068e59  lea     edx, [rax+26h]
0x140068e5c  mov     rcx, [rcx+18h]
0x140068e60  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140068e67  call    WPP_SF_d
0x140068e6c  mov     rcx, [rbx+0A38h]
0x140068e73  lea     rdx, [rsp+1D0h+LockState]; LockState
0x140068e78  xor     r8d, r8d; Flags
0x140068e7b  mov     rcx, [rcx+90h]; Lock
0x140068e82  call    cs:__imp_NdisAcquireRWLockWrite
0x140068e89  nop     dword ptr [rax+rax+00h]
0x140068e8e  lea     rdx, [rbp+0D0h+var_130]; struct _NDIS_PM_PROTOCOL_OFFLOAD *
0x140068e92  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140068e95  call    ?ExtSTAProcessOffloadedGTKProtocol@@YAXPEAUEXTSTA_VELAN@@PEAU_NDIS_PM_PROTOCOL_OFFLOAD@@@Z; ExtSTAProcessOffloadedGTKProtocol(EXTSTA_VELAN *,_NDIS_PM_PROTOCOL_OFFLOAD *)
0x140068e9a  mov     rcx, [rbx+0A38h]
0x140068ea1  lea     rdx, [rsp+1D0h+LockState]; LockState
0x140068ea6  mov     rcx, [rcx+90h]; Lock
0x140068ead  call    cs:__imp_NdisReleaseRWLock
0x140068eb4  nop     dword ptr [rax+rax+00h]
0x140068eb9  jmp     short loc_140068EEE
0x140068ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ec2  cmp     rcx, r14
0x140068ec5  jz      short loc_140068EEE
0x140068ec7  mov     rcx, [rcx+18h]
0x140068ecb  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140068ed2  mov     edx, 27h ; '''
0x140068ed7  mov     r9d, eax
0x140068eda  call    WPP_SF_d
0x140068edf  jmp     short loc_140068EEE
0x140068ee1  lea     rdx, [rsp+1D0h+var_190]; struct DOT11_RSN_REKEY_PARAMETERS *
0x140068ee6  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140068ee9  call    ?ExtSTARequestAsyncRsnRekeyOffload@@YAHPEAUEXTSTA_VELAN@@PEAUDOT11_RSN_REKEY_PARAMETERS@@@Z; ExtSTARequestAsyncRsnRekeyOffload(EXTSTA_VELAN *,DOT11_RSN_REKEY_PARAMETERS *)
0x140068eee  mov     rcx, [rbp+0D0h+var_30]
0x140068ef5  xor     rcx, rsp; StackCookie
0x140068ef8  call    __security_check_cookie
0x140068efd  add     rsp, 1B8h
0x140068f04  pop     r14
0x140068f06  pop     rdi
0x140068f07  pop     rbx
0x140068f08  pop     rbp
0x140068f09  retn
```
