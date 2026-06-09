# ATL::IConnectionPointImpl<CMsftDiscFormat2Data,&_GUID const IID_DDiscFormat2DataEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180018790`
- end: `0x180018901`
- name: `?EnumConnections@?$IConnectionPointImpl@VCMsftDiscFormat2Data@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
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
- `0x180018790`
- `0x18001a1f8`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800187ef`
- `KERNEL32!EnterCriticalSection` at `0x1800187ef`
- `KERNEL32!LeaveCriticalSection` at `0x180018832`
- `KERNEL32!LeaveCriticalSection` at `0x1800188c1`
- `KERNEL32!LeaveCriticalSection` at `0x180018832`
- `KERNEL32!LeaveCriticalSection` at `0x1800188c1`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscFormat2Data,&_GUID const IID_DDiscFormat2DataEvents,ATL::CComDynamicUnkArray>::EnumConnections(
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
  v7 = a1 + 96;
  if ( !a1 )
    v7 = 120;
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
0x180018790  push    rbx
0x180018792  push    rbp
0x180018793  push    rsi
0x180018794  push    rdi
0x180018795  push    r12
0x180018797  push    r13
0x180018799  push    r14
0x18001879b  push    r15
0x18001879d  sub     rsp, 38h
0x1800187a1  mov     r14, rdx
0x1800187a4  mov     rsi, rcx
0x1800187a7  test    rdx, rdx
0x1800187aa  jnz     short loc_1800187B6
0x1800187ac  mov     eax, 80004003h
0x1800187b1  jmp     loc_18001883D
0x1800187b6  mov     ecx, 90h; Size
0x1800187bb  mov     qword ptr [rdx], 0
0x1800187c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800187c7  test    rax, rax
0x1800187ca  jz      short loc_180018838
0x1800187cc  mov     rcx, rax
0x1800187cf  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x1800187d4  mov     rbx, rax
0x1800187d7  test    rax, rax
0x1800187da  jz      short loc_180018838
0x1800187dc  mov     eax, 78h ; 'x'
0x1800187e1  lea     rbp, [rsi+60h]
0x1800187e5  test    rsi, rsi
0x1800187e8  cmovz   rbp, rax
0x1800187ec  mov     rcx, rbp; lpCriticalSection
0x1800187ef  call    cs:__imp_EnterCriticalSection
0x1800187f5  movsxd  rcx, dword ptr [rsi+10h]
0x1800187f9  mov     eax, 10h
0x1800187fe  mul     rcx
0x180018801  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018808  cmovb   rax, rcx
0x18001880c  mov     rcx, rax; unsigned __int64
0x18001880f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018814  mov     r13, rax
0x180018817  test    rax, rax
0x18001881a  jnz     short loc_18001884E
0x18001881c  mov     rax, [rbx]
0x18001881f  lea     edx, [r13+1]
0x180018823  mov     rcx, rbx
0x180018826  mov     rax, [rax+38h]
0x18001882a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001882f  mov     rcx, rbp; lpCriticalSection
0x180018832  call    cs:__imp_LeaveCriticalSection
0x180018838  mov     eax, 8007000Eh
0x18001883d  add     rsp, 38h
0x180018841  pop     r15
0x180018843  pop     r14
0x180018845  pop     r13
0x180018847  pop     r12
0x180018849  pop     rdi
0x18001884a  pop     rsi
0x18001884b  pop     rbp
0x18001884c  pop     rbx
0x18001884d  retn
0x18001884e  movsxd  rax, dword ptr [rsi+10h]
0x180018852  lea     r15, [rsi+8]
0x180018856  mov     rdi, [r15]
0x180018859  mov     r12, r13
0x18001885c  lea     rcx, [rdi+rax*8]
0x180018860  jmp     short loc_1800188A0
0x180018862  mov     rcx, [rdi]
0x180018865  test    rcx, rcx
0x180018868  jz      short loc_180018891
0x18001886a  mov     rax, [rcx]
0x18001886d  mov     rax, [rax+8]
0x180018871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018876  mov     rax, [rdi]
0x180018879  mov     rdx, rdi; struct IUnknown **
0x18001887c  mov     rcx, r15; this
0x18001887f  mov     [r12], rax
0x180018883  call    ?GetCookie@CComDynamicUnkArray@ATL@@QEAAKPEAPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::GetCookie(IUnknown * *)
0x180018888  mov     [r12+8], eax
0x18001888d  add     r12, 10h
0x180018891  movsxd  rcx, dword ptr [rsi+10h]
0x180018895  add     rdi, 8
0x180018899  mov     rax, [r15]
0x18001889c  lea     rcx, [rax+rcx*8]
0x1800188a0  cmp     rdi, rcx
0x1800188a3  jb      short loc_180018862
0x1800188a5  xor     r9d, r9d
0x1800188a8  mov     [rsp+78h+var_58], 2
0x1800188b0  mov     r8, r12
0x1800188b3  mov     rdx, r13
0x1800188b6  mov     rcx, rbx
0x1800188b9  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x1800188be  mov     rcx, rbp; lpCriticalSection
0x1800188c1  call    cs:__imp_LeaveCriticalSection
0x1800188c7  mov     r9, r14; void **
0x1800188ca  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800188d1  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800188d8  mov     rcx, rbx; void *
0x1800188db  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800188e0  mov     edi, eax
0x1800188e2  test    eax, eax
0x1800188e4  jns     short loc_1800188FA
0x1800188e6  mov     rdx, [rbx]
0x1800188e9  mov     rcx, rbx
0x1800188ec  mov     rax, [rdx+38h]
0x1800188f0  mov     edx, 1
0x1800188f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188fa  mov     eax, edi
0x1800188fc  jmp     loc_18001883D
```
