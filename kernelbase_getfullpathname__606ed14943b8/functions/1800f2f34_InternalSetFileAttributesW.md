# InternalSetFileAttributesW

- ea: `0x1800f2f34`
- end: `0x1800f319d`
- name: `InternalSetFileAttributesW`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f2f00`

## callees

- `0x18004b9d0`
- `0x1800f2f34`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x1800f3029`
- `ntdll!RtlReleaseRelativeName` at `0x1800f30e1`
- `ntdll!RtlReleaseRelativeName` at `0x1800f3029`
- `ntdll!RtlReleaseRelativeName` at `0x1800f30e1`
- `ntdll!NtOpenFile` at `0x1800f300f`
- `ntdll!NtOpenFile` at `0x1800f3165`
- `ntdll!NtOpenFile` at `0x1800f300f`
- `ntdll!NtOpenFile` at `0x1800f3165`
- `ntdll!NtSetInformationFile` at `0x1800f3089`
- `ntdll!NtSetInformationFile` at `0x1800f3089`
- `ntdll!RtlSetLastWin32Error` at `0x1800f318c`
- `ntdll!RtlSetLastWin32Error` at `0x1800f318c`
- `ntdll!NtClose` at `0x1800f309b`
- `ntdll!NtClose` at `0x1800f309b`
- `ntdll!RtlFreeHeap` at `0x1800f3047`
- `ntdll!RtlFreeHeap` at `0x1800f30ff`
- `ntdll!RtlFreeHeap` at `0x1800f3047`
- `ntdll!RtlFreeHeap` at `0x1800f30ff`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800f2fa0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800f2fa0`

## pseudocode

```c
__int64 __fastcall InternalSetFileAttributesW(__int64 a1, int a2)
{
  int v3; // eax
  PVOID v4; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v6; // ebx
  __int64 v8; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-69h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-61h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+48h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+B8h] [rbp+1Fh]
  __int64 v16; // [rsp+C8h] [rbp+2Fh]

  v16 = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v15 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v3 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( v3 < 0 )
  {
    if ( v3 != -1073741801 && v3 != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return 0;
    }
    v8 = (unsigned int)v3;
  }
  else
  {
    v4 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v6 >= 0
      || v6 == -1073741811
      && (v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u), v6 >= 0) )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      v16 = a2 & 0x1A3127 | 0x80u;
      FileInformation = 0;
      v15 = 0;
      v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
      NtClose(FileHandle);
      if ( v6 >= 0 )
        return 1;
    }
    else
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    v8 = (unsigned int)v6;
  }
  BaseSetLastNTError(v8);
  return 0;
}

```

## disassembly

```asm
0x1800f2f34  mov     [rsp-8+arg_10], rbx
0x1800f2f39  mov     [rsp-8+arg_18], rsi
0x1800f2f3e  push    rbp
0x1800f2f3f  push    rdi
0x1800f2f40  push    r14
0x1800f2f42  lea     rbp, [rsp-47h]
0x1800f2f47  sub     rsp, 0E0h
0x1800f2f4e  mov     rax, cs:__security_cookie
0x1800f2f55  xor     rax, rsp
0x1800f2f58  mov     [rbp+57h+var_20], rax
0x1800f2f5c  xorps   xmm0, xmm0
0x1800f2f5f  lea     r9, [rbp+57h+RelativeName]
0x1800f2f63  mov     esi, edx
0x1800f2f65  xor     eax, eax
0x1800f2f67  xorps   xmm1, xmm1
0x1800f2f6a  mov     [rbp+57h+var_28], rax
0x1800f2f6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f2f72  xor     r14d, r14d
0x1800f2f75  lea     rdx, [rbp+57h+P]
0x1800f2f79  xor     r8d, r8d
0x1800f2f7c  mov     [rbp+57h+FileHandle], r14
0x1800f2f80  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800f2f84  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f2f88  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800f2f8c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800f2f90  movups  [rbp+57h+FileInformation], xmm0
0x1800f2f94  movups  [rbp+57h+var_38], xmm0
0x1800f2f98  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800f2f9c  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800f2fa0  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800f2fa7  nop     dword ptr [rax+rax+00h]
0x1800f2fac  test    eax, eax
0x1800f2fae  js      loc_1800F3116
0x1800f2fb4  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800f2fb8  mov     rdi, [rbp+57h+P+8]
0x1800f2fbc  test    ax, ax
0x1800f2fbf  jnz     loc_1800F3121
0x1800f2fc5  mov     eax, r14d
0x1800f2fc8  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800f2fcc  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800f2fd0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f2fd4  lea     rax, [rbp+57h+P]
0x1800f2fd8  mov     [rsp+0F0h+OpenOptions], 204020h; OpenOptions
0x1800f2fe0  xorps   xmm0, xmm0
0x1800f2fe3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f2fe7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f2feb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f2ff2  mov     edx, 100100h; DesiredAccess
0x1800f2ff7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f2ffe  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f3002  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800f300a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f300f  call    cs:__imp_NtOpenFile
0x1800f3016  nop     dword ptr [rax+rax+00h]
0x1800f301b  mov     ebx, eax
0x1800f301d  test    eax, eax
0x1800f301f  js      loc_1800F30D5
0x1800f3025  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800f3029  call    cs:__imp_RtlReleaseRelativeName
0x1800f3030  nop     dword ptr [rax+rax+00h]
0x1800f3035  mov     rcx, gs:60h
0x1800f303e  mov     r8, rdi; P
0x1800f3041  xor     edx, edx; Flags
0x1800f3043  mov     rcx, [rcx+30h]; HeapHandle
0x1800f3047  call    cs:__imp_RtlFreeHeap
0x1800f304e  nop     dword ptr [rax+rax+00h]
0x1800f3053  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f3057  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800f305b  xor     eax, eax
0x1800f305d  mov     [rsp+0F0h+ShareAccess], 4; FileInformationClass
0x1800f3065  xorps   xmm0, xmm0
0x1800f3068  mov     [rbp+57h+var_28], rax
0x1800f306c  and     esi, 1A3127h
0x1800f3072  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f3076  bts     esi, 7
0x1800f307a  lea     r9d, [rax+28h]; Length
0x1800f307e  mov     dword ptr [rbp+57h+var_28], esi
0x1800f3081  movups  [rbp+57h+FileInformation], xmm0
0x1800f3085  movups  [rbp+57h+var_38], xmm0
0x1800f3089  call    cs:__imp_NtSetInformationFile
0x1800f3090  nop     dword ptr [rax+rax+00h]
0x1800f3095  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f3099  mov     ebx, eax
0x1800f309b  call    cs:__imp_NtClose
0x1800f30a2  nop     dword ptr [rax+rax+00h]
0x1800f30a7  test    ebx, ebx
0x1800f30a9  js      short loc_1800F310B
0x1800f30ab  mov     eax, 1
0x1800f30b0  mov     rcx, [rbp+57h+var_20]
0x1800f30b4  xor     rcx, rsp; StackCookie
0x1800f30b7  call    __security_check_cookie
0x1800f30bc  lea     r11, [rsp+0F0h+var_10]
0x1800f30c4  mov     rbx, [r11+30h]
0x1800f30c8  mov     rsi, [r11+38h]
0x1800f30cc  mov     rsp, r11
0x1800f30cf  pop     r14
0x1800f30d1  pop     rdi
0x1800f30d2  pop     rbp
0x1800f30d3  retn
0x1800f30d5  cmp     ebx, 0C000000Dh
0x1800f30db  jz      short loc_1800F3144
0x1800f30dd  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800f30e1  call    cs:__imp_RtlReleaseRelativeName
0x1800f30e8  nop     dword ptr [rax+rax+00h]
0x1800f30ed  mov     rcx, gs:60h
0x1800f30f6  mov     r8, rdi; P
0x1800f30f9  xor     edx, edx; Flags
0x1800f30fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800f30ff  call    cs:__imp_RtlFreeHeap
0x1800f3106  nop     dword ptr [rax+rax+00h]
0x1800f310b  mov     ecx, ebx
0x1800f310d  call    BaseSetLastNTError
0x1800f3112  xor     eax, eax
0x1800f3114  jmp     short loc_1800F30B0
0x1800f3116  cmp     eax, 0C0000017h
0x1800f311b  jnz     short loc_1800F3180
0x1800f311d  mov     ecx, eax
0x1800f311f  jmp     short loc_1800F310D
0x1800f3121  mov     word ptr [rbp+57h+P], ax
0x1800f3125  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800f3128  mov     dword ptr [rbp+57h+P+2], eax
0x1800f312b  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800f312f  mov     word ptr [rbp+57h+P+6], ax
0x1800f3133  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800f3137  mov     [rbp+57h+P+8], rax
0x1800f313b  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800f313f  jmp     loc_1800F2FCC
0x1800f3144  mov     [rsp+0F0h+OpenOptions], 4020h; OpenOptions
0x1800f314c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f3150  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f3154  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800f315c  mov     edx, 100100h; DesiredAccess
0x1800f3161  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f3165  call    cs:__imp_NtOpenFile
0x1800f316c  nop     dword ptr [rax+rax+00h]
0x1800f3171  mov     ebx, eax
0x1800f3173  test    eax, eax
0x1800f3175  js      loc_1800F30DD
0x1800f317b  jmp     loc_1800F3025
0x1800f3180  cmp     eax, 0C000009Ah
0x1800f3185  jz      short loc_1800F311D
0x1800f3187  mov     ecx, 3; LastError
0x1800f318c  call    cs:__imp_RtlSetLastWin32Error
0x1800f3193  nop     dword ptr [rax+rax+00h]
0x1800f3198  jmp     loc_1800F3112
```
