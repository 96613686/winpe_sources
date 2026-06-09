# CIISServer::~CIISServer(void)

- ea: `0x180009b20`
- end: `0x180009be0`
- name: `??1CIISServer@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(CIISServer *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180009bf0`
- `0x180009c20`
- `0x180009df0`
- `0x18000a4b0`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x180009b20`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b6c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b7b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b6c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b7b`

## pseudocode

```c
void __fastcall CIISServer::~CIISServer(CIISServer *this)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  void *v4; // rbx
  __int64 v5; // rcx

  *(_QWORD *)this = &CIISServer::`vftable'{for `IADsServiceOperations'};
  *((_QWORD *)this + 1) = &CIISServer::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApp::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApp::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISServer::`vftable'{for `INonDelegatingUnknown'};
  v2 = (WCHAR *)*((_QWORD *)this + 8);
  if ( v2 )
    FreeADsStr(v2);
  v3 = (WCHAR *)*((_QWORD *)this + 9);
  if ( v3 )
    FreeADsStr(v3);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    CAggregateeDispMgr::~CAggregateeDispMgr(*((CAggregateeDispMgr **)this + 11));
    operator delete(v4);
  }
  v5 = *((_QWORD *)this + 15);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  CCredentials::FreeUserName((unsigned __int16 **)this + 12);
  CCredentials::FreePassword((LPVOID *)this + 13, (unsigned int *)this + 29);
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISServer *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x180009b20  mov     [rsp+arg_0], rbx
0x180009b25  push    rdi
0x180009b26  sub     rsp, 20h
0x180009b2a  lea     rax, ??_7CIISServer@@6BIADsServiceOperations@@@; const CIISServer::`vftable'{for `IADsServiceOperations'}
0x180009b31  mov     rdi, rcx
0x180009b34  mov     [rcx], rax
0x180009b37  lea     rax, ??_7CIISServer@@6BIPrivateUnknown@@@; const CIISServer::`vftable'{for `IPrivateUnknown'}
0x180009b3e  mov     [rcx+8], rax
0x180009b42  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x180009b49  mov     [rcx+10h], rax
0x180009b4d  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x180009b54  mov     [rcx+18h], rax
0x180009b58  lea     rax, ??_7CIISServer@@6BINonDelegatingUnknown@@@; const CIISServer::`vftable'{for `INonDelegatingUnknown'}
0x180009b5f  mov     [rcx+20h], rax
0x180009b63  mov     rcx, [rcx+40h]; pStr
0x180009b67  test    rcx, rcx
0x180009b6a  jz      short loc_180009B72
0x180009b6c  call    cs:__imp_FreeADsStr
0x180009b72  mov     rcx, [rdi+48h]; pStr
0x180009b76  test    rcx, rcx
0x180009b79  jz      short loc_180009B81
0x180009b7b  call    cs:__imp_FreeADsStr
0x180009b81  mov     rbx, [rdi+58h]
0x180009b85  test    rbx, rbx
0x180009b88  jz      short loc_180009B9A
0x180009b8a  mov     rcx, rbx; this
0x180009b8d  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x180009b92  mov     rcx, rbx; Block
0x180009b95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009b9a  mov     rcx, [rdi+78h]
0x180009b9e  test    rcx, rcx
0x180009ba1  jz      short loc_180009BAF
0x180009ba3  mov     rax, [rcx]
0x180009ba6  mov     rax, [rax+10h]
0x180009baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009baf  lea     rcx, [rdi+60h]; unsigned __int16 **
0x180009bb3  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180009bb8  lea     rdx, [rdi+74h]; unsigned int *
0x180009bbc  lea     rcx, [rdi+68h]; unsigned __int16 **
0x180009bc0  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180009bc5  lea     rcx, [rdi+2Ch]; this
0x180009bc9  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x180009bce  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180009bd5  mov     rbx, [rsp+28h+arg_0]
0x180009bda  add     rsp, 20h
0x180009bde  pop     rdi
0x180009bdf  retn
```
