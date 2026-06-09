# CContext::PushErrorNoTls(_GUID *,bool)

- ea: `0x1800cb624`
- end: `0x1800cb6f3`
- name: `?PushErrorNoTls@CContext@@QEAAXPEAU_GUID@@_N@Z`
- size: `207`
- prototype: `void __fastcall(CContext *__hidden this, struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9788`

## callees

- `0x180001514`
- `0x180021c50`
- `0x180053c18`
- `0x1800cb624`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800cb664`
- `ole32!CoCreateInstance` at `0x1800cb664`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800cb682`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800cb682`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CContext::PushErrorNoTls(CContext *this, struct _GUID *a2)
{
  struct _GUID *v4; // r8
  int *ppv; // [rsp+20h] [rbp-38h]
  ICreateErrorInfo *pperrinfo[3]; // [rsp+40h] [rbp-18h] BYREF
  struct IErrorInfo *v7; // [rsp+78h] [rbp+20h] BYREF

  v7 = 0;
  if ( !CContext::ADOErrorLookupExists(this)
    || CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&v7) < 0 )
  {
    pperrinfo[0] = 0;
    if ( CreateErrorInfo(pperrinfo) >= 0 )
      ((void (__fastcall *)(ICreateErrorInfo *, GUID *, struct IErrorInfo **))pperrinfo[0]->lpVtbl->QueryInterface)(
        pperrinfo[0],
        &IID_IErrorInfo,
        &v7);
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(pperrinfo);
  }
  if ( v7 )
    CContext::AddErrorRecord(this, v7, v4, a2, ppv, 0, 0);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v7);
}

```

## disassembly

```asm
0x1800cb624  mov     [rsp+arg_0], rbx
0x1800cb629  push    rdi
0x1800cb62a  sub     rsp, 50h
0x1800cb62e  mov     rbx, rdx
0x1800cb631  mov     rdi, rcx
0x1800cb634  mov     [rsp+58h+arg_18], 0
0x1800cb63d  call    ?ADOErrorLookupExists@CContext@@QEAA_NXZ; CContext::ADOErrorLookupExists(void)
0x1800cb642  test    al, al
0x1800cb644  jz      short loc_1800CB674
0x1800cb646  lea     rax, [rsp+58h+arg_18]
0x1800cb64b  mov     [rsp+58h+ppv], rax; int *
0x1800cb650  lea     r9, IID_IErrorInfo; riid
0x1800cb657  xor     edx, edx; pUnkOuter
0x1800cb659  lea     r8d, [rdx+1]; dwClsContext
0x1800cb65d  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x1800cb664  call    cs:__imp_CoCreateInstance
0x1800cb66b  nop     dword ptr [rax+rax+00h]
0x1800cb670  test    eax, eax
0x1800cb672  jns     short loc_1800CB6B9
0x1800cb674  mov     [rsp+58h+pperrinfo], 0
0x1800cb67d  lea     rcx, [rsp+58h+pperrinfo]; pperrinfo
0x1800cb682  call    cs:__imp_CreateErrorInfo
0x1800cb689  nop     dword ptr [rax+rax+00h]
0x1800cb68e  test    eax, eax
0x1800cb690  js      short loc_1800CB6AF
0x1800cb692  mov     rcx, [rsp+58h+pperrinfo]
0x1800cb697  mov     rax, [rcx]
0x1800cb69a  lea     r8, [rsp+58h+arg_18]
0x1800cb69f  lea     rdx, IID_IErrorInfo
0x1800cb6a6  mov     rax, [rax]
0x1800cb6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb6ae  nop
0x1800cb6af  lea     rcx, [rsp+58h+pperrinfo]
0x1800cb6b4  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800cb6b9  mov     rdx, [rsp+58h+arg_18]; struct IErrorInfo *
0x1800cb6be  test    rdx, rdx
0x1800cb6c1  jz      short loc_1800CB6DD
0x1800cb6c3  mov     [rsp+58h+var_28], 0; bool
0x1800cb6c8  mov     [rsp+58h+var_30], 0; struct tagDISPPARAMS *
0x1800cb6d1  mov     r9, rbx; struct _GUID *
0x1800cb6d4  mov     rcx, rdi; this
0x1800cb6d7  call    ?AddErrorRecord@CContext@@QEAAJPEAUIErrorInfo@@PEAU_GUID@@1PEAJPEAUtagDISPPARAMS@@_N@Z; CContext::AddErrorRecord(IErrorInfo *,_GUID *,_GUID *,long *,tagDISPPARAMS *,bool)
0x1800cb6dc  nop
0x1800cb6dd  lea     rcx, [rsp+58h+arg_18]
0x1800cb6e2  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800cb6e7  mov     rbx, [rsp+58h+arg_0]
0x1800cb6ec  add     rsp, 50h
0x1800cb6f0  pop     rdi
0x1800cb6f1  retn
```
