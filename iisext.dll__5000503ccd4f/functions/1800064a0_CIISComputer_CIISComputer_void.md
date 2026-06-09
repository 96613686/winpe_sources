# CIISComputer::~CIISComputer(void)

- ea: `0x1800064a0`
- end: `0x180006560`
- name: `??1CIISComputer@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(CIISComputer *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006570`
- `0x1800065a0`
- `0x18000683c`
- `0x180006eb0`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x1800064a0`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x1800064ec`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800064fb`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800064ec`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800064fb`

## pseudocode

```c
void __fastcall CIISComputer::~CIISComputer(CIISComputer *this)
{
  WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  void *v4; // rbx
  __int64 v5; // rcx

  *(_QWORD *)this = &CIISComputer::`vftable'{for `IISComputer2'};
  *((_QWORD *)this + 1) = &CIISComputer::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApp::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApp::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISComputer::`vftable'{for `INonDelegatingUnknown'};
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
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISComputer *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x1800064a0  mov     [rsp+arg_0], rbx
0x1800064a5  push    rdi
0x1800064a6  sub     rsp, 20h
0x1800064aa  lea     rax, ??_7CIISComputer@@6BIISComputer2@@@; const CIISComputer::`vftable'{for `IISComputer2'}
0x1800064b1  mov     rdi, rcx
0x1800064b4  mov     [rcx], rax
0x1800064b7  lea     rax, ??_7CIISComputer@@6BIPrivateUnknown@@@; const CIISComputer::`vftable'{for `IPrivateUnknown'}
0x1800064be  mov     [rcx+8], rax
0x1800064c2  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x1800064c9  mov     [rcx+10h], rax
0x1800064cd  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x1800064d4  mov     [rcx+18h], rax
0x1800064d8  lea     rax, ??_7CIISComputer@@6BINonDelegatingUnknown@@@; const CIISComputer::`vftable'{for `INonDelegatingUnknown'}
0x1800064df  mov     [rcx+20h], rax
0x1800064e3  mov     rcx, [rcx+40h]; pStr
0x1800064e7  test    rcx, rcx
0x1800064ea  jz      short loc_1800064F2
0x1800064ec  call    cs:__imp_FreeADsStr
0x1800064f2  mov     rcx, [rdi+48h]; pStr
0x1800064f6  test    rcx, rcx
0x1800064f9  jz      short loc_180006501
0x1800064fb  call    cs:__imp_FreeADsStr
0x180006501  mov     rbx, [rdi+58h]
0x180006505  test    rbx, rbx
0x180006508  jz      short loc_18000651A
0x18000650a  mov     rcx, rbx; this
0x18000650d  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x180006512  mov     rcx, rbx; Block
0x180006515  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000651a  mov     rcx, [rdi+78h]
0x18000651e  test    rcx, rcx
0x180006521  jz      short loc_18000652F
0x180006523  mov     rax, [rcx]
0x180006526  mov     rax, [rax+10h]
0x18000652a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652f  lea     rcx, [rdi+60h]; unsigned __int16 **
0x180006533  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180006538  lea     rdx, [rdi+74h]; unsigned int *
0x18000653c  lea     rcx, [rdi+68h]; unsigned __int16 **
0x180006540  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180006545  lea     rcx, [rdi+2Ch]; this
0x180006549  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x18000654e  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180006555  mov     rbx, [rsp+28h+arg_0]
0x18000655a  add     rsp, 20h
0x18000655e  pop     rdi
0x18000655f  retn
```
