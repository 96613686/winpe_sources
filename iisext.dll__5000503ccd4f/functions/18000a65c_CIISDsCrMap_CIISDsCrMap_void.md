# CIISDsCrMap::~CIISDsCrMap(void)

- ea: `0x18000a65c`
- end: `0x18000a72e`
- name: `??1CIISDsCrMap@@QEAA@XZ`
- size: `210`
- prototype: `void __fastcall(CIISDsCrMap *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000a8b0`
- `0x18000a94c`
- `0x18000d1d0`

## callees

- `0x180001048`
- `0x1800049a0`
- `0x1800050a8`
- `0x18000a65c`
- `0x18000dee4`
- `0x18000df38`
- `0x180012010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000a6ba`
- `KERNEL32!LocalFree` at `0x18000a6c9`
- `KERNEL32!LocalFree` at `0x18000a6ba`
- `KERNEL32!LocalFree` at `0x18000a6c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6a8`

## pseudocode

```c
void __fastcall CIISDsCrMap::~CIISDsCrMap(CIISDsCrMap *this)
{
  OLECHAR *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rbx
  __int64 v6; // rcx

  *(_QWORD *)this = &CIISDsCrMap::`vftable'{for `IISDsCrMap'};
  *((_QWORD *)this + 1) = &CIISDsCrMap::`vftable'{for `IPrivateUnknown'};
  *((_QWORD *)this + 2) = &CIISDsCrMap::`vftable'{for `IPrivateDispatch'};
  *((_QWORD *)this + 3) = &CIISDsCrMap::`vftable'{for `IADsExtension'};
  *((_QWORD *)this + 4) = &CIISDsCrMap::`vftable'{for `INonDelegatingUnknown'};
  v2 = (OLECHAR *)*((_QWORD *)this + 9);
  if ( v2 )
    SysFreeString(v2);
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 )
    LocalFree(v3);
  v4 = (void *)*((_QWORD *)this + 15);
  if ( v4 )
    LocalFree(v4);
  v5 = (void *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    CAggregateeDispMgr::~CAggregateeDispMgr(*((CAggregateeDispMgr **)this + 14));
    operator delete(v5);
  }
  v6 = *((_QWORD *)this + 7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  CCredentials::FreeUserName((unsigned __int16 **)this + 10);
  CCredentials::FreePassword((LPVOID *)this + 11, (unsigned int *)this + 25);
  SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT((CIISDsCrMap *)((char *)this + 44));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x18000a65c  mov     [rsp+arg_0], rbx
0x18000a661  push    rdi
0x18000a662  sub     rsp, 20h
0x18000a666  lea     rax, ??_7CIISDsCrMap@@6BIISDsCrMap@@@; const CIISDsCrMap::`vftable'{for `IISDsCrMap'}
0x18000a66d  mov     rdi, rcx
0x18000a670  mov     [rcx], rax
0x18000a673  lea     rax, ??_7CIISDsCrMap@@6BIPrivateUnknown@@@; const CIISDsCrMap::`vftable'{for `IPrivateUnknown'}
0x18000a67a  mov     [rcx+8], rax
0x18000a67e  lea     rax, ??_7CIISDsCrMap@@6BIPrivateDispatch@@@; const CIISDsCrMap::`vftable'{for `IPrivateDispatch'}
0x18000a685  mov     [rcx+10h], rax
0x18000a689  lea     rax, ??_7CIISDsCrMap@@6BIADsExtension@@@; const CIISDsCrMap::`vftable'{for `IADsExtension'}
0x18000a690  mov     [rcx+18h], rax
0x18000a694  lea     rax, ??_7CIISDsCrMap@@6BINonDelegatingUnknown@@@; const CIISDsCrMap::`vftable'{for `INonDelegatingUnknown'}
0x18000a69b  mov     [rcx+20h], rax
0x18000a69f  mov     rcx, [rcx+48h]; bstrString
0x18000a6a3  test    rcx, rcx
0x18000a6a6  jz      short loc_18000A6AE
0x18000a6a8  call    cs:__imp_SysFreeString
0x18000a6ae  mov     rcx, [rdi+80h]; hMem
0x18000a6b5  test    rcx, rcx
0x18000a6b8  jz      short loc_18000A6C0
0x18000a6ba  call    cs:__imp_LocalFree
0x18000a6c0  mov     rcx, [rdi+78h]; hMem
0x18000a6c4  test    rcx, rcx
0x18000a6c7  jz      short loc_18000A6CF
0x18000a6c9  call    cs:__imp_LocalFree
0x18000a6cf  mov     rbx, [rdi+70h]
0x18000a6d3  test    rbx, rbx
0x18000a6d6  jz      short loc_18000A6E8
0x18000a6d8  mov     rcx, rbx; this
0x18000a6db  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x18000a6e0  mov     rcx, rbx; Block
0x18000a6e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a6e8  mov     rcx, [rdi+38h]
0x18000a6ec  test    rcx, rcx
0x18000a6ef  jz      short loc_18000A6FD
0x18000a6f1  mov     rax, [rcx]
0x18000a6f4  mov     rax, [rax+10h]
0x18000a6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fd  lea     rcx, [rdi+50h]; unsigned __int16 **
0x18000a701  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000a706  lea     rdx, [rdi+64h]; unsigned int *
0x18000a70a  lea     rcx, [rdi+58h]; unsigned __int16 **
0x18000a70e  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x18000a713  lea     rcx, [rdi+2Ch]; this
0x18000a717  call    ??1SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)
0x18000a71c  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x18000a723  mov     rbx, [rsp+28h+arg_0]
0x18000a728  add     rsp, 20h
0x18000a72c  pop     rdi
0x18000a72d  retn
```
