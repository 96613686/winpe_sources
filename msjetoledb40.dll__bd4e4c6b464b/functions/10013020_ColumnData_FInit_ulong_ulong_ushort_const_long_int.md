# ColumnData::FInit(ulong,ulong,ushort const *,long &,int)

- ea: `0x10013020`
- end: `0x100130ec`
- name: `?FInit@ColumnData@@QAEJKKPBGAAJH@Z`
- size: `204`
- prototype: `int __thiscall(ColumnData *__hidden this, JET_SESID sesid, unsigned int, const unsigned __int16 *, int *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x100146e0`
- `0x10035f80`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003d390`
- `0x10047070`

## callees

- `0x10013020`
- `0x1001c6d0`
- `0x1004d420`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x100130d0`
- `msjet40!__imp__JetCloseTable@8` at `0x100130d0`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x10013063`
- `msjet40!__imp__JetGetColumnInfo@28` at `0x10013063`

## pseudocode

```c
int __thiscall ColumnData::FInit(
        ColumnData *this,
        JET_SESID sesid,
        unsigned int a3,
        const unsigned __int16 *a4,
        int *a5,
        int a6)
{
  int v6; // esi
  int ColumnInfo; // eax
  _BYTE v10[4]; // [esp+1Ch] [ebp-3Ch] BYREF
  JET_TABLEID tableid; // [esp+20h] [ebp-38h]
  int v12; // [esp+24h] [ebp-34h]

  v6 = 0;
  tableid = -1;
  ColumnInfo = JetGetColumnInfo(sesid, a3, a4, 0, v10, 56, 1);
  *a5 = ColumnInfo;
  if ( ColumnInfo != -3031 )
  {
    if ( ColumnInfo < 0 )
      return -2147467259;
    if ( v12 )
      v6 = (**(int (__thiscall ***)(ColumnData *, JET_SESID, unsigned int, _BYTE *, int, const unsigned __int16 *, _DWORD, int, int *))this)(
             this,
             sesid,
             a3,
             v10,
             -1,
             a4,
             0,
             a6,
             a5);
  }
  if ( tableid != -1 )
    JetCloseTable(sesid, tableid);
  return v6;
}

```

## disassembly

```asm
0x10013020  mov     edi, edi
0x10013022  push    ebp
0x10013023  mov     ebp, esp
0x10013025  and     esp, 0FFFFFFF8h
0x10013028  sub     esp, 44h
0x1001302b  mov     eax, ___security_cookie
0x10013030  xor     eax, esp
0x10013032  mov     [esp+44h+var_4], eax
0x10013036  mov     eax, [ebp+arg_C]
0x10013039  push    ebx
0x1001303a  mov     ebx, [ebp+arg_8]
0x1001303d  push    esi
0x1001303e  push    edi
0x1001303f  mov     edi, [ebp+sesid]
0x10013042  xor     esi, esi
0x10013044  push    1
0x10013046  push    38h ; '8'
0x10013048  mov     [esp+58h+var_40], eax
0x1001304c  lea     eax, [esp+58h+var_3C]
0x10013050  push    eax
0x10013051  push    esi
0x10013052  push    ebx
0x10013053  push    [ebp+arg_4]
0x10013056  mov     [esp+68h+var_44], ecx
0x1001305a  push    edi
0x1001305b  mov     [esp+6Ch+tableid], 0FFFFFFFFh
0x10013063  call    ds:__imp__JetGetColumnInfo@28; JetGetColumnInfo(x,x,x,x,x,x,x)
0x10013069  mov     ecx, [esp+50h+var_40]
0x1001306d  mov     [ecx], eax
0x1001306f  cmp     eax, 0FFFFF429h
0x10013074  jz      short loc_100130C5
0x10013076  test    eax, eax
0x10013078  jz      short loc_10013095
0x1001307a  jns     short loc_10013095
0x1001307c  mov     eax, 80004005h
0x10013081  pop     edi
0x10013082  pop     esi
0x10013083  pop     ebx
0x10013084  mov     ecx, [esp+44h+var_4]
0x10013088  xor     ecx, esp; StackCookie
0x1001308a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001308f  mov     esp, ebp
0x10013091  pop     ebp
0x10013092  retn    14h
0x10013095  cmp     [esp+50h+var_34], esi
0x10013099  jz      short loc_100130C5
0x1001309b  mov     eax, [esp+50h+var_44]
0x1001309f  push    ecx
0x100130a0  push    [ebp+arg_10]
0x100130a3  mov     eax, [eax]
0x100130a5  push    0
0x100130a7  push    ebx
0x100130a8  push    0FFFFFFFFh
0x100130aa  mov     esi, [eax]
0x100130ac  lea     eax, [esp+64h+var_3C]
0x100130b0  push    eax
0x100130b1  push    [ebp+arg_4]
0x100130b4  mov     ecx, esi
0x100130b6  push    edi
0x100130b7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100130bd  mov     ecx, [esp+70h+var_44]
0x100130c1  call    esi
0x100130c3  mov     esi, eax
0x100130c5  mov     ecx, [esp+50h+tableid]
0x100130c9  cmp     ecx, 0FFFFFFFFh
0x100130cc  jz      short loc_100130D6
0x100130ce  push    ecx; tableid
0x100130cf  push    edi; sesid
0x100130d0  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100130d6  mov     ecx, [esp+50h+var_4]
0x100130da  mov     eax, esi
0x100130dc  pop     edi
0x100130dd  pop     esi
0x100130de  pop     ebx
0x100130df  xor     ecx, esp; StackCookie
0x100130e1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100130e6  mov     esp, ebp
0x100130e8  pop     ebp
0x100130e9  retn    14h
```
