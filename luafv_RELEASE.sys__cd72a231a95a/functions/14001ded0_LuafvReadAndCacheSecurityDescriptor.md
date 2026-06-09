# LuafvReadAndCacheSecurityDescriptor

- ea: `0x14001ded0`
- end: `0x14001e572`
- name: `LuafvReadAndCacheSecurityDescriptor`
- size: `1698`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, __int64, __m128i *, char, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001730`
- `0x14001f5d0`

## callees

- `0x140001268`
- `0x14001dd40`
- `0x14001ded0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001e390`
- `ntoskrnl!RtlCompareMemory` at `0x14001e390`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df4b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df82`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001dfd8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e04d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e2d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e31b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e412`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df4b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001df82`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001dfd8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e04d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e2d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e31b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e412`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df25`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dfa5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e016`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2aa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2f4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e3db`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e4a3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df25`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001df6f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001dfa5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e016`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2aa`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e2f4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e3db`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e4a3`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e26e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e550`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e26e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e550`
- `ntoskrnl!ExAllocatePool2` at `0x14001e1d8`
- `ntoskrnl!ExAllocatePool2` at `0x14001e1d8`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001df5c`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001e34f`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001df5c`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14001e34f`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dfc5`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e03a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e21a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e3c1`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e3ff`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e4dc`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dfc5`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e03a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e21a`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e3c1`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e3ff`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e4dc`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e1ff`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e2e1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e4ef`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e1ff`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e2e1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e4ef`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e19b`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e254`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e19b`
- `FLTMGR!FltQuerySecurityObject` at `0x14001e254`
- `FLTMGR!FltClose` at `0x14001e282`
- `FLTMGR!FltClose` at `0x14001e561`
- `FLTMGR!FltClose` at `0x14001e282`
- `FLTMGR!FltClose` at `0x14001e561`
- `FLTMGR!FltCreateFileEx2` at `0x14001e133`
- `FLTMGR!FltCreateFileEx2` at `0x14001e133`

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
          dword_14000ECBC += v18,
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
    v30 = LuafvCalculateHash((unsigned __int16 *)(v20 + 48), LengthNeeded);
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
0x14001ded0  push    rbp
0x14001ded2  push    rbx
0x14001ded3  push    rsi
0x14001ded4  push    rdi
0x14001ded5  push    r12
0x14001ded7  push    r13
0x14001ded9  push    r14
0x14001dedb  push    r15
0x14001dedd  lea     rbp, [rsp-17h]
0x14001dee2  sub     rsp, 0F8h
0x14001dee9  xorps   xmm0, xmm0
0x14001deec  xor     r13d, r13d
0x14001deef  mov     r12, rcx
0x14001def2  mov     [rbp+4Fh+FileHandle], r13
0x14001def6  movups  xmmword ptr [rbp+4Fh+var_80.ObjectName], xmm0
0x14001defa  xor     eax, eax
0x14001defc  mov     [rbp+4Fh+FileObject], r13
0x14001df00  lea     rcx, FastMutex; FastMutex
0x14001df07  mov     [rbp+4Fh+LengthNeeded], r13d
0x14001df0b  movups  xmmword ptr [rbp+4Fh+var_80+1Ch], xmm0
0x14001df0f  movzx   r15d, r9b
0x14001df13  mov     r14, r8
0x14001df16  mov     rdi, rdx
0x14001df19  movups  [rbp+4Fh+var_90], xmm0
0x14001df1d  movups  xmmword ptr [rbp+4Fh+var_80.Length], xmm0
0x14001df21  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x14001df25  call    cs:__imp_ExAcquireFastMutex
0x14001df2c  nop     dword ptr [rax+rax+00h]
0x14001df31  mov     rax, gs:188h
0x14001df3a  cmp     [rdi+8], rax
0x14001df3e  jz      loc_14001E00E
0x14001df44  lea     rcx, FastMutex; FastMutex
0x14001df4b  call    cs:__imp_ExReleaseFastMutex
0x14001df52  nop     dword ptr [rax+rax+00h]
0x14001df57  xor     edx, edx
0x14001df59  mov     rcx, rdi
0x14001df5c  call    cs:__imp_FltAcquirePushLockSharedEx
0x14001df63  nop     dword ptr [rax+rax+00h]
0x14001df68  lea     rcx, FastMutex; FastMutex
0x14001df6f  call    cs:__imp_ExAcquireFastMutex
0x14001df76  nop     dword ptr [rax+rax+00h]
0x14001df7b  lea     rcx, FastMutex; FastMutex
0x14001df82  call    cs:__imp_ExReleaseFastMutex
0x14001df89  nop     dword ptr [rax+rax+00h]
0x14001df8e  mov     rbx, [rdi+0E8h]
0x14001df95  lea     rcx, FastMutex; FastMutex
0x14001df9c  test    rbx, rbx
0x14001df9f  jz      short loc_14001E016
0x14001dfa1  lock inc dword ptr [rbx+20h]
0x14001dfa5  call    cs:__imp_ExAcquireFastMutex
0x14001dfac  nop     dword ptr [rax+rax+00h]
0x14001dfb1  mov     rax, gs:188h
0x14001dfba  cmp     [rdi+8], rax
0x14001dfbe  jz      short loc_14001E002
0x14001dfc0  xor     edx, edx
0x14001dfc2  mov     rcx, rdi
0x14001dfc5  call    cs:__imp_FltReleasePushLockEx
0x14001dfcc  nop     dword ptr [rax+rax+00h]
0x14001dfd1  lea     rcx, FastMutex; FastMutex
0x14001dfd8  call    cs:__imp_ExReleaseFastMutex
0x14001dfdf  nop     dword ptr [rax+rax+00h]
0x14001dfe4  mov     rax, [rbp+4Fh+arg_20]
0x14001dfe8  mov     [rax], rbx
0x14001dfeb  xor     eax, eax
0x14001dfed  add     rsp, 0F8h
0x14001dff4  pop     r15
0x14001dff6  pop     r14
0x14001dff8  pop     r13
0x14001dffa  pop     r12
0x14001dffc  pop     rdi
0x14001dffd  pop     rsi
0x14001dffe  pop     rbx
0x14001dfff  pop     rbp
0x14001e000  retn
0x14001e002  sub     dword ptr [rdi+10h], 1
0x14001e006  jnz     short loc_14001DFD1
0x14001e008  mov     [rdi+8], r13
0x14001e00c  jmp     short loc_14001DFC0
0x14001e00e  inc     dword ptr [rdi+10h]
0x14001e011  jmp     loc_14001DF7B
0x14001e016  call    cs:__imp_ExAcquireFastMutex
0x14001e01d  nop     dword ptr [rax+rax+00h]
0x14001e022  mov     rax, gs:188h
0x14001e02b  cmp     [rdi+8], rax
0x14001e02f  jz      loc_14001E16A
0x14001e035  xor     edx, edx
0x14001e037  mov     rcx, rdi
0x14001e03a  call    cs:__imp_FltReleasePushLockEx
0x14001e041  nop     dword ptr [rax+rax+00h]
0x14001e046  lea     rcx, FastMutex; FastMutex
0x14001e04d  call    cs:__imp_ExReleaseFastMutex
0x14001e054  nop     dword ptr [rax+rax+00h]
0x14001e059  movups  xmm1, xmmword ptr [r14]
0x14001e05d  mov     rdx, [r14+8]
0x14001e061  mov     [rbp+4Fh+FileHandle], r13
0x14001e065  movd    eax, xmm1
0x14001e069  mov     [rbp+4Fh+FileObject], r13
0x14001e06d  movups  [rbp+4Fh+var_90], xmm1
0x14001e071  movzx   ecx, ax
0x14001e074  add     rcx, rdx
0x14001e077  cmp     rcx, rdx
0x14001e07a  jbe     short loc_14001E09D
0x14001e07c  nop     dword ptr [rax+00h]
0x14001e080  movzx   eax, word ptr [rcx-2]
0x14001e084  sub     rcx, 2
0x14001e088  cmp     ax, 5Ch ; '\'
0x14001e08c  jz      short loc_14001E09D
0x14001e08e  cmp     ax, 3Ah ; ':'
0x14001e092  jz      loc_14001E518
0x14001e098  cmp     rcx, rdx
0x14001e09b  ja      short loc_14001E080
0x14001e09d  mov     [rsp+130h+DriverContext], r13; DriverContext
0x14001e0a2  lea     rax, [rbp+4Fh+var_90]
0x14001e0a6  mov     [rbp+4Fh+var_80.ObjectName], rax
0x14001e0aa  lea     r9, [rbp+4Fh+FileObject]; FileObject
0x14001e0ae  mov     eax, 905h
0x14001e0b3  mov     [rbp+4Fh+var_80.Length], 30h ; '0'
0x14001e0ba  mov     ecx, 901h
0x14001e0bf  mov     [rbp+4Fh+var_80.RootDirectory], r13
0x14001e0c3  xorps   xmm0, xmm0
0x14001e0c6  mov     [rbp+4Fh+var_80.Attributes], 240h
0x14001e0cd  test    r15b, r15b
0x14001e0d0  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x14001e0d4  mov     rdx, r12; Instance
0x14001e0d7  cmovz   eax, ecx
0x14001e0da  mov     rcx, cs:LuafvDriverData; Filter
0x14001e0e1  mov     [rsp+130h+Flags], eax; Flags
0x14001e0e5  lea     rax, [rbp+4Fh+var_50]
0x14001e0e9  mov     [rsp+130h+EaLength], r13d; EaLength
0x14001e0ee  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x14001e0f3  mov     [rsp+130h+CreateOptions], 20h ; ' '; CreateOptions
0x14001e0fb  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x14001e103  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14001e10b  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x14001e113  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x14001e118  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14001e11d  lea     rax, [rbp+4Fh+var_80]
0x14001e121  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14001e126  mov     [rsp+130h+DesiredAccess], 120000h; DesiredAccess
0x14001e12e  movdqu  xmmword ptr [rbp+4Fh+var_80.SecurityDescriptor], xmm0
0x14001e133  call    cs:__imp_FltCreateFileEx2
0x14001e13a  nop     dword ptr [rax+rax+00h]
0x14001e13f  mov     ebx, eax
0x14001e141  test    eax, eax
0x14001e143  jns     short loc_14001E17D
0x14001e145  mov     [rbp+4Fh+FileHandle], r13
0x14001e149  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14001e14d  test    rcx, rcx
0x14001e150  jnz     loc_14001E550
0x14001e156  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14001e15a  test    rcx, rcx
0x14001e15d  jnz     loc_14001E561
0x14001e163  mov     eax, ebx
0x14001e165  jmp     loc_14001DFED
0x14001e16a  sub     dword ptr [rdi+10h], 1
0x14001e16e  jnz     loc_14001E046
0x14001e174  mov     [rdi+8], r13
0x14001e178  jmp     loc_14001E035
0x14001e17d  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x14001e181  lea     rax, [rbp+4Fh+LengthNeeded]
0x14001e185  mov     [rsp+130h+ObjectAttributes], rax; LengthNeeded
0x14001e18a  xor     r9d, r9d; SecurityDescriptor
0x14001e18d  mov     r8d, 1Fh; SecurityInformation
0x14001e193  mov     [rsp+130h+DesiredAccess], r13d; Length
0x14001e198  mov     rcx, r12; Instance
0x14001e19b  call    cs:__imp_FltQuerySecurityObject
0x14001e1a2  nop     dword ptr [rax+rax+00h]
0x14001e1a7  mov     ebx, eax
0x14001e1a9  cmp     eax, 0C0000023h
0x14001e1ae  jnz     short loc_14001E149
0x14001e1b0  mov     ebx, [rbp+4Fh+LengthNeeded]
0x14001e1b3  add     ebx, 28h ; '('
0x14001e1b6  cmp     ebx, 28h ; '('
0x14001e1b9  jb      loc_14001E42C
0x14001e1bf  lea     eax, [rbx+8]
0x14001e1c2  cmp     eax, 8
0x14001e1c5  jb      loc_14001E436
0x14001e1cb  mov     edx, eax
0x14001e1cd  mov     ecx, 100h
0x14001e1d2  mov     r8d, 6661754Ch
0x14001e1d8  call    cs:__imp_ExAllocatePool2
0x14001e1df  nop     dword ptr [rax+rax+00h]
0x14001e1e4  mov     r14, rax
0x14001e1e7  test    rax, rax
0x14001e1ea  jz      loc_14001E436
0x14001e1f0  xor     edx, edx
0x14001e1f2  mov     [rax], ebx
0x14001e1f4  lea     rcx, PoolLock
0x14001e1fb  mov     byte ptr [rax+4], 0FFh
0x14001e1ff  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e206  nop     dword ptr [rax+rax+00h]
0x14001e20b  add     cs:dword_14000ECBC, ebx
0x14001e211  lea     rcx, PoolLock
0x14001e218  xor     edx, edx
0x14001e21a  call    cs:__imp_FltReleasePushLockEx
0x14001e221  nop     dword ptr [rax+rax+00h]
0x14001e226  lea     r15, [r14+8]
0x14001e22a  test    r15, r15
0x14001e22d  jz      loc_14001E436
0x14001e233  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x14001e237  lea     rax, [rbp+4Fh+LengthNeeded]
0x14001e23b  mov     [rsp+130h+ObjectAttributes], rax; LengthNeeded
0x14001e240  lea     r9, [r15+28h]; SecurityDescriptor
0x14001e244  mov     eax, [rbp+4Fh+LengthNeeded]
0x14001e247  mov     r8d, 1Fh; SecurityInformation
0x14001e24d  mov     rcx, r12; Instance
0x14001e250  mov     [rsp+130h+DesiredAccess], eax; Length
0x14001e254  call    cs:__imp_FltQuerySecurityObject
0x14001e25b  nop     dword ptr [rax+rax+00h]
0x14001e260  mov     ebx, eax
0x14001e262  test    eax, eax
0x14001e264  js      loc_14001E543
0x14001e26a  mov     rcx, [rbp+4Fh+FileObject]; Object
0x14001e26e  call    cs:__imp_ObfDereferenceObject
0x14001e275  nop     dword ptr [rax+rax+00h]
0x14001e27a  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14001e27e  mov     [rbp+4Fh+FileObject], r13
0x14001e282  call    cs:__imp_FltClose
0x14001e289  nop     dword ptr [rax+rax+00h]
0x14001e28e  mov     edx, [rbp+4Fh+LengthNeeded]
0x14001e291  lea     rcx, [r15+28h]
0x14001e295  mov     [rbp+4Fh+FileHandle], r13
0x14001e299  call    LuafvCalculateHash
0x14001e29e  lea     rcx, FastMutex; FastMutex
0x14001e2a5  mov     [rbp+4Fh+var_98], eax
0x14001e2a8  mov     ebx, eax
0x14001e2aa  call    cs:__imp_ExAcquireFastMutex
0x14001e2b1  nop     dword ptr [rax+rax+00h]
0x14001e2b6  mov     rcx, gs:188h
0x14001e2bf  cmp     [rdi+8], rcx
0x14001e2c3  jz      loc_14001E52D
0x14001e2c9  lea     rcx, FastMutex; FastMutex
0x14001e2d0  call    cs:__imp_ExReleaseFastMutex
0x14001e2d7  nop     dword ptr [rax+rax+00h]
0x14001e2dc  xor     edx, edx
0x14001e2de  mov     rcx, rdi
0x14001e2e1  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e2e8  nop     dword ptr [rax+rax+00h]
0x14001e2ed  lea     rcx, FastMutex; FastMutex
0x14001e2f4  call    cs:__imp_ExAcquireFastMutex
0x14001e2fb  nop     dword ptr [rax+rax+00h]
0x14001e300  mov     rax, gs:188h
0x14001e309  mov     [rdi+8], rax
0x14001e30d  mov     dword ptr [rdi+10h], 1
0x14001e314  lea     rcx, FastMutex; FastMutex
0x14001e31b  call    cs:__imp_ExReleaseFastMutex
0x14001e322  nop     dword ptr [rax+rax+00h]
0x14001e327  cmp     [rdi+0E8h], r13
0x14001e32e  jnz     loc_14001E489
0x14001e334  mov     eax, ebx
0x14001e336  lea     rcx, SdTable
0x14001e33d  and     eax, 0Fh
0x14001e340  xor     edx, edx
0x14001e342  lea     rax, [rax+rax*2]
0x14001e346  lea     r12, [rcx+rax*8]
0x14001e34a  lea     rcx, [r12+10h]
0x14001e34f  call    cs:__imp_FltAcquirePushLockSharedEx
0x14001e356  nop     dword ptr [rax+rax+00h]
0x14001e35b  mov     [rbp+4Fh+arg_8], r13b
0x14001e35f  mov     r14, [r12]
0x14001e363  mov     eax, [rbp+4Fh+LengthNeeded]
0x14001e366  cmp     r14, r12
0x14001e369  jz      loc_14001E440
0x14001e36f  cmp     [r14+1Ch], ebx
0x14001e373  jnz     loc_14001E53B
0x14001e379  cmp     [r14+18h], eax
0x14001e37d  jnz     loc_14001E53B
0x14001e383  mov     rcx, [r14+10h]; Source1
0x14001e387  lea     rdx, [r15+28h]; Source2
0x14001e38b  mov     r8d, eax; Length
0x14001e38e  mov     ebx, eax
0x14001e390  call    cs:__imp_RtlCompareMemory
0x14001e397  nop     dword ptr [rax+rax+00h]
0x14001e39c  cmp     rax, rbx
0x14001e39f  jnz     loc_14001E535
0x14001e3a5  mov     rcx, r15
0x14001e3a8  call    LuafvFreePool
0x14001e3ad  mov     r15, r14
0x14001e3b0  lock inc dword ptr [r14+20h]
0x14001e3b5  lock inc dword ptr [r14+20h]
0x14001e3ba  xor     edx, edx
0x14001e3bc  lea     rcx, [r12+10h]
0x14001e3c1  call    cs:__imp_FltReleasePushLockEx
0x14001e3c8  nop     dword ptr [rax+rax+00h]
0x14001e3cd  lea     rcx, FastMutex; FastMutex
0x14001e3d4  mov     [rdi+0E8h], r15
0x14001e3db  call    cs:__imp_ExAcquireFastMutex
0x14001e3e2  nop     dword ptr [rax+rax+00h]
0x14001e3e7  mov     rax, gs:188h
0x14001e3f0  cmp     [rdi+8], rax
0x14001e3f4  jz      loc_14001E47A
0x14001e3fa  xor     edx, edx
0x14001e3fc  mov     rcx, rdi
0x14001e3ff  call    cs:__imp_FltReleasePushLockEx
0x14001e406  nop     dword ptr [rax+rax+00h]
0x14001e40b  lea     rcx, FastMutex; FastMutex
0x14001e412  call    cs:__imp_ExReleaseFastMutex
0x14001e419  nop     dword ptr [rax+rax+00h]
0x14001e41e  mov     rax, [rbp+4Fh+arg_20]
0x14001e422  xor     ebx, ebx
  ... truncated ...
```
