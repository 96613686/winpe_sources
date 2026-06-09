# CXMLReader::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180024eb0`
- end: `0x1800257e6`
- name: `?CreateNode@CXMLReader@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `2358`
- prototype: `__int64 __usercall@<rax>(CXMLReader *__hidden this@<rcx>, struct IXMLNodeSource *@<rdx>, void *@<r8>, unsigned __int16@<r9w>, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18001b008`
- `0x180024eb0`
- `0x180026c5c`
- `0x180026d20`
- `0x18002701c`
- `0x1800270cc`
- `0x180027d24`
- `0x180028a9c`
- `0x1800299d4`
- `0x180029dc0`
- `0x18002dca4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180024f16`
- `OLEAUT32!__imp_SysStringLen` at `0x180024f16`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::CreateNode(
        CXMLReader *this,
        struct IXMLNodeSource *a2,
        struct CParseNode *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct _XML_NODE_INFO *v6; // rsi
  int *v7; // r12
  int v8; // edi
  UINT v10; // eax
  unsigned int *v11; // r14
  unsigned __int16 **v12; // r15
  _DWORD *v13; // r13
  int v14; // ecx
  CXMLReader *v15; // rcx
  _QWORD *v16; // r13
  unsigned __int64 v17; // rcx
  CCollectionList *v18; // r13
  int v19; // edx
  struct CParseNode *Node; // r15
  char v21; // cl
  char v22; // dl
  __int64 i; // rax
  int v24; // r13d
  struct _XML_NODE_INFO *v25; // r14
  unsigned int v26; // r8d
  struct CParseNode *v27; // rdx
  const unsigned __int16 *v28; // r9
  unsigned int v29; // eax
  unsigned int v30; // ecx
  int v31; // r13d
  __int64 v32; // rax
  char IsMatch; // al
  int v34; // r14d
  __int64 v35; // rax
  char v36; // al
  int v37; // r14d
  unsigned int v38; // r8d
  const unsigned __int16 *v39; // rdx
  int v40; // r14d
  int v41; // r14d
  char v42; // [rsp+40h] [rbp-48h]
  char v43; // [rsp+41h] [rbp-47h]
  unsigned int v44; // [rsp+44h] [rbp-44h]
  int v45; // [rsp+48h] [rbp-40h]
  unsigned __int64 v46[2]; // [rsp+50h] [rbp-38h] BYREF

  v44 = 0;
  v6 = *a5;
  v7 = (int *)((char *)this + 480);
  v8 = 1;
  if ( *((_DWORD *)*a5 + 1) != 1 && *v7 != 5 )
    return 0;
  if ( *v7 == 4 )
  {
    v10 = SysStringLen(*((BSTR *)this + 18));
    v11 = (unsigned int *)((char *)v6 + 24);
    v12 = (unsigned __int16 **)((char *)v6 + 16);
    if ( (unsigned __int8)CXMLReader::IsMatch(
                            this,
                            *((_QWORD *)v6 + 2),
                            *((unsigned int *)v6 + 6),
                            0,
                            *((_QWORD *)this + 18),
                            v10,
                            6) )
    {
      *v7 = 5;
      return 0;
    }
    v13 = (_DWORD *)((char *)this + 480);
  }
  else
  {
    v13 = (_DWORD *)((char *)this + 480);
    v11 = (unsigned int *)((char *)v6 + 24);
    v12 = (unsigned __int16 **)((char *)v6 + 16);
  }
  v14 = *v7;
  if ( *v7 == 2 )
  {
    if ( (unsigned __int8)CXMLReader::IsMatch(
                            this,
                            *((_QWORD *)v6 + 2),
                            *((unsigned int *)v6 + 6),
                            *((unsigned int *)v6 + 7),
                            &wszSchema,
                            6,
                            1) )
    {
      if ( CXMLReader::IsRowsetSchema(v15, a5, a4) )
        *v13 = 3;
    }
    else if ( (unsigned __int8)CXMLReader::IsMatch(
                                 this,
                                 *((_QWORD *)v6 + 2),
                                 *((unsigned int *)v6 + 6),
                                 *((unsigned int *)v6 + 7),
                                 L"xml",
                                 3,
                                 6) )
    {
      return (unsigned int)CXMLReader::ProcessNamespaceDcl(this, a5, a4);
    }
    return v44;
  }
  if ( ((v14 - 3) & 0xFFFFFFFD) != 0 )
    return 0;
  if ( v14 != 5 || *((_QWORD *)this + 57) )
  {
LABEL_34:
    if ( *v7 == 3
      && ((unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszExtends, 7, 1)
       || !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszElementType, 11, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszAttributeType, 13, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszDataType, 8, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszElement, 7, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszAttribute, 9, 1)) )
    {
      return 0;
    }
    Node = 0;
    v21 = 0;
    v42 = 0;
    v22 = 0;
    v43 = 0;
    for ( i = 0; ; i = (unsigned int)(v45 + 1) )
    {
      v45 = i;
      v24 = a4;
      LODWORD(v46[0]) = a4;
      if ( (unsigned int)i >= a4 )
        return 0;
      v25 = a5[i];
      if ( (unsigned int)(*((_DWORD *)v25 + 1) - 1) <= 1 )
      {
        Node = CNodePool::GetNode(*((CNodePool **)this + 51), (struct CNodePool **)this + 51);
        if ( !Node )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049CC0[0] )
            bidTraceW(off_180049208[0], 2775040, off_180049CC0[0], 2147942414LL, 2710);
          ThrowHR(-2147024882);
        }
        if ( *v7 != 5 || *((_BYTE *)this + 400) )
        {
          v30 = *((_DWORD *)v25 + 7);
          v29 = *((_DWORD *)v25 + 6);
          v28 = (const unsigned __int16 *)*((_QWORD *)v25 + 2);
          v26 = *((_DWORD *)v25 + 1);
          if ( v45 )
            v27 = (struct CParseNode *)*((_QWORD *)v6 + 4);
          else
            v27 = a3;
        }
        else
        {
          v26 = *((_DWORD *)v25 + 1);
          if ( v45 )
            v27 = (struct CParseNode *)*((_QWORD *)v6 + 4);
          else
            v27 = a3;
          v28 = 0;
          v29 = 0;
          v30 = 0;
        }
        CParseNode::Init(Node, v27, v26, v28, v29, v30);
        v31 = CCollectionArray::Insert(
                (CXMLReader *)((char *)this + 416),
                *((_DWORD *)this + 110),
                (unsigned __int64)Node);
        if ( v31 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049CB8[0] )
            bidTraceW(off_180049208[0], 2784256, off_180049CB8[0], (unsigned int)v31, 2719);
          ThrowHR(v31);
        }
        *((_DWORD *)Node + 11) = (*((_DWORD *)this + 110))++;
        v24 = v46[0];
        v21 = v42;
        v22 = v43;
      }
      switch ( *((_DWORD *)v25 + 1) )
      {
        case 1:
          *((_QWORD *)v6 + 4) = Node;
          if ( *v7 == 3 )
          {
            if ( a3 )
              ++*((_DWORD *)a3 + 6);
            if ( (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszAttributeType,
                                    13,
                                    1) )
              *((_BYTE *)Node + 40) |= 1u;
          }
          if ( *v7 == 5 && !*((_BYTE *)this + 400) )
          {
            *((_DWORD *)Node + 6) = v24;
            *((_QWORD *)Node + 2) = a5;
            return 0;
          }
          v22 = 0;
          v43 = 0;
          v21 = 0;
          v42 = 0;
          break;
        case 2:
          if ( *v7 == 3 )
          {
            v43 = 0;
            if ( (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszName,
                                    4,
                                    1)
              || (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszType,
                                    4,
                                    1) )
            {
              v21 = 1;
              v42 = 1;
              v22 = 0;
            }
            else
            {
              v42 = 0;
              v32 = -1;
              do
                ++v32;
              while ( *((_WORD *)&wszContent + v32) );
              IsMatch = CXMLReader::IsMatch(
                          this,
                          *((_QWORD *)v25 + 2),
                          *((unsigned int *)v25 + 6),
                          *((unsigned int *)v25 + 7),
                          &wszContent,
                          v32,
                          6);
              v21 = 0;
              if ( IsMatch )
              {
                v22 = 1;
                v43 = 1;
              }
              else
              {
                v22 = 0;
              }
            }
          }
          break;
        case 0xD:
          if ( *v7 != 3 )
          {
            if ( *v7 != 5 )
              continue;
            v38 = *((_DWORD *)v25 + 6);
            v39 = (const unsigned __int16 *)*((_QWORD *)v25 + 2);
            if ( Node )
            {
              v40 = CParseNode::SetValue(Node, v39, v38);
              if ( v40 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180049CA0[0] )
                  bidTraceW(off_180049208[0], 2861056, off_180049CA0[0], (unsigned int)v40, 2794);
                ThrowHR(v40);
              }
            }
            else
            {
              v41 = CParseNode::SetValue(a3, v39, v38);
              if ( v41 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180049C98[0] )
                  bidTraceW(off_180049208[0], 2869248, off_180049C98[0], (unsigned int)v41, 2802);
                ThrowHR(v41);
              }
            }
            goto LABEL_115;
          }
          if ( v21 )
          {
            v34 = CParseNode::SetValue(
                    *((CParseNode **)v6 + 4),
                    *((const unsigned __int16 **)v25 + 2),
                    *((_DWORD *)v25 + 6));
            if ( v34 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049CB0[0] )
                bidTraceW(off_180049208[0], 2842624, off_180049CB0[0], (unsigned int)v34, 2776);
              ThrowHR(v34);
            }
LABEL_115:
            v21 = v42;
            v22 = v43;
            continue;
          }
          if ( !v22 )
          {
            v37 = CParseNode::SetValue(Node, *((const unsigned __int16 **)v25 + 2), *((_DWORD *)v25 + 6));
            if ( v37 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049CA8[0] )
                bidTraceW(off_180049208[0], 2852864, off_180049CA8[0], (unsigned int)v37, 2786);
              ThrowHR(v37);
            }
            goto LABEL_115;
          }
          v35 = -1;
          do
            ++v35;
          while ( *((_WORD *)&wszTextOnly + v35) );
          v36 = CXMLReader::IsMatch(
                  this,
                  *((_QWORD *)v25 + 2),
                  *((unsigned int *)v25 + 6),
                  *((unsigned int *)v25 + 7),
                  &wszTextOnly,
                  v35,
                  6);
          v21 = v42;
          v22 = v43;
          if ( v36 )
            *(_BYTE *)(*((_QWORD *)v6 + 4) + 40LL) |= 1u;
          break;
        default:
          continue;
      }
    }
  }
  v16 = (_QWORD *)((char *)this + 136);
  v11 = (unsigned int *)((char *)v6 + 24);
  v12 = (unsigned __int16 **)((char *)v6 + 16);
  v46[0] = 0;
  CCollectionList::LookUpByKey(
    *((CCollectionList **)this + 17),
    *((unsigned __int16 **)v6 + 2),
    *((_DWORD *)v6 + 6),
    v46);
  v17 = v46[0];
  *((_QWORD *)this + 57) = v46[0];
  if ( !v17 )
  {
    v46[0] = 0;
    CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 80), *v12, *v11, v46);
    v17 = v46[0];
    *((_QWORD *)this + 57) = v46[0];
  }
  if ( v17 )
  {
LABEL_27:
    v19 = *(_DWORD *)v17;
    if ( (unsigned int)(*(_DWORD *)v17 - 5) <= 1 )
    {
      if ( v19 != 6 )
        v8 = 4;
      *((_DWORD *)this + 119) = v8;
      *((_QWORD *)this + 57) = 0;
      return 0;
    }
    if ( v19 == 1 )
      *v16 = *(_QWORD *)(*(_QWORD *)(v17 + 8) + 632LL);
    goto LABEL_34;
  }
  v18 = *(CCollectionList **)(*((_QWORD *)this + 17) + 48LL);
  while ( v18 )
  {
    v46[0] = 0;
    CCollectionList::LookUpByKey(v18, *((unsigned __int16 **)v6 + 2), *((_DWORD *)v6 + 6), v46);
    v17 = v46[0];
    *((_QWORD *)this + 57) = v46[0];
    v18 = (CCollectionList *)*((_QWORD *)v18 + 6);
    if ( v17 )
    {
      v16 = (_QWORD *)((char *)this + 136);
      goto LABEL_27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024eb0  mov     rax, rsp
0x180024eb3  mov     [rax+8], rbx
0x180024eb7  mov     [rax+10h], rsi
0x180024ebb  mov     [rax+20h], r9w
0x180024ec0  mov     [rax+18h], r8
0x180024ec4  push    rdi
0x180024ec5  push    r12
0x180024ec7  push    r13
0x180024ec9  push    r14
0x180024ecb  push    r15
0x180024ecd  sub     rsp, 60h
0x180024ed1  mov     rbx, rcx
0x180024ed4  mov     [rsp+88h+var_44], 0
0x180024edc  mov     rax, [rsp+88h+arg_20]
0x180024ee4  mov     rsi, [rax]
0x180024ee7  lea     r12, [rcx+1E0h]
0x180024eee  mov     edi, 1
0x180024ef3  cmp     [rsi+4], edi
0x180024ef6  jz      short loc_180024F08
0x180024ef8  cmp     dword ptr [r12], 5
0x180024efd  jz      short loc_180024F08
0x180024eff  mov     eax, [rsp+88h+var_44]
0x180024f03  jmp     loc_1800257CB
0x180024f08  cmp     dword ptr [r12], 4
0x180024f0d  jnz     short loc_180024F71
0x180024f0f  mov     rcx, [rcx+90h]; pbstr
0x180024f16  call    cs:__imp_SysStringLen
0x180024f1d  nop     dword ptr [rax+rax+00h]
0x180024f22  lea     r14, [rsi+18h]
0x180024f26  lea     r15, [rsi+10h]
0x180024f2a  mov     [rsp+88h+var_58], 6
0x180024f32  mov     [rsp+88h+var_60], eax
0x180024f36  mov     rax, [rbx+90h]
0x180024f3d  mov     qword ptr [rsp+88h+var_68], rax
0x180024f42  xor     r9d, r9d
0x180024f45  mov     r8d, [r14]
0x180024f48  mov     rdx, [r15]
0x180024f4b  mov     rcx, rbx
0x180024f4e  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024f53  test    al, al
0x180024f55  jz      short loc_180024F68
0x180024f57  mov     dword ptr [r12], 5
0x180024f5f  mov     eax, [rsp+88h+var_44]
0x180024f63  jmp     loc_1800257CB
0x180024f68  lea     r13, [rbx+1E0h]
0x180024f6f  jmp     short loc_180024F7C
0x180024f71  mov     r13, r12
0x180024f74  lea     r14, [rsi+18h]
0x180024f78  lea     r15, [rsi+10h]
0x180024f7c  mov     ecx, [r12]
0x180024f80  cmp     ecx, 2
0x180024f83  jnz     loc_180025037
0x180024f89  mov     [rsp+88h+var_58], edi
0x180024f8d  mov     [rsp+88h+var_60], 6
0x180024f95  lea     rax, ?wszSchema@@3PAGA; "Schema"
0x180024f9c  mov     qword ptr [rsp+88h+var_68], rax
0x180024fa1  mov     r9d, [rsi+1Ch]
0x180024fa5  mov     r8d, [rsi+18h]
0x180024fa9  mov     rdx, [rsi+10h]
0x180024fad  mov     rcx, rbx
0x180024fb0  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024fb5  test    al, al
0x180024fb7  jz      short loc_180024FDD
0x180024fb9  movzx   r8d, [rsp+88h+arg_18]; unsigned int
0x180024fc2  mov     rdx, [rsp+88h+arg_20]; struct _XML_NODE_INFO **
0x180024fca  call    ?IsRowsetSchema@CXMLReader@@AEAA_NPEAPEAU_XML_NODE_INFO@@K@Z; CXMLReader::IsRowsetSchema(_XML_NODE_INFO * *,ulong)
0x180024fcf  test    al, al
0x180024fd1  jz      short loc_18002502E
0x180024fd3  mov     dword ptr [r13+0], 3
0x180024fdb  jmp     short loc_18002502E
0x180024fdd  mov     [rsp+88h+var_58], 6
0x180024fe5  mov     [rsp+88h+var_60], 3
0x180024fed  lea     rax, aXml; "xml"
0x180024ff4  mov     qword ptr [rsp+88h+var_68], rax
0x180024ff9  mov     r9d, [rsi+1Ch]
0x180024ffd  mov     r8d, [rsi+18h]
0x180025001  mov     rdx, [rsi+10h]
0x180025005  mov     rcx, rbx
0x180025008  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002500d  test    al, al
0x18002500f  jz      short loc_18002502E
0x180025011  movzx   r8d, [rsp+88h+arg_18]; unsigned int
0x18002501a  mov     rdx, [rsp+88h+arg_20]; struct _XML_NODE_INFO **
0x180025022  mov     rcx, rbx; this
0x180025025  call    ?ProcessNamespaceDcl@CXMLReader@@AEAAJPEAPEAU_XML_NODE_INFO@@K@Z; CXMLReader::ProcessNamespaceDcl(_XML_NODE_INFO * *,ulong)
0x18002502a  mov     [rsp+88h+var_44], eax
0x18002502e  mov     eax, [rsp+88h+var_44]
0x180025032  jmp     loc_1800257CB
0x180025037  lea     eax, [rcx-3]
0x18002503a  test    eax, 0FFFFFFFDh
0x18002503f  jnz     loc_1800254C0
0x180025045  xor     r13d, r13d
0x180025048  cmp     ecx, 5
0x18002504b  jnz     loc_180025169
0x180025051  cmp     [rbx+1C8h], r13
0x180025058  jnz     loc_180025169
0x18002505e  lea     r13, [rbx+88h]
0x180025065  lea     r14, [rsi+18h]
0x180025069  lea     r15, [rsi+10h]
0x18002506d  mov     [rsp+88h+var_38], 0
0x180025076  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x18002507b  mov     r8d, [r14]; unsigned int
0x18002507e  mov     rdx, [r15]; unsigned __int16 *
0x180025081  mov     rcx, [r13+0]; this
0x180025085  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x18002508a  mov     rcx, [rsp+88h+var_38]
0x18002508f  mov     [rbx+1C8h], rcx
0x180025096  xor     r8d, r8d
0x180025099  test    rcx, rcx
0x18002509c  jnz     short loc_1800250CF
0x18002509e  mov     [rsp+88h+var_38], r8
0x1800250a3  lea     rcx, [rbx+50h]; this
0x1800250a7  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x1800250ac  mov     r8d, [r14]; unsigned int
0x1800250af  mov     rdx, [r15]; unsigned __int16 *
0x1800250b2  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800250b7  mov     rcx, [rsp+88h+var_38]
0x1800250bc  mov     [rbx+1C8h], rcx
0x1800250c3  lea     rax, [rbx+88h]
0x1800250ca  xor     r8d, r8d
0x1800250cd  jmp     short loc_1800250D2
0x1800250cf  mov     rax, r13
0x1800250d2  test    rcx, rcx
0x1800250d5  jnz     short loc_180025127
0x1800250d7  mov     rax, [rax]
0x1800250da  mov     r13, [rax+30h]
0x1800250de  test    r13, r13
0x1800250e1  jz      short loc_18002511E
0x1800250e3  mov     [rsp+88h+var_38], r8
0x1800250e8  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x1800250ed  mov     r8d, [rsi+18h]; unsigned int
0x1800250f1  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800250f5  mov     rcx, r13; this
0x1800250f8  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800250fd  mov     rcx, [rsp+88h+var_38]
0x180025102  mov     [rbx+1C8h], rcx
0x180025109  mov     r13, [r13+30h]
0x18002510d  xor     r8d, r8d
0x180025110  test    rcx, rcx
0x180025113  jz      short loc_1800250DE
0x180025115  lea     r13, [rbx+88h]
0x18002511c  jmp     short loc_180025127
0x18002511e  mov     eax, [rsp+88h+var_44]
0x180025122  jmp     loc_1800257CB
0x180025127  mov     edx, [rcx]
0x180025129  lea     eax, [rdx-5]
0x18002512c  cmp     eax, edi
0x18002512e  jbe     short loc_180025148
0x180025130  cmp     edx, edi
0x180025132  jnz     short loc_180025143
0x180025134  mov     rax, [rcx+8]
0x180025138  mov     rcx, [rax+278h]
0x18002513f  mov     [r13+0], rcx
0x180025143  xor     r13d, r13d
0x180025146  jmp     short loc_180025169
0x180025148  cmp     edx, 6
0x18002514b  mov     eax, 4
0x180025150  cmovnz  edi, eax
0x180025153  mov     [rbx+1DCh], edi
0x180025159  mov     [rbx+1C8h], r8
0x180025160  mov     eax, [rsp+88h+var_44]
0x180025164  jmp     loc_1800257CB
0x180025169  cmp     dword ptr [r12], 3
0x18002516e  jnz     loc_1800252A0
0x180025174  mov     [rsp+88h+var_58], edi
0x180025178  mov     [rsp+88h+var_60], 7
0x180025180  lea     rax, ?wszExtends@@3PAGA; "extends"
0x180025187  mov     qword ptr [rsp+88h+var_68], rax
0x18002518c  mov     r9d, [rsi+1Ch]
0x180025190  mov     r8d, [r14]
0x180025193  mov     rdx, [r15]
0x180025196  mov     rcx, rbx
0x180025199  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002519e  test    al, al
0x1800251a0  jnz     loc_180025297
0x1800251a6  mov     [rsp+88h+var_58], edi
0x1800251aa  mov     [rsp+88h+var_60], 0Bh
0x1800251b2  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x1800251b9  mov     qword ptr [rsp+88h+var_68], rax
0x1800251be  mov     r9d, [rsi+1Ch]
0x1800251c2  mov     r8d, [r14]
0x1800251c5  mov     rdx, [r15]
0x1800251c8  mov     rcx, rbx
0x1800251cb  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800251d0  test    al, al
0x1800251d2  jnz     loc_1800252A0
0x1800251d8  mov     [rsp+88h+var_58], edi
0x1800251dc  mov     [rsp+88h+var_60], 0Dh
0x1800251e4  lea     r13, ?wszAttributeType@@3PAGA; "AttributeType"
0x1800251eb  mov     qword ptr [rsp+88h+var_68], r13
0x1800251f0  mov     r9d, [rsi+1Ch]
0x1800251f4  mov     r8d, [r14]
0x1800251f7  mov     rdx, [r15]
0x1800251fa  mov     rcx, rbx
0x1800251fd  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025202  xor     r13d, r13d
0x180025205  test    al, al
0x180025207  jnz     loc_1800252A0
0x18002520d  mov     [rsp+88h+var_58], edi
0x180025211  mov     [rsp+88h+var_60], 8
0x180025219  lea     rax, ?wszDataType@@3PAGA; "datatype"
0x180025220  mov     qword ptr [rsp+88h+var_68], rax
0x180025225  mov     r9d, [rsi+1Ch]
0x180025229  mov     r8d, [r14]
0x18002522c  mov     rdx, [r15]
0x18002522f  mov     rcx, rbx
0x180025232  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025237  test    al, al
0x180025239  jnz     short loc_1800252A0
0x18002523b  mov     [rsp+88h+var_58], edi
0x18002523f  mov     [rsp+88h+var_60], 7
0x180025247  lea     rax, ?wszElement@@3PAGA; "element"
0x18002524e  mov     qword ptr [rsp+88h+var_68], rax
0x180025253  mov     r9d, [rsi+1Ch]
0x180025257  mov     r8d, [r14]
0x18002525a  mov     rdx, [r15]
0x18002525d  mov     rcx, rbx
0x180025260  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025265  test    al, al
0x180025267  jnz     short loc_1800252A0
0x180025269  mov     [rsp+88h+var_58], edi
0x18002526d  mov     [rsp+88h+var_60], 9
0x180025275  lea     rax, ?wszAttribute@@3PAGA; "attribute"
0x18002527c  mov     qword ptr [rsp+88h+var_68], rax
0x180025281  mov     r9d, [rsi+1Ch]
0x180025285  mov     r8d, [r14]
0x180025288  mov     rdx, [r15]
0x18002528b  mov     rcx, rbx
0x18002528e  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025293  test    al, al
0x180025295  jnz     short loc_1800252A0
0x180025297  mov     eax, [rsp+88h+var_44]
0x18002529b  jmp     loc_1800257CB
0x1800252a0  mov     r15, r13
0x1800252a3  mov     cl, r13b
0x1800252a6  mov     [rsp+88h+var_48], cl
0x1800252aa  mov     dl, r13b
0x1800252ad  mov     [rsp+88h+var_47], dl
0x1800252b1  mov     eax, r13d
0x1800252b4  lea     r9, ?wszTextOnly@@3PAGA; "textOnly"
0x1800252bb  mov     [rsp+88h+var_40], eax
0x1800252bf  movzx   r13d, [rsp+88h+arg_18]
0x1800252c8  mov     dword ptr [rsp+88h+var_38], r13d
0x1800252cd  cmp     eax, r13d
0x1800252d0  jnb     loc_1800254C0
0x1800252d6  mov     r8, [rsp+88h+arg_20]
0x1800252de  mov     r14, [r8+rax*8]
0x1800252e2  mov     eax, [r14+4]
0x1800252e6  sub     eax, edi
0x1800252e8  cmp     eax, edi
0x1800252ea  ja      loc_180025441
0x1800252f0  lea     rcx, [rbx+198h]
0x1800252f7  mov     rdx, rcx; struct CNodePool **
0x1800252fa  mov     rcx, [rcx]; this
0x1800252fd  call    ?GetNode@CNodePool@@QEAAPEAVCParseNode@@PEAPEAV1@@Z; CNodePool::GetNode(CNodePool * *)
0x180025302  mov     r15, rax
0x180025305  xor     r10d, r10d
0x180025308  test    rax, rax
0x18002530b  jnz     short loc_180025352
0x18002530d  test    byte ptr cs:_bidGblFlags, 2
0x180025314  jz      short loc_180025348
0x180025316  mov     rax, cs:off_180049CC0; "<CXMLReader::CreateNode|ADO|ERR>  HRESU"...
0x18002531d  test    rax, rax
0x180025320  jz      short loc_180025348
0x180025322  mov     [rsp+88h+var_68], 0A96h
0x18002532a  mov     r9d, 8007000Eh
0x180025330  mov     r8, cs:off_180049CC0; "<CXMLReader::CreateNode|ADO|ERR>  HRESU"...
0x180025337  mov     edx, 2A5800h
0x18002533c  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025343  call    _bidTraceW
0x180025348  mov     ecx, 8007000Eh; int
0x18002534d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025352  cmp     dword ptr [r12], 5
0x180025357  jnz     short loc_180025386
0x180025359  cmp     [rbx+190h], r10b
0x180025360  jnz     short loc_180025386
0x180025362  mov     r8d, [r14+4]
0x180025366  cmp     [rsp+88h+var_40], r10d
0x18002536b  jz      short loc_180025373
0x18002536d  mov     rdx, [rsi+20h]
0x180025371  jmp     short loc_18002537B
0x180025373  mov     rdx, [rsp+88h+arg_10]
0x18002537b  mov     r9, r10
0x18002537e  mov     eax, r10d
0x180025381  mov     ecx, r10d
0x180025384  jmp     short loc_1800253AB
0x180025386  mov     ecx, [r14+1Ch]
0x18002538a  mov     eax, [r14+18h]
0x18002538e  mov     r9, [r14+10h]; unsigned __int16 *
0x180025392  mov     r8d, [r14+4]; unsigned int
0x180025396  cmp     [rsp+88h+var_40], r10d
0x18002539b  jz      short loc_1800253A3
0x18002539d  mov     rdx, [rsi+20h]
0x1800253a1  jmp     short loc_1800253AB
0x1800253a3  mov     rdx, [rsp+88h+arg_10]; struct CParseNode *
0x1800253ab  mov     [rsp+88h+var_60], ecx; unsigned int
0x1800253af  mov     [rsp+88h+var_68], eax; unsigned int
0x1800253b3  mov     rcx, r15; this
0x1800253b6  call    ?Init@CParseNode@@QEAAJPEAV1@KPEBGKK@Z; CParseNode::Init(CParseNode *,ulong,ushort const *,ulong,ulong)
0x1800253bb  lea     rax, [rbx+1A0h]
  ... truncated ...
```
