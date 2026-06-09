# CXMLReader::ProcessColumnAttribute(CParseNode *,ushort,CMetaData *)

- ea: `0x1800275e4`
- end: `0x180027c44`
- name: `?ProcessColumnAttribute@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z`
- size: `1632`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, unsigned __int16, struct CMetaData *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x180024434`
- `0x180027c4c`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180003c38`
- `0x180004d30`
- `0x180004e24`
- `0x180004f24`
- `0x180005018`
- `0x18000510c`
- `0x180005180`
- `0x18001b008`
- `0x180026d04`
- `0x180027324`
- `0x1800275e4`
- `0x1800295d0`
- `0x180029c8c`
- `0x180029dc0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800277f2`
- `OLEAUT32!__imp_SysStringLen` at `0x180027a4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180027aff`
- `OLEAUT32!__imp_SysStringLen` at `0x1800277f2`
- `OLEAUT32!__imp_SysStringLen` at `0x180027a4f`
- `OLEAUT32!__imp_SysStringLen` at `0x180027aff`
- `OLEAUT32!__imp_VariantInit` at `0x180027623`
- `OLEAUT32!__imp_VariantInit` at `0x180027623`
- `OLEAUT32!__imp_VariantClear` at `0x180027c24`
- `OLEAUT32!__imp_VariantClear` at `0x180027c24`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800276e3`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027744`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027796`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027815`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002787e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002793d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027993`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027a01`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800276e3`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027744`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027796`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027815`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002787e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002793d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027993`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027a01`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::ProcessColumnAttribute(
        CXMLReader *this,
        struct CParseNode *a2,
        unsigned __int16 a3,
        struct CMetaData *a4)
{
  __int64 v5; // rsi
  unsigned __int16 **Value; // rax
  unsigned int v9; // eax
  HRESULT v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int Flags; // r14d
  int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  UINT v21; // eax
  unsigned int v22; // edx
  unsigned int v23; // r15d
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // r14
  int v26; // r15d
  __int64 v27; // r14
  UINT v28; // eax
  unsigned __int16 v29; // r10
  unsigned __int16 v30; // r10
  VARIANTARG pvarg; // [rsp+48h] [rbp-70h] BYREF
  _QWORD pvarSrc[11]; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int64 v34; // [rsp+C8h] [rbp+10h] BYREF

  v5 = a3;
  memset(pvarSrc, 0, 32);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  Value = (unsigned __int16 **)CParseNode::GetValue(a2);
  v9 = CXMLReader::LookupAttributeInfo(
         this,
         *((_DWORD *)a2 + 1),
         *((unsigned __int16 **)a2 + 4),
         *Value,
         (struct tagDBATTRIBINFO *)pvarSrc);
  v10 = v9;
  if ( v9 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049D30[0] )
      bidTraceW(off_180049208[0], 930816, off_180049D30[0], v9, 909);
    goto LABEL_64;
  }
  if ( HIDWORD(pvarSrc[0]) == 16 )
  {
    CMetaData::mdSetName(a4, v5, (unsigned __int16 *)pvarSrc[2], 0xFFFFu);
    goto LABEL_64;
  }
  if ( HIDWORD(pvarSrc[0]) == 17 )
  {
    v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 3u);
    if ( v10 >= 0 )
    {
      v11 = 9648 * v5;
      *(_QWORD *)(v11 + *((_QWORD *)a4 + 4) + 1040) = pvarg.cyVal.Lo;
      *(_DWORD *)(v11 + *((_QWORD *)a4 + 4) + 1048) = 0;
    }
    goto LABEL_64;
  }
  if ( (unsigned int)(HIDWORD(pvarSrc[0]) - 18) <= 1 )
  {
    v34 = 0;
    v27 = 9648 * v5;
    if ( *(_DWORD *)(9648 * v5 + *((_QWORD *)a4 + 4) + 1056) != 3 && HIDWORD(pvarSrc[0]) != 19 )
      goto LABEL_64;
    v28 = SysStringLen((BSTR)pvarSrc[2]);
    if ( (unsigned int)CCollectionList::LookUpByKey(
                         (CXMLReader *)((char *)this + 304),
                         (unsigned __int16 *)pvarSrc[2],
                         v28,
                         &v34) )
      goto LABEL_64;
    if ( HIDWORD(pvarSrc[0]) == 18 && *((_BYTE *)this + 472) )
    {
      v29 = v34;
      if ( (_WORD)v34 == 20 )
      {
        *(_WORD *)(v27 + *((_QWORD *)a4 + 4) + 1052) = 6;
LABEL_61:
        *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1056) = 0;
        if ( IsFixedLength(v29) )
        {
          v34 = 0;
          *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1092) = CMetaData::mdGetFlags(a4, v5) | 0x10;
          *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1096) = 0;
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int64 *, _QWORD))(**((_QWORD **)this + 61)
                                                                                                 + 40LL))(
                 *((_QWORD *)this + 61),
                 v30,
                 v30,
                 0,
                 &v34,
                 0) >= 0 )
          {
            *(_QWORD *)(v27 + *((_QWORD *)a4 + 4) + 1064) = (unsigned int)v34;
            *(_DWORD *)(v27 + *((_QWORD *)a4 + 4) + 1072) = 0;
          }
        }
        goto LABEL_64;
      }
    }
    else
    {
      v29 = v34;
    }
    *(_WORD *)(v27 + *((_QWORD *)a4 + 4) + 1052) = v29;
    goto LABEL_61;
  }
  switch ( HIDWORD(pvarSrc[0]) )
  {
    case 0x14:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0x11u);
      if ( v10 >= 0 )
      {
        v12 = 9648 * v5;
        *(_WORD *)(v12 + *((_QWORD *)a4 + 4) + 1076) = pvarg.bVal;
        *(_DWORD *)(v12 + *((_QWORD *)a4 + 4) + 1080) = 0;
      }
      break;
    case 0x15:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0x11u);
      if ( v10 >= 0 )
      {
        v13 = 9648 * v5;
        *(_WORD *)(v13 + *((_QWORD *)a4 + 4) + 1084) = pvarg.bVal;
        *(_DWORD *)(v13 + *((_QWORD *)a4 + 4) + 1088) = 0;
      }
      break;
    case 0x16:
      Flags = CMetaData::mdGetFlags(a4, v5);
      if ( !SysStringLen((BSTR)pvarSrc[2]) )
        goto LABEL_21;
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 < 0 )
        break;
      if ( pvarg.iVal != -1 )
        v15 = ~LODWORD(pvarSrc[0]) & Flags;
      else
LABEL_21:
        v15 = LODWORD(pvarSrc[0]) | Flags;
      v16 = 9648 * v5;
      *(_DWORD *)(v16 + *((_QWORD *)a4 + 4) + 1092) = v15;
      *(_DWORD *)(v16 + *((_QWORD *)a4 + 4) + 1096) = 0;
      break;
    case 0x1C:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 5u);
      if ( v10 >= 0 )
      {
        v17 = 9648 * v5;
        *(_QWORD *)(v17 + *((_QWORD *)a4 + 4) + 1064) = (unsigned int)(int)pvarg.dblVal;
        *(_DWORD *)(v17 + *((_QWORD *)a4 + 4) + 1072) = 0;
      }
      break;
    case 0x17:
      CMetaData::mdSetBaseColumn(a4, v5, (unsigned __int16 *)pvarSrc[2], 0xFFFFu);
      break;
    case 0x1A:
      CMetaData::mdSetBaseCatalog(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x1B:
      CMetaData::mdSetBaseSchema(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x18:
      CMetaData::mdSetBaseTable(a4, v5, (unsigned __int16 *)pvarSrc[2], 0x11u);
      break;
    case 0x1D:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 )
      {
        v18 = 9648 * v5;
        *(_WORD *)(v18 + *((_QWORD *)a4 + 4) + 9580) = pvarg.iVal;
        *(_DWORD *)(v18 + *((_QWORD *)a4 + 4) + 9584) = 0;
      }
      break;
    case 0x1E:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 && pvarg.iVal == -1 )
      {
        --*((_WORD *)a4 + 1);
        v19 = 9648 * v5;
        *(GUID *)(v19 + *((_QWORD *)a4 + 4) + 2144) = DBCOL_SPECIALCOL;
        *(_DWORD *)(v19 + *((_QWORD *)a4 + 4) + 2160) = 0;
      }
      break;
    case 0x19:
      v10 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, 0xBu);
      if ( v10 >= 0 )
      {
        v20 = 9648 * v5;
        *(_WORD *)(v20 + *((_QWORD *)a4 + 4) + 9528) = pvarg.iVal;
        *(_DWORD *)(v20 + *((_QWORD *)a4 + 4) + 9532) = 0;
      }
      break;
    case 0x1F:
      v21 = SysStringLen((BSTR)pvarSrc[2]);
      v23 = v21;
      if ( v21 )
      {
        LODWORD(v34) = 0;
        v24 = MMMAlloc(v21 >> 1, v22);
        v25 = v24;
        if ( v24 )
        {
          v26 = DecodeBin((unsigned __int16 *)pvarSrc[2], v24, v23, (int *)&v34);
          if ( v26 >= 0 )
          {
            CMetaData::mdSetCalculationInfo(a4, v5, v25, v34);
          }
          else
          {
            operator delete(v25);
            v10 = v26;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
      break;
  }
LABEL_64:
  VariantClear(&pvarg);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800275e4  push    rbx
0x1800275e6  push    rsi
0x1800275e7  push    rdi
0x1800275e8  push    r12
0x1800275ea  push    r14
0x1800275ec  push    r15
0x1800275ee  sub     rsp, 88h
0x1800275f5  mov     rdi, r9
0x1800275f8  movzx   esi, r8w
0x1800275fc  mov     rbx, rdx
0x1800275ff  mov     r15, rcx
0x180027602  xorps   xmm0, xmm0
0x180027605  movups  xmmword ptr [rsp+0B8h+pvarSrc], xmm0
0x18002760a  movups  xmmword ptr [rsp+0B8h+pvarSrc+10h], xmm0
0x18002760f  xorps   xmm1, xmm1
0x180027612  xor     eax, eax
0x180027614  movups  xmmword ptr [rsp+0B8h+pvarg], xmm1
0x180027619  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x18002761e  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x180027623  call    cs:__imp_VariantInit
0x18002762a  nop     dword ptr [rax+rax+00h]
0x18002762f  mov     rcx, rbx; this
0x180027632  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180027637  lea     rcx, [rsp+0B8h+pvarSrc]
0x18002763c  mov     [rsp+0B8h+var_98], rcx; struct tagDBATTRIBINFO *
0x180027641  mov     r9, [rax]; unsigned __int16 *
0x180027644  mov     r8, [rbx+20h]; unsigned __int16 *
0x180027648  mov     edx, [rbx+4]; unsigned int
0x18002764b  mov     rcx, r15; this
0x18002764e  call    ?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z; CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)
0x180027653  mov     ebx, eax
0x180027655  xor     r12d, r12d
0x180027658  test    eax, eax
0x18002765a  jz      short loc_1800276A1
0x18002765c  test    byte ptr cs:_bidGblFlags, 2
0x180027663  jz      loc_180027C1F
0x180027669  mov     rcx, cs:off_180049D30; "<CXMLReader::ProcessColumnAttribute|ADO"...
0x180027670  test    rcx, rcx
0x180027673  jz      loc_180027C1F
0x180027679  mov     dword ptr [rsp+0B8h+var_98], 38Dh
0x180027681  mov     r9d, eax
0x180027684  mov     r8, cs:off_180049D30; "<CXMLReader::ProcessColumnAttribute|ADO"...
0x18002768b  mov     edx, 0E3400h
0x180027690  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027697  call    _bidTraceW
0x18002769c  jmp     loc_180027C1F
0x1800276a1  mov     ecx, dword ptr [rsp+0B8h+pvarSrc+4]
0x1800276a5  cmp     ecx, 10h
0x1800276a8  jnz     short loc_1800276C5
0x1800276aa  mov     r9d, 0FFFFh; unsigned __int16
0x1800276b0  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x1800276b5  movzx   edx, si; unsigned __int16
0x1800276b8  mov     rcx, rdi; this
0x1800276bb  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x1800276c0  jmp     loc_180027922
0x1800276c5  mov     r9d, 11h; unsigned __int16
0x1800276cb  cmp     ecx, r9d
0x1800276ce  jnz     short loc_180027722
0x1800276d0  mov     r9d, 3; vt
0x1800276d6  xor     r8d, r8d; wFlags
0x1800276d9  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x1800276de  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x1800276e3  call    cs:__imp_VariantChangeType
0x1800276ea  nop     dword ptr [rax+rax+00h]
0x1800276ef  mov     ebx, eax
0x1800276f1  test    eax, eax
0x1800276f3  jns     short loc_1800276FA
0x1800276f5  jmp     loc_180027C1F
0x1800276fa  imul    rdx, rsi, 25B0h
0x180027701  mov     ecx, dword ptr [rsp+0B8h+pvarg+8]
0x180027705  mov     rax, [rdi+20h]
0x180027709  mov     [rdx+rax+410h], rcx
0x180027711  mov     rax, [rdi+20h]
0x180027715  mov     [rdx+rax+418h], r12d
0x18002771d  jmp     loc_180027C16
0x180027722  lea     eax, [rcx-12h]
0x180027725  cmp     eax, 1
0x180027728  jbe     loc_180027AD3
0x18002772e  mov     eax, 14h
0x180027733  cmp     ecx, eax
0x180027735  jnz     short loc_180027784
0x180027737  xor     r8d, r8d; wFlags
0x18002773a  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x18002773f  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180027744  call    cs:__imp_VariantChangeType
0x18002774b  nop     dword ptr [rax+rax+00h]
0x180027750  mov     ebx, eax
0x180027752  test    eax, eax
0x180027754  jns     short loc_18002775B
0x180027756  jmp     loc_180027C1F
0x18002775b  imul    rdx, rsi, 25B0h
0x180027762  movzx   ecx, byte ptr [rsp+0B8h+pvarg+8]
0x180027767  mov     rax, [rdi+20h]
0x18002776b  mov     [rdx+rax+434h], cx
0x180027773  mov     rax, [rdi+20h]
0x180027777  mov     [rdx+rax+438h], r12d
0x18002777f  jmp     loc_180027C16
0x180027784  cmp     ecx, 15h
0x180027787  jnz     short loc_1800277D6
0x180027789  xor     r8d, r8d; wFlags
0x18002778c  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180027791  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180027796  call    cs:__imp_VariantChangeType
0x18002779d  nop     dword ptr [rax+rax+00h]
0x1800277a2  mov     ebx, eax
0x1800277a4  test    eax, eax
0x1800277a6  jns     short loc_1800277AD
0x1800277a8  jmp     loc_180027C1F
0x1800277ad  imul    rdx, rsi, 25B0h
0x1800277b4  movzx   ecx, byte ptr [rsp+0B8h+pvarg+8]
0x1800277b9  mov     rax, [rdi+20h]
0x1800277bd  mov     [rdx+rax+43Ch], cx
0x1800277c5  mov     rax, [rdi+20h]
0x1800277c9  mov     [rdx+rax+440h], r12d
0x1800277d1  jmp     loc_180027C16
0x1800277d6  cmp     ecx, 16h
0x1800277d9  jnz     loc_180027868
0x1800277df  movzx   edx, si; unsigned __int16
0x1800277e2  mov     rcx, rdi; this
0x1800277e5  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x1800277ea  mov     r14d, eax
0x1800277ed  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; pbstr
0x1800277f2  call    cs:__imp_SysStringLen
0x1800277f9  nop     dword ptr [rax+rax+00h]
0x1800277fe  test    eax, eax
0x180027800  jz      short loc_180027834
0x180027802  mov     r9d, 0Bh; vt
0x180027808  xor     r8d, r8d; wFlags
0x18002780b  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180027810  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180027815  call    cs:__imp_VariantChangeType
0x18002781c  nop     dword ptr [rax+rax+00h]
0x180027821  mov     ebx, eax
0x180027823  test    eax, eax
0x180027825  jns     short loc_18002782C
0x180027827  jmp     loc_180027C1F
0x18002782c  cmp     word ptr [rsp+0B8h+pvarg+8], 0FFFFh
0x180027832  jnz     short loc_18002783B
0x180027834  or      r14d, dword ptr [rsp+0B8h+pvarSrc]
0x180027839  jmp     short loc_180027844
0x18002783b  mov     eax, dword ptr [rsp+0B8h+pvarSrc]
0x18002783f  not     eax
0x180027841  and     r14d, eax
0x180027844  imul    rcx, rsi, 25B0h
0x18002784b  mov     rax, [rdi+20h]
0x18002784f  mov     [rcx+rax+444h], r14d
0x180027857  mov     rax, [rdi+20h]
0x18002785b  mov     [rcx+rax+448h], r12d
0x180027863  jmp     loc_180027C16
0x180027868  cmp     ecx, 1Ch
0x18002786b  jnz     short loc_1800278C2
0x18002786d  lea     r9d, [rcx-17h]; vt
0x180027871  xor     r8d, r8d; wFlags
0x180027874  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180027879  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x18002787e  call    cs:__imp_VariantChangeType
0x180027885  nop     dword ptr [rax+rax+00h]
0x18002788a  mov     ebx, eax
0x18002788c  test    eax, eax
0x18002788e  jns     short loc_180027895
0x180027890  jmp     loc_180027C1F
0x180027895  imul    rdx, rsi, 25B0h
0x18002789c  cvttsd2si rcx, qword ptr [rsp+0B8h+pvarg+8]
0x1800278a3  mov     ecx, ecx
0x1800278a5  mov     rax, [rdi+20h]
0x1800278a9  mov     [rdx+rax+428h], rcx
0x1800278b1  mov     rax, [rdi+20h]
0x1800278b5  mov     [rdx+rax+430h], r12d
0x1800278bd  jmp     loc_180027C16
0x1800278c2  cmp     ecx, 17h
0x1800278c5  jnz     short loc_1800278DF
0x1800278c7  mov     r9d, 0FFFFh; unsigned __int16
0x1800278cd  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x1800278d2  movzx   edx, si; unsigned __int16
0x1800278d5  mov     rcx, rdi; this
0x1800278d8  call    ?mdSetBaseColumn@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseColumn(ushort,ushort *,ushort)
0x1800278dd  jmp     short loc_180027922
0x1800278df  cmp     ecx, 1Ah
0x1800278e2  jnz     short loc_1800278F6
0x1800278e4  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x1800278e9  movzx   edx, si; unsigned __int16
0x1800278ec  mov     rcx, rdi; this
0x1800278ef  call    ?mdSetBaseCatalog@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseCatalog(ushort,ushort *,ushort)
0x1800278f4  jmp     short loc_180027922
0x1800278f6  cmp     ecx, 1Bh
0x1800278f9  jnz     short loc_18002790D
0x1800278fb  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180027900  movzx   edx, si; unsigned __int16
0x180027903  mov     rcx, rdi; this
0x180027906  call    ?mdSetBaseSchema@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseSchema(ushort,ushort *,ushort)
0x18002790b  jmp     short loc_180027922
0x18002790d  cmp     ecx, 18h
0x180027910  jnz     short loc_180027927
0x180027912  mov     r8, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180027917  movzx   edx, si; unsigned __int16
0x18002791a  mov     rcx, rdi; this
0x18002791d  call    ?mdSetBaseTable@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetBaseTable(ushort,ushort *,ushort)
0x180027922  jmp     loc_180027C16
0x180027927  cmp     ecx, 1Dh
0x18002792a  jnz     short loc_18002797D
0x18002792c  lea     r9d, [rcx-12h]; vt
0x180027930  xor     r8d, r8d; wFlags
0x180027933  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x180027938  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x18002793d  call    cs:__imp_VariantChangeType
0x180027944  nop     dword ptr [rax+rax+00h]
0x180027949  mov     ebx, eax
0x18002794b  test    eax, eax
0x18002794d  jns     short loc_180027954
0x18002794f  jmp     loc_180027C1F
0x180027954  imul    rdx, rsi, 25B0h
0x18002795b  mov     rcx, [rdi+20h]
0x18002795f  movzx   eax, word ptr [rsp+0B8h+pvarg+8]
0x180027964  mov     [rdx+rcx+256Ch], ax
0x18002796c  mov     rax, [rdi+20h]
0x180027970  mov     [rdx+rax+2570h], r12d
0x180027978  jmp     loc_180027C16
0x18002797d  cmp     ecx, 1Eh
0x180027980  jnz     short loc_1800279EB
0x180027982  lea     r9d, [rcx-13h]; vt
0x180027986  xor     r8d, r8d; wFlags
0x180027989  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x18002798e  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180027993  call    cs:__imp_VariantChangeType
0x18002799a  nop     dword ptr [rax+rax+00h]
0x18002799f  mov     ebx, eax
0x1800279a1  test    eax, eax
0x1800279a3  jns     short loc_1800279AA
0x1800279a5  jmp     loc_180027C1F
0x1800279aa  cmp     word ptr [rsp+0B8h+pvarg+8], 0FFFFh
0x1800279b0  jnz     loc_180027C16
0x1800279b6  mov     eax, 0FFFFh
0x1800279bb  add     [rdi+2], ax
0x1800279bf  imul    rcx, rsi, 25B0h
0x1800279c6  mov     rax, [rdi+20h]
0x1800279ca  movups  xmm0, xmmword ptr cs:DBCOL_SPECIALCOL.Data1
0x1800279d1  movdqu  xmmword ptr [rcx+rax+860h], xmm0
0x1800279da  mov     rax, [rdi+20h]
0x1800279de  mov     [rcx+rax+870h], r12d
0x1800279e6  jmp     loc_180027C16
0x1800279eb  cmp     ecx, 19h
0x1800279ee  jnz     short loc_180027A41
0x1800279f0  lea     r9d, [rcx-0Eh]; vt
0x1800279f4  xor     r8d, r8d; wFlags
0x1800279f7  lea     rdx, [rsp+0B8h+pvarSrc+8]; pvarSrc
0x1800279fc  lea     rcx, [rsp+0B8h+pvarg]; pvargDest
0x180027a01  call    cs:__imp_VariantChangeType
0x180027a08  nop     dword ptr [rax+rax+00h]
0x180027a0d  mov     ebx, eax
0x180027a0f  test    eax, eax
0x180027a11  jns     short loc_180027A18
0x180027a13  jmp     loc_180027C1F
0x180027a18  imul    rdx, rsi, 25B0h
0x180027a1f  mov     rcx, [rdi+20h]
0x180027a23  movzx   eax, word ptr [rsp+0B8h+pvarg+8]
0x180027a28  mov     [rdx+rcx+2538h], ax
0x180027a30  mov     rax, [rdi+20h]
0x180027a34  mov     [rdx+rax+253Ch], r12d
0x180027a3c  jmp     loc_180027C16
0x180027a41  cmp     ecx, 1Fh
0x180027a44  jnz     loc_180027C16
0x180027a4a  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; pbstr
0x180027a4f  call    cs:__imp_SysStringLen
0x180027a56  nop     dword ptr [rax+rax+00h]
0x180027a5b  mov     r15d, eax
0x180027a5e  test    eax, eax
0x180027a60  jz      loc_180027C16
0x180027a66  mov     dword ptr [rsp+0B8h+arg_8], r12d
0x180027a6e  mov     ecx, eax
0x180027a70  shr     ecx, 1; unsigned int
0x180027a72  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180027a77  mov     r14, rax
0x180027a7a  test    rax, rax
0x180027a7d  jnz     short loc_180027A89
0x180027a7f  mov     ebx, 8007000Eh
0x180027a84  jmp     loc_180027C1F
0x180027a89  lea     r9, [rsp+0B8h+arg_8]; int *
0x180027a91  mov     r8d, r15d; unsigned int
0x180027a94  mov     rdx, r14; unsigned __int8 *
0x180027a97  mov     rcx, qword ptr [rsp+0B8h+pvarSrc+10h]; unsigned __int16 *
0x180027a9c  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x180027aa1  mov     r15d, eax
0x180027aa4  test    eax, eax
0x180027aa6  jns     short loc_180027AB8
0x180027aa8  mov     rcx, r14; void *
0x180027aab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027ab0  mov     ebx, r15d
0x180027ab3  jmp     loc_180027C1F
0x180027ab8  mov     r9d, dword ptr [rsp+0B8h+arg_8]; unsigned int
0x180027ac0  mov     r8, r14; unsigned __int8 *
0x180027ac3  movzx   edx, si; unsigned __int16
0x180027ac6  mov     rcx, rdi; this
0x180027ac9  call    ?mdSetCalculationInfo@CMetaData@@QEAAXGPEAEK@Z; CMetaData::mdSetCalculationInfo(ushort,uchar *,ulong)
0x180027ace  jmp     loc_180027C16
0x180027ad3  mov     [rsp+0B8h+arg_8], r12
0x180027adb  imul    r14, rsi, 25B0h
0x180027ae2  mov     rax, [rdi+20h]
0x180027ae6  cmp     dword ptr [r14+rax+420h], 3
0x180027aef  jz      short loc_180027AFA
0x180027af1  cmp     ecx, 13h
  ... truncated ...
```
