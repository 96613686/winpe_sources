# CEventClass::CreateFromTier2CheckConfig(IEventSystemTier2 *,IUnknown *,ushort const * *,int,IDispatch * *)

- ea: `0x180030980`
- end: `0x180030bd2`
- name: `?CreateFromTier2CheckConfig@CEventClass@@SAJPEAUIEventSystemTier2@@PEAUIUnknown@@PEAPEBGHPEAPEAUIDispatch@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct IEventSystemTier2 *, struct IUnknown *, const unsigned __int16 **, int, struct IDispatch **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008938`
- `0x180013e70`
- `0x1800157d4`
- `0x180015850`
- `0x180030980`
- `0x1800434ae`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030a15`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030b38`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030b38`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180030a0a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180030a0a`

## string_xrefs

- `0x180030b47`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::CreateFromTier2CheckConfig(
        struct IEventSystemTier2 *a1,
        struct IUnknown *a2,
        const unsigned __int16 **a3,
        int a4,
        struct IDispatch **a5)
{
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  int v9; // edi
  CEventClass *v10; // rax
  CEventClass *v11; // rax
  CEventClass *v12; // rbx
  __int64 (__fastcall **v13)(CEventClass *, GUID *, struct IDispatch **); // rax
  __int64 v14; // r9
  BYTE *v15; // xmm1_8
  __int128 v16; // xmm0
  BYTE *v17; // xmm1_8
  __int128 v18; // xmm0
  BYTE *v19; // xmm1_8
  int v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  IUnknown *pProxy; // [rsp+40h] [rbp-61h] BYREF
  struct IDispatch *v25; // [rsp+48h] [rbp-59h] BYREF
  struct tagPROPVARIANT v26; // [rsp+50h] [rbp-51h] BYREF
  struct tagPROPVARIANT v27; // [rsp+70h] [rbp-31h] BYREF
  struct tagPROPVARIANT pclsid; // [rsp+90h] [rbp-11h] BYREF

  lpVtbl = a2->lpVtbl;
  v25 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  pProxy = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))QueryInterface)(
         a2,
         &IID_IEventClassTier2,
         &pProxy);
  if ( v9 < 0 )
    return (unsigned int)v9;
  CoSetProxyBlanket(
    pProxy,
    0xFFFFFFFF,
    0xFFFFFFFF,
    (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
    0,
    3u,
    (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
    0x40u);
  v10 = (CEventClass *)CoTaskMemAlloc(0x2D0u);
  if ( !v10 )
  {
    v12 = 0;
    goto LABEL_9;
  }
  v11 = CEventClass::CEventClass(v10);
  v12 = v11;
  if ( !v11 )
  {
LABEL_9:
    v9 = -2147024882;
    goto LABEL_10;
  }
  v9 = ((__int64 (__fastcall *)(IUnknown *, char *))pProxy->lpVtbl[1].AddRef)(pProxy, (char *)v11 + 48);
  if ( v9 < 0 )
    goto LABEL_7;
  v13 = *(__int64 (__fastcall ***)(CEventClass *, GUID *, struct IDispatch **))v12;
  *((_DWORD *)v12 + 120) = 0;
  v9 = (*v13)(v12, &IID_IEventClass2, &v25);
  if ( v9 < 0 )
    goto LABEL_7;
  v15 = (BYTE *)*((_QWORD *)v12 + 44);
  *(_OWORD *)&pclsid.vt = *((_OWORD *)v12 + 21);
  v16 = *(_OWORD *)((char *)v12 + 312);
  pclsid.bstrblobVal.pData = v15;
  v17 = (BYTE *)*((_QWORD *)v12 + 41);
  *(_OWORD *)&v26.vt = v16;
  v18 = *((_OWORD *)v12 + 3);
  v26.bstrblobVal.pData = v17;
  v19 = (BYTE *)*((_QWORD *)v12 + 8);
  *(_OWORD *)&v27.vt = v18;
  v27.bstrblobVal.pData = v19;
  v20 = ConcatenateECID_PARTID_APPID(&v27, &v26, &pclsid, v14, (unsigned __int16 *)v12 + 242);
  *((_DWORD *)v12 + 120) = 0;
  v9 = v20;
  if ( v20 < 0 )
LABEL_7:
    CEventClass::`scalar deleting destructor'(v12);
LABEL_10:
  ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v9 >= 0 )
  {
    *(GUID *)&pclsid.vt = GUID_NULL;
    if ( *((_WORD *)v12 + 156) )
    {
      v21 = CLSIDFromString(*((LPCOLESTR *)v12 + 40), (LPCLSID)&pclsid);
      v9 = v21;
      if ( v21 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0xD0u, 0x10u, v21);
    }
    else
    {
      *(GUID *)&pclsid.vt = GUID_NULL;
    }
    v22 = memcmp_0(&GUID_NULL, &pclsid, 0x10u);
    if ( a4 )
    {
      if ( !v22 )
        v9 = -2147220979;
    }
    else if ( v22 )
    {
      return (unsigned int)-2147220978;
    }
    if ( v9 >= 0 )
    {
      *a5 = v25;
      if ( a3 )
        *a3 = (const unsigned __int16 *)((char *)v12 + 484);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180030980  mov     [rsp-8+arg_0], rbx
0x180030985  push    rbp
0x180030986  push    rsi
0x180030987  push    rdi
0x180030988  push    r12
0x18003098a  push    r13
0x18003098c  push    r14
0x18003098e  push    r15
0x180030990  lea     rbp, [rsp-1Fh]
0x180030995  sub     rsp, 0C0h
0x18003099c  mov     rax, cs:__security_cookie
0x1800309a3  xor     rax, rsp
0x1800309a6  mov     [rbp+4Fh+var_40], rax
0x1800309aa  mov     rax, [rdx]
0x1800309ad  mov     r14, r8
0x1800309b0  mov     r12, [rbp+4Fh+arg_20]
0x1800309b4  lea     r8, [rbp+4Fh+pProxy]
0x1800309b8  mov     rcx, rdx
0x1800309bb  xor     r13d, r13d
0x1800309be  lea     rdx, IID_IEventClassTier2
0x1800309c5  mov     [rbp+4Fh+var_A8], r13
0x1800309c9  mov     rax, [rax]
0x1800309cc  mov     r15d, r9d
0x1800309cf  mov     [rbp+4Fh+pProxy], r13
0x1800309d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309d8  mov     edi, eax
0x1800309da  test    eax, eax
0x1800309dc  js      loc_180030B9E
0x1800309e2  mov     rcx, [rbp+4Fh+pProxy]; pProxy
0x1800309e6  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800309ea  mov     [rsp+0F0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800309f2  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800309f5  mov     [rsp+0F0h+pAuthInfo], r9; pAuthInfo
0x1800309fa  mov     r8d, edx; dwAuthzSvc
0x1800309fd  mov     [rsp+0F0h+dwImpLevel], 3; dwImpLevel
0x180030a05  mov     [rsp+0F0h+dwAuthnLevel], r13d; dwAuthnLevel
0x180030a0a  call    cs:__imp_CoSetProxyBlanket
0x180030a10  mov     ecx, 2D0h; cb
0x180030a15  call    cs:__imp_CoTaskMemAlloc
0x180030a1b  test    rax, rax
0x180030a1e  jz      loc_180030AF2
0x180030a24  mov     rcx, rax; this
0x180030a27  call    ??0CEventClass@@AEAA@XZ; CEventClass::CEventClass(void)
0x180030a2c  mov     rbx, rax
0x180030a2f  test    rax, rax
0x180030a32  jz      loc_180030AF5
0x180030a38  mov     rcx, [rbp+4Fh+pProxy]
0x180030a3c  lea     rdx, [rbx+30h]
0x180030a40  mov     rax, [rcx]
0x180030a43  mov     rax, [rax+20h]
0x180030a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a4c  mov     edi, eax
0x180030a4e  test    eax, eax
0x180030a50  js      loc_180030AE8
0x180030a56  mov     rax, [rbx]
0x180030a59  lea     r8, [rbp+4Fh+var_A8]
0x180030a5d  lea     rdx, IID_IEventClass2
0x180030a64  mov     [rbx+1E0h], r13d
0x180030a6b  mov     rcx, rbx
0x180030a6e  mov     rax, [rax]
0x180030a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a76  mov     edi, eax
0x180030a78  test    eax, eax
0x180030a7a  js      short loc_180030AE8
0x180030a7c  movups  xmm0, xmmword ptr [rbx+150h]
0x180030a83  lea     rax, [rbx+1E4h]
0x180030a8a  movsd   xmm1, qword ptr [rbx+160h]
0x180030a92  lea     r8, [rbp+4Fh+pclsid]; struct tagPROPVARIANT *
0x180030a96  movaps  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180030a9a  lea     rdx, [rbp+4Fh+var_A0]; struct tagPROPVARIANT *
0x180030a9e  movups  xmm0, xmmword ptr [rbx+138h]
0x180030aa5  lea     rcx, [rbp+4Fh+var_80]; struct tagPROPVARIANT *
0x180030aa9  mov     qword ptr [rsp+0F0h+dwAuthnLevel], rax; unsigned __int16 *
0x180030aae  movsd   [rbp+4Fh+var_50], xmm1
0x180030ab3  movsd   xmm1, qword ptr [rbx+148h]
0x180030abb  movaps  xmmword ptr [rbp+4Fh+var_A0], xmm0
0x180030abf  movups  xmm0, xmmword ptr [rbx+30h]
0x180030ac3  movsd   qword ptr [rbp+4Fh+var_A0+10h], xmm1
0x180030ac8  movsd   xmm1, qword ptr [rbx+40h]
0x180030acd  movaps  xmmword ptr [rbp+4Fh+var_80], xmm0
0x180030ad1  movsd   qword ptr [rbp+4Fh+var_80+10h], xmm1
0x180030ad6  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x180030adb  mov     [rbx+1E0h], r13d
0x180030ae2  mov     edi, eax
0x180030ae4  test    eax, eax
0x180030ae6  jns     short loc_180030AFA
0x180030ae8  mov     rcx, rbx; this
0x180030aeb  call    ??_GCEventClass@@AEAAPEAXI@Z; CEventClass::`scalar deleting destructor'(uint)
0x180030af0  jmp     short loc_180030AFA
0x180030af2  mov     rbx, r13
0x180030af5  mov     edi, 8007000Eh
0x180030afa  mov     rcx, [rbp+4Fh+pProxy]
0x180030afe  mov     rax, [rcx]
0x180030b01  mov     rax, [rax+10h]
0x180030b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b0a  test    edi, edi
0x180030b0c  js      loc_180030B9E
0x180030b12  mov     esi, 10h
0x180030b17  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180030b1e  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180030b23  cmp     [rbx+138h], r13w
0x180030b2b  jz      short loc_180030B5D
0x180030b2d  mov     rcx, [rbx+140h]; lpsz
0x180030b34  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x180030b38  call    cs:__imp_CLSIDFromString
0x180030b3e  mov     edi, eax
0x180030b40  test    eax, eax
0x180030b42  jns     short loc_180030B62
0x180030b44  mov     r8d, esi; unsigned __int16
0x180030b47  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180030b4e  mov     r9d, eax; int
0x180030b51  mov     edx, 0D0h; unsigned int
0x180030b56  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180030b5b  jmp     short loc_180030B62
0x180030b5d  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180030b62  mov     r8, rsi; Size
0x180030b65  lea     rdx, [rbp+4Fh+pclsid]; Buf2
0x180030b69  lea     rcx, GUID_NULL; Buf1
0x180030b70  call    memcmp_0
0x180030b75  test    r15d, r15d
0x180030b78  jz      short loc_180030BC7
0x180030b7a  test    eax, eax
0x180030b7c  jnz     short loc_180030B83
0x180030b7e  mov     edi, 8004020Dh
0x180030b83  test    edi, edi
0x180030b85  js      short loc_180030B9E
0x180030b87  mov     rax, [rbp+4Fh+var_A8]
0x180030b8b  mov     [r12], rax
0x180030b8f  test    r14, r14
0x180030b92  jz      short loc_180030B9E
0x180030b94  lea     rax, [rbx+1E4h]
0x180030b9b  mov     [r14], rax
0x180030b9e  mov     eax, edi
0x180030ba0  mov     rcx, [rbp+4Fh+var_40]
0x180030ba4  xor     rcx, rsp; StackCookie
0x180030ba7  call    __security_check_cookie
0x180030bac  mov     rbx, [rsp+0F0h+arg_0]
0x180030bb4  add     rsp, 0C0h
0x180030bbb  pop     r15
0x180030bbd  pop     r14
0x180030bbf  pop     r13
0x180030bc1  pop     r12
0x180030bc3  pop     rdi
0x180030bc4  pop     rsi
0x180030bc5  pop     rbp
0x180030bc6  retn
0x180030bc7  test    eax, eax
0x180030bc9  jz      short loc_180030B83
0x180030bcb  mov     edi, 8004020Eh
0x180030bd0  jmp     short loc_180030B9E
```
