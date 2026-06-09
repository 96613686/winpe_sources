# CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)

- ea: `0x180024434`
- end: `0x1800248d0`
- name: `?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, struct CSymbol *, struct XMLCHAPTER *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800248d8`
- `0x1800287cc`

## callees

- `0x1800041b4`
- `0x180004338`
- `0x180005180`
- `0x180016584`
- `0x180024434`
- `0x1800266ac`
- `0x180026d04`
- `0x18002701c`
- `0x1800275e4`
- `0x180027c4c`
- `0x180029528`
- `0x180029dc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180024471`
- `OLEAUT32!__imp_SysStringLen` at `0x1800244d0`
- `OLEAUT32!__imp_SysStringLen` at `0x180024583`
- `OLEAUT32!__imp_SysStringLen` at `0x180024805`
- `OLEAUT32!__imp_SysStringLen` at `0x180024471`
- `OLEAUT32!__imp_SysStringLen` at `0x1800244d0`
- `OLEAUT32!__imp_SysStringLen` at `0x180024583`
- `OLEAUT32!__imp_SysStringLen` at `0x180024805`

## pseudocode

```c
__int64 __fastcall CXMLReader::BuildColumnDefinition(
        CXMLReader *this,
        struct CParseNode *a2,
        struct CSymbol *a3,
        struct XMLCHAPTER *a4)
{
  __int64 v4; // rsi
  BSTR *Value; // r12
  UINT v8; // eax
  unsigned __int16 *v9; // rdx
  __int64 v10; // rbx
  OLECHAR *v11; // rcx
  __int64 v12; // r13
  unsigned __int16 v13; // ax
  __int64 v14; // r8
  UINT v15; // eax
  unsigned int v16; // r12d
  unsigned __int16 v17; // cx
  struct XMLCHAPTER *v18; // rdx
  CXMLReader *v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // r14
  unsigned __int16 *v25; // rbp
  __int64 v26; // rbx
  UINT v27; // eax
  __int64 v28; // rcx
  unsigned __int16 *Name; // rcx
  __int16 v30; // r9
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // ecx
  BSTR *v36; // [rsp+40h] [rbp-48h]
  unsigned int i; // [rsp+40h] [rbp-48h]
  unsigned __int64 v38; // [rsp+A0h] [rbp+18h] BYREF
  struct XMLCHAPTER *v39; // [rsp+A8h] [rbp+20h]

  v39 = a4;
  v4 = *((_QWORD *)a3 + 1);
  Value = (BSTR *)CParseNode::GetValue(a2);
  v36 = Value;
  v8 = SysStringLen(*Value);
  v9 = *Value;
  v38 = 0;
  if ( (unsigned int)CCollectionList::LookUpByKey((CCollectionList *)(v4 + 552), v9, v8, &v38) )
  {
    v11 = *Value;
    LOWORD(v38) = *(_WORD *)(v4 + 608);
    v10 = (unsigned __int16)v38;
    v12 = (unsigned __int16)(v38 - 1);
    v13 = SysStringLen(v11);
    CMetaData::mdSetName((CMetaData *)(v4 + 304), v12, *Value, v13);
    v14 = 9648 * v12;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1092) = 64;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1096) = 0;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1080) = 3;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1088) = 3;
    *(_QWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1064) = 0xFFFFFFFFLL;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1072) = 0;
    *(_WORD *)(v14 + *(_QWORD *)(v4 + 336) + 9580) = 0;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 9584) = 0;
    *(_QWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1040) = v10;
    *(_DWORD *)(v14 + *(_QWORD *)(v4 + 336) + 1048) = 0;
    v15 = SysStringLen(*Value);
    v16 = CCollectionList::Append((CCollectionList *)(v4 + 552), *Value, v15, (unsigned int)v10);
    if ( (v16 & 0x80000000) != 0 )
      return v16;
    *(_DWORD *)(v4 + 608) = (unsigned __int16)v10 + 1;
    v17 = v10;
  }
  else
  {
    v17 = v38;
    v16 = 0;
    LOWORD(v12) = v38 - 1;
  }
  v18 = v39;
  if ( !v39 )
  {
    if ( !(unsigned __int8)CXMLReader::IsMatch(
                             this,
                             *((_QWORD *)a2 + 4),
                             *(unsigned int *)a2,
                             *((unsigned int *)a2 + 1),
                             &wszAttributeType,
                             13,
                             1)
      && !(unsigned __int8)CXMLReader::IsMatch(
                             this,
                             *((_QWORD *)a2 + 4),
                             *(unsigned int *)a2,
                             *((unsigned int *)a2 + 1),
                             &wszElementType,
                             11,
                             1) )
    {
      *((_BYTE *)this + 472) = 1;
      return v16;
    }
    v20 = *((_DWORD *)this + 108);
    LODWORD(v21) = *((_DWORD *)a2 + 11);
    for ( i = v20; ; v20 = i )
    {
      v21 = (unsigned int)(v21 + 1);
      if ( (unsigned int)v21 >= v20 )
      {
        CXMLReader::FixupType(v19, (struct CMetaData *)(v4 + 304), v12);
        v24 = 4LL * (unsigned __int16)v38;
        *(_DWORD *)(v24 + *(_QWORD *)(v4 + 184)) = CMetaData::mdGetSize((CMetaData *)(v4 + 304), v12);
        goto LABEL_27;
      }
      v22 = *(_QWORD *)(*((_QWORD *)this + 53) + 8 * v21);
      if ( *(struct CParseNode **)(v22 + 16) == a2 )
      {
        if ( *(_DWORD *)(v22 + 8) == 1 )
        {
          v23 = CXMLReader::ProcessColumnChild(this, (struct CParseNode *)v22, v12, (struct CMetaData *)(v4 + 304));
        }
        else
        {
          if ( *(_DWORD *)(v22 + 8) != 2 )
            continue;
          v23 = CXMLReader::ProcessColumnAttribute(this, (struct CParseNode *)v22, v12, (struct CMetaData *)(v4 + 304));
        }
        v16 = v23;
        if ( v23 < 0 )
          return v16;
      }
    }
  }
  v25 = *(unsigned __int16 **)(*(_QWORD *)v39 + 640LL);
  v24 = 4LL * v17;
  v26 = 9648LL * (unsigned __int16)v12;
  *(_WORD *)(v26 + *(_QWORD *)(v4 + 336) + 1052) = 136;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1056) = 0;
  *(_DWORD *)(v24 + *(_QWORD *)(v4 + 184)) = 8;
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1064) = 8;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1072) = 0;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1092) = 8208;
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 1096) = 0;
  *(_QWORD *)(*(_QWORD *)(v4 + 544) + 8LL * v17) = v18;
  if ( !*(_DWORD *)(*(_QWORD *)v18 + 616LL) )
  {
    v16 = Exit(-2147467259, 0x91u);
    if ( (v16 & 0x80000000) != 0 )
      return v16;
    v18 = v39;
  }
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9616) = *(unsigned int *)(*(_QWORD *)v18 + 616LL);
  *(_QWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9600) = *(_QWORD *)(*(_QWORD *)v18 + 624LL);
  *(_DWORD *)(v26 + *(_QWORD *)(v4 + 336) + 9608) = 0;
  *(_DWORD *)(*(_QWORD *)v18 + 616LL) = 0;
  *(_QWORD *)(*(_QWORD *)v18 + 624LL) = 0;
  if ( v25 )
  {
    v27 = SysStringLen(*v36);
    v28 = -1;
    do
      ++v28;
    while ( v25[v28] );
    if ( !(unsigned __int8)CXMLReader::IsMatch(this, *v36, v27, 0, v25, v28, 6) )
      CMetaData::mdSetName((CMetaData *)(v4 + 304), v12, v25, 0xFFFFu);
  }
LABEL_27:
  *(_DWORD *)(v24 + *(_QWORD *)(v4 + 176)) = 0;
  Name = CMetaData::mdGetName((CMetaData *)(v4 + 304), v12);
  v31 = -1;
  do
    ++v31;
  while ( Name[v31] != v30 );
  v32 = *(_DWORD *)(v4 + 216);
  *(_DWORD *)(v4 + 268) += v31 + 2;
  v33 = *(_QWORD *)(v4 + 160);
  v34 = (v32 + 7) & 0xFFFFFFF8;
  *(_DWORD *)(v4 + 216) = v34;
  *(_DWORD *)(v24 + v33) = v34;
  *(_DWORD *)(v4 + 216) += 16;
  return v16;
}

```

## disassembly

```asm
0x180024434  mov     [rsp+arg_0], rbx
0x180024439  mov     [rsp+arg_18], r9
0x18002443e  push    rbp
0x18002443f  push    rsi
0x180024440  push    rdi
0x180024441  push    r12
0x180024443  push    r13
0x180024445  push    r14
0x180024447  push    r15
0x180024449  sub     rsp, 50h
0x18002444d  mov     rsi, [r8+8]
0x180024451  mov     r15, rcx
0x180024454  mov     rcx, rdx; this
0x180024457  mov     r14, rdx
0x18002445a  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x18002445f  mov     r12, rax
0x180024462  mov     [rsp+88h+var_48], rax
0x180024467  lea     rdi, [rsi+130h]
0x18002446e  mov     rcx, [rax]; pbstr
0x180024471  call    cs:__imp_SysStringLen
0x180024478  nop     dword ptr [rax+rax+00h]
0x18002447d  mov     rdx, [r12]; unsigned __int16 *
0x180024481  lea     rcx, [rsi+228h]; this
0x180024488  mov     r8d, eax; unsigned int
0x18002448b  mov     [rsp+88h+arg_10], 0
0x180024497  lea     r9, [rsp+88h+arg_10]; unsigned __int64 *
0x18002449f  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800244a4  xor     r9d, r9d
0x1800244a7  lea     ebp, [r9+1]
0x1800244ab  test    eax, eax
0x1800244ad  jz      loc_1800245C3
0x1800244b3  movzx   ebx, word ptr [rsi+260h]
0x1800244ba  mov     rcx, [r12]; pbstr
0x1800244be  movzx   eax, bx
0x1800244c1  sub     ax, bp
0x1800244c4  mov     word ptr [rsp+88h+arg_10], bx
0x1800244cc  movzx   r13d, ax
0x1800244d0  call    cs:__imp_SysStringLen
0x1800244d7  nop     dword ptr [rax+rax+00h]
0x1800244dc  mov     r8, [r12]; unsigned __int16 *
0x1800244e0  movzx   edx, r13w; unsigned __int16
0x1800244e4  movzx   r9d, ax; unsigned __int16
0x1800244e8  mov     rcx, rdi; this
0x1800244eb  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x1800244f0  mov     rax, [rdi+20h]
0x1800244f4  lea     ecx, [rbp+2]
0x1800244f7  imul    r8, r13, 25B0h
0x1800244fe  xor     r9d, r9d
0x180024501  mov     dword ptr [r8+rax+444h], 40h ; '@'
0x18002450d  mov     rax, [rdi+20h]
0x180024511  mov     [r8+rax+448h], r9d
0x180024519  mov     rax, [rdi+20h]
0x18002451d  mov     [r8+rax+438h], ecx
0x180024525  mov     rax, [rdi+20h]
0x180024529  mov     [r8+rax+440h], ecx
0x180024531  mov     ecx, 0FFFFFFFFh
0x180024536  mov     rax, [rdi+20h]
0x18002453a  mov     [r8+rax+428h], rcx
0x180024542  mov     rax, [rdi+20h]
0x180024546  mov     [r8+rax+430h], r9d
0x18002454e  mov     rdx, [rdi+20h]
0x180024552  mov     [r8+rdx+256Ch], r9w
0x18002455b  mov     rax, [rdi+20h]
0x18002455f  mov     [r8+rax+2570h], r9d
0x180024567  mov     rax, [rdi+20h]
0x18002456b  mov     [r8+rax+410h], rbx
0x180024573  mov     rax, [rdi+20h]
0x180024577  mov     [r8+rax+418h], r9d
0x18002457f  mov     rcx, [r12]; pbstr
0x180024583  call    cs:__imp_SysStringLen
0x18002458a  nop     dword ptr [rax+rax+00h]
0x18002458f  mov     rdx, [r12]; unsigned __int16 *
0x180024593  lea     rcx, [rsi+228h]; this
0x18002459a  mov     r8d, eax; unsigned int
0x18002459d  mov     r9d, ebx; unsigned __int64
0x1800245a0  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x1800245a5  xor     r9d, r9d
0x1800245a8  mov     r12d, eax
0x1800245ab  test    eax, eax
0x1800245ad  js      loc_1800248B4
0x1800245b3  movzx   ecx, bx
0x1800245b6  add     ecx, ebp
0x1800245b8  mov     [rsi+260h], ecx
0x1800245be  movzx   ecx, bx
0x1800245c1  jmp     short loc_1800245DE
0x1800245c3  movzx   ecx, word ptr [rsp+88h+arg_10]
0x1800245cb  mov     r12d, r9d
0x1800245ce  movzx   r13d, cx
0x1800245d2  mov     word ptr [rsp+88h+arg_10], cx
0x1800245da  sub     r13w, bp
0x1800245de  mov     rdx, [rsp+88h+arg_18]
0x1800245e6  test    rdx, rdx
0x1800245e9  jnz     loc_1800246F3
0x1800245ef  mov     r9d, [r14+4]
0x1800245f3  lea     rax, ?wszAttributeType@@3PAGA; "AttributeType"
0x1800245fa  mov     r8d, [r14]
0x1800245fd  mov     rcx, r15
0x180024600  mov     rdx, [r14+20h]
0x180024604  mov     [rsp+88h+var_58], ebp
0x180024608  mov     [rsp+88h+var_60], 0Dh
0x180024610  mov     [rsp+88h+var_68], rax
0x180024615  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002461a  test    al, al
0x18002461c  jnz     short loc_180024659
0x18002461e  mov     r9d, [r14+4]
0x180024622  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x180024629  mov     r8d, [r14]
0x18002462c  mov     rcx, r15
0x18002462f  mov     rdx, [r14+20h]
0x180024633  mov     [rsp+88h+var_58], ebp
0x180024637  mov     [rsp+88h+var_60], 0Bh
0x18002463f  mov     [rsp+88h+var_68], rax
0x180024644  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024649  test    al, al
0x18002464b  jnz     short loc_180024659
0x18002464d  mov     [r15+1D8h], bpl
0x180024654  jmp     loc_1800248B4
0x180024659  mov     eax, [r15+1B0h]
0x180024660  mov     ebx, [r14+2Ch]
0x180024664  mov     dword ptr [rsp+88h+var_48], eax
0x180024668  add     ebx, ebp
0x18002466a  cmp     ebx, eax
0x18002466c  jnb     short loc_1800246BB
0x18002466e  mov     rax, [r15+1A8h]
0x180024675  mov     rdx, [rax+rbx*8]; struct CParseNode *
0x180024679  cmp     [rdx+10h], r14
0x18002467d  jnz     short loc_1800246B5
0x18002467f  cmp     [rdx+8], ebp
0x180024682  jnz     short loc_180024695
0x180024684  mov     r9, rdi; struct CMetaData *
0x180024687  movzx   r8d, r13w; unsigned __int16
0x18002468b  mov     rcx, r15; this
0x18002468e  call    ?ProcessColumnChild@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z; CXMLReader::ProcessColumnChild(CParseNode *,ushort,CMetaData *)
0x180024693  jmp     short loc_1800246AA
0x180024695  cmp     dword ptr [rdx+8], 2
0x180024699  jnz     short loc_1800246B5
0x18002469b  mov     r9, rdi; struct CMetaData *
0x18002469e  movzx   r8d, r13w; unsigned __int16
0x1800246a2  mov     rcx, r15; this
0x1800246a5  call    ?ProcessColumnAttribute@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z; CXMLReader::ProcessColumnAttribute(CParseNode *,ushort,CMetaData *)
0x1800246aa  mov     r12d, eax
0x1800246ad  test    eax, eax
0x1800246af  js      loc_1800248B4
0x1800246b5  mov     eax, dword ptr [rsp+88h+var_48]
0x1800246b9  jmp     short loc_180024668
0x1800246bb  movzx   r8d, r13w; unsigned __int16
0x1800246bf  mov     rdx, rdi; struct CMetaData *
0x1800246c2  call    ?FixupType@CXMLReader@@AEAAXPEAVCMetaData@@G@Z; CXMLReader::FixupType(CMetaData *,ushort)
0x1800246c7  movzx   eax, word ptr [rsp+88h+arg_10]
0x1800246cf  movzx   edx, r13w; unsigned __int16
0x1800246d3  mov     rcx, rdi; this
0x1800246d6  lea     r14, ds:0[rax*4]
0x1800246de  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x1800246e3  mov     rcx, [rsi+0B8h]
0x1800246ea  mov     [r14+rcx], eax
0x1800246ee  jmp     loc_18002485C
0x1800246f3  mov     rax, [rdx]
0x1800246f6  mov     r8d, 8
0x1800246fc  movzx   ecx, cx
0x1800246ff  mov     rbp, [rax+280h]
0x180024706  movzx   eax, r13w
0x18002470a  lea     r14, ds:0[rcx*4]
0x180024712  imul    rbx, rax, 25B0h
0x180024719  mov     rax, [rdi+20h]
0x18002471d  mov     word ptr [rbx+rax+41Ch], 88h
0x180024727  mov     rax, [rdi+20h]
0x18002472b  mov     [rbx+rax+420h], r9d
0x180024733  mov     rax, [rsi+0B8h]
0x18002473a  mov     [r14+rax], r8d
0x18002473e  mov     rax, [rdi+20h]
0x180024742  mov     [rbx+rax+428h], r8
0x18002474a  mov     rax, [rdi+20h]
0x18002474e  mov     [rbx+rax+430h], r9d
0x180024756  mov     rax, [rdi+20h]
0x18002475a  mov     dword ptr [rbx+rax+444h], 2010h
0x180024765  mov     rax, [rdi+20h]
0x180024769  mov     [rbx+rax+448h], r9d
0x180024771  mov     rax, [rsi+220h]
0x180024778  mov     [rax+rcx*8], rdx
0x18002477c  mov     rax, [rdx]
0x18002477f  cmp     [rax+268h], r9d
0x180024786  jnz     short loc_1800247AD
0x180024788  mov     edx, 91h; unsigned int
0x18002478d  mov     ecx, 80004005h; int
0x180024792  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180024797  xor     r9d, r9d
0x18002479a  mov     r12d, eax
0x18002479d  test    eax, eax
0x18002479f  js      loc_1800248B4
0x1800247a5  mov     rdx, [rsp+88h+arg_18]
0x1800247ad  mov     rax, [rdx]
0x1800247b0  mov     ecx, [rax+268h]
0x1800247b6  mov     rax, [rdi+20h]
0x1800247ba  mov     [rbx+rax+2590h], rcx
0x1800247c2  mov     rax, [rdx]
0x1800247c5  mov     rcx, [rdi+20h]
0x1800247c9  mov     rax, [rax+270h]
0x1800247d0  mov     [rbx+rcx+2580h], rax
0x1800247d8  mov     rax, [rdi+20h]
0x1800247dc  mov     [rbx+rax+2588h], r9d
0x1800247e4  mov     rax, [rdx]
0x1800247e7  mov     [rax+268h], r9d
0x1800247ee  mov     rax, [rdx]
0x1800247f1  mov     [rax+270h], r9
0x1800247f8  test    rbp, rbp
0x1800247fb  jz      short loc_18002485C
0x1800247fd  mov     rbx, [rsp+88h+var_48]
0x180024802  mov     rcx, [rbx]; pbstr
0x180024805  call    cs:__imp_SysStringLen
0x18002480c  nop     dword ptr [rax+rax+00h]
0x180024811  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024815  xor     edx, edx
0x180024817  inc     rcx
0x18002481a  cmp     [rbp+rcx*2+0], dx
0x18002481f  jnz     short loc_180024817
0x180024821  mov     rdx, [rbx]
0x180024824  xor     r9d, r9d
0x180024827  mov     [rsp+88h+var_58], 6
0x18002482f  mov     r8d, eax
0x180024832  mov     [rsp+88h+var_60], ecx
0x180024836  mov     rcx, r15
0x180024839  mov     [rsp+88h+var_68], rbp
0x18002483e  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024843  test    al, al
0x180024845  jnz     short loc_18002485C
0x180024847  mov     r9d, 0FFFFh; unsigned __int16
0x18002484d  mov     r8, rbp; unsigned __int16 *
0x180024850  movzx   edx, r13w; unsigned __int16
0x180024854  mov     rcx, rdi; this
0x180024857  call    ?mdSetName@CMetaData@@QEAAXGPEAGG@Z; CMetaData::mdSetName(ushort,ushort *,ushort)
0x18002485c  mov     rax, [rsi+0B0h]
0x180024863  xor     r9d, r9d
0x180024866  movzx   edx, r13w; unsigned __int16
0x18002486a  mov     rcx, rdi; this
0x18002486d  mov     [r14+rax], r9d
0x180024871  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x180024876  mov     rcx, rax
0x180024879  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002487d  inc     rax
0x180024880  cmp     [rcx+rax*2], r9w
0x180024885  jnz     short loc_18002487D
0x180024887  mov     ecx, [rsi+0D8h]
0x18002488d  add     eax, 2
0x180024890  add     [rsi+10Ch], eax
0x180024896  add     ecx, 7
0x180024899  mov     rax, [rsi+0A0h]
0x1800248a0  and     ecx, 0FFFFFFF8h
0x1800248a3  mov     [rsi+0D8h], ecx
0x1800248a9  mov     [r14+rax], ecx
0x1800248ad  add     dword ptr [rsi+0D8h], 10h
0x1800248b4  mov     rbx, [rsp+88h+arg_0]
0x1800248bc  mov     eax, r12d
0x1800248bf  add     rsp, 50h
0x1800248c3  pop     r15
0x1800248c5  pop     r14
0x1800248c7  pop     r13
0x1800248c9  pop     r12
0x1800248cb  pop     rdi
0x1800248cc  pop     rsi
0x1800248cd  pop     rbp
0x1800248ce  retn
```
