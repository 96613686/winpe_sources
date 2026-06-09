# CCDSResultsParser::AddSearchClassPropertiesToStore(Windows::Foundation::Collections::IVectorView<Windows::Media::Streaming::Internal::ICDSPropertyValue *> *,IPropertyStore *)

- ea: `0x18002c61c`
- end: `0x18002c83d`
- name: `?AddSearchClassPropertiesToStore@CCDSResultsParser@@SAJPEAU?$IVectorView@PEAUICDSPropertyValue@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@PEAUIPropertyStore@@@Z`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e13c`

## callees

- `0x1800097c0`
- `0x18000d990`
- `0x18002c61c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c6ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c723`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c759`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c78d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c7c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c6ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c723`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c759`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c78d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c7c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c6d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c6d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c73b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c76f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c7a3`

## pseudocode

```c
__int64 __fastcall CCDSResultsParser::AddSearchClassPropertiesToStore(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rax
  int v5; // ebx
  int v6; // edi
  unsigned int v7; // r14d
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64 *, _QWORD, __int64 *); // rbx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v11; // rax
  const WCHAR *v12; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int128 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  unsigned int v19; // [rsp+90h] [rbp+40h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *a1;
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v2 + 56))(a1, &v19);
  if ( v5 >= 0 )
  {
    v6 = 0;
    v7 = 0;
    if ( v19 )
    {
      while ( v5 >= 0 )
      {
        v8 = *a1;
        v21 = 0;
        v9 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v21);
        v5 = v9(a1, v7, &v21);
        if ( v5 >= 0 )
        {
          string = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 56LL))(v21, &string);
          if ( v5 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            if ( CompareStringOrdinal(StringRawBuffer, 21, L"object.item.videoItem", 21, 1) == 2 )
            {
              v6 |= 4u;
            }
            else
            {
              v11 = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(v11, 21, L"object.item.audioItem", 21, 1) == 2 )
              {
                v6 |= 2u;
              }
              else
              {
                v12 = WindowsGetStringRawBuffer(string, 0);
                if ( CompareStringOrdinal(v12, 21, L"object.item.imageItem", 21, 1) == 2 )
                {
                  v6 |= 8u;
                }
                else
                {
                  v13 = WindowsGetStringRawBuffer(string, 0);
                  if ( CompareStringOrdinal(v13, 33, L"object.container.album.musicAlbum", 33, 1) == 2 )
                  {
                    v6 |= 0x40u;
                  }
                  else
                  {
                    v14 = WindowsGetStringRawBuffer(string, 0);
                    if ( CompareStringOrdinal(v14, 34, L"object.container.album.musicArtist", 34, 1) == 2 )
                      v6 |= 0x20u;
                  }
                }
              }
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v21);
        if ( ++v7 >= v19 )
        {
          if ( v5 < 0 )
            return (unsigned int)v5;
          goto LABEL_19;
        }
      }
    }
    else
    {
LABEL_19:
      if ( v6 )
      {
        v18 = 0;
        v17 = 0;
        LOWORD(v17) = 19;
        v15 = *a2;
        DWORD2(v17) = v6;
        return (unsigned int)(*(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, __int128 *))(v15 + 48))(
                               a2,
                               &PKEY_SearchClass,
                               &v17);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c61c  push    rbp
0x18002c61e  push    rbx
0x18002c61f  push    rsi
0x18002c620  push    rdi
0x18002c621  push    r12
0x18002c623  push    r14
0x18002c625  push    r15
0x18002c627  mov     rbp, rsp
0x18002c62a  sub     rsp, 50h
0x18002c62e  mov     rax, [rcx]
0x18002c631  mov     r12, rdx
0x18002c634  lea     rdx, [rbp+arg_0]
0x18002c638  mov     [rbp+arg_0], 0
0x18002c63f  mov     r15, rcx
0x18002c642  mov     rax, [rax+38h]
0x18002c646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c64b  mov     ebx, eax
0x18002c64d  test    eax, eax
0x18002c64f  js      loc_18002C82C
0x18002c655  xor     edi, edi
0x18002c657  xor     r14d, r14d
0x18002c65a  cmp     [rbp+arg_0], edi
0x18002c65d  jbe     loc_18002C7F2
0x18002c663  mov     esi, 1
0x18002c668  test    ebx, ebx
0x18002c66a  js      loc_18002C82C
0x18002c670  mov     rax, [r15]
0x18002c673  lea     rcx, [rbp+arg_18]
0x18002c677  mov     [rbp+arg_18], 0
0x18002c67f  mov     rbx, [rax+30h]
0x18002c683  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002c688  lea     r8, [rbp+arg_18]
0x18002c68c  mov     edx, r14d
0x18002c68f  mov     rcx, r15
0x18002c692  mov     rax, rbx
0x18002c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c69a  mov     ebx, eax
0x18002c69c  test    eax, eax
0x18002c69e  js      loc_18002C7D8
0x18002c6a4  mov     rcx, [rbp+arg_18]
0x18002c6a8  lea     rdx, [rbp+string]
0x18002c6ac  mov     [rbp+string], 0
0x18002c6b4  mov     rax, [rcx]
0x18002c6b7  mov     rax, [rax+38h]
0x18002c6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6c0  mov     ebx, eax
0x18002c6c2  test    eax, eax
0x18002c6c4  js      loc_18002C7CF
0x18002c6ca  mov     rcx, [rbp+string]; string
0x18002c6ce  xor     edx, edx; length
0x18002c6d0  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c6d6  lea     ecx, [rsi+14h]
0x18002c6d9  mov     [rsp+50h+bIgnoreCase], esi; bIgnoreCase
0x18002c6dd  mov     r9d, ecx; cchCount2
0x18002c6e0  lea     r8, aObjectItemVide_0; "object.item.videoItem"
0x18002c6e7  mov     edx, ecx; cchCount1
0x18002c6e9  mov     rcx, rax; lpString1
0x18002c6ec  call    cs:__imp_CompareStringOrdinal
0x18002c6f2  cmp     eax, 2
0x18002c6f5  jnz     short loc_18002C6FF
0x18002c6f7  or      edi, 4
0x18002c6fa  jmp     loc_18002C7CF
0x18002c6ff  mov     rcx, [rbp+string]; string
0x18002c703  xor     edx, edx; length
0x18002c705  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c70b  mov     ecx, 15h
0x18002c710  mov     [rsp+50h+bIgnoreCase], esi; bIgnoreCase
0x18002c714  mov     r9d, ecx; cchCount2
0x18002c717  lea     r8, aObjectItemAudi; "object.item.audioItem"
0x18002c71e  mov     edx, ecx; cchCount1
0x18002c720  mov     rcx, rax; lpString1
0x18002c723  call    cs:__imp_CompareStringOrdinal
0x18002c729  cmp     eax, 2
0x18002c72c  jnz     short loc_18002C735
0x18002c72e  or      edi, eax
0x18002c730  jmp     loc_18002C7CF
0x18002c735  mov     rcx, [rbp+string]; string
0x18002c739  xor     edx, edx; length
0x18002c73b  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c741  mov     ecx, 15h
0x18002c746  mov     [rsp+50h+bIgnoreCase], esi; bIgnoreCase
0x18002c74a  mov     r9d, ecx; cchCount2
0x18002c74d  lea     r8, aObjectItemImag_0; "object.item.imageItem"
0x18002c754  mov     edx, ecx; cchCount1
0x18002c756  mov     rcx, rax; lpString1
0x18002c759  call    cs:__imp_CompareStringOrdinal
0x18002c75f  cmp     eax, 2
0x18002c762  jnz     short loc_18002C769
0x18002c764  or      edi, 8
0x18002c767  jmp     short loc_18002C7CF
0x18002c769  mov     rcx, [rbp+string]; string
0x18002c76d  xor     edx, edx; length
0x18002c76f  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c775  mov     ecx, 21h ; '!'
0x18002c77a  mov     [rsp+50h+bIgnoreCase], esi; bIgnoreCase
0x18002c77e  mov     r9d, ecx; cchCount2
0x18002c781  lea     r8, aObjectContaine_3; "object.container.album.musicAlbum"
0x18002c788  mov     edx, ecx; cchCount1
0x18002c78a  mov     rcx, rax; lpString1
0x18002c78d  call    cs:__imp_CompareStringOrdinal
0x18002c793  cmp     eax, 2
0x18002c796  jnz     short loc_18002C79D
0x18002c798  or      edi, 40h
0x18002c79b  jmp     short loc_18002C7CF
0x18002c79d  mov     rcx, [rbp+string]; string
0x18002c7a1  xor     edx, edx; length
0x18002c7a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c7a9  mov     ecx, 22h ; '"'
0x18002c7ae  mov     [rsp+50h+bIgnoreCase], esi; bIgnoreCase
0x18002c7b2  mov     r9d, ecx; cchCount2
0x18002c7b5  lea     r8, aObjectContaine_1; "object.container.album.musicArtist"
0x18002c7bc  mov     edx, ecx; cchCount1
0x18002c7be  mov     rcx, rax; lpString1
0x18002c7c1  call    cs:__imp_CompareStringOrdinal
0x18002c7c7  cmp     eax, 2
0x18002c7ca  jnz     short loc_18002C7CF
0x18002c7cc  or      edi, 20h
0x18002c7cf  lea     rcx, [rbp+string]; this
0x18002c7d3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002c7d8  lea     rcx, [rbp+arg_18]
0x18002c7dc  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002c7e1  inc     r14d
0x18002c7e4  cmp     r14d, [rbp+arg_0]
0x18002c7e8  jb      loc_18002C663
0x18002c7ee  test    ebx, ebx
0x18002c7f0  js      short loc_18002C82C
0x18002c7f2  test    edi, edi
0x18002c7f4  jz      short loc_18002C82C
0x18002c7f6  xor     eax, eax
0x18002c7f8  lea     r8, [rbp+var_20]
0x18002c7fc  mov     [rbp+var_10], rax
0x18002c800  lea     rdx, PKEY_SearchClass
0x18002c807  xorps   xmm0, xmm0
0x18002c80a  mov     eax, 13h
0x18002c80f  movups  [rbp+var_20], xmm0
0x18002c813  mov     word ptr [rbp+var_20], ax
0x18002c817  mov     rcx, r12
0x18002c81a  mov     rax, [r12]
0x18002c81e  mov     dword ptr [rbp+var_20+8], edi
0x18002c821  mov     rax, [rax+30h]
0x18002c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c82a  mov     ebx, eax
0x18002c82c  mov     eax, ebx
0x18002c82e  add     rsp, 50h
0x18002c832  pop     r15
0x18002c834  pop     r14
0x18002c836  pop     r12
0x18002c838  pop     rdi
0x18002c839  pop     rsi
0x18002c83a  pop     rbx
0x18002c83b  pop     rbp
0x18002c83c  retn
```
