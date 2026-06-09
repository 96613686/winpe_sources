# DdmModernDevice::CompleteClosing(void)

- ea: `0x18003f7c0`
- end: `0x18003fe53`
- name: `?CompleteClosing@DdmModernDevice@@UEAAXXZ`
- size: `1683`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007d00`
- `0x180008efc`
- `0x18000ad58`
- `0x18002f2ec`
- `0x1800304dc`
- `0x180030684`
- `0x1800306c4`
- `0x180037d88`
- `0x18003f7c0`
- `0x1800459d0`
- `0x18005ab8c`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18003fbd0`
- `KERNEL32!SetEvent` at `0x18003fbd0`
- `KERNEL32!LeaveCriticalSection` at `0x18003fded`
- `KERNEL32!LeaveCriticalSection` at `0x18003fded`
- `KERNEL32!EnterCriticalSection` at `0x18003fc88`
- `KERNEL32!EnterCriticalSection` at `0x18003fc88`

## string_xrefs

- `0x18003fa95`: `CompleteClosing:Marking interface '%ws' DISCONNECTED.`
- `0x18003f883`: `DdmModernDevice::CompleteClosing`
- `0x18003fce6`: `DdmModernDevice::CompleteClosing`
- `0x18003fd77`: `DdmModernDevice::CompleteClosing`
- `0x18003f947`: `CompleteClosing:hPort=%d,Auth=%d,Conn=%d %d,Protocol=%d`

## pseudocode

```c
void __fastcall DdmModernDevice::CompleteClosing(DdmModernDevice *this)
{
  int v2; // esi
  struct DdmConnectionTable *Instance; // rax
  int v4; // ebx
  int v5; // r14d
  __int64 v6; // rax
  struct IDimInterface *v7; // rax
  struct IDimInterface *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  struct IDimInterface *v12; // rcx
  bool v13; // zf
  __int64 (__fastcall *v14)(struct IDimInterface *, char *); // rax
  char *v15; // rdx
  _QWORD *v16; // rax
  void (__fastcall *v17)(struct IDimInterface *); // rax
  void (__fastcall *v18)(__int64, __int64); // rbx
  __int64 v19; // rax
  void *v20; // rcx
  _QWORD *v21; // rcx
  DdmConnectionTable *v22; // rax
  int v23; // eax
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  __int64 v25; // [rsp+28h] [rbp-E0h]
  __int64 v26; // [rsp+30h] [rbp-D8h]
  __int64 v27; // [rsp+38h] [rbp-D0h]
  __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v29[3]; // [rsp+50h] [rbp-B8h] BYREF
  char v30[16]; // [rsp+68h] [rbp-A0h] BYREF
  char v31; // [rsp+78h] [rbp-90h] BYREF
  char v32[16]; // [rsp+88h] [rbp-80h] BYREF
  char v33; // [rsp+98h] [rbp-70h] BYREF
  int v34; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v35; // [rsp+ACh] [rbp-5Ch]
  __int128 v36; // [rsp+BCh] [rbp-4Ch]
  int v37; // [rsp+CCh] [rbp-3Ch]
  int v38; // [rsp+D8h] [rbp-30h] BYREF
  char v39[2044]; // [rsp+DCh] [rbp-2Ch] BYREF

  v2 = 0;
  v28 = 0;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v28);
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  *(_OWORD *)&v29[1] = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    ConvertPortNoToString(&v34, *((unsigned int *)this + 24));
    FormatRRASErrorString(
      &v38,
      L"%s: (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
      L"DdmModernDevice::CompleteClosing",
      *((_QWORD *)this + 12),
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 26),
      *((_DWORD *)this + 33));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v38,
        (unsigned int)&v29[1],
        0,
        (__int64)&v34);
  }
  v4 = *((_DWORD *)this + 33) & 0x4000;
  if ( (*((_DWORD *)this + 33) & 0x1000) == 0 )
  {
    v2 = 1;
    DdmModernDevice::SendLinkDownToProtocolEngine(this);
  }
  v5 = *((_DWORD *)this + 32);
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    ConvertPortNoToString(&v34, *((unsigned int *)this + 24));
    LODWORD(v27) = v2 ^ 1;
    LODWORD(v26) = *((_DWORD *)this + 32);
    LODWORD(v25) = v28 == 0;
    FormatRRASErrorString(
      &v38,
      L"CompleteClosing:hPort=%d,Auth=%d,Conn=%d %d,Protocol=%d",
      *((_QWORD *)this + 12),
      v4 != 0,
      v25,
      v26,
      v27);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v38,
        (unsigned int)&v29[1],
        0,
        (__int64)&v34);
  }
  if ( !v4 && v5 == 4 && v2 )
  {
    if ( !v28 )
    {
LABEL_45:
      v23 = *((_DWORD *)this + 33);
      if ( (v23 & 8) != 0 )
      {
        *((_DWORD *)this + 33) = v23 & 0xFFFFFFF7;
        --dword_1800CF4B0;
        if ( (*((_BYTE *)this + 132) & 0x40) != 0 )
          MediaObjAddToTable((STRSAFE_LPCWSTR)this + 391);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      if ( (*((_DWORD *)this + 33) & 0x200000) != 0 )
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v38) = 0;
          LOWORD(v34) = 0;
          ConvertPortNoToString(&v34, *((unsigned int *)this + 24));
          LODWORD(v27) = *((_DWORD *)this + 33);
          LODWORD(v26) = *((_DWORD *)this + 26);
          LODWORD(v25) = *((_DWORD *)this + 32);
          FormatRRASErrorString(
            &v38,
            L"%s: Skip removing device due to active routes (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
            L"DdmModernDevice::CompleteClosing",
            *((_QWORD *)this + 12),
            v25,
            v26,
            v27);
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v38,
              (unsigned int)&v29[1],
              0,
              (__int64)&v34);
        }
      }
      else
      {
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v38) = 0;
          LOWORD(v34) = 0;
          ConvertPortNoToString(&v34, *((unsigned int *)this + 24));
          LODWORD(v27) = *((_DWORD *)this + 33);
          LODWORD(v26) = *((_DWORD *)this + 26);
          LODWORD(v25) = *((_DWORD *)this + 32);
          FormatRRASErrorString(
            &v38,
            L"%s: Removing device (hport: %ld, ConnectionState: %d, devState: %d, flags: 0x%x)",
            L"DdmModernDevice::CompleteClosing",
            *((_QWORD *)this + 12),
            v25,
            v26,
            v27);
          if ( (byte_1800CF404 & 0x10) != 0 )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceInfo,
              (unsigned int)&v38,
              (unsigned int)&v29[1],
              0,
              (__int64)&v34);
        }
        (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800CF670 + 16LL))(
          qword_1800CF670,
          DeviceObjRemoveFromTable,
          *((_QWORD *)this + 12),
          0);
        *((_DWORD *)this + 26) = 10;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_57;
    }
    if ( (*((_BYTE *)this + 132) & 8) != 0 )
      DdmDevice::LogDisconnectEvent(this, &v28);
    v29[0] = this;
    if ( this )
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
    DdmConnection::RemoveLink(v28, v29);
    v6 = v28;
    if ( (*(_BYTE *)(v28 + 80) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(DdmModernDevice *, __int64 *))(*(_QWORD *)this + 696LL))(this, &v28);
      v6 = v28;
    }
    if ( *(_QWORD *)(v6 + 72) == -1 )
    {
LABEL_36:
      if ( !*(_DWORD *)(v6 + 144) )
      {
        v21 = (_QWORD *)(v6 + 1484);
        if ( v6 != -1484
          && (*v21 != *(_QWORD *)&GUID_NULL.Data1
           || *(_QWORD *)(v6 + 1492) != *(_QWORD *)GUID_NULL.Data4
           && (*v21 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)(v6 + 1492) != *(_QWORD *)GUID_NULL.Data4)) )
        {
          RasRdValidateAndUpdateVpnConnectionCount(v21, 0, 0);
        }
      }
      v22 = DdmConnectionTable::GetInstance();
      DdmConnectionTable::RemoveConnection(v22, *((void **)this + 15));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(DdmModernDevice *, __int64))this)(this, 1);
      goto LABEL_45;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
    v7 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                   g_pIDimInterfaceTable,
                                   *(_QWORD *)(v28 + 72));
    v8 = v7;
    if ( !v7 )
    {
LABEL_33:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
      v20 = (void *)*((_QWORD *)this + 1431);
      if ( v20 )
        SetEvent(v20);
      v6 = v28;
      goto LABEL_36;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v7)(v7);
    if ( (byte_1800CF404 & 8) == 0
      || (LOWORD(v38) = 0,
          LOWORD(v34) = 0,
          ConvertPortNoToString(&v34, *((unsigned int *)this + 24)),
          v9 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v8 + 280LL))(v8),
          FormatRRASErrorString(&v38, L"CompleteClosing:Marking interface '%ws' DISCONNECTED.", v9),
          (byte_1800CF404 & 8) == 0) )
    {
LABEL_30:
      InterfaceDisconnected(v8);
      v13 = (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v8 + 72LL))(v8) == 2;
      v17 = *(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v8 + 8LL);
      if ( v13 )
      {
        v17(v8);
      }
      else
      {
        v17(v8);
        v18 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 72LL);
        v19 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v8 + 16LL))(v8);
        v18(g_pIDimInterfaceTable, v19);
      }
      goto LABEL_33;
    }
    v10 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v8 + 280LL))(v8);
    v11 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v8 + 360LL))(v8, v30);
    v12 = v8;
    v13 = v11 == 0;
    v14 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v8 + 360LL);
    if ( v13 )
    {
      if ( !v14(v8, v32) )
      {
        v16 = &v29[1];
        goto LABEL_29;
      }
      v15 = &v33;
      v12 = v8;
      v14 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v8 + 360LL);
    }
    else
    {
      v15 = &v31;
    }
    LODWORD(v16) = v14(v12, v15);
LABEL_29:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v38,
      (_DWORD)v16,
      v10,
      (__int64)&v34);
    goto LABEL_30;
  }
LABEL_57:
  v24 = (void (__fastcall ***)(_QWORD, __int64))v28;
  if ( v28 && _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 8), 0xFFFFFFFF) == 1 )
  {
    if ( v24 )
      (**v24)(v24, 1);
  }
}

```

## disassembly

```asm
0x18003f7c0  mov     rax, rsp
0x18003f7c3  mov     [rax+10h], rbx
0x18003f7c7  mov     [rax+18h], rsi
0x18003f7cb  mov     [rax+20h], rdi
0x18003f7cf  push    rbp
0x18003f7d0  push    r14
0x18003f7d2  push    r15
0x18003f7d4  lea     rbp, [rax-7F8h]
0x18003f7db  sub     rsp, 8E0h
0x18003f7e2  mov     rax, cs:__security_cookie
0x18003f7e9  xor     rax, rsp
0x18003f7ec  mov     [rbp+7F0h+var_20], rax
0x18003f7f3  mov     rdi, rcx
0x18003f7f6  xor     r15d, r15d
0x18003f7f9  mov     esi, r15d
0x18003f7fc  mov     [rsp+8F0h+var_8B0], r15
0x18003f801  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18003f806  lea     r8, [rsp+8F0h+var_8B0]
0x18003f80b  mov     rdx, [rdi+78h]
0x18003f80f  mov     rcx, rax
0x18003f812  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18003f817  mov     [rbp+7F0h+var_820], r15d
0x18003f81b  xor     edx, edx; Val
0x18003f81d  mov     r8d, 7FCh; Size
0x18003f823  lea     rcx, [rbp+7F0h+var_81C]; void *
0x18003f827  call    memset_0
0x18003f82c  mov     [rbp+7F0h+var_850], r15d
0x18003f830  xorps   xmm0, xmm0
0x18003f833  xor     eax, eax
0x18003f835  movups  [rbp+7F0h+var_84C], xmm0
0x18003f839  movups  [rbp+7F0h+var_83C], xmm0
0x18003f83d  mov     [rbp+7F0h+var_82C], eax
0x18003f840  movups  xmmword ptr [rsp+8F0h+var_8A8+8], xmm0
0x18003f845  test    cs:byte_1800CF404, 10h
0x18003f84c  jz      short loc_18003F8CD
0x18003f84e  mov     word ptr [rbp+7F0h+var_820], r15w
0x18003f853  mov     word ptr [rbp+7F0h+var_850], r15w
0x18003f858  mov     edx, [rdi+60h]
0x18003f85b  lea     rcx, [rbp+7F0h+var_850]
0x18003f85f  call    ConvertPortNoToString
0x18003f864  mov     eax, [rdi+84h]
0x18003f86a  mov     [rsp+8F0h+var_8C0], eax
0x18003f86e  mov     eax, [rdi+68h]
0x18003f871  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18003f875  mov     eax, [rdi+80h]
0x18003f87b  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18003f87f  mov     r9, [rdi+60h]
0x18003f883  lea     r8, aDdmmoderndevic_15; "DdmModernDevice::CompleteClosing"
0x18003f88a  lea     rdx, aSHportLdConnec; "%s: (hport: %ld, ConnectionState: %d, d"...
0x18003f891  lea     rcx, [rbp+7F0h+var_820]
0x18003f895  call    FormatRRASErrorString
0x18003f89a  test    cs:byte_1800CF404, 10h
0x18003f8a1  jz      short loc_18003F8CD
0x18003f8a3  lea     rax, [rbp+7F0h+var_850]
0x18003f8a7  mov     [rsp+8F0h+var_8C8], rax
0x18003f8ac  mov     [rsp+8F0h+var_8D0], r15
0x18003f8b1  lea     r9, [rsp+8F0h+var_8A8+8]
0x18003f8b6  lea     r8, [rbp+7F0h+var_820]
0x18003f8ba  lea     rdx, RasDdmParamTraceInfo
0x18003f8c1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003f8c8  call    McTemplateU0zjzz_EventWriteTransfer
0x18003f8cd  mov     eax, [rdi+84h]
0x18003f8d3  mov     ebx, eax
0x18003f8d5  and     ebx, 4000h
0x18003f8db  bt      eax, 0Ch
0x18003f8df  jb      short loc_18003F8EE
0x18003f8e1  mov     esi, 1
0x18003f8e6  mov     rcx, rdi; this
0x18003f8e9  call    ?SendLinkDownToProtocolEngine@DdmModernDevice@@QEAAXXZ; DdmModernDevice::SendLinkDownToProtocolEngine(void)
0x18003f8ee  mov     r14d, [rdi+80h]
0x18003f8f5  test    cs:byte_1800CF404, 8
0x18003f8fc  jz      loc_18003F98A
0x18003f902  mov     word ptr [rbp+7F0h+var_820], r15w
0x18003f907  mov     word ptr [rbp+7F0h+var_850], r15w
0x18003f90c  mov     edx, [rdi+60h]
0x18003f90f  lea     rcx, [rbp+7F0h+var_850]
0x18003f913  call    ConvertPortNoToString
0x18003f918  mov     edx, esi
0x18003f91a  xor     edx, 1
0x18003f91d  mov     eax, [rdi+80h]
0x18003f923  mov     ecx, r15d
0x18003f926  cmp     [rsp+8F0h+var_8B0], r15
0x18003f92b  setz    cl
0x18003f92e  mov     r9d, r15d
0x18003f931  test    ebx, ebx
0x18003f933  setnz   r9b
0x18003f937  mov     [rsp+8F0h+var_8C0], edx
0x18003f93b  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18003f93f  mov     dword ptr [rsp+8F0h+var_8D0], ecx
0x18003f943  mov     r8, [rdi+60h]
0x18003f947  lea     rdx, aCompleteclosin; "CompleteClosing:hPort=%d,Auth=%d,Conn=%"...
0x18003f94e  lea     rcx, [rbp+7F0h+var_820]
0x18003f952  call    FormatRRASErrorString
0x18003f957  test    cs:byte_1800CF404, 8
0x18003f95e  jz      short loc_18003F98A
0x18003f960  lea     rax, [rbp+7F0h+var_850]
0x18003f964  mov     [rsp+8F0h+var_8C8], rax
0x18003f969  mov     [rsp+8F0h+var_8D0], r15
0x18003f96e  lea     r9, [rsp+8F0h+var_8A8+8]
0x18003f973  lea     r8, [rbp+7F0h+var_820]
0x18003f977  lea     rdx, RasDdmParamTraceError
0x18003f97e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003f985  call    McTemplateU0zjzz_EventWriteTransfer
0x18003f98a  test    ebx, ebx
0x18003f98c  jnz     loc_18003FDFA
0x18003f992  cmp     r14d, 4
0x18003f996  jnz     loc_18003FDFA
0x18003f99c  test    esi, esi
0x18003f99e  jz      loc_18003FDFA
0x18003f9a4  cmp     [rsp+8F0h+var_8B0], r15
0x18003f9a9  jz      loc_18003FC56
0x18003f9af  test    byte ptr [rdi+84h], 8
0x18003f9b6  jz      short loc_18003F9C5
0x18003f9b8  lea     rdx, [rsp+8F0h+var_8B0]
0x18003f9bd  mov     rcx, rdi
0x18003f9c0  call    ?LogDisconnectEvent@DdmDevice@@QEAAKAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmDevice::LogDisconnectEvent(RasObjPtr<DdmConnection> &)
0x18003f9c5  mov     qword ptr [rsp+8F0h+var_8A8], rdi
0x18003f9ca  test    rdi, rdi
0x18003f9cd  jz      short loc_18003F9D3
0x18003f9cf  lock inc dword ptr [rdi+8]
0x18003f9d3  lea     rdx, [rsp+8F0h+var_8A8]
0x18003f9d8  mov     rcx, [rsp+8F0h+var_8B0]
0x18003f9dd  call    ?RemoveLink@DdmConnection@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmConnection::RemoveLink(RasObjPtr<DdmDevice> &)
0x18003f9e2  mov     rax, [rsp+8F0h+var_8B0]
0x18003f9e7  test    byte ptr [rax+50h], 10h
0x18003f9eb  jz      short loc_18003FA09
0x18003f9ed  mov     rax, [rdi]
0x18003f9f0  lea     rdx, [rsp+8F0h+var_8B0]
0x18003f9f5  mov     rcx, rdi
0x18003f9f8  mov     rax, [rax+2B8h]
0x18003f9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa04  mov     rax, [rsp+8F0h+var_8B0]
0x18003fa09  cmp     qword ptr [rax+48h], 0FFFFFFFFFFFFFFFFh
0x18003fa0e  jz      loc_18003FBE1
0x18003fa14  mov     rcx, cs:g_pIDimInterfaceTable
0x18003fa1b  mov     rax, [rcx]
0x18003fa1e  mov     rax, [rax+8]
0x18003fa22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa27  mov     rcx, cs:g_pIDimInterfaceTable
0x18003fa2e  mov     rax, [rcx]
0x18003fa31  mov     rdx, [rsp+8F0h+var_8B0]
0x18003fa36  mov     rdx, [rdx+48h]
0x18003fa3a  mov     rax, [rax+40h]
0x18003fa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa43  mov     rsi, rax
0x18003fa46  test    rax, rax
0x18003fa49  jz      loc_18003FBB1
0x18003fa4f  mov     rcx, [rax]
0x18003fa52  mov     rax, [rcx]
0x18003fa55  mov     rcx, rsi
0x18003fa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa5d  test    cs:byte_1800CF404, 8
0x18003fa64  jz      loc_18003FB4D
0x18003fa6a  mov     word ptr [rbp+7F0h+var_820], r15w
0x18003fa6f  mov     word ptr [rbp+7F0h+var_850], r15w
0x18003fa74  mov     edx, [rdi+60h]
0x18003fa77  lea     rcx, [rbp+7F0h+var_850]
0x18003fa7b  call    ConvertPortNoToString
0x18003fa80  mov     rax, [rsi]
0x18003fa83  mov     rcx, rsi
0x18003fa86  mov     rax, [rax+118h]
0x18003fa8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa92  mov     r8, rax
0x18003fa95  lea     rdx, aCompleteclosin_0; "CompleteClosing:Marking interface '%ws'"...
0x18003fa9c  lea     rcx, [rbp+7F0h+var_820]
0x18003faa0  call    FormatRRASErrorString
0x18003faa5  test    cs:byte_1800CF404, 8
0x18003faac  jz      loc_18003FB4D
0x18003fab2  mov     rax, [rsi]
0x18003fab5  mov     rcx, rsi
0x18003fab8  mov     rax, [rax+118h]
0x18003fabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fac4  mov     rbx, rax
0x18003fac7  mov     rcx, [rsi]
0x18003faca  mov     rax, [rcx+168h]
0x18003fad1  lea     rdx, [rsp+8F0h+var_890]
0x18003fad6  mov     rcx, rsi
0x18003fad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fade  mov     rcx, [rsi]
0x18003fae1  mov     r8, [rcx+168h]
0x18003fae8  mov     rcx, rsi
0x18003faeb  test    rax, rax
0x18003faee  mov     rax, r8
0x18003faf1  jz      short loc_18003FAFA
0x18003faf3  lea     rdx, [rsp+8F0h+var_880]
0x18003faf8  jmp     short loc_18003FB19
0x18003fafa  lea     rdx, [rbp+7F0h+var_870]
0x18003fafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb03  test    rax, rax
0x18003fb06  jz      short loc_18003FB20
0x18003fb08  mov     rax, [rsi]
0x18003fb0b  lea     rdx, [rbp+7F0h+var_860]
0x18003fb0f  mov     rcx, rsi
0x18003fb12  mov     rax, [rax+168h]
0x18003fb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb1e  jmp     short loc_18003FB25
0x18003fb20  lea     rax, [rsp+8F0h+var_8A8+8]
0x18003fb25  lea     rcx, [rbp+7F0h+var_850]
0x18003fb29  mov     [rsp+8F0h+var_8C8], rcx
0x18003fb2e  mov     [rsp+8F0h+var_8D0], rbx
0x18003fb33  mov     r9, rax
0x18003fb36  lea     r8, [rbp+7F0h+var_820]
0x18003fb3a  lea     rdx, RasDdmParamTraceError
0x18003fb41  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003fb48  call    McTemplateU0zjzz_EventWriteTransfer
0x18003fb4d  mov     rcx, rsi; struct IDimInterface *
0x18003fb50  call    ?InterfaceDisconnected@@YAXPEAUIDimInterface@@@Z; InterfaceDisconnected(IDimInterface *)
0x18003fb55  mov     rax, [rsi]
0x18003fb58  mov     rcx, rsi
0x18003fb5b  mov     rax, [rax+48h]
0x18003fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb64  mov     rcx, [rsi]
0x18003fb67  mov     rdx, [rcx+8]
0x18003fb6b  mov     rcx, rsi
0x18003fb6e  cmp     eax, 2
0x18003fb71  mov     rax, rdx
0x18003fb74  jz      short loc_18003FBAC
0x18003fb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb7b  mov     rax, cs:g_pIDimInterfaceTable
0x18003fb82  mov     rcx, [rax]
0x18003fb85  mov     rbx, [rcx+48h]
0x18003fb89  mov     rcx, [rsi]
0x18003fb8c  mov     rax, [rcx+10h]
0x18003fb90  mov     rcx, rsi
0x18003fb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb98  mov     rdx, rax
0x18003fb9b  mov     rcx, cs:g_pIDimInterfaceTable
0x18003fba2  mov     rax, rbx
0x18003fba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbaa  jmp     short loc_18003FBB1
0x18003fbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbb1  mov     rcx, cs:g_pIDimInterfaceTable
0x18003fbb8  mov     rax, [rcx]
0x18003fbbb  mov     rax, [rax+18h]
0x18003fbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbc4  mov     rcx, [rdi+2CB8h]; hEvent
0x18003fbcb  test    rcx, rcx
0x18003fbce  jz      short loc_18003FBDC
0x18003fbd0  call    cs:__imp_SetEvent
0x18003fbd7  nop     dword ptr [rax+rax+00h]
0x18003fbdc  mov     rax, [rsp+8F0h+var_8B0]
0x18003fbe1  cmp     [rax+90h], r15d
0x18003fbe8  jnz     short loc_18003FC24
0x18003fbea  lea     rcx, [rax+5CCh]
0x18003fbf1  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x18003fbf8  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18003fbff  test    rcx, rcx
0x18003fc02  jz      short loc_18003FC24
0x18003fc04  cmp     [rcx], rax
0x18003fc07  jnz     short loc_18003FC1A
0x18003fc09  cmp     [rcx+8], rdx
0x18003fc0d  jz      short loc_18003FC24
0x18003fc0f  cmp     [rcx], rax
0x18003fc12  jnz     short loc_18003FC1A
0x18003fc14  cmp     [rcx+8], rdx
0x18003fc18  jz      short loc_18003FC24
0x18003fc1a  xor     r8d, r8d
0x18003fc1d  xor     edx, edx
0x18003fc1f  call    RasRdValidateAndUpdateVpnConnectionCount
0x18003fc24  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18003fc29  mov     rdx, [rdi+78h]; void *
0x18003fc2d  mov     rcx, rax; this
0x18003fc30  call    ?RemoveConnection@DdmConnectionTable@@QEAAXPEAX@Z; DdmConnectionTable::RemoveConnection(void *)
0x18003fc35  nop
0x18003fc36  or      eax, 0FFFFFFFFh
0x18003fc39  lock xadd [rdi+8], eax
0x18003fc3e  cmp     eax, 1
0x18003fc41  jnz     short loc_18003FC56
0x18003fc43  mov     rax, [rdi]
0x18003fc46  mov     edx, 1
0x18003fc4b  mov     rcx, rdi
0x18003fc4e  mov     rax, [rax]
0x18003fc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc56  mov     eax, [rdi+84h]
0x18003fc5c  test    al, 8
0x18003fc5e  jz      short loc_18003FC84
0x18003fc60  and     eax, 0FFFFFFF7h
0x18003fc63  mov     [rdi+84h], eax
0x18003fc69  dec     cs:dword_1800CF4B0
0x18003fc6f  test    byte ptr [rdi+84h], 40h
0x18003fc76  jz      short loc_18003FC84
0x18003fc78  lea     rcx, [rdi+30Eh]; pszSrc
0x18003fc7f  call    ?MediaObjAddToTable@@YAKPEAG@Z; MediaObjAddToTable(ushort *)
0x18003fc84  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003fc88  call    cs:__imp_EnterCriticalSection
0x18003fc8f  nop     dword ptr [rax+rax+00h]
0x18003fc94  test    dword ptr [rdi+84h], 200000h
0x18003fc9e  jz      loc_18003FD39
0x18003fca4  test    cs:byte_1800CF404, 10h
0x18003fcab  jz      loc_18003FDE9
0x18003fcb1  mov     word ptr [rbp+7F0h+var_820], r15w
0x18003fcb6  mov     word ptr [rbp+7F0h+var_850], r15w
0x18003fcbb  mov     edx, [rdi+60h]
0x18003fcbe  lea     rcx, [rbp+7F0h+var_850]
0x18003fcc2  call    ConvertPortNoToString
0x18003fcc7  mov     eax, [rdi+84h]
0x18003fccd  mov     [rsp+8F0h+var_8C0], eax
0x18003fcd1  mov     eax, [rdi+68h]
0x18003fcd4  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18003fcd8  mov     eax, [rdi+80h]
  ... truncated ...
```
