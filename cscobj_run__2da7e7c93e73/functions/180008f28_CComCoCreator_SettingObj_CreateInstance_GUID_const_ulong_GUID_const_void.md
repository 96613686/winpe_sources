# CComCoCreator_SettingObj::CreateInstance(_GUID const &,ulong,_GUID const &,void * *)

- ea: `0x180008f28`
- end: `0x180009015`
- name: `?CreateInstance@CComCoCreator_SettingObj@@SAJAEBU_GUID@@K0PEAPEAX@Z`
- size: `237`
- prototype: `static int(const struct _GUID *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008e54`

## callees

- `0x180005410`
- `0x180008f28`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180008fc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180008fc2`

## pseudocode

```c
__int64 __fastcall CComCoCreator_SettingObj::CreateInstance(
        const struct _GUID *a1,
        DWORD a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // edx
  HRESULT v6; // edi
  unsigned int v7; // r8d
  int v8; // r9d
  IUnknown *pItf; // rbx
  MULTI_QI pResults; // [rsp+30h] [rbp-29h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-11h] BYREF
  _DWORD v13[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+70h] [rbp+17h]
  int v15; // [rsp+78h] [rbp+1Fh]
  int v16; // [rsp+7Ch] [rbp+23h]
  __int64 v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  v14 = 0;
  v13[0] = -1;
  v13[1] = -1;
  v15 = 6;
  pServerInfo.pAuthInfo = (COAUTHINFO *)v13;
  v16 = 3;
  v17 = 0;
  v18 = 64;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pwszName = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 0;
  pResults.pIID = &GUID_d871d3f7_f613_48a1_827e_7a34e560fff6;
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v6 = CoCreateInstanceEx(a1, 0, a2, &pServerInfo, 1u, &pResults);
  if ( v6 >= 0 )
  {
    pItf = pResults.pItf;
    v6 = CscCom_SetClientProxyBlanket(pResults.pItf, v5, v7, v8);
    if ( v6 >= 0 )
      v6 = ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))pItf->lpVtbl->QueryInterface)(
             pItf,
             &GUID_d871d3f7_f613_48a1_827e_7a34e560fff6,
             a4);
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008f28  push    rbp
0x180008f2a  push    rbx
0x180008f2b  push    rsi
0x180008f2c  push    rdi
0x180008f2d  push    r15
0x180008f2f  lea     rbp, [rsp-37h]
0x180008f34  sub     rsp, 90h
0x180008f3b  or      eax, 0FFFFFFFFh
0x180008f3e  mov     [rbp+57h+var_40], 0
0x180008f46  mov     [rbp+57h+var_48], eax
0x180008f49  lea     r15, _GUID_d871d3f7_f613_48a1_827e_7a34e560fff6
0x180008f50  mov     [rbp+57h+var_44], eax
0x180008f53  mov     rsi, r9
0x180008f56  lea     rax, [rbp+57h+var_48]
0x180008f5a  mov     [rbp+57h+var_38], 6
0x180008f61  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180008f65  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180008f69  lea     rax, [rbp+57h+var_80]
0x180008f6d  mov     [rbp+57h+var_34], 3
0x180008f74  mov     r8d, edx; dwClsCtx
0x180008f77  mov     [rsp+0B0h+pResults], rax; pResults
0x180008f7c  xor     edx, edx; punkOuter
0x180008f7e  mov     [rsp+0B0h+dwCount], 1; dwCount
0x180008f86  mov     [rbp+57h+var_30], 0
0x180008f8e  mov     [rbp+57h+var_28], 40h ; '@'
0x180008f96  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], 0
0x180008f9e  mov     [rbp+57h+pServerInfo.pwszName], 0
0x180008fa6  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], 0
0x180008fae  mov     [rbp+57h+var_80.pIID], r15
0x180008fb2  mov     [rbp+57h+var_80.pItf], 0
0x180008fba  mov     qword ptr [rbp+57h+var_80.hr], 0
0x180008fc2  call    cs:__imp_CoCreateInstanceEx
0x180008fc8  mov     edi, eax
0x180008fca  test    eax, eax
0x180008fcc  js      short loc_180009005
0x180008fce  mov     rbx, [rbp+57h+var_80.pItf]
0x180008fd2  mov     rcx, rbx; pProxy
0x180008fd5  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x180008fda  mov     edi, eax
0x180008fdc  test    eax, eax
0x180008fde  js      short loc_180008FF6
0x180008fe0  mov     rax, [rbx]
0x180008fe3  mov     r8, rsi
0x180008fe6  mov     rdx, r15
0x180008fe9  mov     rcx, rbx
0x180008fec  mov     rax, [rax]
0x180008fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff4  mov     edi, eax
0x180008ff6  mov     rax, [rbx]
0x180008ff9  mov     rcx, rbx
0x180008ffc  mov     rax, [rax+10h]
0x180009000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009005  mov     eax, edi
0x180009007  add     rsp, 90h
0x18000900e  pop     r15
0x180009010  pop     rdi
0x180009011  pop     rsi
0x180009012  pop     rbx
0x180009013  pop     rbp
0x180009014  retn
```
