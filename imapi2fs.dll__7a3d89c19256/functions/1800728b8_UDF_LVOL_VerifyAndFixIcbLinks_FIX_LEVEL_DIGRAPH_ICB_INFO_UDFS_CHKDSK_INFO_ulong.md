# UDF_LVOL::VerifyAndFixIcbLinks(FIX_LEVEL,DIGRAPH *,ICB_INFO *,UDFS_CHKDSK_INFO *,ulong *)

- ea: `0x1800728b8`
- end: `0x180073414`
- name: `?VerifyAndFixIcbLinks@UDF_LVOL@@AEAAEW4FIX_LEVEL@@PEAVDIGRAPH@@PEAVICB_INFO@@PEAUUDFS_CHKDSK_INFO@@PEAK@Z`
- size: `2908`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800698f0`

## callees

- `0x180004ab0`
- `0x180020098`
- `0x18005f3b4`
- `0x18005ff7c`
- `0x18006006c`
- `0x1800600dc`
- `0x180060148`
- `0x18006213c`
- `0x180062190`
- `0x1800645a0`
- `0x180065840`
- `0x180067510`
- `0x180067558`
- `0x1800698bc`
- `0x18006c6d0`
- `0x18006cbd0`
- `0x18006cf58`
- `0x18006d25c`
- `0x1800706ac`
- `0x180070d28`
- `0x180070fd4`
- `0x180071944`
- `0x1800721f4`
- `0x1800722b4`
- `0x1800728b8`
- `0x180077060`
- `0x1800770c0`
- `0x180088010`

## pseudocode

```c
char __fastcall UDF_LVOL::VerifyAndFixIcbLinks(
        __int64 a1,
        unsigned int a2,
        DIGRAPH *a3,
        ICB_INFO *a4,
        _DWORD *a5,
        unsigned int *a6)
{
  ICB_INFO *v7; // r12
  __int64 v8; // r9
  int v9; // ebx
  int v10; // edi
  int v11; // r14d
  int v12; // r15d
  int v13; // eax
  unsigned int v14; // r14d
  struct OBJECT *Next; // rax
  struct OBJECT *v16; // rdi
  unsigned int v17; // r13d
  unsigned __int16 NumParents; // ax
  UDF_LVOL *v19; // rcx
  unsigned __int16 v20; // r15
  unsigned int v21; // eax
  MESSAGE *v22; // rcx
  unsigned __int8 v23; // al
  struct FILE_ICB_DESCRIPTOR *v24; // rbx
  unsigned int *v25; // r12
  struct DIGRAPH *v26; // r14
  unsigned int *v27; // r14
  int v28; // eax
  DIGRAPH *v29; // r15
  _DWORD *v31; // rax
  unsigned int v32; // edx
  char v33; // al
  struct ICB_ENTRY *IcbEntry; // rax
  ICB_INFO *v35; // rcx
  unsigned int v36; // edx
  struct ICB_ENTRY *v37; // rax
  int v38; // edx
  char v39; // r9
  int v40; // eax
  DIGRAPH *v41; // r15
  char v42; // al
  unsigned int v43; // eax
  unsigned __int16 PartitionNumberForAllocationTag; // ax
  __int16 v45; // ax
  bool v46; // zf
  DIGRAPH *v47; // rbx
  int v48; // r15d
  unsigned int v49; // r12d
  DIGRAPH *v50; // r13
  struct OBJECT *v51; // rax
  struct OBJECT *v52; // r14
  int v53; // ebx
  unsigned int v54; // eax
  unsigned int v55; // edi
  __int16 v56; // ax
  __int64 v57; // rcx
  unsigned int AllocationTagForFileType; // eax
  __int16 v59; // ax
  unsigned int v60; // ebx
  __int16 v61; // di
  unsigned __int8 v62; // bl
  __int64 v63; // [rsp+30h] [rbp-D8h]
  __int64 v64; // [rsp+38h] [rbp-D0h]
  int v65; // [rsp+40h] [rbp-C8h]
  int v66; // [rsp+48h] [rbp-C0h]
  unsigned int v67; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v68; // [rsp+50h] [rbp-B8h]
  unsigned int v69; // [rsp+54h] [rbp-B4h]
  _QWORD v70[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+68h] [rbp-A0h]
  __int64 v72; // [rsp+70h] [rbp-98h]
  __int64 v73; // [rsp+78h] [rbp-90h]
  _BYTE v74[24]; // [rsp+88h] [rbp-80h] BYREF
  __int16 v75; // [rsp+A0h] [rbp-68h]
  unsigned int v76; // [rsp+A4h] [rbp-64h]
  char v77; // [rsp+ECh] [rbp-1Ch]
  _BYTE v78[256]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int v79; // [rsp+208h] [rbp+100h] BYREF
  unsigned int v80; // [rsp+210h] [rbp+108h]
  DIGRAPH *v81; // [rsp+218h] [rbp+110h]
  ICB_INFO *v82; // [rsp+220h] [rbp+118h]

  v82 = a4;
  v81 = a3;
  v80 = a2;
  v79 = 0;
  v67 = 0;
  v7 = a4;
  FILE_ICB_DESCRIPTOR::FILE_ICB_DESCRIPTOR((FILE_ICB_DESCRIPTOR *)v74);
  DIR_ICB_DESCRIPTOR::DIR_ICB_DESCRIPTOR((DIR_ICB_DESCRIPTOR *)v78);
  v70[0] = &ICB_INFO_ITERATOR::`vftable';
  v70[1] = ICB_INFO_ITERATOR_cd;
  v71 = 0;
  LODWORD(v72) = -1;
  v73 = v8;
  ICB_INFO_ITERATOR::Reset((ICB_INFO_ITERATOR *)v70);
  v9 = a5[4];
  v10 = a5[3];
  v11 = a5[2];
  v12 = a5[1];
  MESSAGE::DisplayMsg(*(_QWORD *)(a1 + 24), 30569, 2, 3, MultiByteStr);
  if ( !MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7D0u, "%d", 0) )
    goto LABEL_28;
  v13 = v12 + v11;
  LOBYTE(a5) = 0;
  v14 = v80;
  v66 = 0;
  v69 = v9 + v10 + v13;
  v68 = 0;
  v71 = 0;
  LODWORD(v72) = -1;
LABEL_104:
  v47 = v81;
  while ( 1 )
  {
    Next = ICB_INFO_ITERATOR::GetNext((ICB_INFO_ITERATOR *)v70);
    v16 = Next;
    if ( !Next )
      break;
    v17 = *((_DWORD *)Next + 2);
    NumParents = DIGRAPH::QueryNumParents(v47, v17);
    v19 = 0;
    v20 = NumParents;
    if ( *((_BYTE *)v16 + 34) )
    {
      v21 = 100 * v66 / v69;
      if ( v21 != v68 )
      {
        v22 = *(MESSAGE **)(a1 + 24);
        v68 = 100 * v66 / v69;
        v23 = MESSAGE::DisplayMsg(v22, 0x7D0u, "%d", v21);
        v19 = 0;
        if ( !v23 )
          goto LABEL_28;
      }
      v24 = 0;
      if ( ((*((_BYTE *)v16 + 34) - 2) & 0xFD) != 0 )
        goto LABEL_45;
      if ( v20 <= 1u )
      {
        v26 = v81;
        v25 = (unsigned int *)((char *)v16 + 12);
      }
      else
      {
        MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x777Eu, "%d", v17);
        v25 = (unsigned int *)((char *)v16 + 12);
        if ( *((_DWORD *)v16 + 3) == -1 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
          LOBYTE(v65) = 0;
          LOBYTE(v64) = 1;
          LODWORD(v63) = -1;
        }
        else
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
          LOBYTE(v65) = 0;
          LOBYTE(v64) = 0;
          LODWORD(v63) = *v25;
        }
        if ( !(unsigned __int8)UDF_LVOL::DeleteIcbInReferences(a1, v24, v14, v81, v82, v63, v64, v65) )
          goto LABEL_28;
        v26 = v81;
        v20 = DIGRAPH::QueryNumParents(v81, v17);
      }
      if ( v20 != 1 )
      {
        v27 = v25;
LABEL_38:
        if ( v20 )
          goto LABEL_43;
        v29 = v81;
        goto LABEL_40;
      }
      if ( !UDF_LVOL::GetLoneParent(v19, v26, v17, &v79) )
        goto LABEL_28;
      v27 = (unsigned int *)((char *)v16 + 12);
      v28 = *((_DWORD *)v16 + 3);
      if ( v28 == -1 )
      {
        MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7780u, "%d", v17);
        if ( *((_BYTE *)v16 + 34) == *((_BYTE *)v16 + 38) )
        {
          if ( !v24 )
          {
            v24 = UDF_LVOL::InitializeIcbForReadWrite(
                    (UDF_LVOL *)a1,
                    v16,
                    (struct FILE_ICB_DESCRIPTOR *)v74,
                    (struct DIR_ICB_DESCRIPTOR *)v78);
            if ( !v24 )
              goto LABEL_28;
          }
          LOBYTE(v63) = 0;
          if ( !(unsigned __int8)UDF_LVOL::AddParentFidToIcb(a1, v24, v79, v80, v82, v63) )
            goto LABEL_28;
          goto LABEL_38;
        }
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        LOBYTE(v65) = 0;
        LOBYTE(v64) = 1;
      }
      else
      {
        if ( v79 == v28 )
          goto LABEL_43;
        MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x777Fu, "%d", v17);
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        LOBYTE(v65) = 0;
        LOBYTE(v64) = 0;
      }
      v29 = v81;
      LODWORD(v63) = -1;
      if ( !(unsigned __int8)UDF_LVOL::DeleteIcbInReferences(a1, v24, v80, v81, v82, v63, v64, v65) )
        goto LABEL_28;
LABEL_40:
      v31 = *(_DWORD **)(a1 + 64);
      if ( v17 == v31[101] )
        goto LABEL_43;
      if ( (v31[116] & 0x3FFFFFFF) != 0 )
      {
        if ( v17 == v31[117] )
          goto LABEL_43;
      }
      else
      {
        v25 = v27;
      }
      if ( *v25 == -1 )
      {
LABEL_43:
        v7 = v82;
LABEL_44:
        v14 = v80;
        goto LABEL_45;
      }
      v32 = *v25;
      v7 = v82;
      if ( ICB_INFO::IsLinkLegal(v82, v32, v17) )
      {
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        LOBYTE(v63) = 0;
        v14 = v80;
        v33 = UDF_LVOL::AddChildEntryToParentIcb(a1, v24, v80, v29, v7, v63, 0);
      }
      else
      {
        IcbEntry = ICB_INFO::GetIcbEntry(v7, v17);
        if ( IcbEntry )
        {
          if ( *((_BYTE *)IcbEntry + 34) )
          {
            v36 = *((_DWORD *)IcbEntry + 3);
            if ( v36 != -1 )
            {
              v37 = ICB_INFO::GetIcbEntry(v35, v36);
              if ( !v37 )
                goto LABEL_44;
              v40 = *((unsigned __int8 *)v37 + 34);
              if ( !(_BYTE)v40 )
                goto LABEL_44;
              if ( v38 != v17 )
              {
                if ( v40 == 1 )
                {
                  if ( v39 == 4 )
                    goto LABEL_44;
                }
                else if ( v40 == 2 )
                {
                  if ( v39 != 3 )
                    goto LABEL_44;
                }
                else if ( v40 == 4 && v39 == 3 )
                {
                  goto LABEL_44;
                }
              }
            }
          }
        }
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        LOBYTE(v65) = 0;
        v14 = v80;
        LOBYTE(v64) = 1;
        LODWORD(v63) = -1;
        v33 = UDF_LVOL::DeleteIcbInReferences(a1, v24, v80, v29, v7, v63, v64, v65);
      }
      if ( !v33 )
        goto LABEL_28;
LABEL_45:
      if ( *((_WORD *)v16 + 18) && *((_BYTE *)v16 + 38) != *((_BYTE *)v16 + 34) )
      {
        MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7783u, "%d", v17);
        if ( *((_BYTE *)v16 + 34) == 1 )
        {
          if ( *((_BYTE *)v16 + 38) != 2 )
            goto LABEL_77;
        }
        else
        {
          if ( *((_BYTE *)v16 + 34) != 2 )
          {
            if ( (unsigned int)*((unsigned __int8 *)v16 + 34) - 3 > 1 )
              goto LABEL_28;
LABEL_77:
            if ( !v24 )
            {
              v24 = UDF_LVOL::InitializeIcbForReadWrite(
                      (UDF_LVOL *)a1,
                      v16,
                      (struct FILE_ICB_DESCRIPTOR *)v74,
                      (struct DIR_ICB_DESCRIPTOR *)v78);
              if ( !v24 )
                goto LABEL_28;
            }
            LOBYTE(v65) = 0;
            v41 = v81;
            LOBYTE(v64) = 1;
            LODWORD(v63) = -1;
            v42 = UDF_LVOL::DeleteIcbInReferences(a1, v24, v14, v81, v7, v63, v64, v65);
LABEL_84:
            if ( !v42 )
              goto LABEL_28;
            goto LABEL_87;
          }
          if ( *((_BYTE *)v16 + 38) != 1 )
            goto LABEL_77;
        }
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        v41 = v81;
        v42 = UDF_LVOL::ChangeIcbReferencesType(a1, v16, *((unsigned __int8 *)v16 + 34), v14, v81, v7);
        goto LABEL_84;
      }
      v41 = v81;
LABEL_87:
      if ( *((_BYTE *)v16 + 34) == 3 && *((_WORD *)v16 + 18) > 1u )
      {
        MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7784u, "%d", v17);
        if ( !v24 )
        {
          v24 = UDF_LVOL::InitializeIcbForReadWrite(
                  (UDF_LVOL *)a1,
                  v16,
                  (struct FILE_ICB_DESCRIPTOR *)v74,
                  (struct DIR_ICB_DESCRIPTOR *)v78);
          if ( !v24 )
            goto LABEL_28;
        }
        LOBYTE(v65) = 0;
        LOBYTE(v64) = 1;
        LODWORD(v63) = -1;
        if ( !(unsigned __int8)UDF_LVOL::DeleteIcbInReferences(a1, v24, v14, v41, v7, v63, v64, v65) )
          goto LABEL_28;
      }
      if ( v24 )
      {
        if ( *((_BYTE *)v24 + 101) )
        {
          if ( v14 )
          {
            v43 = (*(__int64 (__fastcall **)(struct FILE_ICB_DESCRIPTOR *))(*(_QWORD *)v24 + 64LL))(v24);
            PartitionNumberForAllocationTag = UDF_LVOL::GetPartitionNumberForAllocationTag(a1, v43);
            if ( !FILE_ICB_DESCRIPTOR::WriteAllocation(
                    v24,
                    (struct UDF_LVOL *)a1,
                    *(struct SPACE_BITMAP_DESCRIPTOR **)(a1 + 8LL * PartitionNumberForAllocationTag + 112)) )
              goto LABEL_28;
          }
        }
        if ( *((_BYTE *)v24 + 100) )
        {
          v45 = *((_WORD *)v16 + 18);
          if ( *((_WORD *)v16 + 16) != v45 )
          {
            *((_WORD *)v16 + 16) = v45;
            MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7786u, "%d", v17);
            FILE_ICB_DESCRIPTOR::SetLinkCount(v24, *((_WORD *)v16 + 16), (struct UDF_LVOL *)a1);
          }
          if ( v14 )
          {
            if ( !DESCRIPTOR::RecomputeChecksums(v24) )
              goto LABEL_28;
            *((_BYTE *)v24 + 100) = 0;
            if ( !DESCRIPTOR::Write(v24, (struct UDF_LVOL *)a1, &v67) )
              goto LABEL_28;
          }
        }
      }
      ++v66;
      v46 = v24 == 0;
      v47 = v81;
      if ( !v46 )
      {
        LOBYTE(a5) = 1;
        goto LABEL_104;
      }
    }
    else if ( NumParents )
    {
      MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x777Du, "%d", v17);
      DESCRIPTOR::Destroy((DESCRIPTOR *)v74);
      v76 = v17;
      LOBYTE(v65) = 0;
      LOBYTE(v64) = 0;
      LODWORD(v63) = -1;
      v75 = 0;
      if ( !(unsigned __int8)UDF_LVOL::DeleteIcbInReferences(a1, v74, v14, v47, v7, v63, v64, v65) )
        goto LABEL_28;
      LOBYTE(a5) = 1;
    }
  }
  if ( !MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7D0u, "%d", 100) )
    goto LABEL_28;
  MESSAGE::DisplayMsg(*(_QWORD *)(a1 + 24), 30570, 2, 3, MultiByteStr);
  MESSAGE::DisplayMsg(*(_QWORD *)(a1 + 24), 30586, 2, 3, MultiByteStr);
  if ( !MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7D0u, "%d", 0) )
    goto LABEL_28;
  v48 = 0;
  v71 = 0;
  v49 = 0;
  LODWORD(v72) = -1;
  v50 = v81;
  while ( 1 )
  {
    v51 = ICB_INFO_ITERATOR::GetNext((ICB_INFO_ITERATOR *)v70);
    v52 = v51;
    if ( !v51 )
      break;
    if ( *((_BYTE *)v51 + 34) )
    {
      v53 = *((_DWORD *)v51 + 2);
      v54 = 100 * v48 / v69;
      if ( v54 != v49 )
      {
        v49 = 100 * v48 / v69;
        if ( !MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7D0u, "%d", v54) )
          goto LABEL_28;
      }
      ++v48;
      if ( *((_BYTE *)v52 + 38) )
      {
        if ( (unsigned __int8)(*((_BYTE *)v52 + 34) - 1) <= 1u && *((_BYTE *)v52 + 38) == 6 )
        {
          MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7785u, "%d", v53);
          v55 = v80;
          if ( !(unsigned __int8)UDF_LVOL::ChangeIcbReferencesType(
                                   a1,
                                   v52,
                                   *((unsigned __int8 *)v52 + 34),
                                   v80,
                                   v50,
                                   v82) )
            goto LABEL_28;
          LOBYTE(a5) = 1;
        }
        else
        {
          v55 = v80;
        }
        v56 = *((_WORD *)v52 + 18);
        if ( *((_WORD *)v52 + 16) != v56 )
        {
          *((_WORD *)v52 + 16) = v56;
          MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7786u, "%d", v53);
          LOBYTE(a5) = 1;
          if ( v55 )
          {
            LOBYTE(v57) = *((_BYTE *)v52 + 34);
            AllocationTagForFileType = UDF_LVOL::GetAllocationTagForFileType(v57);
            v59 = UDF_LVOL::GetPartitionNumberForAllocationTag(a1, AllocationTagForFileType);
            v60 = *((_DWORD *)v52 + 2);
            v61 = v59;
            DESCRIPTOR::Destroy((DESCRIPTOR *)v74);
            v75 = v61;
            v76 = v60;
            v77 = 0;
            if ( !DESCRIPTOR::Read((DESCRIPTOR *)v74, (struct UDF_LVOL *)a1, &v67) )
              goto LABEL_28;
            FILE_ICB_DESCRIPTOR::SetLinkCount((FILE_ICB_DESCRIPTOR *)v74, *((_WORD *)v52 + 16), (struct UDF_LVOL *)a1);
            if ( !DESCRIPTOR::RecomputeChecksums((DESCRIPTOR *)v74) )
              goto LABEL_28;
            v77 = 0;
            if ( !DESCRIPTOR::Write((DESCRIPTOR *)v74, (struct UDF_LVOL *)a1, &v67) )
              goto LABEL_28;
          }
        }
      }
    }
  }
  if ( !MESSAGE::DisplayMsg(*(MESSAGE **)(a1 + 24), 0x7D0u, "%d", 100) )
  {
LABEL_28:
    v70[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
    DIR_ICB_DESCRIPTOR::~DIR_ICB_DESCRIPTOR((DIR_ICB_DESCRIPTOR *)v78);
    FILE_ICB_DESCRIPTOR::~FILE_ICB_DESCRIPTOR((FILE_ICB_DESCRIPTOR *)v74);
    return 0;
  }
  v62 = 0;
  MESSAGE::DisplayMsg(*(_QWORD *)(a1 + 24), 30587, 2, 3, MultiByteStr);
  if ( (_BYTE)a5 )
    v62 = v80 != 0;
  UDF_LVOL::UpdateExitStatus((unsigned __int8)a5, v62, a6);
  v70[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
  DIR_ICB_DESCRIPTOR::~DIR_ICB_DESCRIPTOR((DIR_ICB_DESCRIPTOR *)v78);
  FILE_ICB_DESCRIPTOR::~FILE_ICB_DESCRIPTOR((FILE_ICB_DESCRIPTOR *)v74);
  return 1;
}

```

## disassembly

```asm
0x1800728b8  mov     rax, rsp
0x1800728bb  mov     [rax+20h], r9
0x1800728bf  mov     [rax+18h], r8
0x1800728c3  mov     [rax+10h], edx
0x1800728c6  push    rbp
0x1800728c7  push    rbx
0x1800728c8  push    rsi
0x1800728c9  push    rdi
0x1800728ca  push    r12
0x1800728cc  push    r13
0x1800728ce  push    r14
0x1800728d0  push    r15
0x1800728d2  lea     rbp, [rax-0F8h]
0x1800728d9  sub     rsp, 1B8h
0x1800728e0  xor     r13d, r13d
0x1800728e3  mov     rsi, rcx
0x1800728e6  lea     rcx, [rbp+0F0h+var_170]; this
0x1800728ea  mov     [rbp+0F0h+arg_0], r13d
0x1800728f1  mov     [rsp+1F0h+var_1AC], r13d
0x1800728f6  mov     r12, r9
0x1800728f9  call    ??0FILE_ICB_DESCRIPTOR@@QEAA@XZ; FILE_ICB_DESCRIPTOR::FILE_ICB_DESCRIPTOR(void)
0x1800728fe  lea     rcx, [rbp+0F0h+var_100]; this
0x180072902  call    ??0DIR_ICB_DESCRIPTOR@@QEAA@XZ; DIR_ICB_DESCRIPTOR::DIR_ICB_DESCRIPTOR(void)
0x180072907  mov     rax, cs:?ICB_INFO_ITERATOR_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const ICB_INFO_ITERATOR_cd
0x18007290e  lea     rcx, ??_7ICB_INFO_ITERATOR@@6B@; const ICB_INFO_ITERATOR::`vftable'
0x180072915  mov     [rsp+1F0h+var_1A0], rcx
0x18007291a  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18007291f  mov     [rsp+1F0h+var_198], rax
0x180072924  mov     [rsp+1F0h+var_190], r13
0x180072929  mov     dword ptr [rsp+1F0h+var_188], 0FFFFFFFFh
0x180072931  mov     [rsp+1F0h+var_180], r9
0x180072936  call    ?Reset@ICB_INFO_ITERATOR@@UEAAXXZ; ICB_INFO_ITERATOR::Reset(void)
0x18007293b  mov     rax, [rbp+0F0h+arg_20]
0x180072942  lea     r9d, [r13+3]
0x180072946  mov     rcx, [rsi+18h]
0x18007294a  lea     r8d, [r13+2]
0x18007294e  mov     edx, 7769h
0x180072953  mov     ebx, [rax+10h]
0x180072956  mov     edi, [rax+0Ch]
0x180072959  mov     r14d, [rax+8]
0x18007295d  mov     r15d, [rax+4]
0x180072961  lea     rax, MultiByteStr
0x180072968  mov     [rsp+1F0h+var_1D0], rax
0x18007296d  call    ?DisplayMsg@MESSAGE@@QEAAEKW4MESSAGE_TYPE@@KPEBDZZ; MESSAGE::DisplayMsg(ulong,MESSAGE_TYPE,ulong,char const *,...)
0x180072972  mov     rcx, [rsi+18h]; this
0x180072976  lea     r8, aD_0; "%d"
0x18007297d  xor     r9d, r9d
0x180072980  mov     edx, 7D0h; unsigned int
0x180072985  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x18007298a  test    al, al
0x18007298c  jz      loc_180072C48
0x180072992  lea     eax, [r15+r14]
0x180072996  mov     byte ptr [rbp+0F0h+arg_20], r13b
0x18007299d  mov     r14d, [rbp+0F0h+arg_8]
0x1800729a4  add     eax, edi
0x1800729a6  add     eax, ebx
0x1800729a8  mov     [rsp+1F0h+var_1B0], r13d
0x1800729ad  mov     dword ptr [rsp+1F0h+var_1A8+4], eax
0x1800729b1  mov     dword ptr [rsp+1F0h+var_1A8], r13d
0x1800729b6  mov     [rsp+1F0h+var_190], r13
0x1800729bb  mov     dword ptr [rsp+1F0h+var_188], 0FFFFFFFFh
0x1800729c3  jmp     loc_180073139
0x1800729c8  xor     r13d, r13d
0x1800729cb  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800729d0  call    ?GetNext@ICB_INFO_ITERATOR@@UEAAPEAVOBJECT@@XZ; ICB_INFO_ITERATOR::GetNext(void)
0x1800729d5  mov     rdi, rax
0x1800729d8  test    rax, rax
0x1800729db  jz      loc_180073145
0x1800729e1  mov     r13d, [rax+8]
0x1800729e5  mov     rcx, rbx; this
0x1800729e8  mov     edx, r13d; unsigned int
0x1800729eb  call    ?QueryNumParents@DIGRAPH@@QEBAKK@Z; DIGRAPH::QueryNumParents(ulong)
0x1800729f0  xor     ecx, ecx
0x1800729f2  mov     r15d, eax
0x1800729f5  cmp     [rdi+22h], cl
0x1800729f8  jnz     short loc_180072A6A
0x1800729fa  test    r15w, r15w
0x1800729fe  jz      short loc_1800729C8
0x180072a00  mov     rcx, [rsi+18h]; this
0x180072a04  lea     r8, aD_0; "%d"
0x180072a0b  mov     r9d, r13d
0x180072a0e  mov     edx, 777Dh; unsigned int
0x180072a13  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180072a18  lea     rcx, [rbp+0F0h+var_170]; this
0x180072a1c  call    ?Destroy@DESCRIPTOR@@AEAAXXZ; DESCRIPTOR::Destroy(void)
0x180072a21  mov     [rbp+0F0h+var_154], r13d
0x180072a25  lea     rdx, [rbp+0F0h+var_170]
0x180072a29  xor     r13d, r13d
0x180072a2c  mov     r9, rbx
0x180072a2f  mov     byte ptr [rsp+1F0h+var_1B8], r13b
0x180072a34  mov     r8d, r14d
0x180072a37  mov     byte ptr [rsp+1F0h+var_1C0], r13b
0x180072a3c  mov     rcx, rsi
0x180072a3f  mov     dword ptr [rsp+1F0h+var_1C8], 0FFFFFFFFh
0x180072a47  mov     [rsp+1F0h+var_1D0], r12
0x180072a4c  mov     [rbp+0F0h+var_158], r13w
0x180072a51  call    ?DeleteIcbInReferences@UDF_LVOL@@AEAAEPEAVFILE_ICB_DESCRIPTOR@@W4FIX_LEVEL@@PEAVDIGRAPH@@PEAVICB_INFO@@KEE@Z; UDF_LVOL::DeleteIcbInReferences(FILE_ICB_DESCRIPTOR *,FIX_LEVEL,DIGRAPH *,ICB_INFO *,ulong,uchar,uchar)
0x180072a56  test    al, al
0x180072a58  jz      loc_180072C48
0x180072a5e  mov     byte ptr [rbp+0F0h+arg_20], 1
0x180072a65  jmp     loc_1800729CB
0x180072a6a  imul    eax, [rsp+1F0h+var_1B0], 64h ; 'd'
0x180072a6f  xor     edx, edx
0x180072a71  div     dword ptr [rsp+1F0h+var_1A8+4]
0x180072a75  cmp     eax, dword ptr [rsp+1F0h+var_1A8]
0x180072a79  jz      short loc_180072AA1
0x180072a7b  mov     rcx, [rsi+18h]; this
0x180072a7f  lea     r8, aD_0; "%d"
0x180072a86  mov     r9d, eax
0x180072a89  mov     dword ptr [rsp+1F0h+var_1A8], eax
0x180072a8d  mov     edx, 7D0h; unsigned int
0x180072a92  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180072a97  xor     ecx, ecx; this
0x180072a99  test    al, al
0x180072a9b  jz      loc_180072C48
0x180072aa1  mov     al, [rdi+22h]
0x180072aa4  mov     rbx, rcx
0x180072aa7  sub     al, 2
0x180072aa9  test    al, 0FDh
0x180072aab  jnz     loc_180072D69
0x180072ab1  mov     eax, 1
0x180072ab6  cmp     r15w, ax
0x180072aba  jbe     loc_180072B80
0x180072ac0  mov     rcx, [rsi+18h]; this
0x180072ac4  lea     r8, aD_0; "%d"
0x180072acb  mov     r9d, r13d
0x180072ace  mov     edx, 777Eh; unsigned int
0x180072ad3  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180072ad8  lea     r12, [rdi+0Ch]
0x180072adc  or      r15d, 0FFFFFFFFh
0x180072ae0  lea     r9, [rbp+0F0h+var_100]; struct DIR_ICB_DESCRIPTOR *
0x180072ae4  mov     rdx, rdi; struct ICB_ENTRY *
0x180072ae7  lea     r8, [rbp+0F0h+var_170]; struct FILE_ICB_DESCRIPTOR *
0x180072aeb  mov     rcx, rsi; this
0x180072aee  cmp     [r12], r15d
0x180072af2  jnz     short loc_180072B17
0x180072af4  call    ?InitializeIcbForReadWrite@UDF_LVOL@@AEAAPEAVFILE_ICB_DESCRIPTOR@@PEAUICB_ENTRY@@PEAV2@PEAVDIR_ICB_DESCRIPTOR@@@Z; UDF_LVOL::InitializeIcbForReadWrite(ICB_ENTRY *,FILE_ICB_DESCRIPTOR *,DIR_ICB_DESCRIPTOR *)
0x180072af9  mov     rbx, rax
0x180072afc  xor     eax, eax
0x180072afe  test    rbx, rbx
0x180072b01  jz      loc_180072C48
0x180072b07  mov     byte ptr [rsp+1F0h+var_1B8], al
0x180072b0b  mov     byte ptr [rsp+1F0h+var_1C0], 1
0x180072b10  mov     dword ptr [rsp+1F0h+var_1C8], r15d
0x180072b15  jmp     short loc_180072B3A
0x180072b17  call    ?InitializeIcbForReadWrite@UDF_LVOL@@AEAAPEAVFILE_ICB_DESCRIPTOR@@PEAUICB_ENTRY@@PEAV2@PEAVDIR_ICB_DESCRIPTOR@@@Z; UDF_LVOL::InitializeIcbForReadWrite(ICB_ENTRY *,FILE_ICB_DESCRIPTOR *,DIR_ICB_DESCRIPTOR *)
0x180072b1c  mov     rbx, rax
0x180072b1f  xor     eax, eax
0x180072b21  test    rbx, rbx
0x180072b24  jz      loc_180072C48
0x180072b2a  mov     byte ptr [rsp+1F0h+var_1B8], al
0x180072b2e  mov     byte ptr [rsp+1F0h+var_1C0], al
0x180072b32  mov     eax, [r12]
0x180072b36  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x180072b3a  mov     rax, [rbp+0F0h+arg_18]
0x180072b41  mov     r8d, r14d
0x180072b44  mov     r9, [rbp+0F0h+arg_10]
0x180072b4b  mov     rdx, rbx
0x180072b4e  mov     rcx, rsi
0x180072b51  mov     [rsp+1F0h+var_1D0], rax
0x180072b56  call    ?DeleteIcbInReferences@UDF_LVOL@@AEAAEPEAVFILE_ICB_DESCRIPTOR@@W4FIX_LEVEL@@PEAVDIGRAPH@@PEAVICB_INFO@@KEE@Z; UDF_LVOL::DeleteIcbInReferences(FILE_ICB_DESCRIPTOR *,FIX_LEVEL,DIGRAPH *,ICB_INFO *,ulong,uchar,uchar)
0x180072b5b  test    al, al
0x180072b5d  jz      loc_180072C48
0x180072b63  mov     r14, [rbp+0F0h+arg_10]
0x180072b6a  mov     edx, r13d; unsigned int
0x180072b6d  mov     rcx, r14; this
0x180072b70  call    ?QueryNumParents@DIGRAPH@@QEBAKK@Z; DIGRAPH::QueryNumParents(ulong)
0x180072b75  movzx   r15d, ax
0x180072b79  mov     eax, 1
0x180072b7e  jmp     short loc_180072B8B
0x180072b80  mov     r14, [rbp+0F0h+arg_10]
0x180072b87  lea     r12, [rdi+0Ch]
0x180072b8b  cmp     r15w, ax
0x180072b8f  jnz     loc_180072D29
0x180072b95  lea     r9, [rbp+0F0h+arg_0]; unsigned int *
0x180072b9c  mov     r8d, r13d; unsigned int
0x180072b9f  mov     rdx, r14; struct DIGRAPH *
0x180072ba2  call    ?GetLoneParent@UDF_LVOL@@AEAAEPEAVDIGRAPH@@KPEAK@Z; UDF_LVOL::GetLoneParent(DIGRAPH *,ulong,ulong *)
0x180072ba7  test    al, al
0x180072ba9  jz      loc_180072C48
0x180072baf  lea     r14, [rdi+0Ch]
0x180072bb3  mov     eax, [r14]
0x180072bb6  cmp     eax, 0FFFFFFFFh
0x180072bb9  jz      loc_180072C7C
0x180072bbf  cmp     [rbp+0F0h+arg_0], eax
0x180072bc5  jz      loc_180072D5B
0x180072bcb  mov     rcx, [rsi+18h]; this
0x180072bcf  lea     r8, aD_0; "%d"
0x180072bd6  mov     r9d, r13d
0x180072bd9  mov     edx, 777Fh; unsigned int
0x180072bde  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180072be3  xor     r15d, r15d
0x180072be6  test    rbx, rbx
0x180072be9  jnz     short loc_180072C06
0x180072beb  lea     r9, [rbp+0F0h+var_100]; struct DIR_ICB_DESCRIPTOR *
0x180072bef  mov     rdx, rdi; struct ICB_ENTRY *
0x180072bf2  lea     r8, [rbp+0F0h+var_170]; struct FILE_ICB_DESCRIPTOR *
0x180072bf6  mov     rcx, rsi; this
0x180072bf9  call    ?InitializeIcbForReadWrite@UDF_LVOL@@AEAAPEAVFILE_ICB_DESCRIPTOR@@PEAUICB_ENTRY@@PEAV2@PEAVDIR_ICB_DESCRIPTOR@@@Z; UDF_LVOL::InitializeIcbForReadWrite(ICB_ENTRY *,FILE_ICB_DESCRIPTOR *,DIR_ICB_DESCRIPTOR *)
0x180072bfe  mov     rbx, rax
0x180072c01  test    rax, rax
0x180072c04  jz      short loc_180072C48
0x180072c06  mov     byte ptr [rsp+1F0h+var_1B8], r15b
0x180072c0b  mov     byte ptr [rsp+1F0h+var_1C0], r15b
0x180072c10  mov     rax, [rbp+0F0h+arg_18]
0x180072c17  mov     rdx, rbx
0x180072c1a  mov     r15, [rbp+0F0h+arg_10]
0x180072c21  mov     rcx, rsi
0x180072c24  mov     r8d, [rbp+0F0h+arg_8]
0x180072c2b  mov     r9, r15
0x180072c2e  mov     dword ptr [rsp+1F0h+var_1C8], 0FFFFFFFFh
0x180072c36  mov     [rsp+1F0h+var_1D0], rax
0x180072c3b  call    ?DeleteIcbInReferences@UDF_LVOL@@AEAAEPEAVFILE_ICB_DESCRIPTOR@@W4FIX_LEVEL@@PEAVDIGRAPH@@PEAVICB_INFO@@KEE@Z; UDF_LVOL::DeleteIcbInReferences(FILE_ICB_DESCRIPTOR *,FIX_LEVEL,DIGRAPH *,ICB_INFO *,ulong,uchar,uchar)
0x180072c40  test    al, al
0x180072c42  jnz     loc_180072D39
0x180072c48  lea     rcx, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x180072c4f  mov     [rsp+1F0h+var_1A0], rcx
0x180072c54  lea     rcx, [rbp+0F0h+var_100]; this
0x180072c58  call    ??1DIR_ICB_DESCRIPTOR@@UEAA@XZ; DIR_ICB_DESCRIPTOR::~DIR_ICB_DESCRIPTOR(void)
0x180072c5d  lea     rcx, [rbp+0F0h+var_170]; this
0x180072c61  call    ??1FILE_ICB_DESCRIPTOR@@UEAA@XZ; FILE_ICB_DESCRIPTOR::~FILE_ICB_DESCRIPTOR(void)
0x180072c66  xor     al, al
0x180072c68  add     rsp, 1B8h
0x180072c6f  pop     r15
0x180072c71  pop     r14
0x180072c73  pop     r13
0x180072c75  pop     r12
0x180072c77  pop     rdi
0x180072c78  pop     rsi
0x180072c79  pop     rbx
0x180072c7a  pop     rbp
0x180072c7b  retn
0x180072c7c  mov     rcx, [rsi+18h]; this
0x180072c80  lea     r8, aD_0; "%d"
0x180072c87  mov     r9d, r13d
0x180072c8a  mov     edx, 7780h; unsigned int
0x180072c8f  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180072c94  mov     al, [rdi+26h]
0x180072c97  cmp     [rdi+22h], al
0x180072c9a  jz      short loc_180072CCE
0x180072c9c  xor     r15d, r15d
0x180072c9f  test    rbx, rbx
0x180072ca2  jnz     short loc_180072CBF
0x180072ca4  lea     r9, [rbp+0F0h+var_100]; struct DIR_ICB_DESCRIPTOR *
0x180072ca8  mov     rdx, rdi; struct ICB_ENTRY *
0x180072cab  lea     r8, [rbp+0F0h+var_170]; struct FILE_ICB_DESCRIPTOR *
0x180072caf  mov     rcx, rsi; this
0x180072cb2  call    ?InitializeIcbForReadWrite@UDF_LVOL@@AEAAPEAVFILE_ICB_DESCRIPTOR@@PEAUICB_ENTRY@@PEAV2@PEAVDIR_ICB_DESCRIPTOR@@@Z; UDF_LVOL::InitializeIcbForReadWrite(ICB_ENTRY *,FILE_ICB_DESCRIPTOR *,DIR_ICB_DESCRIPTOR *)
0x180072cb7  mov     rbx, rax
0x180072cba  test    rax, rax
0x180072cbd  jz      short loc_180072C48
0x180072cbf  mov     byte ptr [rsp+1F0h+var_1B8], r15b
0x180072cc4  mov     byte ptr [rsp+1F0h+var_1C0], 1
0x180072cc9  jmp     loc_180072C10
0x180072cce  xor     eax, eax
0x180072cd0  test    rbx, rbx
0x180072cd3  jnz     short loc_180072CF6
0x180072cd5  lea     r9, [rbp+0F0h+var_100]; struct DIR_ICB_DESCRIPTOR *
0x180072cd9  mov     rdx, rdi; struct ICB_ENTRY *
0x180072cdc  lea     r8, [rbp+0F0h+var_170]; struct FILE_ICB_DESCRIPTOR *
0x180072ce0  mov     rcx, rsi; this
0x180072ce3  call    ?InitializeIcbForReadWrite@UDF_LVOL@@AEAAPEAVFILE_ICB_DESCRIPTOR@@PEAUICB_ENTRY@@PEAV2@PEAVDIR_ICB_DESCRIPTOR@@@Z; UDF_LVOL::InitializeIcbForReadWrite(ICB_ENTRY *,FILE_ICB_DESCRIPTOR *,DIR_ICB_DESCRIPTOR *)
0x180072ce8  mov     rbx, rax
0x180072ceb  xor     eax, eax
0x180072ced  test    rbx, rbx
0x180072cf0  jz      loc_180072C48
0x180072cf6  mov     r9d, [rbp+0F0h+arg_8]
0x180072cfd  mov     rdx, rbx
0x180072d00  mov     r8d, [rbp+0F0h+arg_0]
0x180072d07  mov     rcx, rsi
0x180072d0a  mov     byte ptr [rsp+1F0h+var_1C8], al
0x180072d0e  mov     rax, [rbp+0F0h+arg_18]
0x180072d15  mov     [rsp+1F0h+var_1D0], rax
0x180072d1a  call    ?AddParentFidToIcb@UDF_LVOL@@AEAAEPEAVDIR_ICB_DESCRIPTOR@@KW4FIX_LEVEL@@PEAVICB_INFO@@E@Z; UDF_LVOL::AddParentFidToIcb(DIR_ICB_DESCRIPTOR *,ulong,FIX_LEVEL,ICB_INFO *,uchar)
0x180072d1f  test    al, al
0x180072d21  jz      loc_180072C48
0x180072d27  jmp     short loc_180072D2C
0x180072d29  mov     r14, r12
0x180072d2c  test    r15w, r15w
0x180072d30  jnz     short loc_180072D5B
0x180072d32  mov     r15, [rbp+0F0h+arg_10]
0x180072d39  mov     rax, [rsi+40h]
0x180072d3d  cmp     r13d, [rax+194h]
0x180072d44  jz      short loc_180072D5B
0x180072d46  test    dword ptr [rax+1D0h], 3FFFFFFFh
0x180072d50  jz      short loc_180072DC8
0x180072d52  cmp     r13d, [rax+1D4h]
0x180072d59  jnz     short loc_180072DCB
0x180072d5b  mov     r12, [rbp+0F0h+arg_18]
0x180072d62  mov     r14d, [rbp+0F0h+arg_8]
0x180072d69  xor     r15d, r15d
0x180072d6c  cmp     [rdi+24h], r15w
0x180072d71  jbe     loc_180072FCB
0x180072d77  mov     al, [rdi+22h]
0x180072d7a  cmp     [rdi+26h], al
0x180072d7d  jz      loc_180072FCB
0x180072d83  mov     rcx, [rsi+18h]; this
0x180072d87  lea     r8, aD_0; "%d"
0x180072d8e  mov     r9d, r13d
0x180072d91  mov     edx, 7783h; unsigned int
  ... truncated ...
```
