# MupiIoPostProcess

- ea: `0x14001c350`
- end: `0x14001c6d6`
- name: `MupiIoPostProcess`
- size: `902`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001bbb0`

## callees

- `0x140001880`
- `0x140001c90`
- `0x140002700`
- `0x140002754`
- `0x1400029b0`
- `0x14000fe64`
- `0x14001c350`
- `0x14001c6e0`
- `0x14001c7b0`
- `0x14001c8c0`
- `0x14001cbd0`
- `0x14001d310`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001c613`
- `ntoskrnl!KeBugCheckEx` at `0x14001c613`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001c3c1`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001c3c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c69f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c69f`
- `ntoskrnl!IofCompleteRequest` at `0x14001c4e2`
- `ntoskrnl!IofCompleteRequest` at `0x14001c4e2`

## pseudocode

```c
__int64 __fastcall MupiIoPostProcess(_DWORD *P, __int64 a2, int a3)
{
  int v3; // ebx
  int v5; // ecx
  __int64 v6; // rbp
  ULONG_PTR v7; // rsi
  int v8; // ecx
  PFSRTL_PER_FILEOBJECT_CONTEXT v9; // rax
  ULONG_PTR p_InstanceId; // r9
  _QWORD *v11; // r14
  __int64 v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  _QWORD *v18; // rcx
  int v19; // ecx
  _QWORD *i; // rsi
  _QWORD *v21; // rcx
  int v22; // eax

  v3 = P[9];
  if ( v3 < 0 )
  {
    v5 = P[7];
    if ( v5 >= 0 )
    {
      v3 = v5;
    }
    else if ( (int)P[8] < 0 )
    {
      if ( v3 == -1073741802 )
      {
        v3 = P[8];
        if ( v5 != -1073741802 )
          v3 = v5;
      }
    }
    else
    {
      v3 = P[8];
    }
  }
  v6 = *((_QWORD *)P + 2);
  v7 = *((_QWORD *)P + 5);
  v8 = **(unsigned __int8 **)(v6 + 184);
  if ( v8 == 2 )
  {
    v9 = FsRtlRemovePerFileObjectContext(*(PFILE_OBJECT *)(v7 + 144), MupDeviceObject, 0);
    p_InstanceId = (ULONG_PTR)&v9[-1].InstanceId;
    if ( !v9 )
      p_InstanceId = 0;
    if ( p_InstanceId != v7 )
      KeBugCheckEx(0x103u, 2u, v7, p_InstanceId, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
        *(_QWORD *)(v7 + 144),
        v7);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
        *(_QWORD *)(v7 + 144),
        v7);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 4), 0xFFFFFFFF) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, v7);
      }
      v11 = *(_QWORD **)(v7 + 200);
      while ( v11 != (_QWORD *)(v7 + 200) )
      {
        v18 = v11 - 1;
        v11 = (_QWORD *)*v11;
        MupReleaseSurrogateFileContext(v18);
      }
      v12 = *(_QWORD *)(v7 + 168);
      if ( v12 )
        MupReleaseUncProvider(v12);
      v13 = *(void **)(v7 + 184);
      if ( v13 )
        MupReleaseSurrogateProvider(v13);
      v14 = *(_QWORD *)(v7 + 176);
      if ( v14 )
        MupReleaseUncProvider(v14);
      v15 = *(void **)(v7 + 192);
      if ( v15 )
        MupReleaseSurrogateProvider(v15);
      v16 = *(void **)(v7 + 88);
      if ( v16 )
        ExFreePoolWithTag(v16, 0);
      MupCleanupUncHardeningFileContext(v7 + 248);
      ExFreePoolWithTag((PVOID)v7, 0);
    }
    goto LABEL_31;
  }
  if ( **(_BYTE **)(v6 + 184) )
  {
    v19 = v8 - 1;
    if ( v19 )
    {
      if ( v19 != 18 )
        goto LABEL_31;
    }
  }
  if ( v3 < 0 )
  {
LABEL_58:
    MupRemoveFileContext(v7);
    MupReleaseFileContext((char *)v7);
    goto LABEL_31;
  }
  if ( v3 == 260 )
  {
    if ( *(_QWORD *)(v6 + 56) > 2u && !*(_QWORD *)(v7 + 152) && (unsigned int)(*(_DWORD *)(v7 + 160) - 2) <= 1 )
    {
      v22 = MupRestoreFileNameInFileObject(v7, 0, a3);
      if ( v22 )
      {
        v3 = v22;
        *(_QWORD *)(v6 + 56) = 0;
      }
    }
    goto LABEL_58;
  }
  *(_DWORD *)(v7 + 240) &= ~1u;
  for ( i = (_QWORD *)*((_QWORD *)P + 9); i != (_QWORD *)(P + 18); i = (_QWORD *)*i )
  {
    v21 = (_QWORD *)i[3];
    if ( *((_BYTE *)i + 110) )
    {
      v21[5] = i[15];
    }
    else
    {
      MupReleaseSurrogateFileContext(v21);
      i[3] = 0;
    }
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, P, v6, v3);
  }
  *(_DWORD *)(v6 + 48) = v3;
  IofCompleteRequest((PIRP)v6, 2);
  MupReleaseIrpContext(P);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001c350  mov     [rsp+arg_10], rbx
0x14001c355  mov     [rsp+arg_18], rbp
0x14001c35a  push    rsi
0x14001c35b  push    rdi
0x14001c35c  push    r12
0x14001c35e  sub     rsp, 30h
0x14001c362  mov     ebx, [rcx+24h]
0x14001c365  mov     rdi, rcx
0x14001c368  test    ebx, ebx
0x14001c36a  jns     short loc_14001C384
0x14001c36c  mov     ecx, [rcx+1Ch]
0x14001c36f  test    ecx, ecx
0x14001c371  jns     loc_14001C5AF
0x14001c377  mov     eax, [rdi+20h]
0x14001c37a  test    eax, eax
0x14001c37c  js      loc_14001C516
0x14001c382  mov     ebx, eax
0x14001c384  mov     rbp, [rdi+10h]
0x14001c388  lea     r12, WPP_GLOBAL_Control
0x14001c38f  mov     rsi, [rdi+28h]
0x14001c393  mov     [rsp+48h+arg_0], r14
0x14001c398  mov     [rsp+48h+arg_8], r15
0x14001c39d  mov     rax, [rbp+0B8h]
0x14001c3a4  movzx   ecx, byte ptr [rax]
0x14001c3a7  cmp     ecx, 2
0x14001c3aa  jnz     loc_14001C549
0x14001c3b0  mov     rdx, cs:MupDeviceObject; OwnerId
0x14001c3b7  xor     r8d, r8d; InstanceId
0x14001c3ba  mov     rcx, [rsi+90h]; FileObject
0x14001c3c1  call    cs:__imp_FsRtlRemovePerFileObjectContext
0x14001c3c8  nop     dword ptr [rax+rax+00h]
0x14001c3cd  xor     r14d, r14d
0x14001c3d0  test    rax, rax
0x14001c3d3  lea     r9, [rax-8]
0x14001c3d7  cmovz   r9, r14; BugCheckParameter3
0x14001c3db  cmp     r9, rsi
0x14001c3de  jnz     loc_14001C601
0x14001c3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3eb  cmp     rcx, r12
0x14001c3ee  jz      short loc_14001C3FD
0x14001c3f0  test    dword ptr [rcx+2Ch], 4000000h
0x14001c3f7  jnz     loc_14001C620
0x14001c3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c404  cmp     rcx, r12
0x14001c407  jz      short loc_14001C416
0x14001c409  test    dword ptr [rcx+2Ch], 4000000h
0x14001c410  jnz     loc_14001C646
0x14001c416  mov     eax, 0FFFFFFFFh
0x14001c41b  lock xadd [rsi+4], eax
0x14001c420  cmp     eax, 1
0x14001c423  jnz     loc_14001C4C1
0x14001c429  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c430  cmp     rcx, r12
0x14001c433  jz      short loc_14001C442
0x14001c435  test    dword ptr [rcx+2Ch], 4000000h
0x14001c43c  jnz     loc_14001C66C
0x14001c442  lea     r15, [rsi+0C8h]
0x14001c449  mov     r14, [r15]
0x14001c44c  cmp     r14, r15
0x14001c44f  jnz     loc_14001C532
0x14001c455  mov     rcx, [rsi+0A8h]
0x14001c45c  test    rcx, rcx
0x14001c45f  jz      short loc_14001C466
0x14001c461  call    MupReleaseUncProvider
0x14001c466  mov     rcx, [rsi+0B8h]; P
0x14001c46d  test    rcx, rcx
0x14001c470  jz      short loc_14001C477
0x14001c472  call    MupReleaseSurrogateProvider
0x14001c477  mov     rcx, [rsi+0B0h]
0x14001c47e  test    rcx, rcx
0x14001c481  jnz     loc_14001C689
0x14001c487  mov     rcx, [rsi+0C0h]; P
0x14001c48e  test    rcx, rcx
0x14001c491  jnz     loc_14001C693
0x14001c497  mov     rcx, [rsi+58h]; P
0x14001c49b  test    rcx, rcx
0x14001c49e  jnz     loc_14001C69D
0x14001c4a4  lea     rcx, [rsi+0F8h]
0x14001c4ab  call    MupCleanupUncHardeningFileContext
0x14001c4b0  xor     edx, edx; Tag
0x14001c4b2  mov     rcx, rsi; P
0x14001c4b5  call    cs:__imp_ExFreePoolWithTag
0x14001c4bc  nop     dword ptr [rax+rax+00h]
0x14001c4c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c4c8  cmp     rcx, r12
0x14001c4cb  jz      short loc_14001C4DA
0x14001c4cd  test    dword ptr [rcx+2Ch], 4000000h
0x14001c4d4  jnz     loc_14001C6B0
0x14001c4da  mov     dl, 2; PriorityBoost
0x14001c4dc  mov     [rbp+30h], ebx
0x14001c4df  mov     rcx, rbp; Irp
0x14001c4e2  call    cs:__imp_IofCompleteRequest
0x14001c4e9  nop     dword ptr [rax+rax+00h]
0x14001c4ee  mov     rcx, rdi; P
0x14001c4f1  call    MupReleaseIrpContext
0x14001c4f6  mov     r15, [rsp+48h+arg_8]
0x14001c4fb  mov     eax, ebx
0x14001c4fd  mov     rbx, [rsp+48h+arg_10]
0x14001c502  mov     r14, [rsp+48h+arg_0]
0x14001c507  mov     rbp, [rsp+48h+arg_18]
0x14001c50c  add     rsp, 30h
0x14001c510  pop     r12
0x14001c512  pop     rdi
0x14001c513  pop     rsi
0x14001c514  retn
0x14001c516  cmp     ebx, 0C0000016h
0x14001c51c  jnz     loc_14001C384
0x14001c522  cmp     ecx, 0C0000016h
0x14001c528  mov     ebx, eax
0x14001c52a  cmovnz  ebx, ecx
0x14001c52d  jmp     loc_14001C384
0x14001c532  lea     rcx, [r14-8]; P
0x14001c536  mov     r14, [r14]
0x14001c539  call    MupReleaseSurrogateFileContext
0x14001c53e  cmp     r14, r15
0x14001c541  jz      loc_14001C455
0x14001c547  jmp     short loc_14001C532
0x14001c549  test    ecx, ecx
0x14001c54b  jz      short loc_14001C55B
0x14001c54d  sub     ecx, 1
0x14001c550  jz      short loc_14001C55B
0x14001c552  cmp     ecx, 12h
0x14001c555  jnz     loc_14001C4C1
0x14001c55b  test    ebx, ebx
0x14001c55d  js      loc_14001C5EC
0x14001c563  cmp     ebx, 104h
0x14001c569  jz      short loc_14001C5B6
0x14001c56b  and     dword ptr [rsi+0F0h], 0FFFFFFFEh
0x14001c572  lea     r15, [rdi+48h]
0x14001c576  mov     rsi, [r15]
0x14001c579  cmp     rsi, r15
0x14001c57c  jz      loc_14001C4C1
0x14001c582  xor     r14d, r14d
0x14001c585  mov     rcx, [rsi+18h]; P
0x14001c589  cmp     [rsi+6Eh], r14b
0x14001c58d  jnz     short loc_14001C5A5
0x14001c58f  call    MupReleaseSurrogateFileContext
0x14001c594  mov     [rsi+18h], r14
0x14001c598  mov     rsi, [rsi]
0x14001c59b  cmp     rsi, r15
0x14001c59e  jnz     short loc_14001C585
0x14001c5a0  jmp     loc_14001C4C1
0x14001c5a5  mov     rax, [rsi+78h]
0x14001c5a9  mov     [rcx+28h], rax
0x14001c5ad  jmp     short loc_14001C598
0x14001c5af  mov     ebx, ecx
0x14001c5b1  jmp     loc_14001C384
0x14001c5b6  cmp     qword ptr [rbp+38h], 2
0x14001c5bb  jbe     short loc_14001C5EC
0x14001c5bd  cmp     qword ptr [rsi+98h], 0
0x14001c5c5  jnz     short loc_14001C5EC
0x14001c5c7  mov     eax, [rsi+0A0h]
0x14001c5cd  sub     eax, 2
0x14001c5d0  cmp     eax, 1
0x14001c5d3  ja      short loc_14001C5EC
0x14001c5d5  xor     edx, edx
0x14001c5d7  mov     rcx, rsi
0x14001c5da  call    MupRestoreFileNameInFileObject
0x14001c5df  test    eax, eax
0x14001c5e1  jz      short loc_14001C5EC
0x14001c5e3  xor     r14d, r14d
0x14001c5e6  mov     ebx, eax
0x14001c5e8  mov     [rbp+38h], r14
0x14001c5ec  mov     rcx, rsi; BugCheckParameter2
0x14001c5ef  call    MupRemoveFileContext
0x14001c5f4  mov     rcx, rsi; P
0x14001c5f7  call    MupReleaseFileContext
0x14001c5fc  jmp     loc_14001C4C1
0x14001c601  mov     r8, rsi; BugCheckParameter2
0x14001c604  mov     [rsp+48h+BugCheckParameter4], r14; BugCheckParameter4
0x14001c609  mov     edx, 2; BugCheckParameter1
0x14001c60e  mov     ecx, 103h; BugCheckCode
0x14001c613  call    cs:__imp_KeBugCheckEx
0x14001c620  mov     r9, [rsi+90h]
0x14001c627  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c62e  mov     rcx, [rcx+18h]
0x14001c632  mov     edx, 0Dh
0x14001c637  mov     [rsp+48h+BugCheckParameter4], rsi
0x14001c63c  call    WPP_SF_qq
0x14001c641  jmp     loc_14001C3FD
0x14001c646  mov     r9, [rsi+90h]
0x14001c64d  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c654  mov     rcx, [rcx+18h]
0x14001c658  mov     edx, 0Ah
0x14001c65d  mov     [rsp+48h+BugCheckParameter4], rsi
0x14001c662  call    WPP_SF_qq
0x14001c667  jmp     loc_14001C416
0x14001c66c  mov     rcx, [rcx+18h]
0x14001c670  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c677  mov     edx, 0Bh
0x14001c67c  mov     r9, rsi
0x14001c67f  call    WPP_SF_q
0x14001c684  jmp     loc_14001C442
0x14001c689  call    MupReleaseUncProvider
0x14001c68e  jmp     loc_14001C487
0x14001c693  call    MupReleaseSurrogateProvider
0x14001c698  jmp     loc_14001C497
0x14001c69d  xor     edx, edx; Tag
0x14001c69f  call    cs:__imp_ExFreePoolWithTag
0x14001c6a6  nop     dword ptr [rax+rax+00h]
0x14001c6ab  jmp     loc_14001C4A4
0x14001c6b0  mov     rcx, [rcx+18h]
0x14001c6b4  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001c6bb  mov     edx, 2Bh ; '+'
0x14001c6c0  mov     [rsp+48h+var_20], ebx
0x14001c6c4  mov     r9, rdi
0x14001c6c7  mov     [rsp+48h+BugCheckParameter4], rbp
0x14001c6cc  call    WPP_SF_qqD
0x14001c6d1  jmp     loc_14001C4DA
```
