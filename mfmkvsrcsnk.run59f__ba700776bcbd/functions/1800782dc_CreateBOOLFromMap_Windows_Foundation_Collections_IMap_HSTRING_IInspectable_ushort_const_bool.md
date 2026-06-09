# CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)

- ea: `0x1800782dc`
- end: `0x18007854b`
- name: `?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079a58`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180042d40`
- `0x18006c764`
- `0x1800744d8`
- `0x1800782dc`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078361`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007837b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007837b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800783b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078488`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800783b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078488`

## string_xrefs

- `0x180078306`: `CreateBOOLFromMap`
- `0x18007840d`: `CreateBOOLFromMap`
- `0x1800784e5`: `CreateBOOLFromMap`

## pseudocode

```c
__int64 __fastcall CreateBOOLFromMap(__int64 a1, const WCHAR *a2, bool *a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v23; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v24[3]; // [rsp+31h] [rbp-3Fh] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v26 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "CreateBOOLFromMap", 135);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v26);
  v7 = -1;
  length = 0;
  do
    ++v7;
  while ( a2[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  v9 = v6(a1, string, &v26);
  if ( v9 >= 0 )
  {
    v23 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 144LL))(v26, &v23);
    if ( v9 >= 0 )
    {
      *a3 = v23 != 0;
      goto LABEL_29;
    }
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateBOOLFromMap", 138, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 21;
      goto LABEL_16;
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v9 )
        CallStackContext::TraceFailure(v14, "CreateBOOLFromMap", 135, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 20;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
    }
  }
LABEL_29:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v26);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800782dc  mov     [rsp-28h+arg_18], rbx
0x1800782e1  push    rbp
0x1800782e2  push    rsi
0x1800782e3  push    rdi
0x1800782e4  push    r14
0x1800782e6  push    r15
0x1800782e8  mov     rbp, rsp
0x1800782eb  sub     rsp, 70h
0x1800782ef  mov     rax, cs:__security_cookie
0x1800782f6  xor     rax, rsp
0x1800782f9  mov     [rbp+var_10], rax
0x1800782fd  mov     rdi, r8
0x180078300  mov     rbx, rdx
0x180078303  mov     rsi, rcx
0x180078306  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x18007830d  xor     r15d, r15d
0x180078310  lea     rcx, [rbp+var_3F]; this
0x180078314  mov     r8d, 87h; int
0x18007831a  mov     [rbp+var_38], r15
0x18007831e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180078323  mov     rax, [rsi]
0x180078326  lea     rcx, [rbp+var_38]
0x18007832a  mov     r14, [rax+30h]
0x18007832e  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180078333  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180078337  mov     [rbp+length], r15d
0x18007833b  inc     rcx; unsigned __int64
0x18007833e  cmp     [rbx+rcx*2], r15w
0x180078343  jnz     short loc_18007833B
0x180078345  lea     rdx, [rbp+length]; unsigned int *
0x180078349  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007834e  test    eax, eax
0x180078350  jns     short loc_18007836D
0x180078352  xor     r9d, r9d; lpArguments
0x180078355  xor     r8d, r8d; nNumberOfArguments
0x180078358  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007835d  lea     edx, [r9+1]; dwExceptionFlags
0x180078361  call    cs:__imp_RaiseException
0x180078368  nop     dword ptr [rax+rax+00h]
0x18007836d  mov     edx, [rbp+length]; length
0x180078370  lea     r9, [rbp+string]; string
0x180078374  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180078378  mov     rcx, rbx; sourceString
0x18007837b  call    cs:__imp_WindowsCreateStringReference
0x180078382  nop     dword ptr [rax+rax+00h]
0x180078387  mov     rdx, [rbp+string]
0x18007838b  lea     r8, [rbp+var_38]
0x18007838f  mov     rcx, rsi
0x180078392  mov     rax, r14
0x180078395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007839a  mov     ebx, eax
0x18007839c  test    eax, eax
0x18007839e  jns     loc_180078457
0x1800783a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783ab  test    rcx, rcx
0x1800783ae  jnz     short loc_1800783F7
0x1800783b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800783b7  nop     dword ptr [rax+rax+00h]
0x1800783bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783c3  mov     rcx, rax
0x1800783c6  test    rax, rax
0x1800783c9  jz      short loc_1800783E9
0x1800783cb  mov     rax, [rax]
0x1800783ce  mov     edx, 7F0h
0x1800783d3  mov     rax, [rax+8]
0x1800783d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783dc  test    eax, eax
0x1800783de  jz      short loc_1800783E9
0x1800783e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783e7  jmp     short loc_1800783F7
0x1800783e9  lea     rcx, qword_1800DBF70; this
0x1800783f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783f7  cmp     [rcx+8], r15b
0x1800783fb  jz      short loc_180078422
0x1800783fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078402  cmp     [rax+7CCh], ebx
0x180078408  jz      short loc_180078422
0x18007840a  mov     r9d, ebx; int
0x18007840d  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x180078414  mov     r8d, 87h; int
0x18007841a  mov     rcx, rax; this
0x18007841d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078422  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078429  jb      loc_180078516
0x18007842f  mov     edx, 14h
0x180078434  mov     rcx, cs:WPP_GLOBAL_Control
0x18007843b  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180078442  xor     r9d, r9d
0x180078445  mov     [rsp+70h+var_50], ebx
0x180078449  mov     rcx, [rcx+10h]
0x18007844d  call    WPP_SF_qD
0x180078452  jmp     loc_180078516
0x180078457  mov     rcx, [rbp+var_38]
0x18007845b  lea     rdx, [rbp+var_40]
0x18007845f  mov     [rbp+var_40], r15b
0x180078463  mov     rax, [rcx]
0x180078466  mov     rax, [rax+90h]
0x18007846d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078472  mov     ebx, eax
0x180078474  test    eax, eax
0x180078476  jns     loc_18007850D
0x18007847c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078483  test    rcx, rcx
0x180078486  jnz     short loc_1800784CF
0x180078488  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007848f  nop     dword ptr [rax+rax+00h]
0x180078494  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007849b  mov     rcx, rax
0x18007849e  test    rax, rax
0x1800784a1  jz      short loc_1800784C1
0x1800784a3  mov     rax, [rax]
0x1800784a6  mov     edx, 7F0h
0x1800784ab  mov     rax, [rax+8]
0x1800784af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784b4  test    eax, eax
0x1800784b6  jz      short loc_1800784C1
0x1800784b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800784bf  jmp     short loc_1800784CF
0x1800784c1  lea     rcx, qword_1800DBF70; this
0x1800784c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800784cf  cmp     [rcx+8], r15b
0x1800784d3  jz      short loc_1800784FA
0x1800784d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800784da  cmp     [rax+7CCh], ebx
0x1800784e0  jz      short loc_1800784FA
0x1800784e2  mov     r9d, ebx; int
0x1800784e5  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x1800784ec  mov     r8d, 8Ah; int
0x1800784f2  mov     rcx, rax; this
0x1800784f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800784fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078501  jb      short loc_180078516
0x180078503  mov     edx, 15h
0x180078508  jmp     loc_180078434
0x18007850d  cmp     [rbp+var_40], r15b
0x180078511  setnz   al
0x180078514  mov     [rdi], al
0x180078516  lea     rcx, [rbp+var_3F]; this
0x18007851a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007851f  lea     rcx, [rbp+var_38]
0x180078523  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180078528  mov     eax, ebx
0x18007852a  mov     rcx, [rbp+var_10]
0x18007852e  xor     rcx, rsp; StackCookie
0x180078531  call    __security_check_cookie
0x180078536  mov     rbx, [rsp+70h+arg_18]
0x18007853e  add     rsp, 70h
0x180078542  pop     r15
0x180078544  pop     r14
0x180078546  pop     rdi
0x180078547  pop     rsi
0x180078548  pop     rbp
0x180078549  retn
```
