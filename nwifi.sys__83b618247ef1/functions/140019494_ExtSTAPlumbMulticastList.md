# ExtSTAPlumbMulticastList

- ea: `0x140019494`
- end: `0x140019641`
- name: `ExtSTAPlumbMulticastList`
- size: `429`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400600a0`

## callees

- `0x140019494`
- `0x140019bbc`
- `0x140020dc0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001953c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001953c`
- `ntoskrnl!ExAllocatePool2` at `0x14001954f`
- `ntoskrnl!ExAllocatePool2` at `0x14001954f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019618`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019618`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019629`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400194c7`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400194c7`
- `NDIS!NdisReleaseRWLock` at `0x1400195cd`
- `NDIS!NdisReleaseRWLock` at `0x1400195cd`

## pseudocode

```c
__int64 __fastcall ExtSTAPlumbMulticastList(__int64 a1)
{
  __int64 v2; // rcx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *v4; // rdi
  unsigned int v5; // ebp
  __int64 v6; // r9
  int v7; // eax
  unsigned int v8; // eax
  _DWORD *Pool2; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 2616);
  *(_WORD *)&LockState.LockState = 0;
  p_WaitListHead = 0;
  LockState.OldIrql = 0;
  v4 = 0;
  v5 = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v2 + 144), &LockState, 0);
  if ( !*(_QWORD *)(a1 + 1816) )
    goto LABEL_18;
  v7 = *(_DWORD *)(a1 + 1824);
  if ( !v7 )
    goto LABEL_18;
  v8 = v7 + 16;
  if ( v8 >= 0x10 )
  {
    if ( v8 > 0x40 )
    {
      if ( v8 > 0x100 )
      {
        if ( v8 > 0x400 )
        {
          if ( v8 > 0x800 )
          {
            Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 845771639, v6);
LABEL_14:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              LODWORD(p_WaitListHead) = 0;
              Pool2[2] = 845771639;
              v4 = (char *)(Pool2 + 4);
              v5 = *(_DWORD *)(a1 + 1824);
              memmove(Pool2 + 4, *(const void **)(a1 + 1816), v5);
              goto LABEL_18;
            }
            goto LABEL_15;
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
    goto LABEL_14;
  }
LABEL_15:
  LODWORD(p_WaitListHead) = -1073741670;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      101,
      WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
      *(unsigned int *)(a1 + 1824));
LABEL_18:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(a1 + 2616) + 144LL), &LockState);
  if ( v5 )
  {
    LODWORD(p_WaitListHead) = PtRequestAdapterSync(
                                *(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL),
                                1u,
                                0x1010103u,
                                v4,
                                v5);
    if ( v4 )
    {
      if ( *((_QWORD *)v4 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v4 - 2), v4 - 16);
      else
        ExFreePoolWithTag(v4 - 16, *((_DWORD *)v4 - 2));
    }
  }
  return (unsigned int)p_WaitListHead;
}

```

## disassembly

```asm
0x140019494  push    rbx
0x140019496  push    rbp
0x140019497  push    rsi
0x140019498  push    rdi
0x140019499  sub     rsp, 38h
0x14001949d  mov     rsi, rcx
0x1400194a0  lea     rdx, [rsp+58h+LockState]; LockState
0x1400194a5  mov     rcx, [rcx+0A38h]
0x1400194ac  xor     eax, eax
0x1400194ae  mov     word ptr [rsp+58h+LockState.LockState], ax
0x1400194b3  xor     ebx, ebx
0x1400194b5  mov     [rsp+58h+LockState.OldIrql], bl
0x1400194b9  xor     r8d, r8d; Flags
0x1400194bc  xor     edi, edi
0x1400194be  xor     ebp, ebp
0x1400194c0  mov     rcx, [rcx+90h]; Lock
0x1400194c7  call    cs:__imp_NdisAcquireRWLockWrite
0x1400194ce  nop     dword ptr [rax+rax+00h]
0x1400194d3  cmp     [rsi+718h], rbx
0x1400194da  jz      loc_1400195BA
0x1400194e0  mov     eax, [rsi+720h]
0x1400194e6  test    eax, eax
0x1400194e8  jz      loc_1400195BA
0x1400194ee  add     eax, 10h
0x1400194f1  cmp     eax, 10h
0x1400194f4  jb      short loc_140019560
0x1400194f6  lea     ecx, [rbx+40h]
0x1400194f9  mov     edi, 32697377h
0x1400194fe  cmp     eax, ecx
0x140019500  ja      short loc_14001950B
0x140019502  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140019509  jmp     short loc_140019539
0x14001950b  cmp     eax, 100h
0x140019510  ja      short loc_14001951B
0x140019512  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140019519  jmp     short loc_140019539
0x14001951b  cmp     eax, 400h
0x140019520  ja      short loc_14001952B
0x140019522  lea     rbx, Lookaside
0x140019529  jmp     short loc_140019539
0x14001952b  cmp     eax, 800h
0x140019530  ja      short loc_14001954A
0x140019532  lea     rbx, stru_1400B0180
0x140019539  mov     rcx, rbx; Lookaside
0x14001953c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140019543  nop     dword ptr [rax+rax+00h]
0x140019548  jmp     short loc_14001955B
0x14001954a  mov     edx, eax
0x14001954c  mov     r8d, edi
0x14001954f  call    cs:__imp_ExAllocatePool2
0x140019556  nop     dword ptr [rax+rax+00h]
0x14001955b  test    rax, rax
0x14001955e  jnz     short loc_140019596
0x140019560  mov     ebx, 0C000009Ah
0x140019565  mov     rcx, cs:WPP_GLOBAL_Control
0x14001956c  lea     rax, WPP_GLOBAL_Control
0x140019573  xor     edi, edi
0x140019575  cmp     rcx, rax
0x140019578  jz      short loc_1400195BA
0x14001957a  mov     r9d, [rsi+720h]
0x140019581  lea     edx, [rdi+65h]
0x140019584  mov     rcx, [rcx+18h]
0x140019588  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14001958f  call    WPP_SF_d
0x140019594  jmp     short loc_1400195BA
0x140019596  mov     [rax], rbx
0x140019599  xor     ebx, ebx
0x14001959b  mov     [rax+8], edi
0x14001959e  lea     rdi, [rax+10h]
0x1400195a2  mov     ebp, [rsi+720h]
0x1400195a8  mov     rcx, rdi; void *
0x1400195ab  mov     rdx, [rsi+718h]; Src
0x1400195b2  mov     r8d, ebp; Size
0x1400195b5  call    memmove
0x1400195ba  mov     rcx, [rsi+0A38h]
0x1400195c1  lea     rdx, [rsp+58h+LockState]; LockState
0x1400195c6  mov     rcx, [rcx+90h]; Lock
0x1400195cd  call    cs:__imp_NdisReleaseRWLock
0x1400195d4  nop     dword ptr [rax+rax+00h]
0x1400195d9  test    ebp, ebp
0x1400195db  jz      short loc_140019635
0x1400195dd  mov     rcx, [rsi+0A38h]
0x1400195e4  mov     r9, rdi; void *
0x1400195e7  mov     edx, 1; unsigned int
0x1400195ec  mov     [rsp+58h+var_38], ebp; unsigned int
0x1400195f0  mov     r8d, 1010103h; unsigned int
0x1400195f6  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400195fa  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400195ff  mov     ebx, eax
0x140019601  test    rdi, rdi
0x140019604  jz      short loc_140019635
0x140019606  lea     rcx, [rdi-10h]; P
0x14001960a  mov     r8, [rcx]
0x14001960d  test    r8, r8
0x140019610  jz      short loc_140019626
0x140019612  mov     rdx, rcx; Entry
0x140019615  mov     rcx, r8; Lookaside
0x140019618  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001961f  nop     dword ptr [rax+rax+00h]
0x140019624  jmp     short loc_140019635
0x140019626  mov     edx, [rcx+8]; Tag
0x140019629  call    cs:__imp_ExFreePoolWithTag
0x140019630  nop     dword ptr [rax+rax+00h]
0x140019635  mov     eax, ebx
0x140019637  add     rsp, 38h
0x14001963b  pop     rdi
0x14001963c  pop     rsi
0x14001963d  pop     rbp
0x14001963e  pop     rbx
0x14001963f  retn
```
