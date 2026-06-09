# CTableProperties::SetJetPropertiesToJoltProperties(ulong,ulong,ulong,ushort *)

- ea: `0x10022c40`
- end: `0x10023021`
- name: `?SetJetPropertiesToJoltProperties@CTableProperties@@QAEJKKKPAG@Z`
- size: `993`
- prototype: `int __thiscall(JoltProperties **this, JET_SESID sesid, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x10047070`

## callees

- `0x1001f2d0`
- `0x1001fbe0`
- `0x1001fd70`
- `0x10022c40`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x10022f09`
- `msjet40!__imp__JetCloseTable@8` at `0x10022fef`
- `msjet40!__imp__JetCloseTable@8` at `0x10022f09`
- `msjet40!__imp__JetCloseTable@8` at `0x10022fef`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022cad`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022d7a`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022cad`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022d7a`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022da1`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022e6d`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022da1`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022e6d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022dce`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022e9c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022dce`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022e9c`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10022f7b`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10022f7b`

## pseudocode

```c
int __thiscall CTableProperties::SetJetPropertiesToJoltProperties(
        JoltProperties **this,
        JET_SESID sesid,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  JoltProperties *v5; // ebx
  int v6; // esi
  JET_SESID v7; // edi
  int ObjectInfo; // eax
  int v9; // eax
  unsigned __int16 *v10; // edi
  _WORD *v11; // edx
  int v12; // ecx
  int v13; // esi
  _WORD *v14; // eax
  JET_ERR v15; // eax
  JoltProperties *v16; // ebx
  unsigned int i; // edi
  JET_ERR v18; // eax
  bool v19; // zf
  int v20; // edi
  int v21; // eax
  JoltProperties *v22; // eax
  int v23; // eax
  JET_TABLEID tableid; // [esp+10h] [ebp-100D0h] BYREF
  JoltProperties *v26; // [esp+14h] [ebp-100CCh]
  unsigned int pcbActual; // [esp+18h] [ebp-100C8h] BYREF
  unsigned int pvData; // [esp+1Ch] [ebp-100C4h] BYREF
  CTableProperties *v29; // [esp+20h] [ebp-100C0h]
  unsigned __int16 *v30; // [esp+24h] [ebp-100BCh]
  int v31; // [esp+28h] [ebp-100B8h] BYREF
  unsigned int v32; // [esp+2Ch] [ebp-100B4h] BYREF
  char v33[4]; // [esp+30h] [ebp-100B0h] BYREF
  JET_COLUMNID columnid; // [esp+34h] [ebp-100ACh]
  _BYTE v35[40]; // [esp+48h] [ebp-10098h] BYREF
  _BYTE v36[136]; // [esp+70h] [ebp-10070h] BYREF
  unsigned __int16 v37[32754]; // [esp+F8h] [ebp-FFE8h] BYREF

  tableid = -1;
  v29 = (CTableProperties *)this;
  v30 = a5;
  v31 = 0;
  v5 = this[3];
  v26 = v5;
  if ( !a5 )
    return -2147024809;
  v7 = sesid;
  ObjectInfo = JetGetObjectInfo(sesid, a4, 0, L"Tables", a5, v35, 40, 5);
  if ( ObjectInfo == -1305 )
  {
    v6 = -2147217865;
    goto LABEL_52;
  }
  if ( ObjectInfo )
  {
LABEL_5:
    v6 = -2147467259;
    goto LABEL_52;
  }
  if ( (v35[4] & 6) != 0 )
  {
    v6 = -2147467259;
    if ( JoltProperties::BinarySearch(v5, 0xF7u, &v32) < 0 )
      goto LABEL_52;
    v9 = *((_DWORD *)v5 + 4);
    if ( *(_WORD *)(v9 + 48 * v32 + 16) != 11 || (*(_DWORD *)(v9 + 48 * v32 + 32) & 0x400) == 0 )
      goto LABEL_52;
    *(_WORD *)(v9 + 48 * v32 + 24) = -1;
  }
  v10 = v30;
  v11 = v36;
  v12 = 2147483646;
  v13 = 65;
  do
  {
    if ( !v12 )
      break;
    if ( !*v10 )
      break;
    *v11++ = *v10++;
    --v12;
    --v13;
  }
  while ( v13 );
  v7 = sesid;
  v14 = v11 - 1;
  if ( v13 )
    v14 = v11;
  *v14 = 0;
  if ( (int)JetGetObjectInfo(sesid, a4, 0, L"Tables", v36, &tableid, 4, 6) < 0 )
  {
    v6 = -2147467259;
    goto LABEL_52;
  }
  if ( (int)JetGetTableColumnInfo(sesid, tableid, L"Flags", v33, 24, 0) < 0 )
  {
    v6 = -2147467259;
    goto LABEL_52;
  }
  v15 = JetRetrieveColumn(sesid, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
  if ( v15 < 0 || v15 > 0 && v15 != 1004 )
    goto LABEL_5;
  v16 = v26;
  v6 = JoltProperties::SetbProperty(v26, 0x10Au, (pvData >> 3) & 1);
  if ( v6 >= 0 )
  {
    v6 = JoltProperties::SetbProperty(v16, 0xF0u, (pvData >> 29) & 1);
    if ( v6 >= 0 )
    {
      v6 = JoltProperties::SetbProperty(v16, 0xF6u, (pvData >> 30) & 1);
      if ( v6 >= 0 )
      {
        for ( i = 0; i < 3; ++i )
        {
          if ( (int)JetGetTableColumnInfo(sesid, tableid, (&off_10003058)[4 * i], v33, 24, 0) < 0
            || (v18 = JetRetrieveColumn(sesid, tableid, columnid, v37, 0xFFDEu, &pcbActual, 0, 0),
                v19 = v18 == 0,
                v18 < 0) )
          {
LABEL_55:
            v6 = -2147467259;
LABEL_51:
            v7 = sesid;
            goto LABEL_52;
          }
          if ( v18 > 0 )
          {
            if ( v18 != 1004 )
              goto LABEL_55;
            v19 = 0;
          }
          if ( v19 )
          {
            if ( (pcbActual & 0xFFFFFFFE) >= 0xFFDE )
LABEL_57:
              __report_rangecheckfailure();
            *(unsigned __int16 *)((char *)v37 + (pcbActual & 0xFFFFFFFE)) = 0;
            v6 = JoltProperties::SetStrValue(v26, dword_10003054[4 * i], v37);
            if ( v6 < 0 )
              goto LABEL_51;
          }
        }
        JetCloseTable(sesid, tableid);
        tableid = -1;
        v20 = 0;
        while ( 1 )
        {
          v21 = dword_10003030[3 * v20];
          if ( !v21 )
            break;
          if ( v21 == 1 )
          {
            v22 = (JoltProperties *)*((_DWORD *)v29 + 3);
LABEL_42:
            v26 = v22;
          }
          v23 = JetRetrieveProperty(
                  sesid,
                  a4,
                  L"Tables",
                  v30,
                  0,
                  (&off_10003038)[3 * v20],
                  v37,
                  65502,
                  &pcbActual,
                  &v31,
                  0,
                  0);
          if ( v23 == -3600 || v23 == -1907 || v23 == -1809 )
            goto LABEL_60;
          if ( v23 < 0 )
            goto LABEL_55;
          if ( v31 != 10 )
            goto LABEL_60;
          if ( (pcbActual & 0xFFFFFFFE) >= 0xFFDE )
            goto LABEL_57;
          *(unsigned __int16 *)((char *)v37 + (pcbActual & 0xFFFFFFFE)) = 0;
          v6 = JoltProperties::SetStrValue(v26, *(&dword_10003034 + 3 * v20), v37);
          if ( v6 >= 0 )
          {
LABEL_60:
            if ( (unsigned int)++v20 < 2 )
              continue;
          }
          goto LABEL_51;
        }
        v22 = (JoltProperties *)*((_DWORD *)v29 + 2);
        goto LABEL_42;
      }
    }
  }
LABEL_52:
  if ( tableid != -1 )
    JetCloseTable(v7, tableid);
  return v6;
}

```

## disassembly

```asm
0x10022c40  mov     edi, edi
0x10022c42  push    ebp
0x10022c43  mov     ebp, esp
0x10022c45  and     esp, 0FFFFFFF8h
0x10022c48  mov     eax, 100D4h
0x10022c4d  call    __chkstk
0x10022c52  mov     eax, ___security_cookie
0x10022c57  xor     eax, esp
0x10022c59  mov     [esp+100D4h+var_4], eax
0x10022c60  mov     eax, ecx
0x10022c62  mov     [esp+100D4h+tableid], 0FFFFFFFFh
0x10022c6a  mov     ecx, [ebp+arg_C]
0x10022c6d  mov     [esp+100D4h+var_100C0], eax
0x10022c71  mov     [esp+100D4h+var_100BC], ecx
0x10022c75  mov     [esp+100D4h+var_100B8], 0
0x10022c7d  push    ebx
0x10022c7e  mov     ebx, [eax+0Ch]
0x10022c81  mov     [esp+100D8h+var_100CC], ebx
0x10022c85  push    esi
0x10022c86  push    edi
0x10022c87  test    ecx, ecx
0x10022c89  jnz     short loc_10022C95
0x10022c8b  mov     esi, 80070057h
0x10022c90  jmp     loc_10022FF5
0x10022c95  mov     edi, [ebp+sesid]
0x10022c98  lea     eax, [esp+100E0h+var_10098]
0x10022c9c  push    5
0x10022c9e  push    28h ; '('
0x10022ca0  push    eax
0x10022ca1  push    ecx
0x10022ca2  push    offset aTables; "Tables"
0x10022ca7  push    0
0x10022ca9  push    [ebp+arg_8]
0x10022cac  push    edi
0x10022cad  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10022cb3  cmp     eax, 0FFFFFAE7h
0x10022cb8  jz      loc_10023015
0x10022cbe  test    eax, eax
0x10022cc0  jz      short loc_10022CCC
0x10022cc2  mov     esi, 80004005h
0x10022cc7  jmp     loc_10022FE4
0x10022ccc  test    [esp+100E0h+var_10094], 6
0x10022cd1  jz      short loc_10022D23
0x10022cd3  lea     eax, [esp+100E0h+var_100B4]
0x10022cd7  mov     ecx, ebx; this
0x10022cd9  push    eax; unsigned int *
0x10022cda  push    0F7h; unsigned int
0x10022cdf  mov     esi, 80004005h
0x10022ce4  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10022ce9  test    eax, eax
0x10022ceb  js      loc_10022FE4
0x10022cf1  mov     eax, [esp+100E0h+var_100B4]
0x10022cf5  mov     edx, 0Bh
0x10022cfa  lea     ecx, [eax+eax*2]
0x10022cfd  mov     eax, [ebx+10h]
0x10022d00  add     ecx, ecx
0x10022d02  cmp     dx, [eax+ecx*8+10h]
0x10022d07  jnz     loc_10022FE4
0x10022d0d  test    dword ptr [eax+ecx*8+20h], 400h
0x10022d15  jz      loc_10022FE4
0x10022d1b  or      edx, 0FFFFFFFFh
0x10022d1e  mov     [eax+ecx*8+18h], dx
0x10022d23  mov     edi, [esp+100E0h+var_100BC]
0x10022d27  lea     edx, [esp+100E0h+var_10070]
0x10022d2b  mov     ecx, 7FFFFFFEh
0x10022d30  mov     esi, 41h ; 'A'
0x10022d35  test    ecx, ecx
0x10022d37  jz      short loc_10022D52
0x10022d39  movzx   eax, word ptr [edi]
0x10022d3c  mov     ebx, eax
0x10022d3e  test    ax, ax
0x10022d41  jz      short loc_10022D52
0x10022d43  mov     [edx], bx
0x10022d46  add     edi, 2
0x10022d49  add     edx, 2
0x10022d4c  dec     ecx
0x10022d4d  sub     esi, 1
0x10022d50  jnz     short loc_10022D35
0x10022d52  mov     edi, [ebp+sesid]
0x10022d55  lea     eax, [edx-2]
0x10022d58  test    esi, esi
0x10022d5a  push    6
0x10022d5c  cmovnz  eax, edx
0x10022d5f  xor     ecx, ecx
0x10022d61  push    4
0x10022d63  mov     [eax], cx
0x10022d66  lea     eax, [esp+100E8h+tableid]
0x10022d6a  push    eax
0x10022d6b  lea     eax, [esp+100ECh+var_10070]
0x10022d6f  push    eax
0x10022d70  push    offset aTables; "Tables"
0x10022d75  push    ecx
0x10022d76  push    [ebp+arg_8]
0x10022d79  push    edi
0x10022d7a  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10022d80  test    eax, eax
0x10022d82  jns     short loc_10022D8E
0x10022d84  mov     esi, 80004005h
0x10022d89  jmp     loc_10022FE4
0x10022d8e  push    0
0x10022d90  push    18h
0x10022d92  lea     eax, [esp+100E8h+var_100B0]
0x10022d96  push    eax
0x10022d97  push    offset aFlags; "Flags"
0x10022d9c  push    [esp+100F0h+tableid]
0x10022da0  push    edi
0x10022da1  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10022da7  test    eax, eax
0x10022da9  jns     short loc_10022DB5
0x10022dab  mov     esi, 80004005h
0x10022db0  jmp     loc_10022FE4
0x10022db5  push    0; pretinfo
0x10022db7  push    0; grbit
0x10022db9  lea     eax, [esp+100E8h+pcbActual]
0x10022dbd  push    eax; pcbActual
0x10022dbe  push    4; cbData
0x10022dc0  lea     eax, [esp+100F0h+pvData]
0x10022dc4  push    eax; pvData
0x10022dc5  push    [esp+100F4h+columnid]; columnid
0x10022dc9  push    [esp+100F8h+tableid]; tableid
0x10022dcd  push    edi; sesid
0x10022dce  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10022dd4  test    eax, eax
0x10022dd6  js      loc_10022CC2
0x10022ddc  jle     short loc_10022DE9
0x10022dde  cmp     eax, 3ECh
0x10022de3  jnz     loc_10022CC2
0x10022de9  mov     eax, [esp+100E0h+pvData]
0x10022ded  mov     ebx, [esp+100E0h+var_100CC]
0x10022df1  mov     ecx, ebx; this
0x10022df3  shr     eax, 3
0x10022df6  and     eax, 1
0x10022df9  push    eax; int
0x10022dfa  push    10Ah; unsigned int
0x10022dff  call    ?SetbProperty@JoltProperties@@QAEJKH@Z; JoltProperties::SetbProperty(ulong,int)
0x10022e04  mov     esi, eax
0x10022e06  test    esi, esi
0x10022e08  js      loc_10022FE4
0x10022e0e  mov     eax, [esp+100E0h+pvData]
0x10022e12  mov     ecx, ebx; this
0x10022e14  shr     eax, 1Dh
0x10022e17  and     eax, 1
0x10022e1a  push    eax; int
0x10022e1b  push    0F0h; unsigned int
0x10022e20  call    ?SetbProperty@JoltProperties@@QAEJKH@Z; JoltProperties::SetbProperty(ulong,int)
0x10022e25  mov     esi, eax
0x10022e27  test    esi, esi
0x10022e29  js      loc_10022FE4
0x10022e2f  mov     eax, [esp+100E0h+pvData]
0x10022e33  mov     ecx, ebx; this
0x10022e35  shr     eax, 1Eh
0x10022e38  and     eax, 1
0x10022e3b  push    eax; int
0x10022e3c  push    0F6h; unsigned int
0x10022e41  call    ?SetbProperty@JoltProperties@@QAEJKH@Z; JoltProperties::SetbProperty(ulong,int)
0x10022e46  mov     esi, eax
0x10022e48  test    esi, esi
0x10022e4a  js      loc_10022FE4
0x10022e50  xor     edi, edi
0x10022e52  push    0
0x10022e54  push    18h
0x10022e56  mov     ebx, edi
0x10022e58  lea     eax, [esp+100E8h+var_100B0]
0x10022e5c  shl     ebx, 4
0x10022e5f  push    eax
0x10022e60  push    ds:off_10003058[ebx]; "Connect"
0x10022e66  push    [esp+100F0h+tableid]
0x10022e6a  push    [ebp+sesid]
0x10022e6d  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10022e73  test    eax, eax
0x10022e75  js      loc_1002300E
0x10022e7b  push    0; pretinfo
0x10022e7d  push    0; grbit
0x10022e7f  lea     eax, [esp+100E8h+pcbActual]
0x10022e83  push    eax; pcbActual
0x10022e84  push    0FFDEh; cbData
0x10022e89  lea     eax, [esp+100F0h+var_FFE8]
0x10022e90  push    eax; pvData
0x10022e91  push    [esp+100F4h+columnid]; columnid
0x10022e95  push    [esp+100F8h+tableid]; tableid
0x10022e99  push    [ebp+sesid]; sesid
0x10022e9c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10022ea2  test    eax, eax
0x10022ea4  js      loc_1002300E
0x10022eaa  jle     short loc_10022EB9
0x10022eac  cmp     eax, 3ECh
0x10022eb1  jnz     loc_1002300E
0x10022eb7  test    eax, eax
0x10022eb9  jnz     short loc_10022EF8
0x10022ebb  mov     eax, [esp+100E0h+pcbActual]
0x10022ebf  and     eax, 0FFFFFFFEh
0x10022ec2  cmp     eax, 0FFDEh
0x10022ec7  jnb     loc_1002301C
0x10022ecd  xor     ecx, ecx
0x10022ecf  mov     [esp+eax+100E0h+var_FFE8], cx
0x10022ed7  lea     eax, [esp+100E0h+var_FFE8]
0x10022ede  mov     ecx, [esp+100E0h+var_100CC]; this
0x10022ee2  push    eax; unsigned __int16 *
0x10022ee3  push    ds:dword_10003054[ebx]; unsigned int
0x10022ee9  call    ?SetStrValue@JoltProperties@@QAEJKPAG@Z; JoltProperties::SetStrValue(ulong,ushort *)
0x10022eee  mov     esi, eax
0x10022ef0  test    esi, esi
0x10022ef2  js      loc_10022FE1
0x10022ef8  inc     edi
0x10022ef9  cmp     edi, 3
0x10022efc  jb      loc_10022E52
0x10022f02  push    [esp+100E0h+tableid]; tableid
0x10022f06  push    [ebp+sesid]; sesid
0x10022f09  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10022f0f  mov     [esp+100E0h+tableid], 0FFFFFFFFh
0x10022f17  xor     edi, edi
0x10022f19  nop     dword ptr [eax+00000000h]
0x10022f20  lea     ebx, [edi+edi*2]
0x10022f23  mov     eax, ds:dword_10003030[ebx*4]
0x10022f2a  sub     eax, 0
0x10022f2d  jz      short loc_10022F3D
0x10022f2f  sub     eax, 1
0x10022f32  jnz     short loc_10022F48
0x10022f34  mov     eax, [esp+100E0h+var_100C0]
0x10022f38  mov     eax, [eax+0Ch]
0x10022f3b  jmp     short loc_10022F44
0x10022f3d  mov     eax, [esp+100E0h+var_100C0]
0x10022f41  mov     eax, [eax+8]
0x10022f44  mov     [esp+100E0h+var_100CC], eax
0x10022f48  push    0
0x10022f4a  push    0
0x10022f4c  lea     eax, [esp+100E8h+var_100B8]
0x10022f50  push    eax
0x10022f51  lea     eax, [esp+100ECh+pcbActual]
0x10022f55  push    eax
0x10022f56  push    0FFDEh
0x10022f5b  lea     eax, [esp+100F4h+var_FFE8]
0x10022f62  push    eax
0x10022f63  push    ds:off_10003038[ebx*4]; "ValidationRule"
0x10022f6a  push    0
0x10022f6c  push    [esp+10100h+var_100BC]
0x10022f70  push    offset aTables; "Tables"
0x10022f75  push    [ebp+arg_8]
0x10022f78  push    [ebp+sesid]
0x10022f7b  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x10022f81  cmp     eax, 0FFFFF1F0h
0x10022f86  jz      short loc_10022FD7
0x10022f88  cmp     eax, 0FFFFF88Dh
0x10022f8d  jz      short loc_10022FD7
0x10022f8f  cmp     eax, 0FFFFF8EFh
0x10022f94  jz      short loc_10022FD7
0x10022f96  test    eax, eax
0x10022f98  js      short loc_1002300E
0x10022f9a  cmp     [esp+100E0h+var_100B8], 0Ah
0x10022f9f  jnz     short loc_10022FD7
0x10022fa1  mov     eax, [esp+100E0h+pcbActual]
0x10022fa5  and     eax, 0FFFFFFFEh
0x10022fa8  cmp     eax, 0FFDEh
0x10022fad  jnb     short loc_1002301C
0x10022faf  xor     ecx, ecx
0x10022fb1  mov     [esp+eax+100E0h+var_FFE8], cx
0x10022fb9  lea     eax, [esp+100E0h+var_FFE8]
0x10022fc0  mov     ecx, [esp+100E0h+var_100CC]; this
0x10022fc4  push    eax; unsigned __int16 *
0x10022fc5  push    ds:dword_10003034[ebx*4]; unsigned int
0x10022fcc  call    ?SetStrValue@JoltProperties@@QAEJKPAG@Z; JoltProperties::SetStrValue(ulong,ushort *)
0x10022fd1  mov     esi, eax
0x10022fd3  test    esi, esi
0x10022fd5  js      short loc_10022FE1
0x10022fd7  inc     edi
0x10022fd8  cmp     edi, 2
0x10022fdb  jb      loc_10022F20
0x10022fe1  mov     edi, [ebp+sesid]
0x10022fe4  mov     eax, [esp+100E0h+tableid]
0x10022fe8  cmp     eax, 0FFFFFFFFh
0x10022feb  jz      short loc_10022FF5
0x10022fed  push    eax; tableid
0x10022fee  push    edi; sesid
0x10022fef  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10022ff5  mov     ecx, [esp+100E0h+var_4]
0x10022ffc  mov     eax, esi
0x10022ffe  pop     edi
0x10022fff  pop     esi
0x10023000  pop     ebx
0x10023001  xor     ecx, esp; StackCookie
0x10023003  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10023008  mov     esp, ebp
0x1002300a  pop     ebp
0x1002300b  retn    10h
0x1002300e  mov     esi, 80004005h
0x10023013  jmp     short loc_10022FE1
0x10023015  mov     esi, 80040E37h
0x1002301a  jmp     short loc_10022FE4
0x1002301c  call    ___report_rangecheckfailure
```
