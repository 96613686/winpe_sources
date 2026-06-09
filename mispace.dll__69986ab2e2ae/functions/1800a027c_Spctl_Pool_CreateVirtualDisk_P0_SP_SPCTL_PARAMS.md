# Spctl_Pool_CreateVirtualDisk_P0(_SP_SPCTL_PARAMS *)

- ea: `0x1800a027c`
- end: `0x1800a137a`
- name: `?Spctl_Pool_CreateVirtualDisk_P0@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `4350`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops`

## callers

- `0x1800958b8`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x1800063a0`
- `0x1800063f0`
- `0x180006dd4`
- `0x18000722d`
- `0x18000c644`
- `0x18000cd3c`
- `0x18000cdb0`
- `0x180019f9c`
- `0x180026a6c`
- `0x18002aae0`
- `0x18002ab30`
- `0x18002aba4`
- `0x18002ac20`
- `0x18002d40c`
- `0x180037890`
- `0x180046650`
- `0x180047e78`
- `0x18004ba30`
- `0x180069b88`
- `0x18006b4b0`
- `0x1800810a0`
- `0x1800810ec`
- `0x180081424`
- `0x1800820bc`
- `0x1800a027c`
- `0x1800aef0c`
- `0x1801bb1cc`
- `0x1801c05f0`
- `0x1801c1468`
- `0x1801c1a74`
- `0x1801c3344`
- `0x1801c33b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a082a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a07ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a082a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a05d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a05d0`

## string_xrefs

- `0x1800a02b6`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a060f`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a0648`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a072f`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a0849`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a10f3`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a1151`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x1800a11f3`: `Spctl_Pool_CreateVirtualDisk_P0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spctl_Pool_CreateVirtualDisk_P0(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // edi
  HLOCAL v6; // r12
  struct _SP_SPACE_INFO *v7; // r13
  unsigned int v8; // eax
  _DWORD *v10; // r15
  __int64 v11; // rsi
  unsigned int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  int v26; // r8d
  unsigned int VirtualDiskErrors; // r9d
  int v28; // ecx
  __int16 *v29; // rdx
  __int64 v30; // r14
  __int64 v31; // rcx
  int v32; // r14d
  __int64 v33; // rbx
  _DWORD *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned int v39; // eax
  unsigned int v40; // eax
  int SpaceTemplate; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  unsigned int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  char v48; // bl
  char v49; // r11
  int v50; // eax
  int v51; // ecx
  int v52; // r8d
  __int16 *v53; // rdx
  int v54; // r8d
  int v55; // r9d
  _QWORD *v56; // r15
  __int64 i; // rbx
  void *v58; // rcx
  int v59; // ecx
  int v60; // eax
  __int64 v61; // r15
  __int64 v62; // r14
  __int64 v63; // r10
  int v64; // eax
  unsigned int v65; // edx
  unsigned int v66; // edx
  int v67; // eax
  int v68; // eax
  unsigned int v69; // ecx
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rbx
  unsigned int v72; // edx
  unsigned int v73; // r8d
  unsigned int v74; // ecx
  __int64 v75; // rax
  int v76; // eax
  char *v77; // rbx
  __int64 v78; // rdx
  int TierTemplate; // eax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // r8
  char v83; // r12
  char v84; // r14
  int v85; // eax
  int v86; // ecx
  int v87; // r8d
  int v88; // eax
  unsigned int v89; // edx
  int v90; // ecx
  int v91; // ecx
  __int64 v92; // rax
  int v93; // ecx
  __int64 v94; // rax
  int v95; // ecx
  int v96; // ecx
  int v97; // ecx
  int v98; // r8d
  const unsigned __int16 *v99; // rbx
  int v100; // ecx
  int v101; // r8d
  int *v102; // rdx
  unsigned int v103; // eax
  enum _MI_Result Instance; // eax
  __int64 v105; // rax
  int v106; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v107; // [rsp+44h] [rbp-BCh]
  __int64 v108; // [rsp+48h] [rbp-B8h]
  int v109; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v110; // [rsp+58h] [rbp-A8h] BYREF
  struct _SP_SPACE_INFO *v111; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v112[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CSpCluster *v113; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v114; // [rsp+80h] [rbp-80h] BYREF
  int v115; // [rsp+88h] [rbp-78h]
  void *Block; // [rsp+90h] [rbp-70h]
  HLOCAL v117; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v119; // [rsp+A8h] [rbp-58h] BYREF
  const char *v120; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v121; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v122; // [rsp+C8h] [rbp-38h]
  _BYTE v123[24]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v124; // [rsp+F8h] [rbp-8h]
  __int128 v125; // [rsp+108h] [rbp+8h]
  _BYTE v126[128]; // [rsp+130h] [rbp+30h] BYREF

  v120 = (const char *)a1;
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v106 = 2172;
    hMem = "Spctl_Pool_CreateVirtualDisk_P0";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_1803239C5,
      a3,
      a4,
      (__int64)&hMem,
      (__int64)&v106);
  }
  v5 = 0;
  v113 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v113);
  v113 = 0;
  CSpExtendedStatus::CSpExtendedStatus((CSpExtendedStatus *)v126);
  memset_0(v123, 0, 0x48u);
  v6 = 0;
  v110 = 0;
  v119 = 0;
  v7 = 0;
  v111 = 0;
  v121 = 0;
  v122 = 0;
  v114 = 0;
  LOBYTE(v115) = 0;
  v117 = 0;
  v8 = *((_DWORD *)a1 + 142);
  if ( v8 < 0x18 )
  {
    CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)v126);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v113);
    return 87;
  }
  if ( *((_DWORD *)a1 + 146) >= 0x220u )
  {
    v107 = 0;
    v10 = 0;
    hMem = 0;
    Block = 0;
    v11 = *((_QWORD *)a1 + 70);
    v108 = *((_QWORD *)a1 + 72);
    v12 = *(_DWORD *)(v11 + 12);
    if ( v8 < v12 )
      goto LABEL_10;
    if ( *(_DWORD *)(v11 + 16) != 2005 )
      goto LABEL_10;
    if ( *(_DWORD *)(v11 + 8) < 0x8Au )
      goto LABEL_10;
    if ( v12 < *(_DWORD *)(v11 + 8) )
      goto LABEL_10;
    v13 = *(unsigned int *)(v11 + 40);
    if ( (_DWORD)v13 )
    {
      if ( (unsigned int)v13 < *(_DWORD *)(v11 + 8)
        || (unsigned int)v13 > v12
        || (v13 & 1) != 0
        || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v13), v12 - (unsigned int)v13, v112) < 0 )
      {
        goto LABEL_10;
      }
    }
    if ( (v14 = *(unsigned int *)(v11 + 32), (_DWORD)v14)
      && ((unsigned int)v14 < *(_DWORD *)(v11 + 8)
       || (v15 = *(_DWORD *)(v11 + 12), (unsigned int)v14 > v15)
       || (v14 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v14), v15 - (unsigned int)v14, v112) < 0)
      || (v16 = *(unsigned int *)(v11 + 36), (_DWORD)v16)
      && ((unsigned int)v16 < *(_DWORD *)(v11 + 8)
       || (v17 = *(_DWORD *)(v11 + 12), (unsigned int)v16 > v17)
       || (v16 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v16), v17 - (unsigned int)v16, v112) < 0)
      || (v18 = *(unsigned int *)(v11 + 28), (_DWORD)v18)
      && ((unsigned int)v18 < *(_DWORD *)(v11 + 8)
       || (unsigned int)v18 > *(_DWORD *)(v11 + 12)
       || (v18 & 3) != 0
       || (v19 = v18 + 4, (int)v18 + 4 < (unsigned int)v18)
       || v19 > *(_DWORD *)(v11 + 12)
       || (v20 = 16LL * *(unsigned int *)(v18 + v11), v20 > 0xFFFFFFFF)
       || (unsigned int)v20 + v19 < v19
       || (unsigned int)v20 + v19 > *(_DWORD *)(v11 + 12)) )
    {
LABEL_10:
      v5 = 87;
LABEL_68:
      v30 = v108;
LABEL_69:
      _FillMethodResponse(v30, *((unsigned int *)v120 + 146), v107, v117, *((_QWORD *)v120 + 74));
      v56 = Block;
      if ( Block )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v11 + 44); i = (unsigned int)(i + 1) )
        {
          v58 = (void *)v56[i];
          if ( v58 )
          {
            LocalFree(v58);
            v56[i] = 0;
          }
        }
        operator delete(v56);
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v117 )
        LocalFree(v117);
      if ( v6 )
        LocalFree(v6);
      if ( v7 )
        LocalFree(v7);
      v59 = (int)v119;
      if ( v119 )
        LocalFree(v119);
      if ( (unsigned int)dword_18039EB68 > 5 )
      {
        LODWORD(v111) = 3077;
        v120 = "Spctl_Pool_CreateVirtualDisk_P0";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v59,
          (unsigned int)byte_180327AE9,
          v54,
          v55,
          (__int64)&v120,
          (__int64)&v111);
      }
      goto LABEL_87;
    }
    if ( !(unsigned int)SiGetPool((struct _GUID *)((char *)a1 + 4), 2, (struct _SU_POOL_OBJECT **)&v110) )
    {
      v25 = GleToSmpReturnCode(v22, v21, v23, v24);
      VirtualDiskErrors = v25;
      v107 = v25;
      v28 = dword_18039EB68;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_41;
      v106 = v25;
      v109 = 2380;
      v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
      v29 = (__int16 *)byte_180321A8D;
      goto LABEL_39;
    }
    v109 = 0;
    if ( *(_DWORD *)(v11 + 40) )
    {
      LODWORD(v6) = SmpToSpResiliencyType(v11 + *(unsigned int *)(v11 + 40), v21);
      v109 = (int)v6;
    }
    if ( *(_DWORD *)(v11 + 28) )
    {
      if ( *(_DWORD *)(v11 + 8) >= 0xC0u && *(_BYTE *)(v11 + 188) )
        v31 = *(unsigned __int16 *)(v11 + 190);
      else
        v31 = 1;
      v32 = SmpToSpFaultDomainType(v31);
      v33 = *(unsigned int *)(v11 + 28);
      v34 = LocalAlloc(0x40u, 16 * *(_DWORD *)(v33 + v11) + 8);
      v10 = v34;
      hMem = v34;
      if ( !v34 )
      {
        v39 = GleToSmpReturnCode(v36, v35, v37, v38);
        VirtualDiskErrors = v39;
        v107 = v39;
        v28 = dword_18039EB68;
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v106 = v39;
          v109 = 2403;
          v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
          v29 = &word_180320986;
LABEL_39:
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v28,
            (_DWORD)v29,
            v26,
            VirtualDiskErrors,
            (__int64)v112,
            (__int64)&v109,
            (__int64)&v106);
LABEL_40:
          VirtualDiskErrors = v107;
        }
LABEL_41:
        v6 = v110;
LABEL_42:
        v30 = v108;
        goto LABEL_43;
      }
      *v34 = v32;
      v40 = *(_DWORD *)(v33 + v11);
      v10[1] = v40;
      memcpy_0(v10 + 2, (const void *)(v33 + v11 + 4), 16LL * v40);
    }
    SpaceTemplate = SuGetSpaceTemplate(v110, v21, (unsigned int)v6, v10, &v111);
    v45 = 0;
    if ( !SpaceTemplate )
    {
      VirtualDiskErrors = GleToSmpReturnCode(v43, v42, v44, 0);
      v107 = VirtualDiskErrors;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v106 = VirtualDiskErrors;
        v109 = 2419;
        v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v46,
          (unsigned int)&word_18031F2A6,
          v47,
          VirtualDiskErrors,
          (__int64)v112,
          (__int64)&v109,
          (__int64)&v106);
        v7 = v111;
        goto LABEL_40;
      }
      v7 = v111;
      goto LABEL_41;
    }
    v48 = *(_BYTE *)(v11 + 82);
    v49 = *(_BYTE *)(v11 + 78);
    v7 = v111;
    if ( *(_DWORD *)(v11 + 32) )
    {
      v50 = StringCchCopyW(
              (unsigned __int16 *)v111 + 20,
              0x100u,
              (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 32)));
      v45 = 0;
      if ( v50 < 0 )
      {
        v107 = 5;
        if ( (unsigned int)dword_18039EB68 <= 2 )
        {
LABEL_67:
          v6 = v110;
          goto LABEL_68;
        }
        v109 = 2436;
        v53 = &word_1803204EE;
LABEL_66:
        v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        v106 = 5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v51,
          (_DWORD)v53,
          v52,
          0,
          (__int64)v112,
          (__int64)&v109,
          (__int64)&v106);
        goto LABEL_67;
      }
    }
    if ( *(_DWORD *)(v11 + 36) )
    {
      v60 = StringCchCopyW(
              (unsigned __int16 *)v7 + 276,
              0x400u,
              (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 36)));
      v45 = 0;
      if ( v60 < 0 )
      {
        v107 = 5;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_67;
        v109 = 2447;
        v53 = (__int16 *)qword_180327FC0;
        goto LABEL_66;
      }
    }
    v61 = 0;
    LODWORD(v62) = 0;
    if ( *(_BYTE *)(v11 + 56) )
      *((_QWORD *)v7 + 333) = *(_QWORD *)(v11 + 64);
    v63 = -1;
    if ( *(_BYTE *)(v11 + 72) && *(_BYTE *)(v11 + 73) )
      *((_QWORD *)v7 + 333) = -1;
    if ( *(_BYTE *)(v11 + 52) )
      *((_DWORD *)v7 + 674) = SmpToSpProvisioningType(*(unsigned __int16 *)(v11 + 54));
    if ( *(_DWORD *)(v11 + 8) >= 0xB0u && *(_BYTE *)(v11 + 160) != (_BYTE)v45 )
      *((_QWORD *)v7 + 338) = *(_QWORD *)(v11 + 168);
    if ( *(_DWORD *)(v11 + 8) >= 0xBCu && *(_BYTE *)(v11 + 184) != (_BYTE)v45 )
      *((_DWORD *)v7 + 678) = SmpToSpMediaType(*(unsigned __int16 *)(v11 + 186));
    if ( *(_BYTE *)(v11 + 112) != (_BYTE)v45 )
    {
      v64 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 114));
      *((_DWORD *)v7 + 681) = v64;
      if ( (_DWORD)v6 == 3 )
        *((_DWORD *)v7 + 679) = v64;
    }
    if ( *(_DWORD *)(v11 + 8) >= 0xB8u && *(_BYTE *)(v11 + 180) != (_BYTE)v45 )
      *((_DWORD *)v7 + 679) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 182));
    if ( v48 )
    {
      v65 = *(unsigned __int16 *)(v11 + 84);
      if ( !v49 )
      {
        SP_RESILIENCY_INFO::SetFaultTolerance((struct _SP_SPACE_INFO *)((char *)v7 + 2748), v65);
        goto LABEL_119;
      }
      *((_DWORD *)v7 + 688) = v65;
    }
    else if ( !v49 )
    {
      goto LABEL_119;
    }
    v66 = *(unsigned __int16 *)(v11 + 80);
    if ( v48 )
      *((_DWORD *)v7 + 689) = v66;
    else
      SP_RESILIENCY_INFO::SetNumberOfCopies((struct _SP_SPACE_INFO *)((char *)v7 + 2748), v66);
LABEL_119:
    if ( *(_DWORD *)(v11 + 8) >= 0xB4u && *(_BYTE *)(v11 + 176) != (_BYTE)v45 )
    {
      v67 = *(unsigned __int16 *)(v11 + 178);
      if ( (_WORD)v67 == 0xFFFF )
        v67 = -1;
      *((_DWORD *)v7 + 690) = v67;
    }
    if ( *(_BYTE *)(v11 + 86) != (_BYTE)v45 )
    {
      if ( *(_WORD *)(v11 + 88) == 0xFFFF )
        v68 = -1;
      else
        v68 = *(unsigned __int16 *)(v11 + 88);
      *((_DWORD *)v7 + 691) = v68;
    }
    if ( *(_BYTE *)(v11 + 90) != (_BYTE)v45 && *(_BYTE *)(v11 + 91) != (_BYTE)v45 )
      *((_DWORD *)v7 + 691) = -1;
    if ( *(_BYTE *)(v11 + 96) != (_BYTE)v45 )
      *((_DWORD *)v7 + 692) = *(_DWORD *)(v11 + 104);
    if ( *(_DWORD *)(v11 + 8) >= 0xCCu && *(_BYTE *)(v11 + 200) != (_BYTE)v45 )
      *((_DWORD *)v7 + 700) = *(unsigned __int16 *)(v11 + 202);
    if ( *(_BYTE *)(v11 + 120) != (_BYTE)v45 )
      *((_QWORD *)v7 + 347) = *(_QWORD *)(v11 + 128);
    if ( *(_BYTE *)(v11 + 136) != (_BYTE)v45 && *(_BYTE *)(v11 + 137) != (_BYTE)v45 )
      *((_QWORD *)v7 + 347) = v63;
    if ( *(_DWORD *)(v11 + 8) >= 0xE0u && *(_BYTE *)(v11 + 208) != (_BYTE)v45 )
      *((_QWORD *)v7 + 348) = *(_QWORD *)(v11 + 216);
    if ( *(_DWORD *)(v11 + 8) >= 0xA0u && *(_BYTE *)(v11 + 144) != (_BYTE)v45 )
      *((_QWORD *)v7 + 349) = *(_QWORD *)(v11 + 152);
    if ( *(_DWORD *)(v11 + 8) >= 0xE8u && *(_BYTE *)(v11 + 224) != (_BYTE)v45 && *(_DWORD *)(v11 + 228) != v45 )
      *((_WORD *)v7 + 1434) |= 0x20u;
    if ( *(_DWORD *)(v11 + 8) >= 0xC8u && *(_BYTE *)(v11 + 192) != (_BYTE)v45 && *(_DWORD *)(v11 + 196) != v45 )
      *((_QWORD *)v7 + 331) |= 1uLL;
    if ( *(_DWORD *)(v11 + 44) > v45 )
    {
      v62 = *(unsigned int *)(v11 + 48);
      if ( (unsigned int)v62 < *(_DWORD *)(v11 + 8)
        || (v69 = *(_DWORD *)(v11 + 12), (unsigned int)v62 > v69)
        || (v62 & 7) != 0
        || (v70 = 48LL * *(unsigned int *)(v11 + 44), v70 > 0xFFFFFFFF)
        || v69 - (unsigned int)v62 < (unsigned int)v70 )
      {
LABEL_162:
        v5 = 87;
        goto LABEL_67;
      }
      v61 = v11 + v62;
      v71 = 8LL * *(unsigned int *)(v11 + 44);
      if ( !is_mul_ok(*(unsigned int *)(v11 + 44), 8u) )
        v71 = v63;
      Block = operator new[](v71);
      memset_0(Block, 0, v71);
      v45 = 0;
    }
    v72 = v45;
    v106 = v45;
    v73 = *(_DWORD *)(v11 + 44);
    if ( v73 )
    {
      while ( 1 )
      {
        if ( (int)v62 + 48 < (unsigned int)v62 )
          goto LABEL_162;
        if ( (unsigned int)(v62 + 48) > *(_DWORD *)(v11 + 12) )
          goto LABEL_162;
        v74 = *(_DWORD *)(v61 + 12);
        LODWORD(v111) = v74 + v62;
        if ( v74 + (unsigned int)v62 < (unsigned int)v62
          || v74 + (unsigned int)v62 > *(_DWORD *)(v11 + 12)
          || *(_DWORD *)(v61 + 16) != 2006
          || *(_DWORD *)(v61 + 8) < 0x30u
          || v74 < *(_DWORD *)(v61 + 8) )
        {
          goto LABEL_162;
        }
        v75 = *(unsigned int *)(v61 + 44);
        if ( (_DWORD)v75 )
        {
          if ( (unsigned int)v75 < *(_DWORD *)(v61 + 8) )
            goto LABEL_162;
          if ( (unsigned int)v75 > v74 )
            goto LABEL_162;
          if ( (v75 & 1) != 0 )
            goto LABEL_162;
          v76 = StringCbLengthW((const unsigned __int16 *)(v61 + v75), v74 - (unsigned int)v75, v112);
          LOBYTE(v45) = 0;
          if ( v76 < 0 )
            goto LABEL_162;
          v72 = v106;
        }
        if ( *(_BYTE *)(v61 + 48) != (_BYTE)v45 )
        {
          LODWORD(v6) = *(unsigned __int16 *)(v61 + 50);
          v109 = (int)v6;
        }
        v77 = (char *)Block + 8 * v72;
        v78 = (unsigned int)v6;
        v6 = v110;
        TierTemplate = SuGetTierTemplate(v110, v78, 0, v77);
        v45 = 0;
        if ( !TierTemplate )
        {
          VirtualDiskErrors = GleToSmpReturnCode(v81, v80, v82, 0);
          v107 = VirtualDiskErrors;
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v111) = VirtualDiskErrors;
            v106 = 2735;
            v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v97,
              (unsigned int)byte_180324D99,
              v98,
              VirtualDiskErrors,
              (__int64)v112,
              (__int64)&v106,
              (__int64)&v111);
            VirtualDiskErrors = v107;
          }
          goto LABEL_42;
        }
        if ( *(_DWORD *)(v61 + 8) < 0x50u || (v83 = 1, !*(_BYTE *)(v61 + 76)) )
          v83 = 0;
        if ( *(_DWORD *)(v61 + 8) < 0x64u || (v84 = 1, !*(_BYTE *)(v61 + 96)) )
          v84 = 0;
        if ( *(_DWORD *)(v11 + 32) )
        {
          if ( *(_DWORD *)(v61 + 44) )
          {
            v85 = StringCchPrintfW(
                    (unsigned __int16 *)(*(_QWORD *)v77 + 56LL),
                    0x100u,
                    L"%s-%s",
                    v11 + *(unsigned int *)(v11 + 32),
                    v61 + *(unsigned int *)(v61 + 44));
            v45 = 0;
            if ( v85 < 0 )
            {
              v107 = 5;
              if ( (unsigned int)dword_18039EB68 > 2 )
              {
                LODWORD(v111) = 5;
                v106 = 2763;
                v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v86,
                  (unsigned int)byte_18032237B,
                  v87,
                  0,
                  (__int64)v112,
                  (__int64)&v106,
                  (__int64)&v111);
              }
              goto LABEL_67;
            }
          }
        }
        if ( *(_DWORD *)(v61 + 8) >= 0x68u && *(_BYTE *)(v61 + 100) )
          *(_DWORD *)(*(_QWORD *)v77 + 2616LL) = *(unsigned __int16 *)(v61 + 102);
        if ( *(_BYTE *)(v61 + 24) )
          *(_QWORD *)(*(_QWORD *)v77 + 2624LL) = *(_QWORD *)(v61 + 32);
        if ( *(_DWORD *)(v61 + 8) >= 0x58u && *(_BYTE *)(v61 + 84) )
          *(_DWORD *)(*(_QWORD *)v77 + 2648LL) = SmpToSpProvisioningType(*(unsigned __int16 *)(v61 + 86));
        if ( *(_DWORD *)(v61 + 8) >= 0x78u && *(_BYTE *)(v61 + 104) != (_BYTE)v45 )
          *(_QWORD *)(*(_QWORD *)v77 + 2656LL) = *(_QWORD *)(v61 + 112);
        if ( *(_DWORD *)(v61 + 8) >= 0x5Cu && *(_BYTE *)(v61 + 88) != (_BYTE)v45 )
        {
          v88 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v61 + 90));
          *(_DWORD *)(*(_QWORD *)v77 + 2676LL) = v88;
          if ( v109 == 3 )
            *(_DWORD *)(*(_QWORD *)v77 + 2668LL) = v88;
        }
        if ( *(_DWORD *)(v61 + 8) >= 0x60u && *(_BYTE *)(v61 + 92) != (_BYTE)v45 )
          *(_DWORD *)(*(_QWORD *)v77 + 2668LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v61 + 94));
        if ( v83 )
        {
          v89 = *(unsigned __int16 *)(v61 + 78);
          if ( !v84 )
          {
            SP_RESILIENCY_INFO::SetFaultTolerance((SP_RESILIENCY_INFO *)(*(_QWORD *)v77 + 2692LL), v89);
            goto LABEL_218;
          }
          *(_DWORD *)(*(_QWORD *)v77 + 2696LL) = v89;
        }
        else if ( !v84 )
        {
          goto LABEL_218;
        }
        v80 = *(unsigned __int16 *)(v61 + 98);
        if ( v83 )
          *(_DWORD *)(*(_QWORD *)v77 + 2700LL) = v80;
        else
          SP_RESILIENCY_INFO::SetNumberOfCopies((SP_RESILIENCY_INFO *)(*(_QWORD *)v77 + 2692LL), v80);
LABEL_218:
        if ( *(_DWORD *)(v61 + 8) >= 0x54u && *(_BYTE *)(v61 + 80) != (_BYTE)v45 )
        {
          if ( *(_WORD *)(v61 + 82) == 0xFFFF )
            v90 = -1;
          else
            v90 = *(unsigned __int16 *)(v61 + 82);
          *(_DWORD *)(*(_QWORD *)v77 + 2704LL) = v90;
        }
        if ( *(_DWORD *)(v61 + 8) >= 0x4Cu && *(_BYTE *)(v61 + 72) != (_BYTE)v45 )
        {
          if ( *(_WORD *)(v61 + 74) == 0xFFFF )
            v91 = -1;
          else
            v91 = *(unsigned __int16 *)(v61 + 74);
          *(_DWORD *)(*(_QWORD *)v77 + 2708LL) = v91;
        }
        if ( *(_DWORD *)(v61 + 8) >= 0x48u && *(_BYTE *)(v61 + 56) != (_BYTE)v45 )
          *(_DWORD *)(*(_QWORD *)v77 + 2712LL) = *(_DWORD *)(v61 + 64);
        if ( *(_BYTE *)(v61 + 40) != (_BYTE)v45 )
          *(_DWORD *)(*(_QWORD *)v77 + 2664LL) = SmpToSpMediaType(*(unsigned __int16 *)(v61 + 42));
        v6 = v110;
        if ( *((_DWORD *)v110 + 661) > 0xEu )
        {
          if ( *(_BYTE *)(v11 + 52) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2648LL) = SmpToSpProvisioningType(*(unsigned __int16 *)(v11 + 54));
          if ( *(_DWORD *)(v11 + 8) >= 0xBCu && *(_BYTE *)(v11 + 184) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2664LL) = SmpToSpMediaType(*(unsigned __int16 *)(v11 + 186));
          if ( *(_DWORD *)(v11 + 8) >= 0xB0u && *(_BYTE *)(v11 + 160) != (_BYTE)v45 )
            *(_QWORD *)(*(_QWORD *)v77 + 2656LL) = *(_QWORD *)(v11 + 168);
          if ( *(_DWORD *)(v11 + 8) >= 0xB8u && *(_BYTE *)(v11 + 180) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2668LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 182));
          if ( *(_BYTE *)(v11 + 112) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2676LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 114));
          if ( *(_DWORD *)(v11 + 40) != v45 )
          {
            *(_DWORD *)(*(_QWORD *)v77 + 2692LL) = SmpToSpResiliencyType(v11 + *(unsigned int *)(v11 + 40), v80);
            LOBYTE(v45) = 0;
          }
          if ( *(_BYTE *)(v11 + 82) != (_BYTE)v45 )
          {
            if ( *(_BYTE *)(v11 + 78) == (_BYTE)v45 )
              SP_RESILIENCY_INFO::SetFaultTolerance(
                (SP_RESILIENCY_INFO *)(*(_QWORD *)v77 + 2692LL),
                *(unsigned __int16 *)(v11 + 84));
            else
              *(_DWORD *)(*(_QWORD *)v77 + 2696LL) = *(unsigned __int16 *)(v11 + 84);
          }
          if ( *(_BYTE *)(v11 + 78) != (_BYTE)v45 )
          {
            if ( *(_BYTE *)(v11 + 82) == (_BYTE)v45 )
              SP_RESILIENCY_INFO::SetNumberOfCopies(
                (SP_RESILIENCY_INFO *)(*(_QWORD *)v77 + 2692LL),
                *(unsigned __int16 *)(v11 + 80));
            else
              *(_DWORD *)(*(_QWORD *)v77 + 2700LL) = *(unsigned __int16 *)(v11 + 80);
          }
          if ( *(_DWORD *)(v11 + 8) >= 0xB4u && *(_BYTE *)(v11 + 176) != (_BYTE)v45 )
          {
            if ( *(_WORD *)(v11 + 178) == 0xFFFF )
              v95 = -1;
            else
              v95 = *(unsigned __int16 *)(v11 + 178);
            *(_DWORD *)(*(_QWORD *)v77 + 2704LL) = v95;
          }
          if ( *(_BYTE *)(v11 + 86) != (_BYTE)v45 )
          {
            if ( *(_WORD *)(v11 + 88) == 0xFFFF )
              v96 = -1;
            else
              v96 = *(unsigned __int16 *)(v11 + 88);
            *(_DWORD *)(*(_QWORD *)v77 + 2708LL) = v96;
          }
          if ( *(_BYTE *)(v11 + 90) != (_BYTE)v45 && *(_BYTE *)(v11 + 91) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2708LL) = -1;
          if ( *(_BYTE *)(v11 + 96) != (_BYTE)v45 )
            *(_DWORD *)(*(_QWORD *)v77 + 2712LL) = *(_DWORD *)(v11 + 104);
        }
        else
        {
          v92 = *(_QWORD *)v77;
          v93 = *(_DWORD *)(*(_QWORD *)v77 + 2664LL);
          *(_OWORD *)(v92 + 2648) = *(_OWORD *)((char *)v7 + 2696);
          *(_OWORD *)(v92 + 2664) = *(_OWORD *)((char *)v7 + 2712);
          *(_DWORD *)(*(_QWORD *)v77 + 2664LL) = v93;
          v94 = *(_QWORD *)v77;
          *(_OWORD *)(v94 + 2692) = *(_OWORD *)((char *)v7 + 2748);
          *(_QWORD *)(v94 + 2708) = *(_QWORD *)((char *)v7 + 2764);
        }
        v72 = v106 + 1;
        v106 = v72;
        v73 = *(_DWORD *)(v11 + 44);
        if ( v72 >= v73 )
          goto LABEL_283;
        v61 += *(unsigned int *)(v61 + 12);
        LODWORD(v62) = (_DWORD)v111;
        LODWORD(v6) = v109;
      }
    }
    v6 = v110;
LABEL_283:
    v30 = v108;
    v99 = (const unsigned __int16 *)(v108 + 4);
    if ( !(unsigned int)SuexCreateSpace(
                          (struct _SU_POOL_OBJECT *)v6,
                          v7,
                          v73,
                          (struct _SP_TIER_INFO **const)Block,
                          (unsigned __int16 *const)(v108 + 4),
                          (struct _SU_SPACE_OBJECT **)&v119,
                          (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v117) )
    {
      VirtualDiskErrors = _TranslateCreateVirtualDiskErrors();
      v107 = VirtualDiskErrors;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v106 = 2998;
        v102 = &dword_180322AD4;
LABEL_286:
        v112[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        LODWORD(v111) = VirtualDiskErrors;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v100,
          (_DWORD)v102,
          v101,
          VirtualDiskErrors,
          (__int64)v112,
          (__int64)&v106,
          (__int64)&v111);
        VirtualDiskErrors = v107;
        goto LABEL_43;
      }
      goto LABEL_43;
    }
    if ( !*(_BYTE *)(v11 + 24) )
      goto LABEL_69;
    SuexParseIdLite(v99, (struct _SUEX_ID *)v123);
    v121 = v125;
    v122 = v124;
    v103 = InitializeDiskForSpace(&v121, 0);
    VirtualDiskErrors = v103;
    v107 = v103;
    if ( v103 == 8 )
    {
      if ( (unsigned int)CSpExtendedStatus::Initialize((CSpExtendedStatus *)v126, 0x8024u, 0, 8) )
        CSpExtendedStatus::ToSuexExtendedStatus((CSpExtendedStatus *)v126, (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v117);
      VirtualDiskErrors = v107;
    }
    else if ( !v103 )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v113);
      Instance = CSpCluster::GetInstance(&v113);
      if ( Instance )
      {
        LODWORD(v114) = Instance | 0x85200000;
        VirtualDiskErrors = _status_t::ToSMRC(&v114);
        v107 = VirtualDiskErrors;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_43;
        v106 = 3032;
        v102 = (int *)byte_180328175;
        goto LABEL_286;
      }
      v105 = CSpCluster::AddSpaceToCluster(v113, v112, &v121, v7, 0);
      v114 = *(_QWORD *)v105;
      v115 = *(_DWORD *)(v105 + 8);
      if ( _mm_cvtsi128_si32((__m128i)v114) >= 0 )
        goto LABEL_69;
      VirtualDiskErrors = _status_t::ToSMRC(&v114);
      v107 = VirtualDiskErrors;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v106 = 3042;
        v102 = &dword_180324874;
        goto LABEL_286;
      }
LABEL_43:
      if ( VirtualDiskErrors && VirtualDiskErrors != 46011 && v119 )
        SuDeleteSpace((struct _SU_SPACE_OBJECT *)v119);
      goto LABEL_69;
    }
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_43;
    v106 = 3024;
    v102 = (int *)&byte_180322CFF;
    goto LABEL_286;
  }
  **((_DWORD **)a1 + 74) = 544;
  v5 = 87;
LABEL_87:
  CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)v126);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v113);
  return v5;
}

```

## disassembly

```asm
0x1800a027c  push    rbp
0x1800a027e  push    rbx
0x1800a027f  push    rsi
0x1800a0280  push    rdi
0x1800a0281  push    r12
0x1800a0283  push    r13
0x1800a0285  push    r14
0x1800a0287  push    r15
0x1800a0289  lea     rbp, [rsp-0C8h]
0x1800a0291  sub     rsp, 1C8h
0x1800a0298  mov     rax, cs:__security_cookie
0x1800a029f  xor     rax, rsp
0x1800a02a2  mov     [rbp+100h+var_50], rax
0x1800a02a9  mov     r14, rcx
0x1800a02ac  mov     [rbp+100h+var_150], rcx
0x1800a02b0  mov     eax, cs:dword_18039EB68
0x1800a02b6  lea     rbx, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x1800a02bd  cmp     eax, 5
0x1800a02c0  jbe     short loc_1800A02ED
0x1800a02c2  mov     [rsp+200h+var_1C0], 87Ch
0x1800a02ca  mov     [rbp+100h+hMem], rbx
0x1800a02ce  lea     rax, [rsp+200h+var_1C0]
0x1800a02d3  mov     [rsp+200h+var_1D8], rax
0x1800a02d8  lea     rax, [rbp+100h+hMem]
0x1800a02dc  mov     [rsp+200h+var_1E0], rax
0x1800a02e1  lea     rdx, byte_1803239C5
0x1800a02e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a02ed  xor     edi, edi
0x1800a02ef  mov     [rsp+200h+var_188], rdi
0x1800a02f4  lea     rcx, [rsp+200h+var_188]
0x1800a02f9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a02fe  mov     [rsp+200h+var_188], rdi
0x1800a0303  lea     rcx, [rbp+100h+var_D0]; this
0x1800a0307  call    ??0CSpExtendedStatus@@QEAA@XZ; CSpExtendedStatus::CSpExtendedStatus(void)
0x1800a030c  nop
0x1800a030d  xor     edx, edx; Val
0x1800a030f  lea     r8d, [rdi+48h]; Size
0x1800a0313  lea     rcx, [rbp+100h+var_120]; void *
0x1800a0317  call    memset_0
0x1800a031c  mov     r12d, edi
0x1800a031f  mov     [rsp+200h+var_1A8], rdi
0x1800a0324  mov     [rbp+100h+var_158], rdi
0x1800a0328  mov     r13d, edi
0x1800a032b  mov     [rsp+200h+var_1A0], rdi
0x1800a0330  xorps   xmm0, xmm0
0x1800a0333  movups  [rbp+100h+var_148], xmm0
0x1800a0337  movups  [rbp+100h+var_138], xmm0
0x1800a033b  mov     [rbp+100h+var_180], rdi
0x1800a033f  mov     byte ptr [rbp+100h+var_178], dil
0x1800a0343  mov     [rbp+100h+var_168], rdi
0x1800a0347  mov     eax, [r14+238h]
0x1800a034e  cmp     eax, 18h
0x1800a0351  jnb     short loc_1800A036F
0x1800a0353  lea     rcx, [rbp+100h+var_D0]; this
0x1800a0357  call    ??1CSpExtendedStatus@@QEAA@XZ; CSpExtendedStatus::~CSpExtendedStatus(void)
0x1800a035c  nop
0x1800a035d  lea     rcx, [rsp+200h+var_188]
0x1800a0362  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a0367  lea     eax, [rdi+57h]
0x1800a036a  jmp     loc_1800A088A
0x1800a036f  mov     ecx, 220h
0x1800a0374  cmp     [r14+248h], ecx
0x1800a037b  jnb     short loc_1800A0390
0x1800a037d  mov     rax, [r14+250h]
0x1800a0384  mov     [rax], ecx
0x1800a0386  mov     edi, 57h ; 'W'
0x1800a038b  jmp     loc_1800A0874
0x1800a0390  mov     [rsp+200h+var_1BC], edi
0x1800a0394  mov     r15, rdi
0x1800a0397  mov     [rbp+100h+hMem], rdi
0x1800a039b  mov     [rbp+100h+Block], rdi
0x1800a039f  mov     rsi, [r14+230h]
0x1800a03a6  mov     rcx, [r14+240h]
0x1800a03ad  mov     [rsp+200h+var_1B8], rcx
0x1800a03b2  mov     ecx, [rsi+0Ch]
0x1800a03b5  cmp     eax, ecx
0x1800a03b7  jb      short loc_1800A03CB
0x1800a03b9  cmp     dword ptr [rsi+10h], 7D5h
0x1800a03c0  jnz     short loc_1800A03CB
0x1800a03c2  cmp     dword ptr [rsi+8], 8Ah
0x1800a03c9  jnb     short loc_1800A03D5
0x1800a03cb  mov     edi, 57h ; 'W'
0x1800a03d0  jmp     loc_1800A0767
0x1800a03d5  cmp     ecx, [rsi+8]
0x1800a03d8  jb      short loc_1800A03CB
0x1800a03da  mov     eax, [rsi+28h]
0x1800a03dd  test    eax, eax
0x1800a03df  jz      short loc_1800A0404
0x1800a03e1  cmp     eax, [rsi+8]
0x1800a03e4  jb      short loc_1800A03CB
0x1800a03e6  cmp     eax, ecx
0x1800a03e8  ja      short loc_1800A03CB
0x1800a03ea  test    al, 1
0x1800a03ec  jnz     short loc_1800A03CB
0x1800a03ee  sub     ecx, eax
0x1800a03f0  mov     edx, ecx; unsigned __int64
0x1800a03f2  lea     rcx, [rsi+rax]; unsigned __int16 *
0x1800a03f6  lea     r8, [rsp+200h+var_198]; unsigned __int64 *
0x1800a03fb  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a0400  test    eax, eax
0x1800a0402  js      short loc_1800A03CB
0x1800a0404  mov     eax, [rsi+20h]
0x1800a0407  test    eax, eax
0x1800a0409  jz      short loc_1800A0431
0x1800a040b  cmp     eax, [rsi+8]
0x1800a040e  jb      short loc_1800A03CB
0x1800a0410  mov     ecx, [rsi+0Ch]
0x1800a0413  cmp     eax, ecx
0x1800a0415  ja      short loc_1800A03CB
0x1800a0417  test    al, 1
0x1800a0419  jnz     short loc_1800A03CB
0x1800a041b  sub     ecx, eax
0x1800a041d  mov     edx, ecx; unsigned __int64
0x1800a041f  lea     rcx, [rsi+rax]; unsigned __int16 *
0x1800a0423  lea     r8, [rsp+200h+var_198]; unsigned __int64 *
0x1800a0428  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a042d  test    eax, eax
0x1800a042f  js      short loc_1800A03CB
0x1800a0431  mov     eax, [rsi+24h]
0x1800a0434  test    eax, eax
0x1800a0436  jz      short loc_1800A0462
0x1800a0438  cmp     eax, [rsi+8]
0x1800a043b  jb      short loc_1800A03CB
0x1800a043d  mov     ecx, [rsi+0Ch]
0x1800a0440  cmp     eax, ecx
0x1800a0442  ja      short loc_1800A03CB
0x1800a0444  test    al, 1
0x1800a0446  jnz     short loc_1800A03CB
0x1800a0448  sub     ecx, eax
0x1800a044a  mov     edx, ecx; unsigned __int64
0x1800a044c  lea     rcx, [rsi+rax]; unsigned __int16 *
0x1800a0450  lea     r8, [rsp+200h+var_198]; unsigned __int64 *
0x1800a0455  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a045a  test    eax, eax
0x1800a045c  js      loc_1800A03CB
0x1800a0462  mov     eax, [rsi+1Ch]
0x1800a0465  mov     r8d, 0FFFFFFFFh
0x1800a046b  test    eax, eax
0x1800a046d  jz      short loc_1800A04C1
0x1800a046f  cmp     eax, [rsi+8]
0x1800a0472  jb      loc_1800A03CB
0x1800a0478  cmp     eax, [rsi+0Ch]
0x1800a047b  ja      loc_1800A03CB
0x1800a0481  test    al, 3
0x1800a0483  jnz     loc_1800A03CB
0x1800a0489  lea     ecx, [rax+4]
0x1800a048c  cmp     ecx, eax
0x1800a048e  jb      loc_1800A03CB
0x1800a0494  cmp     ecx, [rsi+0Ch]
0x1800a0497  ja      loc_1800A03CB
0x1800a049d  mov     edx, [rax+rsi]
0x1800a04a0  shl     rdx, 4
0x1800a04a4  cmp     rdx, r8
0x1800a04a7  ja      loc_1800A03CB
0x1800a04ad  lea     eax, [rdx+rcx]
0x1800a04b0  cmp     eax, ecx
0x1800a04b2  jb      loc_1800A03CB
0x1800a04b8  cmp     eax, [rsi+0Ch]
0x1800a04bb  ja      loc_1800A03CB
0x1800a04c1  lea     rcx, [r14+4]; struct _GUID *
0x1800a04c5  lea     r8, [rsp+200h+var_1A8]; struct _SU_POOL_OBJECT **
0x1800a04ca  mov     edx, 2; unsigned int
0x1800a04cf  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x1800a04d4  xor     r14d, r14d
0x1800a04d7  test    eax, eax
0x1800a04d9  jnz     loc_1800A056D
0x1800a04df  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800a04e4  mov     r9d, eax
0x1800a04e7  mov     [rsp+200h+var_1BC], eax
0x1800a04eb  mov     ecx, cs:dword_18039EB68
0x1800a04f1  cmp     ecx, 2
0x1800a04f4  jbe     short loc_1800A0536
0x1800a04f6  mov     [rsp+200h+var_1C0], eax
0x1800a04fa  mov     [rsp+200h+var_1B0], 94Ch
0x1800a0502  mov     [rsp+200h+var_198], rbx
0x1800a0507  lea     rdx, byte_180321A8D
0x1800a050e  lea     rax, [rsp+200h+var_1C0]
0x1800a0513  mov     [rsp+200h+var_1D0], rax
0x1800a0518  lea     rax, [rsp+200h+var_1B0]
0x1800a051d  mov     [rsp+200h+var_1D8], rax
0x1800a0522  lea     rax, [rsp+200h+var_198]
0x1800a0527  mov     [rsp+200h+var_1E0], rax
0x1800a052c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a0531  mov     r9d, [rsp+200h+var_1BC]
0x1800a0536  mov     r12, [rsp+200h+var_1A8]
0x1800a053b  mov     r14, [rsp+200h+var_1B8]
0x1800a0540  test    r9d, r9d
0x1800a0543  jz      loc_1800A076C
0x1800a0549  cmp     r9d, 0B3BBh
0x1800a0550  jz      loc_1800A076C
0x1800a0556  mov     rcx, [rbp+100h+var_158]; struct _SU_SPACE_OBJECT *
0x1800a055a  test    rcx, rcx
0x1800a055d  jz      loc_1800A076C
0x1800a0563  call    ?SuDeleteSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuDeleteSpace(_SU_SPACE_OBJECT *)
0x1800a0568  jmp     loc_1800A076C
0x1800a056d  mov     [rsp+200h+var_1B0], r12d
0x1800a0572  cmp     [rsi+28h], r14d
0x1800a0576  jz      short loc_1800A058A
0x1800a0578  mov     ecx, [rsi+28h]
0x1800a057b  add     rcx, rsi
0x1800a057e  call    ?SmpToSpResiliencyType@@YA?AW4_SP_RESILIENCY_TYPE@@PEBG@Z; SmpToSpResiliencyType(ushort const *)
0x1800a0583  mov     r12d, eax
0x1800a0586  mov     [rsp+200h+var_1B0], eax
0x1800a058a  cmp     [rsi+1Ch], r14d
0x1800a058e  jz      loc_1800A064F
0x1800a0594  cmp     dword ptr [rsi+8], 0C0h
0x1800a059b  jb      short loc_1800A05AF
0x1800a059d  cmp     [rsi+0BCh], r14b
0x1800a05a4  jz      short loc_1800A05AF
0x1800a05a6  movzx   ecx, word ptr [rsi+0BEh]
0x1800a05ad  jmp     short loc_1800A05B4
0x1800a05af  mov     ecx, 1
0x1800a05b4  call    ?SmpToSpFaultDomainType@@YA?AW4_SC_FD_TYPE@@G@Z; SmpToSpFaultDomainType(ushort)
0x1800a05b9  mov     r14d, eax
0x1800a05bc  mov     ebx, [rsi+1Ch]
0x1800a05bf  mov     ecx, [rbx+rsi]
0x1800a05c2  shl     ecx, 4
0x1800a05c5  add     ecx, 8
0x1800a05c8  movsxd  rdx, ecx; uBytes
0x1800a05cb  mov     ecx, 40h ; '@'; uFlags
0x1800a05d0  call    cs:__imp_LocalAlloc
0x1800a05d7  nop     dword ptr [rax+rax+00h]
0x1800a05dc  mov     r15, rax
0x1800a05df  mov     [rbp+100h+hMem], rax
0x1800a05e3  test    rax, rax
0x1800a05e6  jnz     short loc_1800A0627
0x1800a05e8  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800a05ed  mov     r9d, eax
0x1800a05f0  mov     [rsp+200h+var_1BC], eax
0x1800a05f4  mov     ecx, cs:dword_18039EB68
0x1800a05fa  cmp     ecx, 2
0x1800a05fd  jbe     loc_1800A0536
0x1800a0603  mov     [rsp+200h+var_1C0], eax
0x1800a0607  mov     [rsp+200h+var_1B0], 963h
0x1800a060f  lea     rax, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x1800a0616  mov     [rsp+200h+var_198], rax
0x1800a061b  lea     rdx, word_180320986
0x1800a0622  jmp     loc_1800A050E
0x1800a0627  mov     [rax], r14d
0x1800a062a  mov     eax, [rbx+rsi]
0x1800a062d  mov     [r15+4], eax
0x1800a0631  mov     r8d, eax
0x1800a0634  shl     r8, 4; Size
0x1800a0638  lea     rdx, [rsi+4]
0x1800a063c  add     rdx, rbx; Src
0x1800a063f  lea     rcx, [r15+8]; void *
0x1800a0643  call    memcpy_0
0x1800a0648  lea     rbx, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x1800a064f  lea     rax, [rsp+200h+var_1A0]
0x1800a0654  mov     [rsp+200h+var_1E0], rax
0x1800a0659  mov     r9, r15
0x1800a065c  mov     r8d, r12d
0x1800a065f  mov     rcx, [rsp+200h+var_1A8]
0x1800a0664  call    ?SuGetSpaceTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SC_SPACE_USAGE@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_SPACE_INFO@@@Z; SuGetSpaceTemplate(_SU_POOL_OBJECT *,_SC_SPACE_USAGE,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_SPACE_INFO * *)
0x1800a0669  xor     r9d, r9d
0x1800a066c  test    eax, eax
0x1800a066e  jnz     short loc_1800A06D7
0x1800a0670  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800a0675  mov     r9d, eax
0x1800a0678  mov     [rsp+200h+var_1BC], eax
0x1800a067c  mov     eax, cs:dword_18039EB68
0x1800a0682  cmp     eax, 2
0x1800a0685  jbe     short loc_1800A06CD
0x1800a0687  mov     [rsp+200h+var_1C0], r9d
0x1800a068c  mov     [rsp+200h+var_1B0], 973h
0x1800a0694  mov     [rsp+200h+var_198], rbx
0x1800a0699  lea     rax, [rsp+200h+var_1C0]
0x1800a069e  mov     [rsp+200h+var_1D0], rax
0x1800a06a3  lea     rax, [rsp+200h+var_1B0]
0x1800a06a8  mov     [rsp+200h+var_1D8], rax
0x1800a06ad  lea     rax, [rsp+200h+var_198]
0x1800a06b2  mov     [rsp+200h+var_1E0], rax
0x1800a06b7  lea     rdx, word_18031F2A6
0x1800a06be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a06c3  mov     r13, [rsp+200h+var_1A0]
0x1800a06c8  jmp     loc_1800A0531
0x1800a06cd  mov     r13, [rsp+200h+var_1A0]
0x1800a06d2  jmp     loc_1800A0536
0x1800a06d7  mov     bl, [rsi+52h]
0x1800a06da  mov     r11b, [rsi+4Eh]
0x1800a06de  mov     r13, [rsp+200h+var_1A0]
0x1800a06e3  cmp     [rsi+20h], r9d
0x1800a06e7  jz      loc_1800A08AE
0x1800a06ed  mov     r8d, [rsi+20h]
0x1800a06f1  add     r8, rsi; unsigned __int16 *
0x1800a06f4  lea     rcx, [r13+28h]; unsigned __int16 *
0x1800a06f8  mov     edx, 100h; unsigned __int64
0x1800a06fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0702  xor     r9d, r9d
0x1800a0705  test    eax, eax
0x1800a0707  jns     loc_1800A08AE
0x1800a070d  lea     ebx, [r9+5]
0x1800a0711  mov     [rsp+200h+var_1BC], ebx
0x1800a0715  mov     eax, cs:dword_18039EB68
0x1800a071b  cmp     eax, 2
0x1800a071e  jbe     short loc_1800A0762
0x1800a0720  mov     [rsp+200h+var_1B0], 984h
0x1800a0728  lea     rdx, word_1803204EE
0x1800a072f  lea     rax, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x1800a0736  mov     [rsp+200h+var_198], rax
  ... truncated ...
```
