# BaseRegLoadKeyInternal

- ea: `0x18001c180`
- end: `0x18001c345`
- name: `BaseRegLoadKeyInternal`
- size: `453`
- prototype: `ULONG __fastcall(void *, struct _UNICODE_STRING *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800198d0`

## callees

- `0x18001c180`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c28b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c28b`
- `ntdll!NtLoadKey` at `0x18001c2f7`
- `ntdll!NtLoadKey` at `0x18001c2f7`
- `ntdll!RtlReleaseRelativeName` at `0x18001c303`
- `ntdll!RtlReleaseRelativeName` at `0x18001c303`
- `ntdll!RtlNtStatusToDosError` at `0x18001c323`
- `ntdll!RtlNtStatusToDosError` at `0x18001c323`
- `ntdll!RtlFreeHeap` at `0x18001c31b`
- `ntdll!RtlFreeHeap` at `0x18001c31b`

## pseudocode

```c
ULONG __fastcall BaseRegLoadKeyInternal(void *a1, struct _UNICODE_STRING *a2, unsigned __int16 *a3)
{
  __int64 v5; // rcx
  USHORT Length; // cx
  PWSTR Buffer; // r8
  const WCHAR *v8; // rcx
  PWSTR v9; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v11; // ebx
  struct _UNICODE_STRING NtName; // [rsp+20h] [rbp-39h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+30h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES FileObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+80h] [rbp+27h] BYREF

  memset(&KeyObjectAttributes, 0, 44);
  memset(&FileObjectAttributes, 0, 44);
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( !a1 )
    return 87;
  if ( !a3 )
    return 87;
  v5 = *((_QWORD *)a3 + 1);
  if ( !v5 || !*a3 || (*(_BYTE *)a3 & 1) != 0 || *(_WORD *)(v5 + 2 * ((unsigned __int64)*a3 >> 1) - 2) )
    return 87;
  if ( a2 )
  {
    Length = a2->Length;
    if ( a2->Length )
    {
      if ( (Length & 1) == 0 )
      {
        Buffer = a2->Buffer;
        if ( !Buffer || !Buffer[((unsigned __int64)a2->Length >> 1) - 1] )
        {
          a2->Length = Length - 2;
          goto LABEL_14;
        }
      }
    }
    return 87;
  }
  a2 = 0;
LABEL_14:
  if ( *a3 )
    *a3 -= 2;
  v8 = (const WCHAR *)*((_QWORD *)a3 + 1);
  KeyObjectAttributes.RootDirectory = a1;
  KeyObjectAttributes.ObjectName = a2;
  KeyObjectAttributes.Length = 48;
  KeyObjectAttributes.Attributes = 64;
  *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(v8, &NtName, 0, &RelativeName) )
    return 87;
  v9 = NtName.Buffer;
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
  FileObjectAttributes.RootDirectory = ContainingDirectory;
  FileObjectAttributes.Length = 48;
  FileObjectAttributes.ObjectName = &NtName;
  FileObjectAttributes.Attributes = 64;
  *(_OWORD *)&FileObjectAttributes.SecurityDescriptor = 0;
  v11 = NtLoadKey(&KeyObjectAttributes, &FileObjectAttributes);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return RtlNtStatusToDosError(v11);
}

```

## disassembly

```asm
0x18001c180  mov     [rsp-8+arg_0], rbx
0x18001c185  mov     [rsp-8+arg_8], rdi
0x18001c18a  push    rbp
0x18001c18b  lea     rbp, [rsp-57h]
0x18001c190  sub     rsp, 0B0h
0x18001c197  xorps   xmm0, xmm0
0x18001c19a  xorps   xmm1, xmm1
0x18001c19d  xor     eax, eax
0x18001c19f  xor     ebx, ebx
0x18001c1a1  mov     r10, r8
0x18001c1a4  mov     r9, rcx
0x18001c1a7  movups  xmmword ptr [rbp+57h+KeyObjectAttributes.ObjectName], xmm0
0x18001c1ab  movups  xmmword ptr [rbp+57h+FileObjectAttributes.ObjectName], xmm0
0x18001c1af  movups  xmmword ptr [rbp+57h+KeyObjectAttributes+1Ch], xmm0
0x18001c1b3  movups  xmmword ptr [rbp+57h+FileObjectAttributes+1Ch], xmm0
0x18001c1b7  movups  xmmword ptr [rbp+57h+KeyObjectAttributes.Length], xmm0
0x18001c1bb  movups  xmmword ptr [rbp+57h+FileObjectAttributes.Length], xmm0
0x18001c1bf  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18001c1c3  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18001c1c7  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18001c1cb  test    rcx, rcx
0x18001c1ce  jz      loc_18001C32B
0x18001c1d4  test    r8, r8
0x18001c1d7  jz      loc_18001C32B
0x18001c1dd  mov     rcx, [r8+8]
0x18001c1e1  test    rcx, rcx
0x18001c1e4  jz      loc_18001C32B
0x18001c1ea  cmp     [r8], bx
0x18001c1ee  jz      loc_18001C32B
0x18001c1f4  test    byte ptr [r8], 1
0x18001c1f8  jnz     loc_18001C32B
0x18001c1fe  movzx   eax, word ptr [r8]
0x18001c202  shr     rax, 1
0x18001c205  cmp     [rcx+rax*2-2], bx
0x18001c20a  jnz     loc_18001C32B
0x18001c210  test    rdx, rdx
0x18001c213  jz      short loc_18001C24D
0x18001c215  movzx   ecx, word ptr [rdx]
0x18001c218  test    cx, cx
0x18001c21b  jz      loc_18001C32B
0x18001c221  test    cl, 1
0x18001c224  jnz     loc_18001C32B
0x18001c22a  mov     r8, [rdx+8]
0x18001c22e  test    r8, r8
0x18001c231  jz      short loc_18001C244
0x18001c233  mov     eax, ecx
0x18001c235  shr     rax, 1
0x18001c238  cmp     [r8+rax*2-2], bx
0x18001c23e  jnz     loc_18001C32B
0x18001c244  sub     cx, 2
0x18001c248  mov     [rdx], cx
0x18001c24b  jmp     short loc_18001C250
0x18001c24d  mov     rdx, rbx
0x18001c250  movzx   eax, word ptr [r10]
0x18001c254  test    ax, ax
0x18001c257  jz      short loc_18001C261
0x18001c259  sub     ax, 2
0x18001c25d  mov     [r10], ax
0x18001c261  mov     rcx, [r10+8]; DosName
0x18001c265  xor     r8d, r8d; PartName
0x18001c268  mov     [rbp+57h+KeyObjectAttributes.RootDirectory], r9
0x18001c26c  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18001c270  mov     [rbp+57h+KeyObjectAttributes.ObjectName], rdx
0x18001c274  lea     rdx, [rbp+57h+NtName]; NtName
0x18001c278  mov     [rbp+57h+KeyObjectAttributes.Length], 30h ; '0'
0x18001c27f  mov     [rbp+57h+KeyObjectAttributes.Attributes], 40h ; '@'
0x18001c286  movdqu  xmmword ptr [rbp+57h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x18001c28b  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001c291  test    al, al
0x18001c293  jz      loc_18001C32B
0x18001c299  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18001c29d  mov     rdi, [rbp+57h+NtName.Buffer]
0x18001c2a1  test    ax, ax
0x18001c2a4  jz      short loc_18001C2C6
0x18001c2a6  mov     [rbp+57h+NtName.Length], ax
0x18001c2aa  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18001c2ad  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18001c2b0  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18001c2b4  mov     word ptr [rbp+57h+NtName+6], ax
0x18001c2b8  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18001c2bc  mov     [rbp+57h+NtName.Buffer], rax
0x18001c2c0  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18001c2c4  jmp     short loc_18001C2CD
0x18001c2c6  mov     rax, rbx
0x18001c2c9  mov     [rbp+57h+RelativeName.ContainingDirectory], rbx
0x18001c2cd  mov     [rbp+57h+FileObjectAttributes.RootDirectory], rax
0x18001c2d1  lea     rdx, [rbp+57h+FileObjectAttributes]; FileObjectAttributes
0x18001c2d5  lea     rax, [rbp+57h+NtName]
0x18001c2d9  mov     [rbp+57h+FileObjectAttributes.Length], 30h ; '0'
0x18001c2e0  xorps   xmm0, xmm0
0x18001c2e3  mov     [rbp+57h+FileObjectAttributes.ObjectName], rax
0x18001c2e7  lea     rcx, [rbp+57h+KeyObjectAttributes]; KeyObjectAttributes
0x18001c2eb  mov     [rbp+57h+FileObjectAttributes.Attributes], 40h ; '@'
0x18001c2f2  movdqu  xmmword ptr [rbp+57h+FileObjectAttributes.SecurityDescriptor], xmm0
0x18001c2f7  call    cs:__imp_NtLoadKey
0x18001c2fd  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18001c301  mov     ebx, eax
0x18001c303  call    cs:__imp_RtlReleaseRelativeName
0x18001c309  mov     rcx, gs:60h
0x18001c312  mov     r8, rdi; P
0x18001c315  xor     edx, edx; Flags
0x18001c317  mov     rcx, [rcx+30h]; HeapHandle
0x18001c31b  call    cs:__imp_RtlFreeHeap
0x18001c321  mov     ecx, ebx; Status
0x18001c323  call    cs:__imp_RtlNtStatusToDosError
0x18001c329  jmp     short loc_18001C330
0x18001c32b  mov     eax, 57h ; 'W'
0x18001c330  lea     r11, [rsp+0B0h+var_s0]
0x18001c338  mov     rbx, [r11+10h]
0x18001c33c  mov     rdi, [r11+18h]
0x18001c340  mov     rsp, r11
0x18001c343  pop     rbp
0x18001c344  retn
```
