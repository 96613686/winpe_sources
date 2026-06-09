# mkvparser::Block::Frame::Read(mkvparser::IMkvReader *,uchar *)

- ea: `0x1800ada50`
- end: `0x1800adb6c`
- name: `?Read@Frame@Block@mkvparser@@QEBAJPEAUIMkvReader@3@PEAE@Z`
- size: `284`
- prototype: `__int64 __fastcall(mkvparser::Block::Frame *__hidden this, struct mkvparser::IMkvReader *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025380`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800ada50`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adaad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adaad`

## string_xrefs

- `0x1800ada68`: `mkvparser::Block::Frame::Read`
- `0x1800adb0a`: `mkvparser::Block::Frame::Read`

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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Block::Frame::Read", 8892, v7);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 794, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v7);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ada50  mov     [rsp+arg_8], rbx
0x1800ada55  mov     [rsp+arg_10], rsi
0x1800ada5a  push    rdi
0x1800ada5b  sub     rsp, 30h
0x1800ada5f  mov     rbx, r8
0x1800ada62  mov     rdi, rdx
0x1800ada65  mov     rsi, rcx
0x1800ada68  lea     rdx, aMkvparserBlock; "mkvparser::Block::Frame::Read"
0x1800ada6f  mov     r8d, 22BCh; int
0x1800ada75  lea     rcx, [rsp+38h+arg_0]; this
0x1800ada7a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ada7f  mov     rax, [rdi]
0x1800ada82  mov     r9, rbx
0x1800ada85  mov     r8d, [rsi+8]
0x1800ada89  mov     rcx, rdi
0x1800ada8c  mov     rdx, [rsi]
0x1800ada8f  mov     rax, [rax]
0x1800ada92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ada97  mov     ebx, eax
0x1800ada99  test    eax, eax
0x1800ada9b  jns     loc_1800ADB4D
0x1800adaa1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adaa8  test    rcx, rcx
0x1800adaab  jnz     short loc_1800ADAF4
0x1800adaad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adab4  nop     dword ptr [rax+rax+00h]
0x1800adab9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adac0  mov     rcx, rax
0x1800adac3  test    rax, rax
0x1800adac6  jz      short loc_1800ADAE6
0x1800adac8  mov     rax, [rax]
0x1800adacb  mov     edx, 7F0h
0x1800adad0  mov     rax, [rax+8]
0x1800adad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adad9  test    eax, eax
0x1800adadb  jz      short loc_1800ADAE6
0x1800adadd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adae4  jmp     short loc_1800ADAF4
0x1800adae6  lea     rcx, qword_1800DBF70; this
0x1800adaed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adaf4  cmp     byte ptr [rcx+8], 0
0x1800adaf8  jz      short loc_1800ADB1F
0x1800adafa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adaff  cmp     [rax+7CCh], ebx
0x1800adb05  jz      short loc_1800ADB1F
0x1800adb07  mov     r9d, ebx; int
0x1800adb0a  lea     rdx, aMkvparserBlock; "mkvparser::Block::Frame::Read"
0x1800adb11  mov     r8d, 22BCh; int
0x1800adb17  mov     rcx, rax; this
0x1800adb1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adb1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adb26  jb      short loc_1800ADB4F
0x1800adb28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adb2f  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800adb36  mov     edx, 31Ah
0x1800adb3b  mov     [rsp+38h+var_18], ebx
0x1800adb3f  mov     r9, rsi
0x1800adb42  mov     rcx, [rcx+10h]
0x1800adb46  call    WPP_SF_qD
0x1800adb4b  jmp     short loc_1800ADB4F
0x1800adb4d  xor     ebx, ebx
0x1800adb4f  lea     rcx, [rsp+38h+arg_0]; this
0x1800adb54  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800adb59  mov     rsi, [rsp+38h+arg_10]
0x1800adb5e  mov     eax, ebx
0x1800adb60  mov     rbx, [rsp+38h+arg_8]
0x1800adb65  add     rsp, 30h
0x1800adb69  pop     rdi
0x1800adb6a  retn
```
