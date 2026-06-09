# FILE_ICB_DESCRIPTOR::WriteData(void const *,unsigned __int64,ulong,ulong *,SPACE_BITMAP_DESCRIPTOR *)

- ea: `0x180065a58`
- end: `0x1800663b8`
- name: `?WriteData@FILE_ICB_DESCRIPTOR@@QEAAEPEBX_KKPEAKPEAVSPACE_BITMAP_DESCRIPTOR@@@Z`
- size: `2400`
- prototype: `unsigned __int8 __usercall@<al>(FILE_ICB_DESCRIPTOR *__hidden this@<rcx>, const void *@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, unsigned int *, struct SPACE_BITMAP_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180060ea8`
- `0x18006259c`
- `0x180062ba0`
- `0x18006eec4`

## callees

- `0x1800251f6`
- `0x180028568`
- `0x18005fae0`
- `0x180061a18`
- `0x18006259c`
- `0x180062ba0`
- `0x180065a58`
- `0x180067f4c`
- `0x180069d74`
- `0x18006d758`
- `0x18006da80`
- `0x18006dae8`
- `0x18008170e`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180065e16`
- `ntdll!RtlFreeHeap` at `0x180065e16`
- `ntdll!RtlAllocateHeap` at `0x180065d4c`
- `ntdll!RtlAllocateHeap` at `0x180065d4c`

## pseudocode

```c
char __fastcall FILE_ICB_DESCRIPTOR::WriteData(
        FILE_ICB_DESCRIPTOR *this,
        char *a2,
        size_t a3,
        unsigned int a4,
        unsigned int *a5,
        struct SPACE_BITMAP_DESCRIPTOR *a6)
{
  __int64 v6; // rax
  __int64 v7; // r14
  UDF_SA **v10; // rdx
  __int64 v11; // r13
  UDF_EXTENT_LIST **v12; // rbx
  char v13; // al
  __int64 v14; // rax
  unsigned int SectorSize; // r12d
  unsigned int v16; // ecx
  char v17; // r8
  __int64 v18; // r15
  unsigned int *v19; // rbx
  __int64 v20; // r14
  __int64 v21; // rbx
  struct UDF_LVOL *v22; // rdx
  struct SPACE_BITMAP_DESCRIPTOR *v23; // rbx
  size_t v24; // rbx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  char v27; // bl
  unsigned __int64 v28; // rdx
  char *Heap; // r14
  unsigned __int16 v30; // cx
  unsigned int *v31; // rax
  __int64 v32; // rcx
  unsigned int v33; // r15d
  unsigned __int64 v34; // rdx
  unsigned int v35; // ebx
  unsigned int v36; // eax
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  unsigned int v39; // r15d
  __int64 v40; // r15
  unsigned int v41; // ebx
  size_t v42; // rbx
  UDF_EXTENT_LIST *v43; // rcx
  unsigned int v44; // r15d
  unsigned int v45; // ecx
  unsigned __int64 v46; // r15
  unsigned int v47; // r8d
  unsigned int v49; // [rsp+30h] [rbp-40h] BYREF
  char v50; // [rsp+34h] [rbp-3Ch]
  unsigned int v51; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v52; // [rsp+3Ch] [rbp-34h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v54; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v55; // [rsp+48h] [rbp-28h]
  unsigned int v56[2]; // [rsp+50h] [rbp-20h]
  size_t v57; // [rsp+58h] [rbp-18h]
  unsigned int v58[2]; // [rsp+60h] [rbp-10h]

  v6 = *((_QWORD *)this + 4);
  v7 = a4;
  v10 = (UDF_SA **)(v6 + 32);
  if ( v6 )
    v55 = (*(_DWORD *)(*((_QWORD *)*v10 + 6) + 360LL) & 8) != 0 ? 16 : 32;
  else
    v55 = 16;
  v11 = *((_QWORD *)this + 2);
  v12 = (UDF_EXTENT_LIST **)((char *)this + 40);
  v49 = 0;
  v53 = 0;
  v54 = 0;
  v13 = *(_BYTE *)(v11 + 34) & 7;
  v51 = 0;
  v52 = 0;
  *(_QWORD *)v56 = (char *)this + 40;
  if ( v13 == 3 )
  {
    v14 = 172;
    SectorSize = 0;
    if ( *(_WORD *)v11 != 261 )
      v14 = 212;
    v16 = *(_DWORD *)(v14 + v11);
  }
  else
  {
    SectorSize = UDF_SA::QuerySectorSize(*v10);
    if ( !UDF_EXTENT_LIST::QueryInformationLength(*v12, &v51) )
      return 0;
    *(_QWORD *)v56 = (char *)this + 40;
    v16 = v51 * SectorSize;
  }
  v17 = a3 + v7;
  v57 = a3 + v7;
  v18 = 176;
  if ( v16 < a3 + v7 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 34LL) & 7) != 3 )
      goto LABEL_19;
    v19 = (unsigned int *)(v11 + 168);
    v20 = 176;
    if ( *(_WORD *)v11 != 261 )
    {
      v20 = 216;
      v19 = (unsigned int *)(v11 + 208);
    }
    v21 = *v19;
    if ( a3 + a4 + v20 + v21 > UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 4) + 32LL)) )
    {
      v22 = (struct UDF_LVOL *)*((_QWORD *)this + 4);
      if ( !v22 )
        return 0;
      v23 = a6;
      if ( !a6 || !FILE_ICB_DESCRIPTOR::ConvertToNonImmediateAllocDesc(this, v22) )
        return 0;
    }
    else
    {
LABEL_19:
      v23 = a6;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(FILE_ICB_DESCRIPTOR *, size_t, struct SPACE_BITMAP_DESCRIPTOR *, __int64, int))(*(_QWORD *)this + 72LL))(
            this,
            v57,
            v23,
            1,
            1) )
      return 0;
    if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 34LL) & 7) != 3 )
    {
      SectorSize = UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 4) + 32LL));
      if ( !UDF_EXTENT_LIST::QueryInformationLength(*((UDF_EXTENT_LIST **)this + 5), &v51) )
        return 0;
    }
  }
  v24 = *(_QWORD *)(v11 + 56);
  if ( v24 < a3 )
  {
    if ( (a3 - v24) >> 32 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v26 = 22;
      goto LABEL_28;
    }
    v28 = *(_QWORD *)(v11 + 56);
    *(_QWORD *)(v11 + 56) = a3;
    if ( !FILE_ICB_DESCRIPTOR::Fill(this, v28, v17, a3 - v24) )
    {
      *(_QWORD *)(v11 + 56) = v24;
      return 0;
    }
  }
  Heap = 0;
  v30 = *(_WORD *)(*((_QWORD *)this + 2) + 34LL) & 7;
  if ( v30 == 3 )
  {
    if ( *(_WORD *)v11 != 261 )
      v18 = 216;
    v31 = (unsigned int *)(v11 + 168);
    if ( *(_WORD *)v11 != 261 )
      v31 = (unsigned int *)(v11 + 208);
    v32 = v18 + *v31;
    v33 = a4;
    memcpy_0((void *)(a3 + v11 + v32), a2, a4);
    a3 = v57;
    *((_BYTE *)this + 100) = 1;
    goto LABEL_138;
  }
  if ( v30 >= 2u )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids);
    return 0;
  }
  v33 = a4;
  if ( a4 )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v55 * SectorSize);
    if ( !Heap )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v26 = 23;
LABEL_28:
      WPP_SF_(v25[2], v26, &WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids);
      return 0;
    }
    v50 = 0;
    v34 = a3 % SectorSize;
    v35 = v34;
    if ( (_DWORD)v34 )
    {
      v36 = SectorSize - v34;
      if ( a4 < SectorSize - (unsigned int)v34 )
        v36 = a4;
      LODWORD(v57) = v36;
      *(_QWORD *)v58 = a3 / SectorSize;
      if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(**(UDF_EXTENT_LIST ***)v56, v58[0], &v49, &v53) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_56;
        v38 = 24;
        goto LABEL_55;
      }
      v39 = v49;
      v51 = v49;
      if ( v49 == -1 )
      {
        if ( !a6
          || !(*(unsigned __int8 (__fastcall **)(struct SPACE_BITMAP_DESCRIPTOR *, _QWORD, __int64, unsigned int *, int))(*(_QWORD *)a6 + 48LL))(
                a6,
                0,
                1,
                &v49,
                1)
          || !UDF_EXTENT_LIST::AddExtent(**(UDF_EXTENT_LIST ***)v56, v58[0], v49, 1u) )
        {
          goto LABEL_56;
        }
        *((_BYTE *)this + 101) = 1;
        v50 = 1;
        v39 = v49;
        v51 = v49;
      }
      if ( !UDF_LVOL::Read(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v39, 1u, Heap) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_56;
        v38 = 25;
        goto LABEL_55;
      }
      if ( v50 )
        memset_0(Heap, 0, v35);
      v40 = (unsigned int)v57;
      memcpy_0(&Heap[v35], a2, (unsigned int)v57);
      if ( !UDF_LVOL::Write(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v49, 1u, Heap) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_56;
        v38 = 26;
LABEL_55:
        WPP_SF_(v37[2], v38, &WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids);
        goto LABEL_56;
      }
      v41 = v58[0];
      if ( UDF_EXTENT_LIST::QueryLbnFromVbn(*((UDF_EXTENT_LIST **)this + 6), v58[0], &v52, &v54) )
      {
        if ( v52 == -1 )
        {
          if ( !UDF_EXTENT_LIST::AddExtent(*((UDF_EXTENT_LIST **)this + 6), v41, v49, 1u) )
            goto LABEL_56;
          *((_BYTE *)this + 101) = 1;
        }
        v42 = a4 - (unsigned int)v57;
        a2 += v40;
        a3 += v40;
        goto LABEL_82;
      }
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v38 = 27;
        goto LABEL_55;
      }
LABEL_56:
      v27 = 0;
LABEL_57:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return v27;
    }
    v42 = a4;
    v51 = 0;
LABEL_82:
    while ( (unsigned int)v42 >= SectorSize )
    {
      v43 = (UDF_EXTENT_LIST *)*((_QWORD *)this + 5);
      *(_QWORD *)v56 = a3 / SectorSize;
      if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(v43, v56[0], &v49, &v53) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 28;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      v44 = v53;
      if ( v53 > v55 )
        v44 = v55;
      if ( v44 * SectorSize > (unsigned int)v42 )
        v44 = (unsigned int)v42 / SectorSize;
      v45 = v49;
      if ( v49 == -1 )
      {
        if ( !a6
          || !(*(unsigned __int8 (__fastcall **)(struct SPACE_BITMAP_DESCRIPTOR *, _QWORD, _QWORD, unsigned int *, int))(*(_QWORD *)a6 + 48LL))(
                a6,
                v51,
                v44,
                &v49,
                1)
          || !UDF_EXTENT_LIST::AddExtent(*((UDF_EXTENT_LIST **)this + 5), v56[0], v49, v44) )
        {
          goto LABEL_56;
        }
        v45 = v49;
        *((_BYTE *)this + 101) = 1;
      }
      v51 = v45;
      *(_QWORD *)v58 = v44 * SectorSize;
      memcpy_0(Heap, a2, *(size_t *)v58);
      if ( !UDF_LVOL::Write(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v49, v44, Heap) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 29;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(*((UDF_EXTENT_LIST **)this + 6), v56[0], &v52, &v54) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 30;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      if ( v52 == -1 || v54 < v44 )
      {
        if ( !UDF_EXTENT_LIST::AddExtent(*((UDF_EXTENT_LIST **)this + 6), v56[0], v49, v44) )
          goto LABEL_56;
        *((_BYTE *)this + 101) = 1;
      }
      a2 += *(_QWORD *)v58;
      v42 = (unsigned int)(v42 - v58[0]);
      a3 += *(_QWORD *)v58;
    }
    if ( (_DWORD)v42 )
    {
      v46 = a3 / SectorSize;
      if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(*((UDF_EXTENT_LIST **)this + 5), v46, &v49, &v53) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 31;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      v47 = v49;
      if ( v49 == -1 )
      {
        if ( !a6
          || !(*(unsigned __int8 (__fastcall **)(struct SPACE_BITMAP_DESCRIPTOR *, _QWORD, __int64, unsigned int *, int))(*(_QWORD *)a6 + 48LL))(
                a6,
                v51,
                1,
                &v49,
                1)
          || !UDF_EXTENT_LIST::AddExtent(*((UDF_EXTENT_LIST **)this + 5), v46, v49, 1u) )
        {
          goto LABEL_56;
        }
        v47 = v49;
        *((_BYTE *)this + 101) = 1;
        v50 = 1;
      }
      if ( !UDF_LVOL::Read(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v47, 1u, Heap) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 32;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      if ( v50 )
        memset_0(&Heap[(unsigned int)v42], 0, SectorSize - (unsigned int)v42);
      memcpy_0(Heap, a2, v42);
      if ( !UDF_LVOL::Write(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v49, 1u, Heap) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 33;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(*((UDF_EXTENT_LIST **)this + 6), v46, &v52, &v54) )
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v38 = 34;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
      if ( v52 == -1 )
      {
        if ( !UDF_EXTENT_LIST::AddExtent(*((UDF_EXTENT_LIST **)this + 6), v46, v49, 1u) )
          goto LABEL_56;
        *((_BYTE *)this + 101) = 1;
      }
      a3 += v42;
    }
    v33 = a4;
  }
LABEL_138:
  if ( *(_QWORD *)(v11 + 56) < a3 )
    FILE_ICB_DESCRIPTOR::SetInformationLength(this, a3);
  *a5 = v33;
  v27 = 1;
  if ( Heap )
    goto LABEL_57;
  return v27;
}

```

## disassembly

```asm
0x180065a58  mov     [rsp-38h+arg_10], rbx
0x180065a5d  mov     dword ptr [rsp-38h+Size], r9d
0x180065a62  mov     [rsp-38h+Src], rdx
0x180065a67  push    rbp
0x180065a68  push    rsi
0x180065a69  push    rdi
0x180065a6a  push    r12
0x180065a6c  push    r13
0x180065a6e  push    r14
0x180065a70  push    r15
0x180065a72  mov     rbp, rsp
0x180065a75  sub     rsp, 70h
0x180065a79  mov     rax, [rcx+20h]
0x180065a7d  xor     r15d, r15d
0x180065a80  mov     r14d, r9d
0x180065a83  mov     rsi, r8
0x180065a86  mov     [rbp+arg_0], r15b
0x180065a8a  mov     rdi, rcx
0x180065a8d  lea     rdx, [rax+20h]
0x180065a91  test    rax, rax
0x180065a94  jnz     short loc_180065A9F
0x180065a96  mov     [rbp+var_28], 10h
0x180065a9d  jmp     short loc_180065ABB
0x180065a9f  mov     rax, [rdx]
0x180065aa2  mov     rcx, [rax+30h]
0x180065aa6  mov     eax, [rcx+168h]
0x180065aac  and     al, 8
0x180065aae  neg     al
0x180065ab0  sbb     ecx, ecx
0x180065ab2  and     ecx, 0FFFFFFF0h
0x180065ab5  add     ecx, 20h ; ' '
0x180065ab8  mov     [rbp+var_28], ecx
0x180065abb  mov     r13, [rdi+10h]
0x180065abf  lea     rbx, [rdi+28h]
0x180065ac3  mov     [rbp+var_40], r15d
0x180065ac7  mov     r9d, 105h
0x180065acd  mov     [rbp+var_30], r15d
0x180065ad1  mov     [rbp+var_2C], r15d
0x180065ad5  mov     al, [r13+22h]
0x180065ad9  and     al, 7
0x180065adb  mov     [rbp+var_38], r15d
0x180065adf  mov     [rbp+var_34], r15d
0x180065ae3  mov     qword ptr [rbp+var_20], rbx
0x180065ae7  cmp     al, 3
0x180065ae9  jnz     short loc_180065B03
0x180065aeb  cmp     [r13+0], r9w
0x180065af0  lea     eax, [r9-59h]
0x180065af4  lea     ecx, [rax+28h]
0x180065af7  mov     r12d, r15d
0x180065afa  cmovnz  eax, ecx
0x180065afd  mov     ecx, [rax+r13]
0x180065b01  jmp     short loc_180065B33
0x180065b03  mov     rcx, [rdx]; this
0x180065b06  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180065b0b  mov     rcx, [rbx]; this
0x180065b0e  lea     rdx, [rbp+var_38]; unsigned int *
0x180065b12  mov     r12d, eax
0x180065b15  call    ?QueryInformationLength@UDF_EXTENT_LIST@@QEBAEPEAK@Z; UDF_EXTENT_LIST::QueryInformationLength(ulong *)
0x180065b1a  test    al, al
0x180065b1c  jz      loc_18006639B
0x180065b22  mov     ecx, r12d
0x180065b25  mov     qword ptr [rbp+var_20], rbx
0x180065b29  imul    ecx, [rbp+var_38]
0x180065b2d  mov     r9d, 105h
0x180065b33  lea     r8, [rsi+r14]
0x180065b37  mov     eax, ecx
0x180065b39  mov     [rbp+var_18], r8
0x180065b3d  mov     edx, 0D8h
0x180065b42  lea     r15d, [rdx-28h]
0x180065b46  cmp     rax, r8
0x180065b49  jnb     loc_180065C25
0x180065b4f  mov     rax, [rdi+10h]
0x180065b53  mov     cl, [rax+22h]
0x180065b56  and     cl, 7
0x180065b59  cmp     cl, 3
0x180065b5c  jnz     short loc_180065BC9
0x180065b5e  cmp     [r13+0], r9w
0x180065b63  lea     rbx, [r13+0A8h]
0x180065b6a  mov     r14d, r15d
0x180065b6d  cmovnz  r14d, edx
0x180065b71  jz      short loc_180065B7A
0x180065b73  lea     rbx, [r13+0D0h]
0x180065b7a  mov     rcx, [rdi+20h]
0x180065b7e  mov     ebx, [rbx]
0x180065b80  mov     rcx, [rcx+20h]; this
0x180065b84  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180065b89  mov     ecx, eax
0x180065b8b  lea     rax, [r14+rbx]
0x180065b8f  mov     ebx, dword ptr [rbp+Size]
0x180065b92  add     rax, rbx
0x180065b95  add     rax, rsi
0x180065b98  cmp     rax, rcx
0x180065b9b  jbe     short loc_180065BC9
0x180065b9d  mov     rdx, [rdi+20h]; struct UDF_LVOL *
0x180065ba1  test    rdx, rdx
0x180065ba4  jz      loc_180065C6D
0x180065baa  mov     rbx, [rbp+arg_28]
0x180065bae  test    rbx, rbx
0x180065bb1  jz      loc_180065C6D
0x180065bb7  mov     rcx, rdi; this
0x180065bba  call    ?ConvertToNonImmediateAllocDesc@FILE_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@@Z; FILE_ICB_DESCRIPTOR::ConvertToNonImmediateAllocDesc(UDF_LVOL *)
0x180065bbf  test    al, al
0x180065bc1  jz      loc_180065C6D
0x180065bc7  jmp     short loc_180065BCD
0x180065bc9  mov     rbx, [rbp+arg_28]
0x180065bcd  mov     rax, [rdi]
0x180065bd0  mov     r9d, 1
0x180065bd6  mov     rdx, [rbp+var_18]
0x180065bda  mov     r8, rbx
0x180065bdd  mov     rcx, rdi
0x180065be0  mov     dword ptr [rsp+70h+var_50], 1
0x180065be8  mov     rax, [rax+48h]
0x180065bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065bf1  test    al, al
0x180065bf3  jz      short loc_180065C6D
0x180065bf5  mov     rax, [rdi+10h]
0x180065bf9  mov     cl, [rax+22h]
0x180065bfc  and     cl, 7
0x180065bff  cmp     cl, 3
0x180065c02  jz      short loc_180065C25
0x180065c04  mov     rcx, [rdi+20h]
0x180065c08  mov     rcx, [rcx+20h]; this
0x180065c0c  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180065c11  mov     rcx, [rdi+28h]; this
0x180065c15  lea     rdx, [rbp+var_38]; unsigned int *
0x180065c19  mov     r12d, eax
0x180065c1c  call    ?QueryInformationLength@UDF_EXTENT_LIST@@QEBAEPEAK@Z; UDF_EXTENT_LIST::QueryInformationLength(ulong *)
0x180065c21  test    al, al
0x180065c23  jz      short loc_180065C6D
0x180065c25  mov     rbx, [r13+38h]
0x180065c29  cmp     rbx, rsi
0x180065c2c  jnb     short loc_180065C8E
0x180065c2e  mov     r9, rsi
0x180065c31  sub     r9, rbx; unsigned int
0x180065c34  mov     rax, r9
0x180065c37  shr     rax, 20h
0x180065c3b  test    eax, eax
0x180065c3d  jz      short loc_180065C75
0x180065c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065c46  lea     rax, WPP_GLOBAL_Control
0x180065c4d  cmp     rcx, rax
0x180065c50  jz      short loc_180065C6D
0x180065c52  test    byte ptr [rcx+1Ch], 1
0x180065c56  jz      short loc_180065C6D
0x180065c58  mov     edx, 16h
0x180065c5d  mov     rcx, [rcx+10h]
0x180065c61  lea     r8, WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids
0x180065c68  call    WPP_SF_
0x180065c6d  mov     bl, [rbp+arg_0]
0x180065c70  jmp     loc_18006639E
0x180065c75  mov     rdx, rbx; unsigned __int64
0x180065c78  mov     [r13+38h], rsi
0x180065c7c  mov     rcx, rdi; this
0x180065c7f  call    ?Fill@FILE_ICB_DESCRIPTOR@@AEAAE_KDK@Z; FILE_ICB_DESCRIPTOR::Fill(unsigned __int64,char,ulong)
0x180065c84  test    al, al
0x180065c86  jnz     short loc_180065C8E
0x180065c88  mov     [r13+38h], rbx
0x180065c8c  jmp     short loc_180065C6D
0x180065c8e  mov     rax, [rdi+10h]
0x180065c92  xor     r14d, r14d
0x180065c95  movzx   ecx, word ptr [rax+22h]
0x180065c99  and     cx, 7
0x180065c9d  cmp     cx, 3
0x180065ca1  jnz     short loc_180065CEC
0x180065ca3  mov     eax, 105h
0x180065ca8  cmp     [r13+0], ax
0x180065cad  lea     ecx, [rax-2Dh]
0x180065cb0  cmovnz  r15, rcx
0x180065cb4  lea     rax, [r13+0A8h]
0x180065cbb  jz      short loc_180065CC4
0x180065cbd  lea     rax, [r13+0D0h]
0x180065cc4  mov     ecx, [rax]
0x180065cc6  mov     rdx, [rbp+Src]; Src
0x180065cca  add     rcx, r15
0x180065ccd  mov     r15d, dword ptr [rbp+Size]
0x180065cd1  add     rcx, r13
0x180065cd4  add     rcx, rsi; void *
0x180065cd7  mov     r8d, r15d; Size
0x180065cda  call    memcpy_0
0x180065cdf  mov     rsi, [rbp+var_18]
0x180065ce3  mov     byte ptr [rdi+64h], 1
0x180065ce7  jmp     loc_180066377
0x180065cec  cmp     cx, 2
0x180065cf0  jb      short loc_180065D28
0x180065cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180065cf9  lea     rax, WPP_GLOBAL_Control
0x180065d00  cmp     rcx, rax
0x180065d03  jz      short loc_180065D20
0x180065d05  test    byte ptr [rcx+1Ch], 1
0x180065d09  jz      short loc_180065D20
0x180065d0b  mov     rcx, [rcx+10h]
0x180065d0f  lea     r8, WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids
0x180065d16  mov     edx, 23h ; '#'
0x180065d1b  call    WPP_SF_
0x180065d20  mov     bl, r14b
0x180065d23  jmp     loc_18006639E
0x180065d28  mov     r15d, dword ptr [rbp+Size]
0x180065d2c  test    r15d, r15d
0x180065d2f  jz      loc_180066377
0x180065d35  mov     rcx, gs:60h
0x180065d3e  mov     r8d, r12d
0x180065d41  imul    r8d, [rbp+var_28]; Size
0x180065d46  xor     edx, edx; Flags
0x180065d48  mov     rcx, [rcx+30h]; HeapHandle
0x180065d4c  call    cs:__imp_RtlAllocateHeap
0x180065d52  mov     r14, rax
0x180065d55  test    rax, rax
0x180065d58  jnz     short loc_180065D84
0x180065d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180065d61  lea     rax, WPP_GLOBAL_Control
0x180065d68  cmp     rcx, rax
0x180065d6b  jz      loc_180065C6D
0x180065d71  test    byte ptr [rcx+1Ch], 1
0x180065d75  jz      loc_180065C6D
0x180065d7b  lea     edx, [r14+17h]
0x180065d7f  jmp     loc_180065C5D
0x180065d84  xor     edx, edx
0x180065d86  mov     ecx, r12d
0x180065d89  mov     rax, rsi
0x180065d8c  mov     [rbp+var_3C], 0
0x180065d90  div     rcx
0x180065d93  mov     rbx, rdx
0x180065d96  test    edx, edx
0x180065d98  jz      loc_180065FBF
0x180065d9e  mov     eax, r12d
0x180065da1  lea     r9, [rbp+var_30]; unsigned int *
0x180065da5  sub     eax, ebx
0x180065da7  lea     r8, [rbp+var_40]; unsigned int *
0x180065dab  cmp     r15d, eax
0x180065dae  cmovb   eax, r15d
0x180065db2  xor     edx, edx
0x180065db4  mov     dword ptr [rbp+var_18], eax
0x180065db7  mov     rax, rsi
0x180065dba  div     rcx
0x180065dbd  mov     rcx, qword ptr [rbp+var_20]
0x180065dc1  mov     edx, eax; unsigned int
0x180065dc3  mov     qword ptr [rbp+var_10], rax
0x180065dc7  mov     rcx, [rcx]; this
0x180065dca  call    ?QueryLbnFromVbn@UDF_EXTENT_LIST@@QEBAEKPEAK0@Z; UDF_EXTENT_LIST::QueryLbnFromVbn(ulong,ulong *,ulong *)
0x180065dcf  test    al, al
0x180065dd1  jnz     short loc_180065E21
0x180065dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180065dda  lea     rax, WPP_GLOBAL_Control
0x180065de1  cmp     rcx, rax
0x180065de4  jz      short loc_180065E01
0x180065de6  test    byte ptr [rcx+1Ch], 1
0x180065dea  jz      short loc_180065E01
0x180065dec  mov     edx, 18h
0x180065df1  mov     rcx, [rcx+10h]
0x180065df5  lea     r8, WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids
0x180065dfc  call    WPP_SF_
0x180065e01  mov     bl, [rbp+arg_0]
0x180065e04  mov     rcx, gs:60h
0x180065e0d  mov     r8, r14; P
0x180065e10  xor     edx, edx; Flags
0x180065e12  mov     rcx, [rcx+30h]; HeapHandle
0x180065e16  call    cs:__imp_RtlFreeHeap
0x180065e1c  jmp     loc_18006639E
0x180065e21  mov     r15d, [rbp+var_40]
0x180065e25  mov     [rbp+var_38], r15d
0x180065e29  cmp     r15d, 0FFFFFFFFh
0x180065e2d  jnz     short loc_180065E86
0x180065e2f  mov     rcx, [rbp+arg_28]
0x180065e33  test    rcx, rcx
0x180065e36  jz      short loc_180065E01
0x180065e38  mov     rax, [rcx]
0x180065e3b  lea     r9, [rbp+var_40]
0x180065e3f  mov     r15d, 1
0x180065e45  xor     edx, edx
0x180065e47  mov     r8d, r15d
0x180065e4a  mov     dword ptr [rsp+70h+var_50], r15d
0x180065e4f  mov     rax, [rax+30h]
0x180065e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e58  test    al, al
0x180065e5a  jz      short loc_180065E01
0x180065e5c  mov     rax, qword ptr [rbp+var_20]
0x180065e60  mov     r9d, r15d; unsigned int
0x180065e63  mov     r8d, [rbp+var_40]; unsigned int
0x180065e67  mov     edx, [rbp+var_10]; unsigned int
0x180065e6a  mov     rcx, [rax]; this
0x180065e6d  call    ?AddExtent@UDF_EXTENT_LIST@@QEAAEKKK@Z; UDF_EXTENT_LIST::AddExtent(ulong,ulong,ulong)
0x180065e72  test    al, al
0x180065e74  jz      short loc_180065E01
0x180065e76  mov     [rdi+65h], r15b
0x180065e7a  mov     [rbp+var_3C], r15b
0x180065e7e  mov     r15d, [rbp+var_40]
0x180065e82  mov     [rbp+var_38], r15d
0x180065e86  movzx   edx, word ptr [rdi+18h]; unsigned __int16
0x180065e8a  mov     r9d, 1; unsigned int
0x180065e90  mov     rcx, [rdi+20h]; this
0x180065e94  mov     r8d, r15d; unsigned int
0x180065e97  mov     [rsp+70h+var_50], r14; void *
0x180065e9c  call    ?Read@UDF_LVOL@@QEAAEGKKPEAX@Z; UDF_LVOL::Read(ushort,ulong,ulong,void *)
0x180065ea1  test    al, al
0x180065ea3  jnz     short loc_180065ED0
0x180065ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180065eac  lea     rax, WPP_GLOBAL_Control
0x180065eb3  cmp     rcx, rax
0x180065eb6  jz      loc_180065E01
0x180065ebc  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
