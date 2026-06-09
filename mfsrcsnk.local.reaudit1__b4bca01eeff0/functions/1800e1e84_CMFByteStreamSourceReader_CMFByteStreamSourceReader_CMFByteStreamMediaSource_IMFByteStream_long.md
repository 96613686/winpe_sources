# CMFByteStreamSourceReader::CMFByteStreamSourceReader(CMFByteStreamMediaSource *,IMFByteStream *,long *)

- ea: `0x1800e1e84`
- end: `0x1800e22d3`
- name: `??0CMFByteStreamSourceReader@@QEAA@PEAVCMFByteStreamMediaSource@@PEAUIMFByteStream@@PEAJ@Z`
- size: `1103`
- prototype: `CMFByteStreamSourceReader *__fastcall(CMFByteStreamSourceReader *__hidden this, struct CMFByteStreamMediaSource *, struct IMFByteStream *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800dd428`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18005189c`
- `0x180079680`
- `0x1800e1e84`
- `0x1800fea6c`
- `0x180150a50`
- `0x180151328`
- `0x1801710ec`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1f3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e20d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e21d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1f3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e20d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e21d3`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800e2195`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800e2195`

## string_xrefs

- `0x1800e1ee4`: `CMFByteStreamSourceReader::CMFByteStreamSourceReader`
- `0x1800e1f9a`: `CMFByteStreamSourceReader::CMFByteStreamSourceReader`
- `0x1800e205f`: `CMFByteStreamSourceReader::CMFByteStreamSourceReader`
- `0x1800e2132`: `CMFByteStreamSourceReader::CMFByteStreamSourceReader`
- `0x1800e2230`: `CMFByteStreamSourceReader::CMFByteStreamSourceReader`
- `0x1800e218c`: `Network\FileReadSectorSizeInKB`

## pseudocode

```c
CMFByteStreamSourceReader *__fastcall CMFByteStreamSourceReader::CMFByteStreamSourceReader(
        CMFByteStreamSourceReader *this,
        struct CMFByteStreamMediaSource *a2,
        struct IMFByteStream *a3,
        int *a4)
{
  struct IMFByteStream **v4; // rsi
  __int64 v7; // rdx
  int updated; // ebx
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rax
  int v28; // [rsp+70h] [rbp+40h] BYREF
  __int64 v29; // [rsp+78h] [rbp+48h] BYREF
  __int64 v30; // [rsp+88h] [rbp+58h] BYREF

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &CMFByteStreamSourceReader::`vftable';
  v4 = (struct IMFByteStream **)((char *)this + 32);
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = 0x40000;
  ComSmartPtr<CID3Footer>::ComSmartPtr<CID3Footer>((char *)this + 32, a3);
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = -1;
  *((_QWORD *)this + 9) = -1;
  *((_QWORD *)this + 11) = -1;
  *((_DWORD *)this + 11) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 12) = this;
  *((_QWORD *)this + 13) = 1;
  *((_QWORD *)this + 14) = 0;
  v29 = 0;
  v30 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v28,
    "CMFByteStreamSourceReader::CMFByteStreamSourceReader",
    212);
  updated = *a4;
  if ( *a4 >= 0 )
  {
    updated = CMFByteStreamSourceReader::UpdateByteStreamCharacteristics(this);
    if ( updated >= 0 )
    {
      if ( ((unsigned __int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))(*v4)->lpVtbl->QueryInterface)(
             *v4,
             &GUID_64976bfa_fb61_4041_9069_8c9a5f659beb,
             &v30)
        || (updated = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v30 + 24LL))(v30, (char *)this + 44),
            updated >= 0) )
      {
        if ( ((__int64 (__fastcall *)(struct IMFByteStream *, GUID *, __int64 *))(*v4)->lpVtbl->QueryInterface)(
               *v4,
               &IID_IMFByteStreamBuffering,
               &v29) < 0 )
        {
          v28 = 0;
          MFGetConfigurationDWORD(0, L"Network\\FileReadSectorSizeInKB", &v28);
          if ( v28 )
            *((_DWORD *)this + 7) = v28 << 10;
        }
        else
        {
          *((_DWORD *)this + 7) = 0x4000;
        }
        updated = CByteStreamCacheReader2::CreateInstance(
                    *v4,
                    *((_DWORD *)this + 7),
                    (struct CByteStreamCacheReader2 **)this + 2);
        if ( updated >= 0 )
        {
          v26 = v29;
          if ( v29 )
          {
            CMFByteStreamSourceReader::DisallowReadAhead(this);
            v26 = v29;
          }
          if ( (unsigned __int8)byte_1801BA10B >= 8u )
            WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 17), v21, v22, this, *((_DWORD *)this + 11), v26);
        }
        else
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CMFByteStreamSourceReader::CMFByteStreamSourceReader",
                253,
                updated);
          }
          if ( g_wppLevels )
          {
            v12 = 21;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != updated )
            CallStackContext::TraceFailure(v20, "CMFByteStreamSourceReader::CMFByteStreamSourceReader", 221, updated);
        }
        if ( g_wppLevels )
        {
          v12 = 20;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != updated )
          CallStackContext::TraceFailure(v16, "CMFByteStreamSourceReader::CMFByteStreamSourceReader", 217, updated);
      }
      if ( g_wppLevels )
      {
        v12 = 19;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
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
      if ( *((_DWORD *)v11 + 499) != updated )
        CallStackContext::TraceFailure(v11, "CMFByteStreamSourceReader::CMFByteStreamSourceReader", 212, updated);
    }
    if ( g_wppLevels )
    {
      v12 = 18;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids,
        this,
        updated);
    }
  }
  *a4 = updated;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v30);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v29);
  return this;
}

```

## disassembly

```asm
0x1800e1e84  mov     [rsp-38h+arg_10], rbx
0x1800e1e89  push    rbp
0x1800e1e8a  push    rsi
0x1800e1e8b  push    rdi
0x1800e1e8c  push    r12
0x1800e1e8e  push    r13
0x1800e1e90  push    r14
0x1800e1e92  push    r15
0x1800e1e94  mov     rbp, rsp
0x1800e1e97  sub     rsp, 30h
0x1800e1e9b  mov     [rcx+8], rdx
0x1800e1e9f  lea     rax, ??_7CMFByteStreamSourceReader@@6B@; const CMFByteStreamSourceReader::`vftable'
0x1800e1ea6  xor     r13d, r13d
0x1800e1ea9  mov     [rcx], rax
0x1800e1eac  lea     rsi, [rcx+20h]
0x1800e1eb0  mov     [rcx+10h], r13
0x1800e1eb4  mov     [rcx+18h], r13d
0x1800e1eb8  mov     rdi, rcx
0x1800e1ebb  mov     dword ptr [rcx+1Ch], 40000h
0x1800e1ec2  mov     rdx, r8
0x1800e1ec5  mov     rcx, rsi
0x1800e1ec8  mov     r12, r9
0x1800e1ecb  call    ??0?$ComSmartPtr@VCID3Footer@@@@QEAA@PEAVCID3Footer@@@Z; ComSmartPtr<CID3Footer>::ComSmartPtr<CID3Footer>(CID3Footer *)
0x1800e1ed0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e1ed4  mov     [rdi+28h], r13d
0x1800e1ed8  mov     [rdi+30h], rax
0x1800e1edc  lea     r14, [rdi+2Ch]
0x1800e1ee0  mov     [rdi+48h], rax
0x1800e1ee4  lea     rdx, aCmfbytestreams_20; "CMFByteStreamSourceReader::CMFByteStrea"...
0x1800e1eeb  mov     [rdi+58h], rax
0x1800e1eef  lea     rcx, [rbp+arg_0]; this
0x1800e1ef3  mov     [r14], r13d
0x1800e1ef6  mov     r8d, 0D4h; int
0x1800e1efc  mov     [rdi+38h], r13
0x1800e1f00  mov     [rdi+40h], r13d
0x1800e1f04  mov     [rdi+50h], r13d
0x1800e1f08  mov     [rdi+60h], rdi
0x1800e1f0c  mov     qword ptr [rdi+68h], 1
0x1800e1f14  mov     [rdi+70h], r13
0x1800e1f18  mov     [rbp+arg_8], r13
0x1800e1f1c  mov     [rbp+arg_18], r13
0x1800e1f20  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e1f25  mov     ebx, [r12]
0x1800e1f29  test    ebx, ebx
0x1800e1f2b  jns     loc_1800E1FE4
0x1800e1f31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1f38  test    rcx, rcx
0x1800e1f3b  jnz     short loc_1800E1F84
0x1800e1f3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e1f44  nop     dword ptr [rax+rax+00h]
0x1800e1f49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1f50  mov     rcx, rax
0x1800e1f53  test    rax, rax
0x1800e1f56  jz      short loc_1800E1F76
0x1800e1f58  mov     rax, [rax]
0x1800e1f5b  mov     edx, 7F0h
0x1800e1f60  mov     rax, [rax+8]
0x1800e1f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f69  test    eax, eax
0x1800e1f6b  jz      short loc_1800E1F76
0x1800e1f6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1f74  jmp     short loc_1800E1F84
0x1800e1f76  lea     rcx, qword_1801B97E0; this
0x1800e1f7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1f84  cmp     [rcx+8], r13b
0x1800e1f88  jz      short loc_1800E1FAF
0x1800e1f8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e1f8f  cmp     [rax+7CCh], ebx
0x1800e1f95  jz      short loc_1800E1FAF
0x1800e1f97  mov     r9d, ebx; int
0x1800e1f9a  lea     rdx, aCmfbytestreams_20; "CMFByteStreamSourceReader::CMFByteStrea"...
0x1800e1fa1  mov     r8d, 0D4h; int
0x1800e1fa7  mov     rcx, rax; this
0x1800e1faa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e1faf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1fb6  jb      loc_1800E2298
0x1800e1fbc  mov     edx, 12h
0x1800e1fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1fc8  lea     r8, WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids
0x1800e1fcf  mov     r9, rdi
0x1800e1fd2  mov     [rsp+30h+var_10], ebx
0x1800e1fd6  mov     rcx, [rcx+10h]
0x1800e1fda  call    WPP_SF_qD
0x1800e1fdf  jmp     loc_1800E2298
0x1800e1fe4  mov     rcx, rdi; this
0x1800e1fe7  call    ?UpdateByteStreamCharacteristics@CMFByteStreamSourceReader@@AEAAJXZ; CMFByteStreamSourceReader::UpdateByteStreamCharacteristics(void)
0x1800e1fec  mov     ebx, eax
0x1800e1fee  test    eax, eax
0x1800e1ff0  jns     loc_1800E208B
0x1800e1ff6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1ffd  test    rcx, rcx
0x1800e2000  jnz     short loc_1800E2049
0x1800e2002  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2009  nop     dword ptr [rax+rax+00h]
0x1800e200e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2015  mov     rcx, rax
0x1800e2018  test    rax, rax
0x1800e201b  jz      short loc_1800E203B
0x1800e201d  mov     rax, [rax]
0x1800e2020  mov     edx, 7F0h
0x1800e2025  mov     rax, [rax+8]
0x1800e2029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e202e  test    eax, eax
0x1800e2030  jz      short loc_1800E203B
0x1800e2032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2039  jmp     short loc_1800E2049
0x1800e203b  lea     rcx, qword_1801B97E0; this
0x1800e2042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2049  cmp     [rcx+8], r13b
0x1800e204d  jz      short loc_1800E2074
0x1800e204f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2054  cmp     [rax+7CCh], ebx
0x1800e205a  jz      short loc_1800E2074
0x1800e205c  mov     r9d, ebx; int
0x1800e205f  lea     rdx, aCmfbytestreams_20; "CMFByteStreamSourceReader::CMFByteStrea"...
0x1800e2066  mov     r8d, 0D9h; int
0x1800e206c  mov     rcx, rax; this
0x1800e206f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2074  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e207b  jb      loc_1800E2298
0x1800e2081  mov     edx, 13h
0x1800e2086  jmp     loc_1800E1FC1
0x1800e208b  mov     rcx, [rsi]
0x1800e208e  lea     r8, [rbp+arg_18]
0x1800e2092  lea     rdx, _GUID_64976bfa_fb61_4041_9069_8c9a5f659beb
0x1800e2099  mov     rax, [rcx]
0x1800e209c  mov     rax, [rax]
0x1800e209f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20a4  test    eax, eax
0x1800e20a6  jnz     loc_1800E215E
0x1800e20ac  mov     rcx, [rbp+arg_18]
0x1800e20b0  mov     rdx, r14
0x1800e20b3  mov     rax, [rcx]
0x1800e20b6  mov     rax, [rax+18h]
0x1800e20ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20bf  mov     ebx, eax
0x1800e20c1  test    eax, eax
0x1800e20c3  jns     loc_1800E215E
0x1800e20c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e20d0  test    rcx, rcx
0x1800e20d3  jnz     short loc_1800E211C
0x1800e20d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e20dc  nop     dword ptr [rax+rax+00h]
0x1800e20e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e20e8  mov     rcx, rax
0x1800e20eb  test    rax, rax
0x1800e20ee  jz      short loc_1800E210E
0x1800e20f0  mov     rax, [rax]
0x1800e20f3  mov     edx, 7F0h
0x1800e20f8  mov     rax, [rax+8]
0x1800e20fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2101  test    eax, eax
0x1800e2103  jz      short loc_1800E210E
0x1800e2105  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e210c  jmp     short loc_1800E211C
0x1800e210e  lea     rcx, qword_1801B97E0; this
0x1800e2115  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e211c  cmp     [rcx+8], r13b
0x1800e2120  jz      short loc_1800E2147
0x1800e2122  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2127  cmp     [rax+7CCh], ebx
0x1800e212d  jz      short loc_1800E2147
0x1800e212f  mov     r9d, ebx; int
0x1800e2132  lea     rdx, aCmfbytestreams_20; "CMFByteStreamSourceReader::CMFByteStrea"...
0x1800e2139  mov     r8d, 0DDh; int
0x1800e213f  mov     rcx, rax; this
0x1800e2142  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2147  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e214e  jb      loc_1800E2298
0x1800e2154  mov     edx, 14h
0x1800e2159  jmp     loc_1800E1FC1
0x1800e215e  mov     rcx, [rsi]
0x1800e2161  lea     r8, [rbp+arg_8]
0x1800e2165  lea     rdx, IID_IMFByteStreamBuffering
0x1800e216c  mov     rax, [rcx]
0x1800e216f  mov     rax, [rax]
0x1800e2172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2177  test    eax, eax
0x1800e2179  js      short loc_1800E2184
0x1800e217b  mov     dword ptr [rdi+1Ch], 4000h
0x1800e2182  jmp     short loc_1800E21AE
0x1800e2184  lea     r8, [rbp+arg_0]
0x1800e2188  mov     [rbp+arg_0], r13d
0x1800e218c  lea     rdx, aNetworkFilerea; "Network\\FileReadSectorSizeInKB"
0x1800e2193  xor     ecx, ecx
0x1800e2195  call    cs:__imp_MFGetConfigurationDWORD
0x1800e219c  nop     dword ptr [rax+rax+00h]
0x1800e21a1  mov     eax, [rbp+arg_0]
0x1800e21a4  test    eax, eax
0x1800e21a6  jz      short loc_1800E21AE
0x1800e21a8  shl     eax, 0Ah
0x1800e21ab  mov     [rdi+1Ch], eax
0x1800e21ae  mov     edx, [rdi+1Ch]; unsigned int
0x1800e21b1  lea     r8, [rdi+10h]; struct CByteStreamCacheReader2 **
0x1800e21b5  mov     rcx, [rsi]; struct IMFByteStream *
0x1800e21b8  call    ?CreateInstance@CByteStreamCacheReader2@@SAJPEAUIMFByteStream@@KPEAPEAV1@@Z; CByteStreamCacheReader2::CreateInstance(IMFByteStream *,ulong,CByteStreamCacheReader2 * *)
0x1800e21bd  mov     ebx, eax
0x1800e21bf  test    eax, eax
0x1800e21c1  jns     loc_1800E2258
0x1800e21c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e21ce  test    rcx, rcx
0x1800e21d1  jnz     short loc_1800E221A
0x1800e21d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e21da  nop     dword ptr [rax+rax+00h]
0x1800e21df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e21e6  mov     rcx, rax
0x1800e21e9  test    rax, rax
0x1800e21ec  jz      short loc_1800E220C
0x1800e21ee  mov     rax, [rax]
0x1800e21f1  mov     edx, 7F0h
0x1800e21f6  mov     rax, [rax+8]
0x1800e21fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e21ff  test    eax, eax
0x1800e2201  jz      short loc_1800E220C
0x1800e2203  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e220a  jmp     short loc_1800E221A
0x1800e220c  lea     rcx, qword_1801B97E0; this
0x1800e2213  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e221a  cmp     [rcx+8], r13b
0x1800e221e  jz      short loc_1800E2245
0x1800e2220  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2225  cmp     [rax+7CCh], ebx
0x1800e222b  jz      short loc_1800E2245
0x1800e222d  mov     r9d, ebx; int
0x1800e2230  lea     rdx, aCmfbytestreams_20; "CMFByteStreamSourceReader::CMFByteStrea"...
0x1800e2237  mov     r8d, 0FDh; int
0x1800e223d  mov     rcx, rax; this
0x1800e2240  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2245  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e224c  jb      short loc_1800E2298
0x1800e224e  mov     edx, 15h
0x1800e2253  jmp     loc_1800E1FC1
0x1800e2258  mov     rax, [rbp+arg_8]
0x1800e225c  test    rax, rax
0x1800e225f  jz      short loc_1800E226D
0x1800e2261  mov     rcx, rdi; this
0x1800e2264  call    ?DisallowReadAhead@CMFByteStreamSourceReader@@QEAAXXZ; CMFByteStreamSourceReader::DisallowReadAhead(void)
0x1800e2269  mov     rax, [rbp+arg_8]
0x1800e226d  cmp     cs:byte_1801BA10B, 8
0x1800e2274  jb      short loc_1800E2298
0x1800e2276  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e227d  mov     r9, rdi
0x1800e2280  mov     [rsp+30h+var_8], rax
0x1800e2285  mov     eax, [r14]
0x1800e2288  mov     [rsp+30h+var_10], eax
0x1800e228c  mov     rcx, [rcx+88h]
0x1800e2293  call    WPP_SF_qdq
0x1800e2298  lea     rcx, [rbp+arg_0]; this
0x1800e229c  mov     [r12], ebx
0x1800e22a0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800e22a5  lea     rcx, [rbp+arg_18]; void *
0x1800e22a9  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e22ae  lea     rcx, [rbp+arg_8]; void *
0x1800e22b2  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e22b7  mov     rbx, [rsp+30h+arg_10]
0x1800e22bf  mov     rax, rdi
0x1800e22c2  add     rsp, 30h
0x1800e22c6  pop     r15
0x1800e22c8  pop     r14
0x1800e22ca  pop     r13
0x1800e22cc  pop     r12
0x1800e22ce  pop     rdi
0x1800e22cf  pop     rsi
0x1800e22d0  pop     rbp
0x1800e22d1  retn
```
