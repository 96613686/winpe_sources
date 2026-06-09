# SIPolicyPmGetPolicyFolderFiles

- ea: `0x1800e38f8`
- end: `0x1800e3b1b`
- name: `SIPolicyPmGetPolicyFolderFiles`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007ef64`
- `0x1800e3780`

## callees

- `0x18002c0d0`
- `0x180079cf8`
- `0x180091e90`
- `0x1800e2a68`
- `0x1800e38f8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e39a7`
- `ntoskrnl!ExAllocatePool2` at `0x1800e39a7`
- `ntoskrnl!ZwOpenFile` at `0x1800e3981`
- `ntoskrnl!ZwOpenFile` at `0x1800e3981`
- `ntoskrnl!ZwClose` at `0x1800e3ac5`
- `ntoskrnl!ZwClose` at `0x1800e3ac5`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800e3a01`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800e3a01`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetPolicyFolderFiles(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        char a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  WCHAR *Pool2; // rsi
  struct _UNICODE_STRING *FileName; // r14
  NTSTATUS v11; // ebx
  BOOLEAN RestartScan; // al
  __int64 v13; // rdi
  NTSTATUS v14; // eax
  USHORT v15; // cx
  __int64 v16; // r14
  void *FileHandle; // [rsp+60h] [rbp-79h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-71h] BYREF
  struct _UNICODE_STRING *v20; // [rsp+78h] [rbp-61h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-49h] BYREF
  GUID Guid; // [rsp+C0h] [rbp-19h] BYREF

  FileHandle = 0;
  Pool2 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileName = a3;
  v20 = a3;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v11 >= 0 )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, 592, 1769163075);
    if ( Pool2 )
    {
      RestartScan = 1;
      v13 = 0;
      while ( 1 )
      {
        v14 = ZwQueryDirectoryFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                Pool2,
                0x250u,
                FileDirectoryInformation,
                1u,
                FileName,
                RestartScan);
        v11 = v14;
        if ( v14 < 0 )
          break;
        if ( !IoStatusBlock.Information )
          goto LABEL_20;
        if ( a6 && (unsigned int)v13 >= a7 )
        {
          v11 = -1073741670;
          goto LABEL_21;
        }
        v15 = Pool2[30];
        *(_DWORD *)(&String2.MaximumLength + 1) = 0;
        String2.Length = v15;
        String2.Buffer = Pool2 + 32;
        String2.MaximumLength = v15;
        if ( !a5 || (Guid = 0, (int)SIPolicyIsValidPolicyFileName(&String2, &Guid) >= 0) )
        {
          if ( a6 )
          {
            v16 = a6 + 24 * v13;
            v11 = SIPolicyBuildPath((PCUNICODE_STRING)a2, &String2);
            if ( v11 < 0 )
              goto LABEL_21;
            *(_BYTE *)(v16 + 16) = *(_BYTE *)(a2 + 16);
            *(_BYTE *)(v16 + 17) = *(_BYTE *)(a2 + 17);
            FileName = v20;
          }
          v13 = (unsigned int)(v13 + 1);
        }
        RestartScan = 0;
      }
      if ( v14 == -2147483642 || v14 == -1073741809 )
      {
        v11 = 0;
LABEL_20:
        *a8 = v13;
      }
    }
    else
    {
      v11 = -1073741801;
    }
  }
LABEL_21:
  if ( FileHandle )
    ZwClose(FileHandle);
  SIPolicyFree(Pool2);
  if ( v11 == -1073741772 || (unsigned int)(v11 + 1073741766) <= 1 )
    return (unsigned int)-1073741275;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800e38f8  mov     [rsp-8+arg_0], rbx
0x1800e38fd  push    rbp
0x1800e38fe  push    rsi
0x1800e38ff  push    rdi
0x1800e3900  push    r12
0x1800e3902  push    r13
0x1800e3904  push    r14
0x1800e3906  push    r15
0x1800e3908  lea     rbp, [rsp-7]
0x1800e390d  sub     rsp, 0E0h
0x1800e3914  mov     rax, cs:__security_cookie
0x1800e391b  xor     rax, rsp
0x1800e391e  mov     [rbp+37h+var_40], rax
0x1800e3922  mov     r15, [rbp+37h+arg_28]
0x1800e3926  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800e392a  mov     r12, [rbp+37h+arg_38]
0x1800e392e  xor     ecx, ecx
0x1800e3930  xorps   xmm0, xmm0
0x1800e3933  mov     [rbp+37h+FileHandle], rcx
0x1800e3937  mov     esi, ecx
0x1800e3939  mov     [rbp+37h+ObjectAttributes.RootDirectory], rcx
0x1800e393d  mov     r14, r8
0x1800e3940  mov     [rbp+37h+var_98], r8
0x1800e3944  mov     r13, rdx
0x1800e3947  mov     [rbp+37h+ObjectAttributes.ObjectName], rdx
0x1800e394b  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800e394f  mov     [rsp+110h+OpenOptions], 4021h; OpenOptions
0x1800e3957  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800e395b  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800e3963  mov     edx, 100001h; DesiredAccess
0x1800e3968  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 240h
0x1800e3970  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x1800e3974  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800e397c  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e3981  call    cs:__imp_ZwOpenFile
0x1800e3988  nop     dword ptr [rax+rax+00h]
0x1800e398d  mov     ebx, eax
0x1800e398f  test    eax, eax
0x1800e3991  js      loc_1800E3ABC
0x1800e3997  mov     edx, 250h
0x1800e399c  mov     ecx, 100h
0x1800e39a1  mov     r8d, 69734943h
0x1800e39a7  call    cs:__imp_ExAllocatePool2
0x1800e39ae  nop     dword ptr [rax+rax+00h]
0x1800e39b3  mov     rsi, rax
0x1800e39b6  test    rax, rax
0x1800e39b9  jnz     short loc_1800E39C5
0x1800e39bb  mov     ebx, 0C0000017h
0x1800e39c0  jmp     loc_1800E3ABC
0x1800e39c5  mov     al, 1
0x1800e39c7  xor     edi, edi
0x1800e39c9  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800e39cd  xor     r9d, r9d; ApcContext
0x1800e39d0  mov     [rsp+110h+RestartScan], al; RestartScan
0x1800e39d4  xor     r8d, r8d; ApcRoutine
0x1800e39d7  mov     [rsp+110h+FileName], r14; FileName
0x1800e39dc  lea     rax, [rbp+37h+IoStatusBlock]
0x1800e39e0  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800e39e5  xor     edx, edx; Event
0x1800e39e7  mov     [rsp+110h+FileInformationClass], 1; FileInformationClass
0x1800e39ef  mov     [rsp+110h+Length], 250h; Length
0x1800e39f7  mov     qword ptr [rsp+110h+OpenOptions], rsi; FileInformation
0x1800e39fc  mov     qword ptr [rsp+110h+ShareAccess], rax; IoStatusBlock
0x1800e3a01  call    cs:__imp_ZwQueryDirectoryFile
0x1800e3a08  nop     dword ptr [rax+rax+00h]
0x1800e3a0d  mov     ebx, eax
0x1800e3a0f  test    eax, eax
0x1800e3a11  js      loc_1800E3AA8
0x1800e3a17  cmp     [rbp+37h+IoStatusBlock.Information], 0
0x1800e3a1c  jz      loc_1800E3AB8
0x1800e3a22  test    r15, r15
0x1800e3a25  jz      short loc_1800E3A2C
0x1800e3a27  cmp     edi, [rbp+37h+arg_30]
0x1800e3a2a  jnb     short loc_1800E3AA1
0x1800e3a2c  cmp     [rbp+37h+arg_20], 0
0x1800e3a30  lea     rax, [rsi+40h]
0x1800e3a34  movzx   ecx, word ptr [rsi+3Ch]
0x1800e3a38  xorps   xmm0, xmm0
0x1800e3a3b  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x1800e3a3f  mov     [rbp+37h+String2.Length], cx
0x1800e3a43  mov     [rbp+37h+String2.Buffer], rax
0x1800e3a47  mov     [rbp+37h+String2.MaximumLength], cx
0x1800e3a4b  jz      short loc_1800E3A62
0x1800e3a4d  lea     rdx, [rbp+37h+Guid]; Guid
0x1800e3a51  lea     rcx, [rbp+37h+String2]; String2
0x1800e3a55  movups  xmmword ptr [rbp+37h+Guid.Data1], xmm0
0x1800e3a59  call    SIPolicyIsValidPolicyFileName
0x1800e3a5e  test    eax, eax
0x1800e3a60  js      short loc_1800E3A9A
0x1800e3a62  test    r15, r15
0x1800e3a65  jz      short loc_1800E3A98
0x1800e3a67  lea     rcx, [rdi+rdi*2]
0x1800e3a6b  lea     r14, [r15+rcx*8]
0x1800e3a6f  mov     rcx, r13; Source
0x1800e3a72  mov     r8, r14
0x1800e3a75  lea     rdx, [rbp+37h+String2]; PCUNICODE_STRING
0x1800e3a79  call    SIPolicyBuildPath
0x1800e3a7e  mov     ebx, eax
0x1800e3a80  test    eax, eax
0x1800e3a82  js      short loc_1800E3ABC
0x1800e3a84  mov     al, [r13+10h]
0x1800e3a88  mov     [r14+10h], al
0x1800e3a8c  mov     al, [r13+11h]
0x1800e3a90  mov     [r14+11h], al
0x1800e3a94  mov     r14, [rbp+37h+var_98]
0x1800e3a98  inc     edi
0x1800e3a9a  xor     al, al
0x1800e3a9c  jmp     loc_1800E39C9
0x1800e3aa1  mov     ebx, 0C000009Ah
0x1800e3aa6  jmp     short loc_1800E3ABC
0x1800e3aa8  cmp     eax, 80000006h
0x1800e3aad  jz      short loc_1800E3AB6
0x1800e3aaf  cmp     eax, 0C000000Fh
0x1800e3ab4  jnz     short loc_1800E3ABC
0x1800e3ab6  xor     ebx, ebx
0x1800e3ab8  mov     [r12], edi
0x1800e3abc  mov     rcx, [rbp+37h+FileHandle]; Handle
0x1800e3ac0  test    rcx, rcx
0x1800e3ac3  jz      short loc_1800E3AD1
0x1800e3ac5  call    cs:__imp_ZwClose
0x1800e3acc  nop     dword ptr [rax+rax+00h]
0x1800e3ad1  mov     rcx, rsi
0x1800e3ad4  call    SIPolicyFree
0x1800e3ad9  cmp     ebx, 0C0000034h
0x1800e3adf  jz      short loc_1800E3AEC
0x1800e3ae1  lea     eax, [rbx+3FFFFFC6h]
0x1800e3ae7  cmp     eax, 1
0x1800e3aea  ja      short loc_1800E3AF1
0x1800e3aec  mov     ebx, 0C0000225h
0x1800e3af1  mov     eax, ebx
0x1800e3af3  mov     rcx, [rbp+37h+var_40]
0x1800e3af7  xor     rcx, rsp; StackCookie
0x1800e3afa  call    __security_check_cookie
0x1800e3aff  mov     rbx, [rsp+110h+arg_0]
0x1800e3b07  add     rsp, 0E0h
0x1800e3b0e  pop     r15
0x1800e3b10  pop     r14
0x1800e3b12  pop     r13
0x1800e3b14  pop     r12
0x1800e3b16  pop     rdi
0x1800e3b17  pop     rsi
0x1800e3b18  pop     rbp
0x1800e3b19  retn
```
