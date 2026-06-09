# IsRegTSAppCompatEnabled

- ea: `0x180031ba8`
- end: `0x180031d83`
- name: `IsRegTSAppCompatEnabled`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800315f8`

## callees

- `0x180031ba8`
- `0x18008275d`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180031ca6`
- `ntdll!NtQueryValueKey` at `0x180031cf0`
- `ntdll!NtQueryValueKey` at `0x180031ca6`
- `ntdll!NtQueryValueKey` at `0x180031cf0`
- `ntdll!NtOpenKey` at `0x180031c5e`
- `ntdll!NtOpenKey` at `0x180031c5e`
- `ntdll!NtClose` at `0x180031d0f`
- `ntdll!NtClose` at `0x180031d0f`
- `ntdll!RtlInitUnicodeString` at `0x180031be7`
- `ntdll!RtlInitUnicodeString` at `0x180031c7d`
- `ntdll!RtlInitUnicodeString` at `0x180031cc5`
- `ntdll!RtlInitUnicodeString` at `0x180031be7`
- `ntdll!RtlInitUnicodeString` at `0x180031c7d`
- `ntdll!RtlInitUnicodeString` at `0x180031cc5`
- `ntdll!RtlFreeHeap` at `0x180031d3a`
- `ntdll!RtlFreeHeap` at `0x180031d3a`
- `ntdll!RtlAllocateHeap` at `0x180031c0b`
- `ntdll!RtlAllocateHeap` at `0x180031c0b`

## string_xrefs

- `0x180031bc0`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server`
- `0x180031c72`: `TSAppCompat`

## pseudocode

```c
_BOOL8 __fastcall IsRegTSAppCompatEnabled(_BYTE *a1)
{
  _DWORD *Heap; // rax
  BOOL v3; // edi
  _DWORD *v4; // rbx
  char v5; // al
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+30h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server");
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x224u);
  v3 = 0;
  v4 = Heap;
  if ( !DestinationString.Buffer )
  {
    if ( !Heap )
      return v3;
    goto LABEL_9;
  }
  if ( Heap )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"TSAppCompat");
      if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v4, 0x224u, &ResultLength) >= 0
        && v4[1] == 4 )
      {
        v3 = v4[3] != 0;
      }
      RtlInitUnicodeString(&DestinationString, L"TSUserEnabled");
      if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v4, 0x224u, &ResultLength) >= 0
        && v4[1] == 4 )
      {
        v5 = *((_BYTE *)v4 + 12);
      }
      else
      {
        v5 = 0;
      }
      *a1 = v5;
      NtClose(KeyHandle);
    }
LABEL_9:
    memset_0(v4, 0, 0x224u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x180031ba8  mov     [rsp-18h+arg_0], rbx
0x180031bad  mov     [rsp-18h+arg_18], rsi
0x180031bb2  push    rbp
0x180031bb3  push    rdi
0x180031bb4  push    r15
0x180031bb6  mov     rbp, rsp
0x180031bb9  sub     rsp, 70h
0x180031bbd  xorps   xmm0, xmm0
0x180031bc0  lea     rdx, aRegistryMachin_11; "\\Registry\\Machine\\System\\CurrentCon"...
0x180031bc7  xor     eax, eax
0x180031bc9  mov     rsi, rcx
0x180031bcc  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180031bd0  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031bd4  mov     [rbp+KeyHandle], rax
0x180031bd8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180031bdc  mov     [rbp+arg_8], eax
0x180031bdf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180031be3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180031be7  call    cs:__imp_RtlInitUnicodeString
0x180031bee  nop     dword ptr [rax+rax+00h]
0x180031bf3  mov     rcx, gs:60h
0x180031bfc  mov     r15d, 224h
0x180031c02  mov     r8d, r15d; Size
0x180031c05  xor     edx, edx; Flags
0x180031c07  mov     rcx, [rcx+30h]; HeapHandle
0x180031c0b  call    cs:__imp_RtlAllocateHeap
0x180031c12  nop     dword ptr [rax+rax+00h]
0x180031c17  xor     edi, edi
0x180031c19  mov     rbx, rax
0x180031c1c  cmp     [rbp+DestinationString.Buffer], rdi
0x180031c20  jz      loc_180031D62
0x180031c26  test    rax, rax
0x180031c29  jz      loc_180031D46
0x180031c2f  lea     rax, [rbp+DestinationString]
0x180031c33  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031c3a  xorps   xmm0, xmm0
0x180031c3d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031c41  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180031c45  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x180031c49  mov     edx, 20019h; DesiredAccess
0x180031c4e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180031c55  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180031c59  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180031c5e  call    cs:__imp_NtOpenKey
0x180031c65  nop     dword ptr [rax+rax+00h]
0x180031c6a  test    eax, eax
0x180031c6c  js      loc_180031D1B
0x180031c72  lea     rdx, aTsappcompat; "TSAppCompat"
0x180031c79  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031c7d  call    cs:__imp_RtlInitUnicodeString
0x180031c84  nop     dword ptr [rax+rax+00h]
0x180031c89  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180031c8d  lea     rax, [rbp+arg_8]
0x180031c91  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180031c96  lea     r8d, [rdi+2]; KeyValueInformationClass
0x180031c9a  mov     r9, rbx; KeyValueInformation
0x180031c9d  mov     [rsp+70h+Length], r15d; Length
0x180031ca2  lea     rdx, [rbp+DestinationString]; ValueName
0x180031ca6  call    cs:__imp_NtQueryValueKey
0x180031cad  nop     dword ptr [rax+rax+00h]
0x180031cb2  test    eax, eax
0x180031cb4  jns     loc_180031D69
0x180031cba  lea     rdx, aTsuserenabled; "TSUserEnabled"
0x180031cc1  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031cc5  call    cs:__imp_RtlInitUnicodeString
0x180031ccc  nop     dword ptr [rax+rax+00h]
0x180031cd1  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180031cd5  lea     rax, [rbp+arg_8]
0x180031cd9  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180031cde  lea     rdx, [rbp+DestinationString]; ValueName
0x180031ce2  mov     r9, rbx; KeyValueInformation
0x180031ce5  mov     [rsp+70h+Length], r15d; Length
0x180031cea  mov     r8d, 2; KeyValueInformationClass
0x180031cf0  call    cs:__imp_NtQueryValueKey
0x180031cf7  nop     dword ptr [rax+rax+00h]
0x180031cfc  test    eax, eax
0x180031cfe  js      short loc_180031D5E
0x180031d00  cmp     dword ptr [rbx+4], 4
0x180031d04  jnz     short loc_180031D5E
0x180031d06  mov     al, [rbx+0Ch]
0x180031d09  mov     [rsi], al
0x180031d0b  mov     rcx, [rbp+KeyHandle]; Handle
0x180031d0f  call    cs:__imp_NtClose
0x180031d16  nop     dword ptr [rax+rax+00h]
0x180031d1b  mov     r8, r15; Size
0x180031d1e  xor     edx, edx; Val
0x180031d20  mov     rcx, rbx; void *
0x180031d23  call    memset_0
0x180031d28  mov     rcx, gs:60h
0x180031d31  mov     r8, rbx; P
0x180031d34  xor     edx, edx; Flags
0x180031d36  mov     rcx, [rcx+30h]; HeapHandle
0x180031d3a  call    cs:__imp_RtlFreeHeap
0x180031d41  nop     dword ptr [rax+rax+00h]
0x180031d46  lea     r11, [rsp+70h+var_s0]
0x180031d4b  mov     eax, edi
0x180031d4d  mov     rbx, [r11+20h]
0x180031d51  mov     rsi, [r11+38h]
0x180031d55  mov     rsp, r11
0x180031d58  pop     r15
0x180031d5a  pop     rdi
0x180031d5b  pop     rbp
0x180031d5c  retn
0x180031d5e  xor     al, al
0x180031d60  jmp     short loc_180031D09
0x180031d62  test    rbx, rbx
0x180031d65  jnz     short loc_180031D1B
0x180031d67  jmp     short loc_180031D46
0x180031d69  cmp     dword ptr [rbx+4], 4
0x180031d6d  jnz     loc_180031CBA
0x180031d73  cmp     [rbx+0Ch], edi
0x180031d76  mov     eax, 1
0x180031d7b  cmovnz  edi, eax
0x180031d7e  jmp     loc_180031CBA
```
