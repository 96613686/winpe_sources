# mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)

- ea: `0x1800a5fec`
- end: `0x1800a6493`
- name: `?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z`
- size: `1191`
- prototype: `__int64 __usercall@<rax>(mkvparser *__hidden this@<rcx>, struct mkvparser::IMkvReader *@<rdx>, __int64 *@<r8>, __int64@<r9>, __int64 *, __int64 *)`
- caller_count: `20`
- callee_count: `9`
- tags: ``

## callers

- `0x180095f10`
- `0x18009656c`
- `0x180099400`
- `0x18009a83c`
- `0x18009b898`
- `0x18009bd54`
- `0x18009d13c`
- `0x18009d46c`
- `0x18009e0f8`
- `0x18009e964`
- `0x18009f18c`
- `0x1800a07a4`
- `0x1800a0d58`
- `0x1800a3480`
- `0x1800a39a8`
- `0x1800a3d74`
- `0x1800a4adc`
- `0x1800a649c`
- `0x1800a7120`
- `0x1800ab330`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800a5fec`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6044`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6116`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a61c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6325`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a63d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6044`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6116`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a61c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6325`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a63d0`

## pseudocode

```c
__int64 __fastcall mkvparser::ParseElementHeader(
        __int64 (__fastcall ***this)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::IMkvReader **a2,
        struct mkvparser::IMkvReader *a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  int ID; // ebx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40[5]; // [rsp+30h] [rbp-28h] BYREF
  char v41; // [rsp+70h] [rbp+18h] BYREF

  if ( (__int64)a3 < 0 || (__int64)*a2 < (__int64)a3 )
  {
    LODWORD(v40[0]) = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "mkvparser::ParseElementHeader", 586);
    ID = mkvparser::ReadID(this, *a2, a4, v40);
    if ( ID >= 0 )
    {
      *a2 = (struct mkvparser::IMkvReader *)((char *)*a2 + SLODWORD(v40[0]));
      if ( (__int64)a3 < 0 || (__int64)*a2 < (__int64)a3 )
      {
        ID = mkvparser::ReadUInt(this, *a2, a5, v40);
        if ( ID >= 0 )
        {
          v32 = (__int64)*a2 + SLODWORD(v40[0]);
          if ( (unsigned __int64)v32 <= 0x7FFFFFFFFFFFFFFFLL )
          {
            *a2 = (struct mkvparser::IMkvReader *)v32;
            if ( (__int64)a3 < 0 || v32 <= (__int64)a3 )
            {
              ID = 0;
              goto LABEL_72;
            }
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
              CallStackTracing::s_wpInstance = v37;
              if ( v37
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
              {
                v36 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v36 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            ID = -1072875842;
            if ( *((_BYTE *)v36 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::ParseElementHeader", 611, -1072875842);
            }
            if ( g_wppLevels )
            {
              v16 = 52;
              goto LABEL_70;
            }
          }
          else
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            ID = -1072875842;
            if ( *((_BYTE *)v33 + 8) )
            {
              v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)v35 + 499) != -1072875842 )
                CallStackContext::TraceFailure(v35, "mkvparser::ParseElementHeader", 602, -1072875842);
            }
            if ( g_wppLevels )
            {
              v16 = 51;
              goto LABEL_70;
            }
          }
        }
        else
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != ID )
              CallStackContext::TraceFailure(v31, "mkvparser::ParseElementHeader", 595, ID);
          }
          if ( g_wppLevels )
          {
            v16 = 50;
            goto LABEL_70;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        ID = -1072875842;
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v25, "mkvparser::ParseElementHeader", 592, -1072875842);
        }
        if ( g_wppLevels )
        {
          v16 = 49;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != ID )
          CallStackContext::TraceFailure(v22, "mkvparser::ParseElementHeader", 586, ID);
      }
      if ( g_wppLevels )
      {
        v16 = 48;
        goto LABEL_70;
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "mkvparser::ParseElementHeader", 581);
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    ID = -1072875842;
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v15 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v15, "mkvparser::ParseElementHeader", 581, -1072875842);
    }
    if ( g_wppLevels )
    {
      v16 = 47;
LABEL_70:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, ID);
    }
  }
LABEL_72:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)ID;
}

```

## disassembly

```asm
0x1800a5fec  mov     [rsp+arg_0], rbx
0x1800a5ff1  mov     [rsp+arg_8], rbp
0x1800a5ff6  push    rsi
0x1800a5ff7  push    rdi
0x1800a5ff8  push    r14
0x1800a5ffa  sub     rsp, 40h
0x1800a5ffe  mov     rbx, r9
0x1800a6001  mov     rsi, r8
0x1800a6004  mov     rdi, rdx
0x1800a6007  mov     r14, rcx
0x1800a600a  test    r8, r8
0x1800a600d  js      loc_1800A60CB
0x1800a6013  cmp     [rdx], r8
0x1800a6016  jl      loc_1800A60CB
0x1800a601c  mov     edi, 245h
0x1800a6021  lea     rbp, aMkvparserParse; "mkvparser::ParseElementHeader"
0x1800a6028  mov     r8d, edi; int
0x1800a602b  lea     rcx, [rsp+58h+arg_10]; this
0x1800a6030  mov     rdx, rbp; char *
0x1800a6033  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a6038  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a603f  test    rcx, rcx
0x1800a6042  jnz     short loc_1800A608B
0x1800a6044  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a604b  nop     dword ptr [rax+rax+00h]
0x1800a6050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6057  mov     rcx, rax
0x1800a605a  test    rax, rax
0x1800a605d  jz      short loc_1800A607D
0x1800a605f  mov     rax, [rax]
0x1800a6062  mov     edx, 7F0h
0x1800a6067  mov     rax, [rax+8]
0x1800a606b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6070  test    eax, eax
0x1800a6072  jz      short loc_1800A607D
0x1800a6074  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a607b  jmp     short loc_1800A608B
0x1800a607d  lea     rcx, qword_1800DBF70; this
0x1800a6084  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a608b  cmp     byte ptr [rcx+8], 0
0x1800a608f  mov     ebx, 0C00D36BEh
0x1800a6094  jz      short loc_1800A60B4
0x1800a6096  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a609b  cmp     [rax+7CCh], ebx
0x1800a60a1  jz      short loc_1800A60B4
0x1800a60a3  mov     r9d, ebx; int
0x1800a60a6  mov     r8d, edi; int
0x1800a60a9  mov     rdx, rbp; char *
0x1800a60ac  mov     rcx, rax; this
0x1800a60af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a60b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a60bb  jb      loc_1800A6473
0x1800a60c1  mov     edx, 2Fh ; '/'
0x1800a60c6  jmp     loc_1800A6451
0x1800a60cb  lea     rbp, aMkvparserParse; "mkvparser::ParseElementHeader"
0x1800a60d2  mov     dword ptr [rsp+58h+var_28], 0
0x1800a60da  mov     rdx, rbp; char *
0x1800a60dd  lea     rcx, [rsp+58h+arg_10]; this
0x1800a60e2  mov     r8d, 24Ah; int
0x1800a60e8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a60ed  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x1800a60f0  lea     r9, [rsp+58h+var_28]; __int64 *
0x1800a60f5  mov     r8, rbx; __int64
0x1800a60f8  mov     rcx, r14; this
0x1800a60fb  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x1800a6100  mov     ebx, eax
0x1800a6102  test    eax, eax
0x1800a6104  jns     loc_1800A619B
0x1800a610a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6111  test    rcx, rcx
0x1800a6114  jnz     short loc_1800A615D
0x1800a6116  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a611d  nop     dword ptr [rax+rax+00h]
0x1800a6122  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6129  mov     rcx, rax
0x1800a612c  test    rax, rax
0x1800a612f  jz      short loc_1800A614F
0x1800a6131  mov     rax, [rax]
0x1800a6134  mov     edx, 7F0h
0x1800a6139  mov     rax, [rax+8]
0x1800a613d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6142  test    eax, eax
0x1800a6144  jz      short loc_1800A614F
0x1800a6146  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a614d  jmp     short loc_1800A615D
0x1800a614f  lea     rcx, qword_1800DBF70; this
0x1800a6156  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a615d  cmp     byte ptr [rcx+8], 0
0x1800a6161  jz      short loc_1800A6184
0x1800a6163  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6168  cmp     [rax+7CCh], ebx
0x1800a616e  jz      short loc_1800A6184
0x1800a6170  mov     r9d, ebx; int
0x1800a6173  mov     r8d, 24Ah; int
0x1800a6179  mov     rdx, rbp; char *
0x1800a617c  mov     rcx, rax; this
0x1800a617f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6184  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a618b  jb      loc_1800A6473
0x1800a6191  mov     edx, 30h ; '0'
0x1800a6196  jmp     loc_1800A6451
0x1800a619b  movsxd  rax, dword ptr [rsp+58h+var_28]
0x1800a61a0  add     [rdi], rax
0x1800a61a3  test    rsi, rsi
0x1800a61a6  js      loc_1800A624B
0x1800a61ac  cmp     [rdi], rsi
0x1800a61af  jl      loc_1800A624B
0x1800a61b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a61bc  test    rcx, rcx
0x1800a61bf  jnz     short loc_1800A6208
0x1800a61c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a61c8  nop     dword ptr [rax+rax+00h]
0x1800a61cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a61d4  mov     rcx, rax
0x1800a61d7  test    rax, rax
0x1800a61da  jz      short loc_1800A61FA
0x1800a61dc  mov     rax, [rax]
0x1800a61df  mov     edx, 7F0h
0x1800a61e4  mov     rax, [rax+8]
0x1800a61e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a61ed  test    eax, eax
0x1800a61ef  jz      short loc_1800A61FA
0x1800a61f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a61f8  jmp     short loc_1800A6208
0x1800a61fa  lea     rcx, qword_1800DBF70; this
0x1800a6201  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6208  cmp     byte ptr [rcx+8], 0
0x1800a620c  mov     ebx, 0C00D36BEh
0x1800a6211  jz      short loc_1800A6234
0x1800a6213  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6218  cmp     [rax+7CCh], ebx
0x1800a621e  jz      short loc_1800A6234
0x1800a6220  mov     r9d, ebx; int
0x1800a6223  mov     r8d, 250h; int
0x1800a6229  mov     rdx, rbp; char *
0x1800a622c  mov     rcx, rax; this
0x1800a622f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6234  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a623b  jb      loc_1800A6473
0x1800a6241  mov     edx, 31h ; '1'
0x1800a6246  jmp     loc_1800A6451
0x1800a624b  mov     r8, [rsp+58h+arg_20]; __int64
0x1800a6253  lea     r9, [rsp+58h+var_28]; __int64 *
0x1800a6258  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x1800a625b  mov     rcx, r14; this
0x1800a625e  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x1800a6263  mov     ebx, eax
0x1800a6265  test    eax, eax
0x1800a6267  jns     loc_1800A62FE
0x1800a626d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6274  test    rcx, rcx
0x1800a6277  jnz     short loc_1800A62C0
0x1800a6279  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6280  nop     dword ptr [rax+rax+00h]
0x1800a6285  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a628c  mov     rcx, rax
0x1800a628f  test    rax, rax
0x1800a6292  jz      short loc_1800A62B2
0x1800a6294  mov     rax, [rax]
0x1800a6297  mov     edx, 7F0h
0x1800a629c  mov     rax, [rax+8]
0x1800a62a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62a5  test    eax, eax
0x1800a62a7  jz      short loc_1800A62B2
0x1800a62a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a62b0  jmp     short loc_1800A62C0
0x1800a62b2  lea     rcx, qword_1800DBF70; this
0x1800a62b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a62c0  cmp     byte ptr [rcx+8], 0
0x1800a62c4  jz      short loc_1800A62E7
0x1800a62c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a62cb  cmp     [rax+7CCh], ebx
0x1800a62d1  jz      short loc_1800A62E7
0x1800a62d3  mov     r9d, ebx; int
0x1800a62d6  mov     r8d, 253h; int
0x1800a62dc  mov     rdx, rbp; char *
0x1800a62df  mov     rcx, rax; this
0x1800a62e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a62e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a62ee  jb      loc_1800A6473
0x1800a62f4  mov     edx, 32h ; '2'
0x1800a62f9  jmp     loc_1800A6451
0x1800a62fe  movsxd  rdx, dword ptr [rsp+58h+var_28]
0x1800a6303  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800a630d  add     rdx, [rdi]
0x1800a6310  cmp     rdx, rax
0x1800a6313  jbe     loc_1800A63AF
0x1800a6319  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6320  test    rcx, rcx
0x1800a6323  jnz     short loc_1800A636C
0x1800a6325  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a632c  nop     dword ptr [rax+rax+00h]
0x1800a6331  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6338  mov     rcx, rax
0x1800a633b  test    rax, rax
0x1800a633e  jz      short loc_1800A635E
0x1800a6340  mov     rax, [rax]
0x1800a6343  mov     edx, 7F0h
0x1800a6348  mov     rax, [rax+8]
0x1800a634c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6351  test    eax, eax
0x1800a6353  jz      short loc_1800A635E
0x1800a6355  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a635c  jmp     short loc_1800A636C
0x1800a635e  lea     rcx, qword_1800DBF70; this
0x1800a6365  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a636c  cmp     byte ptr [rcx+8], 0
0x1800a6370  mov     ebx, 0C00D36BEh
0x1800a6375  jz      short loc_1800A6398
0x1800a6377  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a637c  cmp     [rax+7CCh], ebx
0x1800a6382  jz      short loc_1800A6398
0x1800a6384  mov     r9d, ebx; int
0x1800a6387  mov     r8d, 25Ah; int
0x1800a638d  mov     rdx, rbp; char *
0x1800a6390  mov     rcx, rax; this
0x1800a6393  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6398  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a639f  jb      loc_1800A6473
0x1800a63a5  mov     edx, 33h ; '3'
0x1800a63aa  jmp     loc_1800A6451
0x1800a63af  mov     [rdi], rdx
0x1800a63b2  test    rsi, rsi
0x1800a63b5  js      loc_1800A6471
0x1800a63bb  cmp     rdx, rsi
0x1800a63be  jle     loc_1800A6471
0x1800a63c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a63cb  test    rcx, rcx
0x1800a63ce  jnz     short loc_1800A6417
0x1800a63d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a63d7  nop     dword ptr [rax+rax+00h]
0x1800a63dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a63e3  mov     rcx, rax
0x1800a63e6  test    rax, rax
0x1800a63e9  jz      short loc_1800A6409
0x1800a63eb  mov     rax, [rax]
0x1800a63ee  mov     edx, 7F0h
0x1800a63f3  mov     rax, [rax+8]
0x1800a63f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a63fc  test    eax, eax
0x1800a63fe  jz      short loc_1800A6409
0x1800a6400  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6407  jmp     short loc_1800A6417
0x1800a6409  lea     rcx, qword_1800DBF70; this
0x1800a6410  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6417  cmp     byte ptr [rcx+8], 0
0x1800a641b  mov     ebx, 0C00D36BEh
0x1800a6420  jz      short loc_1800A6443
0x1800a6422  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6427  cmp     [rax+7CCh], ebx
0x1800a642d  jz      short loc_1800A6443
0x1800a642f  mov     r9d, ebx; int
0x1800a6432  mov     r8d, 263h; int
0x1800a6438  mov     rdx, rbp; char *
0x1800a643b  mov     rcx, rax; this
0x1800a643e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6443  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a644a  jb      short loc_1800A6473
0x1800a644c  mov     edx, 34h ; '4'
0x1800a6451  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6458  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a645f  xor     r9d, r9d
0x1800a6462  mov     [rsp+58h+var_38], ebx
0x1800a6466  mov     rcx, [rcx+10h]
0x1800a646a  call    WPP_SF_qD
0x1800a646f  jmp     short loc_1800A6473
0x1800a6471  xor     ebx, ebx
0x1800a6473  lea     rcx, [rsp+58h+arg_10]; this
0x1800a6478  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a647d  mov     rbp, [rsp+58h+arg_8]
0x1800a6482  mov     eax, ebx
0x1800a6484  mov     rbx, [rsp+58h+arg_0]
0x1800a6489  add     rsp, 40h
0x1800a648d  pop     r14
0x1800a648f  pop     rdi
0x1800a6490  pop     rsi
0x1800a6491  retn
```
