# FindTypeInArray(ushort const *,Windows::Foundation::Collections::IVector<HSTRING__ *> *)

- ea: `0x18009454c`
- end: `0x180094793`
- name: `?FindTypeInArray@@YA_NPEBGPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ce20`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18009454c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800946a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800946a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009469d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009469d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800946b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009476f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800946b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009476f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall FindTypeInArray(__int64 a1, __int64 a2)
{
  char v4; // r14
  int v5; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *v7; // rax
  unsigned int i; // edi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  int v10; // ebx
  PCWSTR StringRawBuffer; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackScopeTrace v15; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v15, "FindTypeInArray", 164);
  v4 = 0;
  if ( a2 )
  {
    v16 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v16);
    if ( v5 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v16 )
          goto LABEL_28;
        string = 0;
        v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a2 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v10 = v9(a2, i, &string);
        if ( v10 < 0 )
          break;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !(unsigned int)_o__wcsicmp(a1, StringRawBuffer) )
        {
          v4 = 1;
LABEL_27:
          WindowsDeleteString(string);
          goto LABEL_28;
        }
        WindowsDeleteString(string);
      }
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
        if ( ThreadRelativeContext->m_result != v10 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "FindTypeInArray", 179, v10);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids, 0, v10);
      goto LABEL_27;
    }
    v6 = CallStackTracing::s_wpInstance;
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
      v7 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( v7->m_result != v5 )
        CallStackContext::TraceFailure(v7, "FindTypeInArray", 175, v5);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids, 0, v5);
  }
LABEL_28:
  CallStackScopeTrace::~CallStackScopeTrace(&v15);
  return v4;
}

```

## disassembly

```asm
0x18009454c  mov     [rsp-28h+arg_0], rbx
0x180094551  push    rbp
0x180094552  push    rsi
0x180094553  push    rdi
0x180094554  push    r14
0x180094556  push    r15
0x180094558  mov     rbp, rsp
0x18009455b  sub     rsp, 30h
0x18009455f  mov     rsi, rdx
0x180094562  mov     r15, rcx
0x180094565  mov     r8d, 0A4h; int
0x18009456b  lea     rdx, aFindtypeinarra; "FindTypeInArray"
0x180094572  lea     rcx, [rbp+arg_8]; this
0x180094576  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009457b  nop
0x18009457c  xor     r14b, r14b
0x18009457f  test    rsi, rsi
0x180094582  jz      loc_180094776
0x180094588  mov     [rbp+arg_10], 0
0x18009458f  mov     rax, [rsi]
0x180094592  lea     rdx, [rbp+arg_10]
0x180094596  mov     rcx, rsi
0x180094599  mov     rax, [rax+38h]
0x18009459d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800945a2  mov     ebx, eax
0x1800945a4  test    eax, eax
0x1800945a6  jns     loc_180094656
0x1800945ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945b3  test    rcx, rcx
0x1800945b6  jnz     short loc_1800945F6
0x1800945b8  lea     rcx, stru_1801FC290
0x1800945bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945c6  mov     rax, cs:stru_1801FC290.__vftable
0x1800945cd  mov     edx, 7F0h
0x1800945d2  mov     rax, [rax+8]
0x1800945d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800945db  test    eax, eax
0x1800945dd  jnz     short loc_1800945EF
0x1800945df  lea     rcx, stru_1801F8A30
0x1800945e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945ed  jmp     short loc_1800945F6
0x1800945ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800945f6  cmp     [rcx+8], r14b
0x1800945fa  jz      short loc_180094621
0x1800945fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094601  cmp     [rax+7CCh], ebx
0x180094607  jz      short loc_180094621
0x180094609  mov     r9d, ebx; int
0x18009460c  mov     r8d, 0AFh; int
0x180094612  lea     rdx, aFindtypeinarra; "FindTypeInArray"
0x180094619  mov     rcx, rax; this
0x18009461c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094621  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094628  jb      loc_180094776
0x18009462e  mov     edx, 14h
0x180094633  mov     [rsp+30h+var_10], ebx
0x180094637  xor     r9d, r9d
0x18009463a  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x180094641  mov     rcx, cs:WPP_GLOBAL_Control
0x180094648  mov     rcx, [rcx+10h]
0x18009464c  call    WPP_SF_qD
0x180094651  jmp     loc_180094776
0x180094656  xor     edi, edi
0x180094658  cmp     edi, [rbp+arg_10]
0x18009465b  jnb     loc_180094776
0x180094661  mov     [rbp+string], 0
0x180094669  mov     rax, [rsi]
0x18009466c  mov     rbx, [rax+30h]
0x180094670  xor     ecx, ecx; string
0x180094672  call    cs:__imp_WindowsDeleteString
0x180094678  mov     [rbp+string], 0
0x180094680  lea     r8, [rbp+string]
0x180094684  mov     edx, edi
0x180094686  mov     rcx, rsi
0x180094689  mov     rax, rbx
0x18009468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094691  mov     ebx, eax
0x180094693  test    eax, eax
0x180094695  js      short loc_1800946C9
0x180094697  xor     edx, edx; length
0x180094699  mov     rcx, [rbp+string]; string
0x18009469d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800946a3  mov     rdx, rax
0x1800946a6  mov     rcx, r15
0x1800946a9  call    cs:__imp__o__wcsicmp
0x1800946af  test    eax, eax
0x1800946b1  jz      short loc_1800946C1
0x1800946b3  mov     rcx, [rbp+string]; string
0x1800946b7  call    cs:__imp_WindowsDeleteString
0x1800946bd  inc     edi
0x1800946bf  jmp     short loc_180094658
0x1800946c1  mov     r14b, 1
0x1800946c4  jmp     loc_18009476B
0x1800946c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800946d0  test    rcx, rcx
0x1800946d3  jnz     short loc_180094713
0x1800946d5  lea     rcx, stru_1801FC290
0x1800946dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800946e3  mov     rax, cs:stru_1801FC290.__vftable
0x1800946ea  mov     edx, 7F0h
0x1800946ef  mov     rax, [rax+8]
0x1800946f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800946f8  test    eax, eax
0x1800946fa  jnz     short loc_18009470C
0x1800946fc  lea     rcx, stru_1801F8A30
0x180094703  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009470a  jmp     short loc_180094713
0x18009470c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180094713  cmp     byte ptr [rcx+8], 0
0x180094717  jz      short loc_18009473E
0x180094719  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009471e  cmp     [rax+7CCh], ebx
0x180094724  jz      short loc_18009473E
0x180094726  mov     r9d, ebx; int
0x180094729  mov     r8d, 0B3h; int
0x18009472f  lea     rdx, aFindtypeinarra; "FindTypeInArray"
0x180094736  mov     rcx, rax; this
0x180094739  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009473e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094745  jb      short loc_18009476B
0x180094747  mov     edx, 15h
0x18009474c  mov     [rsp+30h+var_10], ebx
0x180094750  xor     r9d, r9d
0x180094753  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x18009475a  mov     rcx, cs:WPP_GLOBAL_Control
0x180094761  mov     rcx, [rcx+10h]
0x180094765  call    WPP_SF_qD
0x18009476a  nop
0x18009476b  mov     rcx, [rbp+string]; string
0x18009476f  call    cs:__imp_WindowsDeleteString
0x180094775  nop
0x180094776  lea     rcx, [rbp+arg_8]; this
0x18009477a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009477f  mov     al, r14b
0x180094782  mov     rbx, [rsp+30h+arg_0]
0x180094787  add     rsp, 30h
0x18009478b  pop     r15
0x18009478d  pop     r14
0x18009478f  pop     rdi
0x180094790  pop     rsi
0x180094791  pop     rbp
0x180094792  retn
```
