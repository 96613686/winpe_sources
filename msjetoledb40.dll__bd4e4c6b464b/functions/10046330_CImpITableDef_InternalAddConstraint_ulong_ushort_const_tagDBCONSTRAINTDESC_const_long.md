# CImpITableDef::InternalAddConstraint(ulong &,ushort const *,tagDBCONSTRAINTDESC const *,long &)

- ea: `0x10046330`
- end: `0x100467a6`
- name: `?InternalAddConstraint@CImpITableDef@@QAEJAAKPBGPBUtagDBCONSTRAINTDESC@@AAJ@Z`
- size: `1142`
- prototype: `int __thiscall(CImpITableDef *__hidden this, unsigned int *, const unsigned __int16 *, const struct tagDBCONSTRAINTDESC *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x10044880`
- `0x10044ee0`

## callees

- `0x10016f20`
- `0x1001e800`
- `0x1001ea50`
- `0x100461f0`
- `0x10046330`
- `0x1004cea1`
- `0x1004d420`

## import_xrefs

- `msvcrt!rand` at `0x100463c3`
- `msvcrt!rand` at `0x100463c3`
- `msjet40!__imp__JetSetTableProperty@32` at `0x10046755`
- `msjet40!__imp__JetSetTableProperty@32` at `0x10046755`
- `msjet40!__imp__JetCreateRelationship@44` at `0x10046662`
- `msjet40!__imp__JetCreateRelationship@44` at `0x10046662`

## pseudocode

```c
int __thiscall CImpITableDef::InternalAddConstraint(
        CImpITableDef *this,
        unsigned int *a2,
        const unsigned __int16 *a3,
        const struct tagDBCONSTRAINTDESC *a4,
        int *a5)
{
  int v5; // ebx
  DBID *pConstraintID; // eax
  unsigned int v7; // esi
  CImpITableDef *ConstraintType; // ecx
  DBORDINAL *p_cForeignKeyColumns; // eax
  int Index; // esi
  DBID *pReferencedTableID; // edx
  void *v12; // ebx
  unsigned __int16 *v13; // edi
  DBUPDELRULE UpdateRule; // eax
  DBUPDELRULE DeleteRule; // eax
  DBUPDELRULE v16; // eax
  CImpITableDef *v17; // ecx
  CImpITableDef *v18; // esi
  int Relationship; // eax
  int *v20; // ecx
  OLECHAR *pwszConstraintText; // edx
  OLECHAR *v22; // ecx
  int v24; // eax
  unsigned int v26; // [esp-14h] [ebp-2D4h]
  unsigned __int16 *v27; // [esp-10h] [ebp-2D0h]
  int v28; // [esp-4h] [ebp-2C4h]
  unsigned int *v29; // [esp+0h] [ebp-2C0h]
  int *v30; // [esp+4h] [ebp-2BCh]
  _BYTE v31[4]; // [esp+Ch] [ebp-2B4h] BYREF
  unsigned int v32; // [esp+10h] [ebp-2B0h] BYREF
  unsigned int v33; // [esp+14h] [ebp-2ACh]
  unsigned int *v34; // [esp+18h] [ebp-2A8h]
  unsigned int v35; // [esp+1Ch] [ebp-2A4h] BYREF
  unsigned int v36; // [esp+20h] [ebp-2A0h]
  unsigned int ulPropid; // [esp+24h] [ebp-29Ch]
  CImpITableDef *v38; // [esp+28h] [ebp-298h]
  unsigned int v39; // [esp+2Ch] [ebp-294h]
  void *Block; // [esp+30h] [ebp-290h] BYREF
  unsigned __int16 *v41; // [esp+34h] [ebp-28Ch] BYREF
  unsigned __int16 v42[256]; // [esp+38h] [ebp-288h] BYREF
  _WORD v43[66]; // [esp+238h] [ebp-88h] BYREF

  v39 = (unsigned int)a2;
  v33 = (unsigned int)a3;
  v5 = 0;
  v36 = (unsigned int)a5;
  ulPropid = (unsigned int)v43;
  v43[0] = 0;
  v38 = this;
  pConstraintID = a4->pConstraintID;
  Block = 0;
  v35 = 0;
  v41 = 0;
  v32 = 0;
  if ( pConstraintID )
  {
    if ( pConstraintID->eKind != 2 )
      return -2147217781;
    ulPropid = pConstraintID->uName.ulPropid;
    if ( !ulPropid )
      return -2147217781;
  }
  else
  {
    v7 = 1;
    v43[0] = 90;
    do
      v43[v7++] = _rand() % 10 + 48;
    while ( v7 < 0x3E );
    v43[62] = 0;
    v5 = 0;
  }
  ConstraintType = (CImpITableDef *)a4->ConstraintType;
  p_cForeignKeyColumns = &a4->cForeignKeyColumns;
  v34 = &a4->cForeignKeyColumns;
  if ( ConstraintType == (CImpITableDef *)1 )
    goto LABEL_80;
  if ( *p_cForeignKeyColumns )
    return -2147217800;
  if ( ConstraintType != (CImpITableDef *)3 )
  {
LABEL_80:
    if ( a4->pwszConstraintText )
      return -2147217800;
  }
  else
  {
    if ( !a4->pwszConstraintText )
      return -2147217800;
    p_cForeignKeyColumns = &a4->cForeignKeyColumns;
  }
  pReferencedTableID = a4->pReferencedTableID;
  if ( pReferencedTableID )
  {
    if ( ConstraintType != (CImpITableDef *)1 || !*p_cForeignKeyColumns )
      return -2147217800;
    goto LABEL_22;
  }
  if ( a4->cForeignKeyColumns || ConstraintType == (CImpITableDef *)1 )
    return -2147217800;
  if ( !ConstraintType || (unsigned int)ConstraintType - 1 < 2 )
  {
LABEL_22:
    if ( !a4->cColumns )
      return -2147217800;
  }
  if ( a4->Deferrability )
    return -2147217799;
  switch ( (unsigned int)ConstraintType )
  {
    case 0u:
    case 2u:
      Index = CImpITableDef::BuildColumnList(
                ConstraintType,
                a4->cColumns,
                a4->rgColumnList,
                1,
                (unsigned __int16 **)&Block,
                &v35);
      if ( Index < 0 )
        goto LABEL_62;
      v12 = Block;
      Index = CJOLT::JOLTJetCreateIndex(
                *(_DWORD *)v39,
                *(_DWORD *)(*((_DWORD *)v38 + 2) + 16),
                ulPropid,
                (a4->ConstraintType != 0) + 1,
                (const unsigned __int16 *)Block,
                v35,
                *(const unsigned __int16 **)(*((_DWORD *)v38 + 2) + 16),
                (int *)v36,
                (unsigned int)v29,
                v30);
      if ( Index < 0 )
      {
        v13 = v41;
        if ( *(_DWORD *)v36 == -1402 )
        {
          Index = -2147217767;
          goto LABEL_63;
        }
        if ( *(_DWORD *)v36 != -1002 )
          goto LABEL_63;
        goto LABEL_30;
      }
      operator delete(v12);
      return Index;
    case 1u:
      if ( a4->MatchType )
        return -2147217792;
      UpdateRule = a4->UpdateRule;
      if ( !UpdateRule )
        goto LABEL_39;
      if ( UpdateRule != 1 )
        return -2147217782;
      v5 = 256;
LABEL_39:
      DeleteRule = a4->DeleteRule;
      if ( !DeleteRule )
        goto LABEL_44;
      v16 = DeleteRule - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
          return -2147217782;
        v5 |= 0x2000u;
      }
      else
      {
        v5 |= 0x1000u;
      }
LABEL_44:
      if ( !pReferencedTableID || pReferencedTableID->eKind != 2 || !pReferencedTableID->uName.ulPropid )
        return -2147217865;
      Index = CImpITableDef::BuildColumnList(
                ConstraintType,
                a4->cColumns,
                a4->rgColumnList,
                0,
                (unsigned __int16 **)&Block,
                &v35);
      if ( Index < 0
        || (Index = CImpITableDef::BuildColumnList(v17, *v34, a4->rgForeignKeyColumnList, 0, &v41, &v32), Index < 0)
        || (Index = CDBSession::CloseTableid(*((CDBSession **)v38 + 2), *(_DWORD *)v39), Index < 0) )
      {
LABEL_62:
        v13 = v41;
        v12 = Block;
      }
      else
      {
        v18 = v38;
        v28 = v5;
        v12 = Block;
        *(_DWORD *)v39 = -1;
        v13 = v41;
        Relationship = JetCreateRelationship(
                         *(_DWORD *)(*((_DWORD *)v18 + 2) + 16),
                         *(_DWORD *)(*((_DWORD *)v18 + 2) + 20),
                         ulPropid,
                         v33,
                         v41,
                         a4->pReferencedTableID->uName.ulPropid,
                         v12,
                         v42,
                         256,
                         v31,
                         v28);
        v20 = (int *)v36;
        *(_DWORD *)v36 = Relationship;
        if ( Relationship <= -1305 )
        {
          switch ( Relationship )
          {
            case -1305:
              Index = -2147217860;
              goto LABEL_63;
            case -1907:
            case -1809:
              Index = -2147217911;
              goto LABEL_63;
            case -1507:
              Index = -2147217903;
              goto LABEL_63;
          }
          goto LABEL_60;
        }
        if ( Relationship == -1002 )
        {
LABEL_30:
          Index = -2147217781;
          goto LABEL_63;
        }
        if ( Relationship )
        {
LABEL_60:
          Index = -2147467259;
          goto LABEL_63;
        }
        Index = CJOLT::JOLTJetOpenTable(
                  *(_DWORD *)(*((_DWORD *)v18 + 2) + 20),
                  *(_DWORD *)(*((_DWORD *)v18 + 2) + 16),
                  v33,
                  v26,
                  v27,
                  (const void *)2,
                  (_DWORD *)v39,
                  v20,
                  v29,
                  v30);
      }
LABEL_63:
      if ( v12 )
        operator delete(v12);
      if ( v13 )
        operator delete(v13);
      return Index;
    case 3u:
      pwszConstraintText = a4->pwszConstraintText;
      v22 = pwszConstraintText + 1;
      while ( *pwszConstraintText++ )
        ;
      v24 = JetSetTableProperty(
              *(_DWORD *)(*((_DWORD *)v38 + 2) + 16),
              *(_DWORD *)v39,
              0,
              ulPropid,
              a4->pwszConstraintText,
              2 * (pwszConstraintText - v22),
              12,
              36);
      *(_DWORD *)v36 = v24;
      if ( v24 == -1809 )
        return -2147217911;
      if ( v24 == -1002 )
        return -2147217781;
      Index = 0;
      if ( v24 )
        return -2147467259;
      return Index;
    default:
      return -2147217801;
  }
}

```

## disassembly

```asm
0x10046330  mov     edi, edi
0x10046332  push    ebp
0x10046333  mov     ebp, esp
0x10046335  sub     esp, 2B4h
0x1004633b  mov     eax, ___security_cookie
0x10046340  xor     eax, ebp
0x10046342  mov     [ebp+var_4], eax
0x10046345  mov     eax, [ebp+arg_0]
0x10046348  mov     [ebp+var_294], eax
0x1004634e  mov     eax, [ebp+arg_4]
0x10046351  push    ebx
0x10046352  mov     [ebp+var_2AC], eax
0x10046358  xor     ebx, ebx
0x1004635a  mov     eax, [ebp+arg_C]
0x1004635d  mov     [ebp+var_2A0], eax
0x10046363  lea     eax, [ebp+var_88]
0x10046369  push    esi; int *
0x1004636a  push    edi; unsigned int *
0x1004636b  mov     edi, [ebp+arg_8]
0x1004636e  mov     [ebp+var_29C], eax
0x10046374  xor     eax, eax
0x10046376  mov     [ebp+var_88], ax
0x1004637d  mov     [ebp+var_298], ecx
0x10046383  mov     eax, [edi]
0x10046385  mov     [ebp+Block], 0
0x1004638f  mov     [ebp+var_2A4], 0
0x10046399  mov     [ebp+var_28C], 0
0x100463a3  mov     [ebp+var_2B0], 0
0x100463ad  test    eax, eax
0x100463af  jnz     short loc_100463E7
0x100463b1  mov     eax, 5Ah ; 'Z'
0x100463b6  lea     esi, [ebx+1]
0x100463b9  mov     [ebp+var_88], ax
0x100463c0  lea     ebx, [eax-50h]
0x100463c3  call    ds:__imp__rand
0x100463c9  cdq
0x100463ca  idiv    ebx
0x100463cc  add     edx, 30h ; '0'
0x100463cf  mov     [ebp+esi*2+var_88], dx
0x100463d7  inc     esi
0x100463d8  cmp     esi, 3Eh ; '>'
0x100463db  jb      short loc_100463C3
0x100463dd  xor     eax, eax
0x100463df  mov     [ebp+var_C], ax
0x100463e3  xor     ebx, ebx
0x100463e5  jmp     short loc_10046402
0x100463e7  cmp     dword ptr [eax+10h], 2
0x100463eb  jnz     loc_1004678C
0x100463f1  mov     eax, [eax+14h]
0x100463f4  mov     [ebp+var_29C], eax
0x100463fa  test    eax, eax
0x100463fc  jz      loc_1004678C
0x10046402  mov     ecx, [edi+4]; this
0x10046405  lea     eax, [edi+14h]
0x10046408  mov     [ebp+var_2A8], eax
0x1004640e  cmp     ecx, 1
0x10046411  jz      short loc_10046432
0x10046413  cmp     dword ptr [eax], 0
0x10046416  jz      short loc_10046422
0x10046418  mov     esi, 80040E78h
0x1004641d  jmp     loc_10046791
0x10046422  cmp     ecx, 3
0x10046425  jnz     short loc_10046432
0x10046427  cmp     dword ptr [edi+1Ch], 0
0x1004642b  jz      short loc_10046418
0x1004642d  lea     eax, [edi+14h]
0x10046430  jmp     short loc_10046438
0x10046432  cmp     dword ptr [edi+1Ch], 0
0x10046436  jnz     short loc_10046418
0x10046438  mov     edx, [edi+10h]
0x1004643b  test    edx, edx
0x1004643d  jnz     short loc_1004645B
0x1004643f  cmp     [edi+14h], edx
0x10046442  jnz     short loc_10046418
0x10046444  cmp     ecx, 1
0x10046447  jz      short loc_10046418
0x10046449  mov     eax, ecx
0x1004644b  sub     eax, edx
0x1004644d  jz      short loc_10046465
0x1004644f  sub     eax, 1
0x10046452  jz      short loc_10046465
0x10046454  sub     eax, 1
0x10046457  jz      short loc_10046465
0x10046459  jmp     short loc_1004646B
0x1004645b  cmp     ecx, 1
0x1004645e  jnz     short loc_10046418
0x10046460  cmp     dword ptr [eax], 0
0x10046463  jz      short loc_10046418
0x10046465  cmp     dword ptr [edi+8], 0
0x10046469  jz      short loc_10046418
0x1004646b  cmp     dword ptr [edi+2Ch], 0
0x1004646f  jz      short loc_1004647B
0x10046471  mov     esi, 80040E79h
0x10046476  jmp     loc_10046791
0x1004647b  cmp     ecx, 3; switch 4 cases
0x1004647e  ja      def_10046484; jumptable 10046484 default case
0x10046484  jmp     ds:jpt_10046484[ecx*4]; switch jump
0x1004648b  lea     eax, [ebp+var_2A4]; jumptable 10046484 cases 0,2
0x10046491  push    eax; unsigned int *
0x10046492  lea     eax, [ebp+Block]
0x10046498  push    eax; unsigned __int16 **
0x10046499  push    1; int
0x1004649b  push    dword ptr [edi+0Ch]; struct tagDBID *
0x1004649e  push    dword ptr [edi+8]; unsigned int
0x100464a1  call    ?BuildColumnList@CImpITableDef@@QAEJKQAUtagDBID@@HAAPAGAAK@Z; CImpITableDef::BuildColumnList(ulong,tagDBID * const,int,ushort * &,ulong &)
0x100464a6  mov     esi, eax
0x100464a8  test    esi, esi
0x100464aa  js      loc_100466DE
0x100464b0  mov     eax, [ebp+var_298]
0x100464b6  mov     edx, [ebp+var_2A0]
0x100464bc  mov     ebx, [ebp+Block]
0x100464c2  push    edx; unsigned int
0x100464c3  mov     eax, [eax+8]
0x100464c6  mov     edx, [ebp+var_294]
0x100464cc  mov     ecx, [eax+10h]
0x100464cf  xor     eax, eax
0x100464d1  cmp     [edi+4], eax
0x100464d4  mov     edx, [edx]
0x100464d6  push    ecx; unsigned __int16 *
0x100464d7  push    [ebp+var_2A4]; unsigned int
0x100464dd  setnz   al
0x100464e0  push    ebx; unsigned __int16 *
0x100464e1  inc     eax
0x100464e2  push    eax; unsigned int
0x100464e3  push    [ebp+var_29C]; unsigned int
0x100464e9  call    ?JOLTJetCreateIndex@CJOLT@@SGJKKPBGK0KKAAJ@Z; CJOLT::JOLTJetCreateIndex(ulong,ulong,ushort const *,ulong,ushort const *,ulong,ulong,long &)
0x100464ee  mov     esi, eax
0x100464f0  test    esi, esi
0x100464f2  jns     short loc_10046528
0x100464f4  mov     eax, [ebp+var_2A0]
0x100464fa  mov     edi, [ebp+var_28C]
0x10046500  mov     eax, [eax]
0x10046502  cmp     eax, 0FFFFFA86h
0x10046507  jz      short loc_1004651E
0x10046509  cmp     eax, 0FFFFFC16h
0x1004650e  jnz     loc_100466EA
0x10046514  mov     esi, 80040E8Bh
0x10046519  jmp     loc_100466EA
0x1004651e  mov     esi, 80040E99h
0x10046523  jmp     loc_100466EA
0x10046528  push    ebx; Block
0x10046529  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004652e  add     esp, 4
0x10046531  jmp     loc_10046791
0x10046536  mov     eax, [edi+28h]; jumptable 10046484 case 1
0x10046539  sub     eax, 0
0x1004653c  jz      short loc_1004654B
0x1004653e  sub     eax, 1
0x10046541  mov     esi, 80040E80h
0x10046546  jmp     loc_10046791
0x1004654b  mov     eax, [edi+20h]
0x1004654e  sub     eax, 0
0x10046551  jz      short loc_10046567
0x10046553  sub     eax, 1
0x10046556  jz      short loc_10046562
0x10046558  mov     esi, 80040E8Ah
0x1004655d  jmp     loc_10046791
0x10046562  mov     ebx, 100h
0x10046567  mov     eax, [edi+24h]
0x1004656a  sub     eax, 0
0x1004656d  jz      short loc_10046587
0x1004656f  sub     eax, 1
0x10046572  jz      short loc_10046581
0x10046574  sub     eax, 1
0x10046577  jnz     short loc_10046558
0x10046579  or      ebx, 2000h
0x1004657f  jmp     short loc_10046587
0x10046581  or      ebx, 1000h
0x10046587  test    edx, edx
0x10046589  jz      loc_1004670D
0x1004658f  cmp     dword ptr [edx+10h], 2
0x10046593  jnz     loc_1004670D
0x10046599  cmp     dword ptr [edx+14h], 0
0x1004659d  jz      loc_1004670D
0x100465a3  lea     eax, [ebp+var_2A4]
0x100465a9  push    eax; unsigned int *
0x100465aa  lea     eax, [ebp+Block]
0x100465b0  push    eax; unsigned __int16 **
0x100465b1  push    0; int
0x100465b3  push    dword ptr [edi+0Ch]; struct tagDBID *
0x100465b6  push    dword ptr [edi+8]; unsigned int
0x100465b9  call    ?BuildColumnList@CImpITableDef@@QAEJKQAUtagDBID@@HAAPAGAAK@Z; CImpITableDef::BuildColumnList(ulong,tagDBID * const,int,ushort * &,ulong &)
0x100465be  mov     esi, eax
0x100465c0  test    esi, esi
0x100465c2  js      loc_100466DE
0x100465c8  lea     eax, [ebp+var_2B0]
0x100465ce  push    eax; unsigned int *
0x100465cf  lea     eax, [ebp+var_28C]
0x100465d5  push    eax; unsigned __int16 **
0x100465d6  mov     eax, [ebp+var_2A8]
0x100465dc  push    0; int
0x100465de  push    dword ptr [edi+18h]; struct tagDBID *
0x100465e1  push    dword ptr [eax]; unsigned int
0x100465e3  call    ?BuildColumnList@CImpITableDef@@QAEJKQAUtagDBID@@HAAPAGAAK@Z; CImpITableDef::BuildColumnList(ulong,tagDBID * const,int,ushort * &,ulong &)
0x100465e8  mov     esi, eax
0x100465ea  test    esi, esi
0x100465ec  js      loc_100466DE
0x100465f2  mov     edx, [ebp+var_294]
0x100465f8  mov     eax, [ebp+var_298]
0x100465fe  push    dword ptr [edx]; tableid
0x10046600  mov     ecx, [eax+8]; this
0x10046603  call    ?CloseTableid@CDBSession@@QAEJK@Z; CDBSession::CloseTableid(ulong)
0x10046608  mov     esi, eax
0x1004660a  test    esi, esi
0x1004660c  js      loc_100466DE
0x10046612  mov     eax, [ebp+var_294]
0x10046618  lea     edx, [ebp+var_2B4]
0x1004661e  mov     esi, [ebp+var_298]
0x10046624  push    ebx
0x10046625  mov     ebx, [ebp+Block]
0x1004662b  push    edx
0x1004662c  push    100h
0x10046631  mov     dword ptr [eax], 0FFFFFFFFh
0x10046637  lea     edx, [ebp+var_288]
0x1004663d  mov     eax, [edi+10h]
0x10046640  mov     edi, [ebp+var_28C]
0x10046646  push    edx; unsigned __int16 *
0x10046647  push    ebx; unsigned int
0x10046648  mov     ecx, [eax+14h]
0x1004664b  mov     eax, [esi+8]
0x1004664e  push    ecx
0x1004664f  push    edi
0x10046650  push    [ebp+var_2AC]
0x10046656  push    [ebp+var_29C]
0x1004665c  push    dword ptr [eax+14h]
0x1004665f  push    dword ptr [eax+10h]
0x10046662  call    ds:__imp__JetCreateRelationship@44; JetCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)
0x10046668  mov     ecx, [ebp+var_2A0]
0x1004666e  mov     [ecx], eax
0x10046670  cmp     eax, 0FFFFFAE7h
0x10046675  jg      short loc_100466A3
0x10046677  jz      short loc_1004669C
0x10046679  cmp     eax, 0FFFFF88Dh
0x1004667e  jz      short loc_10046695
0x10046680  cmp     eax, 0FFFFF8EFh
0x10046685  jz      short loc_10046695
0x10046687  cmp     eax, 0FFFFFA1Dh
0x1004668c  jnz     short loc_100466B2
0x1004668e  mov     esi, 80040E11h
0x10046693  jmp     short loc_100466EA
0x10046695  mov     esi, 80040E09h
0x1004669a  jmp     short loc_100466EA
0x1004669c  mov     esi, 80040E3Ch
0x100466a1  jmp     short loc_100466EA
0x100466a3  cmp     eax, 0FFFFFC16h
0x100466a8  jz      loc_10046514
0x100466ae  test    eax, eax
0x100466b0  jz      short loc_100466B9
0x100466b2  mov     esi, 80004005h
0x100466b7  jmp     short loc_100466EA
0x100466b9  mov     edx, [ebp+var_294]
0x100466bf  mov     eax, [esi+8]
0x100466c2  push    ecx; unsigned int
0x100466c3  push    edx; unsigned int
0x100466c4  push    2; void *
0x100466c6  mov     edx, [eax+14h]
0x100466c9  sub     esp, 8
0x100466cc  mov     ecx, [eax+10h]
0x100466cf  push    [ebp+var_2AC]; unsigned int
0x100466d5  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x100466da  mov     esi, eax
0x100466dc  jmp     short loc_100466EA
0x100466de  mov     edi, [ebp+var_28C]
0x100466e4  mov     ebx, [ebp+Block]
0x100466ea  test    ebx, ebx
0x100466ec  jz      short loc_100466F7
0x100466ee  push    ebx; Block
0x100466ef  call    ??3@YAXPAX@Z; operator delete(void *)
0x100466f4  add     esp, 4
0x100466f7  test    edi, edi
0x100466f9  jz      loc_10046791
0x100466ff  push    edi; Block
0x10046700  call    ??3@YAXPAX@Z; operator delete(void *)
0x10046705  add     esp, 4
0x10046708  jmp     loc_10046791
0x1004670d  mov     esi, 80040E37h
0x10046712  jmp     short loc_10046791
0x10046714  mov     esi, [edi+1Ch]; jumptable 10046484 case 3
0x10046717  mov     edx, esi
0x10046719  lea     ecx, [edx+2]
0x1004671c  nop     dword ptr [eax+00h]
0x10046720  mov     ax, [edx]
0x10046723  add     edx, 2
0x10046726  test    ax, ax
0x10046729  jnz     short loc_10046720
0x1004672b  mov     eax, [ebp+var_298]
0x10046731  sub     edx, ecx
0x10046733  push    24h ; '$'
0x10046735  sar     edx, 1
0x10046737  push    0Ch
0x10046739  mov     eax, [eax+8]
0x1004673c  mov     ecx, [eax+10h]
0x1004673f  lea     eax, [edx+edx]
0x10046742  push    eax
0x10046743  mov     eax, [ebp+var_294]
0x10046749  push    esi
0x1004674a  push    [ebp+var_29C]
0x10046750  push    0
0x10046752  push    dword ptr [eax]
0x10046754  push    ecx
  ... truncated ...
```
