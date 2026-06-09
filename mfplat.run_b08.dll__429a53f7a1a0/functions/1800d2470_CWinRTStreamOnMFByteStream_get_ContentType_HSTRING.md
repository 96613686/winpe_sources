# CWinRTStreamOnMFByteStream::get_ContentType(HSTRING__ * *)

- ea: `0x1800d2470`
- end: `0x1800d2745`
- name: `?get_ContentType@CWinRTStreamOnMFByteStream@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `725`
- prototype: `int(CWinRTStreamOnMFByteStream *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800d2470`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d24a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d24a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d2729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d265e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d265e`

## pseudocode

```c
__int64 __fastcall CWinRTStreamOnMFByteStream::get_ContentType(CWinRTStreamOnMFByteStream *this, HSTRING *a2)
{
  __int64 v4; // r14
  char *v5; // rdi
  CallStackTracing *v6; // rcx
  HRESULT String; // ebx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackScopeTrace v15; // [rsp+60h] [rbp+30h] BYREF
  UINT32 length; // [rsp+68h] [rbp+38h] BYREF
  PCNZWCH sourceString; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+78h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v15, "CWinRTStreamOnMFByteStream::get_ContentType", 538);
  v4 = *((_QWORD *)this + 6);
  v5 = (char *)this - 48;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
  sourceString = 0;
  length = 0;
  v18 = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_DWORD *)v5 + 28) )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      String = -2147483629;
      if ( v10->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
        if ( ThreadRelativeContext->m_result != -2147483629 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CWinRTStreamOnMFByteStream::get_ContentType",
            548,
            -2147483629);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v9 = 82;
        goto LABEL_33;
      }
    }
    else
    {
      String = 0;
      if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)v5 + 12) + 24LL))(
             *(_QWORD *)(*((_QWORD *)v5 + 12) + 24LL),
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             &v18) >= 0
        && (*(int (__fastcall **)(__int64, const IID *, PCNZWCH *, UINT32 *))(*(_QWORD *)v18 + 104LL))(
             v18,
             &MF_BYTESTREAM_CONTENT_TYPE,
             &sourceString,
             &length) >= 0 )
      {
        String = WindowsCreateString(sourceString, length, a2);
        if ( String < 0 )
        {
          v12 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v12 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v12 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v12->m_fEnabled )
          {
            v13 = CallStackTracing::GetThreadRelativeContext(v12);
            if ( v13->m_result != String )
              CallStackContext::TraceFailure(v13, "CWinRTStreamOnMFByteStream::get_ContentType", 553, String);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v9 = 83;
            goto LABEL_33;
          }
        }
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    String = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v6->m_fEnabled )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( v8->m_result != -2147467261 )
        CallStackContext::TraceFailure(v8, "CWinRTStreamOnMFByteStream::get_ContentType", 545, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 81;
LABEL_33:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_2b7361d32eac31bbfd89b23d9726b9e0_Traceguids, v5, String);
    }
  }
  CoTaskMemFree((LPVOID)sourceString);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
  CallStackScopeTrace::~CallStackScopeTrace(&v15);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800d2470  push    rbp
0x1800d2472  push    rbx
0x1800d2473  push    rsi
0x1800d2474  push    rdi
0x1800d2475  push    r14
0x1800d2477  mov     rbp, rsp
0x1800d247a  sub     rsp, 30h
0x1800d247e  mov     rsi, rdx
0x1800d2481  mov     rdi, rcx
0x1800d2484  lea     rdx, aCwinrtstreamon_13; "CWinRTStreamOnMFByteStream::get_Content"...
0x1800d248b  mov     r8d, 21Ah; int
0x1800d2491  lea     rcx, [rbp+arg_0]; this
0x1800d2495  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d249a  mov     r14, [rdi+30h]
0x1800d249e  add     rdi, 0FFFFFFFFFFFFFFD0h
0x1800d24a2  lea     rcx, [r14+30h]; lpCriticalSection
0x1800d24a6  call    cs:__imp_EnterCriticalSection
0x1800d24ac  mov     [rbp+sourceString], 0
0x1800d24b4  mov     [rbp+length], 0
0x1800d24bb  mov     [rbp+arg_18], 0
0x1800d24c3  test    rsi, rsi
0x1800d24c6  jnz     loc_1800D2560
0x1800d24cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d24d3  mov     ebx, 80004003h
0x1800d24d8  test    rcx, rcx
0x1800d24db  jnz     short loc_1800D251E
0x1800d24dd  mov     rax, cs:stru_1801FC290.__vftable
0x1800d24e4  lea     r8, stru_1801FC290
0x1800d24eb  mov     edx, 7F0h
0x1800d24f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d24f7  mov     rcx, r8
0x1800d24fa  mov     rax, [rax+8]
0x1800d24fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2503  test    eax, eax
0x1800d2505  jnz     short loc_1800D2517
0x1800d2507  lea     rcx, stru_1801F8A30
0x1800d250e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d2515  jmp     short loc_1800D251E
0x1800d2517  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d251e  cmp     byte ptr [rcx+8], 0
0x1800d2522  jz      short loc_1800D2549
0x1800d2524  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d2529  cmp     [rax+7CCh], ebx
0x1800d252f  jz      short loc_1800D2549
0x1800d2531  mov     r9d, ebx; int
0x1800d2534  lea     rdx, aCwinrtstreamon_13; "CWinRTStreamOnMFByteStream::get_Content"...
0x1800d253b  mov     r8d, 221h; int
0x1800d2541  mov     rcx, rax; this
0x1800d2544  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d2549  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d2550  jb      loc_1800D2712
0x1800d2556  mov     edx, 51h ; 'Q'
0x1800d255b  jmp     loc_1800D26F4
0x1800d2560  mov     qword ptr [rsi], 0
0x1800d2567  cmp     dword ptr [rdi+70h], 0
0x1800d256b  jz      loc_1800D2605
0x1800d2571  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d2578  test    rcx, rcx
0x1800d257b  jnz     short loc_1800D25BE
0x1800d257d  mov     rax, cs:stru_1801FC290.__vftable
0x1800d2584  lea     r8, stru_1801FC290
0x1800d258b  mov     edx, 7F0h
0x1800d2590  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d2597  mov     rcx, r8
0x1800d259a  mov     rax, [rax+8]
0x1800d259e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d25a3  test    eax, eax
0x1800d25a5  jnz     short loc_1800D25B7
0x1800d25a7  lea     rcx, stru_1801F8A30
0x1800d25ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d25b5  jmp     short loc_1800D25BE
0x1800d25b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d25be  cmp     byte ptr [rcx+8], 0
0x1800d25c2  mov     ebx, 80000013h
0x1800d25c7  jz      short loc_1800D25EE
0x1800d25c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d25ce  cmp     [rax+7CCh], ebx
0x1800d25d4  jz      short loc_1800D25EE
0x1800d25d6  mov     r9d, ebx; int
0x1800d25d9  lea     rdx, aCwinrtstreamon_13; "CWinRTStreamOnMFByteStream::get_Content"...
0x1800d25e0  mov     r8d, 224h; int
0x1800d25e6  mov     rcx, rax; this
0x1800d25e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d25ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d25f5  jb      loc_1800D2712
0x1800d25fb  mov     edx, 52h ; 'R'
0x1800d2600  jmp     loc_1800D26F4
0x1800d2605  mov     rax, [rdi+60h]
0x1800d2609  lea     r8, [rbp+arg_18]
0x1800d260d  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800d2614  xor     ebx, ebx
0x1800d2616  mov     rcx, [rax+18h]
0x1800d261a  mov     rax, [rcx]
0x1800d261d  mov     rax, [rax]
0x1800d2620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2625  test    eax, eax
0x1800d2627  js      loc_1800D2712
0x1800d262d  mov     rcx, [rbp+arg_18]
0x1800d2631  lea     r9, [rbp+length]
0x1800d2635  lea     r8, [rbp+sourceString]
0x1800d2639  lea     rdx, MF_BYTESTREAM_CONTENT_TYPE
0x1800d2640  mov     rax, [rcx]
0x1800d2643  mov     rax, [rax+68h]
0x1800d2647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d264c  test    eax, eax
0x1800d264e  js      loc_1800D2712
0x1800d2654  mov     edx, [rbp+length]; length
0x1800d2657  mov     r8, rsi; string
0x1800d265a  mov     rcx, [rbp+sourceString]; sourceString
0x1800d265e  call    cs:__imp_WindowsCreateString
0x1800d2664  mov     ebx, eax
0x1800d2666  test    eax, eax
0x1800d2668  jns     loc_1800D2712
0x1800d266e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d2675  test    rcx, rcx
0x1800d2678  jnz     short loc_1800D26BB
0x1800d267a  mov     rcx, cs:stru_1801FC290.__vftable
0x1800d2681  lea     r8, stru_1801FC290
0x1800d2688  mov     edx, 7F0h
0x1800d268d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d2694  mov     rax, [rcx+8]
0x1800d2698  mov     rcx, r8
0x1800d269b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d26a0  test    eax, eax
0x1800d26a2  jnz     short loc_1800D26B4
0x1800d26a4  lea     rcx, stru_1801F8A30
0x1800d26ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d26b2  jmp     short loc_1800D26BB
0x1800d26b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d26bb  cmp     byte ptr [rcx+8], 0
0x1800d26bf  jz      short loc_1800D26E6
0x1800d26c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d26c6  cmp     [rax+7CCh], ebx
0x1800d26cc  jz      short loc_1800D26E6
0x1800d26ce  mov     r9d, ebx; int
0x1800d26d1  lea     rdx, aCwinrtstreamon_13; "CWinRTStreamOnMFByteStream::get_Content"...
0x1800d26d8  mov     r8d, 229h; int
0x1800d26de  mov     rcx, rax; this
0x1800d26e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d26e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d26ed  jb      short loc_1800D2712
0x1800d26ef  mov     edx, 53h ; 'S'
0x1800d26f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d26fb  lea     r8, WPP_2b7361d32eac31bbfd89b23d9726b9e0_Traceguids
0x1800d2702  mov     r9, rdi
0x1800d2705  mov     [rsp+30h+var_10], ebx
0x1800d2709  mov     rcx, [rcx+10h]
0x1800d270d  call    WPP_SF_qD
0x1800d2712  mov     rcx, [rbp+sourceString]; pv
0x1800d2716  call    cs:__imp_CoTaskMemFree
0x1800d271c  lea     rcx, [rbp+arg_18]
0x1800d2720  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d2725  lea     rcx, [r14+30h]; lpCriticalSection
0x1800d2729  call    cs:__imp_LeaveCriticalSection
0x1800d272f  lea     rcx, [rbp+arg_0]; this
0x1800d2733  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800d2738  mov     eax, ebx
0x1800d273a  add     rsp, 30h
0x1800d273e  pop     r14
0x1800d2740  pop     rdi
0x1800d2741  pop     rsi
0x1800d2742  pop     rbx
0x1800d2743  pop     rbp
0x1800d2744  retn
```
