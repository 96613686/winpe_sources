# CBitstreamReader::PopEG_se(long *)

- ea: `0x180082718`
- end: `0x1800828e3`
- name: `?PopEG_se@CBitstreamReader@@QEAAJPEAJ@Z`
- size: `459`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18007c1c4`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180082718`
- `0x1800828ec`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082759`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082812`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082759`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082812`

## string_xrefs

- `0x18008272d`: `CBitstreamReader::PopEG_se`
- `0x1800827b5`: `CBitstreamReader::PopEG_se`
- `0x180082869`: `CBitstreamReader::PopEG_se`

## pseudocode

```c
__int64 __fastcall CBitstreamReader::PopEG_se(CBitstreamReader *this, int *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  int v9; // ebx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  signed int v18; // eax
  int v19; // ecx
  unsigned int v21; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "CBitstreamReader::PopEG_se", 321);
  if ( a2 )
  {
    *a2 = 0;
    v21 = 0;
    v9 = CBitstreamReader::PopEG_ue(this, &v21);
    if ( v9 >= 0 )
    {
      v18 = v21;
      if ( (v21 & 1) != 0 )
      {
        v18 = v21 + 1;
        v19 = 2;
      }
      else
      {
        v19 = -2;
      }
      *a2 = v18 / v19;
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CBitstreamReader::PopEG_se", 325, v9);
      }
      if ( g_wppLevels )
      {
        v11 = 27;
        goto LABEL_23;
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
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v9 = -2147467261;
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CBitstreamReader::PopEG_se", 321, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 26;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids, this, v9);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180082718  mov     [rsp+arg_0], rbx
0x18008271d  mov     [rsp+arg_10], rsi
0x180082722  push    rdi
0x180082723  sub     rsp, 30h
0x180082727  mov     rdi, rdx
0x18008272a  mov     rsi, rcx
0x18008272d  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x180082734  mov     r8d, 141h; int
0x18008273a  lea     rcx, [rsp+38h+arg_8]; this
0x18008273f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180082744  test    rdi, rdi
0x180082747  jnz     loc_1800827E1
0x18008274d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082754  test    rcx, rcx
0x180082757  jnz     short loc_18008279A
0x180082759  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008275f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082766  mov     rcx, rax
0x180082769  test    rax, rax
0x18008276c  jz      short loc_18008278C
0x18008276e  mov     rax, [rax]
0x180082771  mov     edx, 7F0h
0x180082776  mov     rax, [rax+8]
0x18008277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008277f  test    eax, eax
0x180082781  jz      short loc_18008278C
0x180082783  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008278a  jmp     short loc_18008279A
0x18008278c  lea     rcx, qword_1800D6F70; this
0x180082793  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008279a  cmp     byte ptr [rcx+8], 0
0x18008279e  mov     ebx, 80004003h
0x1800827a3  jz      short loc_1800827CA
0x1800827a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800827aa  cmp     [rax+7CCh], ebx
0x1800827b0  jz      short loc_1800827CA
0x1800827b2  mov     r9d, ebx; int
0x1800827b5  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x1800827bc  mov     r8d, 141h; int
0x1800827c2  mov     rcx, rax; this
0x1800827c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800827ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800827d1  jb      loc_1800828C7
0x1800827d7  mov     edx, 1Ah
0x1800827dc  jmp     loc_18008288C
0x1800827e1  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x1800827e6  mov     dword ptr [rdi], 0
0x1800827ec  mov     rcx, rsi; this
0x1800827ef  mov     [rsp+38h+arg_8], 0
0x1800827f7  call    ?PopEG_ue@CBitstreamReader@@QEAAJPEAK@Z; CBitstreamReader::PopEG_ue(ulong *)
0x1800827fc  mov     ebx, eax
0x1800827fe  test    eax, eax
0x180082800  jns     loc_1800828AC
0x180082806  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008280d  test    rcx, rcx
0x180082810  jnz     short loc_180082853
0x180082812  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082818  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008281f  mov     rcx, rax
0x180082822  test    rax, rax
0x180082825  jz      short loc_180082845
0x180082827  mov     rax, [rax]
0x18008282a  mov     edx, 7F0h
0x18008282f  mov     rax, [rax+8]
0x180082833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082838  test    eax, eax
0x18008283a  jz      short loc_180082845
0x18008283c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082843  jmp     short loc_180082853
0x180082845  lea     rcx, qword_1800D6F70; this
0x18008284c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082853  cmp     byte ptr [rcx+8], 0
0x180082857  jz      short loc_18008287E
0x180082859  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008285e  cmp     [rax+7CCh], ebx
0x180082864  jz      short loc_18008287E
0x180082866  mov     r9d, ebx; int
0x180082869  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x180082870  mov     r8d, 145h; int
0x180082876  mov     rcx, rax; this
0x180082879  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008287e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082885  jb      short loc_1800828C7
0x180082887  mov     edx, 1Bh
0x18008288c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082893  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x18008289a  mov     r9, rsi
0x18008289d  mov     [rsp+38h+var_18], ebx
0x1800828a1  mov     rcx, [rcx+10h]
0x1800828a5  call    WPP_SF_qD
0x1800828aa  jmp     short loc_1800828C7
0x1800828ac  mov     eax, [rsp+38h+arg_8]
0x1800828b0  test    al, 1
0x1800828b2  jnz     short loc_1800828BB
0x1800828b4  mov     ecx, 0FFFFFFFEh
0x1800828b9  jmp     short loc_1800828C2
0x1800828bb  inc     eax
0x1800828bd  mov     ecx, 2
0x1800828c2  cdq
0x1800828c3  idiv    ecx
0x1800828c5  mov     [rdi], eax
0x1800828c7  lea     rcx, [rsp+38h+arg_8]; this
0x1800828cc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800828d1  mov     rsi, [rsp+38h+arg_10]
0x1800828d6  mov     eax, ebx
0x1800828d8  mov     rbx, [rsp+38h+arg_0]
0x1800828dd  add     rsp, 30h
0x1800828e1  pop     rdi
0x1800828e2  retn
```
