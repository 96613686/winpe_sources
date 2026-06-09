# ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)

- ea: `0x1800321d0`
- end: `0x180032384`
- name: `?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const struct _GUID *, int, HINSTANCE hInstance)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005989c`
- `0x1800598d4`

## callees

- `0x180026940`
- `0x1800301ac`
- `0x1800321d0`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!lstrcpyW` at `0x18003224e`
- `KERNEL32!lstrcpyW` at `0x18003224e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003232b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003232b`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180032281`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180032281`
- `USER32!LoadStringW` at `0x180032238`
- `USER32!LoadStringW` at `0x180032238`
- `ole32!ProgIDFromCLSID` at `0x1800322c1`
- `ole32!ProgIDFromCLSID` at `0x1800322c1`
- `ole32!CoTaskMemFree` at `0x1800322ea`
- `ole32!CoTaskMemFree` at `0x1800322ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::AtlSetErrorInfo(
        const struct _GUID *a1,
        WCHAR *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        unsigned int a6,
        HINSTANCE hInstance)
{
  WCHAR *v7; // rdi
  int v8; // esi
  unsigned int v9; // ebx
  LPOLESTR v10; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpszProgID; // [rsp+28h] [rbp-D8h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = a2;
  v15 = 0;
  Buffer[0] = 0;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v9 = a6;
  }
  else
  {
    v8 = (unsigned __int16)a2;
    if ( !LoadStringW(hInstance, (unsigned __int16)a2, Buffer, 1024) )
      lstrcpyW(Buffer, L"Unknown Error");
    v7 = Buffer;
    v9 = a6;
    if ( !a6 )
      v9 = v8 | 0x80040000;
  }
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    perrinfo = 0;
    ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a5);
    lpszProgID = 0;
    ProgIDFromCLSID(&CLSID_DataLinks, &lpszProgID);
    v10 = lpszProgID;
    if ( lpszProgID )
    {
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->SetSource)(pperrinfo);
      v10 = lpszProgID;
    }
    CoTaskMemFree(v10);
    ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v7);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
      SetErrorInfo(0, perrinfo);
    ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&perrinfo);
  }
  if ( !v9 )
    v9 = -2147352567;
  ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&pperrinfo);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v15);
  return v9;
}

```

## disassembly

```asm
0x1800321d0  mov     [rsp-8+arg_0], rbx
0x1800321d5  mov     [rsp-8+arg_10], rsi
0x1800321da  push    rbp
0x1800321db  push    rdi
0x1800321dc  push    r14
0x1800321de  lea     rbp, [rsp-750h]
0x1800321e6  sub     rsp, 850h
0x1800321ed  mov     rax, cs:__security_cookie
0x1800321f4  xor     rax, rsp
0x1800321f7  mov     [rbp+760h+var_20], rax
0x1800321fe  mov     rdi, rdx
0x180032201  mov     r14, [rbp+760h+arg_20]
0x180032208  mov     rcx, [rbp+760h+hInstance]; hInstance
0x18003220f  mov     [rsp+860h+var_828], 0
0x180032218  xor     eax, eax
0x18003221a  mov     [rsp+860h+Buffer], ax
0x18003221f  cmp     rdx, 10000h
0x180032226  jnb     short loc_18003226D
0x180032228  movzx   esi, dx
0x18003222b  mov     r9d, 400h; cchBufferMax
0x180032231  lea     r8, [rsp+860h+Buffer]; lpBuffer
0x180032236  mov     edx, esi; uID
0x180032238  call    cs:__imp_LoadStringW
0x18003223e  test    eax, eax
0x180032240  jnz     short loc_180032254
0x180032242  lea     rdx, String2; "Unknown Error"
0x180032249  lea     rcx, [rsp+860h+Buffer]; lpString1
0x18003224e  call    cs:__imp_lstrcpyW
0x180032254  lea     rdi, [rsp+860h+Buffer]
0x180032259  mov     ebx, [rbp+760h+arg_28]
0x18003225f  test    ebx, ebx
0x180032261  jnz     short loc_180032273
0x180032263  mov     ebx, esi
0x180032265  or      ebx, 80040000h
0x18003226b  jmp     short loc_180032273
0x18003226d  mov     ebx, [rbp+760h+arg_28]
0x180032273  mov     [rsp+860h+pperrinfo], 0
0x18003227c  lea     rcx, [rsp+860h+pperrinfo]; pperrinfo
0x180032281  call    cs:__imp_CreateErrorInfo
0x180032287  test    eax, eax
0x180032289  js      loc_18003233C
0x18003228f  mov     [rsp+860h+perrinfo], 0
0x180032298  mov     rcx, [rsp+860h+pperrinfo]
0x18003229d  mov     rax, [rcx]
0x1800322a0  mov     rdx, r14
0x1800322a3  mov     rax, [rax+18h]
0x1800322a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322ac  mov     [rsp+860h+lpszProgID], 0
0x1800322b5  lea     rdx, [rsp+860h+lpszProgID]; lplpszProgID
0x1800322ba  lea     rcx, CLSID_DataLinks; clsid
0x1800322c1  call    cs:__imp_ProgIDFromCLSID
0x1800322c7  mov     rdx, [rsp+860h+lpszProgID]
0x1800322cc  test    rdx, rdx
0x1800322cf  jz      short loc_1800322E7
0x1800322d1  mov     rcx, [rsp+860h+pperrinfo]
0x1800322d6  mov     rax, [rcx]
0x1800322d9  mov     rax, [rax+20h]
0x1800322dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322e2  mov     rdx, [rsp+860h+lpszProgID]
0x1800322e7  mov     rcx, rdx; pv
0x1800322ea  call    cs:__imp_CoTaskMemFree
0x1800322f0  mov     rcx, [rsp+860h+pperrinfo]
0x1800322f5  mov     rax, [rcx]
0x1800322f8  mov     rdx, rdi
0x1800322fb  mov     rax, [rax+28h]
0x1800322ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032304  mov     rcx, [rsp+860h+pperrinfo]
0x180032309  mov     rax, [rcx]
0x18003230c  lea     r8, [rsp+860h+perrinfo]
0x180032311  lea     rdx, IID_IErrorInfo
0x180032318  mov     rax, [rax]
0x18003231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032320  test    eax, eax
0x180032322  js      short loc_180032332
0x180032324  mov     rdx, [rsp+860h+perrinfo]; perrinfo
0x180032329  xor     ecx, ecx; dwReserved
0x18003232b  call    cs:__imp_SetErrorInfo
0x180032331  nop
0x180032332  lea     rcx, [rsp+860h+perrinfo]
0x180032337  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18003233c  mov     eax, 80020009h
0x180032341  test    ebx, ebx
0x180032343  cmovz   ebx, eax
0x180032346  lea     rcx, [rsp+860h+pperrinfo]
0x18003234b  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x180032350  nop
0x180032351  lea     rcx, [rsp+860h+var_828]
0x180032356  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18003235b  mov     eax, ebx
0x18003235d  mov     rcx, [rbp+760h+var_20]
0x180032364  xor     rcx, rsp; StackCookie
0x180032367  call    __security_check_cookie
0x18003236c  lea     r11, [rsp+860h+var_10]
0x180032374  mov     rbx, [r11+20h]
0x180032378  mov     rsi, [r11+30h]
0x18003237c  mov     rsp, r11
0x18003237f  pop     r14
0x180032381  pop     rdi
0x180032382  pop     rbp
0x180032383  retn
```
