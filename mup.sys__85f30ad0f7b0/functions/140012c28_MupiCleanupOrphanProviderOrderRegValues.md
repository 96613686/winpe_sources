# MupiCleanupOrphanProviderOrderRegValues

- ea: `0x140012c28`
- end: `0x140012e17`
- name: `MupiCleanupOrphanProviderOrderRegValues`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140012560`

## callees

- `0x140003cb8`
- `0x140012c28`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140012d24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012d24`
- `ntoskrnl!ExAllocatePool2` at `0x140012dc0`
- `ntoskrnl!ExAllocatePool2` at `0x140012dc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012da3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012de7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012da3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012de7`
- `ntoskrnl!ZwClose` at `0x140012dfc`
- `ntoskrnl!ZwClose` at `0x140012dfc`
- `ntoskrnl!ZwOpenKey` at `0x140012d63`
- `ntoskrnl!ZwOpenKey` at `0x140012d63`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140012c9d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140012c9d`
- `ntoskrnl!ZwDeleteValueKey` at `0x140012d7f`
- `ntoskrnl!ZwDeleteValueKey` at `0x140012d7f`

## string_xrefs

- `0x140012d19`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

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
0x140012c28  push    rbp
0x140012c2a  push    rbx
0x140012c2b  push    rsi
0x140012c2c  push    rdi
0x140012c2d  push    r14
0x140012c2f  mov     rbp, rsp
0x140012c32  sub     rsp, 80h
0x140012c39  xorps   xmm0, xmm0
0x140012c3c  mov     [rbp+arg_8], 0
0x140012c43  xor     eax, eax
0x140012c45  mov     [rbp+arg_0], 0
0x140012c49  cmp     cs:MupiNetworkProviderOrderKeyHandle, rax
0x140012c50  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012c54  mov     [rbp+KeyHandle], 0
0x140012c5c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012c60  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012c64  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012c68  jz      loc_140012E08
0x140012c6e  xor     edi, edi
0x140012c70  mov     esi, 400h
0x140012c75  jmp     loc_140012DB2
0x140012c7a  mov     rcx, cs:MupiNetworkProviderOrderKeyHandle; KeyHandle
0x140012c81  lea     rax, [rbp+arg_8]
0x140012c85  xorps   xmm0, xmm0
0x140012c88  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140012c8d  mov     r9, rbx; KeyValueInformation
0x140012c90  mov     [rsp+80h+Length], esi; Length
0x140012c94  xor     r8d, r8d; KeyValueInformationClass
0x140012c97  mov     edx, edi; Index
0x140012c99  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140012c9d  call    cs:__imp_ZwEnumerateValueKey
0x140012ca4  nop     dword ptr [rax+rax+00h]
0x140012ca9  cmp     eax, 8000001Ah
0x140012cae  jz      loc_140012DDA
0x140012cb4  cmp     eax, 80000005h
0x140012cb9  jz      loc_140012D9B
0x140012cbf  cmp     eax, 0C0000023h
0x140012cc4  jz      loc_140012D9B
0x140012cca  test    eax, eax
0x140012ccc  js      loc_140012DDA
0x140012cd2  lea     rax, [rbx+0Ch]
0x140012cd6  mov     r14d, edi
0x140012cd9  mov     [rbp+ValueName.Buffer], rax
0x140012cdd  inc     edi
0x140012cdf  movzx   eax, word ptr [rbx+8]
0x140012ce3  mov     [rbp+ValueName.MaximumLength], ax
0x140012ce7  mov     [rbp+ValueName.Length], ax
0x140012ceb  cmp     dword ptr [rbx+4], 4
0x140012cef  jnz     short loc_140012C7A
0x140012cf1  lea     rdx, [rbp+arg_0]
0x140012cf5  lea     rcx, [rbp+ValueName]; Source
0x140012cf9  call    MupiProviderIsInstalled
0x140012cfe  test    eax, eax
0x140012d00  js      loc_140012C7A
0x140012d06  cmp     [rbp+arg_0], 0
0x140012d0a  jnz     loc_140012C7A
0x140012d10  mov     rcx, [rbp+KeyHandle]
0x140012d14  test    rcx, rcx
0x140012d17  jnz     short loc_140012D7B
0x140012d19  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012d20  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012d24  call    cs:__imp_RtlInitUnicodeString
0x140012d2b  nop     dword ptr [rax+rax+00h]
0x140012d30  lea     rax, [rbp+DestinationString]
0x140012d34  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012d3b  xorps   xmm0, xmm0
0x140012d3e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012d42  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012d46  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012d4e  mov     edx, 2; DesiredAccess
0x140012d53  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012d5a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140012d5e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012d63  call    cs:__imp_ZwOpenKey
0x140012d6a  nop     dword ptr [rax+rax+00h]
0x140012d6f  test    eax, eax
0x140012d71  js      loc_140012C7A
0x140012d77  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140012d7b  lea     rdx, [rbp+ValueName]; ValueName
0x140012d7f  call    cs:__imp_ZwDeleteValueKey
0x140012d86  nop     dword ptr [rax+rax+00h]
0x140012d8b  test    eax, eax
0x140012d8d  js      loc_140012C7A
0x140012d93  mov     edi, r14d
0x140012d96  jmp     loc_140012C7A
0x140012d9b  mov     edx, 4F50754Dh; Tag
0x140012da0  mov     rcx, rbx; P
0x140012da3  call    cs:__imp_ExFreePoolWithTag
0x140012daa  nop     dword ptr [rax+rax+00h]
0x140012daf  mov     esi, [rbp+arg_8]
0x140012db2  mov     r8d, 4F50754Dh
0x140012db8  mov     rdx, rsi
0x140012dbb  mov     ecx, 102h
0x140012dc0  call    cs:__imp_ExAllocatePool2
0x140012dc7  nop     dword ptr [rax+rax+00h]
0x140012dcc  mov     rbx, rax
0x140012dcf  test    rax, rax
0x140012dd2  jnz     loc_140012C7A
0x140012dd8  jmp     short loc_140012DF3
0x140012dda  test    rbx, rbx
0x140012ddd  jz      short loc_140012DF3
0x140012ddf  mov     edx, 4F50754Dh; Tag
0x140012de4  mov     rcx, rbx; P
0x140012de7  call    cs:__imp_ExFreePoolWithTag
0x140012dee  nop     dword ptr [rax+rax+00h]
0x140012df3  mov     rcx, [rbp+KeyHandle]; Handle
0x140012df7  test    rcx, rcx
0x140012dfa  jz      short loc_140012E08
0x140012dfc  call    cs:__imp_ZwClose
0x140012e03  nop     dword ptr [rax+rax+00h]
0x140012e08  add     rsp, 80h
0x140012e0f  pop     r14
0x140012e11  pop     rdi
0x140012e12  pop     rsi
0x140012e13  pop     rbx
0x140012e14  pop     rbp
0x140012e15  retn
```
