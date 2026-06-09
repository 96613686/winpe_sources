# CipFindMatchingEndpointSecEntry

- ea: `0x180063400`
- end: `0x180063643`
- name: `CipFindMatchingEndpointSecEntry`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800630c0`

## callees

- `0x1800104a4`
- `0x18002bf20`
- `0x180063400`
- `0x180063770`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800635f6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800635f6`
- `ntoskrnl!ZwCreateKey` at `0x1800635cb`
- `ntoskrnl!ZwCreateKey` at `0x1800635cb`
- `ntoskrnl!ExAllocatePool2` at `0x1800634c4`
- `ntoskrnl!ExAllocatePool2` at `0x1800634c4`
- `ntoskrnl!ZwClose` at `0x18006360c`
- `ntoskrnl!ZwClose` at `0x18006360c`
- `ntoskrnl!ZwOpenKey` at `0x180063558`
- `ntoskrnl!ZwOpenKey` at `0x180063558`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180063493`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180063493`

## string_xrefs

- `0x180063446`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\ExtensionPolicy\`

## pseudocode

```c
__int64 __fastcall CipFindMatchingEndpointSecEntry(__int64 a1, char a2, __int64 a3, void **a4, _BYTE *a5)
{
  NTSTATUS matched; // ebx
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING v11; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  char v14; // [rsp+B0h] [rbp-50h] BYREF

  *(_QWORD *)&SourceString.Length = 9306252;
  KeyHandle = 0;
  *(_QWORD *)&v11.Length = 5111808;
  SourceString.Buffer = L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\ExtensionPolicy\\";
  *a5 = 0;
  v11.Buffer = (PWSTR)&v14;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  matched = RtlStringFromGUIDEx(a3, &v11, 0);
  if ( matched >= 0 )
  {
    DestinationString.MaximumLength = v11.Length + 140;
    DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, (unsigned __int16)(v11.Length + 140), 1919109443);
    if ( !DestinationString.Buffer )
    {
      matched = -1073741801;
      goto LABEL_16;
    }
    DestinationString.Length = 0;
    matched = RtlUnicodeStringCat(&DestinationString, &SourceString);
    if ( matched >= 0 )
    {
      matched = RtlUnicodeStringCat(&DestinationString, &v11);
      if ( matched >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        matched = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
        if ( (int)(matched + 0x80000000) < 0 || matched == -1073741772 )
        {
          if ( matched >= 0 )
          {
            matched = CipMatchExpectedIdentityEKU(KeyHandle);
            if ( matched < 0 )
              goto LABEL_16;
            goto LABEL_15;
          }
          if ( matched == -1073741772 )
          {
            matched = -1073741198;
            if ( a2 )
            {
              matched = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
              if ( matched >= 0 )
              {
                *a5 = 1;
LABEL_15:
                *a4 = KeyHandle;
                KeyHandle = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_16:
  RtlFreeUnicodeString(&DestinationString);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x180063400  mov     [rsp-8+arg_0], rbx
0x180063405  mov     [rsp-8+arg_8], rsi
0x18006340a  push    rbp
0x18006340b  push    rdi
0x18006340c  push    r13
0x18006340e  push    r14
0x180063410  push    r15
0x180063412  lea     rbp, [rsp-10h]
0x180063417  sub     rsp, 110h
0x18006341e  mov     rax, cs:__security_cookie
0x180063425  xor     rax, rsp
0x180063428  mov     [rbp+30h+var_30], rax
0x18006342c  mov     rdi, [rbp+30h+arg_20]
0x180063430  xorps   xmm0, xmm0
0x180063433  xor     eax, eax
0x180063435  mov     qword ptr [rsp+130h+SourceString.Length], 8E008Ch
0x18006343e  mov     [rsp+130h+KeyHandle], rax
0x180063443  mov     r10, r8
0x180063446  lea     rax, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18006344d  mov     qword ptr [rsp+130h+var_D8.Length], 4E0000h
0x180063456  mov     [rsp+130h+SourceString.Buffer], rax
0x18006345b  mov     sil, dl
0x18006345e  lea     rax, [rbp+30h+var_80]
0x180063462  mov     byte ptr [rdi], 0
0x180063465  mov     r14, rcx
0x180063468  mov     [rsp+130h+var_D8.Buffer], rax
0x18006346d  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x180063471  xor     r8d, r8d
0x180063474  lea     rdx, [rsp+130h+var_D8]
0x180063479  mov     rcx, r10
0x18006347c  mov     r15, r9
0x18006347f  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180063484  mov     r13d, 8Ch
0x18006348a  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x18006348f  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x180063493  call    cs:__imp_RtlStringFromGUIDEx
0x18006349a  nop     dword ptr [rax+rax+00h]
0x18006349f  mov     ebx, eax
0x1800634a1  test    eax, eax
0x1800634a3  js      loc_1800635F1
0x1800634a9  movzx   eax, [rsp+130h+var_D8.Length]
0x1800634ae  lea     ecx, [r13+76h]
0x1800634b2  add     ax, r13w
0x1800634b6  mov     r8d, 72634943h
0x1800634bc  movzx   edx, ax
0x1800634bf  mov     [rsp+130h+DestinationString.MaximumLength], dx
0x1800634c4  call    cs:__imp_ExAllocatePool2
0x1800634cb  nop     dword ptr [rax+rax+00h]
0x1800634d0  mov     [rsp+130h+DestinationString.Buffer], rax
0x1800634d5  test    rax, rax
0x1800634d8  jnz     short loc_1800634E4
0x1800634da  mov     ebx, 0C0000017h
0x1800634df  jmp     loc_1800635F1
0x1800634e4  xor     eax, eax
0x1800634e6  lea     rdx, [rsp+130h+SourceString]; SourceString
0x1800634eb  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800634f0  mov     [rsp+130h+DestinationString.Length], ax
0x1800634f5  call    RtlUnicodeStringCat
0x1800634fa  mov     ebx, eax
0x1800634fc  test    eax, eax
0x1800634fe  js      loc_1800635F1
0x180063504  lea     rdx, [rsp+130h+var_D8]; SourceString
0x180063509  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18006350e  call    RtlUnicodeStringCat
0x180063513  mov     ebx, eax
0x180063515  test    eax, eax
0x180063517  js      loc_1800635F1
0x18006351d  lea     rax, [rsp+130h+DestinationString]
0x180063522  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18006352a  xorps   xmm0, xmm0
0x18006352d  mov     [rbp+30h+ObjectAttributes.RootDirectory], 0
0x180063535  mov     r13d, 0F003Fh
0x18006353b  mov     [rbp+30h+ObjectAttributes.Attributes], 40h ; '@'
0x180063542  mov     edx, r13d; DesiredAccess
0x180063545  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x180063549  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18006354e  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180063553  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063558  call    cs:__imp_ZwOpenKey
0x18006355f  nop     dword ptr [rax+rax+00h]
0x180063564  mov     ecx, 80000000h
0x180063569  mov     edx, 0C0000034h
0x18006356e  mov     ebx, eax
0x180063570  add     eax, ecx
0x180063572  test    ecx, eax
0x180063574  jnz     short loc_18006357A
0x180063576  cmp     ebx, edx
0x180063578  jnz     short loc_1800635F1
0x18006357a  test    ebx, ebx
0x18006357c  js      short loc_180063593
0x18006357e  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180063583  mov     rdx, r14
0x180063586  call    CipMatchExpectedIdentityEKU
0x18006358b  mov     ebx, eax
0x18006358d  test    eax, eax
0x18006358f  js      short loc_1800635F1
0x180063591  jmp     short loc_1800635E0
0x180063593  cmp     ebx, edx
0x180063595  jnz     short loc_1800635F1
0x180063597  mov     ebx, 0C0000272h
0x18006359c  test    sil, sil
0x18006359f  jz      short loc_1800635F1
0x1800635a1  mov     [rsp+130h+Disposition], 0; Disposition
0x1800635aa  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1800635af  mov     [rsp+130h+CreateOptions], 0; CreateOptions
0x1800635b7  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800635bc  xor     r9d, r9d; TitleIndex
0x1800635bf  mov     [rsp+130h+Class], 0; Class
0x1800635c8  mov     edx, r13d; DesiredAccess
0x1800635cb  call    cs:__imp_ZwCreateKey
0x1800635d2  nop     dword ptr [rax+rax+00h]
0x1800635d7  mov     ebx, eax
0x1800635d9  test    eax, eax
0x1800635db  js      short loc_1800635F1
0x1800635dd  mov     byte ptr [rdi], 1
0x1800635e0  mov     rax, [rsp+130h+KeyHandle]
0x1800635e5  mov     [r15], rax
0x1800635e8  mov     [rsp+130h+KeyHandle], 0
0x1800635f1  lea     rcx, [rsp+130h+DestinationString]; UnicodeString
0x1800635f6  call    cs:__imp_RtlFreeUnicodeString
0x1800635fd  nop     dword ptr [rax+rax+00h]
0x180063602  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x180063607  test    rcx, rcx
0x18006360a  jz      short loc_180063618
0x18006360c  call    cs:__imp_ZwClose
0x180063613  nop     dword ptr [rax+rax+00h]
0x180063618  mov     eax, ebx
0x18006361a  mov     rcx, [rbp+30h+var_30]
0x18006361e  xor     rcx, rsp; StackCookie
0x180063621  call    __security_check_cookie
0x180063626  lea     r11, [rsp+130h+var_20]
0x18006362e  mov     rbx, [r11+30h]
0x180063632  mov     rsi, [r11+38h]
0x180063636  mov     rsp, r11
0x180063639  pop     r15
0x18006363b  pop     r14
0x18006363d  pop     r13
0x18006363f  pop     rdi
0x180063640  pop     rbp
0x180063641  retn
```
