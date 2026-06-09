# CMimeActiveUrlCache::ActiveObjectFromMoniker(__MIDL_IBindStatusCallback_0003,IMoniker *,IBindCtx *,_GUID const &,void * *,IMoniker * *)

- ea: `0x180034b20`
- end: `0x180034f26`
- name: `?ActiveObjectFromMoniker@CMimeActiveUrlCache@@UEAAJW4__MIDL_IBindStatusCallback_0003@@PEAUIMoniker@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAXPEAPEAU3@@Z`
- size: `1030`
- prototype: `int(CMimeActiveUrlCache *__hidden this, enum __MIDL_IBindStatusCallback_0003, struct IMoniker *, struct IBindCtx *, const struct _GUID *, void **, struct IMoniker **)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180002098`
- `0x180004d60`
- `0x180004f40`
- `0x180012590`
- `0x180015858`
- `0x180021a14`
- `0x1800227b0`
- `0x180034b20`
- `0x1800356a8`
- `0x18003686c`
- `0x180037570`
- `0x180037f8c`
- `0x18003845c`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!ReplaceCharsW` at `0x180034c84`
- `MSOERT2!ReplaceCharsW` at `0x180034c84`
- `KERNEL32!LeaveCriticalSection` at `0x180034e5e`
- `KERNEL32!LeaveCriticalSection` at `0x180034e5e`
- `KERNEL32!EnterCriticalSection` at `0x180034e1c`
- `KERNEL32!EnterCriticalSection` at `0x180034e1c`
- `urlmon!CreateURLMoniker` at `0x180034d27`
- `urlmon!CreateURLMoniker` at `0x180034d27`

## pseudocode

```c
__int64 __fastcall CMimeActiveUrlCache::ActiveObjectFromMoniker(
        CMimeActiveUrlCache *this,
        enum __MIDL_IBindStatusCallback_0003 a2,
        struct IMoniker *a3,
        struct IBindCtx *a4,
        const struct _GUID *a5,
        void **a6,
        struct IMoniker **a7)
{
  const unsigned __int16 *v7; // rsi
  _QWORD *v10; // r11
  HRESULT v11; // ebx
  int v12; // r13d
  const unsigned __int16 *v13; // r15
  const WCHAR *v14; // rcx
  PCWSTR v15; // rcx
  const WCHAR *v16; // rcx
  CMimeActiveUrlCache *v17; // rdi
  int v18; // eax
  enum __MIDL_IBindStatusCallback_0003 v19; // r15d
  const struct _GUID *v20; // rdx
  struct CActiveUrl *v21; // rdi
  struct IObjectWithWeakBackReference *v22; // rcx
  enum __MIDL_IBindStatusCallback_0003 v23; // ebx
  const unsigned __int16 *v24; // r8
  const struct _GUID *v25; // rdx
  struct IObjectWithWeakBackReference *v26; // rcx
  __int64 v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, const struct _GUID *, void **); // rcx
  struct CActiveUrl *v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v31; // [rsp+38h] [rbp-C8h] BYREF
  __MIDL_IBindStatusCallback_0003 v32; // [rsp+40h] [rbp-C0h]
  void *v33; // [rsp+48h] [rbp-B8h] BYREF
  LPMONIKER ppmk; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR szURL; // [rsp+58h] [rbp-A8h]
  struct IMoniker **v36; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR psz1; // [rsp+70h] [rbp-90h]
  struct IBindCtx *v39; // [rsp+88h] [rbp-78h]
  void **v40; // [rsp+90h] [rbp-70h]
  const struct _GUID *v41; // [rsp+98h] [rbp-68h]
  __int128 v42; // [rsp+A0h] [rbp-60h] BYREF
  int v43; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v44[264]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = 0;
  v41 = a5;
  v32 = a2;
  v43 = 0;
  v33 = 0;
  v39 = a4;
  v40 = a6;
  v36 = a7;
  v31 = 0;
  szURL = 0;
  ppmk = 0;
  v30 = 0;
  v42 = 0;
  STRW::STRW((STRW *)&v37, v44, 0x104u);
  if ( !a3 || !a6 || !v10 )
  {
    STRW::~STRW((STRW *)&v37);
    return 2147942487LL;
  }
  *v10 = 0;
  *a6 = 0;
  v11 = ((__int64 (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, unsigned __int16 **))a3->lpVtbl->GetDisplayName)(
          a3,
          0,
          0,
          &v31);
  if ( v11 >= 0 )
  {
    v11 = STRW::Append((STRW *)&v37, v31);
    if ( v11 >= 0 )
    {
      if ( v31 )
      {
        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
        v31 = 0;
      }
      v11 = STRW::UrlUnescapeA((STRW *)&v37);
      if ( v11 >= 0 )
      {
        v12 = v37;
        v13 = &cchOriginalDestLength;
        v14 = &cchOriginalDestLength;
        if ( v37 )
          v14 = psz1;
        if ( !(unsigned int)IsMHTMLUrlW(v14) )
        {
          v15 = &cchOriginalDestLength;
          if ( v12 )
            v15 = psz1;
          ReplaceCharsW(v15, 33);
        }
        v16 = &cchOriginalDestLength;
        if ( v12 )
          v16 = psz1;
        v17 = (CMimeActiveUrlCache *)((char *)this - 32);
        v18 = MimeOleParseMhtmlUrlW(v16);
        v7 = szURL;
        if ( v18 < 0 )
        {
          v23 = v32;
          v24 = &cchOriginalDestLength;
          if ( v12 )
            v24 = psz1;
          CMimeActiveUrlCache::_HandlePragmaNoCache(v17, v32, v24);
          if ( v12 )
            v13 = psz1;
          if ( (int)CMimeActiveUrlCache::_ResolveUrl(v17, v13, &v30) >= 0 )
          {
            v21 = v30;
          }
          else
          {
            v11 = CMimeActiveUrlCache::_RegisterUrl(v17, 0, v23, &v30);
            if ( v11 < 0 )
              goto LABEL_48;
            v21 = v30;
            v26 = v30 ? (struct CActiveUrl *)((char *)v30 + 40) : 0LL;
            v11 = CUnkKeepAlive::CreateInstance(v26, v25, &v33);
            if ( v11 < 0 )
              goto LABEL_48;
            v11 = CActiveUrl::SetOriginalBindData(v21, a3, v39);
            if ( v11 < 0 )
              goto LABEL_48;
          }
          *(_QWORD *)&v42 = 0x2300000014LL;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v21 + 88));
          v27 = *((_QWORD *)v21 + 6);
          if ( v27 )
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD, struct IMoniker **))(*(_QWORD *)(v27 + 32) + 304LL))(
                    v27 + 32,
                    0,
                    &v42,
                    0,
                    v36);
          else
            v11 = -2147467259;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v21 + 88));
          if ( v11 >= 0 )
          {
LABEL_46:
            v28 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)v21 + 18);
            if ( v28 )
              v11 = (**v28)(v28, v41, v40);
          }
        }
        else
        {
          v19 = v32;
          CMimeActiveUrlCache::_HandlePragmaNoCache(v17, v32, szURL);
          if ( (int)CMimeActiveUrlCache::_ResolveUrl(v17, v7, &v30) >= 0 )
          {
            v21 = v30;
LABEL_28:
            *v36 = a3;
            ((void (__fastcall *)(struct IMoniker *))a3->lpVtbl->AddRef)(a3);
            goto LABEL_46;
          }
          v11 = CMimeActiveUrlCache::_RegisterUrl(v17, 0, v19, &v30);
          if ( v11 >= 0 )
          {
            v21 = v30;
            v22 = v30 ? (struct CActiveUrl *)((char *)v30 + 40) : 0LL;
            v11 = CUnkKeepAlive::CreateInstance(v22, v20, &v33);
            if ( v11 >= 0 )
            {
              v11 = CreateURLMoniker(0, v7, &ppmk);
              if ( v11 >= 0 )
              {
                v11 = CActiveUrl::SetOriginalBindData(v21, ppmk, 0);
                if ( v11 >= 0 )
                  goto LABEL_28;
              }
            }
          }
        }
      }
    }
  }
LABEL_48:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v33);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v30);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppmk);
  if ( v7 )
    ((void (__fastcall *)(LPMALLOC, const unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v7);
  if ( v31 )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    v31 = 0;
  }
  STRW::~STRW((STRW *)&v37);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180034b20  push    rbp
0x180034b22  push    rbx
0x180034b23  push    rsi
0x180034b24  push    rdi
0x180034b25  push    r13
0x180034b27  push    r14
0x180034b29  push    r15
0x180034b2b  lea     rbp, [rsp-1E0h]
0x180034b33  sub     rsp, 2E0h
0x180034b3a  mov     rax, cs:__security_cookie
0x180034b41  xor     rax, rsp
0x180034b44  mov     [rbp+210h+var_40], rax
0x180034b4b  mov     rax, [rbp+210h+arg_20]
0x180034b52  xor     esi, esi
0x180034b54  mov     rbx, [rbp+210h+arg_28]
0x180034b5b  mov     r14, r8
0x180034b5e  mov     r11, [rbp+210h+arg_30]
0x180034b65  mov     rdi, rcx
0x180034b68  mov     [rbp+210h+var_278], rax
0x180034b6c  lea     rcx, [rsp+310h+var_2A8]; this
0x180034b71  xor     eax, eax
0x180034b73  mov     [rsp+310h+var_2D0], edx
0x180034b77  xorps   xmm0, xmm0
0x180034b7a  mov     [rbp+210h+var_260], eax
0x180034b7d  mov     r8d, 104h; unsigned int
0x180034b83  mov     [rsp+310h+var_2C8], rax
0x180034b88  lea     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x180034b8c  mov     [rbp+210h+var_288], r9
0x180034b90  mov     [rbp+210h+var_280], rbx
0x180034b94  mov     [rsp+310h+var_2B0], r11
0x180034b99  mov     [rsp+310h+var_2D8], 0
0x180034ba2  mov     [rsp+310h+szURL], rsi
0x180034ba7  mov     [rsp+310h+ppmk], rsi
0x180034bac  mov     [rsp+310h+var_2E0], rsi
0x180034bb1  movups  [rbp+210h+var_270], xmm0
0x180034bb5  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180034bba  test    r14, r14
0x180034bbd  jz      loc_180034EF6
0x180034bc3  test    rbx, rbx
0x180034bc6  jz      loc_180034EF6
0x180034bcc  test    r11, r11
0x180034bcf  jz      loc_180034EF6
0x180034bd5  mov     [r11], rsi
0x180034bd8  lea     r9, [rsp+310h+var_2D8]
0x180034bdd  mov     [rbx], rsi
0x180034be0  xor     r8d, r8d
0x180034be3  mov     rax, [r14]
0x180034be6  xor     edx, edx
0x180034be8  mov     rcx, r14
0x180034beb  mov     rax, [rax+0A0h]
0x180034bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bf7  mov     ebx, eax
0x180034bf9  test    eax, eax
0x180034bfb  js      loc_180034E89
0x180034c01  mov     rdx, [rsp+310h+var_2D8]; unsigned __int16 *
0x180034c06  lea     rcx, [rsp+310h+var_2A8]; this
0x180034c0b  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180034c10  mov     ebx, eax
0x180034c12  test    eax, eax
0x180034c14  js      loc_180034E89
0x180034c1a  mov     rdx, [rsp+310h+var_2D8]
0x180034c1f  test    rdx, rdx
0x180034c22  jz      short loc_180034C3C
0x180034c24  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180034c2b  mov     rax, [rcx]
0x180034c2e  mov     rax, [rax+28h]
0x180034c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c37  mov     [rsp+310h+var_2D8], rsi
0x180034c3c  lea     rcx, [rsp+310h+var_2A8]; this
0x180034c41  call    ?UrlUnescapeA@STRW@@QEAAJXZ; STRW::UrlUnescapeA(void)
0x180034c46  mov     ebx, eax
0x180034c48  test    eax, eax
0x180034c4a  js      loc_180034E89
0x180034c50  mov     r13d, [rsp+310h+var_2A8]
0x180034c55  lea     r15, cchOriginalDestLength
0x180034c5c  test    r13d, r13d
0x180034c5f  mov     rcx, r15
0x180034c62  cmovnz  rcx, [rsp+310h+psz1]; psz1
0x180034c68  call    ?IsMHTMLUrlW@@YAHPEBG@Z; IsMHTMLUrlW(ushort const *)
0x180034c6d  test    eax, eax
0x180034c6f  jnz     short loc_180034C8A
0x180034c71  test    r13d, r13d
0x180034c74  lea     edx, [rax+21h]
0x180034c77  mov     rcx, r15
0x180034c7a  lea     r8d, [rax+5Fh]
0x180034c7e  cmovnz  rcx, [rsp+310h+psz1]
0x180034c84  call    cs:__imp_ReplaceCharsW
0x180034c8a  test    r13d, r13d
0x180034c8d  lea     rdx, [rsp+310h+szURL]
0x180034c92  mov     rcx, r15
0x180034c95  cmovnz  rcx, [rsp+310h+psz1]; psz1
0x180034c9b  xor     r8d, r8d
0x180034c9e  add     rdi, 0FFFFFFFFFFFFFFE0h
0x180034ca2  call    MimeOleParseMhtmlUrlW
0x180034ca7  mov     rsi, [rsp+310h+szURL]
0x180034cac  mov     rcx, rdi; this
0x180034caf  test    eax, eax
0x180034cb1  js      loc_180034D74
0x180034cb7  mov     r15d, [rsp+310h+var_2D0]
0x180034cbc  mov     r8, rsi; unsigned __int16 *
0x180034cbf  mov     edx, r15d; enum __MIDL_IBindStatusCallback_0003
0x180034cc2  call    ?_HandlePragmaNoCache@CMimeActiveUrlCache@@AEAAXW4__MIDL_IBindStatusCallback_0003@@PEBG@Z; CMimeActiveUrlCache::_HandlePragmaNoCache(__MIDL_IBindStatusCallback_0003,ushort const *)
0x180034cc7  lea     r8, [rsp+310h+var_2E0]; struct CActiveUrl **
0x180034ccc  mov     rdx, rsi; unsigned __int16 *
0x180034ccf  mov     rcx, rdi; this
0x180034cd2  call    ?_ResolveUrl@CMimeActiveUrlCache@@AEAAJPEBGPEAPEAVCActiveUrl@@@Z; CMimeActiveUrlCache::_ResolveUrl(ushort const *,CActiveUrl * *)
0x180034cd7  test    eax, eax
0x180034cd9  jns     short loc_180034D53
0x180034cdb  lea     r9, [rsp+310h+var_2E0]; struct CActiveUrl **
0x180034ce0  mov     r8d, r15d; enum __MIDL_IBindStatusCallback_0003
0x180034ce3  xor     edx, edx; struct CMessageTree *
0x180034ce5  mov     rcx, rdi; this
0x180034ce8  call    ?_RegisterUrl@CMimeActiveUrlCache@@AEAAJPEAVCMessageTree@@W4__MIDL_IBindStatusCallback_0003@@PEAPEAVCActiveUrl@@@Z; CMimeActiveUrlCache::_RegisterUrl(CMessageTree *,__MIDL_IBindStatusCallback_0003,CActiveUrl * *)
0x180034ced  mov     ebx, eax
0x180034cef  test    eax, eax
0x180034cf1  js      loc_180034E89
0x180034cf7  mov     rdi, [rsp+310h+var_2E0]
0x180034cfc  test    rdi, rdi
0x180034cff  jz      short loc_180034D07
0x180034d01  lea     rcx, [rdi+28h]
0x180034d05  jmp     short loc_180034D09
0x180034d07  xor     ecx, ecx; struct IObjectWithWeakBackReference *
0x180034d09  lea     r8, [rsp+310h+var_2C8]; void **
0x180034d0e  call    ?CreateInstance@CUnkKeepAlive@@SAJPEAUIObjectWithWeakBackReference@@AEBU_GUID@@PEAPEAX@Z; CUnkKeepAlive::CreateInstance(IObjectWithWeakBackReference *,_GUID const &,void * *)
0x180034d13  mov     ebx, eax
0x180034d15  test    eax, eax
0x180034d17  js      loc_180034E89
0x180034d1d  lea     r8, [rsp+310h+ppmk]; ppmk
0x180034d22  mov     rdx, rsi; szURL
0x180034d25  xor     ecx, ecx; pMkCtx
0x180034d27  call    cs:__imp_CreateURLMoniker
0x180034d2d  mov     ebx, eax
0x180034d2f  test    eax, eax
0x180034d31  js      loc_180034E89
0x180034d37  mov     rdx, [rsp+310h+ppmk]; struct IMoniker *
0x180034d3c  xor     r8d, r8d; struct IBindCtx *
0x180034d3f  mov     rcx, rdi; this
0x180034d42  call    ?SetOriginalBindData@CActiveUrl@@QEAAJPEAUIMoniker@@PEAUIBindCtx@@@Z; CActiveUrl::SetOriginalBindData(IMoniker *,IBindCtx *)
0x180034d47  mov     ebx, eax
0x180034d49  test    eax, eax
0x180034d4b  js      loc_180034E89
0x180034d51  jmp     short loc_180034D58
0x180034d53  mov     rdi, [rsp+310h+var_2E0]
0x180034d58  mov     rdx, [rsp+310h+var_2B0]
0x180034d5d  mov     rcx, r14
0x180034d60  mov     [rdx], r14
0x180034d63  mov     rax, [r14]
0x180034d66  mov     rax, [rax+8]
0x180034d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d6f  jmp     loc_180034E68
0x180034d74  mov     ebx, [rsp+310h+var_2D0]
0x180034d78  test    r13d, r13d
0x180034d7b  mov     r8, r15
0x180034d7e  mov     edx, ebx; enum __MIDL_IBindStatusCallback_0003
0x180034d80  cmovnz  r8, [rsp+310h+psz1]; unsigned __int16 *
0x180034d86  call    ?_HandlePragmaNoCache@CMimeActiveUrlCache@@AEAAXW4__MIDL_IBindStatusCallback_0003@@PEBG@Z; CMimeActiveUrlCache::_HandlePragmaNoCache(__MIDL_IBindStatusCallback_0003,ushort const *)
0x180034d8b  test    r13d, r13d
0x180034d8e  lea     r8, [rsp+310h+var_2E0]; struct CActiveUrl **
0x180034d93  mov     rcx, rdi; this
0x180034d96  cmovnz  r15, [rsp+310h+psz1]
0x180034d9c  mov     rdx, r15; unsigned __int16 *
0x180034d9f  call    ?_ResolveUrl@CMimeActiveUrlCache@@AEAAJPEBGPEAPEAVCActiveUrl@@@Z; CMimeActiveUrlCache::_ResolveUrl(ushort const *,CActiveUrl * *)
0x180034da4  test    eax, eax
0x180034da6  jns     short loc_180034E05
0x180034da8  lea     r9, [rsp+310h+var_2E0]; struct CActiveUrl **
0x180034dad  mov     r8d, ebx; enum __MIDL_IBindStatusCallback_0003
0x180034db0  xor     edx, edx; struct CMessageTree *
0x180034db2  mov     rcx, rdi; this
0x180034db5  call    ?_RegisterUrl@CMimeActiveUrlCache@@AEAAJPEAVCMessageTree@@W4__MIDL_IBindStatusCallback_0003@@PEAPEAVCActiveUrl@@@Z; CMimeActiveUrlCache::_RegisterUrl(CMessageTree *,__MIDL_IBindStatusCallback_0003,CActiveUrl * *)
0x180034dba  mov     ebx, eax
0x180034dbc  test    eax, eax
0x180034dbe  js      loc_180034E89
0x180034dc4  mov     rdi, [rsp+310h+var_2E0]
0x180034dc9  test    rdi, rdi
0x180034dcc  jz      short loc_180034DD4
0x180034dce  lea     rcx, [rdi+28h]
0x180034dd2  jmp     short loc_180034DD6
0x180034dd4  xor     ecx, ecx; struct IObjectWithWeakBackReference *
0x180034dd6  lea     r8, [rsp+310h+var_2C8]; void **
0x180034ddb  call    ?CreateInstance@CUnkKeepAlive@@SAJPEAUIObjectWithWeakBackReference@@AEBU_GUID@@PEAPEAX@Z; CUnkKeepAlive::CreateInstance(IObjectWithWeakBackReference *,_GUID const &,void * *)
0x180034de0  mov     ebx, eax
0x180034de2  test    eax, eax
0x180034de4  js      loc_180034E89
0x180034dea  mov     r8, [rbp+210h+var_288]; struct IBindCtx *
0x180034dee  mov     rdx, r14; struct IMoniker *
0x180034df1  mov     rcx, rdi; this
0x180034df4  call    ?SetOriginalBindData@CActiveUrl@@QEAAJPEAUIMoniker@@PEAUIBindCtx@@@Z; CActiveUrl::SetOriginalBindData(IMoniker *,IBindCtx *)
0x180034df9  mov     ebx, eax
0x180034dfb  test    eax, eax
0x180034dfd  js      loc_180034E89
0x180034e03  jmp     short loc_180034E0A
0x180034e05  mov     rdi, [rsp+310h+var_2E0]
0x180034e0a  lea     rcx, [rdi+58h]; lpCriticalSection
0x180034e0e  mov     dword ptr [rbp+210h+var_270], 14h
0x180034e15  mov     dword ptr [rbp+210h+var_270+4], 23h ; '#'
0x180034e1c  call    cs:__imp_EnterCriticalSection
0x180034e22  mov     rcx, [rdi+30h]
0x180034e26  test    rcx, rcx
0x180034e29  jnz     short loc_180034E32
0x180034e2b  mov     ebx, 80004005h
0x180034e30  jmp     short loc_180034E5A
0x180034e32  mov     rdx, [rsp+310h+var_2B0]
0x180034e37  lea     r8, [rbp+210h+var_270]
0x180034e3b  add     rcx, 20h ; ' '
0x180034e3f  mov     [rsp+310h+var_2F0], rdx
0x180034e44  xor     r9d, r9d
0x180034e47  xor     edx, edx
0x180034e49  mov     rax, [rcx]
0x180034e4c  mov     rax, [rax+130h]
0x180034e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e58  mov     ebx, eax
0x180034e5a  lea     rcx, [rdi+58h]; lpCriticalSection
0x180034e5e  call    cs:__imp_LeaveCriticalSection
0x180034e64  test    ebx, ebx
0x180034e66  js      short loc_180034E89
0x180034e68  mov     rcx, [rdi+90h]
0x180034e6f  test    rcx, rcx
0x180034e72  jz      short loc_180034E89
0x180034e74  mov     rax, [rcx]
0x180034e77  mov     r8, [rbp+210h+var_280]
0x180034e7b  mov     rdx, [rbp+210h+var_278]
0x180034e7f  mov     rax, [rax]
0x180034e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e87  mov     ebx, eax
0x180034e89  lea     rcx, [rsp+310h+var_2C8]
0x180034e8e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034e93  lea     rcx, [rsp+310h+var_2E0]
0x180034e98  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034e9d  lea     rcx, [rsp+310h+ppmk]
0x180034ea2  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034ea7  test    rsi, rsi
0x180034eaa  jz      short loc_180034EC2
0x180034eac  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180034eb3  mov     rdx, rsi
0x180034eb6  mov     rax, [rcx]
0x180034eb9  mov     rax, [rax+28h]
0x180034ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ec2  mov     rdx, [rsp+310h+var_2D8]
0x180034ec7  test    rdx, rdx
0x180034eca  jz      short loc_180034EE8
0x180034ecc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180034ed3  mov     rax, [rcx]
0x180034ed6  mov     rax, [rax+28h]
0x180034eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034edf  mov     [rsp+310h+var_2D8], 0
0x180034ee8  lea     rcx, [rsp+310h+var_2A8]; this
0x180034eed  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180034ef2  mov     eax, ebx
0x180034ef4  jmp     short loc_180034F05
0x180034ef6  lea     rcx, [rsp+310h+var_2A8]; this
0x180034efb  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180034f00  mov     eax, 80070057h
0x180034f05  mov     rcx, [rbp+210h+var_40]
0x180034f0c  xor     rcx, rsp; StackCookie
0x180034f0f  call    __security_check_cookie
0x180034f14  add     rsp, 2E0h
0x180034f1b  pop     r15
0x180034f1d  pop     r14
0x180034f1f  pop     r13
0x180034f21  pop     rdi
0x180034f22  pop     rsi
0x180034f23  pop     rbx
0x180034f24  pop     rbp
0x180034f25  retn
```
