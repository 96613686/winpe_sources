# CountPoliciesZoneMapSubKeysAndValues

- ea: `0x140088760`
- end: `0x140088997`
- name: `CountPoliciesZoneMapSubKeysAndValues`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140089e54`

## callees

- `0x140059dc0`
- `0x1400881a8`
- `0x140088760`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008880a`
- `ntoskrnl!ZwOpenKey` at `0x1400888e1`
- `ntoskrnl!ZwOpenKey` at `0x14008880a`
- `ntoskrnl!ZwOpenKey` at `0x1400888e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400887d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400888a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400887d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400888a2`
- `ntoskrnl!ZwClose` at `0x140088845`
- `ntoskrnl!ZwClose` at `0x14008891f`
- `ntoskrnl!ZwClose` at `0x140088845`
- `ntoskrnl!ZwClose` at `0x14008891f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088961`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088961`
- `ntoskrnl!ZwQueryKey` at `0x140088832`
- `ntoskrnl!ZwQueryKey` at `0x14008890c`
- `ntoskrnl!ZwQueryKey` at `0x140088832`
- `ntoskrnl!ZwQueryKey` at `0x14008890c`

## string_xrefs

- `0x1400887a1`: `\Registry\Machine\Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`

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
0x140088760  mov     [rsp-8+arg_0], rbx
0x140088765  push    rbp
0x140088766  push    rsi
0x140088767  push    rdi
0x140088768  push    r12
0x14008876a  push    r13
0x14008876c  push    r14
0x14008876e  push    r15
0x140088770  lea     rbp, [rsp-27h]
0x140088775  sub     rsp, 0C0h
0x14008877c  mov     rax, cs:__security_cookie
0x140088783  xor     rax, rsp
0x140088786  mov     [rbp+57h+var_38], rax
0x14008878a  xorps   xmm0, xmm0
0x14008878d  xor     ebx, ebx
0x14008878f  mov     r13, rdx
0x140088792  mov     [rbp+57h+SourceString], rbx
0x140088796  mov     r12b, cl
0x140088799  mov     [rbp+57h+var_B8], ebx
0x14008879c  xor     esi, esi
0x14008879e  mov     [r8], ebx
0x1400887a1  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x1400887a8  mov     [rbp+57h+KeyHandle], rsi
0x1400887ac  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400887b0  mov     r15, r8
0x1400887b3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400887b7  xor     edi, edi
0x1400887b9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400887bd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400887c1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400887c5  movups  [rbp+57h+KeyInformation], xmm0
0x1400887c9  movups  [rbp+57h+var_58], xmm0
0x1400887cd  movups  [rbp+57h+var_48], xmm0
0x1400887d1  call    cs:__imp_RtlInitUnicodeString
0x1400887d8  nop     dword ptr [rax+rax+00h]
0x1400887dd  lea     rax, [rbp+57h+DestinationString]
0x1400887e1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400887e8  xorps   xmm0, xmm0
0x1400887eb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400887ef  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400887f3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400887f7  lea     edx, [rsi+1]; DesiredAccess
0x1400887fa  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140088801  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140088805  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008880a  call    cs:__imp_ZwOpenKey
0x140088811  nop     dword ptr [rax+rax+00h]
0x140088816  test    eax, eax
0x140088818  js      short loc_140088871
0x14008881a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14008881e  lea     rax, [rbp+57h+var_B8]
0x140088822  lea     r9d, [rsi+30h]; Length
0x140088826  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14008882b  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14008882f  lea     edx, [rsi+2]; KeyInformationClass
0x140088832  call    cs:__imp_ZwQueryKey
0x140088839  nop     dword ptr [rax+rax+00h]
0x14008883e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140088842  mov     r14d, eax
0x140088845  call    cs:__imp_ZwClose
0x14008884c  nop     dword ptr [rax+rax+00h]
0x140088851  mov     ecx, 80000000h
0x140088856  mov     [rbp+57h+KeyHandle], rbx
0x14008885a  lea     eax, [r14+rcx]
0x14008885e  test    ecx, eax
0x140088860  jnz     short loc_14008886B
0x140088862  cmp     r14d, 80000005h
0x140088869  jnz     short loc_140088871
0x14008886b  mov     edi, dword ptr [rbp+57h+var_48]
0x14008886e  add     edi, dword ptr [rbp+57h+var_58+4]
0x140088871  test    r12b, r12b
0x140088874  jnz     loc_140088951
0x14008887a  lea     r8, [rbp+57h+SourceString]
0x14008887e  mov     rcx, r13
0x140088881  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x140088888  call    BuildUserKeyPath
0x14008888d  mov     rbx, [rbp+57h+SourceString]
0x140088891  mov     esi, eax
0x140088893  test    eax, eax
0x140088895  js      loc_140088954
0x14008889b  mov     rdx, rbx; SourceString
0x14008889e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400888a2  call    cs:__imp_RtlInitUnicodeString
0x1400888a9  nop     dword ptr [rax+rax+00h]
0x1400888ae  lea     rax, [rbp+57h+DestinationString]
0x1400888b2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400888b9  xorps   xmm0, xmm0
0x1400888bc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400888c0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400888c4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400888cc  mov     edx, 1; DesiredAccess
0x1400888d1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400888d8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400888dc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400888e1  call    cs:__imp_ZwOpenKey
0x1400888e8  nop     dword ptr [rax+rax+00h]
0x1400888ed  test    eax, eax
0x1400888ef  js      short loc_140088951
0x1400888f1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400888f5  lea     rax, [rbp+57h+var_B8]
0x1400888f9  mov     r9d, 30h ; '0'; Length
0x1400888ff  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x140088904  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x140088908  lea     edx, [r9-2Eh]; KeyInformationClass
0x14008890c  call    cs:__imp_ZwQueryKey
0x140088913  nop     dword ptr [rax+rax+00h]
0x140088918  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14008891c  mov     r14d, eax
0x14008891f  call    cs:__imp_ZwClose
0x140088926  nop     dword ptr [rax+rax+00h]
0x14008892b  mov     eax, 80000000h
0x140088930  mov     [rbp+57h+KeyHandle], 0
0x140088938  lea     ecx, [r14+rax]
0x14008893c  test    eax, ecx
0x14008893e  jnz     short loc_140088949
0x140088940  cmp     r14d, 80000005h
0x140088947  jnz     short loc_140088951
0x140088949  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x14008894c  add     ecx, dword ptr [rbp+57h+var_48]
0x14008894f  add     edi, ecx
0x140088951  mov     [r15], edi
0x140088954  test    rbx, rbx
0x140088957  jz      short loc_14008896D
0x140088959  mov     edx, 7A4D6D53h; Tag
0x14008895e  mov     rcx, rbx; P
0x140088961  call    cs:__imp_ExFreePoolWithTag
0x140088968  nop     dword ptr [rax+rax+00h]
0x14008896d  mov     eax, esi
0x14008896f  mov     rcx, [rbp+57h+var_38]
0x140088973  xor     rcx, rsp; StackCookie
0x140088976  call    __security_check_cookie
0x14008897b  mov     rbx, [rsp+0F0h+arg_0]
0x140088983  add     rsp, 0C0h
0x14008898a  pop     r15
0x14008898c  pop     r14
0x14008898e  pop     r13
0x140088990  pop     r12
0x140088992  pop     rdi
0x140088993  pop     rsi
0x140088994  pop     rbp
0x140088995  retn
```
