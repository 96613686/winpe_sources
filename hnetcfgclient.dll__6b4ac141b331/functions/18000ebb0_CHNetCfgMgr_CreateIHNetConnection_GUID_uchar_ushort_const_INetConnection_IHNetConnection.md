# CHNetCfgMgr::CreateIHNetConnection(_GUID *,uchar,ushort const *,INetConnection *,IHNetConnection * *)

- ea: `0x18000ebb0`
- end: `0x18000f199`
- name: `?CreateIHNetConnection@CHNetCfgMgr@@UEAAJPEAU_GUID@@EPEBGPEAUINetConnection@@PEAPEAUIHNetConnection@@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, struct _GUID *, unsigned __int8, OLECHAR *, struct INetConnection *, struct IHNetConnection **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000ebb0`
- `0x18000ffc8`
- `0x18001de9c`
- `0x18001f4e4`
- `0x18002886c`
- `0x180028c48`
- `0x180029440`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000ee86`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ee86`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef05`
- `OLEAUT32!__imp_VariantClear` at `0x18000ef05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee94`

## string_xrefs

- `0x18000eeb4`: `PhonebookPath`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::CreateIHNetConnection(
        CHNetCfgMgr *this,
        struct _GUID *a2,
        unsigned __int8 a3,
        OLECHAR *a4,
        struct INetConnection *a5,
        struct IHNetConnection **a6)
{
  PVOID *v10; // rcx
  __int64 v11; // rdx
  struct INetConnection *v13; // r15
  PVOID *v14; // rcx
  int v15; // eax
  int PhonebookPathFromRasNetcon; // edi
  PVOID *v17; // rcx
  struct IWbemClassObject *v18; // r12
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  struct IWbemServices *v21; // rcx
  struct IWbemClassObject *v22; // rbx
  struct IWbemClassObject v23; // rax
  struct IWbemClassObject *v24; // rcx
  int v25; // eax
  int v26; // eax
  struct IWbemClassObject *v27; // r13
  OLECHAR *v28; // rsi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  struct IWbemClassObject *v31; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF
  OLECHAR *psz; // [rsp+A0h] [rbp+48h] BYREF

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  psz = 0;
  v31 = 0;
  if ( !*((_QWORD *)this + 12) )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return 2147500035LL;
    if ( (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_d(v10[2], 49, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 8) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 2147500035LL;
    v11 = 50;
LABEL_23:
    WPP_SF_d(v10[2], v11, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  if ( !a6 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return 2147500035LL;
    if ( (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_d(v10[2], (unsigned int)((_DWORD)a6 + 51), &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 8) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 2147500035LL;
    v11 = 52;
    goto LABEL_23;
  }
  v13 = a5;
  *a6 = 0;
  if ( v13 )
  {
    v15 = CreateConnectionAndPropertyInstances(
            *((struct IWbemServices **)this + 12),
            a2,
            a3,
            a4,
            (struct IWbemClassObject **)&psz,
            &v31);
    PhonebookPathFromRasNetcon = v15;
    if ( v15 < 0 )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)PhonebookPathFromRasNetcon;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v15);
LABEL_94:
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_95:
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 && *((_BYTE *)v17 + 25) >= 6u )
        WPP_SF_d(v17[2], 64, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)PhonebookPathFromRasNetcon);
      return (unsigned int)PhonebookPathFromRasNetcon;
    }
    if ( v15 )
      goto LABEL_94;
    v18 = (struct IWbemClassObject *)psz;
    if ( !a3 )
    {
      psz = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      PhonebookPathFromRasNetcon = GetPhonebookPathFromRasNetcon(v13, &psz);
      if ( PhonebookPathFromRasNetcon < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_48;
        }
        v20 = 56;
LABEL_47:
        WPP_SF_d(
          v19[2],
          v20,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)PhonebookPathFromRasNetcon);
LABEL_48:
        v21 = (struct IWbemServices *)*((_QWORD *)this + 12);
LABEL_49:
        DeleteWmiInstance(v21, v18);
        v22 = v31;
        DeleteWmiInstance(*((struct IWbemServices **)this + 12), v31);
        ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
        v23.lpVtbl = v22->lpVtbl;
        v24 = v22;
LABEL_93:
        ((void (__fastcall *)(struct IWbemClassObject *))v23.lpVtbl->Release)(v24);
        goto LABEL_94;
      }
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(psz);
      CoTaskMemFree(psz);
      if ( pvarg.llVal )
      {
        PhonebookPathFromRasNetcon = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))v18->lpVtbl->Put)(
                                       v18,
                                       L"PhonebookPath",
                                       0,
                                       &pvarg,
                                       0);
        if ( PhonebookPathFromRasNetcon < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
            (unsigned int)PhonebookPathFromRasNetcon);
        }
        VariantClear(&pvarg);
      }
      else
      {
        PhonebookPathFromRasNetcon = -2147024882;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = 58;
          goto LABEL_47;
        }
      }
      v21 = (struct IWbemServices *)*((_QWORD *)this + 12);
      if ( PhonebookPathFromRasNetcon < 0 )
        goto LABEL_49;
      v25 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, _QWORD, _QWORD, _QWORD))v21->lpVtbl->PutInstance)(
              v21,
              v18,
              0,
              0,
              0);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      PhonebookPathFromRasNetcon = v25;
      if ( v25 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v25);
        goto LABEL_94;
      }
      if ( v25 )
        goto LABEL_95;
    }
    psz = 0;
    v26 = ATL::CComObject<CHNetConn>::CreateInstance(&psz);
    v27 = v31;
    PhonebookPathFromRasNetcon = v26;
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v26);
      }
      goto LABEL_92;
    }
    v28 = psz;
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 8LL))(psz);
    PhonebookPathFromRasNetcon = CHNetConn::SetINetConnection((CHNetConn *)v28, v13);
    if ( PhonebookPathFromRasNetcon >= 0 )
    {
      if ( PhonebookPathFromRasNetcon )
      {
LABEL_91:
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_92:
        ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
        v23.lpVtbl = v27->lpVtbl;
        v24 = v27;
        goto LABEL_93;
      }
      PhonebookPathFromRasNetcon = CHNetConn::InitializeFromInstances(
                                     (CHNetConn *)v28,
                                     *((struct IWbemServices **)this + 12),
                                     v18,
                                     v27);
      if ( PhonebookPathFromRasNetcon >= 0 )
      {
        if ( PhonebookPathFromRasNetcon )
          goto LABEL_91;
        PhonebookPathFromRasNetcon = (**(__int64 (__fastcall ***)(OLECHAR *, GUID *, struct IHNetConnection **))v28)(
                                       v28,
                                       &GUID_85d18b71_3032_11d4_9348_00c04f8eeb71,
                                       a6);
        if ( PhonebookPathFromRasNetcon >= 0 )
          goto LABEL_91;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_91;
        }
        v30 = 63;
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_91;
        }
        v30 = 62;
      }
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      v30 = 61;
    }
    WPP_SF_d(v29[2], v30, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)PhonebookPathFromRasNetcon);
    goto LABEL_91;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 && *((_BYTE *)v14 + 25) >= 6u )
      WPP_SF_d(v14[2], 54, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942487LL);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000ebb0  push    rbp
0x18000ebb2  push    rbx
0x18000ebb3  push    rsi
0x18000ebb4  push    rdi
0x18000ebb5  push    r12
0x18000ebb7  push    r13
0x18000ebb9  push    r14
0x18000ebbb  push    r15
0x18000ebbd  mov     rbp, rsp
0x18000ebc0  sub     rsp, 58h
0x18000ebc4  mov     rbx, r9
0x18000ebc7  mov     sil, r8b
0x18000ebca  mov     rdi, rdx
0x18000ebcd  mov     r14, rcx
0x18000ebd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebd7  lea     r15, WPP_GLOBAL_Control
0x18000ebde  mov     r12d, 8
0x18000ebe4  cmp     rcx, r15
0x18000ebe7  jz      short loc_18000EC11
0x18000ebe9  test    [rcx+1Ch], r12b
0x18000ebed  jz      short loc_18000EC11
0x18000ebef  cmp     byte ptr [rcx+19h], 6
0x18000ebf3  jb      short loc_18000EC11
0x18000ebf5  mov     rcx, [rcx+10h]
0x18000ebf9  lea     edx, [r12+28h]
0x18000ebfe  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ec05  call    WPP_SF_
0x18000ec0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec11  xor     r13d, r13d
0x18000ec14  mov     [rbp+psz], r13
0x18000ec18  mov     [rbp+var_28], r13
0x18000ec1c  cmp     [r14+60h], r13
0x18000ec20  jnz     short loc_18000EC71
0x18000ec22  cmp     rcx, r15
0x18000ec25  jz      loc_18000ECD8
0x18000ec2b  test    [rcx+1Ch], r12b
0x18000ec2f  jz      short loc_18000EC59
0x18000ec31  mov     bl, 2
0x18000ec33  cmp     [rcx+19h], bl
0x18000ec36  jb      short loc_18000EC59
0x18000ec38  mov     rcx, [rcx+10h]
0x18000ec3c  lea     edx, [r13+31h]
0x18000ec40  mov     r9d, 80004003h
0x18000ec46  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ec4d  call    WPP_SF_d
0x18000ec52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec59  cmp     rcx, r15
0x18000ec5c  jz      short loc_18000ECD8
0x18000ec5e  test    [rcx+1Ch], r12b
0x18000ec62  jz      short loc_18000ECD8
0x18000ec64  cmp     byte ptr [rcx+19h], 6
0x18000ec68  jb      short loc_18000ECD8
0x18000ec6a  mov     edx, 32h ; '2'
0x18000ec6f  jmp     short loc_18000ECC2
0x18000ec71  mov     rax, [rbp+arg_28]
0x18000ec75  test    rax, rax
0x18000ec78  jnz     short loc_18000ECE2
0x18000ec7a  cmp     rcx, r15
0x18000ec7d  jz      short loc_18000ECD8
0x18000ec7f  test    [rcx+1Ch], r12b
0x18000ec83  jz      short loc_18000ECAC
0x18000ec85  mov     bl, 2
0x18000ec87  cmp     [rcx+19h], bl
0x18000ec8a  jb      short loc_18000ECAC
0x18000ec8c  mov     rcx, [rcx+10h]
0x18000ec90  lea     edx, [rax+33h]
0x18000ec93  mov     r9d, 80004003h
0x18000ec99  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000eca0  call    WPP_SF_d
0x18000eca5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecac  cmp     rcx, r15
0x18000ecaf  jz      short loc_18000ECD8
0x18000ecb1  test    [rcx+1Ch], r12b
0x18000ecb5  jz      short loc_18000ECD8
0x18000ecb7  cmp     byte ptr [rcx+19h], 6
0x18000ecbb  jb      short loc_18000ECD8
0x18000ecbd  mov     edx, 34h ; '4'
0x18000ecc2  mov     rcx, [rcx+10h]
0x18000ecc6  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000eccd  mov     r9d, 80004003h
0x18000ecd3  call    WPP_SF_d
0x18000ecd8  mov     eax, 80004003h
0x18000ecdd  jmp     loc_18000F188
0x18000ece2  mov     r15, [rbp+arg_20]
0x18000ece6  mov     [rax], r13
0x18000ece9  test    r15, r15
0x18000ecec  jnz     short loc_18000ED61
0x18000ecee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecf5  lea     rdi, WPP_GLOBAL_Control
0x18000ecfc  mov     esi, 80070057h
0x18000ed01  cmp     rcx, rdi
0x18000ed04  jz      short loc_18000ED5A
0x18000ed06  test    [rcx+1Ch], r12b
0x18000ed0a  jz      short loc_18000ED31
0x18000ed0c  mov     bl, 2
0x18000ed0e  cmp     [rcx+19h], bl
0x18000ed11  jb      short loc_18000ED31
0x18000ed13  mov     rcx, [rcx+10h]
0x18000ed17  lea     edx, [r15+35h]
0x18000ed1b  mov     r9d, esi
0x18000ed1e  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ed25  call    WPP_SF_d
0x18000ed2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed31  cmp     rcx, rdi
0x18000ed34  jz      short loc_18000ED5A
0x18000ed36  test    [rcx+1Ch], r12b
0x18000ed3a  jz      short loc_18000ED5A
0x18000ed3c  cmp     byte ptr [rcx+19h], 6
0x18000ed40  jb      short loc_18000ED5A
0x18000ed42  mov     rcx, [rcx+10h]
0x18000ed46  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ed4d  mov     edx, 36h ; '6'
0x18000ed52  mov     r9d, esi
0x18000ed55  call    WPP_SF_d
0x18000ed5a  mov     eax, esi
0x18000ed5c  jmp     loc_18000F188
0x18000ed61  mov     rcx, [r14+60h]; struct IWbemServices *
0x18000ed65  lea     rax, [rbp+var_28]
0x18000ed69  mov     [rsp+58h+var_30], rax; struct IWbemClassObject **
0x18000ed6e  mov     r9, rbx; psz
0x18000ed71  lea     rax, [rbp+psz]
0x18000ed75  mov     r8b, sil; unsigned __int8
0x18000ed78  mov     rdx, rdi; rclsid
0x18000ed7b  mov     [rsp+58h+var_38], rax; struct IWbemClassObject **
0x18000ed80  call    ?CreateConnectionAndPropertyInstances@@YAJPEAUIWbemServices@@PEAU_GUID@@EPEBGPEAPEAUIWbemClassObject@@3@Z; CreateConnectionAndPropertyInstances(IWbemServices *,_GUID *,uchar,ushort const *,IWbemClassObject * *,IWbemClassObject * *)
0x18000ed85  mov     edi, eax
0x18000ed87  test    eax, eax
0x18000ed89  jns     short loc_18000EDD4
0x18000ed8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed92  lea     rsi, WPP_GLOBAL_Control
0x18000ed99  cmp     rcx, rsi
0x18000ed9c  jz      loc_18000F186
0x18000eda2  test    [rcx+1Ch], r12b
0x18000eda6  jz      loc_18000F15D
0x18000edac  mov     bl, 2
0x18000edae  cmp     [rcx+19h], bl
0x18000edb1  jb      loc_18000F15D
0x18000edb7  mov     rcx, [rcx+10h]
0x18000edbb  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000edc2  mov     edx, 37h ; '7'
0x18000edc7  mov     r9d, eax
0x18000edca  call    WPP_SF_d
0x18000edcf  jmp     loc_18000F156
0x18000edd4  jnz     loc_18000F14F
0x18000edda  mov     r12, [rbp+psz]
0x18000edde  mov     bl, 2
0x18000ede0  test    sil, sil
0x18000ede3  jnz     loc_18000EFC1
0x18000ede9  xorps   xmm0, xmm0
0x18000edec  mov     [rbp+psz], r13
0x18000edf0  xor     eax, eax
0x18000edf2  lea     rdx, [rbp+psz]; unsigned __int16 **
0x18000edf6  mov     rcx, r15; struct INetConnection *
0x18000edf9  mov     qword ptr [rbp+pvarg+10h], rax
0x18000edfd  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ee01  call    ?GetPhonebookPathFromRasNetcon@@YAJPEAUINetConnection@@PEAPEAG@Z; GetPhonebookPathFromRasNetcon(INetConnection *,ushort * *)
0x18000ee06  mov     edi, eax
0x18000ee08  test    eax, eax
0x18000ee0a  jns     short loc_18000EE79
0x18000ee0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee13  lea     rax, WPP_GLOBAL_Control
0x18000ee1a  cmp     rcx, rax
0x18000ee1d  jz      short loc_18000EE42
0x18000ee1f  test    byte ptr [rcx+1Ch], 8
0x18000ee23  jz      short loc_18000EE42
0x18000ee25  cmp     [rcx+19h], bl
0x18000ee28  jb      short loc_18000EE42
0x18000ee2a  mov     edx, 38h ; '8'
0x18000ee2f  mov     rcx, [rcx+10h]
0x18000ee33  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ee3a  mov     r9d, edi
0x18000ee3d  call    WPP_SF_d
0x18000ee42  mov     rcx, [r14+60h]; struct IWbemServices *
0x18000ee46  mov     rdx, r12; struct IWbemClassObject *
0x18000ee49  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x18000ee4e  mov     rbx, [rbp+var_28]
0x18000ee52  mov     rcx, [r14+60h]; struct IWbemServices *
0x18000ee56  mov     rdx, rbx; struct IWbemClassObject *
0x18000ee59  call    ?DeleteWmiInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; DeleteWmiInstance(IWbemServices *,IWbemClassObject *)
0x18000ee5e  mov     rax, [r12]
0x18000ee62  mov     rcx, r12
0x18000ee65  mov     rax, [rax+10h]
0x18000ee69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee6e  mov     rax, [rbx]
0x18000ee71  mov     rcx, rbx
0x18000ee74  jmp     loc_18000F140
0x18000ee79  mov     rcx, [rbp+psz]; psz
0x18000ee7d  mov     esi, 8
0x18000ee82  mov     word ptr [rbp+pvarg], si
0x18000ee86  call    cs:__imp_SysAllocString
0x18000ee8c  mov     rcx, [rbp+psz]; pv
0x18000ee90  mov     qword ptr [rbp+pvarg+8], rax
0x18000ee94  call    cs:__imp_CoTaskMemFree
0x18000ee9a  cmp     qword ptr [rbp+pvarg+8], r13
0x18000ee9e  jz      loc_18000EF75
0x18000eea4  mov     rax, [r12]
0x18000eea8  lea     r9, [rbp+pvarg]
0x18000eeac  xor     r8d, r8d
0x18000eeaf  mov     dword ptr [rsp+58h+var_38], r13d
0x18000eeb4  lea     rdx, ?c_wszPhonebookPath@@3QBGB; "PhonebookPath"
0x18000eebb  mov     rcx, r12
0x18000eebe  mov     rax, [rax+28h]
0x18000eec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eec7  mov     edi, eax
0x18000eec9  test    eax, eax
0x18000eecb  jns     short loc_18000EF01
0x18000eecd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eed4  lea     rax, WPP_GLOBAL_Control
0x18000eedb  cmp     rcx, rax
0x18000eede  jz      short loc_18000EF01
0x18000eee0  test    [rcx+1Ch], sil
0x18000eee4  jz      short loc_18000EF01
0x18000eee6  cmp     [rcx+19h], bl
0x18000eee9  jb      short loc_18000EF01
0x18000eeeb  mov     rcx, [rcx+10h]
0x18000eeef  lea     edx, [rsi+31h]
0x18000eef2  mov     r9d, edi
0x18000eef5  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000eefc  call    WPP_SF_d
0x18000ef01  lea     rcx, [rbp+pvarg]; pvarg
0x18000ef05  call    cs:__imp_VariantClear
0x18000ef0b  mov     rcx, [r14+60h]
0x18000ef0f  test    edi, edi
0x18000ef11  js      loc_18000EE46
0x18000ef17  mov     rax, [rcx]
0x18000ef1a  xor     r9d, r9d
0x18000ef1d  xor     r8d, r8d
0x18000ef20  mov     [rsp+58h+var_38], r13
0x18000ef25  mov     rdx, r12
0x18000ef28  mov     rax, [rax+70h]
0x18000ef2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef38  mov     edi, eax
0x18000ef3a  test    eax, eax
0x18000ef3c  jns     short loc_18000EFAE
0x18000ef3e  lea     rax, WPP_GLOBAL_Control
0x18000ef45  cmp     rcx, rax
0x18000ef48  jz      short loc_18000EFAE
0x18000ef4a  test    [rcx+1Ch], sil
0x18000ef4e  jz      short loc_18000EFAE
0x18000ef50  cmp     [rcx+19h], bl
0x18000ef53  jb      short loc_18000EFAE
0x18000ef55  mov     rcx, [rcx+10h]
0x18000ef59  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000ef60  mov     edx, 3Bh ; ';'
0x18000ef65  mov     r9d, edi
0x18000ef68  call    WPP_SF_d
0x18000ef6d  mov     r12d, esi
0x18000ef70  jmp     loc_18000F14F
0x18000ef75  mov     edi, 8007000Eh
0x18000ef7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef81  lea     rax, WPP_GLOBAL_Control
0x18000ef88  cmp     rcx, rax
0x18000ef8b  jz      loc_18000EF0B
0x18000ef91  test    [rcx+1Ch], sil
0x18000ef95  jz      loc_18000EF0B
0x18000ef9b  cmp     [rcx+19h], bl
0x18000ef9e  jb      loc_18000EF0B
0x18000efa4  mov     edx, 3Ah ; ':'
0x18000efa9  jmp     loc_18000EE2F
0x18000efae  test    edi, edi
0x18000efb0  jz      short loc_18000EFC6
0x18000efb2  mov     r12d, esi
0x18000efb5  lea     rsi, WPP_GLOBAL_Control
0x18000efbc  jmp     loc_18000F15D
0x18000efc1  mov     esi, 8
0x18000efc6  lea     rcx, [rbp+psz]
0x18000efca  mov     [rbp+psz], r13
0x18000efce  call    ?CreateInstance@?$CComObject@VCHNetConn@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetConn>::CreateInstance(ATL::CComObject<CHNetConn> * *)
0x18000efd3  mov     r13, [rbp+var_28]
0x18000efd7  mov     edi, eax
0x18000efd9  test    eax, eax
0x18000efdb  jns     short loc_18000F024
0x18000efdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efe4  lea     rax, WPP_GLOBAL_Control
0x18000efeb  cmp     rcx, rax
0x18000efee  jz      loc_18000F129
0x18000eff4  test    [rcx+1Ch], sil
0x18000eff8  jz      loc_18000F129
0x18000effe  cmp     [rcx+19h], bl
0x18000f001  jb      loc_18000F129
0x18000f007  mov     rcx, [rcx+10h]
0x18000f00b  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000f012  mov     edx, 3Ch ; '<'
0x18000f017  mov     r9d, edi
0x18000f01a  call    WPP_SF_d
0x18000f01f  jmp     loc_18000F129
0x18000f024  mov     rsi, [rbp+psz]
0x18000f028  mov     rcx, rsi
0x18000f02b  mov     rax, [rsi]
0x18000f02e  mov     rax, [rax+8]
0x18000f032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f037  mov     rdx, r15; struct INetConnection *
0x18000f03a  mov     rcx, rsi; this
0x18000f03d  call    ?SetINetConnection@CHNetConn@@QEAAJPEAUINetConnection@@@Z; CHNetConn::SetINetConnection(INetConnection *)
0x18000f042  mov     edi, eax
0x18000f044  test    eax, eax
0x18000f046  jns     short loc_18000F07C
0x18000f048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f04f  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
