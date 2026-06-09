# GetSubMapFromMap

- ea: `0x18007bff8`
- end: `0x18007c257`
- name: `GetSubMapFromMap`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800789cc`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180042d40`
- `0x18006c764`
- `0x1800744d8`
- `0x18007bff8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007c07d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007c07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007c097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007c097`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007c0cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007c184`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007c0cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007c184`

## pseudocode

```c
__int64 __fastcall GetSubMapFromMap(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, _QWORD); // r14
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
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v23, "GetSubMapFromMap", 774);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)a1 + 48LL);
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
    v9 = (**v25)(v25, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, a3);
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
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007bff8  mov     [rsp-28h+arg_18], rbx
0x18007bffd  push    rbp
0x18007bffe  push    rsi
0x18007bfff  push    rdi
0x18007c000  push    r14
0x18007c002  push    r15
0x18007c004  mov     rbp, rsp
0x18007c007  sub     rsp, 70h
0x18007c00b  mov     rax, cs:__security_cookie
0x18007c012  xor     rax, rsp
0x18007c015  mov     [rbp+var_10], rax
0x18007c019  mov     rsi, r8
0x18007c01c  mov     rbx, rdx
0x18007c01f  mov     rdi, rcx
0x18007c022  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x18007c029  xor     r15d, r15d
0x18007c02c  lea     rcx, [rbp+var_40]; this
0x18007c030  mov     r8d, 306h; int
0x18007c036  mov     [rbp+var_38], r15
0x18007c03a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007c03f  mov     rax, [rdi]
0x18007c042  lea     rcx, [rbp+var_38]
0x18007c046  mov     r14, [rax+30h]
0x18007c04a  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007c04f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007c053  mov     [rbp+length], r15d
0x18007c057  inc     rcx; unsigned __int64
0x18007c05a  cmp     [rbx+rcx*2], r15w
0x18007c05f  jnz     short loc_18007C057
0x18007c061  lea     rdx, [rbp+length]; unsigned int *
0x18007c065  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007c06a  test    eax, eax
0x18007c06c  jns     short loc_18007C089
0x18007c06e  xor     r9d, r9d; lpArguments
0x18007c071  xor     r8d, r8d; nNumberOfArguments
0x18007c074  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007c079  lea     edx, [r9+1]; dwExceptionFlags
0x18007c07d  call    cs:__imp_RaiseException
0x18007c084  nop     dword ptr [rax+rax+00h]
0x18007c089  mov     edx, [rbp+length]; length
0x18007c08c  lea     r9, [rbp+string]; string
0x18007c090  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007c094  mov     rcx, rbx; sourceString
0x18007c097  call    cs:__imp_WindowsCreateStringReference
0x18007c09e  nop     dword ptr [rax+rax+00h]
0x18007c0a3  mov     rdx, [rbp+string]
0x18007c0a7  lea     r8, [rbp+var_38]
0x18007c0ab  mov     rcx, rdi
0x18007c0ae  mov     rax, r14
0x18007c0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0b6  mov     ebx, eax
0x18007c0b8  test    eax, eax
0x18007c0ba  jns     loc_18007C155
0x18007c0c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c0c7  test    rcx, rcx
0x18007c0ca  jnz     short loc_18007C113
0x18007c0cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007c0d3  nop     dword ptr [rax+rax+00h]
0x18007c0d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c0df  mov     rcx, rax
0x18007c0e2  test    rax, rax
0x18007c0e5  jz      short loc_18007C105
0x18007c0e7  mov     rax, [rax]
0x18007c0ea  mov     edx, 7F0h
0x18007c0ef  mov     rax, [rax+8]
0x18007c0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0f8  test    eax, eax
0x18007c0fa  jz      short loc_18007C105
0x18007c0fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c103  jmp     short loc_18007C113
0x18007c105  lea     rcx, qword_1800DBF70; this
0x18007c10c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c113  cmp     [rcx+8], r15b
0x18007c117  jz      short loc_18007C13E
0x18007c119  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007c11e  cmp     [rax+7CCh], ebx
0x18007c124  jz      short loc_18007C13E
0x18007c126  mov     r9d, ebx; int
0x18007c129  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x18007c130  mov     r8d, 306h; int
0x18007c136  mov     rcx, rax; this
0x18007c139  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007c13e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c145  jb      loc_18007C222
0x18007c14b  mov     edx, 66h ; 'f'
0x18007c150  jmp     loc_18007C204
0x18007c155  mov     rcx, [rbp+var_38]
0x18007c159  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007c160  mov     r8, rsi
0x18007c163  mov     rax, [rcx]
0x18007c166  mov     rax, [rax]
0x18007c169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c16e  mov     ebx, eax
0x18007c170  test    eax, eax
0x18007c172  jns     loc_18007C222
0x18007c178  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c17f  test    rcx, rcx
0x18007c182  jnz     short loc_18007C1CB
0x18007c184  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007c18b  nop     dword ptr [rax+rax+00h]
0x18007c190  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c197  mov     rcx, rax
0x18007c19a  test    rax, rax
0x18007c19d  jz      short loc_18007C1BD
0x18007c19f  mov     rax, [rax]
0x18007c1a2  mov     edx, 7F0h
0x18007c1a7  mov     rax, [rax+8]
0x18007c1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1b0  test    eax, eax
0x18007c1b2  jz      short loc_18007C1BD
0x18007c1b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c1bb  jmp     short loc_18007C1CB
0x18007c1bd  lea     rcx, qword_1800DBF70; this
0x18007c1c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007c1cb  cmp     [rcx+8], r15b
0x18007c1cf  jz      short loc_18007C1F6
0x18007c1d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007c1d6  cmp     [rax+7CCh], ebx
0x18007c1dc  jz      short loc_18007C1F6
0x18007c1de  mov     r9d, ebx; int
0x18007c1e1  lea     rdx, aGetsubmapfromm; "GetSubMapFromMap"
0x18007c1e8  mov     r8d, 307h; int
0x18007c1ee  mov     rcx, rax; this
0x18007c1f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007c1f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007c1fd  jb      short loc_18007C222
0x18007c1ff  mov     edx, 67h ; 'g'
0x18007c204  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c20b  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007c212  xor     r9d, r9d
0x18007c215  mov     [rsp+70h+var_50], ebx
0x18007c219  mov     rcx, [rcx+10h]
0x18007c21d  call    WPP_SF_qD
0x18007c222  lea     rcx, [rbp+var_40]; this
0x18007c226  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007c22b  lea     rcx, [rbp+var_38]
0x18007c22f  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007c234  mov     eax, ebx
0x18007c236  mov     rcx, [rbp+var_10]
0x18007c23a  xor     rcx, rsp; StackCookie
0x18007c23d  call    __security_check_cookie
0x18007c242  mov     rbx, [rsp+70h+arg_18]
0x18007c24a  add     rsp, 70h
0x18007c24e  pop     r15
0x18007c250  pop     r14
0x18007c252  pop     rdi
0x18007c253  pop     rsi
0x18007c254  pop     rbp
0x18007c255  retn
```
