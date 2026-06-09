# I_PEVerifyBootDrivers

- ea: `0x18009f510`
- end: `0x18009ff05`
- name: `I_PEVerifyBootDrivers`
- size: `2549`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ec28`
- `0x18002c0d0`
- `0x180080e90`
- `0x18008e168`
- `0x18008eddc`
- `0x18009f510`
- `0x1800a0fe0`
- `0x1800a2f2c`
- `0x1800a5238`
- `0x1800a5338`
- `0x1800a57b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009f5e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009fca9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009f5e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009fca9`
- `ntoskrnl!KeStackAttachProcess` at `0x18009fadd`
- `ntoskrnl!KeStackAttachProcess` at `0x18009fadd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009fee6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009fee6`
- `ntoskrnl!ZwClose` at `0x18009f908`
- `ntoskrnl!ZwClose` at `0x18009f921`
- `ntoskrnl!ZwClose` at `0x18009fe8f`
- `ntoskrnl!ZwClose` at `0x18009feab`
- `ntoskrnl!ZwClose` at `0x18009f908`
- `ntoskrnl!ZwClose` at `0x18009f921`
- `ntoskrnl!ZwClose` at `0x18009fe8f`
- `ntoskrnl!ZwClose` at `0x18009feab`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009fbd8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009fbd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f625`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f655`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009fd59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f625`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f655`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009fd59`
- `ntoskrnl!ZwCreateFile` at `0x18009f727`
- `ntoskrnl!ZwCreateFile` at `0x18009f727`
- `ntoskrnl!RtlCompareMemory` at `0x18009fd17`
- `ntoskrnl!RtlCompareMemory` at `0x18009fd17`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009f8ef`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009fe73`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009f8ef`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18009fe73`
- `ntoskrnl!ZwCreateSection` at `0x18009f7a1`
- `ntoskrnl!ZwCreateSection` at `0x18009f7a1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009f5fe`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009fcbf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009f5fe`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009fcbf`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009f7f3`
- `ntoskrnl!ZwMapViewOfSection` at `0x18009f7f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009f619`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009f649`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009fd4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009f619`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009f649`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009fd4d`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009f82d`
- `ntoskrnl!ZwQueryInformationFile` at `0x18009f82d`
- `ntoskrnl!EtwWrite` at `0x18009fa2b`
- `ntoskrnl!EtwWrite` at `0x18009fe47`
- `ntoskrnl!EtwWrite` at `0x18009fa2b`
- `ntoskrnl!EtwWrite` at `0x18009fe47`
- `ntoskrnl!PsInitialSystemProcess` at `0x18009fad3`

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
      v13 = qword_180049428;
      v14 = 0;
      if ( qword_180049428 && *(_QWORD *)qword_180049428 && *(_QWORD *)(qword_180049428 + 8) )
      {
        v15 = *(_DWORD *)(*(_QWORD *)qword_180049428 + 40LL);
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
0x18009f510  mov     r11, rsp
0x18009f513  push    rbx
0x18009f514  push    rsi
0x18009f515  push    rdi
0x18009f516  push    r12
0x18009f518  push    r13
0x18009f51a  push    r14
0x18009f51c  push    r15
0x18009f51e  sub     rsp, 240h
0x18009f525  mov     rax, cs:__security_cookie
0x18009f52c  xor     rax, rsp
0x18009f52f  mov     [rsp+278h+var_48], rax
0x18009f537  xor     ebx, ebx
0x18009f539  mov     r13d, ebx
0x18009f53c  xor     eax, eax
0x18009f53e  xorps   xmm0, xmm0
0x18009f541  movups  xmmword ptr [rsp+278h+ObjectAttributes.Length], xmm0
0x18009f549  movups  xmmword ptr [rsp+278h+ObjectAttributes.ObjectName], xmm0
0x18009f551  movups  xmmword ptr [rsp+278h+ObjectAttributes+1Ch], xmm0
0x18009f559  movups  xmmword ptr [rsp+278h+IoStatusBlock], xmm0
0x18009f561  mov     [r11-1D8h], rbx
0x18009f568  mov     [r11-1D0h], rbx
0x18009f56f  mov     [r11-1E0h], rbx
0x18009f576  mov     [r11-1C0h], rbx
0x18009f57d  movups  [rsp+278h+Source1], xmm0
0x18009f585  mov     [rsp+278h+var_98], eax
0x18009f58c  mov     [rsp+278h+var_1F8], ebx
0x18009f593  movups  [rsp+278h+FileInformation], xmm0
0x18009f59b  mov     [r11-120h], rax
0x18009f5a2  mov     [rsp+278h+var_1C8], 2
0x18009f5ad  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink], xmm0
0x18009f5b5  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink+10h], xmm0
0x18009f5bd  movups  xmmword ptr [rsp+278h+ApcState.Process], xmm0
0x18009f5c5  xorps   xmm1, xmm1
0x18009f5c8  movups  xmmword ptr [rsp+278h+var_178], xmm1
0x18009f5d0  movups  [rsp+278h+var_168], xmm1
0x18009f5d8  movups  [rsp+278h+var_158], xmm1
0x18009f5e0  call    I_PELoadGRL
0x18009f5e5  call    cs:__imp_KeEnterCriticalRegion
0x18009f5ec  nop     dword ptr [rax+rax+00h]
0x18009f5f1  lea     edi, [rbx+1]
0x18009f5f4  mov     dl, dil; Wait
0x18009f5f7  lea     rcx, g_GRLContextLock; Resource
0x18009f5fe  call    cs:__imp_ExAcquireResourceSharedLite
0x18009f605  nop     dword ptr [rax+rax+00h]
0x18009f60a  lea     rcx, g_GRLContextLock; Resource
0x18009f611  cmp     cs:g_fGRLLoadFailed, ebx
0x18009f617  jz      short loc_18009F63F
0x18009f619  call    cs:__imp_ExReleaseResourceLite
0x18009f620  nop     dword ptr [rax+rax+00h]
0x18009f625  call    cs:__imp_KeLeaveCriticalRegion
0x18009f62c  nop     dword ptr [rax+rax+00h]
0x18009f631  xor     edx, edx
0x18009f633  mov     ecx, edi
0x18009f635  call    PEAuthStoreParameter
0x18009f63a  jmp     loc_18009F8D8
0x18009f63f  mov     r14d, ebx
0x18009f642  mov     [rsp+278h+var_1F0], ebx
0x18009f649  call    cs:__imp_ExReleaseResourceLite
0x18009f650  nop     dword ptr [rax+rax+00h]
0x18009f655  call    cs:__imp_KeLeaveCriticalRegion
0x18009f65c  nop     dword ptr [rax+rax+00h]
0x18009f661  mov     esi, 100000h
0x18009f666  lea     rcx, g_PEBootDriverList
0x18009f66d  mov     rax, cs:g_PEBootDriverList
0x18009f674  cmp     rax, rcx
0x18009f677  jnz     short loc_18009F68A
0x18009f679  mov     edx, edi
0x18009f67b  mov     ecx, 0Ah
0x18009f680  call    PEAuthStoreParameter
0x18009f685  jmp     loc_18009F8DE
0x18009f68a  xorps   xmm0, xmm0
0x18009f68d  xor     ecx, ecx
0x18009f68f  movups  [rsp+278h+Source1], xmm0
0x18009f697  mov     [rsp+278h+var_98], ecx
0x18009f69e  mov     r13, rax
0x18009f6a1  mov     [rsp+278h+var_1B8], rax
0x18009f6a9  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x18009f6b4  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x18009f6bc  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x18009f6c7  lea     r15, [rax+10h]
0x18009f6cb  mov     [rsp+278h+var_1B0], r15
0x18009f6d3  mov     [rsp+278h+ObjectAttributes.ObjectName], r15
0x18009f6db  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009f6e4  mov     [rsp+278h+EaLength], ebx; EaLength
0x18009f6e8  mov     [rsp+278h+EaBuffer], rbx; EaBuffer
0x18009f6ed  mov     [rsp+278h+CreateOptions], 40h ; '@'; CreateOptions
0x18009f6f5  mov     [rsp+278h+CreateDisposition], edi; CreateDisposition
0x18009f6f9  mov     [rsp+278h+ShareAccess], edi; ShareAccess
0x18009f6fd  mov     [rsp+278h+FileAttributes], 80h; FileAttributes
0x18009f705  mov     [rsp+278h+AllocationSize], rbx; AllocationSize
0x18009f70a  lea     r9, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x18009f712  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x18009f71a  mov     edx, 80000000h; DesiredAccess
0x18009f71f  lea     rcx, [rsp+278h+FileHandle]; FileHandle
0x18009f727  call    cs:__imp_ZwCreateFile
0x18009f72e  nop     dword ptr [rax+rax+00h]
0x18009f733  test    eax, eax
0x18009f735  js      loc_18009F8C8
0x18009f73b  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x18009f746  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x18009f74e  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x18009f759  mov     [rsp+278h+ObjectAttributes.ObjectName], rbx
0x18009f761  xorps   xmm0, xmm0
0x18009f764  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009f76d  mov     rax, [rsp+278h+FileHandle]
0x18009f775  mov     qword ptr [rsp+278h+ShareAccess], rax; FileHandle
0x18009f77a  mov     [rsp+278h+FileAttributes], 8000000h; AllocationAttributes
0x18009f782  mov     dword ptr [rsp+278h+AllocationSize], 2; SectionPageProtection
0x18009f78a  xor     r9d, r9d; MaximumSize
0x18009f78d  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x18009f795  lea     edx, [r9+5]; DesiredAccess
0x18009f799  lea     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x18009f7a1  call    cs:__imp_ZwCreateSection
0x18009f7a8  nop     dword ptr [rax+rax+00h]
0x18009f7ad  test    eax, eax
0x18009f7af  js      loc_18009F8C8
0x18009f7b5  mov     dword ptr [rsp+278h+EaBuffer], 2; Win32Protect
0x18009f7bd  mov     [rsp+278h+CreateOptions], ebx; AllocationType
0x18009f7c1  mov     [rsp+278h+CreateDisposition], edi; InheritDisposition
0x18009f7c5  lea     rax, [rsp+278h+ViewSize]
0x18009f7cd  mov     qword ptr [rsp+278h+ShareAccess], rax; ViewSize
0x18009f7d2  mov     qword ptr [rsp+278h+FileAttributes], rbx; SectionOffset
0x18009f7d7  mov     [rsp+278h+AllocationSize], rbx; CommitSize
0x18009f7dc  xor     r9d, r9d; ZeroBits
0x18009f7df  lea     r8, [rsp+278h+BaseAddress]; BaseAddress
0x18009f7e7  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009f7eb  mov     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x18009f7f3  call    cs:__imp_ZwMapViewOfSection
0x18009f7fa  nop     dword ptr [rax+rax+00h]
0x18009f7ff  test    eax, eax
0x18009f801  js      loc_18009F8C8
0x18009f807  mov     dword ptr [rsp+278h+AllocationSize], 5; FileInformationClass
0x18009f80f  mov     r9d, 18h; Length
0x18009f815  lea     r8, [rsp+278h+FileInformation]; FileInformation
0x18009f81d  lea     rdx, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x18009f825  mov     rcx, [rsp+278h+FileHandle]; FileHandle
0x18009f82d  call    cs:__imp_ZwQueryInformationFile
0x18009f834  nop     dword ptr [rax+rax+00h]
0x18009f839  test    eax, eax
0x18009f83b  js      loc_18009F8C8
0x18009f841  mov     [rsp+278h+var_220], rbx
0x18009f846  mov     qword ptr [rsp+278h+EaLength], rbx
0x18009f84b  mov     qword ptr [rsp+278h+CreateOptions], rbx
0x18009f850  mov     qword ptr [rsp+278h+CreateDisposition], rbx
0x18009f855  mov     qword ptr [rsp+278h+ShareAccess], rbx
0x18009f85a  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x18009f85f  lea     rax, [rsp+278h+Source1]
0x18009f867  mov     [rsp+278h+AllocationSize], rax
0x18009f86c  mov     r9d, dword ptr [rsp+278h+ViewSize]
0x18009f874  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x18009f87c  mov     rdx, [rsp+278h+BaseAddress]
0x18009f884  mov     ecx, 8004h
0x18009f889  call    HashKComputeFirstPageHash
0x18009f88e  mov     [rsp+278h+var_1E8], eax
0x18009f895  jmp     short loc_18009F8C0
0x18009f897  mov     [rsp+278h+var_1E8], eax
0x18009f89e  xor     ebx, ebx
0x18009f8a0  lea     edi, [rbx+1]
0x18009f8a3  mov     esi, 100000h
0x18009f8a8  mov     r13, [rsp+278h+var_1B8]
0x18009f8b0  mov     r14d, [rsp+278h+var_1F0]
0x18009f8b8  mov     r15, [rsp+278h+var_1B0]
0x18009f8c0  test    eax, eax
0x18009f8c2  jns     loc_18009F9B1
0x18009f8c8  xor     edx, edx
0x18009f8ca  mov     ecx, edi
0x18009f8cc  call    PEAuthStoreParameter
0x18009f8d1  or      [rsp+278h+var_1F8], esi
0x18009f8d8  mov     cs:g_PEAuthStateVariables, ebx
0x18009f8de  mov     rdx, [rsp+278h+BaseAddress]; BaseAddress
0x18009f8e6  test    rdx, rdx
0x18009f8e9  jz      short loc_18009F8FB
0x18009f8eb  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18009f8ef  call    cs:__imp_ZwUnmapViewOfSection
0x18009f8f6  nop     dword ptr [rax+rax+00h]
0x18009f8fb  mov     rcx, [rsp+278h+FileHandle]; Handle
0x18009f903  test    rcx, rcx
0x18009f906  jz      short loc_18009F914
0x18009f908  call    cs:__imp_ZwClose
0x18009f90f  nop     dword ptr [rax+rax+00h]
0x18009f914  mov     rcx, [rsp+278h+SectionHandle]; Handle
0x18009f91c  test    rcx, rcx
0x18009f91f  jz      short loc_18009F92D
0x18009f921  call    cs:__imp_ZwClose
0x18009f928  nop     dword ptr [rax+rax+00h]
0x18009f92d  cmp     [rsp+278h+var_1F8], 0
0x18009f935  jz      short loc_18009F98B
0x18009f937  mov     r9d, [rsp+278h+var_1F8]
0x18009f93f  or      r9d, 2
0x18009f943  mov     [rsp+278h+var_1F8], r9d
0x18009f94b  mov     [rsp+278h+FileAttributes], ebx; int
0x18009f94f  mov     dword ptr [rsp+278h+AllocationSize], edi; int
0x18009f953  lea     r8, [r13+10h]
0x18009f957  lea     rdx, g_rgEmptyHash
0x18009f95e  lea     rcx, [rsp+278h+Source1]; Source2
0x18009f966  call    I_PEUpdateHashCache
0x18009f96b  mov     ecx, cs:g_PEAuthConfigOptions
0x18009f971  test    dil, cl
0x18009f974  jz      short loc_18009F98B
0x18009f976  mov     r9d, edi
0x18009f979  lea     r8, [r13+10h]
0x18009f97d  xor     edx, edx
0x18009f97f  mov     ecx, [rsp+278h+var_1F8]
0x18009f986  call    I_PEWriteComponentLoadExEvents
0x18009f98b  mov     eax, edi
0x18009f98d  mov     rcx, [rsp+278h+var_48]
0x18009f995  xor     rcx, rsp; StackCookie
0x18009f998  call    __security_check_cookie
0x18009f99d  add     rsp, 240h
0x18009f9a4  pop     r15
0x18009f9a6  pop     r14
0x18009f9a8  pop     r13
0x18009f9aa  pop     r12
0x18009f9ac  pop     rdi
0x18009f9ad  pop     rsi
0x18009f9ae  pop     rbx
0x18009f9af  retn
0x18009f9b1  mov     [rsp+278h+var_148], r15
0x18009f9b9  mov     eax, cs:g_PEAuthConfigOptions
0x18009f9bf  test    dil, al
0x18009f9c2  jz      short loc_18009FA37
0x18009f9c4  lea     rax, [rsp+278h+var_1C8]
0x18009f9cc  mov     [rsp+278h+UserData.Ptr], rax
0x18009f9d4  mov     qword ptr [rsp+278h+UserData.Size], 4
0x18009f9e0  movzx   ecx, word ptr [r15]
0x18009f9e4  mov     rax, [r13+18h]
0x18009f9e8  mov     [rsp+278h+var_D8], rax
0x18009f9f0  mov     [rsp+278h+var_D0], ecx
0x18009f9f7  mov     [rsp+278h+var_CC], ebx
0x18009f9fe  add     r14d, 2
0x18009fa02  mov     [rsp+278h+var_1F0], r14d
0x18009fa0a  lea     rax, [rsp+278h+UserData]
0x18009fa12  mov     [rsp+278h+AllocationSize], rax; UserData
0x18009fa17  mov     r9d, r14d; UserDataCount
0x18009fa1a  xor     r8d, r8d; ActivityId
0x18009fa1d  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x18009fa24  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x18009fa2b  call    cs:__imp_EtwWrite
0x18009fa32  nop     dword ptr [rax+rax+00h]
0x18009fa37  mov     eax, [r13+20h]
0x18009fa3b  cmp     eax, 0C0000428h
0x18009fa40  jnz     loc_18009FC9E
0x18009fa46  mov     r15d, cs:g_CatalogFileHashAlgorithm
0x18009fa4d  mov     [rsp+278h+var_1EC], r15d
0x18009fa55  mov     r12d, cs:g_CatalogFileHashLength
0x18009fa5c  mov     [rsp+278h+var_1F4], r12d
0x18009fa64  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x18009fa6c  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x18009fa71  lea     rax, [rsp+278h+var_88]
0x18009fa79  mov     [rsp+278h+AllocationSize], rax
0x18009fa7e  xor     r9d, r9d
0x18009fa81  mov     rdx, [rsp+278h+BaseAddress]
0x18009fa89  mov     ecx, r15d
0x18009fa8c  call    HashKComputeImageHash
0x18009fa91  mov     [rsp+278h+var_1E8], eax
0x18009fa98  jmp     short loc_18009FAC3
0x18009fa9a  mov     [rsp+278h+var_1E8], eax
0x18009faa1  xor     ebx, ebx
0x18009faa3  lea     edi, [rbx+1]
0x18009faa6  mov     esi, 100000h
0x18009faab  mov     r13, [rsp+278h+var_1B8]
0x18009fab3  mov     r15d, [rsp+278h+var_1EC]
0x18009fabb  mov     r12d, [rsp+278h+var_1F4]
0x18009fac3  test    eax, eax
0x18009fac5  js      loc_18009FCA2
0x18009facb  lea     rdx, [rsp+278h+ApcState]; ApcState
0x18009fad3  mov     rcx, cs:__imp_PsInitialSystemProcess
0x18009fada  mov     rcx, [rcx]; PROCESS
0x18009fadd  call    cs:__imp_KeStackAttachProcess
0x18009fae4  nop     dword ptr [rax+rax+00h]
0x18009fae9  mov     [rsp+278h+var_200], rbx; __int64
0x18009faee  mov     [rsp+278h+var_210], rbx; __int64
0x18009faf3  mov     [rsp+278h+var_218], rbx; __int64
0x18009faf8  mov     [rsp+278h+var_220], rbx; __int64
0x18009fafd  lea     rax, [rsp+278h+var_178]
0x18009fb05  mov     qword ptr [rsp+278h+EaLength], rax; __int64
0x18009fb0a  mov     [rsp+278h+EaBuffer], rbx; __int64
0x18009fb0f  mov     qword ptr [rsp+278h+CreateOptions], rbx; SourceString
0x18009fb14  mov     [rsp+278h+CreateDisposition], 47Fh; int
0x18009fb1c  mov     [rsp+278h+ShareAccess], edi; int
0x18009fb20  mov     [rsp+278h+FileAttributes], ebx; int
0x18009fb24  mov     dword ptr [rsp+278h+AllocationSize], ebx; int
0x18009fb28  mov     r9d, r15d; int
0x18009fb2b  mov     r8d, r12d; int
0x18009fb2e  lea     rdx, [rsp+278h+var_88]; int
0x18009fb36  xor     ecx, ecx; int
0x18009fb38  call    CiVerifyHashInCatalogOrUnsignedCache
0x18009fb3d  mov     r14d, eax
0x18009fb40  test    eax, eax
0x18009fb42  jns     loc_18009FBD0
0x18009fb48  cmp     dword ptr [rsp+278h+var_178], ebx
0x18009fb4f  jz      short loc_18009FB79
0x18009fb51  mov     rcx, qword ptr [rsp+278h+var_168]
0x18009fb59  call    I_MincryptFreeChainInfo
0x18009fb5e  xorps   xmm0, xmm0
0x18009fb61  movups  xmmword ptr [rsp+278h+var_178], xmm0
0x18009fb69  movups  [rsp+278h+var_168], xmm0
0x18009fb71  movups  [rsp+278h+var_158], xmm0
0x18009fb79  mov     [rsp+278h+var_200], rbx; __int64
  ... truncated ...
```
