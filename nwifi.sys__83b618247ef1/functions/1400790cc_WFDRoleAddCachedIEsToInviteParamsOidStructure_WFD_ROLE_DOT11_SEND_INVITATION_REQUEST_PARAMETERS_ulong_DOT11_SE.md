# WFDRoleAddCachedIEsToInviteParamsOidStructure(_WFD_ROLE *,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS *,ulong,_DOT11_SEND_INVITATION_REQUEST_PARAMETERS * *,ulong *)

- ea: `0x1400790cc`
- end: `0x140079492`
- name: `?WFDRoleAddCachedIEsToInviteParamsOidStructure@@YAKPEAU_WFD_ROLE@@PEAU_DOT11_SEND_INVITATION_REQUEST_PARAMETERS@@KPEAPEAU2@PEAK@Z`
- size: `966`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *, unsigned int, struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400879a0`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x1400790cc`
- `0x14007a08c`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007927f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007927f`
- `ntoskrnl!ExAllocatePool2` at `0x140079294`
- `ntoskrnl!ExAllocatePool2` at `0x140079294`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007940e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007940e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007941f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007941f`
- `NDIS!NdisReleaseRWLock` at `0x1400793eb`
- `NDIS!NdisReleaseRWLock` at `0x1400793eb`
- `NDIS!NdisAcquireRWLockRead` at `0x140079195`
- `NDIS!NdisAcquireRWLockRead` at `0x140079195`

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
  __int64 v14; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r12d
  unsigned int v18; // r15d
  unsigned int v19; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **v22; // rax
  unsigned int v24[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS **v26; // [rsp+98h] [rbp+20h]

  v26 = a4;
  v24[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
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
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 8u, v24, 0);
              if ( CachedFrameIEs )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_40;
                v16 = 176;
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
                    177,
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
                v16 = 178;
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
                        *((_OWORD *)v12 + 1) = *((_OWORD *)a2 + 1);
                        *((_OWORD *)v12 + 2) = *((_OWORD *)a2 + 2);
                        *((_OWORD *)v12 + 3) = *((_OWORD *)a2 + 3);
                        *((_OWORD *)v12 + 4) = *((_OWORD *)a2 + 4);
                        *((_QWORD *)v12 + 10) = *((_QWORD *)a2 + 10);
                        *((_DWORD *)v12 + 20) = 88;
                        *((_DWORD *)v12 + 21) = v17 + *((_DWORD *)a2 + 21);
                        memmove(v12 + 88, (char *)a2 + *((unsigned int *)a2 + 20), *((unsigned int *)a2 + 21));
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           8u,
                                           v24,
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
                          v22 = v26;
                          *v8 = v18;
                          *v22 = (struct _DOT11_SEND_INVITATION_REQUEST_PARAMETERS *)v12;
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
                        v16 = 179;
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
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 175, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 181, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, CachedFrameIEs);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x1400790cc  mov     r11, rsp
0x1400790cf  mov     [r11+10h], rbx
0x1400790d3  mov     [r11+20h], r9
0x1400790d7  push    rbp
0x1400790d8  push    rsi
0x1400790d9  push    rdi
0x1400790da  push    r12
0x1400790dc  push    r13
0x1400790de  push    r14
0x1400790e0  push    r15
0x1400790e2  sub     rsp, 40h
0x1400790e6  xor     ebx, ebx
0x1400790e8  mov     esi, r8d
0x1400790eb  xor     eax, eax
0x1400790ed  mov     [rsp+78h+var_48], ebx
0x1400790f1  mov     [r11+9], ax
0x1400790f6  mov     rbp, rdx
0x1400790f9  mov     r14, rcx
0x1400790fc  mov     [r11+8], bl
0x140079100  mov     rcx, cs:WPP_GLOBAL_Control
0x140079107  lea     r15, WPP_GLOBAL_Control
0x14007910e  cmp     rcx, r15
0x140079111  jz      short loc_140079130
0x140079113  mov     rcx, [rcx+18h]
0x140079117  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007911e  mov     edx, 0AEh
0x140079123  call    WPP_SF_
0x140079128  mov     r9, [rsp+78h+arg_18]
0x140079130  test    r14, r14
0x140079133  jz      loc_14007942D
0x140079139  test    r9, r9
0x14007913c  jz      loc_14007942D
0x140079142  mov     r13, [rsp+78h+arg_20]
0x14007914a  test    r13, r13
0x14007914d  jz      loc_14007942D
0x140079153  test    rbp, rbp
0x140079156  jz      loc_14007942D
0x14007915c  mov     ecx, [rbp+50h]
0x14007915f  cmp     ecx, esi
0x140079161  ja      loc_14007942D
0x140079167  mov     edx, [rbp+54h]
0x14007916a  add     edx, ecx
0x14007916c  cmp     edx, ecx
0x14007916e  jb      loc_14007942D
0x140079174  cmp     edx, esi
0x140079176  ja      loc_14007942D
0x14007917c  mov     rcx, [r14+20h]; Lock
0x140079180  lea     rdx, [rsp+78h+LockState]; LockState
0x140079188  xor     r8d, r8d; Flags
0x14007918b  mov     [r9], rbx
0x14007918e  mov     rdi, rbx
0x140079191  mov     [r13+0], ebx
0x140079195  call    cs:__imp_NdisAcquireRWLockRead
0x14007919c  nop     dword ptr [rax+rax+00h]
0x1400791a1  xor     r9d, r9d; unsigned __int8 *
0x1400791a4  lea     r8, [rsp+78h+var_48]; unsigned int *
0x1400791a9  mov     rcx, r14; struct _WFD_ROLE *
0x1400791ac  lea     edx, [r9+8]; enum MANAGEMENT_FRAME_TYPE
0x1400791b0  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x1400791b5  mov     ebx, eax
0x1400791b7  test    eax, eax
0x1400791b9  jz      short loc_1400791D5
0x1400791bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400791c2  cmp     rcx, r15
0x1400791c5  jz      loc_1400793DF
0x1400791cb  mov     edx, 0B0h
0x1400791d0  jmp     loc_1400793CF
0x1400791d5  mov     r12d, [rsp+78h+var_48]
0x1400791da  test    r12d, r12d
0x1400791dd  jz      loc_1400793DF
0x1400791e3  lea     r15d, [r12+rsi]
0x1400791e7  cmp     r15d, esi
0x1400791ea  jnb     short loc_14007922A
0x1400791ec  mov     ebx, 0C0000095h
0x1400791f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400791f8  lea     r15, WPP_GLOBAL_Control
0x1400791ff  cmp     rcx, r15
0x140079202  jz      loc_1400793DF
0x140079208  mov     rcx, [rcx+18h]
0x14007920c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079213  mov     edx, 0B1h
0x140079218  mov     [rsp+78h+var_58], r12d
0x14007921d  mov     r9d, esi
0x140079220  call    WPP_SF_Dd
0x140079225  jmp     loc_1400793DF
0x14007922a  lea     eax, [r15+10h]
0x14007922e  cmp     eax, 10h
0x140079231  jb      loc_1400793B0
0x140079237  mov     ecx, 40h ; '@'
0x14007923c  mov     edi, 30327776h
0x140079241  cmp     eax, ecx
0x140079243  ja      short loc_14007924E
0x140079245  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007924c  jmp     short loc_14007927C
0x14007924e  cmp     eax, 100h
0x140079253  ja      short loc_14007925E
0x140079255  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007925c  jmp     short loc_14007927C
0x14007925e  cmp     eax, 400h
0x140079263  ja      short loc_14007926E
0x140079265  lea     rbx, Lookaside
0x14007926c  jmp     short loc_14007927C
0x14007926e  cmp     eax, 800h
0x140079273  ja      short loc_14007928D
0x140079275  lea     rbx, stru_1400B0180
0x14007927c  mov     rcx, rbx; Lookaside
0x14007927f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140079286  nop     dword ptr [rax+rax+00h]
0x14007928b  jmp     short loc_1400792A0
0x14007928d  xor     ebx, ebx
0x14007928f  mov     edx, eax
0x140079291  mov     r8d, edi
0x140079294  call    cs:__imp_ExAllocatePool2
0x14007929b  nop     dword ptr [rax+rax+00h]
0x1400792a0  test    rax, rax
0x1400792a3  jz      loc_1400793B0
0x1400792a9  mov     [rax+8], edi
0x1400792ac  xor     edx, edx; Val
0x1400792ae  lea     rdi, [rax+10h]
0x1400792b2  mov     r8d, r15d; Size
0x1400792b5  mov     rcx, rdi; void *
0x1400792b8  mov     [rax], rbx
0x1400792bb  call    memset
0x1400792c0  movups  xmm0, xmmword ptr [rbp+0]
0x1400792c4  lea     rbx, [rdi+58h]
0x1400792c8  movups  xmmword ptr [rdi], xmm0
0x1400792cb  movups  xmm1, xmmword ptr [rbp+10h]
0x1400792cf  movups  xmmword ptr [rdi+10h], xmm1
0x1400792d3  movups  xmm0, xmmword ptr [rbp+20h]
0x1400792d7  movups  xmmword ptr [rdi+20h], xmm0
0x1400792db  movups  xmm1, xmmword ptr [rbp+30h]
0x1400792df  movups  xmmword ptr [rdi+30h], xmm1
0x1400792e3  movups  xmm0, xmmword ptr [rbp+40h]
0x1400792e7  movups  xmmword ptr [rdi+40h], xmm0
0x1400792eb  movsd   xmm1, qword ptr [rbp+50h]
0x1400792f0  movsd   qword ptr [rdi+50h], xmm1
0x1400792f5  mov     dword ptr [rdi+50h], 58h ; 'X'
0x1400792fc  mov     ecx, [rbp+54h]
0x1400792ff  add     ecx, r12d
0x140079302  mov     [rdi+54h], ecx
0x140079305  mov     rcx, rbx; void *
0x140079308  mov     edx, [rbp+50h]
0x14007930b  mov     r8d, [rbp+54h]; Size
0x14007930f  add     rdx, rbp; Src
0x140079312  call    memmove
0x140079317  mov     r9d, [rbp+54h]
0x14007931b  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140079320  add     r9, rbx; unsigned __int8 *
0x140079323  mov     edx, 8; enum MANAGEMENT_FRAME_TYPE
0x140079328  mov     rcx, r14; struct _WFD_ROLE *
0x14007932b  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140079330  mov     ebx, eax
0x140079332  test    eax, eax
0x140079334  jz      short loc_140079354
0x140079336  mov     rcx, cs:WPP_GLOBAL_Control
0x14007933d  lea     r15, WPP_GLOBAL_Control
0x140079344  cmp     rcx, r15
0x140079347  jz      loc_1400793DF
0x14007934d  mov     edx, 0B3h
0x140079352  jmp     short loc_1400793CF
0x140079354  mov     rcx, cs:WPP_GLOBAL_Control
0x14007935b  lea     rax, WPP_GLOBAL_Control
0x140079362  cmp     rcx, rax
0x140079365  jz      short loc_140079396
0x140079367  cmp     byte ptr [rcx+29h], 3
0x14007936b  jb      short loc_140079396
0x14007936d  test    dword ptr [rcx+2Ch], 200000h
0x140079374  jz      short loc_140079396
0x140079376  mov     eax, [rdi+54h]
0x140079379  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079380  mov     r9d, [rdi+50h]
0x140079384  mov     edx, 0B4h
0x140079389  mov     rcx, [rcx+18h]
0x14007938d  mov     [rsp+78h+var_58], eax
0x140079391  call    WPP_SF_Dd
0x140079396  mov     rax, [rsp+78h+arg_18]
0x14007939e  mov     [r13+0], r15d
0x1400793a2  lea     r15, WPP_GLOBAL_Control
0x1400793a9  mov     [rax], rdi
0x1400793ac  xor     edi, edi
0x1400793ae  jmp     short loc_1400793DF
0x1400793b0  xor     edi, edi
0x1400793b2  mov     ebx, 0C000009Ah
0x1400793b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400793be  lea     r15, WPP_GLOBAL_Control
0x1400793c5  cmp     rcx, r15
0x1400793c8  jz      short loc_1400793DF
0x1400793ca  mov     edx, 0B2h
0x1400793cf  mov     rcx, [rcx+18h]
0x1400793d3  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x1400793da  call    WPP_SF_
0x1400793df  mov     rcx, [r14+20h]; Lock
0x1400793e3  lea     rdx, [rsp+78h+LockState]; LockState
0x1400793eb  call    cs:__imp_NdisReleaseRWLock
0x1400793f2  nop     dword ptr [rax+rax+00h]
0x1400793f7  test    rdi, rdi
0x1400793fa  jz      short loc_140079453
0x1400793fc  lea     rcx, [rdi-10h]; P
0x140079400  mov     rax, [rcx]
0x140079403  test    rax, rax
0x140079406  jz      short loc_14007941C
0x140079408  mov     rdx, rcx; Entry
0x14007940b  mov     rcx, rax; Lookaside
0x14007940e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079415  nop     dword ptr [rax+rax+00h]
0x14007941a  jmp     short loc_140079453
0x14007941c  mov     edx, [rcx+8]; Tag
0x14007941f  call    cs:__imp_ExFreePoolWithTag
0x140079426  nop     dword ptr [rax+rax+00h]
0x14007942b  jmp     short loc_140079453
0x14007942d  mov     ebx, 0C000000Dh
0x140079432  mov     rcx, cs:WPP_GLOBAL_Control
0x140079439  cmp     rcx, r15
0x14007943c  jz      short loc_140079477
0x14007943e  mov     rcx, [rcx+18h]
0x140079442  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079449  mov     edx, 0AFh
0x14007944e  call    WPP_SF_
0x140079453  mov     rcx, cs:WPP_GLOBAL_Control
0x14007945a  cmp     rcx, r15
0x14007945d  jz      short loc_140079477
0x14007945f  mov     rcx, [rcx+18h]
0x140079463  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007946a  mov     edx, 0B5h
0x14007946f  mov     r9d, ebx
0x140079472  call    WPP_SF_d
0x140079477  mov     eax, ebx
0x140079479  mov     rbx, [rsp+78h+arg_8]
0x140079481  add     rsp, 40h
0x140079485  pop     r15
0x140079487  pop     r14
0x140079489  pop     r13
0x14007948b  pop     r12
0x14007948d  pop     rdi
0x14007948e  pop     rsi
0x14007948f  pop     rbp
0x140079490  retn
```
