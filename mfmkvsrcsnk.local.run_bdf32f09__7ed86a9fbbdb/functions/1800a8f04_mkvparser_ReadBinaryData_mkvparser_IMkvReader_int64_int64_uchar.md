# mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)

- ea: `0x1800a8f04`
- end: `0x1800a9219`
- name: `?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z`
- size: `789`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18009ecd4`
- `0x1800a1b98`
- `0x1800a67dc`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800a8f04`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8f57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9087`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9179`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8f57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9087`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9179`

## string_xrefs

- `0x1800a8f1d`: `mkvparser::ReadBinaryData`

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
            v26 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v19 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
LABEL_51:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a8f04  mov     [rsp+arg_8], rbx
0x1800a8f09  mov     [rsp+arg_10], rbp
0x1800a8f0e  push    rsi
0x1800a8f0f  push    rdi
0x1800a8f10  push    r13
0x1800a8f12  push    r14
0x1800a8f14  push    r15
0x1800a8f16  sub     rsp, 30h
0x1800a8f1a  mov     rdi, r8
0x1800a8f1d  lea     r13, aMkvparserReadb; "mkvparser::ReadBinaryData"
0x1800a8f24  mov     rsi, rdx
0x1800a8f27  mov     r15, rcx
0x1800a8f2a  mov     ebp, 1F7h
0x1800a8f2f  lea     rcx, [rsp+58h+arg_0]; this
0x1800a8f34  mov     r8d, ebp; int
0x1800a8f37  mov     rdx, r13; char *
0x1800a8f3a  mov     r14, r9
0x1800a8f3d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8f42  test    r15, r15
0x1800a8f45  jnz     loc_1800A8FD8
0x1800a8f4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f52  test    rcx, rcx
0x1800a8f55  jnz     short loc_1800A8F98
0x1800a8f57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8f5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f64  mov     rcx, rax
0x1800a8f67  test    rax, rax
0x1800a8f6a  jz      short loc_1800A8F8A
0x1800a8f6c  mov     rax, [rax]
0x1800a8f6f  mov     edx, 7F0h
0x1800a8f74  mov     rax, [rax+8]
0x1800a8f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8f7d  test    eax, eax
0x1800a8f7f  jz      short loc_1800A8F8A
0x1800a8f81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f88  jmp     short loc_1800A8F98
0x1800a8f8a  lea     rcx, qword_1800D6F70; this
0x1800a8f91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f98  cmp     byte ptr [rcx+8], 0
0x1800a8f9c  mov     ebx, 80070057h
0x1800a8fa1  jz      short loc_1800A8FC1
0x1800a8fa3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8fa8  cmp     [rax+7CCh], ebx
0x1800a8fae  jz      short loc_1800A8FC1
0x1800a8fb0  mov     r9d, ebx; int
0x1800a8fb3  mov     r8d, ebp; int
0x1800a8fb6  mov     rdx, r13; char *
0x1800a8fb9  mov     rcx, rax; this
0x1800a8fbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8fc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8fc8  jb      loc_1800A91F6
0x1800a8fce  mov     edx, 28h ; '('
0x1800a8fd3  jmp     loc_1800A9106
0x1800a8fd8  test    rsi, rsi
0x1800a8fdb  jns     loc_1800A9071
0x1800a8fe1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8fe8  test    rcx, rcx
0x1800a8feb  jnz     short loc_1800A902E
0x1800a8fed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8ff3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8ffa  mov     rcx, rax
0x1800a8ffd  test    rax, rax
0x1800a9000  jz      short loc_1800A9020
0x1800a9002  mov     rax, [rax]
0x1800a9005  mov     edx, 7F0h
0x1800a900a  mov     rax, [rax+8]
0x1800a900e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9013  test    eax, eax
0x1800a9015  jz      short loc_1800A9020
0x1800a9017  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a901e  jmp     short loc_1800A902E
0x1800a9020  lea     rcx, qword_1800D6F70; this
0x1800a9027  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a902e  cmp     byte ptr [rcx+8], 0
0x1800a9032  mov     ebx, 80070057h
0x1800a9037  jz      short loc_1800A905A
0x1800a9039  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a903e  cmp     [rax+7CCh], ebx
0x1800a9044  jz      short loc_1800A905A
0x1800a9046  mov     r9d, ebx; int
0x1800a9049  mov     r8d, 1FBh; int
0x1800a904f  mov     rdx, r13; char *
0x1800a9052  mov     rcx, rax; this
0x1800a9055  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a905a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9061  jb      loc_1800A91F6
0x1800a9067  mov     edx, 29h ; ')'
0x1800a906c  jmp     loc_1800A9106
0x1800a9071  cmp     rdi, 1
0x1800a9075  jge     loc_1800A9129
0x1800a907b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9082  test    rcx, rcx
0x1800a9085  jnz     short loc_1800A90C8
0x1800a9087  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a908d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9094  mov     rcx, rax
0x1800a9097  test    rax, rax
0x1800a909a  jz      short loc_1800A90BA
0x1800a909c  mov     rax, [rax]
0x1800a909f  mov     edx, 7F0h
0x1800a90a4  mov     rax, [rax+8]
0x1800a90a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a90ad  test    eax, eax
0x1800a90af  jz      short loc_1800A90BA
0x1800a90b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a90b8  jmp     short loc_1800A90C8
0x1800a90ba  lea     rcx, qword_1800D6F70; this
0x1800a90c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a90c8  cmp     byte ptr [rcx+8], 0
0x1800a90cc  mov     ebx, 0C00D36BEh
0x1800a90d1  jz      short loc_1800A90F4
0x1800a90d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a90d8  cmp     [rax+7CCh], ebx
0x1800a90de  jz      short loc_1800A90F4
0x1800a90e0  mov     r9d, ebx; int
0x1800a90e3  mov     r8d, 200h; int
0x1800a90e9  mov     rdx, r13; char *
0x1800a90ec  mov     rcx, rax; this
0x1800a90ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a90f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a90fb  jb      loc_1800A91F6
0x1800a9101  mov     edx, 2Ah ; '*'
0x1800a9106  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a910d  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a9114  xor     r9d, r9d
0x1800a9117  mov     [rsp+58h+var_38], ebx
0x1800a911b  mov     rcx, [rcx+10h]
0x1800a911f  call    WPP_SF_qD
0x1800a9124  jmp     loc_1800A91F6
0x1800a9129  test    rdi, rdi
0x1800a912c  jle     loc_1800A91F4
0x1800a9132  mov     ebp, 7FFFFFFFh
0x1800a9137  cmp     rdi, 7FFFFFFFh
0x1800a913e  jg      short loc_1800A9142
0x1800a9140  mov     ebp, edi
0x1800a9142  mov     rax, [r15]
0x1800a9145  mov     r9, r14
0x1800a9148  mov     r8d, ebp
0x1800a914b  mov     rdx, rsi
0x1800a914e  mov     rcx, r15
0x1800a9151  mov     rax, [rax]
0x1800a9154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9159  mov     ebx, eax
0x1800a915b  test    eax, eax
0x1800a915d  js      short loc_1800A916D
0x1800a915f  movsxd  rax, ebp
0x1800a9162  add     r14, rax
0x1800a9165  add     rsi, rax
0x1800a9168  sub     rdi, rax
0x1800a916b  jmp     short loc_1800A9129
0x1800a916d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9174  test    rcx, rcx
0x1800a9177  jnz     short loc_1800A91BA
0x1800a9179  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a917f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9186  mov     rcx, rax
0x1800a9189  test    rax, rax
0x1800a918c  jz      short loc_1800A91AC
0x1800a918e  mov     rax, [rax]
0x1800a9191  mov     edx, 7F0h
0x1800a9196  mov     rax, [rax+8]
0x1800a919a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a919f  test    eax, eax
0x1800a91a1  jz      short loc_1800A91AC
0x1800a91a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a91aa  jmp     short loc_1800A91BA
0x1800a91ac  lea     rcx, qword_1800D6F70; this
0x1800a91b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a91ba  cmp     byte ptr [rcx+8], 0
0x1800a91be  jz      short loc_1800A91E1
0x1800a91c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a91c5  cmp     [rax+7CCh], ebx
0x1800a91cb  jz      short loc_1800A91E1
0x1800a91cd  mov     r9d, ebx; int
0x1800a91d0  mov     r8d, 214h; int
0x1800a91d6  mov     rdx, r13; char *
0x1800a91d9  mov     rcx, rax; this
0x1800a91dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a91e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a91e8  jb      short loc_1800A91F6
0x1800a91ea  mov     edx, 2Bh ; '+'
0x1800a91ef  jmp     loc_1800A9106
0x1800a91f4  xor     ebx, ebx
0x1800a91f6  lea     rcx, [rsp+58h+arg_0]; this
0x1800a91fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a9200  mov     rbp, [rsp+58h+arg_10]
0x1800a9205  mov     eax, ebx
0x1800a9207  mov     rbx, [rsp+58h+arg_8]
0x1800a920c  add     rsp, 30h
0x1800a9210  pop     r15
0x1800a9212  pop     r14
0x1800a9214  pop     r13
0x1800a9216  pop     rdi
0x1800a9217  pop     rsi
0x1800a9218  retn
```
