# CDimInterfaceTable::DeleteInterface(void * const)

- ea: `0x1800033c8`
- end: `0x1800037f9`
- name: `?DeleteInterface@CDimInterfaceTable@@QEAAKQEAX@Z`
- size: `1073`
- prototype: `__int64 __fastcall(CDimInterfaceTable *this, void *const)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f890`

## callees

- `0x180002690`
- `0x180002d80`
- `0x180002ddc`
- `0x18000322c`
- `0x1800033c8`
- `0x180003f40`
- `0x180005340`
- `0x1800055f0`
- `0x180005670`
- `0x1800056c4`
- `0x1800067e0`
- `0x180007bf0`
- `0x18000df70`
- `0x180010e38`
- `0x180012be0`
- `0x1800182a0`
- `0x180018d64`
- `0x18001e4d4`
- `0x180032368`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036ef`
- `RASAPI32!RasDeleteEntryW` at `0x1800036d8`
- `RASAPI32!RasDeleteEntryW` at `0x1800036d8`

## string_xrefs

- `0x18000358d`: `PlumbRDIkev2Policy failed to remove ikev2 policy. Error:%d`
- `0x180003685`: `DeleteInterface: Removing interface from phonebook`
- `0x180003745`: `DeleteInterface: Removing interface from service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDimInterfaceTable::DeleteInterface(CDimInterfaceTable *this, void *const a2)
{
  CDimInterfaceTable *v3; // r14
  char v4; // si
  int v5; // edi
  unsigned int v6; // ebx
  CDimInterface *v7; // rcx
  CDimFullRouterInterface **v8; // rax
  const wchar_t *v9; // rdx
  __int64 v10; // rax
  __int128 *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int128 *v15; // r9
  const WCHAR *v16; // r15
  unsigned int PhonebookPath; // eax
  WCHAR *v18; // rsi
  __int64 v19; // rax
  __int128 *v20; // r9
  CDimInterface *v22; // [rsp+30h] [rbp-D0h] BYREF
  std::tr1::_Ref_count_base *v23; // [rsp+38h] [rbp-C8h]
  LPCWSTR v24; // [rsp+40h] [rbp-C0h] BYREF
  std::tr1::_Ref_count_base *v25; // [rsp+48h] [rbp-B8h]
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+74h] [rbp-8Ch]
  __int128 v30; // [rsp+84h] [rbp-7Ch]
  int v31; // [rsp+94h] [rbp-6Ch]
  int v32; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = g_pCDimInterfaceTable;
  v4 = 0;
  ActivityId = 0;
  v26 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v5 = SetRasServerActivityId(&ActivityId);
  CDimInterfaceTable::AcquireExclusive(v3);
  CDimInterfaceTable::GetCDimInterface(v3, &v22, a2);
  if ( !v22 )
  {
    v6 = 6;
    goto LABEL_41;
  }
  v6 = 0;
  v5 = SetActivityId((LPGUID)v22 + 194);
  if ( !(*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 72LL))(v22)
    || (*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 72LL))(v22) == 1
    || (*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 72LL))(v22) == 2 )
  {
    v7 = v22;
    if ( *((_DWORD *)v22 + 772) )
    {
      v6 = 908;
      goto LABEL_41;
    }
    if ( (*((_DWORD *)v22 + 30) & 0x10000000) != 0 )
    {
      v8 = (CDimFullRouterInterface **)std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(
                                         &v24,
                                         (__int64 *)&v22);
      v6 = CDimFullRouterInterface::PlumbIkev2PskPolicy(*v8, 1);
      if ( v25 )
        std::tr1::_Ref_count_base::_Decref(v25);
      if ( !v6 )
        goto LABEL_26;
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_25;
      v9 = L"PlumbIkev2PskPolicy failed. Error:%d";
    }
    else
    {
      if ( !*((_BYTE *)v3 + 116) )
      {
LABEL_27:
        v12 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v7 + 280LL))(v7);
        MprAdminInterfaceSetCredentialsInternal(v13, v12, 0, 0, 0);
        LOBYTE(v24) = Microsoft_Windows_RRASEnableBits & 8;
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v28) = 0;
          v14 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 280LL))(v22);
          v15 = &v26;
          if ( v22 != (CDimInterface *)-3104LL )
            LODWORD(v15) = (_DWORD)v22 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceInfo,
            (unsigned int)L"DeleteInterface: Removing interface from phonebook",
            (_DWORD)v15,
            v14,
            (__int64)&v28);
        }
        v16 = (const WCHAR *)(*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 280LL))(v22);
        v24 = 0;
        PhonebookPath = RpbkGetPhonebookPath((unsigned __int16 **)&v24);
        v18 = (WCHAR *)v24;
        if ( !PhonebookPath )
          RasDeleteEntryW(v24, v16);
        if ( v18 )
          HeapFree(hHeap, 0, v18);
        v4 = 0;
        goto LABEL_36;
      }
      if ( !(unsigned int)IsCustomIkev2PolicyConfiguredForRoutingDomain((struct _GUID *)v22 + 194)
        || !CDimInterface::IsDimFullRouterInterface(v22)
        || (v6 = CDimInterfaceTable::PlumbRDIkev2Policy(v3)) == 0 )
      {
LABEL_26:
        v7 = v22;
        goto LABEL_27;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      {
LABEL_25:
        v6 = 0;
        goto LABEL_26;
      }
      v9 = L"PlumbRDIkev2Policy failed to remove ikev2 policy. Error:%d";
    }
    LOWORD(v32) = 0;
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v32, v9, v6);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v10 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 280LL))(v22);
      v11 = &v26;
      if ( v22 != (CDimInterface *)-3104LL )
        LODWORD(v11) = (_DWORD)v22 + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceError,
        (unsigned int)&v32,
        (_DWORD)v11,
        v10,
        (__int64)&v28);
    }
    goto LABEL_25;
  }
  v4 = 1;
LABEL_36:
  LOBYTE(v24) = Microsoft_Windows_RRASEnableBits & 8;
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v28) = 0;
    v19 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)v22 + 280LL))(v22);
    v20 = &v26;
    if ( v22 != (CDimInterface *)-3104LL )
      LODWORD(v20) = (_DWORD)v22 + 3104;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDimParamTraceInfo,
      (unsigned int)L"DeleteInterface: Removing interface from service",
      (_DWORD)v20,
      v19,
      (__int64)&v28);
  }
  CDimInterfaceTable::RemoveInterface(v3, a2);
LABEL_41:
  std::tr1::shared_ptr<CDimInterface>::shared_ptr<CDimInterface>(&v24);
  std::tr1::shared_ptr<CDimInterface>::operator=(&v22, &v24);
  if ( v25 )
    std::tr1::_Ref_count_base::_Decref(v25);
  if ( v23 )
    std::tr1::_Ref_count_base::_Decref(v23);
  CDimInterfaceTable::ReleaseExclusive(v3);
  UpdateGlobalPhoneBookContext();
  if ( !v6 && v4 )
    RouterIdentityObjectUpdateAttributes(0, 0);
  if ( v5 )
    ReSetActivityId(&ActivityId);
  return v6;
}

```

## disassembly

```asm
0x1800033c8  push    rbp
0x1800033ca  push    rbx
0x1800033cb  push    rsi
0x1800033cc  push    rdi
0x1800033cd  push    r12
0x1800033cf  push    r14
0x1800033d1  push    r15
0x1800033d3  lea     rbp, [rsp-7B0h]
0x1800033db  sub     rsp, 8B0h
0x1800033e2  mov     rax, cs:__security_cookie
0x1800033e9  xor     rax, rsp
0x1800033ec  mov     [rbp+7E0h+var_40], rax
0x1800033f3  mov     r12, rdx
0x1800033f6  mov     r14, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x1800033fd  xor     sil, sil
0x180003400  xorps   xmm0, xmm0
0x180003403  movups  xmmword ptr [rsp+8E0h+ActivityId.Data1], xmm0
0x180003408  xorps   xmm1, xmm1
0x18000340b  movups  [rsp+8E0h+var_890], xmm1
0x180003410  xor     eax, eax
0x180003412  mov     [rbp+7E0h+var_840], eax
0x180003415  xor     edx, edx; Val
0x180003417  mov     r8d, 7FCh; Size
0x18000341d  lea     rcx, [rbp+7E0h+var_83C]; void *
0x180003421  call    memset_0
0x180003426  xor     eax, eax
0x180003428  mov     [rsp+8E0h+var_870], eax
0x18000342c  xorps   xmm0, xmm0
0x18000342f  movups  [rsp+8E0h+var_86C], xmm0
0x180003434  movups  [rbp+7E0h+var_85C], xmm0
0x180003438  mov     [rbp+7E0h+var_84C], eax
0x18000343b  lea     rcx, [rsp+8E0h+ActivityId]; ActivityId
0x180003440  call    SetRasServerActivityId
0x180003445  mov     edi, eax
0x180003447  mov     rcx, r14; this
0x18000344a  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x18000344f  mov     r8, r12
0x180003452  lea     rdx, [rsp+8E0h+var_8B0]
0x180003457  mov     rcx, r14
0x18000345a  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x18000345f  nop
0x180003460  mov     rcx, [rsp+8E0h+var_8B0]
0x180003465  test    rcx, rcx
0x180003468  jnz     short loc_180003472
0x18000346a  lea     ebx, [rcx+6]
0x18000346d  jmp     loc_18000376F
0x180003472  xor     ebx, ebx
0x180003474  add     rcx, 0C20h; ActivityId
0x18000347b  lea     rdx, [rsp+8E0h+ActivityId]
0x180003480  call    SetActivityId
0x180003485  mov     edi, eax
0x180003487  mov     rcx, [rsp+8E0h+var_8B0]
0x18000348c  mov     rax, [rcx]
0x18000348f  mov     rax, [rax+48h]
0x180003493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003498  test    eax, eax
0x18000349a  jz      short loc_1800034D0
0x18000349c  mov     rcx, [rsp+8E0h+var_8B0]
0x1800034a1  mov     rax, [rcx]
0x1800034a4  mov     rax, [rax+48h]
0x1800034a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ad  cmp     eax, 1
0x1800034b0  jz      short loc_1800034D0
0x1800034b2  mov     rcx, [rsp+8E0h+var_8B0]
0x1800034b7  mov     rax, [rcx]
0x1800034ba  mov     rax, [rax+48h]
0x1800034be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c3  cmp     eax, 2
0x1800034c6  jz      short loc_1800034D0
0x1800034c8  mov     sil, 1
0x1800034cb  jmp     loc_1800036F8
0x1800034d0  mov     rcx, [rsp+8E0h+var_8B0]
0x1800034d5  cmp     [rcx+0C10h], ebx
0x1800034db  jz      short loc_1800034E7
0x1800034dd  mov     ebx, 38Ch
0x1800034e2  jmp     loc_18000376F
0x1800034e7  test    dword ptr [rcx+78h], 10000000h
0x1800034ee  jz      short loc_18000353A
0x1800034f0  lea     rdx, [rsp+8E0h+var_8B0]
0x1800034f5  lea     rcx, [rsp+8E0h+var_8A0]
0x1800034fa  call    ??$static_pointer_cast@VCDimFullRouterInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimFullRouterInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x1800034ff  nop
0x180003500  mov     dl, 1; bool
0x180003502  mov     rcx, [rax]; this
0x180003505  call    ?PlumbIkev2PskPolicy@CDimFullRouterInterface@@QEAAK_N@Z; CDimFullRouterInterface::PlumbIkev2PskPolicy(bool)
0x18000350a  mov     ebx, eax
0x18000350c  mov     rcx, [rsp+8E0h+var_898]; this
0x180003511  test    rcx, rcx
0x180003514  jz      short loc_18000351C
0x180003516  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000351b  nop
0x18000351c  test    ebx, ebx
0x18000351e  jz      loc_180003605
0x180003524  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000352b  jz      loc_180003603
0x180003531  lea     rdx, aPlumbikev2pskp_0; "PlumbIkev2PskPolicy failed. Error:%d"
0x180003538  jmp     short loc_180003594
0x18000353a  cmp     [r14+74h], bl
0x18000353e  jz      loc_18000360A
0x180003544  add     rcx, 0C20h; struct _GUID *
0x18000354b  call    ?IsCustomIkev2PolicyConfiguredForRoutingDomain@@YAHPEAU_GUID@@@Z; IsCustomIkev2PolicyConfiguredForRoutingDomain(_GUID *)
0x180003550  test    eax, eax
0x180003552  jz      loc_180003605
0x180003558  mov     rcx, [rsp+8E0h+var_8B0]; this
0x18000355d  call    ?IsDimFullRouterInterface@CDimInterface@@QEBA_NXZ; CDimInterface::IsDimFullRouterInterface(void)
0x180003562  test    al, al
0x180003564  jz      loc_180003605
0x18000356a  mov     r8b, 1
0x18000356d  lea     rdx, [rsp+8E0h+var_8B0]
0x180003572  mov     rcx, r14; this
0x180003575  call    ?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@_N@Z; CDimInterfaceTable::PlumbRDIkev2Policy(std::tr1::shared_ptr<CDimInterface> &,bool)
0x18000357a  mov     ebx, eax
0x18000357c  test    eax, eax
0x18000357e  jz      loc_180003605
0x180003584  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000358b  jz      short loc_180003603
0x18000358d  lea     rdx, aPlumbrdikev2po_0; "PlumbRDIkev2Policy failed to remove ike"...
0x180003594  xor     eax, eax
0x180003596  mov     word ptr [rbp+7E0h+var_840], ax
0x18000359a  mov     word ptr [rsp+8E0h+var_870], ax
0x18000359f  mov     r8d, ebx
0x1800035a2  lea     rcx, [rbp+7E0h+var_840]
0x1800035a6  call    FormatRRASErrorString
0x1800035ab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800035b2  jz      short loc_180003603
0x1800035b4  mov     rcx, [rsp+8E0h+var_8B0]
0x1800035b9  mov     rax, [rcx]
0x1800035bc  mov     rax, [rax+118h]
0x1800035c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c8  mov     rcx, [rsp+8E0h+var_8B0]
0x1800035cd  lea     r9, [rsp+8E0h+var_890]
0x1800035d2  add     rcx, 0C20h
0x1800035d9  cmovnz  r9, rcx
0x1800035dd  lea     rcx, [rsp+8E0h+var_870]
0x1800035e2  mov     [rsp+8E0h+var_8B8], rcx
0x1800035e7  mov     [rsp+8E0h+var_8C0], rax
0x1800035ec  lea     r8, [rbp+7E0h+var_840]
0x1800035f0  lea     rdx, RasDimParamTraceError
0x1800035f7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800035fe  call    McTemplateU0zjzz_EventWriteTransfer
0x180003603  xor     ebx, ebx
0x180003605  mov     rcx, [rsp+8E0h+var_8B0]
0x18000360a  mov     rax, [rcx]
0x18000360d  mov     rax, [rax+118h]
0x180003614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003619  mov     rdx, rax
0x18000361c  mov     [rsp+8E0h+var_8C0], 0
0x180003625  xor     r9d, r9d
0x180003628  xor     r8d, r8d
0x18000362b  call    MprAdminInterfaceSetCredentialsInternal
0x180003630  test    ebx, ebx
0x180003632  jnz     loc_18000376C
0x180003638  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18000363e  and     al, 8
0x180003640  mov     byte ptr [rsp+8E0h+var_8A0], al
0x180003644  jz      short loc_18000369F
0x180003646  xor     eax, eax
0x180003648  mov     word ptr [rsp+8E0h+var_870], ax
0x18000364d  mov     rcx, [rsp+8E0h+var_8B0]
0x180003652  mov     rax, [rcx]
0x180003655  mov     rax, [rax+118h]
0x18000365c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003661  mov     rcx, [rsp+8E0h+var_8B0]
0x180003666  add     rcx, 0C20h
0x18000366d  lea     r9, [rsp+8E0h+var_890]
0x180003672  cmovnz  r9, rcx
0x180003676  lea     rcx, [rsp+8E0h+var_870]
0x18000367b  mov     [rsp+8E0h+var_8B8], rcx
0x180003680  mov     [rsp+8E0h+var_8C0], rax
0x180003685  lea     r8, aDeleteinterfac; "DeleteInterface: Removing interface fro"...
0x18000368c  lea     rdx, RasDimParamTraceInfo
0x180003693  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000369a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000369f  mov     rcx, [rsp+8E0h+var_8B0]
0x1800036a4  mov     rax, [rcx]
0x1800036a7  mov     rax, [rax+118h]
0x1800036ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b3  mov     r15, rax
0x1800036b6  mov     [rsp+8E0h+var_8A0], 0
0x1800036bf  lea     rcx, [rsp+8E0h+var_8A0]; unsigned __int16 **
0x1800036c4  call    ?RpbkGetPhonebookPath@@YAKPEAPEAG@Z; RpbkGetPhonebookPath(ushort * *)
0x1800036c9  mov     rsi, [rsp+8E0h+var_8A0]
0x1800036ce  test    eax, eax
0x1800036d0  jnz     short loc_1800036DE
0x1800036d2  mov     rdx, r15; LPCWSTR
0x1800036d5  mov     rcx, rsi; LPCWSTR
0x1800036d8  call    cs:__imp_RasDeleteEntryW
0x1800036de  test    rsi, rsi
0x1800036e1  jz      short loc_1800036F5
0x1800036e3  mov     r8, rsi; lpMem
0x1800036e6  xor     edx, edx; dwFlags
0x1800036e8  mov     rcx, cs:hHeap; hHeap
0x1800036ef  call    cs:__imp_HeapFree
0x1800036f5  xor     sil, sil
0x1800036f8  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x1800036fe  and     al, 8
0x180003700  mov     byte ptr [rsp+8E0h+var_8A0], al
0x180003704  jz      short loc_18000375F
0x180003706  xor     eax, eax
0x180003708  mov     word ptr [rsp+8E0h+var_870], ax
0x18000370d  mov     rcx, [rsp+8E0h+var_8B0]
0x180003712  mov     rax, [rcx]
0x180003715  mov     rax, [rax+118h]
0x18000371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003721  mov     rcx, [rsp+8E0h+var_8B0]
0x180003726  add     rcx, 0C20h
0x18000372d  lea     r9, [rsp+8E0h+var_890]
0x180003732  cmovnz  r9, rcx
0x180003736  lea     r8, [rsp+8E0h+var_870]
0x18000373b  mov     [rsp+8E0h+var_8B8], r8
0x180003740  mov     [rsp+8E0h+var_8C0], rax
0x180003745  lea     r8, aDeleteinterfac_0; "DeleteInterface: Removing interface fro"...
0x18000374c  lea     rdx, RasDimParamTraceInfo
0x180003753  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000375a  call    McTemplateU0zjzz_EventWriteTransfer
0x18000375f  mov     rdx, r12; void *
0x180003762  mov     rcx, r14; this
0x180003765  call    ?RemoveInterface@CDimInterfaceTable@@EEAAXQEAX@Z; CDimInterfaceTable::RemoveInterface(void * const)
0x18000376a  jmp     short loc_18000376F
0x18000376c  xor     sil, sil
0x18000376f  lea     rcx, [rsp+8E0h+var_8A0]
0x180003774  call    ??0?$shared_ptr@VCDimInterface@@@tr1@std@@QEAA@$$T@Z; std::tr1::shared_ptr<CDimInterface>::shared_ptr<CDimInterface>(std::nullptr_t)
0x180003779  lea     rdx, [rsp+8E0h+var_8A0]
0x18000377e  lea     rcx, [rsp+8E0h+var_8B0]
0x180003783  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@$$QEAV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> &&)
0x180003788  nop
0x180003789  mov     rcx, [rsp+8E0h+var_898]; this
0x18000378e  test    rcx, rcx
0x180003791  jz      short loc_180003799
0x180003793  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180003798  nop
0x180003799  mov     rcx, [rsp+8E0h+var_8A8]; this
0x18000379e  test    rcx, rcx
0x1800037a1  jz      short loc_1800037A9
0x1800037a3  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800037a8  nop
0x1800037a9  mov     rcx, r14; this
0x1800037ac  call    ?ReleaseExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseExclusive(void)
0x1800037b1  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x1800037b6  test    ebx, ebx
0x1800037b8  jnz     short loc_1800037C8
0x1800037ba  test    sil, sil
0x1800037bd  jz      short loc_1800037C8
0x1800037bf  xor     edx, edx; BOOLEAN
0x1800037c1  xor     ecx, ecx; PVOID
0x1800037c3  call    ?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z; RouterIdentityObjectUpdateAttributes(void *,uchar)
0x1800037c8  test    edi, edi
0x1800037ca  jz      short loc_1800037D6
0x1800037cc  lea     rcx, [rsp+8E0h+ActivityId]; ActivityId
0x1800037d1  call    ReSetActivityId
0x1800037d6  mov     eax, ebx
0x1800037d8  mov     rcx, [rbp+7E0h+var_40]
0x1800037df  xor     rcx, rsp; StackCookie
0x1800037e2  call    __security_check_cookie
0x1800037e7  add     rsp, 8B0h
0x1800037ee  pop     r15
0x1800037f0  pop     r14
0x1800037f2  pop     r12
0x1800037f4  pop     rdi
0x1800037f5  pop     rsi
0x1800037f6  pop     rbx
0x1800037f7  pop     rbp
0x1800037f8  retn
```
