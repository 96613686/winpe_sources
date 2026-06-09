# CHost::RunXMLScript(IMoniker *,ushort const *)

- ea: `0x1400069d0`
- end: `0x140006f07`
- name: `?RunXMLScript@CHost@@IEAAJPEAUIMoniker@@PEBG@Z`
- size: `1335`
- prototype: `__int64 __fastcall(CHost *__hidden this, struct IMoniker *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400014b0`

## callees

- `0x1400069d0`
- `0x140009474`
- `0x1400096bc`
- `0x1400097d0`
- `0x1400098ac`
- `0x14000fa78`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x140006ad0`
- `KERNEL32!GetUserDefaultLCID` at `0x140006ad0`
- `ole32!CoGetClassObject` at `0x140006b6c`
- `ole32!CoGetClassObject` at `0x140006b6c`
- `ole32!CoCreateInstance` at `0x140006a92`
- `ole32!CoCreateInstance` at `0x140006ab7`
- `ole32!CoCreateInstance` at `0x140006a92`
- `ole32!CoCreateInstance` at `0x140006ab7`
- `ole32!CreateBindCtx` at `0x140006cd6`
- `ole32!CreateBindCtx` at `0x140006cd6`
- `USER32!SendMessageA` at `0x140006eb9`
- `USER32!SendMessageA` at `0x140006eb9`

## pseudocode

```c
__int64 __fastcall CHost::RunXMLScript(CHost *this, struct IMoniker *a2, unsigned __int16 *a3)
{
  struct IScriptletContext **ppv; // rdi
  __int64 v5; // rcx
  struct XMLScrServProv *v7; // r15
  struct XMLScrSite *v8; // r14
  __int64 v9; // rcx
  HRESULT ClassObject; // ebx
  LCID UserDefaultLCID; // eax
  struct IScriptletContext *v12; // rcx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  int v19; // eax
  int Error; // eax
  struct IScriptletContext *v21; // r8
  unsigned __int16 *v22; // rdi
  int v23; // eax
  __int64 v24; // rcx
  HWND v25; // rcx
  __int64 v27; // [rsp+40h] [rbp-59h] BYREF
  struct XMLScrServProv *v28; // [rsp+48h] [rbp-51h] BYREF
  LPBC ppbc; // [rsp+50h] [rbp-49h] BYREF
  __int64 v30; // [rsp+58h] [rbp-41h] BYREF
  struct XMLScrSite *v31; // [rsp+60h] [rbp-39h] BYREF
  __int64 v32; // [rsp+68h] [rbp-31h] BYREF
  LPVOID v33; // [rsp+70h] [rbp-29h] BYREF
  __int64 v34; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 *v35; // [rsp+80h] [rbp-19h]
  __int128 v36; // [rsp+88h] [rbp-11h] BYREF
  __int64 v37; // [rsp+98h] [rbp-1h]
  __int128 v38; // [rsp+A0h] [rbp+7h] BYREF

  v35 = a3;
  v27 = 0;
  ppv = (struct IScriptletContext **)((char *)this + 680);
  v37 = 0;
  v30 = 0;
  v5 = *((_QWORD *)this + 85);
  v28 = 0;
  v33 = 0;
  v34 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v32 = 0;
  ppbc = 0;
  v38 = 0;
  v36 = 0;
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *ppv = 0;
  }
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 4) = 0;
  }
  if ( CoCreateInstance(&CLSID_ScriptletContext2, 0, 1u, &IID_IScriptletContext, (LPVOID *)ppv) >= 0
    || (ClassObject = CoCreateInstance(&CLSID_ScriptletContext, 0, 1u, &IID_IScriptletContext, (LPVOID *)ppv),
        ClassObject >= 0) )
  {
    LOWORD(v36) = 3;
    UserDefaultLCID = GetUserDefaultLCID();
    v12 = *ppv;
    DWORD2(v36) = UserDefaultLCID;
    ClassObject = (*(__int64 (__fastcall **)(struct IScriptletContext *, __int64, _QWORD, __int128 *))(*(_QWORD *)v12 + 56LL))(
                    v12,
                    1,
                    0,
                    &v36);
    if ( ClassObject >= 0 )
    {
      ClassObject = XMLScrServProv::Create(*ppv, &v28);
      if ( ClassObject < 0
        || (v13 = XMLScrSite::Create(this, *ppv, &v31), v8 = v31, ClassObject = v13, v13 < 0)
        || (ClassObject = (*(__int64 (__fastcall **)(struct IScriptletContext *, struct XMLScrSite *))(*(_QWORD *)*ppv + 24LL))(
                            *ppv,
                            v31),
            ClassObject < 0)
        || (ClassObject = CoGetClassObject(&CLSID_ScriptletConstructor, 1u, 0, &IID_IClassFactory3, &v33),
            ClassObject < 0) )
      {
        v7 = v28;
      }
      else
      {
        v7 = v28;
        ClassObject = (*(__int64 (__fastcall **)(LPVOID, struct XMLScrServProv *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v33 + 40LL))(
                        v33,
                        v28,
                        0,
                        &IID_IScriptletConstructor,
                        &v27);
        if ( ClassObject >= 0 )
        {
          v14 = 34;
          if ( !*((_BYTE *)this + 71) )
            v14 = 2;
          v15 = *((_DWORD *)this + 19);
          v16 = v14 | 0x40;
          if ( !v15 )
            v16 = v14;
          if ( v15 != 1 || *((_BYTE *)this + 68) )
            v16 |= 0x80u;
          v17 = v16 | 0x100;
          if ( !*((_BYTE *)this + 74) )
            v17 = v16;
          v18 = v17;
          LODWORD(v18) = v17 | 0x200;
          if ( !*((_BYTE *)this + 75) )
            v18 = v17;
          ClassObject = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 24LL))(v27, v18);
          if ( ClassObject >= 0 )
          {
            ClassObject = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
                            v27,
                            &IID_IScriptletConstructorWSH,
                            &v30);
            if ( ClassObject >= 0 )
            {
              ClassObject = (**(__int64 (__fastcall ***)(__int64, __int64 *, char *))v27)(
                              v27,
                              qword_140019BB0,
                              (char *)this + 32);
              if ( ClassObject >= 0 )
              {
                ClassObject = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v30 + 24LL))(
                                v30,
                                L"WScript",
                                2);
                if ( ClassObject >= 0 )
                {
                  ClassObject = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v30 + 24LL))(
                                  v30,
                                  L"WSH",
                                  2);
                  if ( ClassObject >= 0 )
                  {
                    ClassObject = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
                                    v27,
                                    &IID_IPersistMoniker,
                                    &v32);
                    if ( ClassObject >= 0 )
                    {
                      ClassObject = CreateBindCtx(0, &ppbc);
                      if ( ClassObject >= 0 )
                      {
                        v38 = 0x10u;
                        ClassObject = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(
                                        ppbc,
                                        &v38);
                        if ( ClassObject >= 0 )
                        {
                          v19 = (*(__int64 (__fastcall **)(__int64, __int64, struct IMoniker *, LPBC, _DWORD))(*(_QWORD *)v32 + 40LL))(
                                  v32,
                                  1,
                                  a2,
                                  ppbc,
                                  0);
                          ClassObject = v19;
                          if ( v19 >= 0 )
                          {
                            if ( !*((_BYTE *)this + 69)
                              || (ClassObject = CTimer::Start(*((CTimer **)this + 81), *((_DWORD *)this + 11)),
                                  ClassObject >= 0) )
                            {
                              v21 = *ppv;
                              v22 = v35;
                              v23 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IScriptletContext *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                      v27,
                                      v35,
                                      v21,
                                      0,
                                      &IID_IUnknown,
                                      &v34);
                              ClassObject = v23;
                              if ( v23 >= 0 )
                              {
                                ClassObject = 0;
                                goto LABEL_46;
                              }
                              if ( v23 == -2147024809 )
                              {
                                Error = CHost::ReportError(this, Global::g_lResourceBase + 21, 0xCF7u, v22);
LABEL_40:
                                ClassObject = Error;
                                if ( Error >= 0 )
                                  goto LABEL_46;
                              }
                            }
                          }
                          else if ( v19 != -2147352319 )
                          {
                            Error = CHost::ReportLoadError(this, 0x80070002);
                            goto LABEL_40;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v24 = *((_QWORD *)this + 4);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 4) = 0;
  }
LABEL_46:
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v7 )
    (*(void (__fastcall **)(struct XMLScrServProv *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v8 )
    (*(void (__fastcall **)(struct XMLScrSite *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v33 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  v25 = (HWND)**((_QWORD **)this + 81);
  if ( v25 )
    SendMessageA(v25, 0x402u, 0, 0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 10, 0, 0) == -2147155970 )
    (*(void (__fastcall **)(CHost *))(*(_QWORD *)this + 64LL))(this);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1400069d0  mov     [rsp-8+arg_18], rbx
0x1400069d5  push    rbp
0x1400069d6  push    rsi
0x1400069d7  push    rdi
0x1400069d8  push    r12
0x1400069da  push    r13
0x1400069dc  push    r14
0x1400069de  push    r15
0x1400069e0  lea     rbp, [rsp-27h]
0x1400069e5  sub     rsp, 0C0h
0x1400069ec  mov     rax, cs:__security_cookie
0x1400069f3  xor     rax, rsp
0x1400069f6  mov     [rbp+57h+var_40], rax
0x1400069fa  xor     ebx, ebx
0x1400069fc  mov     [rbp+57h+var_70], r8
0x140006a00  xor     eax, eax
0x140006a02  mov     [rbp+57h+var_B0], rbx
0x140006a06  lea     rdi, [rcx+2A8h]
0x140006a0d  mov     [rbp+57h+var_58], rax
0x140006a11  mov     rsi, rcx
0x140006a14  mov     [rbp+57h+var_98], rbx
0x140006a18  mov     rcx, [rdi]
0x140006a1b  xorps   xmm0, xmm0
0x140006a1e  mov     [rbp+57h+var_A8], rbx
0x140006a22  xorps   xmm1, xmm1
0x140006a25  mov     [rbp+57h+var_80], rbx
0x140006a29  mov     r13, rdx
0x140006a2c  mov     [rbp+57h+var_78], rbx
0x140006a30  mov     r15d, ebx
0x140006a33  mov     [rbp+57h+var_90], rbx
0x140006a37  mov     r14d, ebx
0x140006a3a  mov     [rbp+57h+var_88], rbx
0x140006a3e  mov     [rbp+57h+ppbc], rbx
0x140006a42  movups  [rbp+57h+var_50], xmm0
0x140006a46  movups  [rbp+57h+var_68], xmm1
0x140006a4a  test    rcx, rcx
0x140006a4d  jz      short loc_140006A5E
0x140006a4f  mov     rax, [rcx]
0x140006a52  mov     rax, [rax+10h]
0x140006a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a5b  mov     [rdi], rbx
0x140006a5e  mov     rcx, [rsi+20h]
0x140006a62  test    rcx, rcx
0x140006a65  jz      short loc_140006A77
0x140006a67  mov     rax, [rcx]
0x140006a6a  mov     rax, [rax+10h]
0x140006a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a73  mov     [rsi+20h], rbx
0x140006a77  lea     r9, IID_IScriptletContext; riid
0x140006a7e  mov     [rsp+0F0h+ppv], rdi; ppv
0x140006a83  xor     edx, edx; pUnkOuter
0x140006a85  lea     rcx, CLSID_ScriptletContext2; rclsid
0x140006a8c  mov     r8d, 1; dwClsContext
0x140006a92  call    cs:__imp_CoCreateInstance
0x140006a98  test    eax, eax
0x140006a9a  jns     short loc_140006AC7
0x140006a9c  lea     r9, IID_IScriptletContext; riid
0x140006aa3  mov     [rsp+0F0h+ppv], rdi; ppv
0x140006aa8  xor     edx, edx; pUnkOuter
0x140006aaa  lea     rcx, CLSID_ScriptletContext; rclsid
0x140006ab1  mov     r8d, 1; dwClsContext
0x140006ab7  call    cs:__imp_CoCreateInstance
0x140006abd  mov     ebx, eax
0x140006abf  test    eax, eax
0x140006ac1  js      loc_140006DDC
0x140006ac7  mov     eax, 3
0x140006acc  mov     word ptr [rbp+57h+var_68], ax
0x140006ad0  call    cs:__imp_GetUserDefaultLCID
0x140006ad6  mov     rcx, [rdi]
0x140006ad9  lea     r9, [rbp+57h+var_68]
0x140006add  mov     dword ptr [rbp+57h+var_68+8], eax
0x140006ae0  xor     r8d, r8d
0x140006ae3  mov     edx, 1
0x140006ae8  mov     rax, [rcx]
0x140006aeb  mov     rax, [rax+38h]
0x140006aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006af4  mov     ebx, eax
0x140006af6  test    eax, eax
0x140006af8  js      loc_140006DDC
0x140006afe  mov     rcx, [rdi]; struct IScriptletContext *
0x140006b01  lea     rdx, [rbp+57h+var_A8]; struct XMLScrServProv **
0x140006b05  call    ?Create@XMLScrServProv@@SAJPEAUIScriptletContext@@PEAPEAV1@@Z; XMLScrServProv::Create(IScriptletContext *,XMLScrServProv * *)
0x140006b0a  mov     ebx, eax
0x140006b0c  test    eax, eax
0x140006b0e  js      loc_140006DD8
0x140006b14  mov     rdx, [rdi]; struct IScriptletContext *
0x140006b17  lea     r8, [rbp+57h+var_90]; struct XMLScrSite **
0x140006b1b  mov     rcx, rsi; struct CHost *
0x140006b1e  call    ?Create@XMLScrSite@@SAJPEAVCHost@@PEAUIScriptletContext@@PEAPEAV1@@Z; XMLScrSite::Create(CHost *,IScriptletContext *,XMLScrSite * *)
0x140006b23  mov     r14, [rbp+57h+var_90]
0x140006b27  mov     ebx, eax
0x140006b29  test    eax, eax
0x140006b2b  js      loc_140006DD8
0x140006b31  mov     rcx, [rdi]
0x140006b34  mov     rdx, r14
0x140006b37  mov     rax, [rcx]
0x140006b3a  mov     rax, [rax+18h]
0x140006b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b43  mov     ebx, eax
0x140006b45  test    eax, eax
0x140006b47  js      loc_140006DD8
0x140006b4d  lea     rax, [rbp+57h+var_80]
0x140006b51  xor     r8d, r8d; pvReserved
0x140006b54  lea     r9, IID_IClassFactory3; riid
0x140006b5b  mov     [rsp+0F0h+ppv], rax; ppv
0x140006b60  mov     edx, 1; dwClsContext
0x140006b65  lea     rcx, CLSID_ScriptletConstructor; rclsid
0x140006b6c  call    cs:__imp_CoGetClassObject
0x140006b72  mov     ebx, eax
0x140006b74  test    eax, eax
0x140006b76  js      loc_140006DD8
0x140006b7c  mov     rcx, [rbp+57h+var_80]
0x140006b80  lea     rdx, [rbp+57h+var_B0]
0x140006b84  mov     r15, [rbp+57h+var_A8]
0x140006b88  lea     r9, IID_IScriptletConstructor
0x140006b8f  mov     [rsp+0F0h+ppv], rdx
0x140006b94  xor     r8d, r8d
0x140006b97  mov     rdx, r15
0x140006b9a  mov     rax, [rcx]
0x140006b9d  mov     rax, [rax+28h]
0x140006ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ba6  mov     ebx, eax
0x140006ba8  test    eax, eax
0x140006baa  js      loc_140006DDC
0x140006bb0  cmp     byte ptr [rsi+47h], 0
0x140006bb4  mov     eax, 2
0x140006bb9  mov     ecx, 22h ; '"'
0x140006bbe  cmovz   ecx, eax
0x140006bc1  mov     eax, [rsi+4Ch]
0x140006bc4  mov     edx, ecx
0x140006bc6  or      edx, 40h
0x140006bc9  test    eax, eax
0x140006bcb  cmovz   edx, ecx
0x140006bce  cmp     eax, 1
0x140006bd1  jnz     short loc_140006BD9
0x140006bd3  cmp     byte ptr [rsi+44h], 0
0x140006bd7  jz      short loc_140006BDD
0x140006bd9  bts     edx, 7
0x140006bdd  mov     rcx, [rbp+57h+var_B0]
0x140006be1  mov     r8d, edx
0x140006be4  bts     r8d, 8
0x140006be9  cmp     byte ptr [rsi+4Ah], 0
0x140006bed  mov     rax, [rcx]
0x140006bf0  cmovz   r8d, edx
0x140006bf4  mov     edx, r8d
0x140006bf7  bts     edx, 9
0x140006bfb  cmp     byte ptr [rsi+4Bh], 0
0x140006bff  mov     rax, [rax+18h]
0x140006c03  cmovz   edx, r8d
0x140006c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c0c  mov     ebx, eax
0x140006c0e  test    eax, eax
0x140006c10  js      loc_140006DDC
0x140006c16  mov     rcx, [rbp+57h+var_B0]
0x140006c1a  lea     r8, [rbp+57h+var_98]
0x140006c1e  lea     rdx, IID_IScriptletConstructorWSH
0x140006c25  mov     rax, [rcx]
0x140006c28  mov     rax, [rax]
0x140006c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c30  mov     ebx, eax
0x140006c32  test    eax, eax
0x140006c34  js      loc_140006DDC
0x140006c3a  mov     rcx, [rbp+57h+var_B0]
0x140006c3e  lea     r8, [rsi+20h]
0x140006c42  lea     rdx, qword_140019BB0
0x140006c49  mov     rax, [rcx]
0x140006c4c  mov     rax, [rax]
0x140006c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c54  mov     ebx, eax
0x140006c56  test    eax, eax
0x140006c58  js      loc_140006DDC
0x140006c5e  mov     rcx, [rbp+57h+var_98]
0x140006c62  lea     rdx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x140006c69  mov     r8d, 2
0x140006c6f  mov     rax, [rcx]
0x140006c72  mov     rax, [rax+18h]
0x140006c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c7b  mov     ebx, eax
0x140006c7d  test    eax, eax
0x140006c7f  js      loc_140006DDC
0x140006c85  mov     rcx, [rbp+57h+var_98]
0x140006c89  lea     rdx, ?GWSZ_WSH@@3QBGB; "WSH"
0x140006c90  mov     r8d, 2
0x140006c96  mov     rax, [rcx]
0x140006c99  mov     rax, [rax+18h]
0x140006c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ca2  mov     ebx, eax
0x140006ca4  test    eax, eax
0x140006ca6  js      loc_140006DDC
0x140006cac  mov     rcx, [rbp+57h+var_B0]
0x140006cb0  lea     r8, [rbp+57h+var_88]
0x140006cb4  lea     rdx, IID_IPersistMoniker
0x140006cbb  mov     rax, [rcx]
0x140006cbe  mov     rax, [rax]
0x140006cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cc6  mov     ebx, eax
0x140006cc8  test    eax, eax
0x140006cca  js      loc_140006DDC
0x140006cd0  lea     rdx, [rbp+57h+ppbc]; ppbc
0x140006cd4  xor     ecx, ecx; reserved
0x140006cd6  call    cs:__imp_CreateBindCtx
0x140006cdc  mov     ebx, eax
0x140006cde  test    eax, eax
0x140006ce0  js      loc_140006DDC
0x140006ce6  mov     rcx, [rbp+57h+ppbc]
0x140006cea  lea     rdx, [rbp+57h+var_50]
0x140006cee  mov     qword ptr [rbp+57h+var_50], 10h
0x140006cf6  mov     qword ptr [rbp+57h+var_50+8], 0
0x140006cfe  mov     rax, [rcx]
0x140006d01  mov     rax, [rax+30h]
0x140006d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d0a  mov     ebx, eax
0x140006d0c  test    eax, eax
0x140006d0e  js      loc_140006DDC
0x140006d14  mov     rcx, [rbp+57h+var_88]
0x140006d18  mov     r8, r13
0x140006d1b  mov     r9, [rbp+57h+ppbc]
0x140006d1f  mov     edx, 1
0x140006d24  mov     dword ptr [rsp+0F0h+ppv], 0
0x140006d2c  mov     rax, [rcx]
0x140006d2f  mov     rax, [rax+28h]
0x140006d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d38  mov     ebx, eax
0x140006d3a  test    eax, eax
0x140006d3c  jns     short loc_140006D58
0x140006d3e  cmp     eax, 80020101h
0x140006d43  jz      loc_140006DDC
0x140006d49  mov     edx, 80070002h; dwMessageId
0x140006d4e  mov     rcx, rsi; this
0x140006d51  call    ?ReportLoadError@CHost@@QEAAJJ@Z; CHost::ReportLoadError(long)
0x140006d56  jmp     short loc_140006DCC
0x140006d58  cmp     byte ptr [rsi+45h], 0
0x140006d5c  jz      short loc_140006D73
0x140006d5e  mov     edx, [rsi+2Ch]; unsigned int
0x140006d61  mov     rcx, [rsi+288h]; this
0x140006d68  call    ?Start@CTimer@@QEAAJK@Z; CTimer::Start(ulong)
0x140006d6d  mov     ebx, eax
0x140006d6f  test    eax, eax
0x140006d71  js      short loc_140006DDC
0x140006d73  mov     rcx, [rbp+57h+var_B0]
0x140006d77  lea     rdx, [rbp+57h+var_78]
0x140006d7b  mov     r8, [rdi]
0x140006d7e  xor     r9d, r9d
0x140006d81  mov     rdi, [rbp+57h+var_70]
0x140006d85  mov     [rsp+0F0h+var_C8], rdx
0x140006d8a  lea     rdx, IID_IUnknown
0x140006d91  mov     rax, [rcx]
0x140006d94  mov     [rsp+0F0h+ppv], rdx
0x140006d99  mov     rdx, rdi
0x140006d9c  mov     rax, [rax+20h]
0x140006da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006da5  mov     ebx, eax
0x140006da7  test    eax, eax
0x140006da9  jns     short loc_140006DD4
0x140006dab  cmp     eax, 80070057h
0x140006db0  jnz     short loc_140006DDC
0x140006db2  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140006db8  mov     r9, rdi; unsigned __int16 *
0x140006dbb  add     edx, 15h; unsigned int
0x140006dbe  mov     r8d, 0CF7h; unsigned int
0x140006dc4  mov     rcx, rsi; this
0x140006dc7  call    ?ReportError@CHost@@QEAAJIIPEBG@Z; CHost::ReportError(uint,uint,ushort const *)
0x140006dcc  mov     ebx, eax
0x140006dce  test    eax, eax
0x140006dd0  js      short loc_140006DDC
0x140006dd2  jmp     short loc_140006DF9
0x140006dd4  xor     ebx, ebx
0x140006dd6  jmp     short loc_140006DF9
0x140006dd8  mov     r15, [rbp+57h+var_A8]
0x140006ddc  mov     rcx, [rsi+20h]
0x140006de0  test    rcx, rcx
0x140006de3  jz      short loc_140006DF9
0x140006de5  mov     rax, [rcx]
0x140006de8  mov     rax, [rax+10h]
0x140006dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006df1  mov     qword ptr [rsi+20h], 0
0x140006df9  mov     rcx, [rbp+57h+ppbc]
0x140006dfd  test    rcx, rcx
0x140006e00  jz      short loc_140006E0E
0x140006e02  mov     rax, [rcx]
0x140006e05  mov     rax, [rax+10h]
0x140006e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e0e  mov     rcx, [rbp+57h+var_88]
0x140006e12  test    rcx, rcx
0x140006e15  jz      short loc_140006E23
0x140006e17  mov     rax, [rcx]
0x140006e1a  mov     rax, [rax+10h]
0x140006e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e23  mov     rcx, [rbp+57h+var_78]
0x140006e27  test    rcx, rcx
0x140006e2a  jz      short loc_140006E38
0x140006e2c  mov     rax, [rcx]
0x140006e2f  mov     rax, [rax+10h]
0x140006e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e38  mov     rcx, [rbp+57h+var_B0]
0x140006e3c  test    rcx, rcx
0x140006e3f  jz      short loc_140006E4D
0x140006e41  mov     rax, [rcx]
0x140006e44  mov     rax, [rax+10h]
0x140006e48  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
