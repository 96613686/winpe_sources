# RxCreateDosDeviceSymbolicLink

- ea: `0x14001ec2c`
- end: `0x14001ed40`
- name: `RxCreateDosDeviceSymbolicLink`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140052bb0`

## callees

- `0x14001ec2c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001ecbd`
- `ntoskrnl!ExAllocatePool2` at `0x14001ecbd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ecf7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001ecf7`
- `ntoskrnl!ZwClose` at `0x14001ed28`
- `ntoskrnl!ZwClose` at `0x14001ed28`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14001ec88`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14001ec88`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14001ecdd`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x14001ecdd`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001ec3e`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001ec3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ed10`

## pseudocode

```c
__int64 __fastcall RxCreateDosDeviceSymbolicLink(UNICODE_STRING *a1, UNICODE_STRING *a2)
{
  unsigned int SymbolicLink; // ebx
  unsigned __int16 v5; // ax
  UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *LinkHandle; // [rsp+A0h] [rbp+38h] BYREF

  SymbolicLink = IoCreateSymbolicLink(a1, a2);
  if ( SymbolicLink == -1073741771 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    LinkHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes) >= 0 )
    {
      v5 = a2->MaximumLength + 2;
      *(_QWORD *)&LinkTarget.Length = 0;
      LinkTarget.MaximumLength = v5;
      LinkTarget.Buffer = (wchar_t *)ExAllocatePool2(258, v5, 1934456914);
      if ( LinkTarget.Buffer )
      {
        if ( ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, 0) >= 0 && RtlEqualUnicodeString(a2, &LinkTarget, 1u) )
          SymbolicLink = 0;
        ExFreePoolWithTag(LinkTarget.Buffer, 0);
        LinkTarget.Buffer = 0;
      }
      ZwClose(LinkHandle);
    }
  }
  return SymbolicLink;
}

```

## disassembly

```asm
0x14001ec2c  push    rbp
0x14001ec2e  push    rbx
0x14001ec2f  push    rsi
0x14001ec30  push    rdi
0x14001ec31  mov     rbp, rsp
0x14001ec34  sub     rsp, 68h
0x14001ec38  mov     rdi, rdx
0x14001ec3b  mov     rsi, rcx
0x14001ec3e  call    cs:__imp_IoCreateSymbolicLink
0x14001ec45  nop     dword ptr [rax+rax+00h]
0x14001ec4a  mov     ebx, eax
0x14001ec4c  cmp     eax, 0C0000035h
0x14001ec51  jnz     loc_14001ED34
0x14001ec57  xor     eax, eax
0x14001ec59  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001ec61  xorps   xmm0, xmm0
0x14001ec64  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14001ec6c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001ec70  mov     [rbp+LinkHandle], rax
0x14001ec74  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x14001ec78  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001ec7c  lea     edx, [rax+1]; DesiredAccess
0x14001ec7f  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x14001ec83  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001ec88  call    cs:__imp_ZwOpenSymbolicLinkObject
0x14001ec8f  nop     dword ptr [rax+rax+00h]
0x14001ec94  test    eax, eax
0x14001ec96  js      loc_14001ED34
0x14001ec9c  movzx   eax, word ptr [rdi+2]
0x14001eca0  xorps   xmm0, xmm0
0x14001eca3  add     ax, 2
0x14001eca7  mov     ecx, 102h
0x14001ecac  movzx   edx, ax
0x14001ecaf  mov     r8d, 734D7852h
0x14001ecb5  movups  xmmword ptr [rbp+LinkTarget.Length], xmm0
0x14001ecb9  mov     [rbp+LinkTarget.MaximumLength], dx
0x14001ecbd  call    cs:__imp_ExAllocatePool2
0x14001ecc4  nop     dword ptr [rax+rax+00h]
0x14001ecc9  mov     [rbp+LinkTarget.Buffer], rax
0x14001eccd  test    rax, rax
0x14001ecd0  jz      short loc_14001ED24
0x14001ecd2  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x14001ecd6  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x14001ecda  xor     r8d, r8d; ReturnedLength
0x14001ecdd  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14001ece4  nop     dword ptr [rax+rax+00h]
0x14001ece9  test    eax, eax
0x14001eceb  js      short loc_14001ED0A
0x14001eced  mov     r8b, 1; CaseInSensitive
0x14001ecf0  lea     rdx, [rbp+LinkTarget]; String2
0x14001ecf4  mov     rcx, rdi; String1
0x14001ecf7  call    cs:__imp_RtlEqualUnicodeString
0x14001ecfe  nop     dword ptr [rax+rax+00h]
0x14001ed03  xor     ecx, ecx
0x14001ed05  test    al, al
0x14001ed07  cmovnz  ebx, ecx
0x14001ed0a  mov     rcx, [rbp+LinkTarget.Buffer]; P
0x14001ed0e  xor     edx, edx; Tag
0x14001ed10  call    cs:__imp_ExFreePoolWithTag
0x14001ed17  nop     dword ptr [rax+rax+00h]
0x14001ed1c  mov     [rbp+LinkTarget.Buffer], 0
0x14001ed24  mov     rcx, [rbp+LinkHandle]; Handle
0x14001ed28  call    cs:__imp_ZwClose
0x14001ed2f  nop     dword ptr [rax+rax+00h]
0x14001ed34  mov     eax, ebx
0x14001ed36  add     rsp, 68h
0x14001ed3a  pop     rdi
0x14001ed3b  pop     rsi
0x14001ed3c  pop     rbx
0x14001ed3d  pop     rbp
0x14001ed3e  retn
```
