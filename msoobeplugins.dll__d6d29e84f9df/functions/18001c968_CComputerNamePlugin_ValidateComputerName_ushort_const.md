# CComputerNamePlugin::_ValidateComputerName(ushort const *)

- ea: `0x18001c968`
- end: `0x18001caef`
- name: `?_ValidateComputerName@CComputerNamePlugin@@AEAAJPEBG@Z`
- size: `391`
- prototype: `__int64 __fastcall(CComputerNamePlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bc60`
- `0x18001bdf0`
- `0x18001c734`

## callees

- `0x180003470`
- `0x18001c498`
- `0x18001c568`
- `0x18001c968`
- `0x1800bf2ac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca1a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ca1a`
- `ntdll!RtlInitUnicodeString` at `0x18001ca7d`
- `ntdll!RtlInitUnicodeString` at `0x18001ca7d`
- `ntdll!RtlCanonicalizeDomainName` at `0x18001ca8e`
- `ntdll!RtlCanonicalizeDomainName` at `0x18001ca8e`
- `ntdll!RtlEqualUnicodeString` at `0x18001caa3`
- `ntdll!RtlEqualUnicodeString` at `0x18001caa3`
- `ntdll!RtlFreeUnicodeString` at `0x18001cab5`
- `ntdll!RtlFreeUnicodeString` at `0x18001cab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ca2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cabf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ca2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cabf`
- `DNSAPI!DnsValidateName_W` at `0x18001c999`
- `DNSAPI!DnsValidateName_W` at `0x18001c999`

## pseudocode

```c
__int64 __fastcall CComputerNamePlugin::_ValidateComputerName(CComputerNamePlugin *this, const unsigned __int16 *a2)
{
  DNS_STATUS v4; // eax
  CComputerNamePlugin *v5; // rcx
  signed int GlobalSettingString; // ebx
  PCNZWCH SourceString; // [rsp+30h] [rbp-50h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-48h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-30h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]

  v4 = DnsValidateName_W(a2, DnsNameHostnameLabel);
  if ( (!v4 || v4 == 9556)
    && (nSize = 16,
        String2 = 0,
        v12 = 0,
        (unsigned int)CComputerNamePlugin::_DnsHostnameToComputerName(this, a2, &String2.Length, &nSize)) )
  {
    SourceString = 0;
    GlobalSettingString = CBasePlugin::_GetGlobalSettingString(this, L"USERNAME", (unsigned __int16 **)&SourceString);
    if ( GlobalSettingString < 0 )
    {
      if ( GlobalSettingString == -2147023728 )
        GlobalSettingString = 0;
    }
    else
    {
      if ( CompareStringW(0x400u, 1u, a2, -1, SourceString, -1) == 2 )
        GlobalSettingString = -2147024844;
      CoTaskMemFree((LPVOID)SourceString);
    }
    if ( GlobalSettingString >= 0 )
    {
      SourceString = 0;
      GlobalSettingString = -2147467259;
      if ( (int)CComputerNamePlugin::_DnsNormalizeName(v5, a2, (unsigned __int16 **)&SourceString) >= 0 )
      {
        DestinationString = 0;
        String2 = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        if ( (int)RtlCanonicalizeDomainName(&String2, &DestinationString, 0) >= 0 )
        {
          GlobalSettingString = RtlEqualUnicodeString(&DestinationString, &String2, 0) == 0 ? 0x80004005 : 0;
          RtlFreeUnicodeString(&String2);
        }
        CoTaskMemFree((LPVOID)SourceString);
      }
    }
  }
  else
  {
    return (unsigned int)-2147023686;
  }
  return (unsigned int)GlobalSettingString;
}

```

## disassembly

```asm
0x18001c968  mov     [rsp-8+arg_10], rbx
0x18001c96d  mov     [rsp-8+arg_18], rdi
0x18001c972  push    rbp
0x18001c973  mov     rbp, rsp
0x18001c976  sub     rsp, 80h
0x18001c97d  mov     rax, cs:__security_cookie
0x18001c984  xor     rax, rsp
0x18001c987  mov     [rbp+var_10], rax
0x18001c98b  mov     rdi, rdx
0x18001c98e  mov     rbx, rcx
0x18001c991  mov     rcx, rdi; pszName
0x18001c994  mov     edx, 3; Format
0x18001c999  call    cs:__imp_DnsValidateName_W
0x18001c99f  test    eax, eax
0x18001c9a1  jz      short loc_18001C9AE
0x18001c9a3  cmp     eax, 2554h
0x18001c9a8  jnz     loc_18001CAC7
0x18001c9ae  xorps   xmm0, xmm0
0x18001c9b1  mov     [rbp+nSize], 10h
0x18001c9b8  lea     r9, [rbp+nSize]; nSize
0x18001c9bc  mov     rdx, rdi; lpWideCharStr
0x18001c9bf  lea     r8, [rbp+String2]; LPWSTR
0x18001c9c3  mov     rcx, rbx; this
0x18001c9c6  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18001c9ca  movups  [rbp+var_20], xmm0
0x18001c9ce  call    ?_DnsHostnameToComputerName@CComputerNamePlugin@@AEAAHPEBGPEAGPEAK@Z; CComputerNamePlugin::_DnsHostnameToComputerName(ushort const *,ushort *,ulong *)
0x18001c9d3  test    eax, eax
0x18001c9d5  jz      loc_18001CAC7
0x18001c9db  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18001c9df  mov     [rbp+SourceString], 0
0x18001c9e7  lea     rdx, aUsername; "USERNAME"
0x18001c9ee  mov     rcx, rbx; this
0x18001c9f1  call    ?_GetGlobalSettingString@CBasePlugin@@IEAAJPEBGPEAPEAG@Z; CBasePlugin::_GetGlobalSettingString(ushort const *,ushort * *)
0x18001c9f6  mov     ebx, eax
0x18001c9f8  test    eax, eax
0x18001c9fa  js      short loc_18001CA37
0x18001c9fc  mov     rax, [rbp+SourceString]
0x18001ca00  or      r9d, 0FFFFFFFFh; cchCount1
0x18001ca04  mov     [rsp+80h+cchCount2], r9d; cchCount2
0x18001ca09  mov     r8, rdi; lpString1
0x18001ca0c  mov     ecx, 400h; Locale
0x18001ca11  mov     [rsp+80h+lpString2], rax; lpString2
0x18001ca16  lea     edx, [r9+2]; dwCmpFlags
0x18001ca1a  call    cs:__imp_CompareStringW
0x18001ca20  cmp     eax, 2
0x18001ca23  mov     ecx, 80070034h
0x18001ca28  cmovz   ebx, ecx
0x18001ca2b  mov     rcx, [rbp+SourceString]; pv
0x18001ca2f  call    cs:__imp_CoTaskMemFree
0x18001ca35  jmp     short loc_18001CA42
0x18001ca37  xor     eax, eax
0x18001ca39  cmp     ebx, 80070490h
0x18001ca3f  cmovz   ebx, eax
0x18001ca42  test    ebx, ebx
0x18001ca44  js      loc_18001CACC
0x18001ca4a  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18001ca4e  mov     [rbp+SourceString], 0
0x18001ca56  mov     rdx, rdi; unsigned __int16 *
0x18001ca59  mov     ebx, 80004005h
0x18001ca5e  call    ?_DnsNormalizeName@CComputerNamePlugin@@AEAAJPEBGPEAPEAG@Z; CComputerNamePlugin::_DnsNormalizeName(ushort const *,ushort * *)
0x18001ca63  test    eax, eax
0x18001ca65  js      short loc_18001CACC
0x18001ca67  mov     rdx, [rbp+SourceString]; SourceString
0x18001ca6b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001ca6f  xorps   xmm0, xmm0
0x18001ca72  xorps   xmm1, xmm1
0x18001ca75  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001ca79  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18001ca7d  call    cs:__imp_RtlInitUnicodeString
0x18001ca83  xor     r8d, r8d
0x18001ca86  lea     rdx, [rbp+DestinationString]
0x18001ca8a  lea     rcx, [rbp+String2]
0x18001ca8e  call    cs:__imp_RtlCanonicalizeDomainName
0x18001ca94  test    eax, eax
0x18001ca96  js      short loc_18001CABB
0x18001ca98  xor     r8d, r8d; CaseInsensitive
0x18001ca9b  lea     rdx, [rbp+String2]; String2
0x18001ca9f  lea     rcx, [rbp+DestinationString]; String1
0x18001caa3  call    cs:__imp_RtlEqualUnicodeString
0x18001caa9  neg     al
0x18001caab  lea     rcx, [rbp+String2]; UnicodeString
0x18001caaf  sbb     edx, edx
0x18001cab1  not     edx
0x18001cab3  and     ebx, edx
0x18001cab5  call    cs:__imp_RtlFreeUnicodeString
0x18001cabb  mov     rcx, [rbp+SourceString]; pv
0x18001cabf  call    cs:__imp_CoTaskMemFree
0x18001cac5  jmp     short loc_18001CACC
0x18001cac7  mov     ebx, 800704BAh
0x18001cacc  mov     eax, ebx
0x18001cace  mov     rcx, [rbp+var_10]
0x18001cad2  xor     rcx, rsp; StackCookie
0x18001cad5  call    __security_check_cookie
0x18001cada  lea     r11, [rsp+80h+var_s0]
0x18001cae2  mov     rbx, [r11+20h]
0x18001cae6  mov     rdi, [r11+28h]
0x18001caea  mov     rsp, r11
0x18001caed  pop     rbp
0x18001caee  retn
```
