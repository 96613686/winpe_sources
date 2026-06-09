# CBitstreamReader::PopByte(uchar *)

- ea: `0x180086098`
- end: `0x1800861c4`
- name: `?PopByte@CBitstreamReader@@QEAAJPEAE@Z`
- size: `300`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18007f9c4`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180086098`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800860d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800860d9`

## string_xrefs

- `0x1800860ad`: `CBitstreamReader::PopByte`
- `0x18008613b`: `CBitstreamReader::PopByte`

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
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180086098  mov     [rsp+arg_0], rbx
0x18008609d  mov     [rsp+arg_10], rsi
0x1800860a2  push    rdi
0x1800860a3  sub     rsp, 30h
0x1800860a7  mov     rdi, rdx
0x1800860aa  mov     rsi, rcx
0x1800860ad  lea     rdx, aCbitstreamread_0; "CBitstreamReader::PopByte"
0x1800860b4  mov     r8d, 68h ; 'h'; int
0x1800860ba  lea     rcx, [rsp+38h+arg_8]; this
0x1800860bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800860c4  test    rdi, rdi
0x1800860c7  jnz     loc_18008617E
0x1800860cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800860d4  test    rcx, rcx
0x1800860d7  jnz     short loc_180086120
0x1800860d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800860e0  nop     dword ptr [rax+rax+00h]
0x1800860e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800860ec  mov     rcx, rax
0x1800860ef  test    rax, rax
0x1800860f2  jz      short loc_180086112
0x1800860f4  mov     rax, [rax]
0x1800860f7  mov     edx, 7F0h
0x1800860fc  mov     rax, [rax+8]
0x180086100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086105  test    eax, eax
0x180086107  jz      short loc_180086112
0x180086109  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086110  jmp     short loc_180086120
0x180086112  lea     rcx, qword_1800DBF70; this
0x180086119  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086120  cmp     byte ptr [rcx+8], 0
0x180086124  mov     ebx, 80004003h
0x180086129  jz      short loc_180086150
0x18008612b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086130  cmp     [rax+7CCh], ebx
0x180086136  jz      short loc_180086150
0x180086138  mov     r9d, ebx; int
0x18008613b  lea     rdx, aCbitstreamread_0; "CBitstreamReader::PopByte"
0x180086142  mov     r8d, 68h ; 'h'; int
0x180086148  mov     rcx, rax; this
0x18008614b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086150  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086157  jb      short loc_1800861A7
0x180086159  mov     rcx, cs:WPP_GLOBAL_Control
0x180086160  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x180086167  mov     edx, 0Fh
0x18008616c  mov     [rsp+38h+var_18], ebx
0x180086170  mov     r9, rsi
0x180086173  mov     rcx, [rcx+10h]
0x180086177  call    WPP_SF_qD
0x18008617c  jmp     short loc_1800861A7
0x18008617e  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180086183  mov     byte ptr [rdi], 0
0x180086186  mov     edx, 8; int
0x18008618b  mov     [rsp+38h+arg_8], 0
0x180086193  mov     rcx, rsi; this
0x180086196  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18008619b  mov     ebx, eax
0x18008619d  test    eax, eax
0x18008619f  js      short loc_1800861A7
0x1800861a1  mov     cl, byte ptr [rsp+38h+arg_8]
0x1800861a5  mov     [rdi], cl
0x1800861a7  lea     rcx, [rsp+38h+arg_8]; this
0x1800861ac  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800861b1  mov     rsi, [rsp+38h+arg_10]
0x1800861b6  mov     eax, ebx
0x1800861b8  mov     rbx, [rsp+38h+arg_0]
0x1800861bd  add     rsp, 30h
0x1800861c1  pop     rdi
0x1800861c2  retn
```
