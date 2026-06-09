# RegistryKey::NtOpen(HKEY__ *,HSTRING__ *,ulong)

- ea: `0x18005e198`
- end: `0x18005e3e9`
- name: `?NtOpen@RegistryKey@@QEAAJPEAUHKEY__@@PEAUHSTRING__@@K@Z`
- size: `593`
- prototype: `HRESULT __fastcall(RegistryKey *this, HKEY__ *hkeyAncestor, HSTRING__ *hstrSubKeyPath, unsigned int desiredAccess)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e170`
- `0x1801445c0`
- `0x1801a6b20`

## callees

- `0x18000833c`
- `0x18005b0a0`
- `0x18005e198`
- `0x1801999b0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18005e21b`
- `ntdll!NtOpenKey` at `0x18005e21b`
- `ntdll!NtQueryKey` at `0x18005e293`
- `ntdll!NtQueryKey` at `0x18005e293`
- `ntdll!RtlNtStatusToDosError` at `0x18005e223`
- `ntdll!RtlNtStatusToDosError` at `0x18005e29b`
- `ntdll!RtlNtStatusToDosError` at `0x18005e223`
- `ntdll!RtlNtStatusToDosError` at `0x18005e29b`
- `ntdll!RtlInitUnicodeString` at `0x18005e1e3`
- `ntdll!RtlInitUnicodeString` at `0x18005e1e3`

## string_xrefs

- `0x18005e2e0`: `StaticNtOpen`
- `0x18005e33b`: `StaticNtOpen`
- `0x18005e392`: `StaticNtOpen`
- `0x18005e2b5`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005e31c`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005e377`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005e3d0`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005e2f5`: `%hs failed with path:%.*ls %.*ls`
- `0x18005e350`: `%hs failed with path: %.*ls queryHr: %x`
- `0x18005e3a7`: `%hs failed with path: %.*ls`

## pseudocode

```c
__int64 __fastcall RegistryKey::NtOpen(
        RegistryKey *this,
        HKEY__ *hkeyAncestor,
        HSTRING__ *hstrSubKeyPath,
        ACCESS_MASK desiredAccess)
{
  const wchar_t *v7; // rdx
  NTSTATUS v8; // eax
  signed int v9; // eax
  HRESULT v10; // edi
  NTSTATUS v12; // eax
  signed int v13; // eax
  HRESULT v14; // ebx
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int ResultLength; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  int KeyInformation; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v19[262]; // [rsp+A4h] [rbp-5Ch] BYREF
  void *retaddr; // [rsp+2D8h] [rbp+1D8h]

  if ( hstrSubKeyPath )
    v7 = (const wchar_t *)*((_QWORD *)hstrSubKeyPath + 2);
  else
    v7 = g_WindowsEmptyStringInternal;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v7);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = hkeyAncestor;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenKey((PHANDLE)&this->_hkey, desiredAccess, &ObjectAttributes);
  v9 = RtlNtStatusToDosError(v8);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 != -2147024894 && v10 < 0 )
  {
    if ( hkeyAncestor )
    {
      ResultLength = 516;
      v12 = NtQueryKey(hkeyAncestor, KeyNameInformation, &KeyInformation, 0x204u, &ResultLength);
      v13 = RtlNtStatusToDosError(v12);
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      if ( v14 < 0 )
      {
        if ( v14 != -2147024662 && v14 != -2147024774 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0x7E1u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v14);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          0x214u,
          "onecore\\com\\combase\\inc\\RegistryKey.hpp",
          v10,
          "%hs failed with path: %.*ls queryHr: %x",
          "StaticNtOpen",
          DestinationString.Length,
          DestinationString.Buffer,
          v14);
      }
      else
      {
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          0x210u,
          "onecore\\com\\combase\\inc\\RegistryKey.hpp",
          v10,
          "%hs failed with path:%.*ls %.*ls",
          "StaticNtOpen",
          KeyInformation,
          v19,
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
        v10,
        "%hs failed with path: %.*ls",
        "StaticNtOpen",
        DestinationString.Length,
        DestinationString.Buffer);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005e198  mov     [rsp-8+arg_10], rbx
0x18005e19d  push    rbp
0x18005e19e  push    rsi
0x18005e19f  push    rdi
0x18005e1a0  lea     rbp, [rsp-1C0h]
0x18005e1a8  sub     rsp, 2C0h
0x18005e1af  mov     rax, cs:__security_cookie
0x18005e1b6  xor     rax, rsp
0x18005e1b9  mov     [rbp+1D0h+var_20], rax
0x18005e1c0  mov     esi, desiredAccess
0x18005e1c3  mov     rbx, hkeyAncestor
0x18005e1c6  mov     rdi, this
0x18005e1c9  test    hstrSubKeyPath, hstrSubKeyPath
0x18005e1cc  jz      loc_18005E366
0x18005e1d2  mov     hkeyAncestor, [hstrSubKeyPath+10h]; SourceString
0x18005e1d6  xorps   xmm0, xmm0
0x18005e1d9  lea     this, [rsp+2D0h+DestinationString]; DestinationString
0x18005e1de  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x18005e1e3  call    cs:__imp_RtlInitUnicodeString
0x18005e1e9  lea     rax, [rsp+2D0h+DestinationString]
0x18005e1ee  mov     qword ptr [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x18005e1f7  xorps   xmm0, xmm0
0x18005e1fa  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x18005e1ff  lea     hstrSubKeyPath, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x18005e204  mov     qword ptr [rbp+1D0h+ObjectAttributes.Attributes], 40h ; '@'
0x18005e20c  mov     edx, esi; DesiredAccess
0x18005e20e  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rbx
0x18005e213  mov     this, rdi; KeyHandle
0x18005e216  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e21b  call    cs:__imp_NtOpenKey
0x18005e221  mov     ecx, eax; Status
0x18005e223  call    cs:__imp_RtlNtStatusToDosError
0x18005e229  mov     edi, eax
0x18005e22b  mov     esi, 80070000h
0x18005e230  test    eax, eax
0x18005e232  jle     short loc_18005E239
0x18005e234  movzx   edi, ax
0x18005e237  or      edi, esi
0x18005e239  cmp     edi, 80070002h
0x18005e23f  jz      short loc_18005E245
0x18005e241  test    edi, edi
0x18005e243  js      short loc_18005E269
0x18005e245  mov     eax, edi
0x18005e247  mov     this, [rbp+1D0h+var_20]
0x18005e24e  xor     this, rsp; StackCookie
0x18005e251  call    __security_check_cookie
0x18005e256  mov     rbx, [rsp+2D0h+arg_10]
0x18005e25e  add     rsp, 2C0h
0x18005e265  pop     rdi
0x18005e266  pop     rsi
0x18005e267  pop     rbp
0x18005e268  retn
0x18005e269  test    rbx, rbx
0x18005e26c  jz      loc_18005E372
0x18005e272  mov     desiredAccess, 204h; Length
0x18005e278  lea     rax, [rsp+2D0h+var_270]
0x18005e27d  lea     hstrSubKeyPath, [rbp+1D0h+KeyInformation]; KeyInformation
0x18005e281  mov     [rsp+2D0h+var_270], desiredAccess
0x18005e286  mov     edx, 3; KeyInformationClass
0x18005e28b  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x18005e290  mov     this, rbx; KeyHandle
0x18005e293  call    cs:__imp_NtQueryKey
0x18005e299  mov     ecx, eax; Status
0x18005e29b  call    cs:__imp_RtlNtStatusToDosError
0x18005e2a1  mov     ebx, eax
0x18005e2a3  test    eax, eax
0x18005e2a5  jle     short loc_18005E2AC
0x18005e2a7  movzx   ebx, ax
0x18005e2aa  or      ebx, esi
0x18005e2ac  test    ebx, ebx
0x18005e2ae  js      short loc_18005E30B
0x18005e2b0  mov     rax, [rsp+2D0h+DestinationString.Buffer]
0x18005e2b5  lea     hstrSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005e2bc  movzx   edx, [rsp+2D0h+DestinationString.Length]
0x18005e2c1  mov     desiredAccess, edi; hr
0x18005e2c4  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005e2cb  mov     [rsp+2D0h+var_288], rax
0x18005e2d0  lea     rax, [rbp+1D0h+var_22C]
0x18005e2d4  mov     [rsp+2D0h+var_290], edx
0x18005e2d8  mov     edx, [rbp+1D0h+KeyInformation]
0x18005e2db  mov     [rsp+2D0h+var_298], rax
0x18005e2e0  lea     rax, callerFunction; "StaticNtOpen"
0x18005e2e7  mov     [rsp+2D0h+var_2A0], edx
0x18005e2eb  mov     edx, 210h; lineNumber
0x18005e2f0  mov     [rsp+2D0h+var_2A8], rax
0x18005e2f5  lea     rax, aHsFailedWithPa; "%hs failed with path:%.*ls %.*ls"
0x18005e2fc  mov     [rsp+2D0h+ResultLength], rax; formatString
0x18005e301  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e306  jmp     loc_18005E245
0x18005e30b  cmp     ebx, 800700EAh
0x18005e311  jnz     loc_18005E3BD
0x18005e317  mov     rax, [rsp+2D0h+DestinationString.Buffer]
0x18005e31c  lea     hstrSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005e323  movzx   edx, [rsp+2D0h+DestinationString.Length]
0x18005e328  mov     desiredAccess, edi; hr
0x18005e32b  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005e332  mov     [rsp+2D0h+var_290], ebx
0x18005e336  mov     [rsp+2D0h+var_298], rax
0x18005e33b  lea     rax, callerFunction; "StaticNtOpen"
0x18005e342  mov     [rsp+2D0h+var_2A0], edx
0x18005e346  mov     edx, 214h; lineNumber
0x18005e34b  mov     [rsp+2D0h+var_2A8], rax
0x18005e350  lea     rax, aHsFailedWithPa_0; "%hs failed with path: %.*ls queryHr: %x"
0x18005e357  mov     [rsp+2D0h+ResultLength], rax; formatString
0x18005e35c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e361  jmp     loc_18005E245
0x18005e366  lea     hkeyAncestor, ?g_WindowsEmptyStringInternal@@3QBGB; ushort const near * const g_WindowsEmptyStringInternal
0x18005e36d  jmp     loc_18005E1D6
0x18005e372  mov     rax, [rsp+2D0h+DestinationString.Buffer]
0x18005e377  lea     hstrSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005e37e  movzx   edx, [rsp+2D0h+DestinationString.Length]
0x18005e383  mov     desiredAccess, edi; hr
0x18005e386  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005e38d  mov     [rsp+2D0h+var_298], rax
0x18005e392  lea     rax, callerFunction; "StaticNtOpen"
0x18005e399  mov     [rsp+2D0h+var_2A0], edx
0x18005e39d  mov     edx, 200h; lineNumber
0x18005e3a2  mov     [rsp+2D0h+var_2A8], rax
0x18005e3a7  lea     rax, aHsFailedWithPa_1; "%hs failed with path: %.*ls"
0x18005e3ae  mov     [rsp+2D0h+ResultLength], rax; formatString
0x18005e3b3  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005e3b8  jmp     loc_18005E245
0x18005e3bd  cmp     ebx, 8007007Ah
0x18005e3c3  jz      loc_18005E317
0x18005e3c9  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005e3d0  lea     hstrSubKeyPath, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x18005e3d7  mov     desiredAccess, ebx; hr
0x18005e3da  mov     edx, 7E1h; lineNumber
0x18005e3df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e3e4  jmp     loc_18005E317
```
