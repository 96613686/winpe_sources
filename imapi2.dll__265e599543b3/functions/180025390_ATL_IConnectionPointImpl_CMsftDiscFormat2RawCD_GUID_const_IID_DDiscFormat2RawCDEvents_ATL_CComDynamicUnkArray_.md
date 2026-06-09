# ATL::IConnectionPointImpl<CMsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180025390`
- end: `0x180025501`
- name: `?EnumConnections@?$IConnectionPointImpl@VCMsftDiscFormat2RawCD@@$1?IID_DDiscFormat2RawCDEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180005800`
- `0x18000fc0c`
- `0x18000fdc8`
- `0x18000fdd4`
- `0x180016844`
- `0x18001a1f8`
- `0x180025390`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800253ef`
- `KERNEL32!EnterCriticalSection` at `0x1800253ef`
- `KERNEL32!LeaveCriticalSection` at `0x180025432`
- `KERNEL32!LeaveCriticalSection` at `0x1800254c1`
- `KERNEL32!LeaveCriticalSection` at `0x180025432`
- `KERNEL32!LeaveCriticalSection` at `0x1800254c1`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        void **a2)
{
  void *v5; // rax
  void *v6; // rbx
  __int64 v7; // rbp
  _DWORD *v8; // r13
  struct IUnknown **v9; // rdi
  _DWORD *v10; // r12
  unsigned __int64 i; // rcx
  int Interface; // edi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = operator new(0x90u);
  if ( !v5 )
    return 2147942414LL;
  v6 = (void *)ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(v5);
  if ( !v6 )
    return 2147942414LL;
  v7 = a1 + 88;
  if ( !a1 )
    v7 = 112;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  v8 = operator new[](saturated_mul(*(int *)(a1 + 16), 0x10u));
  if ( !v8 )
  {
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    return 2147942414LL;
  }
  v9 = *(struct IUnknown ***)(a1 + 8);
  v10 = v8;
  for ( i = (unsigned __int64)&v9[*(int *)(a1 + 16)];
        (unsigned __int64)v9 < i;
        i = *(_QWORD *)(a1 + 8) + 8LL * *(int *)(a1 + 16) )
  {
    if ( *v9 )
    {
      ((void (__fastcall *)(struct IUnknown *))(*v9)->lpVtbl->AddRef)(*v9);
      *(_QWORD *)v10 = *v9;
      v10[2] = ATL::CComDynamicUnkArray::GetCookie((ATL::CComDynamicUnkArray *)(a1 + 8), v9);
      v10 += 4;
    }
    ++v9;
  }
  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
    v6,
    v8,
    v10,
    0,
    2);
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  Interface = ATL::AtlInternalQueryInterface(
                v6,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                a2);
  if ( Interface < 0 )
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180025390  push    rbx
0x180025392  push    rbp
0x180025393  push    rsi
0x180025394  push    rdi
0x180025395  push    r12
0x180025397  push    r13
0x180025399  push    r14
0x18002539b  push    r15
0x18002539d  sub     rsp, 38h
0x1800253a1  mov     r14, rdx
0x1800253a4  mov     rsi, rcx
0x1800253a7  test    rdx, rdx
0x1800253aa  jnz     short loc_1800253B6
0x1800253ac  mov     eax, 80004003h
0x1800253b1  jmp     loc_18002543D
0x1800253b6  mov     ecx, 90h; Size
0x1800253bb  mov     qword ptr [rdx], 0
0x1800253c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800253c7  test    rax, rax
0x1800253ca  jz      short loc_180025438
0x1800253cc  mov     rcx, rax
0x1800253cf  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x1800253d4  mov     rbx, rax
0x1800253d7  test    rax, rax
0x1800253da  jz      short loc_180025438
0x1800253dc  mov     eax, 70h ; 'p'
0x1800253e1  lea     rbp, [rsi+58h]
0x1800253e5  test    rsi, rsi
0x1800253e8  cmovz   rbp, rax
0x1800253ec  mov     rcx, rbp; lpCriticalSection
0x1800253ef  call    cs:__imp_EnterCriticalSection
0x1800253f5  movsxd  rcx, dword ptr [rsi+10h]
0x1800253f9  mov     eax, 10h
0x1800253fe  mul     rcx
0x180025401  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025408  cmovb   rax, rcx
0x18002540c  mov     rcx, rax; unsigned __int64
0x18002540f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025414  mov     r13, rax
0x180025417  test    rax, rax
0x18002541a  jnz     short loc_18002544E
0x18002541c  mov     rax, [rbx]
0x18002541f  lea     edx, [r13+1]
0x180025423  mov     rcx, rbx
0x180025426  mov     rax, [rax+38h]
0x18002542a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002542f  mov     rcx, rbp; lpCriticalSection
0x180025432  call    cs:__imp_LeaveCriticalSection
0x180025438  mov     eax, 8007000Eh
0x18002543d  add     rsp, 38h
0x180025441  pop     r15
0x180025443  pop     r14
0x180025445  pop     r13
0x180025447  pop     r12
0x180025449  pop     rdi
0x18002544a  pop     rsi
0x18002544b  pop     rbp
0x18002544c  pop     rbx
0x18002544d  retn
0x18002544e  movsxd  rax, dword ptr [rsi+10h]
0x180025452  lea     r15, [rsi+8]
0x180025456  mov     rdi, [r15]
0x180025459  mov     r12, r13
0x18002545c  lea     rcx, [rdi+rax*8]
0x180025460  jmp     short loc_1800254A0
0x180025462  mov     rcx, [rdi]
0x180025465  test    rcx, rcx
0x180025468  jz      short loc_180025491
0x18002546a  mov     rax, [rcx]
0x18002546d  mov     rax, [rax+8]
0x180025471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025476  mov     rax, [rdi]
0x180025479  mov     rdx, rdi; struct IUnknown **
0x18002547c  mov     rcx, r15; this
0x18002547f  mov     [r12], rax
0x180025483  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x180025488  mov     [r12+8], eax
0x18002548d  add     r12, 10h
0x180025491  movsxd  rcx, dword ptr [rsi+10h]
0x180025495  add     rdi, 8
0x180025499  mov     rax, [r15]
0x18002549c  lea     rcx, [rax+rcx*8]
0x1800254a0  cmp     rdi, rcx
0x1800254a3  jb      short loc_180025462
0x1800254a5  xor     r9d, r9d
0x1800254a8  mov     [rsp+78h+var_58], 2
0x1800254b0  mov     r8, r12
0x1800254b3  mov     rdx, r13
0x1800254b6  mov     rcx, rbx
0x1800254b9  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x1800254be  mov     rcx, rbp; lpCriticalSection
0x1800254c1  call    cs:__imp_LeaveCriticalSection
0x1800254c7  mov     r9, r14; void **
0x1800254ca  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800254d1  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800254d8  mov     rcx, rbx; void *
0x1800254db  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800254e0  mov     edi, eax
0x1800254e2  test    eax, eax
0x1800254e4  jns     short loc_1800254FA
0x1800254e6  mov     rdx, [rbx]
0x1800254e9  mov     rcx, rbx
0x1800254ec  mov     rax, [rdx+38h]
0x1800254f0  mov     edx, 1
0x1800254f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254fa  mov     eax, edi
0x1800254fc  jmp     loc_18002543D
```
