# CdCompleteFcbOpen

- ea: `0x14000d400`
- end: `0x14000d88f`
- name: `CdCompleteFcbOpen`
- size: `1167`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, int, int, ACCESS_MASK DesiredAccess)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000dc38`
- `0x14000e1d0`
- `0x14000e4a0`
- `0x14000e544`

## callees

- `0x140001114`
- `0x14000bcf8`
- `0x14000c374`
- `0x14000d400`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000d70c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d7a8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d70c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d7a8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d77b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d822`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d77b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d822`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d600`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d600`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000d525`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000d585`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000d525`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000d585`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000d7d5`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000d7d5`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14000d4ed`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14000d4ed`
- `ntoskrnl!IoCheckShareAccess` at `0x14000d552`
- `ntoskrnl!IoCheckShareAccess` at `0x14000d5cd`
- `ntoskrnl!IoCheckShareAccess` at `0x14000d552`
- `ntoskrnl!IoCheckShareAccess` at `0x14000d5cd`
- `ntoskrnl!IoSetShareAccess` at `0x14000d681`
- `ntoskrnl!IoSetShareAccess` at `0x14000d681`
- `ntoskrnl!IoUpdateShareAccess` at `0x14000d692`
- `ntoskrnl!IoUpdateShareAccess` at `0x14000d692`

## pseudocode

```c
NTSTATUS __fastcall CdCompleteFcbOpen(
        PIRP *Context,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        int a5,
        int a6,
        ACCESS_MASK DesiredAccess)
{
  ACCESS_MASK v7; // edi
  __int64 v9; // rbx
  __int64 v10; // rbp
  char v14; // r15
  NTSTATUS result; // eax
  PFILE_OBJECT *v16; // r14
  _OWORD *PoolWithTag; // rax
  unsigned __int64 v18; // r12
  PFILE_OBJECT v19; // rdx
  ULONG Flags; // ecx
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v26; // rax
  struct _FAST_MUTEX *v28; // rcx
  PFILE_OBJECT *v29; // [rsp+30h] [rbp-48h]
  __int64 v30; // [rsp+38h] [rbp-40h]
  char v32; // [rsp+98h] [rbp+20h]
  NTSTATUS v33; // [rsp+A0h] [rbp+28h]

  v7 = DesiredAccess;
  v9 = *a4;
  v10 = a5;
  v32 = 0;
  v14 = 2;
  if ( DesiredAccess == 0x2000000 )
    v7 = ~((a5 != 2 ? 0x116 : 0) | 0x50040) & 0x1F01FF;
  if ( a5 <= 2 && (*(_BYTE *)(a2 + 26) & 1) == 0 )
  {
    if ( *(_DWORD *)(a3 + 56) )
      return -1073741757;
    if ( ((_DWORD)Context[4] & 4) == 0 )
      CdRaiseStatusEx(Context, 3221225688LL, 0, 0x80000, 2772);
    result = CdPurgeVolume(Context, a3, 0);
    if ( result )
      return result;
    v32 = 1;
    CdFspClose(a3);
    if ( *(_DWORD *)(a3 + 64) > 3u )
      return -1073741757;
  }
  v33 = 0;
  if ( !*(_DWORD *)(v9 + 160) )
  {
    v16 = (PFILE_OBJECT *)(a2 + 48);
LABEL_21:
    v30 = 1;
LABEL_22:
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x38u, 0x63636443u);
    v18 = (unsigned __int64)PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
      v29 = v16;
    else
      v29 = (PFILE_OBJECT *)(a2 + 48);
    *PoolWithTag = 0;
    PoolWithTag[1] = 0;
    PoolWithTag[2] = 0;
    *((_QWORD *)PoolWithTag + 6) = 0;
    *((_DWORD *)PoolWithTag + 1) = a6;
    *(_DWORD *)PoolWithTag = 3670791;
    *((_QWORD *)PoolWithTag + 1) = v9;
    if ( *(_DWORD *)(v9 + 160) )
      IoUpdateShareAccess(*v16, (PSHARE_ACCESS)(v9 + 208));
    else
      IoSetShareAccess(v7, *(unsigned __int16 *)(a2 + 26), *v16, (PSHARE_ACCESS)(v9 + 208));
    v19 = *v16;
    if ( (_DWORD)v10 )
    {
      v19->FsContext = (PVOID)v9;
      v19->FsContext2 = (PVOID)(v18 | v10);
      v19->Vpb = *(PVPB *)(*(_QWORD *)(v9 + 120) + 8LL);
      if ( (_DWORD)v10 == 4 )
      {
        Flags = (*v29)->Flags;
        if ( (*(_DWORD *)(a2 + 16) & 8) != 0 )
          v21 = Flags | 8;
        else
          v21 = Flags | 0x40;
        (*v29)->Flags = v21;
      }
      else if ( (_DWORD)v10 == 2 )
      {
        (*v29)->Flags |= 8u;
      }
    }
    else
    {
      v19->FsContext2 = 0;
      v19->FsContext = 0;
    }
    ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
    *(_QWORD *)(a3 + 392) = KeGetCurrentThread();
    v22 = *(_QWORD *)(v9 + 120);
    ++*(_DWORD *)(v9 + 160);
    ++*(_DWORD *)(v22 + 56);
    v23 = *(_QWORD *)(v9 + 120);
    ++*(_DWORD *)(v9 + 164);
    ++*(_DWORD *)(v9 + 168);
    ++*(_DWORD *)(v23 + 60);
    ++*(_DWORD *)(*(_QWORD *)(v9 + 120) + 64LL);
    if ( v32 )
    {
      v24 = *(_QWORD *)(a2 + 48);
      *(_DWORD *)(a3 + 48) |= 0x10u;
      *(_QWORD *)(a3 + 24) = v24;
    }
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)(v9 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v9 + 200) + 136LL));
      *(_QWORD *)(v9 + 184) = CurrentThread;
    }
    ++*(_DWORD *)(v9 + 192);
    if ( (_DWORD)v10 == 4 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v9 + 120) + 52LL) == 2 && FsRtlOplockIsFastIoPossible((POPLOCK)(v9 + 88)) )
      {
        v26 = *(_QWORD *)(v9 + 472);
        if ( !v26 || !*(_BYTE *)(v26 + 16) )
          v14 = 1;
      }
      else
      {
        v14 = 0;
      }
    }
    else
    {
      v14 = 0;
    }
    *(_BYTE *)(v9 + 5) = v14;
    if ( (*(_DWORD *)(v9 + 192))-- == 1 )
    {
      v28 = (struct _FAST_MUTEX *)(*(_QWORD *)(v9 + 200) + 136LL);
      *(_QWORD *)(v9 + 184) = 0;
      ExReleaseFastMutex(v28);
    }
    Context[1]->IoStatus.Information = v30;
    *(_QWORD *)(*(_QWORD *)(a2 + 48) + 40LL) = *(_QWORD *)(v9 + 200) + 8LL;
    return v33;
  }
  if ( (_DWORD)v10 != 4 )
  {
    v16 = (PFILE_OBJECT *)(a2 + 48);
    result = IoCheckShareAccess(
               v7,
               *(unsigned __int16 *)(a2 + 26),
               *(PFILE_OBJECT *)(a2 + 48),
               (PSHARE_ACCESS)(v9 + 208),
               0);
    if ( result < 0 )
      return result;
    goto LABEL_21;
  }
  Context[6] = (PIRP)a4;
  v30 = 1;
  if ( FsRtlCurrentBatchOplock((POPLOCK)(v9 + 88)) )
  {
    v30 = 9;
    if ( FsRtlCheckOplock((POPLOCK)(v9 + 88), Context[1], Context, CdOplockComplete, CdPrePostIrp) == 259 )
      return 259;
  }
  v16 = (PFILE_OBJECT *)(a2 + 48);
  result = IoCheckShareAccess(
             v7,
             *(unsigned __int16 *)(a2 + 26),
             *(PFILE_OBJECT *)(a2 + 48),
             (PSHARE_ACCESS)(v9 + 208),
             0);
  if ( result >= 0 )
  {
    v33 = FsRtlCheckOplock((POPLOCK)(v9 + 88), Context[1], Context, CdOplockComplete, CdPrePostIrp);
    if ( v33 == 259 )
      return 259;
    Context[6] = 0;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x14000d400  mov     [rsp+arg_8], rbx
0x14000d405  mov     [rsp+arg_0], rcx
0x14000d40a  push    rbp
0x14000d40b  push    rsi
0x14000d40c  push    rdi
0x14000d40d  push    r12
0x14000d40f  push    r13
0x14000d411  push    r14
0x14000d413  push    r15
0x14000d415  sub     rsp, 40h
0x14000d419  mov     edi, [rsp+78h+DesiredAccess]
0x14000d420  mov     r12, rcx
0x14000d423  mov     rbx, [r9]
0x14000d426  xor     ecx, ecx
0x14000d428  movsxd  rbp, [rsp+78h+arg_20]
0x14000d430  mov     r14, r9
0x14000d433  mov     [rsp+78h+arg_18], cl
0x14000d43a  mov     rsi, r8
0x14000d43d  mov     r13, rdx
0x14000d440  lea     r15d, [rcx+2]
0x14000d444  cmp     edi, 2000000h
0x14000d44a  jnz     short loc_14000D469
0x14000d44c  mov     eax, ebp
0x14000d44e  sub     eax, r15d
0x14000d451  neg     eax
0x14000d453  sbb     edi, edi
0x14000d455  and     edi, 116h
0x14000d45b  or      edi, 50040h
0x14000d461  not     edi
0x14000d463  and     edi, 1F01FFh
0x14000d469  cmp     ebp, r15d
0x14000d46c  jg      short loc_14000D4BF
0x14000d46e  test    byte ptr [rdx+1Ah], 1
0x14000d472  jnz     short loc_14000D4BF
0x14000d474  cmp     [r8+38h], ecx
0x14000d478  jnz     short loc_14000D4B3
0x14000d47a  mov     eax, [r12+20h]
0x14000d47f  xor     r8d, r8d
0x14000d482  mov     rcx, r12
0x14000d485  test    al, 4
0x14000d487  jz      loc_14000D876
0x14000d48d  mov     rdx, rsi
0x14000d490  call    CdPurgeVolume
0x14000d495  test    eax, eax
0x14000d497  jnz     loc_14000D85D
0x14000d49d  mov     rcx, rsi
0x14000d4a0  mov     [rsp+78h+arg_18], 1
0x14000d4a8  call    CdFspClose
0x14000d4ad  cmp     dword ptr [rsi+40h], 3
0x14000d4b1  jbe     short loc_14000D4BD
0x14000d4b3  mov     eax, 0C0000043h
0x14000d4b8  jmp     loc_14000D85D
0x14000d4bd  xor     ecx, ecx
0x14000d4bf  mov     [rsp+78h+arg_20], ecx
0x14000d4c6  cmp     [rbx+0A0h], ecx
0x14000d4cc  jz      loc_14000D5E3
0x14000d4d2  cmp     ebp, 4
0x14000d4d5  jnz     loc_14000D5B4
0x14000d4db  lea     rcx, [rbx+58h]; Oplock
0x14000d4df  mov     [r12+30h], r14
0x14000d4e4  mov     [rsp+78h+var_40], 1
0x14000d4ed  call    cs:__imp_FsRtlCurrentBatchOplock
0x14000d4f4  nop     dword ptr [rax+rax+00h]
0x14000d4f9  lea     rcx, CdPrePostIrp
0x14000d500  test    al, al
0x14000d502  jz      short loc_14000D538
0x14000d504  mov     rdx, [r12+8]; Irp
0x14000d509  lea     r9, CdOplockComplete; CompletionRoutine
0x14000d510  mov     [rsp+78h+PostIrpRoutine], rcx; PostIrpRoutine
0x14000d515  mov     r8, r12; Context
0x14000d518  lea     rcx, [rbx+58h]; Oplock
0x14000d51c  mov     [rsp+78h+var_40], 9
0x14000d525  call    cs:__imp_FsRtlCheckOplock
0x14000d52c  nop     dword ptr [rax+rax+00h]
0x14000d531  cmp     eax, 103h
0x14000d536  jz      short loc_14000D59F
0x14000d538  movzx   edx, word ptr [r13+1Ah]; DesiredShareAccess
0x14000d53d  lea     r14, [r13+30h]
0x14000d541  mov     r8, [r14]; FileObject
0x14000d544  lea     r9, [rbx+0D0h]; ShareAccess
0x14000d54b  mov     ecx, edi; DesiredAccess
0x14000d54d  mov     byte ptr [rsp+78h+PostIrpRoutine], 0; Update
0x14000d552  call    cs:__imp_IoCheckShareAccess
0x14000d559  nop     dword ptr [rax+rax+00h]
0x14000d55e  test    eax, eax
0x14000d560  js      loc_14000D85D
0x14000d566  mov     rdx, [r12+8]; Irp
0x14000d56b  lea     rax, CdPrePostIrp
0x14000d572  lea     r9, CdOplockComplete; CompletionRoutine
0x14000d579  mov     [rsp+78h+PostIrpRoutine], rax; PostIrpRoutine
0x14000d57e  mov     r8, r12; Context
0x14000d581  lea     rcx, [rbx+58h]; Oplock
0x14000d585  call    cs:__imp_FsRtlCheckOplock
0x14000d58c  nop     dword ptr [rax+rax+00h]
0x14000d591  mov     [rsp+78h+arg_20], eax
0x14000d598  cmp     eax, 103h
0x14000d59d  jnz     short loc_14000D5A9
0x14000d59f  mov     eax, 103h
0x14000d5a4  jmp     loc_14000D85D
0x14000d5a9  mov     qword ptr [r12+30h], 0
0x14000d5b2  jmp     short loc_14000D5F0
0x14000d5b4  movzx   edx, word ptr [r13+1Ah]; DesiredShareAccess
0x14000d5b9  lea     r14, [r13+30h]
0x14000d5bd  mov     r8, [r14]; FileObject
0x14000d5c0  lea     r9, [rbx+0D0h]; ShareAccess
0x14000d5c7  mov     byte ptr [rsp+78h+PostIrpRoutine], cl; Update
0x14000d5cb  mov     ecx, edi; DesiredAccess
0x14000d5cd  call    cs:__imp_IoCheckShareAccess
0x14000d5d4  nop     dword ptr [rax+rax+00h]
0x14000d5d9  test    eax, eax
0x14000d5db  js      loc_14000D85D
0x14000d5e1  jmp     short loc_14000D5E7
0x14000d5e3  lea     r14, [r13+30h]
0x14000d5e7  mov     [rsp+78h+var_40], 1
0x14000d5f0  mov     edx, 38h ; '8'; NumberOfBytes
0x14000d5f5  mov     ecx, 411h; PoolType
0x14000d5fa  mov     r8d, 63636443h; Tag
0x14000d600  call    cs:__imp_ExAllocatePoolWithTag
0x14000d607  nop     dword ptr [rax+rax+00h]
0x14000d60c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000d613  mov     r12, rax
0x14000d616  jnz     short loc_14000D628
0x14000d618  test    rax, rax
0x14000d61b  jz      short loc_14000D628
0x14000d61d  lea     rcx, [r13+30h]
0x14000d621  mov     [rsp+78h+var_48], rcx
0x14000d626  jmp     short loc_14000D62D
0x14000d628  mov     [rsp+78h+var_48], r14
0x14000d62d  xor     eax, eax
0x14000d62f  xorps   xmm0, xmm0
0x14000d632  movups  xmmword ptr [r12], xmm0
0x14000d637  movups  xmmword ptr [r12+10h], xmm0
0x14000d63d  movups  xmmword ptr [r12+20h], xmm0
0x14000d643  mov     [r12+30h], rax
0x14000d648  mov     eax, [rsp+78h+arg_28]
0x14000d64f  mov     [r12+4], eax
0x14000d654  lea     rax, [rbx+0D0h]
0x14000d65b  mov     dword ptr [r12], 380307h
0x14000d663  mov     [r12+8], rbx
0x14000d668  cmp     dword ptr [rbx+0A0h], 0
0x14000d66f  mov     rcx, [r14]; FileObject
0x14000d672  jnz     short loc_14000D68F
0x14000d674  movzx   edx, word ptr [r13+1Ah]; DesiredShareAccess
0x14000d679  mov     r8, rcx; FileObject
0x14000d67c  mov     ecx, edi; DesiredAccess
0x14000d67e  mov     r9, rax; ShareAccess
0x14000d681  call    cs:__imp_IoSetShareAccess
0x14000d688  nop     dword ptr [rax+rax+00h]
0x14000d68d  jmp     short loc_14000D69E
0x14000d68f  mov     rdx, rax; ShareAccess
0x14000d692  call    cs:__imp_IoUpdateShareAccess
0x14000d699  nop     dword ptr [rax+rax+00h]
0x14000d69e  mov     rdx, [r14]
0x14000d6a1  xor     r14d, r14d
0x14000d6a4  test    ebp, ebp
0x14000d6a6  jnz     short loc_14000D6B2
0x14000d6a8  mov     [rdx+20h], r14
0x14000d6ac  mov     [rdx+18h], r14
0x14000d6b0  jmp     short loc_14000D702
0x14000d6b2  mov     [rdx+18h], rbx
0x14000d6b6  mov     rax, rbp
0x14000d6b9  or      rax, r12
0x14000d6bc  mov     [rdx+20h], rax
0x14000d6c0  mov     rax, [rbx+78h]
0x14000d6c4  mov     rcx, [rax+8]
0x14000d6c8  mov     [rdx+10h], rcx
0x14000d6cc  cmp     ebp, 4
0x14000d6cf  jnz     short loc_14000D6F1
0x14000d6d1  mov     rax, [rsp+78h+var_48]
0x14000d6d6  mov     rdx, [rax]
0x14000d6d9  mov     eax, [r13+10h]
0x14000d6dd  mov     ecx, [rdx+50h]
0x14000d6e0  test    al, 8
0x14000d6e2  jz      short loc_14000D6E9
0x14000d6e4  or      ecx, 8
0x14000d6e7  jmp     short loc_14000D6EC
0x14000d6e9  or      ecx, 40h
0x14000d6ec  mov     [rdx+50h], ecx
0x14000d6ef  jmp     short loc_14000D702
0x14000d6f1  cmp     ebp, r15d
0x14000d6f4  jnz     short loc_14000D702
0x14000d6f6  mov     rax, [rsp+78h+var_48]
0x14000d6fb  mov     rax, [rax]
0x14000d6fe  or      dword ptr [rax+50h], 8
0x14000d702  lea     rdi, [rsi+150h]
0x14000d709  mov     rcx, rdi; FastMutex
0x14000d70c  call    cs:__imp_ExAcquireFastMutex
0x14000d713  nop     dword ptr [rax+rax+00h]
0x14000d718  mov     rax, gs:188h
0x14000d721  mov     r12d, 1
0x14000d727  mov     [rsi+188h], rax
0x14000d72e  mov     rax, [rbx+78h]
0x14000d732  add     [rbx+0A0h], r12d
0x14000d739  add     [rax+38h], r12d
0x14000d73d  mov     rax, [rbx+78h]
0x14000d741  add     [rbx+0A4h], r12d
0x14000d748  add     [rbx+0A8h], r12d
0x14000d74f  add     [rax+3Ch], r12d
0x14000d753  mov     rax, [rbx+78h]
0x14000d757  add     [rax+40h], r12d
0x14000d75b  cmp     [rsp+78h+arg_18], r14b
0x14000d763  jz      short loc_14000D771
0x14000d765  mov     rax, [r13+30h]
0x14000d769  or      dword ptr [rsi+30h], 10h
0x14000d76d  mov     [rsi+18h], rax
0x14000d771  mov     rcx, rdi; FastMutex
0x14000d774  mov     [rsi+188h], r14
0x14000d77b  call    cs:__imp_ExReleaseFastMutex
0x14000d782  nop     dword ptr [rax+rax+00h]
0x14000d787  mov     rdi, gs:188h
0x14000d790  mov     esi, 88h
0x14000d795  cmp     rdi, [rbx+0B8h]
0x14000d79c  jz      short loc_14000D7BB
0x14000d79e  mov     rcx, [rbx+0C8h]
0x14000d7a5  add     rcx, rsi; FastMutex
0x14000d7a8  call    cs:__imp_ExAcquireFastMutex
0x14000d7af  nop     dword ptr [rax+rax+00h]
0x14000d7b4  mov     [rbx+0B8h], rdi
0x14000d7bb  add     [rbx+0C0h], r12d
0x14000d7c2  cmp     ebp, 4
0x14000d7c5  jnz     short loc_14000D801
0x14000d7c7  mov     rax, [rbx+78h]
0x14000d7cb  cmp     [rax+34h], r15d
0x14000d7cf  jnz     short loc_14000D7FC
0x14000d7d1  lea     rcx, [rbx+58h]; Oplock
0x14000d7d5  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x14000d7dc  nop     dword ptr [rax+rax+00h]
0x14000d7e1  test    al, al
0x14000d7e3  jz      short loc_14000D7FC
0x14000d7e5  mov     rax, [rbx+1D8h]
0x14000d7ec  test    rax, rax
0x14000d7ef  jz      short loc_14000D7F7
0x14000d7f1  cmp     [rax+10h], r14b
0x14000d7f5  jnz     short loc_14000D804
0x14000d7f7  mov     r15d, r12d
0x14000d7fa  jmp     short loc_14000D804
0x14000d7fc  mov     r15d, r14d
0x14000d7ff  jmp     short loc_14000D804
0x14000d801  mov     r15b, r14b
0x14000d804  mov     [rbx+5], r15b
0x14000d808  sub     [rbx+0C0h], r12d
0x14000d80f  jnz     short loc_14000D82E
0x14000d811  mov     rcx, [rbx+0C8h]
0x14000d818  add     rcx, rsi; FastMutex
0x14000d81b  mov     [rbx+0B8h], r14
0x14000d822  call    cs:__imp_ExReleaseFastMutex
0x14000d829  nop     dword ptr [rax+rax+00h]
0x14000d82e  mov     rcx, [rsp+78h+var_40]
0x14000d833  mov     rax, [rsp+78h+arg_0]
0x14000d83b  mov     rax, [rax+8]
0x14000d83f  mov     [rax+38h], rcx
0x14000d843  mov     rax, [r13+30h]
0x14000d847  mov     rcx, [rbx+0C8h]
0x14000d84e  add     rcx, 8
0x14000d852  mov     [rax+28h], rcx
0x14000d856  mov     eax, [rsp+78h+arg_20]
0x14000d85d  mov     rbx, [rsp+78h+arg_8]
0x14000d865  add     rsp, 40h
0x14000d869  pop     r15
0x14000d86b  pop     r14
0x14000d86d  pop     r13
0x14000d86f  pop     r12
0x14000d871  pop     rdi
0x14000d872  pop     rsi
0x14000d873  pop     rbp
0x14000d874  retn
0x14000d876  mov     r9d, 80000h
0x14000d87c  mov     dword ptr [rsp+78h+PostIrpRoutine], 0AD4h
0x14000d884  mov     edx, 0C00000D8h
0x14000d889  call    CdRaiseStatusEx
```
