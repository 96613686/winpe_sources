# CDimInterfaceTable::SetInfo(void * const,ulong,_DIM_INFORMATION_CONTAINER *)

- ea: `0x180003800`
- end: `0x180003f33`
- name: `?SetInfo@CDimInterfaceTable@@QEAAKQEAXKPEAU_DIM_INFORMATION_CONTAINER@@@Z`
- size: `1843`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, void *const, unsigned int, struct _DIM_INFORMATION_CONTAINER *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800101b0`

## callees

- `0x180002c78`
- `0x180002d80`
- `0x180002ddc`
- `0x180003800`
- `0x180003f40`
- `0x180003f58`
- `0x180005340`
- `0x1800055f0`
- `0x180005670`
- `0x18000b534`
- `0x18000d854`
- `0x18000d984`
- `0x18000df70`
- `0x180018f28`
- `0x18001e788`
- `0x1800244d0`
- `0x180025c24`
- `0x18002737c`
- `0x180032aa8`
- `0x180045d40`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!TimerQInsert` at `0x180003eda`
- `MPRDDM!TimerQInsert` at `0x180003eda`
- `MPRDDM!ReConnectPersistentInterface` at `0x180003ead`
- `MPRDDM!ReConnectPersistentInterface` at `0x180003ece`
- `MPRDDM!TimerQRemove` at `0x180003eb4`
- `MPRDDM!TimerQRemove` at `0x180003eb4`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x180003976`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x180003976`

## string_xrefs

- `0x180003d23`: `Failed to delete PSK specific IKEv2 policies. Error:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDimInterfaceTable::SetInfo(
        CDimInterfaceTable *this,
        unsigned __int64 a2,
        unsigned int a3,
        struct _DIM_INFORMATION_CONTAINER *a4)
{
  __int64 v7; // r14
  bool v8; // cf
  unsigned int v9; // esi
  CDimInterfaceTable *v11; // r13
  __int64 v12; // r8
  __int64 v13; // r9
  char v14; // bl
  __int64 (*v15)(void); // rax
  __int64 v16; // rdx
  struct IDimSRWLock *v17; // rdi
  __int64 v18; // rbx
  int v19; // eax
  struct IDimSRWLock *v20; // rdi
  __int64 v21; // rbx
  int v22; // eax
  struct IDimSRWLock *v23; // rdi
  __int64 v24; // rbx
  int v25; // eax
  unsigned int SizeOfMultiSz; // eax
  unsigned int v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // ecx
  unsigned int v30; // eax
  __int64 v31; // rax
  _OWORD *v32; // r9
  unsigned int v33; // eax
  __int64 v34; // rax
  _OWORD *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  char v39; // [rsp+30h] [rbp-D0h]
  struct IDimSRWLock *v40; // [rsp+38h] [rbp-C8h] BYREF
  std::tr1::_Ref_count_base *v41; // [rsp+40h] [rbp-C0h]
  char v42; // [rsp+48h] [rbp-B8h]
  _BYTE v43[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A8h]
  int v45; // [rsp+5Ch] [rbp-A4h]
  CDimFullRouterInterface *v46; // [rsp+60h] [rbp-A0h] BYREF
  std::tr1::_Ref_count_base *v47; // [rsp+68h] [rbp-98h]
  _OWORD v48[2]; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+90h] [rbp-70h] BYREF
  __int128 v50; // [rsp+94h] [rbp-6Ch]
  __int128 v51; // [rsp+A4h] [rbp-5Ch]
  int v52; // [rsp+B4h] [rbp-4Ch]
  int v53; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v54[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  memset(v48, 0, sizeof(v48));
  v53 = 0;
  memset_0(v54, 0, sizeof(v54));
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  if ( !a4 )
    return 87;
  v7 = *((_QWORD *)a4 + 1);
  if ( !v7 )
    return 87;
  if ( a3 >= 4 )
    return 50;
  if ( !a3 )
  {
    if ( *(_DWORD *)a4 >= 0x21Cu )
      goto LABEL_6;
    return 87;
  }
  if ( a3 == 1 )
  {
    if ( *(_DWORD *)a4 >= 0x220u )
      goto LABEL_12;
    return 87;
  }
LABEL_6:
  if ( a3 == 2 )
  {
    v8 = *(_DWORD *)a4 < 0x9A4u;
    goto LABEL_14;
  }
LABEL_12:
  if ( a3 != 3 )
    goto LABEL_15;
  v8 = *(_DWORD *)a4 < 0x9D0u;
LABEL_14:
  if ( v8 )
    return 87;
LABEL_15:
  v11 = g_pCDimInterfaceTable;
  v9 = InterfaceAjustVLSPointers(a3, *((unsigned __int8 **)a4 + 1));
  v44 = v9;
  if ( v9 )
    return v9;
  CDimInterfaceTable::AcquireExclusive(v11);
  CDimInterfaceTable::GetCDimInterface((__int64)v11, &v40, a2);
  if ( v40 )
  {
    scoped_read_lock::scoped_read_lock((scoped_read_lock *)v43, v40);
    CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(v11, &v40, v12, v13);
    CDimInterfaceTable::RemoveInterfaceFromHostNameMap(v11, &v40);
    IfObjectLoadPhonebookInfo(v40, 0);
    CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(v11, &v40);
    CDimInterfaceTable::InsertInterfaceInHostNameMap(v11, &v40);
    if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) == 3
      || (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) == 6
      || (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) == 4 )
    {
      v38 = v9;
      if ( !*(_DWORD *)(v7 + 520) )
        v38 = 87;
      v9 = v38;
      scoped_lock::~scoped_lock((scoped_lock *)v43);
      goto LABEL_88;
    }
    LOBYTE(a2) = 0;
    v45 = a2;
    v39 = 0;
    SetActivityId((LPGUID)v40 + 194);
    if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) == 2 )
    {
      if ( *(_DWORD *)(v7 + 520) )
        goto LABEL_27;
      if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40) & 4) != 0 )
        v45 = ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 120LL))(v40) & 0x10000000) != 0;
      if ( *(_DWORD *)(v7 + 520) )
      {
LABEL_27:
        if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40) & 4) == 0
          && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 120LL))(v40) & 0x10000000) != 0 )
        {
          if ( (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v11, &v40, 14) )
          {
            v9 = 870;
            scoped_lock::~scoped_lock((scoped_lock *)v43);
            goto LABEL_88;
          }
          v39 = 1;
        }
        if ( *(_DWORD *)(v7 + 520)
          && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40) & 4) == 0
          && (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 456LL))(v40) == 9
          && (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v11, &v40, 44) )
        {
          v9 = 872;
          scoped_lock::~scoped_lock((scoped_lock *)v43);
          goto LABEL_88;
        }
      }
    }
    v14 = 0;
    v42 = 0;
    v15 = *(__int64 (**)(void))(*(_QWORD *)v40 + 104LL);
    if ( *(_DWORD *)(v7 + 520) )
    {
      if ( (v15() & 4) == 0 )
      {
        v17 = v40;
        v18 = *(_QWORD *)v40;
        v19 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40);
        (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v18 + 112))(v17, v19 | 4u);
        v20 = v40;
        v21 = *(_QWORD *)v40;
        v22 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40);
        (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v21 + 112))(v20, v22 & 0xFFFFBFFF);
        v14 = 1;
      }
    }
    else
    {
      if ( (v15() & 4) != 0 )
      {
        v23 = v40;
        v24 = *(_QWORD *)v40;
        v25 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40);
        (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v24 + 112))(v23, v25 & 0xFFFFFFFB);
        v14 = v42;
      }
      if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 40LL))(v40) )
      {
LABEL_43:
        if ( a3 == 1 )
        {
          if ( *(_DWORD *)(v7 + 540) )
          {
            SizeOfMultiSz = MprUtilGetSizeOfMultiSz((STRSAFE_PCNZWCH)(v7 + 544), 0x7D0u);
            v27 = SizeOfMultiSz;
            v9 = v44;
            if ( v44 || (v28 = SizeOfMultiSz + 544, v28 < v27) || v28 > *(_DWORD *)a4 )
            {
              v9 = 87;
              scoped_lock::~scoped_lock((scoped_lock *)v43);
              goto LABEL_88;
            }
          }
        }
        else
        {
          if ( a3 == 2 )
          {
            if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) != 2 )
            {
              v9 = 87;
              goto LABEL_59;
            }
            v29 = 2;
          }
          else
          {
            if ( a3 != 3 )
              goto LABEL_59;
            if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 72LL))(v40) != 2 )
            {
              v9 = 87;
              goto LABEL_79;
            }
            v29 = 3;
          }
          v9 = RpbkSetEntry(v29, (unsigned __int8 *)v7, *(_DWORD *)a4);
        }
LABEL_59:
        if ( !v9 )
        {
          if ( (_BYTE)v45 )
          {
            std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v46, (__int64 *)&v40);
            v30 = CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v46, 1);
            v9 = v30;
            if ( v30 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              {
                LOWORD(v53) = 0;
                LOWORD(v49) = 0;
                FormatRRASErrorString(&v53, L"Failed to delete PSK specific IKEv2 policies. Error:%d", v30);
                if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                {
                  v31 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 280LL))(v40);
                  v32 = v48;
                  if ( v40 != (struct IDimSRWLock *)-3104LL )
                    LODWORD(v32) = (_DWORD)v40 + 3104;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasDimParamTraceAdminError,
                    (unsigned int)&v53,
                    (_DWORD)v32,
                    v31,
                    (__int64)&v49);
                }
              }
              v9 = 0;
            }
LABEL_77:
            if ( v47 )
              std::tr1::_Ref_count_base::_Decref(v47);
            goto LABEL_79;
          }
          if ( v39 )
          {
            std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v46, (__int64 *)&v40);
            v33 = CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v46, 1);
            v9 = v33;
            if ( v33 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              {
                LOWORD(v53) = 0;
                LOWORD(v49) = 0;
                FormatRRASErrorString(&v53, L"Failed to plumb PSK specific IKEv2 policies. Error:%d", v33);
                if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                {
                  v34 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 280LL))(v40);
                  v35 = v48;
                  if ( v40 != (struct IDimSRWLock *)-3104LL )
                    LODWORD(v35) = (_DWORD)v40 + 3104;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasDimParamTraceAdminError,
                    (unsigned int)&v53,
                    (_DWORD)v35,
                    v34,
                    (__int64)&v49);
                }
              }
              v9 = 0;
            }
            goto LABEL_77;
          }
        }
LABEL_79:
        if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 456LL))(v40) == 9
          && (v14
           || !(*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 40LL))(v40)
           && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 104LL))(v40) & 4) != 0) )
        {
          v36 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 16LL))(v40);
          TimerQRemove(v36, ReConnectPersistentInterface);
          v37 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v40 + 16LL))(v40);
          TimerQInsert(v37, 1, ReConnectPersistentInterface);
        }
        scoped_lock::~scoped_lock((scoped_lock *)v43);
        goto LABEL_88;
      }
    }
    LOBYTE(v16) = *(_DWORD *)(v7 + 520) != 0;
    CDimInterface::NotifyOfReachabilityChange(v40, v16, 2);
    goto LABEL_43;
  }
  v9 = 6;
LABEL_88:
  if ( v41 )
    std::tr1::_Ref_count_base::_Decref(v41);
  CDimInterfaceTable::ReleaseExclusive(v11);
  return v9;
}

```

## disassembly

```asm
0x180003800  mov     [rsp-8+arg_0], rbx
0x180003805  push    rbp
0x180003806  push    rsi
0x180003807  push    rdi
0x180003808  push    r12
0x18000380a  push    r13
0x18000380c  push    r14
0x18000380e  push    r15
0x180003810  lea     rbp, [rsp-7D0h]
0x180003818  sub     rsp, 8D0h
0x18000381f  mov     rax, cs:__security_cookie
0x180003826  xor     rax, rsp
0x180003829  mov     [rbp+800h+var_40], rax
0x180003830  mov     r12, r9
0x180003833  mov     r15d, r8d
0x180003836  mov     rbx, rdx
0x180003839  xorps   xmm0, xmm0
0x18000383c  movups  [rbp+800h+var_880], xmm0
0x180003840  xorps   xmm1, xmm1
0x180003843  movups  [rsp+900h+var_890], xmm1
0x180003848  xor     edi, edi
0x18000384a  mov     [rbp+800h+var_840], edi
0x18000384d  xor     edx, edx; Val
0x18000384f  mov     r8d, 7FCh; Size
0x180003855  lea     rcx, [rbp+800h+var_83C]; void *
0x180003859  call    memset_0
0x18000385e  mov     [rbp+800h+var_870], edi
0x180003861  xorps   xmm0, xmm0
0x180003864  xor     eax, eax
0x180003866  movups  [rbp+800h+var_86C], xmm0
0x18000386a  movups  [rbp+800h+var_85C], xmm0
0x18000386e  mov     [rbp+800h+var_84C], eax
0x180003871  test    r12, r12
0x180003874  jz      short loc_1800038C2
0x180003876  mov     r14, [r12+8]
0x18000387b  test    r14, r14
0x18000387e  jz      short loc_1800038C2
0x180003880  test    r15d, r15d
0x180003883  js      loc_180003F29
0x180003889  cmp     r15d, 3
0x18000388d  ja      loc_180003F29
0x180003893  test    r15d, r15d
0x180003896  jnz     short loc_1800038B2
0x180003898  cmp     dword ptr [r12], 21Ch
0x1800038a0  jb      short loc_1800038C2
0x1800038a2  cmp     r15d, 2
0x1800038a6  jnz     short loc_1800038F3
0x1800038a8  cmp     dword ptr [r12], 9A4h
0x1800038b0  jmp     short loc_180003901
0x1800038b2  cmp     r15d, 1
0x1800038b6  jnz     short loc_1800038A2
0x1800038b8  cmp     dword ptr [r12], 220h
0x1800038c0  jnb     short loc_1800038F3
0x1800038c2  mov     esi, 57h ; 'W'
0x1800038c7  mov     eax, esi
0x1800038c9  mov     rcx, [rbp+800h+var_40]
0x1800038d0  xor     rcx, rsp; StackCookie
0x1800038d3  call    __security_check_cookie
0x1800038d8  mov     rbx, [rsp+900h+arg_0]
0x1800038e0  add     rsp, 8D0h
0x1800038e7  pop     r15
0x1800038e9  pop     r14
0x1800038eb  pop     r13
0x1800038ed  pop     r12
0x1800038ef  pop     rdi
0x1800038f0  pop     rsi
0x1800038f1  pop     rbp
0x1800038f2  retn
0x1800038f3  cmp     r15d, 3
0x1800038f7  jnz     short loc_180003903
0x1800038f9  cmp     dword ptr [r12], 9D0h
0x180003901  jb      short loc_1800038C2
0x180003903  mov     r13, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x18000390a  mov     rdx, r14; unsigned __int8 *
0x18000390d  mov     ecx, r15d; unsigned int
0x180003910  call    ?InterfaceAjustVLSPointers@@YAKKPEAE@Z; InterfaceAjustVLSPointers(ulong,uchar *)
0x180003915  mov     esi, eax
0x180003917  mov     [rsp+900h+var_8A8], eax
0x18000391b  test    eax, eax
0x18000391d  jnz     short loc_1800038C7
0x18000391f  mov     rcx, r13; this
0x180003922  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x180003927  mov     r8, rbx
0x18000392a  lea     rdx, [rsp+900h+var_8C8]
0x18000392f  mov     rcx, r13
0x180003932  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x180003937  nop
0x180003938  mov     rdx, [rsp+900h+var_8C8]; struct IDimSRWLock *
0x18000393d  test    rdx, rdx
0x180003940  jnz     short loc_18000394A
0x180003942  lea     esi, [rdx+6]
0x180003945  jmp     loc_180003EEC
0x18000394a  lea     rcx, [rsp+900h+var_8B0]; this
0x18000394f  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x180003954  nop
0x180003955  lea     rdx, [rsp+900h+var_8C8]
0x18000395a  mov     rcx, r13
0x18000395d  call    ?RemoveInterfaceFromRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180003962  lea     rdx, [rsp+900h+var_8C8]
0x180003967  mov     rcx, r13
0x18000396a  call    ?RemoveInterfaceFromHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x18000396f  xor     edx, edx
0x180003971  mov     rcx, [rsp+900h+var_8C8]
0x180003976  call    cs:__imp_IfObjectLoadPhonebookInfo
0x18000397c  lea     rdx, [rsp+900h+var_8C8]
0x180003981  mov     rcx, r13
0x180003984  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180003989  lea     rdx, [rsp+900h+var_8C8]
0x18000398e  mov     rcx, r13
0x180003991  call    ?InsertInterfaceInHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180003996  mov     rcx, [rsp+900h+var_8C8]
0x18000399b  mov     rax, [rcx]
0x18000399e  mov     rax, [rax+48h]
0x1800039a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a7  cmp     eax, 3
0x1800039aa  jz      loc_180003EEE
0x1800039b0  mov     rcx, [rsp+900h+var_8C8]
0x1800039b5  mov     rax, [rcx]
0x1800039b8  mov     rax, [rax+48h]
0x1800039bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c1  cmp     eax, 6
0x1800039c4  jz      loc_180003EEE
0x1800039ca  mov     rcx, [rsp+900h+var_8C8]
0x1800039cf  mov     rax, [rcx]
0x1800039d2  mov     rax, [rax+48h]
0x1800039d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039db  cmp     eax, 4
0x1800039de  jz      loc_180003EEE
0x1800039e4  mov     bl, dil
0x1800039e7  mov     [rsp+900h+var_8A4], ebx
0x1800039eb  mov     [rsp+900h+var_8D0], dil
0x1800039f0  mov     rcx, [rsp+900h+var_8C8]
0x1800039f5  add     rcx, 0C20h; ActivityId
0x1800039fc  lea     rdx, [rbp+800h+var_880]
0x180003a00  call    SetActivityId
0x180003a05  mov     rcx, [rsp+900h+var_8C8]
0x180003a0a  mov     rax, [rcx]
0x180003a0d  mov     rax, [rax+48h]
0x180003a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a16  cmp     eax, 2
0x180003a19  jnz     loc_180003B2C
0x180003a1f  cmp     [r14+208h], edi
0x180003a26  jnz     short loc_180003A6E
0x180003a28  mov     rcx, [rsp+900h+var_8C8]
0x180003a2d  mov     rax, [rcx]
0x180003a30  mov     rax, [rax+68h]
0x180003a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a39  test    al, 4
0x180003a3b  jz      short loc_180003A61
0x180003a3d  mov     rcx, [rsp+900h+var_8C8]
0x180003a42  mov     rax, [rcx]
0x180003a45  mov     rax, [rax+78h]
0x180003a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4e  bt      eax, 1Ch
0x180003a52  movzx   ebx, bl
0x180003a55  mov     eax, 1
0x180003a5a  cmovb   ebx, eax
0x180003a5d  mov     [rsp+900h+var_8A4], ebx
0x180003a61  cmp     [r14+208h], edi
0x180003a68  jz      loc_180003B2C
0x180003a6e  mov     rcx, [rsp+900h+var_8C8]
0x180003a73  mov     rax, [rcx]
0x180003a76  mov     rax, [rax+68h]
0x180003a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a7f  test    al, 4
0x180003a81  jnz     short loc_180003ACB
0x180003a83  mov     rcx, [rsp+900h+var_8C8]
0x180003a88  mov     rax, [rcx]
0x180003a8b  mov     rax, [rax+78h]
0x180003a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a94  bt      eax, 1Ch
0x180003a98  jnb     short loc_180003ACB
0x180003a9a  mov     r8d, 0Eh
0x180003aa0  lea     rdx, [rsp+900h+var_8C8]
0x180003aa5  mov     rcx, r13
0x180003aa8  call    ?DoesInterfaceExistWithSameRemoteEndPoints@CDimInterfaceTable@@QEAA_NAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@K@Z; CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(std::tr1::shared_ptr<CDimInterface> &,ulong)
0x180003aad  test    al, al
0x180003aaf  jz      short loc_180003AC6
0x180003ab1  mov     esi, 366h
0x180003ab6  lea     rcx, [rsp+900h+var_8B0]; this
0x180003abb  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180003ac0  nop
0x180003ac1  jmp     loc_180003F0C
0x180003ac6  mov     [rsp+900h+var_8D0], 1
0x180003acb  cmp     [r14+208h], edi
0x180003ad2  jz      short loc_180003B2C
0x180003ad4  mov     rcx, [rsp+900h+var_8C8]
0x180003ad9  mov     rax, [rcx]
0x180003adc  mov     rax, [rax+68h]
0x180003ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae5  test    al, 4
0x180003ae7  jnz     short loc_180003B2C
0x180003ae9  mov     rcx, [rsp+900h+var_8C8]
0x180003aee  mov     rax, [rcx]
0x180003af1  mov     rax, [rax+1C8h]
0x180003af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afd  cmp     eax, 9
0x180003b00  jnz     short loc_180003B2C
0x180003b02  lea     r8d, [rax+23h]
0x180003b06  lea     rdx, [rsp+900h+var_8C8]
0x180003b0b  mov     rcx, r13
0x180003b0e  call    ?DoesInterfaceExistWithSameRemoteEndPoints@CDimInterfaceTable@@QEAA_NAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@K@Z; CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(std::tr1::shared_ptr<CDimInterface> &,ulong)
0x180003b13  test    al, al
0x180003b15  jz      short loc_180003B2C
0x180003b17  mov     esi, 368h
0x180003b1c  lea     rcx, [rsp+900h+var_8B0]; this
0x180003b21  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180003b26  nop
0x180003b27  jmp     loc_180003F0C
0x180003b2c  mov     bl, dil
0x180003b2f  mov     [rsp+900h+var_8B8], bl
0x180003b33  mov     rcx, [rsp+900h+var_8C8]
0x180003b38  mov     rax, [rcx]
0x180003b3b  mov     rax, [rax+68h]
0x180003b3f  cmp     [r14+208h], edi
0x180003b46  jz      short loc_180003BA6
0x180003b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b4d  test    al, 4
0x180003b4f  jnz     loc_180003BEF
0x180003b55  mov     rdi, [rsp+900h+var_8C8]
0x180003b5a  mov     rbx, [rdi]
0x180003b5d  mov     rcx, rdi
0x180003b60  mov     rax, [rbx+68h]
0x180003b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b69  or      eax, 4
0x180003b6c  mov     edx, eax
0x180003b6e  mov     rcx, rdi
0x180003b71  mov     rax, [rbx+70h]
0x180003b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7a  mov     rdi, [rsp+900h+var_8C8]
0x180003b7f  mov     rbx, [rdi]
0x180003b82  mov     rcx, rdi
0x180003b85  mov     rax, [rbx+68h]
0x180003b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8e  btr     eax, 0Eh
0x180003b92  mov     edx, eax
0x180003b94  mov     rcx, rdi
0x180003b97  mov     rax, [rbx+70h]
0x180003b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba0  mov     bl, 1
0x180003ba2  xor     edi, edi
0x180003ba4  jmp     short loc_180003BEF
0x180003ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bab  test    al, 4
0x180003bad  jz      short loc_180003BDA
0x180003baf  mov     rdi, [rsp+900h+var_8C8]
0x180003bb4  mov     rbx, [rdi]
0x180003bb7  mov     rcx, rdi
0x180003bba  mov     rax, [rbx+68h]
0x180003bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc3  and     eax, 0FFFFFFFBh
0x180003bc6  mov     edx, eax
0x180003bc8  mov     rcx, rdi
0x180003bcb  mov     rax, [rbx+70h]
0x180003bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd4  mov     bl, [rsp+900h+var_8B8]
0x180003bd8  xor     edi, edi
0x180003bda  mov     rcx, [rsp+900h+var_8C8]
0x180003bdf  mov     rax, [rcx]
0x180003be2  mov     rax, [rax+28h]
0x180003be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003beb  test    eax, eax
0x180003bed  jnz     short loc_180003C09
0x180003bef  cmp     [r14+208h], edi
0x180003bf6  setnz   dl
0x180003bf9  mov     r8d, 2
0x180003bff  mov     rcx, [rsp+900h+var_8C8]
0x180003c04  call    ?NotifyOfReachabilityChange@CDimInterface@@QEAAX_NW4_UNREACHABILITY_REASON@@@Z; CDimInterface::NotifyOfReachabilityChange(bool,_UNREACHABILITY_REASON)
0x180003c09  cmp     r15d, 1
0x180003c0d  jnz     short loc_180003C74
0x180003c0f  cmp     [r14+21Ch], edi
0x180003c16  jz      loc_180003CD5
0x180003c1c  lea     rcx, [r14+220h]; psz
0x180003c23  lea     r8, [rsp+900h+var_8A8]
0x180003c28  mov     edx, 7D0h; cchMax
0x180003c2d  call    MprUtilGetSizeOfMultiSz
0x180003c32  mov     ecx, eax
0x180003c34  mov     esi, [rsp+900h+var_8A8]
0x180003c38  test    esi, esi
0x180003c3a  jz      short loc_180003C50
0x180003c3c  lea     esi, [r15+56h]
0x180003c40  lea     rcx, [rsp+900h+var_8B0]; this
0x180003c45  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180003c4a  nop
0x180003c4b  jmp     loc_180003F0C
0x180003c50  add     eax, 220h
0x180003c55  cmp     eax, ecx
0x180003c57  jb      short loc_180003C5F
0x180003c59  cmp     eax, [r12]
0x180003c5d  jbe     short loc_180003CD5
0x180003c5f  mov     esi, 57h ; 'W'
0x180003c64  lea     rcx, [rsp+900h+var_8B0]; this
0x180003c69  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180003c6e  nop
0x180003c6f  jmp     loc_180003F0C
0x180003c74  cmp     r15d, 2
0x180003c78  jnz     short loc_180003C9D
0x180003c7a  mov     rcx, [rsp+900h+var_8C8]
0x180003c7f  mov     rax, [rcx]
0x180003c82  mov     rax, [rax+48h]
  ... truncated ...
```
