# I_PEVerifyBootDrivers

- ea: `0x180098ba0`
- end: `0x180099595`
- name: `I_PEVerifyBootDrivers`
- size: `2549`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ec18`
- `0x18002bef0`
- `0x18007ee50`
- `0x180096368`
- `0x180096fdc`
- `0x180098ba0`
- `0x18009a670`
- `0x1800a3fb4`
- `0x1800a40b4`
- `0x1800a452c`
- `0x1800e07d4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180098c75`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180099339`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180098c75`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180099339`
- `ntoskrnl!KeStackAttachProcess` at `0x18009916d`
- `ntoskrnl!KeStackAttachProcess` at `0x18009916d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099576`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099576`
- `ntoskrnl!ZwClose` at `0x180098f98`
- `ntoskrnl!ZwClose` at `0x180098fb1`
- `ntoskrnl!ZwClose` at `0x18009951f`
- `ntoskrnl!ZwClose` at `0x18009953b`
- `ntoskrnl!ZwClose` at `0x180098f98`
- `ntoskrnl!ZwClose` at `0x180098fb1`
- `ntoskrnl!ZwClose` at `0x18009951f`
- `ntoskrnl!ZwClose` at `0x18009953b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180099268`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180099268`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098cb5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098ce5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800993e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098cb5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098ce5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800993e9`
- `ntoskrnl!ZwCreateFile` at `0x180098db7`
- `ntoskrnl!ZwCreateFile` at `0x180098db7`
- `ntoskrnl!RtlCompareMemory` at `0x1800993a7`
- `ntoskrnl!RtlCompareMemory` at `0x1800993a7`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180098f7f`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180099503`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180098f7f`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180099503`
- `ntoskrnl!ZwCreateSection` at `0x180098e31`
- `ntoskrnl!ZwCreateSection` at `0x180098e31`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180098c8e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009934f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180098c8e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18009934f`
- `ntoskrnl!ZwMapViewOfSection` at `0x180098e83`
- `ntoskrnl!ZwMapViewOfSection` at `0x180098e83`
- `ntoskrnl!ExReleaseResourceLite` at `0x180098ca9`
- `ntoskrnl!ExReleaseResourceLite` at `0x180098cd9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800993dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x180098ca9`
- `ntoskrnl!ExReleaseResourceLite` at `0x180098cd9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800993dd`
- `ntoskrnl!ZwQueryInformationFile` at `0x180098ebd`
- `ntoskrnl!ZwQueryInformationFile` at `0x180098ebd`
- `ntoskrnl!EtwWrite` at `0x1800990bb`
- `ntoskrnl!EtwWrite` at `0x1800994d7`
- `ntoskrnl!EtwWrite` at `0x1800990bb`
- `ntoskrnl!EtwWrite` at `0x1800994d7`
- `ntoskrnl!PsInitialSystemProcess` at `0x180099163`

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
                         (int)BaseAddress,
                         SDWORD2(FileInformation),
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
      v13 = qword_180048410;
      v14 = 0;
      if ( qword_180048410 && *(_QWORD *)qword_180048410 && *(_QWORD *)(qword_180048410 + 8) )
      {
        v15 = *(_DWORD *)(*(_QWORD *)qword_180048410 + 40LL);
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
0x180098ba0  mov     r11, rsp
0x180098ba3  push    rbx
0x180098ba4  push    rsi
0x180098ba5  push    rdi
0x180098ba6  push    r12
0x180098ba8  push    r13
0x180098baa  push    r14
0x180098bac  push    r15
0x180098bae  sub     rsp, 240h
0x180098bb5  mov     rax, cs:__security_cookie
0x180098bbc  xor     rax, rsp
0x180098bbf  mov     [rsp+278h+var_48], rax
0x180098bc7  xor     ebx, ebx
0x180098bc9  mov     r13d, ebx
0x180098bcc  xor     eax, eax
0x180098bce  xorps   xmm0, xmm0
0x180098bd1  movups  xmmword ptr [rsp+278h+ObjectAttributes.Length], xmm0
0x180098bd9  movups  xmmword ptr [rsp+278h+ObjectAttributes.ObjectName], xmm0
0x180098be1  movups  xmmword ptr [rsp+278h+ObjectAttributes+1Ch], xmm0
0x180098be9  movups  xmmword ptr [rsp+278h+IoStatusBlock], xmm0
0x180098bf1  mov     [r11-1D8h], rbx
0x180098bf8  mov     [r11-1D0h], rbx
0x180098bff  mov     [r11-1E0h], rbx
0x180098c06  mov     [r11-1C0h], rbx
0x180098c0d  movups  [rsp+278h+Source1], xmm0
0x180098c15  mov     [rsp+278h+var_98], eax
0x180098c1c  mov     [rsp+278h+var_1F8], ebx
0x180098c23  movups  [rsp+278h+FileInformation], xmm0
0x180098c2b  mov     [r11-120h], rax
0x180098c32  mov     [rsp+278h+var_1C8], 2
0x180098c3d  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink], xmm0
0x180098c45  movups  xmmword ptr [rsp+278h+ApcState.ApcListHead.Flink+10h], xmm0
0x180098c4d  movups  xmmword ptr [rsp+278h+ApcState.Process], xmm0
0x180098c55  xorps   xmm1, xmm1
0x180098c58  movups  xmmword ptr [rsp+278h+var_178], xmm1
0x180098c60  movups  [rsp+278h+var_168], xmm1
0x180098c68  movups  [rsp+278h+var_158], xmm1
0x180098c70  call    I_PELoadGRL
0x180098c75  call    cs:__imp_KeEnterCriticalRegion
0x180098c7c  nop     dword ptr [rax+rax+00h]
0x180098c81  lea     edi, [rbx+1]
0x180098c84  mov     dl, dil; Wait
0x180098c87  lea     rcx, g_GRLContextLock; Resource
0x180098c8e  call    cs:__imp_ExAcquireResourceSharedLite
0x180098c95  nop     dword ptr [rax+rax+00h]
0x180098c9a  lea     rcx, g_GRLContextLock; Resource
0x180098ca1  cmp     cs:g_fGRLLoadFailed, ebx
0x180098ca7  jz      short loc_180098CCF
0x180098ca9  call    cs:__imp_ExReleaseResourceLite
0x180098cb0  nop     dword ptr [rax+rax+00h]
0x180098cb5  call    cs:__imp_KeLeaveCriticalRegion
0x180098cbc  nop     dword ptr [rax+rax+00h]
0x180098cc1  xor     edx, edx
0x180098cc3  mov     ecx, edi
0x180098cc5  call    PEAuthStoreParameter
0x180098cca  jmp     loc_180098F68
0x180098ccf  mov     r14d, ebx
0x180098cd2  mov     [rsp+278h+var_1F0], ebx
0x180098cd9  call    cs:__imp_ExReleaseResourceLite
0x180098ce0  nop     dword ptr [rax+rax+00h]
0x180098ce5  call    cs:__imp_KeLeaveCriticalRegion
0x180098cec  nop     dword ptr [rax+rax+00h]
0x180098cf1  mov     esi, 100000h
0x180098cf6  lea     rcx, g_PEBootDriverList
0x180098cfd  mov     rax, cs:g_PEBootDriverList
0x180098d04  cmp     rax, rcx
0x180098d07  jnz     short loc_180098D1A
0x180098d09  mov     edx, edi
0x180098d0b  mov     ecx, 0Ah
0x180098d10  call    PEAuthStoreParameter
0x180098d15  jmp     loc_180098F6E
0x180098d1a  xorps   xmm0, xmm0
0x180098d1d  xor     ecx, ecx
0x180098d1f  movups  [rsp+278h+Source1], xmm0
0x180098d27  mov     [rsp+278h+var_98], ecx
0x180098d2e  mov     r13, rax
0x180098d31  mov     [rsp+278h+var_1B8], rax
0x180098d39  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x180098d44  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x180098d4c  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x180098d57  lea     r15, [rax+10h]
0x180098d5b  mov     [rsp+278h+var_1B0], r15
0x180098d63  mov     [rsp+278h+ObjectAttributes.ObjectName], r15
0x180098d6b  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x180098d74  mov     [rsp+278h+EaLength], ebx; EaLength
0x180098d78  mov     [rsp+278h+EaBuffer], rbx; EaBuffer
0x180098d7d  mov     [rsp+278h+CreateOptions], 40h ; '@'; CreateOptions
0x180098d85  mov     [rsp+278h+CreateDisposition], edi; CreateDisposition
0x180098d89  mov     [rsp+278h+ShareAccess], edi; ShareAccess
0x180098d8d  mov     [rsp+278h+FileAttributes], 80h; FileAttributes
0x180098d95  mov     [rsp+278h+AllocationSize], rbx; AllocationSize
0x180098d9a  lea     r9, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x180098da2  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x180098daa  mov     edx, 80000000h; DesiredAccess
0x180098daf  lea     rcx, [rsp+278h+FileHandle]; FileHandle
0x180098db7  call    cs:__imp_ZwCreateFile
0x180098dbe  nop     dword ptr [rax+rax+00h]
0x180098dc3  test    eax, eax
0x180098dc5  js      loc_180098F58
0x180098dcb  mov     [rsp+278h+ObjectAttributes.Length], 30h ; '0'
0x180098dd6  mov     [rsp+278h+ObjectAttributes.RootDirectory], rbx
0x180098dde  mov     [rsp+278h+ObjectAttributes.Attributes], 240h
0x180098de9  mov     [rsp+278h+ObjectAttributes.ObjectName], rbx
0x180098df1  xorps   xmm0, xmm0
0x180098df4  movdqu  xmmword ptr [rsp+278h+ObjectAttributes.SecurityDescriptor], xmm0
0x180098dfd  mov     rax, [rsp+278h+FileHandle]
0x180098e05  mov     qword ptr [rsp+278h+ShareAccess], rax; FileHandle
0x180098e0a  mov     [rsp+278h+FileAttributes], 8000000h; AllocationAttributes
0x180098e12  mov     dword ptr [rsp+278h+AllocationSize], 2; SectionPageProtection
0x180098e1a  xor     r9d, r9d; MaximumSize
0x180098e1d  lea     r8, [rsp+278h+ObjectAttributes]; ObjectAttributes
0x180098e25  lea     edx, [r9+5]; DesiredAccess
0x180098e29  lea     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x180098e31  call    cs:__imp_ZwCreateSection
0x180098e38  nop     dword ptr [rax+rax+00h]
0x180098e3d  test    eax, eax
0x180098e3f  js      loc_180098F58
0x180098e45  mov     dword ptr [rsp+278h+EaBuffer], 2; Win32Protect
0x180098e4d  mov     [rsp+278h+CreateOptions], ebx; AllocationType
0x180098e51  mov     [rsp+278h+CreateDisposition], edi; InheritDisposition
0x180098e55  lea     rax, [rsp+278h+ViewSize]
0x180098e5d  mov     qword ptr [rsp+278h+ShareAccess], rax; ViewSize
0x180098e62  mov     qword ptr [rsp+278h+FileAttributes], rbx; SectionOffset
0x180098e67  mov     [rsp+278h+AllocationSize], rbx; CommitSize
0x180098e6c  xor     r9d, r9d; ZeroBits
0x180098e6f  lea     r8, [rsp+278h+BaseAddress]; BaseAddress
0x180098e77  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180098e7b  mov     rcx, [rsp+278h+SectionHandle]; SectionHandle
0x180098e83  call    cs:__imp_ZwMapViewOfSection
0x180098e8a  nop     dword ptr [rax+rax+00h]
0x180098e8f  test    eax, eax
0x180098e91  js      loc_180098F58
0x180098e97  mov     dword ptr [rsp+278h+AllocationSize], 5; FileInformationClass
0x180098e9f  mov     r9d, 18h; Length
0x180098ea5  lea     r8, [rsp+278h+FileInformation]; FileInformation
0x180098ead  lea     rdx, [rsp+278h+IoStatusBlock]; IoStatusBlock
0x180098eb5  mov     rcx, [rsp+278h+FileHandle]; FileHandle
0x180098ebd  call    cs:__imp_ZwQueryInformationFile
0x180098ec4  nop     dword ptr [rax+rax+00h]
0x180098ec9  test    eax, eax
0x180098ecb  js      loc_180098F58
0x180098ed1  mov     [rsp+278h+var_220], rbx
0x180098ed6  mov     qword ptr [rsp+278h+EaLength], rbx
0x180098edb  mov     qword ptr [rsp+278h+CreateOptions], rbx
0x180098ee0  mov     qword ptr [rsp+278h+CreateDisposition], rbx
0x180098ee5  mov     qword ptr [rsp+278h+ShareAccess], rbx
0x180098eea  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x180098eef  lea     rax, [rsp+278h+Source1]
0x180098ef7  mov     [rsp+278h+AllocationSize], rax
0x180098efc  mov     r9d, dword ptr [rsp+278h+ViewSize]
0x180098f04  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x180098f0c  mov     rdx, [rsp+278h+BaseAddress]
0x180098f14  mov     ecx, 8004h
0x180098f19  call    HashKComputeFirstPageHash
0x180098f1e  mov     [rsp+278h+var_1E8], eax
0x180098f25  jmp     short loc_180098F50
0x180098f27  mov     [rsp+278h+var_1E8], eax
0x180098f2e  xor     ebx, ebx
0x180098f30  lea     edi, [rbx+1]
0x180098f33  mov     esi, 100000h
0x180098f38  mov     r13, [rsp+278h+var_1B8]
0x180098f40  mov     r14d, [rsp+278h+var_1F0]
0x180098f48  mov     r15, [rsp+278h+var_1B0]
0x180098f50  test    eax, eax
0x180098f52  jns     loc_180099041
0x180098f58  xor     edx, edx
0x180098f5a  mov     ecx, edi
0x180098f5c  call    PEAuthStoreParameter
0x180098f61  or      [rsp+278h+var_1F8], esi
0x180098f68  mov     cs:g_PEAuthStateVariables, ebx
0x180098f6e  mov     rdx, [rsp+278h+BaseAddress]; BaseAddress
0x180098f76  test    rdx, rdx
0x180098f79  jz      short loc_180098F8B
0x180098f7b  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180098f7f  call    cs:__imp_ZwUnmapViewOfSection
0x180098f86  nop     dword ptr [rax+rax+00h]
0x180098f8b  mov     rcx, [rsp+278h+FileHandle]; Handle
0x180098f93  test    rcx, rcx
0x180098f96  jz      short loc_180098FA4
0x180098f98  call    cs:__imp_ZwClose
0x180098f9f  nop     dword ptr [rax+rax+00h]
0x180098fa4  mov     rcx, [rsp+278h+SectionHandle]; Handle
0x180098fac  test    rcx, rcx
0x180098faf  jz      short loc_180098FBD
0x180098fb1  call    cs:__imp_ZwClose
0x180098fb8  nop     dword ptr [rax+rax+00h]
0x180098fbd  cmp     [rsp+278h+var_1F8], 0
0x180098fc5  jz      short loc_18009901B
0x180098fc7  mov     r9d, [rsp+278h+var_1F8]
0x180098fcf  or      r9d, 2
0x180098fd3  mov     [rsp+278h+var_1F8], r9d
0x180098fdb  mov     [rsp+278h+FileAttributes], ebx; int
0x180098fdf  mov     dword ptr [rsp+278h+AllocationSize], edi; int
0x180098fe3  lea     r8, [r13+10h]
0x180098fe7  lea     rdx, g_rgEmptyHash
0x180098fee  lea     rcx, [rsp+278h+Source1]; Source2
0x180098ff6  call    I_PEUpdateHashCache
0x180098ffb  mov     ecx, cs:g_PEAuthConfigOptions
0x180099001  test    dil, cl
0x180099004  jz      short loc_18009901B
0x180099006  mov     r9d, edi
0x180099009  lea     r8, [r13+10h]
0x18009900d  xor     edx, edx
0x18009900f  mov     ecx, [rsp+278h+var_1F8]
0x180099016  call    I_PEWriteComponentLoadExEvents
0x18009901b  mov     eax, edi
0x18009901d  mov     rcx, [rsp+278h+var_48]
0x180099025  xor     rcx, rsp; StackCookie
0x180099028  call    __security_check_cookie
0x18009902d  add     rsp, 240h
0x180099034  pop     r15
0x180099036  pop     r14
0x180099038  pop     r13
0x18009903a  pop     r12
0x18009903c  pop     rdi
0x18009903d  pop     rsi
0x18009903e  pop     rbx
0x18009903f  retn
0x180099041  mov     [rsp+278h+var_148], r15
0x180099049  mov     eax, cs:g_PEAuthConfigOptions
0x18009904f  test    dil, al
0x180099052  jz      short loc_1800990C7
0x180099054  lea     rax, [rsp+278h+var_1C8]
0x18009905c  mov     [rsp+278h+UserData.Ptr], rax
0x180099064  mov     qword ptr [rsp+278h+UserData.Size], 4
0x180099070  movzx   ecx, word ptr [r15]
0x180099074  mov     rax, [r13+18h]
0x180099078  mov     [rsp+278h+var_D8], rax
0x180099080  mov     [rsp+278h+var_D0], ecx
0x180099087  mov     [rsp+278h+var_CC], ebx
0x18009908e  add     r14d, 2
0x180099092  mov     [rsp+278h+var_1F0], r14d
0x18009909a  lea     rax, [rsp+278h+UserData]
0x1800990a2  mov     [rsp+278h+AllocationSize], rax; UserData
0x1800990a7  mov     r9d, r14d; UserDataCount
0x1800990aa  xor     r8d, r8d; ActivityId
0x1800990ad  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x1800990b4  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800990bb  call    cs:__imp_EtwWrite
0x1800990c2  nop     dword ptr [rax+rax+00h]
0x1800990c7  mov     eax, [r13+20h]
0x1800990cb  cmp     eax, 0C0000428h
0x1800990d0  jnz     loc_18009932E
0x1800990d6  mov     r15d, cs:g_CatalogFileHashAlgorithm
0x1800990dd  mov     [rsp+278h+var_1EC], r15d
0x1800990e5  mov     r12d, cs:g_CatalogFileHashLength
0x1800990ec  mov     [rsp+278h+var_1F4], r12d
0x1800990f4  mov     r8d, dword ptr [rsp+278h+FileInformation+8]
0x1800990fc  mov     qword ptr [rsp+278h+FileAttributes], rbx
0x180099101  lea     rax, [rsp+278h+var_88]
0x180099109  mov     [rsp+278h+AllocationSize], rax
0x18009910e  xor     r9d, r9d
0x180099111  mov     rdx, [rsp+278h+BaseAddress]
0x180099119  mov     ecx, r15d
0x18009911c  call    HashKComputeImageHash
0x180099121  mov     [rsp+278h+var_1E8], eax
0x180099128  jmp     short loc_180099153
0x18009912a  mov     [rsp+278h+var_1E8], eax
0x180099131  xor     ebx, ebx
0x180099133  lea     edi, [rbx+1]
0x180099136  mov     esi, 100000h
0x18009913b  mov     r13, [rsp+278h+var_1B8]
0x180099143  mov     r15d, [rsp+278h+var_1EC]
0x18009914b  mov     r12d, [rsp+278h+var_1F4]
0x180099153  test    eax, eax
0x180099155  js      loc_180099332
0x18009915b  lea     rdx, [rsp+278h+ApcState]; ApcState
0x180099163  mov     rcx, cs:__imp_PsInitialSystemProcess
0x18009916a  mov     rcx, [rcx]; PROCESS
0x18009916d  call    cs:__imp_KeStackAttachProcess
0x180099174  nop     dword ptr [rax+rax+00h]
0x180099179  mov     [rsp+278h+var_200], rbx; __int64
0x18009917e  mov     [rsp+278h+var_210], rbx; __int64
0x180099183  mov     [rsp+278h+var_218], rbx; __int64
0x180099188  mov     [rsp+278h+var_220], rbx; __int64
0x18009918d  lea     rax, [rsp+278h+var_178]
0x180099195  mov     qword ptr [rsp+278h+EaLength], rax; __int64
0x18009919a  mov     [rsp+278h+EaBuffer], rbx; __int64
0x18009919f  mov     qword ptr [rsp+278h+CreateOptions], rbx; SourceString
0x1800991a4  mov     [rsp+278h+CreateDisposition], 47Fh; int
0x1800991ac  mov     [rsp+278h+ShareAccess], edi; int
0x1800991b0  mov     [rsp+278h+FileAttributes], ebx; int
0x1800991b4  mov     dword ptr [rsp+278h+AllocationSize], ebx; int
0x1800991b8  mov     r9d, r15d; int
0x1800991bb  mov     r8d, r12d; int
0x1800991be  lea     rdx, [rsp+278h+var_88]; int
0x1800991c6  xor     ecx, ecx; int
0x1800991c8  call    CiVerifyHashInCatalogOrUnsignedCache
0x1800991cd  mov     r14d, eax
0x1800991d0  test    eax, eax
0x1800991d2  jns     loc_180099260
0x1800991d8  cmp     dword ptr [rsp+278h+var_178], ebx
0x1800991df  jz      short loc_180099209
0x1800991e1  mov     rcx, qword ptr [rsp+278h+var_168]
0x1800991e9  call    I_MincryptFreeChainInfo
0x1800991ee  xorps   xmm0, xmm0
0x1800991f1  movups  xmmword ptr [rsp+278h+var_178], xmm0
0x1800991f9  movups  [rsp+278h+var_168], xmm0
0x180099201  movups  [rsp+278h+var_158], xmm0
0x180099209  mov     [rsp+278h+var_200], rbx; __int64
  ... truncated ...
```
