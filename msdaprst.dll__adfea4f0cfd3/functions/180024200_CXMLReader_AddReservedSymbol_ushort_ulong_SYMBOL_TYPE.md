# CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)

- ea: `0x180024200`
- end: `0x18002432c`
- name: `?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027d24`

## callees

- `0x180019008`
- `0x18001b008`
- `0x180024200`
- `0x180024334`
- `0x18002dca4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180024305`
- `OLEAUT32!__imp_SysFreeString` at `0x180024305`
- `OLEAUT32!__imp_SysStringLen` at `0x180024291`
- `OLEAUT32!__imp_SysStringLen` at `0x180024291`

## string_xrefs

- `0x180024275`: `update`
- `0x18002426c`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::AddReservedSymbol(__int64 a1, const unsigned __int16 *a2, int a3, int a4)
{
  unsigned int v6; // esi
  int v7; // r8d
  unsigned __int16 near **v8; // rdx
  UINT v9; // eax
  int v10; // edi
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h] BYREF
  struct CSymbol *v15; // [rsp+38h] [rbp-10h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+20h]

  v6 = 0;
  pbstr = 0;
  v15 = 0;
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, a2, a3);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, L":", 1);
  switch ( a4 )
  {
    case 4:
      v8 = (unsigned __int16 near **)wszUpdate;
      goto LABEL_9;
    case 5:
      v8 = &wszDelete;
      goto LABEL_9;
    case 6:
      v8 = &wszInsert;
LABEL_9:
      v7 = 6;
      goto LABEL_10;
  }
  if ( a4 != 7 )
    goto LABEL_11;
  v7 = 8;
  v8 = &wszOriginal;
LABEL_10:
  ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, (const unsigned __int16 *)v8, v7);
LABEL_11:
  v9 = SysStringLen(pbstr);
  v10 = CScope::AddSymbol((CScope *)(a1 + 80), pbstr, v9, &v15);
  if ( v10 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049C90[0] )
      bidTraceW(off_180049208[0], 2927616, off_180049C90[0], (unsigned int)v10, 2859);
    try
    {
      ThrowHR(v10);
    }
    catch ( long v14 )
    {
      v12 = &v13;
      *((_DWORD *)v12 + 26) = *((_DWORD *)v12 + 12);
      return v17;
    }
  }
  *(_DWORD *)v15 = a4;
  SysFreeString(pbstr);
  return v6;
}

```

## disassembly

```asm
0x180024200  mov     rax, rsp
0x180024203  mov     [rax+10h], rsi
0x180024207  mov     [rax+18h], rdi
0x18002420b  push    r14
0x18002420d  sub     rsp, 40h
0x180024211  mov     r14d, r9d
0x180024214  mov     rdi, rcx
0x180024217  xor     esi, esi
0x180024219  mov     [rax+8], rsi
0x18002421d  mov     [rax-10h], rsi
0x180024221  lea     rcx, [rax+8]; this
0x180024225  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002422a  lea     r8d, [rsi+1]; int
0x18002422e  lea     rdx, asc_18003A3A4; ":"
0x180024235  lea     rcx, [rsp+48h+pbstr]; this
0x18002423a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002423f  mov     ecx, r14d
0x180024242  sub     ecx, 4
0x180024245  jz      short loc_180024275
0x180024247  sub     ecx, 1
0x18002424a  jz      short loc_18002426C
0x18002424c  sub     ecx, 1
0x18002424f  jz      short loc_180024263
0x180024251  cmp     ecx, 1
0x180024254  jnz     short loc_18002428C
0x180024256  lea     r8d, [rsi+8]
0x18002425a  lea     rdx, ?wszOriginal@@3PAGA; "original"
0x180024261  jmp     short loc_180024282
0x180024263  lea     rdx, ?wszInsert@@3PAGA; "insert"
0x18002426a  jmp     short loc_18002427C
0x18002426c  lea     rdx, ?wszDelete@@3PAGA; "delete"
0x180024273  jmp     short loc_18002427C
0x180024275  lea     rdx, ?wszUpdate@@3PAGA; "update"
0x18002427c  mov     r8d, 6; int
0x180024282  lea     rcx, [rsp+48h+pbstr]; this
0x180024287  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002428c  mov     rcx, [rsp+48h+pbstr]; pbstr
0x180024291  call    cs:__imp_SysStringLen
0x180024298  nop     dword ptr [rax+rax+00h]
0x18002429d  lea     rcx, [rdi+50h]; this
0x1800242a1  lea     r9, [rsp+48h+var_10]; struct CSymbol **
0x1800242a6  mov     r8d, eax; unsigned int
0x1800242a9  mov     rdx, [rsp+48h+pbstr]; unsigned __int16 *
0x1800242ae  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x1800242b3  mov     edi, eax
0x1800242b5  test    eax, eax
0x1800242b7  jns     short loc_1800242F8
0x1800242b9  test    byte ptr cs:_bidGblFlags, 2
0x1800242c0  jz      short loc_1800242F1
0x1800242c2  mov     rax, cs:off_180049C90; "<CXMLReader::AddReservedSymbol|ADO|ERR>"...
0x1800242c9  test    rax, rax
0x1800242cc  jz      short loc_1800242F1
0x1800242ce  mov     [rsp+48h+var_28], 0B2Bh
0x1800242d6  mov     r9d, edi
0x1800242d9  mov     r8, cs:off_180049C90; "<CXMLReader::AddReservedSymbol|ADO|ERR>"...
0x1800242e0  mov     edx, 2CAC00h
0x1800242e5  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800242ec  call    _bidTraceW
0x1800242f1  mov     ecx, edi; int
0x1800242f3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800242f8  mov     rax, [rsp+48h+var_10]
0x1800242fd  mov     [rax], r14d
0x180024300  mov     rcx, [rsp+48h+pbstr]; bstrString
0x180024305  call    cs:__imp_SysFreeString
0x18002430c  nop     dword ptr [rax+rax+00h]
0x180024311  nop
0x180024312  jmp     short loc_180024318
0x180024314  mov     esi, [rsp+48h+arg_18]
0x180024318  mov     eax, esi
0x18002431a  mov     rsi, [rsp+48h+arg_8]
0x18002431f  mov     rdi, [rsp+48h+arg_10]
0x180024324  add     rsp, 40h
0x180024328  pop     r14
0x18002432a  retn
```
