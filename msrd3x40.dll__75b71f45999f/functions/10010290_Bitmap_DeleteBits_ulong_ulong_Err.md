# Bitmap::DeleteBits(ulong,ulong,Err &)

- ea: `0x10010290`
- end: `0x100104f9`
- name: `?DeleteBits@Bitmap@@QAEXKKAAVErr@@@Z`
- size: `617`
- prototype: `void __thiscall(Bitmap *__hidden this, unsigned int, unsigned int, struct Err *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100326a0`

## callees

- `0x1000fc30`
- `0x10010290`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall Bitmap::DeleteBits(Bitmap *this, unsigned int a2, unsigned int a3, void **a4)
{
  Bitmap *v4; // edx
  unsigned int v5; // ebx
  struct Err *v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // edx
  bool v11; // zf
  unsigned int v12; // eax
  int v13; // edx
  int v14; // ecx
  unsigned __int16 v15; // ax
  unsigned int v16; // edx
  int v17; // [esp+Ch] [ebp-10h]
  unsigned int v18; // [esp+Ch] [ebp-10h]
  int v19; // [esp+10h] [ebp-Ch]
  int v20; // [esp+10h] [ebp-Ch]
  unsigned int v21; // [esp+14h] [ebp-8h]

  v4 = this;
  v5 = a2;
  v6 = (struct Err *)a4;
  v7 = *((_DWORD *)this + 2) + 8 * *((_DWORD *)this + 1) - 1;
  v8 = a2 + a3;
  v21 = v7;
  if ( (a2 & 7) != 0 )
  {
    while ( 1 )
    {
      if ( v8 > v7 )
        goto LABEL_18;
      v9 = *((_DWORD *)v4 + 2);
      v19 = *(_DWORD *)v4;
      v10 = v5 - v9;
      v11 = (*(_BYTE *)(((v8 - v9) >> 3) + v19) & *((_BYTE *)&Bitmap::ThisBit + ((v8 - v9) & 7))) == 0;
      v6 = (struct Err *)a4;
      v12 = 8 * *((_DWORD *)this + 1);
      if ( v11 )
        break;
      if ( v10 >= v12 )
        goto LABEL_8;
      if ( v10 >> 3 < *((_DWORD *)this + 1) )
        *(_BYTE *)((v10 >> 3) + v19) |= *((_BYTE *)&Bitmap::ThisBit + (v10 & 7));
LABEL_17:
      v7 = v21;
      ++v5;
      v4 = this;
      ++v8;
      if ( (v5 & 7) == 0 )
        goto LABEL_18;
    }
    if ( v10 < v12 )
    {
      if ( v10 >> 3 < *((_DWORD *)this + 1) )
        *(_BYTE *)((v10 >> 3) + v19) &= ~*((_BYTE *)&Bitmap::ThisBit + (v10 & 7));
      goto LABEL_17;
    }
LABEL_8:
    if ( (int)*a4 < 8 )
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
    goto LABEL_17;
  }
LABEL_18:
  if ( v8 + 7 < v21 )
  {
    v13 = (v5 >> 3) + *(_DWORD *)v4;
    v14 = (v8 >> 3) - (v5 >> 3);
    v17 = v14;
    if ( v8 < v21 - 7 )
    {
      do
      {
        v15 = *(_WORD *)(v14 + v13++);
        v8 += 8;
        v5 += 8;
        v14 = v17;
        *(_BYTE *)(v13 - 1) = v15 >> (a3 & 7);
      }
      while ( v8 < v21 - 7 );
      v6 = (struct Err *)a4;
    }
  }
  if ( v8 <= v21 )
  {
    while ( 1 )
    {
      v20 = *(_DWORD *)this;
      v16 = v5 - *((_DWORD *)this + 2);
      v18 = 8 * *((_DWORD *)this + 1);
      v6 = (struct Err *)a4;
      if ( (*(_BYTE *)(((v8 - *((_DWORD *)this + 2)) >> 3) + *(_DWORD *)this)
          & *((_BYTE *)&Bitmap::ThisBit + ((v8 - *((_DWORD *)this + 2)) & 7))) == 0 )
        break;
      if ( v16 >= v18 )
        goto LABEL_28;
      if ( v16 >> 3 < *((_DWORD *)this + 1) )
        *(_BYTE *)((v16 >> 3) + v20) |= *((_BYTE *)&Bitmap::ThisBit + (v16 & 7));
LABEL_37:
      ++v8;
      ++v5;
      if ( v8 > v21 )
        goto LABEL_38;
    }
    if ( v16 < v18 )
    {
      if ( v16 >> 3 < *((_DWORD *)this + 1) )
        *(_BYTE *)((v16 >> 3) + v20) &= ~*((_BYTE *)&Bitmap::ThisBit + (v16 & 7));
      goto LABEL_37;
    }
LABEL_28:
    if ( (int)*a4 < 8 )
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
    goto LABEL_37;
  }
LABEL_38:
  Bitmap::Clear(this, v5, a3, v6);
}

```

## disassembly

```asm
0x10010290  mov     edi, edi
0x10010292  push    ebp
0x10010293  mov     ebp, esp
0x10010295  sub     esp, 10h
0x10010298  mov     edx, ecx
0x1001029a  push    ebx
0x1001029b  mov     ebx, [ebp+arg_0]
0x1001029e  push    esi
0x1001029f  mov     ecx, [edx+4]
0x100102a2  mov     eax, [edx+8]
0x100102a5  mov     esi, [ebp+arg_8]
0x100102a8  push    edi
0x100102a9  mov     edi, [ebp+arg_4]
0x100102ac  lea     eax, [eax+ecx*8]
0x100102af  mov     [ebp+var_4], edx
0x100102b2  dec     eax
0x100102b3  add     edi, ebx
0x100102b5  mov     [ebp+var_8], eax
0x100102b8  test    bl, 7
0x100102bb  jz      loc_100103AA
0x100102c1  cmp     edi, eax
0x100102c3  ja      loc_100103AA
0x100102c9  mov     eax, [edx+8]
0x100102cc  mov     ecx, edi
0x100102ce  mov     edx, [edx]
0x100102d0  sub     ecx, eax
0x100102d2  mov     [ebp+var_C], edx
0x100102d5  mov     edx, ebx
0x100102d7  mov     esi, [ebp+var_C]
0x100102da  sub     edx, eax
0x100102dc  mov     eax, ecx
0x100102de  and     ecx, 7
0x100102e1  shr     eax, 3
0x100102e4  mov     al, [eax+esi]
0x100102e7  mov     esi, [ebp+var_4]
0x100102ea  test    ds:?ThisBit@Bitmap@@1QBEB[ecx], al; uchar const * const Bitmap::ThisBit
0x100102f0  mov     ecx, [esi+4]
0x100102f3  mov     esi, [ebp+arg_8]
0x100102f6  lea     eax, ds:0[ecx*8]
0x100102fd  jz      short loc_10010325
0x100102ff  cmp     edx, eax
0x10010301  jnb     short loc_10010329
0x10010303  mov     eax, [ebp+var_4]
0x10010306  mov     ecx, edx
0x10010308  shr     ecx, 3
0x1001030b  cmp     ecx, [eax+4]
0x1001030e  jnb     loc_10010399
0x10010314  and     edx, 7
0x10010317  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x1001031d  mov     edx, [ebp+var_C]
0x10010320  or      [ecx+edx], al
0x10010323  jmp     short loc_10010399
0x10010325  cmp     edx, eax
0x10010327  jb      short loc_1001037B
0x10010329  mov     eax, [esi]
0x1001032b  cmp     eax, 8
0x1001032e  jge     short loc_10010399
0x10010330  test    eax, 0FFFFFFFEh
0x10010335  jz      short loc_10010357
0x10010337  mov     eax, [esi+0Ch]
0x1001033a  test    eax, eax
0x1001033c  jz      short loc_10010347
0x1001033e  push    eax; Block
0x1001033f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10010344  add     esp, 4
0x10010347  mov     eax, [esi+10h]
0x1001034a  test    eax, eax
0x1001034c  jz      short loc_10010357
0x1001034e  push    eax; Block
0x1001034f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10010354  add     esp, 4
0x10010357  mov     dword ptr [esi], 8
0x1001035d  mov     dword ptr [esi+4], 0FFFFFB4Ah
0x10010364  mov     dword ptr [esi+8], 0
0x1001036b  mov     dword ptr [esi+0Ch], 0
0x10010372  mov     dword ptr [esi+10h], 0
0x10010379  jmp     short loc_10010399
0x1001037b  mov     eax, [ebp+var_4]
0x1001037e  mov     ecx, edx
0x10010380  shr     ecx, 3
0x10010383  cmp     ecx, [eax+4]
0x10010386  jnb     short loc_10010399
0x10010388  and     edx, 7
0x1001038b  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x10010391  mov     edx, [ebp+var_C]
0x10010394  not     al
0x10010396  and     [ecx+edx], al
0x10010399  mov     eax, [ebp+var_8]
0x1001039c  inc     ebx
0x1001039d  mov     edx, [ebp+var_4]
0x100103a0  inc     edi
0x100103a1  test    bl, 7
0x100103a4  jnz     loc_100102C1
0x100103aa  lea     eax, [edi+7]
0x100103ad  cmp     eax, [ebp+var_8]
0x100103b0  jnb     short loc_100103FB
0x100103b2  mov     edx, [edx]
0x100103b4  mov     eax, ebx
0x100103b6  shr     eax, 3
0x100103b9  mov     ecx, edi
0x100103bb  shr     ecx, 3
0x100103be  add     edx, eax
0x100103c0  sub     ecx, eax
0x100103c2  mov     eax, [ebp+var_8]
0x100103c5  add     eax, 0FFFFFFF9h
0x100103c8  mov     [ebp+var_10], ecx
0x100103cb  cmp     edi, eax
0x100103cd  jnb     short loc_100103FB
0x100103cf  mov     esi, [ebp+arg_4]
0x100103d2  and     esi, 7
0x100103d5  mov     ax, [ecx+edx]
0x100103d9  lea     edx, [edx+1]
0x100103dc  mov     cx, si
0x100103df  add     edi, 8
0x100103e2  shr     ax, cl
0x100103e5  add     ebx, 8
0x100103e8  mov     ecx, [ebp+var_10]
0x100103eb  mov     [edx-1], al
0x100103ee  mov     eax, [ebp+var_8]
0x100103f1  add     eax, 0FFFFFFF9h
0x100103f4  cmp     edi, eax
0x100103f6  jb      short loc_100103D5
0x100103f8  mov     esi, [ebp+arg_8]
0x100103fb  cmp     edi, [ebp+var_8]
0x100103fe  ja      loc_100104E2
0x10010404  mov     esi, [ebp+var_4]
0x10010407  mov     ecx, edi
0x10010409  mov     eax, [esi+4]
0x1001040c  sub     ecx, [esi+8]
0x1001040f  mov     edx, [esi]
0x10010411  shl     eax, 3
0x10010414  mov     [ebp+var_C], edx
0x10010417  mov     edx, ebx
0x10010419  sub     edx, [esi+8]
0x1001041c  mov     esi, [ebp+var_C]
0x1001041f  mov     [ebp+var_10], eax
0x10010422  mov     eax, ecx
0x10010424  shr     eax, 3
0x10010427  and     ecx, 7
0x1001042a  mov     al, [eax+esi]
0x1001042d  mov     esi, [ebp+arg_8]
0x10010430  test    ds:?ThisBit@Bitmap@@1QBEB[ecx], al; uchar const * const Bitmap::ThisBit
0x10010436  jz      short loc_10010462
0x10010438  cmp     edx, [ebp+var_10]
0x1001043b  jnb     short loc_10010467
0x1001043d  mov     eax, [ebp+var_4]
0x10010440  mov     ecx, edx
0x10010442  shr     ecx, 3
0x10010445  cmp     ecx, [eax+4]
0x10010448  jnb     loc_100104D7
0x1001044e  and     edx, 7
0x10010451  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x10010457  mov     edx, [ebp+var_C]
0x1001045a  or      [ecx+edx], al
0x1001045d  jmp     loc_100104D7
0x10010462  cmp     edx, [ebp+var_10]
0x10010465  jb      short loc_100104B9
0x10010467  mov     eax, [esi]
0x10010469  cmp     eax, 8
0x1001046c  jge     short loc_100104D7
0x1001046e  test    eax, 0FFFFFFFEh
0x10010473  jz      short loc_10010495
0x10010475  mov     eax, [esi+0Ch]
0x10010478  test    eax, eax
0x1001047a  jz      short loc_10010485
0x1001047c  push    eax; Block
0x1001047d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10010482  add     esp, 4
0x10010485  mov     eax, [esi+10h]
0x10010488  test    eax, eax
0x1001048a  jz      short loc_10010495
0x1001048c  push    eax; Block
0x1001048d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10010492  add     esp, 4
0x10010495  mov     dword ptr [esi], 8
0x1001049b  mov     dword ptr [esi+4], 0FFFFFB4Ah
0x100104a2  mov     dword ptr [esi+8], 0
0x100104a9  mov     dword ptr [esi+0Ch], 0
0x100104b0  mov     dword ptr [esi+10h], 0
0x100104b7  jmp     short loc_100104D7
0x100104b9  mov     eax, [ebp+var_4]
0x100104bc  mov     ecx, edx
0x100104be  shr     ecx, 3
0x100104c1  cmp     ecx, [eax+4]
0x100104c4  jnb     short loc_100104D7
0x100104c6  and     edx, 7
0x100104c9  mov     al, ds:?ThisBit@Bitmap@@1QBEB[edx]; uchar const * const Bitmap::ThisBit
0x100104cf  mov     edx, [ebp+var_C]
0x100104d2  not     al
0x100104d4  and     [ecx+edx], al
0x100104d7  inc     edi
0x100104d8  inc     ebx
0x100104d9  cmp     edi, [ebp+var_8]
0x100104dc  jbe     loc_10010404
0x100104e2  mov     ecx, [ebp+var_4]; this
0x100104e5  mov     edx, ebx; unsigned int
0x100104e7  push    esi; struct Err *
0x100104e8  push    [ebp+arg_4]; unsigned int
0x100104eb  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x100104f0  pop     edi
0x100104f1  pop     esi
0x100104f2  pop     ebx
0x100104f3  mov     esp, ebp
0x100104f5  pop     ebp
0x100104f6  retn    0Ch
```
