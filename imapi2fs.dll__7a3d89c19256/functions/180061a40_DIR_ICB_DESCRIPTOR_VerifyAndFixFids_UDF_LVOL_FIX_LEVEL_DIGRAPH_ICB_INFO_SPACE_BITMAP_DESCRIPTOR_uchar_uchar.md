# DIR_ICB_DESCRIPTOR::VerifyAndFixFids(UDF_LVOL *,FIX_LEVEL,DIGRAPH *,ICB_INFO *,SPACE_BITMAP_DESCRIPTOR *,uchar *,uchar *)

- ea: `0x180061a40`
- end: `0x1800620da`
- name: `?VerifyAndFixFids@DIR_ICB_DESCRIPTOR@@QEAAEPEAVUDF_LVOL@@W4FIX_LEVEL@@PEAVDIGRAPH@@PEAVICB_INFO@@PEAVSPACE_BITMAP_DESCRIPTOR@@PEAE5@Z`
- size: `1690`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006fad0`

## callees

- `0x180004ab0`
- `0x1800251f6`
- `0x18005db28`
- `0x18005def4`
- `0x18005f118`
- `0x18005ff48`
- `0x18005ff7c`
- `0x1800604bc`
- `0x180060874`
- `0x180060a2c`
- `0x180061098`
- `0x1800613e8`
- `0x180061620`
- `0x180061960`
- `0x180061a18`
- `0x180061a40`
- `0x1800645f0`
- `0x180067510`
- `0x180067558`
- `0x180069fa8`
- `0x18006ca54`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006207b`
- `ntdll!RtlFreeHeap` at `0x18006207b`
- `ntdll!RtlAllocateHeap` at `0x180061cba`
- `ntdll!RtlAllocateHeap` at `0x180061cba`

## pseudocode

```c
char __fastcall DIR_ICB_DESCRIPTOR::VerifyAndFixFids(
        DESCRIPTOR *a1,
        __int64 a2,
        int a3,
        void *a4,
        ICB_INFO *a5,
        __int64 a6,
        _BYTE *a7,
        _BYTE *a8)
{
  MESSAGE *v8; // r14
  unsigned int TagLocation; // eax
  struct ICB_ENTRY *IcbEntry; // r13
  struct UDF_LVOL *v13; // r9
  char v14; // si
  __int64 v15; // rcx
  unsigned __int16 *v16; // rbx
  char v17; // al
  char v18; // cl
  unsigned int v19; // eax
  int v20; // r10d
  unsigned int AllocationTagForFileType; // eax
  unsigned __int16 PartitionNumberForAllocationTag; // ax
  __int64 v23; // rcx
  unsigned int v24; // r10d
  unsigned int v25; // eax
  int v26; // r10d
  char v27; // r12
  char v28; // al
  bool v29; // zf
  unsigned int v30; // eax
  PVOID Heap; // rax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // edx
  unsigned int v36; // eax
  char v37; // r14
  unsigned int v38; // eax
  unsigned int v39; // eax
  struct ICB_ENTRY *v40; // rax
  ICB_INFO *v41; // rcx
  struct ICB_ENTRY *NewIcbEntry; // rax
  struct ICB_ENTRY *v43; // r14
  WSTRING *v44; // rcx
  __int64 v45; // rdx
  struct ICB_ENTRY *v46; // rax
  ICB_INFO *v47; // rcx
  struct ICB_ENTRY *v48; // rax
  int v49; // r8d
  unsigned int v50; // r8d
  unsigned __int8 v51; // bl
  char v52; // r14
  PVOID v53; // r12
  unsigned __int8 v55; // [rsp+28h] [rbp-69h]
  char v56; // [rsp+38h] [rbp-59h]
  char v57; // [rsp+39h] [rbp-58h]
  char v58; // [rsp+3Ah] [rbp-57h]
  char v59; // [rsp+3Bh] [rbp-56h]
  unsigned __int8 v60; // [rsp+3Ch] [rbp-55h] BYREF
  unsigned __int8 v61; // [rsp+3Dh] [rbp-54h] BYREF
  char v62; // [rsp+3Eh] [rbp-53h]
  int v63; // [rsp+40h] [rbp-51h]
  MESSAGE *v64; // [rsp+48h] [rbp-49h]
  PVOID P; // [rsp+50h] [rbp-41h]
  unsigned __int64 v66; // [rsp+58h] [rbp-39h] BYREF
  void *Src; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v68[3]; // [rsp+68h] [rbp-29h] BYREF
  int v69; // [rsp+80h] [rbp-11h]
  __int64 v70; // [rsp+88h] [rbp-9h]
  int v71; // [rsp+90h] [rbp-1h]

  v8 = *(MESSAGE **)(a2 + 24);
  v68[0] = &DSTRING::`vftable';
  v68[1] = DSTRING_cd;
  Src = 0;
  v66 = 0;
  v61 = 0;
  v60 = 0;
  v68[2] = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v64 = v8;
  TagLocation = DESCRIPTOR::GetTagLocation(a1);
  IcbEntry = ICB_INFO::GetIcbEntry(a5, TagLocation);
  if ( !DIR_ICB_DESCRIPTOR::InitializeFidIterator(a1, a3 != 0, v13) )
    goto LABEL_85;
  P = 0;
  v14 = 2;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  while ( DIR_ICB_DESCRIPTOR::NextFid(a1, (struct NSR_FID **)&Src, &v61, &v60) )
  {
    v16 = (unsigned __int16 *)Src;
    v17 = *((_BYTE *)Src + 18);
    if ( (v17 & 4) == 0 )
    {
      v18 = *((_BYTE *)IcbEntry + 34);
      if ( (v17 & 8) != 0 )
      {
        if ( v18 != 2 )
        {
          if ( v18 == 4 )
          {
            if ( (v17 & 2) != 0 )
            {
              v14 = 4;
              if ( *((_DWORD *)IcbEntry + 2) != *((_DWORD *)Src + 6) )
                v14 = 2;
            }
            else
            {
              v14 = 1;
            }
          }
          else
          {
            v14 = 0;
          }
          if ( !v14 )
          {
            v14 = 2;
            goto LABEL_16;
          }
        }
LABEL_22:
        LOBYTE(v15) = v14;
        AllocationTagForFileType = UDF_LVOL::GetAllocationTagForFileType(v15);
        PartitionNumberForAllocationTag = UDF_LVOL::GetPartitionNumberForAllocationTag(a2, AllocationTagForFileType);
        if ( v16[14] != PartitionNumberForAllocationTag
          || v24 >= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v23 + 8LL * PartitionNumberForAllocationTag + 112) + 16LL) + 16LL) )
        {
          v25 = DESCRIPTOR::GetTagLocation(a1);
          MESSAGE::DisplayMsg(v8, 0x77CBu, "%d%d", v25, v26);
          *((_BYTE *)v16 + 18) |= 4u;
          v57 = 1;
          DIR_ICB_DESCRIPTOR::MarkFidAsModified(a1, (struct NSR_FID *)v16);
          goto LABEL_65;
        }
        v27 = 0;
        if ( v16[8] != 1 )
        {
          v16[8] = 1;
          v27 = 1;
        }
        if ( *(_BYTE *)(*((_QWORD *)a1 + 2) + 27LL) != 13 )
        {
          v28 = *((_BYTE *)v16 + 18);
          if ( (v28 & 0x10) != 0 )
          {
            v27 = 1;
            *((_BYTE *)v16 + 18) = v28 & 0xEF;
          }
        }
        if ( (v16[9] & 8) != 0 )
        {
          if ( v58 )
          {
            if ( *((_DWORD *)IcbEntry + 3) == v24 && v56 == v14 )
            {
              v33 = DESCRIPTOR::GetTagLocation(a1);
              MESSAGE::DisplayMsg(v8, 0x7772u, "%d", v33);
              v34 = DESCRIPTOR::GetTagLocation(a1);
              v35 = 30580;
              goto LABEL_39;
            }
            v36 = DESCRIPTOR::GetTagLocation(a1);
            MESSAGE::DisplayMsg(v8, 0x7771u, "%d", v36);
            v59 = 1;
            *((_DWORD *)IcbEntry + 3) = -1;
          }
          else
          {
            v29 = v63 == 0;
            *((_DWORD *)IcbEntry + 3) = v24;
            if ( !v29 )
            {
              v30 = DESCRIPTOR::GetTagLocation(a1);
              MESSAGE::DisplayMsg(v8, 0x7773u, "%d", v30);
              Heap = RtlAllocateHeap(
                       NtCurrentPeb()->ProcessHeap,
                       0,
                       (v16[18] + 41LL + *((unsigned __int8 *)v16 + 19)) & 0xFFFFFFFFFFFFFFFCuLL);
              P = Heap;
              if ( !Heap )
                goto LABEL_85;
              memcpy_0(Heap, v16, (v16[18] + 41LL + *((unsigned __int8 *)v16 + 19)) & 0xFFFFFFFFFFFFFFFCuLL);
              v32 = DESCRIPTOR::GetTagLocation(a1);
              MESSAGE::DisplayMsg(v8, 0x7774u, "%d%d", v32, *((_DWORD *)v16 + 6));
              DIR_ICB_DESCRIPTOR::RemoveFid(a1, (unsigned __int8 *)v16);
              v62 = 1;
            }
            v58 = 1;
            v56 = v14;
          }
          goto LABEL_62;
        }
        if ( *((_BYTE *)v16 + 19) )
        {
          v37 = 0;
          if ( (int)UncompressUnicode(
                      *((unsigned __int8 *)v16 + 19),
                      (unsigned __int8 *)v16 + v16[18] + 38,
                      (struct WSTRING *)v68) > 0 )
            goto LABEL_45;
          v8 = v64;
        }
        v38 = DESCRIPTOR::GetTagLocation(a1);
        MESSAGE::DisplayMsg(v8, 0x77B7u, "%d%d", v38, *((_DWORD *)v16 + 6));
        v37 = 1;
LABEL_45:
        if ( *((_BYTE *)IcbEntry + 34) == 4 && (v16[9] & 2) != 0 )
        {
          v39 = DESCRIPTOR::GetTagLocation(a1);
          v8 = v64;
          MESSAGE::DisplayMsg(v64, 0x77B6u, "%d%d", v39, *((_DWORD *)v16 + 6));
          goto LABEL_50;
        }
        if ( v37 )
        {
          v8 = v64;
LABEL_50:
          v34 = DESCRIPTOR::GetTagLocation(a1);
          v35 = 30581;
LABEL_39:
          MESSAGE::DisplayMsg(v8, v35, "%d%d", v34, *((_DWORD *)v16 + 6));
          *((_BYTE *)v16 + 18) |= 4u;
LABEL_63:
          v57 = 1;
          DIR_ICB_DESCRIPTOR::MarkFidAsModified(a1, (struct NSR_FID *)v16);
          goto LABEL_64;
        }
        DIGRAPH::AddEdge(a4, *((_DWORD *)IcbEntry + 2), *((_DWORD *)v16 + 6));
        v40 = ICB_INFO::GetIcbEntry(a5, *((_DWORD *)v16 + 6));
        if ( v40 )
        {
          if ( *((_BYTE *)v40 + 38) )
          {
            if ( *((_BYTE *)v40 + 38) != v14 )
              *((_BYTE *)v40 + 38) = 6;
          }
          else
          {
            *((_BYTE *)v40 + 38) = v14;
          }
          ++*((_WORD *)v40 + 18);
        }
        else
        {
          NewIcbEntry = ICB_INFO::CreateNewIcbEntry(v41);
          v43 = NewIcbEntry;
          if ( !NewIcbEntry )
            goto LABEL_85;
          *((_DWORD *)NewIcbEntry + 2) = *((_DWORD *)v16 + 6);
          v44 = (WSTRING *)*((_QWORD *)NewIcbEntry + 6);
          *((_WORD *)NewIcbEntry + 18) = 1;
          *((_BYTE *)NewIcbEntry + 38) = v14;
          if ( v44 )
            WSTRING::Initialize(v44, (const struct WSTRING *)v68, 0, 0xFFFFFFFF);
          v45 = *((_DWORD *)v43 + 2) & 0x3FF;
          *(_QWORD *)v43 = *(_QWORD *)(*((_QWORD *)a5 + 2) + 8 * v45);
          *(_QWORD *)(*((_QWORD *)a5 + 2) + 8 * v45) = v43;
        }
        v8 = v64;
LABEL_62:
        if ( v27 )
          goto LABEL_63;
LABEL_64:
        ++v63;
LABEL_65:
        v14 = 2;
      }
      else
      {
        if ( v18 == 4 )
        {
          if ( (v17 & 2) == 0 )
          {
            v14 = 3;
            goto LABEL_22;
          }
        }
        else if ( v18 == 2 )
        {
          v14 = ((v17 & 2) != 0) + 1;
          goto LABEL_22;
        }
LABEL_16:
        v19 = DESCRIPTOR::GetTagLocation(a1);
        MESSAGE::DisplayMsg(v8, 0x77D3u, "%d%d", v19, v20);
        *((_BYTE *)v16 + 18) |= 4u;
        v57 = 1;
        DIR_ICB_DESCRIPTOR::MarkFidAsModified(a1, (struct NSR_FID *)v16);
      }
    }
  }
  if ( !v58 || v59 )
    goto LABEL_76;
  v46 = ICB_INFO::GetIcbEntry(a5, *((_DWORD *)IcbEntry + 3));
  if ( !v46 )
  {
    v48 = ICB_INFO::CreateNewIcbEntry(v47);
    if ( v48 )
    {
      v49 = *((_DWORD *)IcbEntry + 3);
      *((_DWORD *)v48 + 2) = v49;
      v50 = v49 & 0x3FF;
      *((_WORD *)v48 + 18) = 1;
      *((_BYTE *)v48 + 38) = v56;
      *(_QWORD *)v48 = *(_QWORD *)(*((_QWORD *)a5 + 2) + 8LL * v50);
      *(_QWORD *)(*((_QWORD *)a5 + 2) + 8LL * v50) = v48;
      goto LABEL_76;
    }
    goto LABEL_85;
  }
  if ( *((_BYTE *)v46 + 38) )
  {
    if ( *((_BYTE *)v46 + 38) != v56 )
      *((_BYTE *)v46 + 38) = 6;
  }
  else
  {
    *((_BYTE *)v46 + 38) = v56;
  }
  ++*((_WORD *)v46 + 18);
LABEL_76:
  if ( v60 )
    goto LABEL_85;
  if ( !DIR_ICB_DESCRIPTOR::CleanUpFidIterator(a1, &v66) )
    goto LABEL_85;
  v51 = v61;
  if ( v61 )
  {
    FILE_ICB_DESCRIPTOR::SetInformationLength(a1, v66);
    v55 = 1;
    if ( !(*(unsigned __int8 (__fastcall **)(DESCRIPTOR *, unsigned __int64, __int64, __int64))(*(_QWORD *)a1 + 72LL))(
            a1,
            v66,
            a6,
            1) )
      goto LABEL_85;
  }
  if ( !FILE_ICB_DESCRIPTOR::SynchronizeIcbInfo(a1, a5) )
    goto LABEL_85;
  v52 = v62;
  if ( v62 )
  {
    if ( !a3 || v59 )
    {
      v53 = P;
    }
    else
    {
      v53 = P;
      if ( !DIR_ICB_DESCRIPTOR::AddParentEntry(a1, *((_DWORD *)P + 6), *((_BYTE *)P + 18), 1u, v55) )
        goto LABEL_85;
    }
    if ( v53 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v53);
  }
  if ( v59 && a3 && !DIR_ICB_DESCRIPTOR::DeleteAllParentEntries(a1) )
  {
LABEL_85:
    DSTRING::~DSTRING((DSTRING *)v68);
    return 0;
  }
  else
  {
    if ( v57 || v52 || v59 || v51 )
    {
      *a7 = 1;
      if ( a3 )
        *a8 = 1;
    }
    else
    {
      *a7 = 0;
    }
    DSTRING::~DSTRING((DSTRING *)v68);
    return 1;
  }
}

```

## disassembly

```asm
0x180061a40  mov     rax, rsp
0x180061a43  mov     [rax+8], rbx
0x180061a47  mov     [rax+20h], r9
0x180061a4b  mov     [rax+18h], r8d
0x180061a4f  mov     [rax+10h], rdx
0x180061a53  push    rbp
0x180061a54  push    rsi
0x180061a55  push    rdi
0x180061a56  push    r12
0x180061a58  push    r13
0x180061a5a  push    r14
0x180061a5c  push    r15
0x180061a5e  lea     rbp, [rax-3Fh]
0x180061a62  sub     rsp, 90h
0x180061a69  mov     r14, [rdx+18h]
0x180061a6d  lea     rax, ??_7DSTRING@@6B@; const DSTRING::`vftable'
0x180061a74  xor     ebx, ebx
0x180061a76  mov     [rbp+37h+var_60], rax
0x180061a7a  mov     rax, cs:?DSTRING_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const DSTRING_cd
0x180061a81  mov     r12d, r8d
0x180061a84  mov     [rbp+37h+var_58], rax
0x180061a88  mov     r9, rdx
0x180061a8b  mov     rdi, rcx
0x180061a8e  mov     [rbp+37h+Src], rbx
0x180061a92  mov     [rbp+37h+var_70], rbx
0x180061a96  mov     [rbp+37h+var_8B], bl
0x180061a99  mov     [rbp+37h+var_8C], bl
0x180061a9c  mov     [rbp+37h+var_50], rbx
0x180061aa0  mov     [rbp+37h+var_48], ebx
0x180061aa3  mov     [rbp+37h+var_40], rbx
0x180061aa7  mov     [rbp+37h+var_38], ebx
0x180061aaa  mov     [rbp+37h+var_80], r14
0x180061aae  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061ab3  mov     r15, [rbp+37h+arg_20]
0x180061ab7  mov     edx, eax; unsigned int
0x180061ab9  mov     rcx, r15; this
0x180061abc  call    ?GetIcbEntry@ICB_INFO@@QEAAPEAUICB_ENTRY@@K@Z; ICB_INFO::GetIcbEntry(ulong)
0x180061ac1  test    r12d, r12d
0x180061ac4  mov     r8, r9; struct UDF_LVOL *
0x180061ac7  mov     rcx, rdi; this
0x180061aca  mov     r13, rax
0x180061acd  setnz   dl; unsigned __int8
0x180061ad0  call    ?InitializeFidIterator@DIR_ICB_DESCRIPTOR@@QEAAEEPEAVUDF_LVOL@@@Z; DIR_ICB_DESCRIPTOR::InitializeFidIterator(uchar,UDF_LVOL *)
0x180061ad5  test    al, al
0x180061ad7  jz      loc_18006203A
0x180061add  mov     [rbp+37h+P], rbx
0x180061ae1  lea     esi, [rbx+2]
0x180061ae4  mov     [rbp+37h+var_90], bl
0x180061ae7  lea     r12d, [rbx+1]
0x180061aeb  mov     [rbp+37h+var_8F], bl
0x180061aee  mov     [rbp+37h+var_8E], bl
0x180061af1  mov     [rbp+37h+var_8D], bl
0x180061af4  mov     [rbp+37h+var_8A], bl
0x180061af7  mov     [rbp+37h+var_88], ebx
0x180061afa  jmp     short loc_180061AFE
0x180061afc  xor     ebx, ebx
0x180061afe  lea     r9, [rbp+37h+var_8C]; unsigned __int8 *
0x180061b02  mov     rcx, rdi; this
0x180061b05  lea     r8, [rbp+37h+var_8B]; unsigned __int8 *
0x180061b09  lea     rdx, [rbp+37h+Src]; struct NSR_FID **
0x180061b0d  call    ?NextFid@DIR_ICB_DESCRIPTOR@@QEAAEPEAPEAUNSR_FID@@PEAE1@Z; DIR_ICB_DESCRIPTOR::NextFid(NSR_FID * *,uchar *,uchar *)
0x180061b12  test    al, al
0x180061b14  jz      loc_180061F2D
0x180061b1a  mov     rbx, [rbp+37h+Src]
0x180061b1e  mov     al, [rbx+12h]
0x180061b21  test    al, 4
0x180061b23  jnz     short loc_180061AFC
0x180061b25  mov     r10d, [rbx+18h]
0x180061b29  mov     cl, [r13+22h]
0x180061b2d  test    al, 8
0x180061b2f  jz      short loc_180061BA3
0x180061b31  cmp     cl, sil
0x180061b34  jz      loc_180061BC1
0x180061b3a  cmp     cl, 4
0x180061b3d  jnz     short loc_180061B5A
0x180061b3f  test    sil, al
0x180061b42  jz      short loc_180061B55
0x180061b44  cmp     [r13+8], r10d
0x180061b48  mov     esi, 4
0x180061b4d  lea     eax, [rsi-2]
0x180061b50  cmovnz  esi, eax
0x180061b53  jmp     short loc_180061B5D
0x180061b55  mov     sil, r12b
0x180061b58  jmp     short loc_180061B5D
0x180061b5a  xor     sil, sil
0x180061b5d  test    sil, sil
0x180061b60  jnz     short loc_180061BC1
0x180061b62  mov     esi, 2
0x180061b67  mov     rcx, rdi; this
0x180061b6a  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061b6f  mov     r9d, eax
0x180061b72  mov     [rsp+20h], r10d
0x180061b77  mov     rcx, r14; this
0x180061b7a  lea     r8, aDD; "%d%d"
0x180061b81  mov     edx, 77D3h; unsigned int
0x180061b86  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061b8b  or      byte ptr [rbx+12h], 4
0x180061b8f  mov     rdx, rbx; struct NSR_FID *
0x180061b92  mov     rcx, rdi; this
0x180061b95  mov     [rbp+37h+var_8F], r12b
0x180061b99  call    ?MarkFidAsModified@DIR_ICB_DESCRIPTOR@@QEAAEPEAUNSR_FID@@@Z; DIR_ICB_DESCRIPTOR::MarkFidAsModified(NSR_FID *)
0x180061b9e  jmp     loc_180061AFC
0x180061ba3  cmp     cl, 4
0x180061ba6  jnz     short loc_180061BB2
0x180061ba8  test    sil, al
0x180061bab  jnz     short loc_180061B67
0x180061bad  mov     sil, 3
0x180061bb0  jmp     short loc_180061BC1
0x180061bb2  cmp     cl, sil
0x180061bb5  jnz     short loc_180061B67
0x180061bb7  test    sil, al
0x180061bba  setnz   sil
0x180061bbe  add     sil, r12b
0x180061bc1  mov     cl, sil
0x180061bc4  call    ?GetAllocationTagForFileType@UDF_LVOL@@SA?AW4ALLOCATION_TAG@@E@Z; UDF_LVOL::GetAllocationTagForFileType(uchar)
0x180061bc9  mov     rcx, [rbp+37h+arg_8]
0x180061bcd  mov     edx, eax
0x180061bcf  call    ?GetPartitionNumberForAllocationTag@UDF_LVOL@@QEAAGW4ALLOCATION_TAG@@@Z; UDF_LVOL::GetPartitionNumberForAllocationTag(ALLOCATION_TAG)
0x180061bd4  cmp     [rbx+1Ch], ax
0x180061bd8  jnz     short loc_180061BEC
0x180061bda  movzx   eax, ax
0x180061bdd  mov     rcx, [rcx+rax*8+70h]
0x180061be2  mov     rax, [rcx+10h]
0x180061be6  cmp     r10d, [rax+10h]
0x180061bea  jb      short loc_180061C28
0x180061bec  mov     rcx, rdi; this
0x180061bef  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061bf4  mov     r9d, eax
0x180061bf7  mov     [rsp+20h], r10d
0x180061bfc  mov     rcx, r14; this
0x180061bff  lea     r8, aDD; "%d%d"
0x180061c06  mov     edx, 77CBh; unsigned int
0x180061c0b  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061c10  or      byte ptr [rbx+12h], 4
0x180061c14  mov     rdx, rbx; struct NSR_FID *
0x180061c17  mov     rcx, rdi; this
0x180061c1a  mov     [rbp+37h+var_8F], r12b
0x180061c1e  call    ?MarkFidAsModified@DIR_ICB_DESCRIPTOR@@QEAAEPEAUNSR_FID@@@Z; DIR_ICB_DESCRIPTOR::MarkFidAsModified(NSR_FID *)
0x180061c23  jmp     loc_180061F23
0x180061c28  xor     r12b, r12b
0x180061c2b  mov     ecx, 1
0x180061c30  cmp     [rbx+10h], cx
0x180061c34  jz      short loc_180061C3D
0x180061c36  mov     [rbx+10h], cx
0x180061c3a  mov     r12b, cl
0x180061c3d  mov     rax, [rdi+10h]
0x180061c41  cmp     byte ptr [rax+1Bh], 0Dh
0x180061c45  jz      short loc_180061C56
0x180061c47  mov     al, [rbx+12h]
0x180061c4a  test    al, 10h
0x180061c4c  jz      short loc_180061C56
0x180061c4e  and     al, 0EFh
0x180061c50  mov     r12b, cl
0x180061c53  mov     [rbx+12h], al
0x180061c56  test    byte ptr [rbx+12h], 8
0x180061c5a  jz      loc_180061DBB
0x180061c60  cmp     [rbp+37h+var_8E], 0
0x180061c64  jnz     loc_180061D31
0x180061c6a  cmp     [rbp+37h+var_88], 0
0x180061c6e  mov     [r13+0Ch], r10d
0x180061c72  jz      loc_180061D25
0x180061c78  mov     rcx, rdi; this
0x180061c7b  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061c80  mov     r9d, eax
0x180061c83  lea     r8, aD_0; "%d"
0x180061c8a  mov     rcx, r14; this
0x180061c8d  mov     edx, 7773h; unsigned int
0x180061c92  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061c97  movzx   ecx, word ptr [rbx+24h]
0x180061c9b  xor     edx, edx; Flags
0x180061c9d  movzx   r8d, byte ptr [rbx+13h]
0x180061ca2  add     rcx, 29h ; ')'
0x180061ca6  add     r8, rcx
0x180061ca9  mov     rcx, gs:60h
0x180061cb2  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x180061cb6  mov     rcx, [rcx+30h]; HeapHandle
0x180061cba  call    cs:__imp_RtlAllocateHeap
0x180061cc0  mov     [rbp+37h+P], rax
0x180061cc4  test    rax, rax
0x180061cc7  jz      loc_18006203A
0x180061ccd  movzx   edx, word ptr [rbx+24h]
0x180061cd1  mov     rcx, rax; void *
0x180061cd4  movzx   r8d, byte ptr [rbx+13h]
0x180061cd9  add     rdx, 29h ; ')'
0x180061cdd  add     r8, rdx
0x180061ce0  mov     rdx, rbx; Src
0x180061ce3  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x180061ce7  call    memcpy_0
0x180061cec  mov     rcx, rdi; this
0x180061cef  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061cf4  mov     r9d, eax
0x180061cf7  lea     r8, aDD; "%d%d"
0x180061cfe  mov     eax, [rbx+18h]
0x180061d01  mov     edx, 7774h; unsigned int
0x180061d06  mov     rcx, r14; this
0x180061d09  mov     [rsp+20h], eax
0x180061d0d  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061d12  mov     rdx, rbx; unsigned __int8 *
0x180061d15  mov     rcx, rdi; this
0x180061d18  call    ?RemoveFid@DIR_ICB_DESCRIPTOR@@QEAAEPEAE@Z; DIR_ICB_DESCRIPTOR::RemoveFid(uchar *)
0x180061d1d  mov     ecx, 1
0x180061d22  mov     [rbp+37h+var_8A], cl
0x180061d25  mov     [rbp+37h+var_8E], cl
0x180061d28  mov     [rbp+37h+var_90], sil
0x180061d2c  jmp     loc_180061EFD
0x180061d31  cmp     [r13+0Ch], r10d
0x180061d35  jnz     short loc_180061D8B
0x180061d37  cmp     [rbp+37h+var_90], sil
0x180061d3b  jnz     short loc_180061D8B
0x180061d3d  mov     rcx, rdi; this
0x180061d40  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061d45  mov     r9d, eax
0x180061d48  lea     r8, aD_0; "%d"
0x180061d4f  mov     rcx, r14; this
0x180061d52  mov     edx, 7772h; unsigned int
0x180061d57  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061d5c  mov     rcx, rdi; this
0x180061d5f  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061d64  mov     edx, 7774h; unsigned int
0x180061d69  mov     r9d, eax
0x180061d6c  lea     r8, aDD; "%d%d"
0x180061d73  mov     eax, [rbx+18h]
0x180061d76  mov     rcx, r14; this
0x180061d79  mov     [rsp+20h], eax
0x180061d7d  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061d82  or      byte ptr [rbx+12h], 4
0x180061d86  jmp     loc_180061F02
0x180061d8b  mov     rcx, rdi; this
0x180061d8e  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061d93  mov     r9d, eax
0x180061d96  lea     r8, aD_0; "%d"
0x180061d9d  mov     rcx, r14; this
0x180061da0  mov     edx, 7771h; unsigned int
0x180061da5  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061daa  mov     [rbp+37h+var_8D], 1
0x180061dae  mov     dword ptr [r13+0Ch], 0FFFFFFFFh
0x180061db6  jmp     loc_180061EFD
0x180061dbb  cmp     [rbx+13h], cl
0x180061dbe  jb      short loc_180061DE3
0x180061dc0  movzx   edx, word ptr [rbx+24h]
0x180061dc4  lea     r8, [rbp+37h+var_60]; struct WSTRING *
0x180061dc8  movzx   ecx, byte ptr [rbx+13h]; int
0x180061dcc  add     rdx, 26h ; '&'
0x180061dd0  add     rdx, rbx; unsigned __int8 *
0x180061dd3  xor     r14b, r14b
0x180061dd6  call    ?UncompressUnicode@@YAHHPEAEPEAVWSTRING@@@Z; UncompressUnicode(int,uchar *,WSTRING *)
0x180061ddb  test    eax, eax
0x180061ddd  jg      short loc_180061E0C
0x180061ddf  mov     r14, [rbp+37h+var_80]
0x180061de3  mov     rcx, rdi; this
0x180061de6  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061deb  mov     r9d, eax
0x180061dee  lea     r8, aDD; "%d%d"
0x180061df5  mov     eax, [rbx+18h]
0x180061df8  mov     edx, 77B7h; unsigned int
0x180061dfd  mov     rcx, r14; this
0x180061e00  mov     [rsp+20h], eax
0x180061e04  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061e09  mov     r14b, 1
0x180061e0c  cmp     byte ptr [r13+22h], 4
0x180061e11  jnz     short loc_180061E45
0x180061e13  test    byte ptr [rbx+12h], 2
0x180061e17  jz      short loc_180061E45
0x180061e19  mov     rcx, rdi; this
0x180061e1c  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061e21  mov     r14, [rbp+37h+var_80]
0x180061e25  lea     r8, aDD; "%d%d"
0x180061e2c  mov     r9d, eax
0x180061e2f  mov     rcx, r14; this
0x180061e32  mov     eax, [rbx+18h]
0x180061e35  mov     edx, 77B6h; unsigned int
0x180061e3a  mov     [rsp+20h], eax
0x180061e3e  call    ?DisplayMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::DisplayMsg(ulong,char const *,...)
0x180061e43  jmp     short loc_180061E4E
0x180061e45  test    r14b, r14b
0x180061e48  jz      short loc_180061E60
0x180061e4a  mov     r14, [rbp+37h+var_80]
0x180061e4e  mov     rcx, rdi; this
0x180061e51  call    ?GetTagLocation@DESCRIPTOR@@QEAAKXZ; DESCRIPTOR::GetTagLocation(void)
0x180061e56  mov     edx, 7775h
0x180061e5b  jmp     loc_180061D69
0x180061e60  mov     r8d, [rbx+18h]; unsigned int
0x180061e64  mov     edx, [r13+8]; unsigned int
0x180061e68  mov     rcx, [rbp+37h+TableContext]; TableContext
0x180061e6c  call    ?AddEdge@DIGRAPH@@QEAAEKK@Z; DIGRAPH::AddEdge(ulong,ulong)
0x180061e71  mov     edx, [rbx+18h]; unsigned int
0x180061e74  mov     rcx, r15; this
0x180061e77  call    ?GetIcbEntry@ICB_INFO@@QEAAPEAUICB_ENTRY@@K@Z; ICB_INFO::GetIcbEntry(ulong)
0x180061e7c  test    rax, rax
0x180061e7f  jnz     short loc_180061EDA
0x180061e81  call    ?CreateNewIcbEntry@ICB_INFO@@QEAAPEAUICB_ENTRY@@XZ; ICB_INFO::CreateNewIcbEntry(void)
0x180061e86  mov     r14, rax
0x180061e89  test    rax, rax
0x180061e8c  jz      loc_18006203A
0x180061e92  mov     ecx, [rbx+18h]
0x180061e95  mov     [rax+8], ecx
0x180061e98  mov     rcx, [rax+30h]; this
0x180061e9c  mov     word ptr [rax+24h], 1
0x180061ea2  mov     [rax+26h], sil
0x180061ea6  test    rcx, rcx
  ... truncated ...
```
