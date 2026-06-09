# CipFindMatchingEndpointSecEntry

- ea: `0x180063570`
- end: `0x1800637b3`
- name: `CipFindMatchingEndpointSecEntry`
- size: `579`
- prototype: `__int64 __fastcall(__int64, char, __int64, void **, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063230`

## callees

- `0x1800104b4`
- `0x18002c0d0`
- `0x180063570`
- `0x1800638e0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180063766`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063766`
- `ntoskrnl!ZwCreateKey` at `0x18006373b`
- `ntoskrnl!ZwCreateKey` at `0x18006373b`
- `ntoskrnl!ExAllocatePool2` at `0x180063634`
- `ntoskrnl!ExAllocatePool2` at `0x180063634`
- `ntoskrnl!ZwClose` at `0x18006377c`
- `ntoskrnl!ZwClose` at `0x18006377c`
- `ntoskrnl!ZwOpenKey` at `0x1800636c8`
- `ntoskrnl!ZwOpenKey` at `0x1800636c8`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180063603`
- `ntoskrnl!RtlStringFromGUIDEx` at `0x180063603`

## string_xrefs

- `0x1800635b6`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\ExtensionPolicy\`

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
0x180063570  mov     [rsp-8+arg_0], rbx
0x180063575  mov     [rsp-8+arg_8], rsi
0x18006357a  push    rbp
0x18006357b  push    rdi
0x18006357c  push    r13
0x18006357e  push    r14
0x180063580  push    r15
0x180063582  lea     rbp, [rsp-10h]
0x180063587  sub     rsp, 110h
0x18006358e  mov     rax, cs:__security_cookie
0x180063595  xor     rax, rsp
0x180063598  mov     [rbp+30h+var_30], rax
0x18006359c  mov     rdi, [rbp+30h+arg_20]
0x1800635a0  xorps   xmm0, xmm0
0x1800635a3  xor     eax, eax
0x1800635a5  mov     qword ptr [rsp+130h+SourceString.Length], 8E008Ch
0x1800635ae  mov     [rsp+130h+KeyHandle], rax
0x1800635b3  mov     r10, r8
0x1800635b6  lea     rax, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800635bd  mov     qword ptr [rsp+130h+var_D8.Length], 4E0000h
0x1800635c6  mov     [rsp+130h+SourceString.Buffer], rax
0x1800635cb  mov     sil, dl
0x1800635ce  lea     rax, [rbp+30h+var_80]
0x1800635d2  mov     byte ptr [rdi], 0
0x1800635d5  mov     r14, rcx
0x1800635d8  mov     [rsp+130h+var_D8.Buffer], rax
0x1800635dd  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x1800635e1  xor     r8d, r8d
0x1800635e4  lea     rdx, [rsp+130h+var_D8]
0x1800635e9  mov     rcx, r10
0x1800635ec  mov     r15, r9
0x1800635ef  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1800635f4  mov     r13d, 8Ch
0x1800635fa  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x1800635ff  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x180063603  call    cs:__imp_RtlStringFromGUIDEx
0x18006360a  nop     dword ptr [rax+rax+00h]
0x18006360f  mov     ebx, eax
0x180063611  test    eax, eax
0x180063613  js      loc_180063761
0x180063619  movzx   eax, [rsp+130h+var_D8.Length]
0x18006361e  lea     ecx, [r13+76h]
0x180063622  add     ax, r13w
0x180063626  mov     r8d, 72634943h
0x18006362c  movzx   edx, ax
0x18006362f  mov     [rsp+130h+DestinationString.MaximumLength], dx
0x180063634  call    cs:__imp_ExAllocatePool2
0x18006363b  nop     dword ptr [rax+rax+00h]
0x180063640  mov     [rsp+130h+DestinationString.Buffer], rax
0x180063645  test    rax, rax
0x180063648  jnz     short loc_180063654
0x18006364a  mov     ebx, 0C0000017h
0x18006364f  jmp     loc_180063761
0x180063654  xor     eax, eax
0x180063656  lea     rdx, [rsp+130h+SourceString]; SourceString
0x18006365b  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180063660  mov     [rsp+130h+DestinationString.Length], ax
0x180063665  call    RtlUnicodeStringCat
0x18006366a  mov     ebx, eax
0x18006366c  test    eax, eax
0x18006366e  js      loc_180063761
0x180063674  lea     rdx, [rsp+130h+var_D8]; SourceString
0x180063679  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18006367e  call    RtlUnicodeStringCat
0x180063683  mov     ebx, eax
0x180063685  test    eax, eax
0x180063687  js      loc_180063761
0x18006368d  lea     rax, [rsp+130h+DestinationString]
0x180063692  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18006369a  xorps   xmm0, xmm0
0x18006369d  mov     [rbp+30h+ObjectAttributes.RootDirectory], 0
0x1800636a5  mov     r13d, 0F003Fh
0x1800636ab  mov     [rbp+30h+ObjectAttributes.Attributes], 40h ; '@'
0x1800636b2  mov     edx, r13d; DesiredAccess
0x1800636b5  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x1800636b9  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1800636be  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800636c3  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800636c8  call    cs:__imp_ZwOpenKey
0x1800636cf  nop     dword ptr [rax+rax+00h]
0x1800636d4  mov     ecx, 80000000h
0x1800636d9  mov     edx, 0C0000034h
0x1800636de  mov     ebx, eax
0x1800636e0  add     eax, ecx
0x1800636e2  test    ecx, eax
0x1800636e4  jnz     short loc_1800636EA
0x1800636e6  cmp     ebx, edx
0x1800636e8  jnz     short loc_180063761
0x1800636ea  test    ebx, ebx
0x1800636ec  js      short loc_180063703
0x1800636ee  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1800636f3  mov     rdx, r14
0x1800636f6  call    CipMatchExpectedIdentityEKU
0x1800636fb  mov     ebx, eax
0x1800636fd  test    eax, eax
0x1800636ff  js      short loc_180063761
0x180063701  jmp     short loc_180063750
0x180063703  cmp     ebx, edx
0x180063705  jnz     short loc_180063761
0x180063707  mov     ebx, 0C0000272h
0x18006370c  test    sil, sil
0x18006370f  jz      short loc_180063761
0x180063711  mov     [rsp+130h+Disposition], 0; Disposition
0x18006371a  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18006371f  mov     [rsp+130h+CreateOptions], 0; CreateOptions
0x180063727  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x18006372c  xor     r9d, r9d; TitleIndex
0x18006372f  mov     [rsp+130h+Class], 0; Class
0x180063738  mov     edx, r13d; DesiredAccess
0x18006373b  call    cs:__imp_ZwCreateKey
0x180063742  nop     dword ptr [rax+rax+00h]
0x180063747  mov     ebx, eax
0x180063749  test    eax, eax
0x18006374b  js      short loc_180063761
0x18006374d  mov     byte ptr [rdi], 1
0x180063750  mov     rax, [rsp+130h+KeyHandle]
0x180063755  mov     [r15], rax
0x180063758  mov     [rsp+130h+KeyHandle], 0
0x180063761  lea     rcx, [rsp+130h+DestinationString]; UnicodeString
0x180063766  call    cs:__imp_RtlFreeUnicodeString
0x18006376d  nop     dword ptr [rax+rax+00h]
0x180063772  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x180063777  test    rcx, rcx
0x18006377a  jz      short loc_180063788
0x18006377c  call    cs:__imp_ZwClose
0x180063783  nop     dword ptr [rax+rax+00h]
0x180063788  mov     eax, ebx
0x18006378a  mov     rcx, [rbp+30h+var_30]
0x18006378e  xor     rcx, rsp; StackCookie
0x180063791  call    __security_check_cookie
0x180063796  lea     r11, [rsp+130h+var_20]
0x18006379e  mov     rbx, [r11+30h]
0x1800637a2  mov     rsi, [r11+38h]
0x1800637a6  mov     rsp, r11
0x1800637a9  pop     r15
0x1800637ab  pop     r14
0x1800637ad  pop     r13
0x1800637af  pop     rdi
0x1800637b0  pop     rbp
0x1800637b1  retn
```
