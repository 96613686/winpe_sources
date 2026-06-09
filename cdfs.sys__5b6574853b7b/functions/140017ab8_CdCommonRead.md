# CdCommonRead

- ea: `0x140017ab8`
- end: `0x14001815a`
- name: `CdCommonRead`
- size: `1698`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PIRP Irp@<rdx>, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001114`
- `0x140001160`
- `0x140002b10`
- `0x140003300`
- `0x14000f27c`
- `0x14000f618`
- `0x140017ab8`
- `0x1400181a4`
- `0x14001a2a0`
- `0x14001a9a0`

## import_xrefs

- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140017e82`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140017e82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018054`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bddc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018054`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bddc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017d57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017d57`
- `ntoskrnl!CcInitializeCacheMap` at `0x140017f3b`
- `ntoskrnl!CcInitializeCacheMap` at `0x140017f3b`
- `ntoskrnl!KeInitializeEvent` at `0x140017dc0`
- `ntoskrnl!KeInitializeEvent` at `0x140017dc0`
- `ntoskrnl!FsRtlCheckOplock` at `0x140017c45`
- `ntoskrnl!FsRtlCheckOplock` at `0x140017c45`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017eda`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f9f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017eda`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f9f`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140017c7d`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140017c7d`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140017f51`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140017f51`
- `ntoskrnl!CcCopyRead` at `0x140017fd7`
- `ntoskrnl!CcCopyRead` at `0x140017fd7`
- `ntoskrnl!CcMdlRead` at `0x140018012`
- `ntoskrnl!CcMdlRead` at `0x140018012`

## pseudocode

```c
__int64 __fastcall CdCommonRead(__int64 a1, PIRP Irp)
{
  PIRP v2; // rsi
  __int64 v3; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  PFILE_OBJECT FileObject; // rax
  int v7; // r14d
  __int64 FsContext; // r15
  unsigned __int64 v9; // r13
  NTSTATUS Status; // ebx
  ULONG Flags; // ecx
  int v12; // r8d
  int v13; // ecx
  int v14; // eax
  __int64 v15; // r8
  FILE_LOCK *v16; // rcx
  union _LARGE_INTEGER v17; // rcx
  ULONG v18; // r13d
  ULONG v19; // r14d
  _OWORD *v20; // rdx
  _OWORD *PoolWithTag; // rax
  NTSTATUS v22; // eax
  char v23; // al
  __int64 v24; // rax
  __int64 v25; // rcx
  char *v26; // rax
  struct _FILE_OBJECT *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  PVOID v30; // rax
  __int64 v31; // r8
  __int64 v32; // rdx
  union _LARGE_INTEGER FileOffset; // [rsp+38h] [rbp-A0h] BYREF
  int v34; // [rsp+40h] [rbp-98h]
  int v35; // [rsp+44h] [rbp-94h]
  union _LARGE_INTEGER v36; // [rsp+48h] [rbp-90h]
  ULONG v37; // [rsp+50h] [rbp-88h]
  __int64 Length; // [rsp+58h] [rbp-80h]
  __int64 v39; // [rsp+60h] [rbp-78h]
  _OWORD v40[7]; // [rsp+68h] [rbp-70h] BYREF
  unsigned int v41; // [rsp+F0h] [rbp+18h]
  int v42; // [rsp+F8h] [rbp+20h]

  v2 = Irp;
  v3 = a1;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileOffset.QuadPart = 0;
  memset(v40, 0, 44);
  if ( !CurrentStackLocation->Parameters.Read.Length )
  {
    CdCompleteRequest(a1, Irp, 0);
    return 0;
  }
  FileObject = CurrentStackLocation->FileObject;
  v7 = (__int64)FileObject->FsContext2 & 7;
  if ( v7 )
  {
    FsContext = (__int64)FileObject->FsContext;
    v9 = (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    FsContext = 0;
    v9 = 0;
  }
  v39 = FsContext;
  if ( !v7 || v7 == 3 )
  {
    Status = -1073741808;
LABEL_92:
    CdCompleteRequest(a1, Irp, (unsigned int)Status);
    return (unsigned int)Status;
  }
  Status = 0;
  v41 = *(_DWORD *)(a1 + 32) & 4;
  Flags = Irp->Flags;
  v12 = Flags & 2;
  v42 = v12;
  v35 = FileObject->Flags & 2;
  FileOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v37 = Length;
  v36.QuadPart = FileOffset.QuadPart + Length;
  v13 = Flags & 1;
  v14 = 1;
  if ( v7 != 2 )
    v14 = v13;
  v34 = v14;
  CdAcquireResource(v3, *(_QWORD *)(FsContext + 8), 0, (unsigned int)(v12 != 0) + 1);
  if ( v7 != 2 || !v9 || (*(_DWORD *)(v9 + 4) & 0x10) == 0 )
    CdVerifyFcbOperation(v3, FsContext);
  v15 = v41;
  if ( v41 || !v34 || (*(_DWORD *)(FsContext + 172) & 0x1C) == 0 )
  {
    if ( v7 == 4 )
    {
      Status = FsRtlCheckOplock((POPLOCK)(FsContext + 88), v2, (PVOID)v3, CdOplockComplete, CdPrePostIrp);
      if ( Status )
      {
        v2 = 0;
        v3 = 0;
        goto LABEL_86;
      }
      if ( !v42 )
      {
        v16 = *(FILE_LOCK **)(FsContext + 472);
        if ( v16 )
        {
          if ( !FsRtlCheckLockForReadAccess(v16, v2) )
          {
            Status = -1073741740;
            goto LABEL_86;
          }
        }
      }
      v15 = v41;
    }
    if ( v7 == 2 && (*(_DWORD *)(v9 + 4) & 0x20) != 0 )
      goto LABEL_33;
    v17 = *(union _LARGE_INTEGER *)(FsContext + 32);
    if ( FileOffset.QuadPart >= v17.QuadPart )
    {
      Status = -1073741807;
      goto LABEL_86;
    }
    if ( v36.QuadPart <= v17.QuadPart )
    {
LABEL_33:
      v18 = Length;
    }
    else
    {
      v18 = v17.LowPart - FileOffset.LowPart;
      v36 = *(union _LARGE_INTEGER *)(FsContext + 32);
    }
    if ( v34 )
    {
      v19 = *(_DWORD *)(*(_QWORD *)(FsContext + 120) + 444LL)
          & (v18 + *(_DWORD *)(*(_QWORD *)(FsContext + 120) + 440LL));
      if ( ((FileOffset.LowPart | v19) & 0x7FF) != 0 || v19 > v37 )
      {
        if ( !(_DWORD)v15 )
          CdRaiseStatusEx(v3, 3221225688LL, v15, 1441792, 318);
        v19 = v18;
      }
      v20 = *(_OWORD **)(v3 + 48);
      if ( !v20 || (*(_DWORD *)(v3 + 32) & 0x100) == 0 )
      {
        if ( (_DWORD)v15 )
        {
          *(_QWORD *)(v3 + 48) = v40;
          *(_DWORD *)(v3 + 32) &= ~0x100u;
          v20 = v40;
        }
        else
        {
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, 0x30u, 0x6F696443u);
          v20 = PoolWithTag;
          if ( !ExPoolZeroingNativelySupported && PoolWithTag )
          {
            *PoolWithTag = 0;
            PoolWithTag[1] = 0;
            PoolWithTag[2] = 0;
          }
          *(_QWORD *)(v3 + 48) = PoolWithTag;
          *(_DWORD *)(v3 + 32) |= 0x100u;
        }
      }
      *v20 = 0;
      v20[1] = 0;
      v20[2] = 0;
      *(_BYTE *)(*(_QWORD *)(v3 + 48) + 20LL) = BYTE1(*(_DWORD *)(v3 + 32)) & 1;
      if ( v41 )
      {
        KeInitializeEvent((PRKEVENT)(*(_QWORD *)(v3 + 48) + 24LL), NotificationEvent, 0);
      }
      else
      {
        *(_QWORD *)(*(_QWORD *)(v3 + 48) + 32LL) = KeGetCurrentThread();
        *(_QWORD *)(*(_QWORD *)(v3 + 48) + 24LL) = *(_QWORD *)(FsContext + 8);
        *(_DWORD *)(*(_QWORD *)(v3 + 48) + 40LL) = v18;
      }
      v2->IoStatus.Information = v19;
      if ( (*(_DWORD *)(FsContext + 172) & 0x1C) != 0 )
        v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))CdNonCachedXARead)(
                v3,
                FsContext,
                (union _LARGE_INTEGER)FileOffset.QuadPart,
                v19);
      else
        v22 = CdNonCachedRead(v3, FsContext, FileOffset.QuadPart, v19);
      Status = v22;
      if ( v22 == 259 )
      {
        v2 = 0;
        v23 = 0;
        goto LABEL_87;
      }
      if ( v22 >= 0 )
      {
        if ( v19 != v18 )
        {
          v24 = *(_QWORD *)(v3 + 8);
          v25 = *(_QWORD *)(v24 + 8);
          if ( v25 )
          {
            if ( (*(_BYTE *)(v25 + 10) & 5) != 0 )
              v26 = *(char **)(v25 + 24);
            else
              v26 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v25, 0, MmCached, 0, 0, 0x40000010u);
          }
          else
          {
            v26 = *(char **)(v24 + 112);
          }
          if ( !v26 )
            CdRaiseStatusEx(v3, 3221225626LL, 0, 1441792, 438);
          memset(&v26[v18], 0, v19 - v18);
          v2->IoStatus.Information = v18;
        }
      }
      else
      {
        v2->IoStatus.Information = 0;
        if ( (unsigned int)(v22 + 1073741662) <= 1
          || v22 == -1073741643
          || (unsigned int)(v22 + 1073741806) <= 2
          || v22 == -2147483626 )
        {
          CdRaiseStatusEx(v3, (unsigned int)v22, 0, 1441792, 427);
        }
        Status = FsRtlNormalizeNtstatus(v22, -1073741591);
      }
    }
    else
    {
      v27 = CurrentStackLocation->FileObject;
      if ( !v27->PrivateCacheMap )
      {
        CcInitializeCacheMap(v27, (PCC_FILE_SIZES)(FsContext + 24), 0, &Callbacks, (PVOID)FsContext);
        CcSetReadAheadGranularity(CurrentStackLocation->FileObject, 0x10000u);
      }
      if ( (*(_BYTE *)(v3 + 65) & 2) != 0 )
      {
        CcMdlRead(CurrentStackLocation->FileObject, &FileOffset, v18, &v2->MdlAddress, &v2->IoStatus);
        Status = v2->IoStatus.Status;
      }
      else
      {
        v28 = *(_QWORD *)(v3 + 8);
        v29 = *(_QWORD *)(v28 + 8);
        if ( v29 )
        {
          if ( (*(_BYTE *)(v29 + 10) & 5) != 0 )
            v30 = *(PVOID *)(v29 + 24);
          else
            v30 = MmMapLockedPagesSpecifyCache((PMDL)v29, 0, MmCached, 0, 0, 0x40000010u);
        }
        else
        {
          v30 = *(PVOID *)(v28 + 112);
        }
        if ( !v30 )
          CdRaiseStatusEx(v3, 3221225626LL, 0, 1441792, 494);
        if ( !CcCopyRead(CurrentStackLocation->FileObject, &FileOffset, v18, v41 != 0, v30, &v2->IoStatus) )
          goto LABEL_18;
        v32 = (unsigned int)v2->IoStatus.Status;
        if ( (int)v32 < 0 )
        {
          LOBYTE(v31) = 1;
          CdRaiseStatusEx(v3, v32, v31, 1441792, 516);
        }
      }
    }
    if ( v35 && !v42 && Status >= 0 )
      CurrentStackLocation->FileObject->CurrentByteOffset = v36;
    goto LABEL_86;
  }
  *(_DWORD *)(v3 + 32) |= 8u;
LABEL_18:
  Status = -1073741608;
LABEL_86:
  v23 = 1;
LABEL_87:
  if ( v23 )
    ExReleaseResourceLite(*(PERESOURCE *)(FsContext + 8));
  Irp = v2;
  a1 = v3;
  if ( Status != -1073741608 )
    goto LABEL_92;
  CdPrePostIrp((PVOID)v3, v2);
  CdAddToWorkque(v3, v2);
  return 259;
}

```

## disassembly

```asm
0x140017ab8  mov     r11, rsp
0x140017abb  mov     [r11+8], rcx
0x140017abf  push    rbx
0x140017ac0  push    rsi
0x140017ac1  push    rdi
0x140017ac2  push    r12
0x140017ac4  push    r13
0x140017ac6  push    r14
0x140017ac8  push    r15
0x140017aca  sub     rsp, 0A0h
0x140017ad1  mov     rsi, rdx
0x140017ad4  mov     rdi, rcx
0x140017ad7  mov     r12, [rdx+0B8h]
0x140017ade  mov     qword ptr [rsp+0D8h+FileOffset], 0
0x140017ae7  xor     eax, eax
0x140017ae9  xorps   xmm0, xmm0
0x140017aec  movups  [rsp+0D8h+var_70], xmm0
0x140017af1  movups  xmmword ptr [rsp+0D8h+var_60], xmm0
0x140017af6  movups  xmmword ptr [r11-54h], xmm0
0x140017afb  cmp     [r12+8], eax
0x140017b00  jnz     short loc_140017B11
0x140017b02  xor     r8d, r8d
0x140017b05  call    CdCompleteRequest
0x140017b0a  xor     eax, eax
0x140017b0c  jmp     loc_140018094
0x140017b11  mov     rax, [r12+30h]
0x140017b16  mov     r14d, [rax+20h]
0x140017b1a  and     r14d, 7
0x140017b1e  jnz     short loc_140017B28
0x140017b20  xor     r15d, r15d
0x140017b23  xor     r13d, r13d
0x140017b26  jmp     short loc_140017B34
0x140017b28  mov     r15, [rax+18h]
0x140017b2c  mov     r13, [rax+20h]
0x140017b30  and     r13, 0FFFFFFFFFFFFFFF8h
0x140017b34  mov     [rsp+0D8h+var_78], r15
0x140017b39  test    r14d, r14d
0x140017b3c  jz      loc_140018085
0x140017b42  cmp     r14d, 3
0x140017b46  jz      loc_140018085
0x140017b4c  xor     ebx, ebx
0x140017b4e  mov     ecx, [rcx+20h]
0x140017b51  and     ecx, 4
0x140017b54  mov     [rsp+0D8h+arg_10], ecx
0x140017b5b  setnz   [rsp+0D8h+Wait]
0x140017b63  mov     ecx, [rdx+10h]
0x140017b66  mov     r8d, ecx
0x140017b69  and     r8d, 2
0x140017b6d  mov     [rsp+0D8h+arg_18], r8d
0x140017b75  mov     eax, [rax+50h]
0x140017b78  and     eax, 2
0x140017b7b  mov     [rsp+0D8h+var_94], eax
0x140017b7f  mov     rax, [r12+18h]
0x140017b84  mov     qword ptr [rsp+0D8h+FileOffset], rax
0x140017b89  mov     edx, [r12+8]
0x140017b8e  mov     [rsp+0D8h+var_80], rdx
0x140017b93  mov     [rsp+0D8h+var_88], edx
0x140017b97  add     rdx, rax
0x140017b9a  mov     [rsp+0D8h+var_90], rdx
0x140017b9f  lea     edx, [rbx+1]
0x140017ba2  and     ecx, edx
0x140017ba4  mov     eax, edx
0x140017ba6  cmp     r14d, 2
0x140017baa  cmovnz  eax, ecx
0x140017bad  mov     [rsp+0D8h+var_98], eax
0x140017bb1  mov     eax, r8d
0x140017bb4  neg     eax
0x140017bb6  sbb     r9d, r9d
0x140017bb9  neg     r9d
0x140017bbc  add     r9d, edx
0x140017bbf  xor     r8d, r8d
0x140017bc2  mov     rdx, [r15+8]
0x140017bc6  mov     rcx, rdi
0x140017bc9  call    CdAcquireResource
0x140017bce  mov     [rsp+0D8h+var_A8], 1
0x140017bd3  cmp     r14d, 2
0x140017bd7  jnz     short loc_140017BE6
0x140017bd9  test    r13, r13
0x140017bdc  jz      short loc_140017BE6
0x140017bde  mov     eax, [r13+4]
0x140017be2  test    al, 10h
0x140017be4  jnz     short loc_140017BF1
0x140017be6  mov     rdx, r15
0x140017be9  mov     rcx, rdi
0x140017bec  call    CdVerifyFcbOperation
0x140017bf1  mov     r8d, [rsp+0D8h+arg_10]
0x140017bf9  test    r8d, r8d
0x140017bfc  jnz     short loc_140017C22
0x140017bfe  cmp     [rsp+0D8h+var_98], r8d
0x140017c03  jz      short loc_140017C22
0x140017c05  mov     eax, [r15+0ACh]
0x140017c0c  test    al, 1Ch
0x140017c0e  jz      short loc_140017C22
0x140017c10  or      dword ptr [rdi+20h], 8
0x140017c14  mov     ebx, 0C00000D8h
0x140017c19  mov     [rsp+0D8h+var_A4], ebx
0x140017c1d  jmp     loc_140018047
0x140017c22  cmp     r14d, 4
0x140017c26  jnz     short loc_140017C9C
0x140017c28  lea     rcx, [r15+58h]; Oplock
0x140017c2c  lea     rax, CdPrePostIrp
0x140017c33  mov     [rsp+0D8h+PostIrpRoutine], rax; PostIrpRoutine
0x140017c38  lea     r9, CdOplockComplete; CompletionRoutine
0x140017c3f  mov     r8, rdi; Context
0x140017c42  mov     rdx, rsi; Irp
0x140017c45  call    cs:__imp_FsRtlCheckOplock
0x140017c4c  nop     dword ptr [rax+rax+00h]
0x140017c51  mov     ebx, eax
0x140017c53  mov     [rsp+0D8h+var_A4], eax
0x140017c57  test    eax, eax
0x140017c59  jz      short loc_140017C64
0x140017c5b  xor     esi, esi
0x140017c5d  xor     edi, edi
0x140017c5f  jmp     loc_140018047
0x140017c64  cmp     [rsp+0D8h+arg_18], 0
0x140017c6c  jnz     short loc_140017C94
0x140017c6e  mov     rcx, [r15+1D8h]; FileLock
0x140017c75  test    rcx, rcx
0x140017c78  jz      short loc_140017C94
0x140017c7a  mov     rdx, rsi; Irp
0x140017c7d  call    cs:__imp_FsRtlCheckLockForReadAccess
0x140017c84  nop     dword ptr [rax+rax+00h]
0x140017c89  test    al, al
0x140017c8b  jnz     short loc_140017C94
0x140017c8d  mov     ebx, 0C0000054h
0x140017c92  jmp     short loc_140017C19
0x140017c94  mov     r8d, [rsp+0D8h+arg_10]
0x140017c9c  cmp     r14d, 2
0x140017ca0  jnz     short loc_140017CAA
0x140017ca2  mov     eax, [r13+4]
0x140017ca6  test    al, 20h
0x140017ca8  jnz     short loc_140017CD5
0x140017caa  mov     rcx, [r15+20h]
0x140017cae  cmp     qword ptr [rsp+0D8h+FileOffset], rcx
0x140017cb3  jl      short loc_140017CBF
0x140017cb5  mov     ebx, 0C0000011h
0x140017cba  jmp     loc_140017C19
0x140017cbf  cmp     [rsp+0D8h+var_90], rcx
0x140017cc4  jle     short loc_140017CD5
0x140017cc6  mov     r13d, ecx
0x140017cc9  sub     r13d, dword ptr [rsp+0D8h+FileOffset]
0x140017cce  mov     [rsp+0D8h+var_90], rcx
0x140017cd3  jmp     short loc_140017CDA
0x140017cd5  mov     r13, [rsp+0D8h+var_80]
0x140017cda  cmp     [rsp+0D8h+var_98], 0
0x140017cdf  jz      loc_140017F1C
0x140017ce5  mov     rax, [r15+78h]
0x140017ce9  mov     r14d, [rax+1B8h]
0x140017cf0  add     r14d, r13d
0x140017cf3  and     r14d, [rax+1BCh]
0x140017cfa  mov     eax, r14d
0x140017cfd  or      eax, dword ptr [rsp+0D8h+FileOffset]
0x140017d01  test    eax, 7FFh
0x140017d06  jnz     short loc_140017D0F
0x140017d08  cmp     r14d, [rsp+0D8h+var_88]
0x140017d0d  jbe     short loc_140017D1B
0x140017d0f  test    r8d, r8d
0x140017d12  jz      loc_1400180A8
0x140017d18  mov     r14d, r13d
0x140017d1b  mov     rdx, [rdi+30h]
0x140017d1f  test    rdx, rdx
0x140017d22  jz      short loc_140017D2D
0x140017d24  test    dword ptr [rdi+20h], 100h
0x140017d2b  jnz     short loc_140017D8B
0x140017d2d  test    r8d, r8d
0x140017d30  jz      short loc_140017D47
0x140017d32  lea     rax, [rsp+0D8h+var_70]
0x140017d37  mov     [rdi+30h], rax
0x140017d3b  btr     dword ptr [rdi+20h], 8
0x140017d40  lea     rdx, [rsp+0D8h+var_70]
0x140017d45  jmp     short loc_140017D8B
0x140017d47  mov     edx, 30h ; '0'; NumberOfBytes
0x140017d4c  mov     ecx, 610h; PoolType
0x140017d51  mov     r8d, 6F696443h; Tag
0x140017d57  call    cs:__imp_ExAllocatePoolWithTag
0x140017d5e  nop     dword ptr [rax+rax+00h]
0x140017d63  mov     rdx, rax
0x140017d66  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140017d6d  jnz     short loc_140017D82
0x140017d6f  test    rax, rax
0x140017d72  jz      short loc_140017D82
0x140017d74  xorps   xmm0, xmm0
0x140017d77  movups  xmmword ptr [rax], xmm0
0x140017d7a  movups  xmmword ptr [rax+10h], xmm0
0x140017d7e  movups  xmmword ptr [rax+20h], xmm0
0x140017d82  mov     [rdi+30h], rax
0x140017d86  bts     dword ptr [rdi+20h], 8
0x140017d8b  xorps   xmm0, xmm0
0x140017d8e  movups  xmmword ptr [rdx], xmm0
0x140017d91  movups  xmmword ptr [rdx+10h], xmm0
0x140017d95  movups  xmmword ptr [rdx+20h], xmm0
0x140017d99  mov     ecx, [rdi+20h]
0x140017d9c  shr     ecx, 8
0x140017d9f  and     cl, 1
0x140017da2  mov     rax, [rdi+30h]
0x140017da6  mov     [rax+14h], cl
0x140017da9  cmp     [rsp+0D8h+arg_10], 0
0x140017db1  jz      short loc_140017DCE
0x140017db3  mov     rcx, [rdi+30h]
0x140017db7  add     rcx, 18h; Event
0x140017dbb  xor     r8d, r8d; State
0x140017dbe  xor     edx, edx; Type
0x140017dc0  call    cs:__imp_KeInitializeEvent
0x140017dc7  nop     dword ptr [rax+rax+00h]
0x140017dcc  jmp     short loc_140017DF3
0x140017dce  mov     rcx, gs:188h
0x140017dd7  mov     rax, [rdi+30h]
0x140017ddb  mov     [rax+20h], rcx
0x140017ddf  mov     rcx, [rdi+30h]
0x140017de3  mov     rax, [r15+8]
0x140017de7  mov     [rcx+18h], rax
0x140017deb  mov     rax, [rdi+30h]
0x140017def  mov     [rax+28h], r13d
0x140017df3  mov     eax, r14d
0x140017df6  mov     [rsi+38h], rax
0x140017dfa  mov     eax, [r15+0ACh]
0x140017e01  mov     r9d, r14d; int
0x140017e04  mov     r8, qword ptr [rsp+0D8h+FileOffset]; int
0x140017e09  mov     rdx, r15; int
0x140017e0c  mov     rcx, rdi; int
0x140017e0f  test    al, 1Ch
0x140017e11  jz      short loc_140017E1A
0x140017e13  call    CdNonCachedXARead
0x140017e18  jmp     short loc_140017E1F
0x140017e1a  call    CdNonCachedRead
0x140017e1f  mov     [rsp+0D8h+var_A4], eax
0x140017e23  mov     ebx, eax
0x140017e25  cmp     eax, 103h
0x140017e2a  jnz     short loc_140017E39
0x140017e2c  xor     esi, esi
0x140017e2e  xor     al, al
0x140017e30  mov     [rsp+0D8h+var_A8], al
0x140017e34  jmp     loc_14001804C
0x140017e39  test    ebx, ebx
0x140017e3b  jns     short loc_140017E99
0x140017e3d  mov     qword ptr [rsi+38h], 0
0x140017e45  lea     eax, [rbx+3FFFFF5Eh]
0x140017e4b  cmp     eax, 1
0x140017e4e  jbe     loc_1400180C3
0x140017e54  cmp     ebx, 0C00000B5h
0x140017e5a  jz      loc_1400180C3
0x140017e60  lea     eax, [rbx+3FFFFFEEh]
0x140017e66  cmp     eax, 2
0x140017e69  jbe     loc_1400180C3
0x140017e6f  cmp     ebx, 80000016h
0x140017e75  jz      loc_1400180C3
0x140017e7b  mov     edx, 0C00000E9h; GenericException
0x140017e80  mov     ecx, ebx; Exception
0x140017e82  call    cs:__imp_FsRtlNormalizeNtstatus
0x140017e89  nop     dword ptr [rax+rax+00h]
0x140017e8e  mov     ebx, eax
0x140017e90  mov     [rsp+0D8h+var_A4], eax
0x140017e94  jmp     loc_140018024
0x140017e99  cmp     r14d, r13d
0x140017e9c  jz      loc_140018024
0x140017ea2  mov     rax, [rdi+8]
0x140017ea6  mov     rcx, [rax+8]; MemoryDescriptorList
0x140017eaa  test    rcx, rcx
0x140017ead  jnz     short loc_140017EB5
0x140017eaf  mov     rax, [rax+70h]
0x140017eb3  jmp     short loc_140017EE6
0x140017eb5  test    byte ptr [rcx+0Ah], 5
0x140017eb9  jz      short loc_140017EC1
0x140017ebb  mov     rax, [rcx+18h]
0x140017ebf  jmp     short loc_140017EE6
0x140017ec1  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x140017ec9  mov     dword ptr [rsp+0D8h+PostIrpRoutine], 0; BugCheckOnFailure
0x140017ed1  xor     r9d, r9d; RequestedAddress
0x140017ed4  xor     edx, edx; AccessMode
0x140017ed6  lea     r8d, [r9+1]; CacheType
0x140017eda  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140017ee1  nop     dword ptr [rax+rax+00h]
0x140017ee6  test    rax, rax
0x140017ee9  jz      loc_1400180DE
0x140017eef  mov     ecx, r13d
0x140017ef2  mov     qword ptr [rsp+0D8h+Wait], rcx
0x140017efa  sub     r14d, r13d
0x140017efd  mov     r8d, r14d; Size
0x140017f00  add     rcx, rax; void *
0x140017f03  xor     edx, edx; Val
0x140017f05  call    memset
0x140017f0a  nop
0x140017f0b  mov     rax, qword ptr [rsp+0D8h+Wait]
0x140017f13  mov     [rsi+38h], rax
0x140017f17  jmp     loc_140018024
0x140017f1c  mov     rcx, [r12+30h]; FileObject
0x140017f21  cmp     qword ptr [rcx+30h], 0
0x140017f26  jnz     short loc_140017F5D
0x140017f28  lea     rdx, [r15+18h]; FileSizes
0x140017f2c  mov     [rsp+0D8h+PostIrpRoutine], r15; LazyWriteContext
0x140017f31  lea     r9, Callbacks; Callbacks
0x140017f38  xor     r8d, r8d; PinAccess
0x140017f3b  call    cs:__imp_CcInitializeCacheMap
0x140017f42  nop     dword ptr [rax+rax+00h]
0x140017f47  mov     edx, 10000h; Granularity
0x140017f4c  mov     rcx, [r12+30h]; FileObject
0x140017f51  call    cs:__imp_CcSetReadAheadGranularity
0x140017f58  nop     dword ptr [rax+rax+00h]
0x140017f5d  test    byte ptr [rdi+41h], 2
0x140017f61  jnz     loc_140017FF8
  ... truncated ...
```
