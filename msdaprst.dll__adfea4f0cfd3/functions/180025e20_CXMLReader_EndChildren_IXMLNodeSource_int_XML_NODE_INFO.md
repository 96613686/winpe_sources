# CXMLReader::EndChildren(IXMLNodeSource *,int,_XML_NODE_INFO *)

- ea: `0x180025e20`
- end: `0x18002605f`
- name: `?EndChildren@CXMLReader@@UEAAJPEAUIXMLNodeSource@@HPEAU_XML_NODE_INFO@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct IXMLNodeSource *, int, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180016584`
- `0x180025e20`
- `0x18002701c`
- `0x1800287cc`
- `0x180028f38`
- `0x180031010`

## string_xrefs

- `0x180025f13`: `delete`

## pseudocode

```c
__int64 __fastcall CXMLReader::EndChildren(
        CXMLReader *this,
        struct IXMLNodeSource *a2,
        int a3,
        struct _XML_NODE_INFO *a4)
{
  __int64 v4; // rsi
  unsigned int v5; // ebp
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx

  v4 = *((_QWORD *)a4 + 4);
  v5 = 0;
  if ( *((_DWORD *)this + 120) == 5 )
  {
    if ( v4 )
    {
      if ( *((_BYTE *)this + 400) )
        *(_DWORD *)(v4 + 24) = *((_DWORD *)this + 108);
      if ( a3 && !*((_BYTE *)this + 400) )
      {
        *(_DWORD *)(v4 + 8) = 0;
        *(_BYTE *)(v4 + 40) = 5;
      }
      v8 = *((_QWORD *)this + 58);
      if ( !v8 || v4 == v8 )
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
        if ( v9 )
          *((_QWORD *)this + 17) = v9;
        v10 = *((_QWORD *)this + 56);
        *((_BYTE *)this + 400) = 0;
        *((_QWORD *)this + 58) = 0;
        (*(void (__fastcall **)(__int64, struct IXMLNodeSource *))(*(_QWORD *)v10 + 208LL))(v10, a2);
      }
    }
    else if ( !a3
           && (*((_DWORD *)this + 119) == 1
            && (unsigned __int8)CXMLReader::IsMatch(
                                  this,
                                  *((_QWORD *)a4 + 2),
                                  *((unsigned int *)a4 + 6),
                                  *((unsigned int *)a4 + 7),
                                  &wszInsert,
                                  6,
                                  3)
            || *((_DWORD *)this + 119) == 4
            && (unsigned __int8)CXMLReader::IsMatch(
                                  this,
                                  *((_QWORD *)a4 + 2),
                                  *((unsigned int *)a4 + 6),
                                  *((unsigned int *)a4 + 7),
                                  &wszDelete,
                                  6,
                                  3)) )
    {
      *((_DWORD *)this + 119) = 8;
    }
  }
  if ( *((_DWORD *)this + 120) == 3 )
  {
    v11 = *((unsigned int *)a4 + 7);
    v12 = *((unsigned int *)a4 + 6);
    v13 = *((_QWORD *)a4 + 2);
    if ( v4 )
    {
      if ( (unsigned __int8)CXMLReader::IsMatch(this, v13, v12, v11, &wszElementType, 11, 1)
        || (unsigned __int8)CXMLReader::IsMatch(
                              this,
                              *((_QWORD *)a4 + 2),
                              *((unsigned int *)a4 + 6),
                              *((unsigned int *)a4 + 7),
                              &wszAttributeType,
                              13,
                              1) )
      {
        return (unsigned int)CXMLReader::ResolveSymbol(this, (struct CParseNode *)v4);
      }
    }
    else if ( (unsigned __int8)CXMLReader::IsMatch(this, v13, v12, v11, &wszSchema, 6, 1) )
    {
      if ( *((_BYTE *)this + 472) )
      {
        v14 = *((_QWORD *)this + 17);
        v15 = 0;
        if ( *(_DWORD *)(v14 + 16) )
          v15 = **(_QWORD **)(v14 + 8);
        if ( !(unsigned int)CXMLRowset::AllColumnsInitialized(*(CXMLRowset **)(v15 + 8)) )
        {
          v5 = -2147467259;
          Exit(-2147467259, 0x91u);
        }
      }
      v16 = *((_QWORD *)this + 56);
      *((_DWORD *)this + 120) = 4;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 208LL))(v16);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180025e20  push    rbx
0x180025e22  push    rbp
0x180025e23  push    rsi
0x180025e24  push    rdi
0x180025e25  sub     rsp, 48h
0x180025e29  mov     rsi, [r9+20h]
0x180025e2d  xor     ebp, ebp
0x180025e2f  cmp     dword ptr [rcx+1E0h], 5
0x180025e36  mov     rdi, r9
0x180025e39  mov     rbx, rcx
0x180025e3c  jnz     loc_180025F4D
0x180025e42  test    rsi, rsi
0x180025e45  jz      short loc_180025EC3
0x180025e47  cmp     [rcx+190h], bpl
0x180025e4e  jz      short loc_180025E59
0x180025e50  mov     eax, [rcx+1B0h]
0x180025e56  mov     [rsi+18h], eax
0x180025e59  test    r8d, r8d
0x180025e5c  jz      short loc_180025E6E
0x180025e5e  cmp     [rcx+190h], bpl
0x180025e65  jnz     short loc_180025E6E
0x180025e67  mov     [rsi+8], ebp
0x180025e6a  mov     byte ptr [rsi+28h], 5
0x180025e6e  mov     rax, [rcx+1D0h]
0x180025e75  test    rax, rax
0x180025e78  jz      short loc_180025E83
0x180025e7a  cmp     rsi, rax
0x180025e7d  jnz     loc_180025F4D
0x180025e83  mov     rax, [rcx+88h]
0x180025e8a  mov     rcx, [rax+30h]
0x180025e8e  test    rcx, rcx
0x180025e91  jz      short loc_180025E9A
0x180025e93  mov     [rbx+88h], rcx
0x180025e9a  mov     rcx, [rbx+1C0h]
0x180025ea1  mov     [rbx+190h], bpl
0x180025ea8  mov     [rbx+1D0h], rbp
0x180025eaf  mov     rax, [rcx]
0x180025eb2  mov     rax, [rax+0D0h]
0x180025eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ebe  jmp     loc_180025F4D
0x180025ec3  test    r8d, r8d
0x180025ec6  jnz     loc_180025F4D
0x180025ecc  cmp     dword ptr [rcx+1DCh], 1
0x180025ed3  jnz     short loc_180025F06
0x180025ed5  mov     r9d, [r9+1Ch]
0x180025ed9  lea     rax, ?wszInsert@@3PAGA; "insert"
0x180025ee0  mov     r8d, [rdi+18h]
0x180025ee4  mov     rdx, [rdi+10h]
0x180025ee8  mov     [rsp+68h+var_38], 3
0x180025ef0  mov     [rsp+68h+var_40], 6
0x180025ef8  mov     [rsp+68h+var_48], rax
0x180025efd  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025f02  test    al, al
0x180025f04  jnz     short loc_180025F43
0x180025f06  cmp     dword ptr [rbx+1DCh], 4
0x180025f0d  jnz     short loc_180025F4D
0x180025f0f  mov     r9d, [rdi+1Ch]
0x180025f13  lea     rax, ?wszDelete@@3PAGA; "delete"
0x180025f1a  mov     r8d, [rdi+18h]
0x180025f1e  mov     rcx, rbx
0x180025f21  mov     rdx, [rdi+10h]
0x180025f25  mov     [rsp+68h+var_38], 3
0x180025f2d  mov     [rsp+68h+var_40], 6
0x180025f35  mov     [rsp+68h+var_48], rax
0x180025f3a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025f3f  test    al, al
0x180025f41  jz      short loc_180025F4D
0x180025f43  mov     dword ptr [rbx+1DCh], 8
0x180025f4d  cmp     dword ptr [rbx+1E0h], 3
0x180025f54  jnz     loc_180026053
0x180025f5a  mov     r9d, [rdi+1Ch]
0x180025f5e  mov     rcx, rbx
0x180025f61  mov     r8d, [rdi+18h]
0x180025f65  mov     rdx, [rdi+10h]
0x180025f69  mov     [rsp+68h+var_38], 1
0x180025f71  test    rsi, rsi
0x180025f74  jz      short loc_180025FDA
0x180025f76  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x180025f7d  mov     [rsp+68h+var_40], 0Bh
0x180025f85  mov     [rsp+68h+var_48], rax
0x180025f8a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025f8f  test    al, al
0x180025f91  jnz     short loc_180025FCB
0x180025f93  mov     r9d, [rdi+1Ch]
0x180025f97  lea     rax, ?wszAttributeType@@3PAGA; "AttributeType"
0x180025f9e  mov     r8d, [rdi+18h]
0x180025fa2  mov     rcx, rbx
0x180025fa5  mov     rdx, [rdi+10h]
0x180025fa9  mov     [rsp+68h+var_38], 1
0x180025fb1  mov     [rsp+68h+var_40], 0Dh
0x180025fb9  mov     [rsp+68h+var_48], rax
0x180025fbe  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025fc3  test    al, al
0x180025fc5  jz      loc_180026053
0x180025fcb  mov     rdx, rsi; struct CParseNode *
0x180025fce  mov     rcx, rbx; this
0x180025fd1  call    ?ResolveSymbol@CXMLReader@@AEAAJPEAVCParseNode@@@Z; CXMLReader::ResolveSymbol(CParseNode *)
0x180025fd6  mov     ebp, eax
0x180025fd8  jmp     short loc_180026053
0x180025fda  lea     rax, ?wszSchema@@3PAGA; "Schema"
0x180025fe1  mov     [rsp+68h+var_40], 6
0x180025fe9  mov     [rsp+68h+var_48], rax
0x180025fee  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025ff3  test    al, al
0x180025ff5  jz      short loc_180026053
0x180025ff7  cmp     [rbx+1D8h], bpl
0x180025ffe  jz      short loc_180026033
0x180026000  mov     rax, [rbx+88h]
0x180026007  xor     ecx, ecx
0x180026009  cmp     [rax+10h], ecx
0x18002600c  jbe     short loc_180026015
0x18002600e  mov     rax, [rax+8]
0x180026012  mov     rcx, [rax]
0x180026015  mov     rcx, [rcx+8]; this
0x180026019  call    ?AllColumnsInitialized@CXMLRowset@@QEAAHXZ; CXMLRowset::AllColumnsInitialized(void)
0x18002601e  test    eax, eax
0x180026020  jnz     short loc_180026033
0x180026022  mov     ebp, 80004005h
0x180026027  mov     edx, 91h; unsigned int
0x18002602c  mov     ecx, ebp; int
0x18002602e  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180026033  mov     rcx, [rbx+1C0h]
0x18002603a  mov     dword ptr [rbx+1E0h], 4
0x180026044  mov     rax, [rcx]
0x180026047  mov     rax, [rax+0D0h]
0x18002604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026053  mov     eax, ebp
0x180026055  add     rsp, 48h
0x180026059  pop     rdi
0x18002605a  pop     rsi
0x18002605b  pop     rbp
0x18002605c  pop     rbx
0x18002605d  retn
```
