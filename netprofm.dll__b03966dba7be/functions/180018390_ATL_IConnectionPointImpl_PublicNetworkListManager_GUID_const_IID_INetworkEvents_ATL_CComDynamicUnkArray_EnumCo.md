# ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180018390`
- end: `0x1800185bf`
- name: `?EnumConnections@?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, char **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180006530`
- `0x1800123b0`
- `0x180012870`
- `0x180012f40`
- `0x180014f2c`
- `0x180018390`
- `0x180018ea8`
- `0x18001984c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018574`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800184df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001844c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001844c`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkEvents,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        char **a2)
{
  char **v2; // rdi
  __int64 v3; // r14
  char *v5; // rbx
  __int64 v6; // rsi
  ATL::CComDynamicUnkArray *v7; // r12
  int *v8; // r13
  unsigned __int64 v9; // rax
  _QWORD *v10; // r15
  struct IUnknown **v11; // r10
  struct IUnknown **v12; // r14
  unsigned int Cookie; // eax
  __int64 v14; // r10
  int Interface; // edi
  struct IUnknown **v18; // [rsp+98h] [rbp+10h]
  char *v19; // [rsp+A0h] [rbp+18h]
  void *v20; // [rsp+A8h] [rbp+20h]
  _QWORD *v21; // [rsp+A8h] [rbp+20h]

  v2 = a2;
  v3 = a1;
  if ( !a2 )
    return 2147500035LL;
  try
  {
    *a2 = 0;
    v20 = operator new(0x90u);
    memset_0(v20, 0, 0x90u);
    v5 = (char *)ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>((__int64)v20);
    v19 = v5;
  }
  catch ( ... )
  {
    v3 = a1;
    v2 = a2;
    v5 = v19;
  }
  if ( !v5 )
    return 2147942414LL;
  v6 = v3 + 144;
  if ( !v3 )
    v6 = 152;
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  v7 = (ATL::CComDynamicUnkArray *)(v3 + 8);
  v8 = (int *)(v3 + 16);
  v9 = 16LL * *(int *)(v3 + 16);
  if ( !is_mul_ok(*(int *)(v3 + 16), 0x10u) )
    v9 = -1;
  try
  {
    v10 = operator new[](v9);
    v21 = v10;
  }
  catch ( ... )
  {
    v2 = a2;
    v5 = v19;
    v10 = v21;
    v8 = (int *)(v3 + 16);
    v7 = (ATL::CComDynamicUnkArray *)(v3 + 8);
  }
  if ( !v10 )
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942414LL;
  }
  v11 = (struct IUnknown **)v10;
  v18 = (struct IUnknown **)v10;
  v12 = *(struct IUnknown ***)v7;
  if ( *(_QWORD *)v7 < (unsigned __int64)(*(_QWORD *)v7 + 8LL * *v8) )
  {
    do
    {
      if ( *v12 )
      {
        ((void (__fastcall *)(struct IUnknown *))(*v12)->lpVtbl->AddRef)(*v12);
        *v18 = *v12;
        Cookie = ATL::CComDynamicUnkArray::GetCookie(v7, v12);
        *(_DWORD *)(v14 + 8) = Cookie;
        v11 = (struct IUnknown **)(v14 + 16);
        v18 = v11;
      }
      ++v12;
    }
    while ( (unsigned __int64)v12 < *(_QWORD *)v7 + 8LL * *v8 );
  }
  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
    v5,
    v10,
    v11,
    0,
    2);
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  Interface = ATL::AtlInternalQueryInterface(
                v5,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                v2);
  if ( Interface < 0 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180018390  mov     [rsp+arg_8], rdx
0x180018395  mov     [rsp+arg_0], rcx
0x18001839a  push    rbx
0x18001839b  push    rsi
0x18001839c  push    rdi
0x18001839d  push    r12
0x18001839f  push    r13
0x1800183a1  push    r14
0x1800183a3  push    r15
0x1800183a5  sub     rsp, 50h
0x1800183a9  mov     rdi, rdx
0x1800183ac  mov     r14, rcx
0x1800183af  test    rdx, rdx
0x1800183b2  jnz     short loc_1800183BE
0x1800183b4  mov     eax, 80004003h
0x1800183b9  jmp     loc_1800185AF
0x1800183be  mov     qword ptr [rdx], 0
0x1800183c5  mov     [rsp+88h+arg_10], 0
0x1800183d1  mov     esi, 90h
0x1800183d6  mov     ecx, esi; Size
0x1800183d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800183dd  mov     rbx, rax
0x1800183e0  mov     [rsp+88h+arg_18], rax
0x1800183e8  mov     r8d, esi; Size
0x1800183eb  xor     edx, edx; Val
0x1800183ed  mov     rcx, rax; void *
0x1800183f0  call    memset_0
0x1800183f5  mov     rcx, rbx
0x1800183f8  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x1800183fd  mov     rbx, rax
0x180018400  mov     [rsp+88h+arg_10], rax
0x180018408  jmp     short loc_180018422
0x18001840a  mov     r14, [rsp+88h+arg_0]
0x180018412  mov     rdi, [rsp+88h+arg_8]
0x18001841a  mov     rbx, [rsp+88h+arg_10]
0x180018422  test    rbx, rbx
0x180018425  jnz     short loc_180018431
0x180018427  mov     eax, 8007000Eh
0x18001842c  jmp     loc_1800185AF
0x180018431  lea     rsi, [r14+90h]
0x180018438  mov     eax, 98h
0x18001843d  test    r14, r14
0x180018440  cmovz   rsi, rax
0x180018444  mov     [rsp+88h+var_48], rsi
0x180018449  mov     rcx, rsi; lpCriticalSection
0x18001844c  call    cs:__imp_EnterCriticalSection
0x180018452  mov     [rsp+88h+arg_18], 0
0x18001845e  lea     r12, [r14+8]
0x180018462  mov     [rsp+88h+var_50], r12
0x180018467  lea     r13, [r12+8]
0x18001846c  mov     [rsp+88h+var_58], r13
0x180018471  movsxd  rcx, dword ptr [r13+0]
0x180018475  mov     eax, 10h
0x18001847a  mul     rcx
0x18001847d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018484  cmovb   rax, rcx
0x180018488  mov     rcx, rax; unsigned __int64
0x18001848b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018490  mov     r15, rax
0x180018493  mov     [rsp+88h+arg_18], rax
0x18001849b  jmp     short loc_1800184C4
0x18001849d  mov     rdi, [rsp+88h+arg_8]
0x1800184a5  mov     rbx, [rsp+88h+arg_10]
0x1800184ad  mov     r15, [rsp+88h+arg_18]
0x1800184b5  mov     r13, [rsp+88h+var_58]
0x1800184ba  mov     r12, [rsp+88h+var_50]
0x1800184bf  mov     rsi, [rsp+88h+var_48]
0x1800184c4  test    r15, r15
0x1800184c7  jnz     short loc_1800184EA
0x1800184c9  mov     rax, [rbx]
0x1800184cc  lea     edx, [r15+1]
0x1800184d0  mov     rcx, rbx
0x1800184d3  mov     rax, [rax+38h]
0x1800184d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184dc  mov     rcx, rsi; lpCriticalSection
0x1800184df  call    cs:__imp_LeaveCriticalSection
0x1800184e5  jmp     loc_180018427
0x1800184ea  mov     r10, r15
0x1800184ed  mov     [rsp+88h+arg_8], r15
0x1800184f5  mov     r14, [r12]
0x1800184f9  movsxd  rax, dword ptr [r13+0]
0x1800184fd  lea     rcx, [r14+rax*8]
0x180018501  cmp     r14, rcx
0x180018504  jnb     short loc_180018558
0x180018506  mov     rcx, [r14]
0x180018509  test    rcx, rcx
0x18001850c  jz      short loc_180018543
0x18001850e  mov     rax, [rcx]
0x180018511  mov     rax, [rax+8]
0x180018515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851a  mov     rax, [r14]
0x18001851d  mov     r10, [rsp+88h+arg_8]
0x180018525  mov     [r10], rax
0x180018528  mov     rdx, r14; struct IUnknown **
0x18001852b  mov     rcx, r12; this
0x18001852e  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x180018533  mov     [r10+8], eax
0x180018537  add     r10, 10h
0x18001853b  mov     [rsp+88h+arg_8], r10
0x180018543  add     r14, 8
0x180018547  movsxd  r9, dword ptr [r13+0]
0x18001854b  mov     rax, [r12]
0x18001854f  lea     r9, [rax+r9*8]
0x180018553  cmp     r14, r9
0x180018556  jb      short loc_180018506
0x180018558  mov     [rsp+88h+var_68], 2
0x180018560  xor     r9d, r9d
0x180018563  mov     r8, r10
0x180018566  mov     rdx, r15
0x180018569  mov     rcx, rbx
0x18001856c  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x180018571  mov     rcx, rsi; lpCriticalSection
0x180018574  call    cs:__imp_LeaveCriticalSection
0x18001857a  mov     r9, rdi; void **
0x18001857d  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180018584  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18001858b  mov     rcx, rbx; void *
0x18001858e  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180018593  mov     edi, eax
0x180018595  test    eax, eax
0x180018597  jns     short loc_1800185AD
0x180018599  mov     rcx, [rbx]
0x18001859c  mov     rax, [rcx+38h]
0x1800185a0  mov     edx, 1
0x1800185a5  mov     rcx, rbx
0x1800185a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ad  mov     eax, edi
0x1800185af  add     rsp, 50h
0x1800185b3  pop     r15
0x1800185b5  pop     r14
0x1800185b7  pop     r13
0x1800185b9  pop     r12
0x1800185bb  pop     rdi
0x1800185bc  pop     rsi
0x1800185bd  pop     rbx
0x1800185be  retn
```
