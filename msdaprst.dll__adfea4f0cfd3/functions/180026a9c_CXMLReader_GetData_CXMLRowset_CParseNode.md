# CXMLReader::GetData(CXMLRowset *,CParseNode *)

- ea: `0x180026a9c`
- end: `0x180026c56`
- name: `?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAVCParseNode@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, struct CParseNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800263a4`

## callees

- `0x180026a9c`
- `0x180026d04`
- `0x18002851c`
- `0x180029dc0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180026acd`
- `OLEAUT32!__imp_SysStringLen` at `0x180026b1e`
- `OLEAUT32!__imp_SysStringLen` at `0x180026beb`
- `OLEAUT32!__imp_SysStringLen` at `0x180026acd`
- `OLEAUT32!__imp_SysStringLen` at `0x180026b1e`
- `OLEAUT32!__imp_SysStringLen` at `0x180026beb`

## pseudocode

```c
__int64 __fastcall CXMLReader::GetData(CXMLReader *this, struct CXMLRowset *a2, struct CParseNode *a3)
{
  _DWORD *v3; // r14
  OLECHAR *v5; // rcx
  CCollectionList *v8; // rbx
  UINT v9; // eax
  unsigned __int16 *v10; // rdx
  UINT v12; // eax
  int v13; // r15d
  __int64 v14; // rbx
  _QWORD *v15; // rdx
  BSTR *Value; // rax
  UINT v17; // eax
  unsigned int v18; // r14d
  __int64 v19; // rbx
  __int64 v20; // rdx
  unsigned __int64 v21; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v5 = (OLECHAR *)*((_QWORD *)a3 + 4);
  v21 = 0;
  if ( v5
    && (v8 = (CCollectionList *)*((_QWORD *)this + 17),
        v9 = SysStringLen(v5),
        v10 = (unsigned __int16 *)*((_QWORD *)a3 + 4),
        v22 = 0,
        CCollectionList::LookUpByKey(v8, v10, v9, &v22),
        (v3 = (_DWORD *)v22) != 0)
    || *((_DWORD *)this + 119) != 2 )
  {
    v12 = SysStringLen(*((BSTR *)a3 + 4));
    v13 = CCollectionList::LookUpByKey(
            (struct CXMLRowset *)((char *)a2 + 552),
            *((unsigned __int16 **)a3 + 4),
            v12,
            &v21);
    if ( v13 >= 0 )
    {
      if ( ((*((_DWORD *)this + 119) - 4) & 0xFFFFFFFB) != 0 )
        v14 = *(_QWORD *)(*((_QWORD *)a2 + 35) + 8LL * (unsigned int)v21);
      else
        v14 = *(_QWORD *)(*((_QWORD *)a2 + 36) + 8LL * (unsigned int)v21);
      if ( *v3 == 1 )
      {
        v15 = *(_QWORD **)(*((_QWORD *)a2 + 68) + 8LL * (unsigned int)v21);
        if ( !v15[2] )
        {
          v15[2] = a3;
          *(_QWORD *)(v14 + 8) = v15;
          *(_DWORD *)(*v15 + 612LL) = 0;
          *(_DWORD *)(*v15 + 248LL) = 0;
          *((_DWORD *)v15 + 2) = *((_DWORD *)a3 + 11);
        }
      }
      else
      {
        *(_DWORD *)(v14 + 4) = 0;
        *(_QWORD *)(v14 + 8) = *(_QWORD *)CParseNode::GetValue(a3);
        Value = (BSTR *)CParseNode::GetValue(a3);
        v17 = SysStringLen(*Value);
        *(_DWORD *)v14 = v17;
        if ( !v17 && *((_DWORD *)this + 119) == 2 && *((_DWORD *)a3 + 2) == 1 )
        {
          v18 = *((_DWORD *)this + 108);
          LODWORD(v19) = *((_DWORD *)a3 + 11);
          while ( 1 )
          {
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= v18 )
              break;
            v20 = *(_QWORD *)(*((_QWORD *)this + 53) + 8 * v19);
            if ( *(_DWORD *)(v20 + 8) == 2 && *(struct CParseNode **)(v20 + 16) == a3 )
              CXMLReader::ProcessRowsetAttribute(this, (struct CParseNode *)v20, a2);
          }
        }
      }
    }
    return (unsigned int)v13;
  }
  else
  {
    CXMLReader::ProcessRowsetAttribute(this, a3, a2);
    return 0;
  }
}

```

## disassembly

```asm
0x180026a9c  mov     [rsp+arg_0], rbx
0x180026aa1  push    rbp
0x180026aa2  push    rsi
0x180026aa3  push    rdi
0x180026aa4  push    r14
0x180026aa6  push    r15
0x180026aa8  sub     rsp, 20h
0x180026aac  xor     r14d, r14d
0x180026aaf  mov     rsi, rcx
0x180026ab2  mov     rcx, [r8+20h]; pbstr
0x180026ab6  mov     rdi, r8
0x180026ab9  mov     [rsp+48h+arg_10], r14
0x180026abe  mov     rbp, rdx
0x180026ac1  test    rcx, rcx
0x180026ac4  jz      short loc_180026AFC
0x180026ac6  mov     rbx, [rsi+88h]
0x180026acd  call    cs:__imp_SysStringLen
0x180026ad4  nop     dword ptr [rax+rax+00h]
0x180026ad9  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180026add  lea     r9, [rsp+48h+arg_18]; unsigned __int64 *
0x180026ae2  mov     r8d, eax; unsigned int
0x180026ae5  mov     [rsp+48h+arg_18], r14
0x180026aea  mov     rcx, rbx; this
0x180026aed  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026af2  mov     r14, [rsp+48h+arg_18]
0x180026af7  test    r14, r14
0x180026afa  jnz     short loc_180026B1A
0x180026afc  cmp     dword ptr [rsi+1DCh], 2
0x180026b03  jnz     short loc_180026B1A
0x180026b05  mov     r8, rbp; struct CXMLRowset *
0x180026b08  mov     rdx, rdi; struct CParseNode *
0x180026b0b  mov     rcx, rsi; this
0x180026b0e  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180026b13  xor     eax, eax
0x180026b15  jmp     loc_180026C44
0x180026b1a  mov     rcx, [rdi+20h]; pbstr
0x180026b1e  call    cs:__imp_SysStringLen
0x180026b25  nop     dword ptr [rax+rax+00h]
0x180026b2a  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180026b2e  lea     rcx, [rbp+228h]; this
0x180026b35  mov     r8d, eax; unsigned int
0x180026b38  lea     r9, [rsp+48h+arg_10]; unsigned __int64 *
0x180026b3d  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026b42  mov     r15d, eax
0x180026b45  test    eax, eax
0x180026b47  js      loc_180026C41
0x180026b4d  mov     ecx, [rsi+1DCh]
0x180026b53  mov     r8, [rsp+48h+arg_10]
0x180026b58  sub     ecx, 4
0x180026b5b  test    ecx, 0FFFFFFFBh
0x180026b61  jz      short loc_180026B73
0x180026b63  mov     rcx, [rbp+118h]
0x180026b6a  mov     edx, r8d
0x180026b6d  mov     rbx, [rcx+rdx*8]
0x180026b71  jmp     short loc_180026B81
0x180026b73  mov     rax, [rbp+120h]
0x180026b7a  mov     ecx, r8d
0x180026b7d  mov     rbx, [rax+rcx*8]
0x180026b81  cmp     dword ptr [r14], 1
0x180026b85  jnz     short loc_180026BCA
0x180026b87  mov     rax, [rbp+220h]
0x180026b8e  mov     ecx, r8d
0x180026b91  mov     rdx, [rax+rcx*8]
0x180026b95  cmp     qword ptr [rdx+10h], 0
0x180026b9a  jnz     loc_180026C41
0x180026ba0  mov     [rdx+10h], rdi
0x180026ba4  mov     [rbx+8], rdx
0x180026ba8  mov     rax, [rdx]
0x180026bab  mov     dword ptr [rax+264h], 0
0x180026bb5  mov     rax, [rdx]
0x180026bb8  mov     dword ptr [rax+0F8h], 0
0x180026bc2  mov     eax, [rdi+2Ch]
0x180026bc5  mov     [rdx+8], eax
0x180026bc8  jmp     short loc_180026C41
0x180026bca  mov     rcx, rdi; this
0x180026bcd  mov     dword ptr [rbx+4], 0
0x180026bd4  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180026bd9  mov     rcx, [rax]
0x180026bdc  mov     [rbx+8], rcx
0x180026be0  mov     rcx, rdi; this
0x180026be3  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180026be8  mov     rcx, [rax]; pbstr
0x180026beb  call    cs:__imp_SysStringLen
0x180026bf2  nop     dword ptr [rax+rax+00h]
0x180026bf7  mov     [rbx], eax
0x180026bf9  test    eax, eax
0x180026bfb  jnz     short loc_180026C41
0x180026bfd  cmp     dword ptr [rsi+1DCh], 2
0x180026c04  jnz     short loc_180026C41
0x180026c06  cmp     dword ptr [rdi+8], 1
0x180026c0a  jnz     short loc_180026C41
0x180026c0c  mov     r14d, [rsi+1B0h]
0x180026c13  mov     ebx, [rdi+2Ch]
0x180026c16  jmp     short loc_180026C3A
0x180026c18  mov     rax, [rsi+1A8h]
0x180026c1f  mov     rdx, [rax+rbx*8]; struct CParseNode *
0x180026c23  cmp     dword ptr [rdx+8], 2
0x180026c27  jnz     short loc_180026C3A
0x180026c29  cmp     [rdx+10h], rdi
0x180026c2d  jnz     short loc_180026C3A
0x180026c2f  mov     r8, rbp; struct CXMLRowset *
0x180026c32  mov     rcx, rsi; this
0x180026c35  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180026c3a  inc     ebx
0x180026c3c  cmp     ebx, r14d
0x180026c3f  jb      short loc_180026C18
0x180026c41  mov     eax, r15d
0x180026c44  mov     rbx, [rsp+48h+arg_0]
0x180026c49  add     rsp, 20h
0x180026c4d  pop     r15
0x180026c4f  pop     r14
0x180026c51  pop     rdi
0x180026c52  pop     rsi
0x180026c53  pop     rbp
0x180026c54  retn
```
