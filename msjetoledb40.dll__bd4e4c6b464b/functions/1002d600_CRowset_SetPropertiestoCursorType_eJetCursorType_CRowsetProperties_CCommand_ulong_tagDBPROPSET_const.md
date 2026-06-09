# CRowset::SetPropertiestoCursorType(eJetCursorType,CRowsetProperties &,CCommand *,ulong,tagDBPROPSET * const)

- ea: `0x1002d600`
- end: `0x1002d777`
- name: `?SetPropertiestoCursorType@CRowset@@IAEJW4eJetCursorType@@AAVCRowsetProperties@@PAVCCommand@@KQAUtagDBPROPSET@@@Z`
- size: `375`
- prototype: `int __thiscall __high(enum eJetCursorType, struct CRowsetProperties *, struct CCommand *, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10028340`

## callees

- `0x1001f2d0`
- `0x10025630`
- `0x1002d600`
- `0x1004cc50`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1002d740`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1002d740`

## pseudocode

```c
int __stdcall CRowset::SetPropertiestoCursorType(unsigned int a1, int a2, __int64 a3, unsigned int a4)
{
  HRESULT v4; // edi
  unsigned int v5; // eax
  JoltProperties *v6; // ebx
  VARIANTARG *v7; // esi
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // eax
  const VARIANTARG *v13; // eax
  struct _GUID v15; // [esp-10h] [ebp-38h]
  struct tagVARIANT *v16; // [esp+0h] [ebp-28h]
  struct tagVARIANT *v17; // [esp+4h] [ebp-24h]
  unsigned int v18; // [esp+8h] [ebp-20h]
  unsigned int v19; // [esp+Ch] [ebp-1Ch] BYREF
  unsigned int v20; // [esp+10h] [ebp-18h] BYREF
  unsigned int v21; // [esp+14h] [ebp-14h]
  VARIANTARG *v22; // [esp+18h] [ebp-10h]
  int v23; // [esp+1Ch] [ebp-Ch]
  unsigned int v24; // [esp+20h] [ebp-8h]
  unsigned int v25; // [esp+24h] [ebp-4h]

  v23 = 0;
  v4 = 0;
  if ( a1 > 5 )
    return v4;
  v5 = 0;
  v21 = 0;
  do
  {
    v6 = *(JoltProperties **)(a2 + 8);
    v24 = 104 * v5;
    v25 = dword_10005A20[26 * v5];
    if ( JoltProperties::BinarySearch(v6, v25, &v20) < 0 )
      v7 = 0;
    else
      v7 = (VARIANTARG *)(*((_DWORD *)v6 + 4) + 48 * v20);
    v22 = v7 + 1;
    if ( JoltProperties::BinarySearch(v6, v25, &v19) < 0 )
      v8 = 0;
    else
      v8 = *((_DWORD *)v6 + 4) + 48 * v19;
    if ( (*(_BYTE *)(v8 + 40) & 2) != 0 )
    {
      v9 = 8 * a1;
      v10 = v24;
      if ( word_10005A28[8 * a1 + v24 / 2] )
      {
        v11 = dword_10005A24[v24 / 4];
        if ( v11 )
        {
          if ( v11 != 1 || (~dword_10005A30[4 * a1 + v24 / 4] & v22->lVal) == 0 )
          {
LABEL_17:
            if ( v4 < 0 )
              break;
            goto LABEL_23;
          }
        }
        else if ( fIsEqualVariants(v16, v17) )
        {
          goto LABEL_17;
        }
        *(_QWORD *)v15.Data4 = a4 | 0x800000000LL;
        *(_QWORD *)&v15.Data1 = a3;
        v12 = HandleInvalidPropertyValue(
                *(_OWORD *)&DBPROPSET_ROWSET,
                v15,
                (struct CSettableProperties *)v16,
                (struct CCommand *)v17,
                v18,
                (struct tagDBPROPSET *const)v19,
                v20);
        v23 = 1;
        v4 = v12;
        goto LABEL_17;
      }
    }
    else
    {
      v10 = v24;
      v9 = 8 * a1;
    }
    v13 = (const VARIANTARG *)((char *)&word_10005A28[v9] + v10);
    if ( v13->vt )
    {
      v4 = VariantCopy(v7 + 1, v13);
      if ( v4 < 0 )
        break;
      v7[2].lVal |= 2u;
    }
LABEL_23:
    v5 = v21 + 1;
    v21 = v5;
  }
  while ( v5 < 0xB );
  if ( v23 == 1 )
    return -2147217887;
  return v4;
}

```

## disassembly

```asm
0x1002d600  mov     edi, edi
0x1002d602  push    ebp
0x1002d603  mov     ebp, esp
0x1002d605  sub     esp, 1Ch
0x1002d608  push    ebx; unsigned int
0x1002d609  xor     eax, eax
0x1002d60b  push    esi; struct CCommand *
0x1002d60c  push    edi; struct CSettableProperties *
0x1002d60d  mov     [ebp+var_C], eax
0x1002d610  xor     edi, edi
0x1002d612  mov     eax, [ebp+arg_0]
0x1002d615  cmp     eax, 0FFFFh
0x1002d61a  jz      loc_1002D76C
0x1002d620  jg      loc_1002D76C
0x1002d626  cmp     eax, 5
0x1002d629  ja      loc_1002D76C
0x1002d62f  movzx   eax, ds:byte_1002D77C[eax]
0x1002d636  jmp     ds:jpt_1002D636[eax*4]; switch 1 cases
0x1002d63d  xor     eax, eax; jumptable 1002D636 case 0
0x1002d63f  mov     [ebp+var_14], eax
0x1002d642  mov     ecx, [ebp+arg_4]
0x1002d645  imul    eax, 68h ; 'h'
0x1002d648  mov     ebx, [ecx+8]
0x1002d64b  lea     ecx, [ebp+var_18]
0x1002d64e  push    ecx; unsigned int *
0x1002d64f  mov     [ebp+var_8], eax
0x1002d652  mov     ecx, ebx; this
0x1002d654  mov     eax, ds:dword_10005A20[eax]
0x1002d65a  push    eax; unsigned int
0x1002d65b  mov     [ebp+var_4], eax
0x1002d65e  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1002d663  test    eax, eax
0x1002d665  js      short loc_1002D675
0x1002d667  mov     eax, [ebp+var_18]
0x1002d66a  lea     esi, [eax+eax*2]
0x1002d66d  shl     esi, 4
0x1002d670  add     esi, [ebx+10h]
0x1002d673  jmp     short loc_1002D677
0x1002d675  xor     esi, esi
0x1002d677  lea     eax, [esi+10h]
0x1002d67a  mov     ecx, ebx; this
0x1002d67c  mov     [ebp+var_10], eax
0x1002d67f  lea     eax, [ebp+var_1C]
0x1002d682  push    eax; unsigned int *
0x1002d683  push    [ebp+var_4]; unsigned int
0x1002d686  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1002d68b  test    eax, eax
0x1002d68d  js      short loc_1002D69D
0x1002d68f  mov     eax, [ebp+var_1C]
0x1002d692  lea     eax, [eax+eax*2]
0x1002d695  shl     eax, 4
0x1002d698  add     eax, [ebx+10h]
0x1002d69b  jmp     short loc_1002D69F
0x1002d69d  xor     eax, eax
0x1002d69f  test    byte ptr [eax+28h], 2
0x1002d6a3  mov     eax, [ebp+arg_0]
0x1002d6a6  jz      short loc_1002D726
0x1002d6a8  mov     edx, [ebp+var_8]
0x1002d6ab  xor     ecx, ecx
0x1002d6ad  shl     eax, 4
0x1002d6b0  add     edx, eax
0x1002d6b2  cmp     cx, ds:word_10005A28[edx]
0x1002d6b9  mov     ecx, [ebp+var_8]
0x1002d6bc  jz      short loc_1002D72C
0x1002d6be  mov     eax, ds:dword_10005A24[ecx]
0x1002d6c4  sub     eax, 0
0x1002d6c7  jz      short loc_1002D6E0
0x1002d6c9  sub     eax, 1
0x1002d6cc  jnz     short loc_1002D720
0x1002d6ce  mov     ecx, [ebp+var_10]
0x1002d6d1  mov     eax, ds:dword_10005A30[edx]
0x1002d6d7  not     eax
0x1002d6d9  test    [ecx+8], eax
0x1002d6dc  jz      short loc_1002D720
0x1002d6de  jmp     short loc_1002D6F2
0x1002d6e0  mov     ecx, [ebp+var_10]
0x1002d6e3  lea     edx, word_10005A28[edx]
0x1002d6e9  call    ?fIsEqualVariants@@YGHAAUtagVARIANT@@0@Z; fIsEqualVariants(tagVARIANT &,tagVARIANT &)
0x1002d6ee  test    eax, eax
0x1002d6f0  jnz     short loc_1002D720
0x1002d6f2  movups  xmm0, xmmword ptr ds:_DBPROPSET_ROWSET.Data1
0x1002d6f9  mov     edx, [ebp+arg_4]
0x1002d6fc  mov     ecx, [ebp+var_4]
0x1002d6ff  push    8
0x1002d701  push    dword ptr [ebp+arg_8.Data4]
0x1002d704  push    dword ptr [ebp+arg_8.Data2]
0x1002d707  push    [ebp+arg_8.Data1]; struct _GUID
0x1002d70a  sub     esp, 10h
0x1002d70d  mov     eax, esp
0x1002d70f  movups  xmmword ptr [eax], xmm0
0x1002d712  call    ?HandleInvalidPropertyValue@@YGJKU_GUID@@AAVCSettableProperties@@PAVCCommand@@KQAUtagDBPROPSET@@K@Z; HandleInvalidPropertyValue(ulong,_GUID,CSettableProperties &,CCommand *,ulong,tagDBPROPSET * const,ulong)
0x1002d717  mov     [ebp+var_C], 1
0x1002d71e  mov     edi, eax
0x1002d720  test    edi, edi
0x1002d722  js      short loc_1002D760
0x1002d724  jmp     short loc_1002D750
0x1002d726  mov     ecx, [ebp+var_8]
0x1002d729  shl     eax, 4
0x1002d72c  lea     eax, word_10005A28[eax]
0x1002d732  add     eax, ecx
0x1002d734  xor     ecx, ecx
0x1002d736  cmp     cx, [eax]
0x1002d739  jz      short loc_1002D750
0x1002d73b  push    eax; pvargSrc
0x1002d73c  lea     ecx, [esi+10h]
0x1002d73f  push    ecx; pvargDest
0x1002d740  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1002d746  mov     edi, eax
0x1002d748  test    edi, edi
0x1002d74a  js      short loc_1002D760
0x1002d74c  or      dword ptr [esi+28h], 2
0x1002d750  mov     eax, [ebp+var_14]
0x1002d753  inc     eax
0x1002d754  mov     [ebp+var_14], eax
0x1002d757  cmp     eax, 0Bh
0x1002d75a  jb      loc_1002D642
0x1002d760  cmp     [ebp+var_C], 1
0x1002d764  mov     ecx, 80040E21h
0x1002d769  cmovz   edi, ecx
0x1002d76c  mov     eax, edi
0x1002d76e  pop     edi
0x1002d76f  pop     esi
0x1002d770  pop     ebx
0x1002d771  mov     esp, ebp
0x1002d773  pop     ebp
0x1002d774  retn    14h
```
