# FeatureExperimentManager::ShouldApplyConfig(VariantConfiguration const &)

- ea: `0x180068a14`
- end: `0x180068c13`
- name: `?ShouldApplyConfig@FeatureExperimentManager@@CA_NAEBVVariantConfiguration@@@Z`
- size: `511`
- prototype: `bool __fastcall(const struct VariantConfiguration *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180067550`

## callees

- `0x180003220`
- `0x180010450`
- `0x180016b6c`
- `0x180019704`
- `0x180019890`
- `0x180027290`
- `0x18004bf64`
- `0x180068a14`
- `0x180075f58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180068bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180068bae`

## string_xrefs

- `0x180068ac7`: `RollbackPolicy`
- `0x180068b2c`: `RollbackPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall FeatureExperimentManager::ShouldApplyConfig(const struct VariantConfiguration *a1)
{
  __m128i si128; // xmm1
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  HSTRING v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  char v13; // bl
  __int64 v14; // rdx
  INT32 result; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  _OWORD v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  __int128 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  _BYTE v27[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[32]; // [rsp+E0h] [rbp-20h] BYREF

  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( StagingControls_GetFeatureMetadata(4u, *((_DWORD *)a1 + 1), (struct _RTL_FEATURE_CONFIGURATION_METADATA *)&v20) < 0
    || (v24 & 0x800000000LL) == 0
    || HIDWORD(v23) != 3 )
  {
    goto LABEL_19;
  }
  v19[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v19[1] = si128;
  LOWORD(v19[0]) = 0;
  v3 = *((_QWORD *)a1 + 5);
  v4 = *((_QWORD *)a1 + 6);
  if ( v3 != v4 )
  {
    while ( 1 )
    {
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v5,
                              *(_QWORD *)(v3 + 16),
                              L"RollbackPolicy",
                              14) )
        break;
      v3 += 72;
      if ( v3 == v4 )
        goto LABEL_9;
    }
    std::wstring::operator=(v19, v3 + 32);
LABEL_9:
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v18[0] = 0;
  v18[1] = si128;
  LOWORD(v18[0]) = 0;
  v6 = v25;
  v7 = v26;
  while ( v6 != v7 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                            v8,
                            *(_QWORD *)(v6 + 16),
                            L"RollbackPolicy",
                            14) )
    {
      std::wstring::operator=(v18, v6 + 32);
      break;
    }
    v6 += 72;
  }
  result = 0;
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
  v9 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v27, &v17) + 24);
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v28, &v17);
  WindowsCompareStringOrdinal(*(HSTRING *)(v10 + 24), v9, &result);
  if ( result )
  {
    std::wstring::_Tidy_deallocate(v18, v11);
    std::wstring::_Tidy_deallocate(v19, v14);
LABEL_19:
    v13 = 1;
    goto LABEL_20;
  }
  std::wstring::_Tidy_deallocate(v18, v11);
  std::wstring::_Tidy_deallocate(v19, v12);
  v13 = 0;
LABEL_20:
  std::vector<RTL_PROPERTY_BAG_ITEM>::_Tidy(&v25);
  return v13;
}

```

## disassembly

```asm
0x180068a14  mov     [rsp-8+arg_8], rbx
0x180068a19  mov     [rsp-8+arg_10], rdi
0x180068a1e  push    rbp
0x180068a1f  lea     rbp, [rsp-10h]
0x180068a24  sub     rsp, 110h
0x180068a2b  mov     rax, cs:__security_cookie
0x180068a32  xor     rax, rsp
0x180068a35  mov     [rbp+10h+var_10], rax
0x180068a39  mov     rdi, rcx
0x180068a3c  xor     eax, eax
0x180068a3e  mov     [rsp+110h+var_A0], rax
0x180068a43  xorps   xmm0, xmm0
0x180068a46  movups  [rsp+110h+var_98], xmm0
0x180068a4b  mov     [rbp+10h+var_88], rax
0x180068a4f  xorps   xmm1, xmm1
0x180068a52  movups  [rbp+10h+var_80], xmm1
0x180068a56  mov     [rbp+10h+var_70], rax
0x180068a5a  mov     [rbp+10h+var_68], rax
0x180068a5e  movdqa  [rbp+10h+var_60], xmm0
0x180068a63  lea     r8, [rsp+110h+var_A0]; struct _RTL_FEATURE_CONFIGURATION_METADATA *
0x180068a68  mov     edx, [rcx+4]; unsigned int
0x180068a6b  lea     ecx, [rax+4]; unsigned int
0x180068a6e  call    ?StagingControls_GetFeatureMetadata@@YAJIIPEAU_RTL_FEATURE_CONFIGURATION_METADATA@@@Z; StagingControls_GetFeatureMetadata(uint,uint,_RTL_FEATURE_CONFIGURATION_METADATA *)
0x180068a73  test    eax, eax
0x180068a75  js      loc_180068BE5
0x180068a7b  test    byte ptr [rbp+10h+var_70+4], 8
0x180068a7f  jz      loc_180068BE5
0x180068a85  cmp     dword ptr [rbp+10h+var_80+0Ch], 3
0x180068a89  jnz     loc_180068BE5
0x180068a8f  xorps   xmm0, xmm0
0x180068a92  movups  [rsp+110h+var_C0], xmm0
0x180068a97  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180068a9f  movdqu  [rsp+110h+var_B0], xmm1
0x180068aa5  xor     eax, eax
0x180068aa7  mov     word ptr [rsp+110h+var_C0], ax
0x180068aac  mov     rbx, [rdi+28h]
0x180068ab0  mov     rdi, [rdi+30h]
0x180068ab4  cmp     rbx, rdi
0x180068ab7  jz      short loc_180068AFF
0x180068ab9  mov     rcx, rbx
0x180068abc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068ac1  mov     r9d, 0Eh
0x180068ac7  lea     r8, ?RollbackPolicy@FeatureMetadataUtils@@3QBGB; "RollbackPolicy"
0x180068ace  mov     rdx, [rbx+10h]
0x180068ad2  mov     rcx, rax
0x180068ad5  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180068ada  test    al, al
0x180068adc  jnz     short loc_180068AE9
0x180068ade  add     rbx, 48h ; 'H'
0x180068ae2  cmp     rbx, rdi
0x180068ae5  jnz     short loc_180068AB9
0x180068ae7  jmp     short loc_180068AF7
0x180068ae9  lea     rdx, [rbx+20h]
0x180068aed  lea     rcx, [rsp+110h+var_C0]
0x180068af2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180068af7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180068aff  xorps   xmm0, xmm0
0x180068b02  movups  [rsp+110h+var_E0], xmm0
0x180068b07  movdqu  [rsp+110h+var_D0], xmm1
0x180068b0d  xor     eax, eax
0x180068b0f  mov     word ptr [rsp+110h+var_E0], ax
0x180068b14  mov     rbx, [rbp+10h+var_68]
0x180068b18  mov     rdi, qword ptr [rbp+10h+var_60]
0x180068b1c  jmp     short loc_180068B47
0x180068b1e  mov     rcx, rbx
0x180068b21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068b26  mov     r9d, 0Eh
0x180068b2c  lea     r8, ?RollbackPolicy@FeatureMetadataUtils@@3QBGB; "RollbackPolicy"
0x180068b33  mov     rdx, [rbx+10h]
0x180068b37  mov     rcx, rax
0x180068b3a  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180068b3f  test    al, al
0x180068b41  jnz     short loc_180068B4E
0x180068b43  add     rbx, 48h ; 'H'
0x180068b47  cmp     rbx, rdi
0x180068b4a  jnz     short loc_180068B1E
0x180068b4c  jmp     short loc_180068B5C
0x180068b4e  lea     rdx, [rbx+20h]
0x180068b52  lea     rcx, [rsp+110h+var_E0]
0x180068b57  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180068b5c  mov     [rsp+110h+result], 0
0x180068b64  lea     rcx, [rsp+110h+var_E0]
0x180068b69  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068b6e  mov     [rsp+110h+var_E8], rax
0x180068b73  lea     rdx, [rsp+110h+var_E8]
0x180068b78  lea     rcx, [rbp+10h+var_50]
0x180068b7c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180068b81  mov     rbx, [rax+18h]
0x180068b85  lea     rcx, [rsp+110h+var_C0]
0x180068b8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068b8f  mov     [rsp+110h+var_E8], rax
0x180068b94  lea     rdx, [rsp+110h+var_E8]
0x180068b99  lea     rcx, [rbp+10h+var_30]
0x180068b9d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180068ba2  lea     r8, [rsp+110h+result]; result
0x180068ba7  mov     rdx, rbx; string2
0x180068baa  mov     rcx, [rax+18h]; string1
0x180068bae  call    cs:__imp_WindowsCompareStringOrdinal
0x180068bb4  nop
0x180068bb5  lea     rcx, [rsp+110h+var_E0]
0x180068bba  cmp     [rsp+110h+result], 0
0x180068bbf  jnz     short loc_180068BD5
0x180068bc1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068bc6  nop
0x180068bc7  lea     rcx, [rsp+110h+var_C0]
0x180068bcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068bd1  xor     ebx, ebx
0x180068bd3  jmp     short loc_180068BE7
0x180068bd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068bda  nop
0x180068bdb  lea     rcx, [rsp+110h+var_C0]
0x180068be0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068be5  mov     bl, 1
0x180068be7  lea     rcx, [rbp+10h+var_68]
0x180068beb  call    ?_Tidy@?$vector@URTL_PROPERTY_BAG_ITEM@@V?$allocator@URTL_PROPERTY_BAG_ITEM@@@std@@@std@@AEAAXXZ; std::vector<RTL_PROPERTY_BAG_ITEM>::_Tidy(void)
0x180068bf0  mov     al, bl
0x180068bf2  mov     rcx, [rbp+10h+var_10]
0x180068bf6  xor     rcx, rsp; StackCookie
0x180068bf9  call    __security_check_cookie
0x180068bfe  lea     r11, [rsp+110h+var_s0]
0x180068c06  mov     rbx, [r11+18h]
0x180068c0a  mov     rdi, [r11+20h]
0x180068c0e  mov     rsp, r11
0x180068c11  pop     rbp
0x180068c12  retn
```
