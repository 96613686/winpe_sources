# ExtSTAReceivePacket(EXTSTA_VELAN *,NWIFI_MSDU * const,uint)

- ea: `0x140012560`
- end: `0x1400127a3`
- name: `?ExtSTAReceivePacket@@YAXPEAUEXTSTA_VELAN@@QEAUNWIFI_MSDU@@I@Z`
- size: `579`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct NWIFI_MSDU *const, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000d21c`
- `0x140012560`
- `0x1400127ac`
- `0x140013720`
- `0x14006b658`
- `0x14006b7b0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400126a1`
- `NDIS!NdisReleaseRWLock` at `0x140012754`
- `NDIS!NdisReleaseRWLock` at `0x1400126a1`
- `NDIS!NdisReleaseRWLock` at `0x140012754`
- `NDIS!NdisAcquireRWLockRead` at `0x1400125b7`
- `NDIS!NdisAcquireRWLockRead` at `0x1400126d0`
- `NDIS!NdisAcquireRWLockRead` at `0x1400125b7`
- `NDIS!NdisAcquireRWLockRead` at `0x1400126d0`

## pseudocode

```c
void __fastcall ExtSTAReceivePacket(struct EXTSTA_VELAN *a1, struct NWIFI_MSDU *const a2, unsigned int a3)
{
  int v6; // ebx
  unsigned int v7; // r14d
  int i; // r15d
  struct NWIFI_MSDU *v9; // rdi
  _NET_BUFFER_LIST *pNdisPacket; // rdx
  _WORD *pvLookaheadBuf; // r9
  __int64 v12; // r8
  __int16 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // edi
  int v20; // eax
  struct _ADAPT *v21; // rcx
  unsigned int v22; // r8d
  unsigned int v23; // edi
  int j; // esi
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+18h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( a3 == 32 )
    v6 = -1;
  else
    v6 = (1 << a3) - 1;
  NdisAcquireRWLockRead(a1->pGenVElan->pRWLock, &LockState, 0);
  if ( (a1->ModuleStatus.uValue & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_cd320d255d73392dd823018075971813_Traceguids);
    }
  }
  else
  {
    v6 = 0;
    v7 = 0;
    for ( i = 1; v7 < a3; v6 = v20 )
    {
      v9 = &a2[(unsigned __int64)v7];
      pNdisPacket = v9->MSDUCore.pNdisPacket;
      pvLookaheadBuf = v9->MSDUCore.pvLookaheadBuf;
      v12 = *(_QWORD *)&pNdisPacket->Context->ContextData[pNdisPacket->Context->Offset];
      v13 = (__int16 *)pNdisPacket->NetBufferListInfo[6];
      if ( v13[1] == 48 )
        v14 = *((_QWORD *)v13 + 4);
      else
        v14 = 0;
      *(_QWORD *)(v12 + 24) = v14;
      v15 = *(_QWORD *)(v12 + 8);
      if ( v15 && *((int *)v13 + 5) < 0 )
      {
        v16 = v13[10];
        v17 = *(__int16 *)(v15 + 50);
        *(_WORD *)(v15 + 48) = v16;
        *(_WORD *)(v15 + 50) = (v17 + v16) / 2;
      }
      if ( (((unsigned __int16)*pvLookaheadBuf >> 2) & 3) != 0 )
      {
        if ( (((unsigned __int16)*pvLookaheadBuf >> 2) & 3) == 2 )
        {
          v18 = ExtSTAReceiveDataPacket(a1, &a2[(unsigned __int64)v7], (struct _NWIFI_LOCK_STATE *)&LockState);
LABEL_21:
          v19 = v18;
          goto LABEL_22;
        }
      }
      else
      {
        if ( (unsigned __int8)*pvLookaheadBuf >> 4 == 4 )
        {
          v18 = ExtSTAProcessProbeRequest(a1, &a2[(unsigned __int64)v7]);
          goto LABEL_21;
        }
        if ( (unsigned __int8)*pvLookaheadBuf >> 4 == 5 || (unsigned __int8)*pvLookaheadBuf >> 4 == 8 )
        {
          NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
          v19 = ExtSTAProcessProbeResponse(a1, &a2[(unsigned __int64)v7]);
          NdisAcquireRWLockRead(a1->pGenVElan->pRWLock, &LockState, 0);
          goto LABEL_22;
        }
      }
      v19 = -1073676273;
LABEL_22:
      v20 = v6 | i;
      if ( v19 == 259 )
        v20 = v6;
      ++v7;
      i *= 2;
    }
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( v6 )
  {
    v23 = 0;
    for ( j = 1; v23 < a3; j *= 2 )
    {
      if ( (j & v6) != 0 )
        FilterReturnNetBufferLists(v21, a2[(unsigned __int64)v23].MSDUCore.pNdisPacket, v22);
      ++v23;
    }
  }
}

```

## disassembly

```asm
0x140012560  mov     [rsp+arg_0], rbx
0x140012565  mov     [rsp+arg_8], rbp
0x14001256a  push    rsi
0x14001256b  push    rdi
0x14001256c  push    r12
0x14001256e  push    r14
0x140012570  push    r15
0x140012572  sub     rsp, 20h
0x140012576  xor     eax, eax
0x140012578  mov     [rsp+48h+LockState.OldIrql], 0
0x14001257d  mov     word ptr [rsp+48h+LockState.LockState], ax
0x140012582  mov     ebp, r8d
0x140012585  mov     r12, rdx
0x140012588  mov     rsi, rcx
0x14001258b  cmp     r8d, 20h ; ' '
0x14001258f  jnz     short loc_140012596
0x140012591  or      ebx, 0FFFFFFFFh
0x140012594  jmp     short loc_1400125A1
0x140012596  mov     ecx, ebp
0x140012598  mov     ebx, 1
0x14001259d  shl     ebx, cl
0x14001259f  dec     ebx
0x1400125a1  mov     rcx, [rsi+0A38h]
0x1400125a8  lea     rdx, [rsp+48h+LockState]; LockState
0x1400125ad  xor     r8d, r8d; Flags
0x1400125b0  mov     rcx, [rcx+90h]; Lock
0x1400125b7  call    cs:__imp_NdisAcquireRWLockRead
0x1400125be  nop     dword ptr [rax+rax+00h]
0x1400125c3  mov     eax, [rsi]
0x1400125c5  test    al, 4
0x1400125c7  jnz     loc_14001270C
0x1400125cd  xor     ebx, ebx
0x1400125cf  xor     r14d, r14d
0x1400125d2  lea     r15d, [rbx+1]
0x1400125d6  test    ebp, ebp
0x1400125d8  jz      loc_140012741
0x1400125de  mov     edi, r14d
0x1400125e1  shl     rdi, 6
0x1400125e5  add     rdi, r12
0x1400125e8  mov     rdx, [rdi+20h]
0x1400125ec  mov     r9, [rdi+18h]
0x1400125f0  mov     rcx, [rdx+10h]
0x1400125f4  movzx   eax, word ptr [rcx+0Ah]
0x1400125f8  mov     r8, [rax+rcx+10h]
0x1400125fd  mov     rax, [rdx+0C0h]
0x140012604  cmp     word ptr [rax+2], 30h ; '0'
0x140012609  jnz     short loc_140012611
0x14001260b  mov     rcx, [rax+20h]
0x14001260f  jmp     short loc_140012613
0x140012611  xor     ecx, ecx
0x140012613  mov     [r8+18h], rcx
0x140012617  mov     r8, [r8+8]
0x14001261b  test    r8, r8
0x14001261e  jz      short loc_140012643
0x140012620  cmp     dword ptr [rax+14h], 0
0x140012624  jge     short loc_140012643
0x140012626  movsx   eax, word ptr [rax+14h]
0x14001262a  movsx   ecx, word ptr [r8+32h]
0x14001262f  mov     [r8+30h], ax
0x140012634  add     eax, ecx
0x140012636  cdq
0x140012637  mov     ecx, 2
0x14001263c  idiv    ecx
0x14001263e  mov     [r8+32h], ax
0x140012643  movzx   ecx, word ptr [r9]
0x140012647  mov     r8d, ecx
0x14001264a  shr     r8d, 2
0x14001264e  and     r8d, 3
0x140012652  jz      short loc_140012672
0x140012654  sub     r8d, 1
0x140012658  jz      short loc_140012687
0x14001265a  cmp     r8d, 1
0x14001265e  jnz     short loc_140012687
0x140012660  lea     r8, [rsp+48h+LockState]
0x140012665  mov     rdx, rdi
0x140012668  mov     rcx, rsi; struct EXTSTA_VELAN *
0x14001266b  call    ExtSTAReceiveDataPacket
0x140012670  jmp     short loc_1400126E9
0x140012672  shr     ecx, 4
0x140012675  and     ecx, 0Fh
0x140012678  sub     ecx, 4
0x14001267b  jz      short loc_1400126DE
0x14001267d  sub     ecx, 1
0x140012680  jz      short loc_14001268E
0x140012682  cmp     ecx, 3
0x140012685  jz      short loc_14001268E
0x140012687  mov     edi, 0C001000Fh
0x14001268c  jmp     short loc_1400126EB
0x14001268e  mov     rcx, [rsi+0A38h]
0x140012695  lea     rdx, [rsp+48h+LockState]; LockState
0x14001269a  mov     rcx, [rcx+90h]; Lock
0x1400126a1  call    cs:__imp_NdisReleaseRWLock
0x1400126a8  nop     dword ptr [rax+rax+00h]
0x1400126ad  mov     rdx, rdi
0x1400126b0  mov     rcx, rsi
0x1400126b3  call    ExtSTAProcessProbeResponse
0x1400126b8  mov     rcx, [rsi+0A38h]
0x1400126bf  lea     rdx, [rsp+48h+LockState]; LockState
0x1400126c4  xor     r8d, r8d; Flags
0x1400126c7  mov     edi, eax
0x1400126c9  mov     rcx, [rcx+90h]; Lock
0x1400126d0  call    cs:__imp_NdisAcquireRWLockRead
0x1400126d7  nop     dword ptr [rax+rax+00h]
0x1400126dc  jmp     short loc_1400126EB
0x1400126de  mov     rdx, rdi
0x1400126e1  mov     rcx, rsi
0x1400126e4  call    ExtSTAProcessProbeRequest
0x1400126e9  mov     edi, eax
0x1400126eb  mov     eax, r15d
0x1400126ee  or      eax, ebx
0x1400126f0  cmp     edi, 103h
0x1400126f6  cmovz   eax, ebx
0x1400126f9  inc     r14d
0x1400126fc  add     r15d, r15d
0x1400126ff  mov     ebx, eax
0x140012701  cmp     r14d, ebp
0x140012704  jb      loc_1400125DE
0x14001270a  jmp     short loc_140012741
0x14001270c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012713  lea     rax, WPP_GLOBAL_Control
0x14001271a  cmp     rcx, rax
0x14001271d  jz      short loc_140012741
0x14001271f  cmp     byte ptr [rcx+29h], 4
0x140012723  jb      short loc_140012741
0x140012725  mov     eax, [rcx+2Ch]
0x140012728  test    al, 20h
0x14001272a  jz      short loc_140012741
0x14001272c  mov     rcx, [rcx+18h]
0x140012730  lea     r8, WPP_cd320d255d73392dd823018075971813_Traceguids
0x140012737  mov     edx, 0Ah
0x14001273c  call    WPP_SF_
0x140012741  mov     rcx, [rsi+0A38h]
0x140012748  lea     rdx, [rsp+48h+LockState]; LockState
0x14001274d  mov     rcx, [rcx+90h]; Lock
0x140012754  call    cs:__imp_NdisReleaseRWLock
0x14001275b  nop     dword ptr [rax+rax+00h]
0x140012760  test    ebx, ebx
0x140012762  jz      short loc_14001278B
0x140012764  xor     edi, edi
0x140012766  mov     esi, 1
0x14001276b  test    ebp, ebp
0x14001276d  jz      short loc_14001278B
0x14001276f  test    ebx, esi
0x140012771  jz      short loc_140012783
0x140012773  mov     edx, edi
0x140012775  shl     rdx, 6
0x140012779  mov     rdx, [rdx+r12+20h]; struct _NET_BUFFER_LIST *
0x14001277e  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x140012783  inc     edi
0x140012785  add     esi, esi
0x140012787  cmp     edi, ebp
0x140012789  jb      short loc_14001276F
0x14001278b  mov     rbx, [rsp+48h+arg_0]
0x140012790  mov     rbp, [rsp+48h+arg_8]
0x140012795  add     rsp, 20h
0x140012799  pop     r15
0x14001279b  pop     r14
0x14001279d  pop     r12
0x14001279f  pop     rdi
0x1400127a0  pop     rsi
0x1400127a1  retn
```
