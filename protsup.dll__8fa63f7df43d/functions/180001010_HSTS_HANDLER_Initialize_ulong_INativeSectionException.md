# HSTS_HANDLER::Initialize(ulong,INativeSectionException * *)

- ea: `0x180001010`
- end: `0x180001242`
- name: `?Initialize@HSTS_HANDLER@@AEAAJKPEAPEAVINativeSectionException@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(HSTS_HANDLER *__hidden this, unsigned int, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001580`

## callees

- `0x180001010`
- `0x180001ab0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall HSTS_HANDLER::Initialize(HSTS_HANDLER *this, unsigned int a2, struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // rax
  int HstsHeaderValue; // ebx
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-34h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+50h] [rbp-18h] BYREF
  int v18; // [rsp+B8h] [rbp+50h] BYREF

  v17[0] = 0;
  v16 = 0;
  v15 = 0;
  v6 = *(_QWORD *)s_pGlobalInfo;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v7 = *(__int64 (__fastcall **)(struct IHttpServer *))(v6 + 56);
  v18 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v7(s_pGlobalInfo);
  HstsHeaderValue = (**v8)(v8, &IID_INativeConfigurationSystem, v17);
  if ( HstsHeaderValue >= 0 )
  {
    HstsHeaderValue = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v17[0] + 56LL))(v17[0], &v16);
    if ( HstsHeaderValue >= 0 )
    {
      HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct INativeSectionException **))(*(_QWORD *)v16 + 32LL))(
                          v16,
                          a2,
                          &v15,
                          a3);
      if ( HstsHeaderValue >= 0 )
      {
        v10 = v15;
        *((_DWORD *)this + 2) = a2;
        HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v10 + 32LL))(
                            v10,
                            L"hsts",
                            &v14);
        if ( HstsHeaderValue >= 0 )
        {
          HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                              v14,
                              L"enabled",
                              (char *)this + 12,
                              0,
                              0);
          if ( HstsHeaderValue >= 0 )
          {
            HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v14 + 48LL))(
                                v14,
                                L"max-age",
                                &v13,
                                0,
                                0);
            if ( HstsHeaderValue >= 0 )
            {
              HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                                  v14,
                                  L"includeSubDomains",
                                  &v12,
                                  0,
                                  0);
              if ( HstsHeaderValue >= 0 )
              {
                HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                                    v14,
                                    L"preload",
                                    &v18,
                                    0,
                                    0);
                if ( HstsHeaderValue >= 0 )
                {
                  HstsHeaderValue = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                                      v14,
                                      L"redirectHttpToHttps",
                                      (char *)this + 16,
                                      0,
                                      0);
                  if ( HstsHeaderValue >= 0 )
                    HstsHeaderValue = HSTS_HANDLER::CreateHstsHeaderValue(
                                        v13,
                                        v12,
                                        v18,
                                        (HSTS_HANDLER *)((char *)this + 24));
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[0] + 16LL))(v17[0]);
  return (unsigned int)HstsHeaderValue;
}

```

## disassembly

```asm
0x180001010  push    rbp
0x180001012  push    rbx
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r14
0x180001017  push    r15
0x180001019  mov     rbp, rsp
0x18000101c  sub     rsp, 68h
0x180001020  xor     r15d, r15d
0x180001023  mov     rdi, rcx
0x180001026  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000102d  mov     r14, r8
0x180001030  mov     esi, edx
0x180001032  mov     [rbp+var_18], r15
0x180001036  mov     [rbp+var_20], r15
0x18000103a  mov     [rbp+var_28], r15
0x18000103e  mov     rax, [rcx]
0x180001041  mov     [rbp+var_30], r15
0x180001045  mov     [rbp+var_34], r15d
0x180001049  mov     [rbp+var_38], r15d
0x18000104d  mov     rax, [rax+38h]
0x180001051  mov     [rbp+arg_18], r15d
0x180001055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000105a  mov     r9, rax
0x18000105d  lea     r8, [rbp+var_18]
0x180001061  lea     rdx, IID_INativeConfigurationSystem
0x180001068  mov     rcx, [rax]
0x18000106b  mov     rax, [rcx]
0x18000106e  mov     rcx, r9
0x180001071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001076  mov     ebx, eax
0x180001078  test    eax, eax
0x18000107a  js      loc_1800011D3
0x180001080  mov     rcx, [rbp+var_18]
0x180001084  lea     rdx, [rbp+var_20]
0x180001088  mov     rax, [rcx]
0x18000108b  mov     rax, [rax+38h]
0x18000108f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001094  mov     ebx, eax
0x180001096  test    eax, eax
0x180001098  js      loc_1800011D3
0x18000109e  mov     rcx, [rbp+var_20]
0x1800010a2  lea     r8, [rbp+var_28]
0x1800010a6  mov     r9, r14
0x1800010a9  mov     edx, esi
0x1800010ab  mov     rax, [rcx]
0x1800010ae  mov     rax, [rax+20h]
0x1800010b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010b7  mov     ebx, eax
0x1800010b9  test    eax, eax
0x1800010bb  js      loc_1800011D3
0x1800010c1  mov     rcx, [rbp+var_28]
0x1800010c5  lea     r8, [rbp+var_30]
0x1800010c9  mov     [rdi+8], esi
0x1800010cc  lea     rdx, aHsts; "hsts"
0x1800010d3  mov     rax, [rcx]
0x1800010d6  mov     rax, [rax+20h]
0x1800010da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010df  mov     ebx, eax
0x1800010e1  test    eax, eax
0x1800010e3  js      loc_1800011D3
0x1800010e9  mov     rcx, [rbp+var_30]
0x1800010ed  lea     r8, [rdi+0Ch]
0x1800010f1  xor     r9d, r9d
0x1800010f4  mov     [rsp+68h+var_48], r15
0x1800010f9  lea     rdx, aEnabled; "enabled"
0x180001100  mov     rax, [rcx]
0x180001103  mov     rax, [rax+48h]
0x180001107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000110c  mov     ebx, eax
0x18000110e  test    eax, eax
0x180001110  js      loc_1800011D3
0x180001116  mov     rcx, [rbp+var_30]
0x18000111a  lea     r8, [rbp+var_34]
0x18000111e  xor     r9d, r9d
0x180001121  mov     [rsp+68h+var_48], r15
0x180001126  lea     rdx, aMaxAge_0; "max-age"
0x18000112d  mov     rax, [rcx]
0x180001130  mov     rax, [rax+30h]
0x180001134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001139  mov     ebx, eax
0x18000113b  test    eax, eax
0x18000113d  js      loc_1800011D3
0x180001143  mov     rcx, [rbp+var_30]
0x180001147  lea     r8, [rbp+var_38]
0x18000114b  xor     r9d, r9d
0x18000114e  mov     [rsp+68h+var_48], r15
0x180001153  lea     rdx, aIncludesubdoma_0; "includeSubDomains"
0x18000115a  mov     rax, [rcx]
0x18000115d  mov     rax, [rax+48h]
0x180001161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001166  mov     ebx, eax
0x180001168  test    eax, eax
0x18000116a  js      short loc_1800011D3
0x18000116c  mov     rcx, [rbp+var_30]
0x180001170  lea     r8, [rbp+arg_18]
0x180001174  xor     r9d, r9d
0x180001177  mov     [rsp+68h+var_48], r15
0x18000117c  lea     rdx, aPreload; "preload"
0x180001183  mov     rax, [rcx]
0x180001186  mov     rax, [rax+48h]
0x18000118a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000118f  mov     ebx, eax
0x180001191  test    eax, eax
0x180001193  js      short loc_1800011D3
0x180001195  mov     rcx, [rbp+var_30]
0x180001199  lea     r8, [rdi+10h]
0x18000119d  xor     r9d, r9d
0x1800011a0  mov     [rsp+68h+var_48], r15
0x1800011a5  lea     rdx, aRedirecthttpto; "redirectHttpToHttps"
0x1800011ac  mov     rax, [rcx]
0x1800011af  mov     rax, [rax+48h]
0x1800011b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011b8  mov     ebx, eax
0x1800011ba  test    eax, eax
0x1800011bc  js      short loc_1800011D3
0x1800011be  mov     r8d, [rbp+arg_18]; int
0x1800011c2  lea     r9, [rdi+18h]; struct STRA *
0x1800011c6  mov     edx, [rbp+var_38]; int
0x1800011c9  mov     ecx, [rbp+var_34]; unsigned int
0x1800011cc  call    ?CreateHstsHeaderValue@HSTS_HANDLER@@CAJKHHPEAVSTRA@@@Z; HSTS_HANDLER::CreateHstsHeaderValue(ulong,int,int,STRA *)
0x1800011d1  mov     ebx, eax
0x1800011d3  mov     rcx, [rbp+var_30]
0x1800011d7  test    rcx, rcx
0x1800011da  jz      short loc_1800011EC
0x1800011dc  mov     rax, [rcx]
0x1800011df  mov     rax, [rax+10h]
0x1800011e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e8  mov     [rbp+var_30], r15
0x1800011ec  mov     rcx, [rbp+var_28]
0x1800011f0  test    rcx, rcx
0x1800011f3  jz      short loc_180001205
0x1800011f5  mov     rax, [rcx]
0x1800011f8  mov     rax, [rax+10h]
0x1800011fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001201  mov     [rbp+var_28], r15
0x180001205  mov     rcx, [rbp+var_20]
0x180001209  test    rcx, rcx
0x18000120c  jz      short loc_18000121E
0x18000120e  mov     rax, [rcx]
0x180001211  mov     rax, [rax+10h]
0x180001215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121a  mov     [rbp+var_20], r15
0x18000121e  mov     rcx, [rbp+var_18]
0x180001222  test    rcx, rcx
0x180001225  jz      short loc_180001233
0x180001227  mov     rax, [rcx]
0x18000122a  mov     rax, [rax+10h]
0x18000122e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001233  mov     eax, ebx
0x180001235  add     rsp, 68h
0x180001239  pop     r15
0x18000123b  pop     r14
0x18000123d  pop     rdi
0x18000123e  pop     rsi
0x18000123f  pop     rbx
0x180001240  pop     rbp
0x180001241  retn
```
