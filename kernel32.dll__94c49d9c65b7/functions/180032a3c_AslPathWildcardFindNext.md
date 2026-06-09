# AslPathWildcardFindNext

- ea: `0x180032a3c`
- end: `0x18003357f`
- name: `AslPathWildcardFindNext`
- size: `2883`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18004a8d8`
- `0x180078100`

## callees

- `0x180021144`
- `0x1800212e4`
- `0x180032a3c`
- `0x180033588`
- `0x18004e1b4`
- `0x180055710`
- `0x18005c390`
- `0x180070bcc`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180032c7c`
- `ntdll!RtlpEnsureBufferSize` at `0x180032e7a`
- `ntdll!RtlpEnsureBufferSize` at `0x180032f75`
- `ntdll!RtlpEnsureBufferSize` at `0x180032fdf`
- `ntdll!RtlpEnsureBufferSize` at `0x180032c7c`
- `ntdll!RtlpEnsureBufferSize` at `0x180032e7a`
- `ntdll!RtlpEnsureBufferSize` at `0x180032f75`
- `ntdll!RtlpEnsureBufferSize` at `0x180032fdf`
- `ntdll!RtlFreeUnicodeString` at `0x180033542`
- `ntdll!RtlFreeUnicodeString` at `0x180033542`
- `ntdll!RtlReAllocateHeap` at `0x1800333aa`
- `ntdll!RtlReAllocateHeap` at `0x180033442`
- `ntdll!RtlReAllocateHeap` at `0x1800333aa`
- `ntdll!RtlReAllocateHeap` at `0x180033442`
- `ntdll!ZwQueryDirectoryFile` at `0x180032baf`
- `ntdll!ZwQueryDirectoryFile` at `0x180032baf`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180033050`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180033050`
- `ntdll!RtlInitUnicodeString` at `0x180032b6c`
- `ntdll!RtlInitUnicodeString` at `0x180032b6c`
- `ntdll!RtlAllocateHeap` at `0x180032acc`
- `ntdll!RtlAllocateHeap` at `0x18003318e`
- `ntdll!RtlAllocateHeap` at `0x180033422`
- `ntdll!RtlAllocateHeap` at `0x180032acc`
- `ntdll!RtlAllocateHeap` at `0x18003318e`
- `ntdll!RtlAllocateHeap` at `0x180033422`

## string_xrefs

- `0x180032cb6`: `AslPathWildcardFindNext`
- `0x180032ceb`: `AslPathWildcardFindNext`
- `0x180032d0c`: `AslPathWildcardFindNext`
- `0x180032f3f`: `AslPathWildcardFindNext`
- `0x180033319`: `AslPathWildcardFindNext`
- `0x18003347e`: `AslPathWildcardFindNext`
- `0x180033064`: `RtlNtPathNameToDosPathName failed [%x]`
- `0x180032ca1`: `Failed to compute the path length [%x]`
- `0x180032b32`: `AslpPathWildcardPeekNode`
- `0x180032d73`: `AslpPathWildcardPeekNode`
- `0x18003309e`: `AslpPathWildcardPushNode failed [%x]`
- `0x180032d00`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x180032cda`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x180032b43`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180032d8d`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180032d9a`: `AslpPathWildcardPopNode`
- `0x1800334f3`: `RtlStringCbCopyNW failed [%x]`
- `0x180033471`: `AslpPathWildcardAllocMatchNode failed [%x]`

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
0x180032a3c  mov     [rsp-8+arg_8], rbx
0x180032a41  mov     [rsp-8+arg_18], rsi
0x180032a46  push    rbp
0x180032a47  push    rdi
0x180032a48  push    r13
0x180032a4a  push    r14
0x180032a4c  push    r15
0x180032a4e  lea     rbp, [rsp-37h]
0x180032a53  sub     rsp, 100h
0x180032a5a  mov     rax, cs:__security_cookie
0x180032a61  xor     rax, rsp
0x180032a64  mov     [rbp+57h+Path.ByteBuffer.ReservedForIMalloc], rax
0x180032a68  mov     qword ptr [rbp+57h+UnicodeString.Length], rcx
0x180032a6c  mov     rdi, r8
0x180032a6f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180032a73  jz      loc_18003334A
0x180032a79  xor     r15d, r15d
0x180032a7c  test    rcx, rcx
0x180032a7f  jz      loc_180033354
0x180032a85  test    r8, r8
0x180032a88  jz      loc_18003335E
0x180032a8e  xorps   xmm1, xmm1
0x180032a91  xorps   xmm0, xmm0
0x180032a94  xor     eax, eax
0x180032a96  mov     r8d, 268h; Size
0x180032a9c  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180032aa0  mov     [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x180032aa4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180032aa8  lea     edx, [rax+8]; Flags
0x180032aab  movups  [rbp+57h+var_90], xmm0
0x180032aaf  movups  [rbp+57h+var_80], xmm0
0x180032ab3  movups  xmmword ptr [rbp+57h+Path.String.Length], xmm1
0x180032ab7  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer], xmm1
0x180032abb  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size], xmm1
0x180032abf  mov     rcx, gs:60h
0x180032ac8  mov     rcx, [rcx+30h]; HeapHandle
0x180032acc  call    cs:__imp_RtlAllocateHeap
0x180032ad2  mov     r13, rax
0x180032ad5  test    rax, rax
0x180032ad8  jz      loc_180033368
0x180032ade  lea     r14d, [r15+2]
0x180032ae2  mov     esi, 4
0x180032ae7  mov     rax, [rdi+20h]
0x180032aeb  cmp     rax, 1
0x180032aef  jb      loc_18003350A
0x180032af5  lea     rdx, [rax-1]; ullMultiplier
0x180032af9  cmp     rdx, rax
0x180032afc  jnb     short loc_180032B25
0x180032afe  mov     rcx, [rdi+18h]; ullMultiplicand
0x180032b02  lea     r8, [rbp+57h+pullResult]; pullResult
0x180032b06  mov     [rbp+57h+pullResult], r15
0x180032b0a  call    ULongLongMult
0x180032b0f  test    eax, eax
0x180032b11  js      short loc_180032B25
0x180032b13  mov     rbx, [rbp+57h+pullResult]
0x180032b17  add     rbx, [rdi+38h]
0x180032b1b  cmp     rbx, [rdi+38h]
0x180032b1f  jnb     loc_180033372
0x180032b25  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x180032b2c  mov     r8d, 81Fh
0x180032b32  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180032b39  mov     ecx, 1
0x180032b3e  call    AslLogCallPrintf
0x180032b43  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180032b4a  mov     r8d, 9C2h
0x180032b50  mov     ebx, 0C00000E5h
0x180032b55  jmp     loc_180032F3B
0x180032b5a  cmp     [rbx+18h], r15
0x180032b5e  jz      loc_18003330C
0x180032b64  mov     rdx, [rbx+10h]; SourceString
0x180032b68  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032b6c  call    cs:__imp_RtlInitUnicodeString
0x180032b72  mov     rcx, [rbx+18h]; FileHandle
0x180032b76  lea     rax, [rbp+57h+DestinationString]
0x180032b7a  mov     [rsp+120h+RestartScan], r15b; RestartScan
0x180032b7f  xor     r9d, r9d; ApcContext
0x180032b82  mov     [rsp+120h+FileName], rax; FileName
0x180032b87  xor     r8d, r8d; ApcRoutine
0x180032b8a  mov     [rsp+120h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180032b8f  lea     rax, [rbp+57h+var_70]
0x180032b93  mov     [rsp+120h+FileInformationClass], 3; FileInformationClass
0x180032b9b  xor     edx, edx; Event
0x180032b9d  mov     [rsp+120h+Length], 268h; Length
0x180032ba5  mov     [rsp+120h+FileInformation], r13; FileInformation
0x180032baa  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x180032baf  call    cs:__imp_ZwQueryDirectoryFile
0x180032bb5  test    eax, eax
0x180032bb7  js      loc_180032CCC
0x180032bbd  cmp     [r13+3Ch], esi
0x180032bc1  lea     rsi, [r13+5Eh]
0x180032bc5  jz      loc_1800333E1
0x180032bcb  cmp     [r13+3Ch], r14d
0x180032bcf  jz      loc_1800333F3
0x180032bd5  mov     r9d, [r13+38h]
0x180032bd9  lea     rcx, [rbp+57h+var_90]
0x180032bdd  movzx   eax, word ptr [r13+3Ch]
0x180032be2  mov     rdx, rbx
0x180032be5  mov     r8, [rbx+10h]
0x180032be9  shr     r9d, 4
0x180032bed  mov     word ptr [rsp+120h+FileInformation], ax
0x180032bf2  and     r9d, 1
0x180032bf6  mov     [rsp+120h+IoStatusBlock], rsi
0x180032bfb  call    AslpPathWildcardAllocMatchNode
0x180032c00  cmp     eax, 0C0000273h
0x180032c05  jnz     loc_180032DB0
0x180032c0b  movzx   eax, word ptr [rbx]
0x180032c0e  add     ax, [r13+3Ch]
0x180032c13  cmp     ax, [rbx]
0x180032c16  jb      loc_180032CA1
0x180032c1c  lea     r8d, [r14+rax]
0x180032c20  cmp     r8w, ax
0x180032c24  jb      short loc_180032CA1
0x180032c26  lea     rax, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180032c2a  movzx   r8d, r8w
0x180032c2e  mov     rdx, r14
0x180032c31  mov     [rbp+57h+Path.ByteBuffer.StaticSize], r14
0x180032c35  mov     [rbp+57h+Path.ByteBuffer.StaticBuffer], rax
0x180032c39  lea     rcx, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180032c3d  add     r8, 2; RequiredSize
0x180032c41  mov     [rbp+57h+Path.ByteBuffer.Buffer], rcx
0x180032c45  mov     r14d, 0FFFEh
0x180032c4b  mov     [rbp+57h+Path.ByteBuffer.Size], rdx
0x180032c4f  mov     word ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], r15w
0x180032c54  lea     rax, [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize]
0x180032c58  mov     [rbp+57h+Path.String.Buffer], rax
0x180032c5c  mov     dword ptr [rbp+57h+Path.String.Length], 20000h
0x180032c63  cmp     r8, r14
0x180032c66  ja      loc_18003348A
0x180032c6c  cmp     r8, 2
0x180032c70  jbe     loc_180032E4E
0x180032c76  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x180032c7a  xor     ecx, ecx; Flags
0x180032c7c  call    cs:__imp_RtlpEnsureBufferSize
0x180032c82  test    eax, eax
0x180032c84  jns     loc_180033494
0x180032c8a  mov     ebx, 0C0000017h
0x180032c8f  lea     r9, aRtlensureunico; "RtlEnsureUnicodeStringBufferSizeBytes f"...
0x180032c96  mov     r8d, 0A4Eh
0x180032c9c  jmp     loc_180032F3B
0x180032ca1  lea     r9, aFailedToComput; "Failed to compute the path length [%x]"
0x180032ca8  mov     dword ptr [rsp+120h+IoStatusBlock], 0C0000095h
0x180032cb0  mov     r8d, 0A45h
0x180032cb6  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180032cbd  mov     ecx, 1
0x180032cc2  call    AslLogCallPrintf
0x180032cc7  jmp     loc_180032AE2
0x180032ccc  cmp     eax, 80000006h
0x180032cd1  jz      short loc_180032D2A
0x180032cd3  cmp     eax, 0C000000Fh
0x180032cd8  jz      short loc_180032D2A
0x180032cda  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x180032ce1  mov     dword ptr [rsp+120h+IoStatusBlock], eax
0x180032ce5  mov     r8d, 9DFh
0x180032ceb  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180032cf2  mov     ecx, 1
0x180032cf7  call    AslLogCallPrintf
0x180032cfc  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180032d00  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x180032d07  mov     [rsp+120h+FileInformation], rax
0x180032d0c  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180032d13  mov     rax, [rbx+8]
0x180032d17  mov     r8d, 9E0h
0x180032d1d  mov     ecx, r14d
0x180032d20  mov     [rsp+120h+IoStatusBlock], rax
0x180032d25  call    AslLogCallPrintf
0x180032d2a  mov     rax, [rdi+20h]
0x180032d2e  cmp     rax, 1
0x180032d32  jnb     loc_1800333CF
0x180032d38  mov     ebx, 8000001Ah
0x180032d3d  jmp     short loc_180032D89
0x180032d3f  mov     rcx, [rdi+18h]; ullMultiplicand
0x180032d43  lea     r8, [rbp+57h+pullResult]; pullResult
0x180032d47  mov     [rbp+57h+pullResult], r15
0x180032d4b  call    ULongLongMult
0x180032d50  test    eax, eax
0x180032d52  js      short loc_180032D66
0x180032d54  mov     rdx, [rbp+57h+pullResult]
0x180032d58  add     rdx, [rdi+38h]
0x180032d5c  cmp     rdx, [rdi+38h]
0x180032d60  jnb     loc_180033380
0x180032d66  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x180032d6d  mov     r8d, 81Fh
0x180032d73  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180032d7a  mov     ecx, 1
0x180032d7f  mov     ebx, 0C00000E5h
0x180032d84  call    AslLogCallPrintf
0x180032d89  mov     dword ptr [rsp+120h+IoStatusBlock], ebx
0x180032d8d  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180032d94  mov     r8d, 83Ah
0x180032d9a  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x180032da1  mov     ecx, 1
0x180032da6  call    AslLogCallPrintf
0x180032dab  jmp     loc_180032AE7
0x180032db0  mov     esi, 4
0x180032db5  cmp     eax, 0C0000103h
0x180032dba  jz      loc_180032AE7
0x180032dc0  cmp     eax, 0C00000BAh
0x180032dc5  jz      loc_180032AE7
0x180032dcb  test    eax, eax
0x180032dcd  js      loc_18003346D
0x180032dd3  mov     r15, [rdi+20h]
0x180032dd7  cmp     r15, [rdi+28h]
0x180032ddb  jb      loc_180033076
0x180032de1  lea     rcx, [r15+1]
0x180032de5  cmp     rcx, [rdi+28h]
0x180032de9  jbe     loc_180033406
0x180032def  mov     r14, [rdi+30h]
0x180032df3  dec     r14
0x180032df6  lea     r8, [r14+rcx]
0x180032dfa  cmp     r8, rcx
0x180032dfd  jb      short loc_180032E31
0x180032dff  mov     rax, [rdi+18h]
0x180032e03  mul     qword ptr [rdi+28h]
0x180032e07  mov     [rbp+57h+Size], 0
0x180032e0f  test    rdx, rdx
0x180032e12  jnz     short loc_180032E31
0x180032e14  mov     rax, [rdi+18h]
0x180032e18  not     r14
0x180032e1b  and     r14, r8
0x180032e1e  mov     [rbp+57h+Size], rdx
0x180032e22  mul     r14
0x180032e25  mov     rsi, rax
0x180032e28  test    rdx, rdx
0x180032e2b  jz      loc_180033410
0x180032e31  mov     ebx, 0C0000095h
0x180032e36  mov     r14d, 2
0x180032e3c  xor     r15d, r15d
0x180032e3f  mov     eax, ebx
0x180032e41  test    ebx, ebx
0x180032e43  jns     loc_180032AE2
0x180032e49  jmp     loc_18003309A
0x180032e4e  mov     [rbp+57h+Path.String.Buffer], rcx
0x180032e52  mov     r9d, r15d
0x180032e55  mov     [rbp+57h+Path.String.MaximumLength], dx
0x180032e59  mov     [rbp+57h+Path.String.Length], r15w
0x180032e5e  movzx   r8d, word ptr [rbx]
0x180032e62  add     r8, 2; RequiredSize
0x180032e66  cmp     r8, r14
0x180032e69  ja      loc_1800334A1
0x180032e6f  cmp     r8, rdx
0x180032e72  jbe     short loc_180032E9F
0x180032e74  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x180032e78  xor     ecx, ecx; Flags
0x180032e7a  call    cs:__imp_RtlpEnsureBufferSize
0x180032e80  test    eax, eax
0x180032e82  jns     loc_1800334AB
0x180032e88  mov     ebx, 0C0000017h
0x180032e8d  lea     r9, aRtlassignunico; "RtlAssignUnicodeStringBuffer failed [%x"...
0x180032e94  mov     r8d, 0A58h
0x180032e9a  jmp     loc_180032F3B
0x180032e9f  mov     [rbp+57h+Path.String.Buffer], rcx
0x180032ea3  movzx   r8d, word ptr [rbx]; Size
0x180032ea7  mov     rdx, [rbx+8]; Src
0x180032eab  movzx   eax, r9w
0x180032eaf  shr     rax, 1
0x180032eb2  lea     rcx, [rcx+rax*2]; void *
0x180032eb6  call    memmove_0
0x180032ebb  movzx   ecx, [rbp+57h+Path.String.Length]
0x180032ebf  lea     eax, [rcx+2]
0x180032ec2  add     ax, [rbx]
0x180032ec5  mov     [rbp+57h+Path.String.MaximumLength], ax
0x180032ec9  add     cx, [rbx]
0x180032ecc  mov     rax, [rbp+57h+Path.String.Buffer]
0x180032ed0  movzx   edx, cx
0x180032ed3  mov     [rbp+57h+Path.String.Length], dx
0x180032ed7  shr     rdx, 1
0x180032eda  mov     [rax+rdx*2], r15w
0x180032edf  movzx   ecx, word ptr [rbx]
0x180032ee2  mov     rax, [rbx+8]
0x180032ee6  mov     ebx, 2
0x180032eeb  shr     rcx, 1
0x180032eee  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180032ef4  jnz     short loc_180032F55
0x180032ef6  movzx   r9d, [rbp+57h+Path.String.Length]
0x180032efb  mov     [rbp+57h+DestinationString.Buffer], rsi
0x180032eff  movzx   edx, word ptr [r13+3Ch]
0x180032f04  mov     [rbp+57h+DestinationString.Length], dx
0x180032f08  movzx   eax, word ptr [r13+3Ch]
0x180032f0d  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x180032f11  lea     r8d, [r9+rdx]
0x180032f15  add     r8, 2; RequiredSize
0x180032f19  cmp     r8, r14
0x180032f1c  jbe     loc_1800334C3
0x180032f22  mov     ebx, 0C0000106h
0x180032f27  jmp     short loc_180032F2E
0x180032f29  mov     ebx, 0C0000017h
0x180032f2e  lea     r9, aRtlappendunico_0; "RtlAppendUnicodeStringBuffer failed [%x"...
0x180032f35  mov     r8d, 0A6Eh
0x180032f3b  mov     dword ptr [rsp+120h+IoStatusBlock], ebx
0x180032f3f  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180032f46  mov     ecx, 1
0x180032f4b  call    AslLogCallPrintf
0x180032f50  jmp     loc_18003350F
0x180032f55  movzx   ecx, [rbp+57h+Path.String.Length]
0x180032f59  lea     r8d, [rbx+rcx]
0x180032f5d  add     r8, rbx; RequiredSize
0x180032f60  cmp     r8, r14
0x180032f63  ja      loc_1800334B9
0x180032f69  cmp     r8, [rbp+57h+Path.ByteBuffer.Size]
0x180032f6d  jbe     short loc_180032F97
  ... truncated ...
```
