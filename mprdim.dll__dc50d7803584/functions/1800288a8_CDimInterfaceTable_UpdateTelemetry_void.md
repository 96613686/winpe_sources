# CDimInterfaceTable::UpdateTelemetry(void)

- ea: `0x1800288a8`
- end: `0x180028cad`
- name: `?UpdateTelemetry@CDimInterfaceTable@@QEAAXXZ`
- size: `1029`
- prototype: `void __fastcall(CDimInterfaceTable *__hidden this)`
- caller_count: `8`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800057f0`
- `0x18000e270`
- `0x18000e540`
- `0x18000e8a0`
- `0x18000f890`
- `0x180010090`
- `0x1800101b0`
- `0x180011eb0`

## callees

- `0x180005550`
- `0x180006ce0`
- `0x18000b654`
- `0x1800219f4`
- `0x180022a18`
- `0x180022ab0`
- `0x180023000`
- `0x180023448`
- `0x1800288a8`
- `0x180030210`
- `0x180048010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180028c78`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028c86`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028c78`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028c86`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDimInterfaceTable::UpdateTelemetry(CDimInterfaceTable *this, __int64 a2, const char *a3)
{
  CDimInterfaceTable *v3; // rbx
  int v4; // r12d
  int v5; // r13d
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  int v8; // r15d
  int v9; // r14d
  bool v10; // cf
  int v11; // eax
  int v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  _QWORD *i; // rax
  bool v16; // zf
  _DWORD *v17; // r14
  _DWORD *v18; // r15
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  __int64 j; // rdx
  __int64 v22; // rax
  int v23; // r9d
  __int64 v24; // rcx
  _QWORD *k; // rax
  CDimInterfaceTable *v26; // rax
  int v27; // ecx
  int v28; // [rsp+60h] [rbp-B8h]
  int v29; // [rsp+64h] [rbp-B4h]
  int v30; // [rsp+70h] [rbp-A8h]
  int v31; // [rsp+74h] [rbp-A4h]
  CDimInterfaceTable *v32; // [rsp+78h] [rbp-A0h]
  _DWORD *v33; // [rsp+80h] [rbp-98h]
  _DWORD *v34; // [rsp+88h] [rbp-90h]
  CDimInterfaceTable *v35; // [rsp+90h] [rbp-88h]
  _BYTE v36[32]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v37[96]; // [rsp+B8h] [rbp-60h] BYREF
  int v38; // [rsp+120h] [rbp+8h]
  int v39; // [rsp+128h] [rbp+10h]
  unsigned int v40; // [rsp+130h] [rbp+18h]
  int v41; // [rsp+138h] [rbp+20h]

  v3 = g_pCDimInterfaceTable;
  v32 = g_pCDimInterfaceTable;
  v35 = g_pCDimInterfaceTable;
  v41 = 0;
  v4 = 0;
  v5 = 0;
  v39 = 0;
  v30 = 0;
  v38 = 0;
  v31 = 0;
  v40 = 0;
  v33 = 0;
  v34 = 0;
  v29 = 0;
  std::_Tree_val<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Tree_val<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>(
    (__int64)v36,
    a2,
    a3);
  CDimInterfaceTable::AcquireShared(v3);
  v6 = (_QWORD *)*((_QWORD *)v3 + 28);
  v7 = (_QWORD *)*v6;
  v8 = 0;
  v9 = 0;
  while ( v7 != v6 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 72LL))(v7[4]) == 2 )
    {
      v40 = ++v8;
      (**(void (__fastcall ***)(_QWORD))v7[4])(v7[4]);
      v10 = ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 104LL))(v7[4]) & 0x2000) != 0;
      v11 = v39 + 1;
      if ( !v10 )
        v11 = v39;
      v39 = v11;
      v10 = ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 104LL))(v7[4]) & 0x1000) != 0;
      v12 = v38 + 1;
      if ( !v10 )
        v12 = v38;
      v38 = v12;
      if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 104LL))(v7[4]) & 4) != 0 )
      {
        v13 = std::map<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>>::operator[](
                (__int64)v36,
                (__int128 *)(v7[4] + 3104LL));
        ++*(_DWORD *)v13;
      }
      if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 120LL))(v7[4]) & 0x100) != 0 )
      {
        ++v9;
        if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 104LL))(v7[4]) & 4) != 0 )
          ++v4;
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 456LL))(v7[4]) == 9 )
      {
        ++v41;
        if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 104LL))(v7[4]) & 4) != 0 )
          ++v5;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7[4] + 8LL))(v7[4]);
      v30 = v39;
      v31 = v38;
    }
    if ( !*((_BYTE *)v7 + 49) )
    {
      v14 = v7[2];
      if ( *(_BYTE *)(v14 + 49) )
      {
        for ( i = (_QWORD *)v7[1]; !*((_BYTE *)i + 49) && v7 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v7 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v14);
      }
      v7 = i;
    }
  }
  v28 = v9;
  try
  {
    v16 = v8 == 0;
    v17 = 0;
    v18 = 0;
    if ( !v16 )
    {
      v18 = operator new[](saturated_mul(v40, 4u));
      v33 = v18;
      v17 = operator new[](saturated_mul(v40, 4u));
      v34 = v17;
      v19 = (_QWORD *)*((_QWORD *)v32 + 28);
      v20 = (_QWORD *)*v19;
      while ( v20 != v19 )
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v20[4] + 72LL))(v20[4]) == 2 )
        {
          for ( j = 0; j != 2; ++j )
          {
            v22 = v20[4];
            v23 = *(_DWORD *)(v22 + 12 * j + 964) >> 10;
            if ( *(_DWORD *)(v22 + 12 * j + 968) )
              v17[v29] = v23;
            else
              v18[v29] = v23;
          }
          ++v29;
        }
        if ( !*((_BYTE *)v20 + 49) )
        {
          v24 = v20[2];
          if ( *(_BYTE *)(v24 + 49) )
          {
            for ( k = (_QWORD *)v20[1]; !*((_BYTE *)k + 49) && v20 == (_QWORD *)k[2]; k = (_QWORD *)k[1] )
              v20 = k;
          }
          else
          {
            k = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v24);
          }
          v20 = k;
        }
      }
    }
  }
  catch ( std::bad_alloc )
  {
    v26 = v35;
    v39 = v30;
    v38 = v31;
    v18 = v33;
    v17 = v34;
    goto LABEL_45;
  }
  v26 = v32;
LABEL_45:
  CDimInterfaceTable::ReleaseShared(v26);
  std::_Tree<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Tree<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>(
    (__int64)v37,
    (__int64)v36);
  CDimSqm::UpdateTelemetry(v27, v40, (unsigned int)v37, v28, v41, v4, v5, v39, v38, (__int64)v18, (__int64)v17);
  if ( v18 )
    operator delete[](v18);
  if ( v17 )
    operator delete[](v17);
  std::_Tree<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned long,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,unsigned long>>,0>>((__int64)v36);
}

```

## disassembly

```asm
0x1800288a8  mov     r11, rsp
0x1800288ab  mov     [r11+8], rcx
0x1800288af  push    rbx
0x1800288b0  push    rsi
0x1800288b1  push    rdi
0x1800288b2  push    r12
0x1800288b4  push    r13
0x1800288b6  push    r14
0x1800288b8  push    r15
0x1800288ba  sub     rsp, 0E0h
0x1800288c1  mov     rbx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x1800288c8  mov     [rsp+118h+var_A0], rbx
0x1800288cd  mov     [rsp+118h+var_88], rbx
0x1800288d5  xor     esi, esi
0x1800288d7  mov     [rsp+118h+arg_18], esi
0x1800288de  mov     r12d, esi
0x1800288e1  mov     r13d, esi
0x1800288e4  mov     eax, esi
0x1800288e6  mov     [rsp+118h+arg_8], eax
0x1800288ed  mov     [rsp+118h+var_A8], eax
0x1800288f1  mov     [rsp+118h+arg_0], eax
0x1800288f8  mov     [rsp+118h+var_A4], eax
0x1800288fc  mov     [rsp+118h+arg_10], esi
0x180028903  mov     [rsp+118h+var_98], rsi
0x18002890b  mov     [rsp+118h+var_90], rsi
0x180028913  mov     [rsp+118h+var_B4], esi
0x180028917  lea     rcx, [r11-80h]
0x18002891b  call    ??0?$_Tree_val@V?$_Tmap_traits@U_GUID@@KU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@QEAA@AEBU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@1@@Z; std::_Tree_val<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Tree_val<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>(_ROUTINGDOMAIN_COMP const &,std::allocator<std::pair<_GUID const,ulong>>)
0x180028920  nop
0x180028921  mov     rcx, rbx; this
0x180028924  call    ?AcquireShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireShared(void)
0x180028929  mov     rdi, [rbx+0E0h]
0x180028930  mov     rbx, [rdi]
0x180028933  mov     r15d, esi
0x180028936  mov     r14d, esi
0x180028939  cmp     rbx, rdi
0x18002893c  jz      loc_180028ABB
0x180028942  mov     rcx, [rbx+20h]
0x180028946  mov     rax, [rcx]
0x180028949  mov     rax, [rax+48h]
0x18002894d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028952  cmp     eax, 2
0x180028955  jnz     loc_180028A7F
0x18002895b  inc     r15d
0x18002895e  mov     [rsp+118h+arg_10], r15d
0x180028966  mov     rcx, [rbx+20h]
0x18002896a  mov     rax, [rcx]
0x18002896d  mov     rax, [rax]
0x180028970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028975  mov     rcx, [rbx+20h]
0x180028979  mov     rax, [rcx]
0x18002897c  mov     rax, [rax+68h]
0x180028980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028985  bt      eax, 0Dh
0x180028989  mov     ecx, [rsp+118h+arg_8]
0x180028990  lea     eax, [rcx+1]
0x180028993  cmovnb  eax, ecx
0x180028996  mov     [rsp+118h+arg_8], eax
0x18002899d  mov     rcx, [rbx+20h]
0x1800289a1  mov     rax, [rcx]
0x1800289a4  mov     rax, [rax+68h]
0x1800289a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289ad  bt      eax, 0Ch
0x1800289b1  mov     ecx, [rsp+118h+arg_0]
0x1800289b8  lea     eax, [rcx+1]
0x1800289bb  cmovnb  eax, ecx
0x1800289be  mov     [rsp+118h+arg_0], eax
0x1800289c5  mov     rcx, [rbx+20h]
0x1800289c9  mov     rax, [rcx]
0x1800289cc  mov     rax, [rax+68h]
0x1800289d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289d5  test    al, 4
0x1800289d7  jz      short loc_1800289F3
0x1800289d9  mov     rdx, [rbx+20h]
0x1800289dd  add     rdx, 0C20h
0x1800289e4  lea     rcx, [rsp+118h+var_80]
0x1800289ec  call    ??A?$map@U_GUID@@KU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@QEAAAEAKAEBU_GUID@@@Z; std::map<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>>::operator[](_GUID const &)
0x1800289f1  inc     dword ptr [rax]
0x1800289f3  mov     rcx, [rbx+20h]
0x1800289f7  mov     rax, [rcx]
0x1800289fa  mov     rax, [rax+78h]
0x1800289fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a03  bt      eax, 8
0x180028a07  jnb     short loc_180028A23
0x180028a09  inc     r14d
0x180028a0c  mov     rcx, [rbx+20h]
0x180028a10  mov     rax, [rcx]
0x180028a13  mov     rax, [rax+68h]
0x180028a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a1c  test    al, 4
0x180028a1e  jz      short loc_180028A23
0x180028a20  inc     r12d
0x180028a23  mov     rcx, [rbx+20h]
0x180028a27  mov     rax, [rcx]
0x180028a2a  mov     rax, [rax+1C8h]
0x180028a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a36  cmp     eax, 9
0x180028a39  jnz     short loc_180028A59
0x180028a3b  inc     [rsp+118h+arg_18]
0x180028a42  mov     rcx, [rbx+20h]
0x180028a46  mov     rax, [rcx]
0x180028a49  mov     rax, [rax+68h]
0x180028a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a52  test    al, 4
0x180028a54  jz      short loc_180028A59
0x180028a56  inc     r13d
0x180028a59  mov     rcx, [rbx+20h]
0x180028a5d  mov     rax, [rcx]
0x180028a60  mov     rax, [rax+8]
0x180028a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a69  mov     eax, [rsp+118h+arg_8]
0x180028a70  mov     [rsp+118h+var_A8], eax
0x180028a74  mov     eax, [rsp+118h+arg_0]
0x180028a7b  mov     [rsp+118h+var_A4], eax
0x180028a7f  cmp     [rbx+31h], sil
0x180028a83  jnz     loc_180028939
0x180028a89  mov     rcx, [rbx+10h]
0x180028a8d  cmp     [rcx+31h], sil
0x180028a91  jnz     short loc_180028A9A
0x180028a93  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x180028a98  jmp     short loc_180028AB3
0x180028a9a  mov     rax, [rbx+8]
0x180028a9e  jmp     short loc_180028AAD
0x180028aa0  cmp     rbx, [rax+10h]
0x180028aa4  jnz     short loc_180028AB3
0x180028aa6  mov     rbx, rax
0x180028aa9  mov     rax, [rax+8]
0x180028aad  cmp     [rax+31h], sil
0x180028ab1  jz      short loc_180028AA0
0x180028ab3  mov     rbx, rax
0x180028ab6  jmp     loc_180028939
0x180028abb  mov     [rsp+118h+var_B0], r12d
0x180028ac0  mov     [rsp+118h+var_AC], r13d
0x180028ac5  mov     [rsp+118h+var_B8], r14d
0x180028aca  test    r15d, r15d
0x180028acd  mov     r14, rsi
0x180028ad0  mov     r15, rsi
0x180028ad3  jz      loc_180028BC6
0x180028ad9  mov     ebx, [rsp+118h+arg_10]
0x180028ae0  mov     edi, 4
0x180028ae5  mov     eax, edi
0x180028ae7  mul     rbx
0x180028aea  lea     r14, [rdi-5]
0x180028aee  cmovb   rax, r14
0x180028af2  mov     rcx, rax; unsigned __int64
0x180028af5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028afa  mov     r15, rax
0x180028afd  mov     [rsp+118h+var_98], rax
0x180028b05  mov     eax, edi
0x180028b07  mul     rbx
0x180028b0a  cmovb   rax, r14
0x180028b0e  mov     rcx, rax; unsigned __int64
0x180028b11  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028b16  mov     r14, rax
0x180028b19  mov     [rsp+118h+var_90], rax
0x180028b21  mov     rax, [rsp+118h+var_A0]
0x180028b26  mov     rdi, [rax+0E0h]
0x180028b2d  mov     rbx, [rdi]
0x180028b30  cmp     rbx, rdi
0x180028b33  jz      loc_180028BC6
0x180028b39  mov     rcx, [rbx+20h]
0x180028b3d  mov     rax, [rcx]
0x180028b40  mov     rax, [rax+48h]
0x180028b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b49  cmp     eax, 2
0x180028b4c  jnz     short loc_180028B8E
0x180028b4e  mov     r10d, [rsp+118h+var_B4]
0x180028b53  mov     rdx, rsi
0x180028b56  lea     rcx, [rdx+rdx*2]
0x180028b5a  mov     rax, [rbx+20h]
0x180028b5e  mov     r9d, [rax+rcx*4+3C4h]
0x180028b66  shr     r9d, 0Ah
0x180028b6a  cmp     [rax+rcx*4+3C8h], esi
0x180028b71  jnz     short loc_180028B79
0x180028b73  mov     [r15+r10*4], r9d
0x180028b77  jmp     short loc_180028B7D
0x180028b79  mov     [r14+r10*4], r9d
0x180028b7d  inc     rdx
0x180028b80  cmp     rdx, 2
0x180028b84  jnz     short loc_180028B56
0x180028b86  inc     r10d
0x180028b89  mov     [rsp+118h+var_B4], r10d
0x180028b8e  cmp     [rbx+31h], sil
0x180028b92  jnz     short loc_180028B30
0x180028b94  mov     rcx, [rbx+10h]
0x180028b98  cmp     [rcx+31h], sil
0x180028b9c  jnz     short loc_180028BA5
0x180028b9e  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x180028ba3  jmp     short loc_180028BBE
0x180028ba5  mov     rax, [rbx+8]
0x180028ba9  jmp     short loc_180028BB8
0x180028bab  cmp     rbx, [rax+10h]
0x180028baf  jnz     short loc_180028BBE
0x180028bb1  mov     rbx, rax
0x180028bb4  mov     rax, [rax+8]
0x180028bb8  cmp     [rax+31h], sil
0x180028bbc  jz      short loc_180028BAB
0x180028bbe  mov     rbx, rax
0x180028bc1  jmp     loc_180028B30
0x180028bc6  mov     rax, [rsp+118h+var_A0]
0x180028bcb  jmp     short loc_180028C05
0x180028bcd  mov     rax, [rsp+118h+var_88]
0x180028bd5  mov     r12d, [rsp+118h+var_B0]
0x180028bda  mov     r13d, [rsp+118h+var_AC]
0x180028bdf  mov     ecx, [rsp+118h+var_A8]
0x180028be3  mov     [rsp+118h+arg_8], ecx
0x180028bea  mov     ecx, [rsp+118h+var_A4]
0x180028bee  mov     [rsp+118h+arg_0], ecx
0x180028bf5  mov     r15, [rsp+118h+var_98]
0x180028bfd  mov     r14, [rsp+118h+var_90]
0x180028c05  mov     rcx, rax; this
0x180028c08  call    ?ReleaseShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseShared(void)
0x180028c0d  lea     rdx, [rsp+118h+var_80]
0x180028c15  lea     rcx, [rsp+118h+var_60]
0x180028c1d  call    ??0?$_Tree@V?$_Tmap_traits@U_GUID@@KU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Tree<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>(std::_Tree<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>> const &)
0x180028c22  mov     [rsp+118h+var_C8], r14
0x180028c27  mov     [rsp+118h+var_D0], r15
0x180028c2c  mov     eax, [rsp+118h+arg_0]
0x180028c33  mov     [rsp+118h+var_D8], eax
0x180028c37  mov     eax, [rsp+118h+arg_8]
0x180028c3e  mov     [rsp+118h+var_E0], eax
0x180028c42  mov     [rsp+118h+var_E8], r13d
0x180028c47  mov     [rsp+118h+var_F0], r12d
0x180028c4c  mov     eax, [rsp+118h+arg_18]
0x180028c53  mov     [rsp+118h+var_F8], eax
0x180028c57  mov     r9d, [rsp+118h+var_B8]
0x180028c5c  lea     r8, [rsp+118h+var_60]
0x180028c64  mov     edx, [rsp+118h+arg_10]
0x180028c6b  call    ?UpdateTelemetry@CDimSqm@@QEAAXKV?$map@U_GUID@@KU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@KKKKKKPEAK1@Z; CDimSqm::UpdateTelemetry(ulong,std::map<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>>,ulong,ulong,ulong,ulong,ulong,ulong,ulong *,ulong *)
0x180028c70  test    r15, r15
0x180028c73  jz      short loc_180028C7E
0x180028c75  mov     rcx, r15
0x180028c78  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028c7e  test    r14, r14
0x180028c81  jz      short loc_180028C8D
0x180028c83  mov     rcx, r14
0x180028c86  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028c8c  nop
0x180028c8d  lea     rcx, [rsp+118h+var_80]
0x180028c95  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@KU_ROUTINGDOMAIN_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ulong,_ROUTINGDOMAIN_COMP,std::allocator<std::pair<_GUID const,ulong>>,0>>(void)
0x180028c9a  add     rsp, 0E0h
0x180028ca1  pop     r15
0x180028ca3  pop     r14
0x180028ca5  pop     r13
0x180028ca7  pop     r12
0x180028ca9  pop     rdi
0x180028caa  pop     rsi
0x180028cab  pop     rbx
0x180028cac  retn
```
