# WFDRoleAddCachedIEsToDiscoverRequestOidStructure(_WFD_ROLE *,_DOT11_WFD_DISCOVER_REQUEST_V2 *,ulong,_DOT11_WFD_DISCOVER_REQUEST_V2 * *,ulong *)

- ea: `0x140078a14`
- end: `0x1400790c6`
- name: `?WFDRoleAddCachedIEsToDiscoverRequestOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_WFD_DISCOVER_REQUEST_V2@@KPEAPEAU2@PEAK@Z`
- size: `1714`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, struct _DOT11_WFD_DISCOVER_REQUEST_V2 *, unsigned int, struct _DOT11_WFD_DISCOVER_REQUEST_V2 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140086670`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140078a14`
- `0x14007a08c`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140078c13`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140078c13`
- `ntoskrnl!ExAllocatePool2` at `0x140078c28`
- `ntoskrnl!ExAllocatePool2` at `0x140078c28`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078bad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078bad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079053`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079053`
- `NDIS!NdisReleaseRWLock` at `0x140078b82`
- `NDIS!NdisReleaseRWLock` at `0x140078b82`
- `NDIS!NdisAcquireRWLockRead` at `0x140078add`
- `NDIS!NdisAcquireRWLockRead` at `0x140078add`

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
  __int64 v13; // r9
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r15d
  unsigned int v17; // r13d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // r9
  __int64 v27; // r9
  int v28; // eax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  unsigned __int8 *v31; // rbx
  unsigned __int8 *v32; // rbp
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v40[17]; // [rsp+34h] [rbp-44h] BYREF
  struct _DOT11_WFD_DISCOVER_REQUEST_V2 **v42; // [rsp+98h] [rbp+20h]

  v42 = a4;
  LockState.OldIrql = 0;
  v40[0] = 0;
  v7 = a1;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = v42;
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
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(v7, 1u, v40, 0);
              if ( CachedFrameIEs )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_19;
                v15 = 184;
                goto LABEL_13;
              }
              v16 = v40[0];
              if ( !v40[0] )
                goto LABEL_19;
              v17 = v40[0] + a3;
              if ( v40[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_19;
                v19 = 185;
                v20 = a3;
                goto LABEL_18;
              }
              v21 = v17 + 16;
              if ( v17 >= 0xFFFFFFF0 )
                goto LABEL_92;
              if ( v21 > 0x40 )
              {
                if ( v21 > 0x100 )
                {
                  if ( v21 > 0x400 )
                  {
                    if ( v21 > 0x800 )
                    {
                      p_WaitListHead = 0;
                      Pool2 = (_DWORD *)ExAllocatePool2(64, v21, 808613750, v13);
LABEL_33:
                      if ( Pool2 )
                      {
                        v11 = (char *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        Pool2[2] = 808613750;
                        memset(Pool2 + 4, 0, v17);
                        *(_OWORD *)v11 = *(_OWORD *)a2;
                        *((_OWORD *)v11 + 1) = *((_OWORD *)a2 + 1);
                        *((_OWORD *)v11 + 2) = *((_OWORD *)a2 + 2);
                        *((_OWORD *)v11 + 3) = *((_OWORD *)a2 + 3);
                        *((_OWORD *)v11 + 4) = *((_OWORD *)a2 + 4);
                        *((_OWORD *)v11 + 5) = *((_OWORD *)a2 + 5);
                        *((_DWORD *)v11 + 24) = *((_DWORD *)a2 + 24);
                        *((_DWORD *)v11 + 6) = 100;
                        v24 = v16 + *((_DWORD *)a2 + 7);
                        *((_DWORD *)v11 + 7) = v24;
                        v25 = v24 + 100;
                        if ( *((_DWORD *)a2 + 5) )
                        {
                          *((_DWORD *)v11 + 4) = v25;
                          v26 = *((unsigned int *)a2 + 5);
                          v16 = 44 * v26;
                          if ( (unsigned __int64)(44 * v26) > 0xFFFFFFFF )
                          {
                            CachedFrameIEs = -1073741675;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                187,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v26,
                                44);
                            goto LABEL_19;
                          }
                          v27 = v16 + v25;
                          if ( (unsigned int)v27 < v25 )
                          {
                            CachedFrameIEs = -1073741675;
                            v18 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              v19 = 188;
                              v20 = 0xFFFFFFFFLL;
LABEL_18:
                              WPP_SF_Dd(
                                v18->AttachedDevice,
                                v19,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v20,
                                v16);
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
                          v16 = 0;
                          v27 = v25;
                        }
                        if ( *((_DWORD *)a2 + 12) )
                        {
                          *((_DWORD *)v11 + 11) = v27;
                          v28 = *((_DWORD *)a2 + 12);
                          if ( v28 + (int)v27 < (unsigned int)v27 )
                          {
                            CachedFrameIEs = -1073741675;
                            v29 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v30 = 189;
                            goto LABEL_63;
                          }
                          v27 = (unsigned int)(v28 + v27);
                        }
                        if ( *((_DWORD *)a2 + 15) )
                        {
                          *((_DWORD *)v11 + 14) = v27;
                          v28 = *((_DWORD *)a2 + 15);
                          if ( v28 + (int)v27 < (unsigned int)v27 )
                          {
                            CachedFrameIEs = -1073741675;
                            v29 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v30 = 190;
                            goto LABEL_63;
                          }
                          v27 = (unsigned int)(v28 + v27);
                        }
                        if ( *((_DWORD *)a2 + 18) )
                        {
                          *((_DWORD *)v11 + 17) = v27;
                          v28 = *((_DWORD *)a2 + 18);
                          if ( v28 + (int)v27 < (unsigned int)v27 )
                          {
                            CachedFrameIEs = -1073741675;
                            v29 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v30 = 191;
                            goto LABEL_63;
                          }
                          v27 = (unsigned int)(v28 + v27);
                        }
                        if ( *((_DWORD *)a2 + 21) )
                        {
                          *((_DWORD *)v11 + 20) = v27;
                          v28 = *((_DWORD *)a2 + 21);
                          if ( v28 + (int)v27 < (unsigned int)v27 )
                          {
                            CachedFrameIEs = -1073741675;
                            v29 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              goto LABEL_19;
                            v30 = 192;
                            goto LABEL_63;
                          }
                          v27 = (unsigned int)(v28 + v27);
                        }
                        if ( !*((_DWORD *)a2 + 23) )
                        {
LABEL_58:
                          if ( (unsigned int)v27 > v17 )
                          {
                            CachedFrameIEs = -1073741811;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              WPP_SF_Dd(
                                WPP_GLOBAL_Control->AttachedDevice,
                                194,
                                WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                                v27,
                                v17);
                            goto LABEL_19;
                          }
                          memmove(v11 + 100, (char *)a2 + *((unsigned int *)a2 + 6), *((unsigned int *)a2 + 7));
                          v31 = (unsigned __int8 *)&v11[*((unsigned int *)a2 + 7) + 100];
                          CachedFrameIEs = WFDRoleGetCachedFrameIEs(v7, 1u, v40, v31);
                          if ( !CachedFrameIEs )
                          {
                            v32 = &v31[v40[0]];
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
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 4), v16);
                              v32 += v16;
                            }
                            v33 = *((_DWORD *)a2 + 12);
                            if ( v33 )
                            {
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 11), v33);
                              v32 += *((unsigned int *)a2 + 12);
                            }
                            v34 = *((_DWORD *)a2 + 15);
                            if ( v34 )
                            {
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 14), v34);
                              v32 += *((unsigned int *)a2 + 15);
                            }
                            v35 = *((_DWORD *)a2 + 18);
                            if ( v35 )
                            {
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 17), v35);
                              v32 += *((unsigned int *)a2 + 18);
                            }
                            v36 = *((_DWORD *)a2 + 21);
                            if ( v36 )
                            {
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 20), v36);
                              v32 += *((unsigned int *)a2 + 21);
                            }
                            v37 = *((_DWORD *)a2 + 23);
                            if ( v37 )
                              memmove(v32, (char *)a2 + *((unsigned int *)a2 + 22), v37);
                            v7 = a1;
                            *a5 = v17;
                            *v42 = (struct _DOT11_WFD_DISCOVER_REQUEST_V2 *)v11;
                            v11 = 0;
                            goto LABEL_19;
                          }
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            goto LABEL_19;
                          v15 = 195;
LABEL_13:
                          WPP_SF_(v14->AttachedDevice, v15, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                          goto LABEL_19;
                        }
                        *((_DWORD *)v11 + 22) = v27;
                        v28 = *((_DWORD *)a2 + 23);
                        if ( v28 + (int)v27 >= (unsigned int)v27 )
                        {
                          v27 = (unsigned int)(v28 + v27);
                          goto LABEL_58;
                        }
                        CachedFrameIEs = -1073741675;
                        v29 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          goto LABEL_19;
                        v30 = 193;
LABEL_63:
                        WPP_SF_Dd(
                          v29->AttachedDevice,
                          v30,
                          WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                          0xFFFFFFFFLL,
                          v28);
                        goto LABEL_19;
                      }
LABEL_92:
                      CachedFrameIEs = -1073741670;
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        goto LABEL_19;
                      v15 = 186;
                      goto LABEL_13;
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
0x140078a14  mov     rax, rsp
0x140078a17  mov     [rax+10h], rbx
0x140078a1b  mov     [rax+20h], r9
0x140078a1f  mov     [rax+8], rcx
0x140078a23  push    rbp
0x140078a24  push    rsi
0x140078a25  push    rdi
0x140078a26  push    r12
0x140078a28  push    r13
0x140078a2a  push    r14
0x140078a2c  push    r15
0x140078a2e  sub     rsp, 40h
0x140078a32  xor     edi, edi
0x140078a34  mov     ebx, r8d
0x140078a37  mov     [rax-48h], dil
0x140078a3b  mov     rsi, rdx
0x140078a3e  mov     [rax-44h], edi
0x140078a41  mov     rbp, rcx
0x140078a44  xor     eax, eax
0x140078a46  mov     word ptr [rsp+78h+LockState.LockState], ax
0x140078a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140078a52  lea     r15, WPP_GLOBAL_Control
0x140078a59  cmp     rcx, r15
0x140078a5c  jz      short loc_140078A7B
0x140078a5e  mov     rcx, [rcx+18h]
0x140078a62  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078a69  mov     edx, 0B6h
0x140078a6e  call    WPP_SF_
0x140078a73  mov     r9, [rsp+78h+arg_18]
0x140078a7b  test    rbp, rbp
0x140078a7e  jz      loc_140079061
0x140078a84  test    r9, r9
0x140078a87  jz      loc_140079061
0x140078a8d  mov     r12, [rsp+78h+arg_20]
0x140078a95  test    r12, r12
0x140078a98  jz      loc_140079061
0x140078a9e  test    rsi, rsi
0x140078aa1  jz      loc_140079061
0x140078aa7  mov     ecx, [rsi+18h]
0x140078aaa  cmp     ecx, ebx
0x140078aac  ja      loc_140079061
0x140078ab2  mov     edx, [rsi+1Ch]
0x140078ab5  add     edx, ecx
0x140078ab7  cmp     edx, ecx
0x140078ab9  jb      loc_140079061
0x140078abf  cmp     edx, ebx
0x140078ac1  ja      loc_140079061
0x140078ac7  mov     rcx, [rbp+20h]; Lock
0x140078acb  lea     rdx, [rsp+78h+LockState]; LockState
0x140078ad0  xor     r8d, r8d; Flags
0x140078ad3  mov     [r9], rdi
0x140078ad6  mov     r14, rdi
0x140078ad9  mov     [r12], edi
0x140078add  call    cs:__imp_NdisAcquireRWLockRead
0x140078ae4  nop     dword ptr [rax+rax+00h]
0x140078ae9  xor     r9d, r9d; unsigned __int8 *
0x140078aec  lea     r8, [rsp+78h+var_44]; unsigned int *
0x140078af1  mov     rcx, rbp; struct _WFD_ROLE *
0x140078af4  lea     edx, [r9+1]; enum MANAGEMENT_FRAME_TYPE
0x140078af8  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140078afd  mov     edi, eax
0x140078aff  test    eax, eax
0x140078b01  jz      short loc_140078B26
0x140078b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b0a  cmp     rcx, r15
0x140078b0d  jz      short loc_140078B79
0x140078b0f  mov     edx, 0B8h
0x140078b14  mov     rcx, [rcx+18h]
0x140078b18  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078b1f  call    WPP_SF_
0x140078b24  jmp     short loc_140078B79
0x140078b26  mov     r15d, [rsp+78h+var_44]
0x140078b2b  test    r15d, r15d
0x140078b2e  jz      short loc_140078B72
0x140078b30  lea     r13d, [r15+rbx]
0x140078b34  cmp     r13d, ebx
0x140078b37  jnb     loc_140078BBE
0x140078b3d  mov     edi, 0C0000095h
0x140078b42  mov     rcx, cs:WPP_GLOBAL_Control
0x140078b49  lea     rax, WPP_GLOBAL_Control
0x140078b50  cmp     rcx, rax
0x140078b53  jz      short loc_140078B72
0x140078b55  mov     edx, 0B9h
0x140078b5a  mov     r9d, ebx
0x140078b5d  mov     rcx, [rcx+18h]
0x140078b61  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078b68  mov     [rsp+78h+var_58], r15d
0x140078b6d  call    WPP_SF_Dd
0x140078b72  lea     r15, WPP_GLOBAL_Control
0x140078b79  mov     rcx, [rbp+20h]; Lock
0x140078b7d  lea     rdx, [rsp+78h+LockState]; LockState
0x140078b82  call    cs:__imp_NdisReleaseRWLock
0x140078b89  nop     dword ptr [rax+rax+00h]
0x140078b8e  test    r14, r14
0x140078b91  jz      loc_140079087
0x140078b97  lea     rcx, [r14-10h]; P
0x140078b9b  mov     rax, [rcx]
0x140078b9e  test    rax, rax
0x140078ba1  jz      loc_140079050
0x140078ba7  mov     rdx, rcx; Entry
0x140078baa  mov     rcx, rax; Lookaside
0x140078bad  call    cs:__imp_ExFreeToNPagedLookasideList
0x140078bb4  nop     dword ptr [rax+rax+00h]
0x140078bb9  jmp     loc_140079087
0x140078bbe  lea     eax, [r13+10h]
0x140078bc2  cmp     eax, 10h
0x140078bc5  jb      loc_14007902A
0x140078bcb  mov     ecx, 40h ; '@'
0x140078bd0  mov     edi, 30327776h
0x140078bd5  cmp     eax, ecx
0x140078bd7  ja      short loc_140078BE2
0x140078bd9  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140078be0  jmp     short loc_140078C10
0x140078be2  cmp     eax, 100h
0x140078be7  ja      short loc_140078BF2
0x140078be9  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140078bf0  jmp     short loc_140078C10
0x140078bf2  cmp     eax, 400h
0x140078bf7  ja      short loc_140078C02
0x140078bf9  lea     rbx, Lookaside
0x140078c00  jmp     short loc_140078C10
0x140078c02  cmp     eax, 800h
0x140078c07  ja      short loc_140078C21
0x140078c09  lea     rbx, stru_1400B0180
0x140078c10  mov     rcx, rbx; Lookaside
0x140078c13  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140078c1a  nop     dword ptr [rax+rax+00h]
0x140078c1f  jmp     short loc_140078C34
0x140078c21  xor     ebx, ebx
0x140078c23  mov     edx, eax
0x140078c25  mov     r8d, edi
0x140078c28  call    cs:__imp_ExAllocatePool2
0x140078c2f  nop     dword ptr [rax+rax+00h]
0x140078c34  test    rax, rax
0x140078c37  jz      loc_14007902A
0x140078c3d  lea     r14, [rax+10h]
0x140078c41  mov     r8d, r13d; Size
0x140078c44  mov     rcx, r14; void *
0x140078c47  mov     [rax], rbx
0x140078c4a  xor     edx, edx; Val
0x140078c4c  mov     [rax+8], edi
0x140078c4f  call    memset
0x140078c54  movups  xmm0, xmmword ptr [rsi]
0x140078c57  mov     r8d, 0FFFFFFFFh
0x140078c5d  movups  xmmword ptr [r14], xmm0
0x140078c61  movups  xmm1, xmmword ptr [rsi+10h]
0x140078c65  movups  xmmword ptr [r14+10h], xmm1
0x140078c6a  movups  xmm0, xmmword ptr [rsi+20h]
0x140078c6e  movups  xmmword ptr [r14+20h], xmm0
0x140078c73  movups  xmm1, xmmword ptr [rsi+30h]
0x140078c77  movups  xmmword ptr [r14+30h], xmm1
0x140078c7c  movups  xmm0, xmmword ptr [rsi+40h]
0x140078c80  movups  xmmword ptr [r14+40h], xmm0
0x140078c85  movups  xmm1, xmmword ptr [rsi+50h]
0x140078c89  movups  xmmword ptr [r14+50h], xmm1
0x140078c8e  mov     eax, [rsi+60h]
0x140078c91  mov     [r14+60h], eax
0x140078c95  mov     dword ptr [r14+18h], 64h ; 'd'
0x140078c9d  mov     ecx, [rsi+1Ch]
0x140078ca0  add     ecx, r15d
0x140078ca3  mov     [r14+1Ch], ecx
0x140078ca7  add     ecx, 64h ; 'd'
0x140078caa  cmp     dword ptr [rsi+14h], 0
0x140078cae  jbe     loc_140078D35
0x140078cb4  mov     [r14+10h], ecx
0x140078cb8  mov     r9d, [rsi+14h]
0x140078cbc  imul    r15, r9, 2Ch ; ','
0x140078cc0  cmp     r15, r8
0x140078cc3  ja      short loc_140078CF7
0x140078cc5  lea     r9d, [r15+rcx]
0x140078cc9  cmp     r9d, ecx
0x140078ccc  jnb     short loc_140078D3B
0x140078cce  mov     edi, 0C0000095h
0x140078cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140078cda  lea     rax, WPP_GLOBAL_Control
0x140078ce1  cmp     rcx, rax
0x140078ce4  jz      loc_140078B72
0x140078cea  mov     edx, 0BCh
0x140078cef  mov     r9d, r8d
0x140078cf2  jmp     loc_140078B5D
0x140078cf7  mov     edi, 0C0000095h
0x140078cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140078d03  lea     r15, WPP_GLOBAL_Control
0x140078d0a  cmp     rcx, r15
0x140078d0d  jz      loc_140078B79
0x140078d13  mov     edx, 0BBh
0x140078d18  mov     [rsp+78h+var_58], 2Ch ; ','
0x140078d20  mov     rcx, [rcx+18h]
0x140078d24  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078d2b  call    WPP_SF_Dd
0x140078d30  jmp     loc_140078B79
0x140078d35  xor     r15d, r15d
0x140078d38  mov     r9d, ecx
0x140078d3b  cmp     dword ptr [rsi+30h], 0
0x140078d3f  jbe     short loc_140078D58
0x140078d41  mov     [r14+2Ch], r9d
0x140078d45  mov     eax, [rsi+30h]
0x140078d48  lea     ecx, [rax+r9]
0x140078d4c  cmp     ecx, r9d
0x140078d4f  jb      loc_140078E00
0x140078d55  mov     r9d, ecx
0x140078d58  cmp     dword ptr [rsi+3Ch], 0
0x140078d5c  jbe     short loc_140078D75
0x140078d5e  mov     [r14+38h], r9d
0x140078d62  mov     eax, [rsi+3Ch]
0x140078d65  lea     ecx, [rax+r9]
0x140078d69  cmp     ecx, r9d
0x140078d6c  jb      loc_140078E2D
0x140078d72  mov     r9d, ecx
0x140078d75  cmp     dword ptr [rsi+48h], 0
0x140078d79  jbe     short loc_140078D92
0x140078d7b  mov     [r14+44h], r9d
0x140078d7f  mov     eax, [rsi+48h]
0x140078d82  lea     ecx, [rax+r9]
0x140078d86  cmp     ecx, r9d
0x140078d89  jb      loc_140078E50
0x140078d8f  mov     r9d, ecx
0x140078d92  cmp     dword ptr [rsi+54h], 0
0x140078d96  jbe     short loc_140078DAF
0x140078d98  mov     [r14+50h], r9d
0x140078d9c  mov     eax, [rsi+54h]
0x140078d9f  lea     ecx, [rax+r9]
0x140078da3  cmp     ecx, r9d
0x140078da6  jb      loc_140078E73
0x140078dac  mov     r9d, ecx
0x140078daf  cmp     dword ptr [rsi+5Ch], 0
0x140078db3  jbe     short loc_140078DCC
0x140078db5  mov     [r14+58h], r9d
0x140078db9  mov     eax, [rsi+5Ch]
0x140078dbc  lea     ecx, [rax+r9]
0x140078dc0  cmp     ecx, r9d
0x140078dc3  jb      loc_140078E96
0x140078dc9  mov     r9d, ecx
0x140078dcc  cmp     r9d, r13d
0x140078dcf  jbe     loc_140078EBC
0x140078dd5  mov     edi, 0C000000Dh
0x140078dda  mov     rcx, cs:WPP_GLOBAL_Control
0x140078de1  lea     r15, WPP_GLOBAL_Control
0x140078de8  cmp     rcx, r15
0x140078deb  jz      loc_140078B79
0x140078df1  mov     edx, 0C2h
0x140078df6  mov     [rsp+78h+var_58], r13d
0x140078dfb  jmp     loc_140078D20
0x140078e00  mov     edi, 0C0000095h
0x140078e05  mov     rcx, cs:WPP_GLOBAL_Control
0x140078e0c  lea     r15, WPP_GLOBAL_Control
0x140078e13  cmp     rcx, r15
0x140078e16  jz      loc_140078B79
0x140078e1c  mov     edx, 0BDh
0x140078e21  mov     [rsp+78h+var_58], eax
0x140078e25  mov     r9d, r8d
0x140078e28  jmp     loc_140078D20
0x140078e2d  mov     edi, 0C0000095h
0x140078e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140078e39  lea     r15, WPP_GLOBAL_Control
0x140078e40  cmp     rcx, r15
0x140078e43  jz      loc_140078B79
0x140078e49  mov     edx, 0BEh
0x140078e4e  jmp     short loc_140078E21
0x140078e50  mov     edi, 0C0000095h
0x140078e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140078e5c  lea     r15, WPP_GLOBAL_Control
0x140078e63  cmp     rcx, r15
0x140078e66  jz      loc_140078B79
0x140078e6c  mov     edx, 0BFh
0x140078e71  jmp     short loc_140078E21
0x140078e73  mov     edi, 0C0000095h
0x140078e78  mov     rcx, cs:WPP_GLOBAL_Control
0x140078e7f  lea     r15, WPP_GLOBAL_Control
0x140078e86  cmp     rcx, r15
0x140078e89  jz      loc_140078B79
0x140078e8f  mov     edx, 0C0h
0x140078e94  jmp     short loc_140078E21
0x140078e96  mov     edi, 0C0000095h
0x140078e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ea2  lea     r15, WPP_GLOBAL_Control
0x140078ea9  cmp     rcx, r15
0x140078eac  jz      loc_140078B79
0x140078eb2  mov     edx, 0C1h
0x140078eb7  jmp     loc_140078E21
0x140078ebc  mov     edx, [rsi+18h]
0x140078ebf  lea     rbx, [r14+64h]
0x140078ec3  mov     r8d, [rsi+1Ch]; Size
0x140078ec7  add     rdx, rsi; Src
0x140078eca  mov     rcx, rbx; void *
0x140078ecd  call    memmove
0x140078ed2  mov     eax, [rsi+1Ch]
0x140078ed5  lea     r8, [rsp+78h+var_44]; unsigned int *
0x140078eda  add     rbx, rax
0x140078edd  mov     edx, 1; enum MANAGEMENT_FRAME_TYPE
0x140078ee2  mov     r9, rbx; unsigned __int8 *
0x140078ee5  mov     rcx, rbp; struct _WFD_ROLE *
0x140078ee8  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140078eed  mov     edi, eax
0x140078eef  test    eax, eax
0x140078ef1  jz      short loc_140078F14
0x140078ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140078efa  lea     r15, WPP_GLOBAL_Control
0x140078f01  cmp     rcx, r15
0x140078f04  jz      loc_140078B79
  ... truncated ...
```
