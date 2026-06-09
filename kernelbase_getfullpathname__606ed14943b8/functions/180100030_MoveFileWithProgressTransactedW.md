# MoveFileWithProgressTransactedW

- ea: `0x180100030`
- end: `0x180100edf`
- name: `MoveFileWithProgressTransactedW`
- size: `3759`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, LPCWSTR lpFileName@<rdx>, int, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fff90`
- `0x1800fffe0`

## callees

- `0x18004b9d0`
- `0x180053c30`
- `0x180075848`
- `0x1800d3eb0`
- `0x1800d6e60`
- `0x1800f2f00`
- `0x1800f9650`
- `0x180100030`
- `0x180116258`
- `0x180119704`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18010042b`
- `ntdll!RtlInitUnicodeString` at `0x18010042b`
- `ntdll!NtQueryInformationFile` at `0x1801002ec`
- `ntdll!NtQueryInformationFile` at `0x180100be3`
- `ntdll!NtQueryInformationFile` at `0x1801002ec`
- `ntdll!NtQueryInformationFile` at `0x180100be3`
- `ntdll!NtOpenFile` at `0x180100232`
- `ntdll!NtOpenFile` at `0x1801002ab`
- `ntdll!NtOpenFile` at `0x1801003b2`
- `ntdll!NtOpenFile` at `0x180100401`
- `ntdll!NtOpenFile` at `0x18010054d`
- `ntdll!NtOpenFile` at `0x180100699`
- `ntdll!NtOpenFile` at `0x180100232`
- `ntdll!NtOpenFile` at `0x1801002ab`
- `ntdll!NtOpenFile` at `0x1801003b2`
- `ntdll!NtOpenFile` at `0x180100401`
- `ntdll!NtOpenFile` at `0x18010054d`
- `ntdll!NtOpenFile` at `0x180100699`
- `ntdll!NtSetInformationFile` at `0x180100b69`
- `ntdll!NtSetInformationFile` at `0x180100b69`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180100174`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18010044a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180100174`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18010044a`
- `ntdll!RtlSetCurrentTransaction` at `0x180100c9a`
- `ntdll!RtlSetCurrentTransaction` at `0x180100d2d`
- `ntdll!RtlSetCurrentTransaction` at `0x180198a0c`
- `ntdll!RtlSetCurrentTransaction` at `0x180100c9a`
- `ntdll!RtlSetCurrentTransaction` at `0x180100d2d`
- `ntdll!RtlSetCurrentTransaction` at `0x180198a0c`
- `ntdll!RtlGetCurrentTransaction` at `0x180100c37`
- `ntdll!RtlGetCurrentTransaction` at `0x180100c37`
- `ntdll!RtlIsDosDeviceName_U` at `0x180100144`
- `ntdll!RtlIsDosDeviceName_U` at `0x180100144`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180100a02`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180100a02`
- `ntdll!NtClose` at `0x180100370`
- `ntdll!NtClose` at `0x180100c0f`
- `ntdll!NtClose` at `0x180100e2f`
- `ntdll!NtClose` at `0x180100e49`
- `ntdll!NtClose` at `0x180198a3c`
- `ntdll!NtClose` at `0x180198a56`
- `ntdll!NtClose` at `0x180100370`
- `ntdll!NtClose` at `0x180100c0f`
- `ntdll!NtClose` at `0x180100e2f`
- `ntdll!NtClose` at `0x180100e49`
- `ntdll!NtClose` at `0x180198a3c`
- `ntdll!NtClose` at `0x180198a56`
- `ntdll!RtlFreeHeap` at `0x1801006cc`
- `ntdll!RtlFreeHeap` at `0x18010088d`
- `ntdll!RtlFreeHeap` at `0x1801009a5`
- `ntdll!RtlFreeHeap` at `0x1801009cd`
- `ntdll!RtlFreeHeap` at `0x180100b89`
- `ntdll!RtlFreeHeap` at `0x180100e76`
- `ntdll!RtlFreeHeap` at `0x180100ea3`
- `ntdll!RtlFreeHeap` at `0x180198a83`
- `ntdll!RtlFreeHeap` at `0x180198ab0`
- `ntdll!RtlFreeHeap` at `0x1801006cc`
- `ntdll!RtlFreeHeap` at `0x18010088d`
- `ntdll!RtlFreeHeap` at `0x1801009a5`
- `ntdll!RtlFreeHeap` at `0x1801009cd`
- `ntdll!RtlFreeHeap` at `0x180100b89`
- `ntdll!RtlFreeHeap` at `0x180100e76`
- `ntdll!RtlFreeHeap` at `0x180100ea3`
- `ntdll!RtlFreeHeap` at `0x180198a83`
- `ntdll!RtlFreeHeap` at `0x180198ab0`
- `ntdll!RtlAllocateHeap` at `0x1801005a1`
- `ntdll!RtlAllocateHeap` at `0x1801007d9`
- `ntdll!RtlAllocateHeap` at `0x180100ae4`
- `ntdll!RtlAllocateHeap` at `0x1801005a1`
- `ntdll!RtlAllocateHeap` at `0x1801007d9`
- `ntdll!RtlAllocateHeap` at `0x180100ae4`

## pseudocode

```c
__int64 __fastcall MoveFileWithProgressTransactedW(
        PCWSTR DosPathName,
        LPCWSTR lpFileName,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  const WCHAR *v6; // r13
  unsigned __int8 v8; // si
  __int64 v9; // rcx
  char v10; // r12
  NTSTATUS v11; // eax
  int v12; // edx
  NTSTATUS v13; // ebx
  NTSTATUS v14; // eax
  int v15; // edx
  struct _UNICODE_STRING v16; // xmm6
  PVOID Heap; // rax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r13
  unsigned int v23; // r15d
  unsigned __int16 v24; // r14
  _WORD *v25; // rax
  _WORD *v26; // r12
  __int64 v27; // rdx
  __int64 v28; // r14
  char *v29; // rax
  _QWORD *v30; // rdi
  __int64 CurrentTransaction; // rbx
  const WCHAR *v32; // rdi
  int v33; // ebx
  unsigned __int8 v35; // [rsp+80h] [rbp-1A8h]
  HANDLE FileHandle; // [rsp+88h] [rbp-1A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-198h] BYREF
  int v38; // [rsp+A0h] [rbp-188h]
  HANDLE v39; // [rsp+A8h] [rbp-180h] BYREF
  HANDLE hObject[2]; // [rsp+B0h] [rbp-178h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-168h] BYREF
  PVOID P[2]; // [rsp+D0h] [rbp-158h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp-148h] BYREF
  PVOID v44[2]; // [rsp+F0h] [rbp-138h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-128h] BYREF
  PVOID v46[2]; // [rsp+110h] [rbp-118h] BYREF
  int v47; // [rsp+120h] [rbp-108h]
  __int64 FileInformation; // [rsp+128h] [rbp-100h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+130h] [rbp-F8h] BYREF
  LPCWSTR v50; // [rsp+160h] [rbp-C8h]
  PCWSTR Path; // [rsp+168h] [rbp-C0h]
  __int64 v52[2]; // [rsp+170h] [rbp-B8h] BYREF
  __int128 v53; // [rsp+180h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+190h] [rbp-98h]
  __int64 v55; // [rsp+198h] [rbp-90h]
  __int64 v56; // [rsp+1A0h] [rbp-88h]
  __int64 v57; // [rsp+1A8h] [rbp-80h]
  _BYTE v58[32]; // [rsp+1B0h] [rbp-78h] BYREF
  __int64 v59; // [rsp+1D0h] [rbp-58h]

  v56 = a4;
  v55 = a3;
  v6 = lpFileName;
  v50 = lpFileName;
  Path = DosPathName;
  v52[0] = a6;
  memset(&ObjectAttributes, 0, 44);
  FileHandle = (HANDLE)-1LL;
  *(_QWORD *)&NtPathName.Length = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = 0;
  v53 = 0;
  LODWORD(v54) = 0;
  memset(v58, 0, sizeof(v58));
  v59 = 0;
  Handle = (HANDLE)-1LL;
  LODWORD(hObject[0]) = 0;
  LODWORD(v39) = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v44 = 0;
  DestinationString.Buffer = 0;
  NtPathName.Buffer = 0;
  if ( lpFileName && RtlIsDosDeviceName_U(lpFileName) )
  {
    v9 = 3221225525LL;
LABEL_4:
    BaseSetLastNTError(v9);
    goto LABEL_124;
  }
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
LABEL_6:
    v9 = 3221225530LL;
    goto LABEL_4;
  }
  v10 = a5;
  if ( (a5 & 4) != 0 && (a5 & 0x10) != 0 )
  {
    v9 = 3221225485LL;
    goto LABEL_4;
  }
  v35 = a5 & 1;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, ((a5 & 8 | 0x10080u) >> 2) | 0x200000);
  if ( v11 < 0 )
  {
    if ( (a5 & 4) != 0 && (unsigned int)(v11 + 1073741772) <= 0xF )
    {
      v12 = 32833;
      if ( _bittest(&v12, v11 + 1073741772) )
      {
        FileHandle = (HANDLE)-1LL;
        v13 = -1073741811;
        goto LABEL_34;
      }
    }
    v13 = -1073741811;
    if ( v11 == -1073741811 )
      v11 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 3u, (a5 & 8 | 0x10080u) >> 2);
    goto LABEL_17;
  }
  v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v14 >= 0 || v14 == -1073741822 )
  {
    v13 = -1073741811;
  }
  else
  {
    v13 = -1073741811;
    if ( v14 != -1073741811 )
    {
      BaseSetLastNTError((unsigned int)v14);
      goto LABEL_124;
    }
  }
  if ( v14 >= 0 && (FileInformation & 0x400) != 0 )
  {
    if ( (unsigned int)(HIDWORD(FileInformation) + 1610612733) > 0x1A
      || (v15 = 67109377, !_bittest(&v15, HIDWORD(FileInformation) + 1610612733)) )
    {
      if ( (unsigned int)(HIDWORD(FileInformation) + 2147483613) > 3 )
      {
        NtClose(FileHandle);
        FileHandle = (HANDLE)-1LL;
        v11 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 3u, (a5 & 8 | 0x10080u) >> 2);
        if ( v11 < 0 )
        {
          if ( ((v11 + 1073741194) & 0xFFFFFFFC) == 0 && v11 != -1073741193 )
            v11 = NtOpenFile(
                    &FileHandle,
                    0x110000u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    3u,
                    ((a5 & 8 | 0x10080u) >> 2) | 0x200000);
LABEL_17:
          if ( v11 < 0 )
          {
            v9 = (unsigned int)v11;
            goto LABEL_4;
          }
        }
      }
    }
  }
LABEL_34:
  if ( (a5 & 4) == 0 || v6 )
  {
    if ( !RtlDosPathNameToNtPathName_U(v6, &DestinationString, 0, 0) )
      goto LABEL_6;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  if ( (a5 & 4) != 0 )
  {
    if ( (NtCurrentPeb()->AppCompatFlags.QuadPart & 0x800000000LL) != 0 )
    {
      *(struct _UNICODE_STRING *)v46 = NtPathName;
      NtPathName.Buffer = 0;
      AssembleRegistryString(v46, 48, 0, &NtPathName);
      if ( !DestinationString.Length )
        goto LABEL_84;
      v16 = DestinationString;
      *(struct _UNICODE_STRING *)v44 = DestinationString;
      DestinationString.Buffer = 0;
      AssembleRegistryString(v44, 48, v35, &DestinationString);
      goto LABEL_83;
    }
    if ( FileHandle == (HANDLE)-1LL
      && NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u) < 0 )
    {
      FileHandle = (HANDLE)-1LL;
    }
    if ( v6 )
    {
      *(_OWORD *)P = 0;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.MaximumLength + 2LL);
      P[1] = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, DestinationString.Buffer, DestinationString.Length);
        v18 = DestinationString.Length >> 1;
        v38 = v18;
        v19 = v18;
        LODWORD(v20) = v18;
        while ( v19 )
        {
          v20 = (unsigned int)(v20 - 1);
          if ( *((_WORD *)P[1] + v20) == 92 )
            break;
          LOWORD(v18) = v20;
          v38 = v20;
          v19 = v20;
        }
        *((_WORD *)P[1] + v19) = 0;
        LOWORD(P[0]) = 2 * v18;
        WORD1(P[0]) = 2 * v18 + 2;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u) < 0 )
          Handle = (HANDLE)-1LL;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
        *(_OWORD *)P = 0;
      }
    }
    if ( FileHandle != (HANDLE)-1LL )
      LODWORD(hObject[0]) = RetrieveFinalPathName(FileHandle, (PUNICODE_STRING)v46);
    if ( Handle != (HANDLE)-1LL )
    {
      LODWORD(v39) = RetrieveFinalPathName(Handle, (PUNICODE_STRING)P);
      v47 = (int)v39;
      if ( (_DWORD)v39 && DestinationString.Length >= 2u )
      {
        v21 = (DestinationString.Length >> 1) - 1;
        v38 = (DestinationString.Length >> 1) - 1;
        while ( DestinationString.Buffer[v21] != 92 && (_DWORD)v21 )
        {
          v21 = (unsigned int)(v21 - 1);
          v38 = v21;
        }
        if ( (unsigned int)v21 <= 6 )
        {
          LODWORD(v21) = v21 + 1;
          v38 = v21;
        }
        v22 = (unsigned int)v21;
        v23 = (DestinationString.Length >> 1) - v21;
        v24 = LOWORD(P[0]) + 2 * ((DestinationString.Length >> 1) - v21);
        LOWORD(v44[0]) = v24;
        WORD1(v44[0]) = v24 + 2;
        v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(v24 + 2));
        v26 = v25;
        v44[1] = v25;
        if ( v25 )
        {
          memcpy_0(v25, P[1], LOWORD(P[0]));
          memcpy_0(&v26[(unsigned __int64)LOWORD(P[0]) >> 1], &DestinationString.Buffer[v22], 2LL * v23);
          v26[(unsigned __int64)v24 >> 1] = 0;
        }
        else
        {
          LODWORD(v39) = 0;
          v47 = 0;
        }
        v6 = v50;
        v10 = a5;
      }
      if ( P[1] )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    }
    if ( FileHandle == (HANDLE)-1LL || !LODWORD(hObject[0]) )
    {
      if ( !NtPathName.Length )
      {
LABEL_78:
        if ( Handle == (HANDLE)-1LL || !(_DWORD)v39 )
        {
          if ( DestinationString.Length )
          {
            v16 = DestinationString;
            *(struct _UNICODE_STRING *)v44 = DestinationString;
            DestinationString.Buffer = 0;
            AssembleRegistryString(v44, 50, v35, &DestinationString);
LABEL_83:
            v44[1] = (PVOID)_mm_srli_si128((__m128i)v16, 8).m128i_u64[0];
          }
        }
        else
        {
          AssembleRegistryString(v44, 49, v35, &DestinationString);
        }
LABEL_84:
        if ( v46[1] )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v46[1]);
        if ( v44[1] )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v44[1]);
        if ( NtPathName.Buffer && (!v6 || DestinationString.Buffer) )
        {
          if ( RtlDetermineDosPathNameType_U(Path) == RtlPathTypeUncAbsolute || (v10 & 2) != 0 )
            goto LABEL_98;
          v28 = v52[0];
          v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 2, 0, v52[0]);
          if ( v13 == -1073741772 )
          {
            v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 1, 1, v28);
            if ( v13 == -1073741670 )
              v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 2, 1, v28);
          }
        }
        else
        {
          v13 = -1073741670;
        }
        if ( v13 < 0 )
        {
LABEL_98:
          v9 = (unsigned int)v13;
          goto LABEL_4;
        }
        goto LABEL_99;
      }
      *(struct _UNICODE_STRING *)v46 = NtPathName;
      NtPathName.Buffer = 0;
      v27 = 50;
    }
    else
    {
      v27 = 49;
    }
    AssembleRegistryString(v46, v27, 0, &NtPathName);
    goto LABEL_78;
  }
  v29 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 24LL);
  v30 = v29;
  if ( !v29 )
  {
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  memcpy_0(v29 + 20, DestinationString.Buffer, DestinationString.Length);
  *(_BYTE *)v30 = v35;
  v30[1] = 0;
  *((_DWORD *)v30 + 4) = DestinationString.Length;
  v13 = NtSetInformationFile(
          FileHandle,
          &IoStatusBlock,
          v30,
          DestinationString.Length + 24,
          (FILE_INFORMATION_CLASS)((a5 & 0x10 | 0xA0u) >> 4));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
  if ( v13 >= 0 )
  {
LABEL_99:
    v8 = 1;
    goto LABEL_124;
  }
  if ( v13 != -1073741612 && v13 != -1072103368 || (a5 & 2) == 0 )
    goto LABEL_98;
  if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, v58, 0x28u, FileBasicInformation) >= 0 && (v59 & 0x10) != 0 )
  {
    v9 = 3221225658LL;
    goto LABEL_4;
  }
  NtClose(FileHandle);
  FileHandle = (HANDLE)-1LL;
  v39 = (HANDLE)-1LL;
  hObject[0] = (HANDLE)-1LL;
  CurrentTransaction = RtlGetCurrentTransaction();
  v57 = CurrentTransaction;
  v52[0] = (__int64)BasepMoveFileCopyProgress;
  v52[1] = 0;
  LODWORD(v53) = a5;
  *((_QWORD *)&v53 + 1) = v55;
  v54 = v56;
  RtlSetCurrentTransaction(0);
  v32 = Path;
  v8 = BasepCopyFileExW(
         (_DWORD)Path,
         (_DWORD)v6,
         (unsigned int)v52,
         (unsigned int)&v53,
         0,
         0,
         0,
         !(a5 & 1) | 0x804u,
         0,
         (__int64)&v39,
         (__int64)hObject,
         CurrentTransaction,
         0,
         0,
         0,
         0);
  RtlSetCurrentTransaction(CurrentTransaction);
  if ( v8 )
  {
    if ( v39 != (HANDLE)-1LL && hObject[0] != (HANDLE)-1LL )
    {
      v33 = BasepNotifyTrackingService(&v39, &ObjectAttributes);
      if ( v33 < 0 && (a5 & 0x20) != 0 )
      {
        if ( hObject[0] != (HANDLE)-1LL )
          CloseHandle(hObject[0]);
        hObject[0] = (HANDLE)-1LL;
        DeleteFileW(v6);
        v8 = 0;
        BaseSetLastNTError((unsigned int)v33);
      }
    }
  }
  if ( v39 != (HANDLE)-1LL )
  {
    CloseHandle(v39);
    v39 = (HANDLE)-1LL;
  }
  if ( hObject[0] != (HANDLE)-1LL )
  {
    CloseHandle(hObject[0]);
    hObject[0] = (HANDLE)-1LL;
  }
  if ( v8 && !DeleteFileW(v32) )
  {
    SetFileAttributesW(v32, 0x80u);
    DeleteFileW(v32);
  }
LABEL_124:
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  return v8;
}

```

## disassembly

```asm
0x180100030  mov     r11, rsp
0x180100033  push    rbx
0x180100034  push    rsi
0x180100035  push    rdi
0x180100036  push    r12
0x180100038  push    r13
0x18010003a  push    r14
0x18010003c  push    r15
0x18010003e  sub     rsp, 1F0h
0x180100045  movaps  xmmword ptr [r11-48h], xmm6
0x18010004a  mov     rax, cs:__security_cookie
0x180100051  xor     rax, rsp
0x180100054  mov     [rsp+228h+var_50], rax
0x18010005c  mov     [rsp+228h+var_88], r9
0x180100064  mov     [rsp+228h+var_90], r8
0x18010006c  mov     r13, rdx
0x18010006f  mov     [rsp+228h+var_C8], rdx
0x180100077  mov     rbx, rcx
0x18010007a  mov     [rsp+228h+Path], rcx
0x180100082  mov     rax, [rsp+228h+arg_28]
0x18010008a  mov     qword ptr [rsp+228h+var_B8], rax
0x180100092  xor     eax, eax
0x180100094  xorps   xmm0, xmm0
0x180100097  movups  xmmword ptr [rsp+228h+ObjectAttributes.Length], xmm0
0x18010009f  movups  xmmword ptr [rsp+228h+ObjectAttributes.ObjectName], xmm0
0x1801000a7  movups  xmmword ptr [rsp+228h+ObjectAttributes+1Ch], xmm0
0x1801000af  mov     qword ptr [r11-1A0h], 0FFFFFFFFFFFFFFFFh
0x1801000ba  xor     r15d, r15d
0x1801000bd  mov     [r11-168h], r15
0x1801000c4  mov     [r11-198h], r15
0x1801000cb  movups  xmmword ptr [rsp+228h+IoStatusBlock], xmm0
0x1801000d3  mov     [r11-100h], r15
0x1801000da  mov     sil, r15b
0x1801000dd  movups  [rsp+228h+var_A8], xmm0
0x1801000e5  mov     dword ptr [rsp+228h+var_98], eax
0x1801000ec  xorps   xmm1, xmm1
0x1801000ef  movups  xmmword ptr [r11-78h], xmm1
0x1801000f4  movups  xmmword ptr [r11-68h], xmm1
0x1801000f9  mov     [r11-58h], rax
0x1801000fd  mov     qword ptr [r11-148h], 0FFFFFFFFFFFFFFFFh
0x180100108  mov     [r11-178h], r15d
0x18010010f  mov     [r11-180h], r15d
0x180100116  movups  xmmword ptr [rsp+228h+P], xmm0
0x18010011e  movups  xmmword ptr [rsp+228h+var_118], xmm1
0x180100126  movups  xmmword ptr [rsp+228h+var_138], xmm0
0x18010012e  mov     [r11-190h], r15
0x180100135  mov     [r11-160h], r15
0x18010013c  test    rdx, rdx
0x18010013f  jz      short loc_180100163
0x180100141  mov     rcx, rdx; Name
0x180100144  call    cs:__imp_RtlIsDosDeviceName_U
0x18010014b  nop     dword ptr [rax+rax+00h]
0x180100150  test    eax, eax
0x180100152  jz      short loc_180100163
0x180100154  mov     ecx, 0C0000035h
0x180100159  call    BaseSetLastNTError
0x18010015e  jmp     loc_180100E21
0x180100163  xor     r9d, r9d; DirectoryInfo
0x180100166  xor     r8d, r8d; NtFileNamePart
0x180100169  lea     rdx, [rsp+228h+NtPathName]; NtPathName
0x180100171  mov     rcx, rbx; DosPathName
0x180100174  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18010017b  nop     dword ptr [rax+rax+00h]
0x180100180  test    al, al
0x180100182  jnz     short loc_18010018B
0x180100184  mov     ecx, 0C000003Ah
0x180100189  jmp     short loc_180100159
0x18010018b  mov     r12d, [rsp+228h+arg_20]
0x180100193  mov     edi, r12d
0x180100196  and     edi, 4
0x180100199  jz      short loc_1801001A8
0x18010019b  test    r12b, 10h
0x18010019f  jz      short loc_1801001A8
0x1801001a1  mov     ecx, 0C000000Dh
0x1801001a6  jmp     short loc_180100159
0x1801001a8  mov     al, r12b
0x1801001ab  and     al, 1
0x1801001ad  mov     [rsp+228h+var_1A8], al
0x1801001b4  mov     [rsp+228h+ObjectAttributes.Length], 30h ; '0'
0x1801001bf  mov     [rsp+228h+ObjectAttributes.RootDirectory], r15
0x1801001c7  mov     [rsp+228h+ObjectAttributes.Attributes], 40h ; '@'
0x1801001d2  lea     rax, [rsp+228h+NtPathName]
0x1801001da  mov     [rsp+228h+ObjectAttributes.ObjectName], rax
0x1801001e2  xorps   xmm0, xmm0
0x1801001e5  movdqu  xmmword ptr [rsp+228h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801001ee  mov     r14d, r12d
0x1801001f1  and     r14d, 8
0x1801001f5  or      r14d, 10080h
0x1801001fc  shr     r14d, 2
0x180100200  mov     r15d, r14d
0x180100203  bts     r15d, 15h
0x180100208  mov     [rsp+228h+OpenOptions], r15d; OpenOptions
0x18010020d  mov     [rsp+228h+ShareAccess], 7; ShareAccess
0x180100215  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x18010021d  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x180100225  mov     edx, 110080h; DesiredAccess
0x18010022a  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x180100232  call    cs:__imp_NtOpenFile
0x180100239  nop     dword ptr [rax+rax+00h]
0x18010023e  test    eax, eax
0x180100240  jns     loc_1801002C6
0x180100246  xor     r15d, r15d
0x180100249  test    edi, edi
0x18010024b  jz      short loc_180100278
0x18010024d  lea     ecx, [rax+3FFFFFCCh]
0x180100253  cmp     ecx, 0Fh
0x180100256  ja      short loc_180100278
0x180100258  mov     edx, 8041h
0x18010025d  bt      edx, ecx
0x180100260  jnb     short loc_180100278
0x180100262  mov     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18010026e  mov     ebx, 0C000000Dh
0x180100273  jmp     loc_180100418
0x180100278  mov     ebx, 0C000000Dh
0x18010027d  cmp     eax, ebx
0x18010027f  jnz     short loc_1801002B7
0x180100281  mov     [rsp+228h+OpenOptions], r14d; OpenOptions
0x180100286  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x18010028e  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x180100296  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x18010029e  mov     edx, 110000h; DesiredAccess
0x1801002a3  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1801002ab  call    cs:__imp_NtOpenFile
0x1801002b2  nop     dword ptr [rax+rax+00h]
0x1801002b7  test    eax, eax
0x1801002b9  jns     loc_180100418
0x1801002bf  mov     ecx, eax
0x1801002c1  jmp     loc_180100159
0x1801002c6  mov     [rsp+228h+ShareAccess], 23h ; '#'; FileInformationClass
0x1801002ce  mov     r9d, 8; Length
0x1801002d4  lea     r8, [rsp+228h+FileInformation]; FileInformation
0x1801002dc  lea     rdx, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1801002e4  mov     rcx, [rsp+228h+FileHandle]; FileHandle
0x1801002ec  call    cs:__imp_NtQueryInformationFile
0x1801002f3  nop     dword ptr [rax+rax+00h]
0x1801002f8  test    eax, eax
0x1801002fa  jns     short loc_18010031B
0x1801002fc  cmp     eax, 0C0000002h
0x180100301  jz      short loc_18010031B
0x180100303  mov     ebx, 0C000000Dh
0x180100308  cmp     eax, ebx
0x18010030a  jz      short loc_180100320
0x18010030c  mov     ecx, eax
0x18010030e  call    BaseSetLastNTError
0x180100313  xor     r15d, r15d
0x180100316  jmp     loc_180100E21
0x18010031b  mov     ebx, 0C000000Dh
0x180100320  test    eax, eax
0x180100322  js      loc_180100415
0x180100328  test    [rsp+228h+FileInformation], 400h
0x180100333  jz      loc_180100415
0x180100339  mov     ecx, [rsp+228h+var_FC]
0x180100340  lea     eax, [rcx+5FFFFFFDh]
0x180100346  cmp     eax, 1Ah
0x180100349  ja      short loc_180100359
0x18010034b  mov     edx, 4000201h
0x180100350  bt      edx, eax
0x180100353  jb      loc_180100415
0x180100359  lea     eax, [rcx+7FFFFFDDh]
0x18010035f  cmp     eax, 3
0x180100362  jbe     loc_180100415
0x180100368  mov     rcx, [rsp+228h+FileHandle]; Handle
0x180100370  call    cs:__imp_NtClose
0x180100377  nop     dword ptr [rax+rax+00h]
0x18010037c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180100380  mov     [rsp+228h+FileHandle], rax
0x180100388  mov     [rsp+228h+OpenOptions], r14d; OpenOptions
0x18010038d  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x180100395  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x18010039d  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1801003a5  mov     edx, 110000h; DesiredAccess
0x1801003aa  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1801003b2  call    cs:__imp_NtOpenFile
0x1801003b9  nop     dword ptr [rax+rax+00h]
0x1801003be  test    eax, eax
0x1801003c0  jns     short loc_180100415
0x1801003c2  lea     ecx, [rax+3FFFFD8Ah]
0x1801003c8  test    ecx, 0FFFFFFFCh
0x1801003ce  jnz     short loc_18010040D
0x1801003d0  cmp     eax, 0C0000277h
0x1801003d5  jz      short loc_18010040D
0x1801003d7  mov     [rsp+228h+OpenOptions], r15d; OpenOptions
0x1801003dc  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x1801003e4  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1801003ec  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1801003f4  mov     edx, 110000h; DesiredAccess
0x1801003f9  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x180100401  call    cs:__imp_NtOpenFile
0x180100408  nop     dword ptr [rax+rax+00h]
0x18010040d  xor     r15d, r15d
0x180100410  jmp     loc_1801002B7
0x180100415  xor     r15d, r15d
0x180100418  test    edi, edi
0x18010041a  jz      short loc_180100439
0x18010041c  test    r13, r13
0x18010041f  jnz     short loc_180100439
0x180100421  xor     edx, edx; SourceString
0x180100423  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x18010042b  call    cs:__imp_RtlInitUnicodeString
0x180100432  nop     dword ptr [rax+rax+00h]
0x180100437  jmp     short loc_18010045E
0x180100439  xor     r9d, r9d; DirectoryInfo
0x18010043c  xor     r8d, r8d; NtFileNamePart
0x18010043f  lea     rdx, [rsp+228h+DestinationString]; NtPathName
0x180100447  mov     rcx, r13; DosPathName
0x18010044a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180100451  nop     dword ptr [rax+rax+00h]
0x180100456  test    al, al
0x180100458  jz      loc_180100184
0x18010045e  test    edi, edi
0x180100460  jz      loc_180100AC4
0x180100466  mov     rax, gs:60h
0x18010046f  mov     rcx, 800000000h
0x180100479  test    [rax+2C8h], rcx
0x180100480  jz      loc_180100515
0x180100486  movaps  xmm0, xmmword ptr [rsp+228h+NtPathName.Length]
0x18010048e  movdqa  xmmword ptr [rsp+228h+var_118], xmm0
0x180100497  mov     [rsp+228h+NtPathName.Buffer], r15
0x18010049f  mov     edi, 30h ; '0'
0x1801004a4  mov     edx, edi
0x1801004a6  lea     r9, [rsp+228h+NtPathName]
0x1801004ae  xor     r8d, r8d
0x1801004b1  lea     rcx, [rsp+228h+var_118]
0x1801004b9  call    AssembleRegistryString
0x1801004be  cmp     [rsp+228h+DestinationString.Length], r15w
0x1801004c7  jz      short loc_18010050B
0x1801004c9  movaps  xmm6, xmmword ptr [rsp+228h+DestinationString.Length]
0x1801004d1  movaps  xmmword ptr [rsp+228h+var_138], xmm6
0x1801004d9  mov     [rsp+228h+DestinationString.Buffer], r15
0x1801004e1  movzx   r8d, [rsp+228h+var_1A8]
0x1801004ea  mov     edx, edi
0x1801004ec  lea     r9, [rsp+228h+DestinationString]
0x1801004f4  lea     rcx, [rsp+228h+var_138]
0x1801004fc  call    AssembleRegistryString
0x180100501  mov     edi, 2
0x180100506  jmp     loc_180100976
0x18010050b  mov     edi, 2
0x180100510  jmp     loc_180100984
0x180100515  cmp     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18010051e  jnz     short loc_180100569
0x180100520  mov     [rsp+228h+OpenOptions], 4020h; OpenOptions
0x180100528  mov     [rsp+228h+ShareAccess], 7; ShareAccess
0x180100530  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x180100538  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x180100540  mov     edx, 100080h; DesiredAccess
0x180100545  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x18010054d  call    cs:__imp_NtOpenFile
0x180100554  nop     dword ptr [rax+rax+00h]
0x180100559  test    eax, eax
0x18010055b  jns     short loc_180100569
0x18010055d  mov     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180100569  mov     edi, 2
0x18010056e  test    r13, r13
0x180100571  jz      loc_1801006E3
0x180100577  xorps   xmm0, xmm0
0x18010057a  movups  xmmword ptr [rsp+228h+P], xmm0
0x180100582  mov     edx, cs:KernelBaseGlobalData; Flags
0x180100588  movzx   r8d, [rsp+228h+DestinationString.MaximumLength]
0x180100591  add     r8, rdi; Size
0x180100594  mov     rcx, gs:60h
0x18010059d  mov     rcx, [rcx+30h]; HeapHandle
0x1801005a1  call    cs:__imp_RtlAllocateHeap
0x1801005a8  nop     dword ptr [rax+rax+00h]
0x1801005ad  mov     [rsp+228h+P+8], rax
0x1801005b5  test    rax, rax
0x1801005b8  jz      loc_1801006E3
0x1801005be  movzx   r8d, [rsp+228h+DestinationString.Length]; Size
0x1801005c7  mov     rdx, [rsp+228h+DestinationString.Buffer]; Src
0x1801005cf  mov     rcx, rax; void *
0x1801005d2  call    memcpy_0
0x1801005d7  movzx   edx, [rsp+228h+DestinationString.Length]
0x1801005df  shr     edx, 1
0x1801005e1  mov     [rsp+228h+var_188], edx
0x1801005e8  mov     r8d, edx
0x1801005eb  mov     ecx, edx
0x1801005ed  mov     r9, [rsp+228h+P+8]
0x1801005f5  test    r8d, r8d
0x1801005f8  jz      short loc_180100614
0x1801005fa  dec     ecx
0x1801005fc  mov     eax, ecx
0x1801005fe  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x180100604  jz      short loc_180100614
0x180100606  mov     edx, ecx
0x180100608  mov     [rsp+228h+var_188], ecx
0x18010060f  mov     r8d, ecx
0x180100612  jmp     short loc_1801005F5
0x180100614  mov     ecx, r8d
0x180100617  mov     [r9+rcx*2], r15w
0x18010061c  add     dx, dx
0x18010061f  mov     word ptr [rsp+228h+P], dx
0x180100627  add     dx, di
0x18010062a  mov     word ptr [rsp+228h+P+2], dx
0x180100632  mov     [rsp+228h+ObjectAttributes.Length], 30h ; '0'
0x18010063d  mov     [rsp+228h+ObjectAttributes.RootDirectory], r15
0x180100645  mov     [rsp+228h+ObjectAttributes.Attributes], 40h ; '@'
0x180100650  lea     rax, [rsp+228h+P]
0x180100658  mov     [rsp+228h+ObjectAttributes.ObjectName], rax
0x180100660  xorps   xmm0, xmm0
0x180100663  movdqu  xmmword ptr [rsp+228h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010066c  mov     [rsp+228h+OpenOptions], 4020h; OpenOptions
  ... truncated ...
```
