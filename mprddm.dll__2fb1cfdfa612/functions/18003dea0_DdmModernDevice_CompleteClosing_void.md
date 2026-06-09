# DdmModernDevice::CompleteClosing(void)

- ea: `0x18003dea0`
- end: `0x18003e591`
- name: `?CompleteClosing@DdmModernDevice@@UEAAXXZ`
- size: `1777`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002bbe`
- `0x180007c50`
- `0x180008e08`
- `0x18000aae0`
- `0x18002d0c4`
- `0x18002e0ec`
- `0x18002e268`
- `0x18002e2a8`
- `0x180036248`
- `0x18003dea0`
- `0x180044890`
- `0x180058c2c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003df47`
- `msvcrt!_itow_s` at `0x18003e00f`
- `msvcrt!_itow_s` at `0x18003e186`
- `msvcrt!_itow_s` at `0x18003e3f2`
- `msvcrt!_itow_s` at `0x18003e498`
- `msvcrt!_itow_s` at `0x18003df47`
- `msvcrt!_itow_s` at `0x18003e00f`
- `msvcrt!_itow_s` at `0x18003e186`
- `msvcrt!_itow_s` at `0x18003e3f2`
- `msvcrt!_itow_s` at `0x18003e498`
- `KERNEL32!SetEvent` at `0x18003e2dc`
- `KERNEL32!SetEvent` at `0x18003e2dc`
- `KERNEL32!LeaveCriticalSection` at `0x18003e537`
- `KERNEL32!LeaveCriticalSection` at `0x18003e537`
- `KERNEL32!EnterCriticalSection` at `0x18003e3b2`
- `KERNEL32!EnterCriticalSection` at `0x18003e3b2`

## string_xrefs

- `0x18003e1a1`: `CompleteClosing:Marking interface '%ws' DISCONNECTED.`
- `0x18003df6c`: `DdmModernDevice::CompleteClosing`
- `0x18003e417`: `DdmModernDevice::CompleteClosing`
- `0x18003e4bd`: `DdmModernDevice::CompleteClosing`
- `0x18003e043`: `CompleteClosing:hPort=%d,Auth=%d,Conn=%d %d,Protocol=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DdmModernDevice::CompleteClosing(DdmModernDevice *this)
{
  struct DdmConnectionTable *Instance; // rax
  int v3; // ecx
  int v4; // esi
  int v5; // ebx
  int v6; // r14d
  int v7; // ecx
  __int64 v8; // rax
  struct IDimInterface *v9; // rax
  struct IDimInterface *v10; // rsi
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  struct IDimInterface *v15; // rcx
  bool v16; // zf
  __int64 (__fastcall *v17)(struct IDimInterface *, char *); // rax
  char *v18; // rdx
  __int128 *v19; // rax
  void (__fastcall *v20)(struct IDimInterface *); // rax
  void (__fastcall *v21)(__int64, __int64); // rbx
  __int64 v22; // rax
  void *v23; // rcx
  _QWORD *v24; // rbx
  DdmConnectionTable *v25; // rax
  int v26; // eax
  int v27; // ecx
  int v28; // ecx
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  __int64 v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  DdmModernDevice *v34; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  char v36[16]; // [rsp+60h] [rbp-A0h] BYREF
  char v37; // [rsp+70h] [rbp-90h] BYREF
  char v38[16]; // [rsp+80h] [rbp-80h] BYREF
  char v39; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+A4h] [rbp-5Ch]
  __int128 v42; // [rsp+B4h] [rbp-4Ch]
  int v43; // [rsp+C4h] [rbp-3Ch]
  int v44; // [rsp+D0h] [rbp-30h] BYREF
  char v45[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v33 = 0;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v33);
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  *(_DWORD *)Buffer = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v35 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v44) = 0;
    Buffer[0] = 0;
    v3 = *((_DWORD *)this + 24);
    if ( v3 != -1 )
      _itow_s(v3, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v44,
      L"%s: (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
      L"DdmModernDevice::CompleteClosing",
      *((_QWORD *)this + 12),
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 26),
      *((_DWORD *)this + 33));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v44,
        (unsigned int)&v35,
        0,
        (__int64)Buffer);
  }
  v4 = 0;
  v5 = *((_DWORD *)this + 33) & 0x4000;
  if ( (*((_DWORD *)this + 33) & 0x1000) == 0 )
  {
    v4 = 1;
    DdmModernDevice::SendLinkDownToProtocolEngine(this);
  }
  v6 = *((_DWORD *)this + 32);
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v44) = 0;
    Buffer[0] = 0;
    v7 = *((_DWORD *)this + 24);
    if ( v7 != -1 )
      _itow_s(v7, Buffer, 0x14u, 10);
    LODWORD(v32) = v4 ^ 1;
    LODWORD(v31) = *((_DWORD *)this + 32);
    LODWORD(v30) = v33 == 0;
    FormatRRASErrorString(
      &v44,
      L"CompleteClosing:hPort=%d,Auth=%d,Conn=%d %d,Protocol=%d",
      *((_QWORD *)this + 12),
      v5 != 0,
      v30,
      v31,
      v32);
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v44,
        (unsigned int)&v35,
        0,
        (__int64)Buffer);
  }
  if ( !v5 && v6 == 4 && v4 )
  {
    if ( !v33 )
    {
LABEL_51:
      v26 = *((_DWORD *)this + 33);
      if ( (v26 & 8) != 0 )
      {
        *((_DWORD *)this + 33) = v26 & 0xFFFFFFF7;
        --dword_1800C84B0;
        if ( (*((_BYTE *)this + 132) & 0x40) != 0 )
          MediaObjAddToTable((wchar_t *)this + 391);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      if ( (*((_DWORD *)this + 33) & 0x200000) != 0 )
      {
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v44) = 0;
          Buffer[0] = 0;
          v27 = *((_DWORD *)this + 24);
          if ( v27 != -1 )
            _itow_s(v27, Buffer, 0x14u, 10);
          LODWORD(v32) = *((_DWORD *)this + 33);
          LODWORD(v31) = *((_DWORD *)this + 26);
          LODWORD(v30) = *((_DWORD *)this + 32);
          FormatRRASErrorString(
            &v44,
            L"%s: Skip removing device due to active routes (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
            L"DdmModernDevice::CompleteClosing",
            *((_QWORD *)this + 12),
            v30,
            v31,
            v32);
          if ( (byte_1800C8404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v44,
              (unsigned int)&v35,
              0,
              (__int64)Buffer);
        }
      }
      else
      {
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v44) = 0;
          Buffer[0] = 0;
          v28 = *((_DWORD *)this + 24);
          if ( v28 != -1 )
            _itow_s(v28, Buffer, 0x14u, 10);
          LODWORD(v32) = *((_DWORD *)this + 33);
          LODWORD(v31) = *((_DWORD *)this + 26);
          LODWORD(v30) = *((_DWORD *)this + 32);
          FormatRRASErrorString(
            &v44,
            L"%s: Removing device (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
            L"DdmModernDevice::CompleteClosing",
            *((_QWORD *)this + 12),
            v30,
            v31,
            v32);
          if ( (byte_1800C8404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v44,
              (unsigned int)&v35,
              0,
              (__int64)Buffer);
        }
        (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800C8670 + 16LL))(
          qword_1800C8670,
          DeviceObjRemoveFromTable,
          *((_QWORD *)this + 12),
          0);
        *((_DWORD *)this + 26) = 10;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_67;
    }
    if ( (*((_BYTE *)this + 132) & 8) != 0 )
      DdmDevice::LogDisconnectEvent(this, &v33);
    v34 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    DdmConnection::RemoveLink(v33, &v34);
    v8 = v33;
    if ( (*(_BYTE *)(v33 + 80) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(DdmModernDevice *, __int64 *))(*(_QWORD *)this + 696LL))(this, &v33);
      v8 = v33;
    }
    if ( *(_QWORD *)(v8 + 72) == -1 )
      goto LABEL_40;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
    v9 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                   g_pIDimInterfaceTable,
                                   *(_QWORD *)(v33 + 72));
    v10 = v9;
    if ( !v9 )
    {
LABEL_37:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
      v23 = (void *)*((_QWORD *)this + 1431);
      if ( v23 )
        SetEvent(v23);
      v8 = v33;
LABEL_40:
      if ( *(_DWORD *)(v8 + 144) )
        goto LABEL_49;
      v24 = (_QWORD *)(v8 + 1484);
      if ( v8 == -1484 )
        goto LABEL_44;
      if ( *v24 != *(_QWORD *)&GUID_NULL.Data1 )
        goto LABEL_48;
      if ( *(_QWORD *)(v8 + 1492) == *(_QWORD *)GUID_NULL.Data4 )
      {
LABEL_44:
        if ( !memcmp_0(&GUID_NULL, &GUID_NULL, 0x10u) )
          goto LABEL_49;
        if ( !v24 )
          goto LABEL_48;
      }
      if ( *v24 == *(_QWORD *)&GUID_NULL.Data1 && v24[1] == *(_QWORD *)GUID_NULL.Data4 )
      {
LABEL_49:
        v25 = DdmConnectionTable::GetInstance();
        DdmConnectionTable::RemoveConnection(v25, *((void **)this + 15));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(DdmModernDevice *, __int64))this)(this, 1);
        goto LABEL_51;
      }
LABEL_48:
      RasRdValidateAndUpdateVpnConnectionCount(v24, 0, 0);
      goto LABEL_49;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v9)(v9);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_34;
    LOWORD(v44) = 0;
    Buffer[0] = 0;
    v11 = *((_DWORD *)this + 24);
    if ( v11 != -1 )
      _itow_s(v11, Buffer, 0x14u, 10);
    v12 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v10 + 280LL))(v10);
    FormatRRASErrorString(&v44, L"CompleteClosing:Marking interface '%ws' DISCONNECTED.", v12);
    if ( (byte_1800C8404 & 8) == 0 )
    {
LABEL_34:
      InterfaceDisconnected(v10);
      v16 = (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v10 + 72LL))(v10) == 2;
      v20 = *(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v10 + 8LL);
      if ( v16 )
      {
        v20(v10);
      }
      else
      {
        v20(v10);
        v21 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 72LL);
        v22 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v10 + 16LL))(v10);
        v21(g_pIDimInterfaceTable, v22);
      }
      goto LABEL_37;
    }
    v13 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v10 + 280LL))(v10);
    v14 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v10 + 360LL))(v10, v36);
    v15 = v10;
    v16 = v14 == 0;
    v17 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v10 + 360LL);
    if ( v16 )
    {
      if ( !v17(v10, v38) )
      {
        v19 = &v35;
        goto LABEL_33;
      }
      v18 = &v39;
      v15 = v10;
      v17 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v10 + 360LL);
    }
    else
    {
      v18 = &v37;
    }
    LODWORD(v19) = v17(v15, v18);
LABEL_33:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v44,
      (_DWORD)v19,
      v13,
      (__int64)Buffer);
    goto LABEL_34;
  }
LABEL_67:
  v29 = (void (__fastcall ***)(_QWORD, __int64))v33;
  if ( v33 && _InterlockedExchangeAdd((volatile signed __int32 *)(v33 + 8), 0xFFFFFFFF) == 1 )
  {
    if ( v29 )
      (**v29)(v29, 1);
  }
}

```

## disassembly

```asm
0x18003dea0  mov     [rsp-8+arg_8], rbx
0x18003dea5  mov     [rsp-8+arg_10], rsi
0x18003deaa  push    rbp
0x18003deab  push    rdi
0x18003deac  push    r14
0x18003deae  lea     rbp, [rsp-7E0h]
0x18003deb6  sub     rsp, 8E0h
0x18003debd  mov     rax, cs:__security_cookie
0x18003dec4  xor     rax, rsp
0x18003dec7  mov     [rbp+7F0h+var_20], rax
0x18003dece  mov     rdi, rcx
0x18003ded1  mov     [rsp+8F0h+var_8B0], 0
0x18003deda  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18003dedf  lea     r8, [rsp+8F0h+var_8B0]
0x18003dee4  mov     rdx, [rdi+78h]
0x18003dee8  mov     rcx, rax
0x18003deeb  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18003def0  xor     eax, eax
0x18003def2  mov     [rbp+7F0h+var_820], eax
0x18003def5  xor     edx, edx; Val
0x18003def7  mov     r8d, 7FCh; Size
0x18003defd  lea     rcx, [rbp+7F0h+var_81C]; void *
0x18003df01  call    memset_0
0x18003df06  xor     eax, eax
0x18003df08  mov     dword ptr [rbp+7F0h+Buffer], eax
0x18003df0b  xorps   xmm0, xmm0
0x18003df0e  movups  [rbp+7F0h+var_84C], xmm0
0x18003df12  movups  [rbp+7F0h+var_83C], xmm0
0x18003df16  mov     [rbp+7F0h+var_82C], eax
0x18003df19  movups  [rsp+8F0h+var_8A0], xmm0
0x18003df1e  test    cs:byte_1800C8404, 10h
0x18003df25  jz      loc_18003DFBA
0x18003df2b  mov     word ptr [rbp+7F0h+var_820], ax
0x18003df2f  mov     [rbp+7F0h+Buffer], ax
0x18003df33  mov     ecx, [rdi+60h]; Value
0x18003df36  cmp     ecx, 0FFFFFFFFh
0x18003df39  jz      short loc_18003DF4D
0x18003df3b  lea     r9d, [rax+0Ah]; Radix
0x18003df3f  lea     r8d, [rax+14h]; BufferCount
0x18003df43  lea     rdx, [rbp+7F0h+Buffer]; Buffer
0x18003df47  call    cs:__imp__itow_s
0x18003df4d  mov     eax, [rdi+84h]
0x18003df53  mov     [rsp+8F0h+var_8C0], eax
0x18003df57  mov     eax, [rdi+68h]
0x18003df5a  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18003df5e  mov     eax, [rdi+80h]
0x18003df64  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18003df68  mov     r9, [rdi+60h]
0x18003df6c  lea     r8, aDdmmoderndevic_15; "DdmModernDevice::CompleteClosing"
0x18003df73  lea     rdx, aSHportLdConnec; "%s: (hport: %ld, ConnectionState: %d, d"...
0x18003df7a  lea     rcx, [rbp+7F0h+var_820]
0x18003df7e  call    FormatRRASErrorString
0x18003df83  test    cs:byte_1800C8404, 10h
0x18003df8a  jz      short loc_18003DFBA
0x18003df8c  lea     rax, [rbp+7F0h+Buffer]
0x18003df90  mov     [rsp+8F0h+var_8C8], rax
0x18003df95  mov     [rsp+8F0h+var_8D0], 0
0x18003df9e  lea     r9, [rsp+8F0h+var_8A0]
0x18003dfa3  lea     r8, [rbp+7F0h+var_820]
0x18003dfa7  lea     rdx, RasDdmParamTraceInfo
0x18003dfae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dfb5  call    McTemplateU0zjzz_EventWriteTransfer
0x18003dfba  xor     esi, esi
0x18003dfbc  mov     eax, [rdi+84h]
0x18003dfc2  mov     ebx, eax
0x18003dfc4  and     ebx, 4000h
0x18003dfca  bt      eax, 0Ch
0x18003dfce  jb      short loc_18003DFDD
0x18003dfd0  mov     esi, 1
0x18003dfd5  mov     rcx, rdi; this
0x18003dfd8  call    ?SendLinkDownToProtocolEngine@DdmModernDevice@@QEAAXXZ; DdmModernDevice::SendLinkDownToProtocolEngine(void)
0x18003dfdd  mov     r14d, [rdi+80h]
0x18003dfe4  test    cs:byte_1800C8404, 8
0x18003dfeb  jz      loc_18003E08A
0x18003dff1  xor     eax, eax
0x18003dff3  mov     word ptr [rbp+7F0h+var_820], ax
0x18003dff7  mov     [rbp+7F0h+Buffer], ax
0x18003dffb  mov     ecx, [rdi+60h]; Value
0x18003dffe  cmp     ecx, 0FFFFFFFFh
0x18003e001  jz      short loc_18003E015
0x18003e003  lea     r9d, [rax+0Ah]; Radix
0x18003e007  lea     r8d, [rax+14h]; BufferCount
0x18003e00b  lea     rdx, [rbp+7F0h+Buffer]; Buffer
0x18003e00f  call    cs:__imp__itow_s
0x18003e015  mov     edx, esi
0x18003e017  xor     edx, 1
0x18003e01a  mov     eax, [rdi+80h]
0x18003e020  xor     ecx, ecx
0x18003e022  cmp     [rsp+8F0h+var_8B0], rcx
0x18003e027  setz    cl
0x18003e02a  xor     r9d, r9d
0x18003e02d  test    ebx, ebx
0x18003e02f  setnz   r9b
0x18003e033  mov     [rsp+8F0h+var_8C0], edx
0x18003e037  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18003e03b  mov     dword ptr [rsp+8F0h+var_8D0], ecx
0x18003e03f  mov     r8, [rdi+60h]
0x18003e043  lea     rdx, aCompleteclosin; "CompleteClosing:hPort=%d,Auth=%d,Conn=%"...
0x18003e04a  lea     rcx, [rbp+7F0h+var_820]
0x18003e04e  call    FormatRRASErrorString
0x18003e053  test    cs:byte_1800C8404, 8
0x18003e05a  jz      short loc_18003E08A
0x18003e05c  lea     rax, [rbp+7F0h+Buffer]
0x18003e060  mov     [rsp+8F0h+var_8C8], rax
0x18003e065  mov     [rsp+8F0h+var_8D0], 0
0x18003e06e  lea     r9, [rsp+8F0h+var_8A0]
0x18003e073  lea     r8, [rbp+7F0h+var_820]
0x18003e077  lea     rdx, RasDdmParamTraceError
0x18003e07e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e085  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e08a  test    ebx, ebx
0x18003e08c  jnz     loc_18003E53E
0x18003e092  cmp     r14d, 4
0x18003e096  jnz     loc_18003E53E
0x18003e09c  test    esi, esi
0x18003e09e  jz      loc_18003E53E
0x18003e0a4  cmp     [rsp+8F0h+var_8B0], 0
0x18003e0aa  jz      loc_18003E37D
0x18003e0b0  test    byte ptr [rdi+84h], 8
0x18003e0b7  jz      short loc_18003E0C6
0x18003e0b9  lea     rdx, [rsp+8F0h+var_8B0]
0x18003e0be  mov     rcx, rdi
0x18003e0c1  call    ?LogDisconnectEvent@DdmDevice@@QEAAKAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmDevice::LogDisconnectEvent(RasObjPtr<DdmConnection> &)
0x18003e0c6  mov     [rsp+8F0h+var_8A8], rdi
0x18003e0cb  lock inc dword ptr [rdi+8]
0x18003e0cf  lea     rdx, [rsp+8F0h+var_8A8]
0x18003e0d4  mov     rcx, [rsp+8F0h+var_8B0]
0x18003e0d9  call    ?RemoveLink@DdmConnection@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmConnection::RemoveLink(RasObjPtr<DdmDevice> &)
0x18003e0de  mov     rax, [rsp+8F0h+var_8B0]
0x18003e0e3  test    byte ptr [rax+50h], 10h
0x18003e0e7  jz      short loc_18003E105
0x18003e0e9  mov     rax, [rdi]
0x18003e0ec  lea     rdx, [rsp+8F0h+var_8B0]
0x18003e0f1  mov     rcx, rdi
0x18003e0f4  mov     rax, [rax+2B8h]
0x18003e0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e100  mov     rax, [rsp+8F0h+var_8B0]
0x18003e105  cmp     qword ptr [rax+48h], 0FFFFFFFFFFFFFFFFh
0x18003e10a  jz      loc_18003E2E7
0x18003e110  mov     rcx, cs:g_pIDimInterfaceTable
0x18003e117  mov     rax, [rcx]
0x18003e11a  mov     rax, [rax+8]
0x18003e11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e123  mov     rcx, cs:g_pIDimInterfaceTable
0x18003e12a  mov     rax, [rcx]
0x18003e12d  mov     rdx, [rsp+8F0h+var_8B0]
0x18003e132  mov     rdx, [rdx+48h]
0x18003e136  mov     rax, [rax+40h]
0x18003e13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e13f  mov     rsi, rax
0x18003e142  test    rax, rax
0x18003e145  jz      loc_18003E2BD
0x18003e14b  mov     rcx, [rax]
0x18003e14e  mov     rax, [rcx]
0x18003e151  mov     rcx, rsi
0x18003e154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e159  test    cs:byte_1800C8404, 8
0x18003e160  jz      loc_18003E259
0x18003e166  xor     ecx, ecx
0x18003e168  mov     word ptr [rbp+7F0h+var_820], cx
0x18003e16c  xor     eax, eax
0x18003e16e  mov     [rbp+7F0h+Buffer], ax
0x18003e172  mov     ecx, [rdi+60h]; Value
0x18003e175  cmp     ecx, 0FFFFFFFFh
0x18003e178  jz      short loc_18003E18C
0x18003e17a  lea     r9d, [rax+0Ah]; Radix
0x18003e17e  lea     r8d, [rax+14h]; BufferCount
0x18003e182  lea     rdx, [rbp+7F0h+Buffer]; Buffer
0x18003e186  call    cs:__imp__itow_s
0x18003e18c  mov     rax, [rsi]
0x18003e18f  mov     rcx, rsi
0x18003e192  mov     rax, [rax+118h]
0x18003e199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e19e  mov     r8, rax
0x18003e1a1  lea     rdx, aCompleteclosin_0; "CompleteClosing:Marking interface '%ws'"...
0x18003e1a8  lea     rcx, [rbp+7F0h+var_820]
0x18003e1ac  call    FormatRRASErrorString
0x18003e1b1  test    cs:byte_1800C8404, 8
0x18003e1b8  jz      loc_18003E259
0x18003e1be  mov     rax, [rsi]
0x18003e1c1  mov     rcx, rsi
0x18003e1c4  mov     rax, [rax+118h]
0x18003e1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1d0  mov     rbx, rax
0x18003e1d3  mov     rcx, [rsi]
0x18003e1d6  mov     rax, [rcx+168h]
0x18003e1dd  lea     rdx, [rsp+8F0h+var_890]
0x18003e1e2  mov     rcx, rsi
0x18003e1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1ea  mov     rcx, [rsi]
0x18003e1ed  mov     r8, [rcx+168h]
0x18003e1f4  mov     rcx, rsi
0x18003e1f7  test    rax, rax
0x18003e1fa  mov     rax, r8
0x18003e1fd  jz      short loc_18003E206
0x18003e1ff  lea     rdx, [rsp+8F0h+var_880]
0x18003e204  jmp     short loc_18003E225
0x18003e206  lea     rdx, [rbp+7F0h+var_870]
0x18003e20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e20f  test    rax, rax
0x18003e212  jz      short loc_18003E22C
0x18003e214  mov     rax, [rsi]
0x18003e217  lea     rdx, [rbp+7F0h+var_860]
0x18003e21b  mov     rcx, rsi
0x18003e21e  mov     rax, [rax+168h]
0x18003e225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e22a  jmp     short loc_18003E231
0x18003e22c  lea     rax, [rsp+8F0h+var_8A0]
0x18003e231  lea     rcx, [rbp+7F0h+Buffer]
0x18003e235  mov     [rsp+8F0h+var_8C8], rcx
0x18003e23a  mov     [rsp+8F0h+var_8D0], rbx
0x18003e23f  mov     r9, rax
0x18003e242  lea     r8, [rbp+7F0h+var_820]
0x18003e246  lea     rdx, RasDdmParamTraceError
0x18003e24d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e254  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e259  mov     rcx, rsi; struct IDimInterface *
0x18003e25c  call    ?InterfaceDisconnected@@YAXPEAUIDimInterface@@@Z; InterfaceDisconnected(IDimInterface *)
0x18003e261  mov     rax, [rsi]
0x18003e264  mov     rcx, rsi
0x18003e267  mov     rax, [rax+48h]
0x18003e26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e270  mov     rcx, [rsi]
0x18003e273  mov     rdx, [rcx+8]
0x18003e277  mov     rcx, rsi
0x18003e27a  cmp     eax, 2
0x18003e27d  mov     rax, rdx
0x18003e280  jz      short loc_18003E2B8
0x18003e282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e287  mov     rax, cs:g_pIDimInterfaceTable
0x18003e28e  mov     rcx, [rax]
0x18003e291  mov     rbx, [rcx+48h]
0x18003e295  mov     rcx, [rsi]
0x18003e298  mov     rax, [rcx+10h]
0x18003e29c  mov     rcx, rsi
0x18003e29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2a4  mov     rdx, rax
0x18003e2a7  mov     rcx, cs:g_pIDimInterfaceTable
0x18003e2ae  mov     rax, rbx
0x18003e2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2b6  jmp     short loc_18003E2BD
0x18003e2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2bd  mov     rcx, cs:g_pIDimInterfaceTable
0x18003e2c4  mov     rax, [rcx]
0x18003e2c7  mov     rax, [rax+18h]
0x18003e2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2d0  mov     rcx, [rdi+2CB8h]; hEvent
0x18003e2d7  test    rcx, rcx
0x18003e2da  jz      short loc_18003E2E2
0x18003e2dc  call    cs:__imp_SetEvent
0x18003e2e2  mov     rax, [rsp+8F0h+var_8B0]
0x18003e2e7  cmp     dword ptr [rax+90h], 0
0x18003e2ee  jnz     short loc_18003E34B
0x18003e2f0  lea     rbx, [rax+5CCh]
0x18003e2f7  mov     r14, qword ptr cs:GUID_NULL.Data4
0x18003e2fe  mov     rsi, qword ptr cs:GUID_NULL.Data1
0x18003e305  test    rbx, rbx
0x18003e308  jz      short loc_18003E315
0x18003e30a  cmp     [rbx], rsi
0x18003e30d  jnz     short loc_18003E33E
0x18003e30f  cmp     [rbx+8], r14
0x18003e313  jnz     short loc_18003E333
0x18003e315  mov     r8d, 10h; Size
0x18003e31b  lea     rcx, GUID_NULL; Buf1
0x18003e322  mov     rdx, rcx; Buf2
0x18003e325  call    memcmp_0
0x18003e32a  test    eax, eax
0x18003e32c  jz      short loc_18003E34B
0x18003e32e  test    rbx, rbx
0x18003e331  jz      short loc_18003E33E
0x18003e333  cmp     [rbx], rsi
0x18003e336  jnz     short loc_18003E33E
0x18003e338  cmp     [rbx+8], r14
0x18003e33c  jz      short loc_18003E34B
0x18003e33e  xor     r8d, r8d
0x18003e341  xor     edx, edx
0x18003e343  mov     rcx, rbx
0x18003e346  call    RasRdValidateAndUpdateVpnConnectionCount
0x18003e34b  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18003e350  mov     rdx, [rdi+78h]; void *
0x18003e354  mov     rcx, rax; this
0x18003e357  call    ?RemoveConnection@DdmConnectionTable@@QEAAXPEAX@Z; DdmConnectionTable::RemoveConnection(void *)
0x18003e35c  nop
0x18003e35d  or      eax, 0FFFFFFFFh
0x18003e360  lock xadd [rdi+8], eax
0x18003e365  cmp     eax, 1
0x18003e368  jnz     short loc_18003E37D
0x18003e36a  mov     rax, [rdi]
0x18003e36d  mov     edx, 1
0x18003e372  mov     rcx, rdi
0x18003e375  mov     rax, [rax]
0x18003e378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e37d  mov     eax, [rdi+84h]
0x18003e383  or      esi, 0FFFFFFFFh
0x18003e386  test    al, 8
0x18003e388  jz      short loc_18003E3AE
0x18003e38a  and     eax, 0FFFFFFF7h
0x18003e38d  mov     [rdi+84h], eax
0x18003e393  add     cs:dword_1800C84B0, esi
0x18003e399  test    byte ptr [rdi+84h], 40h
  ... truncated ...
```
