# AllocStringArrayForAttributes(Windows::Foundation::Collections::IVector<HSTRING__ *> *,tagPROPVARIANT *)

- ea: `0x1800ce58c`
- end: `0x1800cea10`
- name: `?AllocStringArrayForAttributes@@YAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAUtagPROPVARIANT@@@Z`
- size: `1156`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180193c08`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800ce58c`
- `0x180120ecc`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce5d0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce9e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce5d0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ce9e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce9df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ce9df`

## pseudocode

```c
__int64 __fastcall AllocStringArrayForAttributes(__int64 *a1, __int64 a2)
{
  HRESULT v4; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  void *v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, _QWORD, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // r14
  UINT32 v18; // r12d
  void *v19; // rcx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 length; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+48h] BYREF

  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&length, "AllocStringArrayForAttributes", 1912);
  v4 = PropVariantClear((PROPVARIANT *)a2);
  if ( v4 < 0 )
  {
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
      if ( ThreadRelativeContext->m_result != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "AllocStringArrayForAttributes", 1912, v4);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_60;
    v7 = 248;
    goto LABEL_11;
  }
  *(_WORD *)a2 = 4127;
  *(_DWORD *)(a2 + 8) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a1 + 56))(a1, &v27);
  if ( v4 < 0 )
  {
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v9->m_result != v4 )
        CallStackContext::TraceFailure(v9, "AllocStringArrayForAttributes", 1917, v4);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_60;
    v7 = 249;
LABEL_11:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v4);
    goto LABEL_60;
  }
  v10 = CoTaskMemAlloc(8LL * v27);
  *(_QWORD *)(a2 + 16) = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 8LL * v27);
    v13 = v27;
    v14 = 0;
    *(_DWORD *)(a2 + 8) = v27;
    while ( 1 )
    {
      if ( (unsigned int)v14 >= v13 )
        goto LABEL_61;
      v15 = *a1;
      string[0] = 0;
      length = 0;
      v16 = *(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v15 + 48);
      WindowsDeleteString(0);
      string[0] = 0;
      v4 = v16(a1, (unsigned int)v14, string);
      if ( v4 < 0 )
        break;
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], &length);
      if ( StringRawBuffer && length )
      {
        v18 = 2 * length + 2;
        *(_QWORD *)(*(_QWORD *)(a2 + 16) + 8 * v14) = CoTaskMemAlloc(v18);
        v19 = *(void **)(*(_QWORD *)(a2 + 16) + 8 * v14);
        if ( !v19 )
        {
          v20 = CallStackTracing::s_wpInstance;
          v4 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v20 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v20->m_fEnabled )
          {
            v21 = CallStackTracing::GetThreadRelativeContext(v20);
            if ( v21->m_result != -2147024882 )
              CallStackContext::TraceFailure(v21, "AllocStringArrayForAttributes", 1950, -2147024882);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              252,
              &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
              0,
              -2147024882);
LABEL_59:
          WindowsDeleteString(string[0]);
          goto LABEL_60;
        }
        memcpy_0(v19, StringRawBuffer, v18);
      }
      WindowsDeleteString(string[0]);
      v13 = v27;
      v14 = (unsigned int)(v14 + 1);
    }
    v22 = CallStackTracing::s_wpInstance;
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
      v23 = CallStackTracing::GetThreadRelativeContext(v22);
      if ( v23->m_result != v4 )
        CallStackContext::TraceFailure(v23, "AllocStringArrayForAttributes", 1934, v4);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v4);
    goto LABEL_59;
  }
  v11 = CallStackTracing::s_wpInstance;
  v4 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v11 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v11->m_fEnabled )
  {
    v12 = CallStackTracing::GetThreadRelativeContext(v11);
    if ( v12->m_result != -2147024882 )
      CallStackContext::TraceFailure(v12, "AllocStringArrayForAttributes", 1922, -2147024882);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      250,
      &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
      0,
      -2147024882);
LABEL_60:
  PropVariantClear((PROPVARIANT *)a2);
LABEL_61:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&length);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ce58c  mov     [rsp-28h+arg_0], rbx
0x1800ce591  mov     [rsp-28h+arg_8], rsi
0x1800ce596  push    rbp
0x1800ce597  push    rdi
0x1800ce598  push    r12
0x1800ce59a  push    r14
0x1800ce59c  push    r15
0x1800ce59e  mov     rbp, rsp
0x1800ce5a1  sub     rsp, 40h
0x1800ce5a5  mov     rsi, rdx
0x1800ce5a8  mov     [rbp+arg_18], 0
0x1800ce5af  mov     r15, rcx
0x1800ce5b2  lea     r14, aAllocstringarr; "AllocStringArrayForAttributes"
0x1800ce5b9  mov     edi, 778h
0x1800ce5be  lea     rcx, [rbp+length]; this
0x1800ce5c2  mov     r8d, edi; int
0x1800ce5c5  mov     rdx, r14; char *
0x1800ce5c8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ce5cd  mov     rcx, rsi; pvar
0x1800ce5d0  call    cs:__imp_PropVariantClear
0x1800ce5d6  mov     ebx, eax
0x1800ce5d8  test    eax, eax
0x1800ce5da  jns     loc_1800CE667
0x1800ce5e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce5e7  test    rcx, rcx
0x1800ce5ea  jnz     short loc_1800CE628
0x1800ce5ec  mov     rdx, cs:stru_1801FC290.__vftable
0x1800ce5f3  lea     rcx, stru_1801FC290
0x1800ce5fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce601  mov     rax, [rdx+8]
0x1800ce605  lea     edx, [rdi+78h]
0x1800ce608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce60d  test    eax, eax
0x1800ce60f  jnz     short loc_1800CE621
0x1800ce611  lea     rcx, stru_1801F8A30
0x1800ce618  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce61f  jmp     short loc_1800CE628
0x1800ce621  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce628  cmp     byte ptr [rcx+8], 0
0x1800ce62c  jz      short loc_1800CE64C
0x1800ce62e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce633  cmp     [rax+7CCh], ebx
0x1800ce639  jz      short loc_1800CE64C
0x1800ce63b  mov     r9d, ebx; int
0x1800ce63e  mov     r8d, edi; int
0x1800ce641  mov     rdx, r14; char *
0x1800ce644  mov     rcx, rax; this
0x1800ce647  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce64c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce653  jb      loc_1800CE9E5
0x1800ce659  mov     edx, 0F8h
0x1800ce65e  mov     [rsp+40h+var_20], ebx
0x1800ce662  jmp     loc_1800CE7C0
0x1800ce667  mov     word ptr [rsi], 101Fh
0x1800ce66c  lea     rdx, [rbp+arg_18]
0x1800ce670  mov     dword ptr [rsi+8], 0
0x1800ce677  mov     rcx, r15
0x1800ce67a  mov     rax, [r15]
0x1800ce67d  mov     rax, [rax+38h]
0x1800ce681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce686  mov     ebx, eax
0x1800ce688  test    eax, eax
0x1800ce68a  jns     loc_1800CE718
0x1800ce690  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce697  test    rcx, rcx
0x1800ce69a  jnz     short loc_1800CE6DA
0x1800ce69c  mov     rax, cs:stru_1801FC290.__vftable
0x1800ce6a3  lea     rcx, stru_1801FC290
0x1800ce6aa  mov     edx, 7F0h
0x1800ce6af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce6b6  mov     rax, [rax+8]
0x1800ce6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce6bf  test    eax, eax
0x1800ce6c1  jnz     short loc_1800CE6D3
0x1800ce6c3  lea     rcx, stru_1801F8A30
0x1800ce6ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce6d1  jmp     short loc_1800CE6DA
0x1800ce6d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce6da  cmp     byte ptr [rcx+8], 0
0x1800ce6de  jz      short loc_1800CE701
0x1800ce6e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce6e5  cmp     [rax+7CCh], ebx
0x1800ce6eb  jz      short loc_1800CE701
0x1800ce6ed  mov     r9d, ebx; int
0x1800ce6f0  mov     r8d, 77Dh; int
0x1800ce6f6  mov     rdx, r14; char *
0x1800ce6f9  mov     rcx, rax; this
0x1800ce6fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce701  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce708  jb      loc_1800CE9E5
0x1800ce70e  mov     edx, 0F9h
0x1800ce713  jmp     loc_1800CE65E
0x1800ce718  mov     ecx, [rbp+arg_18]
0x1800ce71b  shl     rcx, 3; cb
0x1800ce71f  call    cs:__imp_CoTaskMemAlloc
0x1800ce725  mov     [rsi+10h], rax
0x1800ce729  test    rax, rax
0x1800ce72c  jnz     loc_1800CE7DF
0x1800ce732  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce739  mov     edi, 8007000Eh
0x1800ce73e  mov     ebx, edi
0x1800ce740  test    rcx, rcx
0x1800ce743  jnz     short loc_1800CE783
0x1800ce745  mov     rax, cs:stru_1801FC290.__vftable
0x1800ce74c  lea     rcx, stru_1801FC290
0x1800ce753  mov     edx, 7F0h
0x1800ce758  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce75f  mov     rax, [rax+8]
0x1800ce763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce768  test    eax, eax
0x1800ce76a  jnz     short loc_1800CE77C
0x1800ce76c  lea     rcx, stru_1801F8A30
0x1800ce773  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce77a  jmp     short loc_1800CE783
0x1800ce77c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce783  cmp     byte ptr [rcx+8], 0
0x1800ce787  jz      short loc_1800CE7AA
0x1800ce789  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce78e  cmp     [rax+7CCh], edi
0x1800ce794  jz      short loc_1800CE7AA
0x1800ce796  mov     r9d, edi; int
0x1800ce799  mov     r8d, 782h; int
0x1800ce79f  mov     rdx, r14; char *
0x1800ce7a2  mov     rcx, rax; this
0x1800ce7a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce7aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce7b1  jb      loc_1800CE9E5
0x1800ce7b7  mov     edx, 0FAh
0x1800ce7bc  mov     [rsp+40h+var_20], edi
0x1800ce7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce7c7  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800ce7ce  xor     r9d, r9d
0x1800ce7d1  mov     rcx, [rcx+10h]
0x1800ce7d5  call    WPP_SF_qD
0x1800ce7da  jmp     loc_1800CE9E5
0x1800ce7df  mov     r8d, [rbp+arg_18]
0x1800ce7e3  xor     edx, edx; Val
0x1800ce7e5  shl     r8, 3; Size
0x1800ce7e9  mov     rcx, rax; void *
0x1800ce7ec  call    memset_0
0x1800ce7f1  mov     eax, [rbp+arg_18]
0x1800ce7f4  xor     edi, edi
0x1800ce7f6  mov     [rsi+8], eax
0x1800ce7f9  cmp     edi, eax
0x1800ce7fb  jnb     loc_1800CE9EE
0x1800ce801  mov     rax, [r15]
0x1800ce804  xor     ecx, ecx; string
0x1800ce806  mov     [rbp+string], 0
0x1800ce80e  mov     [rbp+length], 0
0x1800ce815  mov     rbx, [rax+30h]
0x1800ce819  call    cs:__imp_WindowsDeleteString
0x1800ce81f  lea     r8, [rbp+string]
0x1800ce823  mov     [rbp+string], 0
0x1800ce82b  mov     edx, edi
0x1800ce82d  mov     rcx, r15
0x1800ce830  mov     rax, rbx
0x1800ce833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce838  mov     ebx, eax
0x1800ce83a  test    eax, eax
0x1800ce83c  js      loc_1800CE93A
0x1800ce842  mov     rcx, [rbp+string]; string
0x1800ce846  lea     rdx, [rbp+length]; length
0x1800ce84a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ce850  mov     r14, rax
0x1800ce853  test    rax, rax
0x1800ce856  jz      short loc_1800CE88F
0x1800ce858  mov     ecx, [rbp+length]
0x1800ce85b  test    ecx, ecx
0x1800ce85d  jz      short loc_1800CE88F
0x1800ce85f  lea     ecx, ds:2[rcx*2]; cb
0x1800ce866  mov     r12d, ecx
0x1800ce869  call    cs:__imp_CoTaskMemAlloc
0x1800ce86f  mov     rcx, [rsi+10h]
0x1800ce873  mov     [rcx+rdi*8], rax
0x1800ce877  mov     rax, [rsi+10h]
0x1800ce87b  mov     rcx, [rax+rdi*8]; void *
0x1800ce87f  test    rcx, rcx
0x1800ce882  jz      short loc_1800CE8A3
0x1800ce884  mov     r8d, r12d; Size
0x1800ce887  mov     rdx, r14; Src
0x1800ce88a  call    memcpy_0
0x1800ce88f  mov     rcx, [rbp+string]; string
0x1800ce893  call    cs:__imp_WindowsDeleteString
0x1800ce899  mov     eax, [rbp+arg_18]
0x1800ce89c  inc     edi
0x1800ce89e  jmp     loc_1800CE7F9
0x1800ce8a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce8aa  mov     edi, 8007000Eh
0x1800ce8af  mov     ebx, edi
0x1800ce8b1  test    rcx, rcx
0x1800ce8b4  jnz     short loc_1800CE8F4
0x1800ce8b6  mov     rax, cs:stru_1801FC290.__vftable
0x1800ce8bd  lea     rcx, stru_1801FC290
0x1800ce8c4  mov     edx, 7F0h
0x1800ce8c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce8d0  mov     rax, [rax+8]
0x1800ce8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce8d9  test    eax, eax
0x1800ce8db  jnz     short loc_1800CE8ED
0x1800ce8dd  lea     rcx, stru_1801F8A30
0x1800ce8e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce8eb  jmp     short loc_1800CE8F4
0x1800ce8ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce8f4  cmp     byte ptr [rcx+8], 0
0x1800ce8f8  jz      short loc_1800CE91F
0x1800ce8fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce8ff  cmp     [rax+7CCh], edi
0x1800ce905  jz      short loc_1800CE91F
0x1800ce907  mov     r9d, edi; int
0x1800ce90a  lea     rdx, aAllocstringarr; "AllocStringArrayForAttributes"
0x1800ce911  mov     r8d, 79Eh; int
0x1800ce917  mov     rcx, rax; this
0x1800ce91a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce91f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce926  jb      loc_1800CE9DB
0x1800ce92c  mov     edx, 0FCh
0x1800ce931  mov     [rsp+40h+var_20], edi
0x1800ce935  jmp     loc_1800CE9C1
0x1800ce93a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce941  test    rcx, rcx
0x1800ce944  jnz     short loc_1800CE984
0x1800ce946  mov     rax, cs:stru_1801FC290.__vftable
0x1800ce94d  lea     rcx, stru_1801FC290
0x1800ce954  mov     edx, 7F0h
0x1800ce959  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce960  mov     rax, [rax+8]
0x1800ce964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce969  test    eax, eax
0x1800ce96b  jnz     short loc_1800CE97D
0x1800ce96d  lea     rcx, stru_1801F8A30
0x1800ce974  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ce97b  jmp     short loc_1800CE984
0x1800ce97d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ce984  cmp     byte ptr [rcx+8], 0
0x1800ce988  jz      short loc_1800CE9AF
0x1800ce98a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ce98f  cmp     [rax+7CCh], ebx
0x1800ce995  jz      short loc_1800CE9AF
0x1800ce997  mov     r9d, ebx; int
0x1800ce99a  lea     rdx, aAllocstringarr; "AllocStringArrayForAttributes"
0x1800ce9a1  mov     r8d, 78Eh; int
0x1800ce9a7  mov     rcx, rax; this
0x1800ce9aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ce9af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ce9b6  jb      short loc_1800CE9DB
0x1800ce9b8  mov     edx, 0FBh
0x1800ce9bd  mov     [rsp+40h+var_20], ebx
0x1800ce9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce9c8  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800ce9cf  xor     r9d, r9d
0x1800ce9d2  mov     rcx, [rcx+10h]
0x1800ce9d6  call    WPP_SF_qD
0x1800ce9db  mov     rcx, [rbp+string]; string
0x1800ce9df  call    cs:__imp_WindowsDeleteString
0x1800ce9e5  mov     rcx, rsi; pvar
0x1800ce9e8  call    cs:__imp_PropVariantClear
0x1800ce9ee  lea     rcx, [rbp+length]; this
0x1800ce9f2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ce9f7  mov     rsi, [rsp+40h+arg_8]
0x1800ce9fc  mov     eax, ebx
0x1800ce9fe  mov     rbx, [rsp+40h+arg_0]
0x1800cea03  add     rsp, 40h
0x1800cea07  pop     r15
0x1800cea09  pop     r14
0x1800cea0b  pop     r12
0x1800cea0d  pop     rdi
0x1800cea0e  pop     rbp
0x1800cea0f  retn
```
