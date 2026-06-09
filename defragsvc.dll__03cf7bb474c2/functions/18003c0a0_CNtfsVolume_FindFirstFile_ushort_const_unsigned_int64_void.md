# CNtfsVolume::_FindFirstFile(ushort const *,unsigned __int64 *,void * *)

- ea: `0x18003c0a0`
- end: `0x18003c6de`
- name: `?_FindFirstFile@CNtfsVolume@@AEAAJPEBGPEA_KPEAPEAX@Z`
- size: `1598`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, const unsigned __int16 *, unsigned __int64 *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ae04`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180039ae4`
- `0x18003c0a0`
- `0x18003d58c`
- `0x18003d8f4`
- `0x180061b48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c25a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c2a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c45c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c5d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c25a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c2a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c45c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c5d0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003c24b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003c24b`
- `ntdll!RtlIsDosDeviceName_U` at `0x18003c273`
- `ntdll!RtlIsDosDeviceName_U` at `0x18003c273`
- `ntdll!RtlReleaseRelativeName` at `0x18003c281`
- `ntdll!RtlReleaseRelativeName` at `0x18003c5a1`
- `ntdll!RtlReleaseRelativeName` at `0x18003c672`
- `ntdll!RtlReleaseRelativeName` at `0x18003c281`
- `ntdll!RtlReleaseRelativeName` at `0x18003c5a1`
- `ntdll!RtlReleaseRelativeName` at `0x18003c672`
- `ntdll!NtOpenFile` at `0x18003c3d7`
- `ntdll!NtOpenFile` at `0x18003c416`
- `ntdll!NtOpenFile` at `0x18003c3d7`
- `ntdll!NtOpenFile` at `0x18003c416`
- `ntdll!NtQueryDirectoryFileEx` at `0x18003c581`
- `ntdll!NtQueryDirectoryFileEx` at `0x18003c581`
- `ntdll!RtlInitializeCriticalSection` at `0x18003c621`
- `ntdll!RtlInitializeCriticalSection` at `0x18003c621`
- `ntdll!NtClose` at `0x18003c6ad`
- `ntdll!NtClose` at `0x18003c6ad`
- `ntdll!RtlInitUnicodeString` at `0x18003c217`
- `ntdll!RtlInitUnicodeString` at `0x18003c217`
- `ntdll!RtlNtStatusToDosError` at `0x18003c438`
- `ntdll!RtlNtStatusToDosError` at `0x18003c5c8`
- `ntdll!RtlNtStatusToDosError` at `0x18003c438`
- `ntdll!RtlNtStatusToDosError` at `0x18003c5c8`
- `ntdll!RtlFreeHeap` at `0x18003c299`
- `ntdll!RtlFreeHeap` at `0x18003c5b9`
- `ntdll!RtlFreeHeap` at `0x18003c68f`
- `ntdll!RtlFreeHeap` at `0x18003c299`
- `ntdll!RtlFreeHeap` at `0x18003c5b9`
- `ntdll!RtlFreeHeap` at `0x18003c68f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003c492`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18003c492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c52d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c52d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c5ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c595`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c698`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_FindFirstFile(
        CNtfsVolume *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3,
        void **a4)
{
  bool v8; // r15
  PWSTR Buffer; // rsi
  _QWORD *v10; // r14
  __int16 v11; // ax
  CNtfsVolume *v12; // rcx
  __int16 v13; // ax
  int FileIdFromFilePath; // ecx
  BOOLEAN v15; // al
  char v16; // bl
  USHORT Length; // cx
  __int16 v18; // ax
  PWSTR v19; // rdx
  unsigned int v20; // r8d
  NTSTATUS v21; // eax
  NTSTATUS v22; // ecx
  DWORD v23; // eax
  unsigned int v24; // edi
  unsigned int v25; // edx
  WCHAR *v26; // rcx
  _QWORD *v27; // rax
  NTSTATUS v28; // ebx
  DWORD v29; // eax
  char *v30; // rbx
  unsigned int v31; // ebx
  struct _UNICODE_STRING NtName; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR PartName[2]; // [rsp+60h] [rbp-A0h] BYREF
  int DoesPathContainWildCards; // [rsp+70h] [rbp-90h] BYREF
  __int16 v36; // [rsp+74h] [rbp-8Ch]
  __int16 v37; // [rsp+76h] [rbp-8Ah]
  void *FileHandle; // [rsp+A8h] [rbp-58h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  int v43; // [rsp+168h] [rbp+68h] BYREF
  int v44; // [rsp+178h] [rbp+78h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&DoesPathContainWildCards,
    "CNtfsVolume::_FindFirstFile",
    1908,
    1);
  FileHandle = (void *)-1LL;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  *(_OWORD *)PartName = 0;
  NtName = 0;
  v8 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  Buffer = 0;
  v10 = 0;
  v44 = 0;
  v43 = 0;
  v11 = 1930;
  if ( !a2 || (v36 = 1930, v11 = 1931, !a3) || (v36 = 1931, v11 = 1932, !a4) )
  {
    DoesPathContainWildCards = -2147024809;
    goto LABEL_80;
  }
  DoesPathContainWildCards = 0;
  v36 = 1932;
  *a4 = (void *)-1LL;
  *a3 = 0;
  DoesPathContainWildCards = CNtfsVolume::_DoesPathContainWildCards((CNtfsVolume *)0xFFFFFFFFFFFFFFFFLL, a2, &v44);
  v11 = 1937;
  if ( DoesPathContainWildCards < 0 )
  {
LABEL_80:
    v37 = v11;
    goto LABEL_81;
  }
  v36 = 1937;
  if ( v44 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    if ( DestinationString.Length )
      v8 = DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 46;
    v15 = RtlDosPathNameToRelativeNtPathName_U(a2, &NtName, &PartName[1], &RelativeName);
    v16 = 0;
    if ( !v15 )
    {
      SetLastError(3u);
      v13 = 1986;
      goto LABEL_9;
    }
    Buffer = NtName.Buffer;
    if ( RtlIsDosDeviceName_U(DestinationString.Buffer) )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      SetLastError(0x103u);
      v13 = 2003;
      goto LABEL_9;
    }
    Length = NtName.Length;
    if ( PartName[1] )
    {
      v18 = NtName.Length + LOWORD(NtName.Buffer) - LOWORD(PartName[1]);
      LOWORD(PartName[0]) = v18;
    }
    else
    {
      v18 = 0;
      LOWORD(PartName[0]) = 0;
    }
    WORD1(PartName[0]) = v18;
    if ( !RelativeName.RelativeName.Length
      || (v19 = RelativeName.RelativeName.Buffer, RelativeName.RelativeName.Buffer == PartName[1]) )
    {
      RelativeName.ContainingDirectory = 0;
      if ( PartName[1] )
      {
        Length = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
        NtName.Length = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
        NtName.MaximumLength = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
      }
    }
    else if ( PartName[1] )
    {
      Length = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
      NtName.Length = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
      NtName.MaximumLength = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
      NtName.Buffer = RelativeName.RelativeName.Buffer;
LABEL_29:
      v20 = Length >> 1;
      if ( v20 >= 2 && v19[v20 - 2] != 58 && v19[v20 - 1] == 92 )
        v16 = 1;
      DoesPathContainWildCards = CNtfsVolume::_IsFileOnVolume(this, &NtName, &v43);
      v11 = 2050;
      if ( DoesPathContainWildCards < 0 )
        goto LABEL_80;
      v36 = 2050;
      if ( !v43 )
      {
        v13 = 2054;
        goto LABEL_9;
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = RelativeName.ContainingDirectory;
      ObjectAttributes.Attributes = 0;
      ObjectAttributes.ObjectName = &NtName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v21 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
      if ( v16 && (v21 == -1073741811 || v21 == -1073741565) )
      {
        NtName.Length -= 2;
        v21 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
      }
      if ( v21 < 0 )
      {
        v22 = -1073741766;
        if ( v21 != -1073741772 )
        {
          if ( v21 == -1073741788 )
            v21 = -1073741766;
          v22 = v21;
        }
        v23 = RtlNtStatusToDosError(v22);
        SetLastError(v23);
        v13 = 2108;
        goto LABEL_9;
      }
      if ( !LOWORD(PartName[0]) )
      {
        SetLastError(2u);
        v13 = 2123;
        goto LABEL_9;
      }
      v24 = 616;
      if ( LOWORD(PartName[0]) == 6 && RtlCompareMemory(PartName[1], L"*.*", 6u) == 6 )
      {
        LOWORD(PartName[0]) = 2;
        goto LABEL_67;
      }
      v25 = 0;
      v26 = (WCHAR *)PartName[1];
      if ( ((__int64)PartName[0] & 0xFFFE) == 0 )
      {
LABEL_64:
        if ( v8 && *(v26 - 1) == 42 )
          *(v26 - 1) = 60;
        while ( 1 )
        {
LABEL_67:
          v27 = CoTaskMemAlloc(v24);
          v10 = v27;
          if ( !v27 )
          {
            DoesPathContainWildCards = -2147024882;
            v37 = 2170;
            goto LABEL_81;
          }
          DoesPathContainWildCards = 0;
          v36 = 2170;
          v28 = NtQueryDirectoryFileEx(FileHandle, 0, 0, 0, &IoStatusBlock, v27, v24, 60, 10, PartName);
          if ( v28 != -2147483643 )
            break;
          v24 *= 2;
          CoTaskMemFree(v10);
        }
        RtlReleaseRelativeName(&RelativeName);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
        if ( v28 < 0 )
        {
          Buffer = 0;
          v29 = RtlNtStatusToDosError(v28);
          SetLastError(v29);
          v13 = 2200;
          goto LABEL_9;
        }
        *a3 = v10[9];
        goto LABEL_73;
      }
      while ( 1 )
      {
        if ( v25 && *v26 == 46 && *(v26 - 1) == 42 )
          *(v26 - 1) = 60;
        if ( *v26 == 63 )
          break;
        if ( *v26 == 42 )
          goto LABEL_60;
LABEL_63:
        ++v25;
        ++v26;
        if ( v25 >= LOWORD(PartName[0]) >> 1 )
          goto LABEL_64;
      }
      *v26 = 62;
LABEL_60:
      if ( v25 && *(v26 - 1) == 46 )
        *(v26 - 1) = 34;
      goto LABEL_63;
    }
    v19 = NtName.Buffer;
    goto LABEL_29;
  }
  DoesPathContainWildCards = CNtfsVolume::_IsFileOnVolume(this, a2, &v43);
  v11 = 1942;
  if ( DoesPathContainWildCards < 0 )
    goto LABEL_80;
  v36 = 1942;
  if ( !v43 )
  {
    v13 = 1946;
LABEL_9:
    DoesPathContainWildCards = 1;
    v36 = v13;
    goto LABEL_81;
  }
  FileIdFromFilePath = CNtfsVolume::_GetFileIdFromFilePath(v12, a2, a3);
  DoesPathContainWildCards = FileIdFromFilePath;
  v11 = 1949;
  if ( FileIdFromFilePath < 0 )
    goto LABEL_80;
  v36 = 1949;
  if ( FileIdFromFilePath == 1 )
  {
    v13 = 1953;
    goto LABEL_9;
  }
LABEL_73:
  v30 = (char *)CoTaskMemAlloc(0x48u);
  v11 = 2207;
  if ( !v30 )
  {
    DoesPathContainWildCards = -2147024882;
    Buffer = 0;
    goto LABEL_80;
  }
  DoesPathContainWildCards = 0;
  v36 = 2207;
  *(_QWORD *)v30 = FileHandle;
  *((_QWORD *)v30 + 1) = 0;
  *((_QWORD *)v30 + 2) = 0;
  *((_DWORD *)v30 + 6) = 0;
  if ( RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v30 + 32)) < 0 )
  {
    CoTaskMemFree(v30);
    v30 = 0;
  }
  *a4 = v30;
  DoesPathContainWildCards = 0;
  Buffer = 0;
LABEL_81:
  RtlReleaseRelativeName(&RelativeName);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  CoTaskMemFree(v10);
  if ( a4 == (void **)-1LL && FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  v31 = DoesPathContainWildCards;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DoesPathContainWildCards);
  return v31;
}

```

## disassembly

```asm
0x18003c0a0  mov     [rsp-8+arg_0], rbx
0x18003c0a5  push    rbp
0x18003c0a6  push    rsi
0x18003c0a7  push    rdi
0x18003c0a8  push    r12
0x18003c0aa  push    r13
0x18003c0ac  push    r14
0x18003c0ae  push    r15
0x18003c0b0  lea     rbp, [rsp-20h]
0x18003c0b5  sub     rsp, 120h
0x18003c0bc  mov     r13, r9
0x18003c0bf  mov     r12, r8
0x18003c0c2  mov     rbx, rdx
0x18003c0c5  mov     rdi, rcx
0x18003c0c8  mov     r9d, 1; unsigned __int16
0x18003c0ce  mov     r8d, 774h; unsigned __int16
0x18003c0d4  lea     rdx, aCntfsvolumeFin_3; "CNtfsVolume::_FindFirstFile"
0x18003c0db  lea     rcx, [rsp+150h+var_E0]; this
0x18003c0e0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003c0e5  nop
0x18003c0e6  or      rcx, 0FFFFFFFFFFFFFFFFh; this
0x18003c0ea  mov     [rbp+50h+FileHandle], rcx
0x18003c0ee  xorps   xmm0, xmm0
0x18003c0f1  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x18003c0f5  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x18003c0f9  movups  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c0fd  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18003c101  xorps   xmm1, xmm1
0x18003c104  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x18003c108  movups  xmmword ptr [rsp+150h+PartName], xmm0
0x18003c10d  movups  xmmword ptr [rsp+150h+NtName.Length], xmm1
0x18003c112  xor     r15d, r15d
0x18003c115  mov     [rbp+50h+RelativeName.RelativeName.Length], r15w
0x18003c11a  movups  xmmword ptr [rbp+50h+RelativeName.RelativeName.MaximumLength], xmm0
0x18003c11e  movups  xmmword ptr [rbp+50h+RelativeName.ContainingDirectory], xmm0
0x18003c122  mov     esi, r15d
0x18003c125  mov     r14d, r15d
0x18003c128  mov     [rbp+50h+arg_18], r15d
0x18003c12c  mov     [rbp+50h+arg_8], r15d
0x18003c130  mov     eax, 78Ah
0x18003c135  test    rbx, rbx
0x18003c138  jz      loc_18003C661
0x18003c13e  mov     [rsp+150h+var_DC], ax
0x18003c143  mov     eax, 78Bh
0x18003c148  test    r12, r12
0x18003c14b  jz      loc_18003C661
0x18003c151  mov     [rsp+150h+var_DC], ax
0x18003c156  mov     eax, 78Ch
0x18003c15b  test    r13, r13
0x18003c15e  jz      loc_18003C661
0x18003c164  mov     [rsp+150h+var_E0], r15d
0x18003c169  mov     [rsp+150h+var_DC], ax
0x18003c16e  mov     [r13+0], rcx
0x18003c172  mov     [r12], r15
0x18003c176  lea     r8, [rbp+50h+arg_18]; int *
0x18003c17a  mov     rdx, rbx; unsigned __int16 *
0x18003c17d  call    ?_DoesPathContainWildCards@CNtfsVolume@@AEAAJPEBGPEAH@Z; CNtfsVolume::_DoesPathContainWildCards(ushort const *,int *)
0x18003c182  mov     [rsp+150h+var_E0], eax
0x18003c186  test    eax, eax
0x18003c188  mov     eax, 791h
0x18003c18d  js      loc_18003C669
0x18003c193  mov     [rsp+150h+var_DC], ax
0x18003c198  mov     rdx, rbx; unsigned __int16 *
0x18003c19b  cmp     [rbp+50h+arg_18], r15d
0x18003c19f  jnz     short loc_18003C213
0x18003c1a1  lea     r8, [rbp+50h+arg_8]; int *
0x18003c1a5  mov     rcx, rdi; this
0x18003c1a8  call    ?_IsFileOnVolume@CNtfsVolume@@AEAAJPEBGPEAH@Z; CNtfsVolume::_IsFileOnVolume(ushort const *,int *)
0x18003c1ad  mov     [rsp+150h+var_E0], eax
0x18003c1b1  test    eax, eax
0x18003c1b3  mov     eax, 796h
0x18003c1b8  js      loc_18003C669
0x18003c1be  mov     [rsp+150h+var_DC], ax
0x18003c1c3  cmp     [rbp+50h+arg_8], r15d
0x18003c1c7  jnz     short loc_18003C1E0
0x18003c1c9  mov     eax, 79Ah
0x18003c1ce  mov     [rsp+150h+var_E0], 1
0x18003c1d6  mov     [rsp+150h+var_DC], ax
0x18003c1db  jmp     loc_18003C66E
0x18003c1e0  mov     r8, r12; unsigned __int64 *
0x18003c1e3  mov     rdx, rbx; unsigned __int16 *
0x18003c1e6  call    ?_GetFileIdFromFilePath@CNtfsVolume@@AEAAJPEBGPEA_K@Z; CNtfsVolume::_GetFileIdFromFilePath(ushort const *,unsigned __int64 *)
0x18003c1eb  mov     ecx, eax
0x18003c1ed  mov     [rsp+150h+var_E0], eax
0x18003c1f1  test    eax, eax
0x18003c1f3  mov     eax, 79Dh
0x18003c1f8  js      loc_18003C669
0x18003c1fe  mov     [rsp+150h+var_DC], ax
0x18003c203  cmp     ecx, 1
0x18003c206  jnz     loc_18003C5E8
0x18003c20c  mov     eax, 7A1h
0x18003c211  jmp     short loc_18003C1CE
0x18003c213  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x18003c217  call    cs:__imp_RtlInitUnicodeString
0x18003c21d  movzx   eax, [rbp+50h+DestinationString.Length]
0x18003c221  test    ax, ax
0x18003c224  jz      short loc_18003C23A
0x18003c226  mov     ecx, eax
0x18003c228  shr     rcx, 1
0x18003c22b  mov     rax, [rbp+50h+DestinationString.Buffer]
0x18003c22f  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x18003c235  jnz     short loc_18003C23A
0x18003c237  mov     r15b, 1
0x18003c23a  lea     r9, [rbp+50h+RelativeName]; RelativeName
0x18003c23e  lea     r8, [rsp+150h+PartName+8]; PartName
0x18003c243  lea     rdx, [rsp+150h+NtName]; NtName
0x18003c248  mov     rcx, rbx; DosName
0x18003c24b  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18003c251  xor     ebx, ebx
0x18003c253  test    al, al
0x18003c255  jnz     short loc_18003C26A
0x18003c257  lea     ecx, [rbx+3]; dwErrCode
0x18003c25a  call    cs:__imp_SetLastError
0x18003c260  mov     eax, 7C2h
0x18003c265  jmp     loc_18003C1CE
0x18003c26a  mov     rsi, [rsp+150h+NtName.Buffer]
0x18003c26f  mov     rcx, [rbp+50h+DestinationString.Buffer]; Name
0x18003c273  call    cs:__imp_RtlIsDosDeviceName_U
0x18003c279  test    eax, eax
0x18003c27b  jz      short loc_18003C2B4
0x18003c27d  lea     rcx, [rbp+50h+RelativeName]; RelativeName
0x18003c281  call    cs:__imp_RtlReleaseRelativeName
0x18003c287  mov     rcx, gs:60h
0x18003c290  mov     r8, rsi; P
0x18003c293  xor     edx, edx; Flags
0x18003c295  mov     rcx, [rcx+30h]; HeapHandle
0x18003c299  call    cs:__imp_RtlFreeHeap
0x18003c29f  mov     ecx, 103h; dwErrCode
0x18003c2a4  call    cs:__imp_SetLastError
0x18003c2aa  mov     eax, 7D3h
0x18003c2af  jmp     loc_18003C1CE
0x18003c2b4  movzx   r9d, word ptr [rsp+150h+PartName+8]
0x18003c2ba  movzx   ecx, [rsp+150h+NtName.Length]
0x18003c2bf  mov     r8, [rsp+150h+PartName+8]
0x18003c2c4  test    r8, r8
0x18003c2c7  jz      short loc_18003C2DC
0x18003c2c9  movzx   eax, word ptr [rsp+150h+NtName.Buffer]
0x18003c2ce  sub     ax, r9w
0x18003c2d2  add     ax, cx
0x18003c2d5  mov     word ptr [rsp+150h+PartName], ax
0x18003c2da  jmp     short loc_18003C2E3
0x18003c2dc  mov     eax, ebx
0x18003c2de  mov     word ptr [rsp+150h+PartName], bx
0x18003c2e3  mov     word ptr [rsp+150h+PartName+2], ax
0x18003c2e8  cmp     [rbp+50h+RelativeName.RelativeName.Length], bx
0x18003c2ec  jz      short loc_18003C314
0x18003c2ee  mov     rdx, [rbp+50h+RelativeName.RelativeName.Buffer]
0x18003c2f2  cmp     rdx, r8
0x18003c2f5  jz      short loc_18003C314
0x18003c2f7  test    r8, r8
0x18003c2fa  jz      short loc_18003C330
0x18003c2fc  movzx   ecx, r9w
0x18003c300  sub     cx, dx
0x18003c303  mov     [rsp+150h+NtName.Length], cx
0x18003c308  mov     [rsp+150h+NtName.MaximumLength], cx
0x18003c30d  mov     [rsp+150h+NtName.Buffer], rdx
0x18003c312  jmp     short loc_18003C335
0x18003c314  mov     [rbp+50h+RelativeName.ContainingDirectory], rbx
0x18003c318  test    r8, r8
0x18003c31b  jz      short loc_18003C330
0x18003c31d  movzx   ecx, r9w
0x18003c321  sub     cx, word ptr [rsp+150h+NtName.Buffer]
0x18003c326  mov     [rsp+150h+NtName.Length], cx
0x18003c32b  mov     [rsp+150h+NtName.MaximumLength], cx
0x18003c330  mov     rdx, [rsp+150h+NtName.Buffer]
0x18003c335  movzx   r8d, cx
0x18003c339  shr     r8d, 1
0x18003c33c  cmp     r8d, 2
0x18003c340  jb      short loc_18003C35A
0x18003c342  lea     eax, [r8-2]
0x18003c346  cmp     word ptr [rdx+rax*2], 3Ah ; ':'
0x18003c34b  jz      short loc_18003C35A
0x18003c34d  lea     eax, [r8-1]
0x18003c351  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x18003c356  jnz     short loc_18003C35A
0x18003c358  mov     bl, 1
0x18003c35a  lea     r8, [rbp+50h+arg_8]; int *
0x18003c35e  lea     rdx, [rsp+150h+NtName]; struct _UNICODE_STRING *
0x18003c363  mov     rcx, rdi; this
0x18003c366  call    ?_IsFileOnVolume@CNtfsVolume@@AEAAJPEAU_UNICODE_STRING@@PEAH@Z; CNtfsVolume::_IsFileOnVolume(_UNICODE_STRING *,int *)
0x18003c36b  mov     [rsp+150h+var_E0], eax
0x18003c36f  test    eax, eax
0x18003c371  mov     eax, 802h
0x18003c376  js      loc_18003C669
0x18003c37c  mov     [rsp+150h+var_DC], ax
0x18003c381  cmp     [rbp+50h+arg_8], r14d
0x18003c385  jnz     short loc_18003C391
0x18003c387  mov     eax, 806h
0x18003c38c  jmp     loc_18003C1CE
0x18003c391  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x18003c398  mov     rax, [rbp+50h+RelativeName.ContainingDirectory]
0x18003c39c  mov     [rbp+50h+ObjectAttributes.RootDirectory], rax
0x18003c3a0  mov     [rbp+50h+ObjectAttributes.Attributes], r14d
0x18003c3a4  lea     rax, [rsp+150h+NtName]
0x18003c3a9  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x18003c3ad  xorps   xmm0, xmm0
0x18003c3b0  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c3b5  mov     edi, 4021h
0x18003c3ba  mov     [rsp+150h+OpenOptions], edi; OpenOptions
0x18003c3be  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x18003c3c6  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18003c3ca  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x18003c3ce  mov     edx, 100001h; DesiredAccess
0x18003c3d3  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x18003c3d7  call    cs:__imp_NtOpenFile
0x18003c3dd  test    bl, bl
0x18003c3df  jz      short loc_18003C41C
0x18003c3e1  cmp     eax, 0C000000Dh
0x18003c3e6  jz      short loc_18003C3EF
0x18003c3e8  cmp     eax, 0C0000103h
0x18003c3ed  jnz     short loc_18003C41C
0x18003c3ef  mov     eax, 0FFFEh
0x18003c3f4  add     [rsp+150h+NtName.Length], ax
0x18003c3f9  mov     [rsp+150h+OpenOptions], edi; OpenOptions
0x18003c3fd  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x18003c405  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18003c409  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x18003c40d  mov     edx, 100001h; DesiredAccess
0x18003c412  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x18003c416  call    cs:__imp_NtOpenFile
0x18003c41c  xor     ebx, ebx
0x18003c41e  test    eax, eax
0x18003c420  jns     short loc_18003C450
0x18003c422  mov     ecx, 0C000003Ah
0x18003c427  cmp     eax, 0C0000034h
0x18003c42c  jz      short loc_18003C438
0x18003c42e  cmp     eax, 0C0000024h
0x18003c433  cmovz   eax, ecx
0x18003c436  mov     ecx, eax; Status
0x18003c438  call    cs:__imp_RtlNtStatusToDosError
0x18003c43e  mov     ecx, eax; dwErrCode
0x18003c440  call    cs:__imp_SetLastError
0x18003c446  mov     eax, 83Ch
0x18003c44b  jmp     loc_18003C1CE
0x18003c450  cmp     word ptr [rsp+150h+PartName], bx
0x18003c455  jnz     short loc_18003C46C
0x18003c457  mov     ecx, 2; dwErrCode
0x18003c45c  call    cs:__imp_SetLastError
0x18003c462  mov     eax, 84Bh
0x18003c467  jmp     loc_18003C1CE
0x18003c46c  mov     edi, 268h
0x18003c471  mov     r9d, 3Ch ; '<'
0x18003c477  lea     r14d, [r9-36h]
0x18003c47b  cmp     word ptr [rsp+150h+PartName], r14w
0x18003c481  jnz     short loc_18003C4AF
0x18003c483  mov     r8d, r14d; Length
0x18003c486  lea     rdx, asc_180075E88; "*.*"
0x18003c48d  mov     rcx, [rsp+150h+PartName+8]; Source1
0x18003c492  call    cs:__imp_RtlCompareMemory
0x18003c498  cmp     rax, r14
0x18003c49b  jnz     short loc_18003C4A9
0x18003c49d  lea     r8d, [r14-4]
0x18003c4a1  mov     word ptr [rsp+150h+PartName], r8w
0x18003c4a7  jmp     short loc_18003C523
0x18003c4a9  mov     r9d, 3Ch ; '<'
0x18003c4af  mov     edx, ebx
0x18003c4b1  mov     rcx, [rsp+150h+PartName+8]
0x18003c4b6  movzx   eax, word ptr [rsp+150h+PartName]
0x18003c4bb  test    eax, 0FFFFFFFEh
0x18003c4c0  jbe     short loc_18003C512
0x18003c4c2  mov     r8d, 2
0x18003c4c8  test    edx, edx
0x18003c4ca  jz      short loc_18003C4DE
0x18003c4cc  cmp     word ptr [rcx], 2Eh ; '.'
0x18003c4d0  jnz     short loc_18003C4DE
0x18003c4d2  cmp     word ptr [rcx-2], 2Ah ; '*'
0x18003c4d7  jnz     short loc_18003C4DE
0x18003c4d9  mov     [rcx-2], r9w
0x18003c4de  cmp     word ptr [rcx], 3Fh ; '?'
0x18003c4e2  jz      short loc_18003C4EC
0x18003c4e4  cmp     word ptr [rcx], 2Ah ; '*'
0x18003c4e8  jnz     short loc_18003C502
0x18003c4ea  jmp     short loc_18003C4F1
0x18003c4ec  mov     word ptr [rcx], 3Eh ; '>'
0x18003c4f1  test    edx, edx
0x18003c4f3  jz      short loc_18003C502
0x18003c4f5  cmp     word ptr [rcx-2], 2Eh ; '.'
0x18003c4fa  jnz     short loc_18003C502
0x18003c4fc  mov     word ptr [rcx-2], 22h ; '"'
0x18003c502  inc     edx
0x18003c504  add     rcx, r8
0x18003c507  movzx   eax, word ptr [rsp+150h+PartName]
0x18003c50c  shr     eax, 1
0x18003c50e  cmp     edx, eax
0x18003c510  jb      short loc_18003C4C8
0x18003c512  test    r15b, r15b
0x18003c515  jz      short loc_18003C523
0x18003c517  cmp     word ptr [rcx-2], 2Ah ; '*'
0x18003c51c  jnz     short loc_18003C523
0x18003c51e  mov     [rcx-2], r9w
0x18003c523  xor     r15d, r15d
0x18003c526  mov     ebx, 87Ah
0x18003c52b  mov     ecx, edi; cb
0x18003c52d  call    cs:__imp_CoTaskMemAlloc
0x18003c533  mov     r14, rax
0x18003c536  test    rax, rax
0x18003c539  jz      loc_18003C652
0x18003c53f  mov     [rsp+150h+var_E0], r15d
0x18003c544  mov     [rsp+150h+var_DC], bx
0x18003c549  lea     rax, [rsp+150h+PartName]
  ... truncated ...
```
