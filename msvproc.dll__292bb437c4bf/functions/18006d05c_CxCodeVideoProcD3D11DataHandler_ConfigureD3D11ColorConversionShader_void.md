# CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader(void)

- ea: `0x18006d05c`
- end: `0x18006d721`
- name: `?ConfigureD3D11ColorConversionShader@CxCodeVideoProcD3D11DataHandler@@AEAAJXZ`
- size: `1733`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18004e5f0`
- `0x18006eb24`
- `0x180071900`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180036268`
- `0x18003639c`
- `0x18005b450`
- `0x180065fd0`
- `0x18006bf40`
- `0x18006bf50`
- `0x18006bf60`
- `0x18006d05c`
- `0x180071e58`
- `0x180071fe4`
- `0x180073064`
- `0x1800735d0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d0cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d193`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d248`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d613`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d0cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d193`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d248`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006d613`

## string_xrefs

- `0x18006d07c`: `CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader`
- `0x18006d4c2`: `CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader(
        CxCodeVideoProcD3D11DataHandler *this)
{
  CxCodeVideoProcD3D11DataHandler *v1; // rbx
  int v2; // r13d
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  _DWORD *v14; // rax
  bool v15; // zf
  int v16; // edi
  struct ID3D11Device *v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  int v21; // r12d
  __int64 v22; // rcx
  int v23; // r15d
  __int64 v24; // rcx
  int v25; // r14d
  __int64 v26; // rcx
  int v27; // ebp
  __int64 v28; // rcx
  int v29; // esi
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // ebx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  _DWORD *v39; // rax
  int v40; // edx
  int v41; // r8d
  char v42; // r9
  char v43; // r10
  char v44; // r11
  char *v45; // rsi
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  float v49; // xmm0_4
  float v50; // xmm0_4
  __int64 v51; // r8
  struct MFD3D::D3DCbufferWrapperIface *v52; // r8
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  char v57; // [rsp+60h] [rbp-78h]
  int v59; // [rsp+E8h] [rbp+10h] BYREF
  char *v60; // [rsp+F0h] [rbp+18h]

  v1 = this;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v59,
    "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
    3129);
  v2 = 0;
  if ( !*(_DWORD *)(*((_QWORD *)v1 + 2) + 988LL) )
    goto LABEL_25;
  v2 = CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(v1, 0);
  if ( v2 < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
          3136,
          v2);
    }
    if ( g_wppLevels )
    {
      v6 = 194;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, v1, v2);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  v2 = CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(v1, *(unsigned int *)(*((_QWORD *)v1 + 2) + 1100LL));
  if ( v2 < 0 )
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
      if ( *((_DWORD *)v9 + 499) != v2 )
        CallStackContext::TraceFailure(
          v9,
          "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
          3137,
          v2);
    }
    if ( g_wppLevels )
    {
      v6 = 195;
      goto LABEL_13;
    }
  }
  else
  {
LABEL_25:
    v10 = *((_QWORD *)v1 + 2);
    if ( !*(_DWORD *)(v10 + 992)
      || (v2 = CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(v1, *(unsigned int *)(v10 + 1000)), v2 >= 0) )
    {
      v14 = (_DWORD *)*((_QWORD *)v1 + 2);
      v15 = (v14[282] | v14[318] | v14[257]) == 0;
      v16 = v14[282] | v14[318] | v14[257];
      v59 = v16;
      if ( v15 )
      {
        MFD3D::D3D11CbufferWrapperImpl::destroy((CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2144));
        MFD3D::D3D11CbufferWrapperImpl::destroy((CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2192));
        MFD3D::D3D11CbufferWrapperImpl::destroy((CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2240));
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qdd(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            201,
            &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
            v1,
            *(_DWORD *)(*((_QWORD *)v1 + 2) + 1100LL),
            *(_DWORD *)(*((_QWORD *)v1 + 2) + 1000LL));
        goto LABEL_79;
      }
      if ( (v16 & 2) != 0 )
      {
        CxCodeVideoProcD3DDataHandler::UpdateD3DShaderColorSpace(v1);
        v17 = (struct ID3D11Device *)*((_QWORD *)v1 + 285);
        v60 = (char *)v1 + 448;
        v2 = MFD3D::D3D11CbufferWrapperImpl::create(
               (CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2144),
               v17,
               (CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 448));
        if ( v2 < 0 )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != v2 )
              CallStackContext::TraceFailure(
                v20,
                "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
                3152,
                v2);
          }
          if ( g_wppLevels )
          {
            v6 = 197;
            goto LABEL_13;
          }
          goto LABEL_79;
        }
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        {
          v21 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v60) + 40);
          v23 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v22) + 36);
          v25 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v24) + 32);
          v27 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v26) + 28);
          v29 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v28) + 24);
          v16 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v30) + 20);
          v32 = *(_DWORD *)(MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v31) + 16);
          MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v33);
          MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v34);
          MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v35);
          MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v36);
          MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v37);
          v39 = (_DWORD *)MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(v38);
          v57 = v32;
          v1 = this;
          WPP_SF_qddddddddddddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            v40,
            v41,
            (_DWORD)this,
            *(_DWORD *)(*((_QWORD *)this + 2) + 1100LL),
            *(_DWORD *)(*((_QWORD *)this + 2) + 1000LL),
            *v39,
            v40,
            v41,
            v42,
            v43,
            v44,
            v57,
            v16,
            v29,
            v27,
            v25,
            v23,
            v21);
          LOBYTE(v16) = v59;
        }
      }
      if ( (v16 & 1) != 0 )
      {
        CxCodeVideoProcD3DDataHandler::UpdateD3DShaderColorSpaceEDR(v1);
        v45 = (char *)v1 + 864;
        v2 = MFD3D::D3D11CbufferWrapperImpl::create(
               (CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2192),
               *((struct ID3D11Device **)v1 + 285),
               (CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 864));
        if ( v2 < 0 )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v47;
            if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
            {
              v46 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v46 + 8) )
          {
            v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
            if ( *((_DWORD *)v48 + 499) != v2 )
              CallStackContext::TraceFailure(
                v48,
                "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
                3167,
                v2);
          }
          if ( g_wppLevels )
          {
            v6 = 199;
            goto LABEL_13;
          }
          goto LABEL_79;
        }
      }
      else
      {
        v45 = (char *)v1 + 864;
      }
      if ( (v16 & 8) != 0 )
      {
        v49 = (float)*(int *)(MFD3D::D3DCbufferWrapper<_stD3D11FixedTMGlobals>::operator->(v45) + 68);
        *(float *)(MFD3D::D3DCbufferWrapper<_stD3D11OutsideModeGlobals>::operator->((char *)v1 + 1120) + 12) = v49;
        v50 = (float)*(int *)(MFD3D::D3DCbufferWrapper<_stD3D11FixedTMGlobals>::operator->(v45) + 64);
        *(float *)(MFD3D::D3DCbufferWrapper<_stD3D11OutsideModeGlobals>::operator->(v51) + 8) = v50;
        v2 = MFD3D::D3D11CbufferWrapperImpl::create(
               (CxCodeVideoProcD3D11DataHandler *)((char *)v1 + 2240),
               *((struct ID3D11Device **)v1 + 285),
               v52);
        if ( v2 < 0 )
        {
          v53 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != v2 )
              CallStackContext::TraceFailure(
                v55,
                "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
                3174,
                v2);
          }
          if ( g_wppLevels )
          {
            v6 = 200;
            goto LABEL_13;
          }
        }
      }
      goto LABEL_79;
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
      if ( *((_DWORD *)v13 + 499) != v2 )
        CallStackContext::TraceFailure(
          v13,
          "CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader",
          3142,
          v2);
    }
    if ( g_wppLevels )
    {
      v6 = 196;
      goto LABEL_13;
    }
  }
LABEL_79:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v59);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18006d05c  mov     rax, rsp
0x18006d05f  mov     [rax+20h], rbx
0x18006d063  mov     [rax+8], rcx
0x18006d067  push    rbp
0x18006d068  push    rsi
0x18006d069  push    rdi
0x18006d06a  push    r12
0x18006d06c  push    r13
0x18006d06e  push    r14
0x18006d070  push    r15
0x18006d072  sub     rsp, 0A0h
0x18006d079  mov     rbx, rcx
0x18006d07c  lea     r14, aCxcodevideopro_51; "CxCodeVideoProcD3D11DataHandler::Config"...
0x18006d083  mov     rdx, r14; char *
0x18006d086  lea     rcx, [rax+10h]; this
0x18006d08a  mov     r8d, 0C39h; int
0x18006d090  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006d095  mov     rax, [rbx+10h]
0x18006d099  xor     ebp, ebp
0x18006d09b  mov     r13d, ebp
0x18006d09e  cmp     [rax+3DCh], ebp
0x18006d0a4  jz      loc_18006D213
0x18006d0aa  xor     edx, edx
0x18006d0ac  mov     rcx, rbx
0x18006d0af  call    ?EnsureProcessingShader@CxCodeVideoProcD3D11DataHandler@@EEAAJW4FallbackColorConversionShader@@@Z; CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(FallbackColorConversionShader)
0x18006d0b4  mov     r13d, eax
0x18006d0b7  test    eax, eax
0x18006d0b9  jns     loc_18006D16A
0x18006d0bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0c6  test    rcx, rcx
0x18006d0c9  jnz     short loc_18006D10C
0x18006d0cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d0d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0d8  mov     rcx, rax
0x18006d0db  test    rax, rax
0x18006d0de  jz      short loc_18006D0FE
0x18006d0e0  mov     rax, [rax]
0x18006d0e3  mov     edx, 7F0h
0x18006d0e8  mov     rax, [rax+8]
0x18006d0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0f1  test    eax, eax
0x18006d0f3  jz      short loc_18006D0FE
0x18006d0f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d0fc  jmp     short loc_18006D10C
0x18006d0fe  lea     rcx, qword_180153440; this
0x18006d105  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d10c  cmp     [rcx+8], bpl
0x18006d110  jz      short loc_18006D134
0x18006d112  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d117  cmp     [rax+7CCh], r13d
0x18006d11e  jz      short loc_18006D134
0x18006d120  mov     r9d, r13d; int
0x18006d123  mov     r8d, 0C40h; int
0x18006d129  mov     rdx, r14; char *
0x18006d12c  mov     rcx, rax; this
0x18006d12f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d134  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d13b  jb      loc_18006D6F6
0x18006d141  mov     edx, 0C2h
0x18006d146  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d14d  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18006d154  mov     r9, rbx
0x18006d157  mov     [rsp+0D8h+var_B8], r13d
0x18006d15c  mov     rcx, [rcx+10h]
0x18006d160  call    WPP_SF_qD
0x18006d165  jmp     loc_18006D6F6
0x18006d16a  mov     rdx, [rbx+10h]
0x18006d16e  mov     rcx, rbx
0x18006d171  mov     edx, [rdx+44Ch]
0x18006d177  call    ?EnsureProcessingShader@CxCodeVideoProcD3D11DataHandler@@EEAAJW4FallbackColorConversionShader@@@Z; CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(FallbackColorConversionShader)
0x18006d17c  mov     r13d, eax
0x18006d17f  test    eax, eax
0x18006d181  jns     loc_18006D213
0x18006d187  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d18e  test    rcx, rcx
0x18006d191  jnz     short loc_18006D1D4
0x18006d193  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d199  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d1a0  mov     rcx, rax
0x18006d1a3  test    rax, rax
0x18006d1a6  jz      short loc_18006D1C6
0x18006d1a8  mov     rax, [rax]
0x18006d1ab  mov     edx, 7F0h
0x18006d1b0  mov     rax, [rax+8]
0x18006d1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d1b9  test    eax, eax
0x18006d1bb  jz      short loc_18006D1C6
0x18006d1bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d1c4  jmp     short loc_18006D1D4
0x18006d1c6  lea     rcx, qword_180153440; this
0x18006d1cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d1d4  cmp     [rcx+8], bpl
0x18006d1d8  jz      short loc_18006D1FC
0x18006d1da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d1df  cmp     [rax+7CCh], r13d
0x18006d1e6  jz      short loc_18006D1FC
0x18006d1e8  mov     r9d, r13d; int
0x18006d1eb  mov     r8d, 0C41h; int
0x18006d1f1  mov     rdx, r14; char *
0x18006d1f4  mov     rcx, rax; this
0x18006d1f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d1fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d203  jb      loc_18006D6F6
0x18006d209  mov     edx, 0C3h
0x18006d20e  jmp     loc_18006D146
0x18006d213  mov     rdx, [rbx+10h]
0x18006d217  cmp     [rdx+3E0h], ebp
0x18006d21d  jz      loc_18006D2C8
0x18006d223  mov     edx, [rdx+3E8h]
0x18006d229  mov     rcx, rbx
0x18006d22c  call    ?EnsureProcessingShader@CxCodeVideoProcD3D11DataHandler@@EEAAJW4FallbackColorConversionShader@@@Z; CxCodeVideoProcD3D11DataHandler::EnsureProcessingShader(FallbackColorConversionShader)
0x18006d231  mov     r13d, eax
0x18006d234  test    eax, eax
0x18006d236  jns     loc_18006D2C8
0x18006d23c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d243  test    rcx, rcx
0x18006d246  jnz     short loc_18006D289
0x18006d248  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d24e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d255  mov     rcx, rax
0x18006d258  test    rax, rax
0x18006d25b  jz      short loc_18006D27B
0x18006d25d  mov     rax, [rax]
0x18006d260  mov     edx, 7F0h
0x18006d265  mov     rax, [rax+8]
0x18006d269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d26e  test    eax, eax
0x18006d270  jz      short loc_18006D27B
0x18006d272  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d279  jmp     short loc_18006D289
0x18006d27b  lea     rcx, qword_180153440; this
0x18006d282  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d289  cmp     [rcx+8], bpl
0x18006d28d  jz      short loc_18006D2B1
0x18006d28f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d294  cmp     [rax+7CCh], r13d
0x18006d29b  jz      short loc_18006D2B1
0x18006d29d  mov     r9d, r13d; int
0x18006d2a0  mov     r8d, 0C46h; int
0x18006d2a6  mov     rdx, r14; char *
0x18006d2a9  mov     rcx, rax; this
0x18006d2ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d2b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d2b8  jb      loc_18006D6F6
0x18006d2be  mov     edx, 0C4h
0x18006d2c3  jmp     loc_18006D146
0x18006d2c8  mov     rax, [rbx+10h]
0x18006d2cc  mov     edi, [rax+404h]
0x18006d2d2  or      edi, [rax+4F8h]
0x18006d2d8  or      edi, [rax+468h]
0x18006d2de  mov     [rsp+0D8h+arg_8], edi
0x18006d2e5  jz      loc_18006D68F
0x18006d2eb  test    dil, 2
0x18006d2ef  jz      loc_18006D4CB
0x18006d2f5  mov     rcx, rbx; this
0x18006d2f8  call    ?UpdateD3DShaderColorSpace@CxCodeVideoProcD3DDataHandler@@IEAAXXZ; CxCodeVideoProcD3DDataHandler::UpdateD3DShaderColorSpace(void)
0x18006d2fd  mov     rdx, [rbx+8E8h]; struct ID3D11Device *
0x18006d304  lea     r8, [rbx+1C0h]; struct MFD3D::D3DCbufferWrapperIface *
0x18006d30b  lea     rcx, [rbx+860h]; this
0x18006d312  mov     [rsp+0D8h+arg_10], r8
0x18006d31a  call    ?create@D3D11CbufferWrapperImpl@MFD3D@@QEAAJPEAUID3D11Device@@PEAVD3DCbufferWrapperIface@2@@Z; MFD3D::D3D11CbufferWrapperImpl::create(ID3D11Device *,MFD3D::D3DCbufferWrapperIface *)
0x18006d31f  mov     r13d, eax
0x18006d322  test    eax, eax
0x18006d324  jns     loc_18006D3B6
0x18006d32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d331  test    rcx, rcx
0x18006d334  jnz     short loc_18006D377
0x18006d336  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d33c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d343  mov     rcx, rax
0x18006d346  test    rax, rax
0x18006d349  jz      short loc_18006D369
0x18006d34b  mov     rax, [rax]
0x18006d34e  mov     edx, 7F0h
0x18006d353  mov     rax, [rax+8]
0x18006d357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d35c  test    eax, eax
0x18006d35e  jz      short loc_18006D369
0x18006d360  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d367  jmp     short loc_18006D377
0x18006d369  lea     rcx, qword_180153440; this
0x18006d370  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d377  cmp     [rcx+8], bpl
0x18006d37b  jz      short loc_18006D39F
0x18006d37d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d382  cmp     [rax+7CCh], r13d
0x18006d389  jz      short loc_18006D39F
0x18006d38b  mov     r9d, r13d; int
0x18006d38e  mov     r8d, 0C50h; int
0x18006d394  mov     rdx, r14; char *
0x18006d397  mov     rcx, rax; this
0x18006d39a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d39f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d3a6  jb      loc_18006D6F6
0x18006d3ac  mov     edx, 0C5h
0x18006d3b1  jmp     loc_18006D146
0x18006d3b6  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006d3bd  jb      loc_18006D4CB
0x18006d3c3  mov     rcx, [rsp+0D8h+arg_10]
0x18006d3cb  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3d0  mov     r12d, [rax+28h]
0x18006d3d4  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3d9  mov     r15d, [rax+24h]
0x18006d3dd  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3e2  mov     r14d, [rax+20h]
0x18006d3e6  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3eb  mov     ebp, [rax+1Ch]
0x18006d3ee  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3f3  mov     esi, [rax+18h]
0x18006d3f6  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d3fb  mov     edi, [rax+14h]
0x18006d3fe  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d403  mov     ebx, [rax+10h]
0x18006d406  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d40b  mov     r11d, [rax+50h]
0x18006d40f  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d414  mov     r10d, [rax+4Ch]
0x18006d418  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d41d  mov     r9d, [rax+0Ch]
0x18006d421  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d426  mov     r8d, [rax+8]
0x18006d42a  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d42f  mov     edx, [rax+4]
0x18006d432  call    ??C?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@QEAAPEAU_stD3D11ColorConversionGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->(void)
0x18006d437  mov     rcx, [rsp+0D8h+arg_0]
0x18006d43f  mov     [rsp+0D8h+var_48], r12d
0x18006d447  mov     [rsp+0D8h+var_50], r15d
0x18006d44f  mov     eax, [rax]
0x18006d451  mov     rcx, [rcx+10h]
0x18006d455  mov     [rsp+0D8h+var_58], r14d
0x18006d45d  mov     [rsp+0D8h+var_60], ebp
0x18006d461  mov     [rsp+0D8h+var_68], esi
0x18006d465  mov     [rsp+0D8h+var_70], edi
0x18006d469  mov     dword ptr [rsp+0D8h+var_78], ebx
0x18006d46d  mov     rbx, [rsp+0D8h+arg_0]
0x18006d475  mov     [rsp+0D8h+var_80], r11d
0x18006d47a  mov     [rsp+0D8h+var_88], r10d
0x18006d47f  mov     [rsp+0D8h+var_90], r9d
0x18006d484  mov     r9, rbx
0x18006d487  mov     [rsp+0D8h+var_98], r8d
0x18006d48c  mov     [rsp+0D8h+var_A0], edx
0x18006d490  mov     [rsp+0D8h+var_A8], eax
0x18006d494  mov     eax, [rcx+3E8h]
0x18006d49a  mov     [rsp+0D8h+var_B0], eax
0x18006d49e  mov     eax, [rcx+44Ch]
0x18006d4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d4ab  mov     [rsp+0D8h+var_B8], eax
0x18006d4af  mov     rcx, [rcx+150h]
0x18006d4b6  call    WPP_SF_qddddddddddddddd
0x18006d4bb  mov     edi, [rsp+0D8h+arg_8]
0x18006d4c2  lea     r14, aCxcodevideopro_51; "CxCodeVideoProcD3D11DataHandler::Config"...
0x18006d4c9  xor     ebp, ebp
0x18006d4cb  test    dil, 1
0x18006d4cf  jz      loc_18006D591
0x18006d4d5  mov     rcx, rbx; this
0x18006d4d8  call    ?UpdateD3DShaderColorSpaceEDR@CxCodeVideoProcD3DDataHandler@@IEAAXXZ; CxCodeVideoProcD3DDataHandler::UpdateD3DShaderColorSpaceEDR(void)
0x18006d4dd  mov     rdx, [rbx+8E8h]; struct ID3D11Device *
0x18006d4e4  lea     rsi, [rbx+360h]
0x18006d4eb  mov     r8, rsi; struct MFD3D::D3DCbufferWrapperIface *
0x18006d4ee  lea     rcx, [rbx+890h]; this
0x18006d4f5  call    ?create@D3D11CbufferWrapperImpl@MFD3D@@QEAAJPEAUID3D11Device@@PEAVD3DCbufferWrapperIface@2@@Z; MFD3D::D3D11CbufferWrapperImpl::create(ID3D11Device *,MFD3D::D3DCbufferWrapperIface *)
0x18006d4fa  mov     r13d, eax
0x18006d4fd  test    eax, eax
0x18006d4ff  jns     loc_18006D598
0x18006d505  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d50c  test    rcx, rcx
0x18006d50f  jnz     short loc_18006D552
0x18006d511  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006d517  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d51e  mov     rcx, rax
0x18006d521  test    rax, rax
0x18006d524  jz      short loc_18006D544
0x18006d526  mov     rax, [rax]
0x18006d529  mov     edx, 7F0h
0x18006d52e  mov     rax, [rax+8]
0x18006d532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d537  test    eax, eax
0x18006d539  jz      short loc_18006D544
0x18006d53b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d542  jmp     short loc_18006D552
0x18006d544  lea     rcx, qword_180153440; this
0x18006d54b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006d552  cmp     [rcx+8], bpl
0x18006d556  jz      short loc_18006D57A
0x18006d558  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006d55d  cmp     [rax+7CCh], r13d
0x18006d564  jz      short loc_18006D57A
0x18006d566  mov     r9d, r13d; int
0x18006d569  mov     r8d, 0C5Fh; int
0x18006d56f  mov     rdx, r14; char *
0x18006d572  mov     rcx, rax; this
0x18006d575  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006d57a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006d581  jb      loc_18006D6F6
0x18006d587  mov     edx, 0C7h
0x18006d58c  jmp     loc_18006D146
0x18006d591  lea     rsi, [rbx+360h]
0x18006d598  test    dil, 8
0x18006d59c  jz      loc_18006D6F6
0x18006d5a2  mov     rcx, rsi
  ... truncated ...
```
