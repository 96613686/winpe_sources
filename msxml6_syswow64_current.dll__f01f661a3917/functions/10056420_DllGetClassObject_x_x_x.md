# DllGetClassObject(x,x,x)

- ea: `0x10056420`
- end: `0x10056527`
- name: `_DllGetClassObject@12`
- size: `263`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1005064c`
- `0x100508cd`
- `0x10056420`
- `0x1005734a`
- `0x100674dd`
- `0x10067bc0`
- `0x1006c080`
- `0x10071c33`
- `0x10076046`
- `0x100779c5`
- `0x10077a1b`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1005646e`
- `RPCRT4!NdrDllGetClassObject` at `0x1005646e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  unsigned int v4; // esi
  const ClassFactory *v5; // ebx
  Microsoft::WRL::Details::DefaultModule<1> *v6; // eax
  EnsureTls _EnsureTls; // [esp+14h] [ebp-20h] BYREF
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  if ( !ppv )
    return -2147024809;
  v4 = 0;
  *ppv = 0;
  EnsureTls::EnsureTls(&_EnsureTls);
  if ( _EnsureTls._tlsdata )
  {
    result = NdrDllGetClassObject(
               rclsid,
               riid,
               ppv,
               (const ProxyFileInfo **)aProxyFileList,
               &CLSID_PSFactoryBuffer,
               &gPFactory);
    if ( result )
    {
      ms_exc.registration.TryLevel = 0;
      while ( v4 < 0xC )
      {
        v5 = MSXML::ClassFactories::s_ComponentFactoryTable[v4];
        if ( IsEqualGUID(rclsid, v5->_pclsid) )
        {
          EnsureClassInit();
          return ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), const ClassFactory *, const IID *const, LPVOID *))v5->QueryInterface)(
                   v5->QueryInterface,
                   v5,
                   riid,
                   ppv);
        }
        ++v4;
      }
      EnsureClassInit();
      v6 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
      return Microsoft::WRL::Details::GetClassObject<1>(v6, rclsid, riid, (const _GUID *)ppv);
    }
  }
  else
  {
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x10056420  push    14h
0x10056422  push    offset stru_10173AE8
0x10056427  call    __SEH_prolog4
0x1005642c  mov     edi, [ebp+ppv]
0x1005642f  test    edi, edi
0x10056431  jnz     short loc_1005643D
0x10056433  mov     eax, 80070057h
0x10056438  jmp     loc_10056515
0x1005643d  xor     esi, esi
0x1005643f  mov     [edi], esi
0x10056441  lea     ecx, [ebp+_EnsureTls]; this
0x10056444  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10056449  cmp     [ebp+_EnsureTls._tlsdata], esi
0x1005644c  jnz     short loc_10056458
0x1005644e  mov     eax, 80004005h
0x10056453  jmp     loc_10056515
0x10056458  push    offset _gPFactory; pPSFactoryBuffer
0x1005645d  push    offset _CLSID_PSFactoryBuffer; pclsid
0x10056462  push    offset _aProxyFileList; pProxyFileList
0x10056467  push    edi; ppv
0x10056468  push    [ebp+iid]; riid
0x1005646b  push    [ebp+clsid]; rclsid
0x1005646e  call    ds:__imp__NdrDllGetClassObject@24; NdrDllGetClassObject(x,x,x,x,x,x)
0x10056474  test    eax, eax
0x10056476  jz      loc_10056515
0x1005647c  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1005647f  mov     [ebp+i], esi
0x10056482  cmp     esi, 0Ch
0x10056485  jnb     short loc_100564BA
0x10056487  mov     ebx, ds:MSXML__ClassFactories__s_ComponentFactoryTable[esi*4]
0x1005648e  mov     edx, [ebx+4]; rguid2
0x10056491  mov     ecx, [ebp+clsid]; rguid1
0x10056494  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x10056499  test    eax, eax
0x1005649b  jz      short loc_100564B7
0x1005649d  call    EnsureClassInit
0x100564a2  mov     eax, [ebx]
0x100564a4  mov     esi, [eax]
0x100564a6  push    edi
0x100564a7  push    [ebp+iid]
0x100564aa  push    ebx
0x100564ab  mov     ecx, esi; this
0x100564ad  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100564b3  call    esi
0x100564b5  jmp     short loc_1005650B
0x100564b7  inc     esi
0x100564b8  jmp     short loc_1005647F
0x100564ba  call    EnsureClassInit
0x100564bf  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SGAAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x100564c4  push    edi; ppv
0x100564c5  push    [ebp+iid]; riid
0x100564c8  push    [ebp+clsid]; clsid
0x100564cb  mov     ecx, eax; modulePtr
0x100564cd  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YGJPAVModuleBase@012@PBGABU_GUID@@2PAPAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x100564d2  jmp     short loc_1005650B
0x100564d4  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100564d7  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100564dc  retn
0x100564dd  mov     esp, [ebp+ms_exc.old_esp]
0x100564e0  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100564e5  mov     eax, [ebp+ppv]
0x100564e8  mov     dword ptr [eax], 0
0x100564ee  mov     ecx, __tls_index
0x100564f4  mov     eax, large fs:2Ch
0x100564fa  mov     eax, [eax+ecx*4]
0x100564fd  mov     eax, [eax+4]
0x10056503  mov     ecx, [eax+8]; e
0x10056506  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1005650b  mov     [ebp+hr], eax
0x1005650e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10056515  mov     ecx, [ebp+ms_exc.registration.Next]
0x10056518  mov     large fs:0, ecx
0x1005651f  pop     ecx
0x10056520  pop     edi
0x10056521  pop     esi
0x10056522  pop     ebx
0x10056523  leave
0x10056524  retn    0Ch
```
