# UlChannelBindConfigProcessing

- ea: `0x1400fb4d4`
- end: `0x1400fb70e`
- name: `UlChannelBindConfigProcessing`
- size: `570`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1400c8eb0`
- `0x1400e6584`

## callees

- `0x140074420`
- `0x1400b1bac`
- `0x1400fb3d0`
- `0x1400fb454`
- `0x1400fb4d4`
- `0x140146114`
- `0x140146a98`
- `0x1401cebd0`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400fb686`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400fb686`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400fb5c5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400fb5c5`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400fb63d`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400fb63d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400fb5ea`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400fb5ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb5f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb692`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb5f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fb692`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb5b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb62a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb5b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fb62a`

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
0x1400fb4d4  mov     [rsp+arg_0], rbx
0x1400fb4d9  mov     [rsp+arg_18], r9
0x1400fb4de  mov     [rsp+arg_10], r8b
0x1400fb4e3  push    rbp
0x1400fb4e4  push    rsi
0x1400fb4e5  push    rdi
0x1400fb4e6  push    r12
0x1400fb4e8  push    r13
0x1400fb4ea  push    r14
0x1400fb4ec  push    r15
0x1400fb4ee  sub     rsp, 30h
0x1400fb4f2  mov     rax, [rcx+18h]
0x1400fb4f6  xor     ebx, ebx
0x1400fb4f8  mov     r13, r9
0x1400fb4fb  mov     rsi, rdx
0x1400fb4fe  mov     rdi, rcx
0x1400fb501  mov     r15, [rax+448h]
0x1400fb508  mov     rax, [rdx+10h]
0x1400fb50c  test    rax, rax
0x1400fb50f  jz      short loc_1400FB514
0x1400fb511  mov     ebx, [rax+10h]
0x1400fb514  test    byte ptr [r15+6E2h], 20h
0x1400fb51c  jz      short loc_1400FB53B
0x1400fb51e  mov     eax, [rdx]
0x1400fb520  lea     rcx, [r15+698h]
0x1400fb527  mov     r9b, [rdx+4]
0x1400fb52b  and     eax, 1
0x1400fb52e  mov     [rsp+68h+var_40], ebx
0x1400fb532  mov     [rsp+68h+var_48], eax
0x1400fb536  call    McTemplateK0uqq_EtwWriteTransfer
0x1400fb53b  test    byte ptr cs:xmmword_1401A2CA0, 4
0x1400fb542  jz      short loc_1400FB567
0x1400fb544  mov     eax, [rsi]
0x1400fb546  lea     r8, WPP_bc9fc6652f5239547d16a26279776278_Traceguids
0x1400fb54d  movzx   r9d, word ptr [rsi+4]
0x1400fb552  and     eax, 1
0x1400fb555  mov     edx, 0Bh
0x1400fb55a  mov     [rsp+68h+var_40], ebx
0x1400fb55e  mov     [rsp+68h+var_48], eax
0x1400fb562  call    WPP_SF_HLL
0x1400fb567  mov     rbp, [rdi+630h]
0x1400fb56e  test    rbp, rbp
0x1400fb571  jz      short loc_1400FB578
0x1400fb573  mov     r12b, 1
0x1400fb576  jmp     short loc_1400FB5A2
0x1400fb578  xor     r12b, r12b
0x1400fb57b  cmp     [rdi+629h], r12b
0x1400fb582  jz      short loc_1400FB59B
0x1400fb584  mov     rbp, [rdi+528h]
0x1400fb58b  lea     r14, aServerSession; "SERVER_SESSION"
0x1400fb592  add     rbp, 178h
0x1400fb599  jmp     short loc_1400FB5B0
0x1400fb59b  mov     rbp, [rdi+530h]
0x1400fb5a2  lea     r14, aDefaultGroup; "DEFAULT_GROUP"
0x1400fb5a9  add     rbp, 180h
0x1400fb5b0  call    cs:__imp_KeEnterCriticalRegion
0x1400fb5b7  nop     dword ptr [rax+rax+00h]
0x1400fb5bc  mov     rcx, [r15+558h]
0x1400fb5c3  xor     edx, edx
0x1400fb5c5  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400fb5cc  nop     dword ptr [rax+rax+00h]
0x1400fb5d1  mov     r8, r13
0x1400fb5d4  mov     rdx, rsi
0x1400fb5d7  mov     rcx, rbp
0x1400fb5da  mov     rbx, rax
0x1400fb5dd  call    UlIsChannelBindChangeNeeded
0x1400fb5e2  xor     edx, edx
0x1400fb5e4  mov     rcx, rbx
0x1400fb5e7  mov     r13d, eax
0x1400fb5ea  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400fb5f1  nop     dword ptr [rax+rax+00h]
0x1400fb5f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400fb5fd  nop     dword ptr [rax+rax+00h]
0x1400fb602  xor     ebx, ebx
0x1400fb604  test    r13d, r13d
0x1400fb607  js      loc_1400FB6ED
0x1400fb60d  mov     rax, [rsp+68h+arg_18]
0x1400fb615  cmp     [rax], bl
0x1400fb617  jz      loc_1400FB6ED
0x1400fb61d  cmp     [rsp+68h+arg_10], bl
0x1400fb624  jz      loc_1400FB6ED
0x1400fb62a  call    cs:__imp_KeEnterCriticalRegion
0x1400fb631  nop     dword ptr [rax+rax+00h]
0x1400fb636  mov     rcx, [r15+558h]
0x1400fb63d  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400fb644  nop     dword ptr [rax+rax+00h]
0x1400fb649  test    r12b, r12b
0x1400fb64c  jz      short loc_1400FB674
0x1400fb64e  mov     rcx, [rdi+530h]
0x1400fb655  cmp     [rdi+630h], rcx
0x1400fb65c  jz      short loc_1400FB674
0x1400fb65e  mov     eax, [rsi]
0x1400fb660  lea     r14, aOwnerGroup; "OWNER_GROUP"
0x1400fb667  test    al, 1
0x1400fb669  jz      short loc_1400FB67F
0x1400fb66b  add     rcx, 180h
0x1400fb672  jmp     short loc_1400FB677
0x1400fb674  mov     rcx, rbp
0x1400fb677  mov     rdx, rsi
0x1400fb67a  call    UlUpdateChannelBindConfig
0x1400fb67f  mov     rcx, [r15+558h]
0x1400fb686  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400fb68d  nop     dword ptr [rax+rax+00h]
0x1400fb692  call    cs:__imp_KeLeaveCriticalRegion
0x1400fb699  nop     dword ptr [rax+rax+00h]
0x1400fb69e  mov     rdx, [rdi+18h]
0x1400fb6a2  test    rdx, rdx
0x1400fb6a5  jz      short loc_1400FB6ED
0x1400fb6a7  mov     rcx, [rdx+448h]
0x1400fb6ae  test    byte ptr [rcx+6E2h], 20h
0x1400fb6b5  jz      short loc_1400FB6ED
0x1400fb6b7  cmp     [rcx+6F0h], rbx
0x1400fb6be  jz      short loc_1400FB6CF
0x1400fb6c0  xor     r8d, r8d
0x1400fb6c3  mov     rcx, rdi
0x1400fb6c6  call    UlEtwEvaluateFilterForRequestConnection
0x1400fb6cb  test    al, al
0x1400fb6cd  jz      short loc_1400FB6ED
0x1400fb6cf  mov     rax, [rdi+18h]
0x1400fb6d3  lea     r8, [rdi+48h]
0x1400fb6d7  mov     r9, r14
0x1400fb6da  mov     rcx, [rax+448h]
0x1400fb6e1  add     rcx, 698h
0x1400fb6e8  call    McTemplateK0s_EtwWriteTransfer
0x1400fb6ed  mov     rcx, rsi
0x1400fb6f0  call    UlCleanupChannelBindConfig
0x1400fb6f5  mov     rbx, [rsp+68h+arg_0]
0x1400fb6fa  mov     eax, r13d
0x1400fb6fd  add     rsp, 30h
0x1400fb701  pop     r15
0x1400fb703  pop     r14
0x1400fb705  pop     r13
0x1400fb707  pop     r12
0x1400fb709  pop     rdi
0x1400fb70a  pop     rsi
0x1400fb70b  pop     rbp
0x1400fb70c  retn
```
