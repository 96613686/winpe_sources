# CXMLReader::ProcessNamespaceDcl(_XML_NODE_INFO * *,ulong)

- ea: `0x180027d24`
- end: `0x180028140`
- name: `?ProcessNamespaceDcl@CXMLReader@@AEAAJPEAPEAU_XML_NODE_INFO@@K@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct _XML_NODE_INFO **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024eb0`

## callees

- `0x180019008`
- `0x18001b008`
- `0x180024200`
- `0x180027d24`
- `0x180029528`
- `0x1800295ac`
- `0x18002dca4`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180027d80`
- `msvcrt!_wcsnicmp` at `0x180027dc1`
- `msvcrt!_wcsnicmp` at `0x180027de4`
- `msvcrt!_wcsnicmp` at `0x180027e07`
- `msvcrt!_wcsnicmp` at `0x180027fc9`
- `msvcrt!_wcsnicmp` at `0x180027fe8`
- `msvcrt!_wcsnicmp` at `0x180028007`
- `msvcrt!_wcsnicmp` at `0x180027d80`
- `msvcrt!_wcsnicmp` at `0x180027dc1`
- `msvcrt!_wcsnicmp` at `0x180027de4`
- `msvcrt!_wcsnicmp` at `0x180027e07`
- `msvcrt!_wcsnicmp` at `0x180027fc9`
- `msvcrt!_wcsnicmp` at `0x180027fe8`
- `msvcrt!_wcsnicmp` at `0x180028007`

## string_xrefs

- `0x180027d75`: `xmlns:`
- `0x180027dd9`: `urn:schemas-microsoft-com:xml-data`
- `0x180027fdd`: `urn:schemas-microsoft-com:datatypes`
- `0x180027dfc`: `urn:schemas-microsoft-com:rowset`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessNamespaceDcl(CXMLReader *this, struct _XML_NODE_INFO **a2, unsigned int a3)
{
  unsigned int v3; // eax
  struct _XML_NODE_INFO **v4; // rbx
  unsigned int v6; // r12d
  __int64 v7; // r13
  struct _XML_NODE_INFO *v8; // rdi
  struct _XML_NODE_INFO *v9; // rbx
  unsigned int v10; // esi
  unsigned __int16 *v11; // r14
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // ebx
  unsigned int v20; // edi
  ATL::CComBSTR *v21; // rbx
  int v22; // r8d
  const unsigned __int16 *v23; // rdx
  CCollectionList *v24; // rcx
  int appended; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  unsigned int v30; // [rsp+30h] [rbp-38h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 0;
  LODWORD(v7) = 1;
  while ( (unsigned int)v7 < v3 )
  {
    try
    {
      v8 = v4[(unsigned int)v7];
      if ( *((_DWORD *)v8 + 1) == 2 && !_wcsnicmp(*((const wchar_t **)v8 + 2), L"xmlns:", 6u) )
      {
        v7 = (unsigned int)(v7 + 1);
        v9 = v4[v7];
        v10 = ~*((_DWORD *)v8 + 7) + *((_DWORD *)v8 + 6);
        v11 = (unsigned __int16 *)(*((_QWORD *)v8 + 2) + 2 * (*((unsigned int *)v8 + 7) + 1LL));
        if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_xmldata, *((unsigned int *)v9 + 6))
          && _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_Friendly_xmldata, *((unsigned int *)v9 + 6)) )
        {
          if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_oledb, *((unsigned int *)v9 + 6)) )
          {
            if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_dt, *((unsigned int *)v9 + 6))
              && _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_Friendly_dt, *((unsigned int *)v9 + 6)) )
            {
              if ( !_wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_schema, *((unsigned int *)v9 + 6)) )
              {
                v20 = 4;
                v21 = (CXMLReader *)((char *)this + 152);
                ATL::CComBSTR::Append((CXMLReader *)((char *)this + 152), v11, v10);
                v22 = 1;
                v23 = L":";
                goto LABEL_34;
              }
              v20 = 5;
            }
            else
            {
              v20 = 2;
            }
          }
          else
          {
            v12 = CXMLReader::AddReservedSymbol(this, v11, v10, 4);
            v13 = v12;
            if ( v12 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_180049D60[0] )
                  bidTraceW(off_180049208[0], 600064, off_180049D60[0], (unsigned int)v12, 586);
              }
              ThrowHR(v13);
            }
            v14 = CXMLReader::AddReservedSymbol(this, v11, v10, 7);
            v15 = v14;
            if ( v14 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049D58[0] )
                bidTraceW(off_180049208[0], 601088, off_180049D58[0], (unsigned int)v14, 587);
              ThrowHR(v15);
            }
            v16 = CXMLReader::AddReservedSymbol(this, v11, v10, 6);
            v17 = v16;
            if ( v16 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049D50[0] )
                bidTraceW(off_180049208[0], 602112, off_180049D50[0], (unsigned int)v16, 588);
              ThrowHR(v17);
            }
            v18 = CXMLReader::AddReservedSymbol(this, v11, v10, 5);
            v19 = v18;
            if ( v18 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049D48[0] )
                bidTraceW(off_180049208[0], 603136, off_180049D48[0], (unsigned int)v18, 589);
              ThrowHR(v19);
            }
            v20 = 3;
            v21 = (CXMLReader *)((char *)this + 144);
            ATL::CComBSTR::Append((CXMLReader *)((char *)this + 144), v11, v10);
            ATL::CComBSTR::Append((CXMLReader *)((char *)this + 144), L":", 1);
            v22 = 4;
            v23 = (const unsigned __int16 *)&wszData;
LABEL_34:
            ATL::CComBSTR::Append(v21, v23, v22);
          }
        }
        else
        {
          v20 = 1;
        }
        v24 = (CXMLReader *)((char *)this + 160);
        if ( v20 == 5 )
        {
          appended = CCollectionList::AppendDup(v24, v11, v10, 5u);
          v26 = appended;
          if ( appended < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049D40[0] )
              bidTraceW(off_180049208[0], 628736, off_180049D40[0], (unsigned int)appended, 614);
            ThrowHR(v26);
          }
        }
        else
        {
          v27 = CCollectionList::Append(v24, v11, v10, v20);
          v28 = v27;
          if ( v27 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049D38[0] )
              bidTraceW(off_180049208[0], 632832, off_180049D38[0], (unsigned int)v27, 618);
            ThrowHR(v28);
          }
        }
        v4 = a2;
      }
      LODWORD(v7) = v7 + 1;
      v3 = a3;
    }
    catch ( long v30 )
    {
      return v30;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180027d24  mov     rax, rsp
0x180027d27  mov     [rax+8], rbx
0x180027d2b  mov     [rax+20h], rsi
0x180027d2f  mov     [rax+18h], r8d
0x180027d33  mov     [rax+10h], rdx
0x180027d37  push    rdi
0x180027d38  push    r12
0x180027d3a  push    r13
0x180027d3c  push    r14
0x180027d3e  push    r15
0x180027d40  sub     rsp, 40h
0x180027d44  mov     eax, r8d
0x180027d47  mov     rbx, rdx
0x180027d4a  mov     r15, rcx
0x180027d4d  xor     r12d, r12d
0x180027d50  lea     r13d, [r12+1]
0x180027d55  cmp     r13d, eax
0x180027d58  jnb     loc_180028118
0x180027d5e  mov     eax, r13d
0x180027d61  mov     rdi, [rbx+rax*8]
0x180027d65  cmp     dword ptr [rdi+4], 2
0x180027d69  jnz     loc_180028109
0x180027d6f  mov     r8d, 6; MaxCount
0x180027d75  lea     rdx, aXmlns; "xmlns:"
0x180027d7c  mov     rcx, [rdi+10h]; String1
0x180027d80  call    cs:__imp__wcsnicmp
0x180027d87  nop     dword ptr [rax+rax+00h]
0x180027d8c  test    eax, eax
0x180027d8e  jnz     loc_180028109
0x180027d94  inc     r13d
0x180027d97  mov     rbx, [rbx+r13*8]
0x180027d9b  mov     edx, [rdi+1Ch]
0x180027d9e  mov     ecx, edx
0x180027da0  not     ecx
0x180027da2  mov     esi, [rdi+18h]
0x180027da5  add     esi, ecx
0x180027da7  mov     rax, [rdi+10h]
0x180027dab  inc     rdx
0x180027dae  lea     r14, [rax+rdx*2]
0x180027db2  mov     r8d, [rbx+18h]; MaxCount
0x180027db6  lea     rdx, ?wsznsDef_xmldata@@3PAGA; "uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C148"...
0x180027dbd  mov     rcx, [rbx+10h]; String1
0x180027dc1  call    cs:__imp__wcsnicmp
0x180027dc8  nop     dword ptr [rax+rax+00h]
0x180027dcd  test    eax, eax
0x180027dcf  jz      loc_180028052
0x180027dd5  mov     r8d, [rbx+18h]; MaxCount
0x180027dd9  lea     rdx, ?wsznsDef_Friendly_xmldata@@3PAGA; "urn:schemas-microsoft-com:xml-data"
0x180027de0  mov     rcx, [rbx+10h]; String1
0x180027de4  call    cs:__imp__wcsnicmp
0x180027deb  nop     dword ptr [rax+rax+00h]
0x180027df0  test    eax, eax
0x180027df2  jz      loc_180028052
0x180027df8  mov     r8d, [rbx+18h]; MaxCount
0x180027dfc  lea     rdx, ?wsznsDef_oledb@@3PAGA; "urn:schemas-microsoft-com:rowset"
0x180027e03  mov     rcx, [rbx+10h]; String1
0x180027e07  call    cs:__imp__wcsnicmp
0x180027e0e  nop     dword ptr [rax+rax+00h]
0x180027e13  test    eax, eax
0x180027e15  jnz     loc_180027FBA
0x180027e1b  lea     r9d, [rax+4]
0x180027e1f  mov     r8d, esi
0x180027e22  mov     rdx, r14
0x180027e25  mov     rcx, r15
0x180027e28  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180027e2d  mov     ebx, eax
0x180027e2f  test    eax, eax
0x180027e31  jns     short loc_180027E72
0x180027e33  test    byte ptr cs:_bidGblFlags, 2
0x180027e3a  jz      short loc_180027E6B
0x180027e3c  mov     rcx, cs:off_180049D60; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027e43  test    rcx, rcx
0x180027e46  jz      short loc_180027E6B
0x180027e48  mov     [rsp+68h+var_48], 24Ah
0x180027e50  mov     r9d, eax
0x180027e53  mov     r8, cs:off_180049D60; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027e5a  mov     edx, 92800h
0x180027e5f  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027e66  call    _bidTraceW
0x180027e6b  mov     ecx, ebx; int
0x180027e6d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027e72  mov     r9d, 7
0x180027e78  mov     r8d, esi
0x180027e7b  mov     rdx, r14
0x180027e7e  mov     rcx, r15
0x180027e81  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180027e86  mov     ebx, eax
0x180027e88  test    eax, eax
0x180027e8a  jns     short loc_180027ECB
0x180027e8c  test    byte ptr cs:_bidGblFlags, 2
0x180027e93  jz      short loc_180027EC4
0x180027e95  mov     rcx, cs:off_180049D58; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027e9c  test    rcx, rcx
0x180027e9f  jz      short loc_180027EC4
0x180027ea1  mov     [rsp+68h+var_48], 24Bh
0x180027ea9  mov     r9d, eax
0x180027eac  mov     r8, cs:off_180049D58; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027eb3  mov     edx, 92C00h
0x180027eb8  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027ebf  call    _bidTraceW
0x180027ec4  mov     ecx, ebx; int
0x180027ec6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027ecb  mov     r9d, 6
0x180027ed1  mov     r8d, esi
0x180027ed4  mov     rdx, r14
0x180027ed7  mov     rcx, r15
0x180027eda  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180027edf  mov     ebx, eax
0x180027ee1  test    eax, eax
0x180027ee3  jns     short loc_180027F24
0x180027ee5  test    byte ptr cs:_bidGblFlags, 2
0x180027eec  jz      short loc_180027F1D
0x180027eee  mov     rcx, cs:off_180049D50; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027ef5  test    rcx, rcx
0x180027ef8  jz      short loc_180027F1D
0x180027efa  mov     [rsp+68h+var_48], 24Ch
0x180027f02  mov     r9d, eax
0x180027f05  mov     r8, cs:off_180049D50; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027f0c  mov     edx, 93000h
0x180027f11  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027f18  call    _bidTraceW
0x180027f1d  mov     ecx, ebx; int
0x180027f1f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027f24  mov     r9d, 5
0x180027f2a  mov     r8d, esi
0x180027f2d  mov     rdx, r14
0x180027f30  mov     rcx, r15
0x180027f33  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180027f38  mov     ebx, eax
0x180027f3a  test    eax, eax
0x180027f3c  jns     short loc_180027F7D
0x180027f3e  test    byte ptr cs:_bidGblFlags, 2
0x180027f45  jz      short loc_180027F76
0x180027f47  mov     rcx, cs:off_180049D48; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027f4e  test    rcx, rcx
0x180027f51  jz      short loc_180027F76
0x180027f53  mov     [rsp+68h+var_48], 24Dh
0x180027f5b  mov     r9d, eax
0x180027f5e  mov     r8, cs:off_180049D48; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027f65  mov     edx, 93400h
0x180027f6a  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027f71  call    _bidTraceW
0x180027f76  mov     ecx, ebx; int
0x180027f78  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027f7d  mov     edi, 3
0x180027f82  lea     rbx, [r15+90h]
0x180027f89  mov     r8d, esi; int
0x180027f8c  mov     rdx, r14; unsigned __int16 *
0x180027f8f  mov     rcx, rbx; this
0x180027f92  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180027f97  lea     r8d, [rdi-2]; int
0x180027f9b  lea     rdx, asc_18003A3A4; ":"
0x180027fa2  mov     rcx, rbx; this
0x180027fa5  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180027faa  lea     r8d, [rdi+1]
0x180027fae  lea     rdx, ?wszData@@3PAGA; "data"
0x180027fb5  jmp     loc_18002803A
0x180027fba  mov     r8d, [rbx+18h]; MaxCount
0x180027fbe  lea     rdx, ?wsznsDef_dt@@3PAGA; "uuid:C2F41010-65B3-11d1-A29F-00AA00C148"...
0x180027fc5  mov     rcx, [rbx+10h]; String1
0x180027fc9  call    cs:__imp__wcsnicmp
0x180027fd0  nop     dword ptr [rax+rax+00h]
0x180027fd5  test    eax, eax
0x180027fd7  jz      short loc_18002804B
0x180027fd9  mov     r8d, [rbx+18h]; MaxCount
0x180027fdd  lea     rdx, ?wsznsDef_Friendly_dt@@3PAGA; "urn:schemas-microsoft-com:datatypes"
0x180027fe4  mov     rcx, [rbx+10h]; String1
0x180027fe8  call    cs:__imp__wcsnicmp
0x180027fef  nop     dword ptr [rax+rax+00h]
0x180027ff4  test    eax, eax
0x180027ff6  jz      short loc_18002804B
0x180027ff8  mov     r8d, [rbx+18h]; MaxCount
0x180027ffc  lea     rdx, ?wsznsDef_schema@@3PAGA; "#RowsetSchema"
0x180028003  mov     rcx, [rbx+10h]; String1
0x180028007  call    cs:__imp__wcsnicmp
0x18002800e  nop     dword ptr [rax+rax+00h]
0x180028013  test    eax, eax
0x180028015  jnz     short loc_180028044
0x180028017  lea     edi, [rax+4]
0x18002801a  lea     rbx, [r15+98h]
0x180028021  mov     r8d, esi; int
0x180028024  mov     rdx, r14; unsigned __int16 *
0x180028027  mov     rcx, rbx; this
0x18002802a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002802f  lea     r8d, [rdi-3]; int
0x180028033  lea     rdx, asc_18003A3A4; ":"
0x18002803a  mov     rcx, rbx; this
0x18002803d  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180028042  jmp     short loc_180028057
0x180028044  mov     edi, 5
0x180028049  jmp     short loc_180028057
0x18002804b  mov     edi, 2
0x180028050  jmp     short loc_180028057
0x180028052  mov     edi, 1
0x180028057  lea     rcx, [r15+0A0h]; this
0x18002805e  mov     r9d, edi; unsigned __int64
0x180028061  mov     r8d, esi; unsigned int
0x180028064  mov     rdx, r14; unsigned __int16 *
0x180028067  cmp     edi, 5
0x18002806a  jnz     short loc_1800280BA
0x18002806c  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x180028071  mov     ebx, eax
0x180028073  test    eax, eax
0x180028075  jns     loc_180028104
0x18002807b  test    byte ptr cs:_bidGblFlags, 2
0x180028082  jz      short loc_1800280B3
0x180028084  mov     rcx, cs:off_180049D40; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x18002808b  test    rcx, rcx
0x18002808e  jz      short loc_1800280B3
0x180028090  mov     [rsp+68h+var_48], 266h
0x180028098  mov     r9d, eax
0x18002809b  mov     r8, cs:off_180049D40; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x1800280a2  mov     edx, 99800h
0x1800280a7  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800280ae  call    _bidTraceW
0x1800280b3  mov     ecx, ebx; int
0x1800280b5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800280ba  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x1800280bf  mov     ebx, eax
0x1800280c1  test    eax, eax
0x1800280c3  jns     short loc_180028104
0x1800280c5  test    byte ptr cs:_bidGblFlags, 2
0x1800280cc  jz      short loc_1800280FD
0x1800280ce  mov     rcx, cs:off_180049D38; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x1800280d5  test    rcx, rcx
0x1800280d8  jz      short loc_1800280FD
0x1800280da  mov     [rsp+68h+var_48], 26Ah
0x1800280e2  mov     r9d, eax
0x1800280e5  mov     r8, cs:off_180049D38; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x1800280ec  mov     edx, 9A800h
0x1800280f1  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800280f8  call    _bidTraceW
0x1800280fd  mov     ecx, ebx; int
0x1800280ff  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180028104  mov     rbx, [rsp+68h+arg_8]
0x180028109  inc     r13d
0x18002810c  mov     eax, [rsp+68h+arg_10]
0x180028113  jmp     loc_180027D55
0x180028118  jmp     short loc_180028122
0x18002811a  mov     r12d, [rsp+68h+arg_10]
0x180028122  mov     eax, r12d
0x180028125  lea     r11, [rsp+68h+var_28]
0x18002812a  mov     rbx, [r11+30h]
0x18002812e  mov     rsi, [r11+48h]
0x180028132  mov     rsp, r11
0x180028135  pop     r15
0x180028137  pop     r14
0x180028139  pop     r13
0x18002813b  pop     r12
0x18002813d  pop     rdi
0x18002813e  retn
```
