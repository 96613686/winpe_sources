# AslPathWildcardFindNext

- ea: `0x1800be9d0`
- end: `0x1800bf4eb`
- name: `AslPathWildcardFindNext`
- size: `2843`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800a9c60`
- `0x1800be468`

## callees

- `0x180041774`
- `0x18004281c`
- `0x180075fa0`
- `0x180076f14`
- `0x180076f20`
- `0x1800ab19c`
- `0x1800be9d0`
- `0x1800bf7f8`
- `0x1800bfb78`
- `0x1800bfee4`
- `0x1800bff54`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800bed4d`
- `ntdll!RtlInitUnicodeString` at `0x1800bed4d`
- `ntdll!RtlAllocateHeap` at `0x1800bea79`
- `ntdll!RtlAllocateHeap` at `0x1800becbf`
- `ntdll!RtlAllocateHeap` at `0x1800bf016`
- `ntdll!RtlAllocateHeap` at `0x1800bea79`
- `ntdll!RtlAllocateHeap` at `0x1800becbf`
- `ntdll!RtlAllocateHeap` at `0x1800bf016`
- `ntdll!RtlReAllocateHeap` at `0x1800becdf`
- `ntdll!RtlReAllocateHeap` at `0x1800bf036`
- `ntdll!RtlReAllocateHeap` at `0x1800becdf`
- `ntdll!RtlReAllocateHeap` at `0x1800bf036`
- `ntdll!RtlFreeUnicodeString` at `0x1800bf4ae`
- `ntdll!RtlFreeUnicodeString` at `0x1800bf4ae`
- `ntdll!ZwQueryDirectoryFile` at `0x1800bed91`
- `ntdll!ZwQueryDirectoryFile` at `0x1800bed91`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf1ba`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf212`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf2ba`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf359`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf1ba`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf212`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf2ba`
- `ntdll!RtlpEnsureBufferSize` at `0x1800bf359`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800bf3db`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800bf3db`

## string_xrefs

- `0x1800bed2b`: `AslpPathWildcardPeekNode failed [%x]`
- `0x1800bf44d`: `AslpPathWildcardPeekNode failed [%x]`
- `0x1800bed38`: `AslpPathWildcardPopNode`
- `0x1800bed11`: `AslpPathWildcardPeekNode`
- `0x1800bf43c`: `AslpPathWildcardPeekNode`
- `0x1800bf41b`: `RtlStringCbCopyNW failed [%x]`
- `0x1800beb05`: `AslPathWildcardFindNext`
- `0x1800bedbe`: `AslPathWildcardFindNext`
- `0x1800beddf`: `AslPathWildcardFindNext`
- `0x1800bf0d7`: `AslPathWildcardFindNext`
- `0x1800bf12e`: `AslPathWildcardFindNext`
- `0x1800bf463`: `AslPathWildcardFindNext`
- `0x1800bf151`: `AslpPathWildcardPushNode failed [%x]`
- `0x1800bf0ca`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x1800bf119`: `Failed to compute the path length [%x]`
- `0x1800bedad`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x1800bedd3`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x1800bf3eb`: `RtlNtPathNameToDosPathName failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileInformation; // r13
  unsigned int v6; // ebx
  __int64 v7; // rax
  ULONGLONG v8; // rcx
  unsigned __int16 *v9; // rbx
  __int64 v10; // rax
  int v11; // ebx
  ULONGLONG v12; // rcx
  ULONGLONG v13; // rdx
  __int64 v14; // r10
  ULONGLONG v15; // rcx
  __int64 v16; // r9
  char *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r9
  ULONGLONG v20; // rbx
  ULONGLONG v21; // r10
  ULONGLONG v22; // rcx
  const void *v23; // rdx
  ULONGLONG v24; // rsi
  ULONGLONG v25; // rdx
  ULONGLONG v26; // rsi
  void *v27; // r8
  size_t v28; // r14
  void *v29; // rcx
  PVOID v30; // rax
  PVOID Heap; // rbx
  NTSTATUS v32; // eax
  __int64 v33; // rax
  ULONGLONG v34; // rcx
  ULONGLONG v35; // rdx
  __int64 v36; // r10
  ULONGLONG v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rbx
  __int64 v40; // r9
  ULONGLONG v41; // r10
  ULONGLONG v42; // rcx
  PWSTR Buffer; // rsi
  bool v44; // zf
  int matched; // eax
  ULONGLONG v46; // r15
  __int64 v47; // r14
  ULONGLONG v48; // rdx
  ULONGLONG v49; // rcx
  __int64 v50; // r9
  ULONGLONG v51; // r14
  void *v52; // r8
  size_t v53; // rsi
  void *v54; // rcx
  PVOID v55; // rax
  PVOID v56; // rbx
  ULONGLONG v57; // rcx
  _OWORD *v58; // rdx
  int v59; // eax
  SIZE_T v60; // rdx
  WCHAR *p_ReservedForAllocatedSize; // rcx
  SIZE_T v62; // r8
  const char *v63; // r9
  __int64 v64; // r8
  USHORT Length; // r9
  SIZE_T v66; // r8
  USHORT v67; // cx
  unsigned __int64 v68; // r8
  USHORT v69; // ax
  USHORT v70; // r9
  USHORT v71; // dx
  unsigned __int64 v72; // r8
  unsigned __int64 v73; // rdx
  NTSTATUS v74; // eax
  int v75; // eax
  PUCHAR StaticBuffer; // rcx
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-E0h]
  ULONGLONG Size; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v79; // [rsp+68h] [rbp-98h] BYREF
  ULONGLONG pullResult; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v83; // [rsp+98h] [rbp-68h] BYREF
  __int128 v84; // [rsp+A8h] [rbp-58h]
  struct _IO_STATUS_BLOCK v85; // [rsp+B8h] [rbp-48h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+C8h] [rbp-38h] BYREF

  *(_QWORD *)&UnicodeString.Length = a1;
  if ( a3 == -1 )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v79 = 0;
  v85 = 0;
  DestinationString = 0;
  v83 = 0;
  v84 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v6 = -1073741801;
    goto LABEL_131;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v7 = *(_QWORD *)(a3 + 32);
            if ( !v7 )
            {
              v6 = -2147483642;
              goto LABEL_130;
            }
            v8 = *(_QWORD *)(a3 + 24);
            pullResult = 0;
            if ( ULongLongMult(v8, v7 - 1, &pullResult) < 0
              || (v9 = (unsigned __int16 *)(*(_QWORD *)(a3 + 56) + pullResult),
                  (unsigned __int64)v9 < *(_QWORD *)(a3 + 56))
              || !v9 )
            {
              AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
              v63 = "AslpPathWildcardPeekNode failed [%x]";
              v64 = 2498;
              v6 = -1073741595;
              goto LABEL_128;
            }
            if ( *((_QWORD *)v9 + 3) )
              break;
            AslLogCallPrintf(1, "AslPathWildcardFindNext", 2503, "Node on the stack with invalid handle.");
            v10 = *(_QWORD *)(a3 + 32);
            if ( !v10 )
              goto LABEL_15;
            v12 = *(_QWORD *)(a3 + 24);
            pullResult = 0;
            if ( ULongLongMult(v12, v10 - 1, &pullResult) < 0 )
              goto LABEL_39;
            v13 = *(_QWORD *)(a3 + 56) + pullResult;
            if ( v13 < *(_QWORD *)(a3 + 56) || !v13 )
              goto LABEL_39;
            AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + pullResult);
            v14 = *(_QWORD *)(a3 + 32);
            if ( v14 )
            {
              v15 = *(_QWORD *)(a3 + 24);
              pullResult = 0;
              if ( ULongLongMult(v15, v14 - 1, &pullResult) >= 0 )
              {
                v17 = (char *)(*(_QWORD *)(a3 + 56) + pullResult);
                if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
                {
                  v18 = *(_QWORD *)(a3 + 32);
                  v19 = ~v16;
                  v44 = v19 + v18 == 0;
                  v20 = v19 + v18;
                  Size = v20;
                  if ( v44 )
                    goto LABEL_28;
                  if ( ULongLongMult(v20, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                  {
                    v22 = *(_QWORD *)(a3 + 24);
                    pullResult = 0;
                    if ( ULongLongMult(v22, v21, &pullResult) >= 0 )
                    {
                      v23 = (const void *)(*(_QWORD *)(a3 + 56) + pullResult);
                      if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                      {
                        v20 = Size;
LABEL_27:
                        memmove_0(v17, v23, v20);
                        goto LABEL_28;
                      }
                    }
                  }
                }
              }
            }
          }
          RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v9 + 2));
          v32 = ZwQueryDirectoryFile(
                  *((HANDLE *)v9 + 3),
                  0,
                  0,
                  0,
                  &v85,
                  FileInformation,
                  0x268u,
                  FileBothDirectoryInformation,
                  1u,
                  &DestinationString,
                  0);
          if ( v32 >= 0 )
            break;
          if ( v32 != -2147483642 && v32 != -1073741809 )
          {
            AslLogCallPrintf(
              1,
              "AslPathWildcardFindNext",
              2527,
              "NtQueryDirectoryFile failed to query next file [%x]",
              v32);
            AslLogCallPrintf(
              2,
              "AslPathWildcardFindNext",
              2528,
              "FilePath: '%ws'  Pattern: '%ws'",
              *((_QWORD *)v9 + 1),
              DestinationString.Buffer);
          }
          v33 = *(_QWORD *)(a3 + 32);
          if ( !v33 )
          {
LABEL_15:
            v11 = -2147483622;
            goto LABEL_40;
          }
          v34 = *(_QWORD *)(a3 + 24);
          Size = 0;
          if ( ULongLongMult(v34, v33 - 1, &Size) >= 0
            && (v35 = *(_QWORD *)(a3 + 56) + Size, v35 >= *(_QWORD *)(a3 + 56))
            && v35 )
          {
            AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + Size);
            v36 = *(_QWORD *)(a3 + 32);
            if ( v36 )
            {
              v37 = *(_QWORD *)(a3 + 24);
              Size = 0;
              if ( ULongLongMult(v37, v36 - 1, &Size) >= 0 )
              {
                v17 = (char *)(*(_QWORD *)(a3 + 56) + Size);
                if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
                {
                  v39 = *(_QWORD *)(a3 + 32);
                  v40 = ~v38;
                  v44 = v40 + v39 == 0;
                  v20 = v40 + v39;
                  pullResult = v20;
                  if ( v44 )
                  {
LABEL_28:
                    memset_0(&v17[v20], 0, *(_QWORD *)(a3 + 24));
                    if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                    {
                      v24 = *(_QWORD *)(a3 + 40);
                      v25 = *(_QWORD *)(a3 + 24);
                      if ( v25 * v24 >= 0x400 && *(_QWORD *)(a3 + 32) < v24 >> 2 )
                      {
                        Size = 0;
                        if ( ULongLongMult(v24, v25, &pullResult) >= 0 )
                        {
                          v26 = v24 >> 1;
                          if ( ULongLongMult(v26, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                          {
                            v27 = *(void **)(a3 + 56);
                            v28 = Size;
                            v29 = *(void **)(a3 + 16);
                            if ( v27 )
                            {
                              Heap = RtlReAllocateHeap(v29, 0, v27, Size);
                            }
                            else
                            {
                              v30 = RtlAllocateHeap(v29, 0, Size);
                              Heap = v30;
                              if ( v30 )
                                memset_0(v30, 0, v28);
                            }
                            if ( Heap )
                            {
                              *(_QWORD *)(a3 + 56) = Heap;
                              *(_QWORD *)(a3 + 40) = v26;
                            }
                          }
                        }
                      }
                    }
                  }
                  else if ( ULongLongMult(v20, *(_QWORD *)(a3 + 24), &pullResult) >= 0 )
                  {
                    v42 = *(_QWORD *)(a3 + 24);
                    Size = 0;
                    if ( ULongLongMult(v42, v41, &Size) >= 0 )
                    {
                      v23 = (const void *)(*(_QWORD *)(a3 + 56) + Size);
                      if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                      {
                        v20 = pullResult;
                        goto LABEL_27;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
LABEL_39:
            v11 = -1073741595;
            AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
LABEL_40:
            LODWORD(IoStatusBlock) = v11;
            AslLogCallPrintf(1, "AslpPathWildcardPopNode", 2106, "AslpPathWildcardPeekNode failed [%x]", IoStatusBlock);
          }
        }
        Buffer = (PWSTR)(FileInformation + 94);
        if ( *((_DWORD *)FileInformation + 15) == 4 )
        {
          if ( *Buffer != 46 )
            break;
          v44 = *((_WORD *)FileInformation + 48) == 46;
        }
        else
        {
          if ( *((_DWORD *)FileInformation + 15) != 2 )
            break;
          Buffer = (PWSTR)(FileInformation + 94);
          v44 = *((_WORD *)FileInformation + 47) == 46;
        }
      }
      while ( v44 );
      matched = AslpPathWildcardAllocMatchNode(
                  (unsigned int)&v83,
                  (_DWORD)v9,
                  *((_QWORD *)v9 + 2),
                  (*((_DWORD *)FileInformation + 14) >> 4) & 1,
                  (__int64)Buffer,
                  *((_WORD *)FileInformation + 30));
      if ( matched == -1073741197 )
        break;
      if ( matched != -1073741565 && matched != -1073741638 )
      {
        if ( matched < 0 )
        {
          LODWORD(IoStatusBlock) = matched;
          AslLogCallPrintf(
            1,
            "AslPathWildcardFindNext",
            2585,
            "AslpPathWildcardAllocMatchNode failed [%x]",
            IoStatusBlock);
        }
        else
        {
          v46 = *(_QWORD *)(a3 + 32);
          if ( v46 >= *(_QWORD *)(a3 + 40) )
          {
            if ( v46 + 1 <= *(_QWORD *)(a3 + 40) )
            {
              v6 = -1073741811;
              goto LABEL_84;
            }
            v47 = *(_QWORD *)(a3 + 48) - 1LL;
            if ( *(_QWORD *)(a3 + 48) + v46 < v46 + 1
              || (v48 = *(_QWORD *)(a3 + 24),
                  v49 = *(_QWORD *)(a3 + 40),
                  Size = 0,
                  ULongLongMult(v49, v48, &pullResult) < 0)
              || (v51 = v50 & ~v47, ULongLongMult(v51, *(_QWORD *)(a3 + 24), &Size) < 0) )
            {
              v6 = -1073741675;
LABEL_84:
              v59 = v6;
LABEL_90:
              LODWORD(IoStatusBlock) = v59;
              AslLogCallPrintf(
                1,
                "AslPathWildcardFindNext",
                2577,
                "AslpPathWildcardPushNode failed [%x]",
                IoStatusBlock);
              goto LABEL_130;
            }
            v52 = *(void **)(a3 + 56);
            v53 = Size;
            v54 = *(void **)(a3 + 16);
            if ( v52 )
            {
              v56 = RtlReAllocateHeap(v54, 0, v52, Size);
            }
            else
            {
              v55 = RtlAllocateHeap(v54, 0, Size);
              v56 = v55;
              if ( v55 )
                memset_0(v55, 0, v53);
            }
            if ( !v56 )
            {
              v6 = -1073741801;
              goto LABEL_84;
            }
            *(_QWORD *)(a3 + 40) = v51;
            *(_QWORD *)(a3 + 56) = v56;
          }
          v57 = *(_QWORD *)(a3 + 24);
          Size = 0;
          if ( ULongLongMult(v57, v46, &Size) < 0
            || (v58 = (_OWORD *)(*(_QWORD *)(a3 + 56) + Size), (unsigned __int64)v58 < *(_QWORD *)(a3 + 56)) )
          {
            v59 = -1073741675;
            v6 = -1073741675;
            goto LABEL_90;
          }
          *v58 = v83;
          v58[1] = v84;
          ++*(_QWORD *)(a3 + 32);
        }
      }
    }
    if ( (int)RtlUShortAdd(*v9, *((unsigned __int16 *)FileInformation + 30), &v79) >= 0
      && (int)RtlUShortAdd(v79, 2, &v79) >= 0 )
    {
      break;
    }
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2629, "Failed to compute the path length [%x]", -1073741675);
  }
  v60 = 2;
  Path.ByteBuffer.StaticSize = 2;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  v62 = v79 + 2LL;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Size = 2;
  LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
  Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
  *(_DWORD *)&Path.String.Length = 0x20000;
  if ( v62 > 0xFFFE )
  {
    v6 = -1073741562;
    goto LABEL_96;
  }
  if ( v62 > 2 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v62) < 0 )
    {
      v6 = -1073741801;
LABEL_96:
      v63 = "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]";
      v64 = 2638;
LABEL_128:
      LODWORD(IoStatusBlock) = v6;
      AslLogCallPrintf(1, "AslPathWildcardFindNext", v64, v63, IoStatusBlock);
      goto LABEL_130;
    }
    v60 = Path.ByteBuffer.Size;
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  Length = 0;
  Path.String.MaximumLength = v60;
  Path.String.Length = 0;
  v66 = *v9 + 2LL;
  if ( v66 > 0xFFFE )
  {
    v6 = -1073741562;
LABEL_103:
    v63 = "RtlAssignUnicodeStringBuffer failed [%x]";
    v64 = 2648;
    goto LABEL_128;
  }
  if ( v66 > v60 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v66) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_103;
    }
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v9 + 1), *v9);
  Path.String.MaximumLength = *v9 + Path.String.Length + 2;
  Path.String.Length += *v9;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  if ( *(_WORD *)(*((_QWORD *)v9 + 1) + 2 * ((unsigned __int64)*v9 >> 1) - 2) != 92 )
  {
    v67 = Path.String.Length;
    v68 = (unsigned int)Path.String.Length + 2 + 2LL;
    if ( v68 > 0xFFFE )
    {
      v6 = -1073741562;
LABEL_111:
      v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
      v64 = 2655;
      goto LABEL_128;
    }
    if ( v68 > Path.ByteBuffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v68) < 0 )
      {
        v6 = -1073741801;
        goto LABEL_111;
      }
      v67 = Path.String.Length;
    }
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v67 >> 1)] = pszSrch[0];
    v69 = Path.String.Length + 4;
    Path.String.Length += 2;
    Path.String.MaximumLength = v69;
    Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  }
  v70 = Path.String.Length;
  DestinationString.Buffer = Buffer;
  DestinationString.Length = *((_WORD *)FileInformation + 30);
  v71 = DestinationString.Length;
  DestinationString.MaximumLength = *((_WORD *)FileInformation + 30);
  v72 = Path.String.Length + (unsigned int)DestinationString.Length + 2LL;
  if ( v72 > 0xFFFE )
  {
    v6 = -1073741562;
LABEL_119:
    v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
    v64 = 2670;
    goto LABEL_128;
  }
  if ( v72 > Path.ByteBuffer.Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v72) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_119;
    }
    Buffer = DestinationString.Buffer;
    v71 = DestinationString.Length;
    v70 = Path.String.Length;
  }
  Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
  memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v70 >> 1)], Buffer, v71);
  v73 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
  Path.String.Length = v73;
  Path.String.MaximumLength = v73 + 2;
  Path.String.Buffer[v73 >> 1] = 0;
  if ( *(_DWORD *)a3 && (v74 = RtlNtPathNameToDosPathName(0, &Path, 0, 0), v6 = v74, v74 < 0) )
  {
    LODWORD(IoStatusBlock) = v74;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2681, "RtlNtPathNameToDosPathName failed [%x]", IoStatusBlock);
  }
  else
  {
    v75 = RtlStringCbCopyNW(*(_QWORD *)&UnicodeString.Length, 520, Path.String.Buffer, Path.String.Length);
    v6 = v75;
    if ( v75 >= 0 )
    {
      v6 = 0;
    }
    else
    {
      LODWORD(IoStatusBlock) = v75;
      AslLogCallPrintf(1, "AslPathWildcardFindNext", 2692, "RtlStringCbCopyNW failed [%x]", IoStatusBlock);
    }
  }
LABEL_130:
  AslFree(NtCurrentPeb()->ProcessHeap, FileInformation);
LABEL_131:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer && Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
  {
    *(_QWORD *)&UnicodeString.Length = 0;
    UnicodeString.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    RtlFreeUnicodeString(&UnicodeString);
    StaticBuffer = Path.ByteBuffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return v6;
}

```

## disassembly

```asm
0x1800be9d0  mov     [rsp-8+arg_8], rbx
0x1800be9d5  mov     [rsp-8+arg_18], rsi
0x1800be9da  push    rbp
0x1800be9db  push    rdi
0x1800be9dc  push    r13
0x1800be9de  push    r14
0x1800be9e0  push    r15
0x1800be9e2  lea     rbp, [rsp-10h]
0x1800be9e7  sub     rsp, 110h
0x1800be9ee  mov     rax, cs:__security_cookie
0x1800be9f5  xor     rax, rsp
0x1800be9f8  mov     [rbp+30h+Path.ByteBuffer.ReservedForIMalloc], rax
0x1800be9fc  mov     qword ptr [rbp+30h+UnicodeString.Length], rcx
0x1800bea00  mov     rdi, r8
0x1800bea03  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800bea07  jnz     short loc_1800BEA13
0x1800bea09  mov     eax, 80000006h
0x1800bea0e  jmp     loc_1800BF4C3
0x1800bea13  xor     r15d, r15d
0x1800bea16  test    rcx, rcx
0x1800bea19  jnz     short loc_1800BEA25
0x1800bea1b  mov     eax, 0C00000EFh
0x1800bea20  jmp     loc_1800BF4C3
0x1800bea25  test    rdi, rdi
0x1800bea28  jnz     short loc_1800BEA34
0x1800bea2a  mov     eax, 0C00000F1h
0x1800bea2f  jmp     loc_1800BF4C3
0x1800bea34  xorps   xmm1, xmm1
0x1800bea37  mov     [rsp+130h+var_C8], r15w
0x1800bea3d  xorps   xmm0, xmm0
0x1800bea40  xor     eax, eax
0x1800bea42  movups  xmmword ptr [rbp+30h+var_78], xmm0
0x1800bea46  mov     [rbp+30h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x1800bea4a  mov     r8d, 268h; Size
0x1800bea50  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x1800bea55  lea     edx, [rax+8]; Flags
0x1800bea58  movups  [rbp+30h+var_98], xmm0
0x1800bea5c  movups  [rbp+30h+var_88], xmm0
0x1800bea60  movups  xmmword ptr [rbp+30h+Path.String.Length], xmm1
0x1800bea64  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Buffer], xmm1
0x1800bea68  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Size], xmm1
0x1800bea6c  mov     rcx, gs:60h
0x1800bea75  mov     rcx, [rcx+30h]; HeapHandle
0x1800bea79  call    cs:__imp_RtlAllocateHeap
0x1800bea7f  mov     r13, rax
0x1800bea82  test    rax, rax
0x1800bea85  jnz     short loc_1800BEA91
0x1800bea87  mov     ebx, 0C0000017h
0x1800bea8c  jmp     loc_1800BF490
0x1800bea91  mov     r14d, 2
0x1800bea97  mov     esi, 4
0x1800bea9c  mov     rax, [rdi+20h]
0x1800beaa0  cmp     rax, 1
0x1800beaa4  jb      loc_1800BF476
0x1800beaaa  lea     rdx, [rax-1]; ullMultiplier
0x1800beaae  cmp     rdx, rax
0x1800beab1  jnb     loc_1800BF42F
0x1800beab7  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800beabb  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800beac0  mov     [rsp+130h+pullResult], r15
0x1800beac5  call    ULongLongMult
0x1800beaca  test    eax, eax
0x1800beacc  js      loc_1800BF42F
0x1800bead2  mov     rbx, [rsp+130h+pullResult]
0x1800bead7  add     rbx, [rdi+38h]
0x1800beadb  cmp     rbx, [rdi+38h]
0x1800beadf  jb      loc_1800BF42F
0x1800beae5  test    rbx, rbx
0x1800beae8  jz      loc_1800BF42F
0x1800beaee  cmp     [rbx+18h], r15
0x1800beaf2  jnz     loc_1800BED44
0x1800beaf8  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x1800beaff  mov     r8d, 9C7h
0x1800beb05  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800beb0c  mov     ecx, 1
0x1800beb11  call    AslLogCallPrintf
0x1800beb16  mov     rax, [rdi+20h]
0x1800beb1a  cmp     rax, 1
0x1800beb1e  jnb     short loc_1800BEB2A
0x1800beb20  mov     ebx, 8000001Ah
0x1800beb25  jmp     loc_1800BED27
0x1800beb2a  lea     rdx, [rax-1]; ullMultiplier
0x1800beb2e  cmp     rdx, rax
0x1800beb31  jnb     loc_1800BED04
0x1800beb37  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800beb3b  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800beb40  mov     [rsp+130h+pullResult], r15
0x1800beb45  call    ULongLongMult
0x1800beb4a  test    eax, eax
0x1800beb4c  js      loc_1800BED04
0x1800beb52  mov     rdx, [rsp+130h+pullResult]
0x1800beb57  add     rdx, [rdi+38h]
0x1800beb5b  cmp     rdx, [rdi+38h]
0x1800beb5f  jb      loc_1800BED04
0x1800beb65  test    rdx, rdx
0x1800beb68  jz      loc_1800BED04
0x1800beb6e  mov     rcx, rdx
0x1800beb71  call    AslpPathWildcardFreeMatchNode
0x1800beb76  mov     r10, [rdi+20h]
0x1800beb7a  lea     r9, [r10-1]
0x1800beb7e  cmp     r9, r10
0x1800beb81  jnb     loc_1800BEA9C
0x1800beb87  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800beb8b  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800beb90  mov     rdx, r9; ullMultiplier
0x1800beb93  mov     [rsp+130h+pullResult], r15
0x1800beb98  call    ULongLongMult
0x1800beb9d  test    eax, eax
0x1800beb9f  js      loc_1800BEA9C
0x1800beba5  mov     rsi, [rsp+130h+pullResult]
0x1800bebaa  add     rsi, [rdi+38h]
0x1800bebae  cmp     rsi, [rdi+38h]
0x1800bebb2  jb      loc_1800BEA97
0x1800bebb8  mov     rbx, [rdi+20h]
0x1800bebbc  not     r9
0x1800bebbf  add     rbx, r9
0x1800bebc2  mov     [rsp+130h+Size], rbx
0x1800bebc7  jz      short loc_1800BEC23
0x1800bebc9  mov     rdx, [rdi+18h]; ullMultiplier
0x1800bebcd  lea     r8, [rsp+130h+Size]; pullResult
0x1800bebd2  mov     rcx, rbx; ullMultiplicand
0x1800bebd5  call    ULongLongMult
0x1800bebda  test    eax, eax
0x1800bebdc  js      loc_1800BEA97
0x1800bebe2  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800bebe6  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800bebeb  mov     rdx, r10; ullMultiplier
0x1800bebee  mov     [rsp+130h+pullResult], r15
0x1800bebf3  call    ULongLongMult
0x1800bebf8  test    eax, eax
0x1800bebfa  js      loc_1800BEA97
0x1800bec00  mov     rdx, [rsp+130h+pullResult]
0x1800bec05  add     rdx, [rdi+38h]; Src
0x1800bec09  cmp     rdx, [rdi+38h]
0x1800bec0d  jb      loc_1800BEA97
0x1800bec13  mov     rbx, [rsp+130h+Size]
0x1800bec18  mov     r8, rbx; Size
0x1800bec1b  mov     rcx, rsi; void *
0x1800bec1e  call    memmove_0
0x1800bec23  mov     r8, [rdi+18h]; Size
0x1800bec27  lea     rcx, [rsi+rbx]; void *
0x1800bec2b  xor     edx, edx; Val
0x1800bec2d  call    memset_0
0x1800bec32  dec     qword ptr [rdi+20h]
0x1800bec36  mov     esi, 4
0x1800bec3b  cmp     qword ptr [rdi+20h], 10h
0x1800bec40  jbe     loc_1800BEA9C
0x1800bec46  mov     rsi, [rdi+28h]
0x1800bec4a  mov     rdx, [rdi+18h]; ullMultiplier
0x1800bec4e  mov     rax, rsi
0x1800bec51  imul    rax, rdx
0x1800bec55  cmp     rax, 400h
0x1800bec5b  jb      loc_1800BEA97
0x1800bec61  mov     rax, rsi
0x1800bec64  shr     rax, 2
0x1800bec68  cmp     [rdi+20h], rax
0x1800bec6c  jnb     loc_1800BEA97
0x1800bec72  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800bec77  mov     [rsp+130h+Size], r15
0x1800bec7c  mov     rcx, rsi; ullMultiplicand
0x1800bec7f  call    ULongLongMult
0x1800bec84  test    eax, eax
0x1800bec86  js      loc_1800BEA97
0x1800bec8c  mov     rdx, [rdi+18h]; ullMultiplier
0x1800bec90  lea     r8, [rsp+130h+Size]; pullResult
0x1800bec95  shr     rsi, 1
0x1800bec98  mov     rcx, rsi; ullMultiplicand
0x1800bec9b  call    ULongLongMult
0x1800beca0  test    eax, eax
0x1800beca2  js      loc_1800BEA97
0x1800beca8  mov     r8, [rdi+38h]; Ptr
0x1800becac  xor     edx, edx; Flags
0x1800becae  mov     r14, [rsp+130h+Size]
0x1800becb3  mov     rcx, [rdi+10h]; Heap
0x1800becb7  test    r8, r8
0x1800becba  jnz     short loc_1800BECDC
0x1800becbc  mov     r8, r14; Size
0x1800becbf  call    cs:__imp_RtlAllocateHeap
0x1800becc5  mov     rbx, rax
0x1800becc8  test    rax, rax
0x1800beccb  jz      short loc_1800BECE8
0x1800beccd  mov     r8, r14; Size
0x1800becd0  xor     edx, edx; Val
0x1800becd2  mov     rcx, rax; void *
0x1800becd5  call    memset_0
0x1800becda  jmp     short loc_1800BECE8
0x1800becdc  mov     r9, r14; Size
0x1800becdf  call    cs:__imp_RtlReAllocateHeap
0x1800bece5  mov     rbx, rax
0x1800bece8  mov     r14d, 2
0x1800becee  test    rbx, rbx
0x1800becf1  jz      loc_1800BEA97
0x1800becf7  mov     [rdi+38h], rbx
0x1800becfb  mov     [rdi+28h], rsi
0x1800becff  jmp     loc_1800BEA97
0x1800bed04  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x1800bed0b  mov     r8d, 81Fh
0x1800bed11  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x1800bed18  mov     ecx, 1
0x1800bed1d  mov     ebx, 0C00000E5h
0x1800bed22  call    AslLogCallPrintf
0x1800bed27  mov     dword ptr [rsp+130h+IoStatusBlock], ebx
0x1800bed2b  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x1800bed32  mov     r8d, 83Ah
0x1800bed38  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x1800bed3f  jmp     loc_1800BF0DE
0x1800bed44  mov     rdx, [rbx+10h]; SourceString
0x1800bed48  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800bed4d  call    cs:__imp_RtlInitUnicodeString
0x1800bed53  mov     rcx, [rbx+18h]; FileHandle
0x1800bed57  lea     rax, [rsp+130h+DestinationString]
0x1800bed5c  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x1800bed61  xor     r9d, r9d; ApcContext
0x1800bed64  mov     [rsp+130h+FileName], rax; FileName
0x1800bed69  xor     r8d, r8d; ApcRoutine
0x1800bed6c  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800bed71  lea     rax, [rbp+30h+var_78]
0x1800bed75  mov     [rsp+130h+FileInformationClass], 3; FileInformationClass
0x1800bed7d  xor     edx, edx; Event
0x1800bed7f  mov     [rsp+130h+Length], 268h; Length
0x1800bed87  mov     [rsp+130h+FileInformation], r13; FileInformation
0x1800bed8c  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x1800bed91  call    cs:__imp_ZwQueryDirectoryFile
0x1800bed97  test    eax, eax
0x1800bed99  jns     loc_1800BEF02
0x1800bed9f  cmp     eax, 80000006h
0x1800beda4  jz      short loc_1800BEDFD
0x1800beda6  cmp     eax, 0C000000Fh
0x1800bedab  jz      short loc_1800BEDFD
0x1800bedad  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x1800bedb4  mov     dword ptr [rsp+130h+IoStatusBlock], eax
0x1800bedb8  mov     r8d, 9DFh
0x1800bedbe  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800bedc5  mov     ecx, 1
0x1800bedca  call    AslLogCallPrintf
0x1800bedcf  mov     rax, [rbp+30h+DestinationString.Buffer]
0x1800bedd3  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x1800bedda  mov     [rsp+130h+FileInformation], rax
0x1800beddf  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800bede6  mov     rax, [rbx+8]
0x1800bedea  mov     r8d, 9E0h
0x1800bedf0  mov     ecx, r14d
0x1800bedf3  mov     [rsp+130h+IoStatusBlock], rax
0x1800bedf8  call    AslLogCallPrintf
0x1800bedfd  mov     rax, [rdi+20h]
0x1800bee01  cmp     rax, 1
0x1800bee05  jb      loc_1800BEB20
0x1800bee0b  lea     rdx, [rax-1]; ullMultiplier
0x1800bee0f  cmp     rdx, rax
0x1800bee12  jnb     loc_1800BED04
0x1800bee18  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800bee1c  lea     r8, [rsp+130h+Size]; pullResult
0x1800bee21  mov     [rsp+130h+Size], r15
0x1800bee26  call    ULongLongMult
0x1800bee2b  test    eax, eax
0x1800bee2d  js      loc_1800BED04
0x1800bee33  mov     rdx, [rsp+130h+Size]
0x1800bee38  add     rdx, [rdi+38h]
0x1800bee3c  cmp     rdx, [rdi+38h]
0x1800bee40  jb      loc_1800BED04
0x1800bee46  test    rdx, rdx
0x1800bee49  jz      loc_1800BED04
0x1800bee4f  mov     rcx, rdx
0x1800bee52  call    AslpPathWildcardFreeMatchNode
0x1800bee57  mov     r10, [rdi+20h]
0x1800bee5b  lea     r9, [r10-1]
0x1800bee5f  cmp     r9, r10
0x1800bee62  jnb     loc_1800BEA9C
0x1800bee68  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800bee6c  lea     r8, [rsp+130h+Size]; pullResult
0x1800bee71  mov     rdx, r9; ullMultiplier
0x1800bee74  mov     [rsp+130h+Size], r15
0x1800bee79  call    ULongLongMult
0x1800bee7e  test    eax, eax
0x1800bee80  js      loc_1800BEA9C
0x1800bee86  mov     rsi, [rsp+130h+Size]
0x1800bee8b  add     rsi, [rdi+38h]
0x1800bee8f  cmp     rsi, [rdi+38h]
0x1800bee93  jb      loc_1800BEA97
0x1800bee99  mov     rbx, [rdi+20h]
0x1800bee9d  not     r9
0x1800beea0  add     rbx, r9
0x1800beea3  mov     [rsp+130h+pullResult], rbx
0x1800beea8  jz      loc_1800BEC23
0x1800beeae  mov     rdx, [rdi+18h]; ullMultiplier
0x1800beeb2  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800beeb7  mov     rcx, rbx; ullMultiplicand
0x1800beeba  call    ULongLongMult
0x1800beebf  test    eax, eax
0x1800beec1  js      loc_1800BEA97
0x1800beec7  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800beecb  lea     r8, [rsp+130h+Size]; pullResult
0x1800beed0  mov     rdx, r10; ullMultiplier
0x1800beed3  mov     [rsp+130h+Size], r15
0x1800beed8  call    ULongLongMult
0x1800beedd  test    eax, eax
0x1800beedf  js      loc_1800BEA97
0x1800beee5  mov     rdx, [rsp+130h+Size]
0x1800beeea  add     rdx, [rdi+38h]
0x1800beeee  cmp     rdx, [rdi+38h]
  ... truncated ...
```
