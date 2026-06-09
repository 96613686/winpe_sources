# CCertRequest::_GetSCEPProperty(ushort * const,long,long,long,ushort * *)

- ea: `0x18001027c`
- end: `0x18001043a`
- name: `?_GetSCEPProperty@CCertRequest@@AEAAJQEAGJJJPEAPEAG@Z`
- size: `446`
- prototype: `int(CCertRequest *__hidden this, unsigned __int16 *const, int, int, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e140`

## callees

- `0x18000b9cc`
- `0x18001027c`
- `0x1800127a4`
- `0x180028590`
- `0x180028638`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010404`
- `OLEAUT32!__imp_SysFreeString` at `0x18001040f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010419`
- `OLEAUT32!__imp_SysFreeString` at `0x180010404`
- `OLEAUT32!__imp_SysFreeString` at `0x18001040f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010419`
- `OLEAUT32!__imp_SysStringLen` at `0x1800103bd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800103bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800103cf`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800102df`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800103a7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800102df`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800103a7`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180010354`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800103f9`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180010354`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800103f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertRequest::_GetSCEPProperty(
        CCertRequest *this,
        unsigned __int16 *const a2,
        int a3,
        int a4,
        int a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v10; // rbx
  unsigned __int16 **v11; // r14
  void *v12; // rcx
  unsigned int v13; // ecx
  int v14; // edx
  unsigned int v15; // edi
  unsigned int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  UINT v20; // eax
  __int64 v21; // rsi
  unsigned __int16 *v22; // rax
  BSTR v24; // [rsp+30h] [rbp-10h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF

  v10 = 0;
  pbstr = 0;
  v24 = 0;
  bstrString = 0;
  v11 = a6;
  *a6 = 0;
  v12 = (void *)*((_QWORD *)this + 17);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 17) = 0;
  }
  if ( a4 )
  {
    v13 = 239600324;
LABEL_5:
    v14 = -2147024809;
    v15 = -2147024809;
LABEL_6:
    CSPrintErrorLineFile(v13, v14);
    goto LABEL_28;
  }
  v16 = scepParseRequestHeaderParameter(a2, 0, &v24, &bstrString);
  v15 = v16;
  if ( v16 )
  {
    v14 = v16;
    v13 = 240124612;
    goto LABEL_6;
  }
  if ( a3 == 1000 )
  {
LABEL_17:
    if ( a5 != 3 )
    {
      v13 = 240714436;
      goto LABEL_5;
    }
    v19 = NDESGetServerCertificates(v24, bstrString, a3 == 1002, v11, &pbstr);
    v15 = v19;
    if ( v19 )
    {
      v17 = v19;
      v18 = 241238724;
      goto LABEL_21;
    }
LABEL_22:
    v15 = 0;
    goto LABEL_23;
  }
  if ( a3 != 1001 )
  {
    if ( a3 != 1002 )
    {
      v13 = 242680516;
      goto LABEL_5;
    }
    goto LABEL_17;
  }
  if ( a5 != 4 )
  {
    v13 = 241763012;
    goto LABEL_5;
  }
  v15 = NDESGetServerCapabilities(v24, bstrString, v11, &pbstr);
  CSPrintErrorLineFileData(*v11, 0xE7002C4u, v15);
  if ( !v15 )
    goto LABEL_22;
  v17 = v15;
  v18 = 242287300;
LABEL_21:
  CSPrintErrorLineFile(v18, v17);
LABEL_23:
  v10 = pbstr;
  if ( pbstr )
  {
    v20 = SysStringLen(pbstr);
    if ( v20 )
    {
      v21 = v20 + 1;
      v22 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21);
      *((_QWORD *)this + 17) = v22;
      if ( v22 )
        StringCchCopyW(v22, (unsigned int)v21, v10);
      CSPrintErrorLineFileData(v10, 0xE8802C4u, v15);
    }
  }
LABEL_28:
  SysFreeString(bstrString);
  SysFreeString(v24);
  SysFreeString(v10);
  return v15;
}

```

## disassembly

```asm
0x18001027c  mov     [rsp-28h+arg_8], rbx
0x180010281  mov     [rsp-28h+arg_10], rsi
0x180010286  push    rbp
0x180010287  push    rdi
0x180010288  push    r12
0x18001028a  push    r14
0x18001028c  push    r15
0x18001028e  mov     rbp, rsp
0x180010291  sub     rsp, 40h
0x180010295  mov     edi, r9d
0x180010298  mov     esi, r8d
0x18001029b  mov     r12, rdx
0x18001029e  mov     r15, rcx
0x1800102a1  xor     ebx, ebx
0x1800102a3  mov     [rbp+pbstr], rbx
0x1800102a7  mov     [rbp+var_10], rbx
0x1800102ab  mov     [rbp+bstrString], rbx
0x1800102af  mov     r14, [rbp+arg_28]
0x1800102b3  mov     [r14], rbx
0x1800102b6  mov     rcx, [rcx+88h]; pv
0x1800102bd  test    rcx, rcx
0x1800102c0  jz      short loc_1800102CF
0x1800102c2  call    cs:__imp_CoTaskMemFree
0x1800102c8  mov     [r15+88h], rbx
0x1800102cf  test    edi, edi
0x1800102d1  jz      short loc_1800102EA
0x1800102d3  mov     ecx, 0E4802C4h
0x1800102d8  mov     edx, 80070057h
0x1800102dd  mov     edi, edx
0x1800102df  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800102e5  jmp     loc_180010400
0x1800102ea  lea     r9, [rbp+bstrString]; unsigned __int16 **
0x1800102ee  lea     r8, [rbp+var_10]; unsigned __int16 **
0x1800102f2  xor     edx, edx; unsigned __int16 *
0x1800102f4  mov     rcx, r12; unsigned __int16 *
0x1800102f7  call    ?scepParseRequestHeaderParameter@@YAJPEAGPEBGPEAPEAG2@Z; scepParseRequestHeaderParameter(ushort *,ushort const *,ushort * *,ushort * *)
0x1800102fc  mov     edi, eax
0x1800102fe  test    eax, eax
0x180010300  jz      short loc_18001030B
0x180010302  mov     edx, eax
0x180010304  mov     ecx, 0E5002C4h
0x180010309  jmp     short loc_1800102DF
0x18001030b  mov     ecx, esi
0x18001030d  sub     ecx, 3E8h
0x180010313  jz      short loc_180010367
0x180010315  sub     ecx, 1
0x180010318  jz      short loc_180010326
0x18001031a  cmp     ecx, 1
0x18001031d  jz      short loc_180010367
0x18001031f  mov     ecx, 0E7702C4h
0x180010324  jmp     short loc_1800102D8
0x180010326  cmp     [rbp+arg_20], 4
0x18001032a  jz      short loc_180010333
0x18001032c  mov     ecx, 0E6902C4h
0x180010331  jmp     short loc_1800102D8
0x180010333  lea     r9, [rbp+pbstr]; unsigned __int16 **
0x180010337  mov     r8, r14; unsigned __int16 **
0x18001033a  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18001033e  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180010342  call    ?NDESGetServerCapabilities@@YAJPEAG0PEAPEAG1@Z; NDESGetServerCapabilities(ushort *,ushort *,ushort * *,ushort * *)
0x180010347  mov     edi, eax
0x180010349  mov     r8d, eax
0x18001034c  mov     edx, 0E7002C4h
0x180010351  mov     rcx, [r14]
0x180010354  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001035a  test    edi, edi
0x18001035c  jz      short loc_1800103AF
0x18001035e  mov     edx, edi
0x180010360  mov     ecx, 0E7102C4h
0x180010365  jmp     short loc_1800103A7
0x180010367  cmp     [rbp+arg_20], 3
0x18001036b  jz      short loc_180010377
0x18001036d  mov     ecx, 0E5902C4h
0x180010372  jmp     loc_1800102D8
0x180010377  cmp     esi, 3EAh
0x18001037d  setz    r8b; bool
0x180010381  lea     rax, [rbp+pbstr]
0x180010385  mov     [rsp+40h+var_20], rax; unsigned __int16 **
0x18001038a  mov     r9, r14; unsigned __int16 **
0x18001038d  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180010391  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180010395  call    ?NDESGetServerCertificates@@YAJPEAG0_NPEAPEAG2@Z; NDESGetServerCertificates(ushort *,ushort *,bool,ushort * *,ushort * *)
0x18001039a  mov     edi, eax
0x18001039c  test    eax, eax
0x18001039e  jz      short loc_1800103AF
0x1800103a0  mov     edx, eax
0x1800103a2  mov     ecx, 0E6102C4h
0x1800103a7  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800103ad  jmp     short loc_1800103B1
0x1800103af  xor     edi, edi
0x1800103b1  mov     rbx, [rbp+pbstr]
0x1800103b5  test    rbx, rbx
0x1800103b8  jz      short loc_180010400
0x1800103ba  mov     rcx, rbx; pbstr
0x1800103bd  call    cs:__imp_SysStringLen
0x1800103c3  test    eax, eax
0x1800103c5  jz      short loc_180010400
0x1800103c7  inc     eax
0x1800103c9  mov     esi, eax
0x1800103cb  lea     rcx, [rax+rax]; cb
0x1800103cf  call    cs:__imp_CoTaskMemAlloc
0x1800103d5  mov     [r15+88h], rax
0x1800103dc  test    rax, rax
0x1800103df  jz      short loc_1800103EE
0x1800103e1  mov     r8, rbx; unsigned __int16 *
0x1800103e4  mov     edx, esi; unsigned __int64
0x1800103e6  mov     rcx, rax; unsigned __int16 *
0x1800103e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800103ee  mov     r8d, edi
0x1800103f1  mov     edx, 0E8802C4h
0x1800103f6  mov     rcx, rbx
0x1800103f9  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x1800103ff  nop
0x180010400  mov     rcx, [rbp+bstrString]; bstrString
0x180010404  call    cs:__imp_SysFreeString
0x18001040a  nop
0x18001040b  mov     rcx, [rbp+var_10]; bstrString
0x18001040f  call    cs:__imp_SysFreeString
0x180010415  nop
0x180010416  mov     rcx, rbx; bstrString
0x180010419  call    cs:__imp_SysFreeString
0x18001041f  mov     eax, edi
0x180010421  lea     r11, [rsp+40h+var_s0]
0x180010426  mov     rbx, [r11+38h]
0x18001042a  mov     rsi, [r11+40h]
0x18001042e  mov     rsp, r11
0x180010431  pop     r15
0x180010433  pop     r14
0x180010435  pop     r12
0x180010437  pop     rdi
0x180010438  pop     rbp
0x180010439  retn
```
