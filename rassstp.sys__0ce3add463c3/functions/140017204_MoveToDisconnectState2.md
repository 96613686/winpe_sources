# MoveToDisconnectState2

- ea: `0x140017204`
- end: `0x14001737f`
- name: `MoveToDisconnectState2`
- size: `379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140016cf0`
- `0x140017204`
- `0x140018054`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400172f1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400172f1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017314`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140017314`

## pseudocode

```c
void __fastcall MoveToDisconnectState2(__int64 a1)
{
  char v2; // dl
  int v3; // ecx
  __int64 v4; // rdx
  _DWORD *v5; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v2 = *(_BYTE *)(a1 + 326);
  v3 = *(_DWORD *)(a1 + 24);
  if ( v2 )
  {
    if ( ((v3 - 5) & 0xFFFFFFFC) == 0 && v3 != 7 )
      goto LABEL_17;
LABEL_14:
    v4 = v2 != 0 ? 8 : 16;
    *(_DWORD *)(a1 + 24) = v4;
    SstpTimerReschedule(a1 + 48, TimeoutInfo[2 * v4 + 1], a1, 1, TimeoutInfo[2 * v4], 0);
    v5 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
    if ( v5 )
    {
      v5[4] = 17825800;
      *((_WORD *)v5 + 11) = 1792;
      *((_WORD *)v5 + 12) = 0;
      *((_WORD *)v5 + 10) = __ROR2__(*((_WORD *)v5 + 8), 8);
      SendControlFrame(a1);
    }
    else
    {
      MoveToCallDisconnectedState(a1, 0, 0);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    }
    goto LABEL_17;
  }
  if ( ((v3 - 13) & 0xFFFFFFFC) != 0 || v3 == 15 )
    goto LABEL_14;
LABEL_17:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140017204  mov     [rsp+arg_0], rbx
0x140017209  push    rsi
0x14001720a  sub     rsp, 30h
0x14001720e  mov     rbx, rcx
0x140017211  mov     rcx, cs:WPP_GLOBAL_Control
0x140017218  lea     rsi, WPP_GLOBAL_Control
0x14001721f  cmp     rcx, rsi
0x140017222  jz      short loc_14001727A
0x140017224  mov     eax, [rcx+2Ch]
0x140017227  and     eax, 84h
0x14001722c  cmp     al, 84h
0x14001722e  jnz     short loc_140017245
0x140017230  mov     rcx, [rcx+18h]
0x140017234  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001723b  mov     edx, 4Ch ; 'L'
0x140017240  call    WPP_SF_
0x140017245  mov     rcx, cs:WPP_GLOBAL_Control
0x14001724c  cmp     rcx, rsi
0x14001724f  jz      short loc_14001727A
0x140017251  mov     eax, [rcx+2Ch]
0x140017254  test    al, 4
0x140017256  jz      short loc_14001727A
0x140017258  cmp     byte ptr [rcx+29h], 3
0x14001725c  jb      short loc_14001727A
0x14001725e  mov     rcx, [rcx+18h]
0x140017262  lea     r9, [rbx+16Ch]
0x140017269  mov     edx, 4Dh ; 'M'
0x14001726e  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140017275  call    WPP_SF__guid_
0x14001727a  mov     dl, [rbx+146h]
0x140017280  mov     ecx, [rbx+18h]
0x140017283  test    dl, dl
0x140017285  jz      short loc_14001729B
0x140017287  lea     eax, [rcx-5]
0x14001728a  test    eax, 0FFFFFFFCh
0x14001728f  jnz     short loc_1400172AE
0x140017291  cmp     ecx, 7
0x140017294  jz      short loc_1400172AE
0x140017296  jmp     loc_140017346
0x14001729b  lea     eax, [rcx-0Dh]
0x14001729e  test    eax, 0FFFFFFFCh
0x1400172a3  jnz     short loc_1400172AE
0x1400172a5  cmp     ecx, 0Fh
0x1400172a8  jnz     loc_140017346
0x1400172ae  neg     dl
0x1400172b0  mov     [rsp+38h+var_10], 0
0x1400172b5  lea     r10, TimeoutInfo
0x1400172bc  mov     r9b, 1
0x1400172bf  sbb     eax, eax
0x1400172c1  lea     rcx, [rbx+30h]
0x1400172c5  and     eax, 0FFFFFFF8h
0x1400172c8  mov     r8, rbx
0x1400172cb  lea     edx, [rax+10h]
0x1400172ce  mov     [rbx+18h], edx
0x1400172d1  add     rdx, rdx
0x1400172d4  mov     eax, [r10+rdx*8]
0x1400172d8  mov     rdx, [r10+rdx*8+8]
0x1400172dd  mov     [rsp+38h+var_18], eax
0x1400172e1  call    SstpTimerReschedule
0x1400172e6  mov     rcx, cs:SstpFsmGlobalInfo
0x1400172ed  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400172f1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400172f8  nop     dword ptr [rax+rax+00h]
0x1400172fd  mov     rdx, rax
0x140017300  mov     rcx, rbx
0x140017303  test    rax, rax
0x140017306  jnz     short loc_140017322
0x140017308  xor     r8d, r8d
0x14001730b  call    MoveToCallDisconnectedState
0x140017310  lea     rcx, [rbx+10h]; SpinLock
0x140017314  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001731b  nop     dword ptr [rax+rax+00h]
0x140017320  jmp     short loc_140017346
0x140017322  mov     dword ptr [rax+10h], 1100008h
0x140017329  mov     word ptr [rax+16h], 700h
0x14001732f  xor     eax, eax
0x140017331  mov     [rdx+18h], ax
0x140017335  movzx   eax, word ptr [rdx+10h]
0x140017339  ror     ax, 8
0x14001733d  mov     [rdx+14h], ax
0x140017341  call    SendControlFrame
0x140017346  mov     rcx, cs:WPP_GLOBAL_Control
0x14001734d  cmp     rcx, rsi
0x140017350  jz      short loc_140017373
0x140017352  mov     eax, [rcx+2Ch]
0x140017355  and     eax, 84h
0x14001735a  cmp     al, 84h
0x14001735c  jnz     short loc_140017373
0x14001735e  mov     rcx, [rcx+18h]
0x140017362  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140017369  mov     edx, 4Eh ; 'N'
0x14001736e  call    WPP_SF_
0x140017373  mov     rbx, [rsp+38h+arg_0]
0x140017378  add     rsp, 30h
0x14001737c  pop     rsi
0x14001737d  retn
```
