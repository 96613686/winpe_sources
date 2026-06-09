# CAVIIAVSStreamParser::CreateAudioFormatChange(tWAVEFORMATEX *,IMFSample * *)

- ea: `0x1801455cc`
- end: `0x1801459d7`
- name: `?CreateAudioFormatChange@CAVIIAVSStreamParser@@AEAAJPEAUtWAVEFORMATEX@@PEAPEAUIMFSample@@@Z`
- size: `1035`
- prototype: `int(CAVIIAVSStreamParser *__hidden this, struct tWAVEFORMATEX *, struct IMFSample **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180144a80`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x1801455cc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801456ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145794`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145859`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145912`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801456ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145794`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145859`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145912`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1801456c8`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1801456c8`
- `MFPlat!MFCreateSample` at `0x180145772`
- `MFPlat!MFCreateSample` at `0x180145772`
- `MFPlat!MFCreateMediaType` at `0x180145610`
- `MFPlat!MFCreateMediaType` at `0x180145610`

## string_xrefs

- `0x1801455e2`: `CAVIIAVSStreamParser::CreateAudioFormatChange`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::CreateAudioFormatChange(
        CAVIIAVSStreamParser *this,
        struct tWAVEFORMATEX *a2,
        struct IMFSample **a3)
{
  __int64 v6; // rdx
  HRESULT v7; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  IMFSample *v20; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v32; // [rsp+50h] [rbp+8h] BYREF
  IMFMediaType *ppMFType; // [rsp+68h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v32,
    "CAVIIAVSStreamParser::CreateAudioFormatChange",
    138);
  ppMFType = 0;
  v7 = MFCreateMediaType(&ppMFType);
  if ( v7 >= 0 )
  {
    v7 = MFInitMediaTypeFromWaveFormatEx(ppMFType, a2, a2->cbSize + 18);
    if ( v7 >= 0 )
    {
      v7 = MFCreateSample(a3);
      if ( v7 >= 0 )
      {
        v20 = *a3;
        SetSampleTime = (*a3)->lpVtbl->SetSampleTime;
        v22 = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)this + 96LL))(this);
        v7 = ((__int64 (__fastcall *)(IMFSample *, __int64))SetSampleTime)(v20, v22);
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(_QWORD, __int64 *, IMFMediaType *))(*a3)->lpVtbl->SetUnknown)(
                 *a3,
                 AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
                 ppMFType);
          if ( v7 < 0 )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAVIIAVSStreamParser::CreateAudioFormatChange",
                  148,
                  v7);
            }
            if ( g_wppLevels )
            {
              v11 = 23;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != v7 )
              CallStackContext::TraceFailure(v26, "CAVIIAVSStreamParser::CreateAudioFormatChange", 147, v7);
          }
          if ( g_wppLevels )
          {
            v11 = 22;
            goto LABEL_56;
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
          if ( *((_DWORD *)v19 + 499) != v7 )
            CallStackContext::TraceFailure(v19, "CAVIIAVSStreamParser::CreateAudioFormatChange", 146, v7);
        }
        if ( g_wppLevels )
        {
          v11 = 21;
          goto LABEL_56;
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
        if ( *((_DWORD *)v15 + 499) != v7 )
          CallStackContext::TraceFailure(v15, "CAVIIAVSStreamParser::CreateAudioFormatChange", 143, v7);
      }
      if ( g_wppLevels )
      {
        v11 = 20;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v7 )
        CallStackContext::TraceFailure(v10, "CAVIIAVSStreamParser::CreateAudioFormatChange", 142, v7);
    }
    if ( g_wppLevels )
    {
      v11 = 19;
LABEL_56:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v7);
    }
  }
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801455cc  mov     [rsp+arg_8], rbx
0x1801455d1  mov     [rsp+arg_10], rsi
0x1801455d6  push    rdi
0x1801455d7  push    r14
0x1801455d9  push    r15
0x1801455db  sub     rsp, 30h
0x1801455df  mov     r14, r8
0x1801455e2  lea     r15, aCaviiavsstream_3; "CAVIIAVSStreamParser::CreateAudioFormat"...
0x1801455e9  mov     rdi, rdx
0x1801455ec  mov     rsi, rcx
0x1801455ef  mov     rdx, r15; char *
0x1801455f2  lea     rcx, [rsp+48h+arg_0]; this
0x1801455f7  mov     r8d, 8Ah; int
0x1801455fd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180145602  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x180145607  mov     [rsp+48h+ppMFType], 0
0x180145610  call    cs:__imp_MFCreateMediaType
0x180145617  nop     dword ptr [rax+rax+00h]
0x18014561c  mov     ebx, eax
0x18014561e  test    eax, eax
0x180145620  jns     loc_1801456B7
0x180145626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014562d  test    rcx, rcx
0x180145630  jnz     short loc_180145679
0x180145632  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145639  nop     dword ptr [rax+rax+00h]
0x18014563e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145645  mov     rcx, rax
0x180145648  test    rax, rax
0x18014564b  jz      short loc_18014566B
0x18014564d  mov     rax, [rax]
0x180145650  mov     edx, 7F0h
0x180145655  mov     rax, [rax+8]
0x180145659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014565e  test    eax, eax
0x180145660  jz      short loc_18014566B
0x180145662  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145669  jmp     short loc_180145679
0x18014566b  lea     rcx, qword_1801B97E0; this
0x180145672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145679  cmp     byte ptr [rcx+8], 0
0x18014567d  jz      short loc_1801456A0
0x18014567f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145684  cmp     [rax+7CCh], ebx
0x18014568a  jz      short loc_1801456A0
0x18014568c  mov     r9d, ebx; int
0x18014568f  mov     r8d, 8Eh; int
0x180145695  mov     rdx, r15; char *
0x180145698  mov     rcx, rax; this
0x18014569b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801456a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801456a7  jb      loc_1801459AC
0x1801456ad  mov     edx, 13h
0x1801456b2  jmp     loc_18014598E
0x1801456b7  movzx   r8d, word ptr [rdi+10h]
0x1801456bc  mov     rdx, rdi; pWaveFormat
0x1801456bf  mov     rcx, [rsp+48h+ppMFType]; pMFType
0x1801456c4  add     r8d, 12h; cbBufSize
0x1801456c8  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x1801456cf  nop     dword ptr [rax+rax+00h]
0x1801456d4  mov     ebx, eax
0x1801456d6  test    eax, eax
0x1801456d8  jns     loc_18014576F
0x1801456de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801456e5  test    rcx, rcx
0x1801456e8  jnz     short loc_180145731
0x1801456ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801456f1  nop     dword ptr [rax+rax+00h]
0x1801456f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801456fd  mov     rcx, rax
0x180145700  test    rax, rax
0x180145703  jz      short loc_180145723
0x180145705  mov     rax, [rax]
0x180145708  mov     edx, 7F0h
0x18014570d  mov     rax, [rax+8]
0x180145711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145716  test    eax, eax
0x180145718  jz      short loc_180145723
0x18014571a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145721  jmp     short loc_180145731
0x180145723  lea     rcx, qword_1801B97E0; this
0x18014572a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145731  cmp     byte ptr [rcx+8], 0
0x180145735  jz      short loc_180145758
0x180145737  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014573c  cmp     [rax+7CCh], ebx
0x180145742  jz      short loc_180145758
0x180145744  mov     r9d, ebx; int
0x180145747  mov     r8d, 8Fh; int
0x18014574d  mov     rdx, r15; char *
0x180145750  mov     rcx, rax; this
0x180145753  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145758  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014575f  jb      loc_1801459AC
0x180145765  mov     edx, 14h
0x18014576a  jmp     loc_18014598E
0x18014576f  mov     rcx, r14; ppIMFSample
0x180145772  call    cs:__imp_MFCreateSample
0x180145779  nop     dword ptr [rax+rax+00h]
0x18014577e  mov     ebx, eax
0x180145780  test    eax, eax
0x180145782  jns     loc_180145819
0x180145788  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014578f  test    rcx, rcx
0x180145792  jnz     short loc_1801457DB
0x180145794  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014579b  nop     dword ptr [rax+rax+00h]
0x1801457a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801457a7  mov     rcx, rax
0x1801457aa  test    rax, rax
0x1801457ad  jz      short loc_1801457CD
0x1801457af  mov     rax, [rax]
0x1801457b2  mov     edx, 7F0h
0x1801457b7  mov     rax, [rax+8]
0x1801457bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801457c0  test    eax, eax
0x1801457c2  jz      short loc_1801457CD
0x1801457c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801457cb  jmp     short loc_1801457DB
0x1801457cd  lea     rcx, qword_1801B97E0; this
0x1801457d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801457db  cmp     byte ptr [rcx+8], 0
0x1801457df  jz      short loc_180145802
0x1801457e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801457e6  cmp     [rax+7CCh], ebx
0x1801457ec  jz      short loc_180145802
0x1801457ee  mov     r9d, ebx; int
0x1801457f1  mov     r8d, 92h; int
0x1801457f7  mov     rdx, r15; char *
0x1801457fa  mov     rcx, rax; this
0x1801457fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145802  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145809  jb      loc_1801459AC
0x18014580f  mov     edx, 15h
0x180145814  jmp     loc_18014598E
0x180145819  mov     rdi, [r14]
0x18014581c  mov     rcx, rsi
0x18014581f  mov     rdx, [rsi]
0x180145822  mov     rax, [rdi]
0x180145825  mov     rbx, [rax+120h]
0x18014582c  mov     rax, [rdx+60h]
0x180145830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145835  mov     rdx, rax
0x180145838  mov     rcx, rdi
0x18014583b  mov     rax, rbx
0x18014583e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145843  mov     ebx, eax
0x180145845  test    eax, eax
0x180145847  jns     loc_1801458DE
0x18014584d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145854  test    rcx, rcx
0x180145857  jnz     short loc_1801458A0
0x180145859  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145860  nop     dword ptr [rax+rax+00h]
0x180145865  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014586c  mov     rcx, rax
0x18014586f  test    rax, rax
0x180145872  jz      short loc_180145892
0x180145874  mov     rax, [rax]
0x180145877  mov     edx, 7F0h
0x18014587c  mov     rax, [rax+8]
0x180145880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145885  test    eax, eax
0x180145887  jz      short loc_180145892
0x180145889  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145890  jmp     short loc_1801458A0
0x180145892  lea     rcx, qword_1801B97E0; this
0x180145899  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801458a0  cmp     byte ptr [rcx+8], 0
0x1801458a4  jz      short loc_1801458C7
0x1801458a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801458ab  cmp     [rax+7CCh], ebx
0x1801458b1  jz      short loc_1801458C7
0x1801458b3  mov     r9d, ebx; int
0x1801458b6  mov     r8d, 93h; int
0x1801458bc  mov     rdx, r15; char *
0x1801458bf  mov     rcx, rax; this
0x1801458c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801458c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801458ce  jb      loc_1801459AC
0x1801458d4  mov     edx, 16h
0x1801458d9  jmp     loc_18014598E
0x1801458de  mov     rcx, [r14]
0x1801458e1  lea     rdx, AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE
0x1801458e8  mov     r8, [rsp+48h+ppMFType]
0x1801458ed  mov     rax, [rcx]
0x1801458f0  mov     rax, [rax+0D8h]
0x1801458f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801458fc  mov     ebx, eax
0x1801458fe  test    eax, eax
0x180145900  jns     loc_1801459AC
0x180145906  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014590d  test    rcx, rcx
0x180145910  jnz     short loc_180145959
0x180145912  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145919  nop     dword ptr [rax+rax+00h]
0x18014591e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145925  mov     rcx, rax
0x180145928  test    rax, rax
0x18014592b  jz      short loc_18014594B
0x18014592d  mov     rax, [rax]
0x180145930  mov     edx, 7F0h
0x180145935  mov     rax, [rax+8]
0x180145939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014593e  test    eax, eax
0x180145940  jz      short loc_18014594B
0x180145942  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145949  jmp     short loc_180145959
0x18014594b  lea     rcx, qword_1801B97E0; this
0x180145952  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145959  cmp     byte ptr [rcx+8], 0
0x18014595d  jz      short loc_180145980
0x18014595f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145964  cmp     [rax+7CCh], ebx
0x18014596a  jz      short loc_180145980
0x18014596c  mov     r9d, ebx; int
0x18014596f  mov     r8d, 94h; int
0x180145975  mov     rdx, r15; char *
0x180145978  mov     rcx, rax; this
0x18014597b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145980  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145987  jb      short loc_1801459AC
0x180145989  mov     edx, 17h
0x18014598e  mov     rcx, cs:WPP_GLOBAL_Control
0x180145995  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18014599c  mov     r9, rsi
0x18014599f  mov     [rsp+48h+var_28], ebx
0x1801459a3  mov     rcx, [rcx+10h]
0x1801459a7  call    WPP_SF_qD
0x1801459ac  lea     rcx, [rsp+48h+ppMFType]; void *
0x1801459b1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1801459b6  lea     rcx, [rsp+48h+arg_0]; this
0x1801459bb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801459c0  mov     rsi, [rsp+48h+arg_10]
0x1801459c5  mov     eax, ebx
0x1801459c7  mov     rbx, [rsp+48h+arg_8]
0x1801459cc  add     rsp, 30h
0x1801459d0  pop     r15
0x1801459d2  pop     r14
0x1801459d4  pop     rdi
0x1801459d5  retn
```
