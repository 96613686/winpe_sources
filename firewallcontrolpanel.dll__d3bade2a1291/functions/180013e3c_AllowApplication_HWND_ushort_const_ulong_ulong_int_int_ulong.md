# AllowApplication(HWND__ *,ushort const *,ulong,ulong,int,int,ulong)

- ea: `0x180013e3c`
- end: `0x180014227`
- name: `?AllowApplication@@YAJPEAUHWND__@@PEBGKKHHK@Z`
- size: `1003`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, unsigned int, unsigned int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011ed4`

## callees

- `0x180008b30`
- `0x180009e38`
- `0x180013e3c`
- `0x180014230`
- `0x180014268`
- `0x180014f84`
- `0x1800150a4`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180013f94`
- `OLEAUT32!__imp_VariantInit` at `0x180013f94`
- `FirewallAPI!FWGetGlobalConfig` at `0x180013edd`
- `FirewallAPI!FWGetGlobalConfig` at `0x180013edd`

## pseudocode

```c
__int64 __fastcall AllowApplication(
        HWND a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned int a7)
{
  int v9; // esi
  int v10; // r14d
  struct IMultiObjectElevationFactory *v11; // rdi
  unsigned int v12; // r13d
  unsigned int v13; // ebx
  struct INetFwRule *v14; // rcx
  unsigned int v15; // ecx
  struct IUnknown *v16; // rbx
  struct IUnknown *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v21; // [rsp+28h] [rbp-81h]
  struct IUnknown *v22; // [rsp+58h] [rbp-51h] BYREF
  int v23; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+64h] [rbp-45h] BYREF
  int v25; // [rsp+68h] [rbp-41h]
  unsigned int v26; // [rsp+6Ch] [rbp-3Dh] BYREF
  __int64 v27; // [rsp+70h] [rbp-39h] BYREF
  struct IUnknown *v28; // [rsp+78h] [rbp-31h] BYREF
  __int64 v29; // [rsp+80h] [rbp-29h] BYREF
  struct IMultiObjectElevationFactory *v30; // [rsp+88h] [rbp-21h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-19h] BYREF
  __int64 v32; // [rsp+98h] [rbp-11h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-9h] BYREF
  int v34; // [rsp+A8h] [rbp-1h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp+7h] BYREF

  v33 = 0;
  v29 = 0;
  v32 = 0;
  v22 = 0;
  v31 = 0;
  v28 = 0;
  v30 = 0;
  a6 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v23 = 0;
  v25 = 0;
  v34 = 4;
  if ( a2 && a3 )
  {
    v9 = 0;
    v21 = 0;
    FWGetGlobalConfig(545, 0, 5, 2);
    v10 = CreateMultiObjectElevationFactory(a1, &v30);
    if ( v10 >= 0 )
    {
      v11 = v30;
      v10 = (*(__int64 (__fastcall **)(struct IMultiObjectElevationFactory *, GUID *, GUID *, __int64 *))(*(_QWORD *)v30 + 40LL))(
              v30,
              &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
              &GUID_98325047_c671_4174_8d81_defcd3f03186,
              &v33);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 144LL))(v33, &v29);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v29 + 88LL))(
                  v29,
                  &v31);
          if ( v10 >= 0 )
          {
            v10 = (**v31)(v31, &IID_IEnumVARIANT, &v32);
            if ( v10 >= 0 )
            {
              VariantInit(&pvarg);
              v12 = a7;
              v13 = a4;
              while ( !v10 )
              {
                v26 = 0;
                v24 = 0;
                v10 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v32 + 24LL))(
                        v32,
                        1,
                        &pvarg,
                        &a6);
                if ( v10 || a6 != 1 || pvarg.vt != 9 )
                  break;
                v14 = (struct INetFwRule *)v22;
                if ( v22 != pvarg.punkVal )
                {
                  ATL::AtlComQIPtrAssign(&v22, pvarg.punkVal, &GUID_af230d27_baba_4e42_aced_f524f22cfce2);
                  v14 = (struct INetFwRule *)v22;
                }
                if ( v14 )
                {
                  v9 = CheckIfRuleNeedsUpdate(v14, a2, a3, a5, v21, v12, v13, &v23, &v26, &v24);
                  if ( v9 >= 0 )
                  {
                    if ( v23 )
                    {
                      if ( a5 )
                      {
                        v15 = v24;
                        if ( v24 == v12 )
                          v15 = 0;
                      }
                      else
                      {
                        v15 = v13;
                      }
                      if ( (v15 & v25) != 0 )
                      {
                        v9 = CopyRule(v11, (struct INetFwRule *)v22, (struct INetFwRule **)&v28, v15 & v25);
                        if ( v9 < 0 )
                          break;
                        v16 = v28;
                        v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v29 + 64LL))(v29, v28);
                        if ( v9 < 0 )
                          break;
                        if ( v16 )
                          ATL::AtlComPtrAssign(&v28, v17);
                        v13 = a4;
                      }
                      v9 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v22->lpVtbl[14].QueryInterface)(v22, 1);
                      if ( v9 < 0 )
                        break;
                      v18 = v26;
                      if ( !a5 )
                        v18 = a3;
                      v9 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v22->lpVtbl[12].Release)(v22, v18);
                      if ( v9 < 0 )
                        break;
                      v27 = 0;
                      v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v22->lpVtbl->QueryInterface)(
                             v22,
                             &GUID_9c27c8da_189b_4dde_89f7_8b39a316782c,
                             &v27);
                      if ( v9 < 0 )
                      {
                        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                        break;
                      }
                      v19 = 2;
                      if ( !a5 )
                        v19 = 3;
                      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 352LL))(v27, v19);
                      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v9 >= 0 )
      v9 = v10;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v31);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    return (unsigned int)v9;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v31);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180013e3c  mov     rax, rsp
0x180013e3f  mov     [rax+8], rbx
0x180013e43  mov     [rax+18h], rsi
0x180013e47  mov     [rax+20h], r9d
0x180013e4b  mov     [rax+10h], rdx
0x180013e4f  push    rbp
0x180013e50  push    rdi
0x180013e51  push    r12
0x180013e53  push    r13
0x180013e55  push    r14
0x180013e57  lea     rbp, [rax-47h]
0x180013e5b  sub     rsp, 0C0h
0x180013e62  mov     r12d, r8d
0x180013e65  mov     rax, rdx
0x180013e68  mov     rbx, rcx
0x180013e6b  xor     edx, edx
0x180013e6d  mov     [rbp+3Fh+var_48], rdx
0x180013e71  mov     [rbp+3Fh+var_68], rdx
0x180013e75  mov     [rbp+3Fh+var_50], rdx
0x180013e79  mov     [rbp+3Fh+var_90], rdx
0x180013e7d  mov     [rbp+3Fh+var_58], rdx
0x180013e81  mov     [rbp+3Fh+var_70], rdx
0x180013e85  mov     [rbp+3Fh+var_60], rdx
0x180013e89  mov     [rbp+3Fh+arg_28], edx
0x180013e8c  xorps   xmm0, xmm0
0x180013e8f  xor     ecx, ecx
0x180013e91  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180013e95  mov     qword ptr [rbp+3Fh+pvarg+10h], rcx
0x180013e99  mov     [rbp+3Fh+var_88], edx
0x180013e9c  mov     [rbp+3Fh+var_80], edx
0x180013e9f  mov     [rbp+3Fh+var_40], 4
0x180013ea6  test    rax, rax
0x180013ea9  jz      loc_1800141C1
0x180013eaf  test    r8d, r8d
0x180013eb2  jz      loc_1800141C1
0x180013eb8  mov     esi, edx
0x180013eba  mov     ecx, 221h
0x180013ebf  lea     rax, [rbp+3Fh+var_40]
0x180013ec3  mov     qword ptr [rsp+0E0h+var_B0], rax
0x180013ec8  lea     rax, [rbp+3Fh+var_80]
0x180013ecc  mov     qword ptr [rsp+0E0h+var_B8], rax
0x180013ed1  mov     [rsp+0E0h+var_C0], edx; int
0x180013ed5  lea     r9d, [rdx+2]
0x180013ed9  lea     r8d, [rdx+5]
0x180013edd  call    cs:__imp_FWGetGlobalConfig
0x180013ee3  lea     rdx, [rbp+3Fh+var_60]; struct IMultiObjectElevationFactory **
0x180013ee7  mov     rcx, rbx; HWND
0x180013eea  call    ?CreateMultiObjectElevationFactory@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@@Z; CreateMultiObjectElevationFactory(HWND__ *,IMultiObjectElevationFactory * *)
0x180013eef  mov     r14d, eax
0x180013ef2  test    eax, eax
0x180013ef4  js      loc_180014172
0x180013efa  mov     rdi, [rbp+3Fh+var_60]
0x180013efe  mov     rax, [rdi]
0x180013f01  lea     r9, [rbp+3Fh+var_48]
0x180013f05  lea     r8, _GUID_98325047_c671_4174_8d81_defcd3f03186
0x180013f0c  lea     rdx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd
0x180013f13  mov     rcx, rdi
0x180013f16  mov     rax, [rax+28h]
0x180013f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1f  mov     r14d, eax
0x180013f22  test    eax, eax
0x180013f24  js      loc_180014172
0x180013f2a  mov     rcx, [rbp+3Fh+var_48]
0x180013f2e  mov     rax, [rcx]
0x180013f31  lea     rdx, [rbp+3Fh+var_68]
0x180013f35  mov     rax, [rax+90h]
0x180013f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f41  mov     r14d, eax
0x180013f44  test    eax, eax
0x180013f46  js      loc_180014172
0x180013f4c  mov     rcx, [rbp+3Fh+var_68]
0x180013f50  mov     rax, [rcx]
0x180013f53  lea     rdx, [rbp+3Fh+var_58]
0x180013f57  mov     rax, [rax+58h]
0x180013f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f60  mov     r14d, eax
0x180013f63  test    eax, eax
0x180013f65  js      loc_180014172
0x180013f6b  mov     rcx, [rbp+3Fh+var_58]
0x180013f6f  mov     rax, [rcx]
0x180013f72  lea     r8, [rbp+3Fh+var_50]
0x180013f76  lea     rdx, IID_IEnumVARIANT
0x180013f7d  mov     rax, [rax]
0x180013f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f85  mov     r14d, eax
0x180013f88  test    eax, eax
0x180013f8a  js      loc_180014172
0x180013f90  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180013f94  call    cs:__imp_VariantInit
0x180013f9a  mov     r13d, [rbp+3Fh+arg_30]
0x180013f9e  mov     ebx, [rbp+3Fh+arg_18]
0x180013fa1  test    r14d, r14d
0x180013fa4  jnz     loc_180014172
0x180013faa  mov     [rbp+3Fh+var_7C], r14d
0x180013fae  mov     [rbp+3Fh+var_84], r14d
0x180013fb2  mov     rcx, [rbp+3Fh+var_50]
0x180013fb6  mov     rax, [rcx]
0x180013fb9  lea     r9, [rbp+3Fh+arg_28]
0x180013fbd  lea     r8, [rbp+3Fh+pvarg]
0x180013fc1  lea     edx, [r14+1]
0x180013fc5  mov     rax, [rax+18h]
0x180013fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fce  mov     r14d, eax
0x180013fd1  test    eax, eax
0x180013fd3  jnz     loc_180014172
0x180013fd9  cmp     [rbp+3Fh+arg_28], 1
0x180013fdd  jnz     loc_180014172
0x180013fe3  cmp     word ptr [rbp+3Fh+pvarg], 9
0x180013fe8  jnz     loc_180014172
0x180013fee  mov     rdx, qword ptr [rbp+3Fh+pvarg+8]; struct IUnknown *
0x180013ff2  mov     rcx, [rbp+3Fh+var_90]
0x180013ff6  cmp     rcx, rdx
0x180013ff9  jz      short loc_18001400F
0x180013ffb  lea     r8, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; struct _GUID *
0x180014002  lea     rcx, [rbp+3Fh+var_90]; struct IUnknown **
0x180014006  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18001400b  mov     rcx, [rbp+3Fh+var_90]; struct INetFwRule *
0x18001400f  test    rcx, rcx
0x180014012  jz      short loc_180013FA1
0x180014014  lea     rax, [rbp+3Fh+var_84]
0x180014018  mov     [rsp+0E0h+var_98], rax; unsigned int *
0x18001401d  lea     rax, [rbp+3Fh+var_7C]
0x180014021  mov     [rsp+0E0h+var_A0], rax; unsigned int *
0x180014026  lea     rax, [rbp+3Fh+var_88]
0x18001402a  mov     [rsp+0E0h+var_A8], rax; int *
0x18001402f  mov     [rsp+0E0h+var_B0], ebx; unsigned int
0x180014033  mov     [rsp+0E0h+var_B8], r13d; unsigned int
0x180014038  mov     r9d, [rbp+3Fh+arg_20]; int
0x18001403c  mov     r8d, r12d; unsigned int
0x18001403f  mov     rdx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x180014043  call    ?CheckIfRuleNeedsUpdate@@YAJPEAUINetFwRule@@PEBGKHHKKAEAHPEAK3@Z; CheckIfRuleNeedsUpdate(INetFwRule *,ushort const *,ulong,int,int,ulong,ulong,int &,ulong *,ulong *)
0x180014048  mov     esi, eax
0x18001404a  test    eax, eax
0x18001404c  js      loc_180013FA1
0x180014052  cmp     [rbp+3Fh+var_88], 0
0x180014056  jz      loc_180013FA1
0x18001405c  cmp     [rbp+3Fh+arg_20], 0
0x180014060  jnz     short loc_180014066
0x180014062  mov     ecx, ebx
0x180014064  jmp     short loc_180014071
0x180014066  mov     ecx, [rbp+3Fh+var_84]
0x180014069  xor     eax, eax
0x18001406b  cmp     ecx, r13d
0x18001406e  cmovz   ecx, eax
0x180014071  mov     r9d, [rbp+3Fh+var_80]
0x180014075  and     r9d, ecx; unsigned int
0x180014078  jz      short loc_1800140C6
0x18001407a  lea     r8, [rbp+3Fh+var_70]; struct INetFwRule **
0x18001407e  mov     rdx, [rbp+3Fh+var_90]; struct INetFwRule *
0x180014082  mov     rcx, rdi; struct IMultiObjectElevationFactory *
0x180014085  call    ?CopyRule@@YAJPEAUIMultiObjectElevationFactory@@PEAUINetFwRule@@PEAPEAU2@K@Z; CopyRule(IMultiObjectElevationFactory *,INetFwRule *,INetFwRule * *,ulong)
0x18001408a  mov     esi, eax
0x18001408c  test    eax, eax
0x18001408e  js      loc_180014172
0x180014094  mov     rcx, [rbp+3Fh+var_68]
0x180014098  mov     rax, [rcx]
0x18001409b  mov     rbx, [rbp+3Fh+var_70]
0x18001409f  mov     rdx, rbx
0x1800140a2  mov     rax, [rax+40h]
0x1800140a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ab  mov     esi, eax
0x1800140ad  test    eax, eax
0x1800140af  js      loc_180014172
0x1800140b5  test    rbx, rbx
0x1800140b8  jz      short loc_1800140C3
0x1800140ba  lea     rcx, [rbp+3Fh+var_70]; struct IUnknown **
0x1800140be  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800140c3  mov     ebx, [rbp+3Fh+arg_18]
0x1800140c6  mov     rcx, [rbp+3Fh+var_90]
0x1800140ca  mov     rax, [rcx]
0x1800140cd  mov     edx, 1
0x1800140d2  mov     rax, [rax+150h]
0x1800140d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140de  mov     esi, eax
0x1800140e0  test    eax, eax
0x1800140e2  js      loc_180014172
0x1800140e8  mov     rcx, [rbp+3Fh+var_90]
0x1800140ec  mov     rax, [rcx]
0x1800140ef  mov     rax, [rax+130h]
0x1800140f6  cmp     [rbp+3Fh+arg_20], 0
0x1800140fa  mov     edx, [rbp+3Fh+var_7C]
0x1800140fd  jnz     short loc_180014102
0x1800140ff  mov     edx, r12d
0x180014102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014107  mov     esi, eax
0x180014109  test    eax, eax
0x18001410b  js      short loc_180014172
0x18001410d  mov     [rbp+3Fh+var_78], 0
0x180014115  mov     rcx, [rbp+3Fh+var_90]
0x180014119  mov     rax, [rcx]
0x18001411c  lea     r8, [rbp+3Fh+var_78]
0x180014120  lea     rdx, _GUID_9c27c8da_189b_4dde_89f7_8b39a316782c
0x180014127  mov     rax, [rax]
0x18001412a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001412f  mov     esi, eax
0x180014131  test    eax, eax
0x180014133  js      short loc_180014168
0x180014135  mov     rcx, [rbp+3Fh+var_78]
0x180014139  mov     rax, [rcx]
0x18001413c  mov     rax, [rax+160h]
0x180014143  cmp     [rbp+3Fh+arg_20], 0
0x180014147  mov     edx, 2
0x18001414c  jnz     short loc_180014153
0x18001414e  mov     edx, 3
0x180014153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014158  mov     esi, eax
0x18001415a  lea     rcx, [rbp+3Fh+var_78]
0x18001415e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014163  jmp     loc_180013FA1
0x180014168  lea     rcx, [rbp+3Fh+var_78]
0x18001416c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014171  nop
0x180014172  test    esi, esi
0x180014174  cmovns  esi, r14d
0x180014178  lea     rcx, [rbp+3Fh+var_60]
0x18001417c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014181  nop
0x180014182  lea     rcx, [rbp+3Fh+var_70]
0x180014186  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001418b  nop
0x18001418c  lea     rcx, [rbp+3Fh+var_58]
0x180014190  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014195  nop
0x180014196  lea     rcx, [rbp+3Fh+var_90]
0x18001419a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001419f  nop
0x1800141a0  lea     rcx, [rbp+3Fh+var_50]
0x1800141a4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141a9  nop
0x1800141aa  lea     rcx, [rbp+3Fh+var_68]
0x1800141ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141b3  nop
0x1800141b4  lea     rcx, [rbp+3Fh+var_48]
0x1800141b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141bd  mov     eax, esi
0x1800141bf  jmp     short loc_18001420B
0x1800141c1  lea     rcx, [rbp+3Fh+var_60]
0x1800141c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141ca  nop
0x1800141cb  lea     rcx, [rbp+3Fh+var_70]
0x1800141cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141d4  nop
0x1800141d5  lea     rcx, [rbp+3Fh+var_58]
0x1800141d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141de  nop
0x1800141df  lea     rcx, [rbp+3Fh+var_90]
0x1800141e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141e8  nop
0x1800141e9  lea     rcx, [rbp+3Fh+var_50]
0x1800141ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141f2  nop
0x1800141f3  lea     rcx, [rbp+3Fh+var_68]
0x1800141f7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141fc  nop
0x1800141fd  lea     rcx, [rbp+3Fh+var_48]
0x180014201  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014206  mov     eax, 80070057h
0x18001420b  lea     r11, [rsp+0E0h+var_20]
0x180014213  mov     rbx, [r11+30h]
0x180014217  mov     rsi, [r11+40h]
0x18001421b  mov     rsp, r11
0x18001421e  pop     r14
0x180014220  pop     r13
0x180014222  pop     r12
0x180014224  pop     rdi
0x180014225  pop     rbp
0x180014226  retn
```
