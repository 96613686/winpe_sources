# CBitstreamReader::PopEG_ue(ulong *)

- ea: `0x1800863ac`
- end: `0x180086639`
- name: `?PopEG_ue@CBitstreamReader@@QEAAJPEAK@Z`
- size: `653`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18007f2e4`
- `0x18007f9c4`
- `0x1800861cc`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800863ac`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800863f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800864c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086585`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800863f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800864c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086585`

## string_xrefs

- `0x1800863c9`: `CBitstreamReader::PopEG_ue`
- `0x180086454`: `CBitstreamReader::PopEG_ue`
- `0x18008651e`: `CBitstreamReader::PopEG_ue`
- `0x1800865e2`: `CBitstreamReader::PopEG_ue`

## pseudocode

```c
__int64 __fastcall CBitstreamReader::PopEG_ue(CBitstreamReader *this, unsigned int *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  int v9; // ebx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  int v12; // esi
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int v27; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v27, "CBitstreamReader::PopEG_ue", 300);
  if ( a2 )
  {
    v12 = -1;
    v27 = 0;
    v13 = 0;
    while ( !v13 )
    {
      v9 = CBitstreamReader::PopN(this, 1, &v27);
      if ( v9 < 0 )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CBitstreamReader::PopEG_ue", 307, v9);
        }
        if ( g_wppLevels )
        {
          v11 = 24;
          goto LABEL_26;
        }
        goto LABEL_39;
      }
      v13 = v27;
      ++v12;
    }
    v9 = CBitstreamReader::PopN(this, v12, &v27);
    if ( v9 >= 0 )
    {
      *a2 = (1 << v12) + v27 - 1;
    }
    else
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
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
        if ( *((_DWORD *)v25 + 499) != v9 )
          CallStackContext::TraceFailure(v25, "CBitstreamReader::PopEG_ue", 310, v9);
      }
      if ( g_wppLevels )
      {
        v11 = 25;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v9 = -2147467261;
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CBitstreamReader::PopEG_ue", 300, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 23;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids, this, v9);
    }
  }
LABEL_39:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800863ac  mov     [rsp+arg_0], rbx
0x1800863b1  mov     [rsp+arg_10], rbp
0x1800863b6  push    rsi
0x1800863b7  push    rdi
0x1800863b8  push    r14
0x1800863ba  sub     rsp, 30h
0x1800863be  mov     r14, rdx
0x1800863c1  mov     rbp, rcx
0x1800863c4  mov     edi, 12Ch
0x1800863c9  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x1800863d0  mov     r8d, edi; int
0x1800863d3  lea     rcx, [rsp+48h+arg_8]; this
0x1800863d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800863dd  test    r14, r14
0x1800863e0  jnz     loc_180086480
0x1800863e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800863ed  test    rcx, rcx
0x1800863f0  jnz     short loc_180086439
0x1800863f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800863f9  nop     dword ptr [rax+rax+00h]
0x1800863fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086405  mov     rcx, rax
0x180086408  test    rax, rax
0x18008640b  jz      short loc_18008642B
0x18008640d  mov     rax, [rax]
0x180086410  mov     edx, 7F0h
0x180086415  mov     rax, [rax+8]
0x180086419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008641e  test    eax, eax
0x180086420  jz      short loc_18008642B
0x180086422  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086429  jmp     short loc_180086439
0x18008642b  lea     rcx, qword_1800DBF70; this
0x180086432  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086439  cmp     byte ptr [rcx+8], 0
0x18008643d  mov     ebx, 80004003h
0x180086442  jz      short loc_180086466
0x180086444  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086449  cmp     [rax+7CCh], ebx
0x18008644f  jz      short loc_180086466
0x180086451  mov     r9d, ebx; int
0x180086454  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x18008645b  mov     r8d, edi; int
0x18008645e  mov     rcx, rax; this
0x180086461  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086466  mov     edi, 1
0x18008646b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180086472  jb      loc_180086619
0x180086478  lea     edx, [rdi+16h]
0x18008647b  jmp     loc_180086545
0x180086480  or      esi, 0FFFFFFFFh
0x180086483  mov     [rsp+48h+arg_8], 0
0x18008648b  xor     eax, eax
0x18008648d  lea     edi, [rsi+2]
0x180086490  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x180086495  mov     rcx, rbp; this
0x180086498  test    eax, eax
0x18008649a  jnz     loc_180086568
0x1800864a0  mov     edx, edi; int
0x1800864a2  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x1800864a7  mov     ebx, eax
0x1800864a9  test    eax, eax
0x1800864ab  js      short loc_1800864B5
0x1800864ad  mov     eax, [rsp+48h+arg_8]
0x1800864b1  add     esi, edi
0x1800864b3  jmp     short loc_180086490
0x1800864b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800864bc  test    rcx, rcx
0x1800864bf  jnz     short loc_180086508
0x1800864c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800864c8  nop     dword ptr [rax+rax+00h]
0x1800864cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800864d4  mov     rcx, rax
0x1800864d7  test    rax, rax
0x1800864da  jz      short loc_1800864FA
0x1800864dc  mov     rax, [rax]
0x1800864df  mov     edx, 7F0h
0x1800864e4  mov     rax, [rax+8]
0x1800864e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864ed  test    eax, eax
0x1800864ef  jz      short loc_1800864FA
0x1800864f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800864f8  jmp     short loc_180086508
0x1800864fa  lea     rcx, qword_1800DBF70; this
0x180086501  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086508  cmp     byte ptr [rcx+8], 0
0x18008650c  jz      short loc_180086533
0x18008650e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086513  cmp     [rax+7CCh], ebx
0x180086519  jz      short loc_180086533
0x18008651b  mov     r9d, ebx; int
0x18008651e  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x180086525  mov     r8d, 133h; int
0x18008652b  mov     rcx, rax; this
0x18008652e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086533  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18008653a  jb      loc_180086619
0x180086540  mov     edx, 18h
0x180086545  mov     rcx, cs:WPP_GLOBAL_Control
0x18008654c  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x180086553  mov     r9, rbp
0x180086556  mov     [rsp+48h+var_28], ebx
0x18008655a  mov     rcx, [rcx+10h]
0x18008655e  call    WPP_SF_qD
0x180086563  jmp     loc_180086619
0x180086568  mov     edx, esi; int
0x18008656a  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18008656f  mov     ebx, eax
0x180086571  test    eax, eax
0x180086573  jns     loc_18008660A
0x180086579  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086580  test    rcx, rcx
0x180086583  jnz     short loc_1800865CC
0x180086585  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008658c  nop     dword ptr [rax+rax+00h]
0x180086591  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086598  mov     rcx, rax
0x18008659b  test    rax, rax
0x18008659e  jz      short loc_1800865BE
0x1800865a0  mov     rax, [rax]
0x1800865a3  mov     edx, 7F0h
0x1800865a8  mov     rax, [rax+8]
0x1800865ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800865b1  test    eax, eax
0x1800865b3  jz      short loc_1800865BE
0x1800865b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800865bc  jmp     short loc_1800865CC
0x1800865be  lea     rcx, qword_1800DBF70; this
0x1800865c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800865cc  cmp     byte ptr [rcx+8], 0
0x1800865d0  jz      short loc_1800865F7
0x1800865d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800865d7  cmp     [rax+7CCh], ebx
0x1800865dd  jz      short loc_1800865F7
0x1800865df  mov     r9d, ebx; int
0x1800865e2  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x1800865e9  mov     r8d, 136h; int
0x1800865ef  mov     rcx, rax; this
0x1800865f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800865f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800865fe  jb      short loc_180086619
0x180086600  mov     edx, 19h
0x180086605  jmp     loc_180086545
0x18008660a  mov     ecx, esi
0x18008660c  shl     edi, cl
0x18008660e  mov     ecx, [rsp+48h+arg_8]
0x180086612  dec     ecx
0x180086614  add     ecx, edi
0x180086616  mov     [r14], ecx
0x180086619  lea     rcx, [rsp+48h+arg_8]; this
0x18008661e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180086623  mov     rbp, [rsp+48h+arg_10]
0x180086628  mov     eax, ebx
0x18008662a  mov     rbx, [rsp+48h+arg_0]
0x18008662f  add     rsp, 30h
0x180086633  pop     r14
0x180086635  pop     rdi
0x180086636  pop     rsi
0x180086637  retn
```
