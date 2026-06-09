# OpenFilePlySetup

- ea: `0x100102c0`
- end: `0x100106f7`
- name: `OpenFilePlySetup`
- size: `1079`
- prototype: `int __fastcall(int, int, __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x10010790`

## callees

- `0x1000dcc0`
- `0x1000df70`
- `0x100102c0`
- `0x10025f86`

## pseudocode

```c
int __fastcall OpenFilePlySetup(int a1, int a2, __int16 a3)
{
  int v6; // ecx
  int v7; // ecx
  int v8; // edx
  int v9; // eax
  __int16 v10; // di
  __int16 v11; // cx
  __int16 v12; // cx
  __int16 v13; // cx
  __int16 v14; // ax
  __int16 v15; // cx
  int v16; // ecx
  int v17; // [esp+14h] [ebp-18h]
  __int16 v18; // [esp+18h] [ebp-14h]
  __int16 v19; // [esp+1Ch] [ebp-10h]
  __int16 v20; // [esp+1Ch] [ebp-10h]
  __int16 v21; // [esp+20h] [ebp-Ch]
  int v22; // [esp+20h] [ebp-Ch]
  __int16 *v23; // [esp+24h] [ebp-8h] BYREF
  __int16 v24; // [esp+28h] [ebp-4h] BYREF
  __int16 v25; // [esp+2Ah] [ebp-2h]

  if ( *(_DWORD *)(a2 + 32) )
    return 0;
  BFSetFilePosition(*(int **)(a1 + 20), 0, *(_DWORD *)(a2 + 4));
  if ( ExcelReadRecordHeader(a1, &v24) )
    return -10;
  if ( v24 != 9 && v24 != 521 && v24 != 1033 && v24 != 2057 )
    return -13;
  v6 = *(_DWORD *)(a1 + 40);
  if ( v6 )
    *(_DWORD *)(v6 + 8) = **(_DWORD **)(v6 + 8);
  else
    BFSetFilePosition(*(int **)(a1 + 20), 1, v25);
  *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                       + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                       - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
  while ( 1 )
  {
    v7 = ExcelReadRecordHeader(a1, &v24);
    if ( v7 )
      return v7;
    switch ( v24 )
    {
      case 47:
        return -12;
      case 129:
        v7 = ExcelReadTotalRecord(a1, &v24, &v23);
        if ( v7 )
          return v7;
        if ( (*(_BYTE *)v23 & 0x10) != 0 )
        {
          *(_DWORD *)(a2 + 24) = 0;
          *(_DWORD *)(a2 + 28) = 0;
          return 0;
        }
LABEL_34:
        *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                             + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                             - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        break;
      case 523:
        v7 = ExcelReadTotalRecord(a1, &v24, &v23);
        if ( v7 )
          return v7;
        if ( *(int *)(a1 + 4) >= 8 )
        {
          v8 = *((_DWORD *)v23 + 1);
          v9 = *((_DWORD *)v23 + 2);
        }
        else
        {
          v8 = v23[2];
          v9 = v23[3];
        }
        *(_WORD *)(a2 + 26) = 0;
        *(_WORD *)(a2 + 30) = 0;
        if ( v8 == v9 )
        {
          *(_WORD *)(a2 + 24) = 0;
          *(_WORD *)(a2 + 28) = 0;
          *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                               + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                               - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        }
        else
        {
          *(_WORD *)(a2 + 24) = v8;
          *(_WORD *)(a2 + 28) = v9 - 1;
          if ( (a3 & 0x800) != 0 )
            goto LABEL_34;
          *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 88);
          *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                               + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                               - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        }
        break;
      case 512:
        v7 = ExcelReadTotalRecord(a1, &v24, &v23);
        if ( v7 )
          return v7;
        if ( *(int *)(a1 + 4) < 8 )
        {
          v19 = *v23;
          v21 = v23[1];
          v10 = v23[2];
          v11 = v23[3];
          if ( *v23 == v21 )
          {
            *(_DWORD *)(a2 + 24) = 0;
            *(_DWORD *)(a2 + 28) = 0;
          }
          else
          {
            *(_WORD *)(a2 + 24) = *v23;
            v12 = v11 - 1;
            *(_WORD *)(a2 + 26) = v10;
            *(_WORD *)(a2 + 30) = v12;
            *(_WORD *)(a2 + 28) = v21 - 1;
            if ( !v19 && v21 == 1 && !v10 && !v12 )
              *(_WORD *)(a2 + 28) = v21;
          }
          goto LABEL_34;
        }
        v13 = v23[5];
        v22 = *(_DWORD *)v23;
        v17 = *((_DWORD *)v23 + 1);
        v20 = v23[4];
        v18 = v13;
        if ( *(_DWORD *)v23 == v17 )
        {
          *(_DWORD *)(a2 + 24) = 0;
          *(_DWORD *)(a2 + 28) = 1;
          *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                               + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                               - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        }
        else
        {
          *(_WORD *)(a2 + 26) = v23[4];
          v14 = v13 - 1;
          v15 = 0;
          if ( v20 != v18 )
            v15 = v14;
          *(_WORD *)(a2 + 24) = v22;
          *(_WORD *)(a2 + 28) = v17 - 1;
          *(_WORD *)(a2 + 30) = v15;
          if ( (_WORD)v22 || (_WORD)v17 != 1 || v20 || v15 )
            goto LABEL_34;
          *(_WORD *)(a2 + 28) = 1;
          *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                               + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                               - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        }
        break;
      case 10:
      case 516:
      case 638:
      case 515:
      case 189:
      case 190:
      case 513:
      case 517:
      case 214:
      case 253:
      case 518:
      case 1030:
      case 6:
      case 519:
      case 545:
      case 1212:
        return v7;
      default:
        v16 = *(_DWORD *)(a1 + 40);
        if ( v16 )
          *(_DWORD *)(v16 + 8) = **(_DWORD **)(v16 + 8);
        else
          BFSetFilePosition(*(int **)(a1 + 20), 1, v25);
        *(_DWORD *)(a1 + 88) = *(_DWORD *)(*(_DWORD *)(a1 + 20) + 8)
                             + *(_DWORD *)(*(_DWORD *)(a1 + 20) + 84)
                             - *(_DWORD *)(*(_DWORD *)(a1 + 20) + 4);
        break;
    }
  }
}

```

## disassembly

```asm
0x100102c0  mov     edi, edi
0x100102c2  push    ebp
0x100102c3  mov     ebp, esp
0x100102c5  sub     esp, 20h
0x100102c8  push    ebx
0x100102c9  push    esi
0x100102ca  mov     esi, edx
0x100102cc  mov     ebx, ecx
0x100102ce  push    edi
0x100102cf  cmp     dword ptr [esi+20h], 0
0x100102d3  jz      short loc_100102E0
0x100102d5  xor     eax, eax
0x100102d7  pop     edi
0x100102d8  pop     esi
0x100102d9  pop     ebx
0x100102da  mov     esp, ebp
0x100102dc  pop     ebp
0x100102dd  retn    4
0x100102e0  push    dword ptr [esi+4]
0x100102e3  mov     ecx, [ebx+14h]
0x100102e6  xor     edx, edx
0x100102e8  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x100102ed  lea     edx, [ebp+var_4]
0x100102f0  mov     ecx, ebx
0x100102f2  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x100102f7  test    eax, eax
0x100102f9  jz      short loc_10010309
0x100102fb  mov     eax, 0FFFFFFF6h
0x10010300  pop     edi
0x10010301  pop     esi
0x10010302  pop     ebx
0x10010303  mov     esp, ebp
0x10010305  pop     ebp
0x10010306  retn    4
0x10010309  mov     eax, [ebp+var_4]
0x1001030c  cmp     ax, 9
0x10010310  jz      short loc_1001033E
0x10010312  mov     ecx, 209h
0x10010317  cmp     ax, cx
0x1001031a  jz      short loc_1001033E
0x1001031c  mov     ecx, 409h
0x10010321  cmp     ax, cx
0x10010324  jz      short loc_1001033E
0x10010326  mov     ecx, 809h
0x1001032b  cmp     ax, cx
0x1001032e  jz      short loc_1001033E
0x10010330  mov     eax, 0FFFFFFF3h
0x10010335  pop     edi
0x10010336  pop     esi
0x10010337  pop     ebx
0x10010338  mov     esp, ebp
0x1001033a  pop     ebp
0x1001033b  retn    4
0x1001033e  mov     ecx, [ebx+28h]
0x10010341  mov     edi, 1
0x10010346  test    ecx, ecx
0x10010348  jz      short loc_10010354
0x1001034a  mov     eax, [ecx+8]
0x1001034d  mov     eax, [eax]
0x1001034f  mov     [ecx+8], eax
0x10010352  jmp     short loc_10010363
0x10010354  movsx   eax, word ptr [ebp+var_4+2]
0x10010358  mov     edx, edi
0x1001035a  mov     ecx, [ebx+14h]
0x1001035d  push    eax
0x1001035e  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10010363  mov     ecx, [ebx+14h]
0x10010366  mov     eax, [ecx+54h]
0x10010369  sub     eax, [ecx+4]
0x1001036c  add     eax, [ecx+8]
0x1001036f  mov     [ebx+58h], eax
0x10010372  lea     edx, [ebp+var_4]
0x10010375  mov     ecx, ebx
0x10010377  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x1001037c  mov     ecx, eax
0x1001037e  test    ecx, ecx
0x10010380  jnz     loc_100106EC
0x10010386  mov     eax, [ebp+var_4]
0x10010389  mov     edx, 81h
0x1001038e  cmp     ax, 2Fh ; '/'
0x10010392  jz      loc_100106E7
0x10010398  cmp     ax, dx
0x1001039b  jnz     short loc_100103D4
0x1001039d  lea     eax, [ebp+var_8]
0x100103a0  mov     ecx, ebx
0x100103a2  push    eax
0x100103a3  lea     edx, [ebp+var_4]
0x100103a6  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100103ab  mov     ecx, eax
0x100103ad  test    ecx, ecx
0x100103af  jnz     loc_100106EC
0x100103b5  mov     eax, [ebp+var_8]
0x100103b8  test    byte ptr [eax], 10h
0x100103bb  jz      loc_100104CB
0x100103c1  xor     eax, eax
0x100103c3  mov     [esi+18h], eax
0x100103c6  mov     [esi+1Ch], eax
0x100103c9  mov     eax, ecx
0x100103cb  pop     edi
0x100103cc  pop     esi
0x100103cd  pop     ebx
0x100103ce  mov     esp, ebp
0x100103d0  pop     ebp
0x100103d1  retn    4
0x100103d4  mov     edx, 20Bh
0x100103d9  cmp     ax, dx
0x100103dc  jnz     loc_10010471
0x100103e2  lea     eax, [ebp+var_8]
0x100103e5  mov     ecx, ebx
0x100103e7  push    eax
0x100103e8  lea     edx, [ebp+var_4]
0x100103eb  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x100103f0  mov     ecx, eax
0x100103f2  test    ecx, ecx
0x100103f4  jnz     loc_100106EC
0x100103fa  cmp     dword ptr [ebx+4], 8
0x100103fe  mov     eax, [ebp+var_8]
0x10010401  jge     short loc_1001040D
0x10010403  movsx   edx, word ptr [eax+4]
0x10010407  movsx   eax, word ptr [eax+6]
0x1001040b  jmp     short loc_10010413
0x1001040d  mov     edx, [eax+4]
0x10010410  mov     eax, [eax+8]
0x10010413  xor     ecx, ecx
0x10010415  mov     [esi+1Ah], cx
0x10010419  mov     [esi+1Eh], cx
0x1001041d  cmp     edx, eax
0x1001041f  jnz     short loc_1001043F
0x10010421  xor     eax, eax
0x10010423  mov     [esi+18h], ax
0x10010427  mov     [esi+1Ch], ax
0x1001042b  mov     eax, [ebx+14h]
0x1001042e  mov     ecx, [eax+54h]
0x10010431  sub     ecx, [eax+4]
0x10010434  add     ecx, [eax+8]
0x10010437  mov     [ebx+58h], ecx
0x1001043a  jmp     loc_10010372
0x1001043f  dec     eax
0x10010440  test    [ebp+arg_0], 800h
0x10010447  movzx   ecx, ax
0x1001044a  movzx   eax, dx
0x1001044d  mov     [esi+18h], ax
0x10010451  mov     [esi+1Ch], cx
0x10010455  jnz     short loc_100104CB
0x10010457  mov     eax, [ebx+58h]
0x1001045a  mov     [esi+10h], eax
0x1001045d  mov     eax, [ebx+14h]
0x10010460  mov     ecx, [eax+54h]
0x10010463  sub     ecx, [eax+4]
0x10010466  add     ecx, [eax+8]
0x10010469  mov     [ebx+58h], ecx
0x1001046c  jmp     loc_10010372
0x10010471  mov     edx, 200h
0x10010476  cmp     ax, dx
0x10010479  jnz     loc_100105E1
0x1001047f  lea     eax, [ebp+var_8]
0x10010482  mov     ecx, ebx
0x10010484  push    eax
0x10010485  lea     edx, [ebp+var_4]
0x10010488  call    _ExcelReadTotalRecord@12; ExcelReadTotalRecord(x,x,x)
0x1001048d  mov     ecx, eax
0x1001048f  test    ecx, ecx
0x10010491  jnz     loc_100106EC
0x10010497  cmp     dword ptr [ebx+4], 8
0x1001049b  mov     ecx, [ebp+var_8]
0x1001049e  jge     short loc_10010512
0x100104a0  movzx   edx, word ptr [ecx]
0x100104a3  mov     eax, edx
0x100104a5  mov     [ebp+var_10], eax
0x100104a8  movzx   eax, word ptr [ecx+2]
0x100104ac  mov     edi, eax
0x100104ae  mov     [ebp+var_C], edi
0x100104b1  movzx   edi, word ptr [ecx+4]
0x100104b5  movzx   ecx, word ptr [ecx+6]
0x100104b9  cmp     dx, ax
0x100104bc  jnz     short loc_100104DF
0x100104be  xor     eax, eax
0x100104c0  mov     [esi+18h], eax
0x100104c3  mov     [esi+1Ch], eax
0x100104c6  mov     edi, 1
0x100104cb  mov     eax, [ebx+14h]
0x100104ce  mov     ecx, [eax+54h]
0x100104d1  sub     ecx, [eax+4]
0x100104d4  add     ecx, [eax+8]
0x100104d7  mov     [ebx+58h], ecx
0x100104da  jmp     loc_10010372
0x100104df  mov     [esi+18h], dx
0x100104e3  dec     ecx
0x100104e4  cmp     word ptr [ebp+var_10], 0
0x100104e9  mov     edx, [ebp+var_C]
0x100104ec  mov     [esi+1Ah], di
0x100104f0  mov     [esi+1Eh], cx
0x100104f4  lea     eax, [edx-1]
0x100104f7  mov     [esi+1Ch], ax
0x100104fb  jnz     short loc_100104C6
0x100104fd  test    ax, ax
0x10010500  jnz     short loc_100104C6
0x10010502  test    di, di
0x10010505  jnz     short loc_100104C6
0x10010507  test    cx, cx
0x1001050a  jnz     short loc_100104C6
0x1001050c  mov     [esi+1Ch], dx
0x10010510  jmp     short loc_100104C6
0x10010512  mov     edx, [ecx]
0x10010514  mov     edi, [ecx+4]
0x10010517  movzx   eax, word ptr [ecx+8]
0x1001051b  movzx   ecx, word ptr [ecx+0Ah]
0x1001051f  mov     [ebp+var_C], edx
0x10010522  mov     edx, eax
0x10010524  mov     [ebp+var_18], edi
0x10010527  mov     [ebp+var_10], edx
0x1001052a  mov     [ebp+var_1C], edx
0x1001052d  mov     [ebp+var_14], ecx
0x10010530  cmp     [ebp+var_C], edi
0x10010533  jnz     short loc_1001055B
0x10010535  xor     eax, eax
0x10010537  mov     edi, 1
0x1001053c  mov     [esi+18h], eax
0x1001053f  mov     [esi+1Eh], ax
0x10010543  mov     [esi+1Ch], di
0x10010547  mov     eax, [ebx+14h]
0x1001054a  mov     ecx, [eax+54h]
0x1001054d  sub     ecx, [eax+4]
0x10010550  add     ecx, [eax+8]
0x10010553  mov     [ebx+58h], ecx
0x10010556  jmp     loc_10010372
0x1001055b  mov     edx, [ebp+var_10]
0x1001055e  mov     [esi+1Ah], ax
0x10010562  lea     eax, [ecx-1]
0x10010565  movzx   eax, ax
0x10010568  xor     ecx, ecx
0x1001056a  cmp     dx, word ptr [ebp+var_14]
0x1001056e  cmovnz  ecx, eax
0x10010571  mov     eax, [ebp+var_18]
0x10010574  dec     eax
0x10010575  movzx   edi, cx
0x10010578  movzx   edx, ax
0x1001057b  mov     eax, [ebp+var_C]
0x1001057e  movzx   ecx, ax
0x10010581  mov     eax, [ebp+var_1C]
0x10010584  movzx   eax, ax
0x10010587  mov     [ebp+var_1C], eax
0x1001058a  mov     eax, edx
0x1001058c  mov     [esi+18h], cx
0x10010590  mov     [esi+1Ch], ax
0x10010594  mov     eax, edi
0x10010596  mov     [esi+1Eh], di
0x1001059a  test    cx, cx
0x1001059d  jnz     loc_100104C6
0x100105a3  mov     ecx, [ebp+var_1C]
0x100105a6  movzx   ecx, cx
0x100105a9  test    dx, dx
0x100105ac  jnz     loc_100104C6
0x100105b2  test    cx, cx
0x100105b5  jnz     loc_100104C6
0x100105bb  test    ax, ax
0x100105be  jnz     loc_100104C6
0x100105c4  mov     edi, 1
0x100105c9  mov     [esi+1Ch], di
0x100105cd  mov     eax, [ebx+14h]
0x100105d0  mov     ecx, [eax+54h]
0x100105d3  sub     ecx, [eax+4]
0x100105d6  add     ecx, [eax+8]
0x100105d9  mov     [ebx+58h], ecx
0x100105dc  jmp     loc_10010372
0x100105e1  cmp     ax, 0Ah
0x100105e5  jz      loc_100106EC
0x100105eb  mov     edx, 204h
0x100105f0  cmp     ax, dx
0x100105f3  jz      loc_100106EC
0x100105f9  mov     edx, 27Eh
0x100105fe  cmp     ax, dx
0x10010601  jz      loc_100106EC
0x10010607  mov     edx, 203h
0x1001060c  cmp     ax, dx
0x1001060f  jz      loc_100106EC
0x10010615  mov     edx, 0BDh
0x1001061a  cmp     ax, dx
0x1001061d  jz      loc_100106EC
0x10010623  mov     edx, 0BEh
0x10010628  cmp     ax, dx
0x1001062b  jz      loc_100106EC
0x10010631  mov     edx, 201h
0x10010636  cmp     ax, dx
0x10010639  jz      loc_100106EC
0x1001063f  mov     edx, 205h
0x10010644  cmp     ax, dx
0x10010647  jz      loc_100106EC
0x1001064d  mov     edx, 0D6h
0x10010652  cmp     ax, dx
0x10010655  jz      loc_100106EC
0x1001065b  mov     edx, 0FDh
0x10010660  cmp     ax, dx
0x10010663  jz      loc_100106EC
0x10010669  mov     edx, 206h
0x1001066e  cmp     ax, dx
0x10010671  jz      short loc_100106EC
0x10010673  mov     edx, 406h
0x10010678  cmp     ax, dx
0x1001067b  jz      short loc_100106EC
  ... truncated ...
```
