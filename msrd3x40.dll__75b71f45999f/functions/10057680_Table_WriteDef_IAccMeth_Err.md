# Table::WriteDef(IAccMeth *,Err &)

- ea: `0x10057680`
- end: `0x100577dc`
- name: `?WriteDef@Table@@AAEXPAVIAccMeth@@AAVErr@@@Z`
- size: `348`
- prototype: `void __thiscall(Table *__hidden this, struct IAccMeth *, struct Err *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10057dd0`

## callees

- `0x10010580`
- `0x10023690`
- `0x10057680`
- `0x1005a700`
- `0x1005ad80`
- `0x1005c7e0`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::WriteDef(Table *this, Database **a2, struct Err *a3)
{
  Table *v3; // edi
  Database **v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // edi
  unsigned int v7; // ebx
  bool v8; // zf
  void *v9; // eax
  unsigned int v10; // [esp+10h] [ebp-30h] BYREF
  void *Block; // [esp+14h] [ebp-2Ch]
  void *v12; // [esp+18h] [ebp-28h]
  int v13; // [esp+20h] [ebp-20h] BYREF
  int v14; // [esp+24h] [ebp-1Ch]
  unsigned int v15; // [esp+2Ch] [ebp-14h] BYREF
  Table *v16; // [esp+30h] [ebp-10h]
  int v17; // [esp+3Ch] [ebp-4h]

  v3 = this;
  v16 = this;
  v10 = *((_DWORD *)this + 10);
  Block = 0;
  v12 = 0;
  v17 = 0;
  TblPage::SaveTable((TblPage *)&v10, this, a3);
  if ( (*(_BYTE *)a3 & 8) != 0 )
    goto LABEL_13;
  v4 = a2;
  v5 = TblPage::SavePages((TblPage *)&v10, (struct IAccMeth *)a2, v10, &v15, a3);
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    v6 = v15;
    v10 = v5;
    if ( !v15 )
    {
LABEL_10:
      v3 = v16;
      goto LABEL_11;
    }
    while ( 1 )
    {
      v13 = 0;
      v14 = 0;
      LOBYTE(v17) = 1;
      Database::ReadPage(v4[2], (struct PageRef *)&v13, v6, 1, (void **)a3, (struct Transaction *)v4);
      if ( (*(_BYTE *)a3 & 8) != 0 )
        break;
      v7 = *(_DWORD *)(v14 + 4);
      Transaction::FreePage(a2, v6, 1, a3);
      if ( (*(_BYTE *)a3 & 8) != 0 )
        break;
      LOBYTE(v17) = 0;
      v6 = v7;
      if ( v13 )
        --*(_WORD *)(v13 + 76);
      v8 = v7 == 0;
      v4 = a2;
      if ( v8 )
      {
        v5 = v10;
        goto LABEL_10;
      }
    }
    v3 = v16;
    if ( v13 )
      --*(_WORD *)(v13 + 76);
  }
  v5 = v10;
LABEL_11:
  if ( (*(_BYTE *)a3 & 8) == 0 )
    *((_DWORD *)v3 + 10) = v5;
LABEL_13:
  v9 = v12;
  if ( v12 )
  {
    if ( *(_DWORD *)v12 )
      --*(_WORD *)(*(_DWORD *)v12 + 76);
    operator delete(v9);
  }
  else if ( Block )
  {
    operator delete[](Block);
  }
}

```

## disassembly

```asm
0x10057680  mov     edi, edi
0x10057682  push    ebp
0x10057683  mov     ebp, esp
0x10057685  push    0FFFFFFFFh
0x10057687  push    offset ?WriteDef@Table@@AAEXPAVIAccMeth@@AAVErr@@@Z_SEH
0x1005768c  mov     eax, large fs:0
0x10057692  push    eax
0x10057693  sub     esp, 24h
0x10057696  push    ebx
0x10057697  push    esi
0x10057698  push    edi
0x10057699  mov     eax, ___security_cookie
0x1005769e  xor     eax, ebp
0x100576a0  push    eax
0x100576a1  lea     eax, [ebp+var_C]
0x100576a4  mov     large fs:0, eax
0x100576aa  mov     edi, ecx
0x100576ac  mov     [ebp+var_10], edi
0x100576af  mov     eax, [edi+28h]
0x100576b2  mov     [ebp+var_30], eax
0x100576b5  mov     [ebp+Block], 0
0x100576bc  mov     [ebp+var_28], 0
0x100576c3  mov     esi, [ebp+arg_4]
0x100576c6  lea     ecx, [ebp+var_30]; this
0x100576c9  push    esi; struct Err *
0x100576ca  push    edi; struct Table *
0x100576cb  mov     [ebp+var_4], 0
0x100576d2  call    ?SaveTable@TblPage@@QAEXPAVTable@@AAVErr@@@Z; TblPage::SaveTable(Table *,Err &)
0x100576d7  test    byte ptr [esi], 8
0x100576da  jnz     loc_10057775
0x100576e0  mov     ebx, [ebp+arg_0]
0x100576e3  lea     eax, [ebp+var_14]
0x100576e6  push    esi; struct Err *
0x100576e7  push    eax; unsigned int *
0x100576e8  push    [ebp+var_30]; unsigned int
0x100576eb  lea     ecx, [ebp+var_30]; this
0x100576ee  push    ebx; struct IAccMeth *
0x100576ef  call    ?SavePages@TblPage@@AAEKPAVIAccMeth@@KPAKAAVErr@@@Z; TblPage::SavePages(IAccMeth *,ulong,ulong *,Err &)
0x100576f4  test    byte ptr [esi], 8
0x100576f7  jnz     loc_100577B3
0x100576fd  mov     edi, [ebp+var_14]
0x10057700  mov     [ebp+var_30], eax
0x10057703  test    edi, edi
0x10057705  jz      short loc_1005776A
0x10057707  nop     word ptr [eax+eax+00000000h]
0x10057710  mov     [ebp+var_20], 0
0x10057717  mov     [ebp+var_1C], 0
0x1005771e  push    ebx; struct Transaction *
0x1005771f  push    esi; struct Err *
0x10057720  push    1; char
0x10057722  push    edi; unsigned int
0x10057723  lea     eax, [ebp+var_20]
0x10057726  mov     byte ptr [ebp+var_4], 1
0x1005772a  mov     ecx, [ebx+8]; this
0x1005772d  push    eax; struct PageRef *
0x1005772e  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x10057733  test    byte ptr [esi], 8
0x10057736  jnz     short loc_100577A5
0x10057738  mov     eax, [ebp+var_1C]
0x1005773b  mov     ecx, [ebp+arg_0]
0x1005773e  push    esi
0x1005773f  push    1
0x10057741  mov     ebx, [eax+4]
0x10057744  push    edi
0x10057745  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x1005774a  test    byte ptr [esi], 8
0x1005774d  jnz     short loc_100577A5
0x1005774f  mov     byte ptr [ebp+var_4], 0
0x10057753  mov     edi, ebx
0x10057755  mov     eax, [ebp+var_20]
0x10057758  test    eax, eax
0x1005775a  jz      short loc_10057760
0x1005775c  dec     word ptr [eax+4Ch]
0x10057760  test    ebx, ebx
0x10057762  mov     ebx, [ebp+arg_0]
0x10057765  jnz     short loc_10057710
0x10057767  mov     eax, [ebp+var_30]
0x1005776a  mov     edi, [ebp+var_10]
0x1005776d  test    byte ptr [esi], 8
0x10057770  jnz     short loc_10057775
0x10057772  mov     [edi+28h], eax
0x10057775  mov     eax, [ebp+var_28]
0x10057778  test    eax, eax
0x1005777a  jz      short loc_100577B8
0x1005777c  mov     ecx, [eax]
0x1005777e  test    ecx, ecx
0x10057780  jz      short loc_10057786
0x10057782  dec     word ptr [ecx+4Ch]
0x10057786  push    0Ch; unsigned int
0x10057788  push    eax; Block
0x10057789  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005778e  add     esp, 8
0x10057791  mov     ecx, [ebp+var_C]
0x10057794  mov     large fs:0, ecx
0x1005779b  pop     ecx
0x1005779c  pop     edi
0x1005779d  pop     esi
0x1005779e  pop     ebx
0x1005779f  mov     esp, ebp
0x100577a1  pop     ebp
0x100577a2  retn    8
0x100577a5  mov     eax, [ebp+var_20]
0x100577a8  mov     edi, [ebp+var_10]
0x100577ab  test    eax, eax
0x100577ad  jz      short loc_100577B3
0x100577af  dec     word ptr [eax+4Ch]
0x100577b3  mov     eax, [ebp+var_30]
0x100577b6  jmp     short loc_1005776D
0x100577b8  mov     eax, [ebp+Block]
0x100577bb  test    eax, eax
0x100577bd  jz      short loc_100577C8
0x100577bf  push    eax; Block
0x100577c0  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100577c5  add     esp, 4
0x100577c8  mov     ecx, [ebp+var_C]
0x100577cb  mov     large fs:0, ecx
0x100577d2  pop     ecx
0x100577d3  pop     edi
0x100577d4  pop     esi
0x100577d5  pop     ebx
0x100577d6  mov     esp, ebp
0x100577d8  pop     ebp
0x100577d9  retn    8
0x10062120  lea     ecx, [ebp+var_30]; this
0x10062123  jmp     ??1TblPage@@QAE@XZ; TblPage::~TblPage(void)
0x10062128  lea     ecx, [ebp+var_20]; this
0x1006212b  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x10062135  nop
0x10062136  nop
0x10062137  mov     edx, [esp-4+arg_4]
0x1006213b  lea     eax, [edx+0Ch]
0x1006213e  mov     ecx, [edx-34h]
0x10062141  xor     ecx, eax; StackCookie
0x10062143  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10062148  mov     eax, offset stru_1006481C
0x1006214d  jmp     ___CxxFrameHandler3
```
