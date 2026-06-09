# DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)

- ea: `0x180095ae4`
- end: `0x180095ca8`
- name: `?DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(bool *, enum PrivacyConsentSettingsVersion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180095210`

## callees

- `0x180003470`
- `0x180008544`
- `0x180042068`
- `0x180094994`
- `0x180095ae4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095c1a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095bff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095bff`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoesUserRegionRequireConsents(bool *a1, enum PrivacyConsentSettingsVersion *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  __int64 v11; // rcx
  wchar_t **v12; // rdi
  const WCHAR *v13; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v15; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v17 = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v4 = Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(v20, &v17);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    v6 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  string = 0;
  v8 = v17;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(v8, &string);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
    WindowsDeleteString(string);
    string = 0;
    v11 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v5;
  }
  v12 = &`DoesUserRegionRequireConsents'::`2'::RegionPrivacyRequirements;
  while ( 1 )
  {
    v13 = *v12;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, v13, -1, 1) == 2 )
      break;
    v12 += 2;
    if ( v12 == (wchar_t **)&c_szCapabilityLocation )
    {
      *a1 = 0;
      if ( a2 )
        *(_DWORD *)a2 = 0;
      goto LABEL_17;
    }
  }
  *a1 = 1;
  if ( a2 )
    *(_DWORD *)a2 = *((_DWORD *)v12 + 2);
LABEL_17:
  WindowsDeleteString(string);
  string = 0;
  v15 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180095ae4  mov     [rsp-28h+arg_10], rbx
0x180095ae9  push    rbp
0x180095aea  push    rsi
0x180095aeb  push    rdi
0x180095aec  push    r14
0x180095aee  push    r15
0x180095af0  mov     rbp, rsp
0x180095af3  sub     rsp, 70h
0x180095af7  mov     rax, cs:__security_cookie
0x180095afe  xor     rax, rsp
0x180095b01  mov     [rbp+var_10], rax
0x180095b05  mov     rsi, rdx
0x180095b08  mov     r14, rcx
0x180095b0b  xor     r15d, r15d
0x180095b0e  mov     [rbp+var_40], r15
0x180095b12  mov     [rbp+var_18], r15
0x180095b16  lea     r9d, [r15+26h]; unsigned int
0x180095b1a  lea     r8d, [r15+27h]; unsigned int
0x180095b1e  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x180095b25  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180095b29  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180095b2e  nop
0x180095b2f  lea     rdx, [rbp+var_40]
0x180095b33  mov     rcx, [rbp+var_18]
0x180095b37  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x180095b3c  mov     ebx, eax
0x180095b3e  test    eax, eax
0x180095b40  jns     short loc_180095B7C
0x180095b42  mov     rcx, [rbp+28h]; this
0x180095b46  mov     r9d, eax; char *
0x180095b49  lea     r8, aOnecoreuapInte_10; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x180095b50  mov     edx, 0CFh; void *
0x180095b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095b5a  nop
0x180095b5b  mov     rcx, [rbp+var_40]
0x180095b5f  test    rcx, rcx
0x180095b62  jz      short loc_180095B75
0x180095b64  mov     [rbp+var_40], r15
0x180095b68  mov     rax, [rcx]
0x180095b6b  mov     rax, [rax+10h]
0x180095b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b74  nop
0x180095b75  mov     eax, ebx
0x180095b77  jmp     loc_180095C88
0x180095b7c  mov     [rbp+string], r15
0x180095b80  mov     rdi, [rbp+var_40]
0x180095b84  mov     rax, [rdi]
0x180095b87  mov     rbx, [rax+40h]
0x180095b8b  xor     ecx, ecx; string
0x180095b8d  call    cs:__imp_WindowsDeleteString
0x180095b93  mov     [rbp+string], r15
0x180095b97  lea     rdx, [rbp+string]
0x180095b9b  mov     rcx, rdi
0x180095b9e  mov     rax, rbx
0x180095ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ba6  mov     ebx, eax
0x180095ba8  test    eax, eax
0x180095baa  jns     short loc_180095BEF
0x180095bac  mov     rcx, [rbp+28h]; this
0x180095bb0  mov     r9d, eax; char *
0x180095bb3  lea     r8, aOnecoreuapInte_10; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x180095bba  mov     edx, 0D2h; void *
0x180095bbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095bc4  nop
0x180095bc5  mov     rcx, [rbp+string]; string
0x180095bc9  call    cs:__imp_WindowsDeleteString
0x180095bcf  mov     [rbp+string], r15
0x180095bd3  mov     rcx, [rbp+var_40]
0x180095bd7  test    rcx, rcx
0x180095bda  jz      short loc_180095BED
0x180095bdc  mov     [rbp+var_40], r15
0x180095be0  mov     rax, [rcx]
0x180095be3  mov     rax, [rax+10h]
0x180095be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095bec  nop
0x180095bed  jmp     short loc_180095B75
0x180095bef  lea     rdi, ?RegionPrivacyRequirements@?1??DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z@4QBU_unnamed_type_RegionPrivacyRequirements_@?1??1@YAJ01@Z@B; `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::_unnamed_type_RegionPrivacyRequirements_ const near * const `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::RegionPrivacyRequirements
0x180095bf6  mov     rbx, [rdi]
0x180095bf9  xor     edx, edx; length
0x180095bfb  mov     rcx, [rbp+string]; string
0x180095bff  call    cs:__imp_WindowsGetStringRawBuffer
0x180095c05  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180095c0d  or      r9d, 0FFFFFFFFh; cchCount2
0x180095c11  mov     r8, rbx; lpString2
0x180095c14  or      edx, r9d; cchCount1
0x180095c17  mov     rcx, rax; lpString1
0x180095c1a  call    cs:__imp_CompareStringOrdinal
0x180095c20  cmp     eax, 2
0x180095c23  jz      short loc_180095C50
0x180095c25  add     rdi, 10h
0x180095c29  lea     rax, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180095c30  cmp     rdi, rax
0x180095c33  jnz     short loc_180095BF6
0x180095c35  mov     [r14], r15b
0x180095c38  test    rsi, rsi
0x180095c3b  jz      short loc_180095C40
0x180095c3d  mov     [rsi], r15d
0x180095c40  mov     rcx, [rbp+string]; string
0x180095c44  call    cs:__imp_WindowsDeleteString
0x180095c4a  mov     [rbp+string], r15
0x180095c4e  jmp     short loc_180095C6C
0x180095c50  mov     byte ptr [r14], 1
0x180095c54  test    rsi, rsi
0x180095c57  jz      short loc_180095C5E
0x180095c59  mov     eax, [rdi+8]
0x180095c5c  mov     [rsi], eax
0x180095c5e  mov     rcx, [rbp+string]; string
0x180095c62  call    cs:__imp_WindowsDeleteString
0x180095c68  mov     [rbp+string], r15
0x180095c6c  mov     rcx, [rbp+var_40]
0x180095c70  test    rcx, rcx
0x180095c73  jz      short loc_180095C86
0x180095c75  mov     [rbp+var_40], r15
0x180095c79  mov     rax, [rcx]
0x180095c7c  mov     rax, [rax+10h]
0x180095c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c85  nop
0x180095c86  xor     eax, eax
0x180095c88  mov     rcx, [rbp+var_10]
0x180095c8c  xor     rcx, rsp; StackCookie
0x180095c8f  call    __security_check_cookie
0x180095c94  mov     rbx, [rsp+70h+arg_10]
0x180095c9c  add     rsp, 70h
0x180095ca0  pop     r15
0x180095ca2  pop     r14
0x180095ca4  pop     rdi
0x180095ca5  pop     rsi
0x180095ca6  pop     rbp
0x180095ca7  retn
```
