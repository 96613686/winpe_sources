# CContentDirectoryRowset::_ContentDirectoryBrowse(ulong)

- ea: `0x18001c744`
- end: `0x18001cc49`
- name: `?_ContentDirectoryBrowse@CContentDirectoryRowset@@AEAAJK@Z`
- size: `1285`
- prototype: `__int64 __fastcall(CContentDirectoryRowset *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000de58`
- `0x180011930`
- `0x180014a00`
- `0x18001681c`
- `0x180019d18`
- `0x18001a28c`
- `0x18001bba8`
- `0x18001c0ec`
- `0x18001c670`
- `0x18001c744`
- `0x18001db80`
- `0x18001dd14`
- `0x18001dd80`
- `0x18001e220`
- `0x18001e7c0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c80e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001cc19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c80e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001cc19`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001ca47`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001ca47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cb8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cb99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c8de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cb8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cb99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cba7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CContentDirectoryRowset::_ContentDirectoryBrowse(CContentDirectoryRowset *this, unsigned int a2)
{
  __int64 v2; // r15
  PVOID *v4; // rcx
  HSTRING v5; // rbx
  int SortCriteriaForFolder; // r12d
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, const wchar_t *, PROPVARIANT *); // rdi
  const unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  int v11; // r15d
  int v12; // r14d
  PCWSTR StringRawBuffer; // rsi
  PCWSTR v14; // rdi
  unsigned int v15; // eax
  int v16; // esi
  int v17; // edi
  PCWSTR v18; // rax
  int v19; // r8d
  void *v20; // rsi
  __int64 (__fastcall *v21)(void *, HSTRING, _QWORD, HSTRING, _DWORD, _DWORD, HSTRING, __int64 *); // rdi
  struct Windows::Media::Streaming::Internal::IContentRequest **v22; // rsi
  __int64 v23; // rdi
  struct Windows::Media::Streaming::Internal::IContentRequest *v24; // rax
  CContentRequestDelegate **v25; // rdi
  unsigned int v26; // edx
  int IsCompleted; // r14d
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, struct Windows::Media::Streaming::Internal::IContentRequest **); // rdi
  __int64 v30; // rax
  int v31; // r15d
  int v32; // r14d
  PCWSTR v33; // rsi
  PCWSTR v34; // rdi
  unsigned int v35; // eax
  int v36; // ecx
  __int64 v38; // [rsp+60h] [rbp-59h] BYREF
  struct Windows::Media::Streaming::Internal::IContentRequest *v39; // [rsp+68h] [rbp-51h] BYREF
  HSTRING string; // [rsp+70h] [rbp-49h] BYREF
  void *v41; // [rsp+78h] [rbp-41h] BYREF
  HSTRING v42; // [rsp+80h] [rbp-39h] BYREF
  struct Windows::Media::Streaming::Internal::IContentRequest *v43; // [rsp+88h] [rbp-31h] BYREF
  __int64 v44; // [rsp+90h] [rbp-29h] BYREF
  PROPVARIANT pvar; // [rsp+98h] [rbp-21h] BYREF
  HSTRING v46; // [rsp+B0h] [rbp-9h] BYREF

  v2 = a2;
  LODWORD(v38) = a2;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  pvar.vt = 0;
  v5 = 0;
  v42 = 0;
  if ( *((_QWORD *)this + 34) )
  {
    v7 = *((_QWORD *)this + 36);
    v8 = *(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v7 + 24LL);
    PropVariantClear(&pvar);
    SortCriteriaForFolder = v8(v7, L"ObjectID", &pvar);
    if ( SortCriteriaForFolder >= 0 )
    {
      v9 = CPropVariant::GetString((CPropVariant *)&pvar);
      if ( v9 )
      {
        SortCriteriaForFolder = Windows::Internal::String::_InitializeHelper(&v42, v9);
        v5 = v42;
      }
      else
      {
        SortCriteriaForFolder = -2147467261;
      }
      if ( SortCriteriaForFolder >= 0 )
      {
        Windows::Internal::StringReference::StringReference(&v46, L"*");
        string = 0;
        v44 = 0;
        SortCriteriaForFolder = CContentDirectoryRowset::_GetSortCriteriaForFolder(
                                  (HSTRING *)this,
                                  *((_DWORD *)this + 97),
                                  &string);
        if ( SortCriteriaForFolder >= 0 )
        {
          if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
          {
            v10 = v2;
            v11 = *((_DWORD *)this + 10 * v2 + 20);
            v12 = *((_DWORD *)this + 10 * v10 + 18);
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v14 = WindowsGetStringRawBuffer(v46, 0);
            v15 = (unsigned int)WindowsGetStringRawBuffer(v5, 0);
            McTemplateU0zzzzqqqqq_EventWriteTransfer(
              0,
              (unsigned int)ContentDirectory_Search_Start,
              v15,
              (unsigned int)L"**Browse**",
              (__int64)v14,
              (__int64)StringRawBuffer,
              v12,
              v11,
              0,
              0,
              0);
            LODWORD(v2) = v38;
          }
          v41 = 0;
          SortCriteriaForFolder = AgileGitPtr::CopyLocal(
                                    (CContentDirectoryRowset *)((char *)this + 344),
                                    &GUID_6550c614_7e79_4549_8064_681b3fca61df,
                                    &v41);
          if ( SortCriteriaForFolder >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v16 = *((_DWORD *)this + 10 * (unsigned int)v2 + 20);
              v17 = *((_DWORD *)this + 10 * (unsigned int)v2 + 18);
              v18 = WindowsGetStringRawBuffer(v5, 0);
              WPP_SF_qSDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v19, (_DWORD)this, (__int64)v18, v17, v16);
            }
            v38 = 0;
            v20 = v41;
            v21 = *(__int64 (__fastcall **)(void *, HSTRING, _QWORD, HSTRING, _DWORD, _DWORD, HSTRING, __int64 *))(*(_QWORD *)v41 + 80LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v38);
            SortCriteriaForFolder = v21(
                                      v20,
                                      v5,
                                      0,
                                      v46,
                                      *((_DWORD *)this + 10 * (unsigned int)v2 + 18),
                                      *((_DWORD *)this + 10 * (unsigned int)v2 + 20),
                                      string,
                                      &v38);
            if ( SortCriteriaForFolder >= 0 )
            {
              v22 = (struct Windows::Media::Streaming::Internal::IContentRequest **)((char *)this + 400);
              v23 = v38;
              v24 = 0;
              v39 = 0;
              SortCriteriaForFolder = 0;
              if ( v38 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v39);
                SortCriteriaForFolder = RoGetAgileReference(0, &GUID_d459d20d_1e3a_543c_bb1c_569c96afdca7, v23, &v39);
                v24 = v39;
              }
              v39 = 0;
              v43 = *v22;
              *v22 = v24;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v39);
              if ( SortCriteriaForFolder >= 0 )
              {
                v25 = (CContentRequestDelegate **)((char *)this + 408);
                SortCriteriaForFolder = Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>((char *)this + 408);
                if ( SortCriteriaForFolder >= 0 )
                {
                  SortCriteriaForFolder = (*(__int64 (__fastcall **)(__int64, CContentRequestDelegate *))(*(_QWORD *)v38 + 64LL))(
                                            v38,
                                            *v25);
                  if ( SortCriteriaForFolder >= 0 )
                  {
                    SortCriteriaForFolder = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v38 + 48LL))(
                                              v38,
                                              ((unsigned __int64)*v25 + 8) & -(__int64)(*v25 != 0));
                    if ( SortCriteriaForFolder >= 0 )
                    {
                      SortCriteriaForFolder = CContentRequestDelegate::Wait(*v25, v26);
                      if ( SortCriteriaForFolder >= 0 )
                      {
                        v39 = 0;
                        IsCompleted = CContentRequestDelegate::IsCompleted(*v25);
                        v28 = v38;
                        v29 = *(__int64 (__fastcall **)(__int64, struct Windows::Media::Streaming::Internal::IContentRequest **))(*(_QWORD *)v38 + 80LL);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v39);
                        SortCriteriaForFolder = v29(v28, &v39);
                        if ( SortCriteriaForFolder >= 0 )
                          SortCriteriaForFolder = CContentDirectoryRowset::_QueryResults(this, v39, v2, IsCompleted);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v39);
                      }
                    }
                  }
                }
                else
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 408);
                  AgileGitPtr::Revoke((CContentDirectoryRowset *)((char *)this + 400));
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v38);
                }
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v38);
          }
          if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
          {
            v30 = 5LL * (unsigned int)v2;
            v31 = *((_DWORD *)this + 10 * (unsigned int)v2 + 20);
            v32 = *((_DWORD *)this + 2 * v30 + 18);
            v33 = WindowsGetStringRawBuffer(string, 0);
            v34 = WindowsGetStringRawBuffer(v46, 0);
            v35 = (unsigned int)WindowsGetStringRawBuffer(v5, 0);
            McTemplateU0zzzzqqqqq_EventWriteTransfer(
              v36,
              (unsigned int)ContentDirectory_Search_Stop,
              v35,
              (unsigned int)L"**Browse**",
              (__int64)v34,
              (__int64)v33,
              v32,
              v31,
              0,
              0,
              SortCriteriaForFolder);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v41);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v44);
        Windows::Internal::String::~String(&string);
      }
    }
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 4u )
      WPP_SF_(v4[2], 16, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
    SortCriteriaForFolder = -2147024809;
  }
  Windows::Internal::String::~String(&v42);
  PropVariantClear(&pvar);
  return (unsigned int)SortCriteriaForFolder;
}

```

## disassembly

```asm
0x18001c744  mov     [rsp-8+arg_10], rbx
0x18001c749  push    rbp
0x18001c74a  push    rsi
0x18001c74b  push    rdi
0x18001c74c  push    r12
0x18001c74e  push    r13
0x18001c750  push    r14
0x18001c752  push    r15
0x18001c754  lea     rbp, [rsp-27h]
0x18001c759  sub     rsp, 0E0h
0x18001c760  mov     rax, cs:__security_cookie
0x18001c767  xor     rax, rsp
0x18001c76a  mov     [rbp+57h+var_40], rax
0x18001c76e  mov     r15d, edx
0x18001c771  mov     dword ptr [rbp+57h+var_B0], r15d
0x18001c775  mov     r13, rcx
0x18001c778  lea     rdx, WPP_GLOBAL_Control
0x18001c77f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c786  cmp     rcx, rdx
0x18001c789  jz      short loc_18001C7B4
0x18001c78b  test    byte ptr [rcx+1Ch], 2
0x18001c78f  jz      short loc_18001C7B4
0x18001c791  mov     edx, 0Fh
0x18001c796  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001c79d  mov     rcx, [rcx+10h]
0x18001c7a1  call    WPP_SF_
0x18001c7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7ad  lea     rdx, WPP_GLOBAL_Control
0x18001c7b4  xor     r14d, r14d
0x18001c7b7  mov     word ptr [rbp+57h+pvar], r14w
0x18001c7bc  mov     ebx, r14d
0x18001c7bf  mov     [rbp+57h+var_90], rbx
0x18001c7c3  cmp     [r13+110h], r14
0x18001c7ca  jnz     short loc_18001C7FC
0x18001c7cc  cmp     rcx, rdx
0x18001c7cf  jz      short loc_18001C7F1
0x18001c7d1  test    byte ptr [rcx+1Ch], 40h
0x18001c7d5  jz      short loc_18001C7F1
0x18001c7d7  cmp     byte ptr [rcx+19h], 4
0x18001c7db  jb      short loc_18001C7F1
0x18001c7dd  lea     edx, [r14+10h]
0x18001c7e1  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001c7e8  mov     rcx, [rcx+10h]
0x18001c7ec  call    WPP_SF_
0x18001c7f1  mov     r12d, 80070057h
0x18001c7f7  jmp     loc_18001CC0B
0x18001c7fc  mov     rsi, [r13+120h]
0x18001c803  mov     rax, [rsi]
0x18001c806  mov     rdi, [rax+18h]
0x18001c80a  lea     rcx, [rbp+57h+pvar]; pvar
0x18001c80e  call    cs:__imp_PropVariantClear
0x18001c814  lea     r8, [rbp+57h+pvar]
0x18001c818  lea     rdx, g_wszObjectID; "ObjectID"
0x18001c81f  mov     rcx, rsi
0x18001c822  mov     rax, rdi
0x18001c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c82a  mov     r12d, eax
0x18001c82d  test    eax, eax
0x18001c82f  js      loc_18001CC0B
0x18001c835  lea     rcx, [rbp+57h+pvar]; this
0x18001c839  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18001c83e  test    rax, rax
0x18001c841  jz      short loc_18001C858
0x18001c843  mov     rdx, rax; unsigned __int16 *
0x18001c846  lea     rcx, [rbp+57h+var_90]; this
0x18001c84a  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001c84f  mov     r12d, eax
0x18001c852  mov     rbx, [rbp+57h+var_90]
0x18001c856  jmp     short loc_18001C85E
0x18001c858  mov     r12d, 80004003h
0x18001c85e  test    r12d, r12d
0x18001c861  js      loc_18001CC0B
0x18001c867  lea     rdx, Src; "*"
0x18001c86e  lea     rcx, [rbp+57h+var_60]; string
0x18001c872  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x18001c877  mov     [rbp+57h+string], r14
0x18001c87b  mov     [rbp+57h+var_80], r14
0x18001c87f  lea     r8, [rbp+57h+string]; HSTRING *
0x18001c883  mov     edx, [r13+184h]; unsigned int
0x18001c88a  mov     rcx, r13; this
0x18001c88d  call    ?_GetSortCriteriaForFolder@CContentDirectoryRowset@@AEAAJKPEAPEAUHSTRING__@@@Z; CContentDirectoryRowset::_GetSortCriteriaForFolder(ulong,HSTRING__ * *)
0x18001c892  mov     r12d, eax
0x18001c895  test    eax, eax
0x18001c897  js      loc_18001CBF7
0x18001c89d  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x18001c8a4  jz      short loc_18001C923
0x18001c8a6  mov     rcx, r15
0x18001c8a9  lea     rax, [r15+r15*4]
0x18001c8ad  mov     r15d, [r13+rax*8+50h]
0x18001c8b2  lea     rax, [rcx+rcx*4]
0x18001c8b6  mov     r14d, [r13+rax*8+48h]
0x18001c8bb  xor     edx, edx; length
0x18001c8bd  mov     rcx, [rbp+57h+string]; string
0x18001c8c1  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c8c7  mov     rsi, rax
0x18001c8ca  xor     edx, edx; length
0x18001c8cc  mov     rcx, [rbp+57h+var_60]; string
0x18001c8d0  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c8d6  mov     rdi, rax
0x18001c8d9  xor     edx, edx; length
0x18001c8db  mov     rcx, rbx; string
0x18001c8de  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c8e4  xor     ecx, ecx
0x18001c8e6  mov     [rsp+110h+var_C0], ecx
0x18001c8ea  mov     [rsp+110h+var_C8], ecx
0x18001c8ee  mov     [rsp+110h+var_D0], ecx
0x18001c8f2  mov     dword ptr [rsp+110h+var_D8], r15d
0x18001c8f7  mov     dword ptr [rsp+110h+var_E0], r14d
0x18001c8fc  mov     [rsp+110h+var_E8], rsi
0x18001c901  mov     [rsp+110h+var_F0], rdi
0x18001c906  lea     r9, aBrowse; "**Browse**"
0x18001c90d  mov     r8, rax
0x18001c910  lea     rdx, ContentDirectory_Search_Start
0x18001c917  call    McTemplateU0zzzzqqqqq_EventWriteTransfer
0x18001c91c  mov     r15d, dword ptr [rbp+57h+var_B0]
0x18001c920  xor     r14d, r14d
0x18001c923  mov     [rbp+57h+var_98], r14
0x18001c927  lea     rcx, [r13+158h]; this
0x18001c92e  lea     r8, [rbp+57h+var_98]; void **
0x18001c932  lea     rdx, _GUID_6550c614_7e79_4549_8064_681b3fca61df; struct _GUID *
0x18001c939  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18001c93e  mov     r12d, eax
0x18001c941  test    eax, eax
0x18001c943  js      loc_18001CB66
0x18001c949  mov     rax, cs:WPP_GLOBAL_Control
0x18001c950  lea     rcx, WPP_GLOBAL_Control
0x18001c957  cmp     rax, rcx
0x18001c95a  jz      short loc_18001C9AD
0x18001c95c  test    byte ptr [rax+1Ch], 40h
0x18001c960  jz      short loc_18001C9AD
0x18001c962  cmp     byte ptr [rax+19h], 4
0x18001c966  jb      short loc_18001C9AD
0x18001c968  mov     ecx, r15d
0x18001c96b  lea     rax, [rcx+rcx*4]
0x18001c96f  mov     esi, [r13+rax*8+50h]
0x18001c974  lea     rax, [rcx+rcx*4]
0x18001c978  mov     edi, [r13+rax*8+48h]
0x18001c97d  xor     edx, edx; length
0x18001c97f  mov     rcx, rbx; string
0x18001c982  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c988  mov     edx, 11h
0x18001c98d  mov     dword ptr [rsp+110h+var_E0], esi
0x18001c991  mov     dword ptr [rsp+110h+var_E8], edi
0x18001c995  mov     [rsp+110h+var_F0], rax
0x18001c99a  mov     r9, r13
0x18001c99d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9a4  mov     rcx, [rcx+10h]
0x18001c9a8  call    WPP_SF_qSDD
0x18001c9ad  mov     [rbp+57h+var_B0], r14
0x18001c9b1  mov     rsi, [rbp+57h+var_98]
0x18001c9b5  mov     rax, [rsi]
0x18001c9b8  mov     rdi, [rax+50h]
0x18001c9bc  lea     rcx, [rbp+57h+var_B0]
0x18001c9c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001c9c5  mov     r10, [rbp+57h+string]
0x18001c9c9  mov     edx, r15d
0x18001c9cc  lea     r8, [rdx+rdx*4]
0x18001c9d0  lea     r9, [rdx+rdx*4]
0x18001c9d4  lea     rax, [rbp+57h+var_B0]
0x18001c9d8  mov     [rsp+110h+var_D8], rax
0x18001c9dd  mov     [rsp+110h+var_E0], r10
0x18001c9e2  mov     edx, [r13+r8*8+50h]
0x18001c9e7  mov     dword ptr [rsp+110h+var_E8], edx
0x18001c9eb  mov     edx, [r13+r9*8+48h]
0x18001c9f0  mov     dword ptr [rsp+110h+var_F0], edx
0x18001c9f4  mov     r9, [rbp+57h+var_60]
0x18001c9f8  xor     r8d, r8d
0x18001c9fb  mov     rdx, rbx
0x18001c9fe  mov     rcx, rsi
0x18001ca01  mov     rax, rdi
0x18001ca04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca09  mov     r12d, eax
0x18001ca0c  test    eax, eax
0x18001ca0e  js      loc_18001CB5D
0x18001ca14  lea     rsi, [r13+190h]
0x18001ca1b  mov     rdi, [rbp+57h+var_B0]
0x18001ca1f  mov     rax, r14
0x18001ca22  mov     [rbp+57h+var_A8], rax
0x18001ca26  mov     r12d, r14d
0x18001ca29  test    rdi, rdi
0x18001ca2c  jz      short loc_18001CA54
0x18001ca2e  lea     rcx, [rbp+57h+var_A8]
0x18001ca32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001ca37  lea     r9, [rbp+57h+var_A8]
0x18001ca3b  mov     r8, rdi
0x18001ca3e  lea     rdx, _GUID_d459d20d_1e3a_543c_bb1c_569c96afdca7
0x18001ca45  xor     ecx, ecx
0x18001ca47  call    cs:__imp_RoGetAgileReference
0x18001ca4d  mov     r12d, eax
0x18001ca50  mov     rax, [rbp+57h+var_A8]
0x18001ca54  mov     [rbp+57h+var_A8], r14
0x18001ca58  mov     rcx, [rsi]
0x18001ca5b  mov     [rbp+57h+var_88], rcx
0x18001ca5f  mov     [rsi], rax
0x18001ca62  lea     rcx, [rbp+57h+var_88]
0x18001ca66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001ca6b  lea     rcx, [rbp+57h+var_A8]
0x18001ca6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001ca74  test    r12d, r12d
0x18001ca77  js      loc_18001CB5D
0x18001ca7d  lea     rdi, [r13+198h]
0x18001ca84  mov     rcx, rdi
0x18001ca87  call    ??$MakeAndInitialize@VCContentRequestDelegate@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCContentRequestDelegate@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CContentRequestDelegate>>)
0x18001ca8c  mov     r12d, eax
0x18001ca8f  test    eax, eax
0x18001ca91  jns     short loc_18001CAB1
0x18001ca93  mov     rcx, rdi
0x18001ca96  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001ca9b  mov     rcx, rsi; this
0x18001ca9e  call    ?Revoke@AgileGitPtr@@QEAAJXZ; AgileGitPtr::Revoke(void)
0x18001caa3  lea     rcx, [rbp+57h+var_B0]
0x18001caa7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001caac  jmp     loc_18001CB5D
0x18001cab1  mov     rcx, [rbp+57h+var_B0]
0x18001cab5  mov     rax, [rcx]
0x18001cab8  mov     rdx, [rdi]
0x18001cabb  mov     rax, [rax+40h]
0x18001cabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cac4  mov     r12d, eax
0x18001cac7  test    eax, eax
0x18001cac9  js      loc_18001CB5D
0x18001cacf  mov     rcx, [rbp+57h+var_B0]
0x18001cad3  mov     rdx, [rdi]
0x18001cad6  mov     r8, [rcx]
0x18001cad9  lea     rax, [rdx+8]
0x18001cadd  neg     rdx
0x18001cae0  sbb     rdx, rdx
0x18001cae3  and     rdx, rax
0x18001cae6  mov     rax, [r8+30h]
0x18001caea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caef  mov     r12d, eax
0x18001caf2  test    eax, eax
0x18001caf4  js      short loc_18001CB5D
0x18001caf6  mov     rcx, [rdi]; this
0x18001caf9  call    ?Wait@CContentRequestDelegate@@QEAAJK@Z; CContentRequestDelegate::Wait(ulong)
0x18001cafe  mov     r12d, eax
0x18001cb01  test    eax, eax
0x18001cb03  js      short loc_18001CB5D
0x18001cb05  mov     [rbp+57h+var_A8], r14
0x18001cb09  mov     rcx, [rdi]; this
0x18001cb0c  call    ?IsCompleted@CContentRequestDelegate@@QEAAHXZ; CContentRequestDelegate::IsCompleted(void)
0x18001cb11  mov     r14d, eax
0x18001cb14  mov     rsi, [rbp+57h+var_B0]
0x18001cb18  mov     rdx, [rsi]
0x18001cb1b  mov     rdi, [rdx+50h]
0x18001cb1f  lea     rcx, [rbp+57h+var_A8]
0x18001cb23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cb28  lea     rdx, [rbp+57h+var_A8]
0x18001cb2c  mov     rcx, rsi
0x18001cb2f  mov     rax, rdi
0x18001cb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb37  mov     r12d, eax
0x18001cb3a  test    eax, eax
0x18001cb3c  js      short loc_18001CB53
0x18001cb3e  mov     r9d, r14d; int
0x18001cb41  mov     r8d, r15d; unsigned int
0x18001cb44  mov     rdx, [rbp+57h+var_A8]; struct Windows::Media::Streaming::Internal::IContentRequest *
0x18001cb48  mov     rcx, r13; this
0x18001cb4b  call    ?_QueryResults@CContentDirectoryRowset@@AEAAJPEAUIContentRequest@Internal@Streaming@Media@Windows@@KH@Z; CContentDirectoryRowset::_QueryResults(Windows::Media::Streaming::Internal::IContentRequest *,ulong,int)
0x18001cb50  mov     r12d, eax
0x18001cb53  lea     rcx, [rbp+57h+var_A8]
0x18001cb57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cb5c  nop
0x18001cb5d  lea     rcx, [rbp+57h+var_B0]
0x18001cb61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cb66  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x18001cb6d  jz      short loc_18001CBED
0x18001cb6f  mov     ecx, r15d
0x18001cb72  lea     rax, [rcx+rcx*4]
0x18001cb76  mov     r15d, [r13+rax*8+50h]
0x18001cb7b  lea     rax, [rcx+rcx*4]
0x18001cb7f  mov     r14d, [r13+rax*8+48h]
0x18001cb84  xor     edx, edx; length
0x18001cb86  mov     rcx, [rbp+57h+string]; string
0x18001cb8a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cb90  mov     rsi, rax
0x18001cb93  xor     edx, edx; length
0x18001cb95  mov     rcx, [rbp+57h+var_60]; string
0x18001cb99  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cb9f  mov     rdi, rax
0x18001cba2  xor     edx, edx; length
0x18001cba4  mov     rcx, rbx; string
0x18001cba7  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cbad  mov     [rsp+110h+var_C0], r12d
0x18001cbb2  mov     [rsp+110h+var_C8], 0
0x18001cbba  mov     [rsp+110h+var_D0], 0
0x18001cbc2  mov     dword ptr [rsp+110h+var_D8], r15d
0x18001cbc7  mov     dword ptr [rsp+110h+var_E0], r14d
0x18001cbcc  mov     [rsp+110h+var_E8], rsi
0x18001cbd1  mov     [rsp+110h+var_F0], rdi
0x18001cbd6  lea     r9, aBrowse; "**Browse**"
0x18001cbdd  mov     r8, rax
0x18001cbe0  lea     rdx, ContentDirectory_Search_Stop
0x18001cbe7  call    McTemplateU0zzzzqqqqq_EventWriteTransfer
0x18001cbec  nop
0x18001cbed  lea     rcx, [rbp+57h+var_98]
0x18001cbf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cbf6  nop
0x18001cbf7  lea     rcx, [rbp+57h+var_80]
0x18001cbfb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
  ... truncated ...
```
