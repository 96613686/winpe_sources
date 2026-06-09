# DdmLegacyDevice::CompleteClosing(void)

- ea: `0x180029a40`
- end: `0x18002a1f0`
- name: `?CompleteClosing@DdmLegacyDevice@@UEAAXXZ`
- size: `1968`
- prototype: `void __fastcall(DdmLegacyDevice *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002bbe`
- `0x180007b7c`
- `0x180007c50`
- `0x180008e08`
- `0x18000aae0`
- `0x180029a40`
- `0x18002d0c4`
- `0x18002e0ec`
- `0x18002e268`
- `0x18002e2a8`
- `0x180033fb0`
- `0x180034168`
- `0x180036248`
- `0x180058c2c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180029b33`
- `msvcrt!_itow_s` at `0x180029e1c`
- `msvcrt!_itow_s` at `0x180029b33`
- `msvcrt!_itow_s` at `0x180029e1c`
- `KERNEL32!LeaveCriticalSection` at `0x18002a174`
- `KERNEL32!LeaveCriticalSection` at `0x18002a174`
- `KERNEL32!EnterCriticalSection` at `0x18002a163`
- `KERNEL32!EnterCriticalSection` at `0x18002a163`
- `rasman!RasFreeBuffer` at `0x18002a044`
- `rasman!RasFreeBuffer` at `0x18002a05d`
- `rasman!RasFreeBuffer` at `0x18002a044`
- `rasman!RasFreeBuffer` at `0x18002a05d`
- `rasman!RasBundleGetPort` at `0x180029d53`
- `rasman!RasBundleGetPort` at `0x180029d53`

## string_xrefs

- `0x180029b94`: `CompleteClosing:hPort=%d,Auth=%d,Rcv=%d,Conn=%d %d,Sec=%d %d,Protocol=%d`
- `0x180029ce1`: `CompleteClosing: Skipping version 1 Admin Dll callback for IKEv2 connection`
- `0x180029e37`: `CompleteClosing:Marking interface '%ws' DISCONNECTED.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DdmLegacyDevice::CompleteClosing(DdmLegacyDevice *this)
{
  struct DdmConnectionTable *Instance; // rax
  int v3; // r13d
  int v4; // esi
  int v5; // r14d
  int v6; // ebx
  int v7; // r15d
  int v8; // r12d
  int v9; // ecx
  __int64 v10; // r8
  unsigned int i; // ebx
  __int64 v12; // rcx
  void (__fastcall *v13)(_RAS_PORT_0 *, _RAS_PORT_1 *); // rax
  __int64 v14; // rax
  struct IDimInterface *v15; // rax
  struct IDimInterface *v16; // rsi
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  struct IDimInterface *v21; // rcx
  bool v22; // zf
  __int64 (__fastcall *v23)(struct IDimInterface *, char *); // rax
  struct _EVENT_DATA_DESCRIPTOR *v24; // rdx
  __int128 *v25; // rax
  void (__fastcall *v26)(struct IDimInterface *); // rax
  void (__fastcall *v27)(__int64, __int64); // rbx
  __int64 v28; // rax
  _QWORD *v29; // rbx
  DdmConnectionTable *v30; // rax
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rcx
  const wchar_t *v34; // r8
  __int64 v35; // rdx
  wchar_t *v36; // rax
  wchar_t v37; // r9
  wchar_t *v38; // rcx
  __int64 v39; // rdx
  void (__fastcall ***v40)(_QWORD, __int64); // rcx
  _QWORD v41[2]; // [rsp+50h] [rbp-B0h] BYREF
  DdmLegacyDevice *v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  _RAS_PORT_1 v44; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-40h] BYREF
  char v46[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+E0h] [rbp-20h] BYREF
  char v48[16]; // [rsp+F0h] [rbp-10h] BYREF
  _RAS_PORT_0 v49; // [rsp+100h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+290h] [rbp+190h] BYREF
  const wchar_t *v51; // [rsp+2A0h] [rbp+1A0h]
  __int64 v52; // [rsp+2A8h] [rbp+1A8h]
  wchar_t Buffer[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v54; // [rsp+2B4h] [rbp+1B4h]
  __int128 v55; // [rsp+2C4h] [rbp+1C4h]
  int v56; // [rsp+2D4h] [rbp+1D4h]
  int v57; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v58[2044]; // [rsp+2E4h] [rbp+1E4h] BYREF

  v41[0] = 0;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), v41);
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  *(_DWORD *)Buffer = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v45 = 0;
  v3 = *((_DWORD *)this + 34);
  v4 = *((_DWORD *)this + 33) & 0x4000;
  v5 = *((_DWORD *)this + 33) & 0x2000;
  v6 = *((_DWORD *)this + 33) & 0x1000;
  v7 = *((_DWORD *)this + 32);
  v8 = *((_DWORD *)this + 300);
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v57) = 0;
    Buffer[0] = 0;
    v9 = *((_DWORD *)this + 24);
    if ( v9 != -1 )
      _itow_s(v9, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v57,
      L"CompleteClosing:hPort=%d,Auth=%d,Rcv=%d,Conn=%d %d,Sec=%d %d,Protocol=%d",
      *((_QWORD *)this + 12),
      v4 != 0,
      v5 != 0,
      v41[0] == 0,
      v7 != 4,
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 300),
      v6 != 0);
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v57,
        (unsigned int)&v45,
        0,
        (__int64)Buffer);
  }
  if ( v4 || v5 || v7 != 4 || v8 != 2 || v6 )
    goto LABEL_80;
  if ( (*((_BYTE *)this + 132) & 8) != 0 )
    DdmDevice::LogDisconnectEvent(this, v41);
  if ( v41[0] )
  {
    v43 = 0;
    v42 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    DdmConnection::RemoveLink(v41[0], &v42);
    if ( (*((_BYTE *)this + 132) & 0x20) != 0 )
    {
      memset_0(&v49, 0, sizeof(v49));
      memset_0(&v44, 0, sizeof(v44));
      if ( !DdmDevice::GetRasPortData(this, &v49) && !DdmDevice::GetRasPortData(this, &v44) )
      {
        for ( i = 0; i < dword_1800C8568; ++i )
        {
          v12 = 168LL * i;
          if ( (unsigned __int16)v3 == 15 && *((_BYTE *)qword_1800C8560 + v12 + 8) == 1 )
          {
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              v51 = L"CompleteClosing: Skipping version 1 Admin Dll callback for IKEv2 connection";
              v52 = 152;
              McGenEventWrite_EventWriteTransfer(
                (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
                v10,
                (unsigned __int16)v3 - 13,
                &v50);
            }
          }
          else
          {
            v13 = *(void (__fastcall **)(_RAS_PORT_0 *, _RAS_PORT_1 *))((char *)qword_1800C8560 + v12 + 104);
            if ( v13 )
              v13(&v49, &v44);
          }
        }
      }
    }
    if ( !(unsigned int)RasBundleGetPort(*(_QWORD *)(v41[0] + 56LL), &v43) )
      goto LABEL_56;
    v14 = v41[0];
    if ( *(_DWORD *)(v41[0] + 96LL) )
      goto LABEL_56;
    if ( (*(_BYTE *)(v41[0] + 80LL) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(DdmLegacyDevice *, _QWORD *))(*(_QWORD *)this + 696LL))(this, v41);
      v14 = v41[0];
    }
    if ( *(_QWORD *)(v14 + 72) == -1 )
    {
LABEL_46:
      if ( !*(_DWORD *)(v14 + 144) )
      {
        v29 = (_QWORD *)(v14 + 1484);
        if ( v14 != -1484 )
        {
          if ( *v29 != *(_QWORD *)&GUID_NULL.Data1 )
            goto LABEL_54;
          if ( *(_QWORD *)(v14 + 1492) != *(_QWORD *)GUID_NULL.Data4 )
          {
LABEL_52:
            if ( *v29 == *(_QWORD *)&GUID_NULL.Data1 && v29[1] == *(_QWORD *)GUID_NULL.Data4 )
              goto LABEL_55;
            goto LABEL_54;
          }
        }
        if ( memcmp_0(&GUID_NULL, &GUID_NULL, 0x10u) )
        {
          if ( v29 )
            goto LABEL_52;
LABEL_54:
          RasRdValidateAndUpdateVpnConnectionCount(v29, 0, 0);
        }
      }
LABEL_55:
      v30 = DdmConnectionTable::GetInstance();
      DdmConnectionTable::RemoveConnection(v30, *((void **)this + 15));
LABEL_56:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(DdmLegacyDevice *, __int64))this)(this, 1);
      goto LABEL_58;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
    v15 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                    g_pIDimInterfaceTable,
                                    *(_QWORD *)(v41[0] + 72LL));
    v16 = v15;
    if ( !v15 )
    {
LABEL_45:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
      v14 = v41[0];
      goto LABEL_46;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v15)(v15);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_42;
    LOWORD(v57) = 0;
    Buffer[0] = 0;
    v17 = *((_DWORD *)this + 24);
    if ( v17 != -1 )
      _itow_s(v17, Buffer, 0x14u, 10);
    v18 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 280LL))(v16);
    FormatRRASErrorString(&v57, L"CompleteClosing:Marking interface '%ws' DISCONNECTED.", v18);
    if ( (byte_1800C8404 & 8) == 0 )
    {
LABEL_42:
      InterfaceDisconnected(v16);
      v22 = (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 72LL))(v16) == 2;
      v26 = *(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 8LL);
      if ( v22 )
      {
        v26(v16);
      }
      else
      {
        v26(v16);
        v27 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 72LL);
        v28 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 16LL))(v16);
        v27(g_pIDimInterfaceTable, v28);
      }
      goto LABEL_45;
    }
    v19 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 280LL))(v16);
    v20 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL))(v16, v46);
    v21 = v16;
    v22 = v20 == 0;
    v23 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL);
    if ( v22 )
    {
      if ( !v23(v16, v48) )
      {
        v25 = &v45;
        goto LABEL_41;
      }
      v24 = &v50;
      v21 = v16;
      v23 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL);
    }
    else
    {
      v24 = (struct _EVENT_DATA_DESCRIPTOR *)&v47;
    }
    LODWORD(v25) = v23(v21, (char *)v24);
LABEL_41:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v57,
      (_DWORD)v25,
      v19,
      (__int64)Buffer);
    goto LABEL_42;
  }
LABEL_58:
  v31 = *((_DWORD *)this + 33);
  if ( (v31 & 8) != 0 )
  {
    *((_DWORD *)this + 33) = v31 & 0xFFFFFFF7;
    --dword_1800C84B0;
    if ( (*((_BYTE *)this + 132) & 0x40) != 0 )
      MediaObjAddToTable((wchar_t *)this + 391);
  }
  if ( *((_QWORD *)this + 151) )
  {
    RasFreeBuffer();
    *((_QWORD *)this + 151) = 0;
  }
  if ( *((_QWORD *)this + 152) )
  {
    RasFreeBuffer();
    *((_QWORD *)this + 152) = 0;
  }
  (*(void (__fastcall **)(DdmLegacyDevice *, _QWORD))(*(_QWORD *)this + 640LL))(this, 0);
  v32 = *((_DWORD *)this + 33);
  if ( (v32 & 0x400) != 0 )
  {
    (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800C8670 + 16LL))(
      qword_1800C8670,
      DeviceObjRemoveFromTable,
      *((_QWORD *)this + 12),
      0);
  }
  else
  {
    *((_QWORD *)this + 15) = -1;
    *((_WORD *)this + 84) = 0;
    *((_WORD *)this + 341) = 0;
    *((_WORD *)this + 620) = 0;
    *((_DWORD *)this + 33) = v32 & 0xFFFEFFFD;
    *((_DWORD *)this + 35) = 0;
    *(_OWORD *)((char *)this + 1076) = 0;
    v33 = 2147483646;
    v34 = L"{NA}";
    v35 = 40;
    v36 = (wchar_t *)((char *)this + 1092);
    do
    {
      if ( !v33 )
        break;
      v37 = *v34;
      if ( !*v34 )
        break;
      ++v34;
      *v36++ = v37;
      --v33;
      --v35;
    }
    while ( v35 );
    v38 = v36 - 1;
    if ( v35 )
      v38 = v36;
    *v38 = 0;
    v39 = (unsigned int)(*(_DWORD *)(qword_1800C84F8 + 4) - 2);
    if ( *(_DWORD *)(qword_1800C84F8 + 4) == 2 )
      goto LABEL_79;
    if ( *(_DWORD *)(qword_1800C84F8 + 4) == 3 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      *((_DWORD *)this + 26) = 10;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_80;
    }
    v39 = (unsigned int)(*(_DWORD *)(qword_1800C84F8 + 4) - 4);
    if ( *(_DWORD *)(qword_1800C84F8 + 4) == 4 )
    {
LABEL_79:
      (*(void (__fastcall **)(DdmLegacyDevice *, __int64, const wchar_t *))(*(_QWORD *)this + 480LL))(this, v39, v34);
      (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 168LL))(this);
      goto LABEL_80;
    }
    if ( *(_DWORD *)(qword_1800C84F8 + 4) == 7 )
      *((_DWORD *)this + 26) = 10;
  }
LABEL_80:
  v40 = (void (__fastcall ***)(_QWORD, __int64))v41[0];
  if ( v41[0] && _InterlockedExchangeAdd((volatile signed __int32 *)(v41[0] + 8LL), 0xFFFFFFFF) == 1 )
  {
    if ( v40 )
      (**v40)(v40, 1);
  }
}

```

## disassembly

```asm
0x180029a40  push    rbp
0x180029a42  push    rbx
0x180029a43  push    rsi
0x180029a44  push    rdi
0x180029a45  push    r12
0x180029a47  push    r13
0x180029a49  push    r14
0x180029a4b  push    r15
0x180029a4d  lea     rbp, [rsp-9F8h]
0x180029a55  sub     rsp, 0AF8h
0x180029a5c  mov     rax, cs:__security_cookie
0x180029a63  xor     rax, rsp
0x180029a66  mov     [rbp+0A30h+var_50], rax
0x180029a6d  mov     rdi, rcx
0x180029a70  mov     [rsp+0B30h+var_AE0], 0
0x180029a79  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x180029a7e  lea     r8, [rsp+0B30h+var_AE0]
0x180029a83  mov     rdx, [rdi+78h]
0x180029a87  mov     rcx, rax
0x180029a8a  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x180029a8f  xor     eax, eax
0x180029a91  mov     [rbp+0A30h+var_850], eax
0x180029a97  xor     edx, edx; Val
0x180029a99  mov     r8d, 7FCh; Size
0x180029a9f  lea     rcx, [rbp+0A30h+var_84C]; void *
0x180029aa6  call    memset_0
0x180029aab  xor     eax, eax
0x180029aad  mov     dword ptr [rbp+0A30h+Buffer], eax
0x180029ab3  xorps   xmm0, xmm0
0x180029ab6  movups  [rbp+0A30h+var_87C], xmm0
0x180029abd  movups  [rbp+0A30h+var_86C], xmm0
0x180029ac4  mov     [rbp+0A30h+var_85C], eax
0x180029aca  movups  [rbp+0A30h+var_A70], xmm0
0x180029ace  mov     r13d, [rdi+88h]
0x180029ad5  mov     ebx, [rdi+84h]
0x180029adb  mov     esi, ebx
0x180029add  and     esi, 4000h
0x180029ae3  mov     r14d, ebx
0x180029ae6  and     r14d, 2000h
0x180029aed  and     ebx, 1000h
0x180029af3  mov     r15d, [rdi+80h]
0x180029afa  mov     r12d, [rdi+4B0h]
0x180029b01  test    cs:byte_1800C8404, 8
0x180029b08  jz      loc_180029BE3
0x180029b0e  mov     word ptr [rbp+0A30h+var_850], ax
0x180029b15  mov     [rbp+0A30h+Buffer], ax
0x180029b1c  mov     ecx, [rdi+60h]; Value
0x180029b1f  cmp     ecx, 0FFFFFFFFh
0x180029b22  jz      short loc_180029B39
0x180029b24  lea     r9d, [rax+0Ah]; Radix
0x180029b28  lea     r8d, [rax+14h]; BufferCount
0x180029b2c  lea     rdx, [rbp+0A30h+Buffer]; Buffer
0x180029b33  call    cs:__imp__itow_s
0x180029b39  xor     r11d, r11d
0x180029b3c  test    ebx, ebx
0x180029b3e  setnz   r11b
0x180029b42  mov     edx, [rdi+4B0h]
0x180029b48  mov     r8d, [rdi+80h]
0x180029b4f  xor     r10d, r10d
0x180029b52  cmp     r15d, 4
0x180029b56  setnz   r10b
0x180029b5a  xor     ecx, ecx
0x180029b5c  cmp     [rsp+0B30h+var_AE0], rcx
0x180029b61  setz    cl
0x180029b64  xor     eax, eax
0x180029b66  test    r14d, r14d
0x180029b69  setnz   al
0x180029b6c  xor     r9d, r9d
0x180029b6f  test    esi, esi
0x180029b71  setnz   r9b
0x180029b75  mov     [rsp+0B30h+var_AE8], r11d
0x180029b7a  mov     [rsp+0B30h+var_AF0], edx
0x180029b7e  mov     [rsp+0B30h+var_AF8], r8d
0x180029b83  mov     [rsp+0B30h+var_B00], r10d
0x180029b88  mov     dword ptr [rsp+0B30h+var_B08], ecx
0x180029b8c  mov     dword ptr [rsp+0B30h+var_B10], eax
0x180029b90  mov     r8, [rdi+60h]
0x180029b94  lea     rdx, aCompleteclosin_1; "CompleteClosing:hPort=%d,Auth=%d,Rcv=%d"...
0x180029b9b  lea     rcx, [rbp+0A30h+var_850]
0x180029ba2  call    FormatRRASErrorString
0x180029ba7  test    cs:byte_1800C8404, 8
0x180029bae  jz      short loc_180029BE3
0x180029bb0  lea     rax, [rbp+0A30h+Buffer]
0x180029bb7  mov     [rsp+0B30h+var_B08], rax
0x180029bbc  mov     [rsp+0B30h+var_B10], 0
0x180029bc5  lea     r9, [rbp+0A30h+var_A70]
0x180029bc9  lea     r8, [rbp+0A30h+var_850]
0x180029bd0  lea     rdx, RasDdmParamTraceError
0x180029bd7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029bde  call    McTemplateU0zjzz_EventWriteTransfer
0x180029be3  test    esi, esi
0x180029be5  jnz     loc_18002A1A1
0x180029beb  test    r14d, r14d
0x180029bee  jnz     loc_18002A1A1
0x180029bf4  cmp     r15d, 4
0x180029bf8  jnz     loc_18002A1A1
0x180029bfe  cmp     r12d, 2
0x180029c02  jnz     loc_18002A1A1
0x180029c08  xor     r15d, r15d
0x180029c0b  test    ebx, ebx
0x180029c0d  jnz     loc_18002A1A1
0x180029c13  test    byte ptr [rdi+84h], 8
0x180029c1a  jz      short loc_180029C29
0x180029c1c  lea     rdx, [rsp+0B30h+var_AE0]
0x180029c21  mov     rcx, rdi
0x180029c24  call    ?LogDisconnectEvent@DdmDevice@@QEAAKAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmDevice::LogDisconnectEvent(RasObjPtr<DdmConnection> &)
0x180029c29  cmp     [rsp+0B30h+var_AE0], r15
0x180029c2e  jz      loc_18002A00A
0x180029c34  mov     [rsp+0B30h+var_AC8], r15
0x180029c39  mov     [rsp+0B30h+var_AD0], rdi
0x180029c3e  lock inc dword ptr [rdi+8]
0x180029c42  lea     rdx, [rsp+0B30h+var_AD0]
0x180029c47  mov     rcx, [rsp+0B30h+var_AE0]
0x180029c4c  call    ?RemoveLink@DdmConnection@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmConnection::RemoveLink(RasObjPtr<DdmDevice> &)
0x180029c51  test    byte ptr [rdi+84h], 20h
0x180029c58  jz      loc_180029D45
0x180029c5e  xor     edx, edx; Val
0x180029c60  mov     r8d, 188h; Size
0x180029c66  lea     rcx, [rbp+0A30h+var_A30]; void *
0x180029c6a  call    memset_0
0x180029c6f  xor     edx, edx; Val
0x180029c71  lea     r8d, [rdx+48h]; Size
0x180029c75  lea     rcx, [rsp+0B30h+var_AC0]; void *
0x180029c7a  call    memset_0
0x180029c7f  lea     rdx, [rbp+0A30h+var_A30]; struct _RAS_PORT_0 *
0x180029c83  mov     rcx, rdi; this
0x180029c86  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_0@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_0 *)
0x180029c8b  test    eax, eax
0x180029c8d  jnz     loc_180029D45
0x180029c93  lea     rdx, [rsp+0B30h+var_AC0]; struct _RAS_PORT_1 *
0x180029c98  mov     rcx, rdi; this
0x180029c9b  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_1@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_1 *)
0x180029ca0  test    eax, eax
0x180029ca2  jnz     loc_180029D45
0x180029ca8  movzx   esi, r13w
0x180029cac  mov     ebx, r15d
0x180029caf  cmp     cs:dword_1800C8568, r15d
0x180029cb6  jbe     loc_180029D45
0x180029cbc  mov     eax, ebx
0x180029cbe  imul    rcx, rax, 0A8h
0x180029cc5  mov     rax, cs:qword_1800C8560
0x180029ccc  cmp     esi, 0Fh
0x180029ccf  jnz     short loc_180029D1F
0x180029cd1  cmp     byte ptr [rcx+rax+8], 1
0x180029cd6  jnz     short loc_180029D1F
0x180029cd8  test    cs:byte_1800C8404, 10h
0x180029cdf  jz      short loc_180029D37
0x180029ce1  lea     rax, aCompleteclosin_2; "CompleteClosing: Skipping version 1 Adm"...
0x180029ce8  mov     [rbp+0A30h+var_890], rax
0x180029cef  mov     [rbp+0A30h+var_888], 98h
0x180029cfa  lea     rax, [rbp+0A30h+var_8A0]
0x180029d01  mov     [rsp+0B30h+var_B10], rax
0x180029d06  lea     r9d, [rsi-0Dh]
0x180029d0a  lea     rdx, RasDdmTraceInfo
0x180029d11  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029d18  call    McGenEventWrite_EventWriteTransfer
0x180029d1d  jmp     short loc_180029D37
0x180029d1f  mov     rax, [rcx+rax+68h]
0x180029d24  test    rax, rax
0x180029d27  jz      short loc_180029D37
0x180029d29  lea     rdx, [rsp+0B30h+var_AC0]
0x180029d2e  lea     rcx, [rbp+0A30h+var_A30]
0x180029d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d37  inc     ebx
0x180029d39  cmp     ebx, cs:dword_1800C8568
0x180029d3f  jb      loc_180029CBC
0x180029d45  lea     rdx, [rsp+0B30h+var_AC8]
0x180029d4a  mov     rcx, [rsp+0B30h+var_AE0]
0x180029d4f  mov     rcx, [rcx+38h]
0x180029d53  call    cs:__imp_RasBundleGetPort
0x180029d59  test    eax, eax
0x180029d5b  jz      loc_180029FEA
0x180029d61  mov     rax, [rsp+0B30h+var_AE0]
0x180029d66  cmp     [rax+60h], r15d
0x180029d6a  jnz     loc_180029FEA
0x180029d70  test    byte ptr [rax+50h], 10h
0x180029d74  jz      short loc_180029D92
0x180029d76  mov     rax, [rdi]
0x180029d79  lea     rdx, [rsp+0B30h+var_AE0]
0x180029d7e  mov     rcx, rdi
0x180029d81  mov     rax, [rax+2B8h]
0x180029d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d8d  mov     rax, [rsp+0B30h+var_AE0]
0x180029d92  cmp     qword ptr [rax+48h], 0FFFFFFFFFFFFFFFFh
0x180029d97  jz      loc_180029F74
0x180029d9d  mov     rcx, cs:g_pIDimInterfaceTable
0x180029da4  mov     rax, [rcx]
0x180029da7  mov     rax, [rax+8]
0x180029dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029db0  mov     rcx, cs:g_pIDimInterfaceTable
0x180029db7  mov     rax, [rcx]
0x180029dba  mov     rdx, [rsp+0B30h+var_AE0]
0x180029dbf  mov     rdx, [rdx+48h]
0x180029dc3  mov     rax, [rax+40h]
0x180029dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dcc  mov     rsi, rax
0x180029dcf  test    rax, rax
0x180029dd2  jz      loc_180029F5C
0x180029dd8  mov     rcx, [rax]
0x180029ddb  mov     rax, [rcx]
0x180029dde  mov     rcx, rsi
0x180029de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de6  test    cs:byte_1800C8404, 8
0x180029ded  jz      loc_180029EF8
0x180029df3  mov     word ptr [rbp+0A30h+var_850], r15w
0x180029dfb  mov     [rbp+0A30h+Buffer], r15w
0x180029e03  mov     ecx, [rdi+60h]; Value
0x180029e06  cmp     ecx, 0FFFFFFFFh
0x180029e09  jz      short loc_180029E22
0x180029e0b  mov     r9d, 0Ah; Radix
0x180029e11  lea     r8d, [r9+0Ah]; BufferCount
0x180029e15  lea     rdx, [rbp+0A30h+Buffer]; Buffer
0x180029e1c  call    cs:__imp__itow_s
0x180029e22  mov     rax, [rsi]
0x180029e25  mov     rcx, rsi
0x180029e28  mov     rax, [rax+118h]
0x180029e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e34  mov     r8, rax
0x180029e37  lea     rdx, aCompleteclosin_0; "CompleteClosing:Marking interface '%ws'"...
0x180029e3e  lea     rcx, [rbp+0A30h+var_850]
0x180029e45  call    FormatRRASErrorString
0x180029e4a  test    cs:byte_1800C8404, 8
0x180029e51  jz      loc_180029EF8
0x180029e57  mov     rax, [rsi]
0x180029e5a  mov     rcx, rsi
0x180029e5d  mov     rax, [rax+118h]
0x180029e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e69  mov     rbx, rax
0x180029e6c  mov     rcx, [rsi]
0x180029e6f  mov     rax, [rcx+168h]
0x180029e76  lea     rdx, [rbp+0A30h+var_A60]
0x180029e7a  mov     rcx, rsi
0x180029e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e82  mov     rcx, [rsi]
0x180029e85  mov     r8, [rcx+168h]
0x180029e8c  mov     rcx, rsi
0x180029e8f  test    rax, rax
0x180029e92  mov     rax, r8
0x180029e95  jz      short loc_180029E9D
0x180029e97  lea     rdx, [rbp+0A30h+var_A50]
0x180029e9b  jmp     short loc_180029EBF
0x180029e9d  lea     rdx, [rbp+0A30h+var_A40]
0x180029ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ea6  test    rax, rax
0x180029ea9  jz      short loc_180029EC6
0x180029eab  mov     rax, [rsi]
0x180029eae  lea     rdx, [rbp+0A30h+var_8A0]
0x180029eb5  mov     rcx, rsi
0x180029eb8  mov     rax, [rax+168h]
0x180029ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ec4  jmp     short loc_180029ECA
0x180029ec6  lea     rax, [rbp+0A30h+var_A70]
0x180029eca  lea     r8, [rbp+0A30h+Buffer]
0x180029ed1  mov     [rsp+0B30h+var_B08], r8
0x180029ed6  mov     [rsp+0B30h+var_B10], rbx
0x180029edb  mov     r9, rax
0x180029ede  lea     r8, [rbp+0A30h+var_850]
0x180029ee5  lea     rdx, RasDdmParamTraceError
0x180029eec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180029ef3  call    McTemplateU0zjzz_EventWriteTransfer
0x180029ef8  mov     rcx, rsi; struct IDimInterface *
0x180029efb  call    ?InterfaceDisconnected@@YAXPEAUIDimInterface@@@Z; InterfaceDisconnected(IDimInterface *)
0x180029f00  mov     rax, [rsi]
0x180029f03  mov     rcx, rsi
0x180029f06  mov     rax, [rax+48h]
0x180029f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f0f  mov     rcx, [rsi]
0x180029f12  mov     rdx, [rcx+8]
0x180029f16  mov     rcx, rsi
0x180029f19  cmp     eax, 2
0x180029f1c  mov     rax, rdx
0x180029f1f  jz      short loc_180029F57
0x180029f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f26  mov     rax, cs:g_pIDimInterfaceTable
0x180029f2d  mov     rcx, [rax]
0x180029f30  mov     rbx, [rcx+48h]
0x180029f34  mov     rcx, [rsi]
0x180029f37  mov     rax, [rcx+10h]
0x180029f3b  mov     rcx, rsi
0x180029f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f43  mov     rdx, rax
0x180029f46  mov     rcx, cs:g_pIDimInterfaceTable
0x180029f4d  mov     rax, rbx
0x180029f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f55  jmp     short loc_180029F5C
0x180029f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f5c  mov     rcx, cs:g_pIDimInterfaceTable
0x180029f63  mov     rax, [rcx]
0x180029f66  mov     rax, [rax+18h]
0x180029f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f6f  mov     rax, [rsp+0B30h+var_AE0]
0x180029f74  cmp     [rax+90h], r15d
0x180029f7b  jnz     short loc_180029FD8
0x180029f7d  lea     rbx, [rax+5CCh]
0x180029f84  mov     r14, qword ptr cs:GUID_NULL.Data4
0x180029f8b  mov     rsi, qword ptr cs:GUID_NULL.Data1
0x180029f92  test    rbx, rbx
0x180029f95  jz      short loc_180029FA2
0x180029f97  cmp     [rbx], rsi
0x180029f9a  jnz     short loc_180029FCB
  ... truncated ...
```
