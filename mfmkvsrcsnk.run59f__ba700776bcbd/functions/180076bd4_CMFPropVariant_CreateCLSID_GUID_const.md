# CMFPropVariant::CreateCLSID(_GUID const *)

- ea: `0x180076bd4`
- end: `0x180076cfe`
- name: `?CreateCLSID@CMFPropVariant@@QEAAJPEBU_GUID@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180051754`
- `0x1800748fc`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180076bd4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076bf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c38`

## string_xrefs

- `0x180076c05`: `CMFPropVariant::CreateCLSID`
- `0x180076c95`: `CMFPropVariant::CreateCLSID`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v9;
}

```

## disassembly

```asm
0x180076bd4  mov     [rsp+arg_8], rbx
0x180076bd9  mov     [rsp+arg_10], rsi
0x180076bde  push    rdi
0x180076bdf  sub     rsp, 30h
0x180076be3  mov     rdi, rcx
0x180076be6  mov     word ptr [rcx], 48h ; 'H'
0x180076beb  mov     ecx, 10h; cb
0x180076bf0  mov     rsi, rdx
0x180076bf3  call    cs:__imp_CoTaskMemAlloc
0x180076bfa  nop     dword ptr [rax+rax+00h]
0x180076bff  mov     r8d, 71Fh; int
0x180076c05  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x180076c0c  lea     rcx, [rsp+38h+arg_0]; this
0x180076c11  mov     [rdi+8], rax
0x180076c15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076c1a  mov     rax, [rdi+8]
0x180076c1e  test    rax, rax
0x180076c21  jnz     loc_180076CD8
0x180076c27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c2e  mov     ebx, 8007000Eh
0x180076c33  test    rcx, rcx
0x180076c36  jnz     short loc_180076C7F
0x180076c38  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076c3f  nop     dword ptr [rax+rax+00h]
0x180076c44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c4b  mov     rcx, rax
0x180076c4e  test    rax, rax
0x180076c51  jz      short loc_180076C71
0x180076c53  mov     rax, [rax]
0x180076c56  mov     edx, 7F0h
0x180076c5b  mov     rax, [rax+8]
0x180076c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c64  test    eax, eax
0x180076c66  jz      short loc_180076C71
0x180076c68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c6f  jmp     short loc_180076C7F
0x180076c71  lea     rcx, qword_1800DBF70; this
0x180076c78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c7f  cmp     byte ptr [rcx+8], 0
0x180076c83  jz      short loc_180076CAA
0x180076c85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076c8a  cmp     [rax+7CCh], ebx
0x180076c90  jz      short loc_180076CAA
0x180076c92  mov     r9d, ebx; int
0x180076c95  lea     rdx, aCmfpropvariant_3; "CMFPropVariant::CreateCLSID"
0x180076c9c  mov     r8d, 71Fh; int
0x180076ca2  mov     rcx, rax; this
0x180076ca5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076caa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076cb1  jb      short loc_180076CE1
0x180076cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180076cba  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180076cc1  mov     edx, 7Ah ; 'z'
0x180076cc6  mov     [rsp+38h+var_18], ebx
0x180076cca  mov     r9, rdi
0x180076ccd  mov     rcx, [rcx+10h]
0x180076cd1  call    WPP_SF_qD
0x180076cd6  jmp     short loc_180076CE1
0x180076cd8  movups  xmm0, xmmword ptr [rsi]
0x180076cdb  xor     ebx, ebx
0x180076cdd  movdqu  xmmword ptr [rax], xmm0
0x180076ce1  lea     rcx, [rsp+38h+arg_0]; this
0x180076ce6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180076ceb  mov     rsi, [rsp+38h+arg_10]
0x180076cf0  mov     eax, ebx
0x180076cf2  mov     rbx, [rsp+38h+arg_8]
0x180076cf7  add     rsp, 30h
0x180076cfb  pop     rdi
0x180076cfc  retn
```
