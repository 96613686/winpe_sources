# KspPropertyHandler

- ea: `0x18004a048`
- end: `0x18004a957`
- name: `KspPropertyHandler`
- size: `2319`
- prototype: `NTSTATUS __fastcall(__int64 Irp, unsigned int, struct _LIST_ENTRY *, __int64 (__fastcall *)(__int64, _QWORD, __int64), unsigned int, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1800339a0`
- `0x180036f10`
- `0x180038ea0`
- `0x180049bf0`
- `0x180049c20`

## callees

- `0x180010154`
- `0x180010804`
- `0x180019c00`
- `0x180019cb0`
- `0x180019d00`
- `0x18001a000`
- `0x1800337b8`
- `0x180038edc`
- `0x1800391d8`
- `0x18004a048`
- `0x18004bbe0`
- `0x18004d5d0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x18004a0c4`
- `ntoskrnl!ProbeForRead` at `0x18004a245`
- `ntoskrnl!ProbeForRead` at `0x18004a315`
- `ntoskrnl!ProbeForRead` at `0x18004a0c4`
- `ntoskrnl!ProbeForRead` at `0x18004a245`
- `ntoskrnl!ProbeForRead` at `0x18004a315`
- `ntoskrnl!ProbeForWrite` at `0x18004a2b1`
- `ntoskrnl!ProbeForWrite` at `0x18004a2b1`
- `ntoskrnl!ExAllocatePool2` at `0x18004a13d`
- `ntoskrnl!ExAllocatePool2` at `0x18004a13d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004a350`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004a350`

## pseudocode

```c
NTSTATUS __fastcall KspPropertyHandler(
        __int64 Irp,
        unsigned int a2,
        struct _LIST_ENTRY *a3,
        __int64 (__fastcall *a4)(__int64, _QWORD, __int64),
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 v8; // rdi
  struct _IO_STACK_LOCATION *v9; // rsi
  unsigned int Options; // r9d
  size_t Length; // r12
  unsigned int v12; // ebx
  unsigned __int64 v13; // rcx
  unsigned int v14; // r15d
  __int64 v15; // r8
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  int OutboundQuota; // r14d
  NTSTATUS result; // eax
  __int64 v19; // r15
  int IsEnabledDeviceUsageNoInline; // eax
  PNAMED_PIPE_CREATE_PARAMETERS v21; // rdx
  char *v22; // rcx
  int v23; // ebx
  int v24; // eax
  KPROCESSOR_MODE v25; // r9
  PVOID v26; // rdx
  struct _IRP *v27; // rcx
  int v28; // eax
  KPROCESSOR_MODE v29; // r9
  PVOID v30; // rdx
  struct _IRP *v31; // rcx
  __int64 v32; // rbx
  char *v33; // r10
  int v34; // edx
  unsigned int v35; // r14d
  struct _LIST_ENTRY *v36; // r8
  __int64 v37; // rax
  int *v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // esi
  unsigned int v41; // r11d
  __int64 v42; // r15
  struct _LIST_ENTRY *v43; // rcx
  bool v44; // cf
  __int64 v45; // rax
  __int64 v46; // r10
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, __int64, __int64); // rax
  __int64 v49; // rax
  __int64 (__fastcall *v50)(__int64, char *, __int64); // rax
  int v51; // ecx
  __int64 v52; // rcx
  int v53; // edx
  unsigned int v54; // r13d
  int v55; // r10d
  unsigned int *v56; // rcx
  bool v57; // zf
  unsigned int v58; // r9d
  unsigned __int64 v59; // r8
  __int64 v60; // rax
  _OWORD *v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rsi
  int v64; // r15d
  _OWORD *v65; // rbx
  _OWORD *v66; // rbx
  __int64 v67; // rax
  __int64 PropertyItem; // rdx
  ULONG_PTR v69; // rax
  _OWORD **v70; // r13
  unsigned int Size; // [rsp+20h] [rbp-48h]

  v8 = Irp;
  v9 = *(struct _IO_STACK_LOCATION **)(Irp + 184);
  Options = v9->Parameters.Create.Options;
  Size = Options;
  Length = v9->Parameters.Read.Length;
  v12 = (Length + 7) & 0xFFFFFFF8;
  v13 = *(_QWORD *)(Irp + 24);
  if ( v13 )
  {
    v19 = v12;
    goto LABEL_65;
  }
  if ( Options < 0x18 )
    return -1073741306;
  if ( v12 < (unsigned int)Length )
    return -1073741306;
  v14 = v12 + Options;
  if ( v12 + Options < v12 )
    return -1073741306;
  if ( *(_BYTE *)(v8 + 64) )
    ProbeForRead(v9->Parameters.CreatePipe.Parameters, Options, 1u);
  v57 = (unsigned int)Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline() == 0;
  Parameters = v9->Parameters.CreatePipe.Parameters;
  if ( v57 || !*(_BYTE *)(v8 + 64) )
    OutboundQuota = Parameters->OutboundQuota;
  else
    OutboundQuota = RtlReadULongFromUser(&Parameters->OutboundQuota);
  if ( a4 && (OutboundQuota & 3) != 0 )
  {
    if ( (_DWORD)Length && (OutboundQuota & 1) != 0 )
      LOBYTE(v15) = 1;
    else
      v15 = 0;
    result = a4(v8, v14, v15);
    if ( result < 0 )
      return result;
  }
  else
  {
    *(_QWORD *)(v8 + 24) = ExAllocatePool2(99, v14, 1886409547);
    *(_DWORD *)(v8 + 16) |= 0x30u;
  }
  v19 = v12;
  memset(*(void **)(v8 + 24), 0, v12);
  IsEnabledDeviceUsageNoInline = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
  v21 = v9->Parameters.CreatePipe.Parameters;
  v22 = (char *)(v12 + *(_QWORD *)(v8 + 24));
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( *(_BYTE *)(v8 + 64) )
      RtlCopyFromUser(v22, v21, Size);
    else
      RtlCopyVolatileMemory(v22, v21, Size);
  }
  else
  {
    memmove(v22, v21, Size);
  }
  *(_DWORD *)(*(_QWORD *)(v8 + 24) + v12 + 20LL) = OutboundQuota;
  v23 = OutboundQuota & 0x67FFFFFF;
  if ( (OutboundQuota & 0x67FFFFFFu) > 0x800 )
  {
    if ( v23 != 0x4000 && v23 != 4096 )
    {
      if ( v23 != 0x2000 && v23 != 0x8000 && v23 != 0x10000 )
        return -1073741811;
      goto LABEL_49;
    }
    goto LABEL_55;
  }
  switch ( v23 )
  {
    case 2048:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
LABEL_55:
      if ( (_DWORD)Length )
      {
        v28 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
        v29 = *(_BYTE *)(v8 + 64);
        if ( v28 )
        {
          v30 = *(PVOID *)(v8 + 112);
          v31 = *(struct _IRP **)(v8 + 24);
          if ( v29 )
            RtlCopyFromUser(v31, v30, Length);
          else
            RtlCopyVolatileMemory(v31, v30, Length);
        }
        else
        {
          if ( v29 )
            ProbeForRead(*(volatile void **)(v8 + 112), Length, 1u);
          memmove(*(void **)(v8 + 24), *(const void **)(v8 + 112), Length);
        }
      }
      goto LABEL_63;
  }
  if ( v23 != 4 )
  {
    if ( v23 != 256 && v23 != 512 && v23 != 1024 )
      return -1073741811;
    goto LABEL_49;
  }
LABEL_34:
  if ( OutboundQuota >= 0 )
  {
LABEL_49:
    if ( (_DWORD)Length )
    {
      if ( *(_BYTE *)(v8 + 64) )
        ProbeForWrite(*(volatile void **)(v8 + 112), Length, 1u);
      if ( !a4 || v23 != 1 )
        *(_DWORD *)(v8 + 16) |= 0x40u;
    }
    goto LABEL_63;
  }
  if ( (_DWORD)Length )
  {
    v24 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
    v25 = *(_BYTE *)(v8 + 64);
    if ( v24 )
    {
      v26 = *(PVOID *)(v8 + 112);
      v27 = *(struct _IRP **)(v8 + 24);
      if ( v25 )
        RtlCopyFromUser(v27, v26, Length);
      else
        RtlCopyVolatileMemory(v27, v26, Length);
    }
    else
    {
      if ( v25 )
        ProbeForRead(*(volatile void **)(v8 + 112), Length, 1u);
      memmove(*(void **)(v8 + 24), *(const void **)(v8 + 112), Length);
    }
    goto LABEL_49;
  }
LABEL_63:
  v13 = *(_QWORD *)(v8 + 24);
  Options = Size;
LABEL_65:
  v32 = v13 & -(__int64)((_DWORD)Length != 0);
  v33 = (char *)(v13 + v19);
  v34 = *(_DWORD *)(v13 + v19 + 20);
  v35 = v34 & 0x77FFFFFF;
  v36 = *(struct _LIST_ENTRY **)(v13 + v19);
  if ( v36 == *(struct _LIST_ENTRY **)&KSPROPSETID_Topology.Data1
    && *((_QWORD *)v33 + 1) == *(_QWORD *)KSPROPSETID_Topology.Data4 )
  {
    v35 = v34 & 0xEFFFFFFF;
  }
  if ( (v35 & 0x10000000) != 0 )
  {
    if ( Options < 0x20 )
      return -1073741306;
    if ( a6 )
    {
      v37 = *((unsigned int *)v33 + 6);
      if ( (unsigned int)v37 >= a7 )
        return -1073741808;
      v38 = *(int **)(a6 + 8 * v37);
      if ( !v38 )
        return -1073741275;
      a2 = *v38;
      if ( !*v38 )
        return -1073741275;
      a3 = (struct _LIST_ENTRY *)*((_QWORD *)v38 + 1);
      a5 = v38[1];
    }
    v35 = v34 & 0x67FFFFFF;
  }
  v39 = 72;
  if ( a5 )
    v39 = a5;
  v40 = a2;
  v41 = a2;
  v42 = 40;
  while ( 1 )
  {
    if ( !v41 )
      goto LABEL_169;
    if ( !a3 )
      goto LABEL_168;
    if ( v36 == a3->Flink->Flink )
    {
      v43 = (struct _LIST_ENTRY *)*((_QWORD *)v33 + 1);
      if ( v43 == a3->Flink->Blink )
        break;
    }
    a3 = (struct _LIST_ENTRY *)((char *)a3 + 40);
    --v41;
  }
  if ( (v35 & 0xFFF00) == 0 )
  {
    PropertyItem = FindPropertyItem(a3, v39);
    if ( PropertyItem )
    {
      if ( Size < *(_DWORD *)(PropertyItem + 16) )
        return -1073741789;
      v69 = *(unsigned int *)(PropertyItem + 20);
      if ( (unsigned int)Length < (unsigned int)v69 )
      {
        if ( v35 == 4 && !(_DWORD)Length )
        {
          *(_QWORD *)(v8 + 56) = v69;
          result = -2147483643;
          *(_DWORD *)(v8 + 48) = -2147483643;
          return result;
        }
        return -1073741789;
      }
      *(_QWORD *)(v8 + 120) = a3;
      if ( a5 )
        *(_QWORD *)(v8 + 144) = PropertyItem;
      if ( v35 == 1 || v35 == 4 )
      {
        if ( *(_QWORD *)(PropertyItem + 8) )
        {
          *(_QWORD *)(v8 + 56) = *(unsigned int *)(PropertyItem + 20);
          return (*(__int64 (__fastcall **)(__int64, char *, __int64))(PropertyItem + 8))(v8, v33, v32);
        }
      }
      else
      {
        v50 = *(__int64 (__fastcall **)(__int64, char *, __int64))(PropertyItem + 24);
        if ( v50 )
          return v50(v8, v33, v32);
      }
    }
LABEL_168:
    if ( !v41 )
    {
LABEL_169:
      if ( *(_QWORD *)v33 != *(_QWORD *)&GUID_NULL.Data1 || *((_QWORD *)v33 + 1) != *(_QWORD *)GUID_NULL.Data4 )
        return -1073741264;
      if ( !*((_DWORD *)v33 + 4) && v35 == 256 )
      {
        if ( !(_DWORD)Length )
        {
          *(_QWORD *)(v8 + 56) = 16LL * a2;
          return -2147483643;
        }
        if ( (_DWORD)Length == 4 )
        {
          **(_DWORD **)(v8 + 24) = 16 * a2;
          goto LABEL_121;
        }
        if ( Length >= 16 * (unsigned __int64)a2 )
        {
          *(_QWORD *)(v8 + 56) = 16LL * a2;
          v70 = (_OWORD **)a3 - 5 * a2;
          if ( a2 )
          {
            do
            {
              *(_OWORD *)v32 = **v70;
              v32 += 16;
              v70 += 5;
              --v40;
            }
            while ( v40 );
          }
          return 0;
        }
        return -1073741789;
      }
      return -1073741811;
    }
    return -1073741275;
  }
  switch ( v35 )
  {
    case 0x100u:
      return 0;
    case 0x200u:
      goto LABEL_95;
    case 0x800u:
      if ( v36 != *(struct _LIST_ENTRY **)&KSPROPSETID_DrmAudioStream.Data1
        || v43 != *(struct _LIST_ENTRY **)KSPROPSETID_DrmAudioStream.Data4 )
      {
        return SerializePropertySet(v8, v33, a3, (unsigned int)v39);
      }
      return -1073741811;
    case 0x1000u:
      if ( v36 != *(struct _LIST_ENTRY **)&KSPROPSETID_DrmAudioStream.Data1
        || v43 != *(struct _LIST_ENTRY **)KSPROPSETID_DrmAudioStream.Data4 )
      {
        return UnserializePropertySet(v8, v33, a3, 0xFFFFFFFFLL);
      }
      return -1073741811;
    case 0x2000u:
    case 0x4000u:
      v49 = FindPropertyItem(a3, v39);
      if ( !v49 )
        return -1073741275;
      if ( *(_QWORD *)(v49 + 56) )
      {
        *(_QWORD *)(v8 + 120) = a3;
        if ( a5 )
          *(_QWORD *)(v8 + 144) = v49;
        v50 = *(__int64 (__fastcall **)(__int64, char *, __int64))(v49 + 56);
        return v50(v8, v33, v32);
      }
      return -1073741811;
    case 0x8000u:
      v44 = (unsigned int)Length < 4;
      goto LABEL_97;
  }
  if ( v35 != 0x10000 )
    goto LABEL_98;
LABEL_95:
  if ( (_DWORD)Length == 4 )
    goto LABEL_98;
  v44 = (unsigned int)Length < 0x28;
LABEL_97:
  if ( v44 )
    return -1073741789;
LABEL_98:
  v45 = FindPropertyItem(a3, v39);
  v47 = v45;
  if ( !v45 )
    return -1073741275;
  *(_QWORD *)(v8 + 120) = a3;
  if ( a5 )
    *(_QWORD *)(v8 + 144) = v45;
  v48 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(v45 + 56);
  if ( !v48 || (result = v48(v8, v46, v32), result == -1073741802) || result == 263 )
  {
    if ( v35 == 1024 )
      return KsHandleSizedListQuery((PIRP)v8, *(_DWORD *)(v47 + 40), 0x18u, *(const void **)(v47 + 48));
    if ( v35 == 0x8000 )
    {
      *(_DWORD *)v32 = *(_DWORD *)(v47 + 64);
LABEL_121:
      *(_QWORD *)(v8 + 56) = 4;
      return 0;
    }
    v51 = (*(_QWORD *)(v47 + 8) != 0) | 2;
    if ( !*(_QWORD *)(v47 + 24) )
      v51 = *(_QWORD *)(v47 + 8) != 0;
    *(_DWORD *)v32 = v51;
    if ( (unsigned int)Length < 0x28 )
    {
      v42 = 4;
      v67 = v8;
      v8 = 56;
      goto LABEL_156;
    }
    *(_DWORD *)(v32 + 36) = 0;
    v52 = *(_QWORD *)(v47 + 32);
    if ( !v52 )
    {
      *(_DWORD *)(v32 + 4) = 40;
      *(GUID *)(v32 + 8) = GUID_NULL;
      *(_QWORD *)(v32 + 24) = 0;
      *(_DWORD *)(v32 + 32) = 0;
LABEL_154:
      v67 = 56;
LABEL_156:
      *(_QWORD *)(v8 + v67) = v42;
      return 0;
    }
    v53 = 0;
    v54 = 40;
    v55 = *(_DWORD *)(v52 + 24);
    v56 = *(unsigned int **)(v52 + 32);
    while ( v55 )
    {
      if ( (v56[3] & 1) != 0 )
        v57 = v35 == 0x10000;
      else
        v57 = v35 == 512;
      if ( v57 )
      {
        v58 = v54 + 16;
        if ( v54 + 16 < v54 )
          return -1073741811;
        v59 = v56[1] * (unsigned __int64)v56[2];
        if ( v59 > 0xFFFFFFFF )
          return -1073741811;
        v54 = v59 + v58;
        if ( (unsigned int)v59 + v58 < v58 )
          return -1073741811;
        ++v53;
      }
      --v55;
      v56 += 6;
    }
    *(_DWORD *)(v32 + 4) = v54;
    v60 = *(_QWORD *)(v47 + 32);
    *(_OWORD *)(v32 + 8) = *(_OWORD *)v60;
    *(_QWORD *)(v32 + 24) = *(_QWORD *)(v60 + 16);
    *(_DWORD *)(v32 + 32) = v53;
    if ( (_DWORD)Length == 40 )
      goto LABEL_154;
    if ( (unsigned int)Length >= v54 )
    {
      v61 = (_OWORD *)(v32 + 40);
      v62 = *(_QWORD *)(v47 + 32);
      v63 = *(_QWORD *)(v62 + 32);
      v64 = *(_DWORD *)(v62 + 24);
      if ( v35 == 512 )
      {
        if ( v64 )
        {
          do
          {
            if ( (*(_DWORD *)(v63 + 12) & 1) == 0 )
            {
              *v61 = *(_OWORD *)v63;
              v66 = v61 + 1;
              memmove(v61 + 1, *(const void **)(v63 + 16), (unsigned int)(*(_DWORD *)(v63 + 8) * *(_DWORD *)(v63 + 4)));
              v61 = (_OWORD *)((char *)v66 + (unsigned int)(*(_DWORD *)(v63 + 8) * *(_DWORD *)(v63 + 4)));
            }
            v63 += 24;
            --v64;
          }
          while ( v64 );
          goto LABEL_152;
        }
      }
      else if ( v64 )
      {
        do
        {
          if ( (*(_DWORD *)(v63 + 12) & 1) != 0 && v35 == 0x10000 )
          {
            *v61 = *(_OWORD *)v63;
            v65 = v61 + 1;
            memmove(v61 + 1, *(const void **)(v63 + 16), (unsigned int)(*(_DWORD *)(v63 + 4) * *(_DWORD *)(v63 + 8)));
            v61 = (_OWORD *)((char *)v65 + (unsigned int)(*(_DWORD *)(v63 + 4) * *(_DWORD *)(v63 + 8)));
          }
          v63 += 24;
          --v64;
        }
        while ( v64 );
LABEL_152:
        v8 = Irp;
      }
      v42 = v54;
      goto LABEL_154;
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
0x18004a065  mov     r13, r8
0x18004a068  mov     rdi, rcx
0x18004a06b  mov     rsi, [rcx+0B8h]
0x18004a072  mov     r9d, [rsi+10h]
0x18004a076  mov     [rsp+68h+Size], r9d
0x18004a07b  mov     r12d, [rsi+8]
0x18004a07f  lea     ebx, [r12+7]
0x18004a084  and     ebx, 0FFFFFFF8h
0x18004a087  mov     rcx, [rcx+18h]
0x18004a08b  test    rcx, rcx
0x18004a08e  jnz     loc_18004A36F
0x18004a094  cmp     r9d, 18h
0x18004a098  jb      loc_18004A3BD
0x18004a09e  cmp     ebx, r12d
0x18004a0a1  jb      loc_18004A3BD
0x18004a0a7  lea     r15d, [rbx+r9]
0x18004a0ab  cmp     r15d, ebx
0x18004a0ae  jb      loc_18004A3BD
0x18004a0b4  cmp     [rdi+40h], cl
0x18004a0b7  jz      short loc_18004A0D0
0x18004a0b9  mov     edx, r9d; Length
0x18004a0bc  lea     r8d, [rcx+1]; Alignment
0x18004a0c0  mov     rcx, [rsi+20h]; Address
0x18004a0c4  call    cs:__imp_ProbeForRead
0x18004a0cb  nop     dword ptr [rax+rax+00h]
0x18004a0d0  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004a0d5  test    eax, eax
0x18004a0d7  mov     rax, [rsi+20h]
0x18004a0db  jz      short loc_18004A0F1
0x18004a0dd  cmp     byte ptr [rdi+40h], 0
0x18004a0e1  jz      short loc_18004A0F1
0x18004a0e3  lea     rcx, [rax+14h]
0x18004a0e7  call    RtlReadULongFromUser
0x18004a0ec  mov     r14d, eax
0x18004a0ef  jmp     short loc_18004A0F5
0x18004a0f1  mov     r14d, [rax+14h]
0x18004a0f5  mov     rax, [rsp+68h+arg_18]
0x18004a0fd  test    rax, rax
0x18004a100  jz      short loc_18004A12F
0x18004a102  test    r14b, 3
0x18004a106  jz      short loc_18004A12F
0x18004a108  test    r12d, r12d
0x18004a10b  jz      short loc_18004A118
0x18004a10d  test    r14b, 1
0x18004a111  jz      short loc_18004A118
0x18004a113  mov     r8b, 1
0x18004a116  jmp     short loc_18004A11B
0x18004a118  xor     r8d, r8d
0x18004a11b  mov     edx, r15d
0x18004a11e  mov     rcx, rdi
0x18004a121  call    _guard_dispatch_icall
0x18004a126  test    eax, eax
0x18004a128  jns     short loc_18004A151
0x18004a12a  jmp     loc_18004A946
0x18004a12f  mov     edx, r15d
0x18004a132  mov     ecx, 63h ; 'c'
0x18004a137  mov     r8d, 7070534Bh
0x18004a13d  call    cs:__imp_ExAllocatePool2
0x18004a144  nop     dword ptr [rax+rax+00h]
0x18004a149  mov     [rdi+18h], rax
0x18004a14d  or      dword ptr [rdi+10h], 30h
0x18004a151  mov     r15d, ebx
0x18004a154  mov     r8d, ebx; Size
0x18004a157  xor     edx, edx; Val
0x18004a159  mov     rcx, [rdi+18h]; void *
0x18004a15d  call    memset
0x18004a162  mov     ebx, [rsp+68h+Size]
0x18004a166  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004a16b  mov     rdx, [rsi+20h]; Src
0x18004a16f  mov     rcx, [rdi+18h]
0x18004a173  add     rcx, r15; void *
0x18004a176  mov     r8d, ebx; Size
0x18004a179  test    eax, eax
0x18004a17b  jz      short loc_18004A191
0x18004a17d  cmp     byte ptr [rdi+40h], 0
0x18004a181  jz      short loc_18004A18A
0x18004a183  call    RtlCopyFromUser
0x18004a188  jmp     short loc_18004A196
0x18004a18a  call    RtlCopyVolatileMemory
0x18004a18f  jmp     short loc_18004A196
0x18004a191  call    memmove
0x18004a196  mov     rax, [rdi+18h]
0x18004a19a  mov     [rax+r15+14h], r14d
0x18004a19f  mov     ebx, r14d
0x18004a1a2  and     ebx, 67FFFFFFh
0x18004a1a8  mov     esi, 800h
0x18004a1ad  cmp     ebx, esi
0x18004a1af  ja      loc_18004A263
0x18004a1b5  jz      loc_18004A295
0x18004a1bb  mov     eax, ebx
0x18004a1bd  sub     eax, 1
0x18004a1c0  jz      short loc_18004A1F6
0x18004a1c2  sub     eax, 1
0x18004a1c5  jz      loc_18004A2D3
0x18004a1cb  sub     eax, 2
0x18004a1ce  jz      short loc_18004A1F6
0x18004a1d0  sub     eax, 0FCh
0x18004a1d5  jz      loc_18004A295
0x18004a1db  sub     eax, 100h
0x18004a1e0  jz      loc_18004A295
0x18004a1e6  cmp     eax, 200h
0x18004a1eb  jz      loc_18004A295
0x18004a1f1  jmp     loc_18004A28B
0x18004a1f6  test    r14d, r14d
0x18004a1f9  jns     loc_18004A295
0x18004a1ff  test    r12d, r12d
0x18004a202  jz      loc_18004A331
0x18004a208  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004a20d  mov     r9b, [rdi+40h]
0x18004a211  test    eax, eax
0x18004a213  jz      short loc_18004A233
0x18004a215  mov     rdx, [rdi+70h]; Src
0x18004a219  mov     rcx, [rdi+18h]; void *
0x18004a21d  mov     r8, r12; Size
0x18004a220  test    r9b, r9b
0x18004a223  jz      short loc_18004A22C
0x18004a225  call    RtlCopyFromUser
0x18004a22a  jmp     short loc_18004A295
0x18004a22c  call    RtlCopyVolatileMemory
0x18004a231  jmp     short loc_18004A295
0x18004a233  test    r9b, r9b
0x18004a236  jz      short loc_18004A251
0x18004a238  mov     rdx, r12; Length
0x18004a23b  mov     r8d, 1; Alignment
0x18004a241  mov     rcx, [rdi+70h]; Address
0x18004a245  call    cs:__imp_ProbeForRead
0x18004a24c  nop     dword ptr [rax+rax+00h]
0x18004a251  mov     r8, r12; Size
0x18004a254  mov     rdx, [rdi+70h]; Src
0x18004a258  mov     rcx, [rdi+18h]; void *
0x18004a25c  call    memmove
0x18004a261  jmp     short loc_18004A295
0x18004a263  cmp     ebx, 4000h
0x18004a269  jz      short loc_18004A2D3
0x18004a26b  cmp     ebx, 1000h
0x18004a271  jz      short loc_18004A2D3
0x18004a273  cmp     ebx, 2000h
0x18004a279  jz      short loc_18004A295
0x18004a27b  cmp     ebx, 8000h
0x18004a281  jz      short loc_18004A295
0x18004a283  cmp     ebx, 10000h
0x18004a289  jz      short loc_18004A295
0x18004a28b  mov     eax, 0C000000Dh
0x18004a290  jmp     loc_18004A946
0x18004a295  test    r12d, r12d
0x18004a298  jz      loc_18004A331
0x18004a29e  cmp     byte ptr [rdi+40h], 0
0x18004a2a2  jz      short loc_18004A2BD
0x18004a2a4  mov     rdx, r12; Length
0x18004a2a7  mov     r8d, 1; Alignment
0x18004a2ad  mov     rcx, [rdi+70h]; Address
0x18004a2b1  call    cs:__imp_ProbeForWrite
0x18004a2b8  nop     dword ptr [rax+rax+00h]
0x18004a2bd  cmp     [rsp+68h+arg_18], 0
0x18004a2c6  jz      short loc_18004A2CD
0x18004a2c8  cmp     ebx, 1
0x18004a2cb  jz      short loc_18004A331
0x18004a2cd  or      dword ptr [rdi+10h], 40h
0x18004a2d1  jmp     short loc_18004A331
0x18004a2d3  test    r12d, r12d
0x18004a2d6  jz      short loc_18004A331
0x18004a2d8  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004a2dd  mov     r9b, [rdi+40h]
0x18004a2e1  test    eax, eax
0x18004a2e3  jz      short loc_18004A303
0x18004a2e5  mov     rdx, [rdi+70h]; Src
0x18004a2e9  mov     rcx, [rdi+18h]; void *
0x18004a2ed  mov     r8, r12; Size
0x18004a2f0  test    r9b, r9b
0x18004a2f3  jz      short loc_18004A2FC
0x18004a2f5  call    RtlCopyFromUser
0x18004a2fa  jmp     short loc_18004A331
0x18004a2fc  call    RtlCopyVolatileMemory
0x18004a301  jmp     short loc_18004A331
0x18004a303  test    r9b, r9b
0x18004a306  jz      short loc_18004A321
0x18004a308  mov     rdx, r12; Length
0x18004a30b  mov     r8d, 1; Alignment
0x18004a311  mov     rcx, [rdi+70h]; Address
0x18004a315  call    cs:__imp_ProbeForRead
0x18004a31c  nop     dword ptr [rax+rax+00h]
0x18004a321  mov     r8, r12; Size
0x18004a324  mov     rdx, [rdi+70h]; Src
0x18004a328  mov     rcx, [rdi+18h]; void *
0x18004a32c  call    memmove
0x18004a331  mov     rcx, [rdi+18h]
0x18004a335  mov     r9d, [rsp+68h+Size]
0x18004a33a  jmp     short loc_18004A372
0x18004a33c  mov     edi, eax
0x18004a33e  mov     rbx, [rsp+68h+arg_0]
0x18004a343  cmp     qword ptr [rbx+18h], 0
0x18004a348  jz      short loc_18004A368
0x18004a34a  xor     edx, edx; Tag
0x18004a34c  mov     rcx, [rbx+18h]; P
0x18004a350  call    cs:__imp_ExFreePoolWithTag
0x18004a357  nop     dword ptr [rax+rax+00h]
0x18004a35c  mov     qword ptr [rbx+18h], 0
0x18004a364  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004a368  mov     eax, edi
0x18004a36a  jmp     loc_18004A946
0x18004a36f  mov     r15d, ebx
0x18004a372  mov     eax, r12d
0x18004a375  neg     eax
0x18004a377  sbb     rbx, rbx
0x18004a37a  and     rbx, rcx
0x18004a37d  lea     r10, [rcx+r15]
0x18004a381  mov     edx, [r10+14h]
0x18004a385  mov     r14d, edx
0x18004a388  and     r14d, 77FFFFFFh
0x18004a38f  mov     r8, [r10]
0x18004a392  cmp     r8, qword ptr cs:KSPROPSETID_Topology.Data1
0x18004a399  jnz     short loc_18004A3B0
0x18004a39b  mov     rax, qword ptr cs:KSPROPSETID_Topology.Data4
0x18004a3a2  cmp     [r10+8], rax
0x18004a3a6  jnz     short loc_18004A3B0
0x18004a3a8  mov     r14d, edx
0x18004a3ab  btr     r14d, 1Ch
0x18004a3b0  bt      r14d, 1Ch
0x18004a3b5  jnb     short loc_18004A421
0x18004a3b7  cmp     r9d, 20h ; ' '
0x18004a3bb  jnb     short loc_18004A3C7
0x18004a3bd  mov     eax, 0C0000206h
0x18004a3c2  jmp     loc_18004A946
0x18004a3c7  mov     rcx, [rsp+68h+arg_28]
0x18004a3cf  test    rcx, rcx
0x18004a3d2  jz      short loc_18004A417
0x18004a3d4  mov     eax, [r10+18h]
0x18004a3d8  cmp     eax, [rsp+68h+arg_30]
0x18004a3df  jb      short loc_18004A3EB
0x18004a3e1  mov     eax, 0C0000010h
0x18004a3e6  jmp     loc_18004A946
0x18004a3eb  mov     rax, [rcx+rax*8]
0x18004a3ef  test    rax, rax
0x18004a3f2  jz      loc_18004A941
0x18004a3f8  mov     r11d, [rax]
0x18004a3fb  mov     [rsp+68h+arg_8], r11d
0x18004a400  test    r11d, r11d
0x18004a403  jz      loc_18004A941
0x18004a409  mov     r13, [rax+8]
0x18004a40d  mov     eax, [rax+4]
0x18004a410  mov     [rsp+68h+arg_20], eax
0x18004a417  mov     r14d, edx
0x18004a41a  and     r14d, 67FFFFFFh
0x18004a421  mov     edx, 48h ; 'H'
0x18004a426  mov     eax, [rsp+68h+arg_20]
0x18004a42d  test    eax, eax
0x18004a42f  cmovnz  edx, eax
0x18004a432  mov     esi, [rsp+68h+arg_8]
0x18004a436  mov     r11d, esi
0x18004a439  mov     r15d, 28h ; '('
0x18004a43f  mov     r9d, 0FFFFFFFFh
0x18004a445  test    r11d, r11d
0x18004a448  jz      loc_18004A86C
0x18004a44e  test    r13, r13
0x18004a451  jz      loc_18004A863
0x18004a457  mov     rax, [r13+0]
0x18004a45b  cmp     r8, [rax]
0x18004a45e  jnz     short loc_18004A46A
0x18004a460  mov     rcx, [r10+8]
0x18004a464  cmp     rcx, [rax+8]
0x18004a468  jz      short loc_18004A472
0x18004a46a  add     r13, r15
0x18004a46d  add     r11d, r9d
0x18004a470  jmp     short loc_18004A445
0x18004a472  test    r14d, 0FFF00h
0x18004a479  jz      loc_18004A7E8
0x18004a47f  cmp     r14d, 100h
0x18004a486  jz      loc_18004A62B
0x18004a48c  cmp     r14d, 200h
0x18004a493  jz      short loc_18004A4DF
0x18004a495  cmp     r14d, 800h
0x18004a49c  jz      loc_18004A5E9
0x18004a4a2  cmp     r14d, 1000h
0x18004a4a9  jz      loc_18004A5C0
0x18004a4af  cmp     r14d, 2000h
0x18004a4b6  jz      loc_18004A574
0x18004a4bc  cmp     r14d, 4000h
0x18004a4c3  jz      loc_18004A574
0x18004a4c9  cmp     r14d, 8000h
0x18004a4d0  jz      loc_18004A56B
0x18004a4d6  cmp     r14d, 10000h
0x18004a4dd  jnz     short loc_18004A4EE
0x18004a4df  cmp     r12d, 4
0x18004a4e3  jz      short loc_18004A4EE
0x18004a4e5  cmp     r12d, r15d
0x18004a4e8  jb      loc_18004A8F9
0x18004a4ee  mov     r8d, [r10+10h]
0x18004a4f2  mov     rcx, r13
0x18004a4f5  call    FindPropertyItem
  ... truncated ...
```
