# CWMThumbnailStreamProperty::FormatAsNativeBlob(IStream *)

- ea: `0x18006f3a0`
- end: `0x18006f8ad`
- name: `?FormatAsNativeBlob@CWMThumbnailStreamProperty@@MEAAJPEAUIStream@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002400`
- `0x180002e54`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18006f3a0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f616`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f86c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006f86c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f4dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f72e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f7d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f430`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f4dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f72e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f7d0`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::FormatAsNativeBlob(PROPVARIANT *this, struct IStream *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  char *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _BYTE v37[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v38[3]; // [rsp+34h] [rbp-94h] BYREF
  _BYTE v39[16]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v40; // [rsp+50h] [rbp-78h]

  memset_0(v39, 0, 0x50u);
  v38[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v37,
    "CWMThumbnailStreamProperty::FormatAsNativeBlob",
    640);
  v5 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v39, 1);
  if ( v5 < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 640, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v11 = 60;
    goto LABEL_12;
  }
  v12 = v40;
  if ( v40 >= 0xFFFFFFFF )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v15, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 649, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v16 = 61;
    goto LABEL_68;
  }
  v17 = v40 + 47;
  if ( (unsigned int)v40 >= 0xFFFFFFD1 )
  {
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v20, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 654, -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v11 = 62;
    goto LABEL_12;
  }
  this[5].vt = 65;
  this[5].lVal = v17;
  v21 = (char *)CoTaskMemAlloc(v17);
  this[5].bstrblobVal.pData = (BYTE *)v21;
  if ( !v21 )
  {
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v22, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v26, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 664, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v11 = 63;
    goto LABEL_12;
  }
  *v21 = 3;
  *(_DWORD *)(v21 + 1) = v12;
  *(_OWORD *)(v21 + 5) = *(_OWORD *)L"image/jpeg";
  *(_QWORD *)(v21 + 19) = *(_QWORD *)L"peg";
  *(_OWORD *)(v21 + 27) = *(_OWORD *)L"thumbnail";
  *(_DWORD *)(v21 + 43) = *(_DWORD *)L"l";
  v5 = ((__int64 (__fastcall *)(struct IStream *, char *, _QWORD, _DWORD *))a2->lpVtbl->Read)(a2, v21 + 47, v12, v38);
  if ( v5 < 0 )
  {
    v30 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != v5 )
        CallStackContext::TraceFailure(v32, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 685, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v11 = 64;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
LABEL_69:
    PropVariantClear(this + 5);
    goto LABEL_70;
  }
  if ( v38[0] != v12 )
  {
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v35, "CWMThumbnailStreamProperty::FormatAsNativeBlob", 689, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_69;
    v16 = 65;
LABEL_68:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      -2147418113);
    goto LABEL_69;
  }
LABEL_70:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006f3a0  mov     [rsp+arg_10], rbx
0x18006f3a5  push    rsi
0x18006f3a6  push    rdi
0x18006f3a7  push    r12
0x18006f3a9  push    r13
0x18006f3ab  push    r14
0x18006f3ad  sub     rsp, 0A0h
0x18006f3b4  mov     rax, cs:__security_cookie
0x18006f3bb  xor     rax, rsp
0x18006f3be  mov     [rsp+0C8h+var_38], rax
0x18006f3c6  mov     r14, rdx
0x18006f3c9  mov     rsi, rcx
0x18006f3cc  xor     edx, edx; Val
0x18006f3ce  lea     rcx, [rsp+0C8h+var_88]; void *
0x18006f3d3  lea     r8d, [rdx+50h]; Size
0x18006f3d7  call    memset_0
0x18006f3dc  mov     edi, 280h
0x18006f3e1  mov     [rsp+0C8h+var_94], 0
0x18006f3e9  lea     r12, aCwmthumbnailst_1; "CWMThumbnailStreamProperty::FormatAsNat"...
0x18006f3f0  mov     r8d, edi; int
0x18006f3f3  mov     rdx, r12; char *
0x18006f3f6  lea     rcx, [rsp+0C8h+var_98]; this
0x18006f3fb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006f400  mov     rax, [r14]
0x18006f403  lea     rdx, [rsp+0C8h+var_88]
0x18006f408  mov     r8d, 1
0x18006f40e  mov     rcx, r14
0x18006f411  mov     rax, [rax+60h]
0x18006f415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f41a  mov     ebx, eax
0x18006f41c  test    eax, eax
0x18006f41e  jns     loc_18006F4B6
0x18006f424  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f42b  test    rcx, rcx
0x18006f42e  jnz     short loc_18006F477
0x18006f430  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f437  nop     dword ptr [rax+rax+00h]
0x18006f43c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f443  mov     rcx, rax
0x18006f446  test    rax, rax
0x18006f449  jz      short loc_18006F469
0x18006f44b  mov     rax, [rax]
0x18006f44e  mov     edx, 7F0h
0x18006f453  mov     rax, [rax+8]
0x18006f457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f45c  test    eax, eax
0x18006f45e  jz      short loc_18006F469
0x18006f460  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f467  jmp     short loc_18006F477
0x18006f469  lea     rcx, qword_1800DBF70; this
0x18006f470  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f477  cmp     byte ptr [rcx+8], 0
0x18006f47b  jz      short loc_18006F49B
0x18006f47d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f482  cmp     [rax+7CCh], ebx
0x18006f488  jz      short loc_18006F49B
0x18006f48a  mov     r9d, ebx; int
0x18006f48d  mov     r8d, edi; int
0x18006f490  mov     rdx, r12; char *
0x18006f493  mov     rcx, rax; this
0x18006f496  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f49b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f4a2  jb      loc_18006F868
0x18006f4a8  mov     edx, 3Ch ; '<'
0x18006f4ad  mov     [rsp+0C8h+var_A8], ebx
0x18006f4b1  jmp     loc_18006F84E
0x18006f4b6  mov     rdi, [rsp+0C8h+var_78]
0x18006f4bb  mov     eax, 0FFFFFFFFh
0x18006f4c0  cmp     rdi, rax
0x18006f4c3  jb      loc_18006F561
0x18006f4c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f4d0  mov     edi, 8000FFFFh
0x18006f4d5  mov     ebx, edi
0x18006f4d7  test    rcx, rcx
0x18006f4da  jnz     short loc_18006F523
0x18006f4dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f4e3  nop     dword ptr [rax+rax+00h]
0x18006f4e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f4ef  mov     rcx, rax
0x18006f4f2  test    rax, rax
0x18006f4f5  jz      short loc_18006F515
0x18006f4f7  mov     rax, [rax]
0x18006f4fa  mov     edx, 7F0h
0x18006f4ff  mov     rax, [rax+8]
0x18006f503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f508  test    eax, eax
0x18006f50a  jz      short loc_18006F515
0x18006f50c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f513  jmp     short loc_18006F523
0x18006f515  lea     rcx, qword_1800DBF70; this
0x18006f51c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f523  cmp     byte ptr [rcx+8], 0
0x18006f527  jz      short loc_18006F54A
0x18006f529  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f52e  cmp     [rax+7CCh], edi
0x18006f534  jz      short loc_18006F54A
0x18006f536  mov     r9d, edi; int
0x18006f539  mov     r8d, 289h; int
0x18006f53f  mov     rdx, r12; char *
0x18006f542  mov     rcx, rax; this
0x18006f545  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f54a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f551  jb      loc_18006F868
0x18006f557  mov     edx, 3Dh ; '='
0x18006f55c  jmp     loc_18006F84A
0x18006f561  lea     eax, [rdi+2Fh]
0x18006f564  cmp     eax, 2Fh ; '/'
0x18006f567  jnb     loc_18006F603
0x18006f56d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f574  mov     ebx, 80070216h
0x18006f579  test    rcx, rcx
0x18006f57c  jnz     short loc_18006F5C5
0x18006f57e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f585  nop     dword ptr [rax+rax+00h]
0x18006f58a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f591  mov     rcx, rax
0x18006f594  test    rax, rax
0x18006f597  jz      short loc_18006F5B7
0x18006f599  mov     rax, [rax]
0x18006f59c  mov     edx, 7F0h
0x18006f5a1  mov     rax, [rax+8]
0x18006f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f5aa  test    eax, eax
0x18006f5ac  jz      short loc_18006F5B7
0x18006f5ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f5b5  jmp     short loc_18006F5C5
0x18006f5b7  lea     rcx, qword_1800DBF70; this
0x18006f5be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f5c5  cmp     byte ptr [rcx+8], 0
0x18006f5c9  jz      short loc_18006F5EC
0x18006f5cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f5d0  cmp     [rax+7CCh], ebx
0x18006f5d6  jz      short loc_18006F5EC
0x18006f5d8  mov     r9d, ebx; int
0x18006f5db  mov     r8d, 28Eh; int
0x18006f5e1  mov     rdx, r12; char *
0x18006f5e4  mov     rcx, rax; this
0x18006f5e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f5ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f5f3  jb      loc_18006F868
0x18006f5f9  mov     edx, 3Eh ; '>'
0x18006f5fe  jmp     loc_18006F4AD
0x18006f603  mov     r13d, 41h ; 'A'
0x18006f609  mov     ecx, eax; cb
0x18006f60b  mov     [rsi+78h], r13w
0x18006f610  mov     [rsi+80h], eax
0x18006f616  call    cs:__imp_CoTaskMemAlloc
0x18006f61d  nop     dword ptr [rax+rax+00h]
0x18006f622  mov     [rsi+88h], rax
0x18006f629  mov     rdx, rax
0x18006f62c  test    rax, rax
0x18006f62f  jnz     loc_18006F6CB
0x18006f635  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f63c  mov     ebx, 8007000Eh
0x18006f641  test    rcx, rcx
0x18006f644  jnz     short loc_18006F68D
0x18006f646  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f64d  nop     dword ptr [rax+rax+00h]
0x18006f652  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f659  mov     rcx, rax
0x18006f65c  test    rax, rax
0x18006f65f  jz      short loc_18006F67F
0x18006f661  mov     rax, [rax]
0x18006f664  mov     edx, 7F0h
0x18006f669  mov     rax, [rax+8]
0x18006f66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f672  test    eax, eax
0x18006f674  jz      short loc_18006F67F
0x18006f676  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f67d  jmp     short loc_18006F68D
0x18006f67f  lea     rcx, qword_1800DBF70; this
0x18006f686  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f68d  cmp     byte ptr [rcx+8], 0
0x18006f691  jz      short loc_18006F6B4
0x18006f693  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f698  cmp     [rax+7CCh], ebx
0x18006f69e  jz      short loc_18006F6B4
0x18006f6a0  mov     r9d, ebx; int
0x18006f6a3  mov     r8d, 298h; int
0x18006f6a9  mov     rdx, r12; char *
0x18006f6ac  mov     rcx, rax; this
0x18006f6af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f6b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f6bb  jb      loc_18006F868
0x18006f6c1  mov     edx, 3Fh ; '?'
0x18006f6c6  jmp     loc_18006F4AD
0x18006f6cb  mov     byte ptr [rax], 3
0x18006f6ce  lea     r9, [rsp+0C8h+var_94]
0x18006f6d3  mov     [rax+1], edi
0x18006f6d6  mov     r8d, edi
0x18006f6d9  movups  xmm0, xmmword ptr cs:aImageJpeg; "image/jpeg"
0x18006f6e0  mov     rcx, r14
0x18006f6e3  movups  xmmword ptr [rax+5], xmm0
0x18006f6e7  movsd   xmm1, qword ptr cs:aImageJpeg+0Eh; "peg"
0x18006f6ef  movsd   qword ptr [rax+13h], xmm1
0x18006f6f4  movups  xmm0, xmmword ptr cs:aThumbnail; "thumbnail"
0x18006f6fb  movups  xmmword ptr [rax+1Bh], xmm0
0x18006f6ff  mov     eax, dword ptr cs:aThumbnail+10h; "l"
0x18006f705  mov     [rdx+2Bh], eax
0x18006f708  add     rdx, 2Fh ; '/'
0x18006f70c  mov     rax, [r14]
0x18006f70f  mov     rax, [rax+18h]
0x18006f713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f718  mov     ebx, eax
0x18006f71a  test    eax, eax
0x18006f71c  jns     loc_18006F7B3
0x18006f722  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f729  test    rcx, rcx
0x18006f72c  jnz     short loc_18006F775
0x18006f72e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f735  nop     dword ptr [rax+rax+00h]
0x18006f73a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f741  mov     rcx, rax
0x18006f744  test    rax, rax
0x18006f747  jz      short loc_18006F767
0x18006f749  mov     rax, [rax]
0x18006f74c  mov     edx, 7F0h
0x18006f751  mov     rax, [rax+8]
0x18006f755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f75a  test    eax, eax
0x18006f75c  jz      short loc_18006F767
0x18006f75e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f765  jmp     short loc_18006F775
0x18006f767  lea     rcx, qword_1800DBF70; this
0x18006f76e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f775  cmp     byte ptr [rcx+8], 0
0x18006f779  jz      short loc_18006F79C
0x18006f77b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f780  cmp     [rax+7CCh], ebx
0x18006f786  jz      short loc_18006F79C
0x18006f788  mov     r9d, ebx; int
0x18006f78b  mov     r8d, 2ADh; int
0x18006f791  mov     rdx, r12; char *
0x18006f794  mov     rcx, rax; this
0x18006f797  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f79c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f7a3  jb      loc_18006F868
0x18006f7a9  mov     edx, 40h ; '@'
0x18006f7ae  jmp     loc_18006F4AD
0x18006f7b3  cmp     [rsp+0C8h+var_94], edi
0x18006f7b7  jz      loc_18006F878
0x18006f7bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7c4  mov     edi, 8000FFFFh
0x18006f7c9  mov     ebx, edi
0x18006f7cb  test    rcx, rcx
0x18006f7ce  jnz     short loc_18006F817
0x18006f7d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f7d7  nop     dword ptr [rax+rax+00h]
0x18006f7dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f7e3  mov     rcx, rax
0x18006f7e6  test    rax, rax
0x18006f7e9  jz      short loc_18006F809
0x18006f7eb  mov     rax, [rax]
0x18006f7ee  mov     edx, 7F0h
0x18006f7f3  mov     rax, [rax+8]
0x18006f7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7fc  test    eax, eax
0x18006f7fe  jz      short loc_18006F809
0x18006f800  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f807  jmp     short loc_18006F817
0x18006f809  lea     rcx, qword_1800DBF70; this
0x18006f810  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f817  cmp     byte ptr [rcx+8], 0
0x18006f81b  jz      short loc_18006F83E
0x18006f81d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f822  cmp     [rax+7CCh], edi
0x18006f828  jz      short loc_18006F83E
0x18006f82a  mov     r9d, edi; int
0x18006f82d  mov     r8d, 2B1h; int
0x18006f833  mov     rdx, r12; char *
0x18006f836  mov     rcx, rax; this
0x18006f839  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f83e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f845  jb      short loc_18006F868
0x18006f847  mov     edx, r13d
0x18006f84a  mov     [rsp+0C8h+var_A8], edi
0x18006f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f855  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18006f85c  mov     r9, rsi
0x18006f85f  mov     rcx, [rcx+10h]
0x18006f863  call    WPP_SF_qD
0x18006f868  lea     rcx, [rsi+78h]; pvar
0x18006f86c  call    cs:__imp_PropVariantClear
0x18006f873  nop     dword ptr [rax+rax+00h]
0x18006f878  lea     rcx, [rsp+0C8h+var_98]; this
0x18006f87d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006f882  mov     eax, ebx
0x18006f884  mov     rcx, [rsp+0C8h+var_38]
0x18006f88c  xor     rcx, rsp; StackCookie
0x18006f88f  call    __security_check_cookie
0x18006f894  mov     rbx, [rsp+0C8h+arg_10]
0x18006f89c  add     rsp, 0A0h
0x18006f8a3  pop     r14
0x18006f8a5  pop     r13
0x18006f8a7  pop     r12
0x18006f8a9  pop     rdi
0x18006f8aa  pop     rsi
0x18006f8ab  retn
```
