# CBitstreamReader::PopN(int,ulong *)

- ea: `0x180086640`
- end: `0x180086aee`
- name: `?PopN@CBitstreamReader@@QEAAJHPEAK@Z`
- size: `1198`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, int, unsigned int *)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x18007e76c`
- `0x18007e940`
- `0x18007ec30`
- `0x18007f2e4`
- `0x18007f9c4`
- `0x180081f04`
- `0x1800833ec`
- `0x180084c84`
- `0x180086098`
- `0x1800863ac`
- `0x180086af4`
- `0x180086b48`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008668f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008680a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086a46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008668f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008680a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086a46`

## string_xrefs

- `0x180086659`: `CBitstreamReader::PopN`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v20 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids, this, v11);
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
          v23 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          &WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids,
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
      v37 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180086640  mov     [rsp+arg_0], rbx
0x180086645  mov     [rsp+arg_8], rbp
0x18008664a  push    rsi
0x18008664b  push    rdi
0x18008664c  push    r13
0x18008664e  push    r14
0x180086650  push    r15
0x180086652  sub     rsp, 30h
0x180086656  mov     r14, r8
0x180086659  lea     r13, aCbitstreamread; "CBitstreamReader::PopN"
0x180086660  mov     esi, edx
0x180086662  mov     rbx, rcx
0x180086665  mov     ebp, 0D0h
0x18008666a  lea     rcx, [rsp+58h+arg_10]; this
0x18008666f  mov     r8d, ebp; int
0x180086672  mov     rdx, r13; char *
0x180086675  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008667a  test    r14, r14
0x18008667d  jnz     loc_180086716
0x180086683  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008668a  test    rcx, rcx
0x18008668d  jnz     short loc_1800866D6
0x18008668f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086696  nop     dword ptr [rax+rax+00h]
0x18008669b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800866a2  mov     rcx, rax
0x1800866a5  test    rax, rax
0x1800866a8  jz      short loc_1800866C8
0x1800866aa  mov     rax, [rax]
0x1800866ad  mov     edx, 7F0h
0x1800866b2  mov     rax, [rax+8]
0x1800866b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866bb  test    eax, eax
0x1800866bd  jz      short loc_1800866C8
0x1800866bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800866c6  jmp     short loc_1800866D6
0x1800866c8  lea     rcx, qword_1800DBF70; this
0x1800866cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800866d6  cmp     byte ptr [rcx+8], 0
0x1800866da  mov     edi, 80004003h
0x1800866df  jz      short loc_1800866FF
0x1800866e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800866e6  cmp     [rax+7CCh], edi
0x1800866ec  jz      short loc_1800866FF
0x1800866ee  mov     r9d, edi; int
0x1800866f1  mov     r8d, ebp; int
0x1800866f4  mov     rdx, r13; char *
0x1800866f7  mov     rcx, rax; this
0x1800866fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800866ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086706  jb      loc_180086ACA
0x18008670c  mov     edx, 12h
0x180086711  jmp     loc_1800867B6
0x180086716  mov     dword ptr [r14], 0
0x18008671d  test    esi, esi
0x18008671f  jns     loc_1800867D9
0x180086725  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008672c  mov     edi, 80070057h
0x180086731  test    rcx, rcx
0x180086734  jnz     short loc_18008677D
0x180086736  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008673d  nop     dword ptr [rax+rax+00h]
0x180086742  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086749  mov     rcx, rax
0x18008674c  test    rax, rax
0x18008674f  jz      short loc_18008676F
0x180086751  mov     rax, [rax]
0x180086754  mov     edx, 7F0h
0x180086759  mov     rax, [rax+8]
0x18008675d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086762  test    eax, eax
0x180086764  jz      short loc_18008676F
0x180086766  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008676d  jmp     short loc_18008677D
0x18008676f  lea     rcx, qword_1800DBF70; this
0x180086776  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008677d  cmp     byte ptr [rcx+8], 0
0x180086781  jz      short loc_1800867A4
0x180086783  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086788  cmp     [rax+7CCh], edi
0x18008678e  jz      short loc_1800867A4
0x180086790  mov     r9d, edi; int
0x180086793  mov     r8d, 0D5h; int
0x180086799  mov     rdx, r13; char *
0x18008679c  mov     rcx, rax; this
0x18008679f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800867a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800867ab  jb      loc_180086ACA
0x1800867b1  mov     edx, 13h
0x1800867b6  mov     [rsp+58h+var_38], edi
0x1800867ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800867c1  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x1800867c8  mov     r9, rbx
0x1800867cb  mov     rcx, [rcx+10h]
0x1800867cf  call    WPP_SF_qD
0x1800867d4  jmp     loc_180086ACA
0x1800867d9  mov     r10d, [rbx+0Ch]
0x1800867dd  mov     eax, r10d
0x1800867e0  mov     r9d, [rbx+8]
0x1800867e4  mov     r8d, [rbx+10h]
0x1800867e8  sub     eax, r9d
0x1800867eb  shl     eax, 3
0x1800867ee  sub     eax, r8d
0x1800867f1  cmp     esi, eax
0x1800867f3  jbe     loc_18008688F
0x1800867f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086800  mov     edi, 80004005h
0x180086805  test    rcx, rcx
0x180086808  jnz     short loc_180086851
0x18008680a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086811  nop     dword ptr [rax+rax+00h]
0x180086816  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008681d  mov     rcx, rax
0x180086820  test    rax, rax
0x180086823  jz      short loc_180086843
0x180086825  mov     rax, [rax]
0x180086828  mov     edx, 7F0h
0x18008682d  mov     rax, [rax+8]
0x180086831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086836  test    eax, eax
0x180086838  jz      short loc_180086843
0x18008683a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086841  jmp     short loc_180086851
0x180086843  lea     rcx, qword_1800DBF70; this
0x18008684a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086851  cmp     byte ptr [rcx+8], 0
0x180086855  jz      short loc_180086878
0x180086857  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008685c  cmp     [rax+7CCh], edi
0x180086862  jz      short loc_180086878
0x180086864  mov     r9d, edi; int
0x180086867  mov     r8d, 0D9h; int
0x18008686d  mov     rdx, r13; char *
0x180086870  mov     rcx, rax; this
0x180086873  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086878  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008687f  jb      loc_180086ACA
0x180086885  mov     edx, 14h
0x18008688a  jmp     loc_1800867B6
0x18008688f  mov     edi, esi
0x180086891  shr     edi, 1Fh
0x180086894  test    esi, esi
0x180086896  jz      loc_180086ACA
0x18008689c  test    r8d, r8d
0x18008689f  jnz     loc_180086981
0x1800868a5  cmp     esi, 8
0x1800868a8  jnz     loc_180086981
0x1800868ae  cmp     r9d, r10d
0x1800868b1  jb      loc_180086953
0x1800868b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868be  mov     esi, 8000FFFFh
0x1800868c3  mov     edi, esi
0x1800868c5  test    rcx, rcx
0x1800868c8  jnz     short loc_180086911
0x1800868ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800868d1  nop     dword ptr [rax+rax+00h]
0x1800868d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868dd  mov     rcx, rax
0x1800868e0  test    rax, rax
0x1800868e3  jz      short loc_180086903
0x1800868e5  mov     rax, [rax]
0x1800868e8  mov     edx, 7F0h
0x1800868ed  mov     rax, [rax+8]
0x1800868f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868f6  test    eax, eax
0x1800868f8  jz      short loc_180086903
0x1800868fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086901  jmp     short loc_180086911
0x180086903  lea     rcx, qword_1800DBF70; this
0x18008690a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086911  cmp     byte ptr [rcx+8], 0
0x180086915  jz      short loc_180086938
0x180086917  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008691c  cmp     [rax+7CCh], esi
0x180086922  jz      short loc_180086938
0x180086924  mov     r9d, esi; int
0x180086927  mov     r8d, 0E4h; int
0x18008692d  mov     rdx, r13; char *
0x180086930  mov     rcx, rax; this
0x180086933  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086938  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008693f  jb      loc_180086ACA
0x180086945  mov     edx, 15h
0x18008694a  mov     [rsp+58h+var_38], esi
0x18008694e  jmp     loc_1800867BA
0x180086953  mov     rax, [rbx]
0x180086956  movzx   edx, byte ptr [r9+rax]
0x18008695b  lea     eax, [r9+1]
0x18008695f  mov     [rbx+8], eax
0x180086962  mov     [r14], edx
0x180086965  mov     eax, [rbx+8]
0x180086968  cmp     eax, [rbx+0Ch]
0x18008696b  jnb     short loc_180086977
0x18008696d  mov     ecx, eax
0x18008696f  mov     rax, [rbx]
0x180086972  mov     dl, [rcx+rax]
0x180086975  jmp     short loc_180086979
0x180086977  xor     dl, dl
0x180086979  mov     [rbx+14h], dl
0x18008697c  jmp     loc_180086ACA
0x180086981  xor     r15d, r15d
0x180086984  lea     r11, [rbx+14h]
0x180086988  xor     ebp, ebp
0x18008698a  cmp     ebp, esi
0x18008698c  jge     loc_180086AC7
0x180086992  test    r8d, r8d
0x180086995  jnz     short loc_1800869AD
0x180086997  cmp     [rbx+8], r10d
0x18008699b  jnb     loc_180086A33
0x1800869a1  mov     ecx, [rbx+8]
0x1800869a4  mov     rax, [rbx]
0x1800869a7  mov     cl, [rcx+rax]
0x1800869aa  mov     [r11], cl
0x1800869ad  movzx   edx, byte ptr [r11]
0x1800869b1  lea     eax, [r15+r15]
0x1800869b5  mov     ecx, edx
0x1800869b7  add     dl, dl
0x1800869b9  shr     ecx, 7
0x1800869bc  mov     r15d, ecx
0x1800869bf  mov     [r11], dl
0x1800869c2  or      r15d, eax
0x1800869c5  inc     r8d
0x1800869c8  mov     [rbx+10h], r8d
0x1800869cc  cmp     r8d, 8
0x1800869d0  jnz     short loc_180086A2C
0x1800869d2  mov     r9d, [rbx+8]
0x1800869d6  mov     dword ptr [rbx+10h], 0
0x1800869dd  lea     edx, [r9+1]
0x1800869e1  mov     [rbx+8], edx
0x1800869e4  cmp     edx, r10d
0x1800869e7  jnb     short loc_1800869F2
0x1800869e9  mov     rax, [rbx]
0x1800869ec  mov     r8b, [rdx+rax]
0x1800869f0  jmp     short loc_1800869F5
0x1800869f2  xor     r8b, r8b
0x1800869f5  cmp     byte ptr [rbx+15h], 0
0x1800869f9  mov     [r11], r8b
0x1800869fc  jz      short loc_180086A29
0x1800869fe  cmp     edx, r10d
0x180086a01  jnb     short loc_180086A29
0x180086a03  cmp     edx, 2
0x180086a06  jb      short loc_180086A29
0x180086a08  mov     r8, [rbx]
0x180086a0b  lea     eax, [rdx-2]
0x180086a0e  cmp     byte ptr [rax+r8], 0
0x180086a13  jnz     short loc_180086A29
0x180086a15  cmp     byte ptr [r9+r8], 0
0x180086a1a  jnz     short loc_180086A29
0x180086a1c  cmp     byte ptr [rdx+r8], 3
0x180086a21  jnz     short loc_180086A29
0x180086a23  lea     eax, [rdx+1]
0x180086a26  mov     [rbx+8], eax
0x180086a29  xor     r8d, r8d
0x180086a2c  inc     ebp
0x180086a2e  jmp     loc_18008698A
0x180086a33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a3a  mov     esi, 8000FFFFh
0x180086a3f  mov     edi, esi
0x180086a41  test    rcx, rcx
0x180086a44  jnz     short loc_180086A8D
0x180086a46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086a4d  nop     dword ptr [rax+rax+00h]
0x180086a52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a59  mov     rcx, rax
0x180086a5c  test    rax, rax
0x180086a5f  jz      short loc_180086A7F
0x180086a61  mov     rax, [rax]
0x180086a64  mov     edx, 7F0h
0x180086a69  mov     rax, [rax+8]
0x180086a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a72  test    eax, eax
0x180086a74  jz      short loc_180086A7F
0x180086a76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a7d  jmp     short loc_180086A8D
0x180086a7f  lea     rcx, qword_1800DBF70; this
0x180086a86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a8d  cmp     byte ptr [rcx+8], 0
0x180086a91  jz      short loc_180086AB4
0x180086a93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086a98  cmp     [rax+7CCh], esi
0x180086a9e  jz      short loc_180086AB4
0x180086aa0  mov     r9d, esi; int
0x180086aa3  mov     r8d, 0FAh; int
0x180086aa9  mov     rdx, r13; char *
0x180086aac  mov     rcx, rax; this
0x180086aaf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086ab4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086abb  jb      short loc_180086ACA
0x180086abd  mov     edx, 16h
0x180086ac2  jmp     loc_18008694A
0x180086ac7  mov     [r14], r15d
0x180086aca  lea     rcx, [rsp+58h+arg_10]; this
0x180086acf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180086ad4  mov     rbx, [rsp+58h+arg_0]
0x180086ad9  mov     eax, edi
0x180086adb  mov     rbp, [rsp+58h+arg_8]
0x180086ae0  add     rsp, 30h
0x180086ae4  pop     r15
0x180086ae6  pop     r14
0x180086ae8  pop     r13
  ... truncated ...
```
