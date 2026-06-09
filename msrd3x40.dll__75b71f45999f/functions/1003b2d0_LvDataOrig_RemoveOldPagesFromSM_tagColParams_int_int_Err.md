# LvDataOrig::RemoveOldPagesFromSM(tagColParams *,int,int,Err &)

- ea: `0x1003b2d0`
- end: `0x1003b3f3`
- name: `?RemoveOldPagesFromSM@LvDataOrig@@QAEXPAUtagColParams@@HHAAVErr@@@Z`
- size: `291`
- prototype: `void __thiscall(LvDataOrig *__hidden this, struct tagColParams *, int, struct tagColParams *, struct Err *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1001f040`
- `0x1003f080`

## callees

- `0x1000f890`
- `0x1003ab80`
- `0x1003b2d0`
- `0x1003b400`
- `0x1003b600`
- `0x100471e0`
- `0x100473e0`
- `0x10047a60`

## pseudocode

```c
void __thiscall LvDataOrig::RemoveOldPagesFromSM(
        LvDataOrig *this,
        struct tagColParams *a2,
        int a3,
        struct tagColParams *a4,
        struct Err *a5)
{
  int v5; // ebx
  LvDataOrig *v6; // edi
  unsigned int v7; // eax
  struct tagColParams *i; // ecx
  _DWORD *v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // edi
  AbstractSpacemap *v13; // [esp+14h] [ebp-4h]

  v5 = 0;
  v6 = this;
  if ( !*((_DWORD *)this + 515) )
    LvDataOrig::GetRecordData(this, (int)a2, 0, a5);
  if ( (*(_BYTE *)a5 & 8) == 0 && *((_DWORD *)v6 + 518) )
  {
    v7 = *((_DWORD *)v6 + 522);
    if ( v7 && !*((_DWORD *)v6 + 521) )
      LvDataOrig::GetWriteLock(v6, this, v7 >> 8, a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      LvDataOrig::LoadOriginalBookmarks(v6, a4, (int)a4, a5);
      for ( i = a4; (*(_BYTE *)a5 & 8) == 0; i = a4 )
      {
        v9 = (_DWORD *)*((_DWORD *)v6 + 518);
        if ( v5 >= v9[1] )
          break;
        if ( v5 > (int)i )
          break;
        v10 = *(_DWORD *)(v5 * *v9 + v9[3]);
        if ( !v10 )
          break;
        v11 = v10 >> 8;
        v13 = *(AbstractSpacemap **)(*((_DWORD *)this + 517) + 16);
        AbstractSpacemap::Setup(v13, 1, a5);
        if ( (*(_BYTE *)a5 & 8) == 0
          && AbstractSpacemap::GetBitmap(v13, v11, 2, a5) == 1
          && (*(_BYTE *)(((v11 - *((_DWORD *)v13 + 6)) >> 3) + *((_DWORD *)v13 + 4))
            & *((_BYTE *)&Bitmap::ThisBit + ((v11 - *((_DWORD *)v13 + 6)) & 7))) != 0 )
        {
          Bitmap::Clear((AbstractSpacemap *)((char *)v13 + 16), v11, a5);
          AbstractSpacemap::UpdateBitmap(v13);
        }
        v6 = this;
        ++v5;
      }
    }
  }
}

```

## disassembly

```asm
0x1003b2d0  mov     edi, edi
0x1003b2d2  push    ebp
0x1003b2d3  mov     ebp, esp
0x1003b2d5  sub     esp, 0Ch
0x1003b2d8  push    ebx
0x1003b2d9  push    esi
0x1003b2da  mov     esi, [ebp+arg_C]
0x1003b2dd  xor     ebx, ebx
0x1003b2df  push    edi
0x1003b2e0  mov     edi, ecx
0x1003b2e2  mov     [ebp+var_8], edi
0x1003b2e5  cmp     [edi+80Ch], ebx
0x1003b2eb  jnz     short loc_1003B2F7
0x1003b2ed  push    esi
0x1003b2ee  push    ebx
0x1003b2ef  push    [ebp+arg_0]
0x1003b2f2  call    ?GetRecordData@LvDataOrig@@QAEXPAUtagColParams@@W4LvNullWarningAction@@AAVErr@@@Z; LvDataOrig::GetRecordData(tagColParams *,LvNullWarningAction,Err &)
0x1003b2f7  test    byte ptr [esi], 8
0x1003b2fa  jnz     loc_1003B3EA
0x1003b300  cmp     [edi+818h], ebx
0x1003b306  jz      loc_1003B3EA
0x1003b30c  mov     eax, [edi+828h]
0x1003b312  test    eax, eax
0x1003b314  jz      short loc_1003B32B
0x1003b316  cmp     [edi+824h], ebx
0x1003b31c  jnz     short loc_1003B32B
0x1003b31e  push    esi; struct Err *
0x1003b31f  shr     eax, 8
0x1003b322  push    eax; unsigned int
0x1003b323  push    ecx; struct tagColParams *
0x1003b324  mov     ecx, edi; this
0x1003b326  call    ?GetWriteLock@LvDataOrig@@AAEXPAUtagColParams@@KAAVErr@@@Z; LvDataOrig::GetWriteLock(tagColParams *,ulong,Err &)
0x1003b32b  test    byte ptr [esi], 8
0x1003b32e  mov     ecx, [ebp+arg_8]
0x1003b331  jnz     loc_1003B3EA
0x1003b337  push    esi; struct Err *
0x1003b338  push    ecx; int
0x1003b339  push    ecx; struct tagColParams *
0x1003b33a  mov     ecx, edi; this
0x1003b33c  call    ?LoadOriginalBookmarks@LvDataOrig@@AAEXPAUtagColParams@@HAAVErr@@@Z; LvDataOrig::LoadOriginalBookmarks(tagColParams *,int,Err &)
0x1003b341  test    byte ptr [esi], 8
0x1003b344  mov     ecx, [ebp+arg_8]
0x1003b347  jnz     loc_1003B3EA
0x1003b34d  nop     dword ptr [eax]
0x1003b350  mov     eax, [edi+818h]
0x1003b356  cmp     ebx, [eax+4]
0x1003b359  jge     loc_1003B3EA
0x1003b35f  cmp     ebx, ecx
0x1003b361  jg      loc_1003B3EA
0x1003b367  mov     ecx, [eax]
0x1003b369  mov     eax, [eax+0Ch]
0x1003b36c  imul    ecx, ebx
0x1003b36f  mov     edi, [ecx+eax]
0x1003b372  test    edi, edi
0x1003b374  jz      short loc_1003B3EA
0x1003b376  mov     eax, [ebp+var_8]
0x1003b379  push    esi
0x1003b37a  shr     edi, 8
0x1003b37d  push    1
0x1003b37f  mov     eax, [eax+814h]
0x1003b385  mov     [ebp+var_C], edi
0x1003b388  mov     eax, [eax+10h]
0x1003b38b  mov     ecx, eax
0x1003b38d  mov     [ebp+var_4], eax
0x1003b390  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x1003b395  test    byte ptr [esi], 8
0x1003b398  jnz     short loc_1003B3DA
0x1003b39a  mov     ecx, [ebp+var_4]
0x1003b39d  push    esi
0x1003b39e  push    2
0x1003b3a0  push    edi
0x1003b3a1  call    ?GetBitmap@AbstractSpacemap@@IAE?AW4GBResult@1@KW4GBDirection@1@AAVErr@@@Z; AbstractSpacemap::GetBitmap(ulong,AbstractSpacemap::GBDirection,Err &)
0x1003b3a6  cmp     eax, 1
0x1003b3a9  jnz     short loc_1003B3DA
0x1003b3ab  mov     ecx, [ebp+var_4]
0x1003b3ae  add     ecx, 10h; this
0x1003b3b1  sub     edi, [ecx+8]
0x1003b3b4  mov     eax, [ecx]
0x1003b3b6  mov     edx, edi
0x1003b3b8  shr     edx, 3
0x1003b3bb  and     edi, 7
0x1003b3be  mov     al, [edx+eax]
0x1003b3c1  test    ds:?ThisBit@Bitmap@@1QBEB[edi], al; uchar const * const Bitmap::ThisBit
0x1003b3c7  jz      short loc_1003B3DA
0x1003b3c9  push    esi; struct Err *
0x1003b3ca  push    [ebp+var_C]; unsigned int
0x1003b3cd  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x1003b3d2  mov     ecx, [ebp+var_4]; this
0x1003b3d5  call    ?UpdateBitmap@AbstractSpacemap@@IAEXXZ; AbstractSpacemap::UpdateBitmap(void)
0x1003b3da  mov     edi, [ebp+var_8]
0x1003b3dd  inc     ebx
0x1003b3de  test    byte ptr [esi], 8
0x1003b3e1  mov     ecx, [ebp+arg_8]
0x1003b3e4  jz      loc_1003B350
0x1003b3ea  pop     edi
0x1003b3eb  pop     esi
0x1003b3ec  pop     ebx
0x1003b3ed  mov     esp, ebp
0x1003b3ef  pop     ebp
0x1003b3f0  retn    10h
```
