# ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkListManagerEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x1800185d0`
- end: `0x1800187fc`
- name: `?EnumConnections@?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkListManagerEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `556`
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
- `0x1800185d0`
- `0x180018ea8`
- `0x18001984c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001871c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001871c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800187b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018689`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkListManagerEvents,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        char **a2)
{
  char *v5; // rbx
  __int64 v6; // rsi
  ATL::CComDynamicUnkArray *v7; // r12
  int *v8; // r13
  _QWORD *v9; // rax
  _QWORD *v10; // r15
  struct IUnknown **v11; // r10
  struct IUnknown **v12; // r14
  unsigned int Cookie; // eax
  __int64 v14; // r10
  int Interface; // edi
  struct IUnknown **v16; // [rsp+98h] [rbp+10h]
  void *v17; // [rsp+A8h] [rbp+20h]

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v17 = operator new(0x90u);
  memset_0(v17, 0, 0x90u);
  v5 = (char *)ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>((__int64)v17);
  if ( !v5 )
    return 2147942414LL;
  v6 = a1 + 72;
  if ( !a1 )
    v6 = 152;
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  v7 = (ATL::CComDynamicUnkArray *)(a1 + 8);
  v8 = (int *)(a1 + 16);
  v9 = operator new[](saturated_mul(*(int *)(a1 + 16), 0x10u));
  v10 = v9;
  if ( !v9 )
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942414LL;
  }
  v11 = (struct IUnknown **)v9;
  v16 = (struct IUnknown **)v9;
  v12 = *(struct IUnknown ***)v7;
  if ( *(_QWORD *)v7 < (unsigned __int64)(*(_QWORD *)v7 + 8LL * *v8) )
  {
    do
    {
      if ( *v12 )
      {
        ((void (__fastcall *)(struct IUnknown *))(*v12)->lpVtbl->AddRef)(*v12);
        *v16 = *v12;
        Cookie = ATL::CComDynamicUnkArray::GetCookie(v7, v12);
        *(_DWORD *)(v14 + 8) = Cookie;
        v11 = (struct IUnknown **)(v14 + 16);
        v16 = v11;
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
                a2);
  if ( Interface < 0 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800185d0  mov     [rsp+arg_8], rdx
0x1800185d5  mov     [rsp+arg_0], rcx
0x1800185da  push    rbx
0x1800185db  push    rsi
0x1800185dc  push    rdi
0x1800185dd  push    r12
0x1800185df  push    r13
0x1800185e1  push    r14
0x1800185e3  push    r15
0x1800185e5  sub     rsp, 50h
0x1800185e9  mov     rdi, rdx
0x1800185ec  mov     r14, rcx
0x1800185ef  test    rdx, rdx
0x1800185f2  jnz     short loc_1800185FE
0x1800185f4  mov     eax, 80004003h
0x1800185f9  jmp     loc_1800187EC
0x1800185fe  mov     qword ptr [rdx], 0
0x180018605  mov     [rsp+88h+arg_10], 0
0x180018611  mov     esi, 90h
0x180018616  mov     ecx, esi; Size
0x180018618  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001861d  mov     rbx, rax
0x180018620  mov     [rsp+88h+arg_18], rax
0x180018628  mov     r8d, esi; Size
0x18001862b  xor     edx, edx; Val
0x18001862d  mov     rcx, rax; void *
0x180018630  call    memset_0
0x180018635  mov     rcx, rbx
0x180018638  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x18001863d  mov     rbx, rax
0x180018640  mov     [rsp+88h+arg_10], rax
0x180018648  jmp     short loc_180018662
0x18001864a  mov     r14, [rsp+88h+arg_0]
0x180018652  mov     rdi, [rsp+88h+arg_8]
0x18001865a  mov     rbx, [rsp+88h+arg_10]
0x180018662  test    rbx, rbx
0x180018665  jnz     short loc_180018671
0x180018667  mov     eax, 8007000Eh
0x18001866c  jmp     loc_1800187EC
0x180018671  lea     rsi, [r14+48h]
0x180018675  mov     eax, 98h
0x18001867a  test    r14, r14
0x18001867d  cmovz   rsi, rax
0x180018681  mov     [rsp+88h+var_48], rsi
0x180018686  mov     rcx, rsi; lpCriticalSection
0x180018689  call    cs:__imp_EnterCriticalSection
0x18001868f  mov     [rsp+88h+arg_18], 0
0x18001869b  lea     r12, [r14+8]
0x18001869f  mov     [rsp+88h+var_50], r12
0x1800186a4  lea     r13, [r12+8]
0x1800186a9  mov     [rsp+88h+var_58], r13
0x1800186ae  movsxd  rcx, dword ptr [r13+0]
0x1800186b2  mov     eax, 10h
0x1800186b7  mul     rcx
0x1800186ba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800186c1  cmovb   rax, rcx
0x1800186c5  mov     rcx, rax; unsigned __int64
0x1800186c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800186cd  mov     r15, rax
0x1800186d0  mov     [rsp+88h+arg_18], rax
0x1800186d8  jmp     short loc_180018701
0x1800186da  mov     rdi, [rsp+88h+arg_8]
0x1800186e2  mov     rbx, [rsp+88h+arg_10]
0x1800186ea  mov     r15, [rsp+88h+arg_18]
0x1800186f2  mov     r13, [rsp+88h+var_58]
0x1800186f7  mov     r12, [rsp+88h+var_50]
0x1800186fc  mov     rsi, [rsp+88h+var_48]
0x180018701  test    r15, r15
0x180018704  jnz     short loc_180018727
0x180018706  mov     rax, [rbx]
0x180018709  lea     edx, [r15+1]
0x18001870d  mov     rcx, rbx
0x180018710  mov     rax, [rax+38h]
0x180018714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018719  mov     rcx, rsi; lpCriticalSection
0x18001871c  call    cs:__imp_LeaveCriticalSection
0x180018722  jmp     loc_180018667
0x180018727  mov     r10, r15
0x18001872a  mov     [rsp+88h+arg_8], r15
0x180018732  mov     r14, [r12]
0x180018736  movsxd  rax, dword ptr [r13+0]
0x18001873a  lea     rcx, [r14+rax*8]
0x18001873e  cmp     r14, rcx
0x180018741  jnb     short loc_180018795
0x180018743  mov     rcx, [r14]
0x180018746  test    rcx, rcx
0x180018749  jz      short loc_180018780
0x18001874b  mov     rax, [rcx]
0x18001874e  mov     rax, [rax+8]
0x180018752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018757  mov     rax, [r14]
0x18001875a  mov     r10, [rsp+88h+arg_8]
0x180018762  mov     [r10], rax
0x180018765  mov     rdx, r14; struct IUnknown **
0x180018768  mov     rcx, r12; this
0x18001876b  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x180018770  mov     [r10+8], eax
0x180018774  add     r10, 10h
0x180018778  mov     [rsp+88h+arg_8], r10
0x180018780  add     r14, 8
0x180018784  movsxd  r9, dword ptr [r13+0]
0x180018788  mov     rax, [r12]
0x18001878c  lea     r9, [rax+r9*8]
0x180018790  cmp     r14, r9
0x180018793  jb      short loc_180018743
0x180018795  mov     [rsp+88h+var_68], 2
0x18001879d  xor     r9d, r9d
0x1800187a0  mov     r8, r10
0x1800187a3  mov     rdx, r15
0x1800187a6  mov     rcx, rbx
0x1800187a9  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x1800187ae  mov     rcx, rsi; lpCriticalSection
0x1800187b1  call    cs:__imp_LeaveCriticalSection
0x1800187b7  mov     r9, rdi; void **
0x1800187ba  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800187c1  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800187c8  mov     rcx, rbx; void *
0x1800187cb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800187d0  mov     edi, eax
0x1800187d2  test    eax, eax
0x1800187d4  jns     short loc_1800187EA
0x1800187d6  mov     rcx, [rbx]
0x1800187d9  mov     rax, [rcx+38h]
0x1800187dd  mov     edx, 1
0x1800187e2  mov     rcx, rbx
0x1800187e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ea  mov     eax, edi
0x1800187ec  add     rsp, 50h
0x1800187f0  pop     r15
0x1800187f2  pop     r14
0x1800187f4  pop     r13
0x1800187f6  pop     r12
0x1800187f8  pop     rdi
0x1800187f9  pop     rsi
0x1800187fa  pop     rbx
0x1800187fb  retn
```
