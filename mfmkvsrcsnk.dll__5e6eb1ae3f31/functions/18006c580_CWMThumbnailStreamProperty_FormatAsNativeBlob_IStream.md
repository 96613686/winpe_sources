# CWMThumbnailStreamProperty::FormatAsNativeBlob(IStream *)

- ea: `0x18006c580`
- end: `0x18006ca5c`
- name: `?FormatAsNativeBlob@CWMThumbnailStreamProperty@@MEAAJPEAUIStream@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800023e0`
- `0x180002e14`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006c580`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c7e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ca22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ca22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c610`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c752`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c80e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c8f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c98c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c610`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c752`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c80e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c8f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c98c`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v18 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v24 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v30 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v33 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18006c580  mov     [rsp+arg_10], rbx
0x18006c585  push    rsi
0x18006c586  push    rdi
0x18006c587  push    r12
0x18006c589  push    r13
0x18006c58b  push    r14
0x18006c58d  sub     rsp, 0A0h
0x18006c594  mov     rax, cs:__security_cookie
0x18006c59b  xor     rax, rsp
0x18006c59e  mov     [rsp+0C8h+var_38], rax
0x18006c5a6  mov     r14, rdx
0x18006c5a9  mov     rsi, rcx
0x18006c5ac  xor     edx, edx; Val
0x18006c5ae  lea     rcx, [rsp+0C8h+var_88]; void *
0x18006c5b3  lea     r8d, [rdx+50h]; Size
0x18006c5b7  call    memset_0
0x18006c5bc  mov     edi, 280h
0x18006c5c1  mov     [rsp+0C8h+var_94], 0
0x18006c5c9  lea     r12, aCwmthumbnailst_1; "CWMThumbnailStreamProperty::FormatAsNat"...
0x18006c5d0  mov     r8d, edi; int
0x18006c5d3  mov     rdx, r12; char *
0x18006c5d6  lea     rcx, [rsp+0C8h+var_98]; this
0x18006c5db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006c5e0  mov     rax, [r14]
0x18006c5e3  lea     rdx, [rsp+0C8h+var_88]
0x18006c5e8  mov     r8d, 1
0x18006c5ee  mov     rcx, r14
0x18006c5f1  mov     rax, [rax+60h]
0x18006c5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5fa  mov     ebx, eax
0x18006c5fc  test    eax, eax
0x18006c5fe  jns     loc_18006C690
0x18006c604  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c60b  test    rcx, rcx
0x18006c60e  jnz     short loc_18006C651
0x18006c610  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c616  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c61d  mov     rcx, rax
0x18006c620  test    rax, rax
0x18006c623  jz      short loc_18006C643
0x18006c625  mov     rax, [rax]
0x18006c628  mov     edx, 7F0h
0x18006c62d  mov     rax, [rax+8]
0x18006c631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c636  test    eax, eax
0x18006c638  jz      short loc_18006C643
0x18006c63a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c641  jmp     short loc_18006C651
0x18006c643  lea     rcx, qword_1800D6F70; this
0x18006c64a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c651  cmp     byte ptr [rcx+8], 0
0x18006c655  jz      short loc_18006C675
0x18006c657  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c65c  cmp     [rax+7CCh], ebx
0x18006c662  jz      short loc_18006C675
0x18006c664  mov     r9d, ebx; int
0x18006c667  mov     r8d, edi; int
0x18006c66a  mov     rdx, r12; char *
0x18006c66d  mov     rcx, rax; this
0x18006c670  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c675  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c67c  jb      loc_18006CA1E
0x18006c682  mov     edx, 3Ch ; '<'
0x18006c687  mov     [rsp+0C8h+var_A8], ebx
0x18006c68b  jmp     loc_18006CA04
0x18006c690  mov     rdi, [rsp+0C8h+var_78]
0x18006c695  mov     eax, 0FFFFFFFFh
0x18006c69a  cmp     rdi, rax
0x18006c69d  jb      loc_18006C735
0x18006c6a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c6aa  mov     edi, 8000FFFFh
0x18006c6af  mov     ebx, edi
0x18006c6b1  test    rcx, rcx
0x18006c6b4  jnz     short loc_18006C6F7
0x18006c6b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c6bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c6c3  mov     rcx, rax
0x18006c6c6  test    rax, rax
0x18006c6c9  jz      short loc_18006C6E9
0x18006c6cb  mov     rax, [rax]
0x18006c6ce  mov     edx, 7F0h
0x18006c6d3  mov     rax, [rax+8]
0x18006c6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6dc  test    eax, eax
0x18006c6de  jz      short loc_18006C6E9
0x18006c6e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c6e7  jmp     short loc_18006C6F7
0x18006c6e9  lea     rcx, qword_1800D6F70; this
0x18006c6f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c6f7  cmp     byte ptr [rcx+8], 0
0x18006c6fb  jz      short loc_18006C71E
0x18006c6fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c702  cmp     [rax+7CCh], edi
0x18006c708  jz      short loc_18006C71E
0x18006c70a  mov     r9d, edi; int
0x18006c70d  mov     r8d, 289h; int
0x18006c713  mov     rdx, r12; char *
0x18006c716  mov     rcx, rax; this
0x18006c719  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c71e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c725  jb      loc_18006CA1E
0x18006c72b  mov     edx, 3Dh ; '='
0x18006c730  jmp     loc_18006CA00
0x18006c735  lea     eax, [rdi+2Fh]
0x18006c738  cmp     eax, 2Fh ; '/'
0x18006c73b  jnb     loc_18006C7D1
0x18006c741  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c748  mov     ebx, 80070216h
0x18006c74d  test    rcx, rcx
0x18006c750  jnz     short loc_18006C793
0x18006c752  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c758  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c75f  mov     rcx, rax
0x18006c762  test    rax, rax
0x18006c765  jz      short loc_18006C785
0x18006c767  mov     rax, [rax]
0x18006c76a  mov     edx, 7F0h
0x18006c76f  mov     rax, [rax+8]
0x18006c773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c778  test    eax, eax
0x18006c77a  jz      short loc_18006C785
0x18006c77c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c783  jmp     short loc_18006C793
0x18006c785  lea     rcx, qword_1800D6F70; this
0x18006c78c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c793  cmp     byte ptr [rcx+8], 0
0x18006c797  jz      short loc_18006C7BA
0x18006c799  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c79e  cmp     [rax+7CCh], ebx
0x18006c7a4  jz      short loc_18006C7BA
0x18006c7a6  mov     r9d, ebx; int
0x18006c7a9  mov     r8d, 28Eh; int
0x18006c7af  mov     rdx, r12; char *
0x18006c7b2  mov     rcx, rax; this
0x18006c7b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c7ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c7c1  jb      loc_18006CA1E
0x18006c7c7  mov     edx, 3Eh ; '>'
0x18006c7cc  jmp     loc_18006C687
0x18006c7d1  mov     r13d, 41h ; 'A'
0x18006c7d7  mov     ecx, eax; cb
0x18006c7d9  mov     [rsi+78h], r13w
0x18006c7de  mov     [rsi+80h], eax
0x18006c7e4  call    cs:__imp_CoTaskMemAlloc
0x18006c7ea  mov     [rsi+88h], rax
0x18006c7f1  mov     rdx, rax
0x18006c7f4  test    rax, rax
0x18006c7f7  jnz     loc_18006C88D
0x18006c7fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c804  mov     ebx, 8007000Eh
0x18006c809  test    rcx, rcx
0x18006c80c  jnz     short loc_18006C84F
0x18006c80e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c814  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c81b  mov     rcx, rax
0x18006c81e  test    rax, rax
0x18006c821  jz      short loc_18006C841
0x18006c823  mov     rax, [rax]
0x18006c826  mov     edx, 7F0h
0x18006c82b  mov     rax, [rax+8]
0x18006c82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c834  test    eax, eax
0x18006c836  jz      short loc_18006C841
0x18006c838  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c83f  jmp     short loc_18006C84F
0x18006c841  lea     rcx, qword_1800D6F70; this
0x18006c848  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c84f  cmp     byte ptr [rcx+8], 0
0x18006c853  jz      short loc_18006C876
0x18006c855  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c85a  cmp     [rax+7CCh], ebx
0x18006c860  jz      short loc_18006C876
0x18006c862  mov     r9d, ebx; int
0x18006c865  mov     r8d, 298h; int
0x18006c86b  mov     rdx, r12; char *
0x18006c86e  mov     rcx, rax; this
0x18006c871  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c876  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c87d  jb      loc_18006CA1E
0x18006c883  mov     edx, 3Fh ; '?'
0x18006c888  jmp     loc_18006C687
0x18006c88d  mov     byte ptr [rax], 3
0x18006c890  lea     r9, [rsp+0C8h+var_94]
0x18006c895  mov     [rax+1], edi
0x18006c898  mov     r8d, edi
0x18006c89b  movups  xmm0, xmmword ptr cs:aImageJpeg; "image/jpeg"
0x18006c8a2  mov     rcx, r14
0x18006c8a5  movups  xmmword ptr [rax+5], xmm0
0x18006c8a9  movsd   xmm1, qword ptr cs:aImageJpeg+0Eh; "peg"
0x18006c8b1  movsd   qword ptr [rax+13h], xmm1
0x18006c8b6  movups  xmm0, xmmword ptr cs:aThumbnail; "thumbnail"
0x18006c8bd  movups  xmmword ptr [rax+1Bh], xmm0
0x18006c8c1  mov     eax, dword ptr cs:aThumbnail+10h; "l"
0x18006c8c7  mov     [rdx+2Bh], eax
0x18006c8ca  add     rdx, 2Fh ; '/'
0x18006c8ce  mov     rax, [r14]
0x18006c8d1  mov     rax, [rax+18h]
0x18006c8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8da  mov     ebx, eax
0x18006c8dc  test    eax, eax
0x18006c8de  jns     loc_18006C96F
0x18006c8e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8eb  test    rcx, rcx
0x18006c8ee  jnz     short loc_18006C931
0x18006c8f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c8f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8fd  mov     rcx, rax
0x18006c900  test    rax, rax
0x18006c903  jz      short loc_18006C923
0x18006c905  mov     rax, [rax]
0x18006c908  mov     edx, 7F0h
0x18006c90d  mov     rax, [rax+8]
0x18006c911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c916  test    eax, eax
0x18006c918  jz      short loc_18006C923
0x18006c91a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c921  jmp     short loc_18006C931
0x18006c923  lea     rcx, qword_1800D6F70; this
0x18006c92a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c931  cmp     byte ptr [rcx+8], 0
0x18006c935  jz      short loc_18006C958
0x18006c937  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c93c  cmp     [rax+7CCh], ebx
0x18006c942  jz      short loc_18006C958
0x18006c944  mov     r9d, ebx; int
0x18006c947  mov     r8d, 2ADh; int
0x18006c94d  mov     rdx, r12; char *
0x18006c950  mov     rcx, rax; this
0x18006c953  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c958  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c95f  jb      loc_18006CA1E
0x18006c965  mov     edx, 40h ; '@'
0x18006c96a  jmp     loc_18006C687
0x18006c96f  cmp     [rsp+0C8h+var_94], edi
0x18006c973  jz      loc_18006CA28
0x18006c979  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c980  mov     edi, 8000FFFFh
0x18006c985  mov     ebx, edi
0x18006c987  test    rcx, rcx
0x18006c98a  jnz     short loc_18006C9CD
0x18006c98c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c992  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c999  mov     rcx, rax
0x18006c99c  test    rax, rax
0x18006c99f  jz      short loc_18006C9BF
0x18006c9a1  mov     rax, [rax]
0x18006c9a4  mov     edx, 7F0h
0x18006c9a9  mov     rax, [rax+8]
0x18006c9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9b2  test    eax, eax
0x18006c9b4  jz      short loc_18006C9BF
0x18006c9b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c9bd  jmp     short loc_18006C9CD
0x18006c9bf  lea     rcx, qword_1800D6F70; this
0x18006c9c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c9cd  cmp     byte ptr [rcx+8], 0
0x18006c9d1  jz      short loc_18006C9F4
0x18006c9d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c9d8  cmp     [rax+7CCh], edi
0x18006c9de  jz      short loc_18006C9F4
0x18006c9e0  mov     r9d, edi; int
0x18006c9e3  mov     r8d, 2B1h; int
0x18006c9e9  mov     rdx, r12; char *
0x18006c9ec  mov     rcx, rax; this
0x18006c9ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c9f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c9fb  jb      short loc_18006CA1E
0x18006c9fd  mov     edx, r13d
0x18006ca00  mov     [rsp+0C8h+var_A8], edi
0x18006ca04  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca0b  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18006ca12  mov     r9, rsi
0x18006ca15  mov     rcx, [rcx+10h]
0x18006ca19  call    WPP_SF_qD
0x18006ca1e  lea     rcx, [rsi+78h]; pvar
0x18006ca22  call    cs:__imp_PropVariantClear
0x18006ca28  lea     rcx, [rsp+0C8h+var_98]; this
0x18006ca2d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006ca32  mov     eax, ebx
0x18006ca34  mov     rcx, [rsp+0C8h+var_38]
0x18006ca3c  xor     rcx, rsp; StackCookie
0x18006ca3f  call    __security_check_cookie
0x18006ca44  mov     rbx, [rsp+0C8h+arg_10]
0x18006ca4c  add     rsp, 0A0h
0x18006ca53  pop     r14
0x18006ca55  pop     r13
0x18006ca57  pop     r12
0x18006ca59  pop     rdi
0x18006ca5a  pop     rsi
0x18006ca5b  retn
```
