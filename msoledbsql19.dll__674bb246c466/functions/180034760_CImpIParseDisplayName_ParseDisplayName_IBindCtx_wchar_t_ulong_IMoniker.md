# CImpIParseDisplayName::ParseDisplayName(IBindCtx *,wchar_t *,ulong *,IMoniker * *)

- ea: `0x180034760`
- end: `0x180034a4e`
- name: `?ParseDisplayName@CImpIParseDisplayName@@UEAAJPEAUIBindCtx@@PEA_WPEAKPEAPEAUIMoniker@@@Z`
- size: `750`
- prototype: `int(CImpIParseDisplayName *__hidden this, struct IBindCtx *, wchar_t *, unsigned int *, struct IMoniker **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x180003090`
- `0x1800030c0`
- `0x180003d80`
- `0x180009340`
- `0x180034760`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180034862`
- `ole32!CoCreateInstance` at `0x180034862`
- `ole32!CreatePointerMoniker` at `0x18003494b`
- `ole32!CreatePointerMoniker` at `0x18003494b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800348db`
- `OLEAUT32!__imp_SysAllocString` at `0x1800348db`
- `OLEAUT32!__imp_VariantInit` at `0x18003483c`
- `OLEAUT32!__imp_VariantInit` at `0x18003483c`
- `OLEAUT32!__imp_VariantClear` at `0x180034978`
- `OLEAUT32!__imp_VariantClear` at `0x180034978`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180034832`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180034832`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CImpIParseDisplayName::ParseDisplayName(
        CImpIParseDisplayName *this,
        struct IBindCtx *a2,
        wchar_t *a3,
        unsigned int *a4,
        struct IMoniker **ppmk)
{
  int v7; // eax
  HRESULT v8; // eax
  HRESULT PointerMoniker; // ebx
  int v10; // eax
  LPVOID ppv; // [rsp+40h] [rbp-81h] BYREF
  LPUNKNOWN punk; // [rsp+48h] [rbp-79h] BYREF
  __int64 v14; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-69h] BYREF
  int v16; // [rsp+60h] [rbp-61h]
  GUID v17; // [rsp+64h] [rbp-5Dh]
  __int64 v18; // [rsp+80h] [rbp-41h] BYREF
  DBID v19; // [rsp+90h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-11h] BYREF

  v14 = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266320[0] )
    bidScopeEnterW(&v14, off_180266320[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  if ( ppmk )
    *ppmk = 0;
  if ( !a3 || !a4 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v7 = bidTraceHR(off_180260358[0], 522249, 2147746277LL);
    else
      v7 = -2147221019;
    goto LABEL_29;
  }
  if ( !ppmk )
  {
    if ( (bidGblFlags & 2) != 0 )
      v7 = bidTraceHR(off_180260358[0], 528393, 2147549183LL);
    else
      v7 = -2147418113;
LABEL_29:
    PointerMoniker = CError::PostHResult(g_pCError, v7, &IID_IParseDisplayName);
    goto LABEL_30;
  }
  ppv = 0;
  punk = 0;
  SetErrorInfo(0, 0);
  VariantInit(&pvarg);
  v8 = CoCreateInstance(&CLSID_MSOLEDBSQL19, 0, 1u, &IID_IDBProperties, &ppv);
  PointerMoniker = v8;
  if ( v8 >= 0 )
  {
    v15 = &v18;
    v16 = 1;
    v17 = DBPROPSET_DBINIT;
    v18 = 59;
    v19 = DB_NULLID;
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 40LL))(ppv, 1, &v15);
    PointerMoniker = v10;
    if ( v10 >= 0 )
    {
      (**(void (__fastcall ***)(LPVOID, GUID *, LPUNKNOWN *))ppv)(ppv, &IID_IUnknown, &punk);
      PointerMoniker = CreatePointerMoniker(punk, ppmk);
      if ( PointerMoniker < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(off_180260358[0], 584713);
        *ppmk = 0;
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260358[0], 574473, (unsigned int)v10);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    _mm_lfence();
    bidTraceHR(off_180260358[0], 556041, (unsigned int)v8);
  }
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( punk )
    ((void (__fastcall *)(LPUNKNOWN))punk->lpVtbl->Release)(punk);
LABEL_30:
  if ( (bidGblFlags & 2) != 0 && off_180262F10[0] )
    bidTraceW(off_180260358[0], 601088, off_180262F10[0], (unsigned int)PointerMoniker);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v14);
  return (unsigned int)PointerMoniker;
}

```

## disassembly

```asm
0x180034760  push    rbp
0x180034762  push    rbx
0x180034763  push    rsi
0x180034764  push    rdi
0x180034765  push    r14
0x180034767  push    r15
0x180034769  lea     rbp, [rsp-27h]
0x18003476e  sub     rsp, 0E8h
0x180034775  mov     rax, cs:__security_cookie
0x18003477c  xor     rax, rsp
0x18003477f  mov     [rbp+4Fh+var_40], rax
0x180034783  mov     r14, r9
0x180034786  mov     rsi, r8
0x180034789  mov     rdi, [rbp+4Fh+ppmk]
0x18003478d  mov     [rbp+4Fh+var_C0], 0FFFFFFFFFFFFFFFFh
0x180034795  test    byte ptr cs:_bidGblFlags, 4
0x18003479c  jz      short loc_1800347D4
0x18003479e  mov     rax, cs:off_180266320; "<IParseDisplayName::ParseDisplayName|OL"...
0x1800347a5  test    rax, rax
0x1800347a8  jz      short loc_1800347D4
0x1800347aa  mov     r8, [rcx+8]
0x1800347ae  mov     [rsp+110h+var_E0], rdi
0x1800347b3  mov     [rsp+110h+var_E8], r9
0x1800347b8  mov     [rsp+110h+ppv], rsi
0x1800347bd  mov     r9, rdx
0x1800347c0  mov     r8d, [r8+34h]
0x1800347c4  mov     rdx, cs:off_180266320; "<IParseDisplayName::ParseDisplayName|OL"...
0x1800347cb  lea     rcx, [rbp+4Fh+var_C0]
0x1800347cf  call    _bidScopeEnterW
0x1800347d4  xor     r15d, r15d
0x1800347d7  test    rdi, rdi
0x1800347da  jz      short loc_1800347DF
0x1800347dc  mov     [rdi], r15
0x1800347df  test    rsi, rsi
0x1800347e2  jz      loc_1800349AD
0x1800347e8  test    r14, r14
0x1800347eb  jz      loc_1800349AD
0x1800347f1  test    rdi, rdi
0x1800347f4  jnz     short loc_180034825
0x1800347f6  test    byte ptr cs:_bidGblFlags, 2
0x1800347fd  jz      short loc_18003481B
0x1800347ff  mov     edx, 81009h
0x180034804  mov     r8d, 8000FFFFh
0x18003480a  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180034811  call    _bidTraceHR
0x180034816  jmp     loc_1800349D4
0x18003481b  mov     eax, 8000FFFFh
0x180034820  jmp     loc_1800349D4
0x180034825  mov     [rsp+110h+var_D0], r15
0x18003482a  mov     [rbp+4Fh+punk], r15
0x18003482e  xor     edx, edx; perrinfo
0x180034830  xor     ecx, ecx; dwReserved
0x180034832  call    cs:__imp_SetErrorInfo
0x180034838  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18003483c  call    cs:__imp_VariantInit
0x180034842  lea     rax, [rsp+110h+var_D0]
0x180034847  mov     [rsp+110h+ppv], rax; ppv
0x18003484c  lea     r9, IID_IDBProperties; riid
0x180034853  xor     edx, edx; pUnkOuter
0x180034855  mov     r8d, 1; dwClsContext
0x18003485b  lea     rcx, CLSID_MSOLEDBSQL19; rclsid
0x180034862  call    cs:__imp_CoCreateInstance
0x180034868  mov     ebx, eax
0x18003486a  test    eax, eax
0x18003486c  jns     short loc_180034897
0x18003486e  test    byte ptr cs:_bidGblFlags, 2
0x180034875  jz      loc_180034974
0x18003487b  lfence
0x18003487e  mov     r8d, eax
0x180034881  mov     edx, 87C09h
0x180034886  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003488d  call    _bidTraceHR
0x180034892  jmp     loc_180034974
0x180034897  lea     rax, [rbp+4Fh+var_90]
0x18003489b  mov     [rbp+4Fh+var_B8], rax
0x18003489f  mov     [rbp+4Fh+var_B0], 1
0x1800348a6  movups  xmm0, xmmword ptr cs:DBPROPSET_DBINIT.Data1
0x1800348ad  movups  [rbp+4Fh+var_AC], xmm0
0x1800348b1  mov     [rbp+4Fh+var_90], 3Bh ; ';'
0x1800348b9  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x1800348c0  movaps  [rbp+4Fh+var_80], xmm0
0x1800348c4  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x1800348cb  movaps  [rbp+4Fh+var_70], xmm1
0x1800348cf  mov     eax, 8
0x1800348d4  mov     word ptr [rbp+4Fh+pvarg], ax
0x1800348d8  mov     rcx, rsi; psz
0x1800348db  call    cs:__imp_SysAllocString
0x1800348e1  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x1800348e5  mov     rcx, [rsp+110h+var_D0]
0x1800348ea  mov     rax, [rcx]
0x1800348ed  lea     r8, [rbp+4Fh+var_B8]
0x1800348f1  mov     edx, 1
0x1800348f6  mov     rax, [rax+28h]
0x1800348fa  call    cs:__guard_dispatch_icall_fptr
0x180034900  mov     ebx, eax
0x180034902  test    eax, eax
0x180034904  jns     short loc_180034928
0x180034906  test    byte ptr cs:_bidGblFlags, 2
0x18003490d  jz      short loc_180034974
0x18003490f  lfence
0x180034912  mov     r8d, eax
0x180034915  mov     edx, 8C409h
0x18003491a  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180034921  call    _bidTraceHR
0x180034926  jmp     short loc_180034974
0x180034928  mov     rcx, [rsp+110h+var_D0]
0x18003492d  mov     rax, [rcx]
0x180034930  lea     r8, [rbp+4Fh+punk]
0x180034934  lea     rdx, IID_IUnknown
0x18003493b  mov     rax, [rax]
0x18003493e  call    cs:__guard_dispatch_icall_fptr
0x180034944  mov     rdx, rdi; ppmk
0x180034947  mov     rcx, [rbp+4Fh+punk]; punk
0x18003494b  call    cs:__imp_CreatePointerMoniker
0x180034951  mov     ebx, eax
0x180034953  test    eax, eax
0x180034955  jns     short loc_180034974
0x180034957  test    byte ptr cs:_bidGblFlags, 2
0x18003495e  jz      short loc_180034971
0x180034960  mov     edx, 8EC09h
0x180034965  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003496c  call    _bidTraceMark
0x180034971  mov     [rdi], r15
0x180034974  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180034978  call    cs:__imp_VariantClear
0x18003497e  mov     rcx, [rsp+110h+var_D0]
0x180034983  test    rcx, rcx
0x180034986  jz      short loc_180034995
0x180034988  mov     rax, [rcx]
0x18003498b  mov     rax, [rax+10h]
0x18003498f  call    cs:__guard_dispatch_icall_fptr
0x180034995  mov     rcx, [rbp+4Fh+punk]
0x180034999  test    rcx, rcx
0x18003499c  jz      short loc_1800349EB
0x18003499e  mov     rax, [rcx]
0x1800349a1  mov     rax, [rax+10h]
0x1800349a5  call    cs:__guard_dispatch_icall_fptr
0x1800349ab  jmp     short loc_1800349EB
0x1800349ad  test    byte ptr cs:_bidGblFlags, 2
0x1800349b4  jz      short loc_1800349CF
0x1800349b6  mov     edx, 7F809h
0x1800349bb  mov     r8d, 800401E5h
0x1800349c1  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800349c8  call    _bidTraceHR
0x1800349cd  jmp     short loc_1800349D4
0x1800349cf  mov     eax, 800401E5h
0x1800349d4  lea     r8, IID_IParseDisplayName; struct _GUID *
0x1800349db  mov     edx, eax; int
0x1800349dd  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x1800349e4  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x1800349e9  mov     ebx, eax
0x1800349eb  test    byte ptr cs:_bidGblFlags, 2
0x1800349f2  jz      short loc_180034A26
0x1800349f4  mov     rax, cs:off_180262F10; "<IParseDisplayName::ParseDisplayName|OL"...
0x1800349fb  test    rax, rax
0x1800349fe  jz      short loc_180034A26
0x180034a00  mov     [rsp+110h+var_E8], rdi
0x180034a05  mov     [rsp+110h+ppv], r14
0x180034a0a  mov     r9d, ebx
0x180034a0d  mov     r8, cs:off_180262F10; "<IParseDisplayName::ParseDisplayName|OL"...
0x180034a14  mov     edx, 92C00h
0x180034a19  mov     rcx, cs:off_180260358; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180034a20  call    _bidTraceW
0x180034a25  nop
0x180034a26  lea     rcx, [rbp+4Fh+var_C0]; this
0x180034a2a  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180034a2f  nop
0x180034a30  mov     eax, ebx
0x180034a32  mov     rcx, [rbp+4Fh+var_40]
0x180034a36  xor     rcx, rsp; StackCookie
0x180034a39  call    __security_check_cookie
0x180034a3e  add     rsp, 0E8h
0x180034a45  pop     r15
0x180034a47  pop     r14
0x180034a49  pop     rdi
0x180034a4a  pop     rsi
0x180034a4b  pop     rbx
0x180034a4c  pop     rbp
0x180034a4d  retn
```
