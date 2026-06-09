# _getBaseURLFromSite(IUnknown *)

- ea: `0x180067ea4`
- end: `0x1800684ff`
- name: `?_getBaseURLFromSite@@YAPEAVString@@PEAUIUnknown@@@Z`
- size: `1627`
- prototype: `struct String *__fastcall(struct IUnknown *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180067bd0`
- `0x180093df0`

## callees

- `0x180014214`
- `0x18001ecd0`
- `0x1800222c0`
- `0x180037454`
- `0x1800585d8`
- `0x180064034`
- `0x180067ea4`
- `0x180102d20`
- `0x180102db0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180068408`
- `msvcrt!_resetstkoflw` at `0x180068408`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006845b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006845b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800683f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800683f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068086`
- `OLEAUT32!__imp_SysAllocString` at `0x180067f12`
- `OLEAUT32!__imp_SysAllocString` at `0x180067f12`
- `OLEAUT32!__imp_SysFreeString` at `0x180068347`
- `OLEAUT32!__imp_SysFreeString` at `0x1800683e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800684d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180068347`
- `OLEAUT32!__imp_SysFreeString` at `0x1800683e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800684d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18006826c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800682f4`
- `OLEAUT32!__imp_SysStringLen` at `0x18006826c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800682f4`
- `OLEAUT32!__imp_VariantInit` at `0x18006815b`
- `OLEAUT32!__imp_VariantInit` at `0x180068192`
- `OLEAUT32!__imp_VariantInit` at `0x1800682b4`
- `OLEAUT32!__imp_VariantInit` at `0x18006815b`
- `OLEAUT32!__imp_VariantInit` at `0x180068192`
- `OLEAUT32!__imp_VariantInit` at `0x1800682b4`
- `OLEAUT32!__imp_VariantClear` at `0x180068314`
- `OLEAUT32!__imp_VariantClear` at `0x180068314`

## pseudocode

```c
struct String *__fastcall _getBaseURLFromSite(struct IUnknown *a1)
{
  struct String *v2; // rbx
  OLECHAR *v3; // rsi
  LONG v4; // edi
  __int64 v5; // rax
  const unsigned __int16 *bstrVal; // rdi
  UINT v7; // eax
  LONG v9; // [rsp+30h] [rbp-1178h] BYREF
  LONG v10; // [rsp+34h] [rbp-1174h]
  struct String *v11; // [rsp+38h] [rbp-1170h]
  struct IUnknown *v12; // [rsp+40h] [rbp-1168h] BYREF
  struct IUnknown *v13; // [rsp+48h] [rbp-1160h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-1158h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp-1150h] BYREF
  __int64 v16; // [rsp+60h] [rbp-1148h] BYREF
  __int64 *v17; // [rsp+68h] [rbp-1140h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-1138h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-1130h] BYREF
  __int64 v20; // [rsp+80h] [rbp-1128h] BYREF
  struct IUnknown *v21; // [rsp+88h] [rbp-1120h] BYREF
  struct IUnknown *v22; // [rsp+90h] [rbp-1118h] BYREF
  struct IUnknown *v23; // [rsp+98h] [rbp-1110h] BYREF
  VARIANTARG v24; // [rsp+A0h] [rbp-1108h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-10E8h] BYREF
  OLECHAR *v26; // [rsp+D8h] [rbp-10D0h]
  struct IUnknown *v27; // [rsp+E0h] [rbp-10C8h] BYREF
  VARIANTARG v28; // [rsp+E8h] [rbp-10C0h] BYREF
  VARIANTARG v29; // [rsp+100h] [rbp-10A8h] BYREF
  unsigned __int16 Src[2088]; // [rsp+120h] [rbp-1088h] BYREF

  v12 = 0;
  v23 = 0;
  v22 = 0;
  v13 = 0;
  v27 = 0;
  v21 = 0;
  pv = 0;
  bstrString = 0;
  v2 = 0;
  v11 = 0;
  v3 = SysAllocString(L"HREF");
  v26 = v3;
  if ( !v3 )
    goto LABEL_40;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IServiceProvider,
         &v12) < 0 )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a1->lpVtbl->QueryInterface)(
           a1,
           &IID_IHTMLDocument2,
           &v13) < 0 )
      goto LABEL_40;
LABEL_14:
    v17 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, __int64 **))v13->lpVtbl[2].Release)(v13, &v17) >= 0 && v17 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64 *, LONG *))(*v17 + 72))(v17, &v9);
      v4 = 0;
      v10 = 0;
      while ( v4 < v9 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = v4;
        memset(&v28, 0, sizeof(v28));
        VariantInit(&v28);
        v20 = 0;
        v5 = *v17;
        v24 = v28;
        v29 = pvarg;
        (*(void (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, __int64 *))(v5 + 88))(v17, &v29, &v24, &v20);
        if ( v20 )
        {
          v16 = 0;
          (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v20)(v20, &IID_IHTMLElement, &v16);
          if ( v16 )
          {
            pbstr = 0;
            (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 112LL))(v16, &pbstr);
            if ( pbstr )
            {
              if ( SysStringLen(pbstr) == 4 )
              {
                if ( (unsigned int)fastcmpni(pbstr, L"BASE", 4u) )
                {
                  if ( !(unsigned int)fastcmpni(pbstr, L"BODY", 4u) )
                    v4 = v9;
                }
                else
                {
                  memset(&v24, 0, sizeof(v24));
                  VariantInit(&v24);
                  (*(void (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *))(*(_QWORD *)v16 + 64LL))(
                    v16,
                    v3,
                    0,
                    &v24);
                  if ( v24.vt == 8 )
                  {
                    bstrVal = v24.bstrVal;
                    if ( v24.llVal )
                    {
                      v7 = SysStringLen(v24.bstrVal);
                      v2 = String::newString(bstrVal, v7);
                      v11 = v2;
                    }
                  }
                  VariantClear(&v24);
                  v4 = v9;
                }
                v10 = v4;
              }
              SysFreeString(pbstr);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v10 = ++v4;
      }
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    }
    if ( ((int (__fastcall *)(struct IUnknown *, BSTR *))v13->lpVtbl[13].AddRef)(v13, &bstrString) >= 0 )
    {
      if ( !v2 || (v2 = URL::resolveURL(v2, bstrString), (v11 = v2) == 0) )
      {
        v2 = String::newString(bstrString);
        v11 = v2;
      }
      SysFreeString(bstrString);
    }
    goto LABEL_40;
  }
  if ( ((int (__fastcall *)(struct IUnknown *, __int64 *, GUID *, struct IUnknown **))v12->lpVtbl[1].QueryInterface)(
         v12,
         &UUID_MSXMLSecureBaseUrl,
         &IID_IStream,
         &v21) >= 0 )
  {
    v14 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, unsigned __int16 *, __int64, unsigned int *))v21->lpVtbl[1].QueryInterface)(
           v21,
           Src,
           4168,
           &v14) >= 0 )
    {
      v2 = String::newString(Src, v14 >> 1);
      v11 = v2;
      goto LABEL_40;
    }
  }
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, GUID *, struct IUnknown **))v12->lpVtbl[1].QueryInterface)(
         v12,
         &IID_IBindHost,
         &IID_IBindHost,
         &v23) < 0 )
  {
    if ( ((int (__fastcall *)(struct IUnknown *, SID *, GUID *, struct IUnknown **))v12->lpVtbl[1].QueryInterface)(
           v12,
           &SID_SContainerDispatch,
           &IID_IHTMLDocument2,
           &v13) < 0
      && ((int (__fastcall *)(struct IUnknown *, GUID *, GUID *, struct IUnknown **))v12->lpVtbl[1].QueryInterface)(
           v12,
           &IID_IInternetHostSecurityManager,
           &IID_IHTMLDocument2,
           &v13) < 0 )
    {
      goto LABEL_40;
    }
    goto LABEL_14;
  }
  if ( ((int (__fastcall *)(struct IUnknown *, const unsigned __int16 *, _QWORD, struct IUnknown **, _DWORD))v23->lpVtbl[1].QueryInterface)(
         v23,
         L".",
         0,
         &v22,
         0) >= 0
    && ((int (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, LPVOID *))v22->lpVtbl[6].Release)(v22, 0, 0, &pv) >= 0 )
  {
    v2 = String::newString((const unsigned __int16 *)pv);
    v11 = v2;
    CoTaskMemFree(pv);
  }
LABEL_40:
  release(&v21);
  release(&v22);
  release(&v23);
  release(&v12);
  release(&v13);
  release(&v27);
  SysFreeString(v3);
  return v2;
}

```

## disassembly

```asm
0x180067ea4  push    rbx
0x180067ea6  push    rsi
0x180067ea7  push    rdi
0x180067ea8  push    r14
0x180067eaa  mov     eax, 1188h
0x180067eaf  call    _alloca_probe
0x180067eb4  sub     rsp, rax
0x180067eb7  mov     rax, cs:__security_cookie
0x180067ebe  xor     rax, rsp
0x180067ec1  mov     [rsp+11A8h+var_38], rax
0x180067ec9  mov     rdi, rcx
0x180067ecc  xor     r14d, r14d
0x180067ecf  mov     [rsp+11A8h+var_1168], r14
0x180067ed4  mov     [rsp+11A8h+var_1110], r14
0x180067edc  mov     [rsp+11A8h+var_1118], r14
0x180067ee4  mov     [rsp+11A8h+var_1160], r14
0x180067ee9  mov     [rsp+11A8h+var_10C8], r14
0x180067ef1  mov     [rsp+11A8h+var_1120], r14
0x180067ef9  mov     [rsp+11A8h+pv], r14
0x180067efe  mov     [rsp+11A8h+bstrString], r14
0x180067f03  mov     ebx, r14d
0x180067f06  mov     [rsp+11A8h+var_1170], rbx
0x180067f0b  lea     rcx, psz; "HREF"
0x180067f12  call    cs:__imp_SysAllocString
0x180067f18  mov     rsi, rax
0x180067f1b  mov     [rsp+11A8h+var_10D0], rax
0x180067f23  test    rax, rax
0x180067f26  jz      loc_18006848E
0x180067f2c  mov     rax, [rdi]
0x180067f2f  lea     r8, [rsp+11A8h+var_1168]
0x180067f34  lea     rdx, IID_IServiceProvider
0x180067f3b  mov     rcx, rdi
0x180067f3e  mov     rax, [rax]
0x180067f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f46  test    eax, eax
0x180067f48  jns     short loc_180067F71
0x180067f4a  mov     rax, [rdi]
0x180067f4d  lea     r8, [rsp+11A8h+var_1160]
0x180067f52  lea     rdx, IID_IHTMLDocument2
0x180067f59  mov     rcx, rdi
0x180067f5c  mov     rax, [rax]
0x180067f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f64  test    eax, eax
0x180067f66  jns     loc_1800680E5
0x180067f6c  jmp     loc_18006848E
0x180067f71  mov     rcx, [rsp+11A8h+var_1168]
0x180067f76  mov     rax, [rcx]
0x180067f79  lea     r9, [rsp+11A8h+var_1120]
0x180067f81  lea     r8, IID_IStream
0x180067f88  lea     rdx, UUID_MSXMLSecureBaseUrl
0x180067f8f  mov     rax, [rax+18h]
0x180067f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f98  test    eax, eax
0x180067f9a  js      short loc_180067FEC
0x180067f9c  mov     [rsp+11A8h+var_1158], r14d
0x180067fa1  mov     rcx, [rsp+11A8h+var_1120]
0x180067fa9  mov     rax, [rcx]
0x180067fac  lea     r9, [rsp+11A8h+var_1158]
0x180067fb1  mov     r8d, 1048h
0x180067fb7  lea     rdx, [rsp+11A8h+Src]
0x180067fbf  mov     rax, [rax+18h]
0x180067fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fc8  test    eax, eax
0x180067fca  js      short loc_180067FEC
0x180067fcc  mov     edx, [rsp+11A8h+var_1158]
0x180067fd0  shr     edx, 1; int
0x180067fd2  lea     rcx, [rsp+11A8h+Src]; Src
0x180067fda  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180067fdf  mov     rbx, rax
0x180067fe2  mov     [rsp+11A8h+var_1170], rax
0x180067fe7  jmp     loc_18006848E
0x180067fec  mov     rcx, [rsp+11A8h+var_1168]
0x180067ff1  mov     rax, [rcx]
0x180067ff4  lea     r9, [rsp+11A8h+var_1110]
0x180067ffc  lea     rdx, IID_IBindHost
0x180068003  mov     r8, rdx
0x180068006  mov     rax, [rax+18h]
0x18006800a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006800f  test    eax, eax
0x180068011  js      short loc_180068091
0x180068013  mov     rcx, [rsp+11A8h+var_1110]
0x18006801b  mov     rax, [rcx]
0x18006801e  mov     [rsp+11A8h+var_1188], r14d
0x180068023  lea     r9, [rsp+11A8h+var_1118]
0x18006802b  xor     r8d, r8d
0x18006802e  lea     rdx, asc_18012EDCC; "."
0x180068035  mov     rax, [rax+18h]
0x180068039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006803e  test    eax, eax
0x180068040  js      loc_18006848E
0x180068046  mov     rcx, [rsp+11A8h+var_1118]
0x18006804e  mov     rax, [rcx]
0x180068051  lea     r9, [rsp+11A8h+pv]
0x180068056  xor     r8d, r8d
0x180068059  xor     edx, edx
0x18006805b  mov     rax, [rax+0A0h]
0x180068062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068067  test    eax, eax
0x180068069  js      loc_1800683EB
0x18006806f  mov     rcx, [rsp+11A8h+pv]; unsigned __int16 *
0x180068074  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180068079  mov     rbx, rax
0x18006807c  mov     [rsp+11A8h+var_1170], rax
0x180068081  mov     rcx, [rsp+11A8h+pv]; pv
0x180068086  call    cs:__imp_CoTaskMemFree
0x18006808c  jmp     loc_1800683EB
0x180068091  mov     rcx, [rsp+11A8h+var_1168]
0x180068096  mov     rax, [rcx]
0x180068099  lea     r9, [rsp+11A8h+var_1160]
0x18006809e  lea     r8, IID_IHTMLDocument2
0x1800680a5  lea     rdx, SID_SContainerDispatch
0x1800680ac  mov     rax, [rax+18h]
0x1800680b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680b5  test    eax, eax
0x1800680b7  jns     short loc_1800680E5
0x1800680b9  mov     rcx, [rsp+11A8h+var_1168]
0x1800680be  mov     rax, [rcx]
0x1800680c1  lea     r9, [rsp+11A8h+var_1160]
0x1800680c6  lea     r8, IID_IHTMLDocument2
0x1800680cd  lea     rdx, IID_IInternetHostSecurityManager
0x1800680d4  mov     rax, [rax+18h]
0x1800680d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680dd  test    eax, eax
0x1800680df  js      loc_18006848E
0x1800680e5  mov     [rsp+11A8h+var_1140], r14
0x1800680ea  mov     rcx, [rsp+11A8h+var_1160]
0x1800680ef  mov     rax, [rcx]
0x1800680f2  lea     rdx, [rsp+11A8h+var_1140]
0x1800680f7  mov     rax, [rax+40h]
0x1800680fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068100  test    eax, eax
0x180068102  js      loc_18006838E
0x180068108  mov     rcx, [rsp+11A8h+var_1140]
0x18006810d  test    rcx, rcx
0x180068110  jz      loc_18006838E
0x180068116  mov     [rsp+11A8h+var_1178], r14d
0x18006811b  mov     rax, [rcx]
0x18006811e  lea     rdx, [rsp+11A8h+var_1178]
0x180068123  mov     rax, [rax+48h]
0x180068127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006812c  mov     edi, r14d
0x18006812f  mov     [rsp+11A8h+var_1174], r14d
0x180068134  cmp     edi, [rsp+11A8h+var_1178]
0x180068138  jge     loc_18006837D
0x18006813e  xorps   xmm0, xmm0
0x180068141  xor     eax, eax
0x180068143  movups  xmmword ptr [rsp+11A8h+pvarg], xmm0
0x18006814b  mov     qword ptr [rsp+11A8h+pvarg+10h], rax
0x180068153  lea     rcx, [rsp+11A8h+pvarg]; pvarg
0x18006815b  call    cs:__imp_VariantInit
0x180068161  mov     eax, 3
0x180068166  mov     word ptr [rsp+11A8h+pvarg], ax
0x18006816e  mov     dword ptr [rsp+11A8h+pvarg+8], edi
0x180068175  xorps   xmm0, xmm0
0x180068178  xor     eax, eax
0x18006817a  movups  xmmword ptr [rsp+11A8h+var_10C0], xmm0
0x180068182  mov     qword ptr [rsp+11A8h+var_10C0+10h], rax
0x18006818a  lea     rcx, [rsp+11A8h+var_10C0]; pvarg
0x180068192  call    cs:__imp_VariantInit
0x180068198  mov     [rsp+11A8h+var_1128], r14
0x1800681a0  mov     rcx, [rsp+11A8h+var_1140]
0x1800681a5  mov     rax, [rcx]
0x1800681a8  movups  xmm0, xmmword ptr [rsp+11A8h+var_10C0]
0x1800681b0  movaps  xmmword ptr [rsp+11A8h+var_1108], xmm0
0x1800681b8  movsd   xmm1, qword ptr [rsp+11A8h+var_10C0+10h]
0x1800681c1  movsd   qword ptr [rsp+11A8h+var_1108+10h], xmm1
0x1800681ca  movups  xmm0, xmmword ptr [rsp+11A8h+pvarg]
0x1800681d2  movaps  [rsp+11A8h+var_10A8], xmm0
0x1800681da  movsd   xmm1, qword ptr [rsp+11A8h+pvarg+10h]
0x1800681e3  movsd   [rsp+11A8h+var_1098], xmm1
0x1800681ec  lea     r9, [rsp+11A8h+var_1128]
0x1800681f4  lea     r8, [rsp+11A8h+var_1108]
0x1800681fc  lea     rdx, [rsp+11A8h+var_10A8]
0x180068204  mov     rax, [rax+58h]
0x180068208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006820d  mov     rcx, [rsp+11A8h+var_1128]
0x180068215  test    rcx, rcx
0x180068218  jz      loc_180068372
0x18006821e  mov     [rsp+11A8h+var_1148], r14
0x180068223  mov     rax, [rcx]
0x180068226  lea     r8, [rsp+11A8h+var_1148]
0x18006822b  lea     rdx, IID_IHTMLElement
0x180068232  mov     rax, [rax]
0x180068235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006823a  mov     rcx, [rsp+11A8h+var_1148]
0x18006823f  test    rcx, rcx
0x180068242  jz      loc_18006835E
0x180068248  mov     [rsp+11A8h+pbstr], r14
0x18006824d  mov     rax, [rcx]
0x180068250  lea     rdx, [rsp+11A8h+pbstr]
0x180068255  mov     rax, [rax+70h]
0x180068259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006825e  mov     rcx, [rsp+11A8h+pbstr]; pbstr
0x180068263  test    rcx, rcx
0x180068266  jz      loc_18006834D
0x18006826c  call    cs:__imp_SysStringLen
0x180068272  cmp     eax, 4
0x180068275  jnz     loc_180068342
0x18006827b  mov     r8d, eax; unsigned __int64
0x18006827e  lea     rdx, aBase; "BASE"
0x180068285  mov     rcx, [rsp+11A8h+pbstr]; unsigned __int16 *
0x18006828a  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x18006828f  test    eax, eax
0x180068291  jnz     loc_180068320
0x180068297  xorps   xmm0, xmm0
0x18006829a  xor     eax, eax
0x18006829c  movups  xmmword ptr [rsp+11A8h+var_1108], xmm0
0x1800682a4  mov     qword ptr [rsp+11A8h+var_1108+10h], rax
0x1800682ac  lea     rcx, [rsp+11A8h+var_1108]; pvarg
0x1800682b4  call    cs:__imp_VariantInit
0x1800682ba  mov     rcx, [rsp+11A8h+var_1148]
0x1800682bf  mov     rax, [rcx]
0x1800682c2  lea     r9, [rsp+11A8h+var_1108]
0x1800682ca  xor     r8d, r8d
0x1800682cd  mov     rdx, rsi
0x1800682d0  mov     rax, [rax+40h]
0x1800682d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682d9  cmp     word ptr [rsp+11A8h+var_1108], 8
0x1800682e2  jnz     short loc_18006830C
0x1800682e4  mov     rdi, qword ptr [rsp+11A8h+var_1108+8]
0x1800682ec  test    rdi, rdi
0x1800682ef  jz      short loc_18006830C
0x1800682f1  mov     rcx, rdi; pbstr
0x1800682f4  call    cs:__imp_SysStringLen
0x1800682fa  mov     edx, eax; int
0x1800682fc  mov     rcx, rdi; Src
0x1800682ff  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180068304  mov     rbx, rax
0x180068307  mov     [rsp+11A8h+var_1170], rax
0x18006830c  lea     rcx, [rsp+11A8h+var_1108]; pvarg
0x180068314  call    cs:__imp_VariantClear
0x18006831a  mov     edi, [rsp+11A8h+var_1178]
0x18006831e  jmp     short loc_18006833E
0x180068320  mov     r8d, 4; unsigned __int64
0x180068326  lea     rdx, aBody; "BODY"
0x18006832d  mov     rcx, [rsp+11A8h+pbstr]; unsigned __int16 *
0x180068332  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x180068337  test    eax, eax
0x180068339  cmovz   edi, [rsp+11A8h+var_1178]
0x18006833e  mov     [rsp+11A8h+var_1174], edi
0x180068342  mov     rcx, [rsp+11A8h+pbstr]; bstrString
0x180068347  call    cs:__imp_SysFreeString
0x18006834d  mov     rcx, [rsp+11A8h+var_1148]
0x180068352  mov     rax, [rcx]
0x180068355  mov     rax, [rax+10h]
0x180068359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006835e  mov     rcx, [rsp+11A8h+var_1128]
0x180068366  mov     rax, [rcx]
0x180068369  mov     rax, [rax+10h]
0x18006836d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068372  inc     edi
0x180068374  mov     [rsp+11A8h+var_1174], edi
0x180068378  jmp     loc_180068134
0x18006837d  mov     rcx, [rsp+11A8h+var_1140]
0x180068382  mov     rax, [rcx]
0x180068385  mov     rax, [rax+10h]
0x180068389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006838e  mov     rcx, [rsp+11A8h+var_1160]
0x180068393  mov     rax, [rcx]
0x180068396  lea     rdx, [rsp+11A8h+bstrString]
0x18006839b  mov     rax, [rax+140h]
0x1800683a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683a7  test    eax, eax
0x1800683a9  js      loc_18006848E
0x1800683af  test    rbx, rbx
0x1800683b2  jz      short loc_1800683CE
0x1800683b4  mov     rdx, [rsp+11A8h+bstrString]; unsigned __int16 *
0x1800683b9  mov     rcx, rbx; struct String *
0x1800683bc  call    ?resolveURL@URL@@SAPEAVString@@PEAV2@PEBG@Z; URL::resolveURL(String *,ushort const *)
0x1800683c1  mov     rbx, rax
0x1800683c4  mov     [rsp+11A8h+var_1170], rax
0x1800683c9  test    rax, rax
0x1800683cc  jnz     short loc_1800683E0
0x1800683ce  mov     rcx, [rsp+11A8h+bstrString]; unsigned __int16 *
0x1800683d3  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800683d8  mov     rbx, rax
0x1800683db  mov     [rsp+11A8h+var_1170], rax
0x1800683e0  mov     rcx, [rsp+11A8h+bstrString]; bstrString
0x1800683e5  call    cs:__imp_SysFreeString
0x1800683eb  jmp     loc_18006848E
0x1800683f0  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800683f6  call    cs:__imp_TlsGetValue
0x1800683fc  mov     rbx, rax
0x1800683ff  cmp     dword ptr [rax+54h], 0C00000FDh
0x180068406  jnz     short loc_180068481
0x180068408  call    cs:__imp__resetstkoflw
0x18006840e  test    eax, eax
0x180068410  jnz     short loc_180068463
0x180068412  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180068419  test    rcx, rcx
0x18006841c  jz      short loc_180068430
0x18006841e  cmp     [rcx+50h], rbx
0x180068422  jnz     short loc_180068430
0x180068424  mov     rax, [rcx]
0x180068427  mov     rax, [rax+20h]
0x18006842b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068430  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180068437  test    rcx, rcx
0x18006843a  jz      short loc_18006844E
0x18006843c  cmp     [rcx+50h], rbx
  ... truncated ...
```
