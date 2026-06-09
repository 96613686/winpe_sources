# CMediaServerFolder::FindDeviceByUDN(CTrackedMediaServerCollection *,HSTRING__ *,Windows::Media::Streaming::IBasicDevice * *)

- ea: `0x18001eff0`
- end: `0x18001f1f7`
- name: `?FindDeviceByUDN@CMediaServerFolder@@SAJPEAVCTrackedMediaServerCollection@@PEAUHSTRING__@@PEAPEAUIBasicDevice@Streaming@Media@Windows@@@Z`
- size: `519`
- prototype: `static int(struct CTrackedMediaServerCollection *, HSTRING, struct Windows::Media::Streaming::IBasicDevice **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800195d4`
- `0x1800200e8`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000dcf8`
- `0x1800198d4`
- `0x180019b84`
- `0x18001eff0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f136`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f0ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f1ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f0ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f1ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMediaServerFolder::FindDeviceByUDN(
        struct CTrackedMediaServerCollection *a1,
        HSTRING a2,
        struct Windows::Media::Streaming::IBasicDevice **a3)
{
  int MediaServers; // ebx
  __int64 v6; // r14
  unsigned int i; // esi
  int (__fastcall *v8)(__int64, _QWORD, struct Windows::Media::Streaming::IBasicDevice **); // rbx
  const WCHAR *StringRawBuffer; // r12
  const WCHAR *v10; // rax
  struct Windows::Media::Streaming::IBasicDevice *v11; // rax
  PCWSTR v12; // rax
  UINT32 v14; // [rsp+30h] [rbp-20h] BYREF
  struct Windows::Media::Streaming::IBasicDevice *v15; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+40h] BYREF
  UINT32 length; // [rsp+98h] [rbp+48h] BYREF

  if ( a3 )
    *a3 = 0;
  v17 = 0;
  MediaServers = CTrackedMediaServerCollection::GetMediaServers(a1, &v17);
  if ( MediaServers >= 0 )
  {
    v18 = 0;
    v6 = v17;
    MediaServers = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 56LL))(v17, &v18);
    if ( MediaServers >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids, v18);
      }
      for ( i = 0; i < v18; ++i )
      {
        v15 = 0;
        v8 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::Media::Streaming::IBasicDevice **))(*(_QWORD *)v6 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
        if ( v8(v6, i, &v15) >= 0 )
        {
          string = 0;
          MediaServers = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::IBasicDevice *, HSTRING *))(*(_QWORD *)v15 + 80LL))(
                           v15,
                           &string);
          if ( MediaServers >= 0 )
          {
            length = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
            v14 = 0;
            v10 = WindowsGetStringRawBuffer(a2, &v14);
            if ( length == v14 && CompareStringOrdinal(StringRawBuffer, length, v10, v14, 1) == 2 )
            {
              if ( a3 )
              {
                v11 = v15;
                v15 = 0;
                *a3 = v11;
              }
              Windows::Internal::String::~String(&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
              goto LABEL_24;
            }
          }
          Windows::Internal::String::~String(&string);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
      }
      MediaServers = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v12 = WindowsGetStringRawBuffer(a2, 0);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids, v12);
      }
    }
  }
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
  return (unsigned int)MediaServers;
}

```

## disassembly

```asm
0x18001eff0  mov     [rsp-28h+arg_0], rbx
0x18001eff5  mov     [rsp-28h+arg_8], rsi
0x18001effa  push    rbp
0x18001effb  push    rdi
0x18001effc  push    r12
0x18001effe  push    r14
0x18001f000  push    r15
0x18001f002  mov     rbp, rsp
0x18001f005  sub     rsp, 50h
0x18001f009  mov     rdi, r8
0x18001f00c  mov     r15, rdx
0x18001f00f  test    r8, r8
0x18001f012  jz      short loc_18001F01B
0x18001f014  mov     qword ptr [r8], 0
0x18001f01b  mov     [rbp+var_8], 0
0x18001f023  lea     rdx, [rbp+var_8]
0x18001f027  call    ?GetMediaServers@CTrackedMediaServerCollection@@QEAAJPEAPEAU?$IVector@PEAUIBasicDevice@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@Z; CTrackedMediaServerCollection::GetMediaServers(Windows::Foundation::Collections::IVector<Windows::Media::Streaming::IBasicDevice *> * *)
0x18001f02c  mov     ebx, eax
0x18001f02e  test    eax, eax
0x18001f030  js      loc_18001F1D3
0x18001f036  mov     [rbp+arg_10], 0
0x18001f03d  mov     r14, [rbp+var_8]
0x18001f041  mov     rax, [r14]
0x18001f044  lea     rdx, [rbp+arg_10]
0x18001f048  mov     rcx, r14
0x18001f04b  mov     rax, [rax+38h]
0x18001f04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f054  mov     ebx, eax
0x18001f056  test    eax, eax
0x18001f058  js      loc_18001F1D3
0x18001f05e  lea     rdx, WPP_GLOBAL_Control
0x18001f065  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f06c  cmp     rcx, rdx
0x18001f06f  jz      short loc_18001F096
0x18001f071  test    byte ptr [rcx+1Ch], 40h
0x18001f075  jz      short loc_18001F096
0x18001f077  cmp     byte ptr [rcx+19h], 4
0x18001f07b  jb      short loc_18001F096
0x18001f07d  mov     edx, 11h
0x18001f082  mov     r9d, [rbp+arg_10]
0x18001f086  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18001f08d  mov     rcx, [rcx+10h]
0x18001f091  call    WPP_SF_d
0x18001f096  xor     esi, esi
0x18001f098  cmp     esi, [rbp+arg_10]
0x18001f09b  jnb     loc_18001F184
0x18001f0a1  mov     [rbp+var_18], 0
0x18001f0a9  mov     rax, [r14]
0x18001f0ac  mov     rbx, [rax+30h]
0x18001f0b0  lea     rcx, [rbp+var_18]
0x18001f0b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001f0b9  lea     r8, [rbp+var_18]
0x18001f0bd  mov     edx, esi
0x18001f0bf  mov     rcx, r14
0x18001f0c2  mov     rax, rbx
0x18001f0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ca  test    eax, eax
0x18001f0cc  js      short loc_18001F14B
0x18001f0ce  mov     [rbp+string], 0
0x18001f0d6  mov     rcx, [rbp+var_18]
0x18001f0da  mov     rax, [rcx]
0x18001f0dd  lea     rdx, [rbp+string]
0x18001f0e1  mov     rax, [rax+50h]
0x18001f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ea  mov     ebx, eax
0x18001f0ec  test    eax, eax
0x18001f0ee  js      short loc_18001F141
0x18001f0f0  mov     [rbp+length], 0
0x18001f0f7  lea     rdx, [rbp+length]; length
0x18001f0fb  mov     rcx, [rbp+string]; string
0x18001f0ff  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f105  mov     r12, rax
0x18001f108  mov     [rbp+var_20], 0
0x18001f10f  lea     rdx, [rbp+var_20]; length
0x18001f113  mov     rcx, r15; string
0x18001f116  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f11c  mov     edx, [rbp+length]; cchCount1
0x18001f11f  mov     r9d, [rbp+var_20]; cchCount2
0x18001f123  cmp     edx, r9d
0x18001f126  jnz     short loc_18001F141
0x18001f128  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18001f130  mov     r8, rax; lpString2
0x18001f133  mov     rcx, r12; lpString1
0x18001f136  call    cs:__imp_CompareStringOrdinal
0x18001f13c  cmp     eax, 2
0x18001f13f  jz      short loc_18001F15B
0x18001f141  lea     rcx, [rbp+string]; this
0x18001f145  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001f14a  nop
0x18001f14b  lea     rcx, [rbp+var_18]
0x18001f14f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001f154  inc     esi
0x18001f156  jmp     loc_18001F098
0x18001f15b  test    rdi, rdi
0x18001f15e  jz      short loc_18001F16F
0x18001f160  mov     rax, [rbp+var_18]
0x18001f164  mov     [rbp+var_18], 0
0x18001f16c  mov     [rdi], rax
0x18001f16f  lea     rcx, [rbp+string]; this
0x18001f173  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001f178  nop
0x18001f179  lea     rcx, [rbp+var_18]
0x18001f17d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001f182  jmp     short loc_18001F1D3
0x18001f184  mov     ebx, 80004005h
0x18001f189  mov     rax, cs:WPP_GLOBAL_Control
0x18001f190  lea     rcx, WPP_GLOBAL_Control
0x18001f197  cmp     rax, rcx
0x18001f19a  jz      short loc_18001F1D3
0x18001f19c  test    byte ptr [rax+1Ch], 40h
0x18001f1a0  jz      short loc_18001F1D3
0x18001f1a2  cmp     byte ptr [rax+19h], 4
0x18001f1a6  jb      short loc_18001F1D3
0x18001f1a8  xor     edx, edx; length
0x18001f1aa  mov     rcx, r15; string
0x18001f1ad  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f1b3  mov     edx, 12h
0x18001f1b8  mov     r9, rax
0x18001f1bb  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18001f1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1c9  mov     rcx, [rcx+10h]
0x18001f1cd  call    WPP_SF_S
0x18001f1d2  nop
0x18001f1d3  lea     rcx, [rbp+var_8]
0x18001f1d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001f1dc  mov     eax, ebx
0x18001f1de  lea     r11, [rsp+50h+var_s0]
0x18001f1e3  mov     rbx, [r11+30h]
0x18001f1e7  mov     rsi, [r11+38h]
0x18001f1eb  mov     rsp, r11
0x18001f1ee  pop     r15
0x18001f1f0  pop     r14
0x18001f1f2  pop     r12
0x18001f1f4  pop     rdi
0x18001f1f5  pop     rbp
0x18001f1f6  retn
```
