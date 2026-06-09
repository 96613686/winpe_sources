# WFDRoleAddCachedIEsToInviteParamsOidStructure(_WFD_ROLE *,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS *,ulong,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS * *,ulong *)

- ea: `0x14007a8fc`
- end: `0x14007acc2`
- name: `?WFDRoleAddCachedIEsToInviteParamsOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_SEND_INVITATION_REQUEST_PARAMETERS@@KPEAPEAU2@PEAK@Z`
- size: `966`
- prototype: `unsigned int __usercall@<eax>(struct _WFD_ROLE *@<rcx>, struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *@<rdx>, unsigned int@<r8d>, struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400891d0`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x14007a8fc`
- `0x14007b8bc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007aaaf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007aaaf`
- `ntoskrnl!ExAllocatePool2` at `0x14007aac4`
- `ntoskrnl!ExAllocatePool2` at `0x14007aac4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007ac3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007ac3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ac4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ac4f`
- `NDIS!NdisReleaseRWLock` at `0x14007ac1b`
- `NDIS!NdisReleaseRWLock` at `0x14007ac1b`
- `NDIS!NdisAcquireRWLockRead` at `0x14007a9c5`
- `NDIS!NdisAcquireRWLockRead` at `0x14007a9c5`

## pseudocode

```c
__int64 __fastcall WFDRoleAddCachedIEsToInviteParamsOidStructure(
        struct _WFD_ROLE *a1,
        struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *a2,
        unsigned int a3,
        struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **a4,
        unsigned int *a5)
{
  unsigned int *v8; // r13
  unsigned int v9; // ecx
  unsigned int v10; // edx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  char *v12; // rdi
  unsigned int CachedFrameIEs; // ebx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r12d
  unsigned int v17; // r15d
  unsigned int v18; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **v21; // rax
  unsigned int v23[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  v23[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = v25;
  }
  if ( a1 )
  {
    if ( a4 )
    {
      v8 = a5;
      if ( a5 )
      {
        if ( a2 )
        {
          v9 = *((_DWORD *)a2 + 20);
          if ( v9 <= a3 )
          {
            v10 = v9 + *((_DWORD *)a2 + 21);
            if ( v10 >= v9 && v10 <= a3 )
            {
              pRWLock = a1->pRWLock;
              *a4 = 0;
              v12 = 0;
              *v8 = 0;
              NdisAcquireRWLockRead(pRWLock, &LockState, 0);
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 8u, v23, 0);
              if ( CachedFrameIEs )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v15 = 176;
                goto LABEL_39;
              }
              v16 = v23[0];
              if ( !v23[0] )
                goto LABEL_40;
              v17 = v23[0] + a3;
              if ( v23[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    177,
                    WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                    a3,
                    v23[0]);
                goto LABEL_40;
              }
              v18 = v17 + 16;
              if ( v17 >= 0xFFFFFFF0 )
              {
LABEL_37:
                v12 = 0;
                CachedFrameIEs = -1073741670;
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v15 = 178;
                goto LABEL_39;
              }
              if ( v18 > 0x40 )
              {
                if ( v18 > 0x100 )
                {
                  if ( v18 > 0x400 )
                  {
                    if ( v18 > 0x800 )
                    {
                      p_WaitListHead = 0;
                      Pool2 = (_DWORD *)ExAllocatePool2(64, v18, 808613750);
LABEL_28:
                      if ( Pool2 )
                      {
                        Pool2[2] = 808613750;
                        v12 = (char *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        memset(Pool2 + 4, 0, v17);
                        *(_OWORD *)v12 = *(_OWORD *)a2;
                        *((_OWORD *)v12 + 1) = *((_OWORD *)a2 + 1);
                        *((_OWORD *)v12 + 2) = *((_OWORD *)a2 + 2);
                        *((_OWORD *)v12 + 3) = *((_OWORD *)a2 + 3);
                        *((_OWORD *)v12 + 4) = *((_OWORD *)a2 + 4);
                        *((_QWORD *)v12 + 10) = *((_QWORD *)a2 + 10);
                        *((_DWORD *)v12 + 20) = 88;
                        *((_DWORD *)v12 + 21) = v16 + *((_DWORD *)a2 + 21);
                        memmove(v12 + 88, (char *)a2 + *((unsigned int *)a2 + 20), *((unsigned int *)a2 + 21));
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           8u,
                                           v23,
                                           (unsigned __int8 *)&v12[*((unsigned int *)a2 + 21) + 88]);
                        if ( !CachedFrameIEs )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_Dd(
                              WPP_GLOBAL_Control->AttachedDevice,
                              180,
                              WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                              *((unsigned int *)v12 + 20),
                              *((_DWORD *)v12 + 21));
                          }
                          v21 = v25;
                          *v8 = v17;
                          *v21 = (struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *)v12;
                          v12 = 0;
                          goto LABEL_40;
                        }
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
LABEL_40:
                          NdisReleaseRWLock(a1->pRWLock, &LockState);
                          if ( v12 )
                          {
                            if ( *((_QWORD *)v12 - 2) )
                              ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 16);
                            else
                              ExFreePoolWithTag(v12 - 16, *((_DWORD *)v12 - 2));
                          }
                          goto LABEL_46;
                        }
                        v15 = 179;
LABEL_39:
                        WPP_SF_(v14->AttachedDevice, v15, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                        goto LABEL_40;
                      }
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
              goto LABEL_28;
            }
          }
        }
      }
    }
  }
  CachedFrameIEs = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return CachedFrameIEs;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 175, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, CachedFrameIEs);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x14007a8fc  mov     r11, rsp
0x14007a8ff  mov     [r11+10h], rbx
0x14007a903  mov     [r11+20h], r9
0x14007a907  push    rbp
0x14007a908  push    rsi
0x14007a909  push    rdi
0x14007a90a  push    r12
0x14007a90c  push    r13
0x14007a90e  push    r14
0x14007a910  push    r15
0x14007a912  sub     rsp, 40h
0x14007a916  xor     ebx, ebx
0x14007a918  mov     esi, r8d
0x14007a91b  xor     eax, eax
0x14007a91d  mov     [rsp+78h+var_48], ebx
0x14007a921  mov     [r11+9], ax
0x14007a926  mov     rbp, rdx
0x14007a929  mov     r14, rcx
0x14007a92c  mov     [r11+8], bl
0x14007a930  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a937  lea     r15, WPP_GLOBAL_Control
0x14007a93e  cmp     rcx, r15
0x14007a941  jz      short loc_14007A960
0x14007a943  mov     rcx, [rcx+18h]
0x14007a947  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a94e  mov     edx, 0AEh
0x14007a953  call    WPP_SF_
0x14007a958  mov     r9, [rsp+78h+arg_18]
0x14007a960  test    r14, r14
0x14007a963  jz      loc_14007AC5D
0x14007a969  test    r9, r9
0x14007a96c  jz      loc_14007AC5D
0x14007a972  mov     r13, [rsp+78h+arg_20]
0x14007a97a  test    r13, r13
0x14007a97d  jz      loc_14007AC5D
0x14007a983  test    rbp, rbp
0x14007a986  jz      loc_14007AC5D
0x14007a98c  mov     ecx, [rbp+50h]
0x14007a98f  cmp     ecx, esi
0x14007a991  ja      loc_14007AC5D
0x14007a997  mov     edx, [rbp+54h]
0x14007a99a  add     edx, ecx
0x14007a99c  cmp     edx, ecx
0x14007a99e  jb      loc_14007AC5D
0x14007a9a4  cmp     edx, esi
0x14007a9a6  ja      loc_14007AC5D
0x14007a9ac  mov     rcx, [r14+20h]; Lock
0x14007a9b0  lea     rdx, [rsp+78h+LockState]; LockState
0x14007a9b8  xor     r8d, r8d; Flags
0x14007a9bb  mov     [r9], rbx
0x14007a9be  mov     rdi, rbx
0x14007a9c1  mov     [r13+0], ebx
0x14007a9c5  call    cs:__imp_NdisAcquireRWLockRead
0x14007a9cc  nop     dword ptr [rax+rax+00h]
0x14007a9d1  xor     r9d, r9d; unsigned __int8 *
0x14007a9d4  lea     r8, [rsp+78h+var_48]; unsigned int *
0x14007a9d9  mov     rcx, r14; struct _WFD_ROLE *
0x14007a9dc  lea     edx, [r9+8]; enum MANAGEMENT_FRAME_TYPE
0x14007a9e0  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007a9e5  mov     ebx, eax
0x14007a9e7  test    eax, eax
0x14007a9e9  jz      short loc_14007AA05
0x14007a9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a9f2  cmp     rcx, r15
0x14007a9f5  jz      loc_14007AC0F
0x14007a9fb  mov     edx, 0B0h
0x14007aa00  jmp     loc_14007ABFF
0x14007aa05  mov     r12d, [rsp+78h+var_48]
0x14007aa0a  test    r12d, r12d
0x14007aa0d  jz      loc_14007AC0F
0x14007aa13  lea     r15d, [r12+rsi]
0x14007aa17  cmp     r15d, esi
0x14007aa1a  jnb     short loc_14007AA5A
0x14007aa1c  mov     ebx, 0C0000095h
0x14007aa21  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aa28  lea     r15, WPP_GLOBAL_Control
0x14007aa2f  cmp     rcx, r15
0x14007aa32  jz      loc_14007AC0F
0x14007aa38  mov     rcx, [rcx+18h]
0x14007aa3c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007aa43  mov     edx, 0B1h
0x14007aa48  mov     [rsp+78h+var_58], r12d
0x14007aa4d  mov     r9d, esi
0x14007aa50  call    WPP_SF_Dd
0x14007aa55  jmp     loc_14007AC0F
0x14007aa5a  lea     eax, [r15+10h]
0x14007aa5e  cmp     eax, 10h
0x14007aa61  jb      loc_14007ABE0
0x14007aa67  mov     ecx, 40h ; '@'
0x14007aa6c  mov     edi, 30327776h
0x14007aa71  cmp     eax, ecx
0x14007aa73  ja      short loc_14007AA7E
0x14007aa75  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007aa7c  jmp     short loc_14007AAAC
0x14007aa7e  cmp     eax, 100h
0x14007aa83  ja      short loc_14007AA8E
0x14007aa85  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007aa8c  jmp     short loc_14007AAAC
0x14007aa8e  cmp     eax, 400h
0x14007aa93  ja      short loc_14007AA9E
0x14007aa95  lea     rbx, Lookaside
0x14007aa9c  jmp     short loc_14007AAAC
0x14007aa9e  cmp     eax, 800h
0x14007aaa3  ja      short loc_14007AABD
0x14007aaa5  lea     rbx, stru_1400B31C0
0x14007aaac  mov     rcx, rbx; Lookaside
0x14007aaaf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007aab6  nop     dword ptr [rax+rax+00h]
0x14007aabb  jmp     short loc_14007AAD0
0x14007aabd  xor     ebx, ebx
0x14007aabf  mov     edx, eax
0x14007aac1  mov     r8d, edi
0x14007aac4  call    cs:__imp_ExAllocatePool2
0x14007aacb  nop     dword ptr [rax+rax+00h]
0x14007aad0  test    rax, rax
0x14007aad3  jz      loc_14007ABE0
0x14007aad9  mov     [rax+8], edi
0x14007aadc  xor     edx, edx; Val
0x14007aade  lea     rdi, [rax+10h]
0x14007aae2  mov     r8d, r15d; Size
0x14007aae5  mov     rcx, rdi; void *
0x14007aae8  mov     [rax], rbx
0x14007aaeb  call    memset
0x14007aaf0  movups  xmm0, xmmword ptr [rbp+0]
0x14007aaf4  lea     rbx, [rdi+58h]
0x14007aaf8  movups  xmmword ptr [rdi], xmm0
0x14007aafb  movups  xmm1, xmmword ptr [rbp+10h]
0x14007aaff  movups  xmmword ptr [rdi+10h], xmm1
0x14007ab03  movups  xmm0, xmmword ptr [rbp+20h]
0x14007ab07  movups  xmmword ptr [rdi+20h], xmm0
0x14007ab0b  movups  xmm1, xmmword ptr [rbp+30h]
0x14007ab0f  movups  xmmword ptr [rdi+30h], xmm1
0x14007ab13  movups  xmm0, xmmword ptr [rbp+40h]
0x14007ab17  movups  xmmword ptr [rdi+40h], xmm0
0x14007ab1b  movsd   xmm1, qword ptr [rbp+50h]
0x14007ab20  movsd   qword ptr [rdi+50h], xmm1
0x14007ab25  mov     dword ptr [rdi+50h], 58h ; 'X'
0x14007ab2c  mov     ecx, [rbp+54h]
0x14007ab2f  add     ecx, r12d
0x14007ab32  mov     [rdi+54h], ecx
0x14007ab35  mov     rcx, rbx; void *
0x14007ab38  mov     edx, [rbp+50h]
0x14007ab3b  mov     r8d, [rbp+54h]; Size
0x14007ab3f  add     rdx, rbp; Src
0x14007ab42  call    memmove
0x14007ab47  mov     r9d, [rbp+54h]
0x14007ab4b  lea     r8, [rsp+78h+var_48]; unsigned int *
0x14007ab50  add     r9, rbx; unsigned __int8 *
0x14007ab53  mov     edx, 8; enum MANAGEMENT_FRAME_TYPE
0x14007ab58  mov     rcx, r14; struct _WFD_ROLE *
0x14007ab5b  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007ab60  mov     ebx, eax
0x14007ab62  test    eax, eax
0x14007ab64  jz      short loc_14007AB84
0x14007ab66  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ab6d  lea     r15, WPP_GLOBAL_Control
0x14007ab74  cmp     rcx, r15
0x14007ab77  jz      loc_14007AC0F
0x14007ab7d  mov     edx, 0B3h
0x14007ab82  jmp     short loc_14007ABFF
0x14007ab84  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ab8b  lea     rax, WPP_GLOBAL_Control
0x14007ab92  cmp     rcx, rax
0x14007ab95  jz      short loc_14007ABC6
0x14007ab97  cmp     byte ptr [rcx+29h], 3
0x14007ab9b  jb      short loc_14007ABC6
0x14007ab9d  test    dword ptr [rcx+2Ch], 200000h
0x14007aba4  jz      short loc_14007ABC6
0x14007aba6  mov     eax, [rdi+54h]
0x14007aba9  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007abb0  mov     r9d, [rdi+50h]
0x14007abb4  mov     edx, 0B4h
0x14007abb9  mov     rcx, [rcx+18h]
0x14007abbd  mov     [rsp+78h+var_58], eax
0x14007abc1  call    WPP_SF_Dd
0x14007abc6  mov     rax, [rsp+78h+arg_18]
0x14007abce  mov     [r13+0], r15d
0x14007abd2  lea     r15, WPP_GLOBAL_Control
0x14007abd9  mov     [rax], rdi
0x14007abdc  xor     edi, edi
0x14007abde  jmp     short loc_14007AC0F
0x14007abe0  xor     edi, edi
0x14007abe2  mov     ebx, 0C000009Ah
0x14007abe7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007abee  lea     r15, WPP_GLOBAL_Control
0x14007abf5  cmp     rcx, r15
0x14007abf8  jz      short loc_14007AC0F
0x14007abfa  mov     edx, 0B2h
0x14007abff  mov     rcx, [rcx+18h]
0x14007ac03  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007ac0a  call    WPP_SF_
0x14007ac0f  mov     rcx, [r14+20h]; Lock
0x14007ac13  lea     rdx, [rsp+78h+LockState]; LockState
0x14007ac1b  call    cs:__imp_NdisReleaseRWLock
0x14007ac22  nop     dword ptr [rax+rax+00h]
0x14007ac27  test    rdi, rdi
0x14007ac2a  jz      short loc_14007AC83
0x14007ac2c  lea     rcx, [rdi-10h]; P
0x14007ac30  mov     rax, [rcx]
0x14007ac33  test    rax, rax
0x14007ac36  jz      short loc_14007AC4C
0x14007ac38  mov     rdx, rcx; Entry
0x14007ac3b  mov     rcx, rax; Lookaside
0x14007ac3e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007ac45  nop     dword ptr [rax+rax+00h]
0x14007ac4a  jmp     short loc_14007AC83
0x14007ac4c  mov     edx, [rcx+8]; Tag
0x14007ac4f  call    cs:__imp_ExFreePoolWithTag
0x14007ac56  nop     dword ptr [rax+rax+00h]
0x14007ac5b  jmp     short loc_14007AC83
0x14007ac5d  mov     ebx, 0C000000Dh
0x14007ac62  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac69  cmp     rcx, r15
0x14007ac6c  jz      short loc_14007ACA7
0x14007ac6e  mov     rcx, [rcx+18h]
0x14007ac72  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007ac79  mov     edx, 0AFh
0x14007ac7e  call    WPP_SF_
0x14007ac83  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac8a  cmp     rcx, r15
0x14007ac8d  jz      short loc_14007ACA7
0x14007ac8f  mov     rcx, [rcx+18h]
0x14007ac93  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007ac9a  mov     edx, 0B5h
0x14007ac9f  mov     r9d, ebx
0x14007aca2  call    WPP_SF_d
0x14007aca7  mov     eax, ebx
0x14007aca9  mov     rbx, [rsp+78h+arg_8]
0x14007acb1  add     rsp, 40h
0x14007acb5  pop     r15
0x14007acb7  pop     r14
0x14007acb9  pop     r13
0x14007acbb  pop     r12
0x14007acbd  pop     rdi
0x14007acbe  pop     rsi
0x14007acbf  pop     rbp
0x14007acc0  retn
```
