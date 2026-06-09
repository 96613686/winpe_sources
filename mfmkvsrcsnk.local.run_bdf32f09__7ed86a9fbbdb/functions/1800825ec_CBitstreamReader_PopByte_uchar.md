# CBitstreamReader::PopByte(uchar *)

- ea: `0x1800825ec`
- end: `0x180082711`
- name: `?PopByte@CBitstreamReader@@QEAAJPEAE@Z`
- size: `293`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, unsigned __int8 *)`
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
- `0x1800825ec`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008262d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008262d`

## string_xrefs

- `0x180082601`: `CBitstreamReader::PopByte`
- `0x180082689`: `CBitstreamReader::PopByte`

## pseudocode

```c
__int64 __fastcall CBitstreamReader::PopByte(CBitstreamReader *this, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  int v9; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v12; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CBitstreamReader::PopByte", 104);
  if ( a2 )
  {
    *a2 = 0;
    v12 = 0;
    v9 = CBitstreamReader::PopN(this, 8, &v12);
    if ( v9 >= 0 )
      *a2 = v12;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CBitstreamReader::PopByte", 104, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800825ec  mov     [rsp+arg_0], rbx
0x1800825f1  mov     [rsp+arg_10], rsi
0x1800825f6  push    rdi
0x1800825f7  sub     rsp, 30h
0x1800825fb  mov     rdi, rdx
0x1800825fe  mov     rsi, rcx
0x180082601  lea     rdx, aCbitstreamread_0; "CBitstreamReader::PopByte"
0x180082608  mov     r8d, 68h ; 'h'; int
0x18008260e  lea     rcx, [rsp+38h+arg_8]; this
0x180082613  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180082618  test    rdi, rdi
0x18008261b  jnz     loc_1800826CC
0x180082621  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082628  test    rcx, rcx
0x18008262b  jnz     short loc_18008266E
0x18008262d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082633  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008263a  mov     rcx, rax
0x18008263d  test    rax, rax
0x180082640  jz      short loc_180082660
0x180082642  mov     rax, [rax]
0x180082645  mov     edx, 7F0h
0x18008264a  mov     rax, [rax+8]
0x18008264e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082653  test    eax, eax
0x180082655  jz      short loc_180082660
0x180082657  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008265e  jmp     short loc_18008266E
0x180082660  lea     rcx, qword_1800D6F70; this
0x180082667  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008266e  cmp     byte ptr [rcx+8], 0
0x180082672  mov     ebx, 80004003h
0x180082677  jz      short loc_18008269E
0x180082679  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008267e  cmp     [rax+7CCh], ebx
0x180082684  jz      short loc_18008269E
0x180082686  mov     r9d, ebx; int
0x180082689  lea     rdx, aCbitstreamread_0; "CBitstreamReader::PopByte"
0x180082690  mov     r8d, 68h ; 'h'; int
0x180082696  mov     rcx, rax; this
0x180082699  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008269e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800826a5  jb      short loc_1800826F5
0x1800826a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800826ae  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x1800826b5  mov     edx, 0Fh
0x1800826ba  mov     [rsp+38h+var_18], ebx
0x1800826be  mov     r9, rsi
0x1800826c1  mov     rcx, [rcx+10h]
0x1800826c5  call    WPP_SF_qD
0x1800826ca  jmp     short loc_1800826F5
0x1800826cc  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x1800826d1  mov     byte ptr [rdi], 0
0x1800826d4  mov     edx, 8; int
0x1800826d9  mov     [rsp+38h+arg_8], 0
0x1800826e1  mov     rcx, rsi; this
0x1800826e4  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x1800826e9  mov     ebx, eax
0x1800826eb  test    eax, eax
0x1800826ed  js      short loc_1800826F5
0x1800826ef  mov     cl, byte ptr [rsp+38h+arg_8]
0x1800826f3  mov     [rdi], cl
0x1800826f5  lea     rcx, [rsp+38h+arg_8]; this
0x1800826fa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800826ff  mov     rsi, [rsp+38h+arg_10]
0x180082704  mov     eax, ebx
0x180082706  mov     rbx, [rsp+38h+arg_0]
0x18008270b  add     rsp, 30h
0x18008270f  pop     rdi
0x180082710  retn
```
