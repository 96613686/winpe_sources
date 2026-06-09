# CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)

- ea: `0x1800390a4`
- end: `0x1800392fa`
- name: `?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800180fc`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180019f84`
- `0x18003639c`
- `0x1800390a4`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039129`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003913d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003913d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003916c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003923e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003916c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003923e`

## string_xrefs

- `0x1800390ce`: `CreateBOOLFromMap`
- `0x1800391c3`: `CreateBOOLFromMap`
- `0x180039295`: `CreateBOOLFromMap`

## pseudocode

```c
__int64 __fastcall CreateBOOLFromMap(__int64 a1, const WCHAR *a2, bool *a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // r14
  unsigned __int64 v7; // rcx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v17; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v18[3]; // [rsp+31h] [rbp-3Fh] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v20 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "CreateBOOLFromMap", 135);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v7 = -1;
  length = 0;
  do
    ++v7;
  while ( a2[v7] );
  if ( (int)ULongLongToULong(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  v8 = v6(a1, string, &v20);
  if ( v8 >= 0 )
  {
    v17 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v20 + 144LL))(v20, &v17);
    if ( v8 >= 0 )
    {
      *a3 = v17 != 0;
      goto LABEL_29;
    }
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateBOOLFromMap", 138, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 21;
      goto LABEL_16;
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CreateBOOLFromMap", 135, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 20;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
    }
  }
LABEL_29:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800390a4  mov     [rsp-28h+arg_18], rbx
0x1800390a9  push    rbp
0x1800390aa  push    rsi
0x1800390ab  push    rdi
0x1800390ac  push    r14
0x1800390ae  push    r15
0x1800390b0  mov     rbp, rsp
0x1800390b3  sub     rsp, 70h
0x1800390b7  mov     rax, cs:__security_cookie
0x1800390be  xor     rax, rsp
0x1800390c1  mov     [rbp+var_10], rax
0x1800390c5  mov     rdi, r8
0x1800390c8  mov     rbx, rdx
0x1800390cb  mov     rsi, rcx
0x1800390ce  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x1800390d5  xor     r15d, r15d
0x1800390d8  lea     rcx, [rbp+var_3F]; this
0x1800390dc  mov     r8d, 87h; int
0x1800390e2  mov     [rbp+var_38], r15
0x1800390e6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800390eb  mov     rax, [rsi]
0x1800390ee  lea     rcx, [rbp+var_38]
0x1800390f2  mov     r14, [rax+30h]
0x1800390f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800390fb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800390ff  mov     [rbp+length], r15d
0x180039103  inc     rcx; unsigned __int64
0x180039106  cmp     [rbx+rcx*2], r15w
0x18003910b  jnz     short loc_180039103
0x18003910d  lea     rdx, [rbp+length]; unsigned int *
0x180039111  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180039116  test    eax, eax
0x180039118  jns     short loc_18003912F
0x18003911a  xor     r9d, r9d; lpArguments
0x18003911d  xor     r8d, r8d; nNumberOfArguments
0x180039120  mov     ecx, 0C000000Dh; dwExceptionCode
0x180039125  lea     edx, [r9+1]; dwExceptionFlags
0x180039129  call    cs:__imp_RaiseException
0x18003912f  mov     edx, [rbp+length]; length
0x180039132  lea     r9, [rbp+string]; string
0x180039136  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003913a  mov     rcx, rbx; sourceString
0x18003913d  call    cs:__imp_WindowsCreateStringReference
0x180039143  mov     rdx, [rbp+string]
0x180039147  lea     r8, [rbp+var_38]
0x18003914b  mov     rcx, rsi
0x18003914e  mov     rax, r14
0x180039151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039156  mov     ebx, eax
0x180039158  test    eax, eax
0x18003915a  jns     loc_18003920D
0x180039160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039167  test    rcx, rcx
0x18003916a  jnz     short loc_1800391AD
0x18003916c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039172  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039179  mov     rcx, rax
0x18003917c  test    rax, rax
0x18003917f  jz      short loc_18003919F
0x180039181  mov     rax, [rax]
0x180039184  mov     edx, 7F0h
0x180039189  mov     rax, [rax+8]
0x18003918d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039192  test    eax, eax
0x180039194  jz      short loc_18003919F
0x180039196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003919d  jmp     short loc_1800391AD
0x18003919f  lea     rcx, qword_180153440; this
0x1800391a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800391ad  cmp     [rcx+8], r15b
0x1800391b1  jz      short loc_1800391D8
0x1800391b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800391b8  cmp     [rax+7CCh], ebx
0x1800391be  jz      short loc_1800391D8
0x1800391c0  mov     r9d, ebx; int
0x1800391c3  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x1800391ca  mov     r8d, 87h; int
0x1800391d0  mov     rcx, rax; this
0x1800391d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800391d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800391df  jb      loc_1800392C6
0x1800391e5  mov     edx, 14h
0x1800391ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391f1  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800391f8  xor     r9d, r9d
0x1800391fb  mov     [rsp+70h+var_50], ebx
0x1800391ff  mov     rcx, [rcx+10h]
0x180039203  call    WPP_SF_qD
0x180039208  jmp     loc_1800392C6
0x18003920d  mov     rcx, [rbp+var_38]
0x180039211  lea     rdx, [rbp+var_40]
0x180039215  mov     [rbp+var_40], r15b
0x180039219  mov     rax, [rcx]
0x18003921c  mov     rax, [rax+90h]
0x180039223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039228  mov     ebx, eax
0x18003922a  test    eax, eax
0x18003922c  jns     loc_1800392BD
0x180039232  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039239  test    rcx, rcx
0x18003923c  jnz     short loc_18003927F
0x18003923e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039244  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003924b  mov     rcx, rax
0x18003924e  test    rax, rax
0x180039251  jz      short loc_180039271
0x180039253  mov     rax, [rax]
0x180039256  mov     edx, 7F0h
0x18003925b  mov     rax, [rax+8]
0x18003925f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039264  test    eax, eax
0x180039266  jz      short loc_180039271
0x180039268  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003926f  jmp     short loc_18003927F
0x180039271  lea     rcx, qword_180153440; this
0x180039278  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003927f  cmp     [rcx+8], r15b
0x180039283  jz      short loc_1800392AA
0x180039285  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003928a  cmp     [rax+7CCh], ebx
0x180039290  jz      short loc_1800392AA
0x180039292  mov     r9d, ebx; int
0x180039295  lea     rdx, aCreateboolfrom; "CreateBOOLFromMap"
0x18003929c  mov     r8d, 8Ah; int
0x1800392a2  mov     rcx, rax; this
0x1800392a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800392aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800392b1  jb      short loc_1800392C6
0x1800392b3  mov     edx, 15h
0x1800392b8  jmp     loc_1800391EA
0x1800392bd  cmp     [rbp+var_40], r15b
0x1800392c1  setnz   al
0x1800392c4  mov     [rdi], al
0x1800392c6  lea     rcx, [rbp+var_3F]; this
0x1800392ca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800392cf  lea     rcx, [rbp+var_38]
0x1800392d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800392d8  mov     eax, ebx
0x1800392da  mov     rcx, [rbp+var_10]
0x1800392de  xor     rcx, rsp; StackCookie
0x1800392e1  call    __security_check_cookie
0x1800392e6  mov     rbx, [rsp+70h+arg_18]
0x1800392ee  add     rsp, 70h
0x1800392f2  pop     r15
0x1800392f4  pop     r14
0x1800392f6  pop     rdi
0x1800392f7  pop     rsi
0x1800392f8  pop     rbp
0x1800392f9  retn
```
