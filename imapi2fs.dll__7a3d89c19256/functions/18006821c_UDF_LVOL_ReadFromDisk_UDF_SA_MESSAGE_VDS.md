# UDF_LVOL::ReadFromDisk(UDF_SA *,MESSAGE *,VDS *)

- ea: `0x18006821c`
- end: `0x180068620`
- name: `?ReadFromDisk@UDF_LVOL@@QEAAEPEAVUDF_SA@@PEAVMESSAGE@@PEAVVDS@@@Z`
- size: `1028`
- prototype: `unsigned __int8 __fastcall(UDF_SA **this, struct UDF_SA *, struct MESSAGE *, UNALLOCATED_SPACE_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006b540`

## callees

- `0x180001670`
- `0x180004ab0`
- `0x180005040`
- `0x180028568`
- `0x18005ee4c`
- `0x18005fae0`
- `0x180066c54`
- `0x180066f40`
- `0x1800670a4`
- `0x1800675ac`
- `0x18006800c`
- `0x18006821c`
- `0x180068628`
- `0x180068858`
- `0x180068a9c`
- `0x180068ea0`
- `0x18006e10c`
- `0x18006f048`
- `0x18007d0b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006851b`
- `ntdll!RtlFreeHeap` at `0x18006851b`
- `ntdll!RtlAllocateHeap` at `0x180068486`
- `ntdll!RtlAllocateHeap` at `0x180068486`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int8 __fastcall UDF_LVOL::ReadFromDisk(
        UDF_SA **this,
        struct UDF_SA *a2,
        struct MESSAGE *a3,
        UNALLOCATED_SPACE_DESCRIPTOR **a4)
{
  char v7; // r14
  unsigned __int8 v9; // dl
  NUMBER_SET *v10; // rax
  NUMBER_SET *v11; // rcx
  UDF_SA *v12; // rcx
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned int v15; // r15d
  unsigned int SectorSize; // eax
  unsigned __int64 v17; // rbp
  unsigned int v18; // eax
  PVOID Heap; // r12
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned __int8 Blocks; // al
  __int64 v23; // rdi
  unsigned int v24[22]; // [rsp+30h] [rbp-58h] BYREF

  v7 = 0;
  if ( !UDF_LVOL::Initialize((UDF_LVOL *)this, a2, a3, (struct VDS *)a4) )
    return 0;
  if ( *((_BYTE *)this + 146) )
    return 1;
  if ( *((_BYTE *)this + 145) && !UDF_LVOL::ReadSparingTable((UDF_LVOL *)this) )
  {
    MESSAGE::DisplayMsg((MESSAGE *)a3, 0x77C8u, MultiByteStr);
    return 0;
  }
  if ( !UDF_LVOL::ReadSpaceBitmapDescriptor((UDF_LVOL *)this) )
    return 0;
  if ( *((_BYTE *)this + *((unsigned __int16 *)this + 90) + 143) )
  {
    if ( !*((_BYTE *)this + 149) )
    {
      MESSAGE::DisplayMsg((MESSAGE *)a3, 0x7793u, "%d", *((_DWORD *)this[7] + 17));
      if ( !UDF_LVOL::CreateSpaceBitmapDescriptor((UDF_LVOL *)this, v9) )
        return 0;
    }
  }
  if ( *((_BYTE *)this + 147) )
  {
    if ( !METADATA_PARTITION::ReadPartitionStructures(this[21]) )
      return 0;
    this[*((unsigned __int16 *)this + 88) + 14] = (UDF_SA *)*((_QWORD *)this[21] + 6);
    this[*((unsigned __int16 *)this + 88) + 12] = (UDF_SA *)*((_QWORD *)this[21] + 5);
    *((_BYTE *)this + *((unsigned __int16 *)this + 88) + 143) = *((_BYTE *)this[21] + 72);
  }
  if ( !UDF_LVOL::ReadFileSetDescriptor((UDF_LVOL *)this) )
    return 0;
  if ( *((_BYTE *)this + 141) )
  {
    MESSAGE::DisplayMsg((MESSAGE *)a3, 0x7792u, "%d", *((_DWORD *)this[6] + 63));
    if ( !UDF_LVOL::CreateFileSetDescriptor((UDF_LVOL *)this) )
      return 0;
  }
  if ( this[19] && !UDF_LVOL::ReadNonAllocatableSpaceStream((UDF_LVOL *)this) )
    return 0;
  v10 = (NUMBER_SET *)operator new(0x80u);
  v11 = v10;
  if ( v10 )
  {
    *((_QWORD *)v10 + 15) = 0;
    *(_QWORD *)v10 = &NUMBER_SET::`vftable';
    *((_QWORD *)v10 + 1) = NUMBER_SET_cd;
  }
  else
  {
    v11 = 0;
  }
  this[11] = v11;
  if ( !v11 || !NUMBER_SET::Initialize(v11) )
    return 0;
  if ( UDF_LVOL::ReadLogicalVolumeIntegritySequence((UDF_LVOL *)this, (UDF_SA *)((char *)this[6] + 432)) )
    return 1;
  MESSAGE::DisplayMsg((MESSAGE *)a3, 0x77EFu, "%d", *((_DWORD *)this[6] + 109));
  v12 = this[4];
  v13 = *((_DWORD *)this[6] + 109);
  v14 = *((_QWORD *)v12 + 6);
  v24[0] = v13;
  v15 = (*(_DWORD *)(v14 + 360) & 8) != 0 ? 16 : 32;
  SectorSize = UDF_SA::QuerySectorSize(v12);
  v17 = (SectorSize + (unsigned __int64)*((unsigned int *)this[6] + 108) - 1) / SectorSize;
  v18 = UDF_SA::QuerySectorSize(this[4]);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v17 * v18);
  if ( !Heap )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v21 = 17;
    goto LABEL_46;
  }
  while ( 1 )
  {
    Blocks = UNALLOCATED_SPACE_DESCRIPTOR::AllocateBlocks(a4[8], v13 + v17, v17, v24, v15);
    v23 = v24[0];
    if ( !Blocks )
      break;
    if ( (unsigned __int8)IO_DP_DRIVE::Read(*((_QWORD *)a2 + 6), v24[0], (unsigned int)v17, Heap) )
    {
      v7 = 1;
      break;
    }
    v13 = v15 + v23;
    v24[0] = v13;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( !v7 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v21 = 18;
    goto LABEL_46;
  }
  if ( !UDF_LVOL::CreateLogicalVolumeIntegrityDescriptor((UDF_LVOL *)this) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v21 = 19;
    goto LABEL_46;
  }
  *((_DWORD *)this[10] + (unsigned int)(2 * *((_DWORD *)this[10] + 18)) + 29) = 1;
  *((_DWORD *)this[10] + 7) = 1;
  if ( (unsigned __int8)NUMBER_SET::Add(this[11], v23, (unsigned int)v17) )
  {
    *((_DWORD *)this[6] + 109) = v23;
    *((_BYTE *)this[4] + 656) = 1;
    MESSAGE::DisplayMsg((MESSAGE *)a3, 0x77F0u, "%d", v23);
    return 1;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v21 = 20;
LABEL_46:
    WPP_SF_(v20[2], v21, &WPP_aa5e611ff52c37f86cb6d37266dd366a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18006821c  mov     [rsp+arg_8], rdx
0x180068221  push    rbx
0x180068222  push    rbp
0x180068223  push    rsi
0x180068224  push    rdi
0x180068225  push    r12
0x180068227  push    r13
0x180068229  push    r14
0x18006822b  push    r15
0x18006822d  sub     rsp, 48h
0x180068231  mov     r13, r9
0x180068234  mov     rsi, r8
0x180068237  mov     rbx, rcx
0x18006823a  call    ?Initialize@UDF_LVOL@@AEAAEPEAVUDF_SA@@PEAVMESSAGE@@PEAVVDS@@@Z; UDF_LVOL::Initialize(UDF_SA *,MESSAGE *,VDS *)
0x18006823f  xor     r14d, r14d
0x180068242  test    al, al
0x180068244  jz      short loc_18006827C
0x180068246  cmp     [rbx+92h], r14b
0x18006824d  jz      short loc_180068253
0x18006824f  mov     al, 1
0x180068251  jmp     short loc_18006827E
0x180068253  cmp     [rbx+91h], r14b
0x18006825a  jz      short loc_18006828F
0x18006825c  mov     rcx, rbx; this
0x18006825f  call    ?ReadSparingTable@UDF_LVOL@@AEAAEXZ; UDF_LVOL::ReadSparingTable(void)
0x180068264  test    al, al
0x180068266  jnz     short loc_18006828F
0x180068268  lea     r8, MultiByteStr; char *
0x18006826f  mov     edx, 77C8h; unsigned int
0x180068274  mov     rcx, rsi; this
0x180068277  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18006827c  xor     al, al
0x18006827e  add     rsp, 48h
0x180068282  pop     r15
0x180068284  pop     r14
0x180068286  pop     r13
0x180068288  pop     r12
0x18006828a  pop     rdi
0x18006828b  pop     rsi
0x18006828c  pop     rbp
0x18006828d  pop     rbx
0x18006828e  retn
0x18006828f  mov     rcx, rbx; this
0x180068292  call    ?ReadSpaceBitmapDescriptor@UDF_LVOL@@AEAAEXZ; UDF_LVOL::ReadSpaceBitmapDescriptor(void)
0x180068297  test    al, al
0x180068299  jz      short loc_18006827C
0x18006829b  movzx   eax, word ptr [rbx+0B4h]
0x1800682a2  lea     rdi, aD_0; "%d"
0x1800682a9  cmp     [rax+rbx+8Fh], r14b
0x1800682b1  jz      short loc_1800682E0
0x1800682b3  cmp     [rbx+95h], r14b
0x1800682ba  jnz     short loc_1800682E0
0x1800682bc  mov     r9, [rbx+38h]
0x1800682c0  mov     r8, rdi; char *
0x1800682c3  mov     edx, 7793h; unsigned int
0x1800682c8  mov     rcx, rsi; this
0x1800682cb  mov     r9d, [r9+44h]
0x1800682cf  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x1800682d4  mov     rcx, rbx; this
0x1800682d7  call    ?CreateSpaceBitmapDescriptor@UDF_LVOL@@AEAAEE@Z; UDF_LVOL::CreateSpaceBitmapDescriptor(uchar)
0x1800682dc  test    al, al
0x1800682de  jz      short loc_18006827C
0x1800682e0  cmp     [rbx+93h], r14b
0x1800682e7  jz      short loc_18006833F
0x1800682e9  mov     rcx, [rbx+0A8h]; this
0x1800682f0  call    ?ReadPartitionStructures@METADATA_PARTITION@@QEAAEXZ; METADATA_PARTITION::ReadPartitionStructures(void)
0x1800682f5  test    al, al
0x1800682f7  jz      short loc_18006827C
0x1800682f9  mov     rax, [rbx+0A8h]
0x180068300  movzx   ecx, word ptr [rbx+0B0h]
0x180068307  mov     rax, [rax+30h]
0x18006830b  mov     [rbx+rcx*8+70h], rax
0x180068310  mov     rax, [rbx+0A8h]
0x180068317  movzx   ecx, word ptr [rbx+0B0h]
0x18006831e  mov     rax, [rax+28h]
0x180068322  mov     [rbx+rcx*8+60h], rax
0x180068327  mov     rax, [rbx+0A8h]
0x18006832e  movzx   ecx, word ptr [rbx+0B0h]
0x180068335  mov     al, [rax+48h]
0x180068338  mov     [rcx+rbx+8Fh], al
0x18006833f  mov     rcx, rbx; this
0x180068342  call    ?ReadFileSetDescriptor@UDF_LVOL@@AEAAEXZ; UDF_LVOL::ReadFileSetDescriptor(void)
0x180068347  test    al, al
0x180068349  jz      loc_18006827C
0x18006834f  cmp     [rbx+8Dh], r14b
0x180068356  jz      short loc_180068383
0x180068358  mov     r9, [rbx+30h]
0x18006835c  mov     r8, rdi; char *
0x18006835f  mov     edx, 7792h; unsigned int
0x180068364  mov     rcx, rsi; this
0x180068367  mov     r9d, [r9+0FCh]
0x18006836e  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180068373  mov     rcx, rbx; this
0x180068376  call    ?CreateFileSetDescriptor@UDF_LVOL@@AEAAEXZ; UDF_LVOL::CreateFileSetDescriptor(void)
0x18006837b  test    al, al
0x18006837d  jz      loc_18006827C
0x180068383  cmp     [rbx+98h], r14
0x18006838a  jz      short loc_18006839C
0x18006838c  mov     rcx, rbx; this
0x18006838f  call    ?ReadNonAllocatableSpaceStream@UDF_LVOL@@AEAAEXZ; UDF_LVOL::ReadNonAllocatableSpaceStream(void)
0x180068394  test    al, al
0x180068396  jz      loc_18006827C
0x18006839c  mov     ecx, 80h; unsigned __int64
0x1800683a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800683a6  mov     rcx, rax
0x1800683a9  test    rax, rax
0x1800683ac  jz      short loc_1800683C9
0x1800683ae  lea     rax, ??_7NUMBER_SET@@6B@; const NUMBER_SET::`vftable'
0x1800683b5  mov     [rcx+78h], r14
0x1800683b9  mov     [rcx], rax
0x1800683bc  mov     rax, cs:?NUMBER_SET_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const NUMBER_SET_cd
0x1800683c3  mov     [rcx+8], rax
0x1800683c7  jmp     short loc_1800683CC
0x1800683c9  mov     rcx, r14; this
0x1800683cc  mov     [rbx+58h], rcx
0x1800683d0  test    rcx, rcx
0x1800683d3  jz      loc_18006827C
0x1800683d9  call    ?Initialize@NUMBER_SET@@QEAAEXZ; NUMBER_SET::Initialize(void)
0x1800683de  test    al, al
0x1800683e0  jz      loc_18006827C
0x1800683e6  mov     rdx, [rbx+30h]
0x1800683ea  mov     rcx, rbx; this
0x1800683ed  add     rdx, 1B0h; struct EXTENTAD *
0x1800683f4  call    ?ReadLogicalVolumeIntegritySequence@UDF_LVOL@@AEAAEPEAUEXTENTAD@@@Z; UDF_LVOL::ReadLogicalVolumeIntegritySequence(EXTENTAD *)
0x1800683f9  test    al, al
0x1800683fb  jnz     loc_18006824F
0x180068401  mov     r9, [rbx+30h]
0x180068405  mov     r8, rdi; char *
0x180068408  mov     edx, 77EFh; unsigned int
0x18006840d  mov     rcx, rsi; this
0x180068410  mov     r9d, [r9+1B4h]
0x180068417  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18006841c  mov     rax, [rbx+30h]
0x180068420  mov     rcx, [rbx+20h]; this
0x180068424  mov     edi, [rax+1B4h]
0x18006842a  mov     rax, [rcx+30h]
0x18006842e  mov     [rsp+88h+var_58], edi
0x180068432  mov     edx, [rax+168h]
0x180068438  and     dl, 8
0x18006843b  neg     dl
0x18006843d  sbb     r15d, r15d
0x180068440  and     r15d, 0FFFFFFF0h
0x180068444  add     r15d, 20h ; ' '
0x180068448  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006844d  mov     rcx, [rbx+20h]; this
0x180068451  xor     edx, edx
0x180068453  mov     r8d, eax
0x180068456  mov     rax, [rbx+30h]
0x18006845a  mov     eax, [rax+1B0h]
0x180068460  dec     rax
0x180068463  add     rax, r8
0x180068466  div     r8
0x180068469  mov     rbp, rax
0x18006846c  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180068471  mov     rcx, gs:60h
0x18006847a  xor     edx, edx; Flags
0x18006847c  imul    eax, ebp
0x18006847f  mov     rcx, [rcx+30h]; HeapHandle
0x180068483  mov     r8d, eax; Size
0x180068486  call    cs:__imp_RtlAllocateHeap
0x18006848c  mov     r12, rax
0x18006848f  test    rax, rax
0x180068492  jnz     short loc_1800684BF
0x180068494  mov     rcx, cs:WPP_GLOBAL_Control
0x18006849b  lea     rax, WPP_GLOBAL_Control
0x1800684a2  cmp     rcx, rax
0x1800684a5  jz      loc_18006827C
0x1800684ab  test    byte ptr [rcx+1Ch], 1
0x1800684af  jz      loc_18006827C
0x1800684b5  lea     edx, [r12+11h]
0x1800684ba  jmp     loc_1800685DA
0x1800684bf  mov     rcx, [r13+40h]; this
0x1800684c3  lea     edx, [rdi+rbp]; unsigned int
0x1800684c6  lea     r9, [rsp+88h+var_58]; unsigned int *
0x1800684cb  mov     [rsp+88h+var_68], r15d; unsigned int
0x1800684d0  mov     r8d, ebp; unsigned int
0x1800684d3  call    ?AllocateBlocks@UNALLOCATED_SPACE_DESCRIPTOR@@QEAAEKKPEAKK@Z; UNALLOCATED_SPACE_DESCRIPTOR::AllocateBlocks(ulong,ulong,ulong *,ulong)
0x1800684d8  mov     edi, [rsp+88h+var_58]
0x1800684dc  test    al, al
0x1800684de  jz      short loc_180068509
0x1800684e0  mov     rax, [rsp+88h+arg_8]
0x1800684e8  mov     edx, edi
0x1800684ea  mov     r9, r12
0x1800684ed  mov     r8d, ebp
0x1800684f0  mov     rcx, [rax+30h]
0x1800684f4  call    ?Read@IO_DP_DRIVE@@QEAAEVBIG_INT@@KPEAX@Z; IO_DP_DRIVE::Read(BIG_INT,ulong,void *)
0x1800684f9  test    al, al
0x1800684fb  jnz     short loc_180068506
0x1800684fd  add     edi, r15d
0x180068500  mov     [rsp+88h+var_58], edi
0x180068504  jmp     short loc_1800684BF
0x180068506  mov     r14b, 1
0x180068509  mov     rcx, gs:60h
0x180068512  mov     r8, r12; P
0x180068515  xor     edx, edx; Flags
0x180068517  mov     rcx, [rcx+30h]; HeapHandle
0x18006851b  call    cs:__imp_RtlFreeHeap
0x180068521  test    r14b, r14b
0x180068524  jnz     short loc_180068551
0x180068526  mov     rcx, cs:WPP_GLOBAL_Control
0x18006852d  lea     rax, WPP_GLOBAL_Control
0x180068534  cmp     rcx, rax
0x180068537  jz      loc_18006827C
0x18006853d  test    byte ptr [rcx+1Ch], 1
0x180068541  jz      loc_18006827C
0x180068547  mov     edx, 12h
0x18006854c  jmp     loc_1800685DA
0x180068551  mov     rcx, rbx; this
0x180068554  call    ?CreateLogicalVolumeIntegrityDescriptor@UDF_LVOL@@AEAAEXZ; UDF_LVOL::CreateLogicalVolumeIntegrityDescriptor(void)
0x180068559  test    al, al
0x18006855b  jnz     short loc_180068585
0x18006855d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068564  lea     rax, WPP_GLOBAL_Control
0x18006856b  cmp     rcx, rax
0x18006856e  jz      loc_18006827C
0x180068574  test    byte ptr [rcx+1Ch], 1
0x180068578  jz      loc_18006827C
0x18006857e  mov     edx, 13h
0x180068583  jmp     short loc_1800685DA
0x180068585  mov     rcx, [rbx+50h]
0x180068589  mov     rdx, rdi
0x18006858c  mov     r8d, ebp
0x18006858f  mov     eax, [rcx+48h]
0x180068592  add     eax, eax
0x180068594  mov     dword ptr [rcx+rax*4+74h], 1
0x18006859c  mov     rax, [rbx+50h]
0x1800685a0  mov     dword ptr [rax+1Ch], 1
0x1800685a7  mov     rcx, [rbx+58h]
0x1800685ab  call    ?Add@NUMBER_SET@@QEAAEVBIG_INT@@0@Z; NUMBER_SET::Add(BIG_INT,BIG_INT)
0x1800685b0  test    al, al
0x1800685b2  jnz     short loc_1800685EF
0x1800685b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800685bb  lea     rax, WPP_GLOBAL_Control
0x1800685c2  cmp     rcx, rax
0x1800685c5  jz      loc_18006827C
0x1800685cb  test    byte ptr [rcx+1Ch], 1
0x1800685cf  jz      loc_18006827C
0x1800685d5  mov     edx, 14h
0x1800685da  mov     rcx, [rcx+10h]
0x1800685de  lea     r8, WPP_aa5e611ff52c37f86cb6d37266dd366a_Traceguids
0x1800685e5  call    WPP_SF_
0x1800685ea  jmp     loc_18006827C
0x1800685ef  mov     rax, [rbx+30h]
0x1800685f3  lea     r8, aD_0; "%d"
0x1800685fa  mov     r9d, edi
0x1800685fd  mov     edx, 77F0h; unsigned int
0x180068602  mov     rcx, rsi; this
0x180068605  mov     [rax+1B4h], edi
0x18006860b  mov     rax, [rbx+20h]
0x18006860f  mov     byte ptr [rax+290h], 1
0x180068616  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18006861b  jmp     loc_18006824F
```
