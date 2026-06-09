# CDimInterfaceTable::UpdatePhonebookInfo(void * const)

- ea: `0x180027f74`
- end: `0x18002863a`
- name: `?UpdatePhonebookInfo@CDimInterfaceTable@@QEAAKQEAX@Z`
- size: `1734`
- prototype: `unsigned int __fastcall(CDimInterfaceTable *__hidden this, void *const)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800107f0`

## callees

- `0x180002c78`
- `0x180002d80`
- `0x180002ddc`
- `0x180003f40`
- `0x180003f58`
- `0x180005340`
- `0x1800055f0`
- `0x180005670`
- `0x1800056c4`
- `0x18000b534`
- `0x18000d854`
- `0x18000df70`
- `0x180010e38`
- `0x180012be0`
- `0x1800244d0`
- `0x180025c24`
- `0x18002737c`
- `0x180027f74`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x1800280c0`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x1800280c0`

## string_xrefs

- `0x180028351`: `Failed to delete PSK specific IKEv2 policies. Error:%d`
- `0x18002813a`: `Another IKEv2 PSK interface using the same destination already exists. Disabling this interface`
- `0x18002820f`: `Another GRE interface using the same GRE key and destination already exists. Disabling this interface`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDimInterfaceTable::UpdatePhonebookInfo(CDimInterfaceTable *this, unsigned __int64 a2)
{
  CDimInterfaceTable *v3; // rdi
  int v4; // r13d
  unsigned int v5; // ebx
  int v6; // r14d
  bool v7; // r12
  char v8; // r15
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // r14d
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  __int128 *v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // esi
  __int64 v17; // rax
  __int128 *v18; // r9
  bool v19; // si
  unsigned int v20; // eax
  __int64 v21; // rax
  __int128 *v22; // r9
  __int64 v23; // rax
  __int128 *v24; // r9
  __int64 v25; // rax
  __int128 *v26; // r9
  struct IDimSRWLock *v28; // [rsp+30h] [rbp-D0h] BYREF
  std::tr1::_Ref_count_base *v29; // [rsp+38h] [rbp-C8h]
  CDimFullRouterInterface *v30; // [rsp+40h] [rbp-C0h] BYREF
  std::tr1::_Ref_count_base *v31; // [rsp+48h] [rbp-B8h]
  char v32[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+58h] [rbp-A8h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  __int128 v36; // [rsp+7Ch] [rbp-84h]
  __int128 v37; // [rsp+8Ch] [rbp-74h]
  int v38; // [rsp+9Ch] [rbp-64h]
  int v39; // [rsp+A0h] [rbp-60h] BYREF
  char v40[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = g_pCDimInterfaceTable;
  ActivityId = 0;
  v33 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v4 = SetRasServerActivityId(&ActivityId);
  if ( !*((_BYTE *)v3 + 117) )
    UpdateGlobalPhoneBookContext();
  CDimInterfaceTable::AcquireExclusive(v3);
  CDimInterfaceTable::GetCDimInterface((__int64)v3, &v28, a2);
  if ( !v28 )
  {
    v5 = 6;
    if ( v29 )
      std::tr1::_Ref_count_base::_Decref(v29);
    goto LABEL_75;
  }
  v5 = 0;
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v32, v28);
  v6 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 120LL))(v28);
  v7 = 0;
  v8 = 0;
  v4 = SetActivityId((LPGUID)v28 + 194);
  v11 = v6 & 0x10000000;
  if ( !v11 )
    v7 = (unsigned int)IsCustomIkev2PolicyConfiguredForRoutingDomain((struct _GUID *)v28 + 194) != 0;
  if ( !*((_BYTE *)v3 + 117) )
  {
    CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(v3, &v28, v9, v10);
    CDimInterfaceTable::RemoveInterfaceFromHostNameMap(v3, &v28);
    IfObjectLoadPhonebookInfo(v28, 0);
    CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(v3, &v28);
    CDimInterfaceTable::InsertInterfaceInHostNameMap(v3, &v28);
  }
  if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 104LL))(v28) & 4) != 0 && v11 )
  {
    if ( (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v3, &v28, 14) )
    {
      v8 = 1;
      v5 = 870;
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        v12 = L"Another IKEv2 PSK interface using the same destination already exists. Disabling this interface";
        goto LABEL_16;
      }
    }
LABEL_25:
    if ( !v8 )
      goto LABEL_35;
    goto LABEL_26;
  }
  if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 104LL))(v28) & 4) == 0 )
    goto LABEL_25;
  if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 456LL))(v28) != 9 )
    goto LABEL_25;
  if ( !(unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v3, &v28, 44) )
    goto LABEL_25;
  v8 = 1;
  v5 = 872;
  if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
    goto LABEL_25;
  v12 = L"Another GRE interface using the same GRE key and destination already exists. Disabling this interface";
LABEL_16:
  LOWORD(v35) = 0;
  LOWORD(v39) = 0;
  FormatRRASErrorString(&v39, v12, v5);
  if ( (Microsoft_Windows_RRASEnableBits & 1) == 0 )
    goto LABEL_25;
  v13 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 280LL))(v28);
  v14 = &v33;
  if ( v28 != (struct IDimSRWLock *)-3104LL )
    LODWORD(v14) = (_DWORD)v28 + 3104;
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasDimParamTraceAdminError,
    (unsigned int)&v39,
    (_DWORD)v14,
    v13,
    (__int64)&v35);
LABEL_26:
  v15 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 768LL))(v28);
  v16 = v15;
  if ( v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v39) = 0;
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v39, L"Failed to Disable Interface. Error: %d", v15);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v17 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 280LL))(v28);
        v18 = &v33;
        if ( v28 != (struct IDimSRWLock *)-3104LL )
          LODWORD(v18) = (_DWORD)v28 + 3104;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v39,
          (_DWORD)v18,
          v17,
          (__int64)&v35);
      }
    }
    v5 = v16;
    scoped_lock::~scoped_lock((scoped_lock *)v32);
    if ( v29 )
      std::tr1::_Ref_count_base::_Decref(v29);
    goto LABEL_75;
  }
LABEL_35:
  if ( v11 && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 120LL))(v28) & 0x10000000) == 0 )
  {
    v19 = 0;
    std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v30, (__int64 *)&v28);
    v20 = CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v30, 1);
    v5 = v20;
    if ( v20 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v39) = 0;
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v39, L"Failed to delete PSK specific IKEv2 policies. Error:%d", v20);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v21 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 280LL))(v28);
          v22 = &v33;
          if ( v28 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v22) = (_DWORD)v28 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v39,
            (_DWORD)v22,
            v21,
            (__int64)&v35);
        }
      }
      v5 = 0;
    }
    if ( v7 && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 104LL))(v28) & 4) != 0 )
      v19 = v8 == 0;
    if ( v31 )
      std::tr1::_Ref_count_base::_Decref(v31);
    if ( !v19 )
      goto LABEL_73;
    goto LABEL_64;
  }
  if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 104LL))(v28) & 4) != 0
    && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 120LL))(v28) & 0x10000000) != 0 )
  {
    std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v30, (__int64 *)&v28);
    v5 = CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v30, 0);
    if ( v5 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v39) = 0;
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v39, L"Failed to plumb PSK specific IKEv2 policies. Error:%d", v5);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v23 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 280LL))(v28);
          v24 = &v33;
          if ( v28 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v24) = (_DWORD)v28 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v39,
            (_DWORD)v24,
            v23,
            (__int64)&v35);
        }
      }
      v5 = 0;
    }
    if ( v31 )
      std::tr1::_Ref_count_base::_Decref(v31);
    goto LABEL_73;
  }
  if ( v7 )
  {
LABEL_64:
    std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v30, (__int64 *)&v28);
    CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v30, 1);
    v5 = CDimFullRouterInterface::PlumbIkev2PskPolicy((struct _GUID *)v30, 0);
    if ( v5 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v39) = 0;
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v39, L"PlumbIkev2PskPolicy failed to add ikev2 policy. Error:%d", v5);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v25 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 280LL))(v28);
          v26 = &v33;
          if ( v28 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v26) = (_DWORD)v28 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v39,
            (_DWORD)v26,
            v25,
            (__int64)&v35);
        }
      }
      v5 = ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v28 + 104LL))(v28) & 4) == 0 ? 0x367 : 0;
    }
    if ( v31 )
      std::tr1::_Ref_count_base::_Decref(v31);
  }
LABEL_73:
  scoped_lock::~scoped_lock((scoped_lock *)v32);
  if ( v29 )
    std::tr1::_Ref_count_base::_Decref(v29);
LABEL_75:
  CDimInterfaceTable::ReleaseExclusive(v3);
  if ( v4 )
    ReSetActivityId(&ActivityId);
  return v5;
}

```

## disassembly

```asm
0x180027f74  push    rbp
0x180027f76  push    rbx
0x180027f77  push    rsi
0x180027f78  push    rdi
0x180027f79  push    r12
0x180027f7b  push    r13
0x180027f7d  push    r14
0x180027f7f  push    r15
0x180027f81  lea     rbp, [rsp-7B8h]
0x180027f89  sub     rsp, 8B8h
0x180027f90  mov     rax, cs:__security_cookie
0x180027f97  xor     rax, rsp
0x180027f9a  mov     [rbp+7F0h+var_50], rax
0x180027fa1  mov     rbx, rdx
0x180027fa4  mov     rdi, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180027fab  xorps   xmm0, xmm0
0x180027fae  movups  xmmword ptr [rsp+8F0h+ActivityId.Data1], xmm0
0x180027fb3  xorps   xmm1, xmm1
0x180027fb6  movups  [rsp+8F0h+var_898], xmm1
0x180027fbb  xor     eax, eax
0x180027fbd  mov     [rbp+7F0h+var_850], eax
0x180027fc0  xor     edx, edx; Val
0x180027fc2  mov     r8d, 7FCh; Size
0x180027fc8  lea     rcx, [rbp+7F0h+var_84C]; void *
0x180027fcc  call    memset_0
0x180027fd1  xor     eax, eax
0x180027fd3  mov     [rsp+8F0h+var_878], eax
0x180027fd7  xorps   xmm0, xmm0
0x180027fda  movups  [rsp+8F0h+var_874], xmm0
0x180027fdf  movups  [rbp+7F0h+var_864], xmm0
0x180027fe3  mov     [rbp+7F0h+var_854], eax
0x180027fe6  lea     rcx, [rsp+8F0h+ActivityId]; ActivityId
0x180027feb  call    SetRasServerActivityId
0x180027ff0  mov     r13d, eax
0x180027ff3  cmp     byte ptr [rdi+75h], 0
0x180027ff7  jnz     short loc_180027FFE
0x180027ff9  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x180027ffe  mov     rcx, rdi; this
0x180028001  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x180028006  mov     r8, rbx
0x180028009  lea     rdx, [rsp+8F0h+var_8C0]
0x18002800e  mov     rcx, rdi
0x180028011  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x180028016  nop
0x180028017  mov     rdx, [rsp+8F0h+var_8C0]; struct IDimSRWLock *
0x18002801c  test    rdx, rdx
0x18002801f  jnz     short loc_180028039
0x180028021  lea     ebx, [rdx+6]
0x180028024  mov     rcx, [rsp+8F0h+var_8B8]; this
0x180028029  test    rcx, rcx
0x18002802c  jz      short loc_180028034
0x18002802e  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180028033  nop
0x180028034  jmp     loc_1800285FE
0x180028039  xor     ebx, ebx
0x18002803b  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180028040  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x180028045  nop
0x180028046  mov     rcx, [rsp+8F0h+var_8C0]
0x18002804b  mov     rax, [rcx]
0x18002804e  mov     rax, [rax+78h]
0x180028052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028057  mov     r14d, eax
0x18002805a  xor     r12b, r12b
0x18002805d  xor     r15b, r15b
0x180028060  mov     rcx, [rsp+8F0h+var_8C0]
0x180028065  add     rcx, 0C20h; ActivityId
0x18002806c  lea     rdx, [rsp+8F0h+ActivityId]
0x180028071  call    SetActivityId
0x180028076  mov     r13d, eax
0x180028079  and     r14d, 10000000h
0x180028080  jnz     short loc_180028099
0x180028082  mov     rcx, [rsp+8F0h+var_8C0]
0x180028087  add     rcx, 0C20h; struct _GUID *
0x18002808e  call    ?IsCustomIkev2PolicyConfiguredForRoutingDomain@@YAHPEAU_GUID@@@Z; IsCustomIkev2PolicyConfiguredForRoutingDomain(_GUID *)
0x180028093  test    eax, eax
0x180028095  setnz   r12b
0x180028099  cmp     [rdi+75h], r15b
0x18002809d  jnz     short loc_1800280E0
0x18002809f  lea     rdx, [rsp+8F0h+var_8C0]
0x1800280a4  mov     rcx, rdi
0x1800280a7  call    ?RemoveInterfaceFromRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800280ac  lea     rdx, [rsp+8F0h+var_8C0]
0x1800280b1  mov     rcx, rdi
0x1800280b4  call    ?RemoveInterfaceFromHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800280b9  xor     edx, edx
0x1800280bb  mov     rcx, [rsp+8F0h+var_8C0]
0x1800280c0  call    cs:__imp_IfObjectLoadPhonebookInfo
0x1800280c6  lea     rdx, [rsp+8F0h+var_8C0]
0x1800280cb  mov     rcx, rdi
0x1800280ce  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800280d3  lea     rdx, [rsp+8F0h+var_8C0]
0x1800280d8  mov     rcx, rdi
0x1800280db  call    ?InsertInterfaceInHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800280e0  mov     rcx, [rsp+8F0h+var_8C0]
0x1800280e5  mov     rax, [rcx]
0x1800280e8  mov     rax, [rax+68h]
0x1800280ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280f1  mov     sil, 4
0x1800280f4  test    sil, al
0x1800280f7  jz      loc_1800281B6
0x1800280fd  test    r14d, r14d
0x180028100  jz      loc_1800281B6
0x180028106  mov     r8d, 0Eh
0x18002810c  lea     rdx, [rsp+8F0h+var_8C0]
0x180028111  mov     rcx, rdi
0x180028114  call    ?DoesInterfaceExistWithSameRemoteEndPoints@CDimInterfaceTable@@QEAA_NAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@K@Z; CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(std::tr1::shared_ptr<CDimInterface> &,ulong)
0x180028119  test    al, al
0x18002811b  jz      loc_18002821B
0x180028121  mov     eax, 1
0x180028126  mov     r15b, al
0x180028129  mov     ebx, 366h
0x18002812e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x180028134  jz      loc_18002821B
0x18002813a  lea     rdx, aAnotherIkev2Ps; "Another IKEv2 PSK interface using the s"...
0x180028141  xor     eax, eax
0x180028143  mov     r8d, ebx
0x180028146  mov     word ptr [rsp+8F0h+var_878], ax
0x18002814b  mov     word ptr [rbp+7F0h+var_850], ax
0x18002814f  lea     rcx, [rbp+7F0h+var_850]
0x180028153  call    FormatRRASErrorString
0x180028158  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002815f  jz      loc_18002821B
0x180028165  mov     rcx, [rsp+8F0h+var_8C0]
0x18002816a  mov     rax, [rcx]
0x18002816d  mov     rax, [rax+118h]
0x180028174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028179  mov     rcx, [rsp+8F0h+var_8C0]
0x18002817e  add     rcx, 0C20h
0x180028185  lea     r9, [rsp+8F0h+var_898]
0x18002818a  cmovnz  r9, rcx
0x18002818e  lea     rcx, [rsp+8F0h+var_878]
0x180028193  mov     [rsp+8F0h+var_8C8], rcx
0x180028198  mov     [rsp+8F0h+var_8D0], rax
0x18002819d  lea     r8, [rbp+7F0h+var_850]
0x1800281a1  lea     rdx, RasDimParamTraceAdminError
0x1800281a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800281af  call    McTemplateU0zjzz_EventWriteTransfer
0x1800281b4  jmp     short loc_180028224
0x1800281b6  mov     rcx, [rsp+8F0h+var_8C0]
0x1800281bb  mov     rax, [rcx]
0x1800281be  mov     rax, [rax+68h]
0x1800281c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281c7  test    sil, al
0x1800281ca  jz      short loc_18002821B
0x1800281cc  mov     rcx, [rsp+8F0h+var_8C0]
0x1800281d1  mov     rax, [rcx]
0x1800281d4  mov     rax, [rax+1C8h]
0x1800281db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e0  cmp     eax, 9
0x1800281e3  jnz     short loc_18002821B
0x1800281e5  lea     r8d, [rax+23h]
0x1800281e9  lea     rdx, [rsp+8F0h+var_8C0]
0x1800281ee  mov     rcx, rdi
0x1800281f1  call    ?DoesInterfaceExistWithSameRemoteEndPoints@CDimInterfaceTable@@QEAA_NAEAV?$shared_ptr@VCDimInterface@@@tr1@std@@K@Z; CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(std::tr1::shared_ptr<CDimInterface> &,ulong)
0x1800281f6  test    al, al
0x1800281f8  jz      short loc_18002821B
0x1800281fa  mov     eax, 1
0x1800281ff  mov     r15b, al
0x180028202  mov     ebx, 368h
0x180028207  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x18002820d  jz      short loc_18002821B
0x18002820f  lea     rdx, aAnotherGreInte; "Another GRE interface using the same GR"...
0x180028216  jmp     loc_180028141
0x18002821b  test    r15b, r15b
0x18002821e  jz      loc_1800282E6
0x180028224  mov     rcx, [rsp+8F0h+var_8C0]
0x180028229  mov     rax, [rcx]
0x18002822c  mov     rax, [rax+300h]
0x180028233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028238  mov     esi, eax
0x18002823a  test    eax, eax
0x18002823c  jz      loc_1800282E3
0x180028242  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180028249  jz      short loc_1800282C1
0x18002824b  xor     ecx, ecx
0x18002824d  mov     word ptr [rbp+7F0h+var_850], cx
0x180028251  mov     word ptr [rsp+8F0h+var_878], cx
0x180028256  mov     r8d, eax
0x180028259  lea     rdx, aFailedToDisabl; "Failed to Disable Interface. Error: %d"
0x180028260  lea     rcx, [rbp+7F0h+var_850]
0x180028264  call    FormatRRASErrorString
0x180028269  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180028270  jz      short loc_1800282C1
0x180028272  mov     rcx, [rsp+8F0h+var_8C0]
0x180028277  mov     rax, [rcx]
0x18002827a  mov     rax, [rax+118h]
0x180028281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028286  mov     rcx, [rsp+8F0h+var_8C0]
0x18002828b  add     rcx, 0C20h
0x180028292  lea     r9, [rsp+8F0h+var_898]
0x180028297  cmovnz  r9, rcx
0x18002829b  lea     rdx, [rsp+8F0h+var_878]
0x1800282a0  mov     [rsp+8F0h+var_8C8], rdx
0x1800282a5  mov     [rsp+8F0h+var_8D0], rax
0x1800282aa  lea     r8, [rbp+7F0h+var_850]
0x1800282ae  lea     rdx, RasDimParamTraceError
0x1800282b5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800282bc  call    McTemplateU0zjzz_EventWriteTransfer
0x1800282c1  mov     ebx, esi
0x1800282c3  lea     rcx, [rsp+8F0h+var_8A0]; this
0x1800282c8  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x1800282cd  nop
0x1800282ce  mov     rcx, [rsp+8F0h+var_8B8]; this
0x1800282d3  test    rcx, rcx
0x1800282d6  jz      short loc_1800282DE
0x1800282d8  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800282dd  nop
0x1800282de  jmp     loc_1800285FE
0x1800282e3  mov     sil, 4
0x1800282e6  test    r14d, r14d
0x1800282e9  jz      loc_180028401
0x1800282ef  mov     rcx, [rsp+8F0h+var_8C0]
0x1800282f4  mov     rax, [rcx]
0x1800282f7  mov     rax, [rax+78h]
0x1800282fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028300  bt      eax, 1Ch
0x180028304  jb      loc_180028401
0x18002830a  xor     sil, sil
0x18002830d  lea     rdx, [rsp+8F0h+var_8C0]
0x180028312  lea     rcx, [rsp+8F0h+var_8B0]
0x180028317  call    ??$static_pointer_cast@VCDimFullRouterInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimFullRouterInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x18002831c  nop
0x18002831d  mov     r14d, 1
0x180028323  mov     dl, r14b; bool
0x180028326  mov     rcx, [rsp+8F0h+var_8B0]; this
0x18002832b  call    ?PlumbIkev2PskPolicy@CDimFullRouterInterface@@QEAAK_N@Z; CDimFullRouterInterface::PlumbIkev2PskPolicy(bool)
0x180028330  mov     ebx, eax
0x180028332  test    eax, eax
0x180028334  jz      loc_1800283BB
0x18002833a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180028341  jz      short loc_1800283B9
0x180028343  xor     ecx, ecx
0x180028345  mov     word ptr [rbp+7F0h+var_850], cx
0x180028349  mov     word ptr [rsp+8F0h+var_878], cx
0x18002834e  mov     r8d, eax
0x180028351  lea     rdx, aFailedToDelete; "Failed to delete PSK specific IKEv2 pol"...
0x180028358  lea     rcx, [rbp+7F0h+var_850]
0x18002835c  call    FormatRRASErrorString
0x180028361  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180028368  jz      short loc_1800283B9
0x18002836a  mov     rcx, [rsp+8F0h+var_8C0]
0x18002836f  mov     rax, [rcx]
0x180028372  mov     rax, [rax+118h]
0x180028379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002837e  mov     rcx, [rsp+8F0h+var_8C0]
0x180028383  add     rcx, 0C20h
0x18002838a  lea     r9, [rsp+8F0h+var_898]
0x18002838f  cmovnz  r9, rcx
0x180028393  lea     rcx, [rsp+8F0h+var_878]
0x180028398  mov     [rsp+8F0h+var_8C8], rcx
0x18002839d  mov     [rsp+8F0h+var_8D0], rax
0x1800283a2  lea     r8, [rbp+7F0h+var_850]
0x1800283a6  lea     rdx, RasDimParamTraceError
0x1800283ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800283b4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800283b9  xor     ebx, ebx
0x1800283bb  test    r12b, r12b
0x1800283be  jz      short loc_1800283E0
0x1800283c0  mov     rcx, [rsp+8F0h+var_8C0]
0x1800283c5  mov     rax, [rcx]
0x1800283c8  mov     rax, [rax+68h]
0x1800283cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283d1  test    al, 4
0x1800283d3  jz      short loc_1800283E0
0x1800283d5  movzx   esi, sil
0x1800283d9  test    r15b, r15b
0x1800283dc  cmovz   esi, r14d
0x1800283e0  mov     rcx, [rsp+8F0h+var_8A8]; this
0x1800283e5  test    rcx, rcx
0x1800283e8  jz      short loc_1800283F0
0x1800283ea  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800283ef  nop
0x1800283f0  test    sil, sil
0x1800283f3  jz      loc_1800285E3
0x1800283f9  mov     sil, 4
0x1800283fc  jmp     loc_180028501
0x180028401  mov     rcx, [rsp+8F0h+var_8C0]
0x180028406  mov     rax, [rcx]
0x180028409  mov     rax, [rax+68h]
0x18002840d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028412  test    sil, al
0x180028415  jz      loc_1800284F2
0x18002841b  mov     rcx, [rsp+8F0h+var_8C0]
0x180028420  mov     rax, [rcx]
0x180028423  mov     rax, [rax+78h]
0x180028427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002842c  bt      eax, 1Ch
0x180028430  jnb     loc_1800284F2
0x180028436  lea     rdx, [rsp+8F0h+var_8C0]
0x18002843b  lea     rcx, [rsp+8F0h+var_8B0]
0x180028440  call    ??$static_pointer_cast@VCDimFullRouterInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimFullRouterInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x180028445  nop
0x180028446  xor     edx, edx; bool
0x180028448  mov     rcx, [rsp+8F0h+var_8B0]; this
0x18002844d  call    ?PlumbIkev2PskPolicy@CDimFullRouterInterface@@QEAAK_N@Z; CDimFullRouterInterface::PlumbIkev2PskPolicy(bool)
0x180028452  mov     ebx, eax
0x180028454  test    eax, eax
0x180028456  jz      loc_1800284DD
0x18002845c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
  ... truncated ...
```
