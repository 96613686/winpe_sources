# CWmiProvider::~CWmiProvider(void)

- ea: `0x1800236d8`
- end: `0x18002385b`
- name: `??1CWmiProvider@@AEAA@XZ`
- size: `387`
- prototype: `void __fastcall(CWmiProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025bb0`

## callees

- `0x180016280`
- `0x1800236d8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002376d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800237c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023825`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002376d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800237c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023825`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023723`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023723`

## pseudocode

```c
void __fastcall CWmiProvider::~CWmiProvider(CWmiProvider *this)
{
  CRefCounted *v2; // rcx
  unsigned int v3; // edi
  unsigned int v4; // edi
  unsigned int v5; // ebx
  LPVOID ppv; // [rsp+60h] [rbp+28h] BYREF

  *(_QWORD *)this = &CWmiProvider::`vftable'{for `IWbemProviderInit'};
  *((_QWORD *)this + 1) = &CWmiProvider::`vftable'{for `IWbemServices'};
  *((_QWORD *)this + 2) = &CWmiProvider::`vftable'{for `IWbemShutdown'};
  v2 = (CRefCounted *)*((_QWORD *)this + 23);
  if ( v2 )
    CRefCounted::ReleaseReference(v2);
  if ( *((_DWORD *)this + 18) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&g_cRefDll);
  v3 = *((_DWORD *)this + 40);
  *((_QWORD *)this + 18) = &CInterfaceInGITBase::`vftable';
  if ( v3 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  v4 = *((_DWORD *)this + 30);
  *((_QWORD *)this + 13) = &CInterfaceInGITBase::`vftable';
  if ( v4 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  *((_QWORD *)this + 10) = &CInterfaceInGITBase::`vftable';
  v5 = *((_DWORD *)this + 24);
  if ( v5 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v5);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x1800236d8  push    rbp
0x1800236da  push    rbx
0x1800236db  push    rdi
0x1800236dc  push    r14
0x1800236de  mov     rbp, rsp
0x1800236e1  sub     rsp, 38h
0x1800236e5  lea     rax, ??_7CWmiProvider@@6BIWbemProviderInit@@@; const CWmiProvider::`vftable'{for `IWbemProviderInit'}
0x1800236ec  mov     rbx, rcx
0x1800236ef  mov     [rcx], rax
0x1800236f2  lea     rax, ??_7CWmiProvider@@6BIWbemServices@@@; const CWmiProvider::`vftable'{for `IWbemServices'}
0x1800236f9  mov     [rcx+8], rax
0x1800236fd  lea     rax, ??_7CWmiProvider@@6BIWbemShutdown@@@; const CWmiProvider::`vftable'{for `IWbemShutdown'}
0x180023704  mov     [rcx+10h], rax
0x180023708  mov     rcx, [rcx+0B8h]; this
0x18002370f  test    rcx, rcx
0x180023712  jz      short loc_180023719
0x180023714  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180023719  cmp     dword ptr [rbx+48h], 0
0x18002371d  jz      short loc_180023729
0x18002371f  lea     rcx, [rbx+20h]; lpCriticalSection
0x180023723  call    cs:__imp_DeleteCriticalSection
0x180023729  lock dec cs:?g_cRefDll@@3JA; long g_cRefDll
0x180023730  lea     r14, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x180023737  mov     edi, [rbx+0A0h]
0x18002373d  mov     [rbx+90h], r14
0x180023744  test    edi, edi
0x180023746  jz      short loc_180023799
0x180023748  xor     edx, edx; pUnkOuter
0x18002374a  mov     [rbp+arg_0], 0
0x180023752  lea     rax, [rbp+arg_0]
0x180023756  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18002375d  mov     [rsp+38h+ppv], rax; ppv
0x180023762  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180023769  lea     r8d, [rdx+1]; dwClsContext
0x18002376d  call    cs:__imp_CoCreateInstance
0x180023773  test    eax, eax
0x180023775  js      short loc_180023799
0x180023777  mov     rcx, [rbp+arg_0]
0x18002377b  mov     edx, edi
0x18002377d  mov     rax, [rcx]
0x180023780  mov     rax, [rax+20h]
0x180023784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023789  mov     rcx, [rbp+arg_0]
0x18002378d  mov     rax, [rcx]
0x180023790  mov     rax, [rax+10h]
0x180023794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023799  mov     edi, [rbx+78h]
0x18002379c  mov     [rbx+68h], r14
0x1800237a0  test    edi, edi
0x1800237a2  jz      short loc_1800237F5
0x1800237a4  xor     edx, edx; pUnkOuter
0x1800237a6  mov     [rbp+arg_0], 0
0x1800237ae  lea     rax, [rbp+arg_0]
0x1800237b2  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800237b9  mov     [rsp+38h+ppv], rax; ppv
0x1800237be  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800237c5  lea     r8d, [rdx+1]; dwClsContext
0x1800237c9  call    cs:__imp_CoCreateInstance
0x1800237cf  test    eax, eax
0x1800237d1  js      short loc_1800237F5
0x1800237d3  mov     rcx, [rbp+arg_0]
0x1800237d7  mov     edx, edi
0x1800237d9  mov     rax, [rcx]
0x1800237dc  mov     rax, [rax+20h]
0x1800237e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237e5  mov     rcx, [rbp+arg_0]
0x1800237e9  mov     rax, [rcx]
0x1800237ec  mov     rax, [rax+10h]
0x1800237f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f5  mov     [rbx+50h], r14
0x1800237f9  mov     ebx, [rbx+60h]
0x1800237fc  test    ebx, ebx
0x1800237fe  jz      short loc_180023851
0x180023800  xor     edx, edx; pUnkOuter
0x180023802  mov     [rbp+arg_0], 0
0x18002380a  lea     rax, [rbp+arg_0]
0x18002380e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180023815  mov     [rsp+38h+ppv], rax; ppv
0x18002381a  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180023821  lea     r8d, [rdx+1]; dwClsContext
0x180023825  call    cs:__imp_CoCreateInstance
0x18002382b  test    eax, eax
0x18002382d  js      short loc_180023851
0x18002382f  mov     rcx, [rbp+arg_0]
0x180023833  mov     edx, ebx
0x180023835  mov     rax, [rcx]
0x180023838  mov     rax, [rax+20h]
0x18002383c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023841  mov     rcx, [rbp+arg_0]
0x180023845  mov     rax, [rcx]
0x180023848  mov     rax, [rax+10h]
0x18002384c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023851  add     rsp, 38h
0x180023855  pop     r14
0x180023857  pop     rdi
0x180023858  pop     rbx
0x180023859  pop     rbp
0x18002385a  retn
```
