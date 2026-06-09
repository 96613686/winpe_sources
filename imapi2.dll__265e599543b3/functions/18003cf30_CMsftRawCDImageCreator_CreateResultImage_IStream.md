# CMsftRawCDImageCreator::CreateResultImage(IStream * *)

- ea: `0x18003cf30`
- end: `0x18003d87d`
- name: `?CreateResultImage@CMsftRawCDImageCreator@@UEAAJPEAPEAUIStream@@@Z`
- size: `2381`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *this, struct IStream **, const struct _GUID *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000ea20`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180015564`
- `0x180016778`
- `0x18003c2b0`
- `0x18003ce6c`
- `0x18003cf30`
- `0x18003dd48`
- `0x18003f354`
- `0x18003fdb4`
- `0x180041000`
- `0x180047040`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d11d`
- `ole32!CoCreateInstance` at `0x18003d1e7`
- `ole32!CoCreateInstance` at `0x18003d351`
- `ole32!CoCreateInstance` at `0x18003d454`
- `ole32!CoCreateInstance` at `0x18003d505`
- `ole32!CoCreateInstance` at `0x18003d687`
- `ole32!CoCreateInstance` at `0x18003d11d`
- `ole32!CoCreateInstance` at `0x18003d1e7`
- `ole32!CoCreateInstance` at `0x18003d351`
- `ole32!CoCreateInstance` at `0x18003d454`
- `ole32!CoCreateInstance` at `0x18003d505`
- `ole32!CoCreateInstance` at `0x18003d687`
- `KERNEL32!LocalAlloc` at `0x18003d036`
- `KERNEL32!LocalAlloc` at `0x18003d036`
- `KERNEL32!LocalFree` at `0x18003d5ef`
- `KERNEL32!LocalFree` at `0x18003d5ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsftRawCDImageCreator::CreateResultImage(
        CMsftRawCDImageCreator *this,
        struct IStream **a2,
        const struct _GUID *a3)
{
  CMsftRawCDImageCreator *v3; // r15
  CMsftStreamSubcode *v4; // rbx
  signed int UpdatedInterestingPoints; // edi
  int v6; // edx
  unsigned int v7; // edx
  CInterestingPoint *v8; // rcx
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  int v13; // eax
  HRESULT Instance; // eax
  signed int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  LPVOID *v21; // r8
  int v22; // edi
  __int64 v23; // rbx
  void *v24; // rbx
  int v25; // r13d
  HRESULT v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // ebx
  LPVOID *v30; // rax
  unsigned int v31; // r15d
  LPVOID v32; // rcx
  __int64 v33; // r9
  HRESULT v34; // eax
  int v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  LPVOID v38; // rcx
  int v40; // [rsp+28h] [rbp-50h]
  LPVOID *hMem; // [rsp+40h] [rbp-38h]
  CMsftStreamSubcode *v42; // [rsp+48h] [rbp-30h] BYREF
  LPVOID v43; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v44; // [rsp+58h] [rbp-20h] BYREF
  struct CInterestingPoint *v45[2]; // [rsp+60h] [rbp-18h] BYREF
  CMsftRawCDImageCreator *v46; // [rsp+C0h] [rbp+48h] BYREF
  struct IStream **v47; // [rsp+C8h] [rbp+50h]
  unsigned int v48; // [rsp+D0h] [rbp+58h]
  LPVOID *ppv; // [rsp+D8h] [rbp+60h] BYREF

  v47 = a2;
  v46 = this;
  v3 = this;
  v44 = 0;
  v4 = 0;
  v42 = 0;
  v43 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 13, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    }
    UpdatedInterestingPoints = -2147467261;
    goto LABEL_139;
  }
  *a2 = 0;
  v6 = *((_DWORD *)this + 27);
  hMem = 0;
  v48 = 0;
  v45[0] = 0;
  LODWORD(ppv) = 0;
  UpdatedInterestingPoints = CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(
                               this,
                               v6,
                               v45,
                               (unsigned int *)&ppv);
  if ( UpdatedInterestingPoints < 0 )
    goto LABEL_50;
  v8 = (CInterestingPoint *)*((_QWORD *)v3 + 14);
  if ( v8 )
    CInterestingPoint::`vector deleting destructor'(v8, v7);
  *((struct CInterestingPoint **)v3 + 14) = v45[0];
  *((_DWORD *)v3 + 30) = (_DWORD)ppv;
  v9 = *((_DWORD *)v3 + 27);
  v10 = v9 + 2;
  if ( *((_WORD *)v3 + 42) )
    v10 = v9 + v9 + 1;
  v48 = v10 + 1;
  v11 = v10 + 1;
  hMem = (LPVOID *)LocalAlloc(0x40u, 8LL * (unsigned int)(v10 + 1));
  if ( hMem )
  {
    v13 = ATL::CComObject<CMsftStreamSubcode>::CreateInstance(&v42);
    UpdatedInterestingPoints = v13;
    if ( v13 >= 0 )
    {
      (*(void (__fastcall **)(CMsftStreamSubcode *))(*(_QWORD *)v42 + 8LL))(v42);
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_25;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 87),
        15,
        &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids,
        (unsigned int)v13);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_25:
    if ( (unsigned int)(*((_DWORD *)v3 + 19) - 2) <= 1 && !*((_QWORD *)v3 + 12) )
    {
      Instance = CoCreateInstance(
                   &CLSID_MsftStreamZero,
                   0,
                   0x17u,
                   &GUID_0000000c_0000_0000_c000_000000000046,
                   (LPVOID *)v3 + 12);
      UpdatedInterestingPoints = Instance;
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
        {
          v16 = 16;
LABEL_95:
          WPP_SF_d(v12[87], v16, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)Instance);
          goto LABEL_96;
        }
        goto LABEL_51;
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v3 + 12) + 48LL))(
              *((_QWORD *)v3 + 12),
              0xFFFFFFFFFFFFFFFLL);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      UpdatedInterestingPoints = v15;
    }
    if ( UpdatedInterestingPoints < 0 )
    {
LABEL_51:
      v20 = 0;
      if ( UpdatedInterestingPoints < 0 )
        goto LABEL_97;
      v21 = hMem;
      while ( v20 <= *((_DWORD *)v3 + 27) )
      {
        v22 = v20 + 1;
        LODWORD(ppv) = v20 + 1;
        if ( v20 > 1 && *((_WORD *)v3 + 42) )
          LODWORD(ppv) = 2 * v20;
        v23 = 432LL * v20;
        CTrackData::ValidateInitialized((CMsftRawCDImageCreator *)((char *)v3 + v23 + 128));
        v24 = *(void **)((char *)v3 + v23 + 128);
        if ( v24 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 8LL))(v24);
        v21 = hMem;
        hMem[(int)ppv] = v24;
        v20 = v22;
      }
      if ( *((_WORD *)v3 + 42) )
      {
        v25 = 2;
        while ( v25 <= *((_DWORD *)v3 + 27) )
        {
          ppv = &v21[2 * v25 - 1];
          v26 = CoCreateInstance(&CLSID_MsftStreamZero, 0, 0x17u, &GUID_0000000c_0000_0000_c000_000000000046, ppv);
          UpdatedInterestingPoints = v26;
          if ( v26 < 0 )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
            {
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 87),
                20,
                &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids,
                (unsigned int)(v25 - 1),
                v25,
                v26);
              goto LABEL_96;
            }
            goto LABEL_97;
          }
          v27 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppv + 48LL))(*ppv, 352800);
          v12 = (PVOID *)WPP_GLOBAL_Control;
          UpdatedInterestingPoints = v27;
          if ( v27 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
          {
            v40 = 352800;
            WPP_SF_ddiid(*((_QWORD *)WPP_GLOBAL_Control + 87), v28, a3, (unsigned int)(v25 - 1), v25);
            goto LABEL_96;
          }
          ++v25;
          if ( v27 < 0 )
            goto LABEL_97;
          v21 = hMem;
        }
      }
      ppv = &v21[v48 - 1];
      Instance = CoCreateInstance(&CLSID_MsftStreamZero, 0, 0x17u, &GUID_0000000c_0000_0000_c000_000000000046, ppv);
      UpdatedInterestingPoints = Instance;
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
        {
          goto LABEL_97;
        }
        v16 = 22;
        goto LABEL_95;
      }
      v17 = 15876000;
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppv + 48LL))(*ppv, 15876000);
      UpdatedInterestingPoints = v18;
      if ( v18 >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_MsftStreamConcatenate,
                     0,
                     0x17u,
                     &GUID_27354146_7f64_5b0f_8f00_5d77afbe261e,
                     &v44);
        UpdatedInterestingPoints = Instance;
        if ( Instance < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
          {
            goto LABEL_97;
          }
          v16 = 24;
          goto LABEL_95;
        }
        Instance = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, _QWORD))(*(_QWORD *)v44 + 120LL))(v44, hMem, v48);
        UpdatedInterestingPoints = Instance;
        if ( Instance < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
          {
            goto LABEL_97;
          }
          v16 = 25;
          goto LABEL_95;
        }
LABEL_96:
        v12 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_97;
      }
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_97;
      }
      v19 = 23;
LABEL_49:
      WPP_SF_iid(v12[87], v19, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, v17, v17, v18);
      goto LABEL_96;
    }
    Instance = CMsftStreamSubcode::Initialize(v42, v3);
    UpdatedInterestingPoints = Instance;
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_97;
      }
      v16 = 17;
      goto LABEL_95;
    }
    Instance = CoCreateInstance(&CLSID_MsftStreamZero, 0, 0x17u, &GUID_0000000c_0000_0000_c000_000000000046, hMem);
    UpdatedInterestingPoints = Instance;
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_97;
      }
      v16 = 18;
      goto LABEL_95;
    }
    v17 = 52920000;
    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*hMem + 48LL))(*hMem, 52920000);
    UpdatedInterestingPoints = v18;
    if ( v18 < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
      {
        v19 = 19;
        goto LABEL_49;
      }
      goto LABEL_51;
    }
LABEL_50:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 87), 14, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, v11, v11);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  UpdatedInterestingPoints = -2147024882;
LABEL_97:
  v29 = 0;
  if ( v48 )
  {
    v30 = hMem;
    v31 = v48;
    do
    {
      v32 = v30[v29];
      if ( v32 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
        v30 = hMem;
        hMem[v29] = 0;
      }
      ++v29;
    }
    while ( v29 < v31 );
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v3 = v46;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( UpdatedInterestingPoints < 0 )
  {
    v4 = v42;
    goto LABEL_139;
  }
  v33 = *((unsigned int *)v3 + 19);
  LODWORD(v46) = 2352;
  *(_OWORD *)v45 = 0;
  if ( (_DWORD)v33 == 1 )
  {
    HIDWORD(v46) = 16;
LABEL_115:
    v34 = CoCreateInstance(&CLSID_MsftStreamInterleave, 0, 0x17u, &GUID_27354147_7f64_5b0f_8f00_5d77afbe261e, &v43);
    UpdatedInterestingPoints = v34;
    if ( v34 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 87),
        27,
        &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids,
        (unsigned int)v34);
    }
    goto LABEL_120;
  }
  if ( (unsigned int)(v33 - 2) <= 1 )
  {
    HIDWORD(v46) = 96;
    goto LABEL_115;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 708) & 0x10) != 0 && *((_BYTE *)v12 + 705) >= 3u )
    WPP_SF_d(v12[87], 26, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, v33);
  UpdatedInterestingPoints = -2147467259;
LABEL_120:
  v45[0] = (struct CInterestingPoint *)v44;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 8LL))(v44);
  v4 = v42;
  if ( UpdatedInterestingPoints >= 0 )
  {
    v35 = (**(__int64 (__fastcall ***)(CMsftStreamSubcode *, GUID *, struct CInterestingPoint **))v42)(
            v42,
            &GUID_0000000c_0000_0000_c000_000000000046,
            &v45[1]);
    UpdatedInterestingPoints = v35;
    if ( v35 >= 0 )
    {
      v35 = (*(__int64 (__fastcall **)(LPVOID, struct CInterestingPoint **, CMsftRawCDImageCreator **, __int64))(*(_QWORD *)v43 + 112LL))(
              v43,
              v45,
              &v46,
              2);
      UpdatedInterestingPoints = v35;
      if ( v35 >= 0 )
        goto LABEL_132;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_132;
      }
      v37 = 29;
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 705) < 3u )
      {
        goto LABEL_132;
      }
      v37 = 28;
    }
    WPP_SF_d(v36[87], v37, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)v35);
  }
LABEL_132:
  if ( v45[1] )
  {
    (*(void (__fastcall **)(struct CInterestingPoint *))(*(_QWORD *)v45[1] + 16LL))(v45[1]);
    v45[1] = 0;
  }
  if ( v45[0] )
    (*(void (__fastcall **)(struct CInterestingPoint *))(*(_QWORD *)v45[0] + 16LL))(v45[0]);
  if ( UpdatedInterestingPoints >= 0 )
  {
    v38 = v43;
    *v47 = (struct IStream *)v43;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 8LL))(v38);
  }
LABEL_139:
  if ( v4 )
    (*(void (__fastcall **)(CMsftStreamSubcode *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( !*((_WORD *)v3 + 21664) )
  {
    Imapi2Utility::SQMLogRawImageSession(
      (Imapi2Utility *)(unsigned int)UpdatedInterestingPoints,
      *((_DWORD *)v3 + 19),
      *((_WORD *)v3 + 42) != 0,
      *((_WORD *)v3 + 21666) != 0,
      *((_WORD *)v3 + 21665) != 0,
      v40);
    *((_WORD *)v3 + 21664) = 1;
  }
  if ( (UpdatedInterestingPoints & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(UpdatedInterestingPoints, (int)&CLSID_MsftRawCDImageCreator, a3);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
  return (unsigned int)UpdatedInterestingPoints;
}

```

## disassembly

```asm
0x18003cf30  mov     [rsp-40h+arg_8], rdx
0x18003cf35  mov     [rsp-40h+arg_0], rcx
0x18003cf3a  push    rbp
0x18003cf3b  push    rbx
0x18003cf3c  push    rsi
0x18003cf3d  push    rdi
0x18003cf3e  push    r12
0x18003cf40  push    r13
0x18003cf42  push    r14
0x18003cf44  push    r15
0x18003cf46  mov     rbp, rsp
0x18003cf49  sub     rsp, 78h
0x18003cf4d  xor     r13d, r13d
0x18003cf50  mov     r15, rcx
0x18003cf53  mov     [rbp+var_20], r13
0x18003cf57  mov     ebx, r13d
0x18003cf5a  mov     [rbp+var_30], rbx
0x18003cf5e  mov     [rbp+var_28], r13
0x18003cf62  test    rdx, rdx
0x18003cf65  jnz     short loc_18003CFB2
0x18003cf67  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf6e  lea     r12, WPP_GLOBAL_Control
0x18003cf75  cmp     rcx, r12
0x18003cf78  jz      short loc_18003CFA8
0x18003cf7a  lea     esi, [rdx+10h]
0x18003cf7d  test    [rcx+2C4h], sil
0x18003cf84  jz      short loc_18003CFA8
0x18003cf86  mov     r14b, 3
0x18003cf89  cmp     [rcx+2C1h], r14b
0x18003cf90  jb      short loc_18003CFA8
0x18003cf92  mov     rcx, [rcx+2B8h]
0x18003cf99  lea     edx, [rsi-3]
0x18003cf9c  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003cfa3  call    WPP_SF_
0x18003cfa8  mov     edi, 80004003h
0x18003cfad  jmp     loc_18003D7DC
0x18003cfb2  mov     [rdx], r13
0x18003cfb5  lea     r9, [rbp+arg_18]; unsigned int *
0x18003cfb9  mov     edx, [rcx+6Ch]; int
0x18003cfbc  lea     r8, [rbp+var_18]; struct CInterestingPoint **
0x18003cfc0  mov     [rbp+hMem], r13
0x18003cfc4  mov     [rbp+arg_10], r13d
0x18003cfc8  mov     [rbp+var_18], r13
0x18003cfcc  mov     dword ptr [rbp+arg_18], r13d
0x18003cfd0  call    ?ValidateAndCreateUpdatedInterestingPoints@CMsftRawCDImageCreator@@AEBAJJPEAPEAVCInterestingPoint@@PEAK@Z; CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(long,CInterestingPoint * *,ulong *)
0x18003cfd5  lea     r12, WPP_GLOBAL_Control
0x18003cfdc  mov     edi, eax
0x18003cfde  lea     r13, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003cfe5  mov     esi, 10h
0x18003cfea  mov     r14b, 3
0x18003cfed  test    eax, eax
0x18003cfef  js      loc_18003D28A
0x18003cff5  mov     rcx, [r15+70h]; this
0x18003cff9  test    rcx, rcx
0x18003cffc  jz      short loc_18003D003
0x18003cffe  call    ??_ECInterestingPoint@@QEAAPEAXI@Z; CInterestingPoint::`vector deleting destructor'(uint)
0x18003d003  mov     rax, [rbp+var_18]
0x18003d007  mov     [r15+70h], rax
0x18003d00b  mov     eax, dword ptr [rbp+arg_18]
0x18003d00e  mov     [r15+78h], eax
0x18003d012  mov     eax, [r15+6Ch]
0x18003d016  lea     ecx, [rax+2]
0x18003d019  cmp     [r15+54h], bx
0x18003d01e  jz      short loc_18003D024
0x18003d020  dec     ecx
0x18003d022  add     ecx, eax
0x18003d024  inc     ecx
0x18003d026  mov     edx, ecx
0x18003d028  mov     [rbp+arg_10], ecx
0x18003d02b  mov     ebx, ecx
0x18003d02d  mov     ecx, 40h ; '@'; uFlags
0x18003d032  shl     rdx, 3; uBytes
0x18003d036  call    cs:__imp_LocalAlloc
0x18003d03c  mov     [rbp+hMem], rax
0x18003d040  test    rax, rax
0x18003d043  jnz     short loc_18003D091
0x18003d045  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d04c  cmp     rcx, r12
0x18003d04f  jz      short loc_18003D087
0x18003d051  test    [rcx+2C4h], sil
0x18003d058  jz      short loc_18003D087
0x18003d05a  cmp     [rcx+2C1h], r14b
0x18003d061  jb      short loc_18003D087
0x18003d063  mov     rcx, [rcx+2B8h]
0x18003d06a  lea     edx, [rax+0Eh]
0x18003d06d  mov     r9d, ebx
0x18003d070  mov     dword ptr [rsp+78h+ppv], ebx
0x18003d074  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003d07b  call    WPP_SF_Dd
0x18003d080  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d087  mov     edi, 8007000Eh
0x18003d08c  jmp     loc_18003D590
0x18003d091  lea     rcx, [rbp+var_30]
0x18003d095  call    ?CreateInstance@?$CComObject@VCMsftStreamSubcode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsftStreamSubcode>::CreateInstance(ATL::CComObject<CMsftStreamSubcode> * *)
0x18003d09a  mov     edi, eax
0x18003d09c  test    eax, eax
0x18003d09e  jns     short loc_18003D0D7
0x18003d0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0a7  cmp     rcx, r12
0x18003d0aa  jz      short loc_18003D0EE
0x18003d0ac  test    [rcx+2C4h], sil
0x18003d0b3  jz      short loc_18003D0EE
0x18003d0b5  cmp     [rcx+2C1h], r14b
0x18003d0bc  jb      short loc_18003D0EE
0x18003d0be  mov     rcx, [rcx+2B8h]
0x18003d0c5  mov     edx, 0Fh
0x18003d0ca  mov     r9d, eax
0x18003d0cd  mov     r8, r13
0x18003d0d0  call    WPP_SF_d
0x18003d0d5  jmp     short loc_18003D0E7
0x18003d0d7  mov     rcx, [rbp+var_30]
0x18003d0db  mov     rax, [rcx]
0x18003d0de  mov     rax, [rax+8]
0x18003d0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0ee  mov     eax, [r15+4Ch]
0x18003d0f2  sub     eax, 2
0x18003d0f5  cmp     eax, 1
0x18003d0f8  ja      short loc_18003D14B
0x18003d0fa  lea     rbx, [r15+60h]
0x18003d0fe  cmp     qword ptr [rbx], 0
0x18003d102  jnz     short loc_18003D14B
0x18003d104  xor     edx, edx; pUnkOuter
0x18003d106  mov     [rsp+78h+ppv], rbx; ppv
0x18003d10b  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003d112  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003d119  lea     r8d, [rdx+17h]; dwClsContext
0x18003d11d  call    cs:__imp_CoCreateInstance
0x18003d123  mov     edi, eax
0x18003d125  test    eax, eax
0x18003d127  js      short loc_18003D199
0x18003d129  mov     rcx, [rbx]
0x18003d12c  mov     rdx, 0FFFFFFFFFFFFFFFh
0x18003d136  mov     rax, [rcx]
0x18003d139  mov     rax, [rax+30h]
0x18003d13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d142  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d149  mov     edi, eax
0x18003d14b  test    edi, edi
0x18003d14d  js      loc_18003D291
0x18003d153  mov     rcx, [rbp+var_30]; this
0x18003d157  mov     rdx, r15; struct CMsftRawCDImageCreator *
0x18003d15a  call    ?Initialize@CMsftStreamSubcode@@QEAAJPEAVCMsftRawCDImageCreator@@@Z; CMsftStreamSubcode::Initialize(CMsftRawCDImageCreator *)
0x18003d15f  mov     edi, eax
0x18003d161  test    eax, eax
0x18003d163  jns     short loc_18003D1CA
0x18003d165  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d16c  cmp     rcx, r12
0x18003d16f  jz      loc_18003D590
0x18003d175  test    [rcx+2C4h], sil
0x18003d17c  jz      loc_18003D590
0x18003d182  cmp     [rcx+2C1h], r14b
0x18003d189  jb      loc_18003D590
0x18003d18f  mov     edx, 11h
0x18003d194  jmp     loc_18003D577
0x18003d199  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1a0  cmp     rcx, r12
0x18003d1a3  jz      loc_18003D291
0x18003d1a9  test    [rcx+2C4h], sil
0x18003d1b0  jz      loc_18003D291
0x18003d1b6  cmp     [rcx+2C1h], r14b
0x18003d1bd  jb      loc_18003D291
0x18003d1c3  mov     edx, esi
0x18003d1c5  jmp     loc_18003D577
0x18003d1ca  mov     rdx, [rbp+hMem]
0x18003d1ce  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003d1d5  mov     [rsp+78h+ppv], rdx; ppv
0x18003d1da  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003d1e1  xor     edx, edx; pUnkOuter
0x18003d1e3  lea     r8d, [rdx+17h]; dwClsContext
0x18003d1e7  call    cs:__imp_CoCreateInstance
0x18003d1ed  mov     edi, eax
0x18003d1ef  test    eax, eax
0x18003d1f1  jns     short loc_18003D227
0x18003d1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1fa  cmp     rcx, r12
0x18003d1fd  jz      loc_18003D590
0x18003d203  test    [rcx+2C4h], sil
0x18003d20a  jz      loc_18003D590
0x18003d210  cmp     [rcx+2C1h], r14b
0x18003d217  jb      loc_18003D590
0x18003d21d  mov     edx, 12h
0x18003d222  jmp     loc_18003D577
0x18003d227  mov     rax, [rbp+hMem]
0x18003d22b  mov     ebx, 3277EC0h
0x18003d230  mov     edx, ebx
0x18003d232  mov     rcx, [rax]
0x18003d235  mov     rax, [rcx]
0x18003d238  mov     rax, [rax+30h]
0x18003d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d241  mov     edi, eax
0x18003d243  test    eax, eax
0x18003d245  jns     short loc_18003D28A
0x18003d247  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d24e  cmp     rcx, r12
0x18003d251  jz      short loc_18003D291
0x18003d253  test    [rcx+2C4h], sil
0x18003d25a  jz      short loc_18003D291
0x18003d25c  cmp     [rcx+2C1h], r14b
0x18003d263  jb      short loc_18003D291
0x18003d265  mov     edx, 13h
0x18003d26a  mov     rcx, [rcx+2B8h]
0x18003d271  mov     r9, rbx
0x18003d274  mov     dword ptr [rsp+78h+var_50], eax
0x18003d278  mov     r8, r13
0x18003d27b  mov     [rsp+78h+ppv], rbx
0x18003d280  call    WPP_SF_iid
0x18003d285  jmp     loc_18003D589
0x18003d28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d291  xor     eax, eax
0x18003d293  test    edi, edi
0x18003d295  js      loc_18003D590
0x18003d29b  mov     r8, [rbp+hMem]
0x18003d29f  xor     esi, esi
0x18003d2a1  cmp     eax, [r15+6Ch]
0x18003d2a5  jg      short loc_18003D305
0x18003d2a7  lea     edi, [rax+1]
0x18003d2aa  mov     dword ptr [rbp+arg_18], edi
0x18003d2ad  cmp     eax, 1
0x18003d2b0  jle     short loc_18003D2C1
0x18003d2b2  cmp     [r15+54h], si
0x18003d2b7  jz      short loc_18003D2C1
0x18003d2b9  lea     ecx, [rax-1]
0x18003d2bc  add     ecx, edi
0x18003d2be  mov     dword ptr [rbp+arg_18], ecx
0x18003d2c1  cdqe
0x18003d2c3  lea     rcx, [r15+80h]
0x18003d2ca  imul    rbx, rax, 1B0h
0x18003d2d1  add     rcx, rbx; this
0x18003d2d4  call    ?ValidateInitialized@CTrackData@@AEBAXXZ; CTrackData::ValidateInitialized(void)
0x18003d2d9  mov     rbx, [rbx+r15+80h]
0x18003d2e1  test    rbx, rbx
0x18003d2e4  jz      short loc_18003D2F5
0x18003d2e6  mov     rax, [rbx]
0x18003d2e9  mov     rcx, rbx
0x18003d2ec  mov     rax, [rax+8]
0x18003d2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2f5  movsxd  rax, dword ptr [rbp+arg_18]
0x18003d2f9  mov     r8, [rbp+hMem]
0x18003d2fd  mov     [r8+rax*8], rbx
0x18003d301  mov     eax, edi
0x18003d303  jmp     short loc_18003D2A1
0x18003d305  xor     eax, eax
0x18003d307  lea     esi, [rax+10h]
0x18003d30a  cmp     [r15+54h], ax
0x18003d30f  jz      loc_18003D42E
0x18003d315  mov     ebx, 56220h
0x18003d31a  lea     r13d, [rax+2]
0x18003d31e  cmp     r13d, [r15+6Ch]
0x18003d322  jg      loc_18003D427
0x18003d328  xor     edx, edx; pUnkOuter
0x18003d32a  lea     eax, ds:0FFFFFFFFFFFFFFFFh[r13*2]
0x18003d332  lea     rax, [r8+rax*8]
0x18003d336  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003d33d  mov     [rbp+arg_18], rax
0x18003d341  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003d348  mov     [rsp+78h+ppv], rax; ppv
0x18003d34d  lea     r8d, [rdx+17h]; dwClsContext
0x18003d351  call    cs:__imp_CoCreateInstance
0x18003d357  mov     edi, eax
0x18003d359  test    eax, eax
0x18003d35b  js      short loc_18003D3D3
0x18003d35d  mov     rcx, [rbp+arg_18]
0x18003d361  mov     rdx, rbx
0x18003d364  mov     rcx, [rcx]
0x18003d367  mov     rax, [rcx]
0x18003d36a  mov     rax, [rax+30h]
0x18003d36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d373  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d37a  mov     edi, eax
0x18003d37c  test    eax, eax
0x18003d37e  jns     short loc_18003D397
0x18003d380  cmp     rcx, r12
0x18003d383  jz      short loc_18003D397
0x18003d385  test    [rcx+2C4h], sil
0x18003d38c  jz      short loc_18003D397
0x18003d38e  cmp     [rcx+2C1h], r14b
0x18003d395  jnb     short loc_18003D3AB
0x18003d397  inc     r13d
0x18003d39a  test    edi, edi
0x18003d39c  js      loc_18003D590
0x18003d3a2  mov     r8, [rbp+hMem]
0x18003d3a6  jmp     loc_18003D31E
0x18003d3ab  mov     rcx, [rcx+2B8h]
0x18003d3b2  lea     r9d, [r13-1]
0x18003d3b6  mov     [rsp+78h+var_40], edi
0x18003d3ba  mov     [rsp+78h+var_48], rbx
0x18003d3bf  mov     [rsp+78h+var_50], rbx
0x18003d3c4  mov     dword ptr [rsp+78h+ppv], r13d
0x18003d3c9  call    WPP_SF_ddiid
0x18003d3ce  jmp     loc_18003D589
0x18003d3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3da  cmp     rcx, r12
0x18003d3dd  jz      loc_18003D590
0x18003d3e3  test    [rcx+2C4h], sil
0x18003d3ea  jz      loc_18003D590
0x18003d3f0  cmp     [rcx+2C1h], r14b
0x18003d3f7  jb      loc_18003D590
0x18003d3fd  mov     rcx, [rcx+2B8h]
0x18003d404  lea     r9d, [r13-1]
  ... truncated ...
```
