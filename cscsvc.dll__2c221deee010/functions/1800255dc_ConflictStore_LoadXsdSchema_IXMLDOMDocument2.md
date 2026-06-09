# ConflictStore_LoadXsdSchema(IXMLDOMDocument2 *)

- ea: `0x1800255dc`
- end: `0x180025893`
- name: `?ConflictStore_LoadXsdSchema@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800252d0`

## callees

- `0x1800255dc`
- `0x1800349d0`
- `0x180036394`
- `0x18003c460`
- `0x18003c488`
- `0x180089010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180025659`
- `OLEAUT32!__imp_SysAllocString` at `0x180025659`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180025843`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180025843`
- `OLEAUT32!__imp_VariantClear` at `0x1800256dc`
- `OLEAUT32!__imp_VariantClear` at `0x18002574d`
- `OLEAUT32!__imp_VariantClear` at `0x1800256dc`
- `OLEAUT32!__imp_VariantClear` at `0x18002574d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025766`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025766`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002563e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002563e`

## pseudocode

```c
__int64 __fastcall ConflictStore_LoadXsdSchema(struct IXMLDOMDocument2 *a1)
{
  int v2; // edi
  HRESULT v3; // eax
  BSTR v4; // rsi
  OLECHAR *v5; // rbx
  LPVOID v6; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(LPVOID, OLECHAR *, VARIANTARG *); // rdi
  int v9; // edi
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *putref_schemas)(IXMLDOMDocument2 *, VARIANT); // rdi
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v14; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+50h] BYREF
  IErrorInfo *pperrinfo; // [rsp+C8h] [rbp+58h] BYREF

  bstrString = 0;
  v2 = ConflictStore_XsdSchemaDocFromHtmlResource((int)a1, (struct IXMLDOMDocument2 **)&bstrString);
  if ( v2 >= 0 )
  {
    ppv = 0;
    v3 = CoCreateInstance(
           &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
           0,
           1u,
           &GUID_373984c8_b845_449b_91e7_45ac83036ade,
           &ppv);
    v4 = bstrString;
    v2 = v3;
    if ( v3 >= 0 )
    {
      v5 = SysAllocString(L"urn:OfflineFiles-ConflictStore-Schema");
      if ( v5 )
      {
        v6 = ppv;
        v7 = *(_QWORD *)ppv;
        pvarg.llVal = (LONGLONG)v4;
        v8 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v7 + 56);
        pvarg.vt = 9;
        if ( v4 )
        {
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v4 + 8LL))(v4);
          v6 = ppv;
        }
        v14 = pvarg;
        v9 = v8(v6, v5, &v14);
        VariantClear(&pvarg);
        if ( v9 < 0 )
        {
          pperrinfo = 0;
          if ( GetErrorInfo(0, &pperrinfo) )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids);
            }
          }
          else
          {
            bstrString = 0;
            if ( ((int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &bstrString) < 0 )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33,
                  WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids,
                  bstrString);
              }
              SysFreeString(bstrString);
            }
            ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
          }
          v2 = -2147467259;
        }
        else
        {
          lpVtbl = a1->lpVtbl;
          pvarg.llVal = (LONGLONG)ppv;
          putref_schemas = lpVtbl->putref_schemas;
          pvarg.vt = 9;
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
          v14 = pvarg;
          v2 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))putref_schemas)(a1, &v14);
          if ( pvarg.vt == 4095 )
            pvarg.vt = 8;
          VariantClear(&pvarg);
        }
      }
      else
      {
        v2 = -2147024882;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      SysFreeString(v5);
    }
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids, (unsigned int)v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800255dc  push    rbp
0x1800255de  push    rbx
0x1800255df  push    rsi
0x1800255e0  push    rdi
0x1800255e1  push    r12
0x1800255e3  push    r13
0x1800255e5  push    r14
0x1800255e7  mov     rbp, rsp
0x1800255ea  sub     rsp, 70h
0x1800255ee  lea     rdx, [rbp+bstrString]; struct IXMLDOMDocument2 **
0x1800255f2  mov     [rbp+bstrString], 0
0x1800255fa  mov     r14, rcx
0x1800255fd  call    ?ConflictStore_XsdSchemaDocFromHtmlResource@@YAJIPEAPEAUIXMLDOMDocument2@@@Z; ConflictStore_XsdSchemaDocFromHtmlResource(uint,IXMLDOMDocument2 * *)
0x180025602  lea     r13, WPP_GLOBAL_Control
0x180025609  mov     edi, eax
0x18002560b  mov     r12d, 800000h
0x180025611  test    eax, eax
0x180025613  js      loc_180025858
0x180025619  xor     edx, edx; pUnkOuter
0x18002561b  mov     [rbp+arg_8], 0
0x180025623  lea     rax, [rbp+arg_8]
0x180025627  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x18002562e  mov     [rsp+70h+ppv], rax; ppv
0x180025633  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x18002563a  lea     r8d, [rdx+1]; dwClsContext
0x18002563e  call    cs:__imp_CoCreateInstance
0x180025644  mov     rsi, [rbp+bstrString]
0x180025648  mov     edi, eax
0x18002564a  test    eax, eax
0x18002564c  js      loc_180025849
0x180025652  lea     rcx, aUrnOfflinefile; "urn:OfflineFiles-ConflictStore-Schema"
0x180025659  call    cs:__imp_SysAllocString
0x18002565f  mov     rbx, rax
0x180025662  test    rax, rax
0x180025665  jnz     short loc_180025671
0x180025667  mov     edi, 8007000Eh
0x18002566c  jmp     loc_180025830
0x180025671  mov     rcx, [rbp+arg_8]
0x180025675  mov     rax, [rcx]
0x180025678  mov     qword ptr [rbp+pvarg+8], rsi
0x18002567c  mov     rdi, [rax+38h]
0x180025680  mov     eax, 9
0x180025685  mov     word ptr [rbp+pvarg], ax
0x180025689  test    rsi, rsi
0x18002568c  jz      short loc_1800256A1
0x18002568e  mov     rax, [rsi]
0x180025691  mov     rcx, rsi
0x180025694  mov     rax, [rax+8]
0x180025698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002569d  mov     rcx, [rbp+arg_8]
0x1800256a1  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800256a5  lea     r8, [rbp+var_20]
0x1800256a9  mov     rdx, rbx
0x1800256ac  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800256b1  mov     rax, rdi
0x1800256b4  movaps  [rbp+var_20], xmm0
0x1800256b8  movsd   [rbp+var_10], xmm1
0x1800256bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256c2  mov     ecx, 0FFFh
0x1800256c7  mov     edi, eax
0x1800256c9  mov     eax, 8
0x1800256ce  cmp     word ptr [rbp+pvarg], cx
0x1800256d2  jnz     short loc_1800256D8
0x1800256d4  mov     word ptr [rbp+pvarg], ax
0x1800256d8  lea     rcx, [rbp+pvarg]; pvarg
0x1800256dc  call    cs:__imp_VariantClear
0x1800256e2  test    edi, edi
0x1800256e4  js      short loc_180025758
0x1800256e6  mov     rax, [r14]
0x1800256e9  mov     rcx, [rbp+arg_8]
0x1800256ed  mov     qword ptr [rbp+pvarg+8], rcx
0x1800256f1  mov     rdi, [rax+270h]
0x1800256f8  mov     eax, 9
0x1800256fd  mov     word ptr [rbp+pvarg], ax
0x180025701  test    rcx, rcx
0x180025704  jz      short loc_180025712
0x180025706  mov     rax, [rcx]
0x180025709  mov     rax, [rax+8]
0x18002570d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025712  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180025716  lea     rdx, [rbp+var_20]
0x18002571a  mov     rcx, r14
0x18002571d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180025722  mov     rax, rdi
0x180025725  movaps  [rbp+var_20], xmm0
0x180025729  movsd   [rbp+var_10], xmm1
0x18002572e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025733  mov     edi, eax
0x180025735  mov     eax, 0FFFh
0x18002573a  cmp     word ptr [rbp+pvarg], ax
0x18002573e  jnz     short loc_180025749
0x180025740  mov     eax, 8
0x180025745  mov     word ptr [rbp+pvarg], ax
0x180025749  lea     rcx, [rbp+pvarg]; pvarg
0x18002574d  call    cs:__imp_VariantClear
0x180025753  jmp     loc_180025830
0x180025758  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002575c  mov     [rbp+pperrinfo], 0
0x180025764  xor     ecx, ecx; dwReserved
0x180025766  call    cs:__imp_GetErrorInfo
0x18002576c  test    eax, eax
0x18002576e  jnz     loc_180025804
0x180025774  mov     rcx, [rbp+pperrinfo]
0x180025778  lea     rdx, [rbp+bstrString]
0x18002577c  mov     [rbp+bstrString], 0
0x180025784  mov     rax, [rcx]
0x180025787  mov     rax, [rax+28h]
0x18002578b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025790  test    eax, eax
0x180025792  js      short loc_1800257CB
0x180025794  mov     rcx, cs:WPP_GLOBAL_Control
0x18002579b  cmp     rcx, r13
0x18002579e  jz      short loc_1800257BF
0x1800257a0  test    [rcx+1Ch], r12d
0x1800257a4  jz      short loc_1800257BF
0x1800257a6  mov     r9, [rbp+bstrString]
0x1800257aa  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x1800257b1  mov     rcx, [rcx+10h]
0x1800257b5  mov     edx, 21h ; '!'
0x1800257ba  call    WPP_SF_S
0x1800257bf  mov     rcx, [rbp+bstrString]; bstrString
0x1800257c3  call    cs:__imp_SysFreeString
0x1800257c9  jmp     short loc_1800257F2
0x1800257cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257d2  cmp     rcx, r13
0x1800257d5  jz      short loc_1800257F2
0x1800257d7  test    [rcx+1Ch], r12d
0x1800257db  jz      short loc_1800257F2
0x1800257dd  mov     rcx, [rcx+10h]
0x1800257e1  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x1800257e8  mov     edx, 22h ; '"'
0x1800257ed  call    WPP_SF_
0x1800257f2  mov     rcx, [rbp+pperrinfo]
0x1800257f6  mov     rax, [rcx]
0x1800257f9  mov     rax, [rax+10h]
0x1800257fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025802  jmp     short loc_18002582B
0x180025804  mov     rcx, cs:WPP_GLOBAL_Control
0x18002580b  cmp     rcx, r13
0x18002580e  jz      short loc_18002582B
0x180025810  test    [rcx+1Ch], r12d
0x180025814  jz      short loc_18002582B
0x180025816  mov     rcx, [rcx+10h]
0x18002581a  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x180025821  mov     edx, 23h ; '#'
0x180025826  call    WPP_SF_
0x18002582b  mov     edi, 80004005h
0x180025830  mov     rcx, [rbp+arg_8]
0x180025834  mov     rax, [rcx]
0x180025837  mov     rax, [rax+10h]
0x18002583b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025840  mov     rcx, rbx; bstrString
0x180025843  call    cs:__imp_SysFreeString
0x180025849  mov     rax, [rsi]
0x18002584c  mov     rcx, rsi
0x18002584f  mov     rax, [rax+10h]
0x180025853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025858  mov     rcx, cs:WPP_GLOBAL_Control
0x18002585f  cmp     rcx, r13
0x180025862  jz      short loc_180025882
0x180025864  test    [rcx+1Ch], r12d
0x180025868  jz      short loc_180025882
0x18002586a  mov     rcx, [rcx+10h]
0x18002586e  lea     r8, WPP_02028e3dddf63d5a7432d80ff826e539_Traceguids
0x180025875  mov     edx, 24h ; '$'
0x18002587a  mov     r9d, edi
0x18002587d  call    WPP_SF_d
0x180025882  mov     eax, edi
0x180025884  add     rsp, 70h
0x180025888  pop     r14
0x18002588a  pop     r13
0x18002588c  pop     r12
0x18002588e  pop     rdi
0x18002588f  pop     rsi
0x180025890  pop     rbx
0x180025891  pop     rbp
0x180025892  retn
```
