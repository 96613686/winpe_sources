# CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)

- ea: `0x1800775b0`
- end: `0x1800777f4`
- name: `?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `580`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007559c`
- `0x18007656c`
- `0x180076bb0`
- `0x1800771e4`
- `0x1800777fc`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180069a78`
- `0x180071330`
- `0x1800775b0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007762f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007762f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077644`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077675`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077725`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077675`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077725`

## string_xrefs

- `0x1800775e0`: `CreateStringFromMap`
- `0x1800776cc`: `CreateStringFromMap`
- `0x18007777c`: `CreateStringFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // rbp
  unsigned __int64 v7; // rbx
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
  _BYTE v23[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v24; // [rsp+38h] [rbp-60h] BYREF
  HSTRING string; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-50h] BYREF

  v24 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CreateStringFromMap", 43);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v24);
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    LODWORD(v7) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v7, &hstringHeader, &string);
  v9 = v6(a1, string, &v24);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 152LL))(v24, a3);
    if ( v9 < 0 )
    {
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
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringFromMap", 44, v9);
      }
      if ( g_wppLevels )
      {
        v15 = 11;
        goto LABEL_27;
      }
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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v9 )
        CallStackContext::TraceFailure(v14, "CreateStringFromMap", 43, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 10;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800775b0  mov     [rsp+arg_18], rbx
0x1800775b5  push    rbp
0x1800775b6  push    rsi
0x1800775b7  push    rdi
0x1800775b8  push    r14
0x1800775ba  push    r15
0x1800775bc  sub     rsp, 70h
0x1800775c0  mov     rax, cs:__security_cookie
0x1800775c7  xor     rax, rsp
0x1800775ca  mov     [rsp+98h+var_38], rax
0x1800775cf  xor     r15d, r15d
0x1800775d2  mov     rsi, r8
0x1800775d5  mov     rdi, rdx
0x1800775d8  mov     [rsp+98h+var_60], r15
0x1800775dd  mov     r14, rcx
0x1800775e0  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x1800775e7  lea     rcx, [rsp+98h+var_68]; this
0x1800775ec  lea     r8d, [r15+2Bh]; int
0x1800775f0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800775f5  mov     rax, [r14]
0x1800775f8  lea     rcx, [rsp+98h+var_60]
0x1800775fd  mov     rbp, [rax+30h]
0x180077601  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180077606  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007760a  inc     rbx
0x18007760d  cmp     [rdi+rbx*2], r15w
0x180077612  jnz     short loc_18007760A
0x180077614  mov     eax, 0FFFFFFFFh
0x180077619  cmp     rbx, rax
0x18007761c  jbe     short loc_180077635
0x18007761e  xor     r9d, r9d; lpArguments
0x180077621  xor     r8d, r8d; nNumberOfArguments
0x180077624  mov     ecx, 0C000000Dh; dwExceptionCode
0x180077629  mov     ebx, eax
0x18007762b  lea     edx, [r9+1]; dwExceptionFlags
0x18007762f  call    cs:__imp_RaiseException
0x180077635  lea     r9, [rsp+98h+string]; string
0x18007763a  mov     edx, ebx; length
0x18007763c  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180077641  mov     rcx, rdi; sourceString
0x180077644  call    cs:__imp_WindowsCreateStringReference
0x18007764a  mov     rdx, [rsp+98h+string]
0x18007764f  lea     r8, [rsp+98h+var_60]
0x180077654  mov     rcx, r14
0x180077657  mov     rax, rbp
0x18007765a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007765f  mov     ebx, eax
0x180077661  test    eax, eax
0x180077663  jns     loc_1800776F8
0x180077669  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077670  test    rcx, rcx
0x180077673  jnz     short loc_1800776B6
0x180077675  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007767b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077682  mov     rcx, rax
0x180077685  test    rax, rax
0x180077688  jz      short loc_1800776A8
0x18007768a  mov     rax, [rax]
0x18007768d  mov     edx, 7F0h
0x180077692  mov     rax, [rax+8]
0x180077696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007769b  test    eax, eax
0x18007769d  jz      short loc_1800776A8
0x18007769f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800776a6  jmp     short loc_1800776B6
0x1800776a8  lea     rcx, qword_1800D6F70; this
0x1800776af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800776b6  cmp     [rcx+8], r15b
0x1800776ba  jz      short loc_1800776E1
0x1800776bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800776c1  cmp     [rax+7CCh], ebx
0x1800776c7  jz      short loc_1800776E1
0x1800776c9  mov     r9d, ebx; int
0x1800776cc  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x1800776d3  mov     r8d, 2Bh ; '+'; int
0x1800776d9  mov     rcx, rax; this
0x1800776dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800776e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800776e8  jb      loc_1800777BD
0x1800776ee  mov     edx, 0Ah
0x1800776f3  jmp     loc_18007779F
0x1800776f8  mov     rcx, [rsp+98h+var_60]
0x1800776fd  mov     rdx, rsi
0x180077700  mov     rax, [rcx]
0x180077703  mov     rax, [rax+98h]
0x18007770a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007770f  mov     ebx, eax
0x180077711  test    eax, eax
0x180077713  jns     loc_1800777BD
0x180077719  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077720  test    rcx, rcx
0x180077723  jnz     short loc_180077766
0x180077725  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007772b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077732  mov     rcx, rax
0x180077735  test    rax, rax
0x180077738  jz      short loc_180077758
0x18007773a  mov     rax, [rax]
0x18007773d  mov     edx, 7F0h
0x180077742  mov     rax, [rax+8]
0x180077746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007774b  test    eax, eax
0x18007774d  jz      short loc_180077758
0x18007774f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077756  jmp     short loc_180077766
0x180077758  lea     rcx, qword_1800D6F70; this
0x18007775f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077766  cmp     [rcx+8], r15b
0x18007776a  jz      short loc_180077791
0x18007776c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077771  cmp     [rax+7CCh], ebx
0x180077777  jz      short loc_180077791
0x180077779  mov     r9d, ebx; int
0x18007777c  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x180077783  mov     r8d, 2Ch ; ','; int
0x180077789  mov     rcx, rax; this
0x18007778c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077791  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077798  jb      short loc_1800777BD
0x18007779a  mov     edx, 0Bh
0x18007779f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800777a6  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800777ad  xor     r9d, r9d
0x1800777b0  mov     [rsp+98h+var_78], ebx
0x1800777b4  mov     rcx, [rcx+10h]
0x1800777b8  call    WPP_SF_qD
0x1800777bd  lea     rcx, [rsp+98h+var_68]; this
0x1800777c2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800777c7  lea     rcx, [rsp+98h+var_60]
0x1800777cc  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x1800777d1  mov     eax, ebx
0x1800777d3  mov     rcx, [rsp+98h+var_38]
0x1800777d8  xor     rcx, rsp; StackCookie
0x1800777db  call    __security_check_cookie
0x1800777e0  mov     rbx, [rsp+98h+arg_18]
0x1800777e8  add     rsp, 70h
0x1800777ec  pop     r15
0x1800777ee  pop     r14
0x1800777f0  pop     rdi
0x1800777f1  pop     rsi
0x1800777f2  pop     rbp
0x1800777f3  retn
```
