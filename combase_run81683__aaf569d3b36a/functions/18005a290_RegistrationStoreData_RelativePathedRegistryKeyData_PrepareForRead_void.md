# RegistrationStoreData::RelativePathedRegistryKeyData::PrepareForRead(void)

- ea: `0x18005a290`
- end: `0x18005a57b`
- name: `?PrepareForRead@RelativePathedRegistryKeyData@RegistrationStoreData@@UEAAJXZ`
- size: `747`
- prototype: `HRESULT __fastcall(RegistrationStoreData::RelativePathedRegistryKeyData *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b800`

## callees

- `0x18000833c`
- `0x18005a290`
- `0x18005a584`
- `0x18005b0a0`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18005a374`
- `ntdll!NtOpenKey` at `0x18005a374`
- `ntdll!NtQueryKey` at `0x18005a3d0`
- `ntdll!NtQueryKey` at `0x18005a3d0`
- `ntdll!RtlNtStatusToDosError` at `0x18005a37c`
- `ntdll!RtlNtStatusToDosError` at `0x18005a3d8`
- `ntdll!RtlNtStatusToDosError` at `0x18005a37c`
- `ntdll!RtlNtStatusToDosError` at `0x18005a3d8`
- `ntdll!RtlInitUnicodeString` at `0x18005a339`
- `ntdll!RtlInitUnicodeString` at `0x18005a46e`
- `ntdll!RtlInitUnicodeString` at `0x18005a339`
- `ntdll!RtlInitUnicodeString` at `0x18005a46e`

## string_xrefs

- `0x18005a42a`: `StaticNtOpen`
- `0x18005a4c1`: `StaticNtOpen`
- `0x18005a524`: `StaticNtOpen`
- `0x18005a3f6`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a4a2`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a509`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a562`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005a436`: `%hs failed with path:%.*ls %.*ls`
- `0x18005a4d6`: `%hs failed with path: %.*ls queryHr: %x`
- `0x18005a539`: `%hs failed with path: %.*ls`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::RelativePathedRegistryKeyData::PrepareForRead(
        RegistrationStoreData::RelativePathedRegistryKeyData *this)
{
  RegistryKey *p_key; // rsi
  HRESULT v3; // ebx
  HSTRING__ *hstr; // rbx
  __int64 (*Key)(void); // rax
  void *v7; // rdi
  const wchar_t *v8; // rdx
  NTSTATUS v9; // eax
  signed int v10; // eax
  NTSTATUS v11; // eax
  signed int v12; // eax
  HRESULT v13; // edi
  HKEY__ *v14; // rdi
  const wchar_t *v15; // rdx
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ResultLength; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  int KeyInformation; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v20[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  void *retaddr; // [rsp+2E8h] [rbp+1E8h]

  p_key = &this->_key;
  if ( this->_key._hkey )
    return 0;
  v3 = this->_parent.ptr_->PrepareForRead(this->_parent.ptr_);
  if ( v3 >= 0 )
  {
    hstr = this->_name.hstr_;
    Key = (__int64 (*)(void))this->_parent.ptr_->Key;
    if ( (this->_options & 1) != 0 )
    {
      v14 = (HKEY__ *)Key();
      if ( hstr )
        v15 = (const wchar_t *)*((_QWORD *)hstr + 2);
      else
        v15 = g_WindowsEmptyStringInternal;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v15);
      return (unsigned int)RegistryKey::StaticNtOpenCaseSensitive(
                             v14,
                             &DestinationString,
                             0x20119u,
                             (HKEY__ **)&p_key->_hkey);
    }
    else
    {
      v7 = (void *)Key();
      if ( hstr )
        v8 = (const wchar_t *)*((_QWORD *)hstr + 2);
      else
        v8 = g_WindowsEmptyStringInternal;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v8);
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = v7;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = NtOpenKey((PHANDLE)&p_key->_hkey, 0x20119u, &ObjectAttributes);
      v10 = RtlNtStatusToDosError(v9);
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      if ( v3 != -2147024894 && v3 < 0 )
      {
        if ( v7 )
        {
          ResultLength = 516;
          v11 = NtQueryKey(v7, KeyNameInformation, &KeyInformation, 0x204u, &ResultLength);
          v12 = RtlNtStatusToDosError(v11);
          v13 = v12;
          if ( v12 > 0 )
            v13 = (unsigned __int16)v12 | 0x80070000;
          if ( v13 < 0 )
          {
            if ( v13 != -2147024662 && v13 != -2147024774 )
              wil::details::in1diag3::_Log_Hr(retaddr, 0x7E1u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v13);
            wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              0x214u,
              "onecore\\com\\combase\\inc\\RegistryKey.hpp",
              v3,
              "%hs failed with path: %.*ls queryHr: %x",
              "StaticNtOpen",
              DestinationString.Length,
              DestinationString.Buffer,
              v13);
          }
          else
          {
            wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              0x210u,
              "onecore\\com\\combase\\inc\\RegistryKey.hpp",
              v3,
              "%hs failed with path:%.*ls %.*ls",
              "StaticNtOpen",
              KeyInformation,
              v20,
              DestinationString.Length,
              DestinationString.Buffer);
          }
        }
        else
        {
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            0x200u,
            "onecore\\com\\combase\\inc\\RegistryKey.hpp",
            v3,
            "%hs failed with path: %.*ls",
            "StaticNtOpen",
            DestinationString.Length,
            DestinationString.Buffer);
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005a290  push    rbp
0x18005a292  push    rbx
0x18005a293  push    rsi
0x18005a294  push    rdi
0x18005a295  lea     rbp, [rsp-1C8h]
0x18005a29d  sub     rsp, 2C8h
0x18005a2a4  mov     rax, cs:__security_cookie
0x18005a2ab  xor     rax, rsp
0x18005a2ae  mov     [rbp+1E0h+var_30], rax
0x18005a2b5  lea     rsi, [this+10h]
0x18005a2b9  mov     rdi, this
0x18005a2bc  mov     rax, [rsi]
0x18005a2bf  test    rax, rax
0x18005a2c2  jnz     short loc_18005A2F7
0x18005a2c4  mov     this, [this+20h]
0x18005a2c8  mov     rax, [this]
0x18005a2cb  mov     rax, [rax+18h]
0x18005a2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2d4  mov     ebx, eax
0x18005a2d6  test    eax, eax
0x18005a2d8  jns     short loc_18005A2FB
0x18005a2da  mov     eax, ebx
0x18005a2dc  mov     this, [rbp+1E0h+var_30]
0x18005a2e3  xor     this, rsp; StackCookie
0x18005a2e6  call    __security_check_cookie
0x18005a2eb  add     rsp, 2C8h
0x18005a2f2  pop     rdi
0x18005a2f3  pop     rsi
0x18005a2f4  pop     rbx
0x18005a2f5  pop     rbp
0x18005a2f6  retn
0x18005a2f7  xor     eax, eax
0x18005a2f9  jmp     short loc_18005A2DC
0x18005a2fb  test    byte ptr [rdi+30h], 1
0x18005a2ff  mov     this, [rdi+20h]
0x18005a303  mov     rbx, [rdi+28h]
0x18005a307  mov     rax, [this]
0x18005a30a  mov     rax, [rax+0C8h]
0x18005a311  jnz     loc_18005A44C
0x18005a317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a31c  mov     rdi, rax
0x18005a31f  test    rbx, rbx
0x18005a322  jz      loc_18005A4EC
0x18005a328  mov     rdx, [rbx+10h]; SourceString
0x18005a32c  xorps   xmm0, xmm0
0x18005a32f  lea     this, [rsp+2E0h+DestinationString]; DestinationString
0x18005a334  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x18005a339  call    cs:__imp_RtlInitUnicodeString
0x18005a33f  lea     rax, [rsp+2E0h+DestinationString]
0x18005a344  mov     qword ptr [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18005a34d  xorps   xmm0, xmm0
0x18005a350  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x18005a355  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18005a35a  mov     qword ptr [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005a362  mov     edx, 20119h; DesiredAccess
0x18005a367  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x18005a36c  mov     this, rsi; KeyHandle
0x18005a36f  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a374  call    cs:__imp_NtOpenKey
0x18005a37a  mov     ecx, eax; Status
0x18005a37c  call    cs:__imp_RtlNtStatusToDosError
0x18005a382  mov     ebx, eax
0x18005a384  mov     esi, 80070000h
0x18005a389  test    eax, eax
0x18005a38b  jle     short loc_18005A392
0x18005a38d  movzx   ebx, ax
0x18005a390  or      ebx, esi
0x18005a392  cmp     ebx, 80070002h
0x18005a398  jz      loc_18005A2DA
0x18005a39e  test    ebx, ebx
0x18005a3a0  jns     loc_18005A2DA
0x18005a3a6  test    rdi, rdi
0x18005a3a9  jz      loc_18005A504
0x18005a3af  mov     r9d, 204h; Length
0x18005a3b5  lea     rax, [rsp+2E0h+var_280]
0x18005a3ba  lea     r8, [rbp+1E0h+KeyInformation]; KeyInformation
0x18005a3be  mov     [rsp+2E0h+var_280], r9d
0x18005a3c3  mov     edx, 3; KeyInformationClass
0x18005a3c8  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18005a3cd  mov     this, rdi; KeyHandle
0x18005a3d0  call    cs:__imp_NtQueryKey
0x18005a3d6  mov     ecx, eax; Status
0x18005a3d8  call    cs:__imp_RtlNtStatusToDosError
0x18005a3de  mov     edi, eax
0x18005a3e0  test    eax, eax
0x18005a3e2  jle     short loc_18005A3E9
0x18005a3e4  movzx   edi, ax
0x18005a3e7  or      edi, esi
0x18005a3e9  test    edi, edi
0x18005a3eb  js      loc_18005A491
0x18005a3f1  mov     rax, [rsp+2E0h+DestinationString.Buffer]
0x18005a3f6  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005a3fd  movzx   edx, [rsp+2E0h+DestinationString.Length]
0x18005a402  mov     r9d, ebx; hr
0x18005a405  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005a40c  mov     [rsp+2E0h+var_298], rax
0x18005a411  lea     rax, [rbp+1E0h+var_23C]
0x18005a415  mov     [rsp+2E0h+var_2A0], edx
0x18005a419  mov     edx, 210h; lineNumber
0x18005a41e  mov     [rsp+2E0h+var_2A8], rax
0x18005a423  mov     eax, [rbp+1E0h+KeyInformation]
0x18005a426  mov     [rsp+2E0h+var_2B0], eax
0x18005a42a  lea     rax, callerFunction; "StaticNtOpen"
0x18005a431  mov     [rsp+2E0h+var_2B8], rax
0x18005a436  lea     rax, aHsFailedWithPa; "%hs failed with path:%.*ls %.*ls"
0x18005a43d  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005a442  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a447  jmp     loc_18005A2DA
0x18005a44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a451  mov     rdi, rax
0x18005a454  test    rbx, rbx
0x18005a457  jz      loc_18005A4F8
0x18005a45d  mov     rdx, [rbx+10h]; SourceString
0x18005a461  xorps   xmm0, xmm0
0x18005a464  lea     this, [rsp+2E0h+DestinationString]; DestinationString
0x18005a469  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x18005a46e  call    cs:__imp_RtlInitUnicodeString
0x18005a474  mov     r9, rsi; phkey
0x18005a477  lea     rdx, [rsp+2E0h+DestinationString]; subKeyName
0x18005a47c  mov     r8d, 20119h; desiredAccess
0x18005a482  mov     this, rdi; hkeyParent
0x18005a485  call    ?StaticNtOpenCaseSensitive@RegistryKey@@CAJPEAUHKEY__@@AEBU_UNICODE_STRING@@KPEAPEAU2@@Z; RegistryKey::StaticNtOpenCaseSensitive(HKEY__ *,_UNICODE_STRING const &,ulong,HKEY__ * *)
0x18005a48a  mov     ebx, eax
0x18005a48c  jmp     loc_18005A2DA
0x18005a491  cmp     edi, 800700EAh
0x18005a497  jnz     loc_18005A54F
0x18005a49d  mov     rax, [rsp+2E0h+DestinationString.Buffer]
0x18005a4a2  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005a4a9  movzx   edx, [rsp+2E0h+DestinationString.Length]
0x18005a4ae  mov     r9d, ebx; hr
0x18005a4b1  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005a4b8  mov     [rsp+2E0h+var_2A0], edi
0x18005a4bc  mov     [rsp+2E0h+var_2A8], rax
0x18005a4c1  lea     rax, callerFunction; "StaticNtOpen"
0x18005a4c8  mov     [rsp+2E0h+var_2B0], edx
0x18005a4cc  mov     edx, 214h; lineNumber
0x18005a4d1  mov     [rsp+2E0h+var_2B8], rax
0x18005a4d6  lea     rax, aHsFailedWithPa_0; "%hs failed with path: %.*ls queryHr: %x"
0x18005a4dd  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005a4e2  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a4e7  jmp     loc_18005A2DA
0x18005a4ec  lea     rdx, ?g_WindowsEmptyStringInternal@@3QBGB; ushort const near * const g_WindowsEmptyStringInternal
0x18005a4f3  jmp     loc_18005A32C
0x18005a4f8  lea     rdx, ?g_WindowsEmptyStringInternal@@3QBGB; ushort const near * const g_WindowsEmptyStringInternal
0x18005a4ff  jmp     loc_18005A461
0x18005a504  mov     rax, [rsp+2E0h+DestinationString.Buffer]
0x18005a509  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005a510  movzx   edx, [rsp+2E0h+DestinationString.Length]
0x18005a515  mov     r9d, ebx; hr
0x18005a518  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005a51f  mov     [rsp+2E0h+var_2A8], rax
0x18005a524  lea     rax, callerFunction; "StaticNtOpen"
0x18005a52b  mov     [rsp+2E0h+var_2B0], edx
0x18005a52f  mov     edx, 200h; lineNumber
0x18005a534  mov     [rsp+2E0h+var_2B8], rax
0x18005a539  lea     rax, aHsFailedWithPa_1; "%hs failed with path: %.*ls"
0x18005a540  mov     [rsp+2E0h+ResultLength], rax; formatString
0x18005a545  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a54a  jmp     loc_18005A2DA
0x18005a54f  cmp     edi, 8007007Ah
0x18005a555  jz      loc_18005A49D
0x18005a55b  mov     this, [rbp+1E8h]; callerReturnAddress
0x18005a562  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005a569  mov     r9d, edi; hr
0x18005a56c  mov     edx, 7E1h; lineNumber
0x18005a571  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a576  jmp     loc_18005A49D
```
