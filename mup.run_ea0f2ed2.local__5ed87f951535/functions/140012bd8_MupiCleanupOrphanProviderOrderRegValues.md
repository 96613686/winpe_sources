# MupiCleanupOrphanProviderOrderRegValues

- ea: `0x140012bd8`
- end: `0x140012dc7`
- name: `MupiCleanupOrphanProviderOrderRegValues`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140012510`

## callees

- `0x140003cb8`
- `0x140012bd8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140012cd4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012cd4`
- `ntoskrnl!ExAllocatePool2` at `0x140012d70`
- `ntoskrnl!ExAllocatePool2` at `0x140012d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012d97`
- `ntoskrnl!ZwClose` at `0x140012dac`
- `ntoskrnl!ZwClose` at `0x140012dac`
- `ntoskrnl!ZwOpenKey` at `0x140012d13`
- `ntoskrnl!ZwOpenKey` at `0x140012d13`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140012c4d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140012c4d`
- `ntoskrnl!ZwDeleteValueKey` at `0x140012d2f`
- `ntoskrnl!ZwDeleteValueKey` at `0x140012d2f`

## string_xrefs

- `0x140012cc9`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

## pseudocode

```c
void MupiCleanupOrphanProviderOrderRegValues()
{
  ULONG v0; // edi
  __int64 Length; // rsi
  NTSTATUS v2; // eax
  ULONG v3; // r14d
  void *v4; // rcx
  __int64 Pool2; // rbx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+B8h] [rbp+38h] BYREF
  void *KeyHandle; // [rsp+C0h] [rbp+40h] BYREF

  ResultLength = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( MupiNetworkProviderOrderKeyHandle )
  {
    v0 = 0;
    Length = 1024;
LABEL_15:
    Pool2 = ExAllocatePool2(258, Length, 1330672973);
    if ( !Pool2 )
    {
LABEL_18:
      if ( KeyHandle )
        ZwClose(KeyHandle);
      return;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          ValueName = 0;
          v2 = ZwEnumerateValueKey(
                 MupiNetworkProviderOrderKeyHandle,
                 v0,
                 KeyValueBasicInformation,
                 (PVOID)Pool2,
                 Length,
                 &ResultLength);
          if ( v2 == -2147483622 )
            goto LABEL_17;
          if ( v2 == -2147483643 || v2 == -1073741789 )
          {
            ExFreePoolWithTag((PVOID)Pool2, 0x4F50754Du);
            Length = ResultLength;
            goto LABEL_15;
          }
          if ( v2 < 0 )
          {
LABEL_17:
            ExFreePoolWithTag((PVOID)Pool2, 0x4F50754Du);
            goto LABEL_18;
          }
          v3 = v0;
          ValueName.Buffer = (PWSTR)(Pool2 + 12);
          ++v0;
          ValueName.MaximumLength = *(_WORD *)(Pool2 + 8);
          ValueName.Length = ValueName.MaximumLength;
        }
        while ( *(_DWORD *)(Pool2 + 4) != 4 || (int)MupiProviderIsInstalled(&ValueName) < 0 );
        v4 = KeyHandle;
        if ( !KeyHandle )
          break;
LABEL_12:
        if ( ZwDeleteValueKey(v4, &ValueName) >= 0 )
          v0 = v3;
      }
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Networkprovider\\ProviderOrder");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes) >= 0 )
      {
        v4 = KeyHandle;
        goto LABEL_12;
      }
    }
  }
}

```

## disassembly

```asm
0x140012bd8  push    rbp
0x140012bda  push    rbx
0x140012bdb  push    rsi
0x140012bdc  push    rdi
0x140012bdd  push    r14
0x140012bdf  mov     rbp, rsp
0x140012be2  sub     rsp, 80h
0x140012be9  xorps   xmm0, xmm0
0x140012bec  mov     [rbp+arg_8], 0
0x140012bf3  xor     eax, eax
0x140012bf5  mov     [rbp+arg_0], 0
0x140012bf9  cmp     cs:MupiNetworkProviderOrderKeyHandle, rax
0x140012c00  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012c04  mov     [rbp+KeyHandle], 0
0x140012c0c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012c10  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012c14  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012c18  jz      loc_140012DB8
0x140012c1e  xor     edi, edi
0x140012c20  mov     esi, 400h
0x140012c25  jmp     loc_140012D62
0x140012c2a  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; KeyHandle
0x140012c31  lea     rax, [rbp+arg_8]
0x140012c35  xorps   xmm0, xmm0
0x140012c38  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140012c3d  mov     r9, rbx; KeyValueInformation
0x140012c40  mov     [rsp+80h+Length], esi; Length
0x140012c44  xor     r8d, r8d; KeyValueInformationClass
0x140012c47  mov     edx, edi; Index
0x140012c49  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140012c4d  call    cs:__imp_ZwEnumerateValueKey
0x140012c54  nop     dword ptr [rax+rax+00h]
0x140012c59  cmp     eax, 8000001Ah
0x140012c5e  jz      loc_140012D8A
0x140012c64  cmp     eax, 80000005h
0x140012c69  jz      loc_140012D4B
0x140012c6f  cmp     eax, 0C0000023h
0x140012c74  jz      loc_140012D4B
0x140012c7a  test    eax, eax
0x140012c7c  js      loc_140012D8A
0x140012c82  lea     rax, [rbx+0Ch]
0x140012c86  mov     r14d, edi
0x140012c89  mov     [rbp+ValueName.Buffer], rax
0x140012c8d  inc     edi
0x140012c8f  movzx   eax, word ptr [rbx+8]
0x140012c93  mov     [rbp+ValueName.MaximumLength], ax
0x140012c97  mov     [rbp+ValueName.Length], ax
0x140012c9b  cmp     dword ptr [rbx+4], 4
0x140012c9f  jnz     short loc_140012C2A
0x140012ca1  lea     rdx, [rbp+arg_0]
0x140012ca5  lea     rcx, [rbp+ValueName]; Source
0x140012ca9  call    MupiProviderIsInstalled
0x140012cae  test    eax, eax
0x140012cb0  js      loc_140012C2A
0x140012cb6  cmp     [rbp+arg_0], 0
0x140012cba  jnz     loc_140012C2A
0x140012cc0  mov     rcx, [rbp+KeyHandle]
0x140012cc4  test    rcx, rcx
0x140012cc7  jnz     short loc_140012D2B
0x140012cc9  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012cd0  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012cd4  call    cs:__imp_RtlInitUnicodeString
0x140012cdb  nop     dword ptr [rax+rax+00h]
0x140012ce0  lea     rax, [rbp+DestinationString]
0x140012ce4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012ceb  xorps   xmm0, xmm0
0x140012cee  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012cf2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012cf6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012cfe  mov     edx, 2; DesiredAccess
0x140012d03  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012d0a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140012d0e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012d13  call    cs:__imp_ZwOpenKey
0x140012d1a  nop     dword ptr [rax+rax+00h]
0x140012d1f  test    eax, eax
0x140012d21  js      loc_140012C2A
0x140012d27  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140012d2b  lea     rdx, [rbp+ValueName]; ValueName
0x140012d2f  call    cs:__imp_ZwDeleteValueKey
0x140012d36  nop     dword ptr [rax+rax+00h]
0x140012d3b  test    eax, eax
0x140012d3d  js      loc_140012C2A
0x140012d43  mov     edi, r14d
0x140012d46  jmp     loc_140012C2A
0x140012d4b  mov     edx, 4F50754Dh; Tag
0x140012d50  mov     rcx, rbx; P
0x140012d53  call    cs:__imp_ExFreePoolWithTag
0x140012d5a  nop     dword ptr [rax+rax+00h]
0x140012d5f  mov     esi, [rbp+arg_8]
0x140012d62  mov     r8d, 4F50754Dh
0x140012d68  mov     rdx, rsi
0x140012d6b  mov     ecx, 102h
0x140012d70  call    cs:__imp_ExAllocatePool2
0x140012d77  nop     dword ptr [rax+rax+00h]
0x140012d7c  mov     rbx, rax
0x140012d7f  test    rax, rax
0x140012d82  jnz     loc_140012C2A
0x140012d88  jmp     short loc_140012DA3
0x140012d8a  test    rbx, rbx
0x140012d8d  jz      short loc_140012DA3
0x140012d8f  mov     edx, 4F50754Dh; Tag
0x140012d94  mov     rcx, rbx; P
0x140012d97  call    cs:__imp_ExFreePoolWithTag
0x140012d9e  nop     dword ptr [rax+rax+00h]
0x140012da3  mov     rcx, [rbp+KeyHandle]; Handle
0x140012da7  test    rcx, rcx
0x140012daa  jz      short loc_140012DB8
0x140012dac  call    cs:__imp_ZwClose
0x140012db3  nop     dword ptr [rax+rax+00h]
0x140012db8  add     rsp, 80h
0x140012dbf  pop     r14
0x140012dc1  pop     rdi
0x140012dc2  pop     rsi
0x140012dc3  pop     rbx
0x140012dc4  pop     rbp
0x140012dc5  retn
```
