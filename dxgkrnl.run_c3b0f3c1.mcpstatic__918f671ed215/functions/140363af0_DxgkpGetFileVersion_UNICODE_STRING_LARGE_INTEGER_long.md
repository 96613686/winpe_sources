# DxgkpGetFileVersion(_UNICODE_STRING *,_LARGE_INTEGER *,long *)

- ea: `0x140363af0`
- end: `0x140364032`
- name: `?DxgkpGetFileVersion@@YAJPEAU_UNICODE_STRING@@PEAT_LARGE_INTEGER@@PEAJ@Z`
- size: `1346`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, union _LARGE_INTEGER *, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1402386bc`
- `0x1402a8674`
- `0x1403634e0`
- `0x1403fd128`

## callees

- `0x14001b9c0`
- `0x1400a0ba8`
- `0x1400a0bd0`
- `0x140363af0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140363fd4`
- `ntoskrnl!ObfDereferenceObject` at `0x140363fd4`
- `ntoskrnl!ZwClose` at `0x140363fea`
- `ntoskrnl!ZwClose` at `0x140364000`
- `ntoskrnl!ZwClose` at `0x140363fea`
- `ntoskrnl!ZwClose` at `0x140364000`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140363f8f`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140363f8f`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x140363d4e`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x140363d4e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140363fc0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140363fc0`
- `ntoskrnl!KeStackAttachProcess` at `0x140363da7`
- `ntoskrnl!KeStackAttachProcess` at `0x140363da7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140363ce2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140363ce2`
- `ntoskrnl!ZwOpenFile` at `0x140363bd1`
- `ntoskrnl!ZwOpenFile` at `0x140363bd1`
- `ntoskrnl!PsInitialSystemProcess` at `0x140363d9d`
- `ntoskrnl!PsInitialSystemProcess` at `0x140363de2`
- `ntoskrnl!PsInitialSystemProcess` at `0x140363f9d`
- `ntoskrnl!ZwCreateSection` at `0x140363c80`
- `ntoskrnl!ZwCreateSection` at `0x140363c80`
- `ntoskrnl!MmMapViewOfSection` at `0x140363def`
- `ntoskrnl!MmMapViewOfSection` at `0x140363def`
- `ntoskrnl!LdrResFindResource` at `0x140363e63`
- `ntoskrnl!LdrResFindResource` at `0x140363e63`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140363fa7`
- `ntoskrnl!MmUnmapViewOfSection` at `0x140363fa7`
- `watchdog!WdLogSingleEntry0` at `0x140363f10`
- `watchdog!WdLogSingleEntry0` at `0x140363f10`
- `watchdog!WdLogSingleEntry1` at `0x140363bfa`
- `watchdog!WdLogSingleEntry1` at `0x140363c99`
- `watchdog!WdLogSingleEntry1` at `0x140363d0b`
- `watchdog!WdLogSingleEntry1` at `0x140363d68`
- `watchdog!WdLogSingleEntry1` at `0x140363e08`
- `watchdog!WdLogSingleEntry1` at `0x140363e80`
- `watchdog!WdLogSingleEntry1` at `0x140363bfa`
- `watchdog!WdLogSingleEntry1` at `0x140363c99`
- `watchdog!WdLogSingleEntry1` at `0x140363d0b`
- `watchdog!WdLogSingleEntry1` at `0x140363d68`
- `watchdog!WdLogSingleEntry1` at `0x140363e08`
- `watchdog!WdLogSingleEntry1` at `0x140363e80`

## string_xrefs

- `0x140363c10`: `Failed ZwOpenFile in DxgkpGetFileVersion (ntStatus = %I64d).`
- `0x140363caf`: `Failed to create the section on the opened file in DxgkpGetFileVersion (ntStatus = %I64d).`
- `0x140363f53`: `Failed to access the version information of the mapped file in DxgkpGetFileVersion.`

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
  int v13; // eax
  int Resource; // eax
  __int64 v15; // rbx
  unsigned __int64 v17; // [rsp+58h] [rbp-F0h] BYREF
  PVOID MappedBase; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-E0h] BYREF
  void *SectionHandle; // [rsp+70h] [rbp-D8h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-D0h] BYREF
  PVOID Object; // [rsp+80h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+88h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-80h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-70h] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  v5 = 0;
  SectionHandle = 0;
  v17 = 0;
  v19 = 0;
  MappedBase = 0;
  v6 = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( a3 )
    *a3 = 0;
  v23[0] = 0;
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
    WdLogSingleEntry1(2, v7);
    WdLogGlobalForLineNumber = 189;
    v9 = L"Failed ZwOpenFile in DxgkpGetFileVersion (ntStatus = %I64d).";
    goto LABEL_8;
  }
  ObjectAttributes.ObjectName = 0;
  v10 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x11000000u, FileHandle);
  v8 = v10;
  if ( v10 < 0 )
  {
    WdLogSingleEntry1(2, v10);
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
  v23[1] = Object;
  if ( v11 < 0 )
  {
    WdLogSingleEntry1(2, v11);
    WdLogGlobalForLineNumber = 226;
    v9 = L"Failed to get the section object from the file in DxgkpGetFileVersion (ntStatus = %I64d).";
    goto LABEL_8;
  }
  v19 = 0;
  v12 = MmMapViewInSystemSpaceEx(Object, &MappedBase, &v17, &v19, 1);
  if ( v12 < 0 )
  {
    WdLogSingleEntry1(3, v12);
    WdLogGlobalForLineNumber = 246;
    MappedBase = 0;
    v17 = 0;
    v19 = 0;
    v6 = 0;
    KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
    v13 = MmMapViewOfSection(v5, PsInitialSystemProcess, &MappedBase, 0, 0, &v19, &v17, 2, 0, 2, 0);
    v8 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry1(2, v13);
      WdLogGlobalForLineNumber = 274;
      v9 = L"Failed to map the file with MmMapViewOfSection in DxgkpGetFileVersion (ntStatus = %I64d).";
      goto LABEL_8;
    }
  }
  a2->QuadPart = 0;
  Resource = LdrResFindResource(MappedBase, 16, 1, 0, v23, &v17, 0, 0, 16);
  v8 = Resource;
  if ( Resource >= 0 )
  {
    if ( v17 >= 0x5C )
    {
      v15 = v23[0];
      if ( !wcsncmp_0((const wchar_t *)(v23[0] + 6LL), L"VS_VERSION_INFO", 0x20u) )
      {
        a2->HighPart = *(_DWORD *)(v15 + 48);
        a2->LowPart = *(_DWORD *)(v15 + 52);
      }
    }
  }
  else
  {
    WdLogSingleEntry1(2, Resource);
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
0x140363af0  mov     r11, rsp
0x140363af3  push    rbx
0x140363af4  push    rsi
0x140363af5  push    rdi
0x140363af6  push    r12
0x140363af8  push    r13
0x140363afa  push    r14
0x140363afc  push    r15
0x140363afe  sub     rsp, 110h
0x140363b05  mov     rax, cs:__security_cookie
0x140363b0c  xor     rax, rsp
0x140363b0f  mov     [rsp+148h+var_40], rax
0x140363b17  mov     rbx, r8
0x140363b1a  mov     r13, rdx
0x140363b1d  xor     edi, edi
0x140363b1f  mov     [rsp+148h+FileHandle], rdi
0x140363b24  mov     dword ptr [rsp+148h+ObjectAttributes+4], edi
0x140363b2b  mov     dword ptr [rsp+148h+ObjectAttributes+1Ch], edi
0x140363b32  xorps   xmm0, xmm0
0x140363b35  movups  xmmword ptr [r11-80h], xmm0
0x140363b3a  mov     r15d, edi
0x140363b3d  mov     [rsp+148h+SectionHandle], rdi
0x140363b42  mov     [rsp+148h+var_F0], rdi
0x140363b47  mov     [rsp+148h+var_E0], rdi
0x140363b4c  mov     [rsp+148h+MappedBase], rdi
0x140363b51  mov     r12b, 1
0x140363b54  mov     [rsp+148h+var_F8], r12b
0x140363b59  movups  xmmword ptr [r11-70h], xmm0
0x140363b5e  movups  xmmword ptr [r11-60h], xmm0
0x140363b63  movups  xmmword ptr [r11-50h], xmm0
0x140363b68  test    r8, r8
0x140363b6b  jz      short loc_140363B70
0x140363b6d  mov     [r8], edi
0x140363b70  mov     [rsp+148h+var_C0], rdi
0x140363b78  mov     [rsp+148h+ObjectAttributes.Length], 30h ; '0'
0x140363b83  mov     [rsp+148h+ObjectAttributes.RootDirectory], rdi
0x140363b8b  mov     [rsp+148h+ObjectAttributes.Attributes], 240h
0x140363b96  mov     [rsp+148h+ObjectAttributes.ObjectName], rcx
0x140363b9e  movdqu  xmmword ptr [rsp+148h+ObjectAttributes.SecurityDescriptor], xmm0
0x140363ba7  mov     [rsp+148h+OpenOptions], 60h ; '`'; OpenOptions
0x140363baf  mov     [rsp+148h+ShareAccess], 5; ShareAccess
0x140363bb7  lea     r9, [rsp+148h+IoStatusBlock]; IoStatusBlock
0x140363bbf  lea     r8, [rsp+148h+ObjectAttributes]; ObjectAttributes
0x140363bc7  mov     edx, 1200A9h; DesiredAccess
0x140363bcc  lea     rcx, [rsp+148h+FileHandle]; FileHandle
0x140363bd1  call    cs:__imp_ZwOpenFile
0x140363bd8  nop     dword ptr [rax+rax+00h]
0x140363bdd  movsxd  rsi, eax
0x140363be0  test    rbx, rbx
0x140363be3  jz      short loc_140363BE7
0x140363be5  mov     [rbx], esi
0x140363be7  test    eax, eax
0x140363be9  jns     short loc_140363C45
0x140363beb  test    rbx, rbx
0x140363bee  jnz     loc_140363F7D
0x140363bf4  mov     rdx, rsi
0x140363bf7  lea     ecx, [rbx+2]
0x140363bfa  call    cs:__imp_WdLogSingleEntry1
0x140363c01  nop     dword ptr [rax+rax+00h]
0x140363c06  mov     cs:WdLogGlobalForLineNumber, 0BDh
0x140363c10  lea     r9, aFailedZwopenfi; "Failed ZwOpenFile in DxgkpGetFileVersio"...
0x140363c17  mov     [rsp+148h+var_108], rdi
0x140363c1c  mov     [rsp+148h+var_110], rdi
0x140363c21  mov     [rsp+148h+var_118], rdi
0x140363c26  mov     qword ptr [rsp+148h+OpenOptions], rdi
0x140363c2b  mov     qword ptr [rsp+148h+ShareAccess], rsi
0x140363c30  or      r8d, 0FFFFFFFFh
0x140363c34  mov     edx, 40000h
0x140363c39  xor     ecx, ecx
0x140363c3b  call    DxgkLogInternalTriageEvent
0x140363c40  jmp     loc_140363F7D
0x140363c45  mov     [rsp+148h+ObjectAttributes.ObjectName], rdi
0x140363c4d  mov     rax, [rsp+148h+FileHandle]
0x140363c52  mov     [rsp+148h+var_118], rax; FileHandle
0x140363c57  mov     [rsp+148h+OpenOptions], 11000000h; AllocationAttributes
0x140363c5f  mov     r14d, 2
0x140363c65  mov     [rsp+148h+ShareAccess], r14d; SectionPageProtection
0x140363c6a  xor     r9d, r9d; MaximumSize
0x140363c6d  lea     r8, [rsp+148h+ObjectAttributes]; ObjectAttributes
0x140363c75  lea     ebx, [r14+2]
0x140363c79  mov     edx, ebx; DesiredAccess
0x140363c7b  lea     rcx, [rsp+148h+SectionHandle]; SectionHandle
0x140363c80  call    cs:__imp_ZwCreateSection
0x140363c87  nop     dword ptr [rax+rax+00h]
0x140363c8c  movsxd  rsi, eax
0x140363c8f  test    eax, eax
0x140363c91  jns     short loc_140363CBB
0x140363c93  mov     rdx, rsi
0x140363c96  mov     ecx, r14d
0x140363c99  call    cs:__imp_WdLogSingleEntry1
0x140363ca0  nop     dword ptr [rax+rax+00h]
0x140363ca5  mov     cs:WdLogGlobalForLineNumber, 0D3h
0x140363caf  lea     r9, aFailedToCreate_17; "Failed to create the section on the ope"...
0x140363cb6  jmp     loc_140363C17
0x140363cbb  mov     [rsp+148h+Object], rdi
0x140363cc3  mov     qword ptr [rsp+148h+OpenOptions], rdi; HandleInformation
0x140363cc8  lea     rax, [rsp+148h+Object]
0x140363cd0  mov     qword ptr [rsp+148h+ShareAccess], rax; Object
0x140363cd5  xor     r9d, r9d; AccessMode
0x140363cd8  xor     r8d, r8d; ObjectType
0x140363cdb  mov     edx, ebx; DesiredAccess
0x140363cdd  mov     rcx, [rsp+148h+SectionHandle]; Handle
0x140363ce2  call    cs:__imp_ObReferenceObjectByHandle
0x140363ce9  nop     dword ptr [rax+rax+00h]
0x140363cee  movsxd  rsi, eax
0x140363cf1  mov     r15, [rsp+148h+Object]
0x140363cf9  mov     [rsp+148h+var_B8], r15
0x140363d01  test    eax, eax
0x140363d03  jns     short loc_140363D2D
0x140363d05  mov     rdx, rsi
0x140363d08  mov     ecx, r14d
0x140363d0b  call    cs:__imp_WdLogSingleEntry1
0x140363d12  nop     dword ptr [rax+rax+00h]
0x140363d17  mov     cs:WdLogGlobalForLineNumber, 0E2h
0x140363d21  lea     r9, aFailedToGetThe_4; "Failed to get the section object from t"...
0x140363d28  jmp     loc_140363C17
0x140363d2d  mov     [rsp+148h+var_E0], rdi
0x140363d32  mov     ebx, 1
0x140363d37  mov     qword ptr [rsp+148h+ShareAccess], rbx
0x140363d3c  lea     r9, [rsp+148h+var_E0]
0x140363d41  lea     r8, [rsp+148h+var_F0]
0x140363d46  lea     rdx, [rsp+148h+MappedBase]
0x140363d4b  mov     rcx, r15
0x140363d4e  call    cs:__imp_MmMapViewInSystemSpaceEx
0x140363d55  nop     dword ptr [rax+rax+00h]
0x140363d5a  test    eax, eax
0x140363d5c  jns     loc_140363E2A
0x140363d62  movsxd  rdx, eax
0x140363d65  lea     ecx, [rbx+2]
0x140363d68  call    cs:__imp_WdLogSingleEntry1
0x140363d6f  nop     dword ptr [rax+rax+00h]
0x140363d74  mov     cs:WdLogGlobalForLineNumber, 0F6h
0x140363d7e  mov     [rsp+148h+MappedBase], rdi
0x140363d83  mov     [rsp+148h+var_F0], rdi
0x140363d88  mov     [rsp+148h+var_E0], rdi
0x140363d8d  mov     r12b, dil
0x140363d90  mov     [rsp+148h+var_F8], dil
0x140363d95  lea     rdx, [rsp+148h+ApcState]; ApcState
0x140363d9d  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140363da4  mov     rcx, [rcx]; PROCESS
0x140363da7  call    cs:__imp_KeStackAttachProcess
0x140363dae  nop     dword ptr [rax+rax+00h]
0x140363db3  mov     [rsp+148h+var_100], r14d
0x140363db8  mov     dword ptr [rsp+148h+var_108], edi
0x140363dbc  mov     dword ptr [rsp+148h+var_110], r14d
0x140363dc1  lea     rax, [rsp+148h+var_F0]
0x140363dc6  mov     [rsp+148h+var_118], rax
0x140363dcb  lea     rax, [rsp+148h+var_E0]
0x140363dd0  mov     qword ptr [rsp+148h+OpenOptions], rax
0x140363dd5  mov     qword ptr [rsp+148h+ShareAccess], rdi
0x140363dda  xor     r9d, r9d
0x140363ddd  lea     r8, [rsp+148h+MappedBase]
0x140363de2  mov     rdx, cs:__imp_PsInitialSystemProcess
0x140363de9  mov     rdx, [rdx]
0x140363dec  mov     rcx, r15
0x140363def  call    cs:__imp_MmMapViewOfSection
0x140363df6  nop     dword ptr [rax+rax+00h]
0x140363dfb  movsxd  rsi, eax
0x140363dfe  test    eax, eax
0x140363e00  jns     short loc_140363E2A
0x140363e02  mov     rdx, rsi
0x140363e05  mov     ecx, r14d
0x140363e08  call    cs:__imp_WdLogSingleEntry1
0x140363e0f  nop     dword ptr [rax+rax+00h]
0x140363e14  mov     cs:WdLogGlobalForLineNumber, 112h
0x140363e1e  lea     r9, aFailedToMapThe; "Failed to map the file with MmMapViewOf"...
0x140363e25  jmp     loc_140363C17
0x140363e2a  mov     [r13+0], rdi
0x140363e2e  mov     edx, 10h
0x140363e33  mov     dword ptr [rsp+148h+var_108], edx
0x140363e37  mov     [rsp+148h+var_110], rdi
0x140363e3c  mov     [rsp+148h+var_118], rdi
0x140363e41  lea     rax, [rsp+148h+var_F0]
0x140363e46  mov     qword ptr [rsp+148h+OpenOptions], rax
0x140363e4b  lea     rax, [rsp+148h+var_C0]
0x140363e53  mov     qword ptr [rsp+148h+ShareAccess], rax
0x140363e58  xor     r9d, r9d
0x140363e5b  mov     r8, rbx
0x140363e5e  mov     rcx, [rsp+148h+MappedBase]
0x140363e63  call    cs:__imp_LdrResFindResource
0x140363e6a  nop     dword ptr [rax+rax+00h]
0x140363e6f  movsxd  rsi, eax
0x140363e72  mov     [rsp+148h+var_F4], esi
0x140363e76  test    eax, eax
0x140363e78  jns     short loc_140363ED1
0x140363e7a  mov     rdx, rsi
0x140363e7d  mov     ecx, r14d
0x140363e80  call    cs:__imp_WdLogSingleEntry1
0x140363e87  nop     dword ptr [rax+rax+00h]
0x140363e8c  mov     cs:WdLogGlobalForLineNumber, 133h
0x140363e96  mov     [rsp+148h+var_108], rdi
0x140363e9b  mov     [rsp+148h+var_110], rdi
0x140363ea0  mov     [rsp+148h+var_118], rdi
0x140363ea5  mov     qword ptr [rsp+148h+OpenOptions], rdi
0x140363eaa  mov     qword ptr [rsp+148h+ShareAccess], rsi
0x140363eaf  lea     r9, aCannotFindTheF; "Cannot find the file version resource i"...
0x140363eb6  or      r8d, 0FFFFFFFFh
0x140363eba  mov     edx, 40000h
0x140363ebf  xor     ecx, ecx
0x140363ec1  call    DxgkLogInternalTriageEvent
0x140363ec6  mov     esi, edi
0x140363ec8  mov     [rsp+148h+var_F4], edi
0x140363ecc  jmp     loc_140363F7D
0x140363ed1  cmp     [rsp+148h+var_F0], 5Ch ; '\'
0x140363ed7  jb      short loc_140363F09
0x140363ed9  mov     rbx, [rsp+148h+var_C0]
0x140363ee1  lea     rcx, [rbx+6]; Str1
0x140363ee5  mov     r8d, 20h ; ' '; MaxCount
0x140363eeb  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x140363ef2  call    wcsncmp_0
0x140363ef7  test    eax, eax
0x140363ef9  jnz     short loc_140363F09
0x140363efb  mov     eax, [rbx+30h]
0x140363efe  mov     [r13+4], eax
0x140363f02  mov     eax, [rbx+34h]
0x140363f05  mov     [r13+0], eax
0x140363f09  jmp     short loc_140363F7D
0x140363f0b  mov     ecx, 2
0x140363f10  call    cs:__imp_WdLogSingleEntry0
0x140363f17  nop     dword ptr [rax+rax+00h]
0x140363f1c  mov     cs:WdLogGlobalForLineNumber, 144h
0x140363f26  mov     [rsp+148h+var_108], 0
0x140363f2f  mov     [rsp+148h+var_110], 0
0x140363f38  mov     [rsp+148h+var_118], 0
0x140363f41  mov     qword ptr [rsp+148h+OpenOptions], 0
0x140363f4a  mov     qword ptr [rsp+148h+ShareAccess], 144h
0x140363f53  lea     r9, aFailedToAccess; "Failed to access the version informatio"...
0x140363f5a  or      r8d, 0FFFFFFFFh
0x140363f5e  mov     edx, 40000h
0x140363f63  xor     ecx, ecx
0x140363f65  call    DxgkLogInternalTriageEvent
0x140363f6a  xor     esi, esi
0x140363f6c  mov     [rsp+148h+var_F4], esi
0x140363f70  mov     r15, [rsp+148h+var_B8]
0x140363f78  mov     r12b, [rsp+148h+var_F8]
0x140363f7d  mov     rdx, [rsp+148h+MappedBase]
0x140363f82  test    rdx, rdx
0x140363f85  jz      short loc_140363FB3
0x140363f87  test    r12b, r12b
0x140363f8a  jz      short loc_140363F9D
0x140363f8c  mov     rcx, rdx; MappedBase
0x140363f8f  call    cs:__imp_MmUnmapViewInSystemSpace
0x140363f96  nop     dword ptr [rax+rax+00h]
0x140363f9b  jmp     short loc_140363FB3
0x140363f9d  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140363fa4  mov     rcx, [rcx]
0x140363fa7  call    cs:__imp_MmUnmapViewOfSection
0x140363fae  nop     dword ptr [rax+rax+00h]
0x140363fb3  test    r12b, r12b
0x140363fb6  jnz     short loc_140363FCC
0x140363fb8  lea     rcx, [rsp+148h+ApcState]; ApcState
0x140363fc0  call    cs:__imp_KeUnstackDetachProcess
0x140363fc7  nop     dword ptr [rax+rax+00h]
0x140363fcc  test    r15, r15
0x140363fcf  jz      short loc_140363FE0
0x140363fd1  mov     rcx, r15; Object
0x140363fd4  call    cs:__imp_ObfDereferenceObject
0x140363fdb  nop     dword ptr [rax+rax+00h]
0x140363fe0  mov     rcx, [rsp+148h+SectionHandle]; Handle
0x140363fe5  test    rcx, rcx
0x140363fe8  jz      short loc_140363FF6
0x140363fea  call    cs:__imp_ZwClose
0x140363ff1  nop     dword ptr [rax+rax+00h]
0x140363ff6  mov     rcx, [rsp+148h+FileHandle]; Handle
0x140363ffb  test    rcx, rcx
0x140363ffe  jz      short loc_14036400C
0x140364000  call    cs:__imp_ZwClose
0x140364007  nop     dword ptr [rax+rax+00h]
0x14036400c  mov     eax, esi
0x14036400e  mov     rcx, [rsp+148h+var_40]
0x140364016  xor     rcx, rsp; StackCookie
0x140364019  call    __security_check_cookie
0x14036401e  add     rsp, 110h
0x140364025  pop     r15
0x140364027  pop     r14
0x140364029  pop     r13
0x14036402b  pop     r12
0x14036402d  pop     rdi
0x14036402e  pop     rsi
0x14036402f  pop     rbx
0x140364030  retn
```
