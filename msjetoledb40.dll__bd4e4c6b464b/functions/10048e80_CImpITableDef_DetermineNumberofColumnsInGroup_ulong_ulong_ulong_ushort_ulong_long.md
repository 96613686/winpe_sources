# CImpITableDef::DetermineNumberofColumnsInGroup(ulong,ulong,ulong,ushort *,ulong &,long &)

- ea: `0x10048e80`
- end: `0x10049020`
- name: `?DetermineNumberofColumnsInGroup@CImpITableDef@@QAEJKKKPAGAAKAAJ@Z`
- size: `416`
- prototype: `int __thiscall(CImpITableDef *__hidden this, JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, unsigned __int16 *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x10047070`

## callees

- `0x10048e80`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msjet40!__imp__JetGetBookmark@20` at `0x10048ec9`
- `msjet40!__imp__JetGetBookmark@20` at `0x10048ec9`
- `msjet40!__imp__JetGotoBookmark@16` at `0x10048fdf`
- `msjet40!__imp__JetGotoBookmark@16` at `0x10048fdf`
- `msjet40!__imp__JetMove@16` at `0x10048f04`
- `msjet40!__imp__JetMove@16` at `0x10048f04`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048f37`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10048f37`

## pseudocode

```c
int __thiscall CImpITableDef::DetermineNumberofColumnsInGroup(
        CImpITableDef *this,
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        unsigned __int16 *a5,
        unsigned int *a6,
        int *a7)
{
  int v7; // edi
  JET_ERR Bookmark; // eax
  int v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  int v13; // eax
  JET_ERR v14; // eax
  unsigned int pcbActual; // [esp+8h] [ebp-9Ch] BYREF
  _BYTE pvBookmark[4]; // [esp+Ch] [ebp-98h] BYREF
  unsigned int *v17; // [esp+10h] [ebp-94h]
  unsigned int v18; // [esp+14h] [ebp-90h] BYREF
  int v19; // [esp+18h] [ebp-8Ch]
  unsigned __int16 pvData[66]; // [esp+1Ch] [ebp-88h] BYREF

  v7 = 0;
  v17 = a6;
  v19 = 0;
  *a7 = 0;
  *a6 = 1;
  Bookmark = JetGetBookmark(sesid, tableid, pvBookmark, 4u, &pcbActual);
  *a7 = Bookmark;
  if ( Bookmark < 0 )
    return -2147467259;
  v10 = 0;
  while ( !v10 )
  {
    v11 = JetMove(sesid, tableid, 1, 0);
    *a7 = v11;
    if ( v11 == -1603 )
      goto LABEL_16;
    v12 = JetRetrieveColumn(sesid, tableid, columnid, pvData, 0x82u, &v18, 0, 0);
    *a7 = v12;
    if ( v12 < 0 )
    {
      v7 = -2147467259;
LABEL_9:
      if ( (v18 & 0xFFFFFFFE) >= 0x82 )
        __report_rangecheckfailure();
      *(unsigned __int16 *)((char *)pvData + (v18 & 0xFFFFFFFE)) = 0;
      goto LABEL_12;
    }
    if ( v12 != 1004 )
      goto LABEL_9;
    pvData[0] = 0;
LABEL_12:
    v13 = wcscmp(pvData, a5);
    if ( v13 )
      v13 = v13 < 0 ? -1 : 1;
    if ( v13 )
    {
      v10 = 1;
      v19 = 1;
      goto LABEL_17;
    }
    ++*v17;
LABEL_16:
    v10 = v19;
LABEL_17:
    if ( *a7 == -1603 )
      break;
  }
  v14 = JetGotoBookmark(sesid, tableid, pvBookmark, 4u);
  *a7 = v14;
  if ( v14 < 0 )
    return -2147467259;
  if ( v7 >= 0 )
    *a7 = 0;
  return v7;
}

```

## disassembly

```asm
0x10048e80  mov     edi, edi
0x10048e82  push    ebp
0x10048e83  mov     ebp, esp
0x10048e85  sub     esp, 9Ch
0x10048e8b  mov     eax, ___security_cookie
0x10048e90  xor     eax, ebp
0x10048e92  mov     [ebp+var_4], eax
0x10048e95  mov     eax, [ebp+arg_10]
0x10048e98  push    ebx
0x10048e99  mov     ebx, [ebp+arg_14]
0x10048e9c  push    edi
0x10048e9d  xor     edi, edi
0x10048e9f  mov     [ebp+var_94], eax
0x10048ea5  mov     [ebp+var_8C], edi
0x10048eab  mov     [ebx], edi
0x10048ead  mov     dword ptr [eax], 1
0x10048eb3  lea     eax, [ebp+pcbActual]
0x10048eb9  push    eax; pcbActual
0x10048eba  push    4; cbMax
0x10048ebc  lea     eax, [ebp+pvBookmark]
0x10048ec2  push    eax; pvBookmark
0x10048ec3  push    [ebp+tableid]; tableid
0x10048ec6  push    [ebp+sesid]; sesid
0x10048ec9  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x10048ecf  mov     [ebx], eax
0x10048ed1  test    eax, eax
0x10048ed3  jns     short loc_10048EEE
0x10048ed5  mov     edi, 80004005h
0x10048eda  mov     eax, edi
0x10048edc  pop     edi
0x10048edd  pop     ebx
0x10048ede  mov     ecx, [ebp+var_4]
0x10048ee1  xor     ecx, ebp; StackCookie
0x10048ee3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10048ee8  mov     esp, ebp
0x10048eea  pop     ebp
0x10048eeb  retn    18h
0x10048eee  xor     eax, eax
0x10048ef0  push    esi
0x10048ef1  mov     esi, edi
0x10048ef3  test    eax, eax
0x10048ef5  jnz     loc_10048FD0
0x10048efb  push    eax; grbit
0x10048efc  push    1; cRow
0x10048efe  push    [ebp+tableid]; tableid
0x10048f01  push    [ebp+sesid]; sesid
0x10048f04  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10048f0a  mov     [ebx], eax
0x10048f0c  cmp     eax, 0FFFFF9BDh
0x10048f11  jz      loc_10048FBE
0x10048f17  push    0; pretinfo
0x10048f19  push    0; grbit
0x10048f1b  lea     eax, [ebp+var_90]
0x10048f21  push    eax; pcbActual
0x10048f22  push    82h; cbData
0x10048f27  lea     eax, [ebp+pvData]
0x10048f2d  push    eax; pvData
0x10048f2e  push    [ebp+columnid]; columnid
0x10048f31  push    [ebp+tableid]; tableid
0x10048f34  push    [ebp+sesid]; sesid
0x10048f37  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10048f3d  mov     [ebx], eax
0x10048f3f  test    eax, eax
0x10048f41  jns     short loc_10048F4A
0x10048f43  mov     edi, 80004005h
0x10048f48  jmp     short loc_10048F53
0x10048f4a  mov     edi, esi
0x10048f4c  cmp     eax, 3ECh
0x10048f51  jz      short loc_10048F73
0x10048f53  mov     eax, [ebp+var_90]
0x10048f59  and     eax, 0FFFFFFFEh
0x10048f5c  cmp     eax, 82h
0x10048f61  jnb     loc_1004901B
0x10048f67  xor     ecx, ecx
0x10048f69  mov     [ebp+eax+pvData], cx
0x10048f71  jmp     short loc_10048F7E
0x10048f73  xor     eax, eax
0x10048f75  mov     edi, esi
0x10048f77  mov     [ebp+pvData], ax
0x10048f7e  mov     ecx, [ebp+arg_C]
0x10048f81  lea     eax, [ebp+pvData]
0x10048f87  mov     dx, [eax]
0x10048f8a  cmp     dx, [ecx]
0x10048f8d  jnz     short loc_10048FAD
0x10048f8f  test    dx, dx
0x10048f92  jz      short loc_10048FA9
0x10048f94  mov     dx, [eax+2]
0x10048f98  cmp     dx, [ecx+2]
0x10048f9c  jnz     short loc_10048FAD
0x10048f9e  add     eax, 4
0x10048fa1  add     ecx, 4
0x10048fa4  test    dx, dx
0x10048fa7  jnz     short loc_10048F87
0x10048fa9  xor     eax, eax
0x10048fab  jmp     short loc_10048FB2
0x10048fad  sbb     eax, eax
0x10048faf  or      eax, 1
0x10048fb2  test    eax, eax
0x10048fb4  jnz     short loc_1004900E
0x10048fb6  mov     eax, [ebp+var_94]
0x10048fbc  inc     dword ptr [eax]
0x10048fbe  mov     eax, [ebp+var_8C]
0x10048fc4  cmp     dword ptr [ebx], 0FFFFF9BDh
0x10048fca  jnz     loc_10048EF1
0x10048fd0  push    4; cbBookmark
0x10048fd2  lea     eax, [ebp+pvBookmark]
0x10048fd8  push    eax; pvBookmark
0x10048fd9  push    [ebp+tableid]; tableid
0x10048fdc  push    [ebp+sesid]; sesid
0x10048fdf  call    ds:__imp__JetGotoBookmark@16; JetGotoBookmark(x,x,x,x)
0x10048fe5  mov     [ebx], eax
0x10048fe7  pop     esi
0x10048fe8  test    eax, eax
0x10048fea  js      loc_10048ED5
0x10048ff0  test    edi, edi
0x10048ff2  js      short loc_10048FFA
0x10048ff4  mov     dword ptr [ebx], 0
0x10048ffa  mov     ecx, [ebp+var_4]
0x10048ffd  mov     eax, edi
0x10048fff  pop     edi
0x10049000  xor     ecx, ebp; StackCookie
0x10049002  pop     ebx
0x10049003  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10049008  mov     esp, ebp
0x1004900a  pop     ebp
0x1004900b  retn    18h
0x1004900e  mov     eax, 1
0x10049013  mov     [ebp+var_8C], eax
0x10049019  jmp     short loc_10048FC4
0x1004901b  call    ___report_rangecheckfailure
```
