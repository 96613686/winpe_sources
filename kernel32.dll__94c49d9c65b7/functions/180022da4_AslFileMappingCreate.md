# AslFileMappingCreate

- ea: `0x180022da4`
- end: `0x180022ffd`
- name: `AslFileMappingCreate`
- size: `601`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x180022a34`
- `0x180077160`
- `0x180077bec`
- `0x180078100`

## callees

- `0x1800212e4`
- `0x1800214b4`
- `0x1800218bc`
- `0x180022da4`
- `0x180024204`
- `0x18005741c`
- `0x18005c414`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180022e78`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180022e78`
- `ntdll!RtlFreeUnicodeString` at `0x180022f0b`
- `ntdll!RtlFreeUnicodeString` at `0x180022f0b`
- `ntdll!ZwQueryInformationFile` at `0x180022ecb`
- `ntdll!ZwQueryInformationFile` at `0x180022ecb`
- `ntdll!RtlInitUnicodeString` at `0x180022e0f`
- `ntdll!RtlInitUnicodeString` at `0x180022e0f`
- `ntdll!RtlAllocateHeap` at `0x180022e2c`
- `ntdll!RtlAllocateHeap` at `0x180022e2c`

## string_xrefs

- `0x180022ee4`: `AslFileMappingCreate`
- `0x180022faa`: `AslFileMappingCreate`
- `0x180022f98`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180022fe9`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180022fd6`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`

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
0x180022da4  mov     [rsp-28h+arg_10], rbx
0x180022da9  mov     [rsp-28h+arg_18], rsi
0x180022dae  push    rbp
0x180022daf  push    rdi
0x180022db0  push    r12
0x180022db2  push    r14
0x180022db4  push    r15
0x180022db6  mov     rbp, rsp
0x180022db9  sub     rsp, 70h
0x180022dbd  mov     rax, cs:__security_cookie
0x180022dc4  xor     rax, rsp
0x180022dc7  mov     [rbp+var_8], rax
0x180022dcb  xor     eax, eax
0x180022dcd  xorps   xmm0, xmm0
0x180022dd0  xor     r12d, r12d
0x180022dd3  mov     [rbp+var_10], rax
0x180022dd7  xorps   xmm1, xmm1
0x180022dda  mov     rdi, rdx
0x180022ddd  mov     r14, rcx
0x180022de0  movups  [rbp+FileInformation], xmm0
0x180022de4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180022de8  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180022dec  test    rdx, rdx
0x180022def  jz      loc_180022F58
0x180022df5  cmp     [rdx], r12w
0x180022df9  jz      loc_180022F58
0x180022dff  test    rcx, rcx
0x180022e02  jz      loc_180022F58
0x180022e08  mov     [rcx], r12
0x180022e0b  lea     rcx, [rbp+DestinationString]; DestinationString
0x180022e0f  call    cs:__imp_RtlInitUnicodeString
0x180022e15  mov     rcx, gs:60h
0x180022e1e  lea     edx, [r12+8]; Flags
0x180022e23  lea     r8d, [r12+50h]; Size
0x180022e28  mov     rcx, [rcx+30h]; HeapHandle
0x180022e2c  call    cs:__imp_RtlAllocateHeap
0x180022e32  mov     rsi, rax
0x180022e35  test    rax, rax
0x180022e38  jz      loc_180022F5F
0x180022e3e  mov     rdx, rdi
0x180022e41  mov     rcx, rax
0x180022e44  call    AslStringDuplicate
0x180022e49  mov     ebx, eax
0x180022e4b  test    eax, eax
0x180022e4d  js      loc_180022FC0
0x180022e53  lea     r8d, [r12+0Ch]; MaxCount
0x180022e58  mov     rcx, rdi; String1
0x180022e5b  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x180022e62  call    _wcsnicmp_0
0x180022e67  test    eax, eax
0x180022e69  jz      short loc_180022E88
0x180022e6b  xor     r9d, r9d
0x180022e6e  lea     rdx, [rbp+DestinationString]
0x180022e72  xor     r8d, r8d
0x180022e75  mov     rcx, rdi
0x180022e78  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180022e7e  mov     ebx, eax
0x180022e80  test    eax, eax
0x180022e82  js      loc_180022FD2
0x180022e88  lea     rdx, [rbp+DestinationString]
0x180022e8c  lea     rcx, [rsi+8]
0x180022e90  call    RtlFileMapInitializeByNtPath
0x180022e95  mov     ebx, eax
0x180022e97  test    eax, eax
0x180022e99  js      loc_180022F66
0x180022e9f  xor     eax, eax
0x180022ea1  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x180022ea9  xorps   xmm0, xmm0
0x180022eac  mov     [rbp+var_10], rax
0x180022eb0  xorps   xmm1, xmm1
0x180022eb3  lea     r8, [rbp+FileInformation]; FileInformation
0x180022eb7  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180022ebb  lea     r9d, [rax+18h]; Length
0x180022ebf  movups  [rbp+FileInformation], xmm1
0x180022ec3  mov     rcx, [rsi+8]; FileHandle
0x180022ec7  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180022ecb  call    cs:__imp_ZwQueryInformationFile
0x180022ed1  mov     ebx, eax
0x180022ed3  test    eax, eax
0x180022ed5  jns     short loc_180022F38
0x180022ed7  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x180022ede  mov     r8d, 0B7h
0x180022ee4  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180022eeb  mov     [rsp+70h+FileInformationClass], eax
0x180022eef  mov     ecx, 1
0x180022ef4  call    AslLogCallPrintf
0x180022ef9  mov     rcx, rsi
0x180022efc  call    AslFileMappingDelete
0x180022f01  cmp     [rbp+DestinationString.Buffer], rdi
0x180022f05  jz      short loc_180022F11
0x180022f07  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180022f0b  call    cs:__imp_RtlFreeUnicodeString
0x180022f11  mov     eax, ebx
0x180022f13  mov     rcx, [rbp+var_8]
0x180022f17  xor     rcx, rsp; StackCookie
0x180022f1a  call    __security_check_cookie
0x180022f1f  lea     r11, [rsp+70h+var_s0]
0x180022f24  mov     rbx, [r11+40h]
0x180022f28  mov     rsi, [r11+48h]
0x180022f2c  mov     rsp, r11
0x180022f2f  pop     r15
0x180022f31  pop     r14
0x180022f33  pop     r12
0x180022f35  pop     rdi
0x180022f36  pop     rbp
0x180022f37  retn
0x180022f38  mov     rax, qword ptr [rbp+FileInformation+8]
0x180022f3c  mov     ebx, r12d
0x180022f3f  mov     [rsi+18h], rax
0x180022f43  mov     rax, qword ptr [rbp+FileInformation+8]
0x180022f47  neg     rax
0x180022f4a  sbb     ecx, ecx
0x180022f4c  neg     ecx
0x180022f4e  inc     ecx
0x180022f50  mov     [rsi+38h], ecx
0x180022f53  mov     [r14], rsi
0x180022f56  jmp     short loc_180022F01
0x180022f58  mov     eax, 0C000000Dh
0x180022f5d  jmp     short loc_180022F13
0x180022f5f  mov     ebx, 0C0000017h
0x180022f64  jmp     short loc_180022F01
0x180022f66  mov     ecx, ebx
0x180022f68  call    AslFileNotFound
0x180022f6d  test    eax, eax
0x180022f6f  jnz     short loc_180022EF9
0x180022f71  lea     eax, [rbx+3FFFFFEDh]
0x180022f77  cmp     eax, 30h ; '0'
0x180022f7a  ja      short loc_180022F8C
0x180022f7c  mov     rcx, 1000000008001h
0x180022f86  bt      rcx, rax
0x180022f8a  jb      short loc_180022FE5
0x180022f8c  cmp     ebx, 0C00000BAh
0x180022f92  jz      short loc_180022FE5
0x180022f94  mov     [rsp+70h+var_48], ebx
0x180022f98  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180022f9f  mov     r8d, 0A1h
0x180022fa5  mov     ecx, 1
0x180022faa  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180022fb1  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x180022fb6  call    AslLogCallPrintf
0x180022fbb  jmp     loc_180022EF9
0x180022fc0  lea     r9, aAslstringdupli_0; "AslStringDuplicate failed [%x]"
0x180022fc7  mov     r8d, 7Bh ; '{'
0x180022fcd  jmp     loc_180022EE4
0x180022fd2  mov     [rsp+70h+var_48], eax
0x180022fd6  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180022fdd  mov     r8d, 94h
0x180022fe3  jmp     short loc_180022FA5
0x180022fe5  mov     [rsp+70h+var_48], ebx
0x180022fe9  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180022ff0  mov     r8d, 0A3h
0x180022ff6  mov     ecx, 3
0x180022ffb  jmp     short loc_180022FAA
```
