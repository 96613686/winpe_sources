# CTiBus::AddInternal(int,ulong,ushort *,CTiDevice * *,tagDEVICE_PROBLEM_DETAILS *,int)

- ea: `0x1800a9f38`
- end: `0x1800aa79a`
- name: `?AddInternal@CTiBus@@AEAAJHKPEAGPEAPEAVCTiDevice@@PEAUtagDEVICE_PROBLEM_DETAILS@@H@Z`
- size: `2146`
- prototype: `__int64 __usercall@<rax>(CTiBus *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, struct CTiDevice **, struct tagDEVICE_PROBLEM_DETAILS *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800aa7a0`
- `0x1800aa7e4`

## callees

- `0x1800091a8`
- `0x1800180a8`
- `0x18002e600`
- `0x18003394c`
- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x1800598d0`
- `0x1800a9d1c`
- `0x1800a9f38`
- `0x1800aabc4`
- `0x1800aaf24`
- `0x1800abc78`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa0da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa19f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa23b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa306`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa0da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa19f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa23b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800aa306`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa06b`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa132`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa299`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa06b`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa132`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800aa299`

## string_xrefs

- `0x1800a9fce`: `TI_COMPAT_DEVICE`
- `0x1800aa02f`: `failed to create prop store`
- `0x1800aa173`: `InitPropVariantFromString(CompatibleIds) failed`
- `0x1800aa1de`: `pPropertyStore->SetValue(PKEY_Device_CompatibleIds) failed`
- `0x1800aa39e`: `CreateMultiSzFromString(HardwareIds) failed`
- `0x1800aa46c`: `CreateMultiSzFromString(Description) failed`
- `0x1800aa3f7`: `CreateMultiSzFromString(CompatibleIds) failed`

## pseudocode

```c
__int64 __fastcall CTiBus::AddInternal(
        CTiBus *this,
        int a2,
        unsigned int a3,
        unsigned __int16 *a4,
        struct CTiDevice **a5,
        struct tagDEVICE_PROBLEM_DETAILS *a6,
        int a7)
{
  CTiBus *v10; // rcx
  const WCHAR *v11; // rdx
  WCHAR *v12; // rsi
  int inited; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v15; // edx
  const char *v16; // rcx
  struct IPropertyStore *v17; // rdi
  CTiBus *v18; // rcx
  CTiBus *v19; // rcx
  unsigned int v20; // eax
  CTiDevice *v21; // rax
  CTiDevice *v22; // rdi
  unsigned int v23; // eax
  CTiDevice *v25; // rax
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  unsigned __int16 *v31; // [rsp+28h] [rbp-D8h]
  unsigned int v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR v34; // [rsp+70h] [rbp-90h] BYREF
  struct IPropertyStore *v35; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  void *Block; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v39; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR v40; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR prgsz; // [rsp+B0h] [rbp-50h] BYREF
  struct tagDEVICE_PROBLEM_DETAILS *v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v44; // [rsp+C4h] [rbp-3Ch]
  int v45; // [rsp+CCh] [rbp-34h]
  int v46; // [rsp+D0h] [rbp-30h]
  _DEVPROPERTY v47; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v48; // [rsp+110h] [rbp+10h]
  int v49; // [rsp+120h] [rbp+20h]
  int v50; // [rsp+124h] [rbp+24h]
  int v51; // [rsp+130h] [rbp+30h]
  unsigned int v52; // [rsp+134h] [rbp+34h]
  PCWSTR v53; // [rsp+138h] [rbp+38h]

  v42 = a6;
  v32 = a3;
  v35 = 0;
  v47.CompKey.Key.fmtid.Data1 = 0;
  v37 = 0;
  *(_OWORD *)ppropvar = 0;
  memset_0(&v47.CompKey.Key.fmtid.Data2, 0, 0x5Cu);
  Block = 0;
  v39 = 0;
  v11 = L"TS_INPT\\TS_KBD";
  v34 = 0;
  if ( !a2 )
    v11 = L"TS_INPT\\TS_MOU";
  v33 = 0;
  v12 = 0;
  v40 = L"TI_COMPAT_DEVICE";
  prgsz = v11;
  if ( !*((_DWORD *)this + 184) )
  {
    inited = CTiBus::CreateMultiSzFromString(v10, v11, (unsigned __int16 **)&Block, &v33);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 81;
        v16 = "CreateMultiSzFromString(HardwareIds) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    inited = CTiBus::CreateMultiSzFromString(v18, v40, &v39, &v33);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 82;
        v16 = "CreateMultiSzFromString(CompatibleIds) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    v47.CompKey.Key.fmtid.Data1 = -2082839770;
    v47.CompKey.Store = DEVPROP_STORE_SYSTEM;
    v47.Type = 7;
    v47.Buffer = &v32;
    *(_OWORD *)&v47.CompKey.Key.fmtid.Data2 = *(_OWORD *)&DEVPKEY_Device_SessionId.fmtid.Data2;
    v47.BufferSize = 4;
    inited = CTiBus::CreateMultiSzFromString(v19, a4, (unsigned __int16 **)&v34, &v33);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
          v20,
          (__int64)"CreateMultiSzFromString(Description) failed",
          inited);
      }
      v12 = (WCHAR *)v34;
      goto LABEL_72;
    }
    v49 = 1002;
    v50 = 0;
    v12 = (WCHAR *)v34;
    v52 = 2 * v33;
    v48 = xmmword_1801775A0;
    v51 = 8210;
    v53 = v34;
    goto LABEL_62;
  }
  inited = CPNPPropertyStore::CreateInstance(&v35);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 72;
      v16 = "failed to create prop store";
LABEL_9:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v16,
        inited);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  inited = InitPropVariantFromStringVector(&prgsz, 1u, ppropvar);
  if ( inited >= 0 )
  {
    v17 = v35;
    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v35->lpVtbl->SetValue)(
               v35,
               &PKEY_Device_HardwareIds,
               ppropvar);
    PropVariantClear(ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 74;
        v16 = "pPropertyStore->SetValue(PKEY_Device_HardwareIds) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    inited = InitPropVariantFromStringVector(&v40, 1u, ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 75;
        v16 = "InitPropVariantFromString(CompatibleIds) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v17->lpVtbl->SetValue)(
               v17,
               &PKEY_Device_CompatibleIds,
               ppropvar);
    PropVariantClear(ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 76;
        v16 = "pPropertyStore->SetValue(PKEY_Device_CompatibleIds) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    v43 = -2082839770;
    LOWORD(ppropvar[0]) = 19;
    v44 = *(_QWORD *)&DEVPKEY_Device_SessionId.fmtid.Data2;
    LODWORD(ppropvar[1]) = v32;
    v45 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&DEVPKEY_Device_SessionId.fmtid.Data2, 8));
    v46 = 6;
    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, int *, PROPVARIANT *))v17->lpVtbl->SetValue)(
               v17,
               &v43,
               ppropvar);
    PropVariantClear(ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 78;
        v16 = "pPropertyStore->SetValue(SessionIDKey) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    v34 = a4;
    inited = InitPropVariantFromStringVector(&v34, 1u, ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 79;
        v16 = "InitPropVariantFromString(Description) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, PROPVARIANT *))v17->lpVtbl->SetValue)(
               v17,
               &xmmword_1801775A0,
               ppropvar);
    PropVariantClear(ppropvar);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 80;
        v16 = "pPropertyStore->SetValue(PKEY_Device_SessionDescr) failed";
        goto LABEL_9;
      }
      goto LABEL_72;
    }
LABEL_62:
    if ( a2 )
    {
      v21 = (CTiDevice *)operator new(0x308u);
      v22 = v21;
      if ( v21 )
      {
        CTiDevice::CTiDevice(v21, v32, *((struct CTiNotify **)this + 82));
        *((_QWORD *)v22 + 86) = 0;
        *(_QWORD *)v22 = &CTiKeyboard::`vftable';
        *((_QWORD *)v22 + 87) = 0;
        *((_QWORD *)v22 + 89) = 0;
        *((_QWORD *)v22 + 95) = 0;
        *((_DWORD *)v22 + 192) = 0;
      }
      else
      {
        v22 = 0;
      }
      if ( !v22 )
        goto LABEL_67;
    }
    else
    {
      v25 = (CTiDevice *)operator new(0x2A8u);
      v22 = v25;
      if ( !v25 )
      {
LABEL_67:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
            v23,
            (__int64)"CTiDevice");
        }
        inited = -2147024882;
        goto LABEL_72;
      }
      CTiDevice::CTiDevice(v25, v32, *((struct CTiNotify **)this + 82));
      *(_QWORD *)v22 = &CTiMouse::`vftable';
    }
    inited = (*(__int64 (__fastcall **)(CTiDevice *))(*(_QWORD *)v22 + 8LL))(v22);
    if ( inited >= 0 )
    {
      inited = CTiBus::SetupDevice(this, v22, a4, v35, (unsigned __int16 *)Block, v39, &v47, 2u, v32, a7, v42);
      if ( inited >= 0 )
      {
        *((_DWORD *)v22 + 154) = 1;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 89) + 8LL))(*((_QWORD *)this + 89));
        *a5 = v22;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_94;
      }
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      v29 = 86;
      v30 = "SetupDevice failed";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_94:
        if ( v22 )
        {
          if ( *((_QWORD *)v22 + 3) || *((_QWORD *)v22 + 4) )
            CTiBus::RemoveDevice(this, v22, v26, v27);
          else
            (**(void (__fastcall ***)(CTiDevice *, __int64))v22)(v22, 1);
        }
        goto LABEL_72;
      }
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      v29 = 85;
      v30 = "failed to init pDev";
    }
    LODWORD(v31) = inited;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
      v28,
      (__int64)v30,
      v31);
    goto LABEL_94;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 73;
    v16 = "InitPropVariantFromString(HardwareIds) failed";
    goto LABEL_9;
  }
LABEL_72:
  if ( Block )
    operator delete(Block);
  if ( v39 )
    operator delete(v39);
  if ( v12 )
    operator delete(v12);
  if ( v35 )
    ((void (__fastcall *)(struct IPropertyStore *))v35->lpVtbl->Release)(v35);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800a9f38  mov     [rsp-8+arg_8], rbx
0x1800a9f3d  push    rbp
0x1800a9f3e  push    rsi
0x1800a9f3f  push    rdi
0x1800a9f40  push    r12
0x1800a9f42  push    r13
0x1800a9f44  push    r14
0x1800a9f46  push    r15
0x1800a9f48  lea     rbp, [rsp-50h]
0x1800a9f4d  sub     rsp, 150h
0x1800a9f54  mov     rax, cs:__security_cookie
0x1800a9f5b  xor     rax, rsp
0x1800a9f5e  mov     [rbp+80h+var_40], rax
0x1800a9f62  mov     rax, [rbp+80h+arg_28]
0x1800a9f69  xor     ebx, ebx
0x1800a9f6b  mov     r13, [rbp+80h+arg_20]
0x1800a9f72  mov     r12d, edx
0x1800a9f75  mov     [rbp+80h+var_C8], rax
0x1800a9f79  mov     r14, rcx
0x1800a9f7c  mov     [rsp+180h+var_120], r8d
0x1800a9f81  lea     rcx, [rbp+80h+var_A0.CompKey.Key.fmtid.Data2]; void *
0x1800a9f85  xorps   xmm0, xmm0
0x1800a9f88  mov     [rsp+180h+var_108], rbx
0x1800a9f8d  xor     eax, eax
0x1800a9f8f  mov     [rbp+80h+var_A0.CompKey.Key.fmtid.Data1], ebx
0x1800a9f92  lea     r8d, [rbx+5Ch]; Size
0x1800a9f96  mov     [rbp+80h+var_F0], rax
0x1800a9f9a  xor     edx, edx; Val
0x1800a9f9c  mov     r15, r9
0x1800a9f9f  movups  xmmword ptr [rbp+80h+ppropvar], xmm0
0x1800a9fa3  call    memset_0
0x1800a9fa8  test    r12d, r12d
0x1800a9fab  mov     [rbp+80h+Block], rbx
0x1800a9faf  lea     rax, aTsInptTsMou; "TS_INPT\\TS_MOU"
0x1800a9fb6  mov     [rbp+80h+var_E0], rbx
0x1800a9fba  lea     rdx, aTsInptTsKbd; "TS_INPT\\TS_KBD"
0x1800a9fc1  mov     [rsp+180h+var_110], rbx
0x1800a9fc6  cmovz   rdx, rax; unsigned __int16 *
0x1800a9fca  mov     [rsp+180h+var_118], ebx
0x1800a9fce  lea     rax, aTiCompatDevice; "TI_COMPAT_DEVICE"
0x1800a9fd5  mov     esi, ebx
0x1800a9fd7  mov     [rbp+80h+var_D8], rax
0x1800a9fdb  mov     [rbp+80h+prgsz], rdx
0x1800a9fdf  cmp     [r14+2E0h], ebx
0x1800a9fe6  jz      loc_1800AA355
0x1800a9fec  lea     rcx, [rsp+180h+var_108]; struct IPropertyStore **
0x1800a9ff1  call    ?CreateInstance@CPNPPropertyStore@@SAJPEAPEAUIPropertyStore@@@Z; CPNPPropertyStore::CreateInstance(IPropertyStore * *)
0x1800a9ff6  mov     ebx, eax
0x1800a9ff8  test    eax, eax
0x1800a9ffa  jns     short loc_1800AA05E
0x1800a9ffc  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa003  lea     rcx, WPP_GLOBAL_Control
0x1800aa00a  cmp     rax, rcx
0x1800aa00d  jz      loc_1800AA595
0x1800aa013  test    byte ptr [rax+1Ch], 8
0x1800aa017  jz      loc_1800AA595
0x1800aa01d  cmp     byte ptr [rax+19h], 2
0x1800aa021  jb      loc_1800AA595
0x1800aa027  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa02c  lea     edx, [rsi+48h]
0x1800aa02f  lea     rcx, aFailedToCreate_66; "failed to create prop store"
0x1800aa036  mov     dword ptr [rsp+180h+var_158], ebx
0x1800aa03a  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800aa041  mov     [rsp+180h+var_160], rcx
0x1800aa046  mov     r9d, eax
0x1800aa049  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa050  mov     rcx, [rcx+10h]
0x1800aa054  call    WPP_SF_DsD
0x1800aa059  jmp     loc_1800AA595
0x1800aa05e  lea     r8, [rbp+80h+ppropvar]; ppropvar
0x1800aa062  mov     edx, 1; cElems
0x1800aa067  lea     rcx, [rbp+80h+prgsz]; prgsz
0x1800aa06b  call    cs:__imp_InitPropVariantFromStringVector
0x1800aa071  mov     ebx, eax
0x1800aa073  test    eax, eax
0x1800aa075  jns     short loc_1800AA0B5
0x1800aa077  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa07e  lea     rcx, WPP_GLOBAL_Control
0x1800aa085  cmp     rax, rcx
0x1800aa088  jz      loc_1800AA595
0x1800aa08e  test    byte ptr [rax+1Ch], 8
0x1800aa092  jz      loc_1800AA595
0x1800aa098  cmp     byte ptr [rax+19h], 2
0x1800aa09c  jb      loc_1800AA595
0x1800aa0a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa0a7  mov     edx, 49h ; 'I'
0x1800aa0ac  lea     rcx, aInitpropvarian_4; "InitPropVariantFromString(HardwareIds) "...
0x1800aa0b3  jmp     short loc_1800AA036
0x1800aa0b5  mov     rdi, [rsp+180h+var_108]
0x1800aa0ba  lea     r8, [rbp+80h+ppropvar]
0x1800aa0be  lea     rdx, PKEY_Device_HardwareIds
0x1800aa0c5  mov     rcx, rdi
0x1800aa0c8  mov     rax, [rdi]
0x1800aa0cb  mov     rax, [rax+30h]
0x1800aa0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa0d4  lea     rcx, [rbp+80h+ppropvar]; pvar
0x1800aa0d8  mov     ebx, eax
0x1800aa0da  call    cs:__imp_PropVariantClear
0x1800aa0e0  test    ebx, ebx
0x1800aa0e2  jns     short loc_1800AA125
0x1800aa0e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa0eb  lea     rcx, WPP_GLOBAL_Control
0x1800aa0f2  cmp     rax, rcx
0x1800aa0f5  jz      loc_1800AA595
0x1800aa0fb  test    byte ptr [rax+1Ch], 8
0x1800aa0ff  jz      loc_1800AA595
0x1800aa105  cmp     byte ptr [rax+19h], 2
0x1800aa109  jb      loc_1800AA595
0x1800aa10f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa114  mov     edx, 4Ah ; 'J'
0x1800aa119  lea     rcx, aPpropertystore; "pPropertyStore->SetValue(PKEY_Device_Ha"...
0x1800aa120  jmp     loc_1800AA036
0x1800aa125  lea     r8, [rbp+80h+ppropvar]; ppropvar
0x1800aa129  mov     edx, 1; cElems
0x1800aa12e  lea     rcx, [rbp+80h+var_D8]; prgsz
0x1800aa132  call    cs:__imp_InitPropVariantFromStringVector
0x1800aa138  mov     ebx, eax
0x1800aa13a  test    eax, eax
0x1800aa13c  jns     short loc_1800AA17F
0x1800aa13e  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa145  lea     rcx, WPP_GLOBAL_Control
0x1800aa14c  cmp     rax, rcx
0x1800aa14f  jz      loc_1800AA595
0x1800aa155  test    byte ptr [rax+1Ch], 8
0x1800aa159  jz      loc_1800AA595
0x1800aa15f  cmp     byte ptr [rax+19h], 2
0x1800aa163  jb      loc_1800AA595
0x1800aa169  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa16e  mov     edx, 4Bh ; 'K'
0x1800aa173  lea     rcx, aInitpropvarian_3; "InitPropVariantFromString(CompatibleIds"...
0x1800aa17a  jmp     loc_1800AA036
0x1800aa17f  mov     rax, [rdi]
0x1800aa182  lea     r8, [rbp+80h+ppropvar]
0x1800aa186  lea     rdx, PKEY_Device_CompatibleIds
0x1800aa18d  mov     rcx, rdi
0x1800aa190  mov     rax, [rax+30h]
0x1800aa194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa199  lea     rcx, [rbp+80h+ppropvar]; pvar
0x1800aa19d  mov     ebx, eax
0x1800aa19f  call    cs:__imp_PropVariantClear
0x1800aa1a5  test    ebx, ebx
0x1800aa1a7  jns     short loc_1800AA1EA
0x1800aa1a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa1b0  lea     rcx, WPP_GLOBAL_Control
0x1800aa1b7  cmp     rax, rcx
0x1800aa1ba  jz      loc_1800AA595
0x1800aa1c0  test    byte ptr [rax+1Ch], 8
0x1800aa1c4  jz      loc_1800AA595
0x1800aa1ca  cmp     byte ptr [rax+19h], 2
0x1800aa1ce  jb      loc_1800AA595
0x1800aa1d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa1d9  mov     edx, 4Ch ; 'L'
0x1800aa1de  lea     rcx, aPpropertystore_0; "pPropertyStore->SetValue(PKEY_Device_Co"...
0x1800aa1e5  jmp     loc_1800AA036
0x1800aa1ea  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data2
0x1800aa1f1  mov     eax, 13h
0x1800aa1f6  mov     [rbp+80h+var_C0], 83DA6326h
0x1800aa1fd  mov     word ptr [rbp+80h+ppropvar], ax
0x1800aa201  lea     r8, [rbp+80h+ppropvar]
0x1800aa205  mov     eax, [rsp+180h+var_120]
0x1800aa209  lea     rdx, [rbp+80h+var_C0]
0x1800aa20d  movsd   [rbp+80h+var_BC], xmm0
0x1800aa212  mov     rcx, rdi
0x1800aa215  mov     dword ptr [rbp+80h+ppropvar+8], eax
0x1800aa218  psrldq  xmm0, 8
0x1800aa21d  movd    [rbp+80h+var_B4], xmm0
0x1800aa222  mov     [rbp+80h+var_B0], 6
0x1800aa229  mov     rax, [rdi]
0x1800aa22c  mov     rax, [rax+30h]
0x1800aa230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa235  lea     rcx, [rbp+80h+ppropvar]; pvar
0x1800aa239  mov     ebx, eax
0x1800aa23b  call    cs:__imp_PropVariantClear
0x1800aa241  test    ebx, ebx
0x1800aa243  jns     short loc_1800AA286
0x1800aa245  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa24c  lea     rcx, WPP_GLOBAL_Control
0x1800aa253  cmp     rax, rcx
0x1800aa256  jz      loc_1800AA595
0x1800aa25c  test    byte ptr [rax+1Ch], 8
0x1800aa260  jz      loc_1800AA595
0x1800aa266  cmp     byte ptr [rax+19h], 2
0x1800aa26a  jb      loc_1800AA595
0x1800aa270  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa275  mov     edx, 4Eh ; 'N'
0x1800aa27a  lea     rcx, aPpropertystore_2; "pPropertyStore->SetValue(SessionIDKey) "...
0x1800aa281  jmp     loc_1800AA036
0x1800aa286  lea     r8, [rbp+80h+ppropvar]; ppropvar
0x1800aa28a  mov     [rsp+180h+var_110], r15
0x1800aa28f  mov     edx, 1; cElems
0x1800aa294  lea     rcx, [rsp+180h+var_110]; prgsz
0x1800aa299  call    cs:__imp_InitPropVariantFromStringVector
0x1800aa29f  mov     ebx, eax
0x1800aa2a1  test    eax, eax
0x1800aa2a3  jns     short loc_1800AA2E6
0x1800aa2a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa2ac  lea     rcx, WPP_GLOBAL_Control
0x1800aa2b3  cmp     rax, rcx
0x1800aa2b6  jz      loc_1800AA595
0x1800aa2bc  test    byte ptr [rax+1Ch], 8
0x1800aa2c0  jz      loc_1800AA595
0x1800aa2c6  cmp     byte ptr [rax+19h], 2
0x1800aa2ca  jb      loc_1800AA595
0x1800aa2d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa2d5  mov     edx, 4Fh ; 'O'
0x1800aa2da  lea     rcx, aInitpropvarian_1; "InitPropVariantFromString(Description) "...
0x1800aa2e1  jmp     loc_1800AA036
0x1800aa2e6  mov     rax, [rdi]
0x1800aa2e9  lea     r8, [rbp+80h+ppropvar]
0x1800aa2ed  lea     rdx, xmmword_1801775A0
0x1800aa2f4  mov     rcx, rdi
0x1800aa2f7  mov     rax, [rax+30h]
0x1800aa2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa300  lea     rcx, [rbp+80h+ppropvar]; pvar
0x1800aa304  mov     ebx, eax
0x1800aa306  call    cs:__imp_PropVariantClear
0x1800aa30c  test    ebx, ebx
0x1800aa30e  jns     loc_1800AA4D5
0x1800aa314  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa31b  lea     rcx, WPP_GLOBAL_Control
0x1800aa322  cmp     rax, rcx
0x1800aa325  jz      loc_1800AA595
0x1800aa32b  test    byte ptr [rax+1Ch], 8
0x1800aa32f  jz      loc_1800AA595
0x1800aa335  cmp     byte ptr [rax+19h], 2
0x1800aa339  jb      loc_1800AA595
0x1800aa33f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa344  mov     edx, 50h ; 'P'
0x1800aa349  lea     rcx, aPpropertystore_1; "pPropertyStore->SetValue(PKEY_Device_Se"...
0x1800aa350  jmp     loc_1800AA036
0x1800aa355  lea     r9, [rsp+180h+var_118]; unsigned int *
0x1800aa35a  lea     r8, [rbp+80h+Block]; unsigned __int16 **
0x1800aa35e  call    ?CreateMultiSzFromString@CTiBus@@AEAAJPEBGPEAPEAGPEAK@Z; CTiBus::CreateMultiSzFromString(ushort const *,ushort * *,ulong *)
0x1800aa363  mov     ebx, eax
0x1800aa365  test    eax, eax
0x1800aa367  jns     short loc_1800AA3AA
0x1800aa369  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa370  lea     rcx, WPP_GLOBAL_Control
0x1800aa377  cmp     rax, rcx
0x1800aa37a  jz      loc_1800AA595
0x1800aa380  test    byte ptr [rax+1Ch], 8
0x1800aa384  jz      loc_1800AA595
0x1800aa38a  cmp     byte ptr [rax+19h], 2
0x1800aa38e  jb      loc_1800AA595
0x1800aa394  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa399  mov     edx, 51h ; 'Q'
0x1800aa39e  lea     rcx, aCreatemultiszf_1; "CreateMultiSzFromString(HardwareIds) fa"...
0x1800aa3a5  jmp     loc_1800AA036
0x1800aa3aa  mov     rdx, [rbp+80h+var_D8]; unsigned __int16 *
0x1800aa3ae  lea     r9, [rsp+180h+var_118]; unsigned int *
0x1800aa3b3  lea     r8, [rbp+80h+var_E0]; unsigned __int16 **
0x1800aa3b7  call    ?CreateMultiSzFromString@CTiBus@@AEAAJPEBGPEAPEAGPEAK@Z; CTiBus::CreateMultiSzFromString(ushort const *,ushort * *,ulong *)
0x1800aa3bc  mov     ebx, eax
0x1800aa3be  test    eax, eax
0x1800aa3c0  jns     short loc_1800AA403
0x1800aa3c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa3c9  lea     rcx, WPP_GLOBAL_Control
0x1800aa3d0  cmp     rax, rcx
0x1800aa3d3  jz      loc_1800AA595
0x1800aa3d9  test    byte ptr [rax+1Ch], 8
0x1800aa3dd  jz      loc_1800AA595
0x1800aa3e3  cmp     byte ptr [rax+19h], 2
0x1800aa3e7  jb      loc_1800AA595
0x1800aa3ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa3f2  mov     edx, 52h ; 'R'
0x1800aa3f7  lea     rcx, aCreatemultiszf_0; "CreateMultiSzFromString(CompatibleIds) "...
0x1800aa3fe  jmp     loc_1800AA036
0x1800aa403  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data2
0x1800aa40a  lea     rax, [rsp+180h+var_120]
0x1800aa40f  mov     [rbp+80h+var_A0.CompKey.Key.fmtid.Data1], 83DA6326h
0x1800aa416  lea     r9, [rsp+180h+var_118]; unsigned int *
0x1800aa41b  mov     [rbp+80h+var_A0.CompKey.Store], esi
0x1800aa41e  lea     r8, [rsp+180h+var_110]; unsigned __int16 **
0x1800aa423  mov     [rbp+80h+var_A0.Type], 7
0x1800aa42a  mov     rdx, r15; unsigned __int16 *
0x1800aa42d  mov     [rbp+80h+var_A0.Buffer], rax
0x1800aa431  movdqu  xmmword ptr [rbp+80h+var_A0.CompKey.Key.fmtid.Data2], xmm0
0x1800aa436  mov     [rbp+80h+var_A0.BufferSize], 4
0x1800aa43d  call    ?CreateMultiSzFromString@CTiBus@@AEAAJPEBGPEAPEAGPEAK@Z; CTiBus::CreateMultiSzFromString(ushort const *,ushort * *,ulong *)
0x1800aa442  mov     ebx, eax
0x1800aa444  test    eax, eax
0x1800aa446  jns     short loc_1800AA4A5
0x1800aa448  mov     rax, cs:WPP_GLOBAL_Control
0x1800aa44f  lea     rcx, WPP_GLOBAL_Control
0x1800aa456  cmp     rax, rcx
0x1800aa459  jz      short loc_1800AA49B
0x1800aa45b  test    byte ptr [rax+1Ch], 8
0x1800aa45f  jz      short loc_1800AA49B
0x1800aa461  cmp     byte ptr [rax+19h], 2
0x1800aa465  jb      short loc_1800AA49B
0x1800aa467  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800aa46c  lea     rcx, aCreatemultiszf; "CreateMultiSzFromString(Description) fa"...
0x1800aa473  mov     dword ptr [rsp+180h+var_158], ebx
0x1800aa477  mov     [rsp+180h+var_160], rcx
0x1800aa47c  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800aa483  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa48a  mov     edx, 53h ; 'S'
0x1800aa48f  mov     r9d, eax
0x1800aa492  mov     rcx, [rcx+10h]
0x1800aa496  call    WPP_SF_DsD
  ... truncated ...
```
