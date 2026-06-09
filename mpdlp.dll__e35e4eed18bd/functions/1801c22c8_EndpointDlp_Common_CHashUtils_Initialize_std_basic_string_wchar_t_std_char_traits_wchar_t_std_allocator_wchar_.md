# EndpointDlp::Common::CHashUtils::Initialize(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1801c22c8`
- end: `0x1801c248e`
- name: `?Initialize@CHashUtils@Common@EndpointDlp@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801bd0c0`

## callees

- `0x1800068e4`
- `0x18002c150`
- `0x1800301a0`
- `0x18010cb40`
- `0x1801c22c8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1801c2411`
- `bcrypt!BCryptCreateHash` at `0x1801c2411`
- `bcrypt!BCryptGetProperty` at `0x1801c2355`
- `bcrypt!BCryptGetProperty` at `0x1801c23b4`
- `bcrypt!BCryptGetProperty` at `0x1801c2355`
- `bcrypt!BCryptGetProperty` at `0x1801c23b4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801c231c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801c231c`
- `KERNEL32!HeapAlloc` at `0x1801c2377`
- `KERNEL32!HeapAlloc` at `0x1801c23d4`
- `KERNEL32!HeapAlloc` at `0x1801c2377`
- `KERNEL32!HeapAlloc` at `0x1801c23d4`
- `KERNEL32!GetProcessHeap` at `0x1801c2369`
- `KERNEL32!GetProcessHeap` at `0x1801c23c6`
- `KERNEL32!GetProcessHeap` at `0x1801c2369`
- `KERNEL32!GetProcessHeap` at `0x1801c23c6`

## pseudocode

```c
__int64 __fastcall EndpointDlp::Common::CHashUtils::Initialize(__int64 a1, void *a2)
{
  const WCHAR *v2; // rbx
  unsigned int v3; // esi
  NTSTATUS Property; // edi
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  ULONG v7; // ebx
  HANDLE v8; // rax
  int v9; // edi
  struct EndpointDlp::TraceLoggingProvider *v10; // rax
  _DWORD *v11; // rcx
  __int64 v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+48h] [rbp-20h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-14h] BYREF

  v2 = (const WCHAR *)&pszAlgId;
  v3 = 0;
  std::wstring::operator=(&pszAlgId, a2);
  pcbResult = 0;
  if ( (unsigned __int64)qword_180314418 > 7 )
    v2 = pszAlgId;
  Property = BCryptOpenAlgorithmProvider(&hAlgorithm, v2, 0, 0x20u);
  if ( Property < 0 )
    goto LABEL_9;
  *(_DWORD *)pbOutput = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_9;
  v5 = *(_DWORD *)pbOutput;
  ProcessHeap = GetProcessHeap();
  pbHashObject = (PUCHAR)HeapAlloc(ProcessHeap, 0, v5);
  if ( !pbHashObject )
    goto LABEL_9;
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", (PUCHAR)&dwBytes, 4u, &pcbResult, 0);
  if ( Property >= 0
    && (v7 = dwBytes, v8 = GetProcessHeap(), (*(&pbHashObject + 1) = (PUCHAR)HeapAlloc(v8, 0, v7)) != 0)
    && (Property = BCryptCreateHash(hAlgorithm, &hAlgorithm + 1, pbHashObject, *(ULONG *)pbOutput, 0, 0, 0x20u),
        Property >= 0) )
  {
    byte_180314434 = 1;
  }
  else
  {
LABEL_9:
    v9 = Property | 0x10000000;
    v3 = v9;
    if ( v9 < 0 )
    {
      v10 = EndpointDlp::TraceLoggingProvider::Instance();
      v11 = *(_DWORD **)v10;
      if ( **(_DWORD **)v10 > 2u )
      {
        LODWORD(v13) = v9;
        v14 = (__int64)"CHashUtils::Initialize failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v11,
          (__int64)&v13,
          (__int64)&v14);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1801c22c8  mov     [rsp+arg_0], rbx
0x1801c22cd  mov     [rsp+arg_10], rsi
0x1801c22d2  push    rdi
0x1801c22d3  sub     rsp, 60h
0x1801c22d7  mov     rax, cs:__security_cookie
0x1801c22de  xor     rax, rsp
0x1801c22e1  mov     [rsp+68h+var_10], rax
0x1801c22e6  lea     rbx, pszAlgId
0x1801c22ed  xor     esi, esi
0x1801c22ef  mov     rcx, rbx; void *
0x1801c22f2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801c22f7  cmp     cs:qword_180314418, 7
0x1801c22ff  lea     r9d, [rsi+20h]; dwFlags
0x1801c2303  lea     rcx, hAlgorithm; phAlgorithm
0x1801c230a  mov     [rsp+68h+var_14], esi
0x1801c230e  cmova   rbx, qword ptr cs:pszAlgId
0x1801c2316  xor     r8d, r8d; pszImplementation
0x1801c2319  mov     rdx, rbx; pszAlgId
0x1801c231c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801c2322  mov     edi, eax
0x1801c2324  test    eax, eax
0x1801c2326  js      loc_1801C241D
0x1801c232c  mov     rcx, qword ptr cs:hAlgorithm; hObject
0x1801c2333  lea     rax, [rsp+68h+var_14]
0x1801c2338  mov     [rsp+68h+dwFlags], esi; dwFlags
0x1801c233c  lea     r9d, [rsi+4]; cbOutput
0x1801c2340  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x1801c2345  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1801c234a  lea     rdx, aObjectlength; "ObjectLength"
0x1801c2351  mov     dword ptr [rsp+68h+pbOutput], esi
0x1801c2355  call    cs:__imp_BCryptGetProperty
0x1801c235b  mov     edi, eax
0x1801c235d  test    eax, eax
0x1801c235f  js      loc_1801C241D
0x1801c2365  mov     ebx, dword ptr [rsp+68h+pbOutput]
0x1801c2369  call    cs:__imp_GetProcessHeap
0x1801c236f  mov     r8d, ebx; dwBytes
0x1801c2372  xor     edx, edx; dwFlags
0x1801c2374  mov     rcx, rax; hHeap
0x1801c2377  call    cs:__imp_HeapAlloc
0x1801c237d  mov     qword ptr cs:pbHashObject, rax
0x1801c2384  test    rax, rax
0x1801c2387  jz      loc_1801C241D
0x1801c238d  mov     rcx, qword ptr cs:hAlgorithm; hObject
0x1801c2394  lea     rax, [rsp+68h+var_14]
0x1801c2399  mov     [rsp+68h+dwFlags], esi; dwFlags
0x1801c239d  lea     r9d, [rsi+4]; cbOutput
0x1801c23a1  lea     r8, dwBytes; pbOutput
0x1801c23a8  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1801c23ad  lea     rdx, pszProperty; "HashDigestLength"
0x1801c23b4  call    cs:__imp_BCryptGetProperty
0x1801c23ba  mov     edi, eax
0x1801c23bc  test    eax, eax
0x1801c23be  js      short loc_1801C241D
0x1801c23c0  mov     ebx, cs:dwBytes
0x1801c23c6  call    cs:__imp_GetProcessHeap
0x1801c23cc  mov     r8d, ebx; dwBytes
0x1801c23cf  xor     edx, edx; dwFlags
0x1801c23d1  mov     rcx, rax; hHeap
0x1801c23d4  call    cs:__imp_HeapAlloc
0x1801c23da  mov     qword ptr cs:pbHashObject+8, rax
0x1801c23e1  test    rax, rax
0x1801c23e4  jz      short loc_1801C241D
0x1801c23e6  mov     r9d, dword ptr [rsp+68h+pbOutput]; cbHashObject
0x1801c23eb  lea     rdx, hAlgorithm+8; phHash
0x1801c23f2  mov     r8, qword ptr cs:pbHashObject; pbHashObject
0x1801c23f9  mov     rcx, qword ptr cs:hAlgorithm; hAlgorithm
0x1801c2400  mov     [rsp+68h+var_38], 20h ; ' '; dwFlags
0x1801c2408  mov     [rsp+68h+dwFlags], esi; cbSecret
0x1801c240c  mov     [rsp+68h+pcbResult], rsi; pbSecret
0x1801c2411  call    cs:__imp_BCryptCreateHash
0x1801c2417  mov     edi, eax
0x1801c2419  test    eax, eax
0x1801c241b  jns     short loc_1801C2466
0x1801c241d  or      edi, 10000000h
0x1801c2423  mov     esi, edi
0x1801c2425  jge     short loc_1801C246D
0x1801c2427  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1801c242c  mov     rcx, [rax]; int
0x1801c242f  cmp     dword ptr [rcx], 2
0x1801c2432  jbe     short loc_1801C246D
0x1801c2434  lea     rax, aChashutilsInit; "CHashUtils::Initialize failed"
0x1801c243b  mov     dword ptr [rsp+68h+var_28], edi
0x1801c243f  mov     [rsp+68h+var_20], rax
0x1801c2444  lea     rdx, word_1802C5452
0x1801c244b  lea     rax, [rsp+68h+var_20]
0x1801c2450  mov     qword ptr [rsp+68h+dwFlags], rax; __int64
0x1801c2455  lea     rax, [rsp+68h+var_28]
0x1801c245a  mov     [rsp+68h+pcbResult], rax; __int64
0x1801c245f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801c2464  jmp     short loc_1801C246D
0x1801c2466  mov     cs:byte_180314434, 1
0x1801c246d  mov     eax, esi
0x1801c246f  mov     rcx, [rsp+68h+var_10]
0x1801c2474  xor     rcx, rsp; StackCookie
0x1801c2477  call    __security_check_cookie
0x1801c247c  lea     r11, [rsp+68h+var_8]
0x1801c2481  mov     rbx, [r11+10h]
0x1801c2485  mov     rsi, [r11+20h]
0x1801c2489  mov     rsp, r11
0x1801c248c  pop     rdi
0x1801c248d  retn
```
