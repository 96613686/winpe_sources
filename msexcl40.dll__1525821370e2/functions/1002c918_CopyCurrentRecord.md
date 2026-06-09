# CopyCurrentRecord

- ea: `0x1002c918`
- end: `0x1002cbbe`
- name: `CopyCurrentRecord`
- size: `678`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x1002cc39`
- `0x1002cd40`

## callees

- `0x1002c918`
- `0x10031f44`
- `0x10031fb7`
- `0x10032050`
- `0x10032097`
- `0x100320e5`
- `0x1003213a`
- `0x100321bc`
- `0x10032387`
- `0x10032468`
- `0x1003250c`
- `0x1003257a`
- `0x10032602`

## pseudocode

```c
int __thiscall CopyCurrentRecord(_DWORD *this)
{
  int v1; // esi
  int v2; // eax
  int v3; // ebx
  int v4; // ecx
  bool v5; // zf
  int result; // eax
  int i; // edi
  int v8; // edx
  int Bool; // ecx
  bool v10; // sf
  wchar_t *v11; // ebx
  __int16 v12; // ax
  wchar_t *j; // eax
  int v14; // eax
  int v15; // eax
  wchar_t *v16; // esi
  int v17; // eax
  __int64 v18; // [esp+10h] [ebp-30h] BYREF
  _DWORD *v19; // [esp+1Ch] [ebp-24h]
  int v20; // [esp+20h] [ebp-20h]
  wchar_t *v21; // [esp+24h] [ebp-1Ch] BYREF
  int v22; // [esp+28h] [ebp-18h] BYREF
  int v23; // [esp+2Ch] [ebp-14h]
  int v24; // [esp+30h] [ebp-10h]
  wchar_t *v25; // [esp+34h] [ebp-Ch]
  int v26; // [esp+38h] [ebp-8h] BYREF
  __int16 v27; // [esp+3Ch] [ebp-4h] BYREF

  v1 = (int)this;
  v19 = this;
  v2 = this[1];
  v3 = 0;
  v4 = 2;
  v20 = 0;
  v23 = 0;
  v5 = *(_DWORD *)(v2 + 28) == 0;
  v25 = 0;
  if ( !v5 )
    v4 = 0;
  v5 = *(_BYTE *)(v1 + 29) == 2;
  v24 = v4;
  if ( !v5 )
    return -1603;
  CopyBufferClear(v1);
  for ( i = *(_DWORD *)(*(_DWORD *)(v1 + 4) + 40); ; i = *(_DWORD *)i )
  {
    if ( !i )
    {
      *(_DWORD *)(v1 + 36) = v23;
      return 0;
    }
    result = CellStatus(&v26, &v27, v24);
    if ( result < 0 )
      return result;
    v8 = 0;
    Bool = 0;
    if ( !result )
    {
      switch ( *(_DWORD *)(i + 16) )
      {
        case 1:
          Bool = RecordGetBool(&v26, &v22, v24);
          v10 = Bool < 0;
          if ( Bool )
            goto LABEL_44;
          v25 = (wchar_t *)&v22;
          v3 = 1;
          v14 = CopyPutBool(v26, v22);
          break;
        case 5:
          Bool = RecordGetDouble(&v26, &v18, v24);
          v10 = Bool < 0;
          if ( Bool )
            goto LABEL_44;
          v3 = 8;
          v25 = (wchar_t *)&v18;
          v15 = PutDouble(v26);
          if ( v15 )
          {
            *(_WORD *)(v15 + 8) |= 0x20u;
            Bool = 0;
          }
          else
          {
            Bool = -1011;
          }
          goto LABEL_34;
        case 7:
          Bool = RecordGetDouble(&v26, &v18, v24);
          v10 = Bool < 0;
          if ( Bool )
            goto LABEL_44;
          v3 = 8;
          v25 = (wchar_t *)&v18;
          Bool = PutDouble(v26) != 0 ? 0 : -1011;
          goto LABEL_34;
        case 8:
          Bool = RecordGetDate(&v26, &v18, v24);
          v10 = Bool < 0;
          if ( Bool )
            goto LABEL_44;
          v3 = 8;
          v25 = (wchar_t *)&v18;
          v14 = CopyPutDate(v26);
          break;
        default:
          if ( *(_DWORD *)(i + 16) != 10 )
          {
            if ( *(_DWORD *)(i + 16) == 11 )
            {
              v3 = 0;
              goto LABEL_45;
            }
            if ( *(_DWORD *)(i + 16) != 12 )
            {
LABEL_36:
              if ( v3 <= 0 )
                goto LABEL_45;
              v16 = v25;
              do
              {
                v23 += *(unsigned __int8 *)v16;
                v16 = (wchar_t *)((char *)v16 + 1);
                ++v8;
              }
              while ( v8 < v3 );
              v25 = v16;
              v1 = (int)v19;
              goto LABEL_43;
            }
          }
          Bool = RecordGetAlpha(v1, i, &v26, &v21, v24);
          v10 = Bool < 0;
          if ( Bool )
            goto LABEL_44;
          v11 = v21;
          v25 = v21;
          do
            v12 = *v11++;
          while ( v12 != (_WORD)v20 );
          v3 = v11 - (v21 + 1);
          for ( j = &v21[v3 - 1]; j >= v21; --v3 )
          {
            if ( *j != 32 )
              break;
            --j;
          }
          v14 = CopyPutAlpha(v1, i, v26, (char *)v21, 2 * v3);
          break;
      }
      Bool = v14;
LABEL_34:
      v10 = Bool < 0;
      if ( Bool )
        goto LABEL_44;
      v8 = 0;
      goto LABEL_36;
    }
    if ( !v26 && (v27 & 0x100) == 0 )
      goto LABEL_45;
    Bool = CopyPutBlank(v26);
LABEL_43:
    v10 = Bool < 0;
LABEL_44:
    if ( v10 )
      break;
LABEL_45:
    LOWORD(v8) = *(_WORD *)(i + 28);
    v17 = CopyBufferCellForCol(*(_DWORD *)(v1 + 40), v8);
    if ( v17 )
      *(_WORD *)(v17 + 8) = v27;
  }
  return Bool;
}

```

## disassembly

```asm
0x1002c918  mov     edi, edi
0x1002c91a  push    ebp
0x1002c91b  mov     ebp, esp
0x1002c91d  sub     esp, 34h
0x1002c920  push    ebx
0x1002c921  push    esi
0x1002c922  mov     esi, ecx
0x1002c924  xor     edx, edx
0x1002c926  push    edi
0x1002c927  xor     edi, edi
0x1002c929  mov     [ebp+var_24], esi
0x1002c92c  push    2
0x1002c92e  mov     eax, [esi+4]
0x1002c931  mov     ebx, edi
0x1002c933  pop     ecx
0x1002c934  mov     [ebp+var_20], edi
0x1002c937  mov     [ebp+var_14], edi
0x1002c93a  cmp     [eax+1Ch], edi
0x1002c93d  mov     [ebp+var_C], edi
0x1002c940  cmovnz  ecx, edx
0x1002c943  cmp     byte ptr [esi+1Dh], 2
0x1002c947  mov     [ebp+var_10], ecx
0x1002c94a  jz      short loc_1002C956
0x1002c94c  mov     eax, 0FFFFF9BDh
0x1002c951  jmp     loc_1002CBB5
0x1002c956  mov     ecx, esi
0x1002c958  call    _CopyBufferClear@4; CopyBufferClear(x)
0x1002c95d  mov     eax, [esi+4]
0x1002c960  mov     edi, [eax+28h]
0x1002c963  jmp     loc_1002CBA5
0x1002c968  push    [ebp+var_10]
0x1002c96b  lea     eax, [ebp+var_4]
0x1002c96e  mov     edx, edi
0x1002c970  push    eax
0x1002c971  lea     eax, [ebp+var_8]
0x1002c974  mov     ecx, esi
0x1002c976  push    eax
0x1002c977  call    _CellStatus@20; CellStatus(x,x,x,x,x)
0x1002c97c  test    eax, eax
0x1002c97e  js      loc_1002CBB5
0x1002c984  xor     edx, edx
0x1002c986  mov     ecx, edx
0x1002c988  test    eax, eax
0x1002c98a  jnz     loc_1002CB69
0x1002c990  mov     eax, [edi+10h]
0x1002c993  sub     eax, 1
0x1002c996  jz      loc_1002CB14
0x1002c99c  sub     eax, 4
0x1002c99f  jz      loc_1002CAC6
0x1002c9a5  dec     eax
0x1002c9a6  sub     eax, 1
0x1002c9a9  jz      loc_1002CA79
0x1002c9af  sub     eax, 1
0x1002c9b2  jz      loc_1002CA3C
0x1002c9b8  dec     eax
0x1002c9b9  sub     eax, 1
0x1002c9bc  jz      short loc_1002C9CC
0x1002c9be  sub     eax, 1
0x1002c9c1  jz      short loc_1002CA35
0x1002c9c3  sub     eax, 1
0x1002c9c6  jnz     loc_1002CB4E
0x1002c9cc  push    [ebp+var_10]
0x1002c9cf  lea     eax, [ebp+var_1C]
0x1002c9d2  mov     edx, edi
0x1002c9d4  push    eax
0x1002c9d5  lea     eax, [ebp+var_8]
0x1002c9d8  mov     ecx, esi
0x1002c9da  push    eax
0x1002c9db  call    _RecordGetAlpha@20; RecordGetAlpha(x,x,x,x,x)
0x1002c9e0  mov     ecx, eax
0x1002c9e2  test    ecx, ecx
0x1002c9e4  jnz     loc_1002CB89
0x1002c9ea  mov     ecx, [ebp+var_1C]
0x1002c9ed  mov     ebx, ecx
0x1002c9ef  mov     [ebp+var_C], ecx
0x1002c9f2  lea     edx, [ebx+2]
0x1002c9f5  mov     ax, [ebx]
0x1002c9f8  add     ebx, 2
0x1002c9fb  cmp     ax, word ptr [ebp+var_20]
0x1002c9ff  jnz     short loc_1002C9F5
0x1002ca01  sub     ebx, edx
0x1002ca03  lea     eax, [ecx-2]
0x1002ca06  sar     ebx, 1
0x1002ca08  lea     eax, [eax+ebx*2]
0x1002ca0b  cmp     eax, ecx
0x1002ca0d  jb      short loc_1002CA1F
0x1002ca0f  push    20h ; ' '
0x1002ca11  pop     edx
0x1002ca12  cmp     [eax], dx
0x1002ca15  jnz     short loc_1002CA1F
0x1002ca17  sub     eax, 2
0x1002ca1a  dec     ebx
0x1002ca1b  cmp     eax, ecx
0x1002ca1d  jnb     short loc_1002CA12
0x1002ca1f  lea     eax, [ebx+ebx]
0x1002ca22  mov     edx, edi
0x1002ca24  push    eax
0x1002ca25  push    ecx
0x1002ca26  push    [ebp+var_8]
0x1002ca29  mov     ecx, esi
0x1002ca2b  call    _CopyPutAlpha@20; CopyPutAlpha(x,x,x,x,x)
0x1002ca30  jmp     loc_1002CB46
0x1002ca35  mov     ebx, edx
0x1002ca37  jmp     loc_1002CB8B
0x1002ca3c  push    [ebp+var_10]
0x1002ca3f  lea     eax, [ebp+var_30]
0x1002ca42  mov     edx, edi
0x1002ca44  push    eax
0x1002ca45  lea     eax, [ebp+var_8]
0x1002ca48  mov     ecx, esi
0x1002ca4a  push    eax
0x1002ca4b  call    _RecordGetDate@20; RecordGetDate(x,x,x,x,x)
0x1002ca50  mov     ecx, eax
0x1002ca52  test    ecx, ecx
0x1002ca54  jnz     loc_1002CB89
0x1002ca5a  movsd   xmm3, [ebp+var_30]
0x1002ca5f  lea     eax, [ebp+var_30]
0x1002ca62  push    8
0x1002ca64  pop     ebx
0x1002ca65  push    [ebp+var_8]
0x1002ca68  mov     edx, edi
0x1002ca6a  mov     [ebp+var_C], eax
0x1002ca6d  mov     ecx, esi
0x1002ca6f  call    _CopyPutDate@20; CopyPutDate(x,x,x,x,x)
0x1002ca74  jmp     loc_1002CB46
0x1002ca79  push    [ebp+var_10]
0x1002ca7c  lea     eax, [ebp+var_30]
0x1002ca7f  mov     edx, edi
0x1002ca81  push    eax
0x1002ca82  lea     eax, [ebp+var_8]
0x1002ca85  mov     ecx, esi
0x1002ca87  push    eax
0x1002ca88  call    _RecordGetDouble@20; RecordGetDouble(x,x,x,x,x)
0x1002ca8d  mov     ecx, eax
0x1002ca8f  test    ecx, ecx
0x1002ca91  jnz     loc_1002CB89
0x1002ca97  movsd   xmm3, [ebp+var_30]
0x1002ca9c  lea     eax, [ebp+var_30]
0x1002ca9f  push    8
0x1002caa1  pop     ebx
0x1002caa2  push    [ebp+var_8]
0x1002caa5  mov     edx, edi
0x1002caa7  mov     [ebp+var_C], eax
0x1002caaa  mov     ecx, esi
0x1002caac  call    PutDouble
0x1002cab1  neg     eax
0x1002cab3  sbb     ecx, ecx
0x1002cab5  and     ecx, 3F3h
0x1002cabb  add     ecx, 0FFFFFC0Dh
0x1002cac1  jmp     loc_1002CB48
0x1002cac6  push    [ebp+var_10]
0x1002cac9  lea     eax, [ebp+var_30]
0x1002cacc  mov     edx, edi
0x1002cace  push    eax
0x1002cacf  lea     eax, [ebp+var_8]
0x1002cad2  mov     ecx, esi
0x1002cad4  push    eax
0x1002cad5  call    _RecordGetDouble@20; RecordGetDouble(x,x,x,x,x)
0x1002cada  mov     ecx, eax
0x1002cadc  test    ecx, ecx
0x1002cade  jnz     loc_1002CB89
0x1002cae4  movsd   xmm3, [ebp+var_30]
0x1002cae9  lea     eax, [ebp+var_30]
0x1002caec  push    8
0x1002caee  pop     ebx
0x1002caef  push    [ebp+var_8]
0x1002caf2  mov     edx, edi
0x1002caf4  mov     [ebp+var_C], eax
0x1002caf7  mov     ecx, esi
0x1002caf9  call    PutDouble
0x1002cafe  test    eax, eax
0x1002cb00  jnz     short loc_1002CB09
0x1002cb02  mov     ecx, 0FFFFFC0Dh
0x1002cb07  jmp     short loc_1002CB48
0x1002cb09  push    20h ; ' '
0x1002cb0b  pop     ecx
0x1002cb0c  or      [eax+8], cx
0x1002cb10  xor     ecx, ecx
0x1002cb12  jmp     short loc_1002CB48
0x1002cb14  push    [ebp+var_10]
0x1002cb17  lea     eax, [ebp+var_18]
0x1002cb1a  mov     edx, edi
0x1002cb1c  push    eax
0x1002cb1d  lea     eax, [ebp+var_8]
0x1002cb20  mov     ecx, esi
0x1002cb22  push    eax
0x1002cb23  call    _RecordGetBool@20; RecordGetBool(x,x,x,x,x)
0x1002cb28  mov     ecx, eax
0x1002cb2a  test    ecx, ecx
0x1002cb2c  jnz     short loc_1002CB89
0x1002cb2e  push    [ebp+var_18]
0x1002cb31  lea     eax, [ebp+var_18]
0x1002cb34  xor     ebx, ebx
0x1002cb36  push    [ebp+var_8]
0x1002cb39  mov     edx, edi
0x1002cb3b  mov     [ebp+var_C], eax
0x1002cb3e  mov     ecx, esi
0x1002cb40  inc     ebx
0x1002cb41  call    _CopyPutBool@16; CopyPutBool(x,x,x,x)
0x1002cb46  mov     ecx, eax
0x1002cb48  test    ecx, ecx
0x1002cb4a  jnz     short loc_1002CB89
0x1002cb4c  xor     edx, edx
0x1002cb4e  test    ebx, ebx
0x1002cb50  jle     short loc_1002CB8B
0x1002cb52  mov     esi, [ebp+var_C]
0x1002cb55  movzx   eax, byte ptr [esi]
0x1002cb58  add     [ebp+var_14], eax
0x1002cb5b  inc     esi
0x1002cb5c  inc     edx
0x1002cb5d  cmp     edx, ebx
0x1002cb5f  jl      short loc_1002CB55
0x1002cb61  mov     [ebp+var_C], esi
0x1002cb64  mov     esi, [ebp+var_24]
0x1002cb67  jmp     short loc_1002CB87
0x1002cb69  cmp     [ebp+var_8], ecx
0x1002cb6c  jnz     short loc_1002CB79
0x1002cb6e  mov     eax, 100h
0x1002cb73  test    [ebp+var_4], ax
0x1002cb77  jz      short loc_1002CB8B
0x1002cb79  push    [ebp+var_8]
0x1002cb7c  mov     edx, edi
0x1002cb7e  mov     ecx, esi
0x1002cb80  call    _CopyPutBlank@12; CopyPutBlank(x,x,x)
0x1002cb85  mov     ecx, eax
0x1002cb87  test    ecx, ecx
0x1002cb89  js      short loc_1002CBBA
0x1002cb8b  mov     dx, [edi+1Ch]
0x1002cb8f  mov     ecx, [esi+28h]
0x1002cb92  call    _CopyBufferCellForCol@8; CopyBufferCellForCol(x,x)
0x1002cb97  test    eax, eax
0x1002cb99  jz      short loc_1002CBA3
0x1002cb9b  mov     cx, [ebp+var_4]
0x1002cb9f  mov     [eax+8], cx
0x1002cba3  mov     edi, [edi]
0x1002cba5  test    edi, edi
0x1002cba7  jnz     loc_1002C968
0x1002cbad  mov     eax, [ebp+var_14]
0x1002cbb0  mov     [esi+24h], eax
0x1002cbb3  xor     eax, eax
0x1002cbb5  pop     edi
0x1002cbb6  pop     esi
0x1002cbb7  pop     ebx
0x1002cbb8  leave
0x1002cbb9  retn
0x1002cbba  mov     eax, ecx
0x1002cbbc  jmp     short loc_1002CBB5
```
