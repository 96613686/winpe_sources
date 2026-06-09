# KspPropertyHandler

- ea: `0x18004a048`
- end: `0x18004a8a5`
- name: `KspPropertyHandler`
- size: `2141`
- prototype: `NTSTATUS __fastcall(__int64 Irp, unsigned int, struct _LIST_ENTRY *, __int64 (__fastcall *)(__int64, _QWORD, struct _LIST_ENTRY *), unsigned int, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800339a0`
- `0x180036e00`
- `0x180038d90`
- `0x180049bf0`
- `0x180049c20`

## callees

- `0x180010794`
- `0x180019bb0`
- `0x180019c60`
- `0x180019cc0`
- `0x180019fc0`
- `0x1800337b8`
- `0x180038dcc`
- `0x1800390c8`
- `0x18004a048`
- `0x18004d400`
- `0x18004d4c0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x18004a23e`
- `ntoskrnl!ProbeForWrite` at `0x18004a23e`
- `ntoskrnl!ExAllocatePool2` at `0x18004a139`
- `ntoskrnl!ExAllocatePool2` at `0x18004a139`
- `ntoskrnl!ProbeForRead` at `0x18004a0cb`
- `ntoskrnl!ProbeForRead` at `0x18004a0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004a2a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004a2a6`

## pseudocode

```c
NTSTATUS __fastcall KspPropertyHandler(
        __int64 Irp,
        unsigned int a2,
        struct _LIST_ENTRY *a3,
        __int64 (__fastcall *a4)(__int64, _QWORD, struct _LIST_ENTRY *),
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  struct _LIST_ENTRY *v7; // r12
  unsigned int v8; // r11d
  __int64 v9; // rdi
  struct _IO_STACK_LOCATION *v10; // r14
  unsigned int Options; // r9d
  size_t Length; // r13
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  unsigned int v15; // r15d
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  int ULongFromUser; // esi
  NTSTATUS result; // eax
  __int64 v19; // r15
  PNAMED_PIPE_CREATE_PARAMETERS v20; // rdx
  char *v21; // rcx
  int v22; // ebx
  PVOID v23; // rdx
  struct _IRP *v24; // rcx
  PVOID v25; // rdx
  struct _IRP *v26; // rcx
  __int64 v27; // rbx
  char *v28; // r10
  int v29; // edx
  unsigned int v30; // r14d
  struct _LIST_ENTRY *v31; // r8
  __int64 v32; // rax
  int *v33; // rax
  __int64 v34; // rdx
  unsigned int v35; // esi
  __int64 v36; // r15
  struct _LIST_ENTRY *v37; // rcx
  bool v38; // cf
  __int64 v39; // rax
  __int64 v40; // r10
  __int64 v41; // rsi
  __int64 (__fastcall *v42)(__int64, __int64, __int64); // rax
  __int64 v43; // rax
  __int64 (__fastcall *v44)(__int64, char *, __int64); // rax
  int v45; // ecx
  __int64 v46; // rcx
  int v47; // r8d
  unsigned int v48; // r13d
  int v49; // r10d
  unsigned int *v50; // rcx
  bool v51; // zf
  unsigned int v52; // r9d
  unsigned __int64 v53; // rdx
  __int64 v54; // rax
  _OWORD *v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rsi
  int v58; // r15d
  _OWORD *v59; // rbx
  _OWORD *v60; // rbx
  __int64 v61; // rax
  __int64 PropertyItem; // rdx
  ULONG_PTR v63; // rax
  unsigned __int64 v64; // rcx
  _OWORD **i; // r12
  unsigned int Size; // [rsp+20h] [rbp-48h]
  unsigned int Size_4; // [rsp+24h] [rbp-44h]

  v7 = a3;
  v8 = a2;
  v9 = Irp;
  v10 = *(struct _IO_STACK_LOCATION **)(Irp + 184);
  Options = v10->Parameters.Create.Options;
  Size = Options;
  Length = v10->Parameters.Read.Length;
  Size_4 = Length;
  v13 = ((_DWORD)Length + 7) & 0xFFFFFFF8;
  v14 = *(_QWORD *)(Irp + 24);
  if ( v14 )
  {
    v19 = (unsigned int)v13;
    goto LABEL_53;
  }
  if ( Options < 0x18 )
    return -1073741306;
  if ( (unsigned int)v13 < (unsigned int)Length )
    return -1073741306;
  v15 = v13 + Options;
  if ( (unsigned int)v13 + Options < (unsigned int)v13 )
    return -1073741306;
  if ( *(_BYTE *)(v9 + 64) )
    ProbeForRead(v10->Parameters.CreatePipe.Parameters, Options, 1u);
  Parameters = v10->Parameters.CreatePipe.Parameters;
  if ( *(_BYTE *)(v9 + 64) )
    ULongFromUser = RtlReadULongFromUser(&Parameters->OutboundQuota);
  else
    ULongFromUser = Parameters->OutboundQuota;
  if ( a4 && (ULongFromUser & 3) != 0 )
  {
    if ( (_DWORD)Length && (ULongFromUser & 1) != 0 )
      LOBYTE(a3) = 1;
    else
      a3 = 0;
    result = a4(v9, v15, a3);
    if ( result < 0 )
      return result;
  }
  else
  {
    *(_QWORD *)(v9 + 24) = ExAllocatePool2(99, v15, 1886409547);
    *(_DWORD *)(v9 + 16) |= 0x30u;
  }
  v19 = (unsigned int)v13;
  memset(*(void **)(v9 + 24), 0, (unsigned int)v13);
  v20 = v10->Parameters.CreatePipe.Parameters;
  v21 = (char *)((unsigned int)v13 + *(_QWORD *)(v9 + 24));
  if ( *(_BYTE *)(v9 + 64) )
    RtlCopyFromUser(v21, v20, Size);
  else
    RtlCopyVolatileMemory(v21, v20, Size);
  *(_DWORD *)(*(_QWORD *)(v9 + 24) + v13 + 20) = ULongFromUser;
  v22 = ULongFromUser & 0x67FFFFFF;
  if ( (ULongFromUser & 0x67FFFFFFu) > 0x800 )
  {
    if ( v22 != 4096 )
    {
      if ( v22 == 0x2000 )
        goto LABEL_41;
      if ( v22 != 0x4000 )
      {
        if ( ((v22 - 0x8000) & 0xFFFF7FFF) == 0 )
          goto LABEL_41;
        return -1073741811;
      }
    }
    goto LABEL_47;
  }
  switch ( v22 )
  {
    case 2048:
      goto LABEL_41;
    case 1:
      goto LABEL_31;
    case 2:
LABEL_47:
      if ( (_DWORD)Length )
      {
        v25 = *(PVOID *)(v9 + 112);
        v26 = *(struct _IRP **)(v9 + 24);
        if ( *(_BYTE *)(v9 + 64) )
          RtlCopyFromUser(v26, v25, Length);
        else
          RtlCopyVolatileMemory(v26, v25, Length);
      }
      goto LABEL_51;
  }
  if ( v22 != 4 )
  {
    if ( v22 == 256 || v22 == 512 || v22 == 1024 )
      goto LABEL_41;
    return -1073741811;
  }
LABEL_31:
  if ( ULongFromUser >= 0 )
    goto LABEL_41;
  if ( (_DWORD)Length )
  {
    v23 = *(PVOID *)(v9 + 112);
    v24 = *(struct _IRP **)(v9 + 24);
    if ( *(_BYTE *)(v9 + 64) )
      RtlCopyFromUser(v24, v23, Length);
    else
      RtlCopyVolatileMemory(v24, v23, Length);
LABEL_41:
    if ( (_DWORD)Length )
    {
      if ( *(_BYTE *)(v9 + 64) )
        ProbeForWrite(*(volatile void **)(v9 + 112), Length, 1u);
      if ( !a4 || v22 != 1 )
        *(_DWORD *)(v9 + 16) |= 0x40u;
    }
  }
LABEL_51:
  v14 = *(_QWORD *)(v9 + 24);
  v8 = a2;
  Options = Size;
LABEL_53:
  v27 = v14 & -(__int64)((_DWORD)Length != 0);
  v28 = (char *)(v14 + v19);
  v29 = *(_DWORD *)(v14 + v19 + 20);
  v30 = v29 & 0x77FFFFFF;
  v31 = *(struct _LIST_ENTRY **)(v14 + v19);
  if ( v31 == *(struct _LIST_ENTRY **)&KSPROPSETID_Topology.Data1
    && *((_QWORD *)v28 + 1) == *(_QWORD *)KSPROPSETID_Topology.Data4 )
  {
    v30 = v29 & 0xEFFFFFFF;
  }
  if ( (v30 & 0x10000000) != 0 )
  {
    if ( Options < 0x20 )
      return -1073741306;
    if ( a6 )
    {
      v32 = *((unsigned int *)v28 + 6);
      if ( (unsigned int)v32 >= a7 )
        return -1073741808;
      v33 = *(int **)(a6 + 8 * v32);
      if ( !v33 )
        return -1073741275;
      v8 = *v33;
      if ( !*v33 )
        return -1073741275;
      v7 = (struct _LIST_ENTRY *)*((_QWORD *)v33 + 1);
      a5 = v33[1];
    }
    v30 = v29 & 0x67FFFFFF;
  }
  v34 = 72;
  if ( a5 )
    v34 = a5;
  v35 = v8;
  v36 = 40;
  if ( !v8 )
  {
LABEL_73:
    if ( !v35 )
    {
      if ( *(_QWORD *)v28 != *(_QWORD *)&GUID_NULL.Data1 || *((_QWORD *)v28 + 1) != *(_QWORD *)GUID_NULL.Data4 )
        return -1073741264;
      if ( !*((_DWORD *)v28 + 4) && v30 == 256 )
      {
        if ( !(_DWORD)Length )
        {
          *(_QWORD *)(v9 + 56) = 16LL * v8;
          return -2147483643;
        }
        if ( (_DWORD)Length == 4 )
        {
          **(_DWORD **)(v9 + 24) = 16 * v8;
          goto LABEL_114;
        }
        v64 = 16LL * v8;
        if ( Length >= v64 )
        {
          *(_QWORD *)(v9 + 56) = v64;
          for ( i = (_OWORD **)v7 - 5 * v8; v8; --v8 )
          {
            *(_OWORD *)v27 = **i;
            v27 += 16;
            i += 5;
          }
          return 0;
        }
        return -1073741789;
      }
      return -1073741811;
    }
    return -1073741275;
  }
  while ( 1 )
  {
    if ( !v7 )
      goto LABEL_73;
    if ( v31 == v7->Flink->Flink )
    {
      v37 = (struct _LIST_ENTRY *)*((_QWORD *)v28 + 1);
      if ( v37 == v7->Flink->Blink )
        break;
    }
    v7 = (struct _LIST_ENTRY *)((char *)v7 + 40);
    if ( !--v35 )
      goto LABEL_73;
  }
  if ( (v30 & 0xFFF00) == 0 )
  {
    PropertyItem = FindPropertyItem(v7, v34, *((unsigned int *)v28 + 4), 0xFFFFFFFFLL);
    if ( PropertyItem )
    {
      if ( Size < *(_DWORD *)(PropertyItem + 16) )
        return -1073741789;
      v63 = *(unsigned int *)(PropertyItem + 20);
      if ( (unsigned int)Length < (unsigned int)v63 )
      {
        if ( v30 == 4 && !(_DWORD)Length )
        {
          *(_QWORD *)(v9 + 56) = v63;
          result = -2147483643;
          *(_DWORD *)(v9 + 48) = -2147483643;
          return result;
        }
        return -1073741789;
      }
      *(_QWORD *)(v9 + 120) = v7;
      if ( a5 )
        *(_QWORD *)(v9 + 144) = PropertyItem;
      if ( v30 == 1 || v30 == 4 )
      {
        if ( *(_QWORD *)(PropertyItem + 8) )
        {
          *(_QWORD *)(v9 + 56) = *(unsigned int *)(PropertyItem + 20);
          return (*(__int64 (__fastcall **)(__int64, char *, __int64))(PropertyItem + 8))(v9, v28, v27);
        }
      }
      else
      {
        v44 = *(__int64 (__fastcall **)(__int64, char *, __int64))(PropertyItem + 24);
        if ( v44 )
          return v44(v9, v28, v27);
      }
    }
    goto LABEL_73;
  }
  switch ( v30 )
  {
    case 0x100u:
      return 0;
    case 0x200u:
      goto LABEL_88;
    case 0x800u:
      if ( v31 != *(struct _LIST_ENTRY **)&KSPROPSETID_DrmAudioStream.Data1
        || v37 != *(struct _LIST_ENTRY **)KSPROPSETID_DrmAudioStream.Data4 )
      {
        return SerializePropertySet(v9, v28, v7, (unsigned int)v34);
      }
      return -1073741811;
    case 0x1000u:
      if ( v31 != *(struct _LIST_ENTRY **)&KSPROPSETID_DrmAudioStream.Data1
        || v37 != *(struct _LIST_ENTRY **)KSPROPSETID_DrmAudioStream.Data4 )
      {
        return UnserializePropertySet(v9, v28, v7, 0xFFFFFFFFLL);
      }
      return -1073741811;
  }
  if ( ((v30 - 0x2000) & 0xFFFFDFFF) == 0 )
  {
    v43 = FindPropertyItem(v7, v34, *((unsigned int *)v28 + 4), 0xFFFFFFFFLL);
    if ( !v43 )
      return -1073741275;
    if ( *(_QWORD *)(v43 + 56) )
    {
      *(_QWORD *)(v9 + 120) = v7;
      if ( a5 )
        *(_QWORD *)(v9 + 144) = v43;
      v44 = *(__int64 (__fastcall **)(__int64, char *, __int64))(v43 + 56);
      return v44(v9, v28, v27);
    }
    return -1073741811;
  }
  if ( v30 == 0x8000 )
  {
    v38 = (unsigned int)Length < 4;
    goto LABEL_90;
  }
  if ( v30 != 0x10000 )
    goto LABEL_91;
LABEL_88:
  if ( (_DWORD)Length == 4 )
    goto LABEL_91;
  v38 = (unsigned int)Length < 0x28;
LABEL_90:
  if ( v38 )
    return -1073741789;
LABEL_91:
  v39 = FindPropertyItem(v7, v34, *((unsigned int *)v28 + 4), 0xFFFFFFFFLL);
  v41 = v39;
  if ( !v39 )
    return -1073741275;
  *(_QWORD *)(v9 + 120) = v7;
  if ( a5 )
    *(_QWORD *)(v9 + 144) = v39;
  v42 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(v39 + 56);
  if ( !v42 || (result = v42(v9, v40, v27), result == 263) || result == -1073741802 )
  {
    if ( v30 == 1024 )
      return KsHandleSizedListQuery((PIRP)v9, *(_DWORD *)(v41 + 40), 0x18u, *(const void **)(v41 + 48));
    if ( v30 == 0x8000 )
    {
      *(_DWORD *)v27 = *(_DWORD *)(v41 + 64);
LABEL_114:
      *(_QWORD *)(v9 + 56) = 4;
      return 0;
    }
    v45 = (*(_QWORD *)(v41 + 8) != 0) | 2;
    if ( !*(_QWORD *)(v41 + 24) )
      v45 = *(_QWORD *)(v41 + 8) != 0;
    *(_DWORD *)v27 = v45;
    if ( (unsigned int)Length < 0x28 )
    {
      v36 = 4;
      v61 = v9;
      v9 = 56;
      goto LABEL_148;
    }
    *(_DWORD *)(v27 + 36) = 0;
    v46 = *(_QWORD *)(v41 + 32);
    if ( !v46 )
    {
      *(_DWORD *)(v27 + 4) = 40;
      *(GUID *)(v27 + 8) = GUID_NULL;
      *(_QWORD *)(v27 + 24) = 0;
      *(_DWORD *)(v27 + 32) = 0;
LABEL_146:
      v61 = 56;
LABEL_148:
      *(_QWORD *)(v9 + v61) = v36;
      return 0;
    }
    v47 = 0;
    v48 = 40;
    v49 = *(_DWORD *)(v46 + 24);
    v50 = *(unsigned int **)(v46 + 32);
    if ( v49 )
    {
      while ( 1 )
      {
        if ( (v50[3] & 1) != 0 )
          v51 = v30 == 0x10000;
        else
          v51 = v30 == 512;
        if ( v51 )
        {
          v52 = v48 + 16;
          if ( v48 + 16 < v48 )
            return -1073741811;
          v53 = v50[1] * (unsigned __int64)v50[2];
          if ( v53 > 0xFFFFFFFF )
            return -1073741811;
          v48 = v53 + v52;
          if ( (unsigned int)v53 + v52 < v52 )
            return -1073741811;
          ++v47;
        }
        if ( !--v49 )
          break;
        v50 += 6;
      }
    }
    *(_DWORD *)(v27 + 4) = v48;
    v54 = *(_QWORD *)(v41 + 32);
    *(_OWORD *)(v27 + 8) = *(_OWORD *)v54;
    *(_QWORD *)(v27 + 24) = *(_QWORD *)(v54 + 16);
    *(_DWORD *)(v27 + 32) = v47;
    if ( Size_4 == 40 )
      goto LABEL_146;
    if ( Size_4 >= v48 )
    {
      v55 = (_OWORD *)(v27 + 40);
      v56 = *(_QWORD *)(v41 + 32);
      v57 = *(_QWORD *)(v56 + 32);
      v58 = *(_DWORD *)(v56 + 24);
      if ( v30 == 512 )
      {
        for ( ; v58; --v58 )
        {
          if ( (*(_DWORD *)(v57 + 12) & 1) == 0 )
          {
            *v55 = *(_OWORD *)v57;
            v60 = v55 + 1;
            memmove(v55 + 1, *(const void **)(v57 + 16), (unsigned int)(*(_DWORD *)(v57 + 8) * *(_DWORD *)(v57 + 4)));
            v55 = (_OWORD *)((char *)v60 + (unsigned int)(*(_DWORD *)(v57 + 8) * *(_DWORD *)(v57 + 4)));
          }
          v57 += 24;
        }
      }
      else
      {
        for ( ; v58; --v58 )
        {
          if ( (*(_DWORD *)(v57 + 12) & 1) != 0 && v30 == 0x10000 )
          {
            *v55 = *(_OWORD *)v57;
            v59 = v55 + 1;
            memmove(v55 + 1, *(const void **)(v57 + 16), (unsigned int)(*(_DWORD *)(v57 + 4) * *(_DWORD *)(v57 + 8)));
            v55 = (_OWORD *)((char *)v59 + (unsigned int)(*(_DWORD *)(v57 + 4) * *(_DWORD *)(v57 + 8)));
          }
          v57 += 24;
        }
      }
      v36 = v48;
      goto LABEL_146;
    }
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x18004a048  mov     [rsp+arg_18], r9
0x18004a04d  mov     [rsp+arg_8], edx
0x18004a051  mov     [rsp+arg_0], rcx
0x18004a056  push    rbx
0x18004a057  push    rsi
0x18004a058  push    rdi
0x18004a059  push    r12
0x18004a05b  push    r13
0x18004a05d  push    r14
0x18004a05f  push    r15
0x18004a061  sub     rsp, 30h
0x18004a065  mov     r12, r8
0x18004a068  mov     r11d, edx
0x18004a06b  mov     rdi, rcx
0x18004a06e  mov     r14, [rcx+0B8h]
0x18004a075  mov     r9d, [r14+10h]
0x18004a079  mov     dword ptr [rsp+68h+Size], r9d
0x18004a07e  mov     r13d, [r14+8]
0x18004a082  mov     dword ptr [rsp+68h+Size+4], r13d
0x18004a087  lea     ebx, [r13+7]
0x18004a08b  and     ebx, 0FFFFFFF8h
0x18004a08e  mov     rcx, [rcx+18h]
0x18004a092  test    rcx, rcx
0x18004a095  jnz     loc_18004A2C5
0x18004a09b  cmp     r9d, 18h
0x18004a09f  jb      loc_18004A313
0x18004a0a5  cmp     ebx, r13d
0x18004a0a8  jb      loc_18004A313
0x18004a0ae  lea     r15d, [rbx+r9]
0x18004a0b2  cmp     r15d, ebx
0x18004a0b5  jb      loc_18004A313
0x18004a0bb  cmp     [rdi+40h], cl
0x18004a0be  jz      short loc_18004A0D7
0x18004a0c0  mov     edx, r9d; Length
0x18004a0c3  lea     r8d, [rcx+1]; Alignment
0x18004a0c7  mov     rcx, [r14+20h]; Address
0x18004a0cb  call    cs:__imp_ProbeForRead
0x18004a0d2  nop     dword ptr [rax+rax+00h]
0x18004a0d7  mov     rax, [r14+20h]
0x18004a0db  cmp     byte ptr [rdi+40h], 0
0x18004a0df  jz      short loc_18004A0EE
0x18004a0e1  lea     rcx, [rax+14h]
0x18004a0e5  call    RtlReadULongFromUser
0x18004a0ea  mov     esi, eax
0x18004a0ec  jmp     short loc_18004A0F1
0x18004a0ee  mov     esi, [rax+14h]
0x18004a0f1  mov     rax, [rsp+68h+arg_18]
0x18004a0f9  test    rax, rax
0x18004a0fc  jz      short loc_18004A12B
0x18004a0fe  test    sil, 3
0x18004a102  jz      short loc_18004A12B
0x18004a104  test    r13d, r13d
0x18004a107  jz      short loc_18004A114
0x18004a109  test    sil, 1
0x18004a10d  jz      short loc_18004A114
0x18004a10f  mov     r8b, 1
0x18004a112  jmp     short loc_18004A117
0x18004a114  xor     r8d, r8d
0x18004a117  mov     edx, r15d
0x18004a11a  mov     rcx, rdi
0x18004a11d  call    _guard_dispatch_icall
0x18004a122  test    eax, eax
0x18004a124  jns     short loc_18004A14D
0x18004a126  jmp     loc_18004A894
0x18004a12b  mov     edx, r15d
0x18004a12e  mov     ecx, 63h ; 'c'
0x18004a133  mov     r8d, 7070534Bh
0x18004a139  call    cs:__imp_ExAllocatePool2
0x18004a140  nop     dword ptr [rax+rax+00h]
0x18004a145  mov     [rdi+18h], rax
0x18004a149  or      dword ptr [rdi+10h], 30h
0x18004a14d  mov     r15d, ebx
0x18004a150  mov     r8d, ebx; Size
0x18004a153  xor     edx, edx; Val
0x18004a155  mov     rcx, [rdi+18h]; void *
0x18004a159  call    memset
0x18004a15e  mov     rdx, [r14+20h]; Src
0x18004a162  mov     rcx, [rdi+18h]
0x18004a166  add     rcx, r15; void *
0x18004a169  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18004a16e  cmp     byte ptr [rdi+40h], 0
0x18004a172  jz      short loc_18004A17B
0x18004a174  call    RtlCopyFromUser
0x18004a179  jmp     short loc_18004A180
0x18004a17b  call    RtlCopyVolatileMemory
0x18004a180  mov     rax, [rdi+18h]
0x18004a184  mov     [rax+rbx+14h], esi
0x18004a188  mov     ebx, esi
0x18004a18a  and     ebx, 67FFFFFFh
0x18004a190  mov     eax, 800h
0x18004a195  cmp     ebx, eax
0x18004a197  ja      short loc_18004A1F7
0x18004a199  jz      loc_18004A226
0x18004a19f  mov     eax, ebx
0x18004a1a1  sub     eax, 1
0x18004a1a4  jz      short loc_18004A1CB
0x18004a1a6  sub     eax, 1
0x18004a1a9  jz      loc_18004A260
0x18004a1af  sub     eax, 2
0x18004a1b2  jz      short loc_18004A1CB
0x18004a1b4  sub     eax, 0FCh
0x18004a1b9  jz      short loc_18004A226
0x18004a1bb  sub     eax, 100h
0x18004a1c0  jz      short loc_18004A226
0x18004a1c2  cmp     eax, 200h
0x18004a1c7  jnz     short loc_18004A21C
0x18004a1c9  jmp     short loc_18004A226
0x18004a1cb  test    esi, esi
0x18004a1cd  jns     short loc_18004A226
0x18004a1cf  test    r13d, r13d
0x18004a1d2  jz      loc_18004A282
0x18004a1d8  mov     rdx, [rdi+70h]; Src
0x18004a1dc  mov     rcx, [rdi+18h]; void *
0x18004a1e0  mov     r8, r13; Size
0x18004a1e3  cmp     byte ptr [rdi+40h], 0
0x18004a1e7  jz      short loc_18004A1F0
0x18004a1e9  call    RtlCopyFromUser
0x18004a1ee  jmp     short loc_18004A226
0x18004a1f0  call    RtlCopyVolatileMemory
0x18004a1f5  jmp     short loc_18004A226
0x18004a1f7  cmp     ebx, 1000h
0x18004a1fd  jz      short loc_18004A260
0x18004a1ff  cmp     ebx, 2000h
0x18004a205  jz      short loc_18004A226
0x18004a207  cmp     ebx, 4000h
0x18004a20d  jz      short loc_18004A260
0x18004a20f  lea     eax, [rbx-8000h]
0x18004a215  test    eax, 0FFFF7FFFh
0x18004a21a  jz      short loc_18004A226
0x18004a21c  mov     eax, 0C000000Dh
0x18004a221  jmp     loc_18004A894
0x18004a226  test    r13d, r13d
0x18004a229  jz      short loc_18004A282
0x18004a22b  cmp     byte ptr [rdi+40h], 0
0x18004a22f  jz      short loc_18004A24A
0x18004a231  mov     rdx, r13; Length
0x18004a234  mov     r8d, 1; Alignment
0x18004a23a  mov     rcx, [rdi+70h]; Address
0x18004a23e  call    cs:__imp_ProbeForWrite
0x18004a245  nop     dword ptr [rax+rax+00h]
0x18004a24a  cmp     [rsp+68h+arg_18], 0
0x18004a253  jz      short loc_18004A25A
0x18004a255  cmp     ebx, 1
0x18004a258  jz      short loc_18004A282
0x18004a25a  or      dword ptr [rdi+10h], 40h
0x18004a25e  jmp     short loc_18004A282
0x18004a260  test    r13d, r13d
0x18004a263  jz      short loc_18004A282
0x18004a265  mov     rdx, [rdi+70h]; Src
0x18004a269  mov     rcx, [rdi+18h]; void *
0x18004a26d  mov     r8, r13; Size
0x18004a270  cmp     byte ptr [rdi+40h], 0
0x18004a274  jz      short loc_18004A27D
0x18004a276  call    RtlCopyFromUser
0x18004a27b  jmp     short loc_18004A282
0x18004a27d  call    RtlCopyVolatileMemory
0x18004a282  mov     rcx, [rdi+18h]
0x18004a286  mov     r11d, [rsp+68h+arg_8]
0x18004a28b  mov     r9d, dword ptr [rsp+68h+Size]
0x18004a290  jmp     short loc_18004A2C8
0x18004a292  mov     edi, eax
0x18004a294  mov     rbx, [rsp+68h+arg_0]
0x18004a299  cmp     qword ptr [rbx+18h], 0
0x18004a29e  jz      short loc_18004A2BE
0x18004a2a0  xor     edx, edx; Tag
0x18004a2a2  mov     rcx, [rbx+18h]; P
0x18004a2a6  call    cs:__imp_ExFreePoolWithTag
0x18004a2ad  nop     dword ptr [rax+rax+00h]
0x18004a2b2  mov     qword ptr [rbx+18h], 0
0x18004a2ba  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004a2be  mov     eax, edi
0x18004a2c0  jmp     loc_18004A894
0x18004a2c5  mov     r15d, ebx
0x18004a2c8  mov     eax, r13d
0x18004a2cb  neg     eax
0x18004a2cd  sbb     rbx, rbx
0x18004a2d0  and     rbx, rcx
0x18004a2d3  lea     r10, [rcx+r15]
0x18004a2d7  mov     edx, [r10+14h]
0x18004a2db  mov     r14d, edx
0x18004a2de  and     r14d, 77FFFFFFh
0x18004a2e5  mov     r8, [r10]
0x18004a2e8  cmp     r8, qword ptr cs:KSPROPSETID_Topology.Data1
0x18004a2ef  jnz     short loc_18004A306
0x18004a2f1  mov     rax, qword ptr cs:KSPROPSETID_Topology.Data4
0x18004a2f8  cmp     [r10+8], rax
0x18004a2fc  jnz     short loc_18004A306
0x18004a2fe  mov     r14d, edx
0x18004a301  btr     r14d, 1Ch
0x18004a306  bt      r14d, 1Ch
0x18004a30b  jnb     short loc_18004A372
0x18004a30d  cmp     r9d, 20h ; ' '
0x18004a311  jnb     short loc_18004A31D
0x18004a313  mov     eax, 0C0000206h
0x18004a318  jmp     loc_18004A894
0x18004a31d  mov     rcx, [rsp+68h+arg_28]
0x18004a325  test    rcx, rcx
0x18004a328  jz      short loc_18004A368
0x18004a32a  mov     eax, [r10+18h]
0x18004a32e  cmp     eax, [rsp+68h+arg_30]
0x18004a335  jb      short loc_18004A341
0x18004a337  mov     eax, 0C0000010h
0x18004a33c  jmp     loc_18004A894
0x18004a341  mov     rax, [rcx+rax*8]
0x18004a345  test    rax, rax
0x18004a348  jz      loc_18004A88F
0x18004a34e  mov     r11d, [rax]
0x18004a351  test    r11d, r11d
0x18004a354  jz      loc_18004A88F
0x18004a35a  mov     r12, [rax+8]
0x18004a35e  mov     eax, [rax+4]
0x18004a361  mov     [rsp+68h+arg_20], eax
0x18004a368  mov     r14d, edx
0x18004a36b  and     r14d, 67FFFFFFh
0x18004a372  mov     edx, 48h ; 'H'
0x18004a377  mov     eax, [rsp+68h+arg_20]
0x18004a37e  test    eax, eax
0x18004a380  cmovnz  edx, eax
0x18004a383  mov     esi, r11d
0x18004a386  mov     r15d, 28h ; '('
0x18004a38c  test    r11d, r11d
0x18004a38f  jz      short loc_18004A3B7
0x18004a391  mov     r9d, 0FFFFFFFFh
0x18004a397  test    r12, r12
0x18004a39a  jz      short loc_18004A3B7
0x18004a39c  mov     rax, [r12]
0x18004a3a0  cmp     r8, [rax]
0x18004a3a3  jnz     short loc_18004A3AF
0x18004a3a5  mov     rcx, [r10+8]
0x18004a3a9  cmp     rcx, [rax+8]
0x18004a3ad  jz      short loc_18004A41B
0x18004a3af  add     r12, r15
0x18004a3b2  add     esi, r9d
0x18004a3b5  jnz     short loc_18004A397
0x18004a3b7  mov     r8d, 0FFFFFFFFh
0x18004a3bd  test    esi, esi
0x18004a3bf  jnz     loc_18004A88F
0x18004a3c5  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18004a3cc  cmp     [r10], rax
0x18004a3cf  jnz     loc_18004A888
0x18004a3d5  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18004a3dc  cmp     [r10+8], rax
0x18004a3e0  jnz     loc_18004A888
0x18004a3e6  cmp     [r10+10h], esi
0x18004a3ea  jnz     loc_18004A881
0x18004a3f0  cmp     r14d, 100h
0x18004a3f7  jnz     loc_18004A881
0x18004a3fd  test    r13d, r13d
0x18004a400  jnz     loc_18004A825
0x18004a406  mov     eax, r11d
0x18004a409  shl     rax, 4
0x18004a40d  mov     [rdi+38h], rax
0x18004a411  mov     eax, 80000005h
0x18004a416  jmp     loc_18004A894
0x18004a41b  test    r14d, 0FFF00h
0x18004a422  jz      loc_18004A786
0x18004a428  cmp     r14d, 100h
0x18004a42f  jz      loc_18004A5CC
0x18004a435  cmp     r14d, 200h
0x18004a43c  jz      short loc_18004A480
0x18004a43e  cmp     r14d, 800h
0x18004a445  jz      loc_18004A58A
0x18004a44b  cmp     r14d, 1000h
0x18004a452  jz      loc_18004A561
0x18004a458  lea     eax, [r14-2000h]
0x18004a45f  test    eax, 0FFFFDFFFh
0x18004a464  jz      loc_18004A515
0x18004a46a  cmp     r14d, 8000h
0x18004a471  jz      loc_18004A50C
0x18004a477  cmp     r14d, 10000h
0x18004a47e  jnz     short loc_18004A48F
0x18004a480  cmp     r13d, 4
0x18004a484  jz      short loc_18004A48F
0x18004a486  cmp     r13d, r15d
0x18004a489  jb      loc_18004A84A
0x18004a48f  mov     r8d, [r10+10h]
0x18004a493  mov     rcx, r12
0x18004a496  call    FindPropertyItem
0x18004a49b  mov     rsi, rax
0x18004a49e  test    rax, rax
0x18004a4a1  jz      loc_18004A88F
0x18004a4a7  mov     [rdi+78h], r12
0x18004a4ab  cmp     [rsp+68h+arg_20], 0
0x18004a4b3  jz      short loc_18004A4BC
0x18004a4b5  mov     [rdi+90h], rax
0x18004a4bc  mov     rax, [rax+38h]
0x18004a4c0  test    rax, rax
0x18004a4c3  jz      short loc_18004A4E5
0x18004a4c5  mov     r8, rbx
0x18004a4c8  mov     rdx, r10
0x18004a4cb  mov     rcx, rdi
0x18004a4ce  call    _guard_dispatch_icall
0x18004a4d3  cmp     eax, 107h
0x18004a4d8  jz      short loc_18004A4E5
0x18004a4da  cmp     eax, 0C0000016h
0x18004a4df  jnz     loc_18004A894
0x18004a4e5  cmp     r14d, 400h
0x18004a4ec  jnz     loc_18004A5B6
0x18004a4f2  mov     r9, [rsi+30h]; DataItems
0x18004a4f6  mov     r8d, 18h; DataItemSize
  ... truncated ...
```
