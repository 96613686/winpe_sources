# ExtSTAReceivePacket(EXTSTA_VELAN *,NWIFI_MSDU * const,uint)

- ea: `0x140012570`
- end: `0x1400127b3`
- name: `?ExtSTAReceivePacket@@YAXPEAUEXTSTA_VELAN@@QEAUNWIFI_MSDU@@I@Z`
- size: `579`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct NWIFI_MSDU *const, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000d22c`
- `0x140012570`
- `0x1400127bc`
- `0x140013730`
- `0x140069e28`
- `0x140069f80`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400126b1`
- `NDIS!NdisReleaseRWLock` at `0x140012764`
- `NDIS!NdisReleaseRWLock` at `0x1400126b1`
- `NDIS!NdisReleaseRWLock` at `0x140012764`
- `NDIS!NdisAcquireRWLockRead` at `0x1400125c7`
- `NDIS!NdisAcquireRWLockRead` at `0x1400126e0`
- `NDIS!NdisAcquireRWLockRead` at `0x1400125c7`
- `NDIS!NdisAcquireRWLockRead` at `0x1400126e0`

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
          v18 = ExtSTAReceiveDataPacket(a1);
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
0x140012570  mov     [rsp+arg_0], rbx
0x140012575  mov     [rsp+arg_8], rbp
0x14001257a  push    rsi
0x14001257b  push    rdi
0x14001257c  push    r12
0x14001257e  push    r14
0x140012580  push    r15
0x140012582  sub     rsp, 20h
0x140012586  xor     eax, eax
0x140012588  mov     [rsp+48h+LockState.OldIrql], 0
0x14001258d  mov     word ptr [rsp+48h+LockState.LockState], ax
0x140012592  mov     ebp, r8d
0x140012595  mov     r12, rdx
0x140012598  mov     rsi, rcx
0x14001259b  cmp     r8d, 20h ; ' '
0x14001259f  jnz     short loc_1400125A6
0x1400125a1  or      ebx, 0FFFFFFFFh
0x1400125a4  jmp     short loc_1400125B1
0x1400125a6  mov     ecx, ebp
0x1400125a8  mov     ebx, 1
0x1400125ad  shl     ebx, cl
0x1400125af  dec     ebx
0x1400125b1  mov     rcx, [rsi+0A38h]
0x1400125b8  lea     rdx, [rsp+48h+LockState]; LockState
0x1400125bd  xor     r8d, r8d; Flags
0x1400125c0  mov     rcx, [rcx+90h]; Lock
0x1400125c7  call    cs:__imp_NdisAcquireRWLockRead
0x1400125ce  nop     dword ptr [rax+rax+00h]
0x1400125d3  mov     eax, [rsi]
0x1400125d5  test    al, 4
0x1400125d7  jnz     loc_14001271C
0x1400125dd  xor     ebx, ebx
0x1400125df  xor     r14d, r14d
0x1400125e2  lea     r15d, [rbx+1]
0x1400125e6  test    ebp, ebp
0x1400125e8  jz      loc_140012751
0x1400125ee  mov     edi, r14d
0x1400125f1  shl     rdi, 6
0x1400125f5  add     rdi, r12
0x1400125f8  mov     rdx, [rdi+20h]
0x1400125fc  mov     r9, [rdi+18h]
0x140012600  mov     rcx, [rdx+10h]
0x140012604  movzx   eax, word ptr [rcx+0Ah]
0x140012608  mov     r8, [rax+rcx+10h]
0x14001260d  mov     rax, [rdx+0C0h]
0x140012614  cmp     word ptr [rax+2], 30h ; '0'
0x140012619  jnz     short loc_140012621
0x14001261b  mov     rcx, [rax+20h]
0x14001261f  jmp     short loc_140012623
0x140012621  xor     ecx, ecx
0x140012623  mov     [r8+18h], rcx
0x140012627  mov     r8, [r8+8]
0x14001262b  test    r8, r8
0x14001262e  jz      short loc_140012653
0x140012630  cmp     dword ptr [rax+14h], 0
0x140012634  jge     short loc_140012653
0x140012636  movsx   eax, word ptr [rax+14h]
0x14001263a  movsx   ecx, word ptr [r8+32h]
0x14001263f  mov     [r8+30h], ax
0x140012644  add     eax, ecx
0x140012646  cdq
0x140012647  mov     ecx, 2
0x14001264c  idiv    ecx
0x14001264e  mov     [r8+32h], ax
0x140012653  movzx   ecx, word ptr [r9]
0x140012657  mov     r8d, ecx
0x14001265a  shr     r8d, 2
0x14001265e  and     r8d, 3
0x140012662  jz      short loc_140012682
0x140012664  sub     r8d, 1
0x140012668  jz      short loc_140012697
0x14001266a  cmp     r8d, 1
0x14001266e  jnz     short loc_140012697
0x140012670  lea     r8, [rsp+48h+LockState]
0x140012675  mov     rdx, rdi
0x140012678  mov     rcx, rsi; struct EXTSTA_VELAN *
0x14001267b  call    ExtSTAReceiveDataPacket
0x140012680  jmp     short loc_1400126F9
0x140012682  shr     ecx, 4
0x140012685  and     ecx, 0Fh
0x140012688  sub     ecx, 4
0x14001268b  jz      short loc_1400126EE
0x14001268d  sub     ecx, 1
0x140012690  jz      short loc_14001269E
0x140012692  cmp     ecx, 3
0x140012695  jz      short loc_14001269E
0x140012697  mov     edi, 0C001000Fh
0x14001269c  jmp     short loc_1400126FB
0x14001269e  mov     rcx, [rsi+0A38h]
0x1400126a5  lea     rdx, [rsp+48h+LockState]; LockState
0x1400126aa  mov     rcx, [rcx+90h]; Lock
0x1400126b1  call    cs:__imp_NdisReleaseRWLock
0x1400126b8  nop     dword ptr [rax+rax+00h]
0x1400126bd  mov     rdx, rdi
0x1400126c0  mov     rcx, rsi
0x1400126c3  call    ExtSTAProcessProbeResponse
0x1400126c8  mov     rcx, [rsi+0A38h]
0x1400126cf  lea     rdx, [rsp+48h+LockState]; LockState
0x1400126d4  xor     r8d, r8d; Flags
0x1400126d7  mov     edi, eax
0x1400126d9  mov     rcx, [rcx+90h]; Lock
0x1400126e0  call    cs:__imp_NdisAcquireRWLockRead
0x1400126e7  nop     dword ptr [rax+rax+00h]
0x1400126ec  jmp     short loc_1400126FB
0x1400126ee  mov     rdx, rdi
0x1400126f1  mov     rcx, rsi
0x1400126f4  call    ExtSTAProcessProbeRequest
0x1400126f9  mov     edi, eax
0x1400126fb  mov     eax, r15d
0x1400126fe  or      eax, ebx
0x140012700  cmp     edi, 103h
0x140012706  cmovz   eax, ebx
0x140012709  inc     r14d
0x14001270c  add     r15d, r15d
0x14001270f  mov     ebx, eax
0x140012711  cmp     r14d, ebp
0x140012714  jb      loc_1400125EE
0x14001271a  jmp     short loc_140012751
0x14001271c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012723  lea     rax, WPP_GLOBAL_Control
0x14001272a  cmp     rcx, rax
0x14001272d  jz      short loc_140012751
0x14001272f  cmp     byte ptr [rcx+29h], 4
0x140012733  jb      short loc_140012751
0x140012735  mov     eax, [rcx+2Ch]
0x140012738  test    al, 20h
0x14001273a  jz      short loc_140012751
0x14001273c  mov     rcx, [rcx+18h]
0x140012740  lea     r8, WPP_cd320d255d73392dd823018075971813_Traceguids
0x140012747  mov     edx, 0Ah
0x14001274c  call    WPP_SF_
0x140012751  mov     rcx, [rsi+0A38h]
0x140012758  lea     rdx, [rsp+48h+LockState]; LockState
0x14001275d  mov     rcx, [rcx+90h]; Lock
0x140012764  call    cs:__imp_NdisReleaseRWLock
0x14001276b  nop     dword ptr [rax+rax+00h]
0x140012770  test    ebx, ebx
0x140012772  jz      short loc_14001279B
0x140012774  xor     edi, edi
0x140012776  mov     esi, 1
0x14001277b  test    ebp, ebp
0x14001277d  jz      short loc_14001279B
0x14001277f  test    ebx, esi
0x140012781  jz      short loc_140012793
0x140012783  mov     edx, edi
0x140012785  shl     rdx, 6
0x140012789  mov     rdx, [rdx+r12+20h]; struct _NET_BUFFER_LIST *
0x14001278e  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x140012793  inc     edi
0x140012795  add     esi, esi
0x140012797  cmp     edi, ebp
0x140012799  jb      short loc_14001277F
0x14001279b  mov     rbx, [rsp+48h+arg_0]
0x1400127a0  mov     rbp, [rsp+48h+arg_8]
0x1400127a5  add     rsp, 20h
0x1400127a9  pop     r15
0x1400127ab  pop     r14
0x1400127ad  pop     r12
0x1400127af  pop     rdi
0x1400127b0  pop     rsi
0x1400127b1  retn
```
