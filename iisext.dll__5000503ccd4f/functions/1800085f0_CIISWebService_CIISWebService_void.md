# CIISWebService::~CIISWebService(void)

- ea: `0x1800085f0`
- end: `0x1800086b0`
- name: `??1CIISWebService@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(CIISWebService *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1800086c0`
- `0x180008834`
- `0x180008fc0`
- `0x180009910`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x1800085f0`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x18000863c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000864b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000863c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000864b`

## pseudocode

```c
void __fastcall CIISWebService::~CIISWebService(CIISWebService *this)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  void *v4; // rbx
  __int64 v5; // rcx

  *(_QWORD *)this = &CIISWebService::`vftable'{for `IISWebService'};
  *((_QWORD *)this + 1) = &CIISWebService::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApp::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApp::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISWebService::`vftable'{for `INonDelegatingUnknown'};
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
  CCredentials::FreePassword((unsigned __int16 **)this + 13, (unsigned int *)this + 29);
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISWebService *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x1800085f0  mov     [rsp+arg_0], rbx
0x1800085f5  push    rdi
0x1800085f6  sub     rsp, 20h
0x1800085fa  lea     rax, ??_7CIISWebService@@6BIISWebService@@@; const CIISWebService::`vftable'{for `IISWebService'}
0x180008601  mov     rdi, rcx
0x180008604  mov     [rcx], rax
0x180008607  lea     rax, ??_7CIISWebService@@6BIPrivateUnknown@@@; const CIISWebService::`vftable'{for `IPrivateUnknown'}
0x18000860e  mov     [rcx+8], rax
0x180008612  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x180008619  mov     [rcx+10h], rax
0x18000861d  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x180008624  mov     [rcx+18h], rax
0x180008628  lea     rax, ??_7CIISWebService@@6BINonDelegatingUnknown@@@; const CIISWebService::`vftable'{for `INonDelegatingUnknown'}
0x18000862f  mov     [rcx+20h], rax
0x180008633  mov     rcx, [rcx+40h]; pStr
0x180008637  test    rcx, rcx
0x18000863a  jz      short loc_180008642
0x18000863c  call    cs:__imp_FreeADsStr
0x180008642  mov     rcx, [rdi+48h]; pStr
0x180008646  test    rcx, rcx
0x180008649  jz      short loc_180008651
0x18000864b  call    cs:__imp_FreeADsStr
0x180008651  mov     rbx, [rdi+58h]
0x180008655  test    rbx, rbx
0x180008658  jz      short loc_18000866A
0x18000865a  mov     rcx, rbx; this
0x18000865d  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x180008662  mov     rcx, rbx; Block
0x180008665  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000866a  mov     rcx, [rdi+78h]
0x18000866e  test    rcx, rcx
0x180008671  jz      short loc_18000867F
0x180008673  mov     rax, [rcx]
0x180008676  mov     rax, [rax+10h]
0x18000867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000867f  lea     rcx, [rdi+60h]; unsigned __int16 **
0x180008683  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180008688  lea     rdx, [rdi+74h]; unsigned int *
0x18000868c  lea     rcx, [rdi+68h]; unsigned __int16 **
0x180008690  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180008695  lea     rcx, [rdi+2Ch]; this
0x180008699  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x18000869e  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x1800086a5  mov     rbx, [rsp+28h+arg_0]
0x1800086aa  add     rsp, 20h
0x1800086ae  pop     rdi
0x1800086af  retn
```
