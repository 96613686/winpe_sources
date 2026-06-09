# DxgkpGetFileVersion(_UNICODE_STRING *,_LARGE_INTEGER *,long *)

- ea: `0x140363640`
- end: `0x140363b82`
- name: `?DxgkpGetFileVersion@@YAJPEAU_UNICODE_STRING@@PEAT_LARGE_INTEGER@@PEAJ@Z`
- size: `1346`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, union _LARGE_INTEGER *, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140235b5c`
- `0x1402a1cc4`
- `0x140363030`
- `0x1403ff6c8`

## callees

- `0x14001b890`
- `0x1400a00d8`
- `0x1400a0100`
- `0x140363640`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140363b24`
- `ntoskrnl!ObfDereferenceObject` at `0x140363b24`
- `ntoskrnl!ZwClose` at `0x140363b3a`
- `ntoskrnl!ZwClose` at `0x140363b50`
- `ntoskrnl!ZwClose` at `0x140363b3a`
- `ntoskrnl!ZwClose` at `0x140363b50`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140363adf`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140363adf`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14036389e`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14036389e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140363b10`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140363b10`
- `ntoskrnl!KeStackAttachProcess` at `0x1403638f7`
- `ntoskrnl!KeStackAttachProcess` at `0x1403638f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140363832`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140363832`
- `ntoskrnl!ZwOpenFile` at `0x140363721`
- `ntoskrnl!ZwOpenFile` at `0x140363721`
- `ntoskrnl!PsInitialSystemProcess` at `0x1403638ed`
- `ntoskrnl!PsInitialSystemProcess` at `0x140363932`
- `ntoskrnl!PsInitialSystemProcess` at `0x140363aed`
- `ntoskrnl!ZwCreateSection` at `0x1403637d0`
- `ntoskrnl!ZwCreateSection` at `0x1403637d0`
- `ntoskrnl!MmMapViewOfSection` at `0x14036393f`
- `ntoskrnl!MmMapViewOfSection` at `0x14036393f`
- `ntoskrnl!LdrResFindResource` at `0x1403639b3`
- `ntoskrnl!LdrResFindResource` at `0x1403639b3`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140363af7`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140363af7`
- `watchdog!WdLogSingleEntry0` at `0x140363a60`
- `watchdog!WdLogSingleEntry0` at `0x140363a60`
- `watchdog!WdLogSingleEntry1` at `0x14036374a`
- `watchdog!WdLogSingleEntry1` at `0x1403637e9`
- `watchdog!WdLogSingleEntry1` at `0x14036385b`
- `watchdog!WdLogSingleEntry1` at `0x1403638b8`
- `watchdog!WdLogSingleEntry1` at `0x140363958`
- `watchdog!WdLogSingleEntry1` at `0x1403639d0`
- `watchdog!WdLogSingleEntry1` at `0x14036374a`
- `watchdog!WdLogSingleEntry1` at `0x1403637e9`
- `watchdog!WdLogSingleEntry1` at `0x14036385b`
- `watchdog!WdLogSingleEntry1` at `0x1403638b8`
- `watchdog!WdLogSingleEntry1` at `0x140363958`
- `watchdog!WdLogSingleEntry1` at `0x1403639d0`

## string_xrefs

- `0x140363760`: `Failed ZwOpenFile in DxgkpGetFileVersion (ntStatus = %I64d).`
- `0x1403637ff`: `Failed to create the section on the opened file in DxgkpGetFileVersion (ntStatus = %I64d).`
- `0x140363aa3`: `Failed to access the version information of the mapped file in DxgkpGetFileVersion.`

## pseudocode

```c
__int64 __fastcall DxgkpGetFileVersion(struct _UNICODE_STRING *a1, union _LARGE_INTEGER *a2, int *a3)
{
  PVOID v5; // r15
  char v6; // r12
  NTSTATUS v7; // eax
  __int64 v8; // rsi
  const wchar_t *v9; // r9
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  int v12; // eax
  int Resource; // eax
  __int64 v14; // rbx
  unsigned __int64 v16; // [rsp+58h] [rbp-F0h] BYREF
  PVOID MappedBase; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v18; // [rsp+68h] [rbp-E0h] BYREF
  void *SectionHandle; // [rsp+70h] [rbp-D8h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-D0h] BYREF
  PVOID Object; // [rsp+80h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+88h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-80h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-70h] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  v5 = 0;
  SectionHandle = 0;
  v16 = 0;
  v18 = 0;
  MappedBase = 0;
  v6 = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( a3 )
    *a3 = 0;
  v22[0] = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenFile(&FileHandle, 0x1200A9u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  v8 = v7;
  if ( a3 )
    *a3 = v7;
  if ( v7 < 0 )
  {
    if ( a3 )
      goto LABEL_21;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 189;
    v9 = L"Failed ZwOpenFile in DxgkpGetFileVersion (ntStatus = %I64d).";
    goto LABEL_8;
  }
  ObjectAttributes.ObjectName = 0;
  v10 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x11000000u, FileHandle);
  v8 = v10;
  if ( v10 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 211;
    v9 = L"Failed to create the section on the opened file in DxgkpGetFileVersion (ntStatus = %I64d).";
LABEL_8:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v9, v8, 0, 0, 0, 0);
    goto LABEL_21;
  }
  Object = 0;
  v11 = ObReferenceObjectByHandle(SectionHandle, 4u, 0, 0, &Object, 0);
  v8 = v11;
  v5 = Object;
  v22[1] = Object;
  if ( v11 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 226;
    v9 = L"Failed to get the section object from the file in DxgkpGetFileVersion (ntStatus = %I64d).";
    goto LABEL_8;
  }
  v18 = 0;
  if ( (int)MmMapViewInSystemSpaceEx(Object, &MappedBase, &v16, &v18, 1) < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 246;
    MappedBase = 0;
    v16 = 0;
    v18 = 0;
    v6 = 0;
    KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
    v12 = MmMapViewOfSection(v5, PsInitialSystemProcess, &MappedBase, 0, 0, &v18, &v16, 2, 0, 2, 0);
    v8 = v12;
    if ( v12 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 274;
      v9 = L"Failed to map the file with MmMapViewOfSection in DxgkpGetFileVersion (ntStatus = %I64d).";
      goto LABEL_8;
    }
  }
  a2->QuadPart = 0;
  Resource = LdrResFindResource(MappedBase, 16, 1, 0, v22, &v16, 0, 0, 16);
  v8 = Resource;
  if ( Resource >= 0 )
  {
    if ( v16 >= 0x5C )
    {
      v14 = v22[0];
      if ( !wcsncmp_0((const wchar_t *)(v22[0] + 6LL), L"VS_VERSION_INFO", 0x20u) )
      {
        a2->HighPart = *(_DWORD *)(v14 + 48);
        a2->LowPart = *(_DWORD *)(v14 + 52);
      }
    }
  }
  else
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 307;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Cannot find the file version resource in DxgkpGetFileVersion (ntStatus = %I64d).",
      v8,
      0,
      0,
      0,
      0);
    LODWORD(v8) = 0;
  }
LABEL_21:
  if ( MappedBase )
  {
    if ( v6 )
      MmUnmapViewInSystemSpace(MappedBase);
    else
      MmUnmapViewOfSection(PsInitialSystemProcess);
  }
  if ( !v6 )
    KeUnstackDetachProcess(&ApcState);
  if ( v5 )
    ObfDereferenceObject(v5);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140363640  mov     r11, rsp
0x140363643  push    rbx
0x140363644  push    rsi
0x140363645  push    rdi
0x140363646  push    r12
0x140363648  push    r13
0x14036364a  push    r14
0x14036364c  push    r15
0x14036364e  sub     rsp, 110h
0x140363655  mov     rax, cs:__security_cookie
0x14036365c  xor     rax, rsp
0x14036365f  mov     [rsp+148h+var_40], rax
0x140363667  mov     rbx, r8
0x14036366a  mov     r13, rdx
0x14036366d  xor     edi, edi
0x14036366f  mov     [rsp+148h+FileHandle], rdi
0x140363674  mov     dword ptr [rsp+148h+ObjectAttributes+4], edi
0x14036367b  mov     dword ptr [rsp+148h+ObjectAttributes+1Ch], edi
0x140363682  xorps   xmm0, xmm0
0x140363685  movups  xmmword ptr [r11-80h], xmm0
0x14036368a  mov     r15d, edi
0x14036368d  mov     [rsp+148h+SectionHandle], rdi
0x140363692  mov     [rsp+148h+var_F0], rdi
0x140363697  mov     [rsp+148h+var_E0], rdi
0x14036369c  mov     [rsp+148h+MappedBase], rdi
0x1403636a1  mov     r12b, 1
0x1403636a4  mov     [rsp+148h+var_F8], r12b
0x1403636a9  movups  xmmword ptr [r11-70h], xmm0
0x1403636ae  movups  xmmword ptr [r11-60h], xmm0
0x1403636b3  movups  xmmword ptr [r11-50h], xmm0
0x1403636b8  test    r8, r8
0x1403636bb  jz      short loc_1403636C0
0x1403636bd  mov     [r8], edi
0x1403636c0  mov     [rsp+148h+var_C0], rdi
0x1403636c8  mov     [rsp+148h+ObjectAttributes.Length], 30h ; '0'
0x1403636d3  mov     [rsp+148h+ObjectAttributes.RootDirectory], rdi
0x1403636db  mov     [rsp+148h+ObjectAttributes.Attributes], 240h
0x1403636e6  mov     [rsp+148h+ObjectAttributes.ObjectName], rcx
0x1403636ee  movdqu  xmmword ptr [rsp+148h+ObjectAttributes.SecurityDescriptor], xmm0
0x1403636f7  mov     [rsp+148h+OpenOptions], 60h ; '`'; OpenOptions
0x1403636ff  mov     [rsp+148h+ShareAccess], 5; ShareAccess
0x140363707  lea     r9, [rsp+148h+IoStatusBlock]; IoStatusBlock
0x14036370f  lea     r8, [rsp+148h+ObjectAttributes]; ObjectAttributes
0x140363717  mov     edx, 1200A9h; DesiredAccess
0x14036371c  lea     rcx, [rsp+148h+FileHandle]; FileHandle
0x140363721  call    cs:__imp_ZwOpenFile
0x140363728  nop     dword ptr [rax+rax+00h]
0x14036372d  movsxd  rsi, eax
0x140363730  test    rbx, rbx
0x140363733  jz      short loc_140363737
0x140363735  mov     [rbx], esi
0x140363737  test    eax, eax
0x140363739  jns     short loc_140363795
0x14036373b  test    rbx, rbx
0x14036373e  jnz     loc_140363ACD
0x140363744  mov     rdx, rsi
0x140363747  lea     ecx, [rbx+2]
0x14036374a  call    cs:__imp_WdLogSingleEntry1
0x140363751  nop     dword ptr [rax+rax+00h]
0x140363756  mov     cs:WdLogGlobalForLineNumber, 0BDh
0x140363760  lea     r9, aFailedZwopenfi; "Failed ZwOpenFile in DxgkpGetFileVersio"...
0x140363767  mov     [rsp+148h+var_108], rdi
0x14036376c  mov     [rsp+148h+var_110], rdi
0x140363771  mov     [rsp+148h+var_118], rdi
0x140363776  mov     qword ptr [rsp+148h+OpenOptions], rdi
0x14036377b  mov     qword ptr [rsp+148h+ShareAccess], rsi
0x140363780  or      r8d, 0FFFFFFFFh
0x140363784  mov     edx, 40000h
0x140363789  xor     ecx, ecx
0x14036378b  call    DxgkLogInternalTriageEvent
0x140363790  jmp     loc_140363ACD
0x140363795  mov     [rsp+148h+ObjectAttributes.ObjectName], rdi
0x14036379d  mov     rax, [rsp+148h+FileHandle]
0x1403637a2  mov     [rsp+148h+var_118], rax; FileHandle
0x1403637a7  mov     [rsp+148h+OpenOptions], 11000000h; AllocationAttributes
0x1403637af  mov     r14d, 2
0x1403637b5  mov     [rsp+148h+ShareAccess], r14d; SectionPageProtection
0x1403637ba  xor     r9d, r9d; MaximumSize
0x1403637bd  lea     r8, [rsp+148h+ObjectAttributes]; ObjectAttributes
0x1403637c5  lea     ebx, [r14+2]
0x1403637c9  mov     edx, ebx; DesiredAccess
0x1403637cb  lea     rcx, [rsp+148h+SectionHandle]; SectionHandle
0x1403637d0  call    cs:__imp_ZwCreateSection
0x1403637d7  nop     dword ptr [rax+rax+00h]
0x1403637dc  movsxd  rsi, eax
0x1403637df  test    eax, eax
0x1403637e1  jns     short loc_14036380B
0x1403637e3  mov     rdx, rsi
0x1403637e6  mov     ecx, r14d
0x1403637e9  call    cs:__imp_WdLogSingleEntry1
0x1403637f0  nop     dword ptr [rax+rax+00h]
0x1403637f5  mov     cs:WdLogGlobalForLineNumber, 0D3h
0x1403637ff  lea     r9, aFailedToCreate_16; "Failed to create the section on the ope"...
0x140363806  jmp     loc_140363767
0x14036380b  mov     [rsp+148h+Object], rdi
0x140363813  mov     qword ptr [rsp+148h+OpenOptions], rdi; HandleInformation
0x140363818  lea     rax, [rsp+148h+Object]
0x140363820  mov     qword ptr [rsp+148h+ShareAccess], rax; Object
0x140363825  xor     r9d, r9d; AccessMode
0x140363828  xor     r8d, r8d; ObjectType
0x14036382b  mov     edx, ebx; DesiredAccess
0x14036382d  mov     rcx, [rsp+148h+SectionHandle]; Handle
0x140363832  call    cs:__imp_ObReferenceObjectByHandle
0x140363839  nop     dword ptr [rax+rax+00h]
0x14036383e  movsxd  rsi, eax
0x140363841  mov     r15, [rsp+148h+Object]
0x140363849  mov     [rsp+148h+var_B8], r15
0x140363851  test    eax, eax
0x140363853  jns     short loc_14036387D
0x140363855  mov     rdx, rsi
0x140363858  mov     ecx, r14d
0x14036385b  call    cs:__imp_WdLogSingleEntry1
0x140363862  nop     dword ptr [rax+rax+00h]
0x140363867  mov     cs:WdLogGlobalForLineNumber, 0E2h
0x140363871  lea     r9, aFailedToGetThe_4; "Failed to get the section object from t"...
0x140363878  jmp     loc_140363767
0x14036387d  mov     [rsp+148h+var_E0], rdi
0x140363882  mov     ebx, 1
0x140363887  mov     qword ptr [rsp+148h+ShareAccess], rbx
0x14036388c  lea     r9, [rsp+148h+var_E0]
0x140363891  lea     r8, [rsp+148h+var_F0]
0x140363896  lea     rdx, [rsp+148h+MappedBase]
0x14036389b  mov     rcx, r15
0x14036389e  call    cs:__imp_MmMapViewInSystemSpaceEx
0x1403638a5  nop     dword ptr [rax+rax+00h]
0x1403638aa  test    eax, eax
0x1403638ac  jns     loc_14036397A
0x1403638b2  movsxd  rdx, eax
0x1403638b5  lea     ecx, [rbx+2]
0x1403638b8  call    cs:__imp_WdLogSingleEntry1
0x1403638bf  nop     dword ptr [rax+rax+00h]
0x1403638c4  mov     cs:WdLogGlobalForLineNumber, 0F6h
0x1403638ce  mov     [rsp+148h+MappedBase], rdi
0x1403638d3  mov     [rsp+148h+var_F0], rdi
0x1403638d8  mov     [rsp+148h+var_E0], rdi
0x1403638dd  mov     r12b, dil
0x1403638e0  mov     [rsp+148h+var_F8], dil
0x1403638e5  lea     rdx, [rsp+148h+ApcState]; ApcState
0x1403638ed  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1403638f4  mov     rcx, [rcx]; PROCESS
0x1403638f7  call    cs:__imp_KeStackAttachProcess
0x1403638fe  nop     dword ptr [rax+rax+00h]
0x140363903  mov     [rsp+148h+var_100], r14d
0x140363908  mov     dword ptr [rsp+148h+var_108], edi
0x14036390c  mov     dword ptr [rsp+148h+var_110], r14d
0x140363911  lea     rax, [rsp+148h+var_F0]
0x140363916  mov     [rsp+148h+var_118], rax
0x14036391b  lea     rax, [rsp+148h+var_E0]
0x140363920  mov     qword ptr [rsp+148h+OpenOptions], rax
0x140363925  mov     qword ptr [rsp+148h+ShareAccess], rdi
0x14036392a  xor     r9d, r9d
0x14036392d  lea     r8, [rsp+148h+MappedBase]
0x140363932  mov     rdx, cs:__imp_PsInitialSystemProcess
0x140363939  mov     rdx, [rdx]
0x14036393c  mov     rcx, r15
0x14036393f  call    cs:__imp_MmMapViewOfSection
0x140363946  nop     dword ptr [rax+rax+00h]
0x14036394b  movsxd  rsi, eax
0x14036394e  test    eax, eax
0x140363950  jns     short loc_14036397A
0x140363952  mov     rdx, rsi
0x140363955  mov     ecx, r14d
0x140363958  call    cs:__imp_WdLogSingleEntry1
0x14036395f  nop     dword ptr [rax+rax+00h]
0x140363964  mov     cs:WdLogGlobalForLineNumber, 112h
0x14036396e  lea     r9, aFailedToMapThe; "Failed to map the file with MmMapViewOf"...
0x140363975  jmp     loc_140363767
0x14036397a  mov     [r13+0], rdi
0x14036397e  mov     edx, 10h
0x140363983  mov     dword ptr [rsp+148h+var_108], edx
0x140363987  mov     [rsp+148h+var_110], rdi
0x14036398c  mov     [rsp+148h+var_118], rdi
0x140363991  lea     rax, [rsp+148h+var_F0]
0x140363996  mov     qword ptr [rsp+148h+OpenOptions], rax
0x14036399b  lea     rax, [rsp+148h+var_C0]
0x1403639a3  mov     qword ptr [rsp+148h+ShareAccess], rax
0x1403639a8  xor     r9d, r9d
0x1403639ab  mov     r8, rbx
0x1403639ae  mov     rcx, [rsp+148h+MappedBase]
0x1403639b3  call    cs:__imp_LdrResFindResource
0x1403639ba  nop     dword ptr [rax+rax+00h]
0x1403639bf  movsxd  rsi, eax
0x1403639c2  mov     [rsp+148h+var_F4], esi
0x1403639c6  test    eax, eax
0x1403639c8  jns     short loc_140363A21
0x1403639ca  mov     rdx, rsi
0x1403639cd  mov     ecx, r14d
0x1403639d0  call    cs:__imp_WdLogSingleEntry1
0x1403639d7  nop     dword ptr [rax+rax+00h]
0x1403639dc  mov     cs:WdLogGlobalForLineNumber, 133h
0x1403639e6  mov     [rsp+148h+var_108], rdi
0x1403639eb  mov     [rsp+148h+var_110], rdi
0x1403639f0  mov     [rsp+148h+var_118], rdi
0x1403639f5  mov     qword ptr [rsp+148h+OpenOptions], rdi
0x1403639fa  mov     qword ptr [rsp+148h+ShareAccess], rsi
0x1403639ff  lea     r9, aCannotFindTheF; "Cannot find the file version resource i"...
0x140363a06  or      r8d, 0FFFFFFFFh
0x140363a0a  mov     edx, 40000h
0x140363a0f  xor     ecx, ecx
0x140363a11  call    DxgkLogInternalTriageEvent
0x140363a16  mov     esi, edi
0x140363a18  mov     [rsp+148h+var_F4], edi
0x140363a1c  jmp     loc_140363ACD
0x140363a21  cmp     [rsp+148h+var_F0], 5Ch ; '\'
0x140363a27  jb      short loc_140363A59
0x140363a29  mov     rbx, [rsp+148h+var_C0]
0x140363a31  lea     rcx, [rbx+6]; Str1
0x140363a35  mov     r8d, 20h ; ' '; MaxCount
0x140363a3b  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x140363a42  call    wcsncmp_0
0x140363a47  test    eax, eax
0x140363a49  jnz     short loc_140363A59
0x140363a4b  mov     eax, [rbx+30h]
0x140363a4e  mov     [r13+4], eax
0x140363a52  mov     eax, [rbx+34h]
0x140363a55  mov     [r13+0], eax
0x140363a59  jmp     short loc_140363ACD
0x140363a5b  mov     ecx, 2
0x140363a60  call    cs:__imp_WdLogSingleEntry0
0x140363a67  nop     dword ptr [rax+rax+00h]
0x140363a6c  mov     cs:WdLogGlobalForLineNumber, 144h
0x140363a76  mov     [rsp+148h+var_108], 0
0x140363a7f  mov     [rsp+148h+var_110], 0
0x140363a88  mov     [rsp+148h+var_118], 0
0x140363a91  mov     qword ptr [rsp+148h+OpenOptions], 0
0x140363a9a  mov     qword ptr [rsp+148h+ShareAccess], 144h
0x140363aa3  lea     r9, aFailedToAccess; "Failed to access the version informatio"...
0x140363aaa  or      r8d, 0FFFFFFFFh
0x140363aae  mov     edx, 40000h
0x140363ab3  xor     ecx, ecx
0x140363ab5  call    DxgkLogInternalTriageEvent
0x140363aba  xor     esi, esi
0x140363abc  mov     [rsp+148h+var_F4], esi
0x140363ac0  mov     r15, [rsp+148h+var_B8]
0x140363ac8  mov     r12b, [rsp+148h+var_F8]
0x140363acd  mov     rdx, [rsp+148h+MappedBase]
0x140363ad2  test    rdx, rdx
0x140363ad5  jz      short loc_140363B03
0x140363ad7  test    r12b, r12b
0x140363ada  jz      short loc_140363AED
0x140363adc  mov     rcx, rdx; MappedBase
0x140363adf  call    cs:__imp_MmUnmapViewInSystemSpace
0x140363ae6  nop     dword ptr [rax+rax+00h]
0x140363aeb  jmp     short loc_140363B03
0x140363aed  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140363af4  mov     rcx, [rcx]
0x140363af7  call    cs:__imp_MmUnmapViewOfSection
0x140363afe  nop     dword ptr [rax+rax+00h]
0x140363b03  test    r12b, r12b
0x140363b06  jnz     short loc_140363B1C
0x140363b08  lea     rcx, [rsp+148h+ApcState]; ApcState
0x140363b10  call    cs:__imp_KeUnstackDetachProcess
0x140363b17  nop     dword ptr [rax+rax+00h]
0x140363b1c  test    r15, r15
0x140363b1f  jz      short loc_140363B30
0x140363b21  mov     rcx, r15; Object
0x140363b24  call    cs:__imp_ObfDereferenceObject
0x140363b2b  nop     dword ptr [rax+rax+00h]
0x140363b30  mov     rcx, [rsp+148h+SectionHandle]; Handle
0x140363b35  test    rcx, rcx
0x140363b38  jz      short loc_140363B46
0x140363b3a  call    cs:__imp_ZwClose
0x140363b41  nop     dword ptr [rax+rax+00h]
0x140363b46  mov     rcx, [rsp+148h+FileHandle]; Handle
0x140363b4b  test    rcx, rcx
0x140363b4e  jz      short loc_140363B5C
0x140363b50  call    cs:__imp_ZwClose
0x140363b57  nop     dword ptr [rax+rax+00h]
0x140363b5c  mov     eax, esi
0x140363b5e  mov     rcx, [rsp+148h+var_40]
0x140363b66  xor     rcx, rsp; StackCookie
0x140363b69  call    __security_check_cookie
0x140363b6e  add     rsp, 110h
0x140363b75  pop     r15
0x140363b77  pop     r14
0x140363b79  pop     r13
0x140363b7b  pop     r12
0x140363b7d  pop     rdi
0x140363b7e  pop     rsi
0x140363b7f  pop     rbx
0x140363b80  retn
```
