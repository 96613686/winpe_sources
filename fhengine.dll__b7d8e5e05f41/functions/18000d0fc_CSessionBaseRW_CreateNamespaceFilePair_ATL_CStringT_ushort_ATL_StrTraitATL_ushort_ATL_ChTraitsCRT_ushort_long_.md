# CSessionBaseRW::CreateNamespaceFilePair(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,long,SmartPtr<CNamespaceRecord> &,SmartPtr<CFileRecord> &)

- ea: `0x18000d0fc`
- end: `0x18000d33f`
- name: `?CreateNamespaceFilePair@CSessionBaseRW@@IEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@JAEAV?$SmartPtr@VCNamespaceRecord@@@@AEAV?$SmartPtr@VCFileRecord@@@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, __int64 **, __int64 **)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18000d4f4`
- `0x180010de8`
- `0x18001cb74`
- `0x18001eaf0`

## callees

- `0x1800025b0`
- `0x1800062d0`
- `0x180007970`
- `0x180007a1c`
- `0x180009008`
- `0x1800090f8`
- `0x180009258`
- `0x1800093a8`
- `0x180009404`
- `0x180009560`
- `0x18000960c`
- `0x18000d0fc`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::CreateNamespaceFilePair(__int64 a1, _QWORD *a2, int a3, __int64 **a4, __int64 **a5)
{
  CNamespaceRecord *v9; // rax
  CFileRecord *v10; // rax
  __int64 **v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rcx
  _DWORD *v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  _QWORD *v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  _QWORD *v22; // rcx
  int v23; // edx
  __int64 v24; // rbx
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  const char *v28; // r9
  __int64 v30; // [rsp+78h] [rbp+10h] BYREF

  v9 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
    v9 = CNamespaceRecord::CNamespaceRecord(v9, (__int64 *)(a1 + 16), a1 + 24);
  SmartPtr<CNamespaceRecord>::operator=(a4, v9);
  if ( !*a4 || !**a4 )
  {
    v21 = -2147024882;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v27 = 101;
    v28 = "NamspaceRecord";
LABEL_28:
    WPP_SF_s(v26[2], v27, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v28);
    goto LABEL_29;
  }
  v10 = (CFileRecord *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
    v10 = CFileRecord::CFileRecord(v10, (__int64 *)(a1 + 16), a1 + 24);
  v11 = a5;
  SmartPtr<CFileRecord>::operator=(a5, v10);
  v12 = *v11;
  if ( !*v11 || !*v12 )
  {
    v21 = -2147024882;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v27 = 102;
    v28 = "FileRecord";
    goto LABEL_28;
  }
  v13 = *v12;
  *(_DWORD *)(v13 + 76) = 1;
  *(_WORD *)(v13 + 40) = 1;
  v14 = a3;
  if ( !a3 )
    v14 = *(_DWORD *)(a1 + 36);
  v15 = **v11;
  *(_DWORD *)(v15 + 76) = 1;
  *(_DWORD *)(v15 + 56) = v14;
  v16 = (_DWORD *)**v11;
  v17 = v16[14];
  v16[19] = 1;
  v16[16] = v17;
  v18 = **v11;
  v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v30,
          a2);
  v20 = CFileRecord::SetName(v18, v19);
  v21 = v20;
  if ( v20 >= 0 )
  {
    *(_WORD *)(**a4 + 40) = 16;
    if ( !a3 )
      a3 = *(_DWORD *)(a1 + 36);
    *(_DWORD *)(**a4 + 76) = a3;
    *(_DWORD *)(**a4 + 80) = -1;
    v24 = **a4;
    v25 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v30,
            a2);
    v20 = CNamespaceRecord::SetName(v24, v25);
    v21 = v20;
    if ( v20 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 104;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 103;
LABEL_15:
      WPP_SF_Sd(v22[2], v23, (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, *a2, v20);
    }
  }
LABEL_29:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 24LL));
  return v21;
}

```

## disassembly

```asm
0x18000d0fc  push    rbx
0x18000d0fe  push    rbp
0x18000d0ff  push    rsi
0x18000d100  push    rdi
0x18000d101  push    r14
0x18000d103  push    r15
0x18000d105  sub     rsp, 38h
0x18000d109  mov     r14, r9
0x18000d10c  mov     ebp, r8d
0x18000d10f  mov     r15, rdx
0x18000d112  mov     rsi, rcx
0x18000d115  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d11c  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000d121  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d126  test    rax, rax
0x18000d129  jz      short loc_18000D13B
0x18000d12b  lea     r8, [rsi+18h]
0x18000d12f  lea     rdx, [rsi+10h]
0x18000d133  mov     rcx, rax; this
0x18000d136  call    ??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000d13b  mov     rdx, rax
0x18000d13e  mov     rcx, r14
0x18000d141  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::operator=(CNamespaceRecord *)
0x18000d146  mov     rax, [r14]
0x18000d149  test    rax, rax
0x18000d14c  jz      loc_18000D2E7
0x18000d152  cmp     qword ptr [rax], 0
0x18000d156  jz      loc_18000D2E7
0x18000d15c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d163  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000d168  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d16d  test    rax, rax
0x18000d170  jz      short loc_18000D182
0x18000d172  lea     r8, [rsi+18h]
0x18000d176  lea     rdx, [rsi+10h]
0x18000d17a  mov     rcx, rax; this
0x18000d17d  call    ??0CFileRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CFileRecord::CFileRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000d182  mov     rdx, rax
0x18000d185  mov     rbx, [rsp+68h+arg_20]
0x18000d18d  mov     rcx, rbx
0x18000d190  call    ??4?$SmartPtr@VCFileRecord@@@@QEAAAEAV0@PEAVCFileRecord@@@Z; SmartPtr<CFileRecord>::operator=(CFileRecord *)
0x18000d195  mov     rax, [rbx]
0x18000d198  test    rax, rax
0x18000d19b  jz      loc_18000D2B8
0x18000d1a1  cmp     qword ptr [rax], 0
0x18000d1a5  jz      loc_18000D2B8
0x18000d1ab  mov     rax, [rax]
0x18000d1ae  mov     edi, 1
0x18000d1b3  mov     [rax+4Ch], edi
0x18000d1b6  mov     [rax+28h], di
0x18000d1ba  test    ebp, ebp
0x18000d1bc  mov     edx, ebp
0x18000d1be  jnz     short loc_18000D1C3
0x18000d1c0  mov     edx, [rsi+24h]
0x18000d1c3  mov     rax, [rbx]
0x18000d1c6  mov     rcx, [rax]
0x18000d1c9  mov     [rcx+4Ch], edi
0x18000d1cc  mov     [rcx+38h], edx
0x18000d1cf  mov     rax, [rbx]
0x18000d1d2  mov     rcx, [rax]
0x18000d1d5  mov     eax, [rcx+38h]
0x18000d1d8  mov     [rcx+4Ch], edi
0x18000d1db  mov     [rcx+40h], eax
0x18000d1de  mov     rax, [rbx]
0x18000d1e1  mov     rbx, [rax]
0x18000d1e4  mov     rdx, r15
0x18000d1e7  lea     rcx, [rsp+68h+arg_8]
0x18000d1ec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000d1f1  mov     rdx, rax
0x18000d1f4  mov     rcx, rbx
0x18000d1f7  call    ?SetName@CFileRecord@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::SetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000d1fc  mov     ebx, eax
0x18000d1fe  test    eax, eax
0x18000d200  jns     short loc_18000D244
0x18000d202  lea     rdx, WPP_GLOBAL_Control
0x18000d209  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d210  cmp     rcx, rdx
0x18000d213  jz      loc_18000D324
0x18000d219  test    [rcx+1Ch], dil
0x18000d21d  jz      loc_18000D324
0x18000d223  mov     edx, 67h ; 'g'
0x18000d228  mov     [rsp+68h+var_48], eax
0x18000d22c  mov     r9, [r15]
0x18000d22f  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d236  mov     rcx, [rcx+10h]
0x18000d23a  call    WPP_SF_Sd
0x18000d23f  jmp     loc_18000D324
0x18000d244  mov     rax, [r14]
0x18000d247  mov     rcx, [rax]
0x18000d24a  mov     word ptr [rcx+28h], 10h
0x18000d250  test    ebp, ebp
0x18000d252  jnz     short loc_18000D257
0x18000d254  mov     ebp, [rsi+24h]
0x18000d257  mov     rax, [r14]
0x18000d25a  mov     rcx, [rax]
0x18000d25d  mov     [rcx+4Ch], ebp
0x18000d260  mov     rax, [r14]
0x18000d263  mov     rcx, [rax]
0x18000d266  mov     dword ptr [rcx+50h], 0FFFFFFFFh
0x18000d26d  mov     rax, [r14]
0x18000d270  mov     rbx, [rax]
0x18000d273  mov     rdx, r15
0x18000d276  lea     rcx, [rsp+68h+arg_8]
0x18000d27b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000d280  mov     rdx, rax
0x18000d283  mov     rcx, rbx
0x18000d286  call    ?SetName@CNamespaceRecord@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CNamespaceRecord::SetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000d28b  mov     ebx, eax
0x18000d28d  test    eax, eax
0x18000d28f  jns     loc_18000D324
0x18000d295  lea     rdx, WPP_GLOBAL_Control
0x18000d29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a3  cmp     rcx, rdx
0x18000d2a6  jz      short loc_18000D324
0x18000d2a8  test    [rcx+1Ch], dil
0x18000d2ac  jz      short loc_18000D324
0x18000d2ae  mov     edx, 68h ; 'h'
0x18000d2b3  jmp     loc_18000D228
0x18000d2b8  mov     ebx, 8007000Eh
0x18000d2bd  lea     rdx, WPP_GLOBAL_Control
0x18000d2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2cb  cmp     rcx, rdx
0x18000d2ce  jz      short loc_18000D324
0x18000d2d0  mov     edi, 1
0x18000d2d5  test    [rcx+1Ch], dil
0x18000d2d9  jz      short loc_18000D324
0x18000d2db  lea     edx, [rdi+65h]
0x18000d2de  lea     r9, aFilerecord; "FileRecord"
0x18000d2e5  jmp     short loc_18000D314
0x18000d2e7  mov     ebx, 8007000Eh
0x18000d2ec  lea     rdx, WPP_GLOBAL_Control
0x18000d2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2fa  cmp     rcx, rdx
0x18000d2fd  jz      short loc_18000D324
0x18000d2ff  mov     edi, 1
0x18000d304  test    [rcx+1Ch], dil
0x18000d308  jz      short loc_18000D324
0x18000d30a  lea     edx, [rdi+64h]
0x18000d30d  lea     r9, aNamspacerecord; "NamspaceRecord"
0x18000d314  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d31b  mov     rcx, [rcx+10h]
0x18000d31f  call    WPP_SF_s
0x18000d324  mov     rcx, [r15]
0x18000d327  sub     rcx, 18h; this
0x18000d32b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d330  mov     eax, ebx
0x18000d332  add     rsp, 38h
0x18000d336  pop     r15
0x18000d338  pop     r14
0x18000d33a  pop     rdi
0x18000d33b  pop     rsi
0x18000d33c  pop     rbp
0x18000d33d  pop     rbx
0x18000d33e  retn
```
