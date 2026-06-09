# CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)

- ea: `0x1800ca854`
- end: `0x1800cac07`
- name: `?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001976c`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018a4c`
- `0x18003639c`
- `0x180054140`
- `0x180054ddc`
- `0x180054e90`
- `0x1800ca338`
- `0x1800ca854`
- `0x1800cfec0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cabdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cabdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cab17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cab17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca8d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cab3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca8d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cab3e`

## string_xrefs

- `0x1800ca878`: `CreateMediaSubTypeFromMap`

## pseudocode

```c
__int64 __fastcall CreateMediaSubTypeFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // esi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  int v14; // eax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned __int16 *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  _BYTE v27[8]; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  size_t PtNumOfCharConverted; // [rsp+40h] [rbp-20h] BYREF
  char Dst[8]; // [rsp+48h] [rbp-18h] BYREF

  string = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v27, "CreateMediaSubTypeFromMap", 180);
  WindowsDeleteString(string);
  string = 0;
  v6 = CreateStringFromMap(a1, L"@SubType", &string);
  if ( v6 < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateMediaSubTypeFromMap", 180, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 25;
LABEL_52:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v6);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = -1;
  do
    ++v12;
  while ( StringRawBuffer[v12] );
  if ( v12 == 4 )
  {
    PtNumOfCharConverted = 0;
    v13 = WindowsGetStringRawBuffer(string, 0);
    if ( wcstombs_s(&PtNumOfCharConverted, Dst, 5u, v13, 4u) )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      v6 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v21, "CreateMediaSubTypeFromMap", 210, -1072875845);
      }
      if ( !g_wppLevels )
        goto LABEL_53;
      v18 = 27;
    }
    else
    {
      if ( !memcmp_0(&MFMediaType_Video, &MFMediaType_Video, 0x10u) )
      {
        v14 = *(_DWORD *)Dst;
LABEL_18:
        *(_DWORD *)a4 = v14;
        *(_DWORD *)(a4 + 4) = 0x100000;
        *(_DWORD *)(a4 + 8) = -1442840448;
        *(_DWORD *)(a4 + 12) = 1905997824;
        goto LABEL_53;
      }
      v14 = o_atoi_0(Dst);
      if ( v14 >= 0 )
        goto LABEL_18;
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      v6 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v17, "CreateMediaSubTypeFromMap", 202, -1072875845);
      }
      if ( !g_wppLevels )
        goto LABEL_53;
      v18 = 26;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, -1072875845);
    goto LABEL_53;
  }
  v22 = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  v6 = GUIDFromString(v22, (struct _GUID *)a4);
  if ( v6 < 0 )
  {
    v23 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != v6 )
        CallStackContext::TraceFailure(v25, "CreateMediaSubTypeFromMap", 215, v6);
    }
    if ( g_wppLevels )
    {
      v10 = 28;
      goto LABEL_52;
    }
  }
LABEL_53:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
  WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ca854  mov     [rsp-28h+arg_8], rbx
0x1800ca859  push    rbp
0x1800ca85a  push    rsi
0x1800ca85b  push    rdi
0x1800ca85c  push    r14
0x1800ca85e  push    r15
0x1800ca860  mov     rbp, rsp
0x1800ca863  sub     rsp, 60h
0x1800ca867  mov     rax, cs:__security_cookie
0x1800ca86e  xor     rax, rsp
0x1800ca871  mov     [rbp+var_10], rax
0x1800ca875  mov     rbx, rcx
0x1800ca878  lea     r15, aCreatemediasub; "CreateMediaSubTypeFromMap"
0x1800ca87f  xor     r14d, r14d
0x1800ca882  lea     rcx, [rbp+var_30]; this
0x1800ca886  mov     rdx, r15; char *
0x1800ca889  mov     [rbp+string], r14
0x1800ca88d  mov     r8d, 0B4h; int
0x1800ca893  mov     rdi, r9
0x1800ca896  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ca89b  mov     rcx, [rbp+string]; string
0x1800ca89f  call    cs:__imp_WindowsDeleteString
0x1800ca8a5  lea     r8, [rbp+string]
0x1800ca8a9  mov     [rbp+string], r14
0x1800ca8ad  lea     rdx, aSubtype; "@SubType"
0x1800ca8b4  mov     rcx, rbx
0x1800ca8b7  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800ca8bc  mov     esi, eax
0x1800ca8be  test    eax, eax
0x1800ca8c0  jns     loc_1800CA951
0x1800ca8c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8cd  test    rcx, rcx
0x1800ca8d0  jnz     short loc_1800CA913
0x1800ca8d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca8d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8df  mov     rcx, rax
0x1800ca8e2  test    rax, rax
0x1800ca8e5  jz      short loc_1800CA905
0x1800ca8e7  mov     rax, [rax]
0x1800ca8ea  mov     edx, 7F0h
0x1800ca8ef  mov     rax, [rax+8]
0x1800ca8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca8f8  test    eax, eax
0x1800ca8fa  jz      short loc_1800CA905
0x1800ca8fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca903  jmp     short loc_1800CA913
0x1800ca905  lea     rcx, qword_180153440; this
0x1800ca90c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca913  cmp     [rcx+8], r14b
0x1800ca917  jz      short loc_1800CA93A
0x1800ca919  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca91e  cmp     [rax+7CCh], esi
0x1800ca924  jz      short loc_1800CA93A
0x1800ca926  mov     r9d, esi; int
0x1800ca929  mov     r8d, 0B4h; int
0x1800ca92f  mov     rdx, r15; char *
0x1800ca932  mov     rcx, rax; this
0x1800ca935  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca93a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca941  jb      loc_1800CABD2
0x1800ca947  mov     edx, 19h
0x1800ca94c  jmp     loc_1800CABB4
0x1800ca951  mov     rcx, [rbp+string]; string
0x1800ca955  xor     edx, edx; length
0x1800ca957  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca95d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ca961  inc     rcx
0x1800ca964  cmp     [rax+rcx*2], r14w
0x1800ca969  jnz     short loc_1800CA961
0x1800ca96b  xor     edx, edx; length
0x1800ca96d  cmp     rcx, 4
0x1800ca971  mov     rcx, [rbp+string]; string
0x1800ca975  jnz     loc_1800CAB17
0x1800ca97b  mov     [rbp+PtNumOfCharConverted], r14
0x1800ca97f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca985  mov     r8d, 5; DstSizeInBytes
0x1800ca98b  mov     [rsp+60h+MaxCountInBytes], 4; MaxCountInBytes
0x1800ca994  mov     r9, rax; Src
0x1800ca997  lea     rdx, [rbp+Dst]; Dst
0x1800ca99b  lea     rcx, [rbp+PtNumOfCharConverted]; PtNumOfCharConverted
0x1800ca99f  call    wcstombs_s
0x1800ca9a4  test    eax, eax
0x1800ca9a6  jnz     loc_1800CAA85
0x1800ca9ac  lea     rcx, MFMediaType_Video; Buf1
0x1800ca9b3  mov     rdx, rcx; Buf2
0x1800ca9b6  lea     r8d, [rax+10h]; Size
0x1800ca9ba  call    memcmp_0
0x1800ca9bf  test    eax, eax
0x1800ca9c1  jnz     short loc_1800CA9E2
0x1800ca9c3  mov     eax, dword ptr [rbp+Dst]
0x1800ca9c6  mov     [rdi], eax
0x1800ca9c8  mov     dword ptr [rdi+4], 100000h
0x1800ca9cf  mov     dword ptr [rdi+8], 0AA000080h
0x1800ca9d6  mov     dword ptr [rdi+0Ch], 719B3800h
0x1800ca9dd  jmp     loc_1800CABD2
0x1800ca9e2  lea     rcx, [rbp+Dst]; String
0x1800ca9e6  call    _o_atoi_0
0x1800ca9eb  test    eax, eax
0x1800ca9ed  jns     short loc_1800CA9C6
0x1800ca9ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9f6  mov     ebx, 0C00D36BBh
0x1800ca9fb  mov     esi, ebx
0x1800ca9fd  test    rcx, rcx
0x1800caa00  jnz     short loc_1800CAA43
0x1800caa02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800caa08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa0f  mov     rcx, rax
0x1800caa12  test    rax, rax
0x1800caa15  jz      short loc_1800CAA35
0x1800caa17  mov     rax, [rax]
0x1800caa1a  mov     edx, 7F0h
0x1800caa1f  mov     rax, [rax+8]
0x1800caa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caa28  test    eax, eax
0x1800caa2a  jz      short loc_1800CAA35
0x1800caa2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa33  jmp     short loc_1800CAA43
0x1800caa35  lea     rcx, qword_180153440; this
0x1800caa3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa43  cmp     [rcx+8], r14b
0x1800caa47  jz      short loc_1800CAA6A
0x1800caa49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800caa4e  cmp     [rax+7CCh], ebx
0x1800caa54  jz      short loc_1800CAA6A
0x1800caa56  mov     r9d, ebx; int
0x1800caa59  mov     r8d, 0CAh; int
0x1800caa5f  mov     rdx, r15; char *
0x1800caa62  mov     rcx, rax; this
0x1800caa65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800caa6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caa71  jb      loc_1800CABD2
0x1800caa77  mov     edx, 1Ah
0x1800caa7c  mov     dword ptr [rsp+60h+MaxCountInBytes], ebx
0x1800caa80  jmp     loc_1800CABB8
0x1800caa85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa8c  mov     ebx, 0C00D36BBh
0x1800caa91  mov     esi, ebx
0x1800caa93  test    rcx, rcx
0x1800caa96  jnz     short loc_1800CAAD9
0x1800caa98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800caa9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caaa5  mov     rcx, rax
0x1800caaa8  test    rax, rax
0x1800caaab  jz      short loc_1800CAACB
0x1800caaad  mov     rax, [rax]
0x1800caab0  mov     edx, 7F0h
0x1800caab5  mov     rax, [rax+8]
0x1800caab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caabe  test    eax, eax
0x1800caac0  jz      short loc_1800CAACB
0x1800caac2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caac9  jmp     short loc_1800CAAD9
0x1800caacb  lea     rcx, qword_180153440; this
0x1800caad2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caad9  cmp     [rcx+8], r14b
0x1800caadd  jz      short loc_1800CAB00
0x1800caadf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800caae4  cmp     [rax+7CCh], ebx
0x1800caaea  jz      short loc_1800CAB00
0x1800caaec  mov     r9d, ebx; int
0x1800caaef  mov     r8d, 0D2h; int
0x1800caaf5  mov     rdx, r15; char *
0x1800caaf8  mov     rcx, rax; this
0x1800caafb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cab00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cab07  jb      loc_1800CABD2
0x1800cab0d  mov     edx, 1Bh
0x1800cab12  jmp     loc_1800CAA7C
0x1800cab17  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cab1d  mov     rcx, rax; unsigned __int16 *
0x1800cab20  mov     rdx, rdi; struct _GUID *
0x1800cab23  call    ?GUIDFromString@@YAJPEAGPEAU_GUID@@@Z; GUIDFromString(ushort *,_GUID *)
0x1800cab28  mov     esi, eax
0x1800cab2a  test    eax, eax
0x1800cab2c  jns     loc_1800CABD2
0x1800cab32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cab39  test    rcx, rcx
0x1800cab3c  jnz     short loc_1800CAB7F
0x1800cab3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cab44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cab4b  mov     rcx, rax
0x1800cab4e  test    rax, rax
0x1800cab51  jz      short loc_1800CAB71
0x1800cab53  mov     rax, [rax]
0x1800cab56  mov     edx, 7F0h
0x1800cab5b  mov     rax, [rax+8]
0x1800cab5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cab64  test    eax, eax
0x1800cab66  jz      short loc_1800CAB71
0x1800cab68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cab6f  jmp     short loc_1800CAB7F
0x1800cab71  lea     rcx, qword_180153440; this
0x1800cab78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cab7f  cmp     [rcx+8], r14b
0x1800cab83  jz      short loc_1800CABA6
0x1800cab85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cab8a  cmp     [rax+7CCh], esi
0x1800cab90  jz      short loc_1800CABA6
0x1800cab92  mov     r9d, esi; int
0x1800cab95  mov     r8d, 0D7h; int
0x1800cab9b  mov     rdx, r15; char *
0x1800cab9e  mov     rcx, rax; this
0x1800caba1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800caba6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cabad  jb      short loc_1800CABD2
0x1800cabaf  mov     edx, 1Ch
0x1800cabb4  mov     dword ptr [rsp+60h+MaxCountInBytes], esi
0x1800cabb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cabbf  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800cabc6  xor     r9d, r9d
0x1800cabc9  mov     rcx, [rcx+10h]
0x1800cabcd  call    WPP_SF_qD
0x1800cabd2  lea     rcx, [rbp+var_30]; this
0x1800cabd6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cabdb  mov     rcx, [rbp+string]; string
0x1800cabdf  call    cs:__imp_WindowsDeleteString
0x1800cabe5  mov     eax, esi
0x1800cabe7  mov     rcx, [rbp+var_10]
0x1800cabeb  xor     rcx, rsp; StackCookie
0x1800cabee  call    __security_check_cookie
0x1800cabf3  mov     rbx, [rsp+60h+arg_8]
0x1800cabfb  add     rsp, 60h
0x1800cabff  pop     r15
0x1800cac01  pop     r14
0x1800cac03  pop     rdi
0x1800cac04  pop     rsi
0x1800cac05  pop     rbp
0x1800cac06  retn
```
