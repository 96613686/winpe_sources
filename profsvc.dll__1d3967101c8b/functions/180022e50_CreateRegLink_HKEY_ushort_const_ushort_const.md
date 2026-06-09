# CreateRegLink(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180022e50`
- end: `0x180023040`
- name: `?CreateRegLink@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `496`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022b60`

## callees

- `0x180022e50`
- `0x18002aef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002302b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023018`
- `ntdll!NtOpenKey` at `0x180022ee6`
- `ntdll!NtOpenKey` at `0x180022ee6`
- `ntdll!RtlInitUnicodeString` at `0x180022e7d`
- `ntdll!RtlInitUnicodeString` at `0x180022e91`
- `ntdll!RtlInitUnicodeString` at `0x180022ea9`
- `ntdll!RtlInitUnicodeString` at `0x180022e7d`
- `ntdll!RtlInitUnicodeString` at `0x180022e91`
- `ntdll!RtlInitUnicodeString` at `0x180022ea9`
- `ntdll!NtClose` at `0x180022f83`
- `ntdll!NtClose` at `0x180022fba`
- `ntdll!NtClose` at `0x180022fd7`
- `ntdll!NtClose` at `0x180023004`
- `ntdll!NtClose` at `0x180023023`
- `ntdll!NtClose` at `0x180022f83`
- `ntdll!NtClose` at `0x180022fba`
- `ntdll!NtClose` at `0x180022fd7`
- `ntdll!NtClose` at `0x180023004`
- `ntdll!NtClose` at `0x180023023`
- `ntdll!NtSetValueKey` at `0x180022f56`
- `ntdll!NtSetValueKey` at `0x180022f56`
- `ntdll!NtCreateKey` at `0x180022f2a`
- `ntdll!NtCreateKey` at `0x180022f2a`

## string_xrefs

- `0x180022f64`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180022f9b`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180022fe5`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180022e68`: `SymbolicLinkValue`

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
0x180022e50  mov     [rsp-8+KeyHandle], rdx
0x180022e55  push    rbp
0x180022e56  push    rbx
0x180022e57  push    rsi
0x180022e58  push    rdi
0x180022e59  lea     rbp, [rsp-3Fh]
0x180022e5e  sub     rsp, 0A8h
0x180022e65  mov     rdi, rcx
0x180022e68  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x180022e6f  xorps   xmm0, xmm0
0x180022e72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180022e76  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180022e7a  mov     rbx, r8
0x180022e7d  call    cs:__imp_RtlInitUnicodeString
0x180022e83  xorps   xmm0, xmm0
0x180022e86  lea     rcx, [rbp+57h+var_80]; DestinationString
0x180022e8a  mov     rdx, rbx; SourceString
0x180022e8d  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x180022e91  call    cs:__imp_RtlInitUnicodeString
0x180022e97  xorps   xmm0, xmm0
0x180022e9a  lea     rdx, aSoftwareClasse; "Software\\Classes\\"
0x180022ea1  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180022ea5  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180022ea9  call    cs:__imp_RtlInitUnicodeString
0x180022eaf  lea     rax, [rbp+57h+var_70]
0x180022eb3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180022ebb  xorps   xmm0, xmm0
0x180022ebe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180022ec2  xor     esi, esi
0x180022ec4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 140h
0x180022ecc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022ed0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180022ed4  mov     edx, 2000000h; DesiredAccess
0x180022ed9  mov     [rbp+57h+KeyHandle], rsi
0x180022edd  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180022ee1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022ee6  call    cs:__imp_NtOpenKey
0x180022eec  cmp     eax, 0C0000034h
0x180022ef1  jnz     loc_180023036
0x180022ef7  mov     rbx, [rbp+57h+KeyHandle]
0x180022efb  test    rbx, rbx
0x180022efe  jnz     loc_180023018
0x180022f04  mov     [rsp+0C0h+Disposition], rsi; Disposition
0x180022f09  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022f0d  mov     [rsp+0C0h+CreateOptions], 3; CreateOptions
0x180022f15  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180022f19  xor     r9d, r9d; TitleIndex
0x180022f1c  mov     [rsp+0C0h+Class], rsi; int
0x180022f21  mov     edx, 22h ; '"'; DesiredAccess
0x180022f26  mov     [rbp+57h+KeyHandle], rsi
0x180022f2a  call    cs:__imp_NtCreateKey
0x180022f30  test    eax, eax
0x180022f32  js      short loc_180022F97
0x180022f34  movzx   eax, [rbp+57h+var_80.Length]
0x180022f38  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180022f3c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180022f40  mov     r9d, 6; Type
0x180022f46  mov     [rsp+0C0h+CreateOptions], eax; DataSize
0x180022f4a  xor     r8d, r8d; TitleIndex
0x180022f4d  mov     rax, [rbp+57h+var_80.Buffer]
0x180022f51  mov     [rsp+0C0h+Class], rax; int
0x180022f56  call    cs:__imp_NtSetValueKey
0x180022f5c  test    eax, eax
0x180022f5e  jns     short loc_180022FCE
0x180022f60  mov     rcx, [rbp+5Fh]; this
0x180022f64  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180022f6b  mov     r9d, eax; char *
0x180022f6e  mov     edx, 97h; void *
0x180022f73  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022f78  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180022f7c  mov     ebx, eax
0x180022f7e  test    rcx, rcx
0x180022f81  jz      short loc_180022F89
0x180022f83  call    cs:__imp_NtClose
0x180022f89  mov     eax, ebx
0x180022f8b  add     rsp, 0A8h
0x180022f92  pop     rdi
0x180022f93  pop     rsi
0x180022f94  pop     rbx
0x180022f95  pop     rbp
0x180022f96  retn
0x180022f97  mov     rcx, [rbp+5Fh]; this
0x180022f9b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180022fa2  mov     r9d, eax; char *
0x180022fa5  mov     edx, 88h; void *
0x180022faa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022faf  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180022fb3  mov     ebx, eax
0x180022fb5  test    rcx, rcx
0x180022fb8  jz      short loc_180022F89
0x180022fba  call    cs:__imp_NtClose
0x180022fc0  mov     eax, ebx
0x180022fc2  add     rsp, 0A8h
0x180022fc9  pop     rdi
0x180022fca  pop     rsi
0x180022fcb  pop     rbx
0x180022fcc  pop     rbp
0x180022fcd  retn
0x180022fce  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180022fd2  test    rcx, rcx
0x180022fd5  jz      short loc_180022FDD
0x180022fd7  call    cs:__imp_NtClose
0x180022fdd  xor     eax, eax
0x180022fdf  jmp     short loc_180022F8B
0x180022fe1  mov     rcx, [rbp+5Fh]; this
0x180022fe5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180022fec  mov     r9d, eax; char *
0x180022fef  mov     edx, 8Ch; void *
0x180022ff4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180022ff9  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180022ffd  mov     ebx, eax
0x180022fff  test    rcx, rcx
0x180023002  jz      short loc_180022F89
0x180023004  call    cs:__imp_NtClose
0x18002300a  mov     eax, ebx
0x18002300c  add     rsp, 0A8h
0x180023013  pop     rdi
0x180023014  pop     rsi
0x180023015  pop     rbx
0x180023016  pop     rbp
0x180023017  retn
0x180023018  call    cs:__imp_GetLastError
0x18002301e  mov     rcx, rbx; Handle
0x180023021  mov     edi, eax
0x180023023  call    cs:__imp_NtClose
0x180023029  mov     ecx, edi; dwErrCode
0x18002302b  call    cs:__imp_SetLastError
0x180023031  jmp     loc_180022F04
0x180023036  test    eax, eax
0x180023038  jns     loc_180022F34
0x18002303e  jmp     short loc_180022FE1
```
