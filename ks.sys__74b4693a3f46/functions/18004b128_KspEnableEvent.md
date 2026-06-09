# KspEnableEvent

- ea: `0x18004b128`
- end: `0x18004ba2c`
- name: `KspEnableEvent`
- size: `2308`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, unsigned int, __int64, __int64 (__fastcall *)(__int64, _QWORD, _QWORD), size_t Size, __int64, unsigned int, char)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x1800339a0`
- `0x180036e00`
- `0x1800374c0`
- `0x180049c20`
- `0x18004b0e0`

## callees

- `0x180008114`
- `0x180008640`
- `0x180010794`
- `0x180019bb0`
- `0x180019c60`
- `0x180019cc0`
- `0x180019fc0`
- `0x1800337b8`
- `0x18004b128`
- `0x18005a6bc`
- `0x18005d410`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x18004b2bc`
- `ntoskrnl!ProbeForWrite` at `0x18004b2bc`
- `ntoskrnl!ExAllocatePool2` at `0x18004b211`
- `ntoskrnl!ExAllocatePool2` at `0x18004b211`
- `ntoskrnl!ExSemaphoreObjectType` at `0x18004b800`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b811`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b86a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b811`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18004b86a`
- `ntoskrnl!ExEventObjectType` at `0x18004b859`
- `ntoskrnl!ProbeForRead` at `0x18004b1ae`
- `ntoskrnl!ProbeForRead` at `0x18004b1ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b397`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b3f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b397`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b3f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004b617`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004b617`

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
  __int64 v17; // rdi
  __int64 v18; // rcx
  unsigned int v19; // r12d
  __int64 v20; // rax
  int ULongFromUser; // r15d
  __int64 result; // rax
  __int64 v23; // r12
  void *v24; // rdx
  void *v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rcx
  PVOID v28; // rcx
  void *v29; // rdx
  void *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // rdi
  int v33; // r12d
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // r13d
  unsigned int v37; // ecx
  __int64 EventItem; // rax
  __int64 v39; // r11
  __int64 (__fastcall *v40)(__int64, __int64, __int64); // rax
  unsigned int v41; // edx
  __int64 v42; // rax
  __int64 v43; // rdx
  unsigned int v44; // eax
  unsigned int v45; // ecx
  SIZE_T v46; // rdx
  unsigned int v47; // ebx
  char *PoolWithTag; // rax
  char *v49; // r14
  PVOID *Object; // r8
  _QWORD *v51; // rdi
  int v52; // r10d
  int v53; // eax
  char *v54; // rdi
  NTSTATUS Dpc; // ebx
  int v56; // ecx
  bool v57; // zf
  int v58; // ecx
  int v59; // eax
  KDPC_IMPORTANCE v60; // r8d
  KDEFERRED_ROUTINE *v61; // rdx
  int v62; // ecx
  unsigned __int64 v63; // rcx
  _OWORD **i; // r11
  unsigned int v65; // [rsp+30h] [rbp-88h]
  _QWORD v66[2]; // [rsp+38h] [rbp-80h] BYREF
  __int128 v67; // [rsp+48h] [rbp-70h] BYREF
  __int128 v68; // [rsp+58h] [rbp-60h]
  PVOID P[2]; // [rsp+68h] [rbp-50h]
  _QWORD *Src; // [rsp+C0h] [rbp+8h]
  __int64 v71; // [rsp+D0h] [rbp+18h]

  v71 = a3;
  v11 = a3;
  v14 = *(_QWORD *)(a1 + 184);
  v66[0] = v14;
  v15 = *(unsigned int *)(v14 + 16);
  v65 = *(_DWORD *)(v14 + 16);
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
    v20 = *(_QWORD *)(v14 + 32);
    if ( *(_BYTE *)(a1 + 64) )
      ULongFromUser = RtlReadULongFromUser(v20 + 20);
    else
      ULongFromUser = *(_DWORD *)(v20 + 20);
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
    v23 = v66[0];
    v24 = *(void **)(v66[0] + 32LL);
    v25 = (void *)(v17 + *(_QWORD *)(a1 + 24));
    if ( *(_BYTE *)(a1 + 64) )
      RtlCopyFromUser(v25, v24, v15);
    else
      RtlCopyVolatileMemory(v25, v24, v15);
    *(_DWORD *)(v17 + *(_QWORD *)(a1 + 24) + 20) = ULongFromUser;
    v26 = ULongFromUser & 0xEFFFFFFF;
    if ( v26 == 1 || v26 == 2 || v26 == 4 )
    {
      if ( (_DWORD)v16 )
      {
        v29 = *(void **)(a1 + 112);
        v30 = *(void **)(a1 + 24);
        if ( *(_BYTE *)(a1 + 64) )
          RtlCopyFromUser(v30, v29, v16);
        else
          RtlCopyVolatileMemory(v30, v29, v16);
      }
    }
    else
    {
      if ( v26 != 256 && v26 != 512 && v26 != 1024 )
        return 3221225485LL;
      if ( (_DWORD)v16 )
      {
        if ( *(_BYTE *)(a1 + 64) )
          ProbeForWrite(*(volatile void **)(a1 + 112), v16, 1u);
        *(_DWORD *)(a1 + 16) |= 0x40u;
      }
      if ( v26 == 1024 )
      {
        v67 = 0;
        v68 = 0;
        *(_OWORD *)P = 0;
        if ( v65 < 0x28 )
          return 3221225990LL;
        v27 = *(_QWORD *)(a1 + 24);
        if ( *(_QWORD *)(v17 + v27 + 32) )
          return 3221225485LL;
        *(_QWORD *)&v67 = a4;
        *((_QWORD *)&v67 + 1) = *(_QWORD *)(v23 + 48);
        *(_QWORD *)&v68 = a1;
        *((_QWORD *)&v68 + 1) = *(_QWORD *)(v17 + v27 + 24);
        P[1] = (PVOID)(unsigned int)v16;
        PerformLockedOperation(a5, a6, QueryBufferSynchronize, &v67);
        result = HIDWORD(P[1]);
        if ( SHIDWORD(P[1]) >= 0 )
        {
          memmove(*(void **)(a1 + 24), (char *)P[0] + 24, *((unsigned int *)P[0] + 5));
          v28 = P[0];
          *(_QWORD *)(a1 + 56) = *((unsigned int *)P[0] + 5);
          ExFreePoolWithTag(v28, 0);
          return HIDWORD(P[1]);
        }
        return result;
      }
    }
    v18 = *(_QWORD *)(a1 + 24);
    v11 = v71;
  }
  v31 = v18 & -(__int64)((_DWORD)v16 != 0);
  v32 = v18 + v17;
  v33 = *(_DWORD *)(v32 + 20);
  if ( (v33 & 0x10000000) != 0 )
  {
    if ( (unsigned int)v15 < 0x20 )
      return 3221225990LL;
    if ( a9 )
    {
      v34 = *(unsigned int *)(v32 + 24);
      if ( (unsigned int)v34 >= a10 )
        return 3221225488LL;
      v35 = *(_QWORD *)(a9 + 8 * v34);
      if ( !v35 )
        return 3221226021LL;
      a2 = *(_DWORD *)(v35 + 32);
      if ( !a2 )
        return 3221226021LL;
      v11 = *(_QWORD *)(v35 + 40);
      v71 = v11;
      LODWORD(Size) = *(_DWORD *)(v35 + 36);
    }
    v33 &= ~0x10000000u;
  }
  v36 = 40;
  if ( (_DWORD)Size )
    v36 = Size;
  if ( !a2 )
  {
LABEL_59:
    if ( *(_QWORD *)v32 != *(_QWORD *)&GUID_NULL.Data1 || *(_QWORD *)(v32 + 8) != *(_QWORD *)GUID_NULL.Data4 )
      return 3221226032LL;
    if ( *(_DWORD *)(v32 + 16) || v33 != 256 )
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
    v63 = 16LL * a2;
    if ( v16 >= v63 )
    {
      *(_QWORD *)(a1 + 56) = v63;
      for ( i = (_OWORD **)(-24LL * a2 + v11); a2; --a2 )
      {
        *(_OWORD *)v31 = **i;
        v31 += 16;
        i += 3;
      }
      return 0;
    }
    return 3221225507LL;
  }
  v37 = a2;
  while ( *(_QWORD *)v32 != **(_QWORD **)v11 || *(_QWORD *)(v32 + 8) != *(_QWORD *)(*(_QWORD *)v11 + 8LL) )
  {
    v11 += 24;
    v71 = v11;
    if ( !--v37 )
      goto LABEL_59;
  }
  if ( (v33 & 0xFFF00) != 0 )
  {
    if ( v33 != 512 )
      return 0;
    EventItem = FindEventItem(v11, v36, *(unsigned int *)(v32 + 16));
    if ( EventItem )
    {
      *(_QWORD *)(a1 + 120) = v39;
      if ( (_DWORD)Size )
        *(_QWORD *)(a1 + 144) = EventItem;
      v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(EventItem + 32);
      if ( v40 )
      {
        v41 = v40(a1, v32, v31);
        if ( v41 != 263 )
        {
          result = 0;
          if ( v41 != -1073741802 )
            return v41;
          return result;
        }
      }
      return 0;
    }
    return 3221226021LL;
  }
  v42 = FindEventItem(v11, v36, *(unsigned int *)(v32 + 16));
  v43 = v42;
  Src = (_QWORD *)v42;
  if ( !v42 )
    return 3221226021LL;
  if ( (unsigned int)v16 < *(_DWORD *)(v42 + 4) )
    return 3221225507LL;
  v44 = 0;
  if ( a11 )
  {
    if ( v36 >= 0xFFFFFFE8 )
      return 3221225621LL;
    v44 = v36 + 31;
    if ( v36 + 31 < v36 + 24 )
      return 3221225621LL;
  }
  v45 = v44 + 120;
  if ( v44 + 120 < v44 )
    return 3221225621LL;
  v46 = v45 + *(_DWORD *)(v43 + 8);
  if ( (unsigned int)v46 < v45 )
    return 3221225621LL;
  v47 = v46;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v46, 0x6565534Bu);
  v49 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return 3221225626LL;
    memset(PoolWithTag, 0, v47);
  }
  if ( !v49 )
    return 3221225626LL;
  *(_QWORD *)v49 = Src[3];
  *(_OWORD *)(v49 + 8) = *(_OWORD *)v32;
  *((_QWORD *)v49 + 3) = *(_QWORD *)(v32 + 16);
  Object = (PVOID *)(v49 + 48);
  *((_QWORD *)v49 + 6) = 0;
  *((_QWORD *)v49 + 7) = 0;
  *((_QWORD *)v49 + 8) = *(_QWORD *)(a1 + 112);
  *((_DWORD *)v49 + 18) = *(_DWORD *)v31;
  *((_QWORD *)v49 + 10) = v71;
  v51 = Src;
  *((_QWORD *)v49 + 11) = Src;
  *((_QWORD *)v49 + 12) = *(_QWORD *)(v66[0] + 48LL);
  *((_DWORD *)v49 + 27) = 0;
  v52 = 2;
  if ( v33 == 2 )
  {
    *((_DWORD *)v49 + 28) = 2;
  }
  else
  {
    v53 = 0;
    if ( v33 == 4 )
      v53 = 4;
    *((_DWORD *)v49 + 28) = v53;
  }
  if ( a11 )
  {
    v54 = &v49[(*((unsigned int *)Src + 2) + 127LL) & 0xFFFFFFFFFFFFFFF8uLL];
    *(_OWORD *)v54 = *(_OWORD *)v71;
    *((_QWORD *)v54 + 2) = *(_QWORD *)(v71 + 16);
    memmove(v54 + 24, Src, v36);
    *((_QWORD *)v49 + 10) = v54;
    *((_QWORD *)v49 + 11) = v54 + 24;
    v52 = 2;
    v51 = Src;
    Object = (PVOID *)(v49 + 48);
  }
  if ( *((_DWORD *)v49 + 18) == 1 )
  {
    if ( !*(_QWORD *)(v31 + 16) && !*(_QWORD *)(v31 + 24) )
    {
      Dpc = ObReferenceObjectByHandle(
              *(HANDLE *)(v31 + 8),
              2u,
              (POBJECT_TYPE)ExEventObjectType,
              *(_BYTE *)(a1 + 64),
              Object,
              0);
      goto LABEL_102;
    }
  }
  else
  {
    if ( *((_DWORD *)v49 + 18) == 2 )
    {
      if ( !*(_DWORD *)(v31 + 16) )
      {
        Dpc = ObReferenceObjectByHandle(
                *(HANDLE *)(v31 + 8),
                2u,
                (POBJECT_TYPE)ExSemaphoreObjectType,
                *(_BYTE *)(a1 + 64),
                Object,
                0);
        if ( Dpc >= 0 )
          *((_DWORD *)v49 + 26) = *(_DWORD *)(v31 + 20);
        goto LABEL_102;
      }
      goto LABEL_101;
    }
    if ( *((_DWORD *)v49 + 18) != 4 )
    {
      if ( *((_DWORD *)v49 + 18) == 8 )
      {
        v57 = *(_BYTE *)(a1 + 64) == 0;
        goto LABEL_114;
      }
      if ( *((_DWORD *)v49 + 18) != 16 && *((_DWORD *)v49 + 18) != 32 && *((_DWORD *)v49 + 18) != 128 )
        goto LABEL_101;
    }
    if ( !*(_BYTE *)(a1 + 64) )
    {
      v57 = *(_QWORD *)(v31 + 24) == 0;
LABEL_114:
      if ( v57 )
      {
        Dpc = 0;
        goto LABEL_104;
      }
    }
  }
LABEL_101:
  Dpc = -1073741811;
LABEL_102:
  if ( Dpc < 0 )
    goto LABEL_142;
  v52 = 2;
LABEL_104:
  switch ( *((_DWORD *)v49 + 18) )
  {
    case 1:
    case 2:
      v60 = LowImportance;
LABEL_140:
      v61 = EventDpc;
      goto LABEL_141;
    case 4:
    case 8:
      v62 = *(_DWORD *)(v31 + 16);
      if ( v62 )
      {
        if ( v62 == 1 )
          v52 = 1;
      }
      else
      {
        v52 = 0;
      }
      v60 = v52;
      goto LABEL_140;
    case 0x10:
      if ( (*((_DWORD *)v49 + 28) & 2) == 0 )
        break;
      v60 = MediumImportance;
      v61 = (KDEFERRED_ROUTINE *)OneShotDpc;
      goto LABEL_141;
    case 0x20:
    case 0x80:
      if ( *((_DWORD *)v49 + 18) == 32 )
        v56 = *(_DWORD *)(v31 + 16);
      else
        v56 = *(_DWORD *)(*(_QWORD *)(v31 + 16) + 80LL);
      if ( v56 )
      {
        v58 = v56 - 1;
        if ( !v58 )
        {
          v59 = 0;
          goto LABEL_131;
        }
        if ( v58 == 1 )
        {
          v59 = 2;
LABEL_131:
          v60 = v59;
          v61 = WorkerDpc;
LABEL_141:
          Dpc = CreateDpc(v49 + 32, v61, v60);
          break;
        }
      }
      v59 = 1;
      goto LABEL_131;
  }
LABEL_142:
  if ( Dpc < 0 )
    goto LABEL_151;
  if ( (*((_DWORD *)v49 + 28) & 4) != 0 && !*((_QWORD *)v49 + 7) )
    Dpc = CreateDpc(v49 + 32, WorkerDpc, LowImportance);
  if ( Dpc < 0 )
    goto LABEL_151;
  if ( !v51[2] )
  {
    v66[0] = a4;
    v66[1] = v49 + 32;
    PerformLockedOperation(a5, a6, AddEventSynchronize, v66);
    return 0;
  }
  *(_QWORD *)(a1 + 120) = v49 + 32;
  if ( (_DWORD)Size )
    *(_QWORD *)(a1 + 144) = v51;
  result = ((__int64 (__fastcall *)(__int64, __int64, char *))v51[2])(a1, v31, v49 + 32);
  Dpc = result;
  if ( (int)result < 0 )
  {
LABEL_151:
    KsDiscardEvent((PKSEVENT_ENTRY)(v49 + 32));
    return (unsigned int)Dpc;
  }
  return result;
}

```

## disassembly

```asm
0x18004b128  mov     [rsp+arg_18], r9
0x18004b12d  mov     [rsp+arg_10], r8
0x18004b132  mov     [rsp+Src], rcx
0x18004b137  push    rbx
0x18004b138  push    rsi
0x18004b139  push    rdi
0x18004b13a  push    r12
0x18004b13c  push    r13
0x18004b13e  push    r14
0x18004b140  push    r15
0x18004b142  sub     rsp, 80h
0x18004b149  mov     r11, r8
0x18004b14c  mov     ebx, edx
0x18004b14e  mov     rsi, rcx
0x18004b151  mov     r15, [rcx+0B8h]
0x18004b158  mov     [rsp+0B8h+var_80], r15
0x18004b15d  mov     r13d, [r15+10h]
0x18004b161  mov     [rsp+0B8h+var_88], r13d
0x18004b166  mov     r14d, [r15+8]
0x18004b16a  lea     edi, [r14+7]
0x18004b16e  and     edi, 0FFFFFFF8h
0x18004b171  mov     rcx, [rcx+18h]
0x18004b175  test    rcx, rcx
0x18004b178  jnz     loc_18004B412
0x18004b17e  cmp     r13d, 18h
0x18004b182  jb      loc_18004B431
0x18004b188  cmp     edi, r14d
0x18004b18b  jb      loc_18004B431
0x18004b191  lea     r12d, [rdi+r13]
0x18004b195  cmp     r12d, edi
0x18004b198  jb      loc_18004B431
0x18004b19e  cmp     [rsi+40h], cl
0x18004b1a1  jz      short loc_18004B1BA
0x18004b1a3  mov     edx, r13d; Length
0x18004b1a6  lea     r8d, [rcx+1]; Alignment
0x18004b1aa  mov     rcx, [r15+20h]; Address
0x18004b1ae  call    cs:__imp_ProbeForRead
0x18004b1b5  nop     dword ptr [rax+rax+00h]
0x18004b1ba  mov     rax, [r15+20h]
0x18004b1be  cmp     byte ptr [rsi+40h], 0
0x18004b1c2  jz      short loc_18004B1D2
0x18004b1c4  lea     rcx, [rax+14h]
0x18004b1c8  call    RtlReadULongFromUser
0x18004b1cd  mov     r15d, eax
0x18004b1d0  jmp     short loc_18004B1D6
0x18004b1d2  mov     r15d, [rax+14h]
0x18004b1d6  mov     rax, [rsp+0B8h+arg_30]
0x18004b1de  test    rax, rax
0x18004b1e1  jz      short loc_18004B203
0x18004b1e3  test    r15d, 0FFF00h
0x18004b1ea  jnz     short loc_18004B203
0x18004b1ec  xor     r8d, r8d
0x18004b1ef  mov     edx, r12d
0x18004b1f2  mov     rcx, rsi
0x18004b1f5  call    _guard_dispatch_icall
0x18004b1fa  test    eax, eax
0x18004b1fc  jns     short loc_18004B225
0x18004b1fe  jmp     loc_18004BA18
0x18004b203  mov     edx, r12d
0x18004b206  mov     ecx, 63h ; 'c'
0x18004b20b  mov     r8d, 7070534Bh
0x18004b211  call    cs:__imp_ExAllocatePool2
0x18004b218  nop     dword ptr [rax+rax+00h]
0x18004b21d  mov     [rsi+18h], rax
0x18004b221  or      dword ptr [rsi+10h], 30h
0x18004b225  mov     r8, rdi; Size
0x18004b228  xor     edx, edx; Val
0x18004b22a  mov     rcx, [rsi+18h]; void *
0x18004b22e  call    memset
0x18004b233  mov     r12, [rsp+0B8h+var_80]
0x18004b238  mov     rdx, [r12+20h]; Src
0x18004b23d  mov     rcx, [rsi+18h]
0x18004b241  add     rcx, rdi; void *
0x18004b244  mov     r8, r13; Size
0x18004b247  cmp     byte ptr [rsi+40h], 0
0x18004b24b  jz      short loc_18004B254
0x18004b24d  call    RtlCopyFromUser
0x18004b252  jmp     short loc_18004B259
0x18004b254  call    RtlCopyVolatileMemory
0x18004b259  mov     rax, [rsi+18h]
0x18004b25d  mov     [rdi+rax+14h], r15d
0x18004b262  btr     r15d, 1Ch
0x18004b267  mov     eax, r15d
0x18004b26a  sub     eax, 1
0x18004b26d  jz      loc_18004B3AC
0x18004b273  sub     eax, 1
0x18004b276  jz      loc_18004B3AC
0x18004b27c  sub     eax, 2
0x18004b27f  jz      loc_18004B3AC
0x18004b285  sub     eax, 0FCh
0x18004b28a  jz      short loc_18004B2A4
0x18004b28c  sub     eax, 100h
0x18004b291  jz      short loc_18004B2A4
0x18004b293  cmp     eax, 200h
0x18004b298  jz      short loc_18004B2A4
0x18004b29a  mov     eax, 0C000000Dh
0x18004b29f  jmp     loc_18004BA18
0x18004b2a4  test    r14d, r14d
0x18004b2a7  jz      short loc_18004B2CC
0x18004b2a9  cmp     byte ptr [rsi+40h], 0
0x18004b2ad  jz      short loc_18004B2C8
0x18004b2af  mov     rdx, r14; Length
0x18004b2b2  mov     r8d, 1; Alignment
0x18004b2b8  mov     rcx, [rsi+70h]; Address
0x18004b2bc  call    cs:__imp_ProbeForWrite
0x18004b2c3  nop     dword ptr [rax+rax+00h]
0x18004b2c8  or      dword ptr [rsi+10h], 40h
0x18004b2cc  cmp     r15d, 400h
0x18004b2d3  jnz     loc_18004B3CE
0x18004b2d9  xorps   xmm0, xmm0
0x18004b2dc  movups  [rsp+0B8h+var_70], xmm0
0x18004b2e1  movups  [rsp+0B8h+var_60], xmm0
0x18004b2e6  movups  xmmword ptr [rsp+0B8h+P], xmm0
0x18004b2eb  mov     r13d, 28h ; '('
0x18004b2f1  cmp     [rsp+0B8h+var_88], r13d
0x18004b2f6  jnb     short loc_18004B302
0x18004b2f8  mov     eax, 0C0000206h
0x18004b2fd  jmp     loc_18004BA18
0x18004b302  mov     rcx, [rsi+18h]
0x18004b306  cmp     qword ptr [rdi+rcx+20h], 0
0x18004b30c  jz      short loc_18004B318
0x18004b30e  mov     eax, 0C000000Dh
0x18004b313  jmp     loc_18004BA18
0x18004b318  mov     rax, [rsp+0B8h+arg_18]
0x18004b320  mov     qword ptr [rsp+0B8h+var_70], rax
0x18004b325  mov     rax, [r12+30h]
0x18004b32a  mov     qword ptr [rsp+0B8h+var_70+8], rax
0x18004b32f  mov     qword ptr [rsp+0B8h+var_60], rsi
0x18004b334  mov     rax, [rdi+rcx+18h]
0x18004b339  mov     qword ptr [rsp+0B8h+var_60+8], rax
0x18004b33e  mov     dword ptr [rsp+0B8h+P+8], r14d
0x18004b343  mov     dword ptr [rsp+0B8h+P+0Ch], 0
0x18004b34b  lea     r9, [rsp+0B8h+var_70]
0x18004b350  lea     r8, QueryBufferSynchronize
0x18004b357  mov     rdx, [rsp+0B8h+arg_28]
0x18004b35f  mov     ecx, [rsp+0B8h+arg_20]
0x18004b366  call    PerformLockedOperation
0x18004b36b  mov     eax, dword ptr [rsp+0B8h+P+0Ch]
0x18004b36f  test    eax, eax
0x18004b371  js      short loc_18004B3A7
0x18004b373  mov     rdx, [rsp+0B8h+P]
0x18004b378  mov     r8d, [rdx+14h]; Size
0x18004b37c  add     rdx, 18h; Src
0x18004b380  mov     rcx, [rsi+18h]; void *
0x18004b384  call    memmove
0x18004b389  mov     rcx, [rsp+0B8h+P]; P
0x18004b38e  mov     eax, [rcx+14h]
0x18004b391  mov     [rsi+38h], rax
0x18004b395  xor     edx, edx; Tag
0x18004b397  call    cs:__imp_ExFreePoolWithTag
0x18004b39e  nop     dword ptr [rax+rax+00h]
0x18004b3a3  mov     eax, dword ptr [rsp+0B8h+P+0Ch]
0x18004b3a7  jmp     loc_18004BA18
0x18004b3ac  test    r14d, r14d
0x18004b3af  jz      short loc_18004B3CE
0x18004b3b1  mov     rdx, [rsi+70h]; Src
0x18004b3b5  mov     rcx, [rsi+18h]; void *
0x18004b3b9  mov     r8, r14; Size
0x18004b3bc  cmp     byte ptr [rsi+40h], 0
0x18004b3c0  jz      short loc_18004B3C9
0x18004b3c2  call    RtlCopyFromUser
0x18004b3c7  jmp     short loc_18004B3CE
0x18004b3c9  call    RtlCopyVolatileMemory
0x18004b3ce  mov     rcx, [rsi+18h]
0x18004b3d2  mov     r11, [rsp+0B8h+arg_10]
0x18004b3da  jmp     short loc_18004B412
0x18004b3dc  mov     edi, eax
0x18004b3de  mov     rbx, [rsp+0B8h+Src]
0x18004b3e6  cmp     qword ptr [rbx+18h], 0
0x18004b3eb  jz      short loc_18004B40B
0x18004b3ed  xor     edx, edx; Tag
0x18004b3ef  mov     rcx, [rbx+18h]; P
0x18004b3f3  call    cs:__imp_ExFreePoolWithTag
0x18004b3fa  nop     dword ptr [rax+rax+00h]
0x18004b3ff  mov     qword ptr [rbx+18h], 0
0x18004b407  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004b40b  mov     eax, edi
0x18004b40d  jmp     loc_18004BA18
0x18004b412  mov     eax, r14d
0x18004b415  neg     eax
0x18004b417  sbb     r15, r15
0x18004b41a  and     r15, rcx
0x18004b41d  add     rdi, rcx
0x18004b420  mov     r12d, [rdi+14h]
0x18004b424  bt      r12d, 1Ch
0x18004b429  jnb     short loc_18004B491
0x18004b42b  cmp     r13d, 20h ; ' '
0x18004b42f  jnb     short loc_18004B43B
0x18004b431  mov     eax, 0C0000206h
0x18004b436  jmp     loc_18004BA18
0x18004b43b  mov     rcx, [rsp+0B8h+arg_40]
0x18004b443  test    rcx, rcx
0x18004b446  jz      short loc_18004B48C
0x18004b448  mov     eax, [rdi+18h]
0x18004b44b  cmp     eax, [rsp+0B8h+arg_48]
0x18004b452  jb      short loc_18004B45E
0x18004b454  mov     eax, 0C0000010h
0x18004b459  jmp     loc_18004BA18
0x18004b45e  mov     rax, [rcx+rax*8]
0x18004b462  test    rax, rax
0x18004b465  jz      loc_18004B5BB
0x18004b46b  mov     ebx, [rax+20h]
0x18004b46e  test    ebx, ebx
0x18004b470  jz      loc_18004B5BB
0x18004b476  mov     r11, [rax+28h]
0x18004b47a  mov     [rsp+0B8h+arg_10], r11
0x18004b482  mov     eax, [rax+24h]
0x18004b485  mov     dword ptr [rsp+0B8h+Size], eax
0x18004b48c  btr     r12d, 1Ch
0x18004b491  mov     r13d, 28h ; '('
0x18004b497  mov     eax, dword ptr [rsp+0B8h+Size]
0x18004b49e  test    eax, eax
0x18004b4a0  cmovnz  r13d, eax
0x18004b4a4  test    ebx, ebx
0x18004b4a6  jz      short loc_18004B4D0
0x18004b4a8  mov     ecx, ebx
0x18004b4aa  mov     rdx, [rdi]
0x18004b4ad  mov     rax, [r11]
0x18004b4b0  cmp     rdx, [rax]
0x18004b4b3  jnz     short loc_18004B4BF
0x18004b4b5  mov     rax, [rax+8]
0x18004b4b9  cmp     [rdi+8], rax
0x18004b4bd  jz      short loc_18004B525
0x18004b4bf  add     r11, 18h
0x18004b4c3  mov     [rsp+0B8h+arg_10], r11
0x18004b4cb  add     ecx, 0FFFFFFFFh
0x18004b4ce  jnz     short loc_18004B4AD
0x18004b4d0  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18004b4d7  cmp     [rdi], rax
0x18004b4da  jnz     loc_18004BA13
0x18004b4e0  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18004b4e7  cmp     [rdi+8], rax
0x18004b4eb  jnz     loc_18004BA13
0x18004b4f1  cmp     dword ptr [rdi+10h], 0
0x18004b4f5  jnz     loc_18004BA0C
0x18004b4fb  cmp     r12d, 100h
0x18004b502  jnz     loc_18004BA0C
0x18004b508  test    r14d, r14d
0x18004b50b  jnz     loc_18004B9B5
0x18004b511  mov     eax, ebx
0x18004b513  shl     rax, 4
0x18004b517  mov     [rsi+38h], rax
0x18004b51b  mov     eax, 80000005h
0x18004b520  jmp     loc_18004BA18
0x18004b525  test    r12d, 0FFF00h
0x18004b52c  jz      short loc_18004B59C
0x18004b52e  cmp     r12d, 200h
0x18004b535  jnz     loc_18004B9A3
0x18004b53b  mov     r8d, [rdi+10h]
0x18004b53f  mov     edx, r13d
0x18004b542  mov     rcx, r11
0x18004b545  call    FindEventItem
0x18004b54a  test    rax, rax
0x18004b54d  jz      short loc_18004B5BB
0x18004b54f  mov     [rsi+78h], r11
0x18004b553  cmp     dword ptr [rsp+0B8h+Size], 0
0x18004b55b  jz      short loc_18004B564
0x18004b55d  mov     [rsi+90h], rax
0x18004b564  mov     rax, [rax+20h]
0x18004b568  test    rax, rax
0x18004b56b  jz      loc_18004B9A3
0x18004b571  mov     r8, r15
0x18004b574  mov     rdx, rdi
0x18004b577  mov     rcx, rsi
0x18004b57a  call    _guard_dispatch_icall
0x18004b57f  mov     edx, eax
0x18004b581  cmp     eax, 107h
0x18004b586  jz      loc_18004B9A3
0x18004b58c  xor     eax, eax
0x18004b58e  cmp     edx, 0C0000016h
0x18004b594  cmovnz  eax, edx
0x18004b597  jmp     loc_18004BA18
0x18004b59c  mov     r8d, [rdi+10h]
0x18004b5a0  mov     edx, r13d
0x18004b5a3  mov     rcx, r11
0x18004b5a6  call    FindEventItem
0x18004b5ab  mov     rdx, rax
0x18004b5ae  mov     [rsp+0B8h+Src], rax
0x18004b5b6  test    rax, rax
0x18004b5b9  jnz     short loc_18004B5C5
0x18004b5bb  mov     eax, 0C0000225h
0x18004b5c0  jmp     loc_18004BA18
0x18004b5c5  cmp     r14d, [rax+4]
0x18004b5c9  jb      loc_18004B9DC
0x18004b5cf  xor     eax, eax
0x18004b5d1  cmp     [rsp+0B8h+arg_50], al
0x18004b5d8  jz      short loc_18004B5F2
0x18004b5da  lea     ecx, [r13+18h]
0x18004b5de  cmp     ecx, 18h
0x18004b5e1  jb      loc_18004B9AE
0x18004b5e7  lea     eax, [rcx+7]
0x18004b5ea  cmp     eax, ecx
0x18004b5ec  jb      loc_18004B9AE
0x18004b5f2  lea     ecx, [rax+78h]
0x18004b5f5  cmp     ecx, eax
0x18004b5f7  jb      loc_18004B9AE
0x18004b5fd  mov     edx, [rdx+8]
0x18004b600  add     edx, ecx; NumberOfBytes
0x18004b602  cmp     edx, ecx
0x18004b604  jb      loc_18004B9AE
  ... truncated ...
```
