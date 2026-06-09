# mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)

- ea: `0x1800adb74`
- end: `0x1800adea2`
- name: `?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z`
- size: `814`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a3480`
- `0x1800a649c`
- `0x1800ab330`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800adb74`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adbc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adc63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800add03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800addfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adbc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adc63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800add03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800addfb`

## string_xrefs

- `0x1800adb8d`: `mkvparser::ReadBinaryData`

## pseudocode

```c
__int64 __fastcall mkvparser::ReadBinaryData(mkvparser *this, struct mkvparser::IMkvReader *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int v13; // ebx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  int v22; // ebp
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v30; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "mkvparser::ReadBinaryData", 503);
  if ( this )
  {
    if ( (__int64)a2 >= 0 )
    {
      if ( a3 >= 1 )
      {
        while ( 1 )
        {
          if ( a3 <= 0 )
          {
            v13 = 0;
            goto LABEL_51;
          }
          v22 = 0x7FFFFFFF;
          if ( a3 <= 0x7FFFFFFF )
            v22 = a3;
          v13 = (**(__int64 (__fastcall ***)(mkvparser *, struct mkvparser::IMkvReader *, _QWORD, __int64))this)(
                  this,
                  a2,
                  (unsigned int)v22,
                  a4);
          if ( v13 < 0 )
            break;
          a4 += v22;
          a2 = (struct mkvparser::IMkvReader *)((char *)a2 + v22);
          a3 -= v22;
        }
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::ReadBinaryData", 532, v13);
        }
        if ( g_wppLevels )
        {
          v15 = 43;
          goto LABEL_34;
        }
      }
      else
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
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
        v13 = -1072875842;
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v21, "mkvparser::ReadBinaryData", 512, -1072875842);
        }
        if ( g_wppLevels )
        {
          v15 = 42;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v13 = -2147024809;
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v18, "mkvparser::ReadBinaryData", 507, -2147024809);
      }
      if ( g_wppLevels )
      {
        v15 = 41;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "mkvparser::ReadBinaryData", 503, -2147024809);
    }
    if ( g_wppLevels )
    {
      v15 = 40;
LABEL_34:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
LABEL_51:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800adb74  mov     [rsp+arg_8], rbx
0x1800adb79  mov     [rsp+arg_10], rbp
0x1800adb7e  push    rsi
0x1800adb7f  push    rdi
0x1800adb80  push    r13
0x1800adb82  push    r14
0x1800adb84  push    r15
0x1800adb86  sub     rsp, 30h
0x1800adb8a  mov     rdi, r8
0x1800adb8d  lea     r13, aMkvparserReadb; "mkvparser::ReadBinaryData"
0x1800adb94  mov     rsi, rdx
0x1800adb97  mov     r15, rcx
0x1800adb9a  mov     ebp, 1F7h
0x1800adb9f  lea     rcx, [rsp+58h+arg_0]; this
0x1800adba4  mov     r8d, ebp; int
0x1800adba7  mov     rdx, r13; char *
0x1800adbaa  mov     r14, r9
0x1800adbad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800adbb2  test    r15, r15
0x1800adbb5  jnz     loc_1800ADC4E
0x1800adbbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adbc2  test    rcx, rcx
0x1800adbc5  jnz     short loc_1800ADC0E
0x1800adbc7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adbce  nop     dword ptr [rax+rax+00h]
0x1800adbd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adbda  mov     rcx, rax
0x1800adbdd  test    rax, rax
0x1800adbe0  jz      short loc_1800ADC00
0x1800adbe2  mov     rax, [rax]
0x1800adbe5  mov     edx, 7F0h
0x1800adbea  mov     rax, [rax+8]
0x1800adbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adbf3  test    eax, eax
0x1800adbf5  jz      short loc_1800ADC00
0x1800adbf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adbfe  jmp     short loc_1800ADC0E
0x1800adc00  lea     rcx, qword_1800DBF70; this
0x1800adc07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc0e  cmp     byte ptr [rcx+8], 0
0x1800adc12  mov     ebx, 80070057h
0x1800adc17  jz      short loc_1800ADC37
0x1800adc19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adc1e  cmp     [rax+7CCh], ebx
0x1800adc24  jz      short loc_1800ADC37
0x1800adc26  mov     r9d, ebx; int
0x1800adc29  mov     r8d, ebp; int
0x1800adc2c  mov     rdx, r13; char *
0x1800adc2f  mov     rcx, rax; this
0x1800adc32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adc37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adc3e  jb      loc_1800ADE7E
0x1800adc44  mov     edx, 28h ; '('
0x1800adc49  jmp     loc_1800ADD88
0x1800adc4e  test    rsi, rsi
0x1800adc51  jns     loc_1800ADCED
0x1800adc57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc5e  test    rcx, rcx
0x1800adc61  jnz     short loc_1800ADCAA
0x1800adc63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adc6a  nop     dword ptr [rax+rax+00h]
0x1800adc6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc76  mov     rcx, rax
0x1800adc79  test    rax, rax
0x1800adc7c  jz      short loc_1800ADC9C
0x1800adc7e  mov     rax, [rax]
0x1800adc81  mov     edx, 7F0h
0x1800adc86  mov     rax, [rax+8]
0x1800adc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc8f  test    eax, eax
0x1800adc91  jz      short loc_1800ADC9C
0x1800adc93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adc9a  jmp     short loc_1800ADCAA
0x1800adc9c  lea     rcx, qword_1800DBF70; this
0x1800adca3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adcaa  cmp     byte ptr [rcx+8], 0
0x1800adcae  mov     ebx, 80070057h
0x1800adcb3  jz      short loc_1800ADCD6
0x1800adcb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adcba  cmp     [rax+7CCh], ebx
0x1800adcc0  jz      short loc_1800ADCD6
0x1800adcc2  mov     r9d, ebx; int
0x1800adcc5  mov     r8d, 1FBh; int
0x1800adccb  mov     rdx, r13; char *
0x1800adcce  mov     rcx, rax; this
0x1800adcd1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adcd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adcdd  jb      loc_1800ADE7E
0x1800adce3  mov     edx, 29h ; ')'
0x1800adce8  jmp     loc_1800ADD88
0x1800adced  cmp     rdi, 1
0x1800adcf1  jge     loc_1800ADDAB
0x1800adcf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adcfe  test    rcx, rcx
0x1800add01  jnz     short loc_1800ADD4A
0x1800add03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800add0a  nop     dword ptr [rax+rax+00h]
0x1800add0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800add16  mov     rcx, rax
0x1800add19  test    rax, rax
0x1800add1c  jz      short loc_1800ADD3C
0x1800add1e  mov     rax, [rax]
0x1800add21  mov     edx, 7F0h
0x1800add26  mov     rax, [rax+8]
0x1800add2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add2f  test    eax, eax
0x1800add31  jz      short loc_1800ADD3C
0x1800add33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800add3a  jmp     short loc_1800ADD4A
0x1800add3c  lea     rcx, qword_1800DBF70; this
0x1800add43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800add4a  cmp     byte ptr [rcx+8], 0
0x1800add4e  mov     ebx, 0C00D36BEh
0x1800add53  jz      short loc_1800ADD76
0x1800add55  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800add5a  cmp     [rax+7CCh], ebx
0x1800add60  jz      short loc_1800ADD76
0x1800add62  mov     r9d, ebx; int
0x1800add65  mov     r8d, 200h; int
0x1800add6b  mov     rdx, r13; char *
0x1800add6e  mov     rcx, rax; this
0x1800add71  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800add76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800add7d  jb      loc_1800ADE7E
0x1800add83  mov     edx, 2Ah ; '*'
0x1800add88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800add8f  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800add96  xor     r9d, r9d
0x1800add99  mov     [rsp+58h+var_38], ebx
0x1800add9d  mov     rcx, [rcx+10h]
0x1800adda1  call    WPP_SF_qD
0x1800adda6  jmp     loc_1800ADE7E
0x1800addab  test    rdi, rdi
0x1800addae  jle     loc_1800ADE7C
0x1800addb4  mov     ebp, 7FFFFFFFh
0x1800addb9  cmp     rdi, 7FFFFFFFh
0x1800addc0  jg      short loc_1800ADDC4
0x1800addc2  mov     ebp, edi
0x1800addc4  mov     rax, [r15]
0x1800addc7  mov     r9, r14
0x1800addca  mov     r8d, ebp
0x1800addcd  mov     rdx, rsi
0x1800addd0  mov     rcx, r15
0x1800addd3  mov     rax, [rax]
0x1800addd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adddb  mov     ebx, eax
0x1800adddd  test    eax, eax
0x1800adddf  js      short loc_1800ADDEF
0x1800adde1  movsxd  rax, ebp
0x1800adde4  add     r14, rax
0x1800adde7  add     rsi, rax
0x1800addea  sub     rdi, rax
0x1800added  jmp     short loc_1800ADDAB
0x1800addef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800addf6  test    rcx, rcx
0x1800addf9  jnz     short loc_1800ADE42
0x1800addfb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ade02  nop     dword ptr [rax+rax+00h]
0x1800ade07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ade0e  mov     rcx, rax
0x1800ade11  test    rax, rax
0x1800ade14  jz      short loc_1800ADE34
0x1800ade16  mov     rax, [rax]
0x1800ade19  mov     edx, 7F0h
0x1800ade1e  mov     rax, [rax+8]
0x1800ade22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade27  test    eax, eax
0x1800ade29  jz      short loc_1800ADE34
0x1800ade2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ade32  jmp     short loc_1800ADE42
0x1800ade34  lea     rcx, qword_1800DBF70; this
0x1800ade3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ade42  cmp     byte ptr [rcx+8], 0
0x1800ade46  jz      short loc_1800ADE69
0x1800ade48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ade4d  cmp     [rax+7CCh], ebx
0x1800ade53  jz      short loc_1800ADE69
0x1800ade55  mov     r9d, ebx; int
0x1800ade58  mov     r8d, 214h; int
0x1800ade5e  mov     rdx, r13; char *
0x1800ade61  mov     rcx, rax; this
0x1800ade64  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ade69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ade70  jb      short loc_1800ADE7E
0x1800ade72  mov     edx, 2Bh ; '+'
0x1800ade77  jmp     loc_1800ADD88
0x1800ade7c  xor     ebx, ebx
0x1800ade7e  lea     rcx, [rsp+58h+arg_0]; this
0x1800ade83  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ade88  mov     rbp, [rsp+58h+arg_10]
0x1800ade8d  mov     eax, ebx
0x1800ade8f  mov     rbx, [rsp+58h+arg_8]
0x1800ade94  add     rsp, 30h
0x1800ade98  pop     r15
0x1800ade9a  pop     r14
0x1800ade9c  pop     r13
0x1800ade9e  pop     rdi
0x1800ade9f  pop     rsi
0x1800adea0  retn
```
