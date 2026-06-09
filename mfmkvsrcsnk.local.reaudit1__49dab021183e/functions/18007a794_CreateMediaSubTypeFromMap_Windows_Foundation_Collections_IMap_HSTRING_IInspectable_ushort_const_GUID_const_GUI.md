# CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)

- ea: `0x18007a794`
- end: `0x18007ab91`
- name: `?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18007b64c`

## callees

- `0x180002400`
- `0x180002dd0`
- `0x180002e30`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18007a794`
- `0x18007ab98`
- `0x18007cd8c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a7e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ab5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a7e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ab5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a8ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aa89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a8ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007a8da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aa89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a821`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a968`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aa04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aab6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a821`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a968`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aa04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aab6`

## string_xrefs

- `0x18007a7be`: `CreateMediaSubTypeFromMap`

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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v26 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v37 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18007a794  mov     [rsp-28h+arg_8], rbx
0x18007a799  mov     [rsp-28h+arg_10], rsi
0x18007a79e  push    rbp
0x18007a79f  push    rdi
0x18007a7a0  push    r12
0x18007a7a2  push    r14
0x18007a7a4  push    r15
0x18007a7a6  mov     rbp, rsp
0x18007a7a9  sub     rsp, 60h
0x18007a7ad  mov     rax, cs:__security_cookie
0x18007a7b4  xor     rax, rsp
0x18007a7b7  mov     [rbp+var_10], rax
0x18007a7bb  mov     r14, r8
0x18007a7be  lea     r12, aCreatemediasub; "CreateMediaSubTypeFromMap"
0x18007a7c5  mov     rbx, rcx
0x18007a7c8  xor     r15d, r15d
0x18007a7cb  mov     rdx, r12; char *
0x18007a7ce  mov     [rbp+string], r15
0x18007a7d2  mov     r8d, 0B4h; int
0x18007a7d8  lea     rcx, [rbp+var_30]; this
0x18007a7dc  mov     rdi, r9
0x18007a7df  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007a7e4  mov     rcx, [rbp+string]; string
0x18007a7e8  call    cs:__imp_WindowsDeleteString
0x18007a7ef  nop     dword ptr [rax+rax+00h]
0x18007a7f4  lea     r8, [rbp+string]
0x18007a7f8  mov     [rbp+string], r15
0x18007a7fc  lea     rdx, aSubtype; "@SubType"
0x18007a803  mov     rcx, rbx
0x18007a806  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007a80b  mov     esi, eax
0x18007a80d  test    eax, eax
0x18007a80f  jns     loc_18007A8A6
0x18007a815  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a81c  test    rcx, rcx
0x18007a81f  jnz     short loc_18007A868
0x18007a821  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a828  nop     dword ptr [rax+rax+00h]
0x18007a82d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a834  mov     rcx, rax
0x18007a837  test    rax, rax
0x18007a83a  jz      short loc_18007A85A
0x18007a83c  mov     rax, [rax]
0x18007a83f  mov     edx, 7F0h
0x18007a844  mov     rax, [rax+8]
0x18007a848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a84d  test    eax, eax
0x18007a84f  jz      short loc_18007A85A
0x18007a851  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a858  jmp     short loc_18007A868
0x18007a85a  lea     rcx, qword_1800DBF70; this
0x18007a861  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a868  cmp     [rcx+8], r15b
0x18007a86c  jz      short loc_18007A88F
0x18007a86e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a873  cmp     [rax+7CCh], esi
0x18007a879  jz      short loc_18007A88F
0x18007a87b  mov     r9d, esi; int
0x18007a87e  mov     r8d, 0B4h; int
0x18007a884  mov     rdx, r12; char *
0x18007a887  mov     rcx, rax; this
0x18007a88a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a88f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a896  jb      loc_18007AB50
0x18007a89c  mov     edx, 19h
0x18007a8a1  jmp     loc_18007AB32
0x18007a8a6  mov     rcx, [rbp+string]; string
0x18007a8aa  xor     edx, edx; length
0x18007a8ac  call    cs:__imp_WindowsGetStringRawBuffer
0x18007a8b3  nop     dword ptr [rax+rax+00h]
0x18007a8b8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007a8bc  inc     rcx
0x18007a8bf  cmp     [rax+rcx*2], r15w
0x18007a8c4  jnz     short loc_18007A8BC
0x18007a8c6  xor     edx, edx; length
0x18007a8c8  cmp     rcx, 4
0x18007a8cc  mov     rcx, [rbp+string]; string
0x18007a8d0  jnz     loc_18007AA89
0x18007a8d6  mov     [rbp+PtNumOfCharConverted], r15
0x18007a8da  call    cs:__imp_WindowsGetStringRawBuffer
0x18007a8e1  nop     dword ptr [rax+rax+00h]
0x18007a8e6  mov     r8d, 5; DstSizeInBytes
0x18007a8ec  mov     [rsp+60h+MaxCountInBytes], 4; MaxCountInBytes
0x18007a8f5  mov     r9, rax; Src
0x18007a8f8  lea     rdx, [rbp+Dst]; Dst
0x18007a8fc  lea     rcx, [rbp+PtNumOfCharConverted]; PtNumOfCharConverted
0x18007a900  call    wcstombs_s
0x18007a905  test    eax, eax
0x18007a907  jnz     loc_18007A9F1
0x18007a90d  mov     rax, [r14]
0x18007a910  sub     rax, qword ptr cs:MFMediaType_Video.Data1
0x18007a917  jnz     short loc_18007A924
0x18007a919  mov     rax, [r14+8]
0x18007a91d  sub     rax, qword ptr cs:MFMediaType_Video.Data4
0x18007a924  test    rax, rax
0x18007a927  jnz     short loc_18007A948
0x18007a929  mov     eax, dword ptr [rbp+Dst]
0x18007a92c  mov     [rdi], eax
0x18007a92e  mov     dword ptr [rdi+4], 100000h
0x18007a935  mov     dword ptr [rdi+8], 0AA000080h
0x18007a93c  mov     dword ptr [rdi+0Ch], 719B3800h
0x18007a943  jmp     loc_18007AB50
0x18007a948  lea     rcx, [rbp+Dst]; String
0x18007a94c  call    _o_atoi_0
0x18007a951  test    eax, eax
0x18007a953  jns     short loc_18007A92C
0x18007a955  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a95c  mov     ebx, 0C00D36BBh
0x18007a961  mov     esi, ebx
0x18007a963  test    rcx, rcx
0x18007a966  jnz     short loc_18007A9AF
0x18007a968  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007a96f  nop     dword ptr [rax+rax+00h]
0x18007a974  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a97b  mov     rcx, rax
0x18007a97e  test    rax, rax
0x18007a981  jz      short loc_18007A9A1
0x18007a983  mov     rax, [rax]
0x18007a986  mov     edx, 7F0h
0x18007a98b  mov     rax, [rax+8]
0x18007a98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a994  test    eax, eax
0x18007a996  jz      short loc_18007A9A1
0x18007a998  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a99f  jmp     short loc_18007A9AF
0x18007a9a1  lea     rcx, qword_1800DBF70; this
0x18007a9a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a9af  cmp     [rcx+8], r15b
0x18007a9b3  jz      short loc_18007A9D6
0x18007a9b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007a9ba  cmp     [rax+7CCh], ebx
0x18007a9c0  jz      short loc_18007A9D6
0x18007a9c2  mov     r9d, ebx; int
0x18007a9c5  mov     r8d, 0CAh; int
0x18007a9cb  mov     rdx, r12; char *
0x18007a9ce  mov     rcx, rax; this
0x18007a9d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007a9d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007a9dd  jb      loc_18007AB50
0x18007a9e3  mov     edx, 1Ah
0x18007a9e8  mov     dword ptr [rsp+60h+MaxCountInBytes], ebx
0x18007a9ec  jmp     loc_18007AB36
0x18007a9f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007a9f8  mov     ebx, 0C00D36BBh
0x18007a9fd  mov     esi, ebx
0x18007a9ff  test    rcx, rcx
0x18007aa02  jnz     short loc_18007AA4B
0x18007aa04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007aa0b  nop     dword ptr [rax+rax+00h]
0x18007aa10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa17  mov     rcx, rax
0x18007aa1a  test    rax, rax
0x18007aa1d  jz      short loc_18007AA3D
0x18007aa1f  mov     rax, [rax]
0x18007aa22  mov     edx, 7F0h
0x18007aa27  mov     rax, [rax+8]
0x18007aa2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa30  test    eax, eax
0x18007aa32  jz      short loc_18007AA3D
0x18007aa34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa3b  jmp     short loc_18007AA4B
0x18007aa3d  lea     rcx, qword_1800DBF70; this
0x18007aa44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aa4b  cmp     [rcx+8], r15b
0x18007aa4f  jz      short loc_18007AA72
0x18007aa51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007aa56  cmp     [rax+7CCh], ebx
0x18007aa5c  jz      short loc_18007AA72
0x18007aa5e  mov     r9d, ebx; int
0x18007aa61  mov     r8d, 0D2h; int
0x18007aa67  mov     rdx, r12; char *
0x18007aa6a  mov     rcx, rax; this
0x18007aa6d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007aa72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007aa79  jb      loc_18007AB50
0x18007aa7f  mov     edx, 1Bh
0x18007aa84  jmp     loc_18007A9E8
0x18007aa89  call    cs:__imp_WindowsGetStringRawBuffer
0x18007aa90  nop     dword ptr [rax+rax+00h]
0x18007aa95  mov     rcx, rax; unsigned __int16 *
0x18007aa98  mov     rdx, rdi; struct _GUID *
0x18007aa9b  call    ?GUIDFromString@@YAJPEAGPEAU_GUID@@@Z; GUIDFromString(ushort *,_GUID *)
0x18007aaa0  mov     esi, eax
0x18007aaa2  test    eax, eax
0x18007aaa4  jns     loc_18007AB50
0x18007aaaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aab1  test    rcx, rcx
0x18007aab4  jnz     short loc_18007AAFD
0x18007aab6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007aabd  nop     dword ptr [rax+rax+00h]
0x18007aac2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aac9  mov     rcx, rax
0x18007aacc  test    rax, rax
0x18007aacf  jz      short loc_18007AAEF
0x18007aad1  mov     rax, [rax]
0x18007aad4  mov     edx, 7F0h
0x18007aad9  mov     rax, [rax+8]
0x18007aadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aae2  test    eax, eax
0x18007aae4  jz      short loc_18007AAEF
0x18007aae6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aaed  jmp     short loc_18007AAFD
0x18007aaef  lea     rcx, qword_1800DBF70; this
0x18007aaf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aafd  cmp     [rcx+8], r15b
0x18007ab01  jz      short loc_18007AB24
0x18007ab03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ab08  cmp     [rax+7CCh], esi
0x18007ab0e  jz      short loc_18007AB24
0x18007ab10  mov     r9d, esi; int
0x18007ab13  mov     r8d, 0D7h; int
0x18007ab19  mov     rdx, r12; char *
0x18007ab1c  mov     rcx, rax; this
0x18007ab1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ab24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ab2b  jb      short loc_18007AB50
0x18007ab2d  mov     edx, 1Ch
0x18007ab32  mov     dword ptr [rsp+60h+MaxCountInBytes], esi
0x18007ab36  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ab3d  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007ab44  xor     r9d, r9d
0x18007ab47  mov     rcx, [rcx+10h]
0x18007ab4b  call    WPP_SF_qD
0x18007ab50  lea     rcx, [rbp+var_30]; this
0x18007ab54  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007ab59  mov     rcx, [rbp+string]; string
0x18007ab5d  call    cs:__imp_WindowsDeleteString
0x18007ab64  nop     dword ptr [rax+rax+00h]
0x18007ab69  mov     eax, esi
0x18007ab6b  mov     rcx, [rbp+var_10]
0x18007ab6f  xor     rcx, rsp; StackCookie
0x18007ab72  call    __security_check_cookie
0x18007ab77  lea     r11, [rsp+60h+var_s0]
0x18007ab7c  mov     rbx, [r11+38h]
0x18007ab80  mov     rsi, [r11+40h]
0x18007ab84  mov     rsp, r11
0x18007ab87  pop     r15
0x18007ab89  pop     r14
0x18007ab8b  pop     r12
0x18007ab8d  pop     rdi
0x18007ab8e  pop     rbp
0x18007ab8f  retn
```
