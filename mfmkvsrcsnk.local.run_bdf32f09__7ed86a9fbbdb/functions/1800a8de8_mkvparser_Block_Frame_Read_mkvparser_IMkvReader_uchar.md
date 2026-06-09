# mkvparser::Block::Frame::Read(mkvparser::IMkvReader *,uchar *)

- ea: `0x1800a8de8`
- end: `0x1800a8efd`
- name: `?Read@Frame@Block@mkvparser@@QEBAJPEAUIMkvReader@3@PEAE@Z`
- size: `277`
- prototype: `__int64 __fastcall(mkvparser::Block::Frame *__hidden this, struct mkvparser::IMkvReader *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024440`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800a8de8`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8e45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8e45`

## string_xrefs

- `0x1800a8e00`: `mkvparser::Block::Frame::Read`
- `0x1800a8e9c`: `mkvparser::Block::Frame::Read`

## pseudocode

```c
__int64 __fastcall mkvparser::Block::Frame::Read(
        mkvparser::Block::Frame *this,
        struct mkvparser::IMkvReader *a2,
        unsigned __int8 *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v14, "mkvparser::Block::Frame::Read", 8892);
  v7 = (**(__int64 (__fastcall ***)(struct mkvparser::IMkvReader *, _QWORD, _QWORD, unsigned __int8 *))a2)(
         a2,
         *(_QWORD *)this,
         *((unsigned int *)this + 2),
         a3);
  if ( v7 >= 0 )
  {
    v7 = 0;
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Block::Frame::Read", 8892, v7);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 794, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v7);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a8de8  mov     [rsp+arg_8], rbx
0x1800a8ded  mov     [rsp+arg_10], rsi
0x1800a8df2  push    rdi
0x1800a8df3  sub     rsp, 30h
0x1800a8df7  mov     rbx, r8
0x1800a8dfa  mov     rdi, rdx
0x1800a8dfd  mov     rsi, rcx
0x1800a8e00  lea     rdx, aMkvparserBlock; "mkvparser::Block::Frame::Read"
0x1800a8e07  mov     r8d, 22BCh; int
0x1800a8e0d  lea     rcx, [rsp+38h+arg_0]; this
0x1800a8e12  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8e17  mov     rax, [rdi]
0x1800a8e1a  mov     r9, rbx
0x1800a8e1d  mov     r8d, [rsi+8]
0x1800a8e21  mov     rcx, rdi
0x1800a8e24  mov     rdx, [rsi]
0x1800a8e27  mov     rax, [rax]
0x1800a8e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e2f  mov     ebx, eax
0x1800a8e31  test    eax, eax
0x1800a8e33  jns     loc_1800A8EDF
0x1800a8e39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e40  test    rcx, rcx
0x1800a8e43  jnz     short loc_1800A8E86
0x1800a8e45  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8e4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e52  mov     rcx, rax
0x1800a8e55  test    rax, rax
0x1800a8e58  jz      short loc_1800A8E78
0x1800a8e5a  mov     rax, [rax]
0x1800a8e5d  mov     edx, 7F0h
0x1800a8e62  mov     rax, [rax+8]
0x1800a8e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e6b  test    eax, eax
0x1800a8e6d  jz      short loc_1800A8E78
0x1800a8e6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e76  jmp     short loc_1800A8E86
0x1800a8e78  lea     rcx, qword_1800D6F70; this
0x1800a8e7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e86  cmp     byte ptr [rcx+8], 0
0x1800a8e8a  jz      short loc_1800A8EB1
0x1800a8e8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8e91  cmp     [rax+7CCh], ebx
0x1800a8e97  jz      short loc_1800A8EB1
0x1800a8e99  mov     r9d, ebx; int
0x1800a8e9c  lea     rdx, aMkvparserBlock; "mkvparser::Block::Frame::Read"
0x1800a8ea3  mov     r8d, 22BCh; int
0x1800a8ea9  mov     rcx, rax; this
0x1800a8eac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8eb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8eb8  jb      short loc_1800A8EE1
0x1800a8eba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8ec1  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a8ec8  mov     edx, 31Ah
0x1800a8ecd  mov     [rsp+38h+var_18], ebx
0x1800a8ed1  mov     r9, rsi
0x1800a8ed4  mov     rcx, [rcx+10h]
0x1800a8ed8  call    WPP_SF_qD
0x1800a8edd  jmp     short loc_1800A8EE1
0x1800a8edf  xor     ebx, ebx
0x1800a8ee1  lea     rcx, [rsp+38h+arg_0]; this
0x1800a8ee6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a8eeb  mov     rsi, [rsp+38h+arg_10]
0x1800a8ef0  mov     eax, ebx
0x1800a8ef2  mov     rbx, [rsp+38h+arg_8]
0x1800a8ef7  add     rsp, 30h
0x1800a8efb  pop     rdi
0x1800a8efc  retn
```
