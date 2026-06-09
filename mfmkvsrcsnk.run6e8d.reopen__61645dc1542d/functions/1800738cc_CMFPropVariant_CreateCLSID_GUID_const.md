# CMFPropVariant::CreateCLSID(_GUID const *)

- ea: `0x1800738cc`
- end: `0x1800739e9`
- name: `?CreateCLSID@CMFPropVariant@@QEAAJPEBU_GUID@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004f524`
- `0x180071710`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800738cc`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800738eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800738eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007392a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007392a`

## string_xrefs

- `0x1800738f7`: `CMFPropVariant::CreateCLSID`
- `0x180073981`: `CMFPropVariant::CreateCLSID`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateCLSID(CMFPropVariant *this, const struct _GUID *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _GUID *v7; // rax
  __int64 *v8; // rcx
  unsigned int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+40h] [rbp+8h] BYREF

  *(_WORD *)this = 72;
  *((_QWORD *)this + 1) = CoTaskMemAlloc(0x10u);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CMFPropVariant::CreateCLSID", 1823);
  v7 = (struct _GUID *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    v9 = 0;
    *v7 = *a2;
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateCLSID", 1823, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v9;
}

```

## disassembly

```asm
0x1800738cc  mov     [rsp+arg_8], rbx
0x1800738d1  mov     [rsp+arg_10], rsi
0x1800738d6  push    rdi
0x1800738d7  sub     rsp, 30h
0x1800738db  mov     rdi, rcx
0x1800738de  mov     word ptr [rcx], 48h ; 'H'
0x1800738e3  mov     ecx, 10h; cb
0x1800738e8  mov     rsi, rdx
0x1800738eb  call    cs:__imp_CoTaskMemAlloc
0x1800738f1  mov     r8d, 71Fh; int
0x1800738f7  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x1800738fe  lea     rcx, [rsp+38h+arg_0]; this
0x180073903  mov     [rdi+8], rax
0x180073907  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007390c  mov     rax, [rdi+8]
0x180073910  test    rax, rax
0x180073913  jnz     loc_1800739C4
0x180073919  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073920  mov     ebx, 8007000Eh
0x180073925  test    rcx, rcx
0x180073928  jnz     short loc_18007396B
0x18007392a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073930  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073937  mov     rcx, rax
0x18007393a  test    rax, rax
0x18007393d  jz      short loc_18007395D
0x18007393f  mov     rax, [rax]
0x180073942  mov     edx, 7F0h
0x180073947  mov     rax, [rax+8]
0x18007394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073950  test    eax, eax
0x180073952  jz      short loc_18007395D
0x180073954  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007395b  jmp     short loc_18007396B
0x18007395d  lea     rcx, qword_1800D6F70; this
0x180073964  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007396b  cmp     byte ptr [rcx+8], 0
0x18007396f  jz      short loc_180073996
0x180073971  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073976  cmp     [rax+7CCh], ebx
0x18007397c  jz      short loc_180073996
0x18007397e  mov     r9d, ebx; int
0x180073981  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x180073988  mov     r8d, 71Fh; int
0x18007398e  mov     rcx, rax; this
0x180073991  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073996  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007399d  jb      short loc_1800739CD
0x18007399f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800739a6  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800739ad  mov     edx, 7Ah ; 'z'
0x1800739b2  mov     [rsp+38h+var_18], ebx
0x1800739b6  mov     r9, rdi
0x1800739b9  mov     rcx, [rcx+10h]
0x1800739bd  call    WPP_SF_qD
0x1800739c2  jmp     short loc_1800739CD
0x1800739c4  movups  xmm0, xmmword ptr [rsi]
0x1800739c7  xor     ebx, ebx
0x1800739c9  movdqu  xmmword ptr [rax], xmm0
0x1800739cd  lea     rcx, [rsp+38h+arg_0]; this
0x1800739d2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800739d7  mov     rsi, [rsp+38h+arg_10]
0x1800739dc  mov     eax, ebx
0x1800739de  mov     rbx, [rsp+38h+arg_8]
0x1800739e3  add     rsp, 30h
0x1800739e7  pop     rdi
0x1800739e8  retn
```
