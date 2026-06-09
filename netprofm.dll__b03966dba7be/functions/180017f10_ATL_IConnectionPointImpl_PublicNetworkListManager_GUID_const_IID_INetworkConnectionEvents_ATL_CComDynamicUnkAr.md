# ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180017f10`
- end: `0x18001813c`
- name: `?EnumConnections@?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
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
- `0x180017f10`
- `0x180018ea8`
- `0x18001984c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001805c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001805c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800180f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fc9`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionEvents,ATL::CComDynamicUnkArray>::EnumConnections(
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
  v6 = a1 + 120;
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
0x180017f10  mov     [rsp+arg_8], rdx
0x180017f15  mov     [rsp+arg_0], rcx
0x180017f1a  push    rbx
0x180017f1b  push    rsi
0x180017f1c  push    rdi
0x180017f1d  push    r12
0x180017f1f  push    r13
0x180017f21  push    r14
0x180017f23  push    r15
0x180017f25  sub     rsp, 50h
0x180017f29  mov     rdi, rdx
0x180017f2c  mov     r14, rcx
0x180017f2f  test    rdx, rdx
0x180017f32  jnz     short loc_180017F3E
0x180017f34  mov     eax, 80004003h
0x180017f39  jmp     loc_18001812C
0x180017f3e  mov     qword ptr [rdx], 0
0x180017f45  mov     [rsp+88h+arg_10], 0
0x180017f51  mov     esi, 90h
0x180017f56  mov     ecx, esi; Size
0x180017f58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f5d  mov     rbx, rax
0x180017f60  mov     [rsp+88h+arg_18], rax
0x180017f68  mov     r8d, esi; Size
0x180017f6b  xor     edx, edx; Val
0x180017f6d  mov     rcx, rax; void *
0x180017f70  call    memset_0
0x180017f75  mov     rcx, rbx
0x180017f78  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x180017f7d  mov     rbx, rax
0x180017f80  mov     [rsp+88h+arg_10], rax
0x180017f88  jmp     short loc_180017FA2
0x180017f8a  mov     r14, [rsp+88h+arg_0]
0x180017f92  mov     rdi, [rsp+88h+arg_8]
0x180017f9a  mov     rbx, [rsp+88h+arg_10]
0x180017fa2  test    rbx, rbx
0x180017fa5  jnz     short loc_180017FB1
0x180017fa7  mov     eax, 8007000Eh
0x180017fac  jmp     loc_18001812C
0x180017fb1  lea     rsi, [r14+78h]
0x180017fb5  mov     eax, 98h
0x180017fba  test    r14, r14
0x180017fbd  cmovz   rsi, rax
0x180017fc1  mov     [rsp+88h+var_48], rsi
0x180017fc6  mov     rcx, rsi; lpCriticalSection
0x180017fc9  call    cs:__imp_EnterCriticalSection
0x180017fcf  mov     [rsp+88h+arg_18], 0
0x180017fdb  lea     r12, [r14+8]
0x180017fdf  mov     [rsp+88h+var_50], r12
0x180017fe4  lea     r13, [r12+8]
0x180017fe9  mov     [rsp+88h+var_58], r13
0x180017fee  movsxd  rcx, dword ptr [r13+0]
0x180017ff2  mov     eax, 10h
0x180017ff7  mul     rcx
0x180017ffa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018001  cmovb   rax, rcx
0x180018005  mov     rcx, rax; unsigned __int64
0x180018008  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001800d  mov     r15, rax
0x180018010  mov     [rsp+88h+arg_18], rax
0x180018018  jmp     short loc_180018041
0x18001801a  mov     rdi, [rsp+88h+arg_8]
0x180018022  mov     rbx, [rsp+88h+arg_10]
0x18001802a  mov     r15, [rsp+88h+arg_18]
0x180018032  mov     r13, [rsp+88h+var_58]
0x180018037  mov     r12, [rsp+88h+var_50]
0x18001803c  mov     rsi, [rsp+88h+var_48]
0x180018041  test    r15, r15
0x180018044  jnz     short loc_180018067
0x180018046  mov     rax, [rbx]
0x180018049  lea     edx, [r15+1]
0x18001804d  mov     rcx, rbx
0x180018050  mov     rax, [rax+38h]
0x180018054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018059  mov     rcx, rsi; lpCriticalSection
0x18001805c  call    cs:__imp_LeaveCriticalSection
0x180018062  jmp     loc_180017FA7
0x180018067  mov     r10, r15
0x18001806a  mov     [rsp+88h+arg_8], r15
0x180018072  mov     r14, [r12]
0x180018076  movsxd  rax, dword ptr [r13+0]
0x18001807a  lea     rcx, [r14+rax*8]
0x18001807e  cmp     r14, rcx
0x180018081  jnb     short loc_1800180D5
0x180018083  mov     rcx, [r14]
0x180018086  test    rcx, rcx
0x180018089  jz      short loc_1800180C0
0x18001808b  mov     rax, [rcx]
0x18001808e  mov     rax, [rax+8]
0x180018092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018097  mov     rax, [r14]
0x18001809a  mov     r10, [rsp+88h+arg_8]
0x1800180a2  mov     [r10], rax
0x1800180a5  mov     rdx, r14; struct IUnknown **
0x1800180a8  mov     rcx, r12; this
0x1800180ab  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x1800180b0  mov     [r10+8], eax
0x1800180b4  add     r10, 10h
0x1800180b8  mov     [rsp+88h+arg_8], r10
0x1800180c0  add     r14, 8
0x1800180c4  movsxd  r9, dword ptr [r13+0]
0x1800180c8  mov     rax, [r12]
0x1800180cc  lea     r9, [rax+r9*8]
0x1800180d0  cmp     r14, r9
0x1800180d3  jb      short loc_180018083
0x1800180d5  mov     [rsp+88h+var_68], 2
0x1800180dd  xor     r9d, r9d
0x1800180e0  mov     r8, r10
0x1800180e3  mov     rdx, r15
0x1800180e6  mov     rcx, rbx
0x1800180e9  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x1800180ee  mov     rcx, rsi; lpCriticalSection
0x1800180f1  call    cs:__imp_LeaveCriticalSection
0x1800180f7  mov     r9, rdi; void **
0x1800180fa  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180018101  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180018108  mov     rcx, rbx; void *
0x18001810b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180018110  mov     edi, eax
0x180018112  test    eax, eax
0x180018114  jns     short loc_18001812A
0x180018116  mov     rcx, [rbx]
0x180018119  mov     rax, [rcx+38h]
0x18001811d  mov     edx, 1
0x180018122  mov     rcx, rbx
0x180018125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001812a  mov     eax, edi
0x18001812c  add     rsp, 50h
0x180018130  pop     r15
0x180018132  pop     r14
0x180018134  pop     r13
0x180018136  pop     r12
0x180018138  pop     rdi
0x180018139  pop     rsi
0x18001813a  pop     rbx
0x18001813b  retn
```
