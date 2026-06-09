# BasepOpenFileForMove

- ea: `0x180044c1c`
- end: `0x180044dcd`
- name: `BasepOpenFileForMove`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054940`

## callees

- `0x180044c1c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180044d0f`
- `ntdll!NtOpenFile` at `0x180044da2`
- `ntdll!NtOpenFile` at `0x180044d0f`
- `ntdll!NtOpenFile` at `0x180044da2`
- `ntdll!NtClose` at `0x180044d72`
- `ntdll!NtClose` at `0x180044d72`
- `ntdll!NtQueryInformationFile` at `0x180044d4b`
- `ntdll!NtQueryInformationFile` at `0x180044d4b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180044c5f`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180044c5f`
- `ntdll!RtlReleaseRelativeName` at `0x180044db7`
- `ntdll!RtlReleaseRelativeName` at `0x18007b42e`
- `ntdll!RtlReleaseRelativeName` at `0x180044db7`
- `ntdll!RtlReleaseRelativeName` at `0x18007b42e`

## pseudocode

```c
__int64 __fastcall BasepOpenFileForMove(
        const WCHAR *a1,
        __int64 a2,
        _QWORD *a3,
        void **a4,
        POBJECT_ATTRIBUTES ObjectAttributes,
        int a6)
{
  int v9; // esi
  NTSTATUS v10; // ebx
  HANDLE ContainingDirectory; // rax
  NTSTATUS v12; // eax
  __int64 FileInformation; // [rsp+38h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-68h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-58h] BYREF

  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  v9 = 0;
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *a3 = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(a1, (PUNICODE_STRING)a2, 0, &RelativeName) )
  {
    v10 = -1073741766;
    goto LABEL_14;
  }
  v9 = 1;
  *a3 = *(_QWORD *)(a2 + 8);
  if ( RelativeName.RelativeName.Length )
  {
    *(_WORD *)a2 = RelativeName.RelativeName.Length;
    *(_QWORD *)(a2 + 2) = *(_QWORD *)&RelativeName.RelativeName.MaximumLength;
    *(_DWORD *)(a2 + 10) = *(_DWORD *)((char *)&RelativeName.RelativeName.Buffer + 2);
    *(_WORD *)(a2 + 14) = HIWORD(RelativeName.RelativeName.Buffer);
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes->Length = 48;
  ObjectAttributes->RootDirectory = ContainingDirectory;
  ObjectAttributes->Attributes = 64;
  ObjectAttributes->ObjectName = (PUNICODE_STRING)a2;
  ObjectAttributes->SecurityDescriptor = 0;
  ObjectAttributes->SecurityQualityOfService = 0;
  v12 = NtOpenFile(a4, a6 | 0x100080, ObjectAttributes, &IoStatusBlock, 7u, 0x604020u);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( v12 != -1073741811 )
      goto LABEL_14;
LABEL_13:
    v10 = NtOpenFile(a4, a6 | 0x100000, ObjectAttributes, &IoStatusBlock, 7u, 0x404020u);
    goto LABEL_14;
  }
  FileInformation = 0;
  v10 = NtQueryInformationFile(*a4, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v10 >= 0 && (FileInformation & 0x400) != 0 && HIDWORD(FileInformation) != -1610612733 )
  {
    NtClose(*a4);
    *a4 = (void *)-1LL;
    goto LABEL_13;
  }
LABEL_14:
  if ( v9 )
    RtlReleaseRelativeName(&RelativeName);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180044c1c  mov     rax, rsp
0x180044c1f  push    rbx
0x180044c20  push    rsi
0x180044c21  push    rdi
0x180044c22  push    r12
0x180044c24  push    r14
0x180044c26  push    r15
0x180044c28  sub     rsp, 78h
0x180044c2c  mov     r15, r9
0x180044c2f  mov     rdi, r8
0x180044c32  mov     rbx, rdx
0x180044c35  xorps   xmm0, xmm0
0x180044c38  movups  xmmword ptr [rax-58h], xmm0
0x180044c3c  movups  xmmword ptr [rax-48h], xmm0
0x180044c40  movups  xmmword ptr [rax-68h], xmm0
0x180044c44  xor     r12d, r12d
0x180044c47  mov     esi, r12d
0x180044c4a  mov     [rax-74h], r12d
0x180044c4e  mov     [rdx], r12d
0x180044c51  mov     [rdx+8], r12
0x180044c55  mov     [r8], r12
0x180044c58  lea     r9, [rax-58h]; RelativeName
0x180044c5c  xor     r8d, r8d; PartName
0x180044c5f  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180044c65  test    al, al
0x180044c67  jnz     short loc_180044C77
0x180044c69  mov     ebx, 0C000003Ah
0x180044c6e  mov     [rsp+0A8h+var_78], ebx
0x180044c72  jmp     loc_180044DAE
0x180044c77  mov     esi, 1
0x180044c7c  mov     [rsp+0A8h+var_74], esi
0x180044c80  mov     rax, [rbx+8]
0x180044c84  mov     [rdi], rax
0x180044c87  movzx   eax, [rsp+0A8h+RelativeName.RelativeName.Length]
0x180044c8c  test    ax, ax
0x180044c8f  jz      short loc_180044CB6
0x180044c91  mov     [rbx], ax
0x180044c94  movsd   xmm0, qword ptr [rsp+0A8h+RelativeName.RelativeName.MaximumLength]
0x180044c9a  movsd   qword ptr [rbx+2], xmm0
0x180044c9f  mov     eax, dword ptr [rsp+0A8h+RelativeName.RelativeName.Buffer+2]
0x180044ca3  mov     [rbx+0Ah], eax
0x180044ca6  movzx   eax, word ptr [rsp+0A8h+RelativeName.RelativeName.Buffer+6]
0x180044cab  mov     [rbx+0Eh], ax
0x180044caf  mov     rax, [rsp+0A8h+RelativeName.ContainingDirectory]
0x180044cb4  jmp     short loc_180044CBE
0x180044cb6  mov     rax, r12
0x180044cb9  mov     [rsp+0A8h+RelativeName.ContainingDirectory], rax
0x180044cbe  mov     rdi, [rsp+0A8h+ObjectAttributes]
0x180044cc6  mov     dword ptr [rdi], 30h ; '0'
0x180044ccc  mov     [rdi+8], rax
0x180044cd0  mov     dword ptr [rdi+18h], 40h ; '@'
0x180044cd7  mov     [rdi+10h], rbx
0x180044cdb  mov     [rdi+20h], r12
0x180044cdf  mov     [rdi+28h], r12
0x180044ce3  mov     r14d, [rsp+0A8h+arg_28]
0x180044ceb  mov     edx, r14d
0x180044cee  or      edx, 100080h; DesiredAccess
0x180044cf4  mov     [rsp+0A8h+OpenOptions], 604020h; OpenOptions
0x180044cfc  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x180044d04  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x180044d09  mov     r8, rdi; ObjectAttributes
0x180044d0c  mov     rcx, r15; FileHandle
0x180044d0f  call    cs:__imp_NtOpenFile
0x180044d15  mov     ebx, eax
0x180044d17  mov     [rsp+0A8h+var_78], eax
0x180044d1b  test    eax, eax
0x180044d1d  jns     short loc_180044D2B
0x180044d1f  cmp     eax, 0C000000Dh
0x180044d24  jz      short loc_180044D7F
0x180044d26  jmp     loc_180044DAE
0x180044d2b  mov     [rsp+0A8h+FileInformation], r12
0x180044d30  mov     [rsp+0A8h+ShareAccess], 23h ; '#'; FileInformationClass
0x180044d38  mov     r9d, 8; Length
0x180044d3e  lea     r8, [rsp+0A8h+FileInformation]; FileInformation
0x180044d43  lea     rdx, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x180044d48  mov     rcx, [r15]; FileHandle
0x180044d4b  call    cs:__imp_NtQueryInformationFile
0x180044d51  mov     ebx, eax
0x180044d53  mov     [rsp+0A8h+var_78], eax
0x180044d57  test    eax, eax
0x180044d59  js      short loc_180044DAE
0x180044d5b  test    dword ptr [rsp+0A8h+FileInformation], 400h
0x180044d63  jz      short loc_180044DAE
0x180044d65  cmp     dword ptr [rsp+0A8h+FileInformation+4], 0A0000003h
0x180044d6d  jz      short loc_180044DAE
0x180044d6f  mov     rcx, [r15]; Handle
0x180044d72  call    cs:__imp_NtClose
0x180044d78  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x180044d7f  mov     [rsp+0A8h+OpenOptions], 404020h; OpenOptions
0x180044d87  bts     r14d, 14h
0x180044d8c  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x180044d94  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x180044d99  mov     r8, rdi; ObjectAttributes
0x180044d9c  mov     edx, r14d; DesiredAccess
0x180044d9f  mov     rcx, r15; FileHandle
0x180044da2  call    cs:__imp_NtOpenFile
0x180044da8  mov     [rsp+0A8h+var_78], eax
0x180044dac  mov     ebx, eax
0x180044dae  test    esi, esi
0x180044db0  jz      short loc_180044DBD
0x180044db2  lea     rcx, [rsp+0A8h+RelativeName]; RelativeName
0x180044db7  call    cs:__imp_RtlReleaseRelativeName
0x180044dbd  mov     eax, ebx
0x180044dbf  add     rsp, 78h
0x180044dc3  pop     r15
0x180044dc5  pop     r14
0x180044dc7  pop     r12
0x180044dc9  pop     rdi
0x180044dca  pop     rsi
0x180044dcb  pop     rbx
0x180044dcc  retn
0x18007b41b  push    rbp
0x18007b41d  sub     rsp, 30h
0x18007b421  mov     rbp, rdx
0x18007b424  cmp     dword ptr [rbp+34h], 0
0x18007b428  jz      short loc_18007B435
0x18007b42a  lea     rcx, [rbp+50h]; RelativeName
0x18007b42e  call    cs:__imp_RtlReleaseRelativeName
0x18007b434  nop
0x18007b435  add     rsp, 30h
0x18007b439  pop     rbp
0x18007b43a  retn
```
