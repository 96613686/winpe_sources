# CIISComputer::AllocateComputerObject(IUnknown *,CCredentials &,CIISComputer * *)

- ea: `0x1800065a0`
- end: `0x18000674c`
- name: `?AllocateComputerObject@CIISComputer@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z`
- size: `428`
- prototype: `__int64 __fastcall(struct IUnknown *, struct CCredentials *, struct CIISComputer **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000683c`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800049a0`
- `0x180004c2c`
- `0x180004ef8`
- `0x1800064a0`
- `0x1800065a0`
- `0x18000dea0`
- `0x18000e0d4`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::AllocateComputerObject(
        struct IUnknown *a1,
        struct CCredentials *a2,
        struct CIISComputer **a3)
{
  int TypeInfoEntry; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  TypeInfoEntry = -2147024882;
  v7 = operator new(0x80u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 10) = 1;
    _InterlockedIncrement(&ModuleCount::m_Count);
    v7[4] = &INonDelegatingUnknown::`vftable';
    SERVER_CACHE_CLIENT::SERVER_CACHE_CLIENT((SERVER_CACHE_CLIENT *)((char *)v7 + 44));
    v8[6] = 0;
    *v8 = &CIISComputer::`vftable'{for `IISComputer2'};
    v8[7] = 0;
    v8[1] = &CIISComputer::`vftable'{for `IPrivateUnknown'};
    v8[8] = 0;
    v8[2] = &CIISApp::`vftable'{for `IPrivateDispatch'};
    v8[9] = 0;
    v8[3] = &CIISApp::`vftable'{for `IADsExtension'};
    *((_DWORD *)v8 + 20) = 0;
    v8[4] = &CIISComputer::`vftable'{for `INonDelegatingUnknown'};
    v8[11] = 0;
    CCredentials::Initialize((CCredentials *)(v8 + 12), 0, 0, 0);
    v8[15] = 0;
    v9 = operator new(0x38u);
    if ( v9 )
    {
      v9[2] = 0;
      *v9 = &CAggregateeDispMgr::`vftable';
      v9[3] = 0;
      *((_DWORD *)v9 + 2) = 0;
      v9[4] = 0;
      v9[5] = 0;
      v9[6] = 0;
      TypeInfoEntry = CAggregateeDispMgr::LoadTypeInfoEntry(
                        (CAggregateeDispMgr *)v9,
                        &LIBID_IISExt,
                        &IID_IISComputer2,
                        v8,
                        v11);
      if ( TypeInfoEntry >= 0 )
      {
        TypeInfoEntry = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                          a1,
                          &IID_IADs,
                          &v12);
        if ( TypeInfoEntry >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v8[7] = v12;
          v8[6] = a1;
          CCredentials::operator=((CCredentials *)(v8 + 12), a2);
          result = 0;
          v8[11] = v9;
          *a3 = (struct CIISComputer *)v8;
          return result;
        }
      }
      CAggregateeDispMgr::~CAggregateeDispMgr((CAggregateeDispMgr *)v9);
      operator delete(v9);
    }
    CIISComputer::~CIISComputer((CIISComputer *)v8);
    operator delete(v8);
  }
  return (unsigned int)TypeInfoEntry;
}

```

## disassembly

```asm
0x1800065a0  mov     [rsp+arg_0], rbx
0x1800065a5  mov     [rsp+arg_8], rbp
0x1800065aa  push    rsi
0x1800065ab  push    rdi
0x1800065ac  push    r12
0x1800065ae  push    r14
0x1800065b0  push    r15
0x1800065b2  sub     rsp, 30h
0x1800065b6  mov     r14, rcx
0x1800065b9  xor     r12d, r12d
0x1800065bc  mov     ecx, 80h; Size
0x1800065c1  mov     [rsp+58h+arg_18], r12
0x1800065c6  mov     r15, r8
0x1800065c9  mov     rbp, rdx
0x1800065cc  mov     esi, 8007000Eh
0x1800065d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800065d6  mov     rbx, rax
0x1800065d9  test    rax, rax
0x1800065dc  jz      loc_180006733
0x1800065e2  mov     dword ptr [rax+28h], 1
0x1800065e9  lock inc cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x1800065f0  lea     rax, ??_7INonDelegatingUnknown@@6B@; const INonDelegatingUnknown::`vftable'
0x1800065f7  lea     rcx, [rbx+2Ch]; this
0x1800065fb  mov     [rbx+20h], rax
0x1800065ff  call    ??0SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::SERVER_CACHE_CLIENT(void)
0x180006604  lea     rax, ??_7CIISComputer@@6BIISComputer2@@@; const CIISComputer::`vftable'{for `IISComputer2'}
0x18000660b  mov     [rbx+30h], r12
0x18000660f  mov     [rbx], rax
0x180006612  lea     rcx, [rbx+60h]; this
0x180006616  lea     rax, ??_7CIISComputer@@6BIPrivateUnknown@@@; const CIISComputer::`vftable'{for `IPrivateUnknown'}
0x18000661d  mov     [rbx+38h], r12
0x180006621  mov     [rbx+8], rax
0x180006625  xor     r9d, r9d; unsigned int
0x180006628  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x18000662f  mov     [rbx+40h], r12
0x180006633  mov     [rbx+10h], rax
0x180006637  xor     r8d, r8d; unsigned __int16 *
0x18000663a  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x180006641  mov     [rbx+48h], r12
0x180006645  mov     [rbx+18h], rax
0x180006649  xor     edx, edx; pStr
0x18000664b  lea     rax, ??_7CIISComputer@@6BINonDelegatingUnknown@@@; const CIISComputer::`vftable'{for `INonDelegatingUnknown'}
0x180006652  mov     [rbx+50h], r12d
0x180006656  mov     [rbx+20h], rax
0x18000665a  mov     [rbx+58h], r12
0x18000665e  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180006663  lea     ecx, [r12+38h]; Size
0x180006668  mov     [rbx+78h], r12
0x18000666c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006671  mov     rdi, rax
0x180006674  test    rax, rax
0x180006677  jz      loc_180006723
0x18000667d  lea     rax, ??_7CAggregateeDispMgr@@6B@; const CAggregateeDispMgr::`vftable'
0x180006684  mov     [rdi+10h], r12
0x180006688  mov     r9, rbx; void *
0x18000668b  mov     [rdi], rax
0x18000668e  lea     r8, IID_IISComputer2; struct _GUID *
0x180006695  mov     [rdi+18h], r12
0x180006699  lea     rdx, LIBID_IISExt; struct _GUID *
0x1800066a0  mov     [rdi+8], r12d
0x1800066a4  mov     rcx, rdi; this
0x1800066a7  mov     [rdi+20h], r12
0x1800066ab  mov     [rdi+28h], r12
0x1800066af  mov     [rdi+30h], r12
0x1800066b3  call    ?LoadTypeInfoEntry@CAggregateeDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z; CAggregateeDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)
0x1800066b8  mov     esi, eax
0x1800066ba  test    eax, eax
0x1800066bc  js      short loc_180006713
0x1800066be  mov     rax, [r14]
0x1800066c1  lea     r8, [rsp+58h+arg_18]
0x1800066c6  lea     rdx, IID_IADs
0x1800066cd  mov     rcx, r14
0x1800066d0  mov     rax, [rax]
0x1800066d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d8  mov     esi, eax
0x1800066da  test    eax, eax
0x1800066dc  js      short loc_180006713
0x1800066de  mov     rcx, [rsp+58h+arg_18]
0x1800066e3  mov     rax, [rcx]
0x1800066e6  mov     rax, [rax+10h]
0x1800066ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ef  mov     rax, [rsp+58h+arg_18]
0x1800066f4  lea     rcx, [rbx+60h]; this
0x1800066f8  mov     rdx, rbp; struct CCredentials *
0x1800066fb  mov     [rbx+38h], rax
0x1800066ff  mov     [rbx+30h], r14
0x180006703  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x180006708  xor     eax, eax
0x18000670a  mov     [rbx+58h], rdi
0x18000670e  mov     [r15], rbx
0x180006711  jmp     short loc_180006735
0x180006713  mov     rcx, rdi; this
0x180006716  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x18000671b  mov     rcx, rdi; Block
0x18000671e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006723  mov     rcx, rbx; this
0x180006726  call    ??1CIISComputer@@QEAA@XZ; CIISComputer::~CIISComputer(void)
0x18000672b  mov     rcx, rbx; Block
0x18000672e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006733  mov     eax, esi
0x180006735  mov     rbx, [rsp+58h+arg_0]
0x18000673a  mov     rbp, [rsp+58h+arg_8]
0x18000673f  add     rsp, 30h
0x180006743  pop     r15
0x180006745  pop     r14
0x180006747  pop     r12
0x180006749  pop     rdi
0x18000674a  pop     rsi
0x18000674b  retn
```
