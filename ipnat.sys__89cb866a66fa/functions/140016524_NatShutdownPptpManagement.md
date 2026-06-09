# NatShutdownPptpManagement

- ea: `0x140016524`
- end: `0x1400166c5`
- name: `NatShutdownPptpManagement`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140007ca0`

## callees

- `0x14000218c`
- `0x140006e18`
- `0x140016524`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140016680`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140016680`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001666d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001666d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001656a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001656a`

## pseudocode

```c
void NatShutdownPptpManagement()
{
  KIRQL v0; // al
  __int64 v1; // r8
  KIRQL v2; // di
  __int64 *v3; // rbx
  __int64 **v4; // rax
  _DWORD *v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // rax
  PVOID v8; // rdx
  _QWORD *v9; // rcx
  PVOID *v10; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  v0 = KeAcquireSpinLockRaiseToDpc(&PptpMappingLock);
  v1 = qword_1400320D0;
  v2 = v0;
  if ( (__int64 *)qword_1400320D0 != &qword_1400320D0 )
  {
    do
    {
      v3 = *(__int64 **)v1;
      if ( (*(_DWORD *)(v1 - 16 + 56) & 1) != 0 )
      {
        if ( v3[1] != v1 || (v4 = *(__int64 ***)(v1 + 8), *v4 != (__int64 *)v1) )
LABEL_21:
          __fastfail(3u);
        *v4 = v3;
        v3[1] = (__int64)v4;
        NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, (PVOID)(v1 - 16), 72);
      }
      v1 = (__int64)v3;
    }
    while ( v3 != &qword_1400320D0 );
  }
  v5 = PptpMappingList;
  if ( PptpMappingList == &PptpMappingList )
    goto LABEL_17;
  do
  {
    v6 = *(_QWORD *)v5;
    if ( (v5[14] & 1) != 0 )
    {
      if ( *(_DWORD **)(v6 + 8) != v5 )
        goto LABEL_21;
      v7 = (_QWORD *)*((_QWORD *)v5 + 1);
      if ( (_DWORD *)*v7 != v5 )
        goto LABEL_21;
      *v7 = v6;
      *(_QWORD *)(v6 + 8) = v7;
      NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, v5, 72);
    }
    v5 = (_DWORD *)v6;
  }
  while ( (PVOID *)v6 != &PptpMappingList );
LABEL_17:
  while ( 1 )
  {
    v8 = PptpMappingList;
    if ( PptpMappingList == &PptpMappingList )
      break;
    v9 = *(_QWORD **)PptpMappingList;
    if ( *(PVOID *)(*(_QWORD *)PptpMappingList + 8LL) != PptpMappingList )
      goto LABEL_21;
    v10 = (PVOID *)*((_QWORD *)PptpMappingList + 1);
    if ( *v10 != PptpMappingList )
      goto LABEL_21;
    *v10 = v9;
    v9[1] = v10;
    NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, v8, 72);
  }
  KeReleaseSpinLock(&PptpMappingLock, v2);
  ExDeleteNPagedLookasideList(&PptpLookasideList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
}

```

## disassembly

```asm
0x140016524  push    rbx
0x140016526  push    rbp
0x140016527  push    rdi
0x140016528  push    r15
0x14001652a  sub     rsp, 28h
0x14001652e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016535  lea     r15, WPP_GLOBAL_Control
0x14001653c  cmp     rcx, r15
0x14001653f  jz      short loc_140016563
0x140016541  mov     eax, [rcx+2Ch]
0x140016544  test    al, 1
0x140016546  jz      short loc_140016563
0x140016548  cmp     byte ptr [rcx+29h], 6
0x14001654c  jb      short loc_140016563
0x14001654e  mov     rcx, [rcx+18h]
0x140016552  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x140016559  mov     edx, 6Eh ; 'n'
0x14001655e  call    WPP_SF_
0x140016563  lea     rcx, PptpMappingLock; SpinLock
0x14001656a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016571  nop     dword ptr [rax+rax+00h]
0x140016576  mov     r8, cs:qword_1400320D0
0x14001657d  lea     rbp, qword_1400320D0
0x140016584  mov     dil, al
0x140016587  cmp     r8, rbp
0x14001658a  jz      short loc_1400165D3
0x14001658c  mov     rbx, [r8]
0x14001658f  lea     rdx, [r8-10h]; Entry
0x140016593  mov     ecx, [rdx+38h]
0x140016596  test    cl, 1
0x140016599  jz      short loc_1400165CB
0x14001659b  cmp     [rbx+8], r8
0x14001659f  jnz     loc_14001665C
0x1400165a5  mov     rax, [r8+8]
0x1400165a9  cmp     [rax], r8
0x1400165ac  jnz     loc_14001665C
0x1400165b2  mov     [rax], rbx
0x1400165b5  lea     rcx, PptpLookasideList; Lookaside
0x1400165bc  mov     r8d, 48h ; 'H'
0x1400165c2  mov     [rbx+8], rax
0x1400165c6  call    NatFreeBlockAndUpdateStateAllocationUsage
0x1400165cb  mov     r8, rbx
0x1400165ce  cmp     rbx, rbp
0x1400165d1  jnz     short loc_14001658C
0x1400165d3  mov     rcx, cs:PptpMappingList
0x1400165da  lea     rbp, PptpMappingList
0x1400165e1  cmp     rcx, rbp
0x1400165e4  jz      short loc_140016623
0x1400165e6  mov     eax, [rcx+38h]
0x1400165e9  mov     rbx, [rcx]
0x1400165ec  test    al, 1
0x1400165ee  jz      short loc_14001661B
0x1400165f0  cmp     [rbx+8], rcx
0x1400165f4  jnz     short loc_14001665C
0x1400165f6  mov     rax, [rcx+8]
0x1400165fa  cmp     [rax], rcx
0x1400165fd  jnz     short loc_14001665C
0x1400165ff  mov     rdx, rcx; Entry
0x140016602  mov     [rax], rbx
0x140016605  lea     rcx, PptpLookasideList; Lookaside
0x14001660c  mov     [rbx+8], rax
0x140016610  mov     r8d, 48h ; 'H'
0x140016616  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14001661b  mov     rcx, rbx
0x14001661e  cmp     rbx, rbp
0x140016621  jnz     short loc_1400165E6
0x140016623  mov     rdx, cs:PptpMappingList; Entry
0x14001662a  cmp     rdx, rbp
0x14001662d  jz      short loc_140016663
0x14001662f  mov     rcx, [rdx]
0x140016632  cmp     [rcx+8], rdx
0x140016636  jnz     short loc_14001665C
0x140016638  mov     rax, [rdx+8]
0x14001663c  cmp     [rax], rdx
0x14001663f  jnz     short loc_14001665C
0x140016641  mov     [rax], rcx
0x140016644  mov     r8d, 48h ; 'H'
0x14001664a  mov     [rcx+8], rax
0x14001664e  lea     rcx, PptpLookasideList; Lookaside
0x140016655  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14001665a  jmp     short loc_140016623
0x14001665c  mov     ecx, 3
0x140016661  int     29h; Win8: RtlFailFast(ecx)
0x140016663  mov     dl, dil; NewIrql
0x140016666  lea     rcx, PptpMappingLock; SpinLock
0x14001666d  call    cs:__imp_KeReleaseSpinLock
0x140016674  nop     dword ptr [rax+rax+00h]
0x140016679  lea     rcx, PptpLookasideList; Lookaside
0x140016680  call    cs:__imp_ExDeleteNPagedLookasideList
0x140016687  nop     dword ptr [rax+rax+00h]
0x14001668c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016693  cmp     rcx, r15
0x140016696  jz      short loc_1400166BA
0x140016698  mov     eax, [rcx+2Ch]
0x14001669b  test    al, 1
0x14001669d  jz      short loc_1400166BA
0x14001669f  cmp     byte ptr [rcx+29h], 6
0x1400166a3  jb      short loc_1400166BA
0x1400166a5  mov     rcx, [rcx+18h]
0x1400166a9  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x1400166b0  mov     edx, 6Fh ; 'o'
0x1400166b5  call    WPP_SF_
0x1400166ba  add     rsp, 28h
0x1400166be  pop     r15
0x1400166c0  pop     rdi
0x1400166c1  pop     rbp
0x1400166c2  pop     rbx
0x1400166c3  retn
```
