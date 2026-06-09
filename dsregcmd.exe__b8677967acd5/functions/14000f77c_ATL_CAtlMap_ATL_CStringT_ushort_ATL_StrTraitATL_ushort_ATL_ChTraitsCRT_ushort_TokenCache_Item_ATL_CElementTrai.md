# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::NewNode(ushort const *,uint,uint)

- ea: `0x14000f77c`
- end: `0x14000f8ee`
- name: `?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z`
- size: `370`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000f2ac`

## callees

- `0x1400054e8`
- `0x140005c58`
- `0x140008db4`
- `0x140008e50`
- `0x14000f77c`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000f7ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000f7ce`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::NewNode(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4)
{
  __int64 v5; // r14
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // r8
  _QWORD *i; // rcx
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-28h]

  v5 = a3;
  if ( *(_QWORD *)(a1 + 64) )
    goto LABEL_8;
  v8 = *(unsigned int *)(a1 + 52);
  if ( v8 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v8 < 0x30 )
      goto LABEL_15;
    v8 *= 48LL;
  }
  v9 = malloc(v8 + 8);
  if ( !v9 )
LABEL_15:
    ATL::AtlThrowImpl(0x8007000E);
  *v9 = *(_QWORD *)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v9;
  v10 = (unsigned int)(*(_DWORD *)(a1 + 52) - 1);
  for ( i = &v9[6 * v10 + 1]; (int)v10 >= 0; LODWORD(v10) = v10 - 1 )
  {
    v12 = *(_QWORD *)(a1 + 64);
    i[4] = v12;
    *(_QWORD *)(a1 + 64) = i;
    i -= 6;
  }
LABEL_8:
  v13 = *(_QWORD *)(a1 + 64);
  if ( !v13 )
    ATL::AtlThrowImpl(0x80004005);
  try
  {
    v17 = *(_QWORD *)(a1 + 64);
    *(_QWORD *)(a1 + 64) = *(_QWORD *)(v13 + 32);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (_QWORD *)v13,
      a2);
    *(_QWORD *)(v13 + 8) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  }
  catch ( ... )
  {
    *(_QWORD *)(v17 + 32) = *(_QWORD *)(a1 + 64);
    *(_QWORD *)(a1 + 64) = v17;
    throw;
  }
  *(_QWORD *)(v13 + 16) = v14 + 24;
  *(_QWORD *)(v13 + 24) = 0;
  *(_DWORD *)(v13 + 40) = a4;
  ++*(_QWORD *)(a1 + 8);
  *(_QWORD *)(v13 + 32) = *(_QWORD *)(*(_QWORD *)a1 + 8 * v5);
  *(_QWORD *)(*(_QWORD *)a1 + 8 * v5) = v13;
  if ( *(_QWORD *)(a1 + 8) > *(_QWORD *)(a1 + 32) && !*(_DWORD *)(a1 + 48) )
  {
    v15 = (unsigned int)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(a1);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::Rehash(
      a1,
      v15);
  }
  return v13;
}

```

## disassembly

```asm
0x14000f77c  mov     [rsp+arg_8], rbx
0x14000f781  mov     [rsp+arg_10], rsi
0x14000f786  mov     [rsp+arg_0], rcx
0x14000f78b  push    rdi
0x14000f78c  push    r14
0x14000f78e  push    r15
0x14000f790  sub     rsp, 30h
0x14000f794  mov     r15d, r9d
0x14000f797  mov     r14d, r8d
0x14000f79a  mov     rsi, rdx
0x14000f79d  mov     rbx, rcx
0x14000f7a0  cmp     qword ptr [rcx+40h], 0
0x14000f7a5  jnz     short loc_14000F819
0x14000f7a7  mov     ecx, [rcx+34h]
0x14000f7aa  test    rcx, rcx
0x14000f7ad  jz      short loc_14000F7CA
0x14000f7af  xor     edx, edx
0x14000f7b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f7b5  div     rcx
0x14000f7b8  cmp     rax, 30h ; '0'
0x14000f7bc  jb      loc_14000F8E3
0x14000f7c2  lea     rcx, [rcx+rcx*2]
0x14000f7c6  shl     rcx, 4
0x14000f7ca  add     rcx, 8; Size
0x14000f7ce  call    cs:__imp_malloc
0x14000f7d4  test    rax, rax
0x14000f7d7  jz      loc_14000F8E3
0x14000f7dd  mov     rcx, [rbx+38h]
0x14000f7e1  mov     [rax], rcx
0x14000f7e4  mov     [rbx+38h], rax
0x14000f7e8  mov     r8d, [rbx+34h]
0x14000f7ec  dec     r8d
0x14000f7ef  lea     rcx, [r8+r8*2]
0x14000f7f3  shl     rcx, 4
0x14000f7f7  add     rcx, 8
0x14000f7fb  add     rcx, rax
0x14000f7fe  test    r8d, r8d
0x14000f801  js      short loc_14000F819
0x14000f803  mov     rax, [rbx+40h]
0x14000f807  mov     [rcx+20h], rax
0x14000f80b  mov     [rbx+40h], rcx
0x14000f80f  sub     rcx, 30h ; '0'
0x14000f813  sub     r8d, 1
0x14000f817  jns     short loc_14000F803
0x14000f819  mov     rdi, [rbx+40h]
0x14000f81d  test    rdi, rdi
0x14000f820  jz      loc_14000F8D8
0x14000f826  mov     [rsp+48h+var_28], rdi
0x14000f82b  mov     rax, [rdi+20h]
0x14000f82f  mov     [rbx+40h], rax
0x14000f833  mov     rdx, rsi
0x14000f836  mov     rcx, rdi
0x14000f839  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000f83e  nop
0x14000f83f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f846  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f84d  mov     rax, [rax+18h]
0x14000f851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f856  add     rax, 18h
0x14000f85a  mov     [rdi+8], rax
0x14000f85e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f865  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f86c  mov     rax, [rax+18h]
0x14000f870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f875  add     rax, 18h
0x14000f879  mov     [rdi+10h], rax
0x14000f87d  mov     qword ptr [rdi+18h], 0
0x14000f885  mov     [rdi+28h], r15d
0x14000f889  inc     qword ptr [rbx+8]
0x14000f88d  mov     rax, [rbx]
0x14000f890  mov     rcx, [rax+r14*8]
0x14000f894  mov     [rdi+20h], rcx
0x14000f898  mov     rax, [rbx]
0x14000f89b  mov     [rax+r14*8], rdi
0x14000f89f  mov     rdx, [rbx+8]
0x14000f8a3  cmp     rdx, [rbx+20h]
0x14000f8a7  jbe     short loc_14000F8C1
0x14000f8a9  cmp     dword ptr [rbx+30h], 0
0x14000f8ad  jnz     short loc_14000F8C1
0x14000f8af  mov     rcx, rbx
0x14000f8b2  call    ?PickSize@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::PickSize(unsigned __int64)
0x14000f8b7  mov     edx, eax
0x14000f8b9  mov     rcx, rbx
0x14000f8bc  call    ?Rehash@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@QEAAXI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::Rehash(uint)
0x14000f8c1  mov     rax, rdi
0x14000f8c4  mov     rbx, [rsp+48h+arg_8]
0x14000f8c9  mov     rsi, [rsp+48h+arg_10]
0x14000f8ce  add     rsp, 30h
0x14000f8d2  pop     r15
0x14000f8d4  pop     r14
0x14000f8d6  pop     rdi
0x14000f8d7  retn
0x14000f8d8  mov     ecx, 80004005h; unsigned int
0x14000f8dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000f8e3  mov     ecx, 8007000Eh; unsigned int
0x14000f8e8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
