# WFDRoleAddCachedIEsToAssocDecisionOidStructure(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_DECISION_V2 *,ulong,_DOT11_INCOMING_ASSOC_DECISION_V2 * *,ulong *)

- ea: `0x140079adc`
- end: `0x140079e80`
- name: `?WFDRoleAddCachedIEsToAssocDecisionOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_DECISION_V2@@KPEAPEAU2@PEAK@Z`
- size: `932`
- prototype: `unsigned int __usercall@<eax>(struct _WFD_ROLE *@<rcx>, struct _DOT11_INCOMING_ASSOC_DECISION_V2 *@<rdx>, unsigned int@<r8d>, struct _DOT11_INCOMING_ASSOC_DECISION_V2 **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007550c`
- `0x140075f98`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140079adc`
- `0x14007b8bc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079c8f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140079c8f`
- `ntoskrnl!ExAllocatePool2` at `0x140079ca4`
- `ntoskrnl!ExAllocatePool2` at `0x140079ca4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079dfc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140079dfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079e0d`
- `NDIS!NdisReleaseRWLock` at `0x140079dd9`
- `NDIS!NdisReleaseRWLock` at `0x140079dd9`
- `NDIS!NdisAcquireRWLockRead` at `0x140079ba5`
- `NDIS!NdisAcquireRWLockRead` at `0x140079ba5`

## pseudocode

```c
__int64 __fastcall WFDRoleAddCachedIEsToAssocDecisionOidStructure(
        struct _WFD_ROLE *a1,
        struct _DOT11_INCOMING_ASSOC_DECISION_V2 *a2,
        unsigned int a3,
        struct _DOT11_INCOMING_ASSOC_DECISION_V2 **a4,
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
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 **v21; // rax
  unsigned int v23[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 **v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  v23[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
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
          v9 = *((_DWORD *)a2 + 4);
          if ( v9 <= a3 )
          {
            v10 = v9 + *((_DWORD *)a2 + 5);
            if ( v10 >= v9 && v10 <= a3 )
            {
              pRWLock = a1->pRWLock;
              *a4 = 0;
              v12 = 0;
              *v8 = 0;
              NdisAcquireRWLockRead(pRWLock, &LockState, 0);
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 4u, v23, 0);
              if ( CachedFrameIEs )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v15 = 168;
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
                    169,
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
                v15 = 170;
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
                        *(_OWORD *)(v12 + 12) = *(_OWORD *)((char *)a2 + 12);
                        *((_DWORD *)v12 + 4) = 28;
                        *((_DWORD *)v12 + 5) = v16 + *((_DWORD *)a2 + 5);
                        memmove(v12 + 28, (char *)a2 + *((unsigned int *)a2 + 4), *((unsigned int *)a2 + 5));
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           4u,
                                           v23,
                                           (unsigned __int8 *)&v12[*((unsigned int *)a2 + 5) + 28]);
                        if ( !CachedFrameIEs )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                          {
                            WPP_SF_Dd(
                              WPP_GLOBAL_Control->AttachedDevice,
                              172,
                              WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                              *((unsigned int *)v12 + 4),
                              *((_DWORD *)v12 + 5));
                          }
                          v21 = v25;
                          *v8 = v17;
                          *v21 = (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v12;
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
                        v15 = 171;
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
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, CachedFrameIEs);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x140079adc  mov     r11, rsp
0x140079adf  mov     [r11+10h], rbx
0x140079ae3  mov     [r11+20h], r9
0x140079ae7  push    rbp
0x140079ae8  push    rsi
0x140079ae9  push    rdi
0x140079aea  push    r12
0x140079aec  push    r13
0x140079aee  push    r14
0x140079af0  push    r15
0x140079af2  sub     rsp, 40h
0x140079af6  xor     ebx, ebx
0x140079af8  mov     esi, r8d
0x140079afb  xor     eax, eax
0x140079afd  mov     [rsp+78h+var_48], ebx
0x140079b01  mov     [r11+9], ax
0x140079b06  mov     rbp, rdx
0x140079b09  mov     r14, rcx
0x140079b0c  mov     [r11+8], bl
0x140079b10  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b17  lea     r15, WPP_GLOBAL_Control
0x140079b1e  cmp     rcx, r15
0x140079b21  jz      short loc_140079B40
0x140079b23  mov     rcx, [rcx+18h]
0x140079b27  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079b2e  mov     edx, 0A6h
0x140079b33  call    WPP_SF_
0x140079b38  mov     r9, [rsp+78h+arg_18]
0x140079b40  test    r14, r14
0x140079b43  jz      loc_140079E1B
0x140079b49  test    r9, r9
0x140079b4c  jz      loc_140079E1B
0x140079b52  mov     r13, [rsp+78h+arg_20]
0x140079b5a  test    r13, r13
0x140079b5d  jz      loc_140079E1B
0x140079b63  test    rbp, rbp
0x140079b66  jz      loc_140079E1B
0x140079b6c  mov     ecx, [rbp+10h]
0x140079b6f  cmp     ecx, esi
0x140079b71  ja      loc_140079E1B
0x140079b77  mov     edx, [rbp+14h]
0x140079b7a  add     edx, ecx
0x140079b7c  cmp     edx, ecx
0x140079b7e  jb      loc_140079E1B
0x140079b84  cmp     edx, esi
0x140079b86  ja      loc_140079E1B
0x140079b8c  mov     rcx, [r14+20h]; Lock
0x140079b90  lea     rdx, [rsp+78h+LockState]; LockState
0x140079b98  xor     r8d, r8d; Flags
0x140079b9b  mov     [r9], rbx
0x140079b9e  mov     rdi, rbx
0x140079ba1  mov     [r13+0], ebx
0x140079ba5  call    cs:__imp_NdisAcquireRWLockRead
0x140079bac  nop     dword ptr [rax+rax+00h]
0x140079bb1  xor     r9d, r9d; unsigned __int8 *
0x140079bb4  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140079bb9  mov     rcx, r14; struct _WFD_ROLE *
0x140079bbc  lea     edx, [r9+4]; enum MANAGEMENT_FRAME_TYPE
0x140079bc0  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140079bc5  mov     ebx, eax
0x140079bc7  test    eax, eax
0x140079bc9  jz      short loc_140079BE5
0x140079bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140079bd2  cmp     rcx, r15
0x140079bd5  jz      loc_140079DCD
0x140079bdb  mov     edx, 0A8h
0x140079be0  jmp     loc_140079DBD
0x140079be5  mov     r12d, [rsp+78h+var_48]
0x140079bea  test    r12d, r12d
0x140079bed  jz      loc_140079DCD
0x140079bf3  lea     r15d, [r12+rsi]
0x140079bf7  cmp     r15d, esi
0x140079bfa  jnb     short loc_140079C3A
0x140079bfc  mov     ebx, 0C0000095h
0x140079c01  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c08  lea     r15, WPP_GLOBAL_Control
0x140079c0f  cmp     rcx, r15
0x140079c12  jz      loc_140079DCD
0x140079c18  mov     rcx, [rcx+18h]
0x140079c1c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079c23  mov     edx, 0A9h
0x140079c28  mov     [rsp+78h+var_58], r12d
0x140079c2d  mov     r9d, esi
0x140079c30  call    WPP_SF_Dd
0x140079c35  jmp     loc_140079DCD
0x140079c3a  lea     eax, [r15+10h]
0x140079c3e  cmp     eax, 10h
0x140079c41  jb      loc_140079D9E
0x140079c47  mov     ecx, 40h ; '@'
0x140079c4c  mov     edi, 30327776h
0x140079c51  cmp     eax, ecx
0x140079c53  ja      short loc_140079C5E
0x140079c55  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140079c5c  jmp     short loc_140079C8C
0x140079c5e  cmp     eax, 100h
0x140079c63  ja      short loc_140079C6E
0x140079c65  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140079c6c  jmp     short loc_140079C8C
0x140079c6e  cmp     eax, 400h
0x140079c73  ja      short loc_140079C7E
0x140079c75  lea     rbx, Lookaside
0x140079c7c  jmp     short loc_140079C8C
0x140079c7e  cmp     eax, 800h
0x140079c83  ja      short loc_140079C9D
0x140079c85  lea     rbx, stru_1400B31C0
0x140079c8c  mov     rcx, rbx; Lookaside
0x140079c8f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079c96  nop     dword ptr [rax+rax+00h]
0x140079c9b  jmp     short loc_140079CB0
0x140079c9d  xor     ebx, ebx
0x140079c9f  mov     edx, eax
0x140079ca1  mov     r8d, edi
0x140079ca4  call    cs:__imp_ExAllocatePool2
0x140079cab  nop     dword ptr [rax+rax+00h]
0x140079cb0  test    rax, rax
0x140079cb3  jz      loc_140079D9E
0x140079cb9  mov     [rax+8], edi
0x140079cbc  xor     edx, edx; Val
0x140079cbe  lea     rdi, [rax+10h]
0x140079cc2  mov     r8d, r15d; Size
0x140079cc5  mov     rcx, rdi; void *
0x140079cc8  mov     [rax], rbx
0x140079ccb  call    memset
0x140079cd0  movups  xmm0, xmmword ptr [rbp+0]
0x140079cd4  lea     rbx, [rdi+1Ch]
0x140079cd8  movups  xmmword ptr [rdi], xmm0
0x140079cdb  movups  xmm1, xmmword ptr [rbp+0Ch]
0x140079cdf  movups  xmmword ptr [rdi+0Ch], xmm1
0x140079ce3  mov     dword ptr [rdi+10h], 1Ch
0x140079cea  mov     ecx, [rbp+14h]
0x140079ced  add     ecx, r12d
0x140079cf0  mov     [rdi+14h], ecx
0x140079cf3  mov     rcx, rbx; void *
0x140079cf6  mov     edx, [rbp+10h]
0x140079cf9  mov     r8d, [rbp+14h]; Size
0x140079cfd  add     rdx, rbp; Src
0x140079d00  call    memmove
0x140079d05  mov     r9d, [rbp+14h]
0x140079d09  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140079d0e  add     r9, rbx; unsigned __int8 *
0x140079d11  mov     edx, 4; enum MANAGEMENT_FRAME_TYPE
0x140079d16  mov     rcx, r14; struct _WFD_ROLE *
0x140079d19  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140079d1e  mov     ebx, eax
0x140079d20  test    eax, eax
0x140079d22  jz      short loc_140079D42
0x140079d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d2b  lea     r15, WPP_GLOBAL_Control
0x140079d32  cmp     rcx, r15
0x140079d35  jz      loc_140079DCD
0x140079d3b  mov     edx, 0ABh
0x140079d40  jmp     short loc_140079DBD
0x140079d42  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d49  lea     rax, WPP_GLOBAL_Control
0x140079d50  cmp     rcx, rax
0x140079d53  jz      short loc_140079D84
0x140079d55  cmp     byte ptr [rcx+29h], 3
0x140079d59  jb      short loc_140079D84
0x140079d5b  test    dword ptr [rcx+2Ch], 200000h
0x140079d62  jz      short loc_140079D84
0x140079d64  mov     eax, [rdi+14h]
0x140079d67  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079d6e  mov     r9d, [rdi+10h]
0x140079d72  mov     edx, 0ACh
0x140079d77  mov     rcx, [rcx+18h]
0x140079d7b  mov     [rsp+78h+var_58], eax
0x140079d7f  call    WPP_SF_Dd
0x140079d84  mov     rax, [rsp+78h+arg_18]
0x140079d8c  mov     [r13+0], r15d
0x140079d90  lea     r15, WPP_GLOBAL_Control
0x140079d97  mov     [rax], rdi
0x140079d9a  xor     edi, edi
0x140079d9c  jmp     short loc_140079DCD
0x140079d9e  xor     edi, edi
0x140079da0  mov     ebx, 0C000009Ah
0x140079da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140079dac  lea     r15, WPP_GLOBAL_Control
0x140079db3  cmp     rcx, r15
0x140079db6  jz      short loc_140079DCD
0x140079db8  mov     edx, 0AAh
0x140079dbd  mov     rcx, [rcx+18h]
0x140079dc1  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079dc8  call    WPP_SF_
0x140079dcd  mov     rcx, [r14+20h]; Lock
0x140079dd1  lea     rdx, [rsp+78h+LockState]; LockState
0x140079dd9  call    cs:__imp_NdisReleaseRWLock
0x140079de0  nop     dword ptr [rax+rax+00h]
0x140079de5  test    rdi, rdi
0x140079de8  jz      short loc_140079E41
0x140079dea  lea     rcx, [rdi-10h]; P
0x140079dee  mov     rax, [rcx]
0x140079df1  test    rax, rax
0x140079df4  jz      short loc_140079E0A
0x140079df6  mov     rdx, rcx; Entry
0x140079df9  mov     rcx, rax; Lookaside
0x140079dfc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079e03  nop     dword ptr [rax+rax+00h]
0x140079e08  jmp     short loc_140079E41
0x140079e0a  mov     edx, [rcx+8]; Tag
0x140079e0d  call    cs:__imp_ExFreePoolWithTag
0x140079e14  nop     dword ptr [rax+rax+00h]
0x140079e19  jmp     short loc_140079E41
0x140079e1b  mov     ebx, 0C000000Dh
0x140079e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e27  cmp     rcx, r15
0x140079e2a  jz      short loc_140079E65
0x140079e2c  mov     rcx, [rcx+18h]
0x140079e30  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079e37  mov     edx, 0A7h
0x140079e3c  call    WPP_SF_
0x140079e41  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e48  cmp     rcx, r15
0x140079e4b  jz      short loc_140079E65
0x140079e4d  mov     rcx, [rcx+18h]
0x140079e51  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079e58  mov     edx, 0ADh
0x140079e5d  mov     r9d, ebx
0x140079e60  call    WPP_SF_d
0x140079e65  mov     eax, ebx
0x140079e67  mov     rbx, [rsp+78h+arg_8]
0x140079e6f  add     rsp, 40h
0x140079e73  pop     r15
0x140079e75  pop     r14
0x140079e77  pop     r13
0x140079e79  pop     r12
0x140079e7b  pop     rdi
0x140079e7c  pop     rsi
0x140079e7d  pop     rbp
0x140079e7e  retn
```
