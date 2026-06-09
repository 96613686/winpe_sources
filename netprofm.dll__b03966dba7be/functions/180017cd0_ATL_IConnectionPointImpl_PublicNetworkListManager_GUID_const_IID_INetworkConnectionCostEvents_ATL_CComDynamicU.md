# ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionCostEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180017cd0`
- end: `0x180017efc`
- name: `?EnumConnections@?$IConnectionPointImpl@VPublicNetworkListManager@@$1?IID_INetworkConnectionCostEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
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
- `0x180017cd0`
- `0x180018ea8`
- `0x18001984c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017eb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017eb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017d89`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<PublicNetworkListManager,&_GUID const IID_INetworkConnectionCostEvents,ATL::CComDynamicUnkArray>::EnumConnections(
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
  v6 = v3 + 96;
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
0x180017cd0  mov     [rsp+arg_8], rdx
0x180017cd5  mov     [rsp+arg_0], rcx
0x180017cda  push    rbx
0x180017cdb  push    rsi
0x180017cdc  push    rdi
0x180017cdd  push    r12
0x180017cdf  push    r13
0x180017ce1  push    r14
0x180017ce3  push    r15
0x180017ce5  sub     rsp, 50h
0x180017ce9  mov     rdi, rdx
0x180017cec  mov     r14, rcx
0x180017cef  test    rdx, rdx
0x180017cf2  jnz     short loc_180017CFE
0x180017cf4  mov     eax, 80004003h
0x180017cf9  jmp     loc_180017EEC
0x180017cfe  mov     qword ptr [rdx], 0
0x180017d05  mov     [rsp+88h+arg_10], 0
0x180017d11  mov     esi, 90h
0x180017d16  mov     ecx, esi; Size
0x180017d18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017d1d  mov     rbx, rax
0x180017d20  mov     [rsp+88h+arg_18], rax
0x180017d28  mov     r8d, esi; Size
0x180017d2b  xor     edx, edx; Val
0x180017d2d  mov     rcx, rax; void *
0x180017d30  call    memset_0
0x180017d35  mov     rcx, rbx
0x180017d38  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x180017d3d  mov     rbx, rax
0x180017d40  mov     [rsp+88h+arg_10], rax
0x180017d48  jmp     short loc_180017D62
0x180017d4a  mov     r14, [rsp+88h+arg_0]
0x180017d52  mov     rdi, [rsp+88h+arg_8]
0x180017d5a  mov     rbx, [rsp+88h+arg_10]
0x180017d62  test    rbx, rbx
0x180017d65  jnz     short loc_180017D71
0x180017d67  mov     eax, 8007000Eh
0x180017d6c  jmp     loc_180017EEC
0x180017d71  lea     rsi, [r14+60h]
0x180017d75  mov     eax, 98h
0x180017d7a  test    r14, r14
0x180017d7d  cmovz   rsi, rax
0x180017d81  mov     [rsp+88h+var_48], rsi
0x180017d86  mov     rcx, rsi; lpCriticalSection
0x180017d89  call    cs:__imp_EnterCriticalSection
0x180017d8f  mov     [rsp+88h+arg_18], 0
0x180017d9b  lea     r12, [r14+8]
0x180017d9f  mov     [rsp+88h+var_50], r12
0x180017da4  lea     r13, [r12+8]
0x180017da9  mov     [rsp+88h+var_58], r13
0x180017dae  movsxd  rcx, dword ptr [r13+0]
0x180017db2  mov     eax, 10h
0x180017db7  mul     rcx
0x180017dba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017dc1  cmovb   rax, rcx
0x180017dc5  mov     rcx, rax; unsigned __int64
0x180017dc8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017dcd  mov     r15, rax
0x180017dd0  mov     [rsp+88h+arg_18], rax
0x180017dd8  jmp     short loc_180017E01
0x180017dda  mov     rdi, [rsp+88h+arg_8]
0x180017de2  mov     rbx, [rsp+88h+arg_10]
0x180017dea  mov     r15, [rsp+88h+arg_18]
0x180017df2  mov     r13, [rsp+88h+var_58]
0x180017df7  mov     r12, [rsp+88h+var_50]
0x180017dfc  mov     rsi, [rsp+88h+var_48]
0x180017e01  test    r15, r15
0x180017e04  jnz     short loc_180017E27
0x180017e06  mov     rax, [rbx]
0x180017e09  lea     edx, [r15+1]
0x180017e0d  mov     rcx, rbx
0x180017e10  mov     rax, [rax+38h]
0x180017e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e19  mov     rcx, rsi; lpCriticalSection
0x180017e1c  call    cs:__imp_LeaveCriticalSection
0x180017e22  jmp     loc_180017D67
0x180017e27  mov     r10, r15
0x180017e2a  mov     [rsp+88h+arg_8], r15
0x180017e32  mov     r14, [r12]
0x180017e36  movsxd  rax, dword ptr [r13+0]
0x180017e3a  lea     rcx, [r14+rax*8]
0x180017e3e  cmp     r14, rcx
0x180017e41  jnb     short loc_180017E95
0x180017e43  mov     rcx, [r14]
0x180017e46  test    rcx, rcx
0x180017e49  jz      short loc_180017E80
0x180017e4b  mov     rax, [rcx]
0x180017e4e  mov     rax, [rax+8]
0x180017e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e57  mov     rax, [r14]
0x180017e5a  mov     r10, [rsp+88h+arg_8]
0x180017e62  mov     [r10], rax
0x180017e65  mov     rdx, r14; struct IUnknown **
0x180017e68  mov     rcx, r12; this
0x180017e6b  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x180017e70  mov     [r10+8], eax
0x180017e74  add     r10, 10h
0x180017e78  mov     [rsp+88h+arg_8], r10
0x180017e80  add     r14, 8
0x180017e84  movsxd  r9, dword ptr [r13+0]
0x180017e88  mov     rax, [r12]
0x180017e8c  lea     r9, [rax+r9*8]
0x180017e90  cmp     r14, r9
0x180017e93  jb      short loc_180017E43
0x180017e95  mov     [rsp+88h+var_68], 2
0x180017e9d  xor     r9d, r9d
0x180017ea0  mov     r8, r10
0x180017ea3  mov     rdx, r15
0x180017ea6  mov     rcx, rbx
0x180017ea9  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x180017eae  mov     rcx, rsi; lpCriticalSection
0x180017eb1  call    cs:__imp_LeaveCriticalSection
0x180017eb7  mov     r9, rdi; void **
0x180017eba  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180017ec1  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180017ec8  mov     rcx, rbx; void *
0x180017ecb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180017ed0  mov     edi, eax
0x180017ed2  test    eax, eax
0x180017ed4  jns     short loc_180017EEA
0x180017ed6  mov     rcx, [rbx]
0x180017ed9  mov     rax, [rcx+38h]
0x180017edd  mov     edx, 1
0x180017ee2  mov     rcx, rbx
0x180017ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eea  mov     eax, edi
0x180017eec  add     rsp, 50h
0x180017ef0  pop     r15
0x180017ef2  pop     r14
0x180017ef4  pop     r13
0x180017ef6  pop     r12
0x180017ef8  pop     rdi
0x180017ef9  pop     rsi
0x180017efa  pop     rbx
0x180017efb  retn
```
