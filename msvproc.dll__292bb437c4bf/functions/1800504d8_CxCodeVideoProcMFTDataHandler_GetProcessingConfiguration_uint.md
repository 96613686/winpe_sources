# CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration(uint *)

- ea: `0x1800504d8`
- end: `0x1800507d1`
- name: `?GetProcessingConfiguration@CxCodeVideoProcMFTDataHandler@@QEAAJPEAI@Z`
- size: `761`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180042440`

## callees

- `0x180007040`
- `0x180007148`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800157b0`
- `0x18001e284`
- `0x18002336c`
- `0x18003639c`
- `0x1800504d8`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800505c3`

## string_xrefs

- `0x180050524`: `CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration`
- `0x18005061a`: `CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration(
        CxCodeVideoProcMFTDataHandler *this,
        unsigned int *a2,
        const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *a3)
{
  int v6; // ebx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v8; // ebx
  __int128 v9; // xmm0
  BOOL IsD3DMode; // eax
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  int v14; // r10d
  int v15; // r10d
  _BYTE v16[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19[2]; // [rsp+48h] [rbp-18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v6 = 0;
  if ( *((_DWORD *)this + 34) )
    goto LABEL_20;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v16,
    "CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration",
    6452);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v9 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      v19);
    *((_DWORD *)ThreadRelativeContext + 504) = v8;
    *((_OWORD *)ThreadRelativeContext + 125) = v9;
  }
  IsD3DMode = CxCodeVideoProcMFTDataHandler::IsD3DMode(this);
  v6 = CxCodeVideoProcMFTDataHandler::ConfigureConversions(this, *((_DWORD *)this + 67), IsD3DMode);
  if ( v6 >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v16);
LABEL_20:
    MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsColorSpaceConversionRequired(
      (CxCodeVideoProcMFTDataHandler *)((char *)this + 536),
      (CxCodeVideoProcMFTDataHandler *)((char *)this + 780),
      a3);
    if ( !(unsigned int)CxCodeVideoProcMFTDataHandler::IsNonFRCMode(this) )
    {
      v18 = 0;
      v17 = 0;
      CxCodeVideoProcSampleInfo::GetTime((CxCodeVideoProcMFTDataHandler *)((char *)this + 384), v19, &v18);
      CxCodeVideoProcSampleInfo::GetTime((CxCodeVideoProcMFTDataHandler *)((char *)this + 832), v19, &v17);
      v14 = (v18 != v17 ? 0x100 : 0) | v15;
    }
    *a2 = v14;
    return (unsigned int)v6;
  }
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != v6 )
      CallStackContext::TraceFailure(v13, "CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration", 6452, v6);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 307, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v6);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800504d8  mov     [rsp-18h+arg_10], rbx
0x1800504dd  mov     [rsp-18h+arg_18], rsi
0x1800504e2  push    rbp
0x1800504e3  push    rdi
0x1800504e4  push    r14
0x1800504e6  mov     rbp, rsp
0x1800504e9  sub     rsp, 60h
0x1800504ed  mov     rax, cs:__security_cookie
0x1800504f4  xor     rax, rsp
0x1800504f7  mov     [rbp+var_8], rax
0x1800504fb  mov     r14, rdx
0x1800504fe  mov     rsi, rcx
0x180050501  test    rdx, rdx
0x180050504  jnz     short loc_180050510
0x180050506  mov     eax, 80004003h
0x18005050b  jmp     loc_1800507B0
0x180050510  xor     ebx, ebx
0x180050512  cmp     [rcx+88h], ebx
0x180050518  jnz     loc_180050672
0x18005051e  mov     r8d, 1934h; int
0x180050524  lea     rdx, aCxcodevideopro_135; "CxCodeVideoProcMFTDataHandler::GetProce"...
0x18005052b  lea     rcx, [rbp+var_30]; this
0x18005052f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050534  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005053b  cmp     [rcx+8], bl
0x18005053e  jz      short loc_180050594
0x180050540  cmp     [rsi+0C20h], rbx
0x180050547  jz      short loc_180050594
0x180050549  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005054e  mov     rcx, [rsi+0C20h]
0x180050555  mov     rdi, rax
0x180050558  mov     rax, [rcx]
0x18005055b  mov     rax, [rax+128h]
0x180050562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050567  mov     rcx, [rsi+0C20h]
0x18005056e  lea     rdx, [rbp+var_18]
0x180050572  mov     ebx, eax
0x180050574  mov     rax, [rcx]
0x180050577  mov     rax, [rax+118h]
0x18005057e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050583  movups  xmm0, xmmword ptr [rax]
0x180050586  mov     [rdi+7E0h], ebx
0x18005058c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180050594  mov     rcx, rsi; this
0x180050597  call    ?IsD3DMode@CxCodeVideoProcMFTDataHandler@@QEAAHXZ; CxCodeVideoProcMFTDataHandler::IsD3DMode(void)
0x18005059c  mov     edx, [rsi+10Ch]; int
0x1800505a2  mov     r8d, eax; int
0x1800505a5  mov     rcx, rsi; this
0x1800505a8  call    ?ConfigureConversions@CxCodeVideoProcMFTDataHandler@@AEAAJHH@Z; CxCodeVideoProcMFTDataHandler::ConfigureConversions(int,int)
0x1800505ad  mov     ebx, eax
0x1800505af  test    eax, eax
0x1800505b1  jns     loc_180050669
0x1800505b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505be  test    rcx, rcx
0x1800505c1  jnz     short loc_180050604
0x1800505c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800505c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505d0  mov     rcx, rax
0x1800505d3  test    rax, rax
0x1800505d6  jz      short loc_1800505F6
0x1800505d8  mov     rax, [rax]
0x1800505db  mov     edx, 7F0h
0x1800505e0  mov     rax, [rax+8]
0x1800505e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505e9  test    eax, eax
0x1800505eb  jz      short loc_1800505F6
0x1800505ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800505f4  jmp     short loc_180050604
0x1800505f6  lea     rcx, qword_180153440; this
0x1800505fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050604  cmp     byte ptr [rcx+8], 0
0x180050608  jz      short loc_18005062F
0x18005060a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005060f  cmp     [rax+7CCh], ebx
0x180050615  jz      short loc_18005062F
0x180050617  mov     r9d, ebx; int
0x18005061a  lea     rdx, aCxcodevideopro_135; "CxCodeVideoProcMFTDataHandler::GetProce"...
0x180050621  mov     r8d, 1934h; int
0x180050627  mov     rcx, rax; this
0x18005062a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005062f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050636  jb      short loc_18005065B
0x180050638  mov     rcx, cs:WPP_GLOBAL_Control
0x18005063f  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180050646  mov     edx, 133h
0x18005064b  mov     [rsp+60h+var_40], ebx
0x18005064f  mov     r9, rsi
0x180050652  mov     rcx, [rcx+10h]
0x180050656  call    WPP_SF_qD
0x18005065b  lea     rcx, [rbp+var_30]; this
0x18005065f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050664  jmp     loc_1800507AE
0x180050669  lea     rcx, [rbp+var_30]; this
0x18005066d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050672  lea     rdx, [rsi+30Ch]; struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *
0x180050679  lea     rcx, [rsi+218h]; this
0x180050680  call    ?IsColorSpaceConversionRequired@MFMEDIATYPEUtilsHelper@MFMEDIATYPEUtils@@YAHAEBUVideoColorSpaceAttributes@2@0@Z; MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsColorSpaceConversionRequired(MFMEDIATYPEUtils::VideoColorSpaceAttributes const &,MFMEDIATYPEUtils::VideoColorSpaceAttributes const &)
0x180050685  neg     eax
0x180050687  mov     rax, [rsi+6C8h]
0x18005068e  sbb     edx, edx
0x180050690  and     edx, 400h
0x180050696  neg     rax
0x180050699  mov     eax, [rsi+0BF0h]
0x18005069f  sbb     ecx, ecx
0x1800506a1  and     ecx, 800h
0x1800506a7  or      edx, ecx
0x1800506a9  neg     eax
0x1800506ab  mov     eax, [rsi+0BECh]
0x1800506b1  sbb     ecx, ecx
0x1800506b3  and     ecx, 80h
0x1800506b9  or      edx, ecx
0x1800506bb  neg     eax
0x1800506bd  mov     eax, [rsi+0BE8h]
0x1800506c3  sbb     ecx, ecx
0x1800506c5  and     ecx, 40h
0x1800506c8  or      edx, ecx
0x1800506ca  neg     eax
0x1800506cc  mov     eax, [rsi+0BE4h]
0x1800506d2  sbb     ecx, ecx
0x1800506d4  and     ecx, 20h
0x1800506d7  or      edx, ecx
0x1800506d9  neg     eax
0x1800506db  mov     eax, [rsi+0BE0h]
0x1800506e1  sbb     ecx, ecx
0x1800506e3  and     ecx, 10h
0x1800506e6  or      edx, ecx
0x1800506e8  neg     eax
0x1800506ea  mov     eax, [rsi+0BDCh]
0x1800506f0  sbb     ecx, ecx
0x1800506f2  and     ecx, 8
0x1800506f5  or      edx, ecx
0x1800506f7  neg     eax
0x1800506f9  sbb     ecx, ecx
0x1800506fb  xor     eax, eax
0x1800506fd  and     ecx, 4
0x180050700  or      edx, ecx
0x180050702  cmp     [rsi+0BD8h], eax
0x180050708  setnz   al
0x18005070b  or      edx, eax
0x18005070d  mov     eax, [rsi+618h]
0x180050713  neg     eax
0x180050715  sbb     ecx, ecx
0x180050717  and     ecx, 2
0x18005071a  or      edx, ecx
0x18005071c  cmp     dword ptr [rsi+5BCh], 0
0x180050723  jz      short loc_18005072D
0x180050725  mov     ecx, [rsi+5B8h]
0x18005072b  jmp     short loc_180050740
0x18005072d  cmp     dword ptr [rsi+464h], 0
0x180050734  jz      short loc_18005073E
0x180050736  mov     ecx, [rsi+5C0h]
0x18005073c  jmp     short loc_180050740
0x18005073e  xor     ecx, ecx
0x180050740  xor     eax, eax
0x180050742  mov     r10d, 200h
0x180050748  cmp     ecx, 1
0x18005074b  mov     rcx, rsi; this
0x18005074e  cmovnz  r10d, eax
0x180050752  or      r10d, edx
0x180050755  call    ?IsNonFRCMode@CxCodeVideoProcMFTDataHandler@@IEAAHXZ; CxCodeVideoProcMFTDataHandler::IsNonFRCMode(void)
0x18005075a  test    eax, eax
0x18005075c  jnz     short loc_1800507AB
0x18005075e  lea     rcx, [rsi+180h]; this
0x180050765  mov     [rbp+var_20], 0
0x18005076d  lea     r8, [rbp+var_20]; __int64 *
0x180050771  mov     [rbp+var_28], 0
0x180050779  lea     rdx, [rbp+var_18]; __int64 *
0x18005077d  call    ?GetTime@CxCodeVideoProcSampleInfo@@QEAAXPEA_J0@Z; CxCodeVideoProcSampleInfo::GetTime(__int64 *,__int64 *)
0x180050782  lea     rdx, [rbp+var_18]; __int64 *
0x180050786  lea     rcx, [rsi+340h]; this
0x18005078d  lea     r8, [rbp+var_28]; __int64 *
0x180050791  call    ?GetTime@CxCodeVideoProcSampleInfo@@QEAAXPEA_J0@Z; CxCodeVideoProcSampleInfo::GetTime(__int64 *,__int64 *)
0x180050796  mov     rcx, [rbp+var_28]
0x18005079a  sub     rcx, [rbp+var_20]
0x18005079e  neg     rcx
0x1800507a1  sbb     eax, eax
0x1800507a3  and     eax, 100h
0x1800507a8  or      r10d, eax
0x1800507ab  mov     [r14], r10d
0x1800507ae  mov     eax, ebx
0x1800507b0  mov     rcx, [rbp+var_8]
0x1800507b4  xor     rcx, rsp; StackCookie
0x1800507b7  call    __security_check_cookie
0x1800507bc  lea     r11, [rsp+60h+var_s0]
0x1800507c1  mov     rbx, [r11+30h]
0x1800507c5  mov     rsi, [r11+38h]
0x1800507c9  mov     rsp, r11
0x1800507cc  pop     r14
0x1800507ce  pop     rdi
0x1800507cf  pop     rbp
0x1800507d0  retn
```
