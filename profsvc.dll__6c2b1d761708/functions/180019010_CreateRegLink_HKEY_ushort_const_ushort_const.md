# CreateRegLink(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180019010`
- end: `0x180019255`
- name: `?CreateRegLink@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `581`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800181c8`

## callees

- `0x180019010`
- `0x1800364c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001923a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001921b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001921b`
- `ntdll!NtOpenKey` at `0x1800190b8`
- `ntdll!NtOpenKey` at `0x1800190b8`
- `ntdll!RtlInitUnicodeString` at `0x18001903d`
- `ntdll!RtlInitUnicodeString` at `0x180019057`
- `ntdll!RtlInitUnicodeString` at `0x180019075`
- `ntdll!RtlInitUnicodeString` at `0x18001903d`
- `ntdll!RtlInitUnicodeString` at `0x180019057`
- `ntdll!RtlInitUnicodeString` at `0x180019075`
- `ntdll!NtClose` at `0x180019167`
- `ntdll!NtClose` at `0x1800191a5`
- `ntdll!NtClose` at `0x1800191c9`
- `ntdll!NtClose` at `0x180019200`
- `ntdll!NtClose` at `0x18001922c`
- `ntdll!NtClose` at `0x180019167`
- `ntdll!NtClose` at `0x1800191a5`
- `ntdll!NtClose` at `0x1800191c9`
- `ntdll!NtClose` at `0x180019200`
- `ntdll!NtClose` at `0x18001922c`
- `ntdll!NtSetValueKey` at `0x180019134`
- `ntdll!NtSetValueKey` at `0x180019134`
- `ntdll!NtCreateKey` at `0x180019102`
- `ntdll!NtCreateKey` at `0x180019102`

## string_xrefs

- `0x180019148`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180019186`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800191dd`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180019028`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall CreateRegLink(HKEY a1, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  NTSTATUS v5; // eax
  void *v6; // rbx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  int v11; // eax
  void *v12; // rcx
  int v13; // eax
  DWORD LastError; // edi
  int Class; // [rsp+20h] [rbp-49h]
  int Classa; // [rsp+20h] [rbp-49h]
  int Classb; // [rsp+20h] [rbp-49h]
  struct _UNICODE_STRING v18; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING v19; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  void *KeyHandle; // [rsp+D8h] [rbp+6Fh] BYREF

  KeyHandle = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SymbolicLinkValue");
  v18 = 0;
  RtlInitUnicodeString(&v18, a3);
  v19 = 0;
  RtlInitUnicodeString(&v19, L"Software\\Classes\\");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v19;
  *(_QWORD *)&ObjectAttributes.Attributes = 320;
  ObjectAttributes.RootDirectory = a1;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
  if ( v5 == -1073741772 )
  {
    v6 = KeyHandle;
    if ( KeyHandle )
    {
      LastError = GetLastError();
      NtClose(v6);
      SetLastError(LastError);
    }
    KeyHandle = 0;
    v7 = NtCreateKey(&KeyHandle, 0x22u, &ObjectAttributes, 0, 0, 3u, 0);
    if ( v7 >= 0 )
      goto LABEL_5;
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v7,
            Classa);
    v12 = KeyHandle;
    v9 = v11;
    if ( KeyHandle )
    {
LABEL_10:
      NtClose(v12);
      return v9;
    }
    return v9;
  }
  if ( v5 < 0 )
  {
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x8C,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v5,
            Class);
    v12 = KeyHandle;
    v9 = v13;
    if ( KeyHandle )
      goto LABEL_10;
    return v9;
  }
LABEL_5:
  v8 = NtSetValueKey(KeyHandle, &DestinationString, 0, 6u, v18.Buffer, v18.Length);
  if ( v8 < 0 )
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x97,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
           (const char *)(unsigned int)v8,
           Classb);
    if ( KeyHandle )
      NtClose(KeyHandle);
    return v9;
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return 0;
}

```

## disassembly

```asm
0x180019010  mov     [rsp-8+KeyHandle], rdx
0x180019015  push    rbp
0x180019016  push    rbx
0x180019017  push    rsi
0x180019018  push    rdi
0x180019019  lea     rbp, [rsp-3Fh]
0x18001901e  sub     rsp, 0A8h
0x180019025  mov     rdi, rcx
0x180019028  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x18001902f  xorps   xmm0, xmm0
0x180019032  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019036  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001903a  mov     rbx, r8
0x18001903d  call    cs:__imp_RtlInitUnicodeString
0x180019044  nop     dword ptr [rax+rax+00h]
0x180019049  xorps   xmm0, xmm0
0x18001904c  lea     rcx, [rbp+57h+var_80]; DestinationString
0x180019050  mov     rdx, rbx; SourceString
0x180019053  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x180019057  call    cs:__imp_RtlInitUnicodeString
0x18001905e  nop     dword ptr [rax+rax+00h]
0x180019063  xorps   xmm0, xmm0
0x180019066  lea     rdx, SourceString; "Software\\Classes\\"
0x18001906d  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180019071  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180019075  call    cs:__imp_RtlInitUnicodeString
0x18001907c  nop     dword ptr [rax+rax+00h]
0x180019081  lea     rax, [rbp+57h+var_70]
0x180019085  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001908d  xorps   xmm0, xmm0
0x180019090  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180019094  xor     esi, esi
0x180019096  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 140h
0x18001909e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800190a2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x1800190a6  mov     edx, 2000000h; DesiredAccess
0x1800190ab  mov     [rbp+57h+KeyHandle], rsi
0x1800190af  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800190b3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800190b8  call    cs:__imp_NtOpenKey
0x1800190bf  nop     dword ptr [rax+rax+00h]
0x1800190c4  cmp     eax, 0C0000034h
0x1800190c9  jnz     loc_18001924B
0x1800190cf  mov     rbx, [rbp+57h+KeyHandle]
0x1800190d3  test    rbx, rbx
0x1800190d6  jnz     loc_18001921B
0x1800190dc  mov     [rsp+0C0h+Disposition], rsi; Disposition
0x1800190e1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800190e5  mov     [rsp+0C0h+CreateOptions], 3; CreateOptions
0x1800190ed  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800190f1  xor     r9d, r9d; TitleIndex
0x1800190f4  mov     [rsp+0C0h+Class], rsi; int
0x1800190f9  mov     edx, 22h ; '"'; DesiredAccess
0x1800190fe  mov     [rbp+57h+KeyHandle], rsi
0x180019102  call    cs:__imp_NtCreateKey
0x180019109  nop     dword ptr [rax+rax+00h]
0x18001910e  test    eax, eax
0x180019110  js      short loc_180019182
0x180019112  movzx   eax, [rbp+57h+var_80.Length]
0x180019116  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18001911a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001911e  mov     r9d, 6; Type
0x180019124  mov     [rsp+0C0h+CreateOptions], eax; DataSize
0x180019128  xor     r8d, r8d; TitleIndex
0x18001912b  mov     rax, [rbp+57h+var_80.Buffer]
0x18001912f  mov     [rsp+0C0h+Class], rax; int
0x180019134  call    cs:__imp_NtSetValueKey
0x18001913b  nop     dword ptr [rax+rax+00h]
0x180019140  test    eax, eax
0x180019142  jns     short loc_1800191C0
0x180019144  mov     rcx, [rbp+5Fh]; this
0x180019148  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001914f  mov     r9d, eax; char *
0x180019152  mov     edx, 97h; void *
0x180019157  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001915c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180019160  mov     ebx, eax
0x180019162  test    rcx, rcx
0x180019165  jz      short loc_180019173
0x180019167  call    cs:__imp_NtClose
0x18001916e  nop     dword ptr [rax+rax+00h]
0x180019173  mov     eax, ebx
0x180019175  add     rsp, 0A8h
0x18001917c  pop     rdi
0x18001917d  pop     rsi
0x18001917e  pop     rbx
0x18001917f  pop     rbp
0x180019180  retn
0x180019182  mov     rcx, [rbp+5Fh]; this
0x180019186  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001918d  mov     r9d, eax; char *
0x180019190  mov     edx, 88h; void *
0x180019195  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001919a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001919e  mov     ebx, eax
0x1800191a0  test    rcx, rcx
0x1800191a3  jz      short loc_180019173
0x1800191a5  call    cs:__imp_NtClose
0x1800191ac  nop     dword ptr [rax+rax+00h]
0x1800191b1  mov     eax, ebx
0x1800191b3  add     rsp, 0A8h
0x1800191ba  pop     rdi
0x1800191bb  pop     rsi
0x1800191bc  pop     rbx
0x1800191bd  pop     rbp
0x1800191be  retn
0x1800191c0  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800191c4  test    rcx, rcx
0x1800191c7  jz      short loc_1800191D5
0x1800191c9  call    cs:__imp_NtClose
0x1800191d0  nop     dword ptr [rax+rax+00h]
0x1800191d5  xor     eax, eax
0x1800191d7  jmp     short loc_180019175
0x1800191d9  mov     rcx, [rbp+5Fh]; this
0x1800191dd  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800191e4  mov     r9d, eax; char *
0x1800191e7  mov     edx, 8Ch; void *
0x1800191ec  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800191f1  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800191f5  mov     ebx, eax
0x1800191f7  test    rcx, rcx
0x1800191fa  jz      loc_180019173
0x180019200  call    cs:__imp_NtClose
0x180019207  nop     dword ptr [rax+rax+00h]
0x18001920c  mov     eax, ebx
0x18001920e  add     rsp, 0A8h
0x180019215  pop     rdi
0x180019216  pop     rsi
0x180019217  pop     rbx
0x180019218  pop     rbp
0x180019219  retn
0x18001921b  call    cs:__imp_GetLastError
0x180019222  nop     dword ptr [rax+rax+00h]
0x180019227  mov     rcx, rbx; Handle
0x18001922a  mov     edi, eax
0x18001922c  call    cs:__imp_NtClose
0x180019233  nop     dword ptr [rax+rax+00h]
0x180019238  mov     ecx, edi; dwErrCode
0x18001923a  call    cs:__imp_SetLastError
0x180019241  nop     dword ptr [rax+rax+00h]
0x180019246  jmp     loc_1800190DC
0x18001924b  test    eax, eax
0x18001924d  jns     loc_180019112
0x180019253  jmp     short loc_1800191D9
```
