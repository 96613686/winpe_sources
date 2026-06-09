# MMCReportError(mmcerror::SC &,_GUID const &,_GUID const &)

- ea: `0x140029644`
- end: `0x14002987d`
- name: `?MMCReportError@@YAJAEAVSC@mmcerror@@AEBU_GUID@@1@Z`
- size: `569`
- prototype: `int(struct mmcerror::SC *, const struct _GUID *, const struct _GUID *)`
- caller_count: `13`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400294d0`
- `0x14004ed2c`
- `0x14004f8e8`
- `0x140050528`
- `0x14005a44c`
- `0x140068348`
- `0x1400784cc`
- `0x140078500`
- `0x140078534`
- `0x140083ad4`
- `0x14009ef0c`
- `0x14009ef40`
- `0x1400b6860`

## callees

- `0x140029644`
- `0x14003ce40`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400296f6`
- `USER32!LoadStringW` at `0x1400296f6`
- `msvcrt!wcscpy_s` at `0x140029710`
- `msvcrt!wcscpy_s` at `0x140029710`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14002967d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14002967d`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400296a1`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400296a1`
- `mmcbase!?GetErrorMessage@SC@mmcerror@@QEBAXIPEAG@Z` at `0x140029698`
- `mmcbase!?GetErrorMessage@SC@mmcerror@@QEBAXIPEAG@Z` at `0x140029698`
- `mmcbase!?GetHelpID@SC@mmcerror@@QEAAKXZ` at `0x1400296b5`
- `mmcbase!?GetHelpID@SC@mmcerror@@QEAAKXZ` at `0x1400296b5`
- `mmcbase!?GetHelpFile@SC@mmcerror@@SAPEBGXZ` at `0x1400296a9`
- `mmcbase!?GetHelpFile@SC@mmcerror@@SAPEBGXZ` at `0x1400296a9`
- `ole32!CoTaskMemFree` at `0x1400297da`
- `ole32!CoTaskMemFree` at `0x1400297da`
- `ole32!ProgIDFromCLSID` at `0x14002977a`
- `ole32!ProgIDFromCLSID` at `0x14002977a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14002981b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14002981b`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14002973e`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x14002973e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MMCReportError(struct mmcerror::SC *a1, const struct _GUID *a2, const struct _GUID *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 HelpFile; // r14
  unsigned int HelpID; // r15d
  WCHAR *v13; // rsi
  LPOLESTR v14; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpszProgID; // [rsp+28h] [rbp-D8h] BYREF
  IErrorInfo *perrinfo[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v19[256]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[1024]; // [rsp+240h] [rbp+140h] BYREF

  if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
    return 0;
  mmcerror::SC::GetErrorMessage(a1, 0x100u, v19);
  v6 = mmcerror::SC::ToHr(a1);
  HelpFile = mmcerror::SC::GetHelpFile(v8, v7, v9, v10);
  HelpID = mmcerror::SC::GetHelpID(a1);
  perrinfo[1] = 0;
  Buffer[0] = 0;
  if ( (unsigned __int64)v19 >= 0x10000 )
  {
    v13 = v19;
  }
  else
  {
    if ( !LoadStringW(0, (unsigned __int16)v19, Buffer, 1024) )
      wcscpy_s(Buffer, 0x400u, L"Unknown Error");
    v13 = Buffer;
    if ( !v6 )
      v6 = (unsigned __int16)v19 | 0x80040000;
  }
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    perrinfo[0] = 0;
    ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a2);
    lpszProgID = 0;
    ProgIDFromCLSID(a3, &lpszProgID);
    v14 = lpszProgID;
    if ( lpszProgID )
    {
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->SetSource)(pperrinfo);
      v14 = lpszProgID;
    }
    if ( HelpID && HelpFile )
    {
      ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, HelpID);
      ((void (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, HelpFile);
      v14 = lpszProgID;
    }
    CoTaskMemFree(v14);
    ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v13);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           perrinfo) >= 0 )
      SetErrorInfo(0, perrinfo[0]);
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(perrinfo);
  }
  if ( !v6 )
    v6 = -2147352567;
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  return v6;
}

```

## disassembly

```asm
0x140029644  mov     [rsp-8+arg_18], rbx
0x140029649  push    rbp
0x14002964a  push    rsi
0x14002964b  push    rdi
0x14002964c  push    r12
0x14002964e  push    r13
0x140029650  push    r14
0x140029652  push    r15
0x140029654  lea     rbp, [rsp-950h]
0x14002965c  sub     rsp, 0A50h
0x140029663  mov     rax, cs:__security_cookie
0x14002966a  xor     rax, rsp
0x14002966d  mov     [rbp+980h+var_40], rax
0x140029674  mov     r13, r8
0x140029677  mov     r12, rdx
0x14002967a  mov     rdi, rcx
0x14002967d  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140029683  test    al, al
0x140029685  jz      loc_140029851
0x14002968b  lea     r8, [rsp+0A80h+var_A40]
0x140029690  mov     edx, 100h
0x140029695  mov     rcx, rdi
0x140029698  call    cs:__imp_?GetErrorMessage@SC@mmcerror@@QEBAXIPEAG@Z; mmcerror::SC::GetErrorMessage(uint,ushort *)
0x14002969e  mov     rcx, rdi
0x1400296a1  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400296a7  mov     ebx, eax
0x1400296a9  call    cs:__imp_?GetHelpFile@SC@mmcerror@@SAPEBGXZ; mmcerror::SC::GetHelpFile(void)
0x1400296af  mov     r14, rax
0x1400296b2  mov     rcx, rdi
0x1400296b5  call    cs:__imp_?GetHelpID@SC@mmcerror@@QEAAKXZ; mmcerror::SC::GetHelpID(void)
0x1400296bb  mov     r15d, eax
0x1400296be  mov     [rsp+0A80h+var_A48], 0
0x1400296c7  xor     ecx, ecx; hInstance
0x1400296c9  mov     [rbp+980h+Buffer], cx
0x1400296d0  lea     rax, [rsp+0A80h+var_A40]
0x1400296d5  cmp     rax, 10000h
0x1400296db  jnb     short loc_14002972B
0x1400296dd  lea     rax, [rsp+0A80h+var_A40]
0x1400296e2  movzx   edi, ax
0x1400296e5  mov     esi, 400h
0x1400296ea  mov     r9d, esi; cchBufferMax
0x1400296ed  lea     r8, [rbp+980h+Buffer]; lpBuffer
0x1400296f4  mov     edx, edi; uID
0x1400296f6  call    cs:__imp_LoadStringW
0x1400296fc  test    eax, eax
0x1400296fe  jnz     short loc_140029716
0x140029700  lea     r8, aUnknownError_0; "Unknown Error"
0x140029707  mov     edx, esi; SizeInWords
0x140029709  lea     rcx, [rbp+980h+Buffer]; Destination
0x140029710  call    cs:__imp_wcscpy_s
0x140029716  lea     rsi, [rbp+980h+Buffer]
0x14002971d  test    ebx, ebx
0x14002971f  jnz     short loc_140029730
0x140029721  mov     ebx, edi
0x140029723  or      ebx, 80040000h
0x140029729  jmp     short loc_140029730
0x14002972b  lea     rsi, [rsp+0A80h+var_A40]
0x140029730  mov     [rsp+0A80h+pperrinfo], 0
0x140029739  lea     rcx, [rsp+0A80h+pperrinfo]; pperrinfo
0x14002973e  call    cs:__imp_CreateErrorInfo
0x140029744  test    eax, eax
0x140029746  js      loc_14002982C
0x14002974c  mov     [rsp+0A80h+perrinfo], 0
0x140029755  mov     rcx, [rsp+0A80h+pperrinfo]
0x14002975a  mov     rax, [rcx]
0x14002975d  mov     rdx, r12
0x140029760  mov     rax, [rax+18h]
0x140029764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029769  mov     [rsp+0A80h+lpszProgID], 0
0x140029772  lea     rdx, [rsp+0A80h+lpszProgID]; lplpszProgID
0x140029777  mov     rcx, r13; clsid
0x14002977a  call    cs:__imp_ProgIDFromCLSID
0x140029780  mov     rdx, [rsp+0A80h+lpszProgID]
0x140029785  test    rdx, rdx
0x140029788  jz      short loc_1400297A0
0x14002978a  mov     rcx, [rsp+0A80h+pperrinfo]
0x14002978f  mov     rax, [rcx]
0x140029792  mov     rax, [rax+20h]
0x140029796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002979b  mov     rdx, [rsp+0A80h+lpszProgID]
0x1400297a0  test    r15d, r15d
0x1400297a3  jz      short loc_1400297D7
0x1400297a5  test    r14, r14
0x1400297a8  jz      short loc_1400297D7
0x1400297aa  mov     rcx, [rsp+0A80h+pperrinfo]
0x1400297af  mov     rax, [rcx]
0x1400297b2  mov     edx, r15d
0x1400297b5  mov     rax, [rax+38h]
0x1400297b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297be  mov     rcx, [rsp+0A80h+pperrinfo]
0x1400297c3  mov     rax, [rcx]
0x1400297c6  mov     rdx, r14
0x1400297c9  mov     rax, [rax+30h]
0x1400297cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297d2  mov     rdx, [rsp+0A80h+lpszProgID]
0x1400297d7  mov     rcx, rdx; pv
0x1400297da  call    cs:__imp_CoTaskMemFree
0x1400297e0  mov     rcx, [rsp+0A80h+pperrinfo]
0x1400297e5  mov     rax, [rcx]
0x1400297e8  mov     rdx, rsi
0x1400297eb  mov     rax, [rax+28h]
0x1400297ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297f4  mov     rcx, [rsp+0A80h+pperrinfo]
0x1400297f9  mov     rax, [rcx]
0x1400297fc  lea     r8, [rsp+0A80h+perrinfo]
0x140029801  lea     rdx, IID_IErrorInfo
0x140029808  mov     rax, [rax]
0x14002980b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029810  test    eax, eax
0x140029812  js      short loc_140029822
0x140029814  mov     rdx, [rsp+0A80h+perrinfo]; perrinfo
0x140029819  xor     ecx, ecx; dwReserved
0x14002981b  call    cs:__imp_SetErrorInfo
0x140029821  nop
0x140029822  lea     rcx, [rsp+0A80h+perrinfo]
0x140029827  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14002982c  mov     eax, 80020009h
0x140029831  test    ebx, ebx
0x140029833  cmovz   ebx, eax
0x140029836  mov     rcx, [rsp+0A80h+pperrinfo]
0x14002983b  test    rcx, rcx
0x14002983e  jz      short loc_14002984D
0x140029840  mov     rdx, [rcx]
0x140029843  mov     rax, [rdx+10h]
0x140029847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002984c  nop
0x14002984d  mov     eax, ebx
0x14002984f  jmp     short loc_140029853
0x140029851  xor     eax, eax
0x140029853  mov     rcx, [rbp+980h+var_40]
0x14002985a  xor     rcx, rsp; StackCookie
0x14002985d  call    __security_check_cookie
0x140029862  mov     rbx, [rsp+0A80h+arg_18]
0x14002986a  add     rsp, 0A50h
0x140029871  pop     r15
0x140029873  pop     r14
0x140029875  pop     r13
0x140029877  pop     r12
0x140029879  pop     rdi
0x14002987a  pop     rsi
0x14002987b  pop     rbp
0x14002987c  retn
```
