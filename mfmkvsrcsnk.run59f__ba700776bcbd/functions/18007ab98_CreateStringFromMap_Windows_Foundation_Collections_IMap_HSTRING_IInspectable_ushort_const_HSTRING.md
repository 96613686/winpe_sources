# CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)

- ea: `0x18007ab98`
- end: `0x18007adf2`
- name: `?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `602`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800789cc`
- `0x180079a58`
- `0x18007a0e4`
- `0x18007a794`
- `0x18007adf8`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180042d40`
- `0x18006c764`
- `0x1800744d8`
- `0x18007ab98`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ac1b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ac1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ac35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007ac35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ac6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ad1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ac6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ad1f`

## string_xrefs

- `0x18007abc9`: `CreateStringFromMap`
- `0x18007acc7`: `CreateStringFromMap`
- `0x18007ad7c`: `CreateStringFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
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
  _BYTE v23[4]; // [rsp+30h] [rbp-40h] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "CreateStringFromMap", 43);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v25);
  v7 = -1;
  length = 0;
  do
    ++v7;
  while ( a2[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  v9 = v6(a1, string, &v25);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 152LL))(v25, a3);
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
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v23);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007ab98  mov     [rsp-28h+arg_18], rbx
0x18007ab9d  push    rbp
0x18007ab9e  push    rsi
0x18007ab9f  push    rdi
0x18007aba0  push    r14
0x18007aba2  push    r15
0x18007aba4  mov     rbp, rsp
0x18007aba7  sub     rsp, 70h
0x18007abab  mov     rax, cs:__security_cookie
0x18007abb2  xor     rax, rsp
0x18007abb5  mov     [rbp+var_10], rax
0x18007abb9  xor     r15d, r15d
0x18007abbc  mov     rdi, r8
0x18007abbf  mov     rbx, rdx
0x18007abc2  mov     [rbp+var_38], r15
0x18007abc6  mov     rsi, rcx
0x18007abc9  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x18007abd0  lea     rcx, [rbp+var_40]; this
0x18007abd4  lea     r8d, [r15+2Bh]; int
0x18007abd8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007abdd  mov     rax, [rsi]
0x18007abe0  lea     rcx, [rbp+var_38]
0x18007abe4  mov     r14, [rax+30h]
0x18007abe8  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007abed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007abf1  mov     [rbp+length], r15d
0x18007abf5  inc     rcx; unsigned __int64
0x18007abf8  cmp     [rbx+rcx*2], r15w
0x18007abfd  jnz     short loc_18007ABF5
0x18007abff  lea     rdx, [rbp+length]; unsigned int *
0x18007ac03  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007ac08  test    eax, eax
0x18007ac0a  jns     short loc_18007AC27
0x18007ac0c  xor     r9d, r9d; lpArguments
0x18007ac0f  xor     r8d, r8d; nNumberOfArguments
0x18007ac12  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007ac17  lea     edx, [r9+1]; dwExceptionFlags
0x18007ac1b  call    cs:__imp_RaiseException
0x18007ac22  nop     dword ptr [rax+rax+00h]
0x18007ac27  mov     edx, [rbp+length]; length
0x18007ac2a  lea     r9, [rbp+string]; string
0x18007ac2e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007ac32  mov     rcx, rbx; sourceString
0x18007ac35  call    cs:__imp_WindowsCreateStringReference
0x18007ac3c  nop     dword ptr [rax+rax+00h]
0x18007ac41  mov     rdx, [rbp+string]
0x18007ac45  lea     r8, [rbp+var_38]
0x18007ac49  mov     rcx, rsi
0x18007ac4c  mov     rax, r14
0x18007ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac54  mov     ebx, eax
0x18007ac56  test    eax, eax
0x18007ac58  jns     loc_18007ACF3
0x18007ac5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ac65  test    rcx, rcx
0x18007ac68  jnz     short loc_18007ACB1
0x18007ac6a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ac71  nop     dword ptr [rax+rax+00h]
0x18007ac76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ac7d  mov     rcx, rax
0x18007ac80  test    rax, rax
0x18007ac83  jz      short loc_18007ACA3
0x18007ac85  mov     rax, [rax]
0x18007ac88  mov     edx, 7F0h
0x18007ac8d  mov     rax, [rax+8]
0x18007ac91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac96  test    eax, eax
0x18007ac98  jz      short loc_18007ACA3
0x18007ac9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aca1  jmp     short loc_18007ACB1
0x18007aca3  lea     rcx, qword_1800DBF70; this
0x18007acaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007acb1  cmp     [rcx+8], r15b
0x18007acb5  jz      short loc_18007ACDC
0x18007acb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007acbc  cmp     [rax+7CCh], ebx
0x18007acc2  jz      short loc_18007ACDC
0x18007acc4  mov     r9d, ebx; int
0x18007acc7  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x18007acce  mov     r8d, 2Bh ; '+'; int
0x18007acd4  mov     rcx, rax; this
0x18007acd7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007acdc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ace3  jb      loc_18007ADBD
0x18007ace9  mov     edx, 0Ah
0x18007acee  jmp     loc_18007AD9F
0x18007acf3  mov     rcx, [rbp+var_38]
0x18007acf7  mov     rdx, rdi
0x18007acfa  mov     rax, [rcx]
0x18007acfd  mov     rax, [rax+98h]
0x18007ad04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad09  mov     ebx, eax
0x18007ad0b  test    eax, eax
0x18007ad0d  jns     loc_18007ADBD
0x18007ad13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ad1a  test    rcx, rcx
0x18007ad1d  jnz     short loc_18007AD66
0x18007ad1f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ad26  nop     dword ptr [rax+rax+00h]
0x18007ad2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ad32  mov     rcx, rax
0x18007ad35  test    rax, rax
0x18007ad38  jz      short loc_18007AD58
0x18007ad3a  mov     rax, [rax]
0x18007ad3d  mov     edx, 7F0h
0x18007ad42  mov     rax, [rax+8]
0x18007ad46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad4b  test    eax, eax
0x18007ad4d  jz      short loc_18007AD58
0x18007ad4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ad56  jmp     short loc_18007AD66
0x18007ad58  lea     rcx, qword_1800DBF70; this
0x18007ad5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ad66  cmp     [rcx+8], r15b
0x18007ad6a  jz      short loc_18007AD91
0x18007ad6c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ad71  cmp     [rax+7CCh], ebx
0x18007ad77  jz      short loc_18007AD91
0x18007ad79  mov     r9d, ebx; int
0x18007ad7c  lea     rdx, aCreatestringfr; "CreateStringFromMap"
0x18007ad83  mov     r8d, 2Ch ; ','; int
0x18007ad89  mov     rcx, rax; this
0x18007ad8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ad91  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ad98  jb      short loc_18007ADBD
0x18007ad9a  mov     edx, 0Bh
0x18007ad9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ada6  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007adad  xor     r9d, r9d
0x18007adb0  mov     [rsp+70h+var_50], ebx
0x18007adb4  mov     rcx, [rcx+10h]
0x18007adb8  call    WPP_SF_qD
0x18007adbd  lea     rcx, [rbp+var_40]; this
0x18007adc1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007adc6  lea     rcx, [rbp+var_38]
0x18007adca  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007adcf  mov     eax, ebx
0x18007add1  mov     rcx, [rbp+var_10]
0x18007add5  xor     rcx, rsp; StackCookie
0x18007add8  call    __security_check_cookie
0x18007addd  mov     rbx, [rsp+70h+arg_18]
0x18007ade5  add     rsp, 70h
0x18007ade9  pop     r15
0x18007adeb  pop     r14
0x18007aded  pop     rdi
0x18007adee  pop     rsi
0x18007adef  pop     rbp
0x18007adf0  retn
```
