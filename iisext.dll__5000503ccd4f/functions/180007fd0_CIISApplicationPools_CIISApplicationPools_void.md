# CIISApplicationPools::~CIISApplicationPools(void)

- ea: `0x180007fd0`
- end: `0x180008090`
- name: `??1CIISApplicationPools@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(CIISApplicationPools *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800080a0`
- `0x1800080d0`
- `0x18000828c`
- `0x180008580`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x180007fd0`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x18000801c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000802b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000801c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000802b`

## pseudocode

```c
void __fastcall CIISApplicationPools::~CIISApplicationPools(CIISApplicationPools *this)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  void *v4; // rbx
  __int64 v5; // rcx

  *(_QWORD *)this = &CIISApplicationPools::`vftable'{for `IISApplicationPools'};
  *((_QWORD *)this + 1) = &CIISApplicationPools::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApp::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApp::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISApplicationPools::`vftable'{for `INonDelegatingUnknown'};
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
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISApplicationPools *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp+arg_0], rbx
0x180007fd5  push    rdi
0x180007fd6  sub     rsp, 20h
0x180007fda  lea     rax, ??_7CIISApplicationPools@@6BIISApplicationPools@@@; const CIISApplicationPools::`vftable'{for `IISApplicationPools'}
0x180007fe1  mov     rdi, rcx
0x180007fe4  mov     [rcx], rax
0x180007fe7  lea     rax, ??_7CIISApplicationPools@@6BIPrivateUnknown@@@; const CIISApplicationPools::`vftable'{for `IPrivateUnknown'}
0x180007fee  mov     [rcx+8], rax
0x180007ff2  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x180007ff9  mov     [rcx+10h], rax
0x180007ffd  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x180008004  mov     [rcx+18h], rax
0x180008008  lea     rax, ??_7CIISApplicationPools@@6BINonDelegatingUnknown@@@; const CIISApplicationPools::`vftable'{for `INonDelegatingUnknown'}
0x18000800f  mov     [rcx+20h], rax
0x180008013  mov     rcx, [rcx+40h]; pStr
0x180008017  test    rcx, rcx
0x18000801a  jz      short loc_180008022
0x18000801c  call    cs:__imp_FreeADsStr
0x180008022  mov     rcx, [rdi+48h]; pStr
0x180008026  test    rcx, rcx
0x180008029  jz      short loc_180008031
0x18000802b  call    cs:__imp_FreeADsStr
0x180008031  mov     rbx, [rdi+58h]
0x180008035  test    rbx, rbx
0x180008038  jz      short loc_18000804A
0x18000803a  mov     rcx, rbx; this
0x18000803d  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x180008042  mov     rcx, rbx; Block
0x180008045  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000804a  mov     rcx, [rdi+78h]
0x18000804e  test    rcx, rcx
0x180008051  jz      short loc_18000805F
0x180008053  mov     rax, [rcx]
0x180008056  mov     rax, [rax+10h]
0x18000805a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805f  lea     rcx, [rdi+60h]; unsigned __int16 **
0x180008063  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180008068  lea     rdx, [rdi+74h]; unsigned int *
0x18000806c  lea     rcx, [rdi+68h]; unsigned __int16 **
0x180008070  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180008075  lea     rcx, [rdi+2Ch]; this
0x180008079  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x18000807e  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180008085  mov     rbx, [rsp+28h+arg_0]
0x18000808a  add     rsp, 20h
0x18000808e  pop     rdi
0x18000808f  retn
```
