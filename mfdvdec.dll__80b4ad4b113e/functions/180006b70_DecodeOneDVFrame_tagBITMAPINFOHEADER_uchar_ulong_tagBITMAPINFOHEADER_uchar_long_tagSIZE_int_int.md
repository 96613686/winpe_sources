# DecodeOneDVFrame(tagBITMAPINFOHEADER *,uchar *,ulong,tagBITMAPINFOHEADER *,uchar *,long,tagSIZE *,int *,int *)

- ea: `0x180006b70`
- end: `0x180006fcc`
- name: `?DecodeOneDVFrame@@YAJPEAUtagBITMAPINFOHEADER@@PEAEK01JPEAUtagSIZE@@PEAH3@Z`
- size: `1116`
- prototype: `__int64 __fastcall(struct tagBITMAPINFOHEADER *, unsigned __int8 *, unsigned int, struct tagBITMAPINFOHEADER *, unsigned __int8 *, int, struct tagSIZE *, int *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180002ac0`

## callees

- `0x180001160`
- `0x18000116c`
- `0x180001ec8`
- `0x180002200`
- `0x180006950`
- `0x180006af4`
- `0x180006b70`
- `0x180006fd4`
- `0x18000786c`
- `0x180007938`
- `0x180007968`
- `0x1800082ec`
- `0x180008358`
- `0x18000a064`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006bd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006c79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006df7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006eec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006bd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006c79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006df7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006eec`

## pseudocode

```c
__int64 __fastcall DecodeOneDVFrame(
        struct tagBITMAPINFOHEADER *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct tagBITMAPINFOHEADER *a4,
        unsigned __int8 *a5,
        int a6,
        struct tagSIZE *a7,
        int *a8,
        int *a9)
{
  int DVCodecReq; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // edx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned int v20; // edi
  bool v21; // zf
  unsigned __int8 *v22; // rcx
  int v23; // eax
  void *v24; // rax
  void *v25; // r14
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  int v28; // r8d
  unsigned int v29; // edi
  unsigned __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct CallStackContext *v35; // rax
  int v36; // ecx
  int v37; // ecx
  _BYTE *v39; // [rsp+30h] [rbp-48h]
  struct tagSIZE v40; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v41; // [rsp+90h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "DecodeOneDVFrame", 473);
  v41 = 0;
  v40 = 0;
  if ( a3 < 0x1E0 )
  {
    DVCodecReq = -1072861838;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v14;
      if ( !v14 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v15 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v15 + 499) != -1072861838 )
        CallStackContext::TraceFailure(v15, "DecodeOneDVFrame", 485, -1072861838);
    }
    if ( g_wppLevels )
    {
      v16 = 19;
LABEL_63:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids,
        0,
        DVCodecReq);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  DVCodecReq = GetDVCodecReq(a1, a4, &v41);
  if ( DVCodecReq >= 0 )
  {
    v20 = v41;
    if ( a2[448] != 96 || ((a2[451] & 0x20) == 0 ? (v21 = (v41 & 0x10) == 0) : (v21 = (v41 & 0x20) == 0), v21) )
    {
      if ( (unsigned __int8)byte_180024A4D >= 0x20u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27));
    }
    v22 = a2;
    if ( a3 == 120000 )
    {
      v17 = 10;
    }
    else
    {
      if ( a3 != 144000 )
        goto LABEL_41;
      v17 = 12;
    }
    v23 = 0;
    while ( (*v22 & 0xE0) != 0 )
    {
      v22 += 12000;
      if ( ++v23 >= v17 )
        goto LABEL_41;
    }
    LOBYTE(v17) = 3;
    if ( (v22[4] & 3) == 1 && (v22[5] & 3) == 1 && (v22[6] & 3) == 1 && (v22[7] & 3) == 1 )
      v20 |= 0x20000u;
LABEL_41:
    GetInterlaceAspectRatioInfo(a2, v17, &v40, a8, a9);
    CalcPixelAspectRatio(a1->biWidth, a1->biHeight, &v40, a7);
    v24 = operator new[](0x6B700u);
    v25 = v24;
    if ( v24 )
    {
      v28 = (int)a5;
      v39 = (_BYTE *)(((unsigned __int64)v24 + 63) & 0xFFFFFFFFFFFFFFC0uLL);
      *v39 = 0;
      v29 = DvDecodeAFrame((_DWORD)a2, a3, v28, a4->biSizeImage, v20, a6, (__int64)v39);
      operator delete(v25, v30);
      if ( v29 )
      {
        if ( (unsigned __int8)byte_180024A4D >= 0x20u )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 27), v31, v32, v29);
        DVCodecReq = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v33;
          if ( !v33 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v34 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v34 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v34, "DecodeOneDVFrame", 515, -2147467259);
        }
        if ( g_wppLevels )
        {
          v16 = 24;
          goto LABEL_63;
        }
      }
    }
    else
    {
      DVCodecReq = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v26;
        if ( !v26 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v27 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v27 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v27, "DecodeOneDVFrame", 500, -2147024882);
      }
      if ( g_wppLevels )
      {
        v16 = 22;
        goto LABEL_63;
      }
    }
    goto LABEL_64;
  }
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v18;
    if ( !v18 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v19 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v19 + 499) != DVCodecReq )
      CallStackContext::TraceFailure(v19, "DecodeOneDVFrame", 488, DVCodecReq);
  }
  if ( g_wppLevels )
  {
    v16 = 20;
    goto LABEL_63;
  }
LABEL_64:
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v35 = CallStackTracing::Context(CallStackTracing::s_wpInstance);
    v36 = *((_DWORD *)v35 + 497);
    if ( v36 )
    {
      v37 = v36 - 1;
      *((_DWORD *)v35 + 497) = v37;
      if ( !v37 )
        CallStackContext::ClearState(v35);
    }
  }
  return (unsigned int)DVCodecReq;
}

```

## disassembly

```asm
0x180006b70  mov     rax, rsp
0x180006b73  mov     [rax+8], rbx
0x180006b77  mov     [rax+10h], rbp
0x180006b7b  push    rsi
0x180006b7c  push    rdi
0x180006b7d  push    r12
0x180006b7f  push    r14
0x180006b81  push    r15
0x180006b83  sub     rsp, 50h
0x180006b87  mov     ebp, r8d
0x180006b8a  lea     rdi, aDecodeonedvfra; "DecodeOneDVFrame"
0x180006b91  mov     rsi, rdx
0x180006b94  mov     r14, rcx
0x180006b97  mov     rdx, rdi; char *
0x180006b9a  lea     rcx, [rax+18h]; this
0x180006b9e  mov     r8d, 1D9h; int
0x180006ba4  mov     r15, r9
0x180006ba7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180006bac  xor     r12d, r12d
0x180006baf  mov     [rsp+78h+arg_10], r12d
0x180006bb7  mov     qword ptr [rsp+78h+var_38.cx], r12
0x180006bbc  cmp     ebp, 1E0h
0x180006bc2  jnb     loc_180006C53
0x180006bc8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180006bcf  mov     ebx, 0C00D6D72h
0x180006bd4  jnz     short loc_180006C0E
0x180006bd6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180006bdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006be3  mov     rcx, rax
0x180006be6  test    rax, rax
0x180006be9  jz      short loc_180006C00
0x180006beb  mov     rax, [rax]
0x180006bee  mov     edx, 7F0h
0x180006bf3  mov     rax, [rax+8]
0x180006bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bfc  test    eax, eax
0x180006bfe  jnz     short loc_180006C0E
0x180006c00  lea     rax, off_180022080
0x180006c07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006c0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006c15  cmp     [rcx+8], r12b
0x180006c19  jz      short loc_180006C3C
0x180006c1b  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006c20  cmp     [rax+7CCh], ebx
0x180006c26  jz      short loc_180006C3C
0x180006c28  mov     r9d, ebx; int
0x180006c2b  mov     r8d, 1E5h; int
0x180006c31  mov     rdx, rdi; char *
0x180006c34  mov     rcx, rax; this
0x180006c37  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006c3c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180006c43  jb      loc_180006F82
0x180006c49  mov     edx, 13h
0x180006c4e  jmp     loc_180006F64
0x180006c53  lea     r8, [rsp+78h+arg_10]; unsigned int *
0x180006c5b  mov     rdx, r15; struct tagBITMAPINFOHEADER *
0x180006c5e  mov     rcx, r14; struct tagBITMAPINFOHEADER *
0x180006c61  call    ?GetDVCodecReq@@YAJPEAUtagBITMAPINFOHEADER@@0PEAK@Z; GetDVCodecReq(tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER *,ulong *)
0x180006c66  mov     ebx, eax
0x180006c68  test    eax, eax
0x180006c6a  jns     loc_180006CF6
0x180006c70  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180006c77  jnz     short loc_180006CB1
0x180006c79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180006c7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006c86  mov     rcx, rax
0x180006c89  test    rax, rax
0x180006c8c  jz      short loc_180006CA3
0x180006c8e  mov     rdx, [rax]
0x180006c91  mov     rax, [rdx+8]
0x180006c95  mov     edx, 7F0h
0x180006c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9f  test    eax, eax
0x180006ca1  jnz     short loc_180006CB1
0x180006ca3  lea     rax, off_180022080
0x180006caa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006cb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006cb8  cmp     [rcx+8], r12b
0x180006cbc  jz      short loc_180006CDF
0x180006cbe  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006cc3  cmp     [rax+7CCh], ebx
0x180006cc9  jz      short loc_180006CDF
0x180006ccb  mov     r9d, ebx; int
0x180006cce  mov     r8d, 1E8h; int
0x180006cd4  mov     rdx, rdi; char *
0x180006cd7  mov     rcx, rax; this
0x180006cda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006cdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180006ce6  jb      loc_180006F82
0x180006cec  mov     edx, 14h
0x180006cf1  jmp     loc_180006F64
0x180006cf6  cmp     byte ptr [rsi+1C0h], 60h ; '`'
0x180006cfd  mov     edi, [rsp+78h+arg_10]
0x180006d04  jnz     short loc_180006D1B
0x180006d06  test    byte ptr [rsi+1C3h], 20h
0x180006d0d  jz      short loc_180006D15
0x180006d0f  test    dil, 20h
0x180006d13  jmp     short loc_180006D19
0x180006d15  test    dil, 10h
0x180006d19  jnz     short loc_180006D37
0x180006d1b  cmp     cs:byte_180024A4D, 20h ; ' '
0x180006d22  jb      short loc_180006D37
0x180006d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d2b  mov     rcx, [rcx+0D8h]
0x180006d32  call    WPP_SF_
0x180006d37  mov     rcx, rsi
0x180006d3a  cmp     ebp, 1D4C0h
0x180006d40  jnz     short loc_180006D49
0x180006d42  mov     edx, 0Ah
0x180006d47  jmp     short loc_180006D56
0x180006d49  cmp     ebp, 23280h
0x180006d4f  jnz     short loc_180006D97
0x180006d51  mov     edx, 0Ch
0x180006d56  mov     eax, r12d
0x180006d59  test    byte ptr [rcx], 0E0h
0x180006d5c  jz      short loc_180006D6D
0x180006d5e  add     rcx, 2EE0h
0x180006d65  inc     eax
0x180006d67  cmp     eax, edx
0x180006d69  jb      short loc_180006D59
0x180006d6b  jmp     short loc_180006D97
0x180006d6d  mov     al, [rcx+4]
0x180006d70  mov     dl, 3; unsigned int
0x180006d72  and     al, dl
0x180006d74  cmp     al, 1
0x180006d76  jnz     short loc_180006D97
0x180006d78  mov     al, [rcx+5]
0x180006d7b  and     al, dl
0x180006d7d  cmp     al, 1
0x180006d7f  jnz     short loc_180006D97
0x180006d81  mov     al, [rcx+6]
0x180006d84  and     al, dl
0x180006d86  cmp     al, 1
0x180006d88  jnz     short loc_180006D97
0x180006d8a  mov     al, [rcx+7]
0x180006d8d  and     al, dl
0x180006d8f  cmp     al, 1
0x180006d91  jnz     short loc_180006D97
0x180006d93  bts     edi, 11h
0x180006d97  mov     rax, [rsp+78h+arg_40]
0x180006d9f  lea     r8, [rsp+78h+var_38]; struct tagSIZE *
0x180006da4  mov     r9, [rsp+78h+arg_38]; int *
0x180006dac  mov     rcx, rsi; unsigned __int8 *
0x180006daf  mov     [rsp+78h+var_58], rax; int *
0x180006db4  call    ?GetInterlaceAspectRatioInfo@@YAXPEAEKPEAUtagSIZE@@PEAH2@Z; GetInterlaceAspectRatioInfo(uchar *,ulong,tagSIZE *,int *,int *)
0x180006db9  mov     r9, [rsp+78h+arg_30]; struct tagSIZE *
0x180006dc1  lea     r8, [rsp+78h+var_38]; struct tagSIZE *
0x180006dc6  mov     edx, [r14+8]; int
0x180006dca  mov     ecx, [r14+4]; int
0x180006dce  call    ?CalcPixelAspectRatio@@YAXJJAEBUtagSIZE@@PEAU1@@Z; CalcPixelAspectRatio(long,long,tagSIZE const &,tagSIZE *)
0x180006dd3  mov     ecx, 6B700h; unsigned __int64
0x180006dd8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006ddd  mov     r14, rax
0x180006de0  test    rax, rax
0x180006de3  jnz     loc_180006E78
0x180006de9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180006df0  mov     ebx, 8007000Eh
0x180006df5  jnz     short loc_180006E2F
0x180006df7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180006dfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006e04  mov     rcx, rax
0x180006e07  test    rax, rax
0x180006e0a  jz      short loc_180006E21
0x180006e0c  mov     rax, [rax]
0x180006e0f  mov     edx, 7F0h
0x180006e14  mov     rax, [rax+8]
0x180006e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1d  test    eax, eax
0x180006e1f  jnz     short loc_180006E2F
0x180006e21  lea     rax, off_180022080
0x180006e28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006e2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006e36  cmp     [rcx+8], r12b
0x180006e3a  jz      short loc_180006E61
0x180006e3c  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006e41  cmp     [rax+7CCh], ebx
0x180006e47  jz      short loc_180006E61
0x180006e49  mov     r9d, ebx; int
0x180006e4c  lea     rdx, aDecodeonedvfra; "DecodeOneDVFrame"
0x180006e53  mov     r8d, 1F4h; int
0x180006e59  mov     rcx, rax; this
0x180006e5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006e61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180006e68  jb      loc_180006F82
0x180006e6e  mov     edx, 16h
0x180006e73  jmp     loc_180006F64
0x180006e78  mov     r8, [rsp+78h+arg_20]
0x180006e80  add     rax, 3Fh ; '?'
0x180006e84  and     rax, 0FFFFFFFFFFFFFFC0h
0x180006e88  mov     edx, ebp
0x180006e8a  mov     [rsp+78h+var_48], rax
0x180006e8f  mov     rcx, rsi
0x180006e92  mov     [rax], r12b
0x180006e95  mov     eax, [rsp+78h+arg_28]
0x180006e9c  mov     r9d, [r15+14h]
0x180006ea0  mov     [rsp+78h+var_50], eax
0x180006ea4  mov     dword ptr [rsp+78h+var_58], edi
0x180006ea8  call    DvDecodeAFrame
0x180006ead  mov     rcx, r14; void *
0x180006eb0  mov     edi, eax
0x180006eb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006eb7  test    edi, edi
0x180006eb9  jz      loc_180006F82
0x180006ebf  cmp     cs:byte_180024A4D, 20h ; ' '
0x180006ec6  jb      short loc_180006EDE
0x180006ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ecf  mov     r9d, edi
0x180006ed2  mov     rcx, [rcx+0D8h]
0x180006ed9  call    WPP_SF_D
0x180006ede  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180006ee5  mov     ebx, 80004005h
0x180006eea  jnz     short loc_180006F24
0x180006eec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180006ef2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006ef9  mov     rcx, rax
0x180006efc  test    rax, rax
0x180006eff  jz      short loc_180006F16
0x180006f01  mov     rax, [rax]
0x180006f04  mov     edx, 7F0h
0x180006f09  mov     rax, [rax+8]
0x180006f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f12  test    eax, eax
0x180006f14  jnz     short loc_180006F24
0x180006f16  lea     rax, off_180022080
0x180006f1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006f24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006f2b  cmp     [rcx+8], r12b
0x180006f2f  jz      short loc_180006F56
0x180006f31  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006f36  cmp     [rax+7CCh], ebx
0x180006f3c  jz      short loc_180006F56
0x180006f3e  mov     r9d, ebx; int
0x180006f41  lea     rdx, aDecodeonedvfra; "DecodeOneDVFrame"
0x180006f48  mov     r8d, 203h; int
0x180006f4e  mov     rcx, rax; this
0x180006f51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180006f56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180006f5d  jb      short loc_180006F82
0x180006f5f  mov     edx, 18h
0x180006f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f6b  lea     r8, WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids
0x180006f72  xor     r9d, r9d
0x180006f75  mov     dword ptr [rsp+78h+var_58], ebx
0x180006f79  mov     rcx, [rcx+10h]
0x180006f7d  call    WPP_SF_qd
0x180006f82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006f89  cmp     [rcx+8], r12b
0x180006f8d  jz      short loc_180006FB1
0x180006f8f  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180006f94  mov     ecx, [rax+7C4h]
0x180006f9a  test    ecx, ecx
0x180006f9c  jz      short loc_180006FB1
0x180006f9e  sub     ecx, 1
0x180006fa1  mov     [rax+7C4h], ecx
0x180006fa7  jnz     short loc_180006FB1
0x180006fa9  mov     rcx, rax; this
0x180006fac  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180006fb1  lea     r11, [rsp+78h+var_28]
0x180006fb6  mov     eax, ebx
0x180006fb8  mov     rbx, [r11+30h]
0x180006fbc  mov     rbp, [r11+38h]
0x180006fc0  mov     rsp, r11
0x180006fc3  pop     r15
0x180006fc5  pop     r14
0x180006fc7  pop     r12
0x180006fc9  pop     rdi
0x180006fca  pop     rsi
0x180006fcb  retn
```
