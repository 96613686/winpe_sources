# CSchemaRowset::MapStringPropertyBlobValueToColumn(void *,ulong,ulong,ushort const *,ushort const *,ulong,ulong,long &)

- ea: `0x10035cc0`
- end: `0x10035d86`
- name: `?MapStringPropertyBlobValueToColumn@CSchemaRowset@@IAEJPAXKKPBG1KKAAJ@Z`
- size: `198`
- prototype: `void *__thiscall(CSchemaRowset *this, void *, JET_SESID sesid, unsigned int, const unsigned __int16 *, const unsigned __int16 *, JET_TABLEID tableid, JET_COLUMNID columnid, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x10035f80`

## callees

- `0x10035cc0`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc50`

## import_xrefs

- `msjet40!__imp__JetSetColumn@28` at `0x10035d62`
- `msjet40!__imp__JetSetColumn@28` at `0x10035d62`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10035d27`
- `msjet40!__imp__JetGetPropertyBlobValue@32` at `0x10035d27`

## pseudocode

```c
void *__thiscall CSchemaRowset::MapStringPropertyBlobValueToColumn(
        CSchemaRowset *this,
        void *a2,
        JET_SESID sesid,
        unsigned int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        int *a9)
{
  void *result; // eax
  int PropertyBlobValue; // eax
  JET_ERR v11; // eax
  unsigned int v12; // [esp-Ch] [ebp-FFF8h]
  _BYTE v13[4]; // [esp+4h] [ebp-FFE8h] BYREF
  unsigned int cbData; // [esp+8h] [ebp-FFE4h] BYREF
  _WORD pvData[32750]; // [esp+Ch] [ebp-FFE0h] BYREF

  result = a2;
  cbData = 0;
  if ( a2 )
  {
    PropertyBlobValue = JetGetPropertyBlobValue(a2, a5, L"Description", pvData, 65500, &cbData, v13, 0);
    *a9 = PropertyBlobValue;
    if ( PropertyBlobValue < 0 )
    {
      v11 = 0;
    }
    else
    {
      if ( (cbData & 0xFFFFFFFE) >= 0xFFDC )
        __report_rangecheckfailure();
      v12 = cbData;
      *(_WORD *)((char *)pvData + (cbData & 0xFFFFFFFE)) = 0;
      v11 = JetSetColumn(sesid, tableid, columnid, pvData, v12, 0, 0);
    }
    *a9 = v11;
    return 0;
  }
  else
  {
    *a9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x10035cc0  mov     edi, edi
0x10035cc2  push    ebp
0x10035cc3  mov     ebp, esp
0x10035cc5  mov     eax, 0FFE8h
0x10035cca  call    __chkstk
0x10035ccf  mov     eax, ___security_cookie
0x10035cd4  xor     eax, ebp
0x10035cd6  mov     [ebp+var_4], eax
0x10035cd9  mov     eax, [ebp+arg_0]
0x10035cdc  mov     ecx, [ebp+arg_C]
0x10035cdf  mov     [ebp+cbData], 0
0x10035ce9  push    esi
0x10035cea  mov     esi, [ebp+arg_1C]
0x10035ced  test    eax, eax
0x10035cef  jnz     short loc_10035D04
0x10035cf1  mov     [esi], eax
0x10035cf3  pop     esi
0x10035cf4  mov     ecx, [ebp+var_4]
0x10035cf7  xor     ecx, ebp; StackCookie
0x10035cf9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10035cfe  mov     esp, ebp
0x10035d00  pop     ebp
0x10035d01  retn    20h ; ' '
0x10035d04  push    0
0x10035d06  lea     edx, [ebp+var_FFE8]
0x10035d0c  push    edx
0x10035d0d  lea     edx, [ebp+cbData]
0x10035d13  push    edx
0x10035d14  push    0FFDCh
0x10035d19  lea     edx, [ebp+pvData]
0x10035d1f  push    edx
0x10035d20  push    offset aDescription; "Description"
0x10035d25  push    ecx
0x10035d26  push    eax
0x10035d27  call    ds:__imp__JetGetPropertyBlobValue@32; JetGetPropertyBlobValue(x,x,x,x,x,x,x,x)
0x10035d2d  mov     [esi], eax
0x10035d2f  test    eax, eax
0x10035d31  js      short loc_10035D6A
0x10035d33  mov     ecx, [ebp+cbData]
0x10035d39  mov     eax, ecx
0x10035d3b  and     eax, 0FFFFFFFEh
0x10035d3e  cmp     eax, 0FFDCh
0x10035d43  jnb     short loc_10035D81
0x10035d45  xor     edx, edx
0x10035d47  push    edx; psetinfo
0x10035d48  push    edx; grbit
0x10035d49  push    ecx; cbData
0x10035d4a  mov     [ebp+eax+pvData], dx
0x10035d52  lea     eax, [ebp+pvData]
0x10035d58  push    eax; pvData
0x10035d59  push    [ebp+columnid]; columnid
0x10035d5c  push    [ebp+tableid]; tableid
0x10035d5f  push    [ebp+sesid]; sesid
0x10035d62  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10035d68  jmp     short loc_10035D6C
0x10035d6a  xor     eax, eax
0x10035d6c  mov     ecx, [ebp+var_4]
0x10035d6f  mov     [esi], eax
0x10035d71  xor     ecx, ebp; StackCookie
0x10035d73  xor     eax, eax
0x10035d75  pop     esi
0x10035d76  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10035d7b  mov     esp, ebp
0x10035d7d  pop     ebp
0x10035d7e  retn    20h ; ' '
0x10035d81  call    ___report_rangecheckfailure
```
