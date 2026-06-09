# TableMover::RecordAddress(Err &)

- ea: `0x10059d00`
- end: `0x1005a22b`
- name: `?RecordAddress@TableMover@@UAEPAVRecord@@AAVErr@@@Z`
- size: `1323`
- prototype: `unsigned int **__thiscall(TableMover *this, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10023690`
- `0x10023ad0`
- `0x10023fc0`
- `0x10024ee0`
- `0x10025db0`
- `0x10025ee0`
- `0x10025f50`
- `0x10026020`
- `0x10059d00`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10059f62`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10059fc7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10059f62`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x10059fc7`

## pseudocode

```c
unsigned int **__thiscall TableMover::RecordAddress(TableMover *this, void **a2)
{
  struct Err *v3; // ebx
  int v4; // ecx
  struct PageRef *v5; // edx
  unsigned int **v6; // edi
  int v7; // ecx
  __int16 v8; // ax
  int v9; // eax
  struct PageRef *v10; // edx
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  int (__thiscall *v16)(int); // edi
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int (__thiscall *v21)(int); // edi
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  unsigned int **result; // eax
  int v27; // eax
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  Err *v31; // ecx
  const unsigned __int16 *v32; // edi
  int v33; // [esp+24h] [ebp-18h]
  int v34; // [esp+28h] [ebp-14h]
  char v35; // [esp+2Fh] [ebp-Dh]

  v3 = (struct Err *)a2;
  v35 = 0;
  v34 = 10;
  if ( !*((_DWORD *)this + 3) )
  {
    *((_DWORD *)this + 3) = (*(int (__thiscall **)(TableMover *, void **))(*(_DWORD *)this + 12))(this, a2);
    if ( (*(_BYTE *)a2 & 8) != 0 )
      goto LABEL_72;
  }
  v4 = *((_DWORD *)this + 5);
  v5 = (TableMover *)((char *)this + 20);
  if ( !v4 || *((_DWORD *)this + 7) != *(_DWORD *)(v4 + 64) )
    goto LABEL_8;
  v6 = (unsigned int **)((char *)this + 52);
  while ( 2 )
  {
    if ( *v6 && !*((_DWORD *)this + 4) )
    {
LABEL_50:
      if ( *((_DWORD *)this + 14) > 0x7DCu )
      {
        Err::SetError(a2, -1611, v4);
        goto LABEL_72;
      }
      return v6;
    }
    switch ( DataPage::RecordAddress(v5, *((_DWORD *)this + 3), v6) )
    {
      case 0:
        *((_DWORD *)this + 4) = 0;
        goto LABEL_50;
      case 1:
        v10 = (TableMover *)((char *)this + 36);
        v11 = **v6;
        *((_DWORD *)this + 4) = v11;
        v12 = *((_DWORD *)this + 9);
        if ( v12 )
          v13 = *(_DWORD *)(v12 + 12);
        else
          v13 = 0;
        if ( v11 >> 8 == v13 && v12 && *((_DWORD *)this + 11) == *(_DWORD *)(v12 + 64) )
        {
          v3 = (struct Err *)a2;
        }
        else
        {
LABEL_29:
          v3 = (struct Err *)a2;
          Database::ReadPage(
            *(Database **)(*(_DWORD *)(*((_DWORD *)this + 1) + 40) + 8),
            v10,
            *((_DWORD *)this + 4) >> 8,
            1,
            (struct Err *)a2,
            *(struct Transaction **)(*((_DWORD *)this + 1) + 40));
          if ( (*(_BYTE *)a2 & 8) != 0 )
            goto LABEL_72;
          v10 = (TableMover *)((char *)this + 36);
          *((_DWORD *)this + 11) = *(_DWORD *)(*((_DWORD *)this + 9) + 64);
        }
        switch ( DataPage::RecordAddress(v10, *((_DWORD *)this + 4), v6) )
        {
          case 2:
            goto LABEL_50;
          case 3:
            Err::SetError(v3, -1017, v4);
            goto LABEL_72;
          case 4:
            if ( v35 )
              goto LABEL_34;
            v35 = 1;
            v14 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
            Database::TossCache(*(Database **)(v14 + 16));
            v6 = (unsigned int **)((char *)this + 52);
            v10 = (TableMover *)((char *)this + 36);
            goto LABEL_29;
          default:
LABEL_34:
            v15 = v34--;
            v33 = *((_DWORD *)this + 1);
            v16 = *(int (__thiscall **)(int))(*(_DWORD *)v33 + 56);
            if ( !v15 )
            {
              v23 = v16(v33);
              Database::MarkCorrupt(*(Database **)(v23 + 16), v3);
              Err::Reset(v3);
              v24 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
              Err::SetError(a2, -1206, -8188, *(_DWORD *)(*(_DWORD *)(v24 + 16) + 8), 0, v25);
              goto LABEL_72;
            }
            v17 = v16(v33);
            Database::TossCache(*(Database **)(v17 + 16));
            Sleep(0x64u);
            break;
        }
        goto LABEL_7;
      case 3:
        Err::SetError(a2, -1017, v4);
        goto LABEL_72;
      case 4:
        if ( v35 )
          goto LABEL_38;
        v35 = 1;
        v18 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
        Database::TossCache(*(Database **)(v18 + 16));
        goto LABEL_6;
      default:
LABEL_38:
        v19 = *((_DWORD *)this + 1);
        v20 = v34--;
        v21 = *(int (__thiscall **)(int))(*(_DWORD *)v19 + 56);
        if ( !v20 )
        {
          v27 = v21(v19);
          Database::MarkCorrupt(*(Database **)(v27 + 16), (struct Err *)a2);
          if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
          {
            if ( a2[3] )
              operator delete[](a2[3]);
            if ( a2[4] )
              operator delete[](a2[4]);
          }
          *a2 = (void *)1;
          v28 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
          Err::SetError(a2, -1206, -8188, *(_DWORD *)(*(_DWORD *)(v28 + 16) + 8), 0, v29);
          goto LABEL_72;
        }
        v22 = v21(v19);
        Database::TossCache(*(Database **)(v22 + 16));
        Sleep(0x64u);
LABEL_6:
        v3 = (struct Err *)a2;
LABEL_7:
        v5 = (TableMover *)((char *)this + 20);
LABEL_8:
        Database::ReadPage(
          *(Database **)(*(_DWORD *)(*((_DWORD *)this + 1) + 40) + 8),
          v5,
          *((_DWORD *)this + 3) >> 8,
          1,
          v3,
          *(struct Transaction **)(*((_DWORD *)this + 1) + 40));
        v7 = *(_DWORD *)v3;
        if ( (*(_DWORD *)v3 & 8) != 0 )
          goto LABEL_72;
        v8 = **((_WORD **)this + 6);
        if ( v8 == 257 || v8 == 259 || v8 == 260 || v8 == 262 || v8 == 263 || v8 == 265 )
        {
          v9 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
          v4 = *((_DWORD *)this + 6);
          *((_DWORD *)this + 8) = *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(v9 + 16) + 60) + 104);
          if ( *(_DWORD *)(v4 + 4) > 0x80000u || *(_WORD *)(v4 + 2) > 0x7F6u || *(_WORD *)(v4 + 8) > 0xFFu )
          {
            v30 = (*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1));
            Database::MarkCorrupt(*(Database **)(v30 + 16), (struct Err *)a2);
            if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
            {
              if ( a2[3] )
                operator delete[](a2[3]);
              if ( a2[4] )
                operator delete[](a2[4]);
            }
            *a2 = (void *)1;
            v3 = (struct Err *)a2;
            v32 = *(const unsigned __int16 **)(*(_DWORD *)((*(int (__thiscall **)(_DWORD))(**((_DWORD **)this + 1) + 56))(*((_DWORD *)this + 1))
                                                         + 16)
                                             + 8);
            if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
            {
              if ( a2[3] )
                operator delete[](a2[3]);
              if ( a2[4] )
                operator delete[](a2[4]);
            }
            *a2 = (void *)8;
            a2[1] = (void *)-1206;
            a2[2] = (void *)-8188;
            Err::CopyString(v31, (unsigned __int16 **)a2 + 3, v32);
            goto LABEL_71;
          }
          v5 = (TableMover *)((char *)this + 20);
          v6 = (unsigned int **)((char *)this + 52);
          *((_DWORD *)this + 7) = *(_DWORD *)(*((_DWORD *)this + 5) + 64);
          *((_DWORD *)this + 13) = 0;
          *((_DWORD *)this + 14) = 0;
          *((_DWORD *)this + 15) = 0;
          continue;
        }
        if ( v7 < 8 )
        {
          if ( (v7 & 0xFFFFFFFE) != 0 )
          {
            if ( *((_DWORD *)v3 + 3) )
              operator delete[](*((void **)v3 + 3));
            if ( *((_DWORD *)v3 + 4) )
              operator delete[](*((void **)v3 + 4));
          }
          *(_DWORD *)v3 = 8;
          *((_DWORD *)v3 + 1) = -1611;
          *((_DWORD *)v3 + 2) = 0;
          *((_DWORD *)v3 + 3) = 0;
LABEL_71:
          *((_DWORD *)v3 + 4) = 0;
        }
LABEL_72:
        result = (unsigned int **)((char *)this + 52);
        *((_DWORD *)this + 14) = 0;
        *((_DWORD *)this + 13) = 0;
        *((_DWORD *)this + 15) = 0;
        return result;
    }
  }
}

```

## disassembly

```asm
0x10059d00  mov     edi, edi
0x10059d02  push    ebp
0x10059d03  mov     ebp, esp
0x10059d05  push    0FFFFFFFFh
0x10059d07  push    offset ?RecordAddress@TableMover@@UAEPAVRecord@@AAVErr@@@Z_SEH
0x10059d0c  mov     eax, large fs:0
0x10059d12  push    eax
0x10059d13  sub     esp, 20h
0x10059d16  push    ebx
0x10059d17  push    esi
0x10059d18  push    edi
0x10059d19  mov     eax, ___security_cookie
0x10059d1e  xor     eax, ebp
0x10059d20  push    eax; unsigned int
0x10059d21  lea     eax, [ebp+var_C]
0x10059d24  mov     large fs:0, eax
0x10059d2a  mov     esi, ecx
0x10059d2c  cmp     dword ptr [esi+0Ch], 0
0x10059d30  mov     ebx, [ebp+arg_0]
0x10059d33  mov     [ebp+var_D], 0
0x10059d37  mov     [ebp+var_14], 0Ah
0x10059d3e  jnz     short loc_10059D5E
0x10059d40  mov     eax, [esi]
0x10059d42  push    ebx; void *
0x10059d43  mov     edi, [eax+0Ch]
0x10059d46  mov     ecx, edi
0x10059d48  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059d4e  mov     ecx, esi
0x10059d50  call    edi
0x10059d52  mov     [esi+0Ch], eax
0x10059d55  test    byte ptr [ebx], 8
0x10059d58  jnz     loc_1005A200
0x10059d5e  mov     ecx, [esi+14h]
0x10059d61  lea     edx, [esi+14h]
0x10059d64  mov     edi, 103h
0x10059d69  test    ecx, ecx
0x10059d6b  jz      short loc_10059D88
0x10059d6d  mov     eax, [edx+8]
0x10059d70  cmp     eax, [ecx+40h]
0x10059d73  jnz     short loc_10059D88
0x10059d75  lea     edi, [esi+34h]
0x10059d78  jmp     loc_10059E5F
0x10059d7d  mov     ebx, [ebp+arg_0]
0x10059d80  mov     edi, 103h
0x10059d85  lea     edx, [esi+14h]
0x10059d88  mov     eax, [esi+4]
0x10059d8b  mov     ecx, [esi+0Ch]
0x10059d8e  shr     ecx, 8
0x10059d91  mov     eax, [eax+28h]
0x10059d94  push    eax; struct Transaction *
0x10059d95  push    ebx; struct Err *
0x10059d96  push    1; char
0x10059d98  push    ecx; unsigned int
0x10059d99  mov     ecx, [eax+8]; this
0x10059d9c  push    edx; struct PageRef *
0x10059d9d  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x10059da2  mov     ecx, [ebx]
0x10059da4  test    cl, 8
0x10059da7  jnz     loc_1005A200
0x10059dad  mov     eax, [esi+18h]
0x10059db0  mov     edx, 101h
0x10059db5  movzx   eax, word ptr [eax]
0x10059db8  cmp     ax, dx
0x10059dbb  jz      short loc_10059DEE
0x10059dbd  cmp     ax, di
0x10059dc0  jz      short loc_10059DEE
0x10059dc2  mov     edx, 104h
0x10059dc7  cmp     ax, dx
0x10059dca  jz      short loc_10059DEE
0x10059dcc  mov     edx, 106h
0x10059dd1  cmp     ax, dx
0x10059dd4  jz      short loc_10059DEE
0x10059dd6  mov     edx, 107h
0x10059ddb  cmp     ax, dx
0x10059dde  jz      short loc_10059DEE
0x10059de0  mov     edx, 109h
0x10059de5  cmp     ax, dx
0x10059de8  jnz     loc_10059FD2
0x10059dee  mov     ebx, [esi+4]
0x10059df1  mov     eax, [ebx]
0x10059df3  mov     edi, [eax+38h]
0x10059df6  mov     ecx, edi
0x10059df8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059dfe  mov     ecx, ebx
0x10059e00  call    edi
0x10059e02  mov     ecx, [esi+18h]
0x10059e05  mov     eax, [eax+10h]
0x10059e08  mov     eax, [eax+3Ch]
0x10059e0b  mov     eax, [eax+68h]
0x10059e0e  mov     [esi+20h], eax
0x10059e11  cmp     dword ptr [ecx+4], 80000h
0x10059e18  ja      loc_1005A148
0x10059e1e  mov     eax, 7F6h
0x10059e23  cmp     [ecx+2], ax
0x10059e27  ja      loc_1005A148
0x10059e2d  mov     eax, 0FFh
0x10059e32  cmp     [ecx+8], ax
0x10059e36  ja      loc_1005A148
0x10059e3c  mov     eax, [esi+14h]
0x10059e3f  lea     edx, [esi+14h]
0x10059e42  lea     edi, [esi+34h]
0x10059e45  mov     eax, [eax+40h]
0x10059e48  mov     [edx+8], eax
0x10059e4b  mov     dword ptr [edi], 0
0x10059e51  mov     dword ptr [edi+4], 0
0x10059e58  mov     dword ptr [edi+8], 0
0x10059e5f  cmp     dword ptr [edi], 0
0x10059e62  jz      short loc_10059E6E
0x10059e64  cmp     dword ptr [esi+10h], 0
0x10059e68  jz      loc_1005A08B; jumptable 10059EFA case 2
0x10059e6e  push    edi
0x10059e6f  push    dword ptr [esi+0Ch]
0x10059e72  mov     ecx, edx
0x10059e74  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x10059e79  cmp     eax, 4; switch 5 cases
0x10059e7c  ja      def_10059E82; jumptable 10059E82 default case, case 2
0x10059e82  jmp     ds:jpt_10059E82[eax*4]; switch jump
0x10059e89  mov     eax, [edi]; jumptable 10059E82 case 1
0x10059e8b  lea     edx, [esi+24h]
0x10059e8e  mov     eax, [eax]
0x10059e90  mov     [esi+10h], eax
0x10059e93  mov     ecx, [edx]
0x10059e95  test    ecx, ecx
0x10059e97  jz      short loc_10059E9E
0x10059e99  mov     ebx, [ecx+0Ch]
0x10059e9c  jmp     short loc_10059EA0
0x10059e9e  xor     ebx, ebx
0x10059ea0  shr     eax, 8
0x10059ea3  cmp     eax, ebx
0x10059ea5  jnz     short loc_10059EB8
0x10059ea7  test    ecx, ecx
0x10059ea9  jz      short loc_10059EB8
0x10059eab  mov     eax, [esi+2Ch]
0x10059eae  cmp     eax, [ecx+40h]
0x10059eb1  jnz     short loc_10059EB8
0x10059eb3  mov     ebx, [ebp+arg_0]
0x10059eb6  jmp     short loc_10059EEA
0x10059eb8  mov     eax, [esi+4]
0x10059ebb  mov     ecx, [esi+10h]
0x10059ebe  mov     ebx, [ebp+arg_0]
0x10059ec1  shr     ecx, 8
0x10059ec4  mov     eax, [eax+28h]
0x10059ec7  push    eax; struct Transaction *
0x10059ec8  push    ebx; struct Err *
0x10059ec9  push    1; char
0x10059ecb  push    ecx; unsigned int
0x10059ecc  mov     ecx, [eax+8]; this
0x10059ecf  push    edx; struct PageRef *
0x10059ed0  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x10059ed5  test    byte ptr [ebx], 8
0x10059ed8  jnz     loc_1005A200
0x10059ede  mov     eax, [esi+24h]
0x10059ee1  lea     edx, [esi+24h]
0x10059ee4  mov     eax, [eax+40h]
0x10059ee7  mov     [esi+2Ch], eax
0x10059eea  push    edi
0x10059eeb  push    dword ptr [esi+10h]
0x10059eee  mov     ecx, edx
0x10059ef0  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x10059ef5  cmp     eax, 4; switch 5 cases
0x10059ef8  ja      short def_10059EFA; jumptable 10059EFA default case, cases 0,1
0x10059efa  jmp     ds:jpt_10059EFA[eax*4]; switch jump
0x10059f01  cmp     [ebp+var_D], 0; jumptable 10059EFA case 4
0x10059f05  jnz     short def_10059EFA; jumptable 10059EFA default case, cases 0,1
0x10059f07  mov     ebx, [esi+4]
0x10059f0a  mov     [ebp+var_D], 1
0x10059f0e  mov     eax, [ebx]
0x10059f10  mov     edi, [eax+38h]
0x10059f13  mov     ecx, edi
0x10059f15  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059f1b  mov     ecx, ebx
0x10059f1d  call    edi
0x10059f1f  mov     ecx, [eax+10h]; this
0x10059f22  call    ?TossCache@Database@@QAEXXZ; Database::TossCache(void)
0x10059f27  lea     edi, [esi+34h]
0x10059f2a  lea     edx, [esi+24h]
0x10059f2d  jmp     short loc_10059EB8
0x10059f2f  mov     ecx, [ebp+var_14]; jumptable 10059EFA default case, cases 0,1
0x10059f32  mov     eax, ecx
0x10059f34  dec     ecx
0x10059f35  mov     [ebp+var_14], ecx
0x10059f38  mov     ecx, [esi+4]
0x10059f3b  mov     [ebp+var_18], ecx
0x10059f3e  mov     edi, [ecx]
0x10059f40  mov     edi, [edi+38h]
0x10059f43  mov     ecx, edi
0x10059f45  test    eax, eax
0x10059f47  jz      loc_1005A035
0x10059f4d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059f53  mov     ecx, [ebp+var_18]
0x10059f56  call    edi
0x10059f58  mov     ecx, [eax+10h]; this
0x10059f5b  call    ?TossCache@Database@@QAEXXZ; Database::TossCache(void)
0x10059f60  push    64h ; 'd'; dwMilliseconds
0x10059f62  call    ds:__imp__Sleep@4; Sleep(x)
0x10059f68  jmp     loc_10059D80
0x10059f6d  cmp     [ebp+var_D], 0; jumptable 10059E82 case 4
0x10059f71  jnz     short def_10059E82; jumptable 10059E82 default case, case 2
0x10059f73  mov     ebx, [esi+4]
0x10059f76  mov     [ebp+var_D], 1
0x10059f7a  mov     eax, [ebx]
0x10059f7c  mov     edi, [eax+38h]
0x10059f7f  mov     ecx, edi
0x10059f81  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059f87  mov     ecx, ebx
0x10059f89  call    edi
0x10059f8b  mov     ecx, [eax+10h]; this
0x10059f8e  call    ?TossCache@Database@@QAEXXZ; Database::TossCache(void)
0x10059f93  jmp     loc_10059D7D
0x10059f98  mov     ebx, [esi+4]; jumptable 10059E82 default case, case 2
0x10059f9b  mov     ecx, [ebp+var_14]
0x10059f9e  mov     eax, ecx
0x10059fa0  dec     ecx
0x10059fa1  mov     [ebp+var_14], ecx
0x10059fa4  mov     edi, [ebx]
0x10059fa6  mov     edi, [edi+38h]
0x10059fa9  mov     ecx, edi
0x10059fab  test    eax, eax
0x10059fad  jz      loc_1005A0D0
0x10059fb3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10059fb9  mov     ecx, ebx
0x10059fbb  call    edi
0x10059fbd  mov     ecx, [eax+10h]; this
0x10059fc0  call    ?TossCache@Database@@QAEXXZ; Database::TossCache(void)
0x10059fc5  push    64h ; 'd'; dwMilliseconds
0x10059fc7  call    ds:__imp__Sleep@4; Sleep(x)
0x10059fcd  jmp     loc_10059D7D
0x10059fd2  cmp     ecx, 8
0x10059fd5  jge     loc_1005A200
0x10059fdb  test    ecx, 0FFFFFFFEh
0x10059fe1  jz      short loc_1005A003
0x10059fe3  mov     eax, [ebx+0Ch]
0x10059fe6  test    eax, eax
0x10059fe8  jz      short loc_10059FF3
0x10059fea  push    eax; Block
0x10059feb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10059ff0  add     esp, 4
0x10059ff3  mov     eax, [ebx+10h]
0x10059ff6  test    eax, eax
0x10059ff8  jz      short loc_1005A003
0x10059ffa  push    eax; Block
0x10059ffb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005a000  add     esp, 4
0x1005a003  mov     dword ptr [ebx], 8
0x1005a009  mov     dword ptr [ebx+4], 0FFFFF9B5h
0x1005a010  mov     dword ptr [ebx+8], 0
0x1005a017  mov     dword ptr [ebx+0Ch], 0
0x1005a01e  jmp     loc_1005A1F9
0x1005a023  push    ecx; jumptable 10059EFA case 3
0x1005a024  push    0FFFFFC07h
0x1005a029  mov     ecx, ebx
0x1005a02b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005a030  jmp     loc_1005A200
0x1005a035  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005a03b  mov     ecx, [ebp+var_18]
0x1005a03e  call    edi
0x1005a040  push    ebx; struct Err *
0x1005a041  mov     ecx, [eax+10h]; this
0x1005a044  call    ?MarkCorrupt@Database@@QAEXAAVErr@@@Z; Database::MarkCorrupt(Err &)
0x1005a049  mov     ecx, ebx; this
0x1005a04b  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x1005a050  mov     ebx, [esi+4]
0x1005a053  mov     eax, [ebx]
0x1005a055  mov     edi, [eax+38h]
0x1005a058  mov     ecx, edi
0x1005a05a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005a060  mov     ecx, ebx
0x1005a062  call    edi
0x1005a064  push    ecx
0x1005a065  mov     ecx, [ebp+arg_0]
0x1005a068  push    0
0x1005a06a  mov     eax, [eax+10h]
0x1005a06d  push    dword ptr [eax+8]
0x1005a070  push    0FFFFE004h
0x1005a075  push    0FFFFFB4Ah
0x1005a07a  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x1005a07f  jmp     loc_1005A200
0x1005a084  mov     dword ptr [esi+10h], 0; jumptable 10059E82 case 0
0x1005a08b  cmp     dword ptr [esi+38h], 7DCh; jumptable 10059EFA case 2
0x1005a092  jbe     short loc_1005A0A7
0x1005a094  push    ecx
0x1005a095  mov     ecx, [ebp+arg_0]
0x1005a098  push    0FFFFF9B5h
0x1005a09d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005a0a2  jmp     loc_1005A200
0x1005a0a7  mov     eax, edi
0x1005a0a9  mov     ecx, [ebp+var_C]
0x1005a0ac  mov     large fs:0, ecx
0x1005a0b3  pop     ecx
0x1005a0b4  pop     edi
0x1005a0b5  pop     esi
0x1005a0b6  pop     ebx
0x1005a0b7  mov     esp, ebp
0x1005a0b9  pop     ebp
0x1005a0ba  retn    4
0x1005a0bd  push    ecx; jumptable 10059E82 case 3
0x1005a0be  mov     ecx, [ebp+arg_0]
0x1005a0c1  push    0FFFFFC07h
0x1005a0c6  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005a0cb  jmp     loc_1005A200
  ... truncated ...
```
