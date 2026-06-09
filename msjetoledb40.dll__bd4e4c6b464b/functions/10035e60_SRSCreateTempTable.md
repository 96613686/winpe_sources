# SRSCreateTempTable

- ea: `0x10035e60`
- end: `0x10035f79`
- name: `SRSCreateTempTable`
- size: `281`
- prototype: `int __fastcall(int, _DWORD *, JET_TABLEID *ptableid, JET_COLUMNID *prgcolumnid, JET_GRBIT grbit)`
- caller_count: `17`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x10035f80`
- `0x10036ad0`
- `0x100372f0`
- `0x10037c60`
- `0x10038310`
- `0x10038f10`
- `0x100395b0`
- `0x10039cc0`
- `0x1003a1a0`
- `0x1003a8b0`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003d390`
- `0x1003e190`
- `0x1003eb30`
- `0x1003eda0`
- `0x1003fea0`

## callees

- `0x1001bdc0`
- `0x1001c6d0`
- `0x10035e60`
- `0x1004dc81`

## import_xrefs

- `msjet40!__imp__JetOpenTempTable@24` at `0x10035f30`
- `msjet40!__imp__JetOpenTempTable@24` at `0x10035f30`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10035ecc`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10035ecc`

## pseudocode

```c
int __fastcall SRSCreateTempTable(
        int a1,
        _DWORD *a2,
        JET_TABLEID *ptableid,
        JET_COLUMNID *prgcolumnid,
        JET_GRBIT grbit)
{
  signed int v6; // ebx
  JET_COLUMNDEF *v7; // esi
  bool v9; // zf
  __int16 v10; // ax
  signed int v11; // eax
  int v12; // edx
  int v13; // ecx
  JET_ERR v14; // eax
  int v15; // ebx
  int v16; // [esp+0h] [ebp-1Ch]
  const struct _GUID *v17; // [esp+4h] [ebp-18h]
  JET_SESID sesid; // [esp+Ch] [ebp-10h]
  int v19; // [esp+10h] [ebp-Ch]
  int v20; // [esp+18h] [ebp-4h] BYREF

  v19 = 4 * a1;
  v6 = dword_10003310[4 * a1];
  sesid = a2[4];
  v7 = (JET_COLUMNDEF *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          24 * v6);
  if ( !v7 )
    return -2147024882;
  if ( !a2[32] )
  {
    v9 = JetGetDatabaseInfo(a2[4], a2[5], &v20, 4, 18) == 0;
    v10 = 1033;
    if ( v9 )
      v10 = v20;
    a2[33] = v10;
  }
  v20 = a2[33];
  a2[32] = 1;
  memcpy(v7, (&off_10003314)[v19], 24 * v6);
  v11 = 0;
  if ( v6 > 0 )
  {
    v12 = v20;
    do
    {
      v13 = 3 * v11++;
      *((_DWORD *)&v7->wCountry + 2 * v13) = v12;
    }
    while ( v11 < v6 );
  }
  v14 = JetOpenTempTable(sesid, v7, v6, grbit, ptableid, prgcolumnid);
  if ( v14 )
  {
    v15 = -2147467259;
    CExtError::SendJetErrortoOLEAuto(v14, (int)&IID_IDBSchemaRowset, v16, v17);
  }
  else
  {
    v15 = 0;
  }
  if ( Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNDEF *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v7);
  return v15;
}

```

## disassembly

```asm
0x10035e60  mov     edi, edi
0x10035e62  push    ebp
0x10035e63  mov     ebp, esp
0x10035e65  sub     esp, 10h
0x10035e68  push    ebx
0x10035e69  push    esi; struct _GUID *
0x10035e6a  mov     eax, ecx
0x10035e6c  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10035e72  shl     eax, 4
0x10035e75  push    edi; int
0x10035e76  mov     edi, edx
0x10035e78  mov     [ebp+var_C], eax
0x10035e7b  mov     ebx, ds:dword_10003310[eax]
0x10035e81  mov     eax, [edi+10h]
0x10035e84  mov     [ebp+sesid], eax
0x10035e87  mov     eax, [ecx]
0x10035e89  mov     esi, [eax+0Ch]
0x10035e8c  lea     eax, [ebx+ebx*2]
0x10035e8f  shl     eax, 3
0x10035e92  push    eax
0x10035e93  push    ecx
0x10035e94  mov     ecx, esi
0x10035e96  mov     [ebp+Size], eax
0x10035e99  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10035e9f  call    esi
0x10035ea1  mov     esi, eax
0x10035ea3  test    esi, esi
0x10035ea5  jnz     short loc_10035EB5
0x10035ea7  mov     eax, 8007000Eh
0x10035eac  pop     edi
0x10035ead  pop     esi
0x10035eae  pop     ebx
0x10035eaf  mov     esp, ebp
0x10035eb1  pop     ebp
0x10035eb2  retn    0Ch
0x10035eb5  cmp     dword ptr [edi+80h], 0
0x10035ebc  jnz     short loc_10035EE5
0x10035ebe  push    12h
0x10035ec0  push    4
0x10035ec2  lea     eax, [ebp+var_4]
0x10035ec5  push    eax
0x10035ec6  push    dword ptr [edi+14h]
0x10035ec9  push    dword ptr [edi+10h]
0x10035ecc  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10035ed2  test    eax, eax
0x10035ed4  mov     eax, 409h
0x10035ed9  jnz     short loc_10035EDE
0x10035edb  mov     eax, [ebp+var_4]
0x10035ede  cwde
0x10035edf  mov     [edi+84h], eax
0x10035ee5  mov     eax, [edi+84h]
0x10035eeb  push    [ebp+Size]; Size
0x10035eee  mov     [ebp+var_4], eax
0x10035ef1  mov     eax, [ebp+var_C]
0x10035ef4  mov     dword ptr [edi+80h], 1
0x10035efe  push    ds:off_10003314[eax]; Src
0x10035f04  push    esi; void *
0x10035f05  call    _memcpy
0x10035f0a  add     esp, 0Ch
0x10035f0d  xor     eax, eax
0x10035f0f  test    ebx, ebx
0x10035f11  jle     short loc_10035F22
0x10035f13  mov     edx, [ebp+var_4]
0x10035f16  lea     ecx, [eax+eax*2]
0x10035f19  inc     eax
0x10035f1a  mov     [esi+ecx*8+0Ch], edx
0x10035f1e  cmp     eax, ebx
0x10035f20  jl      short loc_10035F16
0x10035f22  push    [ebp+prgcolumnid]; prgcolumnid
0x10035f25  push    [ebp+ptableid]; ptableid
0x10035f28  push    [ebp+grbit]; grbit
0x10035f2b  push    ebx; ccolumn
0x10035f2c  push    esi; prgcolumndef
0x10035f2d  push    [ebp+sesid]; sesid
0x10035f30  call    ds:__imp__JetOpenTempTable@24; JetOpenTempTable(x,x,x,x,x,x)
0x10035f36  test    eax, eax
0x10035f38  jz      short loc_10035F51
0x10035f3a  mov     ebx, 80004005h
0x10035f3f  mov     ecx, [edi+10h]
0x10035f42  mov     edx, ebx
0x10035f44  push    offset _IID_IDBSchemaRowset; int
0x10035f49  push    eax; unsigned int
0x10035f4a  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10035f4f  jmp     short loc_10035F53
0x10035f51  xor     ebx, ebx
0x10035f53  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10035f59  test    ecx, ecx
0x10035f5b  jz      short loc_10035F6E
0x10035f5d  mov     edx, [ecx]
0x10035f5f  push    esi
0x10035f60  push    ecx
0x10035f61  mov     esi, [edx+14h]
0x10035f64  mov     ecx, esi
0x10035f66  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10035f6c  call    esi
0x10035f6e  pop     edi
0x10035f6f  pop     esi
0x10035f70  mov     eax, ebx
0x10035f72  pop     ebx
0x10035f73  mov     esp, ebp
0x10035f75  pop     ebp
0x10035f76  retn    0Ch
```
