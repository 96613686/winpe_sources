# CBitstreamReader::PopEG_se(long *)

- ea: `0x1800861cc`
- end: `0x1800863a4`
- name: `?PopEG_se@CBitstreamReader@@QEAAJPEAJ@Z`
- size: `472`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, int *)`
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
- `0x1800861cc`
- `0x1800863ac`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008620d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800862cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008620d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800862cc`

## string_xrefs

- `0x1800861e1`: `CBitstreamReader::PopEG_se`
- `0x18008626f`: `CBitstreamReader::PopEG_se`
- `0x180086329`: `CBitstreamReader::PopEG_se`

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
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x1800861cc  mov     [rsp+arg_0], rbx
0x1800861d1  mov     [rsp+arg_10], rsi
0x1800861d6  push    rdi
0x1800861d7  sub     rsp, 30h
0x1800861db  mov     rdi, rdx
0x1800861de  mov     rsi, rcx
0x1800861e1  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x1800861e8  mov     r8d, 141h; int
0x1800861ee  lea     rcx, [rsp+38h+arg_8]; this
0x1800861f3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800861f8  test    rdi, rdi
0x1800861fb  jnz     loc_18008629B
0x180086201  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086208  test    rcx, rcx
0x18008620b  jnz     short loc_180086254
0x18008620d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086214  nop     dword ptr [rax+rax+00h]
0x180086219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086220  mov     rcx, rax
0x180086223  test    rax, rax
0x180086226  jz      short loc_180086246
0x180086228  mov     rax, [rax]
0x18008622b  mov     edx, 7F0h
0x180086230  mov     rax, [rax+8]
0x180086234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086239  test    eax, eax
0x18008623b  jz      short loc_180086246
0x18008623d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086244  jmp     short loc_180086254
0x180086246  lea     rcx, qword_1800DBF70; this
0x18008624d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086254  cmp     byte ptr [rcx+8], 0
0x180086258  mov     ebx, 80004003h
0x18008625d  jz      short loc_180086284
0x18008625f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086264  cmp     [rax+7CCh], ebx
0x18008626a  jz      short loc_180086284
0x18008626c  mov     r9d, ebx; int
0x18008626f  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x180086276  mov     r8d, 141h; int
0x18008627c  mov     rcx, rax; this
0x18008627f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086284  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008628b  jb      loc_180086387
0x180086291  mov     edx, 1Ah
0x180086296  jmp     loc_18008634C
0x18008629b  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x1800862a0  mov     dword ptr [rdi], 0
0x1800862a6  mov     rcx, rsi; this
0x1800862a9  mov     [rsp+38h+arg_8], 0
0x1800862b1  call    ?PopEG_ue@CBitstreamReader@@QEAAJPEAK@Z; CBitstreamReader::PopEG_ue(ulong *)
0x1800862b6  mov     ebx, eax
0x1800862b8  test    eax, eax
0x1800862ba  jns     loc_18008636C
0x1800862c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862c7  test    rcx, rcx
0x1800862ca  jnz     short loc_180086313
0x1800862cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800862d3  nop     dword ptr [rax+rax+00h]
0x1800862d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800862df  mov     rcx, rax
0x1800862e2  test    rax, rax
0x1800862e5  jz      short loc_180086305
0x1800862e7  mov     rax, [rax]
0x1800862ea  mov     edx, 7F0h
0x1800862ef  mov     rax, [rax+8]
0x1800862f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862f8  test    eax, eax
0x1800862fa  jz      short loc_180086305
0x1800862fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086303  jmp     short loc_180086313
0x180086305  lea     rcx, qword_1800DBF70; this
0x18008630c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086313  cmp     byte ptr [rcx+8], 0
0x180086317  jz      short loc_18008633E
0x180086319  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008631e  cmp     [rax+7CCh], ebx
0x180086324  jz      short loc_18008633E
0x180086326  mov     r9d, ebx; int
0x180086329  lea     rdx, aCbitstreamread_2; "CBitstreamReader::PopEG_se"
0x180086330  mov     r8d, 145h; int
0x180086336  mov     rcx, rax; this
0x180086339  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008633e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086345  jb      short loc_180086387
0x180086347  mov     edx, 1Bh
0x18008634c  mov     rcx, cs:WPP_GLOBAL_Control
0x180086353  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x18008635a  mov     r9, rsi
0x18008635d  mov     [rsp+38h+var_18], ebx
0x180086361  mov     rcx, [rcx+10h]
0x180086365  call    WPP_SF_qD
0x18008636a  jmp     short loc_180086387
0x18008636c  mov     eax, [rsp+38h+arg_8]
0x180086370  test    al, 1
0x180086372  jnz     short loc_18008637B
0x180086374  mov     ecx, 0FFFFFFFEh
0x180086379  jmp     short loc_180086382
0x18008637b  inc     eax
0x18008637d  mov     ecx, 2
0x180086382  cdq
0x180086383  idiv    ecx
0x180086385  mov     [rdi], eax
0x180086387  lea     rcx, [rsp+38h+arg_8]; this
0x18008638c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180086391  mov     rsi, [rsp+38h+arg_10]
0x180086396  mov     eax, ebx
0x180086398  mov     rbx, [rsp+38h+arg_0]
0x18008639d  add     rsp, 30h
0x1800863a1  pop     rdi
0x1800863a2  retn
```
