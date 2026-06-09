# CCommand::GetColumnData(ColumnData * *,long &)

- ea: `0x100146e0`
- end: `0x100147df`
- name: `?GetColumnData@CCommand@@IAEJPAPAVColumnData@@AAJ@Z`
- size: `255`
- prototype: `int __thiscall(CCommand *__hidden this, struct ColumnData **, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100132e0`
- `0x10013890`
- `0x1002e3e0`

## callees

- `0x10013020`
- `0x10013100`
- `0x100146e0`
- `0x1001c6d0`
- `0x1004ce5d`

## pseudocode

```c
int __thiscall CCommand::GetColumnData(CCommand *this, struct ColumnData **a2, int *a3)
{
  int v4; // ecx
  int v5; // eax
  int v6; // ebx
  ColumnData *v7; // eax
  bool v8; // zf
  int v9; // ecx
  int v10; // eax
  int v11; // eax

  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v5 = *((_DWORD *)this + 15);
  if ( (v5 & 0x20) != 0 )
  {
    if ( (v5 & 0x10) != 0 )
    {
      if ( *((_DWORD *)this + 26) )
        goto LABEL_16;
      v7 = (ColumnData *)operator new(0x10u);
      if ( !v7 )
      {
        *((_DWORD *)this + 26) = 0;
        v6 = -2147024882;
        goto LABEL_13;
      }
      *(_DWORD *)v7 = &ColumnData::`vftable';
      *((_DWORD *)v7 + 1) = 0;
      *((_DWORD *)v7 + 2) = 0;
      *((_DWORD *)v7 + 3) = 0;
      v8 = *((_DWORD *)this + 18) == 1;
      v9 = *((_DWORD *)this + 13);
      *((_DWORD *)this + 26) = v7;
      v10 = v8
          ? ColumnData::FInit(
              v7,
              *(_DWORD *)(v9 + 16),
              *(_DWORD *)(v9 + 20),
              *((const unsigned __int16 **)this + 19),
              a3,
              0)
          : ColumnData::FInit(v7, *(_DWORD *)(v9 + 16), *(_DWORD *)(v9 + 20), *((_DWORD *)this + 25), a3, 1, v9);
      v4 = v10;
      if ( v10 >= 0 )
      {
LABEL_16:
        *a2 = (struct ColumnData *)*((_DWORD *)this + 26);
        return v4;
      }
      v6 = -2147467259;
    }
    else
    {
      v6 = -2147217846;
    }
  }
  else
  {
    v6 = -2147217908;
  }
LABEL_13:
  v11 = *((_DWORD *)this + 26);
  if ( v11 )
  {
    (*(void (__thiscall **)(int, int))(*(_DWORD *)v11 + 4))(v11, 1);
    *((_DWORD *)this + 26) = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x100146e0  mov     edi, edi
0x100146e2  push    ebp
0x100146e3  mov     ebp, esp
0x100146e5  and     esp, 0FFFFFFF8h
0x100146e8  push    ecx
0x100146e9  push    ebx
0x100146ea  mov     ebx, [ebp+arg_4]
0x100146ed  push    esi
0x100146ee  mov     esi, [ebp+arg_0]
0x100146f1  push    edi
0x100146f2  mov     edi, ecx
0x100146f4  xor     ecx, ecx
0x100146f6  mov     [esi], ecx
0x100146f8  mov     [ebx], ecx
0x100146fa  mov     eax, [edi+3Ch]
0x100146fd  test    al, 20h
0x100146ff  jnz     short loc_1001470B
0x10014701  mov     ebx, 80040E0Ch
0x10014706  jmp     loc_1001479D
0x1001470b  test    al, 10h
0x1001470d  jnz     short loc_10014719
0x1001470f  mov     ebx, 80040E4Ah
0x10014714  jmp     loc_1001479D
0x10014719  cmp     [edi+68h], ecx
0x1001471c  jnz     loc_100147CF
0x10014722  push    10h; Size
0x10014724  call    ??2@YAPAXI@Z; operator new(uint)
0x10014729  add     esp, 4
0x1001472c  mov     [esp+10h+var_4], eax
0x10014730  test    eax, eax
0x10014732  jz      short loc_10014791
0x10014734  mov     dword ptr [eax], offset ??_7ColumnData@@6B@; const ColumnData::`vftable'
0x1001473a  mov     dword ptr [eax+4], 0
0x10014741  mov     dword ptr [eax+8], 0
0x10014748  mov     dword ptr [eax+0Ch], 0
0x1001474f  cmp     dword ptr [edi+48h], 1
0x10014753  mov     ecx, [edi+34h]
0x10014756  mov     [edi+68h], eax
0x10014759  jnz     short loc_10014770
0x1001475b  push    0; int
0x1001475d  push    ebx; int *
0x1001475e  push    dword ptr [edi+4Ch]; unsigned __int16 *
0x10014761  push    dword ptr [ecx+14h]; unsigned int
0x10014764  push    dword ptr [ecx+10h]; sesid
0x10014767  mov     ecx, eax; this
0x10014769  call    ?FInit@ColumnData@@QAEJKKPBGAAJH@Z; ColumnData::FInit(ulong,ulong,ushort const *,long &,int)
0x1001476e  jmp     short loc_10014784
0x10014770  push    ecx; int
0x10014771  push    1; int
0x10014773  push    ebx; int *
0x10014774  push    dword ptr [edi+64h]; unsigned int
0x10014777  push    dword ptr [ecx+14h]; unsigned int
0x1001477a  push    dword ptr [ecx+10h]; sesid
0x1001477d  mov     ecx, eax; this
0x1001477f  call    ?FInit@ColumnData@@QAEJKKKAAJHH@Z; ColumnData::FInit(ulong,ulong,ulong,long &,int,int)
0x10014784  mov     ecx, eax
0x10014786  test    ecx, ecx
0x10014788  jns     short loc_100147CF
0x1001478a  mov     ebx, 80004005h
0x1001478f  jmp     short loc_1001479D
0x10014791  mov     dword ptr [edi+68h], 0
0x10014798  mov     ebx, 8007000Eh
0x1001479d  mov     eax, [edi+68h]
0x100147a0  mov     [esp+10h+var_4], eax
0x100147a4  test    eax, eax
0x100147a6  jz      short loc_100147C4
0x100147a8  mov     edx, [eax]
0x100147aa  push    1
0x100147ac  mov     esi, [edx+4]
0x100147af  mov     ecx, esi
0x100147b1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100147b7  mov     ecx, [esp+14h+var_4]
0x100147bb  call    esi
0x100147bd  mov     dword ptr [edi+68h], 0
0x100147c4  mov     eax, ebx
0x100147c6  pop     edi
0x100147c7  pop     esi
0x100147c8  pop     ebx
0x100147c9  mov     esp, ebp
0x100147cb  pop     ebp
0x100147cc  retn    8
0x100147cf  mov     eax, [edi+68h]
0x100147d2  mov     [esi], eax
0x100147d4  pop     edi
0x100147d5  pop     esi
0x100147d6  mov     eax, ecx
0x100147d8  pop     ebx
0x100147d9  mov     esp, ebp
0x100147db  pop     ebp
0x100147dc  retn    8
```
