# FILE_ICB_DESCRIPTOR::NextAllocation(uchar,ulong *,ulong *,short *,uchar *,SPACE_BITMAP_DESCRIPTOR *)

- ea: `0x180063a90`
- end: `0x180063d36`
- name: `?NextAllocation@FILE_ICB_DESCRIPTOR@@QEAAEEPEAK0PEAFPEAEPEAVSPACE_BITMAP_DESCRIPTOR@@@Z`
- size: `678`
- prototype: `unsigned __int8 __usercall@<al>(FILE_ICB_DESCRIPTOR *__hidden this@<rcx>, unsigned __int8@<dl>, unsigned int *@<r8>, unsigned int *@<r9>, __int16 *, unsigned __int8 *, struct SPACE_BITMAP_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18000a34c`
- `0x1800334f0`
- `0x1800632f4`
- `0x180065180`

## callees

- `0x180003b20`
- `0x180004060`
- `0x18005fae0`
- `0x1800621f8`
- `0x180063060`
- `0x180063a90`
- `0x180064b64`
- `0x180067558`
- `0x18006c50c`
- `0x18006c6d0`
- `0x18006cbd0`
- `0x18006cfc0`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180063c16`
- `ntdll!RtlFreeHeap` at `0x180063c16`

## pseudocode

```c
unsigned __int8 __fastcall FILE_ICB_DESCRIPTOR::NextAllocation(
        FILE_ICB_DESCRIPTOR *this,
        char a2,
        unsigned int *a3,
        unsigned int *a4,
        __int16 *a5,
        unsigned __int8 *a6,
        struct SPACE_BITMAP_DESCRIPTOR *a7)
{
  unsigned __int8 *v7; // rdi
  __int16 *v12; // rbx
  unsigned int *v13; // r8
  unsigned int *v14; // r9
  unsigned int v15; // r9d
  unsigned int SectorSize; // eax
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int16 PartitionNumberForAllocationTag; // ax
  unsigned int v20; // ebx
  struct UDF_LVOL *v21; // rdx
  _WORD *v22; // rax
  void *v23; // r8
  bool v24; // zf
  __int64 v25; // rcx
  __int16 *v26; // rbx
  __int16 v28; // cx
  int v29; // eax
  unsigned int v30; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+38h] [rbp-28h] BYREF
  _WORD *v32; // [rsp+48h] [rbp-18h]
  unsigned __int16 v33; // [rsp+50h] [rbp-10h]
  char v34; // [rsp+52h] [rbp-Eh]
  unsigned int v35; // [rsp+54h] [rbp-Ch]
  unsigned __int16 v36; // [rsp+90h] [rbp+30h] BYREF
  char v37; // [rsp+98h] [rbp+38h]

  v37 = a2;
  v7 = a6;
  v31[0] = &DESCRIPTOR::`vftable';
  v31[1] = DESCRIPTOR_cd;
  v35 = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v30 = 0;
  v36 = 0;
  if ( a6 )
    *a6 = 0;
  if ( *((_DWORD *)this + 17) >= *((_DWORD *)this + 16) )
    goto LABEL_23;
  v12 = a5;
  if ( !FILE_ICB_DESCRIPTOR::GetAllocationAtIteratorPosition(this, &v36, a3, a4, a5) )
    goto LABEL_25;
  v15 = *v14;
  if ( !v15 )
  {
LABEL_23:
    DESCRIPTOR::~DESCRIPTOR((DESCRIPTOR *)v31);
    return 0;
  }
  if ( *v12 != 3 )
  {
    if ( FILE_ICB_DESCRIPTOR::ValidateAllocationDescriptor(this, v36, *v13, v15, *v12, a2) )
      goto LABEL_27;
LABEL_25:
    if ( v7 )
      *v7 = 1;
    goto LABEL_23;
  }
  SectorSize = UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 4) + 32LL));
  if ( (SectorSize + (unsigned __int64)*a4 - 1) / SectorSize != 1 )
    goto LABEL_21;
  v17 = *((_QWORD *)this + 4);
  v18 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *, unsigned __int64))(*(_QWORD *)this + 64LL))(
          this,
          (SectorSize + (unsigned __int64)*a4 - 1) % SectorSize);
  PartitionNumberForAllocationTag = UDF_LVOL::GetPartitionNumberForAllocationTag(v17, v18);
  if ( v36 != PartitionNumberForAllocationTag || a7 && SPACE_BITMAP_DESCRIPTOR::QueryInUse(a7, *a3) )
    goto LABEL_21;
  v20 = *a3;
  DESCRIPTOR::Destroy((DESCRIPTOR *)v31);
  v21 = (struct UDF_LVOL *)*((_QWORD *)this + 4);
  v33 = v36;
  v35 = v20;
  if ( !DESCRIPTOR::Read((DESCRIPTOR *)v31, v21, &v30) )
    goto LABEL_21;
  if ( v30 != 1 )
    goto LABEL_21;
  if ( !DESCRIPTOR::Verify((DESCRIPTOR *)v31) )
    goto LABEL_21;
  v22 = v32;
  if ( *v32 != 258 )
    goto LABEL_21;
  v23 = (void *)*((_QWORD *)this + 9);
  if ( v23 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    v22 = v32;
  }
  v24 = a7 == 0;
  v34 = 0;
  *((_QWORD *)this + 9) = v22;
  if ( !v24 )
    SPACE_BITMAP_DESCRIPTOR::MarkInUse(a7, *a3, 1u);
  FILE_ICB_DESCRIPTOR::AddAllocationDescriptorBlock(this, *a3);
  v25 = *((_QWORD *)this + 9);
  v26 = a5;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 7) = v25 + 24;
  *((_DWORD *)this + 16) = *(_DWORD *)(v25 + 20);
  if ( !FILE_ICB_DESCRIPTOR::GetAllocationAtIteratorPosition(this, &v36, a3, a4, v26)
    || !FILE_ICB_DESCRIPTOR::ValidateAllocationDescriptor(this, v36, *a3, *a4, *v26, v37) )
  {
LABEL_21:
    if ( v7 )
      *v7 = 1;
    goto LABEL_23;
  }
LABEL_27:
  v28 = *(_WORD *)(*((_QWORD *)this + 2) + 34LL) & 7;
  if ( v28 )
  {
    v29 = 20;
    if ( v28 == 1 )
      v29 = 16;
  }
  else
  {
    v29 = 8;
  }
  *((_DWORD *)this + 17) += v29;
  DESCRIPTOR::~DESCRIPTOR((DESCRIPTOR *)v31);
  return 1;
}

```

## disassembly

```asm
0x180063a90  mov     [rsp-28h+arg_10], rbx
0x180063a95  mov     [rsp-28h+arg_18], rsi
0x180063a9a  mov     [rsp-28h+arg_8], dl
0x180063a9e  push    rbp
0x180063a9f  push    rdi
0x180063aa0  push    r13
0x180063aa2  push    r14
0x180063aa4  push    r15
0x180063aa6  mov     rbp, rsp
0x180063aa9  sub     rsp, 60h
0x180063aad  mov     rdi, [rbp+arg_28]
0x180063ab1  lea     rax, ??_7DESCRIPTOR@@6B@; const DESCRIPTOR::`vftable'
0x180063ab8  mov     [rbp+var_28], rax
0x180063abc  mov     r13, r9
0x180063abf  mov     rax, cs:?DESCRIPTOR_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const DESCRIPTOR_cd
0x180063ac6  mov     r15, r8
0x180063ac9  mov     [rbp+var_20], rax
0x180063acd  mov     sil, dl
0x180063ad0  xor     eax, eax
0x180063ad2  mov     [rbp+var_C], 0
0x180063ad9  mov     [rbp+var_10], ax
0x180063add  mov     r14, rcx
0x180063ae0  mov     [rbp+var_18], rax
0x180063ae4  mov     [rbp+var_E], al
0x180063ae7  mov     [rbp+var_30], eax
0x180063aea  mov     [rbp+arg_0], ax
0x180063aee  test    rdi, rdi
0x180063af1  jz      short loc_180063AF5
0x180063af3  mov     [rdi], al
0x180063af5  mov     eax, [rcx+40h]
0x180063af8  cmp     [rcx+44h], eax
0x180063afb  jnb     loc_180063CB1
0x180063b01  mov     rbx, [rbp+arg_20]
0x180063b05  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180063b09  mov     [rsp+60h+var_40], rbx; __int16 *
0x180063b0e  call    ?GetAllocationAtIteratorPosition@FILE_ICB_DESCRIPTOR@@AEAAEPEAGPEAK1PEAF@Z; FILE_ICB_DESCRIPTOR::GetAllocationAtIteratorPosition(ushort *,ulong *,ulong *,short *)
0x180063b13  test    al, al
0x180063b15  jz      loc_180063CF2
0x180063b1b  mov     r9d, [r9]; unsigned int
0x180063b1e  test    r9d, r9d
0x180063b21  jz      loc_180063CB1
0x180063b27  movzx   eax, word ptr [rbx]
0x180063b2a  cmp     ax, 3
0x180063b2e  jnz     loc_180063CD5
0x180063b34  mov     rcx, [r14+20h]
0x180063b38  mov     rcx, [rcx+20h]; this
0x180063b3c  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180063b41  mov     ecx, eax
0x180063b43  xor     edx, edx
0x180063b45  mov     eax, [r13+0]
0x180063b49  mov     esi, 1
0x180063b4e  dec     rax
0x180063b51  add     rax, rcx
0x180063b54  div     rcx
0x180063b57  cmp     rax, rsi
0x180063b5a  jnz     loc_180063CA9
0x180063b60  mov     rax, [r14]
0x180063b63  mov     rcx, r14
0x180063b66  mov     rbx, [r14+20h]
0x180063b6a  mov     rax, [rax+40h]
0x180063b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b73  mov     edx, eax
0x180063b75  mov     rcx, rbx
0x180063b78  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x180063b7d  cmp     [rbp+arg_0], ax
0x180063b81  jnz     loc_180063CA9
0x180063b87  cmp     [rbp+arg_30], 0
0x180063b8c  jz      short loc_180063BA2
0x180063b8e  mov     rcx, [rbp+arg_30]; this
0x180063b92  mov     edx, [r15]; unsigned int
0x180063b95  call    ?QueryInUse@SPACE_BITMAP_DESCRIPTOR@@QEAAEK@Z; SPACE_BITMAP_DESCRIPTOR::QueryInUse(ulong)
0x180063b9a  test    al, al
0x180063b9c  jnz     loc_180063CA9
0x180063ba2  mov     ebx, [r15]
0x180063ba5  lea     rcx, [rbp+var_28]; this
0x180063ba9  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x180063bae  movzx   eax, [rbp+arg_0]
0x180063bb2  lea     r8, [rbp+var_30]; unsigned int *
0x180063bb6  mov     rdx, [r14+20h]; struct UDF_LVOL *
0x180063bba  lea     rcx, [rbp+var_28]; this
0x180063bbe  mov     [rbp+var_10], ax
0x180063bc2  mov     [rbp+var_C], ebx
0x180063bc5  call    ?Read@DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@PEAI@Z; DESCRIPTOR::Read(UDF_LVOL *,uint *)
0x180063bca  test    al, al
0x180063bcc  jz      loc_180063CA9
0x180063bd2  cmp     [rbp+var_30], esi
0x180063bd5  jnz     loc_180063CA9
0x180063bdb  lea     rcx, [rbp+var_28]; this
0x180063bdf  call    ?Verify@DESCRIPTOR@@QEAAEXZ; DESCRIPTOR::Verify(void)
0x180063be4  test    al, al
0x180063be6  jz      loc_180063CA9
0x180063bec  mov     rax, [rbp+var_18]
0x180063bf0  mov     ecx, 102h
0x180063bf5  cmp     [rax], cx
0x180063bf8  jnz     loc_180063CA9
0x180063bfe  mov     r8, [r14+48h]; P
0x180063c02  test    r8, r8
0x180063c05  jz      short loc_180063C20
0x180063c07  mov     rcx, gs:60h
0x180063c10  xor     edx, edx; Flags
0x180063c12  mov     rcx, [rcx+30h]; HeapHandle
0x180063c16  call    cs:__imp_RtlFreeHeap
0x180063c1c  mov     rax, [rbp+var_18]
0x180063c20  cmp     [rbp+arg_30], 0
0x180063c25  mov     [rbp+var_E], 0
0x180063c29  mov     [r14+48h], rax
0x180063c2d  jz      short loc_180063C3E
0x180063c2f  mov     edx, [r15]; unsigned int
0x180063c32  mov     r8d, esi; unsigned int
0x180063c35  mov     rcx, [rbp+arg_30]; this
0x180063c39  call    ?MarkInUse@SPACE_BITMAP_DESCRIPTOR@@QEAAEKK@Z; SPACE_BITMAP_DESCRIPTOR::MarkInUse(ulong,ulong)
0x180063c3e  mov     edx, [r15]; unsigned int
0x180063c41  mov     rcx, r14; this
0x180063c44  call    ?AddAllocationDescriptorBlock@FILE_ICB_DESCRIPTOR@@AEAAEK@Z; FILE_ICB_DESCRIPTOR::AddAllocationDescriptorBlock(ulong)
0x180063c49  mov     rcx, [r14+48h]
0x180063c4d  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180063c51  mov     rbx, [rbp+arg_20]
0x180063c55  mov     r9, r13; unsigned int *
0x180063c58  mov     dword ptr [r14+44h], 0
0x180063c60  mov     r8, r15; unsigned int *
0x180063c63  mov     [rsp+60h+var_40], rbx; __int16 *
0x180063c68  lea     rax, [rcx+18h]
0x180063c6c  mov     [r14+38h], rax
0x180063c70  mov     eax, [rcx+14h]
0x180063c73  mov     rcx, r14; this
0x180063c76  mov     [r14+40h], eax
0x180063c7a  call    ?GetAllocationAtIteratorPosition@FILE_ICB_DESCRIPTOR@@AEAAEPEAGPEAK1PEAF@Z; FILE_ICB_DESCRIPTOR::GetAllocationAtIteratorPosition(ushort *,ulong *,ulong *,short *)
0x180063c7f  test    al, al
0x180063c81  jz      short loc_180063CA9
0x180063c83  mov     al, [rbp+arg_8]
0x180063c86  mov     rcx, r14; this
0x180063c89  mov     r9d, [r13+0]; unsigned int
0x180063c8d  mov     r8d, [r15]; unsigned int
0x180063c90  movzx   edx, [rbp+arg_0]; unsigned __int16
0x180063c94  mov     [rsp+60h+var_38], al; char
0x180063c98  movzx   eax, word ptr [rbx]
0x180063c9b  mov     word ptr [rsp+60h+var_40], ax; __int16
0x180063ca0  call    ?ValidateAllocationDescriptor@FILE_ICB_DESCRIPTOR@@AEAAEGKKFE@Z; FILE_ICB_DESCRIPTOR::ValidateAllocationDescriptor(ushort,ulong,ulong,short,uchar)
0x180063ca5  test    al, al
0x180063ca7  jnz     short loc_180063D01
0x180063ca9  test    rdi, rdi
0x180063cac  jz      short loc_180063CB1
0x180063cae  mov     [rdi], sil
0x180063cb1  lea     rcx, [rbp+var_28]; this
0x180063cb5  call    ??1DESCRIPTOR@@UEAA@XZ; DESCRIPTOR::~DESCRIPTOR(void)
0x180063cba  xor     al, al
0x180063cbc  lea     r11, [rsp+60h+var_s0]
0x180063cc1  mov     rbx, [r11+40h]
0x180063cc5  mov     rsi, [r11+48h]
0x180063cc9  mov     rsp, r11
0x180063ccc  pop     r15
0x180063cce  pop     r14
0x180063cd0  pop     r13
0x180063cd2  pop     rdi
0x180063cd3  pop     rbp
0x180063cd4  retn
0x180063cd5  mov     r8d, [r8]; unsigned int
0x180063cd8  mov     rcx, r14; this
0x180063cdb  movzx   edx, [rbp+arg_0]; unsigned __int16
0x180063cdf  mov     [rsp+60h+var_38], sil; char
0x180063ce4  mov     word ptr [rsp+60h+var_40], ax; __int16
0x180063ce9  call    ?ValidateAllocationDescriptor@FILE_ICB_DESCRIPTOR@@AEAAEGKKFE@Z; FILE_ICB_DESCRIPTOR::ValidateAllocationDescriptor(ushort,ulong,ulong,short,uchar)
0x180063cee  test    al, al
0x180063cf0  jnz     short loc_180063CFC
0x180063cf2  test    rdi, rdi
0x180063cf5  jz      short loc_180063CB1
0x180063cf7  mov     byte ptr [rdi], 1
0x180063cfa  jmp     short loc_180063CB1
0x180063cfc  mov     esi, 1
0x180063d01  mov     rax, [r14+10h]
0x180063d05  movzx   ecx, word ptr [rax+22h]
0x180063d09  and     cx, 7
0x180063d0d  jnz     short loc_180063D16
0x180063d0f  mov     eax, 8
0x180063d14  jmp     short loc_180063D24
0x180063d16  mov     eax, 14h
0x180063d1b  cmp     cx, si
0x180063d1e  lea     edx, [rax-4]
0x180063d21  cmovz   eax, edx
0x180063d24  add     [r14+44h], eax
0x180063d28  lea     rcx, [rbp+var_28]; this
0x180063d2c  call    ??1DESCRIPTOR@@UEAA@XZ; DESCRIPTOR::~DESCRIPTOR(void)
0x180063d31  mov     al, sil
0x180063d34  jmp     short loc_180063CBC
```
