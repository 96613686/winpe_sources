# CCdsItemSorterAndPropertyMapper::MapContainer(Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IContentDirectoryContainer>,uchar,IPropertyStore * *)

- ea: `0x1800270b0`
- end: `0x180027259`
- name: `?MapContainer@CCdsItemSorterAndPropertyMapper@@QEAAJV?$ComPtr@UIContentDirectoryContainer@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@EPEAPEAUIPropertyStore@@@Z`
- size: `425`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001dd80`
- `0x180027d0c`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x180014a00`
- `0x180019b84`
- `0x1800270b0`
- `0x18002d49c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800271a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800271a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCdsItemSorterAndPropertyMapper::MapContainer(__int64 *a1, __int64 *a2, char a3, _QWORD *a4)
{
  void *v7; // r14
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 **); // rbx
  __int64 v10; // rcx
  int v11; // ebx
  void *v13; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  __int64 *v17; // [rsp+80h] [rbp+30h] BYREF
  __int64 *v18; // [rsp+88h] [rbp+38h]

  v18 = a2;
  v17 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids);
  v7 = 0;
  v13 = 0;
  v17 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))*a2;
  v9 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))*a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v17);
  v11 = v9(v8, &GUID_7855c6f6_b22c_4c2d_83dd_c45004979937, &v17);
  if ( v11 >= 0 )
  {
    v11 = CCdsObjectMapper::MapContentDirectoryObject(v10, v17, 2 - (unsigned int)(a3 != 0), &v13);
    v7 = v13;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v17);
  string = 0;
  if ( v11 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a2 + 48LL))(*a2, &string) < 0
      || (v15 = 0,
          v16 = 0,
          LOWORD(v15) = 31,
          *((_QWORD *)&v15 + 1) = WindowsGetStringRawBuffer(string, 0),
          v11 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v7 + 48LL))(
                  v7,
                  &PKEY_ItemUrl,
                  &v15),
          v11 >= 0) )
    {
      v13 = 0;
      *a4 = v7;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids,
      (unsigned int)v11);
  }
  Windows::Internal::String::~String(&string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(a2);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800270b0  mov     rax, rsp
0x1800270b3  mov     [rax+18h], rbx
0x1800270b7  mov     [rax+20h], rsi
0x1800270bb  mov     [rax+10h], rdx
0x1800270bf  mov     [rax+8], rcx
0x1800270c3  push    rbp
0x1800270c4  push    rdi
0x1800270c5  push    r12
0x1800270c7  push    r14
0x1800270c9  push    r15
0x1800270cb  mov     rbp, rsp
0x1800270ce  sub     rsp, 50h
0x1800270d2  mov     r12, r9
0x1800270d5  mov     r15b, r8b
0x1800270d8  mov     rsi, rdx
0x1800270db  lea     rax, WPP_GLOBAL_Control
0x1800270e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270e9  cmp     rcx, rax
0x1800270ec  jz      short loc_180027109
0x1800270ee  test    byte ptr [rcx+1Ch], 2
0x1800270f2  jz      short loc_180027109
0x1800270f4  mov     edx, 13h
0x1800270f9  lea     r8, WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids
0x180027100  mov     rcx, [rcx+10h]
0x180027104  call    WPP_SF_
0x180027109  xor     r14d, r14d
0x18002710c  mov     [rbp+var_30], r14
0x180027110  mov     [rbp+arg_0], r14
0x180027114  mov     rdi, [rsi]
0x180027117  mov     rax, [rdi]
0x18002711a  mov     rbx, [rax]
0x18002711d  lea     rcx, [rbp+arg_0]
0x180027121  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027126  lea     r8, [rbp+arg_0]
0x18002712a  lea     rdx, _GUID_7855c6f6_b22c_4c2d_83dd_c45004979937
0x180027131  mov     rcx, rdi
0x180027134  mov     rax, rbx
0x180027137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002713c  mov     ebx, eax
0x18002713e  test    eax, eax
0x180027140  js      short loc_18002715F
0x180027142  neg     r15b
0x180027145  sbb     r8d, r8d
0x180027148  add     r8d, 2
0x18002714c  lea     r9, [rbp+var_30]
0x180027150  mov     rdx, [rbp+arg_0]
0x180027154  call    ?MapContentDirectoryObject@CCdsObjectMapper@@QEAAJPEAUIContentDirectoryObject@Internal@Streaming@Media@Windows@@W4_CDS_TYPE@@PEAPEAUIPropertyStore@@@Z; CCdsObjectMapper::MapContentDirectoryObject(Windows::Media::Streaming::Internal::IContentDirectoryObject *,_CDS_TYPE,IPropertyStore * *)
0x180027159  mov     ebx, eax
0x18002715b  mov     r14, [rbp+var_30]
0x18002715f  lea     rcx, [rbp+arg_0]
0x180027163  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027168  mov     [rbp+string], 0
0x180027170  test    ebx, ebx
0x180027172  js      short loc_1800271DD
0x180027174  mov     rcx, [rsi]
0x180027177  mov     rax, [rcx]
0x18002717a  lea     rdx, [rbp+string]
0x18002717e  mov     rax, [rax+30h]
0x180027182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027187  test    eax, eax
0x180027189  js      short loc_1800271D1
0x18002718b  xorps   xmm0, xmm0
0x18002718e  xor     eax, eax
0x180027190  movups  [rbp+var_20], xmm0
0x180027194  mov     [rbp+var_10], rax
0x180027198  mov     eax, 1Fh
0x18002719d  mov     word ptr [rbp+var_20], ax
0x1800271a1  xor     edx, edx; length
0x1800271a3  mov     rcx, [rbp+string]; string
0x1800271a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800271ad  mov     qword ptr [rbp+var_20+8], rax
0x1800271b1  mov     rax, [r14]
0x1800271b4  lea     r8, [rbp+var_20]
0x1800271b8  lea     rdx, PKEY_ItemUrl
0x1800271bf  mov     rcx, r14
0x1800271c2  mov     rax, [rax+30h]
0x1800271c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271cb  mov     ebx, eax
0x1800271cd  test    eax, eax
0x1800271cf  js      short loc_1800271DD
0x1800271d1  mov     [rbp+var_30], 0
0x1800271d9  mov     [r12], r14
0x1800271dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271e4  lea     rax, WPP_GLOBAL_Control
0x1800271eb  cmp     rcx, rax
0x1800271ee  jz      short loc_180027222
0x1800271f0  test    byte ptr [rcx+1Ch], 2
0x1800271f4  jz      short loc_180027222
0x1800271f6  mov     edx, ebx
0x1800271f8  sar     edx, 1Fh
0x1800271fb  and     edx, 0FFFFFFFDh
0x1800271fe  add     edx, 5
0x180027201  movzx   eax, byte ptr [rcx+19h]
0x180027205  cmp     eax, edx
0x180027207  jb      short loc_180027222
0x180027209  mov     edx, 14h
0x18002720e  mov     r9d, ebx
0x180027211  lea     r8, WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids
0x180027218  mov     rcx, [rcx+10h]
0x18002721c  call    WPP_SF_d
0x180027221  nop
0x180027222  lea     rcx, [rbp+string]; this
0x180027226  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002722b  nop
0x18002722c  lea     rcx, [rbp+var_30]
0x180027230  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027235  nop
0x180027236  mov     rcx, rsi
0x180027239  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002723e  mov     eax, ebx
0x180027240  lea     r11, [rsp+50h+var_s0]
0x180027245  mov     rbx, [r11+40h]
0x180027249  mov     rsi, [r11+48h]
0x18002724d  mov     rsp, r11
0x180027250  pop     r15
0x180027252  pop     r14
0x180027254  pop     r12
0x180027256  pop     rdi
0x180027257  pop     rbp
0x180027258  retn
```
