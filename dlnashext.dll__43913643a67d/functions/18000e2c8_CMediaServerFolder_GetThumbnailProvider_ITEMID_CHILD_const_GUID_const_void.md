# CMediaServerFolder::_GetThumbnailProvider(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x18000e2c8`
- end: `0x18000e6aa`
- name: `?_GetThumbnailProvider@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `994`
- prototype: `__int64 __fastcall(CMediaServerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e230`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000ab48`
- `0x18000dd80`
- `0x18000e2c8`
- `0x18001dd14`
- `0x1800200e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e5d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e5d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e47c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000e44e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000e44e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18000e59d`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x18000e59d`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CMediaServerFolder::_GetThumbnailProvider(
        CMediaServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  bool v6; // r14
  HRESULT DeviceByUDN; // ebx
  struct Windows::Media::Streaming::IBasicDevice *v8; // rdi
  __int64 (__fastcall *v9)(struct Windows::Media::Streaming::IBasicDevice *, __int64 *); // rbx
  LPVOID v10; // rdi
  unsigned __int64 v11; // r15
  bool v12; // bl
  unsigned int i; // esi
  LPVOID v14; // rcx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v16; // rcx
  LPVOID v17; // rbx
  void *v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID ppv; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-29h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-21h] BYREF
  __int64 v27; // [rsp+50h] [rbp-19h] BYREF
  __int64 v28; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::Media::Streaming::IBasicDevice *v29; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v30; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 *v31; // [rsp+70h] [rbp+7h] BYREF
  LPVOID v32; // [rsp+78h] [rbp+Fh]

  v6 = 0;
  v31 = 0;
  DeviceByUDN = CMediaServerFolder::_GetString(this, a2, &PKEY_PNPX_GlobalIdentity, &v31);
  if ( DeviceByUDN >= 0 )
  {
    v30 = 0;
    if ( v31 )
    {
      DeviceByUDN = Windows::Internal::String::_InitializeHelper(&v30, v31);
      if ( DeviceByUDN >= 0 )
      {
        v29 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v29);
        DeviceByUDN = CMediaServerFolder::_FindDeviceByUDN(this, v30, &v29);
        if ( DeviceByUDN >= 0 )
        {
          v28 = 0;
          v8 = v29;
          v9 = *(__int64 (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, __int64 *))(*(_QWORD *)v29 + 184LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
          DeviceByUDN = v9(v8, &v28);
          if ( DeviceByUDN >= 0 )
          {
            v10 = 0;
            v32 = 0;
            v25 = 0;
            if ( !v28 )
              goto LABEL_42;
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 56LL))(v28, &v25);
            if ( !v25 )
              goto LABEL_42;
            v11 = 0;
            v12 = 0;
            for ( i = 0; i < v25; ++i )
            {
              ppv = 0;
              (*(void (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v28 + 48LL))(v28, i, &ppv);
              v14 = ppv;
              if ( ppv )
              {
                LODWORD(v27) = 0;
                LODWORD(v26) = 0;
                if ( (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 48LL))(ppv, &v27) >= 0
                  && (*(int (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppv + 56LL))(
                       ppv,
                       &v26) >= 0 )
                {
                  string = 0;
                  (*(void (__fastcall **)(LPVOID, HSTRING *))(*(_QWORD *)ppv + 64LL))(ppv, &string);
                  if ( !WindowsIsStringEmpty(string) )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    v6 = CompareStringOrdinal(StringRawBuffer, -1, L"image/png", 9, 1) == 2;
                  }
                  v16 = (unsigned int)v27 * (unsigned __int64)(unsigned int)v26;
                  if ( v16 >= v11 && (!v12 || v16 > v11 && v6) )
                  {
                    v11 = (unsigned int)v27 * (unsigned __int64)(unsigned int)v26;
                    v17 = ppv;
                    if ( v10 != ppv )
                    {
                      if ( ppv )
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
                      v18 = v10;
                      v10 = v17;
                      v32 = v17;
                      if ( v18 )
                        (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
                    }
                    v12 = v6;
                  }
                  Windows::Internal::String::~String((Windows::Internal::String *)&string);
                  v6 = 0;
                }
                v14 = ppv;
              }
              if ( v14 )
              {
                ppv = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
              }
            }
            if ( v10 )
            {
              v26 = 0;
              DeviceByUDN = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v10 + 72LL))(
                              v10,
                              &v26);
              if ( DeviceByUDN >= 0 )
              {
                v27 = 0;
                v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
                v20 = **v26;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
                DeviceByUDN = v20(v19, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v27);
                if ( DeviceByUDN >= 0 )
                {
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&string);
                  DeviceByUDN = CreateStreamOverRandomAccessStream(
                                  v27,
                                  &GUID_0000000c_0000_0000_c000_000000000046,
                                  &string);
                  if ( DeviceByUDN >= 0 )
                  {
                    ppv = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
                    DeviceByUDN = CoCreateInstance(
                                    &GUID_c7657c4a_9f68_40fa_a4df_96bc08eb3551,
                                    0,
                                    1u,
                                    &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
                                    &ppv);
                    if ( DeviceByUDN >= 0 )
                    {
                      DeviceByUDN = (*(__int64 (__fastcall **)(LPVOID, HSTRING, _QWORD))(*(_QWORD *)ppv + 24LL))(
                                      ppv,
                                      string,
                                      0);
                      if ( DeviceByUDN >= 0 )
                        DeviceByUDN = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))ppv)(
                                        ppv,
                                        a3,
                                        a4);
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&string);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
              }
              v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26;
              if ( v26 )
              {
                v26 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
              }
            }
            else
            {
LABEL_42:
              DeviceByUDN = -2147467259;
            }
            if ( v10 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v29);
      }
    }
    else
    {
      DeviceByUDN = -2147467261;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v30);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v31);
  return (unsigned int)DeviceByUDN;
}

```

## disassembly

```asm
0x18000e2c8  mov     [rsp-8+arg_18], r9
0x18000e2cd  push    rbp
0x18000e2ce  push    rbx
0x18000e2cf  push    rsi
0x18000e2d0  push    rdi
0x18000e2d1  push    r12
0x18000e2d3  push    r13
0x18000e2d5  push    r14
0x18000e2d7  push    r15
0x18000e2d9  lea     rbp, [rsp-1Fh]
0x18000e2de  sub     rsp, 88h
0x18000e2e5  mov     r13, r8
0x18000e2e8  mov     rdi, rcx
0x18000e2eb  xor     r14d, r14d
0x18000e2ee  mov     [rbp+57h+var_50], r14
0x18000e2f2  lea     r9, [rbp+57h+var_50]; unsigned __int16 **
0x18000e2f6  lea     r8, PKEY_PNPX_GlobalIdentity; struct _tagpropertykey *
0x18000e2fd  call    ?_GetString@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CMediaServerFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x18000e302  mov     ebx, eax
0x18000e304  test    eax, eax
0x18000e306  js      loc_18000E68B
0x18000e30c  mov     [rbp+57h+var_58], r14
0x18000e310  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x18000e314  test    rdx, rdx
0x18000e317  jz      loc_18000E67C
0x18000e31d  lea     rcx, [rbp+57h+var_58]; this
0x18000e321  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18000e326  mov     ebx, eax
0x18000e328  test    eax, eax
0x18000e32a  js      loc_18000E681
0x18000e330  mov     [rbp+57h+var_60], r14
0x18000e334  lea     rcx, [rbp+57h+var_60]
0x18000e338  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e33d  lea     r8, [rbp+57h+var_60]; struct Windows::Media::Streaming::IBasicDevice **
0x18000e341  mov     rdx, [rbp+57h+var_58]; HSTRING
0x18000e345  mov     rcx, rdi; this
0x18000e348  call    ?_FindDeviceByUDN@CMediaServerFolder@@AEAAJPEAUHSTRING__@@PEAPEAUIBasicDevice@Streaming@Media@Windows@@@Z; CMediaServerFolder::_FindDeviceByUDN(HSTRING__ *,Windows::Media::Streaming::IBasicDevice * *)
0x18000e34d  mov     ebx, eax
0x18000e34f  test    eax, eax
0x18000e351  js      loc_18000E671
0x18000e357  mov     [rbp+57h+var_68], r14
0x18000e35b  mov     rdi, [rbp+57h+var_60]
0x18000e35f  mov     rax, [rdi]
0x18000e362  mov     rbx, [rax+0B8h]
0x18000e369  lea     rcx, [rbp+57h+var_68]
0x18000e36d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e372  lea     rdx, [rbp+57h+var_68]
0x18000e376  mov     rcx, rdi
0x18000e379  mov     rax, rbx
0x18000e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e381  mov     ebx, eax
0x18000e383  test    eax, eax
0x18000e385  js      loc_18000E667
0x18000e38b  mov     edi, r14d
0x18000e38e  mov     [rbp+57h+var_48], r14
0x18000e392  mov     [rbp+57h+var_80], r14d
0x18000e396  mov     rcx, [rbp+57h+var_68]
0x18000e39a  test    rcx, rcx
0x18000e39d  jz      loc_18000E64D
0x18000e3a3  mov     rax, [rcx]
0x18000e3a6  lea     rdx, [rbp+57h+var_80]
0x18000e3aa  mov     rax, [rax+38h]
0x18000e3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b3  mov     eax, [rbp+57h+var_80]
0x18000e3b6  test    eax, eax
0x18000e3b8  jz      loc_18000E64D
0x18000e3be  mov     r15d, r14d
0x18000e3c1  mov     bl, r14b
0x18000e3c4  mov     esi, r14d
0x18000e3c7  lea     r12d, [r14+1]
0x18000e3cb  mov     [rbp+57h+ppv], r14
0x18000e3cf  mov     rcx, [rbp+57h+var_68]
0x18000e3d3  mov     rax, [rcx]
0x18000e3d6  lea     r8, [rbp+57h+ppv]
0x18000e3da  mov     edx, esi
0x18000e3dc  mov     rax, [rax+30h]
0x18000e3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e5  mov     rcx, [rbp+57h+ppv]
0x18000e3e9  test    rcx, rcx
0x18000e3ec  jz      loc_18000E4FA
0x18000e3f2  mov     dword ptr [rbp+57h+var_70], r14d
0x18000e3f6  mov     dword ptr [rbp+57h+var_78], r14d
0x18000e3fa  mov     rax, [rcx]
0x18000e3fd  lea     rdx, [rbp+57h+var_70]
0x18000e401  mov     rax, [rax+30h]
0x18000e405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40a  test    eax, eax
0x18000e40c  js      loc_18000E4F6
0x18000e412  mov     rcx, [rbp+57h+ppv]
0x18000e416  mov     rax, [rcx]
0x18000e419  lea     rdx, [rbp+57h+var_78]
0x18000e41d  mov     rax, [rax+38h]
0x18000e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e426  test    eax, eax
0x18000e428  js      loc_18000E4F6
0x18000e42e  mov     [rbp+57h+string], 0
0x18000e436  mov     rcx, [rbp+57h+ppv]
0x18000e43a  mov     rax, [rcx]
0x18000e43d  lea     rdx, [rbp+57h+string]
0x18000e441  mov     rax, [rax+40h]
0x18000e445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e44a  mov     rcx, [rbp+57h+string]; string
0x18000e44e  call    cs:__imp_WindowsIsStringEmpty
0x18000e454  test    eax, eax
0x18000e456  jnz     short loc_18000E48D
0x18000e458  xor     edx, edx; length
0x18000e45a  mov     rcx, [rbp+57h+string]; string
0x18000e45e  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e464  mov     [rsp+0C0h+bIgnoreCase], r12d; bIgnoreCase
0x18000e469  mov     r9d, 9; cchCount2
0x18000e46f  lea     r8, aImagePng; "image/png"
0x18000e476  or      edx, 0FFFFFFFFh; cchCount1
0x18000e479  mov     rcx, rax; lpString1
0x18000e47c  call    cs:__imp_CompareStringOrdinal
0x18000e482  movzx   r14d, r14b
0x18000e486  cmp     eax, 2
0x18000e489  cmovz   r14d, r12d
0x18000e48d  mov     ecx, dword ptr [rbp+57h+var_78]
0x18000e490  mov     eax, dword ptr [rbp+57h+var_70]
0x18000e493  imul    rcx, rax
0x18000e497  cmp     rcx, r15
0x18000e49a  jb      short loc_18000E4EA
0x18000e49c  test    bl, bl
0x18000e49e  jz      short loc_18000E4AA
0x18000e4a0  cmp     rcx, r15
0x18000e4a3  jbe     short loc_18000E4EA
0x18000e4a5  test    r14b, r14b
0x18000e4a8  jz      short loc_18000E4EA
0x18000e4aa  mov     r15, rcx
0x18000e4ad  mov     rbx, [rbp+57h+ppv]
0x18000e4b1  cmp     rdi, rbx
0x18000e4b4  jz      short loc_18000E4E7
0x18000e4b6  test    rbx, rbx
0x18000e4b9  jz      short loc_18000E4CB
0x18000e4bb  mov     rax, [rbx]
0x18000e4be  mov     rcx, rbx
0x18000e4c1  mov     rax, [rax+8]
0x18000e4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ca  nop
0x18000e4cb  mov     rcx, rdi
0x18000e4ce  mov     rdi, rbx
0x18000e4d1  mov     [rbp+57h+var_48], rbx
0x18000e4d5  test    rcx, rcx
0x18000e4d8  jz      short loc_18000E4E7
0x18000e4da  mov     rax, [rcx]
0x18000e4dd  mov     rax, [rax+10h]
0x18000e4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e6  nop
0x18000e4e7  mov     bl, r14b
0x18000e4ea  lea     rcx, [rbp+57h+string]; this
0x18000e4ee  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000e4f3  xor     r14d, r14d
0x18000e4f6  mov     rcx, [rbp+57h+ppv]
0x18000e4fa  test    rcx, rcx
0x18000e4fd  jz      short loc_18000E510
0x18000e4ff  mov     [rbp+57h+ppv], r14
0x18000e503  mov     rax, [rcx]
0x18000e506  mov     rax, [rax+10h]
0x18000e50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50f  nop
0x18000e510  add     esi, r12d
0x18000e513  cmp     esi, [rbp+57h+var_80]
0x18000e516  jb      loc_18000E3CB
0x18000e51c  test    rdi, rdi
0x18000e51f  mov     r12, [rbp+57h+arg_18]
0x18000e523  jz      loc_18000E64D
0x18000e529  mov     [rbp+57h+var_78], r14
0x18000e52d  mov     rax, [rdi]
0x18000e530  lea     rdx, [rbp+57h+var_78]
0x18000e534  mov     rcx, rdi
0x18000e537  mov     rax, [rax+48h]
0x18000e53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e540  mov     ebx, eax
0x18000e542  test    eax, eax
0x18000e544  js      loc_18000E631
0x18000e54a  mov     [rbp+57h+var_70], r14
0x18000e54e  mov     rbx, [rbp+57h+var_78]
0x18000e552  mov     rax, [rbx]
0x18000e555  mov     rsi, [rax]
0x18000e558  lea     rcx, [rbp+57h+var_70]
0x18000e55c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e561  lea     r8, [rbp+57h+var_70]
0x18000e565  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18000e56c  mov     rcx, rbx
0x18000e56f  mov     rax, rsi
0x18000e572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e577  mov     ebx, eax
0x18000e579  test    eax, eax
0x18000e57b  js      loc_18000E627
0x18000e581  mov     [rbp+57h+string], r14
0x18000e585  lea     rcx, [rbp+57h+string]
0x18000e589  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e58e  lea     r8, [rbp+57h+string]
0x18000e592  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000e599  mov     rcx, [rbp+57h+var_70]
0x18000e59d  call    cs:__imp_CreateStreamOverRandomAccessStream
0x18000e5a3  mov     ebx, eax
0x18000e5a5  test    eax, eax
0x18000e5a7  js      short loc_18000E61D
0x18000e5a9  mov     [rbp+57h+ppv], r14
0x18000e5ad  lea     rcx, [rbp+57h+ppv]
0x18000e5b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e5b6  lea     rax, [rbp+57h+ppv]
0x18000e5ba  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax; ppv
0x18000e5bf  lea     r9, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f; riid
0x18000e5c6  xor     edx, edx; pUnkOuter
0x18000e5c8  lea     r8d, [rdx+1]; dwClsContext
0x18000e5cc  lea     rcx, _GUID_c7657c4a_9f68_40fa_a4df_96bc08eb3551; rclsid
0x18000e5d3  call    cs:__imp_CoCreateInstance
0x18000e5d9  mov     ebx, eax
0x18000e5db  test    eax, eax
0x18000e5dd  js      short loc_18000E613
0x18000e5df  mov     rcx, [rbp+57h+ppv]
0x18000e5e3  mov     rax, [rcx]
0x18000e5e6  xor     r8d, r8d
0x18000e5e9  mov     rdx, [rbp+57h+string]
0x18000e5ed  mov     rax, [rax+18h]
0x18000e5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f6  mov     ebx, eax
0x18000e5f8  test    eax, eax
0x18000e5fa  js      short loc_18000E613
0x18000e5fc  mov     rcx, [rbp+57h+ppv]
0x18000e600  mov     rax, [rcx]
0x18000e603  mov     r8, r12
0x18000e606  mov     rdx, r13
0x18000e609  mov     rax, [rax]
0x18000e60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e611  mov     ebx, eax
0x18000e613  lea     rcx, [rbp+57h+ppv]
0x18000e617  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e61c  nop
0x18000e61d  lea     rcx, [rbp+57h+string]
0x18000e621  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e626  nop
0x18000e627  lea     rcx, [rbp+57h+var_70]
0x18000e62b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e630  nop
0x18000e631  mov     rcx, [rbp+57h+var_78]
0x18000e635  test    rcx, rcx
0x18000e638  jz      short loc_18000E64B
0x18000e63a  mov     [rbp+57h+var_78], r14
0x18000e63e  mov     rax, [rcx]
0x18000e641  mov     rax, [rax+10h]
0x18000e645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64a  nop
0x18000e64b  jmp     short loc_18000E652
0x18000e64d  mov     ebx, 80004005h
0x18000e652  test    rdi, rdi
0x18000e655  jz      short loc_18000E667
0x18000e657  mov     rax, [rdi]
0x18000e65a  mov     rcx, rdi
0x18000e65d  mov     rax, [rax+10h]
0x18000e661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e666  nop
0x18000e667  lea     rcx, [rbp+57h+var_68]
0x18000e66b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e670  nop
0x18000e671  lea     rcx, [rbp+57h+var_60]
0x18000e675  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e67a  jmp     short loc_18000E681
0x18000e67c  mov     ebx, 80004003h
0x18000e681  lea     rcx, [rbp+57h+var_58]; this
0x18000e685  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18000e68a  nop
0x18000e68b  lea     rcx, [rbp+57h+var_50]
0x18000e68f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000e694  mov     eax, ebx
0x18000e696  add     rsp, 88h
0x18000e69d  pop     r15
0x18000e69f  pop     r14
0x18000e6a1  pop     r13
0x18000e6a3  pop     r12
0x18000e6a5  pop     rdi
0x18000e6a6  pop     rsi
0x18000e6a7  pop     rbx
0x18000e6a8  pop     rbp
0x18000e6a9  retn
```
