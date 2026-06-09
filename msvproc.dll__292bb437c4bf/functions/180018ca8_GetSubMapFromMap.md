# GetSubMapFromMap

- ea: `0x180018ca8`
- end: `0x180018f26`
- name: `GetSubMapFromMap`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180018708`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018ca8`
- `0x18003639c`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018d29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018ddb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018e57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018ddb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018e57`

## pseudocode

```c
__int64 __fastcall GetSubMapFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, _QWORD); // r14
  unsigned __int64 v7; // rbx
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rcx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  _BYTE v18[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-60h] BYREF
  HSTRING string; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-50h] BYREF

  v19 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "GetSubMapFromMap", 774);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
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
  v8 = v6(a1, string, &v19);
  if ( v8 < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "GetSubMapFromMap", 774, v8);
    }
    if ( g_wppLevels )
    {
      v17 = 102;
LABEL_30:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
    }
  }
  else
  {
    v8 = (**v19)(v19, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, a3);
    if ( v8 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "GetSubMapFromMap", 775, v8);
      }
      if ( g_wppLevels )
      {
        v17 = 103;
        goto LABEL_30;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  v9 = v19;
  if ( v19 )
  {
    v19 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v9)[2])(v9);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018ca8  mov     [rsp+arg_18], rbx
0x180018cad  push    rbp
0x180018cae  push    rsi
0x180018caf  push    rdi
0x180018cb0  push    r14
0x180018cb2  push    r15
0x180018cb4  sub     rsp, 70h
0x180018cb8  mov     rax, cs:__security_cookie
0x180018cbf  xor     rax, rsp
0x180018cc2  mov     [rsp+98h+var_38], rax
0x180018cc7  mov     rbp, r8
0x180018cca  mov     rdi, rdx
0x180018ccd  mov     rsi, rcx
0x180018cd0  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x180018cd7  xor     r15d, r15d
0x180018cda  lea     rcx, [rsp+98h+var_68]; this
0x180018cdf  mov     r8d, 306h; int
0x180018ce5  mov     [rsp+98h+var_60], r15
0x180018cea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018cef  mov     rax, [rsi]
0x180018cf2  lea     rcx, [rsp+98h+var_60]
0x180018cf7  mov     r14, [rax+30h]
0x180018cfb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018d00  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018d04  inc     rbx
0x180018d07  cmp     [rdi+rbx*2], r15w
0x180018d0c  jnz     short loc_180018D04
0x180018d0e  mov     eax, 0FFFFFFFFh
0x180018d13  cmp     rbx, rax
0x180018d16  jbe     short loc_180018D2F
0x180018d18  xor     r9d, r9d; lpArguments
0x180018d1b  xor     r8d, r8d; nNumberOfArguments
0x180018d1e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018d23  mov     ebx, eax
0x180018d25  lea     edx, [r9+1]; dwExceptionFlags
0x180018d29  call    cs:__imp_RaiseException
0x180018d2f  lea     r9, [rsp+98h+string]; string
0x180018d34  mov     edx, ebx; length
0x180018d36  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180018d3b  mov     rcx, rdi; sourceString
0x180018d3e  call    cs:__imp_WindowsCreateStringReference
0x180018d44  mov     rdx, [rsp+98h+string]
0x180018d49  lea     r8, [rsp+98h+var_60]
0x180018d4e  mov     rcx, rsi
0x180018d51  mov     rax, r14
0x180018d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d59  mov     ebx, eax
0x180018d5b  test    eax, eax
0x180018d5d  js      short loc_180018DCB
0x180018d5f  mov     rcx, [rsp+98h+var_60]
0x180018d64  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180018d6b  mov     r8, rbp
0x180018d6e  mov     rax, [rcx]
0x180018d71  mov     rax, [rax]
0x180018d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d79  mov     ebx, eax
0x180018d7b  test    eax, eax
0x180018d7d  js      loc_180018E47
0x180018d83  lea     rcx, [rsp+98h+var_68]; this
0x180018d88  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180018d8d  mov     rcx, [rsp+98h+var_60]
0x180018d92  test    rcx, rcx
0x180018d95  jz      short loc_180018DA8
0x180018d97  mov     [rsp+98h+var_60], r15
0x180018d9c  mov     rax, [rcx]
0x180018d9f  mov     rax, [rax+10h]
0x180018da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018da8  mov     eax, ebx
0x180018daa  mov     rcx, [rsp+98h+var_38]
0x180018daf  xor     rcx, rsp; StackCookie
0x180018db2  call    __security_check_cookie
0x180018db7  mov     rbx, [rsp+98h+arg_18]
0x180018dbf  add     rsp, 70h
0x180018dc3  pop     r15
0x180018dc5  pop     r14
0x180018dc7  pop     rdi
0x180018dc8  pop     rsi
0x180018dc9  pop     rbp
0x180018dca  retn
0x180018dcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018dd2  test    rcx, rcx
0x180018dd5  jnz     loc_180018EBF
0x180018ddb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018de1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018de8  mov     rcx, rax
0x180018deb  test    rax, rax
0x180018dee  jz      loc_180018EB1
0x180018df4  mov     rax, [rax]
0x180018df7  mov     edx, 7F0h
0x180018dfc  mov     rax, [rax+8]
0x180018e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e05  test    eax, eax
0x180018e07  jz      loc_180018EB1
0x180018e0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e14  jmp     loc_180018EBF
0x180018e19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018e1e  cmp     [rax+7CCh], ebx
0x180018e24  jz      loc_180018EC9
0x180018e2a  mov     r9d, ebx; int
0x180018e2d  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x180018e34  mov     r8d, 306h; int
0x180018e3a  mov     rcx, rax; this
0x180018e3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018e42  jmp     loc_180018EC9
0x180018e47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e4e  test    rcx, rcx
0x180018e51  jnz     loc_180018EEB
0x180018e57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018e5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e64  mov     rcx, rax
0x180018e67  test    rax, rax
0x180018e6a  jz      short loc_180018EDD
0x180018e6c  mov     rax, [rax]
0x180018e6f  mov     edx, 7F0h
0x180018e74  mov     rax, [rax+8]
0x180018e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e7d  test    eax, eax
0x180018e7f  jz      short loc_180018EDD
0x180018e81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018e88  jmp     short loc_180018EEB
0x180018e8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018e8f  cmp     [rax+7CCh], ebx
0x180018e95  jz      short loc_180018EF1
0x180018e97  mov     r9d, ebx; int
0x180018e9a  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x180018ea1  mov     r8d, 307h; int
0x180018ea7  mov     rcx, rax; this
0x180018eaa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018eaf  jmp     short loc_180018EF1
0x180018eb1  lea     rcx, qword_180153440; this
0x180018eb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018ebf  cmp     [rcx+8], r15b
0x180018ec3  jnz     loc_180018E19
0x180018ec9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018ed0  jb      loc_180018D83
0x180018ed6  mov     edx, 66h ; 'f'
0x180018edb  jmp     short loc_180018F03
0x180018edd  lea     rcx, qword_180153440; this
0x180018ee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018eeb  cmp     [rcx+8], r15b
0x180018eef  jnz     short loc_180018E8A
0x180018ef1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018ef8  jb      loc_180018D83
0x180018efe  mov     edx, 67h ; 'g'
0x180018f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f0a  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180018f11  xor     r9d, r9d
0x180018f14  mov     [rsp+98h+var_78], ebx
0x180018f18  mov     rcx, [rcx+10h]
0x180018f1c  call    WPP_SF_qD
0x180018f21  jmp     loc_180018D83
```
