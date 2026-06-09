# CreateStoreObject(HSTRING__ *,ushort const *,_GUID const &,void * *)

- ea: `0x1800e1728`
- end: `0x1800e1d82`
- name: `?CreateStoreObject@@YAJPEAUHSTRING__@@PEBGAEBU_GUID@@PEAPEAX@Z`
- size: `1626`
- prototype: `__int64 __fastcall(HSTRING string, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800f2188`

## callees

- `0x180004870`
- `0x18001fce4`
- `0x18002146c`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800a0a24`
- `0x1800ad378`
- `0x1800b095c`
- `0x1800e1728`
- `0x1800e1d88`
- `0x1801200d0`
- `0x1801900f8`
- `0x180190180`
- `0x1801902e4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e17d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e181d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e17d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e181d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1a1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1a1d`
- `CompPkgSup!InstantiateComponentFromPackage` at `0x1800e1a5d`
- `CompPkgSup!InstantiateComponentFromPackage` at `0x1800e1a5d`

## string_xrefs

- `0x1800e1752`: `CreateStoreObject`
- `0x1800e1d36`: `CreateStoreObject`

## pseudocode

```c
__int64 __fastcall CreateStoreObject(HSTRING string, const unsigned __int16 *a2, const struct _GUID *a3, void **a4)
{
  int v8; // esi
  unsigned __int64 v9; // rdi
  int v10; // ebx
  unsigned __int64 v11; // rdx
  const WCHAR *v12; // r8
  int v13; // eax
  int v14; // ebx
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  CallStackTracing *v20; // rcx
  PCWSTR StringRawBuffer; // rax
  int v22; // eax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rcx
  int v25; // eax
  CallStackTracing *v26; // rcx
  CallStackTracing *v27; // rcx
  CallStackScopeTrace v29; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, const struct _GUID *, void **); // [rsp+38h] [rbp-31h] BYREF
  _QWORD v31[2]; // [rsp+40h] [rbp-29h] BYREF
  int v32; // [rsp+50h] [rbp-19h]
  Windows::Internal::StringReference v33; // [rsp+58h] [rbp-11h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v29, "CreateStoreObject", 62);
  v8 = 0;
  v31[0] = "CreateStoreObject";
  v31[1] = 0;
  v32 = 15;
  OutputMsg(0, 0xFu, "=>%s", "CreateStoreObject");
  v9 = -1;
  v30 = 0;
  do
    ++v9;
  while ( a2[v9] );
  *a4 = 0;
  if ( v9 < 8 || (v10 = 0, CompareStringOrdinal(a2, 8, L"Windows.", 8, 1) != 2) )
    v10 = 1;
  do
  {
    if ( v10 )
      goto LABEL_26;
    v11 = -1;
    v12 = (&off_1801C1C28)[v8];
    do
      ++v11;
    while ( v12[v11] );
    if ( v9 >= v11 && CompareStringOrdinal(a2, v11, v12, v11, 1) == 2 )
      v10 = 1;
    ++v8;
  }
  while ( !v8 );
  if ( v10 )
  {
LABEL_26:
    Windows::Internal::StringReference::_ConstructorHelper(&v33, a2);
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(v33._hstring, &v30);
    v14 = v18;
    if ( v18 < 0 )
    {
      if ( string )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)StringRawBuffer, (__int64)a2);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v30);
        Windows::Internal::StringReference::_ConstructorHelper(&v33, a2);
        v22 = InstantiateComponentFromPackage(v33._hstring, string, &v30);
        v14 = v22;
        if ( v22 >= 0 )
        {
          v25 = (**v30)(v30, a3, a4);
          v14 = v25;
          if ( v25 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids,
                0,
                v25);
            }
            v26 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v26 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v26->m_fEnabled )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v26);
              if ( ThreadRelativeContext->m_result != v14 )
              {
                v17 = 132;
                goto LABEL_92;
              }
            }
          }
        }
        else if ( v22 == -2147221164 && MFIsElevated() )
        {
          v14 = -2146959337;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids,
              0,
              -2146959337);
          }
          v23 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v23 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v23->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v23);
            if ( ThreadRelativeContext->m_result != -2146959337 )
            {
              v17 = 127;
              goto LABEL_92;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids, 0, v14);
          }
          v24 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v24 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v24->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v24);
            if ( ThreadRelativeContext->m_result != v14 )
            {
              v17 = 129;
              goto LABEL_92;
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids, 0, v18);
        }
        v27 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v27);
          if ( ThreadRelativeContext->m_result != v14 )
          {
            v17 = 136;
            goto LABEL_92;
          }
        }
      }
    }
    else
    {
      v19 = (**v30)(v30, a3, a4);
      v14 = v19;
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids, 0, v19);
        }
        v20 = CallStackTracing::s_wpInstance;
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v20);
          if ( ThreadRelativeContext->m_result != v14 )
          {
            v17 = 102;
            goto LABEL_92;
          }
        }
      }
    }
  }
  else
  {
    v13 = MF::OriginateError((MF *)0x80070005LL, v11);
    v14 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids, 0, v13);
    }
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
      if ( v14 < 0 && ThreadRelativeContext->m_result != v14 )
      {
        v17 = 95;
LABEL_92:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStoreObject", v17, v14);
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v30);
  CAutoTraceStatic::~CAutoTraceStatic((CAutoTraceStatic *)v31);
  CallStackScopeTrace::~CallStackScopeTrace(&v29);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800e1728  push    rbp
0x1800e172a  push    rbx
0x1800e172b  push    rsi
0x1800e172c  push    rdi
0x1800e172d  push    r12
0x1800e172f  push    r13
0x1800e1731  push    r14
0x1800e1733  push    r15
0x1800e1735  lea     rbp, [rsp-1Fh]
0x1800e173a  sub     rsp, 88h
0x1800e1741  mov     rax, cs:__security_cookie
0x1800e1748  xor     rax, rsp
0x1800e174b  mov     [rbp+57h+var_48], rax
0x1800e174f  mov     r13, r8
0x1800e1752  lea     rbx, aCreatestoreobj; "CreateStoreObject"
0x1800e1759  mov     r14, rdx
0x1800e175c  mov     r15, rcx
0x1800e175f  mov     rdx, rbx; char *
0x1800e1762  lea     rcx, [rbp+57h+var_90]; this
0x1800e1766  mov     r8d, 3Eh ; '>'; int
0x1800e176c  mov     r12, r9
0x1800e176f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e1774  xor     esi, esi
0x1800e1776  mov     [rbp+57h+var_80], rbx
0x1800e177a  mov     r9, rbx
0x1800e177d  mov     [rbp+57h+var_78], rsi
0x1800e1781  lea     r8, ?_szEntering@@3QBDB; "=>%s"
0x1800e1788  xor     ecx, ecx; unsigned int
0x1800e178a  lea     eax, [rsi+0Fh]
0x1800e178d  mov     edx, eax; unsigned int
0x1800e178f  mov     [rbp+57h+var_70], eax
0x1800e1792  call    ?OutputMsg@@YAXKKPEBDZZ; OutputMsg(ulong,ulong,char const *,...)
0x1800e1797  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800e179b  mov     [rbp+57h+var_88], rsi
0x1800e179f  inc     rdi
0x1800e17a2  cmp     [r14+rdi*2], si
0x1800e17a7  jnz     short loc_1800E179F
0x1800e17a9  mov     [r12], rsi
0x1800e17ad  mov     r9d, 1
0x1800e17b3  cmp     rdi, 8
0x1800e17b7  jb      short loc_1800E17E4
0x1800e17b9  mov     [rsp+0C0h+bIgnoreCase], r9d; bIgnoreCase
0x1800e17be  lea     r8, aWindows; "Windows."
0x1800e17c5  mov     r9d, 8; cchCount2
0x1800e17cb  mov     rcx, r14; lpString1
0x1800e17ce  mov     edx, r9d; cchCount1
0x1800e17d1  mov     ebx, esi
0x1800e17d3  call    cs:__imp_CompareStringOrdinal
0x1800e17d9  mov     r9d, 1
0x1800e17df  cmp     eax, 2
0x1800e17e2  jz      short loc_1800E17E7
0x1800e17e4  mov     ebx, r9d
0x1800e17e7  xor     ecx, ecx
0x1800e17e9  test    ebx, ebx
0x1800e17eb  jnz     loc_1800E1901
0x1800e17f1  movsxd  rax, esi
0x1800e17f4  lea     r8, off_1801C1C28; "Windows.Media.Protection.PlayReady"
0x1800e17fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e17ff  mov     r8, [r8+rax*8]; lpString2
0x1800e1803  inc     rdx; cchCount1
0x1800e1806  cmp     [r8+rdx*2], cx
0x1800e180b  jnz     short loc_1800E1803
0x1800e180d  cmp     rdi, rdx
0x1800e1810  jb      short loc_1800E1832
0x1800e1812  mov     [rsp+0C0h+bIgnoreCase], r9d; bIgnoreCase
0x1800e1817  mov     rcx, r14; lpString1
0x1800e181a  mov     r9d, edx; cchCount2
0x1800e181d  call    cs:__imp_CompareStringOrdinal
0x1800e1823  cmp     eax, 2
0x1800e1826  mov     r9d, 1
0x1800e182c  cmovz   ebx, r9d
0x1800e1830  xor     ecx, ecx
0x1800e1832  add     esi, r9d
0x1800e1835  cmp     esi, r9d
0x1800e1838  jb      short loc_1800E17E9
0x1800e183a  xor     esi, esi
0x1800e183c  test    ebx, ebx
0x1800e183e  jnz     loc_1800E1903
0x1800e1844  mov     ecx, 80070005h; this
0x1800e1849  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x1800e184e  mov     ebx, eax
0x1800e1850  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1857  lea     rdi, WPP_GLOBAL_Control
0x1800e185e  cmp     rcx, rdi
0x1800e1861  jz      short loc_1800E1889
0x1800e1863  test    byte ptr [rcx+1Ch], 1
0x1800e1867  jz      short loc_1800E1889
0x1800e1869  cmp     byte ptr [rcx+19h], 4
0x1800e186d  jb      short loc_1800E1889
0x1800e186f  mov     rcx, [rcx+10h]
0x1800e1873  lea     edx, [rsi+0Ah]
0x1800e1876  xor     r9d, r9d
0x1800e1879  mov     [rsp+0C0h+bIgnoreCase], eax
0x1800e187d  lea     r8, WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids
0x1800e1884  call    WPP_SF_Dd
0x1800e1889  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1890  test    rcx, rcx
0x1800e1893  jnz     short loc_1800E18D3
0x1800e1895  mov     rax, cs:stru_1801FC290.__vftable
0x1800e189c  lea     rcx, stru_1801FC290
0x1800e18a3  mov     edx, 7F0h
0x1800e18a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e18af  mov     rax, [rax+8]
0x1800e18b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18b8  test    eax, eax
0x1800e18ba  jnz     short loc_1800E18CC
0x1800e18bc  lea     rcx, stru_1801F8A30
0x1800e18c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e18ca  jmp     short loc_1800E18D3
0x1800e18cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e18d3  cmp     [rcx+8], sil
0x1800e18d7  jz      loc_1800E1D45
0x1800e18dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e18e2  test    ebx, ebx
0x1800e18e4  jns     loc_1800E1D45
0x1800e18ea  cmp     [rax+7CCh], ebx
0x1800e18f0  jz      loc_1800E1D45
0x1800e18f6  mov     r8d, 5Fh ; '_'
0x1800e18fc  jmp     loc_1800E1D33
0x1800e1901  xor     esi, esi
0x1800e1903  mov     rdx, r14; unsigned __int16 *
0x1800e1906  lea     rcx, [rbp+57h+var_68]; this
0x1800e190a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800e190f  mov     rcx, [rbp+57h+var_68._hstring]
0x1800e1913  lea     rdx, [rbp+57h+var_88]
0x1800e1917  call    ??$ActivateInstance@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800e191c  mov     ebx, eax
0x1800e191e  test    eax, eax
0x1800e1920  js      loc_1800E19F0
0x1800e1926  mov     rcx, [rbp+57h+var_88]
0x1800e192a  mov     r8, r12
0x1800e192d  mov     rdx, r13
0x1800e1930  mov     rax, [rcx]
0x1800e1933  mov     rax, [rax]
0x1800e1936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e193b  mov     ebx, eax
0x1800e193d  test    eax, eax
0x1800e193f  jns     loc_1800E1D45
0x1800e1945  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e194c  lea     rdi, WPP_GLOBAL_Control
0x1800e1953  cmp     rcx, rdi
0x1800e1956  jz      short loc_1800E1980
0x1800e1958  test    byte ptr [rcx+1Ch], 1
0x1800e195c  jz      short loc_1800E1980
0x1800e195e  cmp     byte ptr [rcx+19h], 4
0x1800e1962  jb      short loc_1800E1980
0x1800e1964  mov     rcx, [rcx+10h]
0x1800e1968  lea     r8, WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids
0x1800e196f  mov     edx, 0Bh
0x1800e1974  mov     [rsp+0C0h+bIgnoreCase], eax
0x1800e1978  xor     r9d, r9d
0x1800e197b  call    WPP_SF_Dd
0x1800e1980  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1987  test    rcx, rcx
0x1800e198a  jnz     short loc_1800E19CA
0x1800e198c  mov     rax, cs:stru_1801FC290.__vftable
0x1800e1993  lea     rcx, stru_1801FC290
0x1800e199a  mov     edx, 7F0h
0x1800e199f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e19a6  mov     rax, [rax+8]
0x1800e19aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e19af  test    eax, eax
0x1800e19b1  jnz     short loc_1800E19C3
0x1800e19b3  lea     rcx, stru_1801F8A30
0x1800e19ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e19c1  jmp     short loc_1800E19CA
0x1800e19c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e19ca  cmp     [rcx+8], sil
0x1800e19ce  jz      loc_1800E1D45
0x1800e19d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e19d9  cmp     [rax+7CCh], ebx
0x1800e19df  jz      loc_1800E1D45
0x1800e19e5  mov     r8d, 66h ; 'f'
0x1800e19eb  jmp     loc_1800E1D33
0x1800e19f0  test    r15, r15
0x1800e19f3  jz      loc_1800E1C95
0x1800e19f9  mov     rax, cs:WPP_GLOBAL_Control
0x1800e1a00  lea     rdi, WPP_GLOBAL_Control
0x1800e1a07  cmp     rax, rdi
0x1800e1a0a  jz      short loc_1800E1A3D
0x1800e1a0c  test    byte ptr [rax+1Ch], 1
0x1800e1a10  jz      short loc_1800E1A3D
0x1800e1a12  cmp     byte ptr [rax+19h], 4
0x1800e1a16  jb      short loc_1800E1A3D
0x1800e1a18  xor     edx, edx; length
0x1800e1a1a  mov     rcx, r15; string
0x1800e1a1d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1a23  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1a2a  mov     [rsp+0C0h+var_98], r14; __int64
0x1800e1a2f  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax; __int64
0x1800e1a34  mov     rcx, [rcx+10h]; LoggerHandle
0x1800e1a38  call    WPP_SF_DSS
0x1800e1a3d  lea     rcx, [rbp+57h+var_88]
0x1800e1a41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1a46  mov     rdx, r14; unsigned __int16 *
0x1800e1a49  lea     rcx, [rbp+57h+var_68]; this
0x1800e1a4d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800e1a52  mov     rcx, [rbp+57h+var_68._hstring]
0x1800e1a56  lea     r8, [rbp+57h+var_88]
0x1800e1a5a  mov     rdx, r15
0x1800e1a5d  call    cs:__imp_InstantiateComponentFromPackage
0x1800e1a63  mov     ebx, eax
0x1800e1a65  test    eax, eax
0x1800e1a67  jns     loc_1800E1BD2
0x1800e1a6d  cmp     eax, 80040154h
0x1800e1a72  jnz     loc_1800E1B2E
0x1800e1a78  call    ?MFIsElevated@@YA_NXZ; MFIsElevated(void)
0x1800e1a7d  test    al, al
0x1800e1a7f  jz      loc_1800E1B2E
0x1800e1a85  mov     ebx, 80080017h
0x1800e1a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1a91  cmp     rcx, rdi
0x1800e1a94  jz      short loc_1800E1ABE
0x1800e1a96  test    byte ptr [rcx+1Ch], 1
0x1800e1a9a  jz      short loc_1800E1ABE
0x1800e1a9c  cmp     byte ptr [rcx+19h], 4
0x1800e1aa0  jb      short loc_1800E1ABE
0x1800e1aa2  mov     rcx, [rcx+10h]
0x1800e1aa6  lea     r8, WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids
0x1800e1aad  mov     edx, 0Dh
0x1800e1ab2  mov     [rsp+0C0h+bIgnoreCase], ebx
0x1800e1ab6  xor     r9d, r9d
0x1800e1ab9  call    WPP_SF_Dd
0x1800e1abe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1ac5  test    rcx, rcx
0x1800e1ac8  jnz     short loc_1800E1B08
0x1800e1aca  mov     rax, cs:stru_1801FC290.__vftable
0x1800e1ad1  lea     rcx, stru_1801FC290
0x1800e1ad8  mov     edx, 7F0h
0x1800e1add  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1ae4  mov     rax, [rax+8]
0x1800e1ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1aed  test    eax, eax
0x1800e1aef  jnz     short loc_1800E1B01
0x1800e1af1  lea     rcx, stru_1801F8A30
0x1800e1af8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1aff  jmp     short loc_1800E1B08
0x1800e1b01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e1b08  cmp     [rcx+8], sil
0x1800e1b0c  jz      loc_1800E1D45
0x1800e1b12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e1b17  cmp     [rax+7CCh], ebx
0x1800e1b1d  jz      loc_1800E1D45
0x1800e1b23  mov     r8d, 7Fh
0x1800e1b29  jmp     loc_1800E1D33
0x1800e1b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1b35  cmp     rcx, rdi
0x1800e1b38  jz      short loc_1800E1B62
0x1800e1b3a  test    byte ptr [rcx+1Ch], 1
0x1800e1b3e  jz      short loc_1800E1B62
0x1800e1b40  cmp     byte ptr [rcx+19h], 4
0x1800e1b44  jb      short loc_1800E1B62
0x1800e1b46  mov     rcx, [rcx+10h]
0x1800e1b4a  lea     r8, WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids
0x1800e1b51  mov     edx, 0Eh
0x1800e1b56  mov     [rsp+0C0h+bIgnoreCase], ebx
0x1800e1b5a  xor     r9d, r9d
0x1800e1b5d  call    WPP_SF_Dd
0x1800e1b62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1b69  test    rcx, rcx
0x1800e1b6c  jnz     short loc_1800E1BAC
0x1800e1b6e  mov     rax, cs:stru_1801FC290.__vftable
0x1800e1b75  lea     rcx, stru_1801FC290
0x1800e1b7c  mov     edx, 7F0h
0x1800e1b81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1b88  mov     rax, [rax+8]
0x1800e1b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1b91  test    eax, eax
0x1800e1b93  jnz     short loc_1800E1BA5
0x1800e1b95  lea     rcx, stru_1801F8A30
0x1800e1b9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1ba3  jmp     short loc_1800E1BAC
0x1800e1ba5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e1bac  cmp     [rcx+8], sil
0x1800e1bb0  jz      loc_1800E1D45
0x1800e1bb6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e1bbb  cmp     [rax+7CCh], ebx
0x1800e1bc1  jz      loc_1800E1D45
0x1800e1bc7  mov     r8d, 81h
0x1800e1bcd  jmp     loc_1800E1D33
0x1800e1bd2  mov     rcx, [rbp+57h+var_88]
0x1800e1bd6  mov     r8, r12
0x1800e1bd9  mov     rdx, r13
0x1800e1bdc  mov     rax, [rcx]
0x1800e1bdf  mov     rax, [rax]
0x1800e1be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1be7  mov     ebx, eax
0x1800e1be9  test    eax, eax
0x1800e1beb  jns     loc_1800E1D45
0x1800e1bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1bf8  cmp     rcx, rdi
0x1800e1bfb  jz      short loc_1800E1C25
0x1800e1bfd  test    byte ptr [rcx+1Ch], 1
0x1800e1c01  jz      short loc_1800E1C25
0x1800e1c03  cmp     byte ptr [rcx+19h], 4
0x1800e1c07  jb      short loc_1800E1C25
0x1800e1c09  mov     rcx, [rcx+10h]
0x1800e1c0d  lea     r8, WPP_1b4cb824cb6633a7727f2f3ddf4c9c1c_Traceguids
0x1800e1c14  mov     edx, 0Fh
0x1800e1c19  mov     [rsp+0C0h+bIgnoreCase], eax
  ... truncated ...
```
