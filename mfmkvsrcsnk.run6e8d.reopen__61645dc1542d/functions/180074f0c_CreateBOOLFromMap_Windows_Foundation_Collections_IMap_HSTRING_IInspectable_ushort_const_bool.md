# CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)

- ea: `0x180074f0c`
- end: `0x180075156`
- name: `?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007656c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180069a78`
- `0x180071330`
- `0x180074f0c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074f8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180074f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180074f9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074fcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007509f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074fcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007509f`

## string_xrefs

- `0x180074f35`: `CreateBOOLFromMap`
- `0x180075024`: `CreateBOOLFromMap`
- `0x1800750f6`: `CreateBOOLFromMap`

## pseudocode

```c
__int64 __fastcall CreateBOOLFromMap(__int64 a1, const WCHAR *a2, bool *a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // r15
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
  char v23; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v24[7]; // [rsp+31h] [rbp-3Fh] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "CreateBOOLFromMap", 135);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v25);
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
  v9 = v6(a1, string, &v25);
  if ( v9 >= 0 )
  {
    v23 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v25 + 144LL))(v25, &v23);
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
        v19 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
    }
  }
LABEL_29:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180074f0c  push    rbp
0x180074f0e  push    rbx
0x180074f0f  push    rsi
0x180074f10  push    rdi
0x180074f11  push    r12
0x180074f13  push    r14
0x180074f15  push    r15
0x180074f17  mov     rbp, rsp
0x180074f1a  sub     rsp, 70h
0x180074f1e  mov     rax, cs:__security_cookie
0x180074f25  xor     rax, rsp
0x180074f28  mov     [rbp+var_10], rax
0x180074f2c  mov     rsi, r8
0x180074f2f  mov     rdi, rdx
0x180074f32  mov     r14, rcx
0x180074f35  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x180074f3c  xor     r12d, r12d
0x180074f3f  lea     rcx, [rbp+var_3F]; this
0x180074f43  mov     r8d, 87h; int
0x180074f49  mov     [rbp+var_38], r12
0x180074f4d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180074f52  mov     rax, [r14]
0x180074f55  lea     rcx, [rbp+var_38]
0x180074f59  mov     r15, [rax+30h]
0x180074f5d  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180074f62  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180074f66  inc     rbx
0x180074f69  cmp     [rdi+rbx*2], r12w
0x180074f6e  jnz     short loc_180074F66
0x180074f70  mov     eax, 0FFFFFFFFh
0x180074f75  cmp     rbx, rax
0x180074f78  jbe     short loc_180074F91
0x180074f7a  xor     r9d, r9d; lpArguments
0x180074f7d  xor     r8d, r8d; nNumberOfArguments
0x180074f80  mov     ecx, 0C000000Dh; dwExceptionCode
0x180074f85  mov     ebx, eax
0x180074f87  lea     edx, [r9+1]; dwExceptionFlags
0x180074f8b  call    cs:__imp_RaiseException
0x180074f91  lea     r9, [rbp+string]; string
0x180074f95  mov     edx, ebx; length
0x180074f97  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180074f9b  mov     rcx, rdi; sourceString
0x180074f9e  call    cs:__imp_WindowsCreateStringReference
0x180074fa4  mov     rdx, [rbp+string]
0x180074fa8  lea     r8, [rbp+var_38]
0x180074fac  mov     rcx, r14
0x180074faf  mov     rax, r15
0x180074fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fb7  mov     ebx, eax
0x180074fb9  test    eax, eax
0x180074fbb  jns     loc_18007506E
0x180074fc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074fc8  test    rcx, rcx
0x180074fcb  jnz     short loc_18007500E
0x180074fcd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180074fd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180074fda  mov     rcx, rax
0x180074fdd  test    rax, rax
0x180074fe0  jz      short loc_180075000
0x180074fe2  mov     rax, [rax]
0x180074fe5  mov     edx, 7F0h
0x180074fea  mov     rax, [rax+8]
0x180074fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ff3  test    eax, eax
0x180074ff5  jz      short loc_180075000
0x180074ff7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180074ffe  jmp     short loc_18007500E
0x180075000  lea     rcx, qword_1800D6F70; this
0x180075007  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007500e  cmp     [rcx+8], r12b
0x180075012  jz      short loc_180075039
0x180075014  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075019  cmp     [rax+7CCh], ebx
0x18007501f  jz      short loc_180075039
0x180075021  mov     r9d, ebx; int
0x180075024  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x18007502b  mov     r8d, 87h; int
0x180075031  mov     rcx, rax; this
0x180075034  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075039  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075040  jb      loc_180075127
0x180075046  mov     edx, 14h
0x18007504b  mov     rcx, cs:WPP_GLOBAL_Control
0x180075052  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180075059  xor     r9d, r9d
0x18007505c  mov     [rsp+70h+var_50], ebx
0x180075060  mov     rcx, [rcx+10h]
0x180075064  call    WPP_SF_qD
0x180075069  jmp     loc_180075127
0x18007506e  mov     rcx, [rbp+var_38]
0x180075072  lea     rdx, [rbp+var_40]
0x180075076  mov     [rbp+var_40], r12b
0x18007507a  mov     rax, [rcx]
0x18007507d  mov     rax, [rax+90h]
0x180075084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075089  mov     ebx, eax
0x18007508b  test    eax, eax
0x18007508d  jns     loc_18007511E
0x180075093  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007509a  test    rcx, rcx
0x18007509d  jnz     short loc_1800750E0
0x18007509f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800750a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800750ac  mov     rcx, rax
0x1800750af  test    rax, rax
0x1800750b2  jz      short loc_1800750D2
0x1800750b4  mov     rax, [rax]
0x1800750b7  mov     edx, 7F0h
0x1800750bc  mov     rax, [rax+8]
0x1800750c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750c5  test    eax, eax
0x1800750c7  jz      short loc_1800750D2
0x1800750c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800750d0  jmp     short loc_1800750E0
0x1800750d2  lea     rcx, qword_1800D6F70; this
0x1800750d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800750e0  cmp     [rcx+8], r12b
0x1800750e4  jz      short loc_18007510B
0x1800750e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800750eb  cmp     [rax+7CCh], ebx
0x1800750f1  jz      short loc_18007510B
0x1800750f3  mov     r9d, ebx; int
0x1800750f6  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x1800750fd  mov     r8d, 8Ah; int
0x180075103  mov     rcx, rax; this
0x180075106  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007510b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075112  jb      short loc_180075127
0x180075114  mov     edx, 15h
0x180075119  jmp     loc_18007504B
0x18007511e  cmp     [rbp+var_40], r12b
0x180075122  setnz   al
0x180075125  mov     [rsi], al
0x180075127  lea     rcx, [rbp+var_3F]; this
0x18007512b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180075130  lea     rcx, [rbp+var_38]
0x180075134  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180075139  mov     eax, ebx
0x18007513b  mov     rcx, [rbp+var_10]
0x18007513f  xor     rcx, rsp; StackCookie
0x180075142  call    __security_check_cookie
0x180075147  add     rsp, 70h
0x18007514b  pop     r15
0x18007514d  pop     r14
0x18007514f  pop     r12
0x180075151  pop     rdi
0x180075152  pop     rsi
0x180075153  pop     rbx
0x180075154  pop     rbp
0x180075155  retn
```
