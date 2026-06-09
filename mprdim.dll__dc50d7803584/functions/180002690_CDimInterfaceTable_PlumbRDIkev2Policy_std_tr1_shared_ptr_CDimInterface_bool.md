# CDimInterfaceTable::PlumbRDIkev2Policy(std::tr1::shared_ptr<CDimInterface> &,bool)

- ea: `0x180002690`
- end: `0x180002af6`
- name: `?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@_N@Z`
- size: `1126`
- prototype: `__int64 __fastcall(CDimInterfaceTable *this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800033c8`
- `0x1800042a8`

## callees

- `0x180002690`
- `0x180002afc`
- `0x180002c78`
- `0x180002d80`
- `0x180003f40`
- `0x180003f58`
- `0x180005340`
- `0x180005670`
- `0x18000b534`
- `0x18000d854`
- `0x18000df70`
- `0x180035d10`
- `0x1800442f0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!DDMPlumbRDIkev2TunnelPolicy` at `0x180002a9b`
- `MPRDDM!DDMPlumbRDIkev2TunnelPolicy` at `0x180002a9b`

## string_xrefs

- `0x1800027b0`: `PlumbRDIkev2Policy: GetRoutingDomainConfiguration failed: %d`
- `0x180002859`: `PlumbRDIkev2Policy: Custom policy is not configured`
- `0x1800028c9`: `PlumbRDIkev2Policy: UpdateRemoteEndpoints failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDimInterfaceTable::PlumbRDIkev2Policy(CDimInterfaceTable *this, __int64 *a2, unsigned __int8 a3)
{
  unsigned int v3; // r12d
  struct IDimSRWLock *v6; // rbx
  struct _GUID *v7; // rsi
  unsigned int RoutingDomainConfiguration; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int updated; // ebx
  __int64 v12; // rax
  __int128 *v13; // r9
  __int64 v14; // rax
  __int128 *v15; // r9
  CDimFullRouterInterface **v16; // rax
  __int64 v17; // rax
  __int128 *v18; // r9
  char v19; // r15
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  __int64 v22; // rax
  __int128 *v23; // r9
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  std::tr1::_Ref_count_base *v30; // [rsp+68h] [rbp-98h]
  __int64 v31[14]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+E0h] [rbp-20h] BYREF
  int v33; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v34; // [rsp+F4h] [rbp-Ch]
  __int128 v35; // [rsp+104h] [rbp+4h]
  int v36; // [rsp+114h] [rbp+14h]
  int v37; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v38[2044]; // [rsp+124h] [rbp+24h] BYREF

  v3 = a3;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  memset_0(v31, 0, 0x68u);
  v6 = (struct IDimSRWLock *)*a2;
  v7 = (struct _GUID *)(*a2 + 3104);
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v32 = 0;
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v26, v6);
  CDimInterfaceTable::AcquireExclusive(this);
  if ( (_BYTE)v3 )
  {
    updated = 0;
    v19 = 0;
  }
  else
  {
    memset_0(v31, 0, 0x68u);
    v25 = 104;
    RoutingDomainConfiguration = GetRoutingDomainConfiguration(v7, 8u, 0, (__int64)&v25, (__int64)v31);
    updated = RoutingDomainConfiguration;
    if ( RoutingDomainConfiguration )
    {
      if ( RoutingDomainConfiguration == 1168 )
      {
        updated = 0;
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v37) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(
          &v37,
          L"PlumbRDIkev2Policy: GetRoutingDomainConfiguration failed: %d",
          RoutingDomainConfiguration);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 280LL))(*a2);
          v13 = &v32;
          if ( v7 )
            LODWORD(v13) = (_DWORD)v7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v37,
            (_DWORD)v13,
            v12,
            (__int64)&v33);
        }
      }
      goto LABEL_42;
    }
    if ( !v31[7] )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v33) = 0;
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 280LL))(*a2);
        v15 = &v32;
        if ( v7 )
          LODWORD(v15) = (_DWORD)v7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminError,
          (unsigned int)L"PlumbRDIkev2Policy: Custom policy is not configured",
          (_DWORD)v15,
          v14,
          (__int64)&v33);
      }
LABEL_41:
      FreeRoutingDomainConfiguration(8, v31);
      goto LABEL_42;
    }
    CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(this, a2, v9, v10);
    v16 = (CDimFullRouterInterface **)std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v29, a2);
    updated = CDimFullRouterInterface::UpdateRemoteEndPoints(*v16);
    if ( v30 )
      std::tr1::_Ref_count_base::_Decref(v30);
    if ( updated )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v37) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(&v37, L"PlumbRDIkev2Policy: UpdateRemoteEndpoints failed: %d", updated);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 280LL))(*a2);
          v18 = &v32;
          if ( v7 )
            LODWORD(v18) = (_DWORD)v7;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v37,
            (_DWORD)v18,
            v17,
            (__int64)&v33);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a2 + 768LL))(*a2);
      goto LABEL_41;
    }
    v19 = 1;
    CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(this, a2);
  }
  CDimInterfaceTable::ReleaseExclusive(this);
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 120LL))(*a2) & 0x10000000) == 0
    && ((_BYTE)v3
     || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 104LL))(*a2) & 4) != 0
     && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*a2 + 344LL))(*a2)) )
  {
    *(_QWORD *)&v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
    v20 = *a2;
    *((_QWORD *)&v27 + 1) = *a2 + 832;
    LODWORD(v28) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 344LL))(v20);
    *((_QWORD *)&v28 + 1) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 352LL))(*a2);
    if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
    {
      LOWORD(v37) = 0;
      LOWORD(v33) = 0;
      v21 = L"Removing";
      if ( !(_BYTE)v3 )
        v21 = L"Plumbing";
      FormatRRASErrorString(&v37, L"%ws IKEv2 policies ...", v21);
      if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
      {
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 280LL))(*a2);
        v23 = &v32;
        if ( v7 )
          LODWORD(v23) = (_DWORD)v7;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminInfo,
          (unsigned int)&v37,
          (_DWORD)v23,
          v22,
          (__int64)&v33);
      }
    }
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
      updated = DDMPlumbRDIkev2TunnelPolicy(v3, v7, v31, 1, &v27);
    else
      updated = 903;
  }
  if ( v19 )
    goto LABEL_41;
LABEL_42:
  scoped_lock::~scoped_lock((scoped_lock *)v26);
  return updated;
}

```

## disassembly

```asm
0x180002690  mov     [rsp-8+arg_10], rbx
0x180002695  mov     [rsp-8+arg_18], rsi
0x18000269a  push    rbp
0x18000269b  push    rdi
0x18000269c  push    r12
0x18000269e  push    r14
0x1800026a0  push    r15
0x1800026a2  lea     rbp, [rsp-830h]
0x1800026aa  sub     rsp, 930h
0x1800026b1  mov     rax, cs:__security_cookie
0x1800026b8  xor     rax, rsp
0x1800026bb  mov     [rbp+850h+var_30], rax
0x1800026c2  movzx   r12d, r8b
0x1800026c6  mov     rdi, rdx
0x1800026c9  mov     r14, rcx
0x1800026cc  xorps   xmm0, xmm0
0x1800026cf  movups  [rsp+950h+var_910], xmm0
0x1800026d4  movups  [rsp+950h+var_900], xmm0
0x1800026d9  mov     [rsp+950h+var_920], 0
0x1800026e1  mov     r15d, 68h ; 'h'
0x1800026e7  mov     r8d, r15d; Size
0x1800026ea  xor     edx, edx; Val
0x1800026ec  lea     rcx, [rsp+950h+var_8E0]; void *
0x1800026f1  call    memset_0
0x1800026f6  mov     rbx, [rdi]
0x1800026f9  lea     rsi, [rbx+0C20h]
0x180002700  xor     eax, eax
0x180002702  mov     [rbp+850h+var_830], eax
0x180002705  xor     edx, edx; Val
0x180002707  mov     r8d, 7FCh; Size
0x18000270d  lea     rcx, [rbp+850h+var_82C]; void *
0x180002711  call    memset_0
0x180002716  xor     eax, eax
0x180002718  mov     [rbp+850h+var_860], eax
0x18000271b  xorps   xmm0, xmm0
0x18000271e  movups  [rbp+850h+var_85C], xmm0
0x180002722  movups  [rbp+850h+var_84C], xmm0
0x180002726  mov     [rbp+850h+var_83C], eax
0x180002729  movups  [rbp+850h+var_870], xmm0
0x18000272d  mov     rdx, rbx; struct IDimSRWLock *
0x180002730  lea     rcx, [rsp+950h+var_918]; this
0x180002735  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x18000273a  nop
0x18000273b  mov     rcx, r14; this
0x18000273e  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x180002743  test    r12b, r12b
0x180002746  jnz     loc_18000294B
0x18000274c  mov     r8d, r15d; Size
0x18000274f  xor     edx, edx; Val
0x180002751  lea     rcx, [rsp+950h+var_8E0]; void *
0x180002756  call    memset_0
0x18000275b  mov     [rsp+950h+var_920], r15d
0x180002760  lea     rax, [rsp+950h+var_8E0]
0x180002765  mov     [rsp+950h+var_930], rax; __int64
0x18000276a  lea     r9, [rsp+950h+var_920]
0x18000276f  xor     r8d, r8d
0x180002772  lea     edx, [r15-60h]
0x180002776  mov     rcx, rsi; struct _GUID *
0x180002779  call    GetRoutingDomainConfiguration
0x18000277e  mov     ebx, eax
0x180002780  test    eax, eax
0x180002782  jz      loc_180002814
0x180002788  cmp     eax, 490h
0x18000278d  jnz     short loc_180002796
0x18000278f  xor     ebx, ebx
0x180002791  jmp     loc_180002ABF
0x180002796  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000279d  jz      loc_180002ABF
0x1800027a3  xor     eax, eax
0x1800027a5  mov     word ptr [rbp+850h+var_830], ax
0x1800027a9  mov     word ptr [rbp+850h+var_860], ax
0x1800027ad  mov     r8d, ebx
0x1800027b0  lea     rdx, aPlumbrdikev2po_2; "PlumbRDIkev2Policy: GetRoutingDomainCon"...
0x1800027b7  lea     rcx, [rbp+850h+var_830]
0x1800027bb  call    FormatRRASErrorString
0x1800027c0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800027c7  jz      loc_180002ABF
0x1800027cd  mov     rcx, [rdi]
0x1800027d0  mov     rax, [rcx]
0x1800027d3  mov     rax, [rax+118h]
0x1800027da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027df  lea     r9, [rbp+850h+var_870]
0x1800027e3  test    rsi, rsi
0x1800027e6  cmovnz  r9, rsi
0x1800027ea  lea     rcx, [rbp+850h+var_860]
0x1800027ee  mov     [rsp+950h+var_928], rcx
0x1800027f3  mov     [rsp+950h+var_930], rax
0x1800027f8  lea     r8, [rbp+850h+var_830]
0x1800027fc  lea     rdx, RasDimParamTraceError
0x180002803  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000280a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000280f  jmp     loc_180002ABF
0x180002814  cmp     [rbp+850h+var_8A8], 0
0x180002819  jnz     short loc_180002878
0x18000281b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180002822  jz      loc_180002AAF
0x180002828  xor     eax, eax
0x18000282a  mov     word ptr [rbp+850h+var_860], ax
0x18000282e  mov     rcx, [rdi]
0x180002831  mov     rax, [rcx]
0x180002834  mov     rax, [rax+118h]
0x18000283b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002840  lea     r9, [rbp+850h+var_870]
0x180002844  test    rsi, rsi
0x180002847  cmovnz  r9, rsi
0x18000284b  lea     rcx, [rbp+850h+var_860]
0x18000284f  mov     [rsp+950h+var_928], rcx
0x180002854  mov     [rsp+950h+var_930], rax
0x180002859  lea     r8, aPlumbrdikev2po; "PlumbRDIkev2Policy: Custom policy is no"...
0x180002860  lea     rdx, RasDimParamTraceAdminError
0x180002867  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000286e  call    McTemplateU0zjzz_EventWriteTransfer
0x180002873  jmp     loc_180002AAF
0x180002878  mov     rdx, rdi
0x18000287b  mov     rcx, r14
0x18000287e  call    ?RemoveInterfaceFromRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180002883  mov     rdx, rdi
0x180002886  lea     rcx, [rsp+950h+var_8F0]
0x18000288b  call    ??$static_pointer_cast@VCDimFullRouterInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimFullRouterInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x180002890  nop
0x180002891  mov     rcx, [rax]; this
0x180002894  call    ?UpdateRemoteEndPoints@CDimFullRouterInterface@@QEAAKXZ; CDimFullRouterInterface::UpdateRemoteEndPoints(void)
0x180002899  mov     ebx, eax
0x18000289b  mov     rcx, [rsp+950h+var_8E8]; this
0x1800028a0  test    rcx, rcx
0x1800028a3  jz      short loc_1800028AB
0x1800028a5  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800028aa  nop
0x1800028ab  test    ebx, ebx
0x1800028ad  jz      loc_18000293B
0x1800028b3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800028ba  jz      short loc_180002924
0x1800028bc  xor     eax, eax
0x1800028be  mov     word ptr [rbp+850h+var_830], ax
0x1800028c2  mov     word ptr [rbp+850h+var_860], ax
0x1800028c6  mov     r8d, ebx
0x1800028c9  lea     rdx, aPlumbrdikev2po_4; "PlumbRDIkev2Policy: UpdateRemoteEndpoin"...
0x1800028d0  lea     rcx, [rbp+850h+var_830]
0x1800028d4  call    FormatRRASErrorString
0x1800028d9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800028e0  jz      short loc_180002924
0x1800028e2  mov     rcx, [rdi]
0x1800028e5  mov     rax, [rcx]
0x1800028e8  mov     rax, [rax+118h]
0x1800028ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f4  lea     r9, [rbp+850h+var_870]
0x1800028f8  test    rsi, rsi
0x1800028fb  cmovnz  r9, rsi
0x1800028ff  lea     rcx, [rbp+850h+var_860]
0x180002903  mov     [rsp+950h+var_928], rcx
0x180002908  mov     [rsp+950h+var_930], rax
0x18000290d  lea     r8, [rbp+850h+var_830]
0x180002911  lea     rdx, RasDimParamTraceError
0x180002918  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000291f  call    McTemplateU0zjzz_EventWriteTransfer
0x180002924  mov     rcx, [rdi]
0x180002927  mov     rax, [rcx]
0x18000292a  mov     rax, [rax+300h]
0x180002931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002936  jmp     loc_180002AAF
0x18000293b  mov     r15b, 1
0x18000293e  mov     rdx, rdi
0x180002941  mov     rcx, r14
0x180002944  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180002949  jmp     short loc_180002950
0x18000294b  xor     ebx, ebx
0x18000294d  xor     r15b, r15b
0x180002950  mov     rcx, r14; this
0x180002953  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x180002958  mov     rcx, [rdi]
0x18000295b  mov     rax, [rcx]
0x18000295e  mov     rax, [rax+78h]
0x180002962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002967  bt      eax, 1Ch
0x18000296b  jb      loc_180002AAA
0x180002971  test    r12b, r12b
0x180002974  jnz     short loc_1800029A7
0x180002976  mov     rcx, [rdi]
0x180002979  mov     rax, [rcx]
0x18000297c  mov     rax, [rax+68h]
0x180002980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002985  test    al, 4
0x180002987  jz      loc_180002AAA
0x18000298d  mov     rcx, [rdi]
0x180002990  mov     rax, [rcx]
0x180002993  mov     rax, [rax+158h]
0x18000299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299f  test    eax, eax
0x1800029a1  jz      loc_180002AAA
0x1800029a7  mov     rcx, [rdi]
0x1800029aa  mov     rax, [rcx]
0x1800029ad  mov     rax, [rax+10h]
0x1800029b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b6  mov     qword ptr [rsp+950h+var_910], rax
0x1800029bb  mov     rcx, [rdi]
0x1800029be  lea     rax, [rcx+340h]
0x1800029c5  mov     qword ptr [rsp+950h+var_910+8], rax
0x1800029ca  mov     rax, [rcx]
0x1800029cd  mov     rax, [rax+158h]
0x1800029d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d9  mov     dword ptr [rsp+950h+var_900], eax
0x1800029dd  mov     rcx, [rdi]
0x1800029e0  mov     rax, [rcx]
0x1800029e3  mov     rax, [rax+160h]
0x1800029ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ef  mov     qword ptr [rsp+950h+var_900+8], rax
0x1800029f4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x1800029fb  jz      short loc_180002A77
0x1800029fd  xor     eax, eax
0x1800029ff  mov     word ptr [rbp+850h+var_830], ax
0x180002a03  mov     word ptr [rbp+850h+var_860], ax
0x180002a07  lea     rax, aPlumbing; "Plumbing"
0x180002a0e  lea     r8, aRemoving; "Removing"
0x180002a15  test    r12b, r12b
0x180002a18  cmovz   r8, rax
0x180002a1c  lea     rdx, aWsIkev2Policie; "%ws IKEv2 policies ..."
0x180002a23  lea     rcx, [rbp+850h+var_830]
0x180002a27  call    FormatRRASErrorString
0x180002a2c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180002a33  jz      short loc_180002A77
0x180002a35  mov     rcx, [rdi]
0x180002a38  mov     rax, [rcx]
0x180002a3b  mov     rax, [rax+118h]
0x180002a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a47  lea     r9, [rbp+850h+var_870]
0x180002a4b  test    rsi, rsi
0x180002a4e  cmovnz  r9, rsi
0x180002a52  lea     rcx, [rbp+850h+var_860]
0x180002a56  mov     [rsp+950h+var_928], rcx
0x180002a5b  mov     [rsp+950h+var_930], rax
0x180002a60  lea     r8, [rbp+850h+var_830]
0x180002a64  lea     rdx, RasDimParamTraceAdminInfo
0x180002a6b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002a72  call    McTemplateU0zjzz_EventWriteTransfer
0x180002a77  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x180002a7e  jz      short loc_180002AA5
0x180002a80  mov     ecx, r12d
0x180002a83  lea     rax, [rsp+950h+var_910]
0x180002a88  mov     [rsp+950h+var_930], rax
0x180002a8d  mov     r9d, 1
0x180002a93  lea     r8, [rsp+950h+var_8E0]
0x180002a98  mov     rdx, rsi
0x180002a9b  call    cs:__imp_DDMPlumbRDIkev2TunnelPolicy
0x180002aa1  mov     ebx, eax
0x180002aa3  jmp     short loc_180002AAA
0x180002aa5  mov     ebx, 387h
0x180002aaa  test    r15b, r15b
0x180002aad  jz      short loc_180002ABF
0x180002aaf  lea     rdx, [rsp+950h+var_8E0]
0x180002ab4  mov     ecx, 8
0x180002ab9  call    FreeRoutingDomainConfiguration
0x180002abe  nop
0x180002abf  lea     rcx, [rsp+950h+var_918]; this
0x180002ac4  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180002ac9  mov     eax, ebx
0x180002acb  mov     rcx, [rbp+850h+var_30]
0x180002ad2  xor     rcx, rsp; StackCookie
0x180002ad5  call    __security_check_cookie
0x180002ada  lea     r11, [rsp+950h+var_20]
0x180002ae2  mov     rbx, [r11+40h]
0x180002ae6  mov     rsi, [r11+48h]
0x180002aea  mov     rsp, r11
0x180002aed  pop     r15
0x180002aef  pop     r14
0x180002af1  pop     r12
0x180002af3  pop     rdi
0x180002af4  pop     rbp
0x180002af5  retn
```
