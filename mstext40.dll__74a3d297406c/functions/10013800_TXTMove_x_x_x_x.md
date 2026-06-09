# TXTMove(x,x,x,x)

- ea: `0x10013800`
- end: `0x10013abf`
- name: `_TXTMove@16`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1000ed90`
- `0x1000fe70`
- `0x100133c0`
- `0x10013800`
- `0x10014460`
- `0x100168a0`
- `0x10016990`
- `0x1001f240`
- `0x1001f830`

## pseudocode

```c
int __stdcall TXTMove(int a1, int a2, int a3, char a4)
{
  int v4; // eax
  int v5; // esi
  int result; // eax
  int v7; // edi
  int v8; // ebx
  BOOL v9; // ebx
  char v10; // cl
  int v11; // eax
  char v12; // bl
  int v13; // ebp
  unsigned int v14; // ebp
  signed int i; // ebp
  signed int v16; // [esp+Ch] [ebp+8h]

  v4 = ISAMDBFindCursor(a1, a2);
  v5 = v4;
  if ( !v4 )
    return -1310;
  v7 = *(_DWORD *)(v4 + 4);
  if ( *(_DWORD *)(v7 + 904) == 2 && *(int *)(v7 + 864) > 0 )
    return -1001;
  if ( *(_DWORD *)(v7 + 880) != 1 || (result = CreateTableWithColumns((const wchar_t *)v7, v4)) == 0 )
  {
    switch ( a3 )
    {
      case 1:
        v8 = (a4 & 1) != 0 ? 6 : 0;
        break;
      case -1:
        v8 = 1;
        if ( (a4 & 1) != 0 )
          v8 = 7;
        break;
      case -2147483648:
        v8 = 2;
        break;
      case 2147483647:
        v8 = 3;
        break;
      default:
        v9 = (a4 & 1) != 0;
        if ( a3 >= 0 )
          v8 = 4 * v9 + 4;
        else
          v8 = 4 * v9 + 5;
        break;
    }
    if ( (a4 & 1) != 0 )
      return -1515;
    result = EstablishAsCurrentCursor(v5);
    if ( !result )
    {
      CopyBufferRelease(v5);
      ReadBufferClear(v5);
      *(_DWORD *)(v7 + 872) = v5;
      if ( !a3 )
      {
        result = -1603;
        if ( *(_BYTE *)(v5 + 29) == 2 )
          return 0;
        return result;
      }
      v10 = *(_BYTE *)(v5 + 29);
      if ( v10 == 4 && v8 != 2 && v8 != 3 )
        return -1603;
      if ( v10 == 1 && v8 == 1 )
        v8 = 3;
      if ( !v10 && !v8 )
        v8 = 2;
      switch ( v8 )
      {
        case 0:
          v11 = TextMove(*(_DWORD *)(v7 + 8), 1);
          if ( v11 )
            goto LABEL_69;
          ++*(_DWORD *)(v5 + 64);
          goto LABEL_41;
        case 1:
          v11 = TextMove(*(_DWORD *)(v7 + 8), 2);
          if ( v11 )
            goto LABEL_69;
          --*(_DWORD *)(v5 + 64);
          goto LABEL_41;
        case 2:
          v11 = TextMove(*(_DWORD *)(v7 + 8), 0);
          if ( v11 )
            goto LABEL_69;
          *(_DWORD *)(v5 + 64) = 1;
          goto LABEL_41;
        case 3:
          v13 = TableRecordCount(*(_DWORD *)(v5 + 4));
          v11 = TextMove(*(_DWORD *)(v7 + 8), 3);
          if ( v11 )
            goto LABEL_69;
          *(_DWORD *)(v5 + 64) = v13;
          goto LABEL_41;
        case 4:
        case 5:
          v14 = abs32(a3);
          v16 = v14;
          if ( !v14 )
            return 0;
          if ( v10 == 1 && v8 == 5 )
          {
            v11 = TextMove(*(_DWORD *)(v7 + 8), 3);
            if ( !v11 )
            {
              v16 = v14 - 1;
              *(_DWORD *)(v5 + 64) = TableRecordCount(*(_DWORD *)(v5 + 4));
              goto LABEL_61;
            }
            goto LABEL_69;
          }
          if ( !v10 && v8 == 4 )
          {
            v11 = TextMove(*(_DWORD *)(v7 + 8), 0);
            if ( v11 )
            {
LABEL_69:
              if ( v11 == -1603 )
                v12 = !v8 || v8 == 4;
              else
                v12 = 4;
LABEL_42:
              *(_BYTE *)(v5 + 29) = v12;
              result = -1603;
              if ( v12 == 2 )
                return 0;
              return result;
            }
            *(_DWORD *)(v5 + 64) = 1;
            v16 = v14 - 1;
          }
LABEL_61:
          for ( i = 0; i < v16; ++i )
          {
            if ( v8 == 5 )
            {
              v11 = TextMove(*(_DWORD *)(v7 + 8), 2);
              if ( v11 )
                goto LABEL_69;
              --*(_DWORD *)(v5 + 64);
            }
            else
            {
              v11 = TextMove(*(_DWORD *)(v7 + 8), 1);
              if ( v11 )
                goto LABEL_69;
              ++*(_DWORD *)(v5 + 64);
            }
          }
LABEL_41:
          v12 = 2;
          TextGetBookmark(*(_DWORD *)(*(_DWORD *)(v5 + 4) + 8), v5 + 32);
          goto LABEL_42;
        default:
          goto LABEL_41;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10013800  push    esi
0x10013801  push    [esp+4+arg_4]
0x10013805  push    [esp+8+arg_0]
0x10013809  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1001380e  mov     esi, eax
0x10013810  test    esi, esi
0x10013812  jnz     short loc_1001381D
0x10013814  mov     eax, 0FFFFFAE2h
0x10013819  pop     esi
0x1001381a  retn    10h
0x1001381d  push    edi
0x1001381e  mov     edi, [esi+4]
0x10013821  cmp     dword ptr [edi+388h], 2
0x10013828  jnz     short loc_1001383D
0x1001382a  cmp     dword ptr [edi+360h], 0
0x10013831  jle     short loc_1001383D
0x10013833  pop     edi
0x10013834  mov     eax, 0FFFFFC17h
0x10013839  pop     esi
0x1001383a  retn    10h
0x1001383d  cmp     dword ptr [edi+370h], 1
0x10013844  jnz     short loc_10013855
0x10013846  push    esi
0x10013847  push    edi
0x10013848  call    _CreateTableWithColumns@8; CreateTableWithColumns(x,x)
0x1001384d  test    eax, eax
0x1001384f  jnz     loc_1001399C
0x10013855  mov     ecx, [esp+8+arg_C]
0x10013859  push    ebx
0x1001385a  push    ebp
0x1001385b  mov     ebp, [esp+10h+arg_8]
0x1001385f  and     ecx, 0FFFFFFF1h
0x10013862  cmp     ebp, 1
0x10013865  jnz     short loc_10013877
0x10013867  mov     eax, ecx
0x10013869  and     al, 1
0x1001386b  movzx   ebx, al
0x1001386e  neg     ebx
0x10013870  sbb     ebx, ebx
0x10013872  and     ebx, 6
0x10013875  jmp     short loc_100138D1
0x10013877  cmp     ebp, 0FFFFFFFFh
0x1001387a  jnz     short loc_1001388E
0x1001387c  test    cl, 1
0x1001387f  mov     ebx, 1
0x10013884  mov     eax, 7
0x10013889  cmovnz  ebx, eax
0x1001388c  jmp     short loc_100138D1
0x1001388e  cmp     ebp, 80000000h
0x10013894  jnz     short loc_1001389D
0x10013896  mov     ebx, 2
0x1001389b  jmp     short loc_100138D1
0x1001389d  cmp     ebp, 7FFFFFFFh
0x100138a3  jnz     short loc_100138AC
0x100138a5  mov     ebx, 3
0x100138aa  jmp     short loc_100138D1
0x100138ac  mov     ebx, 0
0x100138b1  test    ebp, ebp
0x100138b3  jns     short loc_100138C4
0x100138b5  test    cl, 1
0x100138b8  setnz   bl
0x100138bb  lea     ebx, ds:5[ebx*4]
0x100138c2  jmp     short loc_100138D1
0x100138c4  test    cl, 1
0x100138c7  setnz   bl
0x100138ca  lea     ebx, ds:4[ebx*4]
0x100138d1  test    cl, 1
0x100138d4  jz      short loc_100138E2
0x100138d6  pop     ebp
0x100138d7  pop     ebx
0x100138d8  pop     edi
0x100138d9  mov     eax, 0FFFFFA15h
0x100138de  pop     esi
0x100138df  retn    10h
0x100138e2  push    esi
0x100138e3  call    _EstablishAsCurrentCursor@4; EstablishAsCurrentCursor(x)
0x100138e8  test    eax, eax
0x100138ea  jnz     loc_1001399A
0x100138f0  push    esi
0x100138f1  call    _CopyBufferRelease@4; CopyBufferRelease(x)
0x100138f6  push    esi
0x100138f7  call    _ReadBufferClear@4; ReadBufferClear(x)
0x100138fc  mov     [edi+368h], esi
0x10013902  test    ebp, ebp
0x10013904  jnz     short loc_1001391B
0x10013906  pop     ebp
0x10013907  xor     ecx, ecx
0x10013909  mov     eax, 0FFFFF9BDh
0x1001390e  cmp     byte ptr [esi+1Dh], 2
0x10013912  pop     ebx
0x10013913  pop     edi
0x10013914  cmovz   eax, ecx
0x10013917  pop     esi
0x10013918  retn    10h
0x1001391b  mov     cl, [esi+1Dh]
0x1001391e  cmp     cl, 4
0x10013921  jnz     short loc_10013939
0x10013923  cmp     ebx, 2
0x10013926  jz      short loc_10013939
0x10013928  cmp     ebx, 3
0x1001392b  jz      short loc_10013939
0x1001392d  pop     ebp
0x1001392e  pop     ebx
0x1001392f  pop     edi
0x10013930  mov     eax, 0FFFFF9BDh
0x10013935  pop     esi
0x10013936  retn    10h
0x10013939  cmp     cl, 1
0x1001393c  jnz     short loc_10013949
0x1001393e  cmp     ebx, 1
0x10013941  mov     eax, 3
0x10013946  cmovz   ebx, eax
0x10013949  test    cl, cl
0x1001394b  jnz     short loc_10013958
0x1001394d  test    ebx, ebx
0x1001394f  jnz     short loc_10013958
0x10013951  mov     ebx, 2
0x10013956  jmp     short loc_1001395D
0x10013958  cmp     ebx, 5; switch 6 cases
0x1001395b  ja      short def_1001395D; jumptable 1001395D default case
0x1001395d  jmp     ds:jpt_1001395D[ebx*4]; switch jump
0x10013964  push    1; jumptable 1001395D case 0
0x10013966  push    dword ptr [edi+8]
0x10013969  call    _TextMove@8; TextMove(x,x)
0x1001396e  test    eax, eax
0x10013970  jnz     loc_10013A9A
0x10013976  inc     dword ptr [esi+40h]
0x10013979  lea     eax, [esi+20h]; jumptable 1001395D default case
0x1001397c  mov     bl, 2
0x1001397e  push    eax
0x1001397f  mov     eax, [esi+4]
0x10013982  push    dword ptr [eax+8]
0x10013985  call    _TextGetBookmark@8; TextGetBookmark(x,x)
0x1001398a  xor     ecx, ecx
0x1001398c  mov     [esi+1Dh], bl
0x1001398f  cmp     bl, 2
0x10013992  mov     eax, 0FFFFF9BDh
0x10013997  cmovz   eax, ecx
0x1001399a  pop     ebp
0x1001399b  pop     ebx
0x1001399c  pop     edi
0x1001399d  pop     esi
0x1001399e  retn    10h
0x100139a1  push    2; jumptable 1001395D case 1
0x100139a3  push    dword ptr [edi+8]
0x100139a6  call    _TextMove@8; TextMove(x,x)
0x100139ab  test    eax, eax
0x100139ad  jnz     loc_10013A9A
0x100139b3  dec     dword ptr [esi+40h]
0x100139b6  jmp     short def_1001395D; jumptable 1001395D default case
0x100139b8  push    0; jumptable 1001395D case 2
0x100139ba  push    dword ptr [edi+8]
0x100139bd  call    _TextMove@8; TextMove(x,x)
0x100139c2  test    eax, eax
0x100139c4  jnz     loc_10013A9A
0x100139ca  mov     dword ptr [esi+40h], 1
0x100139d1  jmp     short def_1001395D; jumptable 1001395D default case
0x100139d3  push    dword ptr [esi+4]; jumptable 1001395D case 3
0x100139d6  call    _TableRecordCount@4; TableRecordCount(x)
0x100139db  push    3
0x100139dd  push    dword ptr [edi+8]
0x100139e0  mov     ebp, eax
0x100139e2  call    _TextMove@8; TextMove(x,x)
0x100139e7  test    eax, eax
0x100139e9  jnz     loc_10013A9A
0x100139ef  mov     [esi+40h], ebp
0x100139f2  jmp     short def_1001395D; jumptable 1001395D default case
0x100139f4  mov     eax, ebp; jumptable 1001395D cases 4,5
0x100139f6  cdq
0x100139f7  mov     ebp, eax
0x100139f9  xor     ebp, edx
0x100139fb  sub     ebp, edx
0x100139fd  mov     [esp+10h+arg_4], ebp
0x10013a01  jnz     short loc_10013A0C
0x10013a03  pop     ebp
0x10013a04  pop     ebx
0x10013a05  pop     edi
0x10013a06  xor     eax, eax
0x10013a08  pop     esi
0x10013a09  retn    10h
0x10013a0c  cmp     cl, 1
0x10013a0f  jnz     short loc_10013A36
0x10013a11  cmp     ebx, 5
0x10013a14  jnz     short loc_10013A36
0x10013a16  push    3
0x10013a18  push    dword ptr [edi+8]
0x10013a1b  call    _TextMove@8; TextMove(x,x)
0x10013a20  test    eax, eax
0x10013a22  jnz     short loc_10013A9A
0x10013a24  push    dword ptr [esi+4]
0x10013a27  dec     ebp
0x10013a28  mov     [esp+14h+arg_4], ebp
0x10013a2c  call    _TableRecordCount@4; TableRecordCount(x)
0x10013a31  mov     [esi+40h], eax
0x10013a34  jmp     short loc_10013A59
0x10013a36  test    cl, cl
0x10013a38  jnz     short loc_10013A59
0x10013a3a  cmp     ebx, 4
0x10013a3d  jnz     short loc_10013A59
0x10013a3f  push    0
0x10013a41  push    dword ptr [edi+8]
0x10013a44  call    _TextMove@8; TextMove(x,x)
0x10013a49  test    eax, eax
0x10013a4b  jnz     short loc_10013A9A
0x10013a4d  dec     ebp
0x10013a4e  mov     dword ptr [esi+40h], 1
0x10013a55  mov     [esp+10h+arg_4], ebp
0x10013a59  xor     ebp, ebp
0x10013a5b  cmp     [esp+10h+arg_4], ebp
0x10013a5f  jle     def_1001395D; jumptable 1001395D default case
0x10013a65  cmp     ebx, 5
0x10013a68  jnz     short loc_10013A7D
0x10013a6a  push    2
0x10013a6c  push    dword ptr [edi+8]
0x10013a6f  call    _TextMove@8; TextMove(x,x)
0x10013a74  test    eax, eax
0x10013a76  jnz     short loc_10013A9A
0x10013a78  dec     dword ptr [esi+40h]
0x10013a7b  jmp     short loc_10013A8E
0x10013a7d  push    1
0x10013a7f  push    dword ptr [edi+8]
0x10013a82  call    _TextMove@8; TextMove(x,x)
0x10013a87  test    eax, eax
0x10013a89  jnz     short loc_10013A9A
0x10013a8b  inc     dword ptr [esi+40h]
0x10013a8e  inc     ebp
0x10013a8f  cmp     ebp, [esp+10h+arg_4]
0x10013a93  jl      short loc_10013A65
0x10013a95  jmp     def_1001395D; jumptable 1001395D default case
0x10013a9a  cmp     eax, 0FFFFF9BDh
0x10013a9f  jnz     short loc_10013AB8
0x10013aa1  test    ebx, ebx
0x10013aa3  jz      short loc_10013AB1
0x10013aa5  cmp     ebx, 4
0x10013aa8  jz      short loc_10013AB1
0x10013aaa  xor     bl, bl
0x10013aac  jmp     loc_1001398A
0x10013ab1  mov     bl, 1
0x10013ab3  jmp     loc_1001398A
0x10013ab8  mov     bl, 4
0x10013aba  jmp     loc_1001398A
```
