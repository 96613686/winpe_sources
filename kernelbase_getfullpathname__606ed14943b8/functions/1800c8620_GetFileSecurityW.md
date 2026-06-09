# GetFileSecurityW

- ea: `0x1800c8620`
- end: `0x1800c888c`
- name: `GetFileSecurityW`
- size: `620`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x1800c8620`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c86c5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c86c5`
- `ntdll!RtlReleaseRelativeName` at `0x1800c875d`
- `ntdll!RtlReleaseRelativeName` at `0x1800c875d`
- `ntdll!NtQuerySecurityObject` at `0x1800c87a8`
- `ntdll!NtQuerySecurityObject` at `0x1800c87a8`
- `ntdll!NtOpenFile` at `0x1800c8740`
- `ntdll!NtOpenFile` at `0x1800c8879`
- `ntdll!NtOpenFile` at `0x1800c8740`
- `ntdll!NtOpenFile` at `0x1800c8879`
- `ntdll!NtClose` at `0x1800c87ba`
- `ntdll!NtClose` at `0x1800c87ba`
- `ntdll!RtlFreeHeap` at `0x1800c877b`
- `ntdll!RtlFreeHeap` at `0x1800c877b`

## pseudocode

```c
BOOL __stdcall GetFileSecurityW(
        LPCWSTR lpFileName,
        SECURITY_INFORMATION RequestedInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  int v6; // ecx
  ACCESS_MASK v10; // esi
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  NTSTATUS SecurityObject; // edi
  HANDLE FileHandle; // [rsp+30h] [rbp-41h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+38h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-29h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+58h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+7h] BYREF

  FileHandle = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  if ( (RequestedInformation & 0x10000) != 0 )
    v6 = 16908288;
  if ( (RequestedInformation & 0x17) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x20) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x40) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x80u) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x100) != 0 )
    v6 |= 0x20000u;
  v10 = v6 | 0x1000000;
  if ( (RequestedInformation & 8) == 0 )
    v10 = v6;
  if ( RtlDosPathNameToRelativeNtPathName_U(lpFileName, &NtName, 0, &RelativeName) )
  {
    Buffer = NtName.Buffer;
    if ( RelativeName.RelativeName.Length )
    {
      NtName = RelativeName.RelativeName;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    SecurityObject = NtOpenFile(&FileHandle, v10, &ObjectAttributes, &IoStatusBlock, 7u, 0x200000u);
    if ( SecurityObject == -1073741811 )
      SecurityObject = NtOpenFile(&FileHandle, v10, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( SecurityObject < 0
      || (SecurityObject = NtQuerySecurityObject(
                             FileHandle,
                             RequestedInformation,
                             pSecurityDescriptor,
                             nLength,
                             lpnLengthNeeded),
          NtClose(FileHandle),
          SecurityObject < 0) )
    {
      BaseSetLastNTError((unsigned int)SecurityObject);
      return 0;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    BaseSetLastNTError(3221225523LL);
    return 0;
  }
}

```

## disassembly

```asm
0x1800c8620  mov     [rsp-8+arg_10], rbx
0x1800c8625  mov     [rsp-8+arg_18], rsi
0x1800c862a  push    rbp
0x1800c862b  push    r12
0x1800c862d  push    r15
0x1800c862f  lea     rbp, [rsp-3Fh]
0x1800c8634  sub     rsp, 0B0h
0x1800c863b  xorps   xmm0, xmm0
0x1800c863e  mov     [rbp+4Fh+FileHandle], 0
0x1800c8646  xorps   xmm1, xmm1
0x1800c8649  mov     r10, rcx
0x1800c864c  xor     ecx, ecx
0x1800c864e  xor     eax, eax
0x1800c8650  mov     r15d, r9d
0x1800c8653  mov     r12, r8
0x1800c8656  mov     ebx, edx
0x1800c8658  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800c865c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800c8660  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800c8664  movups  xmmword ptr [rbp+4Fh+NtName.Length], xmm0
0x1800c8668  movups  xmmword ptr [rbp+4Fh+RelativeName.RelativeName.Length], xmm1
0x1800c866c  movups  xmmword ptr [rbp+4Fh+RelativeName.ContainingDirectory], xmm1
0x1800c8670  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1800c8674  bt      edx, 10h
0x1800c8678  jb      loc_1800C880A
0x1800c867e  test    bl, 17h
0x1800c8681  jz      short loc_1800C8687
0x1800c8683  bts     ecx, 11h
0x1800c8687  test    bl, 20h
0x1800c868a  jnz     loc_1800C8814
0x1800c8690  test    bl, 40h
0x1800c8693  jnz     loc_1800C881D
0x1800c8699  test    bl, bl
0x1800c869b  js      loc_1800C8826
0x1800c86a1  bt      ebx, 8
0x1800c86a5  jb      loc_1800C882F
0x1800c86ab  mov     esi, ecx
0x1800c86ad  lea     r9, [rbp+4Fh+RelativeName]; RelativeName
0x1800c86b1  bts     esi, 18h
0x1800c86b5  lea     rdx, [rbp+4Fh+NtName]; NtName
0x1800c86b9  test    bl, 8
0x1800c86bc  cmovz   esi, ecx
0x1800c86bf  xor     r8d, r8d; PartName
0x1800c86c2  mov     rcx, r10; DosName
0x1800c86c5  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800c86cc  nop     dword ptr [rax+rax+00h]
0x1800c86d1  test    al, al
0x1800c86d3  jz      loc_1800C87FC
0x1800c86d9  movzx   eax, [rbp+4Fh+RelativeName.RelativeName.Length]
0x1800c86dd  mov     [rsp+0C0h+arg_0], rdi
0x1800c86e5  mov     [rsp+0C0h+arg_8], r14
0x1800c86ed  mov     r14, [rbp+4Fh+NtName.Buffer]
0x1800c86f1  test    ax, ax
0x1800c86f4  jnz     loc_1800C8838
0x1800c86fa  xor     eax, eax
0x1800c86fc  mov     [rbp+4Fh+RelativeName.ContainingDirectory], rax
0x1800c8700  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800c8704  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800c8708  lea     rax, [rbp+4Fh+NtName]
0x1800c870c  mov     [rsp+0C0h+OpenOptions], 200000h; OpenOptions
0x1800c8714  xorps   xmm0, xmm0
0x1800c8717  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800c871b  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800c871f  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800c8726  mov     edx, esi; DesiredAccess
0x1800c8728  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800c872f  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800c8733  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800c873b  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c8740  call    cs:__imp_NtOpenFile
0x1800c8747  nop     dword ptr [rax+rax+00h]
0x1800c874c  mov     edi, eax
0x1800c874e  cmp     eax, 0C000000Dh
0x1800c8753  jz      loc_1800C885B
0x1800c8759  lea     rcx, [rbp+4Fh+RelativeName]; RelativeName
0x1800c875d  call    cs:__imp_RtlReleaseRelativeName
0x1800c8764  nop     dword ptr [rax+rax+00h]
0x1800c8769  mov     rcx, gs:60h
0x1800c8772  mov     r8, r14; P
0x1800c8775  xor     edx, edx; Flags
0x1800c8777  mov     rcx, [rcx+30h]; HeapHandle
0x1800c877b  call    cs:__imp_RtlFreeHeap
0x1800c8782  nop     dword ptr [rax+rax+00h]
0x1800c8787  mov     r14, [rsp+0C0h+arg_8]
0x1800c878f  test    edi, edi
0x1800c8791  js      short loc_1800C87F1
0x1800c8793  mov     rax, [rbp+4Fh+lpnLengthNeeded]
0x1800c8797  mov     r9d, r15d; Length
0x1800c879a  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800c879e  mov     r8, r12; SecurityDescriptor
0x1800c87a1  mov     edx, ebx; SecurityInformation
0x1800c87a3  mov     qword ptr [rsp+0C0h+ShareAccess], rax; LengthNeeded
0x1800c87a8  call    cs:__imp_NtQuerySecurityObject
0x1800c87af  nop     dword ptr [rax+rax+00h]
0x1800c87b4  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800c87b8  mov     edi, eax
0x1800c87ba  call    cs:__imp_NtClose
0x1800c87c1  nop     dword ptr [rax+rax+00h]
0x1800c87c6  test    edi, edi
0x1800c87c8  js      short loc_1800C87F1
0x1800c87ca  mov     eax, 1
0x1800c87cf  mov     rdi, [rsp+0C0h+arg_0]
0x1800c87d7  lea     r11, [rsp+0C0h+var_10]
0x1800c87df  mov     rbx, [r11+30h]
0x1800c87e3  mov     rsi, [r11+38h]
0x1800c87e7  mov     rsp, r11
0x1800c87ea  pop     r15
0x1800c87ec  pop     r12
0x1800c87ee  pop     rbp
0x1800c87ef  retn
0x1800c87f1  mov     ecx, edi
0x1800c87f3  call    BaseSetLastNTError
0x1800c87f8  xor     eax, eax
0x1800c87fa  jmp     short loc_1800C87CF
0x1800c87fc  mov     ecx, 0C0000033h
0x1800c8801  call    BaseSetLastNTError
0x1800c8806  xor     eax, eax
0x1800c8808  jmp     short loc_1800C87D7
0x1800c880a  mov     ecx, 1020000h
0x1800c880f  jmp     loc_1800C867E
0x1800c8814  bts     ecx, 11h
0x1800c8818  jmp     loc_1800C8690
0x1800c881d  bts     ecx, 11h
0x1800c8821  jmp     loc_1800C8699
0x1800c8826  bts     ecx, 11h
0x1800c882a  jmp     loc_1800C86A1
0x1800c882f  bts     ecx, 11h
0x1800c8833  jmp     loc_1800C86AB
0x1800c8838  mov     [rbp+4Fh+NtName.Length], ax
0x1800c883c  mov     eax, dword ptr [rbp+4Fh+RelativeName.RelativeName.MaximumLength]
0x1800c883f  mov     dword ptr [rbp+4Fh+NtName.MaximumLength], eax
0x1800c8842  movzx   eax, word ptr [rbp+4Fh+RelativeName.RelativeName+6]
0x1800c8846  mov     word ptr [rbp+4Fh+NtName+6], ax
0x1800c884a  mov     rax, [rbp+4Fh+RelativeName.RelativeName.Buffer]
0x1800c884e  mov     [rbp+4Fh+NtName.Buffer], rax
0x1800c8852  mov     rax, [rbp+4Fh+RelativeName.ContainingDirectory]
0x1800c8856  jmp     loc_1800C8700
0x1800c885b  mov     [rsp+0C0h+OpenOptions], 0; OpenOptions
0x1800c8863  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800c8867  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800c886b  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800c8873  mov     edx, esi; DesiredAccess
0x1800c8875  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800c8879  call    cs:__imp_NtOpenFile
0x1800c8880  nop     dword ptr [rax+rax+00h]
0x1800c8885  mov     edi, eax
0x1800c8887  jmp     loc_1800C8759
```
