# DdmDevice::LinkUp(int,_PROTOCOL_SRV_NEW_BUNDLE *)

- ea: `0x180036080`
- end: `0x180037211`
- name: `?LinkUp@DdmDevice@@UEAAXHPEAU_PROTOCOL_SRV_NEW_BUNDLE@@@Z`
- size: `4497`
- prototype: `void __fastcall(DdmDevice *__hidden this, int, struct _PROTOCOL_SRV_NEW_BUNDLE *)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180001328`
- `0x180002fcc`
- `0x180007d00`
- `0x18000ace4`
- `0x18000c240`
- `0x18000c408`
- `0x18001bbc4`
- `0x18002ecb0`
- `0x18002ee74`
- `0x18002fb20`
- `0x1800304dc`
- `0x180030684`
- `0x180036080`
- `0x18003a454`
- `0x18003ad24`
- `0x180075588`
- `0x1800755b8`
- `0x18007f7f8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x180036ad6`
- `rtutils!RouterLogEventW` at `0x180037140`
- `rtutils!RouterLogEventW` at `0x180036ad6`
- `rtutils!RouterLogEventW` at `0x180037140`
- `rtutils!RouterLogEventStringW` at `0x180036790`
- `rtutils!RouterLogEventStringW` at `0x180036790`

## string_xrefs

- `0x18003619b`: `DdmDevice::LinkUp`
- `0x18003660e`: `ValidateIncomingVpnClientConnection failed for user %ws: %d`
- `0x180036b8e`: `CreateInsertClientInterfaceForDdm failed: %d`
- `0x180036fdf`: `The interface %ws is already connected/connecting port=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DdmDevice::LinkUp(DdmDevice *this, int a2, struct _PROTOCOL_SRV_NEW_BUNDLE *a3)
{
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // esi
  char v8; // cl
  DWORD dwErrorCode; // r15d
  struct IDimInterface *v10; // rcx
  const wchar_t *v11; // rax
  BYTE *v12; // r8
  struct DdmConnectionTable *Instance; // rax
  DdmConnection *v14; // rbx
  DdmConnection *v15; // rax
  DdmConnection *v16; // rax
  __int64 v17; // rdx
  int v18; // ecx
  _WORD *v19; // r11
  const wchar_t *v20; // rax
  __int64 v21; // r11
  struct IDimInterface *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rax
  struct IDimInterface *v28; // rcx
  bool v29; // zf
  __int64 (__fastcall *v30)(struct IDimInterface *, char *); // rax
  char *v31; // rdx
  __int128 *v32; // rax
  int v33; // esi
  unsigned int v34; // edi
  __int64 v35; // rax
  __int64 v36; // rdi
  __int64 v37; // rax
  struct IDimInterface *v38; // rcx
  __int64 (__fastcall *v39)(struct IDimInterface *, char *); // rax
  char *v40; // rdx
  __int128 *v41; // rax
  int v42; // r13d
  void (__fastcall *v43)(struct IDimInterface *, _QWORD); // rdi
  int v44; // eax
  DdmConnectionTable *v45; // rax
  __int64 v46; // rdi
  __int64 v47; // rax
  __int64 v48; // rdi
  __int64 v49; // rax
  struct IDimInterface *v50; // rcx
  __int64 (__fastcall *v51)(struct IDimInterface *, char *); // rax
  char *v52; // rdx
  __int128 *v53; // rax
  DWORD v54; // ebx
  void (*v55)(void); // rax
  LPWSTR *plpszSubStringArray; // [rsp+28h] [rbp-E0h]
  struct IDimInterface *v57; // [rsp+58h] [rbp-B0h] BYREF
  int v58; // [rsp+60h] [rbp-A8h]
  int v59; // [rsp+64h] [rbp-A4h]
  int v60; // [rsp+68h] [rbp-A0h]
  int v61; // [rsp+6Ch] [rbp-9Ch]
  __int64 v62; // [rsp+70h] [rbp-98h] BYREF
  DdmConnection *v63; // [rsp+78h] [rbp-90h] BYREF
  int v64; // [rsp+80h] [rbp-88h]
  DdmDevice *v65; // [rsp+88h] [rbp-80h]
  DdmConnection *v66; // [rsp+90h] [rbp-78h]
  struct _GUID v67; // [rsp+98h] [rbp-70h] BYREF
  __int128 v68; // [rsp+A8h] [rbp-60h] BYREF
  struct _GUID v69; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v70[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v71; // [rsp+D8h] [rbp-30h]
  _BYTE v72[16]; // [rsp+E8h] [rbp-20h] BYREF
  char v73; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v74[16]; // [rsp+108h] [rbp+0h] BYREF
  char v75; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v76[16]; // [rsp+128h] [rbp+20h] BYREF
  char v77; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v78[16]; // [rsp+148h] [rbp+40h] BYREF
  char v79; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v80[16]; // [rsp+168h] [rbp+60h] BYREF
  char v81; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v82[16]; // [rsp+188h] [rbp+80h] BYREF
  char v83; // [rsp+198h] [rbp+90h] BYREF
  LPWSTR v84[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v85; // [rsp+1B8h] [rbp+B0h]
  int v86; // [rsp+1C8h] [rbp+C0h] BYREF
  __int128 v87; // [rsp+1CCh] [rbp+C4h]
  __int128 v88; // [rsp+1DCh] [rbp+D4h]
  int v89; // [rsp+1ECh] [rbp+E4h]
  int v90; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v91[2044]; // [rsp+1FCh] [rbp+F4h] BYREF

  v64 = a2;
  *(_OWORD *)v84 = 0;
  v85 = 0;
  v57 = 0;
  v63 = 0;
  LODWORD(v62) = 0;
  v5 = (unsigned __int16)*((_DWORD *)this + 34);
  if ( v5 == 15 )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( v5 == 16 )
      v6 = 2;
  }
  v58 = v6;
  v69 = GUID_NULL;
  v7 = 0;
  v59 = 0;
  v60 = 0;
  v65 = this;
  if ( this )
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v90 = 0;
  memset_0(v91, 0, sizeof(v91));
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v68 = 0;
  v8 = byte_1800CF404;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v90) = 0;
    LOWORD(v86) = 0;
    ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
    FormatRRASErrorString(&v90, L"%s (hport: %ld)", L"DdmDevice::LinkUp", *((_QWORD *)this + 12));
    v8 = byte_1800CF404;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v90,
        (unsigned int)&v68,
        0,
        (__int64)&v86);
      v8 = byte_1800CF404;
    }
  }
  if ( (unsigned int)(*((_DWORD *)this + 26) - 4) > 1 )
  {
    if ( (v8 & 0x10) != 0 )
    {
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"Auth not started",
          (unsigned int)&v68,
          0,
          (__int64)&v86);
    }
LABEL_19:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(DdmDevice *, __int64))this)(this, 1);
    return;
  }
  dwErrorCode = (*(__int64 (__fastcall **)(DdmDevice *, char *))(*(_QWORD *)this + 632LL))(this, (char *)this + 120);
  if ( dwErrorCode )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v90) = 0;
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      FormatRRASErrorString(&v90, L"GetBundleHandle failed: %d", dwErrorCode);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v90,
          (unsigned int)&v68,
          0,
          (__int64)&v86);
    }
    (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
    goto LABEL_19;
  }
  (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
  v61 = 1;
  if ( v6 == 1 )
  {
    if ( !*((_QWORD *)a3 + 10) && !*((_QWORD *)a3 + 12) )
    {
      StringCbCopyW((STRSAFE_LPWSTR)this + 84, 0x202u, (STRSAFE_LPCWSTR)a3 + 56);
      StringCbCopyW((STRSAFE_LPWSTR)this + 341, 0x20u, (STRSAFE_LPCWSTR)a3 + 313);
    }
    dwErrorCode = DdmDevice::ValidateIncomingConnection(
                    this,
                    *((struct _ROUTER_IP_ADDRESS **)a3 + 9),
                    *((struct _ROUTER_IP_ADDRESS **)a3 + 10),
                    (unsigned __int16 *)a3 + 56,
                    (struct _PROTOCOL_SRV_NEW_BUNDLE *)((char *)a3 + 88),
                    &v57);
    if ( !dwErrorCode )
    {
      v10 = v57;
      if ( v57 )
      {
        (**(void (__fastcall ***)(struct IDimInterface *))v57)(v57);
        v7 = dwErrorCode + 1;
        v59 = dwErrorCode + 1;
        if ( *((_QWORD *)a3 + 12) )
        {
          v11 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
          StringCbCopyW((STRSAFE_LPWSTR)this + 84, 0x202u, v11);
        }
        (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 640LL))(this, v7);
        v69 = *(struct _GUID *)(*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v57 + 360LL))(
                                 v57,
                                 v70);
        goto LABEL_42;
      }
      v12 = (BYTE *)*((_QWORD *)a3 + 12);
      if ( !v12 )
        goto LABEL_43;
      dwErrorCode = GetRemoteUserNameFromCertificate(
                      *((_DWORD *)a3 + 26),
                      *((_DWORD *)a3 + 22),
                      v12,
                      (unsigned __int16 *)this + 84);
      if ( dwErrorCode )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v90) = 0;
          LOWORD(v86) = 0;
          ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
          FormatRRASErrorString(&v90, L"GetRemoteUserNameFromCertificate failed: %d", dwErrorCode);
          if ( (byte_1800CF404 & 8) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v90,
              (unsigned int)&v68,
              0,
              (__int64)&v86);
        }
        (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
        goto LABEL_143;
      }
    }
LABEL_41:
    if ( dwErrorCode )
      goto LABEL_56;
    goto LABEL_42;
  }
  if ( !v6 )
  {
    dwErrorCode = DdmDevice::ValidateIncomingConnection(this, 0, 0, (unsigned __int16 *)this + 84, 0, &v57);
    if ( dwErrorCode )
      goto LABEL_41;
    v10 = v57;
    if ( !v57 )
      goto LABEL_43;
    (**(void (__fastcall ***)(struct IDimInterface *))v57)(v57);
    v7 = 1;
    v59 = 1;
    (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 640LL))(this, 1);
  }
LABEL_42:
  v10 = v57;
LABEL_43:
  if ( v10 )
  {
    MprInfoDelete(*((LPVOID *)a3 + 1));
    *((_QWORD *)a3 + 1) = 0;
    MprInfoDelete(*((LPVOID *)a3 + 2));
    *((_QWORD *)a3 + 2) = 0;
    MprInfoDelete(*((LPVOID *)a3 + 3));
    MprInfoDelete(*((LPVOID *)a3 + 4));
    *((_QWORD *)a3 + 3) = 0;
    *((_DWORD *)a3 + 10) = 0;
  }
  else
  {
    dwErrorCode = DDMRoutingDomainLookupForIncomingConnection(
                    (unsigned __int16 *)this + 341,
                    (unsigned __int16 *)this + 84,
                    (unsigned __int16 *)a3 + 329,
                    &v69);
    if ( dwErrorCode )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v90) = 0;
        LOWORD(v86) = 0;
        ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
        FormatRRASErrorString(&v90, L"Routing domain lookup failed for user %ws: %d", (char *)this + 168, dwErrorCode);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v90,
            (unsigned int)&v68,
            0,
            (__int64)&v86);
      }
      goto LABEL_56;
    }
    dwErrorCode = ValidateIncomingVpnClientConnection(&v69);
    if ( dwErrorCode )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v90) = 0;
        LOWORD(v86) = 0;
        ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
        FormatRRASErrorString(
          &v90,
          L"ValidateIncomingVpnClientConnection failed for user %ws: %d",
          (char *)this + 168,
          dwErrorCode);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v90,
            (unsigned int)&v68,
            0,
            (__int64)&v86);
      }
    }
    if ( dword_1800CF654 )
      *((_DWORD *)this + 33) |= 0x80u;
  }
  if ( dwErrorCode )
  {
LABEL_56:
    v84[0] = (LPWSTR)((char *)this + 1092);
    v84[1] = (LPWSTR)((char *)this + 168);
    *(_QWORD *)&v85 = (char *)this + 714;
    if ( (unsigned int)dword_1800CF4E4 > 1 )
      RouterLogEventStringW(hLogHandle, 2u, 0x4F2Eu, 3u, v84, dwErrorCode, 3u);
    goto LABEL_58;
  }
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v63);
  v14 = v63;
  if ( v63 )
    goto LABEL_135;
  v71 = 0;
  v15 = (DdmConnection *)operator new(0x5E0u);
  v66 = v15;
  if ( v15 )
    v16 = DdmConnection::DdmConnection(v15, (void *)0xFFFFFFFFFFFFFFFFLL, *((void **)this + 15));
  else
    v16 = 0;
  RasObjPtr<DdmDevice>::reset(&v63, v16);
  v14 = v63;
  if ( !v63 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)L"ConnObj Allocation failed",
          (unsigned int)&v68,
          0,
          (__int64)&v86);
    }
    v17 = 8;
    goto LABEL_68;
  }
  v18 = 1;
  if ( (unsigned __int16)*((_DWORD *)this + 34) == 15 )
    v18 = 128;
  *((_DWORD *)v63 + 20) = v18;
  *((_QWORD *)v14 + 8) = *((_QWORD *)this + 12);
  *(struct _GUID *)((char *)v14 + 1484) = v69;
  *((_QWORD *)v14 + 14) = *((_QWORD *)a3 + 2);
  *((_QWORD *)v14 + 16) = *((_QWORD *)a3 + 3);
  *((_QWORD *)v14 + 17) = *((_QWORD *)a3 + 4);
  *((_DWORD *)v14 + 366) = *((_DWORD *)a3 + 11);
  if ( *(_QWORD *)((char *)this + 1076)
    || _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] != *(_QWORD *)((char *)this + 1084) )
  {
    *(_OWORD *)((char *)v14 + 148) = *(_OWORD *)((char *)this + 1076);
  }
  StringCbCopyW((STRSAFE_LPWSTR)v14 + 82, 0x202u, (STRSAFE_LPCWSTR)this + 84);
  if ( !*v19 && v58 == 1 )
  {
    if ( !v57 )
    {
      v17 = 0;
LABEL_68:
      (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, v17);
      goto LABEL_140;
    }
    v20 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
    StringCbCopyW((STRSAFE_LPWSTR)v14 + 82, 0x202u, v20);
  }
  StringCbCopyW((STRSAFE_LPWSTR)v14 + 339, 0x202u, (STRSAFE_LPCWSTR)this + 84);
  StringCbCopyW((STRSAFE_LPWSTR)v14 + 596, 0x20u, (STRSAFE_LPCWSTR)this + 341);
  v22 = v57;
  if ( v57
    || (v22 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                          + 48LL))(
                                        g_pIDimInterfaceTable,
                                        v21,
                                        0),
        (v57 = v22) != 0) )
  {
    if ( !v7 )
    {
      (**(void (__fastcall ***)(struct IDimInterface *))v22)(v22);
      v59 = 1;
      v22 = v57;
    }
    if ( ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v22 + 104LL))(v22) & 4) == 0 )
    {
      dwErrorCode = 916;
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_133;
      LOWORD(v90) = 0;
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      v25 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
      FormatRRASErrorString(&v90, L"The interface %ws is disabled. Rejecting the connection.", v25);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_133;
      v26 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
      v27 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v57 + 360LL))(v57, v72);
      v28 = v57;
      v29 = v27 == 0;
      v30 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
      if ( v29 )
      {
        if ( !v30(v57, v74) )
        {
          v32 = &v68;
          goto LABEL_106;
        }
        v28 = v57;
        v31 = &v75;
        v30 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
      }
      else
      {
        v31 = &v73;
      }
      LODWORD(v32) = v30(v28, v31);
LABEL_106:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v90,
        (_DWORD)v32,
        v26,
        (__int64)&v86);
LABEL_133:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
      v61 = 0;
      v7 = v59;
      goto LABEL_134;
    }
    if ( (byte_1800CF404 & 8) == 0 )
      goto LABEL_116;
    LOWORD(v90) = 0;
    LOWORD(v86) = 0;
    ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
    v33 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 104LL))(v57);
    v34 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 40LL))(v57);
    v35 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
    LODWORD(plpszSubStringArray) = v33;
    FormatRRASErrorString(&v90, L"Interface name=%ws, State=%d, fFlags=0x%.8x", v35, v34, plpszSubStringArray);
    if ( (byte_1800CF404 & 8) == 0 )
    {
LABEL_116:
      if ( (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 40LL))(v57) != 2
        && ((*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 40LL))(v57) != 1
         || ((*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 104LL))(v57) & 0x800) != 0) )
      {
        v7 = v59;
        goto LABEL_120;
      }
      dwErrorCode = 901;
      if ( (byte_1800CF404 & 8) == 0
        || (LOWORD(v90) = 0,
            LOWORD(v86) = 0,
            ConvertPortNoToString(&v86, *((unsigned int *)this + 24)),
            v46 = *((_QWORD *)this + 12),
            v47 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57),
            FormatRRASErrorString(&v90, L"The interface %ws is already connected/connecting port=%d", v47, v46),
            (byte_1800CF404 & 8) == 0) )
      {
LABEL_132:
        (*(void (__fastcall **)(struct IDimInterface *, __int64))(*(_QWORD *)v57 + 32LL))(v57, 901);
        goto LABEL_133;
      }
      v48 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
      v49 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v57 + 360LL))(v57, v80);
      v50 = v57;
      v29 = v49 == 0;
      v51 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
      if ( v29 )
      {
        if ( !v51(v57, v82) )
        {
          v53 = &v68;
          goto LABEL_131;
        }
        v50 = v57;
        v52 = &v83;
        v51 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
      }
      else
      {
        v52 = &v81;
      }
      LODWORD(v53) = v51(v50, v52);
LABEL_131:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v90,
        (_DWORD)v53,
        v48,
        (__int64)&v86);
      goto LABEL_132;
    }
    v36 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 280LL))(v57);
    v37 = (*(__int64 (__fastcall **)(struct IDimInterface *, _BYTE *))(*(_QWORD *)v57 + 360LL))(v57, v76);
    v38 = v57;
    v29 = v37 == 0;
    v39 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
    if ( v29 )
    {
      if ( !v39(v57, v78) )
      {
        v41 = &v68;
        goto LABEL_115;
      }
      v38 = v57;
      v40 = &v79;
      v39 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v57 + 360LL);
    }
    else
    {
      v40 = &v77;
    }
    LODWORD(v41) = v39(v38, v40);
LABEL_115:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v90,
      (_DWORD)v41,
      v36,
      (__int64)&v86);
    goto LABEL_116;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  v61 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
  v60 = 1;
  v23 = *(_QWORD *)g_pIDimInterfaceTable;
  v24 = *((_QWORD *)a3 + 1);
  v67 = v69;
  LOBYTE(plpszSubStringArray) = 1;
  dwErrorCode = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD, struct _GUID *, __int64, __int64 *, struct IDimInterface **))(v23 + 40))(
                  g_pIDimInterfaceTable,
                  (__int64)v14 + 678,
                  1,
                  *((_QWORD *)v14 + 7),
                  (_DWORD)plpszSubStringArray,
                  &v67,
                  v24,
                  &v62,
                  &v57);
  if ( (_DWORD)v62 == 1 )
  {
    v84[0] = (LPWSTR)((char *)this + 1092);
    v84[1] = (LPWSTR)((char *)this + 168);
    *(_QWORD *)&v85 = (char *)this + 714;
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4EE1u, 3u, v84, 0);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v90) = 0;
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      FormatRRASErrorString(&v90, L"Failed to add the filter with error %d", (unsigned int)v62);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v90,
          (unsigned int)&v68,
          0,
          (__int64)&v86);
    }
  }
  if ( dwErrorCode )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v90) = 0;
      LOWORD(v86) = 0;
      ConvertPortNoToString(&v86, *((unsigned int *)this + 24));
      FormatRRASErrorString(&v90, L"CreateInsertClientInterfaceForDdm failed: %d", dwErrorCode);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v90,
          (unsigned int)&v68,
          0,
          (__int64)&v86);
    }
    goto LABEL_90;
  }
  if ( *((_DWORD *)a3 + 10) )
    *((_DWORD *)v14 + 20) |= 0x40u;
  (**(void (__fastcall ***)(struct IDimInterface *))v57)(v57);
  v7 = 1;
LABEL_120:
  v42 = v61;
  v59 = v7;
  (*(void (__fastcall **)(struct IDimInterface *, __int64))(*(_QWORD *)v57 + 48LL))(v57, 1);
  v43 = *(void (__fastcall **)(struct IDimInterface *, _QWORD))(*(_QWORD *)v57 + 112LL);
  v44 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 104LL))(v57);
  v43(v57, v44 & 0xFFFFFFFE);
  *((_QWORD *)v14 + 9) = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 16LL))(v57);
  *((_DWORD *)v14 + 36) = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 72LL))(v57);
  v45 = DdmConnectionTable::GetInstance();
  DdmConnectionTable::AddConnection(v45);
  if ( v42 )
    goto LABEL_133;
  if ( v60 )
  {
LABEL_90:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
    v60 = 0;
  }
LABEL_134:
  if ( dwErrorCode )
  {
LABEL_58:
    (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 200LL))(this, dwErrorCode);
    goto LABEL_140;
  }
LABEL_135:
  if ( v64 )
    DdmDevice::SendInterfaceInfoToProtocolEngine(this);
  v54 = DdmConnection::AddLink(v14);
  if ( v54 )
  {
    (*(void (__fastcall **)(DdmDevice *, __int64))(*(_QWORD *)this + 200LL))(this, 8);
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, v54);
  }
LABEL_140:
  if ( v7 )
    (*(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v57 + 8LL))(v57);
  if ( v61 )
  {
LABEL_143:
    v55 = *(void (**)(void))(*(_QWORD *)g_pIDimInterfaceTable + 16LL);
LABEL_146:
    v55();
    goto LABEL_147;
  }
  if ( v60 )
  {
    v55 = *(void (**)(void))(*(_QWORD *)g_pIDimInterfaceTable + 24LL);
    goto LABEL_146;
  }
LABEL_147:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmDevice *, __int64))this)(this, 1);
  if ( v63 && _InterlockedExchangeAdd((volatile signed __int32 *)v63 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(DdmConnection *, __int64))v63)(v63, 1);
}

```

## disassembly

```asm
0x180036080  mov     rax, rsp
0x180036083  mov     [rax+10h], rbx
0x180036087  push    rbp
0x180036088  push    rsi
0x180036089  push    rdi
0x18003608a  push    r12
0x18003608c  push    r13
0x18003608e  push    r14
0x180036090  push    r15
0x180036092  lea     rbp, [rax-948h]
0x180036099  sub     rsp, 0A10h
0x1800360a0  movaps  xmmword ptr [rax-48h], xmm6
0x1800360a4  mov     rax, cs:__security_cookie
0x1800360ab  xor     rax, rsp
0x1800360ae  mov     [rbp+940h+var_50], rax
0x1800360b5  mov     rdi, r8
0x1800360b8  mov     [rsp+0A40h+var_9C8], edx
0x1800360bc  mov     r14, rcx
0x1800360bf  xorps   xmm0, xmm0
0x1800360c2  movups  xmmword ptr [rbp+940h+var_8A0], xmm0
0x1800360c9  movups  [rbp+940h+var_890], xmm0
0x1800360d0  xor     r13d, r13d
0x1800360d3  mov     [rsp+0A40h+var_9F0], r13
0x1800360d8  mov     [rsp+0A40h+var_9D0], r13
0x1800360dd  mov     dword ptr [rsp+0A40h+var_9D8], r13d
0x1800360e2  mov     eax, [rcx+88h]
0x1800360e8  movzx   eax, ax
0x1800360eb  lea     ecx, [r13+2]
0x1800360ef  cmp     eax, 0Fh
0x1800360f2  jnz     short loc_1800360F9
0x1800360f4  lea     ebx, [rcx-1]
0x1800360f7  jmp     short loc_180036102
0x1800360f9  mov     ebx, r13d
0x1800360fc  cmp     eax, 10h
0x1800360ff  cmovz   ebx, ecx
0x180036102  mov     [rsp+0A40h+var_9E8], ebx
0x180036106  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003610d  movdqu  xmmword ptr [rbp+940h+var_990.Data1], xmm0
0x180036112  mov     esi, r13d
0x180036115  mov     [rsp+0A40h+var_9E4], r13d
0x18003611a  mov     [rsp+0A40h+var_9E0], r13d
0x18003611f  mov     [rbp+940h+var_9C0], r14
0x180036123  test    r14, r14
0x180036126  jz      short loc_18003612D
0x180036128  lock inc dword ptr [r14+8]
0x18003612d  mov     [rbp+940h+var_850], r13d
0x180036134  xor     edx, edx; Val
0x180036136  mov     r8d, 7FCh; Size
0x18003613c  lea     rcx, [rbp+940h+var_84C]; void *
0x180036143  call    memset_0
0x180036148  mov     [rbp+940h+var_880], r13d
0x18003614f  xorps   xmm0, xmm0
0x180036152  xor     eax, eax
0x180036154  movups  [rbp+940h+var_87C], xmm0
0x18003615b  movups  [rbp+940h+var_86C], xmm0
0x180036162  mov     [rbp+940h+var_85C], eax
0x180036168  movups  [rbp+940h+var_9A0], xmm0
0x18003616c  mov     cl, cs:byte_1800CF404
0x180036172  test    cl, 10h
0x180036175  jz      short loc_1800361F5
0x180036177  mov     word ptr [rbp+940h+var_850], r13w
0x18003617f  mov     word ptr [rbp+940h+var_880], r13w
0x180036187  mov     edx, [r14+60h]
0x18003618b  lea     rcx, [rbp+940h+var_880]
0x180036192  call    ConvertPortNoToString
0x180036197  mov     r9, [r14+60h]
0x18003619b  lea     r8, aDdmdeviceLinku; "DdmDevice::LinkUp"
0x1800361a2  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x1800361a9  lea     rcx, [rbp+940h+var_850]
0x1800361b0  call    FormatRRASErrorString
0x1800361b5  mov     cl, cs:byte_1800CF404
0x1800361bb  test    cl, 10h
0x1800361be  jz      short loc_1800361F5
0x1800361c0  lea     rax, [rbp+940h+var_880]
0x1800361c7  mov     qword ptr [rsp+0A40h+dwErrorCode], rax
0x1800361cc  mov     [rsp+0A40h+plpszSubStringArray], r13
0x1800361d1  lea     r9, [rbp+940h+var_9A0]
0x1800361d5  lea     r8, [rbp+940h+var_850]
0x1800361dc  lea     rdx, RasDdmParamTraceInfo
0x1800361e3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800361ea  call    McTemplateU0zjzz_EventWriteTransfer
0x1800361ef  mov     cl, cs:byte_1800CF404
0x1800361f5  mov     eax, [r14+68h]
0x1800361f9  sub     eax, 4
0x1800361fc  cmp     eax, 1
0x1800361ff  jbe     short loc_180036263
0x180036201  test    cl, 10h
0x180036204  jz      loc_180036317
0x18003620a  mov     word ptr [rbp+940h+var_880], r13w
0x180036212  mov     edx, [r14+60h]
0x180036216  lea     rcx, [rbp+940h+var_880]
0x18003621d  call    ConvertPortNoToString
0x180036222  test    cs:byte_1800CF404, 10h
0x180036229  jz      loc_180036317
0x18003622f  lea     rax, [rbp+940h+var_880]
0x180036236  mov     qword ptr [rsp+0A40h+dwErrorCode], rax
0x18003623b  mov     [rsp+0A40h+plpszSubStringArray], r13
0x180036240  lea     r9, [rbp+940h+var_9A0]
0x180036244  lea     r8, aAuthNotStarted; "Auth not started"
0x18003624b  lea     rdx, RasDdmParamTraceInfo
0x180036252  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180036259  call    McTemplateU0zjzz_EventWriteTransfer
0x18003625e  jmp     loc_180036317
0x180036263  mov     rax, [r14]
0x180036266  lea     rdx, [r14+78h]
0x18003626a  mov     rcx, r14
0x18003626d  mov     rax, [rax+278h]
0x180036274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036279  mov     r15d, eax
0x18003627c  test    eax, eax
0x18003627e  jz      loc_18003633E
0x180036284  mov     r12d, 8
0x18003628a  test    cs:byte_1800CF404, r12b
0x180036291  jz      short loc_180036301
0x180036293  mov     word ptr [rbp+940h+var_850], r13w
0x18003629b  mov     word ptr [rbp+940h+var_880], r13w
0x1800362a3  mov     edx, [r14+60h]
0x1800362a7  lea     rcx, [rbp+940h+var_880]
0x1800362ae  call    ConvertPortNoToString
0x1800362b3  mov     r8d, r15d
0x1800362b6  lea     rdx, aGetbundlehandl; "GetBundleHandle failed: %d"
0x1800362bd  lea     rcx, [rbp+940h+var_850]
0x1800362c4  call    FormatRRASErrorString
0x1800362c9  test    cs:byte_1800CF404, r12b
0x1800362d0  jz      short loc_180036301
0x1800362d2  lea     rax, [rbp+940h+var_880]
0x1800362d9  mov     qword ptr [rsp+0A40h+dwErrorCode], rax
0x1800362de  mov     [rsp+0A40h+plpszSubStringArray], r13
0x1800362e3  lea     r9, [rbp+940h+var_9A0]
0x1800362e7  lea     r8, [rbp+940h+var_850]
0x1800362ee  lea     rdx, RasDdmParamTraceError
0x1800362f5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800362fc  call    McTemplateU0zjzz_EventWriteTransfer
0x180036301  mov     rax, [r14]
0x180036304  mov     edx, r15d
0x180036307  mov     rcx, r14
0x18003630a  mov     rax, [rax+0C8h]
0x180036311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036316  nop
0x180036317  or      eax, 0FFFFFFFFh
0x18003631a  lock xadd [r14+8], eax
0x180036320  cmp     eax, 1
0x180036323  jnz     short loc_180036339
0x180036325  mov     rax, [r14]
0x180036328  mov     edx, 1
0x18003632d  mov     rcx, r14
0x180036330  mov     rax, [rax]
0x180036333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036338  nop
0x180036339  jmp     loc_1800371E1
0x18003633e  mov     rcx, cs:g_pIDimInterfaceTable
0x180036345  mov     rax, [rcx]
0x180036348  mov     rax, [rax]
0x18003634b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036350  mov     [rsp+0A40h+var_9DC], 1
0x180036358  mov     r12d, 202h
0x18003635e  cmp     ebx, 1
0x180036361  jnz     loc_180036510
0x180036367  cmp     [rdi+50h], r13
0x18003636b  jnz     short loc_18003639C
0x18003636d  cmp     [rdi+60h], r13
0x180036371  jnz     short loc_18003639C
0x180036373  lea     r8, [rdi+70h]; pszSrc
0x180036377  lea     rcx, [r14+0A8h]; pszDest
0x18003637e  mov     edx, r12d; cbDest
0x180036381  call    StringCbCopyW
0x180036386  lea     r8, [rdi+272h]; pszSrc
0x18003638d  lea     rcx, [r14+2AAh]; pszDest
0x180036394  lea     edx, [rbx+1Fh]; cbDest
0x180036397  call    StringCbCopyW
0x18003639c  lea     rbx, [rdi+58h]
0x1800363a0  lea     r9, [rdi+70h]; unsigned __int16 *
0x1800363a4  lea     rax, [rsp+0A40h+var_9F0]
0x1800363a9  mov     qword ptr [rsp+0A40h+dwErrorCode], rax; struct IDimInterface **
0x1800363ae  mov     [rsp+0A40h+plpszSubStringArray], rbx; struct _IKEv2_CERT_BLOB *
0x1800363b3  mov     r8, [rdi+50h]; struct _ROUTER_IP_ADDRESS *
0x1800363b7  mov     rdx, [rdi+48h]; struct _ROUTER_IP_ADDRESS *
0x1800363bb  mov     rcx, r14; this
0x1800363be  call    ?ValidateIncomingConnection@DdmDevice@@QEAAKPEAU_ROUTER_IP_ADDRESS@@0PEAGPEAU_IKEv2_CERT_BLOB@@PEAPEAUIDimInterface@@@Z; DdmDevice::ValidateIncomingConnection(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,ushort *,_IKEv2_CERT_BLOB *,IDimInterface * *)
0x1800363c3  mov     r15d, eax
0x1800363c6  test    eax, eax
0x1800363c8  jnz     loc_180036570
0x1800363ce  mov     rcx, [rsp+0A40h+var_9F0]
0x1800363d3  test    rcx, rcx
0x1800363d6  jz      short loc_180036450
0x1800363d8  mov     rax, [rcx]
0x1800363db  mov     rax, [rax]
0x1800363de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363e3  lea     esi, [r15+1]
0x1800363e7  mov     [rsp+0A40h+var_9E4], esi
0x1800363eb  cmp     [rdi+60h], r13
0x1800363ef  jz      short loc_180036417
0x1800363f1  mov     rcx, [rsp+0A40h+var_9F0]
0x1800363f6  mov     rax, [rcx]
0x1800363f9  mov     rax, [rax+118h]
0x180036400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036405  mov     r8, rax; pszSrc
0x180036408  lea     rcx, [r14+0A8h]; pszDest
0x18003640f  mov     rdx, r12; cbDest
0x180036412  call    StringCbCopyW
0x180036417  mov     rax, [r14]
0x18003641a  mov     edx, esi
0x18003641c  mov     rcx, r14
0x18003641f  mov     rax, [rax+280h]
0x180036426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003642b  mov     rcx, [rsp+0A40h+var_9F0]
0x180036430  mov     rax, [rcx]
0x180036433  lea     rdx, [rbp+940h+var_980]
0x180036437  mov     rax, [rax+168h]
0x18003643e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036443  movups  xmm0, xmmword ptr [rax]
0x180036446  movdqu  xmmword ptr [rbp+940h+var_990.Data1], xmm0
0x18003644b  jmp     loc_180036579
0x180036450  mov     r8, [rdi+60h]; pbCertEncoded
0x180036454  test    r8, r8
0x180036457  jz      loc_18003657E
0x18003645d  lea     r9, [r14+0A8h]; unsigned __int16 *
0x180036464  mov     edx, [rbx]; cbCertEncoded
0x180036466  mov     ecx, [rdi+68h]; dwCertEncodingType
0x180036469  call    ?GetRemoteUserNameFromCertificate@@YAKKKPEAEPEAG@Z; GetRemoteUserNameFromCertificate(ulong,ulong,uchar *,ushort *)
0x18003646e  mov     r15d, eax
0x180036471  test    eax, eax
0x180036473  jz      loc_180036570
0x180036479  mov     r12d, 8
0x18003647f  test    cs:byte_1800CF404, r12b
0x180036486  jz      short loc_1800364F6
0x180036488  mov     word ptr [rbp+940h+var_850], r13w
0x180036490  mov     word ptr [rbp+940h+var_880], r13w
0x180036498  mov     edx, [r14+60h]
0x18003649c  lea     rcx, [rbp+940h+var_880]
0x1800364a3  call    ConvertPortNoToString
0x1800364a8  mov     r8d, r15d
0x1800364ab  lea     rdx, aGetremoteusern_0; "GetRemoteUserNameFromCertificate failed"...
0x1800364b2  lea     rcx, [rbp+940h+var_850]
0x1800364b9  call    FormatRRASErrorString
0x1800364be  test    cs:byte_1800CF404, r12b
0x1800364c5  jz      short loc_1800364F6
0x1800364c7  lea     rax, [rbp+940h+var_880]
0x1800364ce  mov     qword ptr [rsp+0A40h+dwErrorCode], rax
0x1800364d3  mov     [rsp+0A40h+plpszSubStringArray], r13
0x1800364d8  lea     r9, [rbp+940h+var_9A0]
0x1800364dc  lea     r8, [rbp+940h+var_850]
0x1800364e3  lea     rdx, RasDdmParamTraceError
0x1800364ea  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800364f1  call    McTemplateU0zjzz_EventWriteTransfer
0x1800364f6  mov     rax, [r14]
0x1800364f9  mov     edx, r15d
0x1800364fc  mov     rcx, r14
0x1800364ff  mov     rax, [rax+0C8h]
0x180036506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003650b  jmp     loc_180037168
0x180036510  test    ebx, ebx
0x180036512  jnz     short loc_180036579
0x180036514  lea     r9, [r14+0A8h]; unsigned __int16 *
0x18003651b  lea     rax, [rsp+0A40h+var_9F0]
0x180036520  mov     qword ptr [rsp+0A40h+dwErrorCode], rax; struct IDimInterface **
0x180036525  mov     [rsp+0A40h+plpszSubStringArray], r13; struct _IKEv2_CERT_BLOB *
0x18003652a  xor     r8d, r8d; struct _ROUTER_IP_ADDRESS *
0x18003652d  xor     edx, edx; struct _ROUTER_IP_ADDRESS *
0x18003652f  mov     rcx, r14; this
0x180036532  call    ?ValidateIncomingConnection@DdmDevice@@QEAAKPEAU_ROUTER_IP_ADDRESS@@0PEAGPEAU_IKEv2_CERT_BLOB@@PEAPEAUIDimInterface@@@Z; DdmDevice::ValidateIncomingConnection(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,ushort *,_IKEv2_CERT_BLOB *,IDimInterface * *)
0x180036537  mov     r15d, eax
0x18003653a  test    eax, eax
0x18003653c  jnz     short loc_180036570
0x18003653e  mov     rcx, [rsp+0A40h+var_9F0]
0x180036543  test    rcx, rcx
0x180036546  jz      short loc_18003657E
0x180036548  mov     rax, [rcx]
0x18003654b  mov     rax, [rax]
0x18003654e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036553  lea     esi, [rbx+1]
0x180036556  mov     [rsp+0A40h+var_9E4], esi
0x18003655a  mov     rax, [r14]
0x18003655d  mov     edx, esi
0x18003655f  mov     rcx, r14
0x180036562  mov     rax, [rax+280h]
0x180036569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003656e  jmp     short loc_180036579
0x180036570  test    r15d, r15d
0x180036573  jnz     loc_180036730
0x180036579  mov     rcx, [rsp+0A40h+var_9F0]
0x18003657e  mov     r12d, 8
0x180036584  lea     r13, RasDdmParamTraceError
0x18003658b  xor     ebx, ebx
0x18003658d  test    rcx, rcx
0x180036590  jnz     loc_1800366EF
0x180036596  lea     rbx, [r14+0A8h]
0x18003659d  lea     r9, [rdi+58h]
0x1800365a1  lea     r8, [rdi+292h]
0x1800365a8  lea     rcx, [r14+2AAh]
0x1800365af  lea     rax, [rbp+940h+var_990]
0x1800365b3  mov     [rsp+0A40h+plpszSubStringArray], rax
0x1800365b8  mov     rdx, rbx
0x1800365bb  call    DDMRoutingDomainLookupForIncomingConnection
0x1800365c0  mov     r15d, eax
0x1800365c3  xor     eax, eax
0x1800365c5  test    r15d, r15d
0x1800365c8  jnz     loc_180036673
0x1800365ce  lea     rcx, [rbp+940h+var_990]; struct _GUID *
0x1800365d2  call    ?ValidateIncomingVpnClientConnection@@YAKPEAU_GUID@@@Z; ValidateIncomingVpnClientConnection(_GUID *)
  ... truncated ...
```
