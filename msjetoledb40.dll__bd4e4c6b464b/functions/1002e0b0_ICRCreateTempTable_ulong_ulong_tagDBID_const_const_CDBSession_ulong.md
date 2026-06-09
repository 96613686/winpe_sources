# ICRCreateTempTable(ulong,ulong,tagDBID const * const,CDBSession *,ulong *)

- ea: `0x1002e0b0`
- end: `0x1002e1f8`
- name: `?ICRCreateTempTable@@YGJKKQBUtagDBID@@PAVCDBSession@@PAK@Z`
- size: `328`
- prototype: `int __stdcall(unsigned int, unsigned int, const struct tagDBID *const, struct CDBSession *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1002e3e0`

## callees

- `0x1001bdc0`
- `0x1001c6d0`
- `0x1002e0b0`

## import_xrefs

- `msjet40!__imp__JetOpenTempTable@24` at `0x1002e18d`
- `msjet40!__imp__JetOpenTempTable@24` at `0x1002e18d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002e135`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002e135`

## pseudocode

```c
int __stdcall ICRCreateTempTable(
        unsigned int a1,
        JET_SESID *a2,
        const struct tagDBID *const ptableid,
        struct CDBSession *a4,
        unsigned int *a5)
{
  JET_COLUMNDEF *v5; // edi
  int v7; // ebx
  bool v8; // zf
  __int16 v9; // ax
  JET_SESID v10; // eax
  unsigned int v11; // ecx
  JET_SESID v12; // esi
  int v13; // eax
  JET_ERR v14; // eax
  int v15; // eax
  int v16; // [esp+0h] [ebp-1Ch]
  const struct _GUID *v17; // [esp+4h] [ebp-18h]
  JET_SESID sesid; // [esp+Ch] [ebp-10h]
  int v19; // [esp+10h] [ebp-Ch] BYREF
  JET_COLUMNID *prgcolumnid; // [esp+14h] [ebp-8h]
  JET_COLUMNDEF *v21; // [esp+18h] [ebp-4h]

  sesid = a2[4];
  v5 = (JET_COLUMNDEF *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          384);
  v21 = v5;
  if ( !v5 )
    return -2147024882;
  prgcolumnid = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                                  *(_DWORD *)(*(_DWORD *)Sys + 12),
                                  Sys,
                                  64);
  if ( prgcolumnid )
  {
    if ( !a2[32] )
    {
      v8 = JetGetDatabaseInfo(a2[4], a2[5], &v19, 4, 18) == 0;
      v9 = 1033;
      if ( v8 )
        v9 = v19;
      a2[33] = v9;
    }
    v10 = a2[33];
    a2[32] = 1;
    v7 = 0;
    qmemcpy(v5, dword_10006100, 0x180u);
    v11 = 0;
    v12 = v10;
    do
    {
      v13 = 3 * v11++;
      *((_DWORD *)&v5->wCountry + 2 * v13) = v12;
    }
    while ( v11 < 0x10 );
    v14 = JetOpenTempTable(sesid, v5, 0x10u, 0, &ptableid->uGuid.guid.Data1, prgcolumnid);
    if ( v14 )
    {
      v7 = -2147467259;
      CExtError::SendJetErrortoOLEAuto(-2147467259, (char *)a2[4], v14, (int)&IID_IColumnsRowset, v16, v17);
    }
    v5 = v21;
  }
  else
  {
    v7 = -2147024882;
  }
  v15 = Sys;
  if ( Sys )
  {
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNDEF *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v5);
    v15 = Sys;
  }
  if ( prgcolumnid )
  {
    if ( v15 )
      (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)v15 + 20))(
        *(_DWORD *)(*(_DWORD *)v15 + 20),
        v15,
        prgcolumnid);
  }
  return v7;
}

```

## disassembly

```asm
0x1002e0b0  mov     edi, edi
0x1002e0b2  push    ebp
0x1002e0b3  mov     ebp, esp
0x1002e0b5  sub     esp, 10h
0x1002e0b8  push    ebx
0x1002e0b9  mov     ebx, [ebp+arg_4]
0x1002e0bc  push    esi; struct _GUID *
0x1002e0bd  push    edi; int
0x1002e0be  push    180h
0x1002e0c3  mov     eax, [ebx+10h]
0x1002e0c6  mov     [ebp+sesid], eax
0x1002e0c9  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1002e0ce  push    eax
0x1002e0cf  mov     ecx, [eax]
0x1002e0d1  mov     esi, [ecx+0Ch]
0x1002e0d4  mov     ecx, esi
0x1002e0d6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002e0dc  call    esi
0x1002e0de  mov     edi, eax
0x1002e0e0  mov     [ebp+var_4], edi
0x1002e0e3  test    edi, edi
0x1002e0e5  jnz     short loc_1002E0F5
0x1002e0e7  pop     edi
0x1002e0e8  pop     esi
0x1002e0e9  mov     eax, 8007000Eh
0x1002e0ee  pop     ebx
0x1002e0ef  mov     esp, ebp
0x1002e0f1  pop     ebp
0x1002e0f2  retn    0Ch
0x1002e0f5  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1002e0fb  push    40h ; '@'
0x1002e0fd  push    ecx
0x1002e0fe  mov     eax, [ecx]
0x1002e100  mov     esi, [eax+0Ch]
0x1002e103  mov     ecx, esi
0x1002e105  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002e10b  call    esi
0x1002e10d  mov     [ebp+prgcolumnid], eax
0x1002e110  test    eax, eax
0x1002e112  jnz     short loc_1002E11E
0x1002e114  mov     ebx, 8007000Eh
0x1002e119  jmp     loc_1002E1B2
0x1002e11e  cmp     dword ptr [ebx+80h], 0
0x1002e125  jnz     short loc_1002E14E
0x1002e127  push    12h
0x1002e129  push    4
0x1002e12b  lea     eax, [ebp+var_C]
0x1002e12e  push    eax
0x1002e12f  push    dword ptr [ebx+14h]
0x1002e132  push    dword ptr [ebx+10h]
0x1002e135  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1002e13b  test    eax, eax
0x1002e13d  mov     eax, 409h
0x1002e142  jnz     short loc_1002E147
0x1002e144  mov     eax, [ebp+var_C]
0x1002e147  cwde
0x1002e148  mov     [ebx+84h], eax
0x1002e14e  mov     eax, [ebx+84h]
0x1002e154  mov     ecx, 60h ; '`'
0x1002e159  mov     dword ptr [ebx+80h], 1
0x1002e163  mov     esi, offset dword_10006100
0x1002e168  mov     edx, edi
0x1002e16a  xor     ebx, ebx
0x1002e16c  rep movsd
0x1002e16e  xor     ecx, ecx
0x1002e170  mov     esi, eax
0x1002e172  lea     eax, [ecx+ecx*2]
0x1002e175  inc     ecx
0x1002e176  mov     [edx+eax*8+0Ch], esi
0x1002e17a  cmp     ecx, 10h
0x1002e17d  jb      short loc_1002E172
0x1002e17f  push    [ebp+prgcolumnid]; prgcolumnid
0x1002e182  push    [ebp+ptableid]; ptableid
0x1002e185  push    0; grbit
0x1002e187  push    10h; ccolumn
0x1002e189  push    edx; prgcolumndef
0x1002e18a  push    [ebp+sesid]; sesid
0x1002e18d  call    ds:__imp__JetOpenTempTable@24; JetOpenTempTable(x,x,x,x,x,x)
0x1002e193  test    eax, eax
0x1002e195  jz      short loc_1002E1AF
0x1002e197  mov     ebx, 80004005h
0x1002e19c  mov     ecx, [ebp+arg_4]
0x1002e19f  mov     edx, ebx
0x1002e1a1  push    offset _IID_IColumnsRowset; int
0x1002e1a6  push    eax; unsigned int
0x1002e1a7  mov     ecx, [ecx+10h]
0x1002e1aa  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1002e1af  mov     edi, [ebp+var_4]
0x1002e1b2  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1002e1b7  test    eax, eax
0x1002e1b9  jz      short loc_1002E1D1
0x1002e1bb  mov     ecx, [eax]
0x1002e1bd  push    edi
0x1002e1be  push    eax
0x1002e1bf  mov     esi, [ecx+14h]
0x1002e1c2  mov     ecx, esi
0x1002e1c4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002e1ca  call    esi
0x1002e1cc  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1002e1d1  mov     edx, [ebp+prgcolumnid]
0x1002e1d4  test    edx, edx
0x1002e1d6  jz      short loc_1002E1ED
0x1002e1d8  test    eax, eax
0x1002e1da  jz      short loc_1002E1ED
0x1002e1dc  mov     ecx, [eax]
0x1002e1de  push    edx
0x1002e1df  push    eax
0x1002e1e0  mov     esi, [ecx+14h]
0x1002e1e3  mov     ecx, esi
0x1002e1e5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002e1eb  call    esi
0x1002e1ed  pop     edi
0x1002e1ee  pop     esi
0x1002e1ef  mov     eax, ebx
0x1002e1f1  pop     ebx
0x1002e1f2  mov     esp, ebp
0x1002e1f4  pop     ebp
0x1002e1f5  retn    0Ch
```
