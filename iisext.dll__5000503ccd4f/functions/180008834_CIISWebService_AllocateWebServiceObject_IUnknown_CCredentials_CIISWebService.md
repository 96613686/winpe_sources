# CIISWebService::AllocateWebServiceObject(IUnknown *,CCredentials &,CIISWebService * *)

- ea: `0x180008834`
- end: `0x1800089e0`
- name: `?AllocateWebServiceObject@CIISWebService@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z`
- size: `428`
- prototype: `static int(struct IUnknown *, struct CCredentials *, struct CIISWebService **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180008fc0`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800049a0`
- `0x180004c2c`
- `0x180004ef8`
- `0x1800085f0`
- `0x180008834`
- `0x18000dea0`
- `0x18000e0d4`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::AllocateWebServiceObject(
        struct IUnknown *a1,
        struct CCredentials *a2,
        struct CIISWebService **a3)
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
    *v8 = &CIISWebService::`vftable'{for `IISWebService'};
    v8[7] = 0;
    v8[1] = &CIISWebService::`vftable'{for `IPrivateUnknown'};
    v8[8] = 0;
    v8[2] = &CIISApp::`vftable'{for `IPrivateDispatch'};
    v8[9] = 0;
    v8[3] = &CIISApp::`vftable'{for `IADsExtension'};
    *((_DWORD *)v8 + 20) = 0;
    v8[4] = &CIISWebService::`vftable'{for `INonDelegatingUnknown'};
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
                        &IID_IISWebService,
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
          *a3 = (struct CIISWebService *)v8;
          return result;
        }
      }
      CAggregateeDispMgr::~CAggregateeDispMgr((CAggregateeDispMgr *)v9);
      operator delete(v9);
    }
    CIISWebService::~CIISWebService((CIISWebService *)v8);
    operator delete(v8);
  }
  return (unsigned int)TypeInfoEntry;
}

```

## disassembly

```asm
0x180008834  mov     [rsp+arg_0], rbx
0x180008839  mov     [rsp+arg_8], rbp
0x18000883e  push    rsi
0x18000883f  push    rdi
0x180008840  push    r12
0x180008842  push    r14
0x180008844  push    r15
0x180008846  sub     rsp, 30h
0x18000884a  mov     r14, rcx
0x18000884d  xor     r12d, r12d
0x180008850  mov     ecx, 80h; Size
0x180008855  mov     [rsp+58h+arg_18], r12
0x18000885a  mov     r15, r8
0x18000885d  mov     rbp, rdx
0x180008860  mov     esi, 8007000Eh
0x180008865  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000886a  mov     rbx, rax
0x18000886d  test    rax, rax
0x180008870  jz      loc_1800089C7
0x180008876  mov     dword ptr [rax+28h], 1
0x18000887d  lock inc cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180008884  lea     rax, ??_7INonDelegatingUnknown@@6B@; const INonDelegatingUnknown::`vftable'
0x18000888b  lea     rcx, [rbx+2Ch]; this
0x18000888f  mov     [rbx+20h], rax
0x180008893  call    ??0SERVER_CACHE_CLIENT@@QEAA@XZ; SERVER_CACHE_CLIENT::SERVER_CACHE_CLIENT(void)
0x180008898  lea     rax, ??_7CIISWebService@@6BIISWebService@@@; const CIISWebService::`vftable'{for `IISWebService'}
0x18000889f  mov     [rbx+30h], r12
0x1800088a3  mov     [rbx], rax
0x1800088a6  lea     rcx, [rbx+60h]; this
0x1800088aa  lea     rax, ??_7CIISWebService@@6BIPrivateUnknown@@@; const CIISWebService::`vftable'{for `IPrivateUnknown'}
0x1800088b1  mov     [rbx+38h], r12
0x1800088b5  mov     [rbx+8], rax
0x1800088b9  xor     r9d, r9d; unsigned int
0x1800088bc  lea     rax, ??_7CIISApp@@6BIPrivateDispatch@@@; const CIISApp::`vftable'{for `IPrivateDispatch'}
0x1800088c3  mov     [rbx+40h], r12
0x1800088c7  mov     [rbx+10h], rax
0x1800088cb  xor     r8d, r8d; unsigned __int16 *
0x1800088ce  lea     rax, ??_7CIISApp@@6BIADsExtension@@@; const CIISApp::`vftable'{for `IADsExtension'}
0x1800088d5  mov     [rbx+48h], r12
0x1800088d9  mov     [rbx+18h], rax
0x1800088dd  xor     edx, edx; pStr
0x1800088df  lea     rax, ??_7CIISWebService@@6BINonDelegatingUnknown@@@; const CIISWebService::`vftable'{for `INonDelegatingUnknown'}
0x1800088e6  mov     [rbx+50h], r12d
0x1800088ea  mov     [rbx+20h], rax
0x1800088ee  mov     [rbx+58h], r12
0x1800088f2  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x1800088f7  lea     ecx, [r12+38h]; Size
0x1800088fc  mov     [rbx+78h], r12
0x180008900  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008905  mov     rdi, rax
0x180008908  test    rax, rax
0x18000890b  jz      loc_1800089B7
0x180008911  lea     rax, ??_7CAggregateeDispMgr@@6B@; const CAggregateeDispMgr::`vftable'
0x180008918  mov     [rdi+10h], r12
0x18000891c  mov     r9, rbx; void *
0x18000891f  mov     [rdi], rax
0x180008922  lea     r8, IID_IISWebService; struct _GUID *
0x180008929  mov     [rdi+18h], r12
0x18000892d  lea     rdx, LIBID_IISExt; struct _GUID *
0x180008934  mov     [rdi+8], r12d
0x180008938  mov     rcx, rdi; this
0x18000893b  mov     [rdi+20h], r12
0x18000893f  mov     [rdi+28h], r12
0x180008943  mov     [rdi+30h], r12
0x180008947  call    ?LoadTypeInfoEntry@CAggregateeDispMgr@@QEAAJAEBU_GUID@@0PEAXJ@Z; CAggregateeDispMgr::LoadTypeInfoEntry(_GUID const &,_GUID const &,void *,long)
0x18000894c  mov     esi, eax
0x18000894e  test    eax, eax
0x180008950  js      short loc_1800089A7
0x180008952  mov     rax, [r14]
0x180008955  lea     r8, [rsp+58h+arg_18]
0x18000895a  lea     rdx, IID_IADs
0x180008961  mov     rcx, r14
0x180008964  mov     rax, [rax]
0x180008967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000896c  mov     esi, eax
0x18000896e  test    eax, eax
0x180008970  js      short loc_1800089A7
0x180008972  mov     rcx, [rsp+58h+arg_18]
0x180008977  mov     rax, [rcx]
0x18000897a  mov     rax, [rax+10h]
0x18000897e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008983  mov     rax, [rsp+58h+arg_18]
0x180008988  lea     rcx, [rbx+60h]; this
0x18000898c  mov     rdx, rbp; struct CCredentials *
0x18000898f  mov     [rbx+38h], rax
0x180008993  mov     [rbx+30h], r14
0x180008997  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x18000899c  xor     eax, eax
0x18000899e  mov     [rbx+58h], rdi
0x1800089a2  mov     [r15], rbx
0x1800089a5  jmp     short loc_1800089C9
0x1800089a7  mov     rcx, rdi; this
0x1800089aa  call    ??1CAggregateeDispMgr@@QEAA@XZ; CAggregateeDispMgr::~CAggregateeDispMgr(void)
0x1800089af  mov     rcx, rdi; Block
0x1800089b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800089b7  mov     rcx, rbx; this
0x1800089ba  call    ??1CIISWebService@@QEAA@XZ; CIISWebService::~CIISWebService(void)
0x1800089bf  mov     rcx, rbx; Block
0x1800089c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800089c7  mov     eax, esi
0x1800089c9  mov     rbx, [rsp+58h+arg_0]
0x1800089ce  mov     rbp, [rsp+58h+arg_8]
0x1800089d3  add     rsp, 30h
0x1800089d7  pop     r15
0x1800089d9  pop     r14
0x1800089db  pop     r12
0x1800089dd  pop     rdi
0x1800089de  pop     rsi
0x1800089df  retn
```
