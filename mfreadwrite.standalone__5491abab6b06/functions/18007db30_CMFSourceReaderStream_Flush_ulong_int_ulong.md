# CMFSourceReaderStream::Flush(ulong,int,ulong)

- ea: `0x18007db30`
- end: `0x18007e0d9`
- name: `?Flush@CMFSourceReaderStream@@UEAAJKHK@Z`
- size: `1449`
- prototype: `__int64 __fastcall(CMFSourceReaderStream *__hidden this, unsigned int, int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006bd4`
- `0x180010ae0`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x18007db30`
- `0x1800a2814`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dbc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dbc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007db95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007de5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007df86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e050`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007db95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007de5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007df86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007e050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ddf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007de08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ddf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007de08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007df37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e001`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007db80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007ddfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007df2c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007dff6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007db80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007ddfd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007df2c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007dff6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007dd11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007de1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007debf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007df4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e017`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007dd11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007de1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007debf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007df4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e017`
- `MFPlat!MFPutWorkItem` at `0x18007dc1a`
- `MFPlat!MFPutWorkItem` at `0x18007dc1a`

## string_xrefs

- `0x18007db60`: `CMFSourceReaderStream::Flush`
- `0x18007dba1`: `CMFSourceReaderStream::Flush`
- `0x18007de74`: `CMFSourceReaderStream::Flush`
- `0x18007df9c`: `CMFSourceReaderStream::Flush`
- `0x18007e066`: `CMFSourceReaderStream::Flush`

## pseudocode

```c
__int64 __fastcall CMFSourceReaderStream::Flush(CMFSourceReaderStream *this, int a2, int a3, DWORD a4)
{
  CallStackTracing *v4; // rdi
  char *v9; // rbx
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  HRESULT v17; // edi
  __int64 *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rbp
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  CallStackTracing *v25; // rbp
  CallStackTracing *v26; // rax
  CallStackTracing *v27; // rcx
  __int64 v28; // rax
  CallStackContext *v29; // r15
  DWORD v30; // r12d
  CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  CallStackTracing *v34; // r14
  CallStackTracing *v35; // rax
  __int64 v36; // rax
  CallStackTracing *v37; // rbp
  CallStackTracing *v38; // rax
  CallStackContext *v39; // r15
  DWORD v40; // r12d
  CallStackContext *v41; // rax
  __int64 v42; // rdx
  CallStackTracing *v43; // rcx
  CallStackTracing *v44; // rax
  __int64 v45; // rax
  CallStackContext *v46; // r15
  DWORD v47; // r12d
  CallStackContext *v48; // rax
  __int64 v49; // rdx
  CallStackTracing *v50; // rcx
  CallStackTracing *v51; // rax
  __int64 v52; // rax
  char v53; // [rsp+90h] [rbp+8h] BYREF

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v9 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v27 = CallStackTracing::s_wpInstance;
      }
      v28 = (**(__int64 (__fastcall ***)(CallStackTracing *))v27)(v27);
      if ( v28 )
        v9 = (char *)v28;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CMFSourceReaderStream::Flush";
      *(_DWORD *)&v9[8 * v13 + 8] = 5771;
    }
    ++*((_DWORD *)v9 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 23) )
  {
    v21 = CallStackTracing::s_wpInstance;
    v17 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v21 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v29 = (CallStackTracing *)((char *)v21 + 208);
      v30 = GetLastError();
      v31 = (CallStackContext *)TlsGetValue(*((_DWORD *)v21 + 3));
      if ( v31 )
      {
        v29 = v31;
      }
      else if ( !GetLastError() )
      {
        v34 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v33, v32);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v34)(v34);
        if ( v36 )
          v29 = (CallStackContext *)v36;
      }
      SetLastError(v30);
      if ( *((_DWORD *)v29 + 499) != -1072873851 )
        CallStackContext::TraceFailure(v29, "CMFSourceReaderStream::Flush", 5779, -1072873851);
    }
    if ( !g_wppLevels )
      goto LABEL_18;
    v22 = 549;
LABEL_39:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids, this, v17);
    goto LABEL_18;
  }
  v14 = 0;
  if ( (unsigned __int8)byte_18010CAF1 >= 8u )
    WPP_SF_qDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      550,
      &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
      this,
      **((_DWORD **)this + 202),
      a2,
      a3);
  *((_DWORD *)this + 419) = a2;
  while ( *((_DWORD *)this + 532) )
  {
    v19 = (__int64 *)*((_QWORD *)this + 264);
    if ( v19 )
    {
      v20 = v19[1];
      v14 = *v19;
      *((_QWORD *)this + 264) = v20;
      if ( v20 )
        *(_QWORD *)(v20 + 16) = 0;
      else
        *((_QWORD *)this + 265) = 0;
      v19[1] = *((_QWORD *)this + 211);
      *((_QWORD *)this + 211) = v19;
      --*((_DWORD *)this + 532);
    }
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
  }
  if ( !a3 )
  {
    v17 = CMFSourceReaderStream::InternalFlush(this);
    if ( v17 >= 0 )
      goto LABEL_18;
    v25 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v46 = (CallStackTracing *)((char *)v25 + 208);
      v47 = GetLastError();
      v48 = (CallStackContext *)TlsGetValue(*((_DWORD *)v25 + 3));
      if ( v48 )
      {
        v46 = v48;
      }
      else if ( !GetLastError() )
      {
        v50 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v52 = (**(__int64 (__fastcall ***)(CallStackTracing *))v50)(v50);
        if ( v52 )
          v46 = (CallStackContext *)v52;
      }
      SetLastError(v47);
      if ( *((_DWORD *)v46 + 499) != v17 )
        CallStackContext::TraceFailure(v46, "CMFSourceReaderStream::Flush", 5819, v17);
    }
    if ( !g_wppLevels )
      goto LABEL_18;
    v22 = 552;
    goto LABEL_39;
  }
  if ( a4 == -1 )
    a4 = *((_DWORD *)this + 416);
  v17 = MFPutWorkItem(a4, (IMFAsyncCallback *)this + 3, 0);
  if ( v17 < 0 )
  {
    v37 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = (CallStackTracing *)((char *)v37 + 208);
      v40 = GetLastError();
      v41 = (CallStackContext *)TlsGetValue(*((_DWORD *)v37 + 3));
      if ( v41 )
      {
        v39 = v41;
      }
      else if ( !GetLastError() )
      {
        v43 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v45 = (**(__int64 (__fastcall ***)(CallStackTracing *))v43)(v43);
        if ( v45 )
          v39 = (CallStackContext *)v45;
      }
      SetLastError(v40);
      if ( *((_DWORD *)v39 + 499) != v17 )
        CallStackContext::TraceFailure(v39, "CMFSourceReaderStream::Flush", 5811, v17);
    }
    if ( g_wppLevels )
    {
      v22 = 551;
      goto LABEL_39;
    }
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v53);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18007db30  push    rbx
0x18007db32  push    rbp
0x18007db33  push    rsi
0x18007db34  push    rdi
0x18007db35  push    r12
0x18007db37  push    r13
0x18007db39  push    r14
0x18007db3b  push    r15
0x18007db3d  sub     rsp, 48h
0x18007db41  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007db48  xor     r13d, r13d
0x18007db4b  mov     ebp, r9d
0x18007db4e  mov     r12d, r8d
0x18007db51  mov     r15d, edx
0x18007db54  mov     rsi, rcx
0x18007db57  test    rdi, rdi
0x18007db5a  jz      loc_18007DD89
0x18007db60  lea     rcx, aCmfsourcereade_14; "CMFSourceReaderStream::Flush"
0x18007db67  cmp     [rdi+8], r13b
0x18007db6b  jz      short loc_18007DBC5
0x18007db6d  lea     rbx, [rdi+0D0h]
0x18007db74  call    cs:__imp_GetLastError
0x18007db7a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18007db7d  mov     r14d, eax
0x18007db80  call    cs:__imp_TlsGetValue
0x18007db86  test    rax, rax
0x18007db89  jz      loc_18007DD9A
0x18007db8f  mov     rbx, rax
0x18007db92  mov     ecx, r14d; dwErrCode
0x18007db95  call    cs:__imp_SetLastError
0x18007db9b  mov     eax, [rbx+7C4h]
0x18007dba1  lea     rcx, aCmfsourcereade_14; "CMFSourceReaderStream::Flush"
0x18007dba8  cmp     eax, [rbx+7C8h]
0x18007dbae  jnb     short loc_18007DBBF
0x18007dbb0  add     rax, rax
0x18007dbb3  mov     [rbx+rax*8], rcx
0x18007dbb7  mov     dword ptr [rbx+rax*8+8], 168Bh
0x18007dbbf  inc     dword ptr [rbx+7C4h]
0x18007dbc5  lea     rcx, [rsi+30h]; lpCriticalSection
0x18007dbc9  call    cs:__imp_EnterCriticalSection
0x18007dbcf  cmp     [rsi+5Ch], r13d
0x18007dbd3  jnz     loc_18007DCB9
0x18007dbd9  cmp     cs:byte_18010CAF1, 8
0x18007dbe0  mov     rdi, r13
0x18007dbe3  jnb     loc_18007E09E
0x18007dbe9  mov     [rsi+68Ch], r15d
0x18007dbf0  or      r14d, 0FFFFFFFFh
0x18007dbf4  cmp     [rsi+850h], r13d
0x18007dbfb  jnz     short loc_18007DC54
0x18007dbfd  test    r12d, r12d
0x18007dc00  jz      loc_18007DCEC
0x18007dc06  cmp     ebp, r14d
0x18007dc09  jnz     short loc_18007DC11
0x18007dc0b  mov     ebp, [rsi+680h]
0x18007dc11  lea     rdx, [rsi+18h]; pCallback
0x18007dc15  xor     r8d, r8d; pState
0x18007dc18  mov     ecx, ebp; dwQueue
0x18007dc1a  call    cs:__imp_MFPutWorkItem
0x18007dc20  mov     edi, eax
0x18007dc22  test    eax, eax
0x18007dc24  js      loc_18007DEAC
0x18007dc2a  lea     rcx, [rsi+30h]; lpCriticalSection
0x18007dc2e  call    cs:__imp_LeaveCriticalSection
0x18007dc34  lea     rcx, [rsp+88h+arg_0]; this
0x18007dc3c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007dc41  mov     eax, edi
0x18007dc43  add     rsp, 48h
0x18007dc47  pop     r15
0x18007dc49  pop     r14
0x18007dc4b  pop     r13
0x18007dc4d  pop     r12
0x18007dc4f  pop     rdi
0x18007dc50  pop     rsi
0x18007dc51  pop     rbp
0x18007dc52  pop     rbx
0x18007dc53  retn
0x18007dc54  mov     rcx, [rsi+840h]
0x18007dc5b  test    rcx, rcx
0x18007dc5e  jz      short loc_18007DC93
0x18007dc60  mov     rax, [rcx+8]
0x18007dc64  mov     rdi, [rcx]
0x18007dc67  mov     [rsi+840h], rax
0x18007dc6e  test    rax, rax
0x18007dc71  jnz     short loc_18007DCB3
0x18007dc73  mov     [rsi+848h], r13
0x18007dc7a  mov     rax, [rsi+698h]
0x18007dc81  mov     [rcx+8], rax
0x18007dc85  mov     [rsi+698h], rcx
0x18007dc8c  add     [rsi+850h], r14d
0x18007dc93  test    rdi, rdi
0x18007dc96  jz      loc_18007DBF4
0x18007dc9c  mov     rax, [rdi]
0x18007dc9f  mov     rcx, rdi
0x18007dca2  mov     rax, [rax+10h]
0x18007dca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcab  mov     rdi, r13
0x18007dcae  jmp     loc_18007DBF4
0x18007dcb3  mov     [rax+10h], r13
0x18007dcb7  jmp     short loc_18007DC7A
0x18007dcb9  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dcc0  mov     edi, 0C00D3E85h
0x18007dcc5  test    rbp, rbp
0x18007dcc8  jz      loc_18007DDCB
0x18007dcce  cmp     [rbp+8], r13b
0x18007dcd2  jnz     loc_18007DDEA
0x18007dcd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007dcdf  jb      loc_18007DC2A
0x18007dce5  mov     edx, 225h
0x18007dcea  jmp     short loc_18007DD66
0x18007dcec  mov     rcx, rsi; this
0x18007dcef  call    ?InternalFlush@CMFSourceReaderStream@@AEAAJXZ; CMFSourceReaderStream::InternalFlush(void)
0x18007dcf4  mov     edi, eax
0x18007dcf6  test    eax, eax
0x18007dcf8  jns     loc_18007DC2A
0x18007dcfe  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dd05  lea     r14, qword_18010C230
0x18007dd0c  test    rbp, rbp
0x18007dd0f  jnz     short loc_18007DD4A
0x18007dd11  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007dd17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dd1e  mov     rcx, rax
0x18007dd21  test    rax, rax
0x18007dd24  jz      loc_18007DFD4
0x18007dd2a  mov     rax, [rax]
0x18007dd2d  mov     edx, 7F0h
0x18007dd32  mov     rax, [rax+8]
0x18007dd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd3b  test    eax, eax
0x18007dd3d  jz      loc_18007DFD4
0x18007dd43  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dd4a  cmp     [rbp+8], r13b
0x18007dd4e  jnz     loc_18007DFE3
0x18007dd54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007dd5b  jb      loc_18007DC2A
0x18007dd61  mov     edx, 228h
0x18007dd66  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dd6d  lea     r8, WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids
0x18007dd74  mov     r9, rsi
0x18007dd77  mov     [rsp+88h+var_68], edi
0x18007dd7b  mov     rcx, [rcx+10h]
0x18007dd7f  call    WPP_SF_qD
0x18007dd84  jmp     loc_18007DC2A
0x18007dd89  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007dd8e  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dd95  jmp     loc_18007DB60
0x18007dd9a  call    cs:__imp_GetLastError
0x18007dda0  test    eax, eax
0x18007dda2  jnz     loc_18007DB92
0x18007dda8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ddaf  test    rcx, rcx
0x18007ddb2  jz      short loc_18007DDDC
0x18007ddb4  mov     rax, [rcx]
0x18007ddb7  mov     rax, [rax]
0x18007ddba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddbf  test    rax, rax
0x18007ddc2  cmovnz  rbx, rax
0x18007ddc6  jmp     loc_18007DB92
0x18007ddcb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007ddd0  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ddd7  jmp     loc_18007DCCE
0x18007dddc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007dde1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dde8  jmp     short loc_18007DDB4
0x18007ddea  lea     r15, [rbp+0D0h]
0x18007ddf1  call    cs:__imp_GetLastError
0x18007ddf7  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x18007ddfa  mov     r12d, eax
0x18007ddfd  call    cs:__imp_TlsGetValue
0x18007de03  test    rax, rax
0x18007de06  jnz     short loc_18007DE58
0x18007de08  call    cs:__imp_GetLastError
0x18007de0e  test    eax, eax
0x18007de10  jnz     short loc_18007DE5B
0x18007de12  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007de19  test    r14, r14
0x18007de1c  jnz     short loc_18007DE41
0x18007de1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007de24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007de2b  mov     rcx, rax
0x18007de2e  test    rax, rax
0x18007de31  jnz     short loc_18007DE8E
0x18007de33  lea     r14, qword_18010C230
0x18007de3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18007de41  mov     rax, [r14]
0x18007de44  mov     rcx, r14
0x18007de47  mov     rax, [rax]
0x18007de4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de4f  test    rax, rax
0x18007de52  cmovnz  r15, rax
0x18007de56  jmp     short loc_18007DE5B
0x18007de58  mov     r15, rax
0x18007de5b  mov     ecx, r12d; dwErrCode
0x18007de5e  call    cs:__imp_SetLastError
0x18007de64  cmp     [r15+7CCh], edi
0x18007de6b  jz      loc_18007DCD8
0x18007de71  mov     r9d, edi; int
0x18007de74  lea     rdx, aCmfsourcereade_14; "CMFSourceReaderStream::Flush"
0x18007de7b  mov     r8d, 1693h; int
0x18007de81  mov     rcx, r15; this
0x18007de84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007de89  jmp     loc_18007DCD8
0x18007de8e  mov     rax, [rax]
0x18007de91  mov     edx, 7F0h
0x18007de96  mov     rax, [rax+8]
0x18007de9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007de9f  test    eax, eax
0x18007dea1  jz      short loc_18007DE33
0x18007dea3  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007deaa  jmp     short loc_18007DE41
0x18007deac  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007deb3  lea     r14, qword_18010C230
0x18007deba  test    rbp, rbp
0x18007debd  jnz     short loc_18007DEF0
0x18007debf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007dec5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007decc  mov     rcx, rax
0x18007decf  test    rax, rax
0x18007ded2  jz      short loc_18007DF0D
0x18007ded4  mov     rax, [rax]
0x18007ded7  mov     edx, 7F0h
0x18007dedc  mov     rax, [rax+8]
0x18007dee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dee5  test    eax, eax
0x18007dee7  jz      short loc_18007DF0D
0x18007dee9  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007def0  cmp     [rbp+8], r13b
0x18007def4  jnz     short loc_18007DF19
0x18007def6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007defd  jb      loc_18007DC2A
0x18007df03  mov     edx, 227h
0x18007df08  jmp     loc_18007DD66
0x18007df0d  mov     rbp, r14
0x18007df10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18007df17  jmp     short loc_18007DEF0
0x18007df19  lea     r15, [rbp+0D0h]
0x18007df20  call    cs:__imp_GetLastError
0x18007df26  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x18007df29  mov     r12d, eax
0x18007df2c  call    cs:__imp_TlsGetValue
0x18007df32  test    rax, rax
0x18007df35  jnz     short loc_18007DF80
0x18007df37  call    cs:__imp_GetLastError
0x18007df3d  test    eax, eax
0x18007df3f  jnz     short loc_18007DF83
0x18007df41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007df48  test    rcx, rcx
0x18007df4b  jnz     short loc_18007DF6C
0x18007df4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007df53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007df5a  mov     rcx, rax
0x18007df5d  test    rax, rax
0x18007df60  jnz     short loc_18007DFB6
0x18007df62  mov     rcx, r14
0x18007df65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007df6c  mov     rax, [rcx]
0x18007df6f  mov     rax, [rax]
0x18007df72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df77  test    rax, rax
0x18007df7a  cmovnz  r15, rax
0x18007df7e  jmp     short loc_18007DF83
0x18007df80  mov     r15, rax
0x18007df83  mov     ecx, r12d; dwErrCode
0x18007df86  call    cs:__imp_SetLastError
0x18007df8c  cmp     [r15+7CCh], edi
0x18007df93  jz      loc_18007DEF6
0x18007df99  mov     r9d, edi; int
0x18007df9c  lea     rdx, aCmfsourcereade_14; "CMFSourceReaderStream::Flush"
0x18007dfa3  mov     r8d, 16B3h; int
0x18007dfa9  mov     rcx, r15; this
0x18007dfac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007dfb1  jmp     loc_18007DEF6
0x18007dfb6  mov     rax, [rax]
0x18007dfb9  mov     edx, 7F0h
0x18007dfbe  mov     rax, [rax+8]
0x18007dfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dfc7  test    eax, eax
0x18007dfc9  jz      short loc_18007DF62
0x18007dfcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dfd2  jmp     short loc_18007DF6C
0x18007dfd4  mov     rbp, r14
0x18007dfd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18007dfde  jmp     loc_18007DD4A
0x18007dfe3  lea     r15, [rbp+0D0h]
0x18007dfea  call    cs:__imp_GetLastError
0x18007dff0  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x18007dff3  mov     r12d, eax
0x18007dff6  call    cs:__imp_TlsGetValue
0x18007dffc  test    rax, rax
0x18007dfff  jnz     short loc_18007E04A
0x18007e001  call    cs:__imp_GetLastError
0x18007e007  test    eax, eax
0x18007e009  jnz     short loc_18007E04D
0x18007e00b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e012  test    rcx, rcx
0x18007e015  jnz     short loc_18007E036
0x18007e017  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e01d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e024  mov     rcx, rax
0x18007e027  test    rax, rax
0x18007e02a  jnz     short loc_18007E080
  ... truncated ...
```
