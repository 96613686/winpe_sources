# CMSVPxDecoderClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ad0`
- end: `0x180003f19`
- name: `?CreateInstance@CMSVPxDecoderClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1097`
- prototype: `__int64 __fastcall(CMSVPxDecoderClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003f20`

## callees

- `0x180001034`
- `0x180001068`
- `0x180001a90`
- `0x180001f10`
- `0x180002cb0`
- `0x180003ad0`
- `0x180004280`
- `0x180004778`
- `0x18000502d`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e3b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003e6a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003e6a`
- `MFPlat!MFTEnumEx` at `0x180003c2a`
- `MFPlat!MFTEnumEx` at `0x180003c2a`

## string_xrefs

- `0x180003b66`: `CMSVPxDecoderClassFactory::CreateInstance`
- `0x180003bcf`: `CMSVPxDecoderClassFactory::CreateInstance`
- `0x180003c66`: `CMSVPxDecoderClassFactory::CreateInstance`
- `0x180003d55`: `CMSVPxDecoderClassFactory::CreateInstance`
- `0x180003dc5`: `CMSVPxDecoderClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMSVPxDecoderClassFactory::CreateInstance(
        CMSVPxDecoderClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 *v7; // rcx
  HRESULT v8; // ebx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v13; // rcx
  struct CallStackContext *v14; // rax
  UINT32 i; // esi
  HRESULT v16; // eax
  IMFActivate *v17; // rdi
  HRESULT (__stdcall *ActivateObject)(IMFActivate *, const IID *const, void **); // rbx
  __int64 *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  struct CallStackContext *v22; // rax
  UINT32 j; // edi
  IMFActivate *v24; // rcx
  UINT32 pnumMFTActivate; // [rsp+30h] [rbp-89h] BYREF
  HRESULT v27; // [rsp+34h] [rbp-85h] BYREF
  IMFActivate **pppMFTActivate; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v29[2]; // [rsp+40h] [rbp-79h] BYREF
  GUID guidCategory; // [rsp+50h] [rbp-69h] BYREF
  MFT_REGISTER_TYPE_INFO pInputType; // [rsp+60h] [rbp-59h] BYREF
  char v32[32]; // [rsp+80h] [rbp-39h] BYREF
  HRESULT *v33; // [rsp+A0h] [rbp-19h]
  __int64 v34; // [rsp+A8h] [rbp-11h]
  GUID *v35; // [rsp+B0h] [rbp-9h]
  __int64 v36; // [rsp+B8h] [rbp-1h]
  GUID *p_guidCategory; // [rsp+C0h] [rbp+7h]
  __int64 v38; // [rsp+C8h] [rbp+Fh]

  pppMFTActivate = 0;
  pnumMFTActivate = 0;
  v29[0] = 0;
  pInputType.guidMajorType = MFMediaType_Video;
  pInputType.guidSubtype = MFVideoFormat_VP90;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -2147221232;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = &qword_18000A4C0;
        CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147221232 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMSVPxDecoderClassFactory::CreateInstance",
            74,
            -2147221232);
      }
      if ( g_wppLevels )
      {
        v10 = 11;
        goto LABEL_48;
      }
    }
    else
    {
      guidCategory = MFT_CATEGORY_VIDEO_DECODER;
      v8 = MFTEnumEx(&guidCategory, 0x40u, &pInputType, 0, &pppMFTActivate, &pnumMFTActivate);
      if ( v8 >= 0 )
      {
        for ( i = 0; i < pnumMFTActivate; ++i )
        {
          v27 = 0;
          if ( ((int (__fastcall *)(IMFActivate *, __int64 *, HRESULT *))pppMFTActivate[i]->lpVtbl->GetUINT32)(
                 pppMFTActivate[i],
                 MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED,
                 &v27) >= 0 )
          {
            v16 = v27;
          }
          else
          {
            v16 = 0;
            v27 = 0;
          }
          if ( v16 )
          {
            v17 = pppMFTActivate[i];
            ActivateObject = v17->lpVtbl->ActivateObject;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
            if ( ((int (__fastcall *)(IMFActivate *, GUID *, _QWORD *))ActivateObject)(
                   v17,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v29) >= 0 )
              break;
          }
        }
        if ( v29[0] )
        {
          v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))v29[0])(v29[0], a3, a4);
          if ( v8 < 0 )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = &qword_18000A4C0;
              CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
              if ( *((_DWORD *)v22 + 499) != v8 )
                CallStackContext::TraceFailure(v22, "CMSVPxDecoderClassFactory::CreateInstance", 96, v8);
            }
            if ( g_wppLevels )
            {
              v10 = 14;
              goto LABEL_48;
            }
          }
        }
        else
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          v8 = -1072868846;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = &qword_18000A4C0;
            CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v20 + 499) != -1072868846 )
              CallStackContext::TraceFailure(v20, "CMSVPxDecoderClassFactory::CreateInstance", 95, -1072868846);
          }
          if ( g_wppLevels )
          {
            v10 = 13;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = &qword_18000A4C0;
          CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v14 + 499) != v8 )
            CallStackContext::TraceFailure(v14, "CMSVPxDecoderClassFactory::CreateInstance", 84, v8);
        }
        if ( g_wppLevels )
        {
          v10 = 12;
          goto LABEL_48;
        }
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = &qword_18000A4C0;
      CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v9, "CMSVPxDecoderClassFactory::CreateInstance", 69, -2147467261);
    }
    if ( g_wppLevels )
    {
      v10 = 10;
LABEL_48:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, a3, this, v8);
    }
  }
  for ( j = 0; j < pnumMFTActivate; ++j )
  {
    v24 = pppMFTActivate[j];
    if ( v24 )
    {
      ((void (__fastcall *)(IMFActivate *, struct IUnknown *))v24->lpVtbl->Release)(v24, a2);
      pppMFTActivate[j] = 0;
    }
  }
  CoTaskMemFree(pppMFTActivate);
  if ( !memcmp_0(&g_InstanceGuid, &GUID_00000000_0000_0000_0000_000000000000, 0x10u)
    && CoCreateGuid(&g_InstanceGuid) >= 0
    && (unsigned int)dword_18000A058 > 4
    && (unsigned __int8)tlgKeywordOn() )
  {
    *(_QWORD *)&guidCategory.Data1 = 0x1000000;
    p_guidCategory = &guidCategory;
    v27 = v8;
    v33 = &v27;
    v38 = 8;
    v35 = &g_InstanceGuid;
    v36 = 16;
    v34 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18000A058, byte_180007DE1, 0, 0, 5, v32);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp-8+arg_8], rbx
0x180003ad5  push    rbp
0x180003ad6  push    rsi
0x180003ad7  push    rdi
0x180003ad8  push    r12
0x180003ada  push    r13
0x180003adc  push    r14
0x180003ade  push    r15
0x180003ae0  lea     rbp, [rsp-27h]
0x180003ae5  sub     rsp, 0E0h
0x180003aec  mov     rax, cs:__security_cookie
0x180003af3  xor     rax, rsp
0x180003af6  mov     [rbp+57h+var_40], rax
0x180003afa  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x180003b01  xor     r13d, r13d
0x180003b04  mov     r15, r9
0x180003b07  mov     [rsp+110h+var_D8], r13
0x180003b0c  mov     r12, r8
0x180003b0f  mov     [rsp+110h+var_E0], r13d
0x180003b14  mov     r14, rcx
0x180003b17  mov     [rbp+57h+var_D0], r13
0x180003b1b  movups  xmm1, xmmword ptr cs:MFVideoFormat_VP90.Data1
0x180003b22  movdqu  xmmword ptr [rbp+57h+pInputType.guidMajorType.Data1], xmm0
0x180003b27  movdqu  xmmword ptr [rbp+57h+pInputType.guidSubtype.Data1], xmm1
0x180003b2c  test    r9, r9
0x180003b2f  jnz     short loc_180003B92
0x180003b31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003b38  mov     ebx, 80004003h
0x180003b3d  test    rcx, rcx
0x180003b40  jnz     short loc_180003B50
0x180003b42  lea     rcx, qword_18000A4C0; this
0x180003b49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003b50  cmp     [rcx+8], r13b
0x180003b54  jz      short loc_180003B7B
0x180003b56  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003b5b  cmp     [rax+7CCh], ebx
0x180003b61  jz      short loc_180003B7B
0x180003b63  mov     r9d, ebx; int
0x180003b66  lea     rdx, aCmsvpxdecoderc; "CMSVPxDecoderClassFactory::CreateInstan"...
0x180003b6d  mov     r8d, 45h ; 'E'; int
0x180003b73  mov     rcx, rax; this
0x180003b76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003b7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003b82  jb      loc_180003DFF
0x180003b88  mov     edx, 0Ah
0x180003b8d  jmp     loc_180003DE8
0x180003b92  mov     [r9], r13
0x180003b95  test    rdx, rdx
0x180003b98  jz      short loc_180003BFB
0x180003b9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003ba1  mov     ebx, 80040110h
0x180003ba6  test    rcx, rcx
0x180003ba9  jnz     short loc_180003BB9
0x180003bab  lea     rcx, qword_18000A4C0; this
0x180003bb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003bb9  cmp     [rcx+8], r13b
0x180003bbd  jz      short loc_180003BE4
0x180003bbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003bc4  cmp     [rax+7CCh], ebx
0x180003bca  jz      short loc_180003BE4
0x180003bcc  mov     r9d, ebx; int
0x180003bcf  lea     rdx, aCmsvpxdecoderc; "CMSVPxDecoderClassFactory::CreateInstan"...
0x180003bd6  mov     r8d, 4Ah ; 'J'; int
0x180003bdc  mov     rcx, rax; this
0x180003bdf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003be4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003beb  jb      loc_180003DFF
0x180003bf1  mov     edx, 0Bh
0x180003bf6  jmp     loc_180003DE8
0x180003bfb  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180003c02  xor     r9d, r9d; pOutputType
0x180003c05  lea     rax, [rsp+110h+var_E0]
0x180003c0a  mov     [rsp+110h+pnumMFTActivate], rax; pnumMFTActivate
0x180003c0f  lea     r8, [rbp+57h+pInputType]; pInputType
0x180003c13  lea     rax, [rsp+110h+var_D8]
0x180003c18  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x180003c1c  mov     [rsp+110h+pppMFTActivate], rax; pppMFTActivate
0x180003c21  lea     edx, [r9+40h]; Flags
0x180003c25  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x180003c2a  call    cs:__imp_MFTEnumEx
0x180003c30  mov     ebx, eax
0x180003c32  test    eax, eax
0x180003c34  jns     short loc_180003C92
0x180003c36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003c3d  test    rcx, rcx
0x180003c40  jnz     short loc_180003C50
0x180003c42  lea     rcx, qword_18000A4C0; this
0x180003c49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003c50  cmp     [rcx+8], r13b
0x180003c54  jz      short loc_180003C7B
0x180003c56  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003c5b  cmp     [rax+7CCh], ebx
0x180003c61  jz      short loc_180003C7B
0x180003c63  mov     r9d, ebx; int
0x180003c66  lea     rdx, aCmsvpxdecoderc; "CMSVPxDecoderClassFactory::CreateInstan"...
0x180003c6d  mov     r8d, 54h ; 'T'; int
0x180003c73  mov     rcx, rax; this
0x180003c76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003c7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003c82  jb      loc_180003DFF
0x180003c88  mov     edx, 0Ch
0x180003c8d  jmp     loc_180003DE8
0x180003c92  mov     esi, r13d
0x180003c95  cmp     [rsp+110h+var_E0], r13d
0x180003c9a  jbe     short loc_180003D17
0x180003c9c  mov     rax, [rsp+110h+var_D8]
0x180003ca1  lea     r8, [rsp+110h+var_DC]
0x180003ca6  mov     edi, esi
0x180003ca8  lea     rdx, MF_MEDIA_EXTENSION_PACKAGED_WINDOWS_SIGNED
0x180003caf  mov     [rsp+110h+var_DC], r13d
0x180003cb4  mov     rcx, [rax+rdi*8]
0x180003cb8  mov     rax, [rcx]
0x180003cbb  mov     rax, [rax+38h]
0x180003cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc4  test    eax, eax
0x180003cc6  jns     short loc_180003CD1
0x180003cc8  mov     eax, r13d
0x180003ccb  mov     [rsp+110h+var_DC], eax
0x180003ccf  jmp     short loc_180003CD5
0x180003cd1  mov     eax, [rsp+110h+var_DC]
0x180003cd5  test    eax, eax
0x180003cd7  jz      short loc_180003D0F
0x180003cd9  mov     rax, [rsp+110h+var_D8]
0x180003cde  lea     rcx, [rbp+57h+var_D0]
0x180003ce2  mov     rdi, [rax+rdi*8]
0x180003ce6  mov     rax, [rdi]
0x180003ce9  mov     rbx, [rax+108h]
0x180003cf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003cf5  lea     r8, [rbp+57h+var_D0]
0x180003cf9  mov     rcx, rdi
0x180003cfc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003d03  mov     rax, rbx
0x180003d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0b  test    eax, eax
0x180003d0d  jns     short loc_180003D17
0x180003d0f  inc     esi
0x180003d11  cmp     esi, [rsp+110h+var_E0]
0x180003d15  jb      short loc_180003C9C
0x180003d17  mov     rcx, [rbp+57h+var_D0]
0x180003d1b  test    rcx, rcx
0x180003d1e  jnz     short loc_180003D7E
0x180003d20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003d27  mov     ebx, 0C00D5212h
0x180003d2c  test    rcx, rcx
0x180003d2f  jnz     short loc_180003D3F
0x180003d31  lea     rcx, qword_18000A4C0; this
0x180003d38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003d3f  cmp     [rcx+8], r13b
0x180003d43  jz      short loc_180003D6A
0x180003d45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003d4a  cmp     [rax+7CCh], ebx
0x180003d50  jz      short loc_180003D6A
0x180003d52  mov     r9d, ebx; int
0x180003d55  lea     rdx, aCmsvpxdecoderc; "CMSVPxDecoderClassFactory::CreateInstan"...
0x180003d5c  mov     r8d, 5Fh ; '_'; int
0x180003d62  mov     rcx, rax; this
0x180003d65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003d6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003d71  jb      loc_180003DFF
0x180003d77  mov     edx, 0Dh
0x180003d7c  jmp     short loc_180003DE8
0x180003d7e  mov     rax, [rcx]
0x180003d81  mov     r8, r15
0x180003d84  mov     rdx, r12
0x180003d87  mov     rax, [rax]
0x180003d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8f  mov     ebx, eax
0x180003d91  test    eax, eax
0x180003d93  jns     short loc_180003DFF
0x180003d95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003d9c  test    rcx, rcx
0x180003d9f  jnz     short loc_180003DAF
0x180003da1  lea     rcx, qword_18000A4C0; this
0x180003da8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003daf  cmp     [rcx+8], r13b
0x180003db3  jz      short loc_180003DDA
0x180003db5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003dba  cmp     [rax+7CCh], ebx
0x180003dc0  jz      short loc_180003DDA
0x180003dc2  mov     r9d, ebx; int
0x180003dc5  lea     rdx, aCmsvpxdecoderc; "CMSVPxDecoderClassFactory::CreateInstan"...
0x180003dcc  mov     r8d, 60h ; '`'; int
0x180003dd2  mov     rcx, rax; this
0x180003dd5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003dda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180003de1  jb      short loc_180003DFF
0x180003de3  mov     edx, 0Eh
0x180003de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003def  mov     r9, r14
0x180003df2  mov     dword ptr [rsp+110h+pppMFTActivate], ebx
0x180003df6  mov     rcx, [rcx+10h]
0x180003dfa  call    WPP_SF_qd
0x180003dff  mov     edi, r13d
0x180003e02  cmp     [rsp+110h+var_E0], r13d
0x180003e07  jbe     short loc_180003E36
0x180003e09  mov     rax, [rsp+110h+var_D8]
0x180003e0e  mov     esi, edi
0x180003e10  mov     rcx, [rax+rsi*8]
0x180003e14  test    rcx, rcx
0x180003e17  jz      short loc_180003E2E
0x180003e19  mov     rax, [rcx]
0x180003e1c  mov     rax, [rax+10h]
0x180003e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e25  mov     rax, [rsp+110h+var_D8]
0x180003e2a  mov     [rax+rsi*8], r13
0x180003e2e  inc     edi
0x180003e30  cmp     edi, [rsp+110h+var_E0]
0x180003e34  jb      short loc_180003E09
0x180003e36  mov     rcx, [rsp+110h+var_D8]; pv
0x180003e3b  call    cs:__imp_CoTaskMemFree
0x180003e41  mov     esi, 10h
0x180003e46  lea     rdi, ?g_InstanceGuid@@3U_GUID@@A; _GUID g_InstanceGuid
0x180003e4d  mov     r8d, esi; Size
0x180003e50  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180003e57  mov     rcx, rdi; Buf1
0x180003e5a  call    memcmp_0
0x180003e5f  test    eax, eax
0x180003e61  jnz     loc_180003EE7
0x180003e67  mov     rcx, rdi; pguid
0x180003e6a  call    cs:__imp_CoCreateGuid
0x180003e70  test    eax, eax
0x180003e72  js      short loc_180003EE7
0x180003e74  mov     eax, cs:dword_18000A058
0x180003e7a  cmp     eax, 4
0x180003e7d  jbe     short loc_180003EE7
0x180003e7f  call    _tlgKeywordOn
0x180003e84  test    al, al
0x180003e86  jz      short loc_180003EE7
0x180003e88  lea     rax, [rbp+57h+guidCategory]
0x180003e8c  mov     qword ptr [rbp+57h+guidCategory.Data1], 1000000h
0x180003e94  mov     [rbp+57h+var_50], rax
0x180003e98  lea     rdx, byte_180007DE1
0x180003e9f  lea     rax, [rsp+110h+var_DC]
0x180003ea4  mov     [rsp+110h+var_DC], ebx
0x180003ea8  mov     [rbp+57h+var_70], rax
0x180003eac  lea     rcx, dword_18000A058
0x180003eb3  lea     rax, [rbp+57h+var_90]
0x180003eb7  mov     [rbp+57h+var_48], 8
0x180003ebf  mov     [rsp+110h+pnumMFTActivate], rax
0x180003ec4  xor     r9d, r9d
0x180003ec7  xor     r8d, r8d
0x180003eca  mov     dword ptr [rsp+110h+pppMFTActivate], 5
0x180003ed2  mov     [rbp+57h+var_60], rdi
0x180003ed6  mov     [rbp+57h+var_58], rsi
0x180003eda  mov     [rbp+57h+var_68], 4
0x180003ee2  call    _tlgWriteTransfer_EventWriteTransfer
0x180003ee7  lea     rcx, [rbp+57h+var_D0]
0x180003eeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003ef0  mov     eax, ebx
0x180003ef2  mov     rcx, [rbp+57h+var_40]
0x180003ef6  xor     rcx, rsp; StackCookie
0x180003ef9  call    __security_check_cookie
0x180003efe  mov     rbx, [rsp+110h+arg_8]
0x180003f06  add     rsp, 0E0h
0x180003f0d  pop     r15
0x180003f0f  pop     r14
0x180003f11  pop     r13
0x180003f13  pop     r12
0x180003f15  pop     rdi
0x180003f16  pop     rsi
0x180003f17  pop     rbp
0x180003f18  retn
```
