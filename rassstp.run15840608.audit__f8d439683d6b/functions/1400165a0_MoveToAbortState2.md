# MoveToAbortState2

- ea: `0x1400165a0`
- end: `0x14001672c`
- name: `MoveToAbortState2`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140015e70`
- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x1400165a0`
- `0x140016cf0`
- `0x140018054`
- `0x1400185f8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001668a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001668a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400166b5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400166b5`

## pseudocode

```c
void __fastcall MoveToAbortState2(__int64 a1, char a2, __int64 a3, int a4, char a5, __int64 a6)
{
  int v6; // ebp
  char v9; // cl
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  PVOID v13; // rax
  __int64 v14; // rdx
  __int16 v15; // [rsp+20h] [rbp-38h]

  v6 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v9 = *(_BYTE *)(a1 + 326);
  v10 = *(_DWORD *)(a1 + 24);
  if ( v9 )
    v11 = v10 - 6;
  else
    v11 = v10 - 14;
  if ( v11 > 2 )
  {
    LOBYTE(a4) = 1;
    v12 = v9 != 0 ? 6 : 14;
    *(_DWORD *)(a1 + 24) = v12;
    SstpTimerReschedule(a1 + 48, TimeoutInfo[2 * v12 + 1], a1, a4, TimeoutInfo[2 * v12], a5);
    if ( a2 )
    {
      v13 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
      if ( v13 )
      {
        GenerateSstpMessageWithStatus(5, 2, v6, (_DWORD)v13 + 18, v15, (__int64)v13 + 16);
        SendControlFrame(a1);
      }
      else
      {
        LOBYTE(v14) = a5;
        MoveToCallDisconnectedState(a1, v14, a6);
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x1400165a0  push    rbx
0x1400165a2  push    rbp
0x1400165a3  push    rsi
0x1400165a4  push    rdi
0x1400165a5  push    r15
0x1400165a7  sub     rsp, 30h
0x1400165ab  mov     ebp, r9d
0x1400165ae  mov     dil, dl
0x1400165b1  mov     rbx, rcx
0x1400165b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165bb  lea     r15, WPP_GLOBAL_Control
0x1400165c2  cmp     rcx, r15
0x1400165c5  jz      short loc_14001661D
0x1400165c7  mov     eax, [rcx+2Ch]
0x1400165ca  and     eax, 84h
0x1400165cf  cmp     al, 84h
0x1400165d1  jnz     short loc_1400165E8
0x1400165d3  mov     rcx, [rcx+18h]
0x1400165d7  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400165de  mov     edx, 34h ; '4'
0x1400165e3  call    WPP_SF_
0x1400165e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165ef  cmp     rcx, r15
0x1400165f2  jz      short loc_14001661D
0x1400165f4  mov     eax, [rcx+2Ch]
0x1400165f7  test    al, 4
0x1400165f9  jz      short loc_14001661D
0x1400165fb  cmp     byte ptr [rcx+29h], 3
0x1400165ff  jb      short loc_14001661D
0x140016601  mov     rcx, [rcx+18h]
0x140016605  lea     r9, [rbx+16Ch]
0x14001660c  mov     edx, 35h ; '5'
0x140016611  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016618  call    WPP_SF__guid_
0x14001661d  mov     cl, [rbx+146h]
0x140016623  mov     eax, [rbx+18h]
0x140016626  test    cl, cl
0x140016628  jz      loc_1400166C3
0x14001662e  add     eax, 0FFFFFFFAh
0x140016631  cmp     eax, 2
0x140016634  jbe     loc_1400166F3
0x14001663a  mov     sil, [rsp+58h+arg_20]
0x140016642  lea     r10, TimeoutInfo
0x140016649  neg     cl
0x14001664b  mov     byte ptr [rsp+58h+var_30], sil
0x140016650  lea     rcx, [rbx+30h]
0x140016654  mov     r9b, 1
0x140016657  sbb     eax, eax
0x140016659  mov     r8, rbx
0x14001665c  and     eax, 0FFFFFFF8h
0x14001665f  lea     edx, [rax+0Eh]
0x140016662  mov     [rbx+18h], edx
0x140016665  add     rdx, rdx
0x140016668  mov     eax, [r10+rdx*8]
0x14001666c  mov     rdx, [r10+rdx*8+8]
0x140016671  mov     dword ptr [rsp+58h+var_38], eax
0x140016675  call    SstpTimerReschedule
0x14001667a  test    dil, dil
0x14001667d  jz      short loc_1400166F3
0x14001667f  mov     rcx, cs:SstpFsmGlobalInfo
0x140016686  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14001668a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140016691  nop     dword ptr [rax+rax+00h]
0x140016696  mov     rdi, rax
0x140016699  test    rax, rax
0x14001669c  jnz     short loc_1400166CB
0x14001669e  mov     r8, [rsp+58h+arg_28]
0x1400166a6  mov     dl, sil
0x1400166a9  mov     rcx, rbx
0x1400166ac  call    MoveToCallDisconnectedState
0x1400166b1  lea     rcx, [rbx+10h]; SpinLock
0x1400166b5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400166bc  nop     dword ptr [rax+rax+00h]
0x1400166c1  jmp     short loc_1400166F3
0x1400166c3  add     eax, 0FFFFFFF2h
0x1400166c6  jmp     loc_140016631
0x1400166cb  mov     edx, 2
0x1400166d0  lea     r9, [rdi+12h]
0x1400166d4  add     rax, 10h
0x1400166d8  mov     r8d, ebp
0x1400166db  mov     [rsp+58h+var_30], rax
0x1400166e0  lea     ecx, [rdx+3]
0x1400166e3  call    GenerateSstpMessageWithStatus
0x1400166e8  mov     rdx, rdi
0x1400166eb  mov     rcx, rbx
0x1400166ee  call    SendControlFrame
0x1400166f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166fa  cmp     rcx, r15
0x1400166fd  jz      short loc_140016720
0x1400166ff  mov     eax, [rcx+2Ch]
0x140016702  and     eax, 84h
0x140016707  cmp     al, 84h
0x140016709  jnz     short loc_140016720
0x14001670b  mov     rcx, [rcx+18h]
0x14001670f  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016716  mov     edx, 36h ; '6'
0x14001671b  call    WPP_SF_
0x140016720  add     rsp, 30h
0x140016724  pop     r15
0x140016726  pop     rdi
0x140016727  pop     rsi
0x140016728  pop     rbp
0x140016729  pop     rbx
0x14001672a  retn
```
