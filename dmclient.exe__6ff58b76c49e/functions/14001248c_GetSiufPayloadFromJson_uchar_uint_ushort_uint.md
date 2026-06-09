# GetSiufPayloadFromJson(uchar *,uint,ushort * *,uint *)

- ea: `0x14001248c`
- end: `0x14001285b`
- name: `?GetSiufPayloadFromJson@@YAJPEAEIPEAPEAGPEAI@Z`
- size: `975`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011fec`

## callees

- `0x140001990`
- `0x14000a9f0`
- `0x14001248c`
- `0x140012864`
- `0x1400187e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012556`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012545`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400125aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012545`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400125aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400125b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400125b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400127df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400127df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400126ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400127ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400126ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400127ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001278c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001278c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001265f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001265f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001251a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012582`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001251a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140012582`

## string_xrefs

- `0x14001263b`: `Windows.Data.Json.JsonObject`
- `0x1400126fe`: `Json not parsed`

## pseudocode

```c
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
  WCHAR *v15; // rsi
  unsigned int v16; // edi
  signed int LastError; // eax
  HANDLE v18; // rax
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  __int64 v24; // rbx
  unsigned __int64 v25; // rdx
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rbx
  HRESULT v33; // eax
  int v34; // edx
  unsigned int v35; // r8d
  __int64 v36; // rbx
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  const WCHAR *StringRawBuffer; // rax
  _BYTE v41[4]; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v42; // [rsp+44h] [rbp-55h] BYREF
  UINT32 length; // [rsp+48h] [rbp-51h] BYREF
  HSTRING string; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v45; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v46; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v47; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v48; // [rsp+70h] [rbp-29h] BYREF
  const char *v49; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  HSTRING v51; // [rsp+98h] [rbp-1h] BYREF

  v45 = 0;
  v46 = 0;
  v47 = 0;
  v41[0] = 0;
  string = 0;
  length = 0;
  v48 = 0;
  v42 = 0;
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
        if ( lpWideCharStr )
        {
          v16 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar);
          if ( v16 )
          {
            v51 = 0;
            v20 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &v51);
            if ( v20 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
              __debugbreak();
            }
            ActivationFactory = RoGetActivationFactory(v51, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v45);
            if ( ActivationFactory >= 0 )
            {
              v24 = *v45;
              v51 = 0;
              v25 = -1;
              do
                ++v25;
              while ( v15[v25] );
              if ( v25 > 0xFFFFFFFF )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v25, v23);
                __debugbreak();
              }
              if ( (int)v25 + 1 < (unsigned int)v25 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v25, v23);
                __debugbreak();
              }
              v26 = WindowsCreateStringReference(v15, v25, &hstringHeader, &v51);
              if ( v26 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
                __debugbreak();
              }
              ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **, _BYTE *))(v24 + 56))(
                                    v45,
                                    v51,
                                    &v46,
                                    v41);
              if ( ActivationFactory >= 0 )
              {
                if ( v41[0] )
                {
                  v32 = *v46;
                  v51 = 0;
                  v33 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &v51);
                  if ( v33 < 0 )
                  {
                    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v33, v34, v35);
                    JUMPOUT(0x14001285ALL);
                  }
                  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v32 + 64))(
                                        v46,
                                        v51,
                                        &v47);
                  if ( ActivationFactory >= 0 )
                  {
                    v36 = *v47;
                    WindowsDeleteString(string);
                    string = 0;
                    v51 = 0;
                    v37 = WindowsCreateStringReference(L"LOCSTRING", 9u, &hstringHeader, &v51);
                    if ( v37 < 0 )
                    {
                      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
                      __debugbreak();
                    }
                    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v36 + 80))(
                                          v47,
                                          v51,
                                          &string);
                    if ( ActivationFactory >= 0 )
                    {
                      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
                      if ( StringRawBuffer )
                      {
                        ActivationFactory = GetWideStringFromBase64(StringRawBuffer, length, &v48, &v42);
                        if ( ActivationFactory >= 0 )
                        {
                          *a3 = v48;
                          *a4 = v42;
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
                  if ( (unsigned int)dword_140027000 > 5 )
                  {
                    v48 = v15;
                    v42 = v16;
                    v49 = "Json not parsed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                      v29,
                      (__int64)byte_1400226C9,
                      v30,
                      v31,
                      (const unsigned __int16 **)&v49,
                      (__int64)&v42,
                      (int **)&v48);
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
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v15);
        }
        else
        {
          ActivationFactory = -2147024882;
        }
      }
      else
      {
        v11 = GetLastError();
        ActivationFactory = v11;
        if ( v11 > 0 )
          ActivationFactory = (unsigned __int16)v11 | 0x80070000;
      }
      if ( v45 )
        (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
      if ( v46 )
        (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
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
  WindowsDeleteString(string);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x14001248c  push    rbp
0x14001248e  push    rbx
0x14001248f  push    rsi
0x140012490  push    rdi
0x140012491  push    r12
0x140012493  push    r13
0x140012495  push    r14
0x140012497  push    r15
0x140012499  lea     rbp, [rsp-1Fh]
0x14001249e  sub     rsp, 0B8h
0x1400124a5  mov     rax, cs:__security_cookie
0x1400124ac  xor     rax, rsp
0x1400124af  mov     [rbp+57h+var_50], rax
0x1400124b3  mov     r13, r9
0x1400124b6  mov     r12, r8
0x1400124b9  mov     edi, edx
0x1400124bb  mov     r15, rcx
0x1400124be  xor     ebx, ebx
0x1400124c0  mov     [rbp+57h+var_98], rbx
0x1400124c4  mov     [rbp+57h+var_90], rbx
0x1400124c8  mov     [rbp+57h+var_88], rbx
0x1400124cc  mov     [rbp+57h+var_B0], bl
0x1400124cf  mov     [rbp+57h+string], rbx
0x1400124d3  mov     [rbp+57h+length], ebx
0x1400124d6  mov     [rbp+57h+var_80], rbx
0x1400124da  mov     [rbp+57h+var_AC], ebx
0x1400124dd  test    rcx, rcx
0x1400124e0  jnz     short loc_1400124EC
0x1400124e2  mov     ebx, 80004003h
0x1400124e7  jmp     loc_1400125FE
0x1400124ec  test    r12, r12
0x1400124ef  jz      short loc_1400124E2
0x1400124f1  test    r13, r13
0x1400124f4  jz      short loc_1400124E2
0x1400124f6  test    edi, edi
0x1400124f8  jnz     short loc_140012504
0x1400124fa  mov     ebx, 80070057h
0x1400124ff  jmp     loc_1400125FE
0x140012504  mov     [rsp+0F0h+cchWideChar], ebx; cchWideChar
0x140012508  mov     [rsp+0F0h+lpWideCharStr], rbx; lpWideCharStr
0x14001250d  mov     r9d, edi; cbMultiByte
0x140012510  mov     r8, r15; lpMultiByteStr
0x140012513  xor     edx, edx; dwFlags
0x140012515  mov     ecx, 0FDE9h; CodePage
0x14001251a  call    cs:__imp_MultiByteToWideChar
0x140012520  mov     r14d, eax
0x140012523  test    eax, eax
0x140012525  jnz     short loc_140012542
0x140012527  call    cs:__imp_GetLastError
0x14001252d  mov     ebx, eax
0x14001252f  test    eax, eax
0x140012531  jle     loc_1400125BE
0x140012537  movzx   ebx, ax
0x14001253a  or      ebx, 80070000h
0x140012540  jmp     short loc_1400125BE
0x140012542  lea     ebx, [rax+rax]
0x140012545  call    cs:__imp_GetProcessHeap
0x14001254b  mov     rcx, rax; hHeap
0x14001254e  mov     r8d, ebx; dwBytes
0x140012551  mov     edx, 8; dwFlags
0x140012556  call    cs:__imp_HeapAlloc
0x14001255c  mov     rsi, rax
0x14001255f  test    rax, rax
0x140012562  jnz     short loc_14001256B
0x140012564  mov     ebx, 8007000Eh
0x140012569  jmp     short loc_1400125BE
0x14001256b  mov     [rsp+0F0h+cchWideChar], r14d; cchWideChar
0x140012570  mov     [rsp+0F0h+lpWideCharStr], rsi; lpWideCharStr
0x140012575  mov     r9d, edi; cbMultiByte
0x140012578  mov     r8, r15; lpMultiByteStr
0x14001257b  xor     edx, edx; dwFlags
0x14001257d  mov     ecx, 0FDE9h; CodePage
0x140012582  call    cs:__imp_MultiByteToWideChar
0x140012588  mov     edi, eax
0x14001258a  xor     r14d, r14d
0x14001258d  test    eax, eax
0x14001258f  jnz     loc_14001262A
0x140012595  call    cs:__imp_GetLastError
0x14001259b  mov     ebx, eax
0x14001259d  test    eax, eax
0x14001259f  jle     short loc_1400125AA
0x1400125a1  movzx   ebx, ax
0x1400125a4  or      ebx, 80070000h
0x1400125aa  call    cs:__imp_GetProcessHeap
0x1400125b0  mov     r8, rsi; lpMem
0x1400125b3  xor     edx, edx; dwFlags
0x1400125b5  mov     rcx, rax; hHeap
0x1400125b8  call    cs:__imp_HeapFree
0x1400125be  mov     rcx, [rbp+57h+var_98]
0x1400125c2  test    rcx, rcx
0x1400125c5  jz      short loc_1400125D3
0x1400125c7  mov     rax, [rcx]
0x1400125ca  mov     rax, [rax+10h]
0x1400125ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125d3  mov     rcx, [rbp+57h+var_90]
0x1400125d7  test    rcx, rcx
0x1400125da  jz      short loc_1400125E8
0x1400125dc  mov     rax, [rcx]
0x1400125df  mov     rax, [rax+10h]
0x1400125e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125e8  mov     rcx, [rbp+57h+var_88]
0x1400125ec  test    rcx, rcx
0x1400125ef  jz      short loc_1400125FE
0x1400125f1  mov     rax, [rcx]
0x1400125f4  mov     rax, [rax+10h]
0x1400125f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400125fd  nop
0x1400125fe  mov     rcx, [rbp+57h+string]; string
0x140012602  call    cs:__imp_WindowsDeleteString
0x140012608  mov     eax, ebx
0x14001260a  mov     rcx, [rbp+57h+var_50]
0x14001260e  xor     rcx, rsp; StackCookie
0x140012611  call    __security_check_cookie
0x140012616  add     rsp, 0B8h
0x14001261d  pop     r15
0x14001261f  pop     r14
0x140012621  pop     r13
0x140012623  pop     r12
0x140012625  pop     rdi
0x140012626  pop     rsi
0x140012627  pop     rbx
0x140012628  pop     rbp
0x140012629  retn
0x14001262a  mov     [rbp+57h+var_58], r14
0x14001262e  lea     r9, [rbp+57h+var_58]; string
0x140012632  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140012636  mov     edx, 1Ch; length
0x14001263b  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140012642  call    cs:__imp_WindowsCreateStringReference
0x140012648  test    eax, eax
0x14001264a  js      loc_140012838
0x140012650  lea     r8, [rbp+57h+var_98]
0x140012654  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x14001265b  mov     rcx, [rbp+57h+var_58]
0x14001265f  call    cs:__imp_RoGetActivationFactory
0x140012665  mov     ebx, eax
0x140012667  test    eax, eax
0x140012669  js      loc_1400125AA
0x14001266f  mov     rax, [rbp+57h+var_98]
0x140012673  mov     rbx, [rax]
0x140012676  mov     [rbp+57h+var_58], r14
0x14001267a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001267e  inc     rdx; int
0x140012681  cmp     [rsi+rdx*2], r14w
0x140012686  jnz     short loc_14001267E
0x140012688  mov     eax, 0FFFFFFFFh
0x14001268d  cmp     rdx, rax
0x140012690  ja      loc_14001282D
0x140012696  lea     eax, [rdx+1]
0x140012699  cmp     eax, edx
0x14001269b  jb      loc_140012840
0x1400126a1  lea     r9, [rbp+57h+var_58]; string
0x1400126a5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400126a9  mov     rcx, rsi; sourceString
0x1400126ac  call    cs:__imp_WindowsCreateStringReference
0x1400126b2  test    eax, eax
0x1400126b4  js      loc_14001284B
0x1400126ba  lea     r9, [rbp+57h+var_B0]
0x1400126be  lea     r8, [rbp+57h+var_90]
0x1400126c2  mov     rdx, [rbp+57h+var_58]
0x1400126c6  mov     rcx, [rbp+57h+var_98]
0x1400126ca  mov     rax, [rbx+38h]
0x1400126ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126d3  mov     ebx, eax
0x1400126d5  test    eax, eax
0x1400126d7  js      loc_1400125AA
0x1400126dd  cmp     [rbp+57h+var_B0], r14b
0x1400126e1  jnz     short loc_140012735
0x1400126e3  mov     ebx, 805DD401h
0x1400126e8  mov     eax, cs:dword_140027000
0x1400126ee  cmp     eax, 5
0x1400126f1  jbe     loc_1400125AA
0x1400126f7  mov     [rbp+57h+var_80], rsi
0x1400126fb  mov     [rbp+57h+var_AC], edi
0x1400126fe  lea     rax, aJsonNotParsed; "Json not parsed"
0x140012705  mov     [rbp+57h+var_78], rax
0x140012709  lea     rax, [rbp+57h+var_80]
0x14001270d  mov     [rsp+0F0h+var_C0], rax
0x140012712  lea     rax, [rbp+57h+var_AC]
0x140012716  mov     qword ptr [rsp+0F0h+cchWideChar], rax
0x14001271b  lea     rax, [rbp+57h+var_78]
0x14001271f  mov     [rsp+0F0h+lpWideCharStr], rax
0x140012724  lea     rdx, byte_1400226C9
0x14001272b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140012730  jmp     loc_1400125AA
0x140012735  mov     rax, [rbp+57h+var_90]
0x140012739  mov     rbx, [rax]
0x14001273c  mov     [rbp+57h+var_58], r14
0x140012740  lea     r9, [rbp+57h+var_58]; string
0x140012744  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140012748  mov     edx, 8; length
0x14001274d  lea     rcx, aSettings; "settings"
0x140012754  call    cs:__imp_WindowsCreateStringReference
0x14001275a  test    eax, eax
0x14001275c  js      loc_140012853
0x140012762  lea     r8, [rbp+57h+var_88]
0x140012766  mov     rdx, [rbp+57h+var_58]
0x14001276a  mov     rcx, [rbp+57h+var_90]
0x14001276e  mov     rax, [rbx+40h]
0x140012772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012777  mov     ebx, eax
0x140012779  test    eax, eax
0x14001277b  js      loc_1400125AA
0x140012781  mov     rax, [rbp+57h+var_88]
0x140012785  mov     rbx, [rax]
0x140012788  mov     rcx, [rbp+57h+string]; string
0x14001278c  call    cs:__imp_WindowsDeleteString
0x140012792  mov     [rbp+57h+string], r14
0x140012796  mov     [rbp+57h+var_58], r14
0x14001279a  lea     r9, [rbp+57h+var_58]; string
0x14001279e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1400127a2  mov     edx, 9; length
0x1400127a7  lea     rcx, aLocstring; "LOCSTRING"
0x1400127ae  call    cs:__imp_WindowsCreateStringReference
0x1400127b4  test    eax, eax
0x1400127b6  js      short loc_140012825
0x1400127b8  lea     r8, [rbp+57h+string]
0x1400127bc  mov     rdx, [rbp+57h+var_58]
0x1400127c0  mov     rcx, [rbp+57h+var_88]
0x1400127c4  mov     rax, [rbx+50h]
0x1400127c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127cd  mov     ebx, eax
0x1400127cf  test    eax, eax
0x1400127d1  js      loc_1400125AA
0x1400127d7  lea     rdx, [rbp+57h+length]; length
0x1400127db  mov     rcx, [rbp+57h+string]; string
0x1400127df  call    cs:__imp_WindowsGetStringRawBuffer
0x1400127e5  test    rax, rax
0x1400127e8  jnz     short loc_1400127F4
0x1400127ea  mov     ebx, 805DD402h
0x1400127ef  jmp     loc_1400125AA
0x1400127f4  lea     r9, [rbp+57h+var_AC]; unsigned int *
0x1400127f8  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x1400127fc  mov     edx, [rbp+57h+length]; cchString
0x1400127ff  mov     rcx, rax; pszString
0x140012802  call    ?GetWideStringFromBase64@@YAJPEBGIPEAPEAGPEAI@Z; GetWideStringFromBase64(ushort const *,uint,ushort * *,uint *)
0x140012807  mov     ebx, eax
0x140012809  test    eax, eax
0x14001280b  js      loc_1400125AA
0x140012811  mov     rax, [rbp+57h+var_80]
0x140012815  mov     [r12], rax
0x140012819  mov     eax, [rbp+57h+var_AC]
0x14001281c  mov     [r13+0], eax
0x140012820  jmp     loc_1400125AA
0x140012825  mov     ecx, eax; this
0x140012827  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001282c  int     3; Trap to Debugger
0x14001282d  mov     ecx, 80070216h; this
0x140012832  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140012837  int     3; Trap to Debugger
0x140012838  mov     ecx, eax; this
0x14001283a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001283f  int     3; Trap to Debugger
0x140012840  mov     ecx, 80070216h; this
0x140012845  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001284a  int     3; Trap to Debugger
0x14001284b  mov     ecx, eax; this
0x14001284d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140012852  int     3; Trap to Debugger
0x140012853  mov     ecx, eax; this
0x140012855  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
