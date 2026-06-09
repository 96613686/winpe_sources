# DllGetClassObject

- ea: `0x180008cb0`
- end: `0x180008db2`
- name: `DllGetClassObject`
- size: `258`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005c84`
- `0x180008cb0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008cd6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008cd6`
- `RPCRT4!NdrDllGetClassObject` at `0x180008d7f`
- `RPCRT4!NdrDllGetClassObject` at `0x180008d7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  HRESULT result; // eax
  int v11; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18004AEA8 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
  {
LABEL_6:
    result = -2147221231;
  }
  else
  {
    while ( 1 )
    {
      v8 = *v6;
      if ( *v6 )
      {
        v9 = *(_QWORD **)v8->Data4;
        if ( *v9 == *(_QWORD *)&rclsid->Data1 && v9[1] == *(_QWORD *)rclsid->Data4 )
          break;
      }
      if ( (unsigned __int64)++v6 >= v7 )
        goto LABEL_6;
    }
    v11 = 1;
    result = Microsoft::WRL::Details::GetCacheEntry(
               (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               (struct Microsoft::WRL::Details::ModuleBase *)&v11,
               &riid->Data1,
               v8,
               ppv);
  }
  if ( result == -2147221231 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  return result;
}

```

## disassembly

```asm
0x180008cb0  push    rbx
0x180008cb2  push    rbp
0x180008cb3  push    rsi
0x180008cb4  push    rdi
0x180008cb5  sub     rsp, 38h
0x180008cb9  mov     rsi, r8
0x180008cbc  mov     rbp, rdx
0x180008cbf  mov     rdi, rcx
0x180008cc2  xor     r9d, r9d; Context
0x180008cc5  xor     r8d, r8d; Parameter
0x180008cc8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008ccf  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008cd6  call    cs:__imp_InitOnceExecuteOnce
0x180008cdc  mov     cs:byte_18004AEA8, 1
0x180008ce3  mov     qword ptr [rsi], 0
0x180008cea  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cf1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cf8  mov     rax, [rax+20h]
0x180008cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d01  lea     rbx, [rax+8]
0x180008d05  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008d0c  mov     rax, [rcx+28h]
0x180008d10  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1c  mov     rdx, rax
0x180008d1f  cmp     rbx, rax
0x180008d22  jnb     short loc_180008D4B
0x180008d24  mov     r9, [rbx]; struct _GUID *
0x180008d27  test    r9, r9
0x180008d2a  jz      short loc_180008D42
0x180008d2c  mov     rax, [r9+8]
0x180008d30  mov     rcx, [rax]
0x180008d33  cmp     rcx, [rdi]
0x180008d36  jnz     short loc_180008D42
0x180008d38  mov     rax, [rax+8]
0x180008d3c  cmp     rax, [rdi+8]
0x180008d40  jz      short loc_180008D8E
0x180008d42  add     rbx, 8
0x180008d46  cmp     rbx, rdx
0x180008d49  jb      short loc_180008D24
0x180008d4b  mov     eax, 80040111h
0x180008d50  cmp     eax, 80040111h
0x180008d55  jnz     short loc_180008D85
0x180008d57  lea     rax, gPFactory
0x180008d5e  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180008d63  lea     rax, CLSID_PSFactoryBuffer
0x180008d6a  mov     [rsp+58h+pclsid], rax; pclsid
0x180008d6f  lea     r9, aProxyFileList; pProxyFileList
0x180008d76  mov     r8, rsi; ppv
0x180008d79  mov     rdx, rbp; riid
0x180008d7c  mov     rcx, rdi; rclsid
0x180008d7f  call    cs:__imp_NdrDllGetClassObject
0x180008d85  add     rsp, 38h
0x180008d89  pop     rdi
0x180008d8a  pop     rsi
0x180008d8b  pop     rbp
0x180008d8c  pop     rbx
0x180008d8d  retn
0x180008d8e  mov     [rsp+58h+arg_10], 1
0x180008d96  mov     [rsp+58h+pclsid], rsi; Ptr
0x180008d9b  mov     r8, rbp; unsigned int *
0x180008d9e  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180008da3  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180008daa  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180008daf  jmp     short loc_180008D50
```
