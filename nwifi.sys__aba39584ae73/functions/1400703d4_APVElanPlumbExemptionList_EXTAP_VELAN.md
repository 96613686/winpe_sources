# APVElanPlumbExemptionList(_EXTAP_VELAN *)

- ea: `0x1400703d4`
- end: `0x1400706bd`
- name: `?APVElanPlumbExemptionList@@YAHPEAU_EXTAP_VELAN@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct _EXTAP_VELAN *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140071360`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400703d4`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007050f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007050f`
- `ntoskrnl!ExAllocatePool2` at `0x140070524`
- `ntoskrnl!ExAllocatePool2` at `0x140070524`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007065b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007065b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007066c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007066c`
- `NDIS!NdisReleaseRWLock` at `0x1400705b6`
- `NDIS!NdisReleaseRWLock` at `0x1400705e0`
- `NDIS!NdisReleaseRWLock` at `0x1400705b6`
- `NDIS!NdisReleaseRWLock` at `0x1400705e0`
- `NDIS!NdisAcquireRWLockRead` at `0x14007044d`
- `NDIS!NdisAcquireRWLockRead` at `0x14007044d`

## pseudocode

```c
__int64 __fastcall APVElanPlumbExemptionList(struct _EXTAP_VELAN *a1)
{
  _FILE_OBJECT *pSecurityEndpoint; // rcx
  const void **FsContext; // r13
  __int64 v4; // r15
  unsigned int v5; // esi
  unsigned int v6; // ebp
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-70h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  memset(v17, 0, 20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
  NdisAcquireRWLockRead(a1->pVElan->pRWLock, &LockState, 0);
  pSecurityEndpoint = a1->pVElan->pSecurityEndpoint;
  if ( pSecurityEndpoint )
  {
    FsContext = (const void **)pSecurityEndpoint->FsContext;
    v4 = *((unsigned int *)FsContext + 46);
    if ( (_DWORD)v4 )
    {
      v5 = 6 * v4;
      if ( (unsigned __int64)(6 * v4) > 0xFFFFFFFF )
      {
        v7 = -1073676267;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v9 = 130;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
      v6 = v5 + 12;
      if ( v5 + 12 < v5 )
      {
        v7 = -1073676267;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v9 = 131;
LABEL_26:
          WPP_SF_(v8->AttachedDevice, v9, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      v10 = v5 + 28;
      if ( v6 >= 0xFFFFFFF0 )
        goto LABEL_22;
      if ( v10 > 0x40 )
      {
        if ( v10 > 0x100 )
        {
          if ( v10 > 0x400 )
          {
            if ( v10 > 0x800 )
            {
              p_WaitListHead = 0;
              Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 809066870);
LABEL_20:
              if ( Pool2 )
              {
                Pool2[2] = 809066870;
                v13 = Pool2 + 4;
                *(_QWORD *)Pool2 = p_WaitListHead;
                memset(Pool2 + 4, 0, v6);
                v13[1] = v4;
                v13[2] = v4;
                memmove(v13 + 3, FsContext[24], v5);
                goto LABEL_29;
              }
LABEL_22:
              v7 = -1073741670;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v9 = 132;
                goto LABEL_26;
              }
LABEL_27:
              NdisReleaseRWLock(a1->pVElan->pRWLock, &LockState);
              goto LABEL_37;
            }
            p_WaitListHead = &stru_1400B31C0;
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
  v6 = 20;
  v13 = v17;
LABEL_29:
  NdisReleaseRWLock(a1->pVElan->pRWLock, &LockState);
  *v13 = 1311104;
  v14 = PtRequestAdapterSync(a1->pVElan->pAdapt, 1u, 0xE010184u, v13, v6);
  v7 = v14;
  if ( v14 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v14);
  if ( v13 != (_DWORD *)v17 && v13 )
  {
    if ( *((_QWORD *)v13 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 - 2), v13 - 4);
    else
      ExFreePoolWithTag(v13 - 4, *(v13 - 2));
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1400703d4  push    rbx
0x1400703d6  push    rbp
0x1400703d7  push    rsi
0x1400703d8  push    rdi
0x1400703d9  push    r12
0x1400703db  push    r13
0x1400703dd  push    r14
0x1400703df  push    r15
0x1400703e1  sub     rsp, 68h
0x1400703e5  mov     rax, cs:__security_cookie
0x1400703ec  xor     rax, rsp
0x1400703ef  mov     [rsp+0A8h+var_58], rax
0x1400703f4  xor     eax, eax
0x1400703f6  mov     [rsp+0A8h+LockState.OldIrql], 0
0x1400703fb  xorps   xmm0, xmm0
0x1400703fe  mov     word ptr [rsp+0A8h+LockState.LockState], ax
0x140070403  movups  xmmword ptr [rsp+0A8h+var_6F], xmm0
0x140070408  mov     dword ptr [rsp+0A8h+var_6F+0Fh], eax
0x14007040c  mov     r14, rcx
0x14007040f  mov     [rsp+0A8h+var_70], al
0x140070413  mov     rcx, cs:WPP_GLOBAL_Control
0x14007041a  lea     r12, WPP_GLOBAL_Control
0x140070421  cmp     rcx, r12
0x140070424  jz      short loc_14007043B
0x140070426  mov     rcx, [rcx+18h]
0x14007042a  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x140070431  mov     edx, 81h
0x140070436  call    WPP_SF_
0x14007043b  mov     rcx, [r14]
0x14007043e  lea     rdx, [rsp+0A8h+LockState]; LockState
0x140070443  xor     r8d, r8d; Flags
0x140070446  mov     rcx, [rcx+90h]; Lock
0x14007044d  call    cs:__imp_NdisAcquireRWLockRead
0x140070454  nop     dword ptr [rax+rax+00h]
0x140070459  mov     rax, [r14]
0x14007045c  mov     rcx, [rax+1700h]
0x140070463  test    rcx, rcx
0x140070466  jz      loc_1400705C7
0x14007046c  mov     r13, [rcx+18h]
0x140070470  mov     r15d, [r13+0B8h]
0x140070477  test    r15d, r15d
0x14007047a  jz      loc_1400705C7
0x140070480  lea     rsi, [r15+r15*2]
0x140070484  mov     eax, 0FFFFFFFFh
0x140070489  add     rsi, rsi
0x14007048c  cmp     rsi, rax
0x14007048f  ja      loc_140070581
0x140070495  lea     ebp, [rsi+0Ch]
0x140070498  cmp     ebp, esi
0x14007049a  jnb     short loc_1400704BB
0x14007049c  mov     ebx, 0C0010015h
0x1400704a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704a8  cmp     rcx, r12
0x1400704ab  jz      loc_1400705A7
0x1400704b1  mov     edx, 83h
0x1400704b6  jmp     loc_140070597
0x1400704bb  lea     eax, [rbp+10h]
0x1400704be  cmp     eax, 10h
0x1400704c1  jb      loc_140070569
0x1400704c7  mov     ecx, 40h ; '@'
0x1400704cc  mov     edi, 30396176h
0x1400704d1  cmp     eax, ecx
0x1400704d3  ja      short loc_1400704DE
0x1400704d5  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400704dc  jmp     short loc_14007050C
0x1400704de  cmp     eax, 100h
0x1400704e3  ja      short loc_1400704EE
0x1400704e5  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400704ec  jmp     short loc_14007050C
0x1400704ee  cmp     eax, 400h
0x1400704f3  ja      short loc_1400704FE
0x1400704f5  lea     rbx, Lookaside
0x1400704fc  jmp     short loc_14007050C
0x1400704fe  cmp     eax, 800h
0x140070503  ja      short loc_14007051D
0x140070505  lea     rbx, stru_1400B31C0
0x14007050c  mov     rcx, rbx; Lookaside
0x14007050f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140070516  nop     dword ptr [rax+rax+00h]
0x14007051b  jmp     short loc_140070530
0x14007051d  xor     ebx, ebx
0x14007051f  mov     edx, eax
0x140070521  mov     r8d, edi
0x140070524  call    cs:__imp_ExAllocatePool2
0x14007052b  nop     dword ptr [rax+rax+00h]
0x140070530  test    rax, rax
0x140070533  jz      short loc_140070569
0x140070535  mov     [rax+8], edi
0x140070538  xor     edx, edx; Val
0x14007053a  lea     rdi, [rax+10h]
0x14007053e  mov     r8d, ebp; Size
0x140070541  mov     rcx, rdi; void *
0x140070544  mov     [rax], rbx
0x140070547  call    memset
0x14007054c  mov     [rdi+4], r15d
0x140070550  lea     rcx, [rdi+0Ch]; void *
0x140070554  mov     [rdi+8], r15d
0x140070558  mov     rdx, [r13+0C0h]; Src
0x14007055f  mov     r8d, esi; Size
0x140070562  call    memmove
0x140070567  jmp     short loc_1400705D1
0x140070569  mov     ebx, 0C000009Ah
0x14007056e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070575  cmp     rcx, r12
0x140070578  jz      short loc_1400705A7
0x14007057a  mov     edx, 84h
0x14007057f  jmp     short loc_140070597
0x140070581  mov     ebx, 0C0010015h
0x140070586  mov     rcx, cs:WPP_GLOBAL_Control
0x14007058d  cmp     rcx, r12
0x140070590  jz      short loc_1400705A7
0x140070592  mov     edx, 82h
0x140070597  mov     rcx, [rcx+18h]
0x14007059b  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x1400705a2  call    WPP_SF_
0x1400705a7  mov     rcx, [r14]
0x1400705aa  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400705af  mov     rcx, [rcx+90h]; Lock
0x1400705b6  call    cs:__imp_NdisReleaseRWLock
0x1400705bd  nop     dword ptr [rax+rax+00h]
0x1400705c2  jmp     loc_140070678
0x1400705c7  mov     ebp, 14h
0x1400705cc  lea     rdi, [rsp+0A8h+var_70]
0x1400705d1  mov     rcx, [r14]
0x1400705d4  lea     rdx, [rsp+0A8h+LockState]; LockState
0x1400705d9  mov     rcx, [rcx+90h]; Lock
0x1400705e0  call    cs:__imp_NdisReleaseRWLock
0x1400705e7  nop     dword ptr [rax+rax+00h]
0x1400705ec  mov     dword ptr [rdi], 140180h
0x1400705f2  mov     r9, rdi; void *
0x1400705f5  mov     rcx, [r14]
0x1400705f8  mov     edx, 1; unsigned int
0x1400705fd  mov     r8d, 0E010184h; unsigned int
0x140070603  mov     [rsp+0A8h+var_88], ebp; unsigned int
0x140070607  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14007060b  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140070610  mov     ebx, eax
0x140070612  test    eax, eax
0x140070614  jz      short loc_14007063A
0x140070616  mov     rcx, cs:WPP_GLOBAL_Control
0x14007061d  cmp     rcx, r12
0x140070620  jz      short loc_14007063A
0x140070622  mov     rcx, [rcx+18h]
0x140070626  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007062d  mov     edx, 85h
0x140070632  mov     r9d, eax
0x140070635  call    WPP_SF_d
0x14007063a  lea     rax, [rsp+0A8h+var_70]
0x14007063f  cmp     rdi, rax
0x140070642  jz      short loc_140070678
0x140070644  test    rdi, rdi
0x140070647  jz      short loc_140070678
0x140070649  lea     rcx, [rdi-10h]; P
0x14007064d  mov     rax, [rcx]
0x140070650  test    rax, rax
0x140070653  jz      short loc_140070669
0x140070655  mov     rdx, rcx; Entry
0x140070658  mov     rcx, rax; Lookaside
0x14007065b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140070662  nop     dword ptr [rax+rax+00h]
0x140070667  jmp     short loc_140070678
0x140070669  mov     edx, [rcx+8]; Tag
0x14007066c  call    cs:__imp_ExFreePoolWithTag
0x140070673  nop     dword ptr [rax+rax+00h]
0x140070678  mov     rcx, cs:WPP_GLOBAL_Control
0x14007067f  cmp     rcx, r12
0x140070682  jz      short loc_14007069C
0x140070684  mov     rcx, [rcx+18h]
0x140070688  lea     r8, WPP_7ce6be9da0b83f5d0060ad89512b0156_Traceguids
0x14007068f  mov     edx, 86h
0x140070694  mov     r9d, ebx
0x140070697  call    WPP_SF_d
0x14007069c  mov     eax, ebx
0x14007069e  mov     rcx, [rsp+0A8h+var_58]
0x1400706a3  xor     rcx, rsp; StackCookie
0x1400706a6  call    __security_check_cookie
0x1400706ab  add     rsp, 68h
0x1400706af  pop     r15
0x1400706b1  pop     r14
0x1400706b3  pop     r13
0x1400706b5  pop     r12
0x1400706b7  pop     rdi
0x1400706b8  pop     rsi
0x1400706b9  pop     rbp
0x1400706ba  pop     rbx
0x1400706bb  retn
```
