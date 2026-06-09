# MoveToCallConnectPendingState

- ea: `0x140016734`
- end: `0x1400168be`
- name: `MoveToCallConnectPendingState`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140005ef0`
- `0x140016734`
- `0x140016cf0`
- `0x140018054`
- `0x140018480`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400167ba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400167ba`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016874`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016874`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001684b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001684b`

## pseudocode

```c
void __fastcall MoveToCallConnectPendingState(__int64 a1)
{
  int v2; // edx
  PVOID v3; // rbx
  int v4; // r9d
  int v5; // r9d

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v3 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
  if ( v3 )
  {
    LOBYTE(v4) = *(_BYTE *)(a1 + 176);
    GenerateSstpConnectionAck((_DWORD)v3 + 18, v2, (_DWORD)v3 + 16, v4, a1 + 144);
    SendControlFrame(a1);
    *(_DWORD *)(a1 + 24) = 11;
    LOBYTE(v5) = 1;
    SstpTimerReschedule(a1 + 48, (_DWORD)off_14000A0B8, a1, v5, dword_14000A0B0, 0);
    if ( !*(_BYTE *)(a1 + 176) )
      goto LABEL_13;
    *(_BYTE *)(a1 + 325) = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
    (*((void (__fastcall **)(_QWORD, _QWORD))SstpFsmGlobalInfo + 12))(*(_QWORD *)(a1 + 136), 0);
  }
  else
  {
    MoveToCallDisconnectedState(a1, 0, 0);
  }
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140016734  mov     [rsp+arg_0], rbx
0x140016739  mov     [rsp+arg_8], rbp
0x14001673e  push    rdi
0x14001673f  sub     rsp, 30h
0x140016743  mov     rdi, rcx
0x140016746  mov     rcx, cs:WPP_GLOBAL_Control
0x14001674d  lea     rbp, WPP_GLOBAL_Control
0x140016754  cmp     rcx, rbp
0x140016757  jz      short loc_1400167AF
0x140016759  mov     eax, [rcx+2Ch]
0x14001675c  and     eax, 84h
0x140016761  cmp     al, 84h
0x140016763  jnz     short loc_14001677A
0x140016765  mov     rcx, [rcx+18h]
0x140016769  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016770  mov     edx, 52h ; 'R'
0x140016775  call    WPP_SF_
0x14001677a  mov     rcx, cs:WPP_GLOBAL_Control
0x140016781  cmp     rcx, rbp
0x140016784  jz      short loc_1400167AF
0x140016786  mov     eax, [rcx+2Ch]
0x140016789  test    al, 4
0x14001678b  jz      short loc_1400167AF
0x14001678d  cmp     byte ptr [rcx+29h], 3
0x140016791  jb      short loc_1400167AF
0x140016793  mov     rcx, [rcx+18h]
0x140016797  lea     r9, [rdi+16Ch]
0x14001679e  mov     edx, 53h ; 'S'
0x1400167a3  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400167aa  call    WPP_SF__guid_
0x1400167af  mov     rcx, cs:SstpFsmGlobalInfo
0x1400167b6  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400167ba  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400167c1  nop     dword ptr [rax+rax+00h]
0x1400167c6  mov     rbx, rax
0x1400167c9  test    rax, rax
0x1400167cc  jnz     short loc_1400167E0
0x1400167ce  xor     r8d, r8d
0x1400167d1  xor     edx, edx
0x1400167d3  mov     rcx, rdi
0x1400167d6  call    MoveToCallDisconnectedState
0x1400167db  jmp     loc_140016870
0x1400167e0  mov     r9b, [rdi+0B0h]
0x1400167e7  lea     rax, [rdi+90h]
0x1400167ee  lea     r8, [rbx+10h]
0x1400167f2  mov     [rsp+38h+var_18], rax
0x1400167f7  lea     rcx, [rbx+12h]
0x1400167fb  call    GenerateSstpConnectionAck
0x140016800  mov     rdx, rbx
0x140016803  mov     rcx, rdi
0x140016806  call    SendControlFrame
0x14001680b  mov     dword ptr [rdi+18h], 0Bh
0x140016812  lea     rcx, [rdi+30h]
0x140016816  mov     eax, cs:dword_14000A0B0
0x14001681c  mov     r9b, 1
0x14001681f  mov     rdx, cs:off_14000A0B8
0x140016826  mov     r8, rdi
0x140016829  mov     [rsp+38h+var_10], 0
0x14001682e  mov     dword ptr [rsp+38h+var_18], eax
0x140016832  call    SstpTimerReschedule
0x140016837  cmp     byte ptr [rdi+0B0h], 0
0x14001683e  jz      short loc_140016880
0x140016840  lea     rcx, [rdi+10h]; SpinLock
0x140016844  mov     byte ptr [rdi+145h], 0
0x14001684b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016852  nop     dword ptr [rax+rax+00h]
0x140016857  mov     rax, cs:SstpFsmGlobalInfo
0x14001685e  xor     edx, edx
0x140016860  mov     rcx, [rdi+88h]
0x140016867  mov     rax, [rax+60h]
0x14001686b  call    _guard_dispatch_icall
0x140016870  lea     rcx, [rdi+10h]; SpinLock
0x140016874  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001687b  nop     dword ptr [rax+rax+00h]
0x140016880  mov     rcx, cs:WPP_GLOBAL_Control
0x140016887  cmp     rcx, rbp
0x14001688a  jz      short loc_1400168AD
0x14001688c  mov     eax, [rcx+2Ch]
0x14001688f  and     eax, 84h
0x140016894  cmp     al, 84h
0x140016896  jnz     short loc_1400168AD
0x140016898  mov     rcx, [rcx+18h]
0x14001689c  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400168a3  mov     edx, 54h ; 'T'
0x1400168a8  call    WPP_SF_
0x1400168ad  mov     rbx, [rsp+38h+arg_0]
0x1400168b2  mov     rbp, [rsp+38h+arg_8]
0x1400168b7  add     rsp, 30h
0x1400168bb  pop     rdi
0x1400168bc  retn
```
