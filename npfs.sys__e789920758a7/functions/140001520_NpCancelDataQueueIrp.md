# NpCancelDataQueueIrp

- ea: `0x140001520`
- end: `0x140001726`
- name: `NpCancelDataQueueIrp`
- size: `518`
- prototype: `_OWORD *__fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000deb8`

## callees

- `0x140001520`
- `0x14000fb00`
- `0x140010290`
- `0x1400113b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000165e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000165e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001589`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001589`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000159b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000159b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000163c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000163c`
- `ntoskrnl!IofCompleteRequest` at `0x14000167e`
- `ntoskrnl!IofCompleteRequest` at `0x14000169d`
- `ntoskrnl!IofCompleteRequest` at `0x14000167e`
- `ntoskrnl!IofCompleteRequest` at `0x14000169d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001648`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001648`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001547`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001547`

## pseudocode

```c
_OWORD *__fastcall NpCancelDataQueueIrp(__int64 a1, IRP *a2)
{
  char *v4; // r13
  PVOID v5; // rbx
  unsigned __int64 v6; // r14
  __int64 v7; // r8
  __int64 v8; // r9
  PVOID v9; // rdi
  int v10; // ebp
  char v11; // dl
  PVOID v12; // rax
  PVOID *v13; // rcx
  int v14; // ecx
  bool v15; // r12
  void *v16; // rbx
  _OWORD *v17; // rbx
  IRP *v18; // rcx
  _OWORD *result; // rax
  _OWORD v20[5]; // [rsp+20h] [rbp-58h] BYREF

  v20[0] = 0;
  if ( a1 )
    IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = 0;
  *((_QWORD *)&v20[0] + 1) = v20;
  *(_QWORD *)&v20[0] = v20;
  v5 = a2->Tail.Overlay.DriverContext[2];
  v6 = (unsigned __int64)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( a1 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v6 + 64, 0, v7, v8);
  }
  v9 = a2->Tail.Overlay.DriverContext[3];
  v10 = 1;
  if ( v9 )
  {
    if ( *((PVOID *)v9 + 1) == v5 )
    {
      *((_DWORD *)v5 + 9) = 0;
      v11 = 1;
    }
    else
    {
      v11 = 0;
    }
    v12 = *(PVOID *)v9;
    if ( *(PVOID *)(*(_QWORD *)v9 + 8LL) != v9 || (v13 = (PVOID *)*((_QWORD *)v9 + 1), *v13 != v9) )
      __fastfail(3u);
    *v13 = v12;
    *((_QWORD *)v12 + 1) = v13;
    v14 = *((_DWORD *)v9 + 10);
    v4 = (char *)*((_QWORD *)v9 + 3);
    v15 = *((_DWORD *)v5 + 4) == 1 && *((_DWORD *)v5 + 8) >= *((_DWORD *)v5 + 7) && *((_DWORD *)v9 + 9);
    *((_DWORD *)v5 + 8) -= *((_DWORD *)v9 + 9);
    *((_DWORD *)v5 + 5) -= v14;
    --*((_DWORD *)v5 + 6);
    if ( *(PVOID *)v5 == v5 )
    {
      *((_DWORD *)v5 + 4) = 2;
    }
    else
    {
      if ( v11 )
        NpGetNextRealDataQueueEntry(v5, v20);
      if ( v15 )
        NpCompleteStalledWrites(v5, v20);
    }
  }
  if ( *((PVOID *)v5 + 5) == v9 )
    _interlockedbittestandset((volatile signed __int32 *)v5 + 10, 0);
  else
    v10 = 0;
  v16 = 0;
  if ( !v10 )
    v16 = v9;
  if ( a1 )
  {
    ExReleasePushLockExclusiveEx(v6 + 64, 0);
    KeLeaveCriticalRegion();
  }
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  NpFreeClientSecurityContext(v4);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
  v17 = *(_OWORD **)&v20[0];
  while ( 1 )
  {
    result = v20;
    if ( v17 == v20 )
      break;
    v18 = (IRP *)((char *)v17 - 168);
    v17 = *(_OWORD **)v17;
    IofCompleteRequest(v18, 2);
  }
  return result;
}

```

## disassembly

```asm
0x140001520  push    rbx
0x140001522  push    rbp
0x140001523  push    rsi
0x140001524  push    rdi
0x140001525  push    r12
0x140001527  push    r13
0x140001529  push    r14
0x14000152b  push    r15
0x14000152d  sub     rsp, 38h
0x140001531  xorps   xmm0, xmm0
0x140001534  mov     rsi, rdx
0x140001537  mov     r15, rcx
0x14000153a  movups  [rsp+78h+var_58], xmm0
0x14000153f  test    rcx, rcx
0x140001542  jz      short loc_140001553
0x140001544  mov     cl, [rdx+45h]; Irql
0x140001547  call    cs:__imp_IoReleaseCancelSpinLock
0x14000154e  nop     dword ptr [rax+rax+00h]
0x140001553  lea     rax, [rsp+78h+var_58]
0x140001558  xor     r13d, r13d
0x14000155b  mov     qword ptr [rsp+78h+var_58+8], rax
0x140001560  lea     rax, [rsp+78h+var_58]
0x140001565  mov     qword ptr [rsp+78h+var_58], rax
0x14000156a  mov     rax, [rsi+0B8h]
0x140001571  mov     rcx, [rax+30h]
0x140001575  mov     r14, [rcx+20h]
0x140001579  mov     rbx, [rsi+88h]
0x140001580  and     r14, 0FFFFFFFFFFFFFFFCh
0x140001584  test    r15, r15
0x140001587  jz      short loc_1400015A7
0x140001589  call    cs:__imp_KeEnterCriticalRegion
0x140001590  nop     dword ptr [rax+rax+00h]
0x140001595  lea     rcx, [r14+40h]
0x140001599  xor     edx, edx
0x14000159b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400015a2  nop     dword ptr [rax+rax+00h]
0x1400015a7  mov     rdi, [rsi+90h]
0x1400015ae  mov     ebp, 1
0x1400015b3  test    rdi, rdi
0x1400015b6  jz      short loc_140001619
0x1400015b8  cmp     [rdi+8], rbx
0x1400015bc  jnz     loc_1400016EB
0x1400015c2  mov     [rbx+24h], r13d
0x1400015c6  mov     dl, bpl
0x1400015c9  mov     rax, [rdi]
0x1400015cc  cmp     [rax+8], rdi
0x1400015d0  jnz     loc_1400016F2
0x1400015d6  mov     rcx, [rdi+8]
0x1400015da  cmp     [rcx], rdi
0x1400015dd  jnz     loc_1400016F2
0x1400015e3  mov     [rcx], rax
0x1400015e6  mov     [rax+8], rcx
0x1400015ea  mov     ecx, [rdi+28h]
0x1400015ed  mov     r13, [rdi+18h]
0x1400015f1  cmp     [rbx+10h], ebp
0x1400015f4  jz      loc_1400016F9
0x1400015fa  xor     r12b, r12b
0x1400015fd  mov     eax, [rdi+24h]
0x140001600  sub     [rbx+20h], eax
0x140001603  sub     [rbx+14h], ecx
0x140001606  dec     dword ptr [rbx+18h]
0x140001609  cmp     [rbx], rbx
0x14000160c  jnz     loc_1400016C5
0x140001612  mov     dword ptr [rbx+10h], 2
0x140001619  cmp     [rbx+28h], rdi
0x14000161d  jnz     loc_1400016E4
0x140001623  lock bts dword ptr [rbx+28h], 0
0x140001629  xor     ebx, ebx
0x14000162b  test    ebp, ebp
0x14000162d  cmovz   rbx, rdi
0x140001631  test    r15, r15
0x140001634  jz      short loc_140001654
0x140001636  lea     rcx, [r14+40h]
0x14000163a  xor     edx, edx
0x14000163c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140001643  nop     dword ptr [rax+rax+00h]
0x140001648  call    cs:__imp_KeLeaveCriticalRegion
0x14000164f  nop     dword ptr [rax+rax+00h]
0x140001654  test    rbx, rbx
0x140001657  jz      short loc_14000166A
0x140001659  xor     edx, edx; Tag
0x14000165b  mov     rcx, rbx; P
0x14000165e  call    cs:__imp_ExFreePoolWithTag
0x140001665  nop     dword ptr [rax+rax+00h]
0x14000166a  mov     rcx, r13; P
0x14000166d  call    NpFreeClientSecurityContext
0x140001672  mov     dl, 2; PriorityBoost
0x140001674  mov     dword ptr [rsi+30h], 0C0000120h
0x14000167b  mov     rcx, rsi; Irp
0x14000167e  call    cs:__imp_IofCompleteRequest
0x140001685  nop     dword ptr [rax+rax+00h]
0x14000168a  mov     rbx, qword ptr [rsp+78h+var_58]
0x14000168f  jmp     short loc_1400016A9
0x140001691  lea     rcx, [rbx-0A8h]; Irp
0x140001698  mov     dl, 2; PriorityBoost
0x14000169a  mov     rbx, [rbx]
0x14000169d  call    cs:__imp_IofCompleteRequest
0x1400016a4  nop     dword ptr [rax+rax+00h]
0x1400016a9  lea     rax, [rsp+78h+var_58]
0x1400016ae  cmp     rbx, rax
0x1400016b1  jnz     short loc_140001691
0x1400016b3  add     rsp, 38h
0x1400016b7  pop     r15
0x1400016b9  pop     r14
0x1400016bb  pop     r13
0x1400016bd  pop     r12
0x1400016bf  pop     rdi
0x1400016c0  pop     rsi
0x1400016c1  pop     rbp
0x1400016c2  pop     rbx
0x1400016c3  retn
0x1400016c5  test    dl, dl
0x1400016c7  jnz     short loc_140001717
0x1400016c9  test    r12b, r12b
0x1400016cc  jz      loc_140001619
0x1400016d2  lea     rdx, [rsp+78h+var_58]
0x1400016d7  mov     rcx, rbx
0x1400016da  call    NpCompleteStalledWrites
0x1400016df  jmp     loc_140001619
0x1400016e4  xor     ebp, ebp
0x1400016e6  jmp     loc_140001629
0x1400016eb  xor     dl, dl
0x1400016ed  jmp     loc_1400015C9
0x1400016f2  mov     ecx, 3
0x1400016f7  int     29h; Win8: RtlFailFast(ecx)
0x1400016f9  mov     eax, [rbx+1Ch]
0x1400016fc  cmp     [rbx+20h], eax
0x1400016ff  jb      loc_1400015FA
0x140001705  cmp     dword ptr [rdi+24h], 0
0x140001709  jz      loc_1400015FA
0x14000170f  mov     r12b, bpl
0x140001712  jmp     loc_1400015FD
0x140001717  lea     rdx, [rsp+78h+var_58]
0x14000171c  mov     rcx, rbx
0x14000171f  call    NpGetNextRealDataQueueEntry
0x140001724  jmp     short loc_1400016C9
```
