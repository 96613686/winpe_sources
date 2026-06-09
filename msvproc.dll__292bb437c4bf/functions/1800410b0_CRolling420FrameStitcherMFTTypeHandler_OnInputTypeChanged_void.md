# CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged(void)

- ea: `0x1800410b0`
- end: `0x18004132a`
- name: `?OnInputTypeChanged@CRolling420FrameStitcherMFTTypeHandler@@MEAAJXZ`
- size: `634`
- prototype: `__int64 __fastcall(CRolling420FrameStitcherMFTTypeHandler *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001bc24`
- `0x180021d08`
- `0x18003639c`
- `0x1800410b0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800411b0`
- `MFPlat!MFCreateMediaType` at `0x1800411b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041100`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800411cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004127d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041100`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800411cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004127d`

## pseudocode

```c
__int64 __fastcall CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged(
        CRolling420FrameStitcherMFTTypeHandler *this)
{
  HRESULT inited; // ebx
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  unsigned int v10; // edx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v15; // [rsp+48h] [rbp+10h] BYREF
  IMFMediaType *ppMFType; // [rsp+50h] [rbp+18h] BYREF

  ppMFType = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v15,
    "CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged",
    137);
  inited = CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(this, 1u);
  if ( inited >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**((_QWORD **)this + 6) + 256LL))(
                 *((_QWORD *)this + 6),
                 ppMFType);
      if ( inited >= 0 )
      {
        CMFTSimpleTypeHandler::SetAvailableOutputType(this, v10, ppMFType);
        goto LABEL_36;
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged",
            139,
            inited);
      }
      if ( g_wppLevels )
      {
        v6 = 28;
        goto LABEL_12;
      }
    }
    else
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)v9 + 499) != inited )
          CallStackContext::TraceFailure(v9, "CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged", 138, inited);
      }
      if ( g_wppLevels )
      {
        v6 = 27;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v4;
      if ( v4 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v5 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v5 + 499) != inited )
        CallStackContext::TraceFailure(v5, "CRolling420FrameStitcherMFTTypeHandler::OnInputTypeChanged", 137, inited);
    }
    if ( g_wppLevels )
    {
      v6 = 26;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids, this, inited);
    }
  }
LABEL_36:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800410b0  mov     [rsp+arg_0], rbx
0x1800410b5  push    rdi
0x1800410b6  sub     rsp, 30h
0x1800410ba  mov     rdi, rcx
0x1800410bd  mov     [rsp+38h+ppMFType], 0
0x1800410c6  lea     rcx, [rsp+38h+arg_8]; this
0x1800410cb  mov     r8d, 89h; int
0x1800410d1  lea     rdx, aCrolling420fra_2; "CRolling420FrameStitcherMFTTypeHandler:"...
0x1800410d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800410dd  mov     edx, 1; unsigned int
0x1800410e2  mov     rcx, rdi; this
0x1800410e5  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x1800410ea  mov     ebx, eax
0x1800410ec  test    eax, eax
0x1800410ee  jns     loc_1800411A1
0x1800410f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800410fb  test    rcx, rcx
0x1800410fe  jnz     short loc_180041141
0x180041100  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041106  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004110d  mov     rcx, rax
0x180041110  test    rax, rax
0x180041113  jz      short loc_180041133
0x180041115  mov     rax, [rax]
0x180041118  mov     edx, 7F0h
0x18004111d  mov     rax, [rax+8]
0x180041121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041126  test    eax, eax
0x180041128  jz      short loc_180041133
0x18004112a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041131  jmp     short loc_180041141
0x180041133  lea     rcx, qword_180153440; this
0x18004113a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041141  cmp     byte ptr [rcx+8], 0
0x180041145  jz      short loc_18004116C
0x180041147  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004114c  cmp     [rax+7CCh], ebx
0x180041152  jz      short loc_18004116C
0x180041154  mov     r9d, ebx; int
0x180041157  lea     rdx, aCrolling420fra_2; "CRolling420FrameStitcherMFTTypeHandler:"...
0x18004115e  mov     r8d, 89h; int
0x180041164  mov     rcx, rax; this
0x180041167  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004116c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041173  jb      loc_180041309
0x180041179  mov     edx, 1Ah
0x18004117e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041185  lea     r8, WPP_b4a5a6fcfe323eb6f6122aca36e987b3_Traceguids
0x18004118c  mov     r9, rdi
0x18004118f  mov     [rsp+38h+var_18], ebx
0x180041193  mov     rcx, [rcx+10h]
0x180041197  call    WPP_SF_qD
0x18004119c  jmp     loc_180041309
0x1800411a1  lea     rcx, [rsp+38h+ppMFType]
0x1800411a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800411ab  lea     rcx, [rsp+38h+ppMFType]; ppMFType
0x1800411b0  call    cs:__imp_MFCreateMediaType
0x1800411b6  mov     ebx, eax
0x1800411b8  test    eax, eax
0x1800411ba  jns     loc_18004124F
0x1800411c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800411c7  test    rcx, rcx
0x1800411ca  jnz     short loc_18004120D
0x1800411cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800411d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800411d9  mov     rcx, rax
0x1800411dc  test    rax, rax
0x1800411df  jz      short loc_1800411FF
0x1800411e1  mov     rax, [rax]
0x1800411e4  mov     edx, 7F0h
0x1800411e9  mov     rax, [rax+8]
0x1800411ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411f2  test    eax, eax
0x1800411f4  jz      short loc_1800411FF
0x1800411f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800411fd  jmp     short loc_18004120D
0x1800411ff  lea     rcx, qword_180153440; this
0x180041206  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004120d  cmp     byte ptr [rcx+8], 0
0x180041211  jz      short loc_180041238
0x180041213  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041218  cmp     [rax+7CCh], ebx
0x18004121e  jz      short loc_180041238
0x180041220  mov     r9d, ebx; int
0x180041223  lea     rdx, aCrolling420fra_2; "CRolling420FrameStitcherMFTTypeHandler:"...
0x18004122a  mov     r8d, 8Ah; int
0x180041230  mov     rcx, rax; this
0x180041233  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041238  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004123f  jb      loc_180041309
0x180041245  mov     edx, 1Bh
0x18004124a  jmp     loc_18004117E
0x18004124f  mov     rcx, [rdi+30h]
0x180041253  mov     rdx, [rsp+38h+ppMFType]
0x180041258  mov     rax, [rcx]
0x18004125b  mov     rax, [rax+100h]
0x180041262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041267  mov     ebx, eax
0x180041269  test    eax, eax
0x18004126b  jns     loc_1800412FC
0x180041271  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041278  test    rcx, rcx
0x18004127b  jnz     short loc_1800412BE
0x18004127d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041283  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004128a  mov     rcx, rax
0x18004128d  test    rax, rax
0x180041290  jz      short loc_1800412B0
0x180041292  mov     rax, [rax]
0x180041295  mov     edx, 7F0h
0x18004129a  mov     rax, [rax+8]
0x18004129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412a3  test    eax, eax
0x1800412a5  jz      short loc_1800412B0
0x1800412a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800412ae  jmp     short loc_1800412BE
0x1800412b0  lea     rcx, qword_180153440; this
0x1800412b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800412be  cmp     byte ptr [rcx+8], 0
0x1800412c2  jz      short loc_1800412E9
0x1800412c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800412c9  cmp     [rax+7CCh], ebx
0x1800412cf  jz      short loc_1800412E9
0x1800412d1  mov     r9d, ebx; int
0x1800412d4  lea     rdx, aCrolling420fra_2; "CRolling420FrameStitcherMFTTypeHandler:"...
0x1800412db  mov     r8d, 8Bh; int
0x1800412e1  mov     rcx, rax; this
0x1800412e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800412e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800412f0  jb      short loc_180041309
0x1800412f2  mov     edx, 1Ch
0x1800412f7  jmp     loc_18004117E
0x1800412fc  mov     r8, [rsp+38h+ppMFType]; struct IMFMediaType *
0x180041301  mov     rcx, rdi; this
0x180041304  call    ?SetAvailableOutputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *)
0x180041309  lea     rcx, [rsp+38h+arg_8]; this
0x18004130e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180041313  lea     rcx, [rsp+38h+ppMFType]
0x180041318  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004131d  mov     eax, ebx
0x18004131f  mov     rbx, [rsp+38h+arg_0]
0x180041324  add     rsp, 30h
0x180041328  pop     rdi
0x180041329  retn
```
