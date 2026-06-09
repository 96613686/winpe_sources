# CMF2DMediaBuffer::ContiguousCopyTo(uchar *,ulong)

- ea: `0x1800609e0`
- end: `0x180060f89`
- name: `?ContiguousCopyTo@CMF2DMediaBuffer@@UEAAJPEAEK@Z`
- size: `1449`
- prototype: `__int64 __fastcall(LONG *this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180022688`
- `0x18002312c`
- `0x180045060`
- `0x180056638`
- `0x1800609e0`
- `0x180061ab0`
- `0x180061e40`
- `0x18006538c`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060c99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060c99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060a90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060b85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060c50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060d3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060e75`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060a90`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060b85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060c50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060d3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180060e75`

## string_xrefs

- `0x180060a37`: `CMF2DMediaBuffer::ContiguousCopyTo`
- `0x180060aed`: `CMF2DMediaBuffer::ContiguousCopyTo`
- `0x180060be5`: `CMF2DMediaBuffer::ContiguousCopyTo`
- `0x180060cb0`: `CMF2DMediaBuffer::ContiguousCopyTo`
- `0x180060d9e`: `CMF2DMediaBuffer::ContiguousCopyTo`
- `0x180060ed5`: `CMF2DMediaBuffer::ContiguousCopyTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMF2DMediaBuffer::ContiguousCopyTo(LONG *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // rsi
  LONG *v6; // r15
  int v7; // ebx
  CallStackTracing *v8; // rdi
  CallStackContext *v9; // rsi
  DWORD v10; // r14d
  CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rdi
  CallStackContext *v16; // rsi
  DWORD v17; // r14d
  CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rdi
  CallStackContext *v22; // rsi
  DWORD v23; // r14d
  CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  int v27; // ecx
  CallStackTracing *v28; // rdi
  CallStackContext *v29; // rsi
  DWORD v30; // r14d
  CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  _DWORD *v34; // r15
  _DWORD *v35; // r12
  _DWORD *v36; // r13
  int v37; // ecx
  CallStackTracing *v38; // rdi
  CallStackContext *v39; // rsi
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  CallStackTracing *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  unsigned __int8 *v46; // [rsp+40h] [rbp-29h] BYREF
  CMF2DMediaBuffer *v47; // [rsp+48h] [rbp-21h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-19h]
  unsigned __int8 *v49[2]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v50[11]; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v51; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v52; // [rsp+D8h] [rbp+6Fh] BYREF
  char v53; // [rsp+E0h] [rbp+77h] BYREF
  int v54; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = a3;
  lpCriticalSection = (LPCRITICAL_SECTION)(this - 12);
  EnterCriticalSection((LPCRITICAL_SECTION)(this - 12));
  v51 = 0;
  v54 = 0;
  v46 = 0;
  v52 = 0;
  v50[0] = v3;
  v50[1] = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v53, "CMF2DMediaBuffer::ContiguousCopyTo", 719);
  v6 = this - 26;
  v47 = (CMF2DMediaBuffer *)(this - 26);
  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(LONG *, unsigned int *))(*(_QWORD *)this + 56LL))(this, &v51);
    if ( v7 >= 0 )
    {
      if ( v51 <= (unsigned int)v3 )
      {
        v7 = CMF2DMediaBuffer::DoLock2DSize(
               (CMF2DMediaBuffer *)(this - 26),
               MF2DBuffer_LockFlags_Read,
               v49,
               &v54,
               &v46,
               &v52);
        if ( v7 >= 0 )
        {
          v49[0] = (unsigned __int8 *)v52;
          v49[1] = v46;
          v34 = this + 20;
          v35 = this + 17;
          v36 = this + 16;
          if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
            McTemplateU0pddddd_EventWriteTransfer(
              v27,
              (unsigned int)Mem2DAlloc_Copy_Start,
              (_DWORD)a2,
              1,
              *v36,
              *v35,
              *v34,
              v3);
          v7 = CMF2DMediaBuffer::InternalCopyBuffer(
                 (CMF2DMediaBuffer *)(this - 26),
                 (struct MFBUFFER::CBuffer *)v50,
                 this[22],
                 (struct MFBUFFER::CBufferRO *)v49,
                 v54);
          if ( v7 >= 0 )
          {
            if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
              McTemplateU0pddddd_EventWriteTransfer(
                v37,
                (unsigned int)Mem2DAlloc_Copy_End,
                (_DWORD)a2,
                1,
                *v36,
                *v35,
                *v34,
                v3);
          }
          else
          {
            v38 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)&qword_18009CF60;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              v39 = (CallStackTracing *)((char *)v38 + 208);
              LastError = GetLastError();
              Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v38 + 3));
              if ( Value )
              {
                v39 = Value;
              }
              else if ( !GetLastError() )
              {
                v42 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)&qword_18009CF60;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
                }
                v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v42)(v42);
                if ( v43 )
                  v39 = (CallStackContext *)v43;
              }
              SetLastError(LastError);
              if ( *((_DWORD *)v39 + 499) != v7 )
                CallStackContext::TraceFailure(v39, "CMF2DMediaBuffer::ContiguousCopyTo", 734, v7);
            }
            if ( g_wppLevels )
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                59,
                &WPP_4914b0c617f436cdc4f55e71727dbf4b_Traceguids,
                v47,
                v7);
          }
          v44 = CMF2DMediaBuffer::DoUnlock2D(v47);
          if ( v7 >= 0 && v44 < 0 )
            v7 = v44;
        }
        else
        {
          v28 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v29 = (CallStackTracing *)((char *)v28 + 208);
            v30 = GetLastError();
            v31 = (CallStackContext *)TlsGetValue(*((_DWORD *)v28 + 3));
            if ( v31 )
            {
              v29 = v31;
            }
            else if ( !GetLastError() )
            {
              v32 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)&qword_18009CF60;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
              }
              v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
              if ( v33 )
                v29 = (CallStackContext *)v33;
            }
            SetLastError(v30);
            if ( *((_DWORD *)v29 + 499) != v7 )
              CallStackContext::TraceFailure(v29, "CMF2DMediaBuffer::ContiguousCopyTo", 727, v7);
          }
          if ( g_wppLevels )
          {
            v14 = 58;
            goto LABEL_16;
          }
        }
      }
      else
      {
        v7 = -2147024809;
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v22 = (CallStackTracing *)((char *)v21 + 208);
          v23 = GetLastError();
          v24 = (CallStackContext *)TlsGetValue(*((_DWORD *)v21 + 3));
          if ( v24 )
          {
            v22 = v24;
          }
          else if ( !GetLastError() )
          {
            v25 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)&qword_18009CF60;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
            }
            v26 = (**(__int64 (__fastcall ***)(CallStackTracing *))v25)(v25);
            if ( v26 )
              v22 = (CallStackContext *)v26;
          }
          SetLastError(v23);
          if ( *((_DWORD *)v22 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v22, "CMF2DMediaBuffer::ContiguousCopyTo", 724, -2147024809);
        }
        if ( g_wppLevels )
        {
          v14 = 57;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v16 = (CallStackTracing *)((char *)v15 + 208);
        v17 = GetLastError();
        v18 = (CallStackContext *)TlsGetValue(*((_DWORD *)v15 + 3));
        if ( v18 )
        {
          v16 = v18;
        }
        else if ( !GetLastError() )
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
          if ( v20 )
            v16 = (CallStackContext *)v20;
        }
        SetLastError(v17);
        if ( *((_DWORD *)v16 + 499) != v7 )
          CallStackContext::TraceFailure(v16, "CMF2DMediaBuffer::ContiguousCopyTo", 721, v7);
      }
      if ( g_wppLevels )
      {
        v14 = 56;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v7 = -2147467261;
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v9 = (CallStackTracing *)((char *)v8 + 208);
      v10 = GetLastError();
      v11 = (CallStackContext *)TlsGetValue(*((_DWORD *)v8 + 3));
      if ( v11 )
      {
        v9 = v11;
      }
      else if ( !GetLastError() )
      {
        v12 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v13 = (**(__int64 (__fastcall ***)(CallStackTracing *))v12)(v12);
        if ( v13 )
          v9 = (CallStackContext *)v13;
      }
      SetLastError(v10);
      if ( *((_DWORD *)v9 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v9, "CMF2DMediaBuffer::ContiguousCopyTo", 719, -2147467261);
    }
    if ( g_wppLevels )
    {
      v14 = 55;
LABEL_16:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_4914b0c617f436cdc4f55e71727dbf4b_Traceguids, v6, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v53);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800609e0  push    rbp
0x1800609e2  push    rbx
0x1800609e3  push    rsi
0x1800609e4  push    rdi
0x1800609e5  push    r12
0x1800609e7  push    r13
0x1800609e9  push    r14
0x1800609eb  push    r15
0x1800609ed  lea     rbp, [rsp-1Fh]
0x1800609f2  sub     rsp, 88h
0x1800609f9  mov     esi, r8d
0x1800609fc  mov     r14, rdx
0x1800609ff  mov     rdi, rcx
0x180060a02  lea     rax, [rcx-30h]
0x180060a06  mov     [rbp+57h+lpCriticalSection], rax
0x180060a0a  mov     rcx, rax; lpCriticalSection
0x180060a0d  call    cs:__imp_EnterCriticalSection
0x180060a13  xor     r12d, r12d
0x180060a16  mov     [rbp+57h+arg_0], r12d
0x180060a1a  mov     [rbp+57h+arg_18], r12d
0x180060a1e  mov     [rbp+57h+var_80], r12
0x180060a22  mov     [rbp+57h+arg_8], r12d
0x180060a26  mov     [rbp+57h+var_58], rsi
0x180060a2a  mov     [rbp+57h+var_50], r14
0x180060a2e  mov     r13d, 2CFh
0x180060a34  mov     r8d, r13d; int
0x180060a37  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060a3e  lea     rcx, [rbp+57h+arg_10]; this
0x180060a42  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180060a47  lea     r15, [rdi-68h]
0x180060a4b  mov     [rbp+57h+var_78], r15
0x180060a4f  test    r14, r14
0x180060a52  jnz     loc_180060B31
0x180060a58  mov     ebx, 80004003h
0x180060a5d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060a64  test    rdi, rdi
0x180060a67  jnz     short loc_180060A77
0x180060a69  lea     rdi, qword_18009CF60
0x180060a70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180060a77  cmp     [rdi+8], r12b
0x180060a7b  jz      short loc_180060AFC
0x180060a7d  lea     rsi, [rdi+0D0h]
0x180060a84  call    cs:__imp_GetLastError
0x180060a8a  mov     r14d, eax
0x180060a8d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180060a90  call    cs:__imp_TlsGetValue
0x180060a96  test    rax, rax
0x180060a99  jz      short loc_180060AA0
0x180060a9b  mov     rsi, rax
0x180060a9e  jmp     short loc_180060AD6
0x180060aa0  call    cs:__imp_GetLastError
0x180060aa6  test    eax, eax
0x180060aa8  jnz     short loc_180060AD6
0x180060aaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060ab1  test    rcx, rcx
0x180060ab4  jnz     short loc_180060AC4
0x180060ab6  lea     rcx, qword_18009CF60
0x180060abd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060ac4  mov     rax, [rcx]
0x180060ac7  mov     rax, [rax]
0x180060aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060acf  test    rax, rax
0x180060ad2  cmovnz  rsi, rax
0x180060ad6  mov     ecx, r14d; dwErrCode
0x180060ad9  call    cs:__imp_SetLastError
0x180060adf  cmp     [rsi+7CCh], ebx
0x180060ae5  jz      short loc_180060AFC
0x180060ae7  mov     r9d, ebx; int
0x180060aea  mov     r8d, r13d; int
0x180060aed  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060af4  mov     rcx, rsi; this
0x180060af7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060afc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060b03  jb      loc_180060F5E
0x180060b09  mov     edx, 37h ; '7'
0x180060b0e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180060b12  mov     r9, r15
0x180060b15  lea     r8, WPP_4914b0c617f436cdc4f55e71727dbf4b_Traceguids
0x180060b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060b23  mov     rcx, [rcx+10h]
0x180060b27  call    WPP_SF_qd
0x180060b2c  jmp     loc_180060F5E
0x180060b31  mov     rax, [rdi]
0x180060b34  lea     rdx, [rbp+57h+arg_0]
0x180060b38  mov     rcx, rdi
0x180060b3b  mov     rax, [rax+38h]
0x180060b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b44  mov     ebx, eax
0x180060b46  test    eax, eax
0x180060b48  jns     loc_180060C0B
0x180060b4e  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060b55  test    rdi, rdi
0x180060b58  jnz     short loc_180060B68
0x180060b5a  lea     rdi, qword_18009CF60
0x180060b61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180060b68  cmp     [rdi+8], r12b
0x180060b6c  jz      loc_180060BF4
0x180060b72  lea     rsi, [rdi+0D0h]
0x180060b79  call    cs:__imp_GetLastError
0x180060b7f  mov     r14d, eax
0x180060b82  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180060b85  call    cs:__imp_TlsGetValue
0x180060b8b  test    rax, rax
0x180060b8e  jz      short loc_180060B95
0x180060b90  mov     rsi, rax
0x180060b93  jmp     short loc_180060BCB
0x180060b95  call    cs:__imp_GetLastError
0x180060b9b  test    eax, eax
0x180060b9d  jnz     short loc_180060BCB
0x180060b9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060ba6  test    rcx, rcx
0x180060ba9  jnz     short loc_180060BB9
0x180060bab  lea     rcx, qword_18009CF60
0x180060bb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060bb9  mov     rax, [rcx]
0x180060bbc  mov     rax, [rax]
0x180060bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bc4  test    rax, rax
0x180060bc7  cmovnz  rsi, rax
0x180060bcb  mov     ecx, r14d; dwErrCode
0x180060bce  call    cs:__imp_SetLastError
0x180060bd4  cmp     [rsi+7CCh], ebx
0x180060bda  jz      short loc_180060BF4
0x180060bdc  mov     r9d, ebx; int
0x180060bdf  mov     r8d, 2D1h; int
0x180060be5  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060bec  mov     rcx, rsi; this
0x180060bef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060bf4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060bfb  jb      loc_180060F5E
0x180060c01  mov     edx, 38h ; '8'
0x180060c06  jmp     loc_180060B0E
0x180060c0b  cmp     [rbp+57h+arg_0], esi
0x180060c0e  jbe     loc_180060CD6
0x180060c14  mov     ebx, 80070057h
0x180060c19  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c20  test    rdi, rdi
0x180060c23  jnz     short loc_180060C33
0x180060c25  lea     rdi, qword_18009CF60
0x180060c2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c33  cmp     [rdi+8], r12b
0x180060c37  jz      loc_180060CBF
0x180060c3d  lea     rsi, [rdi+0D0h]
0x180060c44  call    cs:__imp_GetLastError
0x180060c4a  mov     r14d, eax
0x180060c4d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180060c50  call    cs:__imp_TlsGetValue
0x180060c56  test    rax, rax
0x180060c59  jz      short loc_180060C60
0x180060c5b  mov     rsi, rax
0x180060c5e  jmp     short loc_180060C96
0x180060c60  call    cs:__imp_GetLastError
0x180060c66  test    eax, eax
0x180060c68  jnz     short loc_180060C96
0x180060c6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c71  test    rcx, rcx
0x180060c74  jnz     short loc_180060C84
0x180060c76  lea     rcx, qword_18009CF60
0x180060c7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c84  mov     rax, [rcx]
0x180060c87  mov     rax, [rax]
0x180060c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c8f  test    rax, rax
0x180060c92  cmovnz  rsi, rax
0x180060c96  mov     ecx, r14d; dwErrCode
0x180060c99  call    cs:__imp_SetLastError
0x180060c9f  cmp     [rsi+7CCh], ebx
0x180060ca5  jz      short loc_180060CBF
0x180060ca7  mov     r9d, ebx; int
0x180060caa  mov     r8d, 2D4h; int
0x180060cb0  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060cb7  mov     rcx, rsi; this
0x180060cba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060cbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060cc6  jb      loc_180060F5E
0x180060ccc  mov     edx, 39h ; '9'
0x180060cd1  jmp     loc_180060B0E
0x180060cd6  lea     rax, [rbp+57h+arg_8]
0x180060cda  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x180060cdf  lea     rax, [rbp+57h+var_80]
0x180060ce3  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x180060ce8  lea     r9, [rbp+57h+arg_18]; int *
0x180060cec  lea     r8, [rbp+57h+var_68]; unsigned __int8 **
0x180060cf0  mov     edx, 1; enum _MF2DBuffer_LockFlags
0x180060cf5  mov     rcx, r15; this
0x180060cf8  call    ?DoLock2DSize@CMF2DMediaBuffer@@AEAAJW4_MF2DBuffer_LockFlags@@PEAPEAEPEAJ1PEAK@Z; CMF2DMediaBuffer::DoLock2DSize(_MF2DBuffer_LockFlags,uchar * *,long *,uchar * *,ulong *)
0x180060cfd  mov     ebx, eax
0x180060cff  test    eax, eax
0x180060d01  jns     loc_180060DC4
0x180060d07  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d0e  test    rdi, rdi
0x180060d11  jnz     short loc_180060D21
0x180060d13  lea     rdi, qword_18009CF60
0x180060d1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d21  cmp     [rdi+8], r12b
0x180060d25  jz      loc_180060DAD
0x180060d2b  lea     rsi, [rdi+0D0h]
0x180060d32  call    cs:__imp_GetLastError
0x180060d38  mov     r14d, eax
0x180060d3b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180060d3e  call    cs:__imp_TlsGetValue
0x180060d44  test    rax, rax
0x180060d47  jz      short loc_180060D4E
0x180060d49  mov     rsi, rax
0x180060d4c  jmp     short loc_180060D84
0x180060d4e  call    cs:__imp_GetLastError
0x180060d54  test    eax, eax
0x180060d56  jnz     short loc_180060D84
0x180060d58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d5f  test    rcx, rcx
0x180060d62  jnz     short loc_180060D72
0x180060d64  lea     rcx, qword_18009CF60
0x180060d6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d72  mov     rax, [rcx]
0x180060d75  mov     rax, [rax]
0x180060d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d7d  test    rax, rax
0x180060d80  cmovnz  rsi, rax
0x180060d84  mov     ecx, r14d; dwErrCode
0x180060d87  call    cs:__imp_SetLastError
0x180060d8d  cmp     [rsi+7CCh], ebx
0x180060d93  jz      short loc_180060DAD
0x180060d95  mov     r9d, ebx; int
0x180060d98  mov     r8d, 2D7h; int
0x180060d9e  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060da5  mov     rcx, rsi; this
0x180060da8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060dad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060db4  jb      loc_180060F5E
0x180060dba  mov     edx, 3Ah ; ':'
0x180060dbf  jmp     loc_180060B0E
0x180060dc4  mov     eax, [rbp+57h+arg_8]
0x180060dc7  mov     [rbp+57h+var_68], rax
0x180060dcb  mov     rax, [rbp+57h+var_80]
0x180060dcf  mov     [rbp+57h+var_60], rax
0x180060dd3  lea     r15, [rdi+50h]
0x180060dd7  lea     r12, [rdi+44h]
0x180060ddb  lea     r13, [rdi+40h]
0x180060ddf  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180060de6  jz      short loc_180060E18
0x180060de8  mov     [rsp+0C0h+var_88], esi
0x180060dec  mov     eax, [r15]
0x180060def  mov     [rsp+0C0h+var_90], eax
0x180060df3  mov     eax, [r12]
0x180060df7  mov     dword ptr [rsp+0C0h+var_98], eax
0x180060dfb  mov     eax, [r13+0]
0x180060dff  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180060e03  mov     r9d, 1
0x180060e09  mov     r8, r14
0x180060e0c  lea     rdx, Mem2DAlloc_Copy_Start
0x180060e13  call    McTemplateU0pddddd_EventWriteTransfer
0x180060e18  mov     eax, [rbp+57h+arg_18]
0x180060e1b  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180060e1f  lea     r9, [rbp+57h+var_68]; struct MFBUFFER::CBufferRO *
0x180060e23  mov     r8d, [rdi+58h]; int
0x180060e27  lea     rdx, [rbp+57h+var_58]; struct MFBUFFER::CBuffer *
0x180060e2b  lea     rcx, [rdi-68h]; this
0x180060e2f  call    ?InternalCopyBuffer@CMF2DMediaBuffer@@IEAAJPEAVCBuffer@MFBUFFER@@JPEAVCBufferRO@3@J@Z; CMF2DMediaBuffer::InternalCopyBuffer(MFBUFFER::CBuffer *,long,MFBUFFER::CBufferRO *,long)
0x180060e34  mov     ebx, eax
0x180060e36  test    eax, eax
0x180060e38  jns     loc_180060F13
0x180060e3e  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e45  test    rdi, rdi
0x180060e48  jnz     short loc_180060E58
0x180060e4a  lea     rdi, qword_18009CF60
0x180060e51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e58  cmp     byte ptr [rdi+8], 0
0x180060e5c  jz      loc_180060EE4
0x180060e62  lea     rsi, [rdi+0D0h]
0x180060e69  call    cs:__imp_GetLastError
0x180060e6f  mov     r14d, eax
0x180060e72  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180060e75  call    cs:__imp_TlsGetValue
0x180060e7b  test    rax, rax
0x180060e7e  jz      short loc_180060E85
0x180060e80  mov     rsi, rax
0x180060e83  jmp     short loc_180060EBB
0x180060e85  call    cs:__imp_GetLastError
0x180060e8b  test    eax, eax
0x180060e8d  jnz     short loc_180060EBB
0x180060e8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e96  test    rcx, rcx
0x180060e99  jnz     short loc_180060EA9
0x180060e9b  lea     rcx, qword_18009CF60
0x180060ea2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060ea9  mov     rax, [rcx]
0x180060eac  mov     rax, [rax]
0x180060eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eb4  test    rax, rax
0x180060eb7  cmovnz  rsi, rax
0x180060ebb  mov     ecx, r14d; dwErrCode
0x180060ebe  call    cs:__imp_SetLastError
0x180060ec4  cmp     [rsi+7CCh], ebx
0x180060eca  jz      short loc_180060EE4
0x180060ecc  mov     r9d, ebx; int
0x180060ecf  mov     r8d, 2DEh; int
0x180060ed5  lea     rdx, aCmf2dmediabuff_8; "CMF2DMediaBuffer::ContiguousCopyTo"
0x180060edc  mov     rcx, rsi; this
0x180060edf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060ee4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
