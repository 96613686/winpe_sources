# WFDDeviceSendInvitationResponse(_WFD_ROLE *,_ADAPT *,uchar,void *,uchar (*)[6],uchar (*)[6])

- ea: `0x140088a14`
- end: `0x140088d41`
- name: `?WFDDeviceSendInvitationResponse@@YAHPEAU_WFD_ROLE@@PEAU_ADAPT@@EPEAXPEAY05E3@Z`
- size: `813`
- prototype: `__int64 __usercall@<rax>(struct _WFD_ROLE *@<rcx>, struct _ADAPT *@<rdx>, unsigned __int8@<r8b>, void *@<r9>, unsigned __int8 (*)[6], unsigned __int8 (*)[6])`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14007de4c`

## callees

- `0x14000d22c`
- `0x140020f20`
- `0x1400308ec`
- `0x140030da8`
- `0x14007a08c`
- `0x140088a14`
- `0x14008b510`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088b3c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088b3c`
- `ntoskrnl!ExAllocatePool2` at `0x140088b4f`
- `ntoskrnl!ExAllocatePool2` at `0x140088b4f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d09`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140088d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088d1a`
- `NDIS!NdisReleaseRWLock` at `0x140088c10`
- `NDIS!NdisReleaseRWLock` at `0x140088c31`
- `NDIS!NdisReleaseRWLock` at `0x140088c10`
- `NDIS!NdisReleaseRWLock` at `0x140088c31`
- `NDIS!NdisAcquireRWLockRead` at `0x140088a54`
- `NDIS!NdisAcquireRWLockRead` at `0x140088a54`

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
  __int64 v11; // r9
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // esi
  unsigned int v15; // r14d
  unsigned int v16; // eax
  char *Pool2; // rax
  char v18; // al
  char v19; // r15
  unsigned __int8 *v20; // rcx
  unsigned __int8 *v21; // rcx
  unsigned int v22; // ecx
  unsigned int v24[4]; // [rsp+40h] [rbp-10h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+40h] BYREF
  struct _ADAPT *v26; // [rsp+98h] [rbp+48h]
  char v27; // [rsp+A0h] [rbp+50h]

  v27 = a3;
  v26 = a2;
  pRWLock = a1->pRWLock;
  p_DeviceQueue = 0;
  v24[0] = 0;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  NdisAcquireRWLockRead(pRWLock, &LockState, 0);
  CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 9u, v24, 0);
  if ( CachedFrameIEs )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v13 = 231;
LABEL_25:
      WPP_SF_(v12->AttachedDevice, v13, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v14 = v24[0];
  v15 = v24[0] + 56;
  if ( v24[0] + 56 < 0x38 )
  {
    CachedFrameIEs = -1073676267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 232, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 56, v24[0]);
    goto LABEL_26;
  }
  v16 = v24[0] + 72;
  if ( v15 >= 0xFFFFFFF0 )
  {
LABEL_19:
    CachedFrameIEs = -1073741670;
    p_DeviceQueue = 0;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v13 = 233;
      goto LABEL_25;
    }
LABEL_26:
    NdisReleaseRWLock(a1->pRWLock, &LockState);
    goto LABEL_38;
  }
  if ( v16 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v16 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v16 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v16 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_16;
  }
  Pool2 = (char *)ExAllocatePool2(64, v16, 808679286, v11);
LABEL_18:
  if ( !Pool2 )
    goto LABEL_19;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 808679286;
  memset(Pool2 + 16, 0, v15);
  v18 = v27;
  v19 = 1;
  LODWORD(p_DeviceQueue->L.ListHead.Alignment) = 3670400;
  *((_BYTE *)&p_DeviceQueue->L.SingleListHead + 10) = v18;
  *(_QWORD *)&p_DeviceQueue->L.Depth = a4;
  LOBYTE(p_DeviceQueue->L.TotalFrees) = 0;
  p_DeviceQueue->L.AllocateMisses = 1000;
  if ( v14 )
  {
    p_DeviceQueue->L.Size = 56;
    LODWORD(p_DeviceQueue->L.AllocateEx) = v14;
    CachedFrameIEs = WFDRoleGetCachedFrameIEs(a1, 9u, v24, (unsigned __int8 *)&p_DeviceQueue->L.56);
    if ( CachedFrameIEs )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v13 = 234;
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
  v20 = (unsigned __int8 *)a6;
  if ( a6 )
  {
    *(unsigned int *)((char *)&p_DeviceQueue->L.TotalFrees + 3) = *(_DWORD *)a6;
    *(_WORD *)((char *)&p_DeviceQueue->L.FreeHits + 3) = *((_WORD *)v20 + 2);
  }
  else
  {
    v19 = 0;
  }
  v21 = (unsigned __int8 *)a5;
  BYTE1(p_DeviceQueue->L.Type) = v19;
  HIDWORD(p_DeviceQueue->L.SingleListHead.Next) = *(_DWORD *)v21;
  *((_WORD *)&p_DeviceQueue->L.SingleListHead + 4) = *((_WORD *)v21 + 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
  {
    WPP_SF__MAC_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      235,
      *((unsigned __int8 *)&p_DeviceQueue->L.SingleListHead + 10),
      (char *)&p_DeviceQueue->L.SingleListHead.Next + 4,
      *((unsigned __int8 *)&p_DeviceQueue->L.SingleListHead + 10),
      p_DeviceQueue->L.Size,
      p_DeviceQueue->L.AllocateEx,
      LOBYTE(p_DeviceQueue->L.TotalFrees));
  }
  v22 = NwifiSetDirectOidRequestAsync(v26, 235208974, p_DeviceQueue, v15);
  if ( v22 == 1076035585 )
    v22 = 0;
  v24[0] = v22;
  MapPendingDirectOidStatus((int *)v24);
  CachedFrameIEs = v24[0];
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
0x140088a14  mov     [rsp-38h+arg_18], rbx
0x140088a19  mov     [rsp-38h+arg_10], r8b
0x140088a1e  mov     [rsp-38h+arg_8], rdx
0x140088a23  push    rbp
0x140088a24  push    rsi
0x140088a25  push    rdi
0x140088a26  push    r12
0x140088a28  push    r13
0x140088a2a  push    r14
0x140088a2c  push    r15
0x140088a2e  mov     rbp, rsp
0x140088a31  sub     rsp, 50h
0x140088a35  mov     r13, rcx
0x140088a38  lea     rdx, [rbp+LockState]; LockState
0x140088a3c  mov     rcx, [rcx+20h]; Lock
0x140088a40  xor     ebx, ebx
0x140088a42  xor     eax, eax
0x140088a44  mov     [rbp+var_10], ebx
0x140088a47  xor     r8d, r8d; Flags
0x140088a4a  mov     [rbp+LockState.OldIrql], bl
0x140088a4d  mov     word ptr [rbp+LockState.LockState], ax
0x140088a51  mov     r12, r9
0x140088a54  call    cs:__imp_NdisAcquireRWLockRead
0x140088a5b  nop     dword ptr [rax+rax+00h]
0x140088a60  xor     r9d, r9d; unsigned __int8 *
0x140088a63  lea     r8, [rbp+var_10]; unsigned int *
0x140088a67  lea     edx, [rbx+9]; enum MANAGEMENT_FRAME_TYPE
0x140088a6a  mov     rcx, r13; struct _WFD_ROLE *
0x140088a6d  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140088a72  mov     edi, eax
0x140088a74  test    eax, eax
0x140088a76  jz      short loc_140088A99
0x140088a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140088a7f  lea     rax, WPP_GLOBAL_Control
0x140088a86  cmp     rcx, rax
0x140088a89  jz      loc_140088C08
0x140088a8f  mov     edx, 0E7h
0x140088a94  jmp     loc_140088BF8
0x140088a99  mov     esi, [rbp+var_10]
0x140088a9c  mov     edi, 38h ; '8'
0x140088aa1  lea     r14d, [rsi+38h]
0x140088aa5  cmp     r14d, edi
0x140088aa8  jnb     short loc_140088AEA
0x140088aaa  mov     edi, 0C0010015h
0x140088aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140088ab6  lea     rax, WPP_GLOBAL_Control
0x140088abd  cmp     rcx, rax
0x140088ac0  jz      loc_140088C08
0x140088ac6  mov     rcx, [rcx+18h]
0x140088aca  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088ad1  mov     edx, 0E8h
0x140088ad6  mov     [rsp+50h+var_30], esi
0x140088ada  mov     r9d, 38h ; '8'
0x140088ae0  call    WPP_SF_Dd
0x140088ae5  jmp     loc_140088C08
0x140088aea  lea     eax, [r14+10h]
0x140088aee  cmp     eax, 10h
0x140088af1  jb      short loc_140088B60
0x140088af3  mov     ecx, 40h ; '@'
0x140088af8  mov     r15d, 30337776h
0x140088afe  cmp     eax, ecx
0x140088b00  ja      short loc_140088B0B
0x140088b02  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140088b09  jmp     short loc_140088B39
0x140088b0b  cmp     eax, 100h
0x140088b10  ja      short loc_140088B1B
0x140088b12  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140088b19  jmp     short loc_140088B39
0x140088b1b  cmp     eax, 400h
0x140088b20  ja      short loc_140088B2B
0x140088b22  lea     rbx, Lookaside
0x140088b29  jmp     short loc_140088B39
0x140088b2b  cmp     eax, 800h
0x140088b30  ja      short loc_140088B4A
0x140088b32  lea     rbx, stru_1400B0180
0x140088b39  mov     rcx, rbx; Lookaside
0x140088b3c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088b43  nop     dword ptr [rax+rax+00h]
0x140088b48  jmp     short loc_140088B5B
0x140088b4a  mov     edx, eax
0x140088b4c  mov     r8d, r15d
0x140088b4f  call    cs:__imp_ExAllocatePool2
0x140088b56  nop     dword ptr [rax+rax+00h]
0x140088b5b  test    rax, rax
0x140088b5e  jnz     short loc_140088B85
0x140088b60  mov     edi, 0C000009Ah
0x140088b65  xor     ebx, ebx
0x140088b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140088b6e  lea     rax, WPP_GLOBAL_Control
0x140088b75  cmp     rcx, rax
0x140088b78  jz      loc_140088C08
0x140088b7e  mov     edx, 0E9h
0x140088b83  jmp     short loc_140088BF8
0x140088b85  mov     [rax], rbx
0x140088b88  xor     edx, edx; Val
0x140088b8a  lea     rbx, [rax+10h]
0x140088b8e  mov     r8d, r14d; Size
0x140088b91  mov     rcx, rbx; void *
0x140088b94  mov     [rax+8], r15d
0x140088b98  call    memset
0x140088b9d  mov     al, [rbp+arg_10]
0x140088ba0  mov     r15b, 1
0x140088ba3  mov     dword ptr [rbx], 380180h
0x140088ba9  mov     [rbx+0Ah], al
0x140088bac  mov     [rbx+10h], r12
0x140088bb0  mov     byte ptr [rbx+1Ch], 0
0x140088bb4  mov     dword ptr [rbx+18h], 3E8h
0x140088bbb  test    esi, esi
0x140088bbd  jz      short loc_140088C21
0x140088bbf  mov     [rbx+2Ch], edi
0x140088bc2  lea     r9, [rbx+38h]; unsigned __int8 *
0x140088bc6  lea     r8, [rbp+var_10]; unsigned int *
0x140088bca  mov     [rbx+30h], esi
0x140088bcd  mov     edx, 9; enum MANAGEMENT_FRAME_TYPE
0x140088bd2  mov     rcx, r13; struct _WFD_ROLE *
0x140088bd5  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140088bda  mov     edi, eax
0x140088bdc  test    eax, eax
0x140088bde  jz      short loc_140088C29
0x140088be0  mov     rcx, cs:WPP_GLOBAL_Control
0x140088be7  lea     rax, WPP_GLOBAL_Control
0x140088bee  cmp     rcx, rax
0x140088bf1  jz      short loc_140088C08
0x140088bf3  mov     edx, 0EAh
0x140088bf8  mov     rcx, [rcx+18h]
0x140088bfc  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088c03  call    WPP_SF_
0x140088c08  mov     rcx, [r13+20h]; Lock
0x140088c0c  lea     rdx, [rbp+LockState]; LockState
0x140088c10  call    cs:__imp_NdisReleaseRWLock
0x140088c17  nop     dword ptr [rax+rax+00h]
0x140088c1c  jmp     loc_140088CF2
0x140088c21  mov     qword ptr [rbx+2Ch], 0
0x140088c29  mov     rcx, [r13+20h]; Lock
0x140088c2d  lea     rdx, [rbp+LockState]; LockState
0x140088c31  call    cs:__imp_NdisReleaseRWLock
0x140088c38  nop     dword ptr [rax+rax+00h]
0x140088c3d  mov     rcx, [rbp+arg_28]
0x140088c41  test    rcx, rcx
0x140088c44  jz      short loc_140088C55
0x140088c46  mov     eax, [rcx]
0x140088c48  mov     [rbx+1Fh], eax
0x140088c4b  movzx   eax, word ptr [rcx+4]
0x140088c4f  mov     [rbx+23h], ax
0x140088c53  jmp     short loc_140088C58
0x140088c55  xor     r15b, r15b
0x140088c58  mov     rcx, [rbp+arg_20]
0x140088c5c  lea     r9, [rbx+4]
0x140088c60  mov     [rbx+25h], r15b
0x140088c64  mov     eax, [rcx]
0x140088c66  mov     [r9], eax
0x140088c69  movzx   eax, word ptr [rcx+4]
0x140088c6d  mov     [r9+4], ax
0x140088c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140088c79  lea     rax, WPP_GLOBAL_Control
0x140088c80  cmp     rcx, rax
0x140088c83  jz      short loc_140088CC2
0x140088c85  cmp     byte ptr [rcx+29h], 3
0x140088c89  jb      short loc_140088CC2
0x140088c8b  test    dword ptr [rcx+2Ch], 200000h
0x140088c92  jz      short loc_140088CC2
0x140088c94  movzx   eax, byte ptr [rbx+1Ch]
0x140088c98  mov     edx, 0EBh
0x140088c9d  movzx   r8d, byte ptr [rbx+0Ah]
0x140088ca2  mov     rcx, [rcx+18h]
0x140088ca6  mov     [rsp+50h+var_18], eax
0x140088caa  mov     eax, [rbx+30h]
0x140088cad  mov     [rsp+50h+var_20], eax
0x140088cb1  mov     eax, [rbx+2Ch]
0x140088cb4  mov     [rsp+50h+var_28], eax
0x140088cb8  mov     [rsp+50h+var_30], r8d
0x140088cbd  call    WPP_SF__MAC_DDDD
0x140088cc2  mov     rcx, [rbp+arg_8]; struct _ADAPT *
0x140088cc6  mov     r9d, r14d; unsigned int
0x140088cc9  mov     r8, rbx; void *
0x140088ccc  mov     edx, 0E05010Eh; unsigned int
0x140088cd1  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x140088cd6  mov     ecx, eax
0x140088cd8  xor     eax, eax
0x140088cda  cmp     ecx, 40230001h
0x140088ce0  cmovz   ecx, eax
0x140088ce3  mov     [rbp+var_10], ecx
0x140088ce6  lea     rcx, [rbp+var_10]; int *
0x140088cea  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x140088cef  mov     edi, [rbp+var_10]
0x140088cf2  test    rbx, rbx
0x140088cf5  jz      short loc_140088D26
0x140088cf7  lea     rcx, [rbx-10h]; P
0x140088cfb  mov     rax, [rcx]
0x140088cfe  test    rax, rax
0x140088d01  jz      short loc_140088D17
0x140088d03  mov     rdx, rcx; Entry
0x140088d06  mov     rcx, rax; Lookaside
0x140088d09  call    cs:__imp_ExFreeToNPagedLookasideList
0x140088d10  nop     dword ptr [rax+rax+00h]
0x140088d15  jmp     short loc_140088D26
0x140088d17  mov     edx, [rcx+8]; Tag
0x140088d1a  call    cs:__imp_ExFreePoolWithTag
0x140088d21  nop     dword ptr [rax+rax+00h]
0x140088d26  mov     rbx, [rsp+50h+arg_18]
0x140088d2e  mov     eax, edi
0x140088d30  add     rsp, 50h
0x140088d34  pop     r15
0x140088d36  pop     r14
0x140088d38  pop     r13
0x140088d3a  pop     r12
0x140088d3c  pop     rdi
0x140088d3d  pop     rsi
0x140088d3e  pop     rbp
0x140088d3f  retn
```
