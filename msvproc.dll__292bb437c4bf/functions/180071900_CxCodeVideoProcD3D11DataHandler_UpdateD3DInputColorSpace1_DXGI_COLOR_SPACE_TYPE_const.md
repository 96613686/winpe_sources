# CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1(DXGI_COLOR_SPACE_TYPE const &)

- ea: `0x180071900`
- end: `0x180071ccd`
- name: `?UpdateD3DInputColorSpace1@CxCodeVideoProcD3D11DataHandler@@UEAAJAEBW4DXGI_COLOR_SPACE_TYPE@@@Z`
- size: `973`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this, const enum DXGI_COLOR_SPACE_TYPE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180065890`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180039300`
- `0x180054140`
- `0x18006d05c`
- `0x180071900`
- `0x18007239c`
- `0x1800ca098`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071b63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071c00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071b63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071c00`

## string_xrefs

- `0x180071b2c`: `CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1(
        CxCodeVideoProcD3D11DataHandler *this,
        const enum DXGI_COLOR_SPACE_TYPE *a2)
{
  _DWORD *v2; // rax
  int v3; // edi
  __int64 v6; // rcx
  __int64 v7; // rdx
  struct DXGI_HDR_METADATA_HDR10 *v8; // r8
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r9d
  float v12; // xmm8_4
  float v13; // xmm7_4
  float v14; // xmm6_4
  float v15; // xmm4_4
  float v16; // xmm2_4
  float v17; // xmm1_4
  float v18; // xmm0_4
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v27[4]; // [rsp+78h] [rbp-19h] BYREF
  int v28; // [rsp+7Ch] [rbp-15h] BYREF
  struct IMFMediaType v29[4]; // [rsp+80h] [rbp-11h] BYREF

  v2 = (_DWORD *)*((_QWORD *)this + 2);
  v3 = 0;
  if ( !v2[536] || (v6 = *((_QWORD *)this + 291)) == 0 || v2[247] )
  {
    if ( !v2[282] )
      return (unsigned int)v3;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v27,
      "CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1",
      3536);
    v3 = CxCodeVideoProcD3DDataHandler::ReResolveFallbackShader(this);
    if ( v3 >= 0 )
    {
      v3 = CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader(this);
      if ( v3 >= 0 )
        goto LABEL_35;
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1",
            3537,
            v3);
      }
      if ( !g_wppLevels )
        goto LABEL_35;
      v22 = 211;
    }
    else
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v3 )
          CallStackContext::TraceFailure(v21, "CxCodeVideoProcD3D11DataHandler::UpdateD3DInputColorSpace1", 3536, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_35;
      v22 = 210;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v3);
LABEL_35:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
    return (unsigned int)v3;
  }
  v7 = *((_QWORD *)this + 294);
  v28 = 0;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v6 + 608LL))(v6, v7, 0, &v28);
  if ( *a2 != v28 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 291) + 592LL))(
      *((_QWORD *)this + 291),
      *((_QWORD *)this + 294),
      0);
  if ( *((_QWORD *)this + 292) )
  {
    v9 = *((_QWORD *)this + 2);
    memset(v29, 0, 28);
    if ( (int)MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(*(MFMEDIATYPEUtils **)(v9 + 320), v29, v8) < 0 )
    {
      v29[0].lpVtbl = (struct IMFMediaTypeVtbl *)0x75303A9840747D00LL;
      v29[1].lpVtbl = (struct IMFMediaTypeVtbl *)0x40423D130BB81D4CLL;
      LODWORD(v29[2].lpVtbl) = 80;
      *(struct IMFMediaTypeVtbl **)((char *)&v29[2].lpVtbl + 4) = (struct IMFMediaTypeVtbl *)1;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, struct IMFMediaType *))(**((_QWORD **)this + 292)
                                                                                        + 648LL))(
      *((_QWORD *)this + 292),
      *((_QWORD *)this + 294),
      0,
      1,
      28,
      v29);
    if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 1) != 0 )
    {
      v12 = (float)HIWORD(v29[1].lpVtbl) / 20000.0;
      v13 = (float)WORD2(v29[1].lpVtbl) / 20000.0;
      v14 = (float)WORD1(v29[1].lpVtbl) / 20000.0;
      v15 = (float)LOWORD(v29[1].lpVtbl) / 20000.0;
      v16 = (float)HIWORD(v29[0].lpVtbl) / 20000.0;
      v17 = (float)WORD2(v29[0].lpVtbl) / 20000.0;
      v18 = (float)WORD1(v29[0].lpVtbl) / 20000.0;
      McTemplateU0pffffffffqq_EventWriteTransfer(
        v10,
        (unsigned int)MSVProc_ConfigureInputHDRMetadata,
        *((_QWORD *)this + 294),
        v11,
        SLOBYTE(v18),
        SLOBYTE(v17),
        SLOBYTE(v16),
        SLOBYTE(v15),
        SLOBYTE(v14),
        SLOBYTE(v13),
        SLOBYTE(v12),
        (char)v29[2].lpVtbl,
        SBYTE4(v29[2].lpVtbl));
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180071900  mov     rax, rsp
0x180071903  mov     [rax+18h], rbx
0x180071907  push    rbp
0x180071908  push    rsi
0x180071909  push    rdi
0x18007190a  lea     rbp, [rax-5Fh]
0x18007190e  sub     rsp, 0D0h
0x180071915  movaps  xmmword ptr [rax-28h], xmm6
0x180071919  movaps  xmmword ptr [rax-38h], xmm7
0x18007191d  movaps  xmmword ptr [rax-48h], xmm8
0x180071922  mov     rax, cs:__security_cookie
0x180071929  xor     rax, rsp
0x18007192c  mov     [rbp+57h+var_48], rax
0x180071930  mov     rax, [rcx+10h]
0x180071934  xor     edi, edi
0x180071936  mov     rsi, rdx
0x180071939  mov     rbx, rcx
0x18007193c  cmp     [rax+860h], edi
0x180071942  jz      loc_180071B20
0x180071948  mov     rcx, [rcx+918h]
0x18007194f  test    rcx, rcx
0x180071952  jz      loc_180071B20
0x180071958  cmp     [rax+3DCh], edi
0x18007195e  jnz     loc_180071B20
0x180071964  mov     rdx, [rbx+930h]
0x18007196b  lea     r9, [rbp+57h+var_6C]
0x18007196f  mov     [rbp+57h+var_6C], edi
0x180071972  xor     r8d, r8d
0x180071975  mov     rax, [rcx]
0x180071978  mov     rax, [rax+260h]
0x18007197f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071984  mov     r9d, [rsi]
0x180071987  cmp     r9d, [rbp+57h+var_6C]
0x18007198b  jz      short loc_1800719AD
0x18007198d  mov     rcx, [rbx+918h]
0x180071994  xor     r8d, r8d
0x180071997  mov     rdx, [rbx+930h]
0x18007199e  mov     rax, [rcx]
0x1800719a1  mov     rax, [rax+250h]
0x1800719a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719ad  cmp     [rbx+920h], rdi
0x1800719b4  jz      loc_180071C9D
0x1800719ba  mov     rcx, [rbx+10h]
0x1800719be  lea     rdx, [rbp+57h+var_68]; struct IMFMediaType *
0x1800719c2  xorps   xmm0, xmm0
0x1800719c5  movups  xmmword ptr [rbp+57h+var_68.lpVtbl], xmm0
0x1800719c9  movups  xmmword ptr [rbp+57h+var_68.lpVtbl+0Ch], xmm0
0x1800719cd  mov     rcx, [rcx+140h]; this
0x1800719d4  call    ?GetHDRMetaDataFromMediaType@MFMEDIATYPEUtils@@YAJPEAUIMFMediaType@@PEAUDXGI_HDR_METADATA_HDR10@@@Z; MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(IMFMediaType *,DXGI_HDR_METADATA_HDR10 *)
0x1800719d9  test    eax, eax
0x1800719db  jns     short loc_180071A08
0x1800719dd  mov     dword ptr [rbp+57h+var_68.lpVtbl], 40747D00h
0x1800719e4  mov     dword ptr [rbp+57h+var_68.lpVtbl+4], 75303A98h
0x1800719eb  mov     dword ptr [rbp+57h+var_68.lpVtbl+8], 0BB81D4Ch
0x1800719f2  mov     dword ptr [rbp+57h+var_68.lpVtbl+0Ch], 40423D13h
0x1800719f9  mov     [rbp+57h+var_58], 50h ; 'P'
0x180071a00  mov     [rbp+57h+var_54], 1
0x180071a08  mov     rcx, [rbx+920h]
0x180071a0f  lea     rdx, [rbp+57h+var_68]
0x180071a13  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x180071a18  mov     r9d, 1
0x180071a1e  mov     rdx, [rbx+930h]
0x180071a25  xor     r8d, r8d
0x180071a28  mov     dword ptr [rsp+0E0h+var_C0], 1Ch
0x180071a30  mov     rax, [rcx]
0x180071a33  mov     rax, [rax+288h]
0x180071a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a3f  test    byte ptr cs:Microsoft_Windows_MediaFoundation_MSVProcEnableBits, 1
0x180071a46  jz      loc_180071C9D
0x180071a4c  movss   xmm5, cs:__real@469c4000
0x180071a54  lea     rdx, MSVProc_ConfigureInputHDRMetadata
0x180071a5b  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+0Eh]
0x180071a5f  mov     r8, [rbx+930h]
0x180071a66  movd    xmm8, eax
0x180071a6b  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+0Ch]
0x180071a6f  cvtdq2ps xmm8, xmm8
0x180071a73  movd    xmm7, eax
0x180071a77  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+0Ah]
0x180071a7b  cvtdq2ps xmm7, xmm7
0x180071a7e  movd    xmm6, eax
0x180071a82  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+8]
0x180071a86  cvtdq2ps xmm6, xmm6
0x180071a89  movd    xmm4, eax
0x180071a8d  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+6]
0x180071a91  cvtdq2ps xmm4, xmm4
0x180071a94  movd    xmm2, eax
0x180071a98  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+4]
0x180071a9c  cvtdq2ps xmm2, xmm2
0x180071a9f  movd    xmm1, eax
0x180071aa3  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl+2]
0x180071aa7  cvtdq2ps xmm1, xmm1
0x180071aaa  movd    xmm0, eax
0x180071aae  movzx   eax, word ptr [rbp+57h+var_68.lpVtbl]
0x180071ab2  cvtdq2ps xmm0, xmm0
0x180071ab5  movd    xmm3, eax
0x180071ab9  mov     eax, dword ptr [rbp+57h+var_54]
0x180071abc  mov     [rsp+0E0h+var_80], eax
0x180071ac0  mov     eax, [rbp+57h+var_58]
0x180071ac3  mov     [rsp+0E0h+var_88], eax
0x180071ac7  cvtdq2ps xmm3, xmm3
0x180071aca  divss   xmm8, xmm5
0x180071acf  divss   xmm7, xmm5
0x180071ad3  movss   [rsp+0E0h+var_90], xmm8
0x180071ada  movss   [rsp+0E0h+var_98], xmm7
0x180071ae0  divss   xmm6, xmm5
0x180071ae4  divss   xmm4, xmm5
0x180071ae8  movss   [rsp+0E0h+var_A0], xmm6
0x180071aee  movss   [rsp+0E0h+var_A8], xmm4
0x180071af4  divss   xmm2, xmm5
0x180071af8  divss   xmm1, xmm5
0x180071afc  divss   xmm0, xmm5
0x180071b00  movss   [rsp+0E0h+var_B0], xmm2
0x180071b06  divss   xmm3, xmm5
0x180071b0a  movss   [rsp+0E0h+var_B8], xmm1
0x180071b10  movss   dword ptr [rsp+0E0h+var_C0], xmm0
0x180071b16  call    McTemplateU0pffffffffqq_EventWriteTransfer
0x180071b1b  jmp     loc_180071C9D
0x180071b20  cmp     [rax+468h], edi
0x180071b26  jz      loc_180071C9D
0x180071b2c  lea     rsi, aCxcodevideopro_17; "CxCodeVideoProcD3D11DataHandler::Update"...
0x180071b33  mov     r8d, 0DD0h; int
0x180071b39  mov     rdx, rsi; char *
0x180071b3c  lea     rcx, [rbp+57h+var_70]; this
0x180071b40  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071b45  mov     rcx, rbx; this
0x180071b48  call    ?ReResolveFallbackShader@CxCodeVideoProcD3DDataHandler@@QEAAJXZ; CxCodeVideoProcD3DDataHandler::ReResolveFallbackShader(void)
0x180071b4d  mov     edi, eax
0x180071b4f  test    eax, eax
0x180071b51  jns     loc_180071BE2
0x180071b57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b5e  test    rcx, rcx
0x180071b61  jnz     short loc_180071BA4
0x180071b63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071b69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b70  mov     rcx, rax
0x180071b73  test    rax, rax
0x180071b76  jz      short loc_180071B96
0x180071b78  mov     rax, [rax]
0x180071b7b  mov     edx, 7F0h
0x180071b80  mov     rax, [rax+8]
0x180071b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b89  test    eax, eax
0x180071b8b  jz      short loc_180071B96
0x180071b8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b94  jmp     short loc_180071BA4
0x180071b96  lea     rcx, qword_180153440; this
0x180071b9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ba4  cmp     byte ptr [rcx+8], 0
0x180071ba8  jz      short loc_180071BCB
0x180071baa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071baf  cmp     [rax+7CCh], edi
0x180071bb5  jz      short loc_180071BCB
0x180071bb7  mov     r9d, edi; int
0x180071bba  mov     r8d, 0DD0h; int
0x180071bc0  mov     rdx, rsi; char *
0x180071bc3  mov     rcx, rax; this
0x180071bc6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071bcb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071bd2  jb      loc_180071C94
0x180071bd8  mov     edx, 0D2h
0x180071bdd  jmp     loc_180071C76
0x180071be2  mov     rcx, rbx; this
0x180071be5  call    ?ConfigureD3D11ColorConversionShader@CxCodeVideoProcD3D11DataHandler@@AEAAJXZ; CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader(void)
0x180071bea  mov     edi, eax
0x180071bec  test    eax, eax
0x180071bee  jns     loc_180071C94
0x180071bf4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071bfb  test    rcx, rcx
0x180071bfe  jnz     short loc_180071C41
0x180071c00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071c06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c0d  mov     rcx, rax
0x180071c10  test    rax, rax
0x180071c13  jz      short loc_180071C33
0x180071c15  mov     rax, [rax]
0x180071c18  mov     edx, 7F0h
0x180071c1d  mov     rax, [rax+8]
0x180071c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c26  test    eax, eax
0x180071c28  jz      short loc_180071C33
0x180071c2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c31  jmp     short loc_180071C41
0x180071c33  lea     rcx, qword_180153440; this
0x180071c3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c41  cmp     byte ptr [rcx+8], 0
0x180071c45  jz      short loc_180071C68
0x180071c47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071c4c  cmp     [rax+7CCh], edi
0x180071c52  jz      short loc_180071C68
0x180071c54  mov     r9d, edi; int
0x180071c57  mov     r8d, 0DD1h; int
0x180071c5d  mov     rdx, rsi; char *
0x180071c60  mov     rcx, rax; this
0x180071c63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071c68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071c6f  jb      short loc_180071C94
0x180071c71  mov     edx, 0D3h
0x180071c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c7d  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180071c84  mov     r9, rbx
0x180071c87  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180071c8b  mov     rcx, [rcx+10h]
0x180071c8f  call    WPP_SF_qD
0x180071c94  lea     rcx, [rbp+57h+var_70]; this
0x180071c98  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180071c9d  mov     eax, edi
0x180071c9f  mov     rcx, [rbp+57h+var_48]
0x180071ca3  xor     rcx, rsp; StackCookie
0x180071ca6  call    __security_check_cookie
0x180071cab  lea     r11, [rsp+0E0h+var_10]
0x180071cb3  mov     rbx, [r11+30h]
0x180071cb7  movaps  xmm6, xmmword ptr [r11-10h]
0x180071cbc  movaps  xmm7, xmmword ptr [r11-20h]
0x180071cc1  movaps  xmm8, xmmword ptr [r11-30h]
0x180071cc6  mov     rsp, r11
0x180071cc9  pop     rdi
0x180071cca  pop     rsi
0x180071ccb  pop     rbp
0x180071ccc  retn
```
