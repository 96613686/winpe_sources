# ColumnData::FInit(ulong,ulong,ulong,long &,int,int)

- ea: `0x10013100`
- end: `0x100131c8`
- name: `?FInit@ColumnData@@QAEJKKKAAJHH@Z`
- size: `200`
- prototype: `int __thiscall(ColumnData *__hidden this, JET_SESID sesid, unsigned int, unsigned int, int *, int, int)`
- caller_count: `22`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1000e140`
- `0x100146e0`
- `0x10028340`
- `0x1002e3e0`
- `0x10035f80`
- `0x10036ad0`
- `0x100372f0`
- `0x10037c60`
- `0x10038310`
- `0x10038f10`
- `0x100395b0`
- `0x10039cc0`
- `0x1003a1a0`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003e190`
- `0x1003e7d0`
- `0x1003e990`
- `0x1003eb30`
- `0x1003eda0`
- `0x1003fcd0`
- `0x1003fea0`

## callees

- `0x10013100`
- `0x1001c6d0`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x100131ac`
- `msjet40!__imp__JetCloseTable@8` at `0x100131ac`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10013151`
- `msjet40!__imp__JetGetTableColumnInfo@24` at `0x10013151`
- `msjet40!__imp__JetGetTempQueryColumnInfo@28` at `0x10013148`
- `msjet40!__imp__JetGetTempQueryColumnInfo@28` at `0x10013148`

## pseudocode

```c
int __thiscall ColumnData::FInit(
        ColumnData *this,
        JET_SESID sesid,
        unsigned int a3,
        unsigned int a4,
        int *a5,
        int a6,
        int a7)
{
  int v7; // esi
  int TempQueryColumnInfo; // eax
  _BYTE v11[4]; // [esp+1Ch] [ebp-3Ch] BYREF
  JET_TABLEID tableid; // [esp+20h] [ebp-38h]
  int v13; // [esp+24h] [ebp-34h]

  v7 = 0;
  tableid = -1;
  if ( a6 )
    TempQueryColumnInfo = JetGetTempQueryColumnInfo(sesid, a3, a4, 0, v11, 56, 1);
  else
    TempQueryColumnInfo = JetGetTableColumnInfo(sesid, a4, 0, v11, 56, 1);
  *a5 = TempQueryColumnInfo;
  if ( TempQueryColumnInfo != -3031 )
  {
    if ( TempQueryColumnInfo >= 0 )
    {
      if ( v13 )
        v7 = (**(int (__thiscall ***)(ColumnData *, JET_SESID, unsigned int, _BYTE *, unsigned int, _DWORD, int, _DWORD, int *))this)(
               this,
               sesid,
               a3,
               v11,
               a4,
               0,
               a6,
               0,
               a5);
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
0x10013100  mov     edi, edi
0x10013102  push    ebp
0x10013103  mov     ebp, esp
0x10013105  and     esp, 0FFFFFFF8h
0x10013108  sub     esp, 44h
0x1001310b  mov     eax, ___security_cookie
0x10013110  xor     eax, esp
0x10013112  mov     [esp+44h+var_4], eax
0x10013116  mov     eax, [ebp+arg_C]
0x10013119  push    ebx
0x1001311a  mov     ebx, [ebp+arg_8]
0x1001311d  push    esi
0x1001311e  push    edi
0x1001311f  mov     edi, [ebp+sesid]
0x10013122  xor     esi, esi
0x10013124  push    1
0x10013126  push    38h ; '8'
0x10013128  mov     [esp+58h+var_40], eax
0x1001312c  lea     eax, [esp+58h+var_3C]
0x10013130  push    eax
0x10013131  push    esi
0x10013132  mov     [esp+60h+var_44], ecx
0x10013136  mov     [esp+60h+tableid], 0FFFFFFFFh
0x1001313e  push    ebx
0x1001313f  cmp     [ebp+arg_10], esi
0x10013142  jz      short loc_10013150
0x10013144  push    [ebp+arg_4]
0x10013147  push    edi
0x10013148  call    ds:__imp__JetGetTempQueryColumnInfo@28; JetGetTempQueryColumnInfo(x,x,x,x,x,x,x)
0x1001314e  jmp     short loc_10013157
0x10013150  push    edi
0x10013151  call    ds:__imp__JetGetTableColumnInfo@24; JetGetTableColumnInfo(x,x,x,x,x,x)
0x10013157  mov     ecx, [esp+50h+var_40]
0x1001315b  mov     [ecx], eax
0x1001315d  cmp     eax, 0FFFFF429h
0x10013162  jz      short loc_100131A1
0x10013164  test    eax, eax
0x10013166  jz      short loc_10013171
0x10013168  jns     short loc_10013171
0x1001316a  mov     esi, 80004005h
0x1001316f  jmp     short loc_100131A1
0x10013171  cmp     [esp+50h+var_34], esi
0x10013175  jz      short loc_100131A1
0x10013177  mov     eax, [esp+50h+var_44]
0x1001317b  push    ecx
0x1001317c  push    0
0x1001317e  push    [ebp+arg_10]
0x10013181  mov     eax, [eax]
0x10013183  push    0
0x10013185  push    ebx
0x10013186  mov     esi, [eax]
0x10013188  lea     eax, [esp+64h+var_3C]
0x1001318c  push    eax
0x1001318d  push    [ebp+arg_4]
0x10013190  mov     ecx, esi
0x10013192  push    edi
0x10013193  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10013199  mov     ecx, [esp+70h+var_44]
0x1001319d  call    esi
0x1001319f  mov     esi, eax
0x100131a1  mov     eax, [esp+50h+tableid]
0x100131a5  cmp     eax, 0FFFFFFFFh
0x100131a8  jz      short loc_100131B2
0x100131aa  push    eax; tableid
0x100131ab  push    edi; sesid
0x100131ac  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100131b2  mov     ecx, [esp+50h+var_4]
0x100131b6  mov     eax, esi
0x100131b8  pop     edi
0x100131b9  pop     esi
0x100131ba  pop     ebx
0x100131bb  xor     ecx, esp; StackCookie
0x100131bd  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100131c2  mov     esp, ebp
0x100131c4  pop     ebp
0x100131c5  retn    18h
```
