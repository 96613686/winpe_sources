# CContentDirectoryRowset::_GetSortCapabilitiesFromCDS(void)

- ea: `0x1800104d8`
- end: `0x180010736`
- name: `?_GetSortCapabilitiesFromCDS@CContentDirectoryRowset@@AEAAJXZ`
- size: `606`
- prototype: `__int64 __fastcall(CContentDirectoryRowset *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000de58`
- `0x1800104d8`
- `0x180014a00`
- `0x180019b84`
- `0x18001a28c`
- `0x18001c0ec`
- `0x18001c670`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800106a0`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800106a0`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001059a`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001059a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010661`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CContentDirectoryRowset::_GetSortCapabilitiesFromCDS(CContentDirectoryRowset *this)
{
  int AgileReference; // ebx
  __int64 *v3; // r14
  __int64 v4; // rdi
  HSTRING v5; // rax
  CContentRequestDelegate **v6; // rdi
  unsigned int v7; // edx
  const WCHAR *StringRawBuffer; // r12
  unsigned int v9; // edi
  __int64 i; // r14
  __int64 v12; // [rsp+80h] [rbp+48h] BYREF
  HSTRING string; // [rsp+88h] [rbp+50h] BYREF
  void *v14; // [rsp+90h] [rbp+58h] BYREF
  __int64 v15; // [rsp+98h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
  v12 = 0;
  v14 = 0;
  AgileReference = AgileGitPtr::CopyLocal(
                     (CContentDirectoryRowset *)((char *)this + 344),
                     &GUID_6550c614_7e79_4549_8064_681b3fca61df,
                     &v14);
  if ( AgileReference >= 0 )
  {
    AgileReference = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v14 + 56LL))(v14, &v12);
    if ( AgileReference >= 0 )
    {
      v3 = (__int64 *)((char *)this + 400);
      v4 = v12;
      v5 = 0;
      string = 0;
      AgileReference = 0;
      if ( v12 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&string);
        AgileReference = RoGetAgileReference(0, &GUID_3e1fe603_f897_5263_b328_0806426b8a79, v4, &string);
        v5 = string;
      }
      string = 0;
      v15 = *v3;
      *v3 = (__int64)v5;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&string);
      if ( AgileReference >= 0 )
      {
        v6 = (CContentRequestDelegate **)((char *)this + 408);
        AgileReference = Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>((char *)this + 408);
        if ( AgileReference >= 0 )
        {
          AgileReference = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v12 + 48LL))(
                             v12,
                             ((unsigned __int64)*v6 + 16) & -(__int64)(*v6 != 0));
          if ( AgileReference >= 0 )
          {
            AgileReference = CContentRequestDelegate::Wait(*v6, v7);
            if ( AgileReference >= 0 )
            {
              string = 0;
              AgileReference = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL))(v12, &string);
              if ( AgileReference >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                v9 = 1;
                for ( i = 0; i != 3; ++i )
                {
                  if ( FindStringOrdinal(
                         0x400000u,
                         StringRawBuffer,
                         -1,
                         *((LPCWSTR *)&CContentDirectoryRowset::s_arrSortCapabilities + 2 * i),
                         -1,
                         1) != -1 )
                    v9 = (*((_DWORD *)&CContentDirectoryRowset::s_arrSortCapabilities + 4 * i + 2) | v9) & 0xFFFFFFFE;
                }
                *((_DWORD *)this + 97) = v9;
              }
              Windows::Internal::String::~String(&string);
            }
          }
        }
        else
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)this + 51);
          AgileGitPtr::Revoke((CContentDirectoryRowset *)((char *)this + 400));
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v12);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((AgileReference >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids,
      (unsigned int)AgileReference);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v12);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x1800104d8  push    rbp
0x1800104da  push    rbx
0x1800104db  push    rsi
0x1800104dc  push    rdi
0x1800104dd  push    r12
0x1800104df  push    r13
0x1800104e1  push    r14
0x1800104e3  push    r15
0x1800104e5  mov     rbp, rsp
0x1800104e8  sub     rsp, 38h
0x1800104ec  mov     rsi, rcx
0x1800104ef  lea     r13, WPP_GLOBAL_Control
0x1800104f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104fd  cmp     rcx, r13
0x180010500  jz      short loc_18001051D
0x180010502  test    byte ptr [rcx+1Ch], 2
0x180010506  jz      short loc_18001051D
0x180010508  mov     edx, 0Dh
0x18001050d  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x180010514  mov     rcx, [rcx+10h]
0x180010518  call    WPP_SF_
0x18001051d  xor     r15d, r15d
0x180010520  mov     [rbp+arg_0], r15
0x180010524  mov     [rbp+arg_10], r15
0x180010528  lea     rcx, [rsi+158h]; this
0x18001052f  lea     r8, [rbp+arg_10]; void **
0x180010533  lea     rdx, _GUID_6550c614_7e79_4549_8064_681b3fca61df; struct _GUID *
0x18001053a  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18001053f  mov     ebx, eax
0x180010541  test    eax, eax
0x180010543  js      loc_1800106D2
0x180010549  mov     rcx, [rbp+arg_10]
0x18001054d  mov     rax, [rcx]
0x180010550  lea     rdx, [rbp+arg_0]
0x180010554  mov     rax, [rax+38h]
0x180010558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055d  mov     ebx, eax
0x18001055f  test    eax, eax
0x180010561  js      loc_1800106D2
0x180010567  lea     r14, [rsi+190h]
0x18001056e  mov     rdi, [rbp+arg_0]
0x180010572  mov     eax, r15d
0x180010575  mov     [rbp+string], rax
0x180010579  mov     ebx, r15d
0x18001057c  test    rdi, rdi
0x18001057f  jz      short loc_1800105A6
0x180010581  lea     rcx, [rbp+string]
0x180010585  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001058a  lea     r9, [rbp+string]
0x18001058e  mov     r8, rdi
0x180010591  lea     rdx, _GUID_3e1fe603_f897_5263_b328_0806426b8a79
0x180010598  xor     ecx, ecx
0x18001059a  call    cs:__imp_RoGetAgileReference
0x1800105a0  mov     ebx, eax
0x1800105a2  mov     rax, [rbp+string]
0x1800105a6  mov     [rbp+string], r15
0x1800105aa  mov     rcx, [r14]
0x1800105ad  mov     [rbp+arg_18], rcx
0x1800105b1  mov     [r14], rax
0x1800105b4  lea     rcx, [rbp+arg_18]
0x1800105b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800105bd  lea     rcx, [rbp+string]
0x1800105c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800105c6  test    ebx, ebx
0x1800105c8  js      loc_1800106D2
0x1800105ce  lea     rdi, [rsi+198h]
0x1800105d5  mov     rcx, rdi
0x1800105d8  call    ??$MakeAndInitialize@VCContentRequestDelegate@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCContentRequestDelegate@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CContentRequestDelegate>>)
0x1800105dd  mov     ebx, eax
0x1800105df  test    eax, eax
0x1800105e1  jns     short loc_180010601
0x1800105e3  mov     rcx, rdi
0x1800105e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800105eb  mov     rcx, r14; this
0x1800105ee  call    ?Revoke@AgileGitPtr@@QEAAJXZ; AgileGitPtr::Revoke(void)
0x1800105f3  lea     rcx, [rbp+arg_0]
0x1800105f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800105fc  jmp     loc_1800106D2
0x180010601  mov     rcx, [rbp+arg_0]
0x180010605  mov     rdx, [rdi]
0x180010608  mov     r8, [rcx]
0x18001060b  lea     rax, [rdx+10h]
0x18001060f  neg     rdx
0x180010612  sbb     rdx, rdx
0x180010615  and     rdx, rax
0x180010618  mov     rax, [r8+30h]
0x18001061c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010621  mov     ebx, eax
0x180010623  test    eax, eax
0x180010625  js      loc_1800106D2
0x18001062b  mov     rcx, [rdi]; this
0x18001062e  call    ?Wait@CContentRequestDelegate@@QEAAJK@Z; CContentRequestDelegate::Wait(ulong)
0x180010633  mov     ebx, eax
0x180010635  test    eax, eax
0x180010637  js      loc_1800106D2
0x18001063d  mov     [rbp+string], r15
0x180010641  mov     rcx, [rbp+arg_0]
0x180010645  mov     rax, [rcx]
0x180010648  lea     rdx, [rbp+string]
0x18001064c  mov     rax, [rax+40h]
0x180010650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010655  mov     ebx, eax
0x180010657  test    eax, eax
0x180010659  js      short loc_1800106C9
0x18001065b  xor     edx, edx; length
0x18001065d  mov     rcx, [rbp+string]; string
0x180010661  call    cs:__imp_WindowsGetStringRawBuffer
0x180010667  mov     r12, rax
0x18001066a  mov     edi, 1
0x18001066f  mov     r14, r15
0x180010672  lea     r13, ?s_arrSortCapabilities@CContentDirectoryRowset@@0QBUUPnPElementToSortCapability@1@B; CContentDirectoryRowset::UPnPElementToSortCapability const near * const CContentDirectoryRowset::s_arrSortCapabilities
0x180010679  mov     r15, r14
0x18001067c  shl     r15, 4
0x180010680  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180010688  mov     [rsp+38h+cchValue], 0FFFFFFFFh; cchValue
0x180010690  mov     r9, [r15+r13]; lpStringValue
0x180010694  or      r8d, 0FFFFFFFFh; cchSource
0x180010698  mov     rdx, r12; lpStringSource
0x18001069b  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x1800106a0  call    cs:__imp_FindStringOrdinal
0x1800106a6  cmp     eax, 0FFFFFFFFh
0x1800106a9  jz      short loc_1800106B3
0x1800106ab  or      edi, [r15+r13+8]
0x1800106b0  and     edi, 0FFFFFFFEh
0x1800106b3  inc     r14
0x1800106b6  cmp     r14, 3
0x1800106ba  jnz     short loc_180010679
0x1800106bc  mov     [rsi+184h], edi
0x1800106c2  lea     r13, WPP_GLOBAL_Control
0x1800106c9  lea     rcx, [rbp+string]; this
0x1800106cd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800106d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d9  cmp     rcx, r13
0x1800106dc  jz      short loc_180010710
0x1800106de  test    byte ptr [rcx+1Ch], 2
0x1800106e2  jz      short loc_180010710
0x1800106e4  mov     edx, ebx
0x1800106e6  sar     edx, 1Fh
0x1800106e9  and     edx, 0FFFFFFFDh
0x1800106ec  add     edx, 5
0x1800106ef  movzx   eax, byte ptr [rcx+19h]
0x1800106f3  cmp     eax, edx
0x1800106f5  jb      short loc_180010710
0x1800106f7  mov     edx, 0Eh
0x1800106fc  mov     r9d, ebx
0x1800106ff  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x180010706  mov     rcx, [rcx+10h]
0x18001070a  call    WPP_SF_d
0x18001070f  nop
0x180010710  lea     rcx, [rbp+arg_10]
0x180010714  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010719  nop
0x18001071a  lea     rcx, [rbp+arg_0]
0x18001071e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010723  mov     eax, ebx
0x180010725  add     rsp, 38h
0x180010729  pop     r15
0x18001072b  pop     r14
0x18001072d  pop     r13
0x18001072f  pop     r12
0x180010731  pop     rdi
0x180010732  pop     rsi
0x180010733  pop     rbx
0x180010734  pop     rbp
0x180010735  retn
```
