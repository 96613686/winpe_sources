# AslPathWildcardFindNext

- ea: `0x180034c90`
- end: `0x180035826`
- name: `AslPathWildcardFindNext`
- size: `2966`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18004ef04`
- `0x18007ff50`

## callees

- `0x18001ef8c`
- `0x18001f138`
- `0x180034c90`
- `0x18003582c`
- `0x180053c8c`
- `0x18005a52c`
- `0x180061d70`
- `0x180078848`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180034ee6`
- `ntdll!RtlpEnsureBufferSize` at `0x1800350ea`
- `ntdll!RtlpEnsureBufferSize` at `0x1800351eb`
- `ntdll!RtlpEnsureBufferSize` at `0x18003525b`
- `ntdll!RtlpEnsureBufferSize` at `0x180034ee6`
- `ntdll!RtlpEnsureBufferSize` at `0x1800350ea`
- `ntdll!RtlpEnsureBufferSize` at `0x1800351eb`
- `ntdll!RtlpEnsureBufferSize` at `0x18003525b`
- `ntdll!RtlFreeUnicodeString` at `0x1800357e2`
- `ntdll!RtlFreeUnicodeString` at `0x1800357e2`
- `ntdll!RtlReAllocateHeap` at `0x180035638`
- `ntdll!RtlReAllocateHeap` at `0x1800356dc`
- `ntdll!RtlReAllocateHeap` at `0x180035638`
- `ntdll!RtlReAllocateHeap` at `0x1800356dc`
- `ntdll!ZwQueryDirectoryFile` at `0x180034e0f`
- `ntdll!ZwQueryDirectoryFile` at `0x180034e0f`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800352d2`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800352d2`
- `ntdll!RtlInitUnicodeString` at `0x180034dc6`
- `ntdll!RtlInitUnicodeString` at `0x180034dc6`
- `ntdll!RtlAllocateHeap` at `0x180034d20`
- `ntdll!RtlAllocateHeap` at `0x180035416`
- `ntdll!RtlAllocateHeap` at `0x1800356b6`
- `ntdll!RtlAllocateHeap` at `0x180034d20`
- `ntdll!RtlAllocateHeap` at `0x180035416`
- `ntdll!RtlAllocateHeap` at `0x1800356b6`

## string_xrefs

- `0x180034f26`: `AslPathWildcardFindNext`
- `0x180034f5b`: `AslPathWildcardFindNext`
- `0x180034f7c`: `AslPathWildcardFindNext`
- `0x1800351b5`: `AslPathWildcardFindNext`
- `0x1800355a7`: `AslPathWildcardFindNext`
- `0x18003571e`: `AslPathWildcardFindNext`
- `0x1800352ec`: `RtlNtPathNameToDosPathName failed [%x]`
- `0x180034f11`: `Failed to compute the path length [%x]`
- `0x180034d8c`: `AslpPathWildcardPeekNode`
- `0x180034fe3`: `AslpPathWildcardPeekNode`
- `0x180035326`: `AslpPathWildcardPushNode failed [%x]`
- `0x180034f70`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x180034f4a`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x180034d9d`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180034ffd`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18003500a`: `AslpPathWildcardPopNode`
- `0x180035793`: `RtlStringCbCopyNW failed [%x]`
- `0x180035711`: `AslpPathWildcardAllocMatchNode failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileInformation; // r13
  __int64 v5; // rax
  ULONGLONG v6; // rcx
  unsigned __int16 *v7; // rbx
  const char *v8; // r9
  int v9; // r8d
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  PWSTR Buffer; // rsi
  int matched; // eax
  unsigned __int16 v14; // ax
  SIZE_T v15; // rdx
  WCHAR *p_ReservedForAllocatedSize; // rcx
  SIZE_T v17; // r8
  __int64 v18; // rax
  char v19; // bl
  ULONGLONG v20; // rcx
  ULONGLONG v21; // rdx
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // rcx
  __int64 v24; // r14
  unsigned __int64 v25; // kr00_8
  unsigned __int64 v26; // kr10_8
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // r14
  SIZE_T v29; // rax
  unsigned __int64 v30; // kr20_8
  size_t v31; // rsi
  char v32; // al
  USHORT Length; // r9
  SIZE_T v34; // r8
  USHORT v35; // r9
  USHORT v36; // dx
  unsigned __int64 v37; // r8
  USHORT v38; // cx
  unsigned __int64 v39; // r8
  USHORT v40; // ax
  unsigned __int64 v41; // rdx
  NTSTATUS v42; // eax
  ULONGLONG v43; // rcx
  __int64 v44; // r9
  char *v45; // rsi
  __int64 v46; // rbx
  __int64 v47; // r9
  ULONGLONG v48; // rbx
  ULONGLONG v49; // r10
  ULONGLONG v50; // rcx
  const void *v51; // rdx
  ULONGLONG v52; // rsi
  void *v53; // r8
  size_t v54; // r14
  void *v55; // rcx
  PVOID v56; // rax
  PVOID Heap; // rbx
  ULONGLONG v58; // rcx
  ULONGLONG v59; // rdx
  __int64 v60; // r10
  ULONGLONG v61; // rcx
  __int64 v62; // r9
  __int64 v63; // rbx
  __int64 v64; // r9
  ULONGLONG v65; // r10
  ULONGLONG v66; // rcx
  ULONGLONG v67; // rsi
  ULONGLONG v68; // rdx
  _OWORD *v69; // rax
  __int64 v70; // rax
  __int64 v72; // r10
  bool v73; // zf
  void *v74; // r8
  void *v75; // rcx
  PVOID v76; // rax
  PVOID v77; // rbx
  int v78; // eax
  PUCHAR StaticBuffer; // rcx
  char IoStatusBlock; // [rsp+20h] [rbp-A9h]
  ULONGLONG Size; // [rsp+60h] [rbp-69h] BYREF
  ULONGLONG pullResult; // [rsp+68h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-49h] BYREF
  __int128 v85; // [rsp+90h] [rbp-39h] BYREF
  __int128 v86; // [rsp+A0h] [rbp-29h]
  struct _IO_STATUS_BLOCK v87; // [rsp+B0h] [rbp-19h] BYREF
  struct _RTL_UNICODE_STRING_BUFFER Path; // [rsp+C0h] [rbp-9h] BYREF

  *(_QWORD *)&UnicodeString.Length = a1;
  if ( a3 == -1 )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v87 = 0;
  DestinationString = 0;
  v85 = 0;
  v86 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v10 = -1073741801;
    goto LABEL_138;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          do
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v5 = *(_QWORD *)(a3 + 32);
                if ( !v5 )
                {
                  v10 = -2147483642;
                  goto LABEL_137;
                }
                v6 = *(_QWORD *)(a3 + 24);
                pullResult = 0;
                if ( ULongLongMult(v6, v5 - 1, &pullResult) < 0
                  || (v7 = (unsigned __int16 *)(*(_QWORD *)(a3 + 56) + pullResult),
                      (unsigned __int64)v7 < *(_QWORD *)(a3 + 56))
                  || !v7 )
                {
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"AslpPathWildcardPeekNode",
                    2079,
                    (unsigned int)"RtlArrayGet failed to get the next node",
                    IoStatusBlock);
                  v8 = "AslpPathWildcardPeekNode failed [%x]";
                  v9 = 2498;
                  v10 = -1073741595;
LABEL_51:
                  AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindNext", v9, (_DWORD)v8, v10);
                  goto LABEL_137;
                }
                if ( *((_QWORD *)v7 + 3) )
                  break;
                AslLogCallPrintf(
                  1,
                  (unsigned int)"AslPathWildcardFindNext",
                  2503,
                  (unsigned int)"Node on the stack with invalid handle.",
                  IoStatusBlock);
                v70 = *(_QWORD *)(a3 + 32);
                if ( !v70 )
                  goto LABEL_26;
                v20 = *(_QWORD *)(a3 + 24);
                pullResult = 0;
                if ( ULongLongMult(v20, v70 - 1, &pullResult) < 0 )
                  goto LABEL_29;
                v21 = *(_QWORD *)(a3 + 56) + pullResult;
                if ( v21 < *(_QWORD *)(a3 + 56) || !v21 )
                  goto LABEL_29;
                AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + pullResult);
                v72 = *(_QWORD *)(a3 + 32);
                if ( v72 )
                {
                  v43 = *(_QWORD *)(a3 + 24);
                  pullResult = 0;
                  if ( ULongLongMult(v43, v72 - 1, &pullResult) >= 0 )
                  {
                    v45 = (char *)(*(_QWORD *)(a3 + 56) + pullResult);
                    if ( (unsigned __int64)v45 >= *(_QWORD *)(a3 + 56) )
                    {
                      v46 = *(_QWORD *)(a3 + 32);
                      v47 = ~v44;
                      v73 = v47 + v46 == 0;
                      v48 = v47 + v46;
                      Size = v48;
                      if ( v73 )
                        goto LABEL_91;
                      if ( ULongLongMult(v48, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                      {
                        v50 = *(_QWORD *)(a3 + 24);
                        pullResult = 0;
                        if ( ULongLongMult(v50, v49, &pullResult) >= 0 )
                        {
                          v51 = (const void *)(*(_QWORD *)(a3 + 56) + pullResult);
                          if ( (unsigned __int64)v51 >= *(_QWORD *)(a3 + 56) )
                          {
                            v48 = Size;
LABEL_90:
                            memmove_0(v45, v51, v48);
LABEL_91:
                            memset_0(&v45[v48], 0, *(_QWORD *)(a3 + 24));
                            if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                            {
                              v67 = *(_QWORD *)(a3 + 40);
                              v68 = *(_QWORD *)(a3 + 24);
                              if ( v68 * v67 >= 0x400 && *(_QWORD *)(a3 + 32) < v67 >> 2 )
                              {
                                Size = 0;
                                if ( ULongLongMult(v67, v68, &pullResult) >= 0 )
                                {
                                  v52 = v67 >> 1;
                                  if ( ULongLongMult(v52, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                                  {
                                    v53 = *(void **)(a3 + 56);
                                    v54 = Size;
                                    v55 = *(void **)(a3 + 16);
                                    if ( v53 )
                                    {
                                      Heap = RtlReAllocateHeap(v55, 0, v53, Size);
                                    }
                                    else
                                    {
                                      v56 = RtlAllocateHeap(v55, 0, Size);
                                      Heap = v56;
                                      if ( v56 )
                                        memset_0(v56, 0, v54);
                                    }
                                    if ( Heap )
                                    {
                                      *(_QWORD *)(a3 + 56) = Heap;
                                      *(_QWORD *)(a3 + 40) = v52;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v7 + 2));
              v11 = ZwQueryDirectoryFile(
                      *((HANDLE *)v7 + 3),
                      0,
                      0,
                      0,
                      &v87,
                      FileInformation,
                      0x268u,
                      FileBothDirectoryInformation,
                      1u,
                      &DestinationString,
                      0);
              if ( v11 >= 0 )
                break;
              if ( v11 != -2147483642 && v11 != -1073741809 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"AslPathWildcardFindNext",
                  2527,
                  (unsigned int)"NtQueryDirectoryFile failed to query next file [%x]",
                  v11);
                AslLogCallPrintf(
                  2,
                  (unsigned int)"AslPathWildcardFindNext",
                  2528,
                  (unsigned int)"FilePath: '%ws'  Pattern: '%ws'",
                  *((_QWORD *)v7 + 1));
              }
              v18 = *(_QWORD *)(a3 + 32);
              if ( !v18 )
              {
LABEL_26:
                v19 = 26;
                goto LABEL_30;
              }
              v58 = *(_QWORD *)(a3 + 24);
              Size = 0;
              if ( ULongLongMult(v58, v18 - 1, &Size) >= 0
                && (v59 = *(_QWORD *)(a3 + 56) + Size, v59 >= *(_QWORD *)(a3 + 56))
                && v59 )
              {
                AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + Size);
                v60 = *(_QWORD *)(a3 + 32);
                if ( v60 )
                {
                  v61 = *(_QWORD *)(a3 + 24);
                  Size = 0;
                  if ( ULongLongMult(v61, v60 - 1, &Size) >= 0 )
                  {
                    v45 = (char *)(*(_QWORD *)(a3 + 56) + Size);
                    if ( (unsigned __int64)v45 >= *(_QWORD *)(a3 + 56) )
                    {
                      v63 = *(_QWORD *)(a3 + 32);
                      v64 = ~v62;
                      v73 = v64 + v63 == 0;
                      v48 = v64 + v63;
                      pullResult = v48;
                      if ( v73 )
                        goto LABEL_91;
                      if ( ULongLongMult(v48, *(_QWORD *)(a3 + 24), &pullResult) >= 0 )
                      {
                        v66 = *(_QWORD *)(a3 + 24);
                        Size = 0;
                        if ( ULongLongMult(v66, v65, &Size) >= 0 )
                        {
                          v51 = (const void *)(*(_QWORD *)(a3 + 56) + Size);
                          if ( (unsigned __int64)v51 >= *(_QWORD *)(a3 + 56) )
                          {
                            v48 = pullResult;
                            goto LABEL_90;
                          }
                        }
                      }
                    }
                  }
                }
              }
              else
              {
LABEL_29:
                v19 = -27;
                AslLogCallPrintf(
                  1,
                  (unsigned int)"AslpPathWildcardPeekNode",
                  2079,
                  (unsigned int)"RtlArrayGet failed to get the next node",
                  IoStatusBlock);
LABEL_30:
                AslLogCallPrintf(
                  1,
                  (unsigned int)"AslpPathWildcardPopNode",
                  2106,
                  (unsigned int)"AslpPathWildcardPeekNode failed [%x]",
                  v19);
              }
            }
            Buffer = (PWSTR)(FileInformation + 94);
            if ( *((_DWORD *)FileInformation + 15) == 4 )
            {
              if ( *Buffer != 46 )
                break;
              v73 = *((_WORD *)FileInformation + 48) == 46;
            }
            else
            {
              if ( *((_DWORD *)FileInformation + 15) != 2 )
                break;
              Buffer = (PWSTR)(FileInformation + 94);
              v73 = *((_WORD *)FileInformation + 47) == 46;
            }
          }
          while ( v73 );
          matched = AslpPathWildcardAllocMatchNode(
                      (unsigned int)&v85,
                      (_DWORD)v7,
                      *((_QWORD *)v7 + 2),
                      (*((_DWORD *)FileInformation + 14) >> 4) & 1,
                      (__int64)Buffer,
                      *((_WORD *)FileInformation + 30));
          if ( matched != -1073741197 )
            break;
          v14 = *((_WORD *)FileInformation + 30) + *v7;
          if ( v14 >= *v7 && (unsigned __int16)(v14 + 2) >= v14 )
          {
            v15 = 2;
            Path.ByteBuffer.StaticSize = 2;
            Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
            p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
            v17 = (unsigned __int16)(v14 + 2) + 2LL;
            Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
            Path.ByteBuffer.Size = 2;
            LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
            Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
            *(_DWORD *)&Path.String.Length = 0x20000;
            if ( v17 > 0xFFFE )
            {
              v10 = -1073741562;
              goto LABEL_20;
            }
            if ( v17 > 2 )
            {
              if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v17) < 0 )
              {
                v10 = -1073741801;
LABEL_20:
                v8 = "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]";
                v9 = 2638;
                goto LABEL_51;
              }
              v15 = Path.ByteBuffer.Size;
              p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
            }
            Path.String.Buffer = p_ReservedForAllocatedSize;
            Length = 0;
            Path.String.MaximumLength = v15;
            Path.String.Length = 0;
            v34 = *v7 + 2LL;
            if ( v34 > 0xFFFE )
            {
              v10 = -1073741562;
              goto LABEL_45;
            }
            if ( v34 > v15 )
            {
              if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v34) < 0 )
              {
                v10 = -1073741801;
LABEL_45:
                v8 = "RtlAssignUnicodeStringBuffer failed [%x]";
                v9 = 2648;
                goto LABEL_51;
              }
              p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
              Length = Path.String.Length;
            }
            Path.String.Buffer = p_ReservedForAllocatedSize;
            memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v7 + 1), *v7);
            Path.String.MaximumLength = *v7 + Path.String.Length + 2;
            Path.String.Length += *v7;
            Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
            if ( *(_WORD *)(*((_QWORD *)v7 + 1) + 2 * ((unsigned __int64)*v7 >> 1) - 2) == 92 )
            {
LABEL_47:
              v35 = Path.String.Length;
              DestinationString.Buffer = Buffer;
              DestinationString.Length = *((_WORD *)FileInformation + 30);
              v36 = DestinationString.Length;
              DestinationString.MaximumLength = *((_WORD *)FileInformation + 30);
              v37 = Path.String.Length + (unsigned int)DestinationString.Length + 2LL;
              if ( v37 > 0xFFFE )
              {
                v10 = -1073741562;
LABEL_50:
                v8 = "RtlAppendUnicodeStringBuffer failed [%x]";
                v9 = 2670;
                goto LABEL_51;
              }
              if ( v37 > Path.ByteBuffer.Size )
              {
                if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v37) < 0 )
                {
                  v10 = -1073741801;
                  goto LABEL_50;
                }
                Buffer = DestinationString.Buffer;
                v36 = DestinationString.Length;
                v35 = Path.String.Length;
              }
              Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
              memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v35 >> 1)], Buffer, v36);
              v41 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
              Path.String.Length = v41;
              Path.String.MaximumLength = v41 + 2;
              Path.String.Buffer[v41 >> 1] = 0;
              if ( *(_DWORD *)a3 && (v42 = RtlNtPathNameToDosPathName(0, &Path, 0, 0), v10 = v42, v42 < 0) )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"AslPathWildcardFindNext",
                  2681,
                  (unsigned int)"RtlNtPathNameToDosPathName failed [%x]",
                  v42);
              }
              else
              {
                v78 = RtlStringCbCopyNW(*(_QWORD *)&UnicodeString.Length, 520, Path.String.Buffer, Path.String.Length);
                v10 = v78;
                if ( v78 >= 0 )
                  v10 = 0;
                else
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"AslPathWildcardFindNext",
                    2692,
                    (unsigned int)"RtlStringCbCopyNW failed [%x]",
                    v78);
              }
              goto LABEL_137;
            }
            v38 = Path.String.Length;
            v39 = (unsigned int)Path.String.Length + 2 + 2LL;
            if ( v39 <= 0xFFFE )
            {
              if ( v39 > Path.ByteBuffer.Size )
              {
                if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v39) < 0 )
                {
                  v10 = -1073741801;
LABEL_56:
                  v8 = "RtlAppendUnicodeStringBuffer failed [%x]";
                  v9 = 2655;
                  goto LABEL_51;
                }
                v38 = Path.String.Length;
              }
              Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
              *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v38 >> 1)] = Source[0];
              v40 = Path.String.Length + 4;
              Path.String.Length += 2;
              Path.String.MaximumLength = v40;
              Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
              goto LABEL_47;
            }
            v10 = -1073741562;
            goto LABEL_56;
          }
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindNext",
            2629,
            (unsigned int)"Failed to compute the path length [%x]",
            149);
        }
      }
      while ( matched == -1073741565 || matched == -1073741638 );
      if ( matched >= 0 )
        break;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindNext",
        2585,
        (unsigned int)"AslpPathWildcardAllocMatchNode failed [%x]",
        matched);
    }
    v22 = *(_QWORD *)(a3 + 32);
    if ( v22 >= *(_QWORD *)(a3 + 40) )
      break;
LABEL_64:
    Size = 0;
    if ( !is_mul_ok(*(_QWORD *)(a3 + 24), v22)
      || (v69 = (_OWORD *)(*(_QWORD *)(a3 + 56) + *(_QWORD *)(a3 + 24) * v22),
          (unsigned __int64)v69 < *(_QWORD *)(a3 + 56)) )
    {
      v32 = -107;
      v10 = -1073741675;
      goto LABEL_66;
    }
    *v69 = v85;
    v69[1] = v86;
    ++*(_QWORD *)(a3 + 32);
  }
  v23 = v22 + 1;
  if ( v22 + 1 <= *(_QWORD *)(a3 + 40) )
  {
    v10 = -1073741811;
    goto LABEL_40;
  }
  v24 = *(_QWORD *)(a3 + 48) - 1LL;
  if ( v24 + v23 < v23 )
    goto LABEL_39;
  v25 = *(_QWORD *)(a3 + 40);
  v26 = *(_QWORD *)(a3 + 24);
  Size = 0;
  if ( !is_mul_ok(v25, v26)
    || (v27 = *(_QWORD *)(a3 + 24),
        v28 = (v24 + v23) & ~v24,
        Size = (v25 * (unsigned __int128)v26) >> 64,
        v30 = v27,
        v29 = v28 * v27,
        v31 = v29,
        !is_mul_ok(v28, v30)) )
  {
LABEL_39:
    v10 = -1073741675;
    goto LABEL_40;
  }
  v74 = *(void **)(a3 + 56);
  v75 = *(void **)(a3 + 16);
  if ( v74 )
  {
    v77 = RtlReAllocateHeap(v75, 0, v74, v29);
  }
  else
  {
    v76 = RtlAllocateHeap(v75, 0, v29);
    v77 = v76;
    if ( v76 )
      memset_0(v76, 0, v31);
  }
  if ( v77 )
  {
    *(_QWORD *)(a3 + 40) = v28;
    *(_QWORD *)(a3 + 56) = v77;
    goto LABEL_64;
  }
  v10 = -1073741801;
LABEL_40:
  v32 = v10;
LABEL_66:
  AslLogCallPrintf(
    1,
    (unsigned int)"AslPathWildcardFindNext",
    2577,
    (unsigned int)"AslpPathWildcardPushNode failed [%x]",
    v32);
LABEL_137:
  AslFree(NtCurrentPeb()->ProcessHeap, FileInformation);
LABEL_138:
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
  return v10;
}

```

## disassembly

```asm
0x180034c90  mov     [rsp-8+arg_8], rbx
0x180034c95  mov     [rsp-8+arg_18], rsi
0x180034c9a  push    rbp
0x180034c9b  push    rdi
0x180034c9c  push    r13
0x180034c9e  push    r14
0x180034ca0  push    r15
0x180034ca2  lea     rbp, [rsp-37h]
0x180034ca7  sub     rsp, 100h
0x180034cae  mov     rax, cs:__security_cookie
0x180034cb5  xor     rax, rsp
0x180034cb8  mov     [rbp+57h+Path.ByteBuffer.ReservedForIMalloc], rax
0x180034cbc  mov     qword ptr [rbp+57h+UnicodeString.Length], rcx
0x180034cc0  mov     rdi, r8
0x180034cc3  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180034cc7  jz      loc_1800355D8
0x180034ccd  xor     r15d, r15d
0x180034cd0  test    rcx, rcx
0x180034cd3  jz      loc_1800355E2
0x180034cd9  test    r8, r8
0x180034cdc  jz      loc_1800355EC
0x180034ce2  xorps   xmm1, xmm1
0x180034ce5  xorps   xmm0, xmm0
0x180034ce8  xor     eax, eax
0x180034cea  mov     r8d, 268h; Size
0x180034cf0  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180034cf4  mov     [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x180034cf8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180034cfc  lea     edx, [rax+8]; Flags
0x180034cff  movups  [rbp+57h+var_90], xmm0
0x180034d03  movups  [rbp+57h+var_80], xmm0
0x180034d07  movups  xmmword ptr [rbp+57h+Path.String.Length], xmm1
0x180034d0b  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer], xmm1
0x180034d0f  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size], xmm1
0x180034d13  mov     rcx, gs:60h
0x180034d1c  mov     rcx, [rcx+30h]; HeapHandle
0x180034d20  call    cs:__imp_RtlAllocateHeap
0x180034d27  nop     dword ptr [rax+rax+00h]
0x180034d2c  mov     r13, rax
0x180034d2f  test    rax, rax
0x180034d32  jz      loc_1800355F6
0x180034d38  lea     r14d, [r15+2]
0x180034d3c  mov     esi, 4
0x180034d41  mov     rax, [rdi+20h]
0x180034d45  cmp     rax, 1
0x180034d49  jb      loc_1800357AA
0x180034d4f  lea     rdx, [rax-1]; ullMultiplier
0x180034d53  cmp     rdx, rax
0x180034d56  jnb     short loc_180034D7F
0x180034d58  mov     rcx, [rdi+18h]; ullMultiplicand
0x180034d5c  lea     r8, [rbp+57h+pullResult]; pullResult
0x180034d60  mov     [rbp+57h+pullResult], r15
0x180034d64  call    ULongLongMult
0x180034d69  test    eax, eax
0x180034d6b  js      short loc_180034D7F
0x180034d6d  mov     rbx, [rbp+57h+pullResult]
0x180034d71  add     rbx, [rdi+38h]
0x180034d75  cmp     rbx, [rdi+38h]
0x180034d79  jnb     loc_180035600
0x180034d7f  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x180034d86  mov     r8d, 81Fh
0x180034d8c  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180034d93  mov     ecx, 1
0x180034d98  call    AslLogCallPrintf
0x180034d9d  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180034da4  mov     r8d, 9C2h
0x180034daa  mov     ebx, 0C00000E5h
0x180034daf  jmp     loc_1800351B1
0x180034db4  cmp     [rbx+18h], r15
0x180034db8  jz      loc_18003559A
0x180034dbe  mov     rdx, [rbx+10h]; SourceString
0x180034dc2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180034dc6  call    cs:__imp_RtlInitUnicodeString
0x180034dcd  nop     dword ptr [rax+rax+00h]
0x180034dd2  mov     rcx, [rbx+18h]; FileHandle
0x180034dd6  lea     rax, [rbp+57h+DestinationString]
0x180034dda  mov     [rsp+120h+RestartScan], r15b; RestartScan
0x180034ddf  xor     r9d, r9d; ApcContext
0x180034de2  mov     [rsp+120h+FileName], rax; FileName
0x180034de7  xor     r8d, r8d; ApcRoutine
0x180034dea  mov     [rsp+120h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180034def  lea     rax, [rbp+57h+var_70]
0x180034df3  mov     [rsp+120h+FileInformationClass], 3; FileInformationClass
0x180034dfb  xor     edx, edx; Event
0x180034dfd  mov     [rsp+120h+Length], 268h; Length
0x180034e05  mov     [rsp+120h+FileInformation], r13; FileInformation
0x180034e0a  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x180034e0f  call    cs:__imp_ZwQueryDirectoryFile
0x180034e16  nop     dword ptr [rax+rax+00h]
0x180034e1b  test    eax, eax
0x180034e1d  js      loc_180034F3C
0x180034e23  cmp     [r13+3Ch], esi
0x180034e27  lea     rsi, [r13+5Eh]
0x180034e2b  jz      loc_180035675
0x180034e31  cmp     [r13+3Ch], r14d
0x180034e35  jz      loc_180035687
0x180034e3b  mov     r9d, [r13+38h]
0x180034e3f  lea     rcx, [rbp+57h+var_90]
0x180034e43  movzx   eax, word ptr [r13+3Ch]
0x180034e48  mov     rdx, rbx
0x180034e4b  mov     r8, [rbx+10h]
0x180034e4f  shr     r9d, 4
0x180034e53  mov     word ptr [rsp+120h+FileInformation], ax
0x180034e58  and     r9d, 1
0x180034e5c  mov     [rsp+120h+IoStatusBlock], rsi
0x180034e61  call    AslpPathWildcardAllocMatchNode
0x180034e66  cmp     eax, 0C0000273h
0x180034e6b  jnz     loc_180035020
0x180034e71  movzx   eax, word ptr [rbx]
0x180034e74  add     ax, [r13+3Ch]
0x180034e79  cmp     ax, [rbx]
0x180034e7c  jb      loc_180034F11
0x180034e82  lea     r8d, [r14+rax]
0x180034e86  cmp     r8w, ax
0x180034e8a  jb      loc_180034F11
0x180034e90  lea     rax, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180034e94  movzx   r8d, r8w
0x180034e98  mov     rdx, r14
0x180034e9b  mov     [rbp+57h+Path.ByteBuffer.StaticSize], r14
0x180034e9f  mov     [rbp+57h+Path.ByteBuffer.StaticBuffer], rax
0x180034ea3  lea     rcx, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180034ea7  add     r8, 2; RequiredSize
0x180034eab  mov     [rbp+57h+Path.ByteBuffer.Buffer], rcx
0x180034eaf  mov     r14d, 0FFFEh
0x180034eb5  mov     [rbp+57h+Path.ByteBuffer.Size], rdx
0x180034eb9  mov     word ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], r15w
0x180034ebe  lea     rax, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180034ec2  mov     [rbp+57h+Path.String.Buffer], rax
0x180034ec6  mov     dword ptr [rbp+57h+Path.String.Length], 20000h
0x180034ecd  cmp     r8, r14
0x180034ed0  ja      loc_18003572A
0x180034ed6  cmp     r8, 2
0x180034eda  jbe     loc_1800350BE
0x180034ee0  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x180034ee4  xor     ecx, ecx; Flags
0x180034ee6  call    cs:__imp_RtlpEnsureBufferSize
0x180034eed  nop     dword ptr [rax+rax+00h]
0x180034ef2  test    eax, eax
0x180034ef4  jns     loc_180035734
0x180034efa  mov     ebx, 0C0000017h
0x180034eff  lea     r9, aRtlensureunico; "RtlEnsureUnicodeStringBufferSizeBytes f"...
0x180034f06  mov     r8d, 0A4Eh
0x180034f0c  jmp     loc_1800351B1
0x180034f11  lea     r9, aFailedToComput; "Failed to compute the path length [%x]"
0x180034f18  mov     dword ptr [rsp+120h+IoStatusBlock], 0C0000095h
0x180034f20  mov     r8d, 0A45h
0x180034f26  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180034f2d  mov     ecx, 1
0x180034f32  call    AslLogCallPrintf
0x180034f37  jmp     loc_180034D3C
0x180034f3c  cmp     eax, 80000006h
0x180034f41  jz      short loc_180034F9A
0x180034f43  cmp     eax, 0C000000Fh
0x180034f48  jz      short loc_180034F9A
0x180034f4a  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x180034f51  mov     dword ptr [rsp+120h+IoStatusBlock], eax
0x180034f55  mov     r8d, 9DFh
0x180034f5b  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180034f62  mov     ecx, 1
0x180034f67  call    AslLogCallPrintf
0x180034f6c  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180034f70  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x180034f77  mov     [rsp+120h+FileInformation], rax
0x180034f7c  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180034f83  mov     rax, [rbx+8]
0x180034f87  mov     r8d, 9E0h
0x180034f8d  mov     ecx, r14d
0x180034f90  mov     [rsp+120h+IoStatusBlock], rax
0x180034f95  call    AslLogCallPrintf
0x180034f9a  mov     rax, [rdi+20h]
0x180034f9e  cmp     rax, 1
0x180034fa2  jnb     loc_180035663
0x180034fa8  mov     ebx, 8000001Ah
0x180034fad  jmp     short loc_180034FF9
0x180034faf  mov     rcx, [rdi+18h]; ullMultiplicand
0x180034fb3  lea     r8, [rbp+57h+pullResult]; pullResult
0x180034fb7  mov     [rbp+57h+pullResult], r15
0x180034fbb  call    ULongLongMult
0x180034fc0  test    eax, eax
0x180034fc2  js      short loc_180034FD6
0x180034fc4  mov     rdx, [rbp+57h+pullResult]
0x180034fc8  add     rdx, [rdi+38h]
0x180034fcc  cmp     rdx, [rdi+38h]
0x180034fd0  jnb     loc_18003560E
0x180034fd6  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x180034fdd  mov     r8d, 81Fh
0x180034fe3  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180034fea  mov     ecx, 1
0x180034fef  mov     ebx, 0C00000E5h
0x180034ff4  call    AslLogCallPrintf
0x180034ff9  mov     dword ptr [rsp+120h+IoStatusBlock], ebx
0x180034ffd  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180035004  mov     r8d, 83Ah
0x18003500a  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x180035011  mov     ecx, 1
0x180035016  call    AslLogCallPrintf
0x18003501b  jmp     loc_180034D41
0x180035020  mov     esi, 4
0x180035025  cmp     eax, 0C0000103h
0x18003502a  jz      loc_180034D41
0x180035030  cmp     eax, 0C00000BAh
0x180035035  jz      loc_180034D41
0x18003503b  test    eax, eax
0x18003503d  js      loc_18003570D
0x180035043  mov     r15, [rdi+20h]
0x180035047  cmp     r15, [rdi+28h]
0x18003504b  jb      loc_1800352FE
0x180035051  lea     rcx, [r15+1]
0x180035055  cmp     rcx, [rdi+28h]
0x180035059  jbe     loc_18003569A
0x18003505f  mov     r14, [rdi+30h]
0x180035063  dec     r14
0x180035066  lea     r8, [r14+rcx]
0x18003506a  cmp     r8, rcx
0x18003506d  jb      short loc_1800350A1
0x18003506f  mov     rax, [rdi+18h]
0x180035073  mul     qword ptr [rdi+28h]
0x180035077  mov     [rbp+57h+Size], 0
0x18003507f  test    rdx, rdx
0x180035082  jnz     short loc_1800350A1
0x180035084  mov     rax, [rdi+18h]
0x180035088  not     r14
0x18003508b  and     r14, r8
0x18003508e  mov     [rbp+57h+Size], rdx
0x180035092  mul     r14
0x180035095  mov     rsi, rax
0x180035098  test    rdx, rdx
0x18003509b  jz      loc_1800356A4
0x1800350a1  mov     ebx, 0C0000095h
0x1800350a6  mov     r14d, 2
0x1800350ac  xor     r15d, r15d
0x1800350af  mov     eax, ebx
0x1800350b1  test    ebx, ebx
0x1800350b3  jns     loc_180034D3C
0x1800350b9  jmp     loc_180035322
0x1800350be  mov     [rbp+57h+Path.String.Buffer], rcx
0x1800350c2  mov     r9d, r15d
0x1800350c5  mov     [rbp+57h+Path.String.MaximumLength], dx
0x1800350c9  mov     [rbp+57h+Path.String.Length], r15w
0x1800350ce  movzx   r8d, word ptr [rbx]
0x1800350d2  add     r8, 2; RequiredSize
0x1800350d6  cmp     r8, r14
0x1800350d9  ja      loc_180035741
0x1800350df  cmp     r8, rdx
0x1800350e2  jbe     short loc_180035115
0x1800350e4  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x1800350e8  xor     ecx, ecx; Flags
0x1800350ea  call    cs:__imp_RtlpEnsureBufferSize
0x1800350f1  nop     dword ptr [rax+rax+00h]
0x1800350f6  test    eax, eax
0x1800350f8  jns     loc_18003574B
0x1800350fe  mov     ebx, 0C0000017h
0x180035103  lea     r9, aRtlassignunico; "RtlAssignUnicodeStringBuffer failed [%x"...
0x18003510a  mov     r8d, 0A58h
0x180035110  jmp     loc_1800351B1
0x180035115  mov     [rbp+57h+Path.String.Buffer], rcx
0x180035119  movzx   r8d, word ptr [rbx]; Size
0x18003511d  mov     rdx, [rbx+8]; Src
0x180035121  movzx   eax, r9w
0x180035125  shr     rax, 1
0x180035128  lea     rcx, [rcx+rax*2]; void *
0x18003512c  call    memmove_0
0x180035131  movzx   ecx, [rbp+57h+Path.String.Length]
0x180035135  lea     eax, [rcx+2]
0x180035138  add     ax, [rbx]
0x18003513b  mov     [rbp+57h+Path.String.MaximumLength], ax
0x18003513f  add     cx, [rbx]
0x180035142  mov     rax, [rbp+57h+Path.String.Buffer]
0x180035146  movzx   edx, cx
0x180035149  mov     [rbp+57h+Path.String.Length], dx
0x18003514d  shr     rdx, 1
0x180035150  mov     [rax+rdx*2], r15w
0x180035155  movzx   ecx, word ptr [rbx]
0x180035158  mov     rax, [rbx+8]
0x18003515c  mov     ebx, 2
0x180035161  shr     rcx, 1
0x180035164  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18003516a  jnz     short loc_1800351CB
0x18003516c  movzx   r9d, [rbp+57h+Path.String.Length]
0x180035171  mov     [rbp+57h+DestinationString.Buffer], rsi
0x180035175  movzx   edx, word ptr [r13+3Ch]
0x18003517a  mov     [rbp+57h+DestinationString.Length], dx
0x18003517e  movzx   eax, word ptr [r13+3Ch]
0x180035183  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x180035187  lea     r8d, [r9+rdx]
0x18003518b  add     r8, 2; RequiredSize
0x18003518f  cmp     r8, r14
0x180035192  jbe     loc_180035763
0x180035198  mov     ebx, 0C0000106h
0x18003519d  jmp     short loc_1800351A4
0x18003519f  mov     ebx, 0C0000017h
0x1800351a4  lea     r9, aRtlappendunico_0; "RtlAppendUnicodeStringBuffer failed [%x"...
0x1800351ab  mov     r8d, 0A6Eh
0x1800351b1  mov     dword ptr [rsp+120h+IoStatusBlock], ebx
0x1800351b5  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800351bc  mov     ecx, 1
0x1800351c1  call    AslLogCallPrintf
0x1800351c6  jmp     loc_1800357AF
0x1800351cb  movzx   ecx, [rbp+57h+Path.String.Length]
0x1800351cf  lea     r8d, [rbx+rcx]
  ... truncated ...
```
