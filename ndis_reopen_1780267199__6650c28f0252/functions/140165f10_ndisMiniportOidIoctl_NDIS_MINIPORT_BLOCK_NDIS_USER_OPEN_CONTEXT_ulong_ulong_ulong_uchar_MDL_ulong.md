# ndisMiniportOidIoctl(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *,ulong,ulong,ulong,uchar *,_MDL *,ulong &)

- ea: `0x140165f10`
- end: `0x14016652e`
- name: `?ndisMiniportOidIoctl@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@KKKPEAEPEAU_MDL@@AEAK@Z`
- size: `1566`
- prototype: `int(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_USER_OPEN_CONTEXT *, unsigned int, unsigned int, unsigned int, unsigned __int8 *, struct _MDL *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x1400115c0`
- `0x140040800`

## callees

- `0x14001c0c0`
- `0x14003eb20`
- `0x14003f0e0`
- `0x140054ac0`
- `0x1400550e0`
- `0x1400595e0`
- `0x14005a660`
- `0x14005b730`
- `0x1400ca2c4`
- `0x1400eb380`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x140165f10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14016644e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14016647a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14016644e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14016647a`
- `ntoskrnl!EtwActivityIdControl` at `0x140166049`
- `ntoskrnl!EtwActivityIdControl` at `0x140166049`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166245`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016639d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166245`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016639d`
- `ntoskrnl!ExAllocatePool2` at `0x140166195`
- `ntoskrnl!ExAllocatePool2` at `0x140166312`
- `ntoskrnl!ExAllocatePool2` at `0x140174ec9`
- `ntoskrnl!ExAllocatePool2` at `0x140166195`
- `ntoskrnl!ExAllocatePool2` at `0x140166312`
- `ntoskrnl!ExAllocatePool2` at `0x140174ec9`

## pseudocode

```c
__int64 __fastcall ndisMiniportOidIoctl(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NDIS_USER_OPEN_CONTEXT *a2,
        int a3,
        unsigned int a4,
        unsigned int Size,
        unsigned __int8 *Src,
        struct _MDL *MemoryDescriptorList,
        unsigned int *a8)
{
  __int64 v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  char v14; // r10
  unsigned __int8 *v15; // r14
  int v16; // edx
  int v17; // r8d
  NDIS_OID v18; // r12d
  int v19; // ecx
  int v20; // eax
  NDIS_REQUEST_TYPE RequestType; // ecx
  UINT BytesNeeded; // eax
  int v23; // edx
  unsigned int v24; // edi
  size_t ByteCount; // r14
  __int64 v26; // rsi
  unsigned int v27; // r13d
  size_t v28; // rsi
  void *v29; // rax
  size_t v30; // rsi
  ULONG v31; // ebx
  PVOID v32; // rax
  int StatisticsOids; // eax
  unsigned __int8 v34; // r8
  int v36; // ecx
  unsigned int v37; // r13d
  void *BugCheckOnFailure; // r10
  PVOID MappedSystemVa; // rsi
  void *Pool2; // rax
  void *v41; // rbx
  int v42; // eax
  unsigned int BytesWritten; // r9d
  _DWORD *v44; // r8
  unsigned int v45; // r9d
  int v46; // edx
  int v47; // ecx
  int *v48; // rsi
  int v49; // ecx
  unsigned int v50; // esi
  void *v51; // rax
  size_t v52; // rdi
  __int64 v53; // rax
  ULONG Priority[2]; // [rsp+28h] [rbp-D8h]
  __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h]
  char v57[16]; // [rsp+60h] [rbp-A0h]
  struct _NDIS_OID_REQUEST v58; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)v57 = a1;
  v56 = (__int64)a8;
  v10 = a4;
  memset(&v58, 0, 0xF8u);
  LOBYTE(v55) = 0;
  *a8 = 0;
  if ( a3 != 1507484 )
  {
    ByteCount = 0;
    v24 = 0;
    switch ( a3 )
    {
      case 1507330:
        if ( (unsigned int)v10 < 4 )
          return (unsigned int)-1073741811;
        v37 = *(_DWORD *)Src;
        if ( !(unsigned __int8)ndisIsOidAllowedFromUsermode(*(unsigned int *)Src) )
          return (unsigned int)-1073741790;
        if ( !(unsigned __int8)ndisValidOid(a2, v37) )
          return (unsigned int)-1073741811;
        if ( MemoryDescriptorList && (ByteCount = MemoryDescriptorList->ByteCount, (_DWORD)ByteCount) )
        {
          if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
            MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(
                               MemoryDescriptorList,
                               0,
                               MmCached,
                               0,
                               (ULONG)BugCheckOnFailure,
                               0x40000000u);
          if ( !MappedSystemVa )
            return v24;
          Pool2 = (void *)ExAllocatePool2(64, ByteCount, 1835091022);
          v41 = Pool2;
          if ( !Pool2 )
            return (unsigned int)-1073741670;
          memmove(Pool2, MappedSystemVa, ByteCount);
        }
        else
        {
          MappedSystemVa = BugCheckOnFailure;
          v41 = BugCheckOnFailure;
        }
        v42 = ndisQueryDeviceOid(a2, &v58, v37, v41, ByteCount);
        BytesWritten = v58.DATA.QUERY_INFORMATION.BytesWritten;
        v44 = (_DWORD *)v56;
        *(_DWORD *)v56 = v58.DATA.QUERY_INFORMATION.BytesWritten;
        if ( BytesWritten > (unsigned int)ByteCount )
        {
          *v44 = 0;
          v24 = ndisConvertNdisStatusToNtStatusForIoctl(0, -1073676266, 0);
        }
        else
        {
          v24 = ndisConvertNdisStatusToNtStatusForIoctl(0, v42, 0);
          if ( !v46 && v45 && MappedSystemVa )
          {
            if ( !v41 )
              return v24;
            memmove(MappedSystemVa, v41, v45);
            goto LABEL_66;
          }
        }
        if ( !v41 )
          return v24;
LABEL_66:
        ExFreePoolWithTag(v41, 0);
        return v24;
      case 1507334:
        v48 = (int *)*((_QWORD *)a2 + 2);
        if ( !v48 )
          return (unsigned int)-1073741808;
        v27 = *v48;
        v30 = *((_QWORD *)v48 + 1);
        goto LABEL_33;
      case 1507342:
        goto LABEL_29;
      case 1507368:
      case 1507372:
        if ( a3 == 1507372 )
        {
          if ( (unsigned int)v10 < 4 || ((unsigned __int8)Src & 3) != 0 || (v10 & 3) != 0 )
            return (unsigned int)-1073741811;
          v50 = (unsigned int)v10 >> 2;
          v51 = (void *)ExAllocatePool2(66, 4LL * v50, 1835091022);
          ByteCount = (size_t)v51;
          if ( !v51 )
            return v24;
          memmove(v51, Src, 4LL * v50);
          v52 = ByteCount;
        }
        else
        {
          v53 = *((_QWORD *)a2 + 2);
          if ( !v53 )
            return (unsigned int)-1073741808;
          v50 = *(_DWORD *)v53;
          v52 = *(_QWORD *)(v53 + 8);
        }
        if ( !(unsigned __int8)ndisIsOidAllowedFromUsermode_0(v52, v50) )
        {
          v24 = -1073741790;
          goto LABEL_41;
        }
        Priority[0] = Size;
        StatisticsOids = ndisQueryStatisticsOids(v57[0], Src, *(size_t *)Priority, v56, 1, (__int64)&v55);
        v34 = 0;
        goto LABEL_40;
      case 1507376:
        if ( (unsigned int)v10 < 0xC
          || ((unsigned __int8)Src & 7) != 0
          || !(unsigned __int8)ndisValidOid(a2, *(unsigned int *)Src) )
        {
          return (unsigned int)-1073741811;
        }
        memset(&v58, 0, 0xF8u);
        v23 = ndisMethodDeviceOid(a2, &v58, Src, (unsigned int)v10, Size);
        *(_DWORD *)v56 = v58.DATA.METHOD_INFORMATION.BytesWritten + 8;
        return (unsigned int)ndisConvertNdisStatusToNtStatusForIoctl(0, v23, 0);
      case 1507390:
        LOBYTE(v55) = 1;
LABEL_29:
        if ( (unsigned int)v10 < 4 || ((unsigned __int8)Src & 3) != 0 || (v10 & 3) != 0 )
          return (unsigned int)-1073741811;
        v26 = (unsigned int)v10 >> 2;
        v27 = v26;
        v28 = 4 * v26;
        v29 = (void *)ExAllocatePool2(66, v28, 1835091022);
        ByteCount = (size_t)v29;
        if ( !v29 )
          return v24;
        memmove(v29, Src, v28);
        v30 = ByteCount;
LABEL_33:
        if ( (unsigned __int8)ndisIsOidAllowedFromUsermode_0(v30, v27) )
        {
          if ( MemoryDescriptorList )
          {
            v31 = MemoryDescriptorList->ByteCount;
            if ( v31 )
            {
              v32 = (MemoryDescriptorList->MdlFlags & 5) != 0
                  ? MemoryDescriptorList->MappedSystemVa
                  : MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000000u);
              if ( v32 )
              {
                Priority[0] = v31;
                StatisticsOids = ndisQueryStatisticsOids(v57[0], v32, *(size_t *)Priority, v56, 0, (__int64)&v55);
                v34 = v55;
LABEL_40:
                v24 = ndisConvertNdisStatusToNtStatusForIoctl(0, StatisticsOids, v34);
              }
            }
          }
        }
        else
        {
          v24 = -1073741790;
        }
LABEL_41:
        if ( ByteCount )
          ExFreePoolWithTag((PVOID)ByteCount, 0);
        return v24;
      default:
        return (unsigned int)-1073741822;
    }
  }
  if ( (unsigned int)v10 < 0x2C )
    return (unsigned int)-1073741811;
  if ( Size < 0x2C )
    return (unsigned int)-1073741811;
  if ( *Src != 0xB9 )
    return (unsigned int)-1073741811;
  if ( *((_WORD *)Src + 1) < 0x2Cu )
    return (unsigned int)-1073741811;
  v11 = *((unsigned __int16 *)Src + 20);
  if ( v11 < 0x2C )
    return (unsigned int)-1073741811;
  v12 = v10;
  if ( (unsigned int)v10 >= Size )
    v12 = Size;
  if ( v11 > v12 )
    return (unsigned int)-1073741811;
  if ( !Src[1] )
    return (unsigned int)-1071448060;
  if ( !(unsigned __int8)ndisIsOidAllowedFromUsermode(*((unsigned int *)Src + 3)) )
    return (unsigned int)-1073741790;
  if ( !(unsigned __int8)ndisValidOid(a2, v13) )
    return (unsigned int)-1073741637;
  v15 = &Src[*((unsigned __int16 *)Src + 20)];
  if ( ((unsigned __int8)v15 & 3) != 0 )
    return (unsigned int)-2147483646;
  if ( *((_BYTE *)a2 + 24) == v14 && (*((_DWORD *)Src + 1) & 0xFFFFFFFD) != 0 )
    return (unsigned int)-1073741790;
  memset(&v58, 0, 0xF8u);
  *(_DWORD *)&v58.NdisReserved[16] = 8;
  *(_QWORD *)&v58.NdisReserved[32] = &ndisIntReqIoctl;
  EtwActivityIdControl(3u, (LPGUID)&v58.NdisReserved[96]);
  v18 = *((_DWORD *)Src + 3);
  v58.RequestType = *((_DWORD *)Src + 1);
  v58.PortNumber = *((_DWORD *)Src + 2);
  v58.Header = (NDIS_OBJECT_HEADER)15466902;
  v58.DATA.QUERY_INFORMATION.Oid = v18;
  v58.DATA.QUERY_INFORMATION.InformationBuffer = v15;
  v58.DATA.QUERY_INFORMATION.InformationBufferLength = 0;
  if ( (unsigned int)v10 < Size )
    memset(&Src[v10], 0, Size - (unsigned int)v10);
  v19 = *((_DWORD *)Src + 1);
  if ( v19 == 2 || !v19 )
  {
    v58.DATA.QUERY_INFORMATION.InformationBufferLength = Size - *((unsigned __int16 *)Src + 20);
    memset(v15, 0, v58.DATA.QUERY_INFORMATION.InformationBufferLength);
    LOBYTE(v18) = v58.DATA.QUERY_INFORMATION.Oid;
  }
  else
  {
    v36 = v19 - 1;
    if ( v36 )
    {
      if ( v36 != 11 )
        return (unsigned int)-1073741811;
      v49 = *((unsigned __int16 *)Src + 20);
      v58.DATA.QUERY_INFORMATION.InformationBufferLength = v10 - v49;
      v58.DATA.QUERY_INFORMATION.BytesWritten = Size - v49;
      v58.DATA.QUERY_INFORMATION.BytesNeeded = *((_DWORD *)Src + 4);
    }
    else
    {
      v58.DATA.QUERY_INFORMATION.InformationBufferLength = v10 - *((unsigned __int16 *)Src + 20);
    }
  }
  v58.Timeout = *((_DWORD *)Src + 5);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_qDq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v16,
      v17,
      15,
      (struct _GUID *)&WPP_a48ea93cdc4f3f22353657f4d507625f_Traceguids,
      (char)&v58,
      v18,
      v57[0]);
  }
  v20 = ndisQuerySetMiniport(*((struct _NDIS_MINIPORT_BLOCK **)a2 + 1), 0, &v58, 0, 0);
  RequestType = v58.RequestType;
  *((_DWORD *)Src + 9) = v20;
  if ( RequestType == NdisRequestQueryStatistics || RequestType == NdisRequestQueryInformation )
  {
    *((_DWORD *)Src + 6) = v58.DATA.QUERY_INFORMATION.BytesWritten;
LABEL_23:
    BytesNeeded = v58.DATA.QUERY_INFORMATION.BytesNeeded;
LABEL_24:
    *((_DWORD *)Src + 8) = BytesNeeded;
    goto LABEL_25;
  }
  v47 = RequestType - 1;
  if ( !v47 )
  {
    *((_DWORD *)Src + 7) = v58.DATA.QUERY_INFORMATION.BytesWritten;
    goto LABEL_23;
  }
  if ( v47 == 11 )
  {
    *((_QWORD *)Src + 3) = *(_QWORD *)&v58.DATA.METHOD_INFORMATION.BytesWritten;
    BytesNeeded = v58.DATA.METHOD_INFORMATION.BytesNeeded;
    goto LABEL_24;
  }
LABEL_25:
  v23 = 0;
  *(_DWORD *)v56 = Size;
  return (unsigned int)ndisConvertNdisStatusToNtStatusForIoctl(0, v23, 0);
}

```

## disassembly

```asm
0x140165f10  mov     [rsp-8+arg_10], rbx
0x140165f15  push    rbp
0x140165f16  push    rsi
0x140165f17  push    rdi
0x140165f18  push    r12
0x140165f1a  push    r13
0x140165f1c  push    r14
0x140165f1e  push    r15
0x140165f20  lea     rbp, [rsp-80h]
0x140165f25  sub     rsp, 180h
0x140165f2c  mov     rax, cs:__security_cookie
0x140165f33  xor     rax, rsp
0x140165f36  mov     [rbp+0B0h+var_40], rax
0x140165f3a  mov     rdi, [rbp+0B0h+arg_38]
0x140165f41  mov     r13d, r8d
0x140165f44  mov     rbx, [rbp+0B0h+Src]
0x140165f4b  mov     r15, rdx
0x140165f4e  mov     r12, [rbp+0B0h+MemoryDescriptorList]
0x140165f55  xor     edx, edx; Val
0x140165f57  mov     qword ptr [rsp+1B0h+var_150], rcx
0x140165f5c  mov     r8d, 0F8h; Size
0x140165f62  lea     rcx, [rsp+1B0h+var_140]; void *
0x140165f67  mov     [rsp+1B0h+var_158], rdi
0x140165f6c  mov     esi, r9d
0x140165f6f  call    memset
0x140165f74  xor     r10d, r10d
0x140165f77  mov     byte ptr [rsp+1B0h+var_160], 0
0x140165f7c  mov     [rdi], r10d
0x140165f7f  cmp     r13d, 17009Ch
0x140165f86  jnz     loc_140166125
0x140165f8c  cmp     esi, 2Ch ; ','
0x140165f8f  jb      loc_140166295
0x140165f95  mov     edi, dword ptr [rbp+0B0h+Size]
0x140165f9b  cmp     edi, 2Ch ; ','
0x140165f9e  jb      loc_140166295
0x140165fa4  cmp     byte ptr [rbx], 0B9h
0x140165fa7  jnz     loc_140166295
0x140165fad  cmp     word ptr [rbx+2], 2Ch ; ','
0x140165fb2  jb      loc_140166295
0x140165fb8  movzx   eax, word ptr [rbx+28h]
0x140165fbc  cmp     eax, 2Ch ; ','
0x140165fbf  jb      loc_140166295
0x140165fc5  cmp     esi, edi
0x140165fc7  mov     ecx, esi
0x140165fc9  cmovnb  ecx, edi
0x140165fcc  cmp     eax, ecx
0x140165fce  ja      loc_140166295
0x140165fd4  cmp     byte ptr [rbx+1], 1
0x140165fd8  jb      loc_1401664DC
0x140165fde  mov     ecx, [rbx+0Ch]
0x140165fe1  call    ndisIsOidAllowedFromUsermode
0x140165fe6  test    al, al
0x140165fe8  jz      loc_1401662A9
0x140165fee  mov     edx, ecx
0x140165ff0  mov     rcx, r15
0x140165ff3  call    ndisValidOid
0x140165ff8  test    al, al
0x140165ffa  jz      loc_1401664E6
0x140166000  movzx   r14d, word ptr [rbx+28h]
0x140166005  add     r14, rbx
0x140166008  test    r14b, 3
0x14016600c  jnz     loc_1401664F0
0x140166012  cmp     [r15+18h], r10b
0x140166016  jz      loc_14016629C
0x14016601c  xor     edx, edx; Val
0x14016601e  lea     rcx, [rsp+1B0h+var_140]; void *
0x140166023  mov     r8d, 0F8h; Size
0x140166029  call    memset
0x14016602e  lea     rax, ?ndisIntReqIoctl@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqIoctl
0x140166035  mov     dword ptr [rbp+0B0h+var_140.NdisReserved+10h], 8
0x14016603c  lea     rdx, [rbp+0B0h+var_140.NdisReserved+60h]; ActivityId
0x140166040  mov     qword ptr [rbp+0B0h+var_140.NdisReserved+20h], rax
0x140166044  mov     ecx, 3; ControlCode
0x140166049  call    cs:__imp_EtwActivityIdControl
0x140166050  nop     dword ptr [rax+rax+00h]
0x140166055  mov     eax, [rbx+4]
0x140166058  xor     r13d, r13d
0x14016605b  mov     r12d, [rbx+0Ch]
0x14016605f  mov     [rsp+1B0h+var_140.RequestType], eax
0x140166063  mov     eax, [rbx+8]
0x140166066  mov     [rsp+1B0h+var_140.PortNumber], eax
0x14016606a  mov     dword ptr [rsp+1B0h+var_140.Header.Type], 0EC0196h
0x140166072  mov     dword ptr [rbp+0B0h+var_140.DATA], r12d
0x140166076  mov     qword ptr [rbp+0B0h+var_140.DATA+8], r14
0x14016607a  mov     dword ptr [rbp+0B0h+var_140.DATA+10h], r13d
0x14016607e  cmp     esi, edi
0x140166080  jnb     short loc_140166093
0x140166082  mov     r8d, edi
0x140166085  lea     rcx, [rbx+rsi]; void *
0x140166089  sub     r8d, esi; Size
0x14016608c  xor     edx, edx; Val
0x14016608e  call    memset
0x140166093  mov     ecx, [rbx+4]
0x140166096  cmp     ecx, 2
0x140166099  jnz     loc_14016627B
0x14016609f  movzx   eax, word ptr [rbx+28h]
0x1401660a3  mov     r8d, edi
0x1401660a6  sub     r8d, eax; Size
0x1401660a9  xor     edx, edx; Val
0x1401660ab  mov     rcx, r14; void *
0x1401660ae  mov     dword ptr [rbp+0B0h+var_140.DATA+10h], r8d
0x1401660b2  call    memset
0x1401660b7  mov     r12d, dword ptr [rbp+0B0h+var_140.DATA]
0x1401660bb  mov     eax, [rbx+14h]
0x1401660be  mov     [rsp+1B0h+var_140.Timeout], eax
0x1401660c2  lea     rax, WPP_RECORDER_INITIALIZED
0x1401660c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401660d0  jnz     loc_1401663B9
0x1401660d6  mov     rcx, [r15+8]; struct _NDIS_MINIPORT_BLOCK *
0x1401660da  lea     r8, [rsp+1B0h+var_140]; struct _NDIS_OID_REQUEST *
0x1401660df  xor     r9d, r9d; unsigned __int8
0x1401660e2  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], r13; struct _NDIS_FILTER_BLOCK *
0x1401660e7  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x1401660e9  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x1401660ee  mov     ecx, [rsp+1B0h+var_140.RequestType]
0x1401660f2  mov     [rbx+24h], eax
0x1401660f5  cmp     ecx, 2
0x1401660f8  jnz     loc_1401663FB
0x1401660fe  mov     eax, dword ptr [rbp+0B0h+var_140.DATA+14h]
0x140166101  mov     [rbx+18h], eax
0x140166104  mov     eax, dword ptr [rbp+0B0h+var_140.DATA+18h]
0x140166107  mov     [rbx+20h], eax
0x14016610a  mov     r8, [rsp+1B0h+var_158]
0x14016610f  xor     edx, edx; int
0x140166111  mov     [r8], edi
0x140166114  xor     r8d, r8d; unsigned __int8
0x140166117  xor     ecx, ecx; int
0x140166119  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x14016611e  mov     edi, eax
0x140166120  jmp     loc_140166251
0x140166125  lea     eax, [r13-170002h]; switch 61 cases
0x14016612c  cmp     eax, 3Ch
0x14016612f  ja      def_140166154; jumptable 0000000140166154 default case, cases 1507331-1507333,1507335-1507341,1507343-1507367,1507369-1507371,1507373-1507375,1507377-1507389
0x140166135  lea     rdx, cs:140000000h
0x14016613c  mov     r14, r10
0x14016613f  movzx   eax, ds:(byte_1401046B4 - 140000000h)[rdx+rax]
0x140166147  mov     edi, r10d
0x14016614a  mov     ecx, ds:(jpt_140166154 - 140000000h)[rdx+rax*4]
0x140166151  add     rcx, rdx
0x140166154  jmp     rcx; switch jump
0x14016615a  mov     byte ptr [rsp+1B0h+var_160], 1; jumptable 0000000140166154 case 1507390
0x14016615f  cmp     esi, 4; jumptable 0000000140166154 case 1507342
0x140166162  jb      loc_140166295
0x140166168  test    bl, 3
0x14016616b  setz    cl
0x14016616e  test    sil, 3
0x140166172  setz    al
0x140166175  test    al, cl
0x140166177  jz      loc_140166295
0x14016617d  shr     esi, 2
0x140166180  mov     r8d, 6D61444Eh
0x140166186  mov     r13d, esi
0x140166189  mov     ecx, 42h ; 'B'
0x14016618e  shl     rsi, 2
0x140166192  mov     rdx, rsi
0x140166195  call    cs:__imp_ExAllocatePool2
0x14016619c  nop     dword ptr [rax+rax+00h]
0x1401661a1  mov     r14, rax
0x1401661a4  test    rax, rax
0x1401661a7  jz      loc_140166251
0x1401661ad  mov     r8, rsi; Size
0x1401661b0  mov     rdx, rbx; Src
0x1401661b3  mov     rcx, rax; void *
0x1401661b6  call    memmove
0x1401661bb  mov     rsi, r14
0x1401661be  mov     edx, r13d
0x1401661c1  mov     rcx, rsi
0x1401661c4  call    ndisIsOidAllowedFromUsermode_0
0x1401661c9  test    al, al
0x1401661cb  jz      loc_1401664C8
0x1401661d1  test    r12, r12
0x1401661d4  jz      short loc_14016623B
0x1401661d6  mov     ebx, [r12+28h]
0x1401661db  test    ebx, ebx
0x1401661dd  jz      short loc_14016623B
0x1401661df  test    byte ptr [r12+0Ah], 5
0x1401661e5  jz      loc_140166434
0x1401661eb  mov     rax, [r12+18h]
0x1401661f0  test    rax, rax
0x1401661f3  jz      short loc_14016623B
0x1401661f5  mov     r8, [rsp+1B0h+var_158]
0x1401661fa  lea     rcx, [rsp+1B0h+var_160]
0x1401661ff  mov     [rsp+1B0h+var_170], rcx; __int64
0x140166204  mov     r9d, r13d
0x140166207  mov     rcx, qword ptr [rsp+1B0h+var_150]; char
0x14016620c  mov     rdx, r15
0x14016620f  mov     [rsp+1B0h+var_178], dil; char
0x140166214  mov     qword ptr [rsp+1B0h+var_180], r8; __int64
0x140166219  mov     r8, rsi
0x14016621c  mov     [rsp+1B0h+Priority], ebx; Size
0x140166220  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], rax; void *
0x140166225  call    ndisQueryStatisticsOids
0x14016622a  movzx   r8d, byte ptr [rsp+1B0h+var_160]; unsigned __int8
0x140166230  mov     edx, eax; int
0x140166232  xor     ecx, ecx; int
0x140166234  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x140166239  mov     edi, eax
0x14016623b  test    r14, r14
0x14016623e  jz      short loc_140166251
0x140166240  xor     edx, edx; Tag
0x140166242  mov     rcx, r14; P
0x140166245  call    cs:__imp_ExFreePoolWithTag
0x14016624c  nop     dword ptr [rax+rax+00h]
0x140166251  mov     eax, edi
0x140166253  mov     rcx, [rbp+0B0h+var_40]
0x140166257  xor     rcx, rsp; StackCookie
0x14016625a  call    __security_check_cookie
0x14016625f  mov     rbx, [rsp+1B0h+arg_10]
0x140166267  add     rsp, 180h
0x14016626e  pop     r15
0x140166270  pop     r14
0x140166272  pop     r13
0x140166274  pop     r12
0x140166276  pop     rdi
0x140166277  pop     rsi
0x140166278  pop     rbp
0x140166279  retn
0x14016627b  test    ecx, ecx
0x14016627d  jz      loc_14016609F
0x140166283  sub     ecx, 1
0x140166286  jz      loc_140166515
0x14016628c  cmp     ecx, 0Bh
0x14016628f  jz      loc_1401664FA
0x140166295  mov     edi, 0C000000Dh
0x14016629a  jmp     short loc_140166251
0x14016629c  test    dword ptr [rbx+4], 0FFFFFFFDh
0x1401662a3  jz      loc_14016601C
0x1401662a9  mov     edi, 0C0000022h
0x1401662ae  jmp     short loc_140166251
0x1401662b0  cmp     esi, 4; jumptable 0000000140166154 case 1507330
0x1401662b3  jb      short loc_140166295
0x1401662b5  mov     r13d, [rbx]
0x1401662b8  mov     ecx, r13d
0x1401662bb  call    ndisIsOidAllowedFromUsermode
0x1401662c0  test    al, al
0x1401662c2  jz      short loc_1401662A9
0x1401662c4  mov     edx, r13d
0x1401662c7  mov     rcx, r15
0x1401662ca  call    ndisValidOid
0x1401662cf  test    al, al
0x1401662d1  jz      short loc_140166295
0x1401662d3  test    r12, r12
0x1401662d6  jz      loc_140166429
0x1401662dc  mov     r14d, [r12+28h]
0x1401662e1  test    r14d, r14d
0x1401662e4  jz      loc_140166429
0x1401662ea  test    byte ptr [r12+0Ah], 5
0x1401662f0  jz      loc_14016645F
0x1401662f6  mov     rsi, [r12+18h]
0x1401662fb  test    rsi, rsi
0x1401662fe  jz      loc_140166251
0x140166304  mov     r8d, 6D61444Eh
0x14016630a  mov     rdx, r14
0x14016630d  mov     ecx, 40h ; '@'
0x140166312  call    cs:__imp_ExAllocatePool2
0x140166319  nop     dword ptr [rax+rax+00h]
0x14016631e  mov     rbx, rax
0x140166321  test    rax, rax
0x140166324  jz      loc_14016648E
0x14016632a  mov     r8, r14; Size
0x14016632d  mov     rdx, rsi; Src
0x140166330  mov     rcx, rax; void *
0x140166333  call    memmove
0x140166338  mov     r9, rbx; void *
0x14016633b  mov     [rsp+1B0h+BugCheckOnFailure], r14d; unsigned int
0x140166340  mov     r8d, r13d; unsigned int
0x140166343  lea     rdx, [rsp+1B0h+var_140]; struct _NDIS_OID_REQUEST *
0x140166348  mov     rcx, r15; struct _NDIS_USER_OPEN_CONTEXT *
0x14016634b  call    ?ndisQueryDeviceOid@@YAHPEAU_NDIS_USER_OPEN_CONTEXT@@PEAU_NDIS_OID_REQUEST@@KPEAXI@Z; ndisQueryDeviceOid(_NDIS_USER_OPEN_CONTEXT *,_NDIS_OID_REQUEST *,ulong,void *,uint)
0x140166350  mov     r9d, dword ptr [rbp+0B0h+var_140.DATA+14h]
0x140166354  xor     ecx, ecx; int
0x140166356  mov     r8, [rsp+1B0h+var_158]
0x14016635b  mov     edx, eax; int
0x14016635d  mov     [r8], r9d
0x140166360  cmp     r9d, r14d
0x140166363  ja      loc_140166498
0x140166369  xor     r8d, r8d; unsigned __int8
0x14016636c  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x140166371  mov     edi, eax
0x140166373  test    edx, edx
0x140166375  jnz     short loc_1401663AE
0x140166377  test    r9d, r9d
0x14016637a  jz      short loc_1401663AE
0x14016637c  test    rsi, rsi
0x14016637f  jz      short loc_1401663AE
0x140166381  test    rbx, rbx
0x140166384  jz      loc_140166251
0x14016638a  mov     r8d, r9d; Size
0x14016638d  mov     rdx, rbx; Src
0x140166390  mov     rcx, rsi; void *
0x140166393  call    memmove
0x140166398  xor     edx, edx; Tag
0x14016639a  mov     rcx, rbx; P
0x14016639d  call    cs:__imp_ExFreePoolWithTag
0x1401663a4  nop     dword ptr [rax+rax+00h]
0x1401663a9  jmp     loc_140166251
0x1401663ae  test    rbx, rbx
0x1401663b1  jz      loc_140166251
0x1401663b7  jmp     short loc_140166398
0x1401663b9  mov     rax, qword ptr [rsp+1B0h+var_150]
  ... truncated ...
```
