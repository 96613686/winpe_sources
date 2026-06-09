# CIISApplicationPool::~CIISApplicationPool(void)

- ea: `0x180007020`
- end: `0x1800070f2`
- name: `??1CIISApplicationPool@@QEAA@XZ`
- size: `210`
- prototype: `void __fastcall(CIISApplicationPool *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180007270`
- `0x1800072a0`
- `0x18000745c`
- `0x180007e20`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x180007020`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x18000706c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000707b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000708a`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000706c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000707b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000708a`

## pseudocode

```c
void __fastcall CIISApplicationPool::~CIISApplicationPool(CIISApplicationPool *this)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  WCHAR *v4; // rcx
  void *v5; // rbx
  __int64 v6; // rcx

  *(_QWORD *)this = &CIISApplicationPool::`vftable'{for `IISApplicationPool'};
  *((_QWORD *)this + 1) = &CIISApplicationPool::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApplicationPool::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApplicationPool::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISApplicationPool::`vftable'{for `INonDelegatingUnknown'};
  v2 = (WCHAR *)*((_QWORD *)this + 8);
  if ( v2 )
    FreeADsStr(v2);
  v3 = (WCHAR *)*((_QWORD *)this + 9);
  if ( v3 )
    FreeADsStr(v3);
  v4 = (WCHAR *)*((_QWORD *)this + 10);
  if ( v4 )
    FreeADsStr(v4);
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    CAggregateeDispMgr::~CAggregateeDispMgr(*((CAggregateeDispMgr **)this + 12));
    operator delete(v5);
  }
  v6 = *((_QWORD *)this + 16);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  CCredentials::FreeUserName((unsigned __int16 **)this + 13);
  CCredentials::FreePassword((LPVOID *)this + 14, (unsigned int *)this + 31);
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISApplicationPool *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x180007020  mov     [rsp+arg_0], rbx
0x180007025  push    rdi
0x180007026  sub     rsp, 20h
0x18000702a  lea     rax, ??_7CIISApplicationPool@@6BIISApplicationPool@@@; const CIISApplicationPool::`vftable'{for `IISApplicationPool'}
0x180007031  mov     rdi, rcx
0x180007034  mov     [rcx], rax
0x180007037  lea     rax, ??_7CIISApplicationPool@@6BIPrivateUnknown@@@; const CIISApplicationPool::`vftable'{for `IPrivateUnknown'}
0x18000703e  mov     [rcx+8], rax
0x180007042  lea     rax, ??_7CIISApplicationPool@@6BIPrivateDispatch@@@; const CIISApplicationPool::`vftable'{for `IPrivateDispatch'}
0x180007049  mov     [rcx+10h], rax
0x18000704d  lea     rax, ??_7CIISApplicationPool@@6BIADsExtension@@@; const CIISApplicationPool::`vftable'{for `IADsExtension'}
0x180007054  mov     [rcx+18h], rax
0x180007058  lea     rax, ??_7CIISApplicationPool@@6BINonDelegatingUnknown@@@; const CIISApplicationPool::`vftable'{for `INonDelegatingUnknown'}
0x18000705f  mov     [rcx+20h], rax
0x180007063  mov     rcx, [rcx+40h]; pStr
0x180007067  test    rcx, rcx
0x18000706a  jz      short loc_180007072
0x18000706c  call    cs:__imp_FreeADsStr
0x180007072  mov     rcx, [rdi+48h]; pStr
0x180007076  test    rcx, rcx
0x180007079  jz      short loc_180007081
0x18000707b  call    cs:__imp_FreeADsStr
0x180007081  mov     rcx, [rdi+50h]; pStr
0x180007085  test    rcx, rcx
0x180007088  jz      short loc_180007090
0x18000708a  call    cs:__imp_FreeADsStr
0x180007090  mov     rbx, [rdi+60h]
0x180007094  test    rbx, rbx
0x180007097  jz      short loc_1800070A9
0x180007099  mov     rcx, rbx; this
0x18000709c  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x1800070a1  mov     rcx, rbx; Block
0x1800070a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800070a9  mov     rcx, [rdi+80h]
0x1800070b0  test    rcx, rcx
0x1800070b3  jz      short loc_1800070C1
0x1800070b5  mov     rax, [rcx]
0x1800070b8  mov     rax, [rax+10h]
0x1800070bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c1  lea     rcx, [rdi+68h]; unsigned __int16 **
0x1800070c5  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800070ca  lea     rdx, [rdi+7Ch]; unsigned int *
0x1800070ce  lea     rcx, [rdi+70h]; unsigned __int16 **
0x1800070d2  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800070d7  lea     rcx, [rdi+2Ch]; this
0x1800070db  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x1800070e0  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x1800070e7  mov     rbx, [rsp+28h+arg_0]
0x1800070ec  add     rsp, 20h
0x1800070f0  pop     rdi
0x1800070f1  retn
```
