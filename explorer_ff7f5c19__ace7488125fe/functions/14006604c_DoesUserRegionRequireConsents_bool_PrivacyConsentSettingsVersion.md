# DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)

- ea: `0x14006604c`
- end: `0x140066265`
- name: `?DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(bool *, enum PrivacyConsentSettingsVersion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140065fd4`

## callees

- `0x14006604c`
- `0x14006626c`
- `0x14009ac68`
- `0x1400baca0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140066137`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140066137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140066116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140066116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400660cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006615f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400661ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140066221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400660cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006615f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400661ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140066221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140066091`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoesUserRegionRequireConsents(bool *a1, enum PrivacyConsentSettingsVersion *a2)
{
  wchar_t **i; // rdi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  const WCHAR *v13; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v20 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string);
  if ( v5 >= 0 )
  {
    v8 = Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(string, &v20);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
      v17 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    else
    {
      v21 = 0;
      v10 = v20;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 64LL);
      WindowsDeleteString(0);
      v21 = 0;
      v12 = v11(v10, &v21);
      v9 = v12;
      if ( v12 >= 0 )
      {
        for ( i = &`DoesUserRegionRequireConsents'::`2'::RegionPrivacyRequirements; ; i += 2 )
        {
          if ( i == (wchar_t **)&AccessibilitySettingsTraceLogging::`vftable' )
          {
            *a1 = 0;
            if ( a2 )
              *(_DWORD *)a2 = 0;
            goto LABEL_9;
          }
          v13 = *i;
          StringRawBuffer = WindowsGetStringRawBuffer(v21, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, v13, -1, 1) == 2 )
            break;
        }
        *a1 = 1;
        if ( a2 )
          goto LABEL_22;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PrivacyConsentHelpers.h",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
      WindowsDeleteString(v21);
      v21 = 0;
      v18 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    return v9;
  }
  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
LABEL_22:
  *(_DWORD *)a2 = *((_DWORD *)i + 2);
LABEL_9:
  WindowsDeleteString(v21);
  v21 = 0;
  v15 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x14006604c  mov     [rsp-28h+arg_10], rbx
0x140066051  push    rbp
0x140066052  push    rsi
0x140066053  push    rdi
0x140066054  push    r14
0x140066056  push    r15
0x140066058  mov     rbp, rsp
0x14006605b  sub     rsp, 70h
0x14006605f  mov     rax, cs:__security_cookie
0x140066066  xor     rax, rsp
0x140066069  mov     [rbp+var_10], rax
0x14006606d  mov     rsi, rdx
0x140066070  mov     r14, rcx
0x140066073  xor     r15d, r15d
0x140066076  mov     [rbp+var_40], r15
0x14006607a  mov     [rbp+string], r15
0x14006607e  lea     r9, [rbp+string]; string
0x140066082  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140066086  lea     edx, [r15+26h]; length
0x14006608a  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x140066091  call    cs:__imp_WindowsCreateStringReference
0x140066098  nop     dword ptr [rax+rax+00h]
0x14006609d  test    eax, eax
0x14006609f  js      loc_14006624D
0x1400660a5  lea     rdx, [rbp+var_40]
0x1400660a9  mov     rcx, [rbp+string]
0x1400660ad  call    ??$ActivateInstance@UIGeographicRegion@Globalization@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIGeographicRegion@Globalization@1@@Z; Windows::Foundation::ActivateInstance<Windows::Globalization::IGeographicRegion>(HSTRING__ *,Windows::Globalization::IGeographicRegion * *)
0x1400660b2  mov     ebx, eax
0x1400660b4  test    eax, eax
0x1400660b6  js      loc_1400661AC
0x1400660bc  mov     [rbp+var_38], r15
0x1400660c0  mov     rdi, [rbp+var_40]
0x1400660c4  mov     rax, [rdi]
0x1400660c7  mov     rbx, [rax+40h]
0x1400660cb  xor     ecx, ecx; string
0x1400660cd  call    cs:__imp_WindowsDeleteString
0x1400660d4  nop     dword ptr [rax+rax+00h]
0x1400660d9  mov     [rbp+var_38], r15
0x1400660dd  lea     rdx, [rbp+var_38]
0x1400660e1  mov     rcx, rdi
0x1400660e4  mov     rax, rbx
0x1400660e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400660ec  mov     ebx, eax
0x1400660ee  test    eax, eax
0x1400660f0  js      loc_140066204
0x1400660f6  lea     rdi, ?RegionPrivacyRequirements@?1??DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z@4QBU_unnamed_type_RegionPrivacyRequirements_@?1??1@YAJ01@Z@B; `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::_unnamed_type_RegionPrivacyRequirements_ const near * const `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::RegionPrivacyRequirements
0x1400660fd  lea     rax, ??_7AccessibilitySettingsTraceLogging@@6B@; const AccessibilitySettingsTraceLogging::`vftable'
0x140066104  cmp     rdi, rax
0x140066107  jz      loc_1400661E3
0x14006610d  mov     rbx, [rdi]
0x140066110  xor     edx, edx; length
0x140066112  mov     rcx, [rbp+var_38]; string
0x140066116  call    cs:__imp_WindowsGetStringRawBuffer
0x14006611d  nop     dword ptr [rax+rax+00h]
0x140066122  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x14006612a  or      r9d, 0FFFFFFFFh; cchCount2
0x14006612e  mov     r8, rbx; lpString2
0x140066131  or      edx, r9d; cchCount1
0x140066134  mov     rcx, rax; lpString1
0x140066137  call    cs:__imp_CompareStringOrdinal
0x14006613e  nop     dword ptr [rax+rax+00h]
0x140066143  cmp     eax, 2
0x140066146  jz      short loc_14006614E
0x140066148  add     rdi, 10h
0x14006614c  jmp     short loc_1400660FD
0x14006614e  mov     byte ptr [r14], 1
0x140066152  test    rsi, rsi
0x140066155  jnz     loc_140066255
0x14006615b  mov     rcx, [rbp+var_38]; string
0x14006615f  call    cs:__imp_WindowsDeleteString
0x140066166  nop     dword ptr [rax+rax+00h]
0x14006616b  mov     [rbp+var_38], r15
0x14006616f  mov     rcx, [rbp+var_40]
0x140066173  test    rcx, rcx
0x140066176  jz      short loc_140066189
0x140066178  mov     [rbp+var_40], r15
0x14006617c  mov     rax, [rcx]
0x14006617f  mov     rax, [rax+10h]
0x140066183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066188  nop
0x140066189  xor     eax, eax
0x14006618b  mov     rcx, [rbp+var_10]
0x14006618f  xor     rcx, rsp; StackCookie
0x140066192  call    __security_check_cookie
0x140066197  mov     rbx, [rsp+70h+arg_10]
0x14006619f  add     rsp, 70h
0x1400661a3  pop     r15
0x1400661a5  pop     r14
0x1400661a7  pop     rdi
0x1400661a8  pop     rsi
0x1400661a9  pop     rbp
0x1400661aa  retn
0x1400661ac  mov     rcx, [rbp+28h]; this
0x1400661b0  mov     r9d, ebx; char *
0x1400661b3  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x1400661ba  mov     edx, 0CFh; void *
0x1400661bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400661c4  nop
0x1400661c5  mov     rcx, [rbp+var_40]
0x1400661c9  test    rcx, rcx
0x1400661cc  jz      short loc_1400661DF
0x1400661ce  mov     [rbp+var_40], r15
0x1400661d2  mov     rax, [rcx]
0x1400661d5  mov     rax, [rax+10h]
0x1400661d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400661de  nop
0x1400661df  mov     eax, ebx
0x1400661e1  jmp     short loc_14006618B
0x1400661e3  mov     [r14], r15b
0x1400661e6  test    rsi, rsi
0x1400661e9  jnz     short loc_14006625F
0x1400661eb  mov     rcx, [rbp+var_38]; string
0x1400661ef  call    cs:__imp_WindowsDeleteString
0x1400661f6  nop     dword ptr [rax+rax+00h]
0x1400661fb  mov     [rbp+var_38], r15
0x1400661ff  jmp     loc_14006616F
0x140066204  mov     rcx, [rbp+28h]; this
0x140066208  mov     r9d, ebx; char *
0x14006620b  lea     r8, aOnecoreuapInte_15; "onecoreuap\\internal\\shell\\inc\\Priva"...
0x140066212  mov     edx, 0D2h; void *
0x140066217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006621c  nop
0x14006621d  mov     rcx, [rbp+var_38]; string
0x140066221  call    cs:__imp_WindowsDeleteString
0x140066228  nop     dword ptr [rax+rax+00h]
0x14006622d  mov     [rbp+var_38], r15
0x140066231  mov     rcx, [rbp+var_40]
0x140066235  test    rcx, rcx
0x140066238  jz      short loc_14006624B
0x14006623a  mov     [rbp+var_40], r15
0x14006623e  mov     rax, [rcx]
0x140066241  mov     rax, [rax+10h]
0x140066245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006624a  nop
0x14006624b  jmp     short loc_1400661DF
0x14006624d  mov     ecx, eax; this
0x14006624f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140066254  nop
0x140066255  mov     eax, [rdi+8]
0x140066258  mov     [rsi], eax
0x14006625a  jmp     loc_14006615B
0x14006625f  mov     [rsi], r15d
0x140066262  jmp     short loc_1400661EB
```
