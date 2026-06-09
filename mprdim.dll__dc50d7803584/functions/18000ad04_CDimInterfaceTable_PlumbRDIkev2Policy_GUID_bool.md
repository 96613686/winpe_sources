# CDimInterfaceTable::PlumbRDIkev2Policy(_GUID *,bool)

- ea: `0x18000ad04`
- end: `0x18000b52e`
- name: `?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKPEAU_GUID@@_N@Z`
- size: `2090`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, struct _GUID *, bool)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000eb60`
- `0x18001382c`
- `0x180013a68`
- `0x180014244`
- `0x180014fcc`

## callees

- `0x180002578`
- `0x180002afc`
- `0x180002c78`
- `0x180002d80`
- `0x180005670`
- `0x18000ad04`
- `0x18000b534`
- `0x18000b654`
- `0x18000d854`
- `0x18000df70`
- `0x18001e4d4`
- `0x1800219f4`
- `0x180022208`
- `0x180035d10`
- `0x1800442f0`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b1b7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b4f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b1b7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b4f8`
- `MPRDDM!DDMPlumbRDIkev2TunnelPolicy` at `0x18000b437`
- `MPRDDM!DDMPlumbRDIkev2TunnelPolicy` at `0x18000b437`

## string_xrefs

- `0x18000ae3b`: `PlumbRDIkev2Policy: GetRoutingDomainConfiguration failed: %d`
- `0x18000aede`: `PlumbRDIkev2Policy: Custom policy is not configured`
- `0x18000b00e`: `PlumbRDIkev2Policy:  UpdateRemoteEndpoints failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDimInterfaceTable::PlumbRDIkev2Policy(
        CDimInterfaceTable *this,
        struct _GUID *a2,
        unsigned __int8 a3)
{
  int v4; // ebx
  struct _GUID *v5; // r12
  struct IDimSRWLock *v6; // r14
  char *v7; // rdi
  unsigned int RoutingDomainConfiguration; // eax
  unsigned int v9; // r14d
  __int128 *v10; // r9
  __int128 *v11; // r9
  _QWORD *v12; // rsi
  _QWORD *v13; // rbx
  unsigned int v14; // edi
  _QWORD *v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int updated; // eax
  __int64 v21; // rax
  __int128 *v22; // r9
  __int64 v23; // rcx
  _QWORD *i; // rax
  unsigned __int64 v25; // r13
  bool v26; // zf
  __int128 *v27; // r9
  void *v28; // rax
  int v29; // r14d
  _QWORD *v30; // rsi
  _QWORD *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  const wchar_t *v35; // r8
  __int64 v36; // rax
  __int128 *v37; // r9
  __int64 v38; // r14
  __int64 v39; // rcx
  _QWORD *j; // rax
  __int128 *v41; // r9
  unsigned int v43; // [rsp+30h] [rbp-938h]
  unsigned int v44; // [rsp+30h] [rbp-938h]
  int v45; // [rsp+34h] [rbp-934h] BYREF
  struct _GUID *v46; // [rsp+38h] [rbp-930h]
  char *v47; // [rsp+40h] [rbp-928h] BYREF
  CDimInterfaceTable *v48; // [rsp+48h] [rbp-920h]
  struct _GUID *v49; // [rsp+50h] [rbp-918h]
  _QWORD **v50; // [rsp+60h] [rbp-908h]
  char v51[8]; // [rsp+68h] [rbp-900h] BYREF
  CDimFullRouterInterface *v52; // [rsp+70h] [rbp-8F8h] BYREF
  std::tr1::_Ref_count_base *v53; // [rsp+78h] [rbp-8F0h]
  __int64 v54[14]; // [rsp+80h] [rbp-8E8h] BYREF
  __int128 v55; // [rsp+F0h] [rbp-878h] BYREF
  int v56; // [rsp+100h] [rbp-868h] BYREF
  __int128 v57; // [rsp+104h] [rbp-864h]
  __int128 v58; // [rsp+114h] [rbp-854h]
  int v59; // [rsp+124h] [rbp-844h]
  int v60; // [rsp+130h] [rbp-838h] BYREF
  char v61[2044]; // [rsp+134h] [rbp-834h] BYREF

  v4 = (int)a2;
  v46 = a2;
  v5 = a2;
  v49 = a2;
  v6 = g_pCDimInterfaceTable;
  v48 = g_pCDimInterfaceTable;
  memset_0(v54, 0, 0x68u);
  v7 = 0;
  v47 = 0;
  v55 = 0;
  v60 = 0;
  memset_0(v61, 0, sizeof(v61));
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v51, v6);
  if ( a3 )
  {
    v9 = 0;
    v45 = 0;
  }
  else
  {
    v45 = 104;
    RoutingDomainConfiguration = GetRoutingDomainConfiguration(v5, 8u, 0, (__int64)&v45, (__int64)v54);
    v9 = RoutingDomainConfiguration;
    if ( RoutingDomainConfiguration )
    {
      if ( RoutingDomainConfiguration == 1168 )
      {
        v9 = 0;
      }
      else if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v60) = 0;
        LOWORD(v56) = 0;
        FormatRRASErrorString(
          &v60,
          L"PlumbRDIkev2Policy: GetRoutingDomainConfiguration failed: %d",
          RoutingDomainConfiguration);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v10 = &v55;
          if ( v5 )
            LODWORD(v10) = v4;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v60,
            (_DWORD)v10,
            0,
            (__int64)&v56);
        }
      }
      goto LABEL_94;
    }
    if ( !v54[7] )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v56) = 0;
        v11 = &v55;
        if ( v5 )
          LODWORD(v11) = v4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminError,
          (unsigned int)L"PlumbRDIkev2Policy: Custom policy is not configured",
          (_DWORD)v11,
          0,
          (__int64)&v56);
      }
      goto LABEL_93;
    }
    v45 = 1;
  }
  v50 = (_QWORD **)((char *)v48 + 224);
  v12 = (_QWORD *)*((_QWORD *)v48 + 28);
  v13 = (_QWORD *)*v12;
  v14 = 0;
  while ( v13 != v12 )
  {
    v15 = v13 + 4;
    if ( CDimInterface::IsDimFullRouterInterface((CDimInterface *)v13[4]) )
    {
      v16 = *v15;
      v17 = *(_QWORD *)(*v15 + 3104LL) - *(_QWORD *)&v5->Data1;
      if ( !v17 )
        v17 = *(_QWORD *)(v16 + 3112) - *(_QWORD *)v5->Data4;
      if ( !v17 )
      {
        (**(void (__fastcall ***)(__int64))v16)(v16);
        if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 120LL))(*v15) & 0x10000000) != 0 )
          goto LABEL_39;
        if ( a3 )
          goto LABEL_38;
        if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 104LL))(*v15) & 4) == 0 )
          goto LABEL_39;
        CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(v48, v13 + 4, v18, v19);
        std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v52, v13 + 4);
        updated = CDimFullRouterInterface::UpdateRemoteEndPoints(v52);
        v9 = updated;
        if ( !updated )
        {
          CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(v48, v13 + 4);
          if ( v53 )
            std::tr1::_Ref_count_base::_Decref(v53);
          if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 344LL))(*v15) )
LABEL_38:
            ++v14;
LABEL_39:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
          goto LABEL_40;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v60) = 0;
          LOWORD(v56) = 0;
          FormatRRASErrorString(&v60, L"PlumbRDIkev2Policy:  UpdateRemoteEndpoints failed: %d", updated);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 280LL))(*v15);
            v22 = &v55;
            if ( v5 )
              LODWORD(v22) = (_DWORD)v46;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v60,
              (_DWORD)v22,
              v21,
              (__int64)&v56);
          }
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 768LL))(*v15);
        if ( v53 )
          std::tr1::_Ref_count_base::_Decref(v53);
      }
    }
LABEL_40:
    if ( !*((_BYTE *)v13 + 49) )
    {
      v23 = v13[2];
      if ( *(_BYTE *)(v23 + 49) )
      {
        for ( i = (_QWORD *)v13[1]; !*((_BYTE *)i + 49) && v13 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v13 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v23);
      }
      v13 = i;
    }
  }
  v43 = v14;
  v25 = v14;
  v26 = v14 == 0;
  v7 = v47;
  if ( v26 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      LOWORD(v56) = 0;
      v27 = &v55;
      if ( v5 )
        LODWORD(v27) = (_DWORD)v46;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceAdminError,
        (unsigned int)L"PlumbRDIkev2Policy: No interface found.",
        (_DWORD)v27,
        0,
        (__int64)&v56);
    }
  }
  else
  {
    try
    {
      v28 = operator new[](saturated_mul(v25, 0x20u));
      std::unique_ptr<unsigned short [0]>::reset(&v47, v28);
      operator delete[](0);
    }
    catch ( std::bad_alloc )
    {
      std::unique_ptr<unsigned short [0]>::reset(&v47, 0);
      v5 = v49;
      v29 = (int)v49;
      v46 = v49;
      LODWORD(v25) = v43;
      goto LABEL_54;
    }
    v29 = (int)v46;
LABEL_54:
    v7 = v47;
    if ( v47 )
    {
      v44 = 0;
      v30 = *v50;
      v31 = (_QWORD *)**v50;
      while ( v31 != v30 )
      {
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 72LL))(v31[4]) == 2 )
        {
          v32 = v31[4];
          v33 = *(_QWORD *)(v32 + 3104) - *(_QWORD *)&v5->Data1;
          if ( !v33 )
            v33 = *(_QWORD *)(v32 + 3112) - *(_QWORD *)v5->Data4;
          if ( !v33 )
          {
            (**(void (__fastcall ***)(__int64))v32)(v32);
            if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 120LL))(v31[4]) & 0x10000000) == 0
              && (a3 || ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 104LL))(v31[4]) & 4) != 0)
              && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 344LL))(v31[4]) )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
              {
                LOWORD(v60) = 0;
                LOWORD(v56) = 0;
                v34 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 280LL))(v31[4]);
                v35 = L"Removing";
                if ( !a3 )
                  v35 = L"Plumbing";
                FormatRRASErrorString(&v60, L"%s IKEv2 policies for %s ...", v35, v34);
                if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
                {
                  v36 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 280LL))(v31[4]);
                  v37 = &v55;
                  if ( v5 )
                    LODWORD(v37) = v29;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasDimParamTraceAdminInfo,
                    (unsigned int)&v60,
                    (_DWORD)v37,
                    v36,
                    (__int64)&v56);
                }
              }
              if ( v44 < (unsigned int)v25 )
              {
                v38 = 32LL * v44;
                *(_QWORD *)&v7[v38] = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 16LL))(v31[4]);
                *(_QWORD *)&v7[v38 + 8] = v31[4] + 832LL;
                *(_DWORD *)&v7[v38 + 16] = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 344LL))(v31[4]);
                *(_QWORD *)&v7[v38 + 24] = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 352LL))(v31[4]);
                ++v44;
              }
            }
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[4] + 8LL))(v31[4]);
          }
        }
        v29 = (int)v46;
        if ( !*((_BYTE *)v31 + 49) )
        {
          v39 = v31[2];
          if ( *(_BYTE *)(v39 + 49) )
          {
            for ( j = (_QWORD *)v31[1]; !*((_BYTE *)j + 49) && v31 == (_QWORD *)j[2]; j = (_QWORD *)j[1] )
              v31 = j;
          }
          else
          {
            j = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v39);
          }
          v31 = j;
        }
      }
      if ( (gbldwDIMComponentsLoaded & 4) != 0 )
        v9 = DDMPlumbRDIkev2TunnelPolicy(a3, v5, v54, (unsigned int)v25, v7);
      else
        v9 = 903;
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v60) = 0;
        LOWORD(v56) = 0;
        FormatRRASErrorString(&v60, L"PlumbRDIkev2Policy: malloc failed", 8);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v41 = &v55;
          if ( v5 )
            LODWORD(v41) = v29;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v60,
            (_DWORD)v41,
            0,
            (__int64)&v56);
        }
      }
      v9 = 8;
    }
  }
  if ( v45 )
LABEL_93:
    FreeRoutingDomainConfiguration(8, v54);
LABEL_94:
  scoped_read_lock::~scoped_read_lock((scoped_read_lock *)v51);
  operator delete[](v7);
  return v9;
}

```

## disassembly

```asm
0x18000ad04  mov     r11, rsp
0x18000ad07  mov     [r11+8], rbx
0x18000ad0b  mov     [r11+20h], rsi
0x18000ad0f  mov     [r11+18h], r8b
0x18000ad13  push    rdi
0x18000ad14  push    r12
0x18000ad16  push    r13
0x18000ad18  push    r14
0x18000ad1a  push    r15
0x18000ad1c  sub     rsp, 940h
0x18000ad23  mov     rax, cs:__security_cookie
0x18000ad2a  xor     rax, rsp
0x18000ad2d  mov     [rsp+968h+var_38], rax
0x18000ad35  mov     sil, r8b
0x18000ad38  mov     rbx, rdx
0x18000ad3b  mov     [rsp+968h+var_930], rdx
0x18000ad40  mov     r12, rdx
0x18000ad43  mov     [rsp+968h+var_918], rdx
0x18000ad48  mov     r14, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x18000ad4f  mov     [rsp+968h+var_920], r14
0x18000ad54  mov     r13d, 68h ; 'h'
0x18000ad5a  mov     r8d, r13d; Size
0x18000ad5d  xor     edx, edx; Val
0x18000ad5f  lea     rcx, [r11-8E8h]; void *
0x18000ad66  call    memset_0
0x18000ad6b  xor     r15d, r15d
0x18000ad6e  mov     edi, r15d
0x18000ad71  mov     [rsp+968h+var_928], r15
0x18000ad76  xorps   xmm0, xmm0
0x18000ad79  movups  [rsp+968h+var_878], xmm0
0x18000ad81  mov     [rsp+968h+var_838], r15d
0x18000ad89  xor     edx, edx; Val
0x18000ad8b  mov     r8d, 7FCh; Size
0x18000ad91  lea     rcx, [rsp+968h+var_834]; void *
0x18000ad99  call    memset_0
0x18000ad9e  mov     [rsp+968h+var_868], r15d
0x18000ada6  xorps   xmm0, xmm0
0x18000ada9  xor     eax, eax
0x18000adab  movups  [rsp+968h+var_864], xmm0
0x18000adb3  movups  [rsp+968h+var_854], xmm0
0x18000adbb  mov     [rsp+968h+var_844], eax
0x18000adc2  mov     rdx, r14; struct IDimSRWLock *
0x18000adc5  lea     rcx, [rsp+968h+var_900]; this
0x18000adca  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x18000adcf  nop
0x18000add0  test    sil, sil
0x18000add3  jnz     loc_18000AF07
0x18000add9  mov     [rsp+968h+var_934], r13d
0x18000adde  lea     rax, [rsp+968h+var_8E8]
0x18000ade6  mov     [rsp+968h+var_948], rax; __int64
0x18000adeb  lea     r9, [rsp+968h+var_934]
0x18000adf0  xor     r8d, r8d
0x18000adf3  lea     edx, [r13-60h]
0x18000adf7  mov     rcx, r12; struct _GUID *
0x18000adfa  call    GetRoutingDomainConfiguration
0x18000adff  mov     r14d, eax
0x18000ae02  test    eax, eax
0x18000ae04  jz      loc_18000AE9D
0x18000ae0a  cmp     eax, 490h
0x18000ae0f  jnz     short loc_18000AE19
0x18000ae11  mov     r14d, r15d
0x18000ae14  jmp     loc_18000B4EA
0x18000ae19  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000ae20  jz      loc_18000B4EA
0x18000ae26  mov     word ptr [rsp+968h+var_838], r15w
0x18000ae2f  mov     word ptr [rsp+968h+var_868], r15w
0x18000ae38  mov     r8d, eax
0x18000ae3b  lea     rdx, aPlumbrdikev2po_2; "PlumbRDIkev2Policy: GetRoutingDomainCon"...
0x18000ae42  lea     rcx, [rsp+968h+var_838]
0x18000ae4a  call    FormatRRASErrorString
0x18000ae4f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000ae56  jz      loc_18000B4EA
0x18000ae5c  lea     r9, [rsp+968h+var_878]
0x18000ae64  test    r12, r12
0x18000ae67  cmovnz  r9, rbx
0x18000ae6b  lea     rax, [rsp+968h+var_868]
0x18000ae73  mov     [rsp+968h+var_940], rax
0x18000ae78  mov     [rsp+968h+var_948], r15
0x18000ae7d  lea     r8, [rsp+968h+var_838]
0x18000ae85  lea     rdx, RasDimParamTraceError
0x18000ae8c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ae93  call    McTemplateU0zjzz_EventWriteTransfer
0x18000ae98  jmp     loc_18000B4EA
0x18000ae9d  cmp     [rsp+968h+var_8B0], r15
0x18000aea5  jnz     short loc_18000AEFD
0x18000aea7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18000aeae  jz      loc_18000B4D7
0x18000aeb4  mov     word ptr [rsp+968h+var_868], r15w
0x18000aebd  lea     r9, [rsp+968h+var_878]
0x18000aec5  test    r12, r12
0x18000aec8  cmovnz  r9, rbx
0x18000aecc  lea     rax, [rsp+968h+var_868]
0x18000aed4  mov     [rsp+968h+var_940], rax
0x18000aed9  mov     [rsp+968h+var_948], r15
0x18000aede  lea     r8, aPlumbrdikev2po; "PlumbRDIkev2Policy: Custom policy is no"...
0x18000aee5  lea     rdx, RasDimParamTraceAdminError
0x18000aeec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aef3  call    McTemplateU0zjzz_EventWriteTransfer
0x18000aef8  jmp     loc_18000B4D7
0x18000aefd  mov     [rsp+968h+var_934], 1
0x18000af05  jmp     short loc_18000AF0F
0x18000af07  mov     r14d, r15d
0x18000af0a  mov     [rsp+968h+var_934], r15d
0x18000af0f  mov     [rsp+968h+var_938], r15d
0x18000af14  mov     rax, [rsp+968h+var_920]
0x18000af19  add     rax, 0E0h
0x18000af1f  mov     [rsp+968h+var_908], rax
0x18000af24  mov     rsi, [rax]
0x18000af27  mov     rbx, [rsi]
0x18000af2a  mov     edi, r15d
0x18000af2d  cmp     rbx, rsi
0x18000af30  jz      loc_18000B125
0x18000af36  lea     r13, [rbx+20h]
0x18000af3a  mov     rcx, [r13+0]; this
0x18000af3e  call    ?IsDimFullRouterInterface@CDimInterface@@QEBA_NXZ; CDimInterface::IsDimFullRouterInterface(void)
0x18000af43  test    al, al
0x18000af45  jz      loc_18000B0E9
0x18000af4b  mov     rcx, [r13+0]
0x18000af4f  mov     rax, [rcx+0C20h]
0x18000af56  sub     rax, [r12]
0x18000af5a  jnz     short loc_18000AF68
0x18000af5c  mov     rax, [rcx+0C28h]
0x18000af63  sub     rax, [r12+8]
0x18000af68  test    rax, rax
0x18000af6b  jnz     loc_18000B0E9
0x18000af71  mov     rax, [rcx]
0x18000af74  mov     rax, [rax]
0x18000af77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af7c  mov     rcx, [r13+0]
0x18000af80  mov     rax, [rcx]
0x18000af83  mov     rax, [rax+78h]
0x18000af87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8c  bt      eax, 1Ch
0x18000af90  jb      loc_18000B0D9
0x18000af96  cmp     [rsp+968h+arg_10], r15b
0x18000af9e  jnz     loc_18000B0D7
0x18000afa4  mov     rcx, [r13+0]
0x18000afa8  mov     rax, [rcx]
0x18000afab  mov     rax, [rax+68h]
0x18000afaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb4  test    al, 4
0x18000afb6  jz      loc_18000B0D9
0x18000afbc  mov     rdx, r13
0x18000afbf  mov     rcx, [rsp+968h+var_920]
0x18000afc4  call    ?RemoveInterfaceFromRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x18000afc9  mov     rdx, r13
0x18000afcc  lea     rcx, [rsp+968h+var_8F8]
0x18000afd1  call    ??$static_pointer_cast@VCDimFullRouterInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimFullRouterInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x18000afd6  nop
0x18000afd7  mov     rcx, [rsp+968h+var_8F8]; this
0x18000afdc  call    ?UpdateRemoteEndPoints@CDimFullRouterInterface@@QEAAKXZ; CDimFullRouterInterface::UpdateRemoteEndPoints(void)
0x18000afe1  mov     r14d, eax
0x18000afe4  test    eax, eax
0x18000afe6  jz      loc_18000B0A2
0x18000afec  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000aff3  jz      loc_18000B07C
0x18000aff9  mov     word ptr [rsp+968h+var_838], r15w
0x18000b002  mov     word ptr [rsp+968h+var_868], r15w
0x18000b00b  mov     r8d, eax
0x18000b00e  lea     rdx, aPlumbrdikev2po_3; "PlumbRDIkev2Policy:  UpdateRemoteEndpoi"...
0x18000b015  lea     rcx, [rsp+968h+var_838]
0x18000b01d  call    FormatRRASErrorString
0x18000b022  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000b029  jz      short loc_18000B07C
0x18000b02b  mov     rcx, [r13+0]
0x18000b02f  mov     rax, [rcx]
0x18000b032  mov     rax, [rax+118h]
0x18000b039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03e  lea     r9, [rsp+968h+var_878]
0x18000b046  test    r12, r12
0x18000b049  cmovnz  r9, [rsp+968h+var_930]
0x18000b04f  lea     rcx, [rsp+968h+var_868]
0x18000b057  mov     [rsp+968h+var_940], rcx
0x18000b05c  mov     [rsp+968h+var_948], rax
0x18000b061  lea     r8, [rsp+968h+var_838]
0x18000b069  lea     rdx, RasDimParamTraceError
0x18000b070  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b077  call    McTemplateU0zjzz_EventWriteTransfer
0x18000b07c  mov     rcx, [r13+0]
0x18000b080  mov     rax, [rcx]
0x18000b083  mov     rax, [rax+300h]
0x18000b08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08f  nop
0x18000b090  mov     rcx, [rsp+968h+var_8F0]; this
0x18000b095  test    rcx, rcx
0x18000b098  jz      short loc_18000B0A0
0x18000b09a  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000b09f  nop
0x18000b0a0  jmp     short loc_18000B0E9
0x18000b0a2  mov     rdx, r13
0x18000b0a5  mov     rcx, [rsp+968h+var_920]
0x18000b0aa  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x18000b0af  nop
0x18000b0b0  mov     rcx, [rsp+968h+var_8F0]; this
0x18000b0b5  test    rcx, rcx
0x18000b0b8  jz      short loc_18000B0C0
0x18000b0ba  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000b0bf  nop
0x18000b0c0  mov     rcx, [r13+0]
0x18000b0c4  mov     rax, [rcx]
0x18000b0c7  mov     rax, [rax+158h]
0x18000b0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d3  test    eax, eax
0x18000b0d5  jz      short loc_18000B0D9
0x18000b0d7  inc     edi
0x18000b0d9  mov     rcx, [r13+0]
0x18000b0dd  mov     rax, [rcx]
0x18000b0e0  mov     rax, [rax+8]
0x18000b0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e9  cmp     [rbx+31h], r15b
0x18000b0ed  jnz     loc_18000AF2D
0x18000b0f3  mov     rcx, [rbx+10h]
0x18000b0f7  cmp     [rcx+31h], r15b
0x18000b0fb  jnz     short loc_18000B104
0x18000b0fd  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x18000b102  jmp     short loc_18000B11D
0x18000b104  mov     rax, [rbx+8]
0x18000b108  jmp     short loc_18000B117
0x18000b10a  cmp     rbx, [rax+10h]
0x18000b10e  jnz     short loc_18000B11D
0x18000b110  mov     rbx, rax
0x18000b113  mov     rax, [rax+8]
0x18000b117  cmp     [rax+31h], r15b
0x18000b11b  jz      short loc_18000B10A
0x18000b11d  mov     rbx, rax
0x18000b120  jmp     loc_18000AF2D
0x18000b125  mov     [rsp+968h+var_938], edi
0x18000b129  mov     r13d, edi
0x18000b12c  test    edi, edi
0x18000b12e  mov     rdi, [rsp+968h+var_928]
0x18000b133  jnz     short loc_18000B18D
0x18000b135  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18000b13c  jz      loc_18000B4D0
0x18000b142  mov     word ptr [rsp+968h+var_868], r15w
0x18000b14b  lea     r9, [rsp+968h+var_878]
0x18000b153  test    r12, r12
0x18000b156  cmovnz  r9, [rsp+968h+var_930]
0x18000b15c  lea     rax, [rsp+968h+var_868]
0x18000b164  mov     [rsp+968h+var_940], rax
0x18000b169  mov     [rsp+968h+var_948], r15
0x18000b16e  lea     r8, aPlumbrdikev2po_5; "PlumbRDIkev2Policy: No interface found."
0x18000b175  lea     rdx, RasDimParamTraceAdminError
0x18000b17c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b183  call    McTemplateU0zjzz_EventWriteTransfer
0x18000b188  jmp     loc_18000B4D0
0x18000b18d  mov     eax, 20h ; ' '
0x18000b192  mul     r13
0x18000b195  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b19c  cmovb   rax, rcx
0x18000b1a0  mov     rcx, rax; unsigned __int64
0x18000b1a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b1a8  mov     rdx, rax
0x18000b1ab  lea     rcx, [rsp+968h+var_928]
0x18000b1b0  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18000b1b5  xor     ecx, ecx
0x18000b1b7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b1bd  nop
0x18000b1be  mov     r14, [rsp+968h+var_930]
0x18000b1c3  jmp     short loc_18000B1DA
0x18000b1c5  xor     r15d, r15d
0x18000b1c8  mov     r12, [rsp+968h+var_918]
0x18000b1cd  mov     r14, r12
0x18000b1d0  mov     [rsp+968h+var_930], r12
0x18000b1d5  mov     r13d, [rsp+968h+var_938]
0x18000b1da  mov     rdi, [rsp+968h+var_928]
0x18000b1df  test    rdi, rdi
0x18000b1e2  jz      loc_18000B450
0x18000b1e8  mov     [rsp+968h+var_938], r15d
0x18000b1ed  mov     rsi, [rsp+968h+var_908]
0x18000b1f2  mov     rsi, [rsi]
0x18000b1f5  mov     rbx, [rsi]
0x18000b1f8  cmp     rbx, rsi
0x18000b1fb  jz      loc_18000B413
0x18000b201  mov     rcx, [rbx+20h]
0x18000b205  mov     rax, [rcx]
0x18000b208  mov     rax, [rax+48h]
0x18000b20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b211  cmp     eax, 2
0x18000b214  jnz     loc_18000B3D2
0x18000b21a  mov     rcx, [rbx+20h]
0x18000b21e  mov     rax, [rcx+0C20h]
0x18000b225  sub     rax, [r12]
0x18000b229  jnz     short loc_18000B237
0x18000b22b  mov     rax, [rcx+0C28h]
0x18000b232  sub     rax, [r12+8]
0x18000b237  test    rax, rax
0x18000b23a  jnz     loc_18000B3D2
0x18000b240  mov     rax, [rcx]
0x18000b243  mov     rax, [rax]
0x18000b246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b24b  mov     rcx, [rbx+20h]
0x18000b24f  mov     rax, [rcx]
0x18000b252  mov     rax, [rax+78h]
0x18000b256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b25b  bt      eax, 1Ch
0x18000b25f  jb      loc_18000B3C2
0x18000b265  cmp     [rsp+968h+arg_10], r15b
0x18000b26d  jnz     short loc_18000B287
0x18000b26f  mov     rcx, [rbx+20h]
0x18000b273  mov     rax, [rcx]
  ... truncated ...
```
