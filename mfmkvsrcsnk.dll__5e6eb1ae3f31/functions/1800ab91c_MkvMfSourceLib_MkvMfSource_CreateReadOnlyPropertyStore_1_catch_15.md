# _MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore_::_1_::catch$15

- ea: `0x1800ab91c`
- end: `0x1800ab9eb`
- name: `_MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore_::_1_::catch$15`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800097f0`
- `0x180020d84`
- `0x180071330`
- `0x1800ab91c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab935`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ab935`

## string_xrefs

- `0x1800ab999`: `MkvMfSourceLib::MkvMfSource::CreateReadOnlyPropertyStore`

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
      v5 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800ab91c  mov     [rsp+arg_8], rdx
0x1800ab921  push    rbp
0x1800ab922  sub     rsp, 30h
0x1800ab926  mov     rbp, rdx
0x1800ab929  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab930  test    rcx, rcx
0x1800ab933  jnz     short loc_1800AB976
0x1800ab935  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ab93b  mov     rcx, rax
0x1800ab93e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab945  test    rax, rax
0x1800ab948  jnz     short loc_1800AB95A
0x1800ab94a  lea     rcx, qword_1800D6F70
0x1800ab951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab958  jmp     short loc_1800AB976
0x1800ab95a  mov     rax, [rax]
0x1800ab95d  mov     edx, 7F0h
0x1800ab962  mov     rax, [rax+8]
0x1800ab966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab96b  test    eax, eax
0x1800ab96d  jz      short loc_1800AB94A
0x1800ab96f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab976  cmp     byte ptr [rcx+8], 0
0x1800ab97a  jz      short loc_1800AB9A8
0x1800ab97c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab981  cmp     dword ptr [rax+7CCh], 8007000Eh
0x1800ab98b  jz      short loc_1800AB9A8
0x1800ab98d  mov     r9d, 8007000Eh; int
0x1800ab993  mov     r8d, 460h; int
0x1800ab999  lea     rdx, aMkvmfsourcelib_34; "MkvMfSourceLib::MkvMfSource::CreateRead"...
0x1800ab9a0  mov     rcx, rax; this
0x1800ab9a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab9a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ab9af  jb      short loc_1800AB9DA
0x1800ab9b1  mov     edx, 7Eh ; '~'
0x1800ab9b6  mov     [rsp+38h+var_18], 8007000Eh
0x1800ab9be  mov     r9, [rbp+68h]
0x1800ab9c2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800ab9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab9d0  mov     rcx, [rcx+10h]
0x1800ab9d4  call    WPP_SF_qD
0x1800ab9d9  nop
0x1800ab9da  mov     rax, 0
0x1800ab9e4  add     rsp, 30h
0x1800ab9e8  pop     rbp
0x1800ab9e9  retn
```
