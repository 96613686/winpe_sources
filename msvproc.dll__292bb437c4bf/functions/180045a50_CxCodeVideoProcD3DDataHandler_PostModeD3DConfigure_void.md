# CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure(void)

- ea: `0x180045a50`
- end: `0x180045f01`
- name: `?PostModeD3DConfigure@CxCodeVideoProcD3DDataHandler@@MEAAJXZ`
- size: `1201`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18006dad0`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180036268`
- `0x18003639c`
- `0x1800364d0`
- `0x180045a50`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180045d7d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180045d7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045ce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045e57`

## string_xrefs

- `0x180045a5d`: `CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure`
- `0x180045d3e`: `CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure`
- `0x180045de6`: `CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure`
- `0x180045eae`: `CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure(CxCodeVideoProcD3DDataHandler *this)
{
  int v2; // edi
  __int64 v3; // rcx
  char v4; // r8
  _DWORD *v5; // rax
  __int64 v6; // rdx
  char v7; // al
  bool v8; // zf
  _DWORD *v9; // rax
  _DWORD *v10; // rcx
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _DWORD *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  char v24; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
    "CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure",
    2330);
  v3 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v3 + 992) )
    *(_DWORD *)(v3 + 752) = 0;
  else
    *(_DWORD *)(v3 + 992) = *(_DWORD *)(v3 + 752);
  v4 = byte_180153DE0;
  if ( byte_180153DE0 )
  {
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      127,
      &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
      this,
      *(_DWORD *)(*((_QWORD *)this + 2) + 992LL),
      *(_DWORD *)(*((_QWORD *)this + 2) + 752LL));
    v4 = byte_180153DE0;
  }
  v5 = (_DWORD *)*((_QWORD *)this + 2);
  if ( !v5[247] || v5[89] )
  {
    if ( v5[246] || v5[223] )
      v5[216] = 3;
    else
      v5[216] = 2;
  }
  else
  {
    v5[216] = 1;
  }
  v6 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v6 + 988) || *(_QWORD *)(v6 + 1488) && (*(_BYTE *)(v6 + 2104) & 2) != 0 )
  {
    if ( *(_DWORD *)(v6 + 1304)
      || *(_DWORD *)(v6 + 1312)
      || *(_DWORD *)(v6 + 748)
      || *(_DWORD *)(v6 + 752)
      || *(_DWORD *)(v6 + 1240)
      || *(_DWORD *)(v6 + 1324)
      || *(_DWORD *)(v6 + 1328)
      || *(_DWORD *)(v6 + 80) - *(_DWORD *)(v6 + 72) != *(_DWORD *)(v6 + 432) - *(_DWORD *)(v6 + 424)
      || *(_DWORD *)(v6 + 84) - *(_DWORD *)(v6 + 76) != *(_DWORD *)(v6 + 436) - *(_DWORD *)(v6 + 428)
      || *(_DWORD *)(v6 + 356)
      || (v7 = 0, *(_DWORD *)(v6 + 1200) != *(_DWORD *)(v6 + 564)) )
    {
      v7 = 1;
    }
    if ( (*(_BYTE *)(v6 + 2120) & 4) != 0 || !*(_QWORD *)(v6 + 1488) )
    {
      v8 = v7 == 0;
    }
    else
    {
      if ( v7 || *(_DWORD *)(v6 + 424) )
        goto LABEL_37;
      v8 = *(_DWORD *)(v6 + 428) == 0;
    }
    if ( v8 )
    {
      *(_DWORD *)(v6 + 992) = 0;
      *(_DWORD *)(*((_QWORD *)this + 2) + 2144LL) = 0;
      if ( (unsigned __int8)v4 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 128, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    }
  }
LABEL_37:
  v9 = (_DWORD *)*((_QWORD *)this + 2);
  if ( v9[187] && v9[215] == 1 )
    v9[250] = 8;
  v10 = (_DWORD *)*((_QWORD *)this + 2);
  if ( v10[188] )
  {
    v10[250] = 10 - (v10[141] != 103);
    *(_DWORD *)(*((_QWORD *)this + 2) + 1028LL) = 9;
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 2144LL) )
    goto LABEL_66;
  if ( (*(unsigned __int8 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(*(_QWORD *)this + 56LL))(this)
    && (*(unsigned __int8 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(*(_QWORD *)this + 64LL))(this) )
  {
    v2 = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(*(_QWORD *)this + 184LL))(this);
    if ( v2 < 0 )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure",
            2425,
            v2);
      }
      if ( g_wppLevels )
      {
        v15 = 130;
LABEL_80:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v2);
        goto LABEL_81;
      }
      goto LABEL_81;
    }
LABEL_66:
    v19 = (_DWORD *)*((_QWORD *)this + 2);
    if ( v19[247] || v19[248] || v19[223] )
    {
      v2 = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(*(_QWORD *)this + 96LL))(this);
      if ( v2 < 0 )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v2 )
            CallStackContext::TraceFailure(v22, "CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure", 2430, v2);
        }
        if ( g_wppLevels )
        {
          v15 = 131;
          goto LABEL_80;
        }
      }
    }
    goto LABEL_81;
  }
  v2 = -1072875818;
  RoOriginateErrorW(
    3222091478LL,
    89,
    L"Device does not support video processing, but video processing is required for operation.",
    v11);
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != -1072875818 )
      CallStackContext::TraceFailure(v18, "CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure", 2423, -1072875818);
  }
  if ( g_wppLevels )
  {
    v15 = 129;
    goto LABEL_80;
  }
LABEL_81:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180045a50  push    rbx
0x180045a52  push    rsi
0x180045a53  push    rdi
0x180045a54  push    r14
0x180045a56  sub     rsp, 38h
0x180045a5a  mov     rbx, rcx
0x180045a5d  lea     rdx, aCxcodevideopro_105; "CxCodeVideoProcD3DDataHandler::PostMode"...
0x180045a64  xor     esi, esi
0x180045a66  lea     rcx, [rsp+58h+arg_0]; this
0x180045a6b  mov     r8d, 91Ah; int
0x180045a71  mov     edi, esi
0x180045a73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045a78  mov     rcx, [rbx+10h]
0x180045a7c  cmp     [rcx+3E0h], esi
0x180045a82  jz      short loc_180045A8C
0x180045a84  mov     [rcx+2F0h], esi
0x180045a8a  jmp     short loc_180045A98
0x180045a8c  mov     eax, [rcx+2F0h]
0x180045a92  mov     [rcx+3E0h], eax
0x180045a98  mov     r8b, cs:byte_180153DE0
0x180045a9f  lea     r14, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180045aa6  cmp     r8b, 1
0x180045aaa  jb      short loc_180045AE9
0x180045aac  mov     rcx, [rbx+10h]
0x180045ab0  mov     edx, 7Fh
0x180045ab5  mov     r9, rbx
0x180045ab8  mov     r8, r14
0x180045abb  mov     eax, [rcx+2F0h]
0x180045ac1  mov     [rsp+58h+var_30], eax
0x180045ac5  mov     eax, [rcx+3E0h]
0x180045acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ad2  mov     [rsp+58h+var_38], eax
0x180045ad6  mov     rcx, [rcx+150h]
0x180045add  call    WPP_SF_qdd
0x180045ae2  mov     r8b, cs:byte_180153DE0
0x180045ae9  mov     rax, [rbx+10h]
0x180045aed  cmp     [rax+3DCh], esi
0x180045af3  jz      short loc_180045B09
0x180045af5  cmp     [rax+164h], esi
0x180045afb  jnz     short loc_180045B09
0x180045afd  mov     dword ptr [rax+360h], 1
0x180045b07  jmp     short loc_180045B2F
0x180045b09  cmp     [rax+3D8h], esi
0x180045b0f  jnz     short loc_180045B25
0x180045b11  cmp     [rax+37Ch], esi
0x180045b17  jnz     short loc_180045B25
0x180045b19  mov     dword ptr [rax+360h], 2
0x180045b23  jmp     short loc_180045B2F
0x180045b25  mov     dword ptr [rax+360h], 3
0x180045b2f  mov     rdx, [rbx+10h]
0x180045b33  cmp     [rdx+3DCh], esi
0x180045b39  jnz     short loc_180045B55
0x180045b3b  cmp     [rdx+5D0h], rsi
0x180045b42  jz      loc_180045C32
0x180045b48  test    byte ptr [rdx+838h], 2
0x180045b4f  jz      loc_180045C32
0x180045b55  cmp     [rdx+518h], esi
0x180045b5b  jnz     short loc_180045BD2
0x180045b5d  cmp     [rdx+520h], esi
0x180045b63  jnz     short loc_180045BD2
0x180045b65  cmp     [rdx+2ECh], esi
0x180045b6b  jnz     short loc_180045BD2
0x180045b6d  cmp     [rdx+2F0h], esi
0x180045b73  jnz     short loc_180045BD2
0x180045b75  cmp     [rdx+4D8h], esi
0x180045b7b  jnz     short loc_180045BD2
0x180045b7d  cmp     [rdx+52Ch], esi
0x180045b83  jnz     short loc_180045BD2
0x180045b85  cmp     [rdx+530h], esi
0x180045b8b  jnz     short loc_180045BD2
0x180045b8d  mov     ecx, [rdx+1B0h]
0x180045b93  mov     eax, [rdx+50h]
0x180045b96  sub     ecx, [rdx+1A8h]
0x180045b9c  sub     eax, [rdx+48h]
0x180045b9f  cmp     eax, ecx
0x180045ba1  jnz     short loc_180045BD2
0x180045ba3  mov     ecx, [rdx+1B4h]
0x180045ba9  mov     eax, [rdx+54h]
0x180045bac  sub     ecx, [rdx+1ACh]
0x180045bb2  sub     eax, [rdx+4Ch]
0x180045bb5  cmp     eax, ecx
0x180045bb7  jnz     short loc_180045BD2
0x180045bb9  cmp     [rdx+164h], esi
0x180045bbf  jnz     short loc_180045BD2
0x180045bc1  mov     eax, [rdx+234h]
0x180045bc7  cmp     [rdx+4B0h], eax
0x180045bcd  mov     al, sil
0x180045bd0  jz      short loc_180045BD4
0x180045bd2  mov     al, 1
0x180045bd4  test    byte ptr [rdx+848h], 4
0x180045bdb  jnz     short loc_180045BFA
0x180045bdd  cmp     [rdx+5D0h], rsi
0x180045be4  jz      short loc_180045BFA
0x180045be6  test    al, al
0x180045be8  jnz     short loc_180045C32
0x180045bea  cmp     [rdx+1A8h], esi
0x180045bf0  jnz     short loc_180045C32
0x180045bf2  cmp     [rdx+1ACh], esi
0x180045bf8  jmp     short loc_180045BFC
0x180045bfa  test    al, al
0x180045bfc  jnz     short loc_180045C32
0x180045bfe  mov     [rdx+3E0h], esi
0x180045c04  mov     rax, [rbx+10h]
0x180045c08  mov     [rax+860h], esi
0x180045c0e  cmp     r8b, 20h ; ' '
0x180045c12  jb      short loc_180045C32
0x180045c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c1b  mov     edx, 80h
0x180045c20  mov     r9, rbx
0x180045c23  mov     r8, r14
0x180045c26  mov     rcx, [rcx+150h]
0x180045c2d  call    WPP_SF_q
0x180045c32  mov     rax, [rbx+10h]
0x180045c36  cmp     [rax+2ECh], esi
0x180045c3c  jz      short loc_180045C51
0x180045c3e  cmp     dword ptr [rax+35Ch], 1
0x180045c45  jnz     short loc_180045C51
0x180045c47  mov     dword ptr [rax+3E8h], 8
0x180045c51  mov     rcx, [rbx+10h]
0x180045c55  cmp     [rcx+2F0h], esi
0x180045c5b  jz      short loc_180045C81
0x180045c5d  mov     eax, [rcx+234h]
0x180045c63  sub     eax, 67h ; 'g'
0x180045c66  neg     eax
0x180045c68  sbb     eax, eax
0x180045c6a  add     eax, 0Ah
0x180045c6d  mov     [rcx+3E8h], eax
0x180045c73  mov     rax, [rbx+10h]
0x180045c77  mov     dword ptr [rax+404h], 9
0x180045c81  mov     rax, [rbx+10h]
0x180045c85  cmp     [rax+860h], esi
0x180045c8b  jz      loc_180045E12
0x180045c91  mov     rax, [rbx]
0x180045c94  mov     rcx, rbx
0x180045c97  mov     rax, [rax+38h]
0x180045c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ca0  test    al, al
0x180045ca2  jz      loc_180045D6A
0x180045ca8  mov     rax, [rbx]
0x180045cab  mov     rcx, rbx
0x180045cae  mov     rax, [rax+40h]
0x180045cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb7  test    al, al
0x180045cb9  jz      loc_180045D6A
0x180045cbf  mov     rax, [rbx]
0x180045cc2  mov     rcx, rbx
0x180045cc5  mov     rax, [rax+0B8h]
0x180045ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cd1  mov     edi, eax
0x180045cd3  test    eax, eax
0x180045cd5  jns     loc_180045E12
0x180045cdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ce2  test    rcx, rcx
0x180045ce5  jnz     short loc_180045D28
0x180045ce7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045ced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045cf4  mov     rcx, rax
0x180045cf7  test    rax, rax
0x180045cfa  jz      short loc_180045D1A
0x180045cfc  mov     rax, [rax]
0x180045cff  mov     edx, 7F0h
0x180045d04  mov     rax, [rax+8]
0x180045d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d0d  test    eax, eax
0x180045d0f  jz      short loc_180045D1A
0x180045d11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d18  jmp     short loc_180045D28
0x180045d1a  lea     rcx, qword_180153440; this
0x180045d21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d28  cmp     [rcx+8], sil
0x180045d2c  jz      short loc_180045D53
0x180045d2e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045d33  cmp     [rax+7CCh], edi
0x180045d39  jz      short loc_180045D53
0x180045d3b  mov     r9d, edi; int
0x180045d3e  lea     rdx, aCxcodevideopro_105; "CxCodeVideoProcD3DDataHandler::PostMode"...
0x180045d45  mov     r8d, 979h; int
0x180045d4b  mov     rcx, rax; this
0x180045d4e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045d53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045d5a  jb      loc_180045EEB
0x180045d60  mov     edx, 82h
0x180045d65  jmp     loc_180045ED1
0x180045d6a  mov     edi, 0C00D36D6h
0x180045d6f  lea     r8, aDeviceDoesNotS; "Device does not support video processin"...
0x180045d76  mov     ecx, edi
0x180045d78  mov     edx, 59h ; 'Y'
0x180045d7d  call    cs:__imp_RoOriginateErrorW
0x180045d83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d8a  test    rcx, rcx
0x180045d8d  jnz     short loc_180045DD0
0x180045d8f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045d95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d9c  mov     rcx, rax
0x180045d9f  test    rax, rax
0x180045da2  jz      short loc_180045DC2
0x180045da4  mov     rax, [rax]
0x180045da7  mov     edx, 7F0h
0x180045dac  mov     rax, [rax+8]
0x180045db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045db5  test    eax, eax
0x180045db7  jz      short loc_180045DC2
0x180045db9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045dc0  jmp     short loc_180045DD0
0x180045dc2  lea     rcx, qword_180153440; this
0x180045dc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045dd0  cmp     [rcx+8], sil
0x180045dd4  jz      short loc_180045DFB
0x180045dd6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045ddb  cmp     [rax+7CCh], edi
0x180045de1  jz      short loc_180045DFB
0x180045de3  mov     r9d, edi; int
0x180045de6  lea     rdx, aCxcodevideopro_105; "CxCodeVideoProcD3DDataHandler::PostMode"...
0x180045ded  mov     r8d, 977h; int
0x180045df3  mov     rcx, rax; this
0x180045df6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045dfb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045e02  jb      loc_180045EEB
0x180045e08  mov     edx, 81h
0x180045e0d  jmp     loc_180045ED1
0x180045e12  mov     rax, [rbx+10h]
0x180045e16  cmp     [rax+3DCh], esi
0x180045e1c  jnz     short loc_180045E32
0x180045e1e  cmp     [rax+3E0h], esi
0x180045e24  jnz     short loc_180045E32
0x180045e26  cmp     [rax+37Ch], esi
0x180045e2c  jz      loc_180045EEB
0x180045e32  mov     rax, [rbx]
0x180045e35  mov     rcx, rbx
0x180045e38  mov     rax, [rax+60h]
0x180045e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e41  mov     edi, eax
0x180045e43  test    eax, eax
0x180045e45  jns     loc_180045EEB
0x180045e4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e52  test    rcx, rcx
0x180045e55  jnz     short loc_180045E98
0x180045e57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045e5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e64  mov     rcx, rax
0x180045e67  test    rax, rax
0x180045e6a  jz      short loc_180045E8A
0x180045e6c  mov     rax, [rax]
0x180045e6f  mov     edx, 7F0h
0x180045e74  mov     rax, [rax+8]
0x180045e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e7d  test    eax, eax
0x180045e7f  jz      short loc_180045E8A
0x180045e81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e88  jmp     short loc_180045E98
0x180045e8a  lea     rcx, qword_180153440; this
0x180045e91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e98  cmp     [rcx+8], sil
0x180045e9c  jz      short loc_180045EC3
0x180045e9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045ea3  cmp     [rax+7CCh], edi
0x180045ea9  jz      short loc_180045EC3
0x180045eab  mov     r9d, edi; int
0x180045eae  lea     rdx, aCxcodevideopro_105; "CxCodeVideoProcD3DDataHandler::PostMode"...
0x180045eb5  mov     r8d, 97Eh; int
0x180045ebb  mov     rcx, rax; this
0x180045ebe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045ec3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045eca  jb      short loc_180045EEB
0x180045ecc  mov     edx, 83h
0x180045ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ed8  mov     r9, rbx
0x180045edb  mov     r8, r14
0x180045ede  mov     [rsp+58h+var_38], edi
0x180045ee2  mov     rcx, [rcx+10h]
0x180045ee6  call    WPP_SF_qD
0x180045eeb  lea     rcx, [rsp+58h+arg_0]; this
0x180045ef0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045ef5  mov     eax, edi
0x180045ef7  add     rsp, 38h
0x180045efb  pop     r14
0x180045efd  pop     rdi
0x180045efe  pop     rsi
0x180045eff  pop     rbx
0x180045f00  retn
```
