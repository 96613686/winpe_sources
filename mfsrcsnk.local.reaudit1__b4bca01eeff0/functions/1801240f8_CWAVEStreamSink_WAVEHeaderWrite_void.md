# CWAVEStreamSink::WAVEHeaderWrite(void)

- ea: `0x1801240f8`
- end: `0x180124627`
- name: `?WAVEHeaderWrite@CWAVEStreamSink@@AEAAJXZ`
- size: `1327`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180046ae0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180123620`
- `0x18012405c`
- `0x1801240f8`
- `0x180124a8c`
- `0x180136dd4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124160`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801242d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012438b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801244ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124160`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801242d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012438b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180124436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801244ff`
- `MFPlat!MFCreateMemoryBuffer` at `0x180124206`
- `MFPlat!MFCreateMemoryBuffer` at `0x180124206`

## string_xrefs

- `0x18012410f`: `CWAVEStreamSink::WAVEHeaderWrite`

## pseudocode

```c
__int64 __fastcall CWAVEStreamSink::WAVEHeaderWrite(CRIFFMetadata **this)
{
  __int64 v2; // rdx
  HRESULT Size; // ebx
  wchar_t *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CRIFFMetadata *v28; // rcx
  CRIFFMetadata *v29; // rcx
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
              v25 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
                CallStackTracing::s_wpInstance = v26;
                if ( v26
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
                {
                  v25 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v25 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v25 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Size )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CWAVEStreamSink::WAVEHeaderWrite", 202, Size);
              }
              if ( g_wppLevels )
              {
                v7 = 36;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v21 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
              {
                v21 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v21 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
              if ( *((_DWORD *)v23 + 499) != Size )
                CallStackContext::TraceFailure(v23, "CWAVEStreamSink::WAVEHeaderWrite", 200, Size);
            }
            if ( g_wppLevels )
            {
              v7 = 35;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v19 + 499) != Size )
              CallStackContext::TraceFailure(v19, "CWAVEStreamSink::WAVEHeaderWrite", 198, Size);
          }
          if ( g_wppLevels )
          {
            v7 = 34;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != Size )
            CallStackContext::TraceFailure(v15, "CWAVEStreamSink::WAVEHeaderWrite", 196, Size);
        }
        if ( g_wppLevels )
        {
          v7 = 33;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != Size )
          CallStackContext::TraceFailure(v11, "CWAVEStreamSink::WAVEHeaderWrite", 194, Size);
      }
      if ( g_wppLevels )
      {
        v7 = 32;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v6 + 499) != Size )
        CallStackContext::TraceFailure(v6, "CWAVEStreamSink::WAVEHeaderWrite", 192, Size);
    }
    if ( g_wppLevels )
    {
      v7 = 31;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, this, Size);
    }
  }
  if ( Destination )
    Size = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  if ( (unsigned __int8)byte_1801BA10A >= 8u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids, cbMaxLength);
  v28 = this[49];
  if ( v28 )
  {
    if ( (unsigned int)CRIFFMetadata::IsCommitReady(v28) == 1 )
    {
      v29 = this[49];
      if ( v29 )
      {
        (*(void (__fastcall **)(CRIFFMetadata *))(*(_QWORD *)v29 + 16LL))(v29);
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
0x1801240f8  mov     [rsp-28h+arg_18], rbx
0x1801240fd  push    rbp
0x1801240fe  push    rdi
0x1801240ff  push    r12
0x180124101  push    r13
0x180124103  push    r14
0x180124105  mov     rbp, rsp
0x180124108  sub     rsp, 30h
0x18012410c  mov     rdi, rcx
0x18012410f  lea     r12, aCwavestreamsin_12; "CWAVEStreamSink::WAVEHeaderWrite"
0x180124116  mov     rdx, r12; char *
0x180124119  lea     rcx, [rbp+cbMaxLength]; this
0x18012411d  mov     r8d, 0BBh; int
0x180124123  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180124128  xor     r14d, r14d
0x18012412b  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x18012412f  mov     rcx, rdi; this
0x180124132  mov     [rbp+Destination], r14
0x180124136  mov     [rbp+ppBuffer], r14
0x18012413a  mov     [rbp+cbMaxLength], r14d
0x18012413e  call    ?WAVEHeaderGetSize@CWAVEStreamSink@@AEAAJPEAK@Z; CWAVEStreamSink::WAVEHeaderGetSize(ulong *)
0x180124143  lea     r13, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x18012414a  mov     ebx, eax
0x18012414c  test    eax, eax
0x18012414e  jns     loc_1801241FF
0x180124154  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012415b  test    rcx, rcx
0x18012415e  jnz     short loc_1801241A7
0x180124160  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180124167  nop     dword ptr [rax+rax+00h]
0x18012416c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180124173  mov     rcx, rax
0x180124176  test    rax, rax
0x180124179  jz      short loc_180124199
0x18012417b  mov     rax, [rax]
0x18012417e  mov     edx, 7F0h
0x180124183  mov     rax, [rax+8]
0x180124187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012418c  test    eax, eax
0x18012418e  jz      short loc_180124199
0x180124190  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180124197  jmp     short loc_1801241A7
0x180124199  lea     rcx, qword_1801B97E0; this
0x1801241a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801241a7  cmp     [rcx+8], r14b
0x1801241ab  jz      short loc_1801241CE
0x1801241ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801241b2  cmp     [rax+7CCh], ebx
0x1801241b8  jz      short loc_1801241CE
0x1801241ba  mov     r9d, ebx; int
0x1801241bd  mov     r8d, 0C0h; int
0x1801241c3  mov     rdx, r12; char *
0x1801241c6  mov     rcx, rax; this
0x1801241c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801241ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801241d5  jb      loc_18012458E
0x1801241db  mov     edx, 1Fh
0x1801241e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801241e7  mov     r9, rdi
0x1801241ea  mov     r8, r13
0x1801241ed  mov     dword ptr [rsp+30h+var_10], ebx
0x1801241f1  mov     rcx, [rcx+10h]
0x1801241f5  call    WPP_SF_qD
0x1801241fa  jmp     loc_18012458E
0x1801241ff  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x180124202  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180124206  call    cs:__imp_MFCreateMemoryBuffer
0x18012420d  nop     dword ptr [rax+rax+00h]
0x180124212  mov     ebx, eax
0x180124214  test    eax, eax
0x180124216  jns     loc_1801242AD
0x18012421c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180124223  test    rcx, rcx
0x180124226  jnz     short loc_18012426F
0x180124228  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012422f  nop     dword ptr [rax+rax+00h]
0x180124234  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012423b  mov     rcx, rax
0x18012423e  test    rax, rax
0x180124241  jz      short loc_180124261
0x180124243  mov     rax, [rax]
0x180124246  mov     edx, 7F0h
0x18012424b  mov     rax, [rax+8]
0x18012424f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124254  test    eax, eax
0x180124256  jz      short loc_180124261
0x180124258  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012425f  jmp     short loc_18012426F
0x180124261  lea     rcx, qword_1801B97E0; this
0x180124268  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012426f  cmp     [rcx+8], r14b
0x180124273  jz      short loc_180124296
0x180124275  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012427a  cmp     [rax+7CCh], ebx
0x180124280  jz      short loc_180124296
0x180124282  mov     r9d, ebx; int
0x180124285  mov     r8d, 0C2h; int
0x18012428b  mov     rdx, r12; char *
0x18012428e  mov     rcx, rax; this
0x180124291  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180124296  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012429d  jb      loc_18012458E
0x1801242a3  mov     edx, 20h ; ' '
0x1801242a8  jmp     loc_1801241E0
0x1801242ad  mov     rcx, [rbp+ppBuffer]
0x1801242b1  mov     edx, [rbp+cbMaxLength]
0x1801242b4  mov     rax, [rcx]
0x1801242b7  mov     rax, [rax+30h]
0x1801242bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801242c0  mov     ebx, eax
0x1801242c2  test    eax, eax
0x1801242c4  jns     loc_18012435B
0x1801242ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801242d1  test    rcx, rcx
0x1801242d4  jnz     short loc_18012431D
0x1801242d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801242dd  nop     dword ptr [rax+rax+00h]
0x1801242e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801242e9  mov     rcx, rax
0x1801242ec  test    rax, rax
0x1801242ef  jz      short loc_18012430F
0x1801242f1  mov     rax, [rax]
0x1801242f4  mov     edx, 7F0h
0x1801242f9  mov     rax, [rax+8]
0x1801242fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124302  test    eax, eax
0x180124304  jz      short loc_18012430F
0x180124306  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012430d  jmp     short loc_18012431D
0x18012430f  lea     rcx, qword_1801B97E0; this
0x180124316  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012431d  cmp     [rcx+8], r14b
0x180124321  jz      short loc_180124344
0x180124323  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180124328  cmp     [rax+7CCh], ebx
0x18012432e  jz      short loc_180124344
0x180124330  mov     r9d, ebx; int
0x180124333  mov     r8d, 0C4h; int
0x180124339  mov     rdx, r12; char *
0x18012433c  mov     rcx, rax; this
0x18012433f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180124344  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012434b  jb      loc_18012458E
0x180124351  mov     edx, 21h ; '!'
0x180124356  jmp     loc_1801241E0
0x18012435b  mov     rcx, [rbp+ppBuffer]
0x18012435f  lea     rdx, [rbp+Destination]
0x180124363  xor     r9d, r9d
0x180124366  xor     r8d, r8d
0x180124369  mov     rax, [rcx]
0x18012436c  mov     rax, [rax+18h]
0x180124370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124375  mov     ebx, eax
0x180124377  test    eax, eax
0x180124379  jns     loc_180124410
0x18012437f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180124386  test    rcx, rcx
0x180124389  jnz     short loc_1801243D2
0x18012438b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180124392  nop     dword ptr [rax+rax+00h]
0x180124397  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012439e  mov     rcx, rax
0x1801243a1  test    rax, rax
0x1801243a4  jz      short loc_1801243C4
0x1801243a6  mov     rax, [rax]
0x1801243a9  mov     edx, 7F0h
0x1801243ae  mov     rax, [rax+8]
0x1801243b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801243b7  test    eax, eax
0x1801243b9  jz      short loc_1801243C4
0x1801243bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801243c2  jmp     short loc_1801243D2
0x1801243c4  lea     rcx, qword_1801B97E0; this
0x1801243cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801243d2  cmp     [rcx+8], r14b
0x1801243d6  jz      short loc_1801243F9
0x1801243d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801243dd  cmp     [rax+7CCh], ebx
0x1801243e3  jz      short loc_1801243F9
0x1801243e5  mov     r9d, ebx; int
0x1801243e8  mov     r8d, 0C6h; int
0x1801243ee  mov     rdx, r12; char *
0x1801243f1  mov     rcx, rax; this
0x1801243f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801243f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180124400  jb      loc_18012458E
0x180124406  mov     edx, 22h ; '"'
0x18012440b  jmp     loc_1801241E0
0x180124410  mov     r8d, [rbp+cbMaxLength]; int
0x180124414  mov     rcx, rdi; this
0x180124417  mov     rdx, [rbp+Destination]; Destination
0x18012441b  call    ?WAVEHeaderGetBytes@CWAVEStreamSink@@AEAAJPEAEH@Z; CWAVEStreamSink::WAVEHeaderGetBytes(uchar *,int)
0x180124420  mov     ebx, eax
0x180124422  test    eax, eax
0x180124424  jns     loc_1801244BB
0x18012442a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180124431  test    rcx, rcx
0x180124434  jnz     short loc_18012447D
0x180124436  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012443d  nop     dword ptr [rax+rax+00h]
0x180124442  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180124449  mov     rcx, rax
0x18012444c  test    rax, rax
0x18012444f  jz      short loc_18012446F
0x180124451  mov     rax, [rax]
0x180124454  mov     edx, 7F0h
0x180124459  mov     rax, [rax+8]
0x18012445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124462  test    eax, eax
0x180124464  jz      short loc_18012446F
0x180124466  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012446d  jmp     short loc_18012447D
0x18012446f  lea     rcx, qword_1801B97E0; this
0x180124476  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012447d  cmp     [rcx+8], r14b
0x180124481  jz      short loc_1801244A4
0x180124483  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180124488  cmp     [rax+7CCh], ebx
0x18012448e  jz      short loc_1801244A4
0x180124490  mov     r9d, ebx; int
0x180124493  mov     r8d, 0C8h; int
0x180124499  mov     rdx, r12; char *
0x18012449c  mov     rcx, rax; this
0x18012449f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801244a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801244ab  jb      loc_18012458E
0x1801244b1  mov     edx, 23h ; '#'
0x1801244b6  jmp     loc_1801241E0
0x1801244bb  mov     rcx, [rdi+180h]
0x1801244c2  lea     r9, [rdi+168h]
0x1801244c9  mov     r8d, [rbp+cbMaxLength]
0x1801244cd  mov     rdx, [rbp+Destination]
0x1801244d1  mov     rax, [rcx]
0x1801244d4  mov     r10, [rax+68h]
0x1801244d8  mov     rax, [rbp+ppBuffer]
0x1801244dc  mov     [rsp+30h+var_10], rax
0x1801244e1  mov     rax, r10
0x1801244e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801244e9  mov     ebx, eax
0x1801244eb  test    eax, eax
0x1801244ed  jns     loc_180124580
0x1801244f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801244fa  test    rcx, rcx
0x1801244fd  jnz     short loc_180124546
0x1801244ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180124506  nop     dword ptr [rax+rax+00h]
0x18012450b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180124512  mov     rcx, rax
0x180124515  test    rax, rax
0x180124518  jz      short loc_180124538
0x18012451a  mov     rax, [rax]
0x18012451d  mov     edx, 7F0h
0x180124522  mov     rax, [rax+8]
0x180124526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012452b  test    eax, eax
0x18012452d  jz      short loc_180124538
0x18012452f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180124536  jmp     short loc_180124546
0x180124538  lea     rcx, qword_1801B97E0; this
0x18012453f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180124546  cmp     [rcx+8], r14b
0x18012454a  jz      short loc_18012456D
0x18012454c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180124551  cmp     [rax+7CCh], ebx
0x180124557  jz      short loc_18012456D
0x180124559  mov     r9d, ebx; int
0x18012455c  mov     r8d, 0CAh; int
0x180124562  mov     rdx, r12; char *
0x180124565  mov     rcx, rax; this
0x180124568  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012456d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180124574  jb      short loc_18012458E
0x180124576  mov     edx, 24h ; '$'
0x18012457b  jmp     loc_1801241E0
0x180124580  mov     eax, [rbp+cbMaxLength]
0x180124583  add     [rdi+1C0h], rax
0x18012458a  mov     [rbp+Destination], r14
0x18012458e  cmp     [rbp+Destination], r14
0x180124592  jz      short loc_1801245A6
0x180124594  mov     rcx, [rbp+ppBuffer]
0x180124598  mov     rax, [rcx]
0x18012459b  mov     rax, [rax+20h]
0x18012459f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801245a4  mov     ebx, eax
0x1801245a6  cmp     cs:byte_1801BA10A, 8
0x1801245ad  jb      short loc_1801245CB
0x1801245af  mov     rcx, cs:WPP_GLOBAL_Control
0x1801245b6  mov     edx, 25h ; '%'
0x1801245bb  mov     r9d, [rbp+cbMaxLength]
0x1801245bf  mov     r8, r13
0x1801245c2  mov     rcx, [rcx+60h]
0x1801245c6  call    WPP_SF_d
0x1801245cb  mov     rcx, [rdi+188h]; this
0x1801245d2  test    rcx, rcx
0x1801245d5  jz      short loc_180124600
0x1801245d7  call    ?IsCommitReady@CRIFFMetadata@@QEAAHXZ; CRIFFMetadata::IsCommitReady(void)
0x1801245dc  cmp     eax, 1
0x1801245df  jnz     short loc_180124600
0x1801245e1  mov     rcx, [rdi+188h]
0x1801245e8  test    rcx, rcx
  ... truncated ...
```
