# CAlterTableTableProperties::SetJetPropertiesToJoltProperties(ulong,ulong,ulong,ushort *)

- ea: `0x10023030`
- end: `0x10023381`
- name: `?SetJetPropertiesToJoltProperties@CAlterTableTableProperties@@QAEJKKKPAG@Z`
- size: `849`
- prototype: `int __thiscall(JoltProperties **this, JET_SESID sesid, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x10046bb0`

## callees

- `0x1001fbe0`
- `0x1001fd70`
- `0x10023030`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x10023267`
- `msjet40!__imp__JetCloseTable@8` at `0x1002334f`
- `msjet40!__imp__JetCloseTable@8` at `0x10023267`
- `msjet40!__imp__JetCloseTable@8` at `0x1002334f`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1002309d`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10023115`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1002309d`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10023115`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x1002313c`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x100231cb`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x1002313c`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x100231cb`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10023169`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100231fa`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10023169`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100231fa`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x100232db`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x100232db`

## pseudocode

```c
int __thiscall CAlterTableTableProperties::SetJetPropertiesToJoltProperties(
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
  unsigned __int16 *v9; // edi
  _WORD *v10; // ecx
  int v11; // edx
  int v12; // esi
  _WORD *v13; // eax
  JET_ERR v14; // eax
  unsigned int i; // edi
  JET_ERR v16; // eax
  bool v17; // zf
  int v18; // edi
  int v19; // eax
  JoltProperties *v20; // eax
  int v21; // eax
  JET_TABLEID tableid; // [esp+Ch] [ebp-100CCh] BYREF
  JoltProperties *v24; // [esp+10h] [ebp-100C8h]
  unsigned int pcbActual; // [esp+14h] [ebp-100C4h] BYREF
  CAlterTableTableProperties *v26; // [esp+18h] [ebp-100C0h]
  int v27; // [esp+1Ch] [ebp-100BCh] BYREF
  unsigned int pvData; // [esp+20h] [ebp-100B8h] BYREF
  unsigned __int16 *v29; // [esp+24h] [ebp-100B4h]
  char v30[4]; // [esp+28h] [ebp-100B0h] BYREF
  JET_COLUMNID columnid; // [esp+2Ch] [ebp-100ACh]
  char v32[40]; // [esp+40h] [ebp-10098h] BYREF
  _BYTE v33[136]; // [esp+68h] [ebp-10070h] BYREF
  unsigned __int16 v34[32754]; // [esp+F0h] [ebp-FFE8h] BYREF

  tableid = -1;
  v26 = (CAlterTableTableProperties *)this;
  v5 = this[3];
  v29 = a5;
  v24 = v5;
  v27 = 0;
  if ( !a5 )
    return -2147024809;
  v7 = sesid;
  ObjectInfo = JetGetObjectInfo(sesid, a4, 0, L"Tables", a5, v32, 40, 5);
  if ( ObjectInfo == -1305 )
  {
    v6 = -2147217865;
  }
  else
  {
    if ( ObjectInfo )
    {
LABEL_5:
      v6 = -2147467259;
      goto LABEL_45;
    }
    v9 = a5;
    v10 = v33;
    v11 = 2147483646;
    v12 = 65;
    do
    {
      if ( !v11 )
        break;
      if ( !*v9 )
        break;
      *v10++ = *v9++;
      --v11;
      --v12;
    }
    while ( v12 );
    v7 = sesid;
    v13 = v10 - 1;
    if ( v12 )
      v13 = v10;
    *v13 = 0;
    if ( (int)JetGetObjectInfo(sesid, a4, 0, L"Tables", v33, &tableid, 4, 6) < 0 )
    {
      v6 = -2147467259;
      goto LABEL_45;
    }
    if ( (int)JetGetTableColumnInfo(sesid, tableid, L"Flags", v30, 24, 0) < 0 )
    {
      v6 = -2147467259;
      goto LABEL_45;
    }
    v14 = JetRetrieveColumn(sesid, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
    if ( v14 < 0 || v14 > 0 && v14 != 1004 )
      goto LABEL_5;
    v6 = JoltProperties::SetbProperty(v24, 0x10Au, (pvData >> 3) & 1);
    if ( v6 >= 0 )
    {
      for ( i = 0; i < 2; ++i )
      {
        if ( (int)JetGetTableColumnInfo(sesid, tableid, (&off_100510D8)[4 * i], v30, 24, 0) < 0
          || (v16 = JetRetrieveColumn(sesid, tableid, columnid, v34, 0xFFDEu, &pcbActual, 0, 0), v17 = v16 == 0, v16 < 0) )
        {
LABEL_48:
          v6 = -2147467259;
LABEL_44:
          v7 = sesid;
          goto LABEL_45;
        }
        if ( v16 > 0 )
        {
          if ( v16 != 1004 )
            goto LABEL_48;
          v17 = 0;
        }
        if ( v17 )
        {
          if ( (pcbActual & 0xFFFFFFFE) >= 0xFFDE )
LABEL_50:
            __report_rangecheckfailure();
          *(unsigned __int16 *)((char *)v34 + (pcbActual & 0xFFFFFFFE)) = 0;
          v6 = JoltProperties::SetStrValue(v24, dword_100510D4[4 * i], v34);
          if ( v6 < 0 )
            goto LABEL_44;
        }
      }
      JetCloseTable(sesid, tableid);
      tableid = -1;
      v18 = 0;
      while ( 1 )
      {
        v19 = dword_10003030[3 * v18];
        if ( !v19 )
          break;
        if ( v19 == 1 )
        {
          v20 = (JoltProperties *)*((_DWORD *)v26 + 3);
LABEL_35:
          v24 = v20;
        }
        v21 = JetRetrieveProperty(
                sesid,
                a4,
                L"Tables",
                v29,
                0,
                (&off_10003038)[3 * v18],
                v34,
                65502,
                &pcbActual,
                &v27,
                0,
                0);
        if ( v21 == -3600 || v21 == -1907 || v21 == -1809 )
          goto LABEL_53;
        if ( v21 < 0 )
          goto LABEL_48;
        if ( v27 != 10 )
          goto LABEL_53;
        if ( (pcbActual & 0xFFFFFFFE) >= 0xFFDE )
          goto LABEL_50;
        *(unsigned __int16 *)((char *)v34 + (pcbActual & 0xFFFFFFFE)) = 0;
        v6 = JoltProperties::SetStrValue(v24, *(&dword_10003034 + 3 * v18), v34);
        if ( v6 >= 0 )
        {
LABEL_53:
          if ( (unsigned int)++v18 < 2 )
            continue;
        }
        goto LABEL_44;
      }
      v20 = (JoltProperties *)*((_DWORD *)v26 + 2);
      goto LABEL_35;
    }
  }
LABEL_45:
  if ( tableid != -1 )
    JetCloseTable(v7, tableid);
  return v6;
}

```

## disassembly

```asm
0x10023030  mov     edi, edi
0x10023032  push    ebp
0x10023033  mov     ebp, esp
0x10023035  and     esp, 0FFFFFFF8h
0x10023038  mov     eax, 100CCh
0x1002303d  call    __chkstk
0x10023042  mov     eax, ___security_cookie
0x10023047  xor     eax, esp
0x10023049  mov     [esp+100CCh+var_4], eax
0x10023050  push    ebx
0x10023051  mov     eax, ecx
0x10023053  mov     [esp+100D0h+tableid], 0FFFFFFFFh
0x1002305b  push    esi
0x1002305c  mov     esi, [ebp+arg_C]
0x1002305f  mov     [esp+100D4h+var_100C0], eax
0x10023063  mov     ebx, [eax+0Ch]
0x10023066  mov     [esp+100D4h+var_100B4], esi
0x1002306a  mov     [esp+100D4h+var_100C8], ebx
0x1002306e  mov     [esp+100D4h+var_100BC], 0
0x10023076  push    edi
0x10023077  test    esi, esi
0x10023079  jnz     short loc_10023085
0x1002307b  mov     esi, 80070057h
0x10023080  jmp     loc_10023355
0x10023085  mov     edi, [ebp+sesid]
0x10023088  lea     eax, [esp+100D8h+var_10098]
0x1002308c  push    5
0x1002308e  push    28h ; '('
0x10023090  push    eax
0x10023091  push    esi
0x10023092  push    offset aTables; "Tables"
0x10023097  push    0
0x10023099  push    [ebp+arg_8]
0x1002309c  push    edi
0x1002309d  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x100230a3  cmp     eax, 0FFFFFAE7h
0x100230a8  jz      loc_10023375
0x100230ae  test    eax, eax
0x100230b0  jz      short loc_100230BC
0x100230b2  mov     esi, 80004005h
0x100230b7  jmp     loc_10023344
0x100230bc  mov     edi, esi
0x100230be  lea     ecx, [esp+100D8h+var_10070]
0x100230c2  mov     edx, 7FFFFFFEh
0x100230c7  mov     esi, 41h ; 'A'
0x100230cc  nop     dword ptr [eax+00h]
0x100230d0  test    edx, edx
0x100230d2  jz      short loc_100230ED
0x100230d4  movzx   eax, word ptr [edi]
0x100230d7  mov     ebx, eax
0x100230d9  test    ax, ax
0x100230dc  jz      short loc_100230ED
0x100230de  mov     [ecx], bx
0x100230e1  add     edi, 2
0x100230e4  add     ecx, 2
0x100230e7  dec     edx
0x100230e8  sub     esi, 1
0x100230eb  jnz     short loc_100230D0
0x100230ed  mov     edi, [ebp+sesid]
0x100230f0  lea     eax, [ecx-2]
0x100230f3  test    esi, esi
0x100230f5  push    6
0x100230f7  cmovnz  eax, ecx
0x100230fa  xor     ecx, ecx
0x100230fc  push    4
0x100230fe  mov     [eax], cx
0x10023101  lea     eax, [esp+100E0h+tableid]
0x10023105  push    eax
0x10023106  lea     eax, [esp+100E4h+var_10070]
0x1002310a  push    eax
0x1002310b  push    offset aTables; "Tables"
0x10023110  push    ecx
0x10023111  push    [ebp+arg_8]
0x10023114  push    edi
0x10023115  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1002311b  test    eax, eax
0x1002311d  jns     short loc_10023129
0x1002311f  mov     esi, 80004005h
0x10023124  jmp     loc_10023344
0x10023129  push    0
0x1002312b  push    18h
0x1002312d  lea     eax, [esp+100E0h+var_100B0]
0x10023131  push    eax
0x10023132  push    offset aFlags; "Flags"
0x10023137  push    [esp+100E8h+tableid]
0x1002313b  push    edi
0x1002313c  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10023142  test    eax, eax
0x10023144  jns     short loc_10023150
0x10023146  mov     esi, 80004005h
0x1002314b  jmp     loc_10023344
0x10023150  push    0; pretinfo
0x10023152  push    0; grbit
0x10023154  lea     eax, [esp+100E0h+pcbActual]
0x10023158  push    eax; pcbActual
0x10023159  push    4; cbData
0x1002315b  lea     eax, [esp+100E8h+pvData]
0x1002315f  push    eax; pvData
0x10023160  push    [esp+100ECh+columnid]; columnid
0x10023164  push    [esp+100F0h+tableid]; tableid
0x10023168  push    edi; sesid
0x10023169  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002316f  test    eax, eax
0x10023171  js      loc_100230B2
0x10023177  jle     short loc_10023184
0x10023179  cmp     eax, 3ECh
0x1002317e  jnz     loc_100230B2
0x10023184  mov     eax, [esp+100D8h+pvData]
0x10023188  mov     ecx, [esp+100D8h+var_100C8]; this
0x1002318c  shr     eax, 3
0x1002318f  and     eax, 1
0x10023192  push    eax; int
0x10023193  push    10Ah; unsigned int
0x10023198  call    ?SetbProperty@JoltProperties@@QAEJKH@Z; JoltProperties::SetbProperty(ulong,int)
0x1002319d  mov     esi, eax
0x1002319f  test    esi, esi
0x100231a1  js      loc_10023344
0x100231a7  xor     edi, edi
0x100231a9  nop     dword ptr [eax+00000000h]
0x100231b0  push    0
0x100231b2  push    18h
0x100231b4  mov     ebx, edi
0x100231b6  lea     eax, [esp+100E0h+var_100B0]
0x100231ba  shl     ebx, 4
0x100231bd  push    eax
0x100231be  push    off_100510D8[ebx]; "Connect"
0x100231c4  push    [esp+100E8h+tableid]
0x100231c8  push    [ebp+sesid]
0x100231cb  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x100231d1  test    eax, eax
0x100231d3  js      loc_1002336E
0x100231d9  push    0; pretinfo
0x100231db  push    0; grbit
0x100231dd  lea     eax, [esp+100E0h+pcbActual]
0x100231e1  push    eax; pcbActual
0x100231e2  push    0FFDEh; cbData
0x100231e7  lea     eax, [esp+100E8h+var_FFE8]
0x100231ee  push    eax; pvData
0x100231ef  push    [esp+100ECh+columnid]; columnid
0x100231f3  push    [esp+100F0h+tableid]; tableid
0x100231f7  push    [ebp+sesid]; sesid
0x100231fa  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10023200  test    eax, eax
0x10023202  js      loc_1002336E
0x10023208  jle     short loc_10023217
0x1002320a  cmp     eax, 3ECh
0x1002320f  jnz     loc_1002336E
0x10023215  test    eax, eax
0x10023217  jnz     short loc_10023256
0x10023219  mov     eax, [esp+100D8h+pcbActual]
0x1002321d  and     eax, 0FFFFFFFEh
0x10023220  cmp     eax, 0FFDEh
0x10023225  jnb     loc_1002337C
0x1002322b  xor     ecx, ecx
0x1002322d  mov     [esp+eax+100D8h+var_FFE8], cx
0x10023235  lea     eax, [esp+100D8h+var_FFE8]
0x1002323c  mov     ecx, [esp+100D8h+var_100C8]; this
0x10023240  push    eax; unsigned __int16 *
0x10023241  push    dword_100510D4[ebx]; unsigned int
0x10023247  call    ?SetStrValue@JoltProperties@@QAEJKPAG@Z; JoltProperties::SetStrValue(ulong,ushort *)
0x1002324c  mov     esi, eax
0x1002324e  test    esi, esi
0x10023250  js      loc_10023341
0x10023256  inc     edi
0x10023257  cmp     edi, 2
0x1002325a  jb      loc_100231B0
0x10023260  push    [esp+100D8h+tableid]; tableid
0x10023264  push    [ebp+sesid]; sesid
0x10023267  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1002326d  mov     [esp+100D8h+tableid], 0FFFFFFFFh
0x10023275  xor     edi, edi
0x10023277  nop     word ptr [eax+eax+00000000h]
0x10023280  lea     ebx, [edi+edi*2]
0x10023283  mov     eax, ds:dword_10003030[ebx*4]
0x1002328a  sub     eax, 0
0x1002328d  jz      short loc_1002329D
0x1002328f  sub     eax, 1
0x10023292  jnz     short loc_100232A8
0x10023294  mov     eax, [esp+100D8h+var_100C0]
0x10023298  mov     eax, [eax+0Ch]
0x1002329b  jmp     short loc_100232A4
0x1002329d  mov     eax, [esp+100D8h+var_100C0]
0x100232a1  mov     eax, [eax+8]
0x100232a4  mov     [esp+100D8h+var_100C8], eax
0x100232a8  push    0
0x100232aa  push    0
0x100232ac  lea     eax, [esp+100E0h+var_100BC]
0x100232b0  push    eax
0x100232b1  lea     eax, [esp+100E4h+pcbActual]
0x100232b5  push    eax
0x100232b6  push    0FFDEh
0x100232bb  lea     eax, [esp+100ECh+var_FFE8]
0x100232c2  push    eax
0x100232c3  push    ds:off_10003038[ebx*4]; "ValidationRule"
0x100232ca  push    0
0x100232cc  push    [esp+100F8h+var_100B4]
0x100232d0  push    offset aTables; "Tables"
0x100232d5  push    [ebp+arg_8]
0x100232d8  push    [ebp+sesid]
0x100232db  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x100232e1  cmp     eax, 0FFFFF1F0h
0x100232e6  jz      short loc_10023337
0x100232e8  cmp     eax, 0FFFFF88Dh
0x100232ed  jz      short loc_10023337
0x100232ef  cmp     eax, 0FFFFF8EFh
0x100232f4  jz      short loc_10023337
0x100232f6  test    eax, eax
0x100232f8  js      short loc_1002336E
0x100232fa  cmp     [esp+100D8h+var_100BC], 0Ah
0x100232ff  jnz     short loc_10023337
0x10023301  mov     eax, [esp+100D8h+pcbActual]
0x10023305  and     eax, 0FFFFFFFEh
0x10023308  cmp     eax, 0FFDEh
0x1002330d  jnb     short loc_1002337C
0x1002330f  xor     ecx, ecx
0x10023311  mov     [esp+eax+100D8h+var_FFE8], cx
0x10023319  lea     eax, [esp+100D8h+var_FFE8]
0x10023320  mov     ecx, [esp+100D8h+var_100C8]; this
0x10023324  push    eax; unsigned __int16 *
0x10023325  push    ds:dword_10003034[ebx*4]; unsigned int
0x1002332c  call    ?SetStrValue@JoltProperties@@QAEJKPAG@Z; JoltProperties::SetStrValue(ulong,ushort *)
0x10023331  mov     esi, eax
0x10023333  test    esi, esi
0x10023335  js      short loc_10023341
0x10023337  inc     edi
0x10023338  cmp     edi, 2
0x1002333b  jb      loc_10023280
0x10023341  mov     edi, [ebp+sesid]
0x10023344  mov     eax, [esp+100D8h+tableid]
0x10023348  cmp     eax, 0FFFFFFFFh
0x1002334b  jz      short loc_10023355
0x1002334d  push    eax; tableid
0x1002334e  push    edi; sesid
0x1002334f  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10023355  mov     ecx, [esp+100D8h+var_4]
0x1002335c  mov     eax, esi
0x1002335e  pop     edi
0x1002335f  pop     esi
0x10023360  pop     ebx
0x10023361  xor     ecx, esp; StackCookie
0x10023363  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10023368  mov     esp, ebp
0x1002336a  pop     ebp
0x1002336b  retn    10h
0x1002336e  mov     esi, 80004005h
0x10023373  jmp     short loc_10023341
0x10023375  mov     esi, 80040E37h
0x1002337a  jmp     short loc_10023344
0x1002337c  call    ___report_rangecheckfailure
```
