# CWAVEStreamSink::WAVEHeaderWrite(void)

- ea: `0x18011da38`
- end: `0x18011df3c`
- name: `?WAVEHeaderWrite@CWAVEStreamSink@@AEAAJXZ`
- size: `1284`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800435a0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x18011cfa8`
- `0x18011d99c`
- `0x18011da38`
- `0x18011e37c`
- `0x18012f8a4`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011daa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011db5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dc04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dcb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dd58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011de1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011daa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011db5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dc04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dcb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011dd58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011de1b`
- `MFPlat!MFCreateMemoryBuffer` at `0x18011db40`
- `MFPlat!MFCreateMemoryBuffer` at `0x18011db40`

## string_xrefs

- `0x18011da4f`: `CWAVEStreamSink::WAVEHeaderWrite`

## pseudocode

```c
__int64 __fastcall CWAVEStreamSink::WAVEHeaderWrite(CRIFFMetadata **this)
{
  __int64 v2; // rdx
  HRESULT Size; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CRIFFMetadata *v40; // rcx
  CRIFFMetadata *v41; // rcx
  DWORD cbMaxLength; // [rsp+60h] [rbp+30h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int8 *Destination; // [rsp+70h] [rbp+40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cbMaxLength, "CWAVEStreamSink::WAVEHeaderWrite", 187);
  Destination = 0;
  ppBuffer = 0;
  cbMaxLength = 0;
  Size = CWAVEStreamSink::WAVEHeaderGetSize((CWAVEStreamSink *)this, &cbMaxLength);
  if ( Size >= 0 )
  {
    Size = MFCreateMemoryBuffer(cbMaxLength, &ppBuffer);
    if ( Size >= 0 )
    {
      Size = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
               ppBuffer,
               cbMaxLength);
      if ( Size >= 0 )
      {
        Size = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                 ppBuffer,
                 &Destination,
                 0,
                 0);
        if ( Size >= 0 )
        {
          Size = CWAVEStreamSink::WAVEHeaderGetBytes((CWAVEStreamSink *)this, Destination, cbMaxLength);
          if ( Size >= 0 )
          {
            Size = (*(__int64 (__fastcall **)(CRIFFMetadata *, unsigned __int8 *, _QWORD, char *, IMFMediaBuffer *))(*(_QWORD *)this[48] + 104LL))(
                     this[48],
                     Destination,
                     cbMaxLength,
                     (char *)this + 360,
                     ppBuffer);
            if ( Size >= 0 )
            {
              this[56] = (CRIFFMetadata *)((char *)this[56] + cbMaxLength);
              Destination = 0;
            }
            else
            {
              v37 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
                CallStackTracing::s_wpInstance = v38;
                if ( v38
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                {
                  v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v37 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v37 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Size )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CWAVEStreamSink::WAVEHeaderWrite", 202, Size);
              }
              if ( g_wppLevels )
              {
                v9 = 36;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
              {
                v31 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v31 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
              if ( *((_DWORD *)v33 + 499) != Size )
                CallStackContext::TraceFailure(v33, "CWAVEStreamSink::WAVEHeaderWrite", 200, Size);
            }
            if ( g_wppLevels )
            {
              v9 = 35;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != Size )
              CallStackContext::TraceFailure(v27, "CWAVEStreamSink::WAVEHeaderWrite", 198, Size);
          }
          if ( g_wppLevels )
          {
            v9 = 34;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != Size )
            CallStackContext::TraceFailure(v21, "CWAVEStreamSink::WAVEHeaderWrite", 196, Size);
        }
        if ( g_wppLevels )
        {
          v9 = 33;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != Size )
          CallStackContext::TraceFailure(v15, "CWAVEStreamSink::WAVEHeaderWrite", 194, Size);
      }
      if ( g_wppLevels )
      {
        v9 = 32;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != Size )
        CallStackContext::TraceFailure(v8, "CWAVEStreamSink::WAVEHeaderWrite", 192, Size);
    }
    if ( g_wppLevels )
    {
      v9 = 31;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, this, Size);
    }
  }
  if ( Destination )
    Size = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  if ( (unsigned __int8)byte_1801B110A >= 8u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, &WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, cbMaxLength);
  v40 = this[49];
  if ( v40 )
  {
    if ( (unsigned int)CRIFFMetadata::IsCommitReady(v40) == 1 )
    {
      v41 = this[49];
      if ( v41 )
      {
        (*(void (__fastcall **)(CRIFFMetadata *))(*(_QWORD *)v41 + 16LL))(v41);
        this[49] = 0;
      }
    }
  }
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cbMaxLength);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18011da38  mov     [rsp-28h+arg_18], rbx
0x18011da3d  push    rbp
0x18011da3e  push    rdi
0x18011da3f  push    r12
0x18011da41  push    r13
0x18011da43  push    r14
0x18011da45  mov     rbp, rsp
0x18011da48  sub     rsp, 30h
0x18011da4c  mov     rdi, rcx
0x18011da4f  lea     r12, aCwavestreamsin_12; "CWAVEStreamSink::WAVEHeaderWrite"
0x18011da56  mov     rdx, r12; char *
0x18011da59  lea     rcx, [rbp+cbMaxLength]; this
0x18011da5d  mov     r8d, 0BBh; int
0x18011da63  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18011da68  xor     r14d, r14d
0x18011da6b  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x18011da6f  mov     rcx, rdi; this
0x18011da72  mov     [rbp+Destination], r14
0x18011da76  mov     [rbp+ppBuffer], r14
0x18011da7a  mov     [rbp+cbMaxLength], r14d
0x18011da7e  call    ?WAVEHeaderGetSize@CWAVEStreamSink@@AEAAJPEAK@Z; CWAVEStreamSink::WAVEHeaderGetSize(ulong *)
0x18011da83  lea     r13, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x18011da8a  mov     ebx, eax
0x18011da8c  test    eax, eax
0x18011da8e  jns     loc_18011DB39
0x18011da94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011da9b  test    rcx, rcx
0x18011da9e  jnz     short loc_18011DAE1
0x18011daa0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011daa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011daad  mov     rcx, rax
0x18011dab0  test    rax, rax
0x18011dab3  jz      short loc_18011DAD3
0x18011dab5  mov     rax, [rax]
0x18011dab8  mov     edx, 7F0h
0x18011dabd  mov     rax, [rax+8]
0x18011dac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dac6  test    eax, eax
0x18011dac8  jz      short loc_18011DAD3
0x18011daca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dad1  jmp     short loc_18011DAE1
0x18011dad3  lea     rcx, qword_1801B07E0; this
0x18011dada  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dae1  cmp     [rcx+8], r14b
0x18011dae5  jz      short loc_18011DB08
0x18011dae7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011daec  cmp     [rax+7CCh], ebx
0x18011daf2  jz      short loc_18011DB08
0x18011daf4  mov     r9d, ebx; int
0x18011daf7  mov     r8d, 0C0h; int
0x18011dafd  mov     rdx, r12; char *
0x18011db00  mov     rcx, rax; this
0x18011db03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011db08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011db0f  jb      loc_18011DEA4
0x18011db15  mov     edx, 1Fh
0x18011db1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18011db21  mov     r9, rdi
0x18011db24  mov     r8, r13
0x18011db27  mov     dword ptr [rsp+30h+var_10], ebx
0x18011db2b  mov     rcx, [rcx+10h]
0x18011db2f  call    WPP_SF_qD
0x18011db34  jmp     loc_18011DEA4
0x18011db39  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x18011db3c  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18011db40  call    cs:__imp_MFCreateMemoryBuffer
0x18011db46  mov     ebx, eax
0x18011db48  test    eax, eax
0x18011db4a  jns     loc_18011DBDB
0x18011db50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011db57  test    rcx, rcx
0x18011db5a  jnz     short loc_18011DB9D
0x18011db5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011db62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011db69  mov     rcx, rax
0x18011db6c  test    rax, rax
0x18011db6f  jz      short loc_18011DB8F
0x18011db71  mov     rax, [rax]
0x18011db74  mov     edx, 7F0h
0x18011db79  mov     rax, [rax+8]
0x18011db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011db82  test    eax, eax
0x18011db84  jz      short loc_18011DB8F
0x18011db86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011db8d  jmp     short loc_18011DB9D
0x18011db8f  lea     rcx, qword_1801B07E0; this
0x18011db96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011db9d  cmp     [rcx+8], r14b
0x18011dba1  jz      short loc_18011DBC4
0x18011dba3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011dba8  cmp     [rax+7CCh], ebx
0x18011dbae  jz      short loc_18011DBC4
0x18011dbb0  mov     r9d, ebx; int
0x18011dbb3  mov     r8d, 0C2h; int
0x18011dbb9  mov     rdx, r12; char *
0x18011dbbc  mov     rcx, rax; this
0x18011dbbf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011dbc4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011dbcb  jb      loc_18011DEA4
0x18011dbd1  mov     edx, 20h ; ' '
0x18011dbd6  jmp     loc_18011DB1A
0x18011dbdb  mov     rcx, [rbp+ppBuffer]
0x18011dbdf  mov     edx, [rbp+cbMaxLength]
0x18011dbe2  mov     rax, [rcx]
0x18011dbe5  mov     rax, [rax+30h]
0x18011dbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dbee  mov     ebx, eax
0x18011dbf0  test    eax, eax
0x18011dbf2  jns     loc_18011DC83
0x18011dbf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dbff  test    rcx, rcx
0x18011dc02  jnz     short loc_18011DC45
0x18011dc04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011dc0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dc11  mov     rcx, rax
0x18011dc14  test    rax, rax
0x18011dc17  jz      short loc_18011DC37
0x18011dc19  mov     rax, [rax]
0x18011dc1c  mov     edx, 7F0h
0x18011dc21  mov     rax, [rax+8]
0x18011dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dc2a  test    eax, eax
0x18011dc2c  jz      short loc_18011DC37
0x18011dc2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dc35  jmp     short loc_18011DC45
0x18011dc37  lea     rcx, qword_1801B07E0; this
0x18011dc3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dc45  cmp     [rcx+8], r14b
0x18011dc49  jz      short loc_18011DC6C
0x18011dc4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011dc50  cmp     [rax+7CCh], ebx
0x18011dc56  jz      short loc_18011DC6C
0x18011dc58  mov     r9d, ebx; int
0x18011dc5b  mov     r8d, 0C4h; int
0x18011dc61  mov     rdx, r12; char *
0x18011dc64  mov     rcx, rax; this
0x18011dc67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011dc6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011dc73  jb      loc_18011DEA4
0x18011dc79  mov     edx, 21h ; '!'
0x18011dc7e  jmp     loc_18011DB1A
0x18011dc83  mov     rcx, [rbp+ppBuffer]
0x18011dc87  lea     rdx, [rbp+Destination]
0x18011dc8b  xor     r9d, r9d
0x18011dc8e  xor     r8d, r8d
0x18011dc91  mov     rax, [rcx]
0x18011dc94  mov     rax, [rax+18h]
0x18011dc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dc9d  mov     ebx, eax
0x18011dc9f  test    eax, eax
0x18011dca1  jns     loc_18011DD32
0x18011dca7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dcae  test    rcx, rcx
0x18011dcb1  jnz     short loc_18011DCF4
0x18011dcb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011dcb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dcc0  mov     rcx, rax
0x18011dcc3  test    rax, rax
0x18011dcc6  jz      short loc_18011DCE6
0x18011dcc8  mov     rax, [rax]
0x18011dccb  mov     edx, 7F0h
0x18011dcd0  mov     rax, [rax+8]
0x18011dcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dcd9  test    eax, eax
0x18011dcdb  jz      short loc_18011DCE6
0x18011dcdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dce4  jmp     short loc_18011DCF4
0x18011dce6  lea     rcx, qword_1801B07E0; this
0x18011dced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dcf4  cmp     [rcx+8], r14b
0x18011dcf8  jz      short loc_18011DD1B
0x18011dcfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011dcff  cmp     [rax+7CCh], ebx
0x18011dd05  jz      short loc_18011DD1B
0x18011dd07  mov     r9d, ebx; int
0x18011dd0a  mov     r8d, 0C6h; int
0x18011dd10  mov     rdx, r12; char *
0x18011dd13  mov     rcx, rax; this
0x18011dd16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011dd1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011dd22  jb      loc_18011DEA4
0x18011dd28  mov     edx, 22h ; '"'
0x18011dd2d  jmp     loc_18011DB1A
0x18011dd32  mov     r8d, [rbp+cbMaxLength]; int
0x18011dd36  mov     rcx, rdi; this
0x18011dd39  mov     rdx, [rbp+Destination]; Destination
0x18011dd3d  call    ?WAVEHeaderGetBytes@CWAVEStreamSink@@AEAAJPEAEH@Z; CWAVEStreamSink::WAVEHeaderGetBytes(uchar *,int)
0x18011dd42  mov     ebx, eax
0x18011dd44  test    eax, eax
0x18011dd46  jns     loc_18011DDD7
0x18011dd4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dd53  test    rcx, rcx
0x18011dd56  jnz     short loc_18011DD99
0x18011dd58  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011dd5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dd65  mov     rcx, rax
0x18011dd68  test    rax, rax
0x18011dd6b  jz      short loc_18011DD8B
0x18011dd6d  mov     rax, [rax]
0x18011dd70  mov     edx, 7F0h
0x18011dd75  mov     rax, [rax+8]
0x18011dd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011dd7e  test    eax, eax
0x18011dd80  jz      short loc_18011DD8B
0x18011dd82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dd89  jmp     short loc_18011DD99
0x18011dd8b  lea     rcx, qword_1801B07E0; this
0x18011dd92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011dd99  cmp     [rcx+8], r14b
0x18011dd9d  jz      short loc_18011DDC0
0x18011dd9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011dda4  cmp     [rax+7CCh], ebx
0x18011ddaa  jz      short loc_18011DDC0
0x18011ddac  mov     r9d, ebx; int
0x18011ddaf  mov     r8d, 0C8h; int
0x18011ddb5  mov     rdx, r12; char *
0x18011ddb8  mov     rcx, rax; this
0x18011ddbb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011ddc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011ddc7  jb      loc_18011DEA4
0x18011ddcd  mov     edx, 23h ; '#'
0x18011ddd2  jmp     loc_18011DB1A
0x18011ddd7  mov     rcx, [rdi+180h]
0x18011ddde  lea     r9, [rdi+168h]
0x18011dde5  mov     r8d, [rbp+cbMaxLength]
0x18011dde9  mov     rdx, [rbp+Destination]
0x18011dded  mov     rax, [rcx]
0x18011ddf0  mov     r10, [rax+68h]
0x18011ddf4  mov     rax, [rbp+ppBuffer]
0x18011ddf8  mov     [rsp+30h+var_10], rax
0x18011ddfd  mov     rax, r10
0x18011de00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011de05  mov     ebx, eax
0x18011de07  test    eax, eax
0x18011de09  jns     loc_18011DE96
0x18011de0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011de16  test    rcx, rcx
0x18011de19  jnz     short loc_18011DE5C
0x18011de1b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011de21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011de28  mov     rcx, rax
0x18011de2b  test    rax, rax
0x18011de2e  jz      short loc_18011DE4E
0x18011de30  mov     rax, [rax]
0x18011de33  mov     edx, 7F0h
0x18011de38  mov     rax, [rax+8]
0x18011de3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011de41  test    eax, eax
0x18011de43  jz      short loc_18011DE4E
0x18011de45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011de4c  jmp     short loc_18011DE5C
0x18011de4e  lea     rcx, qword_1801B07E0; this
0x18011de55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011de5c  cmp     [rcx+8], r14b
0x18011de60  jz      short loc_18011DE83
0x18011de62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011de67  cmp     [rax+7CCh], ebx
0x18011de6d  jz      short loc_18011DE83
0x18011de6f  mov     r9d, ebx; int
0x18011de72  mov     r8d, 0CAh; int
0x18011de78  mov     rdx, r12; char *
0x18011de7b  mov     rcx, rax; this
0x18011de7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011de83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011de8a  jb      short loc_18011DEA4
0x18011de8c  mov     edx, 24h ; '$'
0x18011de91  jmp     loc_18011DB1A
0x18011de96  mov     eax, [rbp+cbMaxLength]
0x18011de99  add     [rdi+1C0h], rax
0x18011dea0  mov     [rbp+Destination], r14
0x18011dea4  cmp     [rbp+Destination], r14
0x18011dea8  jz      short loc_18011DEBC
0x18011deaa  mov     rcx, [rbp+ppBuffer]
0x18011deae  mov     rax, [rcx]
0x18011deb1  mov     rax, [rax+20h]
0x18011deb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011deba  mov     ebx, eax
0x18011debc  cmp     cs:byte_1801B110A, 8
0x18011dec3  jb      short loc_18011DEE1
0x18011dec5  mov     rcx, cs:WPP_GLOBAL_Control
0x18011decc  mov     edx, 25h ; '%'
0x18011ded1  mov     r9d, [rbp+cbMaxLength]
0x18011ded5  mov     r8, r13
0x18011ded8  mov     rcx, [rcx+60h]
0x18011dedc  call    WPP_SF_d
0x18011dee1  mov     rcx, [rdi+188h]; this
0x18011dee8  test    rcx, rcx
0x18011deeb  jz      short loc_18011DF16
0x18011deed  call    ?IsCommitReady@CRIFFMetadata@@QEAAHXZ; CRIFFMetadata::IsCommitReady(void)
0x18011def2  cmp     eax, 1
0x18011def5  jnz     short loc_18011DF16
0x18011def7  mov     rcx, [rdi+188h]
0x18011defe  test    rcx, rcx
0x18011df01  jz      short loc_18011DF16
0x18011df03  mov     rax, [rcx]
0x18011df06  mov     rax, [rax+10h]
0x18011df0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011df0f  mov     [rdi+188h], r14
0x18011df16  lea     rcx, [rbp+ppBuffer]; void *
0x18011df1a  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
  ... truncated ...
```
