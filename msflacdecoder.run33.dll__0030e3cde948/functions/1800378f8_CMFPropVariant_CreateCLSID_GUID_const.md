# CMFPropVariant::CreateCLSID(_GUID const *)

- ea: `0x1800378f8`
- end: `0x180037a15`
- name: `?CreateCLSID@CMFPropVariant@@QEAAJPEBU_GUID@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035148`
- `0x180046384`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x1800378f8`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037917`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037956`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037956`

## string_xrefs

- `0x180037923`: `CMFPropVariant::CreateCLSID`
- `0x1800379ad`: `CMFPropVariant::CreateCLSID`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateCLSID(CMFPropVariant *this, const struct _GUID *a2)
{
  __int64 v4; // rdx
  struct _GUID *v5; // rax
  __int64 *v6; // rcx
  unsigned int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+40h] [rbp+8h] BYREF

  *(_WORD *)this = 72;
  *((_QWORD *)this + 1) = CoTaskMemAlloc(0x10u);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CMFPropVariant::CreateCLSID", 1823);
  v5 = (struct _GUID *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v7 = 0;
    *v5 = *a2;
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateCLSID", 1823, -2147024882);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return v7;
}

```

## disassembly

```asm
0x1800378f8  mov     [rsp+arg_8], rbx
0x1800378fd  mov     [rsp+arg_10], rsi
0x180037902  push    rdi
0x180037903  sub     rsp, 30h
0x180037907  mov     rdi, rcx
0x18003790a  mov     word ptr [rcx], 48h ; 'H'
0x18003790f  mov     ecx, 10h; cb
0x180037914  mov     rsi, rdx
0x180037917  call    cs:__imp_CoTaskMemAlloc
0x18003791d  mov     r8d, 71Fh; int
0x180037923  lea     rdx, aCmfpropvariant_5; "CMFPropVariant::CreateCLSID"
0x18003792a  lea     rcx, [rsp+38h+arg_0]; this
0x18003792f  mov     [rdi+8], rax
0x180037933  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037938  mov     rax, [rdi+8]
0x18003793c  test    rax, rax
0x18003793f  jnz     loc_1800379F0
0x180037945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003794c  mov     ebx, 8007000Eh
0x180037951  test    rcx, rcx
0x180037954  jnz     short loc_180037997
0x180037956  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003795c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037963  mov     rcx, rax
0x180037966  test    rax, rax
0x180037969  jz      short loc_180037989
0x18003796b  mov     rax, [rax]
0x18003796e  mov     edx, 7F0h
0x180037973  mov     rax, [rax+8]
0x180037977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003797c  test    eax, eax
0x18003797e  jz      short loc_180037989
0x180037980  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037987  jmp     short loc_180037997
0x180037989  lea     rcx, qword_18006EB20; this
0x180037990  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037997  cmp     byte ptr [rcx+8], 0
0x18003799b  jz      short loc_1800379C2
0x18003799d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800379a2  cmp     [rax+7CCh], ebx
0x1800379a8  jz      short loc_1800379C2
0x1800379aa  mov     r9d, ebx; int
0x1800379ad  lea     rdx, aCmfpropvariant_5; "CMFPropVariant::CreateCLSID"
0x1800379b4  mov     r8d, 71Fh; int
0x1800379ba  mov     rcx, rax; this
0x1800379bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800379c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800379c7  cmp     al, 1
0x1800379c9  jb      short loc_1800379F9
0x1800379cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379d2  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800379d9  mov     edx, 7Ah ; 'z'
0x1800379de  mov     [rsp+38h+var_18], ebx
0x1800379e2  mov     r9, rdi
0x1800379e5  mov     rcx, [rcx+10h]
0x1800379e9  call    WPP_SF_qd
0x1800379ee  jmp     short loc_1800379F9
0x1800379f0  movups  xmm0, xmmword ptr [rsi]
0x1800379f3  xor     ebx, ebx
0x1800379f5  movdqu  xmmword ptr [rax], xmm0
0x1800379f9  lea     rcx, [rsp+38h+arg_0]; this
0x1800379fe  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180037a03  mov     rsi, [rsp+38h+arg_10]
0x180037a08  mov     eax, ebx
0x180037a0a  mov     rbx, [rsp+38h+arg_8]
0x180037a0f  add     rsp, 30h
0x180037a13  pop     rdi
0x180037a14  retn
```
