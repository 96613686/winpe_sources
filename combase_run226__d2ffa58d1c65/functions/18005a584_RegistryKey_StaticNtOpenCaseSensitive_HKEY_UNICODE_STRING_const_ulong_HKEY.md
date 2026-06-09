# RegistryKey::StaticNtOpenCaseSensitive(HKEY__ *,_UNICODE_STRING const &,ulong,HKEY__ * *)

- ea: `0x18005a584`
- end: `0x18005a878`
- name: `?StaticNtOpenCaseSensitive@RegistryKey@@CAJPEAUHKEY__@@AEBU_UNICODE_STRING@@KPEAPEAU2@@Z`
- size: `756`
- prototype: `HRESULT __fastcall(HKEY__ *hkeyParent, const _UNICODE_STRING *subKeyName, unsigned int desiredAccess, HKEY__ **phkey)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005a228`
- `0x18005a290`

## callees

- `0x18000833c`
- `0x18005a584`
- `0x18005a880`
- `0x18005b0a0`
- `0x1801999b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18005a5e6`
- `ntdll!NtOpenKey` at `0x18005a5e6`
- `ntdll!NtQueryKey` at `0x18005a63f`
- `ntdll!NtQueryKey` at `0x18005a6f5`
- `ntdll!NtQueryKey` at `0x18005a63f`
- `ntdll!NtQueryKey` at `0x18005a6f5`
- `ntdll!RtlNtStatusToDosError` at `0x18005a5ee`
- `ntdll!RtlNtStatusToDosError` at `0x18005a647`
- `ntdll!RtlNtStatusToDosError` at `0x18005a6fd`
- `ntdll!RtlNtStatusToDosError` at `0x18005a5ee`
- `ntdll!RtlNtStatusToDosError` at `0x18005a647`
- `ntdll!RtlNtStatusToDosError` at `0x18005a6fd`
- `ntdll!RtlEqualUnicodeString` at `0x18005a68c`
- `ntdll!RtlEqualUnicodeString` at `0x18005a68c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a6b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a6b9`

## string_xrefs

- `0x18005a750`: `StaticNtOpen`
- `0x18005a79f`: `StaticNtOpen`
- `0x18005a821`: `StaticNtOpen`
- `0x18005a603`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a75c`: `%hs failed with path:%.*ls %.*ls`
- `0x18005a7b4`: `%hs failed with path: %.*ls queryHr: %x`
- `0x18005a836`: `%hs failed with path: %.*ls`

## pseudocode

```c
__int64 __fastcall RegistryKey::StaticNtOpenCaseSensitive(
        HKEY__ *hkeyParent,
        _UNICODE_STRING *subKeyName,
        ACCESS_MASK desiredAccess,
        HKEY__ **phkey)
{
  NTSTATUS v7; // eax
  signed int v8; // eax
  HRESULT v9; // ebx
  void *v10; // rcx
  NTSTATUS v11; // eax
  signed int v12; // eax
  NTSTATUS v13; // eax
  signed int v14; // eax
  HRESULT v15; // edi
  int Length; // edx
  unsigned int cbBasicInformation; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING actualName; // [rsp+58h] [rbp-A8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 buffer[528]; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+2F8h] [rbp+1F8h]

  ObjectAttributes.RootDirectory = hkeyParent;
  ObjectAttributes.ObjectName = subKeyName;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenKey((PHANDLE)phkey, desiredAccess, &ObjectAttributes);
  v8 = RtlNtStatusToDosError(v7);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 != -2147024894 )
  {
    if ( v9 < 0 )
    {
      if ( hkeyParent )
      {
        cbBasicInformation = 516;
        v13 = NtQueryKey(hkeyParent, KeyNameInformation, buffer, 0x204u, &cbBasicInformation);
        v14 = RtlNtStatusToDosError(v13);
        v15 = v14;
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
        if ( v15 < 0 && v15 != -2147024662 && v15 != -2147024774 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0x7E1u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v15);
        Length = subKeyName->Length;
        if ( v15 < 0 )
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            0x214u,
            "onecore\\com\\combase\\inc\\RegistryKey.hpp",
            v9,
            "%hs failed with path: %.*ls queryHr: %x",
            "StaticNtOpen",
            Length,
            subKeyName->Buffer,
            v15);
        else
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            0x210u,
            "onecore\\com\\combase\\inc\\RegistryKey.hpp",
            v9,
            "%hs failed with path:%.*ls %.*ls",
            "StaticNtOpen",
            *(int *)buffer,
            (const wchar_t *)&buffer[4],
            Length,
            subKeyName->Buffer);
      }
      else
      {
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          0x200u,
          "onecore\\com\\combase\\inc\\RegistryKey.hpp",
          v9,
          "%hs failed with path: %.*ls",
          "StaticNtOpen",
          subKeyName->Length,
          subKeyName->Buffer);
      }
    }
    else
    {
      v10 = *phkey;
      cbBasicInformation = 528;
      v11 = NtQueryKey(v10, KeyBasicInformation, buffer, 0x210u, &cbBasicInformation);
      v12 = RtlNtStatusToDosError(v11);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( v9 < 0 )
      {
        if ( v9 != -2147024774 && v9 != -2147024662 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0x7E1u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v9);
        goto LABEL_10;
      }
      actualName.Length = *(_WORD *)&buffer[12];
      actualName.MaximumLength = *(_WORD *)&buffer[12];
      *(_DWORD *)(&actualName.MaximumLength + 1) = 0;
      actualName.Buffer = (wchar_t *)&buffer[16];
      if ( !RtlEqualUnicodeString(&actualName, subKeyName, 0) )
      {
        v9 = -2147024894;
        wil::details::in1diag3::Log_Hr(retaddr, 0x2ABu, "onecore\\com\\combase\\inc\\RegistryKey.hpp", -2147024894);
LABEL_10:
        RegCloseKey(*phkey);
        *phkey = 0;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005a584  push    rbp
0x18005a586  push    rbx
0x18005a587  push    rsi
0x18005a588  push    rdi
0x18005a589  push    r12
0x18005a58b  push    r14
0x18005a58d  lea     rbp, [rsp-1C8h]
0x18005a595  sub     rsp, 2C8h
0x18005a59c  mov     rax, cs:__security_cookie
0x18005a5a3  xor     rax, rsp
0x18005a5a6  mov     [rbp+1F0h+var_40], rax
0x18005a5ad  mov     eax, desiredAccess
0x18005a5b0  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], hkeyParent
0x18005a5b5  mov     rsi, subKeyName
0x18005a5b8  mov     [rsp+2F0h+ObjectAttributes.ObjectName], subKeyName
0x18005a5bd  mov     rdi, hkeyParent
0x18005a5c0  mov     qword ptr [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005a5c9  xorps   xmm0, xmm0
0x18005a5cc  mov     qword ptr [rbp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005a5d4  mov     edx, eax; DesiredAccess
0x18005a5d6  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005a5db  mov     hkeyParent, phkey; KeyHandle
0x18005a5de  mov     r14, phkey
0x18005a5e1  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a5e6  call    cs:__imp_NtOpenKey
0x18005a5ec  mov     ecx, eax; Status
0x18005a5ee  call    cs:__imp_RtlNtStatusToDosError
0x18005a5f4  mov     ebx, eax
0x18005a5f6  test    eax, eax
0x18005a5f8  jle     short loc_18005A603
0x18005a5fa  movzx   ebx, ax
0x18005a5fd  or      ebx, 80070000h
0x18005a603  lea     r12, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005a60a  cmp     ebx, 80070002h
0x18005a610  jz      loc_18005A76D
0x18005a616  test    ebx, ebx
0x18005a618  js      loc_18005A6CB
0x18005a61e  mov     hkeyParent, [r14]; KeyHandle
0x18005a621  lea     rax, [rsp+2F0h+cbBasicInformation]
0x18005a626  mov     r9d, 210h; Length
0x18005a62c  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x18005a631  lea     r8, [rbp+1F0h+buffer]; KeyInformation
0x18005a635  mov     [rsp+2F0h+cbBasicInformation], 210h
0x18005a63d  xor     edx, edx; KeyInformationClass
0x18005a63f  call    cs:__imp_NtQueryKey
0x18005a645  mov     ecx, eax; Status
0x18005a647  call    cs:__imp_RtlNtStatusToDosError
0x18005a64d  mov     ebx, eax
0x18005a64f  test    eax, eax
0x18005a651  jle     short loc_18005A65C
0x18005a653  movzx   ebx, ax
0x18005a656  or      ebx, 80070000h
0x18005a65c  test    ebx, ebx
0x18005a65e  js      loc_18005A84C
0x18005a664  movzx   eax, word ptr [rbp+1F0h+buffer+0Ch]
0x18005a668  lea     hkeyParent, [rsp+2F0h+actualName]; String1
0x18005a66d  mov     [rsp+2F0h+actualName.Length], ax
0x18005a672  xor     desiredAccess, desiredAccess; CaseInsensitive
0x18005a675  mov     [rsp+2F0h+actualName.MaximumLength], ax
0x18005a67a  mov     subKeyName, rsi; String2
0x18005a67d  xor     eax, eax
0x18005a67f  mov     dword ptr [rsp+2F0h+actualName+4], eax
0x18005a683  lea     rax, [rbp+1F0h+buffer+10h]
0x18005a687  mov     [rsp+2F0h+actualName.Buffer], rax
0x18005a68c  call    cs:__imp_RtlEqualUnicodeString
0x18005a692  test    al, al
0x18005a694  jnz     loc_18005A775
0x18005a69a  mov     hkeyParent, [rbp+1F8h]; callerReturnAddress
0x18005a6a1  mov     ebx, 80070002h
0x18005a6a6  mov     r9d, ebx; hr
0x18005a6a9  mov     r8, r12; fileName
0x18005a6ac  mov     edx, 2ABh; lineNumber
0x18005a6b1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18005a6b6  mov     hkeyParent, [r14]; hKey
0x18005a6b9  call    cs:__imp_RegCloseKey
0x18005a6bf  mov     qword ptr [r14], 0
0x18005a6c6  jmp     loc_18005A775
0x18005a6cb  test    rdi, rdi
0x18005a6ce  jz      loc_18005A808
0x18005a6d4  mov     r9d, 204h; Length
0x18005a6da  lea     rax, [rsp+2F0h+cbBasicInformation]
0x18005a6df  lea     r8, [rbp+1F0h+buffer]; KeyInformation
0x18005a6e3  mov     [rsp+2F0h+cbBasicInformation], r9d
0x18005a6e8  mov     edx, 3; KeyInformationClass
0x18005a6ed  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x18005a6f2  mov     hkeyParent, rdi; KeyHandle
0x18005a6f5  call    cs:__imp_NtQueryKey
0x18005a6fb  mov     ecx, eax; Status
0x18005a6fd  call    cs:__imp_RtlNtStatusToDosError
0x18005a703  mov     edi, eax
0x18005a705  test    eax, eax
0x18005a707  jle     short loc_18005A712
0x18005a709  movzx   edi, ax
0x18005a70c  or      edi, 80070000h
0x18005a712  test    edi, edi
0x18005a714  js      loc_18005A7C7
0x18005a71a  mov     rax, [rsi+8]
0x18005a71e  mov     r9d, ebx; hr
0x18005a721  movzx   edx, word ptr [rsi]
0x18005a724  mov     r8, r12; fileName
0x18005a727  mov     hkeyParent, [rbp+1F8h]; callerReturnAddress
0x18005a72e  test    edi, edi
0x18005a730  js      short loc_18005A796
0x18005a732  mov     [rsp+2F0h+var_2A8], rax
0x18005a737  lea     rax, [rbp+1F0h+buffer+4]
0x18005a73b  mov     [rsp+2F0h+var_2B0], edx
0x18005a73f  mov     edx, 210h; lineNumber
0x18005a744  mov     [rsp+2F0h+var_2B8], rax
0x18005a749  mov     eax, dword ptr [rbp+1F0h+buffer]
0x18005a74c  mov     [rsp+2F0h+var_2C0], eax
0x18005a750  lea     rax, callerFunction; "StaticNtOpen"
0x18005a757  mov     [rsp+2F0h+var_2C8], rax
0x18005a75c  lea     rax, aHsFailedWithPa; "%hs failed with path:%.*ls %.*ls"
0x18005a763  mov     [rsp+2F0h+ResultLength], rax; formatString
0x18005a768  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a76d  test    ebx, ebx
0x18005a76f  jns     loc_18005A61E
0x18005a775  mov     eax, ebx
0x18005a777  mov     hkeyParent, [rbp+1F0h+var_40]
0x18005a77e  xor     hkeyParent, rsp; StackCookie
0x18005a781  call    __security_check_cookie
0x18005a786  add     rsp, 2C8h
0x18005a78d  pop     r14
0x18005a78f  pop     r12
0x18005a791  pop     rdi
0x18005a792  pop     rsi
0x18005a793  pop     rbx
0x18005a794  pop     rbp
0x18005a795  retn
0x18005a796  mov     [rsp+2F0h+var_2B0], edi
0x18005a79a  mov     [rsp+2F0h+var_2B8], rax
0x18005a79f  lea     rax, callerFunction; "StaticNtOpen"
0x18005a7a6  mov     [rsp+2F0h+var_2C0], edx
0x18005a7aa  mov     edx, 214h; lineNumber
0x18005a7af  mov     [rsp+2F0h+var_2C8], rax
0x18005a7b4  lea     rax, aHsFailedWithPa_0; "%hs failed with path: %.*ls queryHr: %x"
0x18005a7bb  mov     [rsp+2F0h+ResultLength], rax; formatString
0x18005a7c0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a7c5  jmp     short loc_18005A76D
0x18005a7c7  cmp     edi, 800700EAh
0x18005a7cd  jz      loc_18005A71A
0x18005a7d3  cmp     edi, 8007007Ah
0x18005a7d9  jz      loc_18005A71A
0x18005a7df  mov     hkeyParent, [rbp+1F8h]; callerReturnAddress
0x18005a7e6  mov     r9d, edi; hr
0x18005a7e9  mov     r8, r12; fileName
0x18005a7ec  mov     edx, 7E1h; lineNumber
0x18005a7f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a7f6  jmp     loc_18005A71A
0x18005a7fb  test    ebx, ebx
0x18005a7fd  js      loc_18005A6B6
0x18005a803  jmp     loc_18005A664
0x18005a808  mov     rax, [rsi+8]
0x18005a80c  mov     r9d, ebx; hr
0x18005a80f  movzx   edx, word ptr [rsi]
0x18005a812  mov     r8, r12; fileName
0x18005a815  mov     hkeyParent, [rbp+1F8h]; callerReturnAddress
0x18005a81c  mov     [rsp+2F0h+var_2B8], rax
0x18005a821  lea     rax, callerFunction; "StaticNtOpen"
0x18005a828  mov     [rsp+2F0h+var_2C0], edx
0x18005a82c  mov     edx, 200h; lineNumber
0x18005a831  mov     [rsp+2F0h+var_2C8], rax
0x18005a836  lea     rax, aHsFailedWithPa_1; "%hs failed with path: %.*ls"
0x18005a83d  mov     [rsp+2F0h+ResultLength], rax; formatString
0x18005a842  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a847  jmp     loc_18005A76D
0x18005a84c  cmp     ebx, 8007007Ah
0x18005a852  jz      short loc_18005A7FB
0x18005a854  cmp     ebx, 800700EAh
0x18005a85a  jz      short loc_18005A7FB
0x18005a85c  mov     hkeyParent, [rbp+1F8h]; callerReturnAddress
0x18005a863  mov     r9d, ebx; hr
0x18005a866  mov     r8, r12; fileName
0x18005a869  mov     edx, 7E1h; lineNumber
0x18005a86e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a873  jmp     loc_18005A6B6
```
