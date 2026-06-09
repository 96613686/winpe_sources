# DllGetClassObject

- ea: `0x180002f20`
- end: `0x180003020`
- name: `DllGetClassObject`
- size: `256`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002b44`
- `0x180002f20`
- `0x180004010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180003011`
- `RPCRT4!NdrDllGetClassObject` at `0x180003011`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002f4d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002f4d`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  HRESULT result; // eax
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+70h] [rbp+18h] BYREF

  *ppv = 0;
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180007688 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &LIBID_EASConsent,
             &gPFactory);
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
      return NdrDllGetClassObject(
               rclsid,
               riid,
               ppv,
               (const ProxyFileInfo **)&aProxyFileList,
               &LIBID_EASConsent,
               &gPFactory);
  }
  v12 = 1;
  result = Microsoft::WRL::Details::GetCacheEntry(
             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
             (struct Microsoft::WRL::Details::ModuleBase *)&v12,
             &riid->Data1,
             v8,
             ppv,
             pPSFactoryBuffer);
  if ( result < 0 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &LIBID_EASConsent,
             &gPFactory);
  return result;
}

```

## disassembly

```asm
0x180002f20  push    rbx
0x180002f22  push    rbp
0x180002f23  push    rsi
0x180002f24  push    rdi
0x180002f25  sub     rsp, 38h
0x180002f29  mov     rsi, r8
0x180002f2c  mov     qword ptr [r8], 0
0x180002f33  mov     rbp, rdx
0x180002f36  mov     rdi, rcx
0x180002f39  xor     r8d, r8d; Parameter
0x180002f3c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180002f43  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180002f4a  xor     r9d, r9d; Context
0x180002f4d  call    cs:__imp_InitOnceExecuteOnce
0x180002f53  mov     cs:byte_180007688, 1
0x180002f5a  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002f61  mov     qword ptr [rsi], 0
0x180002f68  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002f6f  mov     rax, [rax+20h]
0x180002f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f78  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002f7f  lea     rbx, [rax+8]
0x180002f83  mov     rax, [rcx+28h]
0x180002f87  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f93  mov     rdx, rax
0x180002f96  cmp     rbx, rax
0x180002f99  jnb     short loc_180002FE9
0x180002f9b  mov     r9, [rbx]; struct _GUID *
0x180002f9e  test    r9, r9
0x180002fa1  jz      short loc_180002FB9
0x180002fa3  mov     rax, [r9+8]
0x180002fa7  mov     rcx, [rax]
0x180002faa  cmp     rcx, [rdi]
0x180002fad  jnz     short loc_180002FB9
0x180002faf  mov     rax, [rax+8]
0x180002fb3  cmp     rax, [rdi+8]
0x180002fb7  jz      short loc_180002FC4
0x180002fb9  add     rbx, 8
0x180002fbd  cmp     rbx, rdx
0x180002fc0  jb      short loc_180002F9B
0x180002fc2  jmp     short loc_180002FE9
0x180002fc4  mov     r8, rbp; unsigned int *
0x180002fc7  mov     [rsp+58h+arg_10], 1
0x180002fcf  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180002fd4  mov     [rsp+58h+pclsid], rsi; Ptr
0x180002fd9  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180002fe0  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180002fe5  test    eax, eax
0x180002fe7  jns     short loc_180003017
0x180002fe9  lea     rax, gPFactory
0x180002ff0  mov     r8, rsi; ppv
0x180002ff3  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180002ff8  lea     r9, aProxyFileList; pProxyFileList
0x180002fff  lea     rax, LIBID_EASConsent
0x180003006  mov     rdx, rbp; riid
0x180003009  mov     rcx, rdi; rclsid
0x18000300c  mov     [rsp+58h+pclsid], rax; pclsid
0x180003011  call    cs:__imp_NdrDllGetClassObject
0x180003017  add     rsp, 38h
0x18000301b  pop     rdi
0x18000301c  pop     rsi
0x18000301d  pop     rbp
0x18000301e  pop     rbx
0x18000301f  retn
```
