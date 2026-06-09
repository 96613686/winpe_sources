# WFDDeviceSendInvitationResponse(_WFD_ROLE *,_ADAPT *,uchar,void *,uchar (*)[6],uchar (*)[6])

- ea: `0x14008a244`
- end: `0x14008a571`
- name: `?WFDDeviceSendInvitationResponse@@YAHPEAU_WFD_ROLE@@PEAU_ADAPT@@EPEAXPEAY05E3@Z`
- size: `813`
- prototype: `__int64 __usercall@<rax>(struct _WFD_ROLE *@<rcx>, struct _ADAPT *@<rdx>, unsigned __int8@<r8b>, void *@<r9>, unsigned __int8 (*)[6], unsigned __int8 (*)[6])`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14007f67c`

## callees

- `0x14000d21c`
- `0x140020f20`
- `0x140030b7c`
- `0x140031038`
- `0x14007b8bc`
- `0x14008a244`
- `0x14008cd40`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a36c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a36c`
- `ntoskrnl!ExAllocatePool2` at `0x14008a37f`
- `ntoskrnl!ExAllocatePool2` at `0x14008a37f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a539`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a539`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a54a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a54a`
- `NDIS!NdisReleaseRWLock` at `0x14008a440`
- `NDIS!NdisReleaseRWLock` at `0x14008a461`
- `NDIS!NdisReleaseRWLock` at `0x14008a440`
- `NDIS!NdisReleaseRWLock` at `0x14008a461`
- `NDIS!NdisAcquireRWLockRead` at `0x14008a284`
- `NDIS!NdisAcquireRWLockRead` at `0x14008a284`

## pseudocode

```c
__int64 __fastcall WFDDeviceSendInvitationResponse(
        struct _WFD_ROLE *a1,
        struct _ADAPT *a2,
        char a3,
        void *a4,
        unsigned __int8 (*a5)[6],
        unsigned __int8 (*a6)[6])
{
  struct _NDIS_RW_LOCK_EX *pRWLock; // rcx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  unsigned int CachedFrameIEs; // edi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned int v14; // r14d
  unsigned int v15; // eax
  char *Pool2; // rax
  char v17; // al
  char v18; // r15
  unsigned __int8 *v19; // rcx
  unsigned __int8 *v20; // rcx
  unsigned int v21; // ecx
  unsigned int v23[4]; // [rsp+40h] [rbp-10h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+40h] BYREF
  struct _ADAPT *v25; // [rsp+98h] [rbp+48h]
  char v26; // [rsp+A0h] [rbp+50h]

  v26 = a3;
  v25 = a2;
  pRWLock = a1->pRWLock;
  p_DeviceQueue = 0;
  v23[0] = 0;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockRead(pRWLock, &LockState, 0);
  CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 9u, v23, 0);
  if ( CachedFrameIEs )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v12 = 231;
LABEL_25:
      WPP_SF_(v11->AttachedDevice, v12, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v13 = v23[0];
  v14 = v23[0] + 56;
  if ( v23[0] + 56 < 0x38 )
  {
    CachedFrameIEs = -1073676267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 232, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 56, v23[0]);
    goto LABEL_26;
  }
  v15 = v23[0] + 72;
  if ( v14 >= 0xFFFFFFF0 )
  {
LABEL_19:
    CachedFrameIEs = -1073741670;
    p_DeviceQueue = 0;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v12 = 233;
      goto LABEL_25;
    }
LABEL_26:
    NdisReleaseRWLock(a1->pRWLock, &LockState);
    goto LABEL_38;
  }
  if ( v15 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v15 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v15 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v15 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_16;
  }
  Pool2 = (char *)ExAllocatePool2(64, v15, 808679286);
LABEL_18:
  if ( !Pool2 )
    goto LABEL_19;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 808679286;
  memset(Pool2 + 16, 0, v14);
  v17 = v26;
  v18 = 1;
  LODWORD(p_DeviceQueue->L.ListHead.Alignment) = 3670400;
  *((_BYTE *)&p_DeviceQueue->L.SingleListHead + 10) = v17;
  *(_QWORD *)&p_DeviceQueue->L.Depth = a4;
  LOBYTE(p_DeviceQueue->L.TotalFrees) = 0;
  p_DeviceQueue->L.AllocateMisses = 1000;
  if ( v13 )
  {
    p_DeviceQueue->L.Size = 56;
    LODWORD(p_DeviceQueue->L.AllocateEx) = v13;
    CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 9u, v23, (unsigned __int8 *)&p_DeviceQueue->L.56);
    if ( CachedFrameIEs )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v12 = 234;
        goto LABEL_25;
      }
      goto LABEL_26;
    }
  }
  else
  {
    *(_QWORD *)&p_DeviceQueue->L.Size = 0;
  }
  NdisReleaseRWLock(a1->pRWLock, &LockState);
  v19 = (unsigned __int8 *)a6;
  if ( a6 )
  {
    *(unsigned int *)((char *)&p_DeviceQueue->L.TotalFrees + 3) = *(_DWORD *)a6;
    *(_WORD *)((char *)&p_DeviceQueue->L.FreeHits + 3) = *((_WORD *)v19 + 2);
  }
  else
  {
    v18 = 0;
  }
  v20 = (unsigned __int8 *)a5;
  BYTE1(p_DeviceQueue->L.Type) = v18;
  HIDWORD(p_DeviceQueue->L.SingleListHead.Next) = *(_DWORD *)v20;
  *((_WORD *)&p_DeviceQueue->L.SingleListHead + 4) = *((_WORD *)v20 + 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF__MAC_DDDD(WPP_GLOBAL_Control->AttachedDevice, 235);
  }
  v21 = NwifiSetDirectOidRequestAsync(v25, 0xE05010Eu, p_DeviceQueue, v14);
  if ( v21 == 1076035585 )
    v21 = 0;
  v23[0] = v21;
  MapPendingDirectOidStatus((int *)v23);
  CachedFrameIEs = v23[0];
LABEL_38:
  if ( p_DeviceQueue )
  {
    if ( *(_QWORD *)&p_DeviceQueue[-1].L.Future[6] )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)&p_DeviceQueue[-1].L.Future[6],
        &p_DeviceQueue[-1].L.Future[6]);
    else
      ExFreePoolWithTag(&p_DeviceQueue[-1].L.Future[6], p_DeviceQueue[-1].L.Future[8]);
  }
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x14008a244  mov     [rsp-38h+arg_18], rbx
0x14008a249  mov     [rsp-38h+arg_10], r8b
0x14008a24e  mov     [rsp-38h+arg_8], rdx
0x14008a253  push    rbp
0x14008a254  push    rsi
0x14008a255  push    rdi
0x14008a256  push    r12
0x14008a258  push    r13
0x14008a25a  push    r14
0x14008a25c  push    r15
0x14008a25e  mov     rbp, rsp
0x14008a261  sub     rsp, 50h
0x14008a265  mov     r13, rcx
0x14008a268  lea     rdx, [rbp+LockState]; LockState
0x14008a26c  mov     rcx, [rcx+20h]; Lock
0x14008a270  xor     ebx, ebx
0x14008a272  xor     eax, eax
0x14008a274  mov     [rbp+var_10], ebx
0x14008a277  xor     r8d, r8d; Flags
0x14008a27a  mov     [rbp+LockState.OldIrql], bl
0x14008a27d  mov     word ptr [rbp+LockState.LockState], ax
0x14008a281  mov     r12, r9
0x14008a284  call    cs:__imp_NdisAcquireRWLockRead
0x14008a28b  nop     dword ptr [rax+rax+00h]
0x14008a290  xor     r9d, r9d; unsigned __int8 *
0x14008a293  lea     r8, [rbp+var_10]; unsigned int *
0x14008a297  lea     edx, [rbx+9]; enum MANAGEMENT_FRAME_TYPE
0x14008a29a  mov     rcx, r13; struct _WFD_ROLE *
0x14008a29d  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14008a2a2  mov     edi, eax
0x14008a2a4  test    eax, eax
0x14008a2a6  jz      short loc_14008A2C9
0x14008a2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a2af  lea     rax, WPP_GLOBAL_Control
0x14008a2b6  cmp     rcx, rax
0x14008a2b9  jz      loc_14008A438
0x14008a2bf  mov     edx, 0E7h
0x14008a2c4  jmp     loc_14008A428
0x14008a2c9  mov     esi, [rbp+var_10]
0x14008a2cc  mov     edi, 38h ; '8'
0x14008a2d1  lea     r14d, [rsi+38h]
0x14008a2d5  cmp     r14d, edi
0x14008a2d8  jnb     short loc_14008A31A
0x14008a2da  mov     edi, 0C0010015h
0x14008a2df  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a2e6  lea     rax, WPP_GLOBAL_Control
0x14008a2ed  cmp     rcx, rax
0x14008a2f0  jz      loc_14008A438
0x14008a2f6  mov     rcx, [rcx+18h]
0x14008a2fa  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a301  mov     edx, 0E8h
0x14008a306  mov     [rsp+50h+var_30], esi
0x14008a30a  mov     r9d, 38h ; '8'
0x14008a310  call    WPP_SF_Dd
0x14008a315  jmp     loc_14008A438
0x14008a31a  lea     eax, [r14+10h]
0x14008a31e  cmp     eax, 10h
0x14008a321  jb      short loc_14008A390
0x14008a323  mov     ecx, 40h ; '@'
0x14008a328  mov     r15d, 30337776h
0x14008a32e  cmp     eax, ecx
0x14008a330  ja      short loc_14008A33B
0x14008a332  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14008a339  jmp     short loc_14008A369
0x14008a33b  cmp     eax, 100h
0x14008a340  ja      short loc_14008A34B
0x14008a342  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008a349  jmp     short loc_14008A369
0x14008a34b  cmp     eax, 400h
0x14008a350  ja      short loc_14008A35B
0x14008a352  lea     rbx, Lookaside
0x14008a359  jmp     short loc_14008A369
0x14008a35b  cmp     eax, 800h
0x14008a360  ja      short loc_14008A37A
0x14008a362  lea     rbx, stru_1400B31C0
0x14008a369  mov     rcx, rbx; Lookaside
0x14008a36c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a373  nop     dword ptr [rax+rax+00h]
0x14008a378  jmp     short loc_14008A38B
0x14008a37a  mov     edx, eax
0x14008a37c  mov     r8d, r15d
0x14008a37f  call    cs:__imp_ExAllocatePool2
0x14008a386  nop     dword ptr [rax+rax+00h]
0x14008a38b  test    rax, rax
0x14008a38e  jnz     short loc_14008A3B5
0x14008a390  mov     edi, 0C000009Ah
0x14008a395  xor     ebx, ebx
0x14008a397  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a39e  lea     rax, WPP_GLOBAL_Control
0x14008a3a5  cmp     rcx, rax
0x14008a3a8  jz      loc_14008A438
0x14008a3ae  mov     edx, 0E9h
0x14008a3b3  jmp     short loc_14008A428
0x14008a3b5  mov     [rax], rbx
0x14008a3b8  xor     edx, edx; Val
0x14008a3ba  lea     rbx, [rax+10h]
0x14008a3be  mov     r8d, r14d; Size
0x14008a3c1  mov     rcx, rbx; void *
0x14008a3c4  mov     [rax+8], r15d
0x14008a3c8  call    memset
0x14008a3cd  mov     al, [rbp+arg_10]
0x14008a3d0  mov     r15b, 1
0x14008a3d3  mov     dword ptr [rbx], 380180h
0x14008a3d9  mov     [rbx+0Ah], al
0x14008a3dc  mov     [rbx+10h], r12
0x14008a3e0  mov     byte ptr [rbx+1Ch], 0
0x14008a3e4  mov     dword ptr [rbx+18h], 3E8h
0x14008a3eb  test    esi, esi
0x14008a3ed  jz      short loc_14008A451
0x14008a3ef  mov     [rbx+2Ch], edi
0x14008a3f2  lea     r9, [rbx+38h]; unsigned __int8 *
0x14008a3f6  lea     r8, [rbp+var_10]; unsigned int *
0x14008a3fa  mov     [rbx+30h], esi
0x14008a3fd  mov     edx, 9; enum MANAGEMENT_FRAME_TYPE
0x14008a402  mov     rcx, r13; struct _WFD_ROLE *
0x14008a405  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14008a40a  mov     edi, eax
0x14008a40c  test    eax, eax
0x14008a40e  jz      short loc_14008A459
0x14008a410  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a417  lea     rax, WPP_GLOBAL_Control
0x14008a41e  cmp     rcx, rax
0x14008a421  jz      short loc_14008A438
0x14008a423  mov     edx, 0EAh
0x14008a428  mov     rcx, [rcx+18h]
0x14008a42c  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a433  call    WPP_SF_
0x14008a438  mov     rcx, [r13+20h]; Lock
0x14008a43c  lea     rdx, [rbp+LockState]; LockState
0x14008a440  call    cs:__imp_NdisReleaseRWLock
0x14008a447  nop     dword ptr [rax+rax+00h]
0x14008a44c  jmp     loc_14008A522
0x14008a451  mov     qword ptr [rbx+2Ch], 0
0x14008a459  mov     rcx, [r13+20h]; Lock
0x14008a45d  lea     rdx, [rbp+LockState]; LockState
0x14008a461  call    cs:__imp_NdisReleaseRWLock
0x14008a468  nop     dword ptr [rax+rax+00h]
0x14008a46d  mov     rcx, [rbp+arg_28]
0x14008a471  test    rcx, rcx
0x14008a474  jz      short loc_14008A485
0x14008a476  mov     eax, [rcx]
0x14008a478  mov     [rbx+1Fh], eax
0x14008a47b  movzx   eax, word ptr [rcx+4]
0x14008a47f  mov     [rbx+23h], ax
0x14008a483  jmp     short loc_14008A488
0x14008a485  xor     r15b, r15b
0x14008a488  mov     rcx, [rbp+arg_20]
0x14008a48c  lea     r9, [rbx+4]
0x14008a490  mov     [rbx+25h], r15b
0x14008a494  mov     eax, [rcx]
0x14008a496  mov     [r9], eax
0x14008a499  movzx   eax, word ptr [rcx+4]
0x14008a49d  mov     [r9+4], ax
0x14008a4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a4a9  lea     rax, WPP_GLOBAL_Control
0x14008a4b0  cmp     rcx, rax
0x14008a4b3  jz      short loc_14008A4F2
0x14008a4b5  cmp     byte ptr [rcx+29h], 3
0x14008a4b9  jb      short loc_14008A4F2
0x14008a4bb  test    dword ptr [rcx+2Ch], 200000h
0x14008a4c2  jz      short loc_14008A4F2
0x14008a4c4  movzx   eax, byte ptr [rbx+1Ch]
0x14008a4c8  mov     edx, 0EBh
0x14008a4cd  movzx   r8d, byte ptr [rbx+0Ah]
0x14008a4d2  mov     rcx, [rcx+18h]
0x14008a4d6  mov     [rsp+50h+var_18], eax
0x14008a4da  mov     eax, [rbx+30h]
0x14008a4dd  mov     [rsp+50h+var_20], eax
0x14008a4e1  mov     eax, [rbx+2Ch]
0x14008a4e4  mov     [rsp+50h+var_28], eax
0x14008a4e8  mov     [rsp+50h+var_30], r8d
0x14008a4ed  call    WPP_SF__MAC_DDDD
0x14008a4f2  mov     rcx, [rbp+arg_8]; struct _ADAPT *
0x14008a4f6  mov     r9d, r14d; unsigned int
0x14008a4f9  mov     r8, rbx; void *
0x14008a4fc  mov     edx, 0E05010Eh; unsigned int
0x14008a501  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x14008a506  mov     ecx, eax
0x14008a508  xor     eax, eax
0x14008a50a  cmp     ecx, 40230001h
0x14008a510  cmovz   ecx, eax
0x14008a513  mov     [rbp+var_10], ecx
0x14008a516  lea     rcx, [rbp+var_10]; int *
0x14008a51a  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x14008a51f  mov     edi, [rbp+var_10]
0x14008a522  test    rbx, rbx
0x14008a525  jz      short loc_14008A556
0x14008a527  lea     rcx, [rbx-10h]; P
0x14008a52b  mov     rax, [rcx]
0x14008a52e  test    rax, rax
0x14008a531  jz      short loc_14008A547
0x14008a533  mov     rdx, rcx; Entry
0x14008a536  mov     rcx, rax; Lookaside
0x14008a539  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a540  nop     dword ptr [rax+rax+00h]
0x14008a545  jmp     short loc_14008A556
0x14008a547  mov     edx, [rcx+8]; Tag
0x14008a54a  call    cs:__imp_ExFreePoolWithTag
0x14008a551  nop     dword ptr [rax+rax+00h]
0x14008a556  mov     rbx, [rsp+50h+arg_18]
0x14008a55e  mov     eax, edi
0x14008a560  add     rsp, 50h
0x14008a564  pop     r15
0x14008a566  pop     r14
0x14008a568  pop     r13
0x14008a56a  pop     r12
0x14008a56c  pop     rdi
0x14008a56d  pop     rsi
0x14008a56e  pop     rbp
0x14008a56f  retn
```
