# WFDRoleAddCachedIEsToDiscoverRequestOidStructure(_WFD_ROLE *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 * *,ulong *)

- ea: `0x14007a244`
- end: `0x14007a8f6`
- name: `?WFDRoleAddCachedIEsToDiscoverRequestOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAPEAU2@PEAK@Z`
- size: `1714`
- prototype: `unsigned int __usercall@<eax>(struct _WFD_ROLE *@<rcx>, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *@<rdx>, unsigned int@<r8d>, struct _DOT11_WFD_DISCOVER_REQUEST_V2 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140087ea0`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x14007a244`
- `0x14007b8bc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a443`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a443`
- `ntoskrnl!ExAllocatePool2` at `0x14007a458`
- `ntoskrnl!ExAllocatePool2` at `0x14007a458`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a3dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a3dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a883`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a883`
- `NDIS!NdisReleaseRWLock` at `0x14007a3b2`
- `NDIS!NdisReleaseRWLock` at `0x14007a3b2`
- `NDIS!NdisAcquireRWLockRead` at `0x14007a30d`
- `NDIS!NdisAcquireRWLockRead` at `0x14007a30d`

## pseudocode

```c
__int64 __fastcall WFDRoleAddCachedIEsToDiscoverRequestOidStructure(
        struct _WFD_ROLE *a1,
        struct _DOT11_WFD_DISCOVER_REQUEST_V2 *a2,
        unsigned int a3,
        struct _DOT11_WFD_DISCOVER_REQUEST_V2 **a4,
        unsigned int *a5)
{
  struct _WFD_ROLE *v7; // rbp
  unsigned int v8; // ecx
  unsigned int v9; // edx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  char *v11; // r14
  unsigned int CachedFrameIEs; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // r13d
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int64 v25; // r9
  __int64 v26; // r9
  int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  unsigned __int8 *v30; // rbx
  unsigned __int8 *v31; // rbp
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v39[17]; // [rsp+34h] [rbp-44h] BYREF
  struct _DOT11_WFD_DISCOVER_REQUEST_V2 **v41; // [rsp+98h] [rbp+20h]

  v41 = a4;
  LockState.OldIrql = 0;
  v39[0] = 0;
  v7 = a1;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = v41;
  }
  if ( v7 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        if ( a2 )
        {
          v8 = *((_DWORD *)a2 + 6);
          if ( v8 <= a3 )
          {
            v9 = v8 + *((_DWORD *)a2 + 7);
            if ( v9 >= v8 && v9 <= a3 )
            {
              pRWLock = v7->pRWLock;
              *a4 = 0;
              v11 = 0;
              *a5 = 0;
              NdisAcquireRWLockRead(pRWLock, &LockState, 0);
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(v7, 1u, v39, 0);
              if ( CachedFrameIEs )
              {
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_19;
                v14 = 184;
                goto LABEL_13;
              }
              v15 = v39[0];
              if ( !v39[0] )
                goto LABEL_19;
              v16 = v39[0] + a3;
              if ( v39[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_19;
                v18 = 185;
                v19 = a3;
                goto LABEL_18;
              }
              v20 = v16 + 16;
              if ( v16 >= 0xFFFFFFF0 )
                goto LABEL_92;
              if ( v20 > 0x40 )
              {
                if ( v20 > 0x100 )
                {
                  if ( v20 > 0x400 )
                  {
                    if ( v20 > 0x800 )
                    {
                      p_WaitListHead = 0;
                      Pool2 = (_DWORD *)ExAllocatePool2(64, v20, 808613750);
LABEL_33:
                      if ( Pool2 )
                      {
                        v11 = (char *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        Pool2[2] = 808613750;
                        memset(Pool2 + 4, 0, v16);
                        *(_OWORD *)v11 = *(_OWORD *)a2;
                        *((_OWORD *)v11 + 1) = *((_OWORD *)a2 + 1);
                        *((_OWORD *)v11 + 2) = *((_OWORD *)a2 + 2);
                        *((_OWORD *)v11 + 3) = *((_OWORD *)a2 + 3);
                        *((_OWORD *)v11 + 4) = *((_OWORD *)a2 + 4);
                        *((_OWORD *)v11 + 5) = *((_OWORD *)a2 + 5);
                        *((_DWORD *)v11 + 24) = *((_DWORD *)a2 + 24);
                        *((_DWORD *)v11 + 6) = 100;
                        v23 = v15 + *((_DWORD *)a2 + 7);
                        *((_DWORD *)v11 + 7) = v23;
                        v24 = v23 + 100;
                        if ( *((_DWORD *)a2 + 5) )
                        {
                          *((_DWORD *)v11 + 4) = v24;
                          v25 = *((unsigned int *)a2 + 5);
                          v15 = 44 * v25;
                          if ( (unsigned __int64)(44 * v25) > 0xFFFFFFFF )
                          {
                            CachedFrameIEs = -1073741675;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                187,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v25,
                                44);
                            goto LABEL_19;
                          }
                          v26 = v15 + v24;
                          if ( (unsigned int)v26 < v24 )
                          {
                            CachedFrameIEs = -1073741675;
                            v17 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              v18 = 188;
                              v19 = 0xFFFFFFFFLL;
LABEL_18:
                              WPP_SF_Dd(
                                v17->AttachedDevice,
                                v18,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v19,
                                v15);
                            }
LABEL_19:
                            NdisReleaseRWLock(v7->pRWLock, &LockState);
                            if ( v11 )
                            {
                              if ( *((_QWORD *)v11 - 2) )
                                ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 16);
                              else
                                ExFreePoolWithTag(v11 - 16, *((_DWORD *)v11 - 2));
                            }
                            goto LABEL_97;
                          }
                        }
                        else
                        {
                          v15 = 0;
                          v26 = v24;
                        }
                        if ( *((_DWORD *)a2 + 12) )
                        {
                          *((_DWORD *)v11 + 11) = v26;
                          v27 = *((_DWORD *)a2 + 12);
                          if ( v27 + (int)v26 < (unsigned int)v26 )
                          {
                            CachedFrameIEs = -1073741675;
                            v28 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v29 = 189;
                            goto LABEL_63;
                          }
                          v26 = (unsigned int)(v27 + v26);
                        }
                        if ( *((_DWORD *)a2 + 15) )
                        {
                          *((_DWORD *)v11 + 14) = v26;
                          v27 = *((_DWORD *)a2 + 15);
                          if ( v27 + (int)v26 < (unsigned int)v26 )
                          {
                            CachedFrameIEs = -1073741675;
                            v28 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v29 = 190;
                            goto LABEL_63;
                          }
                          v26 = (unsigned int)(v27 + v26);
                        }
                        if ( *((_DWORD *)a2 + 18) )
                        {
                          *((_DWORD *)v11 + 17) = v26;
                          v27 = *((_DWORD *)a2 + 18);
                          if ( v27 + (int)v26 < (unsigned int)v26 )
                          {
                            CachedFrameIEs = -1073741675;
                            v28 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v29 = 191;
                            goto LABEL_63;
                          }
                          v26 = (unsigned int)(v27 + v26);
                        }
                        if ( *((_DWORD *)a2 + 21) )
                        {
                          *((_DWORD *)v11 + 20) = v26;
                          v27 = *((_DWORD *)a2 + 21);
                          if ( v27 + (int)v26 < (unsigned int)v26 )
                          {
                            CachedFrameIEs = -1073741675;
                            v28 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v29 = 192;
                            goto LABEL_63;
                          }
                          v26 = (unsigned int)(v27 + v26);
                        }
                        if ( !*((_DWORD *)a2 + 23) )
                        {
LABEL_58:
                          if ( (unsigned int)v26 > v16 )
                          {
                            CachedFrameIEs = -1073741811;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                194,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v26,
                                v16);
                            goto LABEL_19;
                          }
                          memmove(v11 + 100, (char *)a2 + *((unsigned int *)a2 + 6), *((unsigned int *)a2 + 7));
                          v30 = (unsigned __int8 *)&v11[*((unsigned int *)a2 + 7) + 100];
                          CachedFrameIEs = WFDRoleGetCachedFrameIEs(v7, 1u, v39, v30);
                          if ( !CachedFrameIEs )
                          {
                            v31 = &v30[v39[0]];
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                            {
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                196,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                *((unsigned int *)v11 + 6),
                                *((_DWORD *)v11 + 7));
                            }
                            if ( *((_DWORD *)a2 + 5) )
                            {
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 4), v15);
                              v31 += v15;
                            }
                            v32 = *((_DWORD *)a2 + 12);
                            if ( v32 )
                            {
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 11), v32);
                              v31 += *((unsigned int *)a2 + 12);
                            }
                            v33 = *((_DWORD *)a2 + 15);
                            if ( v33 )
                            {
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 14), v33);
                              v31 += *((unsigned int *)a2 + 15);
                            }
                            v34 = *((_DWORD *)a2 + 18);
                            if ( v34 )
                            {
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 17), v34);
                              v31 += *((unsigned int *)a2 + 18);
                            }
                            v35 = *((_DWORD *)a2 + 21);
                            if ( v35 )
                            {
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 20), v35);
                              v31 += *((unsigned int *)a2 + 21);
                            }
                            v36 = *((_DWORD *)a2 + 23);
                            if ( v36 )
                              memmove(v31, (char *)a2 + *((unsigned int *)a2 + 22), v36);
                            v7 = a1;
                            *a5 = v16;
                            *v41 = (struct _DOT11_WFD_DISCOVER_REQUEST_V2 *)v11;
                            v11 = 0;
                            goto LABEL_19;
                          }
                          v13 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            goto LABEL_19;
                          v14 = 195;
LABEL_13:
                          WPP_SF_(v13->AttachedDevice, v14, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                          goto LABEL_19;
                        }
                        *((_DWORD *)v11 + 22) = v26;
                        v27 = *((_DWORD *)a2 + 23);
                        if ( v27 + (int)v26 >= (unsigned int)v26 )
                        {
                          v26 = (unsigned int)(v27 + v26);
                          goto LABEL_58;
                        }
                        CachedFrameIEs = -1073741675;
                        v28 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          goto LABEL_19;
                        v29 = 193;
LABEL_63:
                        WPP_SF_Dd(
                          v28->AttachedDevice,
                          v29,
                          WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                          0xFFFFFFFFLL,
                          v27);
                        goto LABEL_19;
                      }
LABEL_92:
                      CachedFrameIEs = -1073741670;
                      v13 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_19;
                      v14 = 186;
                      goto LABEL_13;
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
              goto LABEL_33;
            }
          }
        }
      }
    }
  }
  CachedFrameIEs = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return CachedFrameIEs;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 183, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_97:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, CachedFrameIEs);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x14007a244  mov     rax, rsp
0x14007a247  mov     [rax+10h], rbx
0x14007a24b  mov     [rax+20h], r9
0x14007a24f  mov     [rax+8], rcx
0x14007a253  push    rbp
0x14007a254  push    rsi
0x14007a255  push    rdi
0x14007a256  push    r12
0x14007a258  push    r13
0x14007a25a  push    r14
0x14007a25c  push    r15
0x14007a25e  sub     rsp, 40h
0x14007a262  xor     edi, edi
0x14007a264  mov     ebx, r8d
0x14007a267  mov     [rax-48h], dil
0x14007a26b  mov     rsi, rdx
0x14007a26e  mov     [rax-44h], edi
0x14007a271  mov     rbp, rcx
0x14007a274  xor     eax, eax
0x14007a276  mov     word ptr [rsp+78h+LockState.LockState], ax
0x14007a27b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a282  lea     r15, WPP_GLOBAL_Control
0x14007a289  cmp     rcx, r15
0x14007a28c  jz      short loc_14007A2AB
0x14007a28e  mov     rcx, [rcx+18h]
0x14007a292  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a299  mov     edx, 0B6h
0x14007a29e  call    WPP_SF_
0x14007a2a3  mov     r9, [rsp+78h+arg_18]
0x14007a2ab  test    rbp, rbp
0x14007a2ae  jz      loc_14007A891
0x14007a2b4  test    r9, r9
0x14007a2b7  jz      loc_14007A891
0x14007a2bd  mov     r12, [rsp+78h+arg_20]
0x14007a2c5  test    r12, r12
0x14007a2c8  jz      loc_14007A891
0x14007a2ce  test    rsi, rsi
0x14007a2d1  jz      loc_14007A891
0x14007a2d7  mov     ecx, [rsi+18h]
0x14007a2da  cmp     ecx, ebx
0x14007a2dc  ja      loc_14007A891
0x14007a2e2  mov     edx, [rsi+1Ch]
0x14007a2e5  add     edx, ecx
0x14007a2e7  cmp     edx, ecx
0x14007a2e9  jb      loc_14007A891
0x14007a2ef  cmp     edx, ebx
0x14007a2f1  ja      loc_14007A891
0x14007a2f7  mov     rcx, [rbp+20h]; Lock
0x14007a2fb  lea     rdx, [rsp+78h+LockState]; LockState
0x14007a300  xor     r8d, r8d; Flags
0x14007a303  mov     [r9], rdi
0x14007a306  mov     r14, rdi
0x14007a309  mov     [r12], edi
0x14007a30d  call    cs:__imp_NdisAcquireRWLockRead
0x14007a314  nop     dword ptr [rax+rax+00h]
0x14007a319  xor     r9d, r9d; unsigned __int8 *
0x14007a31c  lea     r8, [rsp+78h+var_44]; unsigned int *
0x14007a321  mov     rcx, rbp; struct _WFD_ROLE *
0x14007a324  lea     edx, [r9+1]; enum MANAGEMENT_FRAME_TYPE
0x14007a328  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007a32d  mov     edi, eax
0x14007a32f  test    eax, eax
0x14007a331  jz      short loc_14007A356
0x14007a333  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a33a  cmp     rcx, r15
0x14007a33d  jz      short loc_14007A3A9
0x14007a33f  mov     edx, 0B8h
0x14007a344  mov     rcx, [rcx+18h]
0x14007a348  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a34f  call    WPP_SF_
0x14007a354  jmp     short loc_14007A3A9
0x14007a356  mov     r15d, [rsp+78h+var_44]
0x14007a35b  test    r15d, r15d
0x14007a35e  jz      short loc_14007A3A2
0x14007a360  lea     r13d, [r15+rbx]
0x14007a364  cmp     r13d, ebx
0x14007a367  jnb     loc_14007A3EE
0x14007a36d  mov     edi, 0C0000095h
0x14007a372  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a379  lea     rax, WPP_GLOBAL_Control
0x14007a380  cmp     rcx, rax
0x14007a383  jz      short loc_14007A3A2
0x14007a385  mov     edx, 0B9h
0x14007a38a  mov     r9d, ebx
0x14007a38d  mov     rcx, [rcx+18h]
0x14007a391  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a398  mov     [rsp+78h+var_58], r15d
0x14007a39d  call    WPP_SF_Dd
0x14007a3a2  lea     r15, WPP_GLOBAL_Control
0x14007a3a9  mov     rcx, [rbp+20h]; Lock
0x14007a3ad  lea     rdx, [rsp+78h+LockState]; LockState
0x14007a3b2  call    cs:__imp_NdisReleaseRWLock
0x14007a3b9  nop     dword ptr [rax+rax+00h]
0x14007a3be  test    r14, r14
0x14007a3c1  jz      loc_14007A8B7
0x14007a3c7  lea     rcx, [r14-10h]; P
0x14007a3cb  mov     rax, [rcx]
0x14007a3ce  test    rax, rax
0x14007a3d1  jz      loc_14007A880
0x14007a3d7  mov     rdx, rcx; Entry
0x14007a3da  mov     rcx, rax; Lookaside
0x14007a3dd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007a3e4  nop     dword ptr [rax+rax+00h]
0x14007a3e9  jmp     loc_14007A8B7
0x14007a3ee  lea     eax, [r13+10h]
0x14007a3f2  cmp     eax, 10h
0x14007a3f5  jb      loc_14007A85A
0x14007a3fb  mov     ecx, 40h ; '@'
0x14007a400  mov     edi, 30327776h
0x14007a405  cmp     eax, ecx
0x14007a407  ja      short loc_14007A412
0x14007a409  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007a410  jmp     short loc_14007A440
0x14007a412  cmp     eax, 100h
0x14007a417  ja      short loc_14007A422
0x14007a419  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007a420  jmp     short loc_14007A440
0x14007a422  cmp     eax, 400h
0x14007a427  ja      short loc_14007A432
0x14007a429  lea     rbx, Lookaside
0x14007a430  jmp     short loc_14007A440
0x14007a432  cmp     eax, 800h
0x14007a437  ja      short loc_14007A451
0x14007a439  lea     rbx, stru_1400B31C0
0x14007a440  mov     rcx, rbx; Lookaside
0x14007a443  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007a44a  nop     dword ptr [rax+rax+00h]
0x14007a44f  jmp     short loc_14007A464
0x14007a451  xor     ebx, ebx
0x14007a453  mov     edx, eax
0x14007a455  mov     r8d, edi
0x14007a458  call    cs:__imp_ExAllocatePool2
0x14007a45f  nop     dword ptr [rax+rax+00h]
0x14007a464  test    rax, rax
0x14007a467  jz      loc_14007A85A
0x14007a46d  lea     r14, [rax+10h]
0x14007a471  mov     r8d, r13d; Size
0x14007a474  mov     rcx, r14; void *
0x14007a477  mov     [rax], rbx
0x14007a47a  xor     edx, edx; Val
0x14007a47c  mov     [rax+8], edi
0x14007a47f  call    memset
0x14007a484  movups  xmm0, xmmword ptr [rsi]
0x14007a487  mov     r8d, 0FFFFFFFFh
0x14007a48d  movups  xmmword ptr [r14], xmm0
0x14007a491  movups  xmm1, xmmword ptr [rsi+10h]
0x14007a495  movups  xmmword ptr [r14+10h], xmm1
0x14007a49a  movups  xmm0, xmmword ptr [rsi+20h]
0x14007a49e  movups  xmmword ptr [r14+20h], xmm0
0x14007a4a3  movups  xmm1, xmmword ptr [rsi+30h]
0x14007a4a7  movups  xmmword ptr [r14+30h], xmm1
0x14007a4ac  movups  xmm0, xmmword ptr [rsi+40h]
0x14007a4b0  movups  xmmword ptr [r14+40h], xmm0
0x14007a4b5  movups  xmm1, xmmword ptr [rsi+50h]
0x14007a4b9  movups  xmmword ptr [r14+50h], xmm1
0x14007a4be  mov     eax, [rsi+60h]
0x14007a4c1  mov     [r14+60h], eax
0x14007a4c5  mov     dword ptr [r14+18h], 64h ; 'd'
0x14007a4cd  mov     ecx, [rsi+1Ch]
0x14007a4d0  add     ecx, r15d
0x14007a4d3  mov     [r14+1Ch], ecx
0x14007a4d7  add     ecx, 64h ; 'd'
0x14007a4da  cmp     dword ptr [rsi+14h], 0
0x14007a4de  jbe     loc_14007A565
0x14007a4e4  mov     [r14+10h], ecx
0x14007a4e8  mov     r9d, [rsi+14h]
0x14007a4ec  imul    r15, r9, 2Ch ; ','
0x14007a4f0  cmp     r15, r8
0x14007a4f3  ja      short loc_14007A527
0x14007a4f5  lea     r9d, [r15+rcx]
0x14007a4f9  cmp     r9d, ecx
0x14007a4fc  jnb     short loc_14007A56B
0x14007a4fe  mov     edi, 0C0000095h
0x14007a503  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a50a  lea     rax, WPP_GLOBAL_Control
0x14007a511  cmp     rcx, rax
0x14007a514  jz      loc_14007A3A2
0x14007a51a  mov     edx, 0BCh
0x14007a51f  mov     r9d, r8d
0x14007a522  jmp     loc_14007A38D
0x14007a527  mov     edi, 0C0000095h
0x14007a52c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a533  lea     r15, WPP_GLOBAL_Control
0x14007a53a  cmp     rcx, r15
0x14007a53d  jz      loc_14007A3A9
0x14007a543  mov     edx, 0BBh
0x14007a548  mov     [rsp+78h+var_58], 2Ch ; ','
0x14007a550  mov     rcx, [rcx+18h]
0x14007a554  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a55b  call    WPP_SF_Dd
0x14007a560  jmp     loc_14007A3A9
0x14007a565  xor     r15d, r15d
0x14007a568  mov     r9d, ecx
0x14007a56b  cmp     dword ptr [rsi+30h], 0
0x14007a56f  jbe     short loc_14007A588
0x14007a571  mov     [r14+2Ch], r9d
0x14007a575  mov     eax, [rsi+30h]
0x14007a578  lea     ecx, [rax+r9]
0x14007a57c  cmp     ecx, r9d
0x14007a57f  jb      loc_14007A630
0x14007a585  mov     r9d, ecx
0x14007a588  cmp     dword ptr [rsi+3Ch], 0
0x14007a58c  jbe     short loc_14007A5A5
0x14007a58e  mov     [r14+38h], r9d
0x14007a592  mov     eax, [rsi+3Ch]
0x14007a595  lea     ecx, [rax+r9]
0x14007a599  cmp     ecx, r9d
0x14007a59c  jb      loc_14007A65D
0x14007a5a2  mov     r9d, ecx
0x14007a5a5  cmp     dword ptr [rsi+48h], 0
0x14007a5a9  jbe     short loc_14007A5C2
0x14007a5ab  mov     [r14+44h], r9d
0x14007a5af  mov     eax, [rsi+48h]
0x14007a5b2  lea     ecx, [rax+r9]
0x14007a5b6  cmp     ecx, r9d
0x14007a5b9  jb      loc_14007A680
0x14007a5bf  mov     r9d, ecx
0x14007a5c2  cmp     dword ptr [rsi+54h], 0
0x14007a5c6  jbe     short loc_14007A5DF
0x14007a5c8  mov     [r14+50h], r9d
0x14007a5cc  mov     eax, [rsi+54h]
0x14007a5cf  lea     ecx, [rax+r9]
0x14007a5d3  cmp     ecx, r9d
0x14007a5d6  jb      loc_14007A6A3
0x14007a5dc  mov     r9d, ecx
0x14007a5df  cmp     dword ptr [rsi+5Ch], 0
0x14007a5e3  jbe     short loc_14007A5FC
0x14007a5e5  mov     [r14+58h], r9d
0x14007a5e9  mov     eax, [rsi+5Ch]
0x14007a5ec  lea     ecx, [rax+r9]
0x14007a5f0  cmp     ecx, r9d
0x14007a5f3  jb      loc_14007A6C6
0x14007a5f9  mov     r9d, ecx
0x14007a5fc  cmp     r9d, r13d
0x14007a5ff  jbe     loc_14007A6EC
0x14007a605  mov     edi, 0C000000Dh
0x14007a60a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a611  lea     r15, WPP_GLOBAL_Control
0x14007a618  cmp     rcx, r15
0x14007a61b  jz      loc_14007A3A9
0x14007a621  mov     edx, 0C2h
0x14007a626  mov     [rsp+78h+var_58], r13d
0x14007a62b  jmp     loc_14007A550
0x14007a630  mov     edi, 0C0000095h
0x14007a635  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a63c  lea     r15, WPP_GLOBAL_Control
0x14007a643  cmp     rcx, r15
0x14007a646  jz      loc_14007A3A9
0x14007a64c  mov     edx, 0BDh
0x14007a651  mov     [rsp+78h+var_58], eax
0x14007a655  mov     r9d, r8d
0x14007a658  jmp     loc_14007A550
0x14007a65d  mov     edi, 0C0000095h
0x14007a662  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a669  lea     r15, WPP_GLOBAL_Control
0x14007a670  cmp     rcx, r15
0x14007a673  jz      loc_14007A3A9
0x14007a679  mov     edx, 0BEh
0x14007a67e  jmp     short loc_14007A651
0x14007a680  mov     edi, 0C0000095h
0x14007a685  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a68c  lea     r15, WPP_GLOBAL_Control
0x14007a693  cmp     rcx, r15
0x14007a696  jz      loc_14007A3A9
0x14007a69c  mov     edx, 0BFh
0x14007a6a1  jmp     short loc_14007A651
0x14007a6a3  mov     edi, 0C0000095h
0x14007a6a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6af  lea     r15, WPP_GLOBAL_Control
0x14007a6b6  cmp     rcx, r15
0x14007a6b9  jz      loc_14007A3A9
0x14007a6bf  mov     edx, 0C0h
0x14007a6c4  jmp     short loc_14007A651
0x14007a6c6  mov     edi, 0C0000095h
0x14007a6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6d2  lea     r15, WPP_GLOBAL_Control
0x14007a6d9  cmp     rcx, r15
0x14007a6dc  jz      loc_14007A3A9
0x14007a6e2  mov     edx, 0C1h
0x14007a6e7  jmp     loc_14007A651
0x14007a6ec  mov     edx, [rsi+18h]
0x14007a6ef  lea     rbx, [r14+64h]
0x14007a6f3  mov     r8d, [rsi+1Ch]; Size
0x14007a6f7  add     rdx, rsi; Src
0x14007a6fa  mov     rcx, rbx; void *
0x14007a6fd  call    memmove
0x14007a702  mov     eax, [rsi+1Ch]
0x14007a705  lea     r8, [rsp+78h+var_44]; unsigned int *
0x14007a70a  add     rbx, rax
0x14007a70d  mov     edx, 1; enum MANAGEMENT_FRAME_TYPE
0x14007a712  mov     r9, rbx; unsigned __int8 *
0x14007a715  mov     rcx, rbp; struct _WFD_ROLE *
0x14007a718  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007a71d  mov     edi, eax
0x14007a71f  test    eax, eax
0x14007a721  jz      short loc_14007A744
0x14007a723  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a72a  lea     r15, WPP_GLOBAL_Control
0x14007a731  cmp     rcx, r15
0x14007a734  jz      loc_14007A3A9
  ... truncated ...
```
