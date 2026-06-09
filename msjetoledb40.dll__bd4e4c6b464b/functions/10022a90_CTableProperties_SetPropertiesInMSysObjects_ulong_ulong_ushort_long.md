# CTableProperties::SetPropertiesInMSysObjects(ulong,ulong,ushort *,long &)

- ea: `0x10022a90`
- end: `0x10022c2c`
- name: `?SetPropertiesInMSysObjects@CTableProperties@@QAEJKKPAGAAJ@Z`
- size: `412`
- prototype: `int __thiscall(CTableProperties *__hidden this, JET_SESID sesid, unsigned int, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10044ee0`
- `0x10046bb0`

## callees

- `0x1001f2d0`
- `0x1001fb90`
- `0x10022a90`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x10022bfc`
- `msjet40!__imp__JetCloseTable@8` at `0x10022bfc`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022b0c`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10022b0c`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022b33`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10022b33`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10022b4f`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10022b4f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022b7a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10022b7a`
- `msjet40!__imp__JetSetColumn@28` at `0x10022bc1`
- `msjet40!__imp__JetSetColumn@28` at `0x10022bc1`
- `msjet40!__imp__JetUpdate@20` at `0x10022bde`
- `msjet40!__imp__JetUpdate@20` at `0x10022bde`

## pseudocode

```c
int __thiscall CTableProperties::SetPropertiesInMSysObjects(
        JoltProperties **this,
        JET_SESID sesid,
        unsigned int a3,
        unsigned __int16 *a4,
        int *a5)
{
  JoltProperties *v5; // edi
  int ObjectInfo; // eax
  int v7; // esi
  int TableColumnInfo; // eax
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  int v11; // eax
  unsigned int v12; // edx
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  unsigned int pcbActual; // [esp+Ch] [ebp-30h] BYREF
  CTableProperties *v17; // [esp+10h] [ebp-2Ch]
  unsigned int v18; // [esp+14h] [ebp-28h] BYREF
  unsigned int pvData; // [esp+18h] [ebp-24h] BYREF
  JET_TABLEID tableid; // [esp+1Ch] [ebp-20h] BYREF
  int v21; // [esp+20h] [ebp-1Ch] BYREF
  JET_COLUMNID columnid; // [esp+24h] [ebp-18h]

  v17 = (CTableProperties *)this;
  tableid = -1;
  *a5 = 0;
  v5 = this[3];
  v21 = 24;
  if ( JoltProperties::BinarySearch(v5, 0x10Au, &v18) < 0 || (*(_BYTE *)(*((_DWORD *)v5 + 4) + 48 * v18 + 40) & 1) == 0 )
    return 0;
  ObjectInfo = JetGetObjectInfo(sesid, a3, 1, L"Tables", a4, &tableid, 4, 3);
  *a5 = ObjectInfo;
  if ( ObjectInfo )
  {
    v7 = -2147467259;
  }
  else
  {
    TableColumnInfo = JetGetTableColumnInfo(sesid, tableid, L"Flags", &v21, 24, 0);
    *a5 = TableColumnInfo;
    if ( TableColumnInfo >= 0 )
    {
      v9 = JetPrepareUpdate(sesid, tableid, 2u);
      *a5 = v9;
      if ( v9 >= 0 )
      {
        v10 = JetRetrieveColumn(sesid, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
        *a5 = v10;
        if ( v10 >= 0 )
        {
          v11 = JoltProperties::IsbPropertySet(*((JoltProperties **)v17 + 3), 0x10Au);
          v12 = pvData | 8;
          if ( !v11 )
            v12 = pvData & 0xFFFFFFF7;
          pvData = v12;
          v13 = JetSetColumn(sesid, tableid, columnid, &pvData, 4u, 0, 0);
          *a5 = v13;
          if ( v13 >= 0 )
          {
            v14 = JetUpdate(sesid, tableid, 0, 0, 0);
            *a5 = v14;
            v7 = 0;
            if ( v14 < 0 )
              v7 = -2147467259;
          }
          else
          {
            v7 = -2147467259;
          }
        }
        else
        {
          v7 = -2147467259;
        }
      }
      else
      {
        v7 = -2147467259;
      }
    }
    else
    {
      v7 = -2147467259;
    }
  }
  if ( tableid != -1 )
    JetCloseTable(sesid, tableid);
  return v7;
}

```

## disassembly

```asm
0x10022a90  mov     edi, edi
0x10022a92  push    ebp
0x10022a93  mov     ebp, esp
0x10022a95  sub     esp, 30h
0x10022a98  mov     eax, ___security_cookie
0x10022a9d  xor     eax, ebp
0x10022a9f  mov     [ebp+var_4], eax
0x10022aa2  push    ebx
0x10022aa3  mov     ebx, [ebp+arg_8]
0x10022aa6  mov     eax, ecx
0x10022aa8  push    esi
0x10022aa9  mov     esi, [ebp+arg_C]
0x10022aac  push    edi
0x10022aad  mov     [ebp+var_2C], eax
0x10022ab0  mov     [ebp+tableid], 0FFFFFFFFh
0x10022ab7  mov     dword ptr [esi], 0
0x10022abd  mov     edi, [eax+0Ch]
0x10022ac0  lea     eax, [ebp+var_28]
0x10022ac3  push    eax; unsigned int *
0x10022ac4  push    10Ah; unsigned int
0x10022ac9  mov     ecx, edi; this
0x10022acb  mov     [ebp+var_1C], 18h
0x10022ad2  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10022ad7  test    eax, eax
0x10022ad9  js      loc_10022C17
0x10022adf  mov     eax, [ebp+var_28]
0x10022ae2  lea     ecx, [eax+eax*2]
0x10022ae5  mov     eax, [edi+10h]
0x10022ae8  add     ecx, ecx
0x10022aea  test    byte ptr [eax+ecx*8+28h], 1
0x10022aef  jz      loc_10022C17
0x10022af5  mov     edi, [ebp+sesid]
0x10022af8  lea     eax, [ebp+tableid]
0x10022afb  push    3
0x10022afd  push    4
0x10022aff  push    eax
0x10022b00  push    ebx
0x10022b01  push    offset aTables; "Tables"
0x10022b06  push    1
0x10022b08  push    [ebp+arg_4]
0x10022b0b  push    edi
0x10022b0c  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10022b12  mov     [esi], eax
0x10022b14  test    eax, eax
0x10022b16  jz      short loc_10022B22
0x10022b18  mov     esi, 80004005h
0x10022b1d  jmp     loc_10022BF2
0x10022b22  push    0
0x10022b24  push    18h
0x10022b26  lea     eax, [ebp+var_1C]
0x10022b29  push    eax
0x10022b2a  push    offset aFlags; "Flags"
0x10022b2f  push    [ebp+tableid]
0x10022b32  push    edi
0x10022b33  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10022b39  mov     [esi], eax
0x10022b3b  test    eax, eax
0x10022b3d  jns     short loc_10022B49
0x10022b3f  mov     esi, 80004005h
0x10022b44  jmp     loc_10022BF2
0x10022b49  push    2; prep
0x10022b4b  push    [ebp+tableid]; tableid
0x10022b4e  push    edi; sesid
0x10022b4f  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10022b55  mov     [esi], eax
0x10022b57  test    eax, eax
0x10022b59  jns     short loc_10022B65
0x10022b5b  mov     esi, 80004005h
0x10022b60  jmp     loc_10022BF2
0x10022b65  push    0; pretinfo
0x10022b67  push    0; grbit
0x10022b69  lea     eax, [ebp+pcbActual]
0x10022b6c  push    eax; pcbActual
0x10022b6d  push    4; cbData
0x10022b6f  lea     eax, [ebp+pvData]
0x10022b72  push    eax; pvData
0x10022b73  push    [ebp+columnid]; columnid
0x10022b76  push    [ebp+tableid]; tableid
0x10022b79  push    edi; sesid
0x10022b7a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10022b80  mov     [esi], eax
0x10022b82  test    eax, eax
0x10022b84  jns     short loc_10022B8D
0x10022b86  mov     esi, 80004005h
0x10022b8b  jmp     short loc_10022BF2
0x10022b8d  mov     ecx, [ebp+var_2C]
0x10022b90  push    10Ah; unsigned int
0x10022b95  mov     ecx, [ecx+0Ch]; this
0x10022b98  call    ?IsbPropertySet@JoltProperties@@QBEHK@Z; JoltProperties::IsbPropertySet(ulong)
0x10022b9d  mov     edx, [ebp+pvData]
0x10022ba0  mov     ecx, edx
0x10022ba2  push    0; psetinfo
0x10022ba4  push    0; grbit
0x10022ba6  and     ecx, 0FFFFFFF7h
0x10022ba9  or      edx, 8
0x10022bac  push    4; cbData
0x10022bae  test    eax, eax
0x10022bb0  lea     eax, [ebp+pvData]
0x10022bb3  push    eax; pvData
0x10022bb4  push    [ebp+columnid]; columnid
0x10022bb7  cmovz   edx, ecx
0x10022bba  push    [ebp+tableid]; tableid
0x10022bbd  mov     [ebp+pvData], edx
0x10022bc0  push    edi; sesid
0x10022bc1  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10022bc7  mov     [esi], eax
0x10022bc9  test    eax, eax
0x10022bcb  jns     short loc_10022BD4
0x10022bcd  mov     esi, 80004005h
0x10022bd2  jmp     short loc_10022BF2
0x10022bd4  push    0; pcbActual
0x10022bd6  push    0; cbBookmark
0x10022bd8  push    0; pvBookmark
0x10022bda  push    [ebp+tableid]; tableid
0x10022bdd  push    edi; sesid
0x10022bde  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x10022be4  mov     [esi], eax
0x10022be6  mov     ecx, 80004005h
0x10022beb  xor     esi, esi
0x10022bed  test    eax, eax
0x10022bef  cmovs   esi, ecx
0x10022bf2  mov     eax, [ebp+tableid]
0x10022bf5  cmp     eax, 0FFFFFFFFh
0x10022bf8  jz      short loc_10022C02
0x10022bfa  push    eax; tableid
0x10022bfb  push    edi; sesid
0x10022bfc  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10022c02  pop     edi
0x10022c03  mov     eax, esi
0x10022c05  pop     esi
0x10022c06  pop     ebx
0x10022c07  mov     ecx, [ebp+var_4]
0x10022c0a  xor     ecx, ebp; StackCookie
0x10022c0c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10022c11  mov     esp, ebp
0x10022c13  pop     ebp
0x10022c14  retn    10h
0x10022c17  mov     ecx, [ebp+var_4]
0x10022c1a  xor     eax, eax
0x10022c1c  pop     edi
0x10022c1d  pop     esi
0x10022c1e  xor     ecx, ebp; StackCookie
0x10022c20  pop     ebx
0x10022c21  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10022c26  mov     esp, ebp
0x10022c28  pop     ebp
0x10022c29  retn    10h
```
