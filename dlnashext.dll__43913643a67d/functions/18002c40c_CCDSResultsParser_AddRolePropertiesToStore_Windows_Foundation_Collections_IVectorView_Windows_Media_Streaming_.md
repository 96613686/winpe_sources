# CCDSResultsParser::AddRolePropertiesToStore(Windows::Foundation::Collections::IVectorView<Windows::Media::Streaming::Internal::ICDSPropertyValue *> *,CCDSResultsParser::RoleMap const *,ulong,IPropertyStore *)

- ea: `0x18002c40c`
- end: `0x18002c613`
- name: `?AddRolePropertiesToStore@CCDSResultsParser@@SAJPEAU?$IVectorView@PEAUICDSPropertyValue@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@PEBURoleMap@1@KPEAUIPropertyStore@@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002e13c`

## callees

- `0x1800097c0`
- `0x18000a4a0`
- `0x18000d990`
- `0x18002c40c`
- `0x18002c8fc`
- `0x18002cab8`
- `0x18002cc20`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c534`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c563`

## pseudocode

```c
__int64 __fastcall CCDSResultsParser::AddRolePropertiesToStore(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        struct IPropertyStore *a4)
{
  __int64 *v5; // rsi
  unsigned int v7; // r12d
  __int64 v8; // rax
  int PropertyValueRole; // edi
  unsigned int i; // r15d
  __int64 v11; // rax
  __int64 (__fastcall *v12)(__int64 *, _QWORD, struct Windows::Media::Streaming::Internal::ICDSPropertyValue **); // rbx
  __int64 j; // rsi
  const WCHAR *v14; // rbx
  const WCHAR *StringRawBuffer; // rax
  PCWSTR v16; // rax
  __int64 v17; // rcx
  const struct _tagpropertykey *v18; // rcx
  __int64 v19; // rdx
  unsigned int v21; // [rsp+30h] [rbp-40h] BYREF
  int v22; // [rsp+34h] [rbp-3Ch] BYREF
  struct Windows::Media::Streaming::Internal::ICDSPropertyValue *v23; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  __int128 v26; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h]

  v22 = 2;
  v5 = a1;
  v7 = a3;
  CCDSResultsParser::GetMediaTypeForItem(a4, (enum _CDS_MEDIA_TYPE *)&v22);
  v8 = *v5;
  v21 = 0;
  PropertyValueRole = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v8 + 56))(v5, &v21);
  if ( PropertyValueRole >= 0 )
  {
    for ( i = 0; i < v21; ++i )
    {
      if ( PropertyValueRole < 0 )
        break;
      v11 = *v5;
      v23 = 0;
      v12 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct Windows::Media::Streaming::Internal::ICDSPropertyValue **))(v11 + 48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v23);
      PropertyValueRole = v12(v5, i, &v23);
      if ( PropertyValueRole >= 0 )
      {
        string = 0;
        PropertyValueRole = CCDSResultsParser::GetPropertyValueRole(v23, &string);
        if ( PropertyValueRole >= 0 )
        {
          v24 = 0;
          PropertyValueRole = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::ICDSPropertyValue *, HSTRING *))(*(_QWORD *)v23 + 56LL))(
                                v23,
                                &v24);
          if ( PropertyValueRole >= 0 )
          {
            for ( j = 0; (unsigned int)j < v7; j = (unsigned int)(j + 1) )
            {
              v14 = *(const WCHAR **)(a2 + 24 * j);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(StringRawBuffer, -1, v14, -1, 1) == 2 )
              {
                v27 = 0;
                v26 = 0;
                LOWORD(v26) = 31;
                v16 = WindowsGetStringRawBuffer(v24, 0);
                v17 = *(_QWORD *)(a2 + 24 * j + 16);
                *((_QWORD *)&v26 + 1) = v16;
                if ( (unsigned int)operator==(v17, &PKEY_Null) || v22 == 2 )
                {
                  if ( !CCDSResultsParser::IsPropertyPresentInPropertyStore(
                          a4,
                          *(const struct _tagpropertykey **)(a2 + 24 * j + 8)) )
                  {
                    v19 = *(_QWORD *)(a2 + 24 * j + 8);
LABEL_17:
                    PropertyValueRole = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64, __int128 *))a4->lpVtbl->SetValue)(
                                          a4,
                                          v19,
                                          &v26);
                  }
                }
                else if ( !CCDSResultsParser::IsPropertyPresentInPropertyStore(a4, v18) )
                {
                  v19 = *(_QWORD *)(a2 + 24 * j + 16);
                  goto LABEL_17;
                }
                v7 = a3;
                break;
              }
              v7 = a3;
            }
            v5 = a1;
          }
          Windows::Internal::String::~String(&v24);
        }
        Windows::Internal::String::~String(&string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v23);
    }
  }
  return (unsigned int)PropertyValueRole;
}

```

## disassembly

```asm
0x18002c40c  mov     [rsp-38h+arg_8], rbx
0x18002c411  mov     [rsp-38h+arg_10], r8d
0x18002c416  mov     [rsp-38h+arg_0], rcx
0x18002c41b  push    rbp
0x18002c41c  push    rsi
0x18002c41d  push    rdi
0x18002c41e  push    r12
0x18002c420  push    r13
0x18002c422  push    r14
0x18002c424  push    r15
0x18002c426  mov     rbp, rsp
0x18002c429  sub     rsp, 70h
0x18002c42d  mov     r13, rdx
0x18002c430  mov     [rbp+var_3C], 2
0x18002c437  mov     rsi, rcx
0x18002c43a  lea     rdx, [rbp+var_3C]; enum _CDS_MEDIA_TYPE *
0x18002c43e  mov     rcx, r9; struct IPropertyStore *
0x18002c441  mov     r14, r9
0x18002c444  mov     r12d, r8d
0x18002c447  call    ?GetMediaTypeForItem@CCDSResultsParser@@SAJPEAUIPropertyStore@@PEAW4_CDS_MEDIA_TYPE@@@Z; CCDSResultsParser::GetMediaTypeForItem(IPropertyStore *,_CDS_MEDIA_TYPE *)
0x18002c44c  mov     rax, [rsi]
0x18002c44f  lea     rdx, [rbp+var_40]
0x18002c453  mov     rcx, rsi
0x18002c456  mov     [rbp+var_40], 0
0x18002c45d  mov     rax, [rax+38h]
0x18002c461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c466  mov     edi, eax
0x18002c468  test    eax, eax
0x18002c46a  js      loc_18002C5F9
0x18002c470  xor     r15d, r15d
0x18002c473  cmp     [rbp+var_40], r15d
0x18002c477  jbe     loc_18002C5F9
0x18002c47d  test    edi, edi
0x18002c47f  js      loc_18002C5F9
0x18002c485  mov     rax, [rsi]
0x18002c488  lea     rcx, [rbp+var_38]
0x18002c48c  mov     [rbp+var_38], 0
0x18002c494  mov     rbx, [rax+30h]
0x18002c498  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002c49d  lea     r8, [rbp+var_38]
0x18002c4a1  mov     edx, r15d
0x18002c4a4  mov     rcx, rsi
0x18002c4a7  mov     rax, rbx
0x18002c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4af  mov     edi, eax
0x18002c4b1  test    eax, eax
0x18002c4b3  js      loc_18002C5E3
0x18002c4b9  mov     rcx, [rbp+var_38]; struct Windows::Media::Streaming::Internal::ICDSPropertyValue *
0x18002c4bd  lea     rdx, [rbp+string]; HSTRING *
0x18002c4c1  mov     [rbp+string], 0
0x18002c4c9  call    ?GetPropertyValueRole@CCDSResultsParser@@SAJPEAUICDSPropertyValue@Internal@Streaming@Media@Windows@@PEAPEAUHSTRING__@@@Z; CCDSResultsParser::GetPropertyValueRole(Windows::Media::Streaming::Internal::ICDSPropertyValue *,HSTRING__ * *)
0x18002c4ce  mov     edi, eax
0x18002c4d0  test    eax, eax
0x18002c4d2  js      loc_18002C5DA
0x18002c4d8  mov     rcx, [rbp+var_38]
0x18002c4dc  lea     rdx, [rbp+var_30]
0x18002c4e0  mov     [rbp+var_30], 0
0x18002c4e8  mov     rax, [rcx]
0x18002c4eb  mov     rax, [rax+38h]
0x18002c4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4f4  mov     edi, eax
0x18002c4f6  test    eax, eax
0x18002c4f8  js      loc_18002C5D1
0x18002c4fe  xor     esi, esi
0x18002c500  cmp     esi, r12d
0x18002c503  jnb     loc_18002C5CD
0x18002c509  mov     rcx, [rbp+string]; string
0x18002c50d  lea     r12, [rsi+rsi*2]
0x18002c511  mov     rbx, [r13+r12*8+0]
0x18002c516  xor     edx, edx; length
0x18002c518  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c51e  or      ecx, 0FFFFFFFFh
0x18002c521  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x18002c529  mov     r9d, ecx; cchCount2
0x18002c52c  mov     edx, ecx; cchCount1
0x18002c52e  mov     rcx, rax; lpString1
0x18002c531  mov     r8, rbx; lpString2
0x18002c534  call    cs:__imp_CompareStringOrdinal
0x18002c53a  cmp     eax, 2
0x18002c53d  jz      short loc_18002C547
0x18002c53f  mov     r12d, [rbp+arg_10]
0x18002c543  inc     esi
0x18002c545  jmp     short loc_18002C500
0x18002c547  mov     rcx, [rbp+var_30]; string
0x18002c54b  xor     eax, eax
0x18002c54d  mov     [rbp+var_10], rax
0x18002c551  xorps   xmm0, xmm0
0x18002c554  mov     eax, 1Fh
0x18002c559  xor     edx, edx; length
0x18002c55b  movups  [rbp+var_20], xmm0
0x18002c55f  mov     word ptr [rbp+var_20], ax
0x18002c563  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c569  mov     rcx, [r13+r12*8+10h]
0x18002c56e  lea     rdx, PKEY_Null
0x18002c575  mov     qword ptr [rbp+var_20+8], rax
0x18002c579  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002c57e  test    eax, eax
0x18002c580  jnz     short loc_18002C59E
0x18002c582  cmp     [rbp+var_3C], 2
0x18002c586  jz      short loc_18002C59E
0x18002c588  mov     rdx, rcx; struct _tagpropertykey *
0x18002c58b  mov     rcx, r14; struct IPropertyStore *
0x18002c58e  call    ?IsPropertyPresentInPropertyStore@CCDSResultsParser@@SA_NPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; CCDSResultsParser::IsPropertyPresentInPropertyStore(IPropertyStore *,_tagpropertykey const &)
0x18002c593  test    al, al
0x18002c595  jnz     short loc_18002C5C9
0x18002c597  mov     rdx, [r13+r12*8+10h]
0x18002c59c  jmp     short loc_18002C5B4
0x18002c59e  mov     rdx, [r13+r12*8+8]; struct _tagpropertykey *
0x18002c5a3  mov     rcx, r14; struct IPropertyStore *
0x18002c5a6  call    ?IsPropertyPresentInPropertyStore@CCDSResultsParser@@SA_NPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; CCDSResultsParser::IsPropertyPresentInPropertyStore(IPropertyStore *,_tagpropertykey const &)
0x18002c5ab  test    al, al
0x18002c5ad  jnz     short loc_18002C5C9
0x18002c5af  mov     rdx, [r13+r12*8+8]
0x18002c5b4  mov     rax, [r14]
0x18002c5b7  lea     r8, [rbp+var_20]
0x18002c5bb  mov     rcx, r14
0x18002c5be  mov     rax, [rax+30h]
0x18002c5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5c7  mov     edi, eax
0x18002c5c9  mov     r12d, [rbp+arg_10]
0x18002c5cd  mov     rsi, [rbp+arg_0]
0x18002c5d1  lea     rcx, [rbp+var_30]; this
0x18002c5d5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002c5da  lea     rcx, [rbp+string]; this
0x18002c5de  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002c5e3  lea     rcx, [rbp+var_38]
0x18002c5e7  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002c5ec  inc     r15d
0x18002c5ef  cmp     r15d, [rbp+var_40]
0x18002c5f3  jb      loc_18002C47D
0x18002c5f9  mov     rbx, [rsp+70h+arg_8]
0x18002c601  mov     eax, edi
0x18002c603  add     rsp, 70h
0x18002c607  pop     r15
0x18002c609  pop     r14
0x18002c60b  pop     r13
0x18002c60d  pop     r12
0x18002c60f  pop     rdi
0x18002c610  pop     rsi
0x18002c611  pop     rbp
0x18002c612  retn
```
