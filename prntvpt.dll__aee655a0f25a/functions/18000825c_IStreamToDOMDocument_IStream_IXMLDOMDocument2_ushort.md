# IStreamToDOMDocument(IStream *,IXMLDOMDocument2 * *,ushort * *)

- ea: `0x18000825c`
- end: `0x180008491`
- name: `?IStreamToDOMDocument@@YAJPEAUIStream@@PEAPEAUIXMLDOMDocument2@@PEAPEAG@Z`
- size: `565`
- prototype: `__int64 __fastcall(struct IStream *, struct IXMLDOMDocument2 **, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008190`
- `0x1800121d0`
- `0x180013380`
- `0x180013420`
- `0x1800141b0`

## callees

- `0x180007660`
- `0x18000825c`
- `0x180008da4`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800083dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800083dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008428`
- `OLEAUT32!__imp_SysFreeString` at `0x180008428`
- `OLEAUT32!__imp_SysStringLen` at `0x1800083cf`
- `OLEAUT32!__imp_SysStringLen` at `0x1800083cf`
- `OLEAUT32!__imp_VariantInit` at `0x1800082cd`
- `OLEAUT32!__imp_VariantInit` at `0x1800082cd`
- `OLEAUT32!__imp_VariantClear` at `0x180008432`
- `OLEAUT32!__imp_VariantClear` at `0x180008432`

## pseudocode

```c
__int64 __fastcall IStreamToDOMDocument(struct IStream *a1, struct IXMLDOMDocument2 **a2, unsigned __int16 **a3)
{
  int v6; // esi
  __int64 v7; // rax
  int v8; // eax
  int v9; // ebx
  int v10; // edi
  int v11; // ebx
  OLECHAR *v12; // rcx
  signed int v13; // ebx
  unsigned __int16 *v14; // rax
  LPVOID v15; // rcx
  struct IXMLDOMDocument2 *v16; // rax
  int v18; // [rsp+30h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-21h] BYREF
  __int64 v20; // [rsp+40h] [rbp-19h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-9h] BYREF
  VARIANTARG v23; // [rsp+70h] [rbp+17h] BYREF
  __int16 v24; // [rsp+C8h] [rbp+6Fh] BYREF
  int v25; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !a2 || !a1 )
    return 2147942487LL;
  ppv = 0;
  if ( a3 )
    *a3 = 0;
  v6 = NPrintTicketUtil::CreateDomDocument(&ppv, a2);
  if ( v6 < 0 )
    goto LABEL_25;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.llVal = (LONGLONG)a1;
  pvarg.vt = 13;
  ((void (__fastcall *)(struct IStream *))a1->lpVtbl->AddRef)(a1);
  v7 = *(_QWORD *)ppv;
  v23 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v7 + 464))(ppv, &v23, &v24);
  if ( !v24 )
  {
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 480LL))(ppv, &v20);
    v6 = v8;
    if ( !v20 )
    {
      v6 = -2147418113;
      goto LABEL_21;
    }
    if ( v8 >= 0 )
    {
      v18 = 0;
      v25 = 0;
      pbstr = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 88LL))(v20, &v18);
      v10 = v9 | (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 96LL))(v20, &v25);
      v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v20 + 72LL))(v20, &pbstr);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( !(v10 | v11) && a3 )
      {
        v12 = pbstr;
        if ( !pbstr )
        {
          *a3 = 0;
LABEL_19:
          v6 = -2147221501;
          goto LABEL_20;
        }
        v13 = SysStringLen(pbstr) + 69;
        v14 = SysAllocStringLen(0, v13);
        *a3 = v14;
        if ( v14 )
          v6 = StringCchPrintfW(v14, v13, L"%s(%d,%d)", pbstr, v18, v25);
        if ( v6 < 0 )
        {
          v12 = pbstr;
LABEL_20:
          SysFreeString(v12);
          goto LABEL_21;
        }
      }
      v12 = pbstr;
      goto LABEL_19;
    }
  }
LABEL_21:
  VariantClear(&pvarg);
  if ( v6 >= 0 )
  {
    v15 = ppv;
    v16 = 0;
    if ( ppv )
    {
      v16 = (struct IXMLDOMDocument2 *)ppv;
      v15 = 0;
      ppv = 0;
    }
    *a2 = v16;
    goto LABEL_26;
  }
LABEL_25:
  v15 = ppv;
LABEL_26:
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000825c  mov     [rsp-8+arg_0], rbx
0x180008261  mov     [rsp-8+arg_10], rsi
0x180008266  push    rbp
0x180008267  push    rdi
0x180008268  push    r12
0x18000826a  push    r14
0x18000826c  push    r15
0x18000826e  lea     rbp, [rsp-37h]
0x180008273  sub     rsp, 90h
0x18000827a  xor     r12d, r12d
0x18000827d  mov     r14, r8
0x180008280  mov     r15, rdx
0x180008283  mov     rbx, rcx
0x180008286  test    rdx, rdx
0x180008289  jz      loc_180008470
0x18000828f  test    rcx, rcx
0x180008292  jz      loc_180008470
0x180008298  mov     [rbp+57h+ppv], r12
0x18000829c  test    r8, r8
0x18000829f  jz      short loc_1800082A4
0x1800082a1  mov     [r8], r12
0x1800082a4  lea     rcx, [rbp+57h+ppv]; ppv
0x1800082a8  call    ?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z; NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)
0x1800082ad  mov     esi, eax
0x1800082af  test    eax, eax
0x1800082b1  js      loc_180008457
0x1800082b7  xorps   xmm0, xmm0
0x1800082ba  mov     [rbp+57h+arg_8], r12w
0x1800082bf  xor     eax, eax
0x1800082c1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800082c5  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800082c9  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800082cd  call    cs:__imp_VariantInit
0x1800082d3  mov     eax, 0Dh
0x1800082d8  mov     qword ptr [rbp+57h+pvarg+8], rbx
0x1800082dc  mov     word ptr [rbp+57h+pvarg], ax
0x1800082e0  mov     rcx, rbx
0x1800082e3  mov     rax, [rbx]
0x1800082e6  mov     rax, [rax+8]
0x1800082ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ef  mov     rcx, [rbp+57h+ppv]
0x1800082f3  lea     r8, [rbp+57h+arg_8]
0x1800082f7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800082fb  lea     rdx, [rbp+57h+var_40]
0x1800082ff  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180008304  mov     rax, [rcx]
0x180008307  movaps  [rbp+57h+var_40], xmm0
0x18000830b  movsd   [rbp+57h+var_30], xmm1
0x180008310  mov     rax, [rax+1D0h]
0x180008317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000831c  mov     esi, eax
0x18000831e  cmp     [rbp+57h+arg_8], r12w
0x180008323  jnz     loc_18000842E
0x180008329  mov     rcx, [rbp+57h+ppv]
0x18000832d  lea     rdx, [rbp+57h+var_70]
0x180008331  mov     [rbp+57h+var_70], r12
0x180008335  mov     rax, [rcx]
0x180008338  mov     rax, [rax+1E0h]
0x18000833f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008344  mov     rcx, [rbp+57h+var_70]
0x180008348  mov     esi, eax
0x18000834a  test    rcx, rcx
0x18000834d  jnz     short loc_180008359
0x18000834f  mov     esi, 8000FFFFh
0x180008354  jmp     loc_18000842E
0x180008359  test    eax, eax
0x18000835b  js      loc_18000842E
0x180008361  mov     [rbp+57h+var_80], r12d
0x180008365  lea     rdx, [rbp+57h+var_80]
0x180008369  mov     [rbp+57h+arg_18], r12d
0x18000836d  mov     [rbp+57h+pbstr], r12
0x180008371  mov     rax, [rcx]
0x180008374  mov     rax, [rax+58h]
0x180008378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000837d  mov     rcx, [rbp+57h+var_70]
0x180008381  mov     ebx, eax
0x180008383  mov     rdx, [rcx]
0x180008386  mov     rax, [rdx+60h]
0x18000838a  lea     rdx, [rbp+57h+arg_18]
0x18000838e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008393  mov     rcx, [rbp+57h+var_70]
0x180008397  mov     edi, eax
0x180008399  or      edi, ebx
0x18000839b  mov     rdx, [rcx]
0x18000839e  mov     rax, [rdx+48h]
0x1800083a2  lea     rdx, [rbp+57h+pbstr]
0x1800083a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ab  mov     rcx, [rbp+57h+var_70]
0x1800083af  mov     ebx, eax
0x1800083b1  mov     rdx, [rcx]
0x1800083b4  mov     rax, [rdx+10h]
0x1800083b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083bd  or      ebx, edi
0x1800083bf  jnz     short loc_18000841F
0x1800083c1  test    r14, r14
0x1800083c4  jz      short loc_18000841F
0x1800083c6  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800083ca  test    rcx, rcx
0x1800083cd  jz      short loc_18000841A
0x1800083cf  call    cs:__imp_SysStringLen
0x1800083d5  xor     ecx, ecx; strIn
0x1800083d7  lea     ebx, [rax+45h]
0x1800083da  mov     edx, ebx; ui
0x1800083dc  call    cs:__imp_SysAllocStringLen
0x1800083e2  mov     [r14], rax
0x1800083e5  test    rax, rax
0x1800083e8  jz      short loc_180008410
0x1800083ea  mov     ecx, [rbp+57h+arg_18]
0x1800083ed  lea     r8, aSDD; "%s(%d,%d)"
0x1800083f4  mov     r9, [rbp+57h+pbstr]
0x1800083f8  mov     [rsp+0B0h+var_88], ecx
0x1800083fc  mov     ecx, [rbp+57h+var_80]
0x1800083ff  mov     [rsp+0B0h+var_90], ecx
0x180008403  mov     rcx, rax; unsigned __int16 *
0x180008406  movsxd  rdx, ebx; unsigned __int64
0x180008409  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000840e  mov     esi, eax
0x180008410  test    esi, esi
0x180008412  jns     short loc_18000841F
0x180008414  mov     rcx, [rbp+57h+pbstr]
0x180008418  jmp     short loc_180008428
0x18000841a  mov     [r14], r12
0x18000841d  jmp     short loc_180008423
0x18000841f  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180008423  mov     esi, 80040003h
0x180008428  call    cs:__imp_SysFreeString
0x18000842e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180008432  call    cs:__imp_VariantClear
0x180008438  test    esi, esi
0x18000843a  js      short loc_180008457
0x18000843c  mov     rcx, [rbp+57h+ppv]
0x180008440  mov     rax, r12
0x180008443  test    rcx, rcx
0x180008446  jz      short loc_180008452
0x180008448  mov     rax, rcx
0x18000844b  mov     rcx, r12
0x18000844e  mov     [rbp+57h+ppv], rcx
0x180008452  mov     [r15], rax
0x180008455  jmp     short loc_18000845B
0x180008457  mov     rcx, [rbp+57h+ppv]
0x18000845b  test    rcx, rcx
0x18000845e  jz      short loc_18000846C
0x180008460  mov     rax, [rcx]
0x180008463  mov     rax, [rax+10h]
0x180008467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846c  mov     eax, esi
0x18000846e  jmp     short loc_180008475
0x180008470  mov     eax, 80070057h
0x180008475  lea     r11, [rsp+0B0h+var_20]
0x18000847d  mov     rbx, [r11+30h]
0x180008481  mov     rsi, [r11+40h]
0x180008485  mov     rsp, r11
0x180008488  pop     r15
0x18000848a  pop     r14
0x18000848c  pop     r12
0x18000848e  pop     rdi
0x18000848f  pop     rbp
0x180008490  retn
```
