# METADATA_PARTITION::ReadPartitionStructures(void)

- ea: `0x18006e10c`
- end: `0x18006eb1e`
- name: `?ReadPartitionStructures@METADATA_PARTITION@@QEAAEXZ`
- size: `2578`
- prototype: `unsigned __int8 __fastcall(METADATA_PARTITION *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x18006821c`

## callees

- `0x180004060`
- `0x180004ab0`
- `0x180005040`
- `0x1800063b8`
- `0x180028568`
- `0x18005fae0`
- `0x180062d18`
- `0x1800632f4`
- `0x180063df0`
- `0x180064c08`
- `0x18006c6d0`
- `0x18006cbd0`
- `0x18006cfc0`
- `0x18006e10c`
- `0x180076a94`
- `0x180076c68`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006e944`
- `ntdll!RtlFreeHeap` at `0x18006e944`
- `ntdll!RtlAllocateHeap` at `0x18006e850`
- `ntdll!RtlAllocateHeap` at `0x18006e850`

## pseudocode

```c
unsigned __int8 __fastcall METADATA_PARTITION::ReadPartitionStructures(METADATA_PARTITION *this)
{
  __int64 v1; // rax
  METADATA_FILE *v2; // r14
  __int64 v4; // r12
  unsigned __int16 v5; // r13
  SPACE_BITMAP_DESCRIPTOR *v6; // r15
  METADATA_FILE *v7; // rax
  METADATA_FILE *v8; // rsi
  int v9; // ebx
  DESCRIPTOR *v10; // rcx
  struct UDF_LVOL *v11; // rdx
  __int64 v12; // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  __int64 v14; // rcx
  char v15; // al
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  FILE_ICB_DESCRIPTOR *v18; // rcx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  METADATA_FILE *v20; // rax
  DESCRIPTOR **v21; // rsi
  int v22; // ebx
  DESCRIPTOR *v23; // rcx
  struct UDF_LVOL *v24; // rdx
  __int64 v25; // rcx
  FILE_ICB_DESCRIPTOR **v26; // rbx
  PVOID *v27; // rcx
  DESCRIPTOR *v28; // rdx
  METADATA_FILE *v29; // rax
  METADATA_FILE *v30; // rsi
  int v31; // ebx
  DESCRIPTOR *v32; // rcx
  struct UDF_LVOL *v33; // rdx
  __int64 v34; // rdx
  void (__fastcall ***v35)(_QWORD, __int64); // rcx
  __int64 v36; // rcx
  char v37; // al
  FILE_ICB_DESCRIPTOR *v38; // rcx
  PVOID Heap; // rsi
  void (__fastcall ***v40)(_QWORD, __int64); // rcx
  FILE_ICB_DESCRIPTOR *v41; // rcx
  unsigned __int64 v42; // rbx
  unsigned __int64 v43; // rax
  unsigned int v44; // r14d
  unsigned int v45; // ebx
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  _QWORD *v48; // rax
  void (__fastcall ***v49)(_QWORD, __int64); // rcx
  __int64 v50; // rbx
  __int64 v51; // rcx
  void (__fastcall ***v52)(_QWORD, __int64); // rcx
  __int64 v53; // rcx
  unsigned int SectorSize; // eax
  unsigned int v55; // eax
  struct METADATA_BITMAP *v56; // rax
  char v58; // [rsp+90h] [rbp+48h] BYREF
  char v59; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v60; // [rsp+A0h] [rbp+58h] BYREF
  unsigned int v61; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 7);
  v2 = 0;
  v60 = 0;
  v61 = 0;
  v59 = 0;
  v4 = *(unsigned __int16 *)(v1 + 180);
  v5 = *(_WORD *)(v1 + 176);
  v6 = *(SPACE_BITMAP_DESCRIPTOR **)(v1 + 8 * v4 + 112);
  v7 = (METADATA_FILE *)operator new(0x68u);
  if ( v7 )
    v8 = METADATA_FILE::METADATA_FILE(v7);
  else
    v8 = 0;
  *((_QWORD *)this + 2) = v8;
  if ( !v8 )
    goto LABEL_15;
  v9 = *(_DWORD *)(*((_QWORD *)this + 8) + 40LL);
  DESCRIPTOR::Destroy(v8);
  *((_DWORD *)v8 + 7) = v9;
  *((_WORD *)v8 + 12) = v4;
  v10 = (DESCRIPTOR *)*((_QWORD *)this + 2);
  v11 = (struct UDF_LVOL *)*((_QWORD *)this + 7);
  *((_BYTE *)v10 + 100) = 0;
  if ( !DESCRIPTOR::Read(v10, v11, &v60) )
    goto LABEL_15;
  if ( !DESCRIPTOR::Verify(*((DESCRIPTOR **)this + 2)) )
    goto LABEL_15;
  v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
  if ( *(_WORD *)v12 != 261 && *(_WORD *)v12 != 266 )
    goto LABEL_15;
  if ( v60 != 1
    || *(_WORD *)(v12 + 20) != 4
    || *(_BYTE *)(v12 + 27) != 0xFA
    || (*(_BYTE *)(v12 + 34) & 7) != 0
    || v6 && !SPACE_BITMAP_DESCRIPTOR::MarkInUse(v6, *(_DWORD *)(*((_QWORD *)this + 8) + 40LL), 1u) )
  {
LABEL_15:
    v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    if ( v13 )
    {
      (**v13)(v13, 1);
      *((_QWORD *)this + 2) = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
  }
  v14 = *((_QWORD *)this + 2);
  v15 = 0;
  v58 = 0;
  if ( v14 )
  {
    if ( !(unsigned __int8)FILE_ICB_DESCRIPTOR::VerifyAndFix(v14, *((_QWORD *)this + 7), 0, &v58, &v59) )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v17 = 13;
      goto LABEL_104;
    }
    v15 = v58;
  }
  v18 = (FILE_ICB_DESCRIPTOR *)*((_QWORD *)this + 2);
  if ( v18 && v15 )
  {
    FILE_ICB_DESCRIPTOR::FreeAllIcbAllocation(v18, *((struct UDF_LVOL **)this + 7));
    v19 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    if ( v19 )
      (**v19)(v19, 1);
    *((_QWORD *)this + 2) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
  }
  if ( !*((_QWORD *)this + 2) )
    MESSAGE::DisplayMsg(
      *(MESSAGE **)(*((_QWORD *)this + 7) + 24LL),
      0x77E1u,
      "%d",
      *(_DWORD *)(*((_QWORD *)this + 8) + 40LL));
  v20 = (METADATA_FILE *)operator new(0x68u);
  if ( v20 )
    v2 = METADATA_FILE::METADATA_FILE(v20);
  v21 = (DESCRIPTOR **)((char *)this + 24);
  *((_QWORD *)this + 3) = v2;
  if ( !v2 )
    goto LABEL_51;
  v22 = *(_DWORD *)(*((_QWORD *)this + 8) + 44LL);
  DESCRIPTOR::Destroy(v2);
  *((_DWORD *)v2 + 7) = v22;
  *((_WORD *)v2 + 12) = v4;
  v2 = 0;
  v23 = *v21;
  v24 = (struct UDF_LVOL *)*((_QWORD *)this + 7);
  *((_BYTE *)v23 + 100) = 0;
  if ( !DESCRIPTOR::Read(v23, v24, &v60) || !DESCRIPTOR::Verify(*v21) )
    goto LABEL_51;
  v25 = *((_QWORD *)*v21 + 2);
  if ( *(_WORD *)v25 != 261 )
  {
    if ( *(_WORD *)v25 == 266 )
    {
      v26 = (FILE_ICB_DESCRIPTOR **)((char *)this + 24);
      goto LABEL_44;
    }
LABEL_51:
    v26 = (FILE_ICB_DESCRIPTOR **)((char *)this + 24);
    goto LABEL_52;
  }
  v26 = (FILE_ICB_DESCRIPTOR **)((char *)this + 24);
LABEL_44:
  if ( v60 == 1
    && *(_WORD *)(v25 + 20) == 4
    && *(_BYTE *)(v25 + 27) == 0xFB
    && (*(_BYTE *)(v25 + 34) & 7) == 0
    && (!v6 || SPACE_BITMAP_DESCRIPTOR::MarkInUse(v6, *(_DWORD *)(*((_QWORD *)this + 8) + 44LL), 1u)) )
  {
    goto LABEL_57;
  }
LABEL_52:
  if ( *v26 )
  {
    (**(void (__fastcall ***)(FILE_ICB_DESCRIPTOR *, __int64))*v26)(*v26, 1);
    *v26 = v2;
  }
  v27 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
LABEL_57:
    v27 = (PVOID *)WPP_GLOBAL_Control;
  }
  v58 = (char)v2;
  if ( *v26 != v2 )
  {
    if ( !(unsigned __int8)FILE_ICB_DESCRIPTOR::VerifyAndFix(*v26, *((_QWORD *)this + 7), 0, &v58, &v59) )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v17 = 16;
      goto LABEL_104;
    }
    v27 = (PVOID *)WPP_GLOBAL_Control;
    if ( *v26 != v2 && v58 )
    {
      if ( (*(_BYTE *)(*((_QWORD *)this + 8) + 58LL) & 1) != 0 || *((METADATA_FILE **)this + 2) == v2 )
        FILE_ICB_DESCRIPTOR::FreeAllIcbAllocation(*v26, *((struct UDF_LVOL **)this + 7));
      if ( *v21 )
        (**(void (__fastcall ***)(DESCRIPTOR *, __int64))*v21)(*v21, 1);
      *v21 = v2;
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( *v21 == v2 )
  {
    MESSAGE::DisplayMsg(
      *(MESSAGE **)(*((_QWORD *)this + 7) + 24LL),
      0x77E2u,
      "%d",
      *(_DWORD *)(*((_QWORD *)this + 8) + 44LL));
    v27 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((METADATA_FILE **)this + 2) == v2 )
  {
    if ( *v21 == v2 )
      return 0;
    if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 1) != 0 )
      WPP_SF_d(v27[2], 18, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
    v28 = *v21;
    *(_BYTE *)(*((_QWORD *)*v21 + 2) + 27LL) = -6;
    *((_BYTE *)v28 + 100) = 1;
    *((_QWORD *)this + 2) = *v21;
    *v21 = v2;
  }
  if ( *(_BYTE *)(*((_QWORD *)this + 7) + 148LL) == (_BYTE)v2 )
  {
    v29 = (METADATA_FILE *)operator new(0x68u);
    v30 = v29 ? METADATA_FILE::METADATA_FILE(v29) : v2;
    *((_QWORD *)this + 4) = v30;
    if ( !v30 )
      goto LABEL_94;
    v31 = *(_DWORD *)(*((_QWORD *)this + 8) + 48LL);
    DESCRIPTOR::Destroy(v30);
    *((_WORD *)v30 + 12) = v4;
    *((_DWORD *)v30 + 7) = v31;
    v32 = (DESCRIPTOR *)*((_QWORD *)this + 4);
    v33 = (struct UDF_LVOL *)*((_QWORD *)this + 7);
    *((_BYTE *)v32 + 100) = 0;
    if ( !DESCRIPTOR::Read(v32, v33, &v60) )
      goto LABEL_94;
    if ( !DESCRIPTOR::Verify(*((DESCRIPTOR **)this + 4)) )
      goto LABEL_94;
    v34 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
    if ( *(_WORD *)v34 != 261 && *(_WORD *)v34 != 266 )
      goto LABEL_94;
    if ( v60 != 1
      || *(_WORD *)(v34 + 20) != 4
      || *(_BYTE *)(v34 + 27) != 0xFC
      || !SPACE_BITMAP_DESCRIPTOR::MarkInUse(v6, *(_DWORD *)(*((_QWORD *)this + 8) + 48LL), 1u) )
    {
LABEL_94:
      v35 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
      if ( v35 )
      {
        (**v35)(v35, 1);
        *((_QWORD *)this + 4) = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
    }
  }
  v36 = *((_QWORD *)this + 4);
  v37 = 0;
  v58 = 0;
  if ( v36 )
  {
    if ( !(unsigned __int8)FILE_ICB_DESCRIPTOR::VerifyAndFix(v36, *((_QWORD *)this + 7), 0, &v58, &v59) )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v17 = 20;
LABEL_104:
      WPP_SF_d(v16[2], v17, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
      return 0;
    }
    v37 = v58;
  }
  v38 = (FILE_ICB_DESCRIPTOR *)*((_QWORD *)this + 4);
  Heap = 0;
  if ( v38 && v37 )
  {
    FILE_ICB_DESCRIPTOR::FreeAllIcbAllocation(v38, *((struct UDF_LVOL **)this + 7));
    v40 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
    if ( v40 )
      (**v40)(v40, 1);
    *((_QWORD *)this + 4) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
  }
  v41 = (FILE_ICB_DESCRIPTOR *)*((_QWORD *)this + 4);
  if ( v41 && (*(_BYTE *)(*((_QWORD *)v41 + 2) + 34LL) & 7) == 3 )
    FILE_ICB_DESCRIPTOR::InitializeForReadWrite(v41, *((struct UDF_LVOL **)this + 7));
  v42 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 56LL);
  v43 = v42 / UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 7) + 32LL));
  v44 = v43;
  if ( *((_QWORD *)this + 4) )
  {
    v45 = (((unsigned __int64)(unsigned int)v43 + 7) >> 3) + 24;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v45);
    if ( !Heap )
    {
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v47 = 22;
      goto LABEL_155;
    }
    v48 = operator new(0x30u);
    if ( v48 )
    {
      *(_QWORD *)((char *)v48 + 28) = 0;
      *v48 = &METADATA_BITMAP::`vftable';
      v48[1] = METADATA_BITMAP_cd;
      *((_WORD *)v48 + 12) = 0;
      v48[2] = 0;
      *((_BYTE *)v48 + 26) = 0;
      *((_BYTE *)v48 + 36) = 1;
      v48[5] = 0;
    }
    else
    {
      v48 = 0;
    }
    *((_QWORD *)this + 5) = v48;
    if ( !v48 )
    {
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v47 = 23;
      goto LABEL_155;
    }
    if ( !FILE_ICB_DESCRIPTOR::ReadData(*((FILE_ICB_DESCRIPTOR **)this + 4), Heap, 0, v45, &v61) || v61 != v45 )
    {
      v49 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
      if ( v49 )
        (**v49)(v49, 1);
      *((_QWORD *)this + 5) = 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
    }
  }
  v50 = *((_QWORD *)this + 5);
  if ( v50 )
  {
    DESCRIPTOR::Destroy(*((DESCRIPTOR **)this + 5));
    *(_QWORD *)(v50 + 16) = Heap;
    *(_BYTE *)(v50 + 26) = 1;
    *(_WORD *)(v50 + 24) = v5;
    if ( !DESCRIPTOR::Verify(*((DESCRIPTOR **)this + 5))
      || (v51 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL), *(_WORD *)v51 != 264)
      || *(_DWORD *)(v51 + 16) != v44 )
    {
      v52 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
      if ( v52 )
        (**v52)(v52, 1);
      *((_QWORD *)this + 5) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
    }
  }
  v53 = *((_QWORD *)this + 7);
  if ( !*(_BYTE *)(v53 + 148) )
    *((_BYTE *)this + 72) = *((_QWORD *)this + 5) == 0;
  if ( *((_BYTE *)this + 72) )
  {
    MESSAGE::DisplayMsg(*(MESSAGE **)(v53 + 24), 0x77E3u, "%d", *(_DWORD *)(*((_QWORD *)this + 8) + 48LL));
    SectorSize = UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 7) + 32LL));
    *((_QWORD *)this + 5) = METADATA_BITMAP::Create(
                              3 - (*(_WORD *)(*((_QWORD *)this + 7) + 40LL) < 0x200u),
                              *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 32LL) + 78LL),
                              *(_DWORD *)(*((_QWORD *)this + 8) + 48LL),
                              v5,
                              SectorSize,
                              v44,
                              1);
  }
  v55 = UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 7) + 32LL));
  v56 = METADATA_BITMAP::Create(
          3 - (*(_WORD *)(*((_QWORD *)this + 7) + 40LL) < 0x200u),
          *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 32LL) + 78LL),
          *(_DWORD *)(*((_QWORD *)this + 8) + 48LL),
          v5,
          v55,
          v44,
          0);
  *((_QWORD *)this + 6) = v56;
  if ( v56 && (*((_QWORD *)this + 5) || *(_BYTE *)(*((_QWORD *)this + 7) + 148LL)) )
    return 1;
  v46 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v47 = 26;
LABEL_155:
    WPP_SF_(v46[2], v47, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18006e10c  push    rbp
0x18006e10e  push    rbx
0x18006e10f  push    rsi
0x18006e110  push    rdi
0x18006e111  push    r12
0x18006e113  push    r13
0x18006e115  push    r14
0x18006e117  push    r15
0x18006e119  mov     rbp, rsp
0x18006e11c  sub     rsp, 48h
0x18006e120  mov     rax, [rcx+38h]
0x18006e124  xor     r14d, r14d
0x18006e127  mov     rdi, rcx
0x18006e12a  mov     [rbp+arg_10], r14d
0x18006e12e  mov     [rbp+arg_18], r14d
0x18006e132  mov     [rbp+arg_8], r14b
0x18006e136  movzx   r12d, word ptr [rax+0B4h]
0x18006e13e  lea     ecx, [r14+68h]; unsigned __int64
0x18006e142  movzx   r13d, word ptr [rax+0B0h]
0x18006e14a  mov     r15, [rax+r12*8+70h]
0x18006e14f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e154  test    rax, rax
0x18006e157  jz      short loc_18006E166
0x18006e159  mov     rcx, rax; this
0x18006e15c  call    ??0METADATA_FILE@@QEAA@XZ; METADATA_FILE::METADATA_FILE(void)
0x18006e161  mov     rsi, rax
0x18006e164  jmp     short loc_18006E169
0x18006e166  mov     rsi, r14
0x18006e169  mov     [rdi+10h], rsi
0x18006e16d  lea     rbx, WPP_GLOBAL_Control
0x18006e174  test    rsi, rsi
0x18006e177  jz      loc_18006E21D
0x18006e17d  mov     rax, [rdi+40h]
0x18006e181  mov     rcx, rsi; this
0x18006e184  mov     ebx, [rax+28h]
0x18006e187  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x18006e18c  mov     [rsi+1Ch], ebx
0x18006e18f  lea     r8, [rbp+arg_10]; unsigned int *
0x18006e193  mov     [rsi+18h], r12w
0x18006e198  mov     rcx, [rdi+10h]; this
0x18006e19c  mov     rdx, [rdi+38h]; struct UDF_LVOL *
0x18006e1a0  mov     [rcx+64h], r14b
0x18006e1a4  call    ?Read@DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@PEAI@Z; DESCRIPTOR::Read(UDF_LVOL *,uint *)
0x18006e1a9  test    al, al
0x18006e1ab  jz      short loc_18006E216
0x18006e1ad  mov     rcx, [rdi+10h]; this
0x18006e1b1  call    ?Verify@DESCRIPTOR@@QEAAEXZ; DESCRIPTOR::Verify(void)
0x18006e1b6  test    al, al
0x18006e1b8  jz      short loc_18006E216
0x18006e1ba  mov     rax, [rdi+10h]
0x18006e1be  mov     rcx, [rax+10h]
0x18006e1c2  mov     eax, 105h
0x18006e1c7  cmp     [rcx], ax
0x18006e1ca  jz      short loc_18006E1D6
0x18006e1cc  mov     eax, 10Ah
0x18006e1d1  cmp     [rcx], ax
0x18006e1d4  jnz     short loc_18006E216
0x18006e1d6  cmp     [rbp+arg_10], 1
0x18006e1da  jnz     short loc_18006E216
0x18006e1dc  cmp     word ptr [rcx+14h], 4
0x18006e1e1  jnz     short loc_18006E216
0x18006e1e3  cmp     byte ptr [rcx+1Bh], 0FAh
0x18006e1e7  jnz     short loc_18006E216
0x18006e1e9  test    byte ptr [rcx+22h], 7
0x18006e1ed  jnz     short loc_18006E216
0x18006e1ef  test    r15, r15
0x18006e1f2  jz      short loc_18006E26B
0x18006e1f4  mov     rdx, [rdi+40h]
0x18006e1f8  mov     r8d, 1; unsigned int
0x18006e1fe  mov     rcx, r15; this
0x18006e201  mov     edx, [rdx+28h]; unsigned int
0x18006e204  call    ?MarkInUse@SPACE_BITMAP_DESCRIPTOR@@QEAAEKK@Z; SPACE_BITMAP_DESCRIPTOR::MarkInUse(ulong,ulong)
0x18006e209  lea     rbx, WPP_GLOBAL_Control
0x18006e210  test    al, al
0x18006e212  jnz     short loc_18006E272
0x18006e214  jmp     short loc_18006E21D
0x18006e216  lea     rbx, WPP_GLOBAL_Control
0x18006e21d  mov     rcx, [rdi+10h]
0x18006e221  test    rcx, rcx
0x18006e224  jz      short loc_18006E23A
0x18006e226  mov     rax, [rcx]
0x18006e229  mov     edx, 1
0x18006e22e  mov     rax, [rax]
0x18006e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e236  mov     [rdi+10h], r14
0x18006e23a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e241  cmp     rcx, rbx
0x18006e244  jz      short loc_18006E272
0x18006e246  test    byte ptr [rcx+1Ch], 1
0x18006e24a  jz      short loc_18006E272
0x18006e24c  mov     r9, [rdi+40h]
0x18006e250  lea     r8, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids
0x18006e257  mov     rcx, [rcx+10h]
0x18006e25b  mov     edx, 0Ch
0x18006e260  mov     r9d, [r9+28h]
0x18006e264  call    WPP_SF_d
0x18006e269  jmp     short loc_18006E272
0x18006e26b  lea     rbx, WPP_GLOBAL_Control
0x18006e272  mov     rcx, [rdi+10h]
0x18006e276  mov     al, r14b
0x18006e279  mov     [rbp+arg_0], al
0x18006e27c  test    rcx, rcx
0x18006e27f  jz      short loc_18006E2CD
0x18006e281  mov     rdx, [rdi+38h]
0x18006e285  lea     rax, [rbp+arg_8]
0x18006e289  lea     r9, [rbp+arg_0]
0x18006e28d  mov     [rsp+48h+var_28], rax
0x18006e292  xor     r8d, r8d
0x18006e295  call    ?VerifyAndFix@FILE_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@W4FIX_LEVEL@@PEAE2@Z; FILE_ICB_DESCRIPTOR::VerifyAndFix(UDF_LVOL *,FIX_LEVEL,uchar *,uchar *)
0x18006e29a  test    al, al
0x18006e29c  jnz     short loc_18006E2CA
0x18006e29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2a5  cmp     rcx, rbx
0x18006e2a8  jz      loc_18006EB0B
0x18006e2ae  test    byte ptr [rcx+1Ch], 1
0x18006e2b2  jz      loc_18006EB0B
0x18006e2b8  mov     r9, [rdi+40h]
0x18006e2bc  mov     edx, 0Dh
0x18006e2c1  mov     r9d, [r9+28h]
0x18006e2c5  jmp     loc_18006E762
0x18006e2ca  mov     al, [rbp+arg_0]
0x18006e2cd  mov     rcx, [rdi+10h]; this
0x18006e2d1  test    rcx, rcx
0x18006e2d4  jz      short loc_18006E32F
0x18006e2d6  test    al, al
0x18006e2d8  jz      short loc_18006E32F
0x18006e2da  mov     rdx, [rdi+38h]; struct UDF_LVOL *
0x18006e2de  call    ?FreeAllIcbAllocation@FILE_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@@Z; FILE_ICB_DESCRIPTOR::FreeAllIcbAllocation(UDF_LVOL *)
0x18006e2e3  mov     rcx, [rdi+10h]
0x18006e2e7  test    rcx, rcx
0x18006e2ea  jz      short loc_18006E2FC
0x18006e2ec  mov     rax, [rcx]
0x18006e2ef  mov     edx, 1
0x18006e2f4  mov     rax, [rax]
0x18006e2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2fc  mov     [rdi+10h], r14
0x18006e300  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e307  cmp     rcx, rbx
0x18006e30a  jz      short loc_18006E32F
0x18006e30c  test    byte ptr [rcx+1Ch], 1
0x18006e310  jz      short loc_18006E32F
0x18006e312  mov     r9, [rdi+40h]
0x18006e316  lea     r8, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids
0x18006e31d  mov     rcx, [rcx+10h]
0x18006e321  mov     edx, 0Eh
0x18006e326  mov     r9d, [r9+28h]
0x18006e32a  call    WPP_SF_d
0x18006e32f  cmp     [rdi+10h], r14
0x18006e333  jnz     short loc_18006E356
0x18006e335  mov     r9, [rdi+40h]
0x18006e339  lea     r8, aD_0; "%d"
0x18006e340  mov     rcx, [rdi+38h]
0x18006e344  mov     edx, 77E1h; unsigned int
0x18006e349  mov     r9d, [r9+28h]
0x18006e34d  mov     rcx, [rcx+18h]; this
0x18006e351  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18006e356  mov     ecx, 68h ; 'h'; unsigned __int64
0x18006e35b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e360  test    rax, rax
0x18006e363  jz      short loc_18006E370
0x18006e365  mov     rcx, rax; this
0x18006e368  call    ??0METADATA_FILE@@QEAA@XZ; METADATA_FILE::METADATA_FILE(void)
0x18006e36d  mov     r14, rax
0x18006e370  lea     rsi, [rdi+18h]
0x18006e374  mov     [rsi], r14
0x18006e377  test    r14, r14
0x18006e37a  jz      loc_18006E41C
0x18006e380  mov     rax, [rdi+40h]
0x18006e384  mov     rcx, r14; this
0x18006e387  mov     ebx, [rax+2Ch]
0x18006e38a  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x18006e38f  mov     [r14+1Ch], ebx
0x18006e393  lea     r8, [rbp+arg_10]; unsigned int *
0x18006e397  mov     [r14+18h], r12w
0x18006e39c  xor     r14d, r14d
0x18006e39f  mov     rcx, [rsi]; this
0x18006e3a2  mov     rdx, [rdi+38h]; struct UDF_LVOL *
0x18006e3a6  mov     [rcx+64h], r14b
0x18006e3aa  call    ?Read@DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@PEAI@Z; DESCRIPTOR::Read(UDF_LVOL *,uint *)
0x18006e3af  test    al, al
0x18006e3b1  jz      short loc_18006E41C
0x18006e3b3  mov     rcx, [rsi]; this
0x18006e3b6  call    ?Verify@DESCRIPTOR@@QEAAEXZ; DESCRIPTOR::Verify(void)
0x18006e3bb  test    al, al
0x18006e3bd  jz      short loc_18006E41C
0x18006e3bf  mov     rax, [rsi]
0x18006e3c2  mov     rcx, [rax+10h]
0x18006e3c6  mov     eax, 105h
0x18006e3cb  cmp     [rcx], ax
0x18006e3ce  jnz     short loc_18006E3D5
0x18006e3d0  mov     rbx, rsi
0x18006e3d3  jmp     short loc_18006E3E3
0x18006e3d5  mov     eax, 10Ah
0x18006e3da  cmp     [rcx], ax
0x18006e3dd  jnz     short loc_18006E41C
0x18006e3df  lea     rbx, [rdi+18h]
0x18006e3e3  cmp     [rbp+arg_10], 1
0x18006e3e7  jnz     short loc_18006E41F
0x18006e3e9  cmp     word ptr [rcx+14h], 4
0x18006e3ee  jnz     short loc_18006E41F
0x18006e3f0  cmp     byte ptr [rcx+1Bh], 0FBh
0x18006e3f4  jnz     short loc_18006E41F
0x18006e3f6  test    byte ptr [rcx+22h], 7
0x18006e3fa  jnz     short loc_18006E41F
0x18006e3fc  test    r15, r15
0x18006e3ff  jz      short loc_18006E470
0x18006e401  mov     rdx, [rdi+40h]
0x18006e405  mov     r8d, 1; unsigned int
0x18006e40b  mov     rcx, r15; this
0x18006e40e  mov     edx, [rdx+2Ch]; unsigned int
0x18006e411  call    ?MarkInUse@SPACE_BITMAP_DESCRIPTOR@@QEAAEKK@Z; SPACE_BITMAP_DESCRIPTOR::MarkInUse(ulong,ulong)
0x18006e416  test    al, al
0x18006e418  jz      short loc_18006E41F
0x18006e41a  jmp     short loc_18006E470
0x18006e41c  mov     rbx, rsi
0x18006e41f  mov     rcx, [rbx]
0x18006e422  test    rcx, rcx
0x18006e425  jz      short loc_18006E43A
0x18006e427  mov     rax, [rcx]
0x18006e42a  mov     edx, 1
0x18006e42f  mov     rax, [rax]
0x18006e432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e437  mov     [rbx], r14
0x18006e43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e441  lea     rax, WPP_GLOBAL_Control
0x18006e448  cmp     rcx, rax
0x18006e44b  jz      short loc_18006E477
0x18006e44d  test    byte ptr [rcx+1Ch], 1
0x18006e451  jz      short loc_18006E477
0x18006e453  mov     r9, [rdi+40h]
0x18006e457  lea     r8, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids
0x18006e45e  mov     rcx, [rcx+10h]
0x18006e462  mov     edx, 0Fh
0x18006e467  mov     r9d, [r9+2Ch]
0x18006e46b  call    WPP_SF_d
0x18006e470  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e477  mov     al, r14b
0x18006e47a  mov     [rbp+arg_0], al
0x18006e47d  cmp     [rbx], r14
0x18006e480  jz      loc_18006E562
0x18006e486  mov     rdx, [rdi+38h]
0x18006e48a  lea     rax, [rbp+arg_8]
0x18006e48e  mov     rcx, [rbx]
0x18006e491  lea     r9, [rbp+arg_0]
0x18006e495  xor     r8d, r8d
0x18006e498  mov     [rsp+48h+var_28], rax
0x18006e49d  call    ?VerifyAndFix@FILE_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@W4FIX_LEVEL@@PEAE2@Z; FILE_ICB_DESCRIPTOR::VerifyAndFix(UDF_LVOL *,FIX_LEVEL,uchar *,uchar *)
0x18006e4a2  test    al, al
0x18006e4a4  jnz     short loc_18006E4D9
0x18006e4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4ad  lea     rax, WPP_GLOBAL_Control
0x18006e4b4  cmp     rcx, rax
0x18006e4b7  jz      loc_18006EB0B
0x18006e4bd  test    byte ptr [rcx+1Ch], 1
0x18006e4c1  jz      loc_18006EB0B
0x18006e4c7  mov     r9, [rdi+40h]
0x18006e4cb  mov     edx, 10h
0x18006e4d0  mov     r9d, [r9+2Ch]
0x18006e4d4  jmp     loc_18006E762
0x18006e4d9  mov     al, [rbp+arg_0]
0x18006e4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4e3  cmp     [rbx], r14
0x18006e4e6  jz      short loc_18006E562
0x18006e4e8  test    al, al
0x18006e4ea  jz      short loc_18006E562
0x18006e4ec  mov     rax, [rdi+40h]
0x18006e4f0  test    byte ptr [rax+3Ah], 1
0x18006e4f4  jnz     short loc_18006E4FC
0x18006e4f6  cmp     [rdi+10h], r14
0x18006e4fa  jnz     short loc_18006E508
0x18006e4fc  mov     rdx, [rdi+38h]; struct UDF_LVOL *
0x18006e500  mov     rcx, [rbx]; this
0x18006e503  call    ?FreeAllIcbAllocation@FILE_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@@Z; FILE_ICB_DESCRIPTOR::FreeAllIcbAllocation(UDF_LVOL *)
0x18006e508  mov     rcx, [rsi]
0x18006e50b  test    rcx, rcx
0x18006e50e  jz      short loc_18006E520
0x18006e510  mov     rax, [rcx]
0x18006e513  mov     edx, 1
0x18006e518  mov     rax, [rax]
0x18006e51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e520  mov     [rsi], r14
0x18006e523  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e52a  lea     rbx, WPP_GLOBAL_Control
0x18006e531  cmp     rcx, rbx
0x18006e534  jz      short loc_18006E569
0x18006e536  test    byte ptr [rcx+1Ch], 1
0x18006e53a  jz      short loc_18006E569
0x18006e53c  mov     r9, [rdi+40h]
0x18006e540  lea     r8, WPP_83b371e4cc3a36167e52495c5059672e_Traceguids
0x18006e547  mov     rcx, [rcx+10h]
0x18006e54b  mov     edx, 11h
0x18006e550  mov     r9d, [r9+2Ch]
0x18006e554  call    WPP_SF_d
0x18006e559  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e560  jmp     short loc_18006E569
0x18006e562  lea     rbx, WPP_GLOBAL_Control
0x18006e569  cmp     [rsi], r14
0x18006e56c  jnz     short loc_18006E596
0x18006e56e  mov     r9, [rdi+40h]
0x18006e572  lea     r8, aD_0; "%d"
  ... truncated ...
```
