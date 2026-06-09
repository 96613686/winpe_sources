# WFDRoleAddCachedIEsToAssocParamIEsOidStructure(_WFD_ROLE *,DOT11_ASSOCIATION_PARAMS *,ulong,DOT11_ASSOCIATION_PARAMS * *,ulong *)

- ea: `0x140079e88`
- end: `0x14007a23b`
- name: `?WFDRoleAddCachedIEsToAssocParamIEsOidStructure@@YAKPEAU_WFD_ROLE@@PEAUDOT11_ASSOCIATION_PARAMS@@KPEAPEAU2@PEAK@Z`
- size: `947`
- prototype: `unsigned int __usercall@<eax>(struct _WFD_ROLE *@<rcx>, struct DOT11_ASSOCIATION_PARAMS *@<rdx>, unsigned int@<r8d>, struct DOT11_ASSOCIATION_PARAMS **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14006c270`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x14006f2bc`
- `0x140079e88`
- `0x14007b8bc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a08a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a08a`
- `ntoskrnl!ExAllocatePool2` at `0x14007a09f`
- `ntoskrnl!ExAllocatePool2` at `0x14007a09f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a024`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007a024`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1c8`
- `NDIS!NdisReleaseRWLock` at `0x140079ff9`
- `NDIS!NdisReleaseRWLock` at `0x140079ff9`
- `NDIS!NdisAcquireRWLockRead` at `0x140079f51`
- `NDIS!NdisAcquireRWLockRead` at `0x140079f51`

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
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r15d
  unsigned int v17; // r13d
  unsigned int v18; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  struct DOT11_ASSOCIATION_PARAMS **v21; // rax
  unsigned int v23[18]; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+8h] BYREF
  struct DOT11_ASSOCIATION_PARAMS **v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  v23[0] = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
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
              CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 3u, v23, 0);
              if ( CachedFrameIEs )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_18;
                v15 = 160;
                goto LABEL_13;
              }
              v16 = v23[0];
              if ( !v23[0] )
                goto LABEL_18;
              v17 = v23[0] + a3;
              if ( v23[0] + a3 < a3 )
              {
                CachedFrameIEs = -1073741675;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    161,
                    WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
                    a3,
                    v23[0]);
                goto LABEL_18;
              }
              v18 = v17 + 16;
              if ( v17 >= 0xFFFFFFF0 )
                goto LABEL_41;
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
LABEL_32:
                      if ( Pool2 )
                      {
                        Pool2[2] = 808613750;
                        v12 = (struct DOT11_ASSOCIATION_PARAMS *)(Pool2 + 4);
                        *(_QWORD *)Pool2 = p_WaitListHead;
                        memset(Pool2 + 4, 0, v17);
                        *(_OWORD *)&v12->Header.Type = *(_OWORD *)&a2->Header.Type;
                        v12->uAssocRequestIEsLength = a2->uAssocRequestIEsLength;
                        v12->uAssocRequestIEsOffset = 20;
                        v12->uAssocRequestIEsLength = v16 + a2->uAssocRequestIEsLength;
                        memmove(&v12[1], &a2->Header.Type + a2->uAssocRequestIEsOffset, a2->uAssocRequestIEsLength);
                        CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                           a1,
                                           3u,
                                           v23,
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
                          v21 = v25;
                          *v8 = v17;
                          *v21 = v12;
                          v12 = 0;
                          goto LABEL_18;
                        }
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          v15 = 163;
LABEL_13:
                          WPP_SF_(v14->AttachedDevice, v15, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
                          goto LABEL_18;
                        }
                        goto LABEL_18;
                      }
LABEL_41:
                      v12 = 0;
                      CachedFrameIEs = -1073741670;
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        v15 = 162;
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
0x140079e88  mov     r11, rsp
0x140079e8b  mov     [r11+10h], rbx
0x140079e8f  mov     [r11+20h], r9
0x140079e93  push    rbp
0x140079e94  push    rsi
0x140079e95  push    rdi
0x140079e96  push    r12
0x140079e98  push    r13
0x140079e9a  push    r14
0x140079e9c  push    r15
0x140079e9e  sub     rsp, 40h
0x140079ea2  xor     ebx, ebx
0x140079ea4  mov     esi, r8d
0x140079ea7  xor     eax, eax
0x140079ea9  mov     [rsp+78h+var_48], ebx
0x140079ead  mov     [r11+9], ax
0x140079eb2  mov     rbp, rdx
0x140079eb5  mov     r14, rcx
0x140079eb8  mov     [r11+8], bl
0x140079ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ec3  lea     r15, WPP_GLOBAL_Control
0x140079eca  cmp     rcx, r15
0x140079ecd  jz      short loc_140079EEC
0x140079ecf  mov     rcx, [rcx+18h]
0x140079ed3  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079eda  mov     edx, 9Eh
0x140079edf  call    WPP_SF_
0x140079ee4  mov     r9, [rsp+78h+arg_18]
0x140079eec  test    r14, r14
0x140079eef  jz      loc_14007A1D6
0x140079ef5  test    r9, r9
0x140079ef8  jz      loc_14007A1D6
0x140079efe  mov     r12, [rsp+78h+arg_20]
0x140079f06  test    r12, r12
0x140079f09  jz      loc_14007A1D6
0x140079f0f  test    rbp, rbp
0x140079f12  jz      loc_14007A1D6
0x140079f18  mov     ecx, [rbp+0Ch]
0x140079f1b  cmp     ecx, esi
0x140079f1d  ja      loc_14007A1D6
0x140079f23  mov     edx, [rbp+10h]
0x140079f26  add     edx, ecx
0x140079f28  cmp     edx, ecx
0x140079f2a  jb      loc_14007A1D6
0x140079f30  cmp     edx, esi
0x140079f32  ja      loc_14007A1D6
0x140079f38  mov     rcx, [r14+20h]; Lock
0x140079f3c  lea     rdx, [rsp+78h+LockState]; LockState
0x140079f44  xor     r8d, r8d; Flags
0x140079f47  mov     [r9], rbx
0x140079f4a  mov     rdi, rbx
0x140079f4d  mov     [r12], ebx
0x140079f51  call    cs:__imp_NdisAcquireRWLockRead
0x140079f58  nop     dword ptr [rax+rax+00h]
0x140079f5d  xor     r9d, r9d; unsigned __int8 *
0x140079f60  lea     r8, [rsp+78h+var_48]; unsigned int *
0x140079f65  mov     rcx, r14; struct _WFD_ROLE *
0x140079f68  lea     edx, [r9+3]; enum MANAGEMENT_FRAME_TYPE
0x140079f6c  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140079f71  mov     ebx, eax
0x140079f73  test    eax, eax
0x140079f75  jz      short loc_140079F9A
0x140079f77  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f7e  cmp     rcx, r15
0x140079f81  jz      short loc_140079FED
0x140079f83  mov     edx, 0A0h
0x140079f88  mov     rcx, [rcx+18h]
0x140079f8c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079f93  call    WPP_SF_
0x140079f98  jmp     short loc_140079FED
0x140079f9a  mov     r15d, [rsp+78h+var_48]
0x140079f9f  test    r15d, r15d
0x140079fa2  jz      short loc_140079FE6
0x140079fa4  lea     r13d, [r15+rsi]
0x140079fa8  cmp     r13d, esi
0x140079fab  jnb     loc_14007A035
0x140079fb1  mov     ebx, 0C0000095h
0x140079fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140079fbd  lea     rax, WPP_GLOBAL_Control
0x140079fc4  cmp     rcx, rax
0x140079fc7  jz      short loc_140079FE6
0x140079fc9  mov     rcx, [rcx+18h]
0x140079fcd  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x140079fd4  mov     edx, 0A1h
0x140079fd9  mov     [rsp+78h+var_58], r15d
0x140079fde  mov     r9d, esi
0x140079fe1  call    WPP_SF_Dd
0x140079fe6  lea     r15, WPP_GLOBAL_Control
0x140079fed  mov     rcx, [r14+20h]; Lock
0x140079ff1  lea     rdx, [rsp+78h+LockState]; LockState
0x140079ff9  call    cs:__imp_NdisReleaseRWLock
0x14007a000  nop     dword ptr [rax+rax+00h]
0x14007a005  test    rdi, rdi
0x14007a008  jz      loc_14007A1FC
0x14007a00e  lea     rcx, [rdi-10h]; P
0x14007a012  mov     rax, [rcx]
0x14007a015  test    rax, rax
0x14007a018  jz      loc_14007A1C5
0x14007a01e  mov     rdx, rcx; Entry
0x14007a021  mov     rcx, rax; Lookaside
0x14007a024  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007a02b  nop     dword ptr [rax+rax+00h]
0x14007a030  jmp     loc_14007A1FC
0x14007a035  lea     eax, [r13+10h]
0x14007a039  cmp     eax, 10h
0x14007a03c  jb      loc_14007A19D
0x14007a042  mov     ecx, 40h ; '@'
0x14007a047  mov     edi, 30327776h
0x14007a04c  cmp     eax, ecx
0x14007a04e  ja      short loc_14007A059
0x14007a050  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007a057  jmp     short loc_14007A087
0x14007a059  cmp     eax, 100h
0x14007a05e  ja      short loc_14007A069
0x14007a060  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007a067  jmp     short loc_14007A087
0x14007a069  cmp     eax, 400h
0x14007a06e  ja      short loc_14007A079
0x14007a070  lea     rbx, Lookaside
0x14007a077  jmp     short loc_14007A087
0x14007a079  cmp     eax, 800h
0x14007a07e  ja      short loc_14007A098
0x14007a080  lea     rbx, stru_1400B31C0
0x14007a087  mov     rcx, rbx; Lookaside
0x14007a08a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007a091  nop     dword ptr [rax+rax+00h]
0x14007a096  jmp     short loc_14007A0AB
0x14007a098  xor     ebx, ebx
0x14007a09a  mov     edx, eax
0x14007a09c  mov     r8d, edi
0x14007a09f  call    cs:__imp_ExAllocatePool2
0x14007a0a6  nop     dword ptr [rax+rax+00h]
0x14007a0ab  test    rax, rax
0x14007a0ae  jz      loc_14007A19D
0x14007a0b4  mov     [rax+8], edi
0x14007a0b7  xor     edx, edx; Val
0x14007a0b9  lea     rdi, [rax+10h]
0x14007a0bd  mov     r8d, r13d; Size
0x14007a0c0  mov     rcx, rdi; void *
0x14007a0c3  mov     [rax], rbx
0x14007a0c6  call    memset
0x14007a0cb  movups  xmm0, xmmword ptr [rbp+0]
0x14007a0cf  lea     rbx, [rdi+14h]
0x14007a0d3  movups  xmmword ptr [rdi], xmm0
0x14007a0d6  mov     eax, [rbp+10h]
0x14007a0d9  mov     [rdi+10h], eax
0x14007a0dc  mov     dword ptr [rdi+0Ch], 14h
0x14007a0e3  mov     ecx, [rbp+10h]
0x14007a0e6  add     ecx, r15d
0x14007a0e9  mov     [rdi+10h], ecx
0x14007a0ec  mov     rcx, rbx; void *
0x14007a0ef  mov     edx, [rbp+0Ch]
0x14007a0f2  mov     r8d, [rbp+10h]; Size
0x14007a0f6  add     rdx, rbp; Src
0x14007a0f9  call    memmove
0x14007a0fe  mov     r9d, [rbp+10h]
0x14007a102  lea     r8, [rsp+78h+var_48]; unsigned int *
0x14007a107  add     r9, rbx; unsigned __int8 *
0x14007a10a  mov     edx, 3; enum MANAGEMENT_FRAME_TYPE
0x14007a10f  mov     rcx, r14; struct _WFD_ROLE *
0x14007a112  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14007a117  mov     ebx, eax
0x14007a119  test    eax, eax
0x14007a11b  jz      short loc_14007A13E
0x14007a11d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a124  lea     r15, WPP_GLOBAL_Control
0x14007a12b  cmp     rcx, r15
0x14007a12e  jz      loc_140079FED
0x14007a134  mov     edx, 0A3h
0x14007a139  jmp     loc_140079F88
0x14007a13e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a145  lea     r15, WPP_GLOBAL_Control
0x14007a14c  cmp     rcx, r15
0x14007a14f  jz      short loc_14007A187
0x14007a151  cmp     byte ptr [rcx+29h], 3
0x14007a155  jb      short loc_14007A187
0x14007a157  test    dword ptr [rcx+2Ch], 200000h
0x14007a15e  jz      short loc_14007A187
0x14007a160  mov     eax, [rdi+10h]
0x14007a163  lea     r9, [rdi+4]
0x14007a167  mov     rcx, [rcx+18h]
0x14007a16b  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a172  mov     [rsp+78h+var_50], eax
0x14007a176  mov     edx, 0A4h
0x14007a17b  mov     eax, [rdi+0Ch]
0x14007a17e  mov     [rsp+78h+var_58], eax
0x14007a182  call    WPP_SF__MAC_DD
0x14007a187  mov     rax, [rsp+78h+arg_18]
0x14007a18f  mov     [r12], r13d
0x14007a193  mov     [rax], rdi
0x14007a196  xor     edi, edi
0x14007a198  jmp     loc_140079FED
0x14007a19d  xor     edi, edi
0x14007a19f  mov     ebx, 0C000009Ah
0x14007a1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a1ab  lea     r15, WPP_GLOBAL_Control
0x14007a1b2  cmp     rcx, r15
0x14007a1b5  jz      loc_140079FED
0x14007a1bb  mov     edx, 0A2h
0x14007a1c0  jmp     loc_140079F88
0x14007a1c5  mov     edx, [rcx+8]; Tag
0x14007a1c8  call    cs:__imp_ExFreePoolWithTag
0x14007a1cf  nop     dword ptr [rax+rax+00h]
0x14007a1d4  jmp     short loc_14007A1FC
0x14007a1d6  mov     ebx, 0C000000Dh
0x14007a1db  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a1e2  cmp     rcx, r15
0x14007a1e5  jz      short loc_14007A220
0x14007a1e7  mov     rcx, [rcx+18h]
0x14007a1eb  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a1f2  mov     edx, 9Fh
0x14007a1f7  call    WPP_SF_
0x14007a1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a203  cmp     rcx, r15
0x14007a206  jz      short loc_14007A220
0x14007a208  mov     rcx, [rcx+18h]
0x14007a20c  lea     r8, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007a213  mov     edx, 0A5h
0x14007a218  mov     r9d, ebx
0x14007a21b  call    WPP_SF_d
0x14007a220  mov     eax, ebx
0x14007a222  mov     rbx, [rsp+78h+arg_8]
0x14007a22a  add     rsp, 40h
0x14007a22e  pop     r15
0x14007a230  pop     r14
0x14007a232  pop     r13
0x14007a234  pop     r12
0x14007a236  pop     rdi
0x14007a237  pop     rsi
0x14007a238  pop     rbp
0x14007a239  retn
```
