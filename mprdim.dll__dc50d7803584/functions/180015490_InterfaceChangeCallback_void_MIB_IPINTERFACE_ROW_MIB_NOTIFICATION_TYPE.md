# InterfaceChangeCallback(void *,_MIB_IPINTERFACE_ROW *,_MIB_NOTIFICATION_TYPE)

- ea: `0x180015490`
- end: `0x180015acb`
- name: `?InterfaceChangeCallback@@YAXPEAXPEAU_MIB_IPINTERFACE_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `1595`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001610`
- `0x180003f58`
- `0x1800056c4`
- `0x18000d854`
- `0x18000da10`
- `0x18000def0`
- `0x18000df70`
- `0x180013c9c`
- `0x180015490`
- `0x180015ad4`
- `0x180024450`
- `0x180027304`
- `0x180033e90`
- `0x180035244`
- `0x1800454dc`
- `0x180045694`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a90`

## string_xrefs

- `0x1800155c3`: `InterfaceChangeCallback: Got interface %s notification. Interface LUID:0x%I64x, Compartment Id:%d`
- `0x180015614`: `InterfaceChangeCallback: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x1800156b4`: `InterfaceChangeCallback: Ignoring notification for %ws, compartment %d, as this routing domain is not enabled for RRAS`
- `0x18001571b`: `RoutingDomainChangeCallback: GetRoutingDomainConfiguration for %ws, compartment %d failed with error %d. Ignoring the error`
- `0x18001580f`: `InterfaceChangeCallback: NsiGetInterfaceIndexAndLuidFromIsolationInfo for VSID:%d failed with error %d`
- `0x1800158ac`: `InterfaceChangeCallback: IsTenantInterfacePresentInRegistry failed with error %d`
- `0x180015919`: `InterfaceChangeCallback: DimCreateInterfaceEntry failed with error %d`
- `0x18001593f`: `InterfaceChangeCallback: Interface (LUID: 0x%I64x, VSID:%d) already present in the registry. Not creating a new entry. Current stack name: %ws`
- `0x180015a03`: `InterfaceChangeCallback: Interface (LUID: 0x%I64x, VSID:%d) is already loaded in service.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InterfaceChangeCallback(
        PVOID CallerContext,
        PMIB_IPINTERFACE_ROW Row,
        MIB_NOTIFICATION_TYPE NotificationType)
{
  __int64 v3; // rbx
  NET_IF_COMPARTMENT_ID v5; // edi
  struct _DIM_COMPARTMENT_INTERFACE *v6; // r14
  int v7; // esi
  unsigned int RoutingDomainIdForCompartment; // eax
  unsigned int v9; // eax
  CDimInterfaceTable *v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // r12d
  unsigned int *v14; // rdi
  unsigned int InterfaceIndexAndLuidFromIsolationInfo; // eax
  NET_LUID *p_InterfaceLuid; // r15
  unsigned int v17; // eax
  CDimInterfaceTable *v18; // rcx
  const wchar_t *v19; // rdx
  unsigned int v20; // eax
  PNET_IFINDEX InterfaceIndex; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h]
  unsigned int v23; // [rsp+34h] [rbp-CCh] BYREF
  int v24; // [rsp+38h] [rbp-C8h] BYREF
  struct _DIM_COMPARTMENT_INTERFACE *v25; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v29[4]; // [rsp+60h] [rbp-A0h]
  GUID v30; // [rsp+80h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v34; // [rsp+B4h] [rbp-4Ch]
  __int128 v35; // [rsp+C4h] [rbp-3Ch]
  int v36; // [rsp+D4h] [rbp-2Ch]
  _BYTE v37[80]; // [rsp+E0h] [rbp-20h] BYREF
  int v38; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v39[2044]; // [rsp+134h] [rbp+34h] BYREF

  v3 = NotificationType;
  v5 = (unsigned int)CallerContext;
  v29[0] = L"Parameter";
  v29[1] = L"Addition";
  v29[2] = L"Deletion";
  v29[3] = L"Initial";
  v6 = 0;
  v25 = 0;
  v30 = GUID_NULL;
  v23 = 0;
  *(_QWORD *)v27 = 0;
  v26 = 0;
  v24 = 0;
  memset_0(v37, 0, sizeof(v37));
  ActivityId = 0;
  v32 = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( !Row || (_DWORD)v3 == 3 || !(_DWORD)v3 )
    return;
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v28, (struct IDimSRWLock *)&gblRoutingDomainOpsLock);
  v7 = SetRasServerActivityId(&ActivityId);
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v38) = 0;
    FormatRRASErrorString(
      &v38,
      L"InterfaceChangeCallback: Got interface %s notification. Interface LUID:0x%I64x, Compartment Id:%d",
      v29[v3],
      Row->InterfaceLuid.Value,
      v5);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v38);
  }
  RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(v5, &v30);
  if ( RoutingDomainIdForCompartment )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v38) = 0;
      FormatRRASErrorString(
        &v38,
        L"InterfaceChangeCallback: NsiGetRoutingDomainIdForCompartment failed with error %d",
        RoutingDomainIdForCompartment);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v38);
    }
    goto LABEL_61;
  }
  if ( v7 )
    ReSetActivityId(&ActivityId);
  v22 = SetActivityId(&v30);
  MprConvertGuidToString(&v30, 40, v37);
  v9 = IsRoutingDomainAvailable(&v30, &v24);
  if ( v9 )
  {
    if ( v9 == 1168 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_60;
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      FormatRRASErrorString(
        &v38,
        L"InterfaceChangeCallback: Ignoring notification for %ws, compartment %d, as this routing domain is not enabled for RRAS",
        v37,
        v5);
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_60;
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      LODWORD(InterfaceIndex) = v9;
      FormatRRASErrorString(
        &v38,
        L"RoutingDomainChangeCallback: GetRoutingDomainConfiguration for %ws, compartment %d failed with error %d. Ignoring the error",
        v37,
        v5,
        InterfaceIndex);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_60;
    goto LABEL_18;
  }
  if ( !v24 )
    goto LABEL_60;
  if ( (_DWORD)v3 != 1 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v38, aInterfacechang_3, Row->InterfaceLuid.Value);
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceInfo,
          (unsigned int)&v38,
          (unsigned int)&v30,
          0,
          (__int64)&v33);
    }
    CDimInterfaceTable::RemoveInterface(v10, &v30, &Row->InterfaceLuid);
    goto LABEL_60;
  }
  v11 = DimEnumerateInterfacesFromStack(v5, &v23, &v25);
  if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      FormatRRASErrorString(&v38, L"InterfaceChangeCallback: DimEnumerateInterfacesFromStack failed with error %d", v11);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v38,
          (unsigned int)&v30,
          0,
          (__int64)&v33);
    }
    goto LABEL_27;
  }
  v12 = 0;
  v13 = v23;
  if ( !v23 )
  {
LABEL_27:
    v6 = v25;
    goto LABEL_60;
  }
  v6 = v25;
  while ( 1 )
  {
    v14 = (unsigned int *)((char *)v6 + 536 * v12);
    InterfaceIndexAndLuidFromIsolationInfo = NsiGetInterfaceIndexAndLuidFromIsolationInfo(
                                               *((_QWORD *)v14 + 1),
                                               (__int64)&v30,
                                               *v14,
                                               (ULONG64 *)v27,
                                               &v26);
    if ( InterfaceIndexAndLuidFromIsolationInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v38) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(
          &v38,
          L"InterfaceChangeCallback: NsiGetInterfaceIndexAndLuidFromIsolationInfo for VSID:%d failed with error %d",
          *v14,
          InterfaceIndexAndLuidFromIsolationInfo);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v38,
            (unsigned int)&v30,
            0,
            (__int64)&v33);
      }
      goto LABEL_35;
    }
    p_InterfaceLuid = &Row->InterfaceLuid;
    if ( *(_QWORD *)v27 == Row->InterfaceLuid.Value )
      break;
LABEL_35:
    if ( ++v12 >= v13 )
      goto LABEL_60;
  }
  v23 = 0;
  v17 = IsTenantInterfacePresentInRegistry(
          &v30,
          *(union _NET_LUID_LH *)(v14 + 2),
          *v14,
          (const unsigned __int16 *)v14 + 8,
          (int *)&v23);
  if ( !v17 )
  {
    if ( v23 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v38) = 0;
        LOWORD(v33) = 0;
        FormatRRASErrorString(
          &v38,
          L"InterfaceChangeCallback: Interface (LUID: 0x%I64x, VSID:%d) already present in the registry. Not creating a ne"
           "w entry. Current stack name: %ws",
          p_InterfaceLuid->Value,
          *v14,
          v14 + 4);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v38,
            (unsigned int)&v30,
            0,
            (__int64)&v33);
      }
    }
    else
    {
      v17 = DimCreateInterfaceEntry(&v30, (unsigned __int16 *)v14 + 8);
      if ( v17 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          goto LABEL_60;
        v19 = L"InterfaceChangeCallback: DimCreateInterfaceEntry failed with error %d";
LABEL_40:
        LOWORD(v33) = 0;
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, v19, v17);
LABEL_41:
        if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          goto LABEL_60;
LABEL_18:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v38,
          (unsigned int)&v30,
          0,
          (__int64)&v33);
        goto LABEL_60;
      }
    }
    if ( CDimInterfaceTable::DoesInterfaceExist(v18, &v30, &Row->InterfaceLuid) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_60;
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      FormatRRASErrorString(
        &v38,
        L"InterfaceChangeCallback: Interface (LUID: 0x%I64x, VSID:%d) is already loaded in service.",
        p_InterfaceLuid->Value,
        *v14);
    }
    else
    {
      v20 = CDimInterfaceTable::RegLoadInterfaces(
              g_pCDimInterfaceTable,
              (unsigned __int16 *)v14 + 8,
              &v30,
              1u,
              (struct _DIM_COMPARTMENT_INTERFACE *)v14);
      if ( !v20 || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_60;
      LOWORD(v38) = 0;
      LOWORD(v33) = 0;
      FormatRRASErrorString(
        &v38,
        L"InterfaceChangeCallback: RegLoadInterfaces for %ws failed with error %d",
        v14 + 4,
        v20);
    }
    goto LABEL_41;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    v19 = L"InterfaceChangeCallback: IsTenantInterfacePresentInRegistry failed with error %d";
    goto LABEL_40;
  }
LABEL_60:
  v7 = v22;
LABEL_61:
  if ( v7 )
    ReSetActivityId(&ActivityId);
  if ( v6 )
    HeapFree(hHeap, 0, v6);
  scoped_lock::~scoped_lock((scoped_lock *)v28);
}

```

## disassembly

```asm
0x180015490  mov     [rsp-8+arg_18], rbx
0x180015495  push    rbp
0x180015496  push    rsi
0x180015497  push    rdi
0x180015498  push    r12
0x18001549a  push    r13
0x18001549c  push    r14
0x18001549e  push    r15
0x1800154a0  lea     rbp, [rsp-840h]
0x1800154a8  sub     rsp, 940h
0x1800154af  mov     rax, cs:__security_cookie
0x1800154b6  xor     rax, rsp
0x1800154b9  mov     [rbp+870h+var_40], rax
0x1800154c0  movsxd  rbx, r8d
0x1800154c3  mov     r13, rdx
0x1800154c6  mov     rdi, rcx
0x1800154c9  lea     rax, aParameter; "Parameter"
0x1800154d0  mov     [rsp+970h+var_910], rax
0x1800154d5  lea     rax, aAddition; "Addition"
0x1800154dc  mov     [rsp+970h+var_908], rax
0x1800154e1  lea     rax, aDeletion; "Deletion"
0x1800154e8  mov     [rsp+970h+var_900], rax
0x1800154ed  lea     rax, aInitial; "Initial"
0x1800154f4  mov     [rsp+970h+var_8F8], rax
0x1800154f9  xor     r15d, r15d
0x1800154fc  mov     r14d, r15d
0x1800154ff  mov     [rsp+970h+var_930], r15
0x180015504  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001550b  movdqu  xmmword ptr [rbp+870h+var_8F0.Data1], xmm0
0x180015510  mov     [rsp+970h+var_93C], r15d
0x180015515  mov     qword ptr [rsp+970h+var_920], r15
0x18001551a  mov     [rsp+970h+var_928], r15d
0x18001551f  mov     [rsp+970h+var_938], r15d
0x180015524  xor     edx, edx; Val
0x180015526  lea     r8d, [r15+50h]; Size
0x18001552a  lea     rcx, [rbp+870h+var_890]; void *
0x18001552e  call    memset_0
0x180015533  xorps   xmm0, xmm0
0x180015536  movups  xmmword ptr [rbp+870h+ActivityId.Data1], xmm0
0x18001553a  xorps   xmm1, xmm1
0x18001553d  movups  [rbp+870h+var_8D0], xmm1
0x180015541  mov     [rbp+870h+var_840], r15d
0x180015545  xor     edx, edx; Val
0x180015547  mov     r8d, 7FCh; Size
0x18001554d  lea     rcx, [rbp+870h+var_83C]; void *
0x180015551  call    memset_0
0x180015556  mov     [rbp+870h+var_8C0], r15d
0x18001555a  xorps   xmm0, xmm0
0x18001555d  xor     eax, eax
0x18001555f  movups  [rbp+870h+var_8BC], xmm0
0x180015563  movups  [rbp+870h+var_8AC], xmm0
0x180015567  mov     [rbp+870h+var_89C], eax
0x18001556a  test    r13, r13
0x18001556d  jz      loc_180015AA1
0x180015573  cmp     ebx, 3
0x180015576  jz      loc_180015AA1
0x18001557c  test    ebx, ebx
0x18001557e  jz      loc_180015AA1
0x180015584  lea     rdx, ?gblRoutingDomainOpsLock@@3Vcritical_section@@A; struct IDimSRWLock *
0x18001558b  lea     rcx, [rsp+970h+var_918]; this
0x180015590  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x180015595  nop
0x180015596  lea     rcx, [rbp+870h+ActivityId]; ActivityId
0x18001559a  call    SetRasServerActivityId
0x18001559f  mov     esi, eax
0x1800155a1  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800155a8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x1800155af  jz      short loc_1800155EF
0x1800155b1  mov     word ptr [rbp+870h+var_840], r15w
0x1800155b6  mov     dword ptr [rsp+970h+InterfaceIndex], edi
0x1800155ba  mov     r9, [r13+8]
0x1800155be  mov     r8, [rsp+rbx*8+970h+var_910]
0x1800155c3  lea     rdx, aInterfacechang_6; "InterfaceChangeCallback: Got interface "...
0x1800155ca  lea     rcx, [rbp+870h+var_840]
0x1800155ce  call    FormatRRASErrorString
0x1800155d3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x1800155da  jz      short loc_1800155EF
0x1800155dc  lea     r8, [rbp+870h+var_840]
0x1800155e0  lea     rdx, RasDimTraceInfo
0x1800155e7  mov     rcx, r12
0x1800155ea  call    McTemplateU0z_EventWriteTransfer
0x1800155ef  lea     rdx, [rbp+870h+var_8F0]
0x1800155f3  mov     ecx, edi
0x1800155f5  call    NsiGetRoutingDomainIdForCompartment
0x1800155fa  test    eax, eax
0x1800155fc  jz      short loc_180015648
0x1800155fe  mov     bl, 4
0x180015600  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015606  jz      loc_180015A72
0x18001560c  mov     word ptr [rbp+870h+var_840], r15w
0x180015611  mov     r8d, eax
0x180015614  lea     rdx, aInterfacechang_4; "InterfaceChangeCallback: NsiGetRoutingD"...
0x18001561b  lea     rcx, [rbp+870h+var_840]
0x18001561f  call    FormatRRASErrorString
0x180015624  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001562a  jz      loc_180015A72
0x180015630  lea     r8, [rbp+870h+var_840]
0x180015634  lea     rdx, RasDimTraceError
0x18001563b  mov     rcx, r12
0x18001563e  call    McTemplateU0z_EventWriteTransfer
0x180015643  jmp     loc_180015A72
0x180015648  test    esi, esi
0x18001564a  jz      short loc_180015655
0x18001564c  lea     rcx, [rbp+870h+ActivityId]; ActivityId
0x180015650  call    ReSetActivityId
0x180015655  lea     rdx, [rbp+870h+ActivityId]
0x180015659  lea     rcx, [rbp+870h+var_8F0]; ActivityId
0x18001565d  call    SetActivityId
0x180015662  mov     [rsp+970h+var_940], eax
0x180015666  lea     r8, [rbp+870h+var_890]
0x18001566a  mov     edx, 28h ; '('
0x18001566f  lea     rcx, [rbp+870h+var_8F0]
0x180015673  call    MprConvertGuidToString
0x180015678  lea     rdx, [rsp+970h+var_938]; int *
0x18001567d  lea     rcx, [rbp+870h+var_8F0]; struct _GUID *
0x180015681  call    ?IsRoutingDomainAvailable@@YAKPEAU_GUID@@PEAH@Z; IsRoutingDomainAvailable(_GUID *,int *)
0x180015686  test    eax, eax
0x180015688  jz      loc_18001572D
0x18001568e  mov     bl, 4
0x180015690  cmp     eax, 490h
0x180015695  jnz     short loc_1800156FA
0x180015697  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001569d  jz      loc_180015A6E
0x1800156a3  mov     word ptr [rbp+870h+var_840], r15w
0x1800156a8  mov     word ptr [rbp+870h+var_8C0], r15w
0x1800156ad  mov     r9d, edi
0x1800156b0  lea     r8, [rbp+870h+var_890]
0x1800156b4  lea     rdx, aInterfacechang; "InterfaceChangeCallback: Ignoring notif"...
0x1800156bb  lea     rcx, [rbp+870h+var_840]
0x1800156bf  call    FormatRRASErrorString
0x1800156c4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800156ca  jz      loc_180015A6E
0x1800156d0  lea     rax, [rbp+870h+var_8C0]
0x1800156d4  mov     [rsp+970h+var_948], rax
0x1800156d9  mov     [rsp+970h+InterfaceIndex], r15
0x1800156de  mov     rcx, r12
0x1800156e1  lea     rdx, RasDimParamTraceError
0x1800156e8  lea     r8, [rbp+870h+var_840]
0x1800156ec  lea     r9, [rbp+870h+var_8F0]
0x1800156f0  call    McTemplateU0zjzz_EventWriteTransfer
0x1800156f5  jmp     loc_180015A6E
0x1800156fa  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015700  jz      loc_180015A6E
0x180015706  mov     word ptr [rbp+870h+var_840], r15w
0x18001570b  mov     word ptr [rbp+870h+var_8C0], r15w
0x180015710  mov     dword ptr [rsp+970h+InterfaceIndex], eax
0x180015714  mov     r9d, edi
0x180015717  lea     r8, [rbp+870h+var_890]
0x18001571b  lea     rdx, aRoutingdomainc_2; "RoutingDomainChangeCallback: GetRouting"...
0x180015722  lea     rcx, [rbp+870h+var_840]
0x180015726  call    FormatRRASErrorString
0x18001572b  jmp     short loc_1800156C4
0x18001572d  cmp     [rsp+970h+var_938], r15d
0x180015732  jz      loc_180015A6E
0x180015738  cmp     ebx, 1
0x18001573b  jnz     loc_180015A0C
0x180015741  lea     r8, [rsp+970h+var_930]; struct _DIM_COMPARTMENT_INTERFACE **
0x180015746  lea     rdx, [rsp+970h+var_93C]; unsigned int *
0x18001574b  mov     ecx, edi; CompartmentId
0x18001574d  call    ?DimEnumerateInterfacesFromStack@@YAKIPEAKPEAPEAU_DIM_COMPARTMENT_INTERFACE@@@Z; DimEnumerateInterfacesFromStack(uint,ulong *,_DIM_COMPARTMENT_INTERFACE * *)
0x180015752  test    eax, eax
0x180015754  jz      short loc_1800157B4
0x180015756  mov     bl, 4
0x180015758  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001575e  jz      short loc_1800157AA
0x180015760  mov     word ptr [rbp+870h+var_840], r15w
0x180015765  mov     word ptr [rbp+870h+var_8C0], r15w
0x18001576a  mov     r8d, eax
0x18001576d  lea     rdx, aInterfacechang_0; "InterfaceChangeCallback: DimEnumerateIn"...
0x180015774  lea     rcx, [rbp+870h+var_840]
0x180015778  call    FormatRRASErrorString
0x18001577d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015783  jz      short loc_1800157AA
0x180015785  lea     rax, [rbp+870h+var_8C0]
0x180015789  mov     [rsp+970h+var_948], rax
0x18001578e  mov     [rsp+970h+InterfaceIndex], r15
0x180015793  lea     r9, [rbp+870h+var_8F0]
0x180015797  lea     r8, [rbp+870h+var_840]
0x18001579b  lea     rdx, RasDimParamTraceError
0x1800157a2  mov     rcx, r12
0x1800157a5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800157aa  mov     r14, [rsp+970h+var_930]
0x1800157af  jmp     loc_180015A6E
0x1800157b4  mov     esi, r15d
0x1800157b7  mov     r12d, [rsp+970h+var_93C]
0x1800157bc  test    r12d, r12d
0x1800157bf  jz      short loc_1800157AA
0x1800157c1  mov     bl, 4
0x1800157c3  mov     r14, [rsp+970h+var_930]
0x1800157c8  mov     eax, esi
0x1800157ca  imul    rdi, rax, 218h
0x1800157d1  add     rdi, r14
0x1800157d4  lea     rax, [rsp+970h+var_928]
0x1800157d9  mov     [rsp+970h+InterfaceIndex], rax; InterfaceIndex
0x1800157de  lea     r9, [rsp+970h+var_920]; int
0x1800157e3  mov     r8d, [rdi]; int
0x1800157e6  lea     rdx, [rbp+870h+var_8F0]; int
0x1800157ea  mov     rcx, [rdi+8]; int
0x1800157ee  call    NsiGetInterfaceIndexAndLuidFromIsolationInfo
0x1800157f3  test    eax, eax
0x1800157f5  jz      short loc_180015852
0x1800157f7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800157fd  jz      short loc_180015863
0x1800157ff  mov     word ptr [rbp+870h+var_840], r15w
0x180015804  mov     word ptr [rbp+870h+var_8C0], r15w
0x180015809  mov     r9d, eax
0x18001580c  mov     r8d, [rdi]
0x18001580f  lea     rdx, aInterfacechang_8; "InterfaceChangeCallback: NsiGetInterfac"...
0x180015816  lea     rcx, [rbp+870h+var_840]
0x18001581a  call    FormatRRASErrorString
0x18001581f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015825  jz      short loc_180015863
0x180015827  lea     rax, [rbp+870h+var_8C0]
0x18001582b  mov     [rsp+970h+var_948], rax
0x180015830  mov     [rsp+970h+InterfaceIndex], r15
0x180015835  lea     r9, [rbp+870h+var_8F0]
0x180015839  lea     r8, [rbp+870h+var_840]
0x18001583d  lea     rdx, RasDimParamTraceError
0x180015844  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001584b  call    McTemplateU0zjzz_EventWriteTransfer
0x180015850  jmp     short loc_180015863
0x180015852  lea     r15, [r13+8]
0x180015856  mov     rax, [r15]
0x180015859  cmp     qword ptr [rsp+970h+var_920], rax
0x18001585e  jz      short loc_180015873
0x180015860  xor     r15d, r15d
0x180015863  inc     esi
0x180015865  cmp     esi, r12d
0x180015868  jb      loc_1800157C8
0x18001586e  jmp     loc_180015A6E
0x180015873  mov     [rsp+970h+var_93C], 0
0x18001587b  lea     rsi, [rdi+10h]
0x18001587f  lea     rax, [rsp+970h+var_93C]
0x180015884  mov     [rsp+970h+InterfaceIndex], rax; int *
0x180015889  mov     r9, rsi; unsigned __int16 *
0x18001588c  mov     r8d, [rdi]; unsigned int
0x18001588f  mov     rdx, [rdi+8]; union _NET_LUID_LH
0x180015893  lea     rcx, [rbp+870h+var_8F0]; struct _GUID *
0x180015897  call    ?IsTenantInterfacePresentInRegistry@@YAKPEAU_GUID@@T_NET_LUID_LH@@KPEBGPEAH@Z; IsTenantInterfacePresentInRegistry(_GUID *,_NET_LUID_LH,ulong,ushort const *,int *)
0x18001589c  test    eax, eax
0x18001589e  jz      short loc_1800158F3
0x1800158a0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800158a6  jz      loc_180015A6E
0x1800158ac  lea     rdx, aInterfacechang_9; "InterfaceChangeCallback: IsTenantInterf"...
0x1800158b3  xor     ecx, ecx
0x1800158b5  mov     r8d, eax
0x1800158b8  mov     word ptr [rbp+870h+var_8C0], cx
0x1800158bc  mov     word ptr [rbp+870h+var_840], cx
0x1800158c0  lea     rcx, [rbp+870h+var_840]
0x1800158c4  call    FormatRRASErrorString
0x1800158c9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800158cf  jz      loc_180015A6E
0x1800158d5  lea     rax, [rbp+870h+var_8C0]
0x1800158d9  mov     [rsp+970h+var_948], rax
0x1800158de  mov     [rsp+970h+InterfaceIndex], 0
0x1800158e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800158ee  jmp     loc_1800156E1
0x1800158f3  cmp     [rsp+970h+var_93C], 0
0x1800158f8  jnz     short loc_180015922
0x1800158fa  mov     r9, rdi
0x1800158fd  mov     rdx, rsi; unsigned __int16 *
0x180015900  lea     rcx, [rbp+870h+var_8F0]; struct _GUID *
0x180015904  call    DimCreateInterfaceEntry
0x180015909  test    eax, eax
0x18001590b  jz      short loc_180015984
0x18001590d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015913  jz      loc_180015A6E
0x180015919  lea     rdx, aInterfacechang_2; "InterfaceChangeCallback: DimCreateInter"...
0x180015920  jmp     short loc_1800158B3
0x180015922  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015928  jz      short loc_180015984
0x18001592a  xor     eax, eax
0x18001592c  mov     word ptr [rbp+870h+var_840], ax
0x180015930  mov     word ptr [rbp+870h+var_8C0], ax
0x180015934  mov     [rsp+970h+InterfaceIndex], rsi
0x180015939  mov     r9d, [rdi]
0x18001593c  mov     r8, [r15]
0x18001593f  lea     rdx, aInterfacechang_7; "InterfaceChangeCallback: Interface (LUI"...
0x180015946  lea     rcx, [rbp+870h+var_840]
0x18001594a  call    FormatRRASErrorString
0x18001594f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180015955  jz      short loc_180015984
0x180015957  lea     rax, [rbp+870h+var_8C0]
0x18001595b  mov     [rsp+970h+var_948], rax
0x180015960  mov     [rsp+970h+InterfaceIndex], 0
0x180015969  lea     r9, [rbp+870h+var_8F0]
0x18001596d  lea     r8, [rbp+870h+var_840]
0x180015971  lea     rdx, RasDimParamTraceError
0x180015978  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001597f  call    McTemplateU0zjzz_EventWriteTransfer
0x180015984  mov     r8, r15; union _NET_LUID_LH *
0x180015987  lea     rdx, [rbp+870h+var_8F0]; struct _GUID *
0x18001598b  call    ?DoesInterfaceExist@CDimInterfaceTable@@QEAA_NAEBU_GUID@@AEBT_NET_LUID_LH@@@Z; CDimInterfaceTable::DoesInterfaceExist(_GUID const &,_NET_LUID_LH const &)
0x180015990  test    al, al
0x180015992  jnz     short loc_1800159EB
0x180015994  mov     [rsp+970h+InterfaceIndex], rdi; struct _DIM_COMPARTMENT_INTERFACE *
0x180015999  mov     r9d, 1; unsigned int
0x18001599f  lea     r8, [rbp+870h+var_8F0]; struct _GUID *
0x1800159a3  mov     rdx, rsi; unsigned __int16 *
0x1800159a6  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
  ... truncated ...
```
