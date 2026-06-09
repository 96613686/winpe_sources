# CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)

- ea: `0x1800771e4`
- end: `0x1800775aa`
- name: `?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180077fb4`

## callees

- `0x1800023e0`
- `0x180002d90`
- `0x180002df0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800771e4`
- `0x1800775b0`
- `0x180079614`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800772f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800774b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800772f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800774b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007726b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800773a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800774dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007726b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800773a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077436`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800774dc`

## string_xrefs

- `0x18007720e`: `CreateMediaSubTypeFromMap`

## pseudocode

```c
__int64 __fastcall CreateMediaSubTypeFromMap(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rcx
  const wchar_t *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned __int16 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  _BYTE v41[8]; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  size_t PtNumOfCharConverted; // [rsp+40h] [rbp-20h] BYREF
  char Dst[8]; // [rsp+48h] [rbp-18h] BYREF

  string = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v41, "CreateMediaSubTypeFromMap", 180);
  WindowsDeleteString(string);
  string = 0;
  v8 = CreateStringFromMap(a1, L"@SubType", &string);
  if ( v8 < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateMediaSubTypeFromMap", 180, v8);
    }
    if ( g_wppLevels )
    {
      v14 = 25;
LABEL_54:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v16 = -1;
  do
    ++v16;
  while ( StringRawBuffer[v16] );
  if ( v16 == 4 )
  {
    PtNumOfCharConverted = 0;
    v17 = WindowsGetStringRawBuffer(string, 0);
    if ( wcstombs_s(&PtNumOfCharConverted, Dst, 5u, v17, 4u) )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
        if ( *((_DWORD *)v32 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v32, "CreateMediaSubTypeFromMap", 210, -1072875845);
      }
      if ( !g_wppLevels )
        goto LABEL_55;
      v29 = 27;
    }
    else
    {
      v21 = *a3 - *(_QWORD *)&MFMediaType_Video.Data1;
      if ( *a3 == *(_QWORD *)&MFMediaType_Video.Data1 )
        v21 = a3[1] - *(_QWORD *)MFMediaType_Video.Data4;
      if ( !v21 )
      {
        v22 = *(_DWORD *)Dst;
LABEL_20:
        *(_DWORD *)a4 = v22;
        *(_DWORD *)(a4 + 4) = 0x100000;
        *(_DWORD *)(a4 + 8) = -1442840448;
        *(_DWORD *)(a4 + 12) = 1905997824;
        goto LABEL_55;
      }
      v22 = o_atoi_0(Dst);
      if ( v22 >= 0 )
        goto LABEL_20;
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v28, "CreateMediaSubTypeFromMap", 202, -1072875845);
      }
      if ( !g_wppLevels )
        goto LABEL_55;
      v29 = 26;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, -1072875845);
    goto LABEL_55;
  }
  v33 = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  v8 = GUIDFromString(v33, (struct _GUID *)a4);
  if ( v8 < 0 )
  {
    v37 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v39 + 499) != v8 )
        CallStackContext::TraceFailure(v39, "CreateMediaSubTypeFromMap", 215, v8);
    }
    if ( g_wppLevels )
    {
      v14 = 28;
      goto LABEL_54;
    }
  }
LABEL_55:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800771e4  mov     [rsp-28h+arg_8], rbx
0x1800771e9  mov     [rsp-28h+arg_10], rsi
0x1800771ee  push    rbp
0x1800771ef  push    rdi
0x1800771f0  push    r12
0x1800771f2  push    r14
0x1800771f4  push    r15
0x1800771f6  mov     rbp, rsp
0x1800771f9  sub     rsp, 60h
0x1800771fd  mov     rax, cs:__security_cookie
0x180077204  xor     rax, rsp
0x180077207  mov     [rbp+var_10], rax
0x18007720b  mov     r14, r8
0x18007720e  lea     r12, aCreatemediasub; "CreateMediaSubTypeFromMap"
0x180077215  mov     rbx, rcx
0x180077218  xor     r15d, r15d
0x18007721b  mov     rdx, r12; char *
0x18007721e  mov     [rbp+string], r15
0x180077222  mov     r8d, 0B4h; int
0x180077228  lea     rcx, [rbp+var_30]; this
0x18007722c  mov     rdi, r9
0x18007722f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180077234  mov     rcx, [rbp+string]; string
0x180077238  call    cs:__imp_WindowsDeleteString
0x18007723e  lea     r8, [rbp+string]
0x180077242  mov     [rbp+string], r15
0x180077246  lea     rdx, aSubtype; "@SubType"
0x18007724d  mov     rcx, rbx
0x180077250  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180077255  mov     esi, eax
0x180077257  test    eax, eax
0x180077259  jns     loc_1800772EA
0x18007725f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077266  test    rcx, rcx
0x180077269  jnz     short loc_1800772AC
0x18007726b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077271  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077278  mov     rcx, rax
0x18007727b  test    rax, rax
0x18007727e  jz      short loc_18007729E
0x180077280  mov     rax, [rax]
0x180077283  mov     edx, 7F0h
0x180077288  mov     rax, [rax+8]
0x18007728c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077291  test    eax, eax
0x180077293  jz      short loc_18007729E
0x180077295  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007729c  jmp     short loc_1800772AC
0x18007729e  lea     rcx, qword_1800D6F70; this
0x1800772a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800772ac  cmp     [rcx+8], r15b
0x1800772b0  jz      short loc_1800772D3
0x1800772b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800772b7  cmp     [rax+7CCh], esi
0x1800772bd  jz      short loc_1800772D3
0x1800772bf  mov     r9d, esi; int
0x1800772c2  mov     r8d, 0B4h; int
0x1800772c8  mov     rdx, r12; char *
0x1800772cb  mov     rcx, rax; this
0x1800772ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800772d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800772da  jb      loc_180077570
0x1800772e0  mov     edx, 19h
0x1800772e5  jmp     loc_180077552
0x1800772ea  mov     rcx, [rbp+string]; string
0x1800772ee  xor     edx, edx; length
0x1800772f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800772f6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800772fa  inc     rcx
0x1800772fd  cmp     [rax+rcx*2], r15w
0x180077302  jnz     short loc_1800772FA
0x180077304  xor     edx, edx; length
0x180077306  cmp     rcx, 4
0x18007730a  mov     rcx, [rbp+string]; string
0x18007730e  jnz     loc_1800774B5
0x180077314  mov     [rbp+PtNumOfCharConverted], r15
0x180077318  call    cs:__imp_WindowsGetStringRawBuffer
0x18007731e  mov     r8d, 5; DstSizeInBytes
0x180077324  mov     [rsp+60h+MaxCountInBytes], 4; MaxCountInBytes
0x18007732d  mov     r9, rax; Src
0x180077330  lea     rdx, [rbp+Dst]; Dst
0x180077334  lea     rcx, [rbp+PtNumOfCharConverted]; PtNumOfCharConverted
0x180077338  call    wcstombs_s
0x18007733d  test    eax, eax
0x18007733f  jnz     loc_180077423
0x180077345  mov     rax, [r14]
0x180077348  sub     rax, qword ptr cs:MFMediaType_Video.Data1
0x18007734f  jnz     short loc_18007735C
0x180077351  mov     rax, [r14+8]
0x180077355  sub     rax, qword ptr cs:MFMediaType_Video.Data4
0x18007735c  test    rax, rax
0x18007735f  jnz     short loc_180077380
0x180077361  mov     eax, dword ptr [rbp+Dst]
0x180077364  mov     [rdi], eax
0x180077366  mov     dword ptr [rdi+4], 100000h
0x18007736d  mov     dword ptr [rdi+8], 0AA000080h
0x180077374  mov     dword ptr [rdi+0Ch], 719B3800h
0x18007737b  jmp     loc_180077570
0x180077380  lea     rcx, [rbp+Dst]; String
0x180077384  call    _o_atoi_0
0x180077389  test    eax, eax
0x18007738b  jns     short loc_180077364
0x18007738d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077394  mov     ebx, 0C00D36BBh
0x180077399  mov     esi, ebx
0x18007739b  test    rcx, rcx
0x18007739e  jnz     short loc_1800773E1
0x1800773a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800773a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773ad  mov     rcx, rax
0x1800773b0  test    rax, rax
0x1800773b3  jz      short loc_1800773D3
0x1800773b5  mov     rax, [rax]
0x1800773b8  mov     edx, 7F0h
0x1800773bd  mov     rax, [rax+8]
0x1800773c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773c6  test    eax, eax
0x1800773c8  jz      short loc_1800773D3
0x1800773ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773d1  jmp     short loc_1800773E1
0x1800773d3  lea     rcx, qword_1800D6F70; this
0x1800773da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800773e1  cmp     [rcx+8], r15b
0x1800773e5  jz      short loc_180077408
0x1800773e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800773ec  cmp     [rax+7CCh], ebx
0x1800773f2  jz      short loc_180077408
0x1800773f4  mov     r9d, ebx; int
0x1800773f7  mov     r8d, 0CAh; int
0x1800773fd  mov     rdx, r12; char *
0x180077400  mov     rcx, rax; this
0x180077403  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077408  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007740f  jb      loc_180077570
0x180077415  mov     edx, 1Ah
0x18007741a  mov     dword ptr [rsp+60h+MaxCountInBytes], ebx
0x18007741e  jmp     loc_180077556
0x180077423  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007742a  mov     ebx, 0C00D36BBh
0x18007742f  mov     esi, ebx
0x180077431  test    rcx, rcx
0x180077434  jnz     short loc_180077477
0x180077436  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007743c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077443  mov     rcx, rax
0x180077446  test    rax, rax
0x180077449  jz      short loc_180077469
0x18007744b  mov     rax, [rax]
0x18007744e  mov     edx, 7F0h
0x180077453  mov     rax, [rax+8]
0x180077457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007745c  test    eax, eax
0x18007745e  jz      short loc_180077469
0x180077460  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077467  jmp     short loc_180077477
0x180077469  lea     rcx, qword_1800D6F70; this
0x180077470  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077477  cmp     [rcx+8], r15b
0x18007747b  jz      short loc_18007749E
0x18007747d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077482  cmp     [rax+7CCh], ebx
0x180077488  jz      short loc_18007749E
0x18007748a  mov     r9d, ebx; int
0x18007748d  mov     r8d, 0D2h; int
0x180077493  mov     rdx, r12; char *
0x180077496  mov     rcx, rax; this
0x180077499  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007749e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800774a5  jb      loc_180077570
0x1800774ab  mov     edx, 1Bh
0x1800774b0  jmp     loc_18007741A
0x1800774b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800774bb  mov     rcx, rax; unsigned __int16 *
0x1800774be  mov     rdx, rdi; struct _GUID *
0x1800774c1  call    ?GUIDFromString@@YAJPEAGPEAU_GUID@@@Z; GUIDFromString(ushort *,_GUID *)
0x1800774c6  mov     esi, eax
0x1800774c8  test    eax, eax
0x1800774ca  jns     loc_180077570
0x1800774d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800774d7  test    rcx, rcx
0x1800774da  jnz     short loc_18007751D
0x1800774dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800774e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800774e9  mov     rcx, rax
0x1800774ec  test    rax, rax
0x1800774ef  jz      short loc_18007750F
0x1800774f1  mov     rax, [rax]
0x1800774f4  mov     edx, 7F0h
0x1800774f9  mov     rax, [rax+8]
0x1800774fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077502  test    eax, eax
0x180077504  jz      short loc_18007750F
0x180077506  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007750d  jmp     short loc_18007751D
0x18007750f  lea     rcx, qword_1800D6F70; this
0x180077516  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007751d  cmp     [rcx+8], r15b
0x180077521  jz      short loc_180077544
0x180077523  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077528  cmp     [rax+7CCh], esi
0x18007752e  jz      short loc_180077544
0x180077530  mov     r9d, esi; int
0x180077533  mov     r8d, 0D7h; int
0x180077539  mov     rdx, r12; char *
0x18007753c  mov     rcx, rax; this
0x18007753f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077544  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007754b  jb      short loc_180077570
0x18007754d  mov     edx, 1Ch
0x180077552  mov     dword ptr [rsp+60h+MaxCountInBytes], esi
0x180077556  mov     rcx, cs:WPP_GLOBAL_Control
0x18007755d  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180077564  xor     r9d, r9d
0x180077567  mov     rcx, [rcx+10h]
0x18007756b  call    WPP_SF_qD
0x180077570  lea     rcx, [rbp+var_30]; this
0x180077574  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180077579  mov     rcx, [rbp+string]; string
0x18007757d  call    cs:__imp_WindowsDeleteString
0x180077583  mov     eax, esi
0x180077585  mov     rcx, [rbp+var_10]
0x180077589  xor     rcx, rsp; StackCookie
0x18007758c  call    __security_check_cookie
0x180077591  lea     r11, [rsp+60h+var_s0]
0x180077596  mov     rbx, [r11+38h]
0x18007759a  mov     rsi, [r11+40h]
0x18007759e  mov     rsp, r11
0x1800775a1  pop     r15
0x1800775a3  pop     r14
0x1800775a5  pop     r12
0x1800775a7  pop     rdi
0x1800775a8  pop     rbp
0x1800775a9  retn
```
