# WFDRoleAddCachedIEsToAssocParamIEsOidStructure(_WFD_ROLE *,DOT11_ASSOCIATION_PARAMS *,ulong,DOT11_ASSOCIATION_PARAMS * *,ulong *)

- ea: `0x140078658`
- end: `0x140078a0b`
- name: `?WFDRoleAddCachedIEsToAssocParamIEsOidStructure@@YAKPEAU_WFD_ROLE@@PEAUDOT11_ASSOCIATION_PARAMS@@KPEAPEAU2@PEAK@Z`
- size: `947`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, struct DOT11_ASSOCIATION_PARAMS *, ULONG, struct DOT11_ASSOCIATION_PARAMS **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14006aa40`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x14006da8c`
- `0x140078658`
- `0x14007a08c`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007885a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007885a`
- `ntoskrnl!ExAllocatePool2` at `0x14007886f`
- `ntoskrnl!ExAllocatePool2` at `0x14007886f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400787f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400787f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078998`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078998`
- `NDIS!NdisReleaseRWLock` at `0x1400787c9`
- `NDIS!NdisReleaseRWLock` at `0x1400787c9`
- `NDIS!NdisAcquireRWLockRead` at `0x140078721`
- `NDIS!NdisAcquireRWLockRead` at `0x140078721`

## pseudocode

```c
__int64 __fastcall WFDRoleAddCachedIEsToAssocParamIEsOidStructure(
        struct _WFD_ROLE *a1,
        struct DOT11_ASSOCIATION_PARAMS *a2,
        ULONG a3,
        struct DOT11_ASSOCIATION_PARAMS **a4,
        unsigned int *a5)
{
  unsigned int *v8; // r12
  ULONG uAssocRequestIEsOffset; // ecx
  ULONG v10; // edx
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  struct DOT11_ASSOCIATION_PARAMS *v12; // rdi
  unsigned int CachedFrameIEs; // ebx
  __int64 v14; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r15d
  unsigned int v18; // r13d
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  struct DOT11_ASSOCIATION_PARAMS **v22; // rax
  unsigned int v24[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct DOT11_ASSOCIATION_PARAMS **v26; // [rsp+98h] [rbp+20h]

  v26 = a4;
  v24[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    a4 = v26;
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
          uAssocRequestIEsOffset = a2->uAssocRequestIEsOffset;
          if ( uAssocRequestIEsOffset <= a3 )
          {
            v10 = uAssocRequestIEsOffset + a2->uAssocRequestIEsLength;
            if ( v10 >= uAssocRequestIEsOffset && v10 <= a3 )
            {
              pRWLock = a1->pRWLock;
              *a4 = 0;
              v12 = 0;
              *v8 = 0;
              NdisAcquireRWLockRead(pRWLock, &LockState, 0);
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 3u, v24, 0);
              if ( CachedFrameIEs )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_18;
                v16 = 160;
                goto LABEL_13;
              }
              v17 = v24[0];
              if ( !v24[0] )
                goto LABEL_18;
              v18 = v24[0] + a3;
              if ( v24[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    161,
                    WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                    a3,
                    v24[0]);
                goto LABEL_18;
              }
              v19 = v18 + 16;
              if ( v18 >= 0xFFFFFFF0 )
                goto LABEL_41;
              if ( v19 > 0x40 )
              {
                if ( v19 > 0x100 )
                {
                  if ( v19 > 0x400 )
                  {
                    if ( v19 > 0x800 )
                    {
                      p_WaitListHead = 0;
                      Pool2 = (_DWORD *)ExAllocatePool2(64, v19, 808613750, v14);
LABEL_32:
                      if ( Pool2 )
                      {
                        Pool2[2] = 808613750;
                        v12 = (struct DOT11_ASSOCIATION_PARAMS *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        memset(Pool2 + 4, 0, v18);
                        *(_OWORD *)&v12->Header.Type = *(_OWORD *)&a2->Header.Type;
                        v12->uAssocRequestIEsLength = a2->uAssocRequestIEsLength;
                        v12->uAssocRequestIEsOffset = 20;
                        v12->uAssocRequestIEsLength = v17 + a2->uAssocRequestIEsLength;
                        memmove(&v12[1], &a2->Header.Type + a2->uAssocRequestIEsOffset, a2->uAssocRequestIEsLength);
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           3u,
                                           v24,
                                           &v12[1].Header.Type + a2->uAssocRequestIEsLength);
                        if ( !CachedFrameIEs )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF__MAC_DD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              164,
                              (unsigned int)WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                              (_DWORD)v12 + 4,
                              v12->uAssocRequestIEsOffset,
                              v12->uAssocRequestIEsLength);
                          }
                          v22 = v26;
                          *v8 = v18;
                          *v22 = v12;
                          v12 = 0;
                          goto LABEL_18;
                        }
                        v15 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          v16 = 163;
LABEL_13:
                          WPP_SF_(v15->AttachedDevice, v16, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                          goto LABEL_18;
                        }
                        goto LABEL_18;
                      }
LABEL_41:
                      v12 = 0;
                      CachedFrameIEs = -1073741670;
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        v16 = 162;
                        goto LABEL_13;
                      }
LABEL_18:
                      NdisReleaseRWLock(a1->pRWLock, &LockState);
                      if ( v12 )
                      {
                        if ( *(_QWORD *)v12[-1].BSSID )
                          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12[-1].BSSID, v12[-1].BSSID);
                        else
                          ExFreePoolWithTag(v12[-1].BSSID, v12[-1].uAssocRequestIEsOffset);
                      }
                      goto LABEL_46;
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
              goto LABEL_32;
            }
          }
        }
      }
    }
  }
  CachedFrameIEs = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return CachedFrameIEs;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, CachedFrameIEs);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x140078658  mov     r11, rsp
0x14007865b  mov     [r11+10h], rbx
0x14007865f  mov     [r11+20h], r9
0x140078663  push    rbp
0x140078664  push    rsi
0x140078665  push    rdi
0x140078666  push    r12
0x140078668  push    r13
0x14007866a  push    r14
0x14007866c  push    r15
0x14007866e  sub     rsp, 40h
0x140078672  xor     ebx, ebx
0x140078674  mov     esi, r8d
0x140078677  xor     eax, eax
0x140078679  mov     [rsp+78h+var_48], ebx
0x14007867d  mov     [r11+9], ax
0x140078682  mov     rbp, rdx
0x140078685  mov     r14, rcx
0x140078688  mov     [r11+8], bl
0x14007868c  mov     rcx, cs:WPP_GLOBAL_Control
0x140078693  lea     r15, WPP_GLOBAL_Control
0x14007869a  cmp     rcx, r15
0x14007869d  jz      short loc_1400786BC
0x14007869f  mov     rcx, [rcx+18h]
0x1400786a3  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400786aa  mov     edx, 9Eh
0x1400786af  call    WPP_SF_
0x1400786b4  mov     r9, [rsp+78h+arg_18]
0x1400786bc  test    r14, r14
0x1400786bf  jz      loc_1400789A6
0x1400786c5  test    r9, r9
0x1400786c8  jz      loc_1400789A6
0x1400786ce  mov     r12, [rsp+78h+arg_20]
0x1400786d6  test    r12, r12
0x1400786d9  jz      loc_1400789A6
0x1400786df  test    rbp, rbp
0x1400786e2  jz      loc_1400789A6
0x1400786e8  mov     ecx, [rbp+0Ch]
0x1400786eb  cmp     ecx, esi
0x1400786ed  ja      loc_1400789A6
0x1400786f3  mov     edx, [rbp+10h]
0x1400786f6  add     edx, ecx
0x1400786f8  cmp     edx, ecx
0x1400786fa  jb      loc_1400789A6
0x140078700  cmp     edx, esi
0x140078702  ja      loc_1400789A6
0x140078708  mov     rcx, [r14+20h]; Lock
0x14007870c  lea     rdx, [rsp+78h+LockState]; LockState
0x140078714  xor     r8d, r8d; Flags
0x140078717  mov     [r9], rbx
0x14007871a  mov     rdi, rbx
0x14007871d  mov     [r12], ebx
0x140078721  call    cs:__imp_NdisAcquireRWLockRead
0x140078728  nop     dword ptr [rax+rax+00h]
0x14007872d  xor     r9d, r9d; unsigned __int8 *
0x140078730  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140078735  mov     rcx, r14; struct _WFD_ROLE *
0x140078738  lea     edx, [r9+3]; enum MANAGEMENT_FRAME_TYPE
0x14007873c  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140078741  mov     ebx, eax
0x140078743  test    eax, eax
0x140078745  jz      short loc_14007876A
0x140078747  mov     rcx, cs:WPP_GLOBAL_Control
0x14007874e  cmp     rcx, r15
0x140078751  jz      short loc_1400787BD
0x140078753  mov     edx, 0A0h
0x140078758  mov     rcx, [rcx+18h]
0x14007875c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078763  call    WPP_SF_
0x140078768  jmp     short loc_1400787BD
0x14007876a  mov     r15d, [rsp+78h+var_48]
0x14007876f  test    r15d, r15d
0x140078772  jz      short loc_1400787B6
0x140078774  lea     r13d, [r15+rsi]
0x140078778  cmp     r13d, esi
0x14007877b  jnb     loc_140078805
0x140078781  mov     ebx, 0C0000095h
0x140078786  mov     rcx, cs:WPP_GLOBAL_Control
0x14007878d  lea     rax, WPP_GLOBAL_Control
0x140078794  cmp     rcx, rax
0x140078797  jz      short loc_1400787B6
0x140078799  mov     rcx, [rcx+18h]
0x14007879d  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400787a4  mov     edx, 0A1h
0x1400787a9  mov     [rsp+78h+var_58], r15d
0x1400787ae  mov     r9d, esi
0x1400787b1  call    WPP_SF_Dd
0x1400787b6  lea     r15, WPP_GLOBAL_Control
0x1400787bd  mov     rcx, [r14+20h]; Lock
0x1400787c1  lea     rdx, [rsp+78h+LockState]; LockState
0x1400787c9  call    cs:__imp_NdisReleaseRWLock
0x1400787d0  nop     dword ptr [rax+rax+00h]
0x1400787d5  test    rdi, rdi
0x1400787d8  jz      loc_1400789CC
0x1400787de  lea     rcx, [rdi-10h]; P
0x1400787e2  mov     rax, [rcx]
0x1400787e5  test    rax, rax
0x1400787e8  jz      loc_140078995
0x1400787ee  mov     rdx, rcx; Entry
0x1400787f1  mov     rcx, rax; Lookaside
0x1400787f4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400787fb  nop     dword ptr [rax+rax+00h]
0x140078800  jmp     loc_1400789CC
0x140078805  lea     eax, [r13+10h]
0x140078809  cmp     eax, 10h
0x14007880c  jb      loc_14007896D
0x140078812  mov     ecx, 40h ; '@'
0x140078817  mov     edi, 30327776h
0x14007881c  cmp     eax, ecx
0x14007881e  ja      short loc_140078829
0x140078820  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140078827  jmp     short loc_140078857
0x140078829  cmp     eax, 100h
0x14007882e  ja      short loc_140078839
0x140078830  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140078837  jmp     short loc_140078857
0x140078839  cmp     eax, 400h
0x14007883e  ja      short loc_140078849
0x140078840  lea     rbx, Lookaside
0x140078847  jmp     short loc_140078857
0x140078849  cmp     eax, 800h
0x14007884e  ja      short loc_140078868
0x140078850  lea     rbx, stru_1400B0180
0x140078857  mov     rcx, rbx; Lookaside
0x14007885a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140078861  nop     dword ptr [rax+rax+00h]
0x140078866  jmp     short loc_14007887B
0x140078868  xor     ebx, ebx
0x14007886a  mov     edx, eax
0x14007886c  mov     r8d, edi
0x14007886f  call    cs:__imp_ExAllocatePool2
0x140078876  nop     dword ptr [rax+rax+00h]
0x14007887b  test    rax, rax
0x14007887e  jz      loc_14007896D
0x140078884  mov     [rax+8], edi
0x140078887  xor     edx, edx; Val
0x140078889  lea     rdi, [rax+10h]
0x14007888d  mov     r8d, r13d; Size
0x140078890  mov     rcx, rdi; void *
0x140078893  mov     [rax], rbx
0x140078896  call    memset
0x14007889b  movups  xmm0, xmmword ptr [rbp+0]
0x14007889f  lea     rbx, [rdi+14h]
0x1400788a3  movups  xmmword ptr [rdi], xmm0
0x1400788a6  mov     eax, [rbp+10h]
0x1400788a9  mov     [rdi+10h], eax
0x1400788ac  mov     dword ptr [rdi+0Ch], 14h
0x1400788b3  mov     ecx, [rbp+10h]
0x1400788b6  add     ecx, r15d
0x1400788b9  mov     [rdi+10h], ecx
0x1400788bc  mov     rcx, rbx; void *
0x1400788bf  mov     edx, [rbp+0Ch]
0x1400788c2  mov     r8d, [rbp+10h]; Size
0x1400788c6  add     rdx, rbp; Src
0x1400788c9  call    memmove
0x1400788ce  mov     r9d, [rbp+10h]
0x1400788d2  lea     r8, [rsp+78h+var_48]; unsigned int *
0x1400788d7  add     r9, rbx; unsigned __int8 *
0x1400788da  mov     edx, 3; enum MANAGEMENT_FRAME_TYPE
0x1400788df  mov     rcx, r14; struct _WFD_ROLE *
0x1400788e2  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x1400788e7  mov     ebx, eax
0x1400788e9  test    eax, eax
0x1400788eb  jz      short loc_14007890E
0x1400788ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400788f4  lea     r15, WPP_GLOBAL_Control
0x1400788fb  cmp     rcx, r15
0x1400788fe  jz      loc_1400787BD
0x140078904  mov     edx, 0A3h
0x140078909  jmp     loc_140078758
0x14007890e  mov     rcx, cs:WPP_GLOBAL_Control
0x140078915  lea     r15, WPP_GLOBAL_Control
0x14007891c  cmp     rcx, r15
0x14007891f  jz      short loc_140078957
0x140078921  cmp     byte ptr [rcx+29h], 3
0x140078925  jb      short loc_140078957
0x140078927  test    dword ptr [rcx+2Ch], 200000h
0x14007892e  jz      short loc_140078957
0x140078930  mov     eax, [rdi+10h]
0x140078933  lea     r9, [rdi+4]
0x140078937  mov     rcx, [rcx+18h]
0x14007893b  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078942  mov     [rsp+78h+var_50], eax
0x140078946  mov     edx, 0A4h
0x14007894b  mov     eax, [rdi+0Ch]
0x14007894e  mov     [rsp+78h+var_58], eax
0x140078952  call    WPP_SF__MAC_DD
0x140078957  mov     rax, [rsp+78h+arg_18]
0x14007895f  mov     [r12], r13d
0x140078963  mov     [rax], rdi
0x140078966  xor     edi, edi
0x140078968  jmp     loc_1400787BD
0x14007896d  xor     edi, edi
0x14007896f  mov     ebx, 0C000009Ah
0x140078974  mov     rcx, cs:WPP_GLOBAL_Control
0x14007897b  lea     r15, WPP_GLOBAL_Control
0x140078982  cmp     rcx, r15
0x140078985  jz      loc_1400787BD
0x14007898b  mov     edx, 0A2h
0x140078990  jmp     loc_140078758
0x140078995  mov     edx, [rcx+8]; Tag
0x140078998  call    cs:__imp_ExFreePoolWithTag
0x14007899f  nop     dword ptr [rax+rax+00h]
0x1400789a4  jmp     short loc_1400789CC
0x1400789a6  mov     ebx, 0C000000Dh
0x1400789ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400789b2  cmp     rcx, r15
0x1400789b5  jz      short loc_1400789F0
0x1400789b7  mov     rcx, [rcx+18h]
0x1400789bb  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400789c2  mov     edx, 9Fh
0x1400789c7  call    WPP_SF_
0x1400789cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400789d3  cmp     rcx, r15
0x1400789d6  jz      short loc_1400789F0
0x1400789d8  mov     rcx, [rcx+18h]
0x1400789dc  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400789e3  mov     edx, 0A5h
0x1400789e8  mov     r9d, ebx
0x1400789eb  call    WPP_SF_d
0x1400789f0  mov     eax, ebx
0x1400789f2  mov     rbx, [rsp+78h+arg_8]
0x1400789fa  add     rsp, 40h
0x1400789fe  pop     r15
0x140078a00  pop     r14
0x140078a02  pop     r13
0x140078a04  pop     r12
0x140078a06  pop     rdi
0x140078a07  pop     rsi
0x140078a08  pop     rbp
0x140078a09  retn
```
