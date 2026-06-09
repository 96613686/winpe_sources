# CBitstreamReader::PopN(int,ulong *)

- ea: `0x180082b6c`
- end: `0x180082ffb`
- name: `?PopN@CBitstreamReader@@QEAAJHPEAK@Z`
- size: `1167`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, int, unsigned int *)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x18007afdc`
- `0x18007b1a4`
- `0x18007b488`
- `0x18007bb1c`
- `0x18007c1c4`
- `0x18007e5e8`
- `0x18007fa3c`
- `0x180081210`
- `0x1800825ec`
- `0x1800828ec`
- `0x180083004`
- `0x180083058`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082bbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082c5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082d2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082f5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082bbb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082c5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082d2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082f5a`

## string_xrefs

- `0x180082b85`: `CBitstreamReader::PopN`

## pseudocode

```c
__int64 __fastcall CBitstreamReader::PopN(CBitstreamReader *this, int a2, unsigned int *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  unsigned int v11; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  unsigned int v17; // r10d
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // edx
  unsigned int v28; // eax
  char v29; // dl
  int v30; // r15d
  _BYTE *v31; // r11
  int i; // ebp
  unsigned int v33; // ecx
  char v34; // r8
  bool v35; // zf
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  char v41; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "CBitstreamReader::PopN", 208);
  if ( !a3 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CBitstreamReader::PopN", 208, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_84;
    v13 = 18;
    goto LABEL_23;
  }
  *a3 = 0;
  if ( a2 < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147024809;
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
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v16, "CBitstreamReader::PopN", 213, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_84;
    v13 = 19;
    goto LABEL_23;
  }
  v17 = *((_DWORD *)this + 3);
  v18 = *((unsigned int *)this + 2);
  v19 = *((unsigned int *)this + 4);
  if ( a2 > 8 * (v17 - (unsigned int)v18) - (unsigned int)v19 )
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v19, v18);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v22, "CBitstreamReader::PopN", 217, -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_84;
    v13 = 20;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids, this, v11);
    goto LABEL_84;
  }
  v11 = (unsigned int)a2 >> 31;
  if ( !a2 )
    goto LABEL_84;
  if ( !(_DWORD)v19 && a2 == 8 )
  {
    if ( (unsigned int)v18 < v17 )
    {
      v27 = *(unsigned __int8 *)(v18 + *(_QWORD *)this);
      *((_DWORD *)this + 2) = v18 + 1;
      *a3 = v27;
      v28 = *((_DWORD *)this + 2);
      if ( v28 >= *((_DWORD *)this + 3) )
        v29 = 0;
      else
        v29 = *(_BYTE *)(v28 + *(_QWORD *)this);
      *((_BYTE *)this + 20) = v29;
    }
    else
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v19, v18);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v25, "CBitstreamReader::PopN", 228, -2147418113);
      }
      if ( g_wppLevels )
      {
        v26 = 21;
LABEL_50:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v26,
          WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids,
          this,
          -2147418113);
      }
    }
    goto LABEL_84;
  }
  v30 = 0;
  v31 = (char *)this + 20;
  for ( i = 0; ; ++i )
  {
    if ( i >= a2 )
    {
      *a3 = v30;
      goto LABEL_84;
    }
    if ( !(_DWORD)v19 )
      break;
LABEL_60:
    v6 = (unsigned __int8)*v31;
    v33 = v6;
    LOBYTE(v6) = 2 * v6;
    *v31 = v6;
    v30 = (2 * v30) | (v33 >> 7);
    v19 = (unsigned int)(v19 + 1);
    *((_DWORD *)this + 4) = v19;
    if ( (_DWORD)v19 == 8 )
    {
      v18 = *((unsigned int *)this + 2);
      *((_DWORD *)this + 4) = 0;
      v6 = (unsigned int)(v18 + 1);
      *((_DWORD *)this + 2) = v6;
      if ( (unsigned int)v6 >= v17 )
        v34 = 0;
      else
        v34 = *(_BYTE *)(v6 + *(_QWORD *)this);
      v35 = *((_BYTE *)this + 21) == 0;
      *v31 = v34;
      if ( !v35 && (unsigned int)v6 < v17 && (unsigned int)v6 >= 2 )
      {
        v36 = *(_QWORD *)this;
        if ( !*(_BYTE *)((unsigned int)(v18 - 1) + *(_QWORD *)this)
          && !*(_BYTE *)(v18 + v36)
          && *(_BYTE *)(v6 + v36) == 3 )
        {
          *((_DWORD *)this + 2) = v18 + 2;
        }
      }
      v19 = 0;
    }
  }
  if ( *((_DWORD *)this + 2) < v17 )
  {
    *v31 = *(_BYTE *)(*((unsigned int *)this + 2) + *(_QWORD *)this);
    goto LABEL_60;
  }
  v37 = (__int64 *)CallStackTracing::s_wpInstance;
  v11 = -2147418113;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v19, v18);
    CallStackTracing::s_wpInstance = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v37 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
    if ( *((_DWORD *)v39 + 499) != -2147418113 )
      CallStackContext::TraceFailure(v39, "CBitstreamReader::PopN", 250, -2147418113);
  }
  if ( g_wppLevels )
  {
    v26 = 22;
    goto LABEL_50;
  }
LABEL_84:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return v11;
}

```

## disassembly

```asm
0x180082b6c  mov     [rsp+arg_0], rbx
0x180082b71  mov     [rsp+arg_8], rbp
0x180082b76  push    rsi
0x180082b77  push    rdi
0x180082b78  push    r13
0x180082b7a  push    r14
0x180082b7c  push    r15
0x180082b7e  sub     rsp, 30h
0x180082b82  mov     r14, r8
0x180082b85  lea     r13, aCbitstreamread; "CBitstreamReader::PopN"
0x180082b8c  mov     esi, edx
0x180082b8e  mov     rbx, rcx
0x180082b91  mov     ebp, 0D0h
0x180082b96  lea     rcx, [rsp+58h+arg_10]; this
0x180082b9b  mov     r8d, ebp; int
0x180082b9e  mov     rdx, r13; char *
0x180082ba1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180082ba6  test    r14, r14
0x180082ba9  jnz     loc_180082C3C
0x180082baf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082bb6  test    rcx, rcx
0x180082bb9  jnz     short loc_180082BFC
0x180082bbb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082bc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082bc8  mov     rcx, rax
0x180082bcb  test    rax, rax
0x180082bce  jz      short loc_180082BEE
0x180082bd0  mov     rax, [rax]
0x180082bd3  mov     edx, 7F0h
0x180082bd8  mov     rax, [rax+8]
0x180082bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082be1  test    eax, eax
0x180082be3  jz      short loc_180082BEE
0x180082be5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082bec  jmp     short loc_180082BFC
0x180082bee  lea     rcx, qword_1800D6F70; this
0x180082bf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082bfc  cmp     byte ptr [rcx+8], 0
0x180082c00  mov     edi, 80004003h
0x180082c05  jz      short loc_180082C25
0x180082c07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082c0c  cmp     [rax+7CCh], edi
0x180082c12  jz      short loc_180082C25
0x180082c14  mov     r9d, edi; int
0x180082c17  mov     r8d, ebp; int
0x180082c1a  mov     rdx, r13; char *
0x180082c1d  mov     rcx, rax; this
0x180082c20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082c25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082c2c  jb      loc_180082FD8
0x180082c32  mov     edx, 12h
0x180082c37  jmp     loc_180082CD6
0x180082c3c  mov     dword ptr [r14], 0
0x180082c43  test    esi, esi
0x180082c45  jns     loc_180082CF9
0x180082c4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082c52  mov     edi, 80070057h
0x180082c57  test    rcx, rcx
0x180082c5a  jnz     short loc_180082C9D
0x180082c5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082c62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082c69  mov     rcx, rax
0x180082c6c  test    rax, rax
0x180082c6f  jz      short loc_180082C8F
0x180082c71  mov     rax, [rax]
0x180082c74  mov     edx, 7F0h
0x180082c79  mov     rax, [rax+8]
0x180082c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082c82  test    eax, eax
0x180082c84  jz      short loc_180082C8F
0x180082c86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082c8d  jmp     short loc_180082C9D
0x180082c8f  lea     rcx, qword_1800D6F70; this
0x180082c96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082c9d  cmp     byte ptr [rcx+8], 0
0x180082ca1  jz      short loc_180082CC4
0x180082ca3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082ca8  cmp     [rax+7CCh], edi
0x180082cae  jz      short loc_180082CC4
0x180082cb0  mov     r9d, edi; int
0x180082cb3  mov     r8d, 0D5h; int
0x180082cb9  mov     rdx, r13; char *
0x180082cbc  mov     rcx, rax; this
0x180082cbf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082cc4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082ccb  jb      loc_180082FD8
0x180082cd1  mov     edx, 13h
0x180082cd6  mov     [rsp+58h+var_38], edi
0x180082cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180082ce1  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x180082ce8  mov     r9, rbx
0x180082ceb  mov     rcx, [rcx+10h]
0x180082cef  call    WPP_SF_qD
0x180082cf4  jmp     loc_180082FD8
0x180082cf9  mov     r10d, [rbx+0Ch]
0x180082cfd  mov     eax, r10d
0x180082d00  mov     r9d, [rbx+8]
0x180082d04  mov     r8d, [rbx+10h]
0x180082d08  sub     eax, r9d
0x180082d0b  shl     eax, 3
0x180082d0e  sub     eax, r8d
0x180082d11  cmp     esi, eax
0x180082d13  jbe     loc_180082DA9
0x180082d19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082d20  mov     edi, 80004005h
0x180082d25  test    rcx, rcx
0x180082d28  jnz     short loc_180082D6B
0x180082d2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082d30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082d37  mov     rcx, rax
0x180082d3a  test    rax, rax
0x180082d3d  jz      short loc_180082D5D
0x180082d3f  mov     rax, [rax]
0x180082d42  mov     edx, 7F0h
0x180082d47  mov     rax, [rax+8]
0x180082d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d50  test    eax, eax
0x180082d52  jz      short loc_180082D5D
0x180082d54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082d5b  jmp     short loc_180082D6B
0x180082d5d  lea     rcx, qword_1800D6F70; this
0x180082d64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082d6b  cmp     byte ptr [rcx+8], 0
0x180082d6f  jz      short loc_180082D92
0x180082d71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082d76  cmp     [rax+7CCh], edi
0x180082d7c  jz      short loc_180082D92
0x180082d7e  mov     r9d, edi; int
0x180082d81  mov     r8d, 0D9h; int
0x180082d87  mov     rdx, r13; char *
0x180082d8a  mov     rcx, rax; this
0x180082d8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082d92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082d99  jb      loc_180082FD8
0x180082d9f  mov     edx, 14h
0x180082da4  jmp     loc_180082CD6
0x180082da9  mov     edi, esi
0x180082dab  shr     edi, 1Fh
0x180082dae  test    esi, esi
0x180082db0  jz      loc_180082FD8
0x180082db6  test    r8d, r8d
0x180082db9  jnz     loc_180082E95
0x180082dbf  cmp     esi, 8
0x180082dc2  jnz     loc_180082E95
0x180082dc8  cmp     r9d, r10d
0x180082dcb  jb      loc_180082E67
0x180082dd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082dd8  mov     esi, 8000FFFFh
0x180082ddd  mov     edi, esi
0x180082ddf  test    rcx, rcx
0x180082de2  jnz     short loc_180082E25
0x180082de4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082dea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082df1  mov     rcx, rax
0x180082df4  test    rax, rax
0x180082df7  jz      short loc_180082E17
0x180082df9  mov     rax, [rax]
0x180082dfc  mov     edx, 7F0h
0x180082e01  mov     rax, [rax+8]
0x180082e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e0a  test    eax, eax
0x180082e0c  jz      short loc_180082E17
0x180082e0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082e15  jmp     short loc_180082E25
0x180082e17  lea     rcx, qword_1800D6F70; this
0x180082e1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082e25  cmp     byte ptr [rcx+8], 0
0x180082e29  jz      short loc_180082E4C
0x180082e2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082e30  cmp     [rax+7CCh], esi
0x180082e36  jz      short loc_180082E4C
0x180082e38  mov     r9d, esi; int
0x180082e3b  mov     r8d, 0E4h; int
0x180082e41  mov     rdx, r13; char *
0x180082e44  mov     rcx, rax; this
0x180082e47  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082e4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082e53  jb      loc_180082FD8
0x180082e59  mov     edx, 15h
0x180082e5e  mov     [rsp+58h+var_38], esi
0x180082e62  jmp     loc_180082CDA
0x180082e67  mov     rax, [rbx]
0x180082e6a  movzx   edx, byte ptr [r9+rax]
0x180082e6f  lea     eax, [r9+1]
0x180082e73  mov     [rbx+8], eax
0x180082e76  mov     [r14], edx
0x180082e79  mov     eax, [rbx+8]
0x180082e7c  cmp     eax, [rbx+0Ch]
0x180082e7f  jnb     short loc_180082E8B
0x180082e81  mov     ecx, eax
0x180082e83  mov     rax, [rbx]
0x180082e86  mov     dl, [rcx+rax]
0x180082e89  jmp     short loc_180082E8D
0x180082e8b  xor     dl, dl
0x180082e8d  mov     [rbx+14h], dl
0x180082e90  jmp     loc_180082FD8
0x180082e95  xor     r15d, r15d
0x180082e98  lea     r11, [rbx+14h]
0x180082e9c  xor     ebp, ebp
0x180082e9e  cmp     ebp, esi
0x180082ea0  jge     loc_180082FD5
0x180082ea6  test    r8d, r8d
0x180082ea9  jnz     short loc_180082EC1
0x180082eab  cmp     [rbx+8], r10d
0x180082eaf  jnb     loc_180082F47
0x180082eb5  mov     ecx, [rbx+8]
0x180082eb8  mov     rax, [rbx]
0x180082ebb  mov     cl, [rcx+rax]
0x180082ebe  mov     [r11], cl
0x180082ec1  movzx   edx, byte ptr [r11]
0x180082ec5  lea     eax, [r15+r15]
0x180082ec9  mov     ecx, edx
0x180082ecb  add     dl, dl
0x180082ecd  shr     ecx, 7
0x180082ed0  mov     r15d, ecx
0x180082ed3  mov     [r11], dl
0x180082ed6  or      r15d, eax
0x180082ed9  inc     r8d
0x180082edc  mov     [rbx+10h], r8d
0x180082ee0  cmp     r8d, 8
0x180082ee4  jnz     short loc_180082F40
0x180082ee6  mov     r9d, [rbx+8]
0x180082eea  mov     dword ptr [rbx+10h], 0
0x180082ef1  lea     edx, [r9+1]
0x180082ef5  mov     [rbx+8], edx
0x180082ef8  cmp     edx, r10d
0x180082efb  jnb     short loc_180082F06
0x180082efd  mov     rax, [rbx]
0x180082f00  mov     r8b, [rdx+rax]
0x180082f04  jmp     short loc_180082F09
0x180082f06  xor     r8b, r8b
0x180082f09  cmp     byte ptr [rbx+15h], 0
0x180082f0d  mov     [r11], r8b
0x180082f10  jz      short loc_180082F3D
0x180082f12  cmp     edx, r10d
0x180082f15  jnb     short loc_180082F3D
0x180082f17  cmp     edx, 2
0x180082f1a  jb      short loc_180082F3D
0x180082f1c  mov     r8, [rbx]
0x180082f1f  lea     eax, [rdx-2]
0x180082f22  cmp     byte ptr [rax+r8], 0
0x180082f27  jnz     short loc_180082F3D
0x180082f29  cmp     byte ptr [r9+r8], 0
0x180082f2e  jnz     short loc_180082F3D
0x180082f30  cmp     byte ptr [rdx+r8], 3
0x180082f35  jnz     short loc_180082F3D
0x180082f37  lea     eax, [rdx+1]
0x180082f3a  mov     [rbx+8], eax
0x180082f3d  xor     r8d, r8d
0x180082f40  inc     ebp
0x180082f42  jmp     loc_180082E9E
0x180082f47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082f4e  mov     esi, 8000FFFFh
0x180082f53  mov     edi, esi
0x180082f55  test    rcx, rcx
0x180082f58  jnz     short loc_180082F9B
0x180082f5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082f60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082f67  mov     rcx, rax
0x180082f6a  test    rax, rax
0x180082f6d  jz      short loc_180082F8D
0x180082f6f  mov     rax, [rax]
0x180082f72  mov     edx, 7F0h
0x180082f77  mov     rax, [rax+8]
0x180082f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f80  test    eax, eax
0x180082f82  jz      short loc_180082F8D
0x180082f84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082f8b  jmp     short loc_180082F9B
0x180082f8d  lea     rcx, qword_1800D6F70; this
0x180082f94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082f9b  cmp     byte ptr [rcx+8], 0
0x180082f9f  jz      short loc_180082FC2
0x180082fa1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082fa6  cmp     [rax+7CCh], esi
0x180082fac  jz      short loc_180082FC2
0x180082fae  mov     r9d, esi; int
0x180082fb1  mov     r8d, 0FAh; int
0x180082fb7  mov     rdx, r13; char *
0x180082fba  mov     rcx, rax; this
0x180082fbd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082fc2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082fc9  jb      short loc_180082FD8
0x180082fcb  mov     edx, 16h
0x180082fd0  jmp     loc_180082E5E
0x180082fd5  mov     [r14], r15d
0x180082fd8  lea     rcx, [rsp+58h+arg_10]; this
0x180082fdd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180082fe2  mov     rbx, [rsp+58h+arg_0]
0x180082fe7  mov     eax, edi
0x180082fe9  mov     rbp, [rsp+58h+arg_8]
0x180082fee  add     rsp, 30h
0x180082ff2  pop     r15
0x180082ff4  pop     r14
0x180082ff6  pop     r13
0x180082ff8  pop     rdi
0x180082ff9  pop     rsi
0x180082ffa  retn
```
