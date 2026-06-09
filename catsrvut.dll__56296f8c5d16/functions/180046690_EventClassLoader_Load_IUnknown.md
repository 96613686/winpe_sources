# EventClassLoader::Load(IUnknown *)

- ea: `0x180046690`
- end: `0x180046cb4`
- name: `?Load@EventClassLoader@@UEAAJPEAUIUnknown@@@Z`
- size: `1572`
- prototype: `__int64 __fastcall(EventClassLoader *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180046690`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800469be`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046ac0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046b72`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046bb6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800469be`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046ac0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046b72`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046bb6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046924`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046966`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046924`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046966`
- `OLEAUT32!__imp_SysAllocString` at `0x180046944`
- `OLEAUT32!__imp_SysAllocString` at `0x180046978`
- `OLEAUT32!__imp_SysAllocString` at `0x180046944`
- `OLEAUT32!__imp_SysAllocString` at `0x180046978`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c38`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c51`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c78`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c83`
- `OLEAUT32!__imp_SysFreeString` at `0x180056664`
- `OLEAUT32!__imp_SysFreeString` at `0x18005666e`
- `OLEAUT32!__imp_SysFreeString` at `0x180056678`
- `OLEAUT32!__imp_SysFreeString` at `0x180056685`
- `OLEAUT32!__imp_SysFreeString` at `0x180056692`
- `OLEAUT32!__imp_SysFreeString` at `0x18005669f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566b3`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c38`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c51`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c78`
- `OLEAUT32!__imp_SysFreeString` at `0x180046c83`
- `OLEAUT32!__imp_SysFreeString` at `0x180056664`
- `OLEAUT32!__imp_SysFreeString` at `0x18005666e`
- `OLEAUT32!__imp_SysFreeString` at `0x180056678`
- `OLEAUT32!__imp_SysFreeString` at `0x180056685`
- `OLEAUT32!__imp_SysFreeString` at `0x180056692`
- `OLEAUT32!__imp_SysFreeString` at `0x18005669f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566b3`

## pseudocode

```c
__int64 __fastcall EventClassLoader::Load(const OLECHAR *this, struct IUnknown *a2)
{
  int v4; // r14d
  int v5; // ebx
  int v6; // eax
  __int64 v8; // [rsp+38h] [rbp-F0h] BYREF
  int v9; // [rsp+40h] [rbp-E8h] BYREF
  int v10; // [rsp+44h] [rbp-E4h] BYREF
  int v11; // [rsp+48h] [rbp-E0h] BYREF
  int v12; // [rsp+4Ch] [rbp-DCh]
  __int64 v13; // [rsp+50h] [rbp-D8h] BYREF
  LPCOLESTR v14; // [rsp+58h] [rbp-D0h] BYREF
  LPCOLESTR v15; // [rsp+60h] [rbp-C8h] BYREF
  LPCOLESTR lpsz; // [rsp+68h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-B8h] BYREF
  BSTR v18; // [rsp+78h] [rbp-B0h] BYREF
  BSTR v19; // [rsp+80h] [rbp-A8h] BYREF
  BSTR v20; // [rsp+88h] [rbp-A0h] BYREF
  LPCOLESTR v21[2]; // [rsp+90h] [rbp-98h] BYREF
  GUID pclsid; // [rsp+A0h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-78h] BYREF

  v21[1] = this;
  v8 = 0;
  v13 = 0;
  lpsz = 0;
  bstrString = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21[0] = 0;
  v14 = 0;
  v15 = 0;
  pclsid = 0;
  v10 = 0;
  v11 = 0;
  v9 = 0;
  v4 = 0;
  v12 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IEventClass2,
         &v8);
  if ( v5 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IEventClass3,
           &v13);
    v5 = v6;
    if ( v6 >= 0 || v6 == -2147467262 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v8 + 56LL))(v8, &lpsz);
      if ( !v5 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 72LL))(v8, &bstrString);
        if ( !v5 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 120LL))(v8, &v18);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 152LL))(v8, &v19);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 168LL))(v8, &v20);
              if ( v5 >= 0 )
              {
                v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v8 + 184LL))(v8, v21);
                if ( v5 >= 0 )
                {
                  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 200LL))(v8, &v10);
                  if ( v5 >= 0 )
                  {
                    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 216LL))(v8, &v11);
                    if ( v5 >= 0 )
                    {
                      if ( v13 )
                      {
                        v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v13 + 232LL))(v13, &v14);
                        if ( v5 < 0 )
                          goto LABEL_35;
                        v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v13 + 248LL))(v13, &v15);
                        if ( v5 < 0 )
                          goto LABEL_35;
                      }
                      else if ( !StringFromGUID2(&guidGlobalPartition, sz, 39)
                             || (v14 = SysAllocString(sz)) == 0
                             || !StringFromGUID2(&GUID_NULL, sz, 39)
                             || (v15 = SysAllocString(sz)) == 0 )
                      {
                        v5 = -2147024882;
                        goto LABEL_35;
                      }
                      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 120LL))(*((_QWORD *)this + 1));
                      if ( v5 >= 0 )
                      {
                        v4 = 1;
                        v12 = 1;
                        CLSIDFromString(lpsz, &pclsid);
                        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                               *((_QWORD *)this + 1),
                               0,
                               0,
                               &pclsid);
                        if ( v5 >= 0 )
                        {
                          v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, BSTR))(**((_QWORD **)this + 1) + 160LL))(
                                 *((_QWORD *)this + 1),
                                 1,
                                 0,
                                 bstrString);
                          if ( v5 >= 0 )
                          {
                            v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, BSTR))(**((_QWORD **)this + 1)
                                                                                          + 160LL))(
                                   *((_QWORD *)this + 1),
                                   2,
                                   0,
                                   v18);
                            if ( v5 >= 0 )
                            {
                              v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, BSTR))(**((_QWORD **)this + 1)
                                                                                            + 160LL))(
                                     *((_QWORD *)this + 1),
                                     3,
                                     0,
                                     v19);
                              if ( v5 >= 0 )
                              {
                                v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, BSTR))(**((_QWORD **)this + 1)
                                                                                              + 160LL))(
                                       *((_QWORD *)this + 1),
                                       4,
                                       0,
                                       v20);
                                if ( v5 >= 0 )
                                {
                                  if ( !v21[0]
                                    || (CLSIDFromString(v21[0], &pclsid),
                                        v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                                               *((_QWORD *)this + 1),
                                               5,
                                               0,
                                               &pclsid),
                                        v5 >= 0) )
                                  {
                                    v9 = v10;
                                    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 1) + 160LL))(
                                           *((_QWORD *)this + 1),
                                           6,
                                           0,
                                           &v9);
                                    if ( v5 >= 0 )
                                    {
                                      v9 = v11;
                                      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 1) + 160LL))(
                                             *((_QWORD *)this + 1),
                                             7,
                                             0,
                                             &v9);
                                      if ( v5 >= 0 )
                                      {
                                        if ( !v14
                                          || (CLSIDFromString(v14, &pclsid),
                                              v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                                                     *((_QWORD *)this + 1),
                                                     8,
                                                     0,
                                                     &pclsid),
                                              v5 >= 0) )
                                        {
                                          if ( v15 )
                                          {
                                            CLSIDFromString(v15, &pclsid);
                                            v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                                                   *((_QWORD *)this + 1),
                                                   9,
                                                   0,
                                                   &pclsid);
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
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  SysFreeString((BSTR)lpsz);
  SysFreeString(bstrString);
  SysFreeString(v18);
  SysFreeString(v19);
  SysFreeString(v20);
  SysFreeString((BSTR)v21[0]);
  SysFreeString((BSTR)v14);
  SysFreeString((BSTR)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046690  mov     r11, rsp
0x180046693  mov     [r11+18h], rbx
0x180046697  mov     [r11+20h], rsi
0x18004669b  push    rdi
0x18004669c  push    r14
0x18004669e  push    r15
0x1800466a0  sub     rsp, 110h
0x1800466a7  mov     rax, cs:__security_cookie
0x1800466ae  xor     rax, rsp
0x1800466b1  mov     [rsp+128h+var_28], rax
0x1800466b9  mov     rsi, rdx
0x1800466bc  mov     rdi, rcx
0x1800466bf  mov     [rsp+128h+var_90], rcx
0x1800466c7  xor     r15d, r15d
0x1800466ca  mov     [rsp+128h+var_F0], r15
0x1800466cf  mov     [rsp+128h+var_D8], r15
0x1800466d4  mov     [rsp+128h+lpsz], r15
0x1800466d9  mov     [rsp+128h+bstrString], r15
0x1800466de  mov     [rsp+128h+var_B0], r15
0x1800466e3  mov     [r11-0A8h], r15
0x1800466ea  mov     [r11-0A0h], r15
0x1800466f1  mov     [r11-98h], r15
0x1800466f8  mov     [rsp+128h+var_D0], r15
0x1800466fd  mov     [rsp+128h+var_C8], r15
0x180046702  xorps   xmm0, xmm0
0x180046705  movups  xmmword ptr [rsp+128h+pclsid.Data1], xmm0
0x18004670d  mov     [rsp+128h+var_E4], r15d
0x180046712  mov     [rsp+128h+var_E0], r15d
0x180046717  mov     [rsp+128h+var_E8], r15d
0x18004671c  mov     r14d, r15d
0x18004671f  mov     [rsp+128h+var_DC], r15d
0x180046724  mov     rax, [rdx]
0x180046727  lea     r8, [rsp+128h+var_F0]
0x18004672c  lea     rdx, IID_IEventClass2
0x180046733  mov     rcx, rsi
0x180046736  mov     rax, [rax]
0x180046739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004673e  mov     ebx, eax
0x180046740  mov     [rsp+128h+var_F8], eax
0x180046744  test    eax, eax
0x180046746  js      loc_180046BE4
0x18004674c  mov     rax, [rsi]
0x18004674f  lea     r8, [rsp+128h+var_D8]
0x180046754  lea     rdx, IID_IEventClass3
0x18004675b  mov     rcx, rsi
0x18004675e  mov     rax, [rax]
0x180046761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046766  mov     ebx, eax
0x180046768  mov     [rsp+128h+var_F8], eax
0x18004676c  test    eax, eax
0x18004676e  jns     short loc_180046780
0x180046770  cmp     eax, 80004002h
0x180046775  jnz     loc_180046BE4
0x18004677b  mov     [rsp+128h+var_F8], r15d
0x180046780  mov     rcx, [rsp+128h+var_F0]
0x180046785  mov     rax, [rcx]
0x180046788  lea     rdx, [rsp+128h+lpsz]
0x18004678d  mov     rax, [rax+38h]
0x180046791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046796  mov     ebx, eax
0x180046798  mov     [rsp+128h+var_F8], eax
0x18004679c  test    eax, eax
0x18004679e  jnz     loc_180046BE4
0x1800467a4  mov     rcx, [rsp+128h+var_F0]
0x1800467a9  mov     rax, [rcx]
0x1800467ac  lea     rdx, [rsp+128h+bstrString]
0x1800467b1  mov     rax, [rax+48h]
0x1800467b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467ba  mov     ebx, eax
0x1800467bc  mov     [rsp+128h+var_F8], eax
0x1800467c0  test    eax, eax
0x1800467c2  jnz     loc_180046BE4
0x1800467c8  mov     rcx, [rsp+128h+var_F0]
0x1800467cd  mov     rax, [rcx]
0x1800467d0  lea     rdx, [rsp+128h+var_B0]
0x1800467d5  mov     rax, [rax+78h]
0x1800467d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800467de  mov     ebx, eax
0x1800467e0  mov     [rsp+128h+var_F8], eax
0x1800467e4  test    eax, eax
0x1800467e6  js      loc_180046BE4
0x1800467ec  mov     rcx, [rsp+128h+var_F0]
0x1800467f1  mov     rax, [rcx]
0x1800467f4  lea     rdx, [rsp+128h+var_A8]
0x1800467fc  mov     rax, [rax+98h]
0x180046803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046808  mov     ebx, eax
0x18004680a  mov     [rsp+128h+var_F8], eax
0x18004680e  test    eax, eax
0x180046810  js      loc_180046BE4
0x180046816  mov     rcx, [rsp+128h+var_F0]
0x18004681b  mov     rax, [rcx]
0x18004681e  lea     rdx, [rsp+128h+var_A0]
0x180046826  mov     rax, [rax+0A8h]
0x18004682d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046832  mov     ebx, eax
0x180046834  mov     [rsp+128h+var_F8], eax
0x180046838  test    eax, eax
0x18004683a  js      loc_180046BE4
0x180046840  mov     rcx, [rsp+128h+var_F0]
0x180046845  mov     rax, [rcx]
0x180046848  lea     rdx, [rsp+128h+var_98]
0x180046850  mov     rax, [rax+0B8h]
0x180046857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004685c  mov     ebx, eax
0x18004685e  mov     [rsp+128h+var_F8], eax
0x180046862  test    eax, eax
0x180046864  js      loc_180046BE4
0x18004686a  mov     rcx, [rsp+128h+var_F0]
0x18004686f  mov     rax, [rcx]
0x180046872  lea     rdx, [rsp+128h+var_E4]
0x180046877  mov     rax, [rax+0C8h]
0x18004687e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046883  mov     ebx, eax
0x180046885  mov     [rsp+128h+var_F8], eax
0x180046889  test    eax, eax
0x18004688b  js      loc_180046BE4
0x180046891  mov     rcx, [rsp+128h+var_F0]
0x180046896  mov     rax, [rcx]
0x180046899  lea     rdx, [rsp+128h+var_E0]
0x18004689e  mov     rax, [rax+0D8h]
0x1800468a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468aa  mov     ebx, eax
0x1800468ac  mov     [rsp+128h+var_F8], eax
0x1800468b0  test    eax, eax
0x1800468b2  js      loc_180046BE4
0x1800468b8  mov     rcx, [rsp+128h+var_D8]
0x1800468bd  test    rcx, rcx
0x1800468c0  jz      short loc_18004690D
0x1800468c2  mov     rax, [rcx]
0x1800468c5  lea     rdx, [rsp+128h+var_D0]
0x1800468ca  mov     rax, [rax+0E8h]
0x1800468d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468d6  mov     ebx, eax
0x1800468d8  mov     [rsp+128h+var_F8], eax
0x1800468dc  test    eax, eax
0x1800468de  js      loc_180046BE4
0x1800468e4  mov     rcx, [rsp+128h+var_D8]
0x1800468e9  mov     rax, [rcx]
0x1800468ec  lea     rdx, [rsp+128h+var_C8]
0x1800468f1  mov     rax, [rax+0F8h]
0x1800468f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468fd  mov     ebx, eax
0x1800468ff  mov     [rsp+128h+var_F8], eax
0x180046903  test    eax, eax
0x180046905  js      loc_180046BE4
0x18004690b  jmp     short loc_180046988
0x18004690d  mov     ebx, 27h ; '''
0x180046912  mov     r8d, ebx; cchMax
0x180046915  lea     rdx, [rsp+128h+sz]; lpsz
0x18004691d  lea     rcx, guidGlobalPartition; rguid
0x180046924  call    cs:__imp_StringFromGUID2
0x18004692a  test    eax, eax
0x18004692c  jnz     short loc_18004693C
0x18004692e  mov     ebx, 8007000Eh
0x180046933  mov     [rsp+128h+var_F8], ebx
0x180046937  jmp     loc_180046BE4
0x18004693c  lea     rcx, [rsp+128h+sz]; psz
0x180046944  call    cs:__imp_SysAllocString
0x18004694a  mov     [rsp+128h+var_D0], rax
0x18004694f  test    rax, rax
0x180046952  jz      short loc_18004692E
0x180046954  mov     r8d, ebx; cchMax
0x180046957  lea     rdx, [rsp+128h+sz]; lpsz
0x18004695f  lea     rcx, GUID_NULL; rguid
0x180046966  call    cs:__imp_StringFromGUID2
0x18004696c  test    eax, eax
0x18004696e  jz      short loc_18004692E
0x180046970  lea     rcx, [rsp+128h+sz]; psz
0x180046978  call    cs:__imp_SysAllocString
0x18004697e  mov     [rsp+128h+var_C8], rax
0x180046983  test    rax, rax
0x180046986  jz      short loc_18004692E
0x180046988  mov     rcx, [rdi+8]
0x18004698c  mov     rax, [rcx]
0x18004698f  mov     rax, [rax+78h]
0x180046993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046998  mov     ebx, eax
0x18004699a  mov     [rsp+128h+var_F8], eax
0x18004699e  test    eax, eax
0x1800469a0  js      loc_180046BE4
0x1800469a6  mov     r14d, 1
0x1800469ac  mov     [rsp+128h+var_DC], r14d
0x1800469b1  lea     rdx, [rsp+128h+pclsid]; pclsid
0x1800469b9  mov     rcx, [rsp+128h+lpsz]; lpsz
0x1800469be  call    cs:__imp_CLSIDFromString
0x1800469c4  mov     rcx, [rdi+8]
0x1800469c8  mov     rax, [rcx]
0x1800469cb  lea     r9, [rsp+128h+pclsid]
0x1800469d3  xor     r8d, r8d
0x1800469d6  xor     edx, edx
0x1800469d8  mov     rax, [rax+0A0h]
0x1800469df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469e4  mov     ebx, eax
0x1800469e6  mov     [rsp+128h+var_F8], eax
0x1800469ea  test    eax, eax
0x1800469ec  js      loc_180046BE4
0x1800469f2  mov     rcx, [rdi+8]
0x1800469f6  mov     rax, [rcx]
0x1800469f9  mov     r9, [rsp+128h+bstrString]
0x1800469fe  xor     r8d, r8d
0x180046a01  mov     edx, r14d
0x180046a04  mov     rax, [rax+0A0h]
0x180046a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a10  mov     ebx, eax
0x180046a12  mov     [rsp+128h+var_F8], eax
0x180046a16  test    eax, eax
0x180046a18  js      loc_180046BE4
0x180046a1e  mov     rcx, [rdi+8]
0x180046a22  mov     rax, [rcx]
0x180046a25  mov     r9, [rsp+128h+var_B0]
0x180046a2a  xor     r8d, r8d
0x180046a2d  lea     edx, [r14+1]
0x180046a31  mov     rax, [rax+0A0h]
0x180046a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a3d  mov     ebx, eax
0x180046a3f  mov     [rsp+128h+var_F8], eax
0x180046a43  test    eax, eax
0x180046a45  js      loc_180046BE4
0x180046a4b  mov     rcx, [rdi+8]
0x180046a4f  mov     rax, [rcx]
0x180046a52  mov     r9, [rsp+128h+var_A8]
0x180046a5a  xor     r8d, r8d
0x180046a5d  lea     edx, [r14+2]
0x180046a61  mov     rax, [rax+0A0h]
0x180046a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a6d  mov     ebx, eax
0x180046a6f  mov     [rsp+128h+var_F8], eax
0x180046a73  test    eax, eax
0x180046a75  js      loc_180046BE4
0x180046a7b  mov     rcx, [rdi+8]
0x180046a7f  mov     rax, [rcx]
0x180046a82  mov     r9, [rsp+128h+var_A0]
0x180046a8a  xor     r8d, r8d
0x180046a8d  lea     edx, [r14+3]
0x180046a91  mov     rax, [rax+0A0h]
0x180046a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a9d  mov     ebx, eax
0x180046a9f  mov     [rsp+128h+var_F8], eax
0x180046aa3  test    eax, eax
0x180046aa5  js      loc_180046BE4
0x180046aab  mov     rcx, [rsp+128h+var_98]; lpsz
0x180046ab3  test    rcx, rcx
0x180046ab6  jz      short loc_180046AF6
0x180046ab8  lea     rdx, [rsp+128h+pclsid]; pclsid
0x180046ac0  call    cs:__imp_CLSIDFromString
0x180046ac6  mov     rcx, [rdi+8]
0x180046aca  mov     rax, [rcx]
0x180046acd  lea     r9, [rsp+128h+pclsid]
0x180046ad5  xor     r8d, r8d
0x180046ad8  lea     edx, [r14+4]
0x180046adc  mov     rax, [rax+0A0h]
0x180046ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ae8  mov     ebx, eax
0x180046aea  mov     [rsp+128h+var_F8], eax
0x180046aee  test    eax, eax
0x180046af0  js      loc_180046BE4
0x180046af6  mov     eax, [rsp+128h+var_E4]
0x180046afa  mov     [rsp+128h+var_E8], eax
0x180046afe  mov     rcx, [rdi+8]
0x180046b02  mov     rax, [rcx]
0x180046b05  lea     r9, [rsp+128h+var_E8]
0x180046b0a  xor     r8d, r8d
0x180046b0d  lea     edx, [r8+6]
0x180046b11  mov     rax, [rax+0A0h]
0x180046b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b1d  mov     ebx, eax
0x180046b1f  mov     [rsp+128h+var_F8], eax
0x180046b23  test    eax, eax
0x180046b25  js      loc_180046BE4
0x180046b2b  mov     eax, [rsp+128h+var_E0]
0x180046b2f  mov     [rsp+128h+var_E8], eax
0x180046b33  mov     rcx, [rdi+8]
0x180046b37  mov     rax, [rcx]
0x180046b3a  lea     r9, [rsp+128h+var_E8]
0x180046b3f  xor     r8d, r8d
0x180046b42  lea     edx, [r8+7]
0x180046b46  mov     rax, [rax+0A0h]
0x180046b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b52  mov     ebx, eax
0x180046b54  mov     [rsp+128h+var_F8], eax
0x180046b58  test    eax, eax
0x180046b5a  js      loc_180046BE4
0x180046b60  mov     rcx, [rsp+128h+var_D0]; lpsz
0x180046b65  test    rcx, rcx
0x180046b68  jz      short loc_180046BA4
0x180046b6a  lea     rdx, [rsp+128h+pclsid]; pclsid
0x180046b72  call    cs:__imp_CLSIDFromString
0x180046b78  mov     rcx, [rdi+8]
0x180046b7c  mov     rax, [rcx]
0x180046b7f  lea     r9, [rsp+128h+pclsid]
0x180046b87  xor     r8d, r8d
0x180046b8a  lea     edx, [r8+8]
0x180046b8e  mov     rax, [rax+0A0h]
0x180046b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b9a  mov     ebx, eax
0x180046b9c  mov     [rsp+128h+var_F8], eax
0x180046ba0  test    eax, eax
0x180046ba2  js      short loc_180046BE4
0x180046ba4  mov     rcx, [rsp+128h+var_C8]; lpsz
  ... truncated ...
```
