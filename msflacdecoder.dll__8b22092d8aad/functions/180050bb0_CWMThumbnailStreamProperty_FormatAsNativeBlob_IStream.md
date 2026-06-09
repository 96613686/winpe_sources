# CWMThumbnailStreamProperty::FormatAsNativeBlob(IStream *)

- ea: `0x180050bb0`
- end: `0x18005108c`
- name: `?FormatAsNativeBlob@CWMThumbnailStreamProperty@@MEAAJPEAUIStream@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(PROPVARIANT *this, struct IStream *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180050bb0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050e14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180051052`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180051052`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050fbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050fbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMThumbnailStreamProperty::FormatAsNativeBlob(PROPVARIANT *this, struct IStream *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  char *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v31[3]; // [rsp+34h] [rbp-94h] BYREF
  _BYTE v32[16]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-78h]

  memset_0(v32, 0, 0x50u);
  v31[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CWMThumbnailStreamProperty::FormatAsNativeBlob",
    640);
  v5 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v32, 1);
  if ( v5 < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 640, v5);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 60;
    goto LABEL_12;
  }
  v10 = v33;
  if ( v33 >= 0xFFFFFFFF )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v13, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 649, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v14 = 61;
    goto LABEL_68;
  }
  v15 = v33 + 47;
  if ( (unsigned int)v33 >= 0xFFFFFFD1 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v18, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 654, -2147024362);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 62;
    goto LABEL_12;
  }
  this[5].vt = 65;
  this[5].lVal = v15;
  v19 = (char *)CoTaskMemAlloc(v15);
  this[5].bstrblobVal.pData = (BYTE *)v19;
  if ( !v19 )
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
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
      if ( *((_DWORD *)v22 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v22, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 664, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 63;
    goto LABEL_12;
  }
  *v19 = 3;
  *(_DWORD *)(v19 + 1) = v10;
  *(_OWORD *)(v19 + 5) = *(_OWORD *)L"image/jpeg";
  *(_QWORD *)(v19 + 19) = *(_QWORD *)L"peg";
  *(_OWORD *)(v19 + 27) = *(_OWORD *)L"thumbnail";
  *(_DWORD *)(v19 + 43) = *(_DWORD *)L"l";
  v5 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, _DWORD *))a2->lpVtbl->Read)(a2, v19 + 47, v10, v31);
  if ( v5 < 0 )
  {
    v23 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)((__int64 (*)(void))MFGetCallStackTracingWeakReference)();
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != v5 )
        CallStackContext::TraceFailure(v25, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 685, v5);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v9 = 64;
LABEL_12:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
LABEL_69:
    PropVariantClear(this + 5);
    goto LABEL_70;
  }
  if ( v31[0] != v10 )
  {
    v26 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)((__int64 (*)(void))MFGetCallStackTracingWeakReference)();
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
      if ( *((_DWORD *)v28 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v28, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 689, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_69;
    v14 = 65;
LABEL_68:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      -2147418113);
    goto LABEL_69;
  }
LABEL_70:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180050bb0  mov     [rsp+arg_10], rbx
0x180050bb5  push    rsi
0x180050bb6  push    rdi
0x180050bb7  push    r12
0x180050bb9  push    r13
0x180050bbb  push    r14
0x180050bbd  sub     rsp, 0A0h
0x180050bc4  mov     rax, cs:__security_cookie
0x180050bcb  xor     rax, rsp
0x180050bce  mov     [rsp+0C8h+var_38], rax
0x180050bd6  mov     r14, rdx
0x180050bd9  mov     rsi, rcx
0x180050bdc  xor     edx, edx; Val
0x180050bde  lea     rcx, [rsp+0C8h+var_88]; void *
0x180050be3  lea     r8d, [rdx+50h]; Size
0x180050be7  call    memset_0
0x180050bec  mov     edi, 280h
0x180050bf1  mov     [rsp+0C8h+var_94], 0
0x180050bf9  lea     r12, aCwmthumbnailst_1; "CWMThumbnailStreamProperty::FormatAsNat"...
0x180050c00  mov     r8d, edi; int
0x180050c03  mov     rdx, r12; char *
0x180050c06  lea     rcx, [rsp+0C8h+var_98]; this
0x180050c0b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050c10  mov     rax, [r14]
0x180050c13  lea     rdx, [rsp+0C8h+var_88]
0x180050c18  mov     r8d, 1
0x180050c1e  mov     rcx, r14
0x180050c21  mov     rax, [rax+60h]
0x180050c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c2a  mov     ebx, eax
0x180050c2c  test    eax, eax
0x180050c2e  jns     loc_180050CC0
0x180050c34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050c3b  test    rcx, rcx
0x180050c3e  jnz     short loc_180050C81
0x180050c40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050c46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050c4d  mov     rcx, rax
0x180050c50  test    rax, rax
0x180050c53  jz      short loc_180050C73
0x180050c55  mov     rax, [rax]
0x180050c58  mov     edx, 7F0h
0x180050c5d  mov     rax, [rax+8]
0x180050c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c66  test    eax, eax
0x180050c68  jz      short loc_180050C73
0x180050c6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050c71  jmp     short loc_180050C81
0x180050c73  lea     rcx, qword_18006EB20; this
0x180050c7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050c81  cmp     byte ptr [rcx+8], 0
0x180050c85  jz      short loc_180050CA5
0x180050c87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050c8c  cmp     [rax+7CCh], ebx
0x180050c92  jz      short loc_180050CA5
0x180050c94  mov     r9d, ebx; int
0x180050c97  mov     r8d, edi; int
0x180050c9a  mov     rdx, r12; char *
0x180050c9d  mov     rcx, rax; this
0x180050ca0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050ca5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050caa  cmp     al, 1
0x180050cac  jb      loc_18005104E
0x180050cb2  mov     edx, 3Ch ; '<'
0x180050cb7  mov     [rsp+0C8h+var_A8], ebx
0x180050cbb  jmp     loc_180051034
0x180050cc0  mov     rdi, [rsp+0C8h+var_78]
0x180050cc5  mov     eax, 0FFFFFFFFh
0x180050cca  cmp     rdi, rax
0x180050ccd  jb      loc_180050D65
0x180050cd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050cda  mov     edi, 8000FFFFh
0x180050cdf  mov     ebx, edi
0x180050ce1  test    rcx, rcx
0x180050ce4  jnz     short loc_180050D27
0x180050ce6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050cec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050cf3  mov     rcx, rax
0x180050cf6  test    rax, rax
0x180050cf9  jz      short loc_180050D19
0x180050cfb  mov     rax, [rax]
0x180050cfe  mov     edx, 7F0h
0x180050d03  mov     rax, [rax+8]
0x180050d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d0c  test    eax, eax
0x180050d0e  jz      short loc_180050D19
0x180050d10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d17  jmp     short loc_180050D27
0x180050d19  lea     rcx, qword_18006EB20; this
0x180050d20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d27  cmp     byte ptr [rcx+8], 0
0x180050d2b  jz      short loc_180050D4E
0x180050d2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050d32  cmp     [rax+7CCh], edi
0x180050d38  jz      short loc_180050D4E
0x180050d3a  mov     r9d, edi; int
0x180050d3d  mov     r8d, 289h; int
0x180050d43  mov     rdx, r12; char *
0x180050d46  mov     rcx, rax; this
0x180050d49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050d4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050d53  cmp     al, 1
0x180050d55  jb      loc_18005104E
0x180050d5b  mov     edx, 3Dh ; '='
0x180050d60  jmp     loc_180051030
0x180050d65  lea     eax, [rdi+2Fh]
0x180050d68  cmp     eax, 2Fh ; '/'
0x180050d6b  jnb     loc_180050E01
0x180050d71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d78  mov     ebx, 80070216h
0x180050d7d  test    rcx, rcx
0x180050d80  jnz     short loc_180050DC3
0x180050d82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050d88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050d8f  mov     rcx, rax
0x180050d92  test    rax, rax
0x180050d95  jz      short loc_180050DB5
0x180050d97  mov     rax, [rax]
0x180050d9a  mov     edx, 7F0h
0x180050d9f  mov     rax, [rax+8]
0x180050da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050da8  test    eax, eax
0x180050daa  jz      short loc_180050DB5
0x180050dac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050db3  jmp     short loc_180050DC3
0x180050db5  lea     rcx, qword_18006EB20; this
0x180050dbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050dc3  cmp     byte ptr [rcx+8], 0
0x180050dc7  jz      short loc_180050DEA
0x180050dc9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050dce  cmp     [rax+7CCh], ebx
0x180050dd4  jz      short loc_180050DEA
0x180050dd6  mov     r9d, ebx; int
0x180050dd9  mov     r8d, 28Eh; int
0x180050ddf  mov     rdx, r12; char *
0x180050de2  mov     rcx, rax; this
0x180050de5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050dea  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050def  cmp     al, 1
0x180050df1  jb      loc_18005104E
0x180050df7  mov     edx, 3Eh ; '>'
0x180050dfc  jmp     loc_180050CB7
0x180050e01  mov     r13d, 41h ; 'A'
0x180050e07  mov     ecx, eax; cb
0x180050e09  mov     [rsi+78h], r13w
0x180050e0e  mov     [rsi+80h], eax
0x180050e14  call    cs:__imp_CoTaskMemAlloc
0x180050e1a  mov     [rsi+88h], rax
0x180050e21  mov     rdx, rax
0x180050e24  test    rax, rax
0x180050e27  jnz     loc_180050EBD
0x180050e2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050e34  mov     ebx, 8007000Eh
0x180050e39  test    rcx, rcx
0x180050e3c  jnz     short loc_180050E7F
0x180050e3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050e44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050e4b  mov     rcx, rax
0x180050e4e  test    rax, rax
0x180050e51  jz      short loc_180050E71
0x180050e53  mov     rax, [rax]
0x180050e56  mov     edx, 7F0h
0x180050e5b  mov     rax, [rax+8]
0x180050e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e64  test    eax, eax
0x180050e66  jz      short loc_180050E71
0x180050e68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050e6f  jmp     short loc_180050E7F
0x180050e71  lea     rcx, qword_18006EB20; this
0x180050e78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050e7f  cmp     byte ptr [rcx+8], 0
0x180050e83  jz      short loc_180050EA6
0x180050e85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050e8a  cmp     [rax+7CCh], ebx
0x180050e90  jz      short loc_180050EA6
0x180050e92  mov     r9d, ebx; int
0x180050e95  mov     r8d, 298h; int
0x180050e9b  mov     rdx, r12; char *
0x180050e9e  mov     rcx, rax; this
0x180050ea1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050ea6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050eab  cmp     al, 1
0x180050ead  jb      loc_18005104E
0x180050eb3  mov     edx, 3Fh ; '?'
0x180050eb8  jmp     loc_180050CB7
0x180050ebd  mov     byte ptr [rax], 3
0x180050ec0  lea     r9, [rsp+0C8h+var_94]
0x180050ec5  mov     [rax+1], edi
0x180050ec8  mov     r8d, edi
0x180050ecb  movups  xmm0, xmmword ptr cs:aImageJpeg; "image/jpeg"
0x180050ed2  mov     rcx, r14
0x180050ed5  movups  xmmword ptr [rax+5], xmm0
0x180050ed9  movsd   xmm1, qword ptr cs:aImageJpeg+0Eh; "peg"
0x180050ee1  movsd   qword ptr [rax+13h], xmm1
0x180050ee6  movups  xmm0, xmmword ptr cs:aThumbnail; "thumbnail"
0x180050eed  movups  xmmword ptr [rax+1Bh], xmm0
0x180050ef1  mov     eax, dword ptr cs:aThumbnail+10h; "l"
0x180050ef7  mov     [rdx+2Bh], eax
0x180050efa  add     rdx, 2Fh ; '/'
0x180050efe  mov     rax, [r14]
0x180050f01  mov     rax, [rax+18h]
0x180050f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f0a  mov     ebx, eax
0x180050f0c  test    eax, eax
0x180050f0e  jns     loc_180050F9F
0x180050f14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050f1b  test    rcx, rcx
0x180050f1e  jnz     short loc_180050F61
0x180050f20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050f26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050f2d  mov     rcx, rax
0x180050f30  test    rax, rax
0x180050f33  jz      short loc_180050F53
0x180050f35  mov     rax, [rax]
0x180050f38  mov     edx, 7F0h
0x180050f3d  mov     rax, [rax+8]
0x180050f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f46  test    eax, eax
0x180050f48  jz      short loc_180050F53
0x180050f4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050f51  jmp     short loc_180050F61
0x180050f53  lea     rcx, qword_18006EB20; this
0x180050f5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050f61  cmp     byte ptr [rcx+8], 0
0x180050f65  jz      short loc_180050F88
0x180050f67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050f6c  cmp     [rax+7CCh], ebx
0x180050f72  jz      short loc_180050F88
0x180050f74  mov     r9d, ebx; int
0x180050f77  mov     r8d, 2ADh; int
0x180050f7d  mov     rdx, r12; char *
0x180050f80  mov     rcx, rax; this
0x180050f83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050f88  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180050f8d  cmp     al, 1
0x180050f8f  jb      loc_18005104E
0x180050f95  mov     edx, 40h ; '@'
0x180050f9a  jmp     loc_180050CB7
0x180050f9f  cmp     [rsp+0C8h+var_94], edi
0x180050fa3  jz      loc_180051058
0x180050fa9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050fb0  mov     edi, 8000FFFFh
0x180050fb5  mov     ebx, edi
0x180050fb7  test    rcx, rcx
0x180050fba  jnz     short loc_180050FFD
0x180050fbc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050fc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050fc9  mov     rcx, rax
0x180050fcc  test    rax, rax
0x180050fcf  jz      short loc_180050FEF
0x180050fd1  mov     rax, [rax]
0x180050fd4  mov     edx, 7F0h
0x180050fd9  mov     rax, [rax+8]
0x180050fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fe2  test    eax, eax
0x180050fe4  jz      short loc_180050FEF
0x180050fe6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050fed  jmp     short loc_180050FFD
0x180050fef  lea     rcx, qword_18006EB20; this
0x180050ff6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ffd  cmp     byte ptr [rcx+8], 0
0x180051001  jz      short loc_180051024
0x180051003  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051008  cmp     [rax+7CCh], edi
0x18005100e  jz      short loc_180051024
0x180051010  mov     r9d, edi; int
0x180051013  mov     r8d, 2B1h; int
0x180051019  mov     rdx, r12; char *
0x18005101c  mov     rcx, rax; this
0x18005101f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051024  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180051029  cmp     al, 1
0x18005102b  jb      short loc_18005104E
0x18005102d  mov     edx, r13d
0x180051030  mov     [rsp+0C8h+var_A8], edi
0x180051034  mov     rcx, cs:WPP_GLOBAL_Control
0x18005103b  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180051042  mov     r9, rsi
0x180051045  mov     rcx, [rcx+10h]
0x180051049  call    WPP_SF_qd
0x18005104e  lea     rcx, [rsi+78h]; pvar
0x180051052  call    cs:__imp_PropVariantClear
0x180051058  lea     rcx, [rsp+0C8h+var_98]; this
0x18005105d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180051062  mov     eax, ebx
0x180051064  mov     rcx, [rsp+0C8h+var_38]
0x18005106c  xor     rcx, rsp; StackCookie
0x18005106f  call    __security_check_cookie
0x180051074  mov     rbx, [rsp+0C8h+arg_10]
0x18005107c  add     rsp, 0A0h
0x180051083  pop     r14
0x180051085  pop     r13
0x180051087  pop     r12
0x180051089  pop     rdi
0x18005108a  pop     rsi
0x18005108b  retn
```
