# CountPoliciesZoneMapSubKeysAndValues

- ea: `0x140088710`
- end: `0x140088947`
- name: `CountPoliciesZoneMapSubKeysAndValues`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140089e04`

## callees

- `0x140059dc0`
- `0x140088158`
- `0x140088710`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400887ba`
- `ntoskrnl!ZwOpenKey` at `0x140088891`
- `ntoskrnl!ZwOpenKey` at `0x1400887ba`
- `ntoskrnl!ZwOpenKey` at `0x140088891`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088781`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088852`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088781`
- `ntoskrnl!RtlInitUnicodeString` at `0x140088852`
- `ntoskrnl!ZwClose` at `0x1400887f5`
- `ntoskrnl!ZwClose` at `0x1400888cf`
- `ntoskrnl!ZwClose` at `0x1400887f5`
- `ntoskrnl!ZwClose` at `0x1400888cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088911`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088911`
- `ntoskrnl!ZwQueryKey` at `0x1400887e2`
- `ntoskrnl!ZwQueryKey` at `0x1400888bc`
- `ntoskrnl!ZwQueryKey` at `0x1400887e2`
- `ntoskrnl!ZwQueryKey` at `0x1400888bc`

## string_xrefs

- `0x140088751`: `\Registry\Machine\Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`

## pseudocode

```c
__int64 __fastcall CountPoliciesZoneMapSubKeysAndValues(char a1, __int64 a2, _DWORD *a3)
{
  WCHAR *v3; // rbx
  unsigned int v6; // esi
  int v8; // edi
  NTSTATUS v9; // r14d
  int v10; // eax
  NTSTATUS v11; // r14d
  void *KeyHandle; // [rsp+30h] [rbp-69h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-61h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-59h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-41h] BYREF
  __int128 KeyInformation; // [rsp+88h] [rbp-11h] BYREF
  __int128 v19; // [rsp+98h] [rbp-1h]
  __int128 v20; // [rsp+A8h] [rbp+Fh]

  v3 = 0;
  SourceString = 0;
  ResultLength = 0;
  v6 = 0;
  *a3 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v8 = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v19 = 0;
  v20 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    v9 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
    ZwClose(KeyHandle);
    KeyHandle = 0;
    if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147483643 )
      v8 = DWORD1(v19) + v20;
  }
  if ( !a1 )
  {
    v10 = BuildUserKeyPath(
            a2,
            L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap",
            &SourceString);
    v3 = (WCHAR *)SourceString;
    v6 = v10;
    if ( v10 < 0 )
      goto LABEL_12;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
    {
      v11 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
      ZwClose(KeyHandle);
      KeyHandle = 0;
      if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147483643 )
        v8 += v20 + DWORD1(v19);
    }
  }
  *a3 = v8;
LABEL_12:
  if ( v3 )
    ExFreePoolWithTag(v3, 0x7A4D6D53u);
  return v6;
}

```

## disassembly

```asm
0x140088710  mov     [rsp-8+arg_0], rbx
0x140088715  push    rbp
0x140088716  push    rsi
0x140088717  push    rdi
0x140088718  push    r12
0x14008871a  push    r13
0x14008871c  push    r14
0x14008871e  push    r15
0x140088720  lea     rbp, [rsp-27h]
0x140088725  sub     rsp, 0C0h
0x14008872c  mov     rax, cs:__security_cookie
0x140088733  xor     rax, rsp
0x140088736  mov     [rbp+57h+var_38], rax
0x14008873a  xorps   xmm0, xmm0
0x14008873d  xor     ebx, ebx
0x14008873f  mov     r13, rdx
0x140088742  mov     [rbp+57h+SourceString], rbx
0x140088746  mov     r12b, cl
0x140088749  mov     [rbp+57h+var_B8], ebx
0x14008874c  xor     esi, esi
0x14008874e  mov     [r8], ebx
0x140088751  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x140088758  mov     [rbp+57h+KeyHandle], rsi
0x14008875c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140088760  mov     r15, r8
0x140088763  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140088767  xor     edi, edi
0x140088769  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14008876d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088771  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140088775  movups  [rbp+57h+KeyInformation], xmm0
0x140088779  movups  [rbp+57h+var_58], xmm0
0x14008877d  movups  [rbp+57h+var_48], xmm0
0x140088781  call    cs:__imp_RtlInitUnicodeString
0x140088788  nop     dword ptr [rax+rax+00h]
0x14008878d  lea     rax, [rbp+57h+DestinationString]
0x140088791  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140088798  xorps   xmm0, xmm0
0x14008879b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14008879f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400887a3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400887a7  lea     edx, [rsi+1]; DesiredAccess
0x1400887aa  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400887b1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400887b5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400887ba  call    cs:__imp_ZwOpenKey
0x1400887c1  nop     dword ptr [rax+rax+00h]
0x1400887c6  test    eax, eax
0x1400887c8  js      short loc_140088821
0x1400887ca  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400887ce  lea     rax, [rbp+57h+var_B8]
0x1400887d2  lea     r9d, [rsi+30h]; Length
0x1400887d6  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x1400887db  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1400887df  lea     edx, [rsi+2]; KeyInformationClass
0x1400887e2  call    cs:__imp_ZwQueryKey
0x1400887e9  nop     dword ptr [rax+rax+00h]
0x1400887ee  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400887f2  mov     r14d, eax
0x1400887f5  call    cs:__imp_ZwClose
0x1400887fc  nop     dword ptr [rax+rax+00h]
0x140088801  mov     ecx, 80000000h
0x140088806  mov     [rbp+57h+KeyHandle], rbx
0x14008880a  lea     eax, [r14+rcx]
0x14008880e  test    ecx, eax
0x140088810  jnz     short loc_14008881B
0x140088812  cmp     r14d, 80000005h
0x140088819  jnz     short loc_140088821
0x14008881b  mov     edi, dword ptr [rbp+57h+var_48]
0x14008881e  add     edi, dword ptr [rbp+57h+var_58+4]
0x140088821  test    r12b, r12b
0x140088824  jnz     loc_140088901
0x14008882a  lea     r8, [rbp+57h+SourceString]
0x14008882e  mov     rcx, r13
0x140088831  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140088838  call    BuildUserKeyPath
0x14008883d  mov     rbx, [rbp+57h+SourceString]
0x140088841  mov     esi, eax
0x140088843  test    eax, eax
0x140088845  js      loc_140088904
0x14008884b  mov     rdx, rbx; SourceString
0x14008884e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140088852  call    cs:__imp_RtlInitUnicodeString
0x140088859  nop     dword ptr [rax+rax+00h]
0x14008885e  lea     rax, [rbp+57h+DestinationString]
0x140088862  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140088869  xorps   xmm0, xmm0
0x14008886c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140088870  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140088874  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14008887c  mov     edx, 1; DesiredAccess
0x140088881  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140088888  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14008888c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140088891  call    cs:__imp_ZwOpenKey
0x140088898  nop     dword ptr [rax+rax+00h]
0x14008889d  test    eax, eax
0x14008889f  js      short loc_140088901
0x1400888a1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400888a5  lea     rax, [rbp+57h+var_B8]
0x1400888a9  mov     r9d, 30h ; '0'; Length
0x1400888af  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x1400888b4  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1400888b8  lea     edx, [r9-2Eh]; KeyInformationClass
0x1400888bc  call    cs:__imp_ZwQueryKey
0x1400888c3  nop     dword ptr [rax+rax+00h]
0x1400888c8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400888cc  mov     r14d, eax
0x1400888cf  call    cs:__imp_ZwClose
0x1400888d6  nop     dword ptr [rax+rax+00h]
0x1400888db  mov     eax, 80000000h
0x1400888e0  mov     [rbp+57h+KeyHandle], 0
0x1400888e8  lea     ecx, [r14+rax]
0x1400888ec  test    eax, ecx
0x1400888ee  jnz     short loc_1400888F9
0x1400888f0  cmp     r14d, 80000005h
0x1400888f7  jnz     short loc_140088901
0x1400888f9  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x1400888fc  add     ecx, dword ptr [rbp+57h+var_48]
0x1400888ff  add     edi, ecx
0x140088901  mov     [r15], edi
0x140088904  test    rbx, rbx
0x140088907  jz      short loc_14008891D
0x140088909  mov     edx, 7A4D6D53h; Tag
0x14008890e  mov     rcx, rbx; P
0x140088911  call    cs:__imp_ExFreePoolWithTag
0x140088918  nop     dword ptr [rax+rax+00h]
0x14008891d  mov     eax, esi
0x14008891f  mov     rcx, [rbp+57h+var_38]
0x140088923  xor     rcx, rsp; StackCookie
0x140088926  call    __security_check_cookie
0x14008892b  mov     rbx, [rsp+0F0h+arg_0]
0x140088933  add     rsp, 0C0h
0x14008893a  pop     r15
0x14008893c  pop     r14
0x14008893e  pop     r13
0x140088940  pop     r12
0x140088942  pop     rdi
0x140088943  pop     rsi
0x140088944  pop     rbp
0x140088945  retn
```
