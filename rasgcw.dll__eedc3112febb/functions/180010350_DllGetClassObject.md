# DllGetClassObject

- ea: `0x180010350`
- end: `0x180010406`
- name: `DllGetClassObject`
- size: `182`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c178`
- `0x180010350`
- `0x18002af18`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800103c2`
- `RPCRT4!NdrDllGetClassObject` at `0x1800103c2`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  DebugInit("RASGCW");
  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  pStubVtblList = aProxyFileList->pStubVtblList;
  if ( *pStubVtblList )
    pclsid = **(const CLSID ***)pStubVtblList;
  else
    pclsid = 0;
  if ( NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory) >= 0 )
    return 0;
  if ( qword_18004D998 )
    return ATL::CComModule::GetClassObject((ATL::CComModule *)&_Module, rclsid, riid, ppv);
  return -2147467259;
}

```

## disassembly

```asm
0x180010350  mov     [rsp+arg_0], rbx
0x180010355  mov     [rsp+arg_8], rsi
0x18001035a  push    rdi
0x18001035b  sub     rsp, 30h
0x18001035f  mov     rsi, rcx
0x180010362  mov     rbx, r8
0x180010365  lea     rcx, aRasgcw; "RASGCW"
0x18001036c  mov     rdi, rdx
0x18001036f  call    DebugInit
0x180010374  test    rbx, rbx
0x180010377  jnz     short loc_180010380
0x180010379  mov     eax, 80070057h
0x18001037e  jmp     short loc_1800103F6
0x180010380  mov     qword ptr [rbx], 0
0x180010387  mov     rax, cs:aProxyFileList
0x18001038e  mov     rcx, [rax+8]
0x180010392  mov     rax, [rcx]
0x180010395  test    rax, rax
0x180010398  jz      short loc_18001039F
0x18001039a  mov     rcx, [rax]
0x18001039d  jmp     short loc_1800103A1
0x18001039f  xor     ecx, ecx
0x1800103a1  lea     rax, gPFactory
0x1800103a8  mov     r8, rbx; ppv
0x1800103ab  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800103b0  lea     r9, aProxyFileList; pProxyFileList
0x1800103b7  mov     [rsp+38h+pclsid], rcx; pclsid
0x1800103bc  mov     rdx, rdi; riid
0x1800103bf  mov     rcx, rsi; rclsid
0x1800103c2  call    cs:__imp_NdrDllGetClassObject
0x1800103c8  test    eax, eax
0x1800103ca  jns     short loc_1800103F4
0x1800103cc  cmp     cs:qword_18004D998, 0
0x1800103d4  jz      short loc_1800103ED
0x1800103d6  mov     r9, rbx; void **
0x1800103d9  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800103e0  mov     r8, rdi; struct _GUID *
0x1800103e3  mov     rdx, rsi; struct _GUID *
0x1800103e6  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x1800103eb  jmp     short loc_1800103F6
0x1800103ed  mov     eax, 80004005h
0x1800103f2  jmp     short loc_1800103F6
0x1800103f4  xor     eax, eax
0x1800103f6  mov     rbx, [rsp+38h+arg_0]
0x1800103fb  mov     rsi, [rsp+38h+arg_8]
0x180010400  add     rsp, 30h
0x180010404  pop     rdi
0x180010405  retn
```
