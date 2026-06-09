# CreateVideoRendererInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,VideoRendererPackInfo &)

- ea: `0x180018708`
- end: `0x180018a43`
- name: `?CreateVideoRendererInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUVideoRendererPackInfo@@@Z`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d8b0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018708`
- `0x180018ca8`
- `0x180018f2c`
- `0x18001976c`
- `0x1800346b4`
- `0x18003639c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001877d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018843`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001890a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001877d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018843`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001890a`

## string_xrefs

- `0x18001872d`: `CreateVideoRendererInfoFromMediaExtensionMap`
- `0x1800187d4`: `CreateVideoRendererInfoFromMediaExtensionMap`
- `0x18001889a`: `CreateVideoRendererInfoFromMediaExtensionMap`
- `0x180018961`: `CreateVideoRendererInfoFromMediaExtensionMap`
- `0x18001899a`: `VideoRendererExtensionProfiles`
- `0x1800189c8`: `VideoRendererExtensionProfile`

## pseudocode

```c
__int64 __fastcall CreateVideoRendererInfoFromMediaExtensionMap(__int64 a1, __int64 a2)
{
  int SubMapFromMap; // edi
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // [rsp+30h] [rbp-10h] BYREF
  __int64 v23; // [rsp+38h] [rbp-8h] BYREF
  char v24; // [rsp+70h] [rbp+30h] BYREF
  __int64 v25; // [rsp+78h] [rbp+38h] BYREF

  v25 = 0;
  v23 = 0;
  v22 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
    "CreateVideoRendererInfoFromMediaExtensionMap",
    1384);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  SubMapFromMap = GetSubMapFromMap(a1, L"VideoRendererEffect", &v25);
  if ( SubMapFromMap >= 0 )
  {
    SubMapFromMap = CreateInprocMFTExtensionInfoFromMediaExtensionMap(a1, v25, a2);
    if ( SubMapFromMap >= 0 )
    {
      *(_DWORD *)(a2 + 64) |= 1u;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      GetSubMapFromMap(v25, L"InputTypes", &v23);
      SubMapFromMap = CreateTypeVectorFromMap(v23, v12, v13, a2 + 72);
      if ( SubMapFromMap >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        GetSubMapFromMap(v25, L"VideoRendererExtensionProfiles", &v22);
        v17 = (_QWORD *)(a2 + 448);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
        CreateStringVectorFromMap(v22, (__int64)L"VideoRendererExtensionProfile", (__int64)L"@Profile", 0, v17);
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != SubMapFromMap )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CreateVideoRendererInfoFromMediaExtensionMap",
              1391,
              SubMapFromMap);
        }
        if ( g_wppLevels )
        {
          v8 = 185;
          goto LABEL_12;
        }
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
        if ( *((_DWORD *)v11 + 499) != SubMapFromMap )
          CallStackContext::TraceFailure(v11, "CreateVideoRendererInfoFromMediaExtensionMap", 1385, SubMapFromMap);
      }
      if ( g_wppLevels )
      {
        v8 = 184;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != SubMapFromMap )
        CallStackContext::TraceFailure(v7, "CreateVideoRendererInfoFromMediaExtensionMap", 1384, SubMapFromMap);
    }
    if ( g_wppLevels )
    {
      v8 = 183;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        SubMapFromMap);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return (unsigned int)SubMapFromMap;
}

```

## disassembly

```asm
0x180018708  mov     [rsp-18h+arg_0], rbx
0x18001870d  push    rbp
0x18001870e  push    rsi
0x18001870f  push    rdi
0x180018710  mov     rbp, rsp
0x180018713  sub     rsp, 40h
0x180018717  mov     rbx, rdx
0x18001871a  mov     [rbp+arg_18], 0
0x180018722  mov     rsi, rcx
0x180018725  mov     [rbp+var_8], 0
0x18001872d  lea     rdx, aCreatevideoren; "CreateVideoRendererInfoFromMediaExtensi"...
0x180018734  mov     [rbp+var_10], 0
0x18001873c  lea     rcx, [rbp+arg_10]; this
0x180018740  mov     r8d, 568h; int
0x180018746  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001874b  lea     rcx, [rbp+arg_18]
0x18001874f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018754  lea     r8, [rbp+arg_18]
0x180018758  mov     rcx, rsi
0x18001875b  lea     rdx, aVideorenderere_0; "VideoRendererEffect"
0x180018762  call    GetSubMapFromMap
0x180018767  mov     edi, eax
0x180018769  test    eax, eax
0x18001876b  jns     loc_18001881E
0x180018771  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018778  test    rcx, rcx
0x18001877b  jnz     short loc_1800187BE
0x18001877d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018783  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001878a  mov     rcx, rax
0x18001878d  test    rax, rax
0x180018790  jz      short loc_1800187B0
0x180018792  mov     rax, [rax]
0x180018795  mov     edx, 7F0h
0x18001879a  mov     rax, [rax+8]
0x18001879e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187a3  test    eax, eax
0x1800187a5  jz      short loc_1800187B0
0x1800187a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800187ae  jmp     short loc_1800187BE
0x1800187b0  lea     rcx, qword_180153440; this
0x1800187b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800187be  cmp     byte ptr [rcx+8], 0
0x1800187c2  jz      short loc_1800187E9
0x1800187c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800187c9  cmp     [rax+7CCh], edi
0x1800187cf  jz      short loc_1800187E9
0x1800187d1  mov     r9d, edi; int
0x1800187d4  lea     rdx, aCreatevideoren; "CreateVideoRendererInfoFromMediaExtensi"...
0x1800187db  mov     r8d, 568h; int
0x1800187e1  mov     rcx, rax; this
0x1800187e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800187e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800187f0  jb      loc_1800189D4
0x1800187f6  mov     edx, 0B7h
0x1800187fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018802  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180018809  xor     r9d, r9d
0x18001880c  mov     dword ptr [rsp+40h+var_20], edi
0x180018810  mov     rcx, [rcx+10h]
0x180018814  call    WPP_SF_qD
0x180018819  jmp     loc_1800189D4
0x18001881e  mov     rdx, [rbp+arg_18]
0x180018822  mov     r8, rbx
0x180018825  mov     rcx, rsi
0x180018828  call    ?CreateInprocMFTExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUInprocMFTExtensionInfo@@@Z; CreateInprocMFTExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,InprocMFTExtensionInfo &)
0x18001882d  mov     edi, eax
0x18001882f  test    eax, eax
0x180018831  jns     loc_1800188C6
0x180018837  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001883e  test    rcx, rcx
0x180018841  jnz     short loc_180018884
0x180018843  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018849  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018850  mov     rcx, rax
0x180018853  test    rax, rax
0x180018856  jz      short loc_180018876
0x180018858  mov     rax, [rax]
0x18001885b  mov     edx, 7F0h
0x180018860  mov     rax, [rax+8]
0x180018864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018869  test    eax, eax
0x18001886b  jz      short loc_180018876
0x18001886d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018874  jmp     short loc_180018884
0x180018876  lea     rcx, qword_180153440; this
0x18001887d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018884  cmp     byte ptr [rcx+8], 0
0x180018888  jz      short loc_1800188AF
0x18001888a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001888f  cmp     [rax+7CCh], edi
0x180018895  jz      short loc_1800188AF
0x180018897  mov     r9d, edi; int
0x18001889a  lea     rdx, aCreatevideoren; "CreateVideoRendererInfoFromMediaExtensi"...
0x1800188a1  mov     r8d, 569h; int
0x1800188a7  mov     rcx, rax; this
0x1800188aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800188af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800188b6  jb      loc_1800189D4
0x1800188bc  mov     edx, 0B8h
0x1800188c1  jmp     loc_1800187FB
0x1800188c6  or      dword ptr [rbx+40h], 1
0x1800188ca  lea     rcx, [rbp+var_8]
0x1800188ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188d3  mov     rcx, [rbp+arg_18]
0x1800188d7  lea     r8, [rbp+var_8]
0x1800188db  lea     rdx, aInputtypes; "InputTypes"
0x1800188e2  call    GetSubMapFromMap
0x1800188e7  mov     rcx, [rbp+var_8]
0x1800188eb  lea     r9, [rbx+48h]
0x1800188ef  call    ?CreateTypeVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@AEAV?$CTDynArray@U_GUID@@$0BE@@@@Z; CreateTypeVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,CTDynArray<_GUID,20> &)
0x1800188f4  mov     edi, eax
0x1800188f6  test    eax, eax
0x1800188f8  jns     loc_180018989
0x1800188fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018905  test    rcx, rcx
0x180018908  jnz     short loc_18001894B
0x18001890a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018910  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018917  mov     rcx, rax
0x18001891a  test    rax, rax
0x18001891d  jz      short loc_18001893D
0x18001891f  mov     rax, [rax]
0x180018922  mov     edx, 7F0h
0x180018927  mov     rax, [rax+8]
0x18001892b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018930  test    eax, eax
0x180018932  jz      short loc_18001893D
0x180018934  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001893b  jmp     short loc_18001894B
0x18001893d  lea     rcx, qword_180153440; this
0x180018944  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001894b  cmp     byte ptr [rcx+8], 0
0x18001894f  jz      short loc_180018976
0x180018951  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018956  cmp     [rax+7CCh], edi
0x18001895c  jz      short loc_180018976
0x18001895e  mov     r9d, edi; int
0x180018961  lea     rdx, aCreatevideoren; "CreateVideoRendererInfoFromMediaExtensi"...
0x180018968  mov     r8d, 56Fh; int
0x18001896e  mov     rcx, rax; this
0x180018971  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018976  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001897d  jb      short loc_1800189D4
0x18001897f  mov     edx, 0B9h
0x180018984  jmp     loc_1800187FB
0x180018989  lea     rcx, [rbp+var_10]
0x18001898d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018992  mov     rcx, [rbp+arg_18]
0x180018996  lea     r8, [rbp+var_10]
0x18001899a  lea     rdx, aVideorenderere_1; "VideoRendererExtensionProfiles"
0x1800189a1  call    GetSubMapFromMap
0x1800189a6  add     rbx, 1C0h
0x1800189ad  mov     rcx, rbx
0x1800189b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800189b5  mov     rcx, [rbp+var_10]
0x1800189b9  lea     r8, aProfile; "@Profile"
0x1800189c0  xor     r9d, r9d
0x1800189c3  mov     [rsp+40h+var_20], rbx
0x1800189c8  lea     rdx, sourceString; "VideoRendererExtensionProfile"
0x1800189cf  call    ?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NPEAPEAU?$IVector@PEAUHSTRING__@@@234@@Z; CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,Windows::Foundation::Collections::IVector<HSTRING__ *> * *)
0x1800189d4  lea     rcx, [rbp+arg_10]; this
0x1800189d8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800189dd  mov     rcx, [rbp+var_10]
0x1800189e1  test    rcx, rcx
0x1800189e4  jz      short loc_1800189FA
0x1800189e6  mov     [rbp+var_10], 0
0x1800189ee  mov     rax, [rcx]
0x1800189f1  mov     rax, [rax+10h]
0x1800189f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189fa  mov     rcx, [rbp+var_8]
0x1800189fe  test    rcx, rcx
0x180018a01  jz      short loc_180018A17
0x180018a03  mov     [rbp+var_8], 0
0x180018a0b  mov     rax, [rcx]
0x180018a0e  mov     rax, [rax+10h]
0x180018a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a17  mov     rcx, [rbp+arg_18]
0x180018a1b  test    rcx, rcx
0x180018a1e  jz      short loc_180018A34
0x180018a20  mov     [rbp+arg_18], 0
0x180018a28  mov     rax, [rcx]
0x180018a2b  mov     rax, [rax+10h]
0x180018a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a34  mov     rbx, [rsp+40h+arg_0]
0x180018a39  mov     eax, edi
0x180018a3b  add     rsp, 40h
0x180018a3f  pop     rdi
0x180018a40  pop     rsi
0x180018a41  pop     rbp
0x180018a42  retn
```
