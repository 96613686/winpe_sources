# CxCodeVideoProcThread::PutWorkItem(tagRECT const &,long (*)(tagRECT const &,ParameterBase const *),ParameterBase const *)

- ea: `0x18000e090`
- end: `0x18000e1ef`
- name: `?PutWorkItem@CxCodeVideoProcThread@@QEAAJAEBUtagRECT@@P6AJ0PEBUParameterBase@@@Z1@Z`
- size: `351`
- prototype: `__int64 __fastcall(CxCodeVideoProcThread *__hidden this, const struct tagRECT *, int (*)(const struct tagRECT *, const struct ParameterBase *), const struct ParameterBase *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e200`

## callees

- `0x18000a954`
- `0x18000caec`
- `0x18000e090`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFPutWorkItem2` at `0x18000e10e`
- `MFPlat!MFPutWorkItem2` at `0x18000e10e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e150`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e150`

## string_xrefs

- `0x18000e0d1`: `CxCodeVideoProcThread::PutWorkItem`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThread::PutWorkItem(
        CxCodeVideoProcThread *this,
        const struct tagRECT *a2,
        int (*a3)(const struct tagRECT *, const struct ParameterBase *),
        const struct ParameterBase *a4)
{
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  HRESULT v9; // edi
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  char v14; // [rsp+40h] [rbp+8h] BYREF

  *((struct tagRECT *)this + 1) = *a2;
  *((_QWORD *)this + 5) = a3;
  *((_QWORD *)this + 4) = a4;
  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    v7 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v7 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v8 = 2 * v7;
      *((_QWORD *)ThreadRelativeContext + v8) = "CxCodeVideoProcThread::PutWorkItem";
      *((_DWORD *)ThreadRelativeContext + 2 * v8 + 2) = 208;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v9 = MFPutWorkItem2(*((_DWORD *)this + 14), 0, (IMFAsyncCallback *)this + 1, 0);
  if ( v9 < 0 )
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
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v9 )
        CallStackContext::TraceFailure(v13, "CxCodeVideoProcThread::PutWorkItem", 208, v9);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids, this, v9);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e090  mov     [rsp+arg_8], rbx
0x18000e095  mov     [rsp+arg_10], rsi
0x18000e09a  push    rdi
0x18000e09b  sub     rsp, 30h
0x18000e09f  mov     eax, [rdx+0Ch]
0x18000e0a2  mov     rbx, rcx
0x18000e0a5  mov     [rcx+1Ch], eax
0x18000e0a8  mov     eax, [rdx]
0x18000e0aa  mov     [rcx+10h], eax
0x18000e0ad  mov     eax, [rdx+8]
0x18000e0b0  mov     [rcx+18h], eax
0x18000e0b3  mov     eax, [rdx+4]
0x18000e0b6  mov     [rcx+14h], eax
0x18000e0b9  mov     [rcx+28h], r8
0x18000e0bd  mov     [rcx+20h], r9
0x18000e0c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000e0c8  test    rcx, rcx
0x18000e0cb  jz      short loc_18000E136
0x18000e0cd  cmp     byte ptr [rcx+8], 0
0x18000e0d1  lea     rsi, aCxcodevideopro_115; "CxCodeVideoProcThread::PutWorkItem"
0x18000e0d8  jz      short loc_18000E102
0x18000e0da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e0df  mov     ecx, [rax+7C4h]
0x18000e0e5  cmp     ecx, [rax+7C8h]
0x18000e0eb  jnb     short loc_18000E0FC
0x18000e0ed  add     rcx, rcx
0x18000e0f0  mov     [rax+rcx*8], rsi
0x18000e0f4  mov     dword ptr [rax+rcx*8+8], 0D0h
0x18000e0fc  inc     dword ptr [rax+7C4h]
0x18000e102  mov     ecx, [rbx+38h]; dwQueue
0x18000e105  lea     r8, [rbx+8]; pCallback
0x18000e109  xor     r9d, r9d; pState
0x18000e10c  xor     edx, edx; Priority
0x18000e10e  call    cs:__imp_MFPutWorkItem2
0x18000e114  mov     edi, eax
0x18000e116  test    eax, eax
0x18000e118  js      short loc_18000E144
0x18000e11a  lea     rcx, [rsp+38h+arg_0]; this
0x18000e11f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000e124  mov     rbx, [rsp+38h+arg_8]
0x18000e129  mov     eax, edi
0x18000e12b  mov     rsi, [rsp+38h+arg_10]
0x18000e130  add     rsp, 30h
0x18000e134  pop     rdi
0x18000e135  retn
0x18000e136  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000e13b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e142  jmp     short loc_18000E0CD
0x18000e144  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e14b  test    rcx, rcx
0x18000e14e  jnz     short loc_18000E1B4
0x18000e150  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000e156  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e15d  mov     rcx, rax
0x18000e160  test    rax, rax
0x18000e163  jz      short loc_18000E1A6
0x18000e165  mov     rax, [rax]
0x18000e168  mov     edx, 7F0h
0x18000e16d  mov     rax, [rax+8]
0x18000e171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e176  test    eax, eax
0x18000e178  jz      short loc_18000E1A6
0x18000e17a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e181  jmp     short loc_18000E1B4
0x18000e183  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e188  cmp     [rax+7CCh], edi
0x18000e18e  jz      short loc_18000E1BA
0x18000e190  mov     r9d, edi; int
0x18000e193  mov     r8d, 0D0h; int
0x18000e199  mov     rdx, rsi; char *
0x18000e19c  mov     rcx, rax; this
0x18000e19f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e1a4  jmp     short loc_18000E1BA
0x18000e1a6  lea     rcx, qword_180153440; this
0x18000e1ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e1b4  cmp     byte ptr [rcx+8], 0
0x18000e1b8  jnz     short loc_18000E183
0x18000e1ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e1c1  jb      loc_18000E11A
0x18000e1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ce  lea     r8, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids
0x18000e1d5  mov     edx, 0Eh
0x18000e1da  mov     [rsp+38h+var_18], edi
0x18000e1de  mov     r9, rbx
0x18000e1e1  mov     rcx, [rcx+10h]
0x18000e1e5  call    WPP_SF_qD
0x18000e1ea  jmp     loc_18000E11A
```
