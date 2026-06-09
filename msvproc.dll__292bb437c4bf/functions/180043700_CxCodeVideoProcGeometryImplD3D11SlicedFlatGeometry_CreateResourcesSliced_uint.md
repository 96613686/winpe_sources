# CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced(uint)

- ea: `0x180043700`
- end: `0x1800438a5`
- name: `?CreateResourcesSliced@CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry@@UEAAJI@Z`
- size: `421`
- prototype: `__int64 __fastcall(CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180043700`
- `0x1800a0130`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043779`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043779`

## string_xrefs

- `0x180043717`: `CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced`
- `0x1800437d0`: `CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced(
        CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry *this,
        unsigned int a2)
{
  int VSConstBuffer; // ebx
  __int64 i; // rsi
  struct ID3D11Buffer **v6; // rbx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced",
    196);
  if ( a2 - 1 > 7 )
  {
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        20,
        WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
        (char *)this - 40,
        a2);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
    return 2147500037LL;
  }
  else
  {
    VSConstBuffer = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= a2 )
      {
        *((_DWORD *)this + 18) = a2;
        goto LABEL_17;
      }
      v6 = (struct ID3D11Buffer **)((char *)this + 8 * i);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v6 + 1);
      VSConstBuffer = CxCodeVideoProcGeometryImplD3D11::CreateVSConstBuffer(
                        (CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry *)((char *)this - 40),
                        v6 + 1);
      if ( VSConstBuffer < 0 )
        break;
    }
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != VSConstBuffer )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcGeometryImplD3D11SlicedFlatGeometry::CreateResourcesSliced",
          205,
          VSConstBuffer);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
        (char *)this - 40,
        VSConstBuffer);
LABEL_17:
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        22,
        WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
        (char *)this - 40,
        VSConstBuffer);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
    return (unsigned int)VSConstBuffer;
  }
}

```

## disassembly

```asm
0x180043700  mov     [rsp+arg_0], rbx
0x180043705  mov     [rsp+arg_10], rbp
0x18004370a  push    rsi
0x18004370b  push    rdi
0x18004370c  push    r14
0x18004370e  sub     rsp, 30h
0x180043712  mov     edi, edx
0x180043714  mov     r14, rcx
0x180043717  lea     rdx, aCxcodevideopro_29; "CxCodeVideoProcGeometryImplD3D11SlicedF"...
0x18004371e  mov     r8d, 0C4h; int
0x180043724  lea     rcx, [rsp+48h+arg_8]; this
0x180043729  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004372e  lea     eax, [rdi-1]
0x180043731  cmp     eax, 7
0x180043734  ja      loc_180043853
0x18004373a  xor     ebx, ebx
0x18004373c  lea     rbp, [r14-28h]
0x180043740  xor     esi, esi
0x180043742  cmp     esi, edi
0x180043744  jnb     loc_180043813
0x18004374a  lea     rbx, [r14+rsi*8]
0x18004374e  lea     rcx, [rbx+8]
0x180043752  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180043757  lea     rdx, [rbx+8]; struct ID3D11Buffer **
0x18004375b  mov     rcx, rbp; this
0x18004375e  call    ?CreateVSConstBuffer@CxCodeVideoProcGeometryImplD3D11@@IEAAJPEAPEAUID3D11Buffer@@@Z; CxCodeVideoProcGeometryImplD3D11::CreateVSConstBuffer(ID3D11Buffer * *)
0x180043763  mov     ebx, eax
0x180043765  test    eax, eax
0x180043767  js      short loc_18004376D
0x180043769  inc     esi
0x18004376b  jmp     short loc_180043742
0x18004376d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043774  test    rcx, rcx
0x180043777  jnz     short loc_1800437BA
0x180043779  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004377f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043786  mov     rcx, rax
0x180043789  test    rax, rax
0x18004378c  jz      short loc_1800437AC
0x18004378e  mov     rax, [rax]
0x180043791  mov     edx, 7F0h
0x180043796  mov     rax, [rax+8]
0x18004379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004379f  test    eax, eax
0x1800437a1  jz      short loc_1800437AC
0x1800437a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437aa  jmp     short loc_1800437BA
0x1800437ac  lea     rcx, qword_180153440; this
0x1800437b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437ba  cmp     byte ptr [rcx+8], 0
0x1800437be  jz      short loc_1800437E5
0x1800437c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800437c5  cmp     [rax+7CCh], ebx
0x1800437cb  jz      short loc_1800437E5
0x1800437cd  mov     r9d, ebx; int
0x1800437d0  lea     rdx, aCxcodevideopro_29; "CxCodeVideoProcGeometryImplD3D11SlicedF"...
0x1800437d7  mov     r8d, 0CDh; int
0x1800437dd  mov     rcx, rax; this
0x1800437e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800437e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800437ec  jb      short loc_180043816
0x1800437ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437f5  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x1800437fc  mov     edx, 15h
0x180043801  mov     [rsp+48h+var_28], ebx
0x180043805  mov     r9, rbp
0x180043808  mov     rcx, [rcx+10h]
0x18004380c  call    WPP_SF_qD
0x180043811  jmp     short loc_180043816
0x180043813  mov     [rbp+70h], edi
0x180043816  cmp     cs:byte_180153DE0, 20h ; ' '
0x18004381d  jb      short loc_180043845
0x18004381f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043826  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x18004382d  mov     edx, 16h
0x180043832  mov     [rsp+48h+var_28], ebx
0x180043836  mov     r9, rbp
0x180043839  mov     rcx, [rcx+150h]
0x180043840  call    WPP_SF_qD
0x180043845  lea     rcx, [rsp+48h+arg_8]; this
0x18004384a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004384f  mov     eax, ebx
0x180043851  jmp     short loc_180043892
0x180043853  cmp     cs:byte_180153DE0, 20h ; ' '
0x18004385a  jb      short loc_180043883
0x18004385c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043863  lea     r9, [r14-28h]
0x180043867  mov     edx, 14h
0x18004386c  mov     [rsp+48h+var_28], edi
0x180043870  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x180043877  mov     rcx, [rcx+150h]
0x18004387e  call    WPP_SF_qD
0x180043883  lea     rcx, [rsp+48h+arg_8]; this
0x180043888  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004388d  mov     eax, 80004005h
0x180043892  mov     rbx, [rsp+48h+arg_0]
0x180043897  mov     rbp, [rsp+48h+arg_10]
0x18004389c  add     rsp, 30h
0x1800438a0  pop     r14
0x1800438a2  pop     rdi
0x1800438a3  pop     rsi
0x1800438a4  retn
```
