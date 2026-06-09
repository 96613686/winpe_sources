# FILE_ICB_DESCRIPTOR::WriteNextAllocation(ulong,ulong,short,SPACE_BITMAP_DESCRIPTOR *)

- ea: `0x180066570`
- end: `0x1800668d8`
- name: `?WriteNextAllocation@FILE_ICB_DESCRIPTOR@@AEAAEKKFPEAVSPACE_BITMAP_DESCRIPTOR@@@Z`
- size: `872`
- prototype: `unsigned __int8 __usercall@<al>(FILE_ICB_DESCRIPTOR *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, __int16@<r9w>, struct SPACE_BITMAP_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065840`

## callees

- `0x18005fae0`
- `0x1800621f8`
- `0x180064544`
- `0x180066570`
- `0x180067558`
- `0x18006c50c`
- `0x18006c5e4`
- `0x18006c6d0`
- `0x18006ca54`
- `0x18006cf58`
- `0x18006d25c`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800667b0`
- `ntdll!RtlFreeHeap` at `0x1800667b0`

## pseudocode

```c
char __fastcall FILE_ICB_DESCRIPTOR::WriteNextAllocation(
        FILE_ICB_DESCRIPTOR *this,
        unsigned int a2,
        unsigned int a3,
        __int16 a4,
        struct SPACE_BITMAP_DESCRIPTOR *a5)
{
  __int64 v6; // rcx
  UDF_SA *v8; // rcx
  char v9; // r14
  unsigned int SectorSize; // r13d
  __int16 v11; // r8
  __int64 v12; // rdx
  int v13; // r15d
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int TagLocation; // r10d
  __int64 v17; // rbx
  unsigned int v18; // eax
  unsigned __int16 PartitionNumberForAllocationTag; // ax
  __int64 v20; // rcx
  __int16 v21; // dx
  int v22; // eax
  int v23; // edx
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int16 v26; // ax
  __int64 v27; // rbx
  __int16 v28; // di
  void *v29; // r8
  __int64 v30; // rbx
  unsigned int v31; // eax
  unsigned __int16 v32; // ax
  struct DESCRIPTOR *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rbx
  unsigned int v37; // eax
  unsigned __int16 v38; // ax
  __int16 v39; // cx
  SIZE_T Size; // [rsp+20h] [rbp-40h]
  unsigned int v42; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v43[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v44; // [rsp+48h] [rbp-18h]
  __int16 v45; // [rsp+50h] [rbp-10h]
  char v46; // [rsp+52h] [rbp-Eh]
  int v47; // [rsp+54h] [rbp-Ch]
  unsigned int v48; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v49; // [rsp+A8h] [rbp+48h]
  unsigned int v50; // [rsp+B0h] [rbp+50h]

  v50 = a3;
  v49 = a2;
  v43[0] = &DESCRIPTOR::`vftable';
  v6 = *((_QWORD *)this + 4);
  v43[1] = DESCRIPTOR_cd;
  v48 = 0;
  v47 = 0;
  v45 = 0;
  v44 = 0;
  v46 = 0;
  v8 = *(UDF_SA **)(v6 + 32);
  v42 = 0;
  v9 = 1;
  SectorSize = UDF_SA::QuerySectorSize(v8);
  v11 = *(_WORD *)(*((_QWORD *)this + 2) + 34LL) & 7;
  if ( v11 )
  {
    v12 = 40;
    if ( v11 == 1 )
      v12 = 32;
  }
  else
  {
    v12 = 16;
  }
  v13 = 8;
  if ( v12 + (unsigned __int64)*((unsigned int *)this + 17) > *((unsigned int *)this + 16) )
  {
    v14 = *((_DWORD *)this + 23);
    if ( *((_DWORD *)this + 24) >= v14 )
    {
      if ( v14 )
        TagLocation = *(_DWORD *)(*((_QWORD *)this + 10) + 4LL * (v14 - 1));
      else
        TagLocation = DESCRIPTOR::GetTagLocation(this);
      if ( !a5
        || !(*(unsigned __int8 (__fastcall **)(struct SPACE_BITMAP_DESCRIPTOR *, _QWORD, __int64, unsigned int *, int))(*(_QWORD *)a5 + 48LL))(
              a5,
              TagLocation,
              1,
              &v48,
              1)
        || !FILE_ICB_DESCRIPTOR::AddAllocationDescriptorBlock(this, v48) )
      {
        goto LABEL_33;
      }
      v15 = v48;
    }
    else
    {
      v15 = *(_DWORD *)(*((_QWORD *)this + 10) + 4LL * *((unsigned int *)this + 24));
      v48 = v15;
    }
    v17 = *((_QWORD *)this + 4);
    v18 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *))(*(_QWORD *)this + 64LL))(this);
    PartitionNumberForAllocationTag = UDF_LVOL::GetPartitionNumberForAllocationTag(v17, v18);
    if ( !FILE_ICB_DESCRIPTOR::SetAllocationAtIteratorPosition(
            this,
            PartitionNumberForAllocationTag,
            v15,
            SectorSize,
            3) )
    {
LABEL_33:
      v9 = 0;
      goto LABEL_38;
    }
    v20 = *((_QWORD *)this + 2);
    v21 = *(_WORD *)(v20 + 34) & 7;
    if ( v21 )
    {
      v22 = 20;
      if ( v21 == 1 )
        v22 = 16;
    }
    else
    {
      v22 = 8;
    }
    *((_DWORD *)this + 17) += v22;
    v23 = *((_DWORD *)this + 17);
    if ( *((_DWORD *)this + 24) )
    {
      *(_DWORD *)(*((_QWORD *)this + 9) + 20LL) = v23;
      *(_DWORD *)(*((_QWORD *)this + 9) + 16LL) = 0;
      v24 = *((_QWORD *)this + 4);
      v25 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *))(*(_QWORD *)this + 64LL))(this);
      v26 = UDF_LVOL::GetPartitionNumberForAllocationTag(v24, v25);
      v27 = *((_QWORD *)this + 9);
      v28 = v26;
      DESCRIPTOR::Destroy((DESCRIPTOR *)v43);
      v44 = v27;
      v46 = 0;
      v45 = v28;
      if ( !DESCRIPTOR::RecomputeChecksums((DESCRIPTOR *)v43)
        || !DESCRIPTOR::Write((DESCRIPTOR *)v43, *((UDF_SA ***)this + 4), &v42)
        || v42 != 1 )
      {
        goto LABEL_33;
      }
    }
    else
    {
      if ( *(_WORD *)v20 == 266 )
        *(_DWORD *)(v20 + 212) = v23;
      else
        *(_DWORD *)(v20 + 172) = v23;
      *((_BYTE *)this + 100) = 1;
    }
    ++*((_DWORD *)this + 24);
    v29 = (void *)*((_QWORD *)this + 9);
    if ( v29 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
      *((_QWORD *)this + 9) = 0;
    }
    v30 = *((_QWORD *)this + 4);
    v31 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *))(*(_QWORD *)this + 64LL))(this);
    v32 = UDF_LVOL::GetPartitionNumberForAllocationTag(v30, v31);
    LODWORD(Size) = SectorSize;
    v33 = DESCRIPTOR::Create(
            0x102u,
            3 - (*(_WORD *)(*((_QWORD *)this + 4) + 40LL) < 0x200u),
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 32LL) + 78LL),
            v48,
            Size,
            v32);
    if ( !v33 )
      goto LABEL_33;
    v34 = *((_QWORD *)v33 + 2);
    *((_BYTE *)v33 + 26) = 0;
    *((_QWORD *)this + 9) = v34;
    (**(void (__fastcall ***)(struct DESCRIPTOR *, __int64))v33)(v33, 1);
    *(_DWORD *)(*((_QWORD *)this + 9) + 20LL) = SectorSize - 24;
    v35 = *((_QWORD *)this + 9);
    *((_DWORD *)this + 17) = 0;
    *((_QWORD *)this + 7) = v35 + 24;
    *((_DWORD *)this + 16) = *(_DWORD *)(v35 + 20);
  }
  v36 = *((_QWORD *)this + 4);
  v37 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *))(*(_QWORD *)this + 56LL))(this);
  v38 = UDF_LVOL::GetPartitionNumberForAllocationTag(v36, v37);
  if ( !FILE_ICB_DESCRIPTOR::SetAllocationAtIteratorPosition(this, v38, v49, v50, a4) )
    goto LABEL_33;
  v39 = *(_WORD *)(*((_QWORD *)this + 2) + 34LL) & 7;
  if ( v39 )
  {
    v13 = 20;
    if ( v39 == 1 )
      v13 = 16;
  }
  *((_DWORD *)this + 17) += v13;
LABEL_38:
  DESCRIPTOR::~DESCRIPTOR((DESCRIPTOR *)v43);
  return v9;
}

```

## disassembly

```asm
0x180066570  mov     [rsp-38h+arg_18], rbx
0x180066575  mov     [rsp-38h+arg_10], r8d
0x18006657a  mov     [rsp-38h+arg_8], edx
0x18006657e  push    rbp
0x18006657f  push    rsi
0x180066580  push    rdi
0x180066581  push    r12
0x180066583  push    r13
0x180066585  push    r14
0x180066587  push    r15
0x180066589  mov     rbp, rsp
0x18006658c  sub     rsp, 60h
0x180066590  xor     edi, edi
0x180066592  lea     rax, ??_7DESCRIPTOR@@6B@; const DESCRIPTOR::`vftable'
0x180066599  mov     rsi, rcx
0x18006659c  mov     [rbp+var_28], rax
0x1800665a0  mov     rcx, [rcx+20h]
0x1800665a4  movzx   r12d, r9w
0x1800665a8  mov     rax, cs:?DESCRIPTOR_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const DESCRIPTOR_cd
0x1800665af  mov     [rbp+var_20], rax
0x1800665b3  mov     [rbp+arg_0], edi
0x1800665b6  mov     [rbp+var_C], edi
0x1800665b9  mov     [rbp+var_10], di
0x1800665bd  mov     [rbp+var_18], rdi
0x1800665c1  mov     [rbp+var_E], dil
0x1800665c5  mov     rcx, [rcx+20h]; this
0x1800665c9  mov     [rbp+var_30], edi
0x1800665cc  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x1800665d1  mov     rcx, [rsi+10h]
0x1800665d5  lea     r14d, [rdi+1]
0x1800665d9  mov     r13d, eax
0x1800665dc  movzx   r8d, word ptr [rcx+22h]
0x1800665e1  and     r8w, 7
0x1800665e6  jnz     short loc_1800665ED
0x1800665e8  lea     edx, [rdi+10h]
0x1800665eb  jmp     short loc_1800665FC
0x1800665ed  mov     edx, 28h ; '('
0x1800665f2  cmp     r8w, r14w
0x1800665f6  lea     eax, [rdx-8]
0x1800665f9  cmovz   edx, eax
0x1800665fc  mov     ecx, [rsi+44h]
0x1800665ff  mov     r15d, 8
0x180066605  mov     eax, [rsi+40h]
0x180066608  add     rcx, rdx
0x18006660b  cmp     rcx, rax
0x18006660e  jbe     loc_180066851
0x180066614  mov     eax, [rsi+5Ch]
0x180066617  cmp     [rsi+60h], eax
0x18006661a  jnb     short loc_18006662B
0x18006661c  mov     ecx, [rsi+60h]
0x18006661f  mov     rax, [rsi+50h]
0x180066623  mov     edi, [rax+rcx*4]
0x180066626  mov     [rbp+arg_0], edi
0x180066629  jmp     short loc_18006668D
0x18006662b  test    eax, eax
0x18006662d  jz      short loc_18006663C
0x18006662f  lea     ecx, [rax-1]
0x180066632  mov     rax, [rsi+50h]
0x180066636  mov     r10d, [rax+rcx*4]
0x18006663a  jmp     short loc_180066647
0x18006663c  mov     rcx, rsi; this
0x18006663f  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180066644  mov     r10d, eax
0x180066647  mov     rcx, [rbp+arg_20]
0x18006664b  test    rcx, rcx
0x18006664e  jz      loc_18006688B
0x180066654  mov     rdx, [rcx]
0x180066657  lea     r9, [rbp+arg_0]
0x18006665b  mov     r8d, r14d
0x18006665e  mov     dword ptr [rsp+60h+Size], r14d
0x180066663  mov     rax, [rdx+30h]
0x180066667  mov     edx, r10d
0x18006666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006666f  test    al, al
0x180066671  jz      loc_18006688B
0x180066677  mov     edx, [rbp+arg_0]; unsigned int
0x18006667a  mov     rcx, rsi; this
0x18006667d  call    ?AddAllocationDescriptorBlock@FILE_ICB_DESCRIPTOR@@AEAAEK@Z; FILE_ICB_DESCRIPTOR::AddAllocationDescriptorBlock(ulong)
0x180066682  test    al, al
0x180066684  jz      loc_18006688B
0x18006668a  mov     edi, [rbp+arg_0]
0x18006668d  mov     rax, [rsi]
0x180066690  mov     rcx, rsi
0x180066693  mov     rbx, [rsi+20h]
0x180066697  mov     rax, [rax+40h]
0x18006669b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666a0  mov     edx, eax
0x1800666a2  mov     rcx, rbx
0x1800666a5  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x1800666aa  movzx   edx, ax; unsigned __int16
0x1800666ad  mov     word ptr [rsp+60h+Size], 3; __int16
0x1800666b4  mov     r9d, r13d; unsigned int
0x1800666b7  mov     r8d, edi; unsigned int
0x1800666ba  mov     rcx, rsi; this
0x1800666bd  call    ?SetAllocationAtIteratorPosition@FILE_ICB_DESCRIPTOR@@AEAAEGKKF@Z; FILE_ICB_DESCRIPTOR::SetAllocationAtIteratorPosition(ushort,ulong,ulong,short)
0x1800666c2  xor     edi, edi
0x1800666c4  test    al, al
0x1800666c6  jz      loc_18006688B
0x1800666cc  mov     rcx, [rsi+10h]
0x1800666d0  movzx   edx, word ptr [rcx+22h]
0x1800666d4  and     dx, 7
0x1800666d8  jnz     short loc_1800666DF
0x1800666da  mov     eax, r15d
0x1800666dd  jmp     short loc_1800666EE
0x1800666df  mov     eax, 14h
0x1800666e4  cmp     dx, r14w
0x1800666e8  lea     edx, [rax-4]
0x1800666eb  cmovz   eax, edx
0x1800666ee  add     [rsi+44h], eax
0x1800666f1  mov     edx, [rsi+44h]
0x1800666f4  cmp     [rsi+60h], edi
0x1800666f7  jnz     short loc_180066717
0x1800666f9  mov     eax, 10Ah
0x1800666fe  cmp     [rcx], ax
0x180066701  jnz     short loc_18006670B
0x180066703  mov     [rcx+0D4h], edx
0x180066709  jmp     short loc_180066711
0x18006670b  mov     [rcx+0ACh], edx
0x180066711  mov     [rsi+64h], r14b
0x180066715  jmp     short loc_180066794
0x180066717  mov     rax, [rsi+48h]
0x18006671b  mov     rcx, rsi
0x18006671e  mov     [rax+14h], edx
0x180066721  mov     rax, [rsi+48h]
0x180066725  mov     [rax+10h], edi
0x180066728  mov     rax, [rsi]
0x18006672b  mov     rbx, [rsi+20h]
0x18006672f  mov     rax, [rax+40h]
0x180066733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066738  mov     edx, eax
0x18006673a  mov     rcx, rbx
0x18006673d  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x180066742  mov     rbx, [rsi+48h]
0x180066746  lea     rcx, [rbp+var_28]; this
0x18006674a  movzx   edi, ax
0x18006674d  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x180066752  lea     rcx, [rbp+var_28]; this
0x180066756  mov     [rbp+var_18], rbx
0x18006675a  mov     [rbp+var_E], 0
0x18006675e  mov     [rbp+var_10], di
0x180066762  call    ?RecomputeChecksums@DESCRIPTOR@@QEAAEXZ; DESCRIPTOR::RecomputeChecksums(void)
0x180066767  xor     edi, edi
0x180066769  test    al, al
0x18006676b  jz      loc_18006688B
0x180066771  mov     rdx, [rsi+20h]; struct UDF_LVOL *
0x180066775  lea     r8, [rbp+var_30]; unsigned int *
0x180066779  lea     rcx, [rbp+var_28]; this
0x18006677d  call    ?Write@DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@PEAI@Z; DESCRIPTOR::Write(UDF_LVOL *,uint *)
0x180066782  test    al, al
0x180066784  jz      loc_18006688B
0x18006678a  cmp     [rbp+var_30], r14d
0x18006678e  jnz     loc_18006688B
0x180066794  add     [rsi+60h], r14d
0x180066798  mov     r8, [rsi+48h]; P
0x18006679c  test    r8, r8
0x18006679f  jz      short loc_1800667BA
0x1800667a1  mov     rcx, gs:60h
0x1800667aa  xor     edx, edx; Flags
0x1800667ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800667b0  call    cs:__imp_RtlFreeHeap
0x1800667b6  mov     [rsi+48h], rdi
0x1800667ba  mov     rax, [rsi]
0x1800667bd  mov     rcx, rsi
0x1800667c0  mov     rbx, [rsi+20h]
0x1800667c4  mov     rax, [rax+40h]
0x1800667c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667cd  mov     edx, eax
0x1800667cf  mov     rcx, rbx
0x1800667d2  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x1800667d7  mov     rcx, [rsi+20h]
0x1800667db  mov     edx, 200h
0x1800667e0  mov     r9d, [rbp+arg_0]; unsigned int
0x1800667e4  mov     [rsp+60h+var_38], ax; unsigned __int16
0x1800667e9  mov     dword ptr [rsp+60h+Size], r13d; Size
0x1800667ee  cmp     [rcx+28h], dx
0x1800667f2  mov     r8, [rcx+20h]
0x1800667f6  mov     ecx, 102h; unsigned __int16
0x1800667fb  sbb     dx, dx
0x1800667fe  add     dx, 3; unsigned __int16
0x180066802  movzx   r8d, word ptr [r8+4Eh]; unsigned __int16
0x180066807  call    ?Create@DESCRIPTOR@@SAPEAV1@GGGKIG@Z; DESCRIPTOR::Create(ushort,ushort,ushort,ulong,uint,ushort)
0x18006680c  mov     r8, rax
0x18006680f  test    rax, rax
0x180066812  jz      short loc_18006688B
0x180066814  mov     rcx, [rax+10h]
0x180066818  mov     edx, r14d
0x18006681b  mov     [rax+1Ah], dil
0x18006681f  mov     [rsi+48h], rcx
0x180066823  mov     rcx, [rax]
0x180066826  mov     rax, [rcx]
0x180066829  mov     rcx, r8
0x18006682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066831  mov     rax, [rsi+48h]
0x180066835  lea     ecx, [r13-18h]
0x180066839  mov     [rax+14h], ecx
0x18006683c  mov     rcx, [rsi+48h]
0x180066840  mov     [rsi+44h], edi
0x180066843  lea     rax, [rcx+18h]
0x180066847  mov     [rsi+38h], rax
0x18006684b  mov     eax, [rcx+14h]
0x18006684e  mov     [rsi+40h], eax
0x180066851  mov     rax, [rsi]
0x180066854  mov     rcx, rsi
0x180066857  mov     rbx, [rsi+20h]
0x18006685b  mov     rax, [rax+38h]
0x18006685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066864  mov     edx, eax
0x180066866  mov     rcx, rbx
0x180066869  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x18006686e  mov     r9d, [rbp+arg_10]; unsigned int
0x180066872  movzx   edx, ax; unsigned __int16
0x180066875  mov     r8d, [rbp+arg_8]; unsigned int
0x180066879  mov     rcx, rsi; this
0x18006687c  mov     word ptr [rsp+60h+Size], r12w; __int16
0x180066882  call    ?SetAllocationAtIteratorPosition@FILE_ICB_DESCRIPTOR@@AEAAEGKKF@Z; FILE_ICB_DESCRIPTOR::SetAllocationAtIteratorPosition(ushort,ulong,ulong,short)
0x180066887  test    al, al
0x180066889  jnz     short loc_180066890
0x18006688b  mov     r14b, dil
0x18006688e  jmp     short loc_1800668B4
0x180066890  mov     rax, [rsi+10h]
0x180066894  movzx   ecx, word ptr [rax+22h]
0x180066898  and     cx, 7
0x18006689c  jz      short loc_1800668B0
0x18006689e  mov     r15d, 14h
0x1800668a4  cmp     cx, r14w
0x1800668a8  lea     eax, [r15-4]
0x1800668ac  cmovz   r15d, eax
0x1800668b0  add     [rsi+44h], r15d
0x1800668b4  lea     rcx, [rbp+var_28]; this
0x1800668b8  call    ??1DESCRIPTOR@@UEAA@XZ; DESCRIPTOR::~DESCRIPTOR(void)
0x1800668bd  mov     rbx, [rsp+60h+arg_18]
0x1800668c5  mov     al, r14b
0x1800668c8  add     rsp, 60h
0x1800668cc  pop     r15
0x1800668ce  pop     r14
0x1800668d0  pop     r13
0x1800668d2  pop     r12
0x1800668d4  pop     rdi
0x1800668d5  pop     rsi
0x1800668d6  pop     rbp
0x1800668d7  retn
```
