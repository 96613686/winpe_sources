# WFDRoleCacheIEsAndCreateOidStructure(ulong,_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *,_WFD_ROLE *,_DOT11_WFD_ADDITIONAL_IE * *,ulong *)

- ea: `0x140079498`
- end: `0x140079a15`
- name: `?WFDRoleCacheIEsAndCreateOidStructure@@YAHKPEAU_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST@@PEAU_WFD_ROLE@@PEAPEAU_DOT11_WFD_ADDITIONAL_IE@@PEAK@Z`
- size: `1405`
- prototype: `__int64 __fastcall(size_t Size, struct _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *Src, struct _WFD_ROLE *, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14007ab50`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140079498`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079621`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079749`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079621`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079749`
- `ntoskrnl!ExAllocatePool2` at `0x14007963f`
- `ntoskrnl!ExAllocatePool2` at `0x140079764`
- `ntoskrnl!ExAllocatePool2` at `0x14007963f`
- `ntoskrnl!ExAllocatePool2` at `0x140079764`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400798b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007990c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079944`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400798b3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007990c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079944`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007991d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079958`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007996c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007991d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079958`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007996c`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079830`
- `NDIS!NdisAcquireRWLockWrite` at `0x140079830`
- `NDIS!NdisReleaseRWLock` at `0x140079859`
- `NDIS!NdisReleaseRWLock` at `0x140079859`

## pseudocode

```c
__int64 __fastcall WFDRoleCacheIEsAndCreateOidStructure(
        size_t Size,
        struct _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *Src,
        struct _WFD_ROLE *a3,
        unsigned __int64 a4,
        unsigned int *a5)
{
  size_t v5; // r15
  unsigned int *v8; // rax
  unsigned int v9; // r8d
  unsigned int v10; // ecx
  int v11; // edx
  unsigned int uIEsLength; // eax
  unsigned int uIEsOffset; // r10d
  unsigned int v14; // ebx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v21; // r14
  _DWORD *v22; // r12
  char *v23; // rbx
  unsigned int v24; // r12d
  __int64 v25; // r9
  unsigned int v26; // eax
  char *v27; // rax
  _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *v28; // rdi
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // ecx
  __int64 v32; // r8
  unsigned int v33; // eax
  unsigned int v34; // edx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  unsigned int Sizea; // [rsp+20h] [rbp-58h]
  unsigned int Sizeb; // [rsp+20h] [rbp-58h]
  _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *pFrameIEList; // [rsp+28h] [rbp-50h]
  struct _DOT11_WFD_ADDITIONAL_IE *v40; // [rsp+30h] [rbp-48h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF
  struct _DOT11_WFD_ADDITIONAL_IE **v42; // [rsp+98h] [rbp+20h]

  v42 = (struct _DOT11_WFD_ADDITIONAL_IE **)a4;
  v5 = (unsigned int)Size;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = (unsigned __int64)v42;
  }
  if ( Src )
  {
    if ( (unsigned int)v5 >= 0x64 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          v8 = a5;
          if ( a5 )
          {
            *(_QWORD *)a4 = 0;
            v9 = v5 - 100;
            *v8 = 0;
            v10 = 0;
            v11 = 0;
            while ( v10 < 0xC )
            {
              uIEsLength = Src->Frames[v10].uIEsLength;
              if ( uIEsLength > v9
                || (uIEsOffset = Src->Frames[v10].uIEsOffset, uIEsOffset > (unsigned int)v5)
                || (a4 = uIEsOffset + uIEsLength, (unsigned int)a4 < uIEsLength)
                || (unsigned int)a4 > (unsigned int)v5 )
              {
                v14 = -1073676267;
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  return v14;
                v16 = 38;
                goto LABEL_74;
              }
              if ( uIEsLength )
                ++v11;
              v9 -= uIEsLength;
              ++v10;
            }
            if ( v11 != Src->uNumberOfFrames )
            {
              v14 = -1073676267;
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                return v14;
              v16 = 39;
LABEL_74:
              WPP_SF_(v15->AttachedDevice, v16, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
              goto LABEL_75;
            }
            Sizea = Src->Frames[2].uIEsLength + Src->Frames[1].uIEsLength + Src->Frames[0].uIEsLength + 28;
            v17 = Sizea + 16;
            if ( Sizea + 16 < 0x10 )
              goto LABEL_70;
            p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
            if ( v17 > 0x40 )
            {
              if ( v17 > 0x100 )
              {
                if ( v17 > 0x400 )
                {
                  if ( v17 > 0x800 )
                  {
                    p_WaitListHead = 0;
                    Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 808613750, a4);
LABEL_33:
                    v21 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
                    if ( Pool2 )
                    {
                      pFrameIEList = 0;
                      v22 = Pool2 + 4;
                      *(_QWORD *)Pool2 = p_WaitListHead;
                      Pool2[2] = 808613750;
                      v40 = (struct _DOT11_WFD_ADDITIONAL_IE *)(Pool2 + 4);
                      memset(Pool2 + 4, 0, Sizea);
                      *v22 = 1835392;
                      memmove(v22 + 7, (char *)Src + Src->Frames[0].uIEsOffset, Src->Frames[0].uIEsLength);
                      v22[1] = 28;
                      v22[2] = Src->Frames[0].uIEsLength;
                      v23 = (char *)v22 + Src->Frames[0].uIEsLength + 28;
                      memmove(v23, (char *)Src + Src->Frames[1].uIEsOffset, Src->Frames[1].uIEsLength);
                      v22[5] = (_DWORD)v23 - (_DWORD)v22;
                      v22[6] = Src->Frames[1].uIEsLength;
                      v24 = (_DWORD)v23 + Src->Frames[1].uIEsLength;
                      memmove(
                        &v23[Src->Frames[1].uIEsLength],
                        (char *)Src + Src->Frames[2].uIEsOffset,
                        Src->Frames[2].uIEsLength);
                      *((_DWORD *)v21 + 7) = v24 - ((_DWORD)v21 + 16);
                      *((_DWORD *)v21 + 8) = Src->Frames[2].uIEsLength;
                      v26 = v5 + 16;
                      if ( (unsigned int)(v5 + 16) < 0x10 )
                        goto LABEL_45;
                      Sizeb = Src->Frames[2].uIEsLength;
                      if ( v26 > 0x40 )
                      {
                        if ( v26 > 0x100 )
                        {
                          if ( v26 > 0x400 )
                          {
                            if ( v26 > 0x800 )
                            {
                              p_DeviceQueue = 0;
                              v27 = (char *)ExAllocatePool2(64, v26, 808613750, v25);
LABEL_44:
                              if ( v27 )
                              {
                                *(_QWORD *)v27 = p_DeviceQueue;
                                v28 = (_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *)(v27 + 16);
                                *((_DWORD *)v27 + 2) = 808613750;
                                memset(v27 + 16, 0, v5);
                                memmove(v28, Src, v5);
                                v31 = v28->Frames[1].uIEsLength;
                                if ( v31 )
                                {
                                  if ( v31 < 2 )
                                  {
                                    v14 = -1073676267;
                                    v29 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                    {
                                      v30 = 42;
                                      goto LABEL_60;
                                    }
LABEL_61:
                                    if ( v21 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
                                    {
                                      if ( *v21 )
                                        ExFreeToNPagedLookasideList(*v21, v21);
                                      else
                                        ExFreePoolWithTag(v21, *((_DWORD *)v21 + 2));
                                    }
                                    if ( v28 )
                                    {
                                      if ( v28[-1].Frames[10] )
                                        ExFreeToNPagedLookasideList(
                                          *(PNPAGED_LOOKASIDE_LIST *)&v28[-1].Frames[10],
                                          &v28[-1].Frames[10]);
                                      else
                                        ExFreePoolWithTag(&v28[-1].Frames[10], v28[-1].Frames[11].uIEsOffset);
                                    }
                                    goto LABEL_55;
                                  }
                                  v32 = v28->Frames[1].uIEsOffset;
                                  v33 = *((unsigned __int8 *)&v28->uNumberOfFrames + v32 + 1);
                                  v34 = v33 + 2;
                                  if ( v33 + 2 < v33 || v34 > v31 )
                                  {
                                    v14 = -1073676267;
                                    v29 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                    {
                                      v30 = 43;
                                      goto LABEL_60;
                                    }
                                    goto LABEL_61;
                                  }
                                  v28->Frames[1].uIEsLength = v31 - v34;
                                  v28->Frames[1].uIEsOffset = v32 + v34;
                                }
                                v14 = 0;
                                NdisAcquireRWLockWrite(a3->pRWLock, &LockState, 0);
                                pRWLock = a3->pRWLock;
                                pFrameIEList = a3->pFrameIEList;
                                a3->pFrameIEList = v28;
                                a3->cbFrameIEList = v5;
                                NdisReleaseRWLock(pRWLock, &LockState);
                                *v42 = v40;
                                *a5 = Sizeb + v24 - (_DWORD)v40;
LABEL_55:
                                if ( pFrameIEList )
                                {
                                  if ( pFrameIEList[-1].Frames[10] )
                                    ExFreeToNPagedLookasideList(
                                      *(PNPAGED_LOOKASIDE_LIST *)&pFrameIEList[-1].Frames[10],
                                      &pFrameIEList[-1].Frames[10]);
                                  else
                                    ExFreePoolWithTag(
                                      &pFrameIEList[-1].Frames[10],
                                      pFrameIEList[-1].Frames[11].uIEsOffset);
                                }
                                goto LABEL_75;
                              }
LABEL_45:
                              v14 = -1073741670;
                              v28 = 0;
                              v29 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
                                v30 = 41;
LABEL_60:
                                WPP_SF_(v29->AttachedDevice, v30, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                                goto LABEL_61;
                              }
                              goto LABEL_61;
                            }
                            p_DeviceQueue = &stru_1400B0180;
                          }
                          else
                          {
                            p_DeviceQueue = &Lookaside;
                          }
                        }
                        else
                        {
                          p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
                        }
                      }
                      v27 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
                      goto LABEL_44;
                    }
LABEL_70:
                    v14 = -1073741670;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      return v14;
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_75:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        44,
                        WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                        v14);
                    return v14;
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
  v14 = -1073741811;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v16 = 37;
    goto LABEL_74;
  }
  return v14;
}

```

## disassembly

```asm
0x140079498  mov     r11, rsp
0x14007949b  mov     [r11+8], rbx
0x14007949f  mov     [r11+20h], r9
0x1400794a3  push    rbp
0x1400794a4  push    rsi
0x1400794a5  push    rdi
0x1400794a6  push    r12
0x1400794a8  push    r13
0x1400794aa  push    r14
0x1400794ac  push    r15
0x1400794ae  sub     rsp, 40h
0x1400794b2  xor     r12d, r12d
0x1400794b5  mov     r15d, ecx
0x1400794b8  xor     eax, eax
0x1400794ba  mov     [r11+10h], r12b
0x1400794be  mov     [r11+11h], ax
0x1400794c3  mov     r13, r8
0x1400794c6  mov     rsi, rdx
0x1400794c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794d0  lea     r11, WPP_GLOBAL_Control
0x1400794d7  cmp     rcx, r11
0x1400794da  jz      short loc_1400794FE
0x1400794dc  mov     rcx, [rcx+18h]
0x1400794e0  lea     edx, [rax+24h]
0x1400794e3  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400794ea  call    WPP_SF_
0x1400794ef  mov     r9, [rsp+78h+arg_18]
0x1400794f7  lea     r11, WPP_GLOBAL_Control
0x1400794fe  test    rsi, rsi
0x140079501  jz      loc_1400799A9
0x140079507  cmp     r15d, 64h ; 'd'
0x14007950b  jb      loc_1400799A9
0x140079511  test    r13, r13
0x140079514  jz      loc_1400799A9
0x14007951a  test    r9, r9
0x14007951d  jz      loc_1400799A9
0x140079523  mov     rax, [rsp+78h+arg_20]
0x14007952b  test    rax, rax
0x14007952e  jz      loc_1400799A9
0x140079534  mov     [r9], r12
0x140079537  lea     r8d, [r15-64h]
0x14007953b  mov     [rax], r12d
0x14007953e  mov     ecx, r12d
0x140079541  mov     edx, r12d
0x140079544  cmp     ecx, 0Ch
0x140079547  jnb     short loc_14007959A
0x140079549  mov     r9d, ecx
0x14007954c  mov     eax, [rsi+r9*8+8]
0x140079551  cmp     eax, r8d
0x140079554  ja      short loc_14007957B
0x140079556  mov     r10d, [rsi+r9*8+4]
0x14007955b  cmp     r10d, r15d
0x14007955e  ja      short loc_14007957B
0x140079560  lea     r9d, [r10+rax]
0x140079564  cmp     r9d, eax
0x140079567  jb      short loc_14007957B
0x140079569  cmp     r9d, r15d
0x14007956c  ja      short loc_14007957B
0x14007956e  test    eax, eax
0x140079570  jz      short loc_140079574
0x140079572  inc     edx
0x140079574  sub     r8d, eax
0x140079577  inc     ecx
0x140079579  jmp     short loc_140079544
0x14007957b  mov     ebx, 0C0010015h
0x140079580  mov     rcx, cs:WPP_GLOBAL_Control
0x140079587  cmp     rcx, r11
0x14007958a  jz      loc_1400799FA
0x140079590  mov     edx, 26h ; '&'
0x140079595  jmp     loc_1400799BF
0x14007959a  cmp     edx, [rsi]
0x14007959c  jz      short loc_1400795BD
0x14007959e  mov     ebx, 0C0010015h
0x1400795a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400795aa  cmp     rcx, r11
0x1400795ad  jz      loc_1400799FA
0x1400795b3  mov     edx, 27h ; '''
0x1400795b8  jmp     loc_1400799BF
0x1400795bd  mov     ecx, [rsi+10h]
0x1400795c0  mov     ebp, 10h
0x1400795c5  add     ecx, [rsi+18h]
0x1400795c8  mov     eax, [rsi+8]
0x1400795cb  add     eax, 1Ch
0x1400795ce  add     eax, ecx
0x1400795d0  mov     dword ptr [rsp+78h+Size], eax
0x1400795d4  add     eax, 10h
0x1400795d7  cmp     eax, ebp
0x1400795d9  jb      loc_14007997A
0x1400795df  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400795e6  cmp     eax, 40h ; '@'
0x1400795e9  ja      short loc_1400795F0
0x1400795eb  mov     rbx, rdi
0x1400795ee  jmp     short loc_14007961E
0x1400795f0  cmp     eax, 100h
0x1400795f5  ja      short loc_140079600
0x1400795f7  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400795fe  jmp     short loc_14007961E
0x140079600  cmp     eax, 400h
0x140079605  ja      short loc_140079610
0x140079607  lea     rbx, Lookaside
0x14007960e  jmp     short loc_14007961E
0x140079610  cmp     eax, 800h
0x140079615  ja      short loc_14007962F
0x140079617  lea     rbx, stru_1400B0180
0x14007961e  mov     rcx, rbx; Lookaside
0x140079621  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079628  nop     dword ptr [rax+rax+00h]
0x14007962d  jmp     short loc_14007964B
0x14007962f  mov     edx, eax
0x140079631  mov     ecx, 40h ; '@'
0x140079636  mov     r8d, 30327776h
0x14007963c  mov     rbx, r12
0x14007963f  call    cs:__imp_ExAllocatePool2
0x140079646  nop     dword ptr [rax+rax+00h]
0x14007964b  mov     r14, rax
0x14007964e  test    rax, rax
0x140079651  jz      loc_14007997A
0x140079657  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x14007965c  xor     edx, edx; Val
0x14007965e  mov     [rsp+78h+var_50], r12
0x140079663  lea     r12, [rax+10h]
0x140079667  mov     rcx, r12; void *
0x14007966a  mov     [rax], rbx
0x14007966d  mov     dword ptr [rax+8], 30327776h
0x140079674  mov     [rsp+78h+var_48], r12
0x140079679  call    memset
0x14007967e  mov     dword ptr [r12], 1C0180h
0x140079686  lea     rbx, [r12+1Ch]
0x14007968b  mov     edx, [rsi+4]
0x14007968e  mov     rcx, rbx; void *
0x140079691  mov     r8d, [rsi+8]; Size
0x140079695  add     rdx, rsi; Src
0x140079698  call    memmove
0x14007969d  mov     eax, ebx
0x14007969f  sub     eax, r12d
0x1400796a2  mov     [r12+4], eax
0x1400796a7  mov     eax, [rsi+8]
0x1400796aa  mov     [r12+8], eax
0x1400796af  mov     eax, [rsi+8]
0x1400796b2  mov     edx, [rsi+0Ch]
0x1400796b5  add     rbx, rax
0x1400796b8  mov     r8d, [rsi+10h]; Size
0x1400796bc  mov     rcx, rbx; void *
0x1400796bf  add     rdx, rsi; Src
0x1400796c2  call    memmove
0x1400796c7  mov     eax, ebx
0x1400796c9  sub     eax, r12d
0x1400796cc  mov     [r12+14h], eax
0x1400796d1  mov     eax, [rsi+10h]
0x1400796d4  mov     [r12+18h], eax
0x1400796d9  mov     r12d, [rsi+10h]
0x1400796dd  mov     edx, [rsi+14h]
0x1400796e0  add     r12, rbx
0x1400796e3  mov     r8d, [rsi+18h]; Size
0x1400796e7  mov     rcx, r12; void *
0x1400796ea  add     rdx, rsi; Src
0x1400796ed  call    memmove
0x1400796f2  lea     rcx, [r14+10h]
0x1400796f6  mov     eax, r12d
0x1400796f9  sub     eax, ecx
0x1400796fb  mov     [rcx+0Ch], eax
0x1400796fe  mov     eax, [rsi+18h]
0x140079701  mov     [rcx+10h], eax
0x140079704  lea     eax, [r15+10h]
0x140079708  cmp     eax, ebp
0x14007970a  jb      short loc_140079775
0x14007970c  mov     ecx, [rsi+18h]
0x14007970f  mov     dword ptr [rsp+78h+Size], ecx
0x140079713  cmp     eax, 40h ; '@'
0x140079716  jbe     short loc_140079746
0x140079718  cmp     eax, 100h
0x14007971d  ja      short loc_140079728
0x14007971f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140079726  jmp     short loc_140079746
0x140079728  cmp     eax, 400h
0x14007972d  ja      short loc_140079738
0x14007972f  lea     rdi, Lookaside
0x140079736  jmp     short loc_140079746
0x140079738  cmp     eax, 800h
0x14007973d  ja      short loc_140079757
0x14007973f  lea     rdi, stru_1400B0180
0x140079746  mov     rcx, rdi; Lookaside
0x140079749  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079750  nop     dword ptr [rax+rax+00h]
0x140079755  jmp     short loc_140079770
0x140079757  xor     edi, edi
0x140079759  mov     edx, eax
0x14007975b  mov     r8d, 30327776h
0x140079761  lea     ecx, [rdi+40h]
0x140079764  call    cs:__imp_ExAllocatePool2
0x14007976b  nop     dword ptr [rax+rax+00h]
0x140079770  test    rax, rax
0x140079773  jnz     short loc_14007979B
0x140079775  mov     ebx, 0C000009Ah
0x14007977a  xor     edi, edi
0x14007977c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079783  lea     rsi, WPP_GLOBAL_Control
0x14007978a  cmp     rcx, rsi
0x14007978d  jz      loc_1400798F1
0x140079793  lea     edx, [rdi+29h]
0x140079796  jmp     loc_1400798E1
0x14007979b  mov     [rax], rdi
0x14007979e  mov     r8, r15; Size
0x1400797a1  lea     rdi, [rax+10h]
0x1400797a5  mov     dword ptr [rax+8], 30327776h
0x1400797ac  mov     rcx, rdi; void *
0x1400797af  xor     edx, edx; Val
0x1400797b1  call    memset
0x1400797b6  mov     r8, r15; Size
0x1400797b9  mov     rdx, rsi; Src
0x1400797bc  mov     rcx, rdi; void *
0x1400797bf  call    memmove
0x1400797c4  mov     ecx, [rdi+10h]
0x1400797c7  test    ecx, ecx
0x1400797c9  jz      short loc_14007981F
0x1400797cb  cmp     ecx, 2
0x1400797ce  jnb     short loc_1400797F6
0x1400797d0  mov     ebx, 0C0010015h
0x1400797d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400797dc  lea     rsi, WPP_GLOBAL_Control
0x1400797e3  cmp     rcx, rsi
0x1400797e6  jz      loc_1400798F1
0x1400797ec  mov     edx, 2Ah ; '*'
0x1400797f1  jmp     loc_1400798E1
0x1400797f6  mov     r8d, [rdi+0Ch]
0x1400797fa  movzx   eax, byte ptr [r8+rdi+1]
0x140079800  lea     edx, [rax+2]
0x140079803  cmp     edx, eax
0x140079805  jb      loc_1400798C4
0x14007980b  cmp     edx, ecx
0x14007980d  ja      loc_1400798C4
0x140079813  sub     ecx, edx
0x140079815  lea     eax, [r8+rdx]
0x140079819  mov     [rdi+10h], ecx
0x14007981c  mov     [rdi+0Ch], eax
0x14007981f  mov     rcx, [r13+20h]; Lock
0x140079823  lea     rdx, [rsp+78h+LockState]; LockState
0x14007982b  xor     r8d, r8d; Flags
0x14007982e  xor     ebx, ebx
0x140079830  call    cs:__imp_NdisAcquireRWLockWrite
0x140079837  nop     dword ptr [rax+rax+00h]
0x14007983c  mov     rax, [r13+30h]
0x140079840  lea     rdx, [rsp+78h+LockState]; LockState
0x140079848  mov     rcx, [r13+20h]; Lock
0x14007984c  mov     [rsp+78h+var_50], rax
0x140079851  mov     [r13+30h], rdi
0x140079855  mov     [r13+28h], r15d
0x140079859  call    cs:__imp_NdisReleaseRWLock
0x140079860  nop     dword ptr [rax+rax+00h]
0x140079865  mov     rax, [rsp+78h+var_48]
0x14007986a  lea     rsi, WPP_GLOBAL_Control
0x140079871  mov     rcx, [rsp+78h+arg_18]
0x140079879  sub     r12d, eax
0x14007987c  add     r12d, dword ptr [rsp+78h+Size]
0x140079881  mov     [rcx], rax
0x140079884  mov     rax, [rsp+78h+arg_20]
0x14007988c  mov     [rax], r12d
0x14007988f  mov     rax, [rsp+78h+var_50]
0x140079894  test    rax, rax
0x140079897  jz      loc_1400799D6
0x14007989d  lea     rcx, [rax-10h]; P
0x1400798a1  mov     rax, [rcx]
0x1400798a4  test    rax, rax
0x1400798a7  jz      loc_140079969
0x1400798ad  mov     rdx, rcx; Entry
0x1400798b0  mov     rcx, rax; Lookaside
0x1400798b3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400798ba  nop     dword ptr [rax+rax+00h]
0x1400798bf  jmp     loc_1400799D6
0x1400798c4  mov     ebx, 0C0010015h
0x1400798c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400798d0  lea     rsi, WPP_GLOBAL_Control
0x1400798d7  cmp     rcx, rsi
0x1400798da  jz      short loc_1400798F1
0x1400798dc  mov     edx, 2Bh ; '+'
0x1400798e1  mov     rcx, [rcx+18h]
0x1400798e5  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400798ec  call    WPP_SF_
0x1400798f1  lea     rcx, [r14+rbp]
0x1400798f5  test    rcx, rcx
0x1400798f8  jz      short loc_140079929
0x1400798fa  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400798fe  mov     rax, [rcx]
0x140079901  test    rax, rax
0x140079904  jz      short loc_14007991A
0x140079906  mov     rdx, rcx; Entry
0x140079909  mov     rcx, rax; Lookaside
0x14007990c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079913  nop     dword ptr [rax+rax+00h]
0x140079918  jmp     short loc_140079929
0x14007991a  mov     edx, [rcx+8]; Tag
0x14007991d  call    cs:__imp_ExFreePoolWithTag
0x140079924  nop     dword ptr [rax+rax+00h]
0x140079929  test    rdi, rdi
0x14007992c  jz      loc_14007988F
0x140079932  lea     rcx, [rdi-10h]; P
0x140079936  mov     rax, [rcx]
0x140079939  test    rax, rax
0x14007993c  jz      short loc_140079955
0x14007993e  mov     rdx, rcx; Entry
  ... truncated ...
```
