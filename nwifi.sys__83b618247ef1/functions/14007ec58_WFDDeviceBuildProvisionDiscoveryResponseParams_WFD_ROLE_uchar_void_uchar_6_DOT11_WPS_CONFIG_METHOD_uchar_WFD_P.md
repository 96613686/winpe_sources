# WFDDeviceBuildProvisionDiscoveryResponseParams(_WFD_ROLE *,uchar,void *,uchar (*)[6],_DOT11_WPS_CONFIG_METHOD,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 * *)

- ea: `0x14007ec58`
- end: `0x14007f109`
- name: `?WFDDeviceBuildProvisionDiscoveryResponseParams@@YAHPEAU_WFD_ROLE@@EPEAXPEAY05EW4_DOT11_WPS_CONFIG_METHOD@@EPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@EPEAPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z`
- size: `1201`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, char, void *, unsigned __int8 (*)[6], enum _DOT11_WPS_CONFIG_METHOD, unsigned __int8, struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *, char, struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007e374`
- `0x14008538c`

## callees

- `0x14000d22c`
- `0x14002ffb4`
- `0x14007a08c`
- `0x14007a384`
- `0x14007ec58`
- `0x140098ffc`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ec9a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ecfc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ee42`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ec9a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ecfc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ee42`
- `ntoskrnl!ExAllocatePool2` at `0x14007ee5a`
- `ntoskrnl!ExAllocatePool2` at `0x14007ee5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f012`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f043`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f09e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f012`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f043`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007f09e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f023`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f023`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f0b3`
- `NDIS!NdisReleaseRWLock` at `0x14007ef98`
- `NDIS!NdisReleaseRWLock` at `0x14007efef`
- `NDIS!NdisReleaseRWLock` at `0x14007ef98`
- `NDIS!NdisReleaseRWLock` at `0x14007efef`
- `NDIS!NdisAcquireRWLockRead` at `0x14007ed7e`
- `NDIS!NdisAcquireRWLockRead` at `0x14007ed7e`

## pseudocode

```c
__int64 __fastcall WFDDeviceBuildProvisionDiscoveryResponseParams(
        struct _WFD_ROLE *a1,
        char a2,
        void *a3,
        unsigned __int8 (*a4)[6],
        enum _DOT11_WPS_CONFIG_METHOD a5,
        unsigned __int8 a6,
        struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *a7,
        char a8,
        struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 **a9)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *v11; // rax
  PNPAGED_LOOKASIDE_LIST *v12; // r14
  _DWORD *v13; // rbx
  PNPAGED_LOOKASIDE_LIST *v14; // rax
  PNPAGED_LOOKASIDE_LIST *v15; // r15
  unsigned int CachedFrameIEs; // ebx
  char *v17; // rdi
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // r12d
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // eax
  _DWORD *Pool2; // rax
  size_t v25; // r8
  __int64 v26; // rsi
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-Ch] BYREF
  unsigned int v30; // [rsp+38h] [rbp-8h] BYREF
  size_t Size; // [rsp+3Ch] [rbp-4h]

  v30 = 0;
  LockState.OldIrql = 0;
  p_WaitListHead = &Lookaside;
  *(_WORD *)&LockState.LockState = 0;
  v11 = ExAllocateFromNPagedLookasideList(&Lookaside);
  v12 = (PNPAGED_LOOKASIDE_LIST *)v11;
  if ( v11 )
  {
    v13 = v11 + 4;
    *(_QWORD *)v11 = &Lookaside;
    v11[2] = 808679286;
    memset(v11 + 4, 0, 0x208u);
    *v13 = 2;
    v13[2] = a5;
    v13[1] = 524296;
    v13[3] |= 1u;
    v13[4] = 32;
    v29 = 256;
    v14 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&Lookaside);
    v15 = v14;
    if ( !v14 )
    {
      CachedFrameIEs = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 266, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_46;
    }
    *v14 = &Lookaside;
    *((_DWORD *)v14 + 2) = 808679286;
    memset(v14 + 2, 0, 0x100u);
    if ( !(unsigned __int8)WcnGenerateWpsIe(v13, &v29, v15 + 2) )
    {
      CachedFrameIEs = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 267, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_40;
    }
    v17 = 0;
    NdisAcquireRWLockRead(a1->pRWLock, &LockState, 0);
    CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, MANAGEMENT_FRAME_TYPE_PROVISION_DISCOVERY_RESPONSE, &v30, 0);
    if ( CachedFrameIEs )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_36;
      v19 = 268;
      goto LABEL_9;
    }
    v20 = v30;
    v21 = v29 + 320;
    if ( v29 + 320 < 0x140 || (v22 = v21 + v30, LODWORD(Size) = v21 + v30, v21 + v30 < v21) )
    {
      CachedFrameIEs = -2147483643;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          269,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          320,
          v29,
          v30);
      goto LABEL_36;
    }
    v23 = v22 + 16;
    if ( v22 >= 0xFFFFFFF0 )
      goto LABEL_23;
    if ( v23 > 0x40 )
    {
      if ( v23 > 0x100 )
      {
        if ( v23 > 0x400 )
        {
          if ( v23 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v23, 808679286, 320);
LABEL_22:
            if ( Pool2 )
            {
              v25 = (unsigned int)Size;
              v17 = (char *)(Pool2 + 4);
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 808679286;
              CachedFrameIEs = 0;
              memset(Pool2 + 4, 0, v25);
              v17[10] = a2;
              *((_QWORD *)v17 + 2) = a3;
              *(_DWORD *)v17 = 2621824;
              *((_DWORD *)v17 + 6) = 1000;
              *((_DWORD *)v17 + 1) = *(_DWORD *)a4;
              v26 = v29;
              *((_WORD *)v17 + 4) = *(_WORD *)&(*a4)[4];
              *((_DWORD *)v17 + 7) = 320;
              *((_DWORD *)v17 + 8) = v20 + v26;
              memmove(v17 + 320, v15 + 2, (unsigned int)v26);
              if ( v20
                && (CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                       a1,
                                       MANAGEMENT_FRAME_TYPE_PROVISION_DISCOVERY_RESPONSE,
                                       &v30,
                                       (unsigned __int8 *)&v17[*((unsigned int *)v17 + 7) + v26])) != 0 )
              {
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  v19 = 271;
                  goto LABEL_9;
                }
              }
              else
              {
                if ( !*((_DWORD *)a7 + 16)
                  || (CachedFrameIEs = WFDRoleHandleIncomingServiceSessionRequest(
                                         a1,
                                         a5,
                                         a6,
                                         a8,
                                         a7,
                                         (struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)v17)) == 0 )
                {
                  NdisReleaseRWLock(a1->pRWLock, &LockState);
                  *a9 = (struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)v17;
LABEL_40:
                  if ( v15 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
                  {
                    if ( *v15 )
                      ExFreeToNPagedLookasideList(*v15, v15);
                    else
                      ExFreePoolWithTag(v15, *((_DWORD *)v15 + 2));
                  }
LABEL_46:
                  if ( *v12 )
                    ExFreeToNPagedLookasideList(*v12, v12);
                  else
                    ExFreePoolWithTag(v12, *((_DWORD *)v12 + 2));
                  return CachedFrameIEs;
                }
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  v19 = 272;
                  goto LABEL_9;
                }
              }
LABEL_36:
              NdisReleaseRWLock(a1->pRWLock, &LockState);
              if ( v17 )
              {
                if ( *((_QWORD *)v17 - 2) )
                  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v17 - 2), v17 - 16);
                else
                  ExFreePoolWithTag(v17 - 16, *((_DWORD *)v17 - 2));
              }
              goto LABEL_40;
            }
LABEL_23:
            CachedFrameIEs = -1073741670;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              v19 = 270;
LABEL_9:
              WPP_SF_(v18->AttachedDevice, v19, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
              goto LABEL_36;
            }
            goto LABEL_36;
          }
          p_WaitListHead = &stru_1400B0180;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_22;
  }
  CachedFrameIEs = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 265, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x14007ec58  mov     rax, rsp
0x14007ec5b  mov     [rax+8], rbx
0x14007ec5f  mov     [rax+20h], r9
0x14007ec63  mov     [rax+18h], r8
0x14007ec67  mov     [rax+10h], dl
0x14007ec6a  push    rbp
0x14007ec6b  push    rsi
0x14007ec6c  push    rdi
0x14007ec6d  push    r12
0x14007ec6f  push    r13
0x14007ec71  push    r14
0x14007ec73  push    r15
0x14007ec75  mov     rbp, rsp
0x14007ec78  sub     rsp, 40h
0x14007ec7c  mov     r13, rcx
0x14007ec7f  mov     dword ptr [rbp+var_C+4], 0
0x14007ec86  xor     eax, eax
0x14007ec88  mov     [rbp+LockState.OldIrql], 0
0x14007ec8c  lea     rsi, Lookaside
0x14007ec93  mov     word ptr [rbp+LockState.LockState], ax
0x14007ec97  mov     rcx, rsi; Lookaside
0x14007ec9a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007eca1  nop     dword ptr [rax+rax+00h]
0x14007eca6  mov     r14, rax
0x14007eca9  test    rax, rax
0x14007ecac  jz      loc_14007F0C1
0x14007ecb2  lea     rbx, [rax+10h]
0x14007ecb6  mov     [rax], rsi
0x14007ecb9  mov     r12d, 30337776h
0x14007ecbf  mov     rcx, rbx; void *
0x14007ecc2  xor     edx, edx; Val
0x14007ecc4  mov     [rax+8], r12d
0x14007ecc8  mov     r8d, 208h; Size
0x14007ecce  call    memset
0x14007ecd3  mov     eax, [rbp+arg_20]
0x14007ecd6  mov     edi, 100h
0x14007ecdb  mov     dword ptr [rbx], 2
0x14007ece1  mov     rcx, rsi; Lookaside
0x14007ece4  mov     [rbx+8], eax
0x14007ece7  mov     dword ptr [rbx+4], 80008h
0x14007ecee  or      dword ptr [rbx+0Ch], 1
0x14007ecf2  mov     dword ptr [rbx+10h], 20h ; ' '
0x14007ecf9  mov     dword ptr [rbp+var_C], edi
0x14007ecfc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007ed03  nop     dword ptr [rax+rax+00h]
0x14007ed08  mov     r15, rax
0x14007ed0b  test    rax, rax
0x14007ed0e  jz      loc_14007F066
0x14007ed14  mov     r8d, edi; Size
0x14007ed17  mov     [rax], rsi
0x14007ed1a  xor     edx, edx; Val
0x14007ed1c  mov     [rax+8], r12d
0x14007ed20  lea     rcx, [rax+10h]; void *
0x14007ed24  call    memset
0x14007ed29  lea     r8, [r15+10h]
0x14007ed2d  mov     rcx, rbx
0x14007ed30  lea     rdx, [rbp+var_C]
0x14007ed34  call    WcnGenerateWpsIe
0x14007ed39  test    al, al
0x14007ed3b  jnz     short loc_14007ED71
0x14007ed3d  mov     ebx, 0C0000001h
0x14007ed42  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed49  lea     rax, WPP_GLOBAL_Control
0x14007ed50  cmp     rcx, rax
0x14007ed53  jz      loc_14007F02F
0x14007ed59  mov     rcx, [rcx+18h]
0x14007ed5d  lea     edx, [rdi+0Bh]
0x14007ed60  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007ed67  call    WPP_SF_
0x14007ed6c  jmp     loc_14007F02F
0x14007ed71  mov     rcx, [r13+20h]; Lock
0x14007ed75  lea     rdx, [rbp+LockState]; LockState
0x14007ed79  xor     r8d, r8d; Flags
0x14007ed7c  xor     edi, edi
0x14007ed7e  call    cs:__imp_NdisAcquireRWLockRead
0x14007ed85  nop     dword ptr [rax+rax+00h]
0x14007ed8a  xor     r9d, r9d; unsigned __int8 *
0x14007ed8d  lea     r8, [rbp+var_C+4]; unsigned int *
0x14007ed91  lea     edx, [rdi+0Bh]; enum MANAGEMENT_FRAME_TYPE
0x14007ed94  mov     rcx, r13; struct _WFD_ROLE *
0x14007ed97  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007ed9c  mov     ebx, eax
0x14007ed9e  test    eax, eax
0x14007eda0  jz      short loc_14007EDD3
0x14007eda2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eda9  lea     rax, WPP_GLOBAL_Control
0x14007edb0  cmp     rcx, rax
0x14007edb3  jz      loc_14007EFE7
0x14007edb9  mov     edx, 10Ch
0x14007edbe  mov     rcx, [rcx+18h]
0x14007edc2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007edc9  call    WPP_SF_
0x14007edce  jmp     loc_14007EFE7
0x14007edd3  mov     r8d, dword ptr [rbp+var_C]
0x14007edd7  mov     r9d, 140h
0x14007eddd  mov     r12d, dword ptr [rbp+var_C+4]
0x14007ede1  lea     eax, [r8+140h]
0x14007ede8  cmp     eax, r9d
0x14007edeb  jb      loc_14007EFB0
0x14007edf1  lea     ecx, [rax+r12]
0x14007edf5  mov     dword ptr [rbp+Size], ecx
0x14007edf8  cmp     ecx, eax
0x14007edfa  jb      loc_14007EFB0
0x14007ee00  lea     eax, [rcx+10h]
0x14007ee03  cmp     eax, 10h
0x14007ee06  jb      short loc_14007EE6B
0x14007ee08  mov     ecx, 40h ; '@'
0x14007ee0d  cmp     eax, ecx
0x14007ee0f  ja      short loc_14007EE1A
0x14007ee11  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14007ee18  jmp     short loc_14007EE3F
0x14007ee1a  cmp     eax, 100h
0x14007ee1f  ja      short loc_14007EE2A
0x14007ee21  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007ee28  jmp     short loc_14007EE3F
0x14007ee2a  cmp     eax, 400h
0x14007ee2f  jbe     short loc_14007EE3F
0x14007ee31  cmp     eax, 800h
0x14007ee36  ja      short loc_14007EE50
0x14007ee38  lea     rsi, stru_1400B0180
0x14007ee3f  mov     rcx, rsi; Lookaside
0x14007ee42  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007ee49  nop     dword ptr [rax+rax+00h]
0x14007ee4e  jmp     short loc_14007EE66
0x14007ee50  xor     esi, esi
0x14007ee52  mov     edx, eax
0x14007ee54  mov     r8d, 30337776h
0x14007ee5a  call    cs:__imp_ExAllocatePool2
0x14007ee61  nop     dword ptr [rax+rax+00h]
0x14007ee66  test    rax, rax
0x14007ee69  jnz     short loc_14007EE91
0x14007ee6b  mov     ebx, 0C000009Ah
0x14007ee70  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ee77  lea     rax, WPP_GLOBAL_Control
0x14007ee7e  cmp     rcx, rax
0x14007ee81  jz      loc_14007EFE7
0x14007ee87  mov     edx, 10Eh
0x14007ee8c  jmp     loc_14007EDBE
0x14007ee91  mov     r8d, dword ptr [rbp+Size]; Size
0x14007ee95  lea     rdi, [rax+10h]
0x14007ee99  mov     rcx, rdi; void *
0x14007ee9c  mov     [rax], rsi
0x14007ee9f  xor     edx, edx; Val
0x14007eea1  mov     dword ptr [rax+8], 30337776h
0x14007eea8  xor     ebx, ebx
0x14007eeaa  call    memset
0x14007eeaf  mov     rcx, [rbp+arg_18]
0x14007eeb3  lea     rdx, [r15+10h]; Src
0x14007eeb7  mov     al, [rbp+arg_8]
0x14007eeba  mov     [rdi+0Ah], al
0x14007eebd  mov     rax, [rbp+arg_10]
0x14007eec1  mov     [rdi+10h], rax
0x14007eec5  mov     dword ptr [rdi], 280180h
0x14007eecb  mov     dword ptr [rdi+18h], 3E8h
0x14007eed2  mov     eax, [rcx]
0x14007eed4  mov     [rdi+4], eax
0x14007eed7  movzx   eax, word ptr [rcx+4]
0x14007eedb  mov     ecx, dword ptr [rbp+var_C]
0x14007eede  mov     esi, ecx
0x14007eee0  mov     [rdi+8], ax
0x14007eee4  mov     r8d, esi; Size
0x14007eee7  mov     dword ptr [rdi+1Ch], 140h
0x14007eeee  lea     eax, [r12+rcx]
0x14007eef2  lea     rcx, [rdi+140h]; void *
0x14007eef9  mov     [rdi+20h], eax
0x14007eefc  call    memmove
0x14007ef01  test    r12d, r12d
0x14007ef04  jz      short loc_14007EF46
0x14007ef06  mov     r9d, [rdi+1Ch]
0x14007ef0a  lea     r8, [rbp+var_C+4]; unsigned int *
0x14007ef0e  add     r9, rdi
0x14007ef11  lea     edx, [rbx+0Bh]; enum MANAGEMENT_FRAME_TYPE
0x14007ef14  add     r9, rsi; unsigned __int8 *
0x14007ef17  mov     rcx, r13; struct _WFD_ROLE *
0x14007ef1a  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007ef1f  mov     ebx, eax
0x14007ef21  test    eax, eax
0x14007ef23  jz      short loc_14007EF46
0x14007ef25  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ef2c  lea     rax, WPP_GLOBAL_Control
0x14007ef33  cmp     rcx, rax
0x14007ef36  jz      loc_14007EFE7
0x14007ef3c  mov     edx, 10Fh
0x14007ef41  jmp     loc_14007EDBE
0x14007ef46  mov     rax, [rbp+arg_30]
0x14007ef4a  cmp     dword ptr [rax+40h], 0
0x14007ef4e  jz      short loc_14007EF90
0x14007ef50  mov     r9b, [rbp+arg_38]; unsigned __int8
0x14007ef54  mov     rcx, r13; struct _WFD_ROLE *
0x14007ef57  mov     r8b, [rbp+arg_28]; unsigned __int8
0x14007ef5b  mov     edx, [rbp+arg_20]; enum _DOT11_WPS_CONFIG_METHOD
0x14007ef5e  mov     [rsp+40h+var_18], rdi; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *
0x14007ef63  mov     [rsp+40h+var_20], rax; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x14007ef68  call    ?WFDRoleHandleIncomingServiceSessionRequest@@YAHPEAU_WFD_ROLE@@W4_DOT11_WPS_CONFIG_METHOD@@EEPEBU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDRoleHandleIncomingServiceSessionRequest(_WFD_ROLE *,_DOT11_WPS_CONFIG_METHOD,uchar,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES const *,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)
0x14007ef6d  mov     ebx, eax
0x14007ef6f  test    eax, eax
0x14007ef71  jz      short loc_14007EF90
0x14007ef73  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ef7a  lea     rax, WPP_GLOBAL_Control
0x14007ef81  cmp     rcx, rax
0x14007ef84  jz      short loc_14007EFE7
0x14007ef86  mov     edx, 110h
0x14007ef8b  jmp     loc_14007EDBE
0x14007ef90  mov     rcx, [r13+20h]; Lock
0x14007ef94  lea     rdx, [rbp+LockState]; LockState
0x14007ef98  call    cs:__imp_NdisReleaseRWLock
0x14007ef9f  nop     dword ptr [rax+rax+00h]
0x14007efa4  mov     rax, [rbp+arg_40]
0x14007efab  mov     [rax], rdi
0x14007efae  jmp     short loc_14007F02F
0x14007efb0  mov     ebx, 80000005h
0x14007efb5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007efbc  lea     rax, WPP_GLOBAL_Control
0x14007efc3  cmp     rcx, rax
0x14007efc6  jz      short loc_14007EFE7
0x14007efc8  mov     rcx, [rcx+18h]
0x14007efcc  mov     edx, 10Dh
0x14007efd1  mov     dword ptr [rsp+40h+var_18], r12d
0x14007efd6  mov     dword ptr [rsp+40h+var_20], r8d
0x14007efdb  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007efe2  call    WPP_SF_lll
0x14007efe7  mov     rcx, [r13+20h]; Lock
0x14007efeb  lea     rdx, [rbp+LockState]; LockState
0x14007efef  call    cs:__imp_NdisReleaseRWLock
0x14007eff6  nop     dword ptr [rax+rax+00h]
0x14007effb  test    rdi, rdi
0x14007effe  jz      short loc_14007F02F
0x14007f000  lea     rcx, [rdi-10h]; P
0x14007f004  mov     rax, [rcx]
0x14007f007  test    rax, rax
0x14007f00a  jz      short loc_14007F020
0x14007f00c  mov     rdx, rcx; Entry
0x14007f00f  mov     rcx, rax; Lookaside
0x14007f012  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f019  nop     dword ptr [rax+rax+00h]
0x14007f01e  jmp     short loc_14007F02F
0x14007f020  mov     edx, [rcx+8]; Tag
0x14007f023  call    cs:__imp_ExFreePoolWithTag
0x14007f02a  nop     dword ptr [rax+rax+00h]
0x14007f02f  lea     rax, [r15+10h]
0x14007f033  test    rax, rax
0x14007f036  jz      short loc_14007F093
0x14007f038  mov     rcx, [r15]; Lookaside
0x14007f03b  test    rcx, rcx
0x14007f03e  jz      short loc_14007F051
0x14007f040  mov     rdx, r15; Entry
0x14007f043  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f04a  nop     dword ptr [rax+rax+00h]
0x14007f04f  jmp     short loc_14007F093
0x14007f051  mov     edx, [r15+8]; Tag
0x14007f055  mov     rcx, r15; P
0x14007f058  call    cs:__imp_ExFreePoolWithTag
0x14007f05f  nop     dword ptr [rax+rax+00h]
0x14007f064  jmp     short loc_14007F093
0x14007f066  mov     ebx, 0C000009Ah
0x14007f06b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f072  lea     rax, WPP_GLOBAL_Control
0x14007f079  cmp     rcx, rax
0x14007f07c  jz      short loc_14007F093
0x14007f07e  mov     rcx, [rcx+18h]
0x14007f082  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007f089  mov     edx, 10Ah
0x14007f08e  call    WPP_SF_
0x14007f093  mov     rcx, [r14]; Lookaside
0x14007f096  test    rcx, rcx
0x14007f099  jz      short loc_14007F0AC
0x14007f09b  mov     rdx, r14; Entry
0x14007f09e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007f0a5  nop     dword ptr [rax+rax+00h]
0x14007f0aa  jmp     short loc_14007F0EE
0x14007f0ac  mov     edx, [r14+8]; Tag
0x14007f0b0  mov     rcx, r14; P
0x14007f0b3  call    cs:__imp_ExFreePoolWithTag
0x14007f0ba  nop     dword ptr [rax+rax+00h]
0x14007f0bf  jmp     short loc_14007F0EE
0x14007f0c1  mov     ebx, 0C000009Ah
0x14007f0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f0cd  lea     rax, WPP_GLOBAL_Control
0x14007f0d4  cmp     rcx, rax
0x14007f0d7  jz      short loc_14007F0EE
0x14007f0d9  mov     rcx, [rcx+18h]
0x14007f0dd  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14007f0e4  mov     edx, 109h
0x14007f0e9  call    WPP_SF_
0x14007f0ee  mov     eax, ebx
0x14007f0f0  mov     rbx, [rsp+40h+arg_0]
0x14007f0f8  add     rsp, 40h
0x14007f0fc  pop     r15
0x14007f0fe  pop     r14
0x14007f100  pop     r13
0x14007f102  pop     r12
0x14007f104  pop     rdi
0x14007f105  pop     rsi
0x14007f106  pop     rbp
0x14007f107  retn
```
