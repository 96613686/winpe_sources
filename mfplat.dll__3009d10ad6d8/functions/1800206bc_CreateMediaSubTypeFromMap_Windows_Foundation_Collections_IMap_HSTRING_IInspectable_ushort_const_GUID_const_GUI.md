# CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)

- ea: `0x1800206bc`
- end: `0x180020b7a`
- name: `?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001f3ac`

## callees

- `0x1800206bc`
- `0x180020b80`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x1801200d0`
- `0x180120e00`
- `0x180120eb4`
- `0x1801215f0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002077c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800207a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002077c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800207a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002074f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002083a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002074f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002083a`

## string_xrefs

- `0x180020714`: `CreateMediaSubTypeFromMap`

## pseudocode

```c
__int64 __fastcall CreateMediaSubTypeFromMap(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int m_dwDepth; // ecx
  __int64 v10; // rdx
  int v11; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  __int64 i; // rcx
  CallStackTracing *v17; // rcx
  __int64 v18; // rdx
  struct CallStackContext *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  CallStackTracing *v22; // rcx
  __int64 v23; // rdx
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  const wchar_t *v29; // rax
  CallStackScopeTrace v30; // [rsp+70h] [rbp-29h] BYREF
  HSTRING string; // [rsp+78h] [rbp-21h] BYREF
  size_t PtNumOfCharConverted; // [rsp+80h] [rbp-19h] BYREF
  char v33[32]; // [rsp+88h] [rbp-11h] BYREF
  char Dst[8]; // [rsp+A8h] [rbp+Fh] BYREF

  string = 0;
  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v5 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v5->m_fEnabled )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    m_dwDepth = ThreadRelativeContext->m_dwDepth;
    if ( m_dwDepth < ThreadRelativeContext->m_dwMaxDepth )
    {
      v10 = m_dwDepth;
      ThreadRelativeContext->m_rgInfo[v10].m_pszFunction = "CreateMediaSubTypeFromMap";
      ThreadRelativeContext->m_rgInfo[v10].m_lineNumber = 180;
    }
    ++ThreadRelativeContext->m_dwDepth;
  }
  WindowsDeleteString(string);
  string = 0;
  v11 = CreateStringFromMap(a1, L"@SubType", &string);
  if ( v11 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = -1;
    do
      ++v13;
    while ( StringRawBuffer[v13] );
    if ( v13 != 4 )
    {
      v14 = WindowsGetStringRawBuffer(string, 0);
      if ( swscanf(
             v14,
             L"%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%02x%02x%02x",
             a4,
             a4 + 4,
             a4 + 6,
             v33,
             &v33[4],
             &v33[8],
             &v33[12],
             &v33[16],
             &v33[20],
             &v33[24],
             &v33[28]) == 11 )
      {
        for ( i = 0; i != 8; ++i )
          *(_BYTE *)(a4 + i + 8) = v33[4 * i];
        v11 = 0;
        goto LABEL_14;
      }
      v27 = CallStackTracing::s_wpInstance;
      v11 = -2147467259;
      *(GUID *)a4 = GUID_00000000_0000_0000_0000_000000000000;
      if ( !v27 )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v27->m_fEnabled )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( v28->m_result != -2147467259 )
          CallStackContext::TraceFailure(v28, "CreateMediaSubTypeFromMap", 215, -2147467259);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v18 = 28;
        goto LABEL_57;
      }
      goto LABEL_14;
    }
    PtNumOfCharConverted = 0;
    v29 = WindowsGetStringRawBuffer(string, 0);
    if ( wcstombs_s(&PtNumOfCharConverted, Dst, 5u, v29, 4u) )
    {
      v25 = CallStackTracing::s_wpInstance;
      v11 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v25 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v25->m_fEnabled )
      {
        v26 = CallStackTracing::GetThreadRelativeContext(v25);
        if ( v26->m_result != -1072875845 )
          CallStackContext::TraceFailure(v26, "CreateMediaSubTypeFromMap", 210, -1072875845);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_14;
      v23 = 27;
    }
    else
    {
      v20 = *a3 - *(_QWORD *)&MFMediaType_Video.Data1;
      if ( *a3 == *(_QWORD *)&MFMediaType_Video.Data1 )
        v20 = a3[1] - *(_QWORD *)MFMediaType_Video.Data4;
      if ( !v20 )
      {
        v21 = *(_DWORD *)Dst;
LABEL_31:
        *(_DWORD *)a4 = v21;
        *(_DWORD *)(a4 + 4) = 0x100000;
        *(_DWORD *)(a4 + 8) = -1442840448;
        *(_DWORD *)(a4 + 12) = 1905997824;
        goto LABEL_14;
      }
      v21 = o_atoi_0(Dst);
      if ( v21 >= 0 )
        goto LABEL_31;
      v22 = CallStackTracing::s_wpInstance;
      v11 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v22->m_fEnabled )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( v24->m_result != -1072875845 )
          CallStackContext::TraceFailure(v24, "CreateMediaSubTypeFromMap", 202, -1072875845);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_14;
      v23 = 26;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, -1072875845);
    goto LABEL_14;
  }
  v17 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v17 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v17->m_fEnabled )
  {
    v19 = CallStackTracing::GetThreadRelativeContext(v17);
    if ( v19->m_result != v11 )
      CallStackContext::TraceFailure(v19, "CreateMediaSubTypeFromMap", 180, v11);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v18 = 25;
LABEL_57:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v11);
  }
LABEL_14:
  CallStackScopeTrace::~CallStackScopeTrace(&v30);
  WindowsDeleteString(string);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800206bc  mov     [rsp-8+arg_8], rbx
0x1800206c1  push    rbp
0x1800206c2  push    rsi
0x1800206c3  push    rdi
0x1800206c4  push    r12
0x1800206c6  push    r13
0x1800206c8  push    r14
0x1800206ca  push    r15
0x1800206cc  lea     rbp, [rsp-27h]
0x1800206d1  sub     rsp, 0C0h
0x1800206d8  mov     rax, cs:__security_cookie
0x1800206df  xor     rax, rsp
0x1800206e2  mov     [rbp+57h+var_40], rax
0x1800206e6  xor     r14d, r14d
0x1800206e9  lea     r12, stru_1801F8A30
0x1800206f0  mov     rdi, rcx
0x1800206f3  mov     [rbp+57h+string], r14
0x1800206f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800206fe  lea     r15, stru_1801FC290
0x180020705  mov     rbx, r9
0x180020708  mov     rsi, r8
0x18002070b  test    rcx, rcx
0x18002070e  jz      loc_180020869
0x180020714  lea     r13, aCreatemediasub; "CreateMediaSubTypeFromMap"
0x18002071b  cmp     [rcx+8], r14b
0x18002071f  jz      short loc_18002074B
0x180020721  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020726  mov     ecx, [rax+7C4h]
0x18002072c  cmp     ecx, [rax+7C8h]
0x180020732  jnb     short loc_180020745
0x180020734  mov     edx, ecx
0x180020736  add     rdx, rdx
0x180020739  mov     [rax+rdx*8], r13
0x18002073d  mov     dword ptr [rax+rdx*8+8], 0B4h
0x180020745  inc     dword ptr [rax+7C4h]
0x18002074b  mov     rcx, [rbp+57h+string]; string
0x18002074f  call    cs:__imp_WindowsDeleteString
0x180020755  lea     r8, [rbp+57h+string]
0x180020759  mov     [rbp+57h+string], r14
0x18002075d  lea     rdx, aSubtype; "@SubType"
0x180020764  mov     rcx, rdi
0x180020767  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18002076c  mov     edi, eax
0x18002076e  test    eax, eax
0x180020770  js      loc_1800208A7
0x180020776  mov     rcx, [rbp+57h+string]; string
0x18002077a  xor     edx, edx; length
0x18002077c  call    cs:__imp_WindowsGetStringRawBuffer
0x180020782  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020786  inc     rcx
0x180020789  cmp     [rax+rcx*2], r14w
0x18002078e  jnz     short loc_180020786
0x180020790  xor     edx, edx; length
0x180020792  cmp     rcx, 4
0x180020796  mov     rcx, [rbp+57h+string]; string
0x18002079a  jz      loc_180020B2E
0x1800207a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800207a6  lea     rdx, [rbp+57h+var_4C]
0x1800207aa  mov     r8, rbx
0x1800207ad  mov     [rsp+0F0h+var_90], rdx
0x1800207b2  lea     rcx, [rbx+6]
0x1800207b6  lea     rdx, [rbp+57h+var_50]
0x1800207ba  mov     [rsp+0F0h+var_98], rdx
0x1800207bf  lea     r9, [rbx+4]
0x1800207c3  lea     rdx, [rbp+57h+var_54]
0x1800207c7  mov     [rsp+0F0h+var_A0], rdx
0x1800207cc  lea     rdx, [rbp+57h+var_58]
0x1800207d0  mov     [rsp+0F0h+var_A8], rdx
0x1800207d5  lea     rdx, [rbp+57h+var_5C]
0x1800207d9  mov     [rsp+0F0h+var_B0], rdx
0x1800207de  lea     rdx, [rbp+57h+var_60]
0x1800207e2  mov     [rsp+0F0h+var_B8], rdx
0x1800207e7  lea     rdx, [rbp+57h+var_64]
0x1800207eb  mov     [rsp+0F0h+var_C0], rdx
0x1800207f0  lea     rdx, [rbp+57h+var_68]
0x1800207f4  mov     [rsp+0F0h+var_C8], rdx
0x1800207f9  lea     rdx, a08x04hx04hx02x; "%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%"...
0x180020800  mov     [rsp+0F0h+MaxCountInBytes], rcx
0x180020805  mov     rcx, rax; Buffer
0x180020808  call    swscanf
0x18002080d  cmp     eax, 0Bh
0x180020810  jnz     loc_180020A7E
0x180020816  mov     rcx, r14
0x180020819  mov     al, [rbp+rcx*4+57h+var_68]
0x18002081d  mov     [rbx+rcx+8], al
0x180020821  inc     rcx
0x180020824  cmp     rcx, 8
0x180020828  jnz     short loc_180020819
0x18002082a  mov     edi, r14d
0x18002082d  lea     rcx, [rbp+57h+var_80]; this
0x180020831  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180020836  mov     rcx, [rbp+57h+string]; string
0x18002083a  call    cs:__imp_WindowsDeleteString
0x180020840  mov     eax, edi
0x180020842  mov     rcx, [rbp+57h+var_40]
0x180020846  xor     rcx, rsp; StackCookie
0x180020849  call    __security_check_cookie
0x18002084e  mov     rbx, [rsp+0F0h+arg_8]
0x180020856  add     rsp, 0C0h
0x18002085d  pop     r15
0x18002085f  pop     r14
0x180020861  pop     r13
0x180020863  pop     r12
0x180020865  pop     rdi
0x180020866  pop     rsi
0x180020867  pop     rbp
0x180020868  retn
0x180020869  mov     rax, cs:stru_1801FC290.__vftable
0x180020870  mov     edx, 7F0h
0x180020875  mov     rcx, r15
0x180020878  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x18002087f  mov     rax, [rax+8]
0x180020883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020888  test    eax, eax
0x18002088a  jnz     short loc_18002089B
0x18002088c  mov     rcx, r12
0x18002088f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020896  jmp     loc_180020714
0x18002089b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800208a2  jmp     loc_180020714
0x1800208a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800208ae  test    rcx, rcx
0x1800208b1  jnz     short loc_1800208E0
0x1800208b3  mov     r8, cs:stru_1801FC290.__vftable
0x1800208ba  mov     edx, 7F0h
0x1800208bf  mov     rcx, r15
0x1800208c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800208c9  mov     rax, [r8+8]
0x1800208cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208d2  test    eax, eax
0x1800208d4  jnz     short loc_1800208FD
0x1800208d6  mov     rcx, r12; this
0x1800208d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800208e0  cmp     [rcx+8], r14b
0x1800208e4  jnz     short loc_180020906
0x1800208e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800208ed  jb      loc_18002082D
0x1800208f3  mov     edx, 19h
0x1800208f8  jmp     loc_180020ADF
0x1800208fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020904  jmp     short loc_1800208E0
0x180020906  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002090b  cmp     [rax+7CCh], edi
0x180020911  jz      short loc_1800208E6
0x180020913  mov     r9d, edi; int
0x180020916  mov     r8d, 0B4h; int
0x18002091c  mov     rdx, r13; char *
0x18002091f  mov     rcx, rax; this
0x180020922  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180020927  jmp     short loc_1800208E6
0x180020929  mov     rax, [rsi]
0x18002092c  sub     rax, qword ptr cs:MFMediaType_Video.Data1
0x180020933  jnz     short loc_180020940
0x180020935  mov     rax, [rsi+8]
0x180020939  sub     rax, qword ptr cs:MFMediaType_Video.Data4
0x180020940  test    rax, rax
0x180020943  jnz     loc_180020B64
0x180020949  mov     eax, dword ptr [rbp+57h+Dst]
0x18002094c  mov     [rbx], eax
0x18002094e  mov     dword ptr [rbx+4], 100000h
0x180020955  mov     dword ptr [rbx+8], 0AA000080h
0x18002095c  mov     dword ptr [rbx+0Ch], 719B3800h
0x180020963  jmp     loc_18002082D
0x180020968  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002096f  mov     ebx, 0C00D36BBh
0x180020974  mov     edi, ebx
0x180020976  test    rcx, rcx
0x180020979  jnz     short loc_1800209A8
0x18002097b  mov     rax, cs:stru_1801FC290.__vftable
0x180020982  mov     edx, 7F0h
0x180020987  mov     rcx, r15
0x18002098a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x180020991  mov     rax, [rax+8]
0x180020995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002099a  test    eax, eax
0x18002099c  jnz     short loc_1800209C5
0x18002099e  mov     rcx, r12; this
0x1800209a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800209a8  cmp     [rcx+8], r14b
0x1800209ac  jnz     short loc_1800209CE
0x1800209ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800209b5  jb      loc_18002082D
0x1800209bb  mov     edx, 1Ah
0x1800209c0  jmp     loc_180020A49
0x1800209c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800209cc  jmp     short loc_1800209A8
0x1800209ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800209d3  cmp     [rax+7CCh], ebx
0x1800209d9  jz      short loc_1800209AE
0x1800209db  mov     r9d, ebx; int
0x1800209de  mov     r8d, 0CAh; int
0x1800209e4  mov     rdx, r13; char *
0x1800209e7  mov     rcx, rax; this
0x1800209ea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800209ef  jmp     short loc_1800209AE
0x1800209f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800209f8  mov     ebx, 0C00D36BBh
0x1800209fd  mov     edi, ebx
0x1800209ff  test    rcx, rcx
0x180020a02  jnz     short loc_180020A31
0x180020a04  mov     rax, cs:stru_1801FC290.__vftable
0x180020a0b  mov     edx, 7F0h
0x180020a10  mov     rcx, r15
0x180020a13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x180020a1a  mov     rax, [rax+8]
0x180020a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a23  test    eax, eax
0x180020a25  jnz     short loc_180020A52
0x180020a27  mov     rcx, r12; this
0x180020a2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020a31  cmp     [rcx+8], r14b
0x180020a35  jnz     short loc_180020A5B
0x180020a37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020a3e  jb      loc_18002082D
0x180020a44  mov     edx, 1Bh
0x180020a49  mov     dword ptr [rsp+0F0h+MaxCountInBytes], ebx
0x180020a4d  jmp     loc_180020AE3
0x180020a52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020a59  jmp     short loc_180020A31
0x180020a5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020a60  cmp     [rax+7CCh], ebx
0x180020a66  jz      short loc_180020A37
0x180020a68  mov     r9d, ebx; int
0x180020a6b  mov     r8d, 0D2h; int
0x180020a71  mov     rdx, r13; char *
0x180020a74  mov     rcx, rax; this
0x180020a77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180020a7c  jmp     short loc_180020A37
0x180020a7e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180020a85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020a8c  mov     edi, 80004005h
0x180020a91  movdqu  xmmword ptr [rbx], xmm0
0x180020a95  test    rcx, rcx
0x180020a98  jnz     short loc_180020AC7
0x180020a9a  mov     rax, cs:stru_1801FC290.__vftable
0x180020aa1  mov     edx, 7F0h
0x180020aa6  mov     rcx, r15
0x180020aa9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x180020ab0  mov     rax, [rax+8]
0x180020ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ab9  test    eax, eax
0x180020abb  jnz     short loc_180020B02
0x180020abd  mov     rcx, r12; this
0x180020ac0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020ac7  cmp     [rcx+8], r14b
0x180020acb  jnz     short loc_180020B0B
0x180020acd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020ad4  jb      loc_18002082D
0x180020ada  mov     edx, 1Ch
0x180020adf  mov     dword ptr [rsp+0F0h+MaxCountInBytes], edi
0x180020ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aea  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180020af1  xor     r9d, r9d
0x180020af4  mov     rcx, [rcx+10h]
0x180020af8  call    WPP_SF_qD
0x180020afd  jmp     loc_18002082D
0x180020b02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020b09  jmp     short loc_180020AC7
0x180020b0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020b10  cmp     [rax+7CCh], edi
0x180020b16  jz      short loc_180020ACD
0x180020b18  mov     r9d, edi; int
0x180020b1b  mov     r8d, 0D7h; int
0x180020b21  mov     rdx, r13; char *
0x180020b24  mov     rcx, rax; this
0x180020b27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180020b2c  jmp     short loc_180020ACD
0x180020b2e  mov     [rbp+57h+PtNumOfCharConverted], r14
0x180020b32  call    cs:__imp_WindowsGetStringRawBuffer
0x180020b38  mov     r8d, 5; DstSizeInBytes
0x180020b3e  mov     [rsp+0F0h+MaxCountInBytes], 4; MaxCountInBytes
0x180020b47  mov     r9, rax; Src
0x180020b4a  lea     rdx, [rbp+57h+Dst]; Dst
0x180020b4e  lea     rcx, [rbp+57h+PtNumOfCharConverted]; PtNumOfCharConverted
0x180020b52  call    wcstombs_s
0x180020b57  test    eax, eax
0x180020b59  jnz     loc_1800209F1
0x180020b5f  jmp     loc_180020929
0x180020b64  lea     rcx, [rbp+57h+Dst]; String
0x180020b68  call    _o_atoi_0
0x180020b6d  test    eax, eax
0x180020b6f  jns     loc_18002094C
0x180020b75  jmp     loc_180020968
```
