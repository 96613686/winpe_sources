# CMediaServerFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180001c70`
- end: `0x1800021a7`
- name: `?ParseDisplayName@CMediaServerFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `1335`
- prototype: `int(CMediaServerFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180001c70`
- `0x1800021b0`
- `0x180005f90`
- `0x18000d68c`
- `0x180011930`
- `0x1800125c4`
- `0x180015994`
- `0x180019b84`
- `0x18001e91c`
- `0x18002c844`
- `0x18002d9ac`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800020ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000217e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800020ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000217e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001d20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180001d20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180001d63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180001f60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180001d63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180001f60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001db5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001db5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180001dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000214b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000215a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000216a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000214b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000215a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000216a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180001d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180001d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180001fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180001fa5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMediaServerFolder::ParseDisplayName(
        CMediaServerFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  struct _ITEMIDLIST_ABSOLUTE *v8; // rdi
  WCHAR *v9; // rbx
  HSTRING v10; // rsi
  HSTRING v11; // r14
  __int64 v12; // rdx
  const WCHAR *StringRawBuffer; // rax
  HSTRING *v14; // r9
  int Item; // r12d
  const unsigned __int16 *v16; // r15
  const unsigned __int16 *v17; // rax
  int v18; // eax
  HSTRING v19; // rcx
  const unsigned __int16 *v20; // rax
  _WORD *v21; // r13
  unsigned __int16 *v22; // r15
  unsigned __int16 i; // ax
  unsigned __int64 v24; // r13
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  WCHAR *v27; // r10
  __int64 v28; // rcx
  WCHAR *v29; // rax
  WCHAR v30; // dx
  __int64 v31; // rdx
  WCHAR *v32; // rcx
  __int64 v33; // r8
  bool v34; // cf
  unsigned __int64 v35; // r8
  CMediaServerFolder *v36; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v38; // rcx
  struct IBindCtx *v39; // r15
  const struct _ITEMIDLIST_RELATIVE *v40; // rcx
  void *v42; // [rsp+40h] [rbp-91h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-89h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v44; // [rsp+50h] [rbp-81h] BYREF
  HSTRING v45; // [rsp+58h] [rbp-79h] BYREF
  HSTRING v46; // [rsp+60h] [rbp-71h] BYREF
  WCHAR *v47; // [rsp+68h] [rbp-69h]
  CMediaServerFolder *v48; // [rsp+70h] [rbp-61h]
  HSTRING v49; // [rsp+78h] [rbp-59h] BYREF
  struct _ITEMIDLIST_ABSOLUTE **v50; // [rsp+80h] [rbp-51h]
  unsigned int *v51; // [rsp+88h] [rbp-49h]
  struct IBindCtx *v52; // [rsp+90h] [rbp-41h]
  HWND v53; // [rsp+98h] [rbp-39h]
  HSTRING string; // [rsp+A8h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-21h] BYREF

  v42 = a4;
  v52 = a3;
  v53 = a2;
  v48 = this;
  v50 = a6;
  v51 = a7;
  v8 = 0;
  v44 = 0;
  v9 = 0;
  v47 = 0;
  v45 = 0;
  v10 = 0;
  v46 = 0;
  v11 = 0;
  v49 = 0;
  v12 = -1;
  do
    ++v12;
  while ( a4[v12] );
  if ( WindowsCreateStringReference(a4, v12, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  *a6 = 0;
  length[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, length);
  if ( length[0] <= 0x10 || CompareStringOrdinal(StringRawBuffer, 16, L"dlna-playsingle:", 16, 1) != 2 )
  {
    v22 = a4;
    for ( i = *a4; *v22; i = *v22 )
    {
      if ( i == 92 )
        break;
      ++v22;
    }
    v24 = v22 - a4;
    v9 = 0;
    v47 = 0;
    v25 = v24 + 1;
    *(_QWORD *)length = v24 + 1;
    if ( v24 + 1 < v24 )
    {
      Item = -2147024362;
    }
    else
    {
      v47 = 0;
      if ( is_mul_ok(v25, 2u) )
      {
        v9 = (WCHAR *)LocalAlloc(0, 2 * v25);
        v47 = v9;
        Item = -2147024882;
        if ( v9 )
          Item = 0;
        v25 = *(_QWORD *)length;
      }
      else
      {
        Item = -2147024362;
      }
      if ( Item >= 0 )
      {
        if ( (v9 || !v25) && v25 <= 0x7FFFFFFF )
        {
          if ( v24 < 0x7FFFFFFF )
          {
            if ( v25 )
            {
              v26 = v25;
              v27 = v9;
              v28 = 0;
              v29 = (WCHAR *)v42;
              do
              {
                if ( !v24 )
                  break;
                v30 = *v29;
                if ( !*v29 )
                  break;
                ++v29;
                *v27++ = v30;
                --v24;
                ++v28;
                --v26;
              }
              while ( v26 );
              v31 = v28 - 1;
              if ( v26 )
                v31 = v28;
              v32 = v27 - 1;
              if ( v26 )
                v32 = v27;
              *v32 = 0;
              if ( v26 )
              {
                v34 = v25 == v31;
                v33 = v25 - v31;
                if ( !v34 && v33 != 1 )
                {
                  v35 = 2 * v33;
                  if ( v35 > 2 )
                    memset_0(&v9[v31 + 1], 0, v35 - 2);
                }
              }
            }
          }
          else if ( v25 )
          {
            *v9 = 0;
          }
        }
        else
        {
          *v9 = 0;
        }
        v21 = v22 + 1;
        if ( !*v22 )
          v21 = v22;
        goto LABEL_47;
      }
    }
    v21 = v42;
LABEL_47:
    if ( Item < 0 )
      goto LABEL_67;
    if ( CompareStringOrdinal(v9, 5, L"uuid:", 5, 1) != 2 )
    {
      Item = -2147024829;
      goto LABEL_67;
    }
    v16 = v9;
    goto LABEL_51;
  }
  Item = DlnaUrlHelpers::ParsePlaysingleUrl((DlnaUrlHelpers *)string, (HSTRING)&v45, &v46, v14);
  if ( Item < 0 )
  {
    v10 = v46;
    goto LABEL_67;
  }
  v16 = WindowsGetStringRawBuffer(v45, 0);
  v10 = v46;
  v17 = WindowsGetStringRawBuffer(v46, 0);
  v18 = CCDSResultsParser::ObjectIDNeedsEscaping(v17);
  v19 = v10;
  if ( v18 )
  {
    v20 = WindowsGetStringRawBuffer(v10, 0);
    Item = CCDSResultsParser::EscapeObjectID(v20, &v49);
    v11 = v49;
    v19 = v49;
  }
  v21 = WindowsGetStringRawBuffer(v19, 0);
LABEL_51:
  if ( Item < 0 )
    goto LABEL_67;
  v36 = v48;
  Item = CMediaServerFolder::_GetItem((CMediaServerFolder *)((char *)v48 - 16), v16, &v44);
  if ( Item == -2147024829 )
  {
    if ( WindowsIsStringEmpty(v45) )
      goto LABEL_66;
    v42 = &v45;
    CurrentThreadId = GetCurrentThreadId();
    Item = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_88f464e67b6dfb4d6f0af93dc2251f1b___(
             v38,
             CurrentThreadId,
             &v42);
    if ( Item < 0 )
      goto LABEL_66;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)v36 + 136);
    Item = CMediaServerFolder::_GetItem((CMediaServerFolder *)((char *)v36 - 16), v16, &v44);
  }
  if ( Item < 0 )
  {
LABEL_66:
    v8 = v44;
    goto LABEL_67;
  }
  if ( *v21 )
  {
    v42 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v42);
    v39 = v52;
    v8 = v44;
    Item = CMediaServerFolder::BindToObject(v48, v44, v52, &GUID_000214e6_0000_0000_c000_000000000046, &v42);
    if ( Item >= 0 )
    {
      *(_QWORD *)length = 0;
      Item = (*(__int64 (__fastcall **)(void *, HWND, struct IBindCtx *, _WORD *, _QWORD, UINT32 *, unsigned int *))(*(_QWORD *)v42 + 24LL))(
               v42,
               v53,
               v39,
               v21,
               0,
               length,
               v51);
      if ( Item >= 0 )
        Item = CombineIDLists(v8, *(const struct _ITEMIDLIST_RELATIVE **)length, v50);
      v40 = *(const struct _ITEMIDLIST_RELATIVE **)length;
      *(_QWORD *)length = 0;
      CoTaskMemFree(v40);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v42);
  }
  else
  {
    v8 = 0;
    *v50 = v44;
    if ( v51 && *v51 )
    {
      *v51 &= 0xA8840054;
      Item = 0;
    }
  }
LABEL_67:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((Item >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids,
      (unsigned int)Item);
  }
  if ( v11 )
    WindowsDeleteString(v11);
  if ( v10 )
    WindowsDeleteString(v10);
  if ( v45 )
    WindowsDeleteString(v45);
  LocalFree(v9);
  CoTaskMemFree(v8);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x180001c70  push    rbp
0x180001c72  push    rbx
0x180001c73  push    rsi
0x180001c74  push    rdi
0x180001c75  push    r12
0x180001c77  push    r13
0x180001c79  push    r14
0x180001c7b  push    r15
0x180001c7d  lea     rbp, [rsp-7]
0x180001c82  sub     rsp, 0D8h
0x180001c89  mov     rax, cs:__security_cookie
0x180001c90  xor     rax, rsp
0x180001c93  mov     [rbp+3Fh+var_48], rax
0x180001c97  mov     r12, r9
0x180001c9a  mov     [rsp+110h+var_D0], r9
0x180001c9f  mov     [rbp+3Fh+var_80], r8
0x180001ca3  mov     [rbp+3Fh+var_78], rdx
0x180001ca7  mov     [rbp+3Fh+var_A0], rcx
0x180001cab  mov     r15, [rbp+3Fh+arg_28]
0x180001caf  mov     [rbp+3Fh+var_90], r15
0x180001cb3  mov     rax, [rbp+3Fh+arg_30]
0x180001cb7  mov     [rbp+3Fh+var_88], rax
0x180001cbb  xor     r13d, r13d
0x180001cbe  mov     edi, r13d
0x180001cc1  mov     [rsp+110h+var_C0], r13
0x180001cc6  mov     ebx, r13d
0x180001cc9  mov     [rbp+3Fh+var_A8], rbx
0x180001ccd  mov     [rbp+3Fh+var_B8], r13
0x180001cd1  mov     esi, r13d
0x180001cd4  mov     [rbp+3Fh+var_B0], r13
0x180001cd8  mov     r14d, r13d
0x180001cdb  mov     [rbp+3Fh+var_98], r13
0x180001cdf  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180001ce6  nop     word ptr [rax+rax+00000000h]
0x180001cf0  inc     rdx; length
0x180001cf3  cmp     word ptr [r9+rdx*2], 0
0x180001cf9  jnz     short loc_180001CF0
0x180001cfb  lea     r9, [rbp+3Fh+string]; string
0x180001cff  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x180001d03  mov     rcx, r12; sourceString
0x180001d06  call    cs:__imp_WindowsCreateStringReference
0x180001d0c  test    eax, eax
0x180001d0e  jns     short loc_180001D26
0x180001d10  xor     r9d, r9d; lpArguments
0x180001d13  xor     r8d, r8d; nNumberOfArguments
0x180001d16  mov     edx, 1; dwExceptionFlags
0x180001d1b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180001d20  call    cs:__imp_RaiseException
0x180001d26  mov     [r15], r13
0x180001d29  mov     [rsp+110h+length], r13d
0x180001d2e  lea     rdx, [rsp+110h+length]; length
0x180001d33  mov     rcx, [rbp+3Fh+string]; string
0x180001d37  call    cs:__imp_WindowsGetStringRawBuffer
0x180001d3d  cmp     [rsp+110h+length], 10h
0x180001d42  jbe     loc_180001DEA
0x180001d48  mov     [rsp+110h+bIgnoreCase], 1; bIgnoreCase
0x180001d50  mov     r9d, 10h; cchCount2
0x180001d56  lea     r8, String2; "dlna-playsingle:"
0x180001d5d  mov     edx, r9d; cchCount1
0x180001d60  mov     rcx, rax; lpString1
0x180001d63  call    cs:__imp_CompareStringOrdinal
0x180001d69  cmp     eax, 2
0x180001d6c  jnz     short loc_180001DEA
0x180001d6e  lea     r8, [rbp+3Fh+var_B0]; HSTRING *
0x180001d72  lea     rdx, [rbp+3Fh+var_B8]; HSTRING
0x180001d76  mov     rcx, [rbp+3Fh+string]; this
0x180001d7a  call    ?ParsePlaysingleUrl@DlnaUrlHelpers@@YAJPEAUHSTRING__@@PEAPEAU2@1@Z; DlnaUrlHelpers::ParsePlaysingleUrl(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180001d7f  mov     r12d, eax
0x180001d82  test    eax, eax
0x180001d84  js      short loc_180001DE1
0x180001d86  xor     edx, edx; length
0x180001d88  mov     rcx, [rbp+3Fh+var_B8]; string
0x180001d8c  call    cs:__imp_WindowsGetStringRawBuffer
0x180001d92  mov     r15, rax
0x180001d95  xor     edx, edx; length
0x180001d97  mov     rsi, [rbp+3Fh+var_B0]
0x180001d9b  mov     rcx, rsi; string
0x180001d9e  call    cs:__imp_WindowsGetStringRawBuffer
0x180001da4  mov     rcx, rax; unsigned __int16 *
0x180001da7  call    ?ObjectIDNeedsEscaping@CCDSResultsParser@@SAHPEBG@Z; CCDSResultsParser::ObjectIDNeedsEscaping(ushort const *)
0x180001dac  xor     edx, edx; length
0x180001dae  mov     rcx, rsi; string
0x180001db1  test    eax, eax
0x180001db3  jz      short loc_180001DD3
0x180001db5  call    cs:__imp_WindowsGetStringRawBuffer
0x180001dbb  lea     rdx, [rbp+3Fh+var_98]; HSTRING *
0x180001dbf  mov     rcx, rax; unsigned __int16 *
0x180001dc2  call    ?EscapeObjectID@CCDSResultsParser@@SAJPEBGPEAPEAUHSTRING__@@@Z; CCDSResultsParser::EscapeObjectID(ushort const *,HSTRING__ * *)
0x180001dc7  mov     r12d, eax
0x180001dca  xor     edx, edx; length
0x180001dcc  mov     r14, [rbp+3Fh+var_98]
0x180001dd0  mov     rcx, r14; string
0x180001dd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180001dd9  mov     r13, rax
0x180001ddc  jmp     loc_180001F79
0x180001de1  mov     rsi, [rbp+3Fh+var_B0]
0x180001de5  jmp     loc_1800020FD
0x180001dea  mov     r15, r12
0x180001ded  movzx   eax, word ptr [r12]
0x180001df2  test    ax, ax
0x180001df5  jz      short loc_180001E0A
0x180001df7  cmp     ax, 5Ch ; '\'
0x180001dfb  jz      short loc_180001E0A
0x180001dfd  add     r15, 2
0x180001e01  movzx   eax, word ptr [r15]
0x180001e05  test    ax, ax
0x180001e08  jnz     short loc_180001DF7
0x180001e0a  mov     r13, r15
0x180001e0d  sub     r13, r12
0x180001e10  sar     r13, 1
0x180001e13  xor     ebx, ebx
0x180001e15  mov     [rbp+3Fh+var_A8], rbx
0x180001e19  lea     r8, [r13+1]
0x180001e1d  mov     qword ptr [rsp+110h+length], r8
0x180001e22  cmp     r8, r13
0x180001e25  jb      loc_180001F31
0x180001e2b  mov     [rbp+3Fh+var_A8], rbx
0x180001e2f  mov     eax, 2
0x180001e34  mul     r8
0x180001e37  test    rdx, rdx
0x180001e3a  jnz     short loc_180001E64
0x180001e3c  mov     rdx, rax; uBytes
0x180001e3f  xor     ecx, ecx; uFlags
0x180001e41  call    cs:__imp_LocalAlloc
0x180001e47  mov     rbx, rax
0x180001e4a  mov     [rbp+3Fh+var_A8], rax
0x180001e4e  xor     eax, eax
0x180001e50  mov     r12d, 8007000Eh
0x180001e56  test    rbx, rbx
0x180001e59  cmovnz  r12d, eax
0x180001e5d  mov     r8, qword ptr [rsp+110h+length]
0x180001e62  jmp     short loc_180001E6A
0x180001e64  mov     r12d, 80070216h
0x180001e6a  test    r12d, r12d
0x180001e6d  js      loc_180001F37
0x180001e73  test    rbx, rbx
0x180001e76  jnz     short loc_180001E7D
0x180001e78  test    r8, r8
0x180001e7b  jnz     short loc_180001E86
0x180001e7d  cmp     r8, 7FFFFFFFh
0x180001e84  jbe     short loc_180001E90
0x180001e86  xor     eax, eax
0x180001e88  mov     [rbx], ax
0x180001e8b  jmp     loc_180001F22
0x180001e90  cmp     r13, 7FFFFFFFh
0x180001e97  jb      short loc_180001EA9
0x180001e99  test    r8, r8
0x180001e9c  jz      loc_180001F22
0x180001ea2  xor     eax, eax
0x180001ea4  mov     [rbx], ax
0x180001ea7  jmp     short loc_180001F22
0x180001ea9  test    r8, r8
0x180001eac  jz      short loc_180001F22
0x180001eae  mov     r9, r8
0x180001eb1  mov     r10, rbx
0x180001eb4  xor     ecx, ecx
0x180001eb6  mov     rax, [rsp+110h+var_D0]
0x180001ebb  test    r13, r13
0x180001ebe  jz      short loc_180001EE0
0x180001ec0  movzx   edx, word ptr [rax]
0x180001ec3  test    dx, dx
0x180001ec6  jz      short loc_180001EE0
0x180001ec8  add     rax, 2
0x180001ecc  mov     [r10], dx
0x180001ed0  add     r10, 2
0x180001ed4  dec     r13
0x180001ed7  inc     rcx
0x180001eda  sub     r9, 1
0x180001ede  jnz     short loc_180001EBB
0x180001ee0  lea     rdx, [rcx-1]
0x180001ee4  test    r9, r9
0x180001ee7  cmovnz  rdx, rcx
0x180001eeb  lea     rcx, [r10-2]
0x180001eef  cmovnz  rcx, r10
0x180001ef3  xor     eax, eax
0x180001ef5  mov     [rcx], ax
0x180001ef8  test    r9, r9
0x180001efb  jz      short loc_180001F22
0x180001efd  sub     r8, rdx
0x180001f00  cmp     r8, 1
0x180001f04  jbe     short loc_180001F22
0x180001f06  add     r8, r8
0x180001f09  cmp     r8, 2
0x180001f0d  jbe     short loc_180001F22
0x180001f0f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180001f13  lea     rcx, [rdx+1]
0x180001f17  lea     rcx, [rbx+rcx*2]; void *
0x180001f1b  xor     edx, edx; Val
0x180001f1d  call    memset_0
0x180001f22  lea     r13, [r15+2]
0x180001f26  cmp     word ptr [r15], 0
0x180001f2b  cmovz   r13, r15
0x180001f2f  jmp     short loc_180001F3C
0x180001f31  mov     r12d, 80070216h
0x180001f37  mov     r13, [rsp+110h+var_D0]
0x180001f3c  test    r12d, r12d
0x180001f3f  js      loc_1800020FD
0x180001f45  mov     [rsp+110h+bIgnoreCase], 1; bIgnoreCase
0x180001f4d  mov     r9d, 5; cchCount2
0x180001f53  lea     r8, aUuid; "uuid:"
0x180001f5a  mov     edx, r9d; cchCount1
0x180001f5d  mov     rcx, rbx; lpString1
0x180001f60  call    cs:__imp_CompareStringOrdinal
0x180001f66  cmp     eax, 2
0x180001f69  jz      short loc_180001F76
0x180001f6b  mov     r12d, 80070043h
0x180001f71  jmp     loc_1800020FD
0x180001f76  mov     r15, rbx
0x180001f79  test    r12d, r12d
0x180001f7c  js      loc_1800020FD
0x180001f82  mov     rdi, [rbp+3Fh+var_A0]
0x180001f86  lea     r8, [rsp+110h+var_C0]; struct _ITEMID_CHILD **
0x180001f8b  mov     rdx, r15; unsigned __int16 *
0x180001f8e  lea     rcx, [rdi-10h]; this
0x180001f92  call    ?_GetItem@CMediaServerFolder@@AEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z; CMediaServerFolder::_GetItem(ushort const *,_ITEMID_CHILD * *)
0x180001f97  mov     r12d, eax
0x180001f9a  cmp     eax, 80070043h
0x180001f9f  jnz     short loc_180001FF9
0x180001fa1  mov     rcx, [rbp+3Fh+var_B8]; string
0x180001fa5  call    cs:__imp_WindowsIsStringEmpty
0x180001fab  test    eax, eax
0x180001fad  jnz     loc_1800020F8
0x180001fb3  lea     rax, [rbp+3Fh+var_B8]
0x180001fb7  mov     [rsp+110h+var_D0], rax
0x180001fbc  call    cs:__imp_GetCurrentThreadId
0x180001fc2  lea     r8, [rsp+110h+var_D0]
0x180001fc7  mov     edx, eax
0x180001fc9  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_88f464e67b6dfb4d6f0af93dc2251f1b___
0x180001fce  mov     r12d, eax
0x180001fd1  test    eax, eax
0x180001fd3  js      loc_1800020F8
0x180001fd9  lea     rcx, [rdi+88h]
0x180001fe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180001fe5  lea     r8, [rsp+110h+var_C0]; struct _ITEMID_CHILD **
0x180001fea  mov     rdx, r15; unsigned __int16 *
0x180001fed  lea     rcx, [rdi-10h]; this
0x180001ff1  call    ?_GetItem@CMediaServerFolder@@AEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z; CMediaServerFolder::_GetItem(ushort const *,_ITEMID_CHILD * *)
0x180001ff6  mov     r12d, eax
0x180001ff9  test    r12d, r12d
0x180001ffc  js      loc_1800020F8
0x180002002  cmp     word ptr [r13+0], 0
0x180002008  jz      loc_1800020CD
0x18000200e  mov     [rsp+110h+var_D0], 0
0x180002017  lea     rcx, [rsp+110h+var_D0]
0x18000201c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002021  lea     rax, [rsp+110h+var_D0]
0x180002026  mov     qword ptr [rsp+110h+bIgnoreCase], rax; void **
0x18000202b  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x180002032  mov     r15, [rbp+3Fh+var_80]
0x180002036  mov     r8, r15; struct IBindCtx *
0x180002039  mov     rdi, [rsp+110h+var_C0]
0x18000203e  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180002041  mov     rcx, [rbp+3Fh+var_A0]; this
0x180002045  call    ?BindToObject@CMediaServerFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CMediaServerFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)
0x18000204a  mov     r12d, eax
0x18000204d  test    eax, eax
0x18000204f  js      short loc_1800020C1
0x180002051  mov     qword ptr [rsp+110h+length], 0
0x18000205a  mov     rcx, [rsp+110h+var_D0]
0x18000205f  mov     rax, [rcx]
0x180002062  mov     r9, [rbp+3Fh+var_88]
0x180002066  mov     [rsp+110h+var_E0], r9
0x18000206b  lea     rdx, [rsp+110h+length]
0x180002070  mov     [rsp+110h+var_E8], rdx
0x180002075  mov     qword ptr [rsp+110h+bIgnoreCase], 0
0x18000207e  mov     r9, r13
0x180002081  mov     r8, r15
0x180002084  mov     rdx, [rbp+3Fh+var_78]
0x180002088  mov     rax, [rax+18h]
0x18000208c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002091  mov     r12d, eax
0x180002094  test    eax, eax
0x180002096  js      short loc_1800020AC
0x180002098  mov     r8, [rbp+3Fh+var_90]; struct _ITEMIDLIST_ABSOLUTE **
0x18000209c  mov     rdx, qword ptr [rsp+110h+length]; struct _ITEMIDLIST_RELATIVE *
0x1800020a1  mov     rcx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x1800020a4  call    ?CombineIDLists@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; CombineIDLists(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800020a9  mov     r12d, eax
0x1800020ac  mov     rcx, qword ptr [rsp+110h+length]; pv
0x1800020b1  mov     qword ptr [rsp+110h+length], 0
0x1800020ba  call    cs:__imp_CoTaskMemFree
0x1800020c0  nop
0x1800020c1  lea     rcx, [rsp+110h+var_D0]
0x1800020c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800020cb  jmp     short loc_1800020FD
0x1800020cd  mov     rax, [rsp+110h+var_C0]
0x1800020d2  xor     edi, edi
0x1800020d4  mov     rcx, [rbp+3Fh+var_90]
0x1800020d8  mov     [rcx], rax
0x1800020db  mov     r9, [rbp+3Fh+var_88]
0x1800020df  test    r9, r9
0x1800020e2  jz      short loc_1800020FD
0x1800020e4  mov     eax, [r9]
0x1800020e7  test    eax, eax
0x1800020e9  jz      short loc_1800020FD
0x1800020eb  and     eax, 0A8840054h
0x1800020f0  mov     [r9], eax
0x1800020f3  xor     r12d, r12d
0x1800020f6  jmp     short loc_1800020FD
0x1800020f8  mov     rdi, [rsp+110h+var_C0]
  ... truncated ...
```
