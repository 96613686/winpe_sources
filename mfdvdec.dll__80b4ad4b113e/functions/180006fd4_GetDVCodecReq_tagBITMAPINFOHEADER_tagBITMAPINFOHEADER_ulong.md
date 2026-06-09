# GetDVCodecReq(tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER *,ulong *)

- ea: `0x180006fd4`
- end: `0x180007864`
- name: `?GetDVCodecReq@@YAJPEAUtagBITMAPINFOHEADER@@0PEAK@Z`
- size: `2192`
- prototype: `__int64 __fastcall(struct tagBITMAPINFOHEADER *, struct tagBITMAPINFOHEADER *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006b70`

## callees

- `0x180001ec8`
- `0x180002200`
- `0x180006950`
- `0x180006fd4`
- `0x1800082ec`
- `0x180008358`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000703f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800071b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007293`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000736f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000744c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007550`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007628`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800076db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000778e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000703f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800071b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007293`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000736f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000744c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007550`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180007628`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800076db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000778e`

## pseudocode

```c
__int64 __fastcall GetDVCodecReq(struct tagBITMAPINFOHEADER *a1, struct tagBITMAPINFOHEADER *a2, unsigned int *a3)
{
  DWORD biCompression; // eax
  int v5; // eax
  int v6; // r10d
  int v7; // r9d
  void ***v8; // rcx
  unsigned int v9; // edi
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  struct CallStackContext *v13; // rcx
  int v14; // eax
  int v15; // eax
  LONG biWidth; // ecx
  LONG biHeight; // eax
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  int v20; // edx
  int v21; // ecx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  LONG v28; // eax
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  int v31; // r9d
  int v32; // eax
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  void ***v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct CallStackContext *v40; // rax
  int v41; // ecx
  int v42; // ecx
  char v44; // [rsp+60h] [rbp+8h] BYREF

  biCompression = a2->biCompression;
  if ( biCompression == 844715353 )
  {
    v5 = 16448;
    v6 = 8256;
    v7 = 32832;
    goto LABEL_24;
  }
  if ( biCompression && biCompression != 3 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 138);
    v8 = (void ***)CallStackTracing::s_wpInstance;
    v9 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (void ***)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &off_180022080;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::Context((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v11, "GetDVCodecReq", 138, -2147024809);
      v8 = (void ***)CallStackTracing::s_wpInstance;
    }
    if ( g_wppLevels )
    {
      v12 = 11;
LABEL_16:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids,
        0,
        -2147024809);
LABEL_17:
      v8 = (void ***)CallStackTracing::s_wpInstance;
    }
LABEL_18:
    if ( *((_BYTE *)v8 + 8) )
    {
      v13 = CallStackTracing::Context((CallStackTracing *)v8);
      v14 = *((_DWORD *)v13 + 497);
      if ( v14 )
      {
        v15 = v14 - 1;
        *((_DWORD *)v13 + 497) = v15;
        if ( !v15 )
          goto LABEL_150;
      }
    }
    return v9;
  }
  if ( a2->biBitCount == 32 )
  {
    v5 = 20736;
    v6 = 12544;
    v7 = 37120;
LABEL_24:
    if ( a1->biCompression != 1819506276 )
    {
      if ( a1->biCompression == 1684567652 )
      {
        v7 = v5;
      }
      else
      {
        if ( a1->biCompression != 1685288548 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 168);
          v8 = (void ***)CallStackTracing::s_wpInstance;
          v9 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v8 = (void ***)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &off_180022080;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v36 = CallStackTracing::Context((CallStackTracing *)v8);
            if ( *((_DWORD *)v36 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v36, "GetDVCodecReq", 168, -2147024809);
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          if ( g_wppLevels )
          {
            v12 = 12;
            goto LABEL_16;
          }
          goto LABEL_18;
        }
        v7 = v6;
      }
    }
    biWidth = a2->biWidth;
    biHeight = a2->biHeight;
    switch ( biWidth )
    {
      case 88:
        if ( biHeight != 60 && biHeight != 72 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 175);
          v8 = (void ***)CallStackTracing::s_wpInstance;
          v9 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v8 = (void ***)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &off_180022080;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v19 = CallStackTracing::Context((CallStackTracing *)v8);
            if ( *((_DWORD *)v19 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v19, "GetDVCodecReq", 175, -2147024809);
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          if ( g_wppLevels )
          {
            v12 = 13;
            goto LABEL_16;
          }
          goto LABEL_18;
        }
        v20 = 24;
        v21 = 40;
        break;
      case 180:
        if ( biHeight != 120 && biHeight != 144 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 183);
          v8 = (void ***)CallStackTracing::s_wpInstance;
          v9 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v8 = (void ***)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &off_180022080;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v23 = CallStackTracing::Context((CallStackTracing *)v8);
            if ( *((_DWORD *)v23 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v23, "GetDVCodecReq", 183, -2147024809);
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          if ( g_wppLevels )
          {
            v12 = 14;
            goto LABEL_16;
          }
          goto LABEL_18;
        }
        v20 = 20;
        v21 = 36;
        break;
      case 360:
        if ( biHeight != 240 && biHeight != 288 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 191);
          v8 = (void ***)CallStackTracing::s_wpInstance;
          v9 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v8 = (void ***)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &off_180022080;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v25 = CallStackTracing::Context((CallStackTracing *)v8);
            if ( *((_DWORD *)v25 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v25, "GetDVCodecReq", 191, -2147024809);
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          if ( g_wppLevels )
          {
            v12 = 15;
            goto LABEL_16;
          }
          goto LABEL_18;
        }
        v20 = 18;
        v21 = 34;
        break;
      case 720:
        if ( biHeight != 480 && biHeight != 576 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 199);
          v8 = (void ***)CallStackTracing::s_wpInstance;
          v9 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v8 = (void ***)CallStackTracing::s_wpInstance;
            }
            else
            {
              v8 = &off_180022080;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
            }
          }
          if ( *((_BYTE *)v8 + 8) )
          {
            v27 = CallStackTracing::Context((CallStackTracing *)v8);
            if ( *((_DWORD *)v27 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v27, "GetDVCodecReq", 199, -2147024809);
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          if ( g_wppLevels )
          {
            v12 = 16;
            goto LABEL_16;
          }
          goto LABEL_18;
        }
        v20 = 17;
        v21 = 33;
        break;
      default:
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 205);
        v8 = (void ***)CallStackTracing::s_wpInstance;
        v9 = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          else
          {
            v8 = &off_180022080;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
          }
        }
        if ( *((_BYTE *)v8 + 8) )
        {
          v34 = CallStackTracing::Context((CallStackTracing *)v8);
          if ( *((_DWORD *)v34 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v34, "GetDVCodecReq", 205, -2147024809);
          v8 = (void ***)CallStackTracing::s_wpInstance;
        }
        if ( g_wppLevels )
        {
          v12 = 17;
          goto LABEL_16;
        }
        goto LABEL_18;
    }
    v28 = a1->biHeight;
    if ( v28 == 480 || v28 == 240 || v28 == 120 || v28 == 60 )
    {
      v31 = v20 | v7;
    }
    else
    {
      if ( v28 != 576 && v28 != 288 && v28 != 144 && v28 != 72 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 222);
        v8 = (void ***)CallStackTracing::s_wpInstance;
        v9 = -2147467259;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v8 = (void ***)CallStackTracing::s_wpInstance;
          }
          else
          {
            v8 = &off_180022080;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
          }
        }
        if ( *((_BYTE *)v8 + 8) )
        {
          v30 = CallStackTracing::Context((CallStackTracing *)v8);
          if ( *((_DWORD *)v30 + 499) != -2147467259 )
            CallStackContext::TraceFailure(v30, "GetDVCodecReq", 222, -2147467259);
          v8 = (void ***)CallStackTracing::s_wpInstance;
        }
        if ( g_wppLevels )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids,
            0,
            -2147467259);
          goto LABEL_17;
        }
        goto LABEL_18;
      }
      v31 = v21 | v7;
    }
    v9 = 0;
    v32 = v31 | 0x2000000;
    if ( (v31 & 1) == 0 )
      v32 = v31;
    *a3 = v32;
    return v9;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "GetDVCodecReq", 133);
  v37 = (void ***)CallStackTracing::s_wpInstance;
  v9 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v37 = (void ***)CallStackTracing::s_wpInstance;
    }
    else
    {
      v37 = &off_180022080;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v39 = CallStackTracing::Context((CallStackTracing *)v37);
    if ( *((_DWORD *)v39 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v39, "GetDVCodecReq", 133, -2147024809);
    v37 = (void ***)CallStackTracing::s_wpInstance;
  }
  if ( g_wppLevels )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids, 0, -2147024809);
    v37 = (void ***)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v40 = CallStackTracing::Context((CallStackTracing *)v37);
    v41 = *((_DWORD *)v40 + 497);
    if ( v41 )
    {
      v42 = v41 - 1;
      *((_DWORD *)v40 + 497) = v42;
      if ( !v42 )
      {
        v13 = v40;
LABEL_150:
        CallStackContext::ClearState(v13);
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180006fd4  push    rbx
0x180006fd6  push    rbp
0x180006fd7  push    rsi
0x180006fd8  push    rdi
0x180006fd9  sub     rsp, 38h
0x180006fdd  mov     eax, [rdx+10h]
0x180006fe0  xor     esi, esi
0x180006fe2  mov     r11, rcx
0x180006fe5  cmp     eax, 32595559h
0x180006fea  jnz     short loc_180007002
0x180006fec  mov     eax, 4040h
0x180006ff1  mov     r10d, 2040h
0x180006ff7  mov     r9d, 8040h
0x180006ffd  jmp     loc_180007132
0x180007002  test    eax, eax
0x180007004  jz      loc_180007116
0x18000700a  cmp     eax, 3
0x18000700d  jz      loc_180007116
0x180007013  mov     ebp, 8Ah
0x180007018  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x18000701f  mov     r8d, ebp; int
0x180007022  lea     rcx, [rsp+58h+arg_0]; this
0x180007027  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000702c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007033  mov     ebx, 80070057h
0x180007038  mov     edi, ebx
0x18000703a  test    rcx, rcx
0x18000703d  jnz     short loc_180007080
0x18000703f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180007045  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000704c  mov     rcx, rax
0x18000704f  test    rax, rax
0x180007052  jz      short loc_180007072
0x180007054  mov     rax, [rax]
0x180007057  mov     edx, 7F0h
0x18000705c  mov     rax, [rax+8]
0x180007060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007065  test    eax, eax
0x180007067  jz      short loc_180007072
0x180007069  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007070  jmp     short loc_180007080
0x180007072  lea     rcx, off_180022080; this
0x180007079  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180007080  cmp     [rcx+8], sil
0x180007084  jz      short loc_1800070AF
0x180007086  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x18000708b  cmp     [rax+7CCh], ebx
0x180007091  jz      short loc_1800070A8
0x180007093  mov     r9d, ebx; int
0x180007096  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x18000709d  mov     r8d, ebp; int
0x1800070a0  mov     rcx, rax; this
0x1800070a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800070a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800070af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800070b6  jb      short loc_1800070E2
0x1800070b8  mov     edx, 0Bh
0x1800070bd  mov     [rsp+58h+var_38], ebx
0x1800070c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070c8  lea     r8, WPP_524693c28da23ae8ba1ebb68770bc5f8_Traceguids
0x1800070cf  xor     r9d, r9d
0x1800070d2  mov     rcx, [rcx+10h]
0x1800070d6  call    WPP_SF_qd
0x1800070db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800070e2  cmp     [rcx+8], sil
0x1800070e6  jz      loc_180007859
0x1800070ec  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800070f1  mov     rcx, rax
0x1800070f4  mov     eax, [rax+7C4h]
0x1800070fa  test    eax, eax
0x1800070fc  jz      loc_180007859
0x180007102  sub     eax, 1
0x180007105  mov     [rcx+7C4h], eax
0x18000710b  jnz     loc_180007859
0x180007111  jmp     loc_180007854
0x180007116  cmp     word ptr [rdx+0Eh], 20h ; ' '
0x18000711b  jnz     loc_180007762
0x180007121  mov     eax, 5100h
0x180007126  mov     r10d, 3100h
0x18000712c  mov     r9d, 9100h
0x180007132  cmp     dword ptr [rcx+10h], 6C737664h
0x180007139  jz      short loc_180007159
0x18000713b  cmp     dword ptr [rcx+10h], 64687664h
0x180007142  jnz     short loc_180007149
0x180007144  mov     r9d, eax
0x180007147  jmp     short loc_180007159
0x180007149  cmp     dword ptr [rcx+10h], 64737664h
0x180007150  jnz     loc_1800076AF
0x180007156  mov     r9d, r10d
0x180007159  mov     ecx, [rdx+4]
0x18000715c  mov     edi, 240h
0x180007161  mov     eax, [rdx+8]
0x180007164  mov     ebx, 0F0h
0x180007169  lea     r10d, [rdi-60h]
0x18000716d  lea     ebp, [rbx+30h]
0x180007170  cmp     ecx, 58h ; 'X'
0x180007173  jnz     loc_180007249
0x180007179  cmp     eax, 3Ch ; '<'
0x18000717c  jz      loc_18000723C
0x180007182  cmp     eax, 48h ; 'H'
0x180007185  jz      loc_18000723C
0x18000718b  lea     ebp, [rcx+57h]
0x18000718e  mov     r8d, ebp; int
0x180007191  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x180007198  lea     rcx, [rsp+58h+arg_0]; this
0x18000719d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800071a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800071a9  mov     ebx, 80070057h
0x1800071ae  mov     edi, ebx
0x1800071b0  test    rcx, rcx
0x1800071b3  jnz     short loc_1800071F6
0x1800071b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800071bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800071c2  mov     rcx, rax
0x1800071c5  test    rax, rax
0x1800071c8  jz      short loc_1800071E8
0x1800071ca  mov     rax, [rax]
0x1800071cd  mov     edx, 7F0h
0x1800071d2  mov     rax, [rax+8]
0x1800071d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071db  test    eax, eax
0x1800071dd  jz      short loc_1800071E8
0x1800071df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800071e6  jmp     short loc_1800071F6
0x1800071e8  lea     rcx, off_180022080; this
0x1800071ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800071f6  cmp     [rcx+8], sil
0x1800071fa  jz      short loc_180007225
0x1800071fc  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180007201  cmp     [rax+7CCh], ebx
0x180007207  jz      short loc_18000721E
0x180007209  mov     r9d, ebx; int
0x18000720c  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x180007213  mov     r8d, ebp; int
0x180007216  mov     rcx, rax; this
0x180007219  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000721e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007225  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000722c  jb      loc_1800070E2
0x180007232  mov     edx, 0Dh
0x180007237  jmp     loc_1800070BD
0x18000723c  mov     edx, 18h
0x180007241  lea     ecx, [rdx+10h]
0x180007244  jmp     loc_1800074DB
0x180007249  cmp     ecx, 0B4h
0x18000724f  jnz     loc_180007327
0x180007255  cmp     eax, 78h ; 'x'
0x180007258  jz      loc_18000731A
0x18000725e  cmp     eax, 90h
0x180007263  jz      loc_18000731A
0x180007269  lea     ebp, [rcx+3]
0x18000726c  mov     r8d, ebp; int
0x18000726f  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x180007276  lea     rcx, [rsp+58h+arg_0]; this
0x18000727b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180007280  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007287  mov     ebx, 80070057h
0x18000728c  mov     edi, ebx
0x18000728e  test    rcx, rcx
0x180007291  jnz     short loc_1800072D4
0x180007293  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180007299  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800072a0  mov     rcx, rax
0x1800072a3  test    rax, rax
0x1800072a6  jz      short loc_1800072C6
0x1800072a8  mov     rax, [rax]
0x1800072ab  mov     edx, 7F0h
0x1800072b0  mov     rax, [rax+8]
0x1800072b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b9  test    eax, eax
0x1800072bb  jz      short loc_1800072C6
0x1800072bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800072c4  jmp     short loc_1800072D4
0x1800072c6  lea     rcx, off_180022080; this
0x1800072cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800072d4  cmp     [rcx+8], sil
0x1800072d8  jz      short loc_180007303
0x1800072da  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800072df  cmp     [rax+7CCh], ebx
0x1800072e5  jz      short loc_1800072FC
0x1800072e7  mov     r9d, ebx; int
0x1800072ea  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x1800072f1  mov     r8d, ebp; int
0x1800072f4  mov     rcx, rax; this
0x1800072f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800072fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007303  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000730a  jb      loc_1800070E2
0x180007310  mov     edx, 0Eh
0x180007315  jmp     loc_1800070BD
0x18000731a  mov     edx, 14h
0x18000731f  lea     ecx, [rdx+10h]
0x180007322  jmp     loc_1800074DB
0x180007327  cmp     ecx, 168h
0x18000732d  jnz     loc_180007403
0x180007333  cmp     eax, ebx
0x180007335  jz      loc_1800073F6
0x18000733b  cmp     eax, ebp
0x18000733d  jz      loc_1800073F6
0x180007343  mov     ebp, 0BFh
0x180007348  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x18000734f  mov     r8d, ebp; int
0x180007352  lea     rcx, [rsp+58h+arg_0]; this
0x180007357  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000735c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007363  mov     ebx, 80070057h
0x180007368  mov     edi, ebx
0x18000736a  test    rcx, rcx
0x18000736d  jnz     short loc_1800073B0
0x18000736f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180007375  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000737c  mov     rcx, rax
0x18000737f  test    rax, rax
0x180007382  jz      short loc_1800073A2
0x180007384  mov     rax, [rax]
0x180007387  mov     edx, 7F0h
0x18000738c  mov     rax, [rax+8]
0x180007390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007395  test    eax, eax
0x180007397  jz      short loc_1800073A2
0x180007399  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800073a0  jmp     short loc_1800073B0
0x1800073a2  lea     rcx, off_180022080; this
0x1800073a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800073b0  cmp     [rcx+8], sil
0x1800073b4  jz      short loc_1800073DF
0x1800073b6  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x1800073bb  cmp     [rax+7CCh], ebx
0x1800073c1  jz      short loc_1800073D8
0x1800073c3  mov     r9d, ebx; int
0x1800073c6  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x1800073cd  mov     r8d, ebp; int
0x1800073d0  mov     rcx, rax; this
0x1800073d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800073d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800073df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800073e6  jb      loc_1800070E2
0x1800073ec  mov     edx, 0Fh
0x1800073f1  jmp     loc_1800070BD
0x1800073f6  mov     edx, 12h
0x1800073fb  lea     ecx, [rdx+10h]
0x1800073fe  jmp     loc_1800074DB
0x180007403  cmp     ecx, 2D0h
0x180007409  jnz     loc_1800075FC
0x18000740f  cmp     eax, r10d
0x180007412  jz      loc_1800074D3
0x180007418  cmp     eax, edi
0x18000741a  jz      loc_1800074D3
0x180007420  mov     ebp, 0C7h
0x180007425  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x18000742c  mov     r8d, ebp; int
0x18000742f  lea     rcx, [rsp+58h+arg_0]; this
0x180007434  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180007439  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007440  mov     ebx, 80070057h
0x180007445  mov     edi, ebx
0x180007447  test    rcx, rcx
0x18000744a  jnz     short loc_18000748D
0x18000744c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180007452  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180007459  mov     rcx, rax
0x18000745c  test    rax, rax
0x18000745f  jz      short loc_18000747F
0x180007461  mov     rax, [rax]
0x180007464  mov     edx, 7F0h
0x180007469  mov     rax, [rax+8]
0x18000746d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007472  test    eax, eax
0x180007474  jz      short loc_18000747F
0x180007476  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000747d  jmp     short loc_18000748D
0x18000747f  lea     rcx, off_180022080; this
0x180007486  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000748d  cmp     [rcx+8], sil
0x180007491  jz      short loc_1800074BC
0x180007493  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180007498  cmp     [rax+7CCh], ebx
0x18000749e  jz      short loc_1800074B5
0x1800074a0  mov     r9d, ebx; int
0x1800074a3  lea     rdx, aGetdvcodecreq; "GetDVCodecReq"
0x1800074aa  mov     r8d, ebp; int
0x1800074ad  mov     rcx, rax; this
0x1800074b0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800074b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800074bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800074c3  jb      loc_1800070E2
0x1800074c9  mov     edx, 10h
0x1800074ce  jmp     loc_1800070BD
0x1800074d3  mov     edx, 11h
0x1800074d8  lea     ecx, [rdx+10h]
0x1800074db  mov     eax, [r11+8]
0x1800074df  cmp     eax, r10d
0x1800074e2  jz      loc_1800075E0
0x1800074e8  cmp     eax, ebx
0x1800074ea  jz      loc_1800075E0
0x1800074f0  cmp     eax, 78h ; 'x'
0x1800074f3  jz      loc_1800075E0
0x1800074f9  cmp     eax, 3Ch ; '<'
0x1800074fc  jz      loc_1800075E0
0x180007502  cmp     eax, edi
  ... truncated ...
```
