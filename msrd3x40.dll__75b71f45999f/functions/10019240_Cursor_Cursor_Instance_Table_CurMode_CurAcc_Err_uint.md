# Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)

- ea: `0x10019240`
- end: `0x10019579`
- name: `??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z`
- size: `825`
- prototype: ``
- caller_count: `15`
- callee_count: `14`
- tags: ``

## callers

- `0x1001dc70`
- `0x1001dfc0`
- `0x1002a480`
- `0x1002ad10`
- `0x1002b2e0`
- `0x10035910`
- `0x10035f50`
- `0x10036910`
- `0x10044e20`
- `0x1004faf0`
- `0x10050100`
- `0x10050630`
- `0x10056b70`
- `0x10058210`
- `0x10058c40`

## callees

- `0x1000eb60`
- `0x10012db0`
- `0x10012dd0`
- `0x10019240`
- `0x10025ee0`
- `0x10026020`
- `0x10047d30`
- `0x10047e10`
- `0x1004be70`
- `0x100593b0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
int __thiscall Cursor::Cursor(int this, int a2, int a3, int a4, int a5, Err *a6, int a7)
{
  int v8; // edi
  int v9; // esi
  int v10; // eax
  int v11; // eax
  struct Err *v12; // esi
  SortMover *v13; // eax
  int v14; // ecx
  int v15; // edx
  int v16; // eax
  int v17; // ecx
  int v18; // edx
  int v19; // eax
  int v20; // ecx
  Collection *v21; // edi
  unsigned int v22; // eax
  _DWORD *v23; // edi
  unsigned int v24; // eax
  _DWORD *v25; // edi
  unsigned int v26; // eax
  int v27; // eax
  TableMover *v29; // eax
  SortMover *Block; // [esp+10h] [ebp-18h]
  TableMover *Blocka; // [esp+10h] [ebp-18h]
  int v32; // [esp+18h] [ebp-10h]

  *(_DWORD *)this = &Cursor::`vftable';
  *(_DWORD *)(this + 4) = a2;
  *(_DWORD *)(this + 8) = *(_DWORD *)(a2 + 12);
  AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)(this + 140));
  AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)(this + 236));
  *(_DWORD *)(this + 352) = 0;
  *(_DWORD *)(this + 356) = 0;
  *(_DWORD *)(this + 348) = 0;
  v8 = 0;
  *(_DWORD *)(this + 20) = a5;
  *(_DWORD *)(this + 12) = a3;
  *(_DWORD *)(this + 16) = a4;
  *(_DWORD *)(this + 24) = 0;
  *(_DWORD *)(this + 28) = 0;
  *(_DWORD *)(this + 40) = *(_DWORD *)(a2 + 60);
  *(_WORD *)(this + 48) = -1;
  *(_DWORD *)(this + 52) = 0;
  *(_DWORD *)(this + 44) = 3;
  *(_DWORD *)(this + 64) = -1;
  v9 = *(_DWORD *)(this + 4);
  v32 = 0;
  v10 = *(_DWORD *)(*(_DWORD *)(a2 + 12) + 56);
  *(_DWORD *)(this + 332) &= 0xFFFFFFF0;
  *(_DWORD *)(this + 68) = v10;
  *(_DWORD *)(this + 72) = 0;
  *(_DWORD *)(this + 76) = 0;
  *(_DWORD *)(this + 80) = 0;
  *(_DWORD *)(this + 84) = 0;
  *(_DWORD *)(this + 88) = 0;
  *(_DWORD *)(this + 92) = 0;
  *(_DWORD *)(this + 336) = 1;
  *(_DWORD *)(this + 340) = 0;
  *(_DWORD *)(this + 360) = 0;
  v11 = *(_DWORD *)(*(_DWORD *)(v9 + 16) + 104);
  if ( !v11 || v11 == 3 )
    *(_DWORD *)(this + 16) = 0;
  *(_DWORD *)(this + 360) = *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(v9 + 16) + 60) + 104);
  if ( a4 == 6 )
  {
    Block = (SortMover *)operator new(0x8Cu);
    v12 = a6;
    v13 = SortMover::SortMover(Block, (struct Cursor *)this, (void **)a6);
    *(_DWORD *)(this + 32) = v13;
    if ( !v13 )
    {
LABEL_6:
      Err::SetError(v12, -1011, v14);
      goto LABEL_10;
    }
    if ( (*(_BYTE *)a6 & 8) != 0 )
    {
      (**(void (__thiscall ***)(SortMover *, int))v13)(v13, 1);
      *(_DWORD *)(this + 32) = 0;
LABEL_9:
      v12 = a6;
    }
  }
  else if ( *(_DWORD *)(a3 + 28) )
  {
    Blocka = (TableMover *)operator new(0x44u);
    v29 = TableMover::TableMover(Blocka, (struct Cursor *)this);
    v12 = a6;
    *(_DWORD *)(this + 32) = v29;
    if ( !v29 )
      goto LABEL_6;
    if ( !a7 )
      v8 = 1;
    v32 = v8;
  }
  else
  {
    *(_DWORD *)(this + 32) = 0;
    if ( *(_DWORD *)(a3 + 44) == 9 )
      goto LABEL_9;
    v12 = a6;
    Err::SetError(a6, -1206, a3);
  }
LABEL_10:
  v15 = *(_DWORD *)(*(_DWORD *)(this + 12) + 28);
  v16 = *(_DWORD *)(this + 40);
  v17 = *(_DWORD *)(v16 + 8);
  *(_DWORD *)(this + 140) = v17;
  *(_DWORD *)(this + 144) = v16;
  *(_DWORD *)(this + 148) = v15;
  *(_DWORD *)(this + 232) = *(_DWORD *)(*(_DWORD *)(v17 + 60) + 104);
  v18 = *(_DWORD *)(*(_DWORD *)(this + 12) + 32);
  v19 = *(_DWORD *)(this + 40);
  v20 = *(_DWORD *)(v19 + 8);
  *(_DWORD *)(this + 236) = v20;
  *(_DWORD *)(this + 240) = v19;
  *(_DWORD *)(this + 244) = v18;
  *(_DWORD *)(this + 328) = *(_DWORD *)(*(_DWORD *)(v20 + 60) + 104);
  v21 = *(Collection **)(this + 4);
  if ( *(_DWORD *)(*((_DWORD *)v21 + 4) + 68) == 1 )
    *(_DWORD *)(this + 196) = 2;
  *(_DWORD *)(this + 36) = *(_DWORD *)(this + 32);
  if ( (*(_BYTE *)v12 & 8) == 0 )
  {
    v22 = *((_DWORD *)v21 + 2);
    if ( v22 < *((_DWORD *)v21 + 1) || (Collection::Grow(v21, v22 + 1, v12), (*(_BYTE *)v12 & 8) == 0) )
    {
      *(_DWORD *)(*(_DWORD *)v21 + 4 * (*((_DWORD *)v21 + 2))++) = this;
      if ( (*(_BYTE *)v12 & 8) == 0 )
      {
        v23 = *(_DWORD **)(this + 12);
        v24 = v23[28];
        if ( v24 < v23[27] || (Collection::Grow((Collection *)(v23 + 26), v24 + 1, v12), (*(_BYTE *)v12 & 8) == 0) )
        {
          *(_DWORD *)(v23[26] + 4 * v23[28]++) = this;
          if ( (*(_BYTE *)v12 & 8) == 0 )
          {
            v25 = *(_DWORD **)(this + 8);
            v26 = v25[8];
            if ( v26 < v25[7] || (Collection::Grow((Collection *)(v25 + 6), v26 + 1, v12), (*(_BYTE *)v12 & 8) == 0) )
              *(_DWORD *)(v25[6] + 4 * v25[8]++) = this;
          }
        }
      }
    }
  }
  v27 = *(_DWORD *)(this + 12);
  *(_DWORD *)(this + 108) = this;
  *(_BYTE *)(this + 128) = 0;
  ++*(_DWORD *)(v27 + 76);
  if ( v32 )
  {
    if ( (*(_BYTE *)v12 & 8) == 0 )
    {
      (*(void (__thiscall **)(_DWORD, int, _DWORD, struct Err *))(**(_DWORD **)(this + 32) + 8))(
        *(_DWORD *)(this + 32),
        1,
        0,
        v12);
      if ( (*(_BYTE *)a6 & 1) == 0 && *((_DWORD *)a6 + 1) == -1603 )
        Err::Reset(a6);
    }
  }
  return this;
}

```

## disassembly

```asm
0x10019240  mov     edi, edi
0x10019242  push    ebp
0x10019243  mov     ebp, esp
0x10019245  push    0FFFFFFFFh
0x10019247  push    offset ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z_SEH
0x1001924c  mov     eax, large fs:0
0x10019252  push    eax
0x10019253  sub     esp, 0Ch
0x10019256  push    ebx
0x10019257  push    esi
0x10019258  push    edi
0x10019259  mov     eax, ___security_cookie
0x1001925e  xor     eax, ebp
0x10019260  push    eax; unsigned int
0x10019261  lea     eax, [ebp+var_C]
0x10019264  mov     large fs:0, eax
0x1001926a  mov     ebx, ecx
0x1001926c  mov     [ebp+var_14], ebx
0x1001926f  mov     esi, [ebp+arg_0]
0x10019272  lea     ecx, [ebx+8Ch]; this
0x10019278  mov     dword ptr [ebx], offset ??_7Cursor@@6B@; const Cursor::`vftable'
0x1001927e  mov     [ebx+4], esi
0x10019281  mov     eax, [esi+0Ch]
0x10019284  mov     [ebx+8], eax
0x10019287  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x1001928c  lea     ecx, [ebx+0ECh]; this
0x10019292  mov     [ebp+var_4], 0
0x10019299  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x1001929e  mov     dword ptr [ebx+160h], 0
0x100192a8  mov     dword ptr [ebx+164h], 0
0x100192b2  mov     dword ptr [ebx+15Ch], 0
0x100192bc  mov     eax, [ebp+arg_C]
0x100192bf  xor     edi, edi
0x100192c1  mov     ecx, [ebp+arg_4]
0x100192c4  mov     edx, [ebp+arg_8]
0x100192c7  mov     byte ptr [ebp+var_4], 2
0x100192cb  mov     [ebx+14h], eax
0x100192ce  mov     [ebx+0Ch], ecx
0x100192d1  mov     [ebx+10h], edx
0x100192d4  mov     [ebx+18h], edi
0x100192d7  mov     [ebx+1Ch], edi
0x100192da  mov     eax, [esi+3Ch]
0x100192dd  mov     [ebx+28h], eax
0x100192e0  mov     eax, 0FFFFh
0x100192e5  mov     [ebx+30h], ax
0x100192e9  mov     [ebx+34h], edi
0x100192ec  mov     dword ptr [ebx+2Ch], 3
0x100192f3  mov     dword ptr [ebx+40h], 0FFFFFFFFh
0x100192fa  mov     eax, [esi+0Ch]
0x100192fd  mov     esi, [ebx+4]
0x10019300  mov     [ebp+var_10], edi
0x10019303  mov     eax, [eax+38h]
0x10019306  and     dword ptr [ebx+14Ch], 0FFFFFFF0h
0x1001930d  mov     [ebx+44h], eax
0x10019310  mov     [ebx+48h], edi
0x10019313  mov     [ebx+4Ch], edi
0x10019316  mov     [ebx+50h], edi
0x10019319  mov     [ebx+54h], edi
0x1001931c  mov     [ebx+58h], edi
0x1001931f  mov     [ebx+5Ch], edi
0x10019322  mov     dword ptr [ebx+150h], 1
0x1001932c  mov     [ebx+154h], edi
0x10019332  mov     [ebx+168h], edi
0x10019338  mov     eax, [esi+10h]
0x1001933b  mov     eax, [eax+68h]
0x1001933e  test    eax, eax
0x10019340  jz      short loc_10019347
0x10019342  cmp     eax, 3
0x10019345  jnz     short loc_1001934A
0x10019347  mov     [ebx+10h], edi
0x1001934a  mov     eax, [esi+10h]
0x1001934d  mov     eax, [eax+3Ch]
0x10019350  mov     eax, [eax+68h]
0x10019353  mov     [ebx+168h], eax
0x10019359  cmp     edx, 6
0x1001935c  jnz     loc_1001950E
0x10019362  push    8Ch; Size
0x10019367  call    ??2@YAPAXI@Z; operator new(uint)
0x1001936c  add     esp, 4
0x1001936f  mov     [ebp+Block], eax
0x10019372  mov     esi, [ebp+arg_10]
0x10019375  mov     ecx, eax; this
0x10019377  push    esi; struct Err *
0x10019378  push    ebx; struct Cursor *
0x10019379  mov     byte ptr [ebp+var_4], 3
0x1001937d  call    ??0SortMover@@QAE@PAVCursor@@AAVErr@@@Z; SortMover::SortMover(Cursor *,Err &)
0x10019382  mov     edi, eax
0x10019384  mov     byte ptr [ebp+var_4], 2
0x10019388  mov     [ebx+20h], edi
0x1001938b  test    edi, edi
0x1001938d  jnz     short loc_1001939E
0x1001938f  push    ecx
0x10019390  push    0FFFFFC0Dh
0x10019395  mov     ecx, esi
0x10019397  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001939c  jmp     short loc_100193BF
0x1001939e  test    byte ptr [esi], 8
0x100193a1  jz      short loc_100193BF
0x100193a3  mov     eax, [edi]
0x100193a5  push    1; void *
0x100193a7  mov     esi, [eax]
0x100193a9  mov     ecx, esi
0x100193ab  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100193b1  mov     ecx, edi
0x100193b3  call    esi
0x100193b5  mov     dword ptr [ebx+20h], 0
0x100193bc  mov     esi, [ebp+arg_10]
0x100193bf  mov     eax, [ebx+0Ch]
0x100193c2  mov     edx, [eax+1Ch]
0x100193c5  mov     eax, [ebx+28h]
0x100193c8  mov     ecx, [eax+8]
0x100193cb  mov     [ebx+8Ch], ecx
0x100193d1  mov     [ebx+90h], eax
0x100193d7  mov     [ebx+94h], edx
0x100193dd  mov     eax, [ecx+3Ch]
0x100193e0  mov     eax, [eax+68h]
0x100193e3  mov     [ebx+0E8h], eax
0x100193e9  mov     eax, [ebx+0Ch]
0x100193ec  mov     edx, [eax+20h]
0x100193ef  mov     eax, [ebx+28h]
0x100193f2  mov     ecx, [eax+8]
0x100193f5  mov     [ebx+0ECh], ecx
0x100193fb  mov     [ebx+0F0h], eax
0x10019401  mov     [ebx+0F4h], edx
0x10019407  mov     eax, [ecx+3Ch]
0x1001940a  mov     eax, [eax+68h]
0x1001940d  mov     [ebx+148h], eax
0x10019413  mov     edi, [ebx+4]
0x10019416  mov     eax, [edi+10h]
0x10019419  cmp     dword ptr [eax+44h], 1
0x1001941d  jnz     short loc_10019429
0x1001941f  mov     dword ptr [ebx+0C4h], 2
0x10019429  mov     eax, [ebx+20h]
0x1001942c  mov     [ebx+24h], eax
0x1001942f  test    byte ptr [esi], 8
0x10019432  jnz     short loc_100194AE
0x10019434  mov     eax, [edi+8]
0x10019437  cmp     eax, [edi+4]
0x1001943a  jb      short loc_1001944B
0x1001943c  push    esi; struct Err *
0x1001943d  inc     eax
0x1001943e  mov     ecx, edi; this
0x10019440  push    eax; unsigned int
0x10019441  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10019446  test    byte ptr [esi], 8
0x10019449  jnz     short loc_100194AE
0x1001944b  mov     ecx, [edi+8]
0x1001944e  mov     eax, [edi]
0x10019450  mov     [eax+ecx*4], ebx
0x10019453  inc     dword ptr [edi+8]
0x10019456  test    byte ptr [esi], 8
0x10019459  jnz     short loc_100194AE
0x1001945b  mov     edi, [ebx+0Ch]
0x1001945e  mov     eax, [edi+70h]
0x10019461  cmp     eax, [edi+6Ch]
0x10019464  jb      short loc_10019476
0x10019466  push    esi; struct Err *
0x10019467  inc     eax
0x10019468  lea     ecx, [edi+68h]; this
0x1001946b  push    eax; unsigned int
0x1001946c  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10019471  test    byte ptr [esi], 8
0x10019474  jnz     short loc_100194AE
0x10019476  mov     ecx, [edi+70h]
0x10019479  mov     eax, [edi+68h]
0x1001947c  mov     [eax+ecx*4], ebx
0x1001947f  inc     dword ptr [edi+70h]
0x10019482  test    byte ptr [esi], 8
0x10019485  jnz     short loc_100194AE
0x10019487  mov     edi, [ebx+8]
0x1001948a  mov     eax, [edi+20h]
0x1001948d  cmp     eax, [edi+1Ch]
0x10019490  jb      short loc_100194A2
0x10019492  push    esi; struct Err *
0x10019493  inc     eax
0x10019494  lea     ecx, [edi+18h]; this
0x10019497  push    eax; unsigned int
0x10019498  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x1001949d  test    byte ptr [esi], 8
0x100194a0  jnz     short loc_100194AE
0x100194a2  mov     ecx, [edi+20h]
0x100194a5  mov     eax, [edi+18h]
0x100194a8  mov     [eax+ecx*4], ebx
0x100194ab  inc     dword ptr [edi+20h]
0x100194ae  mov     eax, [ebx+0Ch]
0x100194b1  mov     [ebx+6Ch], ebx
0x100194b4  mov     byte ptr [ebx+80h], 0
0x100194bb  inc     dword ptr [eax+4Ch]
0x100194be  cmp     [ebp+var_10], 0
0x100194c2  jz      short loc_100194F8
0x100194c4  test    byte ptr [esi], 8
0x100194c7  jnz     short loc_100194F8
0x100194c9  mov     edi, [ebx+20h]
0x100194cc  push    esi
0x100194cd  push    0; unsigned int
0x100194cf  push    1; void *
0x100194d1  mov     eax, [edi]
0x100194d3  mov     esi, [eax+8]
0x100194d6  mov     ecx, esi
0x100194d8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100194de  mov     ecx, edi
0x100194e0  call    esi
0x100194e2  mov     ecx, [ebp+arg_10]; this
0x100194e5  test    byte ptr [ecx], 1
0x100194e8  jnz     short loc_100194F8
0x100194ea  cmp     dword ptr [ecx+4], 0FFFFF9BDh
0x100194f1  jnz     short loc_100194F8
0x100194f3  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x100194f8  mov     eax, ebx
0x100194fa  mov     ecx, [ebp+var_C]
0x100194fd  mov     large fs:0, ecx
0x10019504  pop     ecx
0x10019505  pop     edi
0x10019506  pop     esi
0x10019507  pop     ebx
0x10019508  mov     esp, ebp
0x1001950a  pop     ebp
0x1001950b  retn    18h
0x1001950e  cmp     [ecx+1Ch], edi
0x10019511  jnz     short loc_10019535
0x10019513  mov     [ebx+20h], edi
0x10019516  cmp     dword ptr [ecx+2Ch], 9
0x1001951a  jz      loc_100193BC
0x10019520  mov     esi, [ebp+arg_10]
0x10019523  push    ecx
0x10019524  push    0FFFFFB4Ah
0x10019529  mov     ecx, esi
0x1001952b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10019530  jmp     loc_100193BF
0x10019535  push    44h ; 'D'; Size
0x10019537  call    ??2@YAPAXI@Z; operator new(uint)
0x1001953c  add     esp, 4
0x1001953f  mov     [ebp+Block], eax
0x10019542  mov     ecx, eax; this
0x10019544  push    ebx; struct Cursor *
0x10019545  call    ??0TableMover@@QAE@PAVCursor@@@Z; TableMover::TableMover(Cursor *)
0x1001954a  mov     esi, [ebp+arg_10]
0x1001954d  mov     [ebx+20h], eax
0x10019550  test    eax, eax
0x10019552  jnz     short loc_10019566
0x10019554  push    ecx
0x10019555  push    0FFFFFC0Dh
0x1001955a  mov     ecx, esi
0x1001955c  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10019561  jmp     loc_100193BF
0x10019566  cmp     [ebp+arg_14], edi
0x10019569  mov     eax, 1
0x1001956e  cmovz   edi, eax
0x10019571  mov     [ebp+var_10], edi
0x10019574  jmp     loc_100193BF
0x1005fd20  mov     ecx, [ebp+var_14]
0x1005fd23  add     ecx, 8Ch; this
0x1005fd29  jmp     ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x1005fd2e  mov     ecx, [ebp+var_14]
0x1005fd31  add     ecx, 0ECh; this
0x1005fd37  jmp     ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x1005fd3c  mov     ecx, [ebp+var_14]
0x1005fd3f  add     ecx, 15Ch; this
0x1005fd45  jmp     ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x1005fd4a  push    8Ch; unsigned int
0x1005fd4f  mov     eax, [ebp+Block]
0x1005fd52  push    eax; Block
0x1005fd53  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005fd58  add     esp, 8
0x1005fd5b  retn
0x1005fd61  nop
0x1005fd62  nop
0x1005fd63  mov     edx, [esp-4+arg_4]
0x1005fd67  lea     eax, [edx+0Ch]
0x1005fd6a  mov     ecx, [edx-1Ch]
0x1005fd6d  xor     ecx, eax; StackCookie
0x1005fd6f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fd74  mov     eax, offset stru_10062E74
0x1005fd79  jmp     ___CxxFrameHandler3
```
