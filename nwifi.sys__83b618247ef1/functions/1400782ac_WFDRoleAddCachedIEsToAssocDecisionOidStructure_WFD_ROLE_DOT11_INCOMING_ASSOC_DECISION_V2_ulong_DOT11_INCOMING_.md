# WFDRoleAddCachedIEsToAssocDecisionOidStructure(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_DECISION_V2 *,ulong,_DOT11_INCOMING_ASSOC_DECISION_V2 * *,ulong *)

- ea: `0x1400782ac`
- end: `0x140078650`
- name: `?WFDRoleAddCachedIEsToAssocDecisionOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_DECISION_V2@@KPEAPEAU2@PEAK@Z`
- size: `932`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, struct _DOT11_INCOMING_ASSOC_DECISION_V2 *, unsigned int, struct _DOT11_INCOMING_ASSOC_DECISION_V2 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140073cdc`
- `0x140074768`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x1400782ac`
- `0x14007a08c`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007845f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007845f`
- `ntoskrnl!ExAllocatePool2` at `0x140078474`
- `ntoskrnl!ExAllocatePool2` at `0x140078474`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400785cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400785cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400785dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400785dd`
- `NDIS!NdisReleaseRWLock` at `0x1400785a9`
- `NDIS!NdisReleaseRWLock` at `0x1400785a9`
- `NDIS!NdisAcquireRWLockRead` at `0x140078375`
- `NDIS!NdisAcquireRWLockRead` at `0x140078375`

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
  __int64 v14; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r12d
  unsigned int v18; // r15d
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 **v22; // rax
  unsigned int v24[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 **v26; // [rsp+98h] [rbp+20h]

  v26 = a4;
  v24[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
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
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 4u, v24, 0);
              if ( CachedFrameIEs )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v16 = 168;
                goto LABEL_39;
              }
              v17 = v24[0];
              if ( !v24[0] )
                goto LABEL_40;
              v18 = v24[0] + a3;
              if ( v24[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    169,
                    WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                    a3,
                    v24[0]);
                goto LABEL_40;
              }
              v19 = v18 + 16;
              if ( v18 >= 0xFFFFFFF0 )
              {
LABEL_37:
                v12 = 0;
                CachedFrameIEs = -1073741670;
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v16 = 170;
                goto LABEL_39;
              }
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
LABEL_28:
                      if ( Pool2 )
                      {
                        Pool2[2] = 808613750;
                        v12 = (char *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        memset(Pool2 + 4, 0, v18);
                        *(_OWORD *)v12 = *(_OWORD *)a2;
                        *(_OWORD *)(v12 + 12) = *(_OWORD *)((char *)a2 + 12);
                        *((_DWORD *)v12 + 4) = 28;
                        *((_DWORD *)v12 + 5) = v17 + *((_DWORD *)a2 + 5);
                        memmove(v12 + 28, (char *)a2 + *((unsigned int *)a2 + 4), *((unsigned int *)a2 + 5));
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           4u,
                                           v24,
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
                          v22 = v26;
                          *v8 = v18;
                          *v22 = (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v12;
                          v12 = 0;
                          goto LABEL_40;
                        }
                        v15 = WPP_GLOBAL_Control;
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
                        v16 = 171;
LABEL_39:
                        WPP_SF_(v15->AttachedDevice, v16, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                        goto LABEL_40;
                      }
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
0x1400782ac  mov     r11, rsp
0x1400782af  mov     [r11+10h], rbx
0x1400782b3  mov     [r11+20h], r9
0x1400782b7  push    rbp
0x1400782b8  push    rsi
0x1400782b9  push    rdi
0x1400782ba  push    r12
0x1400782bc  push    r13
0x1400782be  push    r14
0x1400782c0  push    r15
0x1400782c2  sub     rsp, 40h
0x1400782c6  xor     ebx, ebx
0x1400782c8  mov     esi, r8d
0x1400782cb  xor     eax, eax
0x1400782cd  mov     [rsp+78h+var_48], ebx
0x1400782d1  mov     [r11+9], ax
0x1400782d6  mov     rbp, rdx
0x1400782d9  mov     r14, rcx
0x1400782dc  mov     [r11+8], bl
0x1400782e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400782e7  lea     r15, WPP_GLOBAL_Control
0x1400782ee  cmp     rcx, r15
0x1400782f1  jz      short loc_140078310
0x1400782f3  mov     rcx, [rcx+18h]
0x1400782f7  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400782fe  mov     edx, 0A6h
0x140078303  call    WPP_SF_
0x140078308  mov     r9, [rsp+78h+arg_18]
0x140078310  test    r14, r14
0x140078313  jz      loc_1400785EB
0x140078319  test    r9, r9
0x14007831c  jz      loc_1400785EB
0x140078322  mov     r13, [rsp+78h+arg_20]
0x14007832a  test    r13, r13
0x14007832d  jz      loc_1400785EB
0x140078333  test    rbp, rbp
0x140078336  jz      loc_1400785EB
0x14007833c  mov     ecx, [rbp+10h]
0x14007833f  cmp     ecx, esi
0x140078341  ja      loc_1400785EB
0x140078347  mov     edx, [rbp+14h]
0x14007834a  add     edx, ecx
0x14007834c  cmp     edx, ecx
0x14007834e  jb      loc_1400785EB
0x140078354  cmp     edx, esi
0x140078356  ja      loc_1400785EB
0x14007835c  mov     rcx, [r14+20h]; Lock
0x140078360  lea     rdx, [rsp+78h+LockState]; LockState
0x140078368  xor     r8d, r8d; Flags
0x14007836b  mov     [r9], rbx
0x14007836e  mov     rdi, rbx
0x140078371  mov     [r13+0], ebx
0x140078375  call    cs:__imp_NdisAcquireRWLockRead
0x14007837c  nop     dword ptr [rax+rax+00h]
0x140078381  xor     r9d, r9d; unsigned __int8 *
0x140078384  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140078389  mov     rcx, r14; struct _WFD_ROLE *
0x14007838c  lea     edx, [r9+4]; enum MANAGEMENT_FRAME_TYPE
0x140078390  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140078395  mov     ebx, eax
0x140078397  test    eax, eax
0x140078399  jz      short loc_1400783B5
0x14007839b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400783a2  cmp     rcx, r15
0x1400783a5  jz      loc_14007859D
0x1400783ab  mov     edx, 0A8h
0x1400783b0  jmp     loc_14007858D
0x1400783b5  mov     r12d, [rsp+78h+var_48]
0x1400783ba  test    r12d, r12d
0x1400783bd  jz      loc_14007859D
0x1400783c3  lea     r15d, [r12+rsi]
0x1400783c7  cmp     r15d, esi
0x1400783ca  jnb     short loc_14007840A
0x1400783cc  mov     ebx, 0C0000095h
0x1400783d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400783d8  lea     r15, WPP_GLOBAL_Control
0x1400783df  cmp     rcx, r15
0x1400783e2  jz      loc_14007859D
0x1400783e8  mov     rcx, [rcx+18h]
0x1400783ec  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400783f3  mov     edx, 0A9h
0x1400783f8  mov     [rsp+78h+var_58], r12d
0x1400783fd  mov     r9d, esi
0x140078400  call    WPP_SF_Dd
0x140078405  jmp     loc_14007859D
0x14007840a  lea     eax, [r15+10h]
0x14007840e  cmp     eax, 10h
0x140078411  jb      loc_14007856E
0x140078417  mov     ecx, 40h ; '@'
0x14007841c  mov     edi, 30327776h
0x140078421  cmp     eax, ecx
0x140078423  ja      short loc_14007842E
0x140078425  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007842c  jmp     short loc_14007845C
0x14007842e  cmp     eax, 100h
0x140078433  ja      short loc_14007843E
0x140078435  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007843c  jmp     short loc_14007845C
0x14007843e  cmp     eax, 400h
0x140078443  ja      short loc_14007844E
0x140078445  lea     rbx, Lookaside
0x14007844c  jmp     short loc_14007845C
0x14007844e  cmp     eax, 800h
0x140078453  ja      short loc_14007846D
0x140078455  lea     rbx, stru_1400B0180
0x14007845c  mov     rcx, rbx; Lookaside
0x14007845f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140078466  nop     dword ptr [rax+rax+00h]
0x14007846b  jmp     short loc_140078480
0x14007846d  xor     ebx, ebx
0x14007846f  mov     edx, eax
0x140078471  mov     r8d, edi
0x140078474  call    cs:__imp_ExAllocatePool2
0x14007847b  nop     dword ptr [rax+rax+00h]
0x140078480  test    rax, rax
0x140078483  jz      loc_14007856E
0x140078489  mov     [rax+8], edi
0x14007848c  xor     edx, edx; Val
0x14007848e  lea     rdi, [rax+10h]
0x140078492  mov     r8d, r15d; Size
0x140078495  mov     rcx, rdi; void *
0x140078498  mov     [rax], rbx
0x14007849b  call    memset
0x1400784a0  movups  xmm0, xmmword ptr [rbp+0]
0x1400784a4  lea     rbx, [rdi+1Ch]
0x1400784a8  movups  xmmword ptr [rdi], xmm0
0x1400784ab  movups  xmm1, xmmword ptr [rbp+0Ch]
0x1400784af  movups  xmmword ptr [rdi+0Ch], xmm1
0x1400784b3  mov     dword ptr [rdi+10h], 1Ch
0x1400784ba  mov     ecx, [rbp+14h]
0x1400784bd  add     ecx, r12d
0x1400784c0  mov     [rdi+14h], ecx
0x1400784c3  mov     rcx, rbx; void *
0x1400784c6  mov     edx, [rbp+10h]
0x1400784c9  mov     r8d, [rbp+14h]; Size
0x1400784cd  add     rdx, rbp; Src
0x1400784d0  call    memmove
0x1400784d5  mov     r9d, [rbp+14h]
0x1400784d9  lea     r8, [rsp+78h+var_48]; unsigned int *
0x1400784de  add     r9, rbx; unsigned __int8 *
0x1400784e1  mov     edx, 4; enum MANAGEMENT_FRAME_TYPE
0x1400784e6  mov     rcx, r14; struct _WFD_ROLE *
0x1400784e9  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x1400784ee  mov     ebx, eax
0x1400784f0  test    eax, eax
0x1400784f2  jz      short loc_140078512
0x1400784f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400784fb  lea     r15, WPP_GLOBAL_Control
0x140078502  cmp     rcx, r15
0x140078505  jz      loc_14007859D
0x14007850b  mov     edx, 0ABh
0x140078510  jmp     short loc_14007858D
0x140078512  mov     rcx, cs:WPP_GLOBAL_Control
0x140078519  lea     rax, WPP_GLOBAL_Control
0x140078520  cmp     rcx, rax
0x140078523  jz      short loc_140078554
0x140078525  cmp     byte ptr [rcx+29h], 3
0x140078529  jb      short loc_140078554
0x14007852b  test    dword ptr [rcx+2Ch], 200000h
0x140078532  jz      short loc_140078554
0x140078534  mov     eax, [rdi+14h]
0x140078537  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007853e  mov     r9d, [rdi+10h]
0x140078542  mov     edx, 0ACh
0x140078547  mov     rcx, [rcx+18h]
0x14007854b  mov     [rsp+78h+var_58], eax
0x14007854f  call    WPP_SF_Dd
0x140078554  mov     rax, [rsp+78h+arg_18]
0x14007855c  mov     [r13+0], r15d
0x140078560  lea     r15, WPP_GLOBAL_Control
0x140078567  mov     [rax], rdi
0x14007856a  xor     edi, edi
0x14007856c  jmp     short loc_14007859D
0x14007856e  xor     edi, edi
0x140078570  mov     ebx, 0C000009Ah
0x140078575  mov     rcx, cs:WPP_GLOBAL_Control
0x14007857c  lea     r15, WPP_GLOBAL_Control
0x140078583  cmp     rcx, r15
0x140078586  jz      short loc_14007859D
0x140078588  mov     edx, 0AAh
0x14007858d  mov     rcx, [rcx+18h]
0x140078591  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078598  call    WPP_SF_
0x14007859d  mov     rcx, [r14+20h]; Lock
0x1400785a1  lea     rdx, [rsp+78h+LockState]; LockState
0x1400785a9  call    cs:__imp_NdisReleaseRWLock
0x1400785b0  nop     dword ptr [rax+rax+00h]
0x1400785b5  test    rdi, rdi
0x1400785b8  jz      short loc_140078611
0x1400785ba  lea     rcx, [rdi-10h]; P
0x1400785be  mov     rax, [rcx]
0x1400785c1  test    rax, rax
0x1400785c4  jz      short loc_1400785DA
0x1400785c6  mov     rdx, rcx; Entry
0x1400785c9  mov     rcx, rax; Lookaside
0x1400785cc  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400785d3  nop     dword ptr [rax+rax+00h]
0x1400785d8  jmp     short loc_140078611
0x1400785da  mov     edx, [rcx+8]; Tag
0x1400785dd  call    cs:__imp_ExFreePoolWithTag
0x1400785e4  nop     dword ptr [rax+rax+00h]
0x1400785e9  jmp     short loc_140078611
0x1400785eb  mov     ebx, 0C000000Dh
0x1400785f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400785f7  cmp     rcx, r15
0x1400785fa  jz      short loc_140078635
0x1400785fc  mov     rcx, [rcx+18h]
0x140078600  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078607  mov     edx, 0A7h
0x14007860c  call    WPP_SF_
0x140078611  mov     rcx, cs:WPP_GLOBAL_Control
0x140078618  cmp     rcx, r15
0x14007861b  jz      short loc_140078635
0x14007861d  mov     rcx, [rcx+18h]
0x140078621  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140078628  mov     edx, 0ADh
0x14007862d  mov     r9d, ebx
0x140078630  call    WPP_SF_d
0x140078635  mov     eax, ebx
0x140078637  mov     rbx, [rsp+78h+arg_8]
0x14007863f  add     rsp, 40h
0x140078643  pop     r15
0x140078645  pop     r14
0x140078647  pop     r13
0x140078649  pop     r12
0x14007864b  pop     rdi
0x14007864c  pop     rsi
0x14007864d  pop     rbp
0x14007864e  retn
```
