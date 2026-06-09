# SortMover::Seek(SeekOption,Err &)

- ea: `0x1004c8f0`
- end: `0x1004cb53`
- name: `?Seek@SortMover@@UAEXW4SeekOption@@AAVErr@@@Z`
- size: `611`
- prototype: `void __thiscall __high(enum SeekOption, struct Err *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1000eb60`
- `0x10012d60`
- `0x10025ee0`
- `0x10026060`
- `0x1004c8f0`
- `0x1004cee0`

## pseudocode

```c
int __thiscall SortMover::Seek(_DWORD *this, void *a2, struct Err *a3)
{
  _DWORD *v3; // edi
  _DWORD **v4; // ebx
  Checksum *v5; // ecx
  unsigned int v6; // eax
  unsigned __int8 *v7; // esi
  int result; // eax
  _DWORD *v9; // esi
  int v10; // edx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  unsigned int v14; // edx
  int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // esi
  unsigned int v18; // ebx
  int v19; // ecx
  int v20; // edx
  unsigned int v21; // esi
  bool v22; // cf
  unsigned __int8 v23; // al
  unsigned __int8 v24; // al
  unsigned __int8 v25; // al
  int v26; // eax
  struct Err *v27; // ebx
  unsigned int v28; // eax
  int v29; // eax
  int v30; // [esp+Ch] [ebp-24h]
  unsigned int v31; // [esp+10h] [ebp-20h]
  unsigned int v32; // [esp+18h] [ebp-18h]
  int v33; // [esp+1Ch] [ebp-14h]
  unsigned int v34; // [esp+20h] [ebp-10h]
  unsigned int v35; // [esp+24h] [ebp-Ch]
  _DWORD *v37; // [esp+2Ch] [ebp-4h]

  v3 = this;
  v4 = (_DWORD **)this[1];
  ((void (__thiscall *)(_DWORD **, struct Err *))(*v4)[31])(v4, a3);
  v6 = v3[10];
  if ( v6 > 0xFF )
  {
    v7 = (unsigned __int8 *)(v3[11] + 253);
    *(_WORD *)v7 = Checksum::ComputeCrc(v5, v7, v6 - 253);
    v3[10] = 255;
  }
  if ( !v3[2] )
  {
    result = SortMover::WrapUpInput((int)v3, a3);
    if ( result != 2 )
    {
      if ( (*(_BYTE *)a3 & 8) == 0 )
        return (*(int (__thiscall **)(_DWORD *, void *, struct Err *))(*v4[9] + 28))(v4[9], a2, a3);
      return result;
    }
  }
  v9 = (_DWORD *)v3[3];
  v10 = 1;
  v37 = v9;
  v30 = 1;
  v11 = v9[3];
  v12 = v9[6];
  v34 = v12;
  v13 = v9[5] + 4 * v11;
  v35 = v13;
  v31 = v13;
  if ( !v11 )
    goto LABEL_39;
  v14 = v3[10];
  v15 = v3[11];
  v16 = v9[5];
  v32 = v14;
  v33 = v15;
  while ( 1 )
  {
    v17 = v14;
    v18 = v16 + 4 * ((int)(v13 - v16) >> 3);
    v19 = *(_DWORD *)v18 + 4;
    v22 = *(unsigned __int16 *)(*(_DWORD *)v18 + 2) < v14;
    v20 = v33;
    if ( v22 )
      v17 = *(unsigned __int16 *)(*(_DWORD *)v18 + 2);
    v22 = v17 < 4;
    v21 = v17 - 4;
    if ( v22 )
    {
LABEL_15:
      if ( v21 == -4 )
        goto LABEL_24;
    }
    else
    {
      while ( *(_DWORD *)v19 == *(_DWORD *)v20 )
      {
        v19 += 4;
        v20 += 4;
        v22 = v21 < 4;
        v21 -= 4;
        if ( v22 )
          goto LABEL_15;
      }
    }
    v22 = *(_BYTE *)v19 < *(_BYTE *)v20;
    if ( *(_BYTE *)v19 != *(_BYTE *)v20
      || v21 != -3
      && ((v23 = *(_BYTE *)(v19 + 1), v22 = v23 < *(_BYTE *)(v20 + 1), v23 != *(_BYTE *)(v20 + 1))
       || v21 != -2
       && ((v24 = *(_BYTE *)(v19 + 2), v22 = v24 < *(_BYTE *)(v20 + 2), v24 != *(_BYTE *)(v20 + 2))
        || v21 != -1 && (v25 = *(_BYTE *)(v19 + 3), v22 = v25 < *(_BYTE *)(v20 + 3), v25 != *(_BYTE *)(v20 + 3)))) )
    {
      v26 = v22 ? -1 : 1;
      goto LABEL_25;
    }
LABEL_24:
    v26 = 0;
LABEL_25:
    if ( a2 == (void *)4 )
    {
      if ( v26 <= 0 )
      {
        v13 = v31;
        v16 = v18 + 4;
        v10 = v30;
        goto LABEL_35;
      }
      v10 = v30;
    }
    else
    {
      v10 = v30;
      if ( v26 < 0 )
      {
        v13 = v31;
        v16 = v18 + 4;
        goto LABEL_35;
      }
      if ( !v26 )
        v10 = 0;
      v30 = v10;
    }
    v13 = v18;
    v31 = v18;
LABEL_35:
    if ( v16 == v13 )
      break;
    v14 = v32;
  }
  v12 = v34;
  v3 = this;
  if ( v13 < v35 )
    v12 = v13;
  v9 = v37;
LABEL_39:
  v3[4] = v12;
  switch ( (unsigned int)a2 )
  {
    case 0u:
      v27 = a3;
      if ( v10 == 1 )
        v3[4] = v9[6];
      break;
    case 2u:
      v28 = v9[6];
      if ( v12 != v28 )
      {
        if ( v12 > v9[5] )
          v28 = v12 - 4;
        v3[4] = v28;
      }
      goto LABEL_46;
    case 3u:
      v27 = a3;
      if ( v10 == 1 )
      {
        Err::SetWarning(a3, 1039);
        v29 = v3[3];
        v13 = v3[4];
        if ( v13 <= *(_DWORD *)(v29 + 20) )
          v3[4] = *(_DWORD *)(v29 + 24);
        else
          v3[4] = v13 - 4;
      }
      break;
    case 5u:
      if ( v10 != 1 )
        goto LABEL_46;
      v27 = a3;
      Err::SetWarning(a3, 1039);
      break;
    default:
LABEL_46:
      v27 = a3;
      break;
  }
  result = v3[4];
  if ( result == *(_DWORD *)(v3[3] + 24) )
  {
    result = Err::SetError(v27, -1601, v13);
    v3[2] = 1;
  }
  else
  {
    v3[2] = 2;
  }
  return result;
}

```

## disassembly

```asm
0x1004c8f0  mov     edi, edi
0x1004c8f2  push    ebp
0x1004c8f3  mov     ebp, esp
0x1004c8f5  and     esp, 0FFFFFFF8h
0x1004c8f8  sub     esp, 24h
0x1004c8fb  push    ebx
0x1004c8fc  push    esi
0x1004c8fd  push    edi; unsigned int
0x1004c8fe  push    [ebp+arg_4]; void *
0x1004c901  mov     edi, ecx
0x1004c903  mov     [esp+34h+var_8], edi
0x1004c907  mov     ebx, [edi+4]
0x1004c90a  mov     eax, [ebx]
0x1004c90c  mov     esi, [eax+7Ch]
0x1004c90f  mov     ecx, esi
0x1004c911  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004c917  mov     ecx, ebx
0x1004c919  call    esi
0x1004c91b  mov     eax, [edi+28h]
0x1004c91e  cmp     eax, 0FFh
0x1004c923  jbe     short loc_1004C944
0x1004c925  mov     esi, [edi+2Ch]
0x1004c928  add     eax, 0FFFFFF03h
0x1004c92d  add     esi, 0FDh
0x1004c933  push    eax; unsigned int
0x1004c934  push    esi; unsigned __int8 *
0x1004c935  call    ?ComputeCrc@Checksum@@QAEGPAEI@Z; Checksum::ComputeCrc(uchar *,uint)
0x1004c93a  mov     [esi], ax
0x1004c93d  mov     dword ptr [edi+28h], 0FFh
0x1004c944  cmp     dword ptr [edi+8], 0
0x1004c948  jnz     short loc_1004C984
0x1004c94a  mov     esi, [ebp+arg_4]
0x1004c94d  mov     ecx, edi
0x1004c94f  push    esi
0x1004c950  call    ?WrapUpInput@SortMover@@AAE?AW4SrtMvrMode@@AAVErr@@@Z; SortMover::WrapUpInput(Err &)
0x1004c955  cmp     eax, 2
0x1004c958  jz      short loc_1004C984
0x1004c95a  test    byte ptr [esi], 8
0x1004c95d  jnz     loc_1004CB4A
0x1004c963  mov     edi, [ebx+24h]
0x1004c966  push    esi; unsigned int
0x1004c967  push    [ebp+arg_0]; void *
0x1004c96a  mov     eax, [edi]
0x1004c96c  mov     esi, [eax+1Ch]
0x1004c96f  mov     ecx, esi
0x1004c971  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004c977  mov     ecx, edi
0x1004c979  call    esi
0x1004c97b  pop     edi
0x1004c97c  pop     esi
0x1004c97d  pop     ebx
0x1004c97e  mov     esp, ebp
0x1004c980  pop     ebp
0x1004c981  retn    8
0x1004c984  mov     esi, [edi+0Ch]
0x1004c987  mov     edx, 1
0x1004c98c  mov     [esp+30h+var_4], esi
0x1004c990  mov     [esp+30h+var_24], edx
0x1004c994  mov     eax, [esi+0Ch]
0x1004c997  mov     ecx, [esi+14h]
0x1004c99a  mov     ebx, [esi+18h]
0x1004c99d  mov     [esp+30h+var_1C], ecx
0x1004c9a1  mov     [esp+30h+var_10], ebx
0x1004c9a5  lea     ecx, [ecx+eax*4]
0x1004c9a8  mov     [esp+30h+var_C], ecx
0x1004c9ac  mov     [esp+30h+var_20], ecx
0x1004c9b0  test    eax, eax
0x1004c9b2  jz      loc_1004CA9F
0x1004c9b8  mov     edx, [edi+28h]
0x1004c9bb  mov     eax, [edi+2Ch]
0x1004c9be  mov     edi, [esp+30h+var_1C]
0x1004c9c2  mov     [esp+30h+var_18], edx
0x1004c9c6  mov     [esp+30h+var_14], eax
0x1004c9ca  jmp     short loc_1004C9D4
0x1004c9d0  mov     edx, [esp+30h+var_18]
0x1004c9d4  mov     eax, ecx
0x1004c9d6  mov     esi, edx
0x1004c9d8  sub     eax, edi
0x1004c9da  sar     eax, 3
0x1004c9dd  lea     ebx, [edi+eax*4]
0x1004c9e0  mov     eax, [ebx]
0x1004c9e2  lea     ecx, [eax+4]
0x1004c9e5  movzx   eax, word ptr [eax+2]
0x1004c9e9  cmp     eax, edx
0x1004c9eb  mov     edx, [esp+30h+var_14]
0x1004c9ef  cmovb   esi, eax
0x1004c9f2  sub     esi, 4
0x1004c9f5  jb      short loc_1004CA08
0x1004c9f7  mov     eax, [ecx]
0x1004c9f9  cmp     eax, [edx]
0x1004c9fb  jnz     short loc_1004CA0D
0x1004c9fd  add     ecx, 4
0x1004ca00  add     edx, 4
0x1004ca03  sub     esi, 4
0x1004ca06  jnb     short loc_1004C9F7
0x1004ca08  cmp     esi, 0FFFFFFFCh
0x1004ca0b  jz      short loc_1004CA41
0x1004ca0d  mov     al, [ecx]
0x1004ca0f  cmp     al, [edx]
0x1004ca11  jnz     short loc_1004CA3A
0x1004ca13  cmp     esi, 0FFFFFFFDh
0x1004ca16  jz      short loc_1004CA41
0x1004ca18  mov     al, [ecx+1]
0x1004ca1b  cmp     al, [edx+1]
0x1004ca1e  jnz     short loc_1004CA3A
0x1004ca20  cmp     esi, 0FFFFFFFEh
0x1004ca23  jz      short loc_1004CA41
0x1004ca25  mov     al, [ecx+2]
0x1004ca28  cmp     al, [edx+2]
0x1004ca2b  jnz     short loc_1004CA3A
0x1004ca2d  cmp     esi, 0FFFFFFFFh
0x1004ca30  jz      short loc_1004CA41
0x1004ca32  mov     al, [ecx+3]
0x1004ca35  cmp     al, [edx+3]
0x1004ca38  jz      short loc_1004CA41
0x1004ca3a  sbb     eax, eax
0x1004ca3c  or      eax, 1
0x1004ca3f  jmp     short loc_1004CA43
0x1004ca41  xor     eax, eax
0x1004ca43  cmp     [ebp+arg_0], 4
0x1004ca47  jnz     short loc_1004CA62
0x1004ca49  test    eax, eax
0x1004ca4b  js      short loc_1004CA55
0x1004ca4d  jz      short loc_1004CA55
0x1004ca4f  mov     edx, [esp+30h+var_24]
0x1004ca53  jmp     short loc_1004CA7E
0x1004ca55  mov     ecx, [esp+30h+var_20]
0x1004ca59  lea     edi, [ebx+4]
0x1004ca5c  mov     edx, [esp+30h+var_24]
0x1004ca60  jmp     short loc_1004CA84
0x1004ca62  mov     edx, [esp+30h+var_24]
0x1004ca66  test    eax, eax
0x1004ca68  jns     short loc_1004CA73
0x1004ca6a  mov     ecx, [esp+30h+var_20]
0x1004ca6e  lea     edi, [ebx+4]
0x1004ca71  jmp     short loc_1004CA84
0x1004ca73  xor     ecx, ecx
0x1004ca75  test    eax, eax
0x1004ca77  cmovz   edx, ecx
0x1004ca7a  mov     [esp+30h+var_24], edx
0x1004ca7e  mov     ecx, ebx
0x1004ca80  mov     [esp+30h+var_20], ecx
0x1004ca84  cmp     edi, ecx
0x1004ca86  jnz     loc_1004C9D0
0x1004ca8c  cmp     ecx, [esp+30h+var_C]
0x1004ca90  mov     ebx, [esp+30h+var_10]
0x1004ca94  mov     edi, [esp+30h+var_8]
0x1004ca98  cmovb   ebx, ecx
0x1004ca9b  mov     esi, [esp+30h+var_4]
0x1004ca9f  mov     eax, [ebp+arg_0]
0x1004caa2  mov     [edi+10h], ebx
0x1004caa5  cmp     eax, 5; switch 6 cases
0x1004caa8  ja      short def_1004CAAA; jumptable 1004CAAA default case, cases 1,4
0x1004caaa  jmp     ds:jpt_1004CAAA[eax*4]; switch jump
0x1004cab1  mov     ebx, [ebp+arg_4]; jumptable 1004CAAA case 0
0x1004cab4  cmp     edx, 1
0x1004cab7  jnz     short loc_1004CAD6
0x1004cab9  mov     eax, [esi+18h]
0x1004cabc  mov     [edi+10h], eax
0x1004cabf  jmp     short loc_1004CAD6
0x1004cac1  mov     eax, [esi+18h]; jumptable 1004CAAA case 2
0x1004cac4  cmp     ebx, eax
0x1004cac6  jz      short def_1004CAAA; jumptable 1004CAAA default case, cases 1,4
0x1004cac8  cmp     ebx, [esi+14h]
0x1004cacb  jbe     short loc_1004CAD0
0x1004cacd  lea     eax, [ebx-4]
0x1004cad0  mov     [edi+10h], eax
0x1004cad3  mov     ebx, [ebp+arg_4]; jumptable 1004CAAA default case, cases 1,4
0x1004cad6  mov     edx, [edi+0Ch]
0x1004cad9  mov     eax, [edi+10h]
0x1004cadc  cmp     eax, [edx+18h]
0x1004cadf  jnz     short loc_1004CB43
0x1004cae1  push    ecx
0x1004cae2  push    0FFFFF9BFh
0x1004cae7  mov     ecx, ebx
0x1004cae9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004caee  mov     dword ptr [edi+8], 1
0x1004caf5  pop     edi
0x1004caf6  pop     esi
0x1004caf7  pop     ebx
0x1004caf8  mov     esp, ebp
0x1004cafa  pop     ebp
0x1004cafb  retn    8
0x1004cafe  mov     ebx, [ebp+arg_4]; jumptable 1004CAAA case 3
0x1004cb01  cmp     edx, 1
0x1004cb04  jnz     short loc_1004CAD6
0x1004cb06  push    40Fh; int
0x1004cb0b  mov     ecx, ebx; this
0x1004cb0d  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1004cb12  mov     eax, [edi+0Ch]
0x1004cb15  mov     ecx, [edi+10h]
0x1004cb18  cmp     ecx, [eax+14h]
0x1004cb1b  jbe     short loc_1004CB25
0x1004cb1d  lea     eax, [ecx-4]
0x1004cb20  mov     [edi+10h], eax
0x1004cb23  jmp     short loc_1004CAD6
0x1004cb25  mov     eax, [eax+18h]
0x1004cb28  mov     [edi+10h], eax
0x1004cb2b  jmp     short loc_1004CAD6
0x1004cb2d  cmp     edx, 1; jumptable 1004CAAA case 5
0x1004cb30  jnz     short def_1004CAAA; jumptable 1004CAAA default case, cases 1,4
0x1004cb32  mov     ebx, [ebp+arg_4]
0x1004cb35  mov     ecx, ebx; this
0x1004cb37  push    40Fh; int
0x1004cb3c  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1004cb41  jmp     short loc_1004CAD6
0x1004cb43  mov     dword ptr [edi+8], 2
0x1004cb4a  pop     edi
0x1004cb4b  pop     esi
0x1004cb4c  pop     ebx
0x1004cb4d  mov     esp, ebp
0x1004cb4f  pop     ebp
0x1004cb50  retn    8
```
