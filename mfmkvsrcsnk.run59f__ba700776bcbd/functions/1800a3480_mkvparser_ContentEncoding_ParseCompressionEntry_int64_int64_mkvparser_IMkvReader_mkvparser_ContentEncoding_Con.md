# mkvparser::ContentEncoding::ParseCompressionEntry(__int64,__int64,mkvparser::IMkvReader *,mkvparser::ContentEncoding::ContentCompression *)

- ea: `0x1800a3480`
- end: `0x1800a39a2`
- name: `?ParseCompressionEntry@ContentEncoding@mkvparser@@QEAAJ_J0PEAUIMkvReader@2@PEAUContentCompression@12@@Z`
- size: `1314`
- prototype: `int(mkvparser::ContentEncoding *__hidden this, __int64, __int64, struct mkvparser::IMkvReader *, struct mkvparser::ContentEncoding::ContentCompression *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a3d74`

## callees

- `0x180001ff0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087364`
- `0x1800a3480`
- `0x1800a5fec`
- `0x1800adb74`
- `0x1800af7b0`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a35b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3652`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a36e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a381b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a38f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a35b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3652`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a36e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a381b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a38f3`

## string_xrefs

- `0x1800a34ca`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a3612`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a36af`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a3749`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a37e3`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a3878`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a38d4`: `mkvparser::ContentEncoding::ParseCompressionEntry`
- `0x1800a3955`: `mkvparser::ContentEncoding::ParseCompressionEntry`

## pseudocode

```c
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
          v41 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v25 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v38 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v35 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      BinaryData = mkvparser::ReadBinaryData(v58, v15, v16, (__int64)v20, (unsigned __int8 *)v51);
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
            v32 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v48 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
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
0x1800a3480  mov     [rsp-38h+arg_0], rbx
0x1800a3485  mov     [rsp-38h+arg_18], r9
0x1800a348a  push    rbp
0x1800a348b  push    rsi
0x1800a348c  push    rdi
0x1800a348d  push    r12
0x1800a348f  push    r13
0x1800a3491  push    r14
0x1800a3493  push    r15
0x1800a3495  mov     rbp, rsp
0x1800a3498  sub     rsp, 50h
0x1800a349c  mov     r15, [rbp+arg_20]
0x1800a34a0  lea     r13, [rdx+r8]
0x1800a34a4  xor     esi, esi
0x1800a34a6  mov     [rbp+var_18], rdx
0x1800a34aa  mov     [rbp+arg_10], sil
0x1800a34ae  mov     r14, r9
0x1800a34b1  mov     rdi, rdx
0x1800a34b4  mov     r12, rcx
0x1800a34b7  cmp     rdi, r13
0x1800a34ba  jge     loc_1800A38C9
0x1800a34c0  mov     r8d, 1414h; int
0x1800a34c6  mov     [rbp+var_20], rsi
0x1800a34ca  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a34d1  mov     qword ptr [rbp+var_10], rsi
0x1800a34d5  lea     rcx, [rbp+arg_8]; this
0x1800a34d9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a34de  lea     rax, [rbp+var_10]
0x1800a34e2  mov     r8, r13; __int64 *
0x1800a34e5  lea     r9, [rbp+var_20]; __int64
0x1800a34e9  mov     [rsp+50h+var_30], rax; unsigned __int8 *
0x1800a34ee  lea     rdx, [rbp+var_18]; struct mkvparser::IMkvReader *
0x1800a34f2  mov     rcx, r14; this
0x1800a34f5  call    ?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z; mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)
0x1800a34fa  mov     ebx, eax
0x1800a34fc  test    eax, eax
0x1800a34fe  js      loc_1800A380F
0x1800a3504  cmp     [rbp+var_20], 4254h
0x1800a350c  mov     rdi, [rbp+var_18]
0x1800a3510  mov     rsi, qword ptr [rbp+var_10]
0x1800a3514  jnz     short loc_1800A3543
0x1800a3516  lea     r9, [rbp+arg_8]; __int64
0x1800a351a  mov     [rbp+arg_8], 0
0x1800a3522  mov     r8, rsi; __int64
0x1800a3525  mov     rdx, rdi; struct mkvparser::IMkvReader *
0x1800a3528  mov     rcx, r14; this
0x1800a352b  call    ?UnserializeUInt@mkvparser@@YAJPEAUIMkvReader@1@_J1AEA_J@Z; mkvparser::UnserializeUInt(mkvparser::IMkvReader *,__int64,__int64,__int64 &)
0x1800a3530  mov     ebx, eax
0x1800a3532  test    eax, eax
0x1800a3534  js      short loc_1800A35A9
0x1800a3536  mov     rax, [rbp+arg_8]
0x1800a353a  mov     [r15], rax
0x1800a353d  mov     [rbp+arg_10], 1
0x1800a3541  jmp     short loc_1800A3592
0x1800a3543  cmp     [rbp+var_20], 4255h
0x1800a354b  jnz     short loc_1800A3592
0x1800a354d  test    rsi, rsi
0x1800a3550  jle     loc_1800A3775
0x1800a3556  mov     rdx, rsi
0x1800a3559  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x1800a355e  mov     r14, rax
0x1800a3561  test    rax, rax
0x1800a3564  jz      loc_1800A36DB
0x1800a356a  mov     rcx, [rbp+arg_18]; this
0x1800a356e  mov     r9, rax; __int64
0x1800a3571  mov     r8, rsi; __int64
0x1800a3574  mov     rdx, rdi; struct mkvparser::IMkvReader *
0x1800a3577  call    ?ReadBinaryData@mkvparser@@YAJPEAUIMkvReader@1@_J1PEAE@Z; mkvparser::ReadBinaryData(mkvparser::IMkvReader *,__int64,__int64,uchar *)
0x1800a357c  mov     ebx, eax
0x1800a357e  test    eax, eax
0x1800a3580  js      loc_1800A363E
0x1800a3586  mov     [r15+8], r14
0x1800a358a  mov     r14, [rbp+arg_18]
0x1800a358e  mov     [r15+10h], rsi
0x1800a3592  add     rdi, rsi
0x1800a3595  lea     rcx, [rbp+arg_8]; this
0x1800a3599  mov     [rbp+var_18], rdi
0x1800a359d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a35a2  xor     esi, esi
0x1800a35a4  jmp     loc_1800A34B7
0x1800a35a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a35b0  test    rcx, rcx
0x1800a35b3  jnz     short loc_1800A35FC
0x1800a35b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a35bc  nop     dword ptr [rax+rax+00h]
0x1800a35c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a35c8  mov     rcx, rax
0x1800a35cb  test    rax, rax
0x1800a35ce  jz      short loc_1800A35EE
0x1800a35d0  mov     rax, [rax]
0x1800a35d3  mov     edx, 7F0h
0x1800a35d8  mov     rax, [rax+8]
0x1800a35dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a35e1  test    eax, eax
0x1800a35e3  jz      short loc_1800A35EE
0x1800a35e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a35ec  jmp     short loc_1800A35FC
0x1800a35ee  lea     rcx, qword_1800DBF70; this
0x1800a35f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a35fc  cmp     byte ptr [rcx+8], 0
0x1800a3600  jz      short loc_1800A3627
0x1800a3602  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3607  cmp     [rax+7CCh], ebx
0x1800a360d  jz      short loc_1800A3627
0x1800a360f  mov     r9d, ebx; int
0x1800a3612  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a3619  mov     r8d, 1418h; int
0x1800a361f  mov     rcx, rax; this
0x1800a3622  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3627  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a362e  jb      loc_1800A38B9
0x1800a3634  mov     edx, 1B7h
0x1800a3639  jmp     loc_1800A389B
0x1800a363e  mov     rcx, r14; Block
0x1800a3641  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a3646  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a364d  test    rcx, rcx
0x1800a3650  jnz     short loc_1800A3699
0x1800a3652  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3659  nop     dword ptr [rax+rax+00h]
0x1800a365e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3665  mov     rcx, rax
0x1800a3668  test    rax, rax
0x1800a366b  jz      short loc_1800A368B
0x1800a366d  mov     rax, [rax]
0x1800a3670  mov     edx, 7F0h
0x1800a3675  mov     rax, [rax+8]
0x1800a3679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a367e  test    eax, eax
0x1800a3680  jz      short loc_1800A368B
0x1800a3682  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3689  jmp     short loc_1800A3699
0x1800a368b  lea     rcx, qword_1800DBF70; this
0x1800a3692  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3699  cmp     byte ptr [rcx+8], 0
0x1800a369d  jz      short loc_1800A36C4
0x1800a369f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a36a4  cmp     [rax+7CCh], ebx
0x1800a36aa  jz      short loc_1800A36C4
0x1800a36ac  mov     r9d, ebx; int
0x1800a36af  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a36b6  mov     r8d, 1429h; int
0x1800a36bc  mov     rcx, rax; this
0x1800a36bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a36c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a36cb  jb      loc_1800A38B9
0x1800a36d1  mov     edx, 1BAh
0x1800a36d6  jmp     loc_1800A389B
0x1800a36db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a36e2  test    rcx, rcx
0x1800a36e5  jnz     short loc_1800A372E
0x1800a36e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a36ee  nop     dword ptr [rax+rax+00h]
0x1800a36f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a36fa  mov     rcx, rax
0x1800a36fd  test    rax, rax
0x1800a3700  jz      short loc_1800A3720
0x1800a3702  mov     rax, [rax]
0x1800a3705  mov     edx, 7F0h
0x1800a370a  mov     rax, [rax+8]
0x1800a370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3713  test    eax, eax
0x1800a3715  jz      short loc_1800A3720
0x1800a3717  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a371e  jmp     short loc_1800A372E
0x1800a3720  lea     rcx, qword_1800DBF70; this
0x1800a3727  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a372e  cmp     byte ptr [rcx+8], 0
0x1800a3732  mov     ebx, 8007000Eh
0x1800a3737  jz      short loc_1800A375E
0x1800a3739  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a373e  cmp     [rax+7CCh], ebx
0x1800a3744  jz      short loc_1800A375E
0x1800a3746  mov     r9d, ebx; int
0x1800a3749  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a3750  mov     r8d, 1424h; int
0x1800a3756  mov     rcx, rax; this
0x1800a3759  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a375e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3765  jb      loc_1800A38B9
0x1800a376b  mov     edx, 1B9h
0x1800a3770  jmp     loc_1800A389B
0x1800a3775  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a377c  test    rcx, rcx
0x1800a377f  jnz     short loc_1800A37C8
0x1800a3781  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3788  nop     dword ptr [rax+rax+00h]
0x1800a378d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3794  mov     rcx, rax
0x1800a3797  test    rax, rax
0x1800a379a  jz      short loc_1800A37BA
0x1800a379c  mov     rax, [rax]
0x1800a379f  mov     edx, 7F0h
0x1800a37a4  mov     rax, [rax+8]
0x1800a37a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a37ad  test    eax, eax
0x1800a37af  jz      short loc_1800A37BA
0x1800a37b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a37b8  jmp     short loc_1800A37C8
0x1800a37ba  lea     rcx, qword_1800DBF70; this
0x1800a37c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a37c8  cmp     byte ptr [rcx+8], 0
0x1800a37cc  mov     ebx, 0C00D36BEh
0x1800a37d1  jz      short loc_1800A37F8
0x1800a37d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a37d8  cmp     [rax+7CCh], ebx
0x1800a37de  jz      short loc_1800A37F8
0x1800a37e0  mov     r9d, ebx; int
0x1800a37e3  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a37ea  mov     r8d, 141Fh; int
0x1800a37f0  mov     rcx, rax; this
0x1800a37f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a37f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a37ff  jb      loc_1800A38B9
0x1800a3805  mov     edx, 1B8h
0x1800a380a  jmp     loc_1800A389B
0x1800a380f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3816  test    rcx, rcx
0x1800a3819  jnz     short loc_1800A3862
0x1800a381b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3822  nop     dword ptr [rax+rax+00h]
0x1800a3827  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a382e  mov     rcx, rax
0x1800a3831  test    rax, rax
0x1800a3834  jz      short loc_1800A3854
0x1800a3836  mov     rax, [rax]
0x1800a3839  mov     edx, 7F0h
0x1800a383e  mov     rax, [rax+8]
0x1800a3842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3847  test    eax, eax
0x1800a3849  jz      short loc_1800A3854
0x1800a384b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3852  jmp     short loc_1800A3862
0x1800a3854  lea     rcx, qword_1800DBF70; this
0x1800a385b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3862  cmp     [rcx+8], sil
0x1800a3866  jz      short loc_1800A388D
0x1800a3868  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a386d  cmp     [rax+7CCh], ebx
0x1800a3873  jz      short loc_1800A388D
0x1800a3875  mov     r9d, ebx; int
0x1800a3878  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a387f  mov     r8d, 1414h; int
0x1800a3885  mov     rcx, rax; this
0x1800a3888  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a388d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3894  jb      short loc_1800A38B9
0x1800a3896  mov     edx, 1B6h
0x1800a389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a38a2  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a38a9  mov     r9, r12
0x1800a38ac  mov     dword ptr [rsp+50h+var_30], ebx
0x1800a38b0  mov     rcx, [rcx+10h]
0x1800a38b4  call    WPP_SF_qD
0x1800a38b9  lea     rcx, [rbp+arg_8]; this
0x1800a38bd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a38c2  mov     eax, ebx
0x1800a38c4  jmp     loc_1800A3989
0x1800a38c9  jz      loc_1800A397E
0x1800a38cf  mov     edi, 1435h
0x1800a38d4  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a38db  mov     r8d, edi; int
0x1800a38de  lea     rcx, [rbp+arg_8]; this
0x1800a38e2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a38e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a38ee  test    rcx, rcx
0x1800a38f1  jnz     short loc_1800A393A
0x1800a38f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a38fa  nop     dword ptr [rax+rax+00h]
0x1800a38ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3906  mov     rcx, rax
0x1800a3909  test    rax, rax
0x1800a390c  jz      short loc_1800A392C
0x1800a390e  mov     rax, [rax]
0x1800a3911  mov     edx, 7F0h
0x1800a3916  mov     rax, [rax+8]
0x1800a391a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a391f  test    eax, eax
0x1800a3921  jz      short loc_1800A392C
0x1800a3923  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a392a  jmp     short loc_1800A393A
0x1800a392c  lea     rcx, qword_1800DBF70; this
0x1800a3933  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a393a  mov     ebx, 0C00D36BEh
0x1800a393f  cmp     [rcx+8], sil
0x1800a3943  jz      short loc_1800A3967
0x1800a3945  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a394a  cmp     [rax+7CCh], ebx
0x1800a3950  jz      short loc_1800A3967
0x1800a3952  mov     r9d, ebx; int
0x1800a3955  lea     rdx, aMkvparserConte_1; "mkvparser::ContentEncoding::ParseCompre"...
0x1800a395c  mov     r8d, edi; int
0x1800a395f  mov     rcx, rax; this
0x1800a3962  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3967  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a396e  jb      loc_1800A38B9
0x1800a3974  mov     edx, 1BBh
0x1800a3979  jmp     loc_1800A389B
0x1800a397e  cmp     [rbp+arg_10], sil
0x1800a3982  jnz     short loc_1800A3987
  ... truncated ...
```
