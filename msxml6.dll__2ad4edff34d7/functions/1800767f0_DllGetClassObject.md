# DllGetClassObject

- ea: `0x1800767f0`
- end: `0x180076927`
- name: `DllGetClassObject`
- size: `311`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002b064`
- `0x1800767f0`
- `0x180087e48`
- `0x180096038`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800d199c`
- `0x180188010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180076860`
- `RPCRT4!NdrDllGetClassObject` at `0x180076860`

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
0x1800767f0  mov     [rsp+arg_10], ppv
0x1800767f5  push    rbx
0x1800767f6  push    rsi
0x1800767f7  push    rdi
0x1800767f8  push    r14
0x1800767fa  sub     rsp, 48h
0x1800767fe  mov     rbx, ppv
0x180076801  mov     r14, iid
0x180076804  mov     rdi, clsid
0x180076807  test    ppv, ppv
0x18007680a  jnz     short loc_180076816
0x18007680c  mov     eax, 80070057h
0x180076811  jmp     loc_18007691D
0x180076816  mov     qword ptr [ppv], 0
0x18007681d  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180076824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076829  test    rax, rax
0x18007682c  jnz     short loc_180076838
0x18007682e  mov     eax, 80004005h
0x180076833  jmp     loc_18007691D
0x180076838  lea     rax, gPFactory
0x18007683f  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180076844  lea     rax, CLSID_PSFactoryBuffer
0x18007684b  mov     [rsp+68h+pclsid], rax; pclsid
0x180076850  lea     r9, aProxyFileList; pProxyFileList
0x180076857  mov     ppv, rbx; ppv
0x18007685a  mov     iid, r14; riid
0x18007685d  mov     clsid, rdi; rclsid
0x180076860  call    cs:__imp_NdrDllGetClassObject
0x180076866  test    eax, eax
0x180076868  jz      loc_18007691D
0x18007686e  xor     edx, edx
0x180076870  mov     [rsp+68h+i], edx
0x180076874  movsxd  rax, edx
0x180076877  cmp     rax, 0Ch
0x18007687b  jnb     short loc_1800768BD
0x18007687d  lea     rsi, MSXML__ClassFactories__s_ComponentFactoryTable
0x180076884  mov     rsi, [rsi+rax*8]
0x180076888  mov     ppv, [rsi+8]
0x18007688c  mov     rax, [rdi]
0x18007688f  cmp     rax, [ppv]
0x180076892  jnz     short loc_1800768B9
0x180076894  mov     rax, [rdi+8]
0x180076898  cmp     rax, [ppv+8]
0x18007689c  jnz     short loc_1800768B9
0x18007689e  call    EnsureClassInit
0x1800768a3  mov     rax, [rsi]
0x1800768a6  mov     ppv, rbx
0x1800768a9  mov     iid, r14
0x1800768ac  mov     clsid, rsi
0x1800768af  mov     rax, [rax]
0x1800768b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768b7  jmp     short loc_1800768DA
0x1800768b9  inc     edx
0x1800768bb  jmp     short loc_180076870
0x1800768bd  call    EnsureClassInit
0x1800768c2  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800768c7  mov     [rsp+68h+pclsid], rbx; modulePtr
0x1800768cc  mov     r9, r14; ppv
0x1800768cf  mov     ppv, rdi; riid
0x1800768d2  mov     clsid, rax; modulePtr
0x1800768d5  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800768da  mov     [rsp+68h+hr], eax
0x1800768de  jmp     short loc_18007691D
0x1800768e0  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800768e5  mov     rax, [rsp+68h+arg_10]
0x1800768ed  mov     qword ptr [rax], 0
0x1800768f4  mov     ecx, cs:_tls_index
0x1800768fa  mov     rax, gs:58h
0x180076903  mov     edx, 8
0x180076908  mov     rax, [rax+clsid*8]
0x18007690c  mov     clsid, [rax+iid]
0x180076910  mov     clsid, [clsid+8]; e
0x180076914  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x180076919  mov     [rsp+68h+hr], eax
0x18007691d  add     rsp, 48h
0x180076921  pop     r14
0x180076923  pop     rdi
0x180076924  pop     rsi
0x180076925  pop     rbx
0x180076926  retn
0x18017c32b  push    rbp
0x18017c32d  sub     rsp, 30h
0x18017c331  mov     rbp, rdx
0x18017c334  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017c339  nop
0x18017c33a  add     rsp, 30h
0x18017c33e  pop     rbp
0x18017c33f  retn
```
