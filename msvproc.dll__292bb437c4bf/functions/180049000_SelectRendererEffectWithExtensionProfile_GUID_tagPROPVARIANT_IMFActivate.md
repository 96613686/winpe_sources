# SelectRendererEffectWithExtensionProfile(_GUID,tagPROPVARIANT *,IMFActivate * *)

- ea: `0x180049000`
- end: `0x18004935c`
- name: `?SelectRendererEffectWithExtensionProfile@@YAJU_GUID@@PEAUtagPROPVARIANT@@PEAPEAUIMFActivate@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct tagPROPVARIANT *, struct IMFActivate **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800300ac`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180049000`
- `0x180054140`
- `0x180066110`
- `0x180066a98`
- `0x1800b301c`
- `0x1800b30bc`
- `0x1800b3294`
- `0x1800b32ac`
- `0x1800b343c`
- `0x1800b344c`
- `0x1800b6324`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004921a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004931f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004921a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004931f`
- `MFPlat!MFTEnumEx` at `0x1800490cc`
- `MFPlat!MFTEnumEx` at `0x1800490cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800490f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049258`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800490f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049258`

## string_xrefs

- `0x180049071`: `SelectRendererEffectWithExtensionProfile`
- `0x180049151`: `SelectRendererEffectWithExtensionProfile`
- `0x1800492af`: `SelectRendererEffectWithExtensionProfile`

## pseudocode

```c
__int64 __fastcall SelectRendererEffectWithExtensionProfile(
        struct _GUID *a1,
        struct tagPROPVARIANT *a2,
        struct IMFActivate **a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // r8
  bool v7; // zf
  HRESULT v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rax
  UINT32 *pnumMFTActivate; // rbx
  IMFActivate ***pppMFTActivate; // rax
  int v13; // edx
  int v14; // r8d
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  unsigned int i; // edi
  __int64 v20; // rcx
  __int64 j; // rdx
  unsigned __int16 *v22; // rcx
  __int64 v23; // r9
  int v24; // eax
  int v25; // r8d
  struct IMFActivate **v26; // rax
  struct IMFActivate *v27; // rcx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v32[8]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v33[8]; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 v34; // [rsp+40h] [rbp-39h]
  PROPVARIANT pvar; // [rsp+48h] [rbp-31h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v37[16]; // [rsp+70h] [rbp-9h] BYREF
  MFT_REGISTER_TYPE_INFO pInputType; // [rsp+80h] [rbp+7h] BYREF

  pInputType.guidSubtype = *a1;
  pInputType.guidMajorType = MFMediaType_Video;
  wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(
    v33,
    a2);
  v7 = *(_WORD *)v5 == 31;
  memset(&pvar, 0, sizeof(pvar));
  if ( v7 )
  {
    v9 = *(_QWORD *)(v5 + 8);
    *v6 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v32,
      "SelectRendererEffectWithExtensionProfile",
      150);
    v10 = wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address<unsigned int>(
            v33,
            v37);
    pnumMFTActivate = (UINT32 *)MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::data(v10);
    pppMFTActivate = (IMFActivate ***)wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(v33);
    guidCategory = (GUID)MFT_CATEGORY_VIDEO_RENDERER_EFFECT;
    v8 = MFTEnumEx(&guidCategory, 0x400u, &pInputType, 0, pppMFTActivate, pnumMFTActivate);
    wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address_ptr<unsigned int>::~size_address_ptr<unsigned int>(v37);
    if ( v8 >= 0 )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 42), v13, v14, v9, a1->Data1, v34);
      for ( i = 0; i < v34; ++i )
      {
        v20 = *(_QWORD *)wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](
                           v33,
                           i);
        if ( v20
          && (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v20 + 24LL))(
               v20,
               MFT_ENUM_VIDEO_RENDERER_EXTENSION_PROFILE,
               &pvar) >= 0 )
        {
          for ( j = 0; ; j = (unsigned int)(j + 1) )
          {
            if ( (unsigned int)j >= pvar.lVal )
            {
              PropVariantClear(&pvar);
              goto LABEL_29;
            }
            v22 = *(unsigned __int16 **)&pvar.bstrblobVal.pData[8 * j];
            v23 = v9 - (_QWORD)v22;
            do
            {
              v24 = *(unsigned __int16 *)((char *)v22 + v23);
              v25 = *v22 - v24;
              if ( v25 )
                break;
              ++v22;
            }
            while ( v24 );
            if ( !v25 )
              break;
          }
          v26 = (struct IMFActivate **)wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](
                                         v33,
                                         i);
          v27 = *v26;
          *a3 = *v26;
          ((void (__fastcall *)(struct IMFActivate *))v27->lpVtbl->AddRef)(v27);
          goto LABEL_42;
        }
LABEL_29:
        ;
      }
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -1072868846;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072868846 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "SelectRendererEffectWithExtensionProfile",
            183,
            -1072868846);
      }
      if ( g_wppLevels )
      {
        v18 = 20;
        goto LABEL_41;
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
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
        if ( *((_DWORD *)v17 + 499) != v8 )
          CallStackContext::TraceFailure(v17, "SelectRendererEffectWithExtensionProfile", 150, v8);
      }
      if ( g_wppLevels )
      {
        v18 = 18;
LABEL_41:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids, 0, v8);
      }
    }
LABEL_42:
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        21,
        &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
        (unsigned int)v8);
    PropVariantClear(&pvar);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v32);
  }
  else
  {
    v8 = -2147024809;
  }
  wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(v33);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049000  mov     [rsp-8+arg_18], rbx
0x180049005  push    rbp
0x180049006  push    rsi
0x180049007  push    rdi
0x180049008  push    r14
0x18004900a  push    r15
0x18004900c  lea     rbp, [rsp-37h]
0x180049011  sub     rsp, 0B0h
0x180049018  mov     rax, cs:__security_cookie
0x18004901f  xor     rax, rsp
0x180049022  mov     [rbp+57h+var_30], rax
0x180049026  movaps  xmm0, xmmword ptr [rcx]
0x180049029  mov     rdi, rcx
0x18004902c  movups  xmm1, xmmword ptr cs:MFMediaType_Video.Data1
0x180049033  lea     rcx, [rbp+57h+var_98]
0x180049037  mov     r15, r8
0x18004903a  movdqu  xmmword ptr [rbp+57h+pInputType.guidSubtype.Data1], xmm0
0x18004903f  movdqu  xmmword ptr [rbp+57h+pInputType.guidMajorType.Data1], xmm1
0x180049044  call    ??0?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x180049049  xor     eax, eax
0x18004904b  xorps   xmm0, xmm0
0x18004904e  cmp     word ptr [rdx], 1Fh
0x180049052  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180049056  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18004905a  jz      short loc_180049066
0x18004905c  mov     ebx, 80070057h
0x180049061  jmp     loc_18004932E
0x180049066  mov     r14, [rdx+8]
0x18004906a  lea     rcx, [rbp+57h+var_A0]; this
0x18004906e  mov     [r8], rax
0x180049071  lea     rdx, aSelectrenderer_0; "SelectRendererEffectWithExtensionProfil"...
0x180049078  mov     esi, 96h
0x18004907d  mov     r8d, esi; int
0x180049080  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049085  lea     rdx, [rbp+57h+var_60]
0x180049089  lea     rcx, [rbp+57h+var_98]
0x18004908d  call    ??$size_address@I@?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA?AU?$size_address_ptr@I@01@XZ; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address<uint>(void)
0x180049092  mov     rcx, rax
0x180049095  call    ?data@?$D3DCbufferWrapper@U_stD3D11ColorConversionGlobals@@@MFD3D@@UEAAPEAXXZ; MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::data(void)
0x18004909a  lea     rcx, [rbp+57h+var_98]
0x18004909e  mov     rbx, rax
0x1800490a1  call    ??I?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAPEAPEAPEAUIMFActivate@@XZ; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(void)
0x1800490a6  movups  xmm0, cs:MFT_CATEGORY_VIDEO_RENDERER_EFFECT
0x1800490ad  mov     [rsp+0D0h+pnumMFTActivate], rbx; pnumMFTActivate
0x1800490b2  lea     r8, [rbp+57h+pInputType]; pInputType
0x1800490b6  xor     r9d, r9d; pOutputType
0x1800490b9  mov     [rsp+0D0h+pppMFTActivate], rax; pppMFTActivate
0x1800490be  mov     edx, 400h; Flags
0x1800490c3  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x1800490c7  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x1800490cc  call    cs:__imp_MFTEnumEx
0x1800490d2  lea     rcx, [rbp+57h+var_60]
0x1800490d6  mov     ebx, eax
0x1800490d8  call    ??1?$size_address_ptr@I@?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::size_address_ptr<uint>::~size_address_ptr<uint>(void)
0x1800490dd  mov     eax, ebx
0x1800490df  shr     eax, 1Fh
0x1800490e2  test    al, al
0x1800490e4  jz      loc_18004917A
0x1800490ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800490f1  test    rcx, rcx
0x1800490f4  jnz     short loc_180049137
0x1800490f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800490fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049103  mov     rcx, rax
0x180049106  test    rax, rax
0x180049109  jz      short loc_180049129
0x18004910b  mov     rax, [rax]
0x18004910e  mov     edx, 7F0h
0x180049113  mov     rax, [rax+8]
0x180049117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004911c  test    eax, eax
0x18004911e  jz      short loc_180049129
0x180049120  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049127  jmp     short loc_180049137
0x180049129  lea     rcx, qword_180153440; this
0x180049130  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049137  cmp     byte ptr [rcx+8], 0
0x18004913b  jz      short loc_180049163
0x18004913d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049142  test    ebx, ebx
0x180049144  jns     short loc_180049163
0x180049146  cmp     [rax+7CCh], ebx
0x18004914c  jz      short loc_180049163
0x18004914e  mov     r9d, ebx; int
0x180049151  lea     rdx, aSelectrenderer_0; "SelectRendererEffectWithExtensionProfil"...
0x180049158  mov     r8d, esi; int
0x18004915b  mov     rcx, rax; this
0x18004915e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049163  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004916a  jb      loc_1800492F0
0x180049170  mov     edx, 12h
0x180049175  jmp     loc_1800492D2
0x18004917a  cmp     cs:byte_180153DE0, 20h ; ' '
0x180049181  jb      short loc_1800491A6
0x180049183  mov     eax, dword ptr [rbp+57h+var_90]
0x180049186  mov     r9, r14
0x180049189  mov     rcx, cs:WPP_GLOBAL_Control
0x180049190  mov     dword ptr [rsp+0D0h+pnumMFTActivate], eax
0x180049194  mov     eax, [rdi]
0x180049196  mov     dword ptr [rsp+0D0h+pppMFTActivate], eax
0x18004919a  mov     rcx, [rcx+150h]
0x1800491a1  call    WPP_SF_SDd
0x1800491a6  xor     edi, edi
0x1800491a8  mov     esi, edi
0x1800491aa  cmp     rsi, [rbp+57h+var_90]
0x1800491ae  jnb     loc_180049247
0x1800491b4  mov     edx, esi
0x1800491b6  lea     rcx, [rbp+57h+var_98]
0x1800491ba  call    ??A?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAAEAPEAUIMFActivate@@_K@Z; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](unsigned __int64)
0x1800491bf  mov     rcx, [rax]
0x1800491c2  test    rcx, rcx
0x1800491c5  jz      short loc_180049220
0x1800491c7  mov     rax, [rcx]
0x1800491ca  lea     r8, [rbp+57h+pvar]
0x1800491ce  lea     rdx, MFT_ENUM_VIDEO_RENDERER_EXTENSION_PROFILE
0x1800491d5  mov     rax, [rax+18h]
0x1800491d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491de  test    eax, eax
0x1800491e0  js      short loc_180049220
0x1800491e2  mov     r10, qword ptr [rbp+57h+pvar+10h]
0x1800491e6  xor     edx, edx
0x1800491e8  cmp     edx, dword ptr [rbp+57h+pvar+8]
0x1800491eb  jnb     short loc_180049216
0x1800491ed  mov     rcx, [r10+rdx*8]
0x1800491f1  mov     r9, r14
0x1800491f4  sub     r9, rcx
0x1800491f7  movzx   r8d, word ptr [rcx]
0x1800491fb  movzx   eax, word ptr [rcx+r9]
0x180049200  sub     r8d, eax
0x180049203  jnz     short loc_18004920D
0x180049205  add     rcx, 2
0x180049209  test    eax, eax
0x18004920b  jnz     short loc_1800491F7
0x18004920d  test    r8d, r8d
0x180049210  jz      short loc_180049224
0x180049212  inc     edx
0x180049214  jmp     short loc_1800491E8
0x180049216  lea     rcx, [rbp+57h+pvar]; pvar
0x18004921a  call    cs:__imp_PropVariantClear
0x180049220  inc     edi
0x180049222  jmp     short loc_1800491A8
0x180049224  mov     rdx, rsi
0x180049227  lea     rcx, [rbp+57h+var_98]
0x18004922b  call    ??A?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAAEAPEAUIMFActivate@@_K@Z; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator[](unsigned __int64)
0x180049230  mov     rcx, [rax]
0x180049233  mov     [r15], rcx
0x180049236  mov     rax, [rcx]
0x180049239  mov     rax, [rax+8]
0x18004923d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049242  jmp     loc_1800492F0
0x180049247  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004924e  mov     ebx, 0C00D5212h
0x180049253  test    rcx, rcx
0x180049256  jnz     short loc_180049299
0x180049258  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004925e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049265  mov     rcx, rax
0x180049268  test    rax, rax
0x18004926b  jz      short loc_18004928B
0x18004926d  mov     rax, [rax]
0x180049270  mov     edx, 7F0h
0x180049275  mov     rax, [rax+8]
0x180049279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004927e  test    eax, eax
0x180049280  jz      short loc_18004928B
0x180049282  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049289  jmp     short loc_180049299
0x18004928b  lea     rcx, qword_180153440; this
0x180049292  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049299  cmp     byte ptr [rcx+8], 0
0x18004929d  jz      short loc_1800492C4
0x18004929f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800492a4  cmp     [rax+7CCh], ebx
0x1800492aa  jz      short loc_1800492C4
0x1800492ac  mov     r9d, ebx; int
0x1800492af  lea     rdx, aSelectrenderer_0; "SelectRendererEffectWithExtensionProfil"...
0x1800492b6  mov     r8d, 0B7h; int
0x1800492bc  mov     rcx, rax; this
0x1800492bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800492c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800492cb  jb      short loc_1800492F0
0x1800492cd  mov     edx, 14h
0x1800492d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492d9  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800492e0  xor     r9d, r9d
0x1800492e3  mov     dword ptr [rsp+0D0h+pppMFTActivate], ebx
0x1800492e7  mov     rcx, [rcx+10h]
0x1800492eb  call    WPP_SF_qD
0x1800492f0  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800492f7  jb      short loc_18004931B
0x1800492f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180049300  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x180049307  mov     edx, 15h
0x18004930c  mov     r9d, ebx
0x18004930f  mov     rcx, [rcx+150h]
0x180049316  call    WPP_SF_d
0x18004931b  lea     rcx, [rbp+57h+pvar]; pvar
0x18004931f  call    cs:__imp_PropVariantClear
0x180049325  lea     rcx, [rbp+57h+var_A0]; this
0x180049329  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004932e  lea     rcx, [rbp+57h+var_98]
0x180049332  call    ??1?$unique_any_array_ptr@PEAUIMFActivate@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IMFActivate *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x180049337  mov     eax, ebx
0x180049339  mov     rcx, [rbp+57h+var_30]
0x18004933d  xor     rcx, rsp; StackCookie
0x180049340  call    __security_check_cookie
0x180049345  mov     rbx, [rsp+0D0h+arg_18]
0x18004934d  add     rsp, 0B0h
0x180049354  pop     r15
0x180049356  pop     r14
0x180049358  pop     rdi
0x180049359  pop     rsi
0x18004935a  pop     rbp
0x18004935b  retn
```
