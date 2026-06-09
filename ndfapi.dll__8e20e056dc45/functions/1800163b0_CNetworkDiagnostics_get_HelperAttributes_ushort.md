# CNetworkDiagnostics::get_HelperAttributes(ushort * *)

- ea: `0x1800163b0`
- end: `0x1800165b6`
- name: `?get_HelperAttributes@CNetworkDiagnostics@@UEAAJPEAPEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x180005688`
- `0x18000bb70`
- `0x18000bd24`
- `0x18000cde4`
- `0x18000e5c8`
- `0x1800163b0`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001647d`
- `ole32!CoTaskMemFree` at `0x18001647d`
- `OLEAUT32!__imp_SysAllocString` at `0x180016566`
- `OLEAUT32!__imp_SysAllocString` at `0x180016566`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkDiagnostics::get_HelperAttributes(CNetworkDiagnostics *this, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r15
  int HelperAttributeXML; // esi
  __int64 v5; // r12
  __int64 v6; // rax
  void *v7; // r14
  __int64 v8; // r8
  unsigned int i; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  OLECHAR *v13; // rbx
  BSTR v14; // rax
  const ATL::CAtlException *v15; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 **v17; // [rsp+78h] [rbp+10h]
  OLECHAR *psz; // [rsp+80h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  if ( !*((_DWORD *)this + 30) )
    return 2147943176LL;
  HelperAttributeXML = 0;
  v5 = *((_QWORD *)this + 2);
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    psz = (OLECHAR *)(v6 + 24);
    pv = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &psz,
      "<HelperAttributes>");
    for ( i = 0; i < *(_DWORD *)(v5 + 32) && HelperAttributeXML >= 0; ++i )
    {
      HelperAttributeXML = GetHelperAttributeXML(
                             (struct tagHELPER_ATTRIBUTE *const)(*(_QWORD *)(v5 + 40) + 144LL * i),
                             (unsigned __int16 **)&pv);
      if ( HelperAttributeXML >= 0 )
      {
        v7 = pv;
        if ( pv )
        {
          v8 = -1;
          do
            ++v8;
          while ( *((_WORD *)pv + v8) );
        }
        ATL::CSimpleStringT<unsigned short,0>::Append(&psz, pv);
        CoTaskMemFree(v7);
        pv = 0;
      }
    }
    v10 = *((_QWORD *)psz - 3);
    if ( !v10 || (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10)) == 0 )
    {
      v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
      if ( !v11 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) + 24;
    if ( (unsigned __int64)"</HelperAttributes>" >= 0x10000 )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v16,
        "</HelperAttributes>");
    else
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        &v16,
        (unsigned __int16)"</HelperAttributes>");
    v12 = v16;
    ATL::CSimpleStringT<unsigned short,0>::Append(&psz, v16);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 - 24) + 8LL))(*(_QWORD *)(v12 - 24));
  }
  catch ( const ATL::CAtlException *v15 )
  {
    LODWORD(v16) = *(_DWORD *)v15;
    CoTaskMemFree(pv);
    v2 = v17;
    HelperAttributeXML = v16;
  }
  psz = (OLECHAR *)(v6 + 24);
  pv = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    &psz,
    "<HelperAttributes>");
  for ( i = 0; i < *(_DWORD *)(v5 + 32) && HelperAttributeXML >= 0; ++i )
  {
    HelperAttributeXML = GetHelperAttributeXML(
                           (struct tagHELPER_ATTRIBUTE *const)(*(_QWORD *)(v5 + 40) + 144LL * i),
                           (unsigned __int16 **)&pv);
    if ( HelperAttributeXML >= 0 )
    {
      v7 = pv;
      if ( pv )
      {
        v8 = -1;
        do
          ++v8;
        while ( *((_WORD *)pv + v8) );
      }
      ATL::CSimpleStringT<unsigned short,0>::Append(&psz, pv);
      CoTaskMemFree(v7);
      pv = 0;
    }
  }
}

```

## disassembly

```asm
0x1800163b0  mov     [rsp+arg_8], rdx
0x1800163b5  push    rbx
0x1800163b6  push    rsi
0x1800163b7  push    rdi
0x1800163b8  push    r12
0x1800163ba  push    r14
0x1800163bc  push    r15
0x1800163be  sub     rsp, 38h
0x1800163c2  mov     r15, rdx
0x1800163c5  xor     edi, edi
0x1800163c7  cmp     [rcx+78h], edi
0x1800163ca  jnz     short loc_1800163D6
0x1800163cc  mov     eax, 80070308h
0x1800163d1  jmp     loc_18001659C
0x1800163d6  mov     esi, edi
0x1800163d8  mov     r12, [rcx+10h]
0x1800163dc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800163e3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800163ea  mov     rax, [rax+18h]
0x1800163ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163f3  add     rax, 18h
0x1800163f7  mov     [rsp+68h+psz], rax
0x1800163ff  mov     [rsp+68h+pv], rdi
0x180016407  lea     rdx, aHelperattribut; "<HelperAttributes>"
0x18001640e  lea     rcx, [rsp+68h+psz]
0x180016416  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18001641b  mov     ebx, edi
0x18001641d  cmp     ebx, [r12+20h]
0x180016422  jnb     short loc_18001648F
0x180016424  test    esi, esi
0x180016426  js      short loc_18001648F
0x180016428  mov     eax, ebx
0x18001642a  lea     rcx, [rax+rax*8]
0x18001642e  shl     rcx, 4
0x180016432  add     rcx, [r12+28h]; struct tagHELPER_ATTRIBUTE *
0x180016437  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x18001643f  call    ?GetHelperAttributeXML@@YAJQEAUtagHELPER_ATTRIBUTE@@PEAPEAG@Z; GetHelperAttributeXML(tagHELPER_ATTRIBUTE * const,ushort * *)
0x180016444  mov     esi, eax
0x180016446  test    eax, eax
0x180016448  js      short loc_18001648B
0x18001644a  mov     r14, [rsp+68h+pv]
0x180016452  test    r14, r14
0x180016455  jnz     short loc_18001645C
0x180016457  mov     r8d, edi
0x18001645a  jmp     short loc_18001646A
0x18001645c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016460  inc     r8
0x180016463  cmp     [r14+r8*2], di
0x180016468  jnz     short loc_180016460
0x18001646a  mov     rdx, r14
0x18001646d  lea     rcx, [rsp+68h+psz]
0x180016475  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001647a  mov     rcx, r14; pv
0x18001647d  call    cs:__imp_CoTaskMemFree
0x180016483  mov     [rsp+68h+pv], rdi
0x18001648b  inc     ebx
0x18001648d  jmp     short loc_18001641D
0x18001648f  mov     rax, [rsp+68h+psz]
0x180016497  mov     rcx, [rax-18h]
0x18001649b  test    rcx, rcx
0x18001649e  jz      short loc_1800164B4
0x1800164a0  mov     rax, [rcx]
0x1800164a3  mov     rax, [rax+20h]
0x1800164a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ac  mov     rcx, rax
0x1800164af  test    rax, rax
0x1800164b2  jnz     short loc_1800164D7
0x1800164b4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800164bb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800164c2  mov     rax, [rax+20h]
0x1800164c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164cb  mov     rcx, rax
0x1800164ce  test    rax, rax
0x1800164d1  jz      loc_1800165AA
0x1800164d7  mov     rax, [rcx]
0x1800164da  mov     rax, [rax+18h]
0x1800164de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164e3  add     rax, 18h
0x1800164e7  mov     [rsp+68h+arg_0], rax
0x1800164ec  lea     rdx, aHelperattribut_0; "</HelperAttributes>"
0x1800164f3  lea     rcx, [rsp+68h+arg_0]
0x1800164f8  cmp     rdx, 10000h
0x1800164ff  jnb     short loc_18001650B
0x180016501  movzx   edx, dx
0x180016504  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180016509  jmp     short loc_180016511
0x18001650b  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180016510  nop
0x180016511  mov     rbx, [rsp+68h+arg_0]
0x180016516  mov     r8d, [rbx-10h]
0x18001651a  mov     rdx, rbx
0x18001651d  lea     rcx, [rsp+68h+psz]
0x180016525  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001652a  nop
0x18001652b  lea     rdx, [rbx-18h]
0x18001652f  or      eax, 0FFFFFFFFh
0x180016532  lock xadd [rdx+10h], eax
0x180016537  sub     eax, 1
0x18001653a  jg      short loc_18001654C
0x18001653c  mov     rcx, [rdx]
0x18001653f  mov     rax, [rcx]
0x180016542  mov     rax, [rax+8]
0x180016546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654b  nop
0x18001654c  jmp     short loc_180016557
0x18001654e  mov     r15, [rsp+68h+arg_8]
0x180016553  mov     esi, dword ptr [rsp+68h+arg_0]
0x180016557  mov     rbx, [rsp+68h+psz]
0x18001655f  test    esi, esi
0x180016561  js      short loc_18001657A
0x180016563  mov     rcx, rbx; psz
0x180016566  call    cs:__imp_SysAllocString
0x18001656c  mov     [r15], rax
0x18001656f  mov     ecx, 8007000Eh
0x180016574  test    rax, rax
0x180016577  cmovz   esi, ecx
0x18001657a  lea     rdx, [rbx-18h]
0x18001657e  or      ecx, 0FFFFFFFFh
0x180016581  lock xadd [rdx+10h], ecx
0x180016586  sub     ecx, 1
0x180016589  jg      short loc_18001659A
0x18001658b  mov     rcx, [rdx]
0x18001658e  mov     r8, [rcx]
0x180016591  mov     rax, [r8+8]
0x180016595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659a  mov     eax, esi
0x18001659c  add     rsp, 38h
0x1800165a0  pop     r15
0x1800165a2  pop     r14
0x1800165a4  pop     r12
0x1800165a6  pop     rdi
0x1800165a7  pop     rsi
0x1800165a8  pop     rbx
0x1800165a9  retn
0x1800165aa  mov     ecx, 80004005h; int
0x1800165af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
