# DdmLegacyDevice::CompleteClosing(void)

- ea: `0x18002bc90`
- end: `0x18002c42c`
- name: `?CompleteClosing@DdmLegacyDevice@@UEAAXXZ`
- size: `1948`
- prototype: `void __fastcall(DdmLegacyDevice *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007c0c`
- `0x180007d00`
- `0x180008efc`
- `0x18000ad58`
- `0x18002bc90`
- `0x18002f2ec`
- `0x1800304dc`
- `0x180030684`
- `0x1800306c4`
- `0x180035e2c`
- `0x180035f14`
- `0x180037d88`
- `0x18005ab8c`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002c39c`
- `KERNEL32!LeaveCriticalSection` at `0x18002c39c`
- `KERNEL32!EnterCriticalSection` at `0x18002c385`
- `KERNEL32!EnterCriticalSection` at `0x18002c385`
- `rasman!RasFreeBuffer` at `0x18002c261`
- `rasman!RasFreeBuffer` at `0x18002c280`
- `rasman!RasFreeBuffer` at `0x18002c261`
- `rasman!RasFreeBuffer` at `0x18002c280`
- `rasman!RasBundleGetPort` at `0x18002bf9e`
- `rasman!RasBundleGetPort` at `0x18002bf9e`

## string_xrefs

- `0x18002bddf`: `CompleteClosing:hPort=%d,Auth=%d,Rcv=%d,Conn=%d %d,Sec=%d %d,Protocol=%d`
- `0x18002bf2d`: `CompleteClosing: Skipping version 1 Admin Dll callback for IKEv2 connection`
- `0x18002c078`: `CompleteClosing:Marking interface '%ws' DISCONNECTED.`

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
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int i; // ebx
  char *v12; // rcx
  void (__fastcall *v13)(_RAS_PORT_0 *, _RAS_PORT_1 *); // rax
  __int64 v14; // rax
  struct IDimInterface *v15; // rax
  struct IDimInterface *v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  struct IDimInterface *v20; // rcx
  bool v21; // zf
  __int64 (__fastcall *v22)(struct IDimInterface *, char *); // rax
  char *v23; // rdx
  __int128 *v24; // rax
  void (__fastcall *v25)(struct IDimInterface *); // rax
  void (__fastcall *v26)(__int64, __int64); // rbx
  __int64 v27; // rax
  _QWORD *v28; // rcx
  DdmConnectionTable *v29; // rax
  int v30; // eax
  int v31; // eax
  _WORD *v32; // rcx
  __int64 v33; // rdx
  signed __int64 v34; // r8
  __int16 v35; // ax
  _WORD *v36; // rax
  __int64 v37; // rdx
  void (__fastcall ***v38)(_QWORD, __int64); // rcx
  __int64 v39; // [rsp+58h] [rbp-B0h] BYREF
  DdmLegacyDevice *v40; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+68h] [rbp-A0h] BYREF
  _RAS_PORT_1 v42; // [rsp+78h] [rbp-90h] BYREF
  __int128 v43; // [rsp+C8h] [rbp-40h] BYREF
  char v44[16]; // [rsp+D8h] [rbp-30h] BYREF
  char v45; // [rsp+E8h] [rbp-20h] BYREF
  char v46[16]; // [rsp+F8h] [rbp-10h] BYREF
  char v47; // [rsp+108h] [rbp+0h] BYREF
  _RAS_PORT_0 v48; // [rsp+118h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+2A8h] [rbp+1A0h] BYREF
  const wchar_t *v50; // [rsp+2B8h] [rbp+1B0h]
  __int64 v51; // [rsp+2C0h] [rbp+1B8h]
  int v52; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int128 v53; // [rsp+2CCh] [rbp+1C4h]
  __int128 v54; // [rsp+2DCh] [rbp+1D4h]
  int v55; // [rsp+2ECh] [rbp+1E4h]
  int v56; // [rsp+2F8h] [rbp+1F0h] BYREF
  char v57[2044]; // [rsp+2FCh] [rbp+1F4h] BYREF

  v39 = 0;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v39);
  v56 = 0;
  memset_0(v57, 0, sizeof(v57));
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v43 = 0;
  v3 = *((unsigned __int16 *)this + 68);
  v4 = *((_DWORD *)this + 33) & 0x4000;
  v5 = *((_DWORD *)this + 33) & 0x2000;
  v6 = *((_DWORD *)this + 33) & 0x1000;
  v7 = *((_DWORD *)this + 32);
  v8 = *((_DWORD *)this + 300);
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v56) = 0;
    LOWORD(v52) = 0;
    ConvertPortNoToString(&v52, *((unsigned int *)this + 24));
    FormatRRASErrorString(
      &v56,
      L"CompleteClosing:hPort=%d,Auth=%d,Rcv=%d,Conn=%d %d,Sec=%d %d,Protocol=%d",
      *((_QWORD *)this + 12),
      v4 != 0,
      v5 != 0,
      v39 == 0,
      v7 != 4,
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 300),
      v6 != 0);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v56,
        (unsigned int)&v43,
        0,
        (__int64)&v52);
  }
  if ( v4 || v5 || v7 != 4 || v8 != 2 || v6 )
    goto LABEL_76;
  if ( (*((_BYTE *)this + 132) & 8) != 0 )
    DdmDevice::LogDisconnectEvent(this, &v39);
  v9 = v39;
  if ( v39 )
  {
    v41 = 0;
    v40 = this;
    if ( this )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      v9 = v39;
    }
    DdmConnection::RemoveLink(v9, &v40);
    if ( (*((_BYTE *)this + 132) & 0x20) != 0 )
    {
      memset_0(&v48, 0, sizeof(v48));
      memset_0(&v42, 0, sizeof(v42));
      if ( !DdmDevice::GetRasPortData(this, &v48) && !DdmDevice::GetRasPortData(this, &v42) )
      {
        for ( i = 0; i < dword_1800CF568; ++i )
        {
          v12 = (char *)qword_1800CF560 + 168 * i;
          if ( v3 == 15 && v12[8] == 1 )
          {
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              v50 = L"CompleteClosing: Skipping version 1 Admin Dll callback for IKEv2 connection";
              v51 = 152;
              McGenEventWrite_EventWriteTransfer(
                (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
                v10,
                2u,
                &v49);
            }
          }
          else
          {
            v13 = (void (__fastcall *)(_RAS_PORT_0 *, _RAS_PORT_1 *))*((_QWORD *)v12 + 13);
            if ( v13 )
              v13(&v48, &v42);
          }
        }
      }
    }
    if ( !(unsigned int)RasBundleGetPort(*(_QWORD *)(v39 + 56), &v41) )
      goto LABEL_52;
    v14 = v39;
    if ( *(_DWORD *)(v39 + 96) )
      goto LABEL_52;
    if ( (*(_BYTE *)(v39 + 80) & 0x10) != 0 )
    {
      (*(void (__fastcall **)(DdmLegacyDevice *, __int64 *))(*(_QWORD *)this + 696LL))(this, &v39);
      v14 = v39;
    }
    if ( *(_QWORD *)(v14 + 72) == -1 )
    {
LABEL_44:
      if ( !*(_DWORD *)(v14 + 144) )
      {
        v28 = (_QWORD *)(v14 + 1484);
        if ( v14 != -1484
          && (*v28 != *(_QWORD *)&GUID_NULL.Data1
           || *(_QWORD *)(v14 + 1492) != *(_QWORD *)GUID_NULL.Data4
           && (*v28 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)(v14 + 1492) != *(_QWORD *)GUID_NULL.Data4)) )
        {
          RasRdValidateAndUpdateVpnConnectionCount(v28, 0, 0);
        }
      }
      v29 = DdmConnectionTable::GetInstance();
      DdmConnectionTable::RemoveConnection(v29, *((void **)this + 15));
LABEL_52:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(DdmLegacyDevice *, __int64))this)(this, 1);
      goto LABEL_54;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 8LL))(g_pIDimInterfaceTable);
    v15 = (struct IDimInterface *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
                                    g_pIDimInterfaceTable,
                                    *(_QWORD *)(v39 + 72));
    v16 = v15;
    if ( !v15 )
    {
LABEL_43:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 24LL))(g_pIDimInterfaceTable);
      v14 = v39;
      goto LABEL_44;
    }
    (**(void (__fastcall ***)(struct IDimInterface *))v15)(v15);
    if ( (byte_1800CF404 & 8) == 0
      || (LOWORD(v56) = 0,
          LOWORD(v52) = 0,
          ConvertPortNoToString(&v52, *((unsigned int *)this + 24)),
          v17 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 280LL))(v16),
          FormatRRASErrorString(&v56, L"CompleteClosing:Marking interface '%ws' DISCONNECTED.", v17),
          (byte_1800CF404 & 8) == 0) )
    {
LABEL_40:
      InterfaceDisconnected(v16);
      v21 = (*(unsigned int (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 72LL))(v16) == 2;
      v25 = *(void (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 8LL);
      if ( v21 )
      {
        v25(v16);
      }
      else
      {
        v25(v16);
        v26 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 72LL);
        v27 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 16LL))(v16);
        v26(g_pIDimInterfaceTable, v27);
      }
      goto LABEL_43;
    }
    v18 = (*(__int64 (__fastcall **)(struct IDimInterface *))(*(_QWORD *)v16 + 280LL))(v16);
    v19 = (*(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL))(v16, v44);
    v20 = v16;
    v21 = v19 == 0;
    v22 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL);
    if ( v21 )
    {
      if ( !v22(v16, v46) )
      {
        v24 = &v43;
        goto LABEL_39;
      }
      v23 = &v47;
      v20 = v16;
      v22 = *(__int64 (__fastcall **)(struct IDimInterface *, char *))(*(_QWORD *)v16 + 360LL);
    }
    else
    {
      v23 = &v45;
    }
    LODWORD(v24) = v22(v20, v23);
LABEL_39:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDdmParamTraceError,
      (unsigned int)&v56,
      (_DWORD)v24,
      v18,
      (__int64)&v52);
    goto LABEL_40;
  }
LABEL_54:
  v30 = *((_DWORD *)this + 33);
  if ( (v30 & 8) != 0 )
  {
    *((_DWORD *)this + 33) = v30 & 0xFFFFFFF7;
    --dword_1800CF4B0;
    if ( (*((_BYTE *)this + 132) & 0x40) != 0 )
      MediaObjAddToTable((STRSAFE_LPCWSTR)this + 391);
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
  v31 = *((_DWORD *)this + 33);
  if ( (v31 & 0x400) != 0 )
  {
    (*(void (__fastcall **)(DdmThreadPool *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), _QWORD, _QWORD))(*(_QWORD *)qword_1800CF670 + 16LL))(
      qword_1800CF670,
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
    *((_DWORD *)this + 33) = v31 & 0xFFFEFFFD;
    *((_DWORD *)this + 35) = 0;
    *(_OWORD *)((char *)this + 1076) = 0;
    v32 = (_WORD *)((char *)this + 1092);
    v33 = 40;
    v34 = (char *)L"{NA}" - ((char *)this + 1092);
    do
    {
      if ( v33 == -2147483606 )
        break;
      v35 = *(_WORD *)((char *)v32 + v34);
      if ( !v35 )
        break;
      *v32++ = v35;
      --v33;
    }
    while ( v33 );
    v36 = v32 - 1;
    if ( v33 )
      v36 = v32;
    *v36 = 0;
    v37 = (unsigned int)(*(_DWORD *)(qword_1800CF4F8 + 4) - 2);
    if ( *(_DWORD *)(qword_1800CF4F8 + 4) == 2 )
      goto LABEL_75;
    if ( *(_DWORD *)(qword_1800CF4F8 + 4) == 3 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      *((_DWORD *)this + 26) = 10;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_76;
    }
    v37 = (unsigned int)(*(_DWORD *)(qword_1800CF4F8 + 4) - 4);
    if ( *(_DWORD *)(qword_1800CF4F8 + 4) == 4 )
    {
LABEL_75:
      (*(void (__fastcall **)(DdmLegacyDevice *, __int64, signed __int64))(*(_QWORD *)this + 480LL))(this, v37, v34);
      (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 168LL))(this);
      goto LABEL_76;
    }
    if ( *(_DWORD *)(qword_1800CF4F8 + 4) == 7 )
      *((_DWORD *)this + 26) = 10;
  }
LABEL_76:
  v38 = (void (__fastcall ***)(_QWORD, __int64))v39;
  if ( v39 && _InterlockedExchangeAdd((volatile signed __int32 *)(v39 + 8), 0xFFFFFFFF) == 1 )
  {
    if ( v38 )
      (**v38)(v38, 1);
  }
}

```

## disassembly

```asm
0x18002bc90  mov     rax, rsp
0x18002bc93  mov     [rax+10h], rbx
0x18002bc97  mov     [rax+18h], rsi
0x18002bc9b  mov     [rax+20h], rdi
0x18002bc9f  push    rbp
0x18002bca0  push    r12
0x18002bca2  push    r13
0x18002bca4  push    r14
0x18002bca6  push    r15
0x18002bca8  lea     rbp, [rax-0A28h]
0x18002bcaf  sub     rsp, 0B00h
0x18002bcb6  mov     rax, cs:__security_cookie
0x18002bcbd  xor     rax, rsp
0x18002bcc0  mov     [rbp+0A20h+var_30], rax
0x18002bcc7  mov     rdi, rcx
0x18002bcca  xor     ebx, ebx
0x18002bccc  mov     [rsp+0B20h+var_AD0], rbx
0x18002bcd1  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18002bcd6  lea     r8, [rsp+0B20h+var_AD0]
0x18002bcdb  mov     rdx, [rdi+78h]
0x18002bcdf  mov     rcx, rax
0x18002bce2  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x18002bce7  mov     [rbp+0A20h+var_830], ebx
0x18002bced  xor     edx, edx; Val
0x18002bcef  mov     r8d, 7FCh; Size
0x18002bcf5  lea     rcx, [rbp+0A20h+var_82C]; void *
0x18002bcfc  call    memset_0
0x18002bd01  mov     [rbp+0A20h+var_860], ebx
0x18002bd07  xorps   xmm0, xmm0
0x18002bd0a  xor     eax, eax
0x18002bd0c  movups  [rbp+0A20h+var_85C], xmm0
0x18002bd13  movups  [rbp+0A20h+var_84C], xmm0
0x18002bd1a  mov     [rbp+0A20h+var_83C], eax
0x18002bd20  movups  [rbp+0A20h+var_A60], xmm0
0x18002bd24  movzx   r13d, word ptr [rdi+88h]
0x18002bd2c  mov     ebx, [rdi+84h]
0x18002bd32  mov     esi, ebx
0x18002bd34  and     esi, 4000h
0x18002bd3a  mov     r14d, ebx
0x18002bd3d  and     r14d, 2000h
0x18002bd44  and     ebx, 1000h
0x18002bd4a  mov     r15d, [rdi+80h]
0x18002bd51  mov     r12d, [rdi+4B0h]
0x18002bd58  test    cs:byte_1800CF404, 8
0x18002bd5f  jz      loc_18002BE2B
0x18002bd65  mov     word ptr [rbp+0A20h+var_830], ax
0x18002bd6c  mov     word ptr [rbp+0A20h+var_860], ax
0x18002bd73  mov     edx, [rdi+60h]
0x18002bd76  lea     rcx, [rbp+0A20h+var_860]
0x18002bd7d  call    ConvertPortNoToString
0x18002bd82  xor     r9d, r9d
0x18002bd85  mov     r11d, r9d
0x18002bd88  test    ebx, ebx
0x18002bd8a  setnz   r11b
0x18002bd8e  mov     edx, [rdi+4B0h]
0x18002bd94  mov     r8d, [rdi+80h]
0x18002bd9b  mov     r10d, r9d
0x18002bd9e  cmp     r15d, 4
0x18002bda2  setnz   r10b
0x18002bda6  mov     ecx, r9d
0x18002bda9  cmp     [rsp+0B20h+var_AD0], r9
0x18002bdae  setz    cl
0x18002bdb1  mov     eax, r9d
0x18002bdb4  test    r14d, r14d
0x18002bdb7  setnz   al
0x18002bdba  test    esi, esi
0x18002bdbc  setnz   r9b
0x18002bdc0  mov     dword ptr [rsp+0B20h+var_AD8], r11d
0x18002bdc5  mov     [rsp+0B20h+var_AE0], edx
0x18002bdc9  mov     [rsp+0B20h+var_AE8], r8d
0x18002bdce  mov     [rsp+0B20h+var_AF0], r10d
0x18002bdd3  mov     [rsp+0B20h+var_AF8], ecx
0x18002bdd7  mov     dword ptr [rsp+0B20h+var_B00], eax
0x18002bddb  mov     r8, [rdi+60h]
0x18002bddf  lea     rdx, aCompleteclosin_1; "CompleteClosing:hPort=%d,Auth=%d,Rcv=%d"...
0x18002bde6  lea     rcx, [rbp+0A20h+var_830]
0x18002bded  call    FormatRRASErrorString
0x18002bdf2  test    cs:byte_1800CF404, 8
0x18002bdf9  jz      short loc_18002BE2B
0x18002bdfb  lea     rax, [rbp+0A20h+var_860]
0x18002be02  mov     qword ptr [rsp+0B20h+var_AF8], rax
0x18002be07  and     [rsp+0B20h+var_B00], 0
0x18002be0d  lea     r9, [rbp+0A20h+var_A60]
0x18002be11  lea     r8, [rbp+0A20h+var_830]
0x18002be18  lea     rdx, RasDdmParamTraceError
0x18002be1f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002be26  call    McTemplateU0zjzz_EventWriteTransfer
0x18002be2b  test    esi, esi
0x18002be2d  jnz     loc_18002C3CF
0x18002be33  test    r14d, r14d
0x18002be36  jnz     loc_18002C3CF
0x18002be3c  cmp     r15d, 4
0x18002be40  jnz     loc_18002C3CF
0x18002be46  cmp     r12d, 2
0x18002be4a  jnz     loc_18002C3CF
0x18002be50  xor     r14d, r14d
0x18002be53  test    ebx, ebx
0x18002be55  jnz     loc_18002C3CF
0x18002be5b  test    byte ptr [rdi+84h], 8
0x18002be62  jz      short loc_18002BE71
0x18002be64  lea     rdx, [rsp+0B20h+var_AD0]
0x18002be69  mov     rcx, rdi
0x18002be6c  call    ?LogDisconnectEvent@DdmDevice@@QEAAKAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmDevice::LogDisconnectEvent(RasObjPtr<DdmConnection> &)
0x18002be71  mov     rcx, [rsp+0B20h+var_AD0]
0x18002be76  test    rcx, rcx
0x18002be79  jz      loc_18002C227
0x18002be7f  mov     [rsp+0B20h+var_AC0], r14
0x18002be84  mov     [rsp+0B20h+var_AC8], rdi
0x18002be89  test    rdi, rdi
0x18002be8c  jz      short loc_18002BE97
0x18002be8e  lock inc dword ptr [rdi+8]
0x18002be92  mov     rcx, [rsp+0B20h+var_AD0]
0x18002be97  lea     rdx, [rsp+0B20h+var_AC8]
0x18002be9c  call    ?RemoveLink@DdmConnection@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmConnection::RemoveLink(RasObjPtr<DdmDevice> &)
0x18002bea1  test    byte ptr [rdi+84h], 20h
0x18002bea8  jz      loc_18002BF90
0x18002beae  xor     edx, edx; Val
0x18002beb0  mov     r8d, 188h; Size
0x18002beb6  lea     rcx, [rbp+0A20h+var_A10]; void *
0x18002beba  call    memset_0
0x18002bebf  xor     edx, edx; Val
0x18002bec1  lea     r8d, [rdx+48h]; Size
0x18002bec5  lea     rcx, [rsp+0B20h+var_AB0]; void *
0x18002beca  call    memset_0
0x18002becf  lea     rdx, [rbp+0A20h+var_A10]; struct _RAS_PORT_0 *
0x18002bed3  mov     rcx, rdi; this
0x18002bed6  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_0@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_0 *)
0x18002bedb  test    eax, eax
0x18002bedd  jnz     loc_18002BF90
0x18002bee3  lea     rdx, [rsp+0B20h+var_AB0]; struct _RAS_PORT_1 *
0x18002bee8  mov     rcx, rdi; this
0x18002beeb  call    ?GetRasPortData@DdmDevice@@QEAAKPEAU_RAS_PORT_1@@@Z; DdmDevice::GetRasPortData(_RAS_PORT_1 *)
0x18002bef0  test    eax, eax
0x18002bef2  jnz     loc_18002BF90
0x18002bef8  mov     ebx, r14d
0x18002befb  cmp     cs:dword_1800CF568, r14d
0x18002bf02  jbe     loc_18002BF90
0x18002bf08  mov     eax, ebx
0x18002bf0a  imul    rcx, rax, 0A8h
0x18002bf11  add     rcx, cs:qword_1800CF560
0x18002bf18  cmp     r13d, 0Fh
0x18002bf1c  jnz     short loc_18002BF6B
0x18002bf1e  cmp     byte ptr [rcx+8], 1
0x18002bf22  jnz     short loc_18002BF6B
0x18002bf24  test    cs:byte_1800CF404, 10h
0x18002bf2b  jz      short loc_18002BF82
0x18002bf2d  lea     rax, aCompleteclosin_2; "CompleteClosing: Skipping version 1 Adm"...
0x18002bf34  mov     [rbp+0A20h+var_870], rax
0x18002bf3b  mov     [rbp+0A20h+var_868], 98h
0x18002bf46  lea     rax, [rbp+0A20h+var_880]
0x18002bf4d  mov     [rsp+0B20h+var_B00], rax
0x18002bf52  lea     r9d, [r13-0Dh]
0x18002bf56  lea     rdx, RasDdmTraceInfo
0x18002bf5d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002bf64  call    McGenEventWrite_EventWriteTransfer
0x18002bf69  jmp     short loc_18002BF82
0x18002bf6b  mov     rax, [rcx+68h]
0x18002bf6f  test    rax, rax
0x18002bf72  jz      short loc_18002BF82
0x18002bf74  lea     rdx, [rsp+0B20h+var_AB0]
0x18002bf79  lea     rcx, [rbp+0A20h+var_A10]
0x18002bf7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf82  inc     ebx
0x18002bf84  cmp     ebx, cs:dword_1800CF568
0x18002bf8a  jb      loc_18002BF08
0x18002bf90  lea     rdx, [rsp+0B20h+var_AC0]
0x18002bf95  mov     rcx, [rsp+0B20h+var_AD0]
0x18002bf9a  mov     rcx, [rcx+38h]
0x18002bf9e  call    cs:__imp_RasBundleGetPort
0x18002bfa5  nop     dword ptr [rax+rax+00h]
0x18002bfaa  test    eax, eax
0x18002bfac  jz      loc_18002C207
0x18002bfb2  mov     rax, [rsp+0B20h+var_AD0]
0x18002bfb7  cmp     [rax+60h], r14d
0x18002bfbb  jnz     loc_18002C207
0x18002bfc1  test    byte ptr [rax+50h], 10h
0x18002bfc5  jz      short loc_18002BFE3
0x18002bfc7  mov     rax, [rdi]
0x18002bfca  lea     rdx, [rsp+0B20h+var_AD0]
0x18002bfcf  mov     rcx, rdi
0x18002bfd2  mov     rax, [rax+2B8h]
0x18002bfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfde  mov     rax, [rsp+0B20h+var_AD0]
0x18002bfe3  cmp     qword ptr [rax+48h], 0FFFFFFFFFFFFFFFFh
0x18002bfe8  jz      loc_18002C1B2
0x18002bfee  mov     rcx, cs:g_pIDimInterfaceTable
0x18002bff5  mov     rax, [rcx]
0x18002bff8  mov     rax, [rax+8]
0x18002bffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c001  mov     rcx, cs:g_pIDimInterfaceTable
0x18002c008  mov     rax, [rcx]
0x18002c00b  mov     rdx, [rsp+0B20h+var_AD0]
0x18002c010  mov     rdx, [rdx+48h]
0x18002c014  mov     rax, [rax+40h]
0x18002c018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c01d  mov     rsi, rax
0x18002c020  test    rax, rax
0x18002c023  jz      loc_18002C19A
0x18002c029  mov     rcx, [rax]
0x18002c02c  mov     rax, [rcx]
0x18002c02f  mov     rcx, rsi
0x18002c032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c037  test    cs:byte_1800CF404, 8
0x18002c03e  jz      loc_18002C136
0x18002c044  mov     word ptr [rbp+0A20h+var_830], r14w
0x18002c04c  mov     word ptr [rbp+0A20h+var_860], r14w
0x18002c054  mov     edx, [rdi+60h]
0x18002c057  lea     rcx, [rbp+0A20h+var_860]
0x18002c05e  call    ConvertPortNoToString
0x18002c063  mov     rax, [rsi]
0x18002c066  mov     rcx, rsi
0x18002c069  mov     rax, [rax+118h]
0x18002c070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c075  mov     r8, rax
0x18002c078  lea     rdx, aCompleteclosin_0; "CompleteClosing:Marking interface '%ws'"...
0x18002c07f  lea     rcx, [rbp+0A20h+var_830]
0x18002c086  call    FormatRRASErrorString
0x18002c08b  test    cs:byte_1800CF404, 8
0x18002c092  jz      loc_18002C136
0x18002c098  mov     rax, [rsi]
0x18002c09b  mov     rcx, rsi
0x18002c09e  mov     rax, [rax+118h]
0x18002c0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0aa  mov     rbx, rax
0x18002c0ad  mov     rcx, [rsi]
0x18002c0b0  mov     rax, [rcx+168h]
0x18002c0b7  lea     rdx, [rbp+0A20h+var_A50]
0x18002c0bb  mov     rcx, rsi
0x18002c0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0c3  mov     rcx, [rsi]
0x18002c0c6  mov     r8, [rcx+168h]
0x18002c0cd  mov     rcx, rsi
0x18002c0d0  test    rax, rax
0x18002c0d3  mov     rax, r8
0x18002c0d6  jz      short loc_18002C0DE
0x18002c0d8  lea     rdx, [rbp+0A20h+var_A40]
0x18002c0dc  jmp     short loc_18002C0FD
0x18002c0de  lea     rdx, [rbp+0A20h+var_A30]
0x18002c0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0e7  test    rax, rax
0x18002c0ea  jz      short loc_18002C104
0x18002c0ec  mov     rax, [rsi]
0x18002c0ef  lea     rdx, [rbp+0A20h+var_A20]
0x18002c0f3  mov     rcx, rsi
0x18002c0f6  mov     rax, [rax+168h]
0x18002c0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c102  jmp     short loc_18002C108
0x18002c104  lea     rax, [rbp+0A20h+var_A60]
0x18002c108  lea     r8, [rbp+0A20h+var_860]
0x18002c10f  mov     qword ptr [rsp+0B20h+var_AF8], r8
0x18002c114  mov     [rsp+0B20h+var_B00], rbx
0x18002c119  mov     r9, rax
0x18002c11c  lea     r8, [rbp+0A20h+var_830]
0x18002c123  lea     rdx, RasDdmParamTraceError
0x18002c12a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c131  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c136  mov     rcx, rsi; struct IDimInterface *
0x18002c139  call    ?InterfaceDisconnected@@YAXPEAUIDimInterface@@@Z; InterfaceDisconnected(IDimInterface *)
0x18002c13e  mov     rax, [rsi]
0x18002c141  mov     rcx, rsi
0x18002c144  mov     rax, [rax+48h]
0x18002c148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c14d  mov     rcx, [rsi]
0x18002c150  mov     rdx, [rcx+8]
0x18002c154  mov     rcx, rsi
0x18002c157  cmp     eax, 2
0x18002c15a  mov     rax, rdx
0x18002c15d  jz      short loc_18002C195
0x18002c15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c164  mov     rax, cs:g_pIDimInterfaceTable
0x18002c16b  mov     rcx, [rax]
0x18002c16e  mov     rbx, [rcx+48h]
0x18002c172  mov     rcx, [rsi]
0x18002c175  mov     rax, [rcx+10h]
0x18002c179  mov     rcx, rsi
0x18002c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c181  mov     rdx, rax
0x18002c184  mov     rcx, cs:g_pIDimInterfaceTable
0x18002c18b  mov     rax, rbx
0x18002c18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c193  jmp     short loc_18002C19A
0x18002c195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c19a  mov     rcx, cs:g_pIDimInterfaceTable
0x18002c1a1  mov     rax, [rcx]
0x18002c1a4  mov     rax, [rax+18h]
0x18002c1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ad  mov     rax, [rsp+0B20h+var_AD0]
0x18002c1b2  cmp     [rax+90h], r14d
0x18002c1b9  jnz     short loc_18002C1F5
0x18002c1bb  lea     rcx, [rax+5CCh]
0x18002c1c2  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x18002c1c9  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18002c1d0  test    rcx, rcx
0x18002c1d3  jz      short loc_18002C1F5
0x18002c1d5  cmp     [rcx], rax
0x18002c1d8  jnz     short loc_18002C1EB
0x18002c1da  cmp     [rcx+8], rdx
0x18002c1de  jz      short loc_18002C1F5
0x18002c1e0  cmp     [rcx], rax
0x18002c1e3  jnz     short loc_18002C1EB
  ... truncated ...
```
