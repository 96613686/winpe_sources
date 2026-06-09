# CSchemaRowset::MapStringPropertyValueToColumn(ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,long &)

- ea: `0x10035d90`
- end: `0x10035e4c`
- name: `?MapStringPropertyValueToColumn@CSchemaRowset@@IAEJKKPBG000KKAAJ@Z`
- size: `188`
- prototype: `int __thiscall(CSchemaRowset *__hidden this, JET_SESID sesid, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, JET_TABLEID tableid, JET_COLUMNID columnid, int *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x10036ad0`
- `0x100372f0`
- `0x10038f10`
- `0x100395b0`
- `0x1003c980`

## callees

- `0x10035d90`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`

## import_xrefs

- `msjet40!__imp__JetSetColumn@28` at `0x10035e27`
- `msjet40!__imp__JetSetColumn@28` at `0x10035e27`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10035dee`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x10035dee`

## pseudocode

```c
int __thiscall CSchemaRowset::MapStringPropertyValueToColumn(
        CSchemaRowset *this,
        JET_SESID sesid,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        int *a10)
{
  int v10; // eax
  JET_ERR v11; // eax
  unsigned int v13; // [esp-Ch] [ebp-FFFCh]
  _BYTE v14[4]; // [esp+8h] [ebp-FFE8h] BYREF
  unsigned int cbData; // [esp+Ch] [ebp-FFE4h] BYREF
  _WORD pvData[32750]; // [esp+10h] [ebp-FFE0h] BYREF

  cbData = 0;
  v10 = JetRetrieveProperty(sesid, a3, L"Tables", a5, a6, a7, pvData, 65500, &cbData, v14, 0, 0);
  *a10 = v10;
  if ( v10 < 0 )
  {
    v11 = 0;
  }
  else
  {
    if ( (cbData & 0xFFFFFFFE) >= 0xFFDC )
      __report_rangecheckfailure();
    v13 = cbData;
    *(_WORD *)((char *)pvData + (cbData & 0xFFFFFFFE)) = 0;
    v11 = JetSetColumn(sesid, tableid, columnid, pvData, v13, 0, 0);
  }
  *a10 = v11;
  return 0;
}

```

## disassembly

```asm
0x10035d90  mov     edi, edi
0x10035d92  push    ebp
0x10035d93  mov     ebp, esp
0x10035d95  mov     eax, 0FFE8h
0x10035d9a  call    __chkstk
0x10035d9f  mov     eax, ___security_cookie
0x10035da4  xor     eax, ebp
0x10035da6  mov     [ebp+var_4], eax
0x10035da9  mov     eax, [ebp+arg_14]
0x10035dac  mov     ecx, [ebp+arg_10]
0x10035daf  push    esi
0x10035db0  push    edi
0x10035db1  mov     edx, [ebp+arg_C]
0x10035db4  lea     edi, [ebp+var_FFE8]
0x10035dba  push    0
0x10035dbc  push    0
0x10035dbe  push    edi
0x10035dbf  mov     esi, [ebp+arg_20]
0x10035dc2  lea     edi, [ebp+cbData]
0x10035dc8  push    edi
0x10035dc9  push    0FFDCh
0x10035dce  lea     edi, [ebp+pvData]
0x10035dd4  mov     [ebp+cbData], 0
0x10035dde  push    edi
0x10035ddf  mov     edi, [ebp+sesid]
0x10035de2  push    eax
0x10035de3  push    ecx
0x10035de4  push    edx
0x10035de5  push    offset aTables; "Tables"
0x10035dea  push    [ebp+arg_4]
0x10035ded  push    edi
0x10035dee  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x10035df4  mov     [esi], eax
0x10035df6  test    eax, eax
0x10035df8  js      short loc_10035E2F
0x10035dfa  mov     ecx, [ebp+cbData]
0x10035e00  mov     eax, ecx
0x10035e02  and     eax, 0FFFFFFFEh
0x10035e05  cmp     eax, 0FFDCh
0x10035e0a  jnb     short loc_10035E47
0x10035e0c  xor     edx, edx
0x10035e0e  push    edx; psetinfo
0x10035e0f  push    edx; grbit
0x10035e10  push    ecx; cbData
0x10035e11  mov     [ebp+eax+pvData], dx
0x10035e19  lea     eax, [ebp+pvData]
0x10035e1f  push    eax; pvData
0x10035e20  push    [ebp+columnid]; columnid
0x10035e23  push    [ebp+tableid]; tableid
0x10035e26  push    edi; sesid
0x10035e27  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10035e2d  jmp     short loc_10035E31
0x10035e2f  xor     eax, eax
0x10035e31  mov     ecx, [ebp+var_4]
0x10035e34  mov     [esi], eax
0x10035e36  xor     ecx, ebp; StackCookie
0x10035e38  pop     edi
0x10035e39  xor     eax, eax
0x10035e3b  pop     esi
0x10035e3c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10035e41  mov     esp, ebp
0x10035e43  pop     ebp
0x10035e44  retn    24h ; '$'
0x10035e47  call    ___report_rangecheckfailure
```
