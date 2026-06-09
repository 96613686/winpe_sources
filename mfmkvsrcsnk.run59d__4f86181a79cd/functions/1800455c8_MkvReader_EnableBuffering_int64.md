# MkvReader::EnableBuffering(__int64)

- ea: `0x1800455c8`
- end: `0x1800458a6`
- name: `?EnableBuffering@MkvReader@@QEBAJ_J@Z`
- size: `734`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001fbf0`
- `0x180020110`

## callees

- `0x180002e54`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180043418`
- `0x1800455c8`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045721`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800457f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045721`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800457f7`

## string_xrefs

- `0x1800456e6`: `MkvReader::EnableBuffering`
- `0x180045784`: `MkvReader::EnableBuffering`
- `0x18004585a`: `MkvReader::EnableBuffering`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::EnableBuffering(MkvReader *this, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rcx
  double v8; // xmm1_8
  __int64 v9; // rcx
  double v10; // xmm0_8
  __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD v26[2]; // [rsp+30h] [rbp-40h] BYREF
  int *v27; // [rsp+40h] [rbp-30h]
  int v28; // [rsp+48h] [rbp-28h]
  __int64 v29; // [rsp+50h] [rbp-20h]
  __int64 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  int v32; // [rsp+68h] [rbp-8h]
  char v33; // [rsp+90h] [rbp+20h] BYREF
  __int64 v34; // [rsp+A0h] [rbp+30h] BYREF
  int v35; // [rsp+A8h] [rbp+38h] BYREF
  int v36; // [rsp+ACh] [rbp+3Ch]

  v34 = 0;
  Microsoft::WRL::ComPtr<IMFByteStream>::As<IMFByteStreamBuffering>((char *)this + 16, &v34);
  if ( v34 )
  {
    memset_0(v26, 0, 0x40u);
    v5 = v31;
    if ( a2 >= 0 )
      v5 = a2;
    v31 = v5;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), v26);
    v7 = v26[0];
    if ( v6 < 0 )
      v7 = -1;
    v26[0] = v7;
    v26[1] = v7;
    if ( v7 && a2 > 0 )
    {
      v8 = (double)(int)a2 / 10000000.0;
      if ( v8 > 0.0 )
      {
        v9 = 8 * v7;
        if ( v9 < 0 )
          v10 = (double)(int)(v9 & 1 | ((unsigned __int64)v9 >> 1))
              + (double)(int)(v9 & 1 | ((unsigned __int64)v9 >> 1));
        else
          v10 = (double)(int)v9;
        v35 = (int)(v10 / v8);
        v36 = 10000;
        v27 = &v35;
        v28 = 1;
      }
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = 0;
    v30 = 0;
    v32 = 1065353216;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "MkvReader::EnableBuffering", 189);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v34 + 24LL))(v34, v26);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 32LL))(v34, 1);
      if ( v12 >= 0 )
      {
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
        v4 = 0;
        goto LABEL_40;
      }
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::EnableBuffering", 190, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 17;
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
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
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v12 )
          CallStackContext::TraceFailure(v17, "MkvReader::EnableBuffering", 189, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 16;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v12);
LABEL_27:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
    v4 = v12;
    goto LABEL_40;
  }
  v4 = 1;
LABEL_40:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  return v4;
}

```

## disassembly

```asm
0x1800455c8  mov     [rsp-18h+arg_8], rbx
0x1800455cd  push    rbp
0x1800455ce  push    rsi
0x1800455cf  push    rdi
0x1800455d0  mov     rbp, rsp
0x1800455d3  sub     rsp, 70h
0x1800455d7  mov     rdi, rdx
0x1800455da  mov     rsi, rcx
0x1800455dd  mov     [rbp+arg_10], 0
0x1800455e5  lea     rdx, [rbp+arg_10]
0x1800455e9  add     rcx, 10h
0x1800455ed  call    ??$As@UIMFByteStreamBuffering@@@?$ComPtr@UIMFByteStream@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMFByteStreamBuffering@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFByteStream>::As<IMFByteStreamBuffering>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFByteStreamBuffering>>)
0x1800455f2  cmp     [rbp+arg_10], 0
0x1800455f7  jnz     short loc_180045603
0x1800455f9  mov     ebx, 1
0x1800455fe  jmp     loc_18004588A
0x180045603  xor     edx, edx; Val
0x180045605  lea     r8d, [rdx+40h]; Size
0x180045609  lea     rcx, [rbp+var_40]; void *
0x18004560d  call    memset_0
0x180045612  mov     rax, [rbp+var_10]
0x180045616  test    rdi, rdi
0x180045619  cmovns  rax, rdi
0x18004561d  mov     [rbp+var_10], rax
0x180045621  mov     rcx, [rsi+10h]
0x180045625  mov     rax, [rcx]
0x180045628  lea     rdx, [rbp+var_40]
0x18004562c  mov     rax, [rax+20h]
0x180045630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045635  mov     rcx, [rbp+var_40]
0x180045639  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004563d  test    eax, eax
0x18004563f  cmovs   rcx, rdx
0x180045643  mov     [rbp+var_40], rcx
0x180045647  mov     [rbp+var_38], rcx
0x18004564b  lea     ebx, [rdx+2]
0x18004564e  test    rcx, rcx
0x180045651  jz      short loc_1800456BA
0x180045653  test    rdi, rdi
0x180045656  jle     short loc_1800456BA
0x180045658  xorps   xmm1, xmm1
0x18004565b  cvtsi2sd xmm1, rdi
0x180045660  divsd   xmm1, cs:__real@416312d000000000
0x180045668  comisd  xmm1, cs:__real@0000000000000000
0x180045670  jbe     short loc_1800456C9
0x180045672  shl     rcx, 3
0x180045676  xorps   xmm0, xmm0
0x180045679  test    rcx, rcx
0x18004567c  js      short loc_180045685
0x18004567e  cvtsi2sd xmm0, rcx
0x180045683  jmp     short loc_18004569A
0x180045685  mov     rax, rcx
0x180045688  shr     rax, 1
0x18004568b  and     rcx, rbx
0x18004568e  or      rax, rcx
0x180045691  cvtsi2sd xmm0, rax
0x180045696  addsd   xmm0, xmm0
0x18004569a  divsd   xmm0, xmm1
0x18004569e  cvttsd2si rax, xmm0
0x1800456a3  mov     [rbp+arg_18], eax
0x1800456a6  mov     [rbp+arg_1C], 2710h
0x1800456ad  lea     rax, [rbp+arg_18]
0x1800456b1  mov     [rbp+var_30], rax
0x1800456b5  mov     [rbp+var_28], ebx
0x1800456b8  jmp     short loc_1800456C9
0x1800456ba  mov     [rbp+var_30], 0
0x1800456c2  mov     [rbp+var_28], 0
0x1800456c9  mov     [rbp+var_20], 0
0x1800456d1  mov     [rbp+var_18], 0
0x1800456d9  mov     [rbp+var_8], 3F800000h
0x1800456e0  mov     r8d, 0BDh; int
0x1800456e6  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x1800456ed  lea     rcx, [rbp+arg_0]; this
0x1800456f1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800456f6  nop
0x1800456f7  mov     rcx, [rbp+arg_10]
0x1800456fb  mov     rax, [rcx]
0x1800456fe  lea     rdx, [rbp+var_40]
0x180045702  mov     rax, [rax+18h]
0x180045706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004570b  mov     edi, eax
0x18004570d  test    eax, eax
0x18004570f  jns     loc_1800457CF
0x180045715  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004571c  test    rcx, rcx
0x18004571f  jnz     short loc_180045768
0x180045721  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045728  nop     dword ptr [rax+rax+00h]
0x18004572d  mov     rcx, rax
0x180045730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045737  test    rax, rax
0x18004573a  jz      short loc_18004575A
0x18004573c  mov     rax, [rax]
0x18004573f  mov     edx, 7F0h
0x180045744  mov     rax, [rax+8]
0x180045748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004574d  test    eax, eax
0x18004574f  jz      short loc_18004575A
0x180045751  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045758  jmp     short loc_180045768
0x18004575a  lea     rcx, qword_1800DBF70; this
0x180045761  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045768  cmp     byte ptr [rcx+8], 0
0x18004576c  jz      short loc_180045793
0x18004576e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045773  cmp     [rax+7CCh], edi
0x180045779  jz      short loc_180045793
0x18004577b  mov     r9d, edi; int
0x18004577e  mov     r8d, 0BDh; int
0x180045784  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x18004578b  mov     rcx, rax; this
0x18004578e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045793  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180045799  jb      short loc_1800457BF
0x18004579b  mov     edx, 10h
0x1800457a0  mov     [rsp+70h+var_50], edi
0x1800457a4  mov     r9, rsi
0x1800457a7  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800457ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457b5  mov     rcx, [rcx+10h]
0x1800457b9  call    WPP_SF_qD
0x1800457be  nop
0x1800457bf  lea     rcx, [rbp+arg_0]; this
0x1800457c3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800457c8  mov     ebx, edi
0x1800457ca  jmp     loc_18004588A
0x1800457cf  mov     rcx, [rbp+arg_10]
0x1800457d3  mov     rax, [rcx]
0x1800457d6  mov     edx, ebx
0x1800457d8  mov     rax, [rax+20h]
0x1800457dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457e1  mov     edi, eax
0x1800457e3  test    eax, eax
0x1800457e5  jns     loc_18004587F
0x1800457eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800457f2  test    rcx, rcx
0x1800457f5  jnz     short loc_18004583E
0x1800457f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800457fe  nop     dword ptr [rax+rax+00h]
0x180045803  mov     rcx, rax
0x180045806  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004580d  test    rax, rax
0x180045810  jz      short loc_180045830
0x180045812  mov     rax, [rax]
0x180045815  mov     edx, 7F0h
0x18004581a  mov     rax, [rax+8]
0x18004581e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045823  test    eax, eax
0x180045825  jz      short loc_180045830
0x180045827  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004582e  jmp     short loc_18004583E
0x180045830  lea     rcx, qword_1800DBF70; this
0x180045837  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004583e  cmp     byte ptr [rcx+8], 0
0x180045842  jz      short loc_180045869
0x180045844  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045849  cmp     [rax+7CCh], edi
0x18004584f  jz      short loc_180045869
0x180045851  mov     r9d, edi; int
0x180045854  mov     r8d, 0BEh; int
0x18004585a  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x180045861  mov     rcx, rax; this
0x180045864  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045869  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x18004586f  jb      loc_1800457BF
0x180045875  mov     edx, 11h
0x18004587a  jmp     loc_1800457A0
0x18004587f  lea     rcx, [rbp+arg_0]; this
0x180045883  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045888  xor     ebx, ebx
0x18004588a  lea     rcx, [rbp+arg_10]
0x18004588e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045893  mov     eax, ebx
0x180045895  mov     rbx, [rsp+70h+arg_8]
0x18004589d  add     rsp, 70h
0x1800458a1  pop     rdi
0x1800458a2  pop     rsi
0x1800458a3  pop     rbp
0x1800458a4  retn
```
