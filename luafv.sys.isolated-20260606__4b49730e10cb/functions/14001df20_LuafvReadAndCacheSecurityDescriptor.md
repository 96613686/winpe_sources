# LuafvReadAndCacheSecurityDescriptor

- ea: `0x14001df20`
- end: `0x14001e5c2`
- name: `LuafvReadAndCacheSecurityDescriptor`
- size: `1698`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001730`
- `0x14001f620`

## callees

- `0x140001268`
- `0x14001dd90`
- `0x14001df20`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001e3e0`
- `ntoskrnl!RtlCompareMemory` at `0x14001e3e0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df9b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001dfd2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e028`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e09d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e320`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e36b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e462`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df9b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001dfd2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e028`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e09d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e320`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e36b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e462`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df75`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dfbf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dff5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e066`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e344`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e42b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e4f3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df75`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dfbf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dff5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e066`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e344`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e42b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e4f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e2be`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e5a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e2be`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e5a0`
- `ntoskrnl!ExAllocatePool2` at `0x14001e228`
- `ntoskrnl!ExAllocatePool2` at `0x14001e228`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001dfac`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001e39f`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001dfac`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001e39f`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e015`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e08a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e26a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e411`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e44f`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e52c`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e015`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e08a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e26a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e411`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e44f`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e52c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e24f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e331`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e53f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e24f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e331`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e53f`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e1eb`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e2a4`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e1eb`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e2a4`
- `FLTMGR!FltClose` at `0x14001e2d2`
- `FLTMGR!FltClose` at `0x14001e5b1`
- `FLTMGR!FltClose` at `0x14001e2d2`
- `FLTMGR!FltClose` at `0x14001e5b1`
- `FLTMGR!FltCreateFileEx2` at `0x14001e183`
- `FLTMGR!FltCreateFileEx2` at `0x14001e183`

## pseudocode

```c
__int64 __fastcall LuafvReadAndCacheSecurityDescriptor(
        PFLT_INSTANCE Instance,
        __int64 a2,
        __m128i *a3,
        char a4,
        __int64 *a5)
{
  __int64 v9; // rbx
  bool v11; // zf
  __m128i v12; // xmm1
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  __int16 v15; // ax
  ULONG Flags; // eax
  NTSTATUS v17; // ebx
  ULONG v18; // ebx
  __int64 Pool2; // rax
  __int64 v20; // r14
  __int64 v21; // r15
  int v22; // ebx
  __int64 *v23; // r12
  __int64 v24; // r14
  ULONG v25; // eax
  __int64 v26; // rax
  ULONG LengthNeeded; // [rsp+80h] [rbp-61h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-51h] BYREF
  int v30; // [rsp+98h] [rbp-49h]
  __m128i v31; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-1h] BYREF
  char i; // [rsp+148h] [rbp+67h]

  FileHandle = 0;
  FileObject = 0;
  LengthNeeded = 0;
  v31 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(a2 + 8) == KeGetCurrentThread() )
  {
    ++*(_DWORD *)(a2 + 16);
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquirePushLockSharedEx(a2, 0);
    ExAcquireFastMutex(&FastMutex);
  }
  ExReleaseFastMutex(&FastMutex);
  v9 = *(_QWORD *)(a2 + 232);
  if ( v9 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 32));
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a2 + 8) == KeGetCurrentThread() )
    {
      v11 = (*(_DWORD *)(a2 + 16))-- == 1;
      if ( !v11 )
        goto LABEL_6;
      *(_QWORD *)(a2 + 8) = 0;
    }
LABEL_5:
    FltReleasePushLockEx(a2, 0);
LABEL_6:
    ExReleaseFastMutex(&FastMutex);
    *a5 = v9;
    return 0;
  }
  ExAcquireFastMutex(&FastMutex);
  if ( *(struct _KTHREAD **)(a2 + 8) != KeGetCurrentThread() )
    goto LABEL_11;
  v11 = (*(_DWORD *)(a2 + 16))-- == 1;
  if ( v11 )
  {
    *(_QWORD *)(a2 + 8) = 0;
LABEL_11:
    FltReleasePushLockEx(a2, 0);
  }
  ExReleaseFastMutex(&FastMutex);
  v12 = *a3;
  v13 = a3->m128i_u64[1];
  FileHandle = 0;
  FileObject = 0;
  v31 = v12;
  v14 = v13 + (unsigned __int16)_mm_cvtsi128_si32(v12);
  while ( v14 > v13 )
  {
    v15 = *(_WORD *)(v14 - 2);
    v14 -= 2LL;
    if ( v15 == 92 )
      break;
    if ( v15 == 58 )
      v31.m128i_i16[0] = 2 * ((__int64)(v14 - v13) >> 1);
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
  Flags = 2309;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( !a4 )
    Flags = 2305;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = FltCreateFileEx2(
          LuafvDriverData,
          Instance,
          &FileHandle,
          &FileObject,
          0x120000u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          7u,
          1u,
          0x20u,
          0,
          0,
          Flags,
          0);
  if ( v17 >= 0 )
  {
    v17 = FltQuerySecurityObject(Instance, FileObject, 0x1Fu, 0, 0, &LengthNeeded);
    if ( v17 != -1073741789 )
      goto LABEL_21;
    v18 = LengthNeeded + 40;
    if ( LengthNeeded >= 0xFFFFFFD8 )
    {
      v17 = -1073741675;
      goto LABEL_21;
    }
    if ( v18 >= 0xFFFFFFF8 )
      goto LABEL_48;
    Pool2 = ExAllocatePool2(256, LengthNeeded + 48, 1717663052);
    v20 = Pool2;
    if ( !Pool2
      || (*(_DWORD *)Pool2 = v18,
          *(_BYTE *)(Pool2 + 4) = -1,
          FltAcquirePushLockExclusiveEx(&PoolLock, 0),
          dword_14000F2FC += v18,
          FltReleasePushLockEx(&PoolLock, 0),
          v21 = v20 + 8,
          v20 == -8) )
    {
LABEL_48:
      v17 = -1073741670;
      goto LABEL_21;
    }
    v17 = FltQuerySecurityObject(
            Instance,
            FileObject,
            0x1Fu,
            (PSECURITY_DESCRIPTOR)(v20 + 48),
            LengthNeeded,
            &LengthNeeded);
    if ( v17 < 0 )
    {
      LuafvFreePool(v20 + 8);
      goto LABEL_21;
    }
    ObfDereferenceObject(FileObject);
    FileObject = 0;
    FltClose(FileHandle);
    FileHandle = 0;
    v30 = LuafvCalculateHash(v20 + 48, LengthNeeded);
    v22 = v30;
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a2 + 8) == KeGetCurrentThread() )
    {
      ++*(_DWORD *)(a2 + 16);
    }
    else
    {
      ExReleaseFastMutex(&FastMutex);
      FltAcquirePushLockExclusiveEx(a2, 0);
      ExAcquireFastMutex(&FastMutex);
      *(_QWORD *)(a2 + 8) = KeGetCurrentThread();
      *(_DWORD *)(a2 + 16) = 1;
    }
    ExReleaseFastMutex(&FastMutex);
    if ( *(_QWORD *)(a2 + 232) )
    {
      LuafvFreePool(v20 + 8);
      v9 = *(_QWORD *)(a2 + 232);
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 32));
      ExAcquireFastMutex(&FastMutex);
      if ( *(struct _KTHREAD **)(a2 + 8) == KeGetCurrentThread() )
      {
        v11 = (*(_DWORD *)(a2 + 16))-- == 1;
        if ( !v11 )
          goto LABEL_6;
        *(_QWORD *)(a2 + 8) = 0;
      }
      goto LABEL_5;
    }
    v23 = &SdTable[3 * (v22 & 0xF)];
    FltAcquirePushLockSharedEx(v23 + 2, 0);
    for ( i = 0; ; i = 1 )
    {
      v24 = *v23;
      v25 = LengthNeeded;
      while ( (__int64 *)v24 != v23 )
      {
        if ( *(_DWORD *)(v24 + 28) == v22 && *(_DWORD *)(v24 + 24) == v25 )
        {
          if ( RtlCompareMemory(*(const void **)(v24 + 16), (const void *)(v21 + 40), v25) == v25 )
          {
            LuafvFreePool(v21);
            v21 = v24;
            _InterlockedIncrement((volatile signed __int32 *)(v24 + 32));
            _InterlockedIncrement((volatile signed __int32 *)(v24 + 32));
            goto LABEL_44;
          }
          v25 = LengthNeeded;
          v22 = v30;
        }
        v24 = *(_QWORD *)v24;
      }
      if ( i )
        break;
      FltReleasePushLockEx(v23 + 2, 0);
      FltAcquirePushLockExclusiveEx(v23 + 2, 0);
    }
    *(_DWORD *)(v21 + 32) = 2;
    *(_DWORD *)(v21 + 28) = v22;
    *(_DWORD *)(v21 + 24) = LengthNeeded;
    *(_QWORD *)(v21 + 16) = v21 + 40;
    v26 = *v23;
    if ( *(__int64 **)(*v23 + 8) != v23 )
      __fastfail(3u);
    *(_QWORD *)v21 = v26;
    *(_QWORD *)(v21 + 8) = v23;
    *(_QWORD *)(v26 + 8) = v21;
    *v23 = v21;
LABEL_44:
    FltReleasePushLockEx(v23 + 2, 0);
    *(_QWORD *)(a2 + 232) = v21;
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(a2 + 8) == KeGetCurrentThread() )
    {
      v11 = (*(_DWORD *)(a2 + 16))-- == 1;
      if ( !v11 )
        goto LABEL_46;
      *(_QWORD *)(a2 + 8) = 0;
    }
    FltReleasePushLockEx(a2, 0);
LABEL_46:
    ExReleaseFastMutex(&FastMutex);
    v17 = 0;
    *a5 = v21;
    goto LABEL_21;
  }
  FileHandle = 0;
LABEL_21:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14001df20  push    rbp
0x14001df22  push    rbx
0x14001df23  push    rsi
0x14001df24  push    rdi
0x14001df25  push    r12
0x14001df27  push    r13
0x14001df29  push    r14
0x14001df2b  push    r15
0x14001df2d  lea     rbp, [rsp-17h]
0x14001df32  sub     rsp, 0F8h
0x14001df39  xorps   xmm0, xmm0
0x14001df3c  xor     r13d, r13d
0x14001df3f  mov     r12, rcx
0x14001df42  mov     [rbp+4Fh+FileHandle], r13
0x14001df46  movups  xmmword ptr [rbp+4Fh+var_80.ObjectName], xmm0
0x14001df4a  xor     eax, eax
0x14001df4c  mov     [rbp+4Fh+FileObject], r13
0x14001df50  lea     rcx, FastMutex; FastMutex
0x14001df57  mov     [rbp+4Fh+LengthNeeded], r13d
0x14001df5b  movups  xmmword ptr [rbp+4Fh+var_80+1Ch], xmm0
0x14001df5f  movzx   r15d, r9b
0x14001df63  mov     r14, r8
0x14001df66  mov     rdi, rdx
0x14001df69  movups  [rbp+4Fh+var_90], xmm0
0x14001df6d  movups  xmmword ptr [rbp+4Fh+var_80.Length], xmm0
0x14001df71  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x14001df75  call    cs:__imp_ExAcquireFastMutex
0x14001df7c  nop     dword ptr [rax+rax+00h]
0x14001df81  mov     rax, gs:188h
0x14001df8a  cmp     [rdi+8], rax
0x14001df8e  jz      loc_14001E05E
0x14001df94  lea     rcx, FastMutex; FastMutex
0x14001df9b  call    cs:__imp_ExReleaseFastMutex
0x14001dfa2  nop     dword ptr [rax+rax+00h]
0x14001dfa7  xor     edx, edx
0x14001dfa9  mov     rcx, rdi
0x14001dfac  call    cs:__imp_FltAcquirePushLockSharedEx
0x14001dfb3  nop     dword ptr [rax+rax+00h]
0x14001dfb8  lea     rcx, FastMutex; FastMutex
0x14001dfbf  call    cs:__imp_ExAcquireFastMutex
0x14001dfc6  nop     dword ptr [rax+rax+00h]
0x14001dfcb  lea     rcx, FastMutex; FastMutex
0x14001dfd2  call    cs:__imp_ExReleaseFastMutex
0x14001dfd9  nop     dword ptr [rax+rax+00h]
0x14001dfde  mov     rbx, [rdi+0E8h]
0x14001dfe5  lea     rcx, FastMutex; FastMutex
0x14001dfec  test    rbx, rbx
0x14001dfef  jz      short loc_14001E066
0x14001dff1  lock inc dword ptr [rbx+20h]
0x14001dff5  call    cs:__imp_ExAcquireFastMutex
0x14001dffc  nop     dword ptr [rax+rax+00h]
0x14001e001  mov     rax, gs:188h
0x14001e00a  cmp     [rdi+8], rax
0x14001e00e  jz      short loc_14001E052
0x14001e010  xor     edx, edx
0x14001e012  mov     rcx, rdi
0x14001e015  call    cs:__imp_FltReleasePushLockEx
0x14001e01c  nop     dword ptr [rax+rax+00h]
0x14001e021  lea     rcx, FastMutex; FastMutex
0x14001e028  call    cs:__imp_ExReleaseFastMutex
0x14001e02f  nop     dword ptr [rax+rax+00h]
0x14001e034  mov     rax, [rbp+4Fh+arg_20]
0x14001e038  mov     [rax], rbx
0x14001e03b  xor     eax, eax
0x14001e03d  add     rsp, 0F8h
0x14001e044  pop     r15
0x14001e046  pop     r14
0x14001e048  pop     r13
0x14001e04a  pop     r12
0x14001e04c  pop     rdi
0x14001e04d  pop     rsi
0x14001e04e  pop     rbx
0x14001e04f  pop     rbp
0x14001e050  retn
0x14001e052  sub     dword ptr [rdi+10h], 1
0x14001e056  jnz     short loc_14001E021
0x14001e058  mov     [rdi+8], r13
0x14001e05c  jmp     short loc_14001E010
0x14001e05e  inc     dword ptr [rdi+10h]
0x14001e061  jmp     loc_14001DFCB
0x14001e066  call    cs:__imp_ExAcquireFastMutex
0x14001e06d  nop     dword ptr [rax+rax+00h]
0x14001e072  mov     rax, gs:188h
0x14001e07b  cmp     [rdi+8], rax
0x14001e07f  jz      loc_14001E1BA
0x14001e085  xor     edx, edx
0x14001e087  mov     rcx, rdi
0x14001e08a  call    cs:__imp_FltReleasePushLockEx
0x14001e091  nop     dword ptr [rax+rax+00h]
0x14001e096  lea     rcx, FastMutex; FastMutex
0x14001e09d  call    cs:__imp_ExReleaseFastMutex
0x14001e0a4  nop     dword ptr [rax+rax+00h]
0x14001e0a9  movups  xmm1, xmmword ptr [r14]
0x14001e0ad  mov     rdx, [r14+8]
0x14001e0b1  mov     [rbp+4Fh+FileHandle], r13
0x14001e0b5  movd    eax, xmm1
0x14001e0b9  mov     [rbp+4Fh+FileObject], r13
0x14001e0bd  movups  [rbp+4Fh+var_90], xmm1
0x14001e0c1  movzx   ecx, ax
0x14001e0c4  add     rcx, rdx
0x14001e0c7  cmp     rcx, rdx
0x14001e0ca  jbe     short loc_14001E0ED
0x14001e0cc  nop     dword ptr [rax+00h]
0x14001e0d0  movzx   eax, word ptr [rcx-2]
0x14001e0d4  sub     rcx, 2
0x14001e0d8  cmp     ax, 5Ch ; '\'
0x14001e0dc  jz      short loc_14001E0ED
0x14001e0de  cmp     ax, 3Ah ; ':'
0x14001e0e2  jz      loc_14001E568
0x14001e0e8  cmp     rcx, rdx
0x14001e0eb  ja      short loc_14001E0D0
0x14001e0ed  mov     [rsp+130h+DriverContext], r13; DriverContext
0x14001e0f2  lea     rax, [rbp+4Fh+var_90]
0x14001e0f6  mov     [rbp+4Fh+var_80.ObjectName], rax
0x14001e0fa  lea     r9, [rbp+4Fh+FileObject]; FileObject
0x14001e0fe  mov     eax, 905h
0x14001e103  mov     [rbp+4Fh+var_80.Length], 30h ; '0'
0x14001e10a  mov     ecx, 901h
0x14001e10f  mov     [rbp+4Fh+var_80.RootDirectory], r13
0x14001e113  xorps   xmm0, xmm0
0x14001e116  mov     [rbp+4Fh+var_80.Attributes], 240h
0x14001e11d  test    r15b, r15b
0x14001e120  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x14001e124  mov     rdx, r12; Instance
0x14001e127  cmovz   eax, ecx
0x14001e12a  mov     rcx, cs:LuafvDriverData; Filter
0x14001e131  mov     [rsp+130h+Flags], eax; Flags
0x14001e135  lea     rax, [rbp+4Fh+var_50]
0x14001e139  mov     [rsp+130h+EaLength], r13d; EaLength
0x14001e13e  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x14001e143  mov     [rsp+130h+CreateOptions], 20h ; ' '; CreateOptions
0x14001e14b  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x14001e153  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14001e15b  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x14001e163  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x14001e168  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14001e16d  lea     rax, [rbp+4Fh+var_80]
0x14001e171  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14001e176  mov     [rsp+130h+DesiredAccess], 120000h; DesiredAccess
0x14001e17e  movdqu  xmmword ptr [rbp+4Fh+var_80.SecurityDescriptor], xmm0
0x14001e183  call    cs:__imp_FltCreateFileEx2
0x14001e18a  nop     dword ptr [rax+rax+00h]
0x14001e18f  mov     ebx, eax
0x14001e191  test    eax, eax
0x14001e193  jns     short loc_14001E1CD
0x14001e195  mov     [rbp+4Fh+FileHandle], r13
0x14001e199  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14001e19d  test    rcx, rcx
0x14001e1a0  jnz     loc_14001E5A0
0x14001e1a6  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14001e1aa  test    rcx, rcx
0x14001e1ad  jnz     loc_14001E5B1
0x14001e1b3  mov     eax, ebx
0x14001e1b5  jmp     loc_14001E03D
0x14001e1ba  sub     dword ptr [rdi+10h], 1
0x14001e1be  jnz     loc_14001E096
0x14001e1c4  mov     [rdi+8], r13
0x14001e1c8  jmp     loc_14001E085
0x14001e1cd  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x14001e1d1  lea     rax, [rbp+4Fh+LengthNeeded]
0x14001e1d5  mov     [rsp+130h+ObjectAttributes], rax; LengthNeeded
0x14001e1da  xor     r9d, r9d; SecurityDescriptor
0x14001e1dd  mov     r8d, 1Fh; SecurityInformation
0x14001e1e3  mov     [rsp+130h+DesiredAccess], r13d; Length
0x14001e1e8  mov     rcx, r12; Instance
0x14001e1eb  call    cs:__imp_FltQuerySecurityObject
0x14001e1f2  nop     dword ptr [rax+rax+00h]
0x14001e1f7  mov     ebx, eax
0x14001e1f9  cmp     eax, 0C0000023h
0x14001e1fe  jnz     short loc_14001E199
0x14001e200  mov     ebx, [rbp+4Fh+LengthNeeded]
0x14001e203  add     ebx, 28h ; '('
0x14001e206  cmp     ebx, 28h ; '('
0x14001e209  jb      loc_14001E47C
0x14001e20f  lea     eax, [rbx+8]
0x14001e212  cmp     eax, 8
0x14001e215  jb      loc_14001E486
0x14001e21b  mov     edx, eax
0x14001e21d  mov     ecx, 100h
0x14001e222  mov     r8d, 6661754Ch
0x14001e228  call    cs:__imp_ExAllocatePool2
0x14001e22f  nop     dword ptr [rax+rax+00h]
0x14001e234  mov     r14, rax
0x14001e237  test    rax, rax
0x14001e23a  jz      loc_14001E486
0x14001e240  xor     edx, edx
0x14001e242  mov     [rax], ebx
0x14001e244  lea     rcx, PoolLock
0x14001e24b  mov     byte ptr [rax+4], 0FFh
0x14001e24f  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e256  nop     dword ptr [rax+rax+00h]
0x14001e25b  add     cs:dword_14000F2FC, ebx
0x14001e261  lea     rcx, PoolLock
0x14001e268  xor     edx, edx
0x14001e26a  call    cs:__imp_FltReleasePushLockEx
0x14001e271  nop     dword ptr [rax+rax+00h]
0x14001e276  lea     r15, [r14+8]
0x14001e27a  test    r15, r15
0x14001e27d  jz      loc_14001E486
0x14001e283  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x14001e287  lea     rax, [rbp+4Fh+LengthNeeded]
0x14001e28b  mov     [rsp+130h+ObjectAttributes], rax; LengthNeeded
0x14001e290  lea     r9, [r15+28h]; SecurityDescriptor
0x14001e294  mov     eax, [rbp+4Fh+LengthNeeded]
0x14001e297  mov     r8d, 1Fh; SecurityInformation
0x14001e29d  mov     rcx, r12; Instance
0x14001e2a0  mov     [rsp+130h+DesiredAccess], eax; Length
0x14001e2a4  call    cs:__imp_FltQuerySecurityObject
0x14001e2ab  nop     dword ptr [rax+rax+00h]
0x14001e2b0  mov     ebx, eax
0x14001e2b2  test    eax, eax
0x14001e2b4  js      loc_14001E593
0x14001e2ba  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14001e2be  call    cs:__imp_ObfDereferenceObject
0x14001e2c5  nop     dword ptr [rax+rax+00h]
0x14001e2ca  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14001e2ce  mov     [rbp+4Fh+FileObject], r13
0x14001e2d2  call    cs:__imp_FltClose
0x14001e2d9  nop     dword ptr [rax+rax+00h]
0x14001e2de  mov     edx, [rbp+4Fh+LengthNeeded]
0x14001e2e1  lea     rcx, [r15+28h]
0x14001e2e5  mov     [rbp+4Fh+FileHandle], r13
0x14001e2e9  call    LuafvCalculateHash
0x14001e2ee  lea     rcx, FastMutex; FastMutex
0x14001e2f5  mov     [rbp+4Fh+var_98], eax
0x14001e2f8  mov     ebx, eax
0x14001e2fa  call    cs:__imp_ExAcquireFastMutex
0x14001e301  nop     dword ptr [rax+rax+00h]
0x14001e306  mov     rcx, gs:188h
0x14001e30f  cmp     [rdi+8], rcx
0x14001e313  jz      loc_14001E57D
0x14001e319  lea     rcx, FastMutex; FastMutex
0x14001e320  call    cs:__imp_ExReleaseFastMutex
0x14001e327  nop     dword ptr [rax+rax+00h]
0x14001e32c  xor     edx, edx
0x14001e32e  mov     rcx, rdi
0x14001e331  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e338  nop     dword ptr [rax+rax+00h]
0x14001e33d  lea     rcx, FastMutex; FastMutex
0x14001e344  call    cs:__imp_ExAcquireFastMutex
0x14001e34b  nop     dword ptr [rax+rax+00h]
0x14001e350  mov     rax, gs:188h
0x14001e359  mov     [rdi+8], rax
0x14001e35d  mov     dword ptr [rdi+10h], 1
0x14001e364  lea     rcx, FastMutex; FastMutex
0x14001e36b  call    cs:__imp_ExReleaseFastMutex
0x14001e372  nop     dword ptr [rax+rax+00h]
0x14001e377  cmp     [rdi+0E8h], r13
0x14001e37e  jnz     loc_14001E4D9
0x14001e384  mov     eax, ebx
0x14001e386  lea     rcx, SdTable
0x14001e38d  and     eax, 0Fh
0x14001e390  xor     edx, edx
0x14001e392  lea     rax, [rax+rax*2]
0x14001e396  lea     r12, [rcx+rax*8]
0x14001e39a  lea     rcx, [r12+10h]
0x14001e39f  call    cs:__imp_FltAcquirePushLockSharedEx
0x14001e3a6  nop     dword ptr [rax+rax+00h]
0x14001e3ab  mov     [rbp+4Fh+arg_8], r13b
0x14001e3af  mov     r14, [r12]
0x14001e3b3  mov     eax, [rbp+4Fh+LengthNeeded]
0x14001e3b6  cmp     r14, r12
0x14001e3b9  jz      loc_14001E490
0x14001e3bf  cmp     [r14+1Ch], ebx
0x14001e3c3  jnz     loc_14001E58B
0x14001e3c9  cmp     [r14+18h], eax
0x14001e3cd  jnz     loc_14001E58B
0x14001e3d3  mov     rcx, [r14+10h]; Source1
0x14001e3d7  lea     rdx, [r15+28h]; Source2
0x14001e3db  mov     r8d, eax; Length
0x14001e3de  mov     ebx, eax
0x14001e3e0  call    cs:__imp_RtlCompareMemory
0x14001e3e7  nop     dword ptr [rax+rax+00h]
0x14001e3ec  cmp     rax, rbx
0x14001e3ef  jnz     loc_14001E585
0x14001e3f5  mov     rcx, r15
0x14001e3f8  call    LuafvFreePool
0x14001e3fd  mov     r15, r14
0x14001e400  lock inc dword ptr [r14+20h]
0x14001e405  lock inc dword ptr [r14+20h]
0x14001e40a  xor     edx, edx
0x14001e40c  lea     rcx, [r12+10h]
0x14001e411  call    cs:__imp_FltReleasePushLockEx
0x14001e418  nop     dword ptr [rax+rax+00h]
0x14001e41d  lea     rcx, FastMutex; FastMutex
0x14001e424  mov     [rdi+0E8h], r15
0x14001e42b  call    cs:__imp_ExAcquireFastMutex
0x14001e432  nop     dword ptr [rax+rax+00h]
0x14001e437  mov     rax, gs:188h
0x14001e440  cmp     [rdi+8], rax
0x14001e444  jz      loc_14001E4CA
0x14001e44a  xor     edx, edx
0x14001e44c  mov     rcx, rdi
0x14001e44f  call    cs:__imp_FltReleasePushLockEx
0x14001e456  nop     dword ptr [rax+rax+00h]
0x14001e45b  lea     rcx, FastMutex; FastMutex
0x14001e462  call    cs:__imp_ExReleaseFastMutex
0x14001e469  nop     dword ptr [rax+rax+00h]
0x14001e46e  mov     rax, [rbp+4Fh+arg_20]
0x14001e472  xor     ebx, ebx
  ... truncated ...
```
