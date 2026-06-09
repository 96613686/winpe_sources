# TblPage::ReadPages(Instance *,ulong,Err &)

- ea: `0x1005b3b0`
- end: `0x1005b673`
- name: `?ReadPages@TblPage@@AAEXPAVInstance@@KAAVErr@@@Z`
- size: `707`
- prototype: `void __thiscall(TblPage *this, struct Instance *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x10051a30`
- `0x10053400`

## callees

- `0x10010580`
- `0x10023690`
- `0x10025ee0`
- `0x1005b380`
- `0x1005b3b0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
void __thiscall TblPage::ReadPages(TblPage *this, struct Instance *a2, unsigned int a3, void **a4)
{
  TblPage *v4; // esi
  struct PageRef *v5; // eax
  int v6; // ecx
  int *v7; // edi
  int *v8; // eax
  PageRef *v9; // ecx
  unsigned int v10; // ecx
  int v11; // ecx
  int v12; // edi
  _DWORD *v13; // edx
  signed int v14; // esi
  int v15; // ecx
  void *v16; // eax
  unsigned int v17; // [esp-4h] [ebp-40h]
  int v18; // [esp+14h] [ebp-28h] BYREF
  int v19; // [esp+18h] [ebp-24h]
  int v20; // [esp+20h] [ebp-1Ch]
  int v21; // [esp+24h] [ebp-18h]
  TblPage *v22; // [esp+28h] [ebp-14h]
  unsigned int v23; // [esp+2Ch] [ebp-10h]
  int v24; // [esp+38h] [ebp-4h]

  v4 = this;
  v22 = this;
  v5 = (struct PageRef *)operator new(0xCu);
  v20 = (int)v5;
  *(_DWORD *)v5 = 0;
  *((_DWORD *)v5 + 1) = 0;
  *((_DWORD *)v4 + 2) = v5;
  Database::ReadPage(
    *(Database **)(*((_DWORD *)a2 + 15) + 8),
    v5,
    a3,
    1,
    (struct Err *)a4,
    *((struct Transaction **)a2 + 15));
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    v6 = *(_DWORD *)(*((_DWORD *)v4 + 2) + 4);
    if ( *(_WORD *)v6 == 264 )
    {
      Err::SetError(a4, -1305, *(_DWORD *)(*((_DWORD *)v4 + 2) + 4));
    }
    else if ( *(_WORD *)v6 == 258 )
    {
      v7 = (int *)(v6 + 8);
      *((_DWORD *)v4 + 1) = v6 + 8;
      v23 = *(_DWORD *)(v6 + 4);
      if ( !v23 || *v7 <= 2040 )
        return;
      v17 = *v7;
      v21 = 1;
      v8 = (int *)operator new[](v17);
      *((_DWORD *)v4 + 1) = v8;
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        qmemcpy(v8, v7, 0x7F8u);
        v4 = v22;
        v9 = (PageRef *)*((_DWORD *)v22 + 2);
        if ( v9 )
          PageRef::`scalar deleting destructor'(v9, *((_DWORD *)v22 + 2));
        v10 = v23;
        *((_DWORD *)v22 + 2) = 0;
        while ( 1 )
        {
          v18 = 0;
          v19 = 0;
          v24 = 0;
          Database::ReadPage(
            *(Database **)(*((_DWORD *)a2 + 15) + 8),
            (struct PageRef *)&v18,
            v10,
            1,
            (struct Err *)a4,
            *((struct Transaction **)a2 + 15));
          if ( (*(_BYTE *)a4 & 8) != 0 )
            break;
          v12 = v19;
          if ( *(_WORD *)v19 != 258 )
          {
            Err::SetError(a4, -1206, v11);
            break;
          }
          v13 = (_DWORD *)*((_DWORD *)v4 + 1);
          v14 = *v13 - 2040 * v21;
          v20 = 2040 * v21;
          if ( v14 <= 2040 )
          {
            if ( v14 != 2040 && *(_DWORD *)(v19 + 4) )
            {
              Err::SetError(a4, -1206, 2040 * v21);
              v4 = v22;
              break;
            }
          }
          else
          {
            v14 = 2040;
          }
          memcpy(&v13[510 * v21], (const void *)(v19 + 8), v14);
          v10 = *(_DWORD *)(v12 + 4);
          v23 = v10;
          if ( v10 )
          {
            v4 = v22;
          }
          else
          {
            v15 = v14 + v20;
            v4 = v22;
            if ( v15 != **((_DWORD **)v22 + 1) && (int)*a4 < 8 )
            {
              if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
              {
                if ( a4[3] )
                  operator delete[](a4[3]);
                if ( a4[4] )
                  operator delete[](a4[4]);
              }
              *a4 = (void *)8;
              a4[1] = (void *)-1206;
              a4[2] = 0;
              a4[3] = 0;
              a4[4] = 0;
            }
            v10 = v23;
          }
          ++v21;
          v24 = -1;
          if ( v18 )
            --*(_WORD *)(v18 + 76);
          if ( !v10 )
            return;
        }
        if ( v18 )
          --*(_WORD *)(v18 + 76);
      }
    }
    else
    {
      Err::SetError(a4, -1206, *(_DWORD *)(*((_DWORD *)v4 + 2) + 4));
    }
  }
  v16 = (void *)*((_DWORD *)v4 + 2);
  if ( v16 )
  {
    if ( *(_DWORD *)v16 )
      --*(_WORD *)(*(_DWORD *)v16 + 76);
    operator delete(v16, 0xCu);
    *((_DWORD *)v4 + 2) = 0;
  }
  else
  {
    if ( !*((_DWORD *)v4 + 1) )
      return;
    operator delete[](*((void **)v4 + 1));
  }
  *((_DWORD *)v4 + 1) = 0;
}

```

## disassembly

```asm
0x1005b3b0  mov     edi, edi
0x1005b3b2  push    ebp
0x1005b3b3  mov     ebp, esp
0x1005b3b5  push    0FFFFFFFFh
0x1005b3b7  push    offset ?ReadPages@TblPage@@AAEXPAVInstance@@KAAVErr@@@Z_SEH
0x1005b3bc  mov     eax, large fs:0
0x1005b3c2  push    eax
0x1005b3c3  sub     esp, 20h
0x1005b3c6  push    ebx
0x1005b3c7  push    esi
0x1005b3c8  push    edi
0x1005b3c9  mov     eax, ___security_cookie
0x1005b3ce  xor     eax, ebp
0x1005b3d0  push    eax
0x1005b3d1  lea     eax, [ebp+var_C]
0x1005b3d4  mov     large fs:0, eax
0x1005b3da  mov     esi, ecx
0x1005b3dc  mov     [ebp+var_14], esi
0x1005b3df  push    0Ch; Size
0x1005b3e1  call    ??2@YAPAXI@Z; operator new(uint)
0x1005b3e6  mov     ebx, [ebp+arg_8]
0x1005b3e9  mov     edx, eax
0x1005b3eb  mov     eax, [ebp+arg_0]
0x1005b3ee  add     esp, 4
0x1005b3f1  mov     [ebp+var_1C], edx
0x1005b3f4  mov     dword ptr [edx], 0
0x1005b3fa  mov     dword ptr [edx+4], 0
0x1005b401  mov     [esi+8], edx
0x1005b404  mov     eax, [eax+3Ch]
0x1005b407  push    eax; struct Transaction *
0x1005b408  push    ebx; struct Err *
0x1005b409  push    1; char
0x1005b40b  push    [ebp+arg_4]; unsigned int
0x1005b40e  mov     ecx, [eax+8]; this
0x1005b411  push    edx; struct PageRef *
0x1005b412  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1005b417  test    byte ptr [ebx], 8
0x1005b41a  jnz     loc_1005B623
0x1005b420  mov     eax, [esi+8]
0x1005b423  mov     edi, 108h
0x1005b428  mov     ecx, [eax+4]
0x1005b42b  movzx   eax, word ptr [ecx]
0x1005b42e  mov     edx, eax
0x1005b430  cmp     ax, di
0x1005b433  jnz     short loc_1005B447
0x1005b435  push    ecx
0x1005b436  push    0FFFFFAE7h
0x1005b43b  mov     ecx, ebx
0x1005b43d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005b442  jmp     loc_1005B623
0x1005b447  mov     eax, 102h
0x1005b44c  cmp     dx, ax
0x1005b44f  jz      short loc_1005B463
0x1005b451  push    ecx
0x1005b452  push    0FFFFFB4Ah
0x1005b457  mov     ecx, ebx
0x1005b459  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005b45e  jmp     loc_1005B623
0x1005b463  lea     edi, [ecx+8]
0x1005b466  mov     [esi+4], edi
0x1005b469  mov     eax, [ecx+4]
0x1005b46c  mov     [ebp+var_10], eax
0x1005b46f  test    eax, eax
0x1005b471  jz      loc_1005B65F
0x1005b477  mov     eax, [edi]
0x1005b479  cmp     eax, 7F8h
0x1005b47e  jle     loc_1005B65F
0x1005b484  push    eax; unsigned int
0x1005b485  mov     [ebp+var_18], 1
0x1005b48c  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1005b491  add     esp, 4
0x1005b494  mov     [esi+4], eax
0x1005b497  test    byte ptr [ebx], 8
0x1005b49a  jnz     loc_1005B623
0x1005b4a0  mov     esi, edi
0x1005b4a2  mov     ecx, 1FEh
0x1005b4a7  mov     edi, eax
0x1005b4a9  rep movsd
0x1005b4ab  mov     esi, [ebp+var_14]
0x1005b4ae  mov     ecx, [esi+8]; this
0x1005b4b1  test    ecx, ecx
0x1005b4b3  jz      short loc_1005B4BB
0x1005b4b5  push    ecx; unsigned int
0x1005b4b6  call    ??_GPageRef@@QAEPAXI@Z; PageRef::`scalar deleting destructor'(uint)
0x1005b4bb  mov     ecx, [ebp+var_10]
0x1005b4be  mov     dword ptr [esi+8], 0
0x1005b4c5  nop     word ptr [eax+eax+00000000h]
0x1005b4d0  mov     [ebp+var_28], 0
0x1005b4d7  mov     [ebp+var_24], 0
0x1005b4de  mov     eax, [ebp+arg_0]
0x1005b4e1  mov     [ebp+var_4], 0
0x1005b4e8  mov     eax, [eax+3Ch]
0x1005b4eb  push    eax; struct Transaction *
0x1005b4ec  push    ebx; struct Err *
0x1005b4ed  push    1; char
0x1005b4ef  push    ecx; unsigned int
0x1005b4f0  lea     ecx, [ebp+var_28]
0x1005b4f3  push    ecx; struct PageRef *
0x1005b4f4  mov     ecx, [eax+8]; this
0x1005b4f7  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1005b4fc  test    byte ptr [ebx], 8
0x1005b4ff  jnz     loc_1005B618
0x1005b505  mov     edi, [ebp+var_24]
0x1005b508  mov     eax, 102h
0x1005b50d  cmp     [edi], ax
0x1005b510  jnz     loc_1005B60B
0x1005b516  mov     edx, [esi+4]
0x1005b519  imul    ecx, [ebp+var_18], 7F8h
0x1005b520  mov     esi, [edx]
0x1005b522  sub     esi, ecx
0x1005b524  mov     [ebp+var_1C], ecx
0x1005b527  cmp     esi, 7F8h
0x1005b52d  jle     short loc_1005B536
0x1005b52f  mov     esi, 7F8h
0x1005b534  jmp     short loc_1005B542
0x1005b536  jz      short loc_1005B542
0x1005b538  cmp     dword ptr [edi+4], 0
0x1005b53c  jnz     loc_1005B5F9
0x1005b542  push    esi; Size
0x1005b543  lea     eax, [edi+8]
0x1005b546  push    eax; Src
0x1005b547  lea     eax, [edx+ecx]
0x1005b54a  push    eax; void *
0x1005b54b  call    _memcpy
0x1005b550  mov     ecx, [edi+4]
0x1005b553  add     esp, 0Ch
0x1005b556  mov     [ebp+var_10], ecx
0x1005b559  test    ecx, ecx
0x1005b55b  jnz     loc_1005B5F4
0x1005b561  mov     ecx, [ebp+var_1C]
0x1005b564  add     ecx, esi
0x1005b566  mov     esi, [ebp+var_14]
0x1005b569  mov     eax, [esi+4]
0x1005b56c  cmp     ecx, [eax]
0x1005b56e  jz      short loc_1005B5C0
0x1005b570  mov     eax, [ebx]
0x1005b572  cmp     eax, 8
0x1005b575  jge     short loc_1005B5C0
0x1005b577  test    eax, 0FFFFFFFEh
0x1005b57c  jz      short loc_1005B59E
0x1005b57e  mov     eax, [ebx+0Ch]
0x1005b581  test    eax, eax
0x1005b583  jz      short loc_1005B58E
0x1005b585  push    eax; Block
0x1005b586  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005b58b  add     esp, 4
0x1005b58e  mov     eax, [ebx+10h]
0x1005b591  test    eax, eax
0x1005b593  jz      short loc_1005B59E
0x1005b595  push    eax; Block
0x1005b596  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005b59b  add     esp, 4
0x1005b59e  mov     dword ptr [ebx], 8
0x1005b5a4  mov     dword ptr [ebx+4], 0FFFFFB4Ah
0x1005b5ab  mov     dword ptr [ebx+8], 0
0x1005b5b2  mov     dword ptr [ebx+0Ch], 0
0x1005b5b9  mov     dword ptr [ebx+10h], 0
0x1005b5c0  mov     ecx, [ebp+var_10]
0x1005b5c3  inc     [ebp+var_18]
0x1005b5c6  mov     [ebp+var_4], 0FFFFFFFFh
0x1005b5cd  mov     eax, [ebp+var_28]
0x1005b5d0  test    eax, eax
0x1005b5d2  jz      short loc_1005B5D8
0x1005b5d4  dec     word ptr [eax+4Ch]
0x1005b5d8  test    ecx, ecx
0x1005b5da  jnz     loc_1005B4D0
0x1005b5e0  mov     ecx, [ebp+var_C]
0x1005b5e3  mov     large fs:0, ecx
0x1005b5ea  pop     ecx
0x1005b5eb  pop     edi
0x1005b5ec  pop     esi
0x1005b5ed  pop     ebx
0x1005b5ee  mov     esp, ebp
0x1005b5f0  pop     ebp
0x1005b5f1  retn    0Ch
0x1005b5f4  mov     esi, [ebp+var_14]
0x1005b5f7  jmp     short loc_1005B5C3
0x1005b5f9  push    ecx
0x1005b5fa  push    0FFFFFB4Ah
0x1005b5ff  mov     ecx, ebx
0x1005b601  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005b606  mov     esi, [ebp+var_14]
0x1005b609  jmp     short loc_1005B618
0x1005b60b  push    ecx
0x1005b60c  push    0FFFFFB4Ah
0x1005b611  mov     ecx, ebx
0x1005b613  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005b618  mov     eax, [ebp+var_28]
0x1005b61b  test    eax, eax
0x1005b61d  jz      short loc_1005B623
0x1005b61f  dec     word ptr [eax+4Ch]
0x1005b623  mov     eax, [esi+8]
0x1005b626  test    eax, eax
0x1005b628  jz      short loc_1005B648
0x1005b62a  mov     ecx, [eax]
0x1005b62c  test    ecx, ecx
0x1005b62e  jz      short loc_1005B634
0x1005b630  dec     word ptr [ecx+4Ch]
0x1005b634  push    0Ch; unsigned int
0x1005b636  push    eax; Block
0x1005b637  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005b63c  add     esp, 8
0x1005b63f  mov     dword ptr [esi+8], 0
0x1005b646  jmp     short loc_1005B658
0x1005b648  mov     eax, [esi+4]
0x1005b64b  test    eax, eax
0x1005b64d  jz      short loc_1005B65F
0x1005b64f  push    eax; Block
0x1005b650  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005b655  add     esp, 4
0x1005b658  mov     dword ptr [esi+4], 0
0x1005b65f  mov     ecx, [ebp+var_C]
0x1005b662  mov     large fs:0, ecx
0x1005b669  pop     ecx
0x1005b66a  pop     edi
0x1005b66b  pop     esi
0x1005b66c  pop     ebx
0x1005b66d  mov     esp, ebp
0x1005b66f  pop     ebp
0x1005b670  retn    0Ch
0x10062480  lea     ecx, [ebp+var_28]; this
0x10062483  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x1006248d  nop
0x1006248e  nop
0x1006248f  mov     edx, [esp-4+arg_4]
0x10062493  lea     eax, [edx+0Ch]
0x10062496  mov     ecx, [edx-30h]
0x10062499  xor     ecx, eax; StackCookie
0x1006249b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100624a0  mov     eax, offset stru_10064AC4
0x100624a5  jmp     ___CxxFrameHandler3
```
