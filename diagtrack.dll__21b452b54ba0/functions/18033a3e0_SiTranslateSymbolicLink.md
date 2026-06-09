# SiTranslateSymbolicLink

- ea: `0x18033a3e0`
- end: `0x18033a5a4`
- name: `SiTranslateSymbolicLink`
- size: `452`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803391bc`
- `0x180339994`
- `0x18033b468`

## callees

- `0x18033a3e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18033a497`
- `ntdll!RtlFreeHeap` at `0x18033a580`
- `ntdll!RtlFreeHeap` at `0x18033a497`
- `ntdll!RtlFreeHeap` at `0x18033a580`
- `ntdll!NtClose` at `0x18033a4eb`
- `ntdll!NtClose` at `0x18033a55d`
- `ntdll!NtClose` at `0x18033a4eb`
- `ntdll!NtClose` at `0x18033a55d`
- `ntdll!RtlInitUnicodeString` at `0x18033a427`
- `ntdll!RtlInitUnicodeString` at `0x18033a46f`
- `ntdll!RtlInitUnicodeString` at `0x18033a427`
- `ntdll!RtlInitUnicodeString` at `0x18033a46f`
- `ntdll!RtlAllocateHeap` at `0x18033a4b9`
- `ntdll!RtlAllocateHeap` at `0x18033a4b9`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18033a45b`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18033a53c`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18033a45b`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18033a53c`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18033a4d8`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18033a4d8`

## pseudocode

```c
NTSTATUS __fastcall SiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG DataWritten; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&LinkTarget.Length = 0;
  DataWritten = 0;
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
  result = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    DataWritten = 0;
    do
    {
      while ( 1 )
      {
        v5 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
        if ( v5 == -1073741789 )
          break;
        NtClose(SymbolicLinkHandle);
        SymbolicLinkHandle = 0;
        if ( v5 < 0 )
          goto LABEL_12;
        LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        LinkTarget.MaximumLength = v4;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
        {
          v5 = 0;
          *a2 = LinkTarget.Buffer;
          LinkTarget.Buffer = 0;
          goto LABEL_10;
        }
      }
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      LinkTarget.MaximumLength = DataWritten;
      v4 = DataWritten + 2;
      LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataWritten + 2);
    }
    while ( LinkTarget.Buffer );
    v5 = -1073741670;
LABEL_10:
    if ( SymbolicLinkHandle )
    {
      NtClose(SymbolicLinkHandle);
      SymbolicLinkHandle = 0;
    }
LABEL_12:
    if ( LinkTarget.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18033a3e0  mov     [rsp-18h+arg_0], rbx
0x18033a3e5  mov     [rsp-18h+arg_8], rsi
0x18033a3ea  push    rbp
0x18033a3eb  push    rdi
0x18033a3ec  push    r14
0x18033a3ee  mov     rbp, rsp
0x18033a3f1  sub     rsp, 70h
0x18033a3f5  xorps   xmm0, xmm0
0x18033a3f8  xor     r14d, r14d
0x18033a3fb  mov     rsi, rdx
0x18033a3fe  mov     qword ptr [rbp+LinkTarget.Length], r14
0x18033a402  mov     rdx, rcx; SourceString
0x18033a405  mov     [rbp+DataWritten], r14d
0x18033a409  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18033a40d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18033a411  mov     [rbp+SymbolicLinkHandle], r14
0x18033a415  xor     eax, eax
0x18033a417  mov     [rbp+LinkTarget.Buffer], r14
0x18033a41b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18033a41f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18033a423  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18033a427  call    cs:__imp_RtlInitUnicodeString
0x18033a42d  lea     rax, [rbp+DestinationString]
0x18033a431  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18033a438  xorps   xmm0, xmm0
0x18033a43b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18033a43f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18033a443  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x18033a447  lea     edx, [r14+1]; DesiredAccess
0x18033a44b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18033a452  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x18033a456  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18033a45b  call    cs:__imp_NtOpenSymbolicLinkObject
0x18033a461  test    eax, eax
0x18033a463  js      loc_18033A588
0x18033a469  xor     edx, edx; SourceString
0x18033a46b  lea     rcx, [rbp+LinkTarget]; DestinationString
0x18033a46f  call    cs:__imp_RtlInitUnicodeString
0x18033a475  mov     edi, r14d
0x18033a478  mov     [rbp+DataWritten], r14d
0x18033a47c  jmp     short loc_18033A4CC
0x18033a47e  cmp     [rbp+LinkTarget.Buffer], r14
0x18033a482  jz      short loc_18033A49D
0x18033a484  mov     rcx, gs:60h
0x18033a48d  xor     edx, edx; Flags
0x18033a48f  mov     r8, [rbp+LinkTarget.Buffer]; P
0x18033a493  mov     rcx, [rcx+30h]; HeapHandle
0x18033a497  call    cs:__imp_RtlFreeHeap
0x18033a49d  mov     eax, [rbp+DataWritten]
0x18033a4a0  xor     edx, edx; Flags
0x18033a4a2  mov     [rbp+LinkTarget.MaximumLength], ax
0x18033a4a6  mov     rcx, gs:60h
0x18033a4af  lea     edi, [rax+2]
0x18033a4b2  mov     r8d, edi; Size
0x18033a4b5  mov     rcx, [rcx+30h]; HeapHandle
0x18033a4b9  call    cs:__imp_RtlAllocateHeap
0x18033a4bf  mov     [rbp+LinkTarget.Buffer], rax
0x18033a4c3  test    rax, rax
0x18033a4c6  jz      loc_18033A59D
0x18033a4cc  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x18033a4d0  lea     r8, [rbp+DataWritten]; DataWritten
0x18033a4d4  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x18033a4d8  call    cs:__imp_NtQuerySymbolicLinkObject
0x18033a4de  mov     ebx, eax
0x18033a4e0  cmp     eax, 0C0000023h
0x18033a4e5  jz      short loc_18033A47E
0x18033a4e7  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x18033a4eb  call    cs:__imp_NtClose
0x18033a4f1  mov     [rbp+SymbolicLinkHandle], r14
0x18033a4f5  test    ebx, ebx
0x18033a4f7  js      short loc_18033A567
0x18033a4f9  movzx   edx, [rbp+LinkTarget.Length]
0x18033a4fd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18033a501  mov     rax, [rbp+LinkTarget.Buffer]
0x18033a505  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x18033a509  shr     rdx, 1
0x18033a50c  xorps   xmm0, xmm0
0x18033a50f  mov     [rax+rdx*2], r14w
0x18033a514  lea     rax, [rbp+LinkTarget]
0x18033a518  mov     edx, 1; DesiredAccess
0x18033a51d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18033a521  mov     [rbp+LinkTarget.MaximumLength], di
0x18033a525  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18033a52c  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x18033a530  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18033a537  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18033a53c  call    cs:__imp_NtOpenSymbolicLinkObject
0x18033a542  test    eax, eax
0x18033a544  jns     short loc_18033A4CC
0x18033a546  mov     rax, [rbp+LinkTarget.Buffer]
0x18033a54a  mov     ebx, r14d
0x18033a54d  mov     [rsi], rax
0x18033a550  mov     [rbp+LinkTarget.Buffer], r14
0x18033a554  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x18033a558  test    rcx, rcx
0x18033a55b  jz      short loc_18033A567
0x18033a55d  call    cs:__imp_NtClose
0x18033a563  mov     [rbp+SymbolicLinkHandle], r14
0x18033a567  cmp     [rbp+LinkTarget.Buffer], r14
0x18033a56b  jz      short loc_18033A586
0x18033a56d  mov     rcx, gs:60h
0x18033a576  xor     edx, edx; Flags
0x18033a578  mov     r8, [rbp+LinkTarget.Buffer]; P
0x18033a57c  mov     rcx, [rcx+30h]; HeapHandle
0x18033a580  call    cs:__imp_RtlFreeHeap
0x18033a586  mov     eax, ebx
0x18033a588  lea     r11, [rsp+70h+var_s0]
0x18033a58d  mov     rbx, [r11+20h]
0x18033a591  mov     rsi, [r11+28h]
0x18033a595  mov     rsp, r11
0x18033a598  pop     r14
0x18033a59a  pop     rdi
0x18033a59b  pop     rbp
0x18033a59c  retn
0x18033a59d  mov     ebx, 0C000009Ah
0x18033a5a2  jmp     short loc_18033A554
```
