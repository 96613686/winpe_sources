# DllGetClassObject(x,x,x)

- ea: `0x10056390`
- end: `0x10056497`
- name: `_DllGetClassObject@12`
- size: `263`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x100505bc`
- `0x1005083d`
- `0x10056390`
- `0x100572ba`
- `0x1006743d`
- `0x10067b20`
- `0x1006bff0`
- `0x10071b93`
- `0x10076076`
- `0x100779f5`
- `0x10077a4b`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x100563de`
- `RPCRT4!NdrDllGetClassObject` at `0x100563de`

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
0x10056390  push    14h
0x10056392  push    offset stru_10173BD8
0x10056397  call    __SEH_prolog4
0x1005639c  mov     edi, [ebp+ppv]
0x1005639f  test    edi, edi
0x100563a1  jnz     short loc_100563AD
0x100563a3  mov     eax, 80070057h
0x100563a8  jmp     loc_10056485
0x100563ad  xor     esi, esi
0x100563af  mov     [edi], esi
0x100563b1  lea     ecx, [ebp+_EnsureTls]; this
0x100563b4  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100563b9  cmp     [ebp+_EnsureTls._tlsdata], esi
0x100563bc  jnz     short loc_100563C8
0x100563be  mov     eax, 80004005h
0x100563c3  jmp     loc_10056485
0x100563c8  push    offset _gPFactory; pPSFactoryBuffer
0x100563cd  push    offset _CLSID_PSFactoryBuffer; pclsid
0x100563d2  push    offset _aProxyFileList; pProxyFileList
0x100563d7  push    edi; ppv
0x100563d8  push    [ebp+iid]; riid
0x100563db  push    [ebp+clsid]; rclsid
0x100563de  call    ds:__imp__NdrDllGetClassObject@24; NdrDllGetClassObject(x,x,x,x,x,x)
0x100563e4  test    eax, eax
0x100563e6  jz      loc_10056485
0x100563ec  mov     [ebp+ms_exc.registration.TryLevel], esi
0x100563ef  mov     [ebp+i], esi
0x100563f2  cmp     esi, 0Ch
0x100563f5  jnb     short loc_1005642A
0x100563f7  mov     ebx, ds:MSXML__ClassFactories__s_ComponentFactoryTable[esi*4]
0x100563fe  mov     edx, [ebx+4]; rguid2
0x10056401  mov     ecx, [ebp+clsid]; rguid1
0x10056404  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x10056409  test    eax, eax
0x1005640b  jz      short loc_10056427
0x1005640d  call    EnsureClassInit
0x10056412  mov     eax, [ebx]
0x10056414  mov     esi, [eax]
0x10056416  push    edi
0x10056417  push    [ebp+iid]
0x1005641a  push    ebx
0x1005641b  mov     ecx, esi; this
0x1005641d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10056423  call    esi
0x10056425  jmp     short loc_1005647B
0x10056427  inc     esi
0x10056428  jmp     short loc_100563EF
0x1005642a  call    EnsureClassInit
0x1005642f  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SGAAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x10056434  push    edi; ppv
0x10056435  push    [ebp+iid]; riid
0x10056438  push    [ebp+clsid]; clsid
0x1005643b  mov     ecx, eax; modulePtr
0x1005643d  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YGJPAVModuleBase@012@PBGABU_GUID@@2PAPAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x10056442  jmp     short loc_1005647B
0x10056444  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10056447  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1005644c  retn
0x1005644d  mov     esp, [ebp+ms_exc.old_esp]
0x10056450  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10056455  mov     eax, [ebp+ppv]
0x10056458  mov     dword ptr [eax], 0
0x1005645e  mov     ecx, __tls_index
0x10056464  mov     eax, large fs:2Ch
0x1005646a  mov     eax, [eax+ecx*4]
0x1005646d  mov     eax, [eax+4]
0x10056473  mov     ecx, [eax+8]; e
0x10056476  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1005647b  mov     [ebp+hr], eax
0x1005647e  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10056485  mov     ecx, [ebp+ms_exc.registration.Next]
0x10056488  mov     large fs:0, ecx
0x1005648f  pop     ecx
0x10056490  pop     edi
0x10056491  pop     esi
0x10056492  pop     ebx
0x10056493  leave
0x10056494  retn    0Ch
```
