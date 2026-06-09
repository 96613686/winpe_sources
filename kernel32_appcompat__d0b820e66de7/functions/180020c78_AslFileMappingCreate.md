# AslFileMappingCreate

- ea: `0x180020c78`
- end: `0x180020ef0`
- name: `AslFileMappingCreate`
- size: `632`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x180020904`
- `0x18007ef60`
- `0x18007fa2c`
- `0x18007ff50`

## callees

- `0x18001f138`
- `0x18001f31c`
- `0x18001f74c`
- `0x180020c78`
- `0x180022148`
- `0x18005b394`
- `0x180061df4`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180020d58`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180020d58`
- `ntdll!RtlFreeUnicodeString` at `0x180020df7`
- `ntdll!RtlFreeUnicodeString` at `0x180020df7`
- `ntdll!ZwQueryInformationFile` at `0x180020db1`
- `ntdll!ZwQueryInformationFile` at `0x180020db1`
- `ntdll!RtlInitUnicodeString` at `0x180020ce3`
- `ntdll!RtlInitUnicodeString` at `0x180020ce3`
- `ntdll!RtlAllocateHeap` at `0x180020d06`
- `ntdll!RtlAllocateHeap` at `0x180020d06`

## string_xrefs

- `0x180020dd0`: `AslFileMappingCreate`
- `0x180020e9d`: `AslFileMappingCreate`
- `0x180020e8b`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180020edc`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180020ec9`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(HANDLE **a1, const WCHAR *a2)
{
  HANDLE *Heap; // rax
  HANDLE *v5; // rsi
  NTSTATUS v6; // ebx
  int v7; // eax
  const char *v8; // r9
  int v9; // r8d
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  const char *v13; // r9
  int v14; // r8d
  int v15; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]

  v19 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    goto LABEL_13;
  }
  v6 = AslStringDuplicate(Heap, a2);
  if ( v6 >= 0 )
  {
    if ( wcsnicmp_0(a2, L"\\SystemRoot\\", 0xCu)
      && (v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v6 < 0) )
    {
      v13 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v14 = 148;
    }
    else
    {
      v7 = RtlFileMapInitializeByNtPath(v5 + 1, &DestinationString);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v19 = 0;
        IoStatusBlock = 0;
        FileInformation = 0;
        v6 = ZwQueryInformationFile(v5[1], &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
        if ( v6 >= 0 )
        {
          v6 = 0;
          v5[3] = (HANDLE)*((_QWORD *)&FileInformation + 1);
          *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
          *a1 = v5;
          goto LABEL_13;
        }
        v8 = "NtQueryInformationFile failed [%x]";
        v9 = 183;
        goto LABEL_11;
      }
      if ( (unsigned int)AslFileNotFound((unsigned int)v7) )
        goto LABEL_12;
      v11 = (unsigned int)(v6 + 1073741805);
      if ( (unsigned int)v11 <= 0x30 && (v12 = 0x1000000008001LL, _bittest64(&v12, v11)) || v6 == -1073741638 )
      {
        v13 = "RtlFileMapInitializeByFilePath failed %S [%x]";
        v14 = 163;
        v15 = 3;
        goto LABEL_25;
      }
      v13 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v14 = 161;
    }
    v15 = 1;
LABEL_25:
    AslLogCallPrintf(v15, (unsigned int)"AslFileMappingCreate", v14, (_DWORD)v13);
    goto LABEL_12;
  }
  v8 = "AslStringDuplicate failed [%x]";
  v9 = 123;
LABEL_11:
  AslLogCallPrintf(1, (unsigned int)"AslFileMappingCreate", v9, (_DWORD)v8);
LABEL_12:
  AslFileMappingDelete(v5);
LABEL_13:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020c78  mov     [rsp-28h+arg_10], rbx
0x180020c7d  mov     [rsp-28h+arg_18], rsi
0x180020c82  push    rbp
0x180020c83  push    rdi
0x180020c84  push    r12
0x180020c86  push    r14
0x180020c88  push    r15
0x180020c8a  mov     rbp, rsp
0x180020c8d  sub     rsp, 70h
0x180020c91  mov     rax, cs:__security_cookie
0x180020c98  xor     rax, rsp
0x180020c9b  mov     [rbp+var_8], rax
0x180020c9f  xor     eax, eax
0x180020ca1  xorps   xmm0, xmm0
0x180020ca4  xor     r12d, r12d
0x180020ca7  mov     [rbp+var_10], rax
0x180020cab  xorps   xmm1, xmm1
0x180020cae  mov     rdi, rdx
0x180020cb1  mov     r14, rcx
0x180020cb4  movups  [rbp+FileInformation], xmm0
0x180020cb8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180020cbc  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180020cc0  test    rdx, rdx
0x180020cc3  jz      loc_180020E4B
0x180020cc9  cmp     [rdx], r12w
0x180020ccd  jz      loc_180020E4B
0x180020cd3  test    rcx, rcx
0x180020cd6  jz      loc_180020E4B
0x180020cdc  mov     [rcx], r12
0x180020cdf  lea     rcx, [rbp+DestinationString]; DestinationString
0x180020ce3  call    cs:__imp_RtlInitUnicodeString
0x180020cea  nop     dword ptr [rax+rax+00h]
0x180020cef  mov     rcx, gs:60h
0x180020cf8  lea     edx, [r12+8]; Flags
0x180020cfd  lea     r8d, [r12+50h]; Size
0x180020d02  mov     rcx, [rcx+30h]; HeapHandle
0x180020d06  call    cs:__imp_RtlAllocateHeap
0x180020d0d  nop     dword ptr [rax+rax+00h]
0x180020d12  mov     rsi, rax
0x180020d15  test    rax, rax
0x180020d18  jz      loc_180020E52
0x180020d1e  mov     rdx, rdi
0x180020d21  mov     rcx, rax
0x180020d24  call    AslStringDuplicate
0x180020d29  mov     ebx, eax
0x180020d2b  test    eax, eax
0x180020d2d  js      loc_180020EB3
0x180020d33  lea     r8d, [r12+0Ch]; MaxCount
0x180020d38  mov     rcx, rdi; String1
0x180020d3b  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x180020d42  call    _wcsnicmp_0
0x180020d47  test    eax, eax
0x180020d49  jz      short loc_180020D6E
0x180020d4b  xor     r9d, r9d
0x180020d4e  lea     rdx, [rbp+DestinationString]
0x180020d52  xor     r8d, r8d
0x180020d55  mov     rcx, rdi
0x180020d58  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180020d5f  nop     dword ptr [rax+rax+00h]
0x180020d64  mov     ebx, eax
0x180020d66  test    eax, eax
0x180020d68  js      loc_180020EC5
0x180020d6e  lea     rdx, [rbp+DestinationString]
0x180020d72  lea     rcx, [rsi+8]
0x180020d76  call    RtlFileMapInitializeByNtPath
0x180020d7b  mov     ebx, eax
0x180020d7d  test    eax, eax
0x180020d7f  js      loc_180020E59
0x180020d85  xor     eax, eax
0x180020d87  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x180020d8f  xorps   xmm0, xmm0
0x180020d92  mov     [rbp+var_10], rax
0x180020d96  xorps   xmm1, xmm1
0x180020d99  lea     r8, [rbp+FileInformation]; FileInformation
0x180020d9d  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180020da1  lea     r9d, [rax+18h]; Length
0x180020da5  movups  [rbp+FileInformation], xmm1
0x180020da9  mov     rcx, [rsi+8]; FileHandle
0x180020dad  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180020db1  call    cs:__imp_ZwQueryInformationFile
0x180020db8  nop     dword ptr [rax+rax+00h]
0x180020dbd  mov     ebx, eax
0x180020dbf  test    eax, eax
0x180020dc1  jns     short loc_180020E2B
0x180020dc3  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x180020dca  mov     r8d, 0B7h
0x180020dd0  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180020dd7  mov     [rsp+70h+FileInformationClass], eax
0x180020ddb  mov     ecx, 1
0x180020de0  call    AslLogCallPrintf
0x180020de5  mov     rcx, rsi
0x180020de8  call    AslFileMappingDelete
0x180020ded  cmp     [rbp+DestinationString.Buffer], rdi
0x180020df1  jz      short loc_180020E03
0x180020df3  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180020df7  call    cs:__imp_RtlFreeUnicodeString
0x180020dfe  nop     dword ptr [rax+rax+00h]
0x180020e03  mov     eax, ebx
0x180020e05  mov     rcx, [rbp+var_8]
0x180020e09  xor     rcx, rsp; StackCookie
0x180020e0c  call    __security_check_cookie
0x180020e11  lea     r11, [rsp+70h+var_s0]
0x180020e16  mov     rbx, [r11+40h]
0x180020e1a  mov     rsi, [r11+48h]
0x180020e1e  mov     rsp, r11
0x180020e21  pop     r15
0x180020e23  pop     r14
0x180020e25  pop     r12
0x180020e27  pop     rdi
0x180020e28  pop     rbp
0x180020e29  retn
0x180020e2b  mov     rax, qword ptr [rbp+FileInformation+8]
0x180020e2f  mov     ebx, r12d
0x180020e32  mov     [rsi+18h], rax
0x180020e36  mov     rax, qword ptr [rbp+FileInformation+8]
0x180020e3a  neg     rax
0x180020e3d  sbb     ecx, ecx
0x180020e3f  neg     ecx
0x180020e41  inc     ecx
0x180020e43  mov     [rsi+38h], ecx
0x180020e46  mov     [r14], rsi
0x180020e49  jmp     short loc_180020DED
0x180020e4b  mov     eax, 0C000000Dh
0x180020e50  jmp     short loc_180020E05
0x180020e52  mov     ebx, 0C0000017h
0x180020e57  jmp     short loc_180020DED
0x180020e59  mov     ecx, ebx
0x180020e5b  call    AslFileNotFound
0x180020e60  test    eax, eax
0x180020e62  jnz     short loc_180020DE5
0x180020e64  lea     eax, [rbx+3FFFFFEDh]
0x180020e6a  cmp     eax, 30h ; '0'
0x180020e6d  ja      short loc_180020E7F
0x180020e6f  mov     rcx, 1000000008001h
0x180020e79  bt      rcx, rax
0x180020e7d  jb      short loc_180020ED8
0x180020e7f  cmp     ebx, 0C00000BAh
0x180020e85  jz      short loc_180020ED8
0x180020e87  mov     [rsp+70h+var_48], ebx
0x180020e8b  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180020e92  mov     r8d, 0A1h
0x180020e98  mov     ecx, 1
0x180020e9d  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180020ea4  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x180020ea9  call    AslLogCallPrintf
0x180020eae  jmp     loc_180020DE5
0x180020eb3  lea     r9, aAslstringdupli_0; "AslStringDuplicate failed [%x]"
0x180020eba  mov     r8d, 7Bh ; '{'
0x180020ec0  jmp     loc_180020DD0
0x180020ec5  mov     [rsp+70h+var_48], eax
0x180020ec9  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180020ed0  mov     r8d, 94h
0x180020ed6  jmp     short loc_180020E98
0x180020ed8  mov     [rsp+70h+var_48], ebx
0x180020edc  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180020ee3  mov     r8d, 0A3h
0x180020ee9  mov     ecx, 3
0x180020eee  jmp     short loc_180020E9D
```
