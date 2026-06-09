# CMediaServerFolder::CreateMediaServerPropertyStore(Windows::Media::Streaming::IBasicDevice *,IPropertyStore * *)

- ea: `0x180003890`
- end: `0x180003cb6`
- name: `?CreateMediaServerPropertyStore@CMediaServerFolder@@SAJPEAUIBasicDevice@Streaming@Media@Windows@@PEAPEAUIPropertyStore@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(struct Windows::Media::Streaming::IBasicDevice *, struct IPropertyStore **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003530`
- `0x180003cbc`

## callees

- `0x180001710`
- `0x180003890`
- `0x180011930`
- `0x180035010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800038d6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800038d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000395e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000399f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000395e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000399f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003b17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003b17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180003991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180003991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003b38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003ba4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003b38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003ba4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMediaServerFolder::CreateMediaServerPropertyStore(
        struct Windows::Media::Streaming::IBasicDevice *a1,
        struct IPropertyStore **a2)
{
  HRESULT v4; // esi
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, const PROPERTYKEY *, __int128 *); // rbx
  PCWSTR StringRawBuffer; // rax
  void *v8; // rdi
  __int64 (__fastcall *v9)(void *, const PROPERTYKEY *, __int128 *); // rbx
  PCWSTR v10; // rax
  UINT32 StringLen; // ebx
  PCWSTR v12; // rax
  unsigned __int64 v13; // rcx
  unsigned int v14; // r9d
  unsigned int v15; // ebx
  __int64 v16; // rax
  int (__fastcall *v17)(struct Windows::Media::Streaming::IBasicDevice *, GUID *, HSTRING *); // rbx
  __int64 v18; // rax
  int (__fastcall *v19)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *); // rbx
  void *v20; // rdi
  void (__fastcall *v21)(void *, const PROPERTYKEY *, __int16 *); // rbx
  PCWSTR v22; // rax
  int (__fastcall *v23)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *); // rbx
  void *v24; // rdi
  void (__fastcall *v25)(void *, const PROPERTYKEY *, __int16 *); // rbx
  PCWSTR v26; // rax
  int (__fastcall *v27)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *); // rbx
  void *v28; // rdi
  void (__fastcall *v29)(void *, const PROPERTYKEY *, __int16 *); // rbx
  PCWSTR v30; // rax
  void *v31; // rdi
  __int64 (__fastcall *v32)(void *, const PROPERTYKEY *, __int16 *); // rbx
  PCWSTR v33; // rax
  void *v34; // rcx
  HSTRING v36; // [rsp+20h] [rbp-50h] BYREF
  void *ppv; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  __int16 v39; // [rsp+38h] [rbp-38h] BYREF
  _OWORD *v40; // [rsp+40h] [rbp-30h]
  __int128 v41; // [rsp+50h] [rbp-20h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v4 < 0 )
    goto LABEL_30;
  string = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 80LL))(
         a1,
         &string);
  if ( v4 >= 0 )
  {
    v5 = ppv;
    v6 = *(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LOWORD(v41) = 31;
    *((_QWORD *)&v41 + 1) = StringRawBuffer;
    v4 = v6(v5, &PKEY_PNPX_GlobalIdentity, &v41);
    if ( v4 >= 0 )
    {
      v8 = ppv;
      v9 = *(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL);
      v10 = WindowsGetStringRawBuffer(string, 0);
      LOWORD(v41) = 31;
      *((_QWORD *)&v41 + 1) = v10;
      v4 = v9(v8, &PKEY_ParsingName, &v41);
      if ( v4 >= 0 )
      {
        StringLen = WindowsGetStringLen(string);
        v12 = WindowsGetStringRawBuffer(string, 0);
        v13 = 0xDCEB28CE1A3D34F1uLL;
        v14 = 0;
        v15 = 2 * StringLen;
        if ( v15 )
        {
          do
            v13 ^= (v13 >> 2) + 2080 * v13 + *((unsigned __int8 *)v12 + v14++);
          while ( v14 < v15 );
        }
        v16 = *(_QWORD *)ppv;
        LOWORD(v41) = 21;
        *((_QWORD *)&v41 + 1) = v13;
        v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(v16 + 48))(
               ppv,
               &PKEY_ThumbnailCacheId,
               &v41);
        if ( v4 >= 0 )
        {
          v36 = 0;
          v17 = **(int (__fastcall ***)(struct Windows::Media::Streaming::IBasicDevice *, GUID *, HSTRING *))a1;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v36);
          if ( v17(a1, &GUID_27a9ba24_9a99_4f80_979b_4e22d449be11, &v36) >= 0 )
          {
            v41 = 0;
            if ( (*(int (__fastcall **)(HSTRING, __int128 *))(*(_QWORD *)v36 + 64LL))(v36, &v41) >= 0 )
            {
              v18 = *(_QWORD *)ppv;
              v39 = 72;
              v40 = &v41;
              (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(v18 + 48))(
                ppv,
                &PKEY_Device_ContainerId,
                &v39);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v36);
          v36 = 0;
          v19 = *(int (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 64LL);
          WindowsDeleteString(0);
          v36 = 0;
          if ( v19(a1, &v36) >= 0 && !WindowsIsStringEmpty(v36) )
          {
            v20 = ppv;
            v21 = *(void (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)ppv + 48LL);
            v22 = WindowsGetStringRawBuffer(v36, 0);
            v39 = 31;
            v40 = v22;
            v21(v20, &PKEY_Devices_Manufacturer, &v39);
          }
          v23 = *(int (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 88LL);
          WindowsDeleteString(v36);
          v36 = 0;
          if ( v23(a1, &v36) >= 0 && !WindowsIsStringEmpty(v36) )
          {
            v24 = ppv;
            v25 = *(void (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)ppv + 48LL);
            v26 = WindowsGetStringRawBuffer(v36, 0);
            v39 = 31;
            v40 = v26;
            v25(v24, &PKEY_Devices_ModelName, &v39);
          }
          v27 = *(int (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 96LL);
          WindowsDeleteString(v36);
          v36 = 0;
          if ( v27(a1, &v36) >= 0 && !WindowsIsStringEmpty(v36) )
          {
            v28 = ppv;
            v29 = *(void (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)ppv + 48LL);
            v30 = WindowsGetStringRawBuffer(v36, 0);
            v39 = 31;
            v40 = v30;
            v29(v28, &PKEY_Devices_ModelNumber, &v39);
          }
          if ( v36 )
            WindowsDeleteString(v36);
          v36 = 0;
          if ( (*(int (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)a1 + 48LL))(
                 a1,
                 &v36) >= 0 )
          {
            v31 = ppv;
            v32 = *(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)ppv + 48LL);
            v33 = WindowsGetStringRawBuffer(v36, 0);
            v39 = 31;
            v40 = v33;
            v4 = v32(v31, &PKEY_DeviceDisplay_FriendlyName, &v39);
          }
          if ( v36 )
            WindowsDeleteString(v36);
        }
      }
    }
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v4 < 0 )
  {
LABEL_30:
    v34 = ppv;
  }
  else
  {
    v34 = 0;
    *a2 = (struct IPropertyStore *)ppv;
  }
  if ( v34 )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003890  mov     [rsp-38h+arg_10], rbx
0x180003895  push    rbp
0x180003896  push    rsi
0x180003897  push    rdi
0x180003898  push    r12
0x18000389a  push    r13
0x18000389c  push    r14
0x18000389e  push    r15
0x1800038a0  mov     rbp, rsp
0x1800038a3  sub     rsp, 70h
0x1800038a7  mov     rax, cs:__security_cookie
0x1800038ae  xor     rax, rsp
0x1800038b1  mov     [rbp+var_8], rax
0x1800038b5  mov     r15, rdx
0x1800038b8  mov     r14, rcx
0x1800038bb  xor     r12d, r12d
0x1800038be  mov     [rbp+ppv], r12
0x1800038c2  lea     rcx, [rbp+ppv]
0x1800038c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800038cb  lea     rdx, [rbp+ppv]; ppv
0x1800038cf  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800038d6  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800038dc  mov     esi, eax
0x1800038de  test    eax, eax
0x1800038e0  js      loc_180003C76
0x1800038e6  mov     [rbp+string], r12
0x1800038ea  mov     rax, [r14]
0x1800038ed  lea     rdx, [rbp+string]
0x1800038f1  mov     rcx, r14
0x1800038f4  mov     rax, [rax+50h]
0x1800038f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fd  mov     esi, eax
0x1800038ff  test    eax, eax
0x180003901  js      loc_180003C57
0x180003907  mov     rdi, [rbp+ppv]
0x18000390b  mov     rax, [rdi]
0x18000390e  mov     rbx, [rax+30h]
0x180003912  xor     edx, edx; length
0x180003914  mov     rcx, [rbp+string]; string
0x180003918  call    cs:__imp_WindowsGetStringRawBuffer
0x18000391e  mov     r13d, 1Fh
0x180003924  mov     word ptr [rbp+var_20], r13w
0x180003929  mov     qword ptr [rbp+var_20+8], rax
0x18000392d  lea     r8, [rbp+var_20]
0x180003931  lea     rdx, PKEY_PNPX_GlobalIdentity
0x180003938  mov     rcx, rdi
0x18000393b  mov     rax, rbx
0x18000393e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003943  mov     esi, eax
0x180003945  test    eax, eax
0x180003947  js      loc_180003C57
0x18000394d  mov     rdi, [rbp+ppv]
0x180003951  mov     rax, [rdi]
0x180003954  mov     rbx, [rax+30h]
0x180003958  xor     edx, edx; length
0x18000395a  mov     rcx, [rbp+string]; string
0x18000395e  call    cs:__imp_WindowsGetStringRawBuffer
0x180003964  mov     word ptr [rbp+var_20], r13w
0x180003969  mov     qword ptr [rbp+var_20+8], rax
0x18000396d  lea     r8, [rbp+var_20]
0x180003971  lea     rdx, PKEY_ParsingName
0x180003978  mov     rcx, rdi
0x18000397b  mov     rax, rbx
0x18000397e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003983  mov     esi, eax
0x180003985  test    eax, eax
0x180003987  js      loc_180003C57
0x18000398d  mov     rcx, [rbp+string]; string
0x180003991  call    cs:__imp_WindowsGetStringLen
0x180003997  mov     ebx, eax
0x180003999  xor     edx, edx; length
0x18000399b  mov     rcx, [rbp+string]; string
0x18000399f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800039a5  mov     rcx, 0DCEB28CE1A3D34F1h
0x1800039af  mov     r9d, r12d
0x1800039b2  add     ebx, ebx
0x1800039b4  jz      short loc_1800039E7
0x1800039b6  nop     word ptr [rax+rax+00000000h]
0x1800039c0  mov     edx, r9d
0x1800039c3  movzx   r8d, byte ptr [rdx+rax]
0x1800039c8  imul    rdx, rcx, 820h
0x1800039cf  add     r8, rdx
0x1800039d2  mov     rdx, rcx
0x1800039d5  shr     rdx, 2
0x1800039d9  add     r8, rdx
0x1800039dc  xor     rcx, r8
0x1800039df  inc     r9d
0x1800039e2  cmp     r9d, ebx
0x1800039e5  jb      short loc_1800039C0
0x1800039e7  mov     r9, [rbp+ppv]
0x1800039eb  mov     rax, [r9]
0x1800039ee  mov     edx, 15h
0x1800039f3  mov     word ptr [rbp+var_20], dx
0x1800039f7  mov     qword ptr [rbp+var_20+8], rcx
0x1800039fb  lea     r8, [rbp+var_20]
0x1800039ff  lea     rdx, PKEY_ThumbnailCacheId
0x180003a06  mov     rcx, r9
0x180003a09  mov     rax, [rax+30h]
0x180003a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a12  mov     esi, eax
0x180003a14  test    eax, eax
0x180003a16  js      loc_180003C57
0x180003a1c  mov     [rbp+var_50], r12
0x180003a20  mov     rax, [r14]
0x180003a23  mov     rbx, [rax]
0x180003a26  lea     rcx, [rbp+var_50]
0x180003a2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003a2f  lea     r8, [rbp+var_50]
0x180003a33  lea     rdx, _GUID_27a9ba24_9a99_4f80_979b_4e22d449be11
0x180003a3a  mov     rcx, r14
0x180003a3d  mov     rax, rbx
0x180003a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a45  test    eax, eax
0x180003a47  js      short loc_180003A95
0x180003a49  xorps   xmm0, xmm0
0x180003a4c  movups  [rbp+var_20], xmm0
0x180003a50  mov     rcx, [rbp+var_50]
0x180003a54  mov     rax, [rcx]
0x180003a57  lea     rdx, [rbp+var_20]
0x180003a5b  mov     rax, [rax+40h]
0x180003a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a64  test    eax, eax
0x180003a66  js      short loc_180003A95
0x180003a68  mov     rcx, [rbp+ppv]
0x180003a6c  mov     rax, [rcx]
0x180003a6f  mov     edx, 48h ; 'H'
0x180003a74  mov     [rbp+var_38], dx
0x180003a78  lea     rdx, [rbp+var_20]
0x180003a7c  mov     [rbp+var_30], rdx
0x180003a80  lea     r8, [rbp+var_38]
0x180003a84  lea     rdx, PKEY_Device_ContainerId
0x180003a8b  mov     rax, [rax+30h]
0x180003a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a94  nop
0x180003a95  lea     rcx, [rbp+var_50]
0x180003a99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003a9e  mov     [rbp+var_50], r12
0x180003aa2  mov     rax, [r14]
0x180003aa5  mov     rbx, [rax+40h]
0x180003aa9  xor     ecx, ecx; string
0x180003aab  call    cs:__imp_WindowsDeleteString
0x180003ab1  mov     [rbp+var_50], r12
0x180003ab5  lea     rdx, [rbp+var_50]
0x180003ab9  mov     rcx, r14
0x180003abc  mov     rax, rbx
0x180003abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac4  test    eax, eax
0x180003ac6  js      short loc_180003B0C
0x180003ac8  mov     rcx, [rbp+var_50]; string
0x180003acc  call    cs:__imp_WindowsIsStringEmpty
0x180003ad2  test    eax, eax
0x180003ad4  jnz     short loc_180003B0C
0x180003ad6  mov     rdi, [rbp+ppv]
0x180003ada  mov     rax, [rdi]
0x180003add  mov     rbx, [rax+30h]
0x180003ae1  xor     edx, edx; length
0x180003ae3  mov     rcx, [rbp+var_50]; string
0x180003ae7  call    cs:__imp_WindowsGetStringRawBuffer
0x180003aed  mov     [rbp+var_38], r13w
0x180003af2  mov     [rbp+var_30], rax
0x180003af6  lea     r8, [rbp+var_38]
0x180003afa  lea     rdx, PKEY_Devices_Manufacturer
0x180003b01  mov     rcx, rdi
0x180003b04  mov     rax, rbx
0x180003b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0c  mov     rax, [r14]
0x180003b0f  mov     rbx, [rax+58h]
0x180003b13  mov     rcx, [rbp+var_50]; string
0x180003b17  call    cs:__imp_WindowsDeleteString
0x180003b1d  mov     [rbp+var_50], r12
0x180003b21  lea     rdx, [rbp+var_50]
0x180003b25  mov     rcx, r14
0x180003b28  mov     rax, rbx
0x180003b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b30  test    eax, eax
0x180003b32  js      short loc_180003B78
0x180003b34  mov     rcx, [rbp+var_50]; string
0x180003b38  call    cs:__imp_WindowsIsStringEmpty
0x180003b3e  test    eax, eax
0x180003b40  jnz     short loc_180003B78
0x180003b42  mov     rdi, [rbp+ppv]
0x180003b46  mov     rax, [rdi]
0x180003b49  mov     rbx, [rax+30h]
0x180003b4d  xor     edx, edx; length
0x180003b4f  mov     rcx, [rbp+var_50]; string
0x180003b53  call    cs:__imp_WindowsGetStringRawBuffer
0x180003b59  mov     [rbp+var_38], r13w
0x180003b5e  mov     [rbp+var_30], rax
0x180003b62  lea     r8, [rbp+var_38]
0x180003b66  lea     rdx, PKEY_Devices_ModelName
0x180003b6d  mov     rcx, rdi
0x180003b70  mov     rax, rbx
0x180003b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b78  mov     rax, [r14]
0x180003b7b  mov     rbx, [rax+60h]
0x180003b7f  mov     rcx, [rbp+var_50]; string
0x180003b83  call    cs:__imp_WindowsDeleteString
0x180003b89  mov     [rbp+var_50], r12
0x180003b8d  lea     rdx, [rbp+var_50]
0x180003b91  mov     rcx, r14
0x180003b94  mov     rax, rbx
0x180003b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9c  test    eax, eax
0x180003b9e  js      short loc_180003BE5
0x180003ba0  mov     rcx, [rbp+var_50]; string
0x180003ba4  call    cs:__imp_WindowsIsStringEmpty
0x180003baa  test    eax, eax
0x180003bac  jnz     short loc_180003BE5
0x180003bae  mov     rdi, [rbp+ppv]
0x180003bb2  mov     rax, [rdi]
0x180003bb5  mov     rbx, [rax+30h]
0x180003bb9  xor     edx, edx; length
0x180003bbb  mov     rcx, [rbp+var_50]; string
0x180003bbf  call    cs:__imp_WindowsGetStringRawBuffer
0x180003bc5  mov     [rbp+var_38], r13w
0x180003bca  mov     [rbp+var_30], rax
0x180003bce  lea     r8, [rbp+var_38]
0x180003bd2  lea     rdx, PKEY_Devices_ModelNumber
0x180003bd9  mov     rcx, rdi
0x180003bdc  mov     rax, rbx
0x180003bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be4  nop
0x180003be5  mov     rcx, [rbp+var_50]; string
0x180003be9  test    rcx, rcx
0x180003bec  jz      short loc_180003BF4
0x180003bee  call    cs:__imp_WindowsDeleteString
0x180003bf4  mov     [rbp+var_50], r12
0x180003bf8  mov     rax, [r14]
0x180003bfb  lea     rdx, [rbp+var_50]
0x180003bff  mov     rcx, r14
0x180003c02  mov     rax, [rax+30h]
0x180003c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0b  test    eax, eax
0x180003c0d  js      short loc_180003C47
0x180003c0f  mov     rdi, [rbp+ppv]
0x180003c13  mov     rax, [rdi]
0x180003c16  mov     rbx, [rax+30h]
0x180003c1a  xor     edx, edx; length
0x180003c1c  mov     rcx, [rbp+var_50]; string
0x180003c20  call    cs:__imp_WindowsGetStringRawBuffer
0x180003c26  mov     [rbp+var_38], r13w
0x180003c2b  mov     [rbp+var_30], rax
0x180003c2f  lea     r8, [rbp+var_38]
0x180003c33  lea     rdx, PKEY_DeviceDisplay_FriendlyName
0x180003c3a  mov     rcx, rdi
0x180003c3d  mov     rax, rbx
0x180003c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c45  mov     esi, eax
0x180003c47  mov     rcx, [rbp+var_50]; string
0x180003c4b  test    rcx, rcx
0x180003c4e  jz      short loc_180003C57
0x180003c50  call    cs:__imp_WindowsDeleteString
0x180003c56  nop
0x180003c57  mov     rcx, [rbp+string]; string
0x180003c5b  test    rcx, rcx
0x180003c5e  jz      short loc_180003C66
0x180003c60  call    cs:__imp_WindowsDeleteString
0x180003c66  test    esi, esi
0x180003c68  js      short loc_180003C76
0x180003c6a  mov     rax, [rbp+ppv]
0x180003c6e  mov     rcx, r12
0x180003c71  mov     [r15], rax
0x180003c74  jmp     short loc_180003C7A
0x180003c76  mov     rcx, [rbp+ppv]
0x180003c7a  test    rcx, rcx
0x180003c7d  jz      short loc_180003C90
0x180003c7f  mov     [rbp+ppv], r12
0x180003c83  mov     rax, [rcx]
0x180003c86  mov     rax, [rax+10h]
0x180003c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8f  nop
0x180003c90  mov     eax, esi
0x180003c92  mov     rcx, [rbp+var_8]
0x180003c96  xor     rcx, rsp; StackCookie
0x180003c99  call    __security_check_cookie
0x180003c9e  mov     rbx, [rsp+70h+arg_10]
0x180003ca6  add     rsp, 70h
0x180003caa  pop     r15
0x180003cac  pop     r14
0x180003cae  pop     r13
0x180003cb0  pop     r12
0x180003cb2  pop     rdi
0x180003cb3  pop     rsi
0x180003cb4  pop     rbp
0x180003cb5  retn
```
