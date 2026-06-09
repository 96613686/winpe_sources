# CAVIMediaSourcePlugin::ParseHeader(unsigned __int64,IMFMediaBuffer *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800ecb30`
- end: `0x1800ed09b`
- name: `?ParseHeader@CAVIMediaSourcePlugin@@UEAAJ_KPEAUIMFMediaBuffer@@0PEA_KPEAH@Z`
- size: `1387`
- prototype: `int(CAVIMediaSourcePlugin *__hidden this, unsigned __int64, struct IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180035bb0`
- `0x180036c30`
- `0x180054228`
- `0x18005b030`
- `0x18006e578`
- `0x180079680`
- `0x1800aa328`
- `0x1800b966c`
- `0x1800ecb30`
- `0x180121750`
- `0x180150088`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecba7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecca3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecd7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ece2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecfa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecba7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecca3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecd7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ece2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ecfa3`

## string_xrefs

- `0x1800ecb5a`: `CAVIMediaSourcePlugin::ParseHeader`
- `0x1800ecc04`: `CAVIMediaSourcePlugin::ParseHeader`
- `0x1800ecd00`: `CAVIMediaSourcePlugin::ParseHeader`
- `0x1800ecddc`: `CAVIMediaSourcePlugin::ParseHeader`
- `0x1800ece8b`: `CAVIMediaSourcePlugin::ParseHeader`
- `0x1800ed000`: `CAVIMediaSourcePlugin::ParseHeader`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::ParseHeader(
        CAVIMediaSourcePlugin *this,
        unsigned __int64 a2,
        struct IMFMediaBuffer *a3,
        unsigned __int64 a4,
        unsigned __int64 *a5,
        int *a6)
{
  char *v6; // rbp
  int v8; // r12d
  __int64 v12; // rdx
  int FramesIfNecessary; // ebx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rax
  BOOL v32; // ecx
  unsigned int v33; // esi
  __int64 v34; // rdi
  __int64 v35; // rax
  CAVIStreamParser *v36; // r15
  __int64 v37; // rdx
  unsigned int v38; // eax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  _QWORD v43[2]; // [rsp+30h] [rbp-38h] BYREF
  int v44; // [rsp+70h] [rbp+8h] BYREF

  v6 = (char *)this - 8;
  v8 = *((_DWORD *)this + 153);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CAVIMediaSourcePlugin::ParseHeader", 232);
  CSourcePluginBufferReader::SetFileLength((CAVIMediaSourcePlugin *)((char *)this + 80), a2);
  FramesIfNecessary = CSourcePluginBufferReader::AddBuffer((CAVIMediaSourcePlugin *)((char *)this + 80), a4, a3);
  if ( FramesIfNecessary < 0 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != FramesIfNecessary )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIMediaSourcePlugin::ParseHeader",
          236,
          FramesIfNecessary);
    }
    if ( g_wppLevels )
    {
      v17 = 23;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        v6,
        FramesIfNecessary);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  FramesIfNecessary = CAVIFileParser::ParseHeader(
                        *((CAVIFileParser **)v6 + 10),
                        (CAVIMediaSourcePlugin *)((char *)this + 80),
                        v8);
  if ( FramesIfNecessary == -1072863856 )
  {
    *a6 = 1;
    v19 = *((_QWORD *)v6 + 71);
LABEL_15:
    FramesIfNecessary = 0;
    *a5 = v19;
    goto LABEL_80;
  }
  if ( FramesIfNecessary >= 0 )
  {
    if ( *(_BYTE *)(*((_QWORD *)v6 + 10) + 24LL) && !v8 )
    {
      FramesIfNecessary = CAVIMediaSourcePlugin::CacheFirstFramesIfNecessary((CAVIMediaSourcePlugin *)v6);
      if ( FramesIfNecessary == -1072863856 )
      {
        *a6 = 1;
        v19 = *((_QWORD *)this + 70);
        goto LABEL_15;
      }
      if ( FramesIfNecessary < 0 )
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
          if ( *((_DWORD *)v26 + 499) != FramesIfNecessary )
            CallStackContext::TraceFailure(v26, "CAVIMediaSourcePlugin::ParseHeader", 263, FramesIfNecessary);
        }
        if ( g_wppLevels )
        {
          v17 = 25;
          goto LABEL_12;
        }
        goto LABEL_80;
      }
    }
    CSourcePluginBufferReader::RemoveAllBuffers((CAVIMediaSourcePlugin *)((char *)this + 80));
    FramesIfNecessary = CAVIMediaSourcePlugin::BuildPresentationDescriptor((CAVIMediaSourcePlugin *)v6);
    if ( FramesIfNecessary >= 0 )
    {
      v31 = *((_QWORD *)v6 + 10);
      if ( *(_BYTE *)(v31 + 24) )
      {
        v32 = *(_DWORD *)(v31 + 64) == 2 && (*(_DWORD *)(v31 + 52) & 0x100) != 0;
        *((_DWORD *)this + 152) = v32;
        if ( v32 || *((_DWORD *)this + 153) )
        {
          if ( (unsigned __int8)byte_1801BA109 >= 0x10u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, v6);
        }
        else
        {
          v33 = *(_DWORD *)(v31 + 112);
          v34 = 0;
          v44 = 0;
          while ( (unsigned int)v34 < v33 )
          {
            v35 = *((_QWORD *)this + 9);
            v43[0] = 0;
            v36 = *(CAVIStreamParser **)(*(_QWORD *)(v35 + 104) + 8 * v34);
            FramesIfNecessary = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD *))(**((_QWORD **)v6 + 9)
                                                                                           + 272LL))(
                                  *((_QWORD *)v6 + 9),
                                  (unsigned int)v34,
                                  &v44,
                                  v43);
            if ( FramesIfNecessary < 0 )
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
                CallStackTracing::s_wpInstance = v40;
                if ( v40
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                {
                  v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v39 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v39 + 8) )
              {
                v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                if ( *((_DWORD *)v41 + 499) != FramesIfNecessary )
                  CallStackContext::TraceFailure(v41, "CAVIMediaSourcePlugin::ParseHeader", 285, FramesIfNecessary);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  v6,
                  FramesIfNecessary);
              ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v43);
              goto LABEL_80;
            }
            if ( v44 )
            {
              v38 = CAVIStreamParser::CountConsecutiveVideoFrames(v36);
              *((_DWORD *)this + 151) = v38;
              if ( (unsigned __int8)byte_1801BA109 >= 0x10u )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  28,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  v6,
                  v38);
            }
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v43);
            v34 = (unsigned int)(v34 + 1);
          }
        }
      }
    }
    else
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != FramesIfNecessary )
          CallStackContext::TraceFailure(v30, "CAVIMediaSourcePlugin::ParseHeader", 269, FramesIfNecessary);
      }
      if ( g_wppLevels )
      {
        v17 = 26;
        goto LABEL_12;
      }
    }
    goto LABEL_80;
  }
  v20 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
    CallStackTracing::s_wpInstance = v21;
    if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v20 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v20 + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
    if ( *((_DWORD *)v22 + 499) != FramesIfNecessary )
      CallStackContext::TraceFailure(v22, "CAVIMediaSourcePlugin::ParseHeader", 245, FramesIfNecessary);
  }
  if ( g_wppLevels )
  {
    v17 = 24;
    goto LABEL_12;
  }
LABEL_80:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)FramesIfNecessary;
}

```

## disassembly

```asm
0x1800ecb30  mov     [rsp+arg_8], rbx
0x1800ecb35  mov     [rsp+arg_10], rbp
0x1800ecb3a  push    rsi
0x1800ecb3b  push    rdi
0x1800ecb3c  push    r12
0x1800ecb3e  push    r14
0x1800ecb40  push    r15
0x1800ecb42  sub     rsp, 40h
0x1800ecb46  lea     rbp, [rcx-8]
0x1800ecb4a  mov     rdi, r8
0x1800ecb4d  mov     r12d, [rbp+26Ch]
0x1800ecb54  mov     rbx, rdx
0x1800ecb57  mov     r14, rcx
0x1800ecb5a  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ecb61  mov     r8d, 0E8h; int
0x1800ecb67  lea     rcx, [rsp+68h+arg_0]; this
0x1800ecb6c  mov     rsi, r9
0x1800ecb6f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ecb74  lea     r15, [r14+50h]
0x1800ecb78  mov     rdx, rbx; unsigned __int64
0x1800ecb7b  mov     rcx, r15; this
0x1800ecb7e  call    ?SetFileLength@CSourcePluginBufferReader@@QEAAX_K@Z; CSourcePluginBufferReader::SetFileLength(unsigned __int64)
0x1800ecb83  mov     r8, rdi; struct IMFMediaBuffer *
0x1800ecb86  mov     rdx, rsi; unsigned __int64
0x1800ecb89  mov     rcx, r15; this
0x1800ecb8c  call    ?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z; CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)
0x1800ecb91  mov     ebx, eax
0x1800ecb93  test    eax, eax
0x1800ecb95  jns     loc_1800ECC4E
0x1800ecb9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecba2  test    rcx, rcx
0x1800ecba5  jnz     short loc_1800ECBEE
0x1800ecba7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ecbae  nop     dword ptr [rax+rax+00h]
0x1800ecbb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecbba  mov     rcx, rax
0x1800ecbbd  test    rax, rax
0x1800ecbc0  jz      short loc_1800ECBE0
0x1800ecbc2  mov     rax, [rax]
0x1800ecbc5  mov     edx, 7F0h
0x1800ecbca  mov     rax, [rax+8]
0x1800ecbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecbd3  test    eax, eax
0x1800ecbd5  jz      short loc_1800ECBE0
0x1800ecbd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecbde  jmp     short loc_1800ECBEE
0x1800ecbe0  lea     rcx, qword_1801B97E0; this
0x1800ecbe7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecbee  cmp     byte ptr [rcx+8], 0
0x1800ecbf2  jz      short loc_1800ECC19
0x1800ecbf4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ecbf9  cmp     [rax+7CCh], ebx
0x1800ecbff  jz      short loc_1800ECC19
0x1800ecc01  mov     r9d, ebx; int
0x1800ecc04  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ecc0b  mov     r8d, 0ECh; int
0x1800ecc11  mov     rcx, rax; this
0x1800ecc14  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ecc19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ecc20  jb      loc_1800ED075
0x1800ecc26  mov     edx, 17h
0x1800ecc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecc32  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800ecc39  mov     r9, rbp
0x1800ecc3c  mov     [rsp+68h+var_48], ebx
0x1800ecc40  mov     rcx, [rcx+10h]
0x1800ecc44  call    WPP_SF_qD
0x1800ecc49  jmp     loc_1800ED075
0x1800ecc4e  mov     rcx, [rbp+50h]; this
0x1800ecc52  mov     r8d, r12d; int
0x1800ecc55  mov     rdx, r15; struct CSourcePluginBufferReader *
0x1800ecc58  call    ?ParseHeader@CAVIFileParser@@QEAAJPEAVCSourcePluginBufferReader@@H@Z; CAVIFileParser::ParseHeader(CSourcePluginBufferReader *,int)
0x1800ecc5d  mov     edi, 0C00D6590h
0x1800ecc62  mov     ebx, eax
0x1800ecc64  cmp     eax, edi
0x1800ecc66  jnz     short loc_1800ECC8F
0x1800ecc68  mov     rax, [rsp+68h+arg_28]
0x1800ecc70  mov     dword ptr [rax], 1
0x1800ecc76  mov     rcx, [rbp+238h]
0x1800ecc7d  mov     rax, [rsp+68h+arg_20]
0x1800ecc85  xor     ebx, ebx
0x1800ecc87  mov     [rax], rcx
0x1800ecc8a  jmp     loc_1800ED075
0x1800ecc8f  test    ebx, ebx
0x1800ecc91  jns     loc_1800ECD2C
0x1800ecc97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecc9e  test    rcx, rcx
0x1800ecca1  jnz     short loc_1800ECCEA
0x1800ecca3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800eccaa  nop     dword ptr [rax+rax+00h]
0x1800eccaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eccb6  mov     rcx, rax
0x1800eccb9  test    rax, rax
0x1800eccbc  jz      short loc_1800ECCDC
0x1800eccbe  mov     rax, [rax]
0x1800eccc1  mov     edx, 7F0h
0x1800eccc6  mov     rax, [rax+8]
0x1800eccca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecccf  test    eax, eax
0x1800eccd1  jz      short loc_1800ECCDC
0x1800eccd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eccda  jmp     short loc_1800ECCEA
0x1800eccdc  lea     rcx, qword_1801B97E0; this
0x1800ecce3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eccea  cmp     byte ptr [rcx+8], 0
0x1800eccee  jz      short loc_1800ECD15
0x1800eccf0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800eccf5  cmp     [rax+7CCh], ebx
0x1800eccfb  jz      short loc_1800ECD15
0x1800eccfd  mov     r9d, ebx; int
0x1800ecd00  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ecd07  mov     r8d, 0F5h; int
0x1800ecd0d  mov     rcx, rax; this
0x1800ecd10  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ecd15  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ecd1c  jb      loc_1800ED075
0x1800ecd22  mov     edx, 18h
0x1800ecd27  jmp     loc_1800ECC2B
0x1800ecd2c  mov     rax, [rbp+50h]
0x1800ecd30  cmp     byte ptr [rax+18h], 0
0x1800ecd34  jz      loc_1800ECE08
0x1800ecd3a  test    r12d, r12d
0x1800ecd3d  jnz     loc_1800ECE08
0x1800ecd43  mov     rcx, rbp; this
0x1800ecd46  call    ?CacheFirstFramesIfNecessary@CAVIMediaSourcePlugin@@AEAAJXZ; CAVIMediaSourcePlugin::CacheFirstFramesIfNecessary(void)
0x1800ecd4b  mov     ebx, eax
0x1800ecd4d  cmp     eax, edi
0x1800ecd4f  jnz     short loc_1800ECD6B
0x1800ecd51  mov     rax, [rsp+68h+arg_28]
0x1800ecd59  mov     dword ptr [rax], 1
0x1800ecd5f  mov     rcx, [r14+230h]
0x1800ecd66  jmp     loc_1800ECC7D
0x1800ecd6b  test    ebx, ebx
0x1800ecd6d  jns     loc_1800ECE08
0x1800ecd73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecd7a  test    rcx, rcx
0x1800ecd7d  jnz     short loc_1800ECDC6
0x1800ecd7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ecd86  nop     dword ptr [rax+rax+00h]
0x1800ecd8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecd92  mov     rcx, rax
0x1800ecd95  test    rax, rax
0x1800ecd98  jz      short loc_1800ECDB8
0x1800ecd9a  mov     rax, [rax]
0x1800ecd9d  mov     edx, 7F0h
0x1800ecda2  mov     rax, [rax+8]
0x1800ecda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecdab  test    eax, eax
0x1800ecdad  jz      short loc_1800ECDB8
0x1800ecdaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecdb6  jmp     short loc_1800ECDC6
0x1800ecdb8  lea     rcx, qword_1801B97E0; this
0x1800ecdbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecdc6  cmp     byte ptr [rcx+8], 0
0x1800ecdca  jz      short loc_1800ECDF1
0x1800ecdcc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ecdd1  cmp     [rax+7CCh], ebx
0x1800ecdd7  jz      short loc_1800ECDF1
0x1800ecdd9  mov     r9d, ebx; int
0x1800ecddc  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ecde3  mov     r8d, 107h; int
0x1800ecde9  mov     rcx, rax; this
0x1800ecdec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ecdf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ecdf8  jb      loc_1800ED075
0x1800ecdfe  mov     edx, 19h
0x1800ece03  jmp     loc_1800ECC2B
0x1800ece08  mov     rcx, r15; this
0x1800ece0b  call    ?RemoveAllBuffers@CSourcePluginBufferReader@@QEAAXXZ; CSourcePluginBufferReader::RemoveAllBuffers(void)
0x1800ece10  mov     rcx, rbp; this
0x1800ece13  call    ?BuildPresentationDescriptor@CAVIMediaSourcePlugin@@AEAAJXZ; CAVIMediaSourcePlugin::BuildPresentationDescriptor(void)
0x1800ece18  mov     ebx, eax
0x1800ece1a  test    eax, eax
0x1800ece1c  jns     loc_1800ECEB7
0x1800ece22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ece29  test    rcx, rcx
0x1800ece2c  jnz     short loc_1800ECE75
0x1800ece2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ece35  nop     dword ptr [rax+rax+00h]
0x1800ece3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ece41  mov     rcx, rax
0x1800ece44  test    rax, rax
0x1800ece47  jz      short loc_1800ECE67
0x1800ece49  mov     rax, [rax]
0x1800ece4c  mov     edx, 7F0h
0x1800ece51  mov     rax, [rax+8]
0x1800ece55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ece5a  test    eax, eax
0x1800ece5c  jz      short loc_1800ECE67
0x1800ece5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ece65  jmp     short loc_1800ECE75
0x1800ece67  lea     rcx, qword_1801B97E0; this
0x1800ece6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ece75  cmp     byte ptr [rcx+8], 0
0x1800ece79  jz      short loc_1800ECEA0
0x1800ece7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ece80  cmp     [rax+7CCh], ebx
0x1800ece86  jz      short loc_1800ECEA0
0x1800ece88  mov     r9d, ebx; int
0x1800ece8b  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ece92  mov     r8d, 10Dh; int
0x1800ece98  mov     rcx, rax; this
0x1800ece9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ecea0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ecea7  jb      loc_1800ED075
0x1800ecead  mov     edx, 1Ah
0x1800eceb2  jmp     loc_1800ECC2B
0x1800eceb7  mov     rax, [rbp+50h]
0x1800ecebb  cmp     byte ptr [rax+18h], 0
0x1800ecebf  jz      loc_1800ED075
0x1800ecec5  cmp     dword ptr [rax+40h], 2
0x1800ecec9  jnz     short loc_1800ECEDB
0x1800ececb  test    dword ptr [rax+34h], 100h
0x1800eced2  jz      short loc_1800ECEDB
0x1800eced4  mov     ecx, 1
0x1800eced9  jmp     short loc_1800ECEDD
0x1800ecedb  xor     ecx, ecx
0x1800ecedd  mov     [r14+260h], ecx
0x1800ecee4  test    ecx, ecx
0x1800ecee6  jnz     loc_1800ED04D
0x1800eceec  cmp     [r14+264h], ecx
0x1800ecef3  jnz     loc_1800ED04D
0x1800ecef9  mov     esi, [rax+70h]
0x1800ecefc  xor     edi, edi
0x1800ecefe  mov     [rsp+68h+arg_0], ecx
0x1800ecf02  cmp     edi, esi
0x1800ecf04  jnb     loc_1800ED075
0x1800ecf0a  mov     rax, [r14+48h]
0x1800ecf0e  lea     r9, [rsp+68h+var_38]
0x1800ecf13  mov     [rsp+68h+var_38], 0
0x1800ecf1c  lea     r8, [rsp+68h+arg_0]
0x1800ecf21  mov     edx, edi
0x1800ecf23  mov     rcx, [rax+68h]
0x1800ecf27  mov     r15, [rcx+rdi*8]
0x1800ecf2b  mov     rcx, [rbp+48h]
0x1800ecf2f  mov     rax, [rcx]
0x1800ecf32  mov     rax, [rax+110h]
0x1800ecf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf3e  mov     ebx, eax
0x1800ecf40  test    eax, eax
0x1800ecf42  js      short loc_1800ECF97
0x1800ecf44  cmp     [rsp+68h+arg_0], 0
0x1800ecf49  jz      short loc_1800ECF86
0x1800ecf4b  mov     rcx, r15; this
0x1800ecf4e  call    ?CountConsecutiveVideoFrames@CAVIStreamParser@@QEAAKXZ; CAVIStreamParser::CountConsecutiveVideoFrames(void)
0x1800ecf53  mov     [r14+25Ch], eax
0x1800ecf5a  cmp     cs:byte_1801BA109, 10h
0x1800ecf61  jb      short loc_1800ECF86
0x1800ecf63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecf6a  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800ecf71  mov     edx, 1Ch
0x1800ecf76  mov     [rsp+68h+var_48], eax
0x1800ecf7a  mov     r9, rbp
0x1800ecf7d  mov     rcx, [rcx+38h]
0x1800ecf81  call    WPP_SF_qD
0x1800ecf86  lea     rcx, [rsp+68h+var_38]; void *
0x1800ecf8b  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ecf90  inc     edi
0x1800ecf92  jmp     loc_1800ECF02
0x1800ecf97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecf9e  test    rcx, rcx
0x1800ecfa1  jnz     short loc_1800ECFEA
0x1800ecfa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ecfaa  nop     dword ptr [rax+rax+00h]
0x1800ecfaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecfb6  mov     rcx, rax
0x1800ecfb9  test    rax, rax
0x1800ecfbc  jz      short loc_1800ECFDC
0x1800ecfbe  mov     rax, [rax]
0x1800ecfc1  mov     edx, 7F0h
0x1800ecfc6  mov     rax, [rax+8]
0x1800ecfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecfcf  test    eax, eax
0x1800ecfd1  jz      short loc_1800ECFDC
0x1800ecfd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecfda  jmp     short loc_1800ECFEA
0x1800ecfdc  lea     rcx, qword_1801B97E0; this
0x1800ecfe3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ecfea  cmp     byte ptr [rcx+8], 0
0x1800ecfee  jz      short loc_1800ED015
0x1800ecff0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ecff5  cmp     [rax+7CCh], ebx
0x1800ecffb  jz      short loc_1800ED015
0x1800ecffd  mov     r9d, ebx; int
0x1800ed000  lea     rdx, aCavimediasourc_31; "CAVIMediaSourcePlugin::ParseHeader"
0x1800ed007  mov     r8d, 11Dh; int
0x1800ed00d  mov     rcx, rax; this
0x1800ed010  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ed015  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ed01c  jb      short loc_1800ED041
0x1800ed01e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed025  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800ed02c  mov     edx, 1Bh
0x1800ed031  mov     [rsp+68h+var_48], ebx
0x1800ed035  mov     r9, rbp
0x1800ed038  mov     rcx, [rcx+10h]
0x1800ed03c  call    WPP_SF_qD
0x1800ed041  lea     rcx, [rsp+68h+var_38]; void *
0x1800ed046  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ed04b  jmp     short loc_1800ED075
  ... truncated ...
```
