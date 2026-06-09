# GetSubMapFromMap

- ea: `0x180078900`
- end: `0x180078b49`
- name: `GetSubMapFromMap`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007559c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180069a78`
- `0x180071330`
- `0x180078900`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078981`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180078981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078996`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800789c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078a7a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800789c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078a7a`

## pseudocode

```c
__int64 __fastcall GetSubMapFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, _QWORD); // r14
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
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-60h] BYREF
  HSTRING string; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-50h] BYREF

  v24 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "GetSubMapFromMap", 774);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)a1 + 48LL);
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
    v9 = (**v24)(v24, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, a3);
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
          CallStackContext::TraceFailure(ThreadRelativeContext, "GetSubMapFromMap", 775, v9);
      }
      if ( g_wppLevels )
      {
        v15 = 103;
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
        CallStackContext::TraceFailure(v14, "GetSubMapFromMap", 774, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 102;
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
0x180078900  mov     [rsp+arg_18], rbx
0x180078905  push    rbp
0x180078906  push    rsi
0x180078907  push    rdi
0x180078908  push    r14
0x18007890a  push    r15
0x18007890c  sub     rsp, 70h
0x180078910  mov     rax, cs:__security_cookie
0x180078917  xor     rax, rsp
0x18007891a  mov     [rsp+98h+var_38], rax
0x18007891f  mov     rbp, r8
0x180078922  mov     rdi, rdx
0x180078925  mov     rsi, rcx
0x180078928  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x18007892f  xor     r15d, r15d
0x180078932  lea     rcx, [rsp+98h+var_68]; this
0x180078937  mov     r8d, 306h; int
0x18007893d  mov     [rsp+98h+var_60], r15
0x180078942  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180078947  mov     rax, [rsi]
0x18007894a  lea     rcx, [rsp+98h+var_60]
0x18007894f  mov     r14, [rax+30h]
0x180078953  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180078958  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007895c  inc     rbx
0x18007895f  cmp     [rdi+rbx*2], r15w
0x180078964  jnz     short loc_18007895C
0x180078966  mov     eax, 0FFFFFFFFh
0x18007896b  cmp     rbx, rax
0x18007896e  jbe     short loc_180078987
0x180078970  xor     r9d, r9d; lpArguments
0x180078973  xor     r8d, r8d; nNumberOfArguments
0x180078976  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007897b  mov     ebx, eax
0x18007897d  lea     edx, [r9+1]; dwExceptionFlags
0x180078981  call    cs:__imp_RaiseException
0x180078987  lea     r9, [rsp+98h+string]; string
0x18007898c  mov     edx, ebx; length
0x18007898e  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180078993  mov     rcx, rdi; sourceString
0x180078996  call    cs:__imp_WindowsCreateStringReference
0x18007899c  mov     rdx, [rsp+98h+string]
0x1800789a1  lea     r8, [rsp+98h+var_60]
0x1800789a6  mov     rcx, rsi
0x1800789a9  mov     rax, r14
0x1800789ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789b1  mov     ebx, eax
0x1800789b3  test    eax, eax
0x1800789b5  jns     loc_180078A4A
0x1800789bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800789c2  test    rcx, rcx
0x1800789c5  jnz     short loc_180078A08
0x1800789c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800789cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800789d4  mov     rcx, rax
0x1800789d7  test    rax, rax
0x1800789da  jz      short loc_1800789FA
0x1800789dc  mov     rax, [rax]
0x1800789df  mov     edx, 7F0h
0x1800789e4  mov     rax, [rax+8]
0x1800789e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789ed  test    eax, eax
0x1800789ef  jz      short loc_1800789FA
0x1800789f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800789f8  jmp     short loc_180078A08
0x1800789fa  lea     rcx, qword_1800D6F70; this
0x180078a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a08  cmp     [rcx+8], r15b
0x180078a0c  jz      short loc_180078A33
0x180078a0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078a13  cmp     [rax+7CCh], ebx
0x180078a19  jz      short loc_180078A33
0x180078a1b  mov     r9d, ebx; int
0x180078a1e  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x180078a25  mov     r8d, 306h; int
0x180078a2b  mov     rcx, rax; this
0x180078a2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078a33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078a3a  jb      loc_180078B12
0x180078a40  mov     edx, 66h ; 'f'
0x180078a45  jmp     loc_180078AF4
0x180078a4a  mov     rcx, [rsp+98h+var_60]
0x180078a4f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180078a56  mov     r8, rbp
0x180078a59  mov     rax, [rcx]
0x180078a5c  mov     rax, [rax]
0x180078a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a64  mov     ebx, eax
0x180078a66  test    eax, eax
0x180078a68  jns     loc_180078B12
0x180078a6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a75  test    rcx, rcx
0x180078a78  jnz     short loc_180078ABB
0x180078a7a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078a80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078a87  mov     rcx, rax
0x180078a8a  test    rax, rax
0x180078a8d  jz      short loc_180078AAD
0x180078a8f  mov     rax, [rax]
0x180078a92  mov     edx, 7F0h
0x180078a97  mov     rax, [rax+8]
0x180078a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aa0  test    eax, eax
0x180078aa2  jz      short loc_180078AAD
0x180078aa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078aab  jmp     short loc_180078ABB
0x180078aad  lea     rcx, qword_1800D6F70; this
0x180078ab4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078abb  cmp     [rcx+8], r15b
0x180078abf  jz      short loc_180078AE6
0x180078ac1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078ac6  cmp     [rax+7CCh], ebx
0x180078acc  jz      short loc_180078AE6
0x180078ace  mov     r9d, ebx; int
0x180078ad1  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x180078ad8  mov     r8d, 307h; int
0x180078ade  mov     rcx, rax; this
0x180078ae1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078ae6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078aed  jb      short loc_180078B12
0x180078aef  mov     edx, 67h ; 'g'
0x180078af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180078afb  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180078b02  xor     r9d, r9d
0x180078b05  mov     [rsp+98h+var_78], ebx
0x180078b09  mov     rcx, [rcx+10h]
0x180078b0d  call    WPP_SF_qD
0x180078b12  lea     rcx, [rsp+98h+var_68]; this
0x180078b17  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180078b1c  lea     rcx, [rsp+98h+var_60]
0x180078b21  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180078b26  mov     eax, ebx
0x180078b28  mov     rcx, [rsp+98h+var_38]
0x180078b2d  xor     rcx, rsp; StackCookie
0x180078b30  call    __security_check_cookie
0x180078b35  mov     rbx, [rsp+98h+arg_18]
0x180078b3d  add     rsp, 70h
0x180078b41  pop     r15
0x180078b43  pop     r14
0x180078b45  pop     rdi
0x180078b46  pop     rsi
0x180078b47  pop     rbp
0x180078b48  retn
```
