# ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)

- ea: `0x18001d374`
- end: `0x18001d528`
- name: `?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z`
- size: `436`
- prototype: `__int64 __usercall@<rax>(IID *clsid@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const struct _GUID *, int, HINSTANCE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d270`

## callees

- `0x180004640`
- `0x180006b08`
- `0x180006b38`
- `0x18001d374`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001d3f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001d3f7`
- `ole32!ProgIDFromCLSID` at `0x18001d466`
- `ole32!ProgIDFromCLSID` at `0x18001d466`
- `ole32!CoTaskMemFree` at `0x18001d48f`
- `ole32!CoTaskMemFree` at `0x18001d48f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d4d0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d4d0`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d42a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d42a`
- `USER32!LoadStringW` at `0x18001d3df`
- `USER32!LoadStringW` at `0x18001d3df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::AtlSetErrorInfo(
        IID *clsid,
        WCHAR *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        unsigned int a6,
        HINSTANCE hInstance)
{
  WCHAR *v7; // rdi
  int v9; // esi
  unsigned int v10; // ebx
  LPOLESTR v11; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpszProgID; // [rsp+28h] [rbp-D8h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = a2;
  v16 = 0;
  Buffer[0] = 0;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    v10 = a6;
  }
  else
  {
    v9 = (unsigned __int16)a2;
    if ( !LoadStringW(hInstance, (unsigned __int16)a2, Buffer, 1024) )
      _o_wcscpy_s(Buffer, 1024, L"Unknown Error");
    v7 = Buffer;
    v10 = a6;
    if ( !a6 )
      v10 = v9 | 0x80040000;
  }
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    perrinfo = 0;
    ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a5);
    lpszProgID = 0;
    ProgIDFromCLSID(clsid, &lpszProgID);
    v11 = lpszProgID;
    if ( lpszProgID )
    {
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->SetSource)(pperrinfo);
      v11 = lpszProgID;
    }
    CoTaskMemFree(v11);
    ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v7);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
      SetErrorInfo(0, perrinfo);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&perrinfo);
  }
  if ( !v10 )
    v10 = -2147352567;
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&pperrinfo);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v16);
  return v10;
}

```

## disassembly

```asm
0x18001d374  mov     [rsp-8+arg_10], rbx
0x18001d379  push    rbp
0x18001d37a  push    rsi
0x18001d37b  push    rdi
0x18001d37c  push    r14
0x18001d37e  push    r15
0x18001d380  lea     rbp, [rsp-750h]
0x18001d388  sub     rsp, 850h
0x18001d38f  mov     rax, cs:__security_cookie
0x18001d396  xor     rax, rsp
0x18001d399  mov     [rbp+770h+var_30], rax
0x18001d3a0  mov     rdi, rdx
0x18001d3a3  mov     r14, rcx
0x18001d3a6  mov     r15, [rbp+770h+arg_20]
0x18001d3ad  mov     rcx, [rbp+770h+hInstance]; hInstance
0x18001d3b4  mov     [rsp+870h+var_838], 0
0x18001d3bd  xor     eax, eax
0x18001d3bf  mov     [rsp+870h+Buffer], ax
0x18001d3c4  cmp     rdx, 10000h
0x18001d3cb  jnb     short loc_18001D416
0x18001d3cd  movzx   esi, dx
0x18001d3d0  mov     ebx, 400h
0x18001d3d5  mov     r9d, ebx; cchBufferMax
0x18001d3d8  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x18001d3dd  mov     edx, esi; uID
0x18001d3df  call    cs:__imp_LoadStringW
0x18001d3e5  test    eax, eax
0x18001d3e7  jnz     short loc_18001D3FD
0x18001d3e9  lea     r8, aUnknownError; "Unknown Error"
0x18001d3f0  mov     edx, ebx
0x18001d3f2  lea     rcx, [rsp+870h+Buffer]
0x18001d3f7  call    cs:__imp__o_wcscpy_s
0x18001d3fd  lea     rdi, [rsp+870h+Buffer]
0x18001d402  mov     ebx, [rbp+770h+arg_28]
0x18001d408  test    ebx, ebx
0x18001d40a  jnz     short loc_18001D41C
0x18001d40c  mov     ebx, esi
0x18001d40e  or      ebx, 80040000h
0x18001d414  jmp     short loc_18001D41C
0x18001d416  mov     ebx, [rbp+770h+arg_28]
0x18001d41c  mov     [rsp+870h+pperrinfo], 0
0x18001d425  lea     rcx, [rsp+870h+pperrinfo]; pperrinfo
0x18001d42a  call    cs:__imp_CreateErrorInfo
0x18001d430  test    eax, eax
0x18001d432  js      loc_18001D4E1
0x18001d438  mov     [rsp+870h+perrinfo], 0
0x18001d441  mov     rcx, [rsp+870h+pperrinfo]
0x18001d446  mov     rax, [rcx]
0x18001d449  mov     rdx, r15
0x18001d44c  mov     rax, [rax+18h]
0x18001d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d455  mov     [rsp+870h+lpszProgID], 0
0x18001d45e  lea     rdx, [rsp+870h+lpszProgID]; lplpszProgID
0x18001d463  mov     rcx, r14; clsid
0x18001d466  call    cs:__imp_ProgIDFromCLSID
0x18001d46c  mov     rdx, [rsp+870h+lpszProgID]
0x18001d471  test    rdx, rdx
0x18001d474  jz      short loc_18001D48C
0x18001d476  mov     rcx, [rsp+870h+pperrinfo]
0x18001d47b  mov     rax, [rcx]
0x18001d47e  mov     rax, [rax+20h]
0x18001d482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d487  mov     rdx, [rsp+870h+lpszProgID]
0x18001d48c  mov     rcx, rdx; pv
0x18001d48f  call    cs:__imp_CoTaskMemFree
0x18001d495  mov     rcx, [rsp+870h+pperrinfo]
0x18001d49a  mov     rax, [rcx]
0x18001d49d  mov     rdx, rdi
0x18001d4a0  mov     rax, [rax+28h]
0x18001d4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a9  mov     rcx, [rsp+870h+pperrinfo]
0x18001d4ae  mov     rax, [rcx]
0x18001d4b1  lea     r8, [rsp+870h+perrinfo]
0x18001d4b6  lea     rdx, IID_IErrorInfo
0x18001d4bd  mov     rax, [rax]
0x18001d4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c5  test    eax, eax
0x18001d4c7  js      short loc_18001D4D7
0x18001d4c9  mov     rdx, [rsp+870h+perrinfo]; perrinfo
0x18001d4ce  xor     ecx, ecx; dwReserved
0x18001d4d0  call    cs:__imp_SetErrorInfo
0x18001d4d6  nop
0x18001d4d7  lea     rcx, [rsp+870h+perrinfo]
0x18001d4dc  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001d4e1  mov     eax, 80020009h
0x18001d4e6  test    ebx, ebx
0x18001d4e8  cmovz   ebx, eax
0x18001d4eb  lea     rcx, [rsp+870h+pperrinfo]
0x18001d4f0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001d4f5  nop
0x18001d4f6  lea     rcx, [rsp+870h+var_838]
0x18001d4fb  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18001d500  mov     eax, ebx
0x18001d502  mov     rcx, [rbp+770h+var_30]
0x18001d509  xor     rcx, rsp; StackCookie
0x18001d50c  call    __security_check_cookie
0x18001d511  mov     rbx, [rsp+870h+arg_10]
0x18001d519  add     rsp, 850h
0x18001d520  pop     r15
0x18001d522  pop     r14
0x18001d524  pop     rdi
0x18001d525  pop     rsi
0x18001d526  pop     rbp
0x18001d527  retn
```
