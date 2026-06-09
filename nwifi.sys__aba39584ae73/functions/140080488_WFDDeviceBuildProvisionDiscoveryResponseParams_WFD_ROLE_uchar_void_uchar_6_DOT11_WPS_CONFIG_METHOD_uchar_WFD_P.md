# WFDDeviceBuildProvisionDiscoveryResponseParams(_WFD_ROLE *,uchar,void *,uchar (*)[6],_DOT11_WPS_CONFIG_METHOD,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *,uchar,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 * *)

- ea: `0x140080488`
- end: `0x140080939`
- name: `?WFDDeviceBuildProvisionDiscoveryResponseParams@@YAHPEAU_WFD_ROLE@@EPEAXPEAY05EW4_DOT11_WPS_CONFIG_METHOD@@EPEAU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@EPEAPEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z`
- size: `1201`
- prototype: `__int64 __usercall@<rax>(struct _WFD_ROLE *@<rcx>, unsigned __int8@<dl>, void *@<r8>, unsigned __int8 (*)[6]@<r9>, enum _DOT11_WPS_CONFIG_METHOD, unsigned __int8, struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *, unsigned __int8, struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007fba4`
- `0x140086bbc`

## callees

- `0x14000d21c`
- `0x140030244`
- `0x14007b8bc`
- `0x14007bbb4`
- `0x140080488`
- `0x14009a7dc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400804ca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008052c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080672`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400804ca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008052c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140080672`
- `ntoskrnl!ExAllocatePool2` at `0x14008068a`
- `ntoskrnl!ExAllocatePool2` at `0x14008068a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080842`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080873`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400808ce`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080842`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140080873`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400808ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080853`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080888`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400808e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080853`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080888`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400808e3`
- `NDIS!NdisReleaseRWLock` at `0x1400807c8`
- `NDIS!NdisReleaseRWLock` at `0x14008081f`
- `NDIS!NdisReleaseRWLock` at `0x1400807c8`
- `NDIS!NdisReleaseRWLock` at `0x14008081f`
- `NDIS!NdisAcquireRWLockRead` at `0x1400805ae`
- `NDIS!NdisAcquireRWLockRead` at `0x1400805ae`

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
        unsigned __int8 a8,
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
    CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 0xBu, &v30, 0);
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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v23, 808679286);
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
                                       0xBu,
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
          p_WaitListHead = &stru_1400B31C0;
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
0x140080488  mov     rax, rsp
0x14008048b  mov     [rax+8], rbx
0x14008048f  mov     [rax+20h], r9
0x140080493  mov     [rax+18h], r8
0x140080497  mov     [rax+10h], dl
0x14008049a  push    rbp
0x14008049b  push    rsi
0x14008049c  push    rdi
0x14008049d  push    r12
0x14008049f  push    r13
0x1400804a1  push    r14
0x1400804a3  push    r15
0x1400804a5  mov     rbp, rsp
0x1400804a8  sub     rsp, 40h
0x1400804ac  mov     r13, rcx
0x1400804af  mov     dword ptr [rbp+var_C+4], 0
0x1400804b6  xor     eax, eax
0x1400804b8  mov     [rbp+LockState.OldIrql], 0
0x1400804bc  lea     rsi, Lookaside
0x1400804c3  mov     word ptr [rbp+LockState.LockState], ax
0x1400804c7  mov     rcx, rsi; Lookaside
0x1400804ca  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400804d1  nop     dword ptr [rax+rax+00h]
0x1400804d6  mov     r14, rax
0x1400804d9  test    rax, rax
0x1400804dc  jz      loc_1400808F1
0x1400804e2  lea     rbx, [rax+10h]
0x1400804e6  mov     [rax], rsi
0x1400804e9  mov     r12d, 30337776h
0x1400804ef  mov     rcx, rbx; void *
0x1400804f2  xor     edx, edx; Val
0x1400804f4  mov     [rax+8], r12d
0x1400804f8  mov     r8d, 208h; Size
0x1400804fe  call    memset
0x140080503  mov     eax, [rbp+arg_20]
0x140080506  mov     edi, 100h
0x14008050b  mov     dword ptr [rbx], 2
0x140080511  mov     rcx, rsi; Lookaside
0x140080514  mov     [rbx+8], eax
0x140080517  mov     dword ptr [rbx+4], 80008h
0x14008051e  or      dword ptr [rbx+0Ch], 1
0x140080522  mov     dword ptr [rbx+10h], 20h ; ' '
0x140080529  mov     dword ptr [rbp+var_C], edi
0x14008052c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140080533  nop     dword ptr [rax+rax+00h]
0x140080538  mov     r15, rax
0x14008053b  test    rax, rax
0x14008053e  jz      loc_140080896
0x140080544  mov     r8d, edi; Size
0x140080547  mov     [rax], rsi
0x14008054a  xor     edx, edx; Val
0x14008054c  mov     [rax+8], r12d
0x140080550  lea     rcx, [rax+10h]; void *
0x140080554  call    memset
0x140080559  lea     r8, [r15+10h]
0x14008055d  mov     rcx, rbx
0x140080560  lea     rdx, [rbp+var_C]
0x140080564  call    WcnGenerateWpsIe
0x140080569  test    al, al
0x14008056b  jnz     short loc_1400805A1
0x14008056d  mov     ebx, 0C0000001h
0x140080572  mov     rcx, cs:WPP_GLOBAL_Control
0x140080579  lea     rax, WPP_GLOBAL_Control
0x140080580  cmp     rcx, rax
0x140080583  jz      loc_14008085F
0x140080589  mov     rcx, [rcx+18h]
0x14008058d  lea     edx, [rdi+0Bh]
0x140080590  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080597  call    WPP_SF_
0x14008059c  jmp     loc_14008085F
0x1400805a1  mov     rcx, [r13+20h]; Lock
0x1400805a5  lea     rdx, [rbp+LockState]; LockState
0x1400805a9  xor     r8d, r8d; Flags
0x1400805ac  xor     edi, edi
0x1400805ae  call    cs:__imp_NdisAcquireRWLockRead
0x1400805b5  nop     dword ptr [rax+rax+00h]
0x1400805ba  xor     r9d, r9d; unsigned __int8 *
0x1400805bd  lea     r8, [rbp+var_C+4]; unsigned int *
0x1400805c1  lea     edx, [rdi+0Bh]; enum MANAGEMENT_FRAME_TYPE
0x1400805c4  mov     rcx, r13; struct _WFD_ROLE *
0x1400805c7  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x1400805cc  mov     ebx, eax
0x1400805ce  test    eax, eax
0x1400805d0  jz      short loc_140080603
0x1400805d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400805d9  lea     rax, WPP_GLOBAL_Control
0x1400805e0  cmp     rcx, rax
0x1400805e3  jz      loc_140080817
0x1400805e9  mov     edx, 10Ch
0x1400805ee  mov     rcx, [rcx+18h]
0x1400805f2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400805f9  call    WPP_SF_
0x1400805fe  jmp     loc_140080817
0x140080603  mov     r8d, dword ptr [rbp+var_C]
0x140080607  mov     r9d, 140h
0x14008060d  mov     r12d, dword ptr [rbp+var_C+4]
0x140080611  lea     eax, [r8+140h]
0x140080618  cmp     eax, r9d
0x14008061b  jb      loc_1400807E0
0x140080621  lea     ecx, [rax+r12]
0x140080625  mov     dword ptr [rbp+Size], ecx
0x140080628  cmp     ecx, eax
0x14008062a  jb      loc_1400807E0
0x140080630  lea     eax, [rcx+10h]
0x140080633  cmp     eax, 10h
0x140080636  jb      short loc_14008069B
0x140080638  mov     ecx, 40h ; '@'
0x14008063d  cmp     eax, ecx
0x14008063f  ja      short loc_14008064A
0x140080641  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x140080648  jmp     short loc_14008066F
0x14008064a  cmp     eax, 100h
0x14008064f  ja      short loc_14008065A
0x140080651  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140080658  jmp     short loc_14008066F
0x14008065a  cmp     eax, 400h
0x14008065f  jbe     short loc_14008066F
0x140080661  cmp     eax, 800h
0x140080666  ja      short loc_140080680
0x140080668  lea     rsi, stru_1400B31C0
0x14008066f  mov     rcx, rsi; Lookaside
0x140080672  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140080679  nop     dword ptr [rax+rax+00h]
0x14008067e  jmp     short loc_140080696
0x140080680  xor     esi, esi
0x140080682  mov     edx, eax
0x140080684  mov     r8d, 30337776h
0x14008068a  call    cs:__imp_ExAllocatePool2
0x140080691  nop     dword ptr [rax+rax+00h]
0x140080696  test    rax, rax
0x140080699  jnz     short loc_1400806C1
0x14008069b  mov     ebx, 0C000009Ah
0x1400806a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400806a7  lea     rax, WPP_GLOBAL_Control
0x1400806ae  cmp     rcx, rax
0x1400806b1  jz      loc_140080817
0x1400806b7  mov     edx, 10Eh
0x1400806bc  jmp     loc_1400805EE
0x1400806c1  mov     r8d, dword ptr [rbp+Size]; Size
0x1400806c5  lea     rdi, [rax+10h]
0x1400806c9  mov     rcx, rdi; void *
0x1400806cc  mov     [rax], rsi
0x1400806cf  xor     edx, edx; Val
0x1400806d1  mov     dword ptr [rax+8], 30337776h
0x1400806d8  xor     ebx, ebx
0x1400806da  call    memset
0x1400806df  mov     rcx, [rbp+arg_18]
0x1400806e3  lea     rdx, [r15+10h]; Src
0x1400806e7  mov     al, [rbp+arg_8]
0x1400806ea  mov     [rdi+0Ah], al
0x1400806ed  mov     rax, [rbp+arg_10]
0x1400806f1  mov     [rdi+10h], rax
0x1400806f5  mov     dword ptr [rdi], 280180h
0x1400806fb  mov     dword ptr [rdi+18h], 3E8h
0x140080702  mov     eax, [rcx]
0x140080704  mov     [rdi+4], eax
0x140080707  movzx   eax, word ptr [rcx+4]
0x14008070b  mov     ecx, dword ptr [rbp+var_C]
0x14008070e  mov     esi, ecx
0x140080710  mov     [rdi+8], ax
0x140080714  mov     r8d, esi; Size
0x140080717  mov     dword ptr [rdi+1Ch], 140h
0x14008071e  lea     eax, [r12+rcx]
0x140080722  lea     rcx, [rdi+140h]; void *
0x140080729  mov     [rdi+20h], eax
0x14008072c  call    memmove
0x140080731  test    r12d, r12d
0x140080734  jz      short loc_140080776
0x140080736  mov     r9d, [rdi+1Ch]
0x14008073a  lea     r8, [rbp+var_C+4]; unsigned int *
0x14008073e  add     r9, rdi
0x140080741  lea     edx, [rbx+0Bh]; enum MANAGEMENT_FRAME_TYPE
0x140080744  add     r9, rsi; unsigned __int8 *
0x140080747  mov     rcx, r13; struct _WFD_ROLE *
0x14008074a  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14008074f  mov     ebx, eax
0x140080751  test    eax, eax
0x140080753  jz      short loc_140080776
0x140080755  mov     rcx, cs:WPP_GLOBAL_Control
0x14008075c  lea     rax, WPP_GLOBAL_Control
0x140080763  cmp     rcx, rax
0x140080766  jz      loc_140080817
0x14008076c  mov     edx, 10Fh
0x140080771  jmp     loc_1400805EE
0x140080776  mov     rax, [rbp+arg_30]
0x14008077a  cmp     dword ptr [rax+40h], 0
0x14008077e  jz      short loc_1400807C0
0x140080780  mov     r9b, [rbp+arg_38]; unsigned __int8
0x140080784  mov     rcx, r13; struct _WFD_ROLE *
0x140080787  mov     r8b, [rbp+arg_28]; unsigned __int8
0x14008078b  mov     edx, [rbp+arg_20]; enum _DOT11_WPS_CONFIG_METHOD
0x14008078e  mov     [rsp+40h+var_18], rdi; struct _DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *
0x140080793  mov     [rsp+40h+var_20], rax; struct _WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES *
0x140080798  call    ?WFDRoleHandleIncomingServiceSessionRequest@@YAHPEAU_WFD_ROLE@@W4_DOT11_WPS_CONFIG_METHOD@@EEPEBU_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES@@PEAU_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2@@@Z; WFDRoleHandleIncomingServiceSessionRequest(_WFD_ROLE *,_DOT11_WPS_CONFIG_METHOD,uchar,uchar,_WFD_PROVISION_DISCOVERY_REQUEST_ATTRIBUTES const *,_DOT11_SEND_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_V2 *)
0x14008079d  mov     ebx, eax
0x14008079f  test    eax, eax
0x1400807a1  jz      short loc_1400807C0
0x1400807a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807aa  lea     rax, WPP_GLOBAL_Control
0x1400807b1  cmp     rcx, rax
0x1400807b4  jz      short loc_140080817
0x1400807b6  mov     edx, 110h
0x1400807bb  jmp     loc_1400805EE
0x1400807c0  mov     rcx, [r13+20h]; Lock
0x1400807c4  lea     rdx, [rbp+LockState]; LockState
0x1400807c8  call    cs:__imp_NdisReleaseRWLock
0x1400807cf  nop     dword ptr [rax+rax+00h]
0x1400807d4  mov     rax, [rbp+arg_40]
0x1400807db  mov     [rax], rdi
0x1400807de  jmp     short loc_14008085F
0x1400807e0  mov     ebx, 80000005h
0x1400807e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400807ec  lea     rax, WPP_GLOBAL_Control
0x1400807f3  cmp     rcx, rax
0x1400807f6  jz      short loc_140080817
0x1400807f8  mov     rcx, [rcx+18h]
0x1400807fc  mov     edx, 10Dh
0x140080801  mov     dword ptr [rsp+40h+var_18], r12d
0x140080806  mov     dword ptr [rsp+40h+var_20], r8d
0x14008080b  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080812  call    WPP_SF_lll
0x140080817  mov     rcx, [r13+20h]; Lock
0x14008081b  lea     rdx, [rbp+LockState]; LockState
0x14008081f  call    cs:__imp_NdisReleaseRWLock
0x140080826  nop     dword ptr [rax+rax+00h]
0x14008082b  test    rdi, rdi
0x14008082e  jz      short loc_14008085F
0x140080830  lea     rcx, [rdi-10h]; P
0x140080834  mov     rax, [rcx]
0x140080837  test    rax, rax
0x14008083a  jz      short loc_140080850
0x14008083c  mov     rdx, rcx; Entry
0x14008083f  mov     rcx, rax; Lookaside
0x140080842  call    cs:__imp_ExFreeToNPagedLookasideList
0x140080849  nop     dword ptr [rax+rax+00h]
0x14008084e  jmp     short loc_14008085F
0x140080850  mov     edx, [rcx+8]; Tag
0x140080853  call    cs:__imp_ExFreePoolWithTag
0x14008085a  nop     dword ptr [rax+rax+00h]
0x14008085f  lea     rax, [r15+10h]
0x140080863  test    rax, rax
0x140080866  jz      short loc_1400808C3
0x140080868  mov     rcx, [r15]; Lookaside
0x14008086b  test    rcx, rcx
0x14008086e  jz      short loc_140080881
0x140080870  mov     rdx, r15; Entry
0x140080873  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008087a  nop     dword ptr [rax+rax+00h]
0x14008087f  jmp     short loc_1400808C3
0x140080881  mov     edx, [r15+8]; Tag
0x140080885  mov     rcx, r15; P
0x140080888  call    cs:__imp_ExFreePoolWithTag
0x14008088f  nop     dword ptr [rax+rax+00h]
0x140080894  jmp     short loc_1400808C3
0x140080896  mov     ebx, 0C000009Ah
0x14008089b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400808a2  lea     rax, WPP_GLOBAL_Control
0x1400808a9  cmp     rcx, rax
0x1400808ac  jz      short loc_1400808C3
0x1400808ae  mov     rcx, [rcx+18h]
0x1400808b2  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400808b9  mov     edx, 10Ah
0x1400808be  call    WPP_SF_
0x1400808c3  mov     rcx, [r14]; Lookaside
0x1400808c6  test    rcx, rcx
0x1400808c9  jz      short loc_1400808DC
0x1400808cb  mov     rdx, r14; Entry
0x1400808ce  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400808d5  nop     dword ptr [rax+rax+00h]
0x1400808da  jmp     short loc_14008091E
0x1400808dc  mov     edx, [r14+8]; Tag
0x1400808e0  mov     rcx, r14; P
0x1400808e3  call    cs:__imp_ExFreePoolWithTag
0x1400808ea  nop     dword ptr [rax+rax+00h]
0x1400808ef  jmp     short loc_14008091E
0x1400808f1  mov     ebx, 0C000009Ah
0x1400808f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400808fd  lea     rax, WPP_GLOBAL_Control
0x140080904  cmp     rcx, rax
0x140080907  jz      short loc_14008091E
0x140080909  mov     rcx, [rcx+18h]
0x14008090d  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140080914  mov     edx, 109h
0x140080919  call    WPP_SF_
0x14008091e  mov     eax, ebx
0x140080920  mov     rbx, [rsp+40h+arg_0]
0x140080928  add     rsp, 40h
0x14008092c  pop     r15
0x14008092e  pop     r14
0x140080930  pop     r13
0x140080932  pop     r12
0x140080934  pop     rdi
0x140080935  pop     rsi
0x140080936  pop     rbp
0x140080937  retn
```
