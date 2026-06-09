# ReadSettingsCache

- ea: `0x1800f802c`
- end: `0x1800f82fc`
- name: `ReadSettingsCache`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a310`

## callees

- `0x1800f802c`
- `0x1800f8304`
- `0x18010401c`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800f826a`
- `ntdll!RtlInitUnicodeString` at `0x1800f826a`
- `ntdll!NtOpenKey` at `0x1800f80a7`
- `ntdll!NtOpenKey` at `0x1800f81e8`
- `ntdll!NtOpenKey` at `0x1800f8295`
- `ntdll!NtOpenKey` at `0x1800f80a7`
- `ntdll!NtOpenKey` at `0x1800f81e8`
- `ntdll!NtOpenKey` at `0x1800f8295`
- `ntdll!NtQueryValueKey` at `0x1800f8104`
- `ntdll!NtQueryValueKey` at `0x1800f816e`
- `ntdll!NtQueryValueKey` at `0x1800f8104`
- `ntdll!NtQueryValueKey` at `0x1800f816e`
- `ntdll!wcsncpy_s` at `0x1800f82cf`
- `ntdll!wcsncpy_s` at `0x1801a1cbb`
- `ntdll!wcsncpy_s` at `0x1801a1cf1`
- `ntdll!wcsncpy_s` at `0x1801a1d58`
- `ntdll!wcsncpy_s` at `0x1801a1d8e`
- `ntdll!wcsncpy_s` at `0x1801a1e10`
- `ntdll!wcsncpy_s` at `0x1801a1e77`
- `ntdll!wcsncpy_s` at `0x1800f82cf`
- `ntdll!wcsncpy_s` at `0x1801a1cbb`
- `ntdll!wcsncpy_s` at `0x1801a1cf1`
- `ntdll!wcsncpy_s` at `0x1801a1d58`
- `ntdll!wcsncpy_s` at `0x1801a1d8e`
- `ntdll!wcsncpy_s` at `0x1801a1e10`
- `ntdll!wcsncpy_s` at `0x1801a1e77`
- `ntdll!NtClose` at `0x1800f8218`
- `ntdll!NtClose` at `0x1800f8232`
- `ntdll!NtClose` at `0x1801a1daf`
- `ntdll!NtClose` at `0x1801a1e98`
- `ntdll!NtClose` at `0x1800f8218`
- `ntdll!NtClose` at `0x1800f8232`
- `ntdll!NtClose` at `0x1801a1daf`
- `ntdll!NtClose` at `0x1801a1e98`

## pseudocode

```c
int __fastcall ReadSettingsCache(wchar_t *a1, void *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  wchar_t v5; // ax
  const WCHAR *v6; // rdx
  errno_t v7; // eax
  rsize_t v8; // rcx
  errno_t v9; // eax
  rsize_t v10; // rcx
  int StringValue; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v14; // [rsp+38h] [rbp-C8h]
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+94h] [rbp-6Ch]
  wchar_t Source[90]; // [rsp+9Ch] [rbp-64h] BYREF

  ObjectAttributes.RootDirectory = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  KeyHandle = 0;
  Handle = 0;
  v14 = 0;
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&ExplicitSettingsKey;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(v3) = NtOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( (int)v3 >= 0 )
  {
    if ( NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&Currencies,
           KeyValuePartialInformation,
           KeyValueInformation,
           0xB6u,
           &ResultLength) >= 0 )
    {
      v14 = Source;
      if ( v20 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
      {
        ResultLength = ((ResultLength - 12) >> 1) - 1;
        if ( !Source[ResultLength] && ResultLength >= 3 && !wcsncpy_s(a1 + 622, 4u, Source, 3u) )
          a1[621] = 3;
      }
    }
    if ( NtQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&Calendar,
           KeyValuePartialInformation,
           KeyValueInformation,
           0xB6u,
           &ResultLength) >= 0 )
    {
      v14 = Source;
      if ( v20 == 1 && (ResultLength & 1) == 0 && ResultLength > 0xE )
      {
        v4 = ((ResultLength - 12) >> 1) - 1;
        ResultLength = v4;
        if ( (unsigned int)v4 >= 4 && !Source[v4] )
        {
          v5 = CalendarIdFromString(Source);
          if ( v5 )
            a1[620] = v5;
        }
      }
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&GregorianKey;
    ObjectAttributes.RootDirectory = KeyHandle;
    if ( NtOpenKey(&Handle, 1u, &ObjectAttributes) >= 0 )
    {
      if ( (unsigned int)QueryStringValue(Handle, &ShortDate, KeyValueInformation) && ResultLength - 2 <= 0x4D )
      {
        v7 = wcsncpy_s(a1 + 627, 0x50u, v14, ResultLength);
        v8 = ResultLength;
        if ( !v7 )
          a1[626] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 352, 0x50u, v14, v8) )
          a1[351] = ResultLength;
      }
      if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation) && ResultLength - 3 <= 0x4C )
      {
        v9 = wcsncpy_s(a1 + 708, 0x50u, v14, ResultLength);
        v10 = ResultLength;
        if ( !v9 )
          a1[707] = ResultLength;
        if ( a1[620] == 1 && !wcsncpy_s(a1 + 514, 0x50u, v14, v10) )
          a1[513] = ResultLength;
      }
      NtClose(Handle);
      Handle = 0;
    }
    v3 = a1[620];
    if ( (_WORD)v3 != 1 )
    {
      if ( (unsigned int)v3 >= 0x18 )
      {
        v6 = &word_18029DECC;
      }
      else
      {
        _mm_lfence();
        v6 = (const WCHAR *)*((_QWORD *)&CalendarNames + v3);
      }
      if ( *v6 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v6);
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = KeyHandle;
        LODWORD(v3) = NtOpenKey(&Handle, 1u, &ObjectAttributes);
        if ( (int)v3 >= 0 )
        {
          StringValue = QueryStringValue(Handle, &ShortDate, KeyValueInformation);
          if ( StringValue && ResultLength - 2 <= 0x4D && !wcsncpy_s(a1 + 352, 0x50u, v14, ResultLength) )
            a1[351] = ResultLength;
          if ( (unsigned int)QueryStringValue(Handle, &LongDate, KeyValueInformation)
            && ResultLength - 3 <= 0x4C
            && !wcsncpy_s(a1 + 514, 0x50u, v14, ResultLength) )
          {
            a1[513] = ResultLength;
          }
          LODWORD(v3) = NtClose(Handle);
          Handle = 0;
        }
      }
    }
    if ( KeyHandle )
      LODWORD(v3) = NtClose(KeyHandle);
    if ( Handle )
      LODWORD(v3) = NtClose(Handle);
  }
  return v3;
}

```

## disassembly

```asm
0x1800f802c  mov     [rsp-8+arg_10], rbx
0x1800f8031  mov     [rsp-8+arg_18], rsi
0x1800f8036  push    rbp
0x1800f8037  push    rdi
0x1800f8038  push    r14
0x1800f803a  lea     rbp, [rsp-60h]
0x1800f803f  sub     rsp, 160h
0x1800f8046  mov     rax, cs:__security_cookie
0x1800f804d  xor     rax, rsp
0x1800f8050  mov     [rbp+70h+var_20], rax
0x1800f8054  xor     edi, edi
0x1800f8056  mov     [rsp+170h+ObjectAttributes.RootDirectory], rdx
0x1800f805b  mov     rbx, rcx
0x1800f805e  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800f8067  lea     rax, ExplicitSettingsKey
0x1800f806e  mov     qword ptr [rsp+170h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f8077  xorps   xmm0, xmm0
0x1800f807a  mov     [rsp+170h+KeyHandle], rdi
0x1800f807f  lea     esi, [rdi+1]
0x1800f8082  mov     [rsp+170h+Handle], rdi
0x1800f8087  mov     edx, esi; DesiredAccess
0x1800f8089  mov     [rsp+170h+var_138], rdi
0x1800f808e  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800f8093  mov     [rsp+170h+var_140], edi
0x1800f8097  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800f809c  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800f80a1  movdqu  xmmword ptr [rsp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f80a7  call    cs:__imp_NtOpenKey
0x1800f80ae  nop     dword ptr [rax+rax+00h]
0x1800f80b3  test    eax, eax
0x1800f80b5  jns     short loc_1800F80DC
0x1800f80b7  mov     rcx, [rbp+70h+var_20]
0x1800f80bb  xor     rcx, rsp; StackCookie
0x1800f80be  call    __security_check_cookie
0x1800f80c3  lea     r11, [rsp+170h+var_10]
0x1800f80cb  mov     rbx, [r11+30h]
0x1800f80cf  mov     rsi, [r11+38h]
0x1800f80d3  mov     rsp, r11
0x1800f80d6  pop     r14
0x1800f80d8  pop     rdi
0x1800f80d9  pop     rbp
0x1800f80da  retn
0x1800f80dc  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800f80e1  lea     rax, [rsp+170h+var_140]
0x1800f80e6  mov     [rsp+170h+ResultLength], rax; ResultLength
0x1800f80eb  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x1800f80ef  mov     r8d, 2; KeyValueInformationClass
0x1800f80f5  mov     [rsp+170h+Length], 0B6h; Length
0x1800f80fd  lea     rdx, Currencies; ValueName
0x1800f8104  call    cs:__imp_NtQueryValueKey
0x1800f810b  nop     dword ptr [rax+rax+00h]
0x1800f8110  test    eax, eax
0x1800f8112  js      short loc_1800F8146
0x1800f8114  lea     rax, [rbp+70h+Source]
0x1800f8118  mov     [rsp+170h+var_138], rax
0x1800f811d  cmp     [rbp+70h+var_DC], esi
0x1800f8120  jnz     short loc_1800F8146
0x1800f8122  mov     ecx, [rsp+170h+var_140]
0x1800f8126  test    sil, cl
0x1800f8129  jnz     short loc_1800F8146
0x1800f812b  cmp     ecx, 0Eh
0x1800f812e  jbe     short loc_1800F8146
0x1800f8130  add     ecx, 0FFFFFFF4h
0x1800f8133  shr     ecx, 1
0x1800f8135  sub     ecx, esi
0x1800f8137  mov     [rsp+170h+var_140], ecx
0x1800f813b  cmp     [rbp+rcx*2+70h+Source], di
0x1800f8140  jz      loc_1800F82AE
0x1800f8146  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800f814b  lea     rax, [rsp+170h+var_140]
0x1800f8150  mov     [rsp+170h+ResultLength], rax; ResultLength
0x1800f8155  lea     r9, [rbp+70h+KeyValueInformation]; KeyValueInformation
0x1800f8159  mov     r8d, 2; KeyValueInformationClass
0x1800f815f  mov     [rsp+170h+Length], 0B6h; Length
0x1800f8167  lea     rdx, Calendar; ValueName
0x1800f816e  call    cs:__imp_NtQueryValueKey
0x1800f8175  nop     dword ptr [rax+rax+00h]
0x1800f817a  test    eax, eax
0x1800f817c  js      short loc_1800F81C6
0x1800f817e  lea     rax, [rbp+70h+Source]
0x1800f8182  mov     [rsp+170h+var_138], rax
0x1800f8187  cmp     [rbp+70h+var_DC], esi
0x1800f818a  jnz     short loc_1800F81C6
0x1800f818c  mov     ecx, [rsp+170h+var_140]
0x1800f8190  test    sil, cl
0x1800f8193  jnz     short loc_1800F81C6
0x1800f8195  cmp     ecx, 0Eh
0x1800f8198  jbe     short loc_1800F81C6
0x1800f819a  add     ecx, 0FFFFFFF4h
0x1800f819d  shr     ecx, 1
0x1800f819f  sub     ecx, esi
0x1800f81a1  mov     [rsp+170h+var_140], ecx
0x1800f81a5  cmp     ecx, 4
0x1800f81a8  jb      short loc_1800F81C6
0x1800f81aa  cmp     [rbp+rcx*2+70h+Source], di
0x1800f81af  jnz     short loc_1800F81C6
0x1800f81b1  lea     rcx, [rbp+70h+Source]; String2
0x1800f81b5  call    CalendarIdFromString
0x1800f81ba  cmp     ax, si
0x1800f81bd  jb      short loc_1800F81C6
0x1800f81bf  mov     [rbx+4D8h], ax
0x1800f81c6  lea     rax, GregorianKey
0x1800f81cd  mov     edx, esi; DesiredAccess
0x1800f81cf  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800f81d4  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800f81d9  mov     rax, [rsp+170h+KeyHandle]
0x1800f81de  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1800f81e3  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1800f81e8  call    cs:__imp_NtOpenKey
0x1800f81ef  nop     dword ptr [rax+rax+00h]
0x1800f81f4  mov     r14d, 50h ; 'P'
0x1800f81fa  test    eax, eax
0x1800f81fc  jns     loc_1801A1C70
0x1800f8202  movzx   eax, word ptr [rbx+4D8h]
0x1800f8209  cmp     ax, si
0x1800f820c  jnz     short loc_1800F8243
0x1800f820e  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x1800f8213  test    rcx, rcx
0x1800f8216  jz      short loc_1800F8224
0x1800f8218  call    cs:__imp_NtClose
0x1800f821f  nop     dword ptr [rax+rax+00h]
0x1800f8224  mov     rcx, [rsp+170h+Handle]; Handle
0x1800f8229  test    rcx, rcx
0x1800f822c  jz      loc_1800F80B7
0x1800f8232  call    cs:__imp_NtClose
0x1800f8239  nop     dword ptr [rax+rax+00h]
0x1800f823e  jmp     loc_1800F80B7
0x1800f8243  cmp     eax, 18h
0x1800f8246  jnb     loc_1800F82F0
0x1800f824c  lfence
0x1800f824f  lea     rdx, CalendarNames
0x1800f8256  mov     rdx, [rdx+rax*8]; SourceString
0x1800f825a  cmp     [rdx], di
0x1800f825d  jz      short loc_1800F820E
0x1800f825f  xorps   xmm0, xmm0
0x1800f8262  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800f8266  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1800f826a  call    cs:__imp_RtlInitUnicodeString
0x1800f8271  nop     dword ptr [rax+rax+00h]
0x1800f8276  lea     rax, [rbp+70h+DestinationString]
0x1800f827a  mov     edx, esi; DesiredAccess
0x1800f827c  mov     [rsp+170h+ObjectAttributes.ObjectName], rax
0x1800f8281  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800f8286  mov     rax, [rsp+170h+KeyHandle]
0x1800f828b  lea     rcx, [rsp+170h+Handle]; KeyHandle
0x1800f8290  mov     [rsp+170h+ObjectAttributes.RootDirectory], rax
0x1800f8295  call    cs:__imp_NtOpenKey
0x1800f829c  nop     dword ptr [rax+rax+00h]
0x1800f82a1  test    eax, eax
0x1800f82a3  js      loc_1800F820E
0x1800f82a9  jmp     loc_1801A1DC5
0x1800f82ae  mov     r14d, 3
0x1800f82b4  cmp     ecx, r14d
0x1800f82b7  jb      loc_1800F8146
0x1800f82bd  lea     rcx, [rbx+4DCh]; Destination
0x1800f82c4  mov     r9d, r14d; MaxCount
0x1800f82c7  lea     r8, [rbp+70h+Source]; Source
0x1800f82cb  lea     edx, [r14+1]; SizeInWords
0x1800f82cf  call    cs:__imp_wcsncpy_s
0x1800f82d6  nop     dword ptr [rax+rax+00h]
0x1800f82db  test    eax, eax
0x1800f82dd  jnz     loc_1800F8146
0x1800f82e3  mov     [rbx+4DAh], r14w
0x1800f82eb  jmp     loc_1800F8146
0x1800f82f0  lea     rdx, word_18029DECC
0x1800f82f7  jmp     loc_1800F825A
0x1801a1c70  mov     rcx, [rsp+170h+Handle]
0x1801a1c75  lea     rax, [rsp+170h+var_140]
0x1801a1c7a  mov     [rsp+170h+ResultLength], rax
0x1801a1c7f  lea     r8, [rbp+70h+KeyValueInformation]
0x1801a1c83  lea     rax, [rsp+170h+var_138]
0x1801a1c88  lea     rdx, ShortDate
0x1801a1c8f  mov     qword ptr [rsp+170h+Length], rax
0x1801a1c94  call    QueryStringValue
0x1801a1c99  test    eax, eax
0x1801a1c9b  jz      short loc_1801A1D0D
0x1801a1c9d  mov     ecx, [rsp+170h+var_140]
0x1801a1ca1  lea     eax, [rcx-2]
0x1801a1ca4  cmp     eax, 4Dh ; 'M'
0x1801a1ca7  ja      short loc_1801A1D0D
0x1801a1ca9  mov     r8, [rsp+170h+var_138]; Source
0x1801a1cae  mov     r9d, ecx; MaxCount
0x1801a1cb1  lea     rcx, [rbx+4E6h]; Destination
0x1801a1cb8  mov     rdx, r14; SizeInWords
0x1801a1cbb  call    cs:__imp_wcsncpy_s
0x1801a1cc2  nop     dword ptr [rax+rax+00h]
0x1801a1cc7  mov     ecx, [rsp+170h+var_140]
0x1801a1ccb  test    eax, eax
0x1801a1ccd  jnz     short loc_1801A1CD6
0x1801a1ccf  mov     [rbx+4E4h], cx
0x1801a1cd6  cmp     [rbx+4D8h], si
0x1801a1cdd  jnz     short loc_1801A1D0D
0x1801a1cdf  mov     r8, [rsp+170h+var_138]; Source
0x1801a1ce4  mov     r9, rcx; MaxCount
0x1801a1ce7  lea     rcx, [rbx+2C0h]; Destination
0x1801a1cee  mov     rdx, r14; SizeInWords
0x1801a1cf1  call    cs:__imp_wcsncpy_s
0x1801a1cf8  nop     dword ptr [rax+rax+00h]
0x1801a1cfd  test    eax, eax
0x1801a1cff  jnz     short loc_1801A1D0D
0x1801a1d01  movzx   eax, word ptr [rsp+170h+var_140]
0x1801a1d06  mov     [rbx+2BEh], ax
0x1801a1d0d  mov     rcx, [rsp+170h+Handle]
0x1801a1d12  lea     rax, [rsp+170h+var_140]
0x1801a1d17  mov     [rsp+170h+ResultLength], rax
0x1801a1d1c  lea     r8, [rbp+70h+KeyValueInformation]
0x1801a1d20  lea     rax, [rsp+170h+var_138]
0x1801a1d25  lea     rdx, LongDate
0x1801a1d2c  mov     qword ptr [rsp+170h+Length], rax
0x1801a1d31  call    QueryStringValue
0x1801a1d36  test    eax, eax
0x1801a1d38  jz      short loc_1801A1DAA
0x1801a1d3a  mov     ecx, [rsp+170h+var_140]
0x1801a1d3e  lea     eax, [rcx-3]
0x1801a1d41  cmp     eax, 4Ch ; 'L'
0x1801a1d44  ja      short loc_1801A1DAA
0x1801a1d46  mov     r8, [rsp+170h+var_138]; Source
0x1801a1d4b  mov     r9d, ecx; MaxCount
0x1801a1d4e  lea     rcx, [rbx+588h]; Destination
0x1801a1d55  mov     rdx, r14; SizeInWords
0x1801a1d58  call    cs:__imp_wcsncpy_s
0x1801a1d5f  nop     dword ptr [rax+rax+00h]
0x1801a1d64  mov     ecx, [rsp+170h+var_140]
0x1801a1d68  test    eax, eax
0x1801a1d6a  jnz     short loc_1801A1D73
0x1801a1d6c  mov     [rbx+586h], cx
0x1801a1d73  cmp     [rbx+4D8h], si
0x1801a1d7a  jnz     short loc_1801A1DAA
0x1801a1d7c  mov     r8, [rsp+170h+var_138]; Source
0x1801a1d81  mov     r9, rcx; MaxCount
0x1801a1d84  lea     rcx, [rbx+404h]; Destination
0x1801a1d8b  mov     rdx, r14; SizeInWords
0x1801a1d8e  call    cs:__imp_wcsncpy_s
0x1801a1d95  nop     dword ptr [rax+rax+00h]
0x1801a1d9a  test    eax, eax
0x1801a1d9c  jnz     short loc_1801A1DAA
0x1801a1d9e  movzx   eax, word ptr [rsp+170h+var_140]
0x1801a1da3  mov     [rbx+402h], ax
0x1801a1daa  mov     rcx, [rsp+170h+Handle]; Handle
0x1801a1daf  call    cs:__imp_NtClose
0x1801a1db6  nop     dword ptr [rax+rax+00h]
0x1801a1dbb  mov     [rsp+170h+Handle], rdi
0x1801a1dc0  jmp     loc_1800F8202
0x1801a1dc5  mov     rcx, [rsp+170h+Handle]
0x1801a1dca  lea     rax, [rsp+170h+var_140]
0x1801a1dcf  mov     [rsp+170h+ResultLength], rax
0x1801a1dd4  lea     r8, [rbp+70h+KeyValueInformation]
0x1801a1dd8  lea     rax, [rsp+170h+var_138]
0x1801a1ddd  lea     rdx, ShortDate
0x1801a1de4  mov     qword ptr [rsp+170h+Length], rax
0x1801a1de9  call    QueryStringValue
0x1801a1dee  test    eax, eax
0x1801a1df0  jz      short loc_1801A1E2C
0x1801a1df2  mov     ecx, [rsp+170h+var_140]
0x1801a1df6  lea     eax, [rcx-2]
0x1801a1df9  cmp     eax, 4Dh ; 'M'
0x1801a1dfc  ja      short loc_1801A1E2C
0x1801a1dfe  mov     r8, [rsp+170h+var_138]; Source
0x1801a1e03  mov     r9d, ecx; MaxCount
0x1801a1e06  lea     rcx, [rbx+2C0h]; Destination
0x1801a1e0d  mov     rdx, r14; SizeInWords
0x1801a1e10  call    cs:__imp_wcsncpy_s
0x1801a1e17  nop     dword ptr [rax+rax+00h]
0x1801a1e1c  test    eax, eax
0x1801a1e1e  jnz     short loc_1801A1E2C
0x1801a1e20  movzx   eax, word ptr [rsp+170h+var_140]
0x1801a1e25  mov     [rbx+2BEh], ax
0x1801a1e2c  mov     rcx, [rsp+170h+Handle]
0x1801a1e31  lea     rax, [rsp+170h+var_140]
0x1801a1e36  mov     [rsp+170h+ResultLength], rax
0x1801a1e3b  lea     r8, [rbp+70h+KeyValueInformation]
0x1801a1e3f  lea     rax, [rsp+170h+var_138]
0x1801a1e44  lea     rdx, LongDate
0x1801a1e4b  mov     qword ptr [rsp+170h+Length], rax
0x1801a1e50  call    QueryStringValue
0x1801a1e55  test    eax, eax
0x1801a1e57  jz      short loc_1801A1E93
0x1801a1e59  mov     ecx, [rsp+170h+var_140]
0x1801a1e5d  lea     eax, [rcx-3]
0x1801a1e60  cmp     eax, 4Ch ; 'L'
0x1801a1e63  ja      short loc_1801A1E93
0x1801a1e65  mov     r8, [rsp+170h+var_138]; Source
0x1801a1e6a  mov     r9d, ecx; MaxCount
0x1801a1e6d  lea     rcx, [rbx+404h]; Destination
0x1801a1e74  mov     rdx, r14; SizeInWords
0x1801a1e77  call    cs:__imp_wcsncpy_s
0x1801a1e7e  nop     dword ptr [rax+rax+00h]
0x1801a1e83  test    eax, eax
0x1801a1e85  jnz     short loc_1801A1E93
0x1801a1e87  movzx   eax, word ptr [rsp+170h+var_140]
0x1801a1e8c  mov     [rbx+402h], ax
0x1801a1e93  mov     rcx, [rsp+170h+Handle]; Handle
0x1801a1e98  call    cs:__imp_NtClose
0x1801a1e9f  nop     dword ptr [rax+rax+00h]
0x1801a1ea4  mov     [rsp+170h+Handle], rdi
0x1801a1ea9  jmp     loc_1800F820E
```
