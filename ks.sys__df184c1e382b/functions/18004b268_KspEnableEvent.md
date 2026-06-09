# KspEnableEvent

- ea: `0x18004b268`
- end: `0x18004bbcc`
- name: `KspEnableEvent`
- size: `2404`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, unsigned int, __int64, __int64 (__fastcall *)(__int64, _QWORD, _QWORD), size_t Size, __int64, unsigned int, char)`
- caller_count: `5`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800339a0`
- `0x180036f10`
- `0x1800375d0`
- `0x180049c20`
- `0x18004b220`

## callees

- `0x180008114`
- `0x180008640`
- `0x180010154`
- `0x180010804`
- `0x180019c00`
- `0x180019cb0`
- `0x180019d00`
- `0x18001a000`
- `0x1800337b8`
- `0x18004b268`
- `0x18005a85c`
- `0x18005d5b0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x18004b2ee`
- `ntoskrnl!ProbeForRead` at `0x18004b555`
- `ntoskrnl!ProbeForRead` at `0x18004b2ee`
- `ntoskrnl!ProbeForRead` at `0x18004b555`
- `ntoskrnl!ProbeForWrite` at `0x18004b423`
- `ntoskrnl!ProbeForWrite` at `0x18004b423`
- `ntoskrnl!ExAllocatePool2` at `0x18004b35a`
- `ntoskrnl!ExAllocatePool2` at `0x18004b35a`
- `ntoskrnl!ExSemaphoreObjectType` at `0x18004b9a0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b9b1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004ba0a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b9b1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004ba0a`
- `ntoskrnl!ExEventObjectType` at `0x18004b9f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b4fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b596`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b4fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b596`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004b7ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004b7ba`

## pseudocode

```c
__int64 __fastcall KspEnableEvent(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 (__fastcall *a7)(__int64, _QWORD, _QWORD),
        size_t Size,
        __int64 a9,
        unsigned int a10,
        char a11)
{
  __int64 v11; // r11
  __int64 v14; // r15
  size_t v15; // r13
  size_t v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned int v19; // r12d
  __int64 v20; // rax
  int ULongFromUser; // r15d
  __int64 result; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  void *v24; // rcx
  void *v25; // rdx
  __int64 v26; // r12
  unsigned int v27; // r15d
  __int64 v28; // rcx
  PVOID v29; // rcx
  int v30; // eax
  char v31; // r9
  void *v32; // rdx
  void *v33; // rcx
  __int64 v34; // r15
  __int64 v35; // rbx
  int v36; // r12d
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int v39; // r13d
  unsigned int v40; // ecx
  __int64 EventItem; // rax
  __int64 v42; // r11
  __int64 (__fastcall *v43)(__int64, __int64, __int64); // rax
  unsigned int v44; // edx
  __int64 v45; // rax
  __int64 v46; // rdx
  unsigned int v47; // eax
  unsigned int v48; // ecx
  SIZE_T v49; // rdx
  unsigned int v50; // edi
  char *PoolWithTag; // rax
  char *v52; // r14
  _QWORD *v53; // rdi
  PVOID *Object; // r8
  int v55; // r10d
  int v56; // eax
  char *v57; // rdi
  NTSTATUS Dpc; // ebx
  int v59; // ecx
  bool v60; // zf
  int v61; // ecx
  int v62; // eax
  KDPC_IMPORTANCE v63; // r8d
  KDEFERRED_ROUTINE *v64; // rdx
  int v65; // ecx
  unsigned __int64 v66; // rcx
  _OWORD **i; // r11
  unsigned int v68; // [rsp+30h] [rbp-88h]
  _QWORD v69[2]; // [rsp+38h] [rbp-80h] BYREF
  __int128 v70; // [rsp+48h] [rbp-70h] BYREF
  __int128 v71; // [rsp+58h] [rbp-60h]
  PVOID P[2]; // [rsp+68h] [rbp-50h]
  _QWORD *Src; // [rsp+C0h] [rbp+8h]
  __int64 v74; // [rsp+D0h] [rbp+18h]

  v74 = a3;
  v11 = a3;
  v14 = *(_QWORD *)(a1 + 184);
  v69[0] = v14;
  v15 = *(unsigned int *)(v14 + 16);
  v68 = *(_DWORD *)(v14 + 16);
  v16 = *(unsigned int *)(v14 + 8);
  v17 = ((_DWORD)v16 + 7) & 0xFFFFFFF8;
  v18 = *(_QWORD *)(a1 + 24);
  if ( !v18 )
  {
    if ( (unsigned int)v15 < 0x18 )
      return 3221225990LL;
    if ( (unsigned int)v17 < (unsigned int)v16 )
      return 3221225990LL;
    v19 = v17 + v15;
    if ( (int)v17 + (int)v15 < (unsigned int)v17 )
      return 3221225990LL;
    if ( *(_BYTE *)(a1 + 64) )
      ProbeForRead(*(volatile void **)(v14 + 32), (unsigned int)v15, 1u);
    v60 = (unsigned int)Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline() == 0;
    v20 = *(_QWORD *)(v14 + 32);
    if ( v60 || !*(_BYTE *)(a1 + 64) )
      ULongFromUser = *(_DWORD *)(v20 + 20);
    else
      ULongFromUser = RtlReadULongFromUser(v20 + 20);
    if ( !a7 || (ULongFromUser & 0xFFF00) != 0 )
    {
      *(_QWORD *)(a1 + 24) = ExAllocatePool2(99, v19, 1886409547);
      *(_DWORD *)(a1 + 16) |= 0x30u;
    }
    else
    {
      result = a7(a1, v19, 0);
      if ( (int)result < 0 )
        return result;
    }
    memset(*(void **)(a1 + 24), 0, ((_DWORD)v16 + 7) & 0xFFFFFFF8);
    IsEnabledDeviceUsageNoInline = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
    v24 = (void *)(v17 + *(_QWORD *)(a1 + 24));
    if ( IsEnabledDeviceUsageNoInline )
    {
      v25 = *(void **)(v69[0] + 32LL);
      if ( *(_BYTE *)(a1 + 64) )
        RtlCopyFromUser(v24, v25, v15);
      else
        RtlCopyVolatileMemory(v24, v25, v15);
      v26 = v69[0];
    }
    else
    {
      v26 = v69[0];
      memmove(v24, *(const void **)(v69[0] + 32LL), v15);
    }
    *(_DWORD *)(v17 + *(_QWORD *)(a1 + 24) + 20) = ULongFromUser;
    v27 = ULongFromUser & 0xEFFFFFFF;
    if ( v27 == 1 || v27 == 2 || v27 == 4 )
    {
      if ( (_DWORD)v16 )
      {
        v30 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
        v31 = *(_BYTE *)(a1 + 64);
        if ( v30 )
        {
          v32 = *(void **)(a1 + 112);
          v33 = *(void **)(a1 + 24);
          if ( v31 )
            RtlCopyFromUser(v33, v32, v16);
          else
            RtlCopyVolatileMemory(v33, v32, v16);
        }
        else
        {
          if ( v31 )
            ProbeForRead(*(volatile void **)(a1 + 112), v16, 1u);
          memmove(*(void **)(a1 + 24), *(const void **)(a1 + 112), v16);
        }
      }
    }
    else
    {
      if ( v27 != 256 && v27 != 512 && v27 != 1024 )
        return 3221225485LL;
      if ( (_DWORD)v16 )
      {
        if ( *(_BYTE *)(a1 + 64) )
          ProbeForWrite(*(volatile void **)(a1 + 112), v16, 1u);
        *(_DWORD *)(a1 + 16) |= 0x40u;
      }
      if ( v27 == 1024 )
      {
        v70 = 0;
        v71 = 0;
        *(_OWORD *)P = 0;
        if ( v68 < 0x28 )
          return 3221225990LL;
        v28 = *(_QWORD *)(a1 + 24);
        if ( *(_QWORD *)(v17 + v28 + 32) )
          return 3221225485LL;
        *(_QWORD *)&v70 = a4;
        *((_QWORD *)&v70 + 1) = *(_QWORD *)(v26 + 48);
        *(_QWORD *)&v71 = a1;
        *((_QWORD *)&v71 + 1) = *(_QWORD *)(v17 + v28 + 24);
        P[1] = (PVOID)(unsigned int)v16;
        PerformLockedOperation(a5, a6, QueryBufferSynchronize, &v70);
        result = HIDWORD(P[1]);
        if ( SHIDWORD(P[1]) >= 0 )
        {
          memmove(*(void **)(a1 + 24), (char *)P[0] + 24, *((unsigned int *)P[0] + 5));
          v29 = P[0];
          *(_QWORD *)(a1 + 56) = *((unsigned int *)P[0] + 5);
          ExFreePoolWithTag(v29, 0);
          return HIDWORD(P[1]);
        }
        return result;
      }
    }
    v18 = *(_QWORD *)(a1 + 24);
    v11 = v74;
  }
  v34 = v18 & -(__int64)((_DWORD)v16 != 0);
  v35 = v18 + v17;
  v36 = *(_DWORD *)(v35 + 20);
  if ( (v36 & 0x10000000) != 0 )
  {
    if ( (unsigned int)v15 < 0x20 )
      return 3221225990LL;
    if ( a9 )
    {
      v37 = *(unsigned int *)(v35 + 24);
      if ( (unsigned int)v37 >= a10 )
        return 3221225488LL;
      v38 = *(_QWORD *)(a9 + 8 * v37);
      if ( !v38 )
        return 3221226021LL;
      a2 = *(_DWORD *)(v38 + 32);
      if ( !a2 )
        return 3221226021LL;
      v11 = *(_QWORD *)(v38 + 40);
      v74 = v11;
      LODWORD(Size) = *(_DWORD *)(v38 + 36);
    }
    v36 &= ~0x10000000u;
  }
  v39 = 40;
  if ( (_DWORD)Size )
    v39 = Size;
  if ( !a2 )
  {
LABEL_67:
    if ( *(_QWORD *)v35 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)(v35 + 8) != *(_QWORD *)GUID_NULL.Data4 )
      return 3221226032LL;
    if ( *(_DWORD *)(v35 + 16) || v36 != 256 )
      return 3221225485LL;
    if ( !(_DWORD)v16 )
    {
      *(_QWORD *)(a1 + 56) = 16LL * a2;
      return 2147483653LL;
    }
    if ( (_DWORD)v16 == 4 )
    {
      **(_DWORD **)(a1 + 24) = 16 * a2;
      *(_QWORD *)(a1 + 56) = 4;
      return 0;
    }
    v66 = 16LL * a2;
    if ( v16 >= v66 )
    {
      *(_QWORD *)(a1 + 56) = v66;
      for ( i = (_OWORD **)(-24LL * a2 + v11); a2; --a2 )
      {
        *(_OWORD *)v34 = **i;
        v34 += 16;
        i += 3;
      }
      return 0;
    }
    return 3221225507LL;
  }
  v40 = a2;
  while ( *(_QWORD *)v35 != **(_QWORD **)v11 || *(_QWORD *)(v35 + 8) != *(_QWORD *)(*(_QWORD *)v11 + 8LL) )
  {
    v11 += 24;
    v74 = v11;
    if ( !--v40 )
      goto LABEL_67;
  }
  if ( (v36 & 0xFFF00) != 0 )
  {
    if ( v36 != 512 )
      return 0;
    EventItem = FindEventItem(v11, v39, *(unsigned int *)(v35 + 16));
    if ( EventItem )
    {
      *(_QWORD *)(a1 + 120) = v42;
      if ( (_DWORD)Size )
        *(_QWORD *)(a1 + 144) = EventItem;
      v43 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(EventItem + 32);
      if ( v43 )
      {
        v44 = v43(a1, v35, v34);
        if ( v44 != 263 )
        {
          result = 0;
          if ( v44 != -1073741802 )
            return v44;
          return result;
        }
      }
      return 0;
    }
    return 3221226021LL;
  }
  v45 = FindEventItem(v11, v39, *(unsigned int *)(v35 + 16));
  v46 = v45;
  Src = (_QWORD *)v45;
  if ( !v45 )
    return 3221226021LL;
  if ( (unsigned int)v16 < *(_DWORD *)(v45 + 4) )
    return 3221225507LL;
  v47 = 0;
  if ( a11 )
  {
    if ( v39 >= 0xFFFFFFE8 )
      return 3221225621LL;
    v47 = v39 + 31;
    if ( v39 + 31 < v39 + 24 )
      return 3221225621LL;
  }
  v48 = v47 + 120;
  if ( v47 + 120 < v47 )
    return 3221225621LL;
  v49 = v48 + *(_DWORD *)(v46 + 8);
  if ( (unsigned int)v49 < v48 )
    return 3221225621LL;
  v50 = v49;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v49, 0x6565534Bu);
  v52 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return 3221225626LL;
    memset(PoolWithTag, 0, v50);
  }
  if ( !v52 )
    return 3221225626LL;
  v53 = Src;
  *(_QWORD *)v52 = Src[3];
  *(_OWORD *)(v52 + 8) = *(_OWORD *)v35;
  *((_QWORD *)v52 + 3) = *(_QWORD *)(v35 + 16);
  Object = (PVOID *)(v52 + 48);
  *((_QWORD *)v52 + 6) = 0;
  *((_QWORD *)v52 + 7) = 0;
  *((_QWORD *)v52 + 8) = *(_QWORD *)(a1 + 112);
  *((_DWORD *)v52 + 18) = *(_DWORD *)v34;
  *((_QWORD *)v52 + 10) = v74;
  *((_QWORD *)v52 + 11) = Src;
  *((_QWORD *)v52 + 12) = *(_QWORD *)(v69[0] + 48LL);
  *((_DWORD *)v52 + 27) = 0;
  v55 = 2;
  if ( v36 == 2 )
  {
    *((_DWORD *)v52 + 28) = 2;
  }
  else
  {
    v56 = 0;
    if ( v36 == 4 )
      v56 = 4;
    *((_DWORD *)v52 + 28) = v56;
  }
  if ( a11 )
  {
    v57 = &v52[(*((unsigned int *)Src + 2) + 127LL) & 0xFFFFFFFFFFFFFFF8uLL];
    *(_OWORD *)v57 = *(_OWORD *)v74;
    *((_QWORD *)v57 + 2) = *(_QWORD *)(v74 + 16);
    memmove(v57 + 24, Src, v39);
    *((_QWORD *)v52 + 10) = v57;
    *((_QWORD *)v52 + 11) = v57 + 24;
    v55 = 2;
    v53 = Src;
    Object = (PVOID *)(v52 + 48);
  }
  if ( *((_DWORD *)v52 + 18) == 1 )
  {
    if ( !*(_QWORD *)(v34 + 16) && !*(_QWORD *)(v34 + 24) )
    {
      Dpc = ObReferenceObjectByHandle(
              *(HANDLE *)(v34 + 8),
              2u,
              (POBJECT_TYPE)ExEventObjectType,
              *(_BYTE *)(a1 + 64),
              Object,
              0);
      goto LABEL_110;
    }
  }
  else
  {
    if ( *((_DWORD *)v52 + 18) == 2 )
    {
      if ( !*(_DWORD *)(v34 + 16) )
      {
        Dpc = ObReferenceObjectByHandle(
                *(HANDLE *)(v34 + 8),
                2u,
                (POBJECT_TYPE)ExSemaphoreObjectType,
                *(_BYTE *)(a1 + 64),
                Object,
                0);
        if ( Dpc >= 0 )
          *((_DWORD *)v52 + 26) = *(_DWORD *)(v34 + 20);
        goto LABEL_110;
      }
      goto LABEL_109;
    }
    if ( *((_DWORD *)v52 + 18) != 4 )
    {
      if ( *((_DWORD *)v52 + 18) == 8 )
      {
        v60 = *(_BYTE *)(a1 + 64) == 0;
        goto LABEL_122;
      }
      if ( *((_DWORD *)v52 + 18) != 16 && *((_DWORD *)v52 + 18) != 32 && *((_DWORD *)v52 + 18) != 128 )
        goto LABEL_109;
    }
    if ( !*(_BYTE *)(a1 + 64) )
    {
      v60 = *(_QWORD *)(v34 + 24) == 0;
LABEL_122:
      if ( v60 )
      {
        Dpc = 0;
        goto LABEL_112;
      }
    }
  }
LABEL_109:
  Dpc = -1073741811;
LABEL_110:
  if ( Dpc < 0 )
    goto LABEL_150;
  v55 = 2;
LABEL_112:
  switch ( *((_DWORD *)v52 + 18) )
  {
    case 1:
    case 2:
      v63 = LowImportance;
LABEL_148:
      v64 = EventDpc;
      goto LABEL_149;
    case 4:
    case 8:
      v65 = *(_DWORD *)(v34 + 16);
      if ( v65 )
      {
        if ( v65 == 1 )
          v55 = 1;
      }
      else
      {
        v55 = 0;
      }
      v63 = v55;
      goto LABEL_148;
    case 0x10:
      if ( (*((_DWORD *)v52 + 28) & 2) == 0 )
        break;
      v63 = MediumImportance;
      v64 = (KDEFERRED_ROUTINE *)OneShotDpc;
      goto LABEL_149;
    case 0x20:
    case 0x80:
      if ( *((_DWORD *)v52 + 18) == 32 )
        v59 = *(_DWORD *)(v34 + 16);
      else
        v59 = *(_DWORD *)(*(_QWORD *)(v34 + 16) + 80LL);
      if ( v59 )
      {
        v61 = v59 - 1;
        if ( !v61 )
        {
          v62 = 0;
          goto LABEL_139;
        }
        if ( v61 == 1 )
        {
          v62 = 2;
LABEL_139:
          v63 = v62;
          v64 = WorkerDpc;
LABEL_149:
          Dpc = CreateDpc(v52 + 32, v64, v63);
          break;
        }
      }
      v62 = 1;
      goto LABEL_139;
  }
LABEL_150:
  if ( Dpc < 0 )
    goto LABEL_159;
  if ( (*((_DWORD *)v52 + 28) & 4) != 0 && !*((_QWORD *)v52 + 7) )
    Dpc = CreateDpc(v52 + 32, WorkerDpc, LowImportance);
  if ( Dpc < 0 )
    goto LABEL_159;
  if ( !v53[2] )
  {
    v69[0] = a4;
    v69[1] = v52 + 32;
    PerformLockedOperation(a5, a6, AddEventSynchronize, v69);
    return 0;
  }
  *(_QWORD *)(a1 + 120) = v52 + 32;
  if ( (_DWORD)Size )
    *(_QWORD *)(a1 + 144) = v53;
  result = ((__int64 (__fastcall *)(__int64, __int64, char *))v53[2])(a1, v34, v52 + 32);
  Dpc = result;
  if ( (int)result < 0 )
  {
LABEL_159:
    KsDiscardEvent((PKSEVENT_ENTRY)(v52 + 32));
    return (unsigned int)Dpc;
  }
  return result;
}

```

## disassembly

```asm
0x18004b268  mov     [rsp+arg_18], r9
0x18004b26d  mov     [rsp+arg_10], r8
0x18004b272  mov     [rsp+Src], rcx
0x18004b277  push    rbx
0x18004b278  push    rsi
0x18004b279  push    rdi
0x18004b27a  push    r12
0x18004b27c  push    r13
0x18004b27e  push    r14
0x18004b280  push    r15
0x18004b282  sub     rsp, 80h
0x18004b289  mov     r11, r8
0x18004b28c  mov     edi, edx
0x18004b28e  mov     rsi, rcx
0x18004b291  mov     r15, [rcx+0B8h]
0x18004b298  mov     [rsp+0B8h+var_80], r15
0x18004b29d  mov     r13d, [r15+10h]
0x18004b2a1  mov     [rsp+0B8h+var_88], r13d
0x18004b2a6  mov     r14d, [r15+8]
0x18004b2aa  lea     ebx, [r14+7]
0x18004b2ae  and     ebx, 0FFFFFFF8h
0x18004b2b1  mov     rcx, [rcx+18h]
0x18004b2b5  test    rcx, rcx
0x18004b2b8  jnz     loc_18004B5B5
0x18004b2be  cmp     r13d, 18h
0x18004b2c2  jb      loc_18004B5D4
0x18004b2c8  cmp     ebx, r14d
0x18004b2cb  jb      loc_18004B5D4
0x18004b2d1  lea     r12d, [rbx+r13]
0x18004b2d5  cmp     r12d, ebx
0x18004b2d8  jb      loc_18004B5D4
0x18004b2de  cmp     [rsi+40h], cl
0x18004b2e1  jz      short loc_18004B2FA
0x18004b2e3  mov     edx, r13d; Length
0x18004b2e6  lea     r8d, [rcx+1]; Alignment
0x18004b2ea  mov     rcx, [r15+20h]; Address
0x18004b2ee  call    cs:__imp_ProbeForRead
0x18004b2f5  nop     dword ptr [rax+rax+00h]
0x18004b2fa  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004b2ff  test    eax, eax
0x18004b301  mov     rax, [r15+20h]
0x18004b305  jz      short loc_18004B31B
0x18004b307  cmp     byte ptr [rsi+40h], 0
0x18004b30b  jz      short loc_18004B31B
0x18004b30d  lea     rcx, [rax+14h]
0x18004b311  call    RtlReadULongFromUser
0x18004b316  mov     r15d, eax
0x18004b319  jmp     short loc_18004B31F
0x18004b31b  mov     r15d, [rax+14h]
0x18004b31f  mov     rax, [rsp+0B8h+arg_30]
0x18004b327  test    rax, rax
0x18004b32a  jz      short loc_18004B34C
0x18004b32c  test    r15d, 0FFF00h
0x18004b333  jnz     short loc_18004B34C
0x18004b335  xor     r8d, r8d
0x18004b338  mov     edx, r12d
0x18004b33b  mov     rcx, rsi
0x18004b33e  call    _guard_dispatch_icall
0x18004b343  test    eax, eax
0x18004b345  jns     short loc_18004B36E
0x18004b347  jmp     loc_18004BBB8
0x18004b34c  mov     edx, r12d
0x18004b34f  mov     ecx, 63h ; 'c'
0x18004b354  mov     r8d, 7070534Bh
0x18004b35a  call    cs:__imp_ExAllocatePool2
0x18004b361  nop     dword ptr [rax+rax+00h]
0x18004b366  mov     [rsi+18h], rax
0x18004b36a  or      dword ptr [rsi+10h], 30h
0x18004b36e  mov     r8, rbx; Size
0x18004b371  xor     edx, edx; Val
0x18004b373  mov     rcx, [rsi+18h]; void *
0x18004b377  call    memset
0x18004b37c  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004b381  mov     rcx, [rsi+18h]
0x18004b385  add     rcx, rbx; void *
0x18004b388  mov     r8, r13; Size
0x18004b38b  test    eax, eax
0x18004b38d  jz      short loc_18004B3B1
0x18004b38f  mov     rax, [rsp+0B8h+var_80]
0x18004b394  mov     rdx, [rax+20h]; Src
0x18004b398  cmp     byte ptr [rsi+40h], 0
0x18004b39c  jz      short loc_18004B3A5
0x18004b39e  call    RtlCopyFromUser
0x18004b3a3  jmp     short loc_18004B3AA
0x18004b3a5  call    RtlCopyVolatileMemory
0x18004b3aa  mov     r12, [rsp+0B8h+var_80]
0x18004b3af  jmp     short loc_18004B3C0
0x18004b3b1  mov     r12, [rsp+0B8h+var_80]
0x18004b3b6  mov     rdx, [r12+20h]; Src
0x18004b3bb  call    memmove
0x18004b3c0  mov     rax, [rsi+18h]
0x18004b3c4  mov     [rbx+rax+14h], r15d
0x18004b3c9  btr     r15d, 1Ch
0x18004b3ce  mov     eax, r15d
0x18004b3d1  sub     eax, 1
0x18004b3d4  jz      loc_18004B513
0x18004b3da  sub     eax, 1
0x18004b3dd  jz      loc_18004B513
0x18004b3e3  sub     eax, 2
0x18004b3e6  jz      loc_18004B513
0x18004b3ec  sub     eax, 0FCh
0x18004b3f1  jz      short loc_18004B40B
0x18004b3f3  sub     eax, 100h
0x18004b3f8  jz      short loc_18004B40B
0x18004b3fa  cmp     eax, 200h
0x18004b3ff  jz      short loc_18004B40B
0x18004b401  mov     eax, 0C000000Dh
0x18004b406  jmp     loc_18004BBB8
0x18004b40b  test    r14d, r14d
0x18004b40e  jz      short loc_18004B433
0x18004b410  cmp     byte ptr [rsi+40h], 0
0x18004b414  jz      short loc_18004B42F
0x18004b416  mov     rdx, r14; Length
0x18004b419  mov     r8d, 1; Alignment
0x18004b41f  mov     rcx, [rsi+70h]; Address
0x18004b423  call    cs:__imp_ProbeForWrite
0x18004b42a  nop     dword ptr [rax+rax+00h]
0x18004b42f  or      dword ptr [rsi+10h], 40h
0x18004b433  cmp     r15d, 400h
0x18004b43a  jnz     loc_18004B571
0x18004b440  xorps   xmm0, xmm0
0x18004b443  movups  [rsp+0B8h+var_70], xmm0
0x18004b448  movups  [rsp+0B8h+var_60], xmm0
0x18004b44d  movups  xmmword ptr [rsp+0B8h+P], xmm0
0x18004b452  mov     r13d, 28h ; '('
0x18004b458  cmp     [rsp+0B8h+var_88], r13d
0x18004b45d  jnb     short loc_18004B469
0x18004b45f  mov     eax, 0C0000206h
0x18004b464  jmp     loc_18004BBB8
0x18004b469  mov     rcx, [rsi+18h]
0x18004b46d  cmp     qword ptr [rbx+rcx+20h], 0
0x18004b473  jz      short loc_18004B47F
0x18004b475  mov     eax, 0C000000Dh
0x18004b47a  jmp     loc_18004BBB8
0x18004b47f  mov     rax, [rsp+0B8h+arg_18]
0x18004b487  mov     qword ptr [rsp+0B8h+var_70], rax
0x18004b48c  mov     rax, [r12+30h]
0x18004b491  mov     qword ptr [rsp+0B8h+var_70+8], rax
0x18004b496  mov     qword ptr [rsp+0B8h+var_60], rsi
0x18004b49b  mov     rax, [rbx+rcx+18h]
0x18004b4a0  mov     qword ptr [rsp+0B8h+var_60+8], rax
0x18004b4a5  mov     dword ptr [rsp+0B8h+P+8], r14d
0x18004b4aa  mov     dword ptr [rsp+0B8h+P+0Ch], 0
0x18004b4b2  lea     r9, [rsp+0B8h+var_70]
0x18004b4b7  lea     r8, QueryBufferSynchronize
0x18004b4be  mov     rdx, [rsp+0B8h+arg_28]
0x18004b4c6  mov     ecx, [rsp+0B8h+arg_20]
0x18004b4cd  call    PerformLockedOperation
0x18004b4d2  mov     eax, dword ptr [rsp+0B8h+P+0Ch]
0x18004b4d6  test    eax, eax
0x18004b4d8  js      short loc_18004B50E
0x18004b4da  mov     rdx, [rsp+0B8h+P]
0x18004b4df  mov     r8d, [rdx+14h]; Size
0x18004b4e3  add     rdx, 18h; Src
0x18004b4e7  mov     rcx, [rsi+18h]; void *
0x18004b4eb  call    memmove
0x18004b4f0  mov     rcx, [rsp+0B8h+P]; P
0x18004b4f5  mov     eax, [rcx+14h]
0x18004b4f8  mov     [rsi+38h], rax
0x18004b4fc  xor     edx, edx; Tag
0x18004b4fe  call    cs:__imp_ExFreePoolWithTag
0x18004b505  nop     dword ptr [rax+rax+00h]
0x18004b50a  mov     eax, dword ptr [rsp+0B8h+P+0Ch]
0x18004b50e  jmp     loc_18004BBB8
0x18004b513  test    r14d, r14d
0x18004b516  jz      short loc_18004B571
0x18004b518  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004b51d  mov     r9b, [rsi+40h]
0x18004b521  test    eax, eax
0x18004b523  jz      short loc_18004B543
0x18004b525  mov     rdx, [rsi+70h]; Src
0x18004b529  mov     rcx, [rsi+18h]; void *
0x18004b52d  mov     r8, r14; Size
0x18004b530  test    r9b, r9b
0x18004b533  jz      short loc_18004B53C
0x18004b535  call    RtlCopyFromUser
0x18004b53a  jmp     short loc_18004B571
0x18004b53c  call    RtlCopyVolatileMemory
0x18004b541  jmp     short loc_18004B571
0x18004b543  test    r9b, r9b
0x18004b546  jz      short loc_18004B561
0x18004b548  mov     rdx, r14; Length
0x18004b54b  mov     r8d, 1; Alignment
0x18004b551  mov     rcx, [rsi+70h]; Address
0x18004b555  call    cs:__imp_ProbeForRead
0x18004b55c  nop     dword ptr [rax+rax+00h]
0x18004b561  mov     r8, r14; Size
0x18004b564  mov     rdx, [rsi+70h]; Src
0x18004b568  mov     rcx, [rsi+18h]; void *
0x18004b56c  call    memmove
0x18004b571  mov     rcx, [rsi+18h]
0x18004b575  mov     r11, [rsp+0B8h+arg_10]
0x18004b57d  jmp     short loc_18004B5B5
0x18004b57f  mov     edi, eax
0x18004b581  mov     rbx, [rsp+0B8h+Src]
0x18004b589  cmp     qword ptr [rbx+18h], 0
0x18004b58e  jz      short loc_18004B5AE
0x18004b590  xor     edx, edx; Tag
0x18004b592  mov     rcx, [rbx+18h]; P
0x18004b596  call    cs:__imp_ExFreePoolWithTag
0x18004b59d  nop     dword ptr [rax+rax+00h]
0x18004b5a2  mov     qword ptr [rbx+18h], 0
0x18004b5aa  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004b5ae  mov     eax, edi
0x18004b5b0  jmp     loc_18004BBB8
0x18004b5b5  mov     eax, r14d
0x18004b5b8  neg     eax
0x18004b5ba  sbb     r15, r15
0x18004b5bd  and     r15, rcx
0x18004b5c0  add     rbx, rcx
0x18004b5c3  mov     r12d, [rbx+14h]
0x18004b5c7  bt      r12d, 1Ch
0x18004b5cc  jnb     short loc_18004B634
0x18004b5ce  cmp     r13d, 20h ; ' '
0x18004b5d2  jnb     short loc_18004B5DE
0x18004b5d4  mov     eax, 0C0000206h
0x18004b5d9  jmp     loc_18004BBB8
0x18004b5de  mov     rcx, [rsp+0B8h+arg_40]
0x18004b5e6  test    rcx, rcx
0x18004b5e9  jz      short loc_18004B62F
0x18004b5eb  mov     eax, [rbx+18h]
0x18004b5ee  cmp     eax, [rsp+0B8h+arg_48]
0x18004b5f5  jb      short loc_18004B601
0x18004b5f7  mov     eax, 0C0000010h
0x18004b5fc  jmp     loc_18004BBB8
0x18004b601  mov     rax, [rcx+rax*8]
0x18004b605  test    rax, rax
0x18004b608  jz      loc_18004B75E
0x18004b60e  mov     edi, [rax+20h]
0x18004b611  test    edi, edi
0x18004b613  jz      loc_18004B75E
0x18004b619  mov     r11, [rax+28h]
0x18004b61d  mov     [rsp+0B8h+arg_10], r11
0x18004b625  mov     eax, [rax+24h]
0x18004b628  mov     dword ptr [rsp+0B8h+Size], eax
0x18004b62f  btr     r12d, 1Ch
0x18004b634  mov     r13d, 28h ; '('
0x18004b63a  mov     eax, dword ptr [rsp+0B8h+Size]
0x18004b641  test    eax, eax
0x18004b643  cmovnz  r13d, eax
0x18004b647  test    edi, edi
0x18004b649  jz      short loc_18004B673
0x18004b64b  mov     ecx, edi
0x18004b64d  mov     rdx, [rbx]
0x18004b650  mov     rax, [r11]
0x18004b653  cmp     rdx, [rax]
0x18004b656  jnz     short loc_18004B662
0x18004b658  mov     rax, [rax+8]
0x18004b65c  cmp     [rbx+8], rax
0x18004b660  jz      short loc_18004B6C8
0x18004b662  add     r11, 18h
0x18004b666  mov     [rsp+0B8h+arg_10], r11
0x18004b66e  add     ecx, 0FFFFFFFFh
0x18004b671  jnz     short loc_18004B650
0x18004b673  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18004b67a  cmp     [rbx], rax
0x18004b67d  jnz     loc_18004BBB3
0x18004b683  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18004b68a  cmp     [rbx+8], rax
0x18004b68e  jnz     loc_18004BBB3
0x18004b694  cmp     dword ptr [rbx+10h], 0
0x18004b698  jnz     loc_18004BBAC
0x18004b69e  cmp     r12d, 100h
0x18004b6a5  jnz     loc_18004BBAC
0x18004b6ab  test    r14d, r14d
0x18004b6ae  jnz     loc_18004BB55
0x18004b6b4  mov     eax, edi
0x18004b6b6  shl     rax, 4
0x18004b6ba  mov     [rsi+38h], rax
0x18004b6be  mov     eax, 80000005h
0x18004b6c3  jmp     loc_18004BBB8
0x18004b6c8  test    r12d, 0FFF00h
0x18004b6cf  jz      short loc_18004B73F
0x18004b6d1  cmp     r12d, 200h
0x18004b6d8  jnz     loc_18004BB43
0x18004b6de  mov     r8d, [rbx+10h]
0x18004b6e2  mov     edx, r13d
0x18004b6e5  mov     rcx, r11
0x18004b6e8  call    FindEventItem
0x18004b6ed  test    rax, rax
0x18004b6f0  jz      short loc_18004B75E
0x18004b6f2  mov     [rsi+78h], r11
0x18004b6f6  cmp     dword ptr [rsp+0B8h+Size], 0
0x18004b6fe  jz      short loc_18004B707
0x18004b700  mov     [rsi+90h], rax
0x18004b707  mov     rax, [rax+20h]
0x18004b70b  test    rax, rax
0x18004b70e  jz      loc_18004BB43
0x18004b714  mov     r8, r15
0x18004b717  mov     rdx, rbx
0x18004b71a  mov     rcx, rsi
0x18004b71d  call    _guard_dispatch_icall
0x18004b722  mov     edx, eax
0x18004b724  cmp     eax, 107h
0x18004b729  jz      loc_18004BB43
0x18004b72f  xor     eax, eax
0x18004b731  cmp     edx, 0C0000016h
0x18004b737  cmovnz  eax, edx
0x18004b73a  jmp     loc_18004BBB8
0x18004b73f  mov     r8d, [rbx+10h]
  ... truncated ...
```
