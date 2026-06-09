# DdmDevice::LinkUp(int,_PROTOCOL_SRV_NEW_BUNDLE *)

- ea: `0x1800342d0`
- end: `0x1800355b3`
- name: `?LinkUp@DdmDevice@@UEAAXHPEAU_PROTOCOL_SRV_NEW_BUNDLE@@@Z`
- size: `4835`
- prototype: `void __fastcall(DdmDevice *__hidden this, int, struct _PROTOCOL_SRV_NEW_BUNDLE *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180001338`
- `0x180002bbe`
- `0x180002f58`
- `0x180007c50`
- `0x18000bf44`
- `0x18000c0fc`
- `0x18001b210`
- `0x18002cb30`
- `0x18002cce0`
- `0x18002d844`
- `0x18002e0ec`
- `0x18002e268`
- `0x1800342d0`
- `0x180038bb4`
- `0x180039480`
- `0x180071cec`
- `0x18007a960`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800343c2`
- `msvcrt!_itow_s` at `0x18003444d`
- `msvcrt!_itow_s` at `0x1800344e1`
- `msvcrt!_itow_s` at `0x1800347b7`
- `msvcrt!_itow_s` at `0x180034866`
- `msvcrt!_itow_s` at `0x180034989`
- `msvcrt!_itow_s` at `0x180034b1c`
- `msvcrt!_itow_s` at `0x180034e9b`
- `msvcrt!_itow_s` at `0x180034f14`
- `msvcrt!_itow_s` at `0x180034fee`
- `msvcrt!_itow_s` at `0x180035105`
- `msvcrt!_itow_s` at `0x180035358`
- `msvcrt!_itow_s` at `0x1800343c2`
- `msvcrt!_itow_s` at `0x18003444d`
- `msvcrt!_itow_s` at `0x1800344e1`
- `msvcrt!_itow_s` at `0x1800347b7`
- `msvcrt!_itow_s` at `0x180034866`
- `msvcrt!_itow_s` at `0x180034989`
- `msvcrt!_itow_s` at `0x180034b1c`
- `msvcrt!_itow_s` at `0x180034e9b`
- `msvcrt!_itow_s` at `0x180034f14`
- `msvcrt!_itow_s` at `0x180034fee`
- `msvcrt!_itow_s` at `0x180035105`
- `msvcrt!_itow_s` at `0x180035358`
- `rtutils!RouterLogEventW` at `0x180034e6e`
- `rtutils!RouterLogEventW` at `0x1800354ec`
- `rtutils!RouterLogEventW` at `0x180034e6e`
- `rtutils!RouterLogEventW` at `0x1800354ec`
- `rtutils!RouterLogEventStringW` at `0x180034a6a`
- `rtutils!RouterLogEventStringW` at `0x180034a6a`

## string_xrefs

- `0x1800343cc`: `DdmDevice::LinkUp`
- `0x1800347c3`: `ValidateIncomingVpnClientConnection failed for user %ws: %d`
- `0x180034f1d`: `CreateInsertClientInterfaceForDdm failed: %d`
- `0x18003537c`: `The interface %ws is already connected/connecting port=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DdmDevice::LinkUp(DdmDevice *this, int a2, struct _PROTOCOL_SRV_NEW_BUNDLE *a3)
{
  DdmConnection *v5; // r12
  int v6; // eax
  __int64 v7; // rdi
  int v8; // r13d
  char v9; // cl
  int v10; // ecx
  DWORD dwErrorCode; // r14d
  int v12; // ecx
  __int64 v13; // rcx
  __int16 *v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // rax
  __int16 v17; // r9
  _WORD *v18; // rcx
  __int64 v19; // rcx
  __int16 *v20; // r8
  __int64 v21; // rdx
  _WORD *v22; // rax
  __int16 v23; // r9
  _WORD *v24; // rcx
  __int64 v25; // r13
  __int16 *v26; // rax
  __int64 v27; // r8
  _WORD *v28; // rdx
  __int16 v29; // cx
  _WORD *v30; // rcx
  int v31; // ecx
  BYTE *v32; // r8
  int v33; // ecx
  int v34; // ecx
  __int64 v35; // rdx
  struct DdmConnectionTable *Instance; // rax
  DdmConnection *v37; // rax
  DdmConnection *v38; // rax
  char v39; // dl
  int v40; // ecx
  int v41; // ecx
  char *v42; // r11
  __int64 v43; // r10
  __int64 v44; // rcx
  __int16 *v45; // r8
  __int64 v46; // rdx
  _WORD *v47; // rax
  __int16 v48; // r9
  _WORD *v49; // rcx
  __int64 v50; // r13
  __int16 *v51; // rax
  __int64 v52; // r9
  __int64 v53; // r8
  _WORD *v54; // rdx
  __int16 v55; // cx
  _WORD *v56; // rcx
  __int64 v57; // rcx
  __int16 *v58; // rdx
  _WORD *v59; // rax
  __int16 v60; // r8
  _WORD *v61; // rcx
  unsigned __int16 *v62; // rcx
  _WORD *v63; // rax
  _WORD *v64; // rcx
  struct IDimInterface *v65; // rcx
  int v66; // r13d
  int v67; // ecx
  int v68; // ecx
  int v69; // ebx
  int v70; // edi
  int v71; // ecx
  __int64 v72; // rax
  __int64 v73; // rbx
  __int128 *v74; // rax
  int v75; // ecx
  int v76; // edi
  unsigned int v77; // ebx
  __int64 v78; // rax
  __int64 v79; // rbx
  __int128 *v80; // rax
  __int64 v81; // rbx
  int v82; // eax
  DdmConnectionTable *v83; // rax
  int v84; // ecx
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rbx
  __int128 *v88; // rax
  DWORD v89; // ebx
  void (*v90)(void); // rax
  LPWSTR *plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  struct IDimInterface *v92; // [rsp+50h] [rbp-B0h] BYREF
  int v93; // [rsp+58h] [rbp-A8h]
  int v94; // [rsp+5Ch] [rbp-A4h]
  int v95; // [rsp+60h] [rbp-A0h]
  int v96; // [rsp+64h] [rbp-9Ch]
  unsigned int v97; // [rsp+68h] [rbp-98h] BYREF
  int v98; // [rsp+6Ch] [rbp-94h]
  DdmConnection *v99[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v100; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v102; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v103[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v104[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v105[16]; // [rsp+D0h] [rbp-30h] BYREF
  LPWSTR v106[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v107; // [rsp+F0h] [rbp-10h]
  wchar_t Buffer[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v109; // [rsp+104h] [rbp+4h]
  __int128 v110; // [rsp+114h] [rbp+14h]
  int v111; // [rsp+124h] [rbp+24h]
  int v112; // [rsp+130h] [rbp+30h] BYREF
  char v113[2044]; // [rsp+134h] [rbp+34h] BYREF

  v96 = a2;
  *(_OWORD *)v106 = 0;
  v107 = 0;
  v103[0] = 0;
  v92 = 0;
  v5 = 0;
  v99[0] = 0;
  v97 = 0;
  v6 = (unsigned __int16)*((_DWORD *)this + 34);
  v7 = 16;
  if ( v6 == 15 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    if ( v6 == 16 )
      v8 = 2;
  }
  v98 = v8;
  v102 = GUID_NULL;
  v99[1] = this;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v112 = 0;
  memset_0(v113, 0, sizeof(v113));
  *(_DWORD *)Buffer = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v100 = 0;
  v9 = byte_1800C8404;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v112) = 0;
    Buffer[0] = 0;
    v10 = *((_DWORD *)this + 24);
    if ( v10 != -1 )
      _itow_s(v10, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v112, L"%s (hport: %ld)", L"DdmDevice::LinkUp", *((_QWORD *)this + 12));
    v9 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v112,
        (unsigned int)&v100,
        0,
        (__int64)Buffer);
      v9 = byte_1800C8404;
    }
  }
  if ( (unsigned int)(*((_DWORD *)this + 26) - 4) > 1 )
  {
    if ( (v9 & 0x10) != 0 )
    {
      Buffer[0] = 0;
      if ( *((_DWORD *)this + 24) != -1 )
      {
        _itow_s(*((_DWORD *)this + 24), Buffer, 0x14u, 10);
        v9 = byte_1800C8404;
      }
      if ( (v9 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"Auth not started",
          (unsigned int)&v100,
          0,
          (__int64)Buffer);
    }
LABEL_23:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(DdmDevice *, __int64))this)(this, 1);
    return;
  }
  dwErrorCode = (*(__int64 (__fastcall **)(DdmDevice *, char *))(*(_QWORD *)this + 632LL))(this, (char *)this + 120);
  if ( dwErrorCode )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v112) = 0;
      Buffer[0] = 0;
      v12 = *((_DWORD *)this + 24);
      if ( v12 != -1 )
        _itow_s(v12, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v112, L"GetBundleHandle failed: %d", dwErrorCode);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v112,
          (unsigned int)&v100,
          0,
          (__int64)Buffer);
    }
    (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
    goto LABEL_23;
  }
  v94 = 0;
  v95 = 0;
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v93 = 1;
  if ( v8 == 1 )
  {
    if ( !*((_QWORD *)a3 + 10) && !*((_QWORD *)a3 + 12) )
    {
      v13 = 2147483646;
      v14 = (__int16 *)((char *)a3 + 112);
      v15 = 257;
      v16 = (_WORD *)((char *)this + 168);
      do
      {
        if ( !v13 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v13;
        --v15;
      }
      while ( v15 );
      v18 = v16 - 1;
      if ( v15 )
        v18 = v16;
      *v18 = 0;
      v19 = 2147483646;
      v20 = (__int16 *)((char *)a3 + 626);
      v21 = 16;
      v22 = (_WORD *)((char *)this + 682);
      do
      {
        if ( !v19 )
          break;
        v23 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v22++ = v23;
        --v19;
        --v21;
      }
      while ( v21 );
      v24 = v22 - 1;
      if ( v21 )
        v24 = v22;
      *v24 = 0;
    }
    dwErrorCode = DdmDevice::ValidateIncomingConnection(
                    this,
                    *((struct _ROUTER_IP_ADDRESS **)a3 + 9),
                    *((struct _ROUTER_IP_ADDRESS **)a3 + 10),
                    (unsigned __int16 *)a3 + 56,
                    (struct _PROTOCOL_SRV_NEW_BUNDLE *)((char *)a3 + 88),
                    &v92);
    if ( dwErrorCode )
      goto LABEL_82;
    if ( v92 )
    {
      (**(void (__fastcall ***)(struct IDimInterface *))v92)(v92);
      v94 = 1;
      if ( *((_QWORD *)a3 + 12) )
      {
        v25 = 2147483646;
        v26 = (__int16 *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
        v27 = 257;
        v28 = (_WORD *)((char *)this + 168);
        do
        {
          if ( !v25 )
            break;
          v29 = *v26;
          if ( !*v26 )
            break;
          ++v26;
          *v28++ = v29;
          --v25;
          --v27;
        }
        while ( v27 );
        v30 = v28 - 1;
        if ( v27 )
          v30 = v28;
        *v30 = 0;
      }
      (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 640LL))(this, 1);
      v102 = *(struct _GUID *)(*(__int64 (__fastcall **)(struct IDimInterface *, struct _GUID *))(*(_QWORD *)v92 + 360LL))(
                                v92,
                                &Buf1);
    }
    else
    {
      v32 = (BYTE *)*((_QWORD *)a3 + 12);
      if ( !v32 )
        goto LABEL_54;
      dwErrorCode = GetRemoteUserNameFromCertificate(
                      *((_DWORD *)a3 + 26),
                      *((_DWORD *)a3 + 22),
                      v32,
                      (unsigned __int16 *)this + 84);
      if ( dwErrorCode )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v112) = 0;
          Buffer[0] = 0;
          v33 = *((_DWORD *)this + 24);
          if ( v33 != -1 )
            _itow_s(v33, Buffer, 0x14u, 10);
          FormatRRASErrorString(&v112, L"GetRemoteUserNameFromCertificate failed: %d", dwErrorCode);
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v112,
              (unsigned int)&v100,
              0,
              (__int64)Buffer);
        }
        (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
        goto LABEL_207;
      }
    }
  }
  else if ( !v8 )
  {
    dwErrorCode = DdmDevice::ValidateIncomingConnection(this, 0, 0, (unsigned __int16 *)this + 84, 0, &v92);
    if ( dwErrorCode )
    {
LABEL_82:
      v106[0] = (LPWSTR)((char *)this + 1092);
      v106[1] = (LPWSTR)((char *)this + 168);
      *(_QWORD *)&v107 = (char *)this + 714;
      if ( (unsigned int)dword_1800C84E4 > 1 )
        RouterLogEventStringW(hLogHandle, 2u, 0x4F2Eu, 3u, v106, dwErrorCode, 3u);
      v35 = dwErrorCode;
      goto LABEL_85;
    }
    if ( !v92 )
      goto LABEL_54;
    (**(void (__fastcall ***)(struct IDimInterface *))v92)(v92);
    v94 = 1;
    (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 640LL))(this, 1);
  }
  if ( v92 )
  {
    MprInfoDelete(*((LPVOID *)a3 + 1));
    *((_QWORD *)a3 + 1) = 0;
    MprInfoDelete(*((LPVOID *)a3 + 2));
    *((_QWORD *)a3 + 2) = 0;
    MprInfoDelete(*((LPVOID *)a3 + 3));
    MprInfoDelete(*((LPVOID *)a3 + 4));
    *((_QWORD *)a3 + 3) = 0;
    *((_DWORD *)a3 + 10) = 0;
    goto LABEL_81;
  }
LABEL_54:
  dwErrorCode = DDMRoutingDomainLookupForIncomingConnection(
                  (unsigned __int16 *)this + 341,
                  (unsigned __int16 *)this + 84,
                  (unsigned __int16 *)a3 + 329,
                  &v102);
  if ( dwErrorCode )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v112) = 0;
      Buffer[0] = 0;
      v34 = *((_DWORD *)this + 24);
      if ( v34 != -1 )
        _itow_s(v34, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v112, L"Routing domain lookup failed for user %ws: %d", (char *)this + 168, dwErrorCode);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v112,
          (unsigned int)&v100,
          0,
          (__int64)Buffer);
    }
    goto LABEL_82;
  }
  dwErrorCode = ValidateIncomingVpnClientConnection(&v102);
  if ( dwErrorCode && (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v112) = 0;
    Buffer[0] = 0;
    v31 = *((_DWORD *)this + 24);
    if ( v31 != -1 )
      _itow_s(v31, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v112,
      L"ValidateIncomingVpnClientConnection failed for user %ws: %d",
      (char *)this + 168,
      dwErrorCode);
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v112,
        (unsigned int)&v100,
        0,
        (__int64)Buffer);
  }
  if ( dword_1800C8654 )
    *((_DWORD *)this + 33) |= 0x80u;
LABEL_81:
  if ( dwErrorCode )
    goto LABEL_82;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), v99);
  v5 = v99[0];
  if ( v99[0] )
  {
LABEL_198:
    if ( v96 )
      DdmDevice::SendInterfaceInfoToProtocolEngine(this);
    v89 = DdmConnection::AddLink(v5);
    if ( v89 )
    {
      (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, 8);
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, v89);
    }
    goto LABEL_203;
  }
  Buf1 = 0;
  v37 = (DdmConnection *)operator new(0x5E0u);
  v104[0] = v37;
  if ( v37 )
    v38 = DdmConnection::DdmConnection(v37, (void *)0xFFFFFFFFFFFFFFFFLL, *((void **)this + 15));
  else
    v38 = 0;
  RasObjPtr<DdmDevice>::reset(v99, v38);
  v5 = v99[0];
  if ( !v99[0] )
  {
    v39 = byte_1800C8404;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      Buffer[0] = 0;
      v40 = *((_DWORD *)this + 24);
      if ( v40 != -1 )
      {
        _itow_s(v40, Buffer, (unsigned int)(LODWORD(v99[0]) + 20), LODWORD(v99[0]) + 10);
        v39 = byte_1800C8404;
      }
      if ( (v39 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)L"ConnObj Allocation failed",
          (unsigned int)&v100,
          0,
          (__int64)Buffer);
    }
    v35 = 8;
    goto LABEL_85;
  }
  v41 = 1;
  if ( (unsigned __int16)*((_DWORD *)this + 34) == 15 )
    v41 = 128;
  *((_DWORD *)v99[0] + 20) = v41;
  *((_QWORD *)v5 + 8) = *((_QWORD *)this + 12);
  *(struct _GUID *)((char *)v5 + 1484) = v102;
  *((_QWORD *)v5 + 14) = *((_QWORD *)a3 + 2);
  *((_QWORD *)v5 + 16) = *((_QWORD *)a3 + 3);
  *((_QWORD *)v5 + 17) = *((_QWORD *)a3 + 4);
  *((_DWORD *)v5 + 366) = *((_DWORD *)a3 + 11);
  if ( memcmp_0(&Buf1, (char *)this + 1076, 0x10u) )
    *(_OWORD *)((char *)v5 + 148) = *(_OWORD *)((char *)this + 1076);
  v42 = (char *)v5 + 164;
  v43 = 2147483646;
  v44 = 2147483646;
  v45 = (__int16 *)((char *)this + 168);
  v46 = 257;
  v47 = (_WORD *)((char *)v5 + 164);
  do
  {
    if ( !v44 )
      break;
    v48 = *v45;
    if ( !*v45 )
      break;
    ++v45;
    *v47++ = v48;
    --v44;
    --v46;
  }
  while ( v46 );
  v49 = v47 - 1;
  if ( v46 )
    v49 = v47;
  *v49 = 0;
  if ( *((_WORD *)v5 + 82) || v98 != 1 )
  {
    v52 = 257;
    goto LABEL_119;
  }
  if ( v92 )
  {
    v50 = 2147483646;
    v51 = (__int16 *)(*(__int64 (__fastcall **)(struct IDimInterface *, __int64, _QWORD))(*(_QWORD *)v92 + 280LL))(
                       v92,
                       v46,
                       0);
    v52 = 257;
    v53 = 257;
    v54 = (_WORD *)((char *)v5 + 164);
    do
    {
      if ( !v50 )
        break;
      v55 = *v51;
      if ( !*v51 )
        break;
      ++v51;
      *v54++ = v55;
      --v50;
      --v53;
    }
    while ( v53 );
    v56 = v54 - 1;
    if ( v53 )
      v56 = v54;
    *v56 = 0;
    v43 = 2147483646;
    v42 = (char *)v5 + 164;
LABEL_119:
    v57 = 2147483646;
    v58 = (__int16 *)((char *)this + 168);
    v59 = (_WORD *)((char *)v5 + 678);
    do
    {
      if ( !v57 )
        break;
      v60 = *v58;
      if ( *v58 == LOWORD(v103[0]) )
        break;
      ++v58;
      *v59++ = v60;
      --v57;
      --v52;
    }
    while ( v52 );
    v61 = v59 - 1;
    if ( v52 )
      v61 = v59;
    *v61 = 0;
    v62 = (unsigned __int16 *)((char *)this + 682);
    v63 = (_WORD *)((char *)v5 + 1192);
    do
    {
      if ( !v43 )
        break;
      v58 = (__int16 *)*v62;
      if ( !(_WORD)v58 )
        break;
      ++v62;
      *v63++ = (_WORD)v58;
      --v43;
      --v7;
    }
    while ( v7 );
    v64 = v63 - 1;
    if ( v7 )
      v64 = v63;
    *v64 = 0;
    v65 = v92;
    if ( v92
      || (v65 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                           + 48LL))(
                                          g_pIDimInterfaceTable,
                                          v42,
                                          0),
          (v92 = v65) != 0) )
    {
      v66 = v94;
      if ( !v94 )
      {
        (**(void (__fastcall ***)(struct IDimInterface *, __int16 *))v65)(v65, v58);
        v66 = 1;
        v94 = 1;
        v65 = v92;
      }
      if ( ((*(__int64 (__fastcall **)(struct IDimInterface *, __int16 *))(*(_QWORD *)v65 + 104LL))(v65, v58) & 4) == 0 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v112) = 0;
          Buffer[0] = 0;
          v71 = *((_DWORD *)this + 24);
          if ( v71 != -1 )
            _itow_s(v71, Buffer, 0x14u, 10);
          v72 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
          FormatRRASErrorString(&v112, L"The interface %ws is disabled. Rejecting the connection.", v72);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v73 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
            if ( (*(__int64 (__fastcall **)(struct IDimInterface *, struct _GUID *))(*(_QWORD *)v92 + 360LL))(
                   v92,
                   &Buf1) )
            {
              LODWORD(v74) = (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(
                               v92,
                               v104);
            }
            else if ( (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(v92, v103) )
            {
              LODWORD(v74) = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v92 + 360LL))(
                               v92,
                               v105);
            }
            else
            {
              v74 = &v100;
            }
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v112,
              (_DWORD)v74,
              v73,
              (__int64)Buffer);
          }
        }
        dwErrorCode = 916;
        goto LABEL_195;
      }
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v112) = 0;
        Buffer[0] = 0;
        v75 = *((_DWORD *)this + 24);
        if ( v75 != -1 )
          _itow_s(v75, Buffer, 0x14u, 10);
        v76 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 104LL))(v92);
        v77 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 40LL))(v92);
        v78 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
        LODWORD(plpszSubStringArray) = v76;
        FormatRRASErrorString(&v112, L"Interface name=%ws, State=%d, fFlags=0x%.8x", v78, v77, plpszSubStringArray);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v79 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
          if ( (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v92 + 360LL))(v92, v105) )
          {
            LODWORD(v80) = (*(__int64 (__fastcall **)(struct IDimInterface *, struct _GUID *))(*(_QWORD *)v92 + 360LL))(
                             v92,
                             &Buf1);
          }
          else if ( (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(v92, v104) )
          {
            LODWORD(v80) = (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(
                             v92,
                             v103);
          }
          else
          {
            v80 = &v100;
          }
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v112,
            (_DWORD)v80,
            v79,
            (__int64)Buffer);
        }
      }
      if ( (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 40LL))(v92) == 2
        || (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 40LL))(v92) == 1
        && ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 104LL))(v92) & 0x800) == 0 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v112) = 0;
          Buffer[0] = 0;
          v84 = *((_DWORD *)this + 24);
          if ( v84 != -1 )
            _itow_s(v84, Buffer, 0x14u, 10);
          v85 = *((_QWORD *)this + 12);
          v86 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
          FormatRRASErrorString(&v112, L"The interface %ws is already connected/connecting port=%d", v86, v85);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v87 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 280LL))(v92);
            if ( (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v92 + 360LL))(v92, v105) )
            {
              LODWORD(v88) = (*(__int64 (__fastcall **)(struct IDimInterface *, struct _GUID *))(*(_QWORD *)v92 + 360LL))(
                               v92,
                               &Buf1);
            }
            else if ( (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(v92, v104) )
            {
              LODWORD(v88) = (*(__int64 (__fastcall **)(struct IDimInterface *, _QWORD *))(*(_QWORD *)v92 + 360LL))(
                               v92,
                               v103);
            }
            else
            {
              v88 = &v100;
            }
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v112,
              (_DWORD)v88,
              v87,
              (__int64)Buffer);
          }
        }
        dwErrorCode = 901;
        (*(void (__fastcall **)(struct IDimInterface *, __int64))(*(_QWORD *)v92 + 32LL))(v92, 901);
        goto LABEL_195;
      }
      v70 = v95;
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
      Buf1 = v102;
      LOBYTE(plpszSubStringArray) = 1;
      dwErrorCode = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, struct _GUID *, _QWORD, unsigned int *, struct IDimInterface **))(*(_QWORD *)g_pIDimInterfaceTable + 40LL))(
                      g_pIDimInterfaceTable,
                      (__int64)v5 + 678,
                      1,
                      *((_QWORD *)v5 + 7),
                      (_DWORD)plpszSubStringArray,
                      &Buf1,
                      *((_QWORD *)a3 + 1),
                      &v97,
                      &v92);
      v66 = 1;
      if ( v97 == 1 )
      {
        v106[0] = (LPWSTR)((char *)this + 1092);
        v106[1] = (LPWSTR)((char *)this + 168);
        *(_QWORD *)&v107 = (char *)this + 714;
        if ( dword_1800C84E4 )
          RouterLogEventW(hLogHandle, 1u, 0x4EE1u, 3u, v106, 0);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v112) = 0;
          Buffer[0] = 0;
          v67 = *((_DWORD *)this + 24);
          if ( v67 != -1 )
            _itow_s(v67, Buffer, 0x14u, 10);
          FormatRRASErrorString(&v112, L"Failed to add the filter with error %d", v97);
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v112,
              (unsigned int)&v100,
              0,
              (__int64)Buffer);
        }
      }
      if ( dwErrorCode )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v112) = 0;
          Buffer[0] = 0;
          v68 = *((_DWORD *)this + 24);
          if ( v68 != -1 )
            _itow_s(v68, Buffer, 0x14u, 10);
          FormatRRASErrorString(&v112, L"CreateInsertClientInterfaceForDdm failed: %d", dwErrorCode);
          if ( (byte_1800C8404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v112,
              (unsigned int)&v100,
              0,
              (__int64)Buffer);
        }
        v69 = 0;
        goto LABEL_182;
      }
      v70 = 1;
      if ( *((_DWORD *)a3 + 10) )
        *((_DWORD *)v5 + 20) |= 0x40u;
      (**(void (__fastcall ***)(struct IDimInterface *))v92)(v92);
    }
    v94 = v66;
    (*(void (__fastcall **)(struct IDimInterface *, __int64))(*(_QWORD *)v92 + 48LL))(v92, 1);
    v81 = *(_QWORD *)v92;
    v82 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 104LL))(v92);
    (*(void (__fastcall **)(struct IDimInterface *, _QWORD))(v81 + 112))(v92, v82 & 0xFFFFFFFE);
    *((_QWORD *)v5 + 9) = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 16LL))(v92);
    *((_DWORD *)v5 + 36) = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 72LL))(v92);
    v83 = DdmConnectionTable::GetInstance();
    DdmConnectionTable::AddConnection(v83);
    v69 = v93;
    if ( !v93 )
    {
      v94 = v66;
      if ( v70 )
      {
LABEL_182:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
        v95 = 0;
        goto LABEL_196;
      }
      v95 = 0;
LABEL_196:
      if ( dwErrorCode )
      {
        (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
        goto LABEL_204;
      }
      goto LABEL_198;
    }
    v95 = v70;
LABEL_195:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
    v69 = 0;
    v93 = 0;
    goto LABEL_196;
  }
  v35 = 0;
LABEL_85:
  (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, v35);
LABEL_203:
  v69 = v93;
LABEL_204:
  if ( v94 )
    (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v92 + 8LL))(v92);
  if ( v69 )
  {
LABEL_207:
    v90 = *(void (**)(void))(*(_QWORD *)g_pIDimInterfaceTable + 16LL);
LABEL_210:
    v90();
    goto LABEL_211;
  }
  if ( v95 )
  {
    v90 = *(void (**)(void))(*(_QWORD *)g_pIDimInterfaceTable + 24LL);
    goto LABEL_210;
  }
LABEL_211:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmDevice *, __int64))this)(this, 1);
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmConnection *, __int64))v5)(v5, 1);
}

```

## disassembly

```asm
0x1800342d0  mov     [rsp-8+arg_8], rbx
0x1800342d5  push    rbp
0x1800342d6  push    rsi
0x1800342d7  push    rdi
0x1800342d8  push    r12
0x1800342da  push    r13
0x1800342dc  push    r14
0x1800342de  push    r15
0x1800342e0  lea     rbp, [rsp-840h]
0x1800342e8  sub     rsp, 940h
0x1800342ef  mov     rax, cs:__security_cookie
0x1800342f6  xor     rax, rsp
0x1800342f9  mov     [rbp+870h+var_40], rax
0x180034300  mov     rbx, r8
0x180034303  mov     [rsp+970h+var_90C], edx
0x180034307  mov     rsi, rcx
0x18003430a  xorps   xmm0, xmm0
0x18003430d  movups  xmmword ptr [rbp+870h+var_890], xmm0
0x180034311  movups  [rbp+870h+var_880], xmm0
0x180034315  xor     r15d, r15d
0x180034318  mov     [rbp+870h+var_8C0], r15
0x18003431c  mov     [rsp+970h+var_920], r15
0x180034321  mov     r12d, r15d
0x180034324  mov     [rsp+970h+var_900], r15
0x180034329  mov     [rsp+970h+var_908], r15d
0x18003432e  mov     eax, [rcx+88h]
0x180034334  movzx   eax, ax
0x180034337  lea     ecx, [r15+2]
0x18003433b  lea     edi, [rcx+0Eh]
0x18003433e  cmp     eax, 0Fh
0x180034341  jnz     short loc_180034349
0x180034343  lea     r13d, [r15+1]
0x180034347  jmp     short loc_180034352
0x180034349  mov     r13d, r15d
0x18003434c  cmp     eax, edi
0x18003434e  cmovz   r13d, ecx
0x180034352  mov     [rsp+970h+var_904], r13d
0x180034357  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003435e  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x180034363  mov     [rsp+970h+var_8F8], rsi
0x180034368  lock inc dword ptr [rsi+8]
0x18003436c  mov     [rbp+870h+var_840], r15d
0x180034370  xor     edx, edx; Val
0x180034372  mov     r8d, 7FCh; Size
0x180034378  lea     rcx, [rbp+870h+var_83C]; void *
0x18003437c  call    memset_0
0x180034381  mov     dword ptr [rbp+870h+Buffer], r15d
0x180034385  xorps   xmm0, xmm0
0x180034388  xor     eax, eax
0x18003438a  movups  [rbp+870h+var_86C], xmm0
0x18003438e  movups  [rbp+870h+var_85C], xmm0
0x180034392  mov     [rbp+870h+var_84C], eax
0x180034395  movups  [rbp+870h+var_8F0], xmm0
0x180034399  mov     cl, cs:byte_1800C8404
0x18003439f  test    dil, cl
0x1800343a2  jz      short loc_18003441D
0x1800343a4  mov     word ptr [rbp+870h+var_840], r15w
0x1800343a9  mov     [rbp+870h+Buffer], r15w
0x1800343ae  mov     ecx, [rsi+60h]; Value
0x1800343b1  cmp     ecx, 0FFFFFFFFh
0x1800343b4  jz      short loc_1800343C8
0x1800343b6  lea     r9d, [rax+0Ah]; Radix
0x1800343ba  lea     r8d, [rax+14h]; BufferCount
0x1800343be  lea     rdx, [rbp+870h+Buffer]; Buffer
0x1800343c2  call    cs:__imp__itow_s
0x1800343c8  mov     r9, [rsi+60h]
0x1800343cc  lea     r8, aDdmdeviceLinku; "DdmDevice::LinkUp"
0x1800343d3  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x1800343da  lea     rcx, [rbp+870h+var_840]
0x1800343de  call    FormatRRASErrorString
0x1800343e3  mov     cl, cs:byte_1800C8404
0x1800343e9  test    dil, cl
0x1800343ec  jz      short loc_18003441D
0x1800343ee  lea     rax, [rbp+870h+Buffer]
0x1800343f2  mov     qword ptr [rsp+970h+dwErrorCode], rax
0x1800343f7  mov     [rsp+970h+plpszSubStringArray], r15
0x1800343fc  lea     r9, [rbp+870h+var_8F0]
0x180034400  lea     r8, [rbp+870h+var_840]
0x180034404  lea     rdx, RasDdmParamTraceInfo
0x18003440b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034412  call    McTemplateU0zjzz_EventWriteTransfer
0x180034417  mov     cl, cs:byte_1800C8404
0x18003441d  mov     eax, [rsi+68h]
0x180034420  sub     eax, 4
0x180034423  cmp     eax, 1
0x180034426  jbe     short loc_180034493
0x180034428  test    dil, cl
0x18003442b  jz      loc_180034542
0x180034431  mov     [rbp+870h+Buffer], r15w
0x180034436  cmp     dword ptr [rsi+60h], 0FFFFFFFFh
0x18003443a  jz      short loc_180034459
0x18003443c  mov     r9d, 0Ah; Radix
0x180034442  lea     r8d, [r9+0Ah]; BufferCount
0x180034446  lea     rdx, [rbp+870h+Buffer]; Buffer
0x18003444a  mov     ecx, [rsi+60h]; Value
0x18003444d  call    cs:__imp__itow_s
0x180034453  mov     cl, cs:byte_1800C8404
0x180034459  test    dil, cl
0x18003445c  jz      loc_180034542
0x180034462  lea     rax, [rbp+870h+Buffer]
0x180034466  mov     qword ptr [rsp+970h+dwErrorCode], rax
0x18003446b  mov     [rsp+970h+plpszSubStringArray], r15
0x180034470  lea     r9, [rbp+870h+var_8F0]
0x180034474  lea     r8, aAuthNotStarted; "Auth not started"
0x18003447b  lea     rdx, RasDdmParamTraceInfo
0x180034482  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034489  call    McTemplateU0zjzz_EventWriteTransfer
0x18003448e  jmp     loc_180034542
0x180034493  mov     rax, [rsi]
0x180034496  lea     rdx, [rsi+78h]
0x18003449a  mov     rcx, rsi
0x18003449d  mov     rax, [rax+278h]
0x1800344a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a9  mov     r14d, eax
0x1800344ac  test    eax, eax
0x1800344ae  jz      loc_180034568
0x1800344b4  mov     r15d, 8
0x1800344ba  test    cs:byte_1800C8404, r15b
0x1800344c1  jz      short loc_18003452C
0x1800344c3  xor     ebx, ebx
0x1800344c5  mov     word ptr [rbp+870h+var_840], bx
0x1800344c9  mov     [rbp+870h+Buffer], bx
0x1800344cd  mov     ecx, [rsi+60h]; Value
0x1800344d0  cmp     ecx, 0FFFFFFFFh
0x1800344d3  jz      short loc_1800344E7
0x1800344d5  lea     r9d, [r15+2]; Radix
0x1800344d9  lea     r8d, [r15+0Ch]; BufferCount
0x1800344dd  lea     rdx, [rbp+870h+Buffer]; Buffer
0x1800344e1  call    cs:__imp__itow_s
0x1800344e7  mov     r8d, r14d
0x1800344ea  lea     rdx, aGetbundlehandl; "GetBundleHandle failed: %d"
0x1800344f1  lea     rcx, [rbp+870h+var_840]
0x1800344f5  call    FormatRRASErrorString
0x1800344fa  test    cs:byte_1800C8404, r15b
0x180034501  jz      short loc_18003452C
0x180034503  lea     rax, [rbp+870h+Buffer]
0x180034507  mov     qword ptr [rsp+970h+dwErrorCode], rax
0x18003450c  mov     [rsp+970h+plpszSubStringArray], rbx
0x180034511  lea     r9, [rbp+870h+var_8F0]
0x180034515  lea     r8, [rbp+870h+var_840]
0x180034519  lea     rdx, RasDdmParamTraceError
0x180034520  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034527  call    McTemplateU0zjzz_EventWriteTransfer
0x18003452c  mov     rax, [rsi]
0x18003452f  mov     edx, r14d
0x180034532  mov     rcx, rsi
0x180034535  mov     rax, [rax+0C8h]
0x18003453c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034541  nop
0x180034542  or      eax, 0FFFFFFFFh
0x180034545  lock xadd [rsi+8], eax
0x18003454a  cmp     eax, 1
0x18003454d  jnz     short loc_180034563
0x18003454f  mov     rax, [rsi]
0x180034552  mov     edx, 1
0x180034557  mov     rcx, rsi
0x18003455a  mov     rax, [rax]
0x18003455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034562  nop
0x180034563  jmp     loc_180035589
0x180034568  mov     [rsp+970h+var_914], r15d
0x18003456d  mov     [rsp+970h+var_910], r15d
0x180034572  mov     rcx, cs:g_pIDimInterfaceTable
0x180034579  mov     rax, [rcx]
0x18003457c  mov     rax, [rax]
0x18003457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034584  mov     [rsp+970h+var_918], 1
0x18003458c  mov     r15d, 8
0x180034592  mov     r10d, 7FFFFFFEh
0x180034598  cmp     r13d, 1
0x18003459c  jnz     loc_1800348CB
0x1800345a2  xor     r11d, r11d
0x1800345a5  cmp     [rbx+50h], r11
0x1800345a9  jnz     loc_180034646
0x1800345af  cmp     [rbx+60h], r11
0x1800345b3  jnz     loc_180034646
0x1800345b9  mov     ecx, r10d
0x1800345bc  lea     r8, [rbx+70h]
0x1800345c0  mov     edx, 101h
0x1800345c5  lea     rax, [rsi+0A8h]
0x1800345cc  lea     r14d, [r15-6]
0x1800345d0  test    rcx, rcx
0x1800345d3  jz      short loc_1800345F2
0x1800345d5  movzx   r9d, word ptr [r8]
0x1800345d9  test    r9w, r9w
0x1800345dd  jz      short loc_1800345F2
0x1800345df  add     r8, r14
0x1800345e2  mov     [rax], r9w
0x1800345e6  add     rax, r14
0x1800345e9  dec     rcx
0x1800345ec  sub     rdx, 1
0x1800345f0  jnz     short loc_1800345D0
0x1800345f2  lea     rcx, [rax-2]
0x1800345f6  test    rdx, rdx
0x1800345f9  cmovnz  rcx, rax
0x1800345fd  mov     [rcx], r11w
0x180034601  mov     rcx, r10
0x180034604  lea     r8, [rbx+272h]
0x18003460b  mov     rdx, rdi
0x18003460e  lea     rax, [rsi+2AAh]
0x180034615  test    rcx, rcx
0x180034618  jz      short loc_180034637
0x18003461a  movzx   r9d, word ptr [r8]
0x18003461e  test    r9w, r9w
0x180034622  jz      short loc_180034637
0x180034624  add     r8, r14
0x180034627  mov     [rax], r9w
0x18003462b  add     rax, r14
0x18003462e  dec     rcx
0x180034631  sub     rdx, 1
0x180034635  jnz     short loc_180034615
0x180034637  lea     rcx, [rax-2]
0x18003463b  test    rdx, rdx
0x18003463e  cmovnz  rcx, rax
0x180034642  mov     [rcx], r11w
0x180034646  lea     r13, [rbx+58h]
0x18003464a  lea     r9, [rbx+70h]; unsigned __int16 *
0x18003464e  lea     rax, [rsp+970h+var_920]
0x180034653  mov     qword ptr [rsp+970h+dwErrorCode], rax; struct IDimInterface **
0x180034658  mov     [rsp+970h+plpszSubStringArray], r13; struct _IKEv2_CERT_BLOB *
0x18003465d  mov     r8, [rbx+50h]; struct _ROUTER_IP_ADDRESS *
0x180034661  mov     rdx, [rbx+48h]; struct _ROUTER_IP_ADDRESS *
0x180034665  mov     rcx, rsi; this
0x180034668  call    ?ValidateIncomingConnection@DdmDevice@@QEAAKPEAU_ROUTER_IP_ADDRESS@@0PEAGPEAU_IKEv2_CERT_BLOB@@PEAPEAUIDimInterface@@@Z; DdmDevice::ValidateIncomingConnection(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,ushort *,_IKEv2_CERT_BLOB *,IDimInterface * *)
0x18003466d  mov     r14d, eax
0x180034670  test    eax, eax
0x180034672  jnz     loc_180034A16
0x180034678  mov     rcx, [rsp+970h+var_920]
0x18003467d  test    rcx, rcx
0x180034680  jz      loc_180034811
0x180034686  mov     rax, [rcx]
0x180034689  mov     rax, [rax]
0x18003468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034691  mov     [rsp+970h+var_914], 1
0x180034699  cmp     qword ptr [rbx+60h], 0
0x18003469e  jz      short loc_1800346FA
0x1800346a0  mov     r13d, 7FFFFFFEh
0x1800346a6  mov     rcx, [rsp+970h+var_920]
0x1800346ab  mov     rax, [rcx]
0x1800346ae  mov     rax, [rax+118h]
0x1800346b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346ba  mov     r8d, 101h
0x1800346c0  lea     rdx, [rsi+0A8h]
0x1800346c7  xor     r9d, r9d
0x1800346ca  test    r13, r13
0x1800346cd  jz      short loc_1800346EB
0x1800346cf  movzx   ecx, word ptr [rax]
0x1800346d2  test    cx, cx
0x1800346d5  jz      short loc_1800346EB
0x1800346d7  add     rax, 2
0x1800346db  mov     [rdx], cx
0x1800346de  add     rdx, 2
0x1800346e2  dec     r13
0x1800346e5  sub     r8, 1
0x1800346e9  jnz     short loc_1800346CA
0x1800346eb  lea     rcx, [rdx-2]
0x1800346ef  test    r8, r8
0x1800346f2  cmovnz  rcx, rdx
0x1800346f6  mov     [rcx], r9w
0x1800346fa  mov     rax, [rsi]
0x1800346fd  mov     edx, 1
0x180034702  mov     rcx, rsi
0x180034705  mov     rax, [rax+280h]
0x18003470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034711  mov     rcx, [rsp+970h+var_920]
0x180034716  mov     rax, [rcx]
0x180034719  lea     rdx, [rbp+870h+Buf1]
0x18003471d  mov     rax, [rax+168h]
0x180034724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034729  movups  xmm0, xmmword ptr [rax]
0x18003472c  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x180034731  xor     r13d, r13d
0x180034734  cmp     [rsp+970h+var_920], r13
0x180034739  jnz     loc_1800349DD
0x18003473f  lea     r13, [rsi+0A8h]
0x180034746  lea     r9, [rbx+58h]
0x18003474a  lea     r8, [rbx+292h]
0x180034751  lea     rcx, [rsi+2AAh]
0x180034758  lea     rax, [rbp+870h+var_8D0]
0x18003475c  mov     [rsp+970h+plpszSubStringArray], rax
0x180034761  mov     rdx, r13
0x180034764  call    DDMRoutingDomainLookupForIncomingConnection
0x180034769  mov     r14d, eax
0x18003476c  xor     ecx, ecx
0x18003476e  test    eax, eax
0x180034770  jnz     loc_18003495E
0x180034776  lea     rcx, [rbp+870h+var_8D0]; struct _GUID *
0x18003477a  call    ?ValidateIncomingVpnClientConnection@@YAKPEAU_GUID@@@Z; ValidateIncomingVpnClientConnection(_GUID *)
0x18003477f  mov     r14d, eax
0x180034782  xor     ecx, ecx
0x180034784  test    eax, eax
0x180034786  jz      loc_180034941
0x18003478c  test    cs:byte_1800C8404, r15b
0x180034793  jz      loc_180034941
0x180034799  mov     word ptr [rbp+870h+var_840], cx
0x18003479d  mov     [rbp+870h+Buffer], cx
0x1800347a1  mov     ecx, [rsi+60h]; Value
0x1800347a4  cmp     ecx, 0FFFFFFFFh
0x1800347a7  jz      short loc_1800347BD
0x1800347a9  mov     r9d, 0Ah; Radix
  ... truncated ...
```
