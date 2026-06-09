# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x180037a1c`
- end: `0x180037f66`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1354`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800310e0`
- `0x180035148`

## callees

- `0x18001ef50`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180037a1c`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180037e62`
- `OLEAUT32!__imp_SysAllocString` at `0x180037e62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e8a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037c45`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037c45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037a9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037b8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037d17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037de1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037eb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037a9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037b8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037d17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037de1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037eb3`

## string_xrefs

- `0x180037a73`: `CMFPropVariant::CreateString`
- `0x180037b31`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 *v8; // rcx
  signed int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  signed int LastError; // eax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  BSTR v29; // rax
  signed int v30; // eax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v37; // [rsp+60h] [rbp+30h]
  char v38; // [rsp+68h] [rbp+38h] BYREF

  *(_WORD *)this = a2;
  if ( a2 == 30 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  else
  {
    if ( a2 != 31 && a2 != 8 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1854);
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v37 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v37);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1861);
    v14 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v14 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v17, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 124;
LABEL_82:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v9);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
      return (unsigned int)v9;
    }
    *v14 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v9 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v37 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v9 >= 0 )
        {
          v9 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v24 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v24, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_83;
          v12 = 126;
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v9 )
              CallStackContext::TraceFailure(v22, "CMFPropVariant::CreateString", 1881, v9);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_83;
          v12 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v9;
    }
    if ( a2 == 31 )
    {
      v9 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v37 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1888);
      if ( v9 >= 0 )
        goto LABEL_83;
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CMFPropVariant::CreateString", 1888, v9);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v12 = 127;
      goto LABEL_82;
    }
  }
  v9 = 0;
  v29 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v29;
  if ( !v29 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1895);
    v30 = GetLastError();
    v9 = v30;
    if ( v30 > 0 )
      v9 = (unsigned __int16)v30 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_83;
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != v9 )
        CallStackContext::TraceFailure(v34, "CMFPropVariant::CreateString", 1895, v9);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v12 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037a1c  mov     [rsp-28h+arg_10], rbx
0x180037a21  mov     [rsp-28h+arg_18], rsi
0x180037a26  push    rbp
0x180037a27  push    rdi
0x180037a28  push    r12
0x180037a2a  push    r13
0x180037a2c  push    r15
0x180037a2e  mov     rbp, rsp
0x180037a31  sub     rsp, 30h
0x180037a35  mov     [rcx], dx
0x180037a38  mov     r12, r8
0x180037a3b  movzx   ebx, dx
0x180037a3e  mov     r15, rcx
0x180037a41  mov     eax, 1Fh
0x180037a46  cmp     dx, 1Eh
0x180037a4a  jnz     short loc_180037A60
0x180037a4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180037a50  xor     edi, edi
0x180037a52  inc     rdx
0x180037a55  cmp     [r8+rdx], dil
0x180037a59  jnz     short loc_180037A52
0x180037a5b  jmp     loc_180037B2E
0x180037a60  cmp     bx, ax
0x180037a63  jz      loc_180037B1E
0x180037a69  cmp     bx, 8
0x180037a6d  jz      loc_180037B1E
0x180037a73  lea     rsi, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x180037a7a  mov     r8d, 73Eh; int
0x180037a80  mov     rdx, rsi; char *
0x180037a83  lea     rcx, [rbp+arg_8]; this
0x180037a87  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037a93  xor     edi, edi
0x180037a95  mov     ebx, 80070057h
0x180037a9a  test    rcx, rcx
0x180037a9d  jnz     short loc_180037AE0
0x180037a9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037aa5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037aac  mov     rcx, rax
0x180037aaf  test    rax, rax
0x180037ab2  jz      short loc_180037AD2
0x180037ab4  mov     rax, [rax]
0x180037ab7  mov     edx, 7F0h
0x180037abc  mov     rax, [rax+8]
0x180037ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ac5  test    eax, eax
0x180037ac7  jz      short loc_180037AD2
0x180037ac9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ad0  jmp     short loc_180037AE0
0x180037ad2  lea     rcx, qword_18006EB20; this
0x180037ad9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ae0  cmp     [rcx+8], dil
0x180037ae4  jz      short loc_180037B07
0x180037ae6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037aeb  cmp     [rax+7CCh], ebx
0x180037af1  jz      short loc_180037B07
0x180037af3  mov     r9d, ebx; int
0x180037af6  mov     r8d, 73Eh; int
0x180037afc  mov     rdx, rsi; char *
0x180037aff  mov     rcx, rax; this
0x180037b02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037b07  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037b0c  cmp     al, 1
0x180037b0e  jb      loc_180037F44
0x180037b14  mov     edx, 7Bh ; '{'
0x180037b19  jmp     loc_180037F26
0x180037b1e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180037b22  xor     edi, edi
0x180037b24  inc     rdx
0x180037b27  cmp     [r8+rdx*2], di
0x180037b2c  jnz     short loc_180037B24
0x180037b2e  lea     eax, [rbx-1Eh]
0x180037b31  lea     rsi, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x180037b38  cmp     ax, 1
0x180037b3c  ja      loc_180037E5D
0x180037b42  lea     edx, ds:2[rdx*2]
0x180037b49  mov     ecx, edx; cb
0x180037b4b  mov     [rbp+arg_0], edx
0x180037b4e  mov     r13d, edx
0x180037b51  call    cs:__imp_CoTaskMemAlloc
0x180037b57  mov     r8d, 745h; int
0x180037b5d  lea     rcx, [rbp+arg_8]; this
0x180037b61  mov     rdx, rsi; char *
0x180037b64  mov     [r15+8], rax
0x180037b68  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037b6d  mov     rax, [r15+8]
0x180037b71  test    rax, rax
0x180037b74  jnz     loc_180037C0A
0x180037b7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b81  mov     ebx, 8007000Eh
0x180037b86  test    rcx, rcx
0x180037b89  jnz     short loc_180037BCC
0x180037b8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037b91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b98  mov     rcx, rax
0x180037b9b  test    rax, rax
0x180037b9e  jz      short loc_180037BBE
0x180037ba0  mov     rax, [rax]
0x180037ba3  mov     edx, 7F0h
0x180037ba8  mov     rax, [rax+8]
0x180037bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bb1  test    eax, eax
0x180037bb3  jz      short loc_180037BBE
0x180037bb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037bbc  jmp     short loc_180037BCC
0x180037bbe  lea     rcx, qword_18006EB20; this
0x180037bc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037bcc  cmp     [rcx+8], dil
0x180037bd0  jz      short loc_180037BF3
0x180037bd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037bd7  cmp     [rax+7CCh], ebx
0x180037bdd  jz      short loc_180037BF3
0x180037bdf  mov     r9d, ebx; int
0x180037be2  mov     r8d, 745h; int
0x180037be8  mov     rdx, rsi; char *
0x180037beb  mov     rcx, rax; this
0x180037bee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037bf3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037bf8  cmp     al, 1
0x180037bfa  jb      loc_180037F44
0x180037c00  mov     edx, 7Ch ; '|'
0x180037c05  jmp     loc_180037F26
0x180037c0a  lea     rcx, [rbp+arg_8]; this
0x180037c0e  mov     [rax], di
0x180037c11  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180037c16  cmp     bx, 1Eh
0x180037c1a  jnz     loc_180037D96
0x180037c20  mov     eax, [rbp+arg_0]
0x180037c23  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180037c27  shr     eax, 1
0x180037c29  mov     r8, r12; lpMultiByteStr
0x180037c2c  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x180037c30  xor     edx, edx; dwFlags
0x180037c32  mov     rax, [r15+8]
0x180037c36  xor     ecx, ecx; CodePage
0x180037c38  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180037c3d  mov     ebx, edi
0x180037c3f  mov     word ptr [r15], 1Fh
0x180037c45  call    cs:__imp_MultiByteToWideChar
0x180037c4b  test    eax, eax
0x180037c4d  jnz     loc_180037F4D
0x180037c53  mov     r12d, 759h
0x180037c59  lea     rcx, [rbp+arg_8]; this
0x180037c5d  mov     r8d, r12d; int
0x180037c60  mov     rdx, rsi; char *
0x180037c63  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037c68  call    cs:__imp_GetLastError
0x180037c6e  mov     ebx, eax
0x180037c70  test    eax, eax
0x180037c72  jle     short loc_180037C7D
0x180037c74  movzx   ebx, ax
0x180037c77  or      ebx, 80070000h
0x180037c7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c84  test    ebx, ebx
0x180037c86  jns     loc_180037D0D
0x180037c8c  test    rcx, rcx
0x180037c8f  jnz     short loc_180037CD2
0x180037c91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037c97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c9e  mov     rcx, rax
0x180037ca1  test    rax, rax
0x180037ca4  jz      short loc_180037CC4
0x180037ca6  mov     rax, [rax]
0x180037ca9  mov     edx, 7F0h
0x180037cae  mov     rax, [rax+8]
0x180037cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cb7  test    eax, eax
0x180037cb9  jz      short loc_180037CC4
0x180037cbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037cc2  jmp     short loc_180037CD2
0x180037cc4  lea     rcx, qword_18006EB20; this
0x180037ccb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037cd2  cmp     [rcx+8], dil
0x180037cd6  jz      short loc_180037CF6
0x180037cd8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037cdd  cmp     [rax+7CCh], ebx
0x180037ce3  jz      short loc_180037CF6
0x180037ce5  mov     r9d, ebx; int
0x180037ce8  mov     r8d, r12d; int
0x180037ceb  mov     rdx, rsi; char *
0x180037cee  mov     rcx, rax; this
0x180037cf1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037cf6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037cfb  cmp     al, 1
0x180037cfd  jb      loc_180037F44
0x180037d03  mov     edx, 7Dh ; '}'
0x180037d08  jmp     loc_180037F26
0x180037d0d  mov     ebx, 8000FFFFh
0x180037d12  test    rcx, rcx
0x180037d15  jnz     short loc_180037D58
0x180037d17  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037d1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037d24  mov     rcx, rax
0x180037d27  test    rax, rax
0x180037d2a  jz      short loc_180037D4A
0x180037d2c  mov     rax, [rax]
0x180037d2f  mov     edx, 7F0h
0x180037d34  mov     rax, [rax+8]
0x180037d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d3d  test    eax, eax
0x180037d3f  jz      short loc_180037D4A
0x180037d41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037d48  jmp     short loc_180037D58
0x180037d4a  lea     rcx, qword_18006EB20; this
0x180037d51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037d58  cmp     [rcx+8], dil
0x180037d5c  jz      short loc_180037D7F
0x180037d5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037d63  cmp     [rax+7CCh], ebx
0x180037d69  jz      short loc_180037D7F
0x180037d6b  mov     r9d, ebx; int
0x180037d6e  mov     r8d, 75Ah; int
0x180037d74  mov     rdx, rsi; char *
0x180037d77  mov     rcx, rax; this
0x180037d7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037d7f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037d84  cmp     al, 1
0x180037d86  jb      loc_180037F44
0x180037d8c  mov     edx, 7Eh ; '~'
0x180037d91  jmp     loc_180037F26
0x180037d96  mov     eax, 1Fh
0x180037d9b  cmp     bx, ax
0x180037d9e  jnz     loc_180037E5D
0x180037da4  mov     rcx, [r15+8]; unsigned __int16 *
0x180037da8  mov     r8, r12; unsigned __int16 *
0x180037dab  shr     r13, 1
0x180037dae  mov     rdx, r13; unsigned __int64
0x180037db1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037db6  mov     r12d, 760h
0x180037dbc  lea     rcx, [rbp+arg_8]; this
0x180037dc0  mov     r8d, r12d; int
0x180037dc3  mov     rdx, rsi; char *
0x180037dc6  mov     ebx, eax
0x180037dc8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037dcd  test    ebx, ebx
0x180037dcf  jns     loc_180037F44
0x180037dd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ddc  test    rcx, rcx
0x180037ddf  jnz     short loc_180037E22
0x180037de1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037de7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037dee  mov     rcx, rax
0x180037df1  test    rax, rax
0x180037df4  jz      short loc_180037E14
0x180037df6  mov     rax, [rax]
0x180037df9  mov     edx, 7F0h
0x180037dfe  mov     rax, [rax+8]
0x180037e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e07  test    eax, eax
0x180037e09  jz      short loc_180037E14
0x180037e0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037e12  jmp     short loc_180037E22
0x180037e14  lea     rcx, qword_18006EB20; this
0x180037e1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037e22  cmp     [rcx+8], dil
0x180037e26  jz      short loc_180037E46
0x180037e28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037e2d  cmp     [rax+7CCh], ebx
0x180037e33  jz      short loc_180037E46
0x180037e35  mov     r9d, ebx; int
0x180037e38  mov     r8d, r12d; int
0x180037e3b  mov     rdx, rsi; char *
0x180037e3e  mov     rcx, rax; this
0x180037e41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037e46  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037e4b  cmp     al, 1
0x180037e4d  jb      loc_180037F44
0x180037e53  mov     edx, 7Fh
0x180037e58  jmp     loc_180037F26
0x180037e5d  mov     rcx, r12; psz
0x180037e60  mov     ebx, edi
0x180037e62  call    cs:__imp_SysAllocString
0x180037e68  mov     [r15+8], rax
0x180037e6c  test    rax, rax
0x180037e6f  jnz     loc_180037F4D
0x180037e75  mov     r12d, 767h
0x180037e7b  lea     rcx, [rbp+arg_8]; this
0x180037e7f  mov     r8d, r12d; int
0x180037e82  mov     rdx, rsi; char *
0x180037e85  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037e8a  call    cs:__imp_GetLastError
0x180037e90  mov     ebx, eax
0x180037e92  test    eax, eax
0x180037e94  jle     short loc_180037E9F
0x180037e96  movzx   ebx, ax
0x180037e99  or      ebx, 80070000h
0x180037e9f  test    ebx, ebx
0x180037ea1  jns     loc_180037F44
0x180037ea7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037eae  test    rcx, rcx
0x180037eb1  jnz     short loc_180037EF4
0x180037eb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037eb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ec0  mov     rcx, rax
0x180037ec3  test    rax, rax
0x180037ec6  jz      short loc_180037EE6
0x180037ec8  mov     rax, [rax]
0x180037ecb  mov     edx, 7F0h
0x180037ed0  mov     rax, [rax+8]
0x180037ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
