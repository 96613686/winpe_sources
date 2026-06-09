# BiTranslateSymbolicLink

- ea: `0x180031dc4`
- end: `0x180031fbd`
- name: `BiTranslateSymbolicLink`
- size: `505`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030b4c`
- `0x18003121c`
- `0x180034598`
- `0x1800349e4`

## callees

- `0x180031dc4`

## import_xrefs

- `ntdll!ZwOpenSymbolicLinkObject` at `0x180031e40`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180031f47`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180031e40`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180031f47`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x180031ed4`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x180031ed4`
- `ntdll!ZwClose` at `0x180031eed`
- `ntdll!ZwClose` at `0x180031f6d`
- `ntdll!ZwClose` at `0x180031eed`
- `ntdll!ZwClose` at `0x180031f6d`
- `ntdll!RtlFreeHeap` at `0x180031e87`
- `ntdll!RtlFreeHeap` at `0x180031f97`
- `ntdll!RtlFreeHeap` at `0x180031e87`
- `ntdll!RtlFreeHeap` at `0x180031f97`
- `ntdll!RtlInitUnicodeString` at `0x180031e01`
- `ntdll!RtlInitUnicodeString` at `0x180031e5a`
- `ntdll!RtlInitUnicodeString` at `0x180031e01`
- `ntdll!RtlInitUnicodeString` at `0x180031e5a`
- `ntdll!RtlAllocateHeap` at `0x180031eaf`
- `ntdll!RtlAllocateHeap` at `0x180031eaf`

## pseudocode

```c
NTSTATUS __fastcall BiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnedLength; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  ReturnedLength = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
  SymbolicLinkHandle = 0;
  LinkTarget.Buffer = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    ReturnedLength = 0;
    do
    {
      while ( 1 )
      {
        v5 = ZwQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &ReturnedLength);
        if ( v5 == -1073741789 )
          break;
        ZwClose(SymbolicLinkHandle);
        SymbolicLinkHandle = 0;
        if ( v5 < 0 )
          goto LABEL_13;
        LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        LinkTarget.MaximumLength = v4;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
        {
          v5 = 0;
          *a2 = LinkTarget.Buffer;
          goto LABEL_10;
        }
      }
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      LinkTarget.MaximumLength = ReturnedLength;
      v4 = ReturnedLength + 2;
      LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnedLength + 2);
    }
    while ( LinkTarget.Buffer );
    v5 = -1073741670;
LABEL_10:
    if ( SymbolicLinkHandle )
      ZwClose(SymbolicLinkHandle);
    if ( v5 < 0 )
    {
LABEL_13:
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180031dc4  mov     [rsp-18h+arg_0], rbx
0x180031dc9  push    rbp
0x180031dca  push    rsi
0x180031dcb  push    rdi
0x180031dcc  mov     rbp, rsp
0x180031dcf  sub     rsp, 70h
0x180031dd3  xorps   xmm0, xmm0
0x180031dd6  xor     eax, eax
0x180031dd8  mov     rsi, rdx
0x180031ddb  mov     [rbp+ReturnedLength], eax
0x180031dde  mov     rdx, rcx; SourceString
0x180031de1  mov     qword ptr [rbp+LinkTarget.Length], rax
0x180031de5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180031de9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031ded  mov     [rbp+SymbolicLinkHandle], rax
0x180031df1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180031df5  mov     [rbp+LinkTarget.Buffer], rax
0x180031df9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180031dfd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180031e01  call    cs:__imp_RtlInitUnicodeString
0x180031e08  nop     dword ptr [rax+rax+00h]
0x180031e0d  lea     rax, [rbp+DestinationString]
0x180031e11  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031e18  xorps   xmm0, xmm0
0x180031e1b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031e1f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180031e23  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180031e2b  mov     edx, 1; DesiredAccess
0x180031e30  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180031e37  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x180031e3b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180031e40  call    cs:__imp_ZwOpenSymbolicLinkObject
0x180031e47  nop     dword ptr [rax+rax+00h]
0x180031e4c  test    eax, eax
0x180031e4e  js      loc_180031FA5
0x180031e54  xor     edx, edx; SourceString
0x180031e56  lea     rcx, [rbp+LinkTarget]; DestinationString
0x180031e5a  call    cs:__imp_RtlInitUnicodeString
0x180031e61  nop     dword ptr [rax+rax+00h]
0x180031e66  xor     edi, edi
0x180031e68  mov     [rbp+ReturnedLength], edi
0x180031e6b  jmp     short loc_180031EC8
0x180031e6d  cmp     [rbp+LinkTarget.Buffer], 0
0x180031e72  jz      short loc_180031E93
0x180031e74  mov     rcx, gs:60h
0x180031e7d  xor     edx, edx; Flags
0x180031e7f  mov     r8, [rbp+LinkTarget.Buffer]; P
0x180031e83  mov     rcx, [rcx+30h]; HeapHandle
0x180031e87  call    cs:__imp_RtlFreeHeap
0x180031e8e  nop     dword ptr [rax+rax+00h]
0x180031e93  mov     eax, [rbp+ReturnedLength]
0x180031e96  xor     edx, edx; Flags
0x180031e98  mov     [rbp+LinkTarget.MaximumLength], ax
0x180031e9c  mov     rcx, gs:60h
0x180031ea5  lea     edi, [rax+2]
0x180031ea8  mov     r8d, edi; Size
0x180031eab  mov     rcx, [rcx+30h]; HeapHandle
0x180031eaf  call    cs:__imp_RtlAllocateHeap
0x180031eb6  nop     dword ptr [rax+rax+00h]
0x180031ebb  mov     [rbp+LinkTarget.Buffer], rax
0x180031ebf  test    rax, rax
0x180031ec2  jz      loc_180031FB6
0x180031ec8  mov     rcx, [rbp+SymbolicLinkHandle]; LinkHandle
0x180031ecc  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x180031ed0  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x180031ed4  call    cs:__imp_ZwQuerySymbolicLinkObject
0x180031edb  nop     dword ptr [rax+rax+00h]
0x180031ee0  mov     ebx, eax
0x180031ee2  cmp     eax, 0C0000023h
0x180031ee7  jz      short loc_180031E6D
0x180031ee9  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180031eed  call    cs:__imp_ZwClose
0x180031ef4  nop     dword ptr [rax+rax+00h]
0x180031ef9  mov     [rbp+SymbolicLinkHandle], 0
0x180031f01  test    ebx, ebx
0x180031f03  js      short loc_180031F7D
0x180031f05  movzx   edx, [rbp+LinkTarget.Length]
0x180031f09  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180031f0d  mov     rax, [rbp+LinkTarget.Buffer]
0x180031f11  xor     ecx, ecx
0x180031f13  shr     rdx, 1
0x180031f16  xorps   xmm0, xmm0
0x180031f19  mov     [rax+rdx*2], cx
0x180031f1d  lea     rax, [rbp+LinkTarget]
0x180031f21  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180031f25  lea     edx, [rcx+1]; DesiredAccess
0x180031f28  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x180031f2c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031f30  mov     [rbp+LinkTarget.MaximumLength], di
0x180031f34  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031f3b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180031f42  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180031f47  call    cs:__imp_ZwOpenSymbolicLinkObject
0x180031f4e  nop     dword ptr [rax+rax+00h]
0x180031f53  test    eax, eax
0x180031f55  jns     loc_180031EC8
0x180031f5b  mov     rax, [rbp+LinkTarget.Buffer]
0x180031f5f  xor     ebx, ebx
0x180031f61  mov     [rsi], rax
0x180031f64  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180031f68  test    rcx, rcx
0x180031f6b  jz      short loc_180031F79
0x180031f6d  call    cs:__imp_ZwClose
0x180031f74  nop     dword ptr [rax+rax+00h]
0x180031f79  test    ebx, ebx
0x180031f7b  jns     short loc_180031FA3
0x180031f7d  cmp     [rbp+LinkTarget.Buffer], 0
0x180031f82  jz      short loc_180031FA3
0x180031f84  mov     rcx, gs:60h
0x180031f8d  xor     edx, edx; Flags
0x180031f8f  mov     r8, [rbp+LinkTarget.Buffer]; P
0x180031f93  mov     rcx, [rcx+30h]; HeapHandle
0x180031f97  call    cs:__imp_RtlFreeHeap
0x180031f9e  nop     dword ptr [rax+rax+00h]
0x180031fa3  mov     eax, ebx
0x180031fa5  mov     rbx, [rsp+70h+arg_0]
0x180031fad  add     rsp, 70h
0x180031fb1  pop     rdi
0x180031fb2  pop     rsi
0x180031fb3  pop     rbp
0x180031fb4  retn
0x180031fb6  mov     ebx, 0C000009Ah
0x180031fbb  jmp     short loc_180031F64
```
