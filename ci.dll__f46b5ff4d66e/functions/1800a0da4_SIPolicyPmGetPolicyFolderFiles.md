# SIPolicyPmGetPolicyFolderFiles

- ea: `0x1800a0da4`
- end: `0x1800a0fc7`
- name: `SIPolicyPmGetPolicyFolderFiles`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007cfa0`
- `0x1800a0c2c`

## callees

- `0x18002bef0`
- `0x180078438`
- `0x1800a00c0`
- `0x1800a0da4`
- `0x1800e1aac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a0e53`
- `ntoskrnl!ExAllocatePool2` at `0x1800a0e53`
- `ntoskrnl!ZwOpenFile` at `0x1800a0e2d`
- `ntoskrnl!ZwOpenFile` at `0x1800a0e2d`
- `ntoskrnl!ZwClose` at `0x1800a0f71`
- `ntoskrnl!ZwClose` at `0x1800a0f71`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a0ead`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a0ead`

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
0x1800a0da4  mov     [rsp-8+arg_0], rbx
0x1800a0da9  push    rbp
0x1800a0daa  push    rsi
0x1800a0dab  push    rdi
0x1800a0dac  push    r12
0x1800a0dae  push    r13
0x1800a0db0  push    r14
0x1800a0db2  push    r15
0x1800a0db4  lea     rbp, [rsp-7]
0x1800a0db9  sub     rsp, 0E0h
0x1800a0dc0  mov     rax, cs:__security_cookie
0x1800a0dc7  xor     rax, rsp
0x1800a0dca  mov     [rbp+37h+var_40], rax
0x1800a0dce  mov     r15, [rbp+37h+arg_28]
0x1800a0dd2  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800a0dd6  mov     r12, [rbp+37h+arg_38]
0x1800a0dda  xor     ecx, ecx
0x1800a0ddc  xorps   xmm0, xmm0
0x1800a0ddf  mov     [rbp+37h+FileHandle], rcx
0x1800a0de3  mov     esi, ecx
0x1800a0de5  mov     [rbp+37h+ObjectAttributes.RootDirectory], rcx
0x1800a0de9  mov     r14, r8
0x1800a0dec  mov     [rbp+37h+var_98], r8
0x1800a0df0  mov     r13, rdx
0x1800a0df3  mov     [rbp+37h+ObjectAttributes.ObjectName], rdx
0x1800a0df7  lea     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800a0dfb  mov     [rsp+110h+OpenOptions], 4021h; OpenOptions
0x1800a0e03  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800a0e07  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800a0e0f  mov     edx, 100001h; DesiredAccess
0x1800a0e14  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 240h
0x1800a0e1c  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x1800a0e20  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800a0e28  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a0e2d  call    cs:__imp_ZwOpenFile
0x1800a0e34  nop     dword ptr [rax+rax+00h]
0x1800a0e39  mov     ebx, eax
0x1800a0e3b  test    eax, eax
0x1800a0e3d  js      loc_1800A0F68
0x1800a0e43  mov     edx, 250h
0x1800a0e48  mov     ecx, 100h
0x1800a0e4d  mov     r8d, 69734943h
0x1800a0e53  call    cs:__imp_ExAllocatePool2
0x1800a0e5a  nop     dword ptr [rax+rax+00h]
0x1800a0e5f  mov     rsi, rax
0x1800a0e62  test    rax, rax
0x1800a0e65  jnz     short loc_1800A0E71
0x1800a0e67  mov     ebx, 0C0000017h
0x1800a0e6c  jmp     loc_1800A0F68
0x1800a0e71  mov     al, 1
0x1800a0e73  xor     edi, edi
0x1800a0e75  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800a0e79  xor     r9d, r9d; ApcContext
0x1800a0e7c  mov     [rsp+110h+RestartScan], al; RestartScan
0x1800a0e80  xor     r8d, r8d; ApcRoutine
0x1800a0e83  mov     [rsp+110h+FileName], r14; FileName
0x1800a0e88  lea     rax, [rbp+37h+IoStatusBlock]
0x1800a0e8c  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1800a0e91  xor     edx, edx; Event
0x1800a0e93  mov     [rsp+110h+FileInformationClass], 1; FileInformationClass
0x1800a0e9b  mov     [rsp+110h+Length], 250h; Length
0x1800a0ea3  mov     qword ptr [rsp+110h+OpenOptions], rsi; FileInformation
0x1800a0ea8  mov     qword ptr [rsp+110h+ShareAccess], rax; IoStatusBlock
0x1800a0ead  call    cs:__imp_ZwQueryDirectoryFile
0x1800a0eb4  nop     dword ptr [rax+rax+00h]
0x1800a0eb9  mov     ebx, eax
0x1800a0ebb  test    eax, eax
0x1800a0ebd  js      loc_1800A0F54
0x1800a0ec3  cmp     [rbp+37h+IoStatusBlock.Information], 0
0x1800a0ec8  jz      loc_1800A0F64
0x1800a0ece  test    r15, r15
0x1800a0ed1  jz      short loc_1800A0ED8
0x1800a0ed3  cmp     edi, [rbp+37h+arg_30]
0x1800a0ed6  jnb     short loc_1800A0F4D
0x1800a0ed8  cmp     [rbp+37h+arg_20], 0
0x1800a0edc  lea     rax, [rsi+40h]
0x1800a0ee0  movzx   ecx, word ptr [rsi+3Ch]
0x1800a0ee4  xorps   xmm0, xmm0
0x1800a0ee7  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x1800a0eeb  mov     [rbp+37h+String2.Length], cx
0x1800a0eef  mov     [rbp+37h+String2.Buffer], rax
0x1800a0ef3  mov     [rbp+37h+String2.MaximumLength], cx
0x1800a0ef7  jz      short loc_1800A0F0E
0x1800a0ef9  lea     rdx, [rbp+37h+Guid]; Guid
0x1800a0efd  lea     rcx, [rbp+37h+String2]; String2
0x1800a0f01  movups  xmmword ptr [rbp+37h+Guid.Data1], xmm0
0x1800a0f05  call    SIPolicyIsValidPolicyFileName
0x1800a0f0a  test    eax, eax
0x1800a0f0c  js      short loc_1800A0F46
0x1800a0f0e  test    r15, r15
0x1800a0f11  jz      short loc_1800A0F44
0x1800a0f13  lea     rcx, [rdi+rdi*2]
0x1800a0f17  lea     r14, [r15+rcx*8]
0x1800a0f1b  mov     rcx, r13; Source
0x1800a0f1e  mov     r8, r14
0x1800a0f21  lea     rdx, [rbp+37h+String2]; PCUNICODE_STRING
0x1800a0f25  call    SIPolicyBuildPath
0x1800a0f2a  mov     ebx, eax
0x1800a0f2c  test    eax, eax
0x1800a0f2e  js      short loc_1800A0F68
0x1800a0f30  mov     al, [r13+10h]
0x1800a0f34  mov     [r14+10h], al
0x1800a0f38  mov     al, [r13+11h]
0x1800a0f3c  mov     [r14+11h], al
0x1800a0f40  mov     r14, [rbp+37h+var_98]
0x1800a0f44  inc     edi
0x1800a0f46  xor     al, al
0x1800a0f48  jmp     loc_1800A0E75
0x1800a0f4d  mov     ebx, 0C000009Ah
0x1800a0f52  jmp     short loc_1800A0F68
0x1800a0f54  cmp     eax, 80000006h
0x1800a0f59  jz      short loc_1800A0F62
0x1800a0f5b  cmp     eax, 0C000000Fh
0x1800a0f60  jnz     short loc_1800A0F68
0x1800a0f62  xor     ebx, ebx
0x1800a0f64  mov     [r12], edi
0x1800a0f68  mov     rcx, [rbp+37h+FileHandle]; Handle
0x1800a0f6c  test    rcx, rcx
0x1800a0f6f  jz      short loc_1800A0F7D
0x1800a0f71  call    cs:__imp_ZwClose
0x1800a0f78  nop     dword ptr [rax+rax+00h]
0x1800a0f7d  mov     rcx, rsi
0x1800a0f80  call    SIPolicyFree
0x1800a0f85  cmp     ebx, 0C0000034h
0x1800a0f8b  jz      short loc_1800A0F98
0x1800a0f8d  lea     eax, [rbx+3FFFFFC6h]
0x1800a0f93  cmp     eax, 1
0x1800a0f96  ja      short loc_1800A0F9D
0x1800a0f98  mov     ebx, 0C0000225h
0x1800a0f9d  mov     eax, ebx
0x1800a0f9f  mov     rcx, [rbp+37h+var_40]
0x1800a0fa3  xor     rcx, rsp; StackCookie
0x1800a0fa6  call    __security_check_cookie
0x1800a0fab  mov     rbx, [rsp+110h+arg_0]
0x1800a0fb3  add     rsp, 0E0h
0x1800a0fba  pop     r15
0x1800a0fbc  pop     r14
0x1800a0fbe  pop     r13
0x1800a0fc0  pop     r12
0x1800a0fc2  pop     rdi
0x1800a0fc3  pop     rsi
0x1800a0fc4  pop     rbp
0x1800a0fc5  retn
```
