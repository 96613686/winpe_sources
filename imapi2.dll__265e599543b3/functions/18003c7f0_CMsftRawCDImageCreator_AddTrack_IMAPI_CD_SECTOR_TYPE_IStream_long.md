# CMsftRawCDImageCreator::AddTrack(_IMAPI_CD_SECTOR_TYPE,IStream *,long *)

- ea: `0x18003c7f0`
- end: `0x18003cc1b`
- name: `?AddTrack@CMsftRawCDImageCreator@@UEAAJW4_IMAPI_CD_SECTOR_TYPE@@PEAUIStream@@PEAJ@Z`
- size: `1067`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *this, enum _IMAPI_CD_SECTOR_TYPE, struct IStream *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000ea20`
- `0x1800140f4`
- `0x180016778`
- `0x18003c2b0`
- `0x18003c7f0`
- `0x18003dd48`
- `0x180040bb0`
- `0x180040d54`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003c9c8`
- `ole32!CoCreateInstance` at `0x18003c9c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsftRawCDImageCreator::AddTrack(
        CMsftRawCDImageCreator *this,
        enum _IMAPI_CD_SECTOR_TYPE a2,
        struct IStream *a3,
        unsigned int *a4)
{
  char v4; // si
  unsigned int v5; // r12d
  HRESULT Instance; // ebx
  PVOID *v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // edx
  const struct _GUID *v18; // r8
  unsigned int v19; // edx
  CInterestingPoint *v21; // rcx
  CInterestingPoint *v22; // rax
  struct IStream *ppv; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v24; // [rsp+78h] [rbp+48h] BYREF
  CInterestingPoint *v25; // [rsp+80h] [rbp+50h] BYREF

  v4 = 0;
  v5 = *((_DWORD *)this + 27) + 1;
  v25 = 0;
  Instance = 0;
  v24 = 0;
  if ( !*((_WORD *)this + 36) )
    goto LABEL_6;
  Instance = -2136339968;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 30, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
LABEL_6:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 27) + *((_DWORD *)this + 26) > 99 )
  {
    Instance = -2136339967;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 708) & 0x10) != 0 && *((_BYTE *)v11 + 705) >= 3u )
    {
      WPP_SF_(v11[87], 31, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( a2 )
  {
    Instance = -2136339966;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 708) & 0x10) != 0 && *((_BYTE *)v11 + 705) >= 3u )
    {
      WPP_SF_(v11[87], 32, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !a3 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 708) & 0x10) != 0 && *((_BYTE *)v11 + 705) >= 3u )
    {
      WPP_SF_(v11[87], 33, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    Instance = -2147467261;
  }
  if ( !a4 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 708) & 0x10) != 0 && *((_BYTE *)v11 + 705) >= 3u )
      WPP_SF_(v11[87], 34, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    Instance = -2147467261;
    goto LABEL_61;
  }
  *a4 = 0;
  if ( Instance < 0 )
  {
LABEL_61:
    CTrackData::Clear((CMsftRawCDImageCreator *)((char *)this + 432 * v5 + 128));
    if ( v25 )
    {
      CInterestingPoint::`vector deleting destructor'(v25, v19);
      v24 = 0;
    }
    goto LABEL_63;
  }
  if ( *((_WORD *)this + 43) )
    goto LABEL_48;
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_MsftStreamZero,
               0,
               0x17u,
               &GUID_0000000c_0000_0000_c000_000000000046,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct IStream *, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 352800);
    if ( Instance >= 0 )
    {
      Instance = CTrackData::Init((struct IUnknown **)this + 16, IMAPI_CD_SECTOR_AUDIO, ppv);
      if ( Instance < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
        {
          v13 = 37;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
      {
        v13 = 36;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v13 = 35;
LABEL_46:
      WPP_SF_d(v12[87], v13, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)Instance);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  v4 = 1;
  if ( Instance < 0 )
  {
LABEL_60:
    CTrackData::Clear((CMsftRawCDImageCreator *)((char *)this + 128));
    goto LABEL_61;
  }
LABEL_48:
  v14 = 432LL * v5;
  CTrackData::Clear((CMsftRawCDImageCreator *)((char *)this + v14 + 128));
  Instance = CTrackData::Init((struct IUnknown **)((char *)this + v14 + 128), a2, a3);
  if ( Instance < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v16 = 38;
LABEL_58:
      WPP_SF_d(v15[87], v16, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)Instance);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  Instance = CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(
               this,
               *((_DWORD *)this + 27) + 1,
               &v25,
               &v24);
  if ( Instance < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v16 = 39;
      goto LABEL_58;
    }
LABEL_59:
    if ( !v4 )
      goto LABEL_61;
    goto LABEL_60;
  }
  v21 = (CInterestingPoint *)*((_QWORD *)this + 14);
  if ( v21 )
    CInterestingPoint::`vector deleting destructor'(v21, v17);
  v22 = v25;
  ++*((_DWORD *)this + 27);
  *((_QWORD *)this + 14) = v22;
  *((_DWORD *)this + 30) = v24;
  *((_WORD *)this + 43) = -1;
  *a4 = v5;
LABEL_63:
  if ( (Instance & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(Instance, (int)&CLSID_MsftRawCDImageCreator, v18);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003c7f0  mov     [rsp-38h+arg_18], rbx
0x18003c7f5  push    rbp
0x18003c7f6  push    rsi
0x18003c7f7  push    rdi
0x18003c7f8  push    r12
0x18003c7fa  push    r13
0x18003c7fc  push    r14
0x18003c7fe  push    r15
0x18003c800  mov     rbp, rsp
0x18003c803  sub     rsp, 30h
0x18003c807  mov     r12d, [rcx+6Ch]
0x18003c80b  xor     esi, esi
0x18003c80d  inc     r12d
0x18003c810  mov     [rbp+arg_10], rsi
0x18003c814  mov     r15d, edx
0x18003c817  mov     r14, r9
0x18003c81a  lea     rdx, WPP_GLOBAL_Control
0x18003c821  mov     r13, r8
0x18003c824  mov     rdi, rcx
0x18003c827  mov     ebx, esi
0x18003c829  mov     [rbp+arg_8], esi
0x18003c82c  cmp     [rcx+48h], si
0x18003c830  jz      short loc_18003C872
0x18003c832  mov     ebx, 80AA0A00h
0x18003c837  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c83e  cmp     rcx, rdx
0x18003c841  jz      short loc_18003C879
0x18003c843  test    byte ptr [rcx+2C4h], 10h
0x18003c84a  jz      short loc_18003C879
0x18003c84c  cmp     byte ptr [rcx+2C1h], 3
0x18003c853  jb      short loc_18003C879
0x18003c855  mov     rcx, [rcx+2B8h]
0x18003c85c  lea     edx, [rsi+1Eh]
0x18003c85f  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c866  call    WPP_SF_
0x18003c86b  lea     rdx, WPP_GLOBAL_Control
0x18003c872  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c879  mov     eax, [rdi+68h]
0x18003c87c  add     eax, [rdi+6Ch]
0x18003c87f  cmp     eax, 63h ; 'c'
0x18003c882  jle     short loc_18003C8BF
0x18003c884  mov     ebx, 80AA0A01h
0x18003c889  cmp     rcx, rdx
0x18003c88c  jz      short loc_18003C8BF
0x18003c88e  test    byte ptr [rcx+2C4h], 10h
0x18003c895  jz      short loc_18003C8BF
0x18003c897  cmp     byte ptr [rcx+2C1h], 3
0x18003c89e  jb      short loc_18003C8BF
0x18003c8a0  mov     rcx, [rcx+2B8h]
0x18003c8a7  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c8ae  mov     edx, 1Fh
0x18003c8b3  call    WPP_SF_
0x18003c8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8bf  test    r15d, r15d
0x18003c8c2  jz      short loc_18003C906
0x18003c8c4  mov     ebx, 80AA0A02h
0x18003c8c9  lea     rax, WPP_GLOBAL_Control
0x18003c8d0  cmp     rcx, rax
0x18003c8d3  jz      short loc_18003C90D
0x18003c8d5  test    byte ptr [rcx+2C4h], 10h
0x18003c8dc  jz      short loc_18003C90D
0x18003c8de  cmp     byte ptr [rcx+2C1h], 3
0x18003c8e5  jb      short loc_18003C90D
0x18003c8e7  mov     rcx, [rcx+2B8h]
0x18003c8ee  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c8f5  mov     edx, 20h ; ' '
0x18003c8fa  call    WPP_SF_
0x18003c8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c906  lea     rax, WPP_GLOBAL_Control
0x18003c90d  test    r13, r13
0x18003c910  jnz     short loc_18003C953
0x18003c912  cmp     rcx, rax
0x18003c915  jz      short loc_18003C94E
0x18003c917  test    byte ptr [rcx+2C4h], 10h
0x18003c91e  jz      short loc_18003C94E
0x18003c920  cmp     byte ptr [rcx+2C1h], 3
0x18003c927  jb      short loc_18003C94E
0x18003c929  mov     rcx, [rcx+2B8h]
0x18003c930  lea     edx, [r13+21h]
0x18003c934  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c93b  call    WPP_SF_
0x18003c940  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c947  lea     rax, WPP_GLOBAL_Control
0x18003c94e  mov     ebx, 80004003h
0x18003c953  test    r14, r14
0x18003c956  jnz     short loc_18003C990
0x18003c958  cmp     rcx, rax
0x18003c95b  jz      short loc_18003C986
0x18003c95d  test    byte ptr [rcx+2C4h], 10h
0x18003c964  jz      short loc_18003C986
0x18003c966  cmp     byte ptr [rcx+2C1h], 3
0x18003c96d  jb      short loc_18003C986
0x18003c96f  mov     rcx, [rcx+2B8h]
0x18003c976  lea     edx, [r14+22h]
0x18003c97a  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c981  call    WPP_SF_
0x18003c986  mov     ebx, 80004003h
0x18003c98b  jmp     loc_18003CB94
0x18003c990  mov     [r14], esi
0x18003c993  test    ebx, ebx
0x18003c995  js      loc_18003CB94
0x18003c99b  xor     eax, eax
0x18003c99d  cmp     [rdi+56h], ax
0x18003c9a1  jnz     loc_18003CAC2
0x18003c9a7  xor     edx, edx; pUnkOuter
0x18003c9a9  mov     [rbp+arg_0], rsi
0x18003c9ad  lea     rax, [rbp+arg_0]
0x18003c9b1  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003c9b8  mov     [rsp+30h+ppv], rax; ppv
0x18003c9bd  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003c9c4  lea     r8d, [rdx+17h]; dwClsContext
0x18003c9c8  call    cs:__imp_CoCreateInstance
0x18003c9ce  mov     ebx, eax
0x18003c9d0  test    eax, eax
0x18003c9d2  jns     short loc_18003CA0F
0x18003c9d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9db  lea     rax, WPP_GLOBAL_Control
0x18003c9e2  cmp     rcx, rax
0x18003c9e5  jz      loc_18003CAAE
0x18003c9eb  test    byte ptr [rcx+2C4h], 10h
0x18003c9f2  jz      loc_18003CAAE
0x18003c9f8  cmp     byte ptr [rcx+2C1h], 3
0x18003c9ff  jb      loc_18003CAAE
0x18003ca05  mov     edx, 23h ; '#'
0x18003ca0a  jmp     loc_18003CA98
0x18003ca0f  mov     rcx, [rbp+arg_0]
0x18003ca13  mov     edx, 56220h
0x18003ca18  mov     rax, [rcx]
0x18003ca1b  mov     rax, [rax+30h]
0x18003ca1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca24  mov     ebx, eax
0x18003ca26  test    eax, eax
0x18003ca28  jns     short loc_18003CA56
0x18003ca2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca31  lea     rax, WPP_GLOBAL_Control
0x18003ca38  cmp     rcx, rax
0x18003ca3b  jz      short loc_18003CAAE
0x18003ca3d  test    byte ptr [rcx+2C4h], 10h
0x18003ca44  jz      short loc_18003CAAE
0x18003ca46  cmp     byte ptr [rcx+2C1h], 3
0x18003ca4d  jb      short loc_18003CAAE
0x18003ca4f  mov     edx, 24h ; '$'
0x18003ca54  jmp     short loc_18003CA98
0x18003ca56  mov     r8, [rbp+arg_0]; struct IStream *
0x18003ca5a  lea     rcx, [rdi+80h]; this
0x18003ca61  xor     edx, edx; enum _IMAPI_CD_SECTOR_TYPE
0x18003ca63  call    ?Init@CTrackData@@QEAAJW4_IMAPI_CD_SECTOR_TYPE@@PEAUIStream@@@Z; CTrackData::Init(_IMAPI_CD_SECTOR_TYPE,IStream *)
0x18003ca68  mov     ebx, eax
0x18003ca6a  test    eax, eax
0x18003ca6c  jns     short loc_18003CAAE
0x18003ca6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca75  lea     rax, WPP_GLOBAL_Control
0x18003ca7c  cmp     rcx, rax
0x18003ca7f  jz      short loc_18003CAAE
0x18003ca81  test    byte ptr [rcx+2C4h], 10h
0x18003ca88  jz      short loc_18003CAAE
0x18003ca8a  cmp     byte ptr [rcx+2C1h], 3
0x18003ca91  jb      short loc_18003CAAE
0x18003ca93  mov     edx, 25h ; '%'
0x18003ca98  mov     rcx, [rcx+2B8h]
0x18003ca9f  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003caa6  mov     r9d, ebx
0x18003caa9  call    WPP_SF_d
0x18003caae  lea     rcx, [rbp+arg_0]
0x18003cab2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003cab7  mov     sil, 1
0x18003caba  test    ebx, ebx
0x18003cabc  js      loc_18003CB86
0x18003cac2  mov     eax, r12d
0x18003cac5  lea     rcx, [rdi+80h]
0x18003cacc  imul    rbx, rax, 1B0h
0x18003cad3  add     rcx, rbx; this
0x18003cad6  call    ?Clear@CTrackData@@QEAAXXZ; CTrackData::Clear(void)
0x18003cadb  lea     rcx, [rdi+80h]
0x18003cae2  mov     r8, r13; struct IStream *
0x18003cae5  add     rcx, rbx; this
0x18003cae8  mov     edx, r15d; enum _IMAPI_CD_SECTOR_TYPE
0x18003caeb  call    ?Init@CTrackData@@QEAAJW4_IMAPI_CD_SECTOR_TYPE@@PEAUIStream@@@Z; CTrackData::Init(_IMAPI_CD_SECTOR_TYPE,IStream *)
0x18003caf0  mov     ebx, eax
0x18003caf2  test    eax, eax
0x18003caf4  jns     short loc_18003CB22
0x18003caf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cafd  lea     rax, WPP_GLOBAL_Control
0x18003cb04  cmp     rcx, rax
0x18003cb07  jz      short loc_18003CB81
0x18003cb09  test    byte ptr [rcx+2C4h], 10h
0x18003cb10  jz      short loc_18003CB81
0x18003cb12  cmp     byte ptr [rcx+2C1h], 3
0x18003cb19  jb      short loc_18003CB81
0x18003cb1b  mov     edx, 26h ; '&'
0x18003cb20  jmp     short loc_18003CB6B
0x18003cb22  mov     edx, [rdi+6Ch]
0x18003cb25  lea     r9, [rbp+arg_8]; unsigned int *
0x18003cb29  inc     edx; int
0x18003cb2b  lea     r8, [rbp+arg_10]; struct CInterestingPoint **
0x18003cb2f  mov     rcx, rdi; this
0x18003cb32  call    ?ValidateAndCreateUpdatedInterestingPoints@CMsftRawCDImageCreator@@AEBAJJPEAPEAVCInterestingPoint@@PEAK@Z; CMsftRawCDImageCreator::ValidateAndCreateUpdatedInterestingPoints(long,CInterestingPoint * *,ulong *)
0x18003cb37  mov     ebx, eax
0x18003cb39  test    eax, eax
0x18003cb3b  jns     loc_18003CBF1
0x18003cb41  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb48  lea     rax, WPP_GLOBAL_Control
0x18003cb4f  cmp     rcx, rax
0x18003cb52  jz      short loc_18003CB81
0x18003cb54  test    byte ptr [rcx+2C4h], 10h
0x18003cb5b  jz      short loc_18003CB81
0x18003cb5d  cmp     byte ptr [rcx+2C1h], 3
0x18003cb64  jb      short loc_18003CB81
0x18003cb66  mov     edx, 27h ; '''
0x18003cb6b  mov     rcx, [rcx+2B8h]
0x18003cb72  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003cb79  mov     r9d, ebx
0x18003cb7c  call    WPP_SF_d
0x18003cb81  test    sil, sil
0x18003cb84  jz      short loc_18003CB92
0x18003cb86  lea     rcx, [rdi+80h]; this
0x18003cb8d  call    ?Clear@CTrackData@@QEAAXXZ; CTrackData::Clear(void)
0x18003cb92  xor     esi, esi
0x18003cb94  mov     eax, r12d
0x18003cb97  imul    rcx, rax, 1B0h
0x18003cb9e  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18003cba2  add     rcx, rdi; this
0x18003cba5  call    ?Clear@CTrackData@@QEAAXXZ; CTrackData::Clear(void)
0x18003cbaa  mov     rcx, [rbp+arg_10]; this
0x18003cbae  test    rcx, rcx
0x18003cbb1  jz      short loc_18003CBBB
0x18003cbb3  call    ??_ECInterestingPoint@@QEAAPEAXI@Z; CInterestingPoint::`vector deleting destructor'(uint)
0x18003cbb8  mov     [rbp+arg_8], esi
0x18003cbbb  mov     eax, ebx
0x18003cbbd  and     eax, 80FF0000h
0x18003cbc2  cmp     eax, 80AA0000h
0x18003cbc7  jnz     short loc_18003CBD7
0x18003cbc9  lea     rdx, CLSID_MsftRawCDImageCreator; int
0x18003cbd0  mov     ecx, ebx; dwMessageId
0x18003cbd2  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18003cbd7  mov     eax, ebx
0x18003cbd9  mov     rbx, [rsp+30h+arg_18]
0x18003cbe1  add     rsp, 30h
0x18003cbe5  pop     r15
0x18003cbe7  pop     r14
0x18003cbe9  pop     r13
0x18003cbeb  pop     r12
0x18003cbed  pop     rdi
0x18003cbee  pop     rsi
0x18003cbef  pop     rbp
0x18003cbf0  retn
0x18003cbf1  mov     rcx, [rdi+70h]; this
0x18003cbf5  test    rcx, rcx
0x18003cbf8  jz      short loc_18003CBFF
0x18003cbfa  call    ??_ECInterestingPoint@@QEAAPEAXI@Z; CInterestingPoint::`vector deleting destructor'(uint)
0x18003cbff  mov     rax, [rbp+arg_10]
0x18003cc03  inc     dword ptr [rdi+6Ch]
0x18003cc06  mov     [rdi+70h], rax
0x18003cc0a  mov     eax, [rbp+arg_8]
0x18003cc0d  mov     [rdi+78h], eax
0x18003cc10  mov     word ptr [rdi+56h], 0FFFFh
0x18003cc16  mov     [r14], r12d
0x18003cc19  jmp     short loc_18003CBBB
```
