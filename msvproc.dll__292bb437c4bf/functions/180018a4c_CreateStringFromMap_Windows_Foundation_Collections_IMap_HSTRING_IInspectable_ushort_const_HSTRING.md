# CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)

- ea: `0x180018a4c`
- end: `0x180018ca1`
- name: `?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `597`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800180fc`
- `0x180018f2c`
- `0x1800347d0`
- `0x1800ca854`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018a4c`
- `0x18003639c`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018acb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018acb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018ae0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018bc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018bc1`

## string_xrefs

- `0x180018a7c`: `CreateStringFromMap`
- `0x180018b68`: `CreateStringFromMap`
- `0x180018c18`: `CreateStringFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // rbp
  unsigned __int64 v7; // rbx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rcx
  _BYTE v18[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v19; // [rsp+38h] [rbp-60h] BYREF
  HSTRING string; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-50h] BYREF

  v19 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "CreateStringFromMap", 43);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
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
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 152LL))(v19, a3);
    if ( v8 < 0 )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringFromMap", 44, v8);
      }
      if ( g_wppLevels )
      {
        v12 = 11;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CreateStringFromMap", 43, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 10;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018a4c  mov     [rsp+arg_18], rbx
0x180018a51  push    rbp
0x180018a52  push    rsi
0x180018a53  push    rdi
0x180018a54  push    r14
0x180018a56  push    r15
0x180018a58  sub     rsp, 70h
0x180018a5c  mov     rax, cs:__security_cookie
0x180018a63  xor     rax, rsp
0x180018a66  mov     [rsp+98h+var_38], rax
0x180018a6b  xor     r15d, r15d
0x180018a6e  mov     rsi, r8
0x180018a71  mov     rdi, rdx
0x180018a74  mov     [rsp+98h+var_60], r15
0x180018a79  mov     r14, rcx
0x180018a7c  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x180018a83  lea     rcx, [rsp+98h+var_68]; this
0x180018a88  lea     r8d, [r15+2Bh]; int
0x180018a8c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018a91  mov     rax, [r14]
0x180018a94  lea     rcx, [rsp+98h+var_60]
0x180018a99  mov     rbp, [rax+30h]
0x180018a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018aa2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018aa6  inc     rbx
0x180018aa9  cmp     [rdi+rbx*2], r15w
0x180018aae  jnz     short loc_180018AA6
0x180018ab0  mov     eax, 0FFFFFFFFh
0x180018ab5  cmp     rbx, rax
0x180018ab8  jbe     short loc_180018AD1
0x180018aba  xor     r9d, r9d; lpArguments
0x180018abd  xor     r8d, r8d; nNumberOfArguments
0x180018ac0  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018ac5  mov     ebx, eax
0x180018ac7  lea     edx, [r9+1]; dwExceptionFlags
0x180018acb  call    cs:__imp_RaiseException
0x180018ad1  lea     r9, [rsp+98h+string]; string
0x180018ad6  mov     edx, ebx; length
0x180018ad8  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180018add  mov     rcx, rdi; sourceString
0x180018ae0  call    cs:__imp_WindowsCreateStringReference
0x180018ae6  mov     rdx, [rsp+98h+string]
0x180018aeb  lea     r8, [rsp+98h+var_60]
0x180018af0  mov     rcx, r14
0x180018af3  mov     rax, rbp
0x180018af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018afb  mov     ebx, eax
0x180018afd  test    eax, eax
0x180018aff  jns     loc_180018B94
0x180018b05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b0c  test    rcx, rcx
0x180018b0f  jnz     short loc_180018B52
0x180018b11  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018b17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b1e  mov     rcx, rax
0x180018b21  test    rax, rax
0x180018b24  jz      short loc_180018B44
0x180018b26  mov     rax, [rax]
0x180018b29  mov     edx, 7F0h
0x180018b2e  mov     rax, [rax+8]
0x180018b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b37  test    eax, eax
0x180018b39  jz      short loc_180018B44
0x180018b3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b42  jmp     short loc_180018B52
0x180018b44  lea     rcx, qword_180153440; this
0x180018b4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018b52  cmp     [rcx+8], r15b
0x180018b56  jz      short loc_180018B7D
0x180018b58  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018b5d  cmp     [rax+7CCh], ebx
0x180018b63  jz      short loc_180018B7D
0x180018b65  mov     r9d, ebx; int
0x180018b68  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x180018b6f  mov     r8d, 2Bh ; '+'; int
0x180018b75  mov     rcx, rax; this
0x180018b78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018b7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018b84  jb      loc_180018C59
0x180018b8a  mov     edx, 0Ah
0x180018b8f  jmp     loc_180018C3B
0x180018b94  mov     rcx, [rsp+98h+var_60]
0x180018b99  mov     rdx, rsi
0x180018b9c  mov     rax, [rcx]
0x180018b9f  mov     rax, [rax+98h]
0x180018ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bab  mov     ebx, eax
0x180018bad  test    eax, eax
0x180018baf  jns     loc_180018C59
0x180018bb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018bbc  test    rcx, rcx
0x180018bbf  jnz     short loc_180018C02
0x180018bc1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018bc7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018bce  mov     rcx, rax
0x180018bd1  test    rax, rax
0x180018bd4  jz      short loc_180018BF4
0x180018bd6  mov     rax, [rax]
0x180018bd9  mov     edx, 7F0h
0x180018bde  mov     rax, [rax+8]
0x180018be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018be7  test    eax, eax
0x180018be9  jz      short loc_180018BF4
0x180018beb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018bf2  jmp     short loc_180018C02
0x180018bf4  lea     rcx, qword_180153440; this
0x180018bfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018c02  cmp     [rcx+8], r15b
0x180018c06  jz      short loc_180018C2D
0x180018c08  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018c0d  cmp     [rax+7CCh], ebx
0x180018c13  jz      short loc_180018C2D
0x180018c15  mov     r9d, ebx; int
0x180018c18  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x180018c1f  mov     r8d, 2Ch ; ','; int
0x180018c25  mov     rcx, rax; this
0x180018c28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018c2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018c34  jb      short loc_180018C59
0x180018c36  mov     edx, 0Bh
0x180018c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c42  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180018c49  xor     r9d, r9d
0x180018c4c  mov     [rsp+98h+var_78], ebx
0x180018c50  mov     rcx, [rcx+10h]
0x180018c54  call    WPP_SF_qD
0x180018c59  lea     rcx, [rsp+98h+var_68]; this
0x180018c5e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180018c63  mov     rcx, [rsp+98h+var_60]
0x180018c68  test    rcx, rcx
0x180018c6b  jz      short loc_180018C7E
0x180018c6d  mov     [rsp+98h+var_60], r15
0x180018c72  mov     rax, [rcx]
0x180018c75  mov     rax, [rax+10h]
0x180018c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c7e  mov     eax, ebx
0x180018c80  mov     rcx, [rsp+98h+var_38]
0x180018c85  xor     rcx, rsp; StackCookie
0x180018c88  call    __security_check_cookie
0x180018c8d  mov     rbx, [rsp+98h+arg_18]
0x180018c95  add     rsp, 70h
0x180018c99  pop     r15
0x180018c9b  pop     r14
0x180018c9d  pop     rdi
0x180018c9e  pop     rsi
0x180018c9f  pop     rbp
0x180018ca0  retn
```
