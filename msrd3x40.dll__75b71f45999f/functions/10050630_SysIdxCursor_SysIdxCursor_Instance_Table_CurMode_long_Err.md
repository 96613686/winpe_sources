# SysIdxCursor::SysIdxCursor(Instance *,Table *,CurMode,long,Err &)

- ea: `0x10050630`
- end: `0x1005086e`
- name: `??0SysIdxCursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@JAAVErr@@@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1002ad10`

## callees

- `0x10019240`
- `0x10019960`
- `0x10025ee0`
- `0x100336e0`
- `0x10050630`
- `0x100518a0`
- `0x10051e80`
- `0x100544e0`
- `0x10059320`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
char *__thiscall SysIdxCursor::SysIdxCursor(char *this, int a2, int a3, int a4, int a5, struct Err *a6)
{
  int v7; // eax
  int v8; // eax
  Table *v9; // eax
  int v10; // ecx
  Table *v11; // edi
  Table *v12; // ecx
  int v13; // edi
  void *v14; // edi
  struct Session *v16; // [esp-8h] [ebp-2Ch]
  void *Block; // [esp+14h] [ebp-10h]
  Table *Blocka; // [esp+14h] [ebp-10h]

  Cursor::Cursor(this, a2, a3, 1, 0, a6, 0);
  *(_DWORD *)this = &SysIdxCursor::`vftable';
  *((_DWORD *)this + 100) = &Mover::`vftable';
  *((_DWORD *)this + 91) = a2;
  *((_DWORD *)this + 92) = *(_DWORD *)(*(_DWORD *)(a2 + 12) + 52);
  *((_DWORD *)this + 93) = 0;
  *((_DWORD *)this + 94) = a3;
  *((_DWORD *)this + 95) = 1;
  *((_DWORD *)this + 96) = a5;
  *((_DWORD *)this + 97) = 3;
  if ( a5 < 0 || a5 >= *(_DWORD *)(a3 + 24) || *(_DWORD *)(a3 + 4 * a5 + 1524) == -1 )
  {
    v7 = 0;
  }
  else
  {
    _mm_lfence();
    v7 = *(_DWORD *)(a3 + 4 * *(_DWORD *)(a3 + 4 * a5 + 1524) + 1396);
  }
  Block = (void *)(a5 + 381);
  *((_DWORD *)this + 98) = *(_DWORD *)(*(_DWORD *)(v7 + 8) + 40) + *(_DWORD *)(*(_DWORD *)(v7 + 8) + 44);
  if ( a5 < 0 || a5 >= *(_DWORD *)(a3 + 24) || *(_DWORD *)(a3 + 4 * (_DWORD)Block) == -1 )
  {
    v8 = 0;
  }
  else
  {
    _mm_lfence();
    v8 = *(_DWORD *)(a3 + 4 * *(_DWORD *)(a3 + 4 * (_DWORD)Block) + 1396);
  }
  *((_DWORD *)this + 99) = *(_DWORD *)(*(_DWORD *)(v8 + 8) + 48) + *(_DWORD *)(*(_DWORD *)(v8 + 8) + 52);
  *((_DWORD *)this + 9) = this + 400;
  if ( (*(_BYTE *)a6 & 8) != 0 )
    return this;
  Blocka = (Table *)operator new(0x778u);
  v9 = Table::Table(Blocka, *(struct Database **)(*((_DWORD *)this + 92) + 16), a6);
  v11 = v9;
  *((_DWORD *)this + 93) = v9;
  if ( !v9 )
  {
    Err::SetError(a6, -1011, v10);
    goto LABEL_16;
  }
  if ( (*(_BYTE *)a6 & 8) != 0 )
  {
    Table::~Table(v9);
    operator delete(v11);
    *((_DWORD *)this + 93) = 0;
LABEL_16:
    if ( (*(_BYTE *)a6 & 8) != 0 )
      return this;
  }
  v12 = (Table *)*((_DWORD *)this + 93);
  v16 = *(struct Session **)(a2 + 12);
  *((_DWORD *)v12 + 12) = 8;
  Table::AddSession(v12, v16, a6);
  if ( (*(_BYTE *)a6 & 8) == 0 )
  {
    v13 = 0;
    while ( (*(_BYTE *)a6 & 8) == 0 )
    {
      Table::AddColumn(
        *((Table **)this + 93),
        *((struct Instance **)this + 92),
        (&off_10002330)[9 * v13],
        (const struct tagTblColDef *)&dword_10002334[9 * v13],
        a6);
      if ( ++v13 >= 1 )
      {
        if ( (*(_BYTE *)a6 & 8) == 0 )
        {
          ++*(_DWORD *)(*((_DWORD *)this + 93) + 76);
          return this;
        }
        break;
      }
    }
    v14 = (void *)*((_DWORD *)this + 93);
    if ( v14 )
    {
      Table::~Table(*((Table **)this + 93));
      operator delete(v14);
    }
    *((_DWORD *)this + 93) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x10050630  mov     edi, edi
0x10050632  push    ebp
0x10050633  mov     ebp, esp
0x10050635  push    0FFFFFFFFh
0x10050637  push    offset ??0SysIdxCursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@JAAVErr@@@Z_SEH
0x1005063c  mov     eax, large fs:0
0x10050642  push    eax
0x10050643  sub     esp, 8
0x10050646  push    ebx
0x10050647  push    esi
0x10050648  push    edi
0x10050649  mov     eax, ___security_cookie
0x1005064e  xor     eax, ebp
0x10050650  push    eax
0x10050651  lea     eax, [ebp+var_C]
0x10050654  mov     large fs:0, eax
0x1005065a  mov     esi, ecx
0x1005065c  mov     [ebp+var_14], esi
0x1005065f  mov     ebx, [ebp+arg_10]
0x10050662  mov     edi, [ebp+arg_4]
0x10050665  mov     eax, [ebp+arg_0]
0x10050668  push    0
0x1005066a  push    ebx
0x1005066b  push    0
0x1005066d  push    1
0x1005066f  push    edi
0x10050670  push    eax
0x10050671  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x10050676  mov     [ebp+var_4], 0
0x1005067d  mov     dword ptr [esi], offset ??_7SysIdxCursor@@6B@; const SysIdxCursor::`vftable'
0x10050683  mov     dword ptr [esi+190h], offset ??_7Mover@@6B@; const Mover::`vftable'
0x1005068d  mov     eax, [ebp+arg_0]
0x10050690  mov     edx, [ebp+arg_C]
0x10050693  mov     byte ptr [ebp+var_4], 1
0x10050697  mov     [esi+16Ch], eax
0x1005069d  mov     eax, [eax+0Ch]
0x100506a0  mov     eax, [eax+34h]
0x100506a3  mov     [esi+170h], eax
0x100506a9  mov     dword ptr [esi+174h], 0
0x100506b3  mov     [esi+178h], edi
0x100506b9  mov     dword ptr [esi+17Ch], 1
0x100506c3  mov     [esi+180h], edx
0x100506c9  mov     dword ptr [esi+184h], 3
0x100506d3  test    edx, edx
0x100506d5  js      short loc_100506F9
0x100506d7  cmp     edx, [edi+18h]
0x100506da  jge     short loc_100506F9
0x100506dc  cmp     dword ptr [edi+edx*4+5F4h], 0FFFFFFFFh
0x100506e4  jz      short loc_100506F9
0x100506e6  lfence
0x100506e9  mov     eax, [edi+edx*4+5F4h]
0x100506f0  mov     eax, [edi+eax*4+574h]
0x100506f7  jmp     short loc_100506FB
0x100506f9  xor     eax, eax
0x100506fb  mov     eax, [eax+8]
0x100506fe  mov     ebx, 17Dh
0x10050703  mov     ecx, edx
0x10050705  add     ecx, ebx
0x10050707  mov     ebx, [ebp+arg_10]
0x1005070a  mov     [ebp+Block], ecx
0x1005070d  mov     ecx, [eax+2Ch]
0x10050710  add     ecx, [eax+28h]
0x10050713  mov     [esi+188h], ecx
0x10050719  test    edx, edx
0x1005071b  js      short loc_1005073A
0x1005071d  cmp     edx, [edi+18h]
0x10050720  jge     short loc_1005073A
0x10050722  mov     eax, [ebp+Block]
0x10050725  cmp     dword ptr [edi+eax*4], 0FFFFFFFFh
0x10050729  jz      short loc_1005073A
0x1005072b  lfence
0x1005072e  mov     eax, [edi+eax*4]
0x10050731  mov     eax, [edi+eax*4+574h]
0x10050738  jmp     short loc_1005073C
0x1005073a  xor     eax, eax
0x1005073c  mov     eax, [eax+8]
0x1005073f  mov     ecx, [eax+34h]
0x10050742  add     ecx, [eax+30h]
0x10050745  lea     eax, [esi+190h]
0x1005074b  mov     [esi+18Ch], ecx
0x10050751  mov     [esi+24h], eax
0x10050754  test    byte ptr [ebx], 8
0x10050757  jnz     loc_10050858
0x1005075d  push    778h; Size
0x10050762  call    ??2@YAPAXI@Z; operator new(uint)
0x10050767  add     esp, 4
0x1005076a  mov     [ebp+Block], eax
0x1005076d  mov     byte ptr [ebp+var_4], 2
0x10050771  mov     ecx, [esi+170h]
0x10050777  push    ebx; struct Err *
0x10050778  push    dword ptr [ecx+10h]; struct Database *
0x1005077b  mov     ecx, eax; this
0x1005077d  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10050782  mov     edi, eax
0x10050784  mov     byte ptr [ebp+var_4], 1
0x10050788  mov     [esi+174h], edi
0x1005078e  test    edi, edi
0x10050790  jnz     short loc_100507A1
0x10050792  push    ecx
0x10050793  push    0FFFFFC0Dh
0x10050798  mov     ecx, ebx
0x1005079a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005079f  jmp     short loc_100507C5
0x100507a1  test    byte ptr [ebx], 8
0x100507a4  jz      short loc_100507CE
0x100507a6  mov     ecx, edi; this
0x100507a8  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x100507ad  push    778h; unsigned int
0x100507b2  push    edi; Block
0x100507b3  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100507b8  add     esp, 8
0x100507bb  mov     dword ptr [esi+174h], 0
0x100507c5  test    byte ptr [ebx], 8
0x100507c8  jnz     loc_10050858
0x100507ce  mov     eax, [ebp+arg_0]
0x100507d1  mov     ecx, [esi+174h]; this
0x100507d7  push    ebx; struct Err *
0x100507d8  mov     eax, [eax+0Ch]
0x100507db  push    eax; struct Session *
0x100507dc  mov     dword ptr [ecx+30h], 8
0x100507e3  call    ?AddSession@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::AddSession(Session *,Err &)
0x100507e8  test    byte ptr [ebx], 8
0x100507eb  jnz     short loc_10050858
0x100507ed  xor     edi, edi
0x100507ef  nop
0x100507f0  test    byte ptr [ebx], 8
0x100507f3  jnz     short loc_1005082F
0x100507f5  lea     ecx, [edi+edi*8]
0x100507f8  push    ebx; struct Err *
0x100507f9  lea     eax, dword_10002334[ecx*4]
0x10050800  push    eax; struct tagTblColDef *
0x10050801  push    ds:off_10002330[ecx*4]; unsigned __int16 *
0x10050808  mov     ecx, [esi+174h]; this
0x1005080e  push    dword ptr [esi+170h]; struct Instance *
0x10050814  call    ?AddColumn@Table@@QAEPAVColumn@@PAVInstance@@PBGPBUtagTblColDef@@AAVErr@@@Z; Table::AddColumn(Instance *,ushort const *,tagTblColDef const *,Err &)
0x10050819  inc     edi
0x1005081a  cmp     edi, 1
0x1005081d  jl      short loc_100507F0
0x1005081f  test    byte ptr [ebx], 8
0x10050822  jnz     short loc_1005082F
0x10050824  mov     eax, [esi+174h]
0x1005082a  inc     dword ptr [eax+4Ch]
0x1005082d  jmp     short loc_10050858
0x1005082f  mov     edi, [esi+174h]
0x10050835  test    edi, edi
0x10050837  jz      short loc_1005084E
0x10050839  mov     ecx, edi; this
0x1005083b  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10050840  push    778h; unsigned int
0x10050845  push    edi; Block
0x10050846  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005084b  add     esp, 8
0x1005084e  mov     dword ptr [esi+174h], 0
0x10050858  mov     eax, esi
0x1005085a  mov     ecx, [ebp+var_C]
0x1005085d  mov     large fs:0, ecx
0x10050864  pop     ecx
0x10050865  pop     edi
0x10050866  pop     esi
0x10050867  pop     ebx
0x10050868  mov     esp, ebp
0x1005086a  pop     ebp
0x1005086b  retn    14h
0x100619b0  mov     ecx, [ebp+var_14]; this
0x100619b3  jmp     ??1Cursor@@UAE@XZ; Cursor::~Cursor(void)
0x100619b8  mov     ecx, [ebp+var_14]
0x100619bb  add     ecx, 190h; this
0x100619c1  jmp     ??1Mover@@UAE@XZ; Mover::~Mover(void)
0x100619c6  push    778h; unsigned int
0x100619cb  mov     eax, [ebp+Block]
0x100619ce  push    eax; Block
0x100619cf  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100619d4  add     esp, 8
0x100619d7  retn
0x100619dd  nop
0x100619de  nop
0x100619df  mov     edx, [esp-4+arg_4]
0x100619e3  lea     eax, [edx+0Ch]
0x100619e6  mov     ecx, [edx-18h]
0x100619e9  xor     ecx, eax; StackCookie
0x100619eb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100619f0  mov     eax, offset stru_100642A0
0x100619f5  jmp     ___CxxFrameHandler3
```
