# DllGetClassObject

- ea: `0x180075e10`
- end: `0x180075f4e`
- name: `DllGetClassObject`
- size: `318`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180075e10`
- `0x18008703c`
- `0x18009402c`
- `0x180095e54`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800d355c`
- `0x18018c010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180075e80`
- `RPCRT4!NdrDllGetClassObject` at `0x180075e80`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  int i; // edx
  const ClassFactory *v8; // rsi
  const _GUID *pclsid; // r8
  Microsoft::WRL::Details::DefaultModule<1> *v10; // rax
  const wchar_t *v11; // rdx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( !(__int64)g_pfnEntry() )
    return -2147467259;
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result )
  {
    for ( i = 0; (unsigned __int64)i < 0xC; ++i )
    {
      v8 = MSXML::ClassFactories::s_ComponentFactoryTable[i];
      pclsid = v8->_pclsid;
      if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&pclsid->Data1
        && *(_QWORD *)rclsid->Data4 == *(_QWORD *)pclsid->Data4 )
      {
        EnsureClassInit();
        return v8->QueryInterface(&v8->IClassFactory, riid, ppv);
      }
    }
    EnsureClassInit();
    v10 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    return Microsoft::WRL::Details::GetClassObject<1>(v10, v11, rclsid, riid, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x180075e10  mov     [rsp+arg_10], ppv
0x180075e15  push    rbx
0x180075e16  push    rsi
0x180075e17  push    rdi
0x180075e18  push    r14
0x180075e1a  sub     rsp, 48h
0x180075e1e  mov     rbx, ppv
0x180075e21  mov     r14, iid
0x180075e24  mov     rdi, clsid
0x180075e27  test    ppv, ppv
0x180075e2a  jnz     short loc_180075E36
0x180075e2c  mov     eax, 80070057h
0x180075e31  jmp     loc_180075F43
0x180075e36  mov     qword ptr [ppv], 0
0x180075e3d  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180075e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e49  test    rax, rax
0x180075e4c  jnz     short loc_180075E58
0x180075e4e  mov     eax, 80004005h
0x180075e53  jmp     loc_180075F43
0x180075e58  lea     rax, gPFactory
0x180075e5f  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180075e64  lea     rax, CLSID_PSFactoryBuffer
0x180075e6b  mov     [rsp+68h+pclsid], rax; pclsid
0x180075e70  lea     r9, aProxyFileList; pProxyFileList
0x180075e77  mov     ppv, rbx; ppv
0x180075e7a  mov     iid, r14; riid
0x180075e7d  mov     clsid, rdi; rclsid
0x180075e80  call    cs:__imp_NdrDllGetClassObject
0x180075e87  nop     dword ptr [rax+rax+00h]
0x180075e8c  test    eax, eax
0x180075e8e  jz      loc_180075F43
0x180075e94  xor     edx, edx
0x180075e96  mov     [rsp+68h+i], edx
0x180075e9a  movsxd  rax, edx
0x180075e9d  cmp     rax, 0Ch
0x180075ea1  jnb     short loc_180075EE3
0x180075ea3  lea     rsi, MSXML__ClassFactories__s_ComponentFactoryTable
0x180075eaa  mov     rsi, [rsi+rax*8]
0x180075eae  mov     ppv, [rsi+8]
0x180075eb2  mov     rax, [rdi]
0x180075eb5  cmp     rax, [ppv]
0x180075eb8  jnz     short loc_180075EDF
0x180075eba  mov     rax, [rdi+8]
0x180075ebe  cmp     rax, [ppv+8]
0x180075ec2  jnz     short loc_180075EDF
0x180075ec4  call    EnsureClassInit
0x180075ec9  mov     rax, [rsi]
0x180075ecc  mov     ppv, rbx
0x180075ecf  mov     iid, r14
0x180075ed2  mov     clsid, rsi
0x180075ed5  mov     rax, [rax]
0x180075ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075edd  jmp     short loc_180075F00
0x180075edf  inc     edx
0x180075ee1  jmp     short loc_180075E96
0x180075ee3  call    EnsureClassInit
0x180075ee8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180075eed  mov     [rsp+68h+pclsid], rbx; modulePtr
0x180075ef2  mov     r9, r14; ppv
0x180075ef5  mov     ppv, rdi; riid
0x180075ef8  mov     clsid, rax; modulePtr
0x180075efb  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x180075f00  mov     [rsp+68h+hr], eax
0x180075f04  jmp     short loc_180075F43
0x180075f06  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180075f0b  mov     rax, [rsp+68h+arg_10]
0x180075f13  mov     qword ptr [rax], 0
0x180075f1a  mov     ecx, cs:_tls_index
0x180075f20  mov     rax, gs:58h
0x180075f29  mov     edx, 8
0x180075f2e  mov     rax, [rax+clsid*8]
0x180075f32  mov     clsid, [rax+iid]
0x180075f36  mov     clsid, [clsid+8]; e
0x180075f3a  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x180075f3f  mov     [rsp+68h+hr], eax
0x180075f43  add     rsp, 48h
0x180075f47  pop     r14
0x180075f49  pop     rdi
0x180075f4a  pop     rsi
0x180075f4b  pop     rbx
0x180075f4c  retn
0x18017fc82  push    rbp
0x18017fc84  sub     rsp, 30h
0x18017fc88  mov     rbp, rdx
0x18017fc8b  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017fc90  nop
0x18017fc91  add     rsp, 30h
0x18017fc95  pop     rbp
0x18017fc96  retn
```
