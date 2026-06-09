# CRootEnumerator::ParseDisplayName(IBindCtx *,ushort *,ulong *,IMoniker * *)

- ea: `0x18003e350`
- end: `0x18003e81e`
- name: `?ParseDisplayName@CRootEnumerator@@UEAAJPEAUIBindCtx@@PEAGPEAKPEAPEAUIMoniker@@@Z`
- size: `1230`
- prototype: `int(CRootEnumerator *__hidden this, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct IMoniker **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013870`
- `0x180026940`
- `0x180029c30`
- `0x180031ffc`
- `0x18003c270`
- `0x18003c9c4`
- `0x18003e350`
- `0x18003e824`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `msvcrt!wcschr` at `0x18003e50a`
- `msvcrt!wcschr` at `0x18003e50a`
- `KERNEL32!GetModuleHandleW` at `0x18003e58e`
- `KERNEL32!GetModuleHandleW` at `0x18003e58e`
- `KERNEL32!GetProcAddress` at `0x18003e59e`
- `KERNEL32!GetProcAddress` at `0x18003e59e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003e3e3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003e3e3`
- `ole32!CLSIDFromString` at `0x18003e4a4`
- `ole32!CLSIDFromString` at `0x18003e4a4`
- `ole32!CreatePointerMoniker` at `0x18003e620`
- `ole32!CreatePointerMoniker` at `0x18003e620`
- `ole32!CoCreateInstance` at `0x18003e707`
- `ole32!CoCreateInstance` at `0x18003e737`
- `ole32!CoCreateInstance` at `0x18003e707`
- `ole32!CoCreateInstance` at `0x18003e737`

## string_xrefs

- `0x18003e587`: `OLE32.DLL`
- `0x18003e594`: `CoCreateInstanceEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRootEnumerator::ParseDisplayName(
        CRootEnumerator *this,
        struct IBindCtx *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct IMoniker **ppmk)
{
  __int64 v9; // rsi
  unsigned int BidID; // eax
  int v11; // edx
  unsigned int v12; // edi
  wchar_t *v13; // r8
  __int64 v14; // rdx
  DWORD v15; // r12d
  int v16; // eax
  int v17; // edi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v20; // eax
  HRESULT PointerMoniker; // edi
  unsigned int v23; // r8d
  int v24; // ecx
  struct IMoniker **v25; // [rsp+30h] [rbp-71h]
  __int64 v26; // [rsp+40h] [rbp-61h] BYREF
  LPUNKNOWN punk; // [rsp+48h] [rbp-59h] BYREF
  CRootEnumerator *v28; // [rsp+50h] [rbp-51h]
  GUID *v29; // [rsp+58h] [rbp-49h] BYREF
  struct IUnknown *v30; // [rsp+60h] [rbp-41h]
  int v31; // [rsp+68h] [rbp-39h]
  __int128 v32; // [rsp+70h] [rbp-31h] BYREF
  __int128 v33; // [rsp+80h] [rbp-21h]
  __int64 v34; // [rsp+90h] [rbp-11h]
  GUID pclsid; // [rsp+98h] [rbp-9h] BYREF

  v28 = this;
  v26 = -1;
  v9 = 0;
  if ( (bidGblFlags & 4) != 0 && off_1800C9530[0] )
  {
    BidID = CRootEnumerator::GetBidID((CRootEnumerator *)((char *)this - 8));
    v25 = ppmk;
    bidScopeEnterW(&v26, off_1800C9530[0], BidID, a2, (_DWORD)a3, a4);
  }
  pclsid = 0;
  SetErrorInfo(0, 0);
  if ( !a3 || !a4 )
  {
    v12 = -2147221019;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_56;
    OLEDBTraceErr(-2147221019, L"<CRootEnumerator::ParseDisplayName|OLEDB|ERR> ", 0x2B8u);
    if ( (bidGblFlags & 2) == 0 || !off_1800C8FA8[0] )
      goto LABEL_56;
    v13 = off_1800C8FA8[0];
    v14 = 713728;
    goto LABEL_55;
  }
  if ( !ppmk )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CRootEnumerator::ParseDisplayName|OLEDB|ERR> ", 0x2BFu);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8FA0[0] )
          bidTraceW(off_1800C8388[0], 720896, off_1800C8FA0[0], 2147942487LL, (_DWORD)a4, 0, v25);
      }
    }
    if ( (bidGblFlags & 4) != 0 && v26 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v26);
    v11 = -2147024809;
    return CRootEnumerator::PostHResult((CRootEnumerator *)((char *)this - 8), v11, &IID_IParseDisplayName);
  }
  *ppmk = 0;
  *a4 = 0;
  if ( CLSIDFromString(a3, &pclsid) < 0 )
  {
    v12 = -2147221020;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_56;
    OLEDBTraceErr(-2147221020, L"<CRootEnumerator::ParseDisplayName|OLEDB|ERR> ", 0x2CBu);
    if ( (bidGblFlags & 2) == 0 || !off_1800C8F98[0] )
      goto LABEL_56;
    v13 = off_1800C8F98[0];
    v14 = 733184;
LABEL_55:
    bidTraceW(off_1800C8388[0], v14, v13, v12, (_DWORD)a4, (_DWORD)ppmk, v25);
LABEL_56:
    if ( (bidGblFlags & 4) != 0 && v26 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v26);
    v11 = v12;
    return CRootEnumerator::PostHResult((CRootEnumerator *)((char *)this - 8), v11, &IID_IParseDisplayName);
  }
  *a4 = wcschr(a3, 0x7Du) - a3 + 1;
  punk = 0;
  v15 = 21;
  if ( a2 )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    LODWORD(v32) = 40;
    v16 = ((__int64 (__fastcall *)(struct IBindCtx *, __int128 *))a2->lpVtbl->GetBindOptions)(a2, &v32);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v16, L"<CRootEnumerator::ParseDisplayName|OLEDB|ERR> ", 0x2EEu);
    }
    else
    {
      v15 = DWORD1(v33);
      v9 = v34;
    }
    ModuleHandleW = GetModuleHandleW(L"OLE32.DLL");
    ProcAddress = GetProcAddress(ModuleHandleW, "CoCreateInstanceEx");
    if ( ProcAddress )
    {
      v29 = &IID_IUnknown;
      v30 = 0;
      v31 = 0;
      v20 = ((__int64 (__fastcall *)(GUID *, _QWORD, _QWORD, __int64, int, GUID **, struct IMoniker **))ProcAddress)(
              &pclsid,
              0,
              v15,
              v9,
              1,
              &v29,
              v25);
      PointerMoniker = v20;
      if ( v20 >= 0 && v30 )
      {
        ATL::AtlComPtrAssign(&punk, v30);
        ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
LABEL_30:
        PointerMoniker = CreatePointerMoniker(punk, ppmk);
        goto LABEL_31;
      }
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_31:
        if ( PointerMoniker >= 0 )
          goto LABEL_33;
        goto LABEL_32;
      }
      v23 = 776;
      v24 = v20;
LABEL_43:
      OLEDBTraceErr(v24, L"<CRootEnumerator::ParseDisplayName|OLEDB|ERR> ", v23);
      goto LABEL_31;
    }
    if ( v17 < 0 )
      goto LABEL_30;
  }
  PointerMoniker = CoCreateInstance(&pclsid, 0, v15, &IID_IUnknown, (LPVOID *)&punk);
  if ( PointerMoniker == -2147024809 )
  {
    if ( (v15 & 0x10) == 0 )
      goto LABEL_49;
    PointerMoniker = CoCreateInstance(&pclsid, 0, v15 & 0xFFFFFFEF, &IID_IUnknown, (LPVOID *)&punk);
  }
  if ( PointerMoniker >= 0 )
    goto LABEL_30;
LABEL_49:
  if ( (bidGblFlags & 2) != 0 )
  {
    v23 = 801;
    v24 = PointerMoniker;
    goto LABEL_43;
  }
LABEL_32:
  CRootEnumerator::PostHResult((CRootEnumerator *)((char *)v28 - 8), PointerMoniker, &IID_IParseDisplayName);
LABEL_33:
  if ( (bidGblFlags & 2) != 0 && off_1800C8F90[0] )
    bidTraceW(off_1800C8388[0], 838656, off_1800C8F90[0], (unsigned int)PointerMoniker, (_DWORD)a4, (_DWORD)ppmk, v25);
  if ( (bidGblFlags & 4) != 0 && v26 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v26);
  ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&punk);
  return (unsigned int)PointerMoniker;
}

```

## disassembly

```asm
0x18003e350  push    rbp
0x18003e352  push    rbx
0x18003e353  push    rsi
0x18003e354  push    rdi
0x18003e355  push    r12
0x18003e357  push    r13
0x18003e359  push    r14
0x18003e35b  push    r15
0x18003e35d  lea     rbp, [rsp-17h]
0x18003e362  sub     rsp, 0B8h
0x18003e369  mov     rax, cs:__security_cookie
0x18003e370  xor     rax, rsp
0x18003e373  mov     [rbp+4Fh+var_48], rax
0x18003e377  mov     r14, r9
0x18003e37a  mov     rbx, r8
0x18003e37d  mov     rdi, rdx
0x18003e380  mov     r13, rcx
0x18003e383  mov     [rbp+4Fh+var_A0], rcx
0x18003e387  mov     r15, [rbp+4Fh+ppmk]
0x18003e38b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003e38f  mov     [rbp+4Fh+var_B0], r12
0x18003e393  xor     esi, esi
0x18003e395  test    byte ptr cs:_bidGblFlags, 4
0x18003e39c  jz      short loc_18003E3D8
0x18003e39e  mov     rax, cs:off_1800C9530; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e3a5  test    rax, rax
0x18003e3a8  jz      short loc_18003E3D8
0x18003e3aa  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18003e3ae  call    ?GetBidID@CRootEnumerator@@QEAAHXZ; CRootEnumerator::GetBidID(void)
0x18003e3b3  mov     rdx, cs:off_1800C9530; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e3ba  mov     [rsp+0F0h+var_C0], r15
0x18003e3bf  mov     [rsp+0F0h+var_C8], r14
0x18003e3c4  mov     [rsp+0F0h+ppv], rbx
0x18003e3c9  mov     r9, rdi
0x18003e3cc  mov     r8d, eax
0x18003e3cf  lea     rcx, [rbp+4Fh+var_B0]
0x18003e3d3  call    _bidScopeEnterW
0x18003e3d8  xorps   xmm0, xmm0
0x18003e3db  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x18003e3df  xor     edx, edx; perrinfo
0x18003e3e1  xor     ecx, ecx; dwReserved
0x18003e3e3  call    cs:__imp_SetErrorInfo
0x18003e3e9  test    rbx, rbx
0x18003e3ec  jz      loc_18003E760
0x18003e3f2  test    r14, r14
0x18003e3f5  jz      loc_18003E760
0x18003e3fb  test    r15, r15
0x18003e3fe  jnz     loc_18003E497
0x18003e404  mov     esi, 80070057h
0x18003e409  mov     bl, 2
0x18003e40b  test    byte ptr cs:_bidGblFlags, bl
0x18003e411  jz      short loc_18003E460
0x18003e413  mov     r8d, 2BFh; unsigned int
0x18003e419  lea     rdx, aCrootenumerato; "<CRootEnumerator::ParseDisplayName|OLED"...
0x18003e420  mov     ecx, esi; int
0x18003e422  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003e427  test    byte ptr cs:_bidGblFlags, bl
0x18003e42d  jz      short loc_18003E460
0x18003e42f  mov     rax, cs:off_1800C8FA0; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e436  test    rax, rax
0x18003e439  jz      short loc_18003E460
0x18003e43b  mov     [rsp+0F0h+var_C8], r15
0x18003e440  mov     [rsp+0F0h+ppv], r14
0x18003e445  mov     r9d, esi
0x18003e448  mov     r8, cs:off_1800C8FA0; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e44f  mov     edx, 0B0000h
0x18003e454  mov     rcx, cs:off_1800C8388; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18003e45b  call    _bidTraceW
0x18003e460  test    byte ptr cs:_bidGblFlags, 4
0x18003e467  jz      short loc_18003E490
0x18003e469  cmp     [rbp+4Fh+var_B0], r12
0x18003e46d  jz      short loc_18003E490
0x18003e46f  mov     rcx, cs:_bidID
0x18003e476  cmp     rcx, r12
0x18003e479  jz      short loc_18003E490
0x18003e47b  lea     r9, [rbp+4Fh+var_B0]
0x18003e47f  xor     r8d, r8d
0x18003e482  xor     edx, edx
0x18003e484  mov     rax, cs:off_1800BC0E8
0x18003e48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e490  mov     edx, esi
0x18003e492  jmp     loc_18003E7EE
0x18003e497  mov     [r15], rsi
0x18003e49a  mov     [r14], esi
0x18003e49d  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x18003e4a1  mov     rcx, rbx; lpsz
0x18003e4a4  call    cs:__imp_CLSIDFromString
0x18003e4aa  test    eax, eax
0x18003e4ac  jns     short loc_18003E502
0x18003e4ae  mov     edi, 800401E4h
0x18003e4b3  mov     bl, 2
0x18003e4b5  test    byte ptr cs:_bidGblFlags, bl
0x18003e4bb  jz      loc_18003E7BC
0x18003e4c1  mov     r8d, 2CBh; unsigned int
0x18003e4c7  lea     rdx, aCrootenumerato; "<CRootEnumerator::ParseDisplayName|OLED"...
0x18003e4ce  mov     ecx, edi; int
0x18003e4d0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003e4d5  test    byte ptr cs:_bidGblFlags, bl
0x18003e4db  jz      loc_18003E7BC
0x18003e4e1  mov     rax, cs:off_1800C8F98; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e4e8  test    rax, rax
0x18003e4eb  jz      loc_18003E7BC
0x18003e4f1  mov     r8, cs:off_1800C8F98; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e4f8  mov     edx, 0B3000h
0x18003e4fd  jmp     loc_18003E7A3
0x18003e502  mov     edx, 7Dh ; '}'; Ch
0x18003e507  mov     rcx, rbx; Str
0x18003e50a  call    cs:__imp_wcschr
0x18003e510  sub     rax, rbx
0x18003e513  sar     rax, 1
0x18003e516  inc     eax
0x18003e518  mov     [r14], eax
0x18003e51b  mov     [rbp+4Fh+punk], rsi
0x18003e51f  mov     r12d, 15h
0x18003e525  mov     bl, 2
0x18003e527  test    rdi, rdi
0x18003e52a  jz      loc_18003E6EB
0x18003e530  xorps   xmm0, xmm0
0x18003e533  xor     eax, eax
0x18003e535  movups  [rbp+4Fh+var_80], xmm0
0x18003e539  movups  [rbp+4Fh+var_70], xmm0
0x18003e53d  mov     [rbp+4Fh+var_60], rax
0x18003e541  mov     dword ptr [rbp+4Fh+var_80], 28h ; '('
0x18003e548  mov     rax, [rdi]
0x18003e54b  lea     rdx, [rbp+4Fh+var_80]
0x18003e54f  mov     rcx, rdi
0x18003e552  mov     rax, [rax+38h]
0x18003e556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e55b  mov     edi, eax
0x18003e55d  test    eax, eax
0x18003e55f  js      short loc_18003E56B
0x18003e561  mov     r12d, dword ptr [rbp+4Fh+var_70+4]
0x18003e565  mov     rsi, [rbp+4Fh+var_60]
0x18003e569  jmp     short loc_18003E587
0x18003e56b  test    byte ptr cs:_bidGblFlags, bl
0x18003e571  jz      short loc_18003E587
0x18003e573  mov     r8d, 2EEh; unsigned int
0x18003e579  lea     rdx, aCrootenumerato; "<CRootEnumerator::ParseDisplayName|OLED"...
0x18003e580  mov     ecx, edi; int
0x18003e582  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003e587  lea     rcx, ModuleName; "OLE32.DLL"
0x18003e58e  call    cs:__imp_GetModuleHandleW
0x18003e594  lea     rdx, aCocreateinstan_0; "CoCreateInstanceEx"
0x18003e59b  mov     rcx, rax; hModule
0x18003e59e  call    cs:__imp_GetProcAddress
0x18003e5a4  test    rax, rax
0x18003e5a7  jz      loc_18003E6E3
0x18003e5ad  lea     r13, IID_IUnknown
0x18003e5b4  mov     [rbp+4Fh+var_98], r13
0x18003e5b8  mov     [rbp+4Fh+var_90], 0
0x18003e5c0  mov     [rbp+4Fh+var_88], 0
0x18003e5c7  lea     rcx, [rbp+4Fh+var_98]
0x18003e5cb  mov     [rsp+0F0h+var_C8], rcx
0x18003e5d0  mov     dword ptr [rsp+0F0h+ppv], 1
0x18003e5d8  mov     r9, rsi
0x18003e5db  mov     r8d, r12d
0x18003e5de  xor     edx, edx
0x18003e5e0  lea     rcx, [rbp+4Fh+pclsid]
0x18003e5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5e9  mov     edi, eax
0x18003e5eb  test    eax, eax
0x18003e5ed  js      loc_18003E6BE
0x18003e5f3  mov     rdx, [rbp+4Fh+var_90]; struct IUnknown *
0x18003e5f7  test    rdx, rdx
0x18003e5fa  jz      loc_18003E6BE
0x18003e600  lea     rcx, [rbp+4Fh+punk]; struct IUnknown **
0x18003e604  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003e609  mov     rcx, [rbp+4Fh+var_90]
0x18003e60d  mov     rax, [rcx]
0x18003e610  mov     rax, [rax+10h]
0x18003e614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e619  mov     rdx, r15; ppmk
0x18003e61c  mov     rcx, [rbp+4Fh+punk]; punk
0x18003e620  call    cs:__imp_CreatePointerMoniker
0x18003e626  mov     edi, eax
0x18003e628  test    edi, edi
0x18003e62a  jns     short loc_18003E642
0x18003e62c  mov     rcx, [rbp+4Fh+var_A0]
0x18003e630  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18003e634  lea     r8, IID_IParseDisplayName; struct _GUID *
0x18003e63b  mov     edx, edi; int
0x18003e63d  call    ?PostHResult@CRootEnumerator@@AEAAJJAEBU_GUID@@@Z; CRootEnumerator::PostHResult(long,_GUID const &)
0x18003e642  test    byte ptr cs:_bidGblFlags, bl
0x18003e648  jz      short loc_18003E67B
0x18003e64a  mov     rax, cs:off_1800C8F90; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e651  test    rax, rax
0x18003e654  jz      short loc_18003E67B
0x18003e656  mov     [rsp+0F0h+var_C8], r15
0x18003e65b  mov     [rsp+0F0h+ppv], r14
0x18003e660  mov     r9d, edi
0x18003e663  mov     r8, cs:off_1800C8F90; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e66a  mov     edx, 0CCC00h
0x18003e66f  mov     rcx, cs:off_1800C8388; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18003e676  call    _bidTraceW
0x18003e67b  test    byte ptr cs:_bidGblFlags, 4
0x18003e682  jz      short loc_18003E6AE
0x18003e684  cmp     [rbp+4Fh+var_B0], 0FFFFFFFFFFFFFFFFh
0x18003e689  jz      short loc_18003E6AE
0x18003e68b  mov     rcx, cs:_bidID
0x18003e692  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003e696  jz      short loc_18003E6AE
0x18003e698  lea     r9, [rbp+4Fh+var_B0]
0x18003e69c  xor     r8d, r8d
0x18003e69f  xor     edx, edx
0x18003e6a1  mov     rax, cs:off_1800BC0E8
0x18003e6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6ad  nop
0x18003e6ae  lea     rcx, [rbp+4Fh+punk]
0x18003e6b2  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18003e6b7  mov     eax, edi
0x18003e6b9  jmp     loc_18003E7FE
0x18003e6be  test    byte ptr cs:_bidGblFlags, bl
0x18003e6c4  jz      loc_18003E628
0x18003e6ca  mov     r8d, 308h; unsigned int
0x18003e6d0  mov     ecx, eax; int
0x18003e6d2  lea     rdx, aCrootenumerato; "<CRootEnumerator::ParseDisplayName|OLED"...
0x18003e6d9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003e6de  jmp     loc_18003E628
0x18003e6e3  test    edi, edi
0x18003e6e5  js      loc_18003E619
0x18003e6eb  lea     rax, [rbp+4Fh+punk]
0x18003e6ef  mov     [rsp+0F0h+ppv], rax; ppv
0x18003e6f4  lea     r13, IID_IUnknown
0x18003e6fb  mov     r9, r13; riid
0x18003e6fe  mov     r8d, r12d; dwClsContext
0x18003e701  xor     edx, edx; pUnkOuter
0x18003e703  lea     rcx, [rbp+4Fh+pclsid]; rclsid
0x18003e707  call    cs:__imp_CoCreateInstance
0x18003e70d  mov     edi, eax
0x18003e70f  mov     esi, 80070057h
0x18003e714  cmp     eax, esi
0x18003e716  jnz     short loc_18003E73F
0x18003e718  test    r12b, 10h
0x18003e71c  jz      short loc_18003E747
0x18003e71e  and     r12d, 0FFFFFFEFh
0x18003e722  lea     rax, [rbp+4Fh+punk]
0x18003e726  mov     [rsp+0F0h+ppv], rax; ppv
0x18003e72b  mov     r9, r13; riid
0x18003e72e  mov     r8d, r12d; dwClsContext
0x18003e731  xor     edx, edx; pUnkOuter
0x18003e733  lea     rcx, [rbp+4Fh+pclsid]; rclsid
0x18003e737  call    cs:__imp_CoCreateInstance
0x18003e73d  mov     edi, eax
0x18003e73f  test    edi, edi
0x18003e741  jns     loc_18003E619
0x18003e747  test    byte ptr cs:_bidGblFlags, bl
0x18003e74d  jz      loc_18003E62C
0x18003e753  mov     r8d, 321h
0x18003e759  mov     ecx, edi
0x18003e75b  jmp     loc_18003E6D2
0x18003e760  mov     edi, 800401E5h
0x18003e765  mov     bl, 2
0x18003e767  test    byte ptr cs:_bidGblFlags, bl
0x18003e76d  jz      short loc_18003E7BC
0x18003e76f  mov     r8d, 2B8h; unsigned int
0x18003e775  lea     rdx, aCrootenumerato; "<CRootEnumerator::ParseDisplayName|OLED"...
0x18003e77c  mov     ecx, edi; int
0x18003e77e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003e783  test    byte ptr cs:_bidGblFlags, bl
0x18003e789  jz      short loc_18003E7BC
0x18003e78b  mov     rax, cs:off_1800C8FA8; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e792  test    rax, rax
0x18003e795  jz      short loc_18003E7BC
0x18003e797  mov     r8, cs:off_1800C8FA8; "<IParseDisplayName::ParseDisplayName|AP"...
0x18003e79e  mov     edx, 0AE400h
0x18003e7a3  mov     [rsp+0F0h+var_C8], r15
0x18003e7a8  mov     [rsp+0F0h+ppv], r14
0x18003e7ad  mov     r9d, edi
0x18003e7b0  mov     rcx, cs:off_1800C8388; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18003e7b7  call    _bidTraceW
0x18003e7bc  test    byte ptr cs:_bidGblFlags, 4
0x18003e7c3  jz      short loc_18003E7EC
0x18003e7c5  cmp     [rbp+4Fh+var_B0], r12
0x18003e7c9  jz      short loc_18003E7EC
0x18003e7cb  mov     rcx, cs:_bidID
0x18003e7d2  cmp     rcx, r12
0x18003e7d5  jz      short loc_18003E7EC
0x18003e7d7  lea     r9, [rbp+4Fh+var_B0]
0x18003e7db  xor     r8d, r8d
0x18003e7de  xor     edx, edx
0x18003e7e0  mov     rax, cs:off_1800BC0E8
0x18003e7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7ec  mov     edx, edi; int
0x18003e7ee  lea     r8, IID_IParseDisplayName; struct _GUID *
0x18003e7f5  lea     rcx, [r13-8]; this
0x18003e7f9  call    ?PostHResult@CRootEnumerator@@AEAAJJAEBU_GUID@@@Z; CRootEnumerator::PostHResult(long,_GUID const &)
0x18003e7fe  mov     rcx, [rbp+4Fh+var_48]
0x18003e802  xor     rcx, rsp; StackCookie
0x18003e805  call    __security_check_cookie
0x18003e80a  add     rsp, 0B8h
0x18003e811  pop     r15
0x18003e813  pop     r14
0x18003e815  pop     r13
0x18003e817  pop     r12
0x18003e819  pop     rdi
0x18003e81a  pop     rsi
0x18003e81b  pop     rbx
0x18003e81c  pop     rbp
0x18003e81d  retn
```
