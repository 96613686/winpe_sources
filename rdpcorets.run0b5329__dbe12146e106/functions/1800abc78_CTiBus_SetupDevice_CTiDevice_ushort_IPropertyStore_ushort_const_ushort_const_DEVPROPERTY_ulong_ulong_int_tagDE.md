# CTiBus::SetupDevice(CTiDevice *,ushort *,IPropertyStore *,ushort const *,ushort const *,_DEVPROPERTY *,ulong,ulong,int,tagDEVICE_PROBLEM_DETAILS *)

- ea: `0x1800abc78`
- end: `0x1800ac379`
- name: `?SetupDevice@CTiBus@@AEAAJPEAVCTiDevice@@PEAGPEAUIPropertyStore@@PEBG3PEAU_DEVPROPERTY@@KKHPEAUtagDEVICE_PROBLEM_DETAILS@@@Z`
- size: `1793`
- prototype: `int(CTiBus *__hidden this, struct CTiDevice *, unsigned __int16 *, struct IPropertyStore *, const unsigned __int16 *, const unsigned __int16 *, struct _DEVPROPERTY *, unsigned int, unsigned int, int, struct tagDEVICE_PROBLEM_DETAILS *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a9f38`
- `0x1800ab494`
- `0x1800ab8c0`

## callees

- `0x1800041bc`
- `0x1800091a8`
- `0x180012200`
- `0x18001b068`
- `0x18002e27c`
- `0x18002e600`
- `0x18003394c`
- `0x180033958`
- `0x1800598d0`
- `0x1800aa824`
- `0x1800abc78`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800abd82`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800abd82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abcbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abcbe`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800abee1`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800ac305`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800abee1`
- `RDPBASE!PAL_System_CritSecEnter` at `0x1800ac305`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac0e7`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac1d0`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac2e8`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac0e7`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac1d0`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800ac2e8`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800abcef`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800abcef`

## string_xrefs

- `0x1800ac05b`: `CreateSwDevice bus failed`
- `0x1800ac2a2`: `CreateSwDevice child failed`
- `0x1800ac36d`: `Invalid device registry entry`

## pseudocode

```c
__int64 __fastcall CTiBus::SetupDevice(
        CTiBus *this,
        struct CTiDevice *a2,
        unsigned __int16 *a3,
        struct IPropertyStore *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct _DEVPROPERTY *Src,
        unsigned int a8,
        unsigned int a9,
        int a10,
        struct tagDEVICE_PROBLEM_DETAILS *a11)
{
  const IID *v13; // rbx
  int *v15; // rdi
  int SwDevice; // ebx
  unsigned int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  struct _DEVPROPERTY *v20; // rdx
  __int64 v21; // r8
  struct _DEVPROPERTY *v22; // r12
  unsigned int v23; // ebx
  __int64 v24; // rsi
  struct _DEVPROPERTY *v25; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  CTiBus *v31; // rcx
  __int64 v32; // r8
  int v33; // r9d
  unsigned int v34; // eax
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  int v38; // edx
  const char *v39; // rcx
  int v40; // eax
  __int64 v41; // r8
  _QWORD *v42; // rax
  __int64 v43; // rcx
  unsigned int v45; // eax
  int v46; // edx
  const char *v47; // rcx
  __int64 v48; // rcx
  bool v49; // zf
  struct tagDEVICE_PROBLEM_DETAILS *v50; // [rsp+28h] [rbp-71h]
  unsigned int v51; // [rsp+60h] [rbp-39h] BYREF
  int v52; // [rsp+64h] [rbp-35h] BYREF
  int v53; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v54; // [rsp+6Ch] [rbp-2Dh] BYREF
  unsigned __int16 *v55; // [rsp+70h] [rbp-29h] BYREF
  const char *v56; // [rsp+78h] [rbp-21h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v58; // [rsp+90h] [rbp-9h]
  char *v59; // [rsp+E0h] [rbp+47h] BYREF
  int v60; // [rsp+E8h] [rbp+4Fh]
  unsigned __int16 *v61; // [rsp+F0h] [rbp+57h]
  struct IPropertyStore *v62; // [rsp+F8h] [rbp+5Fh]

  v62 = a4;
  v61 = a3;
  LODWORD(v59) = 0;
  v51 = 0;
  v13 = (const IID *)((char *)a2 + 560);
  if ( this != a2 )
  {
    GetSystemTimeAsFileTime((LPFILETIME)a2 + 70);
    *((_QWORD *)a2 + 71) = a2;
  }
  v15 = (int *)((char *)this + 736);
  if ( !*((_DWORD *)this + 184) )
  {
    v24 = a8;
    v60 = a8 + 1;
    v25 = (struct _DEVPROPERTY *)operator new[](saturated_mul(a8 + 1, 0x30u));
    v22 = v25;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DEVPROPERTY");
      }
      return (unsigned int)-2147024882;
    }
    v20 = Src;
    if ( Src )
    {
      memcpy_0(v25, Src, 48 * v24);
      v15 = (int *)((char *)this + 736);
    }
    v27 = v24;
    v22[v27].CompKey.Key.fmtid = 0;
    *(_OWORD *)&v22[v27].CompKey.Key.pid = 0;
    *(_OWORD *)&v22[v27].Type = 0;
    v22[v27].CompKey.Key.fmtid = PKEY_TIBUS_MUID.fmtid;
    v22[v27].Buffer = (PVOID)v13;
    v23 = v60;
    v22[v27].CompKey.Key.pid = 1001;
    v22[v27].Type = 13;
    v22[v27].BufferSize = 16;
LABEL_25:
    v28 = *((_QWORD *)this + 82);
    if ( *(_DWORD *)(v28 + 80) )
      PAL_System_CritSecEnter(*(_QWORD *)(v28 + 72), v20, v21);
    v29 = *v15;
    v60 = 1;
    if ( this == a2 )
    {
      if ( v29 )
      {
        SwDevice = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, struct IPropertyStore *, _QWORD, char *))(**((_QWORD **)this + 91) + 48LL))(
                     *((_QWORD *)this + 91),
                     v61,
                     v62,
                     0,
                     (char *)this + 24);
        if ( SwDevice < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v34 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
            v34,
            (__int64)"AddBusEnumerator failed",
            SwDevice);
        }
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v53 = a10;
          v54 = a9;
          v55 = v61;
          v56 = "TiBus creation: AddBusEnumerator result";
          v52 = SwDevice;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v31,
            (unsigned int)byte_1801A2B9B,
            v32,
            v33,
            (__int64)&v56,
            (__int64)&v55,
            (__int64)&v54,
            (__int64)&v53,
            (__int64)&v52);
        }
        goto LABEL_41;
      }
      SwDevice = CTiBus::CreateSwDevice(
                   (CTiBus *)((char *)this + 744),
                   v61,
                   0,
                   a5,
                   a6,
                   (const unsigned __int16 *)v50,
                   v22,
                   v23,
                   1,
                   (struct HSWDEVICE__ **)this + 93,
                   (unsigned __int16 *)this + 376);
      if ( SwDevice < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v50) = SwDevice;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
            v35,
            (__int64)"CreateSwDevice bus failed",
            v50);
        }
LABEL_41:
        if ( SwDevice < 0 )
          goto LABEL_57;
      }
LABEL_42:
      if ( SwDevice == 1 )
      {
        if ( this != a2 )
        {
          SwDevice = CTiBus::CheckDeviceValid(v31, a2, a9, (int *)&v59, &v51, a11);
          if ( SwDevice < 0 )
          {
            v36 = *((_QWORD *)this + 82);
            if ( *(_DWORD *)(v36 + 80) )
              PAL_System_CritSecLeave(*(_QWORD *)(v36 + 72));
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_59;
            }
            v37 = RdpWppGetCurrentThreadActivityIdPrefix();
            v38 = 65;
            v39 = "Check Device Valid failed";
            goto LABEL_51;
          }
          v60 = (int)v59;
        }
        v48 = *((_QWORD *)this + 82);
        if ( *(_DWORD *)(v48 + 80) )
          PAL_System_CritSecLeave(*(_QWORD *)(v48 + 72));
        if ( v60 )
        {
          v49 = *((_DWORD *)a2 + 4) == 0;
          v59 = (char *)a2 + 8;
          if ( !v49 )
            PAL_System_CritSecEnter(*((_QWORD *)a2 + 1), v30, v32);
          CTiDevice::SignalReady(a2, 0);
          CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
          goto LABEL_59;
        }
        if ( (int)v51 > 0 )
          SwDevice = (unsigned __int16)v51 | 0x80070000;
        else
          SwDevice = v51;
        if ( SwDevice >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_59:
          if ( v22 )
            operator delete(v22);
          return (unsigned int)SwDevice;
        }
        v37 = RdpWppGetCurrentThreadActivityIdPrefix();
        v38 = 66;
        v39 = "Invalid device registry entry";
LABEL_51:
        LODWORD(v50) = SwDevice;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
          v37,
          (__int64)v39,
          v50);
        goto LABEL_59;
      }
      goto LABEL_56;
    }
    if ( v29 )
    {
      v40 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, struct IPropertyStore *, _QWORD, _DWORD, char *))(**((_QWORD **)this + 3) + 88LL))(
              *((_QWORD *)this + 3),
              v61,
              v62,
              0,
              0,
              (char *)a2 + 24);
      SwDevice = v40;
      if ( a10 && v40 == -2147483638 )
      {
        SwDevice = 0;
LABEL_56:
        v41 = *((_QWORD *)this + 82);
        v42 = *(_QWORD **)(v41 + 64);
        *((_QWORD *)a2 + 84) = v42;
        *((_QWORD *)a2 + 83) = v41 + 56;
        *v42 = (char *)a2 + 664;
        ++*(_DWORD *)(v41 + 48);
        *(_QWORD *)(v41 + 64) = (char *)a2 + 664;
        goto LABEL_57;
      }
      if ( v40 >= 0 )
        goto LABEL_42;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = RdpWppGetCurrentThreadActivityIdPrefix();
        v46 = 62;
        v47 = "AddChild failed";
LABEL_72:
        LODWORD(v50) = SwDevice;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v46,
          (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
          v45,
          (__int64)v47,
          v50);
      }
    }
    else
    {
      SwDevice = CTiBus::CreateSwDevice(
                   (struct CTiDevice *)((char *)a2 + 32),
                   v61,
                   (const unsigned __int16 *)this + 376,
                   a5,
                   a6,
                   (const unsigned __int16 *)v50,
                   v22,
                   v23,
                   0,
                   (struct HSWDEVICE__ **)a2 + 4,
                   (unsigned __int16 *)a2 + 20);
      if ( SwDevice >= 0 )
        goto LABEL_42;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = RdpWppGetCurrentThreadActivityIdPrefix();
        v46 = 63;
        v47 = "CreateSwDevice child failed";
        goto LABEL_72;
      }
    }
LABEL_57:
    v43 = *((_QWORD *)this + 82);
    if ( *(_DWORD *)(v43 + 80) )
      PAL_System_CritSecLeave(*(_QWORD *)(v43 + 72));
    goto LABEL_59;
  }
  *(_OWORD *)ppropvar = 0;
  v58 = 0;
  SwDevice = InitPropVariantFromCLSID(v13, ppropvar);
  if ( SwDevice < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 56;
      v19 = "failed to init PKEY_TIBUS_MUID";
LABEL_9:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
        v17,
        (__int64)v19,
        SwDevice);
      return (unsigned int)SwDevice;
    }
    return (unsigned int)SwDevice;
  }
  SwDevice = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))a4->lpVtbl->SetValue)(
               a4,
               &PKEY_TIBUS_MUID,
               ppropvar);
  PropVariantClear(ppropvar);
  if ( SwDevice >= 0 )
  {
    v22 = 0;
    v23 = 0;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 57;
    v19 = "failed to set PKEY_TIBUS_MUID";
    goto LABEL_9;
  }
  return (unsigned int)SwDevice;
}

```

## disassembly

```asm
0x1800abc78  mov     [rsp-8+arg_18], r9
0x1800abc7d  mov     [rsp-8+arg_10], r8
0x1800abc82  push    rbp
0x1800abc83  push    rbx
0x1800abc84  push    rsi
0x1800abc85  push    rdi
0x1800abc86  push    r12
0x1800abc88  push    r13
0x1800abc8a  push    r15
0x1800abc8c  lea     rbp, [rsp-7]
0x1800abc91  sub     rsp, 0A0h
0x1800abc98  mov     dword ptr [rbp+37h+arg_0], 0
0x1800abc9f  mov     rsi, r9
0x1800abca2  mov     [rbp+37h+var_70], 0
0x1800abca9  mov     r13, rdx
0x1800abcac  lea     rbx, [rdx+230h]
0x1800abcb3  mov     r15, rcx
0x1800abcb6  cmp     rcx, rdx
0x1800abcb9  jz      short loc_1800ABCCB
0x1800abcbb  mov     rcx, rbx; lpSystemTimeAsFileTime
0x1800abcbe  call    cs:__imp_GetSystemTimeAsFileTime
0x1800abcc4  mov     [r13+238h], r13
0x1800abccb  lea     rdi, [r15+2E0h]
0x1800abcd2  cmp     dword ptr [rdi], 0
0x1800abcd5  jz      loc_1800ABDDA
0x1800abcdb  xorps   xmm0, xmm0
0x1800abcde  lea     rdx, [rbp+37h+ppropvar]; ppropvar
0x1800abce2  xor     eax, eax
0x1800abce4  mov     rcx, rbx; clsid
0x1800abce7  movups  xmmword ptr [rbp+37h+ppropvar], xmm0
0x1800abceb  mov     [rbp+37h+var_40], rax
0x1800abcef  call    cs:__imp_InitPropVariantFromCLSID
0x1800abcf5  mov     ebx, eax
0x1800abcf7  test    eax, eax
0x1800abcf9  jns     short loc_1800ABD62
0x1800abcfb  mov     rax, cs:WPP_GLOBAL_Control
0x1800abd02  lea     rsi, WPP_GLOBAL_Control
0x1800abd09  cmp     rax, rsi
0x1800abd0c  jz      loc_1800AC1E3
0x1800abd12  test    byte ptr [rax+1Ch], 8
0x1800abd16  jz      loc_1800AC1E3
0x1800abd1c  mov     dil, 2
0x1800abd1f  cmp     [rax+19h], dil
0x1800abd23  jb      loc_1800AC1E3
0x1800abd29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800abd2e  mov     edx, 38h ; '8'
0x1800abd33  lea     rcx, aFailedToInitPk; "failed to init PKEY_TIBUS_MUID"
0x1800abd3a  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800abd3e  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800abd45  mov     [rsp+0D0h+var_B0], rcx
0x1800abd4a  mov     r9d, eax
0x1800abd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abd54  mov     rcx, [rcx+10h]
0x1800abd58  call    WPP_SF_DsD
0x1800abd5d  jmp     loc_1800AC1E3
0x1800abd62  mov     rax, [rsi]
0x1800abd65  lea     r8, [rbp+37h+ppropvar]
0x1800abd69  lea     rdx, ?PKEY_TIBUS_MUID@@3U_tagpropertykey@@B; _tagpropertykey const PKEY_TIBUS_MUID
0x1800abd70  mov     rcx, rsi
0x1800abd73  mov     rax, [rax+30h]
0x1800abd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd7c  lea     rcx, [rbp+37h+ppropvar]; pvar
0x1800abd80  mov     ebx, eax
0x1800abd82  call    cs:__imp_PropVariantClear
0x1800abd88  test    ebx, ebx
0x1800abd8a  jns     short loc_1800ABDD0
0x1800abd8c  mov     rax, cs:WPP_GLOBAL_Control
0x1800abd93  lea     rsi, WPP_GLOBAL_Control
0x1800abd9a  cmp     rax, rsi
0x1800abd9d  jz      loc_1800AC1E3
0x1800abda3  test    byte ptr [rax+1Ch], 8
0x1800abda7  jz      loc_1800AC1E3
0x1800abdad  mov     dil, 2
0x1800abdb0  cmp     [rax+19h], dil
0x1800abdb4  jb      loc_1800AC1E3
0x1800abdba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800abdbf  mov     edx, 39h ; '9'
0x1800abdc4  lea     rcx, aFailedToSetPke_4; "failed to set PKEY_TIBUS_MUID"
0x1800abdcb  jmp     loc_1800ABD3A
0x1800abdd0  xor     r12d, r12d
0x1800abdd3  xor     ebx, ebx
0x1800abdd5  jmp     loc_1800ABED0
0x1800abdda  mov     esi, [rbp+37h+arg_38]
0x1800abddd  lea     eax, [rsi+1]
0x1800abde0  mov     ecx, eax
0x1800abde2  mov     [rbp+37h+arg_8], eax
0x1800abde5  mov     eax, 30h ; '0'
0x1800abdea  mul     rcx
0x1800abded  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800abdf4  cmovb   rax, rcx
0x1800abdf8  mov     rcx, rax; unsigned __int64
0x1800abdfb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800abe00  mov     r12, rax
0x1800abe03  test    rax, rax
0x1800abe06  jnz     short loc_1800ABE64
0x1800abe08  mov     rax, cs:WPP_GLOBAL_Control
0x1800abe0f  lea     rsi, WPP_GLOBAL_Control
0x1800abe16  cmp     rax, rsi
0x1800abe19  jz      short loc_1800ABE5A
0x1800abe1b  test    byte ptr [rax+1Ch], 8
0x1800abe1f  jz      short loc_1800ABE5A
0x1800abe21  mov     dil, 2
0x1800abe24  cmp     [rax+19h], dil
0x1800abe28  jb      short loc_1800ABE5A
0x1800abe2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800abe2f  lea     rcx, aDevproperty; "DEVPROPERTY"
0x1800abe36  mov     r9d, eax
0x1800abe39  mov     [rsp+0D0h+var_B0], rcx
0x1800abe3e  lea     edx, [r12+3Ah]
0x1800abe43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abe4a  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800abe51  mov     rcx, [rcx+10h]
0x1800abe55  call    WPP_SF_Ds
0x1800abe5a  mov     ebx, 8007000Eh
0x1800abe5f  jmp     loc_1800AC1E3
0x1800abe64  mov     rdx, [rbp+37h+Src]; Src
0x1800abe68  test    rdx, rdx
0x1800abe6b  jz      short loc_1800ABE84
0x1800abe6d  lea     r8, [rsi+rsi*2]
0x1800abe71  mov     rcx, r12; void *
0x1800abe74  shl     r8, 4; Size
0x1800abe78  call    memcpy_0
0x1800abe7d  lea     rdi, [r15+2E0h]
0x1800abe84  xorps   xmm0, xmm0
0x1800abe87  lea     rcx, [rsi+rsi*2]
0x1800abe8b  add     rcx, rcx
0x1800abe8e  movups  xmmword ptr [r12+rcx*8], xmm0
0x1800abe93  movups  xmmword ptr [r12+rcx*8+10h], xmm0
0x1800abe99  movups  xmmword ptr [r12+rcx*8+20h], xmm0
0x1800abe9f  movups  xmm0, cs:?PKEY_TIBUS_MUID@@3U_tagpropertykey@@B; _tagpropertykey const PKEY_TIBUS_MUID
0x1800abea6  movups  xmmword ptr [r12+rcx*8], xmm0
0x1800abeab  mov     eax, cs:dword_180177598
0x1800abeb1  mov     [r12+rcx*8+28h], rbx
0x1800abeb6  mov     ebx, [rbp+37h+arg_8]
0x1800abeb9  mov     [r12+rcx*8+10h], eax
0x1800abebe  mov     dword ptr [r12+rcx*8+20h], 0Dh
0x1800abec7  mov     dword ptr [r12+rcx*8+24h], 10h
0x1800abed0  mov     rcx, [r15+290h]
0x1800abed7  cmp     dword ptr [rcx+50h], 0
0x1800abedb  jz      short loc_1800ABEE7
0x1800abedd  mov     rcx, [rcx+48h]
0x1800abee1  call    cs:__imp_PAL_System_CritSecEnter
0x1800abee7  mov     eax, [rdi]
0x1800abee9  mov     edx, 1
0x1800abeee  mov     [rbp+37h+arg_8], edx
0x1800abef1  lea     rsi, WPP_GLOBAL_Control
0x1800abef8  mov     dil, 2
0x1800abefb  cmp     r15, r13
0x1800abefe  jnz     loc_1800AC14A
0x1800abf04  test    eax, eax
0x1800abf06  jz      loc_1800ABFFA
0x1800abf0c  mov     rcx, [r15+2D8h]
0x1800abf13  lea     rdx, [r15+18h]
0x1800abf17  mov     r8, [rbp+37h+arg_18]
0x1800abf1b  xor     r9d, r9d
0x1800abf1e  mov     [rsp+0D0h+var_B0], rdx
0x1800abf23  mov     rdx, [rbp+37h+arg_10]
0x1800abf27  mov     rax, [rcx]
0x1800abf2a  mov     rax, [rax+30h]
0x1800abf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf33  mov     ebx, eax
0x1800abf35  test    eax, eax
0x1800abf37  jns     short loc_1800ABF85
0x1800abf39  mov     rax, cs:WPP_GLOBAL_Control
0x1800abf40  cmp     rax, rsi
0x1800abf43  jz      short loc_1800ABF85
0x1800abf45  test    byte ptr [rax+1Ch], 8
0x1800abf49  jz      short loc_1800ABF85
0x1800abf4b  cmp     [rax+19h], dil
0x1800abf4f  jb      short loc_1800ABF85
0x1800abf51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800abf56  lea     rcx, aAddbusenumerat; "AddBusEnumerator failed"
0x1800abf5d  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800abf61  mov     [rsp+0D0h+var_B0], rcx
0x1800abf66  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800abf6d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abf74  mov     edx, 3Bh ; ';'
0x1800abf79  mov     r9d, eax
0x1800abf7c  mov     rcx, [rcx+10h]
0x1800abf80  call    WPP_SF_DsD
0x1800abf85  mov     eax, cs:dword_1801B76C8
0x1800abf8b  cmp     eax, 4
0x1800abf8e  jbe     loc_1800AC08A
0x1800abf94  mov     eax, [rbp+37h+arg_48]
0x1800abf9a  lea     rdx, byte_1801A2B9B
0x1800abfa1  mov     [rbp+37h+var_68], eax
0x1800abfa4  mov     eax, [rbp+37h+arg_40]
0x1800abfaa  mov     [rbp+37h+var_64], eax
0x1800abfad  mov     rax, [rbp+37h+arg_10]
0x1800abfb1  mov     [rbp+37h+var_60], rax
0x1800abfb5  lea     rax, aTibusCreationA; "TiBus creation: AddBusEnumerator result"
0x1800abfbc  mov     [rbp+37h+var_58], rax
0x1800abfc0  lea     rax, [rbp+37h+var_6C]
0x1800abfc4  mov     qword ptr [rsp+0D0h+var_90], rax
0x1800abfc9  lea     rax, [rbp+37h+var_68]
0x1800abfcd  mov     qword ptr [rsp+0D0h+var_98], rax
0x1800abfd2  lea     rax, [rbp+37h+var_64]
0x1800abfd6  mov     [rsp+0D0h+var_A0], rax
0x1800abfdb  lea     rax, [rbp+37h+var_60]
0x1800abfdf  mov     [rsp+0D0h+var_A8], rax
0x1800abfe4  lea     rax, [rbp+37h+var_58]
0x1800abfe8  mov     [rsp+0D0h+var_B0], rax
0x1800abfed  mov     [rbp+37h+var_6C], ebx
0x1800abff0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800abff5  jmp     loc_1800AC08A
0x1800abffa  mov     r9, [rbp+37h+arg_20]; unsigned __int16 *
0x1800abffe  lea     rax, [r15+2F0h]
0x1800ac005  mov     [rsp+0D0h+var_80], rax; unsigned __int16 *
0x1800ac00a  lea     rcx, [r15+2E8h]; this
0x1800ac011  mov     rax, [rbp+37h+arg_28]
0x1800ac015  xor     r8d, r8d; unsigned __int16 *
0x1800ac018  mov     [rsp+0D0h+var_88], rcx; struct HSWDEVICE__ **
0x1800ac01d  mov     [rsp+0D0h+var_90], edx; int
0x1800ac021  mov     rdx, [rbp+37h+arg_10]; unsigned __int16 *
0x1800ac025  mov     [rsp+0D0h+var_98], ebx; unsigned int
0x1800ac029  mov     [rsp+0D0h+var_A0], r12; struct _DEVPROPERTY *
0x1800ac02e  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1800ac033  call    ?CreateSwDevice@CTiBus@@AEAAJPEBG0000PEAU_DEVPROPERTY@@KHPEAPEAUHSWDEVICE__@@PEAGK@Z; CTiBus::CreateSwDevice(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_DEVPROPERTY *,ulong,int,HSWDEVICE__ * *,ushort *,ulong)
0x1800ac038  mov     ebx, eax
0x1800ac03a  test    eax, eax
0x1800ac03c  jns     short loc_1800AC092
0x1800ac03e  mov     rax, cs:WPP_GLOBAL_Control
0x1800ac045  cmp     rax, rsi
0x1800ac048  jz      short loc_1800AC08A
0x1800ac04a  test    byte ptr [rax+1Ch], 8
0x1800ac04e  jz      short loc_1800AC08A
0x1800ac050  cmp     [rax+19h], dil
0x1800ac054  jb      short loc_1800AC08A
0x1800ac056  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ac05b  lea     rcx, aCreateswdevice; "CreateSwDevice bus failed"
0x1800ac062  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800ac066  mov     [rsp+0D0h+var_B0], rcx
0x1800ac06b  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800ac072  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac079  mov     edx, 3Ch ; '<'
0x1800ac07e  mov     r9d, eax
0x1800ac081  mov     rcx, [rcx+10h]
0x1800ac085  call    WPP_SF_DsD
0x1800ac08a  test    ebx, ebx
0x1800ac08c  js      loc_1800AC1BF
0x1800ac092  cmp     ebx, 1
0x1800ac095  jnz     loc_1800AC192
0x1800ac09b  cmp     r15, r13
0x1800ac09e  jz      loc_1800AC2D7
0x1800ac0a4  mov     rax, [rbp+37h+arg_50]
0x1800ac0ab  lea     r9, [rbp+37h+arg_0]; int *
0x1800ac0af  mov     r8d, [rbp+37h+arg_40]; unsigned int
0x1800ac0b6  mov     rdx, r13; struct CTiDevice *
0x1800ac0b9  mov     [rsp+0D0h+var_A8], rax; struct tagDEVICE_PROBLEM_DETAILS *
0x1800ac0be  lea     rax, [rbp+37h+var_70]
0x1800ac0c2  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x1800ac0c7  call    ?CheckDeviceValid@CTiBus@@AEAAJPEAVCTiDevice@@KPEAHPEAKPEAUtagDEVICE_PROBLEM_DETAILS@@@Z; CTiBus::CheckDeviceValid(CTiDevice *,ulong,int *,ulong *,tagDEVICE_PROBLEM_DETAILS *)
0x1800ac0cc  mov     ebx, eax
0x1800ac0ce  test    eax, eax
0x1800ac0d0  jns     loc_1800AC2D1
0x1800ac0d6  mov     rcx, [r15+290h]
0x1800ac0dd  cmp     dword ptr [rcx+50h], 0
0x1800ac0e1  jz      short loc_1800AC0ED
0x1800ac0e3  mov     rcx, [rcx+48h]
0x1800ac0e7  call    cs:__imp_PAL_System_CritSecLeave
0x1800ac0ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800ac0f4  cmp     rax, rsi
0x1800ac0f7  jz      loc_1800AC1D6
0x1800ac0fd  test    byte ptr [rax+1Ch], 8
0x1800ac101  jz      loc_1800AC1D6
0x1800ac107  cmp     [rax+19h], dil
0x1800ac10b  jb      loc_1800AC1D6
0x1800ac111  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ac116  mov     edx, 41h ; 'A'
0x1800ac11b  lea     rcx, aCheckDeviceVal; "Check Device Valid failed"
0x1800ac122  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800ac126  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x1800ac12d  mov     [rsp+0D0h+var_B0], rcx
0x1800ac132  mov     r9d, eax
0x1800ac135  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac13c  mov     rcx, [rcx+10h]
0x1800ac140  call    WPP_SF_DsD
0x1800ac145  jmp     loc_1800AC1D6
0x1800ac14a  test    eax, eax
0x1800ac14c  jz      loc_1800AC22A
0x1800ac152  mov     rcx, [r15+18h]
0x1800ac156  lea     rdx, [r13+18h]
0x1800ac15a  mov     r8, [rbp+37h+arg_18]
0x1800ac15e  xor     r9d, r9d
0x1800ac161  mov     [rsp+0D0h+var_A8], rdx
0x1800ac166  mov     rdx, [rbp+37h+arg_10]
0x1800ac16a  mov     rax, [rcx]
0x1800ac16d  mov     dword ptr [rsp+0D0h+var_B0], 0
0x1800ac175  mov     rax, [rax+58h]
0x1800ac179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac17e  cmp     [rbp+37h+arg_48], 0
0x1800ac185  mov     ebx, eax
0x1800ac187  jz      short loc_1800AC1F7
0x1800ac189  cmp     eax, 8000000Ah
0x1800ac18e  jnz     short loc_1800AC1F7
0x1800ac190  xor     ebx, ebx
0x1800ac192  mov     r8, [r15+290h]
0x1800ac199  lea     rdx, [r13+298h]
0x1800ac1a0  lea     rcx, [r8+38h]
0x1800ac1a4  mov     rax, [rcx+8]
  ... truncated ...
```
