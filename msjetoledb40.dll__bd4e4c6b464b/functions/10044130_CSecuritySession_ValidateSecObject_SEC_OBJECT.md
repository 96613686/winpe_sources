# CSecuritySession::ValidateSecObject(_SEC_OBJECT *)

- ea: `0x10044130`
- end: `0x1004427c`
- name: `?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z`
- size: `332`
- prototype: `int __thiscall(CSecuritySession *__hidden this, struct _SEC_OBJECT *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10042630`
- `0x100429a0`
- `0x10042c60`
- `0x10042ed0`
- `0x10043310`

## callees

- `0x100257a0`
- `0x100440d0`
- `0x10044130`

## pseudocode

```c
int __thiscall CSecuritySession::ValidateSecObject(CSecuritySession *this, struct _SEC_OBJECT *a2)
{
  int v2; // esi
  SEC_OBJECT_ELEMENT *prgObjects; // ebx
  const GUID *v4; // ecx
  unsigned int v5; // edi
  SEC_OBJECT_ELEMENT *v6; // edx
  const GUID *v8; // ecx
  SEC_OBJECT_ELEMENT *v9; // edx
  unsigned int v10; // edi
  SEC_OBJECT_ELEMENT *v11; // edx
  const GUID *v12; // ecx
  unsigned int v13; // edi
  const GUID *v14; // ecx
  SEC_OBJECT_ELEMENT *v15; // edx
  unsigned int v16; // edi
  int v17; // eax
  bool v18; // cf
  unsigned __int8 v19; // al
  unsigned __int8 v20; // al
  unsigned __int8 Data1_high; // al
  DBKIND eKind; // ecx
  LPOLESTR pwszName; // eax
  bool v24; // zf
  const struct tagDBID *v25; // [esp+0h] [ebp-Ch]
  const struct tagDBID *v26; // [esp+4h] [ebp-8h]

  v2 = 0;
  if ( a2->cObjects > 2 )
    return -2147217811;
  if ( !a2->cObjects )
    return -2147217811;
  prgObjects = a2->prgObjects;
  if ( !prgObjects || !CSecuritySession::MapSECOBJECTELEMENTtoContainerName((CSecuritySession *)a2, a2->prgObjects) )
    return -2147217811;
  v4 = &DBOBJECT_COLUMN;
  v5 = 12;
  v6 = prgObjects;
  while ( v4->Data1 == v6->guidObjectType.Data1 )
  {
    v4 = (const GUID *)((char *)v4 + 4);
    v6 = (SEC_OBJECT_ELEMENT *)((char *)v6 + 4);
    v18 = v5 < 4;
    v5 -= 4;
    if ( v18 )
      return -2147217811;
  }
  if ( a2->cObjects > 1 )
  {
    v8 = &DBOBJECT_TABLE;
    v9 = prgObjects;
    v10 = 12;
    while ( v8->Data1 == v9->guidObjectType.Data1 )
    {
      v8 = (const GUID *)((char *)v8 + 4);
      v9 = (SEC_OBJECT_ELEMENT *)((char *)v9 + 4);
      v18 = v10 < 4;
      v10 -= 4;
      if ( v18 )
      {
        v11 = prgObjects + 1;
        v12 = &DBOBJECT_COLUMN;
        v13 = 12;
        while ( v12->Data1 == v11->guidObjectType.Data1 )
        {
          v12 = (const GUID *)((char *)v12 + 4);
          v11 = (SEC_OBJECT_ELEMENT *)((char *)v11 + 4);
          v18 = v13 < 4;
          v13 -= 4;
          if ( v18 )
          {
            if ( prgObjects[1].ObjectID.eKind != 2 || prgObjects[1].ObjectID.uName.ulPropid )
              return -2147217811;
            goto LABEL_18;
          }
        }
        return -2147217811;
      }
    }
    return -2147217811;
  }
LABEL_18:
  v14 = &DBOBJECT_DATABASE;
  v15 = prgObjects;
  v16 = 12;
  while ( v14->Data1 == v15->guidObjectType.Data1 )
  {
    v14 = (const GUID *)((char *)v14 + 4);
    v15 = (SEC_OBJECT_ELEMENT *)((char *)v15 + 4);
    v18 = v16 < 4;
    v16 -= 4;
    if ( v18 )
    {
      v17 = 0;
      goto LABEL_28;
    }
  }
  v18 = LOBYTE(v14->Data1) < LOBYTE(v15->guidObjectType.Data1);
  if ( LOBYTE(v14->Data1) == LOBYTE(v15->guidObjectType.Data1)
    && (v19 = BYTE1(v14->Data1), v18 = v19 < BYTE1(v15->guidObjectType.Data1), v19 == BYTE1(v15->guidObjectType.Data1))
    && (v20 = BYTE2(v14->Data1), v18 = v20 < BYTE2(v15->guidObjectType.Data1), v20 == BYTE2(v15->guidObjectType.Data1))
    && (Data1_high = HIBYTE(v14->Data1),
        v18 = Data1_high < HIBYTE(v15->guidObjectType.Data1),
        Data1_high == HIBYTE(v15->guidObjectType.Data1)) )
  {
    v17 = 0;
  }
  else
  {
    v17 = v18 ? -1 : 1;
  }
LABEL_28:
  eKind = prgObjects->ObjectID.eKind;
  if ( v17 )
  {
    if ( eKind == 2 )
      return v2;
    v2 = CompareDBIDs(v25, v26);
    v24 = v2 == 0;
    goto LABEL_34;
  }
  if ( eKind != 2 )
    return -2147217811;
  pwszName = prgObjects->ObjectID.uName.pwszName;
  if ( pwszName )
  {
    v24 = *pwszName == 0;
LABEL_34:
    if ( !v24 )
      return -2147217811;
  }
  return v2;
}

```

## disassembly

```asm
0x10044130  mov     edi, edi
0x10044132  push    ebp
0x10044133  mov     ebp, esp
0x10044135  mov     ecx, [ebp+arg_0]; this
0x10044138  push    ebx
0x10044139  push    esi; struct tagDBID *
0x1004413a  xor     esi, esi
0x1004413c  mov     eax, [ecx]
0x1004413e  push    edi; struct tagDBID *
0x1004413f  cmp     eax, 2
0x10044142  ja      loc_1004426E
0x10044148  test    eax, eax
0x1004414a  jz      loc_1004426E
0x10044150  mov     ebx, [ecx+4]
0x10044153  test    ebx, ebx
0x10044155  jz      loc_1004426E
0x1004415b  push    ebx; struct _SEC_OBJECT_ELEMENT *
0x1004415c  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x10044161  test    eax, eax
0x10044163  jz      loc_1004426E
0x10044169  mov     ecx, offset _DBOBJECT_COLUMN
0x1004416e  lea     edi, [esi+0Ch]
0x10044171  mov     edx, ebx
0x10044173  mov     eax, [ecx]
0x10044175  cmp     eax, [edx]
0x10044177  jnz     short loc_10044192
0x10044179  add     ecx, 4
0x1004417c  add     edx, 4
0x1004417f  sub     edi, 4
0x10044182  jnb     short loc_10044173
0x10044184  mov     esi, 80040E6Dh
0x10044189  pop     edi
0x1004418a  mov     eax, esi
0x1004418c  pop     esi
0x1004418d  pop     ebx
0x1004418e  pop     ebp
0x1004418f  retn    4
0x10044192  mov     eax, [ebp+arg_0]
0x10044195  cmp     dword ptr [eax], 1
0x10044198  jbe     short loc_100441F4
0x1004419a  mov     ecx, offset _DBOBJECT_TABLE
0x1004419f  mov     edx, ebx
0x100441a1  mov     edi, 0Ch
0x100441a6  mov     eax, [ecx]
0x100441a8  cmp     eax, [edx]
0x100441aa  jnz     loc_1004426E
0x100441b0  add     ecx, 4
0x100441b3  add     edx, 4
0x100441b6  sub     edi, 4
0x100441b9  jnb     short loc_100441A6
0x100441bb  lea     edx, [ebx+28h]
0x100441be  mov     ecx, offset _DBOBJECT_COLUMN
0x100441c3  mov     edi, 0Ch
0x100441c8  nop     dword ptr [eax+eax+00000000h]
0x100441d0  mov     eax, [ecx]
0x100441d2  cmp     eax, [edx]
0x100441d4  jnz     loc_1004426E
0x100441da  add     ecx, 4
0x100441dd  add     edx, 4
0x100441e0  sub     edi, 4
0x100441e3  jnb     short loc_100441D0
0x100441e5  cmp     dword ptr [ebx+48h], 2
0x100441e9  jnz     loc_1004426E
0x100441ef  cmp     [ebx+4Ch], esi
0x100441f2  jnz     short loc_1004426E
0x100441f4  mov     ecx, offset _DBOBJECT_DATABASE
0x100441f9  mov     edx, ebx
0x100441fb  mov     edi, 0Ch
0x10044200  mov     eax, [ecx]
0x10044202  cmp     eax, [edx]
0x10044204  jnz     short loc_10044215
0x10044206  add     ecx, 4
0x10044209  add     edx, 4
0x1004420c  sub     edi, 4
0x1004420f  jnb     short loc_10044200
0x10044211  xor     eax, eax
0x10044213  jmp     short loc_1004423C
0x10044215  mov     al, [ecx]
0x10044217  cmp     al, [edx]
0x10044219  jnz     short loc_10044237
0x1004421b  mov     al, [ecx+1]
0x1004421e  cmp     al, [edx+1]
0x10044221  jnz     short loc_10044237
0x10044223  mov     al, [ecx+2]
0x10044226  cmp     al, [edx+2]
0x10044229  jnz     short loc_10044237
0x1004422b  mov     al, [ecx+3]
0x1004422e  cmp     al, [edx+3]
0x10044231  jnz     short loc_10044237
0x10044233  xor     eax, eax
0x10044235  jmp     short loc_1004423C
0x10044237  sbb     eax, eax
0x10044239  or      eax, 1
0x1004423c  mov     ecx, [ebx+20h]
0x1004423f  test    eax, eax
0x10044241  jnz     short loc_10044256
0x10044243  cmp     ecx, 2
0x10044246  jnz     short loc_1004426E
0x10044248  mov     eax, [ebx+24h]
0x1004424b  test    eax, eax
0x1004424d  jz      short loc_10044273
0x1004424f  xor     ecx, ecx
0x10044251  cmp     cx, [eax]
0x10044254  jmp     short loc_1004426C
0x10044256  cmp     ecx, 2
0x10044259  jz      short loc_10044273
0x1004425b  lea     ecx, [ebx+10h]
0x1004425e  mov     edx, offset ?NEWCONTAINEROBJECTS@@3UtagDBID@@B; tagDBID const NEWCONTAINEROBJECTS
0x10044263  call    ?CompareDBIDs@@YGJPBUtagDBID@@0@Z; CompareDBIDs(tagDBID const *,tagDBID const *)
0x10044268  mov     esi, eax
0x1004426a  test    esi, esi
0x1004426c  jz      short loc_10044273
0x1004426e  mov     esi, 80040E6Dh
0x10044273  pop     edi
0x10044274  mov     eax, esi
0x10044276  pop     esi
0x10044277  pop     ebx
0x10044278  pop     ebp
0x10044279  retn    4
```
