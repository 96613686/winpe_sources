# GetSiufPayloadFromJson(uchar *,uint,ushort * *,uint *)

- ea: `0x140012e10`
- end: `0x1400131f2`
- name: `?GetSiufPayloadFromJson@@YAJPEAEIPEAPEAGPEAI@Z`
- size: `994`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned int cbMultiByte, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012928`

## callees

- `0x1400019a8`
- `0x14000ac50`
- `0x14000d9b0`
- `0x140012e10`
- `0x1400131f8`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012ef0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012ef0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013147`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001315b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001315b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400130a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400131ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400130a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400131ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400130cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140013065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400130cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013102`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012f9d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012f9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012e9f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012f29`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012e9f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012f29`

## string_xrefs

- `0x140012f73`: `Windows.Data.Json.JsonObject`
- `0x14001300f`: `Json not parsed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSiufPayloadFromJson(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  signed int ActivationFactory; // ebx
  int v9; // eax
  int cchWideChar; // r14d
  signed int v11; // eax
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v15; // rdi
  unsigned int v16; // esi
  signed int LastError; // eax
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 **, _BYTE *); // rbx
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rbx
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int64 v30; // rbx
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  const WCHAR *StringRawBuffer; // rax
  HANDLE v35; // rax
  _BYTE v37[4]; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-55h] BYREF
  UINT32 length; // [rsp+48h] [rbp-51h] BYREF
  HSTRING v40; // [rsp+50h] [rbp-49h] BYREF
  __int64 v41; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v42; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v43; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v44; // [rsp+70h] [rbp-29h] BYREF
  WCHAR *v45; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  HSTRING string; // [rsp+98h] [rbp-1h] BYREF

  v41 = 0;
  v42 = 0;
  v43 = 0;
  v37[0] = 0;
  v40 = 0;
  length = 0;
  v44 = 0;
  v38 = 0;
  if ( lpMultiByteStr && a3 && a4 )
  {
    if ( cbMultiByte )
    {
      v9 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
      cchWideChar = v9;
      if ( v9 )
      {
        v12 = 2 * v9;
        ProcessHeap = GetProcessHeap();
        lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v12);
        v15 = lpWideCharStr;
        v45 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          v16 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar);
          if ( v16 )
          {
            string = 0;
            v18 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
            if ( v18 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
              __debugbreak();
            }
            ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v41);
            if ( ActivationFactory >= 0 )
            {
              v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **, _BYTE *))(*(_QWORD *)v41 + 56LL);
              v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v45);
              ActivationFactory = v21(v41, *(_QWORD *)(v22 + 24), &v42, v37);
              if ( ActivationFactory >= 0 )
              {
                if ( v37[0] )
                {
                  v26 = *v42;
                  string = 0;
                  v27 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &string);
                  if ( v27 < 0 )
                  {
                    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
                    JUMPOUT(0x1400131F1LL);
                  }
                  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v26 + 64))(
                                        v42,
                                        string,
                                        &v43);
                  if ( ActivationFactory >= 0 )
                  {
                    v30 = *v43;
                    WindowsDeleteString(v40);
                    v40 = 0;
                    string = 0;
                    v31 = WindowsCreateStringReference(L"LOCSTRING", 9u, &hstringHeader, &string);
                    if ( v31 < 0 )
                    {
                      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
                      __debugbreak();
                    }
                    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v30 + 80))(
                                          v43,
                                          string,
                                          &v40);
                    if ( ActivationFactory >= 0 )
                    {
                      StringRawBuffer = WindowsGetStringRawBuffer(v40, &length);
                      if ( StringRawBuffer )
                      {
                        ActivationFactory = GetWideStringFromBase64(StringRawBuffer, length, &v44, &v38);
                        if ( ActivationFactory >= 0 )
                        {
                          *a3 = v44;
                          *a4 = v38;
                        }
                      }
                      else
                      {
                        ActivationFactory = -2141334526;
                      }
                    }
                  }
                }
                else
                {
                  ActivationFactory = -2141334527;
                  if ( (unsigned int)dword_140028000 > 5 )
                  {
                    v45 = v15;
                    v38 = v16;
                    v44 = (unsigned __int16 *)"Json not parsed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                      v23,
                      (unsigned int)byte_1400236D1,
                      v24,
                      v25,
                      (__int64)&v44,
                      (__int64)&v38,
                      (__int64)&v45);
                  }
                }
              }
            }
          }
          else
          {
            LastError = GetLastError();
            ActivationFactory = LastError;
            if ( LastError > 0 )
              ActivationFactory = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          ActivationFactory = -2147024882;
        }
        if ( v15 )
        {
          v35 = GetProcessHeap();
          HeapFree(v35, 0, v15);
        }
      }
      else
      {
        v11 = GetLastError();
        ActivationFactory = v11;
        if ( v11 > 0 )
          ActivationFactory = (unsigned __int16)v11 | 0x80070000;
      }
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v42 )
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      if ( v43 )
        (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    }
    else
    {
      ActivationFactory = -2147024809;
    }
  }
  else
  {
    ActivationFactory = -2147467261;
  }
  WindowsDeleteString(v40);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x140012e10  push    rbp
0x140012e12  push    rbx
0x140012e13  push    rsi
0x140012e14  push    rdi
0x140012e15  push    r12
0x140012e17  push    r13
0x140012e19  push    r14
0x140012e1b  push    r15
0x140012e1d  lea     rbp, [rsp-1Fh]
0x140012e22  sub     rsp, 0B8h
0x140012e29  mov     rax, cs:__security_cookie
0x140012e30  xor     rax, rsp
0x140012e33  mov     [rbp+57h+var_50], rax
0x140012e37  mov     r13, r9
0x140012e3a  mov     r12, r8
0x140012e3d  mov     esi, edx
0x140012e3f  mov     r15, rcx
0x140012e42  xor     edi, edi
0x140012e44  mov     [rbp+57h+var_98], rdi
0x140012e48  mov     [rbp+57h+var_90], rdi
0x140012e4c  mov     [rbp+57h+var_88], rdi
0x140012e50  mov     [rbp+57h+var_B0], dil
0x140012e54  mov     [rbp+57h+var_A0], rdi
0x140012e58  mov     [rbp+57h+length], edi
0x140012e5b  mov     [rbp+57h+var_80], rdi
0x140012e5f  mov     [rbp+57h+var_AC], edi
0x140012e62  test    rcx, rcx
0x140012e65  jnz     short loc_140012E71
0x140012e67  mov     ebx, 80004003h
0x140012e6c  jmp     loc_1400131A7
0x140012e71  test    r12, r12
0x140012e74  jz      short loc_140012E67
0x140012e76  test    r13, r13
0x140012e79  jz      short loc_140012E67
0x140012e7b  test    esi, esi
0x140012e7d  jnz     short loc_140012E89
0x140012e7f  mov     ebx, 80070057h
0x140012e84  jmp     loc_1400131A7
0x140012e89  mov     [rsp+0F0h+cchWideChar], edi; cchWideChar
0x140012e8d  mov     [rsp+0F0h+lpWideCharStr], rdi; lpWideCharStr
0x140012e92  mov     r9d, esi; cbMultiByte
0x140012e95  mov     r8, r15; lpMultiByteStr
0x140012e98  xor     edx, edx; dwFlags
0x140012e9a  mov     ecx, 0FDE9h; CodePage
0x140012e9f  call    cs:__imp_MultiByteToWideChar
0x140012ea6  nop     dword ptr [rax+rax+00h]
0x140012eab  mov     r14d, eax
0x140012eae  test    eax, eax
0x140012eb0  jnz     short loc_140012ED6
0x140012eb2  call    cs:__imp_GetLastError
0x140012eb9  nop     dword ptr [rax+rax+00h]
0x140012ebe  mov     ebx, eax
0x140012ec0  test    eax, eax
0x140012ec2  jle     loc_140013167
0x140012ec8  movzx   ebx, ax
0x140012ecb  or      ebx, 80070000h
0x140012ed1  jmp     loc_140013167
0x140012ed6  lea     ebx, [rax+rax]
0x140012ed9  call    cs:__imp_GetProcessHeap
0x140012ee0  nop     dword ptr [rax+rax+00h]
0x140012ee5  mov     rcx, rax; hHeap
0x140012ee8  mov     r8d, ebx; dwBytes
0x140012eeb  mov     edx, 8; dwFlags
0x140012ef0  call    cs:__imp_HeapAlloc
0x140012ef7  nop     dword ptr [rax+rax+00h]
0x140012efc  mov     rdi, rax
0x140012eff  mov     [rbp+57h+var_78], rax
0x140012f03  test    rax, rax
0x140012f06  jnz     short loc_140012F12
0x140012f08  mov     ebx, 8007000Eh
0x140012f0d  jmp     loc_140013142
0x140012f12  mov     [rsp+0F0h+cchWideChar], r14d; cchWideChar
0x140012f17  mov     [rsp+0F0h+lpWideCharStr], rdi; lpWideCharStr
0x140012f1c  mov     r9d, esi; cbMultiByte
0x140012f1f  mov     r8, r15; lpMultiByteStr
0x140012f22  xor     edx, edx; dwFlags
0x140012f24  mov     ecx, 0FDE9h; CodePage
0x140012f29  call    cs:__imp_MultiByteToWideChar
0x140012f30  nop     dword ptr [rax+rax+00h]
0x140012f35  mov     esi, eax
0x140012f37  xor     r14d, r14d
0x140012f3a  test    eax, eax
0x140012f3c  jnz     short loc_140012F62
0x140012f3e  call    cs:__imp_GetLastError
0x140012f45  nop     dword ptr [rax+rax+00h]
0x140012f4a  mov     ebx, eax
0x140012f4c  test    eax, eax
0x140012f4e  jle     loc_140013142
0x140012f54  movzx   ebx, ax
0x140012f57  or      ebx, 80070000h
0x140012f5d  jmp     loc_140013142
0x140012f62  mov     [rbp+57h+string], r14
0x140012f66  lea     r9, [rbp+57h+string]; string
0x140012f6a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140012f6e  mov     edx, 1Ch; length
0x140012f73  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140012f7a  call    cs:__imp_WindowsCreateStringReference
0x140012f81  nop     dword ptr [rax+rax+00h]
0x140012f86  test    eax, eax
0x140012f88  js      loc_1400131E2
0x140012f8e  lea     r8, [rbp+57h+var_98]
0x140012f92  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x140012f99  mov     rcx, [rbp+57h+string]
0x140012f9d  call    cs:__imp_RoGetActivationFactory
0x140012fa4  nop     dword ptr [rax+rax+00h]
0x140012fa9  mov     ebx, eax
0x140012fab  test    eax, eax
0x140012fad  js      loc_140013142
0x140012fb3  mov     rax, [rbp+57h+var_98]
0x140012fb7  mov     rcx, [rax]
0x140012fba  mov     rbx, [rcx+38h]
0x140012fbe  lea     rdx, [rbp+57h+var_78]
0x140012fc2  lea     rcx, [rbp+57h+hstringHeader]
0x140012fc6  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x140012fcb  nop
0x140012fcc  lea     r9, [rbp+57h+var_B0]
0x140012fd0  lea     r8, [rbp+57h+var_90]
0x140012fd4  mov     rdx, [rax+18h]
0x140012fd8  mov     rcx, [rbp+57h+var_98]
0x140012fdc  mov     rax, rbx
0x140012fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fe4  mov     ebx, eax
0x140012fe6  test    eax, eax
0x140012fe8  js      loc_140013142
0x140012fee  cmp     [rbp+57h+var_B0], r14b
0x140012ff2  jnz     short loc_140013046
0x140012ff4  mov     ebx, 805DD401h
0x140012ff9  mov     eax, cs:dword_140028000
0x140012fff  cmp     eax, 5
0x140013002  jbe     loc_140013142
0x140013008  mov     [rbp+57h+var_78], rdi
0x14001300c  mov     [rbp+57h+var_AC], esi
0x14001300f  lea     rax, aJsonNotParsed; "Json not parsed"
0x140013016  mov     [rbp+57h+var_80], rax
0x14001301a  lea     rax, [rbp+57h+var_78]
0x14001301e  mov     [rsp+0F0h+var_C0], rax
0x140013023  lea     rax, [rbp+57h+var_AC]
0x140013027  mov     qword ptr [rsp+0F0h+cchWideChar], rax
0x14001302c  lea     rax, [rbp+57h+var_80]
0x140013030  mov     [rsp+0F0h+lpWideCharStr], rax
0x140013035  lea     rdx, byte_1400236D1
0x14001303c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140013041  jmp     loc_140013142
0x140013046  mov     rax, [rbp+57h+var_90]
0x14001304a  mov     rbx, [rax]
0x14001304d  mov     [rbp+57h+string], r14
0x140013051  lea     r9, [rbp+57h+string]; string
0x140013055  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140013059  mov     edx, 8; length
0x14001305e  lea     rcx, aSettings; "settings"
0x140013065  call    cs:__imp_WindowsCreateStringReference
0x14001306c  nop     dword ptr [rax+rax+00h]
0x140013071  test    eax, eax
0x140013073  js      loc_1400131EA
0x140013079  lea     r8, [rbp+57h+var_88]
0x14001307d  mov     rdx, [rbp+57h+string]
0x140013081  mov     rcx, [rbp+57h+var_90]
0x140013085  mov     rax, [rbx+40h]
0x140013089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001308e  mov     ebx, eax
0x140013090  test    eax, eax
0x140013092  js      loc_140013142
0x140013098  mov     rax, [rbp+57h+var_88]
0x14001309c  mov     rbx, [rax]
0x14001309f  mov     rcx, [rbp+57h+var_A0]; string
0x1400130a3  call    cs:__imp_WindowsDeleteString
0x1400130aa  nop     dword ptr [rax+rax+00h]
0x1400130af  mov     [rbp+57h+var_A0], r14
0x1400130b3  mov     [rbp+57h+string], r14
0x1400130b7  lea     r9, [rbp+57h+string]; string
0x1400130bb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400130bf  mov     edx, 9; length
0x1400130c4  lea     rcx, aLocstring; "LOCSTRING"
0x1400130cb  call    cs:__imp_WindowsCreateStringReference
0x1400130d2  nop     dword ptr [rax+rax+00h]
0x1400130d7  test    eax, eax
0x1400130d9  js      loc_1400131DA
0x1400130df  lea     r8, [rbp+57h+var_A0]
0x1400130e3  mov     rdx, [rbp+57h+string]
0x1400130e7  mov     rcx, [rbp+57h+var_88]
0x1400130eb  mov     rax, [rbx+50h]
0x1400130ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400130f4  mov     ebx, eax
0x1400130f6  test    eax, eax
0x1400130f8  js      short loc_140013142
0x1400130fa  lea     rdx, [rbp+57h+length]; length
0x1400130fe  mov     rcx, [rbp+57h+var_A0]; string
0x140013102  call    cs:__imp_WindowsGetStringRawBuffer
0x140013109  nop     dword ptr [rax+rax+00h]
0x14001310e  test    rax, rax
0x140013111  jnz     short loc_14001311A
0x140013113  mov     ebx, 805DD402h
0x140013118  jmp     short loc_140013142
0x14001311a  lea     r9, [rbp+57h+var_AC]; unsigned int *
0x14001311e  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x140013122  mov     edx, [rbp+57h+length]; cchString
0x140013125  mov     rcx, rax; pszString
0x140013128  call    ?GetWideStringFromBase64@@YAJPEBGIPEAPEAGPEAI@Z; GetWideStringFromBase64(ushort const *,uint,ushort * *,uint *)
0x14001312d  mov     ebx, eax
0x14001312f  test    eax, eax
0x140013131  js      short loc_140013142
0x140013133  mov     rax, [rbp+57h+var_80]
0x140013137  mov     [r12], rax
0x14001313b  mov     eax, [rbp+57h+var_AC]
0x14001313e  mov     [r13+0], eax
0x140013142  test    rdi, rdi
0x140013145  jz      short loc_140013167
0x140013147  call    cs:__imp_GetProcessHeap
0x14001314e  nop     dword ptr [rax+rax+00h]
0x140013153  mov     r8, rdi; lpMem
0x140013156  xor     edx, edx; dwFlags
0x140013158  mov     rcx, rax; hHeap
0x14001315b  call    cs:__imp_HeapFree
0x140013162  nop     dword ptr [rax+rax+00h]
0x140013167  mov     rcx, [rbp+57h+var_98]
0x14001316b  test    rcx, rcx
0x14001316e  jz      short loc_14001317C
0x140013170  mov     rax, [rcx]
0x140013173  mov     rax, [rax+10h]
0x140013177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001317c  mov     rcx, [rbp+57h+var_90]
0x140013180  test    rcx, rcx
0x140013183  jz      short loc_140013191
0x140013185  mov     rax, [rcx]
0x140013188  mov     rax, [rax+10h]
0x14001318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013191  mov     rcx, [rbp+57h+var_88]
0x140013195  test    rcx, rcx
0x140013198  jz      short loc_1400131A7
0x14001319a  mov     rax, [rcx]
0x14001319d  mov     rax, [rax+10h]
0x1400131a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131a6  nop
0x1400131a7  mov     rcx, [rbp+57h+var_A0]; string
0x1400131ab  call    cs:__imp_WindowsDeleteString
0x1400131b2  nop     dword ptr [rax+rax+00h]
0x1400131b7  mov     eax, ebx
0x1400131b9  mov     rcx, [rbp+57h+var_50]
0x1400131bd  xor     rcx, rsp; StackCookie
0x1400131c0  call    __security_check_cookie
0x1400131c5  add     rsp, 0B8h
0x1400131cc  pop     r15
0x1400131ce  pop     r14
0x1400131d0  pop     r13
0x1400131d2  pop     r12
0x1400131d4  pop     rdi
0x1400131d5  pop     rsi
0x1400131d6  pop     rbx
0x1400131d7  pop     rbp
0x1400131d8  retn
0x1400131da  mov     ecx, eax; this
0x1400131dc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400131e1  int     3; Trap to Debugger
0x1400131e2  mov     ecx, eax; this
0x1400131e4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400131e9  int     3; Trap to Debugger
0x1400131ea  mov     ecx, eax; this
0x1400131ec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
