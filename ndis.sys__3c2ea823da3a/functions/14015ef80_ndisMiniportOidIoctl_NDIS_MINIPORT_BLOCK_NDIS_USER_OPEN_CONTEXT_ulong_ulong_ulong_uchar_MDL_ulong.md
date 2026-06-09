# ndisMiniportOidIoctl(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *,ulong,ulong,ulong,uchar *,_MDL *,ulong &)

- ea: `0x14015ef80`
- end: `0x14015f59e`
- name: `?ndisMiniportOidIoctl@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@KKKPEAEPEAU_MDL@@AEAK@Z`
- size: `1566`
- prototype: `int(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_USER_OPEN_CONTEXT *, unsigned int, unsigned int, unsigned int, unsigned __int8 *, struct _MDL *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x14001d460`
- `0x14003e050`

## callees

- `0x140027f60`
- `0x14003c370`
- `0x14003c930`
- `0x14004f3d0`
- `0x14004f9f0`
- `0x1400543c0`
- `0x140055e20`
- `0x140056ef0`
- `0x1400c5114`
- `0x1400e6160`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x14015ef80`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14015f4be`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14015f4ea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14015f4be`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14015f4ea`
- `ntoskrnl!EtwActivityIdControl` at `0x14015f0b9`
- `ntoskrnl!EtwActivityIdControl` at `0x14015f0b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015f2b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015f40d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015f2b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015f40d`
- `ntoskrnl!ExAllocatePool2` at `0x14015f205`
- `ntoskrnl!ExAllocatePool2` at `0x14015f382`
- `ntoskrnl!ExAllocatePool2` at `0x14016e013`
- `ntoskrnl!ExAllocatePool2` at `0x14015f205`
- `ntoskrnl!ExAllocatePool2` at `0x14015f382`
- `ntoskrnl!ExAllocatePool2` at `0x14016e013`

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
0x14015ef80  mov     [rsp-8+arg_10], rbx
0x14015ef85  push    rbp
0x14015ef86  push    rsi
0x14015ef87  push    rdi
0x14015ef88  push    r12
0x14015ef8a  push    r13
0x14015ef8c  push    r14
0x14015ef8e  push    r15
0x14015ef90  lea     rbp, [rsp-80h]
0x14015ef95  sub     rsp, 180h
0x14015ef9c  mov     rax, cs:__security_cookie
0x14015efa3  xor     rax, rsp
0x14015efa6  mov     [rbp+0B0h+var_40], rax
0x14015efaa  mov     rdi, [rbp+0B0h+arg_38]
0x14015efb1  mov     r13d, r8d
0x14015efb4  mov     rbx, [rbp+0B0h+Src]
0x14015efbb  mov     r15, rdx
0x14015efbe  mov     r12, [rbp+0B0h+MemoryDescriptorList]
0x14015efc5  xor     edx, edx; Val
0x14015efc7  mov     qword ptr [rsp+1B0h+var_150], rcx
0x14015efcc  mov     r8d, 0F8h; Size
0x14015efd2  lea     rcx, [rsp+1B0h+var_140]; void *
0x14015efd7  mov     [rsp+1B0h+var_158], rdi
0x14015efdc  mov     esi, r9d
0x14015efdf  call    memset
0x14015efe4  xor     r10d, r10d
0x14015efe7  mov     byte ptr [rsp+1B0h+var_160], 0
0x14015efec  mov     [rdi], r10d
0x14015efef  cmp     r13d, 17009Ch
0x14015eff6  jnz     loc_14015F195
0x14015effc  cmp     esi, 2Ch ; ','
0x14015efff  jb      loc_14015F305
0x14015f005  mov     edi, dword ptr [rbp+0B0h+Size]
0x14015f00b  cmp     edi, 2Ch ; ','
0x14015f00e  jb      loc_14015F305
0x14015f014  cmp     byte ptr [rbx], 0B9h
0x14015f017  jnz     loc_14015F305
0x14015f01d  cmp     word ptr [rbx+2], 2Ch ; ','
0x14015f022  jb      loc_14015F305
0x14015f028  movzx   eax, word ptr [rbx+28h]
0x14015f02c  cmp     eax, 2Ch ; ','
0x14015f02f  jb      loc_14015F305
0x14015f035  cmp     esi, edi
0x14015f037  mov     ecx, esi
0x14015f039  cmovnb  ecx, edi
0x14015f03c  cmp     eax, ecx
0x14015f03e  ja      loc_14015F305
0x14015f044  cmp     byte ptr [rbx+1], 1
0x14015f048  jb      loc_14015F54C
0x14015f04e  mov     ecx, [rbx+0Ch]
0x14015f051  call    ndisIsOidAllowedFromUsermode
0x14015f056  test    al, al
0x14015f058  jz      loc_14015F319
0x14015f05e  mov     edx, ecx
0x14015f060  mov     rcx, r15
0x14015f063  call    ndisValidOid
0x14015f068  test    al, al
0x14015f06a  jz      loc_14015F556
0x14015f070  movzx   r14d, word ptr [rbx+28h]
0x14015f075  add     r14, rbx
0x14015f078  test    r14b, 3
0x14015f07c  jnz     loc_14015F560
0x14015f082  cmp     [r15+18h], r10b
0x14015f086  jz      loc_14015F30C
0x14015f08c  xor     edx, edx; Val
0x14015f08e  lea     rcx, [rsp+1B0h+var_140]; void *
0x14015f093  mov     r8d, 0F8h; Size
0x14015f099  call    memset
0x14015f09e  lea     rax, ?ndisIntReqIoctl@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqIoctl
0x14015f0a5  mov     dword ptr [rbp+0B0h+var_140.NdisReserved+10h], 8
0x14015f0ac  lea     rdx, [rbp+0B0h+var_140.NdisReserved+60h]; ActivityId
0x14015f0b0  mov     qword ptr [rbp+0B0h+var_140.NdisReserved+20h], rax
0x14015f0b4  mov     ecx, 3; ControlCode
0x14015f0b9  call    cs:__imp_EtwActivityIdControl
0x14015f0c0  nop     dword ptr [rax+rax+00h]
0x14015f0c5  mov     eax, [rbx+4]
0x14015f0c8  xor     r13d, r13d
0x14015f0cb  mov     r12d, [rbx+0Ch]
0x14015f0cf  mov     [rsp+1B0h+var_140.RequestType], eax
0x14015f0d3  mov     eax, [rbx+8]
0x14015f0d6  mov     [rsp+1B0h+var_140.PortNumber], eax
0x14015f0da  mov     dword ptr [rsp+1B0h+var_140.Header.Type], 0EC0196h
0x14015f0e2  mov     dword ptr [rbp+0B0h+var_140.DATA], r12d
0x14015f0e6  mov     qword ptr [rbp+0B0h+var_140.DATA+8], r14
0x14015f0ea  mov     dword ptr [rbp+0B0h+var_140.DATA+10h], r13d
0x14015f0ee  cmp     esi, edi
0x14015f0f0  jnb     short loc_14015F103
0x14015f0f2  mov     r8d, edi
0x14015f0f5  lea     rcx, [rbx+rsi]; void *
0x14015f0f9  sub     r8d, esi; Size
0x14015f0fc  xor     edx, edx; Val
0x14015f0fe  call    memset
0x14015f103  mov     ecx, [rbx+4]
0x14015f106  cmp     ecx, 2
0x14015f109  jnz     loc_14015F2EB
0x14015f10f  movzx   eax, word ptr [rbx+28h]
0x14015f113  mov     r8d, edi
0x14015f116  sub     r8d, eax; Size
0x14015f119  xor     edx, edx; Val
0x14015f11b  mov     rcx, r14; void *
0x14015f11e  mov     dword ptr [rbp+0B0h+var_140.DATA+10h], r8d
0x14015f122  call    memset
0x14015f127  mov     r12d, dword ptr [rbp+0B0h+var_140.DATA]
0x14015f12b  mov     eax, [rbx+14h]
0x14015f12e  mov     [rsp+1B0h+var_140.Timeout], eax
0x14015f132  lea     rax, WPP_RECORDER_INITIALIZED
0x14015f139  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14015f140  jnz     loc_14015F429
0x14015f146  mov     rcx, [r15+8]; struct _NDIS_MINIPORT_BLOCK *
0x14015f14a  lea     r8, [rsp+1B0h+var_140]; struct _NDIS_OID_REQUEST *
0x14015f14f  xor     r9d, r9d; unsigned __int8
0x14015f152  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], r13; struct _NDIS_FILTER_BLOCK *
0x14015f157  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x14015f159  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x14015f15e  mov     ecx, [rsp+1B0h+var_140.RequestType]
0x14015f162  mov     [rbx+24h], eax
0x14015f165  cmp     ecx, 2
0x14015f168  jnz     loc_14015F46B
0x14015f16e  mov     eax, dword ptr [rbp+0B0h+var_140.DATA+14h]
0x14015f171  mov     [rbx+18h], eax
0x14015f174  mov     eax, dword ptr [rbp+0B0h+var_140.DATA+18h]
0x14015f177  mov     [rbx+20h], eax
0x14015f17a  mov     r8, [rsp+1B0h+var_158]
0x14015f17f  xor     edx, edx; int
0x14015f181  mov     [r8], edi
0x14015f184  xor     r8d, r8d; unsigned __int8
0x14015f187  xor     ecx, ecx; int
0x14015f189  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x14015f18e  mov     edi, eax
0x14015f190  jmp     loc_14015F2C1
0x14015f195  lea     eax, [r13-170002h]; switch 61 cases
0x14015f19c  cmp     eax, 3Ch
0x14015f19f  ja      def_14015F1C4; jumptable 000000014015F1C4 default case, cases 1507331-1507333,1507335-1507341,1507343-1507367,1507369-1507371,1507373-1507375,1507377-1507389
0x14015f1a5  lea     rdx, cs:140000000h
0x14015f1ac  mov     r14, r10
0x14015f1af  movzx   eax, ds:(byte_1400FF6B4 - 140000000h)[rdx+rax]
0x14015f1b7  mov     edi, r10d
0x14015f1ba  mov     ecx, ds:(jpt_14015F1C4 - 140000000h)[rdx+rax*4]
0x14015f1c1  add     rcx, rdx
0x14015f1c4  jmp     rcx; switch jump
0x14015f1ca  mov     byte ptr [rsp+1B0h+var_160], 1; jumptable 000000014015F1C4 case 1507390
0x14015f1cf  cmp     esi, 4; jumptable 000000014015F1C4 case 1507342
0x14015f1d2  jb      loc_14015F305
0x14015f1d8  test    bl, 3
0x14015f1db  setz    cl
0x14015f1de  test    sil, 3
0x14015f1e2  setz    al
0x14015f1e5  test    al, cl
0x14015f1e7  jz      loc_14015F305
0x14015f1ed  shr     esi, 2
0x14015f1f0  mov     r8d, 6D61444Eh
0x14015f1f6  mov     r13d, esi
0x14015f1f9  mov     ecx, 42h ; 'B'
0x14015f1fe  shl     rsi, 2
0x14015f202  mov     rdx, rsi
0x14015f205  call    cs:__imp_ExAllocatePool2
0x14015f20c  nop     dword ptr [rax+rax+00h]
0x14015f211  mov     r14, rax
0x14015f214  test    rax, rax
0x14015f217  jz      loc_14015F2C1
0x14015f21d  mov     r8, rsi; Size
0x14015f220  mov     rdx, rbx; Src
0x14015f223  mov     rcx, rax; void *
0x14015f226  call    memmove
0x14015f22b  mov     rsi, r14
0x14015f22e  mov     edx, r13d
0x14015f231  mov     rcx, rsi
0x14015f234  call    ndisIsOidAllowedFromUsermode_0
0x14015f239  test    al, al
0x14015f23b  jz      loc_14015F538
0x14015f241  test    r12, r12
0x14015f244  jz      short loc_14015F2AB
0x14015f246  mov     ebx, [r12+28h]
0x14015f24b  test    ebx, ebx
0x14015f24d  jz      short loc_14015F2AB
0x14015f24f  test    byte ptr [r12+0Ah], 5
0x14015f255  jz      loc_14015F4A4
0x14015f25b  mov     rax, [r12+18h]
0x14015f260  test    rax, rax
0x14015f263  jz      short loc_14015F2AB
0x14015f265  mov     r8, [rsp+1B0h+var_158]
0x14015f26a  lea     rcx, [rsp+1B0h+var_160]
0x14015f26f  mov     [rsp+1B0h+var_170], rcx; __int64
0x14015f274  mov     r9d, r13d
0x14015f277  mov     rcx, qword ptr [rsp+1B0h+var_150]; char
0x14015f27c  mov     rdx, r15
0x14015f27f  mov     [rsp+1B0h+var_178], dil; char
0x14015f284  mov     qword ptr [rsp+1B0h+var_180], r8; __int64
0x14015f289  mov     r8, rsi
0x14015f28c  mov     [rsp+1B0h+Priority], ebx; Size
0x14015f290  mov     qword ptr [rsp+1B0h+BugCheckOnFailure], rax; void *
0x14015f295  call    ndisQueryStatisticsOids
0x14015f29a  movzx   r8d, byte ptr [rsp+1B0h+var_160]; unsigned __int8
0x14015f2a0  mov     edx, eax; int
0x14015f2a2  xor     ecx, ecx; int
0x14015f2a4  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x14015f2a9  mov     edi, eax
0x14015f2ab  test    r14, r14
0x14015f2ae  jz      short loc_14015F2C1
0x14015f2b0  xor     edx, edx; Tag
0x14015f2b2  mov     rcx, r14; P
0x14015f2b5  call    cs:__imp_ExFreePoolWithTag
0x14015f2bc  nop     dword ptr [rax+rax+00h]
0x14015f2c1  mov     eax, edi
0x14015f2c3  mov     rcx, [rbp+0B0h+var_40]
0x14015f2c7  xor     rcx, rsp; StackCookie
0x14015f2ca  call    __security_check_cookie
0x14015f2cf  mov     rbx, [rsp+1B0h+arg_10]
0x14015f2d7  add     rsp, 180h
0x14015f2de  pop     r15
0x14015f2e0  pop     r14
0x14015f2e2  pop     r13
0x14015f2e4  pop     r12
0x14015f2e6  pop     rdi
0x14015f2e7  pop     rsi
0x14015f2e8  pop     rbp
0x14015f2e9  retn
0x14015f2eb  test    ecx, ecx
0x14015f2ed  jz      loc_14015F10F
0x14015f2f3  sub     ecx, 1
0x14015f2f6  jz      loc_14015F585
0x14015f2fc  cmp     ecx, 0Bh
0x14015f2ff  jz      loc_14015F56A
0x14015f305  mov     edi, 0C000000Dh
0x14015f30a  jmp     short loc_14015F2C1
0x14015f30c  test    dword ptr [rbx+4], 0FFFFFFFDh
0x14015f313  jz      loc_14015F08C
0x14015f319  mov     edi, 0C0000022h
0x14015f31e  jmp     short loc_14015F2C1
0x14015f320  cmp     esi, 4; jumptable 000000014015F1C4 case 1507330
0x14015f323  jb      short loc_14015F305
0x14015f325  mov     r13d, [rbx]
0x14015f328  mov     ecx, r13d
0x14015f32b  call    ndisIsOidAllowedFromUsermode
0x14015f330  test    al, al
0x14015f332  jz      short loc_14015F319
0x14015f334  mov     edx, r13d
0x14015f337  mov     rcx, r15
0x14015f33a  call    ndisValidOid
0x14015f33f  test    al, al
0x14015f341  jz      short loc_14015F305
0x14015f343  test    r12, r12
0x14015f346  jz      loc_14015F499
0x14015f34c  mov     r14d, [r12+28h]
0x14015f351  test    r14d, r14d
0x14015f354  jz      loc_14015F499
0x14015f35a  test    byte ptr [r12+0Ah], 5
0x14015f360  jz      loc_14015F4CF
0x14015f366  mov     rsi, [r12+18h]
0x14015f36b  test    rsi, rsi
0x14015f36e  jz      loc_14015F2C1
0x14015f374  mov     r8d, 6D61444Eh
0x14015f37a  mov     rdx, r14
0x14015f37d  mov     ecx, 40h ; '@'
0x14015f382  call    cs:__imp_ExAllocatePool2
0x14015f389  nop     dword ptr [rax+rax+00h]
0x14015f38e  mov     rbx, rax
0x14015f391  test    rax, rax
0x14015f394  jz      loc_14015F4FE
0x14015f39a  mov     r8, r14; Size
0x14015f39d  mov     rdx, rsi; Src
0x14015f3a0  mov     rcx, rax; void *
0x14015f3a3  call    memmove
0x14015f3a8  mov     r9, rbx; void *
0x14015f3ab  mov     [rsp+1B0h+BugCheckOnFailure], r14d; unsigned int
0x14015f3b0  mov     r8d, r13d; unsigned int
0x14015f3b3  lea     rdx, [rsp+1B0h+var_140]; struct _NDIS_OID_REQUEST *
0x14015f3b8  mov     rcx, r15; struct _NDIS_USER_OPEN_CONTEXT *
0x14015f3bb  call    ?ndisQueryDeviceOid@@YAHPEAU_NDIS_USER_OPEN_CONTEXT@@PEAU_NDIS_OID_REQUEST@@KPEAXI@Z; ndisQueryDeviceOid(_NDIS_USER_OPEN_CONTEXT *,_NDIS_OID_REQUEST *,ulong,void *,uint)
0x14015f3c0  mov     r9d, dword ptr [rbp+0B0h+var_140.DATA+14h]
0x14015f3c4  xor     ecx, ecx; int
0x14015f3c6  mov     r8, [rsp+1B0h+var_158]
0x14015f3cb  mov     edx, eax; int
0x14015f3cd  mov     [r8], r9d
0x14015f3d0  cmp     r9d, r14d
0x14015f3d3  ja      loc_14015F508
0x14015f3d9  xor     r8d, r8d; unsigned __int8
0x14015f3dc  call    ?ndisConvertNdisStatusToNtStatusForIoctl@@YAJJHE@Z; ndisConvertNdisStatusToNtStatusForIoctl(long,int,uchar)
0x14015f3e1  mov     edi, eax
0x14015f3e3  test    edx, edx
0x14015f3e5  jnz     short loc_14015F41E
0x14015f3e7  test    r9d, r9d
0x14015f3ea  jz      short loc_14015F41E
0x14015f3ec  test    rsi, rsi
0x14015f3ef  jz      short loc_14015F41E
0x14015f3f1  test    rbx, rbx
0x14015f3f4  jz      loc_14015F2C1
0x14015f3fa  mov     r8d, r9d; Size
0x14015f3fd  mov     rdx, rbx; Src
0x14015f400  mov     rcx, rsi; void *
0x14015f403  call    memmove
0x14015f408  xor     edx, edx; Tag
0x14015f40a  mov     rcx, rbx; P
0x14015f40d  call    cs:__imp_ExFreePoolWithTag
0x14015f414  nop     dword ptr [rax+rax+00h]
0x14015f419  jmp     loc_14015F2C1
0x14015f41e  test    rbx, rbx
0x14015f421  jz      loc_14015F2C1
0x14015f427  jmp     short loc_14015F408
0x14015f429  mov     rax, qword ptr [rsp+1B0h+var_150]
  ... truncated ...
```
