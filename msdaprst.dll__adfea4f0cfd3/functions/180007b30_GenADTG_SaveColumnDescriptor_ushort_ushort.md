# GenADTG::SaveColumnDescriptor(ushort,ushort)

- ea: `0x180007b30`
- end: `0x1800081a3`
- name: `?SaveColumnDescriptor@GenADTG@@QEAAHGG@Z`
- size: `1651`
- prototype: `__int64 __fastcall(GenADTG *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x180009394`

## callees

- `0x180002728`
- `0x180002de4`
- `0x180002e2c`
- `0x180002e74`
- `0x180002ebc`
- `0x180002f4c`
- `0x180002f94`
- `0x180003c38`
- `0x1800041b4`
- `0x180004224`
- `0x180004268`
- `0x1800042b0`
- `0x1800042f4`
- `0x180004338`
- `0x180004384`
- `0x180007b30`
- `0x18000943c`
- `0x180009678`
- `0x1800098d4`
- `0x18002dc20`

## pseudocode

```c
__int64 __fastcall GenADTG::SaveColumnDescriptor(GenADTG *this, unsigned __int16 a2, __int16 a3)
{
  __int64 v3; // rsi
  CMetaData *v4; // r14
  __int64 v6; // rdi
  CMetaData *v7; // rcx
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // dx
  int Precision; // r13d
  unsigned __int16 v11; // dx
  unsigned __int16 v12; // dx
  unsigned int Flags; // eax
  unsigned __int16 v14; // dx
  const unsigned __int16 *v15; // r10
  __int16 v16; // r11
  const unsigned __int16 *v17; // r15
  __int64 v19; // rcx
  __int16 v20; // r9
  unsigned __int16 *BaseColumnName; // rax
  __int16 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rax
  __int16 v25; // r11
  unsigned __int16 v26; // r10
  unsigned __int16 v27; // ax
  __int16 RelationConditionsSize; // ax
  __int16 v29; // r10
  __int64 v30; // rax
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *BaseCatalogName; // rax
  const unsigned __int16 *BaseSchemaName; // rax
  __int64 v34; // rcx
  __int64 v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  const unsigned __int8 *RelationConditions; // rax
  const unsigned __int8 *CalculationInfo; // rax
  unsigned __int16 v50[2]; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int8 v51[4]; // [rsp+24h] [rbp-2Ch] BYREF
  unsigned __int8 v52; // [rsp+28h] [rbp-28h] BYREF
  __int16 v53; // [rsp+29h] [rbp-27h]
  unsigned __int8 v54[4]; // [rsp+2Ch] [rbp-24h] BYREF
  unsigned __int8 v55[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 v56[4]; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned __int8 v57[4]; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v58[4]; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned __int8 v59[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 v60[12]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned __int8 v61; // [rsp+90h] [rbp+40h] BYREF
  __int16 v62; // [rsp+A0h] [rbp+50h] BYREF
  int v63; // [rsp+A8h] [rbp+58h] BYREF

  v62 = a3;
  v3 = a2;
  v61 = 6;
  v4 = (GenADTG *)((char *)this + 128);
  v50[0] = 25;
  *(_DWORD *)v60 = 0;
  v6 = -1;
  *(_DWORD *)v59 = 0;
  *(_WORD *)v55 = -1;
  *(_DWORD *)v54 = 0;
  CMetaData::mdGetName((GenADTG *)((char *)this + 128), a2);
  *(_WORD *)v51 = CMetaData::mdGetType(v7, v3);
  *(_DWORD *)v58 = CMetaData::mdGetSize(v4, v8);
  Precision = CMetaData::mdGetPrecision(v4, v9);
  LOBYTE(v63) = CMetaData::mdGetScale(v4, v11);
  Flags = CMetaData::mdGetFlags(v4, v12);
  *(_DWORD *)v56 = Flags;
  v17 = (const unsigned __int16 *)&dword_180037304;
  if ( v15 )
    v17 = v15;
  if ( *((_DWORD *)this + 50) && ((Flags & 0x2000) != 0 || v16 == 136) )
    return 0;
  v19 = *((_QWORD *)this + 21);
  v53 = 0;
  v52 = 0x80;
  if ( v19 && *(_WORD *)(v19 + 4 * v3 + 2) )
  {
    v52 = -16;
    v50[0] = 31;
    if ( CMetaData::mdGetBaseColumnName(v4, v14) )
    {
      BaseColumnName = CMetaData::mdGetBaseColumnName(v4, v3);
      v23 = -1;
      do
        ++v23;
      while ( BaseColumnName[v23] );
      v50[0] = v22 + 2 * v23;
    }
    else
    {
      v24 = -1;
      do
        ++v24;
      while ( v17[v24] );
      v50[0] = v20 + 2 * v24;
    }
  }
  GenADTG::SetOptionalColumnsMap(this, v3, &v52, v50);
  do
    ++v6;
  while ( v17[v6] );
  v25 = 4;
  v26 = v50[0] + 2 * (v6 + 1);
  v50[0] = v26;
  if ( *((_DWORD *)this + 71) != 1 )
  {
    v26 += 4;
    v50[0] = v26;
  }
  v27 = v26;
  if ( ((*(_WORD *)v56 & 0x2000) != 0 || *(_WORD *)v51 == 136) && !*((_DWORD *)this + 50) )
  {
    v50[0] = v26 + 4;
    RelationConditionsSize = CMetaData::mdGetRelationConditionsSize(v4, v3);
    v27 = v25 + v29 + RelationConditionsSize;
    v50[0] = v27;
  }
  if ( ((unsigned __int8)v25 & HIBYTE(v53)) != 0 )
    v50[0] = v25 + v27;
  GenADTG::SaveToBuffer(this, &v61, 1u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)v50, 2u);
  GenADTG::SaveToBuffer(this, &v52, 3u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v62, 2u);
  GenADTG::SaveString(this, v17);
  v30 = *((_QWORD *)this + 21);
  if ( v30 && *(_WORD *)(v30 + 4 * v3 + 2) )
  {
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(*((_QWORD *)v4 + 5) + 4 * v3), 2u);
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(*((_QWORD *)this + 21) + 2LL + 4 * v3), 2u);
    if ( CMetaData::mdGetBaseColumnName(v4, v3) )
      v31 = CMetaData::mdGetBaseColumnName(v4, v3);
    else
      v31 = v17;
    GenADTG::SaveString(this, v31);
  }
  GenADTG::SaveToBuffer(this, v51, 2u);
  GenADTG::SaveToBuffer(this, v58, 4u);
  *(_DWORD *)v59 = Precision;
  GenADTG::SaveToBuffer(this, v59, 4u);
  *(_DWORD *)v60 = (unsigned __int8)v63;
  GenADTG::SaveToBuffer(this, v60, 4u);
  GenADTG::SaveToBuffer(this, v56, 4u);
  if ( CMetaData::mdGetBaseCatalogName(v4, v3) )
  {
    BaseCatalogName = CMetaData::mdGetBaseCatalogName(v4, v3);
    GenADTG::SaveString(this, BaseCatalogName);
  }
  if ( CMetaData::mdGetBaseSchemaName(v4, v3) )
  {
    BaseSchemaName = CMetaData::mdGetBaseSchemaName(v4, v3);
    GenADTG::SaveString(this, BaseSchemaName);
  }
  v34 = *((_QWORD *)this + 20);
  if ( v34 )
  {
    v35 = 9648 * v3;
    if ( !*(_DWORD *)(9648 * v3 + v34 + 6364) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v34 + 6360), 4u);
    v36 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v36 + v35 + 6356) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v36 + 6352), 4u);
    v37 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v37 + v35 + 6372) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v37 + 6368), 4u);
    v38 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v38 + v35 + 6400) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v38 + 6376), 0x18u);
    v39 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v39 + v35 + 7432) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v39 + 6404));
    v40 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v40 + v35 + 8476) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v40 + 7448));
    v41 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v41 + v35 + 9516) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v41 + 8488));
  }
  *(_WORD *)v57 = CMetaData::mdGetAutoIncrement(v4, v3);
  GenADTG::SaveToBuffer(this, v57, 2u);
  v42 = *((_QWORD *)this + 20);
  if ( v42 )
  {
    v43 = 9648 * v3;
    if ( !*(_DWORD *)(9648 * v3 + v42 + 9540) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v42 + 9536), 2u);
    v44 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v44 + v43 + 9548) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v44 + 9544), 4u);
    v45 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v45 + v43 + 9556) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v45 + 9552), 2u);
    v46 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v46 + v43 + 9568) )
    {
      v63 = 0;
      v63 = DownsizeToULONGThrow<unsigned __int64>(*(_QWORD *)(v46 + v43 + 9560));
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v63, 4u);
    }
    v47 = *((_QWORD *)this + 20);
    if ( *(_DWORD *)(v47 + v43 + 2160)
      || !(unsigned int)IsSame((const struct _GUID *)(v43 + v47 + 2144), &DBCOL_SPECIALCOL) )
    {
      goto LABEL_65;
    }
    goto LABEL_64;
  }
  if ( (unsigned __int16)v3 >= *((_WORD *)this + 65) )
LABEL_64:
    *(_WORD *)v55 = 0;
LABEL_65:
  GenADTG::SaveToBuffer(this, v55, 2u);
  if ( *((_DWORD *)this + 71) != 1 )
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)this + 284, 4u);
  if ( ((*(_WORD *)v56 & 0x2000) != 0 || *(_WORD *)v51 == 136) && !*((_DWORD *)this + 50) )
  {
    *(_DWORD *)v54 = CMetaData::mdGetRelationConditionsSize(v4, v3);
    GenADTG::SaveToBuffer(this, v54, 4u);
    RelationConditions = CMetaData::mdGetRelationConditions(v4, v3);
    GenADTG::SaveToBuffer(this, RelationConditions, *(unsigned int *)v54);
    *(_DWORD *)v54 = 0;
    GenADTG::SaveToBuffer(this, v54, 4u);
  }
  if ( (v53 & 0x400) != 0 )
  {
    *(_DWORD *)v54 = CMetaData::mdGetCalculationInfoSize(v4, v3);
    GenADTG::SaveToBuffer(this, v54, 4u);
    CalculationInfo = CMetaData::mdGetCalculationInfo(v4, v3);
    GenADTG::SaveToBuffer(this, CalculationInfo, *(unsigned int *)v54);
  }
  return 1;
}

```

## disassembly

```asm
0x180007b30  mov     [rsp-38h+arg_8], rbx
0x180007b35  mov     [rsp-38h+arg_10], r8w
0x180007b3b  push    rbp
0x180007b3c  push    rsi
0x180007b3d  push    rdi
0x180007b3e  push    r12
0x180007b40  push    r13
0x180007b42  push    r14
0x180007b44  push    r15
0x180007b46  mov     rbp, rsp
0x180007b49  sub     rsp, 50h
0x180007b4d  xor     r12d, r12d
0x180007b50  movzx   esi, dx
0x180007b53  mov     eax, 19h
0x180007b58  mov     [rbp+arg_0], 6
0x180007b5c  lea     r14, [rcx+80h]
0x180007b63  mov     [rbp+var_30], ax
0x180007b67  mov     rbx, rcx
0x180007b6a  mov     dword ptr [rbp+var_C], r12d
0x180007b6e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007b72  mov     dword ptr [rbp+var_10], r12d
0x180007b76  movzx   edx, si; unsigned __int16
0x180007b79  mov     word ptr [rbp+var_20], di
0x180007b7d  mov     rcx, r14; this
0x180007b80  mov     dword ptr [rbp+var_1C], r12d
0x180007b84  mov     dword ptr [rbp+var_14], r12d
0x180007b88  mov     word ptr [rbp+var_2C], r12w
0x180007b8d  mov     dword ptr [rbp+var_24], r12d
0x180007b91  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180007b96  movzx   edx, si; unsigned __int16
0x180007b99  mov     r10, rax
0x180007b9c  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180007ba1  mov     rcx, r14; this
0x180007ba4  mov     word ptr [rbp+var_2C], ax
0x180007ba8  movzx   r11d, ax
0x180007bac  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x180007bb1  mov     rcx, r14; this
0x180007bb4  mov     dword ptr [rbp+var_14], eax
0x180007bb7  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x180007bbc  mov     rcx, r14; this
0x180007bbf  movzx   r13d, al
0x180007bc3  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x180007bc8  mov     rcx, r14; this
0x180007bcb  mov     byte ptr [rbp+arg_18], al
0x180007bce  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180007bd3  test    r10, r10
0x180007bd6  mov     dword ptr [rbp+var_1C], eax
0x180007bd9  lea     r15, dword_180037304
0x180007be0  mov     ecx, 88h
0x180007be5  cmovnz  r15, r10
0x180007be9  cmp     [rbx+0C8h], r12d
0x180007bf0  jz      short loc_180007C05
0x180007bf2  bt      eax, 0Dh
0x180007bf6  jb      short loc_180007BFE
0x180007bf8  cmp     r11w, cx
0x180007bfc  jnz     short loc_180007C05
0x180007bfe  xor     eax, eax
0x180007c00  jmp     loc_18000818A
0x180007c05  mov     rcx, [rbx+0A8h]
0x180007c0c  mov     [rbp+var_27], r12w
0x180007c11  mov     [rbp+var_28], 80h
0x180007c15  test    rcx, rcx
0x180007c18  jz      short loc_180007C7B
0x180007c1a  cmp     [rcx+rsi*4+2], r12w
0x180007c20  jz      short loc_180007C7B
0x180007c22  mov     r9d, 1Fh
0x180007c28  mov     [rbp+var_28], 0F0h
0x180007c2c  mov     rcx, r14; this
0x180007c2f  mov     [rbp+var_30], r9w
0x180007c34  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007c39  test    rax, rax
0x180007c3c  jz      short loc_180007C63
0x180007c3e  movzx   edx, si; unsigned __int16
0x180007c41  mov     rcx, r14; this
0x180007c44  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007c49  mov     rcx, rdi
0x180007c4c  inc     rcx
0x180007c4f  cmp     [rax+rcx*2], r12w
0x180007c54  jnz     short loc_180007C4C
0x180007c56  add     cx, cx
0x180007c59  add     cx, r9w
0x180007c5d  mov     [rbp+var_30], cx
0x180007c61  jmp     short loc_180007C7B
0x180007c63  mov     rax, rdi
0x180007c66  inc     rax
0x180007c69  cmp     [r15+rax*2], r12w
0x180007c6e  jnz     short loc_180007C66
0x180007c70  add     ax, ax
0x180007c73  add     ax, r9w
0x180007c77  mov     [rbp+var_30], ax
0x180007c7b  lea     r9, [rbp+var_30]; unsigned __int16 *
0x180007c7f  movzx   edx, si; unsigned __int16
0x180007c82  lea     r8, [rbp+var_28]; unsigned __int8 *
0x180007c86  mov     rcx, rbx; this
0x180007c89  call    ?SetOptionalColumnsMap@GenADTG@@AEAAXGPEAEPEAG@Z; GenADTG::SetOptionalColumnsMap(ushort,uchar *,ushort *)
0x180007c8e  inc     rdi
0x180007c91  cmp     [r15+rdi*2], r12w
0x180007c96  jnz     short loc_180007C8E
0x180007c98  mov     ecx, 1
0x180007c9d  lea     r12, [rbx+11Ch]
0x180007ca4  add     di, cx
0x180007ca7  lea     r11d, [rcx+3]
0x180007cab  lea     r10d, [rdi+rdi]
0x180007caf  add     r10w, [rbp+var_30]
0x180007cb4  mov     [rbp+var_30], r10w
0x180007cb9  cmp     [r12], ecx
0x180007cbd  jz      short loc_180007CC8
0x180007cbf  add     r10w, r11w
0x180007cc3  mov     [rbp+var_30], r10w
0x180007cc8  test    dword ptr [rbp+var_1C], 2000h
0x180007ccf  movzx   eax, r10w
0x180007cd3  jnz     short loc_180007CE0
0x180007cd5  mov     edx, 88h
0x180007cda  cmp     word ptr [rbp+var_2C], dx
0x180007cde  jnz     short loc_180007D0E
0x180007ce0  cmp     dword ptr [rbx+0C8h], 0
0x180007ce7  jnz     short loc_180007D0E
0x180007ce9  add     r10w, r11w
0x180007ced  movzx   edx, si; unsigned __int16
0x180007cf0  mov     rcx, r14; this
0x180007cf3  mov     [rbp+var_30], r10w
0x180007cf8  call    ?mdGetRelationConditionsSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetRelationConditionsSize(ushort)
0x180007cfd  add     ax, r10w
0x180007d01  mov     ecx, 1
0x180007d06  add     ax, r11w
0x180007d0a  mov     [rbp+var_30], ax
0x180007d0e  test    byte ptr [rbp+var_27+1], r11b
0x180007d12  jz      short loc_180007D1C
0x180007d14  add     ax, r11w
0x180007d18  mov     [rbp+var_30], ax
0x180007d1c  mov     r8d, ecx; unsigned int
0x180007d1f  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x180007d23  mov     rcx, rbx; this
0x180007d26  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d2b  mov     r8d, 2; unsigned int
0x180007d31  lea     rdx, [rbp+var_30]; unsigned __int8 *
0x180007d35  mov     rcx, rbx; this
0x180007d38  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d3d  mov     r8d, 3; unsigned int
0x180007d43  lea     rdx, [rbp+var_28]; unsigned __int8 *
0x180007d47  mov     rcx, rbx; this
0x180007d4a  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d4f  mov     r8d, 2; unsigned int
0x180007d55  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x180007d59  mov     rcx, rbx; this
0x180007d5c  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d61  mov     rdx, r15; unsigned __int16 *
0x180007d64  mov     rcx, rbx; this
0x180007d67  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007d6c  mov     rax, [rbx+0A8h]
0x180007d73  xor     ecx, ecx
0x180007d75  test    rax, rax
0x180007d78  jz      short loc_180007DDD
0x180007d7a  cmp     [rax+rsi*4+2], cx
0x180007d7f  jz      short loc_180007DDD
0x180007d81  mov     rax, [r14+28h]
0x180007d85  lea     r8d, [rcx+2]; unsigned int
0x180007d89  mov     rcx, rbx; this
0x180007d8c  lea     rdx, [rax+rsi*4]; unsigned __int8 *
0x180007d90  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d95  mov     rdx, [rbx+0A8h]
0x180007d9c  mov     r8d, 2; unsigned int
0x180007da2  add     rdx, 2
0x180007da6  mov     rcx, rbx; this
0x180007da9  lea     rdx, [rdx+rsi*4]; unsigned __int8 *
0x180007dad  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007db2  movzx   edx, si; unsigned __int16
0x180007db5  mov     rcx, r14; this
0x180007db8  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007dbd  test    rax, rax
0x180007dc0  jz      short loc_180007DD2
0x180007dc2  movzx   edx, si; unsigned __int16
0x180007dc5  mov     rcx, r14; this
0x180007dc8  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007dcd  mov     rdx, rax
0x180007dd0  jmp     short loc_180007DD5
0x180007dd2  mov     rdx, r15; unsigned __int16 *
0x180007dd5  mov     rcx, rbx; this
0x180007dd8  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007ddd  mov     r8d, 2; unsigned int
0x180007de3  lea     rdx, [rbp+var_2C]; unsigned __int8 *
0x180007de7  mov     rcx, rbx; this
0x180007dea  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007def  mov     r8d, 4; unsigned int
0x180007df5  lea     rdx, [rbp+var_14]; unsigned __int8 *
0x180007df9  mov     rcx, rbx; this
0x180007dfc  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007e01  mov     dword ptr [rbp+var_10], r13d
0x180007e05  lea     rdx, [rbp+var_10]; unsigned __int8 *
0x180007e09  mov     r13d, 4
0x180007e0f  mov     rcx, rbx; this
0x180007e12  mov     r8d, r13d; unsigned int
0x180007e15  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007e1a  movzx   eax, byte ptr [rbp+arg_18]
0x180007e1e  lea     rdx, [rbp+var_C]; unsigned __int8 *
0x180007e22  mov     r8d, r13d; unsigned int
0x180007e25  mov     dword ptr [rbp+var_C], eax
0x180007e28  mov     rcx, rbx; this
0x180007e2b  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007e30  mov     r8d, r13d; unsigned int
0x180007e33  lea     rdx, [rbp+var_1C]; unsigned __int8 *
0x180007e37  mov     rcx, rbx; this
0x180007e3a  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007e3f  movzx   edx, si; unsigned __int16
0x180007e42  mov     rcx, r14; this
0x180007e45  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x180007e4a  xor     r15d, r15d
0x180007e4d  test    rax, rax
0x180007e50  jz      short loc_180007E68
0x180007e52  movzx   edx, si; unsigned __int16
0x180007e55  mov     rcx, r14; this
0x180007e58  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x180007e5d  mov     rdx, rax; unsigned __int16 *
0x180007e60  mov     rcx, rbx; this
0x180007e63  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007e68  movzx   edx, si; unsigned __int16
0x180007e6b  mov     rcx, r14; this
0x180007e6e  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x180007e73  test    rax, rax
0x180007e76  jz      short loc_180007E8E
0x180007e78  movzx   edx, si; unsigned __int16
0x180007e7b  mov     rcx, r14; this
0x180007e7e  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x180007e83  mov     rdx, rax; unsigned __int16 *
0x180007e86  mov     rcx, rbx; this
0x180007e89  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007e8e  mov     rcx, [rbx+0A0h]
0x180007e95  test    rcx, rcx
0x180007e98  jz      loc_180007FA2
0x180007e9e  imul    rdi, rsi, 25B0h
0x180007ea5  cmp     [rdi+rcx+18DCh], r15d
0x180007ead  jnz     short loc_180007EC4
0x180007eaf  lea     rdx, [rcx+18D8h]
0x180007eb6  mov     r8d, r13d; unsigned int
0x180007eb9  add     rdx, rdi; unsigned __int8 *
0x180007ebc  mov     rcx, rbx; this
0x180007ebf  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007ec4  mov     rax, [rbx+0A0h]
0x180007ecb  cmp     [rax+rdi+18D4h], r15d
0x180007ed3  jnz     short loc_180007EEA
0x180007ed5  lea     rdx, [rax+18D0h]
0x180007edc  mov     r8d, r13d; unsigned int
0x180007edf  add     rdx, rdi; unsigned __int8 *
0x180007ee2  mov     rcx, rbx; this
0x180007ee5  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007eea  mov     rax, [rbx+0A0h]
0x180007ef1  cmp     [rax+rdi+18E4h], r15d
0x180007ef9  jnz     short loc_180007F10
0x180007efb  lea     rdx, [rax+18E0h]
0x180007f02  mov     r8d, r13d; unsigned int
0x180007f05  add     rdx, rdi; unsigned __int8 *
0x180007f08  mov     rcx, rbx; this
0x180007f0b  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007f10  mov     rax, [rbx+0A0h]
0x180007f17  cmp     [rax+rdi+1900h], r15d
0x180007f1f  jnz     short loc_180007F39
0x180007f21  lea     rdx, [rax+18E8h]
0x180007f28  mov     r8d, 18h; unsigned int
0x180007f2e  add     rdx, rdi; unsigned __int8 *
0x180007f31  mov     rcx, rbx; this
0x180007f34  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007f39  mov     rax, [rbx+0A0h]
0x180007f40  cmp     [rax+rdi+1D08h], r15d
0x180007f48  jnz     short loc_180007F5C
0x180007f4a  lea     rdx, [rax+1904h]
0x180007f51  mov     rcx, rbx; this
0x180007f54  add     rdx, rdi; unsigned __int16 *
0x180007f57  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007f5c  mov     rax, [rbx+0A0h]
0x180007f63  cmp     [rax+rdi+211Ch], r15d
0x180007f6b  jnz     short loc_180007F7F
0x180007f6d  lea     rdx, [rax+1D18h]
0x180007f74  mov     rcx, rbx; this
0x180007f77  add     rdx, rdi; unsigned __int16 *
0x180007f7a  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007f7f  mov     rax, [rbx+0A0h]
0x180007f86  cmp     [rax+rdi+252Ch], r15d
0x180007f8e  jnz     short loc_180007FA2
0x180007f90  lea     rdx, [rax+2128h]
0x180007f97  mov     rcx, rbx; this
0x180007f9a  add     rdx, rdi; unsigned __int16 *
0x180007f9d  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007fa2  movzx   edx, si; unsigned __int16
0x180007fa5  mov     rcx, r14; this
0x180007fa8  call    ?mdGetAutoIncrement@CMetaData@@QEAAFG@Z; CMetaData::mdGetAutoIncrement(ushort)
0x180007fad  mov     r8d, 2; unsigned int
0x180007fb3  mov     word ptr [rbp+var_18], ax
0x180007fb7  mov     rcx, rbx; this
0x180007fba  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x180007fbe  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007fc3  mov     rcx, [rbx+0A0h]
0x180007fca  test    rcx, rcx
0x180007fcd  jz      loc_1800080AC
0x180007fd3  imul    rdi, rsi, 25B0h
0x180007fda  cmp     [rdi+rcx+2544h], r15d
0x180007fe2  jnz     short loc_180007FFC
0x180007fe4  lea     rdx, [rcx+2540h]
0x180007feb  mov     r8d, 2; unsigned int
0x180007ff1  add     rdx, rdi; unsigned __int8 *
0x180007ff4  mov     rcx, rbx; this
  ... truncated ...
```
