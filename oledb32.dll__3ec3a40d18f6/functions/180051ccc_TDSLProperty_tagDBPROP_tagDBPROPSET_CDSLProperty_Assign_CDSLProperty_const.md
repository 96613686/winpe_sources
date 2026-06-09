# TDSLProperty<tagDBPROP,tagDBPROPSET,CDSLProperty>::Assign(CDSLProperty const &)

- ea: `0x180051ccc`
- end: `0x180051e6b`
- name: `?Assign@?$TDSLProperty@UtagDBPROP@@UtagDBPROPSET@@VCDSLProperty@@@@QEAAJAEBVCDSLProperty@@@Z`
- size: `415`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a448`
- `0x18002798c`
- `0x180027cf4`
- `0x180052348`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x180051ccc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180051d10`
- `OLEAUT32!__imp_VariantClear` at `0x180051d10`
- `OLEAUT32!__imp_VariantCopy` at `0x180051da1`
- `OLEAUT32!__imp_VariantCopy` at `0x180051da1`

## pseudocode

```c
__int64 __fastcall TDSLProperty<tagDBPROP,tagDBPROPSET,CDSLProperty>::Assign(char *a1, __int64 a2)
{
  VARIANTARG *v3; // rbx
  HRESULT v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // edi
  unsigned int v8; // ebx
  unsigned int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-14h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-10h] BYREF
  int v13; // [rsp+48h] [rbp+10h]

  *(_DWORD *)a1 = *(_DWORD *)a2;
  *((_DWORD *)a1 + 1) = *(_DWORD *)(a2 + 4);
  *((_DWORD *)a1 + 2) = *(_DWORD *)(a2 + 8);
  *(DBID *)(a1 + 16) = DB_NULLID;
  v3 = (VARIANTARG *)(a1 + 48);
  v4 = VariantClear((VARIANTARG *)a1 + 2);
  try
  {
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(
          v4,
          L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|OLEDB|ERR> ",
          0x8Du);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(
            v5,
            L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|OLEDB|ERR> ",
            0x8Du);
          if ( (bidGblFlags & 2) != 0 )
            v5 = bidTraceHR(
                   off_1800C83E0[0],
                   144393,
                   L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|Trace|HR> ",
                   v5);
        }
      }
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    v6 = VariantCopy(v3, (const VARIANTARG *)(a2 + 48));
    v13 = v6;
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(
          v6,
          L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|OLEDB|ERR> ",
          0x8Fu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(
            v6,
            L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|OLEDB|ERR> ",
            0x8Fu);
          if ( (bidGblFlags & 2) != 0 )
            v6 = bidTraceHR(
                   off_1800C83E0[0],
                   146441,
                   L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|Trace|HR> ",
                   v6);
        }
      }
      v10 = v6;
      throw (long *)&v10;
    }
  }
  catch ( long v11 )
  {
    if ( (bidGblFlags & 2) != 0
      && (OLEDBTraceErr(
            v13,
            L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|OLEDB|ERR> ",
            0x93u),
          (bidGblFlags & 2) != 0)
      && off_1800C8870[0] )
    {
      v8 = v11;
      bidTraceA(off_1800C83E0[0], 151552, off_1800C8870[0], v11);
    }
    else
    {
      v8 = v11;
    }
    VariantClear((VARIANTARG *)a1 + 2);
    memset_0(a1, 0, 0x48u);
    v6 = v8;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C83E0[0],
                           165897,
                           L"<TDSLProperty<struct tagDBPROP,struct tagDBPROPSET,class CDSLProperty>::Assign|Trace|HR> ",
                           v6);
  return v6;
}

```

## disassembly

```asm
0x180051ccc  mov     [rsp+arg_10], rbx
0x180051cd1  mov     [rsp+arg_18], rsi
0x180051cd6  mov     [rsp+arg_0], rcx
0x180051cdb  push    rdi
0x180051cdc  sub     rsp, 30h
0x180051ce0  mov     rsi, rdx
0x180051ce3  mov     eax, [rdx]
0x180051ce5  mov     [rcx], eax
0x180051ce7  mov     eax, [rdx+4]
0x180051cea  mov     [rcx+4], eax
0x180051ced  mov     eax, [rdx+8]
0x180051cf0  mov     [rcx+8], eax
0x180051cf3  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180051cfa  movups  xmmword ptr [rcx+10h], xmm0
0x180051cfe  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180051d05  movups  xmmword ptr [rcx+20h], xmm1
0x180051d09  lea     rbx, [rcx+30h]
0x180051d0d  mov     rcx, rbx; pvarg
0x180051d10  call    cs:__imp_VariantClear
0x180051d16  mov     edi, eax
0x180051d18  mov     [rsp+38h+arg_8], eax
0x180051d1c  test    eax, eax
0x180051d1e  jns     short loc_180051D9A
0x180051d20  mov     eax, cs:_bidGblFlags
0x180051d26  mov     bl, 2
0x180051d28  test    bl, al
0x180051d2a  jz      short loc_180051D85
0x180051d2c  mov     r8d, 8Dh; unsigned int
0x180051d32  lea     rdx, aTdslpropertySt; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051d39  mov     ecx, edi; int
0x180051d3b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051d40  mov     eax, cs:_bidGblFlags
0x180051d46  test    bl, al
0x180051d48  jz      short loc_180051D85
0x180051d4a  mov     r8d, 8Dh; unsigned int
0x180051d50  lea     rdx, aTdslpropertySt; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051d57  mov     ecx, edi; int
0x180051d59  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051d5e  mov     eax, cs:_bidGblFlags
0x180051d64  test    bl, al
0x180051d66  jz      short loc_180051D85
0x180051d68  mov     r9d, edi
0x180051d6b  lea     r8, aTdslpropertySt_0; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051d72  mov     edx, 23409h
0x180051d77  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180051d7e  call    _bidTraceHR
0x180051d83  mov     edi, eax
0x180051d85  mov     [rsp+38h+pExceptionObject], edi
0x180051d89  lea     rdx, _TI1J; pThrowInfo
0x180051d90  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180051d95  call    _CxxThrowException_0
0x180051d9a  lea     rdx, [rsi+30h]; pvargSrc
0x180051d9e  mov     rcx, rbx; pvargDest
0x180051da1  call    cs:__imp_VariantCopy
0x180051da7  mov     edi, eax
0x180051da9  mov     [rsp+38h+arg_8], eax
0x180051dad  test    eax, eax
0x180051daf  jns     short loc_180051E2C
0x180051db1  mov     eax, cs:_bidGblFlags
0x180051db7  mov     bl, 2
0x180051db9  test    bl, al
0x180051dbb  jz      short loc_180051E16
0x180051dbd  mov     r8d, 8Fh; unsigned int
0x180051dc3  lea     rdx, aTdslpropertySt; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051dca  mov     ecx, edi; int
0x180051dcc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051dd1  mov     eax, cs:_bidGblFlags
0x180051dd7  test    bl, al
0x180051dd9  jz      short loc_180051E16
0x180051ddb  mov     r8d, 8Fh; unsigned int
0x180051de1  lea     rdx, aTdslpropertySt; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051de8  mov     ecx, edi; int
0x180051dea  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180051def  mov     eax, cs:_bidGblFlags
0x180051df5  test    bl, al
0x180051df7  jz      short loc_180051E16
0x180051df9  mov     r9d, edi
0x180051dfc  lea     r8, aTdslpropertySt_0; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051e03  mov     edx, 23C09h
0x180051e08  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180051e0f  call    _bidTraceHR
0x180051e14  mov     edi, eax
0x180051e16  mov     [rsp+38h+var_14], edi
0x180051e1a  lea     rdx, _TI1J; pThrowInfo
0x180051e21  lea     rcx, [rsp+38h+var_14]; pExceptionObject
0x180051e26  call    _CxxThrowException_0
0x180051e2c  jmp     short loc_180051E32
0x180051e2e  mov     edi, [rsp+38h+arg_8]
0x180051e32  mov     bl, 2
0x180051e34  test    byte ptr cs:_bidGblFlags, bl
0x180051e3a  jz      short loc_180051E59
0x180051e3c  mov     r9d, edi
0x180051e3f  lea     r8, aTdslpropertySt_0; "<TDSLProperty<struct tagDBPROP,struct t"...
0x180051e46  mov     edx, 28809h
0x180051e4b  mov     rcx, cs:off_1800C83E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180051e52  call    _bidTraceHR
0x180051e57  mov     edi, eax
0x180051e59  mov     eax, edi
0x180051e5b  mov     rbx, [rsp+38h+arg_10]
0x180051e60  mov     rsi, [rsp+38h+arg_18]
0x180051e65  add     rsp, 30h
0x180051e69  pop     rdi
0x180051e6a  retn
```
