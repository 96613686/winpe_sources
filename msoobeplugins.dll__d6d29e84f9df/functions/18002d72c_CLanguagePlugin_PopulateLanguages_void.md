# CLanguagePlugin::_PopulateLanguages(void)

- ea: `0x18002d72c`
- end: `0x18002da6b`
- name: `?_PopulateLanguages@CLanguagePlugin@@AEAAJXZ`
- size: `831`
- prototype: `__int64 __fastcall(CLanguagePlugin *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ceb0`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180007bbc`
- `0x180008b54`
- `0x18000ac48`
- `0x18000bb38`
- `0x18001a09c`
- `0x18002d72c`
- `0x1800b81e4`
- `0x1800b82d4`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002d864`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002d864`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002d888`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002d888`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d808`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d918`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d808`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d918`
- `KERNEL32!EnumUILanguagesW` at `0x18002d794`
- `KERNEL32!EnumUILanguagesW` at `0x18002d794`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLanguagePlugin::_PopulateLanguages(COOBEItemCollection **this)
{
  unsigned int v2; // r12d
  char v3; // r15
  struct CLanguage *v4; // rbx
  unsigned int i; // r14d
  LCID v6; // eax
  unsigned __int16 v7; // di
  int v8; // esi
  struct CLanguage *v9; // rdi
  struct IOOBEItem *v10; // rdx
  unsigned int Error; // eax
  const wchar_t *v12; // rdx
  int v13; // eax
  struct CLanguage *v15; // [rsp+30h] [rbp-D0h] BYREF
  struct CLanguage *v16; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String2[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR String1[264]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR LCData[264]; // [rsp+670h] [rbp+570h] BYREF

  memset_0(String1, 0, 0x208u);
  v2 = 0;
  g_uNumLangIdx = 0;
  g_LangNumber = 0;
  LODWORD(g_BufferSize) = 0;
  if ( EnumUILanguagesW((UILANGUAGE_ENUMPROCW)EnumUILanguagesProc, 0, 0) )
    v2 = g_uNumLangIdx;
  UnattendLogW(0, L"Found [%d] UI languages", v2);
  v3 = 0;
  v4 = 0;
  v15 = 0;
  for ( i = 0; i < v2; ++i )
  {
    if ( !GetSupportedUILangugages_mOOBE(i, String2, 0x104u) )
    {
      UnattendLogW(1, L"Failed to get UI Language info for language %d", i);
      continue;
    }
    if ( CompareStringOrdinal(String1, -1, String2, -1, 0) == 2 )
      continue;
    if ( StringCchCopyW(String1, 0x104u, String2) < 0 )
      String1[0] = 0;
    if ( !(unsigned int)GetNativeDisplayNameEx(String2, v17, 0x104u) )
    {
      UnattendLogW(1, L"Failed to Native Display name for language %s", String2);
      continue;
    }
    v6 = LocaleNameToLCID(String2, 0);
    v7 = v6;
    if ( !v6 )
    {
      Error = ResultFromKnownLastError();
      v12 = L"Failed to convert locale name to LCID for language %s with hr=0x%08X";
      goto LABEL_30;
    }
    if ( !GetLocaleInfoW(v6, 0x59u, LCData, 260) )
    {
      Error = ResultFromKnownLastError();
      v12 = L"Failed to get locale info for language %s with hr=0x%08X";
LABEL_30:
      UnattendLogW(1, v12, v17, Error);
      continue;
    }
    v16 = 0;
    v8 = CLanguage::s_Create(v17, LCData, v7, &v16);
    if ( v8 < 0 )
      goto LABEL_28;
    v9 = v16;
    if ( v16 )
      v10 = (struct CLanguage *)((char *)v16 + 24);
    else
      v10 = 0;
    v8 = COOBEItemCollection::AddItem(this[6], v10);
    if ( v8 < 0 )
    {
      (*(void (__fastcall **)(struct CLanguage *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_28:
      UnattendLogW(1, L"Failed to add language %s with hr=0x%08X", v17, (unsigned int)v8);
      continue;
    }
    UnattendLogW(0, L"Successfully added language %s", v17);
    if ( CompareStringOrdinal(LCData, -1, L"en", -1, 1) == 2 )
    {
      if ( v3 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
        v4 = v15;
      }
      else
      {
        if ( v9 )
          v9 = (struct CLanguage *)((char *)v9 + 24);
        if ( v4 != v9 )
        {
          if ( v9 )
            (*(void (__fastcall **)(struct CLanguage *))(*(_QWORD *)v9 + 8LL))(v9);
          v16 = v4;
          v4 = v9;
          v15 = v9;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
        }
        v3 = 1;
      }
    }
  }
  if ( v3 )
  {
    if ( v4 )
    {
      v13 = (*(__int64 (__fastcall **)(struct CLanguage *))(*(_QWORD *)v4 + 32LL))(v4);
      if ( v13 < 0 )
        UnattendLogW(2, L"Failed to override language item display name [hr=0x%08X]", (unsigned int)v13);
    }
  }
  (*(void (__fastcall **)(COOBEItemCollection *))(*(_QWORD *)this[6] + 40LL))(this[6]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  return 0;
}

```

## disassembly

```asm
0x18002d72c  push    rbp
0x18002d72e  push    rbx
0x18002d72f  push    rsi
0x18002d730  push    rdi
0x18002d731  push    r12
0x18002d733  push    r13
0x18002d735  push    r14
0x18002d737  push    r15
0x18002d739  lea     rbp, [rsp-798h]
0x18002d741  sub     rsp, 898h
0x18002d748  mov     rax, cs:__security_cookie
0x18002d74f  xor     rax, rsp
0x18002d752  mov     [rbp+7D0h+var_50], rax
0x18002d759  mov     r13, rcx
0x18002d75c  xor     edx, edx; Val
0x18002d75e  mov     r8d, 208h; Size
0x18002d764  lea     rcx, [rbp+7D0h+String1]; void *
0x18002d76b  call    memset_0
0x18002d770  xor     r12d, r12d
0x18002d773  mov     cs:?g_uNumLangIdx@@3IA, r12d; uint g_uNumLangIdx
0x18002d77a  mov     cs:?g_LangNumber@@3IA, r12d; uint g_LangNumber
0x18002d781  mov     cs:?g_BufferSize@@3IA, r12d; uint g_BufferSize
0x18002d788  xor     r8d, r8d; lParam
0x18002d78b  xor     edx, edx; dwFlags
0x18002d78d  lea     rcx, ?EnumUILanguagesProc@@YAHPEAG_J@Z; lpUILanguageEnumProc
0x18002d794  call    cs:__imp_EnumUILanguagesW
0x18002d79a  test    eax, eax
0x18002d79c  cmovnz  r12d, cs:?g_uNumLangIdx@@3IA; uint g_uNumLangIdx
0x18002d7a4  mov     r8d, r12d
0x18002d7a7  lea     rdx, aFoundDUiLangua; "Found [%d] UI languages"
0x18002d7ae  xor     ecx, ecx
0x18002d7b0  call    UnattendLogW
0x18002d7b5  xor     r15b, r15b
0x18002d7b8  xor     ebx, ebx
0x18002d7ba  mov     [rsp+8D0h+var_8A0], rbx
0x18002d7bf  xor     r14d, r14d
0x18002d7c2  lea     esi, [rbx+1]
0x18002d7c5  cmp     r14d, r12d
0x18002d7c8  jnb     loc_18002D9FA
0x18002d7ce  mov     r8d, 104h; unsigned int
0x18002d7d4  lea     rdx, [rbp+7D0h+String2]; unsigned __int16 *
0x18002d7db  mov     ecx, r14d; unsigned int
0x18002d7de  call    ?GetSupportedUILangugages_mOOBE@@YAIIPEAGI@Z; GetSupportedUILangugages_mOOBE(uint,ushort *,uint)
0x18002d7e3  test    eax, eax
0x18002d7e5  jz      loc_18002D9E1
0x18002d7eb  mov     [rsp+8D0h+bIgnoreCase], 0; bIgnoreCase
0x18002d7f3  or      r9d, 0FFFFFFFFh; cchCount2
0x18002d7f7  lea     r8, [rbp+7D0h+String2]; lpString2
0x18002d7fe  or      edx, r9d; cchCount1
0x18002d801  lea     rcx, [rbp+7D0h+String1]; lpString1
0x18002d808  call    cs:__imp_CompareStringOrdinal
0x18002d80e  cmp     eax, 2
0x18002d811  jz      loc_18002D9F2
0x18002d817  lea     r8, [rbp+7D0h+String2]; unsigned __int16 *
0x18002d81e  mov     edx, 104h; unsigned __int64
0x18002d823  lea     rcx, [rbp+7D0h+String1]; unsigned __int16 *
0x18002d82a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d82f  test    eax, eax
0x18002d831  jns     short loc_18002D83C
0x18002d833  xor     eax, eax
0x18002d835  mov     [rbp+7D0h+String1], ax
0x18002d83c  mov     r8d, 104h
0x18002d842  lea     rdx, [rsp+8D0h+var_890]
0x18002d847  lea     rcx, [rbp+7D0h+String2]
0x18002d84e  call    GetNativeDisplayNameEx
0x18002d853  test    eax, eax
0x18002d855  jz      loc_18002D9CA
0x18002d85b  xor     edx, edx; dwFlags
0x18002d85d  lea     rcx, [rbp+7D0h+String2]; lpName
0x18002d864  call    cs:__imp_LocaleNameToLCID
0x18002d86a  mov     edi, eax
0x18002d86c  test    eax, eax
0x18002d86e  jz      loc_18002D9BC
0x18002d874  mov     r9d, 104h; cchData
0x18002d87a  lea     r8, [rbp+7D0h+LCData]; lpLCData
0x18002d881  mov     edx, 59h ; 'Y'; LCType
0x18002d886  mov     ecx, eax; Locale
0x18002d888  call    cs:__imp_GetLocaleInfoW
0x18002d88e  test    eax, eax
0x18002d890  jz      loc_18002D99F
0x18002d896  mov     [rsp+8D0h+var_898], 0
0x18002d89f  movzx   r8d, di; unsigned __int16
0x18002d8a3  lea     r9, [rsp+8D0h+var_898]; struct CLanguage **
0x18002d8a8  lea     rdx, [rbp+7D0h+LCData]; unsigned __int16 *
0x18002d8af  lea     rcx, [rsp+8D0h+var_890]; unsigned __int16 *
0x18002d8b4  call    ?s_Create@CLanguage@@SAJPEBG0GPEAPEAV1@@Z; CLanguage::s_Create(ushort const *,ushort const *,ushort,CLanguage * *)
0x18002d8b9  mov     esi, eax
0x18002d8bb  test    eax, eax
0x18002d8bd  js      loc_18002D98E
0x18002d8c3  mov     rdi, [rsp+8D0h+var_898]
0x18002d8c8  test    rdi, rdi
0x18002d8cb  jz      short loc_18002D8D3
0x18002d8cd  lea     rdx, [rdi+18h]
0x18002d8d1  jmp     short loc_18002D8D5
0x18002d8d3  xor     edx, edx; struct IOOBEItem *
0x18002d8d5  mov     rcx, [r13+30h]; this
0x18002d8d9  call    ?AddItem@COOBEItemCollection@@QEAAJPEAUIOOBEItem@@@Z; COOBEItemCollection::AddItem(IOOBEItem *)
0x18002d8de  mov     esi, eax
0x18002d8e0  test    eax, eax
0x18002d8e2  js      loc_18002D97F
0x18002d8e8  lea     r8, [rsp+8D0h+var_890]
0x18002d8ed  lea     rdx, aSuccessfullyAd; "Successfully added language %s"
0x18002d8f4  xor     ecx, ecx
0x18002d8f6  call    UnattendLogW
0x18002d8fb  mov     esi, 1
0x18002d900  mov     [rsp+8D0h+bIgnoreCase], esi; bIgnoreCase
0x18002d904  or      edx, 0FFFFFFFFh; cchCount1
0x18002d907  mov     r9d, edx; cchCount2
0x18002d90a  lea     r8, aEn; "en"
0x18002d911  lea     rcx, [rbp+7D0h+LCData]; lpString1
0x18002d918  call    cs:__imp_CompareStringOrdinal
0x18002d91e  cmp     eax, 2
0x18002d921  jnz     loc_18002D9F2
0x18002d927  test    r15b, r15b
0x18002d92a  jz      short loc_18002D940
0x18002d92c  lea     rcx, [rsp+8D0h+var_8A0]
0x18002d931  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002d936  mov     rbx, [rsp+8D0h+var_8A0]
0x18002d93b  jmp     loc_18002D9F2
0x18002d940  test    rdi, rdi
0x18002d943  jz      short loc_18002D949
0x18002d945  add     rdi, 18h
0x18002d949  cmp     rbx, rdi
0x18002d94c  jz      short loc_18002D97A
0x18002d94e  test    rdi, rdi
0x18002d951  jz      short loc_18002D963
0x18002d953  mov     rax, [rdi]
0x18002d956  mov     rcx, rdi
0x18002d959  mov     rax, [rax+8]
0x18002d95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d962  nop
0x18002d963  mov     [rsp+8D0h+var_898], rbx
0x18002d968  mov     rbx, rdi
0x18002d96b  mov     [rsp+8D0h+var_8A0], rbx
0x18002d970  lea     rcx, [rsp+8D0h+var_898]
0x18002d975  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002d97a  mov     r15b, sil
0x18002d97d  jmp     short loc_18002D9F2
0x18002d97f  mov     rax, [rdi]
0x18002d982  mov     rcx, rdi
0x18002d985  mov     rax, [rax+10h]
0x18002d989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d98e  mov     r9d, esi
0x18002d991  lea     rdx, aFailedToAddLan; "Failed to add language %s with hr=0x%08"...
0x18002d998  mov     esi, 1
0x18002d99d  jmp     short loc_18002D9AE
0x18002d99f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d9a4  lea     rdx, aFailedToGetLoc_2; "Failed to get locale info for language "...
0x18002d9ab  mov     r9d, eax
0x18002d9ae  lea     r8, [rsp+8D0h+var_890]
0x18002d9b3  mov     ecx, esi
0x18002d9b5  call    UnattendLogW
0x18002d9ba  jmp     short loc_18002D9F2
0x18002d9bc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d9c1  lea     rdx, aFailedToConver; "Failed to convert locale name to LCID f"...
0x18002d9c8  jmp     short loc_18002D9AB
0x18002d9ca  lea     r8, [rbp+7D0h+String2]
0x18002d9d1  lea     rdx, aFailedToNative; "Failed to Native Display name for langu"...
0x18002d9d8  mov     ecx, esi
0x18002d9da  call    UnattendLogW
0x18002d9df  jmp     short loc_18002D9F2
0x18002d9e1  mov     r8d, r14d
0x18002d9e4  lea     rdx, aFailedToGetUiL; "Failed to get UI Language info for lang"...
0x18002d9eb  mov     ecx, esi
0x18002d9ed  call    UnattendLogW
0x18002d9f2  add     r14d, esi
0x18002d9f5  jmp     loc_18002D7C5
0x18002d9fa  test    r15b, r15b
0x18002d9fd  jz      short loc_18002DA2B
0x18002d9ff  test    rbx, rbx
0x18002da02  jz      short loc_18002DA2B
0x18002da04  mov     rax, [rbx]
0x18002da07  mov     rcx, rbx
0x18002da0a  mov     rax, [rax+20h]
0x18002da0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da13  test    eax, eax
0x18002da15  jns     short loc_18002DA2B
0x18002da17  mov     r8d, eax
0x18002da1a  lea     rdx, aFailedToOverri; "Failed to override language item displa"...
0x18002da21  mov     ecx, 2
0x18002da26  call    UnattendLogW
0x18002da2b  mov     rcx, [r13+30h]
0x18002da2f  mov     rax, [rcx]
0x18002da32  mov     rax, [rax+28h]
0x18002da36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da3b  nop
0x18002da3c  lea     rcx, [rsp+8D0h+var_8A0]
0x18002da41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002da46  xor     eax, eax
0x18002da48  mov     rcx, [rbp+7D0h+var_50]
0x18002da4f  xor     rcx, rsp; StackCookie
0x18002da52  call    __security_check_cookie
0x18002da57  add     rsp, 898h
0x18002da5e  pop     r15
0x18002da60  pop     r14
0x18002da62  pop     r13
0x18002da64  pop     r12
0x18002da66  pop     rdi
0x18002da67  pop     rsi
0x18002da68  pop     rbx
0x18002da69  pop     rbp
0x18002da6a  retn
```
