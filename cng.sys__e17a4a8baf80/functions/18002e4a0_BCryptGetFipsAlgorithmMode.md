# BCryptGetFipsAlgorithmMode

- ea: `0x18002e4a0`
- end: `0x18002e673`
- name: `BCryptGetFipsAlgorithmMode`
- size: `467`
- prototype: `NTSTATUS __stdcall(BOOLEAN *pfEnabled)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e67c`

## callees

- `0x18002e4a0`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18002e520`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e538`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7129`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7141`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7236`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e520`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e538`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7129`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7141`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a7236`
- `ntoskrnl!ZwQueryValueKey` at `0x18002e5bd`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a71ca`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a726c`
- `ntoskrnl!ZwQueryValueKey` at `0x18002e5bd`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a71ca`
- `ntoskrnl!ZwQueryValueKey` at `0x1800a726c`
- `ntoskrnl!ZwClose` at `0x18002e657`
- `ntoskrnl!ZwClose` at `0x18002e665`
- `ntoskrnl!ZwClose` at `0x18002e657`
- `ntoskrnl!ZwClose` at `0x18002e665`
- `ntoskrnl!ZwOpenKey` at `0x18002e57f`
- `ntoskrnl!ZwOpenKey` at `0x1800a718a`
- `ntoskrnl!ZwOpenKey` at `0x18002e57f`
- `ntoskrnl!ZwOpenKey` at `0x1800a718a`

## string_xrefs

- `0x18002e515`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\FipsAlgorithmPolicy`
- `0x1800a711d`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

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
0x18002e4a0  mov     r11, rsp
0x18002e4a3  mov     [r11+10h], rbx
0x18002e4a7  mov     [r11+18h], rsi
0x18002e4ab  push    rdi
0x18002e4ac  sub     rsp, 0C0h
0x18002e4b3  mov     rax, cs:__security_cookie
0x18002e4ba  xor     rax, rsp
0x18002e4bd  mov     [rsp+0C8h+var_18], rax
0x18002e4c5  mov     rdi, rcx
0x18002e4c8  xor     esi, esi
0x18002e4ca  mov     [rsp+0C8h+var_98], esi
0x18002e4ce  mov     [r11-70h], rsi
0x18002e4d2  mov     [r11-68h], rsi
0x18002e4d6  mov     qword ptr [rsp+0C8h+DestinationString.Length], rsi
0x18002e4db  mov     [r11-80h], rsi
0x18002e4df  xor     eax, eax
0x18002e4e1  xorps   xmm0, xmm0
0x18002e4e4  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.Length], xmm0
0x18002e4e9  movups  xmmword ptr [rsp+0C8h+ObjectAttributes.ObjectName], xmm0
0x18002e4ee  movups  xmmword ptr [r11-44h], xmm0
0x18002e4f3  mov     [rsp+0C8h+KeyHandle], rsi
0x18002e4f8  mov     [r11-78h], rsi
0x18002e4fc  movups  xmmword ptr [r11-30h], xmm0
0x18002e501  mov     [r11-20h], eax
0x18002e505  mov     [rsp+0C8h+var_94], esi
0x18002e509  test    rcx, rcx
0x18002e50c  jz      loc_18002E64D
0x18002e512  mov     [rcx], sil
0x18002e515  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18002e51c  lea     rcx, [r11-70h]; DestinationString
0x18002e520  call    cs:__imp_RtlInitUnicodeString
0x18002e527  nop     dword ptr [rax+rax+00h]
0x18002e52c  lea     rdx, aEnabled; "Enabled"
0x18002e533  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18002e538  call    cs:__imp_RtlInitUnicodeString
0x18002e53f  nop     dword ptr [rax+rax+00h]
0x18002e544  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x18002e54c  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x18002e551  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x18002e55c  lea     rax, [rsp+0C8h+var_70]
0x18002e561  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x18002e566  xorps   xmm0, xmm0
0x18002e569  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002e572  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x18002e577  lea     edx, [rsi+1]; DesiredAccess
0x18002e57a  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002e57f  call    cs:__imp_ZwOpenKey
0x18002e586  nop     dword ptr [rax+rax+00h]
0x18002e58b  mov     ebx, eax
0x18002e58d  mov     [rsp+0C8h+var_98], eax
0x18002e591  test    eax, eax
0x18002e593  js      short loc_18002E5FF
0x18002e595  lea     rax, [rsp+0C8h+var_94]
0x18002e59a  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18002e59f  mov     [rsp+0C8h+Length], 14h; Length
0x18002e5a7  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x18002e5af  lea     r8d, [rsi+2]; KeyValueInformationClass
0x18002e5b3  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x18002e5b8  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x18002e5bd  call    cs:__imp_ZwQueryValueKey
0x18002e5c4  nop     dword ptr [rax+rax+00h]
0x18002e5c9  mov     ebx, eax
0x18002e5cb  mov     [rsp+0C8h+var_98], eax
0x18002e5cf  test    eax, eax
0x18002e5d1  js      short loc_18002E5FF
0x18002e5d3  cmp     [rsp+0C8h+var_2C], 4
0x18002e5db  jnz     short loc_18002E5F6
0x18002e5dd  cmp     [rsp+0C8h+var_28], 4
0x18002e5e5  jnz     short loc_18002E5F6
0x18002e5e7  cmp     [rsp+0C8h+var_24], sil
0x18002e5ef  jz      short loc_18002E5FF
0x18002e5f1  mov     byte ptr [rdi], 1
0x18002e5f4  jmp     short loc_18002E5FF
0x18002e5f6  mov     ebx, 0C000003Eh
0x18002e5fb  mov     [rsp+0C8h+var_98], ebx
0x18002e5ff  test    ebx, ebx
0x18002e601  cmovs   ebx, esi
0x18002e604  mov     [rsp+0C8h+var_98], ebx
0x18002e608  cmp     [rdi], sil
0x18002e60b  jz      loc_1800A711D
0x18002e611  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x18002e616  test    rcx, rcx
0x18002e619  jnz     short loc_18002E657
0x18002e61b  mov     rcx, [rsp+0C8h+Handle]; Handle
0x18002e620  test    rcx, rcx
0x18002e623  jnz     short loc_18002E665
0x18002e625  mov     eax, ebx
0x18002e627  mov     rcx, [rsp+0C8h+var_18]
0x18002e62f  xor     rcx, rsp; StackCookie
0x18002e632  call    __security_check_cookie
0x18002e637  lea     r11, [rsp+0C8h+var_8]
0x18002e63f  mov     rbx, [r11+18h]
0x18002e643  mov     rsi, [r11+20h]
0x18002e647  mov     rsp, r11
0x18002e64a  pop     rdi
0x18002e64b  retn
0x18002e64d  mov     ebx, 0C000000Dh
0x18002e652  jmp     loc_1800A7114
0x18002e657  call    cs:__imp_ZwClose
0x18002e65e  nop     dword ptr [rax+rax+00h]
0x18002e663  jmp     short loc_18002E61B
0x18002e665  call    cs:__imp_ZwClose
0x18002e66c  nop     dword ptr [rax+rax+00h]
0x18002e671  jmp     short loc_18002E625
0x1800a4fdb  push    rbp
0x1800a4fdd  sub     rsp, 30h
0x1800a4fe1  mov     rbp, rdx
0x1800a4fe4  mov     eax, [rbp+30h]
0x1800a4fe7  xor     ecx, ecx
0x1800a4fe9  test    eax, eax
0x1800a4feb  cmovs   eax, ecx
0x1800a4fee  mov     [rbp+30h], eax
0x1800a4ff1  add     rsp, 30h
0x1800a4ff5  pop     rbp
0x1800a4ff6  retn
0x1800a4ff8  push    rbp
0x1800a4ffa  sub     rsp, 30h
0x1800a4ffe  mov     rbp, rdx
0x1800a5001  mov     eax, [rbp+30h]
0x1800a5004  xor     ecx, ecx
0x1800a5006  test    eax, eax
0x1800a5008  cmovs   eax, ecx
0x1800a500b  mov     [rbp+30h], eax
0x1800a500e  add     rsp, 30h
0x1800a5012  pop     rbp
0x1800a5013  retn
0x1800a5015  push    rbp
0x1800a5017  sub     rsp, 30h
0x1800a501b  mov     rbp, rdx
0x1800a501e  mov     eax, [rbp+30h]
0x1800a5021  xor     ecx, ecx
0x1800a5023  test    eax, eax
0x1800a5025  cmovs   eax, ecx
0x1800a5028  mov     [rbp+30h], eax
0x1800a502b  add     rsp, 30h
0x1800a502f  pop     rbp
0x1800a5030  retn
0x1800a7112  mov     ebx, esi
0x1800a7114  mov     [rsp+0C8h+var_98], ebx
0x1800a7118  jmp     loc_18002E611
0x1800a711d  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800a7124  lea     rcx, [rsp+0C8h+var_70]; DestinationString
0x1800a7129  call    cs:__imp_RtlInitUnicodeString
0x1800a7130  nop     dword ptr [rax+rax+00h]
0x1800a7135  lea     rdx, aFipsalgorithmp; "FipsAlgorithmPolicy"
0x1800a713c  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a7141  call    cs:__imp_RtlInitUnicodeString
0x1800a7148  nop     dword ptr [rax+rax+00h]
0x1800a714d  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x1800a7155  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x1800a715a  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x1800a7165  lea     rax, [rsp+0C8h+var_70]
0x1800a716a  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x1800a716f  xorps   xmm0, xmm0
0x1800a7172  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a717b  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x1800a7180  mov     edx, 1; DesiredAccess
0x1800a7185  lea     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a718a  call    cs:__imp_ZwOpenKey
0x1800a7191  nop     dword ptr [rax+rax+00h]
0x1800a7196  mov     ebx, eax
0x1800a7198  mov     [rsp+0C8h+var_98], eax
0x1800a719c  test    eax, eax
0x1800a719e  js      short loc_1800A720C
0x1800a71a0  lea     rax, [rsp+0C8h+var_94]
0x1800a71a5  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a71aa  mov     [rsp+0C8h+Length], 14h; Length
0x1800a71b2  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a71ba  mov     r8d, 2; KeyValueInformationClass
0x1800a71c0  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a71c5  mov     rcx, [rsp+0C8h+Handle]; KeyHandle
0x1800a71ca  call    cs:__imp_ZwQueryValueKey
0x1800a71d1  nop     dword ptr [rax+rax+00h]
0x1800a71d6  mov     ebx, eax
0x1800a71d8  mov     [rsp+0C8h+var_98], eax
0x1800a71dc  test    eax, eax
0x1800a71de  js      short loc_1800A720C
0x1800a71e0  cmp     [rsp+0C8h+var_2C], 4
0x1800a71e8  jnz     short loc_1800A7203
0x1800a71ea  cmp     [rsp+0C8h+var_28], 4
0x1800a71f2  jnz     short loc_1800A7203
0x1800a71f4  cmp     [rsp+0C8h+var_24], sil
0x1800a71fc  jz      short loc_1800A720C
0x1800a71fe  mov     byte ptr [rdi], 1
0x1800a7201  jmp     short loc_1800A720C
0x1800a7203  mov     ebx, 0C000003Eh
0x1800a7208  mov     [rsp+0C8h+var_98], ebx
0x1800a720c  test    ebx, ebx
0x1800a720e  jns     short loc_1800A7216
0x1800a7210  mov     ebx, esi
0x1800a7212  mov     [rsp+0C8h+var_98], ebx
0x1800a7216  cmp     [rdi], sil
0x1800a7219  jnz     loc_18002E611
0x1800a721f  cmp     [rsp+0C8h+KeyHandle], rsi
0x1800a7224  jz      loc_18002E611
0x1800a722a  lea     rdx, aMdmenabled; "MDMEnabled"
0x1800a7231  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1800a7236  call    cs:__imp_RtlInitUnicodeString
0x1800a723d  nop     dword ptr [rax+rax+00h]
0x1800a7242  lea     rax, [rsp+0C8h+var_94]
0x1800a7247  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800a724c  mov     [rsp+0C8h+Length], 14h; Length
0x1800a7254  lea     r9, [rsp+0C8h+KeyValueInformation]; KeyValueInformation
0x1800a725c  mov     r8d, 2; KeyValueInformationClass
0x1800a7262  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x1800a7267  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x1800a726c  call    cs:__imp_ZwQueryValueKey
0x1800a7273  nop     dword ptr [rax+rax+00h]
0x1800a7278  mov     ebx, eax
0x1800a727a  mov     [rsp+0C8h+var_98], eax
0x1800a727e  test    eax, eax
0x1800a7280  js      short loc_1800A72AE
0x1800a7282  cmp     [rsp+0C8h+var_2C], 4
0x1800a728a  jnz     short loc_1800A72A5
0x1800a728c  cmp     [rsp+0C8h+var_28], 4
0x1800a7294  jnz     short loc_1800A72A5
0x1800a7296  cmp     [rsp+0C8h+var_24], sil
0x1800a729e  jz      short loc_1800A72AE
0x1800a72a0  mov     byte ptr [rdi], 1
0x1800a72a3  jmp     short loc_1800A72AE
0x1800a72a5  mov     ebx, 0C000003Eh
0x1800a72aa  mov     [rsp+0C8h+var_98], ebx
0x1800a72ae  test    ebx, ebx
0x1800a72b0  jns     loc_18002E611
0x1800a72b6  jmp     loc_1800A7112
```
