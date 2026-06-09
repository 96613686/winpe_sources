# BfsInitializeBootDevice

- ea: `0x140003b0c`
- end: `0x140003caa`
- name: `BfsInitializeBootDevice`
- size: `414`
- prototype: `__int64 __fastcall(PUNICODE_STRING LinkTarget)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140003b0c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003bd4`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003c41`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003bd4`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003c41`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140003ba0`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140003ba0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003b61`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003bf8`
- `ntoskrnl!ExAllocatePool2` at `0x140003c12`
- `ntoskrnl!ExAllocatePool2` at `0x140003c12`

## pseudocode

```c
__int64 __fastcall BfsInitializeBootDevice(PUNICODE_STRING LinkTarget)
{
  NTSTATUS v2; // eax
  int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  int v6; // ecx
  PWSTR Buffer; // rcx
  WCHAR *Pool2; // rax
  void *v9; // rcx
  int v11; // [rsp+20h] [rbp-49h]
  unsigned int v12; // [rsp+30h] [rbp-39h] BYREF
  ULONG ReturnedLength; // [rsp+34h] [rbp-35h] BYREF
  void *LinkHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+80h] [rbp+17h] BYREF
  unsigned int *v18; // [rsp+A0h] [rbp+37h]
  __int64 v19; // [rsp+A8h] [rbp+3Fh]

  LinkHandle = 0;
  ReturnedLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\BootDevice");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  v5 = v2;
  if ( v2 < 0 )
  {
    v6 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = v2;
LABEL_13:
      v19 = 4;
      v18 = &v12;
      tlgWriteTransfer_EtwWriteTransfer(v6, (int)&byte_140016D91, v3, v4, v11, &v17);
      return v5;
    }
    return v5;
  }
  v5 = ZwQuerySymbolicLinkObject(LinkHandle, LinkTarget, &ReturnedLength);
  if ( v5 != -1073741789 )
    goto LABEL_10;
  Buffer = LinkTarget->Buffer;
  if ( Buffer )
  {
    *(_DWORD *)&LinkTarget->Length = 0;
    ExFreePoolWithTag(Buffer, 0);
  }
  Pool2 = (WCHAR *)ExAllocatePool2(256, ReturnedLength, 1181967938);
  LinkTarget->Buffer = Pool2;
  if ( Pool2 )
  {
    v9 = LinkHandle;
    LinkTarget->MaximumLength = ReturnedLength;
    v5 = ZwQuerySymbolicLinkObject(v9, LinkTarget, &ReturnedLength);
LABEL_10:
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    goto LABEL_11;
  }
  v5 = -1073741801;
LABEL_11:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v12 = v5;
    goto LABEL_13;
  }
  return v5;
}

```

## disassembly

```asm
0x140003b0c  mov     [rsp-8+arg_8], rbx
0x140003b11  mov     [rsp-8+arg_10], rdi
0x140003b16  push    rbp
0x140003b17  lea     rbp, [rsp-57h]
0x140003b1c  sub     rsp, 0C0h
0x140003b23  mov     rax, cs:__security_cookie
0x140003b2a  xor     rax, rsp
0x140003b2d  mov     [rbp+57h+var_10], rax
0x140003b31  xorps   xmm0, xmm0
0x140003b34  mov     [rbp+57h+LinkHandle], 0
0x140003b3c  mov     rdi, rcx
0x140003b3f  mov     [rbp+57h+ReturnedLength], 0
0x140003b46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140003b4a  lea     rdx, SourceString; "\\Device\\BootDevice"
0x140003b51  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140003b55  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140003b59  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003b5d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140003b61  call    cs:__imp_RtlInitUnicodeString
0x140003b68  nop     dword ptr [rax+rax+00h]
0x140003b6d  lea     rax, [rbp+57h+DestinationString]
0x140003b71  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140003b78  xorps   xmm0, xmm0
0x140003b7b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140003b7f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140003b83  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140003b8b  mov     edx, 1; DesiredAccess
0x140003b90  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140003b97  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003b9b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003ba0  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140003ba7  nop     dword ptr [rax+rax+00h]
0x140003bac  mov     ebx, eax
0x140003bae  test    eax, eax
0x140003bb0  jns     short loc_140003BC9
0x140003bb2  mov     ecx, cs:dword_140019000
0x140003bb8  cmp     ecx, 3
0x140003bbb  jbe     loc_140003C86
0x140003bc1  mov     [rbp+57h+var_90], eax
0x140003bc4  jmp     loc_140003C61
0x140003bc9  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003bcd  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140003bd1  mov     rdx, rdi; LinkTarget
0x140003bd4  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140003bdb  nop     dword ptr [rax+rax+00h]
0x140003be0  mov     ebx, eax
0x140003be2  cmp     eax, 0C0000023h
0x140003be7  jnz     short loc_140003C4F
0x140003be9  mov     rcx, [rdi+8]; P
0x140003bed  test    rcx, rcx
0x140003bf0  jz      short loc_140003C04
0x140003bf2  xor     eax, eax
0x140003bf4  xor     edx, edx; Tag
0x140003bf6  mov     [rdi], eax
0x140003bf8  call    cs:__imp_ExFreePoolWithTag
0x140003bff  nop     dword ptr [rax+rax+00h]
0x140003c04  mov     edx, [rbp+57h+ReturnedLength]
0x140003c07  mov     ecx, 100h
0x140003c0c  mov     r8d, 46736642h
0x140003c12  call    cs:__imp_ExAllocatePool2
0x140003c19  nop     dword ptr [rax+rax+00h]
0x140003c1e  mov     [rdi+8], rax
0x140003c22  test    rax, rax
0x140003c25  jnz     short loc_140003C2E
0x140003c27  mov     ebx, 0C0000017h
0x140003c2c  jmp     short loc_140003C53
0x140003c2e  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x140003c32  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140003c36  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003c3a  mov     rdx, rdi; LinkTarget
0x140003c3d  mov     [rdi+2], ax
0x140003c41  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140003c48  nop     dword ptr [rax+rax+00h]
0x140003c4d  mov     ebx, eax
0x140003c4f  test    ebx, ebx
0x140003c51  jns     short loc_140003C86
0x140003c53  mov     eax, cs:dword_140019000
0x140003c59  cmp     eax, 3
0x140003c5c  jbe     short loc_140003C86
0x140003c5e  mov     [rbp+57h+var_90], ebx
0x140003c61  lea     rax, [rbp+57h+var_90]
0x140003c65  mov     [rbp+57h+var_18], 4
0x140003c6d  mov     [rbp+57h+var_20], rax
0x140003c71  lea     rdx, byte_140016D91; int
0x140003c78  lea     rax, [rbp+57h+var_40]
0x140003c7c  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x140003c81  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003c86  mov     eax, ebx
0x140003c88  mov     rcx, [rbp+57h+var_10]
0x140003c8c  xor     rcx, rsp; StackCookie
0x140003c8f  call    __security_check_cookie
0x140003c94  lea     r11, [rsp+0C0h+var_s0]
0x140003c9c  mov     rbx, [r11+18h]
0x140003ca0  mov     rdi, [r11+20h]
0x140003ca4  mov     rsp, r11
0x140003ca7  pop     rbp
0x140003ca8  retn
```
