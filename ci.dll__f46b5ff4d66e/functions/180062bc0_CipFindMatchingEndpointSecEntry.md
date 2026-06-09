# CipFindMatchingEndpointSecEntry

- ea: `0x180062bc0`
- end: `0x180062e03`
- name: `CipFindMatchingEndpointSecEntry`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062880`

## callees

- `0x180010554`
- `0x18002bef0`
- `0x180062bc0`
- `0x180062f30`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180062db6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180062db6`
- `ntoskrnl!ZwCreateKey` at `0x180062d8b`
- `ntoskrnl!ZwCreateKey` at `0x180062d8b`
- `ntoskrnl!ExAllocatePool2` at `0x180062c84`
- `ntoskrnl!ExAllocatePool2` at `0x180062c84`
- `ntoskrnl!ZwClose` at `0x180062dcc`
- `ntoskrnl!ZwClose` at `0x180062dcc`
- `ntoskrnl!ZwOpenKey` at `0x180062d18`
- `ntoskrnl!ZwOpenKey` at `0x180062d18`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180062c53`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180062c53`

## string_xrefs

- `0x180062c06`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\ExtensionPolicy\`

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
0x180062bc0  mov     [rsp-8+arg_0], rbx
0x180062bc5  mov     [rsp-8+arg_8], rsi
0x180062bca  push    rbp
0x180062bcb  push    rdi
0x180062bcc  push    r13
0x180062bce  push    r14
0x180062bd0  push    r15
0x180062bd2  lea     rbp, [rsp-10h]
0x180062bd7  sub     rsp, 110h
0x180062bde  mov     rax, cs:__security_cookie
0x180062be5  xor     rax, rsp
0x180062be8  mov     [rbp+30h+var_30], rax
0x180062bec  mov     rdi, [rbp+30h+arg_20]
0x180062bf0  xorps   xmm0, xmm0
0x180062bf3  xor     eax, eax
0x180062bf5  mov     qword ptr [rsp+130h+SourceString.Length], 8E008Ch
0x180062bfe  mov     [rsp+130h+KeyHandle], rax
0x180062c03  mov     r10, r8
0x180062c06  lea     rax, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180062c0d  mov     qword ptr [rsp+130h+var_D8.Length], 4E0000h
0x180062c16  mov     [rsp+130h+SourceString.Buffer], rax
0x180062c1b  mov     sil, dl
0x180062c1e  lea     rax, [rbp+30h+var_80]
0x180062c22  mov     byte ptr [rdi], 0
0x180062c25  mov     r14, rcx
0x180062c28  mov     [rsp+130h+var_D8.Buffer], rax
0x180062c2d  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x180062c31  xor     r8d, r8d
0x180062c34  lea     rdx, [rsp+130h+var_D8]
0x180062c39  mov     rcx, r10
0x180062c3c  mov     r15, r9
0x180062c3f  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180062c44  mov     r13d, 8Ch
0x180062c4a  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x180062c4f  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x180062c53  call    cs:__imp_RtlStringFromGUIDEx
0x180062c5a  nop     dword ptr [rax+rax+00h]
0x180062c5f  mov     ebx, eax
0x180062c61  test    eax, eax
0x180062c63  js      loc_180062DB1
0x180062c69  movzx   eax, [rsp+130h+var_D8.Length]
0x180062c6e  lea     ecx, [r13+76h]
0x180062c72  add     ax, r13w
0x180062c76  mov     r8d, 72634943h
0x180062c7c  movzx   edx, ax
0x180062c7f  mov     [rsp+130h+DestinationString.MaximumLength], dx
0x180062c84  call    cs:__imp_ExAllocatePool2
0x180062c8b  nop     dword ptr [rax+rax+00h]
0x180062c90  mov     [rsp+130h+DestinationString.Buffer], rax
0x180062c95  test    rax, rax
0x180062c98  jnz     short loc_180062CA4
0x180062c9a  mov     ebx, 0C0000017h
0x180062c9f  jmp     loc_180062DB1
0x180062ca4  xor     eax, eax
0x180062ca6  lea     rdx, [rsp+130h+SourceString]; SourceString
0x180062cab  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180062cb0  mov     [rsp+130h+DestinationString.Length], ax
0x180062cb5  call    RtlUnicodeStringCat
0x180062cba  mov     ebx, eax
0x180062cbc  test    eax, eax
0x180062cbe  js      loc_180062DB1
0x180062cc4  lea     rdx, [rsp+130h+var_D8]; SourceString
0x180062cc9  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180062cce  call    RtlUnicodeStringCat
0x180062cd3  mov     ebx, eax
0x180062cd5  test    eax, eax
0x180062cd7  js      loc_180062DB1
0x180062cdd  lea     rax, [rsp+130h+DestinationString]
0x180062ce2  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180062cea  xorps   xmm0, xmm0
0x180062ced  mov     [rbp+30h+ObjectAttributes.RootDirectory], 0
0x180062cf5  mov     r13d, 0F003Fh
0x180062cfb  mov     [rbp+30h+ObjectAttributes.Attributes], 40h ; '@'
0x180062d02  mov     edx, r13d; DesiredAccess
0x180062d05  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x180062d09  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180062d0e  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180062d13  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062d18  call    cs:__imp_ZwOpenKey
0x180062d1f  nop     dword ptr [rax+rax+00h]
0x180062d24  mov     ecx, 80000000h
0x180062d29  mov     edx, 0C0000034h
0x180062d2e  mov     ebx, eax
0x180062d30  add     eax, ecx
0x180062d32  test    ecx, eax
0x180062d34  jnz     short loc_180062D3A
0x180062d36  cmp     ebx, edx
0x180062d38  jnz     short loc_180062DB1
0x180062d3a  test    ebx, ebx
0x180062d3c  js      short loc_180062D53
0x180062d3e  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180062d43  mov     rdx, r14
0x180062d46  call    CipMatchExpectedIdentityEKU
0x180062d4b  mov     ebx, eax
0x180062d4d  test    eax, eax
0x180062d4f  js      short loc_180062DB1
0x180062d51  jmp     short loc_180062DA0
0x180062d53  cmp     ebx, edx
0x180062d55  jnz     short loc_180062DB1
0x180062d57  mov     ebx, 0C0000272h
0x180062d5c  test    sil, sil
0x180062d5f  jz      short loc_180062DB1
0x180062d61  mov     [rsp+130h+Disposition], 0; Disposition
0x180062d6a  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180062d6f  mov     [rsp+130h+CreateOptions], 0; CreateOptions
0x180062d77  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x180062d7c  xor     r9d, r9d; TitleIndex
0x180062d7f  mov     [rsp+130h+Class], 0; Class
0x180062d88  mov     edx, r13d; DesiredAccess
0x180062d8b  call    cs:__imp_ZwCreateKey
0x180062d92  nop     dword ptr [rax+rax+00h]
0x180062d97  mov     ebx, eax
0x180062d99  test    eax, eax
0x180062d9b  js      short loc_180062DB1
0x180062d9d  mov     byte ptr [rdi], 1
0x180062da0  mov     rax, [rsp+130h+KeyHandle]
0x180062da5  mov     [r15], rax
0x180062da8  mov     [rsp+130h+KeyHandle], 0
0x180062db1  lea     rcx, [rsp+130h+DestinationString]; UnicodeString
0x180062db6  call    cs:__imp_RtlFreeUnicodeString
0x180062dbd  nop     dword ptr [rax+rax+00h]
0x180062dc2  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x180062dc7  test    rcx, rcx
0x180062dca  jz      short loc_180062DD8
0x180062dcc  call    cs:__imp_ZwClose
0x180062dd3  nop     dword ptr [rax+rax+00h]
0x180062dd8  mov     eax, ebx
0x180062dda  mov     rcx, [rbp+30h+var_30]
0x180062dde  xor     rcx, rsp; StackCookie
0x180062de1  call    __security_check_cookie
0x180062de6  lea     r11, [rsp+130h+var_20]
0x180062dee  mov     rbx, [r11+30h]
0x180062df2  mov     rsi, [r11+38h]
0x180062df6  mov     rsp, r11
0x180062df9  pop     r15
0x180062dfb  pop     r14
0x180062dfd  pop     r13
0x180062dff  pop     rdi
0x180062e00  pop     rbp
0x180062e01  retn
```
