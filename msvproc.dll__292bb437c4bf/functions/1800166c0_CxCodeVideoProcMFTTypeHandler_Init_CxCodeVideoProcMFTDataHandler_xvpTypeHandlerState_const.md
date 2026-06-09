# CxCodeVideoProcMFTTypeHandler::Init(CxCodeVideoProcMFTDataHandler *,xvpTypeHandlerState * const)

- ea: `0x1800166c0`
- end: `0x180016939`
- name: `?Init@CxCodeVideoProcMFTTypeHandler@@QEAAJPEAVCxCodeVideoProcMFTDataHandler@@QEAUxvpTypeHandlerState@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *__hidden this, struct CxCodeVideoProcMFTDataHandler *, struct xvpTypeHandlerState *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001649c`

## callees

- `0x180009940`
- `0x18000a09c`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800166c0`
- `0x180016e1c`
- `0x18003639c`
- `0x180054140`
- `0x1800c7070`
- `0x1800c8484`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800167a0`
- `MFPlat!MFCreateMediaType` at `0x1800167a0`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::Init(
        CxCodeVideoProcMFTTypeHandler *this,
        struct CxCodeVideoProcMFTDataHandler *a2,
        struct xvpTypeHandlerState *const a3)
{
  unsigned int v5; // r8d
  unsigned int inited; // edi
  unsigned int i; // ebx
  unsigned int v8; // eax
  IMFMediaType *v9; // rcx
  unsigned int v10; // r9d
  IMFMediaType *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v14; // ebx
  __int128 v15; // xmm0
  _BYTE v16[8]; // [rsp+30h] [rbp-30h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v18[4]; // [rsp+40h] [rbp-20h] BYREF

  *((_QWORD *)this + 45) = a3;
  XVPReadRegistryOverrides((struct xvpTypeHandlerState *const)((char *)a3 + 24));
  *(_DWORD *)(*((_QWORD *)this + 45) + 16LL) = AccessRegistryInt(
                                                 L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                                                 L"UseStrictTypeCheck",
                                                 0);
  *(_DWORD *)(*((_QWORD *)this + 45) + 20LL) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v16, "CxCodeVideoProcMFTTypeHandler::Init", 7386);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v15 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 48) + 280LL))(
                       *((_QWORD *)this + 48),
                       v18);
    *((_DWORD *)ThreadRelativeContext + 504) = v14;
    *((_OWORD *)ThreadRelativeContext + 125) = v15;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      354,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      *(_DWORD *)(*((_QWORD *)this + 45) + 24LL));
  *((_QWORD *)this + 1) = a2;
  inited = CMFTMultiStreamTypeHandler::InitAvailableInputTypeArray(this, 0x24u, v5);
  if ( !inited )
  {
    for ( i = 0; i < 0x24; ++i )
    {
      ppMFType = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      inited = MFCreateMediaType(&ppMFType);
      if ( inited )
        goto LABEL_18;
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MFMediaType_Video);
      v9 = ppMFType;
      inited = v8;
      if ( v8 )
      {
        if ( ppMFType )
        {
          ppMFType = 0;
          ((void (__fastcall *)(IMFMediaType *))v9->lpVtbl->Release)(v9);
        }
        break;
      }
      v18[1] = 0x100000;
      v18[2] = -1442840448;
      v18[3] = 1905997824;
      v18[0] = *((_DWORD *)&CtypeSurfaces::types + 20 * i);
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _DWORD *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_SUBTYPE,
                 v18);
      if ( inited )
      {
LABEL_18:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
        break;
      }
      CMFTMultiStreamTypeHandler::SetAvailableInputType(this, i, ppMFType, v10);
      v11 = ppMFType;
      if ( ppMFType )
      {
        ppMFType = 0;
        ((void (__fastcall *)(IMFMediaType *))v11->lpVtbl->Release)(v11);
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v16);
  return inited;
}

```

## disassembly

```asm
0x1800166c0  mov     [rsp-28h+arg_10], rbx
0x1800166c5  push    rbp
0x1800166c6  push    rsi
0x1800166c7  push    rdi
0x1800166c8  push    r14
0x1800166ca  push    r15
0x1800166cc  mov     rbp, rsp
0x1800166cf  sub     rsp, 60h
0x1800166d3  mov     rax, cs:__security_cookie
0x1800166da  xor     rax, rsp
0x1800166dd  mov     [rbp+var_10], rax
0x1800166e1  mov     rsi, rcx
0x1800166e4  mov     [rcx+168h], r8
0x1800166eb  lea     rcx, [r8+18h]; enum XVPDebugMode *
0x1800166ef  mov     r14, rdx
0x1800166f2  call    ?XVPReadRegistryOverrides@@YAXAEAW4XVPDebugMode@@@Z; XVPReadRegistryOverrides(XVPDebugMode &)
0x1800166f7  xor     r8d, r8d; int
0x1800166fa  lea     rdx, aUsestricttypec; "UseStrictTypeCheck"
0x180016701  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x180016708  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x18001670d  mov     rdx, [rsi+168h]
0x180016714  lea     rcx, [rbp+var_30]; this
0x180016718  xor     r15d, r15d
0x18001671b  mov     r8d, 1CDAh; int
0x180016721  mov     [rdx+10h], eax
0x180016724  lea     rdx, aCxcodevideopro_169; "CxCodeVideoProcMFTTypeHandler::Init"
0x18001672b  mov     rax, [rsi+168h]
0x180016732  mov     [rax+14h], r15d
0x180016736  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001673b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180016742  cmp     [rcx+8], r15b
0x180016746  jnz     loc_18001689A
0x18001674c  cmp     cs:byte_180153DE0, 20h ; ' '
0x180016753  jnb     loc_1800168F6
0x180016759  mov     edx, 24h ; '$'; unsigned int
0x18001675e  mov     [rsi+8], r14
0x180016762  mov     rcx, rsi; this
0x180016765  call    ?InitAvailableInputTypeArray@CMFTMultiStreamTypeHandler@@IEAAJKK@Z; CMFTMultiStreamTypeHandler::InitAvailableInputTypeArray(ulong,ulong)
0x18001676a  mov     edi, eax
0x18001676c  test    eax, eax
0x18001676e  jnz     loc_18001686F
0x180016774  mov     [rsp+60h+arg_8], r12
0x18001677c  mov     ebx, r15d
0x18001677f  lea     r12, ?types@CtypeSurfaces@@0QBUTypeSurface@@B; TypeSurface const near * const CtypeSurfaces::types
0x180016786  cmp     ebx, 24h ; '$'
0x180016789  jnb     loc_180016867
0x18001678f  lea     rcx, [rbp+ppMFType]
0x180016793  mov     [rbp+ppMFType], r15
0x180016797  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001679c  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800167a0  call    cs:__imp_MFCreateMediaType
0x1800167a6  mov     edi, eax
0x1800167a8  test    eax, eax
0x1800167aa  jnz     loc_18001692B
0x1800167b0  mov     rcx, [rbp+ppMFType]
0x1800167b4  lea     r8, MFMediaType_Video
0x1800167bb  lea     rdx, MF_MT_MAJOR_TYPE
0x1800167c2  mov     rax, [rcx]
0x1800167c5  mov     rax, [rax+0C0h]
0x1800167cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d1  mov     rcx, [rbp+ppMFType]
0x1800167d5  mov     edi, eax
0x1800167d7  test    eax, eax
0x1800167d9  jnz     short loc_180016852
0x1800167db  mov     [rbp+var_1C], 100000h
0x1800167e2  lea     r8, [rbp+var_20]
0x1800167e6  mov     [rbp+var_18], 0AA000080h
0x1800167ed  lea     rdx, MF_MT_SUBTYPE
0x1800167f4  mov     [rbp+var_14], 719B3800h
0x1800167fb  mov     eax, ebx
0x1800167fd  lea     rax, [rax+rax*4]
0x180016801  add     rax, rax
0x180016804  mov     eax, [r12+rax*8]
0x180016808  mov     [rbp+var_20], eax
0x18001680b  mov     rax, [rcx]
0x18001680e  mov     rax, [rax+0C0h]
0x180016815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001681a  mov     edi, eax
0x18001681c  test    eax, eax
0x18001681e  jnz     loc_18001692B
0x180016824  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x180016828  mov     edx, ebx; unsigned int
0x18001682a  mov     rcx, rsi; this
0x18001682d  call    ?SetAvailableInputType@CMFTMultiStreamTypeHandler@@QEAAXKPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::SetAvailableInputType(ulong,IMFMediaType *,ulong)
0x180016832  mov     rcx, [rbp+ppMFType]
0x180016836  test    rcx, rcx
0x180016839  jz      short loc_18001684B
0x18001683b  mov     [rbp+ppMFType], r15
0x18001683f  mov     rax, [rcx]
0x180016842  mov     rax, [rax+10h]
0x180016846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001684b  inc     ebx
0x18001684d  jmp     loc_180016786
0x180016852  test    rcx, rcx
0x180016855  jz      short loc_180016867
0x180016857  mov     [rbp+ppMFType], r15
0x18001685b  mov     rax, [rcx]
0x18001685e  mov     rax, [rax+10h]
0x180016862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016867  mov     r12, [rsp+60h+arg_8]
0x18001686f  lea     rcx, [rbp+var_30]; this
0x180016873  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180016878  mov     eax, edi
0x18001687a  mov     rcx, [rbp+var_10]
0x18001687e  xor     rcx, rsp; StackCookie
0x180016881  call    __security_check_cookie
0x180016886  mov     rbx, [rsp+60h+arg_10]
0x18001688e  add     rsp, 60h
0x180016892  pop     r15
0x180016894  pop     r14
0x180016896  pop     rdi
0x180016897  pop     rsi
0x180016898  pop     rbp
0x180016899  retn
0x18001689a  cmp     [rsi+180h], r15
0x1800168a1  jz      loc_18001674C
0x1800168a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800168ac  mov     rcx, [rsi+180h]
0x1800168b3  mov     rdi, rax
0x1800168b6  mov     rdx, [rcx]
0x1800168b9  mov     rax, [rdx+128h]
0x1800168c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c5  mov     rcx, [rsi+180h]
0x1800168cc  mov     ebx, eax
0x1800168ce  mov     rdx, [rcx]
0x1800168d1  mov     rax, [rdx+118h]
0x1800168d8  lea     rdx, [rbp+var_20]
0x1800168dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e1  movups  xmm0, xmmword ptr [rax]
0x1800168e4  mov     [rdi+7E0h], ebx
0x1800168ea  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800168f1  jmp     loc_18001674C
0x1800168f6  mov     rax, [rsi+168h]
0x1800168fd  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180016904  mov     rcx, cs:WPP_GLOBAL_Control
0x18001690b  mov     edx, 162h
0x180016910  mov     r9, rsi
0x180016913  mov     eax, [rax+18h]
0x180016916  mov     rcx, [rcx+150h]
0x18001691d  mov     [rsp+60h+var_40], eax
0x180016921  call    WPP_SF_qD
0x180016926  jmp     loc_180016759
0x18001692b  lea     rcx, [rbp+ppMFType]
0x18001692f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016934  jmp     loc_180016867
```
