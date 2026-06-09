# CIISApp::~CIISApp(void)

- ea: `0x180004f98`
- end: `0x1800050a0`
- name: `??1CIISApp@@QEAA@XZ`
- size: `264`
- prototype: `void __fastcall(CIISApp *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180005290`
- `0x180005310`
- `0x180005a58`
- `0x180006100`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x180004f98`
- `0x1800050a8`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x18000502c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000503b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000502c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000503b`

## pseudocode

```c
void __fastcall CIISApp::~CIISApp(CIISApp *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  WCHAR *v5; // rcx
  WCHAR *v6; // rcx
  void *v7; // rbx
  __int64 v8; // rcx

  *(_QWORD *)this = &CIISApp::`vftable'{for `IISApp3'};
  *((_QWORD *)this + 1) = &CIISApp::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISApp::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISApp::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISApp::`vftable'{for `INonDelegatingUnknown'};
  v2 = *((_QWORD *)this + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (WCHAR *)*((_QWORD *)this + 8);
  if ( v5 )
    FreeADsStr(v5);
  v6 = (WCHAR *)*((_QWORD *)this + 9);
  if ( v6 )
    FreeADsStr(v6);
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
  {
    CAggregateeDispMgr::~CAggregateeDispMgr(*((CAggregateeDispMgr **)this + 11));
    operator delete(v7);
  }
  v8 = *((_QWORD *)this + 15);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  CCredentials::FreeUserName((unsigned __int16 **)this + 12);
  CCredentials::FreePassword((LPVOID *)this + 13, (unsigned int *)this + 29);
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISApp *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x180004f98  mov     [rsp+arg_0], rbx
0x180004f9d  push    rdi
0x180004f9e  sub     rsp, 20h
0x180004fa2  lea     rax, ??_7CIISApp@@6BIISApp3@@@; const CIISApp::`vftable'{for `IISApp3'}
0x180004fa9  mov     rdi, rcx
0x180004fac  mov     [rcx], rax
0x180004faf  lea     rax, ??_7CIISApp@@6BIPrivateUnknown@@@; const CIISApp::`vftable'{for `IPrivateUnknown'}
0x180004fb6  mov     [rcx+8], rax
0x180004fba  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x180004fc1  mov     [rcx+10h], rax
0x180004fc5  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x180004fcc  mov     [rcx+18h], rax
0x180004fd0  lea     rax, ??_7CIISApp@@6BINonDelegatingUnknown@@@; const CIISApp::`vftable'{for `INonDelegatingUnknown'}
0x180004fd7  mov     [rcx+20h], rax
0x180004fdb  mov     rcx, [rcx+80h]
0x180004fe2  test    rcx, rcx
0x180004fe5  jz      short loc_180004FF3
0x180004fe7  mov     rax, [rcx]
0x180004fea  mov     rax, [rax+10h]
0x180004fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff3  mov     rcx, [rdi+88h]
0x180004ffa  test    rcx, rcx
0x180004ffd  jz      short loc_18000500B
0x180004fff  mov     rax, [rcx]
0x180005002  mov     rax, [rax+10h]
0x180005006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500b  mov     rcx, [rdi+90h]
0x180005012  test    rcx, rcx
0x180005015  jz      short loc_180005023
0x180005017  mov     rax, [rcx]
0x18000501a  mov     rax, [rax+10h]
0x18000501e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005023  mov     rcx, [rdi+40h]; pStr
0x180005027  test    rcx, rcx
0x18000502a  jz      short loc_180005032
0x18000502c  call    cs:__imp_FreeADsStr
0x180005032  mov     rcx, [rdi+48h]; pStr
0x180005036  test    rcx, rcx
0x180005039  jz      short loc_180005041
0x18000503b  call    cs:__imp_FreeADsStr
0x180005041  mov     rbx, [rdi+58h]
0x180005045  test    rbx, rbx
0x180005048  jz      short loc_18000505A
0x18000504a  mov     rcx, rbx; this
0x18000504d  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x180005052  mov     rcx, rbx; Block
0x180005055  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000505a  mov     rcx, [rdi+78h]
0x18000505e  test    rcx, rcx
0x180005061  jz      short loc_18000506F
0x180005063  mov     rax, [rcx]
0x180005066  mov     rax, [rax+10h]
0x18000506a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506f  lea     rcx, [rdi+60h]; unsigned __int16 **
0x180005073  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180005078  lea     rdx, [rdi+74h]; unsigned int *
0x18000507c  lea     rcx, [rdi+68h]; unsigned __int16 **
0x180005080  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180005085  lea     rcx, [rdi+2Ch]; this
0x180005089  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x18000508e  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180005095  mov     rbx, [rsp+28h+arg_0]
0x18000509a  add     rsp, 20h
0x18000509e  pop     rdi
0x18000509f  retn
```
