# MupiIoPostProcess

- ea: `0x14001c300`
- end: `0x14001c686`
- name: `MupiIoPostProcess`
- size: `902`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001bb60`

## callees

- `0x140001880`
- `0x140001c90`
- `0x140002700`
- `0x140002754`
- `0x1400029b0`
- `0x14000fe64`
- `0x14001c300`
- `0x14001c690`
- `0x14001c760`
- `0x14001c870`
- `0x14001cb80`
- `0x14001d2c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001c5c3`
- `ntoskrnl!KeBugCheckEx` at `0x14001c5c3`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001c371`
- `ntoskrnl!FsRtlRemovePerFileObjectContext` at `0x14001c371`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c64f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c64f`
- `ntoskrnl!IofCompleteRequest` at `0x14001c492`
- `ntoskrnl!IofCompleteRequest` at `0x14001c492`

## pseudocode

```c
__int64 __fastcall MupiIoPostProcess(_DWORD *P)
{
  int v1; // ebx
  int v3; // ecx
  __int64 v4; // rbp
  ULONG_PTR v5; // rsi
  int v6; // ecx
  PFSRTL_PER_FILEOBJECT_CONTEXT v7; // rax
  ULONG_PTR p_InstanceId; // r9
  _QWORD *v9; // r14
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  _QWORD *v14; // rcx
  int v15; // ecx
  _QWORD *i; // rsi
  _QWORD *v17; // rcx
  int v18; // eax

  v1 = P[9];
  if ( v1 < 0 )
  {
    v3 = P[7];
    if ( v3 >= 0 )
    {
      v1 = v3;
    }
    else if ( (int)P[8] < 0 )
    {
      if ( v1 == -1073741802 )
      {
        v1 = P[8];
        if ( v3 != -1073741802 )
          v1 = v3;
      }
    }
    else
    {
      v1 = P[8];
    }
  }
  v4 = *((_QWORD *)P + 2);
  v5 = *((_QWORD *)P + 5);
  v6 = **(unsigned __int8 **)(v4 + 184);
  if ( v6 == 2 )
  {
    v7 = FsRtlRemovePerFileObjectContext(*(PFILE_OBJECT *)(v5 + 144), MupDeviceObject, 0);
    p_InstanceId = (ULONG_PTR)&v7[-1].InstanceId;
    if ( !v7 )
      p_InstanceId = 0;
    if ( p_InstanceId != v5 )
      KeBugCheckEx(0x103u, 2u, v5, p_InstanceId, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
        *(_QWORD *)(v5 + 144),
        v5);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
        *(_QWORD *)(v5 + 144),
        v5);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 4), 0xFFFFFFFF) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, v5);
      }
      v9 = *(_QWORD **)(v5 + 200);
      while ( v9 != (_QWORD *)(v5 + 200) )
      {
        v14 = v9 - 1;
        v9 = (_QWORD *)*v9;
        MupReleaseSurrogateFileContext(v14);
      }
      if ( *(_QWORD *)(v5 + 168) )
        MupReleaseUncProvider();
      v10 = *(void **)(v5 + 184);
      if ( v10 )
        MupReleaseSurrogateProvider(v10);
      if ( *(_QWORD *)(v5 + 176) )
        MupReleaseUncProvider();
      v11 = *(void **)(v5 + 192);
      if ( v11 )
        MupReleaseSurrogateProvider(v11);
      v12 = *(void **)(v5 + 88);
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
      MupCleanupUncHardeningFileContext(v5 + 248);
      ExFreePoolWithTag((PVOID)v5, 0);
    }
    goto LABEL_31;
  }
  if ( **(_BYTE **)(v4 + 184) )
  {
    v15 = v6 - 1;
    if ( v15 )
    {
      if ( v15 != 18 )
        goto LABEL_31;
    }
  }
  if ( v1 < 0 )
  {
LABEL_58:
    MupRemoveFileContext(v5);
    MupReleaseFileContext((PVOID)v5);
    goto LABEL_31;
  }
  if ( v1 == 260 )
  {
    if ( *(_QWORD *)(v4 + 56) > 2u && !*(_QWORD *)(v5 + 152) && (unsigned int)(*(_DWORD *)(v5 + 160) - 2) <= 1 )
    {
      v18 = MupRestoreFileNameInFileObject(v5, 0);
      if ( v18 )
      {
        v1 = v18;
        *(_QWORD *)(v4 + 56) = 0;
      }
    }
    goto LABEL_58;
  }
  *(_DWORD *)(v5 + 240) &= ~1u;
  for ( i = (_QWORD *)*((_QWORD *)P + 9); i != (_QWORD *)(P + 18); i = (_QWORD *)*i )
  {
    v17 = (_QWORD *)i[3];
    if ( *((_BYTE *)i + 110) )
    {
      v17[5] = i[15];
    }
    else
    {
      MupReleaseSurrogateFileContext(v17);
      i[3] = 0;
    }
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids, P, v4, v1);
  }
  *(_DWORD *)(v4 + 48) = v1;
  IofCompleteRequest((PIRP)v4, 2);
  MupReleaseIrpContext(P);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001c300  mov     [rsp+arg_10], rbx
0x14001c305  mov     [rsp+arg_18], rbp
0x14001c30a  push    rsi
0x14001c30b  push    rdi
0x14001c30c  push    r12
0x14001c30e  sub     rsp, 30h
0x14001c312  mov     ebx, [rcx+24h]
0x14001c315  mov     rdi, rcx
0x14001c318  test    ebx, ebx
0x14001c31a  jns     short loc_14001C334
0x14001c31c  mov     ecx, [rcx+1Ch]
0x14001c31f  test    ecx, ecx
0x14001c321  jns     loc_14001C55F
0x14001c327  mov     eax, [rdi+20h]
0x14001c32a  test    eax, eax
0x14001c32c  js      loc_14001C4C6
0x14001c332  mov     ebx, eax
0x14001c334  mov     rbp, [rdi+10h]
0x14001c338  lea     r12, WPP_GLOBAL_Control
0x14001c33f  mov     rsi, [rdi+28h]
0x14001c343  mov     [rsp+48h+arg_0], r14
0x14001c348  mov     [rsp+48h+arg_8], r15
0x14001c34d  mov     rax, [rbp+0B8h]
0x14001c354  movzx   ecx, byte ptr [rax]
0x14001c357  cmp     ecx, 2
0x14001c35a  jnz     loc_14001C4F9
0x14001c360  mov     rdx, cs:MupDeviceObject; OwnerId
0x14001c367  xor     r8d, r8d; InstanceId
0x14001c36a  mov     rcx, [rsi+90h]; FileObject
0x14001c371  call    cs:__imp_FsRtlRemovePerFileObjectContext
0x14001c378  nop     dword ptr [rax+rax+00h]
0x14001c37d  xor     r14d, r14d
0x14001c380  test    rax, rax
0x14001c383  lea     r9, [rax-8]
0x14001c387  cmovz   r9, r14; BugCheckParameter3
0x14001c38b  cmp     r9, rsi
0x14001c38e  jnz     loc_14001C5B1
0x14001c394  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c39b  cmp     rcx, r12
0x14001c39e  jz      short loc_14001C3AD
0x14001c3a0  test    dword ptr [rcx+2Ch], 4000000h
0x14001c3a7  jnz     loc_14001C5D0
0x14001c3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3b4  cmp     rcx, r12
0x14001c3b7  jz      short loc_14001C3C6
0x14001c3b9  test    dword ptr [rcx+2Ch], 4000000h
0x14001c3c0  jnz     loc_14001C5F6
0x14001c3c6  mov     eax, 0FFFFFFFFh
0x14001c3cb  lock xadd [rsi+4], eax
0x14001c3d0  cmp     eax, 1
0x14001c3d3  jnz     loc_14001C471
0x14001c3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3e0  cmp     rcx, r12
0x14001c3e3  jz      short loc_14001C3F2
0x14001c3e5  test    dword ptr [rcx+2Ch], 4000000h
0x14001c3ec  jnz     loc_14001C61C
0x14001c3f2  lea     r15, [rsi+0C8h]
0x14001c3f9  mov     r14, [r15]
0x14001c3fc  cmp     r14, r15
0x14001c3ff  jnz     loc_14001C4E2
0x14001c405  mov     rcx, [rsi+0A8h]
0x14001c40c  test    rcx, rcx
0x14001c40f  jz      short loc_14001C416
0x14001c411  call    MupReleaseUncProvider
0x14001c416  mov     rcx, [rsi+0B8h]; P
0x14001c41d  test    rcx, rcx
0x14001c420  jz      short loc_14001C427
0x14001c422  call    MupReleaseSurrogateProvider
0x14001c427  mov     rcx, [rsi+0B0h]
0x14001c42e  test    rcx, rcx
0x14001c431  jnz     loc_14001C639
0x14001c437  mov     rcx, [rsi+0C0h]; P
0x14001c43e  test    rcx, rcx
0x14001c441  jnz     loc_14001C643
0x14001c447  mov     rcx, [rsi+58h]; P
0x14001c44b  test    rcx, rcx
0x14001c44e  jnz     loc_14001C64D
0x14001c454  lea     rcx, [rsi+0F8h]
0x14001c45b  call    MupCleanupUncHardeningFileContext
0x14001c460  xor     edx, edx; Tag
0x14001c462  mov     rcx, rsi; P
0x14001c465  call    cs:__imp_ExFreePoolWithTag
0x14001c46c  nop     dword ptr [rax+rax+00h]
0x14001c471  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c478  cmp     rcx, r12
0x14001c47b  jz      short loc_14001C48A
0x14001c47d  test    dword ptr [rcx+2Ch], 4000000h
0x14001c484  jnz     loc_14001C660
0x14001c48a  mov     dl, 2; PriorityBoost
0x14001c48c  mov     [rbp+30h], ebx
0x14001c48f  mov     rcx, rbp; Irp
0x14001c492  call    cs:__imp_IofCompleteRequest
0x14001c499  nop     dword ptr [rax+rax+00h]
0x14001c49e  mov     rcx, rdi; P
0x14001c4a1  call    MupReleaseIrpContext
0x14001c4a6  mov     r15, [rsp+48h+arg_8]
0x14001c4ab  mov     eax, ebx
0x14001c4ad  mov     rbx, [rsp+48h+arg_10]
0x14001c4b2  mov     r14, [rsp+48h+arg_0]
0x14001c4b7  mov     rbp, [rsp+48h+arg_18]
0x14001c4bc  add     rsp, 30h
0x14001c4c0  pop     r12
0x14001c4c2  pop     rdi
0x14001c4c3  pop     rsi
0x14001c4c4  retn
0x14001c4c6  cmp     ebx, 0C0000016h
0x14001c4cc  jnz     loc_14001C334
0x14001c4d2  cmp     ecx, 0C0000016h
0x14001c4d8  mov     ebx, eax
0x14001c4da  cmovnz  ebx, ecx
0x14001c4dd  jmp     loc_14001C334
0x14001c4e2  lea     rcx, [r14-8]; P
0x14001c4e6  mov     r14, [r14]
0x14001c4e9  call    MupReleaseSurrogateFileContext
0x14001c4ee  cmp     r14, r15
0x14001c4f1  jz      loc_14001C405
0x14001c4f7  jmp     short loc_14001C4E2
0x14001c4f9  test    ecx, ecx
0x14001c4fb  jz      short loc_14001C50B
0x14001c4fd  sub     ecx, 1
0x14001c500  jz      short loc_14001C50B
0x14001c502  cmp     ecx, 12h
0x14001c505  jnz     loc_14001C471
0x14001c50b  test    ebx, ebx
0x14001c50d  js      loc_14001C59C
0x14001c513  cmp     ebx, 104h
0x14001c519  jz      short loc_14001C566
0x14001c51b  and     dword ptr [rsi+0F0h], 0FFFFFFFEh
0x14001c522  lea     r15, [rdi+48h]
0x14001c526  mov     rsi, [r15]
0x14001c529  cmp     rsi, r15
0x14001c52c  jz      loc_14001C471
0x14001c532  xor     r14d, r14d
0x14001c535  mov     rcx, [rsi+18h]; P
0x14001c539  cmp     [rsi+6Eh], r14b
0x14001c53d  jnz     short loc_14001C555
0x14001c53f  call    MupReleaseSurrogateFileContext
0x14001c544  mov     [rsi+18h], r14
0x14001c548  mov     rsi, [rsi]
0x14001c54b  cmp     rsi, r15
0x14001c54e  jnz     short loc_14001C535
0x14001c550  jmp     loc_14001C471
0x14001c555  mov     rax, [rsi+78h]
0x14001c559  mov     [rcx+28h], rax
0x14001c55d  jmp     short loc_14001C548
0x14001c55f  mov     ebx, ecx
0x14001c561  jmp     loc_14001C334
0x14001c566  cmp     qword ptr [rbp+38h], 2
0x14001c56b  jbe     short loc_14001C59C
0x14001c56d  cmp     qword ptr [rsi+98h], 0
0x14001c575  jnz     short loc_14001C59C
0x14001c577  mov     eax, [rsi+0A0h]
0x14001c57d  sub     eax, 2
0x14001c580  cmp     eax, 1
0x14001c583  ja      short loc_14001C59C
0x14001c585  xor     edx, edx
0x14001c587  mov     rcx, rsi
0x14001c58a  call    MupRestoreFileNameInFileObject
0x14001c58f  test    eax, eax
0x14001c591  jz      short loc_14001C59C
0x14001c593  xor     r14d, r14d
0x14001c596  mov     ebx, eax
0x14001c598  mov     [rbp+38h], r14
0x14001c59c  mov     rcx, rsi; BugCheckParameter2
0x14001c59f  call    MupRemoveFileContext
0x14001c5a4  mov     rcx, rsi; P
0x14001c5a7  call    MupReleaseFileContext
0x14001c5ac  jmp     loc_14001C471
0x14001c5b1  mov     r8, rsi; BugCheckParameter2
0x14001c5b4  mov     [rsp+48h+BugCheckParameter4], r14; BugCheckParameter4
0x14001c5b9  mov     edx, 2; BugCheckParameter1
0x14001c5be  mov     ecx, 103h; BugCheckCode
0x14001c5c3  call    cs:__imp_KeBugCheckEx
0x14001c5d0  mov     r9, [rsi+90h]
0x14001c5d7  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c5de  mov     rcx, [rcx+18h]
0x14001c5e2  mov     edx, 0Dh
0x14001c5e7  mov     [rsp+48h+BugCheckParameter4], rsi
0x14001c5ec  call    WPP_SF_qq
0x14001c5f1  jmp     loc_14001C3AD
0x14001c5f6  mov     r9, [rsi+90h]
0x14001c5fd  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c604  mov     rcx, [rcx+18h]
0x14001c608  mov     edx, 0Ah
0x14001c60d  mov     [rsp+48h+BugCheckParameter4], rsi
0x14001c612  call    WPP_SF_qq
0x14001c617  jmp     loc_14001C3C6
0x14001c61c  mov     rcx, [rcx+18h]
0x14001c620  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001c627  mov     edx, 0Bh
0x14001c62c  mov     r9, rsi
0x14001c62f  call    WPP_SF_q
0x14001c634  jmp     loc_14001C3F2
0x14001c639  call    MupReleaseUncProvider
0x14001c63e  jmp     loc_14001C437
0x14001c643  call    MupReleaseSurrogateProvider
0x14001c648  jmp     loc_14001C447
0x14001c64d  xor     edx, edx; Tag
0x14001c64f  call    cs:__imp_ExFreePoolWithTag
0x14001c656  nop     dword ptr [rax+rax+00h]
0x14001c65b  jmp     loc_14001C454
0x14001c660  mov     rcx, [rcx+18h]
0x14001c664  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001c66b  mov     edx, 2Bh ; '+'
0x14001c670  mov     [rsp+48h+var_20], ebx
0x14001c674  mov     r9, rdi
0x14001c677  mov     [rsp+48h+BugCheckParameter4], rbp
0x14001c67c  call    WPP_SF_qqD
0x14001c681  jmp     loc_14001C48A
```
