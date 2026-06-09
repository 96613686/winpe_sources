# CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)

- ea: `0x180026dc0`
- end: `0x180027015`
- name: `?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z`
- size: `597`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800257ec`
- `0x180026dc0`

## callees

- `0x180016584`
- `0x180019008`
- `0x18001b008`
- `0x180020bec`
- `0x1800210a4`
- `0x180026dc0`
- `0x180029528`
- `0x180029748`
- `0x180029770`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180026f87`
- `OLEAUT32!__imp_SysFreeString` at `0x180026f87`
- `OLEAUT32!__imp_SysStringLen` at `0x180026e9b`
- `OLEAUT32!__imp_SysStringLen` at `0x180026f3d`
- `OLEAUT32!__imp_SysStringLen` at `0x180026e9b`
- `OLEAUT32!__imp_SysStringLen` at `0x180026f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::InitRowsets(__int64 a1, __int64 a2, struct IUnknown *a3, CRowset **a4)
{
  CRowset **v4; // r15
  int v7; // ebx
  unsigned int v8; // r12d
  unsigned __int64 v9; // rdi
  unsigned int i; // esi
  CRowset *v11; // rbp
  const unsigned __int16 *v12; // rbx
  unsigned int v13; // edx
  _QWORD *v14; // rcx
  UINT v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  unsigned __int16 *v18; // rbx
  UINT v19; // eax
  __int64 v20; // rdx
  BSTR pbstr; // [rsp+78h] [rbp+10h] BYREF
  struct IUnknown *v23; // [rsp+80h] [rbp+18h]
  CRowset **v24; // [rsp+88h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  v4 = a4;
  v7 = 0;
  v8 = *(_DWORD *)(a2 + 16);
  v9 = 0;
  for ( i = 0; i < v8; ++i )
  {
    if ( i < *(_DWORD *)(a2 + 16) )
    {
      v9 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL * i);
      v7 = 0;
    }
    else
    {
      v7 = 1;
    }
    if ( *(_DWORD *)v9 == 1 )
    {
      v11 = *(CRowset **)(v9 + 8);
      if ( *v4 )
      {
        *((_QWORD *)v11 + 75) = a1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 8LL))(*(_QWORD *)(a1 + 448));
      }
      else
      {
        if ( v8 != 1 )
        {
          v7 = Exit(-2147467259, 0x91u);
          if ( v7 < 0 )
            return (unsigned int)v7;
        }
        v12 = 0;
        pbstr = 0;
        if ( *(_DWORD *)(a2 + 24) )
        {
          v13 = 0;
          do
          {
            v14 = *(_QWORD **)(*(_QWORD *)(a2 + 32) + 8LL * v13);
            if ( v14 )
            {
              while ( v14 )
              {
                if ( v14[2] == v9 )
                {
                  v12 = (const unsigned __int16 *)v14[1];
                  goto LABEL_17;
                }
                v14 = (_QWORD *)v14[3];
              }
            }
            ++v13;
          }
          while ( v13 < *(_DWORD *)(a2 + 24) );
          v12 = 0;
        }
LABEL_17:
        v15 = SysStringLen(*(BSTR *)(a1 + 152));
        ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, *(const unsigned __int16 **)(a1 + 152), v15);
        v16 = -1;
        do
          ++v16;
        while ( v12[v16] );
        ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, v12, v16);
        v17 = CCollectionArray::DeleteByData((CCollectionArray *)a2, v9);
        if ( v17 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049E10[0] )
            bidTraceW(off_180049218, 1027072, off_180049E10[0], v17, 1003);
        }
        else
        {
          CCollectionMap::DeleteByData((CCollectionMap *)(a2 + 24), v9);
        }
        v18 = pbstr;
        v19 = SysStringLen(pbstr);
        CCollectionList::Append((CCollectionList *)a2, v18, v19, v9);
        *((_QWORD *)v11 + 75) = a1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 8LL))(*(_QWORD *)(a1 + 448));
        v4 = v24;
        *v24 = v11;
        *(_BYTE *)(v9 + 16) = 0;
        SysFreeString(v18);
      }
      v7 = CRowset::Init(v11);
      if ( v7 < 0 )
        return (unsigned int)v7;
      CRowset::CheckThreadModel(v11, v23);
      v20 = *((_QWORD *)v11 + 79);
      if ( v20 )
        CXMLReader::InitRowsets(a1, v20, v23, v4);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026dc0  mov     [rsp+arg_0], rbx
0x180026dc5  mov     [rsp+arg_18], r9
0x180026dca  mov     [rsp+arg_10], r8
0x180026dcf  push    rbp
0x180026dd0  push    rsi
0x180026dd1  push    rdi
0x180026dd2  push    r12
0x180026dd4  push    r13
0x180026dd6  push    r14
0x180026dd8  push    r15
0x180026dda  sub     rsp, 30h
0x180026dde  mov     r15, r9
0x180026de1  mov     r14, rdx
0x180026de4  mov     r13, rcx
0x180026de7  xor     r9d, r9d
0x180026dea  mov     ebx, r9d
0x180026ded  mov     r12d, [rdx+10h]
0x180026df1  mov     edi, r9d
0x180026df4  mov     esi, r9d
0x180026df7  test    r12d, r12d
0x180026dfa  jz      loc_180026FFD
0x180026e00  cmp     esi, [r14+10h]
0x180026e04  jb      short loc_180026E0D
0x180026e06  mov     ebx, 1
0x180026e0b  jmp     short loc_180026E1A
0x180026e0d  mov     ecx, esi
0x180026e0f  mov     rax, [r14+8]
0x180026e13  mov     rdi, [rax+rcx*8]
0x180026e17  mov     ebx, r9d
0x180026e1a  cmp     dword ptr [rdi], 1
0x180026e1d  jnz     loc_180026FF2
0x180026e23  mov     rbp, [rdi+8]
0x180026e27  cmp     [r15], r9
0x180026e2a  jnz     loc_180026F95
0x180026e30  cmp     r12d, 1
0x180026e34  jz      short loc_180026E52
0x180026e36  mov     edx, 91h; unsigned int
0x180026e3b  mov     ecx, 80004005h; int
0x180026e40  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180026e45  mov     ebx, eax
0x180026e47  xor     r9d, r9d
0x180026e4a  test    eax, eax
0x180026e4c  js      loc_180026FFD
0x180026e52  mov     rbx, r9
0x180026e55  mov     [rsp+68h+pbstr], r9
0x180026e5a  lea     r15, [r14+18h]
0x180026e5e  cmp     [r15], r9d
0x180026e61  jbe     short loc_180026E94
0x180026e63  mov     edx, r9d
0x180026e66  mov     r8, [r15+8]
0x180026e6a  mov     eax, edx
0x180026e6c  mov     rcx, [r8+rax*8]
0x180026e70  test    rcx, rcx
0x180026e73  jz      short loc_180026E8A
0x180026e75  test    rcx, rcx
0x180026e78  jz      short loc_180026E8A
0x180026e7a  cmp     [rcx+10h], rdi
0x180026e7e  jz      loc_180026F21
0x180026e84  mov     rcx, [rcx+18h]
0x180026e88  jmp     short loc_180026E75
0x180026e8a  inc     edx
0x180026e8c  cmp     edx, [r15]
0x180026e8f  jb      short loc_180026E6A
0x180026e91  mov     rbx, r9
0x180026e94  mov     rcx, [r13+98h]; pbstr
0x180026e9b  call    cs:__imp_SysStringLen
0x180026ea2  nop     dword ptr [rax+rax+00h]
0x180026ea7  mov     r8d, eax; int
0x180026eaa  mov     rdx, [r13+98h]; unsigned __int16 *
0x180026eb1  lea     rcx, [rsp+68h+pbstr]; this
0x180026eb6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180026ebb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026ebf  xor     eax, eax
0x180026ec1  inc     r8; int
0x180026ec4  cmp     [rbx+r8*2], ax
0x180026ec9  jnz     short loc_180026EC1
0x180026ecb  mov     rdx, rbx; unsigned __int16 *
0x180026ece  lea     rcx, [rsp+68h+pbstr]; this
0x180026ed3  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180026ed8  mov     rdx, rdi; unsigned __int64
0x180026edb  mov     rcx, r14; this
0x180026ede  call    ?DeleteByData@CCollectionArray@@QEAAJ_K@Z; CCollectionArray::DeleteByData(unsigned __int64)
0x180026ee3  test    eax, eax
0x180026ee5  jz      short loc_180026F2A
0x180026ee7  test    byte ptr cs:_bidGblFlags, 2
0x180026eee  jz      short loc_180026F35
0x180026ef0  mov     rcx, cs:off_180049E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180026ef7  test    rcx, rcx
0x180026efa  jz      short loc_180026F35
0x180026efc  mov     [rsp+68h+var_48], 3EBh
0x180026f04  mov     r9d, eax
0x180026f07  mov     r8, cs:off_180049E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180026f0e  mov     edx, 0FAC00h
0x180026f13  mov     rcx, cs:off_180049218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180026f1a  call    _bidTraceW
0x180026f1f  jmp     short loc_180026F35
0x180026f21  mov     rbx, [rcx+8]
0x180026f25  jmp     loc_180026E94
0x180026f2a  mov     rdx, rdi; unsigned __int64
0x180026f2d  mov     rcx, r15; this
0x180026f30  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x180026f35  mov     rbx, [rsp+68h+pbstr]
0x180026f3a  mov     rcx, rbx; pbstr
0x180026f3d  call    cs:__imp_SysStringLen
0x180026f44  nop     dword ptr [rax+rax+00h]
0x180026f49  mov     r9, rdi; unsigned __int64
0x180026f4c  mov     r8d, eax; unsigned int
0x180026f4f  mov     rdx, rbx; unsigned __int16 *
0x180026f52  mov     rcx, r14; this
0x180026f55  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x180026f5a  mov     [rbp+258h], r13
0x180026f61  mov     rcx, [r13+1C0h]
0x180026f68  mov     rax, [rcx]
0x180026f6b  mov     rax, [rax+8]
0x180026f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f74  mov     r15, [rsp+68h+arg_18]
0x180026f7c  mov     [r15], rbp
0x180026f7f  xor     eax, eax
0x180026f81  mov     [rdi+10h], al
0x180026f84  mov     rcx, rbx; bstrString
0x180026f87  call    cs:__imp_SysFreeString
0x180026f8e  nop     dword ptr [rax+rax+00h]
0x180026f93  jmp     short loc_180026FAF
0x180026f95  mov     [rbp+258h], r13
0x180026f9c  mov     rcx, [r13+1C0h]
0x180026fa3  mov     rax, [rcx]
0x180026fa6  mov     rax, [rax+8]
0x180026faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026faf  mov     rcx, rbp; this
0x180026fb2  call    ?Init@CRowset@@QEAAJXZ; CRowset::Init(void)
0x180026fb7  mov     ebx, eax
0x180026fb9  test    eax, eax
0x180026fbb  js      short loc_180026FFD
0x180026fbd  mov     rdx, [rsp+68h+arg_10]; struct IUnknown *
0x180026fc5  mov     rcx, rbp; this
0x180026fc8  call    ?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z; CRowset::CheckThreadModel(IUnknown *)
0x180026fcd  mov     rdx, [rbp+278h]
0x180026fd4  xor     r9d, r9d
0x180026fd7  test    rdx, rdx
0x180026fda  jz      short loc_180026FF2
0x180026fdc  mov     r9, r15
0x180026fdf  mov     r8, [rsp+68h+arg_10]
0x180026fe7  mov     rcx, r13
0x180026fea  call    ?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z; CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)
0x180026fef  xor     r9d, r9d
0x180026ff2  inc     esi
0x180026ff4  cmp     esi, r12d
0x180026ff7  jb      loc_180026E00
0x180026ffd  mov     eax, ebx
0x180026fff  mov     rbx, [rsp+68h+arg_0]
0x180027004  add     rsp, 30h
0x180027008  pop     r15
0x18002700a  pop     r14
0x18002700c  pop     r13
0x18002700e  pop     r12
0x180027010  pop     rdi
0x180027011  pop     rsi
0x180027012  pop     rbp
0x180027013  retn
```
