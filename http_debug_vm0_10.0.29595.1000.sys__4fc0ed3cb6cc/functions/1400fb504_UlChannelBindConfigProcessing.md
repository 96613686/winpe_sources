# UlChannelBindConfigProcessing

- ea: `0x1400fb504`
- end: `0x1400fb73e`
- name: `UlChannelBindConfigProcessing`
- size: `570`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1400c8dd0`
- `0x1400e65c4`

## callees

- `0x140074400`
- `0x1400b1acc`
- `0x1400fb400`
- `0x1400fb484`
- `0x1400fb504`
- `0x140146204`
- `0x140146b88`
- `0x1401cebd0`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400fb6b6`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400fb6b6`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400fb5f5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400fb5f5`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400fb66d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400fb66d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400fb61a`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400fb61a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb626`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb6c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb626`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb6c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb5e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb65a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb5e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb65a`

## pseudocode

```c
__int64 __fastcall UlChannelBindConfigProcessing(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  int v4; // ebx
  _BYTE *v5; // r13
  __int64 v8; // r15
  __int64 v9; // rax
  __int64 v10; // rbp
  char v11; // r12
  const char *v12; // r14
  __int64 v13; // rbp
  __int64 v14; // rbx
  int v15; // r13d
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _BYTE *v22; // [rsp+88h] [rbp+20h]

  v22 = a4;
  v4 = 0;
  v5 = a4;
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL);
  v9 = *(_QWORD *)(a2 + 16);
  if ( v9 )
    v4 = *(_DWORD *)(v9 + 16);
  if ( (*(_BYTE *)(v8 + 1762) & 0x20) != 0 )
  {
    LOBYTE(a4) = *(_BYTE *)(a2 + 4);
    McTemplateK0uqq_EtwWriteTransfer(v8 + 1688, a2, a3, (_DWORD)a4, *(_BYTE *)a2 & 1, v4);
  }
  if ( (xmmword_1401A2CA0 & 4) != 0 )
    WPP_SF_HLL(
      a1,
      11,
      WPP_bc9fc6652f5239547d16a26279776278_Traceguids,
      *(unsigned __int16 *)(a2 + 4),
      *(_DWORD *)a2 & 1,
      v4);
  v10 = *(_QWORD *)(a1 + 1584);
  if ( v10 )
  {
    v11 = 1;
LABEL_12:
    v12 = "DEFAULT_GROUP";
    v13 = v10 + 384;
    goto LABEL_13;
  }
  v11 = 0;
  if ( !*(_BYTE *)(a1 + 1577) )
  {
    v10 = *(_QWORD *)(a1 + 1328);
    goto LABEL_12;
  }
  v12 = "SERVER_SESSION";
  v13 = *(_QWORD *)(a1 + 1320) + 376LL;
LABEL_13:
  KeEnterCriticalRegion();
  v14 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v8 + 1368), 0);
  v15 = UlIsChannelBindChangeNeeded(v13, a2, v5);
  ExReleaseCacheAwarePushLockSharedEx(v14, 0);
  KeLeaveCriticalRegion();
  if ( v15 < 0 || !*v22 || !a3 )
    goto LABEL_27;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v8 + 1368));
  if ( !v11 || (v16 = *(_QWORD *)(a1 + 1328), *(_QWORD *)(a1 + 1584) == v16) )
  {
    v17 = v13;
    goto LABEL_21;
  }
  v12 = "OWNER_GROUP";
  if ( (*(_DWORD *)a2 & 1) != 0 )
  {
    v17 = v16 + 384;
LABEL_21:
    UlUpdateChannelBindConfig(v17, a2);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v8 + 1368));
  KeLeaveCriticalRegion();
  v18 = *(_QWORD *)(a1 + 24);
  if ( v18 )
  {
    v19 = *(_QWORD *)(v18 + 1096);
    if ( (*(_BYTE *)(v19 + 1762) & 0x20) != 0
      && (!*(_QWORD *)(v19 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(a1, v18, 0)) )
    {
      McTemplateK0s_EtwWriteTransfer(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL) + 1688LL, v18, a1 + 72, v12);
    }
  }
LABEL_27:
  UlCleanupChannelBindConfig(a2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400fb504  mov     [rsp+arg_0], rbx
0x1400fb509  mov     [rsp+arg_18], r9
0x1400fb50e  mov     [rsp+arg_10], r8b
0x1400fb513  push    rbp
0x1400fb514  push    rsi
0x1400fb515  push    rdi
0x1400fb516  push    r12
0x1400fb518  push    r13
0x1400fb51a  push    r14
0x1400fb51c  push    r15
0x1400fb51e  sub     rsp, 30h
0x1400fb522  mov     rax, [rcx+18h]
0x1400fb526  xor     ebx, ebx
0x1400fb528  mov     r13, r9
0x1400fb52b  mov     rsi, rdx
0x1400fb52e  mov     rdi, rcx
0x1400fb531  mov     r15, [rax+448h]
0x1400fb538  mov     rax, [rdx+10h]
0x1400fb53c  test    rax, rax
0x1400fb53f  jz      short loc_1400FB544
0x1400fb541  mov     ebx, [rax+10h]
0x1400fb544  test    byte ptr [r15+6E2h], 20h
0x1400fb54c  jz      short loc_1400FB56B
0x1400fb54e  mov     eax, [rdx]
0x1400fb550  lea     rcx, [r15+698h]
0x1400fb557  mov     r9b, [rdx+4]
0x1400fb55b  and     eax, 1
0x1400fb55e  mov     [rsp+68h+var_40], ebx
0x1400fb562  mov     [rsp+68h+var_48], eax
0x1400fb566  call    McTemplateK0uqq_EtwWriteTransfer
0x1400fb56b  test    byte ptr cs:xmmword_1401A2CA0, 4
0x1400fb572  jz      short loc_1400FB597
0x1400fb574  mov     eax, [rsi]
0x1400fb576  lea     r8, WPP_bc9fc6652f5239547d16a26279776278_Traceguids
0x1400fb57d  movzx   r9d, word ptr [rsi+4]
0x1400fb582  and     eax, 1
0x1400fb585  mov     edx, 0Bh
0x1400fb58a  mov     [rsp+68h+var_40], ebx
0x1400fb58e  mov     [rsp+68h+var_48], eax
0x1400fb592  call    WPP_SF_HLL
0x1400fb597  mov     rbp, [rdi+630h]
0x1400fb59e  test    rbp, rbp
0x1400fb5a1  jz      short loc_1400FB5A8
0x1400fb5a3  mov     r12b, 1
0x1400fb5a6  jmp     short loc_1400FB5D2
0x1400fb5a8  xor     r12b, r12b
0x1400fb5ab  cmp     [rdi+629h], r12b
0x1400fb5b2  jz      short loc_1400FB5CB
0x1400fb5b4  mov     rbp, [rdi+528h]
0x1400fb5bb  lea     r14, aServerSession; "SERVER_SESSION"
0x1400fb5c2  add     rbp, 178h
0x1400fb5c9  jmp     short loc_1400FB5E0
0x1400fb5cb  mov     rbp, [rdi+530h]
0x1400fb5d2  lea     r14, aDefaultGroup; "DEFAULT_GROUP"
0x1400fb5d9  add     rbp, 180h
0x1400fb5e0  call    cs:__imp_KeEnterCriticalRegion
0x1400fb5e7  nop     dword ptr [rax+rax+00h]
0x1400fb5ec  mov     rcx, [r15+558h]
0x1400fb5f3  xor     edx, edx
0x1400fb5f5  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400fb5fc  nop     dword ptr [rax+rax+00h]
0x1400fb601  mov     r8, r13
0x1400fb604  mov     rdx, rsi
0x1400fb607  mov     rcx, rbp
0x1400fb60a  mov     rbx, rax
0x1400fb60d  call    UlIsChannelBindChangeNeeded
0x1400fb612  xor     edx, edx
0x1400fb614  mov     rcx, rbx
0x1400fb617  mov     r13d, eax
0x1400fb61a  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400fb621  nop     dword ptr [rax+rax+00h]
0x1400fb626  call    cs:__imp_KeLeaveCriticalRegion
0x1400fb62d  nop     dword ptr [rax+rax+00h]
0x1400fb632  xor     ebx, ebx
0x1400fb634  test    r13d, r13d
0x1400fb637  js      loc_1400FB71D
0x1400fb63d  mov     rax, [rsp+68h+arg_18]
0x1400fb645  cmp     [rax], bl
0x1400fb647  jz      loc_1400FB71D
0x1400fb64d  cmp     [rsp+68h+arg_10], bl
0x1400fb654  jz      loc_1400FB71D
0x1400fb65a  call    cs:__imp_KeEnterCriticalRegion
0x1400fb661  nop     dword ptr [rax+rax+00h]
0x1400fb666  mov     rcx, [r15+558h]
0x1400fb66d  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400fb674  nop     dword ptr [rax+rax+00h]
0x1400fb679  test    r12b, r12b
0x1400fb67c  jz      short loc_1400FB6A4
0x1400fb67e  mov     rcx, [rdi+530h]
0x1400fb685  cmp     [rdi+630h], rcx
0x1400fb68c  jz      short loc_1400FB6A4
0x1400fb68e  mov     eax, [rsi]
0x1400fb690  lea     r14, aOwnerGroup; "OWNER_GROUP"
0x1400fb697  test    al, 1
0x1400fb699  jz      short loc_1400FB6AF
0x1400fb69b  add     rcx, 180h
0x1400fb6a2  jmp     short loc_1400FB6A7
0x1400fb6a4  mov     rcx, rbp
0x1400fb6a7  mov     rdx, rsi
0x1400fb6aa  call    UlUpdateChannelBindConfig
0x1400fb6af  mov     rcx, [r15+558h]
0x1400fb6b6  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400fb6bd  nop     dword ptr [rax+rax+00h]
0x1400fb6c2  call    cs:__imp_KeLeaveCriticalRegion
0x1400fb6c9  nop     dword ptr [rax+rax+00h]
0x1400fb6ce  mov     rdx, [rdi+18h]
0x1400fb6d2  test    rdx, rdx
0x1400fb6d5  jz      short loc_1400FB71D
0x1400fb6d7  mov     rcx, [rdx+448h]
0x1400fb6de  test    byte ptr [rcx+6E2h], 20h
0x1400fb6e5  jz      short loc_1400FB71D
0x1400fb6e7  cmp     [rcx+6F0h], rbx
0x1400fb6ee  jz      short loc_1400FB6FF
0x1400fb6f0  xor     r8d, r8d
0x1400fb6f3  mov     rcx, rdi
0x1400fb6f6  call    UlEtwEvaluateFilterForRequestConnection
0x1400fb6fb  test    al, al
0x1400fb6fd  jz      short loc_1400FB71D
0x1400fb6ff  mov     rax, [rdi+18h]
0x1400fb703  lea     r8, [rdi+48h]
0x1400fb707  mov     r9, r14
0x1400fb70a  mov     rcx, [rax+448h]
0x1400fb711  add     rcx, 698h
0x1400fb718  call    McTemplateK0s_EtwWriteTransfer
0x1400fb71d  mov     rcx, rsi
0x1400fb720  call    UlCleanupChannelBindConfig
0x1400fb725  mov     rbx, [rsp+68h+arg_0]
0x1400fb72a  mov     eax, r13d
0x1400fb72d  add     rsp, 30h
0x1400fb731  pop     r15
0x1400fb733  pop     r14
0x1400fb735  pop     r13
0x1400fb737  pop     r12
0x1400fb739  pop     rdi
0x1400fb73a  pop     rsi
0x1400fb73b  pop     rbp
0x1400fb73c  retn
```
