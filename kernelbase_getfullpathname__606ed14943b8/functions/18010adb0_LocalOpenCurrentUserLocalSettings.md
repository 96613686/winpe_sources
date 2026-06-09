# LocalOpenCurrentUserLocalSettings

- ea: `0x18010adb0`
- end: `0x18010af0b`
- name: `LocalOpenCurrentUserLocalSettings`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18010adb0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18010aec7`
- `ntdll!RtlFreeUnicodeString` at `0x18010aed7`
- `ntdll!RtlFreeUnicodeString` at `0x18010aec7`
- `ntdll!RtlFreeUnicodeString` at `0x18010aed7`
- `ntdll!RtlNtStatusToDosError` at `0x18010aee5`
- `ntdll!RtlNtStatusToDosError` at `0x18010aee5`
- `ntdll!NtCreateKey` at `0x18010aeb5`
- `ntdll!NtCreateKey` at `0x18010aeb5`
- `ntdll!RtlAppendUnicodeToString` at `0x18010ae5a`
- `ntdll!RtlAppendUnicodeToString` at `0x18010ae5a`
- `ntdll!RtlCopyUnicodeString` at `0x18010ae43`
- `ntdll!RtlCopyUnicodeString` at `0x18010ae43`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18010ade8`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18010ade8`
- `ntdll!RtlAllocateHeap` at `0x18010ae22`
- `ntdll!RtlAllocateHeap` at `0x18010ae22`

## pseudocode

```c
ULONG __fastcall LocalOpenCurrentUserLocalSettings(__int64 a1, ACCESS_MASK a2, HANDLE *a3)
{
  NTSTATUS v5; // eax
  NTSTATUS appended; // ebx
  NTSTATUS v7; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF

  memset(&ObjectAttributes, 0, 44);
  KeyPath = 0;
  DestinationString = 0;
  v5 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v5 < 0 )
  {
    v7 = v5;
  }
  else
  {
    DestinationString.MaximumLength = KeyPath.MaximumLength + 48;
    DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                        NtCurrentPeb()->ProcessHeap,
                                        0,
                                        (unsigned __int16)(KeyPath.MaximumLength + 48));
    if ( DestinationString.Buffer )
    {
      RtlCopyUnicodeString(&DestinationString, &KeyPath);
      appended = RtlAppendUnicodeToString(&DestinationString, L"_Classes\\Local Settings");
      if ( appended >= 0 )
      {
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 64;
        appended = NtCreateKey(a3, a2, &ObjectAttributes, 0, 0, 0, 0);
      }
    }
    else
    {
      appended = -1073741670;
    }
    RtlFreeUnicodeString(&KeyPath);
    RtlFreeUnicodeString(&DestinationString);
    v7 = appended;
  }
  return RtlNtStatusToDosError(v7);
}

```

## disassembly

```asm
0x18010adb0  push    rbp
0x18010adb2  push    rbx
0x18010adb3  push    rsi
0x18010adb4  push    rdi
0x18010adb5  push    r15
0x18010adb7  lea     rbp, [rsp-37h]
0x18010adbc  sub     rsp, 90h
0x18010adc3  xorps   xmm0, xmm0
0x18010adc6  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x18010adca  xorps   xmm1, xmm1
0x18010adcd  xor     eax, eax
0x18010adcf  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18010add3  mov     rdi, r8
0x18010add6  mov     esi, edx
0x18010add8  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18010addc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18010ade0  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x18010ade4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18010ade8  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18010adef  nop     dword ptr [rax+rax+00h]
0x18010adf4  test    eax, eax
0x18010adf6  js      loc_18010AF07
0x18010adfc  movzx   eax, [rbp+57h+KeyPath.MaximumLength]
0x18010ae00  mov     r15d, 30h ; '0'
0x18010ae06  add     ax, r15w
0x18010ae0a  xor     edx, edx; Flags
0x18010ae0c  movzx   r8d, ax; Size
0x18010ae10  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x18010ae15  mov     rcx, gs:60h
0x18010ae1e  mov     rcx, [rcx+30h]; HeapHandle
0x18010ae22  call    cs:__imp_RtlAllocateHeap
0x18010ae29  nop     dword ptr [rax+rax+00h]
0x18010ae2e  mov     [rbp+57h+DestinationString.Buffer], rax
0x18010ae32  test    rax, rax
0x18010ae35  jz      loc_18010AF00
0x18010ae3b  lea     rdx, [rbp+57h+KeyPath]; SourceString
0x18010ae3f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18010ae43  call    cs:__imp_RtlCopyUnicodeString
0x18010ae4a  nop     dword ptr [rax+rax+00h]
0x18010ae4f  lea     rdx, aClassesLocalSe; "_Classes\\Local Settings"
0x18010ae56  lea     rcx, [rbp+57h+DestinationString]; Destination
0x18010ae5a  call    cs:__imp_RtlAppendUnicodeToString
0x18010ae61  nop     dword ptr [rax+rax+00h]
0x18010ae66  mov     ebx, eax
0x18010ae68  test    eax, eax
0x18010ae6a  js      short loc_18010AEC3
0x18010ae6c  lea     rax, [rbp+57h+DestinationString]
0x18010ae70  mov     [rsp+0B0h+Disposition], 0; Disposition
0x18010ae79  xorps   xmm0, xmm0
0x18010ae7c  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x18010ae84  xor     r9d, r9d; TitleIndex
0x18010ae87  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18010ae8b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18010ae8f  mov     [rsp+0B0h+Class], 0; Class
0x18010ae98  mov     edx, esi; DesiredAccess
0x18010ae9a  mov     [rbp+57h+ObjectAttributes.Length], r15d
0x18010ae9e  mov     rcx, rdi; KeyHandle
0x18010aea1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18010aea9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010aeae  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18010aeb5  call    cs:__imp_NtCreateKey
0x18010aebc  nop     dword ptr [rax+rax+00h]
0x18010aec1  mov     ebx, eax
0x18010aec3  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x18010aec7  call    cs:__imp_RtlFreeUnicodeString
0x18010aece  nop     dword ptr [rax+rax+00h]
0x18010aed3  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x18010aed7  call    cs:__imp_RtlFreeUnicodeString
0x18010aede  nop     dword ptr [rax+rax+00h]
0x18010aee3  mov     ecx, ebx; Status
0x18010aee5  call    cs:__imp_RtlNtStatusToDosError
0x18010aeec  nop     dword ptr [rax+rax+00h]
0x18010aef1  add     rsp, 90h
0x18010aef8  pop     r15
0x18010aefa  pop     rdi
0x18010aefb  pop     rsi
0x18010aefc  pop     rbx
0x18010aefd  pop     rbp
0x18010aefe  retn
0x18010af00  mov     ebx, 0C000009Ah
0x18010af05  jmp     short loc_18010AEC3
0x18010af07  mov     ecx, eax
0x18010af09  jmp     short loc_18010AEE5
```
