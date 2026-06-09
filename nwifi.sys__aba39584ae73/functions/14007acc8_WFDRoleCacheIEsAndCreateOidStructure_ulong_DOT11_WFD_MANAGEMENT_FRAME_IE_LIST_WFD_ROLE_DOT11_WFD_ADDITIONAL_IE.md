# WFDRoleCacheIEsAndCreateOidStructure(ulong,_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *,_WFD_ROLE *,_DOT11_WFD_ADDITIONAL_IE * *,ulong *)

- ea: `0x14007acc8`
- end: `0x14007b245`
- name: `?WFDRoleCacheIEsAndCreateOidStructure@@YAHKPEAU_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST@@PEAU_WFD_ROLE@@PEAPEAU_DOT11_WFD_ADDITIONAL_IE@@PEAK@Z`
- size: `1405`
- prototype: `__int64 __fastcall(size_t Size, struct _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *Src, struct _WFD_ROLE *, struct _DOT11_WFD_ADDITIONAL_IE **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14007c380`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x14007acc8`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ae51`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007af79`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007ae51`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007af79`
- `ntoskrnl!ExAllocatePool2` at `0x14007ae6f`
- `ntoskrnl!ExAllocatePool2` at `0x14007af94`
- `ntoskrnl!ExAllocatePool2` at `0x14007ae6f`
- `ntoskrnl!ExAllocatePool2` at `0x14007af94`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b0e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b13c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b174`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b0e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b13c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b174`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b14d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b188`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b19c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b14d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b188`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b19c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b060`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b060`
- `NDIS!NdisReleaseRWLock` at `0x14007b089`
- `NDIS!NdisReleaseRWLock` at `0x14007b089`

## pseudocode

```c
__int64 __fastcall WFDRoleCacheIEsAndCreateOidStructure(
        size_t Size,
        struct _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *Src,
        struct _WFD_ROLE *a3,
        struct _DOT11_WFD_ADDITIONAL_IE **a4,
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
  unsigned int v25; // eax
  char *v26; // rax
  _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *v27; // rdi
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // ecx
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // edx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  unsigned int Sizea; // [rsp+20h] [rbp-58h]
  unsigned int Sizeb; // [rsp+20h] [rbp-58h]
  _DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *pFrameIEList; // [rsp+28h] [rbp-50h]
  struct _DOT11_WFD_ADDITIONAL_IE *v39; // [rsp+30h] [rbp-48h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF
  struct _DOT11_WFD_ADDITIONAL_IE **v41; // [rsp+98h] [rbp+20h]

  v41 = a4;
  v5 = (unsigned int)Size;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = v41;
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
            *a4 = 0;
            v9 = v5 - 100;
            *v8 = 0;
            v10 = 0;
            v11 = 0;
            while ( v10 < 0xC )
            {
              uIEsLength = Src->Frames[v10].uIEsLength;
              if ( uIEsLength > v9
                || (uIEsOffset = Src->Frames[v10].uIEsOffset, uIEsOffset > (unsigned int)v5)
                || uIEsOffset + uIEsLength < uIEsLength
                || uIEsOffset + uIEsLength > (unsigned int)v5 )
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
                    Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 808613750);
LABEL_33:
                    v21 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
                    if ( Pool2 )
                    {
                      pFrameIEList = 0;
                      v22 = Pool2 + 4;
                      *(_QWORD *)Pool2 = p_WaitListHead;
                      Pool2[2] = 808613750;
                      v39 = (struct _DOT11_WFD_ADDITIONAL_IE *)(Pool2 + 4);
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
                      v25 = v5 + 16;
                      if ( (unsigned int)(v5 + 16) < 0x10 )
                        goto LABEL_45;
                      Sizeb = Src->Frames[2].uIEsLength;
                      if ( v25 > 0x40 )
                      {
                        if ( v25 > 0x100 )
                        {
                          if ( v25 > 0x400 )
                          {
                            if ( v25 > 0x800 )
                            {
                              p_DeviceQueue = 0;
                              v26 = (char *)ExAllocatePool2(64, v25, 808613750);
LABEL_44:
                              if ( v26 )
                              {
                                *(_QWORD *)v26 = p_DeviceQueue;
                                v27 = (_DOT11_WFD_MANAGEMENT_FRAME_IE_LIST *)(v26 + 16);
                                *((_DWORD *)v26 + 2) = 808613750;
                                memset(v26 + 16, 0, v5);
                                memmove(v27, Src, v5);
                                v30 = v27->Frames[1].uIEsLength;
                                if ( v30 )
                                {
                                  if ( v30 < 2 )
                                  {
                                    v14 = -1073676267;
                                    v28 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                    {
                                      v29 = 42;
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
                                    if ( v27 )
                                    {
                                      if ( v27[-1].Frames[10] )
                                        ExFreeToNPagedLookasideList(
                                          *(PNPAGED_LOOKASIDE_LIST *)&v27[-1].Frames[10],
                                          &v27[-1].Frames[10]);
                                      else
                                        ExFreePoolWithTag(&v27[-1].Frames[10], v27[-1].Frames[11].uIEsOffset);
                                    }
                                    goto LABEL_55;
                                  }
                                  v31 = v27->Frames[1].uIEsOffset;
                                  v32 = *((unsigned __int8 *)&v27->uNumberOfFrames + v31 + 1);
                                  v33 = v32 + 2;
                                  if ( v32 + 2 < v32 || v33 > v30 )
                                  {
                                    v14 = -1073676267;
                                    v28 = WPP_GLOBAL_Control;
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                    {
                                      v29 = 43;
                                      goto LABEL_60;
                                    }
                                    goto LABEL_61;
                                  }
                                  v27->Frames[1].uIEsLength = v30 - v33;
                                  v27->Frames[1].uIEsOffset = v31 + v33;
                                }
                                v14 = 0;
                                NdisAcquireRWLockWrite(a3->pRWLock, &LockState, 0);
                                pRWLock = a3->pRWLock;
                                pFrameIEList = a3->pFrameIEList;
                                a3->pFrameIEList = v27;
                                a3->cbFrameIEList = v5;
                                NdisReleaseRWLock(pRWLock, &LockState);
                                *v41 = v39;
                                *a5 = Sizeb + v24 - (_DWORD)v39;
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
                              v27 = 0;
                              v28 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
                                v29 = 41;
LABEL_60:
                                WPP_SF_(v28->AttachedDevice, v29, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                                goto LABEL_61;
                              }
                              goto LABEL_61;
                            }
                            p_DeviceQueue = &stru_1400B31C0;
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
                      v26 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
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
0x14007acc8  mov     r11, rsp
0x14007accb  mov     [r11+8], rbx
0x14007accf  mov     [r11+20h], r9
0x14007acd3  push    rbp
0x14007acd4  push    rsi
0x14007acd5  push    rdi
0x14007acd6  push    r12
0x14007acd8  push    r13
0x14007acda  push    r14
0x14007acdc  push    r15
0x14007acde  sub     rsp, 40h
0x14007ace2  xor     r12d, r12d
0x14007ace5  mov     r15d, ecx
0x14007ace8  xor     eax, eax
0x14007acea  mov     [r11+10h], r12b
0x14007acee  mov     [r11+11h], ax
0x14007acf3  mov     r13, r8
0x14007acf6  mov     rsi, rdx
0x14007acf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad00  lea     r11, WPP_GLOBAL_Control
0x14007ad07  cmp     rcx, r11
0x14007ad0a  jz      short loc_14007AD2E
0x14007ad0c  mov     rcx, [rcx+18h]
0x14007ad10  lea     edx, [rax+24h]
0x14007ad13  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007ad1a  call    WPP_SF_
0x14007ad1f  mov     r9, [rsp+78h+arg_18]
0x14007ad27  lea     r11, WPP_GLOBAL_Control
0x14007ad2e  test    rsi, rsi
0x14007ad31  jz      loc_14007B1D9
0x14007ad37  cmp     r15d, 64h ; 'd'
0x14007ad3b  jb      loc_14007B1D9
0x14007ad41  test    r13, r13
0x14007ad44  jz      loc_14007B1D9
0x14007ad4a  test    r9, r9
0x14007ad4d  jz      loc_14007B1D9
0x14007ad53  mov     rax, [rsp+78h+arg_20]
0x14007ad5b  test    rax, rax
0x14007ad5e  jz      loc_14007B1D9
0x14007ad64  mov     [r9], r12
0x14007ad67  lea     r8d, [r15-64h]
0x14007ad6b  mov     [rax], r12d
0x14007ad6e  mov     ecx, r12d
0x14007ad71  mov     edx, r12d
0x14007ad74  cmp     ecx, 0Ch
0x14007ad77  jnb     short loc_14007ADCA
0x14007ad79  mov     r9d, ecx
0x14007ad7c  mov     eax, [rsi+r9*8+8]
0x14007ad81  cmp     eax, r8d
0x14007ad84  ja      short loc_14007ADAB
0x14007ad86  mov     r10d, [rsi+r9*8+4]
0x14007ad8b  cmp     r10d, r15d
0x14007ad8e  ja      short loc_14007ADAB
0x14007ad90  lea     r9d, [r10+rax]
0x14007ad94  cmp     r9d, eax
0x14007ad97  jb      short loc_14007ADAB
0x14007ad99  cmp     r9d, r15d
0x14007ad9c  ja      short loc_14007ADAB
0x14007ad9e  test    eax, eax
0x14007ada0  jz      short loc_14007ADA4
0x14007ada2  inc     edx
0x14007ada4  sub     r8d, eax
0x14007ada7  inc     ecx
0x14007ada9  jmp     short loc_14007AD74
0x14007adab  mov     ebx, 0C0010015h
0x14007adb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007adb7  cmp     rcx, r11
0x14007adba  jz      loc_14007B22A
0x14007adc0  mov     edx, 26h ; '&'
0x14007adc5  jmp     loc_14007B1EF
0x14007adca  cmp     edx, [rsi]
0x14007adcc  jz      short loc_14007ADED
0x14007adce  mov     ebx, 0C0010015h
0x14007add3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007adda  cmp     rcx, r11
0x14007addd  jz      loc_14007B22A
0x14007ade3  mov     edx, 27h ; '''
0x14007ade8  jmp     loc_14007B1EF
0x14007aded  mov     ecx, [rsi+10h]
0x14007adf0  mov     ebp, 10h
0x14007adf5  add     ecx, [rsi+18h]
0x14007adf8  mov     eax, [rsi+8]
0x14007adfb  add     eax, 1Ch
0x14007adfe  add     eax, ecx
0x14007ae00  mov     dword ptr [rsp+78h+Size], eax
0x14007ae04  add     eax, 10h
0x14007ae07  cmp     eax, ebp
0x14007ae09  jb      loc_14007B1AA
0x14007ae0f  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14007ae16  cmp     eax, 40h ; '@'
0x14007ae19  ja      short loc_14007AE20
0x14007ae1b  mov     rbx, rdi
0x14007ae1e  jmp     short loc_14007AE4E
0x14007ae20  cmp     eax, 100h
0x14007ae25  ja      short loc_14007AE30
0x14007ae27  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007ae2e  jmp     short loc_14007AE4E
0x14007ae30  cmp     eax, 400h
0x14007ae35  ja      short loc_14007AE40
0x14007ae37  lea     rbx, Lookaside
0x14007ae3e  jmp     short loc_14007AE4E
0x14007ae40  cmp     eax, 800h
0x14007ae45  ja      short loc_14007AE5F
0x14007ae47  lea     rbx, stru_1400B31C0
0x14007ae4e  mov     rcx, rbx; Lookaside
0x14007ae51  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007ae58  nop     dword ptr [rax+rax+00h]
0x14007ae5d  jmp     short loc_14007AE7B
0x14007ae5f  mov     edx, eax
0x14007ae61  mov     ecx, 40h ; '@'
0x14007ae66  mov     r8d, 30327776h
0x14007ae6c  mov     rbx, r12
0x14007ae6f  call    cs:__imp_ExAllocatePool2
0x14007ae76  nop     dword ptr [rax+rax+00h]
0x14007ae7b  mov     r14, rax
0x14007ae7e  test    rax, rax
0x14007ae81  jz      loc_14007B1AA
0x14007ae87  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x14007ae8c  xor     edx, edx; Val
0x14007ae8e  mov     [rsp+78h+var_50], r12
0x14007ae93  lea     r12, [rax+10h]
0x14007ae97  mov     rcx, r12; void *
0x14007ae9a  mov     [rax], rbx
0x14007ae9d  mov     dword ptr [rax+8], 30327776h
0x14007aea4  mov     [rsp+78h+var_48], r12
0x14007aea9  call    memset
0x14007aeae  mov     dword ptr [r12], 1C0180h
0x14007aeb6  lea     rbx, [r12+1Ch]
0x14007aebb  mov     edx, [rsi+4]
0x14007aebe  mov     rcx, rbx; void *
0x14007aec1  mov     r8d, [rsi+8]; Size
0x14007aec5  add     rdx, rsi; Src
0x14007aec8  call    memmove
0x14007aecd  mov     eax, ebx
0x14007aecf  sub     eax, r12d
0x14007aed2  mov     [r12+4], eax
0x14007aed7  mov     eax, [rsi+8]
0x14007aeda  mov     [r12+8], eax
0x14007aedf  mov     eax, [rsi+8]
0x14007aee2  mov     edx, [rsi+0Ch]
0x14007aee5  add     rbx, rax
0x14007aee8  mov     r8d, [rsi+10h]; Size
0x14007aeec  mov     rcx, rbx; void *
0x14007aeef  add     rdx, rsi; Src
0x14007aef2  call    memmove
0x14007aef7  mov     eax, ebx
0x14007aef9  sub     eax, r12d
0x14007aefc  mov     [r12+14h], eax
0x14007af01  mov     eax, [rsi+10h]
0x14007af04  mov     [r12+18h], eax
0x14007af09  mov     r12d, [rsi+10h]
0x14007af0d  mov     edx, [rsi+14h]
0x14007af10  add     r12, rbx
0x14007af13  mov     r8d, [rsi+18h]; Size
0x14007af17  mov     rcx, r12; void *
0x14007af1a  add     rdx, rsi; Src
0x14007af1d  call    memmove
0x14007af22  lea     rcx, [r14+10h]
0x14007af26  mov     eax, r12d
0x14007af29  sub     eax, ecx
0x14007af2b  mov     [rcx+0Ch], eax
0x14007af2e  mov     eax, [rsi+18h]
0x14007af31  mov     [rcx+10h], eax
0x14007af34  lea     eax, [r15+10h]
0x14007af38  cmp     eax, ebp
0x14007af3a  jb      short loc_14007AFA5
0x14007af3c  mov     ecx, [rsi+18h]
0x14007af3f  mov     dword ptr [rsp+78h+Size], ecx
0x14007af43  cmp     eax, 40h ; '@'
0x14007af46  jbe     short loc_14007AF76
0x14007af48  cmp     eax, 100h
0x14007af4d  ja      short loc_14007AF58
0x14007af4f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007af56  jmp     short loc_14007AF76
0x14007af58  cmp     eax, 400h
0x14007af5d  ja      short loc_14007AF68
0x14007af5f  lea     rdi, Lookaside
0x14007af66  jmp     short loc_14007AF76
0x14007af68  cmp     eax, 800h
0x14007af6d  ja      short loc_14007AF87
0x14007af6f  lea     rdi, stru_1400B31C0
0x14007af76  mov     rcx, rdi; Lookaside
0x14007af79  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007af80  nop     dword ptr [rax+rax+00h]
0x14007af85  jmp     short loc_14007AFA0
0x14007af87  xor     edi, edi
0x14007af89  mov     edx, eax
0x14007af8b  mov     r8d, 30327776h
0x14007af91  lea     ecx, [rdi+40h]
0x14007af94  call    cs:__imp_ExAllocatePool2
0x14007af9b  nop     dword ptr [rax+rax+00h]
0x14007afa0  test    rax, rax
0x14007afa3  jnz     short loc_14007AFCB
0x14007afa5  mov     ebx, 0C000009Ah
0x14007afaa  xor     edi, edi
0x14007afac  mov     rcx, cs:WPP_GLOBAL_Control
0x14007afb3  lea     rsi, WPP_GLOBAL_Control
0x14007afba  cmp     rcx, rsi
0x14007afbd  jz      loc_14007B121
0x14007afc3  lea     edx, [rdi+29h]
0x14007afc6  jmp     loc_14007B111
0x14007afcb  mov     [rax], rdi
0x14007afce  mov     r8, r15; Size
0x14007afd1  lea     rdi, [rax+10h]
0x14007afd5  mov     dword ptr [rax+8], 30327776h
0x14007afdc  mov     rcx, rdi; void *
0x14007afdf  xor     edx, edx; Val
0x14007afe1  call    memset
0x14007afe6  mov     r8, r15; Size
0x14007afe9  mov     rdx, rsi; Src
0x14007afec  mov     rcx, rdi; void *
0x14007afef  call    memmove
0x14007aff4  mov     ecx, [rdi+10h]
0x14007aff7  test    ecx, ecx
0x14007aff9  jz      short loc_14007B04F
0x14007affb  cmp     ecx, 2
0x14007affe  jnb     short loc_14007B026
0x14007b000  mov     ebx, 0C0010015h
0x14007b005  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b00c  lea     rsi, WPP_GLOBAL_Control
0x14007b013  cmp     rcx, rsi
0x14007b016  jz      loc_14007B121
0x14007b01c  mov     edx, 2Ah ; '*'
0x14007b021  jmp     loc_14007B111
0x14007b026  mov     r8d, [rdi+0Ch]
0x14007b02a  movzx   eax, byte ptr [r8+rdi+1]
0x14007b030  lea     edx, [rax+2]
0x14007b033  cmp     edx, eax
0x14007b035  jb      loc_14007B0F4
0x14007b03b  cmp     edx, ecx
0x14007b03d  ja      loc_14007B0F4
0x14007b043  sub     ecx, edx
0x14007b045  lea     eax, [r8+rdx]
0x14007b049  mov     [rdi+10h], ecx
0x14007b04c  mov     [rdi+0Ch], eax
0x14007b04f  mov     rcx, [r13+20h]; Lock
0x14007b053  lea     rdx, [rsp+78h+LockState]; LockState
0x14007b05b  xor     r8d, r8d; Flags
0x14007b05e  xor     ebx, ebx
0x14007b060  call    cs:__imp_NdisAcquireRWLockWrite
0x14007b067  nop     dword ptr [rax+rax+00h]
0x14007b06c  mov     rax, [r13+30h]
0x14007b070  lea     rdx, [rsp+78h+LockState]; LockState
0x14007b078  mov     rcx, [r13+20h]; Lock
0x14007b07c  mov     [rsp+78h+var_50], rax
0x14007b081  mov     [r13+30h], rdi
0x14007b085  mov     [r13+28h], r15d
0x14007b089  call    cs:__imp_NdisReleaseRWLock
0x14007b090  nop     dword ptr [rax+rax+00h]
0x14007b095  mov     rax, [rsp+78h+var_48]
0x14007b09a  lea     rsi, WPP_GLOBAL_Control
0x14007b0a1  mov     rcx, [rsp+78h+arg_18]
0x14007b0a9  sub     r12d, eax
0x14007b0ac  add     r12d, dword ptr [rsp+78h+Size]
0x14007b0b1  mov     [rcx], rax
0x14007b0b4  mov     rax, [rsp+78h+arg_20]
0x14007b0bc  mov     [rax], r12d
0x14007b0bf  mov     rax, [rsp+78h+var_50]
0x14007b0c4  test    rax, rax
0x14007b0c7  jz      loc_14007B206
0x14007b0cd  lea     rcx, [rax-10h]; P
0x14007b0d1  mov     rax, [rcx]
0x14007b0d4  test    rax, rax
0x14007b0d7  jz      loc_14007B199
0x14007b0dd  mov     rdx, rcx; Entry
0x14007b0e0  mov     rcx, rax; Lookaside
0x14007b0e3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b0ea  nop     dword ptr [rax+rax+00h]
0x14007b0ef  jmp     loc_14007B206
0x14007b0f4  mov     ebx, 0C0010015h
0x14007b0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b100  lea     rsi, WPP_GLOBAL_Control
0x14007b107  cmp     rcx, rsi
0x14007b10a  jz      short loc_14007B121
0x14007b10c  mov     edx, 2Bh ; '+'
0x14007b111  mov     rcx, [rcx+18h]
0x14007b115  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007b11c  call    WPP_SF_
0x14007b121  lea     rcx, [r14+rbp]
0x14007b125  test    rcx, rcx
0x14007b128  jz      short loc_14007B159
0x14007b12a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b12e  mov     rax, [rcx]
0x14007b131  test    rax, rax
0x14007b134  jz      short loc_14007B14A
0x14007b136  mov     rdx, rcx; Entry
0x14007b139  mov     rcx, rax; Lookaside
0x14007b13c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b143  nop     dword ptr [rax+rax+00h]
0x14007b148  jmp     short loc_14007B159
0x14007b14a  mov     edx, [rcx+8]; Tag
0x14007b14d  call    cs:__imp_ExFreePoolWithTag
0x14007b154  nop     dword ptr [rax+rax+00h]
0x14007b159  test    rdi, rdi
0x14007b15c  jz      loc_14007B0BF
0x14007b162  lea     rcx, [rdi-10h]; P
0x14007b166  mov     rax, [rcx]
0x14007b169  test    rax, rax
0x14007b16c  jz      short loc_14007B185
0x14007b16e  mov     rdx, rcx; Entry
  ... truncated ...
```
