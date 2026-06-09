# mkvparser::ContentEncoding::ParseCompressionEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentCompression *)

- ea: `0x18009ecd4`
- end: `0x18009f1d1`
- name: `?ParseCompressionEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentCompression@12@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(mkvparser::ContentEncoding *this, struct mkvparser::IMkvReader *, __int64, struct mkvparser::IMkvReader *, struct mkvparser::ContentEncoding::ContentCompression *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009f58c`

## callees

- `0x180001fd0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008385c`
- `0x18009ecd4`
- `0x1800a1710`
- `0x1800a8f04`
- `0x1800aaa7c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ee09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eea0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ef2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009efc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f057`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ee09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eea0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ef2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009efc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f057`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f129`

## string_xrefs

- `0x18009ed1e`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009ee60`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009eef7`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009ef8b`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009f01f`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009f0ae`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009f10a`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x18009f185`: `mkvparser::ContentEncoding::ParseCompressionEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall mkvparser::ContentEncoding::ParseCompressionEntry(
        mkvparser::ContentEncoding *this,
        struct mkvparser::IMkvReader *a2,
        __int64 a3,
        struct mkvparser::IMkvReader *a4,
        struct mkvparser::ContentEncoding::ContentCompression *a5)
{
  struct mkvparser::ContentEncoding::ContentCompression *v5; // r15
  __int64 *v6; // r13
  struct mkvparser::IMkvReader *v7; // r14
  struct mkvparser::IMkvReader *v8; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int BinaryData; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  struct mkvparser::IMkvReader *v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  void *v24; // r14
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // [rsp+20h] [rbp-30h]
  __int64 *v52; // [rsp+28h] [rbp-28h]
  __int64 v53; // [rsp+30h] [rbp-20h] BYREF
  struct mkvparser::IMkvReader *v54; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v55[8]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v56; // [rsp+98h] [rbp+48h] BYREF
  char v57; // [rsp+A0h] [rbp+50h]
  mkvparser *v58; // [rsp+A8h] [rbp+58h]

  v58 = a4;
  v5 = a5;
  v6 = (__int64 *)((char *)a2 + a3);
  v54 = a2;
  v57 = 0;
  v7 = a4;
  v8 = a2;
  while ( (__int64)v8 < (__int64)v6 )
  {
    v53 = 0;
    *(_QWORD *)v55 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v56,
      "mkvparser::ContentEncoding::ParseCompressionEntry",
      5140);
    BinaryData = mkvparser::ParseElementHeader(
                   v7,
                   (struct mkvparser::IMkvReader *)&v54,
                   v6,
                   (__int64)&v53,
                   (__int64 *)v55,
                   v52);
    if ( BinaryData < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v13, v14);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != BinaryData )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "mkvparser::ContentEncoding::ParseCompressionEntry",
            5140,
            BinaryData);
      }
      if ( !g_wppLevels )
        goto LABEL_64;
      v28 = 438;
      goto LABEL_63;
    }
    v15 = v54;
    v16 = *(_QWORD *)v55;
    if ( v53 == 16980 )
    {
      v56 = 0;
      BinaryData = mkvparser::UnserializeUInt(v7, v54, *(__int64 *)v55, (__int64)&v56, v51);
      if ( BinaryData < 0 )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != BinaryData )
            CallStackContext::TraceFailure(v27, "mkvparser::ContentEncoding::ParseCompressionEntry", 5144, BinaryData);
        }
        if ( g_wppLevels )
        {
          v28 = 439;
          goto LABEL_63;
        }
        goto LABEL_64;
      }
      *(_QWORD *)v5 = v56;
      v57 = 1;
    }
    else if ( v53 == 16981 )
    {
      if ( *(__int64 *)v55 <= 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v13, v14);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        BinaryData = -1072875842;
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v40, "mkvparser::ContentEncoding::ParseCompressionEntry", 5151, -1072875842);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v28 = 440;
        goto LABEL_63;
      }
      v20 = mkvparser::SafeArrayAlloc<char>(v11, *(unsigned __int64 *)v55);
      v24 = v20;
      if ( !v20 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        BinaryData = -2147024882;
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v37, "mkvparser::ContentEncoding::ParseCompressionEntry", 5156, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v28 = 441;
        goto LABEL_63;
      }
      BinaryData = mkvparser::ReadBinaryData(v58, v15, v16, (__int64)v20);
      if ( BinaryData < 0 )
      {
        operator delete(v24);
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != BinaryData )
            CallStackContext::TraceFailure(v34, "mkvparser::ContentEncoding::ParseCompressionEntry", 5161, BinaryData);
        }
        if ( g_wppLevels )
        {
          v28 = 442;
          goto LABEL_63;
        }
LABEL_64:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v56);
        return (unsigned int)BinaryData;
      }
      *((_QWORD *)v5 + 1) = v24;
      v7 = v58;
      *((_QWORD *)v5 + 2) = v16;
    }
    v8 = (struct mkvparser::IMkvReader *)((char *)v15 + v16);
    v54 = v8;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v56);
  }
  if ( v8 != (struct mkvparser::IMkvReader *)v6 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v56,
      "mkvparser::ContentEncoding::ParseCompressionEntry",
      5173);
    v48 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    BinaryData = -1072875842;
    if ( *((_BYTE *)v48 + 8) )
    {
      v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
      if ( *((_DWORD *)v50 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v50, "mkvparser::ContentEncoding::ParseCompressionEntry", 5173, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_64;
    v28 = 443;
LABEL_63:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
      this,
      BinaryData);
    goto LABEL_64;
  }
  if ( !v57 )
    *(_QWORD *)v5 = 0;
  return 0;
}

```

## disassembly

```asm
0x18009ecd4  mov     [rsp-38h+arg_0], rbx
0x18009ecd9  mov     [rsp-38h+arg_18], r9
0x18009ecde  push    rbp
0x18009ecdf  push    rsi
0x18009ece0  push    rdi
0x18009ece1  push    r12
0x18009ece3  push    r13
0x18009ece5  push    r14
0x18009ece7  push    r15
0x18009ece9  mov     rbp, rsp
0x18009ecec  sub     rsp, 50h
0x18009ecf0  mov     r15, [rbp+arg_20]
0x18009ecf4  lea     r13, [rdx+r8]
0x18009ecf8  xor     esi, esi
0x18009ecfa  mov     [rbp+var_18], rdx
0x18009ecfe  mov     [rbp+arg_10], sil
0x18009ed02  mov     r14, r9
0x18009ed05  mov     rdi, rdx
0x18009ed08  mov     r12, rcx
0x18009ed0b  cmp     rdi, r13
0x18009ed0e  jge     loc_18009F0FF
0x18009ed14  mov     r8d, 1414h; int
0x18009ed1a  mov     [rbp+var_20], rsi
0x18009ed1e  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009ed25  mov     qword ptr [rbp+var_10], rsi
0x18009ed29  lea     rcx, [rbp+arg_8]; this
0x18009ed2d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009ed32  lea     rax, [rbp+var_10]
0x18009ed36  mov     r8, r13; __int64 *
0x18009ed39  lea     r9, [rbp+var_20]; __int64
0x18009ed3d  mov     [rsp+50h+var_30], rax; unsigned __int8 *
0x18009ed42  lea     rdx, [rbp+var_18]; struct mkvparser::IMkvReader *
0x18009ed46  mov     rcx, r14; this
0x18009ed49  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x18009ed4e  mov     ebx, eax
0x18009ed50  test    eax, eax
0x18009ed52  js      loc_18009F04B
0x18009ed58  cmp     [rbp+var_20], 4254h
0x18009ed60  mov     rdi, [rbp+var_18]
0x18009ed64  mov     rsi, qword ptr [rbp+var_10]
0x18009ed68  jnz     short loc_18009ED97
0x18009ed6a  lea     r9, [rbp+arg_8]; __int64
0x18009ed6e  mov     [rbp+arg_8], 0
0x18009ed76  mov     r8, rsi; __int64
0x18009ed79  mov     rdx, rdi; struct mkvparser::IMkvReader *
0x18009ed7c  mov     rcx, r14; this
0x18009ed7f  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x18009ed84  mov     ebx, eax
0x18009ed86  test    eax, eax
0x18009ed88  js      short loc_18009EDFD
0x18009ed8a  mov     rax, [rbp+arg_8]
0x18009ed8e  mov     [r15], rax
0x18009ed91  mov     [rbp+arg_10], 1
0x18009ed95  jmp     short loc_18009EDE6
0x18009ed97  cmp     [rbp+var_20], 4255h
0x18009ed9f  jnz     short loc_18009EDE6
0x18009eda1  test    rsi, rsi
0x18009eda4  jle     loc_18009EFB7
0x18009edaa  mov     rdx, rsi
0x18009edad  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x18009edb2  mov     r14, rax
0x18009edb5  test    rax, rax
0x18009edb8  jz      loc_18009EF23
0x18009edbe  mov     rcx, [rbp+arg_18]; this
0x18009edc2  mov     r9, rax; __int64
0x18009edc5  mov     r8, rsi; __int64
0x18009edc8  mov     rdx, rdi; struct mkvparser::IMkvReader *
0x18009edcb  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x18009edd0  mov     ebx, eax
0x18009edd2  test    eax, eax
0x18009edd4  js      loc_18009EE8C
0x18009edda  mov     [r15+8], r14
0x18009edde  mov     r14, [rbp+arg_18]
0x18009ede2  mov     [r15+10h], rsi
0x18009ede6  add     rdi, rsi
0x18009ede9  lea     rcx, [rbp+arg_8]; this
0x18009eded  mov     [rbp+var_18], rdi
0x18009edf1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009edf6  xor     esi, esi
0x18009edf8  jmp     loc_18009ED0B
0x18009edfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ee04  test    rcx, rcx
0x18009ee07  jnz     short loc_18009EE4A
0x18009ee09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ee0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ee16  mov     rcx, rax
0x18009ee19  test    rax, rax
0x18009ee1c  jz      short loc_18009EE3C
0x18009ee1e  mov     rax, [rax]
0x18009ee21  mov     edx, 7F0h
0x18009ee26  mov     rax, [rax+8]
0x18009ee2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee2f  test    eax, eax
0x18009ee31  jz      short loc_18009EE3C
0x18009ee33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ee3a  jmp     short loc_18009EE4A
0x18009ee3c  lea     rcx, qword_1800D6F70; this
0x18009ee43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ee4a  cmp     byte ptr [rcx+8], 0
0x18009ee4e  jz      short loc_18009EE75
0x18009ee50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ee55  cmp     [rax+7CCh], ebx
0x18009ee5b  jz      short loc_18009EE75
0x18009ee5d  mov     r9d, ebx; int
0x18009ee60  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009ee67  mov     r8d, 1418h; int
0x18009ee6d  mov     rcx, rax; this
0x18009ee70  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ee75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ee7c  jb      loc_18009F0EF
0x18009ee82  mov     edx, 1B7h
0x18009ee87  jmp     loc_18009F0D1
0x18009ee8c  mov     rcx, r14; Block
0x18009ee8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009ee94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ee9b  test    rcx, rcx
0x18009ee9e  jnz     short loc_18009EEE1
0x18009eea0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009eea6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009eead  mov     rcx, rax
0x18009eeb0  test    rax, rax
0x18009eeb3  jz      short loc_18009EED3
0x18009eeb5  mov     rax, [rax]
0x18009eeb8  mov     edx, 7F0h
0x18009eebd  mov     rax, [rax+8]
0x18009eec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eec6  test    eax, eax
0x18009eec8  jz      short loc_18009EED3
0x18009eeca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009eed1  jmp     short loc_18009EEE1
0x18009eed3  lea     rcx, qword_1800D6F70; this
0x18009eeda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009eee1  cmp     byte ptr [rcx+8], 0
0x18009eee5  jz      short loc_18009EF0C
0x18009eee7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009eeec  cmp     [rax+7CCh], ebx
0x18009eef2  jz      short loc_18009EF0C
0x18009eef4  mov     r9d, ebx; int
0x18009eef7  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009eefe  mov     r8d, 1429h; int
0x18009ef04  mov     rcx, rax; this
0x18009ef07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ef0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ef13  jb      loc_18009F0EF
0x18009ef19  mov     edx, 1BAh
0x18009ef1e  jmp     loc_18009F0D1
0x18009ef23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ef2a  test    rcx, rcx
0x18009ef2d  jnz     short loc_18009EF70
0x18009ef2f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ef35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ef3c  mov     rcx, rax
0x18009ef3f  test    rax, rax
0x18009ef42  jz      short loc_18009EF62
0x18009ef44  mov     rax, [rax]
0x18009ef47  mov     edx, 7F0h
0x18009ef4c  mov     rax, [rax+8]
0x18009ef50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ef55  test    eax, eax
0x18009ef57  jz      short loc_18009EF62
0x18009ef59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ef60  jmp     short loc_18009EF70
0x18009ef62  lea     rcx, qword_1800D6F70; this
0x18009ef69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ef70  cmp     byte ptr [rcx+8], 0
0x18009ef74  mov     ebx, 8007000Eh
0x18009ef79  jz      short loc_18009EFA0
0x18009ef7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ef80  cmp     [rax+7CCh], ebx
0x18009ef86  jz      short loc_18009EFA0
0x18009ef88  mov     r9d, ebx; int
0x18009ef8b  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009ef92  mov     r8d, 1424h; int
0x18009ef98  mov     rcx, rax; this
0x18009ef9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009efa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009efa7  jb      loc_18009F0EF
0x18009efad  mov     edx, 1B9h
0x18009efb2  jmp     loc_18009F0D1
0x18009efb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009efbe  test    rcx, rcx
0x18009efc1  jnz     short loc_18009F004
0x18009efc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009efc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009efd0  mov     rcx, rax
0x18009efd3  test    rax, rax
0x18009efd6  jz      short loc_18009EFF6
0x18009efd8  mov     rax, [rax]
0x18009efdb  mov     edx, 7F0h
0x18009efe0  mov     rax, [rax+8]
0x18009efe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009efe9  test    eax, eax
0x18009efeb  jz      short loc_18009EFF6
0x18009efed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009eff4  jmp     short loc_18009F004
0x18009eff6  lea     rcx, qword_1800D6F70; this
0x18009effd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f004  cmp     byte ptr [rcx+8], 0
0x18009f008  mov     ebx, 0C00D36BEh
0x18009f00d  jz      short loc_18009F034
0x18009f00f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f014  cmp     [rax+7CCh], ebx
0x18009f01a  jz      short loc_18009F034
0x18009f01c  mov     r9d, ebx; int
0x18009f01f  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009f026  mov     r8d, 141Fh; int
0x18009f02c  mov     rcx, rax; this
0x18009f02f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f034  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f03b  jb      loc_18009F0EF
0x18009f041  mov     edx, 1B8h
0x18009f046  jmp     loc_18009F0D1
0x18009f04b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f052  test    rcx, rcx
0x18009f055  jnz     short loc_18009F098
0x18009f057  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f05d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f064  mov     rcx, rax
0x18009f067  test    rax, rax
0x18009f06a  jz      short loc_18009F08A
0x18009f06c  mov     rax, [rax]
0x18009f06f  mov     edx, 7F0h
0x18009f074  mov     rax, [rax+8]
0x18009f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f07d  test    eax, eax
0x18009f07f  jz      short loc_18009F08A
0x18009f081  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f088  jmp     short loc_18009F098
0x18009f08a  lea     rcx, qword_1800D6F70; this
0x18009f091  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f098  cmp     [rcx+8], sil
0x18009f09c  jz      short loc_18009F0C3
0x18009f09e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f0a3  cmp     [rax+7CCh], ebx
0x18009f0a9  jz      short loc_18009F0C3
0x18009f0ab  mov     r9d, ebx; int
0x18009f0ae  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009f0b5  mov     r8d, 1414h; int
0x18009f0bb  mov     rcx, rax; this
0x18009f0be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f0c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f0ca  jb      short loc_18009F0EF
0x18009f0cc  mov     edx, 1B6h
0x18009f0d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f0d8  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x18009f0df  mov     r9, r12
0x18009f0e2  mov     dword ptr [rsp+50h+var_30], ebx
0x18009f0e6  mov     rcx, [rcx+10h]
0x18009f0ea  call    WPP_SF_qD
0x18009f0ef  lea     rcx, [rbp+arg_8]; this
0x18009f0f3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009f0f8  mov     eax, ebx
0x18009f0fa  jmp     loc_18009F1B9
0x18009f0ff  jz      loc_18009F1AE
0x18009f105  mov     edi, 1435h
0x18009f10a  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009f111  mov     r8d, edi; int
0x18009f114  lea     rcx, [rbp+arg_8]; this
0x18009f118  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f11d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f124  test    rcx, rcx
0x18009f127  jnz     short loc_18009F16A
0x18009f129  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f12f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f136  mov     rcx, rax
0x18009f139  test    rax, rax
0x18009f13c  jz      short loc_18009F15C
0x18009f13e  mov     rax, [rax]
0x18009f141  mov     edx, 7F0h
0x18009f146  mov     rax, [rax+8]
0x18009f14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f14f  test    eax, eax
0x18009f151  jz      short loc_18009F15C
0x18009f153  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f15a  jmp     short loc_18009F16A
0x18009f15c  lea     rcx, qword_1800D6F70; this
0x18009f163  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f16a  mov     ebx, 0C00D36BEh
0x18009f16f  cmp     [rcx+8], sil
0x18009f173  jz      short loc_18009F197
0x18009f175  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f17a  cmp     [rax+7CCh], ebx
0x18009f180  jz      short loc_18009F197
0x18009f182  mov     r9d, ebx; int
0x18009f185  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x18009f18c  mov     r8d, edi; int
0x18009f18f  mov     rcx, rax; this
0x18009f192  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f197  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f19e  jb      loc_18009F0EF
0x18009f1a4  mov     edx, 1BBh
0x18009f1a9  jmp     loc_18009F0D1
0x18009f1ae  cmp     [rbp+arg_10], sil
0x18009f1b2  jnz     short loc_18009F1B7
0x18009f1b4  mov     [r15], rsi
0x18009f1b7  xor     eax, eax
0x18009f1b9  mov     rbx, [rsp+50h+arg_0]
0x18009f1c1  add     rsp, 50h
0x18009f1c5  pop     r15
0x18009f1c7  pop     r14
  ... truncated ...
```
