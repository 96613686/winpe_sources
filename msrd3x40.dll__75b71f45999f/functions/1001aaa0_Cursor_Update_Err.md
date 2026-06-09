# Cursor::Update(Err &)

- ea: `0x1001aaa0`
- end: `0x1001afeb`
- name: `?Update@Cursor@@UAEKAAVErr@@@Z`
- size: `1355`
- prototype: `unsigned int __thiscall(Cursor *__hidden this, struct Err *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1004fd90`
- `0x10058c40`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10018690`
- `0x1001aaa0`
- `0x1001c2d0`
- `0x1001c340`
- `0x1001c3d0`
- `0x1001c8c0`
- `0x1001db50`
- `0x1001ec40`
- `0x1001efe0`
- `0x1001f040`
- `0x1001f190`
- `0x100276b0`
- `0x10038630`
- `0x10039890`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x10052c30`
- `0x10052cc0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
unsigned int __thiscall Cursor::Update(Cursor *this, void **a2)
{
  bool v3; // zf
  struct Err *v4; // edi
  int v5; // esi
  unsigned int result; // eax
  void *v7; // eax
  unsigned int v8; // ecx
  void *v9; // ecx
  Table *v10; // edi
  struct Instance *v11; // eax
  _DWORD *v12; // ecx
  _DWORD *v13; // edx
  int v14; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // eax
  unsigned __int8 *v18; // esi
  void *v19; // eax
  Table *v20; // edi
  struct Instance *v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // [esp+0h] [ebp-84h]
  struct Err *v25; // [esp+4h] [ebp-80h]
  int v26; // [esp+14h] [ebp-70h] BYREF
  _DWORD v27[4]; // [esp+18h] [ebp-6Ch] BYREF
  int v28; // [esp+28h] [ebp-5Ch]
  int v29; // [esp+2Ch] [ebp-58h]
  unsigned int v30; // [esp+30h] [ebp-54h] BYREF
  int inserted; // [esp+34h] [ebp-50h]
  struct Err *v32; // [esp+38h] [ebp-4Ch]
  void *v33; // [esp+3Ch] [ebp-48h]
  void *v34; // [esp+40h] [ebp-44h] BYREF
  void *Block; // [esp+44h] [ebp-40h]
  int v36; // [esp+48h] [ebp-3Ch]
  int v37; // [esp+4Ch] [ebp-38h]
  char v38; // [esp+50h] [ebp-34h] BYREF
  int v39; // [esp+80h] [ebp-4h]

  v3 = *((_DWORD *)this + 11) == 3;
  v4 = (struct Err *)a2;
  v5 = *((_DWORD *)this + 6);
  v32 = (struct Err *)a2;
  inserted = v5;
  v28 = 0;
  if ( v3 )
  {
    if ( (int)*a2 < 8 )
    {
      if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
      {
        if ( a2[3] )
          operator delete[](a2[3]);
        if ( a2[4] )
          operator delete[](a2[4]);
      }
      *a2 = (void *)8;
      a2[1] = (void *)-1609;
      a2[2] = 0;
      a2[3] = 0;
      a2[4] = 0;
    }
    return v5;
  }
  v7 = (void *)*((_DWORD *)this + 3);
  v33 = v7;
  if ( (*((_BYTE *)v7 + 88) & 8) != 0 )
  {
    v3 = (*(_BYTE *)a2 & 8) == 0;
    v8 = *((_DWORD *)v7 + 92);
    v30 = v8;
    if ( !v3 )
      return v5;
    do
    {
      if ( v8 == -1 )
        break;
      v29 = *((_DWORD *)v7 + v8 + 94);
      if ( (*(_BYTE *)(v29 + 49) & 1) != 0
        && (*(int (__thiscall **)(Cursor *, _DWORD, void **))(*(_DWORD *)this + 120))(this, *(_DWORD *)(v29 + 12), a2) )
      {
        EvaluateRule(*(struct Cursor **)(v29 + 52), 2u, a2, v24, v25);
      }
      *(_BYTE *)(v29 + 202) = *((_BYTE *)this + 360);
      v3 = (*(_BYTE *)a2 & 8) == 0;
      v8 = *(_DWORD *)(*((_DWORD *)v33 + 90) + 8 * v30);
      v7 = v33;
      v30 = v8;
    }
    while ( v3 );
    v5 = inserted;
  }
  if ( (*(_BYTE *)a2 & 8) != 0 )
    return v5;
  if ( (*((_BYTE *)v7 + 88) & 4) != 0 )
    EvaluateRule(*((struct Cursor **)v7 + 23), 1u, a2, v24, v25);
  if ( (*(_BYTE *)a2 & 8) != 0 )
    return v5;
  if ( *((_DWORD *)this + 11) != 4
    && (*(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 1) + 16) + 68) != 1 || *((_DWORD *)this + 89)) )
  {
    Session::BeginTransaction(*((_DWORD *)this + 2), 1, a2);
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v28 = 1;
      goto LABEL_27;
    }
    return v5;
  }
LABEL_27:
  switch ( *((_DWORD *)this + 11) )
  {
    case 0:
      if ( *(_DWORD *)(*((_DWORD *)this + 3) + 80) == -1
        || (Cursor::SetVersion(this, (struct Err *)a2), (*(_BYTE *)a2 & 8) == 0) )
      {
        v9 = *(void **)(*((_DWORD *)this + 3) + 84);
        v33 = v9;
        if ( v9 == (void *)-1 || !*((_DWORD *)this + 84) )
          goto LABEL_89;
        if ( (*(_BYTE *)((((unsigned int)v9 - *(_DWORD *)(*((_DWORD *)this + 13) + 24)) >> 3)
                       + *(_DWORD *)(*((_DWORD *)this + 13) + 16))
            & *((_BYTE *)&Bitmap::ThisBit + (((int)v9 - *(_DWORD *)(*((_DWORD *)this + 13) + 24)) & 7))) != 0 )
        {
          (*(void (__thiscall **)(Cursor *, void *, unsigned int *, int, _DWORD, void **))(*(_DWORD *)this + 108))(
            this,
            v33,
            &v30,
            4,
            0,
            a2);
          if ( (*(_BYTE *)a2 & 8) != 0 )
            break;
          v33 = (void *)v30;
          if ( v30 > *((_DWORD *)this + 85) )
          {
            v10 = (Table *)*((_DWORD *)this + 3);
            *((_DWORD *)this + 85) = v30;
            v11 = (struct Instance *)(*(int (__thiscall **)(Cursor *))(*(_DWORD *)this + 56))(this);
            Table::NextRecordNumber(v10, v11, v32, (unsigned int)v33);
            v4 = v32;
          }
        }
        if ( (*(_BYTE *)v4 & 8) == 0 )
        {
LABEL_89:
          if ( !*((_DWORD *)this + 89) || (Cursor::LvUpdateCopyBuffer(this, v4), (*(_BYTE *)v4 & 8) == 0) )
          {
            if ( *((_DWORD *)this + 4) == 6 )
            {
              v12 = (_DWORD *)*((_DWORD *)this + 13);
              v13 = (_DWORD *)*v12;
              v27[1] = v12[1];
              v3 = v13 == v12 + 19;
              v27[0] = v13;
              v14 = *((_DWORD *)this + 3);
              v15 = 2012;
              if ( !v3 )
                v15 = 0;
              v27[2] = v15;
              if ( *(int *)(v14 + 24) <= 0 || (v16 = *(_DWORD *)(v14 + 1524), v16 == -1) )
                v33 = 0;
              else
                v33 = *(void **)(v14 + 4 * v16 + 1396);
              v17 = (*(int (__thiscall **)(_DWORD, int, struct Err *))(**((_DWORD **)this + 8) + 68))(
                      *((_DWORD *)this + 8),
                      255,
                      v32);
              v4 = v32;
              v18 = (unsigned __int8 *)v17;
              if ( (*(_BYTE *)v32 & 8) == 0 )
              {
                v34 = 0;
                Block = &v38;
                v36 = 0;
                v37 = 32;
                v39 = 0;
                Cursor::BuildKeyFromRecord(
                  this,
                  *((struct PhysicalIndex **)v33 + 2),
                  (struct Record *)v27,
                  (struct Key *)&v34,
                  v32);
                if ( (*(_BYTE *)v4 & 8) == 0 )
                {
                  QuickKey::Copy((QuickKey *)&v34, v18, 0xFFu, v4);
                  v19 = (void *)(*(int (__thiscall **)(_DWORD, void *, _DWORD, struct Err *))(**((_DWORD **)this + 8)
                                                                                            + 44))(
                                  *((_DWORD *)this + 8),
                                  v34,
                                  *(_DWORD *)(*((_DWORD *)this + 13) + 4),
                                  v32);
                  v4 = v32;
                  if ( (*(_BYTE *)v32 & 8) == 0 )
                    memcpy(v19, (const void *)(*((_DWORD *)this + 13) + 76), *(_DWORD *)(*((_DWORD *)this + 13) + 4));
                }
                v39 = -1;
                if ( v36 == 1 && Block )
                  operator delete[](Block);
              }
              inserted = 0;
            }
            else
            {
              inserted = Cursor::InsertRecord(this, 0, 0, v4);
            }
            if ( !*((_DWORD *)this + 89) )
              goto LABEL_73;
            if ( (*(_BYTE *)v4 & 8) == 0 )
            {
              Cursor::LvMergeNewPages(this, v4);
              if ( (*(_BYTE *)v4 & 8) == 0 )
              {
                Cursor::LvRemoveOldPagesFromSM(this, v4);
                if ( (*(_BYTE *)v4 & 8) == 0 )
                {
                  Cursor::LvFreeUnusedPages(this, v4);
                  goto LABEL_73;
                }
              }
            }
          }
        }
      }
      break;
    case 1:
    case 2:
    case 4:
      if ( *(_DWORD *)(*((_DWORD *)this + 3) + 80) == -1
        || (Cursor::SetVersion(this, (struct Err *)a2), (*(_BYTE *)a2 & 8) == 0) )
      {
        if ( !*((_DWORD *)this + 89) || (Cursor::LvUpdateCopyBuffer(this, (struct Err *)a2), (*(_BYTE *)a2 & 8) == 0) )
        {
          Cursor::UpdateRecord(this, (struct Err *)a2);
          if ( *((_DWORD *)this + 89) )
          {
            if ( (*(_BYTE *)a2 & 8) != 0 )
              break;
            Cursor::LvMergeNewPages(this, (struct Err *)a2);
            if ( (*(_BYTE *)a2 & 8) != 0 )
              break;
            Cursor::LvRemoveOldPagesFromSM(this, (struct Err *)a2);
            if ( (*(_BYTE *)a2 & 8) != 0 )
              break;
            Cursor::LvFreeUnusedPages(this, (struct Err *)a2);
          }
          if ( (*(_BYTE *)a2 & 8) == 0 )
          {
            if ( *((_DWORD *)this + 11) != 1 && *((_DWORD *)this + 18) >= *(_DWORD *)(*((_DWORD *)this + 2) + 56) - 1 )
              Cursor::UnlockCurrentRecord(this, a2, 0);
            goto LABEL_73;
          }
        }
      }
      break;
    default:
LABEL_73:
      if ( (*(_BYTE *)v4 & 8) == 0 && *((_DWORD *)this + 89) )
        ColumnLv::ResetLongValues((char *)this + 96);
      break;
  }
  if ( v28 )
  {
    if ( (*(_BYTE *)v4 & 8) == 0 )
    {
      Session::CommitTransaction(*((Session **)this + 2), (void **)v4, 0);
      if ( (*(_BYTE *)v4 & 8) == 0 )
        goto LABEL_81;
    }
    v26 = 1;
    v39 = 1;
    Session::AbortTransaction(*((Session **)this + 2), (struct Err *)&v26);
    v39 = -1;
    Err::~Err((Err *)&v26);
  }
  if ( (*(_BYTE *)v4 & 8) != 0 )
    return inserted;
LABEL_81:
  if ( !*((_DWORD *)this + 11) )
  {
    v20 = (Table *)*((_DWORD *)this + 3);
    v21 = (struct Instance *)(*(int (__thiscall **)(Cursor *))(*(_DWORD *)this + 56))(this);
    Table::AddRecords(v20, v21, 1);
  }
  v22 = *(_DWORD *)(*((_DWORD *)this + 2) + 56);
  if ( *((_DWORD *)this + 18) < v22 )
  {
    *((_DWORD *)this + 19) = v22;
    return inserted;
  }
  v23 = *((_DWORD *)this + 3);
  *((_DWORD *)this + 11) = 3;
  --*(_DWORD *)(v23 + 128);
  result = inserted;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 0;
  return result;
}

```

## disassembly

```asm
0x1001aaa0  mov     edi, edi
0x1001aaa2  push    ebp
0x1001aaa3  mov     ebp, esp
0x1001aaa5  push    0FFFFFFFFh
0x1001aaa7  push    offset ?Update@Cursor@@UAEKAAVErr@@@Z_SEH
0x1001aaac  mov     eax, large fs:0
0x1001aab2  push    eax
0x1001aab3  sub     esp, 68h
0x1001aab6  mov     eax, ___security_cookie
0x1001aabb  xor     eax, ebp
0x1001aabd  mov     [ebp+var_14], eax
0x1001aac0  push    ebx
0x1001aac1  push    esi
0x1001aac2  push    edi; unsigned int
0x1001aac3  push    eax; void *
0x1001aac4  lea     eax, [ebp+var_C]
0x1001aac7  mov     large fs:0, eax
0x1001aacd  mov     ebx, ecx
0x1001aacf  cmp     dword ptr [ebx+2Ch], 3
0x1001aad3  mov     edi, [ebp+arg_0]
0x1001aad6  mov     esi, [ebx+18h]
0x1001aad9  mov     [ebp+var_4C], edi
0x1001aadc  mov     [ebp+var_50], esi
0x1001aadf  mov     [ebp+var_5C], 0
0x1001aae6  jnz     short loc_1001AB58
0x1001aae8  mov     eax, [edi]
0x1001aaea  cmp     eax, 8
0x1001aaed  jge     short loc_1001AB38
0x1001aaef  test    eax, 0FFFFFFFEh
0x1001aaf4  jz      short loc_1001AB16
0x1001aaf6  mov     eax, [edi+0Ch]
0x1001aaf9  test    eax, eax
0x1001aafb  jz      short loc_1001AB06
0x1001aafd  push    eax; Block
0x1001aafe  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ab03  add     esp, 4
0x1001ab06  mov     eax, [edi+10h]
0x1001ab09  test    eax, eax
0x1001ab0b  jz      short loc_1001AB16
0x1001ab0d  push    eax; Block
0x1001ab0e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ab13  add     esp, 4
0x1001ab16  mov     dword ptr [edi], 8
0x1001ab1c  mov     dword ptr [edi+4], 0FFFFF9B7h
0x1001ab23  mov     dword ptr [edi+8], 0
0x1001ab2a  mov     dword ptr [edi+0Ch], 0
0x1001ab31  mov     dword ptr [edi+10h], 0
0x1001ab38  mov     eax, esi
0x1001ab3a  mov     ecx, [ebp+var_C]
0x1001ab3d  mov     large fs:0, ecx
0x1001ab44  pop     ecx
0x1001ab45  pop     edi
0x1001ab46  pop     esi
0x1001ab47  pop     ebx
0x1001ab48  mov     ecx, [ebp+var_14]
0x1001ab4b  xor     ecx, ebp; StackCookie
0x1001ab4d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ab52  mov     esp, ebp
0x1001ab54  pop     ebp
0x1001ab55  retn    4
0x1001ab58  mov     eax, [ebx+0Ch]
0x1001ab5b  mov     [ebp+var_48], eax
0x1001ab5e  test    byte ptr [eax+58h], 8
0x1001ab62  jz      short loc_1001ABE2
0x1001ab64  test    byte ptr [edi], 8
0x1001ab67  mov     ecx, [eax+170h]
0x1001ab6d  mov     [ebp+var_54], ecx
0x1001ab70  jnz     short loc_1001AB38
0x1001ab72  cmp     ecx, 0FFFFFFFFh
0x1001ab75  jz      short loc_1001ABDF
0x1001ab77  mov     eax, [eax+ecx*4+178h]
0x1001ab7e  mov     [ebp+var_58], eax
0x1001ab81  test    byte ptr [eax+31h], 1
0x1001ab85  jz      short loc_1001ABB6
0x1001ab87  mov     eax, [ebx]
0x1001ab89  push    edi; unsigned int
0x1001ab8a  mov     esi, [eax+78h]
0x1001ab8d  mov     ecx, esi
0x1001ab8f  mov     eax, [ebp+var_58]
0x1001ab92  push    dword ptr [eax+0Ch]; void *
0x1001ab95  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001ab9b  mov     ecx, ebx
0x1001ab9d  call    esi
0x1001ab9f  test    eax, eax
0x1001aba1  jz      short loc_1001ABB6
0x1001aba3  mov     eax, [ebp+var_58]
0x1001aba6  mov     ecx, ebx
0x1001aba8  push    edi; void *
0x1001aba9  push    2; unsigned int
0x1001abab  push    dword ptr [eax+34h]; struct Cursor *
0x1001abae  mov     edx, [eax+0Ch]
0x1001abb1  call    ?EvaluateRule@@YGXPAVCursor@@KPAXKAAVErr@@@Z; EvaluateRule(Cursor *,ulong,void *,ulong,Err &)
0x1001abb6  mov     ecx, [ebp+var_58]
0x1001abb9  mov     al, [ebx+168h]
0x1001abbf  mov     [ecx+0CAh], al
0x1001abc5  test    byte ptr [edi], 8
0x1001abc8  mov     eax, [ebp+var_48]
0x1001abcb  mov     ecx, [ebp+var_54]
0x1001abce  mov     eax, [eax+168h]
0x1001abd4  mov     ecx, [eax+ecx*8]
0x1001abd7  mov     eax, [ebp+var_48]
0x1001abda  mov     [ebp+var_54], ecx
0x1001abdd  jz      short loc_1001AB72
0x1001abdf  mov     esi, [ebp+var_50]
0x1001abe2  test    byte ptr [edi], 8
0x1001abe5  jnz     loc_1001AB38
0x1001abeb  test    byte ptr [eax+58h], 4
0x1001abef  jz      short loc_1001AC01
0x1001abf1  push    edi; void *
0x1001abf2  push    1; unsigned int
0x1001abf4  push    dword ptr [eax+5Ch]; struct Cursor *
0x1001abf7  or      edx, 0FFFFFFFFh
0x1001abfa  mov     ecx, ebx
0x1001abfc  call    ?EvaluateRule@@YGXPAVCursor@@KPAXKAAVErr@@@Z; EvaluateRule(Cursor *,ulong,void *,ulong,Err &)
0x1001ac01  test    byte ptr [edi], 8
0x1001ac04  jnz     loc_1001AB38
0x1001ac0a  cmp     dword ptr [ebx+2Ch], 4
0x1001ac0e  jz      short loc_1001AC40
0x1001ac10  mov     eax, [ebx+4]
0x1001ac13  mov     eax, [eax+10h]
0x1001ac16  cmp     dword ptr [eax+44h], 1
0x1001ac1a  jnz     short loc_1001AC25
0x1001ac1c  cmp     dword ptr [ebx+164h], 0
0x1001ac23  jbe     short loc_1001AC40
0x1001ac25  mov     ecx, [ebx+8]
0x1001ac28  push    edi
0x1001ac29  push    1
0x1001ac2b  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x1001ac30  test    byte ptr [edi], 8
0x1001ac33  jnz     loc_1001AB38
0x1001ac39  mov     [ebp+var_5C], 1
0x1001ac40  mov     eax, [ebx+2Ch]
0x1001ac43  cmp     eax, 4; switch 5 cases
0x1001ac46  ja      def_1001AC4C; jumptable 1001AC4C default case, case 3
0x1001ac4c  jmp     ds:jpt_1001AC4C[eax*4]; switch jump
0x1001ac53  mov     eax, [ebx+0Ch]; jumptable 1001AC4C case 0
0x1001ac56  cmp     dword ptr [eax+50h], 0FFFFFFFFh
0x1001ac5a  jz      short loc_1001AC6D
0x1001ac5c  push    edi; struct Err *
0x1001ac5d  mov     ecx, ebx; this
0x1001ac5f  call    ?SetVersion@Cursor@@AAEXAAVErr@@@Z; Cursor::SetVersion(Err &)
0x1001ac64  test    byte ptr [edi], 8
0x1001ac67  jnz     loc_1001AF42
0x1001ac6d  mov     eax, [ebx+0Ch]
0x1001ac70  mov     ecx, [eax+54h]
0x1001ac73  mov     [ebp+var_48], ecx
0x1001ac76  cmp     ecx, 0FFFFFFFFh
0x1001ac79  jz      loc_1001AD12
0x1001ac7f  cmp     dword ptr [ebx+150h], 0
0x1001ac86  jz      loc_1001AD12
0x1001ac8c  mov     eax, [ebx+34h]
0x1001ac8f  mov     edx, ecx
0x1001ac91  sub     edx, [eax+18h]
0x1001ac94  mov     eax, [eax+10h]
0x1001ac97  mov     ecx, edx
0x1001ac99  shr     ecx, 3
0x1001ac9c  and     edx, 7
0x1001ac9f  mov     al, [ecx+eax]
0x1001aca2  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1001aca8  jz      short loc_1001AD09
0x1001acaa  mov     eax, [ebx]
0x1001acac  push    edi
0x1001acad  push    0
0x1001acaf  push    4
0x1001acb1  mov     esi, [eax+6Ch]
0x1001acb4  lea     eax, [ebp+var_54]
0x1001acb7  push    eax; unsigned int
0x1001acb8  push    [ebp+var_48]; void *
0x1001acbb  mov     ecx, esi
0x1001acbd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001acc3  mov     ecx, ebx
0x1001acc5  call    esi
0x1001acc7  test    byte ptr [edi], 8
0x1001acca  jnz     loc_1001AF42
0x1001acd0  mov     eax, [ebp+var_54]
0x1001acd3  mov     [ebp+var_48], eax
0x1001acd6  cmp     eax, [ebx+154h]
0x1001acdc  jbe     short loc_1001AD09
0x1001acde  mov     edi, [ebx+0Ch]
0x1001ace1  mov     [ebx+154h], eax
0x1001ace7  mov     eax, [ebx]
0x1001ace9  mov     esi, [eax+38h]
0x1001acec  mov     ecx, esi
0x1001acee  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001acf4  mov     ecx, ebx
0x1001acf6  call    esi
0x1001acf8  push    [ebp+var_48]; unsigned int
0x1001acfb  mov     ecx, edi; this
0x1001acfd  push    [ebp+var_4C]; struct Err *
0x1001ad00  push    eax; struct Instance *
0x1001ad01  call    ?NextRecordNumber@Table@@QAEKPAVInstance@@AAVErr@@K@Z; Table::NextRecordNumber(Instance *,Err &,ulong)
0x1001ad06  mov     edi, [ebp+var_4C]
0x1001ad09  test    byte ptr [edi], 8
0x1001ad0c  jnz     loc_1001AF42
0x1001ad12  cmp     dword ptr [ebx+164h], 0
0x1001ad19  jbe     short loc_1001AD2C
0x1001ad1b  push    edi; struct Err *
0x1001ad1c  mov     ecx, ebx; this
0x1001ad1e  call    ?LvUpdateCopyBuffer@Cursor@@AAEXAAVErr@@@Z; Cursor::LvUpdateCopyBuffer(Err &)
0x1001ad23  test    byte ptr [edi], 8
0x1001ad26  jnz     loc_1001AF42
0x1001ad2c  cmp     dword ptr [ebx+10h], 6
0x1001ad30  jnz     loc_1001AE4F
0x1001ad36  mov     ecx, [ebx+34h]
0x1001ad39  xor     esi, esi
0x1001ad3b  mov     edx, [ecx]
0x1001ad3d  mov     eax, [ecx+4]
0x1001ad40  mov     [ebp+var_68], eax
0x1001ad43  lea     eax, [ecx+4Ch]
0x1001ad46  cmp     edx, eax
0x1001ad48  mov     [ebp+var_6C], edx
0x1001ad4b  mov     eax, [ebx+0Ch]
0x1001ad4e  mov     ecx, 7DCh
0x1001ad53  cmovnz  ecx, esi
0x1001ad56  mov     [ebp+var_64], ecx
0x1001ad59  cmp     [eax+18h], esi
0x1001ad5c  jle     short loc_1001AD75
0x1001ad5e  mov     ecx, [eax+5F4h]
0x1001ad64  cmp     ecx, 0FFFFFFFFh
0x1001ad67  jz      short loc_1001AD75
0x1001ad69  mov     eax, [eax+ecx*4+574h]
0x1001ad70  mov     [ebp+var_48], eax
0x1001ad73  jmp     short loc_1001AD78
0x1001ad75  mov     [ebp+var_48], esi
0x1001ad78  mov     edi, [ebx+20h]
0x1001ad7b  push    [ebp+var_4C]; unsigned int
0x1001ad7e  push    0FFh; void *
0x1001ad83  mov     eax, [edi]
0x1001ad85  mov     esi, [eax+44h]
0x1001ad88  mov     ecx, esi
0x1001ad8a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001ad90  mov     ecx, edi
0x1001ad92  call    esi
0x1001ad94  mov     edi, [ebp+var_4C]
0x1001ad97  mov     esi, eax
0x1001ad99  test    byte ptr [edi], 8
0x1001ad9c  jnz     loc_1001AE46
0x1001ada2  lea     eax, [ebp+var_34]
0x1001ada5  mov     [ebp+var_44], 0
0x1001adac  mov     [ebp+Block], eax
0x1001adaf  mov     [ebp+var_3C], 0
0x1001adb6  mov     [ebp+var_38], 20h ; ' '
0x1001adbd  push    edi; struct Err *
0x1001adbe  lea     eax, [ebp+var_44]
0x1001adc1  mov     [ebp+var_4], 0
0x1001adc8  push    eax; struct Key *
0x1001adc9  lea     eax, [ebp+var_6C]
0x1001adcc  mov     ecx, ebx; this
0x1001adce  push    eax; struct Record *
0x1001adcf  mov     eax, [ebp+var_48]
0x1001add2  push    dword ptr [eax+8]; struct PhysicalIndex *
0x1001add5  call    ?BuildKeyFromRecord@Cursor@@QAEEPAVPhysicalIndex@@AAVRecord@@AAVKey@@AAVErr@@@Z; Cursor::BuildKeyFromRecord(PhysicalIndex *,Record &,Key &,Err &)
0x1001adda  test    byte ptr [edi], 8
0x1001addd  jnz     short loc_1001AE29
0x1001addf  push    edi; struct Err *
0x1001ade0  push    0FFh; unsigned int
0x1001ade5  push    esi; unsigned __int8 *
0x1001ade6  lea     ecx, [ebp+var_44]; this
0x1001ade9  call    ?Copy@QuickKey@@QBEIPAEIAAVErr@@@Z; QuickKey::Copy(uchar *,uint,Err &)
0x1001adee  mov     edi, [ebx+20h]
0x1001adf1  push    [ebp+var_4C]
0x1001adf4  mov     eax, [edi]
0x1001adf6  mov     esi, [eax+2Ch]
0x1001adf9  mov     ecx, esi
0x1001adfb  mov     eax, [ebx+34h]
0x1001adfe  push    dword ptr [eax+4]; unsigned int
0x1001ae01  push    [ebp+var_44]; void *
0x1001ae04  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001ae0a  mov     ecx, edi
0x1001ae0c  call    esi
0x1001ae0e  mov     edi, [ebp+var_4C]
0x1001ae11  test    byte ptr [edi], 8
0x1001ae14  jnz     short loc_1001AE29
0x1001ae16  mov     ecx, [ebx+34h]
0x1001ae19  push    dword ptr [ecx+4]; Size
0x1001ae1c  add     ecx, 4Ch ; 'L'
0x1001ae1f  push    ecx; Src
0x1001ae20  push    eax; void *
0x1001ae21  call    _memcpy
0x1001ae26  add     esp, 0Ch
0x1001ae29  mov     [ebp+var_4], 0FFFFFFFFh
0x1001ae30  cmp     [ebp+var_3C], 1
0x1001ae34  jnz     short loc_1001AE46
0x1001ae36  mov     eax, [ebp+Block]
0x1001ae39  test    eax, eax
0x1001ae3b  jz      short loc_1001AE46
0x1001ae3d  push    eax; Block
0x1001ae3e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ae43  add     esp, 4
0x1001ae46  mov     [ebp+var_50], 0
0x1001ae4d  jmp     short loc_1001AE5E
0x1001ae4f  push    edi
0x1001ae50  push    0
0x1001ae52  push    0
0x1001ae54  mov     ecx, ebx
0x1001ae56  call    ?InsertRecord@Cursor@@AAEKW4CurInsType@@KAAVErr@@@Z; Cursor::InsertRecord(CurInsType,ulong,Err &)
0x1001ae5b  mov     [ebp+var_50], eax
0x1001ae5e  cmp     dword ptr [ebx+164h], 0
0x1001ae65  jbe     def_1001AC4C; jumptable 1001AC4C default case, case 3
0x1001ae6b  test    byte ptr [edi], 8
  ... truncated ...
```
