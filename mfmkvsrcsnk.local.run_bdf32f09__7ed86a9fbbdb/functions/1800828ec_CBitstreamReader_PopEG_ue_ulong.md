# CBitstreamReader::PopEG_ue(ulong *)

- ea: `0x1800828ec`
- end: `0x180082b66`
- name: `?PopEG_ue@CBitstreamReader@@QEAAJPEAK@Z`
- size: `634`
- prototype: `__int64 __fastcall(CBitstreamReader *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18007bb1c`
- `0x18007c1c4`
- `0x180082718`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800828ec`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800829fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082ab9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082932`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800829fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180082ab9`

## string_xrefs

- `0x180082909`: `CBitstreamReader::PopEG_ue`
- `0x18008298e`: `CBitstreamReader::PopEG_ue`
- `0x180082a52`: `CBitstreamReader::PopEG_ue`
- `0x180082b10`: `CBitstreamReader::PopEG_ue`

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
            v17 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v23 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids, this, v9);
    }
  }
LABEL_39:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800828ec  mov     [rsp+arg_0], rbx
0x1800828f1  mov     [rsp+arg_10], rbp
0x1800828f6  push    rsi
0x1800828f7  push    rdi
0x1800828f8  push    r14
0x1800828fa  sub     rsp, 30h
0x1800828fe  mov     r14, rdx
0x180082901  mov     rbp, rcx
0x180082904  mov     edi, 12Ch
0x180082909  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x180082910  mov     r8d, edi; int
0x180082913  lea     rcx, [rsp+48h+arg_8]; this
0x180082918  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008291d  test    r14, r14
0x180082920  jnz     loc_1800829BA
0x180082926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008292d  test    rcx, rcx
0x180082930  jnz     short loc_180082973
0x180082932  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082938  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008293f  mov     rcx, rax
0x180082942  test    rax, rax
0x180082945  jz      short loc_180082965
0x180082947  mov     rax, [rax]
0x18008294a  mov     edx, 7F0h
0x18008294f  mov     rax, [rax+8]
0x180082953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082958  test    eax, eax
0x18008295a  jz      short loc_180082965
0x18008295c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082963  jmp     short loc_180082973
0x180082965  lea     rcx, qword_1800D6F70; this
0x18008296c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082973  cmp     byte ptr [rcx+8], 0
0x180082977  mov     ebx, 80004003h
0x18008297c  jz      short loc_1800829A0
0x18008297e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082983  cmp     [rax+7CCh], ebx
0x180082989  jz      short loc_1800829A0
0x18008298b  mov     r9d, ebx; int
0x18008298e  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x180082995  mov     r8d, edi; int
0x180082998  mov     rcx, rax; this
0x18008299b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800829a0  mov     edi, 1
0x1800829a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800829ac  jb      loc_180082B47
0x1800829b2  lea     edx, [rdi+16h]
0x1800829b5  jmp     loc_180082A79
0x1800829ba  or      esi, 0FFFFFFFFh
0x1800829bd  mov     [rsp+48h+arg_8], 0
0x1800829c5  xor     eax, eax
0x1800829c7  lea     edi, [rsi+2]
0x1800829ca  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x1800829cf  mov     rcx, rbp; this
0x1800829d2  test    eax, eax
0x1800829d4  jnz     loc_180082A9C
0x1800829da  mov     edx, edi; int
0x1800829dc  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x1800829e1  mov     ebx, eax
0x1800829e3  test    eax, eax
0x1800829e5  js      short loc_1800829EF
0x1800829e7  mov     eax, [rsp+48h+arg_8]
0x1800829eb  add     esi, edi
0x1800829ed  jmp     short loc_1800829CA
0x1800829ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800829f6  test    rcx, rcx
0x1800829f9  jnz     short loc_180082A3C
0x1800829fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a08  mov     rcx, rax
0x180082a0b  test    rax, rax
0x180082a0e  jz      short loc_180082A2E
0x180082a10  mov     rax, [rax]
0x180082a13  mov     edx, 7F0h
0x180082a18  mov     rax, [rax+8]
0x180082a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a21  test    eax, eax
0x180082a23  jz      short loc_180082A2E
0x180082a25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a2c  jmp     short loc_180082A3C
0x180082a2e  lea     rcx, qword_1800D6F70; this
0x180082a35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082a3c  cmp     byte ptr [rcx+8], 0
0x180082a40  jz      short loc_180082A67
0x180082a42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082a47  cmp     [rax+7CCh], ebx
0x180082a4d  jz      short loc_180082A67
0x180082a4f  mov     r9d, ebx; int
0x180082a52  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x180082a59  mov     r8d, 133h; int
0x180082a5f  mov     rcx, rax; this
0x180082a62  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082a67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180082a6e  jb      loc_180082B47
0x180082a74  mov     edx, 18h
0x180082a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a80  lea     r8, WPP_4a034bfb94a036f1275e68247e1b0a55_Traceguids
0x180082a87  mov     r9, rbp
0x180082a8a  mov     [rsp+48h+var_28], ebx
0x180082a8e  mov     rcx, [rcx+10h]
0x180082a92  call    WPP_SF_qD
0x180082a97  jmp     loc_180082B47
0x180082a9c  mov     edx, esi; int
0x180082a9e  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x180082aa3  mov     ebx, eax
0x180082aa5  test    eax, eax
0x180082aa7  jns     loc_180082B38
0x180082aad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082ab4  test    rcx, rcx
0x180082ab7  jnz     short loc_180082AFA
0x180082ab9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180082abf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180082ac6  mov     rcx, rax
0x180082ac9  test    rax, rax
0x180082acc  jz      short loc_180082AEC
0x180082ace  mov     rax, [rax]
0x180082ad1  mov     edx, 7F0h
0x180082ad6  mov     rax, [rax+8]
0x180082ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082adf  test    eax, eax
0x180082ae1  jz      short loc_180082AEC
0x180082ae3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180082aea  jmp     short loc_180082AFA
0x180082aec  lea     rcx, qword_1800D6F70; this
0x180082af3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180082afa  cmp     byte ptr [rcx+8], 0
0x180082afe  jz      short loc_180082B25
0x180082b00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180082b05  cmp     [rax+7CCh], ebx
0x180082b0b  jz      short loc_180082B25
0x180082b0d  mov     r9d, ebx; int
0x180082b10  lea     rdx, aCbitstreamread_1; "CBitstreamReader::PopEG_ue"
0x180082b17  mov     r8d, 136h; int
0x180082b1d  mov     rcx, rax; this
0x180082b20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180082b25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180082b2c  jb      short loc_180082B47
0x180082b2e  mov     edx, 19h
0x180082b33  jmp     loc_180082A79
0x180082b38  mov     ecx, esi
0x180082b3a  shl     edi, cl
0x180082b3c  mov     ecx, [rsp+48h+arg_8]
0x180082b40  dec     ecx
0x180082b42  add     ecx, edi
0x180082b44  mov     [r14], ecx
0x180082b47  lea     rcx, [rsp+48h+arg_8]; this
0x180082b4c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180082b51  mov     rbp, [rsp+48h+arg_10]
0x180082b56  mov     eax, ebx
0x180082b58  mov     rbx, [rsp+48h+arg_0]
0x180082b5d  add     rsp, 30h
0x180082b61  pop     r14
0x180082b63  pop     rdi
0x180082b64  pop     rsi
0x180082b65  retn
```
