# APVElanPlumbExemptionList(_EXTAP_VELAN *)

- ea: `0x14006eba4`
- end: `0x14006ee8d`
- name: `?APVElanPlumbExemptionList@@YAHPEAU_EXTAP_VELAN@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006fb30`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14006eba4`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ecdf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ecdf`
- `ntoskrnl!ExAllocatePool2` at `0x14006ecf4`
- `ntoskrnl!ExAllocatePool2` at `0x14006ecf4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ee2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006ee2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ee3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ee3c`
- `NDIS!NdisReleaseRWLock` at `0x14006ed86`
- `NDIS!NdisReleaseRWLock` at `0x14006edb0`
- `NDIS!NdisReleaseRWLock` at `0x14006ed86`
- `NDIS!NdisReleaseRWLock` at `0x14006edb0`
- `NDIS!NdisAcquireRWLockRead` at `0x14006ec1d`
- `NDIS!NdisAcquireRWLockRead` at `0x14006ec1d`

## pseudocode

```c
__int64 __fastcall APVElanPlumbExemptionList(struct _EXTAP_VELAN *a1)
{
  __int64 v2; // r9
  _FILE_OBJECT *pSecurityEndpoint; // rcx
  const void **FsContext; // r13
  __int64 v5; // r15
  unsigned int v6; // esi
  unsigned int v7; // ebp
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v14; // rdi
  unsigned int v15; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v18[24]; // [rsp+38h] [rbp-70h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  memset(v18, 0, 20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
  NdisAcquireRWLockRead(a1->pVElan->pRWLock, &LockState, 0);
  pSecurityEndpoint = a1->pVElan->pSecurityEndpoint;
  if ( pSecurityEndpoint )
  {
    FsContext = (const void **)pSecurityEndpoint->FsContext;
    v5 = *((unsigned int *)FsContext + 46);
    if ( (_DWORD)v5 )
    {
      v6 = 6 * v5;
      if ( (unsigned __int64)(6 * v5) > 0xFFFFFFFF )
      {
        v8 = -1073676267;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v10 = 130;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
      v7 = v6 + 12;
      if ( v6 + 12 < v6 )
      {
        v8 = -1073676267;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v10 = 131;
LABEL_26:
          WPP_SF_(v9->AttachedDevice, v10, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      v11 = v6 + 28;
      if ( v7 >= 0xFFFFFFF0 )
        goto LABEL_22;
      if ( v11 > 0x40 )
      {
        if ( v11 > 0x100 )
        {
          if ( v11 > 0x400 )
          {
            if ( v11 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v11, 809066870, v2);
LABEL_20:
              if ( Pool2 )
              {
                Pool2[2] = 809066870;
                v14 = Pool2 + 4;
                *(_QWORD *)Pool2 = p_WaitListHead;
                memset(Pool2 + 4, 0, v7);
                v14[1] = v5;
                v14[2] = v5;
                memmove(v14 + 3, FsContext[24], v6);
                goto LABEL_29;
              }
LABEL_22:
              v8 = -1073741670;
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v10 = 132;
                goto LABEL_26;
              }
LABEL_27:
              NdisReleaseRWLock(a1->pVElan->pRWLock, &LockState);
              goto LABEL_37;
            }
            p_WaitListHead = &stru_1400B0180;
          }
          else
          {
            p_WaitListHead = &Lookaside;
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
      goto LABEL_20;
    }
  }
  v7 = 20;
  v14 = v18;
LABEL_29:
  NdisReleaseRWLock(a1->pVElan->pRWLock, &LockState);
  *v14 = 1311104;
  v15 = PtRequestAdapterSync(a1->pVElan->pAdapt, 1u, 0xE010184u, v14, v7);
  v8 = v15;
  if ( v15 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v15);
  if ( v14 != (_DWORD *)v18 && v14 )
  {
    if ( *((_QWORD *)v14 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 4);
    else
      ExFreePoolWithTag(v14 - 4, *(v14 - 2));
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x14006eba4  push    rbx
0x14006eba6  push    rbp
0x14006eba7  push    rsi
0x14006eba8  push    rdi
0x14006eba9  push    r12
0x14006ebab  push    r13
0x14006ebad  push    r14
0x14006ebaf  push    r15
0x14006ebb1  sub     rsp, 68h
0x14006ebb5  mov     rax, cs:__security_cookie
0x14006ebbc  xor     rax, rsp
0x14006ebbf  mov     [rsp+0A8h+var_58], rax
0x14006ebc4  xor     eax, eax
0x14006ebc6  mov     [rsp+0A8h+LockState.OldIrql], 0
0x14006ebcb  xorps   xmm0, xmm0
0x14006ebce  mov     word ptr [rsp+0A8h+LockState.LockState], ax
0x14006ebd3  movups  xmmword ptr [rsp+0A8h+var_6F], xmm0
0x14006ebd8  mov     dword ptr [rsp+0A8h+var_6F+0Fh], eax
0x14006ebdc  mov     r14, rcx
0x14006ebdf  mov     [rsp+0A8h+var_70], al
0x14006ebe3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ebea  lea     r12, WPP_GLOBAL_Control
0x14006ebf1  cmp     rcx, r12
0x14006ebf4  jz      short loc_14006EC0B
0x14006ebf6  mov     rcx, [rcx+18h]
0x14006ebfa  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006ec01  mov     edx, 81h
0x14006ec06  call    WPP_SF_
0x14006ec0b  mov     rcx, [r14]
0x14006ec0e  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006ec13  xor     r8d, r8d; Flags
0x14006ec16  mov     rcx, [rcx+90h]; Lock
0x14006ec1d  call    cs:__imp_NdisAcquireRWLockRead
0x14006ec24  nop     dword ptr [rax+rax+00h]
0x14006ec29  mov     rax, [r14]
0x14006ec2c  mov     rcx, [rax+1700h]
0x14006ec33  test    rcx, rcx
0x14006ec36  jz      loc_14006ED97
0x14006ec3c  mov     r13, [rcx+18h]
0x14006ec40  mov     r15d, [r13+0B8h]
0x14006ec47  test    r15d, r15d
0x14006ec4a  jz      loc_14006ED97
0x14006ec50  lea     rsi, [r15+r15*2]
0x14006ec54  mov     eax, 0FFFFFFFFh
0x14006ec59  add     rsi, rsi
0x14006ec5c  cmp     rsi, rax
0x14006ec5f  ja      loc_14006ED51
0x14006ec65  lea     ebp, [rsi+0Ch]
0x14006ec68  cmp     ebp, esi
0x14006ec6a  jnb     short loc_14006EC8B
0x14006ec6c  mov     ebx, 0C0010015h
0x14006ec71  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ec78  cmp     rcx, r12
0x14006ec7b  jz      loc_14006ED77
0x14006ec81  mov     edx, 83h
0x14006ec86  jmp     loc_14006ED67
0x14006ec8b  lea     eax, [rbp+10h]
0x14006ec8e  cmp     eax, 10h
0x14006ec91  jb      loc_14006ED39
0x14006ec97  mov     ecx, 40h ; '@'
0x14006ec9c  mov     edi, 30396176h
0x14006eca1  cmp     eax, ecx
0x14006eca3  ja      short loc_14006ECAE
0x14006eca5  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006ecac  jmp     short loc_14006ECDC
0x14006ecae  cmp     eax, 100h
0x14006ecb3  ja      short loc_14006ECBE
0x14006ecb5  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006ecbc  jmp     short loc_14006ECDC
0x14006ecbe  cmp     eax, 400h
0x14006ecc3  ja      short loc_14006ECCE
0x14006ecc5  lea     rbx, Lookaside
0x14006eccc  jmp     short loc_14006ECDC
0x14006ecce  cmp     eax, 800h
0x14006ecd3  ja      short loc_14006ECED
0x14006ecd5  lea     rbx, stru_1400B0180
0x14006ecdc  mov     rcx, rbx; Lookaside
0x14006ecdf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ece6  nop     dword ptr [rax+rax+00h]
0x14006eceb  jmp     short loc_14006ED00
0x14006eced  xor     ebx, ebx
0x14006ecef  mov     edx, eax
0x14006ecf1  mov     r8d, edi
0x14006ecf4  call    cs:__imp_ExAllocatePool2
0x14006ecfb  nop     dword ptr [rax+rax+00h]
0x14006ed00  test    rax, rax
0x14006ed03  jz      short loc_14006ED39
0x14006ed05  mov     [rax+8], edi
0x14006ed08  xor     edx, edx; Val
0x14006ed0a  lea     rdi, [rax+10h]
0x14006ed0e  mov     r8d, ebp; Size
0x14006ed11  mov     rcx, rdi; void *
0x14006ed14  mov     [rax], rbx
0x14006ed17  call    memset
0x14006ed1c  mov     [rdi+4], r15d
0x14006ed20  lea     rcx, [rdi+0Ch]; void *
0x14006ed24  mov     [rdi+8], r15d
0x14006ed28  mov     rdx, [r13+0C0h]; Src
0x14006ed2f  mov     r8d, esi; Size
0x14006ed32  call    memmove
0x14006ed37  jmp     short loc_14006EDA1
0x14006ed39  mov     ebx, 0C000009Ah
0x14006ed3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed45  cmp     rcx, r12
0x14006ed48  jz      short loc_14006ED77
0x14006ed4a  mov     edx, 84h
0x14006ed4f  jmp     short loc_14006ED67
0x14006ed51  mov     ebx, 0C0010015h
0x14006ed56  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed5d  cmp     rcx, r12
0x14006ed60  jz      short loc_14006ED77
0x14006ed62  mov     edx, 82h
0x14006ed67  mov     rcx, [rcx+18h]
0x14006ed6b  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006ed72  call    WPP_SF_
0x14006ed77  mov     rcx, [r14]
0x14006ed7a  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006ed7f  mov     rcx, [rcx+90h]; Lock
0x14006ed86  call    cs:__imp_NdisReleaseRWLock
0x14006ed8d  nop     dword ptr [rax+rax+00h]
0x14006ed92  jmp     loc_14006EE48
0x14006ed97  mov     ebp, 14h
0x14006ed9c  lea     rdi, [rsp+0A8h+var_70]
0x14006eda1  mov     rcx, [r14]
0x14006eda4  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006eda9  mov     rcx, [rcx+90h]; Lock
0x14006edb0  call    cs:__imp_NdisReleaseRWLock
0x14006edb7  nop     dword ptr [rax+rax+00h]
0x14006edbc  mov     dword ptr [rdi], 140180h
0x14006edc2  mov     r9, rdi; void *
0x14006edc5  mov     rcx, [r14]
0x14006edc8  mov     edx, 1; unsigned int
0x14006edcd  mov     r8d, 0E010184h; unsigned int
0x14006edd3  mov     [rsp+0A8h+var_88], ebp; unsigned int
0x14006edd7  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006eddb  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006ede0  mov     ebx, eax
0x14006ede2  test    eax, eax
0x14006ede4  jz      short loc_14006EE0A
0x14006ede6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eded  cmp     rcx, r12
0x14006edf0  jz      short loc_14006EE0A
0x14006edf2  mov     rcx, [rcx+18h]
0x14006edf6  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006edfd  mov     edx, 85h
0x14006ee02  mov     r9d, eax
0x14006ee05  call    WPP_SF_d
0x14006ee0a  lea     rax, [rsp+0A8h+var_70]
0x14006ee0f  cmp     rdi, rax
0x14006ee12  jz      short loc_14006EE48
0x14006ee14  test    rdi, rdi
0x14006ee17  jz      short loc_14006EE48
0x14006ee19  lea     rcx, [rdi-10h]; P
0x14006ee1d  mov     rax, [rcx]
0x14006ee20  test    rax, rax
0x14006ee23  jz      short loc_14006EE39
0x14006ee25  mov     rdx, rcx; Entry
0x14006ee28  mov     rcx, rax; Lookaside
0x14006ee2b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006ee32  nop     dword ptr [rax+rax+00h]
0x14006ee37  jmp     short loc_14006EE48
0x14006ee39  mov     edx, [rcx+8]; Tag
0x14006ee3c  call    cs:__imp_ExFreePoolWithTag
0x14006ee43  nop     dword ptr [rax+rax+00h]
0x14006ee48  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ee4f  cmp     rcx, r12
0x14006ee52  jz      short loc_14006EE6C
0x14006ee54  mov     rcx, [rcx+18h]
0x14006ee58  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14006ee5f  mov     edx, 86h
0x14006ee64  mov     r9d, ebx
0x14006ee67  call    WPP_SF_d
0x14006ee6c  mov     eax, ebx
0x14006ee6e  mov     rcx, [rsp+0A8h+var_58]
0x14006ee73  xor     rcx, rsp; StackCookie
0x14006ee76  call    __security_check_cookie
0x14006ee7b  add     rsp, 68h
0x14006ee7f  pop     r15
0x14006ee81  pop     r14
0x14006ee83  pop     r13
0x14006ee85  pop     r12
0x14006ee87  pop     rdi
0x14006ee88  pop     rsi
0x14006ee89  pop     rbp
0x14006ee8a  pop     rbx
0x14006ee8b  retn
```
