# MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)

- ea: `0x18001065c`
- end: `0x180010939`
- name: `?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z`
- size: `733`
- prototype: `__int64 __fastcall(struct IMFByteStream *, struct IMFTelemetrySession *, struct MkvMfSourceLib::MkvMfSource **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000aca0`
- `0x18004dfa0`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000bf60`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18001065c`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001079a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001086e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001079a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001086e`

## string_xrefs

- `0x18001067e`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x18001071f`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x1800107fe`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x1800108d2`: `MkvMfSourceLib::MkvMfSource::CreateSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateSource(
        struct IMFByteStream *a1,
        struct IMFTelemetrySession *a2,
        struct MkvMfSourceLib::MkvMfSource **a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct MkvMfSourceLib::MkvMfSource *v22; // rax
  _QWORD v24[4]; // [rsp+30h] [rbp-20h] BYREF
  struct IMFByteStream *v25; // [rsp+70h] [rbp+20h] BYREF
  char v26; // [rsp+80h] [rbp+30h] BYREF
  int v27; // [rsp+88h] [rbp+38h] BYREF

  v25 = a1;
  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "MkvMfSourceLib::MkvMfSource::CreateSource", 47);
  v24[1] = 0;
  v24[2] = &v27;
  if ( a3 )
  {
    v24[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    v27 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfSource,MkvMfSourceLib::MkvMfSource,IMFByteStream * &>(
            v24,
            &v25);
    if ( v27 >= 0 )
    {
      if ( v24[0] )
      {
        (*(void (__fastcall **)(__int64, struct IMFTelemetrySession *))(*(_QWORD *)(v24[0] + 56LL) + 32LL))(
          v24[0] + 56LL,
          a2);
        v22 = (struct MkvMfSourceLib::MkvMfSource *)v24[0];
        v24[0] = 0;
        *a3 = v22;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
        v11 = 0;
        goto LABEL_41;
      }
      v27 = -2147024882;
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( v27 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v27 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfSource::CreateSource", 56, v27);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 13;
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
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( v27 < 0 && *((_DWORD *)v17 + 499) != v27 )
          CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::CreateSource", 55, v27);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 12;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, 0, v27);
LABEL_27:
    v11 = v27;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    goto LABEL_41;
  }
  v27 = -2147467261;
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( v27 < 0 && *((_DWORD *)v10 + 499) != v27 )
      CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfSource::CreateSource", 51, v27);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, 0, v27);
  v11 = v27;
LABEL_41:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return v11;
}

```

## disassembly

```asm
0x18001065c  mov     [rsp-18h+arg_0], rcx
0x180010661  push    rbp
0x180010662  push    rbx
0x180010663  push    rdi
0x180010664  mov     rbp, rsp
0x180010667  sub     rsp, 50h
0x18001066b  mov     rbx, r8
0x18001066e  mov     rdi, rdx
0x180010671  mov     [rbp+arg_18], 0
0x180010678  mov     r8d, 2Fh ; '/'; int
0x18001067e  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010685  lea     rcx, [rbp+arg_10]; this
0x180010689  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001068e  nop
0x18001068f  mov     [rbp+var_18], 0
0x180010697  lea     rax, [rbp+arg_18]
0x18001069b  mov     [rbp+var_10], rax
0x18001069f  test    rbx, rbx
0x1800106a2  jnz     loc_180010765
0x1800106a8  mov     [rbp+arg_18], 80004003h
0x1800106af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106b6  test    rcx, rcx
0x1800106b9  jnz     short loc_1800106FC
0x1800106bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800106c1  mov     rcx, rax
0x1800106c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106cb  test    rax, rax
0x1800106ce  jz      short loc_1800106EE
0x1800106d0  mov     rax, [rax]
0x1800106d3  mov     edx, 7F0h
0x1800106d8  mov     rax, [rax+8]
0x1800106dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e1  test    eax, eax
0x1800106e3  jz      short loc_1800106EE
0x1800106e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106ec  jmp     short loc_1800106FC
0x1800106ee  lea     rcx, qword_1800D6F70; this
0x1800106f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106fc  cmp     byte ptr [rcx+8], 0
0x180010700  jz      short loc_18001072E
0x180010702  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010707  mov     r9d, [rbp+arg_18]; int
0x18001070b  test    r9d, r9d
0x18001070e  jns     short loc_18001072E
0x180010710  cmp     [rax+7CCh], r9d
0x180010717  jz      short loc_18001072E
0x180010719  mov     r8d, 33h ; '3'; int
0x18001071f  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010726  mov     rcx, rax; this
0x180010729  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001072e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010735  jb      short loc_18001075D
0x180010737  mov     edx, 0Bh
0x18001073c  mov     eax, [rbp+arg_18]
0x18001073f  mov     [rsp+50h+var_30], eax
0x180010743  xor     r9d, r9d
0x180010746  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001074d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010754  mov     rcx, [rcx+10h]
0x180010758  call    WPP_SF_qD
0x18001075d  mov     ebx, [rbp+arg_18]
0x180010760  jmp     loc_180010849
0x180010765  mov     [rbp+var_20], 0
0x18001076d  lea     rcx, [rbp+var_20]
0x180010771  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010776  lea     rdx, [rbp+arg_0]
0x18001077a  lea     rcx, [rbp+var_20]
0x18001077e  call    ??$MakeAndInitialize@VMkvMfSource@MkvMfSourceLib@@V12@AEAPEAUIMFByteStream@@@Details@WRL@Microsoft@@YAJPEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEAUIMFByteStream@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfSource,MkvMfSourceLib::MkvMfSource,IMFByteStream * &>(MkvMfSourceLib::MkvMfSource * *,IMFByteStream * &)
0x180010783  mov     [rbp+arg_18], eax
0x180010786  test    eax, eax
0x180010788  jns     loc_18001084E
0x18001078e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010795  test    rcx, rcx
0x180010798  jnz     short loc_1800107DB
0x18001079a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800107a0  mov     rcx, rax
0x1800107a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800107aa  test    rax, rax
0x1800107ad  jz      short loc_1800107CD
0x1800107af  mov     rax, [rax]
0x1800107b2  mov     edx, 7F0h
0x1800107b7  mov     rax, [rax+8]
0x1800107bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c0  test    eax, eax
0x1800107c2  jz      short loc_1800107CD
0x1800107c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800107cb  jmp     short loc_1800107DB
0x1800107cd  lea     rcx, qword_1800D6F70; this
0x1800107d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800107db  cmp     byte ptr [rcx+8], 0
0x1800107df  jz      short loc_18001080D
0x1800107e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800107e6  mov     r9d, [rbp+arg_18]; int
0x1800107ea  test    r9d, r9d
0x1800107ed  jns     short loc_18001080D
0x1800107ef  cmp     [rax+7CCh], r9d
0x1800107f6  jz      short loc_18001080D
0x1800107f8  mov     r8d, 37h ; '7'; int
0x1800107fe  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010805  mov     rcx, rax; this
0x180010808  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001080d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010814  jb      short loc_18001083C
0x180010816  mov     edx, 0Ch
0x18001081b  mov     eax, [rbp+arg_18]
0x18001081e  mov     [rsp+50h+var_30], eax
0x180010822  xor     r9d, r9d
0x180010825  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001082c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010833  mov     rcx, [rcx+10h]
0x180010837  call    WPP_SF_qD
0x18001083c  mov     ebx, [rbp+arg_18]
0x18001083f  lea     rcx, [rbp+var_20]
0x180010843  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010848  nop
0x180010849  jmp     loc_180010926
0x18001084e  mov     rax, [rbp+var_20]
0x180010852  test    rax, rax
0x180010855  jnz     loc_1800108F8
0x18001085b  mov     [rbp+arg_18], 8007000Eh
0x180010862  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010869  test    rcx, rcx
0x18001086c  jnz     short loc_1800108AF
0x18001086e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010874  mov     rcx, rax
0x180010877  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001087e  test    rax, rax
0x180010881  jz      short loc_1800108A1
0x180010883  mov     rax, [rax]
0x180010886  mov     edx, 7F0h
0x18001088b  mov     rax, [rax+8]
0x18001088f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010894  test    eax, eax
0x180010896  jz      short loc_1800108A1
0x180010898  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001089f  jmp     short loc_1800108AF
0x1800108a1  lea     rcx, qword_1800D6F70; this
0x1800108a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800108af  cmp     byte ptr [rcx+8], 0
0x1800108b3  jz      short loc_1800108E1
0x1800108b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800108ba  mov     r9d, [rbp+arg_18]; int
0x1800108be  test    r9d, r9d
0x1800108c1  jns     short loc_1800108E1
0x1800108c3  cmp     [rax+7CCh], r9d
0x1800108ca  jz      short loc_1800108E1
0x1800108cc  mov     r8d, 38h ; '8'; int
0x1800108d2  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x1800108d9  mov     rcx, rax; this
0x1800108dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800108e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800108e8  jb      loc_18001083C
0x1800108ee  mov     edx, 0Dh
0x1800108f3  jmp     loc_18001081B
0x1800108f8  lea     rcx, [rax+38h]
0x1800108fc  mov     rax, [rcx]
0x1800108ff  mov     rdx, rdi
0x180010902  mov     rax, [rax+20h]
0x180010906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001090b  mov     rax, [rbp+var_20]
0x18001090f  mov     [rbp+var_20], 0
0x180010917  mov     [rbx], rax
0x18001091a  lea     rcx, [rbp+var_20]
0x18001091e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010923  nop
0x180010924  xor     ebx, ebx
0x180010926  lea     rcx, [rbp+arg_10]; this
0x18001092a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001092f  mov     eax, ebx
0x180010931  add     rsp, 50h
0x180010935  pop     rdi
0x180010936  pop     rbx
0x180010937  pop     rbp
0x180010938  retn
```
