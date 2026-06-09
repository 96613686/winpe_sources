# CMFFile::_CreateTempFile(__MIDL___MIDL_itf_mfobjects_0000_0018_0001,__MIDL___MIDL_itf_mfobjects_0000_0018_0002,__MIDL___MIDL_itf_mfobjects_0000_0018_0003,IMFByteStream * *)

- ea: `0x18011bacc`
- end: `0x18011c3e9`
- name: `?_CreateTempFile@CMFFile@@SAJW4__MIDL___MIDL_itf_mfobjects_0000_0018_0001@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0002@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0003@@PEAPEAUIMFByteStream@@@Z`
- size: `2333`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180124ed0`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800572d0`
- `0x180092198`
- `0x180098ecc`
- `0x1800aae54`
- `0x18011bacc`
- `0x18011fff0`
- `0x180120030`
- `0x18012003c`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bbd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bf99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bfd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bbd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bf99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011bfd3`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18011bbc8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18011bd4b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18011bbc8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18011bd4b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18011bfc9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18011bfc9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x18011bf8f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x18011bf8f`

## string_xrefs

- `0x18011bafa`: `CMFFile::_CreateTempFile`
- `0x18011bb8b`: `CMFFile::_CreateTempFile`
- `0x18011bc58`: `CMFFile::_CreateTempFile`
- `0x18011bd1a`: `CMFFile::_CreateTempFile`
- `0x18011bdd9`: `CMFFile::_CreateTempFile`
- `0x18011be78`: `CMFFile::_CreateTempFile`
- `0x18011bf36`: `CMFFile::_CreateTempFile`
- `0x18011c053`: `CMFFile::_CreateTempFile`
- `0x18011c111`: `CMFFile::_CreateTempFile`
- `0x18011c1e0`: `CMFFile::_CreateTempFile`
- `0x18011c29f`: `CMFFile::_CreateTempFile`
- `0x18011c368`: `CMFFile::_CreateTempFile`

## pseudocode

```c
__int64 __fastcall CMFFile::_CreateTempFile(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        volatile signed __int32 **a4)
{
  unsigned __int16 *v8; // r13
  void *v9; // r12
  CallStackTracing *v10; // rcx
  int v11; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  unsigned int TempPath2W; // edi
  signed int LastError; // eax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  void *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  signed int v22; // eax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  unsigned int v25; // ebx
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  unsigned __int64 v28; // rdi
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  HCRYPTPROV v31; // rcx
  signed int v32; // eax
  signed int v33; // eax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CMFFile *v38; // rax
  CMFFile *v39; // rax
  volatile signed __int32 *v40; // rdi
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  __int64 dwFlags; // [rsp+20h] [rbp-298h]
  CallStackScopeTrace v50; // [rsp+40h] [rbp-278h] BYREF
  int v51; // [rsp+44h] [rbp-274h] BYREF
  BYTE pbBuffer[8]; // [rsp+48h] [rbp-270h] BYREF
  _BYTE v53[528]; // [rsp+50h] [rbp-268h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v50, "CMFFile::_CreateTempFile", 165);
  v8 = 0;
  v9 = 0;
  if ( !a4 )
  {
    v10 = CallStackTracing::s_wpInstance;
    v11 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFFile::_CreateTempFile", 176, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v13 = 16;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v11);
      goto LABEL_134;
    }
    goto LABEL_134;
  }
  *a4 = 0;
  TempPath2W = GetTempPath2W(260, v53);
  if ( TempPath2W )
    goto LABEL_25;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_25:
    v18 = operator new[](saturated_mul(TempPath2W + 1, 2u));
    v9 = v18;
    if ( !v18 )
    {
      v19 = CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v19->m_fEnabled )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( v20->m_result != -2147024882 )
          CallStackContext::TraceFailure(v20, "CMFFile::_CreateTempFile", 203, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_134;
      v21 = 18;
      goto LABEL_133;
    }
    if ( !(unsigned int)GetTempPath2W(TempPath2W + 1, v18) )
    {
      v22 = GetLastError();
      v11 = v22;
      if ( v22 > 0 )
        v11 = (unsigned __int16)v22 | 0x80070000;
      if ( v11 < 0 )
      {
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v23 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v23->m_fEnabled )
        {
          v24 = CallStackTracing::GetThreadRelativeContext(v23);
          if ( v24->m_result != v11 )
            CallStackContext::TraceFailure(v24, "CMFFile::_CreateTempFile", 207, v11);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v13 = 19;
          goto LABEL_11;
        }
        goto LABEL_134;
      }
    }
    v25 = TempPath2W + 29;
    if ( TempPath2W + 29 < TempPath2W )
    {
      v26 = CallStackTracing::s_wpInstance;
      v11 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v26->m_fEnabled )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( v27->m_result != -2147418113 )
          CallStackContext::TraceFailure(v27, "CMFFile::_CreateTempFile", 216, -2147418113);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 20;
        goto LABEL_11;
      }
      goto LABEL_134;
    }
    v28 = v25;
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v25, 2u));
    if ( !v25 )
    {
      v29 = CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v29->m_fEnabled )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( v30->m_result != -2147024882 )
          CallStackContext::TraceFailure(v30, "CMFFile::_CreateTempFile", 220, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_134;
      v21 = 21;
      goto LABEL_133;
    }
    v31 = hProv;
    *(_QWORD *)pbBuffer = 0;
    if ( !hProv )
    {
      if ( !CryptAcquireContextA(&hProv, 0, 0, 1u, 0xF0000040) )
      {
        v32 = GetLastError();
        v11 = v32;
        if ( v32 > 0 )
          v11 = (unsigned __int16)v32 | 0x80070000;
        v31 = 0;
        if ( v11 < 0 )
        {
LABEL_80:
          v34 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v34 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v34 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v34->m_fEnabled )
          {
            v35 = CallStackTracing::GetThreadRelativeContext(v34);
            if ( v35->m_result != v11 )
              CallStackContext::TraceFailure(v35, "CMFFile::_CreateTempFile", 224, v11);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v13 = 22;
            goto LABEL_11;
          }
          goto LABEL_134;
        }
LABEL_76:
        if ( !CryptGenRandom(v31, 8u, pbBuffer) )
        {
          v33 = GetLastError();
          v11 = v33;
          if ( v33 > 0 )
            v11 = (unsigned __int16)v33 | 0x80070000;
        }
        if ( v11 < 0 )
          goto LABEL_80;
        LODWORD(dwFlags) = *(_DWORD *)pbBuffer;
        v11 = StringCchPrintfW(v8, v28, L"%sMFP%08X%08X.TMP", v9, dwFlags, *(_DWORD *)&pbBuffer[4]);
        if ( v11 < 0 )
        {
          v36 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v36 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v36->m_fEnabled )
          {
            v37 = CallStackTracing::GetThreadRelativeContext(v36);
            if ( v37->m_result != v11 )
              CallStackContext::TraceFailure(v37, "CMFFile::_CreateTempFile", 231, v11);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v13 = 23;
            goto LABEL_11;
          }
          goto LABEL_134;
        }
        v51 = 0;
        v38 = (CMFFile *)operator new(0x108u);
        if ( !v38 || (v39 = CMFFile::CMFFile(v38, &v51), (v40 = (volatile signed __int32 *)v39) == 0) )
        {
          v46 = CallStackTracing::s_wpInstance;
          v11 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v46 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v46->m_fEnabled )
          {
            v47 = CallStackTracing::GetThreadRelativeContext(v46);
            if ( v47->m_result != -2147024882 )
              CallStackContext::TraceFailure(v47, "CMFFile::_CreateTempFile", 238, -2147024882);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_134;
          v21 = 24;
LABEL_133:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids,
            0,
            -2147024882);
          goto LABEL_134;
        }
        v11 = v51;
        if ( v51 >= 0 )
        {
          v11 = CMFFile::Initialize(v39, a1, a2, a3, 1, v8, -1);
          if ( v11 >= 0 )
          {
            _InterlockedIncrement(v40 + 26);
            *a4 = v40;
            goto LABEL_134;
          }
          v44 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v44 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v44->m_fEnabled )
          {
            v45 = CallStackTracing::GetThreadRelativeContext(v44);
            if ( v45->m_result != v11 )
              CallStackContext::TraceFailure(v45, "CMFFile::_CreateTempFile", 249, v11);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_122;
          v43 = 26;
        }
        else
        {
          v41 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v41 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v41 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v41->m_fEnabled )
          {
            v42 = CallStackTracing::GetThreadRelativeContext(v41);
            if ( v42->m_result != v11 )
              CallStackContext::TraceFailure(v42, "CMFFile::_CreateTempFile", 239, v11);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_122;
          v43 = 25;
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v11);
LABEL_122:
        CMFFile::`scalar deleting destructor'((CMFFile *)v40, 1u);
        goto LABEL_134;
      }
      v31 = hProv;
    }
    v11 = 0;
    goto LABEL_76;
  }
  v16 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v16 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v16->m_fEnabled )
  {
    v17 = CallStackTracing::GetThreadRelativeContext(v16);
    if ( v17->m_result != v11 )
      CallStackContext::TraceFailure(v17, "CMFFile::_CreateTempFile", 199, v11);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v13 = 17;
    goto LABEL_11;
  }
LABEL_134:
  operator delete(v8);
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace(&v50);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18011bacc  push    rbx
0x18011bace  push    rbp
0x18011bacf  push    rsi
0x18011bad0  push    rdi
0x18011bad1  push    r12
0x18011bad3  push    r13
0x18011bad5  push    r14
0x18011bad7  push    r15
0x18011bad9  sub     rsp, 278h
0x18011bae0  mov     rax, cs:__security_cookie
0x18011bae7  xor     rax, rsp
0x18011baea  mov     [rsp+2B8h+var_58], rax
0x18011baf2  mov     r15d, r8d
0x18011baf5  mov     r14d, edx
0x18011baf8  mov     ebp, ecx
0x18011bafa  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bb01  mov     r8d, 0A5h; int
0x18011bb07  lea     rcx, [rsp+2B8h+var_278]; this
0x18011bb0c  mov     rsi, r9
0x18011bb0f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18011bb14  xor     r13d, r13d
0x18011bb17  xor     r12d, r12d
0x18011bb1a  test    rsi, rsi
0x18011bb1d  jnz     loc_18011BBBB
0x18011bb23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bb2a  mov     ebx, 80004003h
0x18011bb2f  test    rcx, rcx
0x18011bb32  jnz     short loc_18011BB75
0x18011bb34  mov     rax, cs:stru_1801FC290.__vftable
0x18011bb3b  lea     r8, stru_1801FC290
0x18011bb42  mov     edx, 7F0h
0x18011bb47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bb4e  mov     rcx, r8
0x18011bb51  mov     rax, [rax+8]
0x18011bb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bb5a  test    eax, eax
0x18011bb5c  jnz     short loc_18011BB6E
0x18011bb5e  lea     rcx, stru_1801F8A30
0x18011bb65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bb6c  jmp     short loc_18011BB75
0x18011bb6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011bb75  cmp     [rcx+8], r12b
0x18011bb79  jz      short loc_18011BBA0
0x18011bb7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bb80  cmp     [rax+7CCh], ebx
0x18011bb86  jz      short loc_18011BBA0
0x18011bb88  mov     r9d, ebx; int
0x18011bb8b  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bb92  mov     r8d, 0B0h; int
0x18011bb98  mov     rcx, rax; this
0x18011bb9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bba0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bba7  jb      loc_18011C3A9
0x18011bbad  mov     edx, 10h
0x18011bbb2  mov     dword ptr [rsp+2B8h+dwFlags], ebx
0x18011bbb6  jmp     loc_18011C38F
0x18011bbbb  lea     rdx, [rsp+2B8h+var_268]
0x18011bbc0  mov     [rsi], r12
0x18011bbc3  mov     ecx, 104h
0x18011bbc8  call    cs:__imp_GetTempPath2W
0x18011bbce  mov     edi, eax
0x18011bbd0  test    eax, eax
0x18011bbd2  jnz     loc_18011BC84
0x18011bbd8  call    cs:__imp_GetLastError
0x18011bbde  mov     ebx, eax
0x18011bbe0  test    eax, eax
0x18011bbe2  jle     short loc_18011BBED
0x18011bbe4  movzx   ebx, ax
0x18011bbe7  or      ebx, 80070000h
0x18011bbed  test    ebx, ebx
0x18011bbef  jns     loc_18011BC84
0x18011bbf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bbfc  test    rcx, rcx
0x18011bbff  jnz     short loc_18011BC42
0x18011bc01  mov     rax, cs:stru_1801FC290.__vftable
0x18011bc08  lea     r8, stru_1801FC290
0x18011bc0f  mov     edx, 7F0h
0x18011bc14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc1b  mov     rcx, r8
0x18011bc1e  mov     rax, [rax+8]
0x18011bc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bc27  test    eax, eax
0x18011bc29  jnz     short loc_18011BC3B
0x18011bc2b  lea     rcx, stru_1801F8A30
0x18011bc32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bc39  jmp     short loc_18011BC42
0x18011bc3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011bc42  cmp     [rcx+8], r12b
0x18011bc46  jz      short loc_18011BC6D
0x18011bc48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bc4d  cmp     [rax+7CCh], ebx
0x18011bc53  jz      short loc_18011BC6D
0x18011bc55  mov     r9d, ebx; int
0x18011bc58  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bc5f  mov     r8d, 0C7h; int
0x18011bc65  mov     rcx, rax; this
0x18011bc68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bc6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bc74  jb      loc_18011C3A9
0x18011bc7a  mov     edx, 11h
0x18011bc7f  jmp     loc_18011BBB2
0x18011bc84  lea     ebx, [rdi+1]
0x18011bc87  mov     eax, 2
0x18011bc8c  mov     ecx, ebx
0x18011bc8e  mul     rcx
0x18011bc91  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18011bc98  cmovb   rax, rcx
0x18011bc9c  mov     rcx, rax; unsigned __int64
0x18011bc9f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18011bca4  mov     r12, rax
0x18011bca7  test    rax, rax
0x18011bcaa  jnz     loc_18011BD46
0x18011bcb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bcb7  mov     edi, 8007000Eh
0x18011bcbc  mov     ebx, edi
0x18011bcbe  test    rcx, rcx
0x18011bcc1  jnz     short loc_18011BD04
0x18011bcc3  mov     rax, cs:stru_1801FC290.__vftable
0x18011bcca  lea     r8, stru_1801FC290
0x18011bcd1  mov     edx, 7F0h
0x18011bcd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bcdd  mov     rcx, r8
0x18011bce0  mov     rax, [rax+8]
0x18011bce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bce9  test    eax, eax
0x18011bceb  jnz     short loc_18011BCFD
0x18011bced  lea     rcx, stru_1801F8A30
0x18011bcf4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bcfb  jmp     short loc_18011BD04
0x18011bcfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011bd04  cmp     [rcx+8], r13b
0x18011bd08  jz      short loc_18011BD2F
0x18011bd0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bd0f  cmp     [rax+7CCh], edi
0x18011bd15  jz      short loc_18011BD2F
0x18011bd17  mov     r9d, edi; int
0x18011bd1a  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bd21  mov     r8d, 0CBh; int
0x18011bd27  mov     rcx, rax; this
0x18011bd2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bd2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bd36  jb      loc_18011C3A9
0x18011bd3c  mov     edx, 12h
0x18011bd41  jmp     loc_18011C38B
0x18011bd46  mov     rdx, r12
0x18011bd49  mov     ecx, ebx
0x18011bd4b  call    cs:__imp_GetTempPath2W
0x18011bd51  test    eax, eax
0x18011bd53  jnz     loc_18011BE05
0x18011bd59  call    cs:__imp_GetLastError
0x18011bd5f  mov     ebx, eax
0x18011bd61  test    eax, eax
0x18011bd63  jle     short loc_18011BD6E
0x18011bd65  movzx   ebx, ax
0x18011bd68  or      ebx, 80070000h
0x18011bd6e  test    ebx, ebx
0x18011bd70  jns     loc_18011BE05
0x18011bd76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bd7d  test    rcx, rcx
0x18011bd80  jnz     short loc_18011BDC3
0x18011bd82  mov     rax, cs:stru_1801FC290.__vftable
0x18011bd89  lea     r8, stru_1801FC290
0x18011bd90  mov     edx, 7F0h
0x18011bd95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bd9c  mov     rcx, r8
0x18011bd9f  mov     rax, [rax+8]
0x18011bda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bda8  test    eax, eax
0x18011bdaa  jnz     short loc_18011BDBC
0x18011bdac  lea     rcx, stru_1801F8A30
0x18011bdb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bdba  jmp     short loc_18011BDC3
0x18011bdbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011bdc3  cmp     [rcx+8], r13b
0x18011bdc7  jz      short loc_18011BDEE
0x18011bdc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bdce  cmp     [rax+7CCh], ebx
0x18011bdd4  jz      short loc_18011BDEE
0x18011bdd6  mov     r9d, ebx; int
0x18011bdd9  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bde0  mov     r8d, 0CFh; int
0x18011bde6  mov     rcx, rax; this
0x18011bde9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bdee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bdf5  jb      loc_18011C3A9
0x18011bdfb  mov     edx, 13h
0x18011be00  jmp     loc_18011BBB2
0x18011be05  lea     ebx, [rdi+1Dh]
0x18011be08  cmp     ebx, edi
0x18011be0a  jnb     loc_18011BEA4
0x18011be10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011be17  mov     ebx, 8000FFFFh
0x18011be1c  test    rcx, rcx
0x18011be1f  jnz     short loc_18011BE62
0x18011be21  mov     rax, cs:stru_1801FC290.__vftable
0x18011be28  lea     r8, stru_1801FC290
0x18011be2f  mov     edx, 7F0h
0x18011be34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011be3b  mov     rcx, r8
0x18011be3e  mov     rax, [rax+8]
0x18011be42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011be47  test    eax, eax
0x18011be49  jnz     short loc_18011BE5B
0x18011be4b  lea     rcx, stru_1801F8A30
0x18011be52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011be59  jmp     short loc_18011BE62
0x18011be5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011be62  cmp     [rcx+8], r13b
0x18011be66  jz      short loc_18011BE8D
0x18011be68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011be6d  cmp     [rax+7CCh], ebx
0x18011be73  jz      short loc_18011BE8D
0x18011be75  mov     r9d, ebx; int
0x18011be78  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011be7f  mov     r8d, 0D8h; int
0x18011be85  mov     rcx, rax; this
0x18011be88  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011be8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011be94  jb      loc_18011C3A9
0x18011be9a  mov     edx, 14h
0x18011be9f  jmp     loc_18011BBB2
0x18011bea4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18011beab  mov     edi, ebx
0x18011bead  mov     eax, 2
0x18011beb2  mul     rdi
0x18011beb5  cmovb   rax, rcx
0x18011beb9  mov     rcx, rax; unsigned __int64
0x18011bebc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18011bec1  mov     r13, rax
0x18011bec4  test    ebx, ebx
0x18011bec6  jnz     loc_18011BF62
0x18011becc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bed3  mov     edi, 8007000Eh
0x18011bed8  mov     ebx, edi
0x18011beda  test    rcx, rcx
0x18011bedd  jnz     short loc_18011BF20
0x18011bedf  mov     rcx, cs:stru_1801FC290.__vftable
0x18011bee6  lea     r8, stru_1801FC290
0x18011beed  mov     edx, 7F0h
0x18011bef2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bef9  mov     rax, [rcx+8]
0x18011befd  mov     rcx, r8
0x18011bf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011bf05  test    eax, eax
0x18011bf07  jnz     short loc_18011BF19
0x18011bf09  lea     rcx, stru_1801F8A30
0x18011bf10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011bf17  jmp     short loc_18011BF20
0x18011bf19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011bf20  cmp     byte ptr [rcx+8], 0
0x18011bf24  jz      short loc_18011BF4B
0x18011bf26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011bf2b  cmp     [rax+7CCh], edi
0x18011bf31  jz      short loc_18011BF4B
0x18011bf33  mov     r9d, edi; int
0x18011bf36  lea     rdx, aCmffileCreatet; "CMFFile::_CreateTempFile"
0x18011bf3d  mov     r8d, 0DCh; int
0x18011bf43  mov     rcx, rax; this
0x18011bf46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011bf4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011bf52  jb      loc_18011C3A9
0x18011bf58  mov     edx, 15h
0x18011bf5d  jmp     loc_18011C38B
0x18011bf62  mov     rcx, cs:hProv
0x18011bf69  mov     qword ptr [rsp+2B8h+pbBuffer], 0
0x18011bf72  test    rcx, rcx
0x18011bf75  jnz     short loc_18011BFBD
0x18011bf77  lea     r9d, [rcx+1]; dwProvType
0x18011bf7b  mov     dword ptr [rsp+2B8h+dwFlags], 0F0000040h; dwFlags
0x18011bf83  lea     rcx, hProv; phProv
0x18011bf8a  xor     r8d, r8d; szProvider
0x18011bf8d  xor     edx, edx; szContainer
0x18011bf8f  call    cs:__imp_CryptAcquireContextA
0x18011bf95  test    eax, eax
0x18011bf97  jnz     short loc_18011BFB6
0x18011bf99  call    cs:__imp_GetLastError
0x18011bf9f  mov     ebx, eax
0x18011bfa1  test    eax, eax
0x18011bfa3  jle     short loc_18011BFAE
0x18011bfa5  movzx   ebx, ax
0x18011bfa8  or      ebx, 80070000h
0x18011bfae  xor     ecx, ecx
0x18011bfb0  test    ebx, ebx
0x18011bfb2  js      short loc_18011BFF0
0x18011bfb4  jmp     short loc_18011BFBF
0x18011bfb6  mov     rcx, cs:hProv; hProv
0x18011bfbd  xor     ebx, ebx
0x18011bfbf  lea     r8, [rsp+2B8h+pbBuffer]; pbBuffer
0x18011bfc4  mov     edx, 8; dwLen
0x18011bfc9  call    cs:__imp_CryptGenRandom
0x18011bfcf  test    eax, eax
0x18011bfd1  jnz     short loc_18011BFE8
0x18011bfd3  call    cs:__imp_GetLastError
0x18011bfd9  mov     ebx, eax
0x18011bfdb  test    eax, eax
0x18011bfdd  jle     short loc_18011BFE8
0x18011bfdf  movzx   ebx, ax
0x18011bfe2  or      ebx, 80070000h
0x18011bfe8  test    ebx, ebx
0x18011bfea  jns     loc_18011C07F
  ... truncated ...
```
