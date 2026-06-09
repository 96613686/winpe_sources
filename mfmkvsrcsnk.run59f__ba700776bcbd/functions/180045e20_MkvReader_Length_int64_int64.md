# MkvReader::Length(__int64 *,__int64 *)

- ea: `0x180045e20`
- end: `0x180046090`
- name: `?Length@MkvReader@@UEAAJPEA_J0@Z`
- size: `624`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180045e20`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045f08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045fbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045f08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045fbf`

## string_xrefs

- `0x180045e3e`: `MkvReader::Length`
- `0x180045ecd`: `MkvReader::Length`
- `0x180045f70`: `MkvReader::Length`
- `0x180046027`: `MkvReader::Length`

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
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v14 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180045e20  mov     [rsp+arg_0], rbx
0x180045e25  mov     [rsp+arg_10], rsi
0x180045e2a  push    rdi
0x180045e2b  sub     rsp, 30h
0x180045e2f  mov     rbx, r8
0x180045e32  mov     rsi, rdx
0x180045e35  mov     rdi, rcx
0x180045e38  mov     r8d, 18Bh; int
0x180045e3e  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x180045e45  lea     rcx, [rsp+38h+arg_8]; this
0x180045e4a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045e4f  nop
0x180045e50  test    rsi, rsi
0x180045e53  jnz     loc_180045EF3
0x180045e59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e60  test    rcx, rcx
0x180045e63  jnz     short loc_180045EAC
0x180045e65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045e6c  nop     dword ptr [rax+rax+00h]
0x180045e71  mov     rcx, rax
0x180045e74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e7b  test    rax, rax
0x180045e7e  jz      short loc_180045E9E
0x180045e80  mov     rax, [rax]
0x180045e83  mov     edx, 7F0h
0x180045e88  mov     rax, [rax+8]
0x180045e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e91  test    eax, eax
0x180045e93  jz      short loc_180045E9E
0x180045e95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e9c  jmp     short loc_180045EAC
0x180045e9e  lea     rcx, qword_1800DBF70; this
0x180045ea5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045eac  mov     ebx, 80004003h
0x180045eb1  cmp     byte ptr [rcx+8], 0
0x180045eb5  jz      short loc_180045EDC
0x180045eb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045ebc  cmp     [rax+7CCh], ebx
0x180045ec2  jz      short loc_180045EDC
0x180045ec4  mov     r9d, ebx; int
0x180045ec7  mov     r8d, 18Bh; int
0x180045ecd  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x180045ed4  mov     rcx, rax; this
0x180045ed7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045edc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045ee3  jb      loc_180046073
0x180045ee9  mov     edx, 17h
0x180045eee  jmp     loc_180046044
0x180045ef3  test    rbx, rbx
0x180045ef6  jnz     loc_180045F96
0x180045efc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f03  test    rcx, rcx
0x180045f06  jnz     short loc_180045F4F
0x180045f08  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045f0f  nop     dword ptr [rax+rax+00h]
0x180045f14  mov     rcx, rax
0x180045f17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f1e  test    rax, rax
0x180045f21  jz      short loc_180045F41
0x180045f23  mov     rax, [rax]
0x180045f26  mov     edx, 7F0h
0x180045f2b  mov     rax, [rax+8]
0x180045f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f34  test    eax, eax
0x180045f36  jz      short loc_180045F41
0x180045f38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f3f  jmp     short loc_180045F4F
0x180045f41  lea     rcx, qword_1800DBF70; this
0x180045f48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f4f  mov     ebx, 80004003h
0x180045f54  cmp     byte ptr [rcx+8], 0
0x180045f58  jz      short loc_180045F7F
0x180045f5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045f5f  cmp     [rax+7CCh], ebx
0x180045f65  jz      short loc_180045F7F
0x180045f67  mov     r9d, ebx; int
0x180045f6a  mov     r8d, 18Ch; int
0x180045f70  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x180045f77  mov     rcx, rax; this
0x180045f7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045f7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045f86  jb      loc_180046073
0x180045f8c  mov     edx, 18h
0x180045f91  jmp     loc_180046044
0x180045f96  mov     rax, [rdi+0C8h]
0x180045f9d  test    rax, rax
0x180045fa0  js      loc_180046064
0x180045fa6  cmp     [rdi+0D0h], rax
0x180045fad  jle     loc_180046064
0x180045fb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fba  test    rcx, rcx
0x180045fbd  jnz     short loc_180046006
0x180045fbf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045fc6  nop     dword ptr [rax+rax+00h]
0x180045fcb  mov     rcx, rax
0x180045fce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fd5  test    rax, rax
0x180045fd8  jz      short loc_180045FF8
0x180045fda  mov     rax, [rax]
0x180045fdd  mov     edx, 7F0h
0x180045fe2  mov     rax, [rax+8]
0x180045fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045feb  test    eax, eax
0x180045fed  jz      short loc_180045FF8
0x180045fef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ff6  jmp     short loc_180046006
0x180045ff8  lea     rcx, qword_1800DBF70; this
0x180045fff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046006  mov     ebx, 0C00D36BBh
0x18004600b  cmp     byte ptr [rcx+8], 0
0x18004600f  jz      short loc_180046036
0x180046011  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046016  cmp     [rax+7CCh], ebx
0x18004601c  jz      short loc_180046036
0x18004601e  mov     r9d, ebx; int
0x180046021  mov     r8d, 190h; int
0x180046027  lea     rdx, aMkvreaderLengt; "MkvReader::Length"
0x18004602e  mov     rcx, rax; this
0x180046031  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046036  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004603d  jb      short loc_180046073
0x18004603f  mov     edx, 19h
0x180046044  mov     [rsp+38h+var_18], ebx
0x180046048  mov     r9, rdi
0x18004604b  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180046052  mov     rcx, cs:WPP_GLOBAL_Control
0x180046059  mov     rcx, [rcx+10h]
0x18004605d  call    WPP_SF_qD
0x180046062  jmp     short loc_180046073
0x180046064  mov     [rsi], rax
0x180046067  mov     rax, [rdi+0D0h]
0x18004606e  mov     [rbx], rax
0x180046071  xor     ebx, ebx
0x180046073  lea     rcx, [rsp+38h+arg_8]; this
0x180046078  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004607d  mov     eax, ebx
0x18004607f  mov     rbx, [rsp+38h+arg_0]
0x180046084  mov     rsi, [rsp+38h+arg_10]
0x180046089  add     rsp, 30h
0x18004608d  pop     rdi
0x18004608e  retn
```
