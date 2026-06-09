# BCryptGetFipsAlgorithmMode

- ea: `0x180024370`
- end: `0x180024543`
- name: `BCryptGetFipsAlgorithmMode`
- size: `467`
- prototype: `NTSTATUS __stdcall(BOOLEAN *pfEnabled)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002454c`

## callees

- `0x180024370`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800243f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x180024408`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a038b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a03a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a0498`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800243f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x180024408`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a038b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a03a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a0498`
- `ntoskrnl!ZwQueryValueKey` at `0x18002448d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a042c`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a04ce`
- `ntoskrnl!ZwQueryValueKey` at `0x18002448d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a042c`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a04ce`
- `ntoskrnl!ZwClose` at `0x180024527`
- `ntoskrnl!ZwClose` at `0x180024535`
- `ntoskrnl!ZwClose` at `0x180024527`
- `ntoskrnl!ZwClose` at `0x180024535`
- `ntoskrnl!ZwOpenKey` at `0x18002444f`
- `ntoskrnl!ZwOpenKey` at `0x1800a03ec`
- `ntoskrnl!ZwOpenKey` at `0x18002444f`
- `ntoskrnl!ZwOpenKey` at `0x1800a03ec`

## string_xrefs

- `0x1800243e5`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\FipsAlgorithmPolicy`
- `0x1800a037f`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

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
0x180024370  mov     r11, rsp
0x180024373  mov     [r11+10h], rbx
0x180024377  mov     [r11+18h], rsi
0x18002437b  push    rdi
0x18002437c  sub     rsp, 0C0h
0x180024383  mov     rax, cs:__security_cookie
0x18002438a  xor     rax, rsp
0x18002438d  mov     [rsp+0C8h+var_18], rax
0x180024395  mov     rdi, rcx
0x180024398  xor     esi, esi
0x18002439a  mov     [rsp+0C8h+var_98], esi
0x18002439e  mov     [r11-70h], rsi
0x1800243a2  mov     [r11-68h], rsi
0x1800243a6  mov     qword ptr [rsp+0C8h+DestinationString.Length], rsi
0x1800243ab  mov     [r11-80h], rsi
0x1800243af  xor     eax, eax
0x1800243b1  xorps   xmm0, xmm0
0x1800243b4  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x1800243b9  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x1800243be  movups  xmmword ptr [r11-44h], xmm0
0x1800243c3  mov     [rsp+0C8h+KeyHandle], rsi
0x1800243c8  mov     [r11-78h], rsi
0x1800243cc  movups  xmmword ptr [r11-30h], xmm0
0x1800243d1  mov     [r11-20h], eax
0x1800243d5  mov     [rsp+0C8h+var_94], esi
0x1800243d9  test    rcx, rcx
0x1800243dc  jz      loc_18002451D
0x1800243e2  mov     [rcx], sil
0x1800243e5  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800243ec  lea     rcx, [r11-70h]; DestinationString
0x1800243f0  call    cs:__imp_RtlInitUnicodeString
0x1800243f7  nop     dword ptr [rax+rax+00h]
0x1800243fc  lea     rdx, aEnabled; "Enabled"
0x180024403  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x180024408  call    cs:__imp_RtlInitUnicodeString
0x18002440f  nop     dword ptr [rax+rax+00h]
0x180024414  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x18002441c  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x180024421  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x18002442c  lea     rax, [rsp+0C8h+var_70]
0x180024431  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x180024436  xorps   xmm0, xmm0
0x180024439  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024442  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x180024447  lea     edx, [rsi+1]; DesiredAccess
0x18002444a  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002444f  call    cs:__imp_ZwOpenKey
0x180024456  nop     dword ptr [rax+rax+00h]
0x18002445b  mov     ebx, eax
0x18002445d  mov     [rsp+0C8h+var_98], eax
0x180024461  test    eax, eax
0x180024463  js      short loc_1800244CF
0x180024465  lea     rax, [rsp+0C8h+var_94]
0x18002446a  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18002446f  mov     [rsp+0C8h+Length], 14h; Length
0x180024477  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18002447f  lea     r8d, [rsi+2]; KeyValueInformationClass
0x180024483  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x180024488  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002448d  call    cs:__imp_ZwQueryValueKey
0x180024494  nop     dword ptr [rax+rax+00h]
0x180024499  mov     ebx, eax
0x18002449b  mov     [rsp+0C8h+var_98], eax
0x18002449f  test    eax, eax
0x1800244a1  js      short loc_1800244CF
0x1800244a3  cmp     [rsp+0C8h+var_2C], 4
0x1800244ab  jnz     short loc_1800244C6
0x1800244ad  cmp     [rsp+0C8h+var_28], 4
0x1800244b5  jnz     short loc_1800244C6
0x1800244b7  cmp     [rsp+0C8h+var_24], sil
0x1800244bf  jz      short loc_1800244CF
0x1800244c1  mov     byte ptr [rdi], 1
0x1800244c4  jmp     short loc_1800244CF
0x1800244c6  mov     ebx, 0C000003Eh
0x1800244cb  mov     [rsp+0C8h+var_98], ebx
0x1800244cf  test    ebx, ebx
0x1800244d1  cmovs   ebx, esi
0x1800244d4  mov     [rsp+0C8h+var_98], ebx
0x1800244d8  cmp     [rdi], sil
0x1800244db  jz      loc_1800A037F
0x1800244e1  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x1800244e6  test    rcx, rcx
0x1800244e9  jnz     short loc_180024527
0x1800244eb  mov     rcx, [rsp+0C8h+Handle]; Handle
0x1800244f0  test    rcx, rcx
0x1800244f3  jnz     short loc_180024535
0x1800244f5  mov     eax, ebx
0x1800244f7  mov     rcx, [rsp+0C8h+var_18]
0x1800244ff  xor     rcx, rsp; StackCookie
0x180024502  call    __security_check_cookie
0x180024507  lea     r11, [rsp+0C8h+var_8]
0x18002450f  mov     rbx, [r11+18h]
0x180024513  mov     rsi, [r11+20h]
0x180024517  mov     rsp, r11
0x18002451a  pop     rdi
0x18002451b  retn
0x18002451d  mov     ebx, 0C000000Dh
0x180024522  jmp     loc_1800A0376
0x180024527  call    cs:__imp_ZwClose
0x18002452e  nop     dword ptr [rax+rax+00h]
0x180024533  jmp     short loc_1800244EB
0x180024535  call    cs:__imp_ZwClose
0x18002453c  nop     dword ptr [rax+rax+00h]
0x180024541  jmp     short loc_1800244F5
0x18009e23d  push    rbp
0x18009e23f  sub     rsp, 30h
0x18009e243  mov     rbp, rdx
0x18009e246  mov     eax, [rbp+30h]
0x18009e249  xor     ecx, ecx
0x18009e24b  test    eax, eax
0x18009e24d  cmovs   eax, ecx
0x18009e250  mov     [rbp+30h], eax
0x18009e253  add     rsp, 30h
0x18009e257  pop     rbp
0x18009e258  retn
0x18009e25a  push    rbp
0x18009e25c  sub     rsp, 30h
0x18009e260  mov     rbp, rdx
0x18009e263  mov     eax, [rbp+30h]
0x18009e266  xor     ecx, ecx
0x18009e268  test    eax, eax
0x18009e26a  cmovs   eax, ecx
0x18009e26d  mov     [rbp+30h], eax
0x18009e270  add     rsp, 30h
0x18009e274  pop     rbp
0x18009e275  retn
0x18009e277  push    rbp
0x18009e279  sub     rsp, 30h
0x18009e27d  mov     rbp, rdx
0x18009e280  mov     eax, [rbp+30h]
0x18009e283  xor     ecx, ecx
0x18009e285  test    eax, eax
0x18009e287  cmovs   eax, ecx
0x18009e28a  mov     [rbp+30h], eax
0x18009e28d  add     rsp, 30h
0x18009e291  pop     rbp
0x18009e292  retn
0x1800a0374  mov     ebx, esi
0x1800a0376  mov     [rsp+0C8h+var_98], ebx
0x1800a037a  jmp     loc_1800244E1
0x1800a037f  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800a0386  lea     rcx, [rsp+0C8h+var_70]; DestinationString
0x1800a038b  call    cs:__imp_RtlInitUnicodeString
0x1800a0392  nop     dword ptr [rax+rax+00h]
0x1800a0397  lea     rdx, aFipsalgorithmp; "FipsAlgorithmPolicy"
0x1800a039e  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a03a3  call    cs:__imp_RtlInitUnicodeString
0x1800a03aa  nop     dword ptr [rax+rax+00h]
0x1800a03af  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1800a03b7  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x1800a03bc  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x1800a03c7  lea     rax, [rsp+0C8h+var_70]
0x1800a03cc  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x1800a03d1  xorps   xmm0, xmm0
0x1800a03d4  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a03dd  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x1800a03e2  mov     edx, 1; DesiredAccess
0x1800a03e7  lea     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a03ec  call    cs:__imp_ZwOpenKey
0x1800a03f3  nop     dword ptr [rax+rax+00h]
0x1800a03f8  mov     ebx, eax
0x1800a03fa  mov     [rsp+0C8h+var_98], eax
0x1800a03fe  test    eax, eax
0x1800a0400  js      short loc_1800A046E
0x1800a0402  lea     rax, [rsp+0C8h+var_94]
0x1800a0407  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a040c  mov     [rsp+0C8h+Length], 14h; Length
0x1800a0414  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a041c  mov     r8d, 2; KeyValueInformationClass
0x1800a0422  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a0427  mov     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a042c  call    cs:__imp_ZwQueryValueKey
0x1800a0433  nop     dword ptr [rax+rax+00h]
0x1800a0438  mov     ebx, eax
0x1800a043a  mov     [rsp+0C8h+var_98], eax
0x1800a043e  test    eax, eax
0x1800a0440  js      short loc_1800A046E
0x1800a0442  cmp     [rsp+0C8h+var_2C], 4
0x1800a044a  jnz     short loc_1800A0465
0x1800a044c  cmp     [rsp+0C8h+var_28], 4
0x1800a0454  jnz     short loc_1800A0465
0x1800a0456  cmp     [rsp+0C8h+var_24], sil
0x1800a045e  jz      short loc_1800A046E
0x1800a0460  mov     byte ptr [rdi], 1
0x1800a0463  jmp     short loc_1800A046E
0x1800a0465  mov     ebx, 0C000003Eh
0x1800a046a  mov     [rsp+0C8h+var_98], ebx
0x1800a046e  test    ebx, ebx
0x1800a0470  jns     short loc_1800A0478
0x1800a0472  mov     ebx, esi
0x1800a0474  mov     [rsp+0C8h+var_98], ebx
0x1800a0478  cmp     [rdi], sil
0x1800a047b  jnz     loc_1800244E1
0x1800a0481  cmp     [rsp+0C8h+KeyHandle], rsi
0x1800a0486  jz      loc_1800244E1
0x1800a048c  lea     rdx, aMdmenabled; "MDMEnabled"
0x1800a0493  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a0498  call    cs:__imp_RtlInitUnicodeString
0x1800a049f  nop     dword ptr [rax+rax+00h]
0x1800a04a4  lea     rax, [rsp+0C8h+var_94]
0x1800a04a9  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a04ae  mov     [rsp+0C8h+Length], 14h; Length
0x1800a04b6  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a04be  mov     r8d, 2; KeyValueInformationClass
0x1800a04c4  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a04c9  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x1800a04ce  call    cs:__imp_ZwQueryValueKey
0x1800a04d5  nop     dword ptr [rax+rax+00h]
0x1800a04da  mov     ebx, eax
0x1800a04dc  mov     [rsp+0C8h+var_98], eax
0x1800a04e0  test    eax, eax
0x1800a04e2  js      short loc_1800A0510
0x1800a04e4  cmp     [rsp+0C8h+var_2C], 4
0x1800a04ec  jnz     short loc_1800A0507
0x1800a04ee  cmp     [rsp+0C8h+var_28], 4
0x1800a04f6  jnz     short loc_1800A0507
0x1800a04f8  cmp     [rsp+0C8h+var_24], sil
0x1800a0500  jz      short loc_1800A0510
0x1800a0502  mov     byte ptr [rdi], 1
0x1800a0505  jmp     short loc_1800A0510
0x1800a0507  mov     ebx, 0C000003Eh
0x1800a050c  mov     [rsp+0C8h+var_98], ebx
0x1800a0510  test    ebx, ebx
0x1800a0512  jns     loc_1800244E1
0x1800a0518  jmp     loc_1800A0374
```
