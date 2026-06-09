# ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkCostManagerEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180018150`
- end: `0x18001837c`
- name: `?EnumConnections@?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkCostManagerEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
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
- `0x180018150`
- `0x180018ea8`
- `0x18001984c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001829c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001829c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018331`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018209`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018209`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkCostManagerEvents,ATL::CComDynamicUnkArray>::EnumConnections(
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
  v6 = a1 + 48;
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
0x180018150  mov     [rsp+arg_8], rdx
0x180018155  mov     [rsp+arg_0], rcx
0x18001815a  push    rbx
0x18001815b  push    rsi
0x18001815c  push    rdi
0x18001815d  push    r12
0x18001815f  push    r13
0x180018161  push    r14
0x180018163  push    r15
0x180018165  sub     rsp, 50h
0x180018169  mov     rdi, rdx
0x18001816c  mov     r14, rcx
0x18001816f  test    rdx, rdx
0x180018172  jnz     short loc_18001817E
0x180018174  mov     eax, 80004003h
0x180018179  jmp     loc_18001836C
0x18001817e  mov     qword ptr [rdx], 0
0x180018185  mov     [rsp+88h+arg_10], 0
0x180018191  mov     esi, 90h
0x180018196  mov     ecx, esi; Size
0x180018198  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001819d  mov     rbx, rax
0x1800181a0  mov     [rsp+88h+arg_18], rax
0x1800181a8  mov     r8d, esi; Size
0x1800181ab  xor     edx, edx; Val
0x1800181ad  mov     rcx, rax; void *
0x1800181b0  call    memset_0
0x1800181b5  mov     rcx, rbx
0x1800181b8  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x1800181bd  mov     rbx, rax
0x1800181c0  mov     [rsp+88h+arg_10], rax
0x1800181c8  jmp     short loc_1800181E2
0x1800181ca  mov     r14, [rsp+88h+arg_0]
0x1800181d2  mov     rdi, [rsp+88h+arg_8]
0x1800181da  mov     rbx, [rsp+88h+arg_10]
0x1800181e2  test    rbx, rbx
0x1800181e5  jnz     short loc_1800181F1
0x1800181e7  mov     eax, 8007000Eh
0x1800181ec  jmp     loc_18001836C
0x1800181f1  lea     rsi, [r14+30h]
0x1800181f5  mov     eax, 98h
0x1800181fa  test    r14, r14
0x1800181fd  cmovz   rsi, rax
0x180018201  mov     [rsp+88h+var_48], rsi
0x180018206  mov     rcx, rsi; lpCriticalSection
0x180018209  call    cs:__imp_EnterCriticalSection
0x18001820f  mov     [rsp+88h+arg_18], 0
0x18001821b  lea     r12, [r14+8]
0x18001821f  mov     [rsp+88h+var_50], r12
0x180018224  lea     r13, [r12+8]
0x180018229  mov     [rsp+88h+var_58], r13
0x18001822e  movsxd  rcx, dword ptr [r13+0]
0x180018232  mov     eax, 10h
0x180018237  mul     rcx
0x18001823a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018241  cmovb   rax, rcx
0x180018245  mov     rcx, rax; unsigned __int64
0x180018248  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001824d  mov     r15, rax
0x180018250  mov     [rsp+88h+arg_18], rax
0x180018258  jmp     short loc_180018281
0x18001825a  mov     rdi, [rsp+88h+arg_8]
0x180018262  mov     rbx, [rsp+88h+arg_10]
0x18001826a  mov     r15, [rsp+88h+arg_18]
0x180018272  mov     r13, [rsp+88h+var_58]
0x180018277  mov     r12, [rsp+88h+var_50]
0x18001827c  mov     rsi, [rsp+88h+var_48]
0x180018281  test    r15, r15
0x180018284  jnz     short loc_1800182A7
0x180018286  mov     rax, [rbx]
0x180018289  lea     edx, [r15+1]
0x18001828d  mov     rcx, rbx
0x180018290  mov     rax, [rax+38h]
0x180018294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018299  mov     rcx, rsi; lpCriticalSection
0x18001829c  call    cs:__imp_LeaveCriticalSection
0x1800182a2  jmp     loc_1800181E7
0x1800182a7  mov     r10, r15
0x1800182aa  mov     [rsp+88h+arg_8], r15
0x1800182b2  mov     r14, [r12]
0x1800182b6  movsxd  rax, dword ptr [r13+0]
0x1800182ba  lea     rcx, [r14+rax*8]
0x1800182be  cmp     r14, rcx
0x1800182c1  jnb     short loc_180018315
0x1800182c3  mov     rcx, [r14]
0x1800182c6  test    rcx, rcx
0x1800182c9  jz      short loc_180018300
0x1800182cb  mov     rax, [rcx]
0x1800182ce  mov     rax, [rax+8]
0x1800182d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182d7  mov     rax, [r14]
0x1800182da  mov     r10, [rsp+88h+arg_8]
0x1800182e2  mov     [r10], rax
0x1800182e5  mov     rdx, r14; struct IUnknown **
0x1800182e8  mov     rcx, r12; this
0x1800182eb  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x1800182f0  mov     [r10+8], eax
0x1800182f4  add     r10, 10h
0x1800182f8  mov     [rsp+88h+arg_8], r10
0x180018300  add     r14, 8
0x180018304  movsxd  r9, dword ptr [r13+0]
0x180018308  mov     rax, [r12]
0x18001830c  lea     r9, [rax+r9*8]
0x180018310  cmp     r14, r9
0x180018313  jb      short loc_1800182C3
0x180018315  mov     [rsp+88h+var_68], 2
0x18001831d  xor     r9d, r9d
0x180018320  mov     r8, r10
0x180018323  mov     rdx, r15
0x180018326  mov     rcx, rbx
0x180018329  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x18001832e  mov     rcx, rsi; lpCriticalSection
0x180018331  call    cs:__imp_LeaveCriticalSection
0x180018337  mov     r9, rdi; void **
0x18001833a  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180018341  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180018348  mov     rcx, rbx; void *
0x18001834b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180018350  mov     edi, eax
0x180018352  test    eax, eax
0x180018354  jns     short loc_18001836A
0x180018356  mov     rcx, [rbx]
0x180018359  mov     rax, [rcx+38h]
0x18001835d  mov     edx, 1
0x180018362  mov     rcx, rbx
0x180018365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001836a  mov     eax, edi
0x18001836c  add     rsp, 50h
0x180018370  pop     r15
0x180018372  pop     r14
0x180018374  pop     r13
0x180018376  pop     r12
0x180018378  pop     rdi
0x180018379  pop     rsi
0x18001837a  pop     rbx
0x18001837b  retn
```
