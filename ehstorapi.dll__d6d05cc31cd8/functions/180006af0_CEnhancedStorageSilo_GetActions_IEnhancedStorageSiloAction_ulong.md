# CEnhancedStorageSilo::GetActions(IEnhancedStorageSiloAction * * *,ulong *)

- ea: `0x180006af0`
- end: `0x180007089`
- name: `?GetActions@CEnhancedStorageSilo@@UEAAJPEAPEAPEAUIEnhancedStorageSiloAction@@PEAK@Z`
- size: `1433`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *__hidden this, struct IEnhancedStorageSiloAction ***, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000124c`
- `0x180003924`
- `0x180003bdc`
- `0x180003c54`
- `0x180003df0`
- `0x180003ed0`
- `0x180006024`
- `0x180006208`
- `0x180006988`
- `0x180006af0`
- `0x180007430`
- `0x1800084cc`
- `0x1800085c4`
- `0x180008890`
- `0x180008a7c`
- `0x18000c4c2`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f16`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::GetActions(
        CEnhancedStorageSilo *this,
        struct IEnhancedStorageSiloAction ***a2,
        unsigned int *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int v9; // r14d
  void *v10; // r13
  int RegistryProperty; // eax
  unsigned int v12; // r8d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  _WORD *v16; // rcx
  unsigned int v17; // r9d
  char *v18; // rdx
  bool v19; // zf
  SIZE_T v20; // rbx
  unsigned int v21; // ebx
  const unsigned __int16 *v22; // r15
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rdi
  const unsigned __int16 *v25; // r12
  unsigned __int64 v26; // rdi
  const unsigned __int16 *v27; // rbx
  _QWORD *v28; // rsi
  CEnhancedStorageSilo *v29; // rcx
  __int64 v30; // rbx
  int IndirectString; // eax
  unsigned int v32; // ebx
  unsigned int i; // ebx
  __int64 v34; // rcx
  _QWORD *v36; // rcx
  int v37; // edx
  int v38; // r9d
  int v39; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v40; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-B8h]
  _QWORD *v44; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v45; // [rsp+58h] [rbp-A8h]
  CEnhancedStorageSilo *v46; // [rsp+60h] [rbp-A0h]
  struct IEnhancedStorageSiloAction ***v47; // [rsp+68h] [rbp-98h]
  unsigned int *v48; // [rsp+70h] [rbp-90h]
  _BYTE v49[272]; // [rsp+80h] [rbp-80h] BYREF

  v48 = a3;
  v39 = 0;
  Block = 0;
  v40 = 0;
  v47 = a2;
  v46 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, a2, a3);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v49, "CEnhancedStorageSilo::GetActions", &v39);
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    v7 = 38;
LABEL_12:
    WPP_SF_(v6[2], v7, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids);
LABEL_13:
    v8 = -2147024809;
    goto LABEL_54;
  }
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    v7 = 39;
    goto LABEL_12;
  }
  v9 = 0;
  v10 = 0;
  RegistryProperty = CEnhancedStorageSilo::GetRegistryProperty(
                       this,
                       L"SiloCustomActions",
                       (unsigned __int8 **)&Block,
                       &v40,
                       7u);
  v39 = RegistryProperty;
  if ( RegistryProperty >= 0 )
  {
    v16 = Block;
    v17 = 0;
    v18 = (char *)Block + v40;
    if ( (char *)Block + 1 < v18 )
    {
      do
      {
        v19 = *v16 == 0;
        v12 = v17 + 1;
        ++v16;
        if ( !v19 )
          v12 = v17;
        v17 = v12;
      }
      while ( (char *)v16 + 1 < v18 );
      if ( v12 )
      {
        LODWORD(v18) = (v12 - 1) / 3;
        if ( v12 - 1 == 3 * (_DWORD)v18 )
        {
          v9 = v12 / 3;
          v20 = 8LL * (v12 / 3);
          v10 = CoTaskMemAlloc(v20);
          memset_0(v10, 0, v20);
          v21 = 0;
          v22 = (const unsigned __int16 *)Block;
          v23 = (unsigned __int64)v40 >> 1;
          while ( 1 )
          {
            v43 = v21;
            if ( v21 >= v9 )
            {
              *v47 = (struct IEnhancedStorageSiloAction **)v10;
              *v48 = v9;
              goto LABEL_45;
            }
            v41 = 0;
            v39 = StringCchLengthW(v22, v23, &v41);
            if ( v39 < 0 )
              break;
            v24 = v23 - v41 - 1;
            v25 = &v22[v41 + 1];
            v39 = StringCchLengthW(v25, v24, &v41);
            if ( v39 < 0 )
            {
              v36 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_45;
              v37 = 43;
              v38 = (int)v25;
              goto LABEL_68;
            }
            v26 = v24 - v41 - 1;
            v27 = &v25[v41 + 1];
            v45 = v27;
            v39 = StringCchLengthW(v27, v26, &v41);
            if ( v39 < 0 )
            {
              v36 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_45;
              v37 = 44;
              v38 = (int)v27;
              goto LABEL_68;
            }
            v44 = 0;
            v39 = ATL::CComObject<CEnhancedStorageSiloAction>::CreateInstance(&v44);
            if ( v39 < 0 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_45;
              v14 = 45;
LABEL_58:
              v15 = (unsigned int)v39;
              goto LABEL_18;
            }
            v28 = v44;
            (*(void (__fastcall **)(_QWORD *))(*v44 + 8LL))(v44);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v25, (__int64)v27);
            v29 = v46;
            v30 = *((_QWORD *)v46 + 8);
            v28[12] = v46;
            (*(void (__fastcall **)(CEnhancedStorageSilo *))(*(_QWORD *)v29 + 8LL))(v29);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v28 + 10, v45);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v28 + 11, v30);
            IndirectString = CEnhancedStorageSiloAction::LoadIndirectString(v28 + 8, v22);
            if ( IndirectString >= 0 )
              IndirectString = CEnhancedStorageSiloAction::LoadIndirectString(v28 + 9, v25);
            v39 = IndirectString;
            if ( IndirectString < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  47,
                  &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
                  (unsigned int)IndirectString);
              goto LABEL_45;
            }
            v32 = v43;
            v39 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64))*v28)(
                    v28,
                    &IID_IEnhancedStorageSiloAction,
                    (__int64)v10 + 8 * v43);
            (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
            if ( v39 < 0 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_45;
              v14 = 48;
              goto LABEL_58;
            }
            v23 = v26 - v41 - 1;
            v21 = v32 + 1;
            v22 = &v45[v41 + 1];
          }
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_45;
          v37 = 42;
          v38 = (int)v22;
LABEL_68:
          WPP_SF_Sd(v36[2], v37, (unsigned int)&WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v38, v39);
          goto LABEL_45;
        }
      }
    }
    v39 = -2147023881;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v18, v12, (_DWORD)Block, v40, v17);
      goto LABEL_45;
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v14 = 40;
      v15 = (unsigned int)RegistryProperty;
LABEL_18:
      WPP_SF_d(v13[2], v14, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v15);
    }
LABEL_45:
    if ( v39 >= 0 )
      goto LABEL_51;
  }
  for ( i = 0; i < v9; ++i )
  {
    v34 = *((_QWORD *)v10 + i);
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      *((_QWORD *)v10 + i) = 0;
    }
  }
  CoTaskMemFree(v10);
LABEL_51:
  if ( Block )
  {
    operator delete[](Block);
    Block = 0;
  }
  v8 = v39;
LABEL_54:
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v49);
  return v8;
}

```

## disassembly

```asm
0x180006af0  mov     [rsp-8+arg_18], rbx
0x180006af5  push    rbp
0x180006af6  push    rsi
0x180006af7  push    rdi
0x180006af8  push    r12
0x180006afa  push    r13
0x180006afc  push    r14
0x180006afe  push    r15
0x180006b00  lea     rbp, [rsp-0A0h]
0x180006b08  sub     rsp, 1A0h
0x180006b0f  mov     rax, cs:__security_cookie
0x180006b16  xor     rax, rsp
0x180006b19  mov     [rbp+0D0h+var_40], rax
0x180006b20  xor     r15d, r15d
0x180006b23  mov     [rsp+1D0h+var_160], r8
0x180006b28  mov     [rsp+1D0h+var_1A0], r15d
0x180006b2d  mov     rsi, r8
0x180006b30  mov     [rsp+1D0h+Block], r15
0x180006b35  mov     r12, rdx
0x180006b38  mov     [rsp+1D0h+var_19C], r15d
0x180006b3d  mov     rbx, rcx
0x180006b40  mov     [rsp+1D0h+var_168], rdx
0x180006b45  mov     [rsp+1D0h+var_170], rcx
0x180006b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b51  lea     rdi, WPP_GLOBAL_Control
0x180006b58  cmp     rcx, rdi
0x180006b5b  jz      short loc_180006B7F
0x180006b5d  test    byte ptr [rcx+1Ch], 10h
0x180006b61  jz      short loc_180006B7F
0x180006b63  mov     rcx, [rcx+10h]
0x180006b67  lea     edx, [r15+25h]
0x180006b6b  mov     qword ptr [rsp+1D0h+var_1B0], r8
0x180006b70  mov     r9, r12
0x180006b73  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006b7a  call    WPP_SF_qq
0x180006b7f  lea     r8, [rsp+1D0h+var_1A0]; int *
0x180006b84  lea     rdx, aCenhancedstora_8; "CEnhancedStorageSilo::GetActions"
0x180006b8b  lea     rcx, [rbp+0D0h+var_150]; this
0x180006b8f  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x180006b94  test    r12, r12
0x180006b97  jnz     short loc_180006BB2
0x180006b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ba0  cmp     rcx, rdi
0x180006ba3  jz      short loc_180006BDC
0x180006ba5  test    byte ptr [rcx+1Ch], 2
0x180006ba9  jz      short loc_180006BDC
0x180006bab  lea     edx, [r12+26h]
0x180006bb0  jmp     short loc_180006BCC
0x180006bb2  test    rsi, rsi
0x180006bb5  jnz     short loc_180006BE6
0x180006bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bbe  cmp     rcx, rdi
0x180006bc1  jz      short loc_180006BDC
0x180006bc3  test    byte ptr [rcx+1Ch], 2
0x180006bc7  jz      short loc_180006BDC
0x180006bc9  lea     edx, [rsi+27h]
0x180006bcc  mov     rcx, [rcx+10h]
0x180006bd0  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006bd7  call    WPP_SF_
0x180006bdc  mov     ebx, 80070057h
0x180006be1  jmp     loc_180006F34
0x180006be6  xor     esi, esi
0x180006be8  mov     [rsp+1D0h+var_1B0], 7; unsigned int
0x180006bf0  lea     r9, [rsp+1D0h+var_19C]; unsigned int *
0x180006bf5  mov     rcx, rbx; this
0x180006bf8  lea     r8, [rsp+1D0h+Block]; unsigned __int8 **
0x180006bfd  mov     r14d, esi
0x180006c00  lea     rdx, aSilocustomacti; "SiloCustomActions"
0x180006c07  mov     r13d, esi
0x180006c0a  call    ?GetRegistryProperty@CEnhancedStorageSilo@@AEAAJPEBGPEAPEAEPEAKK@Z; CEnhancedStorageSilo::GetRegistryProperty(ushort const *,uchar * *,ulong *,ulong)
0x180006c0f  mov     [rsp+1D0h+var_1A0], eax
0x180006c13  test    eax, eax
0x180006c15  jns     short loc_180006C4C
0x180006c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c1e  cmp     rcx, rdi
0x180006c21  jz      loc_180006EE2
0x180006c27  test    byte ptr [rcx+1Ch], 2
0x180006c2b  jz      loc_180006EE2
0x180006c31  lea     edx, [rsi+28h]
0x180006c34  mov     r9d, eax
0x180006c37  mov     rcx, [rcx+10h]
0x180006c3b  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006c42  call    WPP_SF_d
0x180006c47  jmp     loc_180006EE2
0x180006c4c  mov     rcx, [rsp+1D0h+Block]
0x180006c51  mov     r9d, esi
0x180006c54  mov     r10d, [rsp+1D0h+var_19C]
0x180006c59  lea     rax, [rcx+1]
0x180006c5d  lea     rdx, [rcx+r10]
0x180006c61  cmp     rax, rdx
0x180006c64  jnb     loc_18000704A
0x180006c6a  cmp     [rcx], si
0x180006c6d  lea     r8d, [r9+1]
0x180006c71  lea     rcx, [rcx+2]
0x180006c75  cmovnz  r8d, r9d
0x180006c79  lea     rax, [rcx+1]
0x180006c7d  mov     r9d, r8d
0x180006c80  cmp     rax, rdx
0x180006c83  jb      short loc_180006C6A
0x180006c85  test    r8d, r8d
0x180006c88  jz      loc_18000704A
0x180006c8e  lea     ecx, [r8-1]
0x180006c92  mov     r11d, 0AAAAAAABh
0x180006c98  mov     eax, r11d
0x180006c9b  mul     ecx
0x180006c9d  shr     edx, 1
0x180006c9f  lea     eax, [rdx+rdx*2]
0x180006ca2  cmp     ecx, eax
0x180006ca4  jnz     loc_18000704A
0x180006caa  mov     eax, r11d
0x180006cad  mul     r8d
0x180006cb0  mov     r14d, edx
0x180006cb3  shr     r14d, 1
0x180006cb6  mov     ebx, r14d
0x180006cb9  shl     rbx, 3
0x180006cbd  mov     rcx, rbx; cb
0x180006cc0  call    cs:__imp_CoTaskMemAlloc
0x180006cc6  mov     r8, rbx; Size
0x180006cc9  xor     edx, edx; Val
0x180006ccb  mov     rcx, rax; void *
0x180006cce  mov     r13, rax
0x180006cd1  call    memset_0
0x180006cd6  mov     edi, [rsp+1D0h+var_19C]
0x180006cda  mov     ebx, esi
0x180006cdc  mov     r15, [rsp+1D0h+Block]
0x180006ce1  shr     rdi, 1
0x180006ce4  mov     [rsp+1D0h+var_188], ebx
0x180006ce8  cmp     ebx, r14d
0x180006ceb  jnb     loc_180007035
0x180006cf1  lea     r8, [rsp+1D0h+var_198]; unsigned __int64 *
0x180006cf6  mov     [rsp+1D0h+var_198], rsi
0x180006cfb  mov     rdx, rdi; unsigned __int64
0x180006cfe  mov     rcx, r15; unsigned __int16 *
0x180006d01  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180006d06  mov     [rsp+1D0h+var_1A0], eax
0x180006d0a  test    eax, eax
0x180006d0c  js      loc_180006FEF
0x180006d12  mov     rax, [rsp+1D0h+var_198]
0x180006d17  lea     r8, [rsp+1D0h+var_198]; unsigned __int64 *
0x180006d1c  sub     rdi, rax
0x180006d1f  dec     rdi
0x180006d22  mov     rdx, rdi; unsigned __int64
0x180006d25  lea     r12, [rax+1]
0x180006d29  lea     r12, [r15+r12*2]
0x180006d2d  mov     rcx, r12; unsigned __int16 *
0x180006d30  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180006d35  mov     [rsp+1D0h+var_1A0], eax
0x180006d39  test    eax, eax
0x180006d3b  js      loc_180006FC4
0x180006d41  mov     rax, [rsp+1D0h+var_198]
0x180006d46  lea     r8, [rsp+1D0h+var_198]; unsigned __int64 *
0x180006d4b  sub     rdi, rax
0x180006d4e  dec     rdi
0x180006d51  mov     rdx, rdi; unsigned __int64
0x180006d54  lea     rbx, [rax+1]
0x180006d58  lea     rbx, [r12+rbx*2]
0x180006d5c  mov     rcx, rbx; unsigned __int16 *
0x180006d5f  mov     [rsp+1D0h+var_178], rbx
0x180006d64  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180006d69  mov     [rsp+1D0h+var_1A0], eax
0x180006d6d  test    eax, eax
0x180006d6f  js      loc_180006F99
0x180006d75  lea     rcx, [rsp+1D0h+var_180]
0x180006d7a  mov     [rsp+1D0h+var_180], rsi
0x180006d7f  call    ?CreateInstance@?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnhancedStorageSiloAction>::CreateInstance(ATL::CComObject<CEnhancedStorageSiloAction> * *)
0x180006d84  mov     [rsp+1D0h+var_1A0], eax
0x180006d88  test    eax, eax
0x180006d8a  js      loc_180006F69
0x180006d90  mov     rsi, [rsp+1D0h+var_180]
0x180006d95  mov     rcx, rsi
0x180006d98  mov     rax, [rsi]
0x180006d9b  mov     rax, [rax+8]
0x180006d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dab  lea     rax, WPP_GLOBAL_Control
0x180006db2  cmp     rcx, rax
0x180006db5  jz      short loc_180006DD3
0x180006db7  test    byte ptr [rcx+1Ch], 20h
0x180006dbb  jz      short loc_180006DD3
0x180006dbd  mov     rcx, [rcx+10h]; LoggerHandle
0x180006dc1  mov     r9, r15
0x180006dc4  mov     [rsp+1D0h+var_1A8], rbx; __int64
0x180006dc9  mov     qword ptr [rsp+1D0h+var_1B0], r12; __int64
0x180006dce  call    WPP_SF_SSS
0x180006dd3  mov     rcx, [rsp+1D0h+var_170]
0x180006dd8  mov     rbx, [rcx+40h]
0x180006ddc  mov     [rsi+60h], rcx
0x180006de0  mov     rax, [rcx]
0x180006de3  mov     rax, [rax+8]
0x180006de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dec  mov     rdx, [rsp+1D0h+var_178]
0x180006df1  lea     rcx, [rsi+50h]
0x180006df5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180006dfa  lea     rcx, [rsi+58h]
0x180006dfe  mov     rdx, rbx
0x180006e01  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180006e06  lea     rcx, [rsi+40h]
0x180006e0a  mov     rdx, r15
0x180006e0d  call    ?LoadIndirectString@CEnhancedStorageSiloAction@@CAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CEnhancedStorageSiloAction::LoadIndirectString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,ushort const *)
0x180006e12  test    eax, eax
0x180006e14  js      short loc_180006E22
0x180006e16  lea     rcx, [rsi+48h]
0x180006e1a  mov     rdx, r12
0x180006e1d  call    ?LoadIndirectString@CEnhancedStorageSiloAction@@CAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CEnhancedStorageSiloAction::LoadIndirectString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,ushort const *)
0x180006e22  mov     [rsp+1D0h+var_1A0], eax
0x180006e26  test    eax, eax
0x180006e28  js      loc_180006EAF
0x180006e2e  mov     rdx, [rsi]
0x180006e31  mov     rcx, rsi
0x180006e34  mov     ebx, [rsp+1D0h+var_188]
0x180006e38  mov     rax, [rdx]
0x180006e3b  lea     rdx, IID_IEnhancedStorageSiloAction
0x180006e42  lea     r8, ds:0[rbx*8]
0x180006e4a  add     r8, r13
0x180006e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e52  mov     [rsp+1D0h+var_1A0], eax
0x180006e56  mov     rcx, rsi
0x180006e59  mov     rax, [rsi]
0x180006e5c  mov     rax, [rax+10h]
0x180006e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e65  xor     esi, esi
0x180006e67  cmp     [rsp+1D0h+var_1A0], esi
0x180006e6b  jl      short loc_180006E8C
0x180006e6d  mov     rax, [rsp+1D0h+var_198]
0x180006e72  mov     rcx, [rsp+1D0h+var_178]
0x180006e77  sub     rdi, rax
0x180006e7a  dec     rdi
0x180006e7d  inc     ebx
0x180006e7f  lea     r15, [rax+1]
0x180006e83  lea     r15, [rcx+r15*2]
0x180006e87  jmp     loc_180006CE4
0x180006e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e93  lea     rax, WPP_GLOBAL_Control
0x180006e9a  cmp     rcx, rax
0x180006e9d  jz      short loc_180006EE2
0x180006e9f  test    byte ptr [rcx+1Ch], 2
0x180006ea3  jz      short loc_180006EE2
0x180006ea5  mov     edx, 30h ; '0'
0x180006eaa  jmp     loc_180006F8F
0x180006eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eb6  lea     rdx, WPP_GLOBAL_Control
0x180006ebd  cmp     rcx, rdx
0x180006ec0  jz      short loc_180006EE0
0x180006ec2  test    byte ptr [rcx+1Ch], 2
0x180006ec6  jz      short loc_180006EE0
0x180006ec8  mov     rcx, [rcx+10h]
0x180006ecc  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180006ed3  mov     edx, 2Fh ; '/'
0x180006ed8  mov     r9d, eax
0x180006edb  call    WPP_SF_d
0x180006ee0  xor     esi, esi
0x180006ee2  cmp     [rsp+1D0h+var_1A0], esi
0x180006ee6  jge     short loc_180006F1C
0x180006ee8  mov     ebx, esi
0x180006eea  test    r14d, r14d
0x180006eed  jz      short loc_180006F13
0x180006eef  mov     edi, ebx
0x180006ef1  mov     rcx, [r13+rdi*8+0]
0x180006ef6  test    rcx, rcx
0x180006ef9  jz      short loc_180006F0C
0x180006efb  mov     rax, [rcx]
0x180006efe  mov     rax, [rax+10h]
0x180006f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f07  mov     [r13+rdi*8+0], rsi
0x180006f0c  inc     ebx
0x180006f0e  cmp     ebx, r14d
0x180006f11  jb      short loc_180006EEF
0x180006f13  mov     rcx, r13; pv
0x180006f16  call    cs:__imp_CoTaskMemFree
0x180006f1c  mov     rcx, [rsp+1D0h+Block]; Block
0x180006f21  test    rcx, rcx
0x180006f24  jz      short loc_180006F30
0x180006f26  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006f2b  mov     [rsp+1D0h+Block], rsi
0x180006f30  mov     ebx, [rsp+1D0h+var_1A0]
0x180006f34  lea     rcx, [rbp+0D0h+var_150]; this
0x180006f38  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180006f3d  mov     eax, ebx
0x180006f3f  mov     rcx, [rbp+0D0h+var_40]
0x180006f46  xor     rcx, rsp; StackCookie
0x180006f49  call    __security_check_cookie
0x180006f4e  mov     rbx, [rsp+1D0h+arg_18]
0x180006f56  add     rsp, 1A0h
0x180006f5d  pop     r15
0x180006f5f  pop     r14
0x180006f61  pop     r13
0x180006f63  pop     r12
0x180006f65  pop     rdi
0x180006f66  pop     rsi
0x180006f67  pop     rbp
0x180006f68  retn
0x180006f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f70  lea     rax, WPP_GLOBAL_Control
0x180006f77  cmp     rcx, rax
0x180006f7a  jz      loc_180006EE2
0x180006f80  test    byte ptr [rcx+1Ch], 2
0x180006f84  jz      loc_180006EE2
0x180006f8a  mov     edx, 2Dh ; '-'
0x180006f8f  mov     r9d, [rsp+1D0h+var_1A0]
0x180006f94  jmp     loc_180006C37
  ... truncated ...
```
