# MoveToDisconnectState1

- ea: `0x14001707c`
- end: `0x1400171fe`
- name: `MoveToDisconnectState1`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140014ef0`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140016cf0`
- `0x14001707c`
- `0x140018054`
- `0x1400185f8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017161`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017161`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017186`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017186`

## pseudocode

```c
void __fastcall MoveToDisconnectState1(__int64 a1)
{
  char v2; // cl
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  PVOID v6; // rax
  __int16 v7; // [rsp+20h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v2 = *(_BYTE *)(a1 + 326);
  v3 = *(_DWORD *)(a1 + 24);
  if ( v2 )
    v4 = v3 - 5;
  else
    v4 = v3 - 13;
  if ( v4 > 3 )
  {
    *(_DWORD *)(a1 + 316) = 0;
    v5 = v2 != 0 ? 7 : 15;
    *(_DWORD *)(a1 + 24) = v5;
    SstpTimerReschedule(a1 + 48, TimeoutInfo[2 * v5 + 1], a1, 1, TimeoutInfo[2 * v5], 0);
    v6 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
    if ( v6 )
    {
      GenerateSstpMessageWithStatus(6, 0, 0, (_DWORD)v6 + 18, v7, (__int64)v6 + 16);
      SendControlFrame(a1);
    }
    else
    {
      MoveToCallDisconnectedState(a1, 0, 0);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x14001707c  mov     [rsp+arg_0], rbx
0x140017081  mov     [rsp+arg_8], rbp
0x140017086  push    rdi
0x140017087  sub     rsp, 30h
0x14001708b  mov     rbx, rcx
0x14001708e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017095  lea     rbp, WPP_GLOBAL_Control
0x14001709c  cmp     rcx, rbp
0x14001709f  jz      short loc_1400170F7
0x1400170a1  mov     eax, [rcx+2Ch]
0x1400170a4  and     eax, 84h
0x1400170a9  cmp     al, 84h
0x1400170ab  jnz     short loc_1400170C2
0x1400170ad  mov     rcx, [rcx+18h]
0x1400170b1  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400170b8  mov     edx, 49h ; 'I'
0x1400170bd  call    WPP_SF_
0x1400170c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170c9  cmp     rcx, rbp
0x1400170cc  jz      short loc_1400170F7
0x1400170ce  mov     eax, [rcx+2Ch]
0x1400170d1  test    al, 4
0x1400170d3  jz      short loc_1400170F7
0x1400170d5  cmp     byte ptr [rcx+29h], 3
0x1400170d9  jb      short loc_1400170F7
0x1400170db  mov     rcx, [rcx+18h]
0x1400170df  lea     r9, [rbx+16Ch]
0x1400170e6  mov     edx, 4Ah ; 'J'
0x1400170eb  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400170f2  call    WPP_SF__guid_
0x1400170f7  mov     cl, [rbx+146h]
0x1400170fd  mov     eax, [rbx+18h]
0x140017100  test    cl, cl
0x140017102  jz      loc_140017194
0x140017108  add     eax, 0FFFFFFFBh
0x14001710b  cmp     eax, 3
0x14001710e  jbe     loc_1400171C0
0x140017114  neg     cl
0x140017116  mov     dword ptr [rbx+13Ch], 0
0x140017120  lea     r10, TimeoutInfo
0x140017127  mov     byte ptr [rsp+38h+var_10], 0
0x14001712c  sbb     eax, eax
0x14001712e  lea     rcx, [rbx+30h]
0x140017132  and     eax, 0FFFFFFF8h
0x140017135  mov     r9b, 1
0x140017138  mov     r8, rbx
0x14001713b  lea     edx, [rax+0Fh]
0x14001713e  mov     [rbx+18h], edx
0x140017141  add     rdx, rdx
0x140017144  mov     eax, [r10+rdx*8]
0x140017148  mov     rdx, [r10+rdx*8+8]
0x14001714d  mov     dword ptr [rsp+38h+var_18], eax
0x140017151  call    SstpTimerReschedule
0x140017156  mov     rcx, cs:SstpFsmGlobalInfo
0x14001715d  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140017161  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140017168  nop     dword ptr [rax+rax+00h]
0x14001716d  xor     edx, edx
0x14001716f  mov     rdi, rax
0x140017172  test    rax, rax
0x140017175  jnz     short loc_14001719C
0x140017177  xor     r8d, r8d
0x14001717a  mov     rcx, rbx
0x14001717d  call    MoveToCallDisconnectedState
0x140017182  lea     rcx, [rbx+10h]; SpinLock
0x140017186  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001718d  nop     dword ptr [rax+rax+00h]
0x140017192  jmp     short loc_1400171C0
0x140017194  add     eax, 0FFFFFFF3h
0x140017197  jmp     loc_14001710B
0x14001719c  xor     r8d, r8d
0x14001719f  lea     r9, [rdi+12h]
0x1400171a3  add     rax, 10h
0x1400171a7  mov     [rsp+38h+var_10], rax
0x1400171ac  lea     ecx, [r8+6]
0x1400171b0  call    GenerateSstpMessageWithStatus
0x1400171b5  mov     rdx, rdi
0x1400171b8  mov     rcx, rbx
0x1400171bb  call    SendControlFrame
0x1400171c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171c7  cmp     rcx, rbp
0x1400171ca  jz      short loc_1400171ED
0x1400171cc  mov     eax, [rcx+2Ch]
0x1400171cf  and     eax, 84h
0x1400171d4  cmp     al, 84h
0x1400171d6  jnz     short loc_1400171ED
0x1400171d8  mov     rcx, [rcx+18h]
0x1400171dc  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400171e3  mov     edx, 4Bh ; 'K'
0x1400171e8  call    WPP_SF_
0x1400171ed  mov     rbx, [rsp+38h+arg_0]
0x1400171f2  mov     rbp, [rsp+38h+arg_8]
0x1400171f7  add     rsp, 30h
0x1400171fb  pop     rdi
0x1400171fc  retn
```
