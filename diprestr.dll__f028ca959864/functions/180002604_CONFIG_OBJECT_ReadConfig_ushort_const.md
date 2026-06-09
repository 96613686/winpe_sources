# CONFIG_OBJECT::ReadConfig(ushort const *)

- ea: `0x180002604`
- end: `0x180002dc8`
- name: `?ReadConfig@CONFIG_OBJECT@@AEAAJPEBG@Z`
- size: `1988`
- prototype: `__int64 __fastcall(CONFIG_OBJECT *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800055f0`

## callees

- `0x180001008`
- `0x180001948`
- `0x180001a2c`
- `0x180001fa4`
- `0x1800021c8`
- `0x180002230`
- `0x180002330`
- `0x180002428`
- `0x180002604`
- `0x180002dd0`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `msvcrt!malloc` at `0x180002a00`
- `msvcrt!malloc` at `0x180002a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002db8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000274b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000276f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000291f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000274b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000276f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000291f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c39`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c47`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c39`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c47`
- `OLEAUT32!__imp_VariantInit` at `0x180002687`
- `OLEAUT32!__imp_VariantInit` at `0x180002687`
- `OLEAUT32!__imp_VariantClear` at `0x180002c18`
- `OLEAUT32!__imp_VariantClear` at `0x180002c18`

## string_xrefs

- `0x180002768`: `system.webServer/security/dynamicIpSecurity`
- `0x180002918`: `system.webServer/security/ipSecurity`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT::ReadConfig(CONFIG_OBJECT *this, unsigned __int16 *a2)
{
  OLECHAR *v4; // r14
  OLECHAR *v5; // r13
  int appended; // ebx
  OLECHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rbx
  unsigned int v12; // edi
  void *v13; // rax
  int v14; // edx
  LONG v15; // r15d
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // r14
  const unsigned __int16 *v19; // rbx
  const unsigned __int16 *v20; // r12
  int v21; // edx
  _DWORD *v22; // rdi
  int v23; // edx
  HLOCAL v25; // rcx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-CCh] BYREF
  BSTR v28; // [rsp+38h] [rbp-C8h]
  struct IAppHostElement *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct IAppHostElement *v30; // [rsp+48h] [rbp-B8h] BYREF
  struct IAppHostElement *v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v32; // [rsp+58h] [rbp-A8h] BYREF
  struct IAppHostElement *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v37; // [rsp+90h] [rbp-70h] BYREF
  void **v38; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-48h]
  unsigned int v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C4h] [rbp-3Ch]
  _BYTE v42[68]; // [rsp+CCh] [rbp-34h] BYREF
  void **v43; // [rsp+110h] [rbp+10h] BYREF
  HLOCAL v44; // [rsp+118h] [rbp+18h]
  unsigned int v45; // [rsp+120h] [rbp+20h]
  _BYTE v46[68]; // [rsp+12Ch] [rbp+2Ch] BYREF
  void **v47; // [rsp+170h] [rbp+70h] BYREF
  OLECHAR *psz; // [rsp+178h] [rbp+78h]
  unsigned int v49; // [rsp+180h] [rbp+80h]
  char v50; // [rsp+18Ch] [rbp+8Ch] BYREF

  STBUFF::STBUFF((STBUFF *)&v47, (int)a2);
  bstrString = 0;
  v30 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v4 = 0;
  v5 = 0;
  v34 = 0;
  v33 = 0;
  v31 = 0;
  v29 = 0;
  v32 = 0;
  v26 = 0;
  VariantInit(&pvarg);
  pvarg.lVal = 0;
  pvarg.vt = 19;
  appended = STBUFF::Resize((STBUFF *)&v47, 0x30u);
  if ( appended < 0 )
    goto LABEL_52;
  v7 = psz;
  *(_OWORD *)psz = *(_OWORD *)L"MACHINE/WEBROOT/APPHOST/";
  *((_OWORD *)v7 + 1) = *(_OWORD *)L"WEBROOT/APPHOST/";
  *((_OWORD *)v7 + 2) = *(_OWORD *)L"APPHOST/";
  v49 = 48;
  *((_BYTE *)psz + 48) = 0;
  HIBYTE(psz[v49 / 2]) = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  appended = STBUFF::AppendData((STBUFF *)&v47, a2, 2 * v8, 0xFFFFFFFF);
  if ( appended < 0 )
    goto LABEL_52;
  LOBYTE(psz[v49 / 2]) = 0;
  HIBYTE(psz[v49 / 2]) = 0;
  bstrString = SysAllocString(psz);
  if ( !bstrString )
    goto LABEL_6;
  v28 = SysAllocString(L"system.webServer/security/dynamicIpSecurity");
  v4 = v28;
  if ( !v28 )
    goto LABEL_6;
  v9 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  appended = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, struct IAppHostElement **))(*(_QWORD *)v9 + 24LL))(
               v9,
               v28,
               bstrString,
               &v30);
  if ( appended >= 0 )
  {
    appended = GetPropertyBOOL(v30, L"enableProxyMode", (int *)this + 5);
    if ( appended >= 0 )
    {
      appended = GetPropertyBOOL(v30, L"enableLoggingOnlyMode", (int *)this + 6);
      if ( appended >= 0 )
      {
        appended = GetPropertyDWORD(v30, L"denyAction", (unsigned int *)this + 76);
        if ( appended >= 0 )
        {
          appended = GetChildElement(v30, L"denyByConcurrentRequests", &v33);
          if ( appended >= 0 )
          {
            appended = GetPropertyBOOL(v33, L"enabled", &v26);
            if ( appended >= 0 )
            {
              if ( v26 )
              {
                appended = GetPropertyDWORD(v33, L"maxConcurrentRequests", (unsigned int *)this + 8);
                if ( appended < 0 )
                  goto LABEL_52;
              }
              else
              {
                *((_DWORD *)this + 8) = 0;
              }
              appended = GetChildElement(v30, L"denyByRequestRate", &v31);
              if ( appended >= 0 )
              {
                v26 = 0;
                appended = GetPropertyBOOL(v31, L"enabled", &v26);
                if ( appended >= 0 )
                {
                  if ( v26 )
                  {
                    appended = GetPropertyDWORD(v31, L"maxRequests", (unsigned int *)this + 7);
                    if ( appended < 0 )
                      goto LABEL_52;
                    appended = GetPropertyDWORD(v31, L"requestIntervalInMilliseconds", (unsigned int *)this + 9);
                    if ( appended < 0 )
                      goto LABEL_52;
                  }
                  else
                  {
                    *((_DWORD *)this + 7) = 0;
                  }
                  v5 = SysAllocString(L"system.webServer/security/ipSecurity");
                  if ( v5 )
                  {
                    v10 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
                    appended = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR, __int64 *))(*(_QWORD *)v10 + 24LL))(
                                 v10,
                                 v5,
                                 bstrString,
                                 &v34);
                    if ( appended < 0 )
                      goto LABEL_52;
                    appended = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v34 + 32LL))(v34, &v32);
                    if ( appended < 0 )
                      goto LABEL_52;
                    v27 = 0;
                    appended = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v32 + 24))(v32, &v27);
                    if ( appended < 0 || !v27 )
                      goto LABEL_52;
                    v11 = operator new(0x18u);
                    if ( v11 )
                    {
                      v11[1] = 0;
                      *v11 = &ALLOW_LIST::`vftable';
                      v11[2] = 0;
                    }
                    else
                    {
                      v11 = 0;
                    }
                    *((_QWORD *)this + 25) = v11;
                    if ( v11 )
                    {
                      v12 = v27;
                      v13 = malloc(8LL * v27);
                      v11[1] = v13;
                      if ( v13 )
                      {
                        *((_DWORD *)v11 + 4) = v12;
                        *((_DWORD *)v11 + 5) = 0;
                        appended = 0;
                        v15 = 0;
                        if ( !v27 )
                          goto LABEL_52;
                        while ( 1 )
                        {
                          STBUFF::STBUFF((STBUFF *)&v43, v14);
                          STBUFF::STBUFF((STBUFF *)&v38, v16);
                          pvarg.lVal = v15;
                          v17 = *v32;
                          v26 = 0;
                          v37 = pvarg;
                          appended = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IAppHostElement **))(v17 + 32))(
                                       v32,
                                       &v37,
                                       &v29);
                          if ( appended < 0 || (appended = GetPropertyBOOL(v29, L"allowed", &v26), appended < 0) )
                          {
LABEL_77:
                            v25 = hMem;
                            v38 = &STBUFF::`vftable';
                            if ( hMem == v42 )
                              goto LABEL_79;
LABEL_78:
                            LocalFree(v25);
                            v41 = 64;
                            hMem = v42;
LABEL_79:
                            v40 = 0;
                            v43 = &STBUFF::`vftable';
                            if ( v44 != v46 )
                              LocalFree(v44);
                            v4 = v28;
                            goto LABEL_52;
                          }
                          if ( !v26 )
                            goto LABEL_45;
                          appended = GetPropertyString(v29, L"ipAddress", (struct STBUFF *)&v43);
                          if ( appended < 0 )
                            goto LABEL_77;
                          if ( v45 )
                            break;
LABEL_46:
                          v38 = &STBUFF::`vftable';
                          if ( hMem != v42 )
                          {
                            LocalFree(hMem);
                            v41 = 64;
                            hMem = v42;
                          }
                          v43 = &STBUFF::`vftable';
                          v40 = 0;
                          if ( v44 != v46 )
                            LocalFree(v44);
                          if ( ++v15 >= v27 )
                          {
                            v4 = v28;
                            goto LABEL_52;
                          }
                        }
                        appended = GetPropertyString(v29, L"subnetMask", (struct STBUFF *)&v38);
                        if ( appended < 0 )
                          goto LABEL_77;
                        v18 = *((_QWORD *)this + 25);
                        *((_BYTE *)hMem + v40) = 0;
                        *((_BYTE *)hMem + v40 + 1) = 0;
                        v19 = (const unsigned __int16 *)hMem;
                        *((_BYTE *)v44 + v45) = 0;
                        *((_BYTE *)v44 + v45 + 1) = 0;
                        v20 = (const unsigned __int16 *)v44;
                        v22 = operator new(0xD0u);
                        if ( !v22 )
                        {
                          appended = -2147024882;
LABEL_75:
                          v25 = hMem;
                          v38 = &STBUFF::`vftable';
                          if ( hMem == v42 )
                            goto LABEL_79;
                          goto LABEL_78;
                        }
                        *(_QWORD *)v22 = &ALLOW_LIST_ENTRY::`vftable';
                        STBUFF::STBUFF((STBUFF *)(v22 + 4), v21);
                        STBUFF::STBUFF((STBUFF *)(v22 + 28), v23);
                        v22[2] = 0;
                        appended = ALLOW_LIST_ENTRY::Set((ALLOW_LIST_ENTRY *)v22, v20, v19);
                        if ( appended < 0 )
                        {
                          (**(void (__fastcall ***)(_DWORD *, __int64))v22)(v22, 1);
                          goto LABEL_75;
                        }
                        *(_QWORD *)(*(_QWORD *)(v18 + 8) + 8LL * (unsigned int)(*(_DWORD *)(v18 + 20))++) = v22;
LABEL_45:
                        ((void (__fastcall *)(struct IAppHostElement *))v29->lpVtbl->Release)(v29);
                        v29 = 0;
                        goto LABEL_46;
                      }
                    }
                  }
LABEL_6:
                  appended = -2147024882;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_52:
  VariantClear(&pvarg);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v4 )
    SysFreeString(v4);
  if ( v5 )
    SysFreeString(v5);
  if ( v29 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v29->lpVtbl->Release)(v29);
    v29 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    v32 = 0;
  }
  if ( v31 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v31->lpVtbl->Release)(v31);
    v31 = 0;
  }
  if ( v33 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v33->lpVtbl->Release)(v33);
    v33 = 0;
  }
  if ( v30 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v30->lpVtbl->Release)(v30);
    v30 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  v47 = &STBUFF::`vftable';
  if ( psz != (OLECHAR *)&v50 )
    LocalFree(psz);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180002604  mov     [rsp-8+arg_10], rbx
0x180002609  push    rbp
0x18000260a  push    rsi
0x18000260b  push    rdi
0x18000260c  push    r12
0x18000260e  push    r13
0x180002610  push    r14
0x180002612  push    r15
0x180002614  lea     rbp, [rsp-0E0h]
0x18000261c  sub     rsp, 1E0h
0x180002623  mov     rax, cs:__security_cookie
0x18000262a  xor     rax, rsp
0x18000262d  mov     [rbp+110h+var_40], rax
0x180002634  mov     rsi, rcx
0x180002637  mov     rdi, rdx
0x18000263a  lea     rcx, [rbp+110h+var_A0]; this
0x18000263e  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180002643  xor     r12d, r12d
0x180002646  lea     rcx, [rsp+210h+pvarg]; pvarg
0x18000264b  xorps   xmm0, xmm0
0x18000264e  mov     [rsp+210h+bstrString], r12
0x180002653  xor     eax, eax
0x180002655  mov     [rsp+210h+var_1C8], r12
0x18000265a  movups  xmmword ptr [rsp+210h+pvarg], xmm0
0x18000265f  mov     qword ptr [rbp+110h+pvarg+10h], rax
0x180002663  mov     r14d, r12d
0x180002666  mov     r13d, r12d
0x180002669  mov     [rsp+210h+var_1A8], r12
0x18000266e  mov     [rsp+210h+var_1B0], r12
0x180002673  mov     [rsp+210h+var_1C0], r12
0x180002678  mov     [rsp+210h+var_1D0], r12
0x18000267d  mov     [rsp+210h+var_1B8], r12
0x180002682  mov     [rsp+210h+var_1E0], r12d
0x180002687  call    cs:__imp_VariantInit
0x18000268d  lea     eax, [r12+13h]
0x180002692  mov     dword ptr [rbp+110h+pvarg+8], r12d
0x180002696  lea     rcx, [rbp+110h+var_A0]; this
0x18000269a  mov     word ptr [rsp+210h+pvarg], ax
0x18000269f  lea     edx, [rax+1Dh]; unsigned int
0x1800026a2  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x1800026a7  lea     r15, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x1800026ae  mov     ebx, eax
0x1800026b0  test    eax, eax
0x1800026b2  js      loc_180002C13
0x1800026b8  mov     rax, [rbp+110h+psz]
0x1800026bc  movups  xmm0, xmmword ptr cs:aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x1800026c3  movups  xmmword ptr [rax], xmm0
0x1800026c6  movups  xmm1, xmmword ptr cs:aMachineWebroot+10h; "WEBROOT/APPHOST/"
0x1800026cd  movups  xmmword ptr [rax+10h], xmm1
0x1800026d1  movups  xmm0, xmmword ptr cs:aMachineWebroot+20h; "APPHOST/"
0x1800026d8  movups  xmmword ptr [rax+20h], xmm0
0x1800026dc  mov     rax, [rbp+110h+psz]
0x1800026e0  mov     [rbp+110h+var_90], 30h ; '0'
0x1800026ea  mov     [rax+30h], r12b
0x1800026ee  mov     ecx, [rbp+110h+var_90]
0x1800026f4  mov     rax, [rbp+110h+psz]
0x1800026f8  inc     ecx
0x1800026fa  mov     [rcx+rax], r12b
0x1800026fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002702  inc     r8
0x180002705  cmp     [rdi+r8*2], r12w
0x18000270a  jnz     short loc_180002702
0x18000270c  add     r8d, r8d; unsigned int
0x18000270f  lea     rcx, [rbp+110h+var_A0]; this
0x180002713  or      r9d, 0FFFFFFFFh; unsigned int
0x180002717  mov     rdx, rdi; void *
0x18000271a  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x18000271f  mov     ebx, eax
0x180002721  test    eax, eax
0x180002723  js      loc_180002C13
0x180002729  mov     ecx, [rbp+110h+var_90]
0x18000272f  mov     rax, [rbp+110h+psz]
0x180002733  mov     [rcx+rax], r12b
0x180002737  mov     ecx, [rbp+110h+var_90]
0x18000273d  mov     rax, [rbp+110h+psz]
0x180002741  inc     ecx
0x180002743  mov     [rcx+rax], r12b
0x180002747  mov     rcx, [rbp+110h+psz]; psz
0x18000274b  call    cs:__imp_SysAllocString
0x180002751  mov     [rsp+210h+bstrString], rax
0x180002756  mov     rbx, rax
0x180002759  test    rax, rax
0x18000275c  jnz     short loc_180002768
0x18000275e  mov     ebx, 8007000Eh
0x180002763  jmp     loc_180002C13
0x180002768  lea     rcx, psz; "system.webServer/security/dynamicIpSecu"...
0x18000276f  call    cs:__imp_SysAllocString
0x180002775  mov     [rsp+210h+var_1D8], rax
0x18000277a  mov     r14, rax
0x18000277d  test    rax, rax
0x180002780  jz      short loc_18000275E
0x180002782  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002789  mov     rax, [rcx]
0x18000278c  mov     rax, [rax+38h]
0x180002790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002795  mov     r10, rax
0x180002798  lea     r9, [rsp+210h+var_1C8]
0x18000279d  mov     r8, rbx
0x1800027a0  mov     rdx, r14
0x1800027a3  mov     rcx, [rax]
0x1800027a6  mov     rax, [rcx+18h]
0x1800027aa  mov     rcx, r10
0x1800027ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b2  mov     ebx, eax
0x1800027b4  test    eax, eax
0x1800027b6  js      loc_180002C13
0x1800027bc  mov     rcx, [rsp+210h+var_1C8]; struct IAppHostElement *
0x1800027c1  lea     r8, [rsi+14h]; int *
0x1800027c5  lea     rdx, aEnableproxymod; "enableProxyMode"
0x1800027cc  call    ?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetPropertyBOOL(IAppHostElement *,ushort const *,int *)
0x1800027d1  mov     ebx, eax
0x1800027d3  test    eax, eax
0x1800027d5  js      loc_180002C13
0x1800027db  mov     rcx, [rsp+210h+var_1C8]; struct IAppHostElement *
0x1800027e0  lea     r8, [rsi+18h]; int *
0x1800027e4  lea     rdx, aEnableloggingo; "enableLoggingOnlyMode"
0x1800027eb  call    ?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetPropertyBOOL(IAppHostElement *,ushort const *,int *)
0x1800027f0  mov     ebx, eax
0x1800027f2  test    eax, eax
0x1800027f4  js      loc_180002C13
0x1800027fa  mov     rcx, [rsp+210h+var_1C8]; struct IAppHostElement *
0x1800027ff  lea     r8, [rsi+130h]; unsigned int *
0x180002806  lea     rdx, aDenyaction; "denyAction"
0x18000280d  call    ?GetPropertyDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetPropertyDWORD(IAppHostElement *,ushort const *,ulong *)
0x180002812  mov     ebx, eax
0x180002814  test    eax, eax
0x180002816  js      loc_180002C13
0x18000281c  mov     rcx, [rsp+210h+var_1C8]; struct IAppHostElement *
0x180002821  lea     r8, [rsp+210h+var_1B0]; struct IAppHostElement **
0x180002826  lea     rdx, aDenybyconcurre; "denyByConcurrentRequests"
0x18000282d  call    ?GetChildElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; GetChildElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x180002832  mov     ebx, eax
0x180002834  test    eax, eax
0x180002836  js      loc_180002C13
0x18000283c  mov     rcx, [rsp+210h+var_1B0]; struct IAppHostElement *
0x180002841  lea     r8, [rsp+210h+var_1E0]; int *
0x180002846  lea     rdx, aEnabled; "enabled"
0x18000284d  call    ?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetPropertyBOOL(IAppHostElement *,ushort const *,int *)
0x180002852  mov     ebx, eax
0x180002854  test    eax, eax
0x180002856  js      loc_180002C13
0x18000285c  cmp     [rsp+210h+var_1E0], r12d
0x180002861  jz      short loc_180002884
0x180002863  mov     rcx, [rsp+210h+var_1B0]; struct IAppHostElement *
0x180002868  lea     r8, [rsi+20h]; unsigned int *
0x18000286c  lea     rdx, aMaxconcurrentr; "maxConcurrentRequests"
0x180002873  call    ?GetPropertyDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetPropertyDWORD(IAppHostElement *,ushort const *,ulong *)
0x180002878  mov     ebx, eax
0x18000287a  test    eax, eax
0x18000287c  js      loc_180002C13
0x180002882  jmp     short loc_180002888
0x180002884  mov     [rsi+20h], r12d
0x180002888  mov     rcx, [rsp+210h+var_1C8]; struct IAppHostElement *
0x18000288d  lea     r8, [rsp+210h+var_1C0]; struct IAppHostElement **
0x180002892  lea     rdx, aDenybyrequestr; "denyByRequestRate"
0x180002899  call    ?GetChildElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; GetChildElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x18000289e  mov     ebx, eax
0x1800028a0  test    eax, eax
0x1800028a2  js      loc_180002C13
0x1800028a8  mov     rcx, [rsp+210h+var_1C0]; struct IAppHostElement *
0x1800028ad  lea     r8, [rsp+210h+var_1E0]; int *
0x1800028b2  lea     rdx, aEnabled; "enabled"
0x1800028b9  mov     [rsp+210h+var_1E0], r12d
0x1800028be  call    ?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetPropertyBOOL(IAppHostElement *,ushort const *,int *)
0x1800028c3  mov     ebx, eax
0x1800028c5  test    eax, eax
0x1800028c7  js      loc_180002C13
0x1800028cd  cmp     [rsp+210h+var_1E0], r12d
0x1800028d2  jz      short loc_180002914
0x1800028d4  mov     rcx, [rsp+210h+var_1C0]; struct IAppHostElement *
0x1800028d9  lea     r8, [rsi+1Ch]; unsigned int *
0x1800028dd  lea     rdx, aMaxrequests; "maxRequests"
0x1800028e4  call    ?GetPropertyDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetPropertyDWORD(IAppHostElement *,ushort const *,ulong *)
0x1800028e9  mov     ebx, eax
0x1800028eb  test    eax, eax
0x1800028ed  js      loc_180002C13
0x1800028f3  mov     rcx, [rsp+210h+var_1C0]; struct IAppHostElement *
0x1800028f8  lea     r8, [rsi+24h]; unsigned int *
0x1800028fc  lea     rdx, aRequestinterva; "requestIntervalInMilliseconds"
0x180002903  call    ?GetPropertyDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; GetPropertyDWORD(IAppHostElement *,ushort const *,ulong *)
0x180002908  mov     ebx, eax
0x18000290a  test    eax, eax
0x18000290c  js      loc_180002C13
0x180002912  jmp     short loc_180002918
0x180002914  mov     [rsi+1Ch], r12d
0x180002918  lea     rcx, aSystemWebserve_0; "system.webServer/security/ipSecurity"
0x18000291f  call    cs:__imp_SysAllocString
0x180002925  mov     r13, rax
0x180002928  test    rax, rax
0x18000292b  jz      loc_18000275E
0x180002931  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002938  mov     rax, [rcx]
0x18000293b  mov     rax, [rax+38h]
0x18000293f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002944  mov     r8, [rsp+210h+bstrString]
0x180002949  lea     r9, [rsp+210h+var_1A8]
0x18000294e  mov     r10, rax
0x180002951  mov     rdx, r13
0x180002954  mov     rcx, [rax]
0x180002957  mov     rax, [rcx+18h]
0x18000295b  mov     rcx, r10
0x18000295e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002963  mov     ebx, eax
0x180002965  test    eax, eax
0x180002967  js      loc_180002C13
0x18000296d  mov     rcx, [rsp+210h+var_1A8]
0x180002972  lea     rdx, [rsp+210h+var_1B8]
0x180002977  mov     rax, [rcx]
0x18000297a  mov     rax, [rax+20h]
0x18000297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002983  mov     ebx, eax
0x180002985  test    eax, eax
0x180002987  js      loc_180002C13
0x18000298d  mov     rcx, [rsp+210h+var_1B8]
0x180002992  lea     rdx, [rsp+210h+var_1DC]
0x180002997  mov     [rsp+210h+var_1DC], r12d
0x18000299c  mov     rax, [rcx]
0x18000299f  mov     rax, [rax+18h]
0x1800029a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a8  mov     ebx, eax
0x1800029aa  test    eax, eax
0x1800029ac  js      loc_180002C13
0x1800029b2  cmp     [rsp+210h+var_1DC], r12d
0x1800029b7  jz      loc_180002C13
0x1800029bd  mov     ecx, 18h; Size
0x1800029c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800029c7  mov     rbx, rax
0x1800029ca  test    rax, rax
0x1800029cd  jz      short loc_1800029E3
0x1800029cf  lea     rax, ??_7ALLOW_LIST@@6B@; const ALLOW_LIST::`vftable'
0x1800029d6  mov     [rbx+8], r12
0x1800029da  mov     [rbx], rax
0x1800029dd  mov     [rbx+10h], r12
0x1800029e1  jmp     short loc_1800029E6
0x1800029e3  mov     rbx, r12
0x1800029e6  mov     [rsi+0C8h], rbx
0x1800029ed  test    rbx, rbx
0x1800029f0  jz      loc_18000275E
0x1800029f6  mov     edi, [rsp+210h+var_1DC]
0x1800029fa  mov     ecx, edi
0x1800029fc  shl     rcx, 3; Size
0x180002a00  call    cs:__imp_malloc
0x180002a06  mov     [rbx+8], rax
0x180002a0a  test    rax, rax
0x180002a0d  jz      loc_18000275E
0x180002a13  mov     [rbx+10h], edi
0x180002a16  mov     [rbx+14h], r12d
0x180002a1a  mov     ebx, r12d
0x180002a1d  mov     r15d, r12d
0x180002a20  cmp     [rsp+210h+var_1DC], r12d
0x180002a25  jbe     loc_180002C0C
0x180002a2b  mov     r14d, 40h ; '@'
0x180002a31  lea     rcx, [rbp+110h+var_100]; this
0x180002a35  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180002a3a  lea     rcx, [rbp+110h+var_160]; this
0x180002a3e  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180002a43  mov     rcx, [rsp+210h+var_1B8]
0x180002a48  lea     r8, [rsp+210h+var_1D0]
0x180002a4d  movsd   xmm1, qword ptr [rbp+110h+pvarg+10h]
0x180002a52  lea     rdx, [rbp+110h+var_180]
0x180002a56  mov     dword ptr [rbp+110h+pvarg+8], r15d
0x180002a5a  movups  xmm0, xmmword ptr [rsp+210h+pvarg]
0x180002a5f  mov     rax, [rcx]
0x180002a62  mov     [rsp+210h+var_1E0], r12d
0x180002a67  movaps  [rbp+110h+var_180], xmm0
0x180002a6b  movsd   [rbp+110h+var_170], xmm1
0x180002a70  mov     rax, [rax+20h]
0x180002a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a79  mov     ebx, eax
0x180002a7b  test    eax, eax
0x180002a7d  js      loc_180002D79
0x180002a83  mov     rcx, [rsp+210h+var_1D0]; struct IAppHostElement *
0x180002a88  lea     r8, [rsp+210h+var_1E0]; int *
0x180002a8d  lea     rdx, aAllowed; "allowed"
0x180002a94  call    ?GetPropertyBOOL@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; GetPropertyBOOL(IAppHostElement *,ushort const *,int *)
0x180002a99  mov     ebx, eax
0x180002a9b  test    eax, eax
0x180002a9d  js      loc_180002D79
0x180002aa3  cmp     [rsp+210h+var_1E0], r12d
0x180002aa8  jz      loc_180002B9E
0x180002aae  mov     rcx, [rsp+210h+var_1D0]; struct IAppHostElement *
0x180002ab3  lea     r8, [rbp+110h+var_100]; struct STBUFF *
0x180002ab7  lea     rdx, aIpaddress; "ipAddress"
0x180002abe  call    ?GetPropertyString@@YAJPEAUIAppHostElement@@PEBGPEAVSTBUFF@@@Z; GetPropertyString(IAppHostElement *,ushort const *,STBUFF *)
0x180002ac3  mov     ebx, eax
0x180002ac5  test    eax, eax
0x180002ac7  js      loc_180002D79
0x180002acd  cmp     [rbp+110h+var_F0], r12d
0x180002ad1  jz      loc_180002BB4
0x180002ad7  mov     rcx, [rsp+210h+var_1D0]; struct IAppHostElement *
0x180002adc  lea     r8, [rbp+110h+var_160]; struct STBUFF *
0x180002ae0  lea     rdx, aSubnetmask; "subnetMask"
0x180002ae7  call    ?GetPropertyString@@YAJPEAUIAppHostElement@@PEBGPEAVSTBUFF@@@Z; GetPropertyString(IAppHostElement *,ushort const *,STBUFF *)
0x180002aec  mov     ebx, eax
0x180002aee  test    eax, eax
0x180002af0  js      loc_180002D79
0x180002af6  mov     ecx, [rbp+110h+var_150]
0x180002af9  mov     rax, [rbp+110h+hMem]
0x180002afd  mov     r14, [rsi+0C8h]
0x180002b04  mov     [rcx+rax], r12b
  ... truncated ...
```
