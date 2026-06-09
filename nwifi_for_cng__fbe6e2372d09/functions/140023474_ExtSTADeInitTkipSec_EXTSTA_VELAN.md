# ExtSTADeInitTkipSec(EXTSTA_VELAN *)

- ea: `0x140023474`
- end: `0x14002372a`
- name: `?ExtSTADeInitTkipSec@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `694`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006533c`

## callees

- `0x140023474`
- `0x140025704`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400236b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400236b5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002357e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002357e`
- `ntoskrnl!ExAllocatePool2` at `0x140023596`
- `ntoskrnl!ExAllocatePool2` at `0x140023596`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400236f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400236f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002370a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002370a`
- `ntoskrnl!ZwSetValueKey` at `0x1400236db`
- `ntoskrnl!ZwSetValueKey` at `0x1400236db`
- `NDIS!NdisMSleep` at `0x1400234a6`
- `NDIS!NdisMSleep` at `0x1400234a6`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400234dd`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400234dd`
- `NDIS!NdisReleaseRWLock` at `0x14002367e`
- `NDIS!NdisReleaseRWLock` at `0x14002367e`

## pseudocode

```c
void __fastcall ExtSTADeInitTkipSec(struct EXTSTA_VELAN *a1)
{
  _QWORD *Data; // rdi
  ULONG DataSize; // ebp
  unsigned __int64 v4; // r14
  unsigned int uNumPeersInTkipMicFailure; // r9d
  int v6; // edx
  __int64 v7; // r8
  int v8; // ecx
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *Pool2; // rax
  __int64 i; // rsi
  DOT11_MAC_STATE_ENTRY *pMacStateEntry; // rdx
  _VELAN *pGenVElan; // rax
  HKEY__ *hMibKey; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v18; // [rsp+68h] [rbp+10h] BYREF

  Data = 0;
  DataSize = 0;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  while ( a1->TkipSec.bExcludeMacListInProgress )
    NdisMSleep(0x30D40u);
  v4 = MEMORY[0xFFFFF78000000014];
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  uNumPeersInTkipMicFailure = a1->TkipSec.uNumPeersInTkipMicFailure;
  v6 = 0;
  v7 = 0;
  if ( uNumPeersInTkipMicFailure )
  {
    do
    {
      v8 = v6 + 1;
      if ( v4 >= a1->TkipSec.TkipMicFailurePeers[v7].ullExpiry )
        v8 = v6;
      v7 = (unsigned int)(v7 + 1);
      v6 = v8;
    }
    while ( (unsigned int)v7 < uNumPeersInTkipMicFailure );
    if ( v8 )
    {
      DataSize = 40 * v8;
      v9 = 40 * v8 + 16;
      if ( (unsigned int)(40 * v8) < 0xFFFFFFF0 )
      {
        if ( v9 > 0x40 )
        {
          if ( v9 > 0x100 )
          {
            if ( v9 > 0x400 )
            {
              if ( v9 > 0x800 )
              {
                p_WaitListHead = 0;
                Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 945910899);
                goto LABEL_19;
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
LABEL_19:
        if ( Pool2 )
        {
          Data = Pool2 + 4;
          *(_QWORD *)Pool2 = p_WaitListHead;
          Pool2[2] = 945910899;
          if ( Pool2 != (_DWORD *)-16LL )
            memset(Pool2 + 4, 0, DataSize);
        }
      }
    }
  }
  for ( i = 0; (unsigned int)i < a1->TkipSec.uNumPeersInTkipMicFailure; i = (unsigned int)(i + 1) )
  {
    pMacStateEntry = a1->TkipSec.TkipMicFailurePeers[i].pMacStateEntry;
    v18 = pMacStateEntry;
    if ( v4 < a1->TkipSec.TkipMicFailurePeers[i].ullExpiry && Data )
    {
      *(_DWORD *)Data = 1346980692;
      Data[2] = a1->TkipSec.TkipMicFailurePeers[i].ullCreatingTime;
      Data[3] = a1->TkipSec.TkipMicFailurePeers[i].ullExpiry;
      *((_BYTE *)Data + 10) = (*((_DWORD *)pMacStateEntry + 10) & 0x20) != 0;
      *((_BYTE *)Data + 11) = a1->TkipSec.TkipMicFailurePeers[i].bDefaultKey;
      *((_DWORD *)Data + 8) = a1->TkipSec.TkipMicFailurePeers[i].uKeyIndex;
      *((_DWORD *)Data + 1) = *(_DWORD *)pMacStateEntry->MacHashEntry.MacKey;
      *((_WORD *)Data + 4) = *(_WORD *)&pMacStateEntry->MacHashEntry.MacKey[4];
    }
    pMacStateEntry->pTkipMicFailureInfo = 0;
    Dot11DecObjCnt(&v18, (unsigned int)pMacStateEntry);
  }
  *(_QWORD *)&a1->TkipSec.uNumPeersInTkipMicFailure = 0;
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( Data )
  {
    pGenVElan = a1->pGenVElan;
    DestinationString = 0;
    hMibKey = pGenVElan->hMibKey;
    RtlInitUnicodeString(&DestinationString, L"TkipCountermeasture");
    ZwSetValueKey(hMibKey, &DestinationString, 0, 3u, Data, DataSize);
    if ( *(Data - 2) )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(Data - 2), Data - 2);
    else
      ExFreePoolWithTag(Data - 2, *((_DWORD *)Data - 2));
  }
}

```

## disassembly

```asm
0x140023474  mov     [rsp+arg_10], rbx
0x140023479  mov     [rsp+arg_18], rbp
0x14002347e  push    rsi
0x14002347f  push    rdi
0x140023480  push    r14
0x140023482  sub     rsp, 40h
0x140023486  xor     edi, edi
0x140023488  xor     eax, eax
0x14002348a  xor     ebp, ebp
0x14002348c  mov     [rsp+58h+LockState.OldIrql], dil
0x140023491  mov     rbx, rcx
0x140023494  mov     word ptr [rsp+58h+LockState.LockState], ax
0x140023499  cmp     [rcx+5F0h], eax
0x14002349f  jz      short loc_1400234BA
0x1400234a1  mov     ecx, 30D40h; MicrosecondsToSleep
0x1400234a6  call    cs:__imp_NdisMSleep
0x1400234ad  nop     dword ptr [rax+rax+00h]
0x1400234b2  cmp     [rbx+5F0h], edi
0x1400234b8  jnz     short loc_1400234A1
0x1400234ba  mov     r14, 0FFFFF78000000014h
0x1400234c4  lea     rdx, [rsp+58h+LockState]; LockState
0x1400234c9  xor     r8d, r8d; Flags
0x1400234cc  mov     r14, [r14]
0x1400234cf  mov     rcx, [rbx+0A38h]
0x1400234d6  mov     rcx, [rcx+90h]; Lock
0x1400234dd  call    cs:__imp_NdisAcquireRWLockWrite
0x1400234e4  nop     dword ptr [rax+rax+00h]
0x1400234e9  mov     r9d, [rbx+338h]
0x1400234f0  xor     edx, edx
0x1400234f2  xor     r8d, r8d
0x1400234f5  test    r9d, r9d
0x1400234f8  jz      loc_1400235C7
0x1400234fe  lea     rcx, [r8+r8*4]
0x140023502  mov     rax, [rbx+rcx*8+348h]
0x14002350a  lea     ecx, [rdx+1]
0x14002350d  cmp     r14, rax
0x140023510  cmovnb  ecx, edx
0x140023513  inc     r8d
0x140023516  mov     edx, ecx
0x140023518  cmp     r8d, r9d
0x14002351b  jb      short loc_1400234FE
0x14002351d  test    ecx, ecx
0x14002351f  jz      loc_1400235C7
0x140023525  lea     eax, [rcx+rcx*4]
0x140023528  lea     ebp, ds:0[rax*8]
0x14002352f  lea     eax, [rbp+10h]
0x140023532  cmp     eax, 10h
0x140023535  jb      loc_1400235C7
0x14002353b  mov     ecx, 40h ; '@'
0x140023540  cmp     eax, ecx
0x140023542  ja      short loc_14002354D
0x140023544  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14002354b  jmp     short loc_14002357B
0x14002354d  cmp     eax, 100h
0x140023552  ja      short loc_14002355D
0x140023554  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14002355b  jmp     short loc_14002357B
0x14002355d  cmp     eax, 400h
0x140023562  ja      short loc_14002356D
0x140023564  lea     rsi, Lookaside
0x14002356b  jmp     short loc_14002357B
0x14002356d  cmp     eax, 800h
0x140023572  ja      short loc_14002358C
0x140023574  lea     rsi, stru_1400B31C0
0x14002357b  mov     rcx, rsi; Lookaside
0x14002357e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140023585  nop     dword ptr [rax+rax+00h]
0x14002358a  jmp     short loc_1400235A2
0x14002358c  xor     esi, esi
0x14002358e  mov     edx, eax
0x140023590  mov     r8d, 38617473h
0x140023596  call    cs:__imp_ExAllocatePool2
0x14002359d  nop     dword ptr [rax+rax+00h]
0x1400235a2  test    rax, rax
0x1400235a5  jz      short loc_1400235C7
0x1400235a7  lea     rdi, [rax+10h]
0x1400235ab  mov     [rax], rsi
0x1400235ae  mov     dword ptr [rax+8], 38617473h
0x1400235b5  test    rdi, rdi
0x1400235b8  jz      short loc_1400235C7
0x1400235ba  mov     r8d, ebp; Size
0x1400235bd  xor     edx, edx; Val
0x1400235bf  mov     rcx, rdi; void *
0x1400235c2  call    memset
0x1400235c7  xor     esi, esi
0x1400235c9  cmp     [rbx+338h], esi
0x1400235cf  jbe     loc_140023660
0x1400235d5  lea     rcx, [rsi+rsi*4]
0x1400235d9  mov     rdx, [rbx+rcx*8+360h]; unsigned int
0x1400235e1  mov     [rsp+58h+arg_8], rdx
0x1400235e6  cmp     r14, [rbx+rcx*8+348h]
0x1400235ee  jnb     short loc_140023640
0x1400235f0  test    rdi, rdi
0x1400235f3  jz      short loc_140023640
0x1400235f5  mov     dword ptr [rdi], 50494B54h
0x1400235fb  mov     rax, [rbx+rcx*8+340h]
0x140023603  mov     [rdi+10h], rax
0x140023607  mov     rax, [rbx+rcx*8+348h]
0x14002360f  mov     [rdi+18h], rax
0x140023613  mov     eax, [rdx+28h]
0x140023616  shr     eax, 5
0x140023619  and     al, 1
0x14002361b  mov     [rdi+0Ah], al
0x14002361e  mov     al, [rbx+rcx*8+350h]
0x140023625  mov     [rdi+0Bh], al
0x140023628  mov     eax, [rbx+rcx*8+354h]
0x14002362f  mov     [rdi+20h], eax
0x140023632  mov     eax, [rdx+10h]
0x140023635  mov     [rdi+4], eax
0x140023638  movzx   eax, word ptr [rdx+14h]
0x14002363c  mov     [rdi+8], ax
0x140023640  lea     rcx, [rsp+58h+arg_8]; struct DOT11_MAC_STATE_ENTRY **
0x140023645  mov     qword ptr [rdx+70h], 0
0x14002364d  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x140023652  inc     esi
0x140023654  cmp     esi, [rbx+338h]
0x14002365a  jb      loc_1400235D5
0x140023660  mov     qword ptr [rbx+338h], 0
0x14002366b  lea     rdx, [rsp+58h+LockState]; LockState
0x140023670  mov     rcx, [rbx+0A38h]
0x140023677  mov     rcx, [rcx+90h]; Lock
0x14002367e  call    cs:__imp_NdisReleaseRWLock
0x140023685  nop     dword ptr [rax+rax+00h]
0x14002368a  test    rdi, rdi
0x14002368d  jz      loc_140023716
0x140023693  mov     rax, [rbx+0A38h]
0x14002369a  lea     rdx, SourceString; "TkipCountermeasture"
0x1400236a1  xorps   xmm0, xmm0
0x1400236a4  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400236a9  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1400236ae  mov     rbx, [rax+1310h]
0x1400236b5  call    cs:__imp_RtlInitUnicodeString
0x1400236bc  nop     dword ptr [rax+rax+00h]
0x1400236c1  mov     r9d, 3; Type
0x1400236c7  mov     [rsp+58h+DataSize], ebp; DataSize
0x1400236cb  xor     r8d, r8d; TitleIndex
0x1400236ce  mov     [rsp+58h+Data], rdi; Data
0x1400236d3  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x1400236d8  mov     rcx, rbx; KeyHandle
0x1400236db  call    cs:__imp_ZwSetValueKey
0x1400236e2  nop     dword ptr [rax+rax+00h]
0x1400236e7  lea     rcx, [rdi-10h]; P
0x1400236eb  mov     rax, [rcx]
0x1400236ee  test    rax, rax
0x1400236f1  jz      short loc_140023707
0x1400236f3  mov     rdx, rcx; Entry
0x1400236f6  mov     rcx, rax; Lookaside
0x1400236f9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140023700  nop     dword ptr [rax+rax+00h]
0x140023705  jmp     short loc_140023716
0x140023707  mov     edx, [rcx+8]; Tag
0x14002370a  call    cs:__imp_ExFreePoolWithTag
0x140023711  nop     dword ptr [rax+rax+00h]
0x140023716  mov     rbx, [rsp+58h+arg_10]
0x14002371b  mov     rbp, [rsp+58h+arg_18]
0x140023720  add     rsp, 40h
0x140023724  pop     r14
0x140023726  pop     rdi
0x140023727  pop     rsi
0x140023728  retn
```
