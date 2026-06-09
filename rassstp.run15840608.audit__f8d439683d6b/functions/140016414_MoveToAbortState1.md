# MoveToAbortState1

- ea: `0x140016414`
- end: `0x14001659a`
- name: `MoveToAbortState1`
- size: `390`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400148f0`
- `0x1400149c0`
- `0x140014b60`
- `0x140017388`
- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140016414`
- `0x140016cf0`
- `0x140018054`
- `0x1400185f8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400164f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400164f6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016521`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016521`

## pseudocode

```c
void __fastcall MoveToAbortState1(__int64 a1, int a2, int a3, char a4, __int64 a5)
{
  char v9; // cl
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  PVOID v13; // rax
  __int64 v14; // rdx
  __int16 v15; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v9 = *(_BYTE *)(a1 + 326);
  v10 = *(_DWORD *)(a1 + 24);
  if ( v9 )
    v11 = v10 - 5;
  else
    v11 = v10 - 13;
  if ( v11 > 3 )
  {
    v12 = v9 != 0 ? 5 : 13;
    *(_DWORD *)(a1 + 24) = v12;
    SstpTimerReschedule(a1 + 48, TimeoutInfo[2 * v12 + 1], a1, 1, TimeoutInfo[2 * v12], a4);
    v13 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
    if ( v13 )
    {
      GenerateSstpMessageWithStatus(5, a2, a3, (_DWORD)v13 + 18, v15, (__int64)v13 + 16);
      SendControlFrame(a1);
    }
    else
    {
      LOBYTE(v14) = a4;
      MoveToCallDisconnectedState(a1, v14, a5);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140016414  push    rbx
0x140016416  push    rbp
0x140016417  push    rsi
0x140016418  push    rdi
0x140016419  push    r12
0x14001641b  push    r14
0x14001641d  sub     rsp, 38h
0x140016421  mov     sil, r9b
0x140016424  mov     ebp, r8d
0x140016427  mov     r14d, edx
0x14001642a  mov     rbx, rcx
0x14001642d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016434  lea     r12, WPP_GLOBAL_Control
0x14001643b  cmp     rcx, r12
0x14001643e  jz      short loc_140016496
0x140016440  mov     eax, [rcx+2Ch]
0x140016443  and     eax, 84h
0x140016448  cmp     al, 84h
0x14001644a  jnz     short loc_140016461
0x14001644c  mov     rcx, [rcx+18h]
0x140016450  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016457  mov     edx, 31h ; '1'
0x14001645c  call    WPP_SF_
0x140016461  mov     rcx, cs:WPP_GLOBAL_Control
0x140016468  cmp     rcx, r12
0x14001646b  jz      short loc_140016496
0x14001646d  mov     eax, [rcx+2Ch]
0x140016470  test    al, 4
0x140016472  jz      short loc_140016496
0x140016474  cmp     byte ptr [rcx+29h], 3
0x140016478  jb      short loc_140016496
0x14001647a  mov     rcx, [rcx+18h]
0x14001647e  lea     r9, [rbx+16Ch]
0x140016485  mov     edx, 32h ; '2'
0x14001648a  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016491  call    WPP_SF__guid_
0x140016496  mov     cl, [rbx+146h]
0x14001649c  mov     eax, [rbx+18h]
0x14001649f  test    cl, cl
0x1400164a1  jz      loc_14001652F
0x1400164a7  add     eax, 0FFFFFFFBh
0x1400164aa  cmp     eax, 3
0x1400164ad  jbe     loc_14001655F
0x1400164b3  neg     cl
0x1400164b5  mov     byte ptr [rsp+68h+var_40], sil
0x1400164ba  lea     r10, TimeoutInfo
0x1400164c1  mov     r9b, 1
0x1400164c4  sbb     eax, eax
0x1400164c6  lea     rcx, [rbx+30h]
0x1400164ca  and     eax, 0FFFFFFF8h
0x1400164cd  mov     r8, rbx
0x1400164d0  lea     edx, [rax+0Dh]
0x1400164d3  mov     [rbx+18h], edx
0x1400164d6  add     rdx, rdx
0x1400164d9  mov     eax, [r10+rdx*8]
0x1400164dd  mov     rdx, [r10+rdx*8+8]
0x1400164e2  mov     dword ptr [rsp+68h+var_48], eax
0x1400164e6  call    SstpTimerReschedule
0x1400164eb  mov     rcx, cs:SstpFsmGlobalInfo
0x1400164f2  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400164f6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400164fd  nop     dword ptr [rax+rax+00h]
0x140016502  mov     rdi, rax
0x140016505  test    rax, rax
0x140016508  jnz     short loc_140016537
0x14001650a  mov     r8, [rsp+68h+arg_20]
0x140016512  mov     dl, sil
0x140016515  mov     rcx, rbx
0x140016518  call    MoveToCallDisconnectedState
0x14001651d  lea     rcx, [rbx+10h]; SpinLock
0x140016521  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016528  nop     dword ptr [rax+rax+00h]
0x14001652d  jmp     short loc_14001655F
0x14001652f  add     eax, 0FFFFFFF3h
0x140016532  jmp     loc_1400164AA
0x140016537  add     rax, 10h
0x14001653b  lea     r9, [rdi+12h]
0x14001653f  mov     r8d, ebp
0x140016542  mov     [rsp+68h+var_40], rax
0x140016547  mov     edx, r14d
0x14001654a  mov     ecx, 5
0x14001654f  call    GenerateSstpMessageWithStatus
0x140016554  mov     rdx, rdi
0x140016557  mov     rcx, rbx
0x14001655a  call    SendControlFrame
0x14001655f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016566  cmp     rcx, r12
0x140016569  jz      short loc_14001658C
0x14001656b  mov     eax, [rcx+2Ch]
0x14001656e  and     eax, 84h
0x140016573  cmp     al, 84h
0x140016575  jnz     short loc_14001658C
0x140016577  mov     rcx, [rcx+18h]
0x14001657b  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016582  mov     edx, 33h ; '3'
0x140016587  call    WPP_SF_
0x14001658c  add     rsp, 38h
0x140016590  pop     r14
0x140016592  pop     r12
0x140016594  pop     rdi
0x140016595  pop     rsi
0x140016596  pop     rbp
0x140016597  pop     rbx
0x140016598  retn
```
