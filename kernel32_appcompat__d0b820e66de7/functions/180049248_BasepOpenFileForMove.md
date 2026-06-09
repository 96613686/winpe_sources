# BasepOpenFileForMove

- ea: `0x180049248`
- end: `0x18004941e`
- name: `BasepOpenFileForMove`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800598f0`

## callees

- `0x180049248`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180049341`
- `ntdll!NtOpenFile` at `0x1800493e6`
- `ntdll!NtOpenFile` at `0x180049341`
- `ntdll!NtOpenFile` at `0x1800493e6`
- `ntdll!NtClose` at `0x1800493b0`
- `ntdll!NtClose` at `0x1800493b0`
- `ntdll!NtQueryInformationFile` at `0x180049383`
- `ntdll!NtQueryInformationFile` at `0x180049383`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18004928b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18004928b`
- `ntdll!RtlReleaseRelativeName` at `0x180049401`
- `ntdll!RtlReleaseRelativeName` at `0x1800834e7`
- `ntdll!RtlReleaseRelativeName` at `0x180049401`
- `ntdll!RtlReleaseRelativeName` at `0x1800834e7`

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
0x180049248  mov     rax, rsp
0x18004924b  push    rbx
0x18004924c  push    rsi
0x18004924d  push    rdi
0x18004924e  push    r12
0x180049250  push    r14
0x180049252  push    r15
0x180049254  sub     rsp, 78h
0x180049258  mov     r15, r9
0x18004925b  mov     rdi, r8
0x18004925e  mov     rbx, rdx
0x180049261  xorps   xmm0, xmm0
0x180049264  movups  xmmword ptr [rax-58h], xmm0
0x180049268  movups  xmmword ptr [rax-48h], xmm0
0x18004926c  movups  xmmword ptr [rax-68h], xmm0
0x180049270  xor     r12d, r12d
0x180049273  mov     esi, r12d
0x180049276  mov     [rax-74h], r12d
0x18004927a  mov     [rdx], r12d
0x18004927d  mov     [rdx+8], r12
0x180049281  mov     [r8], r12
0x180049284  lea     r9, [rax-58h]; RelativeName
0x180049288  xor     r8d, r8d; PartName
0x18004928b  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180049292  nop     dword ptr [rax+rax+00h]
0x180049297  test    al, al
0x180049299  jnz     short loc_1800492A9
0x18004929b  mov     ebx, 0C000003Ah
0x1800492a0  mov     [rsp+0A8h+var_78], ebx
0x1800492a4  jmp     loc_1800493F8
0x1800492a9  mov     esi, 1
0x1800492ae  mov     [rsp+0A8h+var_74], esi
0x1800492b2  mov     rax, [rbx+8]
0x1800492b6  mov     [rdi], rax
0x1800492b9  movzx   eax, [rsp+0A8h+RelativeName.RelativeName.Length]
0x1800492be  test    ax, ax
0x1800492c1  jz      short loc_1800492E8
0x1800492c3  mov     [rbx], ax
0x1800492c6  movsd   xmm0, qword ptr [rsp+0A8h+RelativeName.RelativeName.MaximumLength]
0x1800492cc  movsd   qword ptr [rbx+2], xmm0
0x1800492d1  mov     eax, dword ptr [rsp+0A8h+RelativeName.RelativeName.Buffer+2]
0x1800492d5  mov     [rbx+0Ah], eax
0x1800492d8  movzx   eax, word ptr [rsp+0A8h+RelativeName.RelativeName.Buffer+6]
0x1800492dd  mov     [rbx+0Eh], ax
0x1800492e1  mov     rax, [rsp+0A8h+RelativeName.ContainingDirectory]
0x1800492e6  jmp     short loc_1800492F0
0x1800492e8  mov     rax, r12
0x1800492eb  mov     [rsp+0A8h+RelativeName.ContainingDirectory], rax
0x1800492f0  mov     rdi, [rsp+0A8h+ObjectAttributes]
0x1800492f8  mov     dword ptr [rdi], 30h ; '0'
0x1800492fe  mov     [rdi+8], rax
0x180049302  mov     dword ptr [rdi+18h], 40h ; '@'
0x180049309  mov     [rdi+10h], rbx
0x18004930d  mov     [rdi+20h], r12
0x180049311  mov     [rdi+28h], r12
0x180049315  mov     r14d, [rsp+0A8h+arg_28]
0x18004931d  mov     edx, r14d
0x180049320  or      edx, 100080h; DesiredAccess
0x180049326  mov     [rsp+0A8h+OpenOptions], 604020h; OpenOptions
0x18004932e  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x180049336  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x18004933b  mov     r8, rdi; ObjectAttributes
0x18004933e  mov     rcx, r15; FileHandle
0x180049341  call    cs:__imp_NtOpenFile
0x180049348  nop     dword ptr [rax+rax+00h]
0x18004934d  mov     ebx, eax
0x18004934f  mov     [rsp+0A8h+var_78], eax
0x180049353  test    eax, eax
0x180049355  jns     short loc_180049363
0x180049357  cmp     eax, 0C000000Dh
0x18004935c  jz      short loc_1800493C3
0x18004935e  jmp     loc_1800493F8
0x180049363  mov     [rsp+0A8h+FileInformation], r12
0x180049368  mov     [rsp+0A8h+ShareAccess], 23h ; '#'; FileInformationClass
0x180049370  mov     r9d, 8; Length
0x180049376  lea     r8, [rsp+0A8h+FileInformation]; FileInformation
0x18004937b  lea     rdx, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x180049380  mov     rcx, [r15]; FileHandle
0x180049383  call    cs:__imp_NtQueryInformationFile
0x18004938a  nop     dword ptr [rax+rax+00h]
0x18004938f  mov     ebx, eax
0x180049391  mov     [rsp+0A8h+var_78], eax
0x180049395  test    eax, eax
0x180049397  js      short loc_1800493F8
0x180049399  test    dword ptr [rsp+0A8h+FileInformation], 400h
0x1800493a1  jz      short loc_1800493F8
0x1800493a3  cmp     dword ptr [rsp+0A8h+FileInformation+4], 0A0000003h
0x1800493ab  jz      short loc_1800493F8
0x1800493ad  mov     rcx, [r15]; Handle
0x1800493b0  call    cs:__imp_NtClose
0x1800493b7  nop     dword ptr [rax+rax+00h]
0x1800493bc  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800493c3  mov     [rsp+0A8h+OpenOptions], 404020h; OpenOptions
0x1800493cb  bts     r14d, 14h
0x1800493d0  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x1800493d8  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x1800493dd  mov     r8, rdi; ObjectAttributes
0x1800493e0  mov     edx, r14d; DesiredAccess
0x1800493e3  mov     rcx, r15; FileHandle
0x1800493e6  call    cs:__imp_NtOpenFile
0x1800493ed  nop     dword ptr [rax+rax+00h]
0x1800493f2  mov     [rsp+0A8h+var_78], eax
0x1800493f6  mov     ebx, eax
0x1800493f8  test    esi, esi
0x1800493fa  jz      short loc_18004940D
0x1800493fc  lea     rcx, [rsp+0A8h+RelativeName]; RelativeName
0x180049401  call    cs:__imp_RtlReleaseRelativeName
0x180049408  nop     dword ptr [rax+rax+00h]
0x18004940d  mov     eax, ebx
0x18004940f  add     rsp, 78h
0x180049413  pop     r15
0x180049415  pop     r14
0x180049417  pop     r12
0x180049419  pop     rdi
0x18004941a  pop     rsi
0x18004941b  pop     rbx
0x18004941c  retn
0x1800834d4  push    rbp
0x1800834d6  sub     rsp, 30h
0x1800834da  mov     rbp, rdx
0x1800834dd  cmp     dword ptr [rbp+34h], 0
0x1800834e1  jz      short loc_1800834F4
0x1800834e3  lea     rcx, [rbp+50h]; RelativeName
0x1800834e7  call    cs:__imp_RtlReleaseRelativeName
0x1800834ee  nop     dword ptr [rax+rax+00h]
0x1800834f3  nop
0x1800834f4  add     rsp, 30h
0x1800834f8  pop     rbp
0x1800834f9  retn
```
