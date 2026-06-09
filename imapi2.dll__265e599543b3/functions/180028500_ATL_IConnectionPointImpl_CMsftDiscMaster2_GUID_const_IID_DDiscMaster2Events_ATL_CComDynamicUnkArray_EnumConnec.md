# ATL::IConnectionPointImpl<CMsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180028500`
- end: `0x180028671`
- name: `?EnumConnections@?$IConnectionPointImpl@VCMsftDiscMaster2@@$1?IID_DDiscMaster2Events@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
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
- `0x180028500`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002855f`
- `KERNEL32!EnterCriticalSection` at `0x18002855f`
- `KERNEL32!LeaveCriticalSection` at `0x1800285a2`
- `KERNEL32!LeaveCriticalSection` at `0x180028631`
- `KERNEL32!LeaveCriticalSection` at `0x1800285a2`
- `KERNEL32!LeaveCriticalSection` at `0x180028631`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,ATL::CComDynamicUnkArray>::EnumConnections(
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
  v7 = a1 + 40;
  if ( !a1 )
    v7 = 64;
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
0x180028500  push    rbx
0x180028502  push    rbp
0x180028503  push    rsi
0x180028504  push    rdi
0x180028505  push    r12
0x180028507  push    r13
0x180028509  push    r14
0x18002850b  push    r15
0x18002850d  sub     rsp, 38h
0x180028511  mov     r14, rdx
0x180028514  mov     rsi, rcx
0x180028517  test    rdx, rdx
0x18002851a  jnz     short loc_180028526
0x18002851c  mov     eax, 80004003h
0x180028521  jmp     loc_1800285AD
0x180028526  mov     ecx, 90h; Size
0x18002852b  mov     qword ptr [rdx], 0
0x180028532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028537  test    rax, rax
0x18002853a  jz      short loc_1800285A8
0x18002853c  mov     rcx, rax
0x18002853f  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x180028544  mov     rbx, rax
0x180028547  test    rax, rax
0x18002854a  jz      short loc_1800285A8
0x18002854c  mov     eax, 40h ; '@'
0x180028551  lea     rbp, [rsi+28h]
0x180028555  test    rsi, rsi
0x180028558  cmovz   rbp, rax
0x18002855c  mov     rcx, rbp; lpCriticalSection
0x18002855f  call    cs:__imp_EnterCriticalSection
0x180028565  movsxd  rcx, dword ptr [rsi+10h]
0x180028569  mov     eax, 10h
0x18002856e  mul     rcx
0x180028571  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180028578  cmovb   rax, rcx
0x18002857c  mov     rcx, rax; unsigned __int64
0x18002857f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028584  mov     r13, rax
0x180028587  test    rax, rax
0x18002858a  jnz     short loc_1800285BE
0x18002858c  mov     rax, [rbx]
0x18002858f  lea     edx, [r13+1]
0x180028593  mov     rcx, rbx
0x180028596  mov     rax, [rax+38h]
0x18002859a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002859f  mov     rcx, rbp; lpCriticalSection
0x1800285a2  call    cs:__imp_LeaveCriticalSection
0x1800285a8  mov     eax, 8007000Eh
0x1800285ad  add     rsp, 38h
0x1800285b1  pop     r15
0x1800285b3  pop     r14
0x1800285b5  pop     r13
0x1800285b7  pop     r12
0x1800285b9  pop     rdi
0x1800285ba  pop     rsi
0x1800285bb  pop     rbp
0x1800285bc  pop     rbx
0x1800285bd  retn
0x1800285be  movsxd  rax, dword ptr [rsi+10h]
0x1800285c2  lea     r15, [rsi+8]
0x1800285c6  mov     rdi, [r15]
0x1800285c9  mov     r12, r13
0x1800285cc  lea     rcx, [rdi+rax*8]
0x1800285d0  jmp     short loc_180028610
0x1800285d2  mov     rcx, [rdi]
0x1800285d5  test    rcx, rcx
0x1800285d8  jz      short loc_180028601
0x1800285da  mov     rax, [rcx]
0x1800285dd  mov     rax, [rax+8]
0x1800285e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285e6  mov     rax, [rdi]
0x1800285e9  mov     rdx, rdi; struct IUnknown **
0x1800285ec  mov     rcx, r15; this
0x1800285ef  mov     [r12], rax
0x1800285f3  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x1800285f8  mov     [r12+8], eax
0x1800285fd  add     r12, 10h
0x180028601  movsxd  rcx, dword ptr [rsi+10h]
0x180028605  add     rdi, 8
0x180028609  mov     rax, [r15]
0x18002860c  lea     rcx, [rax+rcx*8]
0x180028610  cmp     rdi, rcx
0x180028613  jb      short loc_1800285D2
0x180028615  xor     r9d, r9d
0x180028618  mov     [rsp+78h+var_58], 2
0x180028620  mov     r8, r12
0x180028623  mov     rdx, r13
0x180028626  mov     rcx, rbx
0x180028629  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x18002862e  mov     rcx, rbp; lpCriticalSection
0x180028631  call    cs:__imp_LeaveCriticalSection
0x180028637  mov     r9, r14; void **
0x18002863a  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180028641  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180028648  mov     rcx, rbx; void *
0x18002864b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180028650  mov     edi, eax
0x180028652  test    eax, eax
0x180028654  jns     short loc_18002866A
0x180028656  mov     rdx, [rbx]
0x180028659  mov     rcx, rbx
0x18002865c  mov     rax, [rdx+38h]
0x180028660  mov     edx, 1
0x180028665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002866a  mov     eax, edi
0x18002866c  jmp     loc_1800285AD
```
