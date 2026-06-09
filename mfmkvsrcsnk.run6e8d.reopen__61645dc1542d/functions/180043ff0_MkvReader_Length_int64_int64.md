# MkvReader::Length(__int64 *,__int64 *)

- ea: `0x180043ff0`
- end: `0x18004424d`
- name: `?Length@MkvReader@@UEAAJPEA_J0@Z`
- size: `605`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180043ff0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800440d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044183`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800440d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044183`

## string_xrefs

- `0x18004400e`: `MkvReader::Length`
- `0x180044097`: `MkvReader::Length`
- `0x180044134`: `MkvReader::Length`
- `0x1800441e5`: `MkvReader::Length`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvReader::Length(MkvReader *this, __int64 *a2, __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  unsigned int v11; // ebx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "MkvReader::Length", 395);
  if ( a2 )
  {
    if ( a3 )
    {
      v17 = *((_QWORD *)this + 25);
      if ( v17 < 0 || *((_QWORD *)this + 26) <= v17 )
      {
        *a2 = v17;
        *a3 = *((_QWORD *)this + 26);
        v11 = 0;
        goto LABEL_37;
      }
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      v11 = -1072875845;
      if ( *((_BYTE *)v18 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::Length", 400, -1072875845);
      }
      if ( g_wppLevels )
      {
        v13 = 25;
        goto LABEL_35;
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      v11 = -2147467261;
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v16, "MkvReader::Length", 396, -2147467261);
      }
      if ( g_wppLevels )
      {
        v13 = 24;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v11 = -2147467261;
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "MkvReader::Length", 395, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 23;
LABEL_35:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v11);
    }
  }
LABEL_37:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return v11;
}

```

## disassembly

```asm
0x180043ff0  mov     [rsp+arg_0], rbx
0x180043ff5  mov     [rsp+arg_10], rsi
0x180043ffa  push    rdi
0x180043ffb  sub     rsp, 30h
0x180043fff  mov     rbx, r8
0x180044002  mov     rsi, rdx
0x180044005  mov     rdi, rcx
0x180044008  mov     r8d, 18Bh; int
0x18004400e  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x180044015  lea     rcx, [rsp+38h+arg_8]; this
0x18004401a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004401f  nop
0x180044020  test    rsi, rsi
0x180044023  jnz     loc_1800440BD
0x180044029  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044030  test    rcx, rcx
0x180044033  jnz     short loc_180044076
0x180044035  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004403b  mov     rcx, rax
0x18004403e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044045  test    rax, rax
0x180044048  jz      short loc_180044068
0x18004404a  mov     rax, [rax]
0x18004404d  mov     edx, 7F0h
0x180044052  mov     rax, [rax+8]
0x180044056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004405b  test    eax, eax
0x18004405d  jz      short loc_180044068
0x18004405f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044066  jmp     short loc_180044076
0x180044068  lea     rcx, qword_1800D6F70; this
0x18004406f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044076  mov     ebx, 80004003h
0x18004407b  cmp     byte ptr [rcx+8], 0
0x18004407f  jz      short loc_1800440A6
0x180044081  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044086  cmp     [rax+7CCh], ebx
0x18004408c  jz      short loc_1800440A6
0x18004408e  mov     r9d, ebx; int
0x180044091  mov     r8d, 18Bh; int
0x180044097  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x18004409e  mov     rcx, rax; this
0x1800440a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800440a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800440ad  jb      loc_180044231
0x1800440b3  mov     edx, 17h
0x1800440b8  jmp     loc_180044202
0x1800440bd  test    rbx, rbx
0x1800440c0  jnz     loc_18004415A
0x1800440c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800440cd  test    rcx, rcx
0x1800440d0  jnz     short loc_180044113
0x1800440d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800440d8  mov     rcx, rax
0x1800440db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800440e2  test    rax, rax
0x1800440e5  jz      short loc_180044105
0x1800440e7  mov     rax, [rax]
0x1800440ea  mov     edx, 7F0h
0x1800440ef  mov     rax, [rax+8]
0x1800440f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440f8  test    eax, eax
0x1800440fa  jz      short loc_180044105
0x1800440fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044103  jmp     short loc_180044113
0x180044105  lea     rcx, qword_1800D6F70; this
0x18004410c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044113  mov     ebx, 80004003h
0x180044118  cmp     byte ptr [rcx+8], 0
0x18004411c  jz      short loc_180044143
0x18004411e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044123  cmp     [rax+7CCh], ebx
0x180044129  jz      short loc_180044143
0x18004412b  mov     r9d, ebx; int
0x18004412e  mov     r8d, 18Ch; int
0x180044134  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x18004413b  mov     rcx, rax; this
0x18004413e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044143  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004414a  jb      loc_180044231
0x180044150  mov     edx, 18h
0x180044155  jmp     loc_180044202
0x18004415a  mov     rax, [rdi+0C8h]
0x180044161  test    rax, rax
0x180044164  js      loc_180044222
0x18004416a  cmp     [rdi+0D0h], rax
0x180044171  jle     loc_180044222
0x180044177  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004417e  test    rcx, rcx
0x180044181  jnz     short loc_1800441C4
0x180044183  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044189  mov     rcx, rax
0x18004418c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044193  test    rax, rax
0x180044196  jz      short loc_1800441B6
0x180044198  mov     rax, [rax]
0x18004419b  mov     edx, 7F0h
0x1800441a0  mov     rax, [rax+8]
0x1800441a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441a9  test    eax, eax
0x1800441ab  jz      short loc_1800441B6
0x1800441ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800441b4  jmp     short loc_1800441C4
0x1800441b6  lea     rcx, qword_1800D6F70; this
0x1800441bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800441c4  mov     ebx, 0C00D36BBh
0x1800441c9  cmp     byte ptr [rcx+8], 0
0x1800441cd  jz      short loc_1800441F4
0x1800441cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800441d4  cmp     [rax+7CCh], ebx
0x1800441da  jz      short loc_1800441F4
0x1800441dc  mov     r9d, ebx; int
0x1800441df  mov     r8d, 190h; int
0x1800441e5  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x1800441ec  mov     rcx, rax; this
0x1800441ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800441f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800441fb  jb      short loc_180044231
0x1800441fd  mov     edx, 19h
0x180044202  mov     [rsp+38h+var_18], ebx
0x180044206  mov     r9, rdi
0x180044209  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044210  mov     rcx, cs:WPP_GLOBAL_Control
0x180044217  mov     rcx, [rcx+10h]
0x18004421b  call    WPP_SF_qD
0x180044220  jmp     short loc_180044231
0x180044222  mov     [rsi], rax
0x180044225  mov     rax, [rdi+0D0h]
0x18004422c  mov     [rbx], rax
0x18004422f  xor     ebx, ebx
0x180044231  lea     rcx, [rsp+38h+arg_8]; this
0x180044236  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004423b  mov     eax, ebx
0x18004423d  mov     rbx, [rsp+38h+arg_0]
0x180044242  mov     rsi, [rsp+38h+arg_10]
0x180044247  add     rsp, 30h
0x18004424b  pop     rdi
0x18004424c  retn
```
