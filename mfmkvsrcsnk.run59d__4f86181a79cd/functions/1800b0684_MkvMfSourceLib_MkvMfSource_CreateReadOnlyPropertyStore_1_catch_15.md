# _MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore_::_1_::catch$15

- ea: `0x1800b0684`
- end: `0x1800b0759`
- name: `_MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore_::_1_::catch$15`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009b04`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b0684`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b069d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b069d`

## string_xrefs

- `0x1800b0707`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`

## pseudocode

```c
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v5 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, a2, a3, a4);
    CallStackTracing::s_wpInstance = v6;
    if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
    {
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
      CallStackContext::TraceFailure(
        ThreadRelativeContext,
        "MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore",
        1120,
        -2147024882);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      126,
      &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
      *(_QWORD *)(a2 + 104),
      -2147024882);
  return 0;
}

```

## disassembly

```asm
0x1800b0684  mov     [rsp+arg_8], rdx
0x1800b0689  push    rbp
0x1800b068a  sub     rsp, 30h
0x1800b068e  mov     rbp, rdx
0x1800b0691  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0698  test    rcx, rcx
0x1800b069b  jnz     short loc_1800B06E4
0x1800b069d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b06a4  nop     dword ptr [rax+rax+00h]
0x1800b06a9  mov     rcx, rax
0x1800b06ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b06b3  test    rax, rax
0x1800b06b6  jnz     short loc_1800B06C8
0x1800b06b8  lea     rcx, qword_1800DBF70
0x1800b06bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b06c6  jmp     short loc_1800B06E4
0x1800b06c8  mov     rax, [rax]
0x1800b06cb  mov     edx, 7F0h
0x1800b06d0  mov     rax, [rax+8]
0x1800b06d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06d9  test    eax, eax
0x1800b06db  jz      short loc_1800B06B8
0x1800b06dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b06e4  cmp     byte ptr [rcx+8], 0
0x1800b06e8  jz      short loc_1800B0716
0x1800b06ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b06ef  cmp     dword ptr [rax+7CCh], 8007000Eh
0x1800b06f9  jz      short loc_1800B0716
0x1800b06fb  mov     r9d, 8007000Eh; int
0x1800b0701  mov     r8d, 460h; int
0x1800b0707  lea     rdx, aMkvmfsourcelib_34; "MkvMfSourceLib::MkvMfSource::CreateRead"...
0x1800b070e  mov     rcx, rax; this
0x1800b0711  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0716  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b071d  jb      short loc_1800B0748
0x1800b071f  mov     edx, 7Eh ; '~'
0x1800b0724  mov     [rsp+38h+var_18], 8007000Eh
0x1800b072c  mov     r9, [rbp+68h]
0x1800b0730  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800b0737  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b073e  mov     rcx, [rcx+10h]
0x1800b0742  call    WPP_SF_qD
0x1800b0747  nop
0x1800b0748  mov     rax, 0
0x1800b0752  add     rsp, 30h
0x1800b0756  pop     rbp
0x1800b0757  retn
```
