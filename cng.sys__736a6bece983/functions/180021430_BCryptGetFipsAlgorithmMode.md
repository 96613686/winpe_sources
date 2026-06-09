# BCryptGetFipsAlgorithmMode

- ea: `0x180021430`
- end: `0x180021603`
- name: `BCryptGetFipsAlgorithmMode`
- size: `467`
- prototype: `NTSTATUS __stdcall(BOOLEAN *pfEnabled)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002160c`

## callees

- `0x180021430`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800214b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800214c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a1f41`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a1f59`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a204e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800214b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800214c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a1f41`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a1f59`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a204e`
- `ntoskrnl!ZwQueryValueKey` at `0x18002154d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a1fe2`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a2084`
- `ntoskrnl!ZwQueryValueKey` at `0x18002154d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a1fe2`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a2084`
- `ntoskrnl!ZwClose` at `0x1800215e7`
- `ntoskrnl!ZwClose` at `0x1800215f5`
- `ntoskrnl!ZwClose` at `0x1800215e7`
- `ntoskrnl!ZwClose` at `0x1800215f5`
- `ntoskrnl!ZwOpenKey` at `0x18002150f`
- `ntoskrnl!ZwOpenKey` at `0x1800a1fa2`
- `ntoskrnl!ZwOpenKey` at `0x18002150f`
- `ntoskrnl!ZwOpenKey` at `0x1800a1fa2`

## string_xrefs

- `0x1800214a5`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\FipsAlgorithmPolicy`
- `0x1800a1f35`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
NTSTATUS __stdcall BCryptGetFipsAlgorithmMode(BOOLEAN *pfEnabled)
{
  int v2; // ebx
  ULONG ResultLength; // [rsp+34h] [rbp-94h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-78h] BYREF
  struct _UNICODE_STRING v8; // [rsp+58h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-60h] BYREF
  __int128 KeyValueInformation; // [rsp+98h] [rbp-30h] BYREF
  int v11; // [rsp+A8h] [rbp-20h]

  *(_QWORD *)&v8.Length = 0;
  v8.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  Handle = 0;
  KeyValueInformation = 0;
  v11 = 0;
  ResultLength = 0;
  if ( pfEnabled )
  {
    *pfEnabled = 0;
    RtlInitUnicodeString(&v8, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\FipsAlgorithmPolicy");
    RtlInitUnicodeString(&DestinationString, L"Enabled");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v8;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
    if ( v2 >= 0 )
    {
      v2 = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
      if ( v2 >= 0 )
      {
        if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
        {
          if ( BYTE12(KeyValueInformation) )
            *pfEnabled = 1;
        }
        else
        {
          v2 = -1073741762;
        }
      }
    }
    if ( v2 < 0 )
      v2 = 0;
    if ( !*pfEnabled )
    {
      RtlInitUnicodeString(&v8, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
      RtlInitUnicodeString(&DestinationString, L"FipsAlgorithmPolicy");
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &v8;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v2 = ZwOpenKey(&Handle, 1u, &ObjectAttributes);
      if ( v2 >= 0 )
      {
        v2 = ZwQueryValueKey(
               Handle,
               &DestinationString,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength);
        if ( v2 >= 0 )
        {
          if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
          {
            if ( BYTE12(KeyValueInformation) )
              *pfEnabled = 1;
          }
          else
          {
            v2 = -1073741762;
          }
        }
      }
      if ( v2 < 0 )
        v2 = 0;
      if ( !*pfEnabled && KeyHandle )
      {
        RtlInitUnicodeString(&DestinationString, L"MDMEnabled");
        v2 = ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x14u,
               &ResultLength);
        if ( v2 >= 0 )
        {
          if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
          {
            if ( BYTE12(KeyValueInformation) )
              *pfEnabled = 1;
          }
          else
          {
            v2 = -1073741762;
          }
        }
        if ( v2 < 0 )
          v2 = 0;
      }
    }
  }
  else
  {
    v2 = -1073741811;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return v2;
}

```

## disassembly

```asm
0x180021430  mov     r11, rsp
0x180021433  mov     [r11+10h], rbx
0x180021437  mov     [r11+18h], rsi
0x18002143b  push    rdi
0x18002143c  sub     rsp, 0C0h
0x180021443  mov     rax, cs:__security_cookie
0x18002144a  xor     rax, rsp
0x18002144d  mov     [rsp+0C8h+var_18], rax
0x180021455  mov     rdi, rcx
0x180021458  xor     esi, esi
0x18002145a  mov     [rsp+0C8h+var_98], esi
0x18002145e  mov     [r11-70h], rsi
0x180021462  mov     [r11-68h], rsi
0x180021466  mov     qword ptr [rsp+0C8h+DestinationString.Length], rsi
0x18002146b  mov     [r11-80h], rsi
0x18002146f  xor     eax, eax
0x180021471  xorps   xmm0, xmm0
0x180021474  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x180021479  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x18002147e  movups  xmmword ptr [r11-44h], xmm0
0x180021483  mov     [rsp+0C8h+KeyHandle], rsi
0x180021488  mov     [r11-78h], rsi
0x18002148c  movups  xmmword ptr [r11-30h], xmm0
0x180021491  mov     [r11-20h], eax
0x180021495  mov     [rsp+0C8h+var_94], esi
0x180021499  test    rcx, rcx
0x18002149c  jz      loc_1800215DD
0x1800214a2  mov     [rcx], sil
0x1800214a5  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800214ac  lea     rcx, [r11-70h]; DestinationString
0x1800214b0  call    cs:__imp_RtlInitUnicodeString
0x1800214b7  nop     dword ptr [rax+rax+00h]
0x1800214bc  lea     rdx, aEnabled; "Enabled"
0x1800214c3  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800214c8  call    cs:__imp_RtlInitUnicodeString
0x1800214cf  nop     dword ptr [rax+rax+00h]
0x1800214d4  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1800214dc  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x1800214e1  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x1800214ec  lea     rax, [rsp+0C8h+var_70]
0x1800214f1  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x1800214f6  xorps   xmm0, xmm0
0x1800214f9  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180021502  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x180021507  lea     edx, [rsi+1]; DesiredAccess
0x18002150a  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002150f  call    cs:__imp_ZwOpenKey
0x180021516  nop     dword ptr [rax+rax+00h]
0x18002151b  mov     ebx, eax
0x18002151d  mov     [rsp+0C8h+var_98], eax
0x180021521  test    eax, eax
0x180021523  js      short loc_18002158F
0x180021525  lea     rax, [rsp+0C8h+var_94]
0x18002152a  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18002152f  mov     [rsp+0C8h+Length], 14h; Length
0x180021537  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18002153f  lea     r8d, [rsi+2]; KeyValueInformationClass
0x180021543  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x180021548  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002154d  call    cs:__imp_ZwQueryValueKey
0x180021554  nop     dword ptr [rax+rax+00h]
0x180021559  mov     ebx, eax
0x18002155b  mov     [rsp+0C8h+var_98], eax
0x18002155f  test    eax, eax
0x180021561  js      short loc_18002158F
0x180021563  cmp     [rsp+0C8h+var_2C], 4
0x18002156b  jnz     short loc_180021586
0x18002156d  cmp     [rsp+0C8h+var_28], 4
0x180021575  jnz     short loc_180021586
0x180021577  cmp     [rsp+0C8h+var_24], sil
0x18002157f  jz      short loc_18002158F
0x180021581  mov     byte ptr [rdi], 1
0x180021584  jmp     short loc_18002158F
0x180021586  mov     ebx, 0C000003Eh
0x18002158b  mov     [rsp+0C8h+var_98], ebx
0x18002158f  test    ebx, ebx
0x180021591  cmovs   ebx, esi
0x180021594  mov     [rsp+0C8h+var_98], ebx
0x180021598  cmp     [rdi], sil
0x18002159b  jz      loc_1800A1F35
0x1800215a1  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x1800215a6  test    rcx, rcx
0x1800215a9  jnz     short loc_1800215E7
0x1800215ab  mov     rcx, [rsp+0C8h+Handle]; Handle
0x1800215b0  test    rcx, rcx
0x1800215b3  jnz     short loc_1800215F5
0x1800215b5  mov     eax, ebx
0x1800215b7  mov     rcx, [rsp+0C8h+var_18]
0x1800215bf  xor     rcx, rsp; StackCookie
0x1800215c2  call    __security_check_cookie
0x1800215c7  lea     r11, [rsp+0C8h+var_8]
0x1800215cf  mov     rbx, [r11+18h]
0x1800215d3  mov     rsi, [r11+20h]
0x1800215d7  mov     rsp, r11
0x1800215da  pop     rdi
0x1800215db  retn
0x1800215dd  mov     ebx, 0C000000Dh
0x1800215e2  jmp     loc_1800A1F2C
0x1800215e7  call    cs:__imp_ZwClose
0x1800215ee  nop     dword ptr [rax+rax+00h]
0x1800215f3  jmp     short loc_1800215AB
0x1800215f5  call    cs:__imp_ZwClose
0x1800215fc  nop     dword ptr [rax+rax+00h]
0x180021601  jmp     short loc_1800215B5
0x1800a006d  push    rbp
0x1800a006f  sub     rsp, 30h
0x1800a0073  mov     rbp, rdx
0x1800a0076  mov     eax, [rbp+30h]
0x1800a0079  xor     ecx, ecx
0x1800a007b  test    eax, eax
0x1800a007d  cmovs   eax, ecx
0x1800a0080  mov     [rbp+30h], eax
0x1800a0083  add     rsp, 30h
0x1800a0087  pop     rbp
0x1800a0088  retn
0x1800a008a  push    rbp
0x1800a008c  sub     rsp, 30h
0x1800a0090  mov     rbp, rdx
0x1800a0093  mov     eax, [rbp+30h]
0x1800a0096  xor     ecx, ecx
0x1800a0098  test    eax, eax
0x1800a009a  cmovs   eax, ecx
0x1800a009d  mov     [rbp+30h], eax
0x1800a00a0  add     rsp, 30h
0x1800a00a4  pop     rbp
0x1800a00a5  retn
0x1800a00a7  push    rbp
0x1800a00a9  sub     rsp, 30h
0x1800a00ad  mov     rbp, rdx
0x1800a00b0  mov     eax, [rbp+30h]
0x1800a00b3  xor     ecx, ecx
0x1800a00b5  test    eax, eax
0x1800a00b7  cmovs   eax, ecx
0x1800a00ba  mov     [rbp+30h], eax
0x1800a00bd  add     rsp, 30h
0x1800a00c1  pop     rbp
0x1800a00c2  retn
0x1800a1f2a  mov     ebx, esi
0x1800a1f2c  mov     [rsp+0C8h+var_98], ebx
0x1800a1f30  jmp     loc_1800215A1
0x1800a1f35  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800a1f3c  lea     rcx, [rsp+0C8h+var_70]; DestinationString
0x1800a1f41  call    cs:__imp_RtlInitUnicodeString
0x1800a1f48  nop     dword ptr [rax+rax+00h]
0x1800a1f4d  lea     rdx, aFipsalgorithmp; "FipsAlgorithmPolicy"
0x1800a1f54  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a1f59  call    cs:__imp_RtlInitUnicodeString
0x1800a1f60  nop     dword ptr [rax+rax+00h]
0x1800a1f65  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1800a1f6d  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x1800a1f72  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x1800a1f7d  lea     rax, [rsp+0C8h+var_70]
0x1800a1f82  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x1800a1f87  xorps   xmm0, xmm0
0x1800a1f8a  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a1f93  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x1800a1f98  mov     edx, 1; DesiredAccess
0x1800a1f9d  lea     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a1fa2  call    cs:__imp_ZwOpenKey
0x1800a1fa9  nop     dword ptr [rax+rax+00h]
0x1800a1fae  mov     ebx, eax
0x1800a1fb0  mov     [rsp+0C8h+var_98], eax
0x1800a1fb4  test    eax, eax
0x1800a1fb6  js      short loc_1800A2024
0x1800a1fb8  lea     rax, [rsp+0C8h+var_94]
0x1800a1fbd  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a1fc2  mov     [rsp+0C8h+Length], 14h; Length
0x1800a1fca  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a1fd2  mov     r8d, 2; KeyValueInformationClass
0x1800a1fd8  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a1fdd  mov     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a1fe2  call    cs:__imp_ZwQueryValueKey
0x1800a1fe9  nop     dword ptr [rax+rax+00h]
0x1800a1fee  mov     ebx, eax
0x1800a1ff0  mov     [rsp+0C8h+var_98], eax
0x1800a1ff4  test    eax, eax
0x1800a1ff6  js      short loc_1800A2024
0x1800a1ff8  cmp     [rsp+0C8h+var_2C], 4
0x1800a2000  jnz     short loc_1800A201B
0x1800a2002  cmp     [rsp+0C8h+var_28], 4
0x1800a200a  jnz     short loc_1800A201B
0x1800a200c  cmp     [rsp+0C8h+var_24], sil
0x1800a2014  jz      short loc_1800A2024
0x1800a2016  mov     byte ptr [rdi], 1
0x1800a2019  jmp     short loc_1800A2024
0x1800a201b  mov     ebx, 0C000003Eh
0x1800a2020  mov     [rsp+0C8h+var_98], ebx
0x1800a2024  test    ebx, ebx
0x1800a2026  jns     short loc_1800A202E
0x1800a2028  mov     ebx, esi
0x1800a202a  mov     [rsp+0C8h+var_98], ebx
0x1800a202e  cmp     [rdi], sil
0x1800a2031  jnz     loc_1800215A1
0x1800a2037  cmp     [rsp+0C8h+KeyHandle], rsi
0x1800a203c  jz      loc_1800215A1
0x1800a2042  lea     rdx, aMdmenabled; "MDMEnabled"
0x1800a2049  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a204e  call    cs:__imp_RtlInitUnicodeString
0x1800a2055  nop     dword ptr [rax+rax+00h]
0x1800a205a  lea     rax, [rsp+0C8h+var_94]
0x1800a205f  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a2064  mov     [rsp+0C8h+Length], 14h; Length
0x1800a206c  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a2074  mov     r8d, 2; KeyValueInformationClass
0x1800a207a  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a207f  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x1800a2084  call    cs:__imp_ZwQueryValueKey
0x1800a208b  nop     dword ptr [rax+rax+00h]
0x1800a2090  mov     ebx, eax
0x1800a2092  mov     [rsp+0C8h+var_98], eax
0x1800a2096  test    eax, eax
0x1800a2098  js      short loc_1800A20C6
0x1800a209a  cmp     [rsp+0C8h+var_2C], 4
0x1800a20a2  jnz     short loc_1800A20BD
0x1800a20a4  cmp     [rsp+0C8h+var_28], 4
0x1800a20ac  jnz     short loc_1800A20BD
0x1800a20ae  cmp     [rsp+0C8h+var_24], sil
0x1800a20b6  jz      short loc_1800A20C6
0x1800a20b8  mov     byte ptr [rdi], 1
0x1800a20bb  jmp     short loc_1800A20C6
0x1800a20bd  mov     ebx, 0C000003Eh
0x1800a20c2  mov     [rsp+0C8h+var_98], ebx
0x1800a20c6  test    ebx, ebx
0x1800a20c8  jns     loc_1800215A1
0x1800a20ce  jmp     loc_1800A1F2A
```
