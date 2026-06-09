# I_PEVerifyBootDrivers

- ea: `0x18009a1d0`
- end: `0x18009abc5`
- name: `I_PEVerifyBootDrivers`
- size: `2549`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ec18`
- `0x18002bf20`
- `0x18008047c`
- `0x180097998`
- `0x18009860c`
- `0x18009a1d0`
- `0x18009bca0`
- `0x1800a55e4`
- `0x1800a56e4`
- `0x1800a5b5c`
- `0x1800e17c4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009a2a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009a969`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009a2a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009a969`
- `ntoskrnl!KeStackAttachProcess` at `0x18009a79d`
- `ntoskrnl!KeStackAttachProcess` at `0x18009a79d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009aba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009aba6`
- `ntoskrnl!ZwClose` at `0x18009a5c8`
- `ntoskrnl!ZwClose` at `0x18009a5e1`
- `ntoskrnl!ZwClose` at `0x18009ab4f`
- `ntoskrnl!ZwClose` at `0x18009ab6b`
- `ntoskrnl!ZwClose` at `0x18009a5c8`
- `ntoskrnl!ZwClose` at `0x18009a5e1`
- `ntoskrnl!ZwClose` at `0x18009ab4f`
- `ntoskrnl!ZwClose` at `0x18009ab6b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009a898`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009a898`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009a2e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009a315`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009aa19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009a2e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009a315`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009aa19`
- `ntoskrnl!ZwCreateFile` at `0x18009a3e7`
- `ntoskrnl!ZwCreateFile` at `0x18009a3e7`
- `ntoskrnl!RtlCompareMemory` at `0x18009a9d7`
- `ntoskrnl!RtlCompareMemory` at `0x18009a9d7`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009a5af`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009ab33`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009a5af`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009ab33`
- `ntoskrnl!ZwCreateSection` at `0x18009a461`
- `ntoskrnl!ZwCreateSection` at `0x18009a461`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009a2be`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009a97f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009a2be`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009a97f`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009a4b3`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009a4b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009a2d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009a309`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009aa0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009a2d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009a309`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009aa0d`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009a4ed`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009a4ed`
- `ntoskrnl!EtwWrite` at `0x18009a6eb`
- `ntoskrnl!EtwWrite` at `0x18009ab07`
- `ntoskrnl!EtwWrite` at `0x18009a6eb`
- `ntoskrnl!EtwWrite` at `0x18009ab07`
- `ntoskrnl!PsInitialSystemProcess` at `0x18009a793`

## pseudocode

```c
__int64 __fastcall I_PEVerifyBootDrivers(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  char *v3; // r13
  int v4; // r14d
  unsigned __int16 *v5; // r15
  int v7; // ecx
  int v8; // eax
  int v9; // r15d
  int v10; // r12d
  int v11; // r14d
  int v12; // eax
  __int64 v13; // r15
  int v14; // r12d
  unsigned int v15; // eax
  unsigned int i; // r14d
  char *v17; // r14
  int v18; // ecx
  _QWORD *v19; // rcx
  PVOID *v20; // rax
  int EaBuffer; // [rsp+48h] [rbp-230h]
  int v22; // [rsp+70h] [rbp-208h]
  unsigned int v23; // [rsp+80h] [rbp-1F8h] BYREF
  int v24; // [rsp+84h] [rbp-1F4h] BYREF
  int v25; // [rsp+88h] [rbp-1F0h]
  int v26; // [rsp+8Ch] [rbp-1ECh] BYREF
  int PageHash; // [rsp+90h] [rbp-1E8h]
  PVOID BaseAddress; // [rsp+98h] [rbp-1E0h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-1D8h] BYREF
  void *SectionHandle; // [rsp+A8h] [rbp-1D0h] BYREF
  int v31; // [rsp+B0h] [rbp-1C8h] BYREF
  ULONG_PTR ViewSize[2]; // [rsp+B8h] [rbp-1C0h] BYREF
  char *v33; // [rsp+C8h] [rbp-1B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-1A8h] BYREF
  __int64 v35[2]; // [rsp+100h] [rbp-178h] BYREF
  __int128 v36; // [rsp+110h] [rbp-168h]
  __int128 v37; // [rsp+120h] [rbp-158h]
  unsigned __int16 *v38; // [rsp+130h] [rbp-148h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+138h] [rbp-140h] BYREF
  __int128 FileInformation; // [rsp+148h] [rbp-130h] BYREF
  __int64 v41; // [rsp+158h] [rbp-120h]
  struct _KAPC_STATE ApcState; // [rsp+160h] [rbp-118h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+190h] [rbp-E8h] BYREF
  __int64 v44; // [rsp+1A0h] [rbp-D8h]
  int v45; // [rsp+1A8h] [rbp-D0h]
  int v46; // [rsp+1ACh] [rbp-CCh]
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+1B0h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+1C0h] [rbp-B8h]
  int v49; // [rsp+1C8h] [rbp-B0h]
  int v50; // [rsp+1CCh] [rbp-ACh]
  __int128 Source1; // [rsp+1D0h] [rbp-A8h] BYREF
  int v52; // [rsp+1E0h] [rbp-98h]
  int v53[16]; // [rsp+1F0h] [rbp-88h] BYREF

  v3 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileHandle = 0;
  SectionHandle = 0;
  BaseAddress = 0;
  ViewSize[0] = 0;
  Source1 = 0;
  v52 = 0;
  v23 = 0;
  FileInformation = 0;
  v41 = 0;
  v31 = 2;
  memset(&ApcState, 0, sizeof(ApcState));
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v37 = 0;
  I_PELoadGRL(a1, a2, a3);
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
  if ( !g_fGRLLoadFailed )
  {
    v4 = 0;
    v25 = 0;
    ExReleaseResourceLite(&g_GRLContextLock);
    KeLeaveCriticalRegion();
    while ( 1 )
    {
      if ( g_PEBootDriverList == &g_PEBootDriverList )
      {
        PEAuthStoreParameter(10, 1);
        goto LABEL_13;
      }
      Source1 = 0;
      v52 = 0;
      v3 = (char *)g_PEBootDriverList;
      ViewSize[1] = (ULONG_PTR)g_PEBootDriverList;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      v5 = (unsigned __int16 *)((char *)g_PEBootDriverList + 16);
      v33 = (char *)g_PEBootDriverList + 16;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)g_PEBootDriverList + 16);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x40u, 0, 0) < 0
        || (ObjectAttributes.Length = 48,
            ObjectAttributes.RootDirectory = 0,
            ObjectAttributes.Attributes = 576,
            ObjectAttributes.ObjectName = 0,
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
            ZwCreateSection(&SectionHandle, 5u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle) < 0)
        || ZwMapViewOfSection(
             SectionHandle,
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &BaseAddress,
             0,
             0,
             0,
             ViewSize,
             ViewShare,
             0,
             2u) < 0
        || ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation) < 0
        || (PageHash = HashKComputeFirstPageHash(
                         32772,
                         (_DWORD)BaseAddress,
                         DWORD2(FileInformation),
                         ViewSize[0],
                         (__int64)&Source1,
                         0,
                         0,
                         0,
                         0,
                         EaBuffer,
                         0,
                         0),
            PageHash < 0) )
      {
        PEAuthStoreParameter(1, 0);
        v23 |= 0x100000u;
        goto LABEL_12;
      }
      v38 = v5;
      if ( (g_PEAuthConfigOptions & 1) != 0 )
      {
        UserData.Ptr = (ULONGLONG)&v31;
        *(_QWORD *)&UserData.Size = 4;
        v7 = *v5;
        v44 = *((_QWORD *)v3 + 3);
        v45 = v7;
        v46 = 0;
        v25 = v4 + 2;
        EtwWrite(g_PEAuthEtwHandle, &PEAUTH_BEGIN_COMPONENT_LOAD, 0, v4 + 2, &UserData);
      }
      v8 = *((_DWORD *)v3 + 8);
      if ( v8 == -1073740760 )
      {
        v9 = g_CatalogFileHashAlgorithm;
        v26 = g_CatalogFileHashAlgorithm;
        v10 = g_CatalogFileHashLength;
        v24 = g_CatalogFileHashLength;
        PageHash = HashKComputeImageHash(
                     (unsigned int)g_CatalogFileHashAlgorithm,
                     BaseAddress,
                     DWORD2(FileInformation),
                     0,
                     v53,
                     0);
        if ( PageHash < 0 )
          goto LABEL_41;
        KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
        v11 = CiVerifyHashInCatalogOrUnsignedCache(
                0,
                (int)v53,
                v10,
                v9,
                0,
                0,
                1,
                1151,
                0,
                0,
                (__int64)v35,
                0,
                0,
                0,
                v22,
                0);
        if ( v11 < 0 )
        {
          if ( LODWORD(v35[0]) )
          {
            I_MincryptFreeChainInfo(v36);
            *(_OWORD *)v35 = 0;
            v36 = 0;
            v37 = 0;
          }
          v11 = CiVerifyHashInCatalogOrUnsignedCache(
                  0,
                  (int)v53,
                  v10,
                  v9,
                  1,
                  0,
                  1,
                  1151,
                  0,
                  0,
                  (__int64)v35,
                  0,
                  0,
                  0,
                  v22,
                  0);
        }
        KeUnstackDetachProcess(&ApcState);
        if ( v11 < 0 )
        {
          if ( v11 == -1073740760 )
            v23 |= 0x10000000u;
          else
            v23 |= 0x100000u;
        }
        else
        {
          v26 = 0;
          v24 = 0;
          v12 = I_PECheckMincryptPolicy((unsigned int)v35, 1, (unsigned int)v53, (unsigned int)&v24, (__int64)&v26);
          v23 |= v12;
          if ( !v23 && v26 == 0x10002 )
            v23 = 0x10000;
        }
        if ( LODWORD(v35[0]) )
        {
          I_MincryptFreeChainInfo(v36);
          *(_OWORD *)v35 = 0;
          v36 = 0;
          v37 = 0;
        }
      }
      else if ( v8 < 0 )
      {
LABEL_41:
        v23 |= 0x100000u;
      }
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
      v13 = qword_180049410;
      v14 = 0;
      if ( qword_180049410 && *(_QWORD *)qword_180049410 && *(_QWORD *)(qword_180049410 + 8) )
      {
        v15 = *(_DWORD *)(*(_QWORD *)qword_180049410 + 40LL);
        v24 = v15;
        for ( i = 0; i < v15; ++i )
        {
          if ( RtlCompareMemory(&Source1, (const void *)(*(_QWORD *)(v13 + 8) + 20LL * i), 0x14u) == 20 )
          {
            v14 = 1;
            break;
          }
          v15 = v24;
        }
      }
      if ( v14 )
        v23 |= 0x2000u;
      ExReleaseResourceLite(&g_GRLContextLock);
      KeLeaveCriticalRegion();
      if ( v23 )
      {
        PEAuthStoreParameter(1, 0);
        g_PEAuthStateVariables = 0;
        v23 |= 2u;
        v17 = v33;
        I_PEUpdateHashCache(&Source1, 1, 0);
        if ( (g_PEAuthConfigOptions & 1) != 0 )
          I_PEWriteComponentLoadExEvents(v23, 0, v17, 1);
      }
      if ( (g_PEAuthConfigOptions & 1) != 0 )
      {
        v47.Ptr = (ULONGLONG)&v23;
        *(_QWORD *)&v47.Size = 4;
        v18 = *v38;
        v48 = *((_QWORD *)v3 + 3);
        v49 = v18;
        v50 = 0;
        EtwWrite(g_PEAuthEtwHandle, &PEAUTH_END_COMPONENT_LOAD, 0, 2u, &v47);
        v4 = 0;
        v25 = 0;
      }
      else
      {
        v4 = v25;
      }
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
      BaseAddress = 0;
      ZwClose(FileHandle);
      FileHandle = 0;
      ZwClose(SectionHandle);
      SectionHandle = 0;
      ViewSize[0] = 0;
      v19 = *(_QWORD **)v3;
      if ( *(char **)(*(_QWORD *)v3 + 8LL) != v3 || (v20 = (PVOID *)*((_QWORD *)v3 + 1), *v20 != v3) )
        __fastfail(3u);
      *v20 = v19;
      v19[1] = v20;
      ExFreePoolWithTag(v3, 0);
      v23 = 0;
    }
  }
  ExReleaseResourceLite(&g_GRLContextLock);
  KeLeaveCriticalRegion();
  PEAuthStoreParameter(1, 0);
LABEL_12:
  g_PEAuthStateVariables = 0;
LABEL_13:
  if ( BaseAddress )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( v23 )
  {
    v23 |= 2u;
    I_PEUpdateHashCache(&Source1, 1, 0);
    if ( (g_PEAuthConfigOptions & 1) != 0 )
      I_PEWriteComponentLoadExEvents(v23, 0, v3 + 16, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x18009a1d0  mov     r11, rsp
0x18009a1d3  push    rbx
0x18009a1d4  push    rsi
0x18009a1d5  push    rdi
0x18009a1d6  push    r12
0x18009a1d8  push    r13
0x18009a1da  push    r14
0x18009a1dc  push    r15
0x18009a1de  sub     rsp, 240h
0x18009a1e5  mov     rax, cs:__security_cookie
0x18009a1ec  xor     rax, rsp
0x18009a1ef  mov     [rsp+278h+var_48], rax
0x18009a1f7  xor     ebx, ebx
0x18009a1f9  mov     r13d, ebx
0x18009a1fc  xor     eax, eax
0x18009a1fe  xorps   xmm0, xmm0
0x18009a201  movups  xmmword ptr [rsp+278h+ObjectAttributes.Length], xmm0
0x18009a209  movups  xmmword ptr [rsp+278h+ObjectAttributes.ObjectName], xmm0
0x18009a211  movups  xmmword ptr [rsp+278h+ObjectAttributes+1Ch], xmm0
0x18009a219  movups  xmmword ptr [rsp+278h+IoStatusBlock], xmm0
0x18009a221  mov     [r11-1D8h], rbx
0x18009a228  mov     [r11-1D0h], rbx
0x18009a22f  mov     [r11-1E0h], rbx
0x18009a236  mov     [r11-1C0h], rbx
0x18009a23d  movups  [rsp+278h+Source1], xmm0
0x18009a245  mov     [rsp+278h+var_98], eax
0x18009a24c  mov     [rsp+278h+var_1F8], ebx
0x18009a253  movups  [rsp+278h+FileInformation], xmm0
0x18009a25b  mov     [r11-120h], rax
0x18009a262  mov     [rsp+278h+var_1C8], 2
0x18009a26d  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink], xmm0
0x18009a275  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink+10h], xmm0
0x18009a27d  movups  xmmword ptr [rsp+278h+ApcState.Process], xmm0
0x18009a285  xorps   xmm1, xmm1
0x18009a288  movups  xmmword ptr [rsp+278h+var_178], xmm1
0x18009a290  movups  [rsp+278h+var_168], xmm1
0x18009a298  movups  [rsp+278h+var_158], xmm1
0x18009a2a0  call    I_PELoadGRL
0x18009a2a5  call    cs:__imp_KeEnterCriticalRegion
0x18009a2ac  nop     dword ptr [rax+rax+00h]
0x18009a2b1  lea     edi, [rbx+1]
0x18009a2b4  mov     dl, dil; Wait
0x18009a2b7  lea     rcx, g_GRLContextLock; Resource
0x18009a2be  call    cs:__imp_ExAcquireResourceSharedLite
0x18009a2c5  nop     dword ptr [rax+rax+00h]
0x18009a2ca  lea     rcx, g_GRLContextLock; Resource
0x18009a2d1  cmp     cs:g_fGRLLoadFailed, ebx
0x18009a2d7  jz      short loc_18009A2FF
0x18009a2d9  call    cs:__imp_ExReleaseResourceLite
0x18009a2e0  nop     dword ptr [rax+rax+00h]
0x18009a2e5  call    cs:__imp_KeLeaveCriticalRegion
0x18009a2ec  nop     dword ptr [rax+rax+00h]
0x18009a2f1  xor     edx, edx
0x18009a2f3  mov     ecx, edi
0x18009a2f5  call    PEAuthStoreParameter
0x18009a2fa  jmp     loc_18009A598
0x18009a2ff  mov     r14d, ebx
0x18009a302  mov     [rsp+278h+var_1F0], ebx
0x18009a309  call    cs:__imp_ExReleaseResourceLite
0x18009a310  nop     dword ptr [rax+rax+00h]
0x18009a315  call    cs:__imp_KeLeaveCriticalRegion
0x18009a31c  nop     dword ptr [rax+rax+00h]
0x18009a321  mov     esi, 100000h
0x18009a326  lea     rcx, g_PEBootDriverList
0x18009a32d  mov     rax, cs:g_PEBootDriverList
0x18009a334  cmp     rax, rcx
0x18009a337  jnz     short loc_18009A34A
0x18009a339  mov     edx, edi
0x18009a33b  mov     ecx, 0Ah
0x18009a340  call    PEAuthStoreParameter
0x18009a345  jmp     loc_18009A59E
0x18009a34a  xorps   xmm0, xmm0
0x18009a34d  xor     ecx, ecx
0x18009a34f  movups  [rsp+278h+Source1], xmm0
0x18009a357  mov     [rsp+278h+var_98], ecx
0x18009a35e  mov     r13, rax
0x18009a361  mov     [rsp+278h+var_1B8], rax
0x18009a369  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x18009a374  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x18009a37c  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x18009a387  lea     r15, [rax+10h]
0x18009a38b  mov     [rsp+278h+var_1B0], r15
0x18009a393  mov     [rsp+278h+ObjectAttributes.ObjectName], r15
0x18009a39b  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009a3a4  mov     [rsp+278h+EaLength], ebx; EaLength
0x18009a3a8  mov     [rsp+278h+EaBuffer], rbx; EaBuffer
0x18009a3ad  mov     [rsp+278h+CreateOptions], 40h ; '@'; CreateOptions
0x18009a3b5  mov     [rsp+278h+CreateDisposition], edi; CreateDisposition
0x18009a3b9  mov     [rsp+278h+ShareAccess], edi; ShareAccess
0x18009a3bd  mov     [rsp+278h+FileAttributes], 80h; FileAttributes
0x18009a3c5  mov     [rsp+278h+AllocationSize], rbx; AllocationSize
0x18009a3ca  lea     r9, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x18009a3d2  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x18009a3da  mov     edx, 80000000h; DesiredAccess
0x18009a3df  lea     rcx, [rsp+278h+FileHandle]; FileHandle
0x18009a3e7  call    cs:__imp_ZwCreateFile
0x18009a3ee  nop     dword ptr [rax+rax+00h]
0x18009a3f3  test    eax, eax
0x18009a3f5  js      loc_18009A588
0x18009a3fb  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x18009a406  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x18009a40e  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x18009a419  mov     [rsp+278h+ObjectAttributes.ObjectName], rbx
0x18009a421  xorps   xmm0, xmm0
0x18009a424  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009a42d  mov     rax, [rsp+278h+FileHandle]
0x18009a435  mov     qword ptr [rsp+278h+ShareAccess], rax; FileHandle
0x18009a43a  mov     [rsp+278h+FileAttributes], 8000000h; AllocationAttributes
0x18009a442  mov     dword ptr [rsp+278h+AllocationSize], 2; SectionPageProtection
0x18009a44a  xor     r9d, r9d; MaximumSize
0x18009a44d  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x18009a455  lea     edx, [r9+5]; DesiredAccess
0x18009a459  lea     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x18009a461  call    cs:__imp_ZwCreateSection
0x18009a468  nop     dword ptr [rax+rax+00h]
0x18009a46d  test    eax, eax
0x18009a46f  js      loc_18009A588
0x18009a475  mov     dword ptr [rsp+278h+EaBuffer], 2; Win32Protect
0x18009a47d  mov     [rsp+278h+CreateOptions], ebx; AllocationType
0x18009a481  mov     [rsp+278h+CreateDisposition], edi; InheritDisposition
0x18009a485  lea     rax, [rsp+278h+ViewSize]
0x18009a48d  mov     qword ptr [rsp+278h+ShareAccess], rax; ViewSize
0x18009a492  mov     qword ptr [rsp+278h+FileAttributes], rbx; SectionOffset
0x18009a497  mov     [rsp+278h+AllocationSize], rbx; CommitSize
0x18009a49c  xor     r9d, r9d; ZeroBits
0x18009a49f  lea     r8, [rsp+278h+BaseAddress]; BaseAddress
0x18009a4a7  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009a4ab  mov     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x18009a4b3  call    cs:__imp_ZwMapViewOfSection
0x18009a4ba  nop     dword ptr [rax+rax+00h]
0x18009a4bf  test    eax, eax
0x18009a4c1  js      loc_18009A588
0x18009a4c7  mov     dword ptr [rsp+278h+AllocationSize], 5; FileInformationClass
0x18009a4cf  mov     r9d, 18h; Length
0x18009a4d5  lea     r8, [rsp+278h+FileInformation]; FileInformation
0x18009a4dd  lea     rdx, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x18009a4e5  mov     rcx, [rsp+278h+FileHandle]; FileHandle
0x18009a4ed  call    cs:__imp_ZwQueryInformationFile
0x18009a4f4  nop     dword ptr [rax+rax+00h]
0x18009a4f9  test    eax, eax
0x18009a4fb  js      loc_18009A588
0x18009a501  mov     [rsp+278h+var_220], rbx
0x18009a506  mov     qword ptr [rsp+278h+EaLength], rbx
0x18009a50b  mov     qword ptr [rsp+278h+CreateOptions], rbx
0x18009a510  mov     qword ptr [rsp+278h+CreateDisposition], rbx
0x18009a515  mov     qword ptr [rsp+278h+ShareAccess], rbx
0x18009a51a  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x18009a51f  lea     rax, [rsp+278h+Source1]
0x18009a527  mov     [rsp+278h+AllocationSize], rax
0x18009a52c  mov     r9d, dword ptr [rsp+278h+ViewSize]
0x18009a534  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x18009a53c  mov     rdx, [rsp+278h+BaseAddress]
0x18009a544  mov     ecx, 8004h
0x18009a549  call    HashKComputeFirstPageHash
0x18009a54e  mov     [rsp+278h+var_1E8], eax
0x18009a555  jmp     short loc_18009A580
0x18009a557  mov     [rsp+278h+var_1E8], eax
0x18009a55e  xor     ebx, ebx
0x18009a560  lea     edi, [rbx+1]
0x18009a563  mov     esi, 100000h
0x18009a568  mov     r13, [rsp+278h+var_1B8]
0x18009a570  mov     r14d, [rsp+278h+var_1F0]
0x18009a578  mov     r15, [rsp+278h+var_1B0]
0x18009a580  test    eax, eax
0x18009a582  jns     loc_18009A671
0x18009a588  xor     edx, edx
0x18009a58a  mov     ecx, edi
0x18009a58c  call    PEAuthStoreParameter
0x18009a591  or      [rsp+278h+var_1F8], esi
0x18009a598  mov     cs:g_PEAuthStateVariables, ebx
0x18009a59e  mov     rdx, [rsp+278h+BaseAddress]; BaseAddress
0x18009a5a6  test    rdx, rdx
0x18009a5a9  jz      short loc_18009A5BB
0x18009a5ab  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009a5af  call    cs:__imp_ZwUnmapViewOfSection
0x18009a5b6  nop     dword ptr [rax+rax+00h]
0x18009a5bb  mov     rcx, [rsp+278h+FileHandle]; Handle
0x18009a5c3  test    rcx, rcx
0x18009a5c6  jz      short loc_18009A5D4
0x18009a5c8  call    cs:__imp_ZwClose
0x18009a5cf  nop     dword ptr [rax+rax+00h]
0x18009a5d4  mov     rcx, [rsp+278h+SectionHandle]; Handle
0x18009a5dc  test    rcx, rcx
0x18009a5df  jz      short loc_18009A5ED
0x18009a5e1  call    cs:__imp_ZwClose
0x18009a5e8  nop     dword ptr [rax+rax+00h]
0x18009a5ed  cmp     [rsp+278h+var_1F8], 0
0x18009a5f5  jz      short loc_18009A64B
0x18009a5f7  mov     r9d, [rsp+278h+var_1F8]
0x18009a5ff  or      r9d, 2
0x18009a603  mov     [rsp+278h+var_1F8], r9d
0x18009a60b  mov     [rsp+278h+FileAttributes], ebx; int
0x18009a60f  mov     dword ptr [rsp+278h+AllocationSize], edi; int
0x18009a613  lea     r8, [r13+10h]
0x18009a617  lea     rdx, g_rgEmptyHash
0x18009a61e  lea     rcx, [rsp+278h+Source1]; Source2
0x18009a626  call    I_PEUpdateHashCache
0x18009a62b  mov     ecx, cs:g_PEAuthConfigOptions
0x18009a631  test    dil, cl
0x18009a634  jz      short loc_18009A64B
0x18009a636  mov     r9d, edi
0x18009a639  lea     r8, [r13+10h]
0x18009a63d  xor     edx, edx
0x18009a63f  mov     ecx, [rsp+278h+var_1F8]
0x18009a646  call    I_PEWriteComponentLoadExEvents
0x18009a64b  mov     eax, edi
0x18009a64d  mov     rcx, [rsp+278h+var_48]
0x18009a655  xor     rcx, rsp; StackCookie
0x18009a658  call    __security_check_cookie
0x18009a65d  add     rsp, 240h
0x18009a664  pop     r15
0x18009a666  pop     r14
0x18009a668  pop     r13
0x18009a66a  pop     r12
0x18009a66c  pop     rdi
0x18009a66d  pop     rsi
0x18009a66e  pop     rbx
0x18009a66f  retn
0x18009a671  mov     [rsp+278h+var_148], r15
0x18009a679  mov     eax, cs:g_PEAuthConfigOptions
0x18009a67f  test    dil, al
0x18009a682  jz      short loc_18009A6F7
0x18009a684  lea     rax, [rsp+278h+var_1C8]
0x18009a68c  mov     [rsp+278h+UserData.Ptr], rax
0x18009a694  mov     qword ptr [rsp+278h+UserData.Size], 4
0x18009a6a0  movzx   ecx, word ptr [r15]
0x18009a6a4  mov     rax, [r13+18h]
0x18009a6a8  mov     [rsp+278h+var_D8], rax
0x18009a6b0  mov     [rsp+278h+var_D0], ecx
0x18009a6b7  mov     [rsp+278h+var_CC], ebx
0x18009a6be  add     r14d, 2
0x18009a6c2  mov     [rsp+278h+var_1F0], r14d
0x18009a6ca  lea     rax, [rsp+278h+UserData]
0x18009a6d2  mov     [rsp+278h+AllocationSize], rax; UserData
0x18009a6d7  mov     r9d, r14d; UserDataCount
0x18009a6da  xor     r8d, r8d; ActivityId
0x18009a6dd  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x18009a6e4  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18009a6eb  call    cs:__imp_EtwWrite
0x18009a6f2  nop     dword ptr [rax+rax+00h]
0x18009a6f7  mov     eax, [r13+20h]
0x18009a6fb  cmp     eax, 0C0000428h
0x18009a700  jnz     loc_18009A95E
0x18009a706  mov     r15d, cs:g_CatalogFileHashAlgorithm
0x18009a70d  mov     [rsp+278h+var_1EC], r15d
0x18009a715  mov     r12d, cs:g_CatalogFileHashLength
0x18009a71c  mov     [rsp+278h+var_1F4], r12d
0x18009a724  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x18009a72c  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x18009a731  lea     rax, [rsp+278h+var_88]
0x18009a739  mov     [rsp+278h+AllocationSize], rax
0x18009a73e  xor     r9d, r9d
0x18009a741  mov     rdx, [rsp+278h+BaseAddress]
0x18009a749  mov     ecx, r15d
0x18009a74c  call    HashKComputeImageHash
0x18009a751  mov     [rsp+278h+var_1E8], eax
0x18009a758  jmp     short loc_18009A783
0x18009a75a  mov     [rsp+278h+var_1E8], eax
0x18009a761  xor     ebx, ebx
0x18009a763  lea     edi, [rbx+1]
0x18009a766  mov     esi, 100000h
0x18009a76b  mov     r13, [rsp+278h+var_1B8]
0x18009a773  mov     r15d, [rsp+278h+var_1EC]
0x18009a77b  mov     r12d, [rsp+278h+var_1F4]
0x18009a783  test    eax, eax
0x18009a785  js      loc_18009A962
0x18009a78b  lea     rdx, [rsp+278h+ApcState]; ApcState
0x18009a793  mov     rcx, cs:__imp_PsInitialSystemProcess
0x18009a79a  mov     rcx, [rcx]; PROCESS
0x18009a79d  call    cs:__imp_KeStackAttachProcess
0x18009a7a4  nop     dword ptr [rax+rax+00h]
0x18009a7a9  mov     [rsp+278h+var_200], rbx; __int64
0x18009a7ae  mov     [rsp+278h+var_210], rbx; __int64
0x18009a7b3  mov     [rsp+278h+var_218], rbx; __int64
0x18009a7b8  mov     [rsp+278h+var_220], rbx; __int64
0x18009a7bd  lea     rax, [rsp+278h+var_178]
0x18009a7c5  mov     qword ptr [rsp+278h+EaLength], rax; __int64
0x18009a7ca  mov     [rsp+278h+EaBuffer], rbx; __int64
0x18009a7cf  mov     qword ptr [rsp+278h+CreateOptions], rbx; SourceString
0x18009a7d4  mov     [rsp+278h+CreateDisposition], 47Fh; int
0x18009a7dc  mov     [rsp+278h+ShareAccess], edi; int
0x18009a7e0  mov     [rsp+278h+FileAttributes], ebx; int
0x18009a7e4  mov     dword ptr [rsp+278h+AllocationSize], ebx; int
0x18009a7e8  mov     r9d, r15d; int
0x18009a7eb  mov     r8d, r12d; int
0x18009a7ee  lea     rdx, [rsp+278h+var_88]; int
0x18009a7f6  xor     ecx, ecx; int
0x18009a7f8  call    CiVerifyHashInCatalogOrUnsignedCache
0x18009a7fd  mov     r14d, eax
0x18009a800  test    eax, eax
0x18009a802  jns     loc_18009A890
0x18009a808  cmp     dword ptr [rsp+278h+var_178], ebx
0x18009a80f  jz      short loc_18009A839
0x18009a811  mov     rcx, qword ptr [rsp+278h+var_168]
0x18009a819  call    I_MincryptFreeChainInfo
0x18009a81e  xorps   xmm0, xmm0
0x18009a821  movups  xmmword ptr [rsp+278h+var_178], xmm0
0x18009a829  movups  [rsp+278h+var_168], xmm0
0x18009a831  movups  [rsp+278h+var_158], xmm0
0x18009a839  mov     [rsp+278h+var_200], rbx; __int64
  ... truncated ...
```
