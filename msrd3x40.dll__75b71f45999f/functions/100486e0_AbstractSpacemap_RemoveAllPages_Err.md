# AbstractSpacemap::RemoveAllPages(Err &)

- ea: `0x100486e0`
- end: `0x10048979`
- name: `?RemoveAllPages@AbstractSpacemap@@QAEXAAVErr@@@Z`
- size: `665`
- prototype: `void __thiscall(AbstractSpacemap *__hidden this, struct Err *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x10053cc0`
- `0x100577f0`
- `0x1005d280`

## callees

- `0x1000fc30`
- `0x10023690`
- `0x10023730`
- `0x100431f0`
- `0x10047a60`
- `0x100486e0`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall AbstractSpacemap::RemoveAllPages(AbstractSpacemap *this, void **a2)
{
  int v3; // ecx
  _BYTE *v4; // eax
  bool v5; // zf
  int i; // esi
  unsigned int v7; // ecx
  struct PageRef *v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  int v12; // ecx
  _BYTE *v13; // ecx
  signed int j; // esi
  unsigned int v15; // ecx
  struct PageRef *v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // [esp+Ch] [ebp-8h]
  unsigned int v20; // [esp+10h] [ebp-4h]

  AbstractSpacemap::Setup(this, 1, a2);
  v3 = (int)*a2;
  if ( ((unsigned __int8)*a2 & 8) != 0 )
    return;
  v4 = (_BYTE *)*((_DWORD *)this + 17);
  if ( v4 )
  {
    if ( *v4 )
    {
      if ( *v4 != 1 )
        goto LABEL_22;
      for ( i = 0; i < 33; ++i )
      {
        if ( *(_DWORD *)&v4[4 * i + 1] )
          break;
      }
      if ( (unsigned int)i > 0x20 )
        goto LABEL_22;
      v7 = *(_DWORD *)&v4[4 * i + 1];
      v20 = v7;
      if ( !v7 )
        goto LABEL_22;
      v8 = (AbstractSpacemap *)((char *)this + 44);
      if ( *((_DWORD *)this + 18) == 1 )
      {
        Database::ReadPageForUpdate(
          *(Database **)this,
          (AbstractSpacemap *)((char *)this + 44),
          v7,
          a2,
          *((struct Transaction **)this + 1),
          0);
      }
      else
      {
        if ( i == *((_DWORD *)this + 3) )
        {
          if ( !PageRef::HasChanged((char *)this + 44) )
          {
            v9 = 1;
            goto LABEL_23;
          }
          v7 = v20;
          v8 = (AbstractSpacemap *)((char *)this + 44);
        }
        Database::ReadPage(*(Database **)this, v8, v7, 1, a2, *((struct Transaction **)this + 1));
      }
      if ( (*(_BYTE *)a2 & 8) != 0 )
      {
LABEL_22:
        v9 = 0;
LABEL_23:
        if ( v9 != 1 )
          return;
        while ( 1 )
        {
          if ( (*(_BYTE *)a2 & 8) != 0 )
            return;
          Bitmap::Clear(
            (AbstractSpacemap *)((char *)this + 16),
            *((_DWORD *)this + 6),
            8 * *((_DWORD *)this + 5),
            (struct Err *)a2);
          if ( **((_BYTE **)this + 17) )
          {
            if ( **((_BYTE **)this + 17) == 1 )
            {
              v11 = *((_DWORD *)this + 11);
              *(_DWORD *)(v11 + 4 * *(_DWORD *)(v11 + 24) + 28) |= 8u;
              ++*(_DWORD *)(v11 + 64);
            }
          }
          else
          {
            v12 = *((_DWORD *)this + 7);
            *(_DWORD *)(v12 + 4 * *(_DWORD *)(v12 + 24) + 28) |= 8u;
            ++*(_DWORD *)(v12 + 64);
            *((_DWORD *)this + 9) = *(_DWORD *)(*((_DWORD *)this + 7) + 64);
          }
          v13 = (_BYTE *)*((_DWORD *)this + 17);
          if ( !v13 )
          {
            if ( (int)*a2 >= 8 )
              return;
            v5 = ((unsigned int)*a2 & 0xFFFFFFFE) == 0;
            goto LABEL_51;
          }
          if ( !*v13 || *v13 != 1 )
            goto LABEL_46;
          for ( j = *((_DWORD *)this + 6) / 0x3FE0u + 1; j < 33; ++j )
          {
            if ( *(_DWORD *)&v13[4 * j + 1] )
              break;
          }
          if ( (unsigned int)j > 0x20 || (v15 = *(_DWORD *)&v13[4 * j + 1], (v19 = v15) == 0) )
          {
LABEL_46:
            v17 = 0;
            goto LABEL_47;
          }
          v16 = (AbstractSpacemap *)((char *)this + 44);
          if ( *((_DWORD *)this + 18) == 1 )
          {
            Database::ReadPageForUpdate(
              *(Database **)this,
              (AbstractSpacemap *)((char *)this + 44),
              v15,
              a2,
              *((struct Transaction **)this + 1),
              0);
          }
          else
          {
            if ( j == *((_DWORD *)this + 3) )
            {
              if ( !PageRef::HasChanged((char *)this + 44) )
              {
                v17 = 1;
                goto LABEL_47;
              }
              v15 = v19;
              v16 = (AbstractSpacemap *)((char *)this + 44);
            }
            Database::ReadPage(*(Database **)this, v16, v15, 1, a2, *((struct Transaction **)this + 1));
          }
          if ( (*(_BYTE *)a2 & 8) != 0 )
            goto LABEL_46;
          *((_DWORD *)this + 13) = *(_DWORD *)(*((_DWORD *)this + 11) + 64);
          *((_DWORD *)this + 3) = j;
          v18 = *((_DWORD *)this + 12) + 4;
          *((_DWORD *)this + 5) = 2044;
          *((_DWORD *)this + 4) = v18;
          *((_DWORD *)this + 6) = 16352 * j;
          v17 = 1;
LABEL_47:
          if ( v17 != 1 )
            return;
        }
      }
      *((_DWORD *)this + 13) = *(_DWORD *)(*((_DWORD *)this + 11) + 64);
      *((_DWORD *)this + 3) = i;
      v10 = *((_DWORD *)this + 12) + 4;
      *((_DWORD *)this + 5) = 2044;
      *((_DWORD *)this + 4) = v10;
      *((_DWORD *)this + 6) = 16352 * i;
    }
    v9 = 1;
    goto LABEL_23;
  }
  if ( v3 < 8 )
  {
    v5 = (v3 & 0xFFFFFFFE) == 0;
LABEL_51:
    if ( !v5 )
    {
      if ( a2[3] )
        operator delete[](a2[3]);
      if ( a2[4] )
        operator delete[](a2[4]);
    }
    *a2 = (void *)8;
    a2[4] = 0;
    a2[3] = 0;
    a2[2] = 0;
    a2[1] = (void *)-1206;
  }
}

```

## disassembly

```asm
0x100486e0  mov     edi, edi
0x100486e2  push    ebp
0x100486e3  mov     ebp, esp
0x100486e5  sub     esp, 8
0x100486e8  push    ebx
0x100486e9  mov     ebx, [ebp+arg_0]
0x100486ec  push    esi
0x100486ed  push    edi
0x100486ee  push    ebx
0x100486ef  push    1
0x100486f1  mov     edi, ecx
0x100486f3  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x100486f8  mov     ecx, [ebx]
0x100486fa  test    cl, 8
0x100486fd  jnz     loc_10048970
0x10048703  mov     eax, [edi+44h]
0x10048706  test    eax, eax
0x10048708  jnz     short loc_1004871E
0x1004870a  cmp     ecx, 8
0x1004870d  jge     loc_10048970
0x10048713  test    ecx, 0FFFFFFFEh
0x10048719  jmp     loc_1004892C
0x1004871e  movzx   ecx, byte ptr [eax]
0x10048721  sub     ecx, 0
0x10048724  jz      loc_100487C6
0x1004872a  sub     ecx, 1
0x1004872d  jnz     loc_100487CD
0x10048733  xor     esi, esi
0x10048735  cmp     dword ptr [eax+esi*4+1], 0
0x1004873a  jnz     short loc_10048742
0x1004873c  inc     esi
0x1004873d  cmp     esi, 21h ; '!'
0x10048740  jl      short loc_10048735
0x10048742  cmp     esi, 20h ; ' '
0x10048745  ja      loc_100487CD
0x1004874b  mov     ecx, [eax+esi*4+1]
0x1004874f  mov     [ebp+var_4], ecx
0x10048752  test    ecx, ecx
0x10048754  jz      short loc_100487CD
0x10048756  cmp     dword ptr [edi+48h], 1
0x1004875a  lea     eax, [edi+2Ch]
0x1004875d  jnz     short loc_10048770
0x1004875f  push    0; char
0x10048761  push    dword ptr [edi+4]; struct Transaction *
0x10048764  push    ebx; struct Err *
0x10048765  push    ecx; unsigned int
0x10048766  mov     ecx, [edi]; this
0x10048768  push    eax; struct PageRef *
0x10048769  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1004876e  jmp     short loc_1004879C
0x10048770  cmp     esi, [edi+0Ch]
0x10048773  jnz     short loc_1004878D
0x10048775  mov     ecx, eax
0x10048777  call    ?HasChanged@PageRef@@QBE?AW4PDChangeStatus@@XZ; PageRef::HasChanged(void)
0x1004877c  test    eax, eax
0x1004877e  jnz     short loc_10048787
0x10048780  mov     eax, 1
0x10048785  jmp     short loc_100487CF
0x10048787  mov     ecx, [ebp+var_4]
0x1004878a  lea     eax, [edi+2Ch]
0x1004878d  push    dword ptr [edi+4]; struct Transaction *
0x10048790  push    ebx; struct Err *
0x10048791  push    1; char
0x10048793  push    ecx; unsigned int
0x10048794  mov     ecx, [edi]; this
0x10048796  push    eax; struct PageRef *
0x10048797  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1004879c  test    byte ptr [ebx], 8
0x1004879f  jnz     short loc_100487CD
0x100487a1  mov     eax, [edi+2Ch]
0x100487a4  mov     eax, [eax+40h]
0x100487a7  mov     [edi+34h], eax
0x100487aa  mov     [edi+0Ch], esi
0x100487ad  mov     eax, [edi+30h]
0x100487b0  add     eax, 4
0x100487b3  mov     dword ptr [edi+14h], 7FCh
0x100487ba  mov     [edi+10h], eax
0x100487bd  imul    eax, esi, 3FE0h
0x100487c3  mov     [edi+18h], eax
0x100487c6  mov     eax, 1
0x100487cb  jmp     short loc_100487CF
0x100487cd  xor     eax, eax
0x100487cf  cmp     eax, 1
0x100487d2  jnz     loc_10048970
0x100487d8  nop     dword ptr [eax+eax+00000000h]
0x100487e0  test    byte ptr [ebx], 8
0x100487e3  jnz     loc_10048970
0x100487e9  mov     eax, [edi+14h]
0x100487ec  lea     ecx, [edi+10h]; this
0x100487ef  mov     edx, [ecx+8]; unsigned int
0x100487f2  push    ebx; struct Err *
0x100487f3  shl     eax, 3
0x100487f6  push    eax; unsigned int
0x100487f7  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x100487fc  mov     eax, [edi+44h]
0x100487ff  movzx   eax, byte ptr [eax]
0x10048802  sub     eax, 0
0x10048805  jz      short loc_1004881C
0x10048807  sub     eax, 1
0x1004880a  jnz     short loc_10048833
0x1004880c  mov     ecx, [edi+2Ch]
0x1004880f  mov     eax, [ecx+18h]
0x10048812  or      dword ptr [ecx+eax*4+1Ch], 8
0x10048817  inc     dword ptr [ecx+40h]
0x1004881a  jmp     short loc_10048833
0x1004881c  mov     ecx, [edi+1Ch]
0x1004881f  mov     eax, [ecx+18h]
0x10048822  or      dword ptr [ecx+eax*4+1Ch], 8
0x10048827  inc     dword ptr [ecx+40h]
0x1004882a  mov     eax, [edi+1Ch]
0x1004882d  mov     eax, [eax+40h]
0x10048830  mov     [edi+24h], eax
0x10048833  mov     ecx, [edi+44h]
0x10048836  mov     esi, [edi+18h]
0x10048839  mov     [ebp+var_4], 0
0x10048840  test    ecx, ecx
0x10048842  jz      loc_10048920
0x10048848  movzx   eax, byte ptr [ecx]
0x1004884b  sub     eax, 0
0x1004884e  jz      loc_1004890B
0x10048854  sub     eax, 1
0x10048857  jnz     loc_1004890B
0x1004885d  mov     eax, 804021h
0x10048862  mul     esi
0x10048864  sub     esi, edx
0x10048866  shr     esi, 1
0x10048868  add     esi, edx
0x1004886a  shr     esi, 0Dh
0x1004886d  inc     esi
0x1004886e  cmp     esi, 21h ; '!'
0x10048871  jge     short loc_10048880
0x10048873  cmp     dword ptr [ecx+esi*4+1], 0
0x10048878  jnz     short loc_10048880
0x1004887a  inc     esi
0x1004887b  cmp     esi, 21h ; '!'
0x1004887e  jl      short loc_10048873
0x10048880  cmp     esi, 20h ; ' '
0x10048883  ja      loc_1004890B
0x10048889  mov     ecx, [ecx+esi*4+1]
0x1004888d  mov     [ebp+var_8], ecx
0x10048890  test    ecx, ecx
0x10048892  jz      short loc_1004890B
0x10048894  cmp     dword ptr [edi+48h], 1
0x10048898  lea     eax, [edi+2Ch]
0x1004889b  jnz     short loc_100488AE
0x1004889d  push    0; char
0x1004889f  push    dword ptr [edi+4]; struct Transaction *
0x100488a2  push    ebx; struct Err *
0x100488a3  push    ecx; unsigned int
0x100488a4  mov     ecx, [edi]; this
0x100488a6  push    eax; struct PageRef *
0x100488a7  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x100488ac  jmp     short loc_100488DA
0x100488ae  cmp     esi, [edi+0Ch]
0x100488b1  jnz     short loc_100488CB
0x100488b3  mov     ecx, eax
0x100488b5  call    ?HasChanged@PageRef@@QBE?AW4PDChangeStatus@@XZ; PageRef::HasChanged(void)
0x100488ba  test    eax, eax
0x100488bc  jnz     short loc_100488C5
0x100488be  mov     eax, 1
0x100488c3  jmp     short loc_1004890E
0x100488c5  mov     ecx, [ebp+var_8]
0x100488c8  lea     eax, [edi+2Ch]
0x100488cb  push    dword ptr [edi+4]; struct Transaction *
0x100488ce  push    ebx; struct Err *
0x100488cf  push    1; char
0x100488d1  push    ecx; unsigned int
0x100488d2  mov     ecx, [edi]; this
0x100488d4  push    eax; struct PageRef *
0x100488d5  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x100488da  test    byte ptr [ebx], 8
0x100488dd  jnz     short loc_1004890B
0x100488df  mov     eax, [edi+2Ch]
0x100488e2  mov     eax, [eax+40h]
0x100488e5  mov     [edi+34h], eax
0x100488e8  mov     [edi+0Ch], esi
0x100488eb  mov     eax, [edi+30h]
0x100488ee  add     eax, 4
0x100488f1  mov     dword ptr [edi+14h], 7FCh
0x100488f8  mov     [edi+10h], eax
0x100488fb  imul    eax, esi, 3FE0h
0x10048901  mov     [edi+18h], eax
0x10048904  mov     eax, 1
0x10048909  jmp     short loc_1004890E
0x1004890b  mov     eax, [ebp+var_4]
0x1004890e  cmp     eax, 1
0x10048911  jz      loc_100487E0
0x10048917  pop     edi
0x10048918  pop     esi
0x10048919  pop     ebx
0x1004891a  mov     esp, ebp
0x1004891c  pop     ebp
0x1004891d  retn    4
0x10048920  mov     eax, [ebx]
0x10048922  cmp     eax, 8
0x10048925  jge     short loc_10048970
0x10048927  test    eax, 0FFFFFFFEh
0x1004892c  jz      short loc_1004894E
0x1004892e  mov     eax, [ebx+0Ch]
0x10048931  test    eax, eax
0x10048933  jz      short loc_1004893E
0x10048935  push    eax; Block
0x10048936  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004893b  add     esp, 4
0x1004893e  mov     eax, [ebx+10h]
0x10048941  test    eax, eax
0x10048943  jz      short loc_1004894E
0x10048945  push    eax; Block
0x10048946  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004894b  add     esp, 4
0x1004894e  mov     dword ptr [ebx], 8
0x10048954  mov     dword ptr [ebx+10h], 0
0x1004895b  mov     dword ptr [ebx+0Ch], 0
0x10048962  mov     dword ptr [ebx+8], 0
0x10048969  mov     dword ptr [ebx+4], 0FFFFFB4Ah
0x10048970  pop     edi
0x10048971  pop     esi
0x10048972  pop     ebx
0x10048973  mov     esp, ebp
0x10048975  pop     ebp
0x10048976  retn    4
```
